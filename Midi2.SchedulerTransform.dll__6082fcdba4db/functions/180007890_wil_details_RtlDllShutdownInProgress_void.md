# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180007890`
- end: `0x1800078e7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007890`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800078ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800078ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800078b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800078b3`

## string_xrefs

- `0x1800078ac`: `ntdll.dll`
- `0x1800078c0`: `RtlDllShutdownInProgress`

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
0x180007890  sub     rsp, 28h
0x180007894  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000789b  test    rax, rax
0x18000789e  jnz     short loc_1800078DC
0x1800078a0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800078a7  test    rax, rax
0x1800078aa  jnz     short loc_1800078C0
0x1800078ac  lea     rcx, aNtdllDll; "ntdll.dll"
0x1800078b3  call    cs:__imp_GetModuleHandleW
0x1800078b9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800078c0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800078c7  mov     rcx, rax; hModule
0x1800078ca  call    cs:__imp_GetProcAddress
0x1800078d0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800078d7  test    rax, rax
0x1800078da  jz      short loc_1800078E2
0x1800078dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078e1  nop
0x1800078e2  add     rsp, 28h
0x1800078e6  retn
```
