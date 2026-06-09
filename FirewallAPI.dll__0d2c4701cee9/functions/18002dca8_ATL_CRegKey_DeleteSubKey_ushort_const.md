# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18002dca8`
- end: `0x18002dd7c`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `212`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18002d198`
- `0x18002edec`
- `0x18002f318`

## callees

- `0x18002dca8`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002dccd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002dccd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002dd06`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002dd06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002dce8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002dd21`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002dce8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002dd21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd63`

## string_xrefs

- `0x18002dcc6`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18002dcde`: `RegDeleteKeyExW`
- `0x18002dcff`: `advapi32.dll`
- `0x18002dd17`: `RegDeleteKeyW`

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
0x18002dca8  mov     [rsp+arg_0], rbx
0x18002dcad  push    rdi
0x18002dcae  sub     rsp, 30h
0x18002dcb2  mov     rdi, rdx
0x18002dcb5  mov     rbx, rcx
0x18002dcb8  cmp     qword ptr [rcx+8], 0
0x18002dcbd  jnz     short loc_18002DD31
0x18002dcbf  cmp     qword ptr [rcx+10h], 0
0x18002dcc4  jnz     short loc_18002DD31
0x18002dcc6  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18002dccd  call    cs:__imp_GetModuleHandleW
0x18002dcd4  nop     dword ptr [rax+rax+00h]
0x18002dcd9  test    rax, rax
0x18002dcdc  jz      short loc_18002DCFA
0x18002dcde  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18002dce5  mov     rcx, rax; hModule
0x18002dce8  call    cs:__imp_GetProcAddress
0x18002dcef  nop     dword ptr [rax+rax+00h]
0x18002dcf4  mov     [rbx+8], rax
0x18002dcf8  jmp     short loc_18002DD31
0x18002dcfa  xor     r8d, r8d; dwFlags
0x18002dcfd  xor     edx, edx; hFile
0x18002dcff  lea     rcx, LibFileName; "advapi32.dll"
0x18002dd06  call    cs:__imp_LoadLibraryExW
0x18002dd0d  nop     dword ptr [rax+rax+00h]
0x18002dd12  test    rax, rax
0x18002dd15  jz      short loc_18002DD31
0x18002dd17  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18002dd1e  mov     rcx, rax; hModule
0x18002dd21  call    cs:__imp_GetProcAddress
0x18002dd28  nop     dword ptr [rax+rax+00h]
0x18002dd2d  mov     [rbx+10h], rax
0x18002dd31  mov     rax, [rbx+8]
0x18002dd35  test    rax, rax
0x18002dd38  jz      short loc_18002DD4D
0x18002dd3a  xor     r9d, r9d
0x18002dd3d  xor     r8d, r8d
0x18002dd40  mov     rdx, rdi
0x18002dd43  mov     rcx, [rbx]
0x18002dd46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd4b  jmp     short loc_18002DD70
0x18002dd4d  mov     rax, [rbx+10h]
0x18002dd51  test    rax, rax
0x18002dd54  jz      short loc_18002DD63
0x18002dd56  mov     rdx, rdi
0x18002dd59  mov     rcx, [rbx]
0x18002dd5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd61  jmp     short loc_18002DD70
0x18002dd63  call    cs:__imp_GetLastError
0x18002dd6a  nop     dword ptr [rax+rax+00h]
0x18002dd6f  nop
0x18002dd70  mov     rbx, [rsp+38h+arg_0]
0x18002dd75  add     rsp, 30h
0x18002dd79  pop     rdi
0x18002dd7a  retn
```
