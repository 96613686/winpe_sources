# ATL::CRegKey::DeleteSubKey(wchar_t const *)

- ea: `0x180195180`
- end: `0x180195235`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const wchar_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180193f24`
- `0x180198678`
- `0x180198b48`

## callees

- `0x180195180`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1801951a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1801951a5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801951d2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801951d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801951ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801951e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801951ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801951e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180195223`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180195223`

## string_xrefs

- `0x18019519e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1801951b0`: `RegDeleteKeyExW`
- `0x1801951cb`: `advapi32.dll`
- `0x1801951dd`: `RegDeleteKeyW`

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
0x180195180  mov     [rsp+arg_0], rbx
0x180195185  push    rdi
0x180195186  sub     rsp, 30h
0x18019518a  mov     rdi, rdx
0x18019518d  mov     rbx, rcx
0x180195190  cmp     qword ptr [rcx+8], 0
0x180195195  jnz     short loc_1801951F1
0x180195197  cmp     qword ptr [rcx+10h], 0
0x18019519c  jnz     short loc_1801951F1
0x18019519e  lea     rcx, aApiMsWinCoreLo_2; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1801951a5  call    cs:__imp_GetModuleHandleW
0x1801951ab  test    rax, rax
0x1801951ae  jz      short loc_1801951C6
0x1801951b0  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1801951b7  mov     rcx, rax; hModule
0x1801951ba  call    cs:__imp_GetProcAddress
0x1801951c0  mov     [rbx+8], rax
0x1801951c4  jmp     short loc_1801951F1
0x1801951c6  xor     r8d, r8d; dwFlags
0x1801951c9  xor     edx, edx; hFile
0x1801951cb  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x1801951d2  call    cs:__imp_LoadLibraryExW
0x1801951d8  test    rax, rax
0x1801951db  jz      short loc_1801951F1
0x1801951dd  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1801951e4  mov     rcx, rax; hModule
0x1801951e7  call    cs:__imp_GetProcAddress
0x1801951ed  mov     [rbx+10h], rax
0x1801951f1  mov     rax, [rbx+8]
0x1801951f5  test    rax, rax
0x1801951f8  jz      short loc_18019520D
0x1801951fa  xor     r9d, r9d
0x1801951fd  xor     r8d, r8d
0x180195200  mov     rdx, rdi
0x180195203  mov     rcx, [rbx]
0x180195206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019520b  jmp     short loc_18019522A
0x18019520d  mov     rax, [rbx+10h]
0x180195211  test    rax, rax
0x180195214  jz      short loc_180195223
0x180195216  mov     rdx, rdi
0x180195219  mov     rcx, [rbx]
0x18019521c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195221  jmp     short loc_18019522A
0x180195223  call    cs:__imp_GetLastError
0x180195229  nop
0x18019522a  mov     rbx, [rsp+38h+arg_0]
0x18019522f  add     rsp, 30h
0x180195233  pop     rdi
0x180195234  retn
```
