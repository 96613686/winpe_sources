# Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::InitializeComponent

- ea: `0x79680`
- end: `0x799e2`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::InitializeComponent`
- size: `866`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x79030`

## string_xrefs

- `0x79824`: `deleteButton`
- `0x79834`: `deleteButton`

## pseudocode

```c

```

## disassembly

```asm
0x79680  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList
0x79685  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7968a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x7968f  stloc.0
0x79690  ldarg.0
0x79691  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ListView::.ctor()
0x79696  stfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::mainListView
0x7969b  ldarg.0
0x7969c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::.ctor()
0x796a1  stfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::columnHeaderType
0x796a6  ldarg.0
0x796a7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::.ctor()
0x796ac  stfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::columnHeaderDetails
0x796b1  ldarg.0
0x796b2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::.ctor()
0x796b7  stfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::columnHeaderStatus
0x796bc  ldarg.0
0x796bd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x796c2  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::deleteButton
0x796c7  ldarg.0
0x796c8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x796cd  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::editButton
0x796d2  ldarg.0
0x796d3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x796d8  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::newButton
0x796dd  ldarg.0
0x796de  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x796e3  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::labelDescriptionTriggerList
0x796e8  ldarg.0
0x796e9  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x796ee  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::tableLayoutPanel1
0x796f3  ldarg.0
0x796f4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::tableLayoutPanel1
0x796f9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x796fe  ldarg.0
0x796ff  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x79704  ldarg.0
0x79705  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::mainListView
0x7970a  ldc.i4.1
0x7970b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_BorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.BorderStyle)
0x79710  ldarg.0
0x79711  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::mainListView
0x79716  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Columns()
0x7971b  ldc.i4.3
0x7971c  newarr   [System.Windows.Forms]System.Windows.Forms.ColumnHeader
0x79721  dup
0x79722  ldc.i4.0
0x79723  ldarg.0
0x79724  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::columnHeaderType
0x79729  stelem.ref
0x7972a  dup
0x7972b  ldc.i4.1
0x7972c  ldarg.0
0x7972d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::columnHeaderDetails
0x79732  stelem.ref
0x79733  dup
0x79734  ldc.i4.2
0x79735  ldarg.0
0x79736  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::columnHeaderStatus
0x7973b  stelem.ref
0x7973c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection::AddRange(class [System.Windows.Forms]System.Windows.Forms.ColumnHeader[])
0x79741  ldarg.0
0x79742  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::tableLayoutPanel1
0x79747  ldarg.0
0x79748  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::mainListView
0x7974d  ldc.i4.4
0x7974e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x79753  ldloc.0
0x79754  ldarg.0
0x79755  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::mainListView
0x7975a  ldstr    aMainlistview// "mainListView"
0x7975f  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x79764  ldarg.0
0x79765  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::mainListView
0x7976a  ldc.i4.1
0x7976b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_FullRowSelect(bool)
0x79770  ldarg.0
0x79771  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::mainListView
0x79776  ldc.i4.1
0x79777  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_HeaderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ColumnHeaderStyle)
0x7977c  ldarg.0
0x7977d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::mainListView
0x79782  ldc.i4.0
0x79783  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_HideSelection(bool)
0x79788  ldarg.0
0x79789  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::mainListView
0x7978e  ldstr    aMainlistview// "mainListView"
0x79793  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x79798  ldarg.0
0x79799  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::mainListView
0x7979e  ldc.i4.1
0x7979f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_ShowItemToolTips(bool)
0x797a4  ldarg.0
0x797a5  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::mainListView
0x797aa  ldc.i4.0
0x797ab  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_UseCompatibleStateImageBehavior(bool)
0x797b0  ldarg.0
0x797b1  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::mainListView
0x797b6  ldc.i4.1
0x797b7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_View(valuetype [System.Windows.Forms]System.Windows.Forms.View)
0x797bc  ldarg.0
0x797bd  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::mainListView
0x797c2  ldarg.0
0x797c3  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::mainListView_DoubleClick(object sender, class [mscorlib]System.EventArgs e)
0x797c9  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x797ce  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_DoubleClick(class [mscorlib]System.EventHandler)
0x797d3  ldarg.0
0x797d4  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::mainListView
0x797d9  ldarg.0
0x797da  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::MainEventsListView_SelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0x797e0  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x797e5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x797ea  ldloc.0
0x797eb  ldarg.0
0x797ec  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::columnHeaderType
0x797f1  ldstr    aColumnheaderty// "columnHeaderType"
0x797f6  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x797fb  ldloc.0
0x797fc  ldarg.0
0x797fd  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::columnHeaderDetails
0x79802  ldstr    aColumnheaderde_0// "columnHeaderDetails"
0x79807  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7980c  ldloc.0
0x7980d  ldarg.0
0x7980e  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::columnHeaderStatus
0x79813  ldstr    aColumnheaderst_0// "columnHeaderStatus"
0x79818  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7981d  ldloc.0
0x7981e  ldarg.0
0x7981f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::deleteButton
0x79824  ldstr    aDeletebutton// "deleteButton"
0x79829  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7982e  ldarg.0
0x7982f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::deleteButton
0x79834  ldstr    aDeletebutton// "deleteButton"
0x79839  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7983e  ldarg.0
0x7983f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::deleteButton
0x79844  ldarg.0
0x79845  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::DeleteButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x7984b  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x79850  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x79855  ldloc.0
0x79856  ldarg.0
0x79857  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::editButton
0x7985c  ldstr    aEditbutton// "editButton"
0x79861  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x79866  ldarg.0
0x79867  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::editButton
0x7986c  ldstr    aEditbutton// "editButton"
0x79871  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x79876  ldarg.0
0x79877  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::editButton
0x7987c  ldarg.0
0x7987d  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::EditButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x79883  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x79888  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x7988d  ldloc.0
0x7988e  ldarg.0
0x7988f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::newButton
0x79894  ldstr    aNewbutton// "newButton"
0x79899  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7989e  ldarg.0
0x7989f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::newButton
0x798a4  ldstr    aNewbutton// "newButton"
0x798a9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x798ae  ldarg.0
0x798af  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::newButton
0x798b4  ldarg.0
0x798b5  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::NewButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x798bb  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x798c0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x798c5  ldarg.0
0x798c6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::tableLayoutPanel1
0x798cb  ldarg.0
0x798cc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::labelDescriptionTriggerList
0x798d1  ldc.i4.4
0x798d2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x798d7  ldloc.0
0x798d8  ldarg.0
0x798d9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::labelDescriptionTriggerList
0x798de  ldstr    aLabeldescripti_8// "labelDescriptionTriggerList"
0x798e3  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x798e8  ldarg.0
0x798e9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::labelDescriptionTriggerList
0x798ee  ldstr    aLabeldescripti_8// "labelDescriptionTriggerList"
0x798f3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x798f8  ldloc.0
0x798f9  ldarg.0
0x798fa  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::tableLayoutPanel1
0x798ff  ldstr    aTablelayoutpan// "tableLayoutPanel1"
0x79904  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x79909  ldarg.0
0x7990a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::tableLayoutPanel1
0x7990f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x79914  ldarg.0
0x79915  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::newButton
0x7991a  ldc.i4.0
0x7991b  ldc.i4.2
0x7991c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x79921  ldarg.0
0x79922  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::tableLayoutPanel1
0x79927  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x7992c  ldarg.0
0x7992d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::labelDescriptionTriggerList
0x79932  ldc.i4.0
0x79933  ldc.i4.0
0x79934  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x79939  ldarg.0
0x7993a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::tableLayoutPanel1
0x7993f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x79944  ldarg.0
0x79945  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::mainListView
0x7994a  ldc.i4.0
0x7994b  ldc.i4.1
0x7994c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x79951  ldarg.0
0x79952  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::tableLayoutPanel1
0x79957  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x7995c  ldarg.0
0x7995d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::editButton
0x79962  ldc.i4.1
0x79963  ldc.i4.2
0x79964  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x79969  ldarg.0
0x7996a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::tableLayoutPanel1
0x7996f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x79974  ldarg.0
0x79975  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::deleteButton
0x7997a  ldc.i4.2
0x7997b  ldc.i4.2
0x7997c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x79981  ldarg.0
0x79982  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::tableLayoutPanel1
0x79987  ldstr    aTablelayoutpan// "tableLayoutPanel1"
0x7998c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x79991  ldloc.0
0x79992  ldarg.0
0x79993  ldstr    aThis// "$this"
0x79998  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7999d  ldarg.0
0x7999e  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x799a3  ldarg.0
0x799a4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::tableLayoutPanel1
0x799a9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x799ae  ldarg.0
0x799af  ldc.i4   0x190
0x799b4  ldc.i4   0x16D
0x799b9  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x799be  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x799c3  ldarg.0
0x799c4  ldstr    aControltrigger_0// "ControlTriggerList"
0x799c9  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x799ce  ldarg.0
0x799cf  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::tableLayoutPanel1
0x799d4  ldc.i4.0
0x799d5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x799da  ldarg.0
0x799db  ldc.i4.0
0x799dc  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x799e1  ret
```
