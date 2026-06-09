# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180004be8`
- end: `0x180004c9d`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180004098`
- `0x1800053d8`
- `0x18000589c`

## callees

- `0x180004be8`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004c22`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004c4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004c22`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004c4f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180004c3a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180004c3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004c0d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004c0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c8b`

## string_xrefs

- `0x180004c06`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180004c18`: `RegDeleteKeyExW`
- `0x180004c33`: `advapi32.dll`
- `0x180004c45`: `RegDeleteKeyW`

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
0x180004be8  mov     [rsp+arg_0], rbx
0x180004bed  push    rdi
0x180004bee  sub     rsp, 30h
0x180004bf2  mov     rdi, rdx
0x180004bf5  mov     rbx, rcx
0x180004bf8  cmp     qword ptr [rcx+8], 0
0x180004bfd  jnz     short loc_180004C59
0x180004bff  cmp     qword ptr [rcx+10h], 0
0x180004c04  jnz     short loc_180004C59
0x180004c06  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180004c0d  call    cs:__imp_GetModuleHandleW
0x180004c13  test    rax, rax
0x180004c16  jz      short loc_180004C2E
0x180004c18  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180004c1f  mov     rcx, rax; hModule
0x180004c22  call    cs:__imp_GetProcAddress
0x180004c28  mov     [rbx+8], rax
0x180004c2c  jmp     short loc_180004C59
0x180004c2e  xor     r8d, r8d; dwFlags
0x180004c31  xor     edx, edx; hFile
0x180004c33  lea     rcx, LibFileName; "advapi32.dll"
0x180004c3a  call    cs:__imp_LoadLibraryExW
0x180004c40  test    rax, rax
0x180004c43  jz      short loc_180004C59
0x180004c45  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180004c4c  mov     rcx, rax; hModule
0x180004c4f  call    cs:__imp_GetProcAddress
0x180004c55  mov     [rbx+10h], rax
0x180004c59  mov     rax, [rbx+8]
0x180004c5d  test    rax, rax
0x180004c60  jz      short loc_180004C75
0x180004c62  xor     r9d, r9d
0x180004c65  xor     r8d, r8d
0x180004c68  mov     rdx, rdi
0x180004c6b  mov     rcx, [rbx]
0x180004c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c73  jmp     short loc_180004C92
0x180004c75  mov     rax, [rbx+10h]
0x180004c79  test    rax, rax
0x180004c7c  jz      short loc_180004C8B
0x180004c7e  mov     rdx, rdi
0x180004c81  mov     rcx, [rbx]
0x180004c84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c89  jmp     short loc_180004C92
0x180004c8b  call    cs:__imp_GetLastError
0x180004c91  nop
0x180004c92  mov     rbx, [rsp+38h+arg_0]
0x180004c97  add     rsp, 30h
0x180004c9b  pop     rdi
0x180004c9c  retn
```
