# Microsoft.SharePoint.Client.Rest.ODataMessageWriterWrapper::WriteServiceDocument

- ea: `0x1d810`
- end: `0x1d867`
- name: `Microsoft.SharePoint.Client.Rest.ODataMessageWriterWrapper::WriteServiceDocument`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1d810`
- `0x294b0`

## string_xrefs

- `0x1d813`: `serviceDocument`

## pseudocode

```c

```

## disassembly

```asm
0x1d810  ldarg.1
0x1d811  brtrue.s loc_1D81E
0x1d813  ldstr    aServicedocumen// "serviceDocument"
0x1d818  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1d81d  throw
0x1d81e  newobj   instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataWorkspace::.ctor()
0x1d823  stloc.0
0x1d824  ldarg.1
0x1d825  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Client.RESTfulODataResourceInfo> Microsoft.SharePoint.Client.RESTfulODataServiceDocument::get_EntitySets()
0x1d82a  brfalse.s loc_1D85A
0x1d82c  ldloc.0
0x1d82d  ldarg.1
0x1d82e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Client.RESTfulODataResourceInfo> Microsoft.SharePoint.Client.RESTfulODataServiceDocument::get_EntitySets()
0x1d833  ldsfld   class [mscorlib]System.Func`2<class Microsoft.SharePoint.Client.RESTfulODataResourceInfo, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataResourceCollectionInfo> Microsoft.SharePoint.Client.Rest.ODataMessageWriterWrapper::CS$<>9__CachedAnonymousMethodDelegate2
0x1d838  brtrue.s loc_1D84B
0x1d83a  ldnull
0x1d83b  ldftn    class [Microsoft.Data.OData]Microsoft.Data.OData.ODataResourceCollectionInfo Microsoft.SharePoint.Client.Rest.ODataMessageWriterWrapper::<WriteServiceDocument>b__1(class Microsoft.SharePoint.Client.RESTfulODataResourceInfo feed)
0x1d841  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.SharePoint.Client.RESTfulODataResourceInfo, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataResourceCollectionInfo>::.ctor(object, native int)
0x1d846  stsfld   class [mscorlib]System.Func`2<class Microsoft.SharePoint.Client.RESTfulODataResourceInfo, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataResourceCollectionInfo> Microsoft.SharePoint.Client.Rest.ODataMessageWriterWrapper::CS$<>9__CachedAnonymousMethodDelegate2
0x1d84b  ldsfld   class [mscorlib]System.Func`2<class Microsoft.SharePoint.Client.RESTfulODataResourceInfo, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataResourceCollectionInfo> Microsoft.SharePoint.Client.Rest.ODataMessageWriterWrapper::CS$<>9__CachedAnonymousMethodDelegate2
0x1d850  call     T0x2B000037
0x1d855  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataWorkspace::set_Collections(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataResourceCollectionInfo>)
0x1d85a  ldarg.0
0x1d85b  ldfld    class [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageWriter Microsoft.SharePoint.Client.Rest.ODataMessageWriterWrapper::m_writer
0x1d860  ldloc.0
0x1d861  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageWriter::WriteServiceDocument(class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWorkspace)
0x1d866  ret
```
