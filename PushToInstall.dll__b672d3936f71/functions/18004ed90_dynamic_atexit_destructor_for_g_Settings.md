# _dynamic_atexit_destructor_for___g_Settings__

- ea: `0x18004ed90`
- end: `0x18004ed9e`
- name: `_dynamic_atexit_destructor_for___g_Settings__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004ed97`

## pseudocode

```c
void dynamic_atexit_destructor_for___g_Settings__()
{
  DeleteCriticalSection(&stru_180066640);
}

```

## disassembly

```asm
0x18004ed90  lea     rcx, stru_180066640
0x18004ed97  jmp     cs:__imp_DeleteCriticalSection
```
