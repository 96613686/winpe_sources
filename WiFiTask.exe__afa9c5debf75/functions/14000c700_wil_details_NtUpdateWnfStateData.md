# wil_details_NtUpdateWnfStateData

- ea: `0x14000c700`
- end: `0x14000c7aa`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140008e4c`
- `0x14000bb38`

## callees

- `0x14000c700`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000c737`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000c737`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c74e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c74e`

## string_xrefs

- `0x14000c730`: `ntdll.dll`
- `0x14000c744`: `NtUpdateWnfStateData`

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
0x14000c700  mov     [rsp+arg_0], rbx
0x14000c705  mov     [rsp+arg_8], rsi
0x14000c70a  push    rdi
0x14000c70b  sub     rsp, 40h
0x14000c70f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14000c716  mov     ebx, r8d
0x14000c719  mov     rdi, rdx
0x14000c71c  mov     rsi, rcx
0x14000c71f  test    r10, r10
0x14000c722  jnz     short loc_14000C76A
0x14000c724  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c72b  test    rax, rax
0x14000c72e  jnz     short loc_14000C744
0x14000c730  lea     rcx, ModuleName; "ntdll.dll"
0x14000c737  call    cs:__imp_GetModuleHandleW
0x14000c73d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c744  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000c74b  mov     rcx, rax; hModule
0x14000c74e  call    cs:__imp_GetProcAddress
0x14000c754  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000c75b  mov     r10, rax
0x14000c75e  test    rax, rax
0x14000c761  jnz     short loc_14000C76A
0x14000c763  mov     eax, 0C0000139h
0x14000c768  jmp     short loc_14000C79A
0x14000c76a  mov     eax, [rsp+48h+arg_30]
0x14000c771  xor     r9d, r9d
0x14000c774  mov     [rsp+48h+var_18], eax
0x14000c778  mov     r8d, ebx
0x14000c77b  mov     eax, [rsp+48h+arg_28]
0x14000c77f  mov     rdx, rdi
0x14000c782  mov     [rsp+48h+var_20], eax
0x14000c786  mov     rcx, rsi
0x14000c789  mov     rax, r10
0x14000c78c  mov     [rsp+48h+var_28], 0
0x14000c795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c79a  mov     rbx, [rsp+48h+arg_0]
0x14000c79f  mov     rsi, [rsp+48h+arg_8]
0x14000c7a4  add     rsp, 40h
0x14000c7a8  pop     rdi
0x14000c7a9  retn
```
