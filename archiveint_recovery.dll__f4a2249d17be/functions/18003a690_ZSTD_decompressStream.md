# ZSTD_decompressStream

- ea: `0x18003a690`
- end: `0x18003b69c`
- name: `ZSTD_decompressStream`
- size: `4108`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x180008860`
- `0x1800c5560`
- `0x1800eb780`

## callees

- `0x1800395c0`
- `0x1800396a0`
- `0x1800397e0`
- `0x180039f50`
- `0x18003a0c0`
- `0x18003a690`
- `0x18003b6b0`
- `0x18003bd60`
- `0x1800454f0`
- `0x180045500`
- `0x1800455d0`
- `0x180045680`
- `0x18004c1d0`
- `0x180055030`
- `0x180055090`
- `0x180055540`
- `0x1800555d0`
- `0x180059bd0`
- `0x180059c60`
- `0x18005a050`
- `0x18005a0e0`
- `0x18005e010`
- `0x18005e120`
- `0x18005e570`
- `0x18005e5a0`
- `0x1800aba54`
- `0x18011a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003acbd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003acbd`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003acf1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003acf1`

## pseudocode

```c
unsigned __int64 __fastcall ZSTD_decompressStream(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  char *v3; // rax
  _QWORD *v4; // rsi
  unsigned __int64 v5; // r9
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // r8
  char *v9; // r13
  char *v10; // rdi
  char *v11; // rax
  unsigned __int64 v12; // rdx
  char *v13; // rbp
  char *v14; // r10
  unsigned __int64 result; // rax
  char *v16; // r14
  char *v17; // r15
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  __int64 v22; // rcx
  size_t v23; // rsi
  size_t v24; // rdi
  size_t v25; // rdx
  bool v26; // zf
  size_t v27; // rcx
  int v28; // eax
  unsigned __int64 *v29; // r13
  unsigned __int64 FrameHeader_advanced; // rbp
  _QWORD *v31; // r14
  __int64 v32; // rdi
  __int64 v33; // rax
  __int64 v34; // r15
  __int64 v35; // rsi
  __int64 i; // rax
  __int64 v37; // rdi
  __int64 v38; // rax
  size_t v39; // rdi
  __int64 v40; // rsi
  unsigned __int64 v41; // rdi
  unsigned __int64 v42; // r14
  int v43; // eax
  __int64 v44; // rdx
  int v45; // eax
  __int64 v46; // rcx
  unsigned __int64 v47; // rdx
  unsigned int v48; // ecx
  unsigned __int64 v49; // rcx
  __int64 v50; // r8
  unsigned __int64 v51; // rax
  unsigned __int64 v52; // rdi
  unsigned __int64 v53; // rdx
  size_t v54; // rsi
  unsigned __int64 v55; // r9
  __int64 v56; // r14
  unsigned __int64 v57; // rax
  __int64 v58; // rax
  void *v59; // rcx
  void (__fastcall *v60)(_QWORD, _QWORD); // rax
  __int64 (__fastcall *v61)(_QWORD, size_t); // rax
  void *v62; // rax
  __int64 v63; // rcx
  int v64; // esi
  char *v65; // rcx
  unsigned __int64 v66; // rdi
  unsigned __int64 v67; // rcx
  unsigned __int64 v68; // rax
  __int64 v69; // r8
  unsigned __int64 v70; // rax
  unsigned __int64 v71; // rcx
  unsigned __int64 v72; // rcx
  int v73; // eax
  __int64 v74; // r8
  unsigned __int64 v75; // rax
  __int64 v76; // rbp
  __int64 v77; // rcx
  size_t v78; // rsi
  char *v79; // rax
  size_t v80; // rdi
  size_t v81; // rax
  __int64 v82; // r9
  int v83; // edi
  __int64 v84; // r8
  unsigned __int64 v85; // rax
  unsigned __int64 v86; // rcx
  int v87; // eax
  __int64 v88; // r8
  unsigned __int64 v89; // rax
  unsigned __int64 v90; // rax
  int v91; // eax
  __int64 v92; // rax
  char *v93; // r13
  _QWORD *v94; // r8
  _QWORD *v95; // rbp
  __int64 v96; // rcx
  int v97; // edx
  unsigned __int64 v98; // rax
  int v99; // edx
  __int64 v100; // rax
  int v101; // eax
  unsigned int v102; // r12d
  int v103; // eax
  __int64 v104; // rdi
  __int64 v105; // r15
  __int64 v106; // r14
  int v107; // esi
  _DWORD *v108; // rbp
  void *v109; // rcx
  __int64 DCtx; // rdi
  _QWORD *v111; // r9
  _QWORD *v112; // r8
  __int64 v113; // rcx
  char *v114; // r9
  __int64 v115; // r10
  _QWORD *v116; // rbp
  __int64 v117; // rdx
  char *v118; // r9
  _QWORD *v119; // rax
  __int64 v120; // rdx
  __int64 v121; // rax
  char *v122; // r9
  __int64 v123; // rdx
  char *v124; // r9
  __int64 v125; // rdx
  char *v126; // [rsp+40h] [rbp-88h]
  char *v127; // [rsp+48h] [rbp-80h]
  char *v128; // [rsp+50h] [rbp-78h]
  char *v129; // [rsp+58h] [rbp-70h]
  char *v130; // [rsp+60h] [rbp-68h]
  char *v131; // [rsp+70h] [rbp-58h]
  char v132[24]; // [rsp+78h] [rbp-50h] BYREF
  _QWORD *v133; // [rsp+D8h] [rbp+10h] BYREF
  _QWORD *v134; // [rsp+E0h] [rbp+18h] BYREF
  unsigned int v135; // [rsp+E8h] [rbp+20h] BYREF

  v134 = a3;
  v133 = a2;
  v3 = (char *)*a3;
  v4 = a2;
  v5 = a3[2];
  v7 = a3[1];
  v8 = a2[1];
  v9 = &v3[v5];
  if ( !v5 )
    v9 = v3;
  v10 = &v3[v7];
  v129 = v9;
  if ( !v7 )
    v10 = v3;
  v11 = (char *)*a2;
  v12 = a2[2];
  v126 = v10;
  v13 = &v11[v8];
  v14 = &v11[v12];
  if ( !v12 )
    v14 = v11;
  v131 = v14;
  if ( !v8 )
    v13 = v11;
  v128 = v13;
  if ( v5 > v7 )
    return -72;
  if ( v12 > v8 )
    return -70;
  if ( *(_DWORD *)(a1 + 30336) == 1
    && *(_DWORD *)(a1 + 30236)
    && (*(char **)(a1 + 30344) != v11 || *(_QWORD *)(a1 + 30360) != v12 || *(_QWORD *)(a1 + 30352) != v8) )
  {
    return -104;
  }
  v16 = v9;
  v127 = v9;
  v17 = v14;
  v130 = v14;
  while ( 1 )
  {
    while ( 1 )
    {
      v18 = *(_DWORD *)(a1 + 30236);
      if ( !v18 )
        break;
      v19 = v18 - 1;
      if ( !v19 )
        goto LABEL_35;
      v20 = v19 - 1;
      if ( !v20 )
        goto LABEL_106;
      v21 = v20 - 1;
      if ( !v21 )
        goto LABEL_133;
      if ( v21 != 1 )
        return -1;
      v22 = *(_QWORD *)(a1 + 30288);
      v23 = *(_QWORD *)(a1 + 30296) - v22;
      v24 = v23;
      if ( v13 - v17 < v23 )
        v24 = v13 - v17;
      if ( v24 )
      {
        memcpy_0(v17, (const void *)(v22 + *(_QWORD *)(a1 + 30272)), v24);
        v22 = *(_QWORD *)(a1 + 30288);
      }
      if ( v17 )
      {
        v17 += v24;
        v130 = v17;
      }
      v25 = v24 + v22;
      v26 = v24 == v23;
      v10 = v126;
      *(_QWORD *)(a1 + 30288) = v25;
      if ( !v26 )
        goto LABEL_181;
      v27 = *(_QWORD *)(a1 + 30280);
      v4 = v133;
      *(_DWORD *)(a1 + 30236) = 2;
      if ( v27 < *(_QWORD *)(a1 + 29928) && v25 + *(unsigned int *)(a1 + 29944) > v27 )
      {
        *(_QWORD *)(a1 + 30296) = 0;
        *(_QWORD *)(a1 + 30288) = 0;
      }
    }
    *(_DWORD *)(a1 + 30236) = 1;
    *(_QWORD *)(a1 + 30296) = 0;
    *(_QWORD *)(a1 + 30288) = 0;
    *(_QWORD *)(a1 + 30256) = 0;
    *(_QWORD *)(a1 + 30304) = 0;
    *(_QWORD *)(a1 + 30324) = 0;
    *(_OWORD *)(a1 + 30344) = *(_OWORD *)v4;
    *(_QWORD *)(a1 + 30360) = v4[2];
LABEL_35:
    v28 = *(_DWORD *)(a1 + 30324);
    if ( v28 )
    {
      if ( !*(_QWORD *)(a1 + 30168) )
      {
        v114 = (char *)&unk_1801547BC;
        v115 = *(_QWORD *)(a1 + 30312);
        if ( !*v4 )
          *v4 = &unk_1801547BC;
        v116 = v134;
        if ( *v134 )
          v114 = (char *)*v134;
        else
          *v134 = &unk_1801547BC;
        switch ( v28 )
        {
          case 5:
            v117 = v4[2];
            v118 = &v114[v116[2]];
            v134 = (_QWORD *)(v116[1] - v116[2]);
            v119 = (_QWORD *)(v4[1] - v117);
            v120 = *v4 + v117;
            v133 = v119;
            v121 = ZBUFFv05_decompressContinue(v115, v120, &v133, v118, &v134);
            break;
          case 6:
            v122 = &v114[v116[2]];
            v123 = v4[2] + *v4;
            v134 = (_QWORD *)(v116[1] - v116[2]);
            v133 = (_QWORD *)(v4[1] - v4[2]);
            v121 = ZBUFFv06_decompressContinue(v115, v123, &v133, v122, &v134);
            break;
          case 7:
            v124 = &v114[v116[2]];
            v125 = v4[2] + *v4;
            v134 = (_QWORD *)(v116[1] - v116[2]);
            v133 = (_QWORD *)(v4[1] - v4[2]);
            v121 = ZBUFFv07_decompressContinue(v115, v125, &v133, v124, &v134);
            break;
          default:
            return -12;
        }
        v71 = v121;
        v4[2] += v133;
        v116[2] += v134;
        if ( v121 )
          return v71;
        *(_DWORD *)(a1 + 30236) = 0;
        return 0;
      }
      return -64;
    }
    v29 = (unsigned __int64 *)(a1 + 29928);
    FrameHeader_advanced = ZSTD_getFrameHeader_advanced(
                             a1 + 29928,
                             a1 + 95956,
                             *(_QWORD *)(a1 + 30304),
                             *(unsigned int *)(a1 + 30104));
    if ( *(_DWORD *)(a1 + 30224) )
    {
      v31 = *(_QWORD **)(a1 + 30216);
      if ( v31 && *(_QWORD *)(a1 + 30192) )
      {
        v135 = *(_DWORD *)(a1 + 29956);
        v32 = v135;
        v33 = ZSTD_XXH64(&v135, 4, 0);
        v34 = v31[1] - 1LL;
        v35 = v33 & v34;
        for ( i = (unsigned int)ZSTD_getDictID_fromDDict(*(_QWORD *)(*v31 + 8 * (v33 & v34)));
              (unsigned int)i != v32;
              i = (unsigned int)ZSTD_getDictID_fromDDict(*(_QWORD *)(*v31 + 8 * v35)) )
        {
          if ( !i )
            break;
          v35 = (v34 & v35) + 1;
        }
        v37 = *(_QWORD *)(*v31 + 8 * v35);
        if ( v37 )
        {
          ZSTD_freeDDict(*(void **)(a1 + 30184));
          *(_DWORD *)(a1 + 30200) = *(_DWORD *)(a1 + 29956);
          *(_QWORD *)(a1 + 30184) = 0;
          *(_QWORD *)(a1 + 30192) = v37;
          *(_DWORD *)(a1 + 30208) = -1;
        }
        v10 = v126;
        v17 = v130;
      }
      v16 = v127;
    }
    if ( FrameHeader_advanced > 0xFFFFFFFFFFFFFF88uLL )
      break;
    if ( FrameHeader_advanced )
    {
      v38 = *(_QWORD *)(a1 + 30304);
      v39 = FrameHeader_advanced - v38;
      v40 = v126 - v16;
      if ( FrameHeader_advanced - v38 > v126 - v16 )
      {
        if ( v40 )
        {
          memcpy_0((void *)(v38 + a1 + 95956), v16, v126 - v16);
          *(_QWORD *)(a1 + 30304) += v40;
        }
        v134[2] = v134[1];
        result = ZSTD_getFrameHeader_advanced(
                   a1 + 29928,
                   a1 + 95956,
                   *(_QWORD *)(a1 + 30304),
                   *(unsigned int *)(a1 + 30104));
        if ( result <= 0xFFFFFFFFFFFFFF88uLL )
        {
          v90 = 2;
          if ( !*(_DWORD *)(a1 + 30104) )
            v90 = 6;
          if ( v90 > FrameHeader_advanced )
            FrameHeader_advanced = v90;
          return FrameHeader_advanced - *(_QWORD *)(a1 + 30304) + 3;
        }
        return result;
      }
      memcpy_0((void *)(v38 + a1 + 95956), v16, v39);
      v4 = v133;
      v16 += v39;
      v10 = v126;
      *(_QWORD *)(a1 + 30304) = FrameHeader_advanced;
      v13 = v128;
      v127 = v16;
    }
    else
    {
      v13 = v128;
      if ( *v29 != -1 && *(_DWORD *)(a1 + 29948) != 1 && v128 - v17 >= *v29 )
      {
        v41 = v10 - v129;
        v42 = *(_QWORD *)(ZSTD_findFrameSizeInfo(v132, v129, v41, *(unsigned int *)(a1 + 30104)) + 8);
        if ( v42 <= v41 )
        {
          v91 = *(_DWORD *)(a1 + 30208);
          if ( v91 != -1 )
          {
            if ( v91 != 1 )
            {
              ZSTD_freeDDict(*(void **)(a1 + 30184));
              v92 = 0;
              *(_QWORD *)(a1 + 30184) = 0;
              *(_QWORD *)(a1 + 30192) = 0;
              *(_DWORD *)(a1 + 30208) = 0;
              goto LABEL_173;
            }
            *(_DWORD *)(a1 + 30208) = 0;
          }
          v92 = *(_QWORD *)(a1 + 30192);
LABEL_173:
          v93 = v129;
          result = ZSTD_decompressMultiFrame(a1, (_DWORD)v17, (int)v128 - (int)v17, (_DWORD)v129, v42, 0, 0, v92);
          if ( result > 0xFFFFFFFFFFFFFF88uLL )
            return result;
          v16 = &v129[v42];
          if ( v17 )
            v17 += result;
          v10 = v126;
          *(_QWORD *)(a1 + 29920) = 0;
          *(_DWORD *)(a1 + 30236) = 0;
          goto LABEL_182;
        }
      }
      if ( *(_DWORD *)(a1 + 30336) == 1 && *(_DWORD *)(a1 + 29948) != 1 && *v29 != -1 && v128 - v17 < *v29 )
        return -70;
      v43 = *(_DWORD *)(a1 + 30208);
      if ( v43 != -1 )
      {
        if ( v43 != 1 )
        {
          ZSTD_freeDDict(*(void **)(a1 + 30184));
          *(_QWORD *)(a1 + 30184) = 0;
          v44 = 0;
          *(_QWORD *)(a1 + 30192) = 0;
          *(_DWORD *)(a1 + 30208) = 0;
          goto LABEL_62;
        }
        *(_DWORD *)(a1 + 30208) = 0;
      }
      v44 = *(_QWORD *)(a1 + 30192);
LABEL_62:
      result = ZSTD_decompressBegin_usingDDict(a1, v44);
      if ( result > 0xFFFFFFFFFFFFFF88uLL )
        return result;
      if ( *(_DWORD *)(a1 + 30104) || (*(_DWORD *)(a1 + 95956) & 0xFFFFFFF0) != 0x184D2A50 )
      {
        result = ZSTD_decodeFrameHeader(a1, a1 + 95956, *(_QWORD *)(a1 + 30304));
        if ( result > 0xFFFFFFFFFFFFFF88uLL )
          return result;
        v46 = 3;
        v45 = 2;
      }
      else
      {
        v45 = 7;
        v46 = *(unsigned int *)(a1 + 95960);
      }
      *(_QWORD *)(a1 + 29920) = v46;
      v47 = 1024;
      *(_DWORD *)(a1 + 29996) = v45;
      if ( *(_QWORD *)(a1 + 29936) > 0x400u )
        v47 = *(_QWORD *)(a1 + 29936);
      *(_QWORD *)(a1 + 29936) = v47;
      if ( v47 > *(_QWORD *)(a1 + 30264) )
        return -16;
      v48 = *(_DWORD *)(a1 + 30232);
      if ( v48 )
      {
        if ( *(_DWORD *)(a1 + 29944) < v48 )
          v48 = *(_DWORD *)(a1 + 29944);
        *(_DWORD *)(a1 + 29944) = v48;
      }
      v49 = *(unsigned int *)(a1 + 29944);
      v50 = 4;
      if ( (unsigned int)v49 > 4 )
        v50 = (unsigned int)v49;
      if ( *(_DWORD *)(a1 + 30336) )
      {
        v52 = 0;
      }
      else
      {
        v51 = 0x20000;
        if ( v47 < 0x20000 )
          v51 = v47;
        if ( v51 < v49 )
          v49 = v51;
        v52 = v47 + 64 + 2 * v49;
        if ( *v29 < v52 )
          v52 = *v29;
      }
      v53 = *(_QWORD *)(a1 + 30248);
      v54 = v50 + v52;
      v55 = *(_QWORD *)(a1 + 30280);
      v56 = (unsigned int)v50;
      if ( v53 + v55 < 3 * (v50 + v52) )
      {
        *(_QWORD *)(a1 + 95976) = 0;
        v57 = 0;
      }
      else
      {
        v57 = ++*(_QWORD *)(a1 + 95976);
      }
      if ( v53 < (unsigned int)v50 || v55 < v52 || v57 >= 0x80 )
      {
        v58 = *(_QWORD *)(a1 + 30168);
        if ( v58 )
        {
          if ( v54 > v58 - 95984 )
            return -64;
        }
        else
        {
          v59 = *(void **)(a1 + 30240);
          if ( v59 )
          {
            v60 = *(void (__fastcall **)(_QWORD, _QWORD))(a1 + 30136);
            if ( v60 )
              v60(*(_QWORD *)(a1 + 30144), *(_QWORD *)(a1 + 30240));
            else
              free(v59);
          }
          v61 = *(__int64 (__fastcall **)(_QWORD, size_t))(a1 + 30128);
          *(_QWORD *)(a1 + 30248) = 0;
          *(_QWORD *)(a1 + 30280) = 0;
          if ( v61 )
            v62 = (void *)v61(*(_QWORD *)(a1 + 30144), v54);
          else
            v62 = malloc(v54);
          *(_QWORD *)(a1 + 30240) = v62;
          if ( !v62 )
            return -64;
        }
        v63 = *(_QWORD *)(a1 + 30240);
        *(_QWORD *)(a1 + 30248) = v56;
        *(_QWORD *)(a1 + 30272) = v56 + v63;
        *(_QWORD *)(a1 + 30280) = v52;
      }
      v16 = v127;
      v10 = v126;
      *(_DWORD *)(a1 + 30236) = 2;
LABEL_106:
      v64 = *(_DWORD *)(a1 + 29996);
      v65 = v10;
      v66 = *(_QWORD *)(a1 + 29920);
      v67 = v65 - v16;
      if ( (unsigned int)(v64 - 3) > 1 || *(_DWORD *)(a1 + 29992) )
        goto LABEL_114;
      v68 = *(_QWORD *)(a1 + 29920);
      if ( v67 < v66 )
        v68 = v67;
      if ( v68 )
      {
        if ( v67 < v66 )
          v66 = v67;
LABEL_114:
        if ( v66 )
          goto LABEL_115;
        *(_DWORD *)(a1 + 30236) = 0;
LABEL_180:
        v10 = v126;
LABEL_181:
        v93 = v129;
LABEL_182:
        v94 = v133;
        v95 = v134;
        v134[2] = &v16[-*v134];
        v94[2] = &v17[-*v94];
        *(_OWORD *)(a1 + 30344) = *(_OWORD *)v94;
        *(_QWORD *)(a1 + 30360) = v94[2];
        if ( v16 == v93 && v17 == v131 )
        {
          if ( (int)++*(_DWORD *)(a1 + 30332) >= 16 )
          {
            if ( v17 == v128 )
              return -80;
            if ( v16 == v10 )
              return -82;
          }
        }
        else
        {
          *(_DWORD *)(a1 + 30332) = 0;
        }
        v96 = *(_QWORD *)(a1 + 29920);
        if ( v96 )
        {
          switch ( *(_DWORD *)(a1 + 29996) )
          {
            case 2:
              v99 = 1;
              break;
            case 3:
              v99 = 2;
              break;
            case 4:
              v99 = 3;
              break;
            case 5:
              v99 = 4;
              break;
            case 6:
            case 7:
              v99 = 5;
              break;
            default:
              v99 = 0;
              break;
          }
          v100 = 0;
          if ( v99 == 2 )
            v100 = 3;
          return v96 + v100 - *(_QWORD *)(a1 + 30256);
        }
        else
        {
          v97 = *(_DWORD *)(a1 + 30328);
          if ( *(_QWORD *)(a1 + 30296) == *(_QWORD *)(a1 + 30288) )
          {
            if ( v97 )
            {
              v98 = v95[2];
              if ( v98 >= v95[1] )
              {
                *(_DWORD *)(a1 + 30236) = 2;
                return 1;
              }
              v95[2] = v98 + 1;
            }
            return 0;
          }
          else
          {
            if ( !v97 )
            {
              --v95[2];
              *(_DWORD *)(a1 + 30328) = 1;
            }
            return 1;
          }
        }
      }
      v66 = 1;
LABEL_115:
      if ( v67 < v66 )
      {
        v10 = v126;
        if ( v16 == v126 )
          goto LABEL_181;
        *(_DWORD *)(a1 + 30236) = 3;
LABEL_133:
        v76 = *(_QWORD *)(a1 + 29920);
        v77 = *(_QWORD *)(a1 + 30256);
        v78 = v76 - v77;
        if ( *(_DWORD *)(a1 + 29996) == 7 )
        {
          v79 = v10;
          v80 = *(_QWORD *)(a1 + 29920) - v77;
          v81 = v79 - v16;
          if ( v78 >= v81 )
            v80 = v81;
          goto LABEL_142;
        }
        if ( v78 > *(_QWORD *)(a1 + 30248) - v77 )
          return -20;
        v80 = v10 - v16;
        if ( v78 < v80 )
          v80 = *(_QWORD *)(a1 + 29920) - v77;
        if ( v80 )
        {
          memcpy_0((void *)(*(_QWORD *)(a1 + 30240) + v77), v16, v80);
LABEL_142:
          if ( v80 )
          {
            v16 += v80;
            *(_QWORD *)(a1 + 30256) += v80;
            v127 = v16;
          }
        }
        if ( v80 < v78 )
          goto LABEL_180;
        v26 = *(_DWORD *)(a1 + 30336) == 0;
        v82 = *(_QWORD *)(a1 + 30240);
        v83 = *(_DWORD *)(a1 + 29996);
        *(_QWORD *)(a1 + 30256) = 0;
        if ( v26 )
        {
          if ( v83 == 7 )
            v84 = 0;
          else
            v84 = *(_QWORD *)(a1 + 30280) - *(_QWORD *)(a1 + 30288);
          v85 = ZSTD_decompressContinue(a1, *(_QWORD *)(a1 + 30288) + *(_QWORD *)(a1 + 30272), v84, v82, v76);
          v71 = v85;
          if ( v85 > 0xFFFFFFFFFFFFFF88uLL )
            return v71;
          if ( v85 || v83 == 7 )
          {
            v86 = *(_QWORD *)(a1 + 30288) + v85;
            v87 = 4;
            *(_QWORD *)(a1 + 30296) = v86;
            goto LABEL_159;
          }
        }
        else
        {
          if ( v83 == 7 )
            v88 = 0;
          else
            v88 = v128 - v17;
          v89 = ZSTD_decompressContinue(a1, v17, v88, v82, v76);
          v71 = v89;
          if ( v89 > 0xFFFFFFFFFFFFFF88uLL )
            return v71;
          v17 += v89;
          v130 = v17;
        }
        v87 = 2;
LABEL_159:
        v10 = v126;
        v13 = v128;
        *(_DWORD *)(a1 + 30236) = v87;
        v4 = v133;
      }
      else
      {
        if ( *(_DWORD *)(a1 + 30336) )
        {
          if ( v64 == 7 )
            v74 = 0;
          else
            v74 = v13 - v17;
          v75 = ZSTD_decompressContinue(a1, v17, v74, v16, v66);
          v71 = v75;
          if ( v75 > 0xFFFFFFFFFFFFFF88uLL )
            return v71;
          v17 += v75;
          v130 = v17;
        }
        else
        {
          if ( v64 == 7 )
            v69 = 0;
          else
            v69 = *(_QWORD *)(a1 + 30280) - *(_QWORD *)(a1 + 30288);
          v70 = ZSTD_decompressContinue(a1, *(_QWORD *)(a1 + 30288) + *(_QWORD *)(a1 + 30272), v69, v16, v66);
          v71 = v70;
          if ( v70 > 0xFFFFFFFFFFFFFF88uLL )
            return v71;
          if ( v70 || v64 == 7 )
          {
            v72 = *(_QWORD *)(a1 + 30288) + v70;
            v73 = 4;
            *(_QWORD *)(a1 + 30296) = v72;
            goto LABEL_130;
          }
        }
        v73 = 2;
LABEL_130:
        v16 += v66;
        *(_DWORD *)(a1 + 30236) = v73;
        v4 = v133;
        v10 = v126;
        v127 = v16;
      }
    }
  }
  if ( (unsigned __int64)(v10 - v129) < 4 )
    return FrameHeader_advanced;
  v101 = *(_DWORD *)v129;
  if ( *(_DWORD *)v129 == -47205083 )
  {
    v102 = 5;
LABEL_218:
    v103 = *(_DWORD *)(a1 + 30208);
    if ( v103 != -1 )
    {
      if ( v103 != 1 )
      {
        ZSTD_freeDDict(*(void **)(a1 + 30184));
        *(_QWORD *)(a1 + 30184) = 0;
        *(_QWORD *)(a1 + 30192) = 0;
        *(_DWORD *)(a1 + 30208) = 0;
        goto LABEL_224;
      }
      *(_DWORD *)(a1 + 30208) = 0;
    }
    v104 = *(_QWORD *)(a1 + 30192);
    if ( v104 )
    {
      v105 = ZSTD_DDict_dictContent(*(_QWORD *)(a1 + 30192));
      v106 = ZSTD_DDict_dictSize(v104);
      goto LABEL_225;
    }
LABEL_224:
    v105 = 0;
    v106 = 0;
LABEL_225:
    if ( !*(_QWORD *)(a1 + 30168) )
    {
      v107 = *(_DWORD *)(a1 + 30320);
      v108 = &v135;
      if ( v105 )
        v108 = (_DWORD *)v105;
      if ( v107 != v102 )
      {
        v109 = *(void **)(a1 + 30312);
        switch ( v107 )
        {
          case 5:
            ZBUFFv05_freeDCtx(v109);
            break;
          case 6:
            ZBUFFv06_freeDCtx(v109);
            break;
          case 7:
            ZBUFFv07_freeDCtx(v109);
            break;
          default:
            break;
        }
      }
      switch ( v102 )
      {
        case 1u:
        case 2u:
        case 3u:
        case 4u:
          goto LABEL_250;
        case 5u:
          if ( v107 == v102 )
            DCtx = *(_QWORD *)(a1 + 30312);
          else
            DCtx = ZBUFFv05_createDCtx();
          if ( !DCtx )
            return -64;
          ZBUFFv05_decompressInitDictionary(DCtx, v108, v106);
          goto LABEL_249;
        case 6u:
          if ( v107 == v102 )
            DCtx = *(_QWORD *)(a1 + 30312);
          else
            DCtx = ZBUFFv06_createDCtx();
          if ( !DCtx )
            return -64;
          ZBUFFv06_decompressInitDictionary(DCtx, v108, v106);
          goto LABEL_249;
        case 7u:
          if ( v107 == v102 )
            DCtx = *(_QWORD *)(a1 + 30312);
          else
            DCtx = ZBUFFv07_createDCtx();
          if ( !DCtx )
            return -64;
          ZBUFFv07_decompressInitDictionary(DCtx, v108, v106);
LABEL_249:
          *(_QWORD *)(a1 + 30312) = DCtx;
LABEL_250:
          v111 = v134;
          v112 = v133;
          v113 = *(_QWORD *)(a1 + 30312);
          *(_DWORD *)(a1 + 30320) = v102;
          *(_DWORD *)(a1 + 30324) = v102;
          result = ZSTD_decompressLegacyStream(v113, v102, v112, v111);
          if ( !result )
            *(_DWORD *)(a1 + 30236) = 0;
          break;
      }
      return result;
    }
    return -64;
  }
  if ( v101 == -47205082 )
  {
    v102 = 6;
    goto LABEL_218;
  }
  if ( v101 == -47205081 )
  {
    v102 = 7;
    goto LABEL_218;
  }
  return FrameHeader_advanced;
}

```

## disassembly

```asm
0x18003a690  mov     [rsp+arg_10], r8
0x18003a695  mov     [rsp+arg_8], rdx
0x18003a69a  push    rbx
0x18003a69b  push    rbp
0x18003a69c  push    rsi
0x18003a69d  push    rdi
0x18003a69e  push    r13
0x18003a6a0  sub     rsp, 0A0h
0x18003a6a7  mov     rax, [r8]
0x18003a6aa  mov     rsi, rdx
0x18003a6ad  mov     r9, [r8+10h]
0x18003a6b1  mov     rbx, rcx
0x18003a6b4  mov     rcx, [r8+8]
0x18003a6b8  test    r9, r9
0x18003a6bb  mov     r8, [rsi+8]
0x18003a6bf  lea     r13, [r9+rax]
0x18003a6c3  cmovz   r13, rax
0x18003a6c7  lea     rdi, [rcx+rax]
0x18003a6cb  test    rcx, rcx
0x18003a6ce  mov     [rsp+0C8h+var_70], r13
0x18003a6d3  cmovz   rdi, rax
0x18003a6d7  mov     rax, [rdx]
0x18003a6da  mov     rdx, [rdx+10h]
0x18003a6de  test    rdx, rdx
0x18003a6e1  mov     [rsp+0C8h+var_88], rdi
0x18003a6e6  lea     rbp, [r8+rax]
0x18003a6ea  lea     r10, [rdx+rax]
0x18003a6ee  cmovz   r10, rax
0x18003a6f2  test    r8, r8
0x18003a6f5  mov     [rsp+0C8h+var_58], r10
0x18003a6fa  cmovz   rbp, rax
0x18003a6fe  mov     [rsp+0C8h+var_78], rbp
0x18003a703  cmp     r9, rcx
0x18003a706  jbe     short loc_18003A71D
0x18003a708  mov     rax, 0FFFFFFFFFFFFFFB8h
0x18003a70f  add     rsp, 0A0h
0x18003a716  pop     r13
0x18003a718  pop     rdi
0x18003a719  pop     rsi
0x18003a71a  pop     rbp
0x18003a71b  pop     rbx
0x18003a71c  retn
0x18003a71d  mov     [rsp+0C8h+arg_0], r12
0x18003a725  mov     [rsp+0C8h+var_30], r14
0x18003a72d  mov     [rsp+0C8h+var_38], r15
0x18003a735  cmp     rdx, r8
0x18003a738  ja      loc_18003B5FB
0x18003a73e  cmp     dword ptr [rbx+7680h], 1
0x18003a745  jnz     short loc_18003A777
0x18003a747  cmp     dword ptr [rbx+761Ch], 0
0x18003a74e  jz      short loc_18003A777
0x18003a750  cmp     [rbx+7688h], rax
0x18003a757  jnz     short loc_18003A76B
0x18003a759  cmp     [rbx+7698h], rdx
0x18003a760  jnz     short loc_18003A76B
0x18003a762  cmp     [rbx+7690h], r8
0x18003a769  jz      short loc_18003A777
0x18003a76b  mov     rax, 0FFFFFFFFFFFFFF98h
0x18003a772  jmp     loc_18003B602
0x18003a777  mov     r14, r13
0x18003a77a  mov     [rsp+0C8h+var_80], r13
0x18003a77f  mov     r15, r10
0x18003a782  mov     [rsp+0C8h+var_68], r10
0x18003a787  mov     dword ptr [rsp+0C8h+var_60], 7
0x18003a78f  xor     r13d, r13d
0x18003a792  mov     r12d, 2
0x18003a798  mov     r9d, 3
0x18003a79e  mov     r8d, 1
0x18003a7a4  nop     dword ptr [rax+00h]
0x18003a7a8  nop     dword ptr [rax+rax+00000000h]
0x18003a7b0  mov     ecx, [rbx+761Ch]
0x18003a7b6  test    ecx, ecx
0x18003a7b8  jz      loc_18003A89E
0x18003a7be  sub     ecx, 1
0x18003a7c1  jz      loc_18003A8E3
0x18003a7c7  sub     ecx, 1
0x18003a7ca  jz      loc_18003AD3F
0x18003a7d0  sub     ecx, 1
0x18003a7d3  jz      loc_18003AE6C
0x18003a7d9  cmp     ecx, 1
0x18003a7dc  jnz     loc_18003AFBF
0x18003a7e2  mov     rcx, [rbx+7650h]
0x18003a7e9  mov     rax, rbp
0x18003a7ec  mov     rsi, [rbx+7658h]
0x18003a7f3  sub     rax, r15
0x18003a7f6  sub     rsi, rcx
0x18003a7f9  cmp     rax, rsi
0x18003a7fc  mov     rdi, rsi
0x18003a7ff  cmovb   rdi, rax
0x18003a803  test    rdi, rdi
0x18003a806  jz      short loc_18003A830
0x18003a808  mov     rdx, [rbx+7640h]
0x18003a80f  mov     r8, rdi; Size
0x18003a812  add     rdx, rcx; Src
0x18003a815  mov     rcx, r15; void *
0x18003a818  call    memcpy_0
0x18003a81d  mov     rcx, [rbx+7650h]
0x18003a824  mov     r8d, 1
0x18003a82a  mov     r9d, 3
0x18003a830  test    r15, r15
0x18003a833  jz      short loc_18003A83D
0x18003a835  add     r15, rdi
0x18003a838  mov     [rsp+0C8h+var_68], r15
0x18003a83d  lea     rdx, [rdi+rcx]
0x18003a841  cmp     rdi, rsi
0x18003a844  mov     rdi, [rsp+0C8h+var_88]
0x18003a849  mov     [rbx+7650h], rdx
0x18003a850  jnz     loc_18003B11D
0x18003a856  mov     rcx, [rbx+7648h]
0x18003a85d  mov     rsi, [rsp+0C8h+arg_8]
0x18003a865  mov     [rbx+761Ch], r12d
0x18003a86c  cmp     rcx, [rbx+74E8h]
0x18003a873  jnb     loc_18003A7B0
0x18003a879  mov     eax, [rbx+74F8h]
0x18003a87f  add     rax, rdx
0x18003a882  cmp     rax, rcx
0x18003a885  jbe     loc_18003A7B0
0x18003a88b  mov     [rbx+7658h], r13
0x18003a892  mov     [rbx+7650h], r13
0x18003a899  jmp     loc_18003A7B0
0x18003a89e  mov     [rbx+761Ch], r8d
0x18003a8a5  mov     [rbx+7658h], r13
0x18003a8ac  mov     [rbx+7650h], r13
0x18003a8b3  mov     [rbx+7630h], r13
0x18003a8ba  mov     [rbx+7660h], r13
0x18003a8c1  mov     qword ptr [rbx+7674h], 0
0x18003a8cc  movups  xmm0, xmmword ptr [rsi]
0x18003a8cf  movups  xmmword ptr [rbx+7688h], xmm0
0x18003a8d6  movsd   xmm1, qword ptr [rsi+10h]
0x18003a8db  movsd   qword ptr [rbx+7698h], xmm1
0x18003a8e3  mov     eax, [rbx+7674h]
0x18003a8e9  test    eax, eax
0x18003a8eb  jnz     loc_18003B488
0x18003a8f1  mov     r9d, [rbx+7598h]
0x18003a8f8  lea     r13, [rbx+74E8h]
0x18003a8ff  mov     r8, [rbx+7660h]
0x18003a906  lea     rdx, [rbx+176D4h]
0x18003a90d  mov     rcx, r13
0x18003a910  call    ZSTD_getFrameHeader_advanced
0x18003a915  cmp     dword ptr [rbx+7610h], 0
0x18003a91c  mov     rbp, rax
0x18003a91f  jz      loc_18003A9F2
0x18003a925  mov     r14, [rbx+7608h]
0x18003a92c  test    r14, r14
0x18003a92f  jz      loc_18003A9ED
0x18003a935  cmp     qword ptr [rbx+75F0h], 0
0x18003a93d  jz      loc_18003A9ED
0x18003a943  mov     edi, [rbx+7504h]
0x18003a949  lea     rcx, [rsp+0C8h+arg_18]
0x18003a951  xor     r8d, r8d
0x18003a954  mov     [rsp+0C8h+arg_18], edi
0x18003a95b  mov     edx, 4
0x18003a960  call    ZSTD_XXH64
0x18003a965  mov     r15, [r14+8]
0x18003a969  mov     rcx, [r14]
0x18003a96c  dec     r15
0x18003a96f  mov     rsi, r15
0x18003a972  and     rsi, rax
0x18003a975  mov     rcx, [rcx+rsi*8]
0x18003a979  call    ZSTD_getDictID_fromDDict
0x18003a97e  mov     eax, eax
0x18003a980  cmp     rax, rdi
0x18003a983  jz      short loc_18003A9A3
0x18003a985  test    rax, rax
0x18003a988  jz      short loc_18003A9A3
0x18003a98a  mov     rcx, [r14]
0x18003a98d  and     rsi, r15
0x18003a990  inc     rsi
0x18003a993  mov     rcx, [rcx+rsi*8]
0x18003a997  call    ZSTD_getDictID_fromDDict
0x18003a99c  mov     eax, eax
0x18003a99e  cmp     rax, rdi
0x18003a9a1  jnz     short loc_18003A985
0x18003a9a3  mov     rax, [r14]
0x18003a9a6  mov     rdi, [rax+rsi*8]
0x18003a9aa  test    rdi, rdi
0x18003a9ad  jz      short loc_18003A9E3
0x18003a9af  mov     rcx, [rbx+75E8h]; Block
0x18003a9b6  call    ZSTD_freeDDict
0x18003a9bb  mov     eax, [rbx+7504h]
0x18003a9c1  mov     [rbx+75F8h], eax
0x18003a9c7  mov     qword ptr [rbx+75E8h], 0
0x18003a9d2  mov     [rbx+75F0h], rdi
0x18003a9d9  mov     dword ptr [rbx+7600h], 0FFFFFFFFh
0x18003a9e3  mov     rdi, [rsp+0C8h+var_88]
0x18003a9e8  mov     r15, [rsp+0C8h+var_68]
0x18003a9ed  mov     r14, [rsp+0C8h+var_80]
0x18003a9f2  cmp     rbp, 0FFFFFFFFFFFFFF88h
0x18003a9f6  ja      loc_18003B288
0x18003a9fc  test    rbp, rbp
0x18003a9ff  jz      short loc_18003AA5A
0x18003aa01  mov     rax, [rbx+7660h]
0x18003aa08  mov     rdi, rbp
0x18003aa0b  mov     rsi, [rsp+0C8h+var_88]
0x18003aa10  sub     rdi, rax
0x18003aa13  sub     rsi, r14
0x18003aa16  cmp     rdi, rsi
0x18003aa19  ja      loc_18003AFCB
0x18003aa1f  lea     rcx, [rbx+176D4h]
0x18003aa26  mov     r8, rdi; Size
0x18003aa29  add     rcx, rax; void *
0x18003aa2c  mov     rdx, r14; Src
0x18003aa2f  call    memcpy_0
0x18003aa34  mov     rsi, [rsp+0C8h+arg_8]
0x18003aa3c  add     r14, rdi
0x18003aa3f  mov     rdi, [rsp+0C8h+var_88]
0x18003aa44  mov     [rbx+7660h], rbp
0x18003aa4b  mov     rbp, [rsp+0C8h+var_78]
0x18003aa50  mov     [rsp+0C8h+var_80], r14
0x18003aa55  jmp     loc_18003A78F
0x18003aa5a  mov     rax, [r13+0]
0x18003aa5e  mov     rbp, [rsp+0C8h+var_78]
0x18003aa63  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003aa67  jz      short loc_18003AAA8
0x18003aa69  cmp     dword ptr [rbx+74FCh], 1
0x18003aa70  jz      short loc_18003AAA8
0x18003aa72  mov     rsi, rbp
0x18003aa75  sub     rsi, r15
0x18003aa78  cmp     rsi, rax
0x18003aa7b  jb      short loc_18003AAA8
0x18003aa7d  sub     rdi, [rsp+0C8h+var_70]
0x18003aa82  lea     rcx, [rsp+0C8h+var_50]
0x18003aa87  mov     r9d, [rbx+7598h]
0x18003aa8e  mov     r8, rdi
0x18003aa91  mov     rdx, [rsp+0C8h+var_70]
0x18003aa96  call    ZSTD_findFrameSizeInfo
0x18003aa9b  mov     r14, [rax+8]
0x18003aa9f  cmp     r14, rdi
0x18003aaa2  jbe     loc_18003B04E
0x18003aaa8  cmp     dword ptr [rbx+7680h], 1
0x18003aaaf  jnz     short loc_18003AAD3
0x18003aab1  cmp     dword ptr [rbx+74FCh], 1
0x18003aab8  jz      short loc_18003AAD3
0x18003aaba  mov     rcx, [r13+0]
0x18003aabe  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003aac2  jz      short loc_18003AAD3
0x18003aac4  mov     rax, rbp
0x18003aac7  sub     rax, r15
0x18003aaca  cmp     rax, rcx
0x18003aacd  jb      loc_18003B5FB
0x18003aad3  mov     eax, [rbx+7600h]
0x18003aad9  cmp     eax, 0FFFFFFFFh
0x18003aadc  jz      short loc_18003AAED
0x18003aade  cmp     eax, 1
0x18003aae1  jnz     short loc_18003AB31
0x18003aae3  mov     dword ptr [rbx+7600h], 0
0x18003aaed  mov     rdx, [rbx+75F0h]
0x18003aaf4  mov     rcx, rbx
0x18003aaf7  call    ZSTD_decompressBegin_usingDDict
0x18003aafc  cmp     rax, 0FFFFFFFFFFFFFF88h
0x18003ab00  ja      loc_18003B602
0x18003ab06  cmp     dword ptr [rbx+7598h], 0
0x18003ab0d  jnz     short loc_18003AB57
0x18003ab0f  mov     eax, [rbx+176D4h]
0x18003ab15  and     eax, 0FFFFFFF0h
0x18003ab18  cmp     eax, 184D2A50h
0x18003ab1d  jnz     short loc_18003AB57
0x18003ab1f  mov     eax, dword ptr [rsp+0C8h+var_60]
0x18003ab23  mov     r12d, 2
0x18003ab29  mov     ecx, [rbx+176D8h]
0x18003ab2f  jmp     short loc_18003AB85
0x18003ab31  mov     rcx, [rbx+75E8h]; Block
0x18003ab38  call    ZSTD_freeDDict
0x18003ab3d  xor     eax, eax
0x18003ab3f  mov     [rbx+75E8h], rax
0x18003ab46  mov     edx, eax
0x18003ab48  mov     [rbx+75F0h], rax
0x18003ab4f  mov     [rbx+7600h], eax
0x18003ab55  jmp     short loc_18003AAF4
0x18003ab57  mov     r8, [rbx+7660h]
0x18003ab5e  lea     rdx, [rbx+176D4h]
0x18003ab65  mov     rcx, rbx
0x18003ab68  call    ZSTD_decodeFrameHeader
0x18003ab6d  cmp     rax, 0FFFFFFFFFFFFFF88h
0x18003ab71  ja      loc_18003B602
0x18003ab77  mov     r12d, 2
0x18003ab7d  mov     ecx, 3
0x18003ab82  mov     eax, r12d
0x18003ab85  mov     [rbx+74E0h], rcx
0x18003ab8c  mov     edx, 400h
0x18003ab91  mov     [rbx+752Ch], eax
0x18003ab97  mov     rax, [rbx+74F0h]
0x18003ab9e  cmp     rax, rdx
0x18003aba1  cmova   rdx, rax
0x18003aba5  mov     [rbx+74F0h], rdx
0x18003abac  cmp     rdx, [rbx+7638h]
0x18003abb3  ja      loc_18003B27C
0x18003abb9  mov     ecx, [rbx+7618h]
0x18003abbf  test    ecx, ecx
0x18003abc1  jz      short loc_18003ABD4
0x18003abc3  mov     eax, [rbx+74F8h]
0x18003abc9  cmp     eax, ecx
0x18003abcb  cmovb   ecx, eax
0x18003abce  mov     [rbx+74F8h], ecx
0x18003abd4  mov     ecx, [rbx+74F8h]
0x18003abda  mov     r8d, 4
0x18003abe0  cmp     ecx, r8d
0x18003abe3  cmova   r8d, ecx
0x18003abe7  cmp     dword ptr [rbx+7680h], 0
0x18003abee  jnz     short loc_18003AC19
  ... truncated ...
```
