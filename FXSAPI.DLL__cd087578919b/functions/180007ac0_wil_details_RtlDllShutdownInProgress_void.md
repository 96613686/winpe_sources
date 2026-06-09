# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180007ac0`
- end: `0x180007b24`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `100`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007ac0`
- `0x18003e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180007b00`
- `KERNEL32!GetProcAddress` at `0x180007b00`
- `KERNEL32!GetModuleHandleW` at `0x180007ae3`
- `KERNEL32!GetModuleHandleW` at `0x180007ae3`

## string_xrefs

- `0x180007adc`: `ntdll.dll`
- `0x180007af6`: `RtlDllShutdownInProgress`

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
0x180007ac0  sub     rsp, 28h
0x180007ac4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180007acb  test    rax, rax
0x180007ace  jnz     short loc_180007B18
0x180007ad0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007ad7  test    rax, rax
0x180007ada  jnz     short loc_180007AF6
0x180007adc  lea     rcx, ModuleName; "ntdll.dll"
0x180007ae3  call    cs:__imp_GetModuleHandleW
0x180007aea  nop     dword ptr [rax+rax+00h]
0x180007aef  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007af6  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180007afd  mov     rcx, rax; hModule
0x180007b00  call    cs:__imp_GetProcAddress
0x180007b07  nop     dword ptr [rax+rax+00h]
0x180007b0c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180007b13  test    rax, rax
0x180007b16  jz      short loc_180007B1E
0x180007b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b1d  nop
0x180007b1e  add     rsp, 28h
0x180007b22  retn
```
