# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180014148`
- end: `0x1800141fd`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800133d8`
- `0x18001597c`
- `0x180015e40`

## callees

- `0x180014148`
- `0x180035010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800141eb`
- `KERNEL32!GetLastError` at `0x1800141eb`
- `KERNEL32!GetProcAddress` at `0x180014182`
- `KERNEL32!GetProcAddress` at `0x1800141af`
- `KERNEL32!GetProcAddress` at `0x180014182`
- `KERNEL32!GetProcAddress` at `0x1800141af`
- `KERNEL32!LoadLibraryExW` at `0x18001419a`
- `KERNEL32!LoadLibraryExW` at `0x18001419a`
- `KERNEL32!GetModuleHandleW` at `0x18001416d`
- `KERNEL32!GetModuleHandleW` at `0x18001416d`

## string_xrefs

- `0x180014166`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180014178`: `RegDeleteKeyExW`
- `0x180014193`: `advapi32.dll`
- `0x1800141a5`: `RegDeleteKeyW`

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
0x180014148  mov     [rsp+arg_0], rbx
0x18001414d  push    rdi
0x18001414e  sub     rsp, 30h
0x180014152  mov     rdi, rdx
0x180014155  mov     rbx, rcx
0x180014158  cmp     qword ptr [rcx+8], 0
0x18001415d  jnz     short loc_1800141B9
0x18001415f  cmp     qword ptr [rcx+10h], 0
0x180014164  jnz     short loc_1800141B9
0x180014166  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18001416d  call    cs:__imp_GetModuleHandleW
0x180014173  test    rax, rax
0x180014176  jz      short loc_18001418E
0x180014178  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18001417f  mov     rcx, rax; hModule
0x180014182  call    cs:__imp_GetProcAddress
0x180014188  mov     [rbx+8], rax
0x18001418c  jmp     short loc_1800141B9
0x18001418e  xor     r8d, r8d; dwFlags
0x180014191  xor     edx, edx; hFile
0x180014193  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x18001419a  call    cs:__imp_LoadLibraryExW
0x1800141a0  test    rax, rax
0x1800141a3  jz      short loc_1800141B9
0x1800141a5  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800141ac  mov     rcx, rax; hModule
0x1800141af  call    cs:__imp_GetProcAddress
0x1800141b5  mov     [rbx+10h], rax
0x1800141b9  mov     rax, [rbx+8]
0x1800141bd  test    rax, rax
0x1800141c0  jz      short loc_1800141D5
0x1800141c2  xor     r9d, r9d
0x1800141c5  xor     r8d, r8d
0x1800141c8  mov     rdx, rdi
0x1800141cb  mov     rcx, [rbx]
0x1800141ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141d3  jmp     short loc_1800141F2
0x1800141d5  mov     rax, [rbx+10h]
0x1800141d9  test    rax, rax
0x1800141dc  jz      short loc_1800141EB
0x1800141de  mov     rdx, rdi
0x1800141e1  mov     rcx, [rbx]
0x1800141e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141e9  jmp     short loc_1800141F2
0x1800141eb  call    cs:__imp_GetLastError
0x1800141f1  nop
0x1800141f2  mov     rbx, [rsp+38h+arg_0]
0x1800141f7  add     rsp, 30h
0x1800141fb  pop     rdi
0x1800141fc  retn
```
