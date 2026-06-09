# wil_details_NtUpdateWnfStateData

- ea: `0x180013ab4`
- end: `0x180013b6b`
- name: `wil_details_NtUpdateWnfStateData`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000f9b8`
- `0x18001277c`

## callees

- `0x180013ab4`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013aeb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013aeb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013b08`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013b08`

## string_xrefs

- `0x180013ae4`: `ntdll.dll`
- `0x180013afe`: `NtUpdateWnfStateData`

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
0x180013ab4  mov     [rsp+arg_0], rbx
0x180013ab9  mov     [rsp+arg_8], rsi
0x180013abe  push    rdi
0x180013abf  sub     rsp, 40h
0x180013ac3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180013aca  mov     ebx, r8d
0x180013acd  mov     rdi, rdx
0x180013ad0  mov     rsi, rcx
0x180013ad3  test    r10, r10
0x180013ad6  jnz     short loc_180013B2A
0x180013ad8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180013adf  test    rax, rax
0x180013ae2  jnz     short loc_180013AFE
0x180013ae4  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180013aeb  call    cs:__imp_GetModuleHandleW
0x180013af2  nop     dword ptr [rax+rax+00h]
0x180013af7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180013afe  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180013b05  mov     rcx, rax; hModule
0x180013b08  call    cs:__imp_GetProcAddress
0x180013b0f  nop     dword ptr [rax+rax+00h]
0x180013b14  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180013b1b  mov     r10, rax
0x180013b1e  test    rax, rax
0x180013b21  jnz     short loc_180013B2A
0x180013b23  mov     eax, 0C0000139h
0x180013b28  jmp     short loc_180013B5A
0x180013b2a  mov     eax, [rsp+48h+arg_30]
0x180013b31  xor     r9d, r9d
0x180013b34  mov     [rsp+48h+var_18], eax
0x180013b38  mov     r8d, ebx
0x180013b3b  mov     eax, [rsp+48h+arg_28]
0x180013b3f  mov     rdx, rdi
0x180013b42  mov     [rsp+48h+var_20], eax
0x180013b46  mov     rcx, rsi
0x180013b49  mov     rax, r10
0x180013b4c  mov     [rsp+48h+var_28], 0
0x180013b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b5a  mov     rbx, [rsp+48h+arg_0]
0x180013b5f  mov     rsi, [rsp+48h+arg_8]
0x180013b64  add     rsp, 40h
0x180013b68  pop     rdi
0x180013b69  retn
```
