# MicrodomImplementation::CMicrodom::FetchProperties(ulong,unsigned __int64,ulong const * const,Windows::Microdom::Rtl::NodePropertyResult * const)

- ea: `0x1800135d0`
- end: `0x18001428c`
- name: `?FetchProperties@CMicrodom@MicrodomImplementation@@QEAAJK_KQEBKQEAUNodePropertyResult@Rtl@Microdom@Windows@@@Z`
- size: `3260`
- prototype: `__int64 __usercall@<rax>(MicrodomImplementation::CMicrodom *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, const unsigned int *const@<r9>, struct Windows::Microdom::Rtl::NodePropertyResult *const)`
- caller_count: `8`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014fc0`
- `0x180057170`
- `0x180057200`
- `0x180057290`
- `0x180057320`
- `0x1800573b0`
- `0x180057440`
- `0x1800574d0`

## callees

- `0x1800031e0`
- `0x1800100a0`
- `0x180012790`
- `0x1800134d0`
- `0x1800135d0`
- `0x180014e00`
- `0x18001fd10`
- `0x180022eb0`
- `0x1800547e0`
- `0x180056e84`
- `0x180057054`

## string_xrefs

- `0x180014173`: `onecore\base\xml\udom_microdom.cpp`
- `0x18001419a`: `onecore\base\xml\udom_microdom.cpp`
- `0x1800141c1`: `onecore\base\xml\udom_microdom.cpp`
- `0x1800141d4`: `MicrodomImplementation::CDomPositionCache::GetLocation`
- `0x1800141ad`: `MicrodomImplementation::CDomLayoutCache::FindObject`
- `0x180014186`: `MicrodomImplementation::CStringpoolCache::FindString`

## pseudocode

```c
int __fastcall MicrodomImplementation::CMicrodom::FetchProperties(
        MicrodomImplementation::CMicrodom *this,
        unsigned int a2,
        struct _LUTF8_STRING *a3,
        const unsigned int *a4,
        struct Windows::Microdom::Rtl::NodePropertyResult *const a5)
{
  struct Windows::Microdom::Rtl::NodePropertyResult *v5; // r14
  MicrodomImplementation::CDomLayoutCache *v6; // r13
  struct _LUTF8_STRING *v7; // rsi
  MicrodomImplementation::CMicrodom *v8; // r12
  unsigned int v9; // r15d
  int result; // eax
  __int64 v11; // rdx
  struct _LUTF8_STRING *v12; // rdi
  struct _MICRODOM_DOM_NODE_HEADER *v13; // rbx
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  _DWORD *v19; // rdx
  __int64 v20; // rax
  int Children; // eax
  __int64 v22; // r13
  char *v23; // r14
  __int64 v24; // rdx
  __int64 v25; // r12
  __int64 v26; // r15
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // rdi
  unsigned __int64 v30; // rax
  size_t v31; // rdx
  unsigned __int64 v32; // rax
  _QWORD *v33; // rax
  _QWORD *v34; // rsi
  _QWORD *v35; // rdx
  _QWORD *v36; // rcx
  _QWORD *v37; // rbx
  __int64 v38; // rbx
  _QWORD *v39; // rax
  _QWORD *v40; // rcx
  int v41; // eax
  unsigned __int64 v42; // r15
  int v43; // edx
  char *v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // rax
  char *v47; // rcx
  struct _LUTF8_STRING *v48; // rax
  __int64 v49; // rdx
  char *v50; // rcx
  __int64 v51; // r8
  char *v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // rcx
  char v55; // al
  unsigned int v56; // eax
  __int64 v57; // rax
  char v58; // al
  char v59; // al
  int v60; // r14d
  __int64 v61; // rsi
  __int64 v62; // rdi
  char v63; // al
  __int64 v64; // rax
  unsigned __int64 v65; // r8
  __int64 v66; // r10
  __int64 v67; // rcx
  unsigned __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // rbx
  __int64 *v71; // rdx
  unsigned __int64 v72; // r8
  __int64 v73; // r9
  unsigned __int64 v74; // rcx
  char *v75; // rcx
  __int64 v76; // rax
  __int16 v77; // dx
  __int64 v78; // rax
  _DWORD *v79; // rdx
  __int128 v80; // xmm0
  __int64 v81; // rax
  unsigned int v82; // eax
  __int64 v83; // rax
  char v84; // al
  __int64 v85; // rsi
  __int64 v86; // rdi
  char v87; // al
  __int64 v88; // rax
  unsigned __int64 v89; // r8
  __int64 v90; // r10
  __int64 v91; // rcx
  unsigned __int64 v92; // rdx
  __int64 v93; // rax
  __int64 v94; // rbx
  __int64 *v95; // rdx
  unsigned __int64 v96; // r8
  __int64 v97; // r9
  __int64 v98; // rcx
  __int64 i; // rcx
  _DWORD *v100; // rdx
  _DWORD *v101; // rcx
  int v102; // eax
  unsigned __int64 v103; // rcx
  unsigned __int16 *v104; // rcx
  unsigned __int8 *v105; // rcx
  __int64 v106; // rcx
  __int64 v107; // rax
  const char *v108; // rax
  struct _LUTF8_STRING *v109[2]; // [rsp+20h] [rbp-51h] BYREF
  unsigned int v110[4]; // [rsp+30h] [rbp-41h] BYREF
  __int64 v111; // [rsp+40h] [rbp-31h]
  const char *v112; // [rsp+48h] [rbp-29h]
  struct _LUTF8_STRING *v113; // [rsp+50h] [rbp-21h]
  struct _MICRODOM_DOM_NODE_HEADER *v114; // [rsp+58h] [rbp-19h]
  struct _MICRODOM_DOM_NODE_HEADER *v115; // [rsp+60h] [rbp-11h] BYREF
  struct Windows::Microdom::Rtl::NodePropertyResult *v116; // [rsp+68h] [rbp-9h]
  unsigned int v117; // [rsp+70h] [rbp-1h]
  MicrodomImplementation::CMicrodom *v118; // [rsp+78h] [rbp+7h]
  const unsigned int *v119; // [rsp+80h] [rbp+Fh]
  MicrodomImplementation::CDomLayoutCache *v120; // [rsp+88h] [rbp+17h]

  v5 = a5;
  v6 = (MicrodomImplementation::CMicrodom *)((char *)this + 48);
  v7 = a3;
  v113 = a3;
  v8 = this;
  v118 = this;
  v119 = a4;
  v117 = a2;
  v9 = a2;
  v116 = a5;
  v115 = 0;
  v120 = (MicrodomImplementation::CMicrodom *)((char *)this + 48);
  result = MicrodomImplementation::CDomLayoutCache::FindObject(
             (MicrodomImplementation::CMicrodom *)((char *)this + 48),
             a2,
             &v115);
  if ( result < 0 )
    return result;
  v11 = 0;
  v12 = 0;
  v109[0] = 0;
  if ( !v7 )
    return 0;
  v13 = v115;
  v114 = v115;
  while ( 1 )
  {
    v14 = v119[(_QWORD)v12];
    if ( v14 <= 0x2000 )
      break;
    switch ( v14 )
    {
      case 0x2001u:
        result = MicrodomImplementation::CMicrodom::ExtractChildren(v8, v9);
        if ( result < 0 )
          return result;
        v45 = *((_QWORD *)v8 + 75) + 40LL;
        v46 = 3LL * (_QWORD)v12;
        *((_DWORD *)v5 + 2 * v46) = 2;
        *((_QWORD *)v5 + v46 + 1) = 152LL * v9 + v45;
        break;
      case 0x2002u:
        result = MicrodomImplementation::CMicrodom::ExtractChildren(v8, v9);
        if ( result < 0 )
          return result;
        v49 = *((_QWORD *)v8 + 75) + 152LL * v9;
        v50 = (char *)v5 + 24 * (_QWORD)v12;
        *(_DWORD *)v50 = 4;
        if ( *(_QWORD *)(v49 + 48) )
        {
          *(_OWORD *)(v50 + 8) = *(_OWORD *)*(_QWORD *)(v49 + 40);
        }
        else
        {
          *(_OWORD *)v110 = 0;
          v110[2] = -1;
          *(_OWORD *)(v50 + 8) = *(_OWORD *)v110;
        }
        break;
      case 0x2003u:
        result = MicrodomImplementation::CMicrodom::ExtractChildren(v8, v9);
        if ( result < 0 )
          return result;
        v51 = *((_QWORD *)v8 + 75) + 152LL * v9;
        v52 = (char *)v5 + 24 * (_QWORD)v12;
        *(_DWORD *)v52 = 4;
        v53 = *(_QWORD *)(v51 + 48);
        if ( v53 )
        {
          *(_OWORD *)(v52 + 8) = *(_OWORD *)(*(_QWORD *)(v51 + 40) + 16 * v53 - 16);
        }
        else
        {
          *(_OWORD *)v110 = 0;
          v110[2] = -1;
          *(_OWORD *)(v52 + 8) = *(_OWORD *)v110;
        }
        break;
      case 0x2004u:
        v54 = 0;
        v55 = *(_BYTE *)v13 & 0xF;
        if ( v55 == 1 )
        {
          v56 = *((_DWORD *)v13 + 5);
          goto LABEL_76;
        }
        if ( v55 != 2 )
          goto LABEL_79;
        v56 = *((_DWORD *)v13 + 3);
        goto LABEL_76;
      case 0x2005u:
        v54 = 0;
        v58 = *(_BYTE *)v13 & 0xF;
        if ( v58 == 1 )
        {
          v56 = *((_DWORD *)v13 + 4);
        }
        else
        {
          if ( v58 != 2 )
            goto LABEL_79;
          v56 = *((_DWORD *)v13 + 2);
        }
LABEL_76:
        if ( v56 != -1 )
        {
          if ( (unsigned __int64)v56 >= *((_QWORD *)v8 + 5) )
            goto LABEL_184;
          v54 = *((_QWORD *)v8 + 4) + 24LL * v56;
        }
LABEL_79:
        v57 = 3LL * (_QWORD)v12;
        *((_DWORD *)v5 + 2 * v57) = 1;
        *((_QWORD *)v5 + v57 + 1) = v54;
        break;
      case 0x2006u:
        v59 = *(_BYTE *)v13 & 0xF;
        v60 = -1;
        *(_OWORD *)v110 = 0;
        if ( v59 == 7 || v59 == 2 )
          goto LABEL_116;
        v61 = *((_QWORD *)v8 + 75) + 152LL * v9;
        if ( *(_DWORD *)(v61 + 80) != -1 )
          goto LABEL_105;
        LODWORD(v62) = v9;
        if ( !v9 )
          goto LABEL_104;
        while ( 2 )
        {
          v62 = (unsigned int)(v62 - 1);
          if ( (unsigned int)v62 >= *(_DWORD *)(*((_QWORD *)v6 + 6) + 8LL) )
            goto LABEL_185;
          result = MicrodomImplementation::CDomLayoutCache::AdvanceCachedPointer(v6, v62);
          if ( result < 0 )
            return result;
          _mm_lfence();
          v63 = **(_BYTE **)(*(_QWORD *)v6 + 40 * v62 + 8) & 0xF;
          if ( v63 != 1 && v63 != 7 )
            goto LABEL_101;
          result = MicrodomImplementation::CMicrodom::ExtractChildren(v8, v62);
          if ( result < 0 )
            return result;
          v64 = *((_QWORD *)v8 + 75);
          v65 = *(_QWORD *)(152LL * (unsigned int)v62 + v64 + 48);
          v66 = 152LL * (unsigned int)v62 + v64;
          if ( v65 )
          {
            v67 = 0;
            while ( *(_DWORD *)(*(_QWORD *)(152LL * (unsigned int)v62 + v64 + 40) + 16 * v67 + 8) != v9 )
            {
              if ( ++v67 >= v65 )
                goto LABEL_97;
            }
          }
          else
          {
LABEL_97:
            v68 = *(_QWORD *)(v66 + 64);
            if ( !v68 )
            {
LABEL_101:
              if ( !(_DWORD)v62 )
                goto LABEL_104;
              continue;
            }
            v69 = 0;
            while ( *(_DWORD *)(*(_QWORD *)(v66 + 56) + 16 * v69 + 8) != v9 )
            {
              if ( ++v69 >= v68 )
                goto LABEL_101;
            }
          }
          break;
        }
        *(_DWORD *)(v61 + 80) = v62;
LABEL_104:
        v12 = v109[0];
LABEL_105:
        v70 = *(unsigned int *)(v61 + 80);
        result = MicrodomImplementation::CMicrodom::ExtractChildren(v8, *(_DWORD *)(v61 + 80));
        if ( result < 0 )
          return result;
        if ( (_DWORD)v70 == v9 )
          goto LABEL_115;
        v71 = (__int64 *)(152 * v70 + *((_QWORD *)v8 + 75) + 40LL);
        if ( !v71 )
          goto LABEL_115;
        v72 = v71[1];
        if ( !v72 )
          goto LABEL_190;
        v73 = *v71;
        v74 = 0;
        while ( *(_DWORD *)(v73 + 16 * v74 + 8) != v9 )
        {
          if ( ++v74 >= v72 )
            goto LABEL_115;
        }
        if ( v74 < v72 - 1 )
          v60 = *(_DWORD *)(v73 + 16 * v74 + 24);
        goto LABEL_115;
      case 0x2007u:
        goto LABEL_61;
      case 0x2008u:
        v77 = 32;
        switch ( *(_BYTE *)v13 & 0xF )
        {
          case 1:
            v77 = 1;
            break;
          case 2:
            v77 = 2;
            break;
          case 3:
            v77 = 3;
            break;
          case 4:
            v77 = 5;
            break;
          case 5:
            v77 = 7;
            break;
          case 6:
            v77 = 8;
            break;
          case 7:
            v77 = 9;
            break;
          default:
            break;
        }
        v78 = 3LL * (_QWORD)v12;
        *((_DWORD *)v5 + 2 * v78) = 6;
        *((_WORD *)v5 + 4 * v78 + 4) = v77;
        break;
      case 0x2009u:
        goto LABEL_126;
      case 0x200Au:
        v79 = (_DWORD *)((char *)v5 + 24 * (_QWORD)v12);
        *v79 = 9;
        v79[4] = *(_DWORD *)(*((_QWORD *)v8 + 12) + 16LL);
        break;
      case 0x200Bu:
        *(_OWORD *)v110 = 0;
        v110[2] = -1;
        result = MicrodomImplementation::CMicrodom::GetParent(v8, v9, &v110[2]);
        if ( result < 0 )
          return result;
        v80 = *(_OWORD *)v110;
        v81 = 3LL * (_QWORD)v12;
        *((_DWORD *)v5 + 2 * v81) = 4;
        *(_OWORD *)((char *)v5 + 8 * v81 + 8) = v80;
        break;
      case 0x200Cu:
        if ( (*(_BYTE *)v13 & 0xF) == 1 )
        {
          v82 = *((_DWORD *)v13 + 3);
        }
        else
        {
          if ( (*(_BYTE *)v13 & 0xF) != 2 )
            goto LABEL_137;
          v82 = *((_DWORD *)v13 + 1);
        }
        if ( v82 != -1 )
        {
          if ( (unsigned __int64)v82 >= *((_QWORD *)v8 + 5) )
          {
LABEL_184:
            v111 = 4066;
            *(_QWORD *)v110 = "onecore\\base\\xml\\udom_microdom.cpp";
            *(_QWORD *)&v110[2] = "MicrodomImplementation::CStringpoolCache::FindString";
            v108 = "StringId < m_Entries.Length";
            goto LABEL_187;
          }
          v11 = *((_QWORD *)v8 + 4) + 24LL * v82;
        }
LABEL_137:
        v83 = 3LL * (_QWORD)v12;
        *((_DWORD *)v5 + 2 * v83) = 1;
        *((_QWORD *)v5 + v83 + 1) = v11;
        break;
      case 0x200Du:
        v84 = *(_BYTE *)v13 & 0xF;
        v60 = -1;
        *(_OWORD *)v110 = 0;
        if ( v84 == 7 || v84 == 2 )
          goto LABEL_116;
        v85 = *((_QWORD *)v8 + 75) + 152LL * v9;
        if ( *(_DWORD *)(v85 + 80) != -1 )
          goto LABEL_159;
        LODWORD(v86) = v9;
        if ( !v9 )
          goto LABEL_158;
        while ( 2 )
        {
          v86 = (unsigned int)(v86 - 1);
          if ( (unsigned int)v86 >= *(_DWORD *)(*((_QWORD *)v6 + 6) + 8LL) )
          {
LABEL_185:
            v111 = 3861;
            *(_QWORD *)v110 = "onecore\\base\\xml\\udom_microdom.cpp";
            *(_QWORD *)&v110[2] = "MicrodomImplementation::CDomLayoutCache::FindObject";
            v108 = "ulIndex < m_Header->ulTotalNodeCount";
            goto LABEL_187;
          }
          result = MicrodomImplementation::CDomLayoutCache::AdvanceCachedPointer(v6, v86);
          if ( result < 0 )
            return result;
          _mm_lfence();
          v87 = **(_BYTE **)(*(_QWORD *)v6 + 40 * v86 + 8) & 0xF;
          if ( v87 != 1 && v87 != 7 )
          {
LABEL_155:
            if ( !(_DWORD)v86 )
              goto LABEL_158;
            continue;
          }
          break;
        }
        result = MicrodomImplementation::CMicrodom::ExtractChildren(v8, v86);
        if ( result < 0 )
          return result;
        v88 = *((_QWORD *)v8 + 75);
        v89 = *(_QWORD *)(152LL * (unsigned int)v86 + v88 + 48);
        v90 = 152LL * (unsigned int)v86 + v88;
        if ( v89 )
        {
          v91 = 0;
          while ( *(_DWORD *)(*(_QWORD *)(152LL * (unsigned int)v86 + v88 + 40) + 16 * v91 + 8) != v9 )
          {
            if ( ++v91 >= v89 )
              goto LABEL_151;
          }
        }
        else
        {
LABEL_151:
          v92 = *(_QWORD *)(v90 + 64);
          if ( !v92 )
            goto LABEL_155;
          v93 = 0;
          while ( *(_DWORD *)(*(_QWORD *)(v90 + 56) + 16 * v93 + 8) != v9 )
          {
            if ( ++v93 >= v92 )
              goto LABEL_155;
          }
        }
        *(_DWORD *)(v85 + 80) = v86;
LABEL_158:
        v12 = v109[0];
LABEL_159:
        v94 = *(unsigned int *)(v85 + 80);
        result = MicrodomImplementation::CMicrodom::ExtractChildren(v8, *(_DWORD *)(v85 + 80));
        if ( result < 0 )
          return result;
        if ( (_DWORD)v94 != v9 )
        {
          v95 = (__int64 *)(152 * v94 + *((_QWORD *)v8 + 75) + 40LL);
          if ( v95 )
          {
            v96 = v95[1];
            if ( !v96 )
              goto LABEL_190;
            v97 = *v95;
            v98 = 0;
            while ( *(_DWORD *)(v97 + 16 * v98 + 8) != v9 )
            {
              if ( ++v98 >= v96 )
                goto LABEL_115;
            }
            if ( v98 )
              v60 = *(_DWORD *)(v97 + 16 * v98 - 8);
          }
        }
LABEL_115:
        v13 = v114;
        v7 = v113;
LABEL_116:
        v75 = (char *)v116 + 24 * (_QWORD)v12;
        v76 = *(_QWORD *)v110;
        *((_DWORD *)v75 + 4) = v60;
        v5 = v116;
        *((_QWORD *)v75 + 1) = v76;
        *((_DWORD *)v75 + 5) = v110[3];
        *(_DWORD *)v75 = 4;
        break;
      case 0x200Eu:
        if ( (unsigned __int64)v9 >= *((_QWORD *)v8 + 59) )
        {
          v111 = 3520;
          *(_QWORD *)v110 = "onecore\\base\\xml\\udom_microdom.cpp";
          *(_QWORD *)&v110[2] = "MicrodomImplementation::CDomPositionCache::GetLocation";
          v108 = "ulLocation < m_PositionList.Length";
LABEL_187:
          v112 = v108;
          RtlReportErrorOrigination(v110, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
          return -1073741811;
        }
        if ( !*((_QWORD *)v8 + 61) )
        {
LABEL_190:
          INTERNAL_ERROR_ACTION(-1073741595);
          __debugbreak();
        }
        for ( i = *((unsigned int *)v8 + 120); (unsigned int)i <= v9; i = *((unsigned int *)v8 + 120) )
        {
          *((_DWORD *)v8 + 120) = i + 1;
          v100 = (_DWORD *)(*((_QWORD *)v8 + 58) + 8 * i);
          switch ( *((_DWORD *)v8 + 121) )
          {
            case 1:
              v105 = (unsigned __int8 *)*((_QWORD *)v8 + 61);
              *v100 = *v105;
              v102 = v105[1];
              v103 = (unsigned __int64)(v105 + 6);
              break;
            case 2:
              v104 = (unsigned __int16 *)*((_QWORD *)v8 + 61);
              *v100 = *v104;
              v102 = v104[1];
              v103 = (unsigned __int64)v104 + 9;
              break;
            case 3:
              v101 = (_DWORD *)*((_QWORD *)v8 + 61);
              *v100 = *v101;
              v102 = v101[1];
              v103 = (unsigned __int64)v101 + 15;
              break;
            default:
              goto LABEL_190;
          }
          v100[1] = v102;
          *((_QWORD *)v8 + 61) = v103 & 0xFFFFFFFFFFFFFFFCuLL;
        }
        v106 = *((_QWORD *)v8 + 58) + 8LL * v9;
        v107 = 3LL * (_QWORD)v12;
        *((_DWORD *)v5 + 2 * v107) = 10;
        *((_QWORD *)v5 + v107 + 1) = v106;
        break;
      default:
        break;
    }
LABEL_180:
    v12 = (struct _LUTF8_STRING *)((char *)v12 + 1);
    v109[0] = v12;
    if ( v12 == v7 )
      return 0;
    v11 = 0;
  }
  if ( v14 != 0x2000 )
  {
    v15 = v14 - 256;
    if ( !v15 )
    {
      v20 = 3LL * (_QWORD)v12;
      memset(v110, 0, sizeof(v110));
      *(_OWORD *)((char *)v5 + 8 * v20) = 0u;
      *((_QWORD *)v5 + v20 + 2) = 0;
      goto LABEL_180;
    }
    v16 = v15 - 259;
    if ( v16 )
    {
      v17 = v16 - 1277;
      if ( !v17 )
      {
LABEL_61:
        v109[0] = 0;
        result = MicrodomImplementation::CMicrodom::GetNodeName(v8, v9, v13, v109);
LABEL_62:
        if ( result < 0 )
          return result;
        v47 = (char *)v5 + 24 * (_QWORD)v12;
        v48 = v109[0];
        *(_DWORD *)v47 = 1;
        *((_QWORD *)v47 + 1) = v48;
        goto LABEL_180;
      }
      v18 = v17 - 1;
      if ( v18 )
      {
        if ( v18 == 511 )
        {
          v19 = (_DWORD *)((char *)v5 + 24 * (_QWORD)v12);
          *v19 = 4;
          v19[4] = *(_DWORD *)(*((_QWORD *)v8 + 12) + 12LL);
        }
        goto LABEL_180;
      }
    }
LABEL_126:
    v109[0] = 0;
    result = MicrodomImplementation::CMicrodom::GetNodeValue(v8, v9, v13, v109);
    goto LABEL_62;
  }
  *(_OWORD *)v110 = 0;
  Children = MicrodomImplementation::CMicrodom::ExtractChildren(v8, v9);
  if ( Children >= 0 )
  {
    v22 = *((_QWORD *)v8 + 75) + 152LL * v9;
    if ( (*(_BYTE *)v13 & 0xF) != 1 || *(_DWORD *)(v22 + 8) != -1 )
      goto LABEL_57;
    v23 = (char *)v8 + 576;
    v24 = *((_QWORD *)v8 + 74);
    v25 = *((_QWORD *)v8 + 72);
    v26 = *((_QWORD *)v118 + 73);
    if ( v26 != v24 )
      goto LABEL_45;
    v27 = (v24 - v25) >> 3;
    if ( v27 == -1 )
    {
      LODWORD(v28) = -1073741675;
      return v28;
    }
    if ( v27 + 1 < v27 )
      goto LABEL_44;
    if ( v27 >= 0x80 )
    {
      if ( !HIDWORD(v27) )
      {
        v29 = 4LL * (unsigned int)v27;
        goto LABEL_27;
      }
      if ( ((4 * HIDWORD(v27)) & 0xFFFFFFFF00000000uLL) == 0 )
      {
        v30 = 4LL * (unsigned int)v27;
        v29 = (HIDWORD(v27) << 34) + v30;
        LODWORD(v28) = v29 < v30 ? 0xC0000095 : 0;
        if ( v29 >= v30 )
          goto LABEL_27;
        goto LABEL_51;
      }
    }
    else
    {
      v29 = v27 + 128;
      if ( v27 + 128 < v27 )
      {
        LODWORD(v28) = -1073741675;
        return v28;
      }
LABEL_27:
      if ( v27 + 1 > v29 )
        v29 = v27 + 1;
      if ( v29 >= 0x1FFFFFFFFFFFFFFFLL )
      {
        LODWORD(v28) = -1073741801;
        return v28;
      }
      if ( v29 <= v27 )
        goto LABEL_43;
      if ( !HIDWORD(v29) )
      {
        v31 = 8LL * (unsigned int)v29;
        goto LABEL_36;
      }
      if ( ((8 * HIDWORD(v29)) & 0xFFFFFFFF00000000uLL) == 0 )
      {
        v32 = 8LL * (unsigned int)v29;
        v31 = (HIDWORD(v29) << 35) + v32;
        LODWORD(v28) = v31 < v32 ? 0xC0000095 : 0;
        if ( v31 >= v32 )
        {
LABEL_36:
          v33 = operator new(v31);
          v34 = v33;
          if ( !v33 )
          {
            LODWORD(v28) = -1073741801;
            goto LABEL_51;
          }
          v35 = *(_QWORD **)v23;
          v36 = v33;
          v37 = (_QWORD *)*((_QWORD *)v23 + 1);
          if ( *(_QWORD **)v23 != v37 )
          {
            do
            {
              if ( v36 )
                *v36 = *v35;
              v37 = (_QWORD *)*((_QWORD *)v23 + 1);
              ++v35;
              ++v36;
            }
            while ( v35 != v37 );
          }
          v38 = ((__int64)v37 - *(_QWORD *)v23) >> 3;
          BUCL::CVector<Windows::Vector<Windows::Microdom::Rtl::Node const> *,BUCL::Rtl::CCallDisposition>::Close(v23);
          v39 = &v34[v38];
          *(_QWORD *)v23 = v34;
          v13 = v114;
          *((_QWORD *)v23 + 1) = v39;
          *((_QWORD *)v23 + 2) = &v34[v29];
LABEL_43:
          v12 = v109[0];
LABEL_44:
          v7 = v113;
LABEL_45:
          v40 = (_QWORD *)*((_QWORD *)v23 + 1);
          if ( v40 )
            *v40 = v22 + 56;
          *((_QWORD *)v23 + 1) += 8LL;
          v41 = 0;
          v42 = (v26 - v25) >> 3;
          v115 = 0;
          if ( v42 > 0xFFFFFFFF )
          {
            HIDWORD(v115) = -1073741675;
          }
          else
          {
            v41 = v42;
            LODWORD(v115) = v42;
            if ( v42 == (unsigned int)v42 )
              HIDWORD(v115) = 0;
            else
              HIDWORD(v115) = -1073741595;
          }
          v28 = (unsigned __int64)v115 >> 32;
          *(_DWORD *)(v22 + 8) = v41;
          if ( (v28 & 0x80000000) != 0LL )
            return v28;
          v5 = v116;
LABEL_57:
          v43 = *(_DWORD *)(v22 + 8);
          v9 = v117;
          v8 = v118;
          v44 = (char *)v5 + 24 * (_QWORD)v12;
          v6 = v120;
          *((_QWORD *)v44 + 1) = *(_QWORD *)v110;
          *((_DWORD *)v44 + 5) = v110[3];
          *(_DWORD *)v44 = 3;
          *((_DWORD *)v44 + 4) = v43;
          goto LABEL_180;
        }
LABEL_51:
        if ( (v28 & 0x80000000) != 0LL )
          return v28;
        goto LABEL_43;
      }
    }
    LODWORD(v28) = -1073741675;
    goto LABEL_51;
  }
  LODWORD(v28) = Children;
  return v28;
}

```

## disassembly

```asm
0x1800135d0  push    rbp
0x1800135d2  push    rsi
0x1800135d3  push    r12
0x1800135d5  push    r13
0x1800135d7  push    r14
0x1800135d9  push    r15
0x1800135db  lea     rbp, [rsp-27h]
0x1800135e0  sub     rsp, 98h
0x1800135e7  mov     r14, [rbp+4Fh+arg_20]
0x1800135eb  lea     r13, [rcx+30h]
0x1800135ef  mov     rsi, r8
0x1800135f2  mov     [rbp+4Fh+var_70], r8
0x1800135f6  mov     r12, rcx
0x1800135f9  mov     [rbp+4Fh+var_48], rcx
0x1800135fd  mov     rcx, r13; this
0x180013600  mov     [rbp+4Fh+var_40], r9
0x180013604  lea     r8, [rbp+4Fh+var_60]; struct _MICRODOM_DOM_NODE_HEADER **
0x180013608  mov     [rbp+4Fh+var_50], edx
0x18001360b  mov     r15d, edx
0x18001360e  mov     [rbp+4Fh+var_58], r14
0x180013612  mov     [rbp+4Fh+var_60], 0
0x18001361a  mov     [rbp+4Fh+var_38], r13
0x18001361e  call    ?FindObject@CDomLayoutCache@MicrodomImplementation@@QEAAJKAEAPEBU_MICRODOM_DOM_NODE_HEADER@@@Z; MicrodomImplementation::CDomLayoutCache::FindObject(ulong,_MICRODOM_DOM_NODE_HEADER const * &)
0x180013623  test    eax, eax
0x180013625  js      loc_180014219
0x18001362b  xor     edx, edx
0x18001362d  mov     [rsp+0C0h+arg_10], rbx
0x180013635  mov     [rsp+0C0h+var_30], rdi
0x18001363d  mov     edi, edx
0x18001363f  mov     [rbp+4Fh+var_A0], rdx
0x180013643  test    rsi, rsi
0x180013646  jz      loc_180014207
0x18001364c  mov     rbx, [rbp+4Fh+var_60]
0x180013650  mov     r8d, 0FFFFFFFFh
0x180013656  mov     [rbp+4Fh+var_68], rbx
0x18001365a  mov     r9d, 1
0x180013660  mov     rax, [rbp+4Fh+var_40]
0x180013664  lea     r10, __ImageBase
0x18001366b  mov     r11d, 9
0x180013671  mov     ecx, 20h ; ' '
0x180013676  mov     eax, [rax+rdi*4]
0x180013679  cmp     eax, 2000h
0x18001367e  ja      loc_1800139BB
0x180013684  jz      short loc_1800136F8
0x180013686  sub     eax, 100h
0x18001368b  jz      short loc_1800136D5
0x18001368d  sub     eax, 103h
0x180013692  jz      loc_180013DED; jumptable 00000001800139D4 case 8201
0x180013698  sub     eax, 4FDh
0x18001369d  jz      loc_180013A22; jumptable 00000001800139D4 case 8199
0x1800136a3  sub     eax, 1
0x1800136a6  jz      loc_180013DED; jumptable 00000001800139D4 case 8201
0x1800136ac  cmp     eax, 1FFh
0x1800136b1  jnz     def_1800139D4; jumptable 00000001800139D4 default case
0x1800136b7  lea     rax, [rdi+rdi*2]
0x1800136bb  lea     rdx, [r14+rax*8]
0x1800136bf  mov     dword ptr [rdx], 4
0x1800136c5  mov     rax, [r12+60h]
0x1800136ca  mov     ecx, [rax+0Ch]
0x1800136cd  mov     [rdx+10h], ecx
0x1800136d0  jmp     def_1800139D4; jumptable 00000001800139D4 default case
0x1800136d5  lea     rax, [rdi+rdi*2]
0x1800136d9  mov     qword ptr [rbp+4Fh+var_90], 0
0x1800136e1  mov     qword ptr [rbp+4Fh+var_90+8], rdx
0x1800136e5  movups  xmm0, xmmword ptr [rbp+4Fh+var_90]
0x1800136e9  movups  xmmword ptr [r14+rax*8], xmm0
0x1800136ee  mov     [r14+rax*8+10h], rdx
0x1800136f3  jmp     def_1800139D4; jumptable 00000001800139D4 default case
0x1800136f8  xorps   xmm0, xmm0
0x1800136fb  mov     edx, r15d; unsigned int
0x1800136fe  mov     rcx, r12; this
0x180013701  movups  xmmword ptr [rbp+4Fh+var_90], xmm0
0x180013705  call    ?ExtractChildren@CMicrodom@MicrodomImplementation@@QEAAJK@Z; MicrodomImplementation::CMicrodom::ExtractChildren(ulong)
0x18001370a  test    eax, eax
0x18001370c  js      loc_18001416A
0x180013712  mov     eax, r15d
0x180013715  imul    r13, rax, 98h
0x18001371c  movzx   eax, byte ptr [rbx]
0x18001371f  add     r13, [r12+258h]
0x180013727  and     al, 0Fh
0x180013729  cmp     al, 1
0x18001372b  jnz     loc_180013981
0x180013731  mov     r9d, 0FFFFFFFFh
0x180013737  cmp     [r13+8], r9d
0x18001373b  jnz     loc_180013981
0x180013741  mov     r15, [rbp+4Fh+var_48]
0x180013745  lea     r14, [r12+240h]
0x18001374d  mov     rdx, [r14+10h]
0x180013751  mov     r12, [r14]
0x180013754  mov     r15, [r15+248h]
0x18001375b  cmp     r15, rdx
0x18001375e  jnz     loc_180013900
0x180013764  sub     rdx, r12
0x180013767  sar     rdx, 3
0x18001376b  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18001376f  jnz     short loc_18001377B
0x180013771  mov     ecx, 0C0000095h
0x180013776  jmp     loc_180013948
0x18001377b  lea     r8, [rdx+1]
0x18001377f  cmp     r8, rdx
0x180013782  jbe     loc_1800138F6
0x180013788  cmp     rdx, 80h
0x18001378f  jnb     short loc_1800137A7
0x180013791  lea     rdi, [rdx+80h]
0x180013798  cmp     rdi, rdx
0x18001379b  jnb     short loc_1800137FA
0x18001379d  mov     ecx, 0C0000095h
0x1800137a2  jmp     loc_180013944
0x1800137a7  mov     rax, rdx
0x1800137aa  shr     rax, 20h
0x1800137ae  test    eax, eax
0x1800137b0  jnz     short loc_1800137BA
0x1800137b2  mov     edi, edx
0x1800137b4  shl     rdi, 2
0x1800137b8  jmp     short loc_1800137FA
0x1800137ba  mov     rcx, rax
0x1800137bd  mov     rax, 0FFFFFFFF00000000h
0x1800137c7  shl     rcx, 2
0x1800137cb  test    rax, rcx
0x1800137ce  jnz     loc_18001393B
0x1800137d4  shl     rcx, 20h
0x1800137d8  mov     eax, edx
0x1800137da  lea     rax, ds:0[rax*4]
0x1800137e2  lea     rdi, [rcx+rax]
0x1800137e6  cmp     rdi, rax
0x1800137e9  sbb     ecx, ecx
0x1800137eb  and     ecx, 0C0000095h
0x1800137f1  cmp     rdi, rax
0x1800137f4  jb      loc_180013940
0x1800137fa  cmp     r8, rdi
0x1800137fd  mov     rax, 1FFFFFFFFFFFFFFFh
0x180013807  cmova   rdi, r8
0x18001380b  cmp     rdi, rax
0x18001380e  jb      short loc_18001381A
0x180013810  mov     ecx, 0C0000017h
0x180013815  jmp     loc_180013944
0x18001381a  cmp     rdi, rdx
0x18001381d  jbe     loc_1800138F2
0x180013823  mov     rax, rdi
0x180013826  shr     rax, 20h
0x18001382a  test    eax, eax
0x18001382c  jnz     short loc_180013836
0x18001382e  mov     edx, edi
0x180013830  shl     rdx, 3
0x180013834  jmp     short loc_180013876
0x180013836  mov     rcx, rax
0x180013839  mov     rax, 0FFFFFFFF00000000h
0x180013843  shl     rcx, 3
0x180013847  test    rax, rcx
0x18001384a  jnz     loc_18001393B
0x180013850  shl     rcx, 20h
0x180013854  mov     eax, edi
0x180013856  lea     rax, ds:0[rax*8]
0x18001385e  lea     rdx, [rcx+rax]
0x180013862  cmp     rdx, rax
0x180013865  sbb     ecx, ecx
0x180013867  and     ecx, 0C0000095h
0x18001386d  cmp     rdx, rax
0x180013870  jb      loc_180013940
0x180013876  mov     rcx, rdx; Size
0x180013879  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001387e  mov     rsi, rax
0x180013881  test    rax, rax
0x180013884  jnz     short loc_18001389A
0x180013886  mov     rsi, [rbp+4Fh+var_70]
0x18001388a  mov     ecx, 0C0000017h
0x18001388f  mov     r9d, 0FFFFFFFFh
0x180013895  jmp     loc_180013940
0x18001389a  mov     rdx, [r14]
0x18001389d  mov     rcx, rsi
0x1800138a0  mov     rbx, [r14+8]
0x1800138a4  cmp     rdx, rbx
0x1800138a7  jz      short loc_1800138CC
0x1800138a9  nop     dword ptr [rax+00000000h]
0x1800138b0  test    rcx, rcx
0x1800138b3  jz      short loc_1800138BB
0x1800138b5  mov     rax, [rdx]
0x1800138b8  mov     [rcx], rax
0x1800138bb  mov     rbx, [r14+8]
0x1800138bf  add     rdx, 8
0x1800138c3  add     rcx, 8
0x1800138c7  cmp     rdx, rbx
0x1800138ca  jnz     short loc_1800138B0
0x1800138cc  sub     rbx, [r14]
0x1800138cf  mov     rcx, r14
0x1800138d2  sar     rbx, 3
0x1800138d6  call    ?Close@?$CVector@PEAU?$Vector@$$CBUNode@Rtl@Microdom@Windows@@@Windows@@VCCallDisposition@Rtl@BUCL@@@BUCL@@QEAAXXZ; BUCL::CVector<Windows::Vector<Windows::Microdom::Rtl::Node const> *,BUCL::Rtl::CCallDisposition>::Close(void)
0x1800138db  lea     rax, [rsi+rbx*8]
0x1800138df  mov     [r14], rsi
0x1800138e2  mov     rbx, [rbp+4Fh+var_68]
0x1800138e6  mov     [r14+8], rax
0x1800138ea  lea     rax, [rsi+rdi*8]
0x1800138ee  mov     [r14+10h], rax
0x1800138f2  mov     rdi, [rbp+4Fh+var_A0]
0x1800138f6  mov     rsi, [rbp+4Fh+var_70]
0x1800138fa  mov     r9d, 0FFFFFFFFh
0x180013900  mov     rcx, [r14+8]
0x180013904  test    rcx, rcx
0x180013907  jz      short loc_180013910
0x180013909  lea     rax, [r13+38h]
0x18001390d  mov     [rcx], rax
0x180013910  add     qword ptr [r14+8], 8
0x180013915  sub     r15, r12
0x180013918  xor     eax, eax
0x18001391a  sar     r15, 3
0x18001391e  mov     [rbp+4Fh+var_60], rax
0x180013922  cmp     r15, r9
0x180013925  ja      short loc_180013962
0x180013927  mov     eax, r15d
0x18001392a  mov     dword ptr [rbp+4Fh+var_60], eax
0x18001392d  cmp     r15, rax
0x180013930  jz      short loc_180013959
0x180013932  mov     dword ptr [rbp+4Fh+var_60+4], 0C00000E5h
0x180013939  jmp     short loc_180013969
0x18001393b  mov     ecx, 0C0000095h
0x180013940  test    ecx, ecx
0x180013942  jns     short loc_1800138F2
0x180013944  mov     rdi, [rbp+4Fh+var_A0]
0x180013948  mov     edx, r9d
0x18001394b  test    ecx, ecx
0x18001394d  js      loc_18001416C
0x180013953  mov     r14, [rbp+4Fh+var_58]
0x180013957  jmp     short loc_180013985
0x180013959  mov     dword ptr [rbp+4Fh+var_60+4], 0
0x180013960  jmp     short loc_180013969
0x180013962  mov     dword ptr [rbp+4Fh+var_60+4], 0C0000095h
0x180013969  mov     rcx, [rbp+4Fh+var_60]
0x18001396d  shr     rcx, 20h
0x180013971  mov     [r13+8], eax
0x180013975  test    ecx, ecx
0x180013977  js      loc_18001416C
0x18001397d  mov     r14, [rbp+4Fh+var_58]
0x180013981  mov     edx, [r13+8]
0x180013985  mov     r15d, [rbp+4Fh+var_50]
0x180013989  lea     rax, [rdi+rdi*2]
0x18001398d  mov     r12, [rbp+4Fh+var_48]
0x180013991  lea     rcx, [r14+rax*8]
0x180013995  mov     rax, qword ptr [rbp+4Fh+var_90]
0x180013999  mov     r8d, 0FFFFFFFFh
0x18001399f  mov     r13, [rbp+4Fh+var_38]
0x1800139a3  mov     [rcx+8], rax
0x1800139a7  mov     eax, [rbp+4Fh+var_90+0Ch]
0x1800139aa  mov     [rcx+14h], eax
0x1800139ad  mov     dword ptr [rcx], 3
0x1800139b3  mov     [rcx+10h], edx
0x1800139b6  jmp     loc_18001414D
0x1800139bb  add     eax, 0FFFFDFFFh; switch 14 cases
0x1800139c0  cmp     eax, 0Dh
0x1800139c3  ja      def_1800139D4; jumptable 00000001800139D4 default case
0x1800139c9  mov     eax, ds:(jpt_1800139D4 - 180000000h)[r10+rax*4]
0x1800139d1  add     rax, r10
0x1800139d4  jmp     rax; switch jump
0x1800139da  mov     edx, r15d; jumptable 00000001800139D4 case 8193
0x1800139dd  mov     rcx, r12; this
0x1800139e0  call    ?ExtractChildren@CMicrodom@MicrodomImplementation@@QEAAJK@Z; MicrodomImplementation::CMicrodom::ExtractChildren(ulong)
0x1800139e5  test    eax, eax
0x1800139e7  js      loc_180014209
0x1800139ed  mov     rdx, [r12+258h]
0x1800139f5  mov     r8d, 0FFFFFFFFh
0x1800139fb  mov     eax, r15d
0x1800139fe  add     rdx, 28h ; '('
0x180013a02  imul    rcx, rax, 98h
0x180013a09  lea     rax, [rdi+rdi*2]
0x180013a0d  add     rdx, rcx
0x180013a10  mov     dword ptr [r14+rax*8], 2
0x180013a18  mov     [r14+rax*8+8], rdx
0x180013a1d  jmp     loc_18001414D
0x180013a22  mov     [rbp+4Fh+var_A0], rdx; jumptable 00000001800139D4 case 8199
0x180013a26  lea     r9, [rbp+4Fh+var_A0]; struct _LUTF8_STRING **
0x180013a2a  mov     edx, r15d; unsigned int
0x180013a2d  mov     r8, rbx; struct _MICRODOM_DOM_NODE_HEADER *
0x180013a30  mov     rcx, r12; this
0x180013a33  call    ?GetNodeName@CMicrodom@MicrodomImplementation@@QEAAJKPEBU_MICRODOM_DOM_NODE_HEADER@@PEAPEBU_LUTF8_STRING@@@Z; MicrodomImplementation::CMicrodom::GetNodeName(ulong,_MICRODOM_DOM_NODE_HEADER const *,_LUTF8_STRING const * *)
0x180013a38  test    eax, eax
0x180013a3a  js      loc_180014209
0x180013a40  lea     rax, [rdi+rdi*2]
0x180013a44  mov     r9d, 1
0x180013a4a  lea     rcx, [r14+rax*8]
0x180013a4e  mov     rax, [rbp+4Fh+var_A0]
0x180013a52  mov     [rcx], r9d
0x180013a55  mov     r8d, 0FFFFFFFFh
0x180013a5b  mov     [rcx+8], rax
0x180013a5f  jmp     def_1800139D4; jumptable 00000001800139D4 default case
0x180013a64  mov     edx, r15d; jumptable 00000001800139D4 case 8194
0x180013a67  mov     rcx, r12; this
0x180013a6a  call    ?ExtractChildren@CMicrodom@MicrodomImplementation@@QEAAJK@Z; MicrodomImplementation::CMicrodom::ExtractChildren(ulong)
0x180013a6f  test    eax, eax
0x180013a71  js      loc_180014209
0x180013a77  mov     eax, r15d
0x180013a7a  mov     r8d, 0FFFFFFFFh
0x180013a80  imul    rdx, rax, 98h
0x180013a87  lea     rax, [rdi+rdi*2]
0x180013a8b  mov     r9d, 1
0x180013a91  add     rdx, [r12+258h]
0x180013a99  lea     rcx, [r14+rax*8]
0x180013a9d  mov     dword ptr [rcx], 4
0x180013aa3  cmp     qword ptr [rdx+30h], 0
0x180013aa8  jbe     short loc_180013ABA
0x180013aaa  mov     rax, [rdx+28h]
0x180013aae  movups  xmm0, xmmword ptr [rax]
  ... truncated ...
```
