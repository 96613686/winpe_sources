# wil_details_NtUpdateWnfStateData

- ea: `0x180016254`
- end: `0x1800162fe`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180013f90`
- `0x180015ea0`

## callees

- `0x180016254`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001628b`
- `KERNEL32!GetModuleHandleW` at `0x18001628b`
- `KERNEL32!GetProcAddress` at `0x1800162a2`
- `KERNEL32!GetProcAddress` at `0x1800162a2`

## string_xrefs

- `0x180016284`: `ntdll.dll`
- `0x180016298`: `NtUpdateWnfStateData`

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
0x180016254  mov     [rsp+arg_0], rbx
0x180016259  mov     [rsp+arg_8], rsi
0x18001625e  push    rdi
0x18001625f  sub     rsp, 40h
0x180016263  mov     ebx, r8d
0x180016266  mov     rdi, rdx
0x180016269  mov     rsi, rcx
0x18001626c  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180016273  test    r10, r10
0x180016276  jnz     short loc_1800162BE
0x180016278  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001627f  test    rax, rax
0x180016282  jnz     short loc_180016298
0x180016284  lea     rcx, ModuleName; "ntdll.dll"
0x18001628b  call    cs:__imp_GetModuleHandleW
0x180016291  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180016298  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001629f  mov     rcx, rax; hModule
0x1800162a2  call    cs:__imp_GetProcAddress
0x1800162a8  mov     r10, rax
0x1800162ab  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800162b2  test    rax, rax
0x1800162b5  jnz     short loc_1800162BE
0x1800162b7  mov     eax, 0C0000139h
0x1800162bc  jmp     short loc_1800162EE
0x1800162be  mov     eax, [rsp+48h+arg_30]
0x1800162c5  mov     [rsp+48h+var_18], eax
0x1800162c9  mov     eax, [rsp+48h+arg_28]
0x1800162cd  mov     [rsp+48h+var_20], eax
0x1800162d1  mov     [rsp+48h+var_28], 0
0x1800162da  xor     r9d, r9d
0x1800162dd  mov     r8d, ebx
0x1800162e0  mov     rdx, rdi
0x1800162e3  mov     rcx, rsi
0x1800162e6  mov     rax, r10
0x1800162e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162ee  mov     rbx, [rsp+48h+arg_0]
0x1800162f3  mov     rsi, [rsp+48h+arg_8]
0x1800162f8  add     rsp, 40h
0x1800162fc  pop     rdi
0x1800162fd  retn
```
