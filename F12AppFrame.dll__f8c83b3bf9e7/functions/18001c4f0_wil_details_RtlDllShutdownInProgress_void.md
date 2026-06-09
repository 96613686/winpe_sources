# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18001c4f0`
- end: `0x18001c547`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18001c4f0`
- `0x180035010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18001c52a`
- `KERNEL32!GetProcAddress` at `0x18001c52a`
- `KERNEL32!GetModuleHandleW` at `0x18001c513`
- `KERNEL32!GetModuleHandleW` at `0x18001c513`

## string_xrefs

- `0x18001c50c`: `ntdll.dll`
- `0x18001c520`: `RtlDllShutdownInProgress`

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
0x18001c4f0  sub     rsp, 28h
0x18001c4f4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18001c4fb  test    rax, rax
0x18001c4fe  jnz     short loc_18001C53C
0x18001c500  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001c507  test    rax, rax
0x18001c50a  jnz     short loc_18001C520
0x18001c50c  lea     rcx, aNtdllDll; "ntdll.dll"
0x18001c513  call    cs:__imp_GetModuleHandleW
0x18001c519  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001c520  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18001c527  mov     rcx, rax; hModule
0x18001c52a  call    cs:__imp_GetProcAddress
0x18001c530  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18001c537  test    rax, rax
0x18001c53a  jz      short loc_18001C542
0x18001c53c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c541  nop
0x18001c542  add     rsp, 28h
0x18001c546  retn
```
