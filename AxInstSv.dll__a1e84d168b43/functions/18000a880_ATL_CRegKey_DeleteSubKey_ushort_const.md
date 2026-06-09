# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18000a880`
- end: `0x18000a935`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e344`
- `0x18000e810`

## callees

- `0x18000a880`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a923`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a923`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a8a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a8a5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a8d2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a8d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a8ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a8e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a8ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a8e7`

## string_xrefs

- `0x18000a89e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000a8b0`: `RegDeleteKeyExW`
- `0x18000a8cb`: `advapi32.dll`
- `0x18000a8dd`: `RegDeleteKeyW`

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
0x18000a880  mov     [rsp+arg_0], rbx
0x18000a885  push    rdi
0x18000a886  sub     rsp, 30h
0x18000a88a  mov     rdi, rdx
0x18000a88d  mov     rbx, rcx
0x18000a890  cmp     qword ptr [rcx+8], 0
0x18000a895  jnz     short loc_18000A8F1
0x18000a897  cmp     qword ptr [rcx+10h], 0
0x18000a89c  jnz     short loc_18000A8F1
0x18000a89e  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000a8a5  call    cs:__imp_GetModuleHandleW
0x18000a8ab  test    rax, rax
0x18000a8ae  jz      short loc_18000A8C6
0x18000a8b0  lea     rdx, ProcName; "RegDeleteKeyExW"
0x18000a8b7  mov     rcx, rax; hModule
0x18000a8ba  call    cs:__imp_GetProcAddress
0x18000a8c0  mov     [rbx+8], rax
0x18000a8c4  jmp     short loc_18000A8F1
0x18000a8c6  xor     r8d, r8d; dwFlags
0x18000a8c9  xor     edx, edx; hFile
0x18000a8cb  lea     rcx, LibFileName; "advapi32.dll"
0x18000a8d2  call    cs:__imp_LoadLibraryExW
0x18000a8d8  test    rax, rax
0x18000a8db  jz      short loc_18000A8F1
0x18000a8dd  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000a8e4  mov     rcx, rax; hModule
0x18000a8e7  call    cs:__imp_GetProcAddress
0x18000a8ed  mov     [rbx+10h], rax
0x18000a8f1  mov     rax, [rbx+8]
0x18000a8f5  test    rax, rax
0x18000a8f8  jz      short loc_18000A90D
0x18000a8fa  xor     r9d, r9d
0x18000a8fd  xor     r8d, r8d
0x18000a900  mov     rdx, rdi
0x18000a903  mov     rcx, [rbx]
0x18000a906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a90b  jmp     short loc_18000A92A
0x18000a90d  mov     rax, [rbx+10h]
0x18000a911  test    rax, rax
0x18000a914  jz      short loc_18000A923
0x18000a916  mov     rdx, rdi
0x18000a919  mov     rcx, [rbx]
0x18000a91c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a921  jmp     short loc_18000A92A
0x18000a923  call    cs:__imp_GetLastError
0x18000a929  nop
0x18000a92a  mov     rbx, [rsp+38h+arg_0]
0x18000a92f  add     rsp, 30h
0x18000a933  pop     rdi
0x18000a934  retn
```
