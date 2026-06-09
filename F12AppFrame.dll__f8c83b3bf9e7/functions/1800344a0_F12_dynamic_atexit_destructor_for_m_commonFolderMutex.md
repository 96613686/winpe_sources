# F12::_dynamic_atexit_destructor_for__m_commonFolderMutex__

- ea: `0x1800344a0`
- end: `0x1800344ae`
- name: `F12::_dynamic_atexit_destructor_for__m_commonFolderMutex__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800344a7`

## pseudocode

```c
void F12::_dynamic_atexit_destructor_for__m_commonFolderMutex__()
{
  DeleteCriticalSection((LPCRITICAL_SECTION)&F12::m_commonFolderMutex);
}

```

## disassembly

```asm
0x1800344a0  lea     rcx, ?m_commonFolderMutex@F12@@3VCComAutoCriticalSection@ATL@@A; ATL::CComAutoCriticalSection F12::m_commonFolderMutex
0x1800344a7  jmp     cs:__imp_DeleteCriticalSection
```
