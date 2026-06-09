# System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::WriteToStream_0

- ea: `0x5840`
- end: `0x58a3`
- name: `System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::WriteToStream_0`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x5820`
- `0x5bb0`
- `0x7a60`

## callees

- `0x5770`
- `0x5840`
- `0x58b0`
- `0xb3c0`

## string_xrefs

- `0x5857`: `writeStream`

## pseudocode

```c

```

## disassembly

```asm
0x5840  ldarg.1
0x5841  ldnull
0x5842  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x5847  brfalse.s loc_5854
0x5849  ldstr    aType// "type"
0x584e  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x5853  throw
0x5854  ldarg.3
0x5855  brtrue.s loc_5862
0x5857  ldstr    aWritestream// "writeStream"
0x585c  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x5861  throw
0x5862  ldarg.s  4
0x5864  brtrue.s loc_5871
0x5866  ldstr    aEffectiveencod// "effectiveEncoding"
0x586b  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x5870  throw
0x5871  ldarg.0
0x5872  ldarg.1
0x5873  ldarg.3
0x5874  ldarg.s  4
0x5876  call     instance class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::CreateJsonWriterInternal(class [mscorlib]System.Type type, class [mscorlib]System.IO.Stream writeStream, class [mscorlib]System.Text.Encoding effectiveEncoding)
0x587b  stloc.0
0x587c  ldloc.0
0x587d  ldc.i4.0
0x587e  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::set_CloseOutput(bool)
0x5883  ldarg.0
0x5884  call     instance class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::CreateJsonSerializerInternal()
0x5889  ldloc.0
0x588a  ldarg.2
0x588b  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Serialize(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter, object)
0x5890  ldloc.0
0x5891  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::Flush()
0x5896  leave.s  loc_58A2
0x5898  ldloc.0
0x5899  brfalse.s loc_58A1
0x589b  ldloc.0
0x589c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x58a1  endfinally
0x58a2  ret
```
