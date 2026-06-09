# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180008894`
- end: `0x180008949`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180004fb8`
- `0x180008d88`

## callees

- `0x180008894`
- `0x18000c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008937`
- `KERNEL32!GetLastError` at `0x180008937`
- `KERNEL32!GetProcAddress` at `0x1800088ce`
- `KERNEL32!GetProcAddress` at `0x1800088fb`
- `KERNEL32!GetProcAddress` at `0x1800088ce`
- `KERNEL32!GetProcAddress` at `0x1800088fb`
- `KERNEL32!GetModuleHandleW` at `0x1800088b9`
- `KERNEL32!GetModuleHandleW` at `0x1800088b9`
- `KERNEL32!LoadLibraryExW` at `0x1800088e6`
- `KERNEL32!LoadLibraryExW` at `0x1800088e6`

## string_xrefs

- `0x1800088b2`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800088c4`: `RegDeleteKeyExW`
- `0x1800088df`: `advapi32.dll`
- `0x1800088f1`: `RegDeleteKeyW`

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
0x180008894  mov     [rsp+arg_0], rbx
0x180008899  push    rdi
0x18000889a  sub     rsp, 30h
0x18000889e  mov     rdi, rdx
0x1800088a1  mov     rbx, rcx
0x1800088a4  cmp     qword ptr [rcx+8], 0
0x1800088a9  jnz     short loc_180008905
0x1800088ab  cmp     qword ptr [rcx+10h], 0
0x1800088b0  jnz     short loc_180008905
0x1800088b2  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800088b9  call    cs:__imp_GetModuleHandleW
0x1800088bf  test    rax, rax
0x1800088c2  jz      short loc_1800088DA
0x1800088c4  lea     rdx, ProcName; "RegDeleteKeyExW"
0x1800088cb  mov     rcx, rax; hModule
0x1800088ce  call    cs:__imp_GetProcAddress
0x1800088d4  mov     [rbx+8], rax
0x1800088d8  jmp     short loc_180008905
0x1800088da  xor     r8d, r8d; dwFlags
0x1800088dd  xor     edx, edx; hFile
0x1800088df  lea     rcx, LibFileName; "advapi32.dll"
0x1800088e6  call    cs:__imp_LoadLibraryExW
0x1800088ec  test    rax, rax
0x1800088ef  jz      short loc_180008905
0x1800088f1  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800088f8  mov     rcx, rax; hModule
0x1800088fb  call    cs:__imp_GetProcAddress
0x180008901  mov     [rbx+10h], rax
0x180008905  mov     rax, [rbx+8]
0x180008909  test    rax, rax
0x18000890c  jz      short loc_180008921
0x18000890e  xor     r9d, r9d
0x180008911  xor     r8d, r8d
0x180008914  mov     rdx, rdi
0x180008917  mov     rcx, [rbx]
0x18000891a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000891f  jmp     short loc_18000893E
0x180008921  mov     rax, [rbx+10h]
0x180008925  test    rax, rax
0x180008928  jz      short loc_180008937
0x18000892a  mov     rdx, rdi
0x18000892d  mov     rcx, [rbx]
0x180008930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008935  jmp     short loc_18000893E
0x180008937  call    cs:__imp_GetLastError
0x18000893d  nop
0x18000893e  mov     rbx, [rsp+38h+arg_0]
0x180008943  add     rsp, 30h
0x180008947  pop     rdi
0x180008948  retn
```
