# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180027d00`
- end: `0x180027d67`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `103`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180027d00`
- `0x18005f010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180027d23`
- `KERNEL32!GetModuleHandleW` at `0x180027d23`
- `KERNEL32!GetProcAddress` at `0x180027d40`
- `KERNEL32!GetProcAddress` at `0x180027d40`

## string_xrefs

- `0x180027d1c`: `ntdll.dll`
- `0x180027d36`: `RtlDllShutdownInProgress`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil::details::RtlDllShutdownInProgress(wil::details *this))(wil::details *)
{
  __int64 (__fastcall *result)(wil::details *); // rax
  HMODULE ModuleHandleW; // rax

  result = (__int64 (__fastcall *)(wil::details *))`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return (__int64 (__fastcall *)(wil::details *))result(this);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  result = (__int64 (__fastcall *)(wil::details *))GetProcAddress(ModuleHandleW, "RtlDllShutdownInProgress");
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (__int64)result;
  if ( result )
    return (__int64 (__fastcall *)(wil::details *))result(this);
  return result;
}

```

## disassembly

```asm
0x180027d00  sub     rsp, 28h
0x180027d04  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180027d0b  test    rax, rax
0x180027d0e  jnz     short loc_180027D5E
0x180027d10  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180027d17  test    rax, rax
0x180027d1a  jnz     short loc_180027D36
0x180027d1c  lea     rcx, aNtdllDll; "ntdll.dll"
0x180027d23  call    cs:__imp_GetModuleHandleW
0x180027d2a  nop     dword ptr [rax+rax+00h]
0x180027d2f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180027d36  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180027d3d  mov     rcx, rax; hModule
0x180027d40  call    cs:__imp_GetProcAddress
0x180027d47  nop     dword ptr [rax+rax+00h]
0x180027d4c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180027d53  test    rax, rax
0x180027d56  jnz     short loc_180027D5E
0x180027d58  add     rsp, 28h
0x180027d5c  retn
0x180027d5e  add     rsp, 28h
0x180027d62  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
