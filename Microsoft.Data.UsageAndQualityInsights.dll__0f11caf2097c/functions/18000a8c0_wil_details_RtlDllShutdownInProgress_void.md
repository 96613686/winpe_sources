# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000a8c0`
- end: `0x18000a917`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000a8c0`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a8e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a8e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a8fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a8fa`

## string_xrefs

- `0x18000a8dc`: `ntdll.dll`
- `0x18000a8f0`: `RtlDllShutdownInProgress`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlDllShutdownInProgress(wil::details *this)
{
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x18000a8c0  sub     rsp, 28h
0x18000a8c4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000a8cb  test    rax, rax
0x18000a8ce  jnz     short loc_18000A90C
0x18000a8d0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a8d7  test    rax, rax
0x18000a8da  jnz     short loc_18000A8F0
0x18000a8dc  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000a8e3  call    cs:__imp_GetModuleHandleW
0x18000a8e9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a8f0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000a8f7  mov     rcx, rax; hModule
0x18000a8fa  call    cs:__imp_GetProcAddress
0x18000a900  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000a907  test    rax, rax
0x18000a90a  jz      short loc_18000A912
0x18000a90c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a911  nop
0x18000a912  add     rsp, 28h
0x18000a916  retn
```
