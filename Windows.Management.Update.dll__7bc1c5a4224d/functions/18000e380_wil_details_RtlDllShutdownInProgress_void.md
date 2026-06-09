# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000e380`
- end: `0x18000e3d7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000e380`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e3a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e3a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e3ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e3ba`

## string_xrefs

- `0x18000e39c`: `ntdll.dll`
- `0x18000e3b0`: `RtlDllShutdownInProgress`

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
0x18000e380  sub     rsp, 28h
0x18000e384  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000e38b  test    rax, rax
0x18000e38e  jnz     short loc_18000E3CC
0x18000e390  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e397  test    rax, rax
0x18000e39a  jnz     short loc_18000E3B0
0x18000e39c  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000e3a3  call    cs:__imp_GetModuleHandleW
0x18000e3a9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e3b0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000e3b7  mov     rcx, rax; hModule
0x18000e3ba  call    cs:__imp_GetProcAddress
0x18000e3c0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000e3c7  test    rax, rax
0x18000e3ca  jz      short loc_18000E3D2
0x18000e3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3d1  nop
0x18000e3d2  add     rsp, 28h
0x18000e3d6  retn
```
