# _dynamic_atexit_destructor_for__CMapiUrl::s_userSidLock__

- ea: `0x18003e480`
- end: `0x18003e48e`
- name: `_dynamic_atexit_destructor_for__CMapiUrl::s_userSidLock__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003e487`

## pseudocode

```c
void dynamic_atexit_destructor_for__CMapiUrl::s_userSidLock__()
{
  DeleteCriticalSection((LPCRITICAL_SECTION)&CMapiUrl::s_userSidLock);
}

```

## disassembly

```asm
0x18003e480  lea     rcx, ?s_userSidLock@CMapiUrl@@0VCComAutoCriticalSection@ATL@@A; ATL::CComAutoCriticalSection CMapiUrl::s_userSidLock
0x18003e487  jmp     cs:__imp_DeleteCriticalSection
```
