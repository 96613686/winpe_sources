# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1400056e0`
- end: `0x14000571c`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `60`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1400056e0`
- `0x1400066b0`
- `0x14002a010`

## string_xrefs

- `0x1400056f9`: `RtlDllShutdownInProgress`

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
0x1400056e0  sub     rsp, 38h
0x1400056e4  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1400056ed  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1400056f4  test    rax, rax
0x1400056f7  jnz     short loc_140005711
0x1400056f9  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x140005700  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140005705  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x14000570c  test    rax, rax
0x14000570f  jz      short loc_140005717
0x140005711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005716  nop
0x140005717  add     rsp, 38h
0x14000571b  retn
```
