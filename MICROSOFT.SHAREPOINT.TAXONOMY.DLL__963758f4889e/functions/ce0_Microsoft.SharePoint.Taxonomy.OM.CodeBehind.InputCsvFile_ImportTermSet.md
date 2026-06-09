# Microsoft.SharePoint.Taxonomy.OM.CodeBehind.InputCsvFile::ImportTermSet

- ea: `0xce0`
- end: `0xe14`
- name: `Microsoft.SharePoint.Taxonomy.OM.CodeBehind.InputCsvFile::ImportTermSet`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0xbe0`

## callees

- `0xce0`
- `0x81b0`
- `0x2acd0`
- `0x4a250`
- `0x4a280`
- `0x4bad0`
- `0x4cc10`
- `0x545b0`

## string_xrefs

- `0xdbf`: `ErrorFailedToCreateTermSet`
- `0xdff`: `ErrorFailedToCreateTermSet`

## pseudocode

```c

```

## disassembly

```asm
0xce0  ldarg.0
0xce1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xce6  callvirt instance class [System.Web]System.Web.HttpFileCollection [System.Web]System.Web.HttpRequest::get_Files()
0xceb  stloc.0
0xcec  ldloc.0
0xced  callvirt instance int32 [System]System.Collections.Specialized.NameObjectCollectionBase::get_Count()
0xcf2  ldc.i4.0
0xcf3  ble      loc_E13
0xcf8  ldloc.0
0xcf9  ldc.i4.0
0xcfa  callvirt instance class [System.Web]System.Web.HttpPostedFile [System.Web]System.Web.HttpFileCollection::get_Item(int32)
0xcff  stloc.1
0xd00  ldloc.1
0xd01  callvirt instance string [System.Web]System.Web.HttpPostedFile::get_FileName()
0xd06  callvirt instance int32 [mscorlib]System.String::get_Length()
0xd0b  ldc.i4.0
0xd0c  ble      loc_E13
0xd11  ldloc.1
0xd12  callvirt instance int32 [System.Web]System.Web.HttpPostedFile::get_ContentLength()
0xd17  ldc.i4.0
0xd18  ble      loc_E13
0xd1d  ldarg.0
0xd1e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xd23  ldstr    aSspid// "sspId"
0xd28  call     T0x2B000002
0xd2d  stloc.s  0xB
0xd2f  ldloca.s 0xB
0xd31  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xd36  stloc.2
0xd37  ldarg.0
0xd38  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xd3d  ldstr    aGroupid// "groupId"
0xd42  call     T0x2B000002
0xd47  stloc.s  0xC
0xd49  ldloca.s 0xC
0xd4b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xd50  stloc.3
0xd51  ldnull
0xd52  stloc.s  4
0xd54  ldnull
0xd55  stloc.s  5
0xd57  ldsfld   string [mscorlib]System.String::Empty
0xd5c  stloc.s  6
0xd5e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0xd63  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0xd68  ldc.i4.1
0xd69  newobj   instance void Microsoft.SharePoint.Taxonomy.TaxonomySession::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, bool updateCache)
0xd6e  stloc.s  7
0xd70  ldloc.s  7
0xd72  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStoreCollection Microsoft.SharePoint.Taxonomy.TaxonomySession::get_TermStores()
0xd77  ldloc.2
0xd78  callvirt instance var<u1> class Microsoft.SharePoint.Taxonomy.Generic.IndexedCollection`1<class Microsoft.SharePoint.Taxonomy.TermStore>::get_Item(!!T0)
0xd7d  stloc.s  8
0xd7f  ldloc.s  8
0xd81  ldloc.3
0xd82  callvirt instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TermStore::GetGroup(valuetype [mscorlib]System.Guid id)
0xd87  stloc.s  9
0xd89  ldloc.s  8
0xd8b  newobj   instance void Microsoft.SharePoint.Taxonomy.ImportManager::.ctor(class Microsoft.SharePoint.Taxonomy.TermStore termStore)
0xd90  stloc.s  0xA
0xd92  ldloc.s  9
0xd94  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0xd99  ldloc.1
0xd9a  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpPostedFile::get_InputStream()
0xd9f  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0xda4  stloc.s  4
0xda6  ldloc.s  0xA
0xda8  ldloc.s  9
0xdaa  ldloc.s  4
0xdac  ldarg.0
0xdad  ldflda   bool Microsoft.SharePoint.Taxonomy.OM.CodeBehind.InputCsvFile::allTermsAdded
0xdb2  ldloca.s 6
0xdb4  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.ImportManager::ImportTermSet(class Microsoft.SharePoint.Taxonomy.Group parentGroup, class [mscorlib]System.IO.TextReader reader, [out] bool& allTermsAdded, [out] string& errorMessage)
0xdb9  stloc.s  5
0xdbb  leave.s  loc_DD5
0xdbd  pop
0xdbe  ldarg.0
0xdbf  ldstr    aErrorfailedtoc// "ErrorFailedToCreateTermSet"
0xdc4  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0xdc9  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPEncode::ScriptEncode(string)
0xdce  stfld    string Microsoft.SharePoint.Taxonomy.OM.CodeBehind.InputCsvFile::errorMessage
0xdd3  leave.s  loc_DD5
0xdd5  leave.s  loc_DE3
0xdd7  ldloc.s  4
0xdd9  brfalse.s loc_DE2
0xddb  ldloc.s  4
0xddd  callvirt instance void [mscorlib]System.IO.TextReader::Close()
0xde2  endfinally
0xde3  ldloc.s  6
0xde5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xdea  brtrue.s loc_DFA
0xdec  ldarg.0
0xded  ldloc.s  6
0xdef  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPEncode::ScriptEncode(string)
0xdf4  stfld    string Microsoft.SharePoint.Taxonomy.OM.CodeBehind.InputCsvFile::errorMessage
0xdf9  ret
0xdfa  ldloc.s  5
0xdfc  brtrue.s loc_E13
0xdfe  ldarg.0
0xdff  ldstr    aErrorfailedtoc// "ErrorFailedToCreateTermSet"
0xe04  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0xe09  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPEncode::ScriptEncode(string)
0xe0e  stfld    string Microsoft.SharePoint.Taxonomy.OM.CodeBehind.InputCsvFile::errorMessage
0xe13  ret
```
