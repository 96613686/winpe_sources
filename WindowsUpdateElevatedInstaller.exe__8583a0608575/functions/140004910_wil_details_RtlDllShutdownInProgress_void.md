# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140004910`
- end: `0x140004967`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140004910`
- `0x140008010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000494a`
- `KERNEL32!GetProcAddress` at `0x14000494a`
- `KERNEL32!GetModuleHandleW` at `0x140004933`
- `KERNEL32!GetModuleHandleW` at `0x140004933`

## string_xrefs

- `0x14000492c`: `ntdll.dll`
- `0x140004940`: `RtlDllShutdownInProgress`

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
0x140004910  sub     rsp, 28h
0x140004914  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000491b  test    rax, rax
0x14000491e  jnz     short loc_14000495C
0x140004920  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004927  test    rax, rax
0x14000492a  jnz     short loc_140004940
0x14000492c  lea     rcx, ModuleName; "ntdll.dll"
0x140004933  call    cs:__imp_GetModuleHandleW
0x140004939  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004940  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x140004947  mov     rcx, rax; hModule
0x14000494a  call    cs:__imp_GetProcAddress
0x140004950  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x140004957  test    rax, rax
0x14000495a  jz      short loc_140004962
0x14000495c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004961  nop
0x140004962  add     rsp, 28h
0x140004966  retn
```
