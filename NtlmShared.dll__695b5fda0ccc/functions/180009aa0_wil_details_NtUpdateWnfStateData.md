# wil_details_NtUpdateWnfStateData

- ea: `0x180009aa0`
- end: `0x180009b4a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000632c`
- `0x180007db8`

## callees

- `0x180009aa0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009aee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009aee`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009ad7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009ad7`

## string_xrefs

- `0x180009ad0`: `ntdll.dll`
- `0x180009ae4`: `NtUpdateWnfStateData`

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
0x180009aa0  mov     [rsp+arg_0], rbx
0x180009aa5  mov     [rsp+arg_8], rsi
0x180009aaa  push    rdi
0x180009aab  sub     rsp, 40h
0x180009aaf  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180009ab6  mov     ebx, r8d
0x180009ab9  mov     rdi, rdx
0x180009abc  mov     rsi, rcx
0x180009abf  test    r10, r10
0x180009ac2  jnz     short loc_180009B0A
0x180009ac4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009acb  test    rax, rax
0x180009ace  jnz     short loc_180009AE4
0x180009ad0  lea     rcx, ModuleName; "ntdll.dll"
0x180009ad7  call    cs:__imp_GetModuleHandleW
0x180009add  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009ae4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180009aeb  mov     rcx, rax; hModule
0x180009aee  call    cs:__imp_GetProcAddress
0x180009af4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180009afb  mov     r10, rax
0x180009afe  test    rax, rax
0x180009b01  jnz     short loc_180009B0A
0x180009b03  mov     eax, 0C0000139h
0x180009b08  jmp     short loc_180009B3A
0x180009b0a  mov     eax, [rsp+48h+arg_30]
0x180009b11  xor     r9d, r9d
0x180009b14  mov     [rsp+48h+var_18], eax
0x180009b18  mov     r8d, ebx
0x180009b1b  mov     eax, [rsp+48h+arg_28]
0x180009b1f  mov     rdx, rdi
0x180009b22  mov     [rsp+48h+var_20], eax
0x180009b26  mov     rcx, rsi
0x180009b29  mov     rax, r10
0x180009b2c  mov     [rsp+48h+var_28], 0
0x180009b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b3a  mov     rbx, [rsp+48h+arg_0]
0x180009b3f  mov     rsi, [rsp+48h+arg_8]
0x180009b44  add     rsp, 40h
0x180009b48  pop     rdi
0x180009b49  retn
```
