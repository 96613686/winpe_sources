# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800055d0`
- end: `0x180005685`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180006e1c`
- `0x1800072dc`
- `0x1800095d0`

## callees

- `0x1800055d0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005622`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005622`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800055f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800055f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000560a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005637`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000560a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005673`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005673`

## string_xrefs

- `0x1800055ee`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180005600`: `RegDeleteKeyExW`
- `0x18000561b`: `advapi32.dll`
- `0x18000562d`: `RegDeleteKeyW`

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
0x1800055d0  mov     [rsp+arg_0], rbx
0x1800055d5  push    rdi
0x1800055d6  sub     rsp, 30h
0x1800055da  mov     rdi, rdx
0x1800055dd  mov     rbx, rcx
0x1800055e0  cmp     qword ptr [rcx+8], 0
0x1800055e5  jnz     short loc_180005641
0x1800055e7  cmp     qword ptr [rcx+10h], 0
0x1800055ec  jnz     short loc_180005641
0x1800055ee  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800055f5  call    cs:__imp_GetModuleHandleW
0x1800055fb  test    rax, rax
0x1800055fe  jz      short loc_180005616
0x180005600  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180005607  mov     rcx, rax; hModule
0x18000560a  call    cs:__imp_GetProcAddress
0x180005610  mov     [rbx+8], rax
0x180005614  jmp     short loc_180005641
0x180005616  xor     r8d, r8d; dwFlags
0x180005619  xor     edx, edx; hFile
0x18000561b  lea     rcx, LibFileName; "advapi32.dll"
0x180005622  call    cs:__imp_LoadLibraryExW
0x180005628  test    rax, rax
0x18000562b  jz      short loc_180005641
0x18000562d  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180005634  mov     rcx, rax; hModule
0x180005637  call    cs:__imp_GetProcAddress
0x18000563d  mov     [rbx+10h], rax
0x180005641  mov     rax, [rbx+8]
0x180005645  test    rax, rax
0x180005648  jz      short loc_18000565D
0x18000564a  xor     r9d, r9d
0x18000564d  xor     r8d, r8d
0x180005650  mov     rdx, rdi
0x180005653  mov     rcx, [rbx]
0x180005656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000565b  jmp     short loc_18000567A
0x18000565d  mov     rax, [rbx+10h]
0x180005661  test    rax, rax
0x180005664  jz      short loc_180005673
0x180005666  mov     rdx, rdi
0x180005669  mov     rcx, [rbx]
0x18000566c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005671  jmp     short loc_18000567A
0x180005673  call    cs:__imp_GetLastError
0x180005679  nop
0x18000567a  mov     rbx, [rsp+38h+arg_0]
0x18000567f  add     rsp, 30h
0x180005683  pop     rdi
0x180005684  retn
```
