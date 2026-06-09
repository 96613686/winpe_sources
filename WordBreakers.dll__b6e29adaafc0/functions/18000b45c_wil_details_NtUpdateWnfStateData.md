# wil_details_NtUpdateWnfStateData

- ea: `0x18000b45c`
- end: `0x18000b506`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180009f90`
- `0x18000b0a0`

## callees

- `0x18000b45c`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b4aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b4aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b493`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b493`

## string_xrefs

- `0x18000b48c`: `ntdll.dll`
- `0x18000b4a0`: `NtUpdateWnfStateData`

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
0x18000b45c  mov     [rsp+arg_0], rbx
0x18000b461  mov     [rsp+arg_8], rsi
0x18000b466  push    rdi
0x18000b467  sub     rsp, 40h
0x18000b46b  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000b472  mov     ebx, r8d
0x18000b475  mov     rdi, rdx
0x18000b478  mov     rsi, rcx
0x18000b47b  test    r10, r10
0x18000b47e  jnz     short loc_18000B4C6
0x18000b480  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b487  test    rax, rax
0x18000b48a  jnz     short loc_18000B4A0
0x18000b48c  lea     rcx, ModuleName; "ntdll.dll"
0x18000b493  call    cs:__imp_GetModuleHandleW
0x18000b499  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b4a0  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000b4a7  mov     rcx, rax; hModule
0x18000b4aa  call    cs:__imp_GetProcAddress
0x18000b4b0  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000b4b7  mov     r10, rax
0x18000b4ba  test    rax, rax
0x18000b4bd  jnz     short loc_18000B4C6
0x18000b4bf  mov     eax, 0C0000139h
0x18000b4c4  jmp     short loc_18000B4F6
0x18000b4c6  mov     eax, [rsp+48h+arg_30]
0x18000b4cd  xor     r9d, r9d
0x18000b4d0  mov     [rsp+48h+var_18], eax
0x18000b4d4  mov     r8d, ebx
0x18000b4d7  mov     eax, [rsp+48h+arg_28]
0x18000b4db  mov     rdx, rdi
0x18000b4de  mov     [rsp+48h+var_20], eax
0x18000b4e2  mov     rcx, rsi
0x18000b4e5  mov     rax, r10
0x18000b4e8  mov     [rsp+48h+var_28], 0
0x18000b4f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4f6  mov     rbx, [rsp+48h+arg_0]
0x18000b4fb  mov     rsi, [rsp+48h+arg_8]
0x18000b500  add     rsp, 40h
0x18000b504  pop     rdi
0x18000b505  retn
```
