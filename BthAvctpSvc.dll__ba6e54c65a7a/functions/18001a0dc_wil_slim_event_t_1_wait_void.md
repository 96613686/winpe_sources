# wil::slim_event_t<1>::wait(void)

- ea: `0x18001a0dc`
- end: `0x18001a142`
- name: `?wait@?$slim_event_t@$00@wil@@QEAA_NXZ`
- size: `102`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180019dd4`
- `0x18001f140`
- `0x180056bc4`

## callees

- `0x180004bd8`
- `0x180018eb8`
- `0x18001a0dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a112`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a112`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x18001a108`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x18001a108`

## string_xrefs

- `0x18001a128`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
char __fastcall wil::slim_event_t<1>::wait(__int64 a1)
{
  volatile void *v2; // rcx
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int CompareAddress; // [rsp+38h] [rbp+10h] BYREF

  do
  {
    if ( (unsigned __int8)wil::slim_event_t<1>::TryAcquireEvent(a1) )
      return 1;
    CompareAddress = 0;
  }
  while ( WaitOnAddress(v2, &CompareAddress, 4u, 0xFFFFFFFF) );
  if ( GetLastError() != 1460 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xDBF,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v3);
  return 0;
}

```

## disassembly

```asm
0x18001a0dc  push    rbx
0x18001a0de  sub     rsp, 20h
0x18001a0e2  mov     rbx, rcx
0x18001a0e5  mov     rcx, rbx
0x18001a0e8  call    ?TryAcquireEvent@?$slim_event_t@$00@wil@@AEAA_NXZ; wil::slim_event_t<1>::TryAcquireEvent(void)
0x18001a0ed  test    al, al
0x18001a0ef  jnz     short loc_18001A13A
0x18001a0f1  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001a0f5  mov     [rsp+28h+CompareAddress], 0
0x18001a0fd  mov     r8d, 4; AddressSize
0x18001a103  lea     rdx, [rsp+28h+CompareAddress]; CompareAddress
0x18001a108  call    cs:__imp_WaitOnAddress
0x18001a10e  test    eax, eax
0x18001a110  jnz     short loc_18001A0E5
0x18001a112  call    cs:__imp_GetLastError
0x18001a118  cmp     eax, 5B4h
0x18001a11d  jnz     short loc_18001A123
0x18001a11f  xor     al, al
0x18001a121  jmp     short loc_18001A13C
0x18001a123  mov     rcx, [rsp+28h]; this
0x18001a128  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001a12f  mov     edx, 0DBFh; void *
0x18001a134  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001a13a  mov     al, 1
0x18001a13c  add     rsp, 20h
0x18001a140  pop     rbx
0x18001a141  retn
```
