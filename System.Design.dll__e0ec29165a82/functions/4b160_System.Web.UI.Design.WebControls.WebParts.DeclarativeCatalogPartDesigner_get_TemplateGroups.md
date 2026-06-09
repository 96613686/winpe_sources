# System.Web.UI.Design.WebControls.WebParts.DeclarativeCatalogPartDesigner::get_TemplateGroups

- ea: `0x4b160`
- end: `0x4b1c5`
- name: `System.Web.UI.Design.WebControls.WebParts.DeclarativeCatalogPartDesigner::get_TemplateGroups`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x27f0`
- `0x10250`
- `0x11000`
- `0x11090`
- `0x11170`
- `0x4b160`

## string_xrefs

- `0x4b170`: `WebPartsTemplate`
- `0x4b191`: `WebPartsTemplate`
- `0x4b19c`: `WebPartsTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x4b160  ldarg.0
0x4b161  call     instance class System.Web.UI.Design.TemplateGroupCollection System.Web.UI.Design.ControlDesigner::get_TemplateGroups()
0x4b166  stloc.0
0x4b167  ldarg.0
0x4b168  ldfld    class System.Web.UI.Design.TemplateGroup System.Web.UI.Design.WebControls.WebParts.DeclarativeCatalogPartDesigner::_templateGroup
0x4b16d  brtrue.s loc_4B1B6
0x4b16f  ldarg.0
0x4b170  ldstr    aWebpartstempla// "WebPartsTemplate"
0x4b175  ldarg.0
0x4b176  ldfld    class [System.Web]System.Web.UI.WebControls.WebParts.DeclarativeCatalogPart System.Web.UI.Design.WebControls.WebParts.DeclarativeCatalogPartDesigner::_catalogPart
0x4b17b  callvirt instance class [System.Web]System.Web.UI.WebControls.Style [System.Web]System.Web.UI.WebControls.WebControl::get_ControlStyle()
0x4b180  newobj   instance void System.Web.UI.Design.TemplateGroup::.ctor(string groupName, class [System.Web]System.Web.UI.WebControls.Style groupStyle)
0x4b185  stfld    class System.Web.UI.Design.TemplateGroup System.Web.UI.Design.WebControls.WebParts.DeclarativeCatalogPartDesigner::_templateGroup
0x4b18a  ldarg.0
0x4b18b  ldfld    class System.Web.UI.Design.TemplateGroup System.Web.UI.Design.WebControls.WebParts.DeclarativeCatalogPartDesigner::_templateGroup
0x4b190  ldarg.0
0x4b191  ldstr    aWebpartstempla// "WebPartsTemplate"
0x4b196  ldarg.0
0x4b197  ldfld    class [System.Web]System.Web.UI.WebControls.WebParts.DeclarativeCatalogPart System.Web.UI.Design.WebControls.WebParts.DeclarativeCatalogPartDesigner::_catalogPart
0x4b19c  ldstr    aWebpartstempla// "WebPartsTemplate"
0x4b1a1  ldarg.0
0x4b1a2  ldfld    class [System.Web]System.Web.UI.WebControls.WebParts.DeclarativeCatalogPart System.Web.UI.Design.WebControls.WebParts.DeclarativeCatalogPartDesigner::_catalogPart
0x4b1a7  callvirt instance class [System.Web]System.Web.UI.WebControls.Style [System.Web]System.Web.UI.WebControls.WebControl::get_ControlStyle()
0x4b1ac  newobj   instance void System.Web.UI.Design.TemplateDefinition::.ctor(class System.Web.UI.Design.ControlDesigner designer, string name, object templatedObject, string templatePropertyName, class [System.Web]System.Web.UI.WebControls.Style style)
0x4b1b1  callvirt instance void System.Web.UI.Design.TemplateGroup::AddTemplateDefinition(class System.Web.UI.Design.TemplateDefinition templateDefinition)
0x4b1b6  ldloc.0
0x4b1b7  ldarg.0
0x4b1b8  ldfld    class System.Web.UI.Design.TemplateGroup System.Web.UI.Design.WebControls.WebParts.DeclarativeCatalogPartDesigner::_templateGroup
0x4b1bd  callvirt instance int32 System.Web.UI.Design.TemplateGroupCollection::Add(class System.Web.UI.Design.TemplateGroup group)
0x4b1c2  pop
0x4b1c3  ldloc.0
0x4b1c4  ret
```
