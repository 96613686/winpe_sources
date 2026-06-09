# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180007030`
- end: `0x180007087`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007030`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000706a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000706a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007053`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007053`

## string_xrefs

- `0x18000704c`: `ntdll.dll`
- `0x180007060`: `RtlDllShutdownInProgress`

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
0x180007030  sub     rsp, 28h
0x180007034  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000703b  test    rax, rax
0x18000703e  jnz     short loc_18000707C
0x180007040  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007047  test    rax, rax
0x18000704a  jnz     short loc_180007060
0x18000704c  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180007053  call    cs:__imp_GetModuleHandleW
0x180007059  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007060  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180007067  mov     rcx, rax; hModule
0x18000706a  call    cs:__imp_GetProcAddress
0x180007070  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180007077  test    rax, rax
0x18000707a  jz      short loc_180007082
0x18000707c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007081  nop
0x180007082  add     rsp, 28h
0x180007086  retn
```
