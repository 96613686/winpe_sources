# ATL::CRegKey::DeleteSubKey(wchar_t const *)

- ea: `0x18000c2bc`
- end: `0x18000c371`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const wchar_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000bb08`
- `0x18000cbe8`
- `0x18000d0b8`

## callees

- `0x18000c2bc`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c2f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c323`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c2f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c323`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c2e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c2e1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c30e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c30e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c35f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c35f`

## string_xrefs

- `0x18000c2da`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000c2ec`: `RegDeleteKeyExW`
- `0x18000c307`: `advapi32.dll`
- `0x18000c319`: `RegDeleteKeyW`

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
0x18000c2bc  mov     [rsp+arg_0], rbx
0x18000c2c1  push    rdi
0x18000c2c2  sub     rsp, 30h
0x18000c2c6  mov     rdi, rdx
0x18000c2c9  mov     rbx, rcx
0x18000c2cc  cmp     qword ptr [rcx+8], 0
0x18000c2d1  jnz     short loc_18000C32D
0x18000c2d3  cmp     qword ptr [rcx+10h], 0
0x18000c2d8  jnz     short loc_18000C32D
0x18000c2da  lea     rcx, aApiMsWinCoreLo_2; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000c2e1  call    cs:__imp_GetModuleHandleW
0x18000c2e7  test    rax, rax
0x18000c2ea  jz      short loc_18000C302
0x18000c2ec  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18000c2f3  mov     rcx, rax; hModule
0x18000c2f6  call    cs:__imp_GetProcAddress
0x18000c2fc  mov     [rbx+8], rax
0x18000c300  jmp     short loc_18000C32D
0x18000c302  xor     r8d, r8d; dwFlags
0x18000c305  xor     edx, edx; hFile
0x18000c307  lea     rcx, LibFileName; "advapi32.dll"
0x18000c30e  call    cs:__imp_LoadLibraryExW
0x18000c314  test    rax, rax
0x18000c317  jz      short loc_18000C32D
0x18000c319  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000c320  mov     rcx, rax; hModule
0x18000c323  call    cs:__imp_GetProcAddress
0x18000c329  mov     [rbx+10h], rax
0x18000c32d  mov     rax, [rbx+8]
0x18000c331  test    rax, rax
0x18000c334  jz      short loc_18000C349
0x18000c336  xor     r9d, r9d
0x18000c339  xor     r8d, r8d
0x18000c33c  mov     rdx, rdi
0x18000c33f  mov     rcx, [rbx]
0x18000c342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c347  jmp     short loc_18000C366
0x18000c349  mov     rax, [rbx+10h]
0x18000c34d  test    rax, rax
0x18000c350  jz      short loc_18000C35F
0x18000c352  mov     rdx, rdi
0x18000c355  mov     rcx, [rbx]
0x18000c358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c35d  jmp     short loc_18000C366
0x18000c35f  call    cs:__imp_GetLastError
0x18000c365  nop
0x18000c366  mov     rbx, [rsp+38h+arg_0]
0x18000c36b  add     rsp, 30h
0x18000c36f  pop     rdi
0x18000c370  retn
```
