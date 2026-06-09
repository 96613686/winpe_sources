# CEnhancedStorageFolder::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x180008880`
- end: `0x18000888d`
- name: `?CreateViewObject@CEnhancedStorageFolder@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `13`
- prototype: `__int64 __fastcall(CEnhancedStorageFolder *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CEnhancedStorageFolder::CreateViewObject(
        CEnhancedStorageFolder *this,
        HWND a2,
        const struct _GUID *a3,
        void **a4)
{
  *a4 = 0;
  return 2147500033LL;
}

```

## disassembly

```asm
0x180008880  mov     qword ptr [r9], 0
0x180008887  mov     eax, 80004001h
0x18000888c  retn
```
