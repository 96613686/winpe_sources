# _dynamic_atexit_destructor_for__s_singletonRadioManagerLock__

- ea: `0x180026fb0`
- end: `0x180026fbe`
- name: `_dynamic_atexit_destructor_for__s_singletonRadioManagerLock__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026fb7`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_singletonRadioManagerLock__()
{
  DeleteCriticalSection(&s_singletonRadioManagerLock);
}

```

## disassembly

```asm
0x180026fb0  lea     rcx, ?s_singletonRadioManagerLock@@3Vcritical_section@wil@@A; wil::critical_section s_singletonRadioManagerLock
0x180026fb7  jmp     cs:__imp_DeleteCriticalSection
```
