# wil::test_token_membership_nothrow<ulong>(bool *,void *,_SID_IDENTIFIER_AUTHORITY const &,ulong &&)

- ea: `0x18009b060`
- end: `0x18009b0ef`
- name: `??$test_token_membership_nothrow@K@wil@@YAJPEA_NPEAXAEBU_SID_IDENTIFIER_AUTHORITY@@$$QEAK@Z`
- size: `143`
- prototype: `__int64 __fastcall(bool *, __int64, int *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009dba0`

## callees

- `0x180005860`
- `0x18000deac`
- `0x18009b060`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18009b0ae`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18009b0ae`

## string_xrefs

- `0x18009b0bd`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall wil::test_token_membership_nothrow<unsigned long>(bool *a1, __int64 a2, int *a3, int *a4)
{
  const char *v5; // r9
  WINBOOL IsMember; // [rsp+20h] [rbp-28h] BYREF
  __int16 SidToCheck; // [rsp+28h] [rbp-20h] BYREF
  int v9; // [rsp+2Ah] [rbp-1Eh]
  __int16 v10; // [rsp+2Eh] [rbp-1Ah]
  int v11; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  v9 = *a3;
  v10 = *((_WORD *)a3 + 2);
  v11 = *a4;
  SidToCheck = 257;
  IsMember = 0;
  if ( !CheckTokenMembership(0, &SidToCheck, &IsMember) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x27C,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
             v5);
  *a1 = IsMember != 0;
  return 0;
}

```

## disassembly

```asm
0x18009b060  push    rbx
0x18009b062  sub     rsp, 40h
0x18009b066  mov     rax, cs:__security_cookie
0x18009b06d  xor     rax, rsp
0x18009b070  mov     [rsp+48h+var_10], rax
0x18009b075  mov     byte ptr [rcx], 0
0x18009b078  lea     rdx, [rsp+48h+SidToCheck]; SidToCheck
0x18009b07d  mov     eax, [r8]
0x18009b080  mov     rbx, rcx
0x18009b083  mov     [rsp+48h+var_1E], eax
0x18009b087  xor     ecx, ecx; TokenHandle
0x18009b089  movzx   eax, word ptr [r8+4]
0x18009b08e  lea     r8, [rsp+48h+IsMember]; IsMember
0x18009b093  mov     [rsp+48h+var_1A], ax
0x18009b098  mov     eax, [r9]
0x18009b09b  mov     [rsp+48h+var_18], eax
0x18009b09f  mov     [rsp+48h+SidToCheck], 101h
0x18009b0a6  mov     [rsp+48h+IsMember], 0
0x18009b0ae  call    cs:__imp_CheckTokenMembership
0x18009b0b4  test    eax, eax
0x18009b0b6  jnz     short loc_18009B0D0
0x18009b0b8  mov     rcx, [rsp+48h]; this
0x18009b0bd  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18009b0c4  mov     edx, 27Ch; void *
0x18009b0c9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009b0ce  jmp     short loc_18009B0DC
0x18009b0d0  cmp     [rsp+48h+IsMember], 0
0x18009b0d5  setnz   al
0x18009b0d8  mov     [rbx], al
0x18009b0da  xor     eax, eax
0x18009b0dc  mov     rcx, [rsp+48h+var_10]
0x18009b0e1  xor     rcx, rsp; StackCookie
0x18009b0e4  call    __security_check_cookie
0x18009b0e9  add     rsp, 40h
0x18009b0ed  pop     rbx
0x18009b0ee  retn
```
