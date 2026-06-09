# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180003640`
- end: `0x1800036f4`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180002ebc`
- `0x180003d58`
- `0x1800041fc`

## callees

- `0x180003640`
- `0x180007010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180003692`
- `KERNEL32!LoadLibraryExW` at `0x180003692`
- `KERNEL32!GetModuleHandleW` at `0x180003665`
- `KERNEL32!GetModuleHandleW` at `0x180003665`
- `KERNEL32!GetLastError` at `0x1800036e3`
- `KERNEL32!GetLastError` at `0x1800036e3`
- `KERNEL32!GetProcAddress` at `0x18000367a`
- `KERNEL32!GetProcAddress` at `0x1800036a7`
- `KERNEL32!GetProcAddress` at `0x18000367a`
- `KERNEL32!GetProcAddress` at `0x1800036a7`

## string_xrefs

- `0x18000365e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180003670`: `RegDeleteKeyExW`
- `0x180003689`: `advapi32.dll`
- `0x18000369d`: `RegDeleteKeyW`

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
0x180003640  mov     [rsp+arg_0], rbx
0x180003645  push    rdi
0x180003646  sub     rsp, 30h
0x18000364a  cmp     qword ptr [rcx+8], 0
0x18000364f  mov     rdi, rdx
0x180003652  mov     rbx, rcx
0x180003655  jnz     short loc_1800036B1
0x180003657  cmp     qword ptr [rcx+10h], 0
0x18000365c  jnz     short loc_1800036B1
0x18000365e  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180003665  call    cs:__imp_GetModuleHandleW
0x18000366b  test    rax, rax
0x18000366e  jz      short loc_180003686
0x180003670  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180003677  mov     rcx, rax; hModule
0x18000367a  call    cs:__imp_GetProcAddress
0x180003680  mov     [rbx+8], rax
0x180003684  jmp     short loc_1800036B1
0x180003686  xor     r8d, r8d; dwFlags
0x180003689  lea     rcx, LibFileName; "advapi32.dll"
0x180003690  xor     edx, edx; hFile
0x180003692  call    cs:__imp_LoadLibraryExW
0x180003698  test    rax, rax
0x18000369b  jz      short loc_1800036B1
0x18000369d  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800036a4  mov     rcx, rax; hModule
0x1800036a7  call    cs:__imp_GetProcAddress
0x1800036ad  mov     [rbx+10h], rax
0x1800036b1  mov     rax, [rbx+8]
0x1800036b5  test    rax, rax
0x1800036b8  jz      short loc_1800036CD
0x1800036ba  mov     rcx, [rbx]
0x1800036bd  xor     r9d, r9d
0x1800036c0  xor     r8d, r8d
0x1800036c3  mov     rdx, rdi
0x1800036c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036cb  jmp     short loc_1800036E9
0x1800036cd  mov     rax, [rbx+10h]
0x1800036d1  test    rax, rax
0x1800036d4  jz      short loc_1800036E3
0x1800036d6  mov     rcx, [rbx]
0x1800036d9  mov     rdx, rdi
0x1800036dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036e1  jmp     short loc_1800036E9
0x1800036e3  call    cs:__imp_GetLastError
0x1800036e9  mov     rbx, [rsp+38h+arg_0]
0x1800036ee  add     rsp, 30h
0x1800036f2  pop     rdi
0x1800036f3  retn
```
