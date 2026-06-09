# System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::LoadAvailableColumnsTree

- ea: `0x4dcb0`
- end: `0x4dd92`
- name: `System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::LoadAvailableColumnsTree`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x4da70`

## callees

- `0x4dcb0`
- `0x8ef40`
- `0x100bd0`
- `0x100d50`
- `0x100d70`
- `0x100dd0`
- `0x100e50`
- `0x100ed0`

## string_xrefs

- `0x4dd31`: `Delete`
- `0x4dd36`: `DGCol_DeleteButton`
- `0x4dd40`: `DGCol_Node_Delete`

## pseudocode

```c

```

## disassembly

```asm
0x4dcb0  ldarg.0
0x4dcb1  ldfld    class DataSourceItem System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::currentDataSource
0x4dcb6  brfalse.s loc_4DCDA
0x4dcb8  ldarg.0
0x4dcb9  newobj   instance void DataSourceNode::.ctor()
0x4dcbe  stfld    class DataSourceNode System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::selectedDataSourceNode
0x4dcc3  ldarg.0
0x4dcc4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::availableColumnsTree
0x4dcc9  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TreeNodeCollection [System.Windows.Forms]System.Windows.Forms.TreeView::get_Nodes()
0x4dcce  ldarg.0
0x4dccf  ldfld    class DataSourceNode System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::selectedDataSourceNode
0x4dcd4  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TreeNodeCollection::Add(class [System.Windows.Forms]System.Windows.Forms.TreeNode)
0x4dcd9  pop
0x4dcda  newobj   instance void ButtonNode::.ctor()
0x4dcdf  stloc.0
0x4dce0  ldarg.0
0x4dce1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::availableColumnsTree
0x4dce6  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TreeNodeCollection [System.Windows.Forms]System.Windows.Forms.TreeView::get_Nodes()
0x4dceb  ldloc.0
0x4dcec  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TreeNodeCollection::Add(class [System.Windows.Forms]System.Windows.Forms.TreeNode)
0x4dcf1  pop
0x4dcf2  ldstr    aSelect_1// "Select"
0x4dcf7  ldstr    aDgcolSelectbut// "DGCol_SelectButton"
0x4dcfc  call     string System.Design.SR::GetString(string name)
0x4dd01  ldstr    aDgcolNodeSelec// "DGCol_Node_Select"
0x4dd06  call     string System.Design.SR::GetString(string name)
0x4dd0b  newobj   instance void ButtonNode::.ctor(string command, string buttonText, string text)
0x4dd10  stloc.1
0x4dd11  ldloc.0
0x4dd12  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TreeNodeCollection [System.Windows.Forms]System.Windows.Forms.TreeNode::get_Nodes()
0x4dd17  ldloc.1
0x4dd18  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TreeNodeCollection::Add(class [System.Windows.Forms]System.Windows.Forms.TreeNode)
0x4dd1d  pop
0x4dd1e  newobj   instance void EditCommandNode::.ctor()
0x4dd23  stloc.2
0x4dd24  ldloc.0
0x4dd25  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TreeNodeCollection [System.Windows.Forms]System.Windows.Forms.TreeNode::get_Nodes()
0x4dd2a  ldloc.2
0x4dd2b  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TreeNodeCollection::Add(class [System.Windows.Forms]System.Windows.Forms.TreeNode)
0x4dd30  pop
0x4dd31  ldstr    aDelete// "Delete"
0x4dd36  ldstr    aDgcolDeletebut// "DGCol_DeleteButton"
0x4dd3b  call     string System.Design.SR::GetString(string name)
0x4dd40  ldstr    aDgcolNodeDelet// "DGCol_Node_Delete"
0x4dd45  call     string System.Design.SR::GetString(string name)
0x4dd4a  newobj   instance void ButtonNode::.ctor(string command, string buttonText, string text)
0x4dd4f  stloc.3
0x4dd50  ldloc.0
0x4dd51  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TreeNodeCollection [System.Windows.Forms]System.Windows.Forms.TreeNode::get_Nodes()
0x4dd56  ldloc.3
0x4dd57  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TreeNodeCollection::Add(class [System.Windows.Forms]System.Windows.Forms.TreeNode)
0x4dd5c  pop
0x4dd5d  newobj   instance void HyperLinkNode::.ctor()
0x4dd62  stloc.s  4
0x4dd64  ldarg.0
0x4dd65  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::availableColumnsTree
0x4dd6a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TreeNodeCollection [System.Windows.Forms]System.Windows.Forms.TreeView::get_Nodes()
0x4dd6f  ldloc.s  4
0x4dd71  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TreeNodeCollection::Add(class [System.Windows.Forms]System.Windows.Forms.TreeNode)
0x4dd76  pop
0x4dd77  newobj   instance void TemplateNode::.ctor()
0x4dd7c  stloc.s  5
0x4dd7e  ldarg.0
0x4dd7f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::availableColumnsTree
0x4dd84  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TreeNodeCollection [System.Windows.Forms]System.Windows.Forms.TreeView::get_Nodes()
0x4dd89  ldloc.s  5
0x4dd8b  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TreeNodeCollection::Add(class [System.Windows.Forms]System.Windows.Forms.TreeNode)
0x4dd90  pop
0x4dd91  ret
```
