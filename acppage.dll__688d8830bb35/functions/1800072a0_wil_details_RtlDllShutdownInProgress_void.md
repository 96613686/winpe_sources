# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800072a0`
- end: `0x1800072fa`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800072a0`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800072c3`
- `KERNEL32!GetModuleHandleW` at `0x1800072c3`
- `KERNEL32!GetProcAddress` at `0x1800072da`
- `KERNEL32!GetProcAddress` at `0x1800072da`

## string_xrefs

- `0x1800072bc`: `ntdll.dll`
- `0x1800072d0`: `RtlDllShutdownInProgress`

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
0x1800072a0  sub     rsp, 28h
0x1800072a4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800072ab  test    rax, rax
0x1800072ae  jnz     short loc_1800072F1
0x1800072b0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800072b7  test    rax, rax
0x1800072ba  jnz     short loc_1800072D0
0x1800072bc  lea     rcx, ModuleName; "ntdll.dll"
0x1800072c3  call    cs:__imp_GetModuleHandleW
0x1800072c9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800072d0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800072d7  mov     rcx, rax; hModule
0x1800072da  call    cs:__imp_GetProcAddress
0x1800072e0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800072e7  test    rax, rax
0x1800072ea  jnz     short loc_1800072F1
0x1800072ec  add     rsp, 28h
0x1800072f0  retn
0x1800072f1  add     rsp, 28h
0x1800072f5  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
