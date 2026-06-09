# Microsoft.ManagementConsole.Internal.SynchronizationContextCache::RestoreOriginalContext

- ea: `0x81e0`
- end: `0x81eb`
- name: `Microsoft.ManagementConsole.Internal.SynchronizationContextCache::RestoreOriginalContext`
- size: `11`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x7f20`
- `0x7f60`
- `0x7fa0`
- `0x7fe0`
- `0x8020`
- `0x9ac0`
- `0x9af0`

## callees

- `0x81c0`

## pseudocode

```c

```

## disassembly

```asm
0x81e0  call     class [mscorlib]System.Threading.SynchronizationContext Microsoft.ManagementConsole.Internal.SynchronizationContextCache::get_OriginalContext()
0x81e5  call     void [mscorlib]System.Threading.SynchronizationContext::SetSynchronizationContext(class [mscorlib]System.Threading.SynchronizationContext)
0x81ea  ret
```
