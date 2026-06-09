# System.Web.UI.Design.WebControls.WizardDesigner::PreFilterProperties

- ea: `0x489d0`
- end: `0x48b72`
- name: `System.Web.UI.Design.WebControls.WizardDesigner::PreFilterProperties`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1b9f0`

## callees

- `0x2660`
- `0x33d0`
- `0x48830`
- `0x489d0`

## string_xrefs

- `0x489d8`: `DisplaySideBar`
- `0x489ec`: `DisplaySideBar`

## pseudocode

```c

```

## disassembly

```asm
0x489d0  ldarg.0
0x489d1  ldarg.1
0x489d2  call     instance void System.Web.UI.Design.ControlDesigner::PreFilterProperties(class [mscorlib]System.Collections.IDictionary properties)
0x489d7  ldarg.1
0x489d8  ldstr    aDisplaysidebar// "DisplaySideBar"
0x489dd  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x489e2  castclass [System]System.ComponentModel.PropertyDescriptor
0x489e7  stloc.0
0x489e8  ldloc.0
0x489e9  brfalse.s loc_48A03
0x489eb  ldarg.1
0x489ec  ldstr    aDisplaysidebar// "DisplaySideBar"
0x489f1  ldarg.0
0x489f2  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x489f7  ldloc.0
0x489f8  ldnull
0x489f9  call     class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.TypeDescriptor::CreateProperty(class [mscorlib]System.Type, class [System]System.ComponentModel.PropertyDescriptor, class [mscorlib]System.Attribute[])
0x489fe  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x48a03  ldarg.0
0x48a04  call     instance bool System.Web.UI.Design.ControlDesigner::get_InTemplateMode()
0x48a09  brfalse.s loc_48A17
0x48a0b  ldarg.0
0x48a0c  ldarg.1
0x48a0d  ldstr    aWizardsteps// "WizardSteps"
0x48a12  call     instance void System.Web.UI.Design.WebControls.WizardDesigner::MarkPropertyNonBrowsable(class [mscorlib]System.Collections.IDictionary properties, string propName)
0x48a17  ldarg.0
0x48a18  ldfld    class [System.Web]System.Web.UI.WebControls.Wizard System.Web.UI.Design.WebControls.WizardDesigner::_wizard
0x48a1d  callvirt instance class [System.Web]System.Web.UI.ITemplate [System.Web]System.Web.UI.WebControls.Wizard::get_StartNavigationTemplate()
0x48a22  brfalse.s loc_48A44
0x48a24  ldsfld   string[] System.Web.UI.Design.WebControls.WizardDesigner::_startNavigationTemplateProperties
0x48a29  stloc.1
0x48a2a  ldc.i4.0
0x48a2b  stloc.2
0x48a2c  br.s     loc_48A3E
0x48a2e  ldloc.1
0x48a2f  ldloc.2
0x48a30  ldelem.ref
0x48a31  stloc.3
0x48a32  ldarg.0
0x48a33  ldarg.1
0x48a34  ldloc.3
0x48a35  call     instance void System.Web.UI.Design.WebControls.WizardDesigner::MarkPropertyNonBrowsable(class [mscorlib]System.Collections.IDictionary properties, string propName)
0x48a3a  ldloc.2
0x48a3b  ldc.i4.1
0x48a3c  add
0x48a3d  stloc.2
0x48a3e  ldloc.2
0x48a3f  ldloc.1
0x48a40  ldlen
0x48a41  conv.i4
0x48a42  blt.s    loc_48A2E
0x48a44  ldarg.0
0x48a45  ldfld    class [System.Web]System.Web.UI.WebControls.Wizard System.Web.UI.Design.WebControls.WizardDesigner::_wizard
0x48a4a  callvirt instance class [System.Web]System.Web.UI.ITemplate [System.Web]System.Web.UI.WebControls.Wizard::get_StepNavigationTemplate()
0x48a4f  brfalse.s loc_48A7B
0x48a51  ldsfld   string[] System.Web.UI.Design.WebControls.WizardDesigner::_stepNavigationTemplateProperties
0x48a56  stloc.s  4
0x48a58  ldc.i4.0
0x48a59  stloc.s  5
0x48a5b  br.s     loc_48A73
0x48a5d  ldloc.s  4
0x48a5f  ldloc.s  5
0x48a61  ldelem.ref
0x48a62  stloc.s  6
0x48a64  ldarg.0
0x48a65  ldarg.1
0x48a66  ldloc.s  6
0x48a68  call     instance void System.Web.UI.Design.WebControls.WizardDesigner::MarkPropertyNonBrowsable(class [mscorlib]System.Collections.IDictionary properties, string propName)
0x48a6d  ldloc.s  5
0x48a6f  ldc.i4.1
0x48a70  add
0x48a71  stloc.s  5
0x48a73  ldloc.s  5
0x48a75  ldloc.s  4
0x48a77  ldlen
0x48a78  conv.i4
0x48a79  blt.s    loc_48A5D
0x48a7b  ldarg.0
0x48a7c  ldfld    class [System.Web]System.Web.UI.WebControls.Wizard System.Web.UI.Design.WebControls.WizardDesigner::_wizard
0x48a81  callvirt instance class [System.Web]System.Web.UI.ITemplate [System.Web]System.Web.UI.WebControls.Wizard::get_FinishNavigationTemplate()
0x48a86  brfalse.s loc_48AB2
0x48a88  ldsfld   string[] System.Web.UI.Design.WebControls.WizardDesigner::_finishNavigationTemplateProperties
0x48a8d  stloc.s  7
0x48a8f  ldc.i4.0
0x48a90  stloc.s  8
0x48a92  br.s     loc_48AAA
0x48a94  ldloc.s  7
0x48a96  ldloc.s  8
0x48a98  ldelem.ref
0x48a99  stloc.s  9
0x48a9b  ldarg.0
0x48a9c  ldarg.1
0x48a9d  ldloc.s  9
0x48a9f  call     instance void System.Web.UI.Design.WebControls.WizardDesigner::MarkPropertyNonBrowsable(class [mscorlib]System.Collections.IDictionary properties, string propName)
0x48aa4  ldloc.s  8
0x48aa6  ldc.i4.1
0x48aa7  add
0x48aa8  stloc.s  8
0x48aaa  ldloc.s  8
0x48aac  ldloc.s  7
0x48aae  ldlen
0x48aaf  conv.i4
0x48ab0  blt.s    loc_48A94
0x48ab2  ldarg.0
0x48ab3  ldfld    class [System.Web]System.Web.UI.WebControls.Wizard System.Web.UI.Design.WebControls.WizardDesigner::_wizard
0x48ab8  callvirt instance class [System.Web]System.Web.UI.ITemplate [System.Web]System.Web.UI.WebControls.Wizard::get_StartNavigationTemplate()
0x48abd  brfalse.s loc_48B03
0x48abf  ldarg.0
0x48ac0  ldfld    class [System.Web]System.Web.UI.WebControls.Wizard System.Web.UI.Design.WebControls.WizardDesigner::_wizard
0x48ac5  callvirt instance class [System.Web]System.Web.UI.ITemplate [System.Web]System.Web.UI.WebControls.Wizard::get_StepNavigationTemplate()
0x48aca  brfalse.s loc_48B03
0x48acc  ldarg.0
0x48acd  ldfld    class [System.Web]System.Web.UI.WebControls.Wizard System.Web.UI.Design.WebControls.WizardDesigner::_wizard
0x48ad2  callvirt instance class [System.Web]System.Web.UI.ITemplate [System.Web]System.Web.UI.WebControls.Wizard::get_FinishNavigationTemplate()
0x48ad7  brfalse.s loc_48B03
0x48ad9  ldsfld   string[] System.Web.UI.Design.WebControls.WizardDesigner::_generalNavigationButtonProperties
0x48ade  stloc.s  0xA
0x48ae0  ldc.i4.0
0x48ae1  stloc.s  0xB
0x48ae3  br.s     loc_48AFB
0x48ae5  ldloc.s  0xA
0x48ae7  ldloc.s  0xB
0x48ae9  ldelem.ref
0x48aea  stloc.s  0xC
0x48aec  ldarg.0
0x48aed  ldarg.1
0x48aee  ldloc.s  0xC
0x48af0  call     instance void System.Web.UI.Design.WebControls.WizardDesigner::MarkPropertyNonBrowsable(class [mscorlib]System.Collections.IDictionary properties, string propName)
0x48af5  ldloc.s  0xB
0x48af7  ldc.i4.1
0x48af8  add
0x48af9  stloc.s  0xB
0x48afb  ldloc.s  0xB
0x48afd  ldloc.s  0xA
0x48aff  ldlen
0x48b00  conv.i4
0x48b01  blt.s    loc_48AE5
0x48b03  ldarg.0
0x48b04  ldfld    class [System.Web]System.Web.UI.WebControls.Wizard System.Web.UI.Design.WebControls.WizardDesigner::_wizard
0x48b09  callvirt instance class [System.Web]System.Web.UI.ITemplate [System.Web]System.Web.UI.WebControls.Wizard::get_HeaderTemplate()
0x48b0e  brfalse.s loc_48B3A
0x48b10  ldsfld   string[] System.Web.UI.Design.WebControls.WizardDesigner::_headerProperties
0x48b15  stloc.s  0xD
0x48b17  ldc.i4.0
0x48b18  stloc.s  0xE
0x48b1a  br.s     loc_48B32
0x48b1c  ldloc.s  0xD
0x48b1e  ldloc.s  0xE
0x48b20  ldelem.ref
0x48b21  stloc.s  0xF
0x48b23  ldarg.0
0x48b24  ldarg.1
0x48b25  ldloc.s  0xF
0x48b27  call     instance void System.Web.UI.Design.WebControls.WizardDesigner::MarkPropertyNonBrowsable(class [mscorlib]System.Collections.IDictionary properties, string propName)
0x48b2c  ldloc.s  0xE
0x48b2e  ldc.i4.1
0x48b2f  add
0x48b30  stloc.s  0xE
0x48b32  ldloc.s  0xE
0x48b34  ldloc.s  0xD
0x48b36  ldlen
0x48b37  conv.i4
0x48b38  blt.s    loc_48B1C
0x48b3a  ldarg.0
0x48b3b  ldfld    class [System.Web]System.Web.UI.WebControls.Wizard System.Web.UI.Design.WebControls.WizardDesigner::_wizard
0x48b40  callvirt instance class [System.Web]System.Web.UI.ITemplate [System.Web]System.Web.UI.WebControls.Wizard::get_SideBarTemplate()
0x48b45  brfalse.s loc_48B71
0x48b47  ldsfld   string[] System.Web.UI.Design.WebControls.WizardDesigner::_sideBarProperties
0x48b4c  stloc.s  0x10
0x48b4e  ldc.i4.0
0x48b4f  stloc.s  0x11
0x48b51  br.s     loc_48B69
0x48b53  ldloc.s  0x10
0x48b55  ldloc.s  0x11
0x48b57  ldelem.ref
0x48b58  stloc.s  0x12
0x48b5a  ldarg.0
0x48b5b  ldarg.1
0x48b5c  ldloc.s  0x12
0x48b5e  call     instance void System.Web.UI.Design.WebControls.WizardDesigner::MarkPropertyNonBrowsable(class [mscorlib]System.Collections.IDictionary properties, string propName)
0x48b63  ldloc.s  0x11
0x48b65  ldc.i4.1
0x48b66  add
0x48b67  stloc.s  0x11
0x48b69  ldloc.s  0x11
0x48b6b  ldloc.s  0x10
0x48b6d  ldlen
0x48b6e  conv.i4
0x48b6f  blt.s    loc_48B53
0x48b71  ret
```
