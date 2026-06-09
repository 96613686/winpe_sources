# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180008950`
- end: `0x1800089a7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180008950`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008973`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008973`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000898a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000898a`

## string_xrefs

- `0x18000896c`: `ntdll.dll`
- `0x180008980`: `RtlDllShutdownInProgress`

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
0x180008950  sub     rsp, 28h
0x180008954  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000895b  test    rax, rax
0x18000895e  jnz     short loc_18000899C
0x180008960  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008967  test    rax, rax
0x18000896a  jnz     short loc_180008980
0x18000896c  lea     rcx, aNtdllDll; "ntdll.dll"
0x180008973  call    cs:__imp_GetModuleHandleW
0x180008979  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008980  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180008987  mov     rcx, rax; hModule
0x18000898a  call    cs:__imp_GetProcAddress
0x180008990  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180008997  test    rax, rax
0x18000899a  jz      short loc_1800089A2
0x18000899c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089a1  nop
0x1800089a2  add     rsp, 28h
0x1800089a6  retn
```
