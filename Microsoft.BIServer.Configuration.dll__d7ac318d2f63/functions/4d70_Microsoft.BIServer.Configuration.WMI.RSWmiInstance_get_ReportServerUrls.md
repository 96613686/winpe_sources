# Microsoft.BIServer.Configuration.WMI.RSWmiInstance::get_ReportServerUrls

- ea: `0x4d70`
- end: `0x4e1f`
- name: `Microsoft.BIServer.Configuration.WMI.RSWmiInstance::get_ReportServerUrls`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x4d70`

## string_xrefs

- `0x4dea`: `ReportServerWebService`

## pseudocode

```c

```

## disassembly

```asm
0x4d70  newobj   instance void [System.Management]System.Management.InvokeMethodOptions::.ctor()
0x4d75  stloc.0
0x4d76  ldloc.0
0x4d77  ldc.i4.0
0x4d78  ldc.i4.0
0x4d79  ldc.i4.s 0xA
0x4d7b  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x4d80  callvirt instance void [System.Management]System.Management.ManagementOptions::set_Timeout(valuetype [mscorlib]System.TimeSpan)
0x4d85  ldarg.0
0x4d86  ldfld    class [System.Management]System.Management.ManagementObject Microsoft.BIServer.Configuration.WMI.RSWmiInstance::_internalObject
0x4d8b  ldstr    aGetreportserve// "GetReportServerUrls"
0x4d90  callvirt instance class [System.Management]System.Management.ManagementBaseObject [System.Management]System.Management.ManagementObject::GetMethodParameters(string)
0x4d95  stloc.1
0x4d96  ldarg.0
0x4d97  ldfld    class [System.Management]System.Management.ManagementObject Microsoft.BIServer.Configuration.WMI.RSWmiInstance::_internalObject
0x4d9c  ldstr    aGetreportserve// "GetReportServerUrls"
0x4da1  ldloc.1
0x4da2  ldloc.0
0x4da3  callvirt instance class [System.Management]System.Management.ManagementBaseObject [System.Management]System.Management.ManagementObject::InvokeMethod(string, class [System.Management]System.Management.ManagementBaseObject, class [System.Management]System.Management.InvokeMethodOptions)
0x4da8  stloc.2
0x4da9  ldloc.2
0x4daa  ldstr    aHresult// "HRESULT"
0x4daf  callvirt instance object [System.Management]System.Management.ManagementBaseObject::get_Item(string)
0x4db4  unbox.any [mscorlib]System.Int32
0x4db9  brtrue.s loc_4E1D
0x4dbb  ldloc.2
0x4dbc  ldstr    aApplicationnam// "ApplicationName"
0x4dc1  callvirt instance object [System.Management]System.Management.ManagementBaseObject::get_Item(string)
0x4dc6  castclass string[]
0x4dcb  stloc.3
0x4dcc  ldloc.2
0x4dcd  ldstr    aUrls// "URLs"
0x4dd2  callvirt instance object [System.Management]System.Management.ManagementBaseObject::get_Item(string)
0x4dd7  castclass string[]
0x4ddc  stloc.s  4
0x4dde  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x4de3  stloc.s  5
0x4de5  ldc.i4.0
0x4de6  stloc.s  6
0x4de8  br.s     loc_4E0D
0x4dea  ldstr    aReportserverwe// "ReportServerWebService"
0x4def  ldloc.3
0x4df0  ldloc.s  6
0x4df2  ldelem.ref
0x4df3  ldc.i4.5
0x4df4  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x4df9  brfalse.s loc_4E07
0x4dfb  ldloc.s  5
0x4dfd  ldloc.s  4
0x4dff  ldloc.s  6
0x4e01  ldelem.ref
0x4e02  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x4e07  ldloc.s  6
0x4e09  ldc.i4.1
0x4e0a  add
0x4e0b  stloc.s  6
0x4e0d  ldloc.s  6
0x4e0f  ldloc.s  4
0x4e11  ldlen
0x4e12  conv.i4
0x4e13  blt.s    loc_4DEA
0x4e15  ldloc.s  5
0x4e17  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x4e1c  ret
0x4e1d  ldnull
0x4e1e  ret
```
