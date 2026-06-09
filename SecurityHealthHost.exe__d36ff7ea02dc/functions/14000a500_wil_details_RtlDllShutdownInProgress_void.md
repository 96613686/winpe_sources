# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x14000a500`
- end: `0x14000a557`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14000a500`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000a523`
- `KERNEL32!GetModuleHandleW` at `0x14000a523`
- `KERNEL32!GetProcAddress` at `0x14000a53a`
- `KERNEL32!GetProcAddress` at `0x14000a53a`

## string_xrefs

- `0x14000a51c`: `ntdll.dll`
- `0x14000a530`: `RtlDllShutdownInProgress`

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
0x14000a500  sub     rsp, 28h
0x14000a504  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000a50b  test    rax, rax
0x14000a50e  jnz     short loc_14000A54C
0x14000a510  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a517  test    rax, rax
0x14000a51a  jnz     short loc_14000A530
0x14000a51c  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000a523  call    cs:__imp_GetModuleHandleW
0x14000a529  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a530  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x14000a537  mov     rcx, rax; hModule
0x14000a53a  call    cs:__imp_GetProcAddress
0x14000a540  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x14000a547  test    rax, rax
0x14000a54a  jz      short loc_14000A552
0x14000a54c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a551  nop
0x14000a552  add     rsp, 28h
0x14000a556  retn
```
