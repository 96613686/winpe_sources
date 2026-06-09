# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180014690`
- end: `0x1800146e8`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `88`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180014690`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800146b3`
- `KERNEL32!GetModuleHandleW` at `0x1800146b3`
- `KERNEL32!GetProcAddress` at `0x1800146ca`
- `KERNEL32!GetProcAddress` at `0x1800146ca`

## string_xrefs

- `0x1800146ac`: `ntdll.dll`
- `0x1800146c0`: `RtlDllShutdownInProgress`

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
0x180014690  sub     rsp, 28h
0x180014694  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18001469b  test    rax, rax
0x18001469e  jnz     short loc_1800146DD
0x1800146a0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800146a7  test    rax, rax
0x1800146aa  jnz     short loc_1800146C0
0x1800146ac  lea     rcx, ModuleName; "ntdll.dll"
0x1800146b3  call    cs:__imp_GetModuleHandleW
0x1800146b9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800146c0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800146c7  mov     rcx, rax; hModule
0x1800146ca  call    cs:__imp_GetProcAddress
0x1800146d0  nop
0x1800146d1  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800146d8  test    rax, rax
0x1800146db  jz      short loc_1800146E3
0x1800146dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146e2  nop
0x1800146e3  add     rsp, 28h
0x1800146e7  retn
```
