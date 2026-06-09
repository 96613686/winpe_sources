# wil_details_NtUpdateWnfStateData

- ea: `0x18000d3e0`
- end: `0x18000d48a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000b264`
- `0x18000cfcc`

## callees

- `0x18000d3e0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d417`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d417`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d42e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d42e`

## string_xrefs

- `0x18000d410`: `ntdll.dll`
- `0x18000d424`: `NtUpdateWnfStateData`

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
0x18000d3e0  mov     [rsp+arg_0], rbx
0x18000d3e5  mov     [rsp+arg_8], rsi
0x18000d3ea  push    rdi
0x18000d3eb  sub     rsp, 40h
0x18000d3ef  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000d3f6  mov     ebx, r8d
0x18000d3f9  mov     rdi, rdx
0x18000d3fc  mov     rsi, rcx
0x18000d3ff  test    r10, r10
0x18000d402  jnz     short loc_18000D44A
0x18000d404  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d40b  test    rax, rax
0x18000d40e  jnz     short loc_18000D424
0x18000d410  lea     rcx, ModuleName; "ntdll.dll"
0x18000d417  call    cs:__imp_GetModuleHandleW
0x18000d41d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d424  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000d42b  mov     rcx, rax; hModule
0x18000d42e  call    cs:__imp_GetProcAddress
0x18000d434  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000d43b  mov     r10, rax
0x18000d43e  test    rax, rax
0x18000d441  jnz     short loc_18000D44A
0x18000d443  mov     eax, 0C0000139h
0x18000d448  jmp     short loc_18000D47A
0x18000d44a  mov     eax, [rsp+48h+arg_30]
0x18000d451  xor     r9d, r9d
0x18000d454  mov     [rsp+48h+var_18], eax
0x18000d458  mov     r8d, ebx
0x18000d45b  mov     eax, [rsp+48h+arg_28]
0x18000d45f  mov     rdx, rdi
0x18000d462  mov     [rsp+48h+var_20], eax
0x18000d466  mov     rcx, rsi
0x18000d469  mov     rax, r10
0x18000d46c  mov     [rsp+48h+var_28], 0
0x18000d475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d47a  mov     rbx, [rsp+48h+arg_0]
0x18000d47f  mov     rsi, [rsp+48h+arg_8]
0x18000d484  add     rsp, 40h
0x18000d488  pop     rdi
0x18000d489  retn
```
