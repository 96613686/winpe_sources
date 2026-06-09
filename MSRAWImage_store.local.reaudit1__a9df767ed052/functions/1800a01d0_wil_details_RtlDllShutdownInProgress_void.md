# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800a01d0`
- end: `0x1800a0215`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `69`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800a01d0`
- `0x1800a0e5c`
- `0x1800b4010`

## string_xrefs

- `0x1800a01ed`: `RtlDllShutdownInProgress`

## pseudocode

```c
char __fastcall wil::details::RtlDllShutdownInProgress(wil::details *this)
{
  __int64 (*NtDllProcedureAddress)(void); // rax
  char v2; // bl

  NtDllProcedureAddress = (__int64 (*)(void))`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  v2 = 0;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return ((__int64 (__fastcall *)(wil::details *))NtDllProcedureAddress)(this);
  NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlDllShutdownInProgress");
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (__int64)NtDllProcedureAddress;
  if ( NtDllProcedureAddress )
    return ((__int64 (__fastcall *)(wil::details *))NtDllProcedureAddress)(this);
  return v2;
}

```

## disassembly

```asm
0x1800a01d0  push    rbx
0x1800a01d2  sub     rsp, 30h
0x1800a01d6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800a01df  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800a01e6  xor     ebx, ebx
0x1800a01e8  test    rax, rax
0x1800a01eb  jnz     short loc_1800A0205
0x1800a01ed  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800a01f4  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800a01f9  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800a0200  test    rax, rax
0x1800a0203  jz      short loc_1800A020C
0x1800a0205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a020a  mov     bl, al
0x1800a020c  mov     al, bl
0x1800a020e  add     rsp, 30h
0x1800a0212  pop     rbx
0x1800a0213  retn
```
