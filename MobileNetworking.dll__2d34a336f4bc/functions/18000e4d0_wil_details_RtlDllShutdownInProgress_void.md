# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000e4d0`
- end: `0x18000e503`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `51`
- prototype: `__int64 (*__fastcall(wil::details *this))(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000e4d0`
- `0x18000e678`
- `0x180012010`

## string_xrefs

- `0x18000e4e0`: `RtlDllShutdownInProgress`

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
0x18000e4d0  sub     rsp, 28h
0x18000e4d4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000e4db  test    rax, rax
0x18000e4de  jnz     short loc_18000E4F8
0x18000e4e0  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000e4e7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000e4ec  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000e4f3  test    rax, rax
0x18000e4f6  jz      short loc_18000E4FE
0x18000e4f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4fd  nop
0x18000e4fe  add     rsp, 28h
0x18000e502  retn
```
