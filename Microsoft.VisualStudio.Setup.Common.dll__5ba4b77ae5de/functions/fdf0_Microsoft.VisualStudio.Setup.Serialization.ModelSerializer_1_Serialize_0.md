# Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1::Serialize_0

- ea: `0xfdf0`
- end: `0xfec7`
- name: `Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1::Serialize_0`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0xc1a0`
- `0xfdf0`

## string_xrefs

- `0xfdf1`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xfdf0  ldarg.1
0xfdf1  ldstr    aWriter// "writer"
0xfdf6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xfdfb  ldarg.2
0xfdfc  box      var<u1>
0xfe01  ldstr    aObject// "object"
0xfe06  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xfe0b  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::.ctor()
0xfe10  dup
0xfe11  ldarg.0
0xfe12  ldc.i4.0
0xfe13  call     instance class Microsoft.VisualStudio.Setup.Serialization.SetupContractResolver class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>>::GetContractResolver(bool)
0xfe18  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_ContractResolver(class [Newtonsoft.Json]Newtonsoft.Json.Serialization.IContractResolver)
0xfe1d  dup
0xfe1e  ldc.i4.8
0xfe1f  ldarg.0
0xfe20  callvirt instance class Microsoft.VisualStudio.Setup.Serialization.ModelContext class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>>::GetContext()
0xfe25  newobj   instance void [mscorlib]System.Runtime.Serialization.StreamingContext::.ctor(valuetype [mscorlib]System.Runtime.Serialization.StreamingContextStates, object)
0xfe2a  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_Context(valuetype [mscorlib]System.Runtime.Serialization.StreamingContext)
0xfe2f  dup
0xfe30  ldarg.0
0xfe31  call     instance class [mscorlib]System.Collections.Generic.IList`1<class [Newtonsoft.Json]Newtonsoft.Json.JsonConverter> class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>>::get_Converters()
0xfe36  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_Converters(class [mscorlib]System.Collections.Generic.IList`1<class [Newtonsoft.Json]Newtonsoft.Json.JsonConverter>)
0xfe3b  dup
0xfe3c  ldc.i4.1
0xfe3d  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_DateTimeZoneHandling(valuetype [Newtonsoft.Json]Newtonsoft.Json.DateTimeZoneHandling)
0xfe42  dup
0xfe43  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xfe48  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_EqualityComparer(class [mscorlib]System.Collections.IEqualityComparer)
0xfe4d  dup
0xfe4e  ldarg.0
0xfe4f  ldftn    instance void class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>>::<Serialize>b__46_0(object, class [Newtonsoft.Json]Newtonsoft.Json.Serialization.ErrorEventArgs)
0xfe55  newobj   instance void class [mscorlib]System.EventHandler`1<class [Newtonsoft.Json]Newtonsoft.Json.Serialization.ErrorEventArgs>::.ctor(object, native int)
0xfe5a  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_Error(class [mscorlib]System.EventHandler`1<class [Newtonsoft.Json]Newtonsoft.Json.Serialization.ErrorEventArgs>)
0xfe5f  dup
0xfe60  ldarg.0
0xfe61  call     instance bool class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>>::get_Indent()
0xfe66  brtrue.s loc_FE6B
0xfe68  ldc.i4.0
0xfe69  br.s     loc_FE6C
0xfe6b  ldc.i4.1
0xfe6c  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_Formatting(valuetype [Newtonsoft.Json]Newtonsoft.Json.Formatting)
0xfe71  stloc.0
0xfe72  ldarg.1
0xfe73  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0xfe78  dup
0xfe79  ldc.i4.0
0xfe7a  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::set_CloseOutput(bool)
0xfe7f  dup
0xfe80  ldarg.0
0xfe81  call     instance int32 class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>>::get_Indentation()
0xfe86  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonTextWriter::set_Indentation(int32)
0xfe8b  dup
0xfe8c  ldc.i4.s 0x20
0xfe8e  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonTextWriter::set_IndentChar(char)
0xfe93  dup
0xfe94  ldarg.0
0xfe95  call     instance char class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>>::get_QuoteChar()
0xfe9a  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonTextWriter::set_QuoteChar(char)
0xfe9f  stloc.1
0xfea0  ldloc.1
0xfea1  stloc.2
0xfea2  ldloc.0
0xfea3  call     class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::CreateDefault(class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings)
0xfea8  ldloc.1
0xfea9  ldarg.2
0xfeaa  box      var<u1>
0xfeaf  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Serialize(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter, object)
0xfeb4  ldloc.1
0xfeb5  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::Flush()
0xfeba  leave.s  loc_FEC6
0xfebc  ldloc.2
0xfebd  brfalse.s loc_FEC5
0xfebf  ldloc.2
0xfec0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xfec5  endfinally
0xfec6  ret
```
