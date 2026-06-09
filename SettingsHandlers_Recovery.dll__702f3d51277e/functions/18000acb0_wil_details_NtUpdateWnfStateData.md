# wil_details_NtUpdateWnfStateData

- ea: `0x18000acb0`
- end: `0x18000ad5a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000831c`
- `0x18000a7e8`

## callees

- `0x18000acb0`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000acfe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000acfe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ace7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ace7`

## string_xrefs

- `0x18000ace0`: `ntdll.dll`
- `0x18000acf4`: `NtUpdateWnfStateData`

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
0x18000acb0  mov     [rsp+arg_0], rbx
0x18000acb5  mov     [rsp+arg_8], rsi
0x18000acba  push    rdi
0x18000acbb  sub     rsp, 40h
0x18000acbf  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000acc6  mov     ebx, r8d
0x18000acc9  mov     rdi, rdx
0x18000accc  mov     rsi, rcx
0x18000accf  test    r10, r10
0x18000acd2  jnz     short loc_18000AD1A
0x18000acd4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000acdb  test    rax, rax
0x18000acde  jnz     short loc_18000ACF4
0x18000ace0  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000ace7  call    cs:__imp_GetModuleHandleW
0x18000aced  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000acf4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000acfb  mov     rcx, rax; hModule
0x18000acfe  call    cs:__imp_GetProcAddress
0x18000ad04  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000ad0b  mov     r10, rax
0x18000ad0e  test    rax, rax
0x18000ad11  jnz     short loc_18000AD1A
0x18000ad13  mov     eax, 0C0000139h
0x18000ad18  jmp     short loc_18000AD4A
0x18000ad1a  mov     eax, [rsp+48h+arg_30]
0x18000ad21  xor     r9d, r9d
0x18000ad24  mov     [rsp+48h+var_18], eax
0x18000ad28  mov     r8d, ebx
0x18000ad2b  mov     eax, [rsp+48h+arg_28]
0x18000ad2f  mov     rdx, rdi
0x18000ad32  mov     [rsp+48h+var_20], eax
0x18000ad36  mov     rcx, rsi
0x18000ad39  mov     rax, r10
0x18000ad3c  mov     [rsp+48h+var_28], 0
0x18000ad45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad4a  mov     rbx, [rsp+48h+arg_0]
0x18000ad4f  mov     rsi, [rsp+48h+arg_8]
0x18000ad54  add     rsp, 40h
0x18000ad58  pop     rdi
0x18000ad59  retn
```
