# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180008700`
- end: `0x180008760`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `96`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180008700`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000872c`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000872c`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180008743`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180008743`

## string_xrefs

- `0x180008725`: `ntdll.dll`
- `0x180008739`: `RtlDllShutdownInProgress`

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
0x180008700  sub     rsp, 38h
0x180008704  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000870d  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180008714  test    rax, rax
0x180008717  jnz     short loc_180008755
0x180008719  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008720  test    rax, rax
0x180008723  jnz     short loc_180008739
0x180008725  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000872c  call    cs:__imp_GetModuleHandleW
0x180008732  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008739  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180008740  mov     rcx, rax; hModule
0x180008743  call    cs:__imp_GetProcAddress
0x180008749  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180008750  test    rax, rax
0x180008753  jz      short loc_18000875B
0x180008755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000875a  nop
0x18000875b  add     rsp, 38h
0x18000875f  retn
```
