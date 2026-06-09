# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180007c50`
- end: `0x180007d05`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180009804`
- `0x180009cc4`
- `0x18000d4f0`

## callees

- `0x180007c50`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007ca2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007ca2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007c75`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007c75`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007c8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007cb7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007c8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007cb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007cf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007cf3`

## string_xrefs

- `0x180007c6e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180007c80`: `RegDeleteKeyExW`
- `0x180007c9b`: `advapi32.dll`
- `0x180007cad`: `RegDeleteKeyW`

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
0x180007c50  mov     [rsp+arg_0], rbx
0x180007c55  push    rdi
0x180007c56  sub     rsp, 30h
0x180007c5a  mov     rdi, rdx
0x180007c5d  mov     rbx, rcx
0x180007c60  cmp     qword ptr [rcx+8], 0
0x180007c65  jnz     short loc_180007CC1
0x180007c67  cmp     qword ptr [rcx+10h], 0
0x180007c6c  jnz     short loc_180007CC1
0x180007c6e  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180007c75  call    cs:__imp_GetModuleHandleW
0x180007c7b  test    rax, rax
0x180007c7e  jz      short loc_180007C96
0x180007c80  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180007c87  mov     rcx, rax; hModule
0x180007c8a  call    cs:__imp_GetProcAddress
0x180007c90  mov     [rbx+8], rax
0x180007c94  jmp     short loc_180007CC1
0x180007c96  xor     r8d, r8d; dwFlags
0x180007c99  xor     edx, edx; hFile
0x180007c9b  lea     rcx, LibFileName; "advapi32.dll"
0x180007ca2  call    cs:__imp_LoadLibraryExW
0x180007ca8  test    rax, rax
0x180007cab  jz      short loc_180007CC1
0x180007cad  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180007cb4  mov     rcx, rax; hModule
0x180007cb7  call    cs:__imp_GetProcAddress
0x180007cbd  mov     [rbx+10h], rax
0x180007cc1  mov     rax, [rbx+8]
0x180007cc5  test    rax, rax
0x180007cc8  jz      short loc_180007CDD
0x180007cca  xor     r9d, r9d
0x180007ccd  xor     r8d, r8d
0x180007cd0  mov     rdx, rdi
0x180007cd3  mov     rcx, [rbx]
0x180007cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cdb  jmp     short loc_180007CFA
0x180007cdd  mov     rax, [rbx+10h]
0x180007ce1  test    rax, rax
0x180007ce4  jz      short loc_180007CF3
0x180007ce6  mov     rdx, rdi
0x180007ce9  mov     rcx, [rbx]
0x180007cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cf1  jmp     short loc_180007CFA
0x180007cf3  call    cs:__imp_GetLastError
0x180007cf9  nop
0x180007cfa  mov     rbx, [rsp+38h+arg_0]
0x180007cff  add     rsp, 30h
0x180007d03  pop     rdi
0x180007d04  retn
```
