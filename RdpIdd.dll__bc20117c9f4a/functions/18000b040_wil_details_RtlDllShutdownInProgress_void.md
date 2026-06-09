# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000b040`
- end: `0x18000b074`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `52`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000b040`
- `0x18000c6dc`
- `0x18003f010`

## string_xrefs

- `0x18000b050`: `RtlDllShutdownInProgress`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlDllShutdownInProgress(wil::details *this)
{
  FARPROC result; // rax

  result = (FARPROC)`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  result = wil_details_GetNtDllProcedureAddress("RtlDllShutdownInProgress");
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  return result;
}

```

## disassembly

```asm
0x18000b040  sub     rsp, 28h
0x18000b044  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000b04b  test    rax, rax
0x18000b04e  jnz     short loc_18000B068
0x18000b050  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000b057  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b05c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000b063  test    rax, rax
0x18000b066  jz      short loc_18000B06E
0x18000b068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b06d  nop
0x18000b06e  add     rsp, 28h
0x18000b072  retn
```
