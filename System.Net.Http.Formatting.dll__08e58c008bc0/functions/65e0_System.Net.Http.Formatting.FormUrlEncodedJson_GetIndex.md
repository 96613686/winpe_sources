# System.Net.Http.Formatting.FormUrlEncodedJson::GetIndex

- ea: `0x65e0`
- end: `0x665a`
- name: `System.Net.Http.Formatting.FormUrlEncodedJson::GetIndex`
- size: `122`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6460`
- `0x6580`

## callees

- `0x3390`
- `0x65e0`
- `0xb330`

## pseudocode

```c

```

## disassembly

```asm
0x65e0  ldc.i4.m1
0x65e1  stloc.0
0x65e2  ldarg.0
0x65e3  callvirt instance int32 [Newtonsoft.Json]Newtonsoft.Json.Linq.JContainer::get_Count()
0x65e8  ldc.i4.0
0x65e9  ble.s    loc_6646
0x65eb  ldarg.0
0x65ec  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken>::get_Keys()
0x65f1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x65f6  stloc.1
0x65f7  br.s     loc_6632
0x65f9  ldloc.1
0x65fa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x65ff  stloc.2
0x6600  ldloc.2
0x6601  ldc.i4.7
0x6602  call     class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.NumberFormatInfo::get_InvariantInfo()
0x6607  ldloca.s 3
0x6609  call     bool [mscorlib]System.Int32::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int32&)
0x660e  brfalse.s loc_6618
0x6610  ldloc.3
0x6611  ldloc.0
0x6612  ble.s    loc_6618
0x6614  ldloc.3
0x6615  stloc.0
0x6616  br.s     loc_6632
0x6618  ldarg.1
0x6619  brfalse.s loc_662D
0x661b  call     string System.Net.Http.Properties.Resources::get_FormUrlEncodedMismatchingTypes()
0x6620  ldloc.2
0x6621  ldc.i4.0
0x6622  newarr   [mscorlib]System.Object
0x6627  call     class [mscorlib]System.ArgumentException System.Web.Http.Error::Argument(string parameterName, string messageFormat, object[] messageArgs)
0x662c  throw
0x662d  ldnull
0x662e  stloc.s  4
0x6630  leave.s  loc_6657
0x6632  ldloc.1
0x6633  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6638  brtrue.s loc_65F9
0x663a  leave.s  loc_6646
0x663c  ldloc.1
0x663d  brfalse.s loc_6645
0x663f  ldloc.1
0x6640  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6645  endfinally
0x6646  ldloc.0
0x6647  ldc.i4.1
0x6648  add
0x6649  stloc.0
0x664a  ldloca.s 0
0x664c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6651  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x6656  ret
0x6657  ldloc.s  4
0x6659  ret
```
