# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18002a2ac`
- end: `0x18002a38a`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `222`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180029110`
- `0x18002c74c`
- `0x18002cc74`

## callees

- `0x18002a2ac`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002a2f6`
- `KERNEL32!GetProcAddress` at `0x18002a32f`
- `KERNEL32!GetProcAddress` at `0x18002a2f6`
- `KERNEL32!GetProcAddress` at `0x18002a32f`
- `KERNEL32!GetModuleHandleW` at `0x18002a2db`
- `KERNEL32!GetModuleHandleW` at `0x18002a2db`
- `KERNEL32!GetLastError` at `0x18002a371`
- `KERNEL32!GetLastError` at `0x18002a371`
- `KERNEL32!LoadLibraryExW` at `0x18002a314`
- `KERNEL32!LoadLibraryExW` at `0x18002a314`

## string_xrefs

- `0x18002a30d`: `advapi32.dll`
- `0x18002a2d4`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18002a325`: `RegDeleteKeyW`
- `0x18002a2ec`: `RegDeleteKeyExW`

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
0x18002a2ac  push    rdi
0x18002a2ae  sub     rsp, 40h
0x18002a2b2  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x18002a2bb  mov     [rsp+48h+arg_0], rbx
0x18002a2c0  mov     rdi, rdx
0x18002a2c3  mov     rbx, rcx
0x18002a2c6  cmp     qword ptr [rcx+8], 0
0x18002a2cb  jnz     short loc_18002A33F
0x18002a2cd  cmp     qword ptr [rcx+10h], 0
0x18002a2d2  jnz     short loc_18002A33F
0x18002a2d4  lea     rcx, aApiMsWinCoreLo_1; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18002a2db  call    cs:__imp_GetModuleHandleW
0x18002a2e2  nop     dword ptr [rax+rax+00h]
0x18002a2e7  test    rax, rax
0x18002a2ea  jz      short loc_18002A308
0x18002a2ec  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18002a2f3  mov     rcx, rax; hModule
0x18002a2f6  call    cs:__imp_GetProcAddress
0x18002a2fd  nop     dword ptr [rax+rax+00h]
0x18002a302  mov     [rbx+8], rax
0x18002a306  jmp     short loc_18002A33F
0x18002a308  xor     r8d, r8d; dwFlags
0x18002a30b  xor     edx, edx; hFile
0x18002a30d  lea     rcx, LibFileName; "advapi32.dll"
0x18002a314  call    cs:__imp_LoadLibraryExW
0x18002a31b  nop     dword ptr [rax+rax+00h]
0x18002a320  test    rax, rax
0x18002a323  jz      short loc_18002A33F
0x18002a325  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18002a32c  mov     rcx, rax; hModule
0x18002a32f  call    cs:__imp_GetProcAddress
0x18002a336  nop     dword ptr [rax+rax+00h]
0x18002a33b  mov     [rbx+10h], rax
0x18002a33f  mov     rax, [rbx+8]
0x18002a343  test    rax, rax
0x18002a346  jz      short loc_18002A35B
0x18002a348  xor     r9d, r9d
0x18002a34b  xor     r8d, r8d
0x18002a34e  mov     rdx, rdi
0x18002a351  mov     rcx, [rbx]
0x18002a354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a359  jmp     short loc_18002A37E
0x18002a35b  mov     rax, [rbx+10h]
0x18002a35f  test    rax, rax
0x18002a362  jz      short loc_18002A371
0x18002a364  mov     rdx, rdi
0x18002a367  mov     rcx, [rbx]
0x18002a36a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a36f  jmp     short loc_18002A37E
0x18002a371  call    cs:__imp_GetLastError
0x18002a378  nop     dword ptr [rax+rax+00h]
0x18002a37d  nop
0x18002a37e  mov     rbx, [rsp+48h+arg_0]
0x18002a383  add     rsp, 40h
0x18002a387  pop     rdi
0x18002a388  retn
```
