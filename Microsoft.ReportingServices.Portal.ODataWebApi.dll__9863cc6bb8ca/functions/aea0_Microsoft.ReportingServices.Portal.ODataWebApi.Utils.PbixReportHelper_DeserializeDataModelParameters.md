# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::DeserializeDataModelParameters

- ea: `0xaea0`
- end: `0xaf0e`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::DeserializeDataModelParameters`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xa670`
- `0xa900`

## callees

- `0xaea0`

## pseudocode

```c

```

## disassembly

```asm
0xaea0  ldarg.1
0xaea1  brtrue.s loc_AEAE
0xaea3  ldstr    aBodyjobj// "bodyJObj"
0xaea8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xaead  throw
0xaeae  ldarg.1
0xaeaf  brfalse.s loc_AEBE
0xaeb1  ldarg.1
0xaeb2  ldstr    aDatamodelparam// "DataModelParameters"
0xaeb7  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0xaebc  br.s     loc_AEBF
0xaebe  ldnull
0xaebf  stloc.0
0xaec0  ldloc.0
0xaec1  brfalse.s loc_AEDF
0xaec3  ldloc.0
0xaec4  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.Linq.JTokenType [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Type()
0xaec9  ldc.i4.s 0xA
0xaecb  beq.s    loc_AEDF
0xaecd  ldloc.0
0xaece  callvirt instance string [mscorlib]System.Object::ToString()
0xaed3  call     object [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::DeserializeObject(string)
0xaed8  castclass [Newtonsoft.Json]Newtonsoft.Json.Linq.JArray
0xaedd  br.s     loc_AEE4
0xaedf  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JArray::.ctor()
0xaee4  ldsfld   class [mscorlib]System.Func`2<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter> <>c::<>9__26_0
0xaee9  dup
0xaeea  brtrue.s loc_AF03
0xaeec  pop
0xaeed  ldsfld   class <>c <>c::<>9
0xaef2  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter <>c::<DeserializeDataModelParameters>b__26_0(class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken p)
0xaef8  newobj   instance void class [mscorlib]System.Func`2<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter>::.ctor(object, native int)
0xaefd  dup
0xaefe  stsfld   class [mscorlib]System.Func`2<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter> <>c::<>9__26_0
0xaf03  call     T0x2B0000EA
0xaf08  call     T0x2B0000EB
0xaf0d  ret
```
