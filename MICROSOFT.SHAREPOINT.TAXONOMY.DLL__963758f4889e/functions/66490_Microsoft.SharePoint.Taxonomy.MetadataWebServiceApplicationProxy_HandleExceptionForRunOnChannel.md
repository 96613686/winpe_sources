# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::HandleExceptionForRunOnChannel

- ea: `0x66490`
- end: `0x6662e`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::HandleExceptionForRunOnChannel`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x760d0`

## callees

- `0x579b0`
- `0x66490`

## string_xrefs

- `0x6655b`: `AccessDeniedEx:`
- `0x6658f`: `AccessDeniedEx:`
- `0x6649c`: `Exception returned from back end service. {0}`
- `0x664d5`: `Metadata backend service request failed in a term store exception: `
- `0x66524`: `Metadata backend service request failed in a term store exception with error code: `
- `0x66573`: `Metadata backend service request failed in a authorized access exception: `
- `0x665c5`: `Retrying because the request failed due to an expired security token for a cached channel.  Error was {0}.`
- `0x665f9`: `Encountered an exception reusing a cached channel.  Error was {0}.`
- `0x66616`: `Metadata backend service request failed in an unknown exception: `

## pseudocode

```c

```

## disassembly

```asm
0x66490  ldc.i4   0x63613432
0x66495  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6649a  ldc.i4.s 0x32
0x6649c  ldstr    aExceptionRetur// "Exception returned from back end servic"...
0x664a1  ldc.i4.1
0x664a2  newarr   [mscorlib]System.Object
0x664a7  stloc.0
0x664a8  ldloc.0
0x664a9  ldc.i4.0
0x664aa  ldarg.0
0x664ab  callvirt instance string [mscorlib]System.Object::ToString()
0x664b0  stelem.ref
0x664b1  ldloc.0
0x664b2  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x664b7  ldarg.0
0x664b8  callvirt instance string [mscorlib]System.Exception::get_Message()
0x664bd  ldstr    aTermstoreex// "TermStoreEx:"
0x664c2  ldc.i4.4
0x664c3  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x664c8  brfalse.s loc_66506
0x664ca  ldarg.1
0x664cb  ldc.i4   0x50D41E
0x664d0  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x664d5  ldstr    aMetadataBacken_0// "Metadata backend service request failed"...
0x664da  ldarg.0
0x664db  callvirt instance string [mscorlib]System.Object::ToString()
0x664e0  call     string [mscorlib]System.String::Concat(string, string)
0x664e5  ldnull
0x664e6  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32, string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x664eb  ldarg.0
0x664ec  callvirt instance string [mscorlib]System.Exception::get_Message()
0x664f1  ldstr    aTermstoreex// "TermStoreEx:"
0x664f6  callvirt instance int32 [mscorlib]System.String::get_Length()
0x664fb  callvirt instance string [mscorlib]System.String::Substring(int32)
0x66500  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x66505  throw
0x66506  ldarg.0
0x66507  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6650c  ldstr    aTermstoreerror// "TermStoreErrorCodeEx:"
0x66511  ldc.i4.4
0x66512  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x66517  brfalse.s loc_66555
0x66519  ldarg.1
0x6651a  ldc.i4   0x50D41F
0x6651f  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x66524  ldstr    aMetadataBacken_1// "Metadata backend service request failed"...
0x66529  ldarg.0
0x6652a  callvirt instance string [mscorlib]System.Object::ToString()
0x6652f  call     string [mscorlib]System.String::Concat(string, string)
0x66534  ldnull
0x66535  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32, string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x6653a  ldarg.0
0x6653b  callvirt instance string [mscorlib]System.Exception::get_Message()
0x66540  ldstr    aTermstoreerror// "TermStoreErrorCodeEx:"
0x66545  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6654a  callvirt instance string [mscorlib]System.String::Substring(int32)
0x6654f  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x66554  throw
0x66555  ldarg.0
0x66556  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6655b  ldstr    aAccessdeniedex// "AccessDeniedEx:"
0x66560  ldc.i4.4
0x66561  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x66566  brfalse.s loc_665A4
0x66568  ldarg.1
0x66569  ldc.i4   0x50D420
0x6656e  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x66573  ldstr    aMetadataBacken_2// "Metadata backend service request failed"...
0x66578  ldarg.0
0x66579  callvirt instance string [mscorlib]System.Object::ToString()
0x6657e  call     string [mscorlib]System.String::Concat(string, string)
0x66583  ldnull
0x66584  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32, string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x66589  ldarg.0
0x6658a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6658f  ldstr    aAccessdeniedex// "AccessDeniedEx:"
0x66594  callvirt instance int32 [mscorlib]System.String::get_Length()
0x66599  callvirt instance string [mscorlib]System.String::Substring(int32)
0x6659e  newobj   instance void [mscorlib]System.UnauthorizedAccessException::.ctor(string)
0x665a3  throw
0x665a4  ldarg.2
0x665a5  brfalse.s loc_66615
0x665a7  ldtoken  [System.ServiceModel]System.ServiceModel.Security.MessageSecurityException
0x665ac  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x665b1  ldarg.0
0x665b2  callvirt instance bool [mscorlib]System.Type::IsInstanceOfType(object)
0x665b7  brfalse.s loc_665E1
0x665b9  ldc.i4   0x5D4707
0x665be  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x665c3  ldc.i4.s 0x32
0x665c5  ldstr    aRetryingBecaus// "Retrying because the request failed due"...
0x665ca  ldc.i4.1
0x665cb  newarr   [mscorlib]System.Object
0x665d0  stloc.1
0x665d1  ldloc.1
0x665d2  ldc.i4.0
0x665d3  ldarg.0
0x665d4  callvirt instance string [mscorlib]System.Object::ToString()
0x665d9  stelem.ref
0x665da  ldloc.1
0x665db  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x665e0  ret
0x665e1  ldc.i4   0x96
0x665e6  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x665eb  brtrue.s loc_66615
0x665ed  ldc.i4   0x666F3279
0x665f2  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x665f7  ldc.i4.s 0x32
0x665f9  ldstr    aEncounteredAnE// "Encountered an exception reusing a cach"...
0x665fe  ldc.i4.1
0x665ff  newarr   [mscorlib]System.Object
0x66604  stloc.2
0x66605  ldloc.2
0x66606  ldc.i4.0
0x66607  ldarg.0
0x66608  callvirt instance string [mscorlib]System.Object::ToString()
0x6660d  stelem.ref
0x6660e  ldloc.2
0x6660f  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x66614  ret
0x66615  ldarg.1
0x66616  ldstr    aMetadataBacken_3// "Metadata backend service request failed"...
0x6661b  ldarg.0
0x6661c  callvirt instance string [mscorlib]System.Object::ToString()
0x66621  call     string [mscorlib]System.String::Concat(string, string)
0x66626  ldnull
0x66627  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x6662c  ldarg.0
0x6662d  throw
```
