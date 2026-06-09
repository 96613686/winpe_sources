# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180008d20`
- end: `0x180008d7a`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180008d20`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008d5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008d5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008d43`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008d43`

## string_xrefs

- `0x180008d3c`: `ntdll.dll`
- `0x180008d50`: `RtlDllShutdownInProgress`

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
0x180008d20  sub     rsp, 28h
0x180008d24  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180008d2b  test    rax, rax
0x180008d2e  jnz     short loc_180008D71
0x180008d30  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008d37  test    rax, rax
0x180008d3a  jnz     short loc_180008D50
0x180008d3c  lea     rcx, ModuleName; "ntdll.dll"
0x180008d43  call    cs:__imp_GetModuleHandleW
0x180008d49  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008d50  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180008d57  mov     rcx, rax; hModule
0x180008d5a  call    cs:__imp_GetProcAddress
0x180008d60  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180008d67  test    rax, rax
0x180008d6a  jnz     short loc_180008D71
0x180008d6c  add     rsp, 28h
0x180008d70  retn
0x180008d71  add     rsp, 28h
0x180008d75  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
