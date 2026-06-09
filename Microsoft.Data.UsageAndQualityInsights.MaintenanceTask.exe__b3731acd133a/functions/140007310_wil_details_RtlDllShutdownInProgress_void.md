# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140007310`
- end: `0x140007367`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140007310`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007333`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007333`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000734a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000734a`

## string_xrefs

- `0x14000732c`: `ntdll.dll`
- `0x140007340`: `RtlDllShutdownInProgress`

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
0x140007310  sub     rsp, 28h
0x140007314  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000731b  test    rax, rax
0x14000731e  jnz     short loc_14000735C
0x140007320  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140007327  test    rax, rax
0x14000732a  jnz     short loc_140007340
0x14000732c  lea     rcx, ModuleName; "ntdll.dll"
0x140007333  call    cs:__imp_GetModuleHandleW
0x140007339  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140007340  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x140007347  mov     rcx, rax; hModule
0x14000734a  call    cs:__imp_GetProcAddress
0x140007350  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x140007357  test    rax, rax
0x14000735a  jz      short loc_140007362
0x14000735c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007361  nop
0x140007362  add     rsp, 28h
0x140007366  retn
```
