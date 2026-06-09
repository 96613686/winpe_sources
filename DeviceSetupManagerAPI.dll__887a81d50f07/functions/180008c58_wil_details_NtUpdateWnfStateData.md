# wil_details_NtUpdateWnfStateData

- ea: `0x180008c58`
- end: `0x180008d02`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000693c`
- `0x180008988`

## callees

- `0x180008c58`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008ca6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008ca6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008c8f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008c8f`

## string_xrefs

- `0x180008c88`: `ntdll.dll`
- `0x180008c9c`: `NtUpdateWnfStateData`

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
0x180008c58  mov     [rsp+arg_0], rbx
0x180008c5d  mov     [rsp+arg_8], rsi
0x180008c62  push    rdi
0x180008c63  sub     rsp, 40h
0x180008c67  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180008c6e  mov     ebx, r8d
0x180008c71  mov     rdi, rdx
0x180008c74  mov     rsi, rcx
0x180008c77  test    r10, r10
0x180008c7a  jnz     short loc_180008CC2
0x180008c7c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008c83  test    rax, rax
0x180008c86  jnz     short loc_180008C9C
0x180008c88  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180008c8f  call    cs:__imp_GetModuleHandleW
0x180008c95  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008c9c  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180008ca3  mov     rcx, rax; hModule
0x180008ca6  call    cs:__imp_GetProcAddress
0x180008cac  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180008cb3  mov     r10, rax
0x180008cb6  test    rax, rax
0x180008cb9  jnz     short loc_180008CC2
0x180008cbb  mov     eax, 0C0000139h
0x180008cc0  jmp     short loc_180008CF2
0x180008cc2  mov     eax, [rsp+48h+arg_30]
0x180008cc9  xor     r9d, r9d
0x180008ccc  mov     [rsp+48h+var_18], eax
0x180008cd0  mov     r8d, ebx
0x180008cd3  mov     eax, [rsp+48h+arg_28]
0x180008cd7  mov     rdx, rdi
0x180008cda  mov     [rsp+48h+var_20], eax
0x180008cde  mov     rcx, rsi
0x180008ce1  mov     rax, r10
0x180008ce4  mov     [rsp+48h+var_28], 0
0x180008ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cf2  mov     rbx, [rsp+48h+arg_0]
0x180008cf7  mov     rsi, [rsp+48h+arg_8]
0x180008cfc  add     rsp, 40h
0x180008d00  pop     rdi
0x180008d01  retn
```
