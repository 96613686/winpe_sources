# System.Windows.Forms.Design.DesignBindingPicker::Pick

- ea: `0xae270`
- end: `0xae442`
- name: `System.Windows.Forms.Design.DesignBindingPicker::Pick`
- size: `466`
- prototype: ``
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x97070`
- `0xa6840`
- `0xa6bf0`
- `0xab910`
- `0xad680`
- `0xad740`
- `0xad9d0`
- `0xaddd0`
- `0xbb5d0`

## callees

- `0x70cb0`
- `0xae270`
- `0xae4b0`
- `0xae4f0`
- `0xaf310`

## string_xrefs

- `0xae35a`: `VsColorPanelHyperLink`
- `0xae377`: `VsColorPanelHyperLink`
- `0xae391`: `VsColorPanelHyperLinkPressed`
- `0xae3ae`: `VsColorPanelHyperLinkPressed`

## pseudocode

```c

```

## disassembly

```asm
0xae270  ldarg.0
0xae271  ldarg.2
0xae272  stfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.DesignBindingPicker::serviceProvider
0xae277  ldarg.0
0xae278  ldarg.0
0xae279  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.DesignBindingPicker::serviceProvider
0xae27e  ldtoken  [System.Windows.Forms]System.Windows.Forms.Design.IWindowsFormsEditorService
0xae283  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xae288  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xae28d  castclass [System.Windows.Forms]System.Windows.Forms.Design.IWindowsFormsEditorService
0xae292  stfld    class [System.Windows.Forms]System.Windows.Forms.Design.IWindowsFormsEditorService System.Windows.Forms.Design.DesignBindingPicker::edSvc
0xae297  ldarg.0
0xae298  ldarg.0
0xae299  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.DesignBindingPicker::serviceProvider
0xae29e  ldtoken  System.ComponentModel.Design.Data.DataSourceProviderService
0xae2a3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xae2a8  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xae2ad  castclass System.ComponentModel.Design.Data.DataSourceProviderService
0xae2b2  stfld    class System.ComponentModel.Design.Data.DataSourceProviderService System.Windows.Forms.Design.DesignBindingPicker::dspSvc
0xae2b7  ldarg.0
0xae2b8  ldarg.0
0xae2b9  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.DesignBindingPicker::serviceProvider
0xae2be  ldtoken  [System]System.ComponentModel.Design.ITypeResolutionService
0xae2c3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xae2c8  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xae2cd  castclass [System]System.ComponentModel.Design.ITypeResolutionService
0xae2d2  stfld    class [System]System.ComponentModel.Design.ITypeResolutionService System.Windows.Forms.Design.DesignBindingPicker::typeSvc
0xae2d7  ldarg.0
0xae2d8  ldarg.0
0xae2d9  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.DesignBindingPicker::serviceProvider
0xae2de  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0xae2e3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xae2e8  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xae2ed  castclass [System]System.ComponentModel.Design.IDesignerHost
0xae2f2  stfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.DesignBindingPicker::hostSvc
0xae2f7  ldarg.0
0xae2f8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Design.IWindowsFormsEditorService System.Windows.Forms.Design.DesignBindingPicker::edSvc
0xae2fd  brtrue.s loc_AE301
0xae2ff  ldnull
0xae300  ret
0xae301  ldarg.0
0xae302  ldarg.1
0xae303  stfld    class [System]System.ComponentModel.ITypeDescriptorContext System.Windows.Forms.Design.DesignBindingPicker::context
0xae308  ldarg.0
0xae309  ldarg.3
0xae30a  stfld    bool System.Windows.Forms.Design.DesignBindingPicker::showDataSources
0xae30f  ldarg.0
0xae310  ldarg.s  4
0xae312  stfld    bool System.Windows.Forms.Design.DesignBindingPicker::showDataMembers
0xae317  ldarg.0
0xae318  ldarg.s  4
0xae31a  brtrue.s loc_AE31F
0xae31c  ldc.i4.1
0xae31d  br.s     loc_AE321
0xae31f  ldarg.s  5
0xae321  stfld    bool System.Windows.Forms.Design.DesignBindingPicker::selectListMembers
0xae326  ldarg.0
0xae327  ldarg.s  6
0xae329  stfld    object System.Windows.Forms.Design.DesignBindingPicker::rootDataSource
0xae32e  ldarg.0
0xae32f  ldarg.s  7
0xae331  stfld    string System.Windows.Forms.Design.DesignBindingPicker::rootDataMember
0xae336  ldarg.0
0xae337  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.DesignBindingPicker::serviceProvider
0xae33c  ldtoken  [System.Windows.Forms]System.Windows.Forms.Design.IUIService
0xae341  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xae346  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xae34b  isinst   [System.Windows.Forms]System.Windows.Forms.Design.IUIService
0xae350  stloc.0
0xae351  ldloc.0
0xae352  brfalse.s loc_AE3C2
0xae354  ldloc.0
0xae355  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0xae35a  ldstr    aVscolorpanelhy// "VsColorPanelHyperLink"
0xae35f  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0xae364  isinst   [System.Drawing]System.Drawing.Color
0xae369  brfalse.s loc_AE38B
0xae36b  ldarg.0
0xae36c  ldfld    class BindingPickerLink System.Windows.Forms.Design.DesignBindingPicker::addNewCtrl
0xae371  ldloc.0
0xae372  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0xae377  ldstr    aVscolorpanelhy// "VsColorPanelHyperLink"
0xae37c  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0xae381  unbox.any [System.Drawing]System.Drawing.Color
0xae386  callvirt instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::set_LinkColor(valuetype [System.Drawing]System.Drawing.Color)
0xae38b  ldloc.0
0xae38c  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0xae391  ldstr    aVscolorpanelhy_0// "VsColorPanelHyperLinkPressed"
0xae396  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0xae39b  isinst   [System.Drawing]System.Drawing.Color
0xae3a0  brfalse.s loc_AE3C2
0xae3a2  ldarg.0
0xae3a3  ldfld    class BindingPickerLink System.Windows.Forms.Design.DesignBindingPicker::addNewCtrl
0xae3a8  ldloc.0
0xae3a9  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0xae3ae  ldstr    aVscolorpanelhy_0// "VsColorPanelHyperLinkPressed"
0xae3b3  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0xae3b8  unbox.any [System.Drawing]System.Drawing.Color
0xae3bd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::set_ActiveLinkColor(valuetype [System.Drawing]System.Drawing.Color)
0xae3c2  ldarg.0
0xae3c3  ldarg.s  8
0xae3c5  call     instance void System.Windows.Forms.Design.DesignBindingPicker::FillTree(class System.Windows.Forms.Design.DesignBinding initialSelectedItem)
0xae3ca  ldarg.0
0xae3cb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Windows.Forms.Design.DesignBindingPicker::addNewPanel
0xae3d0  ldarg.3
0xae3d1  brfalse.s loc_AE3E8
0xae3d3  ldarg.0
0xae3d4  ldfld    class System.ComponentModel.Design.Data.DataSourceProviderService System.Windows.Forms.Design.DesignBindingPicker::dspSvc
0xae3d9  brfalse.s loc_AE3E8
0xae3db  ldarg.0
0xae3dc  ldfld    class System.ComponentModel.Design.Data.DataSourceProviderService System.Windows.Forms.Design.DesignBindingPicker::dspSvc
0xae3e1  callvirt instance bool System.ComponentModel.Design.Data.DataSourceProviderService::get_SupportsAddNewDataSource()
0xae3e6  br.s     loc_AE3E9
0xae3e8  ldc.i4.0
0xae3e9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0xae3ee  ldarg.0
0xae3ef  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Windows.Forms.Design.DesignBindingPicker::helpTextPanel
0xae3f4  ldarg.3
0xae3f5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0xae3fa  ldarg.0
0xae3fb  ldnull
0xae3fc  call     instance void System.Windows.Forms.Design.DesignBindingPicker::UpdateHelpText(class BindingPickerNode mouseNode)
0xae401  ldarg.0
0xae402  ldfld    class [System.Windows.Forms]System.Windows.Forms.Design.IWindowsFormsEditorService System.Windows.Forms.Design.DesignBindingPicker::edSvc
0xae407  ldarg.0
0xae408  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Design.IWindowsFormsEditorService::DropDownControl(class [System.Windows.Forms]System.Windows.Forms.Control)
0xae40d  ldarg.0
0xae40e  ldfld    class System.Windows.Forms.Design.DesignBinding System.Windows.Forms.Design.DesignBindingPicker::selectedItem
0xae413  stloc.1
0xae414  ldarg.0
0xae415  ldnull
0xae416  stfld    class System.Windows.Forms.Design.DesignBinding System.Windows.Forms.Design.DesignBindingPicker::selectedItem
0xae41b  ldarg.0
0xae41c  call     instance void System.Windows.Forms.Design.DesignBindingPicker::EmptyTree()
0xae421  ldarg.0
0xae422  ldnull
0xae423  stfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.DesignBindingPicker::serviceProvider
0xae428  ldarg.0
0xae429  ldnull
0xae42a  stfld    class [System.Windows.Forms]System.Windows.Forms.Design.IWindowsFormsEditorService System.Windows.Forms.Design.DesignBindingPicker::edSvc
0xae42f  ldarg.0
0xae430  ldnull
0xae431  stfld    class System.ComponentModel.Design.Data.DataSourceProviderService System.Windows.Forms.Design.DesignBindingPicker::dspSvc
0xae436  ldarg.0
0xae437  ldnull
0xae438  stfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.DesignBindingPicker::hostSvc
0xae43d  ldnull
0xae43e  starg.s  1
0xae440  ldloc.1
0xae441  ret
```
