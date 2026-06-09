# Microsoft.SharePoint.Client.DataConverter::WriteDictionary

- ea: `0x11680`
- end: `0x116f2`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteDictionary`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x11680`
- `0x13030`
- `0x13220`
- `0x132d0`
- `0x13410`

## string_xrefs

- `0x11683`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x11680  ldarg.0
0x11681  brtrue.s loc_1168E
0x11683  ldstr    aWriter// "writer"
0x11688  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1168d  throw
0x1168e  ldarg.1
0x1168f  brtrue.s loc_11698
0x11691  ldarg.0
0x11692  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x11697  ret
0x11698  ldarg.0
0x11699  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartObjectScope()
0x1169e  ldarg.1
0x1169f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, mvar<u1>>>::GetEnumerator()
0x116a4  stloc.1
0x116a5  br.s     loc_116D7
0x116a7  ldloc.1
0x116a8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, mvar<u1>>>::get_Current()
0x116ad  stloc.0
0x116ae  ldloca.s 0
0x116b0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, mvar<u1>>::get_Key()
0x116b5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x116ba  brtrue.s loc_116D7
0x116bc  ldarg.0
0x116bd  ldloca.s 0
0x116bf  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, mvar<u1>>::get_Key()
0x116c4  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteName(string name)
0x116c9  ldarg.0
0x116ca  ldloca.s 0
0x116cc  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, mvar<u1>>::get_Value()
0x116d1  ldarg.2
0x116d2  call     T0x2B000020
0x116d7  ldloc.1
0x116d8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x116dd  brtrue.s loc_116A7
0x116df  leave.s  loc_116EB
0x116e1  ldloc.1
0x116e2  brfalse.s loc_116EA
0x116e4  ldloc.1
0x116e5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x116ea  endfinally
0x116eb  ldarg.0
0x116ec  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x116f1  ret
```
