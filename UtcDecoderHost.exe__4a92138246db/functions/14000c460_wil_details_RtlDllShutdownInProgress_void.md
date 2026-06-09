# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x14000c460`
- end: `0x14000c4b7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14000c460`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000c483`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000c483`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c49a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c49a`

## string_xrefs

- `0x14000c47c`: `ntdll.dll`
- `0x14000c490`: `RtlDllShutdownInProgress`

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
0x14000c460  sub     rsp, 28h
0x14000c464  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000c46b  test    rax, rax
0x14000c46e  jnz     short loc_14000C4AC
0x14000c470  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c477  test    rax, rax
0x14000c47a  jnz     short loc_14000C490
0x14000c47c  lea     rcx, ModuleName; "ntdll.dll"
0x14000c483  call    cs:__imp_GetModuleHandleW
0x14000c489  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c490  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x14000c497  mov     rcx, rax; hModule
0x14000c49a  call    cs:__imp_GetProcAddress
0x14000c4a0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x14000c4a7  test    rax, rax
0x14000c4aa  jz      short loc_14000C4B2
0x14000c4ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c4b1  nop
0x14000c4b2  add     rsp, 28h
0x14000c4b6  retn
```
