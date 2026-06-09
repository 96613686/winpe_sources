# wil_details_NtUpdateWnfStateData

- ea: `0x1800162d0`
- end: `0x18001637a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180014698`
- `0x180015aa4`

## callees

- `0x1800162d0`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016307`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016307`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001631e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001631e`

## string_xrefs

- `0x180016300`: `ntdll.dll`
- `0x180016314`: `NtUpdateWnfStateData`

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
0x1800162d0  mov     [rsp+arg_0], rbx
0x1800162d5  mov     [rsp+arg_8], rsi
0x1800162da  push    rdi
0x1800162db  sub     rsp, 40h
0x1800162df  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800162e6  mov     ebx, r8d
0x1800162e9  mov     rdi, rdx
0x1800162ec  mov     rsi, rcx
0x1800162ef  test    r10, r10
0x1800162f2  jnz     short loc_18001633A
0x1800162f4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800162fb  test    rax, rax
0x1800162fe  jnz     short loc_180016314
0x180016300  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180016307  call    cs:__imp_GetModuleHandleW
0x18001630d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180016314  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001631b  mov     rcx, rax; hModule
0x18001631e  call    cs:__imp_GetProcAddress
0x180016324  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001632b  mov     r10, rax
0x18001632e  test    rax, rax
0x180016331  jnz     short loc_18001633A
0x180016333  mov     eax, 0C0000139h
0x180016338  jmp     short loc_18001636A
0x18001633a  mov     eax, [rsp+48h+arg_30]
0x180016341  xor     r9d, r9d
0x180016344  mov     [rsp+48h+var_18], eax
0x180016348  mov     r8d, ebx
0x18001634b  mov     eax, [rsp+48h+arg_28]
0x18001634f  mov     rdx, rdi
0x180016352  mov     [rsp+48h+var_20], eax
0x180016356  mov     rcx, rsi
0x180016359  mov     rax, r10
0x18001635c  mov     [rsp+48h+var_28], 0
0x180016365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001636a  mov     rbx, [rsp+48h+arg_0]
0x18001636f  mov     rsi, [rsp+48h+arg_8]
0x180016374  add     rsp, 40h
0x180016378  pop     rdi
0x180016379  retn
```
