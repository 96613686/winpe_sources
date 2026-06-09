# wil_details_NtUpdateWnfStateData

- ea: `0x180010f0c`
- end: `0x180010fc0`
- name: `wil_details_NtUpdateWnfStateData`
- size: `180`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000e094`
- `0x1800109bc`

## callees

- `0x180010f0c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010f60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010f60`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010f43`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010f43`

## string_xrefs

- `0x180010f3c`: `ntdll.dll`
- `0x180010f56`: `NtUpdateWnfStateData`

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
0x180010f0c  mov     [rsp+arg_0], rbx
0x180010f11  mov     [rsp+arg_8], rsi
0x180010f16  push    rdi
0x180010f17  sub     rsp, 40h
0x180010f1b  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180010f22  mov     ebx, r8d
0x180010f25  mov     rdi, rdx
0x180010f28  mov     rsi, rcx
0x180010f2b  test    r10, r10
0x180010f2e  jnz     short loc_180010F82
0x180010f30  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010f37  test    rax, rax
0x180010f3a  jnz     short loc_180010F56
0x180010f3c  lea     rcx, aNtdllDll; "ntdll.dll"
0x180010f43  call    cs:__imp_GetModuleHandleW
0x180010f4a  nop     dword ptr [rax+rax+00h]
0x180010f4f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010f56  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180010f5d  mov     rcx, rax; hModule
0x180010f60  call    cs:__imp_GetProcAddress
0x180010f67  nop     dword ptr [rax+rax+00h]
0x180010f6c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180010f73  mov     r10, rax
0x180010f76  test    rax, rax
0x180010f79  jnz     short loc_180010F82
0x180010f7b  mov     eax, 0C0000139h
0x180010f80  jmp     short loc_180010FAF
0x180010f82  mov     eax, [rsp+48h+arg_30]
0x180010f89  xor     r9d, r9d
0x180010f8c  mov     [rsp+48h+var_18], eax
0x180010f90  mov     r8d, ebx
0x180010f93  mov     eax, [rsp+48h+arg_28]
0x180010f97  mov     rdx, rdi
0x180010f9a  mov     [rsp+48h+var_20], eax
0x180010f9e  mov     rcx, rsi
0x180010fa1  and     [rsp+48h+var_28], 0
0x180010fa7  mov     rax, r10
0x180010faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010faf  mov     rbx, [rsp+48h+arg_0]
0x180010fb4  mov     rsi, [rsp+48h+arg_8]
0x180010fb9  add     rsp, 40h
0x180010fbd  pop     rdi
0x180010fbe  retn
```
