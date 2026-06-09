# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180016fa0`
- end: `0x180016fd6`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `54`
- prototype: `__int64 (*__fastcall(wil::details *this))(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18001307c`
- `0x180016fa0`
- `0x18001c010`

## string_xrefs

- `0x180016fb0`: `RtlDllShutdownInProgress`

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
0x180016fa0  sub     rsp, 28h
0x180016fa4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180016fab  test    rax, rax
0x180016fae  jnz     short loc_180016FCD
0x180016fb0  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180016fb7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180016fbc  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180016fc3  test    rax, rax
0x180016fc6  jnz     short loc_180016FCD
0x180016fc8  add     rsp, 28h
0x180016fcc  retn
0x180016fcd  add     rsp, 28h
0x180016fd1  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
