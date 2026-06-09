# _dynamic_atexit_destructor_for__ErrorRecordStackCriticalSection__

- ea: `0x180032840`
- end: `0x18003284e`
- name: `_dynamic_atexit_destructor_for__ErrorRecordStackCriticalSection__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032847`

## pseudocode

```c
void dynamic_atexit_destructor_for__ErrorRecordStackCriticalSection__()
{
  DeleteCriticalSection(&stru_18004BDC0);
}

```

## disassembly

```asm
0x180032840  lea     rcx, stru_18004BDC0
0x180032847  jmp     cs:__imp_DeleteCriticalSection
```
