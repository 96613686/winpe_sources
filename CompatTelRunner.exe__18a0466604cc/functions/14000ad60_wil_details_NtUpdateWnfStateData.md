# wil_details_NtUpdateWnfStateData

- ea: `0x14000ad60`
- end: `0x14000ae0a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140007f4c`
- `0x14000a5b8`

## callees

- `0x14000ad60`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ad97`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ad97`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000adae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000adae`

## string_xrefs

- `0x14000ad90`: `ntdll.dll`
- `0x14000ada4`: `NtUpdateWnfStateData`

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
0x14000ad60  mov     [rsp+arg_0], rbx
0x14000ad65  mov     [rsp+arg_8], rsi
0x14000ad6a  push    rdi
0x14000ad6b  sub     rsp, 40h
0x14000ad6f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14000ad76  mov     ebx, r8d
0x14000ad79  mov     rdi, rdx
0x14000ad7c  mov     rsi, rcx
0x14000ad7f  test    r10, r10
0x14000ad82  jnz     short loc_14000ADCA
0x14000ad84  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000ad8b  test    rax, rax
0x14000ad8e  jnz     short loc_14000ADA4
0x14000ad90  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000ad97  call    cs:__imp_GetModuleHandleW
0x14000ad9d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000ada4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000adab  mov     rcx, rax; hModule
0x14000adae  call    cs:__imp_GetProcAddress
0x14000adb4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000adbb  mov     r10, rax
0x14000adbe  test    rax, rax
0x14000adc1  jnz     short loc_14000ADCA
0x14000adc3  mov     eax, 0C0000139h
0x14000adc8  jmp     short loc_14000ADFA
0x14000adca  mov     eax, [rsp+48h+arg_30]
0x14000add1  xor     r9d, r9d
0x14000add4  mov     [rsp+48h+var_18], eax
0x14000add8  mov     r8d, ebx
0x14000addb  mov     eax, [rsp+48h+arg_28]
0x14000addf  mov     rdx, rdi
0x14000ade2  mov     [rsp+48h+var_20], eax
0x14000ade6  mov     rcx, rsi
0x14000ade9  mov     rax, r10
0x14000adec  mov     [rsp+48h+var_28], 0
0x14000adf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000adfa  mov     rbx, [rsp+48h+arg_0]
0x14000adff  mov     rsi, [rsp+48h+arg_8]
0x14000ae04  add     rsp, 40h
0x14000ae08  pop     rdi
0x14000ae09  retn
```
