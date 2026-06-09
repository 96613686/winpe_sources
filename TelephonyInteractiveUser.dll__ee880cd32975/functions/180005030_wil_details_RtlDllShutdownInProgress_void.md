# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180005030`
- end: `0x18000508a`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180005030`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005053`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005053`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000506a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000506a`

## string_xrefs

- `0x18000504c`: `ntdll.dll`
- `0x180005060`: `RtlDllShutdownInProgress`

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
0x180005030  sub     rsp, 28h
0x180005034  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000503b  test    rax, rax
0x18000503e  jnz     short loc_180005081
0x180005040  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005047  test    rax, rax
0x18000504a  jnz     short loc_180005060
0x18000504c  lea     rcx, ModuleName; "ntdll.dll"
0x180005053  call    cs:__imp_GetModuleHandleW
0x180005059  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005060  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180005067  mov     rcx, rax; hModule
0x18000506a  call    cs:__imp_GetProcAddress
0x180005070  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180005077  test    rax, rax
0x18000507a  jnz     short loc_180005081
0x18000507c  add     rsp, 28h
0x180005080  retn
0x180005081  add     rsp, 28h
0x180005085  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
