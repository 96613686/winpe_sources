# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140006450`
- end: `0x1400064a7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140006450`
- `0x14000a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140006473`
- `KERNEL32!GetModuleHandleW` at `0x140006473`
- `KERNEL32!GetProcAddress` at `0x14000648a`
- `KERNEL32!GetProcAddress` at `0x14000648a`

## string_xrefs

- `0x14000646c`: `ntdll.dll`
- `0x140006480`: `RtlDllShutdownInProgress`

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
0x140006450  sub     rsp, 28h
0x140006454  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000645b  test    rax, rax
0x14000645e  jnz     short loc_14000649C
0x140006460  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140006467  test    rax, rax
0x14000646a  jnz     short loc_140006480
0x14000646c  lea     rcx, ModuleName; "ntdll.dll"
0x140006473  call    cs:__imp_GetModuleHandleW
0x140006479  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140006480  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x140006487  mov     rcx, rax; hModule
0x14000648a  call    cs:__imp_GetProcAddress
0x140006490  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x140006497  test    rax, rax
0x14000649a  jz      short loc_1400064A2
0x14000649c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400064a1  nop
0x1400064a2  add     rsp, 28h
0x1400064a6  retn
```
