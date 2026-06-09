# wil::operation_guard::close_and_wait(void)

- ea: `0x18001b680`
- end: `0x18001b6f1`
- name: `?close_and_wait@operation_guard@wil@@QEAAXXZ`
- size: `113`
- prototype: `void __fastcall(wil::operation_guard *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013df8`
- `0x180014550`

## callees

- `0x18000b68c`
- `0x18001aed4`
- `0x18001b680`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x18001b6bd`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x18001b6bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b6c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b6c7`

## string_xrefs

- `0x18001b6d9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::operation_guard::close_and_wait(wil::operation_guard *this)
{
  volatile void *v2; // rcx
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int CompareAddress; // [rsp+30h] [rbp+8h] BYREF

  *((_BYTE *)this + 8) = 1;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 1, 0xFFFFFFFF) > 1 )
  {
    while ( !(unsigned __int8)wil::slim_event_t<1>::TryAcquireEvent(this) )
    {
      CompareAddress = 0;
      if ( !WaitOnAddress(v2, &CompareAddress, 4u, 0xFFFFFFFF) )
      {
        if ( GetLastError() != 1460 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xDBF,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v3);
        return;
      }
    }
  }
}

```

## disassembly

```asm
0x18001b680  push    rbx
0x18001b682  sub     rsp, 20h
0x18001b686  mov     rbx, rcx
0x18001b689  mov     byte ptr [rcx+8], 1
0x18001b68d  or      eax, 0FFFFFFFFh
0x18001b690  lock xadd [rcx+4], eax
0x18001b695  sub     eax, 1
0x18001b698  jle     short loc_18001B6EB
0x18001b69a  mov     rcx, rbx
0x18001b69d  call    ?TryAcquireEvent@?$slim_event_t@$00@wil@@AEAA_NXZ; wil::slim_event_t<1>::TryAcquireEvent(void)
0x18001b6a2  test    al, al
0x18001b6a4  jnz     short loc_18001B6EB
0x18001b6a6  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001b6aa  mov     [rsp+28h+CompareAddress], 0
0x18001b6b2  mov     r8d, 4; AddressSize
0x18001b6b8  lea     rdx, [rsp+28h+CompareAddress]; CompareAddress
0x18001b6bd  call    cs:__imp_WaitOnAddress
0x18001b6c3  test    eax, eax
0x18001b6c5  jnz     short loc_18001B69A
0x18001b6c7  call    cs:__imp_GetLastError
0x18001b6cd  cmp     eax, 5B4h
0x18001b6d2  jz      short loc_18001B6EB
0x18001b6d4  mov     rcx, [rsp+28h]; this
0x18001b6d9  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001b6e0  mov     edx, 0DBFh; void *
0x18001b6e5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001b6eb  add     rsp, 20h
0x18001b6ef  pop     rbx
0x18001b6f0  retn
```
