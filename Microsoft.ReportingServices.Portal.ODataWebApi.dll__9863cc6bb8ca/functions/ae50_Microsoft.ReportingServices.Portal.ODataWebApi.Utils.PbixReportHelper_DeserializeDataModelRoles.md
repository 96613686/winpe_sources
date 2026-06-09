# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::DeserializeDataModelRoles

- ea: `0xae50`
- end: `0xae9b`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::DeserializeDataModelRoles`
- size: `75`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xa670`
- `0xa900`

## callees

- `0xae50`

## pseudocode

```c

```

## disassembly

```asm
0xae50  ldarg.2
0xae51  ldstr    aDatamodelroles// "DataModelRoles"
0xae56  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0xae5b  callvirt T0x2B0000E9
0xae60  stloc.0
0xae61  ldloc.0
0xae62  brfalse.s loc_AE9A
0xae64  ldloc.0
0xae65  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>::GetEnumerator()
0xae6a  stloc.1
0xae6b  br.s     loc_AE81
0xae6d  ldloca.s 1
0xae6f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>::get_Current()
0xae74  stloc.2
0xae75  ldarg.1
0xae76  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole> [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::get_DataModelRoles()
0xae7b  ldloc.2
0xae7c  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>::Add(var<u1>)
0xae81  ldloca.s 1
0xae83  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>::MoveNext()
0xae88  brtrue.s loc_AE6D
0xae8a  leave.s  loc_AE9A
0xae8c  ldloca.s 1
0xae8e  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>
0xae94  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xae99  endfinally
0xae9a  ret
```
