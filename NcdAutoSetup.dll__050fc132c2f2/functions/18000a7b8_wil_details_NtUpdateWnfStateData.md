# wil_details_NtUpdateWnfStateData

- ea: `0x18000a7b8`
- end: `0x18000a862`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180006b98`
- `0x18000a270`

## callees

- `0x18000a7b8`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a7ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a7ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a806`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a806`

## string_xrefs

- `0x18000a7e8`: `ntdll.dll`
- `0x18000a7fc`: `NtUpdateWnfStateData`

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
0x18000a7b8  mov     [rsp+arg_0], rbx
0x18000a7bd  mov     [rsp+arg_8], rsi
0x18000a7c2  push    rdi
0x18000a7c3  sub     rsp, 40h
0x18000a7c7  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000a7ce  mov     ebx, r8d
0x18000a7d1  mov     rdi, rdx
0x18000a7d4  mov     rsi, rcx
0x18000a7d7  test    r10, r10
0x18000a7da  jnz     short loc_18000A822
0x18000a7dc  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a7e3  test    rax, rax
0x18000a7e6  jnz     short loc_18000A7FC
0x18000a7e8  lea     rcx, ModuleName; "ntdll.dll"
0x18000a7ef  call    cs:__imp_GetModuleHandleW
0x18000a7f5  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a7fc  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000a803  mov     rcx, rax; hModule
0x18000a806  call    cs:__imp_GetProcAddress
0x18000a80c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000a813  mov     r10, rax
0x18000a816  test    rax, rax
0x18000a819  jnz     short loc_18000A822
0x18000a81b  mov     eax, 0C0000139h
0x18000a820  jmp     short loc_18000A852
0x18000a822  mov     eax, [rsp+48h+arg_30]
0x18000a829  xor     r9d, r9d
0x18000a82c  mov     [rsp+48h+var_18], eax
0x18000a830  mov     r8d, ebx
0x18000a833  mov     eax, [rsp+48h+arg_28]
0x18000a837  mov     rdx, rdi
0x18000a83a  mov     [rsp+48h+var_20], eax
0x18000a83e  mov     rcx, rsi
0x18000a841  mov     rax, r10
0x18000a844  mov     [rsp+48h+var_28], 0
0x18000a84d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a852  mov     rbx, [rsp+48h+arg_0]
0x18000a857  mov     rsi, [rsp+48h+arg_8]
0x18000a85c  add     rsp, 40h
0x18000a860  pop     rdi
0x18000a861  retn
```
