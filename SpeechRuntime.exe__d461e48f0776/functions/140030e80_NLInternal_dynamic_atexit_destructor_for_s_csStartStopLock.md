# NLInternal::_dynamic_atexit_destructor_for__s_csStartStopLock__

- ea: `0x140030e80`
- end: `0x140030e8e`
- name: `NLInternal::_dynamic_atexit_destructor_for__s_csStartStopLock__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140030e87`

## pseudocode

```c
void NLInternal::_dynamic_atexit_destructor_for__s_csStartStopLock__()
{
  DeleteCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x140030e80  lea     rcx, CriticalSection
0x140030e87  jmp     cs:__imp_DeleteCriticalSection
```
