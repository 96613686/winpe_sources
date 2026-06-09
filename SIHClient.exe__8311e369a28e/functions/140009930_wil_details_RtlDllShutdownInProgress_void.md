# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140009930`
- end: `0x14000998f`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `95`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140009930`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000996e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000996e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009957`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009957`

## string_xrefs

- `0x140009950`: `ntdll.dll`
- `0x140009964`: `RtlDllShutdownInProgress`

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
0x140009930  push    rbx
0x140009932  sub     rsp, 20h
0x140009936  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000993d  xor     ebx, ebx
0x14000993f  test    rax, rax
0x140009942  jnz     short loc_140009980
0x140009944  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000994b  test    rax, rax
0x14000994e  jnz     short loc_140009964
0x140009950  lea     rcx, ModuleName; "ntdll.dll"
0x140009957  call    cs:__imp_GetModuleHandleW
0x14000995d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009964  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x14000996b  mov     rcx, rax; hModule
0x14000996e  call    cs:__imp_GetProcAddress
0x140009974  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x14000997b  test    rax, rax
0x14000997e  jz      short loc_140009987
0x140009980  call    _guard_dispatch_icall
0x140009985  mov     bl, al
0x140009987  mov     al, bl
0x140009989  add     rsp, 20h
0x14000998d  pop     rbx
0x14000998e  retn
```
