# Microsoft.SharePoint.Client.DataConverter::WriteList

- ea: `0x11a70`
- end: `0x11ac1`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteList`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x11a70`
- `0x13030`
- `0x13210`
- `0x13410`

## string_xrefs

- `0x11a73`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x11a70  ldarg.0
0x11a71  brtrue.s loc_11A7E
0x11a73  ldstr    aWriter// "writer"
0x11a78  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11a7d  throw
0x11a7e  ldarg.1
0x11a7f  brtrue.s loc_11A88
0x11a81  ldarg.0
0x11a82  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x11a87  ret
0x11a88  ldarg.0
0x11a89  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0x11a8e  ldarg.1
0x11a8f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<mvar<u1>>::GetEnumerator()
0x11a94  stloc.1
0x11a95  br.s     loc_11AA6
0x11a97  ldloc.1
0x11a98  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<mvar<u1>>::get_Current()
0x11a9d  stloc.0
0x11a9e  ldarg.0
0x11a9f  ldloc.0
0x11aa0  ldarg.2
0x11aa1  call     T0x2B000020
0x11aa6  ldloc.1
0x11aa7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11aac  brtrue.s loc_11A97
0x11aae  leave.s  loc_11ABA
0x11ab0  ldloc.1
0x11ab1  brfalse.s loc_11AB9
0x11ab3  ldloc.1
0x11ab4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11ab9  endfinally
0x11aba  ldarg.0
0x11abb  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x11ac0  ret
```
