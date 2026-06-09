# UlGetCGroupForRequest

- ea: `0x1400445e0`
- end: `0x14004599c`
- name: `UlGetCGroupForRequest`
- size: `5052`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x14002cfc0`

## callees

- `0x140030e6c`
- `0x140041fa8`
- `0x1400435e8`
- `0x1400436f0`
- `0x1400437c0`
- `0x140043ad0`
- `0x140043f78`
- `0x1400445e0`
- `0x1400459b0`
- `0x1400a2290`
- `0x1401c3008`
- `0x1401c45cc`
- `0x1401c5128`
- `0x1401c62f8`
- `0x1401c8a48`
- `0x1401c8b04`
- `0x1401c9050`
- `0x1401d9c5c`
- `0x1401d9dd8`
- `0x1401d9e44`
- `0x1401d9f54`
- `0x1401da2b4`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14004568a`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400458d1`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14004568a`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400458d1`
- `ntoskrnl!wcschr` at `0x1400447d6`
- `ntoskrnl!wcschr` at `0x140044cf5`
- `ntoskrnl!wcschr` at `0x1400447d6`
- `ntoskrnl!wcschr` at `0x140044cf5`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x140044683`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x140044683`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x140044eda`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x140044eda`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140044fa9`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400450c1`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140044fa9`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400450c1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140044ee6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140044ee6`
- `ntoskrnl!ExAllocatePool3` at `0x1400452fa`
- `ntoskrnl!ExAllocatePool3` at `0x1400452fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044b5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044b5a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004466e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004466e`

## pseudocode

```c
__int64 __fastcall UlGetCGroupForRequest(__int64 a1)
{
  __int64 v1; // rsi
  _WORD *v2; // rcx
  wchar_t *v3; // r14
  __int64 v4; // rbx
  unsigned __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rax
  int WildcardSite; // ebx
  wchar_t *v9; // r12
  __int64 v10; // r15
  __int64 i; // rbx
  const wchar_t *v12; // r14
  int v13; // edi
  unsigned __int8 v14; // si
  unsigned __int64 v15; // rcx
  bool v16; // zf
  char v17; // al
  WCHAR *v18; // rdi
  wchar_t *v19; // rax
  __int64 v20; // rax
  int v21; // r12d
  __int64 v22; // rsi
  wchar_t *v23; // r8
  __int64 v24; // r13
  WCHAR v25; // ax
  WCHAR v26; // ax
  __int64 v27; // rdi
  __int64 v28; // rcx
  __int64 v29; // rcx
  _WORD *Pool3; // rdi
  __int64 v31; // rcx
  __int64 v32; // rdi
  __int64 v33; // rcx
  wchar_t *v34; // rsi
  __int64 v35; // r14
  __int64 j; // rbx
  const wchar_t *v37; // r15
  int v38; // edi
  unsigned __int8 v39; // r9
  unsigned int v40; // edx
  unsigned __int64 v41; // rcx
  WCHAR *v42; // rdi
  wchar_t *v43; // rax
  __int64 v44; // rax
  int v45; // r12d
  __int64 v46; // rsi
  wchar_t *v47; // r8
  __int64 v48; // r13
  WCHAR v49; // ax
  WCHAR v50; // ax
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rdi
  _WORD *v54; // rax
  __int64 v56; // rax
  __int64 v57; // rdi
  __int64 v58; // rax
  __int64 v59; // rax
  _WORD *v60; // rax
  int v61; // ecx
  __int64 v62; // rdx
  int v63; // ecx
  __int64 v64; // rdx
  __int128 v65; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v66; // [rsp+60h] [rbp-A0h]
  __int64 v67; // [rsp+70h] [rbp-90h] BYREF
  __int64 v68; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *Str; // [rsp+80h] [rbp-80h] BYREF
  __int64 v70; // [rsp+88h] [rbp-78h]
  __int64 v71; // [rsp+90h] [rbp-70h] BYREF
  __int64 v72; // [rsp+98h] [rbp-68h]
  unsigned int v73; // [rsp+A0h] [rbp-60h]
  wchar_t *v74; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v75; // [rsp+B0h] [rbp-50h]
  UNICODE_STRING String2; // [rsp+B8h] [rbp-48h] BYREF
  UNICODE_STRING String1; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t *v78; // [rsp+D8h] [rbp-28h]
  wchar_t *v79; // [rsp+E0h] [rbp-20h]
  __int64 v80; // [rsp+E8h] [rbp-18h]
  __int64 v81; // [rsp+F0h] [rbp-10h]
  __int64 v83; // [rsp+158h] [rbp+58h] BYREF
  int v84; // [rsp+160h] [rbp+60h]
  char v85; // [rsp+168h] [rbp+68h]

  v1 = a1;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    if ( a1 )
      v59 = *(_QWORD *)(a1 + 64);
    else
      v59 = 0;
    WPP_SF_qq(1032, 127, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids, a1, v59);
  }
  v2 = *(_WORD **)(v1 + 2056);
  if ( v2 )
    *v2 = 0;
  if ( *(_DWORD *)(v1 + 1984) == 3 && (v60 = *(_WORD **)(v1 + 2048), *v60 == 42) && !v60[1] )
  {
    *v60 = 47;
    v85 = 1;
  }
  else
  {
    v85 = 0;
  }
  v3 = *(wchar_t **)(v1 + 2032);
  v79 = v3;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qqqi(1028, 142, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, v3, v1, *(_QWORD *)(v1 + 64), v1 + 1296);
  if ( (BYTE8(xmmword_1401A2CA0) & 0x10) != 0 )
    WPP_SF_Sq(1284, 143, (unsigned int)WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, (_DWORD)v3, v1);
  v4 = *(_QWORD *)(*(_QWORD *)(v1 + 24) + 1096LL);
  KeEnterCriticalRegion();
  v81 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v4 + 1368), 0);
  v65 = 0;
  v66 = 0;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qqqi(1028, 56, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, v3, v1, *(_QWORD *)(v1 + 64), v1 + 1296);
  v7 = *(_QWORD *)(v1 + 24);
  *(_QWORD *)&v66 = v1 + 1296;
  BYTE1(v65) = 1;
  Str = 0;
  *((_QWORD *)&v66 + 1) = *(_QWORD *)(v7 + 1096);
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qq(1028, 38, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, v3, &v65);
  if ( !*(_DWORD *)(*(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL) + 20LL) )
  {
    WildcardSite = -1073741772;
    goto LABEL_65;
  }
  LOBYTE(v6) = 1;
  WildcardSite = UlpTreeFindWildcardSite(DWORD2(v66), (_DWORD)v3, v6, (unsigned int)&Str, (__int64)&v65 + 8);
  if ( WildcardSite >= 0 )
  {
    v9 = Str;
    v10 = *((_QWORD *)&v65 + 1);
    v72 = v66;
    v78 = Str;
    v80 = *((_QWORD *)&v65 + 1);
    LOBYTE(v65) = 1;
    v68 = 0;
    v71 = 0;
    LOBYTE(v83) = 0;
    if ( (xmmword_1401A2CA0 & 0x10) != 0 )
      WPP_SF_qqqi(
        1028,
        31,
        WPP_1afab14d2023349dcdd3f873f7453800_Traceguids,
        *((_QWORD *)&v65 + 1),
        Str,
        v66,
        (char *)&v65 + 1);
    i = v10;
    BYTE1(v65) = 1;
    v67 = v10;
    v12 = v9;
    v68 = 0;
    v13 = 0;
    LOBYTE(v83) = 0;
    v6 = 0;
    v75 = 0;
    v14 = 0;
    if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    {
      WPP_SF_qqLqqqq(1028, 29, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, v10, v9, 3, &v83, &v71, &v68, 0);
      i = v67;
      v6 = 0;
    }
    v71 = 0;
    v68 = 0;
    LOBYTE(v83) = 0;
    while ( 1 )
    {
      LODWORD(v5) = *(unsigned __int8 *)(i + 37);
      LODWORD(v15) = 0;
      if ( (_BYTE)v5 )
        v6 = i;
      else
        LODWORD(v15) = v14;
      v16 = *(_BYTE *)(i + 36) == 0;
      v17 = v15;
      v70 = v6;
      LOBYTE(v84) = v15;
      if ( !v16 )
      {
        v17 = 1;
        v75 = i;
        LOBYTE(v84) = 1;
      }
      if ( !v12 || !*v12 )
        goto LABEL_51;
      v18 = (WCHAR *)v12;
      v19 = wcschr(v12, 0x2Fu);
      v12 = v19;
      if ( v19 )
      {
        *v19 = 0;
        v20 = v19 - v18;
        ++v12;
      }
      else
      {
        v20 = -1;
        do
          ++v20;
        while ( v18[v20] );
      }
      v21 = 2 * v20;
      String1 = 0;
      v22 = *(_QWORD *)(v67 + 136);
      v23 = *(wchar_t **)(v67 + 16);
      v74 = v23;
      v24 = *(_QWORD *)(v22 + 1360);
      if ( (xmmword_1401A2CA0 & 0x10) != 0 )
      {
        WPP_SF_qqqdq(1028, 12, WPP_90d6322b044c36e5e3578bb00c1e16fe_Traceguids, v22, v23, v18, v21, &v67);
        v23 = v74;
      }
      i = 0;
      v67 = 0;
      if ( v21 )
        break;
      v13 = -1073741811;
LABEL_43:
      if ( (xmmword_1401A2CA0 & 0x10) != 0 )
      {
        WPP_SF_qD(1028, 13, WPP_90d6322b044c36e5e3578bb00c1e16fe_Traceguids, i, v13);
        i = v67;
      }
      if ( v12 )
      {
        *((_WORD *)v12 - 1) = 47;
        i = v67;
      }
      v6 = v70;
      if ( v13 == -1073741772 )
      {
        v17 = v84;
LABEL_51:
        v71 = v75;
        v68 = v6;
        if ( v75 != v6 )
          LOBYTE(v83) = v17;
LABEL_53:
        if ( (xmmword_1401A2CA0 & 0x10) != 0 )
          WPP_SF_d(1028, 30, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, (unsigned int)v13);
        if ( v71 && (_BYTE)v83 )
        {
          BYTE1(v65) = 0;
LABEL_179:
          LOBYTE(v27) = v72;
          WildcardSite = -1073741772;
        }
        else
        {
          if ( !v68 )
            goto LABEL_179;
          v10 = v68;
          v27 = v72;
          if ( *(_QWORD *)(v68 + 8) )
          {
            while ( v10 )
            {
              if ( *(_BYTE *)(v10 + 37) )
              {
                WildcardSite = UlpSetUrlInfo(v27, v10, 0);
                if ( WildcardSite < 0 )
                  goto LABEL_63;
              }
              v10 = *(_QWORD *)(v10 + 8);
            }
          }
          else
          {
            LOBYTE(v6) = 1;
            WildcardSite = UlpSetUrlInfo(v72, v68, v6);
            if ( WildcardSite < 0 )
              goto LABEL_63;
          }
          WildcardSite = 0;
        }
LABEL_63:
        if ( (xmmword_1401A2CA0 & 0x10) != 0 )
        {
          WPP_SF_qSqqcd(v15, v5, v6, v10, (__int64)v78, v27, v68, SBYTE1(v65), WildcardSite);
          if ( (xmmword_1401A2CA0 & 0x10) != 0 )
            WPP_SF_Dd(1028, 33, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, BYTE1(v65), WildcardSite);
        }
        v1 = a1;
        v3 = v79;
        goto LABEL_65;
      }
      v14 = v84;
      if ( v13 < 0 )
        goto LABEL_53;
    }
    if ( !v23 )
    {
LABEL_42:
      v13 = -1073741772;
      goto LABEL_43;
    }
    v25 = *v18;
    String1.Buffer = v18;
    String1.Length = v21;
    String1.MaximumLength = v21;
    LODWORD(v5) = *(_DWORD *)(v24 + 24);
    v73 = v5;
    if ( v25 )
    {
      do
      {
        if ( v25 >= 0x100u )
          v26 = RtlUpcaseUnicodeChar(v25);
        else
          v26 = *(_WORD *)(v22 + 2LL * (unsigned __int8)v25 + 6080);
        ++v18;
        LODWORD(i) = v26 + 101 * i;
        v25 = *v18;
      }
      while ( *v18 );
      LODWORD(v10) = v80;
      LODWORD(v5) = v73;
      v23 = v74;
    }
    v15 = ((unsigned int)v5
         & ((69069 * (_DWORD)i + 1) & 0xFFFF0000 | ((unsigned __int64)(unsigned int)(1103515245 * i + 12345) >> 16))) << 6;
    for ( i = *(_QWORD *)(v15 + *(_QWORD *)(v24 + 8)); ; i = *(_QWORD *)(i + 24) )
    {
      while ( 1 )
      {
        if ( !i )
        {
          i = v67;
          goto LABEL_42;
        }
        v56 = *(_QWORD *)(i + 8);
        if ( v56 )
          break;
        if ( *(_QWORD *)(*((_QWORD *)v23 + 4) + 8LL) )
        {
          i = *(_QWORD *)(i + 24);
        }
        else
        {
LABEL_181:
          LODWORD(v15) = *(_DWORD *)(i + 32);
          if ( v21 == (_DWORD)v15 )
          {
            *(_DWORD *)(&String2.MaximumLength + 1) = 0;
            String2.Length = v15;
            String2.MaximumLength = v15;
            String2.Buffer = (PWSTR)(i + 144);
            if ( !RtlCompareUnicodeString(&String1, &String2, 1u) )
            {
              v67 = i;
              v13 = 0;
              goto LABEL_43;
            }
            v23 = v74;
          }
          i = *(_QWORD *)(i + 24);
        }
      }
      if ( v23 == *(wchar_t **)(v56 + 16) )
        goto LABEL_181;
    }
  }
LABEL_65:
  v28 = *(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL);
  if ( *(_DWORD *)(v28 + 20) && (BYTE8(xmmword_1401A2CA0) & 0x10) != 0 )
    WPP_SF_SSld(v28, 39, v6, (_DWORD)v3, (__int64)Str, WildcardSite >= 0, WildcardSite);
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_d(1028, 40, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, (unsigned int)WildcardSite);
  if ( WildcardSite != -1073741772 )
    goto LABEL_163;
  if ( !BYTE1(v65) )
    goto LABEL_199;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qilq(1028, 41, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, v1, *(_QWORD *)(v1 + 64), 0, &v65);
  if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL) + 28LL) )
  {
    WildcardSite = UlGenerateRoutingToken(v1, 2);
    if ( WildcardSite >= 0 )
    {
      WildcardSite = UlpTreeFindSiteIpMatch(v1, (char *)&v65 + 8);
      if ( WildcardSite >= 0 )
      {
        v62 = *(_QWORD *)(v1 + 2048) + 2LL;
        LOBYTE(v65) = 1;
        WildcardSite = UlpTreeFindNodeWalker(*((_QWORD *)&v65 + 1), v62, v66, (char *)&v65 + 1);
      }
      if ( (BYTE8(xmmword_1401A2CA0) & 0x10) != 0 )
        WPP_SF_SSld(v61, 42, v6, *(_QWORD *)(v1 + 2080), *(_QWORD *)(v1 + 2048), WildcardSite >= 0, WildcardSite);
    }
  }
  else
  {
    WildcardSite = -1073741772;
  }
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_d(1028, 43, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, (unsigned int)WildcardSite);
  if ( WildcardSite != -1073741772 )
    goto LABEL_163;
  if ( !BYTE1(v65) )
    goto LABEL_199;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qilq(1028, 41, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, v1, *(_QWORD *)(v1 + 64), 1, &v65);
  if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL) + 28LL) )
  {
    WildcardSite = UlGenerateRoutingToken(v1, 3);
    if ( WildcardSite >= 0 )
    {
      WildcardSite = UlpTreeFindSiteIpMatch(v1, (char *)&v65 + 8);
      if ( WildcardSite >= 0 )
      {
        v64 = *(_QWORD *)(v1 + 2048) + 2LL;
        LOBYTE(v65) = 1;
        WildcardSite = UlpTreeFindNodeWalker(*((_QWORD *)&v65 + 1), v64, v66, (char *)&v65 + 1);
      }
      if ( (BYTE8(xmmword_1401A2CA0) & 0x10) != 0 )
        WPP_SF_SSld(v63, 42, v6, *(_QWORD *)(v1 + 2080), *(_QWORD *)(v1 + 2048), WildcardSite >= 0, WildcardSite);
    }
  }
  else
  {
    WildcardSite = -1073741772;
  }
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_d(1028, 43, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, (unsigned int)WildcardSite);
  if ( WildcardSite != -1073741772 )
    goto LABEL_163;
  if ( !BYTE1(v65) )
    goto LABEL_199;
  v83 = 0;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qq(1028, 44, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, v3, &v65);
  if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL) + 12LL) )
  {
    WildcardSite = UlpTreeFindSite(*((_QWORD *)&v66 + 1), v3, &v83, (char *)&v65 + 8);
    if ( WildcardSite >= 0 )
    {
      LOBYTE(v65) = 1;
      WildcardSite = UlpTreeFindNodeWalker(*((_QWORD *)&v65 + 1), v83, v66, (char *)&v65 + 1);
    }
  }
  else
  {
    WildcardSite = -1073741772;
  }
  v29 = *(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL);
  if ( *(_DWORD *)(v29 + 12) && (BYTE8(xmmword_1401A2CA0) & 0x10) != 0 )
    WPP_SF_SSld(v29, 45, v6, (_DWORD)v3, v83, WildcardSite >= 0, WildcardSite);
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_d(1028, 46, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, (unsigned int)WildcardSite);
  if ( WildcardSite != -1073741772 )
    goto LABEL_163;
  if ( !BYTE1(v65) )
    goto LABEL_199;
  Str = 0;
  Pool3 = 0;
  v84 = 0;
  LODWORD(v83) = 0;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qq(1028, 47, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, v3, &v65);
  if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL) + 12LL) )
  {
    WildcardSite = UlpExtractSchemeHostPortIp(v3);
    if ( WildcardSite >= 0 )
    {
      v5 = 2LL * (unsigned int)(v84 + 2);
      if ( v5 <= 0xFFFFFFFF )
        Pool3 = (_WORD *)ExAllocatePool3(66, v5, 1280666709, UxLowPriorityPool, 1);
      if ( Pool3 )
      {
        WildcardSite = UlGenerateSubdomainWildcardUrl(v3, (__int64)&v83);
        if ( WildcardSite >= 0 )
        {
          Pool3[(unsigned int)v83] = 47;
          Pool3[(unsigned int)(v83 + 1)] = 0;
          LODWORD(v83) = v83 + 2;
          WildcardSite = UlpTreeFindSite(*((_QWORD *)&v66 + 1), Pool3, &Str, (char *)&v65 + 8);
          if ( WildcardSite >= 0 )
          {
            LOBYTE(v65) = 1;
            Str = &v3[v84 + 1];
            WildcardSite = UlpTreeFindNodeWalker(*((_QWORD *)&v65 + 1), Str, v66, (char *)&v65 + 1);
          }
        }
      }
      else
      {
        WildcardSite = -1073741670;
      }
    }
  }
  else
  {
    WildcardSite = -1073741772;
  }
  v31 = *(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL);
  if ( *(_DWORD *)(v31 + 12) && (BYTE8(xmmword_1401A2CA0) & 0x10) != 0 )
    WPP_SF_SSl(v31, v5, v6, (_DWORD)v3, (__int64)Str, WildcardSite >= 0);
  if ( Pool3 )
    ExFreePoolWithTag(Pool3, 0);
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_d(1028, 49, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, (unsigned int)WildcardSite);
  if ( WildcardSite != -1073741772 )
    goto LABEL_163;
  if ( !BYTE1(v65) )
    goto LABEL_199;
  v32 = 0;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qqP(1028, 50, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, v1, *(_QWORD *)(v1 + 64), &v65);
  if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL) + 16LL) )
  {
    WildcardSite = UlGenerateRoutingToken(v1, 1);
    if ( WildcardSite >= 0 )
    {
      WildcardSite = UlpTreeFindSiteIpMatch(v1, (char *)&v65 + 8);
      if ( WildcardSite >= 0 )
      {
        v32 = *(_QWORD *)(v1 + 2048) + 2LL;
        LOBYTE(v65) = 1;
        WildcardSite = UlpTreeFindNodeWalker(*((_QWORD *)&v65 + 1), v32, v66, (char *)&v65 + 1);
      }
    }
  }
  else
  {
    WildcardSite = -1073741772;
  }
  v33 = *(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL);
  if ( *(_DWORD *)(v33 + 16) && (BYTE8(xmmword_1401A2CA0) & 0x10) != 0 )
    WPP_SF_SSld(v33, 51, v6, *(_QWORD *)(v1 + 2080), v32, WildcardSite >= 0, WildcardSite);
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_d(1028, 52, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, (unsigned int)WildcardSite);
  if ( WildcardSite != -1073741772 )
  {
LABEL_163:
    if ( WildcardSite >= 0 )
    {
      v52 = *((_QWORD *)&v65 + 1);
      v53 = a1;
      *(_DWORD *)(a1 + 1448) = *(_DWORD *)(*((_QWORD *)&v65 + 1) + 72LL);
      if ( *(_BYTE *)(v52 + 38) && *(_DWORD *)(v52 + 72) == 1 && !(unsigned __int8)UlpIsLocalRequest(a1) )
        WildcardSite = -1073741790;
      goto LABEL_165;
    }
LABEL_200:
    v53 = a1;
    goto LABEL_165;
  }
  if ( !BYTE1(v65) )
    goto LABEL_199;
  v74 = 0;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qq(1028, 53, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, v3, &v65);
  if ( !*(_DWORD *)(*(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL) + 24LL) )
  {
    WildcardSite = -1073741772;
    goto LABEL_157;
  }
  WildcardSite = UlpTreeFindWildcardSite(DWORD2(v66), (_DWORD)v3, 0, (unsigned int)&v74, (__int64)&v65 + 8);
  if ( WildcardSite >= 0 )
  {
    v34 = v74;
    v35 = *((_QWORD *)&v65 + 1);
    v70 = v66;
    v78 = v74;
    LOBYTE(v65) = 1;
    v68 = 0;
    v71 = 0;
    LOBYTE(v83) = 0;
    if ( (xmmword_1401A2CA0 & 0x10) != 0 )
      WPP_SF_qqqi(
        1028,
        31,
        WPP_1afab14d2023349dcdd3f873f7453800_Traceguids,
        *((_QWORD *)&v65 + 1),
        v74,
        v66,
        (char *)&v65 + 1);
    j = v35;
    BYTE1(v65) = 1;
    v67 = v35;
    v37 = v34;
    v68 = 0;
    v38 = 0;
    LOBYTE(v83) = 0;
    v6 = 0;
    v75 = 0;
    v39 = 0;
    if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    {
      WPP_SF_qqLqqqq(1028, 29, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, v35, v34, 3, &v83, &v71, &v68, 0);
      j = v67;
      v6 = 0;
      v39 = 0;
    }
    v71 = 0;
    v68 = 0;
    LOBYTE(v83) = 0;
    while ( 1 )
    {
      v40 = *(unsigned __int8 *)(j + 37);
      LODWORD(v41) = 0;
      if ( (_BYTE)v40 )
        v6 = j;
      else
        LODWORD(v41) = v39;
      v16 = *(_BYTE *)(j + 36) == 0;
      v72 = v6;
      LOBYTE(v84) = v41;
      if ( !v16 )
      {
        v75 = j;
        LOBYTE(v84) = 1;
      }
      if ( !v37 || !*v37 )
        break;
      v42 = (WCHAR *)v37;
      v43 = wcschr(v37, 0x2Fu);
      v37 = v43;
      if ( v43 )
      {
        *v43 = 0;
        v44 = v43 - v42;
        ++v37;
      }
      else
      {
        v44 = -1;
        do
          ++v44;
        while ( v42[v44] );
      }
      v45 = 2 * v44;
      String2 = 0;
      v46 = *(_QWORD *)(v67 + 136);
      v47 = *(wchar_t **)(v67 + 16);
      Str = v47;
      v48 = *(_QWORD *)(v46 + 1360);
      if ( (xmmword_1401A2CA0 & 0x10) != 0 )
      {
        WPP_SF_qqqdq(1028, 12, WPP_90d6322b044c36e5e3578bb00c1e16fe_Traceguids, v46, v47, v42, v45, &v67);
        v47 = Str;
      }
      j = 0;
      v67 = 0;
      if ( v45 )
      {
        if ( !v47 )
        {
LABEL_147:
          v38 = -1073741772;
          goto LABEL_148;
        }
        v49 = *v42;
        String2.Buffer = v42;
        String2.Length = v45;
        String2.MaximumLength = v45;
        v40 = *(_DWORD *)(v48 + 24);
        v73 = v40;
        if ( v49 )
        {
          do
          {
            if ( v49 >= 0x100u )
              v50 = RtlUpcaseUnicodeChar(v49);
            else
              v50 = *(_WORD *)(v46 + 2LL * (unsigned __int8)v49 + 6080);
            ++v42;
            LODWORD(j) = v50 + 101 * j;
            v49 = *v42;
          }
          while ( *v42 );
          v40 = v73;
          v47 = Str;
        }
        v41 = (v40
             & ((69069 * (_DWORD)j + 1) & 0xFFFF0000 | ((unsigned __int64)(unsigned int)(1103515245 * j + 12345) >> 16))) << 6;
        for ( j = *(_QWORD *)(v41 + *(_QWORD *)(v48 + 8)); ; j = *(_QWORD *)(j + 24) )
        {
          while ( 2 )
          {
            if ( !j )
            {
              j = v67;
              goto LABEL_147;
            }
            v58 = *(_QWORD *)(j + 8);
            if ( v58 )
            {
              if ( v47 != *(wchar_t **)(v58 + 16) )
              {
                j = *(_QWORD *)(j + 24);
                continue;
              }
            }
            else if ( *(_QWORD *)(*((_QWORD *)v47 + 4) + 8LL) )
            {
              j = *(_QWORD *)(j + 24);
              continue;
            }
            break;
          }
          LODWORD(v41) = *(_DWORD *)(j + 32);
          if ( v45 == (_DWORD)v41 )
          {
            *(_DWORD *)(&String1.MaximumLength + 1) = 0;
            String1.Length = v41;
            String1.MaximumLength = v41;
            String1.Buffer = (PWSTR)(j + 144);
            if ( !RtlCompareUnicodeString(&String2, &String1, 1u) )
            {
              v67 = j;
              v38 = 0;
              goto LABEL_148;
            }
            v47 = Str;
          }
        }
      }
      v38 = -1073741811;
LABEL_148:
      if ( (xmmword_1401A2CA0 & 0x10) != 0 )
      {
        WPP_SF_qD(1028, 13, WPP_90d6322b044c36e5e3578bb00c1e16fe_Traceguids, j, v38);
        j = v67;
      }
      if ( v37 )
      {
        *((_WORD *)v37 - 1) = 47;
        j = v67;
      }
      v6 = v72;
      if ( v38 == -1073741772 )
        break;
      v39 = v84;
      if ( v38 < 0 )
        goto LABEL_186;
    }
    v71 = v75;
    v68 = v6;
    if ( v75 != v6 )
      LOBYTE(v83) = v84;
LABEL_186:
    if ( (xmmword_1401A2CA0 & 0x10) != 0 )
      WPP_SF_d(1028, 30, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, (unsigned int)v38);
    if ( v71 && (_BYTE)v83 )
    {
      BYTE1(v65) = 0;
    }
    else if ( v68 )
    {
      v35 = v68;
      v57 = v70;
      if ( *(_QWORD *)(v68 + 8) )
      {
        while ( v35 )
        {
          if ( *(_BYTE *)(v35 + 37) )
          {
            WildcardSite = UlpSetUrlInfo(v57, v35, 0);
            if ( WildcardSite < 0 )
              goto LABEL_156;
          }
          v35 = *(_QWORD *)(v35 + 8);
        }
      }
      else
      {
        LOBYTE(v6) = 1;
        WildcardSite = UlpSetUrlInfo(v70, v68, v6);
        if ( WildcardSite < 0 )
          goto LABEL_156;
      }
      WildcardSite = 0;
LABEL_156:
      if ( (xmmword_1401A2CA0 & 0x10) != 0 )
      {
        WPP_SF_qSqqcd(v41, v40, v6, v35, (__int64)v78, v57, v68, SBYTE1(v65), WildcardSite);
        if ( (xmmword_1401A2CA0 & 0x10) != 0 )
          WPP_SF_Dd(1028, 33, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, BYTE1(v65), WildcardSite);
      }
      goto LABEL_157;
    }
    LOBYTE(v57) = v70;
    WildcardSite = -1073741772;
    goto LABEL_156;
  }
LABEL_157:
  v51 = *(_QWORD *)(*((_QWORD *)&v66 + 1) + 1320LL);
  if ( *(_DWORD *)(v51 + 24) && (BYTE8(xmmword_1401A2CA0) & 0x10) != 0 )
    WPP_SF_SSld(v51, 54, v6, (_DWORD)v79, (__int64)v74, WildcardSite >= 0, WildcardSite);
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_d(1028, 55, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, (unsigned int)WildcardSite);
  if ( WildcardSite != -1073741772 )
    goto LABEL_163;
  if ( !BYTE1(v65) )
  {
LABEL_199:
    WildcardSite = -1073741769;
    goto LABEL_200;
  }
  v53 = a1;
  if ( (_BYTE)v65 )
    WildcardSite = -1073741766;
LABEL_165:
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qD(1028, 57, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, v53 + 1296, WildcardSite);
  ExReleaseCacheAwarePushLockSharedEx(v81, 0);
  KeLeaveCriticalRegion();
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qD(1028, 144, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, v53 + 1296, WildcardSite);
  v54 = *(_WORD **)(v53 + 2056);
  if ( v54 )
    *v54 = 63;
  if ( v85 )
    **(_WORD **)(v53 + 2048) = 42;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_d(1032, 128, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids, (unsigned int)WildcardSite);
  return (unsigned int)WildcardSite;
}

```

## disassembly

```asm
0x1400445e0  mov     [rsp-8+arg_0], rcx
0x1400445e5  push    rbp
0x1400445e6  push    rbx
0x1400445e7  push    rsi
0x1400445e8  push    rdi
0x1400445e9  push    r12
0x1400445eb  push    r13
0x1400445ed  push    r14
0x1400445ef  push    r15
0x1400445f1  lea     rbp, [rsp-8]
0x1400445f6  sub     rsp, 108h
0x1400445fd  mov     rsi, rcx
0x140044600  xor     r13d, r13d
0x140044603  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14004460a  jnz     loc_140045530
0x140044610  mov     rcx, [rsi+808h]
0x140044617  test    rcx, rcx
0x14004461a  jz      short loc_140044620
0x14004461c  mov     [rcx], r13w
0x140044620  cmp     dword ptr [rsi+7C0h], 3
0x140044627  mov     r12d, 2Fh ; '/'
0x14004462d  jz      loc_140045561
0x140044633  mov     [rbp+40h+arg_18], r13b
0x140044637  mov     r14, [rsi+7F0h]
0x14004463e  lea     rdi, [rsi+510h]
0x140044645  mov     [rbp+40h+var_60], r14
0x140044649  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044650  jnz     loc_14004558A
0x140044656  test    byte ptr cs:xmmword_1401A2CA0+8, 10h
0x14004465d  jnz     loc_1400455BB
0x140044663  mov     rax, [rsi+18h]
0x140044667  mov     rbx, [rax+448h]
0x14004466e  call    cs:__imp_KeEnterCriticalRegion
0x140044675  nop     dword ptr [rax+rax+00h]
0x14004467a  mov     rcx, [rbx+558h]
0x140044681  xor     edx, edx
0x140044683  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x14004468a  nop     dword ptr [rax+rax+00h]
0x14004468f  xorps   xmm0, xmm0
0x140044692  mov     [rbp+40h+var_50], rax
0x140044696  movups  [rsp+140h+var_F0], xmm0
0x14004469b  movups  [rsp+140h+var_E0], xmm0
0x1400446a0  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400446a7  jnz     loc_1400453D3
0x1400446ad  mov     rax, [rsi+18h]
0x1400446b1  mov     qword ptr [rsp+140h+var_E0], rdi
0x1400446b6  mov     byte ptr [rsp+140h+var_F0+1], 1
0x1400446bb  mov     [rbp+40h+Str], r13
0x1400446bf  mov     rcx, [rax+448h]
0x1400446c6  mov     qword ptr [rsp+140h+var_E0+8], rcx
0x1400446cb  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400446d2  jnz     loc_1400455DE
0x1400446d8  mov     rax, qword ptr [rsp+140h+var_E0+8]
0x1400446dd  mov     rcx, [rax+528h]
0x1400446e4  cmp     [rcx+14h], r13d
0x1400446e8  jz      loc_140045606
0x1400446ee  mov     rcx, qword ptr [rsp+140h+var_E0+8]
0x1400446f3  lea     rax, [rsp+140h+var_F0+8]
0x1400446f8  lea     r9, [rbp+40h+Str]
0x1400446fc  mov     [rsp+140h+var_120], rax
0x140044701  mov     r8b, 1
0x140044704  mov     rdx, r14
0x140044707  call    UlpTreeFindWildcardSite
0x14004470c  mov     ebx, eax
0x14004470e  test    eax, eax
0x140044710  js      loc_1400449BC
0x140044716  mov     r8, qword ptr [rsp+140h+var_E0]
0x14004471b  mov     r12, [rbp+40h+Str]
0x14004471f  mov     r15, qword ptr [rsp+140h+var_F0+8]
0x140044724  mov     [rbp+40h+var_A8], r8
0x140044728  mov     [rbp+40h+var_68], r12
0x14004472c  mov     [rbp+40h+var_58], r15
0x140044730  mov     byte ptr [rsp+140h+var_F0], 1
0x140044735  mov     [rsp+140h+var_C8], r13
0x14004473a  mov     [rbp+40h+var_B0], r13
0x14004473e  mov     byte ptr [rbp+40h+arg_8], r13b
0x140044742  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044749  jnz     loc_140045610
0x14004474f  mov     rbx, r15
0x140044752  mov     byte ptr [rsp+140h+var_F0+1], 1
0x140044757  mov     [rsp+140h+var_D0], rbx
0x14004475c  mov     r14, r12
0x14004475f  mov     [rsp+140h+var_C8], r13
0x140044764  mov     edi, r13d
0x140044767  mov     byte ptr [rbp+40h+arg_8], r13b
0x14004476b  mov     r8, r13
0x14004476e  mov     [rbp+40h+var_90], r13
0x140044772  xor     sil, sil
0x140044775  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x14004477c  jnz     loc_14017605E
0x140044782  mov     [rbp+40h+var_B0], r13
0x140044786  mov     [rsp+140h+var_C8], r13
0x14004478b  mov     byte ptr [rbp+40h+arg_8], sil
0x14004478f  movzx   edx, byte ptr [rbx+25h]
0x140044793  mov     ecx, r13d
0x140044796  test    dl, dl
0x140044798  movzx   eax, sil
0x14004479c  cmovz   ecx, eax
0x14004479f  cmovnz  r8, rbx
0x1400447a3  cmp     byte ptr [rbx+24h], 0
0x1400447a7  movzx   eax, cl
0x1400447aa  mov     [rbp+40h+var_B8], r8
0x1400447ae  mov     byte ptr [rbp+40h+arg_10], cl
0x1400447b1  jnz     loc_1400451CC
0x1400447b7  test    r14, r14
0x1400447ba  jz      loc_14004492B
0x1400447c0  cmp     word ptr [r14], 0
0x1400447c5  jz      loc_14004492B
0x1400447cb  mov     edx, 2Fh ; '/'; Ch
0x1400447d0  mov     rcx, r14; Str
0x1400447d3  mov     rdi, r14
0x1400447d6  call    cs:__imp_wcschr
0x1400447dd  nop     dword ptr [rax+rax+00h]
0x1400447e2  mov     r14, rax
0x1400447e5  test    rax, rax
0x1400447e8  jz      loc_1400450E5
0x1400447ee  mov     [rax], r13w
0x1400447f2  sub     rax, rdi
0x1400447f5  sar     rax, 1
0x1400447f8  add     r14, 2
0x1400447fc  lea     r12d, [rax+rax]
0x140044800  xorps   xmm0, xmm0
0x140044803  mov     rax, [rsp+140h+var_D0]
0x140044808  movups  xmmword ptr [rbp+40h+String1.Length], xmm0
0x14004480c  mov     rsi, [rax+88h]
0x140044813  mov     r8, [rax+10h]
0x140044817  mov     [rbp+40h+var_98], r8
0x14004481b  mov     r13, [rsi+550h]
0x140044822  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044829  jnz     loc_140045642
0x14004482f  xor     ebx, ebx
0x140044831  mov     [rsp+140h+var_D0], rbx
0x140044836  test    r12d, r12d
0x140044839  jz      loc_14004567D
0x14004483f  test    r8, r8
0x140044842  jz      loc_1400448E7
0x140044848  movzx   eax, word ptr [rdi]
0x14004484b  mov     [rbp+40h+String1.Buffer], rdi
0x14004484f  mov     [rbp+40h+String1.Length], r12w
0x140044854  mov     [rbp+40h+String1.MaximumLength], r12w
0x140044859  mov     edx, [r13+18h]
0x14004485d  mov     [rbp+40h+var_A0], edx
0x140044860  test    ax, ax
0x140044863  jz      short loc_1400448A4
0x140044865  mov     r15d, 100h
0x14004486b  nop     dword ptr [rax+rax+00h]
0x140044870  cmp     ax, r15w
0x140044874  jnb     loc_140045687
0x14004487a  movzx   ecx, al
0x14004487d  movzx   eax, word ptr [rsi+rcx*2+17C0h]
0x140044885  imul    ebx, 65h ; 'e'
0x140044888  add     rdi, 2
0x14004488c  movzx   eax, ax
0x14004488f  add     ebx, eax
0x140044891  movzx   eax, word ptr [rdi]
0x140044894  test    ax, ax
0x140044897  jnz     short loc_140044870
0x140044899  mov     r15, [rbp+40h+var_58]
0x14004489d  mov     edx, [rbp+40h+var_A0]
0x1400448a0  mov     r8, [rbp+40h+var_98]
0x1400448a4  imul    ecx, ebx, 41C64E6Dh
0x1400448aa  mov     r9d, 0FFFF0000h
0x1400448b0  imul    eax, ebx, 10DCDh
0x1400448b6  add     ecx, 3039h
0x1400448bc  inc     eax
0x1400448be  shr     rcx, 10h
0x1400448c2  and     rax, r9
0x1400448c5  or      rcx, rax
0x1400448c8  mov     eax, edx
0x1400448ca  and     rcx, rax
0x1400448cd  mov     rax, [r13+8]
0x1400448d1  shl     rcx, 6
0x1400448d5  mov     rbx, [rcx+rax]
0x1400448d9  test    rbx, rbx
0x1400448dc  jnz     loc_140044F3E
0x1400448e2  mov     rbx, [rsp+140h+var_D0]
0x1400448e7  mov     edi, 0C0000034h
0x1400448ec  xor     r13d, r13d
0x1400448ef  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400448f6  jnz     loc_14004546A
0x1400448fc  test    r14, r14
0x1400448ff  jz      short loc_14004490D
0x140044901  mov     word ptr [r14-2], 2Fh ; '/'
0x140044908  mov     rbx, [rsp+140h+var_D0]
0x14004490d  mov     r8, [rbp+40h+var_B8]
0x140044911  cmp     edi, 0C0000034h
0x140044917  jz      short loc_140044927
0x140044919  movzx   esi, byte ptr [rbp+40h+arg_10]
0x14004491d  test    edi, edi
0x14004491f  jns     loc_14004478F
0x140044925  jmp     short loc_140044940
0x140044927  movzx   eax, byte ptr [rbp+40h+arg_10]
0x14004492b  mov     r9, [rbp+40h+var_90]
0x14004492f  mov     [rbp+40h+var_B0], r9
0x140044933  mov     [rsp+140h+var_C8], r8
0x140044938  cmp     r9, r8
0x14004493b  jz      short loc_140044940
0x14004493d  mov     byte ptr [rbp+40h+arg_8], al
0x140044940  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044947  jnz     loc_1400456B1
0x14004494d  cmp     [rbp+40h+var_B0], 0
0x140044952  jnz     loc_1400451DA
0x140044958  mov     rax, [rsp+140h+var_C8]
0x14004495d  test    rax, rax
0x140044960  jz      loc_140044F5B
0x140044966  cmp     qword ptr [rax+8], 0
0x14004496b  mov     r15, rax
0x14004496e  mov     rdi, [rbp+40h+var_A8]
0x140044972  jz      loc_1400451AF
0x140044978  test    r15, r15
0x14004497b  jz      short loc_14004499E
0x14004497d  cmp     byte ptr [r15+25h], 0
0x140044982  jz      short loc_140044998
0x140044984  xor     r8d, r8d
0x140044987  mov     rdx, r15
0x14004498a  mov     rcx, rdi
0x14004498d  call    UlpSetUrlInfo
0x140044992  mov     ebx, eax
0x140044994  test    eax, eax
0x140044996  js      short loc_1400449A1
0x140044998  mov     r15, [r15+8]
0x14004499c  jmp     short loc_140044978
0x14004499e  mov     ebx, r13d
0x1400449a1  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400449a8  jnz     loc_1401760B2
0x1400449ae  mov     rsi, [rbp+40h+arg_0]
0x1400449b2  mov     r12d, 2Fh ; '/'
0x1400449b8  mov     r14, [rbp+40h+var_60]
0x1400449bc  mov     rax, qword ptr [rsp+140h+var_E0+8]
0x1400449c1  mov     rcx, [rax+528h]
0x1400449c8  cmp     dword ptr [rcx+14h], 0
0x1400449cc  jz      short loc_1400449DB
0x1400449ce  test    byte ptr cs:xmmword_1401A2CA0+8, 10h
0x1400449d5  jnz     loc_1400456CF
0x1400449db  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400449e2  jnz     loc_1400456F9
0x1400449e8  mov     r15d, 2Ah ; '*'
0x1400449ee  cmp     ebx, 0C0000034h
0x1400449f4  jnz     loc_140044E9C
0x1400449fa  cmp     byte ptr [rsp+140h+var_F0+1], 0
0x1400449ff  jz      loc_140045073
0x140044a05  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044a0c  jnz     loc_140045717
0x140044a12  mov     rax, qword ptr [rsp+140h+var_E0+8]
0x140044a17  mov     rcx, [rax+528h]
0x140044a1e  cmp     dword ptr [rcx+1Ch], 0
0x140044a22  jnz     loc_140176112
0x140044a28  mov     ebx, 0C0000034h
0x140044a2d  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044a34  jnz     loc_140045491
0x140044a3a  cmp     ebx, 0C0000034h
0x140044a40  jnz     loc_140044E9C
0x140044a46  cmp     byte ptr [rsp+140h+var_F0+1], 0
0x140044a4b  jz      loc_140045073
0x140044a51  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044a58  jnz     loc_14004574D
0x140044a5e  mov     rax, qword ptr [rsp+140h+var_E0+8]
0x140044a63  mov     rcx, [rax+528h]
0x140044a6a  cmp     dword ptr [rcx+1Ch], 0
0x140044a6e  jnz     loc_14017619F
0x140044a74  mov     ebx, 0C0000034h
0x140044a79  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044a80  jnz     loc_1400454AF
0x140044a86  cmp     ebx, 0C0000034h
0x140044a8c  jnz     loc_140044E9C
0x140044a92  cmp     byte ptr [rsp+140h+var_F0+1], 0
0x140044a97  jz      loc_140045073
0x140044a9d  mov     [rbp+40h+arg_8], r13
0x140044aa1  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044aa8  jnz     loc_140045786
0x140044aae  mov     rax, qword ptr [rsp+140h+var_E0+8]
0x140044ab3  mov     rcx, [rax+528h]
0x140044aba  cmp     dword ptr [rcx+0Ch], 0
0x140044abe  jnz     loc_140045206
0x140044ac4  mov     ebx, 0C0000034h
0x140044ac9  mov     rax, qword ptr [rsp+140h+var_E0+8]
0x140044ace  mov     rcx, [rax+528h]
0x140044ad5  cmp     dword ptr [rcx+0Ch], 0
0x140044ad9  jnz     loc_14004539C
0x140044adf  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044ae6  jnz     loc_1400457AE
0x140044aec  cmp     ebx, 0C0000034h
0x140044af2  jnz     loc_140044E9C
0x140044af8  cmp     byte ptr [rsp+140h+var_F0+1], 0
0x140044afd  jz      loc_140045073
0x140044b03  mov     [rbp+40h+Str], r13
0x140044b07  mov     rdi, r13
0x140044b0a  mov     [rbp+40h+arg_10], r13d
0x140044b0e  mov     dword ptr [rbp+40h+arg_8], r13d
0x140044b12  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140044b19  jnz     loc_140045444
0x140044b1f  mov     rax, qword ptr [rsp+140h+var_E0+8]
0x140044b24  mov     rcx, [rax+528h]
0x140044b2b  cmp     dword ptr [rcx+0Ch], 0
0x140044b2f  jnz     loc_1400452B5
0x140044b35  mov     ebx, 0C0000034h
0x140044b3a  mov     rax, qword ptr [rsp+140h+var_E0+8]
0x140044b3f  mov     rcx, [rax+528h]
0x140044b46  cmp     dword ptr [rcx+0Ch], 0
0x140044b4a  jnz     loc_14004526B
  ... truncated ...
```
