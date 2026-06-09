# wil_details_NtUpdateWnfStateData

- ea: `0x180031150`
- end: `0x1800311fa`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18002cf80`
- `0x180030780`

## callees

- `0x180031150`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003119e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003119e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180031187`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180031187`

## string_xrefs

- `0x180031180`: `ntdll.dll`
- `0x180031194`: `NtUpdateWnfStateData`

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
0x180031150  mov     [rsp+arg_0], rbx
0x180031155  mov     [rsp+arg_8], rsi
0x18003115a  push    rdi
0x18003115b  sub     rsp, 40h
0x18003115f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180031166  mov     ebx, r8d
0x180031169  mov     rdi, rdx
0x18003116c  mov     rsi, rcx
0x18003116f  test    r10, r10
0x180031172  jnz     short loc_1800311BA
0x180031174  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003117b  test    rax, rax
0x18003117e  jnz     short loc_180031194
0x180031180  lea     rcx, ModuleName; "ntdll.dll"
0x180031187  call    cs:__imp_GetModuleHandleW
0x18003118d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180031194  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18003119b  mov     rcx, rax; hModule
0x18003119e  call    cs:__imp_GetProcAddress
0x1800311a4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800311ab  mov     r10, rax
0x1800311ae  test    rax, rax
0x1800311b1  jnz     short loc_1800311BA
0x1800311b3  mov     eax, 0C0000139h
0x1800311b8  jmp     short loc_1800311EA
0x1800311ba  mov     eax, [rsp+48h+arg_30]
0x1800311c1  xor     r9d, r9d
0x1800311c4  mov     [rsp+48h+var_18], eax
0x1800311c8  mov     r8d, ebx
0x1800311cb  mov     eax, [rsp+48h+arg_28]
0x1800311cf  mov     rdx, rdi
0x1800311d2  mov     [rsp+48h+var_20], eax
0x1800311d6  mov     rcx, rsi
0x1800311d9  mov     rax, r10
0x1800311dc  mov     [rsp+48h+var_28], 0
0x1800311e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800311ea  mov     rbx, [rsp+48h+arg_0]
0x1800311ef  mov     rsi, [rsp+48h+arg_8]
0x1800311f4  add     rsp, 40h
0x1800311f8  pop     rdi
0x1800311f9  retn
```
