# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140004de0`
- end: `0x140004e37`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140004de0`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140004e1a`
- `KERNEL32!GetProcAddress` at `0x140004e1a`
- `KERNEL32!GetModuleHandleW` at `0x140004e03`
- `KERNEL32!GetModuleHandleW` at `0x140004e03`

## string_xrefs

- `0x140004dfc`: `ntdll.dll`
- `0x140004e10`: `RtlDllShutdownInProgress`

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
0x140004de0  sub     rsp, 28h
0x140004de4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x140004deb  test    rax, rax
0x140004dee  jnz     short loc_140004E2C
0x140004df0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004df7  test    rax, rax
0x140004dfa  jnz     short loc_140004E10
0x140004dfc  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x140004e03  call    cs:__imp_GetModuleHandleW
0x140004e09  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004e10  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x140004e17  mov     rcx, rax; hModule
0x140004e1a  call    cs:__imp_GetProcAddress
0x140004e20  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x140004e27  test    rax, rax
0x140004e2a  jz      short loc_140004E32
0x140004e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e31  nop
0x140004e32  add     rsp, 28h
0x140004e36  retn
```
