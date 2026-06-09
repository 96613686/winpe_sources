# _dynamic_atexit_destructor_for___AUTO_INIT_g_csPendingState__

- ea: `0x140011360`
- end: `0x14001136e`
- name: `_dynamic_atexit_destructor_for___AUTO_INIT_g_csPendingState__`
- size: `14`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140011367`

## pseudocode

```c
void dynamic_atexit_destructor_for___AUTO_INIT_g_csPendingState__()
{
  DeleteCriticalSection(&g_csPendingState);
}

```

## disassembly

```asm
0x140011360  lea     rcx, ?g_csPendingState@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csPendingState
0x140011367  jmp     cs:__imp_DeleteCriticalSection
```
