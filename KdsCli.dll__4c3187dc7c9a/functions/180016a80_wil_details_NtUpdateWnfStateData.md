# wil_details_NtUpdateWnfStateData

- ea: `0x180016a80`
- end: `0x180016b2a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180014f88`
- `0x18001664c`

## callees

- `0x180016a80`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016ab7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016ab7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016ace`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016ace`

## string_xrefs

- `0x180016ab0`: `ntdll.dll`
- `0x180016ac4`: `NtUpdateWnfStateData`

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
0x180016a80  mov     [rsp+arg_0], rbx
0x180016a85  mov     [rsp+arg_8], rsi
0x180016a8a  push    rdi
0x180016a8b  sub     rsp, 40h
0x180016a8f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180016a96  mov     ebx, r8d
0x180016a99  mov     rdi, rdx
0x180016a9c  mov     rsi, rcx
0x180016a9f  test    r10, r10
0x180016aa2  jnz     short loc_180016AEA
0x180016aa4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180016aab  test    rax, rax
0x180016aae  jnz     short loc_180016AC4
0x180016ab0  lea     rcx, ModuleName; "ntdll.dll"
0x180016ab7  call    cs:__imp_GetModuleHandleW
0x180016abd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180016ac4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180016acb  mov     rcx, rax; hModule
0x180016ace  call    cs:__imp_GetProcAddress
0x180016ad4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180016adb  mov     r10, rax
0x180016ade  test    rax, rax
0x180016ae1  jnz     short loc_180016AEA
0x180016ae3  mov     eax, 0C0000139h
0x180016ae8  jmp     short loc_180016B1A
0x180016aea  mov     eax, [rsp+48h+arg_30]
0x180016af1  xor     r9d, r9d
0x180016af4  mov     [rsp+48h+var_18], eax
0x180016af8  mov     r8d, ebx
0x180016afb  mov     eax, [rsp+48h+arg_28]
0x180016aff  mov     rdx, rdi
0x180016b02  mov     [rsp+48h+var_20], eax
0x180016b06  mov     rcx, rsi
0x180016b09  mov     rax, r10
0x180016b0c  mov     [rsp+48h+var_28], 0
0x180016b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b1a  mov     rbx, [rsp+48h+arg_0]
0x180016b1f  mov     rsi, [rsp+48h+arg_8]
0x180016b24  add     rsp, 40h
0x180016b28  pop     rdi
0x180016b29  retn
```
