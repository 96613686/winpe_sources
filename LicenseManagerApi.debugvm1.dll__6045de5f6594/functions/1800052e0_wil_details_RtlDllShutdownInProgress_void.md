# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800052e0`
- end: `0x180005337`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800052e0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000531a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000531a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005303`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005303`

## string_xrefs

- `0x1800052fc`: `ntdll.dll`
- `0x180005310`: `RtlDllShutdownInProgress`

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
0x1800052e0  sub     rsp, 28h
0x1800052e4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800052eb  test    rax, rax
0x1800052ee  jnz     short loc_18000532C
0x1800052f0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800052f7  test    rax, rax
0x1800052fa  jnz     short loc_180005310
0x1800052fc  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180005303  call    cs:__imp_GetModuleHandleW
0x180005309  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005310  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180005317  mov     rcx, rax; hModule
0x18000531a  call    cs:__imp_GetProcAddress
0x180005320  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180005327  test    rax, rax
0x18000532a  jz      short loc_180005332
0x18000532c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005331  nop
0x180005332  add     rsp, 28h
0x180005336  retn
```
