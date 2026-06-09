# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180005020`
- end: `0x1800050d5`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000685c`
- `0x180006d1c`
- `0x1800090b0`

## callees

- `0x180005020`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000505a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005087`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000505a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005087`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005045`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005045`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005072`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050c3`

## string_xrefs

- `0x18000503e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180005050`: `RegDeleteKeyExW`
- `0x18000506b`: `advapi32.dll`
- `0x18000507d`: `RegDeleteKeyW`

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
0x180005020  mov     [rsp+arg_0], rbx
0x180005025  push    rdi
0x180005026  sub     rsp, 30h
0x18000502a  mov     rdi, rdx
0x18000502d  mov     rbx, rcx
0x180005030  cmp     qword ptr [rcx+8], 0
0x180005035  jnz     short loc_180005091
0x180005037  cmp     qword ptr [rcx+10h], 0
0x18000503c  jnz     short loc_180005091
0x18000503e  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180005045  call    cs:__imp_GetModuleHandleW
0x18000504b  test    rax, rax
0x18000504e  jz      short loc_180005066
0x180005050  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180005057  mov     rcx, rax; hModule
0x18000505a  call    cs:__imp_GetProcAddress
0x180005060  mov     [rbx+8], rax
0x180005064  jmp     short loc_180005091
0x180005066  xor     r8d, r8d; dwFlags
0x180005069  xor     edx, edx; hFile
0x18000506b  lea     rcx, LibFileName; "advapi32.dll"
0x180005072  call    cs:__imp_LoadLibraryExW
0x180005078  test    rax, rax
0x18000507b  jz      short loc_180005091
0x18000507d  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180005084  mov     rcx, rax; hModule
0x180005087  call    cs:__imp_GetProcAddress
0x18000508d  mov     [rbx+10h], rax
0x180005091  mov     rax, [rbx+8]
0x180005095  test    rax, rax
0x180005098  jz      short loc_1800050AD
0x18000509a  xor     r9d, r9d
0x18000509d  xor     r8d, r8d
0x1800050a0  mov     rdx, rdi
0x1800050a3  mov     rcx, [rbx]
0x1800050a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050ab  jmp     short loc_1800050CA
0x1800050ad  mov     rax, [rbx+10h]
0x1800050b1  test    rax, rax
0x1800050b4  jz      short loc_1800050C3
0x1800050b6  mov     rdx, rdi
0x1800050b9  mov     rcx, [rbx]
0x1800050bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050c1  jmp     short loc_1800050CA
0x1800050c3  call    cs:__imp_GetLastError
0x1800050c9  nop
0x1800050ca  mov     rbx, [rsp+38h+arg_0]
0x1800050cf  add     rsp, 30h
0x1800050d3  pop     rdi
0x1800050d4  retn
```
