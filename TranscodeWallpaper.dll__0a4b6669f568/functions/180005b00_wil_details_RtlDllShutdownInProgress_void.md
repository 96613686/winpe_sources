# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180005b00`
- end: `0x180005b57`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180005b00`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005b3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005b3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005b23`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005b23`

## string_xrefs

- `0x180005b1c`: `ntdll.dll`
- `0x180005b30`: `RtlDllShutdownInProgress`

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
0x180005b00  sub     rsp, 28h
0x180005b04  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180005b0b  test    rax, rax
0x180005b0e  jnz     short loc_180005B4C
0x180005b10  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005b17  test    rax, rax
0x180005b1a  jnz     short loc_180005B30
0x180005b1c  lea     rcx, ModuleName; "ntdll.dll"
0x180005b23  call    cs:__imp_GetModuleHandleW
0x180005b29  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005b30  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180005b37  mov     rcx, rax; hModule
0x180005b3a  call    cs:__imp_GetProcAddress
0x180005b40  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180005b47  test    rax, rax
0x180005b4a  jz      short loc_180005B52
0x180005b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b51  nop
0x180005b52  add     rsp, 28h
0x180005b56  retn
```
