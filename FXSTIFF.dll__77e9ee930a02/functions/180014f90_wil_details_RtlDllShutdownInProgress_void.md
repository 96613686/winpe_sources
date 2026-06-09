# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180014f90`
- end: `0x180014ff5`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `101`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180014f90`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180014fb3`
- `KERNEL32!GetModuleHandleW` at `0x180014fb3`
- `KERNEL32!GetProcAddress` at `0x180014fd0`
- `KERNEL32!GetProcAddress` at `0x180014fd0`

## string_xrefs

- `0x180014fac`: `ntdll.dll`
- `0x180014fc6`: `RtlDllShutdownInProgress`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
FARPROC __fastcall wil::details::RtlDllShutdownInProgress(wil::details *this)
{
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "RtlDllShutdownInProgress");
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  return result;
}

```

## disassembly

```asm
0x180014f90  sub     rsp, 28h
0x180014f94  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180014f9b  test    rax, rax
0x180014f9e  jnz     short loc_180014FE9
0x180014fa0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014fa7  test    rax, rax
0x180014faa  jnz     short loc_180014FC6
0x180014fac  lea     rcx, ModuleName; "ntdll.dll"
0x180014fb3  call    cs:__imp_GetModuleHandleW
0x180014fba  nop     dword ptr [rax+rax+00h]
0x180014fbf  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014fc6  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180014fcd  mov     rcx, rax; hModule
0x180014fd0  call    cs:__imp_GetProcAddress
0x180014fd7  nop     dword ptr [rax+rax+00h]
0x180014fdc  nop
0x180014fdd  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180014fe4  test    rax, rax
0x180014fe7  jz      short loc_180014FEF
0x180014fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fee  nop
0x180014fef  add     rsp, 28h
0x180014ff3  retn
```
