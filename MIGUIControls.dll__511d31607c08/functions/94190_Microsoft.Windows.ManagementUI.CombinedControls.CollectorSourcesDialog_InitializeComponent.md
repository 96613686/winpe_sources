# Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::InitializeComponent

- ea: `0x94190`
- end: `0x9460e`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::InitializeComponent`
- size: `1150`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x93f80`

## string_xrefs

- `0x943a4`: `buttonAddDomainComputer`
- `0x943b4`: `buttonAddDomainComputer`
- `0x943e8`: `labelComputerGroups`
- `0x943f8`: `labelComputerGroups`
- `0x94409`: `buttonRemove`
- `0x94419`: `buttonRemove`

## pseudocode

```c

```

## disassembly

```asm
0x94190  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog
0x94195  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9419a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x9419f  ldarg.0
0x941a0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x941a5  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonCancel
0x941aa  ldarg.0
0x941ab  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x941b0  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonOK
0x941b5  ldarg.0
0x941b6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x941bb  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::tableLayoutPanelOKCancel
0x941c0  ldarg.0
0x941c1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x941c6  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::tableLayoutPanelSelect
0x941cb  ldarg.0
0x941cc  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x941d1  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonAddDomainComputer
0x941d6  ldarg.0
0x941d7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x941dc  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::labelComputerGroups
0x941e1  ldarg.0
0x941e2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x941e7  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonRemove
0x941ec  ldarg.0
0x941ed  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x941f2  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonTest
0x941f7  ldarg.0
0x941f8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ListView::.ctor()
0x941fd  stfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::listViewSources
0x94202  ldarg.0
0x94203  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x94208  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::labelSeparator1
0x9420d  ldarg.0
0x9420e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::tableLayoutPanelOKCancel
0x94213  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x94218  ldarg.0
0x94219  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::tableLayoutPanelSelect
0x9421e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x94223  ldarg.0
0x94224  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x94229  dup
0x9422a  ldarg.0
0x9422b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonCancel
0x94230  ldstr    aButtoncancel// "buttonCancel"
0x94235  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x9423a  ldarg.0
0x9423b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonCancel
0x94240  ldc.i4.2
0x94241  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x94246  ldarg.0
0x94247  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonCancel
0x9424c  ldstr    aButtoncancel// "buttonCancel"
0x94251  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x94256  ldarg.0
0x94257  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonCancel
0x9425c  ldc.i4.1
0x9425d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x94262  dup
0x94263  ldarg.0
0x94264  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonOK
0x94269  ldstr    aButtonok// "buttonOK"
0x9426e  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x94273  ldarg.0
0x94274  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonOK
0x94279  ldc.i4.1
0x9427a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x9427f  ldarg.0
0x94280  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonOK
0x94285  ldstr    aButtonok// "buttonOK"
0x9428a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x9428f  ldarg.0
0x94290  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonOK
0x94295  ldc.i4.1
0x94296  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x9429b  dup
0x9429c  ldarg.0
0x9429d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::tableLayoutPanelOKCancel
0x942a2  ldstr    aTablelayoutpan_29// "tableLayoutPanelOKCancel"
0x942a7  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x942ac  ldarg.0
0x942ad  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::tableLayoutPanelOKCancel
0x942b2  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x942b7  ldarg.0
0x942b8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonOK
0x942bd  ldc.i4.1
0x942be  ldc.i4.0
0x942bf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x942c4  ldarg.0
0x942c5  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::tableLayoutPanelOKCancel
0x942ca  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x942cf  ldarg.0
0x942d0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonCancel
0x942d5  ldc.i4.2
0x942d6  ldc.i4.0
0x942d7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x942dc  ldarg.0
0x942dd  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::tableLayoutPanelOKCancel
0x942e2  ldstr    aTablelayoutpan_29// "tableLayoutPanelOKCancel"
0x942e7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x942ec  dup
0x942ed  ldarg.0
0x942ee  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::tableLayoutPanelSelect
0x942f3  ldstr    aTablelayoutpan_18// "tableLayoutPanelSelect"
0x942f8  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x942fd  ldarg.0
0x942fe  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::tableLayoutPanelSelect
0x94303  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x94308  ldarg.0
0x94309  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonAddDomainComputer
0x9430e  ldc.i4.1
0x9430f  ldc.i4.1
0x94310  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x94315  ldarg.0
0x94316  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::tableLayoutPanelSelect
0x9431b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x94320  ldarg.0
0x94321  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::labelComputerGroups
0x94326  ldc.i4.0
0x94327  ldc.i4.0
0x94328  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x9432d  ldarg.0
0x9432e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::tableLayoutPanelSelect
0x94333  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x94338  ldarg.0
0x94339  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonRemove
0x9433e  ldc.i4.1
0x9433f  ldc.i4.2
0x94340  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x94345  ldarg.0
0x94346  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::tableLayoutPanelSelect
0x9434b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x94350  ldarg.0
0x94351  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonTest
0x94356  ldc.i4.1
0x94357  ldc.i4.3
0x94358  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x9435d  ldarg.0
0x9435e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::tableLayoutPanelSelect
0x94363  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x94368  ldarg.0
0x94369  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::listViewSources
0x9436e  ldc.i4.0
0x9436f  ldc.i4.1
0x94370  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x94375  ldarg.0
0x94376  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::tableLayoutPanelSelect
0x9437b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x94380  ldarg.0
0x94381  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::labelSeparator1
0x94386  ldc.i4.0
0x94387  ldc.i4.4
0x94388  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x9438d  ldarg.0
0x9438e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::tableLayoutPanelSelect
0x94393  ldstr    aTablelayoutpan_18// "tableLayoutPanelSelect"
0x94398  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x9439d  dup
0x9439e  ldarg.0
0x9439f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonAddDomainComputer
0x943a4  ldstr    aButtonadddomai// "buttonAddDomainComputer"
0x943a9  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x943ae  ldarg.0
0x943af  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonAddDomainComputer
0x943b4  ldstr    aButtonadddomai// "buttonAddDomainComputer"
0x943b9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x943be  ldarg.0
0x943bf  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonAddDomainComputer
0x943c4  ldc.i4.1
0x943c5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x943ca  ldarg.0
0x943cb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonAddDomainComputer
0x943d0  ldarg.0
0x943d1  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonAddDomainComputer_Click(object sender, class [mscorlib]System.EventArgs e)
0x943d7  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x943dc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x943e1  dup
0x943e2  ldarg.0
0x943e3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::labelComputerGroups
0x943e8  ldstr    aLabelcomputerg// "labelComputerGroups"
0x943ed  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x943f2  ldarg.0
0x943f3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::labelComputerGroups
0x943f8  ldstr    aLabelcomputerg// "labelComputerGroups"
0x943fd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x94402  dup
0x94403  ldarg.0
0x94404  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonRemove
0x94409  ldstr    aButtonremove// "buttonRemove"
0x9440e  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x94413  ldarg.0
0x94414  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonRemove
0x94419  ldstr    aButtonremove// "buttonRemove"
0x9441e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x94423  ldarg.0
0x94424  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonRemove
0x94429  ldc.i4.1
0x9442a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x9442f  ldarg.0
0x94430  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonRemove
0x94435  ldarg.0
0x94436  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonRemove_Click(object sender, class [mscorlib]System.EventArgs e)
0x9443c  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x94441  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x94446  dup
0x94447  ldarg.0
0x94448  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonTest
0x9444d  ldstr    aButtontest// "buttonTest"
0x94452  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x94457  ldarg.0
0x94458  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonTest
0x9445d  ldstr    aButtontest// "buttonTest"
0x94462  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x94467  ldarg.0
0x94468  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonTest
0x9446d  ldc.i4.1
0x9446e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x94473  ldarg.0
0x94474  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonTest
0x94479  ldarg.0
0x9447a  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonTest_Click(object sender, class [mscorlib]System.EventArgs e)
0x94480  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x94485  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x9448a  dup
0x9448b  ldarg.0
0x9448c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::listViewSources
0x94491  ldstr    aListviewsource// "listViewSources"
0x94496  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x9449b  ldarg.0
0x9449c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::listViewSources
0x944a1  ldc.i4.1
0x944a2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_FullRowSelect(bool)
0x944a7  ldarg.0
0x944a8  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::listViewSources
0x944ad  ldc.i4.0
0x944ae  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_HideSelection(bool)
0x944b3  ldarg.0
0x944b4  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::listViewSources
0x944b9  ldstr    aListviewsource// "listViewSources"
0x944be  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x944c3  ldarg.0
0x944c4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::tableLayoutPanelSelect
0x944c9  ldarg.0
0x944ca  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::listViewSources
0x944cf  ldc.i4.3
0x944d0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetRowSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x944d5  ldarg.0
0x944d6  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::listViewSources
0x944db  ldc.i4.1
0x944dc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_ShowItemToolTips(bool)
0x944e1  ldarg.0
0x944e2  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::listViewSources
0x944e7  ldc.i4.0
0x944e8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_UseCompatibleStateImageBehavior(bool)
0x944ed  ldarg.0
0x944ee  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::listViewSources
0x944f3  ldc.i4.1
0x944f4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_View(valuetype [System.Windows.Forms]System.Windows.Forms.View)
0x944f9  ldarg.0
0x944fa  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::listViewSources
0x944ff  ldarg.0
0x94500  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::listViewSources_SelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0x94506  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x9450b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x94510  ldarg.0
0x94511  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::listViewSources
0x94516  ldarg.0
0x94517  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::listViewSources_ColumnClick(object sender, class [System.Windows.Forms]System.Windows.Forms.ColumnClickEventArgs e)
0x9451d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnClickEventHandler::.ctor(object, native int)
0x94522  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::add_ColumnClick(class [System.Windows.Forms]System.Windows.Forms.ColumnClickEventHandler)
0x94527  dup
0x94528  ldarg.0
0x94529  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::labelSeparator1
0x9452e  ldstr    aLabelseparator_0// "labelSeparator1"
0x94533  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x94538  ldarg.0
0x94539  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::labelSeparator1
0x9453e  ldc.i4.2
0x9453f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_BorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.BorderStyle)
0x94544  ldarg.0
0x94545  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::tableLayoutPanelSelect
0x9454a  ldarg.0
0x9454b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::labelSeparator1
0x94550  ldc.i4.2
0x94551  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x94556  ldarg.0
0x94557  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::labelSeparator1
0x9455c  ldstr    aLabelseparator_0// "labelSeparator1"
0x94561  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x94566  ldarg.0
0x94567  ldarg.0
0x94568  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CollectorSourcesDialog::buttonOK
0x9456d  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_AcceptButton(class [System.Windows.Forms]System.Windows.Forms.IButtonControl)
0x94572  ldarg.0
0x94573  ldstr    aThis// "$this"
0x94578  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x9457d  ldarg.0
0x9457e  ldc.i4.1
0x9457f  call     instance void [System.Windows.Forms]System.Windows.Forms.ContainerControl::set_AutoScaleMode(valuetype [System.Windows.Forms]System.Windows.Forms.AutoScaleMode)
0x94584  ldarg.0
  ... truncated ...
```
