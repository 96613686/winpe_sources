# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x14000a6e0`
- end: `0x14000a737`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14000a6e0`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000a71a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000a71a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a703`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a703`

## string_xrefs

- `0x14000a6fc`: `ntdll.dll`
- `0x14000a710`: `RtlDllShutdownInProgress`

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
0x14000a6e0  sub     rsp, 28h
0x14000a6e4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000a6eb  test    rax, rax
0x14000a6ee  jnz     short loc_14000A72C
0x14000a6f0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a6f7  test    rax, rax
0x14000a6fa  jnz     short loc_14000A710
0x14000a6fc  lea     rcx, ModuleName; "ntdll.dll"
0x14000a703  call    cs:__imp_GetModuleHandleW
0x14000a709  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a710  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x14000a717  mov     rcx, rax; hModule
0x14000a71a  call    cs:__imp_GetProcAddress
0x14000a720  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x14000a727  test    rax, rax
0x14000a72a  jz      short loc_14000A732
0x14000a72c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a731  nop
0x14000a732  add     rsp, 28h
0x14000a736  retn
```
