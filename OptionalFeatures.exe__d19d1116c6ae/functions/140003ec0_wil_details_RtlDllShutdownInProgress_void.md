# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140003ec0`
- end: `0x140003f1a`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140003ec0`
- `0x140005010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140003efa`
- `KERNEL32!GetProcAddress` at `0x140003efa`
- `KERNEL32!GetModuleHandleW` at `0x140003ee3`
- `KERNEL32!GetModuleHandleW` at `0x140003ee3`

## string_xrefs

- `0x140003edc`: `ntdll.dll`
- `0x140003ef0`: `RtlDllShutdownInProgress`

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
0x140003ec0  sub     rsp, 28h
0x140003ec4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x140003ecb  test    rax, rax
0x140003ece  jnz     short loc_140003F11
0x140003ed0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140003ed7  test    rax, rax
0x140003eda  jnz     short loc_140003EF0
0x140003edc  lea     rcx, ModuleName; "ntdll.dll"
0x140003ee3  call    cs:__imp_GetModuleHandleW
0x140003ee9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140003ef0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x140003ef7  mov     rcx, rax; hModule
0x140003efa  call    cs:__imp_GetProcAddress
0x140003f00  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x140003f07  test    rax, rax
0x140003f0a  jnz     short loc_140003F11
0x140003f0c  add     rsp, 28h
0x140003f10  retn
0x140003f11  add     rsp, 28h
0x140003f15  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
