# Microsoft.ManagementConsole.Internal.SynchronizationContextCache::get_OriginalContext

- ea: `0x81c0`
- end: `0x81d0`
- name: `Microsoft.ManagementConsole.Internal.SynchronizationContextCache::get_OriginalContext`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x81e0`

## pseudocode

```c

```

## disassembly

```asm
0x81c0  ldsfld   class [mscorlib]System.LocalDataStoreSlot Microsoft.ManagementConsole.Internal.SynchronizationContextCache::_syncContextSlot
0x81c5  call     object [mscorlib]System.Threading.Thread::GetData(class [mscorlib]System.LocalDataStoreSlot)
0x81ca  castclass [mscorlib]System.Threading.SynchronizationContext
0x81cf  ret
```
