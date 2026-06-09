# System.Web.UI.Design.WebControls.LoginDesigner::get_TemplateGroups

- ea: `0x29340`
- end: `0x29398`
- name: `System.Web.UI.Design.WebControls.LoginDesigner::get_TemplateGroups`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x27f0`
- `0x2840`
- `0x10250`
- `0x11000`
- `0x11090`
- `0x11170`

## string_xrefs

- `0x29347`: `LayoutTemplate`
- `0x29364`: `LayoutTemplate`
- `0x2936f`: `LayoutTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x29340  ldarg.0
0x29341  call     instance class System.Web.UI.Design.TemplateGroupCollection System.Web.UI.Design.ControlDesigner::get_TemplateGroups()
0x29346  stloc.0
0x29347  ldstr    aLayouttemplate// "LayoutTemplate"
0x2934c  ldarg.0
0x2934d  call     instance class [System.Web]System.Web.UI.Control System.Web.UI.Design.ControlDesigner::get_ViewControl()
0x29352  castclass [System.Web]System.Web.UI.WebControls.WebControl
0x29357  callvirt instance class [System.Web]System.Web.UI.WebControls.Style [System.Web]System.Web.UI.WebControls.WebControl::get_ControlStyle()
0x2935c  newobj   instance void System.Web.UI.Design.TemplateGroup::.ctor(string groupName, class [System.Web]System.Web.UI.WebControls.Style groupStyle)
0x29361  stloc.1
0x29362  ldloc.1
0x29363  ldarg.0
0x29364  ldstr    aLayouttemplate// "LayoutTemplate"
0x29369  ldarg.0
0x2936a  ldfld    class [System.Web]System.Web.UI.WebControls.Login System.Web.UI.Design.WebControls.LoginDesigner::_login
0x2936f  ldstr    aLayouttemplate// "LayoutTemplate"
0x29374  ldarg.0
0x29375  call     instance class [System.Web]System.Web.UI.Control System.Web.UI.Design.ControlDesigner::get_ViewControl()
0x2937a  castclass [System.Web]System.Web.UI.WebControls.WebControl
0x2937f  callvirt instance class [System.Web]System.Web.UI.WebControls.Style [System.Web]System.Web.UI.WebControls.WebControl::get_ControlStyle()
0x29384  newobj   instance void System.Web.UI.Design.TemplateDefinition::.ctor(class System.Web.UI.Design.ControlDesigner designer, string name, object templatedObject, string templatePropertyName, class [System.Web]System.Web.UI.WebControls.Style style)
0x29389  callvirt instance void System.Web.UI.Design.TemplateGroup::AddTemplateDefinition(class System.Web.UI.Design.TemplateDefinition templateDefinition)
0x2938e  ldloc.0
0x2938f  ldloc.1
0x29390  callvirt instance int32 System.Web.UI.Design.TemplateGroupCollection::Add(class System.Web.UI.Design.TemplateGroup group)
0x29395  pop
0x29396  ldloc.0
0x29397  ret
```
