# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800783c0`
- end: `0x180078493`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `211`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18007792c`
- `0x18007964c`
- `0x180079b40`

## callees

- `0x1800783c0`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007847b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007847b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007841e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007841e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800783e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800783e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180078400`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180078439`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180078400`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180078439`

## string_xrefs

- `0x1800783de`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800783f6`: `RegDeleteKeyExW`
- `0x180078415`: `advapi32.dll`
- `0x18007842f`: `RegDeleteKeyW`

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
0x1800783c0  mov     [rsp+arg_0], rbx
0x1800783c5  push    rdi
0x1800783c6  sub     rsp, 30h
0x1800783ca  cmp     qword ptr [rcx+8], 0
0x1800783cf  mov     rdi, rdx
0x1800783d2  mov     rbx, rcx
0x1800783d5  jnz     short loc_180078449
0x1800783d7  cmp     qword ptr [rcx+10h], 0
0x1800783dc  jnz     short loc_180078449
0x1800783de  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800783e5  call    cs:__imp_GetModuleHandleW
0x1800783ec  nop     dword ptr [rax+rax+00h]
0x1800783f1  test    rax, rax
0x1800783f4  jz      short loc_180078412
0x1800783f6  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1800783fd  mov     rcx, rax; hModule
0x180078400  call    cs:__imp_GetProcAddress
0x180078407  nop     dword ptr [rax+rax+00h]
0x18007840c  mov     [rbx+8], rax
0x180078410  jmp     short loc_180078449
0x180078412  xor     r8d, r8d; dwFlags
0x180078415  lea     rcx, LibFileName; "advapi32.dll"
0x18007841c  xor     edx, edx; hFile
0x18007841e  call    cs:__imp_LoadLibraryExW
0x180078425  nop     dword ptr [rax+rax+00h]
0x18007842a  test    rax, rax
0x18007842d  jz      short loc_180078449
0x18007842f  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180078436  mov     rcx, rax; hModule
0x180078439  call    cs:__imp_GetProcAddress
0x180078440  nop     dword ptr [rax+rax+00h]
0x180078445  mov     [rbx+10h], rax
0x180078449  mov     rax, [rbx+8]
0x18007844d  test    rax, rax
0x180078450  jz      short loc_180078465
0x180078452  mov     rcx, [rbx]
0x180078455  xor     r9d, r9d
0x180078458  xor     r8d, r8d
0x18007845b  mov     rdx, rdi
0x18007845e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078463  jmp     short loc_180078487
0x180078465  mov     rax, [rbx+10h]
0x180078469  test    rax, rax
0x18007846c  jz      short loc_18007847B
0x18007846e  mov     rcx, [rbx]
0x180078471  mov     rdx, rdi
0x180078474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078479  jmp     short loc_180078487
0x18007847b  call    cs:__imp_GetLastError
0x180078482  nop     dword ptr [rax+rax+00h]
0x180078487  mov     rbx, [rsp+38h+arg_0]
0x18007848c  add     rsp, 30h
0x180078490  pop     rdi
0x180078491  retn
```
