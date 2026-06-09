# KdcExtractFieldsFromPac(PKERB_AUTHORIZATION_DATA_s *,_PAC_INFO_BUFFER * *,ulong *)

- ea: `0x18005feb8`
- end: `0x1800600be`
- name: `?KdcExtractFieldsFromPac@@YAJPEAUPKERB_AUTHORIZATION_DATA_s@@PEAPEAU_PAC_INFO_BUFFER@@PEAK@Z`
- size: `518`
- prototype: `__int64 __fastcall(struct PKERB_AUTHORIZATION_DATA_s *, struct _PAC_INFO_BUFFER **, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005c560`

## callees

- `0x1800038f0`
- `0x1800101c4`
- `0x1800101ec`
- `0x180010718`
- `0x1800107dc`
- `0x180010884`
- `0x18001fe80`
- `0x18005a060`
- `0x18005feb8`
- `0x18006fc78`
- `0x180070f30`
- `0x1800710d8`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18005ffde`
- `ntdll!RtlEqualSid` at `0x18005fff2`
- `ntdll!RtlEqualSid` at `0x18005ffde`
- `ntdll!RtlEqualSid` at `0x18005fff2`
- `ntdll!RtlValidSid` at `0x18005ffca`
- `ntdll!RtlValidSid` at `0x18005ffca`

## pseudocode

```c
__int64 __fastcall KdcExtractFieldsFromPac(
        struct PKERB_AUTHORIZATION_DATA_s *a1,
        struct _PAC_INFO_BUFFER **a2,
        unsigned int *a3)
{
  __int64 v6; // rax
  _DWORD *v7; // r8
  struct _PACTYPE *v8; // rbp
  struct _PAC_INFO_BUFFER *v9; // r8
  unsigned int v10; // ebx
  struct _PAC_INFO_BUFFER *v11; // rax
  struct _PAC_INFO_BUFFER *v12; // r8
  int v13; // eax
  unsigned int i; // ebx
  void *v15; // rdi
  struct _PAC_INFO_BUFFER *v16; // rax
  struct _PAC_INFO_BUFFER *v17; // rdi
  char *v18; // rax
  struct _PAC_INFO_BUFFER *v19; // rbx
  unsigned int v20; // edx
  _BYTE v22[56]; // [rsp+30h] [rbp-38h] BYREF
  struct _NETLOGON_VALIDATION_SAM_INFO3 *v23; // [rsp+70h] [rbp+8h] BYREF
  __int64 v24; // [rsp+80h] [rbp+18h] BYREF

  v23 = 0;
  v6 = lambda_2a70c627909d6c04886f368e19249c19_::_lambda_2a70c627909d6c04886f368e19249c19_(&v24, &v23);
  wil::scope_exit__lambda_2a70c627909d6c04886f368e19249c19___(v22, v6);
  *v7 = 0;
  v8 = (struct _PACTYPE *)*((_QWORD *)a1 + 3);
  if ( !PAC_UnMarshal(v8, *((_DWORD *)a1 + 4)) )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
    goto LABEL_5;
  }
  v11 = PAC_Find(v8, 1u, v9);
  if ( v11 )
  {
    v13 = PAC_UnmarshallValidationInfo(&v23, *((unsigned __int8 **)v11 + 1), *((_DWORD *)v11 + 1));
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          128,
          WPP_b168486f65343579948eb0cc9cf7c178_Traceguids,
          (unsigned int)v13);
      goto LABEL_5;
    }
    for ( i = 0; i < *((_DWORD *)v23 + 68); ++i )
    {
      v15 = *(void **)(*((_QWORD *)v23 + 35) + 16LL * i);
      if ( RtlValidSid(v15) )
      {
        if ( RtlEqualSid(v15, GlobalAuthenticationAuthorityAssertedSid) )
        {
          *a3 = 1;
          break;
        }
        if ( RtlEqualSid(v15, GlobalAuthenticationServiceAssertedSid) )
        {
          *a3 = 2;
          break;
        }
      }
    }
  }
  v16 = PAC_Find(v8, 2u, v12);
  v17 = v16;
  if ( !v16 )
  {
LABEL_25:
    v10 = 0;
    goto LABEL_26;
  }
  if ( *((_DWORD *)v16 + 1) < 0xFFFFFFF0 )
  {
    v18 = (char *)MIDL_user_allocate((unsigned int)(*((_DWORD *)v16 + 1) + 16));
    v19 = (struct _PAC_INFO_BUFFER *)v18;
    if ( v18 )
    {
      *(_DWORD *)v18 = 2;
      v20 = *((_DWORD *)v17 + 1);
      *((_DWORD *)v18 + 1) = v20;
      *((_QWORD *)v18 + 1) = v18 + 16;
      memcpy_0(v18 + 16, *((const void **)v17 + 1), v20);
      *a2 = v19;
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      {
        WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, *a3);
      }
      goto LABEL_25;
    }
  }
LABEL_5:
  v10 = 60;
LABEL_26:
  wil::details::lambda_call__lambda_eb3c6cf637a6f9bf09df8801c3663cc5___::_lambda_call__lambda_eb3c6cf637a6f9bf09df8801c3663cc5___(v22);
  return v10;
}

```

## disassembly

```asm
0x18005feb8  mov     rax, rsp
0x18005febb  mov     [rax+10h], rbx
0x18005febf  push    rbp
0x18005fec0  push    rsi
0x18005fec1  push    rdi
0x18005fec2  push    r14
0x18005fec4  push    r15
0x18005fec6  sub     rsp, 40h
0x18005feca  mov     rsi, r8
0x18005fecd  mov     r15, rdx
0x18005fed0  mov     r14, rcx
0x18005fed3  mov     qword ptr [rax+8], 0
0x18005fedb  lea     rdx, [rax+8]
0x18005fedf  lea     rcx, [rax+18h]
0x18005fee3  call    _lambda_2a70c627909d6c04886f368e19249c19____lambda_2a70c627909d6c04886f368e19249c19_
0x18005fee8  mov     rdx, rax
0x18005feeb  lea     rcx, [rsp+68h+var_38]
0x18005fef0  call    wil__scope_exit__lambda_2a70c627909d6c04886f368e19249c19___
0x18005fef5  nop
0x18005fef6  mov     dword ptr [r8], 0
0x18005fefd  mov     rbp, [r14+18h]
0x18005ff01  mov     edx, [r14+10h]; unsigned int
0x18005ff05  mov     rcx, rbp; struct _PACTYPE *
0x18005ff08  call    ?PAC_UnMarshal@@YAKPEAU_PACTYPE@@K@Z; PAC_UnMarshal(_PACTYPE *,ulong)
0x18005ff0d  test    eax, eax
0x18005ff0f  jnz     short loc_18005FF49
0x18005ff11  lea     rax, WPP_GLOBAL_Control
0x18005ff18  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ff1f  cmp     rcx, rax
0x18005ff22  jz      short loc_18005FF3F
0x18005ff24  test    byte ptr [rcx+1Ch], 1
0x18005ff28  jz      short loc_18005FF3F
0x18005ff2a  mov     edx, 7Fh
0x18005ff2f  lea     r8, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids
0x18005ff36  mov     rcx, [rcx+10h]
0x18005ff3a  call    WPP_SF_
0x18005ff3f  mov     ebx, 3Ch ; '<'
0x18005ff44  jmp     loc_1800600A1
0x18005ff49  mov     edx, 1; unsigned int
0x18005ff4e  mov     rcx, rbp; struct _PACTYPE *
0x18005ff51  call    ?PAC_Find@@YAPEAU_PAC_INFO_BUFFER@@PEAU_PACTYPE@@KPEAU1@@Z; PAC_Find(_PACTYPE *,ulong,_PAC_INFO_BUFFER *)
0x18005ff56  test    rax, rax
0x18005ff59  jz      loc_18006000E
0x18005ff5f  mov     r8d, [rax+4]; unsigned int
0x18005ff63  mov     rdx, [rax+8]; unsigned __int8 *
0x18005ff67  lea     rcx, [rsp+68h+arg_0]; struct _NETLOGON_VALIDATION_SAM_INFO3 **
0x18005ff6c  call    ?PAC_UnmarshallValidationInfo@@YAJPEAPEAU_NETLOGON_VALIDATION_SAM_INFO3@@PEAEK@Z; PAC_UnmarshallValidationInfo(_NETLOGON_VALIDATION_SAM_INFO3 * *,uchar *,ulong)
0x18005ff71  mov     r9d, eax
0x18005ff74  test    eax, eax
0x18005ff76  jns     short loc_18005FFA8
0x18005ff78  lea     rax, WPP_GLOBAL_Control
0x18005ff7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ff86  cmp     rcx, rax
0x18005ff89  jz      short loc_18005FF3F
0x18005ff8b  test    byte ptr [rcx+1Ch], 1
0x18005ff8f  jz      short loc_18005FF3F
0x18005ff91  mov     edx, 80h
0x18005ff96  lea     r8, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids
0x18005ff9d  mov     rcx, [rcx+10h]
0x18005ffa1  call    WPP_SF_d
0x18005ffa6  jmp     short loc_18005FF3F
0x18005ffa8  xor     ebx, ebx
0x18005ffaa  mov     rax, [rsp+68h+arg_0]
0x18005ffaf  cmp     ebx, [rax+110h]
0x18005ffb5  jnb     short loc_18006000E
0x18005ffb7  mov     ecx, ebx
0x18005ffb9  add     rcx, rcx
0x18005ffbc  mov     rax, [rax+118h]
0x18005ffc3  mov     rdi, [rax+rcx*8]
0x18005ffc7  mov     rcx, rdi; Sid
0x18005ffca  call    cs:__imp_RtlValidSid
0x18005ffd0  test    al, al
0x18005ffd2  jz      short loc_18005FFFC
0x18005ffd4  mov     rdx, cs:?GlobalAuthenticationAuthorityAssertedSid@@3PEAXEA; Sid2
0x18005ffdb  mov     rcx, rdi; Sid1
0x18005ffde  call    cs:__imp_RtlEqualSid
0x18005ffe4  test    al, al
0x18005ffe6  jnz     short loc_180060008
0x18005ffe8  mov     rdx, cs:?GlobalAuthenticationServiceAssertedSid@@3PEAXEA; Sid2
0x18005ffef  mov     rcx, rdi; Sid1
0x18005fff2  call    cs:__imp_RtlEqualSid
0x18005fff8  test    al, al
0x18005fffa  jnz     short loc_180060000
0x18005fffc  inc     ebx
0x18005fffe  jmp     short loc_18005FFAA
0x180060000  mov     dword ptr [rsi], 2
0x180060006  jmp     short loc_18006000E
0x180060008  mov     dword ptr [rsi], 1
0x18006000e  mov     edx, 2; unsigned int
0x180060013  mov     rcx, rbp; struct _PACTYPE *
0x180060016  call    ?PAC_Find@@YAPEAU_PAC_INFO_BUFFER@@PEAU_PACTYPE@@KPEAU1@@Z; PAC_Find(_PACTYPE *,ulong,_PAC_INFO_BUFFER *)
0x18006001b  mov     rdi, rax
0x18006001e  test    rax, rax
0x180060021  jz      short loc_18006009F
0x180060023  mov     ecx, [rax+4]
0x180060026  add     ecx, 10h; size
0x180060029  cmp     ecx, 10h
0x18006002c  jb      loc_18005FF3F
0x180060032  call    MIDL_user_allocate
0x180060037  mov     rbx, rax
0x18006003a  test    rax, rax
0x18006003d  jz      loc_18005FF3F
0x180060043  mov     dword ptr [rax], 2
0x180060049  mov     edx, [rdi+4]
0x18006004c  mov     [rax+4], edx
0x18006004f  lea     rcx, [rax+10h]; void *
0x180060053  mov     [rax+8], rcx
0x180060057  mov     r8d, edx; Size
0x18006005a  mov     rdx, [rdi+8]; Src
0x18006005e  call    memcpy_0
0x180060063  mov     [r15], rbx
0x180060066  lea     rax, WPP_GLOBAL_Control
0x18006006d  mov     rcx, cs:WPP_GLOBAL_Control
0x180060074  cmp     rcx, rax
0x180060077  jz      short loc_18006009F
0x180060079  test    dword ptr [rcx+1Ch], 40000h
0x180060080  jz      short loc_18006009F
0x180060082  mov     edx, 81h
0x180060087  mov     [rsp+68h+var_48], r14
0x18006008c  mov     r9d, [rsi]
0x18006008f  lea     r8, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids
0x180060096  mov     rcx, [rcx+10h]
0x18006009a  call    WPP_SF_Dq
0x18006009f  xor     ebx, ebx
0x1800600a1  lea     rcx, [rsp+68h+var_38]
0x1800600a6  call    wil__details__lambda_call__lambda_eb3c6cf637a6f9bf09df8801c3663cc5______lambda_call__lambda_eb3c6cf637a6f9bf09df8801c3663cc5___
0x1800600ab  mov     eax, ebx
0x1800600ad  mov     rbx, [rsp+68h+arg_8]
0x1800600b2  add     rsp, 40h
0x1800600b6  pop     r15
0x1800600b8  pop     r14
0x1800600ba  pop     rdi
0x1800600bb  pop     rsi
0x1800600bc  pop     rbp
0x1800600bd  retn
```
