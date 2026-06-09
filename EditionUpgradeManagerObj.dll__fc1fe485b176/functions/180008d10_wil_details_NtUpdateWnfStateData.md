# wil_details_NtUpdateWnfStateData

- ea: `0x180008d10`
- end: `0x180008dba`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180006d88`
- `0x180008854`

## callees

- `0x180008d10`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008d5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008d5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008d47`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008d47`

## string_xrefs

- `0x180008d40`: `ntdll.dll`
- `0x180008d54`: `NtUpdateWnfStateData`

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
0x180008d10  mov     [rsp+arg_0], rbx
0x180008d15  mov     [rsp+arg_8], rsi
0x180008d1a  push    rdi
0x180008d1b  sub     rsp, 40h
0x180008d1f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180008d26  mov     ebx, r8d
0x180008d29  mov     rdi, rdx
0x180008d2c  mov     rsi, rcx
0x180008d2f  test    r10, r10
0x180008d32  jnz     short loc_180008D7A
0x180008d34  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008d3b  test    rax, rax
0x180008d3e  jnz     short loc_180008D54
0x180008d40  lea     rcx, ModuleName; "ntdll.dll"
0x180008d47  call    cs:__imp_GetModuleHandleW
0x180008d4d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008d54  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180008d5b  mov     rcx, rax; hModule
0x180008d5e  call    cs:__imp_GetProcAddress
0x180008d64  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180008d6b  mov     r10, rax
0x180008d6e  test    rax, rax
0x180008d71  jnz     short loc_180008D7A
0x180008d73  mov     eax, 0C0000139h
0x180008d78  jmp     short loc_180008DAA
0x180008d7a  mov     eax, [rsp+48h+arg_30]
0x180008d81  xor     r9d, r9d
0x180008d84  mov     [rsp+48h+var_18], eax
0x180008d88  mov     r8d, ebx
0x180008d8b  mov     eax, [rsp+48h+arg_28]
0x180008d8f  mov     rdx, rdi
0x180008d92  mov     [rsp+48h+var_20], eax
0x180008d96  mov     rcx, rsi
0x180008d99  mov     rax, r10
0x180008d9c  mov     [rsp+48h+var_28], 0
0x180008da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008daa  mov     rbx, [rsp+48h+arg_0]
0x180008daf  mov     rsi, [rsp+48h+arg_8]
0x180008db4  add     rsp, 40h
0x180008db8  pop     rdi
0x180008db9  retn
```
