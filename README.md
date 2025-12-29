d# SKButton - Custom Canvas Button for Xojo 2025 R3 (API 2.0)

A highly customizable, modern button control built as a subclass of `DesktopCanvas`. Designed to overcome the limitations of the standard `DesktopButton` while providing native-like behavior and appearance.  

<img width="402" height="321" alt="Screenshot 2025-12-29 at 23 09 05" src="https://github.com/user-attachments/assets/bbeff80b-ccfe-4347-95a1-6380a739891f" />
<img width="402" height="321" alt="Screenshot 2025-12-29 at 23 08 46" src="https://github.com/user-attachments/assets/0b210663-6638-4496-9248-2f1a35f8ba9b" />

## Features

- **Full styling control**  
  Background, hover, pressed colors, border thickness/color, corner radius
- **SVG + Raster icon support**  
  Crisp scaling at any size/DPI using native `Picture.FromData`
- **Flexible icon placement**  
  Left, Right, Above, Below the caption
- **Smart icon + text spacing**  
  Automatic proportional padding when `IconPadding = 0`
- **Content alignment**  
  Left / Center / Right alignment of the entire icon+text group
- **Professional interaction**  
  Hover, pressed (armed) states with proper cancel-on-drag-out behavior
- **Keyboard support**  
  Space/Enter activation (built-in via existing KeyDown handling)
- **Disabled state**  
  Automatic graying of background, text, border, and icon
- **Light / Dark mode aware**  
  Base colors are automatically adapted using simple inversion + system text color
- **Instance-encapsulated Action event**  
  Double-click the `Action` event on an instance to add code directly inside the button (just like native controls)

## Requirements

- Xojo 2025 R3 or later
- API 2.0 enabled
- For dark mode support: enable **Supports Dark Mode** in Project → Shared Build Settings

## Installation
Copy/paste or drag/drop from sample project or import the binary.

## Events

- **Action** – Raised when the button is clicked (mouse release inside bounds or Space/Enter key). Add handler directly on the button instance.

## Properties (Visible in Inspector)

| Group                  | Property             | Description                                                                 |
|------------------------|----------------------|-----------------------------------------------------------------------------|
| Appearance             | BaseBackColor        | Background in light mode (adapted in dark mode)                              |
|                        | BaseHoverColor       | Hover state color (adapted)                                                  |
|                        | BasePressedColor     | Pressed state color (adapted)                                                |
|                        | BorderColor          | Border color                                                                |
|                        | BorderThickness      | Border width in pixels                                                      |
|                        | CornerRadius         | Rounded corner radius                                                       |
| Text                   | Text                 | Button caption                                                              |
|                        | TextColor            | Text color (BaseTextColor – adapted automatically)                           |
|                        | TextFontName         | Font family                                                                 |
|                        | TextSize             | Font size                                                                   |
|                        | TextBold / Italic / Underline | Style flags                                                |
| Layout                 | IconAlignment        | 0=Left, 1=Right, 2=Above, 3=Below                                       |
|                        | ContentAlignment     | 0=Left, 1=Center (default), 2=Right alignment of icon+text group            |
| Icon                   | IconSVG              | Raw SVG XML string (recommended for scalable icons)                         |
|                        | IconPicture          | Traditional raster Picture (fallback)                                        |
|                        | IconPadding          | Pixels between icon and text. 0 = automatic scaling (recommended)           |


<img width="283" height="597" alt="Screenshot 2025-12-29 at 22 58 42" src="https://github.com/user-attachments/assets/cdce9ffe-8e8d-4446-a675-a14e802c53f1" />


## Example Usage

```xojo
// In a window, after placing SKButton1
SKButton1.Text = "Like"
SKButton1.BaseBackColor = &c0077FF00   // Blue
SKButton1.BaseTextColor = &cFFFFFF00   // White text
SKButton1.IconSVG = kHeartSVG         // Const with SVG string
SKButton1.IconAlignment = 0           // Icon left of text
SKButton1.IconPadding = 0             // Auto spacing
SKButton1.ContentAlignment = 1        // Center
SKButton1.CornerRadius = 12
