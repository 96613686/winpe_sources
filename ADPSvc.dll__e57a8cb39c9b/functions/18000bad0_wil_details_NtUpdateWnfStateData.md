# wil_details_NtUpdateWnfStateData

- ea: `0x18000bad0`
- end: `0x18000bb7a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000a4b8`
- `0x18000b684`

## callees

- `0x18000bad0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bb07`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bb07`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bb1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bb1e`

## string_xrefs

- `0x18000bb00`: `ntdll.dll`
- `0x18000bb14`: `NtUpdateWnfStateData`

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
0x18000bad0  mov     [rsp+arg_0], rbx
0x18000bad5  mov     [rsp+arg_8], rsi
0x18000bada  push    rdi
0x18000badb  sub     rsp, 40h
0x18000badf  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000bae6  mov     ebx, r8d
0x18000bae9  mov     rdi, rdx
0x18000baec  mov     rsi, rcx
0x18000baef  test    r10, r10
0x18000baf2  jnz     short loc_18000BB3A
0x18000baf4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bafb  test    rax, rax
0x18000bafe  jnz     short loc_18000BB14
0x18000bb00  lea     rcx, ModuleName; "ntdll.dll"
0x18000bb07  call    cs:__imp_GetModuleHandleW
0x18000bb0d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bb14  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000bb1b  mov     rcx, rax; hModule
0x18000bb1e  call    cs:__imp_GetProcAddress
0x18000bb24  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000bb2b  mov     r10, rax
0x18000bb2e  test    rax, rax
0x18000bb31  jnz     short loc_18000BB3A
0x18000bb33  mov     eax, 0C0000139h
0x18000bb38  jmp     short loc_18000BB6A
0x18000bb3a  mov     eax, [rsp+48h+arg_30]
0x18000bb41  xor     r9d, r9d
0x18000bb44  mov     [rsp+48h+var_18], eax
0x18000bb48  mov     r8d, ebx
0x18000bb4b  mov     eax, [rsp+48h+arg_28]
0x18000bb4f  mov     rdx, rdi
0x18000bb52  mov     [rsp+48h+var_20], eax
0x18000bb56  mov     rcx, rsi
0x18000bb59  mov     rax, r10
0x18000bb5c  mov     [rsp+48h+var_28], 0
0x18000bb65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb6a  mov     rbx, [rsp+48h+arg_0]
0x18000bb6f  mov     rsi, [rsp+48h+arg_8]
0x18000bb74  add     rsp, 40h
0x18000bb78  pop     rdi
0x18000bb79  retn
```
