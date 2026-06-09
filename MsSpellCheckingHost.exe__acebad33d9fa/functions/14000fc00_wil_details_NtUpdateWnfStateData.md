# wil_details_NtUpdateWnfStateData

- ea: `0x14000fc00`
- end: `0x14000fcaa`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x14000cb30`
- `0x14000f770`

## callees

- `0x14000fc00`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000fc37`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000fc37`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000fc4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000fc4e`

## string_xrefs

- `0x14000fc30`: `ntdll.dll`
- `0x14000fc44`: `NtUpdateWnfStateData`

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
0x14000fc00  mov     [rsp+arg_0], rbx
0x14000fc05  mov     [rsp+arg_8], rsi
0x14000fc0a  push    rdi
0x14000fc0b  sub     rsp, 40h
0x14000fc0f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14000fc16  mov     ebx, r8d
0x14000fc19  mov     rdi, rdx
0x14000fc1c  mov     rsi, rcx
0x14000fc1f  test    r10, r10
0x14000fc22  jnz     short loc_14000FC6A
0x14000fc24  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000fc2b  test    rax, rax
0x14000fc2e  jnz     short loc_14000FC44
0x14000fc30  lea     rcx, aNtdllDll; "ntdll.dll"
0x14000fc37  call    cs:__imp_GetModuleHandleW
0x14000fc3d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000fc44  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000fc4b  mov     rcx, rax; hModule
0x14000fc4e  call    cs:__imp_GetProcAddress
0x14000fc54  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000fc5b  mov     r10, rax
0x14000fc5e  test    rax, rax
0x14000fc61  jnz     short loc_14000FC6A
0x14000fc63  mov     eax, 0C0000139h
0x14000fc68  jmp     short loc_14000FC9A
0x14000fc6a  mov     eax, [rsp+48h+arg_30]
0x14000fc71  xor     r9d, r9d
0x14000fc74  mov     [rsp+48h+var_18], eax
0x14000fc78  mov     r8d, ebx
0x14000fc7b  mov     eax, [rsp+48h+arg_28]
0x14000fc7f  mov     rdx, rdi
0x14000fc82  mov     [rsp+48h+var_20], eax
0x14000fc86  mov     rcx, rsi
0x14000fc89  mov     rax, r10
0x14000fc8c  mov     [rsp+48h+var_28], 0
0x14000fc95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fc9a  mov     rbx, [rsp+48h+arg_0]
0x14000fc9f  mov     rsi, [rsp+48h+arg_8]
0x14000fca4  add     rsp, 40h
0x14000fca8  pop     rdi
0x14000fca9  retn
```
