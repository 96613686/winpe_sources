# wil_details_NtUpdateWnfStateData

- ea: `0x140012f4c`
- end: `0x140012ff6`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140011b70`
- `0x140012d0c`

## callees

- `0x140012f4c`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140012f9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140012f9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012f83`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012f83`

## string_xrefs

- `0x140012f7c`: `ntdll.dll`
- `0x140012f90`: `NtUpdateWnfStateData`

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
0x140012f4c  mov     [rsp+arg_0], rbx
0x140012f51  mov     [rsp+arg_8], rsi
0x140012f56  push    rdi
0x140012f57  sub     rsp, 40h
0x140012f5b  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x140012f62  mov     ebx, r8d
0x140012f65  mov     rdi, rdx
0x140012f68  mov     rsi, rcx
0x140012f6b  test    r10, r10
0x140012f6e  jnz     short loc_140012FB6
0x140012f70  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140012f77  test    rax, rax
0x140012f7a  jnz     short loc_140012F90
0x140012f7c  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x140012f83  call    cs:__imp_GetModuleHandleW
0x140012f89  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140012f90  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x140012f97  mov     rcx, rax; hModule
0x140012f9a  call    cs:__imp_GetProcAddress
0x140012fa0  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x140012fa7  mov     r10, rax
0x140012faa  test    rax, rax
0x140012fad  jnz     short loc_140012FB6
0x140012faf  mov     eax, 0C0000139h
0x140012fb4  jmp     short loc_140012FE6
0x140012fb6  mov     eax, [rsp+48h+arg_30]
0x140012fbd  xor     r9d, r9d
0x140012fc0  mov     [rsp+48h+var_18], eax
0x140012fc4  mov     r8d, ebx
0x140012fc7  mov     eax, [rsp+48h+arg_28]
0x140012fcb  mov     rdx, rdi
0x140012fce  mov     [rsp+48h+var_20], eax
0x140012fd2  mov     rcx, rsi
0x140012fd5  mov     rax, r10
0x140012fd8  mov     [rsp+48h+var_28], 0
0x140012fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012fe6  mov     rbx, [rsp+48h+arg_0]
0x140012feb  mov     rsi, [rsp+48h+arg_8]
0x140012ff0  add     rsp, 40h
0x140012ff4  pop     rdi
0x140012ff5  retn
```
