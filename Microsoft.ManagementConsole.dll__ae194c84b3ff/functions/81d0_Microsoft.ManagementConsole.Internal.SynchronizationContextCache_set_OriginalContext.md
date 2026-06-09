# Microsoft.ManagementConsole.Internal.SynchronizationContextCache::set_OriginalContext

- ea: `0x81d0`
- end: `0x81dc`
- name: `Microsoft.ManagementConsole.Internal.SynchronizationContextCache::set_OriginalContext`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x8230`

## pseudocode

```c

```

## disassembly

```asm
0x81d0  ldsfld   class [mscorlib]System.LocalDataStoreSlot Microsoft.ManagementConsole.Internal.SynchronizationContextCache::_syncContextSlot
0x81d5  ldarg.0
0x81d6  call     void [mscorlib]System.Threading.Thread::SetData(class [mscorlib]System.LocalDataStoreSlot, object)
0x81db  ret
```
