# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180010790`
- end: `0x1800107f4`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `100`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180010790`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800107b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800107b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800107d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800107d0`

## string_xrefs

- `0x1800107ac`: `ntdll.dll`
- `0x1800107c6`: `RtlDllShutdownInProgress`

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
0x180010790  sub     rsp, 28h
0x180010794  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18001079b  test    rax, rax
0x18001079e  jnz     short loc_1800107E8
0x1800107a0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800107a7  test    rax, rax
0x1800107aa  jnz     short loc_1800107C6
0x1800107ac  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800107b3  call    cs:__imp_GetModuleHandleW
0x1800107ba  nop     dword ptr [rax+rax+00h]
0x1800107bf  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800107c6  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800107cd  mov     rcx, rax; hModule
0x1800107d0  call    cs:__imp_GetProcAddress
0x1800107d7  nop     dword ptr [rax+rax+00h]
0x1800107dc  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800107e3  test    rax, rax
0x1800107e6  jz      short loc_1800107EE
0x1800107e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107ed  nop
0x1800107ee  add     rsp, 28h
0x1800107f2  retn
```
