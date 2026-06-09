# ATL::CRegKey::DeleteSubKey(char const *)

- ea: `0x180003de8`
- end: `0x180003e9d`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBD@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const char *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180004df8`
- `0x180005408`

## callees

- `0x180003de8`
- `0x18000d010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003e8b`
- `KERNEL32!GetLastError` at `0x180003e8b`
- `KERNEL32!GetProcAddress` at `0x180003e22`
- `KERNEL32!GetProcAddress` at `0x180003e4f`
- `KERNEL32!GetProcAddress` at `0x180003e22`
- `KERNEL32!GetProcAddress` at `0x180003e4f`
- `KERNEL32!LoadLibraryExA` at `0x180003e3a`
- `KERNEL32!LoadLibraryExA` at `0x180003e3a`
- `KERNEL32!GetModuleHandleA` at `0x180003e0d`
- `KERNEL32!GetModuleHandleA` at `0x180003e0d`

## string_xrefs

- `0x180003e06`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180003e18`: `RegDeleteKeyExA`
- `0x180003e33`: `advapi32.dll`
- `0x180003e45`: `RegDeleteKeyA`

## pseudocode

```c
DWORD __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const char *a2)
{
  HMODULE ModuleHandleA; // rax
  HMODULE Library; // rax
  __int64 (__fastcall *v6)(_QWORD, const char *, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v8)(_QWORD, const char *); // rax

  if ( *(_OWORD *)((char *)this + 8) == 0 )
  {
    ModuleHandleA = GetModuleHandleA("API-MS-Win-Core-LocalRegistry-L1-1-0.dll");
    if ( ModuleHandleA )
    {
      *((_QWORD *)this + 1) = GetProcAddress(ModuleHandleA, "RegDeleteKeyExA");
    }
    else
    {
      Library = LoadLibraryExA("advapi32.dll", 0, 0);
      if ( Library )
        *((_QWORD *)this + 2) = GetProcAddress(Library, "RegDeleteKeyA");
    }
  }
  v6 = (__int64 (__fastcall *)(_QWORD, const char *, _QWORD, _QWORD))*((_QWORD *)this + 1);
  if ( v6 )
    return v6(*(_QWORD *)this, a2, 0, 0);
  v8 = (__int64 (__fastcall *)(_QWORD, const char *))*((_QWORD *)this + 2);
  if ( v8 )
    return v8(*(_QWORD *)this, a2);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180003de8  mov     [rsp+arg_0], rbx
0x180003ded  push    rdi
0x180003dee  sub     rsp, 30h
0x180003df2  mov     rdi, rdx
0x180003df5  mov     rbx, rcx
0x180003df8  cmp     qword ptr [rcx+8], 0
0x180003dfd  jnz     short loc_180003E59
0x180003dff  cmp     qword ptr [rcx+10h], 0
0x180003e04  jnz     short loc_180003E59
0x180003e06  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180003e0d  call    cs:__imp_GetModuleHandleA
0x180003e13  test    rax, rax
0x180003e16  jz      short loc_180003E2E
0x180003e18  lea     rdx, ProcName; "RegDeleteKeyExA"
0x180003e1f  mov     rcx, rax; hModule
0x180003e22  call    cs:__imp_GetProcAddress
0x180003e28  mov     [rbx+8], rax
0x180003e2c  jmp     short loc_180003E59
0x180003e2e  xor     r8d, r8d; dwFlags
0x180003e31  xor     edx, edx; hFile
0x180003e33  lea     rcx, LibFileName; "advapi32.dll"
0x180003e3a  call    cs:__imp_LoadLibraryExA
0x180003e40  test    rax, rax
0x180003e43  jz      short loc_180003E59
0x180003e45  lea     rdx, aRegdeletekeya; "RegDeleteKeyA"
0x180003e4c  mov     rcx, rax; hModule
0x180003e4f  call    cs:__imp_GetProcAddress
0x180003e55  mov     [rbx+10h], rax
0x180003e59  mov     rax, [rbx+8]
0x180003e5d  test    rax, rax
0x180003e60  jz      short loc_180003E75
0x180003e62  xor     r9d, r9d
0x180003e65  xor     r8d, r8d
0x180003e68  mov     rdx, rdi
0x180003e6b  mov     rcx, [rbx]
0x180003e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e73  jmp     short loc_180003E92
0x180003e75  mov     rax, [rbx+10h]
0x180003e79  test    rax, rax
0x180003e7c  jz      short loc_180003E8B
0x180003e7e  mov     rdx, rdi
0x180003e81  mov     rcx, [rbx]
0x180003e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e89  jmp     short loc_180003E92
0x180003e8b  call    cs:__imp_GetLastError
0x180003e91  nop
0x180003e92  mov     rbx, [rsp+38h+arg_0]
0x180003e97  add     rsp, 30h
0x180003e9b  pop     rdi
0x180003e9c  retn
```
