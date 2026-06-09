# Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::InitializeComponent

- ea: `0x80070`
- end: `0x802a8`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::InitializeComponent`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x7fbf0`

## string_xrefs

- `0x800ce`: `activeTasksListView`
- `0x80102`: `activeTasksListView`
- `0x80165`: `activeTasksSummaryLabel`
- `0x80175`: `activeTasksSummaryLabel`
- `0x80266`: `ActiveTasksSummaryControl`

## pseudocode

```c

```

## disassembly

```asm
0x80070  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl
0x80075  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8007a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x8007f  ldarg.0
0x80080  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ListView::.ctor()
0x80085  stfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x8008a  ldarg.0
0x8008b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x80090  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksSummaryLabel
0x80095  ldarg.0
0x80096  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x8009b  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::descriptionLabel
0x800a0  ldarg.0
0x800a1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x800a6  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::refreshStatusLabel
0x800ab  ldarg.0
0x800ac  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x800b1  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::tableLayoutPanel1
0x800b6  ldarg.0
0x800b7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::tableLayoutPanel1
0x800bc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x800c1  ldarg.0
0x800c2  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x800c7  dup
0x800c8  ldarg.0
0x800c9  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x800ce  ldstr    aActivetaskslis// "activeTasksListView"
0x800d3  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x800d8  ldarg.0
0x800d9  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x800de  ldc.i4.1
0x800df  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_FullRowSelect(bool)
0x800e4  ldarg.0
0x800e5  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x800ea  ldc.i4.1
0x800eb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_HeaderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ColumnHeaderStyle)
0x800f0  ldarg.0
0x800f1  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x800f6  ldc.i4.0
0x800f7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_MultiSelect(bool)
0x800fc  ldarg.0
0x800fd  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x80102  ldstr    aActivetaskslis// "activeTasksListView"
0x80107  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8010c  ldarg.0
0x8010d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x80112  ldc.i4.1
0x80113  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_ShowItemToolTips(bool)
0x80118  ldarg.0
0x80119  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x8011e  ldc.i4.0
0x8011f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_UseCompatibleStateImageBehavior(bool)
0x80124  ldarg.0
0x80125  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x8012a  ldc.i4.1
0x8012b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_View(valuetype [System.Windows.Forms]System.Windows.Forms.View)
0x80130  ldarg.0
0x80131  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x80136  ldarg.0
0x80137  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView_DoubleClick(object sender, class [mscorlib]System.EventArgs e)
0x8013d  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x80142  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_DoubleClick(class [mscorlib]System.EventHandler)
0x80147  ldarg.0
0x80148  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x8014d  ldarg.0
0x8014e  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView_SelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0x80154  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x80159  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x8015e  dup
0x8015f  ldarg.0
0x80160  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksSummaryLabel
0x80165  ldstr    aActivetaskssum// "activeTasksSummaryLabel"
0x8016a  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8016f  ldarg.0
0x80170  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksSummaryLabel
0x80175  ldstr    aActivetaskssum// "activeTasksSummaryLabel"
0x8017a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8017f  dup
0x80180  ldarg.0
0x80181  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::descriptionLabel
0x80186  ldstr    aDescriptionlab// "descriptionLabel"
0x8018b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x80190  ldarg.0
0x80191  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::descriptionLabel
0x80196  ldstr    aDescriptionlab// "descriptionLabel"
0x8019b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x801a0  dup
0x801a1  ldarg.0
0x801a2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::refreshStatusLabel
0x801a7  ldstr    aRefreshstatusl// "refreshStatusLabel"
0x801ac  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x801b1  ldarg.0
0x801b2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::refreshStatusLabel
0x801b7  ldstr    aRefreshstatusl// "refreshStatusLabel"
0x801bc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x801c1  dup
0x801c2  ldarg.0
0x801c3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::tableLayoutPanel1
0x801c8  ldstr    aTablelayoutpan// "tableLayoutPanel1"
0x801cd  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x801d2  ldarg.0
0x801d3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::tableLayoutPanel1
0x801d8  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x801dd  ldarg.0
0x801de  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::descriptionLabel
0x801e3  ldc.i4.0
0x801e4  ldc.i4.0
0x801e5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x801ea  ldarg.0
0x801eb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::tableLayoutPanel1
0x801f0  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x801f5  ldarg.0
0x801f6  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksListView
0x801fb  ldc.i4.0
0x801fc  ldc.i4.3
0x801fd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x80202  ldarg.0
0x80203  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::tableLayoutPanel1
0x80208  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x8020d  ldarg.0
0x8020e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::refreshStatusLabel
0x80213  ldc.i4.0
0x80214  ldc.i4.2
0x80215  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x8021a  ldarg.0
0x8021b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::tableLayoutPanel1
0x80220  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x80225  ldarg.0
0x80226  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::activeTasksSummaryLabel
0x8022b  ldc.i4.0
0x8022c  ldc.i4.1
0x8022d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x80232  ldarg.0
0x80233  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::tableLayoutPanel1
0x80238  ldstr    aTablelayoutpan// "tableLayoutPanel1"
0x8023d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x80242  ldarg.0
0x80243  ldstr    aThis// "$this"
0x80248  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8024d  ldarg.0
0x8024e  ldc.i4.1
0x8024f  call     instance void [System.Windows.Forms]System.Windows.Forms.ContainerControl::set_AutoScaleMode(valuetype [System.Windows.Forms]System.Windows.Forms.AutoScaleMode)
0x80254  ldarg.0
0x80255  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x8025a  ldarg.0
0x8025b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::tableLayoutPanel1
0x80260  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x80265  ldarg.0
0x80266  ldstr    aActivetaskssum_0// "ActiveTasksSummaryControl"
0x8026b  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x80270  ldarg.0
0x80271  ldarg.0
0x80272  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::ActiveTasksSummaryControl_Load(object sender, class [mscorlib]System.EventArgs e)
0x80278  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x8027d  call     instance void [System.Windows.Forms]System.Windows.Forms.UserControl::add_Load(class [mscorlib]System.EventHandler)
0x80282  ldarg.0
0x80283  ldarg.0
0x80284  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::ActiveTasksSummaryControl_RightToLeftChanged(object sender, class [mscorlib]System.EventArgs e)
0x8028a  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x8028f  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::add_RightToLeftChanged(class [mscorlib]System.EventHandler)
0x80294  ldarg.0
0x80295  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActiveTasksSummaryControl::tableLayoutPanel1
0x8029a  ldc.i4.0
0x8029b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x802a0  ldarg.0
0x802a1  ldc.i4.0
0x802a2  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x802a7  ret
```
