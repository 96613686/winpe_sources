# wil_details_NtUpdateWnfStateData

- ea: `0x1400137a0`
- end: `0x14001384a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x14001192c`
- `0x140013368`

## callees

- `0x1400137a0`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400137d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400137d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400137ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400137ee`

## string_xrefs

- `0x1400137d0`: `ntdll.dll`
- `0x1400137e4`: `NtUpdateWnfStateData`

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
0x1400137a0  mov     [rsp+arg_0], rbx
0x1400137a5  mov     [rsp+arg_8], rsi
0x1400137aa  push    rdi
0x1400137ab  sub     rsp, 40h
0x1400137af  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1400137b6  mov     ebx, r8d
0x1400137b9  mov     rdi, rdx
0x1400137bc  mov     rsi, rcx
0x1400137bf  test    r10, r10
0x1400137c2  jnz     short loc_14001380A
0x1400137c4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400137cb  test    rax, rax
0x1400137ce  jnz     short loc_1400137E4
0x1400137d0  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1400137d7  call    cs:__imp_GetModuleHandleW
0x1400137dd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400137e4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1400137eb  mov     rcx, rax; hModule
0x1400137ee  call    cs:__imp_GetProcAddress
0x1400137f4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1400137fb  mov     r10, rax
0x1400137fe  test    rax, rax
0x140013801  jnz     short loc_14001380A
0x140013803  mov     eax, 0C0000139h
0x140013808  jmp     short loc_14001383A
0x14001380a  mov     eax, [rsp+48h+arg_30]
0x140013811  xor     r9d, r9d
0x140013814  mov     [rsp+48h+var_18], eax
0x140013818  mov     r8d, ebx
0x14001381b  mov     eax, [rsp+48h+arg_28]
0x14001381f  mov     rdx, rdi
0x140013822  mov     [rsp+48h+var_20], eax
0x140013826  mov     rcx, rsi
0x140013829  mov     rax, r10
0x14001382c  mov     [rsp+48h+var_28], 0
0x140013835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001383a  mov     rbx, [rsp+48h+arg_0]
0x14001383f  mov     rsi, [rsp+48h+arg_8]
0x140013844  add     rsp, 40h
0x140013848  pop     rdi
0x140013849  retn
```
