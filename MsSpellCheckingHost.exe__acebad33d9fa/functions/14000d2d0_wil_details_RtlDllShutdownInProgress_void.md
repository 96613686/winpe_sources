# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x14000d2d0`
- end: `0x14000d327`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14000d2d0`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000d2f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000d2f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000d30a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000d30a`

## string_xrefs

- `0x14000d2ec`: `ntdll.dll`
- `0x14000d300`: `RtlDllShutdownInProgress`

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
0x14000d2d0  sub     rsp, 28h
0x14000d2d4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000d2db  test    rax, rax
0x14000d2de  jnz     short loc_14000D31C
0x14000d2e0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000d2e7  test    rax, rax
0x14000d2ea  jnz     short loc_14000D300
0x14000d2ec  lea     rcx, aNtdllDll; "ntdll.dll"
0x14000d2f3  call    cs:__imp_GetModuleHandleW
0x14000d2f9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000d300  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x14000d307  mov     rcx, rax; hModule
0x14000d30a  call    cs:__imp_GetProcAddress
0x14000d310  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x14000d317  test    rax, rax
0x14000d31a  jz      short loc_14000D322
0x14000d31c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d321  nop
0x14000d322  add     rsp, 28h
0x14000d326  retn
```
