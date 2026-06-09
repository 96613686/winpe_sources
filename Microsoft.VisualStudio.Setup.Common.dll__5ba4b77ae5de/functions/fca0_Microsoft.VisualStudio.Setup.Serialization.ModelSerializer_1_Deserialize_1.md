# Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1::Deserialize_1

- ea: `0xfca0`
- end: `0xfd0b`
- name: `Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1::Deserialize_1`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xc1a0`

## string_xrefs

- `0xfca1`: `reader`

## pseudocode

```c

```

## disassembly

```asm
0xfca0  ldarg.1
0xfca1  ldstr    aReader// "reader"
0xfca6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xfcab  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::.ctor()
0xfcb0  dup
0xfcb1  ldarg.0
0xfcb2  ldc.i4.1
0xfcb3  call     instance class Microsoft.VisualStudio.Setup.Serialization.SetupContractResolver class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>>::GetContractResolver(bool)
0xfcb8  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_ContractResolver(class [Newtonsoft.Json]Newtonsoft.Json.Serialization.IContractResolver)
0xfcbd  dup
0xfcbe  ldc.i4.8
0xfcbf  ldarg.0
0xfcc0  callvirt instance class Microsoft.VisualStudio.Setup.Serialization.ModelContext class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>>::GetContext()
0xfcc5  newobj   instance void [mscorlib]System.Runtime.Serialization.StreamingContext::.ctor(valuetype [mscorlib]System.Runtime.Serialization.StreamingContextStates, object)
0xfcca  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_Context(valuetype [mscorlib]System.Runtime.Serialization.StreamingContext)
0xfccf  dup
0xfcd0  ldarg.0
0xfcd1  call     instance class [mscorlib]System.Collections.Generic.IList`1<class [Newtonsoft.Json]Newtonsoft.Json.JsonConverter> class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>>::get_Converters()
0xfcd6  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_Converters(class [mscorlib]System.Collections.Generic.IList`1<class [Newtonsoft.Json]Newtonsoft.Json.JsonConverter>)
0xfcdb  dup
0xfcdc  ldc.i4.1
0xfcdd  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_DateTimeZoneHandling(valuetype [Newtonsoft.Json]Newtonsoft.Json.DateTimeZoneHandling)
0xfce2  dup
0xfce3  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xfce8  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_EqualityComparer(class [mscorlib]System.Collections.IEqualityComparer)
0xfced  dup
0xfcee  ldarg.0
0xfcef  ldftn    instance void class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>>::<Deserialize>b__42_0(object, class [Newtonsoft.Json]Newtonsoft.Json.Serialization.ErrorEventArgs)
0xfcf5  newobj   instance void class [mscorlib]System.EventHandler`1<class [Newtonsoft.Json]Newtonsoft.Json.Serialization.ErrorEventArgs>::.ctor(object, native int)
0xfcfa  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_Error(class [mscorlib]System.EventHandler`1<class [Newtonsoft.Json]Newtonsoft.Json.Serialization.ErrorEventArgs>)
0xfcff  call     class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::CreateDefault(class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings)
0xfd04  ldarg.1
0xfd05  callvirt T0x2B000073
0xfd0a  ret
```
