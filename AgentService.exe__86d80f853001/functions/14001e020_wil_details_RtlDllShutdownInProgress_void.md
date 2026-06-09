# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x14001e020`
- end: `0x14001e077`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14001e020`
- `0x14009b010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14001e043`
- `KERNEL32!GetModuleHandleW` at `0x14001e043`
- `KERNEL32!GetProcAddress` at `0x14001e05a`
- `KERNEL32!GetProcAddress` at `0x14001e05a`

## string_xrefs

- `0x14001e03c`: `ntdll.dll`
- `0x14001e050`: `RtlDllShutdownInProgress`

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
0x14001e020  sub     rsp, 28h
0x14001e024  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14001e02b  test    rax, rax
0x14001e02e  jnz     short loc_14001E06C
0x14001e030  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001e037  test    rax, rax
0x14001e03a  jnz     short loc_14001E050
0x14001e03c  lea     rcx, aNtdllDll; "ntdll.dll"
0x14001e043  call    cs:__imp_GetModuleHandleW
0x14001e049  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001e050  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x14001e057  mov     rcx, rax; hModule
0x14001e05a  call    cs:__imp_GetProcAddress
0x14001e060  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x14001e067  test    rax, rax
0x14001e06a  jz      short loc_14001E072
0x14001e06c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e071  nop
0x14001e072  add     rsp, 28h
0x14001e076  retn
```
