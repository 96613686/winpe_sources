# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::UpdateParametersMapWithOnlyExistingParameters

- ea: `0x3c90`
- end: `0x3d0d`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::UpdateParametersMapWithOnlyExistingParameters`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xdf90`

## callees

- `0x3c90`

## string_xrefs

- `0x3cec`: `Invalid UploadDataModelParameters payload: Cannot update parameters that did not already exist from upload. The following Parameter Names are not already present: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x3c90  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x3c95  stloc.0
0x3c96  ldarg.2
0x3c97  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter>::GetEnumerator()
0x3c9c  stloc.1
0x3c9d  br.s     loc_3CCF
0x3c9f  ldloc.1
0x3ca0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter>::get_Current()
0x3ca5  stloc.2
0x3ca6  ldarg.1
0x3ca7  ldloc.2
0x3ca8  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter::get_Name()
0x3cad  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter>::ContainsKey(var<u1>)
0x3cb2  brtrue.s loc_3CC2
0x3cb4  ldloc.0
0x3cb5  ldloc.2
0x3cb6  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter::get_Name()
0x3cbb  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x3cc0  br.s     loc_3CCF
0x3cc2  ldarg.1
0x3cc3  ldloc.2
0x3cc4  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter::get_Name()
0x3cc9  ldloc.2
0x3cca  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter>::set_Item(var<u1>, !!T0)
0x3ccf  ldloc.1
0x3cd0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3cd5  brtrue.s loc_3C9F
0x3cd7  leave.s  loc_3CE3
0x3cd9  ldloc.1
0x3cda  brfalse.s loc_3CE2
0x3cdc  ldloc.1
0x3cdd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3ce2  endfinally
0x3ce3  ldloc.0
0x3ce4  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<string>::get_Count()
0x3ce9  ldc.i4.0
0x3cea  ble.s    loc_3D0C
0x3cec  ldstr    aInvalidUploadd// "Invalid UploadDataModelParameters paylo"...
0x3cf1  ldloc.0
0x3cf2  call     string [mscorlib]System.String::Format(string, object)
0x3cf7  stloc.3
0x3cf8  ldarg.0
0x3cf9  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::get_Logger()
0x3cfe  ldc.i4.1
0x3cff  ldloc.3
0x3d00  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x3d05  ldloc.3
0x3d06  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.InvalidDataModelParameterException::.ctor(string)
0x3d0b  throw
0x3d0c  ret
```
