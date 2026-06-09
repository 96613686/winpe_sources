# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000ab90`
- end: `0x18000abcc`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `60`
- prototype: `__int64 (*__fastcall(wil::details *this))(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000ab90`
- `0x18000bc78`
- `0x180015010`

## string_xrefs

- `0x18000aba9`: `RtlDllShutdownInProgress`

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
0x18000ab90  sub     rsp, 38h
0x18000ab94  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000ab9d  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000aba4  test    rax, rax
0x18000aba7  jnz     short loc_18000ABC1
0x18000aba9  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000abb0  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000abb5  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000abbc  test    rax, rax
0x18000abbf  jz      short loc_18000ABC7
0x18000abc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abc6  nop
0x18000abc7  add     rsp, 38h
0x18000abcb  retn
```
