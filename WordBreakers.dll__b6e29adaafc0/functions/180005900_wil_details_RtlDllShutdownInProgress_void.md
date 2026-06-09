# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180005900`
- end: `0x180005957`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180005900`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000593a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000593a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005923`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005923`

## string_xrefs

- `0x18000591c`: `ntdll.dll`
- `0x180005930`: `RtlDllShutdownInProgress`

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
0x180005900  sub     rsp, 28h
0x180005904  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000590b  test    rax, rax
0x18000590e  jnz     short loc_18000594C
0x180005910  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005917  test    rax, rax
0x18000591a  jnz     short loc_180005930
0x18000591c  lea     rcx, ModuleName; "ntdll.dll"
0x180005923  call    cs:__imp_GetModuleHandleW
0x180005929  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005930  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180005937  mov     rcx, rax; hModule
0x18000593a  call    cs:__imp_GetProcAddress
0x180005940  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180005947  test    rax, rax
0x18000594a  jz      short loc_180005952
0x18000594c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005951  nop
0x180005952  add     rsp, 28h
0x180005956  retn
```
