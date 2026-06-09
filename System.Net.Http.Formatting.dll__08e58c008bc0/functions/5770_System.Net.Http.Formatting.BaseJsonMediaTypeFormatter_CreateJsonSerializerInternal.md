# System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::CreateJsonSerializerInternal

- ea: `0x5770`
- end: `0x57b2`
- name: `System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::CreateJsonSerializerInternal`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x5680`
- `0x5840`

## callees

- `0x3550`
- `0x3570`
- `0x5770`
- `0x57c0`
- `0xb4b0`
- `0xb4c0`

## string_xrefs

- `0x5788`: `CreateJsonSerializer`
- `0x57a4`: `CreateJsonSerializer`

## pseudocode

```c

```

## disassembly

```asm
0x5770  ldnull
0x5771  stloc.0
0x5772  ldarg.0
0x5773  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::CreateJsonSerializer()
0x5778  stloc.0
0x5779  leave.s  loc_5794
0x577b  call     string System.Net.Http.Properties.Resources::get_JsonSerializerFactoryThrew()
0x5780  ldc.i4.1
0x5781  newarr   [mscorlib]System.Object
0x5786  dup
0x5787  ldc.i4.0
0x5788  ldstr    aCreatejsonseri// "CreateJsonSerializer"
0x578d  stelem.ref
0x578e  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(class [mscorlib]System.Exception innerException, string messageFormat, object[] messageArgs)
0x5793  throw
0x5794  ldloc.0
0x5795  brtrue.s loc_57B0
0x5797  call     string System.Net.Http.Properties.Resources::get_JsonSerializerFactoryReturnedNull()
0x579c  ldc.i4.1
0x579d  newarr   [mscorlib]System.Object
0x57a2  dup
0x57a3  ldc.i4.0
0x57a4  ldstr    aCreatejsonseri// "CreateJsonSerializer"
0x57a9  stelem.ref
0x57aa  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(string messageFormat, object[] messageArgs)
0x57af  throw
0x57b0  ldloc.0
0x57b1  ret
```
