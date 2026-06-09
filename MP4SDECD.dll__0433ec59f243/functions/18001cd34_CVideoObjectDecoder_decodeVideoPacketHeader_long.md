# CVideoObjectDecoder::decodeVideoPacketHeader(long &)

- ea: `0x18001cd34`
- end: `0x18001d940`
- name: `?decodeVideoPacketHeader@CVideoObjectDecoder@@AEAAJAEAJ@Z`
- size: `3084`
- prototype: `__int64 __fastcall(CInputBitStream **this, int *)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180002e90`
- `0x180004f10`
- `0x18000b1e0`
- `0x180035770`
- `0x180035e90`

## callees

- `0x180002cc0`
- `0x18001cd34`
- `0x18001d948`
- `0x180034274`

## pseudocode

```c
__int64 __fastcall CVideoObjectDecoder::decodeVideoPacketHeader(CInputBitStream **this, int *a2)
{
  CInputBitStream *v4; // r9
  int v5; // r11d
  _DWORD *v6; // r10
  unsigned int v7; // r8d
  __int64 v8; // rax
  CInputBitStream *v9; // r11
  unsigned int v10; // r10d
  int v11; // ecx
  int v12; // eax
  int v13; // r9d
  CInputBitStream *v14; // r10
  int v15; // ebp
  _DWORD *v16; // rsi
  __int64 v17; // rcx
  unsigned int v18; // r9d
  int v19; // ecx
  int v20; // r9d
  CInputBitStream *v21; // r10
  int v22; // ebp
  _DWORD *v23; // r11
  __int64 v24; // rcx
  unsigned int v25; // r9d
  int v26; // ecx
  int v27; // r9d
  CInputBitStream *v28; // r10
  int v30; // esi
  __int64 v31; // rcx
  unsigned int v32; // r9d
  int v33; // ecx
  int v34; // ecx
  int v35; // r9d
  unsigned int v36; // r11d
  unsigned int v37; // r8d
  int v38; // r9d
  unsigned int v39; // r8d
  int v40; // r9d
  unsigned int v41; // r10d
  unsigned int v42; // r8d
  int v43; // r14d
  _DWORD *v44; // r11
  __int64 v45; // rcx
  unsigned int v46; // r9d
  int v47; // r9d
  unsigned int v48; // r8d
  int v49; // r9d
  int i; // ebp
  __int64 v51; // rax
  CInputBitStream *v52; // r9
  CInputBitStream *v53; // r14
  int v54; // esi
  _DWORD *v55; // r10
  __int64 v56; // rcx
  unsigned int v57; // r8d
  int v58; // ebp
  __int64 v59; // rdx
  unsigned int v60; // r8d
  int v61; // r8d
  CInputBitStream *v62; // r11
  int v63; // ebp
  _DWORD *v64; // rsi
  __int64 v65; // r10
  __int64 v66; // rcx
  unsigned int v67; // r9d
  int v68; // r9d
  unsigned int v69; // r10d
  unsigned int v70; // r8d
  unsigned int v71; // r9d
  int v72; // ecx
  int v73; // ecx
  int v74; // ecx
  int v75; // esi
  __int64 v76; // rcx
  unsigned int v77; // r9d
  int v78; // r9d
  unsigned int v79; // r8d
  int v80; // r9d
  CInputBitStream *v81; // r10
  int v82; // r14d
  _DWORD *v83; // r11
  __int64 v84; // rcx
  unsigned int v85; // r9d
  int v86; // r9d
  unsigned int v87; // ebp
  unsigned int v88; // r8d
  unsigned int v89; // r9d
  int v90; // ecx
  int v91; // ecx
  int v92; // r11d
  __int64 v93; // rcx
  unsigned int v94; // r8d
  unsigned int v95; // r9d
  int v96; // ebp
  __int64 v97; // rdx
  unsigned int v98; // r8d
  int v99; // r8d
  int v100; // ecx
  CInputBitStream *v101; // r9
  int v102; // r14d
  _DWORD *v103; // r10
  __int64 v104; // rcx
  unsigned int v105; // r8d
  unsigned int v106; // r11d
  int v107; // r15d
  int v108; // r8d
  CInputBitStream *v109; // rax
  CInputBitStream *v110; // r10
  int v111; // r14d
  _DWORD *v112; // r11
  __int64 v113; // rcx
  unsigned int v114; // r9d
  int v115; // r9d
  unsigned int v116; // esi
  __int64 v117; // rdx
  unsigned int v118; // r8d
  int v119; // r9d
  CInputBitStream *v120; // rax
  int v121; // ecx
  __int64 v122; // rdx
  unsigned int v123; // r8d
  int v124; // ecx
  CInputBitStream *v125; // r10
  CInputBitStream *v126; // r10
  CInputBitStream *v127; // rax

  CInputBitStream::flushMPEG4(this[675], 8u);
  v4 = this[675];
  if ( *((_DWORD *)v4 + 5)
    || (v5 = *((_DWORD *)v4 + 2), v6 = (_DWORD *)((char *)v4 + 16), v7 = *((_DWORD *)this + 1886), 8 * v5 < v7)
    && *v6 + 8 * v5 < v7 )
  {
    *((_DWORD *)v4 + 5) = 1;
  }
  else
  {
    v8 = (unsigned int)*v6;
    if ( v7 > (unsigned int)v8 )
    {
      v7 -= v8;
      if ( v5 < 4 )
      {
        CInputBitStream::finalLoad(this[675], *((_DWORD *)v4 + 3) & *((_DWORD *)&GetMask + v8), v7);
        goto LABEL_5;
      }
      v34 = *(unsigned __int8 *)(*(_QWORD *)v4 + 3LL)
          | ((*(unsigned __int8 *)(*(_QWORD *)v4 + 2LL)
            | ((*(unsigned __int8 *)(*(_QWORD *)v4 + 1LL) | (**(unsigned __int8 **)v4 << 8)) << 8)) << 8);
      *(_QWORD *)v4 += 4LL;
      *((_DWORD *)v4 + 2) = v5 - 4;
      LODWORD(v8) = 32;
      *((_DWORD *)v4 + 3) = v34;
    }
    *v6 = v8 - v7;
  }
LABEL_5:
  v9 = this[675];
  if ( *((_DWORD *)v9 + 5) )
    return 4294967196LL;
  v10 = 0;
  v11 = *((_DWORD *)this + 222) * *((_DWORD *)this + 223);
  v12 = v11 - 1;
  if ( v11 != 1 )
  {
    do
    {
      ++v10;
      v12 >>= 1;
    }
    while ( v12 );
  }
  v13 = 0;
  if ( v11 > 1 )
  {
    v30 = *((_DWORD *)v9 + 2);
    if ( 8 * v30 >= v10 || *((_DWORD *)v9 + 4) + 8 * v30 >= v10 )
    {
      v31 = *((unsigned int *)v9 + 4);
      v32 = *((_DWORD *)v9 + 3);
      if ( v10 > (unsigned int)v31 )
      {
        v40 = *((_DWORD *)&GetMask + v31) & v32;
        v41 = v10 - v31;
        if ( v30 < 4 )
        {
          v13 = CInputBitStream::finalLoad(this[675], v40, v41);
        }
        else
        {
          v42 = *(unsigned __int8 *)(*(_QWORD *)v9 + 3LL)
              | ((*(unsigned __int8 *)(*(_QWORD *)v9 + 2LL)
                | ((*(unsigned __int8 *)(*(_QWORD *)v9 + 1LL) | (**(unsigned __int8 **)v9 << 8)) << 8)) << 8);
          *(_QWORD *)v9 += 4LL;
          *((_DWORD *)v9 + 2) = v30 - 4;
          *((_DWORD *)v9 + 3) = v42;
          *((_DWORD *)v9 + 4) = 32 - v41;
          v13 = (v42 >> (32 - v41)) | (v40 << v41);
        }
      }
      else
      {
        v33 = v31 - v10;
        *((_DWORD *)v9 + 4) = v33;
        v13 = (v32 >> v33) & *((_DWORD *)&GetMask + v10);
      }
    }
    else
    {
      *((_DWORD *)v9 + 5) = 1;
    }
    if ( *((_DWORD *)this[675] + 5) )
      return 4294967196LL;
  }
  v14 = this[675];
  *((_DWORD *)this + 1352) = v13;
  if ( *((_DWORD *)v14 + 5)
    || (v15 = *((_DWORD *)v14 + 2), v16 = (_DWORD *)((char *)v14 + 16), (unsigned int)(8 * v15) < 5)
    && (unsigned int)(*v16 + 8 * v15) < 5 )
  {
    *((_DWORD *)v14 + 5) = 1;
    v20 = 0;
  }
  else
  {
    v17 = (unsigned int)*v16;
    v18 = *((_DWORD *)v14 + 3);
    if ( (unsigned int)v17 < 5 )
    {
      v35 = *((_DWORD *)&GetMask + v17) & v18;
      v36 = 5 - v17;
      if ( v15 < 4 )
      {
        v20 = CInputBitStream::finalLoad(v14, v35, v36);
      }
      else
      {
        v37 = *(unsigned __int8 *)(*(_QWORD *)v14 + 3LL)
            | ((*(unsigned __int8 *)(*(_QWORD *)v14 + 2LL)
              | ((*(unsigned __int8 *)(*(_QWORD *)v14 + 1LL) | (**(unsigned __int8 **)v14 << 8)) << 8)) << 8);
        *(_QWORD *)v14 += 4LL;
        *((_DWORD *)v14 + 2) = v15 - 4;
        *((_DWORD *)v14 + 3) = v37;
        *v16 = 32 - v36;
        v20 = (v37 >> (32 - v36)) | (v35 << v36);
      }
    }
    else
    {
      v19 = v17 - 5;
      v20 = (v18 >> v19) & 0x1F;
      *v16 = v19;
    }
  }
  *a2 = v20;
  v21 = this[675];
  if ( *((_DWORD *)v21 + 5) )
    return 4294967196LL;
  v22 = *((_DWORD *)v21 + 2);
  v23 = (_DWORD *)((char *)v21 + 16);
  if ( 8 * v22 || *v23 )
  {
    v24 = (unsigned int)*v23;
    v25 = *((_DWORD *)v21 + 3);
    if ( (_DWORD)v24 )
    {
      v26 = v24 - 1;
      v27 = (v25 >> v26) & 1;
      *v23 = v26;
    }
    else
    {
      v38 = *((_DWORD *)&GetMask + v24) & v25;
      if ( v22 < 4 )
      {
        v27 = CInputBitStream::finalLoad(this[675], v38, 1u);
      }
      else
      {
        v39 = *(unsigned __int8 *)(*(_QWORD *)v21 + 3LL)
            | ((*(unsigned __int8 *)(*(_QWORD *)v21 + 2LL)
              | (((**(unsigned __int8 **)v21 << 8) | *(unsigned __int8 *)(*(_QWORD *)v21 + 1LL)) << 8)) << 8);
        *(_QWORD *)v21 += 4LL;
        *((_DWORD *)v21 + 2) = v22 - 4;
        *((_DWORD *)v21 + 3) = v39;
        *v23 = 31;
        v27 = (v39 >> 31) | (2 * v38);
      }
    }
  }
  else
  {
    *((_DWORD *)v21 + 5) = 1;
    v27 = 0;
  }
  v28 = this[675];
  if ( *((_DWORD *)v28 + 5) )
    return 4294967196LL;
  if ( !v27 )
    return 0;
  for ( i = 0; !*((_DWORD *)v28 + 5); ++i )
  {
    v43 = *((_DWORD *)v28 + 2);
    v44 = (_DWORD *)((char *)v28 + 16);
    if ( !(8 * v43) && !*v44 )
      break;
    v45 = (unsigned int)*v44;
    v46 = *((_DWORD *)v28 + 3);
    if ( (_DWORD)v45 )
    {
      v72 = v45 - 1;
      v49 = (v46 >> v72) & 1;
      *v44 = v72;
    }
    else
    {
      v47 = *((_DWORD *)&GetMask + v45) & v46;
      if ( v43 < 4 )
      {
        v49 = CInputBitStream::finalLoad(v28, v47, 1u);
      }
      else
      {
        v48 = *(unsigned __int8 *)(*(_QWORD *)v28 + 3LL)
            | ((*(unsigned __int8 *)(*(_QWORD *)v28 + 2LL)
              | (((**(unsigned __int8 **)v28 << 8) | *(unsigned __int8 *)(*(_QWORD *)v28 + 1LL)) << 8)) << 8);
        *(_QWORD *)v28 += 4LL;
        *((_DWORD *)v28 + 2) = v43 - 4;
        *((_DWORD *)v28 + 3) = v48;
        *v44 = 31;
        v49 = (v48 >> 31) | (2 * v47);
      }
    }
    if ( !v49 )
      goto LABEL_57;
    v28 = this[675];
    if ( *((_DWORD *)v28 + 5) )
      return 4294967196LL;
  }
  *((_DWORD *)v28 + 5) = 1;
LABEL_57:
  v51 = 138;
  v52 = this[675];
  if ( *((_DWORD *)this + 210) == 2 )
    v51 = 139;
  v53 = (CInputBitStream *)((char *)this[v51] + i);
  this[136] = v53;
  if ( !*((_DWORD *)v52 + 5) && ((v54 = *((_DWORD *)v52 + 2), v55 = (_DWORD *)((char *)v52 + 16), 8 * v54) || *v55) )
  {
    v56 = (unsigned int)*v55;
    v57 = *((_DWORD *)v52 + 3);
    if ( (_DWORD)v56 )
    {
      v73 = v56 - 1;
      v61 = (v57 >> v73) & 1;
      *v55 = v73;
    }
    else
    {
      v58 = *((_DWORD *)&GetMask + v56) & v57;
      if ( v54 < 4 )
      {
        v61 = CInputBitStream::finalLoad(v52, v58, 1u);
      }
      else
      {
        v59 = *(_QWORD *)v52;
        v60 = *(unsigned __int8 *)(*(_QWORD *)v52 + 3LL)
            | ((*(unsigned __int8 *)(*(_QWORD *)v52 + 2LL)
              | (((**(unsigned __int8 **)v52 << 8) | *(unsigned __int8 *)(*(_QWORD *)v52 + 1LL)) << 8)) << 8);
        *v55 = 31;
        *((_DWORD *)v52 + 3) = v60;
        *(_QWORD *)v52 = v59 + 4;
        v61 = (2 * v58) | (v60 >> 31);
        *((_DWORD *)v52 + 2) = v54 - 4;
      }
    }
    if ( !v61 )
      return 4294967196LL;
    v62 = this[675];
    if ( *((_DWORD *)v62 + 5) )
      return 4294967196LL;
    v63 = *((_DWORD *)v62 + 2);
    v64 = (_DWORD *)((char *)v62 + 16);
    v65 = *((unsigned int *)this + 280);
    if ( 8 * v63 < (unsigned int)v65 && *v64 + 8 * v63 < (unsigned int)v65 )
    {
      *((_DWORD *)v62 + 5) = 1;
      v71 = 0;
    }
    else
    {
      v66 = (unsigned int)*v64;
      v67 = *((_DWORD *)v62 + 3);
      if ( (unsigned int)v65 <= (unsigned int)v66 )
      {
        v74 = v66 - v65;
        v71 = (v67 >> v74) & *((_DWORD *)&GetMask + v65);
        *v64 = v74;
      }
      else
      {
        v68 = *((_DWORD *)&GetMask + v66) & v67;
        v69 = v65 - v66;
        if ( v63 < 4 )
        {
          v71 = CInputBitStream::finalLoad(this[675], v68, v69);
        }
        else
        {
          v70 = *(unsigned __int8 *)(*(_QWORD *)v62 + 3LL)
              | ((*(unsigned __int8 *)(*(_QWORD *)v62 + 2LL)
                | (((**(unsigned __int8 **)v62 << 8) | *(unsigned __int8 *)(*(_QWORD *)v62 + 1LL)) << 8)) << 8);
          *(_QWORD *)v62 += 4LL;
          *((_DWORD *)v62 + 2) = v63 - 4;
          *((_DWORD *)v62 + 3) = v70;
          *v64 = 32 - v69;
          v71 = (v70 >> (32 - v69)) | (v68 << v69);
        }
      }
    }
    v125 = this[675];
    if ( *((_DWORD *)v125 + 5) )
      return 4294967196LL;
    this[132] = (CInputBitStream *)(v71 + (_QWORD)v53 * *((int *)this + 13));
    if ( !*((_DWORD *)v125 + 5) && ((v75 = *((_DWORD *)v125 + 2), 8 * v75) || *((_DWORD *)v125 + 4)) )
    {
      v76 = *((unsigned int *)v125 + 4);
      v77 = *((_DWORD *)v125 + 3);
      if ( (_DWORD)v76 )
      {
        v90 = v76 - 1;
        v80 = (v77 >> v90) & 1;
        *((_DWORD *)v125 + 4) = v90;
      }
      else
      {
        v78 = *((_DWORD *)&GetMask + v76) & v77;
        if ( v75 < 4 )
        {
          v80 = CInputBitStream::finalLoad(v125, v78, 1u);
        }
        else
        {
          v79 = *(unsigned __int8 *)(*(_QWORD *)v125 + 3LL)
              | ((*(unsigned __int8 *)(*(_QWORD *)v125 + 2LL)
                | (((**(unsigned __int8 **)v125 << 8) | *(unsigned __int8 *)(*(_QWORD *)v125 + 1LL)) << 8)) << 8);
          *(_QWORD *)v125 += 4LL;
          *((_DWORD *)v125 + 2) = v75 - 4;
          *((_DWORD *)v125 + 3) = v79;
          *((_DWORD *)v125 + 4) = 31;
          v80 = (v79 >> 31) | (2 * v78);
        }
      }
      if ( !v80 )
        return 4294967196LL;
      v81 = this[675];
      if ( *((_DWORD *)v81 + 5) )
        return 4294967196LL;
      v82 = *((_DWORD *)v81 + 2);
      v83 = (_DWORD *)((char *)v81 + 16);
      if ( (unsigned int)(8 * v82) < 2 && (unsigned int)(*v83 + 8 * v82) < 2 )
      {
        *((_DWORD *)v81 + 5) = 1;
        v89 = 0;
      }
      else
      {
        v84 = (unsigned int)*v83;
        v85 = *((_DWORD *)v81 + 3);
        if ( (unsigned int)v84 >= 2 )
        {
          v91 = v84 - 2;
          v89 = (v85 >> v91) & 3;
          *v83 = v91;
        }
        else
        {
          v86 = *((_DWORD *)&GetMask + v84) & v85;
          v87 = 2 - v84;
          if ( v82 < 4 )
          {
            v89 = CInputBitStream::finalLoad(this[675], v86, v87);
          }
          else
          {
            v88 = *(unsigned __int8 *)(*(_QWORD *)v81 + 3LL)
                | ((*(unsigned __int8 *)(*(_QWORD *)v81 + 2LL)
                  | (((**(unsigned __int8 **)v81 << 8) | *(unsigned __int8 *)(*(_QWORD *)v81 + 1LL)) << 8)) << 8);
            *(_QWORD *)v81 += 4LL;
            *((_DWORD *)v81 + 2) = v82 - 4;
            *((_DWORD *)v81 + 3) = v88;
            *v83 = 32 - v87;
            v89 = (v88 >> (32 - v87)) | (v86 << v87);
          }
        }
      }
      v126 = this[675];
      *((_DWORD *)this + 210) = v89;
      if ( *((_DWORD *)v126 + 5) || v89 > 2 && (v89 != 3 || !*((_DWORD *)this + 201)) )
        return 4294967196LL;
      v92 = *((_DWORD *)v126 + 2);
      if ( (unsigned int)(8 * v92) < 3 && (unsigned int)(*((_DWORD *)v126 + 4) + 8 * v92) < 3 )
      {
        *((_DWORD *)v126 + 5) = 1;
        v99 = 0;
      }
      else
      {
        v93 = *((unsigned int *)v126 + 4);
        v94 = *((_DWORD *)v126 + 3);
        if ( (unsigned int)v93 >= 3 )
        {
          v100 = v93 - 3;
          v99 = (v94 >> v100) & 7;
          *((_DWORD *)v126 + 4) = v100;
        }
        else
        {
          v95 = 3 - v93;
          v96 = *((_DWORD *)&GetMask + v93) & v94;
          if ( v92 < 4 )
          {
            v99 = CInputBitStream::finalLoad(v126, v96, v95);
          }
          else
          {
            v97 = *(_QWORD *)v126;
            v98 = *(unsigned __int8 *)(*(_QWORD *)v126 + 3LL)
                | ((*(unsigned __int8 *)(*(_QWORD *)v126 + 2LL)
                  | (((**(unsigned __int8 **)v126 << 8) | *(unsigned __int8 *)(*(_QWORD *)v126 + 1LL)) << 8)) << 8);
            *((_DWORD *)v126 + 4) = 32 - v95;
            *((_DWORD *)v126 + 3) = v98;
            *(_QWORD *)v126 = v97 + 4;
            v99 = (v96 << v95) | (v98 >> (32 - v95));
            *((_DWORD *)v126 + 2) = v92 - 4;
          }
        }
      }
      v127 = this[675];
      *((_DWORD *)this + 219) = v99;
      if ( *((_DWORD *)v127 + 5)
        || *((_DWORD *)this + 201)
        && *((_DWORD *)this + 210) == 3
        && *((int *)this + 202) > 0
        && !(unsigned int)CVideoObjectDecoder::DecodeWarpingPoints(this) )
      {
        return 4294967196LL;
      }
      if ( *((_DWORD *)this + 210) )
      {
        v101 = this[675];
        if ( *((_DWORD *)v101 + 5)
          || (v102 = *((_DWORD *)v101 + 2), v103 = (_DWORD *)((char *)v101 + 16), (unsigned int)(8 * v102) < 3)
          && (unsigned int)(*v103 + 8 * v102) < 3 )
        {
          *((_DWORD *)v101 + 5) = 1;
          v108 = 0;
        }
        else
        {
          v104 = (unsigned int)*v103;
          v105 = *((_DWORD *)v101 + 3);
          if ( (unsigned int)v104 >= 3 )
          {
            v121 = v104 - 3;
            v108 = (v105 >> v121) & 7;
            *v103 = v121;
          }
          else
          {
            v106 = 3 - v104;
            v107 = *((_DWORD *)&GetMask + v104) & v105;
            if ( v102 >= 4 )
            {
              v122 = *(_QWORD *)v101;
              v123 = *(unsigned __int8 *)(*(_QWORD *)v101 + 3LL)
                   | ((*(unsigned __int8 *)(*(_QWORD *)v101 + 2LL)
                     | (((**(unsigned __int8 **)v101 << 8) | *(unsigned __int8 *)(*(_QWORD *)v101 + 1LL)) << 8)) << 8);
              *v103 = 32 - v106;
              *((_DWORD *)v101 + 3) = v123;
              *(_QWORD *)v101 = v122 + 4;
              v108 = (v107 << v106) | (v123 >> (32 - v106));
              *((_DWORD *)v101 + 2) = v102 - 4;
            }
            else
            {
              v108 = CInputBitStream::finalLoad(this[675], v107, v106);
            }
          }
        }
        v109 = this[675];
        *((_DWORD *)this + 213) = v108;
        if ( *((_DWORD *)v109 + 5) )
          return 4294967196LL;
        *((_DWORD *)this + 215) = 1 << (v108 - 1);
        *((_DWORD *)this + 214) = 16 << v108;
      }
      if ( *((_DWORD *)this + 210) != 2 )
        return 0;
      v110 = this[675];
      if ( *((_DWORD *)v110 + 5)
        || (v111 = *((_DWORD *)v110 + 2), v112 = (_DWORD *)((char *)v110 + 16), (unsigned int)(8 * v111) < 3)
        && (unsigned int)(*v112 + 8 * v111) < 3 )
      {
        *((_DWORD *)v110 + 5) = 1;
        v119 = 0;
      }
      else
      {
        v113 = (unsigned int)*v112;
        v114 = *((_DWORD *)v110 + 3);
        if ( (unsigned int)v113 >= 3 )
        {
          v124 = v113 - 3;
          v119 = (v114 >> v124) & 7;
          *v112 = v124;
        }
        else
        {
          v115 = *((_DWORD *)&GetMask + v113) & v114;
          v116 = 3 - v113;
          if ( v111 < 4 )
          {
            v119 = CInputBitStream::finalLoad(this[675], v115, v116);
          }
          else
          {
            v117 = *(_QWORD *)v110;
            v118 = *(unsigned __int8 *)(*(_QWORD *)v110 + 3LL)
                 | ((*(unsigned __int8 *)(*(_QWORD *)v110 + 2LL)
                   | (((**(unsigned __int8 **)v110 << 8) | *(unsigned __int8 *)(*(_QWORD *)v110 + 1LL)) << 8)) << 8);
            *v112 = 32 - v116;
            *((_DWORD *)v110 + 3) = v118;
            *(_QWORD *)v110 = v117 + 4;
            *((_DWORD *)v110 + 2) = v111 - 4;
            v119 = (v118 >> (32 - v116)) | (v115 << v116);
          }
        }
      }
      v120 = this[675];
      *((_DWORD *)this + 216) = v119;
      if ( !*((_DWORD *)v120 + 5) )
      {
        *((_DWORD *)this + 217) = 16 << v119;
        *((_DWORD *)this + 218) = 1 << (v119 - 1);
        return 0;
      }
    }
    else
    {
      *((_DWORD *)v125 + 5) = 1;
    }
  }
  else
  {
    *((_DWORD *)v52 + 5) = 1;
  }
  return 4294967196LL;
}

```

## disassembly

```asm
0x18001cd34  push    rbx
0x18001cd36  push    rbp
0x18001cd37  push    rsi
0x18001cd38  push    rdi
0x18001cd39  push    r12
0x18001cd3b  push    r13
0x18001cd3d  push    r14
0x18001cd3f  push    r15
0x18001cd41  sub     rsp, 28h
0x18001cd45  mov     r14, rdx
0x18001cd48  mov     rbx, rcx
0x18001cd4b  mov     rcx, [rcx+1518h]; this
0x18001cd52  mov     edx, 8; int
0x18001cd57  call    ?flushMPEG4@CInputBitStream@@QEAAXJ@Z; CInputBitStream::flushMPEG4(long)
0x18001cd5c  mov     r9, [rbx+1518h]
0x18001cd63  lea     r15, ?GetMask@@3QBKB; ulong const near * const GetMask
0x18001cd6a  mov     r12d, 20h ; ' '
0x18001cd70  xor     r13d, r13d
0x18001cd73  lea     edi, [r12-1Fh]
0x18001cd78  cmp     [r9+14h], r13d
0x18001cd7c  jnz     loc_18001D020
0x18001cd82  mov     r11d, [r9+8]
0x18001cd86  lea     r10, [r9+10h]
0x18001cd8a  mov     r8d, [rbx+1D78h]
0x18001cd91  lea     ecx, ds:0[r11*8]
0x18001cd99  cmp     ecx, r8d
0x18001cd9c  jb      loc_18001D014
0x18001cda2  mov     eax, [r10]
0x18001cda5  cmp     r8d, eax
0x18001cda8  ja      loc_18001CF02
0x18001cdae  sub     eax, r8d
0x18001cdb1  mov     [r10], eax
0x18001cdb4  mov     r11, [rbx+1518h]
0x18001cdbb  cmp     [r11+14h], r13d
0x18001cdbf  jnz     loc_18001D0FF
0x18001cdc5  mov     ecx, [rbx+37Ch]
0x18001cdcb  mov     r10d, r13d
0x18001cdce  imul    ecx, [rbx+378h]
0x18001cdd5  lea     eax, [rcx-1]
0x18001cdd8  test    eax, eax
0x18001cdda  jz      short loc_18001CDE3
0x18001cddc  add     r10d, edi
0x18001cddf  sar     eax, 1
0x18001cde1  jnz     short loc_18001CDDC
0x18001cde3  mov     r9d, r13d
0x18001cde6  cmp     ecx, edi
0x18001cde8  jg      loc_18001CEB1
0x18001cdee  mov     r10, [rbx+1518h]
0x18001cdf5  mov     [rbx+1520h], r9d
0x18001cdfc  cmp     [r10+14h], r13d
0x18001ce00  jnz     loc_18001D049
0x18001ce06  mov     ebp, [r10+8]
0x18001ce0a  lea     rsi, [r10+10h]
0x18001ce0e  mov     r11d, 5
0x18001ce14  lea     ecx, ds:0[rbp*8]
0x18001ce1b  cmp     ecx, r11d
0x18001ce1e  jb      loc_18001D03E
0x18001ce24  mov     ecx, [rsi]
0x18001ce26  mov     r9d, [r10+0Ch]
0x18001ce2a  cmp     ecx, r11d
0x18001ce2d  jb      loc_18001CF4B
0x18001ce33  add     ecx, 0FFFFFFFBh
0x18001ce36  shr     r9d, cl
0x18001ce39  and     r9d, 1Fh
0x18001ce3d  mov     [rsi], ecx
0x18001ce3f  mov     [r14], r9d
0x18001ce42  mov     r10, [rbx+1518h]
0x18001ce49  cmp     [r10+14h], r13d
0x18001ce4d  jnz     loc_18001D0FF
0x18001ce53  mov     ebp, [r10+8]
0x18001ce57  lea     r11, [r10+10h]
0x18001ce5b  lea     ecx, ds:0[rbp*8]
0x18001ce62  cmp     ecx, edi
0x18001ce64  jb      loc_18001D06B
0x18001ce6a  mov     ecx, [r11]
0x18001ce6d  mov     r9d, [r10+0Ch]
0x18001ce71  cmp     ecx, edi
0x18001ce73  jb      loc_18001CFB0
0x18001ce79  dec     ecx
0x18001ce7b  shr     r9d, cl
0x18001ce7e  and     r9d, edi
0x18001ce81  mov     [r11], ecx
0x18001ce84  mov     r10, [rbx+1518h]
0x18001ce8b  cmp     [r10+14h], r13d
0x18001ce8f  jnz     loc_18001D0FF
0x18001ce95  test    r9d, r9d
0x18001ce98  jnz     loc_18001D877
0x18001ce9e  xor     eax, eax
0x18001cea0  add     rsp, 28h
0x18001cea4  pop     r15
0x18001cea6  pop     r14
0x18001cea8  pop     r13
0x18001ceaa  pop     r12
0x18001ceac  pop     rdi
0x18001cead  pop     rsi
0x18001ceae  pop     rbp
0x18001ceaf  pop     rbx
0x18001ceb0  retn
0x18001ceb1  mov     esi, [r11+8]
0x18001ceb5  lea     ecx, ds:0[rsi*8]
0x18001cebc  cmp     ecx, r10d
0x18001cebf  jb      loc_18001D109
0x18001cec5  mov     ecx, [r11+10h]
0x18001cec9  mov     r9d, [r11+0Ch]
0x18001cecd  cmp     r10d, ecx
0x18001ced0  ja      loc_18001D098
0x18001ced6  sub     ecx, r10d
0x18001ced9  mov     edx, r10d
0x18001cedc  mov     eax, r9d
0x18001cedf  mov     [r11+10h], ecx
0x18001cee3  shr     eax, cl
0x18001cee5  mov     r9d, [r15+rdx*4]
0x18001cee9  and     r9d, eax
0x18001ceec  mov     rcx, [rbx+1518h]
0x18001cef3  cmp     [rcx+14h], r13d
0x18001cef7  jz      loc_18001CDEE
0x18001cefd  jmp     loc_18001D0FF
0x18001cf02  sub     r8d, eax; unsigned int
0x18001cf05  cmp     r11d, 4
0x18001cf09  jl      loc_18001D029
0x18001cf0f  mov     rdx, [r9]
0x18001cf12  movzx   eax, byte ptr [rdx+1]
0x18001cf16  movzx   ecx, byte ptr [rdx]
0x18001cf19  shl     ecx, 8
0x18001cf1c  or      ecx, eax
0x18001cf1e  movzx   eax, byte ptr [rdx+2]
0x18001cf22  shl     ecx, 8
0x18001cf25  or      ecx, eax
0x18001cf27  movzx   eax, byte ptr [rdx+3]
0x18001cf2b  shl     ecx, 8
0x18001cf2e  or      ecx, eax
0x18001cf30  lea     rax, [rdx+4]
0x18001cf34  mov     [r9], rax
0x18001cf37  lea     eax, [r11-4]
0x18001cf3b  mov     [r9+8], eax
0x18001cf3f  mov     eax, r12d
0x18001cf42  mov     [r9+0Ch], ecx
0x18001cf46  jmp     loc_18001CDAE
0x18001cf4b  and     r9d, [r15+rcx*4]
0x18001cf4f  sub     r11d, ecx
0x18001cf52  cmp     ebp, 4
0x18001cf55  jl      loc_18001D055
0x18001cf5b  mov     rdx, [r10]
0x18001cf5e  mov     ecx, r11d
0x18001cf61  shl     r9d, cl
0x18001cf64  movzx   eax, byte ptr [rdx+1]
0x18001cf68  movzx   r8d, byte ptr [rdx]
0x18001cf6c  shl     r8d, 8
0x18001cf70  or      r8d, eax
0x18001cf73  movzx   eax, byte ptr [rdx+2]
0x18001cf77  shl     r8d, 8
0x18001cf7b  or      r8d, eax
0x18001cf7e  movzx   eax, byte ptr [rdx+3]
0x18001cf82  shl     r8d, 8
0x18001cf86  or      r8d, eax
0x18001cf89  lea     rax, [rdx+4]
0x18001cf8d  mov     [r10], rax
0x18001cf90  lea     eax, [rbp-4]
0x18001cf93  mov     [r10+8], eax
0x18001cf97  mov     eax, r12d
0x18001cf9a  sub     eax, r11d
0x18001cf9d  mov     [r10+0Ch], r8d
0x18001cfa1  mov     ecx, eax
0x18001cfa3  mov     [rsi], eax
0x18001cfa5  shr     r8d, cl
0x18001cfa8  or      r9d, r8d
0x18001cfab  jmp     loc_18001CE3F
0x18001cfb0  and     r9d, [r15+rcx*4]
0x18001cfb4  mov     esi, edi
0x18001cfb6  sub     esi, ecx
0x18001cfb8  cmp     ebp, 4
0x18001cfbb  jl      loc_18001D082
0x18001cfc1  mov     rdx, [r10]
0x18001cfc4  mov     ecx, esi
0x18001cfc6  shl     r9d, cl
0x18001cfc9  movzx   eax, byte ptr [rdx]
0x18001cfcc  movzx   r8d, byte ptr [rdx+1]
0x18001cfd1  shl     eax, 8
0x18001cfd4  or      r8d, eax
0x18001cfd7  movzx   eax, byte ptr [rdx+2]
0x18001cfdb  shl     r8d, 8
0x18001cfdf  or      r8d, eax
0x18001cfe2  movzx   eax, byte ptr [rdx+3]
0x18001cfe6  shl     r8d, 8
0x18001cfea  or      r8d, eax
0x18001cfed  lea     rax, [rdx+4]
0x18001cff1  mov     [r10], rax
0x18001cff4  lea     eax, [rbp-4]
0x18001cff7  mov     [r10+8], eax
0x18001cffb  mov     eax, r12d
0x18001cffe  sub     eax, esi
0x18001d000  mov     [r10+0Ch], r8d
0x18001d004  mov     ecx, eax
0x18001d006  mov     [r11], eax
0x18001d009  shr     r8d, cl
0x18001d00c  or      r9d, r8d
0x18001d00f  jmp     loc_18001CE84
0x18001d014  add     ecx, [r10]
0x18001d017  cmp     ecx, r8d
0x18001d01a  jnb     loc_18001CDA2
0x18001d020  mov     [r9+14h], edi
0x18001d024  jmp     loc_18001CDB4
0x18001d029  mov     edx, [r15+rax*4]
0x18001d02d  mov     rcx, r9; this
0x18001d030  and     edx, [r9+0Ch]; unsigned int
0x18001d034  call    ?finalLoad@CInputBitStream@@AEAAKKK@Z; CInputBitStream::finalLoad(ulong,ulong)
0x18001d039  jmp     loc_18001CDB4
0x18001d03e  add     ecx, [rsi]
0x18001d040  cmp     ecx, r11d
0x18001d043  jnb     loc_18001CE24
0x18001d049  mov     [r10+14h], edi
0x18001d04d  mov     r9d, r13d
0x18001d050  jmp     loc_18001CE3F
0x18001d055  mov     r8d, r11d; unsigned int
0x18001d058  mov     edx, r9d; unsigned int
0x18001d05b  mov     rcx, r10; this
0x18001d05e  call    ?finalLoad@CInputBitStream@@AEAAKKK@Z; CInputBitStream::finalLoad(ulong,ulong)
0x18001d063  mov     r9d, eax
0x18001d066  jmp     loc_18001CE3F
0x18001d06b  add     ecx, [r11]
0x18001d06e  cmp     ecx, edi
0x18001d070  jnb     loc_18001CE6A
0x18001d076  mov     [r10+14h], edi
0x18001d07a  mov     r9d, r13d
0x18001d07d  jmp     loc_18001CE84
0x18001d082  mov     r8d, esi; unsigned int
0x18001d085  mov     edx, r9d; unsigned int
0x18001d088  mov     rcx, r10; this
0x18001d08b  call    ?finalLoad@CInputBitStream@@AEAAKKK@Z; CInputBitStream::finalLoad(ulong,ulong)
0x18001d090  mov     r9d, eax
0x18001d093  jmp     loc_18001CE84
0x18001d098  and     r9d, [r15+rcx*4]
0x18001d09c  sub     r10d, ecx
0x18001d09f  cmp     esi, 4
0x18001d0a2  jl      short loc_18001D11F
0x18001d0a4  mov     rdx, [r11]
0x18001d0a7  mov     ecx, r10d
0x18001d0aa  shl     r9d, cl
0x18001d0ad  movzx   eax, byte ptr [rdx+1]
0x18001d0b1  movzx   r8d, byte ptr [rdx]
0x18001d0b5  shl     r8d, 8
0x18001d0b9  or      r8d, eax
0x18001d0bc  movzx   eax, byte ptr [rdx+2]
0x18001d0c0  shl     r8d, 8
0x18001d0c4  or      r8d, eax
0x18001d0c7  movzx   eax, byte ptr [rdx+3]
0x18001d0cb  shl     r8d, 8
0x18001d0cf  or      r8d, eax
0x18001d0d2  lea     rax, [rdx+4]
0x18001d0d6  mov     [r11], rax
0x18001d0d9  lea     eax, [rsi-4]
0x18001d0dc  mov     [r11+8], eax
0x18001d0e0  mov     eax, r12d
0x18001d0e3  sub     eax, r10d
0x18001d0e6  mov     [r11+0Ch], r8d
0x18001d0ea  mov     ecx, eax
0x18001d0ec  mov     [r11+10h], eax
0x18001d0f0  shr     r8d, cl
0x18001d0f3  or      r9d, r8d
0x18001d0f6  jmp     loc_18001CEEC
0x18001d0fb  mov     [r9+14h], edi
0x18001d0ff  mov     eax, 0FFFFFF9Ch
0x18001d104  jmp     loc_18001CEA0
0x18001d109  add     ecx, [r11+10h]
0x18001d10d  cmp     ecx, r10d
0x18001d110  jnb     loc_18001CEC5
0x18001d116  mov     [r11+14h], edi
0x18001d11a  jmp     loc_18001CEEC
0x18001d11f  mov     r8d, r10d; unsigned int
0x18001d122  mov     edx, r9d; unsigned int
0x18001d125  mov     rcx, r11; this
0x18001d128  call    ?finalLoad@CInputBitStream@@AEAAKKK@Z; CInputBitStream::finalLoad(ulong,ulong)
0x18001d12d  mov     r9d, eax
0x18001d130  jmp     loc_18001CEEC
0x18001d135  cmp     [r10+14h], r13d
0x18001d139  jnz     loc_18001D1EB
0x18001d13f  mov     r14d, [r10+8]
0x18001d143  lea     r11, [r10+10h]
0x18001d147  lea     ecx, ds:0[r14*8]
0x18001d14f  cmp     ecx, edi
0x18001d151  jnb     short loc_18001D15E
0x18001d153  add     ecx, [r11]
0x18001d156  cmp     ecx, edi
0x18001d158  jb      loc_18001D1EB
0x18001d15e  mov     ecx, [r11]
0x18001d161  mov     r9d, [r10+0Ch]
0x18001d165  cmp     ecx, edi
0x18001d167  jnb     loc_18001D366
0x18001d16d  and     r9d, [r15+rcx*4]
0x18001d171  mov     esi, edi
0x18001d173  sub     esi, ecx
0x18001d175  cmp     r14d, 4
0x18001d179  jl      loc_18001D376
0x18001d17f  mov     rdx, [r10]
0x18001d182  mov     ecx, esi
0x18001d184  shl     r9d, cl
0x18001d187  movzx   eax, byte ptr [rdx]
0x18001d18a  movzx   r8d, byte ptr [rdx+1]
0x18001d18f  shl     eax, 8
0x18001d192  or      r8d, eax
  ... truncated ...
```
