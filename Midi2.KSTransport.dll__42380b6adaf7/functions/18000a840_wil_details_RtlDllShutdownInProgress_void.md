# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000a840`
- end: `0x18000a897`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000a840`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a863`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a863`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a87a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a87a`

## string_xrefs

- `0x18000a85c`: `ntdll.dll`
- `0x18000a870`: `RtlDllShutdownInProgress`

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
0x18000a840  sub     rsp, 28h
0x18000a844  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000a84b  test    rax, rax
0x18000a84e  jnz     short loc_18000A88C
0x18000a850  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a857  test    rax, rax
0x18000a85a  jnz     short loc_18000A870
0x18000a85c  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000a863  call    cs:__imp_GetModuleHandleW
0x18000a869  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a870  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000a877  mov     rcx, rax; hModule
0x18000a87a  call    cs:__imp_GetProcAddress
0x18000a880  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000a887  test    rax, rax
0x18000a88a  jz      short loc_18000A892
0x18000a88c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a891  nop
0x18000a892  add     rsp, 28h
0x18000a896  retn
```
