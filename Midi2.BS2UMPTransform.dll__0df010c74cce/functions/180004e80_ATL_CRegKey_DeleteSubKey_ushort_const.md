# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180004e80`
- end: `0x180004f35`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800066bc`
- `0x180006b7c`
- `0x180008f00`

## callees

- `0x180004e80`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004ea5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004ea5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004eba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004ee7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004eba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004ee7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180004ed2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180004ed2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f23`

## string_xrefs

- `0x180004e9e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180004eb0`: `RegDeleteKeyExW`
- `0x180004ecb`: `advapi32.dll`
- `0x180004edd`: `RegDeleteKeyW`

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
0x180004e80  mov     [rsp+arg_0], rbx
0x180004e85  push    rdi
0x180004e86  sub     rsp, 30h
0x180004e8a  mov     rdi, rdx
0x180004e8d  mov     rbx, rcx
0x180004e90  cmp     qword ptr [rcx+8], 0
0x180004e95  jnz     short loc_180004EF1
0x180004e97  cmp     qword ptr [rcx+10h], 0
0x180004e9c  jnz     short loc_180004EF1
0x180004e9e  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180004ea5  call    cs:__imp_GetModuleHandleW
0x180004eab  test    rax, rax
0x180004eae  jz      short loc_180004EC6
0x180004eb0  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180004eb7  mov     rcx, rax; hModule
0x180004eba  call    cs:__imp_GetProcAddress
0x180004ec0  mov     [rbx+8], rax
0x180004ec4  jmp     short loc_180004EF1
0x180004ec6  xor     r8d, r8d; dwFlags
0x180004ec9  xor     edx, edx; hFile
0x180004ecb  lea     rcx, LibFileName; "advapi32.dll"
0x180004ed2  call    cs:__imp_LoadLibraryExW
0x180004ed8  test    rax, rax
0x180004edb  jz      short loc_180004EF1
0x180004edd  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180004ee4  mov     rcx, rax; hModule
0x180004ee7  call    cs:__imp_GetProcAddress
0x180004eed  mov     [rbx+10h], rax
0x180004ef1  mov     rax, [rbx+8]
0x180004ef5  test    rax, rax
0x180004ef8  jz      short loc_180004F0D
0x180004efa  xor     r9d, r9d
0x180004efd  xor     r8d, r8d
0x180004f00  mov     rdx, rdi
0x180004f03  mov     rcx, [rbx]
0x180004f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f0b  jmp     short loc_180004F2A
0x180004f0d  mov     rax, [rbx+10h]
0x180004f11  test    rax, rax
0x180004f14  jz      short loc_180004F23
0x180004f16  mov     rdx, rdi
0x180004f19  mov     rcx, [rbx]
0x180004f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f21  jmp     short loc_180004F2A
0x180004f23  call    cs:__imp_GetLastError
0x180004f29  nop
0x180004f2a  mov     rbx, [rsp+38h+arg_0]
0x180004f2f  add     rsp, 30h
0x180004f33  pop     rdi
0x180004f34  retn
```
