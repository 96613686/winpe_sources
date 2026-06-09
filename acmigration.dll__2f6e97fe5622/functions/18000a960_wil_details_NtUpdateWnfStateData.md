# wil_details_NtUpdateWnfStateData

- ea: `0x18000a960`
- end: `0x18000aa0a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180007d7c`
- `0x18000a258`

## callees

- `0x18000a960`
- `0x18006a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000a997`
- `KERNEL32!GetModuleHandleW` at `0x18000a997`
- `KERNEL32!GetProcAddress` at `0x18000a9ae`
- `KERNEL32!GetProcAddress` at `0x18000a9ae`

## string_xrefs

- `0x18000a990`: `ntdll.dll`
- `0x18000a9a4`: `NtUpdateWnfStateData`

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
0x18000a960  mov     [rsp+arg_0], rbx
0x18000a965  mov     [rsp+arg_8], rsi
0x18000a96a  push    rdi
0x18000a96b  sub     rsp, 40h
0x18000a96f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000a976  mov     ebx, r8d
0x18000a979  mov     rdi, rdx
0x18000a97c  mov     rsi, rcx
0x18000a97f  test    r10, r10
0x18000a982  jnz     short loc_18000A9CA
0x18000a984  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a98b  test    rax, rax
0x18000a98e  jnz     short loc_18000A9A4
0x18000a990  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000a997  call    cs:__imp_GetModuleHandleW
0x18000a99d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a9a4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000a9ab  mov     rcx, rax; hModule
0x18000a9ae  call    cs:__imp_GetProcAddress
0x18000a9b4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000a9bb  mov     r10, rax
0x18000a9be  test    rax, rax
0x18000a9c1  jnz     short loc_18000A9CA
0x18000a9c3  mov     eax, 0C0000139h
0x18000a9c8  jmp     short loc_18000A9FA
0x18000a9ca  mov     eax, [rsp+48h+arg_30]
0x18000a9d1  xor     r9d, r9d
0x18000a9d4  mov     [rsp+48h+var_18], eax
0x18000a9d8  mov     r8d, ebx
0x18000a9db  mov     eax, [rsp+48h+arg_28]
0x18000a9df  mov     rdx, rdi
0x18000a9e2  mov     [rsp+48h+var_20], eax
0x18000a9e6  mov     rcx, rsi
0x18000a9e9  mov     rax, r10
0x18000a9ec  mov     [rsp+48h+var_28], 0
0x18000a9f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9fa  mov     rbx, [rsp+48h+arg_0]
0x18000a9ff  mov     rsi, [rsp+48h+arg_8]
0x18000aa04  add     rsp, 40h
0x18000aa08  pop     rdi
0x18000aa09  retn
```
