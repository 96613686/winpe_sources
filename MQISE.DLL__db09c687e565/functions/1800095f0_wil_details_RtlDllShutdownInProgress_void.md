# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800095f0`
- end: `0x180009648`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `88`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800095f0`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180009613`
- `KERNEL32!GetModuleHandleW` at `0x180009613`
- `KERNEL32!GetProcAddress` at `0x18000962a`
- `KERNEL32!GetProcAddress` at `0x18000962a`

## string_xrefs

- `0x18000960c`: `ntdll.dll`
- `0x180009620`: `RtlDllShutdownInProgress`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x1800095f0  sub     rsp, 28h
0x1800095f4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800095fb  test    rax, rax
0x1800095fe  jnz     short loc_18000963D
0x180009600  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009607  test    rax, rax
0x18000960a  jnz     short loc_180009620
0x18000960c  lea     rcx, ModuleName; "ntdll.dll"
0x180009613  call    cs:__imp_GetModuleHandleW
0x180009619  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009620  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180009627  mov     rcx, rax; hModule
0x18000962a  call    cs:__imp_GetProcAddress
0x180009630  nop
0x180009631  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180009638  test    rax, rax
0x18000963b  jz      short loc_180009643
0x18000963d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009642  nop
0x180009643  add     rsp, 28h
0x180009647  retn
```
