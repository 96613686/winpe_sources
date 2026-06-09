# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180026f10`
- end: `0x180026f6a`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180026f10`
- `0x18005d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180026f33`
- `KERNEL32!GetModuleHandleW` at `0x180026f33`
- `KERNEL32!GetProcAddress` at `0x180026f4a`
- `KERNEL32!GetProcAddress` at `0x180026f4a`

## string_xrefs

- `0x180026f2c`: `ntdll.dll`
- `0x180026f40`: `RtlDllShutdownInProgress`

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
0x180026f10  sub     rsp, 28h
0x180026f14  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180026f1b  test    rax, rax
0x180026f1e  jnz     short loc_180026F61
0x180026f20  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180026f27  test    rax, rax
0x180026f2a  jnz     short loc_180026F40
0x180026f2c  lea     rcx, aNtdllDll; "ntdll.dll"
0x180026f33  call    cs:__imp_GetModuleHandleW
0x180026f39  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180026f40  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180026f47  mov     rcx, rax; hModule
0x180026f4a  call    cs:__imp_GetProcAddress
0x180026f50  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180026f57  test    rax, rax
0x180026f5a  jnz     short loc_180026F61
0x180026f5c  add     rsp, 28h
0x180026f60  retn
0x180026f61  add     rsp, 28h
0x180026f65  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
