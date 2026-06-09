# KdcNormalizeWorker(_KERB_INTERNAL_NAME *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong,_SAM_MAPPED_ATTRIBUTE_SET *,uchar *,_UNICODE_STRING *,_KDC_TICKET_INFO *,KERB_EXT_ERROR *,void * *,ulong,ulong,_USER_INTERNAL6_INFORMATION * *,_SID_AND_ATTRIBUTES_LIST *)

- ea: `0x1800635a8`
- end: `0x1800648d1`
- name: `?KdcNormalizeWorker@@YAJPEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@11KKPEAU_SAM_MAPPED_ATTRIBUTE_SET@@PEAE1PEAU_KDC_TICKET_INFO@@PEAUKERB_EXT_ERROR@@PEAPEAXKKPEAPEAU_USER_INTERNAL6_INFORMATION@@PEAU_SID_AND_ATTRIBUTES_LIST@@@Z`
- size: `4905`
- prototype: `__int64 __usercall@<rax>(struct _KERB_INTERNAL_NAME *@<rcx>, struct _UNICODE_STRING *@<rdx>, struct _UNICODE_STRING *@<r8>, struct _UNICODE_STRING *@<r9>, unsigned int, unsigned int, struct _SAM_MAPPED_ATTRIBUTE_SET *, unsigned __int8 *, struct _UNICODE_STRING *, struct _KDC_TICKET_INFO *, struct KERB_EXT_ERROR *, void **, unsigned int, unsigned int, struct _USER_INTERNAL6_INFORMATION **, struct _SID_AND_ATTRIBUTES_LIST *)`
- caller_count: `1`
- callee_count: `21`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006349c`

## callees

- `0x18000a82c`
- `0x18000a860`
- `0x1800101c4`
- `0x1800101ec`
- `0x18001ff94`
- `0x180020230`
- `0x180020380`
- `0x180057634`
- `0x180057fb4`
- `0x18005ad20`
- `0x18005b97c`
- `0x18005c2a4`
- `0x18005f318`
- `0x180060b5c`
- `0x1800635a8`
- `0x1800648d8`
- `0x1800661e0`
- `0x180072338`
- `0x18007bef4`
- `0x18007d3e8`
- `0x18007dc20`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x180063b3e`
- `ntdll!RtlEqualUnicodeString` at `0x180063f8d`
- `ntdll!RtlEqualUnicodeString` at `0x1800643e8`
- `ntdll!RtlEqualUnicodeString` at `0x180063b3e`
- `ntdll!RtlEqualUnicodeString` at `0x180063f8d`
- `ntdll!RtlEqualUnicodeString` at `0x1800643e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KdcNormalizeWorker(
        struct _KERB_INTERNAL_NAME *a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        unsigned int a5,
        unsigned int a6,
        struct _SAM_MAPPED_ATTRIBUTE_SET *a7,
        unsigned __int8 *a8,
        struct _UNICODE_STRING *a9,
        struct _KDC_TICKET_INFO *a10,
        struct KERB_EXT_ERROR *a11,
        void **a12,
        unsigned int a13,
        unsigned int a14,
        struct _USER_INTERNAL6_INFORMATION **a15,
        struct _SID_AND_ATTRIBUTES_LIST *a16)
{
  __m128i v17; // xmm6
  __int64 v18; // rax
  int v19; // r8d
  int v20; // r10d
  CSecurityData *v21; // rcx
  __int64 v22; // rdx
  UNICODE_STRING *v23; // rbx
  bool v24; // r13
  char v25; // r12
  char v26; // si
  __int16 v27; // ax
  unsigned int v28; // r9d
  unsigned int v29; // edx
  int v30; // r8d
  __int64 v31; // rdx
  struct _UNICODE_STRING v32; // xmm1
  unsigned __int16 v33; // dx
  int v34; // eax
  int v35; // eax
  char v36; // al
  int v37; // r8d
  int v38; // r8d
  int v39; // r8d
  int v40; // r8d
  int v41; // r8d
  struct _UNICODE_STRING *v42; // rax
  struct _UNICODE_STRING v43; // xmm0
  BOOLEAN v44; // al
  unsigned __int64 v45; // rcx
  __m128i v46; // xmm0
  unsigned __int16 v47; // dx
  unsigned int TicketInfo; // ebx
  CSecurityData *v49; // rcx
  unsigned __int16 v50; // r8
  __int64 v51; // rdx
  unsigned __int64 v52; // xmm0_8
  bool v53; // zf
  WCHAR *v54; // rdx
  unsigned __int64 v55; // rcx
  char v56; // si
  struct _UNICODE_STRING *v57; // rax
  struct _UNICODE_STRING *v58; // r8
  int v59; // esi
  __int64 v60; // rax
  __int16 v61; // r8
  USHORT v62; // r8
  CSecurityData *v63; // rcx
  unsigned __int8 IsOurRealm; // al
  int v65; // ecx
  unsigned int v66; // eax
  struct KERB_EXT_ERROR *v67; // r13
  struct _KDC_TICKET_INFO *v68; // rsi
  int v69; // ecx
  char v70; // si
  int ReferralTarget; // eax
  CSecurityData *v72; // rcx
  CSecurityData *v73; // rcx
  unsigned int v74; // esi
  unsigned __int8 v75; // si
  CSecurityData *v76; // rcx
  __int64 v77; // rdx
  unsigned __int8 v79; // [rsp+20h] [rbp-F0h]
  struct KERB_EXT_ERROR *v80; // [rsp+30h] [rbp-E0h]
  char v81; // [rsp+90h] [rbp-80h]
  int v82; // [rsp+94h] [rbp-7Ch]
  unsigned __int8 v83; // [rsp+98h] [rbp-78h] BYREF
  unsigned __int8 v84; // [rsp+99h] [rbp-77h] BYREF
  unsigned __int8 v85; // [rsp+9Ah] [rbp-76h] BYREF
  char v86; // [rsp+9Bh] [rbp-75h]
  unsigned int v87; // [rsp+9Ch] [rbp-74h]
  struct _UNICODE_STRING v88; // [rsp+A0h] [rbp-70h] BYREF
  int v89; // [rsp+B0h] [rbp-60h]
  UNICODE_STRING String1; // [rsp+C0h] [rbp-50h] BYREF
  struct _UNICODE_STRING v91; // [rsp+D0h] [rbp-40h] BYREF
  struct _UNICODE_STRING v92; // [rsp+E0h] [rbp-30h] BYREF
  __int128 v93; // [rsp+F0h] [rbp-20h] BYREF
  _BYTE v94[32]; // [rsp+100h] [rbp-10h] BYREF
  char v95[32]; // [rsp+120h] [rbp+10h] BYREF
  char v96; // [rsp+1A0h] [rbp+90h]

  if ( !a8 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  if ( !a9 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  if ( !a10 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  if ( a12 && *a12 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  if ( a15 && *a15 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  if ( a16 && *(_DWORD *)a16 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  v83 = 0;
  v85 = 1;
  v84 = 0;
  String1 = 0;
  v88 = 0;
  v17 = 0;
  v93 = 0;
  v91 = 0;
  v92 = 0;
  v18 = lambda_21c4ea7e66c71d2f543b9ee2e639597c_::_lambda_21c4ea7e66c71d2f543b9ee2e639597c_(v95, &v91, &v92, &v93);
  wil::scope_exit__lambda_21c4ea7e66c71d2f543b9ee2e639597c___(v94, v18);
  *a8 = 0;
  if ( !a1 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
      || ((unsigned __int8)v20 & *((_BYTE *)WPP_GLOBAL_Control + 28)) == 0 )
    {
      goto LABEL_294;
    }
    v22 = (unsigned int)(v20 + 22);
    goto LABEL_293;
  }
  if ( !*((_WORD *)a1 + 1) || (v23 = (UNICODE_STRING *)((char *)a1 + 8), !*((_WORD *)a1 + 4)) )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
      || ((unsigned __int8)v20 & *((_BYTE *)WPP_GLOBAL_Control + 28)) == 0 )
    {
      goto LABEL_294;
    }
    v22 = 24;
    goto LABEL_293;
  }
  v96 = 0;
  v81 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  LOBYTE(v89) = 0;
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
    {
      WPP_SF_DDqZZZDq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a5,
        v19,
        a13,
        a14,
        (char)a1,
        (__int64)a2,
        (__int64)a3,
        (__int64)a4,
        a5,
        (char)a7);
      v21 = WPP_GLOBAL_Control;
    }
    if ( v21 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)v21 + 7) & 0x2000) != 0 )
    {
      WPP_SF__KERB_NAME_(*((_QWORD *)v21 + 2), 26, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, a1);
      v21 = WPP_GLOBAL_Control;
    }
  }
  v27 = a5;
  v28 = a5 >> 4;
  LOBYTE(v28) = (a5 & 0x10) != 0;
  v87 = v28;
  v29 = (a5 & 0x400) << 9;
  v82 = v29;
  v30 = *(__int16 *)a1;
  if ( v30 > 1 )
  {
    v37 = v30 - 2;
    if ( !v37 )
      goto LABEL_62;
    v38 = v37 - 1;
    if ( !v38 )
      goto LABEL_62;
    v39 = v38 - 1;
    if ( !v39 )
    {
LABEL_110:
      v81 = 1;
      v96 = 1;
      v35 = (a5 & 0x400) << 9;
      goto LABEL_111;
    }
    v40 = v39 - 1;
    if ( !v40 )
    {
      if ( v21 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)v21 + 2), 35, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, 5);
      goto LABEL_294;
    }
    v41 = v40 - 1;
    if ( !v41 )
      goto LABEL_58;
    if ( v41 != 4 )
    {
LABEL_62:
      v27 = a5;
      goto LABEL_63;
    }
    if ( *((_WORD *)a1 + 1) == 1 )
    {
      String1 = *v23;
      v81 = 1;
      v17 = (__m128i)String1;
      v26 = 1;
      v24 = 1;
      v88 = DomainName2;
      v82 = (a5 & 0x400) << 9;
      goto LABEL_112;
    }
    if ( v21 == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)v21 + 28) & 1) == 0 )
      goto LABEL_294;
    v22 = 31;
LABEL_293:
    WPP_SF_(*((_QWORD *)v21 + 2), v22, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
    goto LABEL_294;
  }
  if ( v30 == 1 )
    goto LABEL_63;
  if ( v30 != -132 && v30 != -131 )
  {
    if ( v30 != -130 )
    {
      if ( v30 == -129 )
      {
        if ( v21 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 2) != 0 )
        {
          WPP_SF_d(*((_QWORD *)v21 + 2), 32, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, 4294967167LL);
          v21 = WPP_GLOBAL_Control;
        }
      }
      else if ( v30 != -128 )
      {
        goto LABEL_63;
      }
      if ( *((_WORD *)a1 + 1) > 2u )
      {
        if ( v21 == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)v21 + 28) & 1) == 0 )
          goto LABEL_294;
        v31 = 33;
LABEL_116:
        WPP_SF__KERB_NAME_(*((_QWORD *)v21 + 2), v31, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, a1);
LABEL_294:
        TicketInfo = 6;
        goto LABEL_295;
      }
      if ( *((_WORD *)a1 + 1) == 2 )
      {
        if ( v21 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)v21 + 2), 34, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
        String1 = *v23;
        v32 = *(struct _UNICODE_STRING *)((char *)a1 + 24);
        v88 = v32;
        v33 = _mm_cvtsi128_si32((__m128i)v32);
        if ( v33
          && *(_WORD *)(_mm_srli_si128((__m128i)v32, 8).m128i_u64[0] + 2 * ((unsigned __int64)v33 >> 1) - 2) == 46 )
        {
          v88.Length = v33 - 2;
        }
      }
      else
      {
        v17 = *(__m128i *)v23;
        v26 = 1;
      }
      v34 = (a5 & 0x400) << 9;
      if ( (a5 & 0x80u) != 0 )
      {
        v26 = 0;
        v24 = 1;
        v34 = v82 | 0x10;
        String1 = *v23;
        v88 = DomainName2;
      }
      v82 = v34;
      LOBYTE(v87) = v24;
      if ( (a5 & 0x200) == 0 )
      {
LABEL_112:
        if ( KdcRecursing(a1, &v83) )
        {
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_294;
          }
          v31 = 36;
          goto LABEL_116;
        }
        if ( v83 )
        {
          v49 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
LABEL_122:
            if ( v25 )
            {
              if ( v49 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)v49 + 7) & 0x40000) != 0 )
                WPP_SF_(*((_QWORD *)v49 + 2), 38, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
              TicketInfo = KdcGetTicketInfo(&String1, 0x2000u, a6, 0, 0, a10, a11, a12, a13, a14 | 0x20, a15, a16, a7);
              if ( TicketInfo
                && WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
              }
              goto LABEL_295;
            }
            v86 = v89;
            if ( v26 )
            {
              v50 = _mm_cvtsi128_si32(v17);
              v24 = 1;
              v51 = (v50 >> 1) - 1;
              if ( v50 >> 1 == 1 )
              {
LABEL_136:
                v88 = DomainName2;
                String1 = (UNICODE_STRING)v17;
                v54 = (WCHAR *)_mm_srli_si128((__m128i)DomainName2, 8).m128i_u64[0];
                v55 = (unsigned int)_mm_cvtsi128_si32((__m128i)DomainName2);
              }
              else
              {
                v52 = _mm_srli_si128(v17, 8).m128i_u64[0];
                while ( *(_WORD *)(v52 + 2 * v51) != 92 && *(_WORD *)(v52 + 2 * v51) != 64 )
                {
                  v53 = (_DWORD)v51 == 1;
                  v51 = (unsigned int)(v51 - 1);
                  if ( v53 )
                    goto LABEL_136;
                }
                v55 = (unsigned __int16)v51;
                LOWORD(v55) = 2 * v51;
                v60 = (unsigned int)(v51 + 1);
                v61 = v50 - 2 * v51;
                if ( *(_WORD *)(v52 + 2 * v51) == 64 )
                {
                  String1 = (UNICODE_STRING)v17;
                  String1.Length = 2 * v51;
                  String1.MaximumLength = 2 * v51;
                  v54 = (WCHAR *)(v52 + 2 * v60);
                  v88.Buffer = v54;
                  v62 = v61 - 2;
                  v55 = v62;
                  v88.Length = v62;
                  v88.MaximumLength = v62;
                  if ( v62 && v54[((unsigned __int64)v62 >> 1) - 1] == 46 )
                  {
                    LOWORD(v55) = v62 - 2;
                    v88.Length = v62 - 2;
                  }
                }
                else
                {
                  v88 = (struct _UNICODE_STRING)v17;
                  v88.Length = 2 * v51;
                  v88.MaximumLength = 2 * v51;
                  String1.Buffer = (PWSTR)(v52 + 2 * v60);
                  String1.Length = v61 - 2;
                  String1.MaximumLength = v61 - 2;
                  v54 = (WCHAR *)v17.m128i_i64[1];
                }
              }
              if ( (_WORD)v55 && v54[((unsigned __int64)(unsigned __int16)v55 >> 1) - 1] == 46 )
              {
                LOWORD(v55) = v55 - 2;
                v88.Length = v55;
              }
              if ( !CSecurityData::IsOurRealm((CSecurityData *)v55, &v88) )
              {
                LOBYTE(v89) = 1;
                v24 = 0;
                v49 = WPP_GLOBAL_Control;
LABEL_142:
                v56 = a5;
                goto LABEL_143;
              }
              if ( !RtlEqualUnicodeString(&String1, &String2, 1u) )
              {
                v49 = WPP_GLOBAL_Control;
                goto LABEL_169;
              }
              if ( a2 )
              {
                v88 = *a2;
                IsOurRealm = CSecurityData::IsOurRealm(v63, &v88);
                v65 = (unsigned __int8)v89;
                if ( !IsOurRealm )
                  v65 = 1;
                v89 = v65;
                v24 = IsOurRealm != 0;
              }
              v49 = WPP_GLOBAL_Control;
            }
            if ( !v24 )
              goto LABEL_142;
LABEL_169:
            v56 = a5;
            if ( v96 && (a5 & 2) == 0 && *((_WORD *)a1 + 1) == 1 )
            {
              if ( v49 != (CSecurityData *)&WPP_GLOBAL_Control && *((char *)v49 + 28) < 0 )
                WPP_SF_(*((_QWORD *)v49 + 2), 40, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
              v66 = KdcGetTicketInfo(&String1, v82, a6, 0, 0, a10, a11, a12, a13, a14, a15, a16, a7);
              if ( !v66 )
                goto LABEL_275;
              if ( v66 == 27 || v66 == 29 || v66 == -2147483642 )
                goto LABEL_279;
              v49 = WPP_GLOBAL_Control;
            }
LABEL_143:
            v57 = 0;
            if ( !v81 )
            {
              v59 = v56 & 2;
              goto LABEL_202;
            }
            if ( v49 != (CSecurityData *)&WPP_GLOBAL_Control && *((char *)v49 + 28) < 0 )
            {
              WPP_SF_(*((_QWORD *)v49 + 2), 41, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
              v49 = WPP_GLOBAL_Control;
            }
            if ( v96 && (v56 & 2) == 0 && *((_WORD *)a1 + 1) == 1 )
            {
              if ( v49 != (CSecurityData *)&WPP_GLOBAL_Control && *((char *)v49 + 28) < 0 )
                WPP_SF_(*((_QWORD *)v49 + 2), 42, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
              v58 = a3;
              if ( !a3 )
                v58 = &DomainName2;
              v59 = 0;
            }
            else
            {
              v59 = v56 & 2;
              if ( v59 || !v96 )
              {
                v58 = 0;
              }
              else
              {
                v58 = a3;
                if ( !a3 )
                  v58 = &DomainName2;
              }
            }
            v66 = KerbConvertKdcNameToString(&v91, a1, v58);
            if ( v66 )
              goto LABEL_279;
            if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
              WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, &v91);
            v66 = KdcGetTicketInfo(&v91, v59 != 0 ? 64 : 512, a6, 0, 0, a10, a11, a12, a13, a14, a15, a16, a7);
            if ( !v66 )
              goto LABEL_275;
            if ( (a5 & 1) != 0 && v66 == 6 )
            {
              if ( *((_WORD *)a1 + 1) != 2 || *(_WORD *)a1 != 2 )
              {
LABEL_200:
                v49 = WPP_GLOBAL_Control;
                v57 = 0;
LABEL_202:
                if ( !v24 || v96 && !v59 && *((_WORD *)a1 + 1) == 1 )
                {
                  v68 = a10;
                  v67 = a11;
                }
                else
                {
                  if ( v49 != (CSecurityData *)&WPP_GLOBAL_Control && *((char *)v49 + 28) < 0 )
                    WPP_SF_(*((_QWORD *)v49 + 2), 44, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
                  v67 = a11;
                  v68 = a10;
                  v66 = KdcGetTicketInfo(&String1, v82, a6, 0, 0, a10, a11, a12, a13, a14, a15, a16, a7);
                  if ( !v66 )
                    goto LABEL_275;
                  if ( v66 == -2147483642 )
                    goto LABEL_279;
                  if ( v66 <= 0x1D )
                  {
                    v69 = 671092736;
                    if ( _bittest(&v69, v66) )
                      goto LABEL_279;
                  }
                  v49 = WPP_GLOBAL_Control;
                  v57 = 0;
                }
                if ( (_BYTE)v89 && !KdcGlobalCDC )
                {
                  v70 = 0;
                  if ( v49 != (CSecurityData *)&WPP_GLOBAL_Control && *((char *)v49 + 28) < 0 )
                    WPP_SF_(*((_QWORD *)v49 + 2), 45, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
                  if ( !RtlEqualUnicodeString(&String1, &String2, 1u) )
                    *a8 = 1;
                  if ( (a5 & 4) == 0 )
                  {
                    if ( *a8 )
                    {
                      v21 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
                        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      {
                        goto LABEL_294;
                      }
                      v22 = 46;
                      goto LABEL_293;
                    }
                    v70 = 1;
                  }
                  v79 = v70;
                  v68 = a10;
                  ReferralTarget = KdcFindReferralTarget(a10, a9, v67, &v88, v79, a5);
                  if ( ReferralTarget )
                  {
                    if ( ReferralTarget == 29 )
                      goto LABEL_264;
                  }
                  else
                  {
                    if ( !a4 || CSecurityData::IsOurRealm(v72, a4) || (*((_DWORD *)a10 + 10) & 0x400) != 0 )
                    {
                      if ( !(unsigned __int8)KerbCompareUnicodeRealmNames(a9, &v88) )
                        *a8 = 1;
                      goto LABEL_275;
                    }
                    v73 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control )
                    {
                      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      {
                        WPP_SF_(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          47,
                          WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
                        v73 = WPP_GLOBAL_Control;
                      }
                      if ( v73 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v73 + 28) & 1) != 0 )
                        WPP_SF_(*((_QWORD *)v73 + 2), 48, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
                    }
                    FreeTicketInfo(a10);
                    KerbFreeString(a9);
                  }
                  v57 = 0;
                  v49 = WPP_GLOBAL_Control;
                }
                if ( !(_BYTE)v87 || (a5 & 4) == 0 )
                  goto LABEL_294;
                if ( !v91.Buffer )
                {
                  if ( !v86 && (v82 & 0x810) == 0 )
                  {
                    v57 = a3;
                    if ( !a3 )
                      v57 = &DomainName2;
                  }
                  v74 = KerbConvertKdcNameToString(&v91, a1, v57);
                  v49 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
                    && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
                    v49 = WPP_GLOBAL_Control;
                  }
                  if ( v74 )
                  {
LABEL_254:
                    TicketInfo = v74;
                    goto LABEL_295;
                  }
                  v68 = a10;
                }
                if ( v49 != (CSecurityData *)&WPP_GLOBAL_Control && *((char *)v49 + 28) < 0 )
                  WPP_SF_Z(*((_QWORD *)v49 + 2), 50, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, &v91);
                v80 = v68;
                v75 = v83;
                v66 = KdcCrackNameAtGC(&v91, a1, a5, a6, v83, a9, v80, &v85, a8, &v84, v67, a12, a13, a14, a15, a16, a7);
                if ( !v66 )
                {
                  v76 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
                    || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
                  {
                    goto LABEL_275;
                  }
                  v77 = 51;
                  goto LABEL_274;
                }
                if ( v66 == 29 )
                {
LABEL_264:
                  TicketInfo = 29;
                  goto LABEL_295;
                }
                if ( (a5 & 1) != 0 && v66 == 6 && *((_WORD *)a1 + 1) == 2 && *(_WORD *)a1 == 2 )
                {
                  KerbFreeString(&v92);
                  v66 = KerbConvertKdcNameToString(&v92, a1, 0);
                  if ( v66 )
                    goto LABEL_279;
                  v66 = KdcCrackNameAtGC(
                          &v92,
                          a1,
                          a5 & 0xFFFFFFBC | 2,
                          a6,
                          v75,
                          a9,
                          a10,
                          &v85,
                          a8,
                          &v84,
                          v67,
                          a12,
                          a13,
                          a14,
                          a15,
                          a16,
                          a7);
                  if ( !v66 )
                  {
                    v76 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
                      || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
                    {
                      goto LABEL_275;
                    }
                    v77 = 52;
LABEL_274:
                    WPP_SF_(*((_QWORD *)v76 + 2), v77, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
                    goto LABEL_275;
                  }
                }
                if ( !KdcGlobalCDC )
                {
                  if ( !v86 || v75 )
                    goto LABEL_294;
                  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
                    && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
                  }
                  v74 = 0;
                  if ( KdcCheckForCrossForestReferral(a10, a9, v67, &v88, a5) )
                    goto LABEL_294;
                  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
                    && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                  {
                    WPP_SF_ZZ(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      54,
                      (unsigned int)WPP_b168486f65343579948eb0cc9cf7c178_Traceguids,
                      (_DWORD)a9,
                      (__int64)&v88);
                  }
                  *a8 = 1;
                  goto LABEL_254;
                }
                if ( v66 != -2147483642 )
                  v66 = 6;
LABEL_279:
                TicketInfo = v66;
                goto LABEL_295;
              }
              v66 = KerbConvertKdcNameToString(&v92, a1, 0);
              if ( v66 )
                goto LABEL_279;
              v66 = KdcGetTicketInfo(&v92, 0x40u, a6, 0, 0, a10, a11, a12, a13, a14, a15, a16, a7);
              if ( !v66 )
              {
LABEL_275:
                TicketInfo = 0;
                goto LABEL_295;
              }
            }
            if ( v66 == 27 || v66 == 29 || v66 == -2147483642 )
              goto LABEL_279;
            goto LABEL_200;
          }
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
        }
        v49 = WPP_GLOBAL_Control;
        goto LABEL_122;
      }
      v26 = 0;
      v24 = 1;
      v35 = v34 | 0x20000;
      String1 = *v23;
      v88 = DomainName2;
LABEL_111:
      v82 = v35;
      goto LABEL_112;
    }
    if ( v21 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v21 + 2), 30, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, 4294967166LL);
      v29 = (a5 & 0x400) << 9;
      v28 = v87;
    }
LABEL_58:
    v82 = v29 | 0x800;
    String1 = *v23;
    v24 = 1;
    v88 = DomainName2;
    v87 = v28;
    goto LABEL_112;
  }
  if ( v21 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v21 + 2), 27, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, (unsigned int)v30);
    v21 = WPP_GLOBAL_Control;
    goto LABEL_62;
  }
LABEL_63:
  if ( *((_WORD *)a1 + 1) == 1 )
  {
    if ( (v27 & 0x100) != 0 )
    {
      v25 = 1;
      v36 = 0;
LABEL_88:
      String1 = *v23;
      if ( a3 )
        v43 = *a3;
      else
        v43 = DomainName2;
      v88 = v43;
      v81 = v36;
      goto LABEL_112;
    }
    v42 = a3;
    if ( a3 )
    {
      if ( !CSecurityData::IsOurRealm(v21, a3) )
      {
LABEL_87:
        v36 = 1;
        v96 = 1;
        goto LABEL_88;
      }
      v21 = WPP_GLOBAL_Control;
      v42 = a3;
    }
    if ( v21 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 4) != 0 )
      WPP_SF_Z(*((_QWORD *)v21 + 2), 28, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, v42);
    v24 = 1;
    goto LABEL_87;
  }
  if ( *((_WORD *)a1 + 1) != 2 )
    goto LABEL_110;
  v44 = RtlEqualUnicodeString((PCUNICODE_STRING)((char *)a1 + 8), &String2, 1u);
  v45 = 0;
  if ( !v44 )
    goto LABEL_110;
  if ( a2 && CSecurityData::IsOurRealm(0, (struct _UNICODE_STRING *)((char *)a1 + 24)) )
    v46 = *(__m128i *)a2;
  else
    v46 = *(__m128i *)((char *)a1 + 24);
  v88 = (struct _UNICODE_STRING)v46;
  v47 = _mm_cvtsi128_si32(v46);
  if ( v47 )
  {
    v45 = (unsigned __int64)v47 >> 1;
    if ( *(_WORD *)(_mm_srli_si128(v46, 8).m128i_u64[0] + 2 * v45 - 2) == 46 )
      v88.Length = v47 - 2;
  }
  if ( CSecurityData::IsOurRealm((CSecurityData *)v45, &v88) )
  {
    v24 = 1;
    goto LABEL_109;
  }
  if ( !KdcGlobalCDC )
  {
    LOBYTE(v89) = 1;
LABEL_109:
    String1 = *(UNICODE_STRING *)((char *)a1 + 8);
    goto LABEL_112;
  }
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
  }
  TicketInfo = -2147483642;
LABEL_295:
  wil::details::lambda_call__lambda_53504e1e7a1eb439dfdd694e75003677___::_lambda_call__lambda_53504e1e7a1eb439dfdd694e75003677___(v94);
  return TicketInfo;
}

```

## disassembly

```asm
0x1800635a8  mov     rax, rsp
0x1800635ab  mov     [rax+20h], r9
0x1800635af  mov     [rax+18h], r8
0x1800635b3  mov     [rax+10h], rdx
0x1800635b7  push    rbp
0x1800635b8  push    rbx
0x1800635b9  push    rsi
0x1800635ba  push    rdi
0x1800635bb  push    r12
0x1800635bd  push    r13
0x1800635bf  push    r14
0x1800635c1  push    r15
0x1800635c3  lea     rbp, [rsp-48h]
0x1800635c8  sub     rsp, 158h
0x1800635cf  movaps  xmmword ptr [rax-58h], xmm6
0x1800635d3  mov     r15, rcx
0x1800635d6  xor     edi, edi
0x1800635d8  mov     rbx, [rbp+80h+arg_38]
0x1800635df  test    rbx, rbx
0x1800635e2  jnz     short loc_1800635E9
0x1800635e4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800635e9  cmp     [rbp+80h+arg_40], rdi
0x1800635f0  jnz     short loc_1800635F7
0x1800635f2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800635f7  cmp     [rbp+80h+arg_48], rdi
0x1800635fe  jnz     short loc_180063605
0x180063600  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180063605  mov     rax, [rbp+80h+arg_58]
0x18006360c  test    rax, rax
0x18006360f  jz      short loc_18006361B
0x180063611  cmp     [rax], rdi
0x180063614  jz      short loc_18006361B
0x180063616  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006361b  mov     rax, [rbp+80h+arg_70]
0x180063622  test    rax, rax
0x180063625  jz      short loc_180063631
0x180063627  cmp     [rax], rdi
0x18006362a  jz      short loc_180063631
0x18006362c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180063631  mov     rax, [rbp+80h+arg_78]
0x180063638  test    rax, rax
0x18006363b  jz      short loc_180063646
0x18006363d  cmp     [rax], edi
0x18006363f  jz      short loc_180063646
0x180063641  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180063646  mov     [rbp+80h+var_F8], dil
0x18006364a  mov     r10d, 1
0x180063650  mov     [rbp+80h+var_F6], r10b
0x180063654  mov     [rbp+80h+var_F7], dil
0x180063658  xorps   xmm0, xmm0
0x18006365b  movups  xmmword ptr [rbp+80h+String1.Length], xmm0
0x18006365f  xorps   xmm1, xmm1
0x180063662  movups  xmmword ptr [rbp+80h+var_F0.Length], xmm1
0x180063666  xorps   xmm6, xmm6
0x180063669  movups  [rbp+80h+var_A0], xmm0
0x18006366d  movups  xmmword ptr [rbp+80h+var_C0.Length], xmm1
0x180063671  movups  xmmword ptr [rbp+80h+var_B0.Length], xmm0
0x180063675  lea     r9, [rbp+80h+var_A0]
0x180063679  lea     r8, [rbp+80h+var_B0]
0x18006367d  lea     rdx, [rbp+80h+var_C0]
0x180063681  lea     rcx, [rbp+80h+var_70]
0x180063685  call    _lambda_21c4ea7e66c71d2f543b9ee2e639597c____lambda_21c4ea7e66c71d2f543b9ee2e639597c_
0x18006368a  mov     rdx, rax
0x18006368d  lea     rcx, [rbp+80h+var_90]
0x180063691  call    wil__scope_exit__lambda_21c4ea7e66c71d2f543b9ee2e639597c___
0x180063696  nop
0x180063697  mov     [rbx], dil
0x18006369a  test    r15, r15
0x18006369d  jnz     short loc_1800636C9
0x18006369f  lea     rdi, WPP_GLOBAL_Control
0x1800636a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800636ad  cmp     rcx, rdi
0x1800636b0  jz      loc_1800648A5
0x1800636b6  test    [rcx+1Ch], r10b
0x1800636ba  jz      loc_1800648A5
0x1800636c0  lea     edx, [r10+16h]
0x1800636c4  jmp     loc_180064895
0x1800636c9  cmp     [r15+2], di
0x1800636ce  jz      loc_180064877
0x1800636d4  lea     rbx, [r15+8]
0x1800636d8  cmp     [rbx], di
0x1800636db  jz      loc_180064877
0x1800636e1  mov     [rbp+80h+arg_0], dil
0x1800636e8  mov     [rbp+80h+var_100], dil
0x1800636ec  mov     r13b, dil
0x1800636ef  mov     r12b, dil
0x1800636f2  mov     sil, dil
0x1800636f5  mov     byte ptr [rbp+80h+var_E0], dil
0x1800636f9  lea     rdi, WPP_GLOBAL_Control
0x180063700  lea     r14, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids
0x180063707  mov     rcx, cs:WPP_GLOBAL_Control
0x18006370e  cmp     rcx, rdi
0x180063711  jz      loc_1800637A9
0x180063717  test    dword ptr [rcx+1Ch], 2000h
0x18006371e  jz      short loc_180063780
0x180063720  mov     rax, [rbp+80h+arg_30]
0x180063727  mov     [rsp+190h+var_140], rax
0x18006372c  mov     edx, [rbp+80h+arg_20]
0x180063732  mov     dword ptr [rsp+190h+var_148], edx
0x180063736  mov     rax, [rbp+80h+arg_18]
0x18006373d  mov     [rsp+190h+var_150], rax
0x180063742  mov     rax, [rbp+80h+arg_10]
0x180063749  mov     [rsp+190h+var_158], rax
0x18006374e  mov     rax, [rbp+80h+arg_8]
0x180063755  mov     [rsp+190h+var_160], rax
0x18006375a  mov     [rsp+190h+var_168], r15
0x18006375f  mov     eax, [rbp+80h+arg_68]
0x180063765  mov     dword ptr [rsp+190h+var_170], eax
0x180063769  mov     r9d, [rbp+80h+arg_60]
0x180063770  mov     rcx, [rcx+10h]
0x180063774  call    WPP_SF_DDqZZZDq
0x180063779  mov     rcx, cs:WPP_GLOBAL_Control
0x180063780  cmp     rcx, rdi
0x180063783  jz      short loc_1800637A9
0x180063785  test    dword ptr [rcx+1Ch], 2000h
0x18006378c  jz      short loc_1800637A9
0x18006378e  mov     edx, 1Ah
0x180063793  mov     r9, r15
0x180063796  mov     r8, r14
0x180063799  mov     rcx, [rcx+10h]
0x18006379d  call    WPP_SF__KERB_NAME_
0x1800637a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800637a9  mov     eax, [rbp+80h+arg_20]
0x1800637af  mov     r9d, eax
0x1800637b2  shr     r9d, 4
0x1800637b6  mov     r10d, 1
0x1800637bc  and     r9b, r10b
0x1800637bf  mov     [rbp+80h+var_F4], r9d
0x1800637c3  mov     edx, eax
0x1800637c5  and     edx, 400h
0x1800637cb  shl     edx, 9
0x1800637ce  mov     [rbp+80h+var_FC], edx
0x1800637d1  movsx   r8d, word ptr [r15]
0x1800637d5  lea     r11d, [r10+1]
0x1800637d9  cmp     r8d, r10d
0x1800637dc  jg      loc_1800639ED
0x1800637e2  jz      loc_1800639CD
0x1800637e8  cmp     r8d, 0FFFFFF7Ch
0x1800637ef  jz      loc_180063997
0x1800637f5  cmp     r8d, 0FFFFFF7Dh
0x1800637fc  jz      loc_180063997
0x180063802  mov     r11d, 0FFFFFF7Eh
0x180063808  cmp     r8d, r11d
0x18006380b  jz      loc_180063944
0x180063811  lea     r9d, [r11+1]
0x180063815  cmp     r8d, r9d
0x180063818  jz      short loc_180063829
0x18006381a  cmp     r8d, 0FFFFFF80h
0x18006381e  jz      short loc_180063852
0x180063820  lea     r11d, [r10+1]
0x180063824  jmp     loc_1800639CD
0x180063829  cmp     rcx, rdi
0x18006382c  jz      short loc_180063852
0x18006382e  test    byte ptr [rcx+1Ch], 2
0x180063832  jz      short loc_180063852
0x180063834  mov     edx, 20h ; ' '
0x180063839  mov     r8, r14
0x18006383c  mov     rcx, [rcx+10h]
0x180063840  call    WPP_SF_d
0x180063845  mov     rcx, cs:WPP_GLOBAL_Control
0x18006384c  mov     r10d, 1
0x180063852  mov     r9d, 2
0x180063858  cmp     [r15+2], r9w
0x18006385d  jbe     short loc_18006387B
0x18006385f  cmp     rcx, rdi
0x180063862  jz      loc_1800648A5
0x180063868  test    [rcx+1Ch], r10b
0x18006386c  jz      loc_1800648A5
0x180063872  lea     edx, [r9+1Fh]
0x180063876  jmp     loc_180063C58
0x18006387b  jnz     short loc_1800638E4
0x18006387d  cmp     rcx, rdi
0x180063880  jz      short loc_180063899
0x180063882  test    [rcx+1Ch], r9b
0x180063886  jz      short loc_180063899
0x180063888  mov     edx, 22h ; '"'
0x18006388d  mov     r8, r14
0x180063890  mov     rcx, [rcx+10h]
0x180063894  call    WPP_SF_
0x180063899  movups  xmm0, xmmword ptr [rbx]
0x18006389c  movdqu  xmmword ptr [rbp+80h+String1.Length], xmm0
0x1800638a1  movups  xmm1, xmmword ptr [r15+18h]
0x1800638a6  movaps  xmmword ptr [rbp+80h+var_F0.Length], xmm1
0x1800638aa  movd    edx, xmm1
0x1800638ae  xor     r8d, r8d
0x1800638b1  lea     r10d, [r8+1]
0x1800638b5  test    dx, dx
0x1800638b8  jz      short loc_1800638ED
0x1800638ba  movzx   ecx, dx
0x1800638bd  shr     rcx, 1
0x1800638c0  psrldq  xmm1, 8
0x1800638c5  movq    rax, xmm1
0x1800638ca  lea     r9d, [r8+2Eh]
0x1800638ce  cmp     [rax+rcx*2-2], r9w
0x1800638d4  jnz     short loc_1800638ED
0x1800638d6  mov     eax, 0FFFEh
0x1800638db  add     dx, ax
0x1800638de  mov     [rbp+80h+var_F0.Length], dx
0x1800638e2  jmp     short loc_1800638ED
0x1800638e4  movups  xmm6, xmmword ptr [rbx]
0x1800638e7  mov     sil, r10b
0x1800638ea  xor     r8d, r8d
0x1800638ed  movaps  xmm1, xmmword ptr cs:DomainName2.Length
0x1800638f4  mov     ecx, [rbp+80h+arg_20]
0x1800638fa  mov     eax, [rbp+80h+var_FC]
0x1800638fd  test    cl, cl
0x1800638ff  jns     short loc_180063917
0x180063901  mov     sil, r8b
0x180063904  mov     r13b, r10b
0x180063907  or      eax, 10h
0x18006390a  movups  xmm0, xmmword ptr [rbx]
0x18006390d  movdqu  xmmword ptr [rbp+80h+String1.Length], xmm0
0x180063912  movdqu  xmmword ptr [rbp+80h+var_F0.Length], xmm1
0x180063917  mov     [rbp+80h+var_FC], eax
0x18006391a  mov     byte ptr [rbp+80h+var_F4], r13b
0x18006391e  bt      ecx, 9
0x180063922  jnb     loc_180063C29
0x180063928  mov     sil, r8b
0x18006392b  mov     r13b, r10b
0x18006392e  bts     eax, 11h
0x180063932  movups  xmm0, xmmword ptr [rbx]
0x180063935  movdqu  xmmword ptr [rbp+80h+String1.Length], xmm0
0x18006393a  movdqu  xmmword ptr [rbp+80h+var_F0.Length], xmm1
0x18006393f  jmp     loc_180063C26
0x180063944  cmp     rcx, rdi
0x180063947  jz      short loc_180063970
0x180063949  test    byte ptr [rcx+1Ch], 2
0x18006394d  jz      short loc_180063970
0x18006394f  mov     edx, 1Eh
0x180063954  mov     r9d, r11d
0x180063957  mov     r8, r14
0x18006395a  mov     rcx, [rcx+10h]
0x18006395e  call    WPP_SF_d
0x180063963  mov     edx, [rbp+80h+var_FC]
0x180063966  mov     r9d, [rbp+80h+var_F4]
0x18006396a  mov     r10d, 1
0x180063970  bts     edx, 0Bh
0x180063974  mov     [rbp+80h+var_FC], edx
0x180063977  movups  xmm0, xmmword ptr [rbx]
0x18006397a  movdqu  xmmword ptr [rbp+80h+String1.Length], xmm0
0x18006397f  mov     r13b, r10b
0x180063982  movaps  xmm1, xmmword ptr cs:DomainName2.Length
0x180063989  movdqu  xmmword ptr [rbp+80h+var_F0.Length], xmm1
0x18006398e  mov     [rbp+80h+var_F4], r9d
0x180063992  jmp     loc_180063C29
0x180063997  cmp     rcx, rdi
0x18006399a  jz      short loc_1800639CD
0x18006399c  test    [rcx+1Ch], r11b
0x1800639a0  jz      short loc_1800639CD
0x1800639a2  mov     edx, 1Bh
0x1800639a7  mov     r9d, r8d
0x1800639aa  mov     r8, r14
0x1800639ad  mov     rcx, [rcx+10h]
0x1800639b1  call    WPP_SF_d
0x1800639b6  mov     rcx, cs:WPP_GLOBAL_Control; this
0x1800639bd  mov     r10d, 1
0x1800639c3  lea     r11d, [r10+1]
0x1800639c7  mov     eax, [rbp+80h+arg_20]
0x1800639cd  cmp     [r15+2], r10w
0x1800639d2  jnz     loc_180063B26
0x1800639d8  bt      eax, 8
0x1800639dc  jnb     loc_180063A90
0x1800639e2  mov     r12b, r10b
0x1800639e5  mov     al, sil
0x1800639e8  jmp     loc_180063AED
0x1800639ed  sub     r8d, r11d
0x1800639f0  jz      short loc_1800639C7
0x1800639f2  sub     r8d, r10d
0x1800639f5  jz      short loc_1800639C7
0x1800639f7  sub     r8d, r10d
0x1800639fa  jz      loc_180063C12
0x180063a00  sub     r8d, r10d
0x180063a03  jz      short loc_180063A63
0x180063a05  sub     r8d, r10d
0x180063a08  jz      loc_180063970
0x180063a0e  cmp     r8d, 4
0x180063a12  jnz     short loc_1800639C7
0x180063a14  cmp     [r15+2], r10w
0x180063a19  jz      short loc_180063A3A
0x180063a1b  cmp     rcx, rdi
0x180063a1e  jz      loc_1800648A5
0x180063a24  test    [rcx+1Ch], r10b
0x180063a28  jz      loc_1800648A5
0x180063a2e  lea     edx, [r8+1Bh]
0x180063a32  mov     r8, r14
0x180063a35  jmp     loc_18006489C
0x180063a3a  movups  xmm0, xmmword ptr [rbx]
0x180063a3d  movdqu  xmmword ptr [rbp+80h+String1.Length], xmm0
0x180063a42  mov     [rbp+80h+var_100], r10b
0x180063a46  movups  xmm6, xmm0
0x180063a49  mov     sil, r10b
0x180063a4c  mov     r13b, r10b
0x180063a4f  movaps  xmm0, xmmword ptr cs:DomainName2.Length
0x180063a56  movdqu  xmmword ptr [rbp+80h+var_F0.Length], xmm0
0x180063a5b  mov     [rbp+80h+var_FC], edx
0x180063a5e  jmp     loc_180063C29
0x180063a63  cmp     rcx, rdi
0x180063a66  jz      loc_1800648A5
0x180063a6c  test    [rcx+1Ch], r11b
0x180063a70  jz      loc_1800648A5
  ... truncated ...
```
