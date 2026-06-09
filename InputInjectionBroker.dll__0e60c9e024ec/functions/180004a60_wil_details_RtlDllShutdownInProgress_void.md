# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180004a60`
- end: `0x180004ab7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180004a60`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004a9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004a9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004a83`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004a83`

## string_xrefs

- `0x180004a7c`: `ntdll.dll`
- `0x180004a90`: `RtlDllShutdownInProgress`

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
0x180004a60  sub     rsp, 28h
0x180004a64  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180004a6b  test    rax, rax
0x180004a6e  jnz     short loc_180004AAC
0x180004a70  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004a77  test    rax, rax
0x180004a7a  jnz     short loc_180004A90
0x180004a7c  lea     rcx, ModuleName; "ntdll.dll"
0x180004a83  call    cs:__imp_GetModuleHandleW
0x180004a89  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004a90  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180004a97  mov     rcx, rax; hModule
0x180004a9a  call    cs:__imp_GetProcAddress
0x180004aa0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180004aa7  test    rax, rax
0x180004aaa  jz      short loc_180004AB2
0x180004aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ab1  nop
0x180004ab2  add     rsp, 28h
0x180004ab6  retn
```
