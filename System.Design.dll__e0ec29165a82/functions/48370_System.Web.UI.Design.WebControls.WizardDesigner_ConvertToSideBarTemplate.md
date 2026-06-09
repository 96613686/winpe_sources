# System.Web.UI.Design.WebControls.WizardDesigner::ConvertToSideBarTemplate

- ea: `0x48370`
- end: `0x4839a`
- name: `System.Web.UI.Design.WebControls.WizardDesigner::ConvertToSideBarTemplate`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1005c0`

## callees

- `0x48170`
- `0x584f0`
- `0x8ef40`

## string_xrefs

- `0x48371`: `Wizard_ConvertToSideBarTemplate`
- `0x48381`: `SideBarTemplate`
- `0x4838e`: `SideBarList`

## pseudocode

```c

```

## disassembly

```asm
0x48370  ldarg.0
0x48371  ldstr    aWizardConvertt_3// "Wizard_ConvertToSideBarTemplate"
0x48376  call     string System.Design.SR::GetString(string name)
0x4837b  ldarg.0
0x4837c  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x48381  ldstr    aSidebartemplat// "SideBarTemplate"
0x48386  ldc.i4.1
0x48387  newarr   [mscorlib]System.String
0x4838c  dup
0x4838d  ldc.i4.0
0x4838e  ldstr    aSidebarlist// "SideBarList"
0x48393  stelem.ref
0x48394  call     instance void System.Web.UI.Design.WebControls.WizardDesigner::ConvertToTemplate(string description, class [System]System.ComponentModel.IComponent component, string templateName, string[] keys)
0x48399  ret
```
