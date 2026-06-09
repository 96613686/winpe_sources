# System.Web.UI.Design.WebControls.WebParts.WebZoneDesigner::get_TemplateDefinition

- ea: `0x4bfa0`
- end: `0x4bfc8`
- name: `System.Web.UI.Design.WebControls.WebParts.WebZoneDesigner::get_TemplateDefinition`
- size: `40`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x4ade0`
- `0x4b7e0`
- `0x4be10`

## callees

- `0x2840`
- `0x10270`
- `0x584f0`

## string_xrefs

- `0x4bfa1`: `ZoneTemplate`
- `0x4bfac`: `ZoneTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x4bfa0  ldarg.0
0x4bfa1  ldstr    aZonetemplate// "ZoneTemplate"
0x4bfa6  ldarg.0
0x4bfa7  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x4bfac  ldstr    aZonetemplate// "ZoneTemplate"
0x4bfb1  ldarg.0
0x4bfb2  call     instance class [System.Web]System.Web.UI.Control System.Web.UI.Design.ControlDesigner::get_ViewControl()
0x4bfb7  castclass [System.Web]System.Web.UI.WebControls.WebControl
0x4bfbc  callvirt instance class [System.Web]System.Web.UI.WebControls.Style [System.Web]System.Web.UI.WebControls.WebControl::get_ControlStyle()
0x4bfc1  ldc.i4.1
0x4bfc2  newobj   instance void System.Web.UI.Design.TemplateDefinition::.ctor(class System.Web.UI.Design.ControlDesigner designer, string name, object templatedObject, string templatePropertyName, class [System.Web]System.Web.UI.WebControls.Style style, bool serverControlsOnly)
0x4bfc7  ret
```
