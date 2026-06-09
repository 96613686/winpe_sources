# Microsoft.SharePoint.Client.DataConverter::WriteAsJsonArray

- ea: `0x11e80`
- end: `0x11ed1`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteAsJsonArray`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x11e80`
- `0x13030`
- `0x13210`
- `0x13410`

## string_xrefs

- `0x11e83`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x11e80  ldarg.0
0x11e81  brtrue.s loc_11E8E
0x11e83  ldstr    aWriter// "writer"
0x11e88  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11e8d  throw
0x11e8e  ldarg.1
0x11e8f  brtrue.s loc_11E98
0x11e91  ldarg.0
0x11e92  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x11e97  ret
0x11e98  ldarg.0
0x11e99  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0x11e9e  ldarg.1
0x11e9f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<mvar<u1>>::GetEnumerator()
0x11ea4  stloc.1
0x11ea5  br.s     loc_11EB6
0x11ea7  ldloc.1
0x11ea8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<mvar<u1>>::get_Current()
0x11ead  stloc.0
0x11eae  ldarg.0
0x11eaf  ldloc.0
0x11eb0  ldarg.2
0x11eb1  call     T0x2B000020
0x11eb6  ldloc.1
0x11eb7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11ebc  brtrue.s loc_11EA7
0x11ebe  leave.s  loc_11ECA
0x11ec0  ldloc.1
0x11ec1  brfalse.s loc_11EC9
0x11ec3  ldloc.1
0x11ec4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11ec9  endfinally
0x11eca  ldarg.0
0x11ecb  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x11ed0  ret
```
