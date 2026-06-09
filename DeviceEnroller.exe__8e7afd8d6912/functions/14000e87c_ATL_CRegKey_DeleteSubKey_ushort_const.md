# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x14000e87c`
- end: `0x14000e931`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1400161e8`
- `0x140016794`

## callees

- `0x14000e87c`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e8b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e8e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e8b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e8e3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000e8ce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000e8ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000e8a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000e8a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e91f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e91f`

## string_xrefs

- `0x14000e89a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x14000e8ac`: `RegDeleteKeyExW`
- `0x14000e8c7`: `advapi32.dll`
- `0x14000e8d9`: `RegDeleteKeyW`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x14000e87c  mov     [rsp+arg_0], rbx
0x14000e881  push    rdi
0x14000e882  sub     rsp, 30h
0x14000e886  mov     rdi, rdx
0x14000e889  mov     rbx, rcx
0x14000e88c  cmp     qword ptr [rcx+8], 0
0x14000e891  jnz     short loc_14000E8ED
0x14000e893  cmp     qword ptr [rcx+10h], 0
0x14000e898  jnz     short loc_14000E8ED
0x14000e89a  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x14000e8a1  call    cs:__imp_GetModuleHandleW
0x14000e8a7  test    rax, rax
0x14000e8aa  jz      short loc_14000E8C2
0x14000e8ac  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x14000e8b3  mov     rcx, rax; hModule
0x14000e8b6  call    cs:__imp_GetProcAddress
0x14000e8bc  mov     [rbx+8], rax
0x14000e8c0  jmp     short loc_14000E8ED
0x14000e8c2  xor     r8d, r8d; dwFlags
0x14000e8c5  xor     edx, edx; hFile
0x14000e8c7  lea     rcx, LibFileName; "advapi32.dll"
0x14000e8ce  call    cs:__imp_LoadLibraryExW
0x14000e8d4  test    rax, rax
0x14000e8d7  jz      short loc_14000E8ED
0x14000e8d9  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x14000e8e0  mov     rcx, rax; hModule
0x14000e8e3  call    cs:__imp_GetProcAddress
0x14000e8e9  mov     [rbx+10h], rax
0x14000e8ed  mov     rax, [rbx+8]
0x14000e8f1  test    rax, rax
0x14000e8f4  jz      short loc_14000E909
0x14000e8f6  xor     r9d, r9d
0x14000e8f9  xor     r8d, r8d
0x14000e8fc  mov     rdx, rdi
0x14000e8ff  mov     rcx, [rbx]
0x14000e902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e907  jmp     short loc_14000E926
0x14000e909  mov     rax, [rbx+10h]
0x14000e90d  test    rax, rax
0x14000e910  jz      short loc_14000E91F
0x14000e912  mov     rdx, rdi
0x14000e915  mov     rcx, [rbx]
0x14000e918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e91d  jmp     short loc_14000E926
0x14000e91f  call    cs:__imp_GetLastError
0x14000e925  nop
0x14000e926  mov     rbx, [rsp+38h+arg_0]
0x14000e92b  add     rsp, 30h
0x14000e92f  pop     rdi
0x14000e930  retn
```
