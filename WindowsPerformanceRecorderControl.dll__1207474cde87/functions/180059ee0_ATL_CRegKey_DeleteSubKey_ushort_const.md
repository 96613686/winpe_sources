# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180059ee0`
- end: `0x180059f9f`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `191`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18005cacc`

## callees

- `0x180059ee0`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180059f0f`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180059f0f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180059f24`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180059f51`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180059f24`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180059f51`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180059f3c`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180059f3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059f8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059f8d`

## string_xrefs

- `0x180059f08`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180059f1a`: `RegDeleteKeyExW`
- `0x180059f35`: `advapi32.dll`
- `0x180059f47`: `RegDeleteKeyW`

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
0x180059ee0  push    rdi
0x180059ee2  sub     rsp, 40h
0x180059ee6  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x180059eef  mov     [rsp+48h+arg_0], rbx
0x180059ef4  mov     rdi, rdx
0x180059ef7  mov     rbx, rcx
0x180059efa  cmp     qword ptr [rcx+8], 0
0x180059eff  jnz     short loc_180059F5B
0x180059f01  cmp     qword ptr [rcx+10h], 0
0x180059f06  jnz     short loc_180059F5B
0x180059f08  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180059f0f  call    cs:__imp_GetModuleHandleW
0x180059f15  test    rax, rax
0x180059f18  jz      short loc_180059F30
0x180059f1a  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180059f21  mov     rcx, rax; hModule
0x180059f24  call    cs:__imp_GetProcAddress
0x180059f2a  mov     [rbx+8], rax
0x180059f2e  jmp     short loc_180059F5B
0x180059f30  xor     r8d, r8d; dwFlags
0x180059f33  xor     edx, edx; hFile
0x180059f35  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x180059f3c  call    cs:__imp_LoadLibraryExW
0x180059f42  test    rax, rax
0x180059f45  jz      short loc_180059F5B
0x180059f47  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180059f4e  mov     rcx, rax; hModule
0x180059f51  call    cs:__imp_GetProcAddress
0x180059f57  mov     [rbx+10h], rax
0x180059f5b  mov     rax, [rbx+8]
0x180059f5f  test    rax, rax
0x180059f62  jz      short loc_180059F77
0x180059f64  xor     r9d, r9d
0x180059f67  xor     r8d, r8d
0x180059f6a  mov     rdx, rdi
0x180059f6d  mov     rcx, [rbx]
0x180059f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f75  jmp     short loc_180059F94
0x180059f77  mov     rax, [rbx+10h]
0x180059f7b  test    rax, rax
0x180059f7e  jz      short loc_180059F8D
0x180059f80  mov     rdx, rdi
0x180059f83  mov     rcx, [rbx]
0x180059f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f8b  jmp     short loc_180059F94
0x180059f8d  call    cs:__imp_GetLastError
0x180059f93  nop
0x180059f94  mov     rbx, [rsp+48h+arg_0]
0x180059f99  add     rsp, 40h
0x180059f9d  pop     rdi
0x180059f9e  retn
```
