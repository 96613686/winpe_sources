# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140006340`
- end: `0x14000639a`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140006340`
- `0x140007010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006363`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006363`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000637a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000637a`

## string_xrefs

- `0x14000635c`: `ntdll.dll`
- `0x140006370`: `RtlDllShutdownInProgress`

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
0x140006340  sub     rsp, 28h
0x140006344  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000634b  test    rax, rax
0x14000634e  jnz     short loc_140006391
0x140006350  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140006357  test    rax, rax
0x14000635a  jnz     short loc_140006370
0x14000635c  lea     rcx, ModuleName; "ntdll.dll"
0x140006363  call    cs:__imp_GetModuleHandleW
0x140006369  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140006370  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x140006377  mov     rcx, rax; hModule
0x14000637a  call    cs:__imp_GetProcAddress
0x140006380  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x140006387  test    rax, rax
0x14000638a  jnz     short loc_140006391
0x14000638c  add     rsp, 28h
0x140006390  retn
0x140006391  add     rsp, 28h
0x140006395  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
