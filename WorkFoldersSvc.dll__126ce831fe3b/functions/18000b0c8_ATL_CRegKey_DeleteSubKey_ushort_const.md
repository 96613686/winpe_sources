# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18000b0c8`
- end: `0x18000b17d`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e638`
- `0x18000ec40`

## callees

- `0x18000b0c8`
- `0x18013e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000b102`
- `KERNEL32!GetProcAddress` at `0x18000b12f`
- `KERNEL32!GetProcAddress` at `0x18000b102`
- `KERNEL32!GetProcAddress` at `0x18000b12f`
- `KERNEL32!LoadLibraryExW` at `0x18000b11a`
- `KERNEL32!LoadLibraryExW` at `0x18000b11a`
- `KERNEL32!GetLastError` at `0x18000b16b`
- `KERNEL32!GetLastError` at `0x18000b16b`
- `KERNEL32!GetModuleHandleW` at `0x18000b0ed`
- `KERNEL32!GetModuleHandleW` at `0x18000b0ed`

## string_xrefs

- `0x18000b0e6`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000b0f8`: `RegDeleteKeyExW`
- `0x18000b113`: `advapi32.dll`
- `0x18000b125`: `RegDeleteKeyW`

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
0x18000b0c8  mov     [rsp+arg_0], rbx
0x18000b0cd  push    rdi
0x18000b0ce  sub     rsp, 30h
0x18000b0d2  mov     rdi, rdx
0x18000b0d5  mov     rbx, rcx
0x18000b0d8  cmp     qword ptr [rcx+8], 0
0x18000b0dd  jnz     short loc_18000B139
0x18000b0df  cmp     qword ptr [rcx+10h], 0
0x18000b0e4  jnz     short loc_18000B139
0x18000b0e6  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000b0ed  call    cs:__imp_GetModuleHandleW
0x18000b0f3  test    rax, rax
0x18000b0f6  jz      short loc_18000B10E
0x18000b0f8  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18000b0ff  mov     rcx, rax; hModule
0x18000b102  call    cs:__imp_GetProcAddress
0x18000b108  mov     [rbx+8], rax
0x18000b10c  jmp     short loc_18000B139
0x18000b10e  xor     r8d, r8d; dwFlags
0x18000b111  xor     edx, edx; hFile
0x18000b113  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x18000b11a  call    cs:__imp_LoadLibraryExW
0x18000b120  test    rax, rax
0x18000b123  jz      short loc_18000B139
0x18000b125  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000b12c  mov     rcx, rax; hModule
0x18000b12f  call    cs:__imp_GetProcAddress
0x18000b135  mov     [rbx+10h], rax
0x18000b139  mov     rax, [rbx+8]
0x18000b13d  test    rax, rax
0x18000b140  jz      short loc_18000B155
0x18000b142  xor     r9d, r9d
0x18000b145  xor     r8d, r8d
0x18000b148  mov     rdx, rdi
0x18000b14b  mov     rcx, [rbx]
0x18000b14e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b153  jmp     short loc_18000B172
0x18000b155  mov     rax, [rbx+10h]
0x18000b159  test    rax, rax
0x18000b15c  jz      short loc_18000B16B
0x18000b15e  mov     rdx, rdi
0x18000b161  mov     rcx, [rbx]
0x18000b164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b169  jmp     short loc_18000B172
0x18000b16b  call    cs:__imp_GetLastError
0x18000b171  nop
0x18000b172  mov     rbx, [rsp+38h+arg_0]
0x18000b177  add     rsp, 30h
0x18000b17b  pop     rdi
0x18000b17c  retn
```
