# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800098fc`
- end: `0x1800099bb`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `191`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800070b0`
- `0x18000b2f0`
- `0x18000b7ec`

## callees

- `0x1800098fc`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000992b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000992b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180009958`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180009958`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009940`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000996d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009940`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000996d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099a9`

## string_xrefs

- `0x180009924`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180009936`: `RegDeleteKeyExW`
- `0x180009963`: `RegDeleteKeyW`
- `0x180009951`: `advapi32.dll`

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
0x1800098fc  push    rdi
0x1800098fe  sub     rsp, 40h
0x180009902  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000990b  mov     [rsp+48h+arg_0], rbx
0x180009910  mov     rdi, rdx
0x180009913  mov     rbx, rcx
0x180009916  cmp     qword ptr [rcx+8], 0
0x18000991b  jnz     short loc_180009977
0x18000991d  cmp     qword ptr [rcx+10h], 0
0x180009922  jnz     short loc_180009977
0x180009924  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000992b  call    cs:__imp_GetModuleHandleW
0x180009931  test    rax, rax
0x180009934  jz      short loc_18000994C
0x180009936  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18000993d  mov     rcx, rax; hModule
0x180009940  call    cs:__imp_GetProcAddress
0x180009946  mov     [rbx+8], rax
0x18000994a  jmp     short loc_180009977
0x18000994c  xor     r8d, r8d; dwFlags
0x18000994f  xor     edx, edx; hFile
0x180009951  lea     rcx, LibFileName; "advapi32.dll"
0x180009958  call    cs:__imp_LoadLibraryExW
0x18000995e  test    rax, rax
0x180009961  jz      short loc_180009977
0x180009963  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000996a  mov     rcx, rax; hModule
0x18000996d  call    cs:__imp_GetProcAddress
0x180009973  mov     [rbx+10h], rax
0x180009977  mov     rax, [rbx+8]
0x18000997b  test    rax, rax
0x18000997e  jz      short loc_180009993
0x180009980  xor     r9d, r9d
0x180009983  xor     r8d, r8d
0x180009986  mov     rdx, rdi
0x180009989  mov     rcx, [rbx]
0x18000998c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009991  jmp     short loc_1800099B0
0x180009993  mov     rax, [rbx+10h]
0x180009997  test    rax, rax
0x18000999a  jz      short loc_1800099A9
0x18000999c  mov     rdx, rdi
0x18000999f  mov     rcx, [rbx]
0x1800099a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099a7  jmp     short loc_1800099B0
0x1800099a9  call    cs:__imp_GetLastError
0x1800099af  nop
0x1800099b0  mov     rbx, [rsp+48h+arg_0]
0x1800099b5  add     rsp, 40h
0x1800099b9  pop     rdi
0x1800099ba  retn
```
