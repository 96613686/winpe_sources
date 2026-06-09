# CollectionEditorCollectionForm::InitializeComponent

- ea: `0x104ab0`
- end: `0x10505d`
- name: `CollectionEditorCollectionForm::InitializeComponent`
- size: `1453`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x104250`

## callees

- `0xe3d40`
- `0x103b50`
- `0x104ab0`
- `0x105ff0`
- `0x1060b0`
- `0x106180`

## string_xrefs

- `0x104f48`: `addRemoveTableLayoutPanel`
- `0x104f9c`: `addRemoveTableLayoutPanel`
- `0x104d39`: `removeButton`
- `0x104d5d`: `removeButton`

## pseudocode

```c

```

## disassembly

```asm
0x104ab0  ldtoken  System.ComponentModel.Design.CollectionEditor
0x104ab5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x104aba  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x104abf  stloc.0
0x104ac0  ldarg.0
0x104ac1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x104ac6  stfld    class [System.Windows.Forms]System.Windows.Forms.Label CollectionEditorCollectionForm::membersLabel
0x104acb  ldarg.0
0x104acc  newobj   instance void FilterListBox::.ctor()
0x104ad1  stfld    class FilterListBox CollectionEditorCollectionForm::listbox
0x104ad6  ldarg.0
0x104ad7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x104adc  stfld    class [System.Windows.Forms]System.Windows.Forms.Button CollectionEditorCollectionForm::upButton
0x104ae1  ldarg.0
0x104ae2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x104ae7  stfld    class [System.Windows.Forms]System.Windows.Forms.Button CollectionEditorCollectionForm::downButton
0x104aec  ldarg.0
0x104aed  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x104af2  stfld    class [System.Windows.Forms]System.Windows.Forms.Label CollectionEditorCollectionForm::propertiesLabel
0x104af7  ldarg.0
0x104af8  ldarg.0
0x104af9  call     instance class [System]System.ComponentModel.ITypeDescriptorContext CollectionForm::get_Context()
0x104afe  newobj   instance void System.Windows.Forms.Design.VsPropertyGrid::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0x104b03  stfld    class System.Windows.Forms.Design.VsPropertyGrid CollectionEditorCollectionForm::propertyBrowser
0x104b08  ldarg.0
0x104b09  newobj   instance void SplitButton::.ctor()
0x104b0e  stfld    class SplitButton CollectionEditorCollectionForm::addButton
0x104b13  ldarg.0
0x104b14  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x104b19  stfld    class [System.Windows.Forms]System.Windows.Forms.Button CollectionEditorCollectionForm::removeButton
0x104b1e  ldarg.0
0x104b1f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x104b24  stfld    class [System.Windows.Forms]System.Windows.Forms.Button CollectionEditorCollectionForm::okButton
0x104b29  ldarg.0
0x104b2a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x104b2f  stfld    class [System.Windows.Forms]System.Windows.Forms.Button CollectionEditorCollectionForm::cancelButton
0x104b34  ldarg.0
0x104b35  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x104b3a  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel CollectionEditorCollectionForm::okCancelTableLayoutPanel
0x104b3f  ldarg.0
0x104b40  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x104b45  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel CollectionEditorCollectionForm::overArchingTableLayoutPanel
0x104b4a  ldarg.0
0x104b4b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x104b50  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel CollectionEditorCollectionForm::addRemoveTableLayoutPanel
0x104b55  ldarg.0
0x104b56  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel CollectionEditorCollectionForm::okCancelTableLayoutPanel
0x104b5b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x104b60  ldarg.0
0x104b61  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel CollectionEditorCollectionForm::overArchingTableLayoutPanel
0x104b66  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x104b6b  ldarg.0
0x104b6c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel CollectionEditorCollectionForm::addRemoveTableLayoutPanel
0x104b71  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x104b76  ldarg.0
0x104b77  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x104b7c  ldloc.0
0x104b7d  ldarg.0
0x104b7e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label CollectionEditorCollectionForm::membersLabel
0x104b83  ldstr    aMemberslabel// "membersLabel"
0x104b88  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x104b8d  ldarg.0
0x104b8e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label CollectionEditorCollectionForm::membersLabel
0x104b93  ldc.i4.0
0x104b94  ldc.i4.0
0x104b95  ldc.i4.3
0x104b96  ldc.i4.3
0x104b97  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x104b9c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x104ba1  ldarg.0
0x104ba2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label CollectionEditorCollectionForm::membersLabel
0x104ba7  ldstr    aMemberslabel// "membersLabel"
0x104bac  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x104bb1  ldloc.0
0x104bb2  ldarg.0
0x104bb3  ldfld    class FilterListBox CollectionEditorCollectionForm::listbox
0x104bb8  ldstr    aListbox// "listbox"
0x104bbd  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x104bc2  ldarg.0
0x104bc3  ldfld    class FilterListBox CollectionEditorCollectionForm::listbox
0x104bc8  ldarg.0
0x104bc9  callvirt instance bool CollectionForm::CanSelectMultipleInstances()
0x104bce  brtrue.s loc_104BD3
0x104bd0  ldc.i4.1
0x104bd1  br.s     loc_104BD4
0x104bd3  ldc.i4.3
0x104bd4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListBox::set_SelectionMode(valuetype [System.Windows.Forms]System.Windows.Forms.SelectionMode)
0x104bd9  ldarg.0
0x104bda  ldfld    class FilterListBox CollectionEditorCollectionForm::listbox
0x104bdf  ldc.i4.1
0x104be0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListBox::set_DrawMode(valuetype [System.Windows.Forms]System.Windows.Forms.DrawMode)
0x104be5  ldarg.0
0x104be6  ldfld    class FilterListBox CollectionEditorCollectionForm::listbox
0x104beb  ldc.i4.1
0x104bec  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListControl::set_FormattingEnabled(bool)
0x104bf1  ldarg.0
0x104bf2  ldfld    class FilterListBox CollectionEditorCollectionForm::listbox
0x104bf7  ldc.i4.0
0x104bf8  ldc.i4.3
0x104bf9  ldc.i4.3
0x104bfa  ldc.i4.3
0x104bfb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x104c00  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x104c05  ldarg.0
0x104c06  ldfld    class FilterListBox CollectionEditorCollectionForm::listbox
0x104c0b  ldstr    aListbox// "listbox"
0x104c10  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x104c15  ldarg.0
0x104c16  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel CollectionEditorCollectionForm::overArchingTableLayoutPanel
0x104c1b  ldarg.0
0x104c1c  ldfld    class FilterListBox CollectionEditorCollectionForm::listbox
0x104c21  ldc.i4.2
0x104c22  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetRowSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x104c27  ldloc.0
0x104c28  ldarg.0
0x104c29  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button CollectionEditorCollectionForm::upButton
0x104c2e  ldstr    aUpbutton// "upButton"
0x104c33  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x104c38  ldarg.0
0x104c39  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button CollectionEditorCollectionForm::upButton
0x104c3e  ldstr    aUpbutton// "upButton"
0x104c43  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x104c48  ldloc.0
0x104c49  ldarg.0
0x104c4a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button CollectionEditorCollectionForm::downButton
0x104c4f  ldstr    aDownbutton// "downButton"
0x104c54  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x104c59  ldarg.0
0x104c5a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button CollectionEditorCollectionForm::downButton
0x104c5f  ldstr    aDownbutton// "downButton"
0x104c64  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x104c69  ldloc.0
0x104c6a  ldarg.0
0x104c6b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label CollectionEditorCollectionForm::propertiesLabel
0x104c70  ldstr    aPropertieslabe_0// "propertiesLabel"
0x104c75  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x104c7a  ldarg.0
0x104c7b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label CollectionEditorCollectionForm::propertiesLabel
0x104c80  ldc.i4.1
0x104c81  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_AutoEllipsis(bool)
0x104c86  ldarg.0
0x104c87  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label CollectionEditorCollectionForm::propertiesLabel
0x104c8c  ldc.i4.0
0x104c8d  ldc.i4.0
0x104c8e  ldc.i4.3
0x104c8f  ldc.i4.3
0x104c90  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x104c95  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x104c9a  ldarg.0
0x104c9b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label CollectionEditorCollectionForm::propertiesLabel
0x104ca0  ldstr    aPropertieslabe_0// "propertiesLabel"
0x104ca5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x104caa  ldloc.0
0x104cab  ldarg.0
0x104cac  ldfld    class System.Windows.Forms.Design.VsPropertyGrid CollectionEditorCollectionForm::propertyBrowser
0x104cb1  ldstr    aPropertybrowse// "propertyBrowser"
0x104cb6  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x104cbb  ldarg.0
0x104cbc  ldfld    class System.Windows.Forms.Design.VsPropertyGrid CollectionEditorCollectionForm::propertyBrowser
0x104cc1  ldc.i4.0
0x104cc2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PropertyGrid::set_CommandsVisibleIfAvailable(bool)
0x104cc7  ldarg.0
0x104cc8  ldfld    class System.Windows.Forms.Design.VsPropertyGrid CollectionEditorCollectionForm::propertyBrowser
0x104ccd  ldc.i4.3
0x104cce  ldc.i4.3
0x104ccf  ldc.i4.0
0x104cd0  ldc.i4.3
0x104cd1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x104cd6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x104cdb  ldarg.0
0x104cdc  ldfld    class System.Windows.Forms.Design.VsPropertyGrid CollectionEditorCollectionForm::propertyBrowser
0x104ce1  ldstr    aPropertybrowse// "propertyBrowser"
0x104ce6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x104ceb  ldarg.0
0x104cec  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel CollectionEditorCollectionForm::overArchingTableLayoutPanel
0x104cf1  ldarg.0
0x104cf2  ldfld    class System.Windows.Forms.Design.VsPropertyGrid CollectionEditorCollectionForm::propertyBrowser
0x104cf7  ldc.i4.3
0x104cf8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetRowSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x104cfd  ldloc.0
0x104cfe  ldarg.0
0x104cff  ldfld    class SplitButton CollectionEditorCollectionForm::addButton
0x104d04  ldstr    aAddbutton_0// "addButton"
0x104d09  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x104d0e  ldarg.0
0x104d0f  ldfld    class SplitButton CollectionEditorCollectionForm::addButton
0x104d14  ldc.i4.0
0x104d15  ldc.i4.3
0x104d16  ldc.i4.3
0x104d17  ldc.i4.3
0x104d18  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x104d1d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x104d22  ldarg.0
0x104d23  ldfld    class SplitButton CollectionEditorCollectionForm::addButton
0x104d28  ldstr    aAddbutton_0// "addButton"
0x104d2d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x104d32  ldloc.0
0x104d33  ldarg.0
0x104d34  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button CollectionEditorCollectionForm::removeButton
0x104d39  ldstr    aRemovebutton_0// "removeButton"
0x104d3e  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x104d43  ldarg.0
0x104d44  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button CollectionEditorCollectionForm::removeButton
0x104d49  ldc.i4.3
0x104d4a  ldc.i4.3
0x104d4b  ldc.i4.0
0x104d4c  ldc.i4.3
0x104d4d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x104d52  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x104d57  ldarg.0
0x104d58  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button CollectionEditorCollectionForm::removeButton
0x104d5d  ldstr    aRemovebutton_0// "removeButton"
0x104d62  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x104d67  ldloc.0
0x104d68  ldarg.0
0x104d69  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button CollectionEditorCollectionForm::okButton
0x104d6e  ldstr    aOkbutton_0// "okButton"
0x104d73  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x104d78  ldarg.0
0x104d79  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button CollectionEditorCollectionForm::okButton
0x104d7e  ldc.i4.1
0x104d7f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x104d84  ldarg.0
0x104d85  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button CollectionEditorCollectionForm::okButton
0x104d8a  ldc.i4.0
0x104d8b  ldc.i4.3
0x104d8c  ldc.i4.3
0x104d8d  ldc.i4.0
0x104d8e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x104d93  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x104d98  ldarg.0
0x104d99  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button CollectionEditorCollectionForm::okButton
0x104d9e  ldstr    aOkbutton_0// "okButton"
0x104da3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x104da8  ldloc.0
0x104da9  ldarg.0
0x104daa  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button CollectionEditorCollectionForm::cancelButton
0x104daf  ldstr    aCancelbutton_1// "cancelButton"
0x104db4  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x104db9  ldarg.0
0x104dba  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button CollectionEditorCollectionForm::cancelButton
0x104dbf  ldc.i4.2
0x104dc0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x104dc5  ldarg.0
0x104dc6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button CollectionEditorCollectionForm::cancelButton
0x104dcb  ldc.i4.3
0x104dcc  ldc.i4.3
0x104dcd  ldc.i4.0
0x104dce  ldc.i4.0
0x104dcf  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x104dd4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x104dd9  ldarg.0
0x104dda  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button CollectionEditorCollectionForm::cancelButton
0x104ddf  ldstr    aCancelbutton_1// "cancelButton"
0x104de4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x104de9  ldloc.0
0x104dea  ldarg.0
0x104deb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel CollectionEditorCollectionForm::okCancelTableLayoutPanel
0x104df0  ldstr    aOkcanceltablel// "okCancelTableLayoutPanel"
0x104df5  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x104dfa  ldarg.0
0x104dfb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel CollectionEditorCollectionForm::overArchingTableLayoutPanel
0x104e00  ldarg.0
0x104e01  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel CollectionEditorCollectionForm::okCancelTableLayoutPanel
0x104e06  ldc.i4.3
0x104e07  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x104e0c  ldarg.0
0x104e0d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel CollectionEditorCollectionForm::okCancelTableLayoutPanel
0x104e12  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x104e17  ldarg.0
0x104e18  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button CollectionEditorCollectionForm::okButton
0x104e1d  ldc.i4.0
0x104e1e  ldc.i4.0
0x104e1f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x104e24  ldarg.0
0x104e25  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel CollectionEditorCollectionForm::okCancelTableLayoutPanel
0x104e2a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x104e2f  ldarg.0
0x104e30  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button CollectionEditorCollectionForm::cancelButton
0x104e35  ldc.i4.1
0x104e36  ldc.i4.0
0x104e37  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x104e3c  ldarg.0
0x104e3d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel CollectionEditorCollectionForm::okCancelTableLayoutPanel
0x104e42  ldc.i4.3
0x104e43  ldc.i4.3
0x104e44  ldc.i4.0
0x104e45  ldc.i4.0
0x104e46  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x104e4b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x104e50  ldarg.0
0x104e51  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel CollectionEditorCollectionForm::okCancelTableLayoutPanel
0x104e56  ldstr    aOkcanceltablel// "okCancelTableLayoutPanel"
0x104e5b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x104e60  ldloc.0
0x104e61  ldarg.0
0x104e62  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel CollectionEditorCollectionForm::overArchingTableLayoutPanel
0x104e67  ldstr    aOverarchingtab_0// "overArchingTableLayoutPanel"
0x104e6c  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x104e71  ldarg.0
  ... truncated ...
```
