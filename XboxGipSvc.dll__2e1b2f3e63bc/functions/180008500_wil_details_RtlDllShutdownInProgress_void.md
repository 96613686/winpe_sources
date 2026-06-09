# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180008500`
- end: `0x180008557`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180008500`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000853a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000853a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008523`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008523`

## string_xrefs

- `0x18000851c`: `ntdll.dll`
- `0x180008530`: `RtlDllShutdownInProgress`

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
0x180008500  sub     rsp, 28h
0x180008504  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000850b  test    rax, rax
0x18000850e  jnz     short loc_18000854C
0x180008510  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008517  test    rax, rax
0x18000851a  jnz     short loc_180008530
0x18000851c  lea     rcx, ModuleName; "ntdll.dll"
0x180008523  call    cs:__imp_GetModuleHandleW
0x180008529  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008530  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180008537  mov     rcx, rax; hModule
0x18000853a  call    cs:__imp_GetProcAddress
0x180008540  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180008547  test    rax, rax
0x18000854a  jz      short loc_180008552
0x18000854c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008551  nop
0x180008552  add     rsp, 28h
0x180008556  retn
```
