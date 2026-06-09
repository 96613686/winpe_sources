# ATL::CRegKey::DeleteSubKey(wchar_t const *)

- ea: `0x18000b438`
- end: `0x18000b4f7`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `191`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000ad54`
- `0x180011ccc`

## callees

- `0x18000b438`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18000b494`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18000b494`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000b467`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000b467`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000b47c`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000b4a9`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000b47c`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000b4a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b4e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b4e5`

## string_xrefs

- `0x18000b460`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000b472`: `RegDeleteKeyExW`
- `0x18000b49f`: `RegDeleteKeyW`
- `0x18000b48d`: `advapi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000b438  push    rdi
0x18000b43a  sub     rsp, 40h
0x18000b43e  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000b447  mov     [rsp+48h+arg_0], rbx
0x18000b44c  mov     rdi, rdx
0x18000b44f  mov     rbx, rcx
0x18000b452  cmp     qword ptr [rcx+8], 0
0x18000b457  jnz     short loc_18000B4B3
0x18000b459  cmp     qword ptr [rcx+10h], 0
0x18000b45e  jnz     short loc_18000B4B3
0x18000b460  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000b467  call    cs:__imp_GetModuleHandleW
0x18000b46d  test    rax, rax
0x18000b470  jz      short loc_18000B488
0x18000b472  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18000b479  mov     rcx, rax; hModule
0x18000b47c  call    cs:__imp_GetProcAddress
0x18000b482  mov     [rbx+8], rax
0x18000b486  jmp     short loc_18000B4B3
0x18000b488  xor     r8d, r8d; dwFlags
0x18000b48b  xor     edx, edx; hFile
0x18000b48d  lea     rcx, LibFileName; "advapi32.dll"
0x18000b494  call    cs:__imp_LoadLibraryExW
0x18000b49a  test    rax, rax
0x18000b49d  jz      short loc_18000B4B3
0x18000b49f  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000b4a6  mov     rcx, rax; hModule
0x18000b4a9  call    cs:__imp_GetProcAddress
0x18000b4af  mov     [rbx+10h], rax
0x18000b4b3  mov     rax, [rbx+8]
0x18000b4b7  test    rax, rax
0x18000b4ba  jz      short loc_18000B4CF
0x18000b4bc  xor     r9d, r9d
0x18000b4bf  xor     r8d, r8d
0x18000b4c2  mov     rdx, rdi
0x18000b4c5  mov     rcx, [rbx]
0x18000b4c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4cd  jmp     short loc_18000B4EC
0x18000b4cf  mov     rax, [rbx+10h]
0x18000b4d3  test    rax, rax
0x18000b4d6  jz      short loc_18000B4E5
0x18000b4d8  mov     rdx, rdi
0x18000b4db  mov     rcx, [rbx]
0x18000b4de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4e3  jmp     short loc_18000B4EC
0x18000b4e5  call    cs:__imp_GetLastError
0x18000b4eb  nop
0x18000b4ec  mov     rbx, [rsp+48h+arg_0]
0x18000b4f1  add     rsp, 40h
0x18000b4f5  pop     rdi
0x18000b4f6  retn
```
