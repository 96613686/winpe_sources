# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800157b0`
- end: `0x1800157ec`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `60`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800157b0`
- `0x180016490`
- `0x180025010`

## string_xrefs

- `0x1800157c9`: `RtlDllShutdownInProgress`

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
0x1800157b0  sub     rsp, 38h
0x1800157b4  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800157bd  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800157c4  test    rax, rax
0x1800157c7  jnz     short loc_1800157E1
0x1800157c9  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800157d0  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800157d5  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800157dc  test    rax, rax
0x1800157df  jz      short loc_1800157E7
0x1800157e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157e6  nop
0x1800157e7  add     rsp, 38h
0x1800157eb  retn
```
