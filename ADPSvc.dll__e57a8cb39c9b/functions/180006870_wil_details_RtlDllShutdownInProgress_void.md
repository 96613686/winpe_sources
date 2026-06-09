# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180006870`
- end: `0x1800068c7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006870`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006893`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006893`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800068aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800068aa`

## string_xrefs

- `0x18000688c`: `ntdll.dll`
- `0x1800068a0`: `RtlDllShutdownInProgress`

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
0x180006870  sub     rsp, 28h
0x180006874  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000687b  test    rax, rax
0x18000687e  jnz     short loc_1800068BC
0x180006880  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006887  test    rax, rax
0x18000688a  jnz     short loc_1800068A0
0x18000688c  lea     rcx, ModuleName; "ntdll.dll"
0x180006893  call    cs:__imp_GetModuleHandleW
0x180006899  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800068a0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800068a7  mov     rcx, rax; hModule
0x1800068aa  call    cs:__imp_GetProcAddress
0x1800068b0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800068b7  test    rax, rax
0x1800068ba  jz      short loc_1800068C2
0x1800068bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068c1  nop
0x1800068c2  add     rsp, 28h
0x1800068c6  retn
```
