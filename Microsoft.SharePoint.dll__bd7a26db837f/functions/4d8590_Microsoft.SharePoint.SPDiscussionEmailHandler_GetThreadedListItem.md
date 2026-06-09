# Microsoft.SharePoint.SPDiscussionEmailHandler::GetThreadedListItem

- ea: `0x4d8590`
- end: `0x4d8b54`
- name: `Microsoft.SharePoint.SPDiscussionEmailHandler::GetThreadedListItem`
- size: `1476`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x4d8410`

## callees

- `0x188380`
- `0x189150`
- `0x189160`
- `0x189170`
- `0x1b5530`
- `0x1b57a0`
- `0x1b7de0`
- `0x342e60`
- `0x347ec0`
- `0x348a20`
- `0x3e99a0`
- `0x3e99e0`
- `0x3e99f0`
- `0x4c02c0`
- `0x4d84f0`
- `0x4d8590`
- `0x4d8b60`
- `0x4d8cb0`
- `0x4d90c0`
- `0x4d94e0`
- `0x526550`
- `0x53e4b0`
- `0x53e8c0`
- `0x54cf70`
- `0x54cff0`
- `0x574e40`
- `0x575160`
- `0x5751a0`
- `0x575390`
- `0x577060`
- `0x5ccf30`

## string_xrefs

- `0x4d8677`: `ThreadIndex`
- `0x4d8887`: `ThreadIndex`
- `0x4d8970`: `ThreadIndex`
- `0x4d8b1b`: `ThreadIndex`
- `0x4d86a6`: `DiscussionLastUpdated`
- `0x4d8ac0`: `DiscussionLastUpdated`
- `0x4d8696`: `ShortestThreadIndexId`
- `0x4d8610`: `ThreadTopic`
- `0x4d8b0e`: `ThreadTopic`
- `0x4d8684`: `ShortestThreadIndex`
- `0x4d8a75`: `ShortestThreadIndex`
- `0x4d8aa6`: `ShortestThreadIndex`
- `0x4d8715`: `<FieldRef Name="ID"/><FieldRef Name="MessageId"/><FieldRef Name="EmailReferences"/><FieldRef Name="ThreadIndex"/><FieldRef Name="ThreadTopic"/>`
- `0x4d88a3`: `DuplicateThreadIndexError`

## pseudocode

```c

```

## disassembly

```asm
0x4d8590  ldnull
0x4d8591  stloc.0
0x4d8592  ldarg.3
0x4d8593  ldc.i4.0
0x4d8594  stind.i1
0x4d8595  ldarg.s  4
0x4d8597  ldnull
0x4d8598  stind.ref
0x4d8599  ldarg.s  5
0x4d859b  ldnull
0x4d859c  stind.ref
0x4d859d  ldarga.s 1
0x4d859f  ldfld    valuetype ThreadingHeaders MessageContainer::headers
0x4d85a4  stloc.1
0x4d85a5  ldarg.0
0x4d85a6  ldarg.1
0x4d85a7  ldloca.s 2
0x4d85a9  call     instance class Microsoft.SharePoint.SPListItem Microsoft.SharePoint.SPDiscussionEmailHandler::GetFolder(valuetype MessageContainer container, [out] class Microsoft.SharePoint.SPListItemCollection& candidates)
0x4d85ae  stloc.3
0x4d85af  ldloc.3
0x4d85b0  brtrue   loc_4D86C7
0x4d85b5  ldloc.2
0x4d85b6  ldarg.0
0x4d85b7  ldfld    class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPDiscussionEmailHandler::m_List
0x4d85bc  callvirt instance string Microsoft.SharePoint.SPList::get_RootFolderUrl()
0x4d85c1  ldc.i4.1
0x4d85c2  ldsfld   string [mscorlib]System.String::Empty
0x4d85c7  callvirt instance class Microsoft.SharePoint.SPListItem Microsoft.SharePoint.SPListItemCollection::Add(string folderUrl, valuetype Microsoft.SharePoint.SPFileSystemObjectType underlyingObjectType, string leafName)
0x4d85cc  stloc.0
0x4d85cd  ldloca.s 1
0x4d85cf  ldfld    string ThreadingHeaders::normalizedSubject
0x4d85d4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4d85d9  brfalse.s loc_4D85E7
0x4d85db  ldloc.0
0x4d85dc  ldarg.0
0x4d85dd  call     instance string Microsoft.SharePoint.SPDiscussionEmailHandler::get_NoTitle()
0x4d85e2  callvirt instance void Microsoft.SharePoint.SPListItem::set_Name(string value)
0x4d85e7  ldloc.0
0x4d85e8  ldstr    aContenttype// "ContentType"
0x4d85ed  ldarg.0
0x4d85ee  ldfld    class Microsoft.SharePoint.SPContentType Microsoft.SharePoint.SPDiscussionEmailHandler::m_ContentTypeDiscussion
0x4d85f3  callvirt instance string Microsoft.SharePoint.SPContentType::get_Name()
0x4d85f8  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x4d85fd  ldloc.0
0x4d85fe  ldstr    aRelevantmessag// "RelevantMessages"
0x4d8603  ldloca.s 1
0x4d8605  ldfld    string ThreadingHeaders::messageId
0x4d860a  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x4d860f  ldloc.0
0x4d8610  ldstr    aThreadtopic// "ThreadTopic"
0x4d8615  ldloca.s 1
0x4d8617  ldfld    string ThreadingHeaders::threadTopic
0x4d861c  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x4d8621  ldloc.0
0x4d8622  ldstr    aMessageid// "MessageId"
0x4d8627  ldloca.s 1
0x4d8629  ldfld    string ThreadingHeaders::messageId
0x4d862e  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x4d8633  ldloc.0
0x4d8634  ldstr    aEmailreference// "EmailReferences"
0x4d8639  ldloca.s 1
0x4d863b  ldfld    string ThreadingHeaders::emailReferences
0x4d8640  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x4d8645  ldloca.s 1
0x4d8647  ldfld    string ThreadingHeaders::threadIndex
0x4d864c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4d8651  brtrue.s loc_4D865E
0x4d8653  ldloca.s 1
0x4d8655  ldfld    string ThreadingHeaders::threadIndex
0x4d865a  stloc.s  4
0x4d865c  br.s     loc_4D8676
0x4d865e  ldnull
0x4d865f  ldarg.0
0x4d8660  ldfld    class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPDiscussionEmailHandler::m_List
0x4d8665  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0x4d866a  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.SPWeb::get_ServerNow()
0x4d866f  call     string Microsoft.SharePoint.Utilities.SPUtility::CreateThreadIndex(string parentIndex, valuetype [mscorlib]System.DateTime time)
0x4d8674  stloc.s  4
0x4d8676  ldloc.0
0x4d8677  ldstr    aThreadindex// "ThreadIndex"
0x4d867c  ldloc.s  4
0x4d867e  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x4d8683  ldloc.0
0x4d8684  ldstr    aShortestthread_0// "ShortestThreadIndex"
0x4d8689  ldloc.s  4
0x4d868b  call     string Microsoft.SharePoint.SPDiscussionEmailHandler::ConvertToUpperCaseHex(string hexString)
0x4d8690  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x4d8695  ldloc.0
0x4d8696  ldstr    aShortestthread// "ShortestThreadIndexId"
0x4d869b  ldstr    a0// "0"
0x4d86a0  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x4d86a5  ldloc.0
0x4d86a6  ldstr    aDiscussionlast// "DiscussionLastUpdated"
0x4d86ab  ldarg.0
0x4d86ac  ldfld    class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPDiscussionEmailHandler::m_List
0x4d86b1  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0x4d86b6  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.SPWeb::get_ServerNow()
0x4d86bb  box      [mscorlib]System.DateTime
0x4d86c0  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x4d86c5  ldloc.0
0x4d86c6  ret
0x4d86c7  ldloc.3
0x4d86c8  ldstr    aMessageid// "MessageId"
0x4d86cd  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0x4d86d2  castclass [mscorlib]System.String
0x4d86d7  stloc.s  5
0x4d86d9  ldloc.s  5
0x4d86db  brfalse.s loc_4D86F2
0x4d86dd  ldloc.s  5
0x4d86df  ldloca.s 1
0x4d86e1  ldfld    string ThreadingHeaders::messageId
0x4d86e6  call     bool Microsoft.SharePoint.Utilities.SPUtility::StsCompareStrings(string str1, string str2)
0x4d86eb  brfalse.s loc_4D86F2
0x4d86ed  ldarg.3
0x4d86ee  ldc.i4.1
0x4d86ef  stind.i1
0x4d86f0  ldloc.3
0x4d86f1  ret
0x4d86f2  newobj   instance void Microsoft.SharePoint.SPQuery::.ctor()
0x4d86f7  stloc.s  6
0x4d86f9  ldloc.s  6
0x4d86fb  ldloc.1
0x4d86fc  call     string Microsoft.SharePoint.SPDiscussionEmailHandler::GetQueryString(valuetype ThreadingHeaders headers)
0x4d8701  callvirt instance void Microsoft.SharePoint.SPQuery::set_Query(string value)
0x4d8706  ldloc.s  6
0x4d8708  ldloc.3
0x4d8709  callvirt instance class Microsoft.SharePoint.SPFolder Microsoft.SharePoint.SPListItem::get_Folder()
0x4d870e  callvirt instance void Microsoft.SharePoint.SPQuery::set_Folder(class Microsoft.SharePoint.SPFolder value)
0x4d8713  ldloc.s  6
0x4d8715  ldstr    aFieldrefNameId_7// "<FieldRef Name=\"ID\"/><FieldRef Name="...
0x4d871a  callvirt instance void Microsoft.SharePoint.SPQuery::set_ViewFields(string value)
0x4d871f  ldarg.0
0x4d8720  ldfld    class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPDiscussionEmailHandler::m_List
0x4d8725  ldloc.s  6
0x4d8727  callvirt instance class Microsoft.SharePoint.SPListItemCollection Microsoft.SharePoint.SPList::GetItems(class Microsoft.SharePoint.SPQuery query)
0x4d872c  stloc.s  7
0x4d872e  ldloc.s  7
0x4d8730  callvirt instance int32 Microsoft.SharePoint.SPBaseCollection::get_Count()
0x4d8735  ldc.i4.1
0x4d8736  add
0x4d8737  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.SPListItem>::.ctor(int32)
0x4d873c  stloc.s  8
0x4d873e  ldloc.s  8
0x4d8740  ldloc.3
0x4d8741  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.SPListItem>::Add(var<u1>)
0x4d8746  ldloc.s  7
0x4d8748  callvirt instance class [mscorlib]System.Collections.IEnumerator Microsoft.SharePoint.SPBaseCollection::GetEnumerator()
0x4d874d  stloc.s  0x27
0x4d874f  br.s     loc_4D8768
0x4d8751  ldloc.s  0x27
0x4d8753  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4d8758  castclass Microsoft.SharePoint.SPListItem
0x4d875d  stloc.s  9
0x4d875f  ldloc.s  8
0x4d8761  ldloc.s  9
0x4d8763  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.SPListItem>::Add(var<u1>)
0x4d8768  ldloc.s  0x27
0x4d876a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4d876f  brtrue.s loc_4D8751
0x4d8771  leave.s  loc_4D8788
0x4d8773  ldloc.s  0x27
0x4d8775  isinst   [mscorlib]System.IDisposable
0x4d877a  stloc.s  0x28
0x4d877c  ldloc.s  0x28
0x4d877e  brfalse.s loc_4D8787
0x4d8780  ldloc.s  0x28
0x4d8782  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4d8787  endfinally
0x4d8788  ldloca.s 1
0x4d878a  ldfld    string ThreadingHeaders::messageId
0x4d878f  stloc.s  0xA
0x4d8791  ldloca.s 1
0x4d8793  ldfld    string ThreadingHeaders::threadTopic
0x4d8798  stloc.s  0xB
0x4d879a  ldloca.s 1
0x4d879c  ldfld    string ThreadingHeaders::threadIndex
0x4d87a1  stloc.s  0xC
0x4d87a3  ldloca.s 1
0x4d87a5  ldfld    string[] ThreadingHeaders::references
0x4d87aa  stloc.s  0xD
0x4d87ac  ldnull
0x4d87ad  stloc.s  0xE
0x4d87af  ldc.i4.0
0x4d87b0  stloc.s  0xF
0x4d87b2  ldc.i4   0x7FFFFFFF
0x4d87b7  stloc.s  0x10
0x4d87b9  ldc.i4.0
0x4d87ba  stloc.s  0x11
0x4d87bc  ldnull
0x4d87bd  stloc.s  0x12
0x4d87bf  ldc.i4   0x7FFFFFFF
0x4d87c4  stloc.s  0x13
0x4d87c6  ldc.i4.0
0x4d87c7  stloc.s  0x14
0x4d87c9  ldloc.s  8
0x4d87cb  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.SPListItem>::GetEnumerator()
0x4d87d0  stloc.s  0x29
0x4d87d2  br       loc_4D88FB
0x4d87d7  ldloca.s 0x29
0x4d87d9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.SPListItem>::get_Current()
0x4d87de  stloc.s  0x15
0x4d87e0  ldloc.s  0x15
0x4d87e2  ldstr    aMessageid// "MessageId"
0x4d87e7  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0x4d87ec  castclass [mscorlib]System.String
0x4d87f1  stloc.s  0x16
0x4d87f3  ldloc.s  0xA
0x4d87f5  ldloc.s  0x16
0x4d87f7  callvirt instance bool [mscorlib]System.String::Equals(string)
0x4d87fc  brfalse.s loc_4D880A
0x4d87fe  ldarg.3
0x4d87ff  ldc.i4.1
0x4d8800  stind.i1
0x4d8801  ldloc.s  0x15
0x4d8803  stloc.s  0x26
0x4d8805  leave    loc_4D8B51
0x4d880a  ldloc.s  0xD
0x4d880c  ldlen
0x4d880d  conv.i4
0x4d880e  ldc.i4.0
0x4d880f  ble.s    loc_4D8837
0x4d8811  ldc.i4.0
0x4d8812  ldloc.s  0x13
0x4d8814  bge.s    loc_4D8837
0x4d8816  ldloc.s  0xD
0x4d8818  ldloc.s  0x16
0x4d881a  call     T0x2B000051
0x4d881f  stloc.s  0x17
0x4d8821  ldloc.s  0x17
0x4d8823  ldc.i4.0
0x4d8824  blt.s    loc_4D8837
0x4d8826  ldloc.s  0x17
0x4d8828  ldloc.s  0x13
0x4d882a  bgt.s    loc_4D8837
0x4d882c  ldc.i4.1
0x4d882d  stloc.s  0x14
0x4d882f  ldloc.s  0x15
0x4d8831  stloc.s  0x12
0x4d8833  ldloc.s  0x17
0x4d8835  stloc.s  0x13
0x4d8837  ldloc.s  0x15
0x4d8839  ldstr    aEmailreference// "EmailReferences"
0x4d883e  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0x4d8843  castclass [mscorlib]System.String
0x4d8848  stloc.s  0x18
0x4d884a  ldloc.s  0x18
0x4d884c  brfalse.s loc_4D8881
0x4d884e  ldc.i4.0
0x4d884f  ldloc.s  0x13
0x4d8851  bge.s    loc_4D8881
0x4d8853  ldloc.s  0x18
0x4d8855  ldstr    aS_3// "[\\s]+"
0x4d885a  call     string[] [System]System.Text.RegularExpressions.Regex::Split(string, string)
0x4d885f  stloc.s  0x19
0x4d8861  ldloc.s  0x19
0x4d8863  ldloc.s  0xA
0x4d8865  call     T0x2B000051
0x4d886a  stloc.s  0x1A
0x4d886c  ldloc.s  0x1A
0x4d886e  ldc.i4.0
0x4d886f  blt.s    loc_4D8881
0x4d8871  ldc.i4.1
0x4d8872  stloc.s  0x14
0x4d8874  ldloc.s  0x15
0x4d8876  stloc.s  0x12
0x4d8878  ldloc.s  0x1A
0x4d887a  ldloc.s  0x19
0x4d887c  ldlen
0x4d887d  conv.i4
0x4d887e  sub
0x4d887f  stloc.s  0x13
0x4d8881  ldloc.s  0xC
0x4d8883  brfalse.s loc_4D88FB
0x4d8885  ldloc.s  0x15
0x4d8887  ldstr    aThreadindex// "ThreadIndex"
0x4d888c  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0x4d8891  castclass [mscorlib]System.String
0x4d8896  stloc.s  0x1B
0x4d8898  ldloc.s  0xC
0x4d889a  ldloc.s  0x1B
0x4d889c  callvirt instance bool [mscorlib]System.String::Equals(string)
0x4d88a1  brfalse.s loc_4D88B9
0x4d88a3  ldstr    aDuplicatethrea// "DuplicateThreadIndexError"
0x4d88a8  ldc.i4.0
0x4d88a9  newarr   [mscorlib]System.Object
0x4d88ae  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x4d88b3  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x4d88b8  throw
0x4d88b9  ldloc.s  0x1B
0x4d88bb  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4d88c0  ldloc.s  0xF
0x4d88c2  ble.s    loc_4D88CF
0x4d88c4  ldloc.s  0xC
0x4d88c6  ldloc.s  0x1B
0x4d88c8  call     bool Microsoft.SharePoint.Utilities.SPUtility::StsStartsWith(string strMain, string strBegining)
0x4d88cd  brtrue.s loc_4D88DA
0x4d88cf  ldloc.s  0x1B
0x4d88d1  ldloc.s  0xC
0x4d88d3  call     bool Microsoft.SharePoint.Utilities.SPUtility::StsStartsWith(string strMain, string strBegining)
0x4d88d8  brfalse.s loc_4D88FB
  ... truncated ...
```
