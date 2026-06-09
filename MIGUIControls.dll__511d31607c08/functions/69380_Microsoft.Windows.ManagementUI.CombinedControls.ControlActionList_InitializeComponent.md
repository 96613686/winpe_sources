# Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::InitializeComponent

- ea: `0x69380`
- end: `0x697d9`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::InitializeComponent`
- size: `1113`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x68cc0`

## string_xrefs

- `0x69527`: `buttonDelete`
- `0x6954b`: `buttonDelete`
- `0x6963e`: `moveUpButton`
- `0x6964e`: `moveUpButton`
- `0x69682`: `moveDownButton`
- `0x69692`: `moveDownButton`

## pseudocode

```c

```

## disassembly

```asm
0x69380  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList
0x69385  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6938a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x6938f  stloc.0
0x69390  ldarg.0
0x69391  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ListView::.ctor()
0x69396  stfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::listViewActions
0x6939b  ldarg.0
0x6939c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::.ctor()
0x693a1  stfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::columnHeaderType
0x693a6  ldarg.0
0x693a7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::.ctor()
0x693ac  stfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::columnHeaderDetails
0x693b1  ldarg.0
0x693b2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x693b7  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::buttonDelete
0x693bc  ldarg.0
0x693bd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x693c2  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::buttonEdit
0x693c7  ldarg.0
0x693c8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x693cd  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::buttonNew
0x693d2  ldarg.0
0x693d3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x693d8  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::labelDescriptionActionList
0x693dd  ldarg.0
0x693de  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x693e3  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::moveUpButton
0x693e8  ldarg.0
0x693e9  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x693ee  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::moveDownButton
0x693f3  ldarg.0
0x693f4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x693f9  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::tableLayoutPanel
0x693fe  ldarg.0
0x693ff  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::tableLayoutPanel
0x69404  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x69409  ldarg.0
0x6940a  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6940f  ldarg.0
0x69410  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::listViewActions
0x69415  ldc.i4.1
0x69416  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_BorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.BorderStyle)
0x6941b  ldarg.0
0x6941c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::listViewActions
0x69421  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Columns()
0x69426  ldc.i4.2
0x69427  newarr   [System.Windows.Forms]System.Windows.Forms.ColumnHeader
0x6942c  dup
0x6942d  ldc.i4.0
0x6942e  ldarg.0
0x6942f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::columnHeaderType
0x69434  stelem.ref
0x69435  dup
0x69436  ldc.i4.1
0x69437  ldarg.0
0x69438  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::columnHeaderDetails
0x6943d  stelem.ref
0x6943e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection::AddRange(class [System.Windows.Forms]System.Windows.Forms.ColumnHeader[])
0x69443  ldarg.0
0x69444  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::tableLayoutPanel
0x69449  ldarg.0
0x6944a  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::listViewActions
0x6944f  ldc.i4.4
0x69450  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x69455  ldloc.0
0x69456  ldarg.0
0x69457  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::listViewActions
0x6945c  ldstr    aListviewaction// "listViewActions"
0x69461  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x69466  ldarg.0
0x69467  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::listViewActions
0x6946c  ldc.i4.1
0x6946d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_FullRowSelect(bool)
0x69472  ldarg.0
0x69473  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::listViewActions
0x69478  ldc.i4.1
0x69479  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_HeaderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ColumnHeaderStyle)
0x6947e  ldarg.0
0x6947f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::listViewActions
0x69484  ldc.i4.0
0x69485  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_HideSelection(bool)
0x6948a  ldarg.0
0x6948b  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::listViewActions
0x69490  ldstr    aListviewaction// "listViewActions"
0x69495  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6949a  ldarg.0
0x6949b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::tableLayoutPanel
0x694a0  ldarg.0
0x694a1  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::listViewActions
0x694a6  ldc.i4.2
0x694a7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetRowSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x694ac  ldarg.0
0x694ad  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::listViewActions
0x694b2  ldc.i4.0
0x694b3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_UseCompatibleStateImageBehavior(bool)
0x694b8  ldarg.0
0x694b9  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::listViewActions
0x694be  ldc.i4.1
0x694bf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_ShowItemToolTips(bool)
0x694c4  ldarg.0
0x694c5  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::listViewActions
0x694ca  ldc.i4.1
0x694cb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_View(valuetype [System.Windows.Forms]System.Windows.Forms.View)
0x694d0  ldarg.0
0x694d1  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::listViewActions
0x694d6  ldarg.0
0x694d7  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::listViewActions_DoubleClick(object sender, class [mscorlib]System.EventArgs e)
0x694dd  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x694e2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_DoubleClick(class [mscorlib]System.EventHandler)
0x694e7  ldarg.0
0x694e8  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::listViewActions
0x694ed  ldarg.0
0x694ee  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::listViewActions_SelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0x694f4  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x694f9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x694fe  ldloc.0
0x694ff  ldarg.0
0x69500  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::columnHeaderType
0x69505  ldstr    aColumnheaderty// "columnHeaderType"
0x6950a  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6950f  ldloc.0
0x69510  ldarg.0
0x69511  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::columnHeaderDetails
0x69516  ldstr    aColumnheaderde_0// "columnHeaderDetails"
0x6951b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x69520  ldloc.0
0x69521  ldarg.0
0x69522  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::buttonDelete
0x69527  ldstr    aButtondelete// "buttonDelete"
0x6952c  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x69531  ldarg.0
0x69532  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::buttonDelete
0x69537  ldc.i4.s 0x4B
0x69539  ldc.i4.s 0x19
0x6953b  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x69540  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x69545  ldarg.0
0x69546  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::buttonDelete
0x6954b  ldstr    aButtondelete// "buttonDelete"
0x69550  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x69555  ldarg.0
0x69556  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::buttonDelete
0x6955b  ldarg.0
0x6955c  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::DeleteButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x69562  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x69567  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x6956c  ldloc.0
0x6956d  ldarg.0
0x6956e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::buttonEdit
0x69573  ldstr    aButtonedit// "buttonEdit"
0x69578  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6957d  ldarg.0
0x6957e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::buttonEdit
0x69583  ldc.i4.s 0x4B
0x69585  ldc.i4.s 0x19
0x69587  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x6958c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x69591  ldarg.0
0x69592  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::buttonEdit
0x69597  ldstr    aButtonedit// "buttonEdit"
0x6959c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x695a1  ldarg.0
0x695a2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::buttonEdit
0x695a7  ldarg.0
0x695a8  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::EditButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x695ae  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x695b3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x695b8  ldloc.0
0x695b9  ldarg.0
0x695ba  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::buttonNew
0x695bf  ldstr    aButtonnew// "buttonNew"
0x695c4  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x695c9  ldarg.0
0x695ca  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::buttonNew
0x695cf  ldc.i4.s 0x4B
0x695d1  ldc.i4.s 0x19
0x695d3  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x695d8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x695dd  ldarg.0
0x695de  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::buttonNew
0x695e3  ldstr    aButtonnew// "buttonNew"
0x695e8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x695ed  ldarg.0
0x695ee  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::buttonNew
0x695f3  ldarg.0
0x695f4  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::NewButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x695fa  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x695ff  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x69604  ldarg.0
0x69605  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::tableLayoutPanel
0x6960a  ldarg.0
0x6960b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::labelDescriptionActionList
0x69610  ldc.i4.5
0x69611  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x69616  ldloc.0
0x69617  ldarg.0
0x69618  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::labelDescriptionActionList
0x6961d  ldstr    aLabeldescripti_2// "labelDescriptionActionList"
0x69622  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x69627  ldarg.0
0x69628  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::labelDescriptionActionList
0x6962d  ldstr    aLabeldescripti_2// "labelDescriptionActionList"
0x69632  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x69637  ldloc.0
0x69638  ldarg.0
0x69639  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::moveUpButton
0x6963e  ldstr    aMoveupbutton// "moveUpButton"
0x69643  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x69648  ldarg.0
0x69649  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::moveUpButton
0x6964e  ldstr    aMoveupbutton// "moveUpButton"
0x69653  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x69658  ldarg.0
0x69659  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::moveUpButton
0x6965e  ldc.i4.1
0x6965f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x69664  ldarg.0
0x69665  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::moveUpButton
0x6966a  ldarg.0
0x6966b  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::moveUpButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x69671  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x69676  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x6967b  ldloc.0
0x6967c  ldarg.0
0x6967d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::moveDownButton
0x69682  ldstr    aMovedownbutton// "moveDownButton"
0x69687  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6968c  ldarg.0
0x6968d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::moveDownButton
0x69692  ldstr    aMovedownbutton// "moveDownButton"
0x69697  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6969c  ldarg.0
0x6969d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::moveDownButton
0x696a2  ldc.i4.1
0x696a3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x696a8  ldarg.0
0x696a9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::moveDownButton
0x696ae  ldarg.0
0x696af  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::moveDownButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x696b5  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x696ba  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x696bf  ldloc.0
0x696c0  ldarg.0
0x696c1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::tableLayoutPanel
0x696c6  ldstr    aTablelayoutpan_0// "tableLayoutPanel"
0x696cb  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x696d0  ldarg.0
0x696d1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::tableLayoutPanel
0x696d6  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x696db  ldarg.0
0x696dc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::buttonNew
0x696e1  ldc.i4.0
0x696e2  ldc.i4.3
0x696e3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x696e8  ldarg.0
0x696e9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::tableLayoutPanel
0x696ee  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x696f3  ldarg.0
0x696f4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::labelDescriptionActionList
0x696f9  ldc.i4.0
0x696fa  ldc.i4.0
0x696fb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x69700  ldarg.0
0x69701  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::tableLayoutPanel
0x69706  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x6970b  ldarg.0
0x6970c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::listViewActions
0x69711  ldc.i4.0
0x69712  ldc.i4.1
0x69713  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x69718  ldarg.0
0x69719  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::tableLayoutPanel
0x6971e  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x69723  ldarg.0
0x69724  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::buttonEdit
0x69729  ldc.i4.1
0x6972a  ldc.i4.3
0x6972b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x69730  ldarg.0
0x69731  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::tableLayoutPanel
0x69736  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x6973b  ldarg.0
0x6973c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::buttonDelete
0x69741  ldc.i4.2
0x69742  ldc.i4.3
0x69743  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x69748  ldarg.0
0x69749  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::tableLayoutPanel
0x6974e  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x69753  ldarg.0
0x69754  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::moveUpButton
0x69759  ldc.i4.4
0x6975a  ldc.i4.1
0x6975b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x69760  ldarg.0
0x69761  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::tableLayoutPanel
0x69766  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x6976b  ldarg.0
0x6976c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::moveDownButton
  ... truncated ...
```
