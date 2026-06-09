# wil_details_NtUpdateWnfStateData

- ea: `0x18000a730`
- end: `0x18000a7da`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000806c`
- `0x18000a268`

## callees

- `0x18000a730`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000a767`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000a767`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000a77e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000a77e`

## string_xrefs

- `0x18000a760`: `ntdll.dll`
- `0x18000a774`: `NtUpdateWnfStateData`

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
0x18000a730  mov     [rsp+arg_0], rbx
0x18000a735  mov     [rsp+arg_8], rsi
0x18000a73a  push    rdi
0x18000a73b  sub     rsp, 40h
0x18000a73f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000a746  mov     ebx, r8d
0x18000a749  mov     rdi, rdx
0x18000a74c  mov     rsi, rcx
0x18000a74f  test    r10, r10
0x18000a752  jnz     short loc_18000A79A
0x18000a754  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a75b  test    rax, rax
0x18000a75e  jnz     short loc_18000A774
0x18000a760  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000a767  call    cs:__imp_GetModuleHandleW
0x18000a76d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a774  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000a77b  mov     rcx, rax; hModule
0x18000a77e  call    cs:__imp_GetProcAddress
0x18000a784  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000a78b  mov     r10, rax
0x18000a78e  test    rax, rax
0x18000a791  jnz     short loc_18000A79A
0x18000a793  mov     eax, 0C0000139h
0x18000a798  jmp     short loc_18000A7CA
0x18000a79a  mov     eax, [rsp+48h+arg_30]
0x18000a7a1  xor     r9d, r9d
0x18000a7a4  mov     [rsp+48h+var_18], eax
0x18000a7a8  mov     r8d, ebx
0x18000a7ab  mov     eax, [rsp+48h+arg_28]
0x18000a7af  mov     rdx, rdi
0x18000a7b2  mov     [rsp+48h+var_20], eax
0x18000a7b6  mov     rcx, rsi
0x18000a7b9  mov     rax, r10
0x18000a7bc  mov     [rsp+48h+var_28], 0
0x18000a7c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7ca  mov     rbx, [rsp+48h+arg_0]
0x18000a7cf  mov     rsi, [rsp+48h+arg_8]
0x18000a7d4  add     rsp, 40h
0x18000a7d8  pop     rdi
0x18000a7d9  retn
```
