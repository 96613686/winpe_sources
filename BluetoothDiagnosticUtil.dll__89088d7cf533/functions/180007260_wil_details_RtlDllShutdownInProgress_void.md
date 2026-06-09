# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180007260`
- end: `0x1800072c4`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `100`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007260`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800072a0`
- `KERNEL32!GetProcAddress` at `0x1800072a0`
- `KERNEL32!GetModuleHandleW` at `0x180007283`
- `KERNEL32!GetModuleHandleW` at `0x180007283`

## string_xrefs

- `0x18000727c`: `ntdll.dll`
- `0x180007296`: `RtlDllShutdownInProgress`

## pseudocode

```c
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
0x180007260  sub     rsp, 28h
0x180007264  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000726b  test    rax, rax
0x18000726e  jnz     short loc_1800072B8
0x180007270  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007277  test    rax, rax
0x18000727a  jnz     short loc_180007296
0x18000727c  lea     rcx, ModuleName; "ntdll.dll"
0x180007283  call    cs:__imp_GetModuleHandleW
0x18000728a  nop     dword ptr [rax+rax+00h]
0x18000728f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007296  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000729d  mov     rcx, rax; hModule
0x1800072a0  call    cs:__imp_GetProcAddress
0x1800072a7  nop     dword ptr [rax+rax+00h]
0x1800072ac  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800072b3  test    rax, rax
0x1800072b6  jz      short loc_1800072BE
0x1800072b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072bd  nop
0x1800072be  add     rsp, 28h
0x1800072c2  retn
```
