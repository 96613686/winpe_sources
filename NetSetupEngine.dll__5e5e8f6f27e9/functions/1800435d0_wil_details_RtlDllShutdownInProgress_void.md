# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800435d0`
- end: `0x180043615`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `69`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800435d0`
- `0x18004361c`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800435f8`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800435f8`

## string_xrefs

- `0x1800435f1`: `RtlDllShutdownInProgress`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlDllShutdownInProgress(wil::details *this)
{
  FARPROC result; // rax
  HMODULE NtDllModuleHandle; // rax

  result = (FARPROC)`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  NtDllModuleHandle = wil_details_GetNtDllModuleHandle();
  result = GetProcAddress(NtDllModuleHandle, "RtlDllShutdownInProgress");
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  return result;
}

```

## disassembly

```asm
0x1800435d0  sub     rsp, 38h
0x1800435d4  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800435dd  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800435e4  test    rax, rax
0x1800435e7  jnz     short loc_18004360A
0x1800435e9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1800435ee  mov     rcx, rax; hModule
0x1800435f1  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800435f8  call    cs:__imp_GetProcAddress
0x1800435fe  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180043605  test    rax, rax
0x180043608  jz      short loc_180043610
0x18004360a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004360f  nop
0x180043610  add     rsp, 38h
0x180043614  retn
```
