# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18001e770`
- end: `0x18001e7c7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18001e770`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001e793`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001e793`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e7aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e7aa`

## string_xrefs

- `0x18001e78c`: `ntdll.dll`
- `0x18001e7a0`: `RtlDllShutdownInProgress`

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
0x18001e770  sub     rsp, 28h
0x18001e774  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18001e77b  test    rax, rax
0x18001e77e  jnz     short loc_18001E7BC
0x18001e780  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001e787  test    rax, rax
0x18001e78a  jnz     short loc_18001E7A0
0x18001e78c  lea     rcx, LibFileName; "ntdll.dll"
0x18001e793  call    cs:__imp_GetModuleHandleW
0x18001e799  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001e7a0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18001e7a7  mov     rcx, rax; hModule
0x18001e7aa  call    cs:__imp_GetProcAddress
0x18001e7b0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18001e7b7  test    rax, rax
0x18001e7ba  jz      short loc_18001E7C2
0x18001e7bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7c1  nop
0x18001e7c2  add     rsp, 28h
0x18001e7c6  retn
```
