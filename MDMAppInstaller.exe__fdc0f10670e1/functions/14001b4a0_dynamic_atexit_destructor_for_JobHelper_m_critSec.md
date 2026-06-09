# _dynamic_atexit_destructor_for__JobHelper::m_critSec__

- ea: `0x14001b4a0`
- end: `0x14001b4ae`
- name: `_dynamic_atexit_destructor_for__JobHelper::m_critSec__`
- size: `14`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14001b4a7`

## pseudocode

```c
void dynamic_atexit_destructor_for__JobHelper::m_critSec__()
{
  DeleteCriticalSection(&JobHelper::m_critSec);
}

```

## disassembly

```asm
0x14001b4a0  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; ATL::CComAutoCriticalSection JobHelper::m_critSec
0x14001b4a7  jmp     cs:__imp_DeleteCriticalSection
```
