# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x14000bf00`
- end: `0x14000bf33`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `51`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140002d0c`
- `0x14000bf00`
- `0x14003a010`

## string_xrefs

- `0x14000bf10`: `RtlDllShutdownInProgress`

## pseudocode

```c
__int64 (*__fastcall wil::details::RtlDllShutdownInProgress(wil::details *this))(void)
{
  __int64 (*result)(void); // rax

  result = (__int64 (*)(void))`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return (__int64 (*)(void))((__int64 (__fastcall *)(wil::details *))result)(this);
  result = wil_details_GetNtDllProcedureAddress("RtlDllShutdownInProgress");
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (__int64)result;
  if ( result )
    return (__int64 (*)(void))((__int64 (__fastcall *)(wil::details *))result)(this);
  return result;
}

```

## disassembly

```asm
0x14000bf00  sub     rsp, 28h
0x14000bf04  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000bf0b  test    rax, rax
0x14000bf0e  jnz     short loc_14000BF28
0x14000bf10  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x14000bf17  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000bf1c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x14000bf23  test    rax, rax
0x14000bf26  jz      short loc_14000BF2E
0x14000bf28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bf2d  nop
0x14000bf2e  add     rsp, 28h
0x14000bf32  retn
```
