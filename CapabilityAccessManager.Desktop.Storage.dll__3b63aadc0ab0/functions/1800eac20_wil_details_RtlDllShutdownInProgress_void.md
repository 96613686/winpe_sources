# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800eac20`
- end: `0x1800eac77`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800eac20`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800eac5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800eac5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800eac43`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800eac43`

## string_xrefs

- `0x1800eac3c`: `ntdll.dll`
- `0x1800eac50`: `RtlDllShutdownInProgress`

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
0x1800eac20  sub     rsp, 28h
0x1800eac24  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800eac2b  test    rax, rax
0x1800eac2e  jnz     short loc_1800EAC6C
0x1800eac30  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800eac37  test    rax, rax
0x1800eac3a  jnz     short loc_1800EAC50
0x1800eac3c  lea     rcx, ModuleName; "ntdll.dll"
0x1800eac43  call    cs:__imp_GetModuleHandleW
0x1800eac49  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800eac50  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800eac57  mov     rcx, rax; hModule
0x1800eac5a  call    cs:__imp_GetProcAddress
0x1800eac60  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800eac67  test    rax, rax
0x1800eac6a  jz      short loc_1800EAC72
0x1800eac6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eac71  nop
0x1800eac72  add     rsp, 28h
0x1800eac76  retn
```
