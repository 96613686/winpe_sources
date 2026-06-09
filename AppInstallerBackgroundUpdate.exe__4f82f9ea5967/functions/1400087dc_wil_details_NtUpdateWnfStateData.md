# wil_details_NtUpdateWnfStateData

- ea: `0x1400087dc`
- end: `0x140008886`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140007530`
- `0x1400083b4`

## callees

- `0x1400087dc`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008813`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008813`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000882a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000882a`

## string_xrefs

- `0x14000880c`: `ntdll.dll`
- `0x140008820`: `NtUpdateWnfStateData`

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
0x1400087dc  mov     [rsp+arg_0], rbx
0x1400087e1  mov     [rsp+arg_8], rsi
0x1400087e6  push    rdi
0x1400087e7  sub     rsp, 40h
0x1400087eb  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1400087f2  mov     ebx, r8d
0x1400087f5  mov     rdi, rdx
0x1400087f8  mov     rsi, rcx
0x1400087fb  test    r10, r10
0x1400087fe  jnz     short loc_140008846
0x140008800  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008807  test    rax, rax
0x14000880a  jnz     short loc_140008820
0x14000880c  lea     rcx, ModuleName; "ntdll.dll"
0x140008813  call    cs:__imp_GetModuleHandleW
0x140008819  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008820  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x140008827  mov     rcx, rax; hModule
0x14000882a  call    cs:__imp_GetProcAddress
0x140008830  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x140008837  mov     r10, rax
0x14000883a  test    rax, rax
0x14000883d  jnz     short loc_140008846
0x14000883f  mov     eax, 0C0000139h
0x140008844  jmp     short loc_140008876
0x140008846  mov     eax, [rsp+48h+arg_30]
0x14000884d  xor     r9d, r9d
0x140008850  mov     [rsp+48h+var_18], eax
0x140008854  mov     r8d, ebx
0x140008857  mov     eax, [rsp+48h+arg_28]
0x14000885b  mov     rdx, rdi
0x14000885e  mov     [rsp+48h+var_20], eax
0x140008862  mov     rcx, rsi
0x140008865  mov     rax, r10
0x140008868  mov     [rsp+48h+var_28], 0
0x140008871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008876  mov     rbx, [rsp+48h+arg_0]
0x14000887b  mov     rsi, [rsp+48h+arg_8]
0x140008880  add     rsp, 40h
0x140008884  pop     rdi
0x140008885  retn
```
