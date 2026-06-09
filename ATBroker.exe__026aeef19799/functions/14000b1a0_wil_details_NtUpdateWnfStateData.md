# wil_details_NtUpdateWnfStateData

- ea: `0x14000b1a0`
- end: `0x14000b24a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1400086cc`
- `0x14000a958`

## callees

- `0x14000b1a0`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000b1ee`
- `KERNEL32!GetProcAddress` at `0x14000b1ee`
- `KERNEL32!GetModuleHandleW` at `0x14000b1d7`
- `KERNEL32!GetModuleHandleW` at `0x14000b1d7`

## string_xrefs

- `0x14000b1d0`: `ntdll.dll`
- `0x14000b1e4`: `NtUpdateWnfStateData`

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
0x14000b1a0  mov     [rsp+arg_0], rbx
0x14000b1a5  mov     [rsp+arg_8], rsi
0x14000b1aa  push    rdi
0x14000b1ab  sub     rsp, 40h
0x14000b1af  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14000b1b6  mov     ebx, r8d
0x14000b1b9  mov     rdi, rdx
0x14000b1bc  mov     rsi, rcx
0x14000b1bf  test    r10, r10
0x14000b1c2  jnz     short loc_14000B20A
0x14000b1c4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b1cb  test    rax, rax
0x14000b1ce  jnz     short loc_14000B1E4
0x14000b1d0  lea     rcx, ModuleName; "ntdll.dll"
0x14000b1d7  call    cs:__imp_GetModuleHandleW
0x14000b1dd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b1e4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000b1eb  mov     rcx, rax; hModule
0x14000b1ee  call    cs:__imp_GetProcAddress
0x14000b1f4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000b1fb  mov     r10, rax
0x14000b1fe  test    rax, rax
0x14000b201  jnz     short loc_14000B20A
0x14000b203  mov     eax, 0C0000139h
0x14000b208  jmp     short loc_14000B23A
0x14000b20a  mov     eax, [rsp+48h+arg_30]
0x14000b211  xor     r9d, r9d
0x14000b214  mov     [rsp+48h+var_18], eax
0x14000b218  mov     r8d, ebx
0x14000b21b  mov     eax, [rsp+48h+arg_28]
0x14000b21f  mov     rdx, rdi
0x14000b222  mov     [rsp+48h+var_20], eax
0x14000b226  mov     rcx, rsi
0x14000b229  mov     rax, r10
0x14000b22c  mov     [rsp+48h+var_28], 0
0x14000b235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b23a  mov     rbx, [rsp+48h+arg_0]
0x14000b23f  mov     rsi, [rsp+48h+arg_8]
0x14000b244  add     rsp, 40h
0x14000b248  pop     rdi
0x14000b249  retn
```
