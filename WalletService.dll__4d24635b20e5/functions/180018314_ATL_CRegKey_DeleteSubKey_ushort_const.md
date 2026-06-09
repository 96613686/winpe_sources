# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180018314`
- end: `0x1800183c8`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180019400`
- `0x180019820`

## callees

- `0x180018314`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018366`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018366`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001834e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001837b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001834e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001837b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018339`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018339`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183b7`

## string_xrefs

- `0x180018332`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180018344`: `RegDeleteKeyExW`
- `0x18001835d`: `advapi32.dll`
- `0x180018371`: `RegDeleteKeyW`

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
0x180018314  mov     [rsp+arg_0], rbx
0x180018319  push    rdi
0x18001831a  sub     rsp, 30h
0x18001831e  cmp     qword ptr [rcx+8], 0
0x180018323  mov     rdi, rdx
0x180018326  mov     rbx, rcx
0x180018329  jnz     short loc_180018385
0x18001832b  cmp     qword ptr [rcx+10h], 0
0x180018330  jnz     short loc_180018385
0x180018332  lea     rcx, aApiMsWinCoreLo_4; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180018339  call    cs:__imp_GetModuleHandleW
0x18001833f  test    rax, rax
0x180018342  jz      short loc_18001835A
0x180018344  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18001834b  mov     rcx, rax; hModule
0x18001834e  call    cs:__imp_GetProcAddress
0x180018354  mov     [rbx+8], rax
0x180018358  jmp     short loc_180018385
0x18001835a  xor     r8d, r8d; dwFlags
0x18001835d  lea     rcx, LibFileName; "advapi32.dll"
0x180018364  xor     edx, edx; hFile
0x180018366  call    cs:__imp_LoadLibraryExW
0x18001836c  test    rax, rax
0x18001836f  jz      short loc_180018385
0x180018371  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180018378  mov     rcx, rax; hModule
0x18001837b  call    cs:__imp_GetProcAddress
0x180018381  mov     [rbx+10h], rax
0x180018385  mov     rax, [rbx+8]
0x180018389  test    rax, rax
0x18001838c  jz      short loc_1800183A1
0x18001838e  mov     rcx, [rbx]
0x180018391  xor     r9d, r9d
0x180018394  xor     r8d, r8d
0x180018397  mov     rdx, rdi
0x18001839a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001839f  jmp     short loc_1800183BD
0x1800183a1  mov     rax, [rbx+10h]
0x1800183a5  test    rax, rax
0x1800183a8  jz      short loc_1800183B7
0x1800183aa  mov     rcx, [rbx]
0x1800183ad  mov     rdx, rdi
0x1800183b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183b5  jmp     short loc_1800183BD
0x1800183b7  call    cs:__imp_GetLastError
0x1800183bd  mov     rbx, [rsp+38h+arg_0]
0x1800183c2  add     rsp, 30h
0x1800183c6  pop     rdi
0x1800183c7  retn
```
