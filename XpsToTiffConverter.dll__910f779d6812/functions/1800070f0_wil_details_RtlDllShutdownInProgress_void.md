# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800070f0`
- end: `0x180007147`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800070f0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000712a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000712a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007113`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007113`

## string_xrefs

- `0x18000710c`: `ntdll.dll`
- `0x180007120`: `RtlDllShutdownInProgress`

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
0x1800070f0  sub     rsp, 28h
0x1800070f4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800070fb  test    rax, rax
0x1800070fe  jnz     short loc_18000713C
0x180007100  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007107  test    rax, rax
0x18000710a  jnz     short loc_180007120
0x18000710c  lea     rcx, ModuleName; "ntdll.dll"
0x180007113  call    cs:__imp_GetModuleHandleW
0x180007119  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007120  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180007127  mov     rcx, rax; hModule
0x18000712a  call    cs:__imp_GetProcAddress
0x180007130  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180007137  test    rax, rax
0x18000713a  jz      short loc_180007142
0x18000713c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007141  nop
0x180007142  add     rsp, 28h
0x180007146  retn
```
