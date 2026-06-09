# wil_details_NtUpdateWnfStateData

- ea: `0x1800220e0`
- end: `0x180022197`
- name: `wil_details_NtUpdateWnfStateData`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18001a4d8`
- `0x180021e5c`

## callees

- `0x1800220e0`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022117`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022117`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022134`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022134`

## string_xrefs

- `0x180022110`: `ntdll.dll`
- `0x18002212a`: `NtUpdateWnfStateData`

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
0x1800220e0  mov     [rsp+arg_0], rbx
0x1800220e5  mov     [rsp+arg_8], rsi
0x1800220ea  push    rdi
0x1800220eb  sub     rsp, 40h
0x1800220ef  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800220f6  mov     ebx, r8d
0x1800220f9  mov     rdi, rdx
0x1800220fc  mov     rsi, rcx
0x1800220ff  test    r10, r10
0x180022102  jnz     short loc_180022156
0x180022104  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002210b  test    rax, rax
0x18002210e  jnz     short loc_18002212A
0x180022110  lea     rcx, ModuleName; "ntdll.dll"
0x180022117  call    cs:__imp_GetModuleHandleW
0x18002211e  nop     dword ptr [rax+rax+00h]
0x180022123  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002212a  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180022131  mov     rcx, rax; hModule
0x180022134  call    cs:__imp_GetProcAddress
0x18002213b  nop     dword ptr [rax+rax+00h]
0x180022140  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180022147  mov     r10, rax
0x18002214a  test    rax, rax
0x18002214d  jnz     short loc_180022156
0x18002214f  mov     eax, 0C0000139h
0x180022154  jmp     short loc_180022186
0x180022156  mov     eax, [rsp+48h+arg_30]
0x18002215d  xor     r9d, r9d
0x180022160  mov     [rsp+48h+var_18], eax
0x180022164  mov     r8d, ebx
0x180022167  mov     eax, [rsp+48h+arg_28]
0x18002216b  mov     rdx, rdi
0x18002216e  mov     [rsp+48h+var_20], eax
0x180022172  mov     rcx, rsi
0x180022175  mov     rax, r10
0x180022178  mov     [rsp+48h+var_28], 0
0x180022181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022186  mov     rbx, [rsp+48h+arg_0]
0x18002218b  mov     rsi, [rsp+48h+arg_8]
0x180022190  add     rsp, 40h
0x180022194  pop     rdi
0x180022195  retn
```
