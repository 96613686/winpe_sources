# wil_details_NtUpdateWnfStateData

- ea: `0x18000a3f0`
- end: `0x18000a49a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180007b7c`
- `0x180009f28`

## callees

- `0x18000a3f0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a43e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a43e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a427`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a427`

## string_xrefs

- `0x18000a420`: `ntdll.dll`
- `0x18000a434`: `NtUpdateWnfStateData`

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
0x18000a3f0  mov     [rsp+arg_0], rbx
0x18000a3f5  mov     [rsp+arg_8], rsi
0x18000a3fa  push    rdi
0x18000a3fb  sub     rsp, 40h
0x18000a3ff  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000a406  mov     ebx, r8d
0x18000a409  mov     rdi, rdx
0x18000a40c  mov     rsi, rcx
0x18000a40f  test    r10, r10
0x18000a412  jnz     short loc_18000A45A
0x18000a414  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a41b  test    rax, rax
0x18000a41e  jnz     short loc_18000A434
0x18000a420  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000a427  call    cs:__imp_GetModuleHandleW
0x18000a42d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a434  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000a43b  mov     rcx, rax; hModule
0x18000a43e  call    cs:__imp_GetProcAddress
0x18000a444  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000a44b  mov     r10, rax
0x18000a44e  test    rax, rax
0x18000a451  jnz     short loc_18000A45A
0x18000a453  mov     eax, 0C0000139h
0x18000a458  jmp     short loc_18000A48A
0x18000a45a  mov     eax, [rsp+48h+arg_30]
0x18000a461  xor     r9d, r9d
0x18000a464  mov     [rsp+48h+var_18], eax
0x18000a468  mov     r8d, ebx
0x18000a46b  mov     eax, [rsp+48h+arg_28]
0x18000a46f  mov     rdx, rdi
0x18000a472  mov     [rsp+48h+var_20], eax
0x18000a476  mov     rcx, rsi
0x18000a479  mov     rax, r10
0x18000a47c  mov     [rsp+48h+var_28], 0
0x18000a485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a48a  mov     rbx, [rsp+48h+arg_0]
0x18000a48f  mov     rsi, [rsp+48h+arg_8]
0x18000a494  add     rsp, 40h
0x18000a498  pop     rdi
0x18000a499  retn
```
