# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18002bec4`
- end: `0x18002bf79`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18002b490`
- `0x18002cf28`
- `0x18002d414`

## callees

- `0x18002bec4`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002bee9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002bee9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002bf16`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002bf16`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002befe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002bf2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002befe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002bf2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bf67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bf67`

## string_xrefs

- `0x18002bee2`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18002bef4`: `RegDeleteKeyExW`
- `0x18002bf0f`: `advapi32.dll`
- `0x18002bf21`: `RegDeleteKeyW`

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
0x18002bec4  mov     [rsp+arg_0], rbx
0x18002bec9  push    rdi
0x18002beca  sub     rsp, 30h
0x18002bece  mov     rdi, rdx
0x18002bed1  mov     rbx, rcx
0x18002bed4  cmp     qword ptr [rcx+8], 0
0x18002bed9  jnz     short loc_18002BF35
0x18002bedb  cmp     qword ptr [rcx+10h], 0
0x18002bee0  jnz     short loc_18002BF35
0x18002bee2  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18002bee9  call    cs:__imp_GetModuleHandleW
0x18002beef  test    rax, rax
0x18002bef2  jz      short loc_18002BF0A
0x18002bef4  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18002befb  mov     rcx, rax; hModule
0x18002befe  call    cs:__imp_GetProcAddress
0x18002bf04  mov     [rbx+8], rax
0x18002bf08  jmp     short loc_18002BF35
0x18002bf0a  xor     r8d, r8d; dwFlags
0x18002bf0d  xor     edx, edx; hFile
0x18002bf0f  lea     rcx, LibFileName; "advapi32.dll"
0x18002bf16  call    cs:__imp_LoadLibraryExW
0x18002bf1c  test    rax, rax
0x18002bf1f  jz      short loc_18002BF35
0x18002bf21  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18002bf28  mov     rcx, rax; hModule
0x18002bf2b  call    cs:__imp_GetProcAddress
0x18002bf31  mov     [rbx+10h], rax
0x18002bf35  mov     rax, [rbx+8]
0x18002bf39  test    rax, rax
0x18002bf3c  jz      short loc_18002BF51
0x18002bf3e  xor     r9d, r9d
0x18002bf41  xor     r8d, r8d
0x18002bf44  mov     rdx, rdi
0x18002bf47  mov     rcx, [rbx]
0x18002bf4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf4f  jmp     short loc_18002BF6E
0x18002bf51  mov     rax, [rbx+10h]
0x18002bf55  test    rax, rax
0x18002bf58  jz      short loc_18002BF67
0x18002bf5a  mov     rdx, rdi
0x18002bf5d  mov     rcx, [rbx]
0x18002bf60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf65  jmp     short loc_18002BF6E
0x18002bf67  call    cs:__imp_GetLastError
0x18002bf6d  nop
0x18002bf6e  mov     rbx, [rsp+38h+arg_0]
0x18002bf73  add     rsp, 30h
0x18002bf77  pop     rdi
0x18002bf78  retn
```
