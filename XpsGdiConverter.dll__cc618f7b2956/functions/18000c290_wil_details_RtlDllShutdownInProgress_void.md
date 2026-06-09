# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000c290`
- end: `0x18000c2c3`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `51`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000c290`
- `0x18000d180`
- `0x18004a010`

## string_xrefs

- `0x18000c2a0`: `RtlDllShutdownInProgress`

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
0x18000c290  sub     rsp, 28h
0x18000c294  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000c29b  test    rax, rax
0x18000c29e  jnz     short loc_18000C2B8
0x18000c2a0  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000c2a7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000c2ac  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000c2b3  test    rax, rax
0x18000c2b6  jz      short loc_18000C2BE
0x18000c2b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2bd  nop
0x18000c2be  add     rsp, 28h
0x18000c2c2  retn
```
