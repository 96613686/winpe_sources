# wil_details_NtUpdateWnfStateData

- ea: `0x18000edbc`
- end: `0x18000ee66`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000d7f0`
- `0x18000eb7c`

## callees

- `0x18000edbc`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ee0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ee0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000edf3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000edf3`

## string_xrefs

- `0x18000edec`: `ntdll.dll`
- `0x18000ee00`: `NtUpdateWnfStateData`

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
0x18000edbc  mov     [rsp+arg_0], rbx
0x18000edc1  mov     [rsp+arg_8], rsi
0x18000edc6  push    rdi
0x18000edc7  sub     rsp, 40h
0x18000edcb  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000edd2  mov     ebx, r8d
0x18000edd5  mov     rdi, rdx
0x18000edd8  mov     rsi, rcx
0x18000eddb  test    r10, r10
0x18000edde  jnz     short loc_18000EE26
0x18000ede0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ede7  test    rax, rax
0x18000edea  jnz     short loc_18000EE00
0x18000edec  lea     rcx, ModuleName; "ntdll.dll"
0x18000edf3  call    cs:__imp_GetModuleHandleW
0x18000edf9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ee00  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000ee07  mov     rcx, rax; hModule
0x18000ee0a  call    cs:__imp_GetProcAddress
0x18000ee10  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000ee17  mov     r10, rax
0x18000ee1a  test    rax, rax
0x18000ee1d  jnz     short loc_18000EE26
0x18000ee1f  mov     eax, 0C0000139h
0x18000ee24  jmp     short loc_18000EE56
0x18000ee26  mov     eax, [rsp+48h+arg_30]
0x18000ee2d  xor     r9d, r9d
0x18000ee30  mov     [rsp+48h+var_18], eax
0x18000ee34  mov     r8d, ebx
0x18000ee37  mov     eax, [rsp+48h+arg_28]
0x18000ee3b  mov     rdx, rdi
0x18000ee3e  mov     [rsp+48h+var_20], eax
0x18000ee42  mov     rcx, rsi
0x18000ee45  mov     rax, r10
0x18000ee48  mov     [rsp+48h+var_28], 0
0x18000ee51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee56  mov     rbx, [rsp+48h+arg_0]
0x18000ee5b  mov     rsi, [rsp+48h+arg_8]
0x18000ee60  add     rsp, 40h
0x18000ee64  pop     rdi
0x18000ee65  retn
```
