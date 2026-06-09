# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18003faf0`
- end: `0x18003fb2c`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `60`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18003faf0`
- `0x18004088c`
- `0x1800b0010`

## string_xrefs

- `0x18003fb09`: `RtlDllShutdownInProgress`

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
0x18003faf0  sub     rsp, 38h
0x18003faf4  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18003fafd  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18003fb04  test    rax, rax
0x18003fb07  jnz     short loc_18003FB21
0x18003fb09  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18003fb10  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18003fb15  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18003fb1c  test    rax, rax
0x18003fb1f  jz      short loc_18003FB27
0x18003fb21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fb26  nop
0x18003fb27  add     rsp, 38h
0x18003fb2b  retn
```
