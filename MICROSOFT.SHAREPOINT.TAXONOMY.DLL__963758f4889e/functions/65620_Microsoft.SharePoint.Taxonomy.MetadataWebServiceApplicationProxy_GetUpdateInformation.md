# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::GetUpdateInformation

- ea: `0x65620`
- end: `0x6566e`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::GetUpdateInformation`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x10ae0`

## callees

- `0x242d0`
- `0x663a0`
- `0x66a00`
- `0x75c60`

## string_xrefs

- `0x65641`: `packageinfo.xml`
- `0x65635`: `temporaryFolder`
- `0x6565d`: `GetUpdateInformation`

## pseudocode

```c

```

## disassembly

```asm
0x65620  newobj   instance void <>c__DisplayClass16::.ctor()
0x65625  stloc.0
0x65626  ldloc.0
0x65627  ldarg.1
0x65628  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass16::rawPartitionId
0x6562d  ldloc.0
0x6562e  ldarg.2
0x6562f  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass16::lastUpdateTime
0x65634  ldarg.3
0x65635  ldstr    aTemporaryfolde// "temporaryFolder"
0x6563a  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNullOrEmpty(string value, string parameterName)
0x6563f  ldloc.0
0x65640  ldarg.3
0x65641  ldstr    aPackageinfoXml// "packageinfo.xml"
0x65646  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x6564b  stfld    string <>c__DisplayClass16::filePath
0x65650  ldarg.0
0x65651  ldloc.0
0x65652  ldftn    instance void <>c__DisplayClass16::<GetUpdateInformation>b__15(class Microsoft.SharePoint.Taxonomy.IMetadataWebServiceApplication serviceApplication)
0x65658  newobj   instance void CodeToRun::.ctor(object object, native int method)
0x6565d  ldstr    aGetupdateinfor// "GetUpdateInformation"
0x65662  call     instance void Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::RunOnChannel(class CodeToRun codeToRun, string operationName)
0x65667  ldloc.0
0x65668  ldfld    string <>c__DisplayClass16::filePath
0x6566d  ret
```
