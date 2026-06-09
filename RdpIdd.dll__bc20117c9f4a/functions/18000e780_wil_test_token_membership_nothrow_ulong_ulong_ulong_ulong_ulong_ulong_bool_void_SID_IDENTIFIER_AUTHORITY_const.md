# wil::test_token_membership_nothrow<ulong,ulong &,ulong &,ulong &,ulong &,ulong &>(bool *,void *,_SID_IDENTIFIER_AUTHORITY const &,ulong &&,ulong &,ulong &,ulong &,ulong &,ulong &)

- ea: `0x18000e780`
- end: `0x18000e844`
- name: `??$test_token_membership_nothrow@KAEAKAEAKAEAKAEAKAEAK@wil@@YAJPEA_NPEAXAEBU_SID_IDENTIFIER_AUTHORITY@@$$QEAKAEAK4444@Z`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800102b0`

## callees

- `0x180006f60`
- `0x18000aff4`
- `0x18000e780`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000e7fa`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000e7fa`

## string_xrefs

- `0x18000e80e`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::test_token_membership_nothrow<unsigned long,unsigned long &,unsigned long &,unsigned long &,unsigned long &,unsigned long &>(
        bool *a1,
        __int64 a2,
        int *a3,
        int *a4,
        int *a5,
        int *a6,
        int *a7,
        int *a8,
        int *a9)
{
  const char *v10; // r9
  WINBOOL IsMember; // [rsp+20h] [rbp-30h] BYREF
  __int16 SidToCheck; // [rsp+28h] [rbp-28h] BYREF
  int v14; // [rsp+2Ah] [rbp-26h]
  __int16 v15; // [rsp+2Eh] [rbp-22h]
  int v16; // [rsp+30h] [rbp-20h]
  int v17; // [rsp+34h] [rbp-1Ch]
  int v18; // [rsp+38h] [rbp-18h]
  int v19; // [rsp+3Ch] [rbp-14h]
  int v20; // [rsp+40h] [rbp-10h]
  int v21; // [rsp+44h] [rbp-Ch]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  *a1 = 0;
  v14 = *a3;
  v15 = *((_WORD *)a3 + 2);
  v16 = *a4;
  SidToCheck = 1537;
  IsMember = 0;
  v17 = *a5;
  v18 = *a6;
  v19 = *a7;
  v20 = *a8;
  v21 = *a9;
  if ( !CheckTokenMembership(0, &SidToCheck, &IsMember) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x27C,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
             v10);
  *a1 = IsMember != 0;
  return 0;
}

```

## disassembly

```asm
0x18000e780  mov     [rsp-8+arg_8], rbx
0x18000e785  push    rbp
0x18000e786  mov     rbp, rsp
0x18000e789  sub     rsp, 50h
0x18000e78d  mov     rax, cs:__security_cookie
0x18000e794  xor     rax, rsp
0x18000e797  mov     [rbp+var_8], rax
0x18000e79b  mov     byte ptr [rcx], 0
0x18000e79e  lea     rdx, [rbp+SidToCheck]; SidToCheck
0x18000e7a2  mov     eax, [r8]
0x18000e7a5  mov     rbx, rcx
0x18000e7a8  mov     [rbp+var_26], eax
0x18000e7ab  movzx   eax, word ptr [r8+4]
0x18000e7b0  lea     r8, [rbp+IsMember]; IsMember
0x18000e7b4  mov     [rbp+var_22], ax
0x18000e7b8  mov     eax, [r9]
0x18000e7bb  mov     [rbp+var_20], eax
0x18000e7be  mov     rax, [rbp+arg_20]
0x18000e7c2  mov     [rbp+SidToCheck], 601h
0x18000e7c8  mov     [rbp+IsMember], 0
0x18000e7cf  mov     ecx, [rax]
0x18000e7d1  mov     rax, [rbp+arg_28]
0x18000e7d5  mov     [rbp+var_1C], ecx
0x18000e7d8  mov     ecx, [rax]
0x18000e7da  mov     rax, [rbp+arg_30]
0x18000e7de  mov     [rbp+var_18], ecx
0x18000e7e1  mov     ecx, [rax]
0x18000e7e3  mov     rax, [rbp+arg_38]
0x18000e7e7  mov     [rbp+var_14], ecx
0x18000e7ea  mov     ecx, [rax]
0x18000e7ec  mov     rax, [rbp+arg_40]
0x18000e7f0  mov     [rbp+var_10], ecx
0x18000e7f3  mov     ecx, [rax]
0x18000e7f5  mov     [rbp+var_C], ecx
0x18000e7f8  xor     ecx, ecx; TokenHandle
0x18000e7fa  call    cs:__imp_CheckTokenMembership
0x18000e801  nop     dword ptr [rax+rax+00h]
0x18000e806  test    eax, eax
0x18000e808  jnz     short loc_18000E821
0x18000e80a  mov     rcx, [rbp+8]; this
0x18000e80e  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e815  mov     edx, 27Ch; void *
0x18000e81a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e81f  jmp     short loc_18000E82C
0x18000e821  cmp     [rbp+IsMember], 0
0x18000e825  setnz   al
0x18000e828  mov     [rbx], al
0x18000e82a  xor     eax, eax
0x18000e82c  mov     rcx, [rbp+var_8]
0x18000e830  xor     rcx, rsp; StackCookie
0x18000e833  call    __security_check_cookie
0x18000e838  mov     rbx, [rsp+50h+arg_8]
0x18000e83d  add     rsp, 50h
0x18000e841  pop     rbp
0x18000e842  retn
```
