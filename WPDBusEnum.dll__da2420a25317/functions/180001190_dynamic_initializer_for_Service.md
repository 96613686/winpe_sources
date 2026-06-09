# _dynamic_initializer_for___Service__

- ea: `0x180001190`
- end: `0x18000119b`
- name: `_dynamic_initializer_for___Service__`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
void dynamic_initializer_for___Service__()
{
  g_RefCount = 0;
}

```

## disassembly

```asm
0x180001190  mov     cs:?g_RefCount@@3JA, 0; long g_RefCount
0x18000119a  retn
```
