# wil_details_NtUpdateWnfStateData

- ea: `0x1800eceb0`
- end: `0x1800ecf5a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800ea008`
- `0x1800ec938`

## callees

- `0x1800eceb0`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ecefe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ecefe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ecee7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ecee7`

## string_xrefs

- `0x1800ecee0`: `ntdll.dll`
- `0x1800ecef4`: `NtUpdateWnfStateData`

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
0x1800eceb0  mov     [rsp+arg_0], rbx
0x1800eceb5  mov     [rsp+arg_8], rsi
0x1800eceba  push    rdi
0x1800ecebb  sub     rsp, 40h
0x1800ecebf  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800ecec6  mov     ebx, r8d
0x1800ecec9  mov     rdi, rdx
0x1800ececc  mov     rsi, rcx
0x1800ececf  test    r10, r10
0x1800eced2  jnz     short loc_1800ECF1A
0x1800eced4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800ecedb  test    rax, rax
0x1800ecede  jnz     short loc_1800ECEF4
0x1800ecee0  lea     rcx, ModuleName; "ntdll.dll"
0x1800ecee7  call    cs:__imp_GetModuleHandleW
0x1800eceed  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800ecef4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800ecefb  mov     rcx, rax; hModule
0x1800ecefe  call    cs:__imp_GetProcAddress
0x1800ecf04  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800ecf0b  mov     r10, rax
0x1800ecf0e  test    rax, rax
0x1800ecf11  jnz     short loc_1800ECF1A
0x1800ecf13  mov     eax, 0C0000139h
0x1800ecf18  jmp     short loc_1800ECF4A
0x1800ecf1a  mov     eax, [rsp+48h+arg_30]
0x1800ecf21  xor     r9d, r9d
0x1800ecf24  mov     [rsp+48h+var_18], eax
0x1800ecf28  mov     r8d, ebx
0x1800ecf2b  mov     eax, [rsp+48h+arg_28]
0x1800ecf2f  mov     rdx, rdi
0x1800ecf32  mov     [rsp+48h+var_20], eax
0x1800ecf36  mov     rcx, rsi
0x1800ecf39  mov     rax, r10
0x1800ecf3c  mov     [rsp+48h+var_28], 0
0x1800ecf45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ecf4a  mov     rbx, [rsp+48h+arg_0]
0x1800ecf4f  mov     rsi, [rsp+48h+arg_8]
0x1800ecf54  add     rsp, 40h
0x1800ecf58  pop     rdi
0x1800ecf59  retn
```
