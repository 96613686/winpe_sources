# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000b8e0`
- end: `0x18000b913`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `51`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000b8e0`
- `0x18000d170`
- `0x18001f010`

## string_xrefs

- `0x18000b8f0`: `RtlDllShutdownInProgress`

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
0x18000b8e0  sub     rsp, 28h
0x18000b8e4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000b8eb  test    rax, rax
0x18000b8ee  jnz     short loc_18000B908
0x18000b8f0  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000b8f7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b8fc  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000b903  test    rax, rax
0x18000b906  jz      short loc_18000B90E
0x18000b908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b90d  nop
0x18000b90e  add     rsp, 28h
0x18000b912  retn
```
