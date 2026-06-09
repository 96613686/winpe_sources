# System.Web.UI.WebControls.TreeView::OnPreRender

- ea: `0xe74c0`
- end: `0xe7afd`
- name: `System.Web.UI.WebControls.TreeView::OnPreRender`
- size: `1597`
- prototype: ``
- caller_count: `0`
- callee_count: `48`
- tags: ``

## callees

- `0x5cf30`
- `0x5d500`
- `0x5d710`
- `0x5d920`
- `0x5d9a0`
- `0x5dac0`
- `0x5de10`
- `0x5ef10`
- `0x5f680`
- `0x5fc90`
- `0x61290`
- `0x6e1c0`
- `0x6e260`
- `0x71aa0`
- `0x728d0`
- `0x73d90`
- `0x74150`
- `0x77200`
- `0x7d270`
- `0x85fa0`
- `0x90c00`
- `0xdb670`
- `0xdb7e0`
- `0xe04e0`
- `0xe0880`
- `0xe3050`
- `0xe30a0`
- `0xe38e0`
- `0xe42b0`
- `0xe42e0`
- `0xe4520`
- `0xe4580`
- `0xe45c0`
- `0xe4780`
- `0xe47e0`
- `0xe4c30`
- `0xe4d30`
- `0xe4d60`
- `0xe4dd0`
- `0xe4de0`
- `0xe4eb0`
- `0xe4ec0`
- `0xe4fd0`
- `0xe5ba0`
- `0xe5e60`
- `0xe60e0`
- `0xe74c0`
- `0xe7f90`

## string_xrefs

- `0xe7864`: `.selectedHyperLinkClass = '`
- `0xe7934`: `.hoverHyperLinkClass = '`
- `0xe7a82`: `_CreateDataObject1`
- `0xe7ab1`: `_CreateDataObject2`

## pseudocode

```c

```

## disassembly

```asm
0xe74c0  ldarg.0
0xe74c1  ldarg.1
0xe74c2  call     instance void System.Web.UI.WebControls.BaseDataBoundControl::OnPreRender(class [mscorlib]System.EventArgs e)
0xe74c7  ldarg.0
0xe74c8  call     instance void System.Web.UI.WebControls.TreeView::EnsureRenderSettings()
0xe74cd  ldarg.0
0xe74ce  callvirt instance class System.Web.UI.Page System.Web.UI.Control::get_Page()
0xe74d3  brfalse  loc_E7AFC
0xe74d8  ldarg.0
0xe74d9  callvirt instance class System.Web.UI.Page System.Web.UI.Control::get_Page()
0xe74de  callvirt instance bool System.Web.UI.Page::get_IsPostBack()
0xe74e3  brtrue.s loc_E74FF
0xe74e5  ldarg.0
0xe74e6  ldfld    bool System.Web.UI.WebControls.TreeView::_dataBound
0xe74eb  brtrue.s loc_E74FF
0xe74ed  ldarg.0
0xe74ee  ldarg.0
0xe74ef  call     instance class System.Web.UI.WebControls.TreeNodeCollection System.Web.UI.WebControls.TreeView::get_Nodes()
0xe74f4  ldarg.0
0xe74f5  call     instance int32 System.Web.UI.WebControls.TreeView::get_ExpandDepth()
0xe74fa  call     instance void System.Web.UI.WebControls.TreeView::ExpandToDepth(class System.Web.UI.WebControls.TreeNodeCollection nodes, int32 depth)
0xe74ff  ldarg.0
0xe7500  callvirt instance class System.Web.UI.Page System.Web.UI.Control::get_Page()
0xe7505  ldarg.0
0xe7506  callvirt instance void System.Web.UI.Page::RegisterRequiresPostBack(class System.Web.UI.Control control)
0xe750b  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xe7510  stloc.0
0xe7511  ldc.i4.0
0xe7512  stloc.1
0xe7513  ldc.i4.0
0xe7514  stloc.2
0xe7515  br.s     loc_E7531
0xe7517  ldarg.0
0xe7518  ldarg.0
0xe7519  call     instance class System.Web.UI.WebControls.TreeNodeCollection System.Web.UI.WebControls.TreeView::get_Nodes()
0xe751e  ldloc.2
0xe751f  callvirt instance class System.Web.UI.WebControls.TreeNode System.Web.UI.WebControls.TreeNodeCollection::get_Item(int32 index)
0xe7524  ldloca.s 1
0xe7526  ldloc.0
0xe7527  ldc.i4.1
0xe7528  call     instance void System.Web.UI.WebControls.TreeView::SaveNodeState(class System.Web.UI.WebControls.TreeNode node, int32& index, class [mscorlib]System.Text.StringBuilder expandState, bool rendered)
0xe752d  ldloc.2
0xe752e  ldc.i4.1
0xe752f  add
0xe7530  stloc.2
0xe7531  ldloc.2
0xe7532  ldarg.0
0xe7533  call     instance class System.Web.UI.WebControls.TreeNodeCollection System.Web.UI.WebControls.TreeView::get_Nodes()
0xe7538  callvirt instance int32 System.Web.UI.WebControls.TreeNodeCollection::get_Count()
0xe753d  blt.s    loc_E7517
0xe753f  ldarg.0
0xe7540  call     instance bool System.Web.UI.WebControls.TreeView::get_RenderClientScript()
0xe7545  brfalse  loc_E7AFC
0xe754a  ldarg.0
0xe754b  callvirt instance class System.Web.UI.Page System.Web.UI.Control::get_Page()
0xe7550  callvirt instance class System.Web.UI.ClientScriptManager System.Web.UI.Page::get_ClientScript()
0xe7555  stloc.3
0xe7556  ldloc.3
0xe7557  ldarg.0
0xe7558  ldarg.0
0xe7559  call     instance string System.Web.UI.WebControls.TreeView::get_ExpandStateID()
0xe755e  ldloc.0
0xe755f  callvirt instance string [mscorlib]System.Object::ToString()
0xe7564  callvirt instance void System.Web.UI.ClientScriptManager::RegisterHiddenField(class System.Web.UI.Control control, string hiddenFieldName, string hiddenFieldValue)
0xe7569  ldc.i4.6
0xe756a  stloc.s  4
0xe756c  ldarg.0
0xe756d  call     instance bool System.Web.UI.WebControls.TreeView::get_ShowLines()
0xe7572  brfalse.s loc_E7578
0xe7574  ldc.i4.s 0x13
0xe7576  stloc.s  4
0xe7578  ldc.i4.0
0xe7579  stloc.s  0xC
0xe757b  br.s     loc_E75BE
0xe757d  ldarg.0
0xe757e  ldloc.s  0xC
0xe7580  call     instance string System.Web.UI.WebControls.TreeView::GetImageUrl(int32 index)
0xe7585  stloc.s  0xD
0xe7587  ldloc.s  0xD
0xe7589  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe758e  ldc.i4.0
0xe758f  ble.s    loc_E759A
0xe7591  ldloc.s  0xD
0xe7593  call     string System.Web.UI.Util::QuoteJScriptString(string value)
0xe7598  stloc.s  0xD
0xe759a  ldloc.3
0xe759b  ldarg.0
0xe759c  ldarg.0
0xe759d  call     instance string System.Web.UI.WebControls.TreeView::get_ImageArrayID()
0xe75a2  ldstr    asc_1BD99E// "'"
0xe75a7  ldloc.s  0xD
0xe75a9  ldstr    asc_1BD99E// "'"
0xe75ae  call     string [mscorlib]System.String::Concat(string, string, string)
0xe75b3  callvirt instance void System.Web.UI.ClientScriptManager::RegisterArrayDeclaration(class System.Web.UI.Control control, string arrayName, string arrayValue)
0xe75b8  ldloc.s  0xC
0xe75ba  ldc.i4.1
0xe75bb  add
0xe75bc  stloc.s  0xC
0xe75be  ldloc.s  0xC
0xe75c0  ldloc.s  4
0xe75c2  blt.s    loc_E757D
0xe75c4  ldsfld   string [mscorlib]System.String::Empty
0xe75c9  stloc.s  5
0xe75cb  ldarg.0
0xe75cc  call     instance class System.Web.UI.WebControls.TreeNode System.Web.UI.WebControls.TreeView::get_SelectedNode()
0xe75d1  brfalse.s loc_E763B
0xe75d3  ldarg.0
0xe75d4  call     instance class System.Web.UI.WebControls.TreeNode System.Web.UI.WebControls.TreeView::get_SelectedNode()
0xe75d9  stloc.s  0xE
0xe75db  br.s     loc_E75E6
0xe75dd  ldloc.s  0xE
0xe75df  callvirt instance class System.Web.UI.WebControls.TreeNode System.Web.UI.WebControls.TreeNode::GetParentInternal()
0xe75e4  stloc.s  0xE
0xe75e6  ldloc.s  0xE
0xe75e8  brfalse.s loc_E75F4
0xe75ea  ldloc.s  0xE
0xe75ec  ldarg.0
0xe75ed  call     instance class System.Web.UI.WebControls.TreeNode System.Web.UI.WebControls.TreeView::get_RootNode()
0xe75f2  bne.un.s loc_E75DD
0xe75f4  ldloc.s  0xE
0xe75f6  ldarg.0
0xe75f7  call     instance class System.Web.UI.WebControls.TreeNode System.Web.UI.WebControls.TreeView::get_RootNode()
0xe75fc  bne.un.s loc_E7628
0xe75fe  ldarg.0
0xe75ff  call     instance class System.Web.UI.WebControls.TreeNode System.Web.UI.WebControls.TreeView::get_SelectedNode()
0xe7604  callvirt instance string System.Web.UI.WebControls.TreeNode::get_SelectID()
0xe7609  stloc.s  5
0xe760b  ldarg.0
0xe760c  callvirt instance class System.Web.UI.StateBag System.Web.UI.Control::get_ViewState()
0xe7611  ldstr    aSelectednode_0// "SelectedNode"
0xe7616  ldarg.0
0xe7617  call     instance class System.Web.UI.WebControls.TreeNode System.Web.UI.WebControls.TreeView::get_SelectedNode()
0xe761c  callvirt instance string System.Web.UI.WebControls.TreeNode::get_SelectID()
0xe7621  callvirt instance void System.Web.UI.StateBag::set_Item(string key, object value)
0xe7626  br.s     loc_E764C
0xe7628  ldarg.0
0xe7629  callvirt instance class System.Web.UI.StateBag System.Web.UI.Control::get_ViewState()
0xe762e  ldstr    aSelectednode_0// "SelectedNode"
0xe7633  ldnull
0xe7634  callvirt instance void System.Web.UI.StateBag::set_Item(string key, object value)
0xe7639  br.s     loc_E764C
0xe763b  ldarg.0
0xe763c  callvirt instance class System.Web.UI.StateBag System.Web.UI.Control::get_ViewState()
0xe7641  ldstr    aSelectednode_0// "SelectedNode"
0xe7646  ldnull
0xe7647  callvirt instance void System.Web.UI.StateBag::set_Item(string key, object value)
0xe764c  ldloc.3
0xe764d  ldarg.0
0xe764e  ldarg.0
0xe764f  call     instance string System.Web.UI.WebControls.TreeView::get_SelectedNodeFieldID()
0xe7654  ldloc.s  5
0xe7656  callvirt instance void System.Web.UI.ClientScriptManager::RegisterHiddenField(class System.Web.UI.Control control, string hiddenFieldName, string hiddenFieldValue)
0xe765b  ldarg.0
0xe765c  callvirt instance class System.Web.UI.Page System.Web.UI.Control::get_Page()
0xe7661  callvirt instance void System.Web.UI.Page::RegisterWebFormsScript()
0xe7666  ldloc.3
0xe7667  ldarg.0
0xe7668  ldtoken  System.Web.UI.WebControls.TreeView
0xe766d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe7672  ldstr    aTreeviewJs// "TreeView.js"
0xe7677  callvirt instance void System.Web.UI.ClientScriptManager::RegisterClientScriptResource(class System.Web.UI.Control control, class [mscorlib]System.Type type, string resourceName)
0xe767c  ldarg.0
0xe767d  call     instance string System.Web.UI.WebControls.TreeView::get_ClientDataObjectID()
0xe7682  stloc.s  6
0xe7684  ldsfld   string [mscorlib]System.String::Empty
0xe7689  stloc.s  7
0xe768b  ldarg.0
0xe768c  call     instance bool System.Web.UI.WebControls.TreeView::get_PopulateNodesFromClient()
0xe7691  brfalse  loc_E779D
0xe7696  ldarg.0
0xe7697  callvirt instance class System.Web.UI.StateBag System.Web.UI.Control::get_ViewState()
0xe769c  ldstr    aLastindex// "LastIndex"
0xe76a1  ldloc.1
0xe76a2  box      [mscorlib]System.Int32
0xe76a7  callvirt instance void System.Web.UI.StateBag::set_Item(string key, object value)
0xe76ac  ldloc.3
0xe76ad  ldarg.0
0xe76ae  ldarg.0
0xe76af  call     instance string System.Web.UI.WebControls.TreeView::get_PopulateLogID()
0xe76b4  ldsfld   string [mscorlib]System.String::Empty
0xe76b9  callvirt instance void System.Web.UI.ClientScriptManager::RegisterHiddenField(class System.Web.UI.Control control, string hiddenFieldName, string hiddenFieldValue)
0xe76be  ldc.i4.s 0x10
0xe76c0  newarr   [mscorlib]System.String
0xe76c5  dup
0xe76c6  ldc.i4.0
0xe76c7  ldloc.s  6
0xe76c9  stelem.ref
0xe76ca  dup
0xe76cb  ldc.i4.1
0xe76cc  ldstr    aLastindex_0// ".lastIndex = "
0xe76d1  stelem.ref
0xe76d2  dup
0xe76d3  ldc.i4.2
0xe76d4  ldloca.s 1
0xe76d6  call     instance string [mscorlib]System.Int32::ToString()
0xe76db  stelem.ref
0xe76dc  dup
0xe76dd  ldc.i4.3
0xe76de  ldstr    asc_1DB6C2// ";\r\n"
0xe76e3  stelem.ref
0xe76e4  dup
0xe76e5  ldc.i4.4
0xe76e6  ldloc.s  6
0xe76e8  stelem.ref
0xe76e9  dup
0xe76ea  ldc.i4.5
0xe76eb  ldstr    aPopulatelogThe// ".populateLog = theForm.elements['"
0xe76f0  stelem.ref
0xe76f1  dup
0xe76f2  ldc.i4.6
0xe76f3  ldarg.0
0xe76f4  call     instance string System.Web.UI.WebControls.TreeView::get_PopulateLogID()
0xe76f9  stelem.ref
0xe76fa  dup
0xe76fb  ldc.i4.7
0xe76fc  ldstr    asc_1DB70E// "'];\r\n"
0xe7701  stelem.ref
0xe7702  dup
0xe7703  ldc.i4.8
0xe7704  ldloc.s  6
0xe7706  stelem.ref
0xe7707  dup
0xe7708  ldc.i4.s 9
0xe770a  ldstr    aTreeviewid// ".treeViewID = '"
0xe770f  stelem.ref
0xe7710  dup
0xe7711  ldc.i4.s 0xA
0xe7713  ldarg.0
0xe7714  callvirt instance string System.Web.UI.Control::get_UniqueID()
0xe7719  stelem.ref
0xe771a  dup
0xe771b  ldc.i4.s 0xB
0xe771d  ldstr    asc_1DB73A// "';\r\n"
0xe7722  stelem.ref
0xe7723  dup
0xe7724  ldc.i4.s 0xC
0xe7726  ldloc.s  6
0xe7728  stelem.ref
0xe7729  dup
0xe772a  ldc.i4.s 0xD
0xe772c  ldstr    aName_1// ".name = '"
0xe7731  stelem.ref
0xe7732  dup
0xe7733  ldc.i4.s 0xE
0xe7735  ldloc.s  6
0xe7737  stelem.ref
0xe7738  dup
0xe7739  ldc.i4.s 0xF
0xe773b  ldstr    asc_1DB73A// "';\r\n"
0xe7740  stelem.ref
0xe7741  call     string [mscorlib]System.String::Concat(string[])
0xe7746  stloc.s  7
0xe7748  ldloc.3
0xe7749  ldarg.0
0xe774a  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xe774f  ldstr    aPopulatenode// "PopulateNode"
0xe7754  callvirt instance bool System.Web.UI.ClientScriptManager::IsClientScriptBlockRegistered(class [mscorlib]System.Type type, string key)
0xe7759  brtrue.s loc_E779D
0xe775b  ldloc.3
0xe775c  ldarg.0
0xe775d  ldarg.0
0xe775e  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xe7763  ldstr    aPopulatenode// "PopulateNode"
0xe7768  ldsfld   string System.Web.UI.WebControls.TreeView::populateNodeScript
0xe776d  ldloc.3
0xe776e  ldstr    aContextDataTre// "context.data.treeViewID"
0xe7773  ldstr    aParam// "param"
0xe7778  ldstr    aTreeviewProces// "TreeView_ProcessNodeData"
0xe777d  ldstr    aContext// "context"
0xe7782  ldstr    aTreeviewProces// "TreeView_ProcessNodeData"
0xe7787  ldc.i4.0
0xe7788  callvirt instance string System.Web.UI.ClientScriptManager::GetCallbackEventReference(string target, string argument, string clientCallback, string context, string clientErrorCallback, bool useAsync)
0xe778d  ldsfld   string System.Web.UI.WebControls.TreeView::populateNodeScriptEnd
0xe7792  call     string [mscorlib]System.String::Concat(string, string, string)
0xe7797  ldc.i4.1
0xe7798  callvirt instance void System.Web.UI.ClientScriptManager::RegisterClientScriptBlock(class System.Web.UI.Control control, class [mscorlib]System.Type type, string key, string script, bool addScriptTags)
0xe779d  ldsfld   string [mscorlib]System.String::Empty
0xe77a2  stloc.s  8
0xe77a4  ldarg.0
0xe77a5  ldfld    class System.Web.UI.WebControls.TreeNodeStyle System.Web.UI.WebControls.TreeView::_selectedNodeStyle
0xe77aa  brfalse  loc_E787E
0xe77af  ldarg.0
0xe77b0  ldfld    class System.Web.UI.WebControls.TreeNodeStyle System.Web.UI.WebControls.TreeView::_selectedNodeStyle
0xe77b5  callvirt instance string System.Web.UI.WebControls.Style::get_RegisteredCssClass()
0xe77ba  stloc.s  0xF
0xe77bc  ldloc.s  0xF
0xe77be  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe77c3  ldc.i4.0
0xe77c4  ble.s    loc_E77D4
0xe77c6  ldloc.s  0xF
0xe77c8  ldstr    asc_1B0CBE// " "
0xe77cd  call     string [mscorlib]System.String::Concat(string, string)
0xe77d2  stloc.s  0xF
0xe77d4  ldarg.0
0xe77d5  ldfld    class System.Web.UI.WebControls.TreeNodeStyle System.Web.UI.WebControls.TreeView::_selectedNodeStyle
0xe77da  callvirt instance class System.Web.UI.WebControls.HyperLinkStyle System.Web.UI.WebControls.TreeNodeStyle::get_HyperLinkStyle()
0xe77df  callvirt instance string System.Web.UI.WebControls.Style::get_RegisteredCssClass()
0xe77e4  stloc.s  0x10
0xe77e6  ldloc.s  0x10
0xe77e8  callvirt instance int32 [mscorlib]System.String::get_Length()
  ... truncated ...
```
