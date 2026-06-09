# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180018998`
- end: `0x180018a4d`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18001833c`
- `0x180019058`
- `0x180019528`

## callees

- `0x180018998`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800189d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800189ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800189d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800189ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800189bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800189bd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800189ea`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800189ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a3b`

## string_xrefs

- `0x1800189b6`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800189c8`: `RegDeleteKeyExW`
- `0x1800189e3`: `advapi32.dll`
- `0x1800189f5`: `RegDeleteKeyW`

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
0x180018998  mov     [rsp+arg_0], rbx
0x18001899d  push    rdi
0x18001899e  sub     rsp, 30h
0x1800189a2  mov     rdi, rdx
0x1800189a5  mov     rbx, rcx
0x1800189a8  cmp     qword ptr [rcx+8], 0
0x1800189ad  jnz     short loc_180018A09
0x1800189af  cmp     qword ptr [rcx+10h], 0
0x1800189b4  jnz     short loc_180018A09
0x1800189b6  lea     rcx, aApiMsWinCoreLo_1; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800189bd  call    cs:__imp_GetModuleHandleW
0x1800189c3  test    rax, rax
0x1800189c6  jz      short loc_1800189DE
0x1800189c8  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1800189cf  mov     rcx, rax; hModule
0x1800189d2  call    cs:__imp_GetProcAddress
0x1800189d8  mov     [rbx+8], rax
0x1800189dc  jmp     short loc_180018A09
0x1800189de  xor     r8d, r8d; dwFlags
0x1800189e1  xor     edx, edx; hFile
0x1800189e3  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x1800189ea  call    cs:__imp_LoadLibraryExW
0x1800189f0  test    rax, rax
0x1800189f3  jz      short loc_180018A09
0x1800189f5  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800189fc  mov     rcx, rax; hModule
0x1800189ff  call    cs:__imp_GetProcAddress
0x180018a05  mov     [rbx+10h], rax
0x180018a09  mov     rax, [rbx+8]
0x180018a0d  test    rax, rax
0x180018a10  jz      short loc_180018A25
0x180018a12  xor     r9d, r9d
0x180018a15  xor     r8d, r8d
0x180018a18  mov     rdx, rdi
0x180018a1b  mov     rcx, [rbx]
0x180018a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a23  jmp     short loc_180018A42
0x180018a25  mov     rax, [rbx+10h]
0x180018a29  test    rax, rax
0x180018a2c  jz      short loc_180018A3B
0x180018a2e  mov     rdx, rdi
0x180018a31  mov     rcx, [rbx]
0x180018a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a39  jmp     short loc_180018A42
0x180018a3b  call    cs:__imp_GetLastError
0x180018a41  nop
0x180018a42  mov     rbx, [rsp+38h+arg_0]
0x180018a47  add     rsp, 30h
0x180018a4b  pop     rdi
0x180018a4c  retn
```
