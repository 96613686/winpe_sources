# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180004d78`
- end: `0x180004e2d`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000738c`
- `0x18000784c`
- `0x1800093f8`

## callees

- `0x180004d78`
- `0x180012010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004e1b`
- `KERNEL32!GetLastError` at `0x180004e1b`
- `KERNEL32!GetProcAddress` at `0x180004db2`
- `KERNEL32!GetProcAddress` at `0x180004ddf`
- `KERNEL32!GetProcAddress` at `0x180004db2`
- `KERNEL32!GetProcAddress` at `0x180004ddf`
- `KERNEL32!LoadLibraryExW` at `0x180004dca`
- `KERNEL32!LoadLibraryExW` at `0x180004dca`
- `KERNEL32!GetModuleHandleW` at `0x180004d9d`
- `KERNEL32!GetModuleHandleW` at `0x180004d9d`

## string_xrefs

- `0x180004d96`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180004da8`: `RegDeleteKeyExW`
- `0x180004dc3`: `advapi32.dll`
- `0x180004dd5`: `RegDeleteKeyW`

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
0x180004d78  mov     [rsp+arg_0], rbx
0x180004d7d  push    rdi
0x180004d7e  sub     rsp, 30h
0x180004d82  mov     rdi, rdx
0x180004d85  mov     rbx, rcx
0x180004d88  cmp     qword ptr [rcx+8], 0
0x180004d8d  jnz     short loc_180004DE9
0x180004d8f  cmp     qword ptr [rcx+10h], 0
0x180004d94  jnz     short loc_180004DE9
0x180004d96  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180004d9d  call    cs:__imp_GetModuleHandleW
0x180004da3  test    rax, rax
0x180004da6  jz      short loc_180004DBE
0x180004da8  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180004daf  mov     rcx, rax; hModule
0x180004db2  call    cs:__imp_GetProcAddress
0x180004db8  mov     [rbx+8], rax
0x180004dbc  jmp     short loc_180004DE9
0x180004dbe  xor     r8d, r8d; dwFlags
0x180004dc1  xor     edx, edx; hFile
0x180004dc3  lea     rcx, LibFileName; "advapi32.dll"
0x180004dca  call    cs:__imp_LoadLibraryExW
0x180004dd0  test    rax, rax
0x180004dd3  jz      short loc_180004DE9
0x180004dd5  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180004ddc  mov     rcx, rax; hModule
0x180004ddf  call    cs:__imp_GetProcAddress
0x180004de5  mov     [rbx+10h], rax
0x180004de9  mov     rax, [rbx+8]
0x180004ded  test    rax, rax
0x180004df0  jz      short loc_180004E05
0x180004df2  xor     r9d, r9d
0x180004df5  xor     r8d, r8d
0x180004df8  mov     rdx, rdi
0x180004dfb  mov     rcx, [rbx]
0x180004dfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e03  jmp     short loc_180004E22
0x180004e05  mov     rax, [rbx+10h]
0x180004e09  test    rax, rax
0x180004e0c  jz      short loc_180004E1B
0x180004e0e  mov     rdx, rdi
0x180004e11  mov     rcx, [rbx]
0x180004e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e19  jmp     short loc_180004E22
0x180004e1b  call    cs:__imp_GetLastError
0x180004e21  nop
0x180004e22  mov     rbx, [rsp+38h+arg_0]
0x180004e27  add     rsp, 30h
0x180004e2b  pop     rdi
0x180004e2c  retn
```
