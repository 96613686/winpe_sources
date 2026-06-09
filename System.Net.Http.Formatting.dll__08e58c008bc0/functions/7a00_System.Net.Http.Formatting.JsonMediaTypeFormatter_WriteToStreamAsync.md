# System.Net.Http.Formatting.JsonMediaTypeFormatter::WriteToStreamAsync

- ea: `0x7a00`
- end: `0x7a60`
- name: `System.Net.Http.Formatting.JsonMediaTypeFormatter::WriteToStreamAsync`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x39f0`
- `0x57d0`
- `0x77f0`
- `0x7810`
- `0x7a00`
- `0xb3c0`
- `0xb4d0`

## string_xrefs

- `0x7a17`: `writeStream`

## pseudocode

```c

```

## disassembly

```asm
0x7a00  ldarg.1
0x7a01  ldnull
0x7a02  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x7a07  brfalse.s loc_7A14
0x7a09  ldstr    aType// "type"
0x7a0e  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x7a13  throw
0x7a14  ldarg.3
0x7a15  brtrue.s loc_7A22
0x7a17  ldstr    aWritestream// "writeStream"
0x7a1c  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x7a21  throw
0x7a22  ldarg.0
0x7a23  call     instance bool System.Net.Http.Formatting.JsonMediaTypeFormatter::get_UseDataContractJsonSerializer()
0x7a28  brfalse.s loc_7A50
0x7a2a  ldarg.0
0x7a2b  call     instance bool System.Net.Http.Formatting.JsonMediaTypeFormatter::get_Indent()
0x7a30  brfalse.s loc_7A50
0x7a32  call     string System.Net.Http.Properties.Resources::get_UnsupportedIndent()
0x7a37  ldc.i4.1
0x7a38  newarr   [mscorlib]System.Object
0x7a3d  dup
0x7a3e  ldc.i4.0
0x7a3f  ldtoken  [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer
0x7a44  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7a49  stelem.ref
0x7a4a  call     class [mscorlib]System.NotSupportedException System.Web.Http.Error::NotSupported(string messageFormat, object[] messageArgs)
0x7a4f  throw
0x7a50  ldarg.0
0x7a51  ldarg.1
0x7a52  ldarg.2
0x7a53  ldarg.3
0x7a54  ldarg.s  4
0x7a56  ldarg.s  5
0x7a58  ldarg.s  6
0x7a5a  call     instance class [mscorlib]System.Threading.Tasks.Task System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::WriteToStreamAsync(class [mscorlib]System.Type type, object value, class [mscorlib]System.IO.Stream writeStream, class [System.Net.Http]System.Net.Http.HttpContent content, class [System]System.Net.TransportContext transportContext, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x7a5f  ret
```
