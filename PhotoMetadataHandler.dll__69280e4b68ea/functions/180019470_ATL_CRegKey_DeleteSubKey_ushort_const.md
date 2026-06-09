# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180019470`
- end: `0x180019544`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `212`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180018d78`
- `0x180019bcc`
- `0x18001a0d8`

## callees

- `0x180019470`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800194b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800194e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800194b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800194e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019495`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019495`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800194ce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800194ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001952b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001952b`

## string_xrefs

- `0x18001948e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800194a6`: `RegDeleteKeyExW`
- `0x1800194c7`: `advapi32.dll`
- `0x1800194df`: `RegDeleteKeyW`

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
0x180019470  mov     [rsp+arg_0], rbx
0x180019475  push    rdi
0x180019476  sub     rsp, 30h
0x18001947a  mov     rdi, rdx
0x18001947d  mov     rbx, rcx
0x180019480  cmp     qword ptr [rcx+8], 0
0x180019485  jnz     short loc_1800194F9
0x180019487  cmp     qword ptr [rcx+10h], 0
0x18001948c  jnz     short loc_1800194F9
0x18001948e  lea     rcx, aApiMsWinCoreLo_1; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180019495  call    cs:__imp_GetModuleHandleW
0x18001949c  nop     dword ptr [rax+rax+00h]
0x1800194a1  test    rax, rax
0x1800194a4  jz      short loc_1800194C2
0x1800194a6  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1800194ad  mov     rcx, rax; hModule
0x1800194b0  call    cs:__imp_GetProcAddress
0x1800194b7  nop     dword ptr [rax+rax+00h]
0x1800194bc  mov     [rbx+8], rax
0x1800194c0  jmp     short loc_1800194F9
0x1800194c2  xor     r8d, r8d; dwFlags
0x1800194c5  xor     edx, edx; hFile
0x1800194c7  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x1800194ce  call    cs:__imp_LoadLibraryExW
0x1800194d5  nop     dword ptr [rax+rax+00h]
0x1800194da  test    rax, rax
0x1800194dd  jz      short loc_1800194F9
0x1800194df  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800194e6  mov     rcx, rax; hModule
0x1800194e9  call    cs:__imp_GetProcAddress
0x1800194f0  nop     dword ptr [rax+rax+00h]
0x1800194f5  mov     [rbx+10h], rax
0x1800194f9  mov     rax, [rbx+8]
0x1800194fd  test    rax, rax
0x180019500  jz      short loc_180019515
0x180019502  xor     r9d, r9d
0x180019505  xor     r8d, r8d
0x180019508  mov     rdx, rdi
0x18001950b  mov     rcx, [rbx]
0x18001950e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019513  jmp     short loc_180019538
0x180019515  mov     rax, [rbx+10h]
0x180019519  test    rax, rax
0x18001951c  jz      short loc_18001952B
0x18001951e  mov     rdx, rdi
0x180019521  mov     rcx, [rbx]
0x180019524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019529  jmp     short loc_180019538
0x18001952b  call    cs:__imp_GetLastError
0x180019532  nop     dword ptr [rax+rax+00h]
0x180019537  nop
0x180019538  mov     rbx, [rsp+38h+arg_0]
0x18001953d  add     rsp, 30h
0x180019541  pop     rdi
0x180019542  retn
```
