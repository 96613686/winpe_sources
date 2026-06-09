# Microsoft.ManagementConsole.BaseCollection::OnSetComplete

- ea: `0x2e20`
- end: `0x2e50`
- name: `Microsoft.ManagementConsole.BaseCollection::OnSetComplete`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x2be0`
- `0x2bf0`

## pseudocode

```c

```

## disassembly

```asm
0x2e20  ldarg.0
0x2e21  ldarg.1
0x2e22  ldarg.2
0x2e23  ldarg.3
0x2e24  call     instance void [mscorlib]System.Collections.CollectionBase::OnSetComplete(int32, object, object)
0x2e29  ldarg.0
0x2e2a  ldarg.1
0x2e2b  ldc.i4.1
0x2e2c  newarr   [mscorlib]System.Object
0x2e31  stloc.0
0x2e32  ldloc.0
0x2e33  ldc.i4.0
0x2e34  ldarg.2
0x2e35  stelem.ref
0x2e36  ldloc.0
0x2e37  callvirt instance void Microsoft.ManagementConsole.BaseCollection::OnItemsRemoved(int32 index, object[] items)
0x2e3c  ldarg.0
0x2e3d  ldarg.1
0x2e3e  ldc.i4.1
0x2e3f  newarr   [mscorlib]System.Object
0x2e44  stloc.1
0x2e45  ldloc.1
0x2e46  ldc.i4.0
0x2e47  ldarg.3
0x2e48  stelem.ref
0x2e49  ldloc.1
0x2e4a  callvirt instance void Microsoft.ManagementConsole.BaseCollection::OnItemsAdded(int32 index, object[] items)
0x2e4f  ret
```
