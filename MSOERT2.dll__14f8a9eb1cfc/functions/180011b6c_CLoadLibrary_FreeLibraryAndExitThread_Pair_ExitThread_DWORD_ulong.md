# CLoadLibrary_FreeLibraryAndExitThread_Pair::ExitThread_DWORD(ulong)

- ea: `0x180011b6c`
- end: `0x180011b7a`
- name: `?ExitThread_DWORD@CLoadLibrary_FreeLibraryAndExitThread_Pair@@QEAAXK@Z`
- size: `14`
- prototype: `void __fastcall __noreturn(CLoadLibrary_FreeLibraryAndExitThread_Pair *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180006330`

## import_xrefs

- `KERNEL32!FreeLibraryAndExitThread` at `0x180011b73`
- `KERNEL32!FreeLibraryAndExitThread` at `0x180011b73`

## pseudocode

```c
void __fastcall __noreturn CLoadLibrary_FreeLibraryAndExitThread_Pair::ExitThread_DWORD(HMODULE *this, DWORD a2)
{
  FreeLibraryAndExitThread(*this, a2);
}

```

## disassembly

```asm
0x180011b6c  sub     rsp, 28h
0x180011b70  mov     rcx, [rcx]; hLibModule
0x180011b73  call    cs:__imp_FreeLibraryAndExitThread
```
