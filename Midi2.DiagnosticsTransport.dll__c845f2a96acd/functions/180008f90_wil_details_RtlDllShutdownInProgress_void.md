# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180008f90`
- end: `0x180008fe7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180008f90`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008fca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008fca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008fb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008fb3`

## string_xrefs

- `0x180008fac`: `ntdll.dll`
- `0x180008fc0`: `RtlDllShutdownInProgress`

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
0x180008f90  sub     rsp, 28h
0x180008f94  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180008f9b  test    rax, rax
0x180008f9e  jnz     short loc_180008FDC
0x180008fa0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008fa7  test    rax, rax
0x180008faa  jnz     short loc_180008FC0
0x180008fac  lea     rcx, aNtdllDll; "ntdll.dll"
0x180008fb3  call    cs:__imp_GetModuleHandleW
0x180008fb9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008fc0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180008fc7  mov     rcx, rax; hModule
0x180008fca  call    cs:__imp_GetProcAddress
0x180008fd0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180008fd7  test    rax, rax
0x180008fda  jz      short loc_180008FE2
0x180008fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fe1  nop
0x180008fe2  add     rsp, 28h
0x180008fe6  retn
```
