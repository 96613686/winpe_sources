# _WinSqmGetProc(char const *)

- ea: `0x1800f1e18`
- end: `0x1800f1e81`
- name: `?_WinSqmGetProc@@YAP6A_JXZPEBD@Z`
- size: `105`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004a558`
- `0x1800f1d64`

## callees

- `0x1800f1e18`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800f1e5a`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800f1e5a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800f1e6a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800f1e6a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1800f1e3f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1800f1e3f`

## string_xrefs

- `0x1800f1e38`: `Ntdll.dll`

## pseudocode

```c
FARPROC __fastcall _WinSqmGetProc(LPCSTR lpProcName)
{
  __int64 v1; // rbx
  HMODULE LibraryW; // rax

  v1 = 0;
  if ( dword_1801C4480 )
  {
    if ( hModule )
      return GetProcAddress(hModule, lpProcName);
    LibraryW = LoadLibraryW(L"Ntdll.dll");
    if ( LibraryW )
    {
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&hModule, (signed __int64)LibraryW, 0) )
        FreeLibrary(LibraryW);
      return GetProcAddress(hModule, lpProcName);
    }
  }
  return (FARPROC)v1;
}

```

## disassembly

```asm
0x1800f1e18  mov     [rsp+arg_0], rbx
0x1800f1e1d  push    rdi
0x1800f1e1e  sub     rsp, 20h
0x1800f1e22  xor     ebx, ebx
0x1800f1e24  mov     rdi, rcx
0x1800f1e27  cmp     cs:dword_1801C4480, ebx
0x1800f1e2d  jz      short loc_1800F1E73
0x1800f1e2f  cmp     cs:hModule, rbx
0x1800f1e36  jnz     short loc_1800F1E60
0x1800f1e38  lea     rcx, aNtdllDll; "Ntdll.dll"
0x1800f1e3f  call    cs:__imp_LoadLibraryW
0x1800f1e45  mov     rcx, rax; hLibModule
0x1800f1e48  test    rax, rax
0x1800f1e4b  jz      short loc_1800F1E73
0x1800f1e4d  xor     eax, eax
0x1800f1e4f  lock cmpxchg cs:hModule, rcx
0x1800f1e58  jz      short loc_1800F1E60
0x1800f1e5a  call    cs:__imp_FreeLibrary
0x1800f1e60  mov     rcx, cs:hModule; hModule
0x1800f1e67  mov     rdx, rdi; lpProcName
0x1800f1e6a  call    cs:__imp_GetProcAddress
0x1800f1e70  mov     rbx, rax
0x1800f1e73  mov     rax, rbx
0x1800f1e76  mov     rbx, [rsp+28h+arg_0]
0x1800f1e7b  add     rsp, 20h
0x1800f1e7f  pop     rdi
0x1800f1e80  retn
```
