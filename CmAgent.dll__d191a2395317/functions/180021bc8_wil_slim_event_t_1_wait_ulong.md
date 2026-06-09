# wil::slim_event_t<1>::wait(ulong)

- ea: `0x180021bc8`
- end: `0x180021d0d`
- name: `?wait@?$slim_event_t@$00@wil@@QEAA_NK@Z`
- size: `325`
- prototype: `__int64 __fastcall(volatile void *Address)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011ea4`

## callees

- `0x180003ce4`
- `0x180021bc8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x180021c0a`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x180021c73`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x180021c0a`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x180021c73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021cba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021cba`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180021c44`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180021c91`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180021c44`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180021c91`

## string_xrefs

- `0x180021ce4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180021cfb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
bool __fastcall wil::slim_event_t<1>::wait(int *Address, unsigned int a2)
{
  unsigned __int64 v2; // rdi
  const char *v5; // r9
  unsigned __int64 v6; // rdx
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int CompareAddress; // [rsp+38h] [rbp+10h] BYREF
  unsigned __int64 v10; // [rsp+40h] [rbp+18h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+48h] [rbp+20h] BYREF

  v2 = a2;
  if ( !a2 )
    return *Address != 0;
  if ( a2 == -1 )
  {
    while ( !*Address )
    {
      CompareAddress = 0;
      if ( !WaitOnAddress(Address, &CompareAddress, 4u, 0xFFFFFFFF) )
      {
        if ( GetLastError() != 1460 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xDBF,
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v5);
        return 0;
      }
    }
  }
  else
  {
    UnbiasedTime = 0;
    QueryUnbiasedInterruptTime(&UnbiasedTime);
    v6 = 0;
    while ( !*Address )
    {
      if ( v6 >= v2 )
        return 0;
      CompareAddress = *Address;
      if ( !WaitOnAddress(Address, &CompareAddress, 4u, v2 - v6) )
      {
        if ( GetLastError() != 1460 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xDBF,
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v7);
        return 0;
      }
      v10 = 0;
      QueryUnbiasedInterruptTime(&v10);
      v6 = (v10 - UnbiasedTime) / 0x2710;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180021bc8  mov     [rsp+arg_0], rbx
0x180021bcd  push    rdi
0x180021bce  sub     rsp, 20h
0x180021bd2  mov     edi, edx
0x180021bd4  mov     rbx, rcx
0x180021bd7  test    edx, edx
0x180021bd9  jnz     short loc_180021BE7
0x180021bdb  mov     eax, [rcx]
0x180021bdd  test    eax, eax
0x180021bdf  setnz   al
0x180021be2  jmp     loc_180021CD3
0x180021be7  cmp     edi, 0FFFFFFFFh
0x180021bea  jnz     short loc_180021C36
0x180021bec  mov     eax, [rbx]
0x180021bee  test    eax, eax
0x180021bf0  jnz     loc_180021CD1
0x180021bf6  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180021bfa  mov     [rsp+28h+CompareAddress], eax
0x180021bfe  lea     r8d, [rax+4]; AddressSize
0x180021c02  mov     rcx, rbx; Address
0x180021c05  lea     rdx, [rsp+28h+CompareAddress]; CompareAddress
0x180021c0a  call    cs:__imp_WaitOnAddress
0x180021c11  nop     dword ptr [rax+rax+00h]
0x180021c16  test    eax, eax
0x180021c18  jnz     short loc_180021BEC
0x180021c1a  call    cs:__imp_GetLastError
0x180021c21  nop     dword ptr [rax+rax+00h]
0x180021c26  cmp     eax, 5B4h
0x180021c2b  jnz     loc_180021CF6
0x180021c31  jmp     loc_180021CCD
0x180021c36  lea     rcx, [rsp+28h+UnbiasedTime]; UnbiasedTime
0x180021c3b  mov     [rsp+28h+UnbiasedTime], 0
0x180021c44  call    cs:__imp_QueryUnbiasedInterruptTime
0x180021c4b  nop     dword ptr [rax+rax+00h]
0x180021c50  xor     edx, edx
0x180021c52  mov     eax, [rbx]
0x180021c54  test    eax, eax
0x180021c56  jnz     short loc_180021CD1
0x180021c58  cmp     rdx, rdi
0x180021c5b  jnb     short loc_180021CCD
0x180021c5d  mov     r9d, edi
0x180021c60  mov     [rsp+28h+CompareAddress], eax
0x180021c64  sub     r9d, edx; dwMilliseconds
0x180021c67  lea     r8d, [rax+4]; AddressSize
0x180021c6b  lea     rdx, [rsp+28h+CompareAddress]; CompareAddress
0x180021c70  mov     rcx, rbx; Address
0x180021c73  call    cs:__imp_WaitOnAddress
0x180021c7a  nop     dword ptr [rax+rax+00h]
0x180021c7f  test    eax, eax
0x180021c81  jz      short loc_180021CBA
0x180021c83  lea     rcx, [rsp+28h+arg_10]; UnbiasedTime
0x180021c88  mov     [rsp+28h+arg_10], 0
0x180021c91  call    cs:__imp_QueryUnbiasedInterruptTime
0x180021c98  nop     dword ptr [rax+rax+00h]
0x180021c9d  mov     rcx, [rsp+28h+arg_10]
0x180021ca2  mov     rax, 346DC5D63886594Bh
0x180021cac  sub     rcx, [rsp+28h+UnbiasedTime]
0x180021cb1  mul     rcx
0x180021cb4  shr     rdx, 0Bh
0x180021cb8  jmp     short loc_180021C52
0x180021cba  call    cs:__imp_GetLastError
0x180021cc1  nop     dword ptr [rax+rax+00h]
0x180021cc6  cmp     eax, 5B4h
0x180021ccb  jnz     short loc_180021CDF
0x180021ccd  xor     al, al
0x180021ccf  jmp     short loc_180021CD3
0x180021cd1  mov     al, 1
0x180021cd3  mov     rbx, [rsp+28h+arg_0]
0x180021cd8  add     rsp, 20h
0x180021cdc  pop     rdi
0x180021cdd  retn
0x180021cdf  mov     rcx, [rsp+28h]; this
0x180021ce4  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021ceb  mov     edx, 0DBFh; void *
0x180021cf0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180021cf6  mov     rcx, [rsp+28h]; this
0x180021cfb  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021d02  mov     edx, 0DBFh; void *
0x180021d07  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
