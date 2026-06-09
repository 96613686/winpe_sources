# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180006f50`
- end: `0x180006faf`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `95`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006f50`
- `0x180047a30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006f8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006f8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006f77`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006f77`

## string_xrefs

- `0x180006f70`: `ntdll.dll`
- `0x180006f84`: `RtlDllShutdownInProgress`

## pseudocode

```c
char __fastcall wil::details::RtlDllShutdownInProgress(wil::details *this)
{
  FARPROC ProcAddress; // rax
  char v2; // bl
  HMODULE ModuleHandleW; // rax

  ProcAddress = (FARPROC)`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  v2 = 0;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return ((__int64 (__fastcall *)(wil::details *))ProcAddress)(this);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlDllShutdownInProgress");
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (__int64)ProcAddress;
  if ( ProcAddress )
    return ((__int64 (__fastcall *)(wil::details *))ProcAddress)(this);
  return v2;
}

```

## disassembly

```asm
0x180006f50  push    rbx
0x180006f52  sub     rsp, 20h
0x180006f56  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180006f5d  xor     ebx, ebx
0x180006f5f  test    rax, rax
0x180006f62  jnz     short loc_180006FA0
0x180006f64  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006f6b  test    rax, rax
0x180006f6e  jnz     short loc_180006F84
0x180006f70  lea     rcx, ModuleName; "ntdll.dll"
0x180006f77  call    cs:__imp_GetModuleHandleW
0x180006f7d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006f84  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180006f8b  mov     rcx, rax; hModule
0x180006f8e  call    cs:__imp_GetProcAddress
0x180006f94  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180006f9b  test    rax, rax
0x180006f9e  jz      short loc_180006FA7
0x180006fa0  call    _guard_dispatch_icall
0x180006fa5  mov     bl, al
0x180006fa7  mov     al, bl
0x180006fa9  add     rsp, 20h
0x180006fad  pop     rbx
0x180006fae  retn
```
