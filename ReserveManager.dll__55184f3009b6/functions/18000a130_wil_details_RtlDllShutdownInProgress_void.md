# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000a130`
- end: `0x18000a190`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `96`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000a130`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000a15c`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000a15c`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000a173`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000a173`

## string_xrefs

- `0x18000a155`: `ntdll.dll`
- `0x18000a169`: `RtlDllShutdownInProgress`

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
0x18000a130  sub     rsp, 38h
0x18000a134  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000a13d  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000a144  test    rax, rax
0x18000a147  jnz     short loc_18000A185
0x18000a149  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a150  test    rax, rax
0x18000a153  jnz     short loc_18000A169
0x18000a155  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000a15c  call    cs:__imp_GetModuleHandleW
0x18000a162  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a169  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000a170  mov     rcx, rax; hModule
0x18000a173  call    cs:__imp_GetProcAddress
0x18000a179  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000a180  test    rax, rax
0x18000a183  jz      short loc_18000A18B
0x18000a185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a18a  nop
0x18000a18b  add     rsp, 38h
0x18000a18f  retn
```
