# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180005348`
- end: `0x1800053fd`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180005bb8`
- `0x18000607c`

## callees

- `0x180005348`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000536d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000536d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005382`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800053af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005382`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800053af`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000539a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000539a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053eb`

## string_xrefs

- `0x180005366`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180005378`: `RegDeleteKeyExW`
- `0x180005393`: `advapi32.dll`
- `0x1800053a5`: `RegDeleteKeyW`

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
0x180005348  mov     [rsp+arg_0], rbx
0x18000534d  push    rdi
0x18000534e  sub     rsp, 30h
0x180005352  mov     rdi, rdx
0x180005355  mov     rbx, rcx
0x180005358  cmp     qword ptr [rcx+8], 0
0x18000535d  jnz     short loc_1800053B9
0x18000535f  cmp     qword ptr [rcx+10h], 0
0x180005364  jnz     short loc_1800053B9
0x180005366  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000536d  call    cs:__imp_GetModuleHandleW
0x180005373  test    rax, rax
0x180005376  jz      short loc_18000538E
0x180005378  lea     rdx, ProcName; "RegDeleteKeyExW"
0x18000537f  mov     rcx, rax; hModule
0x180005382  call    cs:__imp_GetProcAddress
0x180005388  mov     [rbx+8], rax
0x18000538c  jmp     short loc_1800053B9
0x18000538e  xor     r8d, r8d; dwFlags
0x180005391  xor     edx, edx; hFile
0x180005393  lea     rcx, LibFileName; "advapi32.dll"
0x18000539a  call    cs:__imp_LoadLibraryExW
0x1800053a0  test    rax, rax
0x1800053a3  jz      short loc_1800053B9
0x1800053a5  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800053ac  mov     rcx, rax; hModule
0x1800053af  call    cs:__imp_GetProcAddress
0x1800053b5  mov     [rbx+10h], rax
0x1800053b9  mov     rax, [rbx+8]
0x1800053bd  test    rax, rax
0x1800053c0  jz      short loc_1800053D5
0x1800053c2  xor     r9d, r9d
0x1800053c5  xor     r8d, r8d
0x1800053c8  mov     rdx, rdi
0x1800053cb  mov     rcx, [rbx]
0x1800053ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053d3  jmp     short loc_1800053F2
0x1800053d5  mov     rax, [rbx+10h]
0x1800053d9  test    rax, rax
0x1800053dc  jz      short loc_1800053EB
0x1800053de  mov     rdx, rdi
0x1800053e1  mov     rcx, [rbx]
0x1800053e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053e9  jmp     short loc_1800053F2
0x1800053eb  call    cs:__imp_GetLastError
0x1800053f1  nop
0x1800053f2  mov     rbx, [rsp+38h+arg_0]
0x1800053f7  add     rsp, 30h
0x1800053fb  pop     rdi
0x1800053fc  retn
```
