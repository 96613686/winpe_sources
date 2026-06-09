# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180015e30`
- end: `0x180015ee5`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180015ef0`

## callees

- `0x180015e30`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015e6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015e97`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015e6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015e97`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015e55`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015e55`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180015e82`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180015e82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ed3`

## string_xrefs

- `0x180015e4e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180015e60`: `RegDeleteKeyExW`
- `0x180015e7b`: `advapi32.dll`
- `0x180015e8d`: `RegDeleteKeyW`

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
0x180015e30  mov     [rsp+arg_0], rbx
0x180015e35  push    rdi
0x180015e36  sub     rsp, 30h
0x180015e3a  mov     rdi, rdx
0x180015e3d  mov     rbx, rcx
0x180015e40  cmp     qword ptr [rcx+8], 0
0x180015e45  jnz     short loc_180015EA1
0x180015e47  cmp     qword ptr [rcx+10h], 0
0x180015e4c  jnz     short loc_180015EA1
0x180015e4e  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180015e55  call    cs:__imp_GetModuleHandleW
0x180015e5b  test    rax, rax
0x180015e5e  jz      short loc_180015E76
0x180015e60  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180015e67  mov     rcx, rax; hModule
0x180015e6a  call    cs:__imp_GetProcAddress
0x180015e70  mov     [rbx+8], rax
0x180015e74  jmp     short loc_180015EA1
0x180015e76  xor     r8d, r8d; dwFlags
0x180015e79  xor     edx, edx; hFile
0x180015e7b  lea     rcx, LibFileName; "advapi32.dll"
0x180015e82  call    cs:__imp_LoadLibraryExW
0x180015e88  test    rax, rax
0x180015e8b  jz      short loc_180015EA1
0x180015e8d  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180015e94  mov     rcx, rax; hModule
0x180015e97  call    cs:__imp_GetProcAddress
0x180015e9d  mov     [rbx+10h], rax
0x180015ea1  mov     rax, [rbx+8]
0x180015ea5  test    rax, rax
0x180015ea8  jz      short loc_180015EBD
0x180015eaa  xor     r9d, r9d
0x180015ead  xor     r8d, r8d
0x180015eb0  mov     rdx, rdi
0x180015eb3  mov     rcx, [rbx]
0x180015eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ebb  jmp     short loc_180015EDA
0x180015ebd  mov     rax, [rbx+10h]
0x180015ec1  test    rax, rax
0x180015ec4  jz      short loc_180015ED3
0x180015ec6  mov     rdx, rdi
0x180015ec9  mov     rcx, [rbx]
0x180015ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ed1  jmp     short loc_180015EDA
0x180015ed3  call    cs:__imp_GetLastError
0x180015ed9  nop
0x180015eda  mov     rbx, [rsp+38h+arg_0]
0x180015edf  add     rsp, 30h
0x180015ee3  pop     rdi
0x180015ee4  retn
```
