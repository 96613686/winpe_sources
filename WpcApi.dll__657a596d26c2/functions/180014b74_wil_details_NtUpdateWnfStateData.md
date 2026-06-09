# wil_details_NtUpdateWnfStateData

- ea: `0x180014b74`
- end: `0x180014c1e`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180011b38`
- `0x180014934`

## callees

- `0x180014b74`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014bab`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014bab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014bc2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014bc2`

## string_xrefs

- `0x180014ba4`: `ntdll.dll`
- `0x180014bb8`: `NtUpdateWnfStateData`

## pseudocode

```c
__int64 __fastcall wil_details_NtUpdateWnfStateData(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        int a6,
        int a7)
{
  __int64 (__fastcall *v7)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int); // r10
  HMODULE ModuleHandleW; // rax

  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int))g_wil_details_pfnNtUpdateWnfStateData;
  if ( g_wil_details_pfnNtUpdateWnfStateData )
    return v7(a1, a2, a3, 0, 0, a6, a7);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  g_wil_details_pfnNtUpdateWnfStateData = (__int64)GetProcAddress(ModuleHandleW, "NtUpdateWnfStateData");
  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int))g_wil_details_pfnNtUpdateWnfStateData;
  if ( g_wil_details_pfnNtUpdateWnfStateData )
    return v7(a1, a2, a3, 0, 0, a6, a7);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x180014b74  mov     [rsp+arg_0], rbx
0x180014b79  mov     [rsp+arg_8], rsi
0x180014b7e  push    rdi
0x180014b7f  sub     rsp, 40h
0x180014b83  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180014b8a  mov     ebx, r8d
0x180014b8d  mov     rdi, rdx
0x180014b90  mov     rsi, rcx
0x180014b93  test    r10, r10
0x180014b96  jnz     short loc_180014BDE
0x180014b98  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014b9f  test    rax, rax
0x180014ba2  jnz     short loc_180014BB8
0x180014ba4  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180014bab  call    cs:__imp_GetModuleHandleW
0x180014bb1  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014bb8  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180014bbf  mov     rcx, rax; hModule
0x180014bc2  call    cs:__imp_GetProcAddress
0x180014bc8  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180014bcf  mov     r10, rax
0x180014bd2  test    rax, rax
0x180014bd5  jnz     short loc_180014BDE
0x180014bd7  mov     eax, 0C0000139h
0x180014bdc  jmp     short loc_180014C0E
0x180014bde  mov     eax, [rsp+48h+arg_30]
0x180014be5  xor     r9d, r9d
0x180014be8  mov     [rsp+48h+var_18], eax
0x180014bec  mov     r8d, ebx
0x180014bef  mov     eax, [rsp+48h+arg_28]
0x180014bf3  mov     rdx, rdi
0x180014bf6  mov     [rsp+48h+var_20], eax
0x180014bfa  mov     rcx, rsi
0x180014bfd  mov     rax, r10
0x180014c00  mov     [rsp+48h+var_28], 0
0x180014c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c0e  mov     rbx, [rsp+48h+arg_0]
0x180014c13  mov     rsi, [rsp+48h+arg_8]
0x180014c18  add     rsp, 40h
0x180014c1c  pop     rdi
0x180014c1d  retn
```
