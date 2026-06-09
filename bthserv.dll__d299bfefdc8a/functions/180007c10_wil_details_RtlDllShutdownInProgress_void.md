# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180007c10`
- end: `0x180007c67`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007c10`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007c33`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007c33`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007c4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007c4a`

## string_xrefs

- `0x180007c2c`: `ntdll.dll`
- `0x180007c40`: `RtlDllShutdownInProgress`

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
0x180007c10  sub     rsp, 28h
0x180007c14  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180007c1b  test    rax, rax
0x180007c1e  jnz     short loc_180007C5C
0x180007c20  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007c27  test    rax, rax
0x180007c2a  jnz     short loc_180007C40
0x180007c2c  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180007c33  call    cs:__imp_GetModuleHandleW
0x180007c39  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007c40  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180007c47  mov     rcx, rax; hModule
0x180007c4a  call    cs:__imp_GetProcAddress
0x180007c50  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180007c57  test    rax, rax
0x180007c5a  jz      short loc_180007C62
0x180007c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c61  nop
0x180007c62  add     rsp, 28h
0x180007c66  retn
```
