# Microsoft.SharePoint.Meetings.MtgReorderPageToolPart::LoadScripts

- ea: `0x9c9910`
- end: `0x9c9cdf`
- name: `Microsoft.SharePoint.Meetings.MtgReorderPageToolPart::LoadScripts`
- size: `975`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x789ea0`
- `0x807b80`
- `0x807d80`
- `0x9c4220`
- `0x9d3ae0`
- `0x9d3b30`
- `0x9d3b60`
- `0x9d3b80`
- `0x9d3de0`
- `0x9d3df0`
- `0xa14620`

## string_xrefs

- `0x9c9916`: `MtgTlPart_MovedPages`
- `0x9c99c6`: `MtgTlPart_MoveUp`
- `0x9c9957`: `MtgTlPart_MoveDown`
- `0x9c993e`: `arrMovedItems`
- `0x9c9979`: `MtgTlPart_MoveCore(topNode, bottomNode);`
- `0x9c99e8`: `MtgTlPart_MoveCore(topNode, bottomNode);`
- `0x9c99b0`: `arrMovedItems[topNode.id] = 1;`
- `0x9c99bb`: `document.all['MtgTlPart_MovedPages'].value = arrMovedItems.toString();`
- `0x9c9a2a`: `document.all['MtgTlPart_MovedPages'].value = arrMovedItems.toString();`
- `0x9c9a1f`: `arrMovedItems[bottomNode.id] = 1;`
- `0x9c9a35`: `MtgTlPart_MoveCore`
- `0x9c9b23`: `var upObj = document.all['MtgTlPart_MoveUpName'];`
- `0x9c9b2f`: `var downObj = document.all['MtgTlPart_MoveDownName'];`
- `0x9c9c9c`: ` document.all['MtgTlPart_MoveUpName'].click();`
- `0x9c9cb4`: ` document.all['MtgTlPart_MoveDownName'].click();`

## pseudocode

```c

```

## disassembly

```asm
0x9c9910  ldarg.0
0x9c9911  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x9c9916  ldstr    aMtgtlpartMoved// "MtgTlPart_MovedPages"
0x9c991b  ldstr    asc_C00000// ""
0x9c9920  call     void Microsoft.SharePoint.WebControls.SPPageContentManager::RegisterHiddenField(class [System.Web]System.Web.UI.Page page, string hiddenFieldName, string hiddenFieldInitialValue)
0x9c9925  ldc.i4.0
0x9c9926  newobj   instance void Microsoft.SharePoint.WebPartPages.ScriptBuilder::.ctor(bool includeScriptTags)
0x9c992b  stloc.0
0x9c992c  ldloc.0
0x9c992d  ldstr    aItemselected// "ItemSelected"
0x9c9932  ldstr    asc_D175B2// "''"
0x9c9937  callvirt instance class ScriptVariable Microsoft.SharePoint.WebPartPages.ScriptBuilder::AddVariable(string name, string initialValue)
0x9c993c  pop
0x9c993d  ldloc.0
0x9c993e  ldstr    aArrmoveditems// "arrMovedItems"
0x9c9943  ldstr    aNewArray_0// "new Array()"
0x9c9948  callvirt instance class ScriptVariable Microsoft.SharePoint.WebPartPages.ScriptBuilder::AddVariable(string name, string initialValue)
0x9c994d  pop
0x9c994e  ldarg.0
0x9c994f  ldloca.s 0
0x9c9951  call     instance void Microsoft.SharePoint.Meetings.MtgPageToolPart::LoadSelectScript(class Microsoft.SharePoint.WebPartPages.ScriptBuilder& script)
0x9c9956  ldloc.0
0x9c9957  ldstr    aMtgtlpartMoved_1// "MtgTlPart_MoveDown"
0x9c995c  callvirt instance class ScriptFunction Microsoft.SharePoint.WebPartPages.ScriptBuilder::AddFunction(string name)
0x9c9961  stloc.1
0x9c9962  ldloc.1
0x9c9963  ldstr    aVarTopnodeMtgt// "var topNode = MtgTlPart_GetTrObj(ItemSe"...
0x9c9968  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c996d  ldloc.1
0x9c996e  ldstr    aVarBottomnodeT// "var bottomNode = topNode.nextSibling;"
0x9c9973  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9978  ldloc.1
0x9c9979  ldstr    aMtgtlpartMovec// "MtgTlPart_MoveCore(topNode, bottomNode)"...
0x9c997e  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9983  ldloc.1
0x9c9984  ldstr    aMtgtlpartSetbu// "MtgTlPart_SetButtons();"
0x9c9989  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c998e  ldloc.1
0x9c998f  ldstr    aEventCancelbub// "event.cancelBubble = true;"
0x9c9994  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9999  ldloc.1
0x9c999a  ldstr    aEventReturnval_0// "event.returnValue = false;"
0x9c999f  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c99a4  ldloc.1
0x9c99a5  ldstr    aItemselectedFo// "ItemSelected.focus();"
0x9c99aa  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c99af  ldloc.1
0x9c99b0  ldstr    aArrmoveditemsT// "arrMovedItems[topNode.id] = 1;"
0x9c99b5  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c99ba  ldloc.1
0x9c99bb  ldstr    aDocumentAllMtg_1// "document.all['MtgTlPart_MovedPages'].va"...
0x9c99c0  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c99c5  ldloc.0
0x9c99c6  ldstr    aMtgtlpartMoveu_0// "MtgTlPart_MoveUp"
0x9c99cb  callvirt instance class ScriptFunction Microsoft.SharePoint.WebPartPages.ScriptBuilder::AddFunction(string name)
0x9c99d0  stloc.2
0x9c99d1  ldloc.2
0x9c99d2  ldstr    aVarBottomnodeM// "var bottomNode = MtgTlPart_GetTrObj(Ite"...
0x9c99d7  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c99dc  ldloc.2
0x9c99dd  ldstr    aVarTopnodeBott// "var topNode = bottomNode.previousSiblin"...
0x9c99e2  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c99e7  ldloc.2
0x9c99e8  ldstr    aMtgtlpartMovec// "MtgTlPart_MoveCore(topNode, bottomNode)"...
0x9c99ed  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c99f2  ldloc.2
0x9c99f3  ldstr    aMtgtlpartSetbu// "MtgTlPart_SetButtons();"
0x9c99f8  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c99fd  ldloc.2
0x9c99fe  ldstr    aEventCancelbub// "event.cancelBubble = true;"
0x9c9a03  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9a08  ldloc.2
0x9c9a09  ldstr    aEventReturnval_0// "event.returnValue = false;"
0x9c9a0e  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9a13  ldloc.2
0x9c9a14  ldstr    aItemselectedFo// "ItemSelected.focus();"
0x9c9a19  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9a1e  ldloc.2
0x9c9a1f  ldstr    aArrmoveditemsB// "arrMovedItems[bottomNode.id] = 1;"
0x9c9a24  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9a29  ldloc.2
0x9c9a2a  ldstr    aDocumentAllMtg_1// "document.all['MtgTlPart_MovedPages'].va"...
0x9c9a2f  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9a34  ldloc.0
0x9c9a35  ldstr    aMtgtlpartMovec_0// "MtgTlPart_MoveCore"
0x9c9a3a  callvirt instance class ScriptFunction Microsoft.SharePoint.WebPartPages.ScriptBuilder::AddFunction(string name)
0x9c9a3f  stloc.3
0x9c9a40  ldloc.3
0x9c9a41  ldstr    aTopnodeBottomn// "topNode, bottomNode"
0x9c9a46  callvirt instance void ScriptFunction::AddParameter(string theName)
0x9c9a4b  ldloc.3
0x9c9a4c  ldstr    aVarStrMtgtlpar// "var str = 'MtgTlPart_PagePos' + topNode"...
0x9c9a51  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9a56  ldloc.3
0x9c9a57  ldstr    aVarValNumberDo// "var val = Number(document.all[str].valu"...
0x9c9a5c  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9a61  ldloc.3
0x9c9a62  ldstr    aDocumentAllStr// "document.all[str].value = val + 1;"
0x9c9a67  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9a6c  ldloc.3
0x9c9a6d  ldstr    aDocumentAllMtg_2// "document.all['MtgTlPart_PagePos' + bott"...
0x9c9a72  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9a77  ldloc.3
0x9c9a78  ldstr    aTopnodeSwapnod// " topNode.swapNode(bottomNode);"
0x9c9a7d  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9a82  ldloc.0
0x9c9a83  ldstr    aMtgtlpartSelec_2// "MtgTlPart_SelectCore"
0x9c9a88  callvirt instance class ScriptFunction Microsoft.SharePoint.WebPartPages.ScriptBuilder::AddFunction(string name)
0x9c9a8d  stloc.s  4
0x9c9a8f  ldloc.s  4
0x9c9a91  ldstr    aSrcelement// "srcElement"
0x9c9a96  callvirt instance void ScriptFunction::AddParameter(string theName)
0x9c9a9b  ldloc.s  4
0x9c9a9d  ldstr    aIfItemselected// "if (ItemSelected != null) "
0x9c9aa2  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9aa7  ldloc.s  4
0x9c9aa9  ldstr    aItemselectedCl// " ItemSelected.className='UserCell';"
0x9c9aae  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9ab3  ldloc.s  4
0x9c9ab5  ldstr    aSrcelementClas// "srcElement.className='UserCellSelected'"...
0x9c9aba  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9abf  ldloc.s  4
0x9c9ac1  ldstr    aSrcelementFocu// "srcElement.focus();"
0x9c9ac6  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9acb  ldloc.s  4
0x9c9acd  ldstr    aItemselectedSr// "ItemSelected = srcElement;"
0x9c9ad2  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9ad7  ldloc.s  4
0x9c9ad9  ldstr    aMtgtlpartSetbu// "MtgTlPart_SetButtons();"
0x9c9ade  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9ae3  ldloc.0
0x9c9ae4  ldstr    aMtgtlpartGettr// "MtgTlPart_GetTrObj"
0x9c9ae9  callvirt instance class ScriptFunction Microsoft.SharePoint.WebPartPages.ScriptBuilder::AddFunction(string name)
0x9c9aee  stloc.s  5
0x9c9af0  ldloc.s  5
0x9c9af2  ldstr    aSpanobj// "spanObj"
0x9c9af7  callvirt instance void ScriptFunction::AddParameter(string theName)
0x9c9afc  ldloc.s  5
0x9c9afe  ldstr    aIfSpanobjNullR// "if (spanObj != null) return spanObj.par"...
0x9c9b03  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9b08  ldloc.s  5
0x9c9b0a  ldstr    aElseReturnSpan// "else return spanObj;"
0x9c9b0f  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9b14  ldloc.0
0x9c9b15  ldstr    aMtgtlpartSetbu_0// "MtgTlPart_SetButtons"
0x9c9b1a  callvirt instance class ScriptFunction Microsoft.SharePoint.WebPartPages.ScriptBuilder::AddFunction(string name)
0x9c9b1f  stloc.s  6
0x9c9b21  ldloc.s  6
0x9c9b23  ldstr    aVarUpobjDocume// "var upObj = document.all['MtgTlPart_Mov"...
0x9c9b28  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9b2d  ldloc.s  6
0x9c9b2f  ldstr    aVarDownobjDocu// "var downObj = document.all['MtgTlPart_M"...
0x9c9b34  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9b39  ldloc.s  6
0x9c9b3b  ldstr    aVarItemMtgtlpa// "var item = MtgTlPart_GetTrObj(ItemSelec"...
0x9c9b40  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9b45  ldloc.s  6
0x9c9b47  ldstr    aIfItemNullItem// " if (item == null || item.nextSibling ="...
0x9c9b4c  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9b51  ldloc.s  6
0x9c9b53  ldstr    aIfDownobjDisab// "{ if (downObj.disabled == false)"
0x9c9b58  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9b5d  ldloc.s  6
0x9c9b5f  ldstr    aDownobjDisable// "  { downObj.disabled = true; "
0x9c9b64  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9b69  ldloc.s  6
0x9c9b6b  ldstr    aDownobjChildre// " downObj.children[0].src = '"
0x9c9b70  ldstr    aImagesArrdowni// "images/arrdowni.gif"
0x9c9b75  call     string Microsoft.SharePoint.WebPartPages.Utility::MakeLayoutsRootServerRelative(string relativePath)
0x9c9b7a  call     string Microsoft.SharePoint.Utilities.SPHttpUtility::NoEncode(string valueToEncode)
0x9c9b7f  ldstr    asc_1265618// "'; } }"
0x9c9b84  call     string [mscorlib]System.String::Concat(string, string, string)
0x9c9b89  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9b8e  ldloc.s  6
0x9c9b90  ldstr    aElseIfDownobjD// "else if (downObj.disabled == true) "
0x9c9b95  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9b9a  ldloc.s  6
0x9c9b9c  ldstr    aDownobjDisable_0// " { downObj.disabled = false; "
0x9c9ba1  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9ba6  ldloc.s  6
0x9c9ba8  ldstr    aDownobjChildre_0// "   downObj.children[0].src = '"
0x9c9bad  ldstr    aImagesArrdowna// "images/arrdowna.gif"
0x9c9bb2  call     string Microsoft.SharePoint.WebPartPages.Utility::MakeLayoutsRootServerRelative(string relativePath)
0x9c9bb7  call     string Microsoft.SharePoint.Utilities.SPHttpUtility::NoEncode(string valueToEncode)
0x9c9bbc  ldstr    asc_1265710// "'; }"
0x9c9bc1  call     string [mscorlib]System.String::Concat(string, string, string)
0x9c9bc6  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9bcb  ldloc.s  6
0x9c9bcd  ldstr    aIfItemNullItem_0// "if (item == null || item.previousSiblin"...
0x9c9bd2  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9bd7  ldloc.s  6
0x9c9bd9  ldstr    aIfUpobjDisable// "{ if(upObj.disabled == false) "
0x9c9bde  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9be3  ldloc.s  6
0x9c9be5  ldstr    aUpobjDisabledT// " { upObj.disabled = true; "
0x9c9bea  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9bef  ldloc.s  6
0x9c9bf1  ldstr    aUpobjChildren0// "   upObj.children[0].src = '"
0x9c9bf6  ldstr    aImagesArrupiGi// "images/arrupi.gif"
0x9c9bfb  call     string Microsoft.SharePoint.WebPartPages.Utility::MakeLayoutsRootServerRelative(string relativePath)
0x9c9c00  call     string Microsoft.SharePoint.Utilities.SPHttpUtility::NoEncode(string valueToEncode)
0x9c9c05  ldstr    asc_1265618// "'; } }"
0x9c9c0a  call     string [mscorlib]System.String::Concat(string, string, string)
0x9c9c0f  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9c14  ldloc.s  6
0x9c9c16  ldstr    aElseIfUpobjDis// "else if (upObj.disabled == true) "
0x9c9c1b  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9c20  ldloc.s  6
0x9c9c22  ldstr    aUpobjDisabledF// " { upObj.disabled = false; "
0x9c9c27  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9c2c  ldloc.s  6
0x9c9c2e  ldstr    aUpobjChildren0// "   upObj.children[0].src = '"
0x9c9c33  ldstr    aImagesArrupaGi// "images/arrupa.gif"
0x9c9c38  call     string Microsoft.SharePoint.WebPartPages.Utility::MakeLayoutsRootServerRelative(string relativePath)
0x9c9c3d  call     string Microsoft.SharePoint.Utilities.SPHttpUtility::NoEncode(string valueToEncode)
0x9c9c42  ldstr    asc_1265710// "'; }"
0x9c9c47  call     string [mscorlib]System.String::Concat(string, string, string)
0x9c9c4c  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9c51  ldloc.0
0x9c9c52  ldstr    aMtgtlpartKeydo_0// "MtgTlPart_KeyDown"
0x9c9c57  callvirt instance class ScriptFunction Microsoft.SharePoint.WebPartPages.ScriptBuilder::AddFunction(string name)
0x9c9c5c  stloc.s  7
0x9c9c5e  ldloc.s  7
0x9c9c60  ldstr    aVarSrcelementE_0// "var srcElement = event.srcElement;"
0x9c9c65  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9c6a  ldloc.s  7
0x9c9c6c  ldstr    aVarKeyWindowEv// "var key = window.event.keyCode;"
0x9c9c71  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9c76  ldloc.s  7
0x9c9c78  ldstr    aIfKey32// "if (key == 32) "
0x9c9c7d  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9c82  ldloc.s  7
0x9c9c84  ldstr    aMtgtlpartSelec_3// "MtgTlPart_Select();"
0x9c9c89  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9c8e  ldloc.s  7
0x9c9c90  ldstr    aElseIfKey38Ite// "else if (key == 38 && ItemSelected == s"...
0x9c9c95  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9c9a  ldloc.s  7
0x9c9c9c  ldstr    aDocumentAllMtg_3// " document.all['MtgTlPart_MoveUpName'].c"...
0x9c9ca1  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9ca6  ldloc.s  7
0x9c9ca8  ldstr    aElseIfKey40Ite// "else if (key == 40 && ItemSelected == s"...
0x9c9cad  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9cb2  ldloc.s  7
0x9c9cb4  ldstr    aDocumentAllMtg_4// " document.all['MtgTlPart_MoveDownName']"...
0x9c9cb9  callvirt instance void ScriptFunction::AddStatement(string line)
0x9c9cbe  ldarg.0
0x9c9cbf  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x9c9cc4  ldtoken  Microsoft.SharePoint.Meetings.MtgReorderPageToolPart
0x9c9cc9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9c9cce  ldstr    aMtgtlpartReord// "MtgTlPart_Reorder"
0x9c9cd3  ldloc.0
0x9c9cd4  callvirt instance string Microsoft.SharePoint.WebPartPages.ScriptBuilder::get_ScriptText()
0x9c9cd9  call     void Microsoft.SharePoint.WebControls.SPPageContentManager::RegisterClientScriptBlock(class [System.Web]System.Web.UI.Page page, class [mscorlib]System.Type type, string key, string script)
0x9c9cde  ret
```
