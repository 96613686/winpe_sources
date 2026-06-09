# KdcCrackNameAtGC(_UNICODE_STRING *,_KERB_INTERNAL_NAME *,ulong,ulong,uchar,_UNICODE_STRING *,_KDC_TICKET_INFO *,uchar *,uchar *,uchar *,KERB_EXT_ERROR *,void * *,ulong,ulong,_USER_INTERNAL6_INFORMATION * *,_SID_AND_ATTRIBUTES_LIST *,_SAM_MAPPED_ATTRIBUTE_SET *)

- ea: `0x18005f318`
- end: `0x18005fc66`
- name: `?KdcCrackNameAtGC@@YAJPEAU_UNICODE_STRING@@PEAU_KERB_INTERNAL_NAME@@KKE0PEAU_KDC_TICKET_INFO@@PEAE33PEAUKERB_EXT_ERROR@@PEAPEAXKKPEAPEAU_USER_INTERNAL6_INFORMATION@@PEAU_SID_AND_ATTRIBUTES_LIST@@PEAU_SAM_MAPPED_ATTRIBUTE_SET@@@Z`
- size: `2382`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _KERB_INTERNAL_NAME *, unsigned int, unsigned int, unsigned __int8, struct _UNICODE_STRING *, struct _KDC_TICKET_INFO *, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, struct KERB_EXT_ERROR *, void **, unsigned int, unsigned int, struct _USER_INTERNAL6_INFORMATION **, struct _SID_AND_ATTRIBUTES_LIST *, struct _SAM_MAPPED_ATTRIBUTE_SET *)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800635a8`

## callees

- `0x180002ad0`
- `0x180003980`
- `0x18000e440`
- `0x1800101c4`
- `0x1800101ec`
- `0x180010278`
- `0x18001ff94`
- `0x18003669c`
- `0x18004b568`
- `0x180057130`
- `0x180057634`
- `0x180057fb4`
- `0x18005a060`
- `0x18005a090`
- `0x18005ad20`
- `0x18005bd2c`
- `0x18005d574`
- `0x18005f318`
- `0x180060b5c`
- `0x1800633bc`
- `0x180065dfc`
- `0x180065ef4`
- `0x1800665cc`
- `0x180066660`
- `0x180072338`
- `0x18007a92c`
- `0x18007c4d4`
- `0x18007d0f0`
- `0x18007dc20`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18005f7a5`
- `ntdll!RtlInitUnicodeString` at `0x18005f7ed`
- `ntdll!RtlInitUnicodeString` at `0x18005f839`
- `ntdll!RtlInitUnicodeString` at `0x18005f7a5`
- `ntdll!RtlInitUnicodeString` at `0x18005f7ed`
- `ntdll!RtlInitUnicodeString` at `0x18005f839`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall KdcCrackNameAtGC(
        struct _UNICODE_STRING *a1,
        struct _KERB_INTERNAL_NAME *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int8 a5,
        struct _UNICODE_STRING *a6,
        struct _KDC_TICKET_INFO *a7,
        unsigned __int8 *a8,
        unsigned __int8 *a9,
        unsigned __int8 *a10,
        struct KERB_EXT_ERROR *a11,
        void **a12,
        unsigned int a13,
        unsigned int a14,
        struct _USER_INTERNAL6_INFORMATION **a15,
        struct _SID_AND_ATTRIBUTES_LIST *a16,
        struct _SAM_MAPPED_ATTRIBUTE_SET *a17)
{
  unsigned int v20; // edi
  bool v21; // r12
  unsigned int TicketInfo; // ebx
  void *v23; // r8
  const WCHAR *v24; // rax
  CSecurityData *v25; // rcx
  int v26; // r15d
  int v27; // eax
  struct IKdcBackend *v28; // rax
  unsigned int v29; // r11d
  wchar_t *v30; // rcx
  CSecurityData *v31; // rcx
  unsigned __int8 *v32; // rdi
  unsigned __int8 v33; // r8
  int ReferralTarget; // eax
  CSecurityData *v35; // rcx
  CSecurityData *v37; // rcx
  struct _UNICODE_STRING *p_DestinationString; // r9
  struct KERB_EXT_ERROR *v39; // r15
  __int64 v40; // rdx
  __int64 v41; // rdx
  PWSTR v42; // rdi
  unsigned __int8 v43; // r8
  char v44; // [rsp+70h] [rbp-90h] BYREF
  char v45; // [rsp+71h] [rbp-8Fh] BYREF
  int v46; // [rsp+74h] [rbp-8Ch] BYREF
  void *v47; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v48[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v50; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v51; // [rsp+A4h] [rbp-5Ch] BYREF
  int v52; // [rsp+A8h] [rbp-58h]
  PCWSTR SourceString; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int8 *v54; // [rsp+B8h] [rbp-48h]
  unsigned int v55; // [rsp+C0h] [rbp-40h]
  struct KERB_EXT_ERROR *v56; // [rsp+C8h] [rbp-38h]
  _QWORD v57[8]; // [rsp+D0h] [rbp-30h] BYREF
  char v58; // [rsp+110h] [rbp+10h]
  unsigned __int8 *v59; // [rsp+120h] [rbp+20h] BYREF
  struct _KERB_INTERNAL_NAME *v60; // [rsp+128h] [rbp+28h]
  unsigned __int8 *v61; // [rsp+130h] [rbp+30h]
  struct _UNICODE_STRING v62; // [rsp+140h] [rbp+40h] BYREF
  struct _UNICODE_STRING v63; // [rsp+150h] [rbp+50h] BYREF
  struct _UNICODE_STRING *v64; // [rsp+160h] [rbp+60h]
  struct _SAM_MAPPED_ATTRIBUTE_SET *v65; // [rsp+168h] [rbp+68h]
  struct _SID_AND_ATTRIBUTES_LIST *v66; // [rsp+170h] [rbp+70h]
  struct _USER_INTERNAL6_INFORMATION **v67; // [rsp+178h] [rbp+78h]
  struct _UNICODE_STRING v68; // [rsp+180h] [rbp+80h] BYREF
  wchar_t Buffer[12]; // [rsp+190h] [rbp+90h] BYREF

  v55 = a4;
  v60 = a2;
  v64 = a1;
  v59 = a8;
  v61 = a9;
  v54 = a10;
  v56 = a11;
  *(_QWORD *)&v62.Length = a12;
  v67 = a15;
  v66 = a16;
  v65 = a17;
  v48[0] = 0;
  DestinationString = 0;
  v68 = 0;
  v47 = 0;
  v50 = 256;
  SourceString = 0;
  v51 = 513;
  v46 = 0;
  v44 = 0;
  v45 = 0;
  v63 = 0;
  v57[0] = &v44;
  v57[1] = &v63;
  v57[2] = &v45;
  v57[3] = &v47;
  v57[4] = &SourceString;
  v57[5] = &v59;
  v57[6] = &DestinationString;
  v57[7] = v48;
  v58 = 1;
  if ( (a3 & 0x80u) == 0 )
  {
    if ( (a3 & 0x40) != 0 )
      v20 = -17;
    else
      v20 = (a3 & 0x21) != 0 ? 8 : 10;
  }
  else
  {
    v20 = -11;
  }
  *a8 = 1;
  v47 = MIDL_user_allocate(2LL * v50);
  if ( !v47
    || (SourceString = (PCWSTR)MIDL_user_allocate(2LL * v51)) == 0
    || (v21 = v20 == 8, (v48[0] = (unsigned __int16 *)KerbBuildNullTerminatedString(a1)) == 0) )
  {
LABEL_119:
    v58 = 0;
    lambda_49608eef1472eb6acb259000b1a10843_::operator()(v57);
    return 60;
  }
  TicketInfo = 0;
  v52 = 12;
  if ( !a5 )
    goto LABEL_18;
  if ( v47 )
    MIDL_user_free(v47);
  if ( SourceString )
    MIDL_user_free((void *)SourceString);
  v23 = (void *)*((_QWORD *)a2 + 6);
  v47 = v23;
  v24 = (const WCHAR *)*((_QWORD *)a2 + 4);
  SourceString = v24;
  v45 = 1;
  v25 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_SSS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)&WPP_GLOBAL_Control,
      (_DWORD)v23,
      v48[0],
      (__int64)v24,
      (__int64)v23);
    v23 = v47;
    v25 = WPP_GLOBAL_Control;
  }
  v26 = 0;
  v27 = 0;
  v46 = 0;
  while ( 1 )
  {
    if ( v26 )
      goto LABEL_23;
    if ( !v27 || v27 == 5 )
      break;
    if ( v27 == 7 )
    {
      if ( v25 != (CSecurityData *)&WPP_GLOBAL_Control && *((char *)v25 + 28) < 0 )
      {
        WPP_SF_S(*((_QWORD *)v25 + 2), 14, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, v23);
        v23 = v47;
      }
      RtlInitUnicodeString(&DestinationString, (PCWSTR)v23);
      v32 = v54;
      *v54 = 1;
      goto LABEL_57;
    }
LABEL_23:
    if ( v26 == -1073741136 && (v52 & 4) != 0 )
    {
      v52 &= ~4u;
    }
    else
    {
      if ( v27 == 3 )
      {
        memset(Buffer, 0, 22);
        if ( v20 >= 0xD || (v30 = (wchar_t *)(&KdcGlobalNameTypes)[v20]) == 0 )
        {
          swprintf_s(Buffer, 0xAu, L"%d", v20);
          v30 = Buffer;
        }
        ReportServiceEvent(1u, 0xC000000B, 0, 0, 2u, v48[0], v30);
        LOBYTE(v27) = v46;
        v25 = WPP_GLOBAL_Control;
      }
      if ( byte_1800B2F0A && HIBYTE(word_1800B2F08) )
      {
        if ( !(unsigned int)KdcMatchCrossForestName(v60, &DestinationString) )
        {
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            WPP_SF_Z(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              12,
              WPP_b168486f65343579948eb0cc9cf7c178_Traceguids,
              &DestinationString);
          *v54 = 1;
        }
        v25 = WPP_GLOBAL_Control;
        LOBYTE(v27) = v46;
      }
      if ( v25 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 2) != 0 )
        WPP_SF_SDd(*((_QWORD *)v25 + 2), (unsigned int)&WPP_GLOBAL_Control, (_DWORD)v23, v48[0], v26, v27);
      if ( !v21 )
      {
        v58 = 0;
        lambda_49608eef1472eb6acb259000b1a10843_::operator()(v57);
        return 6;
      }
      MIDL_user_free(v48[0]);
      v21 = 0;
      v48[0] = 0;
      TicketInfo = KdcBuildNt4Name(v48, &DestinationString, v64);
      if ( TicketInfo )
      {
        if ( TicketInfo == 68 )
        {
          *v59 = 0;
          TicketInfo = 0;
          goto LABEL_56;
        }
LABEL_117:
        v58 = 0;
        lambda_49608eef1472eb6acb259000b1a10843_::operator()(v57);
        return TicketInfo;
      }
      v20 = 2;
      v50 = 256;
      v51 = 513;
    }
LABEL_18:
    v28 = GlobalKdcService::Get();
    v26 = (*(__int64 (__fastcall **)(struct IKdcBackend *, _QWORD, _QWORD, unsigned __int16 *, int, unsigned int *, void *, unsigned int *, PCWSTR, int *))(*(_QWORD *)v28 + 128LL))(
            v28,
            v20,
            v29,
            v48[0],
            6,
            &v50,
            v47,
            &v51,
            SourceString,
            &v46);
    v23 = v47;
    v27 = v46;
    v25 = WPP_GLOBAL_Control;
  }
  if ( v25 != (CSecurityData *)&WPP_GLOBAL_Control && *((char *)v25 + 28) < 0 )
  {
    WPP_SF_S(*((_QWORD *)v25 + 2), 15, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, v23);
    v23 = v47;
  }
  RtlInitUnicodeString(&DestinationString, (PCWSTR)v23);
LABEL_56:
  v32 = v54;
LABEL_57:
  if ( CSecurityData::IsOurRealm(v31, &DestinationString) )
  {
    *v61 = 0;
    RtlInitUnicodeString(&v68, SourceString);
    TicketInfo = KdcGetTicketInfo(&v68, 0x100u, v55, 0, 0, a7, v56, *(void ***)&v62.Length, a13, a14, v67, v66, v65);
    goto LABEL_117;
  }
  if ( (a3 & 1) != 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
    if ( *v32 )
    {
      if ( (int)KerbDuplicateStringEx(a6, &DestinationString, v33) < 0 )
        goto LABEL_119;
    }
    else
    {
      ReferralTarget = KdcFindReferralTarget(a7, a6, v56, &DestinationString, 0, a3);
      TicketInfo = ReferralTarget;
      if ( ReferralTarget )
      {
        if ( ReferralTarget == -2147483643 )
          TicketInfo = 7;
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, TicketInfo);
        goto LABEL_117;
      }
    }
LABEL_113:
    *v61 = 1;
    if ( TicketInfo )
      MicrosoftTelemetryAssertTriggeredNoArgs(v35);
    goto LABEL_117;
  }
  if ( !KdcGlobalCDC )
  {
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
    if ( (a3 & 0x22) != 0 && !byte_1800B2F0A && *v32 )
    {
      v44 = 1;
      if ( (int)CSecurityData::GetKdcForestRoot(v37, &v63) < 0 )
        goto LABEL_119;
      if ( v44 )
      {
        p_DestinationString = &v63;
        goto LABEL_89;
      }
    }
    else
    {
      v44 = 0;
    }
    p_DestinationString = &DestinationString;
LABEL_89:
    v39 = v56;
    TicketInfo = KdcFindReferralTarget(a7, a6, v56, p_DestinationString, 0, a3);
    LOBYTE(v40) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstantHAADJ>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_InstantHAADJ>::GetImpl'::`2'::impl,
      v40);
    if ( TicketInfo )
    {
      if ( !KdcUseForestSearchOrder )
        goto LABEL_115;
      if ( *(_WORD *)v60 != 2 )
        goto LABEL_115;
      if ( *((_WORD *)v60 + 1) != 2 )
        goto LABEL_115;
      v62 = 0;
      KerbSearchForests(v60, &v62);
      KerbSqmKdcFSOCallIncrement();
      v42 = v62.Buffer;
      if ( !v62.Buffer )
        goto LABEL_115;
      KerbSqmKdcFSOHitIncrement();
      if ( DestinationString.Buffer )
        KerbFreeString(&DestinationString);
      if ( v44 )
      {
        KerbFreeString(&v63);
        v44 = 0;
      }
      DestinationString = v62;
      v47 = v42;
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_Z(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          WPP_b168486f65343579948eb0cc9cf7c178_Traceguids,
          &DestinationString);
      TicketInfo = KdcCheckForCrossForestReferral(a7, a6, v39, &DestinationString, a3);
      if ( TicketInfo )
      {
LABEL_115:
        if ( TicketInfo == -2147483643 )
          TicketInfo = 7;
        goto LABEL_117;
      }
      goto LABEL_111;
    }
    if ( !v44 )
      goto LABEL_113;
    if ( a7 )
    {
      *((_DWORD *)a7 + 28) |= 0x2000u;
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v41 = 20;
LABEL_98:
        WPP_SF_(*((_QWORD *)v35 + 2), v41, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
      }
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v35);
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v41 = 21;
        goto LABEL_98;
      }
    }
LABEL_111:
    if ( v44 )
    {
      KerbFreeString(&v63);
      KerbFreeString(a6);
      KerbDuplicateStringEx(a6, &DestinationString, v43);
    }
    goto LABEL_113;
  }
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
  }
  v58 = 0;
  lambda_49608eef1472eb6acb259000b1a10843_::operator()(v57);
  return 2147483654LL;
}

```

## disassembly

```asm
0x18005f318  push    rbp
0x18005f31a  push    rbx
0x18005f31b  push    rsi
0x18005f31c  push    rdi
0x18005f31d  push    r12
0x18005f31f  push    r13
0x18005f321  push    r14
0x18005f323  push    r15
0x18005f325  lea     rbp, [rsp-0B8h]
0x18005f32d  sub     rsp, 1B8h
0x18005f334  mov     rax, cs:__security_cookie
0x18005f33b  xor     rax, rsp
0x18005f33e  mov     [rbp+0F0h+var_48], rax
0x18005f345  mov     [rbp+0F0h+var_130], r9d
0x18005f349  mov     r14d, r8d
0x18005f34c  mov     r15, rdx
0x18005f34f  mov     [rbp+0F0h+var_C8], rdx
0x18005f353  mov     rbx, rcx
0x18005f356  mov     [rbp+0F0h+var_90], rcx
0x18005f35a  mov     r13, [rbp+0F0h+arg_28]
0x18005f361  mov     rsi, [rbp+0F0h+arg_30]
0x18005f368  mov     rdx, [rbp+0F0h+arg_38]
0x18005f36f  mov     [rbp+0F0h+var_D0], rdx
0x18005f373  mov     rax, [rbp+0F0h+arg_40]
0x18005f37a  mov     [rbp+0F0h+var_C0], rax
0x18005f37e  mov     rax, [rbp+0F0h+arg_48]
0x18005f385  mov     [rbp+0F0h+var_138], rax
0x18005f389  mov     rax, [rbp+0F0h+arg_50]
0x18005f390  mov     [rbp+0F0h+var_128], rax
0x18005f394  mov     rax, [rbp+0F0h+arg_58]
0x18005f39b  mov     qword ptr [rbp+0F0h+var_B0.Length], rax
0x18005f39f  mov     rax, [rbp+0F0h+arg_70]
0x18005f3a6  mov     [rbp+0F0h+var_78], rax
0x18005f3aa  mov     rax, [rbp+0F0h+arg_78]
0x18005f3b1  mov     [rbp+0F0h+var_80], rax
0x18005f3b5  mov     rax, [rbp+0F0h+arg_80]
0x18005f3bc  mov     [rbp+0F0h+var_88], rax
0x18005f3c0  xor     r12d, r12d
0x18005f3c3  mov     [rbp+0F0h+var_170], r12
0x18005f3c7  xorps   xmm0, xmm0
0x18005f3ca  movups  xmmword ptr [rbp+0F0h+DestinationString.Length], xmm0
0x18005f3ce  xorps   xmm1, xmm1
0x18005f3d1  movups  xmmword ptr [rbp+0F0h+var_70.Length], xmm1
0x18005f3d8  mov     [rsp+1F0h+var_178], r12
0x18005f3dd  mov     [rbp+0F0h+var_150], 100h
0x18005f3e4  mov     [rbp+0F0h+SourceString], r12
0x18005f3e8  mov     [rbp+0F0h+var_14C], 201h
0x18005f3ef  mov     [rsp+1F0h+var_17C], r12d
0x18005f3f4  mov     [rsp+1F0h+var_180], r12b
0x18005f3f9  mov     [rsp+1F0h+var_17F], r12b
0x18005f3fe  movups  xmmword ptr [rbp+0F0h+var_A0.Length], xmm0
0x18005f402  lea     rax, [rsp+1F0h+var_180]
0x18005f407  mov     [rbp+0F0h+var_120], rax
0x18005f40b  lea     rax, [rbp+0F0h+var_A0]
0x18005f40f  mov     [rbp+0F0h+var_118], rax
0x18005f413  lea     rax, [rsp+1F0h+var_17F]
0x18005f418  mov     [rbp+0F0h+var_110], rax
0x18005f41c  lea     rax, [rsp+1F0h+var_178]
0x18005f421  mov     [rbp+0F0h+var_108], rax
0x18005f425  lea     rax, [rbp+0F0h+SourceString]
0x18005f429  mov     [rbp+0F0h+var_100], rax
0x18005f42d  lea     rax, [rbp+0F0h+var_D0]
0x18005f431  mov     [rbp+0F0h+var_F8], rax
0x18005f435  lea     rax, [rbp+0F0h+DestinationString]
0x18005f439  mov     [rbp+0F0h+var_F0], rax
0x18005f43d  lea     rax, [rbp+0F0h+var_170]
0x18005f441  mov     [rbp+0F0h+var_E8], rax
0x18005f445  lea     ecx, [r12+1]
0x18005f44a  mov     [rbp+0F0h+var_E0], cl
0x18005f44d  test    r8b, r8b
0x18005f450  jns     short loc_18005F459
0x18005f452  mov     edi, 0FFFFFFF5h
0x18005f457  jmp     short loc_18005F475
0x18005f459  test    r14b, 40h
0x18005f45d  jz      short loc_18005F466
0x18005f45f  mov     edi, 0FFFFFFEFh
0x18005f464  jmp     short loc_18005F475
0x18005f466  mov     al, r14b
0x18005f469  and     al, 21h
0x18005f46b  neg     al
0x18005f46d  sbb     edi, edi
0x18005f46f  and     edi, 0FFFFFFFEh
0x18005f472  add     edi, 0Ah
0x18005f475  mov     [rdx], cl
0x18005f477  mov     ecx, [rbp+0F0h+var_150]
0x18005f47a  add     rcx, rcx; size
0x18005f47d  call    MIDL_user_allocate
0x18005f482  mov     [rsp+1F0h+var_178], rax
0x18005f487  test    rax, rax
0x18005f48a  jz      loc_18005FC31
0x18005f490  mov     ecx, [rbp+0F0h+var_14C]
0x18005f493  add     rcx, rcx; size
0x18005f496  call    MIDL_user_allocate
0x18005f49b  mov     [rbp+0F0h+SourceString], rax
0x18005f49f  test    rax, rax
0x18005f4a2  jz      loc_18005FC31
0x18005f4a8  cmp     edi, 8
0x18005f4ab  setz    r12b
0x18005f4af  mov     rcx, rbx
0x18005f4b2  call    KerbBuildNullTerminatedString
0x18005f4b7  mov     [rbp+0F0h+var_170], rax
0x18005f4bb  test    rax, rax
0x18005f4be  jz      loc_18005FC2E
0x18005f4c4  xor     ebx, ebx
0x18005f4c6  lea     r11d, [rbx+0Ch]
0x18005f4ca  mov     [rbp+0F0h+var_148], r11d
0x18005f4ce  cmp     [rbp+0F0h+arg_20], bl
0x18005f4d4  jz      short loc_18005F550
0x18005f4d6  mov     rcx, [rsp+1F0h+var_178]; void *
0x18005f4db  test    rcx, rcx
0x18005f4de  jz      short loc_18005F4E5
0x18005f4e0  call    MIDL_user_free
0x18005f4e5  mov     rcx, [rbp+0F0h+SourceString]; void *
0x18005f4e9  test    rcx, rcx
0x18005f4ec  jz      short loc_18005F4F3
0x18005f4ee  call    MIDL_user_free
0x18005f4f3  mov     r8, [r15+30h]
0x18005f4f7  mov     [rsp+1F0h+var_178], r8
0x18005f4fc  mov     rax, [r15+20h]
0x18005f500  mov     [rbp+0F0h+SourceString], rax
0x18005f504  mov     [rsp+1F0h+var_17F], 1
0x18005f509  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f510  lea     rdx, WPP_GLOBAL_Control
0x18005f517  cmp     rcx, rdx
0x18005f51a  jz      short loc_18005F545
0x18005f51c  test    byte ptr [rcx+1Ch], 2
0x18005f520  jz      short loc_18005F545
0x18005f522  mov     [rsp+1F0h+var_1C8], r8
0x18005f527  mov     [rsp+1F0h+var_1D0], rax
0x18005f52c  mov     r9, [rbp+0F0h+var_170]
0x18005f530  mov     rcx, [rcx+10h]
0x18005f534  call    WPP_SF_SSS
0x18005f539  mov     r8, [rsp+1F0h+var_178]
0x18005f53e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f545  xor     r15d, r15d
0x18005f548  xor     eax, eax
0x18005f54a  mov     [rsp+1F0h+var_17C], eax
0x18005f54e  jmp     short loc_18005F5BD
0x18005f550  call    ?Get@GlobalKdcService@@SAAEAUIKdcBackend@@XZ; GlobalKdcService::Get(void)
0x18005f555  mov     r10, rax
0x18005f558  mov     rdx, [rbp+0F0h+SourceString]
0x18005f55c  mov     r8, [rsp+1F0h+var_178]
0x18005f561  mov     rcx, [rax]
0x18005f564  mov     rax, [rcx+80h]
0x18005f56b  lea     rcx, [rsp+1F0h+var_17C]
0x18005f570  mov     qword ptr [rsp+1F0h+var_1A8], rcx
0x18005f575  mov     qword ptr [rsp+1F0h+var_1B0], rdx
0x18005f57a  lea     rcx, [rbp+0F0h+var_14C]
0x18005f57e  mov     [rsp+1F0h+var_1B8], rcx
0x18005f583  mov     [rsp+1F0h+var_1C0], r8
0x18005f588  lea     rcx, [rbp+0F0h+var_150]
0x18005f58c  mov     [rsp+1F0h+var_1C8], rcx
0x18005f591  mov     dword ptr [rsp+1F0h+var_1D0], 6
0x18005f599  mov     r9, [rbp+0F0h+var_170]
0x18005f59d  mov     r8d, r11d
0x18005f5a0  mov     edx, edi
0x18005f5a2  mov     rcx, r10
0x18005f5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f5aa  mov     r15d, eax
0x18005f5ad  mov     r8, [rsp+1F0h+var_178]
0x18005f5b2  mov     eax, [rsp+1F0h+var_17C]
0x18005f5b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f5bd  test    r15d, r15d
0x18005f5c0  jnz     short loc_18005F5DC
0x18005f5c2  test    eax, eax
0x18005f5c4  jz      loc_18005F76A
0x18005f5ca  cmp     eax, 5
0x18005f5cd  jz      loc_18005F76A
0x18005f5d3  cmp     eax, 7
0x18005f5d6  jz      loc_18005F76F
0x18005f5dc  cmp     r15d, 0C00002B0h
0x18005f5e3  jnz     short loc_18005F5FC
0x18005f5e5  mov     r11d, [rbp+0F0h+var_148]
0x18005f5e9  test    r11b, 4
0x18005f5ed  jz      short loc_18005F5FC
0x18005f5ef  and     r11d, 0FFFFFFFBh
0x18005f5f3  mov     [rbp+0F0h+var_148], r11d
0x18005f5f7  jmp     loc_18005F550
0x18005f5fc  cmp     eax, 3
0x18005f5ff  jnz     loc_18005F68A
0x18005f605  xorps   xmm0, xmm0
0x18005f608  xor     eax, eax
0x18005f60a  movups  xmmword ptr [rbp+0F0h+Buffer], xmm0
0x18005f611  mov     qword ptr [rbp+0F0h+Buffer+0Eh], rax
0x18005f618  cmp     edi, 0Dh
0x18005f61b  jnb     short loc_18005F62F
0x18005f61d  mov     eax, edi
0x18005f61f  lea     rcx, ?KdcGlobalNameTypes@@3PAPEAGA; ushort * near * KdcGlobalNameTypes
0x18005f626  mov     rcx, [rcx+rax*8]
0x18005f62a  test    rcx, rcx
0x18005f62d  jnz     short loc_18005F651
0x18005f62f  mov     r9d, edi
0x18005f632  lea     r8, aD; "%d"
0x18005f639  mov     edx, 0Ah; BufferCount
0x18005f63e  lea     rcx, [rbp+0F0h+Buffer]; Buffer
0x18005f645  call    swprintf_s
0x18005f64a  lea     rcx, [rbp+0F0h+Buffer]
0x18005f651  mov     [rsp+1F0h+var_1C0], rcx
0x18005f656  mov     rax, [rbp+0F0h+var_170]
0x18005f65a  mov     [rsp+1F0h+var_1C8], rax
0x18005f65f  mov     dword ptr [rsp+1F0h+var_1D0], 2; unsigned int
0x18005f667  xor     r9d, r9d; void *
0x18005f66a  xor     r8d, r8d; unsigned int
0x18005f66d  mov     edx, 0C000000Bh; unsigned int
0x18005f672  lea     edi, [r9+1]
0x18005f676  mov     ecx, edi; unsigned __int16
0x18005f678  call    ?ReportServiceEvent@@YAKGKKPEAXKZZ; ReportServiceEvent(ushort,ulong,ulong,void *,ulong,...)
0x18005f67d  mov     eax, [rsp+1F0h+var_17C]
0x18005f681  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f688  jmp     short loc_18005F68F
0x18005f68a  mov     edi, 1
0x18005f68f  xor     ebx, ebx
0x18005f691  cmp     cs:byte_1800B2F0A, bl
0x18005f697  jz      short loc_18005F6F4
0x18005f699  cmp     byte ptr cs:word_1800B2F08+1, bl
0x18005f69f  jz      short loc_18005F6F4
0x18005f6a1  lea     rdx, [rbp+0F0h+DestinationString]; struct _UNICODE_STRING *
0x18005f6a5  mov     rcx, [rbp+0F0h+var_C8]; struct _KERB_INTERNAL_NAME *
0x18005f6a9  call    ?KdcMatchCrossForestName@@YAJPEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@@Z; KdcMatchCrossForestName(_KERB_INTERNAL_NAME *,_UNICODE_STRING *)
0x18005f6ae  test    eax, eax
0x18005f6b0  jnz     short loc_18005F6E9
0x18005f6b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f6b9  lea     rax, WPP_GLOBAL_Control
0x18005f6c0  cmp     rcx, rax
0x18005f6c3  jz      short loc_18005F6E2
0x18005f6c5  test    byte ptr [rcx+1Ch], 80h
0x18005f6c9  jz      short loc_18005F6E2
0x18005f6cb  lea     edx, [rbx+0Ch]
0x18005f6ce  lea     r9, [rbp+0F0h+DestinationString]
0x18005f6d2  lea     r8, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids
0x18005f6d9  mov     rcx, [rcx+10h]
0x18005f6dd  call    WPP_SF_Z
0x18005f6e2  mov     rax, [rbp+0F0h+var_138]
0x18005f6e6  mov     [rax], dil
0x18005f6e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f6f0  mov     eax, [rsp+1F0h+var_17C]
0x18005f6f4  lea     rdx, WPP_GLOBAL_Control
0x18005f6fb  cmp     rcx, rdx
0x18005f6fe  jz      short loc_18005F71C
0x18005f700  test    byte ptr [rcx+1Ch], 2
0x18005f704  jz      short loc_18005F71C
0x18005f706  mov     dword ptr [rsp+1F0h+var_1C8], eax
0x18005f70a  mov     dword ptr [rsp+1F0h+var_1D0], r15d
0x18005f70f  mov     r9, [rbp+0F0h+var_170]
0x18005f713  mov     rcx, [rcx+10h]
0x18005f717  call    WPP_SF_SDd
0x18005f71c  test    r12b, r12b
0x18005f71f  jz      loc_18005FC16
0x18005f725  mov     rcx, [rbp+0F0h+var_170]; void *
0x18005f729  call    MIDL_user_free
0x18005f72e  xor     r12d, r12d
0x18005f731  mov     [rbp+0F0h+var_170], r12
0x18005f735  mov     r8, [rbp+0F0h+var_90]; struct _UNICODE_STRING *
0x18005f739  lea     rdx, [rbp+0F0h+DestinationString]; struct _UNICODE_STRING *
0x18005f73d  lea     rcx, [rbp+0F0h+var_170]; unsigned __int16 **
0x18005f741  call    ?KdcBuildNt4Name@@YAJPEAPEAGPEAU_UNICODE_STRING@@1@Z; KdcBuildNt4Name(ushort * *,_UNICODE_STRING *,_UNICODE_STRING *)
0x18005f746  mov     ebx, eax
0x18005f748  test    eax, eax
0x18005f74a  jnz     loc_18005F7F8
0x18005f750  lea     edi, [rax+2]
0x18005f753  mov     [rbp+0F0h+var_150], 100h
0x18005f75a  mov     [rbp+0F0h+var_14C], 201h
0x18005f761  mov     r11d, [rbp+0F0h+var_148]
0x18005f765  jmp     loc_18005F550
0x18005f76a  cmp     eax, 7
0x18005f76d  jnz     short loc_18005F7B7
0x18005f76f  lea     r15, WPP_GLOBAL_Control
0x18005f776  cmp     rcx, r15
0x18005f779  jz      short loc_18005F79E
0x18005f77b  test    byte ptr [rcx+1Ch], 80h
0x18005f77f  jz      short loc_18005F79E
0x18005f781  mov     edx, 0Eh
0x18005f786  mov     r9, r8
0x18005f789  lea     r8, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids
0x18005f790  mov     rcx, [rcx+10h]
0x18005f794  call    WPP_SF_S
0x18005f799  mov     r8, [rsp+1F0h+var_178]
0x18005f79e  mov     rdx, r8; SourceString
0x18005f7a1  lea     rcx, [rbp+0F0h+DestinationString]; DestinationString
0x18005f7a5  call    cs:__imp_RtlInitUnicodeString
0x18005f7ab  mov     rdi, [rbp+0F0h+var_138]
0x18005f7af  mov     byte ptr [rdi], 1
0x18005f7b2  xor     r12d, r12d
0x18005f7b5  jmp     short loc_18005F816
0x18005f7b7  lea     r15, WPP_GLOBAL_Control
0x18005f7be  cmp     rcx, r15
0x18005f7c1  jz      short loc_18005F7E6
0x18005f7c3  test    byte ptr [rcx+1Ch], 80h
0x18005f7c7  jz      short loc_18005F7E6
0x18005f7c9  mov     edx, 0Fh
0x18005f7ce  mov     r9, r8
0x18005f7d1  lea     r8, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids
0x18005f7d8  mov     rcx, [rcx+10h]
0x18005f7dc  call    WPP_SF_S
0x18005f7e1  mov     r8, [rsp+1F0h+var_178]
0x18005f7e6  mov     rdx, r8; SourceString
0x18005f7e9  lea     rcx, [rbp+0F0h+DestinationString]; DestinationString
0x18005f7ed  call    cs:__imp_RtlInitUnicodeString
0x18005f7f3  xor     r12d, r12d
0x18005f7f6  jmp     short loc_18005F812
  ... truncated ...
```
