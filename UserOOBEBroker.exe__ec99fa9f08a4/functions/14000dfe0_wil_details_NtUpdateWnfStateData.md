# wil_details_NtUpdateWnfStateData

- ea: `0x14000dfe0`
- end: `0x14000e08a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x14000ba10`
- `0x14000d8b0`

## callees

- `0x14000dfe0`
- `0x14000f010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000e02e`
- `KERNEL32!GetProcAddress` at `0x14000e02e`
- `KERNEL32!GetModuleHandleW` at `0x14000e017`
- `KERNEL32!GetModuleHandleW` at `0x14000e017`

## string_xrefs

- `0x14000e010`: `ntdll.dll`
- `0x14000e024`: `NtUpdateWnfStateData`

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
0x14000dfe0  mov     [rsp+arg_0], rbx
0x14000dfe5  mov     [rsp+arg_8], rsi
0x14000dfea  push    rdi
0x14000dfeb  sub     rsp, 40h
0x14000dfef  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14000dff6  mov     ebx, r8d
0x14000dff9  mov     rdi, rdx
0x14000dffc  mov     rsi, rcx
0x14000dfff  test    r10, r10
0x14000e002  jnz     short loc_14000E04A
0x14000e004  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000e00b  test    rax, rax
0x14000e00e  jnz     short loc_14000E024
0x14000e010  lea     rcx, ModuleName; "ntdll.dll"
0x14000e017  call    cs:__imp_GetModuleHandleW
0x14000e01d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000e024  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000e02b  mov     rcx, rax; hModule
0x14000e02e  call    cs:__imp_GetProcAddress
0x14000e034  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000e03b  mov     r10, rax
0x14000e03e  test    rax, rax
0x14000e041  jnz     short loc_14000E04A
0x14000e043  mov     eax, 0C0000139h
0x14000e048  jmp     short loc_14000E07A
0x14000e04a  mov     eax, [rsp+48h+arg_30]
0x14000e051  xor     r9d, r9d
0x14000e054  mov     [rsp+48h+var_18], eax
0x14000e058  mov     r8d, ebx
0x14000e05b  mov     eax, [rsp+48h+arg_28]
0x14000e05f  mov     rdx, rdi
0x14000e062  mov     [rsp+48h+var_20], eax
0x14000e066  mov     rcx, rsi
0x14000e069  mov     rax, r10
0x14000e06c  mov     [rsp+48h+var_28], 0
0x14000e075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e07a  mov     rbx, [rsp+48h+arg_0]
0x14000e07f  mov     rsi, [rsp+48h+arg_8]
0x14000e084  add     rsp, 40h
0x14000e088  pop     rdi
0x14000e089  retn
```
