# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140007c70`
- end: `0x140007ca6`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `54`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140007c70`
- `0x14000cf28`
- `0x140010010`

## string_xrefs

- `0x140007c80`: `RtlDllShutdownInProgress`

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
0x140007c70  sub     rsp, 28h
0x140007c74  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x140007c7b  test    rax, rax
0x140007c7e  jnz     short loc_140007C9D
0x140007c80  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x140007c87  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140007c8c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x140007c93  test    rax, rax
0x140007c96  jnz     short loc_140007C9D
0x140007c98  add     rsp, 28h
0x140007c9c  retn
0x140007c9d  add     rsp, 28h
0x140007ca1  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
