# wil_details_NtUpdateWnfStateData

- ea: `0x18000e480`
- end: `0x18000e52a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000b91c`
- `0x18000e240`

## callees

- `0x18000e480`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e4ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e4ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e4b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e4b7`

## string_xrefs

- `0x18000e4b0`: `ntdll.dll`
- `0x18000e4c4`: `NtUpdateWnfStateData`

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
0x18000e480  mov     [rsp+arg_0], rbx
0x18000e485  mov     [rsp+arg_8], rsi
0x18000e48a  push    rdi
0x18000e48b  sub     rsp, 40h
0x18000e48f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000e496  mov     ebx, r8d
0x18000e499  mov     rdi, rdx
0x18000e49c  mov     rsi, rcx
0x18000e49f  test    r10, r10
0x18000e4a2  jnz     short loc_18000E4EA
0x18000e4a4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e4ab  test    rax, rax
0x18000e4ae  jnz     short loc_18000E4C4
0x18000e4b0  lea     rcx, ModuleName; "ntdll.dll"
0x18000e4b7  call    cs:__imp_GetModuleHandleW
0x18000e4bd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e4c4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000e4cb  mov     rcx, rax; hModule
0x18000e4ce  call    cs:__imp_GetProcAddress
0x18000e4d4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000e4db  mov     r10, rax
0x18000e4de  test    rax, rax
0x18000e4e1  jnz     short loc_18000E4EA
0x18000e4e3  mov     eax, 0C0000139h
0x18000e4e8  jmp     short loc_18000E51A
0x18000e4ea  mov     eax, [rsp+48h+arg_30]
0x18000e4f1  xor     r9d, r9d
0x18000e4f4  mov     [rsp+48h+var_18], eax
0x18000e4f8  mov     r8d, ebx
0x18000e4fb  mov     eax, [rsp+48h+arg_28]
0x18000e4ff  mov     rdx, rdi
0x18000e502  mov     [rsp+48h+var_20], eax
0x18000e506  mov     rcx, rsi
0x18000e509  mov     rax, r10
0x18000e50c  mov     [rsp+48h+var_28], 0
0x18000e515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e51a  mov     rbx, [rsp+48h+arg_0]
0x18000e51f  mov     rsi, [rsp+48h+arg_8]
0x18000e524  add     rsp, 40h
0x18000e528  pop     rdi
0x18000e529  retn
```
