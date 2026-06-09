# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1400056d0`
- end: `0x140005703`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `51`
- prototype: `__int64 (*__fastcall(wil::details *this))(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1400056d0`
- `0x140006bd0`
- `0x14001c010`

## string_xrefs

- `0x1400056e0`: `RtlDllShutdownInProgress`

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
0x1400056d0  sub     rsp, 28h
0x1400056d4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1400056db  test    rax, rax
0x1400056de  jnz     short loc_1400056F8
0x1400056e0  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1400056e7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1400056ec  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1400056f3  test    rax, rax
0x1400056f6  jz      short loc_1400056FE
0x1400056f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400056fd  nop
0x1400056fe  add     rsp, 28h
0x140005702  retn
```
