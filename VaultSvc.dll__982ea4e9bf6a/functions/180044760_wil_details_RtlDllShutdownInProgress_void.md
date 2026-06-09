# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180044760`
- end: `0x180044793`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `51`
- prototype: `__int64 (*__fastcall(wil::details *this))(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180044760`
- `0x180045b28`
- `0x18004d010`

## string_xrefs

- `0x180044770`: `RtlDllShutdownInProgress`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180044760  sub     rsp, 28h
0x180044764  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18004476b  test    rax, rax
0x18004476e  jnz     short loc_180044788
0x180044770  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180044777  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18004477c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180044783  test    rax, rax
0x180044786  jz      short loc_18004478E
0x180044788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004478d  nop
0x18004478e  add     rsp, 28h
0x180044792  retn
```
