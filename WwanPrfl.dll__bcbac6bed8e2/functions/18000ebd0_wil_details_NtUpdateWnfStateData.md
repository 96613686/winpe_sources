# wil_details_NtUpdateWnfStateData

- ea: `0x18000ebd0`
- end: `0x18000ec7a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000701c`
- `0x18000d808`

## callees

- `0x18000ebd0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ec1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ec1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ec07`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ec07`

## string_xrefs

- `0x18000ec00`: `ntdll.dll`
- `0x18000ec14`: `NtUpdateWnfStateData`

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
0x18000ebd0  mov     [rsp+arg_0], rbx
0x18000ebd5  mov     [rsp+arg_8], rsi
0x18000ebda  push    rdi
0x18000ebdb  sub     rsp, 40h
0x18000ebdf  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000ebe6  mov     ebx, r8d
0x18000ebe9  mov     rdi, rdx
0x18000ebec  mov     rsi, rcx
0x18000ebef  test    r10, r10
0x18000ebf2  jnz     short loc_18000EC3A
0x18000ebf4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ebfb  test    rax, rax
0x18000ebfe  jnz     short loc_18000EC14
0x18000ec00  lea     rcx, ModuleName; "ntdll.dll"
0x18000ec07  call    cs:__imp_GetModuleHandleW
0x18000ec0d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ec14  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000ec1b  mov     rcx, rax; hModule
0x18000ec1e  call    cs:__imp_GetProcAddress
0x18000ec24  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000ec2b  mov     r10, rax
0x18000ec2e  test    rax, rax
0x18000ec31  jnz     short loc_18000EC3A
0x18000ec33  mov     eax, 0C0000139h
0x18000ec38  jmp     short loc_18000EC6A
0x18000ec3a  mov     eax, [rsp+48h+arg_30]
0x18000ec41  xor     r9d, r9d
0x18000ec44  mov     [rsp+48h+var_18], eax
0x18000ec48  mov     r8d, ebx
0x18000ec4b  mov     eax, [rsp+48h+arg_28]
0x18000ec4f  mov     rdx, rdi
0x18000ec52  mov     [rsp+48h+var_20], eax
0x18000ec56  mov     rcx, rsi
0x18000ec59  mov     rax, r10
0x18000ec5c  mov     [rsp+48h+var_28], 0
0x18000ec65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec6a  mov     rbx, [rsp+48h+arg_0]
0x18000ec6f  mov     rsi, [rsp+48h+arg_8]
0x18000ec74  add     rsp, 40h
0x18000ec78  pop     rdi
0x18000ec79  retn
```
