# System.Net.Http.Formatting.FormUrlEncodedJson::FixSingleContiguousArray

- ea: `0x6720`
- end: `0x678a`
- name: `System.Net.Http.Formatting.FormUrlEncodedJson::FixSingleContiguousArray`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6660`

## callees

- `0x6720`
- `0x6790`

## pseudocode

```c

```

## disassembly

```asm
0x6720  ldarg.0
0x6721  isinst   [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject
0x6726  stloc.0
0x6727  ldloc.0
0x6728  brfalse.s loc_6788
0x672a  ldloc.0
0x672b  callvirt instance int32 [Newtonsoft.Json]Newtonsoft.Json.Linq.JContainer::get_Count()
0x6730  ldc.i4.0
0x6731  ble.s    loc_6788
0x6733  ldloc.0
0x6734  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken>::get_Keys()
0x6739  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x673e  ldloca.s 1
0x6740  call     bool System.Net.Http.Formatting.FormUrlEncodedJson::CanBecomeArray(class [mscorlib]System.Collections.Generic.List`1<string> keys, [out] class [mscorlib]System.Collections.Generic.List`1<string>& sortedKeys)
0x6745  brfalse.s loc_6788
0x6747  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JArray::.ctor()
0x674c  stloc.2
0x674d  ldloc.1
0x674e  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x6753  stloc.3
0x6754  br.s     loc_676D
0x6756  ldloca.s 3
0x6758  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x675d  stloc.s  4
0x675f  ldloc.2
0x6760  ldloc.0
0x6761  ldloc.s  4
0x6763  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0x6768  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JArray::Add(class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken)
0x676d  ldloca.s 3
0x676f  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x6774  brtrue.s loc_6756
0x6776  leave.s  loc_6786
0x6778  ldloca.s 3
0x677a  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x6780  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6785  endfinally
0x6786  ldloc.2
0x6787  ret
0x6788  ldarg.0
0x6789  ret
```
