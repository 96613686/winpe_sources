# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180011490`
- end: `0x1800114c3`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `51`
- prototype: `__int64 (*__fastcall(wil::details *this))(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000dc44`
- `0x180011490`
- `0x18001b010`

## string_xrefs

- `0x1800114a0`: `RtlDllShutdownInProgress`

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
0x180011490  sub     rsp, 28h
0x180011494  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18001149b  test    rax, rax
0x18001149e  jnz     short loc_1800114B8
0x1800114a0  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800114a7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800114ac  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800114b3  test    rax, rax
0x1800114b6  jz      short loc_1800114BE
0x1800114b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114bd  nop
0x1800114be  add     rsp, 28h
0x1800114c2  retn
```
