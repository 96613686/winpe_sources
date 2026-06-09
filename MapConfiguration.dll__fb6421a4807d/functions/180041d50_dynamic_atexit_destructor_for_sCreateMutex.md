# _dynamic_atexit_destructor_for__sCreateMutex__

- ea: `0x180041d50`
- end: `0x180041d5e`
- name: `_dynamic_atexit_destructor_for__sCreateMutex__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180041d57`

## pseudocode

```c
void dynamic_atexit_destructor_for__sCreateMutex__()
{
  DeleteCriticalSection(&stru_18007B7A0);
}

```

## disassembly

```asm
0x180041d50  lea     rcx, stru_18007B7A0
0x180041d57  jmp     cs:__imp_DeleteCriticalSection
```
