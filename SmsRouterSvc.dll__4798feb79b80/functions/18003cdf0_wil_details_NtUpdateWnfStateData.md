# wil_details_NtUpdateWnfStateData

- ea: `0x18003cdf0`
- end: `0x18003ce9a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18003b068`
- `0x18003c33c`

## callees

- `0x18003cdf0`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003ce27`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003ce27`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ce3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ce3e`

## string_xrefs

- `0x18003ce20`: `ntdll.dll`
- `0x18003ce34`: `NtUpdateWnfStateData`

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
0x18003cdf0  mov     [rsp+arg_0], rbx
0x18003cdf5  mov     [rsp+arg_8], rsi
0x18003cdfa  push    rdi
0x18003cdfb  sub     rsp, 40h
0x18003cdff  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18003ce06  mov     ebx, r8d
0x18003ce09  mov     rdi, rdx
0x18003ce0c  mov     rsi, rcx
0x18003ce0f  test    r10, r10
0x18003ce12  jnz     short loc_18003CE5A
0x18003ce14  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003ce1b  test    rax, rax
0x18003ce1e  jnz     short loc_18003CE34
0x18003ce20  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18003ce27  call    cs:__imp_GetModuleHandleW
0x18003ce2d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003ce34  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18003ce3b  mov     rcx, rax; hModule
0x18003ce3e  call    cs:__imp_GetProcAddress
0x18003ce44  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18003ce4b  mov     r10, rax
0x18003ce4e  test    rax, rax
0x18003ce51  jnz     short loc_18003CE5A
0x18003ce53  mov     eax, 0C0000139h
0x18003ce58  jmp     short loc_18003CE8A
0x18003ce5a  mov     eax, [rsp+48h+arg_30]
0x18003ce61  xor     r9d, r9d
0x18003ce64  mov     [rsp+48h+var_18], eax
0x18003ce68  mov     r8d, ebx
0x18003ce6b  mov     eax, [rsp+48h+arg_28]
0x18003ce6f  mov     rdx, rdi
0x18003ce72  mov     [rsp+48h+var_20], eax
0x18003ce76  mov     rcx, rsi
0x18003ce79  mov     rax, r10
0x18003ce7c  mov     [rsp+48h+var_28], 0
0x18003ce85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce8a  mov     rbx, [rsp+48h+arg_0]
0x18003ce8f  mov     rsi, [rsp+48h+arg_8]
0x18003ce94  add     rsp, 40h
0x18003ce98  pop     rdi
0x18003ce99  retn
```
