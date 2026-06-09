# wil_details_NtUpdateWnfStateData

- ea: `0x180025074`
- end: `0x18002511e`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800215c8`
- `0x180024e34`

## callees

- `0x180025074`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800250ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800250ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800250c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800250c2`

## string_xrefs

- `0x1800250a4`: `ntdll.dll`
- `0x1800250b8`: `NtUpdateWnfStateData`

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
0x180025074  mov     [rsp+arg_0], rbx
0x180025079  mov     [rsp+arg_8], rsi
0x18002507e  push    rdi
0x18002507f  sub     rsp, 40h
0x180025083  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18002508a  mov     ebx, r8d
0x18002508d  mov     rdi, rdx
0x180025090  mov     rsi, rcx
0x180025093  test    r10, r10
0x180025096  jnz     short loc_1800250DE
0x180025098  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002509f  test    rax, rax
0x1800250a2  jnz     short loc_1800250B8
0x1800250a4  lea     rcx, LibFileName; "ntdll.dll"
0x1800250ab  call    cs:__imp_GetModuleHandleW
0x1800250b1  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800250b8  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800250bf  mov     rcx, rax; hModule
0x1800250c2  call    cs:__imp_GetProcAddress
0x1800250c8  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800250cf  mov     r10, rax
0x1800250d2  test    rax, rax
0x1800250d5  jnz     short loc_1800250DE
0x1800250d7  mov     eax, 0C0000139h
0x1800250dc  jmp     short loc_18002510E
0x1800250de  mov     eax, [rsp+48h+arg_30]
0x1800250e5  xor     r9d, r9d
0x1800250e8  mov     [rsp+48h+var_18], eax
0x1800250ec  mov     r8d, ebx
0x1800250ef  mov     eax, [rsp+48h+arg_28]
0x1800250f3  mov     rdx, rdi
0x1800250f6  mov     [rsp+48h+var_20], eax
0x1800250fa  mov     rcx, rsi
0x1800250fd  mov     rax, r10
0x180025100  mov     [rsp+48h+var_28], 0
0x180025109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002510e  mov     rbx, [rsp+48h+arg_0]
0x180025113  mov     rsi, [rsp+48h+arg_8]
0x180025118  add     rsp, 40h
0x18002511c  pop     rdi
0x18002511d  retn
```
