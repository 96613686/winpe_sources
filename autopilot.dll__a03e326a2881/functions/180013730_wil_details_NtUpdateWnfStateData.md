# wil_details_NtUpdateWnfStateData

- ea: `0x180013730`
- end: `0x1800137da`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000f8c8`
- `0x1800124d8`

## callees

- `0x180013730`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013767`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013767`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001377e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001377e`

## string_xrefs

- `0x180013760`: `ntdll.dll`
- `0x180013774`: `NtUpdateWnfStateData`

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
0x180013730  mov     [rsp+arg_0], rbx
0x180013735  mov     [rsp+arg_8], rsi
0x18001373a  push    rdi
0x18001373b  sub     rsp, 40h
0x18001373f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180013746  mov     ebx, r8d
0x180013749  mov     rdi, rdx
0x18001374c  mov     rsi, rcx
0x18001374f  test    r10, r10
0x180013752  jnz     short loc_18001379A
0x180013754  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001375b  test    rax, rax
0x18001375e  jnz     short loc_180013774
0x180013760  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180013767  call    cs:__imp_GetModuleHandleW
0x18001376d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180013774  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001377b  mov     rcx, rax; hModule
0x18001377e  call    cs:__imp_GetProcAddress
0x180013784  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001378b  mov     r10, rax
0x18001378e  test    rax, rax
0x180013791  jnz     short loc_18001379A
0x180013793  mov     eax, 0C0000139h
0x180013798  jmp     short loc_1800137CA
0x18001379a  mov     eax, [rsp+48h+arg_30]
0x1800137a1  xor     r9d, r9d
0x1800137a4  mov     [rsp+48h+var_18], eax
0x1800137a8  mov     r8d, ebx
0x1800137ab  mov     eax, [rsp+48h+arg_28]
0x1800137af  mov     rdx, rdi
0x1800137b2  mov     [rsp+48h+var_20], eax
0x1800137b6  mov     rcx, rsi
0x1800137b9  mov     rax, r10
0x1800137bc  mov     [rsp+48h+var_28], 0
0x1800137c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137ca  mov     rbx, [rsp+48h+arg_0]
0x1800137cf  mov     rsi, [rsp+48h+arg_8]
0x1800137d4  add     rsp, 40h
0x1800137d8  pop     rdi
0x1800137d9  retn
```
