# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800085f0`
- end: `0x180008650`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `96`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800085f0`
- `0x18006a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000861c`
- `KERNEL32!GetModuleHandleW` at `0x18000861c`
- `KERNEL32!GetProcAddress` at `0x180008633`
- `KERNEL32!GetProcAddress` at `0x180008633`

## string_xrefs

- `0x180008615`: `ntdll.dll`
- `0x180008629`: `RtlDllShutdownInProgress`

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
0x1800085f0  sub     rsp, 38h
0x1800085f4  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800085fd  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180008604  test    rax, rax
0x180008607  jnz     short loc_180008645
0x180008609  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008610  test    rax, rax
0x180008613  jnz     short loc_180008629
0x180008615  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000861c  call    cs:__imp_GetModuleHandleW
0x180008622  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008629  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180008630  mov     rcx, rax; hModule
0x180008633  call    cs:__imp_GetProcAddress
0x180008639  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180008640  test    rax, rax
0x180008643  jz      short loc_18000864B
0x180008645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000864a  nop
0x18000864b  add     rsp, 38h
0x18000864f  retn
```
