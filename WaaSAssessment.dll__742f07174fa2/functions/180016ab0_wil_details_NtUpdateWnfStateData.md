# wil_details_NtUpdateWnfStateData

- ea: `0x180016ab0`
- end: `0x180016b5a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180014cec`
- `0x1800163a0`

## callees

- `0x180016ab0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016afe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016afe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016ae7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016ae7`

## string_xrefs

- `0x180016ae0`: `ntdll.dll`
- `0x180016af4`: `NtUpdateWnfStateData`

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
0x180016ab0  mov     [rsp+arg_0], rbx
0x180016ab5  mov     [rsp+arg_8], rsi
0x180016aba  push    rdi
0x180016abb  sub     rsp, 40h
0x180016abf  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180016ac6  mov     ebx, r8d
0x180016ac9  mov     rdi, rdx
0x180016acc  mov     rsi, rcx
0x180016acf  test    r10, r10
0x180016ad2  jnz     short loc_180016B1A
0x180016ad4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180016adb  test    rax, rax
0x180016ade  jnz     short loc_180016AF4
0x180016ae0  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180016ae7  call    cs:__imp_GetModuleHandleW
0x180016aed  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180016af4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180016afb  mov     rcx, rax; hModule
0x180016afe  call    cs:__imp_GetProcAddress
0x180016b04  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180016b0b  mov     r10, rax
0x180016b0e  test    rax, rax
0x180016b11  jnz     short loc_180016B1A
0x180016b13  mov     eax, 0C0000139h
0x180016b18  jmp     short loc_180016B4A
0x180016b1a  mov     eax, [rsp+48h+arg_30]
0x180016b21  xor     r9d, r9d
0x180016b24  mov     [rsp+48h+var_18], eax
0x180016b28  mov     r8d, ebx
0x180016b2b  mov     eax, [rsp+48h+arg_28]
0x180016b2f  mov     rdx, rdi
0x180016b32  mov     [rsp+48h+var_20], eax
0x180016b36  mov     rcx, rsi
0x180016b39  mov     rax, r10
0x180016b3c  mov     [rsp+48h+var_28], 0
0x180016b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b4a  mov     rbx, [rsp+48h+arg_0]
0x180016b4f  mov     rsi, [rsp+48h+arg_8]
0x180016b54  add     rsp, 40h
0x180016b58  pop     rdi
0x180016b59  retn
```
