# wil_details_NtUpdateWnfStateData

- ea: `0x180008a28`
- end: `0x180008ad2`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000659c`
- `0x180008758`

## callees

- `0x180008a28`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008a76`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008a76`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008a5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008a5f`

## string_xrefs

- `0x180008a58`: `ntdll.dll`
- `0x180008a6c`: `NtUpdateWnfStateData`

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
0x180008a28  mov     [rsp+arg_0], rbx
0x180008a2d  mov     [rsp+arg_8], rsi
0x180008a32  push    rdi
0x180008a33  sub     rsp, 40h
0x180008a37  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180008a3e  mov     ebx, r8d
0x180008a41  mov     rdi, rdx
0x180008a44  mov     rsi, rcx
0x180008a47  test    r10, r10
0x180008a4a  jnz     short loc_180008A92
0x180008a4c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008a53  test    rax, rax
0x180008a56  jnz     short loc_180008A6C
0x180008a58  lea     rcx, ModuleName; "ntdll.dll"
0x180008a5f  call    cs:__imp_GetModuleHandleW
0x180008a65  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008a6c  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180008a73  mov     rcx, rax; hModule
0x180008a76  call    cs:__imp_GetProcAddress
0x180008a7c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180008a83  mov     r10, rax
0x180008a86  test    rax, rax
0x180008a89  jnz     short loc_180008A92
0x180008a8b  mov     eax, 0C0000139h
0x180008a90  jmp     short loc_180008AC2
0x180008a92  mov     eax, [rsp+48h+arg_30]
0x180008a99  xor     r9d, r9d
0x180008a9c  mov     [rsp+48h+var_18], eax
0x180008aa0  mov     r8d, ebx
0x180008aa3  mov     eax, [rsp+48h+arg_28]
0x180008aa7  mov     rdx, rdi
0x180008aaa  mov     [rsp+48h+var_20], eax
0x180008aae  mov     rcx, rsi
0x180008ab1  mov     rax, r10
0x180008ab4  mov     [rsp+48h+var_28], 0
0x180008abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ac2  mov     rbx, [rsp+48h+arg_0]
0x180008ac7  mov     rsi, [rsp+48h+arg_8]
0x180008acc  add     rsp, 40h
0x180008ad0  pop     rdi
0x180008ad1  retn
```
