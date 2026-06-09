# wil_details_NtUpdateWnfStateData

- ea: `0x18000d0b0`
- end: `0x18000d15a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000990c`
- `0x18000c2d8`

## callees

- `0x18000d0b0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000d0e7`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000d0e7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000d0fe`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000d0fe`

## string_xrefs

- `0x18000d0e0`: `ntdll.dll`
- `0x18000d0f4`: `NtUpdateWnfStateData`

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
0x18000d0b0  mov     [rsp+arg_0], rbx
0x18000d0b5  mov     [rsp+arg_8], rsi
0x18000d0ba  push    rdi
0x18000d0bb  sub     rsp, 40h
0x18000d0bf  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000d0c6  mov     ebx, r8d
0x18000d0c9  mov     rdi, rdx
0x18000d0cc  mov     rsi, rcx
0x18000d0cf  test    r10, r10
0x18000d0d2  jnz     short loc_18000D11A
0x18000d0d4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d0db  test    rax, rax
0x18000d0de  jnz     short loc_18000D0F4
0x18000d0e0  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000d0e7  call    cs:__imp_GetModuleHandleW
0x18000d0ed  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d0f4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000d0fb  mov     rcx, rax; hModule
0x18000d0fe  call    cs:__imp_GetProcAddress
0x18000d104  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000d10b  mov     r10, rax
0x18000d10e  test    rax, rax
0x18000d111  jnz     short loc_18000D11A
0x18000d113  mov     eax, 0C0000139h
0x18000d118  jmp     short loc_18000D14A
0x18000d11a  mov     eax, [rsp+48h+arg_30]
0x18000d121  xor     r9d, r9d
0x18000d124  mov     [rsp+48h+var_18], eax
0x18000d128  mov     r8d, ebx
0x18000d12b  mov     eax, [rsp+48h+arg_28]
0x18000d12f  mov     rdx, rdi
0x18000d132  mov     [rsp+48h+var_20], eax
0x18000d136  mov     rcx, rsi
0x18000d139  mov     rax, r10
0x18000d13c  mov     [rsp+48h+var_28], 0
0x18000d145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d14a  mov     rbx, [rsp+48h+arg_0]
0x18000d14f  mov     rsi, [rsp+48h+arg_8]
0x18000d154  add     rsp, 40h
0x18000d158  pop     rdi
0x18000d159  retn
```
