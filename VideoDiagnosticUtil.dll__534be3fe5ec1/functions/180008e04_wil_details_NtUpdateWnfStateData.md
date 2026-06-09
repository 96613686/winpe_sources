# wil_details_NtUpdateWnfStateData

- ea: `0x180008e04`
- end: `0x180008ebb`
- name: `wil_details_NtUpdateWnfStateData`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180006154`
- `0x180008b80`

## callees

- `0x180008e04`
- `0x18000a010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180008e58`
- `KERNEL32!GetProcAddress` at `0x180008e58`
- `KERNEL32!GetModuleHandleW` at `0x180008e3b`
- `KERNEL32!GetModuleHandleW` at `0x180008e3b`

## string_xrefs

- `0x180008e34`: `ntdll.dll`
- `0x180008e4e`: `NtUpdateWnfStateData`

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
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180008e04  mov     [rsp+arg_0], rbx
0x180008e09  mov     [rsp+arg_8], rsi
0x180008e0e  push    rdi
0x180008e0f  sub     rsp, 40h
0x180008e13  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180008e1a  mov     ebx, r8d
0x180008e1d  mov     rdi, rdx
0x180008e20  mov     rsi, rcx
0x180008e23  test    r10, r10
0x180008e26  jnz     short loc_180008E7A
0x180008e28  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008e2f  test    rax, rax
0x180008e32  jnz     short loc_180008E4E
0x180008e34  lea     rcx, ModuleName; "ntdll.dll"
0x180008e3b  call    cs:__imp_GetModuleHandleW
0x180008e42  nop     dword ptr [rax+rax+00h]
0x180008e47  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008e4e  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180008e55  mov     rcx, rax; hModule
0x180008e58  call    cs:__imp_GetProcAddress
0x180008e5f  nop     dword ptr [rax+rax+00h]
0x180008e64  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180008e6b  mov     r10, rax
0x180008e6e  test    rax, rax
0x180008e71  jnz     short loc_180008E7A
0x180008e73  mov     eax, 0C0000139h
0x180008e78  jmp     short loc_180008EAA
0x180008e7a  mov     eax, [rsp+48h+arg_30]
0x180008e81  xor     r9d, r9d
0x180008e84  mov     [rsp+48h+var_18], eax
0x180008e88  mov     r8d, ebx
0x180008e8b  mov     eax, [rsp+48h+arg_28]
0x180008e8f  mov     rdx, rdi
0x180008e92  mov     [rsp+48h+var_20], eax
0x180008e96  mov     rcx, rsi
0x180008e99  mov     rax, r10
0x180008e9c  mov     [rsp+48h+var_28], 0
0x180008ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eaa  mov     rbx, [rsp+48h+arg_0]
0x180008eaf  mov     rsi, [rsp+48h+arg_8]
0x180008eb4  add     rsp, 40h
0x180008eb8  pop     rdi
0x180008eb9  retn
```
