# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180006b10`
- end: `0x180006b6a`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006b10`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006b33`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006b33`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006b4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006b4a`

## string_xrefs

- `0x180006b2c`: `ntdll.dll`
- `0x180006b40`: `RtlDllShutdownInProgress`

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
0x180006b10  sub     rsp, 28h
0x180006b14  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180006b1b  test    rax, rax
0x180006b1e  jnz     short loc_180006B61
0x180006b20  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006b27  test    rax, rax
0x180006b2a  jnz     short loc_180006B40
0x180006b2c  lea     rcx, ModuleName; "ntdll.dll"
0x180006b33  call    cs:__imp_GetModuleHandleW
0x180006b39  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006b40  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180006b47  mov     rcx, rax; hModule
0x180006b4a  call    cs:__imp_GetProcAddress
0x180006b50  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180006b57  test    rax, rax
0x180006b5a  jnz     short loc_180006B61
0x180006b5c  add     rsp, 28h
0x180006b60  retn
0x180006b61  add     rsp, 28h
0x180006b65  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
