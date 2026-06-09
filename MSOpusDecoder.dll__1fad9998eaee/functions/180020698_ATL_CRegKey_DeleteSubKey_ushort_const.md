# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180020698`
- end: `0x18002074d`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18001fcb0`
- `0x180020f48`
- `0x18002140c`

## callees

- `0x180020698`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800206bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800206bd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800206ea`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800206ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800206d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800206ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800206d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800206ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002073b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002073b`

## string_xrefs

- `0x1800206b6`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800206c8`: `RegDeleteKeyExW`
- `0x1800206e3`: `advapi32.dll`
- `0x1800206f5`: `RegDeleteKeyW`

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
0x180020698  mov     [rsp+arg_0], rbx
0x18002069d  push    rdi
0x18002069e  sub     rsp, 30h
0x1800206a2  mov     rdi, rdx
0x1800206a5  mov     rbx, rcx
0x1800206a8  cmp     qword ptr [rcx+8], 0
0x1800206ad  jnz     short loc_180020709
0x1800206af  cmp     qword ptr [rcx+10h], 0
0x1800206b4  jnz     short loc_180020709
0x1800206b6  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800206bd  call    cs:__imp_GetModuleHandleW
0x1800206c3  test    rax, rax
0x1800206c6  jz      short loc_1800206DE
0x1800206c8  lea     rdx, ProcName; "RegDeleteKeyExW"
0x1800206cf  mov     rcx, rax; hModule
0x1800206d2  call    cs:__imp_GetProcAddress
0x1800206d8  mov     [rbx+8], rax
0x1800206dc  jmp     short loc_180020709
0x1800206de  xor     r8d, r8d; dwFlags
0x1800206e1  xor     edx, edx; hFile
0x1800206e3  lea     rcx, LibFileName; "advapi32.dll"
0x1800206ea  call    cs:__imp_LoadLibraryExW
0x1800206f0  test    rax, rax
0x1800206f3  jz      short loc_180020709
0x1800206f5  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800206fc  mov     rcx, rax; hModule
0x1800206ff  call    cs:__imp_GetProcAddress
0x180020705  mov     [rbx+10h], rax
0x180020709  mov     rax, [rbx+8]
0x18002070d  test    rax, rax
0x180020710  jz      short loc_180020725
0x180020712  xor     r9d, r9d
0x180020715  xor     r8d, r8d
0x180020718  mov     rdx, rdi
0x18002071b  mov     rcx, [rbx]
0x18002071e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020723  jmp     short loc_180020742
0x180020725  mov     rax, [rbx+10h]
0x180020729  test    rax, rax
0x18002072c  jz      short loc_18002073B
0x18002072e  mov     rdx, rdi
0x180020731  mov     rcx, [rbx]
0x180020734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020739  jmp     short loc_180020742
0x18002073b  call    cs:__imp_GetLastError
0x180020741  nop
0x180020742  mov     rbx, [rsp+38h+arg_0]
0x180020747  add     rsp, 30h
0x18002074b  pop     rdi
0x18002074c  retn
```
