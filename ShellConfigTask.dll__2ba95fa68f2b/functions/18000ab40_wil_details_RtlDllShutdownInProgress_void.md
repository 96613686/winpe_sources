# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000ab40`
- end: `0x18000ab97`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000ab40`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ab63`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ab63`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ab7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ab7a`

## string_xrefs

- `0x18000ab5c`: `ntdll.dll`
- `0x18000ab70`: `RtlDllShutdownInProgress`

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
0x18000ab40  sub     rsp, 28h
0x18000ab44  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000ab4b  test    rax, rax
0x18000ab4e  jnz     short loc_18000AB8C
0x18000ab50  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ab57  test    rax, rax
0x18000ab5a  jnz     short loc_18000AB70
0x18000ab5c  lea     rcx, ModuleName; "ntdll.dll"
0x18000ab63  call    cs:__imp_GetModuleHandleW
0x18000ab69  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ab70  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000ab77  mov     rcx, rax; hModule
0x18000ab7a  call    cs:__imp_GetProcAddress
0x18000ab80  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000ab87  test    rax, rax
0x18000ab8a  jz      short loc_18000AB92
0x18000ab8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab91  nop
0x18000ab92  add     rsp, 28h
0x18000ab96  retn
```
