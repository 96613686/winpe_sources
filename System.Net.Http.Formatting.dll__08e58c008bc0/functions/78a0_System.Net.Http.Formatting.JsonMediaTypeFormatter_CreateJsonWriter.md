# System.Net.Http.Formatting.JsonMediaTypeFormatter::CreateJsonWriter

- ea: `0x78a0`
- end: `0x78ee`
- name: `System.Net.Http.Formatting.JsonMediaTypeFormatter::CreateJsonWriter`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x7810`
- `0x78a0`
- `0xb3c0`

## string_xrefs

- `0x78b7`: `writeStream`

## pseudocode

```c

```

## disassembly

```asm
0x78a0  ldarg.1
0x78a1  ldnull
0x78a2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x78a7  brfalse.s loc_78B4
0x78a9  ldstr    aType// "type"
0x78ae  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x78b3  throw
0x78b4  ldarg.2
0x78b5  brtrue.s loc_78C2
0x78b7  ldstr    aWritestream// "writeStream"
0x78bc  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x78c1  throw
0x78c2  ldarg.3
0x78c3  brtrue.s loc_78D0
0x78c5  ldstr    aEffectiveencod// "effectiveEncoding"
0x78ca  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x78cf  throw
0x78d0  ldarg.2
0x78d1  ldarg.3
0x78d2  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(class [mscorlib]System.IO.Stream, class [mscorlib]System.Text.Encoding)
0x78d7  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x78dc  stloc.0
0x78dd  ldarg.0
0x78de  call     instance bool System.Net.Http.Formatting.JsonMediaTypeFormatter::get_Indent()
0x78e3  brfalse.s loc_78EC
0x78e5  ldloc.0
0x78e6  ldc.i4.1
0x78e7  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::set_Formatting(valuetype [Newtonsoft.Json]Newtonsoft.Json.Formatting)
0x78ec  ldloc.0
0x78ed  ret
```
