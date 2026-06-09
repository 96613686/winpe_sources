# _dynamic_atexit_destructor_for__s_ULogSynchronizer__

- ea: `0x14002af00`
- end: `0x14002af0e`
- name: `_dynamic_atexit_destructor_for__s_ULogSynchronizer__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14002af07`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_ULogSynchronizer__()
{
  DeleteCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x14002af00  lea     rcx, CriticalSection
0x14002af07  jmp     cs:__imp_DeleteCriticalSection
```
