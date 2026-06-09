# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180004998`
- end: `0x180004a4a`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `178`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180003c7c`
- `0x1800052a8`
- `0x180005764`

## callees

- `0x180004998`
- `0x180006d3c`
- `0x18000c010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800049bd`
- `KERNEL32!GetModuleHandleW` at `0x1800049bd`
- `KERNEL32!GetProcAddress` at `0x1800049d2`
- `KERNEL32!GetProcAddress` at `0x1800049fc`
- `KERNEL32!GetProcAddress` at `0x1800049d2`
- `KERNEL32!GetProcAddress` at `0x1800049fc`
- `KERNEL32!GetLastError` at `0x180004a38`
- `KERNEL32!GetLastError` at `0x180004a38`

## string_xrefs

- `0x1800049b6`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800049c8`: `RegDeleteKeyExW`
- `0x1800049e1`: `advapi32.dll`
- `0x1800049f2`: `RegDeleteKeyW`

## pseudocode

```c
DWORD __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const unsigned __int16 *a2)
{
  HMODULE ModuleHandleW; // rax
  __int64 v5; // rdx
  HMODULE Library; // rax
  __int64 (__fastcall *v7)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v9)(_QWORD, const unsigned __int16 *); // rax

  if ( *(_OWORD *)((char *)this + 8) == 0 )
  {
    ModuleHandleW = GetModuleHandleW(L"API-MS-Win-Core-LocalRegistry-L1-1-0.dll");
    if ( ModuleHandleW )
    {
      *((_QWORD *)this + 1) = GetProcAddress(ModuleHandleW, "RegDeleteKeyExW");
    }
    else
    {
      Library = IsolationAwareLoadLibraryExW(L"advapi32.dll", v5, 0);
      if ( Library )
        *((_QWORD *)this + 2) = GetProcAddress(Library, "RegDeleteKeyW");
    }
  }
  v7 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD))*((_QWORD *)this + 1);
  if ( v7 )
    return v7(*(_QWORD *)this, a2, 0, 0);
  v9 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *))*((_QWORD *)this + 2);
  if ( v9 )
    return v9(*(_QWORD *)this, a2);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180004998  mov     [rsp+arg_0], rbx
0x18000499d  push    rdi
0x18000499e  sub     rsp, 30h
0x1800049a2  mov     rdi, rdx
0x1800049a5  mov     rbx, rcx
0x1800049a8  cmp     qword ptr [rcx+8], 0
0x1800049ad  jnz     short loc_180004A06
0x1800049af  cmp     qword ptr [rcx+10h], 0
0x1800049b4  jnz     short loc_180004A06
0x1800049b6  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800049bd  call    cs:__imp_GetModuleHandleW
0x1800049c3  test    rax, rax
0x1800049c6  jz      short loc_1800049DE
0x1800049c8  lea     rdx, ProcName; "RegDeleteKeyExW"
0x1800049cf  mov     rcx, rax; hModule
0x1800049d2  call    cs:__imp_GetProcAddress
0x1800049d8  mov     [rbx+8], rax
0x1800049dc  jmp     short loc_180004A06
0x1800049de  xor     r8d, r8d
0x1800049e1  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x1800049e8  call    IsolationAwareLoadLibraryExW
0x1800049ed  test    rax, rax
0x1800049f0  jz      short loc_180004A06
0x1800049f2  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800049f9  mov     rcx, rax; hModule
0x1800049fc  call    cs:__imp_GetProcAddress
0x180004a02  mov     [rbx+10h], rax
0x180004a06  mov     rax, [rbx+8]
0x180004a0a  test    rax, rax
0x180004a0d  jz      short loc_180004A22
0x180004a0f  xor     r9d, r9d
0x180004a12  xor     r8d, r8d
0x180004a15  mov     rdx, rdi
0x180004a18  mov     rcx, [rbx]
0x180004a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a20  jmp     short loc_180004A3F
0x180004a22  mov     rax, [rbx+10h]
0x180004a26  test    rax, rax
0x180004a29  jz      short loc_180004A38
0x180004a2b  mov     rdx, rdi
0x180004a2e  mov     rcx, [rbx]
0x180004a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a36  jmp     short loc_180004A3F
0x180004a38  call    cs:__imp_GetLastError
0x180004a3e  nop
0x180004a3f  mov     rbx, [rsp+38h+arg_0]
0x180004a44  add     rsp, 30h
0x180004a48  pop     rdi
0x180004a49  retn
```
