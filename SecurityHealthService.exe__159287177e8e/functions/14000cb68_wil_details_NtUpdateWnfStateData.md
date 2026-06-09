# wil_details_NtUpdateWnfStateData

- ea: `0x14000cb68`
- end: `0x14000cc12`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x14000ab00`
- `0x14000c898`

## callees

- `0x14000cb68`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000cb9f`
- `KERNEL32!GetModuleHandleW` at `0x14000cb9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000cbb6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000cbb6`

## string_xrefs

- `0x14000cb98`: `ntdll.dll`
- `0x14000cbac`: `NtUpdateWnfStateData`

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
0x14000cb68  mov     [rsp+arg_0], rbx
0x14000cb6d  mov     [rsp+arg_8], rsi
0x14000cb72  push    rdi
0x14000cb73  sub     rsp, 40h
0x14000cb77  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14000cb7e  mov     ebx, r8d
0x14000cb81  mov     rdi, rdx
0x14000cb84  mov     rsi, rcx
0x14000cb87  test    r10, r10
0x14000cb8a  jnz     short loc_14000CBD2
0x14000cb8c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000cb93  test    rax, rax
0x14000cb96  jnz     short loc_14000CBAC
0x14000cb98  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000cb9f  call    cs:__imp_GetModuleHandleW
0x14000cba5  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000cbac  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000cbb3  mov     rcx, rax; hModule
0x14000cbb6  call    cs:__imp_GetProcAddress
0x14000cbbc  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000cbc3  mov     r10, rax
0x14000cbc6  test    rax, rax
0x14000cbc9  jnz     short loc_14000CBD2
0x14000cbcb  mov     eax, 0C0000139h
0x14000cbd0  jmp     short loc_14000CC02
0x14000cbd2  mov     eax, [rsp+48h+arg_30]
0x14000cbd9  xor     r9d, r9d
0x14000cbdc  mov     [rsp+48h+var_18], eax
0x14000cbe0  mov     r8d, ebx
0x14000cbe3  mov     eax, [rsp+48h+arg_28]
0x14000cbe7  mov     rdx, rdi
0x14000cbea  mov     [rsp+48h+var_20], eax
0x14000cbee  mov     rcx, rsi
0x14000cbf1  mov     rax, r10
0x14000cbf4  mov     [rsp+48h+var_28], 0
0x14000cbfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc02  mov     rbx, [rsp+48h+arg_0]
0x14000cc07  mov     rsi, [rsp+48h+arg_8]
0x14000cc0c  add     rsp, 40h
0x14000cc10  pop     rdi
0x14000cc11  retn
```
