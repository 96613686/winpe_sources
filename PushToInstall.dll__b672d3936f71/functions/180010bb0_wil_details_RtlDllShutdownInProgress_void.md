# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180010bb0`
- end: `0x180010c07`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180010bb0`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010bd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010bd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010bea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010bea`

## string_xrefs

- `0x180010bcc`: `ntdll.dll`
- `0x180010be0`: `RtlDllShutdownInProgress`

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
0x180010bb0  sub     rsp, 28h
0x180010bb4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180010bbb  test    rax, rax
0x180010bbe  jnz     short loc_180010BFC
0x180010bc0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010bc7  test    rax, rax
0x180010bca  jnz     short loc_180010BE0
0x180010bcc  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180010bd3  call    cs:__imp_GetModuleHandleW
0x180010bd9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010be0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180010be7  mov     rcx, rax; hModule
0x180010bea  call    cs:__imp_GetProcAddress
0x180010bf0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180010bf7  test    rax, rax
0x180010bfa  jz      short loc_180010C02
0x180010bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c01  nop
0x180010c02  add     rsp, 28h
0x180010c06  retn
```
