# wil_details_NtUpdateWnfStateData

- ea: `0x14000ee14`
- end: `0x14000eebe`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x14000dcc4`
- `0x14000eb6c`

## callees

- `0x14000ee14`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000ee62`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000ee62`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ee4b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ee4b`

## string_xrefs

- `0x14000ee44`: `ntdll.dll`
- `0x14000ee58`: `NtUpdateWnfStateData`

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
0x14000ee14  mov     [rsp+arg_0], rbx
0x14000ee19  mov     [rsp+arg_8], rsi
0x14000ee1e  push    rdi
0x14000ee1f  sub     rsp, 40h
0x14000ee23  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14000ee2a  mov     ebx, r8d
0x14000ee2d  mov     rdi, rdx
0x14000ee30  mov     rsi, rcx
0x14000ee33  test    r10, r10
0x14000ee36  jnz     short loc_14000EE7E
0x14000ee38  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000ee3f  test    rax, rax
0x14000ee42  jnz     short loc_14000EE58
0x14000ee44  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000ee4b  call    cs:__imp_GetModuleHandleW
0x14000ee51  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000ee58  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000ee5f  mov     rcx, rax; hModule
0x14000ee62  call    cs:__imp_GetProcAddress
0x14000ee68  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000ee6f  mov     r10, rax
0x14000ee72  test    rax, rax
0x14000ee75  jnz     short loc_14000EE7E
0x14000ee77  mov     eax, 0C0000139h
0x14000ee7c  jmp     short loc_14000EEAE
0x14000ee7e  mov     eax, [rsp+48h+arg_30]
0x14000ee85  xor     r9d, r9d
0x14000ee88  mov     [rsp+48h+var_18], eax
0x14000ee8c  mov     r8d, ebx
0x14000ee8f  mov     eax, [rsp+48h+arg_28]
0x14000ee93  mov     rdx, rdi
0x14000ee96  mov     [rsp+48h+var_20], eax
0x14000ee9a  mov     rcx, rsi
0x14000ee9d  mov     rax, r10
0x14000eea0  mov     [rsp+48h+var_28], 0
0x14000eea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eeae  mov     rbx, [rsp+48h+arg_0]
0x14000eeb3  mov     rsi, [rsp+48h+arg_8]
0x14000eeb8  add     rsp, 40h
0x14000eebc  pop     rdi
0x14000eebd  retn
```
