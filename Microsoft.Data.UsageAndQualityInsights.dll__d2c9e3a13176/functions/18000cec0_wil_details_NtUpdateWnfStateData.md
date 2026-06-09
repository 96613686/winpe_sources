# wil_details_NtUpdateWnfStateData

- ea: `0x18000cec0`
- end: `0x18000cf6a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180009fa8`
- `0x18000c998`

## callees

- `0x18000cec0`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cef7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cef7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cf0e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cf0e`

## string_xrefs

- `0x18000cef0`: `ntdll.dll`
- `0x18000cf04`: `NtUpdateWnfStateData`

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
0x18000cec0  mov     [rsp+arg_0], rbx
0x18000cec5  mov     [rsp+arg_8], rsi
0x18000ceca  push    rdi
0x18000cecb  sub     rsp, 40h
0x18000cecf  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000ced6  mov     ebx, r8d
0x18000ced9  mov     rdi, rdx
0x18000cedc  mov     rsi, rcx
0x18000cedf  test    r10, r10
0x18000cee2  jnz     short loc_18000CF2A
0x18000cee4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ceeb  test    rax, rax
0x18000ceee  jnz     short loc_18000CF04
0x18000cef0  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000cef7  call    cs:__imp_GetModuleHandleW
0x18000cefd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cf04  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000cf0b  mov     rcx, rax; hModule
0x18000cf0e  call    cs:__imp_GetProcAddress
0x18000cf14  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000cf1b  mov     r10, rax
0x18000cf1e  test    rax, rax
0x18000cf21  jnz     short loc_18000CF2A
0x18000cf23  mov     eax, 0C0000139h
0x18000cf28  jmp     short loc_18000CF5A
0x18000cf2a  mov     eax, [rsp+48h+arg_30]
0x18000cf31  xor     r9d, r9d
0x18000cf34  mov     [rsp+48h+var_18], eax
0x18000cf38  mov     r8d, ebx
0x18000cf3b  mov     eax, [rsp+48h+arg_28]
0x18000cf3f  mov     rdx, rdi
0x18000cf42  mov     [rsp+48h+var_20], eax
0x18000cf46  mov     rcx, rsi
0x18000cf49  mov     rax, r10
0x18000cf4c  mov     [rsp+48h+var_28], 0
0x18000cf55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf5a  mov     rbx, [rsp+48h+arg_0]
0x18000cf5f  mov     rsi, [rsp+48h+arg_8]
0x18000cf64  add     rsp, 40h
0x18000cf68  pop     rdi
0x18000cf69  retn
```
