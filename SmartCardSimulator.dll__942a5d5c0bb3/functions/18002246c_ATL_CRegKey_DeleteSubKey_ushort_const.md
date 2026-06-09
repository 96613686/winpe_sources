# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18002246c`
- end: `0x180022521`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180021b34`

## callees

- `0x18002246c`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800224a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800224d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800224a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800224d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022491`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022491`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800224be`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800224be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002250f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002250f`

## string_xrefs

- `0x18002248a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18002249c`: `RegDeleteKeyExW`
- `0x1800224b7`: `advapi32.dll`
- `0x1800224c9`: `RegDeleteKeyW`

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
0x18002246c  mov     [rsp+arg_0], rbx
0x180022471  push    rdi
0x180022472  sub     rsp, 30h
0x180022476  mov     rdi, rdx
0x180022479  mov     rbx, rcx
0x18002247c  cmp     qword ptr [rcx+8], 0
0x180022481  jnz     short loc_1800224DD
0x180022483  cmp     qword ptr [rcx+10h], 0
0x180022488  jnz     short loc_1800224DD
0x18002248a  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180022491  call    cs:__imp_GetModuleHandleW
0x180022497  test    rax, rax
0x18002249a  jz      short loc_1800224B2
0x18002249c  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1800224a3  mov     rcx, rax; hModule
0x1800224a6  call    cs:__imp_GetProcAddress
0x1800224ac  mov     [rbx+8], rax
0x1800224b0  jmp     short loc_1800224DD
0x1800224b2  xor     r8d, r8d; dwFlags
0x1800224b5  xor     edx, edx; hFile
0x1800224b7  lea     rcx, LibFileName; "advapi32.dll"
0x1800224be  call    cs:__imp_LoadLibraryExW
0x1800224c4  test    rax, rax
0x1800224c7  jz      short loc_1800224DD
0x1800224c9  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800224d0  mov     rcx, rax; hModule
0x1800224d3  call    cs:__imp_GetProcAddress
0x1800224d9  mov     [rbx+10h], rax
0x1800224dd  mov     rax, [rbx+8]
0x1800224e1  test    rax, rax
0x1800224e4  jz      short loc_1800224F9
0x1800224e6  xor     r9d, r9d
0x1800224e9  xor     r8d, r8d
0x1800224ec  mov     rdx, rdi
0x1800224ef  mov     rcx, [rbx]
0x1800224f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224f7  jmp     short loc_180022516
0x1800224f9  mov     rax, [rbx+10h]
0x1800224fd  test    rax, rax
0x180022500  jz      short loc_18002250F
0x180022502  mov     rdx, rdi
0x180022505  mov     rcx, [rbx]
0x180022508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002250d  jmp     short loc_180022516
0x18002250f  call    cs:__imp_GetLastError
0x180022515  nop
0x180022516  mov     rbx, [rsp+38h+arg_0]
0x18002251b  add     rsp, 30h
0x18002251f  pop     rdi
0x180022520  retn
```
