# KdcInsertDomainTrustIntoForest(_LIST_ENTRY *,_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *)

- ea: `0x180058f64`
- end: `0x180059150`
- name: `?KdcInsertDomainTrustIntoForest@@YAJPEAU_LIST_ENTRY@@PEAU_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX@@@Z`
- size: `492`
- prototype: `__int64 __fastcall(struct _LIST_ENTRY *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005718c`

## callees

- `0x180003908`
- `0x180010718`
- `0x1800107dc`
- `0x18001ff94`
- `0x180057068`
- `0x180058f64`
- `0x180059158`
- `0x18005970c`
- `0x18005a060`
- `0x18007c4d4`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800590ef`
- `ntdll!RtlLengthSid` at `0x1800590ef`
- `ntdll!RtlInitializeCriticalSection` at `0x180059016`
- `ntdll!RtlInitializeCriticalSection` at `0x180059016`
- `ntdll!RtlCopySid` at `0x18005911a`
- `ntdll!RtlCopySid` at `0x18005911a`
- `ntdll!RtlUpcaseUnicodeString` at `0x18005906a`
- `ntdll!RtlUpcaseUnicodeString` at `0x18005906a`

## pseudocode

```c
__int64 __fastcall KdcInsertDomainTrustIntoForest(struct _LIST_ENTRY *a1, struct _UNICODE_STRING *a2)
{
  __int64 v4; // rax
  struct _KDC_DOMAIN_INFO *v5; // rbx
  char *v6; // rax
  NTSTATUS v7; // ebx
  unsigned __int8 v8; // r8
  unsigned __int8 v10; // r8
  struct _LIST_ENTRY *Blink; // rcx
  struct _LIST_ENTRY *v12; // rax
  void *v13; // rcx
  size_t v14; // rsi
  void *v15; // rax
  NTSTATUS v16; // eax
  CSecurityData *v17; // rcx
  _BYTE v18[16]; // [rsp+20h] [rbp-10h] BYREF
  char *v19; // [rsp+58h] [rbp+28h] BYREF
  char v20; // [rsp+60h] [rbp+30h] BYREF

  v19 = 0;
  v4 = lambda_2a70c627909d6c04886f368e19249c19_::_lambda_2a70c627909d6c04886f368e19249c19_(&v20, &v19);
  wil::scope_exit__lambda_2a70c627909d6c04886f368e19249c19___(v18, v4);
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_e5b28892b89032293cacd9153c3db07e_Traceguids, a2);
  v5 = KdcLookupDomainByDnsName(a2, a1);
  if ( !v5 )
  {
    v6 = (char *)MIDL_user_allocate(0x110u);
    v19 = v6;
    if ( !v6 )
    {
LABEL_20:
      v7 = -1073741670;
LABEL_7:
      wil::details::lambda_call__lambda_c15c0338d1745c8a41175806980fef98___::_lambda_call__lambda_c15c0338d1745c8a41175806980fef98___(v18);
      return (unsigned int)v7;
    }
    memset_0(v6, 0, 0x110u);
    v7 = RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(v19 + 224));
    if ( v7 < 0 )
      goto LABEL_7;
    *((_DWORD *)v19 + 66) = 1;
    v7 = KerbDuplicateStringEx((struct _UNICODE_STRING *)v19 + 1, a2, v8);
    if ( v7 < 0 )
      goto LABEL_7;
    if ( HIDWORD(a2[2].Buffer) == 2 )
    {
      v7 = RtlUpcaseUnicodeString((PUNICODE_STRING)v19 + 1, (PCUNICODE_STRING)v19 + 1, 0);
      if ( v7 < 0 )
        goto LABEL_7;
    }
    v7 = KerbDuplicateStringEx((struct _UNICODE_STRING *)v19 + 2, a2 + 1, v10);
    if ( v7 < 0 )
      goto LABEL_7;
    *((_DWORD *)v19 + 17) = 1;
    Blink = a1->Blink;
    if ( Blink->Flink != a1 )
      __fastfail(3u);
    v12 = (struct _LIST_ENTRY *)v19;
    *(_QWORD *)v19 = a1;
    v12->Blink = Blink;
    Blink->Flink = v12;
    v5 = (struct _KDC_DOMAIN_INFO *)v19;
    v19 = 0;
    a1->Blink = v12;
  }
  *((_DWORD *)v5 + 15) |= *(_DWORD *)&a2[3].Length;
  *((_DWORD *)v5 + 16) = HIDWORD(a2[2].Buffer);
  if ( ((__int64)a2[2].Buffer & 1) != 0 )
    *((_QWORD *)v5 + 6) = v5;
  if ( ((__int64)a2[2].Buffer & 2) != 0 )
  {
    *((_DWORD *)v5 + 14) |= 4u;
    v13 = *(void **)&a2[2].Length;
    if ( v13 )
    {
      v14 = RtlLengthSid(v13);
      v15 = MIDL_user_allocate(v14);
      *((_QWORD *)v5 + 11) = v15;
      if ( !v15 )
        goto LABEL_20;
      v16 = RtlCopySid(v14, v15, *(PSID *)&a2[2].Length);
      if ( v16 < 0 )
      {
        v7 = v16;
        goto LABEL_7;
      }
      if ( (*((_BYTE *)v5 + 60) & 8) != 0 )
        CSecurityData::SetCrossForestEnabled(v17, 1u);
    }
  }
  wil::details::lambda_call__lambda_c15c0338d1745c8a41175806980fef98___::_lambda_call__lambda_c15c0338d1745c8a41175806980fef98___(v18);
  return 0;
}

```

## disassembly

```asm
0x180058f64  mov     [rsp-18h+arg_0], rbx
0x180058f69  push    rbp
0x180058f6a  push    rsi
0x180058f6b  push    rdi
0x180058f6c  mov     rbp, rsp
0x180058f6f  sub     rsp, 30h
0x180058f73  mov     rdi, rdx
0x180058f76  mov     [rbp+arg_8], 0
0x180058f7e  mov     rsi, rcx
0x180058f81  lea     rdx, [rbp+arg_8]
0x180058f85  lea     rcx, [rbp+arg_10]
0x180058f89  call    _lambda_2a70c627909d6c04886f368e19249c19____lambda_2a70c627909d6c04886f368e19249c19_
0x180058f8e  mov     rdx, rax
0x180058f91  lea     rcx, [rbp+var_10]
0x180058f95  call    wil__scope_exit__lambda_2a70c627909d6c04886f368e19249c19___
0x180058f9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180058fa1  lea     rax, WPP_GLOBAL_Control
0x180058fa8  cmp     rcx, rax
0x180058fab  jz      short loc_180058FCE
0x180058fad  test    dword ptr [rcx+1Ch], 100h
0x180058fb4  jz      short loc_180058FCE
0x180058fb6  mov     rcx, [rcx+10h]
0x180058fba  lea     r8, WPP_e5b28892b89032293cacd9153c3db07e_Traceguids
0x180058fc1  mov     edx, 1Fh
0x180058fc6  mov     r9, rdi
0x180058fc9  call    WPP_SF_Z
0x180058fce  mov     rdx, rsi; struct _LIST_ENTRY *
0x180058fd1  mov     rcx, rdi; struct _UNICODE_STRING *
0x180058fd4  call    ?KdcLookupDomainByDnsName@@YAPEAU_KDC_DOMAIN_INFO@@PEAU_UNICODE_STRING@@PEAU_LIST_ENTRY@@@Z; KdcLookupDomainByDnsName(_UNICODE_STRING *,_LIST_ENTRY *)
0x180058fd9  mov     rbx, rax
0x180058fdc  test    rax, rax
0x180058fdf  jnz     loc_1800590C6
0x180058fe5  mov     ebx, 110h
0x180058fea  mov     ecx, ebx; size
0x180058fec  call    MIDL_user_allocate
0x180058ff1  mov     [rbp+arg_8], rax
0x180058ff5  test    rax, rax
0x180058ff8  jz      loc_180059107
0x180058ffe  mov     r8d, ebx; Size
0x180059001  xor     edx, edx; Val
0x180059003  mov     rcx, rax; void *
0x180059006  call    memset_0
0x18005900b  mov     rcx, [rbp+arg_8]
0x18005900f  add     rcx, 0E0h; CriticalSection
0x180059016  call    cs:__imp_RtlInitializeCriticalSection
0x18005901c  mov     ebx, eax
0x18005901e  test    eax, eax
0x180059020  jns     short loc_180059032
0x180059022  lea     rcx, [rbp+var_10]
0x180059026  call    wil__details__lambda_call__lambda_c15c0338d1745c8a41175806980fef98______lambda_call__lambda_c15c0338d1745c8a41175806980fef98___
0x18005902b  mov     eax, ebx
0x18005902d  jmp     loc_180059143
0x180059032  mov     rax, [rbp+arg_8]
0x180059036  mov     rdx, rdi; struct _UNICODE_STRING *
0x180059039  mov     dword ptr [rax+108h], 1
0x180059043  mov     rcx, [rbp+arg_8]
0x180059047  add     rcx, 10h; struct _UNICODE_STRING *
0x18005904b  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x180059050  mov     ebx, eax
0x180059052  test    eax, eax
0x180059054  js      short loc_180059022
0x180059056  cmp     dword ptr [rdi+2Ch], 2
0x18005905a  jnz     short loc_180059076
0x18005905c  mov     rcx, [rbp+arg_8]
0x180059060  xor     r8d, r8d; AllocateDestinationString
0x180059063  add     rcx, 10h; DestinationString
0x180059067  mov     rdx, rcx; SourceString
0x18005906a  call    cs:__imp_RtlUpcaseUnicodeString
0x180059070  mov     ebx, eax
0x180059072  test    eax, eax
0x180059074  js      short loc_180059022
0x180059076  mov     rcx, [rbp+arg_8]
0x18005907a  lea     rdx, [rdi+10h]; struct _UNICODE_STRING *
0x18005907e  add     rcx, 20h ; ' '; struct _UNICODE_STRING *
0x180059082  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x180059087  mov     ebx, eax
0x180059089  test    eax, eax
0x18005908b  js      short loc_180059022
0x18005908d  mov     rax, [rbp+arg_8]
0x180059091  mov     dword ptr [rax+44h], 1
0x180059098  mov     rcx, [rsi+8]
0x18005909c  cmp     [rcx], rsi
0x18005909f  jz      short loc_1800590A8
0x1800590a1  mov     ecx, 3
0x1800590a6  int     29h; Win8: RtlFailFast(ecx)
0x1800590a8  mov     rax, [rbp+arg_8]
0x1800590ac  mov     [rax], rsi
0x1800590af  mov     [rax+8], rcx
0x1800590b3  mov     [rcx], rax
0x1800590b6  mov     rbx, [rbp+arg_8]
0x1800590ba  mov     [rbp+arg_8], 0
0x1800590c2  mov     [rsi+8], rax
0x1800590c6  mov     eax, [rdi+30h]
0x1800590c9  or      [rbx+3Ch], eax
0x1800590cc  mov     eax, [rdi+2Ch]
0x1800590cf  mov     [rbx+40h], eax
0x1800590d2  test    byte ptr [rdi+28h], 1
0x1800590d6  jz      short loc_1800590DC
0x1800590d8  mov     [rbx+30h], rbx
0x1800590dc  test    byte ptr [rdi+28h], 2
0x1800590e0  jz      short loc_180059138
0x1800590e2  or      dword ptr [rbx+38h], 4
0x1800590e6  mov     rcx, [rdi+20h]; Sid
0x1800590ea  test    rcx, rcx
0x1800590ed  jz      short loc_180059138
0x1800590ef  call    cs:__imp_RtlLengthSid
0x1800590f5  mov     ecx, eax; size
0x1800590f7  mov     esi, eax
0x1800590f9  call    MIDL_user_allocate
0x1800590fe  mov     [rbx+58h], rax
0x180059102  test    rax, rax
0x180059105  jnz     short loc_180059111
0x180059107  mov     ebx, 0C000009Ah
0x18005910c  jmp     loc_180059022
0x180059111  mov     r8, [rdi+20h]; SourceSid
0x180059115  mov     rdx, rax; DestinationSid
0x180059118  mov     ecx, esi; DestinationSidLength
0x18005911a  call    cs:__imp_RtlCopySid
0x180059120  test    eax, eax
0x180059122  jns     short loc_18005912B
0x180059124  mov     ebx, eax
0x180059126  jmp     loc_180059022
0x18005912b  test    byte ptr [rbx+3Ch], 8
0x18005912f  jz      short loc_180059138
0x180059131  mov     dl, 1; unsigned __int8
0x180059133  call    ?SetCrossForestEnabled@CSecurityData@@QEAAXE@Z; CSecurityData::SetCrossForestEnabled(uchar)
0x180059138  lea     rcx, [rbp+var_10]
0x18005913c  call    wil__details__lambda_call__lambda_c15c0338d1745c8a41175806980fef98______lambda_call__lambda_c15c0338d1745c8a41175806980fef98___
0x180059141  xor     eax, eax
0x180059143  mov     rbx, [rsp+30h+arg_0]
0x180059148  add     rsp, 30h
0x18005914c  pop     rdi
0x18005914d  pop     rsi
0x18005914e  pop     rbp
0x18005914f  retn
```
