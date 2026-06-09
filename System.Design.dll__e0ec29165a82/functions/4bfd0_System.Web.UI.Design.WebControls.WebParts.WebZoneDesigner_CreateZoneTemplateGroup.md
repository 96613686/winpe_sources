# System.Web.UI.Design.WebControls.WebParts.WebZoneDesigner::CreateZoneTemplateGroup

- ea: `0x4bfd0`
- end: `0x4c019`
- name: `System.Web.UI.Design.WebControls.WebParts.WebZoneDesigner::CreateZoneTemplateGroup`
- size: `73`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x4ada0`
- `0x4b7a0`
- `0x4bdd0`

## callees

- `0x2840`
- `0x10250`
- `0x11000`
- `0x11090`
- `0x584f0`

## string_xrefs

- `0x4bfd0`: `ZoneTemplate`
- `0x4bfed`: `ZoneTemplate`
- `0x4bff8`: `ZoneTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x4bfd0  ldstr    aZonetemplate// "ZoneTemplate"
0x4bfd5  ldarg.0
0x4bfd6  call     instance class [System.Web]System.Web.UI.Control System.Web.UI.Design.ControlDesigner::get_ViewControl()
0x4bfdb  castclass [System.Web]System.Web.UI.WebControls.WebControl
0x4bfe0  callvirt instance class [System.Web]System.Web.UI.WebControls.Style [System.Web]System.Web.UI.WebControls.WebControl::get_ControlStyle()
0x4bfe5  newobj   instance void System.Web.UI.Design.TemplateGroup::.ctor(string groupName, class [System.Web]System.Web.UI.WebControls.Style groupStyle)
0x4bfea  stloc.0
0x4bfeb  ldloc.0
0x4bfec  ldarg.0
0x4bfed  ldstr    aZonetemplate// "ZoneTemplate"
0x4bff2  ldarg.0
0x4bff3  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x4bff8  ldstr    aZonetemplate// "ZoneTemplate"
0x4bffd  ldarg.0
0x4bffe  call     instance class [System.Web]System.Web.UI.Control System.Web.UI.Design.ControlDesigner::get_ViewControl()
0x4c003  castclass [System.Web]System.Web.UI.WebControls.WebControl
0x4c008  callvirt instance class [System.Web]System.Web.UI.WebControls.Style [System.Web]System.Web.UI.WebControls.WebControl::get_ControlStyle()
0x4c00d  newobj   instance void System.Web.UI.Design.TemplateDefinition::.ctor(class System.Web.UI.Design.ControlDesigner designer, string name, object templatedObject, string templatePropertyName, class [System.Web]System.Web.UI.WebControls.Style style)
0x4c012  callvirt instance void System.Web.UI.Design.TemplateGroup::AddTemplateDefinition(class System.Web.UI.Design.TemplateDefinition templateDefinition)
0x4c017  ldloc.0
0x4c018  ret
```
