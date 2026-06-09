# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x14000b1c0`
- end: `0x14000b217`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14000b1c0`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000b1e3`
- `KERNEL32!GetModuleHandleW` at `0x14000b1e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b1fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b1fa`

## string_xrefs

- `0x14000b1dc`: `ntdll.dll`
- `0x14000b1f0`: `RtlDllShutdownInProgress`

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
0x14000b1c0  sub     rsp, 28h
0x14000b1c4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000b1cb  test    rax, rax
0x14000b1ce  jnz     short loc_14000B20C
0x14000b1d0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b1d7  test    rax, rax
0x14000b1da  jnz     short loc_14000B1F0
0x14000b1dc  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000b1e3  call    cs:__imp_GetModuleHandleW
0x14000b1e9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b1f0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x14000b1f7  mov     rcx, rax; hModule
0x14000b1fa  call    cs:__imp_GetProcAddress
0x14000b200  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x14000b207  test    rax, rax
0x14000b20a  jz      short loc_14000B212
0x14000b20c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b211  nop
0x14000b212  add     rsp, 28h
0x14000b216  retn
```
