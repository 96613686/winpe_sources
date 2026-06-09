# _dynamic_atexit_destructor_for___AUTO_INIT_g_csEnvironment__

- ea: `0x140011340`
- end: `0x14001134e`
- name: `_dynamic_atexit_destructor_for___AUTO_INIT_g_csEnvironment__`
- size: `14`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140011347`

## pseudocode

```c
void dynamic_atexit_destructor_for___AUTO_INIT_g_csEnvironment__()
{
  DeleteCriticalSection(&g_csEnvironment);
}

```

## disassembly

```asm
0x140011340  lea     rcx, ?g_csEnvironment@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csEnvironment
0x140011347  jmp     cs:__imp_DeleteCriticalSection
```
