# Microsoft.VisualStudio.Setup.Serialization.FeedParser`1::Parse_0

- ea: `0xf130`
- end: `0xf198`
- name: `Microsoft.VisualStudio.Setup.Serialization.FeedParser`1::Parse_0`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xc1a0`
- `0xf130`

## string_xrefs

- `0xf165`: `Failed to deserialize `

## pseudocode

```c

```

## disassembly

```asm
0xf130  ldarg.0
0xf131  ldstr    aSerializer// "serializer"
0xf136  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xf13b  ldarg.1
0xf13c  ldstr    aStream// "stream"
0xf141  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xf146  ldarg.1
0xf147  ldc.i4.0
0xf148  conv.i8
0xf149  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0xf14e  ldarg.1
0xf14f  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0xf154  stloc.0
0xf155  ldarg.0
0xf156  ldloc.0
0xf157  callvirt instance var<u1> class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>>::Deserialize(!!T0)
0xf15c  dup
0xf15d  box      var<u1>
0xf162  brtrue.s loc_F189
0xf164  pop
0xf165  ldstr    aFailedToDeseri// "Failed to deserialize "
0xf16a  ldtoken  var<u1>
0xf16f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf174  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xf179  ldstr    aFromStream// " from stream."
0xf17e  call     string [mscorlib]System.String::Concat(string, string, string)
0xf183  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializationException::.ctor(string)
0xf188  throw
0xf189  stloc.1
0xf18a  leave.s  loc_F196
0xf18c  ldloc.0
0xf18d  brfalse.s loc_F195
0xf18f  ldloc.0
0xf190  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf195  endfinally
0xf196  ldloc.1
0xf197  ret
```
