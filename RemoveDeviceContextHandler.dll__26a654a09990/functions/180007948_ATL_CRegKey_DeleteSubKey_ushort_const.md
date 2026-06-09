# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180007948`
- end: `0x1800079f9`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `177`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800093e8`
- `0x180009884`

## callees

- `0x180007948`
- `0x18000ba68`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007982`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800079ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007982`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800079ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000796d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000796d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079e8`

## string_xrefs

- `0x180007966`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180007978`: `RegDeleteKeyExW`
- `0x180007991`: `advapi32.dll`
- `0x1800079a2`: `RegDeleteKeyW`

## pseudocode

```c
DWORD __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const unsigned __int16 *a2)
{
  HMODULE ModuleHandleW; // rax
  __int64 v5; // rdx
  HMODULE Library; // rax
  __int64 (__fastcall *v7)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v9)(_QWORD, const unsigned __int16 *); // rax

  if ( *(_OWORD *)((char *)this + 8) == 0 )
  {
    ModuleHandleW = GetModuleHandleW(L"API-MS-Win-Core-LocalRegistry-L1-1-0.dll");
    if ( ModuleHandleW )
    {
      *((_QWORD *)this + 1) = GetProcAddress(ModuleHandleW, "RegDeleteKeyExW");
    }
    else
    {
      Library = IsolationAwareLoadLibraryExW(L"advapi32.dll", v5, 0);
      if ( Library )
        *((_QWORD *)this + 2) = GetProcAddress(Library, "RegDeleteKeyW");
    }
  }
  v7 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD))*((_QWORD *)this + 1);
  if ( v7 )
    return v7(*(_QWORD *)this, a2, 0, 0);
  v9 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *))*((_QWORD *)this + 2);
  if ( v9 )
    return v9(*(_QWORD *)this, a2);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180007948  mov     [rsp+arg_0], rbx
0x18000794d  push    rdi
0x18000794e  sub     rsp, 30h
0x180007952  cmp     qword ptr [rcx+8], 0
0x180007957  mov     rdi, rdx
0x18000795a  mov     rbx, rcx
0x18000795d  jnz     short loc_1800079B6
0x18000795f  cmp     qword ptr [rcx+10h], 0
0x180007964  jnz     short loc_1800079B6
0x180007966  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000796d  call    cs:__imp_GetModuleHandleW
0x180007973  test    rax, rax
0x180007976  jz      short loc_18000798E
0x180007978  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18000797f  mov     rcx, rax; hModule
0x180007982  call    cs:__imp_GetProcAddress
0x180007988  mov     [rbx+8], rax
0x18000798c  jmp     short loc_1800079B6
0x18000798e  xor     r8d, r8d
0x180007991  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x180007998  call    IsolationAwareLoadLibraryExW
0x18000799d  test    rax, rax
0x1800079a0  jz      short loc_1800079B6
0x1800079a2  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800079a9  mov     rcx, rax; hModule
0x1800079ac  call    cs:__imp_GetProcAddress
0x1800079b2  mov     [rbx+10h], rax
0x1800079b6  mov     rax, [rbx+8]
0x1800079ba  test    rax, rax
0x1800079bd  jz      short loc_1800079D2
0x1800079bf  mov     rcx, [rbx]
0x1800079c2  xor     r9d, r9d
0x1800079c5  xor     r8d, r8d
0x1800079c8  mov     rdx, rdi
0x1800079cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079d0  jmp     short loc_1800079EE
0x1800079d2  mov     rax, [rbx+10h]
0x1800079d6  test    rax, rax
0x1800079d9  jz      short loc_1800079E8
0x1800079db  mov     rcx, [rbx]
0x1800079de  mov     rdx, rdi
0x1800079e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079e6  jmp     short loc_1800079EE
0x1800079e8  call    cs:__imp_GetLastError
0x1800079ee  mov     rbx, [rsp+38h+arg_0]
0x1800079f3  add     rsp, 30h
0x1800079f7  pop     rdi
0x1800079f8  retn
```
