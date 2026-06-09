# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180005b50`
- end: `0x180005bb7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `103`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180005b50`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180005b73`
- `KERNEL32!GetModuleHandleW` at `0x180005b73`
- `KERNEL32!GetProcAddress` at `0x180005b90`
- `KERNEL32!GetProcAddress` at `0x180005b90`

## string_xrefs

- `0x180005b6c`: `ntdll.dll`
- `0x180005b86`: `RtlDllShutdownInProgress`

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
0x180005b50  sub     rsp, 28h
0x180005b54  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180005b5b  test    rax, rax
0x180005b5e  jnz     short loc_180005BAE
0x180005b60  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005b67  test    rax, rax
0x180005b6a  jnz     short loc_180005B86
0x180005b6c  lea     rcx, ModuleName; "ntdll.dll"
0x180005b73  call    cs:__imp_GetModuleHandleW
0x180005b7a  nop     dword ptr [rax+rax+00h]
0x180005b7f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005b86  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180005b8d  mov     rcx, rax; hModule
0x180005b90  call    cs:__imp_GetProcAddress
0x180005b97  nop     dword ptr [rax+rax+00h]
0x180005b9c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180005ba3  test    rax, rax
0x180005ba6  jnz     short loc_180005BAE
0x180005ba8  add     rsp, 28h
0x180005bac  retn
0x180005bae  add     rsp, 28h
0x180005bb2  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
