# wil_details_NtUpdateWnfStateData

- ea: `0x180007f64`
- end: `0x18000800e`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180006434`
- `0x180007c94`

## callees

- `0x180007f64`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007f9b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007f9b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007fb2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007fb2`

## string_xrefs

- `0x180007f94`: `ntdll.dll`
- `0x180007fa8`: `NtUpdateWnfStateData`

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
0x180007f64  mov     [rsp+arg_0], rbx
0x180007f69  mov     [rsp+arg_8], rsi
0x180007f6e  push    rdi
0x180007f6f  sub     rsp, 40h
0x180007f73  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180007f7a  mov     ebx, r8d
0x180007f7d  mov     rdi, rdx
0x180007f80  mov     rsi, rcx
0x180007f83  test    r10, r10
0x180007f86  jnz     short loc_180007FCE
0x180007f88  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007f8f  test    rax, rax
0x180007f92  jnz     short loc_180007FA8
0x180007f94  lea     rcx, ModuleName; "ntdll.dll"
0x180007f9b  call    cs:__imp_GetModuleHandleW
0x180007fa1  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007fa8  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180007faf  mov     rcx, rax; hModule
0x180007fb2  call    cs:__imp_GetProcAddress
0x180007fb8  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180007fbf  mov     r10, rax
0x180007fc2  test    rax, rax
0x180007fc5  jnz     short loc_180007FCE
0x180007fc7  mov     eax, 0C0000139h
0x180007fcc  jmp     short loc_180007FFE
0x180007fce  mov     eax, [rsp+48h+arg_30]
0x180007fd5  xor     r9d, r9d
0x180007fd8  mov     [rsp+48h+var_18], eax
0x180007fdc  mov     r8d, ebx
0x180007fdf  mov     eax, [rsp+48h+arg_28]
0x180007fe3  mov     rdx, rdi
0x180007fe6  mov     [rsp+48h+var_20], eax
0x180007fea  mov     rcx, rsi
0x180007fed  mov     rax, r10
0x180007ff0  mov     [rsp+48h+var_28], 0
0x180007ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ffe  mov     rbx, [rsp+48h+arg_0]
0x180008003  mov     rsi, [rsp+48h+arg_8]
0x180008008  add     rsp, 40h
0x18000800c  pop     rdi
0x18000800d  retn
```
