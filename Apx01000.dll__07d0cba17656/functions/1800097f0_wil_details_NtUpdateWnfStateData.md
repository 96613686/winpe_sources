# wil_details_NtUpdateWnfStateData

- ea: `0x1800097f0`
- end: `0x18000989a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800070fc`
- `0x180009328`

## callees

- `0x1800097f0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009827`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009827`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000983e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000983e`

## string_xrefs

- `0x180009820`: `ntdll.dll`
- `0x180009834`: `NtUpdateWnfStateData`

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
0x1800097f0  mov     [rsp+arg_0], rbx
0x1800097f5  mov     [rsp+arg_8], rsi
0x1800097fa  push    rdi
0x1800097fb  sub     rsp, 40h
0x1800097ff  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180009806  mov     ebx, r8d
0x180009809  mov     rdi, rdx
0x18000980c  mov     rsi, rcx
0x18000980f  test    r10, r10
0x180009812  jnz     short loc_18000985A
0x180009814  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000981b  test    rax, rax
0x18000981e  jnz     short loc_180009834
0x180009820  lea     rcx, ModuleName; "ntdll.dll"
0x180009827  call    cs:__imp_GetModuleHandleW
0x18000982d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009834  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000983b  mov     rcx, rax; hModule
0x18000983e  call    cs:__imp_GetProcAddress
0x180009844  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000984b  mov     r10, rax
0x18000984e  test    rax, rax
0x180009851  jnz     short loc_18000985A
0x180009853  mov     eax, 0C0000139h
0x180009858  jmp     short loc_18000988A
0x18000985a  mov     eax, [rsp+48h+arg_30]
0x180009861  xor     r9d, r9d
0x180009864  mov     [rsp+48h+var_18], eax
0x180009868  mov     r8d, ebx
0x18000986b  mov     eax, [rsp+48h+arg_28]
0x18000986f  mov     rdx, rdi
0x180009872  mov     [rsp+48h+var_20], eax
0x180009876  mov     rcx, rsi
0x180009879  mov     rax, r10
0x18000987c  mov     [rsp+48h+var_28], 0
0x180009885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000988a  mov     rbx, [rsp+48h+arg_0]
0x18000988f  mov     rsi, [rsp+48h+arg_8]
0x180009894  add     rsp, 40h
0x180009898  pop     rdi
0x180009899  retn
```
