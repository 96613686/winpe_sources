# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180012e10`
- end: `0x180012e6a`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180012e10`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180012e33`
- `KERNEL32!GetModuleHandleW` at `0x180012e33`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012e4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012e4a`

## string_xrefs

- `0x180012e2c`: `ntdll.dll`
- `0x180012e40`: `RtlDllShutdownInProgress`

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
0x180012e10  sub     rsp, 28h
0x180012e14  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180012e1b  test    rax, rax
0x180012e1e  jnz     short loc_180012E61
0x180012e20  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012e27  test    rax, rax
0x180012e2a  jnz     short loc_180012E40
0x180012e2c  lea     rcx, ModuleName; "ntdll.dll"
0x180012e33  call    cs:__imp_GetModuleHandleW
0x180012e39  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012e40  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180012e47  mov     rcx, rax; hModule
0x180012e4a  call    cs:__imp_GetProcAddress
0x180012e50  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180012e57  test    rax, rax
0x180012e5a  jnz     short loc_180012E61
0x180012e5c  add     rsp, 28h
0x180012e60  retn
0x180012e61  add     rsp, 28h
0x180012e65  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
