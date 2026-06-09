# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180005e90`
- end: `0x180005eea`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180005e90`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005eca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005eca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005eb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005eb3`

## string_xrefs

- `0x180005eac`: `ntdll.dll`
- `0x180005ec0`: `RtlDllShutdownInProgress`

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
0x180005e90  sub     rsp, 28h
0x180005e94  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180005e9b  test    rax, rax
0x180005e9e  jnz     short loc_180005EE1
0x180005ea0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005ea7  test    rax, rax
0x180005eaa  jnz     short loc_180005EC0
0x180005eac  lea     rcx, ModuleName; "ntdll.dll"
0x180005eb3  call    cs:__imp_GetModuleHandleW
0x180005eb9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005ec0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180005ec7  mov     rcx, rax; hModule
0x180005eca  call    cs:__imp_GetProcAddress
0x180005ed0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180005ed7  test    rax, rax
0x180005eda  jnz     short loc_180005EE1
0x180005edc  add     rsp, 28h
0x180005ee0  retn
0x180005ee1  add     rsp, 28h
0x180005ee5  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
