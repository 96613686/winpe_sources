# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800b7ef0`
- end: `0x1800b7fa5`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800b3454`

## callees

- `0x1800b7ef0`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b7f42`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b7f42`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b7f15`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b7f15`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b7f2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b7f57`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b7f2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b7f57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7f93`

## string_xrefs

- `0x1800b7f0e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800b7f20`: `RegDeleteKeyExW`
- `0x1800b7f3b`: `advapi32.dll`
- `0x1800b7f4d`: `RegDeleteKeyW`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x1800b7ef0  mov     [rsp+arg_0], rbx
0x1800b7ef5  push    rdi
0x1800b7ef6  sub     rsp, 30h
0x1800b7efa  mov     rdi, rdx
0x1800b7efd  mov     rbx, rcx
0x1800b7f00  cmp     qword ptr [rcx+8], 0
0x1800b7f05  jnz     short loc_1800B7F61
0x1800b7f07  cmp     qword ptr [rcx+10h], 0
0x1800b7f0c  jnz     short loc_1800B7F61
0x1800b7f0e  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800b7f15  call    cs:__imp_GetModuleHandleW
0x1800b7f1b  test    rax, rax
0x1800b7f1e  jz      short loc_1800B7F36
0x1800b7f20  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1800b7f27  mov     rcx, rax; hModule
0x1800b7f2a  call    cs:__imp_GetProcAddress
0x1800b7f30  mov     [rbx+8], rax
0x1800b7f34  jmp     short loc_1800B7F61
0x1800b7f36  xor     r8d, r8d; dwFlags
0x1800b7f39  xor     edx, edx; hFile
0x1800b7f3b  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x1800b7f42  call    cs:__imp_LoadLibraryExW
0x1800b7f48  test    rax, rax
0x1800b7f4b  jz      short loc_1800B7F61
0x1800b7f4d  lea     rdx, aRegdeletekeyw_0; "RegDeleteKeyW"
0x1800b7f54  mov     rcx, rax; hModule
0x1800b7f57  call    cs:__imp_GetProcAddress
0x1800b7f5d  mov     [rbx+10h], rax
0x1800b7f61  mov     rax, [rbx+8]
0x1800b7f65  test    rax, rax
0x1800b7f68  jz      short loc_1800B7F7D
0x1800b7f6a  xor     r9d, r9d
0x1800b7f6d  xor     r8d, r8d
0x1800b7f70  mov     rdx, rdi
0x1800b7f73  mov     rcx, [rbx]
0x1800b7f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7f7b  jmp     short loc_1800B7F9A
0x1800b7f7d  mov     rax, [rbx+10h]
0x1800b7f81  test    rax, rax
0x1800b7f84  jz      short loc_1800B7F93
0x1800b7f86  mov     rdx, rdi
0x1800b7f89  mov     rcx, [rbx]
0x1800b7f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7f91  jmp     short loc_1800B7F9A
0x1800b7f93  call    cs:__imp_GetLastError
0x1800b7f99  nop
0x1800b7f9a  mov     rbx, [rsp+38h+arg_0]
0x1800b7f9f  add     rsp, 30h
0x1800b7fa3  pop     rdi
0x1800b7fa4  retn
```
