# F12::_dynamic_atexit_destructor_for__m_hostHelperMutex__

- ea: `0x180034410`
- end: `0x18003441e`
- name: `F12::_dynamic_atexit_destructor_for__m_hostHelperMutex__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180034417`

## pseudocode

```c
void F12::_dynamic_atexit_destructor_for__m_hostHelperMutex__()
{
  DeleteCriticalSection((LPCRITICAL_SECTION)&F12::m_hostHelperMutex);
}

```

## disassembly

```asm
0x180034410  lea     rcx, ?m_hostHelperMutex@F12@@3VCComAutoCriticalSection@ATL@@A; ATL::CComAutoCriticalSection F12::m_hostHelperMutex
0x180034417  jmp     cs:__imp_DeleteCriticalSection
```
