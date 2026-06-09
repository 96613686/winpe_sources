# wil_details_NtUpdateWnfStateData

- ea: `0x18000b110`
- end: `0x18000b1ba`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180008e0c`
- `0x18000ae40`

## callees

- `0x18000b110`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b15e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b15e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b147`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b147`

## string_xrefs

- `0x18000b140`: `ntdll.dll`
- `0x18000b154`: `NtUpdateWnfStateData`

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
0x18000b110  mov     [rsp+arg_0], rbx
0x18000b115  mov     [rsp+arg_8], rsi
0x18000b11a  push    rdi
0x18000b11b  sub     rsp, 40h
0x18000b11f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000b126  mov     ebx, r8d
0x18000b129  mov     rdi, rdx
0x18000b12c  mov     rsi, rcx
0x18000b12f  test    r10, r10
0x18000b132  jnz     short loc_18000B17A
0x18000b134  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b13b  test    rax, rax
0x18000b13e  jnz     short loc_18000B154
0x18000b140  lea     rcx, ModuleName; "ntdll.dll"
0x18000b147  call    cs:__imp_GetModuleHandleW
0x18000b14d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b154  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000b15b  mov     rcx, rax; hModule
0x18000b15e  call    cs:__imp_GetProcAddress
0x18000b164  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000b16b  mov     r10, rax
0x18000b16e  test    rax, rax
0x18000b171  jnz     short loc_18000B17A
0x18000b173  mov     eax, 0C0000139h
0x18000b178  jmp     short loc_18000B1AA
0x18000b17a  mov     eax, [rsp+48h+arg_30]
0x18000b181  xor     r9d, r9d
0x18000b184  mov     [rsp+48h+var_18], eax
0x18000b188  mov     r8d, ebx
0x18000b18b  mov     eax, [rsp+48h+arg_28]
0x18000b18f  mov     rdx, rdi
0x18000b192  mov     [rsp+48h+var_20], eax
0x18000b196  mov     rcx, rsi
0x18000b199  mov     rax, r10
0x18000b19c  mov     [rsp+48h+var_28], 0
0x18000b1a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1aa  mov     rbx, [rsp+48h+arg_0]
0x18000b1af  mov     rsi, [rsp+48h+arg_8]
0x18000b1b4  add     rsp, 40h
0x18000b1b8  pop     rdi
0x18000b1b9  retn
```
