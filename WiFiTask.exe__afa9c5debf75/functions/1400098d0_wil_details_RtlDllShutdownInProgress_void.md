# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1400098d0`
- end: `0x140009927`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1400098d0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400098f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400098f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000990a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000990a`

## string_xrefs

- `0x1400098ec`: `ntdll.dll`
- `0x140009900`: `RtlDllShutdownInProgress`

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
0x1400098d0  sub     rsp, 28h
0x1400098d4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1400098db  test    rax, rax
0x1400098de  jnz     short loc_14000991C
0x1400098e0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400098e7  test    rax, rax
0x1400098ea  jnz     short loc_140009900
0x1400098ec  lea     rcx, ModuleName; "ntdll.dll"
0x1400098f3  call    cs:__imp_GetModuleHandleW
0x1400098f9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009900  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x140009907  mov     rcx, rax; hModule
0x14000990a  call    cs:__imp_GetProcAddress
0x140009910  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x140009917  test    rax, rax
0x14000991a  jz      short loc_140009922
0x14000991c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009921  nop
0x140009922  add     rsp, 28h
0x140009926  retn
```
