# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180004f10`
- end: `0x180004fc5`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000674c`
- `0x180006c0c`
- `0x180008f90`

## callees

- `0x180004f10`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180004f62`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180004f62`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004f35`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004f35`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004f4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004f77`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004f4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004f77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fb3`

## string_xrefs

- `0x180004f2e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180004f40`: `RegDeleteKeyExW`
- `0x180004f5b`: `advapi32.dll`
- `0x180004f6d`: `RegDeleteKeyW`

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
0x180004f10  mov     [rsp+arg_0], rbx
0x180004f15  push    rdi
0x180004f16  sub     rsp, 30h
0x180004f1a  mov     rdi, rdx
0x180004f1d  mov     rbx, rcx
0x180004f20  cmp     qword ptr [rcx+8], 0
0x180004f25  jnz     short loc_180004F81
0x180004f27  cmp     qword ptr [rcx+10h], 0
0x180004f2c  jnz     short loc_180004F81
0x180004f2e  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180004f35  call    cs:__imp_GetModuleHandleW
0x180004f3b  test    rax, rax
0x180004f3e  jz      short loc_180004F56
0x180004f40  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180004f47  mov     rcx, rax; hModule
0x180004f4a  call    cs:__imp_GetProcAddress
0x180004f50  mov     [rbx+8], rax
0x180004f54  jmp     short loc_180004F81
0x180004f56  xor     r8d, r8d; dwFlags
0x180004f59  xor     edx, edx; hFile
0x180004f5b  lea     rcx, LibFileName; "advapi32.dll"
0x180004f62  call    cs:__imp_LoadLibraryExW
0x180004f68  test    rax, rax
0x180004f6b  jz      short loc_180004F81
0x180004f6d  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180004f74  mov     rcx, rax; hModule
0x180004f77  call    cs:__imp_GetProcAddress
0x180004f7d  mov     [rbx+10h], rax
0x180004f81  mov     rax, [rbx+8]
0x180004f85  test    rax, rax
0x180004f88  jz      short loc_180004F9D
0x180004f8a  xor     r9d, r9d
0x180004f8d  xor     r8d, r8d
0x180004f90  mov     rdx, rdi
0x180004f93  mov     rcx, [rbx]
0x180004f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f9b  jmp     short loc_180004FBA
0x180004f9d  mov     rax, [rbx+10h]
0x180004fa1  test    rax, rax
0x180004fa4  jz      short loc_180004FB3
0x180004fa6  mov     rdx, rdi
0x180004fa9  mov     rcx, [rbx]
0x180004fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fb1  jmp     short loc_180004FBA
0x180004fb3  call    cs:__imp_GetLastError
0x180004fb9  nop
0x180004fba  mov     rbx, [rsp+38h+arg_0]
0x180004fbf  add     rsp, 30h
0x180004fc3  pop     rdi
0x180004fc4  retn
```
