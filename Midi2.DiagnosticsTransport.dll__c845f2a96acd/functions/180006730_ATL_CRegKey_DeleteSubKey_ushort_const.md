# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180006730`
- end: `0x1800067e5`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180007f6c`
- `0x18000842c`
- `0x18000a7b0`

## callees

- `0x180006730`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000676a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006797`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000676a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006797`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006782`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006782`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006755`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006755`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067d3`

## string_xrefs

- `0x18000674e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180006760`: `RegDeleteKeyExW`
- `0x18000677b`: `advapi32.dll`
- `0x18000678d`: `RegDeleteKeyW`

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
0x180006730  mov     [rsp+arg_0], rbx
0x180006735  push    rdi
0x180006736  sub     rsp, 30h
0x18000673a  mov     rdi, rdx
0x18000673d  mov     rbx, rcx
0x180006740  cmp     qword ptr [rcx+8], 0
0x180006745  jnz     short loc_1800067A1
0x180006747  cmp     qword ptr [rcx+10h], 0
0x18000674c  jnz     short loc_1800067A1
0x18000674e  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180006755  call    cs:__imp_GetModuleHandleW
0x18000675b  test    rax, rax
0x18000675e  jz      short loc_180006776
0x180006760  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180006767  mov     rcx, rax; hModule
0x18000676a  call    cs:__imp_GetProcAddress
0x180006770  mov     [rbx+8], rax
0x180006774  jmp     short loc_1800067A1
0x180006776  xor     r8d, r8d; dwFlags
0x180006779  xor     edx, edx; hFile
0x18000677b  lea     rcx, LibFileName; "advapi32.dll"
0x180006782  call    cs:__imp_LoadLibraryExW
0x180006788  test    rax, rax
0x18000678b  jz      short loc_1800067A1
0x18000678d  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180006794  mov     rcx, rax; hModule
0x180006797  call    cs:__imp_GetProcAddress
0x18000679d  mov     [rbx+10h], rax
0x1800067a1  mov     rax, [rbx+8]
0x1800067a5  test    rax, rax
0x1800067a8  jz      short loc_1800067BD
0x1800067aa  xor     r9d, r9d
0x1800067ad  xor     r8d, r8d
0x1800067b0  mov     rdx, rdi
0x1800067b3  mov     rcx, [rbx]
0x1800067b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067bb  jmp     short loc_1800067DA
0x1800067bd  mov     rax, [rbx+10h]
0x1800067c1  test    rax, rax
0x1800067c4  jz      short loc_1800067D3
0x1800067c6  mov     rdx, rdi
0x1800067c9  mov     rcx, [rbx]
0x1800067cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067d1  jmp     short loc_1800067DA
0x1800067d3  call    cs:__imp_GetLastError
0x1800067d9  nop
0x1800067da  mov     rbx, [rsp+38h+arg_0]
0x1800067df  add     rsp, 30h
0x1800067e3  pop     rdi
0x1800067e4  retn
```
