# _dynamic_atexit_destructor_for__g_ZTraceContext__

- ea: `0x180003c80`
- end: `0x180003c8e`
- name: `_dynamic_atexit_destructor_for__g_ZTraceContext__`
- size: `14`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003c87`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_ZTraceContext__()
{
  DeleteCriticalSection(&g_ZTraceContext);
}

```

## disassembly

```asm
0x180003c80  lea     rcx, ?g_ZTraceContext@@3VZTraceContext@@A; ZTraceContext g_ZTraceContext
0x180003c87  jmp     cs:__imp_DeleteCriticalSection
```
