# wil_details_NtUpdateWnfStateData

- ea: `0x180018b10`
- end: `0x180018bba`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180015d68`
- `0x18001836c`

## callees

- `0x180018b10`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018b5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018b5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018b47`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018b47`

## string_xrefs

- `0x180018b54`: `NtUpdateWnfStateData`
- `0x180018b40`: `ntdll.dll`

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
0x180018b10  mov     [rsp+arg_0], rbx
0x180018b15  mov     [rsp+arg_8], rsi
0x180018b1a  push    rdi
0x180018b1b  sub     rsp, 40h
0x180018b1f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180018b26  mov     ebx, r8d
0x180018b29  mov     rdi, rdx
0x180018b2c  mov     rsi, rcx
0x180018b2f  test    r10, r10
0x180018b32  jnz     short loc_180018B7A
0x180018b34  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180018b3b  test    rax, rax
0x180018b3e  jnz     short loc_180018B54
0x180018b40  lea     rcx, ModuleName; "ntdll.dll"
0x180018b47  call    cs:__imp_GetModuleHandleW
0x180018b4d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180018b54  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180018b5b  mov     rcx, rax; hModule
0x180018b5e  call    cs:__imp_GetProcAddress
0x180018b64  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180018b6b  mov     r10, rax
0x180018b6e  test    rax, rax
0x180018b71  jnz     short loc_180018B7A
0x180018b73  mov     eax, 0C0000139h
0x180018b78  jmp     short loc_180018BAA
0x180018b7a  mov     eax, [rsp+48h+arg_30]
0x180018b81  xor     r9d, r9d
0x180018b84  mov     [rsp+48h+var_18], eax
0x180018b88  mov     r8d, ebx
0x180018b8b  mov     eax, [rsp+48h+arg_28]
0x180018b8f  mov     rdx, rdi
0x180018b92  mov     [rsp+48h+var_20], eax
0x180018b96  mov     rcx, rsi
0x180018b99  mov     rax, r10
0x180018b9c  mov     [rsp+48h+var_28], 0
0x180018ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018baa  mov     rbx, [rsp+48h+arg_0]
0x180018baf  mov     rsi, [rsp+48h+arg_8]
0x180018bb4  add     rsp, 40h
0x180018bb8  pop     rdi
0x180018bb9  retn
```
