# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x140005dc0`
- end: `0x140005e75`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14000931c`
- `0x140009754`
- `0x14000ceb4`

## callees

- `0x140005dc0`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140005e63`
- `KERNEL32!GetLastError` at `0x140005e63`
- `KERNEL32!GetProcAddress` at `0x140005dfa`
- `KERNEL32!GetProcAddress` at `0x140005e27`
- `KERNEL32!GetProcAddress` at `0x140005dfa`
- `KERNEL32!GetProcAddress` at `0x140005e27`
- `KERNEL32!GetModuleHandleW` at `0x140005de5`
- `KERNEL32!GetModuleHandleW` at `0x140005de5`
- `KERNEL32!LoadLibraryExW` at `0x140005e12`
- `KERNEL32!LoadLibraryExW` at `0x140005e12`

## string_xrefs

- `0x140005dde`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x140005df0`: `RegDeleteKeyExW`
- `0x140005e0b`: `advapi32.dll`
- `0x140005e1d`: `RegDeleteKeyW`

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
0x140005dc0  mov     [rsp+arg_0], rbx
0x140005dc5  push    rdi
0x140005dc6  sub     rsp, 30h
0x140005dca  mov     rdi, rdx
0x140005dcd  mov     rbx, rcx
0x140005dd0  cmp     qword ptr [rcx+8], 0
0x140005dd5  jnz     short loc_140005E31
0x140005dd7  cmp     qword ptr [rcx+10h], 0
0x140005ddc  jnz     short loc_140005E31
0x140005dde  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x140005de5  call    cs:__imp_GetModuleHandleW
0x140005deb  test    rax, rax
0x140005dee  jz      short loc_140005E06
0x140005df0  lea     rdx, ProcName; "RegDeleteKeyExW"
0x140005df7  mov     rcx, rax; hModule
0x140005dfa  call    cs:__imp_GetProcAddress
0x140005e00  mov     [rbx+8], rax
0x140005e04  jmp     short loc_140005E31
0x140005e06  xor     r8d, r8d; dwFlags
0x140005e09  xor     edx, edx; hFile
0x140005e0b  lea     rcx, LibFileName; "advapi32.dll"
0x140005e12  call    cs:__imp_LoadLibraryExW
0x140005e18  test    rax, rax
0x140005e1b  jz      short loc_140005E31
0x140005e1d  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x140005e24  mov     rcx, rax; hModule
0x140005e27  call    cs:__imp_GetProcAddress
0x140005e2d  mov     [rbx+10h], rax
0x140005e31  mov     rax, [rbx+8]
0x140005e35  test    rax, rax
0x140005e38  jz      short loc_140005E4D
0x140005e3a  xor     r9d, r9d
0x140005e3d  xor     r8d, r8d
0x140005e40  mov     rdx, rdi
0x140005e43  mov     rcx, [rbx]
0x140005e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e4b  jmp     short loc_140005E6A
0x140005e4d  mov     rax, [rbx+10h]
0x140005e51  test    rax, rax
0x140005e54  jz      short loc_140005E63
0x140005e56  mov     rdx, rdi
0x140005e59  mov     rcx, [rbx]
0x140005e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e61  jmp     short loc_140005E6A
0x140005e63  call    cs:__imp_GetLastError
0x140005e69  nop
0x140005e6a  mov     rbx, [rsp+38h+arg_0]
0x140005e6f  add     rsp, 30h
0x140005e73  pop     rdi
0x140005e74  retn
```
