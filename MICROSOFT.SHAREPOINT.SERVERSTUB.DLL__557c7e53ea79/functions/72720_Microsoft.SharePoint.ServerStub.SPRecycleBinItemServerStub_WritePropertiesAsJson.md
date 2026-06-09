# Microsoft.SharePoint.ServerStub.SPRecycleBinItemServerStub::WritePropertiesAsJson

- ea: `0x72720`
- end: `0x72a9b`
- name: `Microsoft.SharePoint.ServerStub.SPRecycleBinItemServerStub::WritePropertiesAsJson`
- size: `891`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x72720`

## string_xrefs

- `0x727a9`: `DeletedByEmail`
- `0x727b5`: `DeletedByEmail`
- `0x727c0`: `DeletedByEmail`
- `0x727d8`: `DeletedByEmail`
- `0x727e3`: `DeletedByName`
- `0x727ef`: `DeletedByName`
- `0x727fa`: `DeletedByName`
- `0x72812`: `DeletedByName`
- `0x7281d`: `DeletedDate`
- `0x72829`: `DeletedDate`
- `0x72834`: `DeletedDate`
- `0x7284c`: `DeletedDate`
- `0x72857`: `DeletedDateLocalFormatted`
- `0x72863`: `DeletedDateLocalFormatted`
- `0x7286e`: `DeletedDateLocalFormatted`
- `0x72886`: `DeletedDateLocalFormatted`
- `0x728cb`: `DirNamePath`
- `0x728d7`: `DirNamePath`
- `0x728e2`: `DirNamePath`
- `0x728fa`: `DirNamePath`
- `0x729ed`: `LeafNamePath`
- `0x729f9`: `LeafNamePath`
- `0x72a04`: `LeafNamePath`
- `0x72a1c`: `LeafNamePath`

## pseudocode

```c

```

## disassembly

```asm
0x72720  ldarg.2
0x72721  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem
0x72726  stloc.0
0x72727  ldloc.0
0x72728  brtrue.s loc_7272B
0x7272a  ret
0x7272b  ldarg.0
0x7272c  ldarg.1
0x7272d  ldarg.2
0x7272e  ldarg.3
0x7272f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72734  ldarg.0
0x72735  ldstr    aAuthoremail// "AuthorEmail"
0x7273a  ldarg.3
0x7273b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72740  ldarg.1
0x72741  ldstr    aAuthoremail// "AuthorEmail"
0x72746  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x7274b  ldarg.3
0x7274c  ldstr    aAuthoremail// "AuthorEmail"
0x72751  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x72756  ldarg.1
0x72757  ldloc.0
0x72758  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_AuthorEmail()
0x7275d  ldarg.3
0x7275e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72763  ldarg.3
0x72764  ldstr    aAuthoremail// "AuthorEmail"
0x72769  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x7276e  ldarg.0
0x7276f  ldstr    aAuthorname// "AuthorName"
0x72774  ldarg.3
0x72775  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7277a  ldarg.1
0x7277b  ldstr    aAuthorname// "AuthorName"
0x72780  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x72785  ldarg.3
0x72786  ldstr    aAuthorname// "AuthorName"
0x7278b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x72790  ldarg.1
0x72791  ldloc.0
0x72792  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_AuthorName()
0x72797  ldarg.3
0x72798  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7279d  ldarg.3
0x7279e  ldstr    aAuthorname// "AuthorName"
0x727a3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x727a8  ldarg.0
0x727a9  ldstr    aDeletedbyemail// "DeletedByEmail"
0x727ae  ldarg.3
0x727af  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x727b4  ldarg.1
0x727b5  ldstr    aDeletedbyemail// "DeletedByEmail"
0x727ba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x727bf  ldarg.3
0x727c0  ldstr    aDeletedbyemail// "DeletedByEmail"
0x727c5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x727ca  ldarg.1
0x727cb  ldloc.0
0x727cc  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_DeletedByEmail()
0x727d1  ldarg.3
0x727d2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x727d7  ldarg.3
0x727d8  ldstr    aDeletedbyemail// "DeletedByEmail"
0x727dd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x727e2  ldarg.0
0x727e3  ldstr    aDeletedbyname// "DeletedByName"
0x727e8  ldarg.3
0x727e9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x727ee  ldarg.1
0x727ef  ldstr    aDeletedbyname// "DeletedByName"
0x727f4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x727f9  ldarg.3
0x727fa  ldstr    aDeletedbyname// "DeletedByName"
0x727ff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x72804  ldarg.1
0x72805  ldloc.0
0x72806  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_DeletedByName()
0x7280b  ldarg.3
0x7280c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72811  ldarg.3
0x72812  ldstr    aDeletedbyname// "DeletedByName"
0x72817  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x7281c  ldarg.0
0x7281d  ldstr    aDeleteddate// "DeletedDate"
0x72822  ldarg.3
0x72823  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72828  ldarg.1
0x72829  ldstr    aDeleteddate// "DeletedDate"
0x7282e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x72833  ldarg.3
0x72834  ldstr    aDeleteddate// "DeletedDate"
0x72839  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x7283e  ldarg.1
0x7283f  ldloc.0
0x72840  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_DeletedDate()
0x72845  ldarg.3
0x72846  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7284b  ldarg.3
0x7284c  ldstr    aDeleteddate// "DeletedDate"
0x72851  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x72856  ldarg.0
0x72857  ldstr    aDeleteddateloc// "DeletedDateLocalFormatted"
0x7285c  ldarg.3
0x7285d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72862  ldarg.1
0x72863  ldstr    aDeleteddateloc// "DeletedDateLocalFormatted"
0x72868  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x7286d  ldarg.3
0x7286e  ldstr    aDeleteddateloc// "DeletedDateLocalFormatted"
0x72873  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x72878  ldarg.1
0x72879  ldloc.0
0x7287a  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_DeletedDateLocalFormatted()
0x7287f  ldarg.3
0x72880  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72885  ldarg.3
0x72886  ldstr    aDeleteddateloc// "DeletedDateLocalFormatted"
0x7288b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x72890  ldarg.0
0x72891  ldstr    aDirname// "DirName"
0x72896  ldarg.3
0x72897  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7289c  ldarg.1
0x7289d  ldstr    aDirname// "DirName"
0x728a2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x728a7  ldarg.3
0x728a8  ldstr    aDirname// "DirName"
0x728ad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x728b2  ldarg.1
0x728b3  ldloc.0
0x728b4  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_DirName()
0x728b9  ldarg.3
0x728ba  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x728bf  ldarg.3
0x728c0  ldstr    aDirname// "DirName"
0x728c5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x728ca  ldarg.0
0x728cb  ldstr    aDirnamepath// "DirNamePath"
0x728d0  ldarg.3
0x728d1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x728d6  ldarg.1
0x728d7  ldstr    aDirnamepath// "DirNamePath"
0x728dc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x728e1  ldarg.3
0x728e2  ldstr    aDirnamepath// "DirNamePath"
0x728e7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x728ec  ldarg.1
0x728ed  ldloc.0
0x728ee  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPResourcePath [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_DirNamePath()
0x728f3  ldarg.3
0x728f4  call     T0x2B000027
0x728f9  ldarg.3
0x728fa  ldstr    aDirnamepath// "DirNamePath"
0x728ff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x72904  ldarg.0
0x72905  ldstr    aId_0// "Id"
0x7290a  ldarg.3
0x7290b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72910  ldarg.1
0x72911  ldstr    aId_0// "Id"
0x72916  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x7291b  ldarg.3
0x7291c  ldstr    aId_0// "Id"
0x72921  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x72926  ldarg.1
0x72927  ldloc.0
0x72928  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_ID()
0x7292d  ldarg.3
0x7292e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72933  ldarg.3
0x72934  ldstr    aId_0// "Id"
0x72939  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x7293e  ldarg.0
0x7293f  ldstr    aItemstate// "ItemState"
0x72944  ldarg.3
0x72945  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7294a  ldarg.1
0x7294b  ldstr    aItemstate// "ItemState"
0x72950  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x72955  ldarg.3
0x72956  ldstr    aItemstate// "ItemState"
0x7295b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x72960  ldarg.1
0x72961  ldloc.0
0x72962  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItemState [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_ItemState()
0x72967  ldarg.3
0x72968  call     T0x2B0001E7
0x7296d  ldarg.3
0x7296e  ldstr    aItemstate// "ItemState"
0x72973  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x72978  ldarg.0
0x72979  ldstr    aItemtype// "ItemType"
0x7297e  ldarg.3
0x7297f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72984  ldarg.1
0x72985  ldstr    aItemtype// "ItemType"
0x7298a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x7298f  ldarg.3
0x72990  ldstr    aItemtype// "ItemType"
0x72995  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x7299a  ldarg.1
0x7299b  ldloc.0
0x7299c  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItemType [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_ItemType()
0x729a1  ldarg.3
0x729a2  call     T0x2B0001E8
0x729a7  ldarg.3
0x729a8  ldstr    aItemtype// "ItemType"
0x729ad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x729b2  ldarg.0
0x729b3  ldstr    aLeafname_0// "LeafName"
0x729b8  ldarg.3
0x729b9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x729be  ldarg.1
0x729bf  ldstr    aLeafname_0// "LeafName"
0x729c4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x729c9  ldarg.3
0x729ca  ldstr    aLeafname_0// "LeafName"
0x729cf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x729d4  ldarg.1
0x729d5  ldloc.0
0x729d6  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_LeafName()
0x729db  ldarg.3
0x729dc  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x729e1  ldarg.3
0x729e2  ldstr    aLeafname_0// "LeafName"
0x729e7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x729ec  ldarg.0
0x729ed  ldstr    aLeafnamepath// "LeafNamePath"
0x729f2  ldarg.3
0x729f3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x729f8  ldarg.1
0x729f9  ldstr    aLeafnamepath// "LeafNamePath"
0x729fe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x72a03  ldarg.3
0x72a04  ldstr    aLeafnamepath// "LeafNamePath"
0x72a09  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x72a0e  ldarg.1
0x72a0f  ldloc.0
0x72a10  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPResourcePath [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_LeafNamePath()
0x72a15  ldarg.3
0x72a16  call     T0x2B000027
0x72a1b  ldarg.3
0x72a1c  ldstr    aLeafnamepath// "LeafNamePath"
0x72a21  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x72a26  ldarg.0
0x72a27  ldstr    aSize_0// "Size"
0x72a2c  ldarg.3
0x72a2d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72a32  ldarg.1
0x72a33  ldstr    aSize_0// "Size"
0x72a38  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x72a3d  ldarg.3
0x72a3e  ldstr    aSize_0// "Size"
0x72a43  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x72a48  ldarg.1
0x72a49  ldloc.0
0x72a4a  callvirt instance int64 [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_Size()
0x72a4f  ldarg.3
0x72a50  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt64(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int64, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72a55  ldarg.3
0x72a56  ldstr    aSize_0// "Size"
0x72a5b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x72a60  ldarg.0
0x72a61  ldstr    aTitle// "Title"
0x72a66  ldarg.3
0x72a67  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72a6c  ldarg.1
0x72a6d  ldstr    aTitle// "Title"
0x72a72  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x72a77  ldarg.3
0x72a78  ldstr    aTitle// "Title"
0x72a7d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x72a82  ldarg.1
0x72a83  ldloc.0
0x72a84  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_Title()
0x72a89  ldarg.3
0x72a8a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72a8f  ldarg.3
0x72a90  ldstr    aTitle// "Title"
0x72a95  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x72a9a  ret
```
