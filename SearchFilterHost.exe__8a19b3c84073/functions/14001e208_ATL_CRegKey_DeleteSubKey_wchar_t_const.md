# ATL::CRegKey::DeleteSubKey(wchar_t const *)

- ea: `0x14001e208`
- end: `0x14001e2c7`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `191`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1400229bc`
- `0x140022e00`

## callees

- `0x14001e208`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001e237`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001e237`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001e264`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001e264`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001e24c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001e279`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001e24c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001e279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e2b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e2b5`

## string_xrefs

- `0x14001e230`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x14001e242`: `RegDeleteKeyExW`
- `0x14001e25d`: `advapi32.dll`
- `0x14001e26f`: `RegDeleteKeyW`

## pseudocode

```c
DWORD __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const wchar_t *a2)
{
  HMODULE ModuleHandleW; // rax
  HMODULE Library; // rax
  __int64 (__fastcall *v6)(_QWORD, const wchar_t *, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v8)(_QWORD, const wchar_t *); // rax

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
  v6 = (__int64 (__fastcall *)(_QWORD, const wchar_t *, _QWORD, _QWORD))*((_QWORD *)this + 1);
  if ( v6 )
    return v6(*(_QWORD *)this, a2, 0, 0);
  v8 = (__int64 (__fastcall *)(_QWORD, const wchar_t *))*((_QWORD *)this + 2);
  if ( v8 )
    return v8(*(_QWORD *)this, a2);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x14001e208  push    rdi
0x14001e20a  sub     rsp, 40h
0x14001e20e  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x14001e217  mov     [rsp+48h+arg_0], rbx
0x14001e21c  mov     rdi, rdx
0x14001e21f  mov     rbx, rcx
0x14001e222  cmp     qword ptr [rcx+8], 0
0x14001e227  jnz     short loc_14001E283
0x14001e229  cmp     qword ptr [rcx+10h], 0
0x14001e22e  jnz     short loc_14001E283
0x14001e230  lea     rcx, aApiMsWinCoreLo_2; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x14001e237  call    cs:__imp_GetModuleHandleW
0x14001e23d  test    rax, rax
0x14001e240  jz      short loc_14001E258
0x14001e242  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x14001e249  mov     rcx, rax; hModule
0x14001e24c  call    cs:__imp_GetProcAddress
0x14001e252  mov     [rbx+8], rax
0x14001e256  jmp     short loc_14001E283
0x14001e258  xor     r8d, r8d; dwFlags
0x14001e25b  xor     edx, edx; hFile
0x14001e25d  lea     rcx, LibFileName; "advapi32.dll"
0x14001e264  call    cs:__imp_LoadLibraryExW
0x14001e26a  test    rax, rax
0x14001e26d  jz      short loc_14001E283
0x14001e26f  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x14001e276  mov     rcx, rax; hModule
0x14001e279  call    cs:__imp_GetProcAddress
0x14001e27f  mov     [rbx+10h], rax
0x14001e283  mov     rax, [rbx+8]
0x14001e287  test    rax, rax
0x14001e28a  jz      short loc_14001E29F
0x14001e28c  xor     r9d, r9d
0x14001e28f  xor     r8d, r8d
0x14001e292  mov     rdx, rdi
0x14001e295  mov     rcx, [rbx]
0x14001e298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e29d  jmp     short loc_14001E2BC
0x14001e29f  mov     rax, [rbx+10h]
0x14001e2a3  test    rax, rax
0x14001e2a6  jz      short loc_14001E2B5
0x14001e2a8  mov     rdx, rdi
0x14001e2ab  mov     rcx, [rbx]
0x14001e2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e2b3  jmp     short loc_14001E2BC
0x14001e2b5  call    cs:__imp_GetLastError
0x14001e2bb  nop
0x14001e2bc  mov     rbx, [rsp+48h+arg_0]
0x14001e2c1  add     rsp, 40h
0x14001e2c5  pop     rdi
0x14001e2c6  retn
```
