# Microsoft.ManagementConsole.BaseCollection::OnRemove

- ea: `0x2dc0`
- end: `0x2dd1`
- name: `Microsoft.ManagementConsole.BaseCollection::OnRemove`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2e60`

## pseudocode

```c

```

## disassembly

```asm
0x2dc0  ldarg.0
0x2dc1  ldarg.2
0x2dc2  ldc.i4.0
0x2dc3  callvirt instance void Microsoft.ManagementConsole.BaseCollection::OnValidate(object objectToValidate, bool testForDuplicate)
0x2dc8  ldarg.0
0x2dc9  ldarg.1
0x2dca  ldarg.2
0x2dcb  call     instance void [mscorlib]System.Collections.CollectionBase::OnRemove(int32, object)
0x2dd0  ret
```
