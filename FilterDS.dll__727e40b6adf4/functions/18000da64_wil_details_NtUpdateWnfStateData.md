# wil_details_NtUpdateWnfStateData

- ea: `0x18000da64`
- end: `0x18000db0e`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000b2dc`
- `0x18000d824`

## callees

- `0x18000da64`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dab2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dab2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000da9b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000da9b`

## string_xrefs

- `0x18000da94`: `ntdll.dll`
- `0x18000daa8`: `NtUpdateWnfStateData`

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
0x18000da64  mov     [rsp+arg_0], rbx
0x18000da69  mov     [rsp+arg_8], rsi
0x18000da6e  push    rdi
0x18000da6f  sub     rsp, 40h
0x18000da73  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000da7a  mov     ebx, r8d
0x18000da7d  mov     rdi, rdx
0x18000da80  mov     rsi, rcx
0x18000da83  test    r10, r10
0x18000da86  jnz     short loc_18000DACE
0x18000da88  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000da8f  test    rax, rax
0x18000da92  jnz     short loc_18000DAA8
0x18000da94  lea     rcx, ModuleName; "ntdll.dll"
0x18000da9b  call    cs:__imp_GetModuleHandleW
0x18000daa1  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000daa8  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000daaf  mov     rcx, rax; hModule
0x18000dab2  call    cs:__imp_GetProcAddress
0x18000dab8  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000dabf  mov     r10, rax
0x18000dac2  test    rax, rax
0x18000dac5  jnz     short loc_18000DACE
0x18000dac7  mov     eax, 0C0000139h
0x18000dacc  jmp     short loc_18000DAFE
0x18000dace  mov     eax, [rsp+48h+arg_30]
0x18000dad5  xor     r9d, r9d
0x18000dad8  mov     [rsp+48h+var_18], eax
0x18000dadc  mov     r8d, ebx
0x18000dadf  mov     eax, [rsp+48h+arg_28]
0x18000dae3  mov     rdx, rdi
0x18000dae6  mov     [rsp+48h+var_20], eax
0x18000daea  mov     rcx, rsi
0x18000daed  mov     rax, r10
0x18000daf0  mov     [rsp+48h+var_28], 0
0x18000daf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dafe  mov     rbx, [rsp+48h+arg_0]
0x18000db03  mov     rsi, [rsp+48h+arg_8]
0x18000db08  add     rsp, 40h
0x18000db0c  pop     rdi
0x18000db0d  retn
```
