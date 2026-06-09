# wil_details_NtUpdateWnfStateData

- ea: `0x180010390`
- end: `0x18001043a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000d9bc`
- `0x18000fec8`

## callees

- `0x180010390`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800103c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800103c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800103de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800103de`

## string_xrefs

- `0x1800103c0`: `ntdll.dll`
- `0x1800103d4`: `NtUpdateWnfStateData`

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
0x180010390  mov     [rsp+arg_0], rbx
0x180010395  mov     [rsp+arg_8], rsi
0x18001039a  push    rdi
0x18001039b  sub     rsp, 40h
0x18001039f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800103a6  mov     ebx, r8d
0x1800103a9  mov     rdi, rdx
0x1800103ac  mov     rsi, rcx
0x1800103af  test    r10, r10
0x1800103b2  jnz     short loc_1800103FA
0x1800103b4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800103bb  test    rax, rax
0x1800103be  jnz     short loc_1800103D4
0x1800103c0  lea     rcx, aNtdllDll; "ntdll.dll"
0x1800103c7  call    cs:__imp_GetModuleHandleW
0x1800103cd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800103d4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800103db  mov     rcx, rax; hModule
0x1800103de  call    cs:__imp_GetProcAddress
0x1800103e4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800103eb  mov     r10, rax
0x1800103ee  test    rax, rax
0x1800103f1  jnz     short loc_1800103FA
0x1800103f3  mov     eax, 0C0000139h
0x1800103f8  jmp     short loc_18001042A
0x1800103fa  mov     eax, [rsp+48h+arg_30]
0x180010401  xor     r9d, r9d
0x180010404  mov     [rsp+48h+var_18], eax
0x180010408  mov     r8d, ebx
0x18001040b  mov     eax, [rsp+48h+arg_28]
0x18001040f  mov     rdx, rdi
0x180010412  mov     [rsp+48h+var_20], eax
0x180010416  mov     rcx, rsi
0x180010419  mov     rax, r10
0x18001041c  mov     [rsp+48h+var_28], 0
0x180010425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001042a  mov     rbx, [rsp+48h+arg_0]
0x18001042f  mov     rsi, [rsp+48h+arg_8]
0x180010434  add     rsp, 40h
0x180010438  pop     rdi
0x180010439  retn
```
