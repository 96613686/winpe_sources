# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180004610`
- end: `0x180004674`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `100`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180004610`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004633`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004633`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004650`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004650`

## string_xrefs

- `0x18000462c`: `ntdll.dll`
- `0x180004646`: `RtlDllShutdownInProgress`

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
0x180004610  sub     rsp, 28h
0x180004614  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000461b  test    rax, rax
0x18000461e  jnz     short loc_180004668
0x180004620  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004627  test    rax, rax
0x18000462a  jnz     short loc_180004646
0x18000462c  lea     rcx, ModuleName; "ntdll.dll"
0x180004633  call    cs:__imp_GetModuleHandleW
0x18000463a  nop     dword ptr [rax+rax+00h]
0x18000463f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004646  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000464d  mov     rcx, rax; hModule
0x180004650  call    cs:__imp_GetProcAddress
0x180004657  nop     dword ptr [rax+rax+00h]
0x18000465c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180004663  test    rax, rax
0x180004666  jz      short loc_18000466E
0x180004668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000466d  nop
0x18000466e  add     rsp, 28h
0x180004672  retn
```
