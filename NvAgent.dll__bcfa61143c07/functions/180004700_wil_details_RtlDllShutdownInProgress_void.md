# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180004700`
- end: `0x180004757`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180004700`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004723`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004723`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000473a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000473a`

## string_xrefs

- `0x18000471c`: `ntdll.dll`
- `0x180004730`: `RtlDllShutdownInProgress`

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
0x180004700  sub     rsp, 28h
0x180004704  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000470b  test    rax, rax
0x18000470e  jnz     short loc_18000474C
0x180004710  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004717  test    rax, rax
0x18000471a  jnz     short loc_180004730
0x18000471c  lea     rcx, ModuleName; "ntdll.dll"
0x180004723  call    cs:__imp_GetModuleHandleW
0x180004729  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004730  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180004737  mov     rcx, rax; hModule
0x18000473a  call    cs:__imp_GetProcAddress
0x180004740  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180004747  test    rax, rax
0x18000474a  jz      short loc_180004752
0x18000474c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004751  nop
0x180004752  add     rsp, 28h
0x180004756  retn
```
