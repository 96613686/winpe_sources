# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180006dc0`
- end: `0x180006e75`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000863c`
- `0x180008afc`
- `0x18000afd0`

## callees

- `0x180006dc0`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006e12`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006e12`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006dfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006e27`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006dfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006e27`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006de5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006de5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e63`

## string_xrefs

- `0x180006dde`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180006df0`: `RegDeleteKeyExW`
- `0x180006e0b`: `advapi32.dll`
- `0x180006e1d`: `RegDeleteKeyW`

## pseudocode

```c
DWORD __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const unsigned __int16 *a2)
{
  HMODULE ModuleHandleW; // rax
  HMODULE Library; // rax
  __int64 (__fastcall *v6)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v8)(_QWORD, const unsigned __int16 *); // rax

  if ( *(_OWORD *)((char *)this + 8) == 0 )
  {
    ModuleHandleW = GetModuleHandleW(L"API-MS-Win-Core-LocalRegistry-L1-1-0.dll");
    if ( ModuleHandleW )
    {
      *((_QWORD *)this + 1) = GetProcAddress(ModuleHandleW, "RegDeleteKeyExW");
    }
    else
    {
      Library = LoadLibraryExW(L"advapi32.dll", 0, 0);
      if ( Library )
        *((_QWORD *)this + 2) = GetProcAddress(Library, "RegDeleteKeyW");
    }
  }
  v6 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD))*((_QWORD *)this + 1);
  if ( v6 )
    return v6(*(_QWORD *)this, a2, 0, 0);
  v8 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *))*((_QWORD *)this + 2);
  if ( v8 )
    return v8(*(_QWORD *)this, a2);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180006dc0  mov     [rsp+arg_0], rbx
0x180006dc5  push    rdi
0x180006dc6  sub     rsp, 30h
0x180006dca  mov     rdi, rdx
0x180006dcd  mov     rbx, rcx
0x180006dd0  cmp     qword ptr [rcx+8], 0
0x180006dd5  jnz     short loc_180006E31
0x180006dd7  cmp     qword ptr [rcx+10h], 0
0x180006ddc  jnz     short loc_180006E31
0x180006dde  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180006de5  call    cs:__imp_GetModuleHandleW
0x180006deb  test    rax, rax
0x180006dee  jz      short loc_180006E06
0x180006df0  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180006df7  mov     rcx, rax; hModule
0x180006dfa  call    cs:__imp_GetProcAddress
0x180006e00  mov     [rbx+8], rax
0x180006e04  jmp     short loc_180006E31
0x180006e06  xor     r8d, r8d; dwFlags
0x180006e09  xor     edx, edx; hFile
0x180006e0b  lea     rcx, LibFileName; "advapi32.dll"
0x180006e12  call    cs:__imp_LoadLibraryExW
0x180006e18  test    rax, rax
0x180006e1b  jz      short loc_180006E31
0x180006e1d  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180006e24  mov     rcx, rax; hModule
0x180006e27  call    cs:__imp_GetProcAddress
0x180006e2d  mov     [rbx+10h], rax
0x180006e31  mov     rax, [rbx+8]
0x180006e35  test    rax, rax
0x180006e38  jz      short loc_180006E4D
0x180006e3a  xor     r9d, r9d
0x180006e3d  xor     r8d, r8d
0x180006e40  mov     rdx, rdi
0x180006e43  mov     rcx, [rbx]
0x180006e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e4b  jmp     short loc_180006E6A
0x180006e4d  mov     rax, [rbx+10h]
0x180006e51  test    rax, rax
0x180006e54  jz      short loc_180006E63
0x180006e56  mov     rdx, rdi
0x180006e59  mov     rcx, [rbx]
0x180006e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e61  jmp     short loc_180006E6A
0x180006e63  call    cs:__imp_GetLastError
0x180006e69  nop
0x180006e6a  mov     rbx, [rsp+38h+arg_0]
0x180006e6f  add     rsp, 30h
0x180006e73  pop     rdi
0x180006e74  retn
```
