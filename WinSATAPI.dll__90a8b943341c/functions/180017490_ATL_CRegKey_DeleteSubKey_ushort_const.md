# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180017490`
- end: `0x18001756e`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `222`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180015a44`
- `0x180018a88`
- `0x180018fb0`

## callees

- `0x180017490`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800174f8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800174f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800174bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800174bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800174da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017513`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800174da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017513`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017555`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017555`

## string_xrefs

- `0x1800174b8`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800174d0`: `RegDeleteKeyExW`
- `0x1800174f1`: `advapi32.dll`
- `0x180017509`: `RegDeleteKeyW`

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
0x180017490  push    rdi
0x180017492  sub     rsp, 40h
0x180017496  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x18001749f  mov     [rsp+48h+arg_0], rbx
0x1800174a4  mov     rdi, rdx
0x1800174a7  mov     rbx, rcx
0x1800174aa  cmp     qword ptr [rcx+8], 0
0x1800174af  jnz     short loc_180017523
0x1800174b1  cmp     qword ptr [rcx+10h], 0
0x1800174b6  jnz     short loc_180017523
0x1800174b8  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800174bf  call    cs:__imp_GetModuleHandleW
0x1800174c6  nop     dword ptr [rax+rax+00h]
0x1800174cb  test    rax, rax
0x1800174ce  jz      short loc_1800174EC
0x1800174d0  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1800174d7  mov     rcx, rax; hModule
0x1800174da  call    cs:__imp_GetProcAddress
0x1800174e1  nop     dword ptr [rax+rax+00h]
0x1800174e6  mov     [rbx+8], rax
0x1800174ea  jmp     short loc_180017523
0x1800174ec  xor     r8d, r8d; dwFlags
0x1800174ef  xor     edx, edx; hFile
0x1800174f1  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x1800174f8  call    cs:__imp_LoadLibraryExW
0x1800174ff  nop     dword ptr [rax+rax+00h]
0x180017504  test    rax, rax
0x180017507  jz      short loc_180017523
0x180017509  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180017510  mov     rcx, rax; hModule
0x180017513  call    cs:__imp_GetProcAddress
0x18001751a  nop     dword ptr [rax+rax+00h]
0x18001751f  mov     [rbx+10h], rax
0x180017523  mov     rax, [rbx+8]
0x180017527  test    rax, rax
0x18001752a  jz      short loc_18001753F
0x18001752c  xor     r9d, r9d
0x18001752f  xor     r8d, r8d
0x180017532  mov     rdx, rdi
0x180017535  mov     rcx, [rbx]
0x180017538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001753d  jmp     short loc_180017562
0x18001753f  mov     rax, [rbx+10h]
0x180017543  test    rax, rax
0x180017546  jz      short loc_180017555
0x180017548  mov     rdx, rdi
0x18001754b  mov     rcx, [rbx]
0x18001754e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017553  jmp     short loc_180017562
0x180017555  call    cs:__imp_GetLastError
0x18001755c  nop     dword ptr [rax+rax+00h]
0x180017561  nop
0x180017562  mov     rbx, [rsp+48h+arg_0]
0x180017567  add     rsp, 40h
0x18001756b  pop     rdi
0x18001756c  retn
```
