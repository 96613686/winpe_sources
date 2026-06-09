# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::ReadIsServiceDataMapEnabled

- ea: `0x66630`
- end: `0x66684`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::ReadIsServiceDataMapEnabled`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x668b0`

## callees

- `0x663a0`
- `0x66630`
- `0x66a00`
- `0x76310`

## string_xrefs

- `0x66651`: `GetIsServiceDataMapEnabled`
- `0x6666a`: `Taxonomy Web Service Application does not implement the GetIsServiceDataMapEnabled() method`

## pseudocode

```c

```

## disassembly

```asm
0x66630  ldnull
0x66631  stloc.0
0x66632  newobj   instance void <>c__DisplayClass51::.ctor()
0x66637  stloc.1
0x66638  ldloc.1
0x66639  ldc.i4.0
0x6663a  stfld    bool <>c__DisplayClass51::isServiceDataMapEnabled
0x6663f  ldarg.0
0x66640  ldloc.0
0x66641  brtrue.s loc_66650
0x66643  ldloc.1
0x66644  ldftn    instance void <>c__DisplayClass51::<ReadIsServiceDataMapEnabled>b__4f(class Microsoft.SharePoint.Taxonomy.IMetadataWebServiceApplication serviceApplication)
0x6664a  newobj   instance void CodeToRun::.ctor(object object, native int method)
0x6664f  stloc.0
0x66650  ldloc.0
0x66651  ldstr    aGetisserviceda// "GetIsServiceDataMapEnabled"
0x66656  call     instance void Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::RunOnChannel(class CodeToRun codeToRun, string operationName)
0x6665b  leave.s  loc_6667D
0x6665d  pop
0x6665e  ldc.i4   0x64139C
0x66663  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x66668  ldc.i4.s 0xF
0x6666a  ldstr    aTaxonomyWebSer// "Taxonomy Web Service Application does n"...
0x6666f  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x66674  ldloc.1
0x66675  ldc.i4.0
0x66676  stfld    bool <>c__DisplayClass51::isServiceDataMapEnabled
0x6667b  leave.s  loc_6667D
0x6667d  ldloc.1
0x6667e  ldfld    bool <>c__DisplayClass51::isServiceDataMapEnabled
0x66683  ret
```
