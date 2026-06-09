# BfspRestoreWinreObject

- ea: `0x1800528a8`
- end: `0x18005292f`
- name: `BfspRestoreWinreObject`
- size: `135`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18004d7e4`

## callees

- `0x1800528a8`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800528e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800528e5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180052911`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180052911`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800528c3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800528c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800528d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800528d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052906`

## string_xrefs

- `0x1800528db`: `WinRePostBCDRepair`
- `0x1800528b9`: `REAGENT.DLL`

## pseudocode

```c
__int64 __fastcall BfspRestoreWinreObject(__int64 a1, __int64 a2)
{
  HMODULE Library; // rax
  HMODULE v5; // rdi
  signed int LastError; // ebx
  FARPROC ProcAddress; // rax

  Library = LoadLibraryExW(L"REAGENT.DLL", 0, 0);
  v5 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "WinRePostBCDRepair");
    if ( ProcAddress )
    {
      LastError = 0;
      if ( !((unsigned int (__fastcall *)(__int64, __int64))ProcAddress)(a1, a2) )
        LastError = GetLastError();
    }
    else
    {
      LastError = 127;
    }
    FreeLibrary(v5);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0xC0070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800528a8  push    rbx
0x1800528aa  push    rbp
0x1800528ab  push    rsi
0x1800528ac  push    rdi
0x1800528ad  sub     rsp, 28h
0x1800528b1  mov     rsi, rdx
0x1800528b4  mov     rbp, rcx
0x1800528b7  xor     edx, edx; hFile
0x1800528b9  lea     rcx, aReagentDll; "REAGENT.DLL"
0x1800528c0  xor     r8d, r8d; dwFlags
0x1800528c3  call    cs:__imp_LoadLibraryExW
0x1800528c9  mov     rdi, rax
0x1800528cc  test    rax, rax
0x1800528cf  jnz     short loc_1800528DB
0x1800528d1  call    cs:__imp_GetLastError
0x1800528d7  mov     ebx, eax
0x1800528d9  jmp     short loc_180052917
0x1800528db  lea     rdx, aWinrepostbcdre; "WinRePostBCDRepair"
0x1800528e2  mov     rcx, rdi; hModule
0x1800528e5  call    cs:__imp_GetProcAddress
0x1800528eb  test    rax, rax
0x1800528ee  jnz     short loc_1800528F5
0x1800528f0  lea     ebx, [rax+7Fh]
0x1800528f3  jmp     short loc_18005290E
0x1800528f5  mov     rdx, rsi
0x1800528f8  mov     rcx, rbp
0x1800528fb  xor     ebx, ebx
0x1800528fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052902  test    eax, eax
0x180052904  jnz     short loc_18005290E
0x180052906  call    cs:__imp_GetLastError
0x18005290c  mov     ebx, eax
0x18005290e  mov     rcx, rdi; hLibModule
0x180052911  call    cs:__imp_FreeLibrary
0x180052917  test    ebx, ebx
0x180052919  jle     short loc_180052924
0x18005291b  movzx   ebx, bx
0x18005291e  or      ebx, 0C0070000h
0x180052924  mov     eax, ebx
0x180052926  add     rsp, 28h
0x18005292a  pop     rdi
0x18005292b  pop     rsi
0x18005292c  pop     rbp
0x18005292d  pop     rbx
0x18005292e  retn
```
