# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140006480`
- end: `0x1400064e0`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `96`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140006480`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400064c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400064c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400064ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400064ac`

## string_xrefs

- `0x1400064a5`: `ntdll.dll`
- `0x1400064b9`: `RtlDllShutdownInProgress`

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
0x140006480  sub     rsp, 38h
0x140006484  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x14000648d  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x140006494  test    rax, rax
0x140006497  jnz     short loc_1400064D5
0x140006499  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400064a0  test    rax, rax
0x1400064a3  jnz     short loc_1400064B9
0x1400064a5  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1400064ac  call    cs:__imp_GetModuleHandleW
0x1400064b2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400064b9  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1400064c0  mov     rcx, rax; hModule
0x1400064c3  call    cs:__imp_GetProcAddress
0x1400064c9  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1400064d0  test    rax, rax
0x1400064d3  jz      short loc_1400064DB
0x1400064d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400064da  nop
0x1400064db  add     rsp, 38h
0x1400064df  retn
```
