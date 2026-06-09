# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140004750`
- end: `0x1400047a7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140004750`
- `0x140007010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000478a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000478a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004773`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004773`

## string_xrefs

- `0x14000476c`: `ntdll.dll`
- `0x140004780`: `RtlDllShutdownInProgress`

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
0x140004750  sub     rsp, 28h
0x140004754  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000475b  test    rax, rax
0x14000475e  jnz     short loc_14000479C
0x140004760  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004767  test    rax, rax
0x14000476a  jnz     short loc_140004780
0x14000476c  lea     rcx, ModuleName; "ntdll.dll"
0x140004773  call    cs:__imp_GetModuleHandleW
0x140004779  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004780  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x140004787  mov     rcx, rax; hModule
0x14000478a  call    cs:__imp_GetProcAddress
0x140004790  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x140004797  test    rax, rax
0x14000479a  jz      short loc_1400047A2
0x14000479c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047a1  nop
0x1400047a2  add     rsp, 28h
0x1400047a6  retn
```
