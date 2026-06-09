# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180007e50`
- end: `0x180007ea7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007e50`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007e73`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007e73`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007e8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007e8a`

## string_xrefs

- `0x180007e6c`: `ntdll.dll`
- `0x180007e80`: `RtlDllShutdownInProgress`

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
0x180007e50  sub     rsp, 28h
0x180007e54  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180007e5b  test    rax, rax
0x180007e5e  jnz     short loc_180007E9C
0x180007e60  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007e67  test    rax, rax
0x180007e6a  jnz     short loc_180007E80
0x180007e6c  lea     rcx, aNtdllDll; "ntdll.dll"
0x180007e73  call    cs:__imp_GetModuleHandleW
0x180007e79  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007e80  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180007e87  mov     rcx, rax; hModule
0x180007e8a  call    cs:__imp_GetProcAddress
0x180007e90  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180007e97  test    rax, rax
0x180007e9a  jz      short loc_180007EA2
0x180007e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ea1  nop
0x180007ea2  add     rsp, 28h
0x180007ea6  retn
```
