# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180005550`
- end: `0x1800055a7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180005550`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005573`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005573`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000558a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000558a`

## string_xrefs

- `0x18000556c`: `ntdll.dll`
- `0x180005580`: `RtlDllShutdownInProgress`

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
0x180005550  sub     rsp, 28h
0x180005554  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000555b  test    rax, rax
0x18000555e  jnz     short loc_18000559C
0x180005560  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005567  test    rax, rax
0x18000556a  jnz     short loc_180005580
0x18000556c  lea     rcx, ModuleName; "ntdll.dll"
0x180005573  call    cs:__imp_GetModuleHandleW
0x180005579  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005580  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180005587  mov     rcx, rax; hModule
0x18000558a  call    cs:__imp_GetProcAddress
0x180005590  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180005597  test    rax, rax
0x18000559a  jz      short loc_1800055A2
0x18000559c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055a1  nop
0x1800055a2  add     rsp, 28h
0x1800055a6  retn
```
