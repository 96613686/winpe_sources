# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::FetchServiceSettingsIfNeeded

- ea: `0x668b0`
- end: `0x669c8`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::FetchServiceSettingsIfNeeded`
- size: `280`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x66860`
- `0x66880`

## callees

- `0x2acd0`
- `0x66630`
- `0x66690`
- `0x668b0`

## string_xrefs

- `0x66902`: `Fetching the taxonomy service setting for the service application proxy named {0}`
- `0x66935`: `IsServiceDataMapEnabled is set to {0}.`
- `0x66974`: `Completed fetching the taxonomy service setting from the service application proxy named {0}`

## pseudocode

```c

```

## disassembly

```asm
0x668b0  ldarg.0
0x668b1  ldfld    class [mscorlib]System.Threading.ReaderWriterLock Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::fetchServiceSettingsLock
0x668b6  ldc.i4   0x4E20
0x668bb  callvirt instance void [mscorlib]System.Threading.ReaderWriterLock::AcquireWriterLock(int32)
0x668c0  ldarg.0
0x668c1  ldfld    bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::settingsInitialized
0x668c6  brtrue   loc_669B9
0x668cb  ldarg.0
0x668cc  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::fetchServiceSettingsLastFailureStopwatch
0x668d1  brfalse.s loc_668F6
0x668d3  ldarg.0
0x668d4  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::fetchServiceSettingsLastFailureStopwatch
0x668d9  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x668de  ldc.i4   0x1388
0x668e3  conv.i8
0x668e4  bge.s    loc_668F6
0x668e6  ldstr    aErrortermstore_1// "ErrorTermStoreNotOnline"
0x668eb  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x668f0  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x668f5  throw
0x668f6  ldc.i4   0x64139D
0x668fb  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x66900  ldc.i4.s 0x32
0x66902  ldstr    aFetchingTheTax// "Fetching the taxonomy service setting f"...
0x66907  ldc.i4.1
0x66908  newarr   [mscorlib]System.Object
0x6690d  stloc.0
0x6690e  ldloc.0
0x6690f  ldc.i4.0
0x66910  ldarg.0
0x66911  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_DisplayName()
0x66916  stelem.ref
0x66917  ldloc.0
0x66918  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x6691d  ldarg.0
0x6691e  ldarg.0
0x6691f  call     instance bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::ReadIsServiceDataMapEnabled()
0x66924  stfld    bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::isServiceDataMapEnabled
0x66929  ldc.i4   0x64139E
0x6692e  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x66933  ldc.i4.s 0x32
0x66935  ldstr    aIsservicedatam// "IsServiceDataMapEnabled is set to {0}."
0x6693a  ldc.i4.1
0x6693b  newarr   [mscorlib]System.Object
0x66940  stloc.1
0x66941  ldloc.1
0x66942  ldc.i4.0
0x66943  ldarg.0
0x66944  ldfld    bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::isServiceDataMapEnabled
0x66949  box      [mscorlib]System.Boolean
0x6694e  stelem.ref
0x6694f  ldloc.1
0x66950  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x66955  ldarg.0
0x66956  ldarg.0
0x66957  call     instance class Microsoft.SharePoint.Taxonomy.PartitionSettings Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::ReadServiceApplicationSettings()
0x6695c  stfld    class Microsoft.SharePoint.Taxonomy.PartitionSettings Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::serviceApplicationSettings
0x66961  ldarg.0
0x66962  ldc.i4.1
0x66963  stfld    bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::settingsInitialized
0x66968  ldc.i4   0x64139F
0x6696d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x66972  ldc.i4.s 0x32
0x66974  ldstr    aCompletedFetch// "Completed fetching the taxonomy service"...
0x66979  ldc.i4.1
0x6697a  newarr   [mscorlib]System.Object
0x6697f  stloc.2
0x66980  ldloc.2
0x66981  ldc.i4.0
0x66982  ldarg.0
0x66983  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_DisplayName()
0x66988  stelem.ref
0x66989  ldloc.2
0x6698a  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x6698f  leave.s  loc_669B9
0x66991  ldarg.0
0x66992  ldfld    bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::settingsInitialized
0x66997  brfalse.s loc_669A2
0x66999  ldarg.0
0x6699a  ldnull
0x6699b  stfld    class [System]System.Diagnostics.Stopwatch Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::fetchServiceSettingsLastFailureStopwatch
0x669a0  br.s     loc_669B8
0x669a2  ldarg.0
0x669a3  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x669a8  stfld    class [System]System.Diagnostics.Stopwatch Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::fetchServiceSettingsLastFailureStopwatch
0x669ad  ldarg.0
0x669ae  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::fetchServiceSettingsLastFailureStopwatch
0x669b3  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x669b8  endfinally
0x669b9  leave.s  loc_669C7
0x669bb  ldarg.0
0x669bc  ldfld    class [mscorlib]System.Threading.ReaderWriterLock Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::fetchServiceSettingsLock
0x669c1  callvirt instance void [mscorlib]System.Threading.ReaderWriterLock::ReleaseWriterLock()
0x669c6  endfinally
0x669c7  ret
```
