# wil_details_NtUpdateWnfStateData

- ea: `0x18000e560`
- end: `0x18000e60a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180008ed8`
- `0x18000cde8`

## callees

- `0x18000e560`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000e597`
- `KERNEL32!GetModuleHandleW` at `0x18000e597`
- `KERNEL32!GetProcAddress` at `0x18000e5ae`
- `KERNEL32!GetProcAddress` at `0x18000e5ae`

## string_xrefs

- `0x18000e590`: `ntdll.dll`
- `0x18000e5a4`: `NtUpdateWnfStateData`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil_details_NtUpdateWnfStateData(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        int a6,
        int a7)
{
  FARPROC ProcAddress; // r10
  HMODULE ModuleHandleW; // rax

  ProcAddress = (FARPROC)g_wil_details_pfnNtUpdateWnfStateData;
  if ( g_wil_details_pfnNtUpdateWnfStateData )
    return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int))ProcAddress)(
             a1,
             a2,
             a3,
             0,
             0,
             a6,
             a7);
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "NtUpdateWnfStateData");
  g_wil_details_pfnNtUpdateWnfStateData = (__int64)ProcAddress;
  if ( ProcAddress )
    return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int))ProcAddress)(
             a1,
             a2,
             a3,
             0,
             0,
             a6,
             a7);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x18000e560  mov     [rsp+arg_0], rbx
0x18000e565  mov     [rsp+arg_8], rsi
0x18000e56a  push    rdi
0x18000e56b  sub     rsp, 40h
0x18000e56f  mov     ebx, r8d
0x18000e572  mov     rdi, rdx
0x18000e575  mov     rsi, rcx
0x18000e578  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000e57f  test    r10, r10
0x18000e582  jnz     short loc_18000E5CA
0x18000e584  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e58b  test    rax, rax
0x18000e58e  jnz     short loc_18000E5A4
0x18000e590  lea     rcx, ModuleName; "ntdll.dll"
0x18000e597  call    cs:__imp_GetModuleHandleW
0x18000e59d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e5a4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000e5ab  mov     rcx, rax; hModule
0x18000e5ae  call    cs:__imp_GetProcAddress
0x18000e5b4  mov     r10, rax
0x18000e5b7  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000e5be  test    rax, rax
0x18000e5c1  jnz     short loc_18000E5CA
0x18000e5c3  mov     eax, 0C0000139h
0x18000e5c8  jmp     short loc_18000E5FA
0x18000e5ca  mov     eax, [rsp+48h+arg_30]
0x18000e5d1  mov     [rsp+48h+var_18], eax
0x18000e5d5  mov     eax, [rsp+48h+arg_28]
0x18000e5d9  mov     [rsp+48h+var_20], eax
0x18000e5dd  mov     [rsp+48h+var_28], 0
0x18000e5e6  xor     r9d, r9d
0x18000e5e9  mov     r8d, ebx
0x18000e5ec  mov     rdx, rdi
0x18000e5ef  mov     rcx, rsi
0x18000e5f2  mov     rax, r10
0x18000e5f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5fa  mov     rbx, [rsp+48h+arg_0]
0x18000e5ff  mov     rsi, [rsp+48h+arg_8]
0x18000e604  add     rsp, 40h
0x18000e608  pop     rdi
0x18000e609  retn
```
