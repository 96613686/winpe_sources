# ATL::CRegKey::DeleteSubKey(wchar_t const *)

- ea: `0x140014704`
- end: `0x1400147c3`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `191`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1400245bc`
- `0x140024a44`

## callees

- `0x140014704`
- `0x140070010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140014733`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140014733`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140014748`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140014775`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140014748`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140014775`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140014760`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140014760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400147b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400147b1`

## string_xrefs

- `0x14001472c`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x14001473e`: `RegDeleteKeyExW`
- `0x140014759`: `advapi32.dll`
- `0x14001476b`: `RegDeleteKeyW`

## pseudocode

```c
DWORD __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const wchar_t *a2)
{
  HMODULE ModuleHandleW; // rax
  HMODULE Library; // rax
  __int64 (__fastcall *v6)(_QWORD, const wchar_t *, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v8)(_QWORD, const wchar_t *); // rax

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
  v6 = (__int64 (__fastcall *)(_QWORD, const wchar_t *, _QWORD, _QWORD))*((_QWORD *)this + 1);
  if ( v6 )
    return v6(*(_QWORD *)this, a2, 0, 0);
  v8 = (__int64 (__fastcall *)(_QWORD, const wchar_t *))*((_QWORD *)this + 2);
  if ( v8 )
    return v8(*(_QWORD *)this, a2);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x140014704  push    rdi
0x140014706  sub     rsp, 40h
0x14001470a  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x140014713  mov     [rsp+48h+arg_0], rbx
0x140014718  mov     rdi, rdx
0x14001471b  mov     rbx, rcx
0x14001471e  cmp     qword ptr [rcx+8], 0
0x140014723  jnz     short loc_14001477F
0x140014725  cmp     qword ptr [rcx+10h], 0
0x14001472a  jnz     short loc_14001477F
0x14001472c  lea     rcx, aApiMsWinCoreLo_2; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x140014733  call    cs:__imp_GetModuleHandleW
0x140014739  test    rax, rax
0x14001473c  jz      short loc_140014754
0x14001473e  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x140014745  mov     rcx, rax; hModule
0x140014748  call    cs:__imp_GetProcAddress
0x14001474e  mov     [rbx+8], rax
0x140014752  jmp     short loc_14001477F
0x140014754  xor     r8d, r8d; dwFlags
0x140014757  xor     edx, edx; hFile
0x140014759  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x140014760  call    cs:__imp_LoadLibraryExW
0x140014766  test    rax, rax
0x140014769  jz      short loc_14001477F
0x14001476b  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x140014772  mov     rcx, rax; hModule
0x140014775  call    cs:__imp_GetProcAddress
0x14001477b  mov     [rbx+10h], rax
0x14001477f  mov     rax, [rbx+8]
0x140014783  test    rax, rax
0x140014786  jz      short loc_14001479B
0x140014788  xor     r9d, r9d
0x14001478b  xor     r8d, r8d
0x14001478e  mov     rdx, rdi
0x140014791  mov     rcx, [rbx]
0x140014794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014799  jmp     short loc_1400147B8
0x14001479b  mov     rax, [rbx+10h]
0x14001479f  test    rax, rax
0x1400147a2  jz      short loc_1400147B1
0x1400147a4  mov     rdx, rdi
0x1400147a7  mov     rcx, [rbx]
0x1400147aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400147af  jmp     short loc_1400147B8
0x1400147b1  call    cs:__imp_GetLastError
0x1400147b7  nop
0x1400147b8  mov     rbx, [rsp+48h+arg_0]
0x1400147bd  add     rsp, 40h
0x1400147c1  pop     rdi
0x1400147c2  retn
```
