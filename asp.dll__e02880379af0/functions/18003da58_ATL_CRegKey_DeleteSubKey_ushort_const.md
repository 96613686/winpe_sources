# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18003da58`
- end: `0x18003db0c`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18003ebd8`
- `0x18003f008`

## callees

- `0x18003da58`
- `0x180064010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18003da7d`
- `KERNEL32!GetModuleHandleW` at `0x18003da7d`
- `KERNEL32!LoadLibraryExW` at `0x18003daaa`
- `KERNEL32!LoadLibraryExW` at `0x18003daaa`
- `KERNEL32!GetProcAddress` at `0x18003da92`
- `KERNEL32!GetProcAddress` at `0x18003dabf`
- `KERNEL32!GetProcAddress` at `0x18003da92`
- `KERNEL32!GetProcAddress` at `0x18003dabf`
- `KERNEL32!GetLastError` at `0x18003dafb`
- `KERNEL32!GetLastError` at `0x18003dafb`

## string_xrefs

- `0x18003da76`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18003da88`: `RegDeleteKeyExW`
- `0x18003daa1`: `advapi32.dll`
- `0x18003dab5`: `RegDeleteKeyW`

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
0x18003da58  mov     [rsp+arg_0], rbx
0x18003da5d  push    rdi
0x18003da5e  sub     rsp, 30h
0x18003da62  cmp     qword ptr [rcx+8], 0
0x18003da67  mov     rdi, rdx
0x18003da6a  mov     rbx, rcx
0x18003da6d  jnz     short loc_18003DAC9
0x18003da6f  cmp     qword ptr [rcx+10h], 0
0x18003da74  jnz     short loc_18003DAC9
0x18003da76  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18003da7d  call    cs:__imp_GetModuleHandleW
0x18003da83  test    rax, rax
0x18003da86  jz      short loc_18003DA9E
0x18003da88  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18003da8f  mov     rcx, rax; hModule
0x18003da92  call    cs:__imp_GetProcAddress
0x18003da98  mov     [rbx+8], rax
0x18003da9c  jmp     short loc_18003DAC9
0x18003da9e  xor     r8d, r8d; dwFlags
0x18003daa1  lea     rcx, LibFileName; "advapi32.dll"
0x18003daa8  xor     edx, edx; hFile
0x18003daaa  call    cs:__imp_LoadLibraryExW
0x18003dab0  test    rax, rax
0x18003dab3  jz      short loc_18003DAC9
0x18003dab5  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18003dabc  mov     rcx, rax; hModule
0x18003dabf  call    cs:__imp_GetProcAddress
0x18003dac5  mov     [rbx+10h], rax
0x18003dac9  mov     rax, [rbx+8]
0x18003dacd  test    rax, rax
0x18003dad0  jz      short loc_18003DAE5
0x18003dad2  mov     rcx, [rbx]
0x18003dad5  xor     r9d, r9d
0x18003dad8  xor     r8d, r8d
0x18003dadb  mov     rdx, rdi
0x18003dade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dae3  jmp     short loc_18003DB01
0x18003dae5  mov     rax, [rbx+10h]
0x18003dae9  test    rax, rax
0x18003daec  jz      short loc_18003DAFB
0x18003daee  mov     rcx, [rbx]
0x18003daf1  mov     rdx, rdi
0x18003daf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003daf9  jmp     short loc_18003DB01
0x18003dafb  call    cs:__imp_GetLastError
0x18003db01  mov     rbx, [rsp+38h+arg_0]
0x18003db06  add     rsp, 30h
0x18003db0a  pop     rdi
0x18003db0b  retn
```
