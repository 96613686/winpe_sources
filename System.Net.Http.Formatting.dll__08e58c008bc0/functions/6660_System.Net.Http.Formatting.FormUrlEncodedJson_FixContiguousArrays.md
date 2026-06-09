# System.Net.Http.Formatting.FormUrlEncodedJson::FixContiguousArrays

- ea: `0x6660`
- end: `0x6719`
- name: `System.Net.Http.Formatting.FormUrlEncodedJson::FixContiguousArrays`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6140`
- `0x6660`

## callees

- `0x6660`
- `0x6720`

## pseudocode

```c

```

## disassembly

```asm
0x6660  ldarg.0
0x6661  isinst   [Newtonsoft.Json]Newtonsoft.Json.Linq.JArray
0x6666  stloc.0
0x6667  ldloc.0
0x6668  brfalse.s loc_66A4
0x666a  ldc.i4.0
0x666b  stloc.1
0x666c  br.s     loc_669A
0x666e  ldloc.0
0x666f  ldloc.1
0x6670  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JArray::get_Item(int32)
0x6675  brfalse.s loc_6696
0x6677  ldloc.0
0x6678  ldloc.1
0x6679  ldloc.0
0x667a  ldloc.1
0x667b  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JArray::get_Item(int32)
0x6680  call     class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken System.Net.Http.Formatting.FormUrlEncodedJson::FixSingleContiguousArray(class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken original)
0x6685  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JArray::set_Item(int32, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken)
0x668a  ldloc.0
0x668b  ldloc.1
0x668c  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JArray::get_Item(int32)
0x6691  call     void System.Net.Http.Formatting.FormUrlEncodedJson::FixContiguousArrays(class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken jv)
0x6696  ldloc.1
0x6697  ldc.i4.1
0x6698  add
0x6699  stloc.1
0x669a  ldloc.1
0x669b  ldloc.0
0x669c  callvirt instance int32 [Newtonsoft.Json]Newtonsoft.Json.Linq.JContainer::get_Count()
0x66a1  blt.s    loc_666E
0x66a3  ret
0x66a4  ldarg.0
0x66a5  isinst   [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject
0x66aa  stloc.2
0x66ab  ldloc.2
0x66ac  brfalse.s loc_6718
0x66ae  ldloc.2
0x66af  callvirt instance int32 [Newtonsoft.Json]Newtonsoft.Json.Linq.JContainer::get_Count()
0x66b4  ldc.i4.0
0x66b5  ble.s    loc_6718
0x66b7  ldloc.2
0x66b8  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken>::get_Keys()
0x66bd  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x66c2  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x66c7  stloc.3
0x66c8  br.s     loc_66FF
0x66ca  ldloca.s 3
0x66cc  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x66d1  stloc.s  4
0x66d3  ldloc.2
0x66d4  ldloc.s  4
0x66d6  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0x66db  brfalse.s loc_66FF
0x66dd  ldloc.2
0x66de  ldloc.s  4
0x66e0  ldloc.2
0x66e1  ldloc.s  4
0x66e3  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0x66e8  call     class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken System.Net.Http.Formatting.FormUrlEncodedJson::FixSingleContiguousArray(class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken original)
0x66ed  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::set_Item(string, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken)
0x66f2  ldloc.2
0x66f3  ldloc.s  4
0x66f5  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0x66fa  call     void System.Net.Http.Formatting.FormUrlEncodedJson::FixContiguousArrays(class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken jv)
0x66ff  ldloca.s 3
0x6701  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x6706  brtrue.s loc_66CA
0x6708  leave.s  loc_6718
0x670a  ldloca.s 3
0x670c  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x6712  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6717  endfinally
0x6718  ret
```
