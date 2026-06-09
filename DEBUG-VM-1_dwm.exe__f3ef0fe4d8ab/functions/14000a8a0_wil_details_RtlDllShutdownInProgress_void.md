# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x14000a8a0`
- end: `0x14000a8d6`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `54`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x14000a8a0`
- `0x14000bcc4`
- `0x140010010`

## string_xrefs

- `0x14000a8b0`: `RtlDllShutdownInProgress`

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
0x14000a8a0  sub     rsp, 28h
0x14000a8a4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000a8ab  test    rax, rax
0x14000a8ae  jnz     short loc_14000A8CD
0x14000a8b0  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x14000a8b7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000a8bc  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x14000a8c3  test    rax, rax
0x14000a8c6  jnz     short loc_14000A8CD
0x14000a8c8  add     rsp, 28h
0x14000a8cc  retn
0x14000a8cd  add     rsp, 28h
0x14000a8d1  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
