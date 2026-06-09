# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000a560`
- end: `0x18000a5b7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000a560`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a583`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a583`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a59a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a59a`

## string_xrefs

- `0x18000a57c`: `ntdll.dll`
- `0x18000a590`: `RtlDllShutdownInProgress`

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
0x18000a560  sub     rsp, 28h
0x18000a564  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000a56b  test    rax, rax
0x18000a56e  jnz     short loc_18000A5AC
0x18000a570  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a577  test    rax, rax
0x18000a57a  jnz     short loc_18000A590
0x18000a57c  lea     rcx, ModuleName; "ntdll.dll"
0x18000a583  call    cs:__imp_GetModuleHandleW
0x18000a589  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a590  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000a597  mov     rcx, rax; hModule
0x18000a59a  call    cs:__imp_GetProcAddress
0x18000a5a0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000a5a7  test    rax, rax
0x18000a5aa  jz      short loc_18000A5B2
0x18000a5ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5b1  nop
0x18000a5b2  add     rsp, 28h
0x18000a5b6  retn
```
