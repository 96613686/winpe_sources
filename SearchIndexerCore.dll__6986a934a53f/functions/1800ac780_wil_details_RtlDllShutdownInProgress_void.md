# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800ac780`
- end: `0x1800ac7b3`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `51`
- prototype: `__int64 (*__fastcall(wil::details *this))(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800ac780`
- `0x1800ae300`
- `0x1800b0010`

## string_xrefs

- `0x1800ac790`: `RtlDllShutdownInProgress`

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
0x1800ac780  sub     rsp, 28h
0x1800ac784  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800ac78b  test    rax, rax
0x1800ac78e  jnz     short loc_1800AC7A8
0x1800ac790  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800ac797  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800ac79c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800ac7a3  test    rax, rax
0x1800ac7a6  jz      short loc_1800AC7AE
0x1800ac7a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac7ad  nop
0x1800ac7ae  add     rsp, 28h
0x1800ac7b2  retn
```
