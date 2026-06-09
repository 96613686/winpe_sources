# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18001f8d4`
- end: `0x18001f988`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800201e8`
- `0x18002062c`

## callees

- `0x18001f8d4`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f8f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f8f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f90e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f93b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f90e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f93b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001f926`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001f926`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f977`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f977`

## string_xrefs

- `0x18001f8f2`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18001f904`: `RegDeleteKeyExW`
- `0x18001f91d`: `advapi32.dll`
- `0x18001f931`: `RegDeleteKeyW`

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
0x18001f8d4  mov     [rsp+arg_0], rbx
0x18001f8d9  push    rdi
0x18001f8da  sub     rsp, 30h
0x18001f8de  cmp     qword ptr [rcx+8], 0
0x18001f8e3  mov     rdi, rdx
0x18001f8e6  mov     rbx, rcx
0x18001f8e9  jnz     short loc_18001F945
0x18001f8eb  cmp     qword ptr [rcx+10h], 0
0x18001f8f0  jnz     short loc_18001F945
0x18001f8f2  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18001f8f9  call    cs:__imp_GetModuleHandleW
0x18001f8ff  test    rax, rax
0x18001f902  jz      short loc_18001F91A
0x18001f904  lea     rdx, ProcName; "RegDeleteKeyExW"
0x18001f90b  mov     rcx, rax; hModule
0x18001f90e  call    cs:__imp_GetProcAddress
0x18001f914  mov     [rbx+8], rax
0x18001f918  jmp     short loc_18001F945
0x18001f91a  xor     r8d, r8d; dwFlags
0x18001f91d  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x18001f924  xor     edx, edx; hFile
0x18001f926  call    cs:__imp_LoadLibraryExW
0x18001f92c  test    rax, rax
0x18001f92f  jz      short loc_18001F945
0x18001f931  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18001f938  mov     rcx, rax; hModule
0x18001f93b  call    cs:__imp_GetProcAddress
0x18001f941  mov     [rbx+10h], rax
0x18001f945  mov     rax, [rbx+8]
0x18001f949  test    rax, rax
0x18001f94c  jz      short loc_18001F961
0x18001f94e  mov     rcx, [rbx]
0x18001f951  xor     r9d, r9d
0x18001f954  xor     r8d, r8d
0x18001f957  mov     rdx, rdi
0x18001f95a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f95f  jmp     short loc_18001F97D
0x18001f961  mov     rax, [rbx+10h]
0x18001f965  test    rax, rax
0x18001f968  jz      short loc_18001F977
0x18001f96a  mov     rcx, [rbx]
0x18001f96d  mov     rdx, rdi
0x18001f970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f975  jmp     short loc_18001F97D
0x18001f977  call    cs:__imp_GetLastError
0x18001f97d  mov     rbx, [rsp+38h+arg_0]
0x18001f982  add     rsp, 30h
0x18001f986  pop     rdi
0x18001f987  retn
```
