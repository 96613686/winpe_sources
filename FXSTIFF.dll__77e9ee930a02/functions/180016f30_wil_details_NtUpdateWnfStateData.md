# wil_details_NtUpdateWnfStateData

- ea: `0x180016f30`
- end: `0x180016fe7`
- name: `wil_details_NtUpdateWnfStateData`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180014820`
- `0x180016afc`

## callees

- `0x180016f30`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180016f67`
- `KERNEL32!GetModuleHandleW` at `0x180016f67`
- `KERNEL32!GetProcAddress` at `0x180016f84`
- `KERNEL32!GetProcAddress` at `0x180016f84`

## string_xrefs

- `0x180016f60`: `ntdll.dll`
- `0x180016f7a`: `NtUpdateWnfStateData`

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
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180016f30  mov     [rsp+arg_0], rbx
0x180016f35  mov     [rsp+arg_8], rsi
0x180016f3a  push    rdi
0x180016f3b  sub     rsp, 40h
0x180016f3f  mov     ebx, r8d
0x180016f42  mov     rdi, rdx
0x180016f45  mov     rsi, rcx
0x180016f48  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180016f4f  test    r10, r10
0x180016f52  jnz     short loc_180016FA6
0x180016f54  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180016f5b  test    rax, rax
0x180016f5e  jnz     short loc_180016F7A
0x180016f60  lea     rcx, ModuleName; "ntdll.dll"
0x180016f67  call    cs:__imp_GetModuleHandleW
0x180016f6e  nop     dword ptr [rax+rax+00h]
0x180016f73  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180016f7a  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180016f81  mov     rcx, rax; hModule
0x180016f84  call    cs:__imp_GetProcAddress
0x180016f8b  nop     dword ptr [rax+rax+00h]
0x180016f90  mov     r10, rax
0x180016f93  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180016f9a  test    rax, rax
0x180016f9d  jnz     short loc_180016FA6
0x180016f9f  mov     eax, 0C0000139h
0x180016fa4  jmp     short loc_180016FD6
0x180016fa6  mov     eax, [rsp+48h+arg_30]
0x180016fad  mov     [rsp+48h+var_18], eax
0x180016fb1  mov     eax, [rsp+48h+arg_28]
0x180016fb5  mov     [rsp+48h+var_20], eax
0x180016fb9  mov     [rsp+48h+var_28], 0
0x180016fc2  xor     r9d, r9d
0x180016fc5  mov     r8d, ebx
0x180016fc8  mov     rdx, rdi
0x180016fcb  mov     rcx, rsi
0x180016fce  mov     rax, r10
0x180016fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fd6  mov     rbx, [rsp+48h+arg_0]
0x180016fdb  mov     rsi, [rsp+48h+arg_8]
0x180016fe0  add     rsp, 40h
0x180016fe4  pop     rdi
0x180016fe5  retn
```
