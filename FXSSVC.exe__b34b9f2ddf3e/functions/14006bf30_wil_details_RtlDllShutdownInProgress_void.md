# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x14006bf30`
- end: `0x14006bf87`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14006bf30`
- `0x140085010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14006bf6a`
- `KERNEL32!GetProcAddress` at `0x14006bf6a`
- `KERNEL32!GetModuleHandleW` at `0x14006bf53`
- `KERNEL32!GetModuleHandleW` at `0x14006bf53`

## string_xrefs

- `0x14006bf4c`: `ntdll.dll`
- `0x14006bf60`: `RtlDllShutdownInProgress`

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
0x14006bf30  sub     rsp, 28h
0x14006bf34  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14006bf3b  test    rax, rax
0x14006bf3e  jnz     short loc_14006BF7C
0x14006bf40  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14006bf47  test    rax, rax
0x14006bf4a  jnz     short loc_14006BF60
0x14006bf4c  lea     rcx, ModuleName; "ntdll.dll"
0x14006bf53  call    cs:__imp_GetModuleHandleW
0x14006bf59  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14006bf60  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x14006bf67  mov     rcx, rax; hModule
0x14006bf6a  call    cs:__imp_GetProcAddress
0x14006bf70  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x14006bf77  test    rax, rax
0x14006bf7a  jz      short loc_14006BF82
0x14006bf7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006bf81  nop
0x14006bf82  add     rsp, 28h
0x14006bf86  retn
```
