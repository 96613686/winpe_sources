# wil_details_NtUpdateWnfStateData

- ea: `0x18000d348`
- end: `0x18000d3f2`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180009ad8`
- `0x18000c8e8`

## callees

- `0x18000d348`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d37f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d37f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d396`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d396`

## string_xrefs

- `0x18000d378`: `ntdll.dll`
- `0x18000d38c`: `NtUpdateWnfStateData`

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
0x18000d348  mov     [rsp+arg_0], rbx
0x18000d34d  mov     [rsp+arg_8], rsi
0x18000d352  push    rdi
0x18000d353  sub     rsp, 40h
0x18000d357  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000d35e  mov     ebx, r8d
0x18000d361  mov     rdi, rdx
0x18000d364  mov     rsi, rcx
0x18000d367  test    r10, r10
0x18000d36a  jnz     short loc_18000D3B2
0x18000d36c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d373  test    rax, rax
0x18000d376  jnz     short loc_18000D38C
0x18000d378  lea     rcx, ModuleName; "ntdll.dll"
0x18000d37f  call    cs:__imp_GetModuleHandleW
0x18000d385  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d38c  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000d393  mov     rcx, rax; hModule
0x18000d396  call    cs:__imp_GetProcAddress
0x18000d39c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000d3a3  mov     r10, rax
0x18000d3a6  test    rax, rax
0x18000d3a9  jnz     short loc_18000D3B2
0x18000d3ab  mov     eax, 0C0000139h
0x18000d3b0  jmp     short loc_18000D3E2
0x18000d3b2  mov     eax, [rsp+48h+arg_30]
0x18000d3b9  xor     r9d, r9d
0x18000d3bc  mov     [rsp+48h+var_18], eax
0x18000d3c0  mov     r8d, ebx
0x18000d3c3  mov     eax, [rsp+48h+arg_28]
0x18000d3c7  mov     rdx, rdi
0x18000d3ca  mov     [rsp+48h+var_20], eax
0x18000d3ce  mov     rcx, rsi
0x18000d3d1  mov     rax, r10
0x18000d3d4  mov     [rsp+48h+var_28], 0
0x18000d3dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3e2  mov     rbx, [rsp+48h+arg_0]
0x18000d3e7  mov     rsi, [rsp+48h+arg_8]
0x18000d3ec  add     rsp, 40h
0x18000d3f0  pop     rdi
0x18000d3f1  retn
```
