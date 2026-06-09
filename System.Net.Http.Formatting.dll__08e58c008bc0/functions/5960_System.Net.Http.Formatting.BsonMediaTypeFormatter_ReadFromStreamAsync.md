# System.Net.Http.Formatting.BsonMediaTypeFormatter::ReadFromStreamAsync

- ea: `0x5960`
- end: `0x59d9`
- name: `System.Net.Http.Formatting.BsonMediaTypeFormatter::ReadFromStreamAsync`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x55d0`
- `0x5960`
- `0xb3c0`

## string_xrefs

- `0x5977`: `readStream`

## pseudocode

```c

```

## disassembly

```asm
0x5960  ldarg.1
0x5961  ldnull
0x5962  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x5967  brfalse.s loc_5974
0x5969  ldstr    aType// "type"
0x596e  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x5973  throw
0x5974  ldarg.2
0x5975  brtrue.s loc_5982
0x5977  ldstr    aReadstream// "readStream"
0x597c  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x5981  throw
0x5982  ldarg.1
0x5983  ldtoken  [mscorlib]System.DBNull
0x5988  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x598d  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x5992  brfalse.s loc_59CD
0x5994  ldarg.3
0x5995  brfalse.s loc_59CD
0x5997  ldarg.3
0x5998  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x599d  brfalse.s loc_59CD
0x599f  ldarg.3
0x59a0  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x59a5  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::get_ContentLength()
0x59aa  stloc.0
0x59ab  ldc.i4.0
0x59ac  conv.i8
0x59ad  stloc.1
0x59ae  ldloca.s 0
0x59b0  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::GetValueOrDefault()
0x59b5  ldloc.1
0x59b6  ceq
0x59b8  ldloca.s 0
0x59ba  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x59bf  and
0x59c0  brfalse.s loc_59CD
0x59c2  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x59c7  call     T0x2B000041
0x59cc  ret
0x59cd  ldarg.0
0x59ce  ldarg.1
0x59cf  ldarg.2
0x59d0  ldarg.3
0x59d1  ldarg.s  4
0x59d3  call     instance class [mscorlib]System.Threading.Tasks.Task`1<object> System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::ReadFromStreamAsync(class [mscorlib]System.Type type, class [mscorlib]System.IO.Stream readStream, class [System.Net.Http]System.Net.Http.HttpContent content, class System.Net.Http.Formatting.IFormatterLogger formatterLogger)
0x59d8  ret
```
