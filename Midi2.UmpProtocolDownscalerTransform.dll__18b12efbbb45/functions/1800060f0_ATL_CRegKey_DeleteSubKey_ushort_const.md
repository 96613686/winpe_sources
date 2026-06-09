# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800060f0`
- end: `0x1800061a5`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000792c`
- `0x180007dec`
- `0x18000a170`

## callees

- `0x1800060f0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006142`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006142`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006115`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006115`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000612a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006157`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000612a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006157`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006193`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006193`

## string_xrefs

- `0x18000610e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180006120`: `RegDeleteKeyExW`
- `0x18000613b`: `advapi32.dll`
- `0x18000614d`: `RegDeleteKeyW`

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
0x1800060f0  mov     [rsp+arg_0], rbx
0x1800060f5  push    rdi
0x1800060f6  sub     rsp, 30h
0x1800060fa  mov     rdi, rdx
0x1800060fd  mov     rbx, rcx
0x180006100  cmp     qword ptr [rcx+8], 0
0x180006105  jnz     short loc_180006161
0x180006107  cmp     qword ptr [rcx+10h], 0
0x18000610c  jnz     short loc_180006161
0x18000610e  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180006115  call    cs:__imp_GetModuleHandleW
0x18000611b  test    rax, rax
0x18000611e  jz      short loc_180006136
0x180006120  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180006127  mov     rcx, rax; hModule
0x18000612a  call    cs:__imp_GetProcAddress
0x180006130  mov     [rbx+8], rax
0x180006134  jmp     short loc_180006161
0x180006136  xor     r8d, r8d; dwFlags
0x180006139  xor     edx, edx; hFile
0x18000613b  lea     rcx, LibFileName; "advapi32.dll"
0x180006142  call    cs:__imp_LoadLibraryExW
0x180006148  test    rax, rax
0x18000614b  jz      short loc_180006161
0x18000614d  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180006154  mov     rcx, rax; hModule
0x180006157  call    cs:__imp_GetProcAddress
0x18000615d  mov     [rbx+10h], rax
0x180006161  mov     rax, [rbx+8]
0x180006165  test    rax, rax
0x180006168  jz      short loc_18000617D
0x18000616a  xor     r9d, r9d
0x18000616d  xor     r8d, r8d
0x180006170  mov     rdx, rdi
0x180006173  mov     rcx, [rbx]
0x180006176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000617b  jmp     short loc_18000619A
0x18000617d  mov     rax, [rbx+10h]
0x180006181  test    rax, rax
0x180006184  jz      short loc_180006193
0x180006186  mov     rdx, rdi
0x180006189  mov     rcx, [rbx]
0x18000618c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006191  jmp     short loc_18000619A
0x180006193  call    cs:__imp_GetLastError
0x180006199  nop
0x18000619a  mov     rbx, [rsp+38h+arg_0]
0x18000619f  add     rsp, 30h
0x1800061a3  pop     rdi
0x1800061a4  retn
```
