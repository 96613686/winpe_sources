# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18008cbb0`
- end: `0x18008cc65`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18008c564`
- `0x18009c858`
- `0x18009cc90`

## callees

- `0x18008cbb0`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008cc02`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008cc02`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008cbea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008cc17`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008cbea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008cc17`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18008cbd5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18008cbd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cc53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cc53`

## string_xrefs

- `0x18008cbce`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18008cbe0`: `RegDeleteKeyExW`
- `0x18008cbfb`: `advapi32.dll`
- `0x18008cc0d`: `RegDeleteKeyW`

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
0x18008cbb0  mov     [rsp+arg_0], rbx
0x18008cbb5  push    rdi
0x18008cbb6  sub     rsp, 30h
0x18008cbba  mov     rdi, rdx
0x18008cbbd  mov     rbx, rcx
0x18008cbc0  cmp     qword ptr [rcx+8], 0
0x18008cbc5  jnz     short loc_18008CC21
0x18008cbc7  cmp     qword ptr [rcx+10h], 0
0x18008cbcc  jnz     short loc_18008CC21
0x18008cbce  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18008cbd5  call    cs:__imp_GetModuleHandleW
0x18008cbdb  test    rax, rax
0x18008cbde  jz      short loc_18008CBF6
0x18008cbe0  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18008cbe7  mov     rcx, rax; hModule
0x18008cbea  call    cs:__imp_GetProcAddress
0x18008cbf0  mov     [rbx+8], rax
0x18008cbf4  jmp     short loc_18008CC21
0x18008cbf6  xor     r8d, r8d; dwFlags
0x18008cbf9  xor     edx, edx; hFile
0x18008cbfb  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x18008cc02  call    cs:__imp_LoadLibraryExW
0x18008cc08  test    rax, rax
0x18008cc0b  jz      short loc_18008CC21
0x18008cc0d  lea     rdx, aRegdeletekeyw_0; "RegDeleteKeyW"
0x18008cc14  mov     rcx, rax; hModule
0x18008cc17  call    cs:__imp_GetProcAddress
0x18008cc1d  mov     [rbx+10h], rax
0x18008cc21  mov     rax, [rbx+8]
0x18008cc25  test    rax, rax
0x18008cc28  jz      short loc_18008CC3D
0x18008cc2a  xor     r9d, r9d
0x18008cc2d  xor     r8d, r8d
0x18008cc30  mov     rdx, rdi
0x18008cc33  mov     rcx, [rbx]
0x18008cc36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cc3b  jmp     short loc_18008CC5A
0x18008cc3d  mov     rax, [rbx+10h]
0x18008cc41  test    rax, rax
0x18008cc44  jz      short loc_18008CC53
0x18008cc46  mov     rdx, rdi
0x18008cc49  mov     rcx, [rbx]
0x18008cc4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cc51  jmp     short loc_18008CC5A
0x18008cc53  call    cs:__imp_GetLastError
0x18008cc59  nop
0x18008cc5a  mov     rbx, [rsp+38h+arg_0]
0x18008cc5f  add     rsp, 30h
0x18008cc63  pop     rdi
0x18008cc64  retn
```
