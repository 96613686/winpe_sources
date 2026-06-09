# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180007180`
- end: `0x1800071dc`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `92`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007180`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800071ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800071ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800071a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800071a3`

## string_xrefs

- `0x18000719c`: `ntdll.dll`
- `0x1800071b0`: `RtlDllShutdownInProgress`

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
0x180007180  sub     rsp, 28h
0x180007184  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000718b  test    rax, rax
0x18000718e  jnz     short loc_1800071D1
0x180007190  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007197  test    rax, rax
0x18000719a  jnz     short loc_1800071B0
0x18000719c  lea     rcx, ModuleName; "ntdll.dll"
0x1800071a3  call    cs:__imp_GetModuleHandleW
0x1800071a9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800071b0  lea     rdx, ProcName; "RtlDllShutdownInProgress"
0x1800071b7  mov     rcx, rax; hModule
0x1800071ba  call    cs:__imp_GetProcAddress
0x1800071c0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800071c7  test    rax, rax
0x1800071ca  jnz     short loc_1800071D1
0x1800071cc  add     rsp, 28h
0x1800071d0  retn
0x1800071d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071d6  nop
0x1800071d7  add     rsp, 28h
0x1800071db  retn
```
