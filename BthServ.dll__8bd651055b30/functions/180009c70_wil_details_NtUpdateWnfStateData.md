# wil_details_NtUpdateWnfStateData

- ea: `0x180009c70`
- end: `0x180009d1a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800073bc`
- `0x1800097a8`

## callees

- `0x180009c70`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009ca7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009ca7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009cbe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009cbe`

## string_xrefs

- `0x180009ca0`: `ntdll.dll`
- `0x180009cb4`: `NtUpdateWnfStateData`

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
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180009c70  mov     [rsp+arg_0], rbx
0x180009c75  mov     [rsp+arg_8], rsi
0x180009c7a  push    rdi
0x180009c7b  sub     rsp, 40h
0x180009c7f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180009c86  mov     ebx, r8d
0x180009c89  mov     rdi, rdx
0x180009c8c  mov     rsi, rcx
0x180009c8f  test    r10, r10
0x180009c92  jnz     short loc_180009CDA
0x180009c94  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009c9b  test    rax, rax
0x180009c9e  jnz     short loc_180009CB4
0x180009ca0  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180009ca7  call    cs:__imp_GetModuleHandleW
0x180009cad  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009cb4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180009cbb  mov     rcx, rax; hModule
0x180009cbe  call    cs:__imp_GetProcAddress
0x180009cc4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180009ccb  mov     r10, rax
0x180009cce  test    rax, rax
0x180009cd1  jnz     short loc_180009CDA
0x180009cd3  mov     eax, 0C0000139h
0x180009cd8  jmp     short loc_180009D0A
0x180009cda  mov     eax, [rsp+48h+arg_30]
0x180009ce1  xor     r9d, r9d
0x180009ce4  mov     [rsp+48h+var_18], eax
0x180009ce8  mov     r8d, ebx
0x180009ceb  mov     eax, [rsp+48h+arg_28]
0x180009cef  mov     rdx, rdi
0x180009cf2  mov     [rsp+48h+var_20], eax
0x180009cf6  mov     rcx, rsi
0x180009cf9  mov     rax, r10
0x180009cfc  mov     [rsp+48h+var_28], 0
0x180009d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d0a  mov     rbx, [rsp+48h+arg_0]
0x180009d0f  mov     rsi, [rsp+48h+arg_8]
0x180009d14  add     rsp, 40h
0x180009d18  pop     rdi
0x180009d19  retn
```
