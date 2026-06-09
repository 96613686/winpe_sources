# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140007df0`
- end: `0x140007e47`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140007df0`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007e13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007e13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007e2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007e2a`

## string_xrefs

- `0x140007e0c`: `ntdll.dll`
- `0x140007e20`: `RtlDllShutdownInProgress`

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
0x140007df0  sub     rsp, 28h
0x140007df4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x140007dfb  test    rax, rax
0x140007dfe  jnz     short loc_140007E3C
0x140007e00  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140007e07  test    rax, rax
0x140007e0a  jnz     short loc_140007E20
0x140007e0c  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x140007e13  call    cs:__imp_GetModuleHandleW
0x140007e19  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140007e20  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x140007e27  mov     rcx, rax; hModule
0x140007e2a  call    cs:__imp_GetProcAddress
0x140007e30  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x140007e37  test    rax, rax
0x140007e3a  jz      short loc_140007E42
0x140007e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e41  nop
0x140007e42  add     rsp, 28h
0x140007e46  retn
```
