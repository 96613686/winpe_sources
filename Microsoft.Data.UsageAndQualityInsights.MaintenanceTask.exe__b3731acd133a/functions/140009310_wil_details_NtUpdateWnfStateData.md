# wil_details_NtUpdateWnfStateData

- ea: `0x140009310`
- end: `0x1400093ba`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140006c1c`
- `0x140008e48`

## callees

- `0x140009310`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009347`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009347`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000935e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000935e`

## string_xrefs

- `0x140009340`: `ntdll.dll`
- `0x140009354`: `NtUpdateWnfStateData`

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
0x140009310  mov     [rsp+arg_0], rbx
0x140009315  mov     [rsp+arg_8], rsi
0x14000931a  push    rdi
0x14000931b  sub     rsp, 40h
0x14000931f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x140009326  mov     ebx, r8d
0x140009329  mov     rdi, rdx
0x14000932c  mov     rsi, rcx
0x14000932f  test    r10, r10
0x140009332  jnz     short loc_14000937A
0x140009334  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000933b  test    rax, rax
0x14000933e  jnz     short loc_140009354
0x140009340  lea     rcx, ModuleName; "ntdll.dll"
0x140009347  call    cs:__imp_GetModuleHandleW
0x14000934d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009354  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000935b  mov     rcx, rax; hModule
0x14000935e  call    cs:__imp_GetProcAddress
0x140009364  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000936b  mov     r10, rax
0x14000936e  test    rax, rax
0x140009371  jnz     short loc_14000937A
0x140009373  mov     eax, 0C0000139h
0x140009378  jmp     short loc_1400093AA
0x14000937a  mov     eax, [rsp+48h+arg_30]
0x140009381  xor     r9d, r9d
0x140009384  mov     [rsp+48h+var_18], eax
0x140009388  mov     r8d, ebx
0x14000938b  mov     eax, [rsp+48h+arg_28]
0x14000938f  mov     rdx, rdi
0x140009392  mov     [rsp+48h+var_20], eax
0x140009396  mov     rcx, rsi
0x140009399  mov     rax, r10
0x14000939c  mov     [rsp+48h+var_28], 0
0x1400093a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400093aa  mov     rbx, [rsp+48h+arg_0]
0x1400093af  mov     rsi, [rsp+48h+arg_8]
0x1400093b4  add     rsp, 40h
0x1400093b8  pop     rdi
0x1400093b9  retn
```
