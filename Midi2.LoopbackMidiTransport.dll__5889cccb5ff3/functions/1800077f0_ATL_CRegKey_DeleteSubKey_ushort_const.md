# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800077f0`
- end: `0x1800078a5`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000902c`
- `0x1800094ec`
- `0x18000c6b0`

## callees

- `0x1800077f0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007842`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007842`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007815`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007815`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000782a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007857`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000782a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007893`

## string_xrefs

- `0x18000780e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180007820`: `RegDeleteKeyExW`
- `0x18000783b`: `advapi32.dll`
- `0x18000784d`: `RegDeleteKeyW`

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
0x1800077f0  mov     [rsp+arg_0], rbx
0x1800077f5  push    rdi
0x1800077f6  sub     rsp, 30h
0x1800077fa  mov     rdi, rdx
0x1800077fd  mov     rbx, rcx
0x180007800  cmp     qword ptr [rcx+8], 0
0x180007805  jnz     short loc_180007861
0x180007807  cmp     qword ptr [rcx+10h], 0
0x18000780c  jnz     short loc_180007861
0x18000780e  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180007815  call    cs:__imp_GetModuleHandleW
0x18000781b  test    rax, rax
0x18000781e  jz      short loc_180007836
0x180007820  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180007827  mov     rcx, rax; hModule
0x18000782a  call    cs:__imp_GetProcAddress
0x180007830  mov     [rbx+8], rax
0x180007834  jmp     short loc_180007861
0x180007836  xor     r8d, r8d; dwFlags
0x180007839  xor     edx, edx; hFile
0x18000783b  lea     rcx, LibFileName; "advapi32.dll"
0x180007842  call    cs:__imp_LoadLibraryExW
0x180007848  test    rax, rax
0x18000784b  jz      short loc_180007861
0x18000784d  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180007854  mov     rcx, rax; hModule
0x180007857  call    cs:__imp_GetProcAddress
0x18000785d  mov     [rbx+10h], rax
0x180007861  mov     rax, [rbx+8]
0x180007865  test    rax, rax
0x180007868  jz      short loc_18000787D
0x18000786a  xor     r9d, r9d
0x18000786d  xor     r8d, r8d
0x180007870  mov     rdx, rdi
0x180007873  mov     rcx, [rbx]
0x180007876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000787b  jmp     short loc_18000789A
0x18000787d  mov     rax, [rbx+10h]
0x180007881  test    rax, rax
0x180007884  jz      short loc_180007893
0x180007886  mov     rdx, rdi
0x180007889  mov     rcx, [rbx]
0x18000788c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007891  jmp     short loc_18000789A
0x180007893  call    cs:__imp_GetLastError
0x180007899  nop
0x18000789a  mov     rbx, [rsp+38h+arg_0]
0x18000789f  add     rsp, 30h
0x1800078a3  pop     rdi
0x1800078a4  retn
```
