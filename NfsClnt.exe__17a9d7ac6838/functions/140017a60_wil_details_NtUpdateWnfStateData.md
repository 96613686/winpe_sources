# wil_details_NtUpdateWnfStateData

- ea: `0x140017a60`
- end: `0x140017b0a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140016078`
- `0x140017820`

## callees

- `0x140017a60`
- `0x140019010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140017aae`
- `KERNEL32!GetProcAddress` at `0x140017aae`
- `KERNEL32!GetModuleHandleW` at `0x140017a97`
- `KERNEL32!GetModuleHandleW` at `0x140017a97`

## string_xrefs

- `0x140017a90`: `ntdll.dll`
- `0x140017aa4`: `NtUpdateWnfStateData`

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
0x140017a60  mov     [rsp+arg_0], rbx
0x140017a65  mov     [rsp+arg_8], rsi
0x140017a6a  push    rdi
0x140017a6b  sub     rsp, 40h
0x140017a6f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x140017a76  mov     ebx, r8d
0x140017a79  mov     rdi, rdx
0x140017a7c  mov     rsi, rcx
0x140017a7f  test    r10, r10
0x140017a82  jnz     short loc_140017ACA
0x140017a84  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140017a8b  test    rax, rax
0x140017a8e  jnz     short loc_140017AA4
0x140017a90  lea     rcx, ModuleName; "ntdll.dll"
0x140017a97  call    cs:__imp_GetModuleHandleW
0x140017a9d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140017aa4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x140017aab  mov     rcx, rax; hModule
0x140017aae  call    cs:__imp_GetProcAddress
0x140017ab4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x140017abb  mov     r10, rax
0x140017abe  test    rax, rax
0x140017ac1  jnz     short loc_140017ACA
0x140017ac3  mov     eax, 0C0000139h
0x140017ac8  jmp     short loc_140017AFA
0x140017aca  mov     eax, [rsp+48h+arg_30]
0x140017ad1  xor     r9d, r9d
0x140017ad4  mov     [rsp+48h+var_18], eax
0x140017ad8  mov     r8d, ebx
0x140017adb  mov     eax, [rsp+48h+arg_28]
0x140017adf  mov     rdx, rdi
0x140017ae2  mov     [rsp+48h+var_20], eax
0x140017ae6  mov     rcx, rsi
0x140017ae9  mov     rax, r10
0x140017aec  mov     [rsp+48h+var_28], 0
0x140017af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017afa  mov     rbx, [rsp+48h+arg_0]
0x140017aff  mov     rsi, [rsp+48h+arg_8]
0x140017b04  add     rsp, 40h
0x140017b08  pop     rdi
0x140017b09  retn
```
