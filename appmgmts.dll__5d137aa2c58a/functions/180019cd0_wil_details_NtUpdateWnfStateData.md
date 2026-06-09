# wil_details_NtUpdateWnfStateData

- ea: `0x180019cd0`
- end: `0x180019d7a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180017aec`
- `0x180019a00`

## callees

- `0x180019cd0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019d1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019d1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019d07`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019d07`

## string_xrefs

- `0x180019d00`: `ntdll.dll`
- `0x180019d14`: `NtUpdateWnfStateData`

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
0x180019cd0  mov     [rsp+arg_0], rbx
0x180019cd5  mov     [rsp+arg_8], rsi
0x180019cda  push    rdi
0x180019cdb  sub     rsp, 40h
0x180019cdf  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180019ce6  mov     ebx, r8d
0x180019ce9  mov     rdi, rdx
0x180019cec  mov     rsi, rcx
0x180019cef  test    r10, r10
0x180019cf2  jnz     short loc_180019D3A
0x180019cf4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180019cfb  test    rax, rax
0x180019cfe  jnz     short loc_180019D14
0x180019d00  lea     rcx, ModuleName; "ntdll.dll"
0x180019d07  call    cs:__imp_GetModuleHandleW
0x180019d0d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180019d14  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180019d1b  mov     rcx, rax; hModule
0x180019d1e  call    cs:__imp_GetProcAddress
0x180019d24  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180019d2b  mov     r10, rax
0x180019d2e  test    rax, rax
0x180019d31  jnz     short loc_180019D3A
0x180019d33  mov     eax, 0C0000139h
0x180019d38  jmp     short loc_180019D6A
0x180019d3a  mov     eax, [rsp+48h+arg_30]
0x180019d41  xor     r9d, r9d
0x180019d44  mov     [rsp+48h+var_18], eax
0x180019d48  mov     r8d, ebx
0x180019d4b  mov     eax, [rsp+48h+arg_28]
0x180019d4f  mov     rdx, rdi
0x180019d52  mov     [rsp+48h+var_20], eax
0x180019d56  mov     rcx, rsi
0x180019d59  mov     rax, r10
0x180019d5c  mov     [rsp+48h+var_28], 0
0x180019d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d6a  mov     rbx, [rsp+48h+arg_0]
0x180019d6f  mov     rsi, [rsp+48h+arg_8]
0x180019d74  add     rsp, 40h
0x180019d78  pop     rdi
0x180019d79  retn
```
