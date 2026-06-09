# _dynamic_atexit_destructor_for__JobExecution::m_critSec__

- ea: `0x14001b390`
- end: `0x14001b39e`
- name: `_dynamic_atexit_destructor_for__JobExecution::m_critSec__`
- size: `14`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14001b397`

## pseudocode

```c
void dynamic_atexit_destructor_for__JobExecution::m_critSec__()
{
  DeleteCriticalSection(&JobExecution::m_critSec);
}

```

## disassembly

```asm
0x14001b390  lea     rcx, ?m_critSec@JobExecution@@0VCComAutoCriticalSection@ATL@@A; ATL::CComAutoCriticalSection JobExecution::m_critSec
0x14001b397  jmp     cs:__imp_DeleteCriticalSection
```
