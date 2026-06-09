# System.Web.UI.Design.WebControls.WizardDesigner::ResetSideBarTemplate

- ea: `0x48c60`
- end: `0x48c7c`
- name: `System.Web.UI.Design.WebControls.WizardDesigner::ResetSideBarTemplate`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x100610`

## callees

- `0x48c80`
- `0x584f0`
- `0x8ef40`

## string_xrefs

- `0x48c71`: `SideBarTemplate`
- `0x48c61`: `Wizard_ResetSideBarTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x48c60  ldarg.0
0x48c61  ldstr    aWizardResetsid// "Wizard_ResetSideBarTemplate"
0x48c66  call     string System.Design.SR::GetString(string name)
0x48c6b  ldarg.0
0x48c6c  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x48c71  ldstr    aSidebartemplat// "SideBarTemplate"
0x48c76  call     instance void System.Web.UI.Design.WebControls.WizardDesigner::ResetTemplate(string description, class [System]System.ComponentModel.IComponent component, string templateName)
0x48c7b  ret
```
