# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180008a60`
- end: `0x180008ab7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180008a60`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008a9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008a9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008a83`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008a83`

## string_xrefs

- `0x180008a7c`: `ntdll.dll`
- `0x180008a90`: `RtlDllShutdownInProgress`

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
0x180008a60  sub     rsp, 28h
0x180008a64  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180008a6b  test    rax, rax
0x180008a6e  jnz     short loc_180008AAC
0x180008a70  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008a77  test    rax, rax
0x180008a7a  jnz     short loc_180008A90
0x180008a7c  lea     rcx, ModuleName; "ntdll.dll"
0x180008a83  call    cs:__imp_GetModuleHandleW
0x180008a89  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008a90  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180008a97  mov     rcx, rax; hModule
0x180008a9a  call    cs:__imp_GetProcAddress
0x180008aa0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180008aa7  test    rax, rax
0x180008aaa  jz      short loc_180008AB2
0x180008aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ab1  nop
0x180008ab2  add     rsp, 28h
0x180008ab6  retn
```
