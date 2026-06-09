# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x140003ca4`
- end: `0x140003d59`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1400034dc`
- `0x140004bd8`
- `0x140005098`

## callees

- `0x140003ca4`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003d47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003d47`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003cc9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003cc9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140003cf6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140003cf6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003cde`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003d0b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003cde`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003d0b`

## string_xrefs

- `0x140003cc2`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x140003cd4`: `RegDeleteKeyExW`
- `0x140003cef`: `advapi32.dll`
- `0x140003d01`: `RegDeleteKeyW`

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
0x140003ca4  mov     [rsp+arg_0], rbx
0x140003ca9  push    rdi
0x140003caa  sub     rsp, 30h
0x140003cae  mov     rdi, rdx
0x140003cb1  mov     rbx, rcx
0x140003cb4  cmp     qword ptr [rcx+8], 0
0x140003cb9  jnz     short loc_140003D15
0x140003cbb  cmp     qword ptr [rcx+10h], 0
0x140003cc0  jnz     short loc_140003D15
0x140003cc2  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x140003cc9  call    cs:__imp_GetModuleHandleW
0x140003ccf  test    rax, rax
0x140003cd2  jz      short loc_140003CEA
0x140003cd4  lea     rdx, ProcName; "RegDeleteKeyExW"
0x140003cdb  mov     rcx, rax; hModule
0x140003cde  call    cs:__imp_GetProcAddress
0x140003ce4  mov     [rbx+8], rax
0x140003ce8  jmp     short loc_140003D15
0x140003cea  xor     r8d, r8d; dwFlags
0x140003ced  xor     edx, edx; hFile
0x140003cef  lea     rcx, LibFileName; "advapi32.dll"
0x140003cf6  call    cs:__imp_LoadLibraryExW
0x140003cfc  test    rax, rax
0x140003cff  jz      short loc_140003D15
0x140003d01  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x140003d08  mov     rcx, rax; hModule
0x140003d0b  call    cs:__imp_GetProcAddress
0x140003d11  mov     [rbx+10h], rax
0x140003d15  mov     rax, [rbx+8]
0x140003d19  test    rax, rax
0x140003d1c  jz      short loc_140003D31
0x140003d1e  xor     r9d, r9d
0x140003d21  xor     r8d, r8d
0x140003d24  mov     rdx, rdi
0x140003d27  mov     rcx, [rbx]
0x140003d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d2f  jmp     short loc_140003D4E
0x140003d31  mov     rax, [rbx+10h]
0x140003d35  test    rax, rax
0x140003d38  jz      short loc_140003D47
0x140003d3a  mov     rdx, rdi
0x140003d3d  mov     rcx, [rbx]
0x140003d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d45  jmp     short loc_140003D4E
0x140003d47  call    cs:__imp_GetLastError
0x140003d4d  nop
0x140003d4e  mov     rbx, [rsp+38h+arg_0]
0x140003d53  add     rsp, 30h
0x140003d57  pop     rdi
0x140003d58  retn
```
