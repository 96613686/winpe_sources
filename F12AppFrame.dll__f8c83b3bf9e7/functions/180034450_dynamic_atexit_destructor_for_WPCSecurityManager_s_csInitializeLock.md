# _dynamic_atexit_destructor_for__WPCSecurityManager::s_csInitializeLock__

- ea: `0x180034450`
- end: `0x18003445e`
- name: `_dynamic_atexit_destructor_for__WPCSecurityManager::s_csInitializeLock__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180034457`

## pseudocode

```c
void dynamic_atexit_destructor_for__WPCSecurityManager::s_csInitializeLock__()
{
  DeleteCriticalSection((LPCRITICAL_SECTION)&WPCSecurityManager::s_csInitializeLock);
}

```

## disassembly

```asm
0x180034450  lea     rcx, ?s_csInitializeLock@WPCSecurityManager@@0VCComAutoCriticalSection@ATL@@A; ATL::CComAutoCriticalSection WPCSecurityManager::s_csInitializeLock
0x180034457  jmp     cs:__imp_DeleteCriticalSection
```
