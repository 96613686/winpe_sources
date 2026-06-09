# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000ae10`
- end: `0x18000ae67`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000ae10`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ae4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ae4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ae33`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ae33`

## string_xrefs

- `0x18000ae2c`: `ntdll.dll`
- `0x18000ae40`: `RtlDllShutdownInProgress`

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
0x18000ae10  sub     rsp, 28h
0x18000ae14  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000ae1b  test    rax, rax
0x18000ae1e  jnz     short loc_18000AE5C
0x18000ae20  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ae27  test    rax, rax
0x18000ae2a  jnz     short loc_18000AE40
0x18000ae2c  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000ae33  call    cs:__imp_GetModuleHandleW
0x18000ae39  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ae40  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000ae47  mov     rcx, rax; hModule
0x18000ae4a  call    cs:__imp_GetProcAddress
0x18000ae50  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000ae57  test    rax, rax
0x18000ae5a  jz      short loc_18000AE62
0x18000ae5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae61  nop
0x18000ae62  add     rsp, 28h
0x18000ae66  retn
```
