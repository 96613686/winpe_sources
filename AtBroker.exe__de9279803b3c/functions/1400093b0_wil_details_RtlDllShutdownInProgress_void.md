# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1400093b0`
- end: `0x14000940a`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1400093b0`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400093ea`
- `KERNEL32!GetProcAddress` at `0x1400093ea`
- `KERNEL32!GetModuleHandleW` at `0x1400093d3`
- `KERNEL32!GetModuleHandleW` at `0x1400093d3`

## string_xrefs

- `0x1400093cc`: `ntdll.dll`
- `0x1400093e0`: `RtlDllShutdownInProgress`

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
0x1400093b0  sub     rsp, 28h
0x1400093b4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1400093bb  test    rax, rax
0x1400093be  jnz     short loc_140009401
0x1400093c0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400093c7  test    rax, rax
0x1400093ca  jnz     short loc_1400093E0
0x1400093cc  lea     rcx, ModuleName; "ntdll.dll"
0x1400093d3  call    cs:__imp_GetModuleHandleW
0x1400093d9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400093e0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1400093e7  mov     rcx, rax; hModule
0x1400093ea  call    cs:__imp_GetProcAddress
0x1400093f0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1400093f7  test    rax, rax
0x1400093fa  jnz     short loc_140009401
0x1400093fc  add     rsp, 28h
0x140009400  retn
0x140009401  add     rsp, 28h
0x140009405  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
