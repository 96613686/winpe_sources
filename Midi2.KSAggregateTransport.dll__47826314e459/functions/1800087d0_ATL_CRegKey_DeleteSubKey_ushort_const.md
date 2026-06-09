# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800087d0`
- end: `0x180008885`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a384`
- `0x18000a844`
- `0x1800111b0`

## callees

- `0x1800087d0`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800087f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800087f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000880a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008837`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000880a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008837`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008822`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008873`

## string_xrefs

- `0x1800087ee`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180008800`: `RegDeleteKeyExW`
- `0x18000881b`: `advapi32.dll`
- `0x18000882d`: `RegDeleteKeyW`

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
0x1800087d0  mov     [rsp+arg_0], rbx
0x1800087d5  push    rdi
0x1800087d6  sub     rsp, 30h
0x1800087da  mov     rdi, rdx
0x1800087dd  mov     rbx, rcx
0x1800087e0  cmp     qword ptr [rcx+8], 0
0x1800087e5  jnz     short loc_180008841
0x1800087e7  cmp     qword ptr [rcx+10h], 0
0x1800087ec  jnz     short loc_180008841
0x1800087ee  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800087f5  call    cs:__imp_GetModuleHandleW
0x1800087fb  test    rax, rax
0x1800087fe  jz      short loc_180008816
0x180008800  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180008807  mov     rcx, rax; hModule
0x18000880a  call    cs:__imp_GetProcAddress
0x180008810  mov     [rbx+8], rax
0x180008814  jmp     short loc_180008841
0x180008816  xor     r8d, r8d; dwFlags
0x180008819  xor     edx, edx; hFile
0x18000881b  lea     rcx, LibFileName; "advapi32.dll"
0x180008822  call    cs:__imp_LoadLibraryExW
0x180008828  test    rax, rax
0x18000882b  jz      short loc_180008841
0x18000882d  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180008834  mov     rcx, rax; hModule
0x180008837  call    cs:__imp_GetProcAddress
0x18000883d  mov     [rbx+10h], rax
0x180008841  mov     rax, [rbx+8]
0x180008845  test    rax, rax
0x180008848  jz      short loc_18000885D
0x18000884a  xor     r9d, r9d
0x18000884d  xor     r8d, r8d
0x180008850  mov     rdx, rdi
0x180008853  mov     rcx, [rbx]
0x180008856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000885b  jmp     short loc_18000887A
0x18000885d  mov     rax, [rbx+10h]
0x180008861  test    rax, rax
0x180008864  jz      short loc_180008873
0x180008866  mov     rdx, rdi
0x180008869  mov     rcx, [rbx]
0x18000886c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008871  jmp     short loc_18000887A
0x180008873  call    cs:__imp_GetLastError
0x180008879  nop
0x18000887a  mov     rbx, [rsp+38h+arg_0]
0x18000887f  add     rsp, 30h
0x180008883  pop     rdi
0x180008884  retn
```
