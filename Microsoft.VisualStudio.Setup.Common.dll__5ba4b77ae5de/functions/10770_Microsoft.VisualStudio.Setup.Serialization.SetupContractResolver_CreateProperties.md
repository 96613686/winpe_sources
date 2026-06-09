# Microsoft.VisualStudio.Setup.Serialization.SetupContractResolver::CreateProperties

- ea: `0x10770`
- end: `0x10852`
- name: `Microsoft.VisualStudio.Setup.Serialization.SetupContractResolver::CreateProperties`
- size: `226`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x10610`
- `0x10650`
- `0x10670`
- `0x10690`
- `0x10770`

## pseudocode

```c

```

## disassembly

```asm
0x10770  ldarg.0
0x10771  ldarg.1
0x10772  ldarg.2
0x10773  call     instance class [mscorlib]System.Collections.Generic.IList`1<class [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty> [Newtonsoft.Json]Newtonsoft.Json.Serialization.DefaultContractResolver::CreateProperties(class [mscorlib]System.Type, valuetype [Newtonsoft.Json]Newtonsoft.Json.MemberSerialization)
0x10778  stloc.0
0x10779  ldarg.0
0x1077a  call     instance valuetype Microsoft.VisualStudio.Setup.Serialization.SerializationContext Microsoft.VisualStudio.Setup.Serialization.SetupContractResolver::get_Context()
0x1077f  brtrue.s loc_1078C
0x10781  ldarg.0
0x10782  call     instance bool Microsoft.VisualStudio.Setup.Serialization.SetupContractResolver::get_IsExclusive()
0x10787  brfalse  loc_1081D
0x1078c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty>::.ctor()
0x10791  stloc.1
0x10792  ldloc.0
0x10793  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty>::GetEnumerator()
0x10798  stloc.2
0x10799  br.s     loc_107FE
0x1079b  ldloc.2
0x1079c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty>::get_Current()
0x107a1  stloc.3
0x107a2  ldloc.3
0x107a3  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Serialization.IAttributeProvider [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty::get_AttributeProvider()
0x107a8  dup
0x107a9  brtrue.s loc_107AF
0x107ab  pop
0x107ac  ldnull
0x107ad  br.s     loc_107C4
0x107af  ldtoken  Microsoft.VisualStudio.Setup.Serialization.SerializationContextAttribute
0x107b4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x107b9  ldc.i4.1
0x107ba  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [mscorlib]System.Attribute> [Newtonsoft.Json]Newtonsoft.Json.Serialization.IAttributeProvider::GetAttributes(class [mscorlib]System.Type, bool)
0x107bf  call     T0x2B000078
0x107c4  isinst   Microsoft.VisualStudio.Setup.Serialization.SerializationContextAttribute
0x107c9  stloc.s  4
0x107cb  ldloc.s  4
0x107cd  brtrue.s loc_107DE
0x107cf  ldarg.0
0x107d0  call     instance bool Microsoft.VisualStudio.Setup.Serialization.SetupContractResolver::get_IsExclusive()
0x107d5  brfalse.s loc_107DE
0x107d7  ldsfld   class Microsoft.VisualStudio.Setup.Serialization.SerializationContextAttribute Microsoft.VisualStudio.Setup.Serialization.SerializationContextAttribute::Default
0x107dc  stloc.s  4
0x107de  ldloc.s  4
0x107e0  brfalse.s loc_107FE
0x107e2  ldloc.s  4
0x107e4  ldarg.0
0x107e5  call     instance valuetype Microsoft.VisualStudio.Setup.Serialization.SerializationContext Microsoft.VisualStudio.Setup.Serialization.SetupContractResolver::get_Context()
0x107ea  ldarg.0
0x107eb  call     instance bool Microsoft.VisualStudio.Setup.Serialization.SetupContractResolver::get_IsExclusive()
0x107f0  callvirt instance bool Microsoft.VisualStudio.Setup.Serialization.SerializationContextAttribute::ShouldSerialize(valuetype Microsoft.VisualStudio.Setup.Serialization.SerializationContext context, bool exclusive)
0x107f5  brfalse.s loc_107FE
0x107f7  ldloc.1
0x107f8  ldloc.3
0x107f9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty>::Add(var<u1>)
0x107fe  ldloc.2
0x107ff  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x10804  brtrue.s loc_1079B
0x10806  leave.s  loc_10812
0x10808  ldloc.2
0x10809  brfalse.s loc_10811
0x1080b  ldloc.2
0x1080c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10811  endfinally
0x10812  ldloc.1
0x10813  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty>::get_Count()
0x10818  ldc.i4.0
0x10819  ble.s    loc_1081D
0x1081b  ldloc.1
0x1081c  stloc.0
0x1081d  ldarg.0
0x1081e  call     instance bool Microsoft.VisualStudio.Setup.Serialization.SetupContractResolver::get_Sort()
0x10823  brfalse.s loc_10850
0x10825  ldloc.0
0x10826  ldsfld   class [mscorlib]System.Func`2<class [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty, int32> <>c::<>9__14_0
0x1082b  dup
0x1082c  brtrue.s loc_10845
0x1082e  pop
0x1082f  ldsfld   class <>c <>c::<>9
0x10834  ldftn    instance int32 <>c::<CreateProperties>b__14_0(class [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty p)
0x1083a  newobj   instance void class [mscorlib]System.Func`2<class [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty, int32>::.ctor(object, native int)
0x1083f  dup
0x10840  stsfld   class [mscorlib]System.Func`2<class [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty, int32> <>c::<>9__14_0
0x10845  call     T0x2B000079
0x1084a  call     T0x2B00007A
0x1084f  stloc.0
0x10850  ldloc.0
0x10851  ret
```
