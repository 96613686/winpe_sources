# LibRaw::open_datastream(LibRaw_abstract_datastream *)

- ea: `0x18000adf0`
- end: `0x18000cff7`
- name: `?open_datastream@LibRaw@@UEAAHPEAVLibRaw_abstract_datastream@@@Z`
- size: `8711`
- prototype: `__int64 __fastcall(LibRaw *__hidden this, struct LibRaw_abstract_datastream *)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x180002a00`
- `0x180005d03`
- `0x180005d4b`
- `0x180006bc0`
- `0x180008f30`
- `0x180009220`
- `0x18000adf0`
- `0x180014a70`
- `0x1800491d0`
- `0x1800546b0`
- `0x180094f51`
- `0x180094fc9`
- `0x180094fd5`
- `0x180094fe1`
- `0x1800b0460`
- `0x1800b0b00`
- `0x1800b4010`

## pseudocode

```c
__int64 __fastcall LibRaw::open_datastream(LibRaw *this, struct LibRaw_abstract_datastream *a2)
{
  __int64; // rax
  unsigned int (__fastcall *v5)(LibRaw *); // rax
  unsigned __int16 v6; // bx
  double v7; // xmm7_8
  void (__fastcall *v8)(LibRaw *__hidden); // rax
  int v9; // r8d
  int v10; // r9d
  int v11; // ecx
  int v12; // edx
  char *v13; // rax
  __int64 v14; // rdx
  void (__fastcall *v15)(LibRaw *); // rax
  int v16; // eax
  int v17; // r9d
  int v18; // ecx
  int v19; // edx
  int v20; // r8d
  int v21; // ecx
  int v22; // eax
  unsigned int v23; // r15d
  unsigned int v24; // esi
  __int64 v25; // r10
  unsigned int v26; // r9d
  unsigned int v27; // ecx
  __int64 v28; // kr30_8
  int v29; // eax
  int v30; // ecx
  int v31; // eax
  int v32; // ecx
  float v33; // xmm2_4
  __int16 v34; // r8
  int v35; // edx
  __int16 v36; // ax
  __int16 v37; // cx
  __int16 v38; // ax
  __int16 v39; // cx
  int v40; // r8d
  __int16 v41; // dx
  __int16 v42; // cx
  unsigned int v43; // edx
  int v44; // r10d
  int v45; // r8d
  int v46; // edx
  int v47; // ecx
  int v48; // edx
  int v49; // r11d
  int v50; // r9d
  int v51; // r10d
  int v52; // r8d
  float v53; // xmm3_4
  float v54; // xmm2_4
  double v55; // xmm0_8
  int v56; // ecx
  int v57; // ecx
  unsigned int v58; // r8d
  unsigned int v59; // eax
  unsigned int v60; // r9d
  unsigned int v61; // ecx
  unsigned int v62; // eax
  unsigned int v63; // edx
  char *v64; // rcx
  __int64 v65; // rdx
  unsigned int v66; // r8d
  unsigned int v67; // r11d
  __int16 v68; // ax
  char v69; // si
  char v70; // r10
  __int16 v71; // ax
  int v72; // r9d
  int v73; // r8d
  char v74; // si
  __m128i _XMM12; // xmm12
  __m128 si128; // xmm11
  __m128 _XMM0; // xmm0
  __m128 _XMM0; // xmm0
  __m128 _XMM1; // xmm1
  __m128 _XMM0; // xmm0
  __m128 _XMM0; // xmm0
  __m128 _XMM0; // xmm0
  __m128 v83; // xmm1
  __m128 _XMM0; // xmm0
  __m128 _XMM0; // xmm0
  __m128 _XMM0; // xmm0
  __m128 v87; // xmm1
  __m128 _XMM0; // xmm0
  __m128 _XMM0; // xmm0
  __m128 _XMM0; // xmm0
  __m128 v91; // xmm1
  __m128 v92; // xmm1
  int m; // edx
  unsigned int v94; // r10d
  unsigned int v95; // r9d
  int v96; // eax
  unsigned int v97; // r10d
  unsigned int v98; // r9d
  int v99; // eax
  unsigned int v100; // ecx
  unsigned int v101; // r9d
  int v102; // eax
  unsigned int v103; // ecx
  unsigned int v104; // r9d
  int v105; // eax
  int v106; // r8d
  __int64 v107; // rdx
  __int64 v108; // r9
  float v109; // xmm2_4
  float v110; // xmm3_4
  float *v111; // rcx
  __int64 v112; // rdx
  int v113; // ecx
  float *v114; // rax
  float v115; // xmm2_4
  __int16 v116; // ax
  __int16 v117; // ax
  unsigned __int16 v118; // ax
  __int16 v119; // ax
  unsigned __int16 v120; // dx
  unsigned __int16 v121; // ax
  int v122; // ecx
  __int64 v123; // r15
  unsigned int v124; // eax
  unsigned int i; // edx
  int v126; // esi
  _WORD *v127; // r14
  double v128; // xmm3_8
  int v129; // edx
  __int64 j; // rcx
  void (__fastcall *v131)(LibRaw *__hidden); // rax
  unsigned int k; // edx
  int v133; // ecx
  __int64 v134; // rdx
  int v135; // r8d
  int v136; // eax
  int v137; // eax
  float v138; // xmm0_4
  int v139; // r10d
  int v140; // r11d
  int v141; // r8d
  int v142; // eax
  int v143; // ecx
  int v144; // edx
  unsigned int v145; // r9d
  unsigned int v146; // r8d
  unsigned int v147; // eax
  unsigned int v148; // r9d
  void *v149; // rdx
  __int64 v150; // rax
  __int64 v151; // rsi
  int *v152; // rcx
  float *v153; // rax
  unsigned __int16 v154; // r8
  unsigned __int16 v155; // dx
  unsigned int v156; // eax
  char *v157; // rsi
  __m128i v159; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v160; // [rsp+48h] [rbp-C0h]
  const LibRaw_exceptions *v161; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v162; // [rsp+58h] [rbp-B0h] BYREF

  v160 = -2;
  if ( !a2 )
    return 2;
  if ( !(*(unsigned int (__fastcall **)(struct LibRaw_abstract_datastream *))(*(_QWORD *)a2 + 8LL))(a2) )
    return 4294867287LL;
  if ( (*(__int64 (__fastcall **)(struct LibRaw_abstract_datastream *))(*(_QWORD *)a2 + 40LL))(a2) > 0x7FFFFFFF
    && (*(__int64 (__fastcall **)(struct LibRaw_abstract_datastream *))(*(_QWORD *)a2 + 40LL))(a2) > 0x7FFFFFFF )
  {
    return 4294867284LL;
  }
  LibRaw::recycle(this);
  v5 = (unsigned int (__fastcall *)(LibRaw *))*((_QWORD *)this + 95886);
  if ( !v5 || v5(this) != 1 )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      *((_QWORD *)this + 47659) = a2;
      *((_DWORD *)this + 1346) |= 1u;
      LibRaw::identify(this);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        LibRaw::recycle(this);
         = 4294867289LL;
        __eh34_try_continuation(0, std::bad_alloc `RTTI Type Descriptor', &loc_18000CF6D);
        return ;
      }
      if ( __eh34_catch_type(0, &enum LibRaw_exceptions `RTTI Type Descriptor', &v161) )
      {
        switch ( *(_DWORD *)v161 )
        {
          case 1:
            LibRaw::recycle(this);
             = 4294867289LL;
            __eh34_try_continuation(0, &enum LibRaw_exceptions `RTTI Type Descriptor', &loc_18000CF6D);
            break;
          case 2:
          case 3:
          case 9:
            LibRaw::recycle(this);
             = 4294867288LL;
            __eh34_try_continuation(0, &enum LibRaw_exceptions `RTTI Type Descriptor', &loc_18000CF82);
            break;
          case 4:
          case 5:
            LibRaw::recycle(this);
            __eh34_try_continuation(0, &enum LibRaw_exceptions `RTTI Type Descriptor', &loc_18000CF89);
            return 4294867287LL;
          case 6:
            LibRaw::recycle(this);
             = 4294867286LL;
            __eh34_try_continuation(0, &enum LibRaw_exceptions `RTTI Type Descriptor', &loc_18000CFDB);
            break;
          case 7:
            LibRaw::recycle(this);
             = 4294867285LL;
            __eh34_try_continuation(0, &enum LibRaw_exceptions `RTTI Type Descriptor', &loc_18000CFE2);
            break;
          case 0xA:
            LibRaw::recycle(this);
            __eh34_try_continuation(0, &enum LibRaw_exceptions `RTTI Type Descriptor', &loc_18000CF7B);
            return 4294867284LL;
          case 0xB:
            LibRaw::recycle(this);
             = 4294867283LL;
            __eh34_try_continuation(0, &enum LibRaw_exceptions `RTTI Type Descriptor', &loc_18000CF74);
            break;
          case 0xC:
            LibRaw::recycle(this);
            __eh34_try_continuation(0, &enum LibRaw_exceptions `RTTI Type Descriptor', &loc_18000CFE9);
            return 4294967294LL;
          default:
             = 0xFFFFFFFFLL;
            __eh34_try_continuation(0, &enum LibRaw_exceptions `RTTI Type Descriptor', &loc_18000CFF0);
            break;
        }
        return ;
      }
      if ( __eh34_catch_type(0, std::exception `RTTI Type Descriptor', 0) )
      {
        LibRaw::recycle(this);
        __eh34_try_continuation(0, std::exception `RTTI Type Descriptor', &loc_18000CF89);
        return 4294867287LL;
      }
    }
    if ( (*((_WORD *)this + 190675) || *((_DWORD *)this + 95376)) && !*((_DWORD *)this + 133) )
    {
      v8 = (void (__fastcall *)(LibRaw *__hidden))*((_QWORD *)this + 95898);
      if ( v8 != LibRaw::unpacked_load_raw
        && v8 != LibRaw::unpacked_load_raw_FujiDBP
        && v8 != LibRaw::unpacked_load_raw_fuji_f700s20 )
      {
        return 4294967294LL;
      }
    }
    v9 = *((_DWORD *)this + 48312);
    if ( v9 >= 8 )
    {
      v6 = 0;
    }
    else
    {
      v10 = *((_DWORD *)this + 48308);
      if ( !v10 )
      {
        v11 = *((_DWORD *)this + 48312);
        if ( !*((_QWORD *)this + 47664) )
        {
          v6 = 0;
LABEL_25:
          *((_QWORD *)this + 4 * v11 + 24160) = *((_QWORD *)this + 47664);
          v14 = 32LL * v11;
          *(_DWORD *)((char *)this + v14 + 193268) = *((_DWORD *)this + 48308);
          *(_WORD *)((char *)this + v14 + 193264) = -1;
          *(_DWORD *)((char *)this + v14 + 193256) = *((_DWORD *)this + 95375);
          *(_DWORD *)((char *)this + v14 + 193272) = *((_DWORD *)this + 95374);
          *(_WORD *)((char *)this + v14 + 193260) = *((_WORD *)this + 96614);
          *(_WORD *)((char *)this + v14 + 193262) = *((_WORD *)this + 96615);
          ++*((_DWORD *)this + 48312);
          goto LABEL_27;
        }
      }
      v6 = 0;
      v12 = 0;
      v11 = *((_DWORD *)this + 48312);
      if ( v9 <= 0 )
        goto LABEL_25;
      v13 = (char *)this + 193268;
      while ( *(_QWORD *)(v13 + 12) != *((_QWORD *)this + 47664) || *(_DWORD *)v13 != v10 )
      {
        ++v12;
        v13 += 32;
        if ( v12 >= v9 )
          goto LABEL_25;
      }
    }
LABEL_27:
    *((_BYTE *)this + 915) = 0;
    v15 = (void (__fastcall *)(LibRaw *))*((_QWORD *)this + 95887);
    if ( v15 )
      v15(this);
    if ( *((_DWORD *)this + 133) )
    {
LABEL_44:
      if ( *((void (__fastcall **)(LibRaw *__hidden))this + 95898) == LibRaw::nikon_load_raw )
        LibRaw::nikon_read_curve(this);
      if ( *((void (__fastcall **)(LibRaw *__hidden))this + 95898) == LibRaw::lossless_jpeg_load_raw
        && *((_WORD *)this + 1015)
        && *((_DWORD *)this + 131) == 29
        && (!strnicmp_0((const char *)this + 268, "EOS D2000", 9u)
         || !strnicmp_0((const char *)this + 268, "EOS D6000", 9u)) )
      {
        *((_DWORD *)this + 38220) = 0;
        *((_DWORD *)this + 38222) = 4501;
        memset((char *)this + 136464, 0, 0x4020u);
        *(_OWORD *)((char *)this + 52) = 0;
        *(_OWORD *)((char *)this + 68) = 0;
        *(_OWORD *)((char *)this + 84) = 0;
        *(_OWORD *)((char *)this + 100) = 0;
        *(_OWORD *)((char *)this + 116) = 0;
        *(_OWORD *)((char *)this + 132) = 0;
        *(_OWORD *)((char *)this + 148) = 0;
        *(_OWORD *)((char *)this + 164) = 0;
        *((_DWORD *)this + 16) = 1;
        *((_DWORD *)this + 95384) |= 0x200u;
      }
      if ( *((void (__fastcall **)(LibRaw *__hidden))this + 95898) == LibRaw::panasonic_load_raw )
      {
        v17 = *((_DWORD *)this + 95397);
        if ( (unsigned int)(v17 - 6) <= 1 )
        {
          *((_DWORD *)this + 34116) = *((_DWORD *)this + 95330);
          v18 = *((_DWORD *)this + 95331);
          *((_DWORD *)this + 34117) = v18;
          *((_DWORD *)this + 34118) = *((_DWORD *)this + 95332);
          *((_DWORD *)this + 34119) = v18;
          *((_QWORD *)this + 17060) = 0;
          *((_DWORD *)this + 38220) = 0;
          v19 = *((_DWORD *)this + 38225);
          v20 = *((_DWORD *)this + 38224);
          v21 = *((_DWORD *)this + 38223);
          v22 = v20;
          if ( v20 <= v19 )
            v22 = *((_DWORD *)this + 38225);
          if ( v21 <= v22 )
          {
            v21 = *((_DWORD *)this + 38225);
            if ( v20 > v19 )
              v21 = *((_DWORD *)this + 38224);
          }
          *((_DWORD *)this + 38222) = v21;
          if ( v17 == 6 )
          {
            v23 = *((unsigned __int16 *)this + 9) / 0xBu;
            v24 = *((unsigned __int16 *)this + 9) / 0xEu;
            v25 = *((unsigned int *)this + 95370);
            if ( !*((_DWORD *)this + 95370) )
              v25 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 40LL))(*((_QWORD *)this + 47659))
                  - *((_QWORD *)this + 47680);
            v26 = *((unsigned __int16 *)this + 9);
            if ( v26 == 11 * (v26 / 0xB) && (int)(16 * v23) * (unsigned __int64)*((unsigned __int16 *)this + 8) == v25
              || v26 == 14 * (v26 / 0xE) && (int)(16 * v24) * (unsigned __int64)*((unsigned __int16 *)this + 8) == v25 )
            {
              *((_QWORD *)this + 95898) = LibRaw::panasonicC6_load_raw;
              goto LABEL_72;
            }
          }
          else
          {
            if ( v17 != 7 )
              goto LABEL_72;
            v27 = (*((_DWORD *)this + 95398) != 14) + 9;
            if ( !(*((unsigned __int16 *)this + 9) % v27)
              && *((unsigned __int16 *)this + 8) * (__int64)(int)(16 * (*((unsigned __int16 *)this + 9) / v27)) == *((_DWORD *)this + 95370) )
            {
              *((_QWORD *)this + 95898) = LibRaw::panasonicC7_load_raw;
              goto LABEL_72;
            }
          }
          *((_DWORD *)this + 132) = 0;
        }
      }
LABEL_72:
      if ( *((_DWORD *)this + 131) == 43
        && (!strnicmp_0((const char *)this + 268, "Z", 1u) || !stricmp_0((const char *)this + 268, "D6")) )
      {
        v28 = 7 * *((unsigned __int16 *)this + 9);
        if ( 16 * *((unsigned __int16 *)this + 8) * (int)ceilf_0((float)(((BYTE4(v28) & 3) + (int)v28) >> 2) * 0.0625) == *((_DWORD *)this + 95370) )
          *((_QWORD *)this + 95898) = LibRaw::nikon_14bit_load_raw;
      }
      v29 = *((_DWORD *)this + 131);
      if ( v29 == 63 )
      {
        v30 = *((_DWORD *)this + 38222);
        if ( v30 )
        {
          v31 = *((_DWORD *)this + 38223);
          if ( v31 > v30 && v31 <= 4 * v30 )
          {
            *((_DWORD *)this + 38223) = v31 / 4;
            *((int *)this + 38224) /= 4;
            *((int *)this + 38225) /= 4;
            *((int *)this + 38226) /= 4;
          }
        }
      }
      else if ( v29 == 8 )
      {
        v40 = *((_DWORD *)this + 133);
        if ( !v40 )
        {
          v41 = *((_WORD *)this + 1031);
          if ( v41 != -1 )
          {
            if ( *((_WORD *)this + 90) )
            {
              *((_WORD *)this + 91) += v41;
              *((_WORD *)this + 92) += *((_WORD *)this + 1030);
            }
            else
            {
              *((_WORD *)this + 91) = v41;
              v42 = *((_WORD *)this + 1030);
              *((_WORD *)this + 92) = v42;
              *((_WORD *)this + 93) = *((_WORD *)this + 1033) - v41 + 1;
              *((_WORD *)this + 94) = *((_WORD *)this + 1032) - v42 + 1;
            }
          }
        }
        v43 = *((_DWORD *)this + 48104);
        if ( v43 < 0xE && !v40 && *((void (__fastcall **)(LibRaw *__hidden))this + 95898) != LibRaw::canon_sraw_load_raw )
        {
          v44 = *((_DWORD *)this + 486);
          if ( v44 > (1 << v43) - 1 )
          {
            v45 = 1 << (14 - v43);
            *((int *)this + 38223) /= v45;
            *((int *)this + 38224) /= v45;
            *((int *)this + 38225) /= v45;
            *((int *)this + 38226) /= v45;
            *((int *)this + 488) /= v45;
            *((int *)this + 489) /= v45;
            *((int *)this + 490) /= v45;
            *((int *)this + 491) /= v45;
            *((int *)this + 492) /= v45;
            *((_DWORD *)this + 486) = v44 / v45;
            *((int *)this + 487) /= v45;
          }
        }
      }
      if ( *((_DWORD *)this + 131) == 8
        && *((void (__fastcall **)(LibRaw *__hidden))this + 95898) == LibRaw::canon_sraw_load_raw )
      {
        v32 = *((unsigned __int16 *)this + 9);
        if ( (_WORD)v32 )
        {
          v33 = (float)*((unsigned __int16 *)this + 8) / (float)v32;
          if ( v33 >= 0.57 && v33 <= 0.75
            || (v34 = *((_WORD *)this + 1009), v34 <= 1)
            || (v35 = *((unsigned __int16 *)this + 1008), (__int16)v35 <= 1) )
          {
            if ( (_WORD)v32 == 4032 && *((_WORD *)this + 8) == 3402 && !stricmp_0((const char *)this + 268, "EOS 80D") )
            {
              *((_DWORD *)this + 4) = 297274320;
              *((_DWORD *)this + 6) = 1835016;
              *((_DWORD *)this + 5) = 295439304;
              *((_DWORD *)this + 7) = 295439304;
              *((_DWORD *)this + 95384) |= 0x100u;
              *((_DWORD *)this + 8) = 36288;
            }
          }
          else
          {
            *((_WORD *)this + 9) = v35;
            v36 = *((_WORD *)this + 1031);
            *((_WORD *)this + 13) = v36;
            v37 = *((_WORD *)this + 1033) - v36 + 1;
            *((_WORD *)this + 11) = v37;
            *((_WORD *)this + 15) = v37;
            *((_WORD *)this + 8) = v34;
            v38 = *((_WORD *)this + 1030);
            *((_WORD *)this + 12) = v38;
            v39 = *((_WORD *)this + 1032) - v38 + 1;
            *((_WORD *)this + 10) = v39;
            *((_WORD *)this + 14) = v39;
            *((_DWORD *)this + 95384) |= 0x100u;
            *((_DWORD *)this + 8) = 8 * v35;
          }
        }
      }
      if ( !*((_DWORD *)this + 133)
        && *((_DWORD *)this + 131) == 18
        && *((void (__fastcall **)(LibRaw *__hidden))this + 95898) == LibRaw::unpacked_load_raw )
      {
        v46 = *((_DWORD *)this + 95370);
        v47 = *((unsigned __int16 *)this + 8) * *((unsigned __int16 *)this + 9);
        if ( 2 * v47 != v46 )
        {
          if ( (unsigned int)(7 * v47) >> 2 == v46 )
          {
            *((_QWORD *)this + 95898) = LibRaw::fuji_14bit_load_raw;
            goto LABEL_114;
          }
LABEL_113:
          LibRaw::parse_fuji_compressed_header(this);
          goto LABEL_114;
        }
        if ( !strcmp_0((const char *)this + 460, "X-H2S")
          && (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 40LL))(*((_QWORD *)this + 47659)) < *((_QWORD *)this + 47680) + *((unsigned int *)this + 95370) )
        {
          goto LABEL_113;
        }
      }
LABEL_114:
      v48 = *((unsigned __int16 *)this + 90);
      if ( (unsigned __int16)(v48 - 99) <= 0x26ADu )
      {
        v49 = *((unsigned __int16 *)this + 91);
        if ( (_WORD)v49 != 0xFFFF )
        {
          v50 = *((unsigned __int16 *)this + 93);
          if ( v50 + v49 <= (unsigned int)*((unsigned __int16 *)this + 9) )
          {
            v51 = *((unsigned __int16 *)this + 92);
            if ( (_WORD)v51 != 0xFFFF )
            {
              v52 = *((unsigned __int16 *)this + 94);
              if ( v52 + v51 <= (unsigned int)*((unsigned __int16 *)this + 8) )
              {
                if ( (_WORD)v50 )
                {
                  if ( (_WORD)v52 )
                  {
                    if ( *((_WORD *)this + 95) == 0xFFFF && *((_WORD *)this + 96) == 0xFFFF )
                    {
                      v53 = (float)v50;
                      v54 = (float)v48 / 1000.0;
                      v55 = (float)((float)((float)v50 / (float)v52) / v54);
                      if ( v55 < 0.98 || v55 > 1.02 )
                      {
                        if ( v54 <= (float)(v53 / (float)v52) )
                        {
                          v57 = (int)(float)((float)v52 * v54);
                          *((_WORD *)this + 95) = v49 + (v50 - v57) / 2;
                          *((_WORD *)this + 97) = v57;
                          *((_WORD *)this + 96) = v51;
                          *((_WORD *)this + 98) = v52;
                        }
                        else
                        {
                          v56 = (int)(float)(v53 / v54);
                          *((_WORD *)this + 96) = v51 + (v52 - v56) / 2;
                          *((_WORD *)this + 98) = v56;
                          *((_WORD *)this + 95) = v49;
                          *((_WORD *)this + 97) = v50;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      if ( *((_DWORD *)this + 131) == 18 && *((_DWORD *)this + 136) == 9 )
      {
        v58 = *((unsigned __int16 *)this + 12);
        v59 = 6 * (v58 / 6);
        v60 = v59 + 6;
        if ( v58 == v59 )
          v60 = *((unsigned __int16 *)this + 12);
        v61 = *((unsigned __int16 *)this + 13);
        v62 = 6 * (v61 / 6);
        v63 = v62 + 6;
        if ( v61 == v62 )
          v63 = *((unsigned __int16 *)this + 13);
        if ( v60 != v58 || v63 != v61 )
        {
          *((_WORD *)this + 10) += v58 - v60;
          *((_WORD *)this + 12) = v60;
          *((_WORD *)this + 11) += v61 - v63;
          *((_WORD *)this + 13) = v63;
          v64 = (char *)this + 548;
          v65 = 6;
          do
          {
            *v64 = v64[36];
            v64[1] = v64[37];
            v64[2] = v64[38];
            v64[3] = v64[39];
            v64[4] = v64[40];
            v64[5] = v64[41];
            v64 += 6;
            --v65;
          }
          while ( v65 );
        }
        v66 = 6;
        goto LABEL_153;
      }
      if ( *((_WORD *)this + 190675) )
        goto LABEL_177;
      v67 = *((_DWORD *)this + 136);
      if ( v67 < 0x3E8 )
        goto LABEL_177;
      v68 = *((_WORD *)this + 12);
      if ( (v68 & 1) != 0 )
      {
        *((_WORD *)this + 12) = v68 + 1;
        --*((_WORD *)this + 10);
        v69 = 1;
      }
      else
      {
        if ( (*((_BYTE *)this + 26) & 1) == 0 )
        {
LABEL_152:
          v66 = 2;
LABEL_153:
          v94 = *((unsigned __int16 *)this + 91);
          if ( (unsigned __int16)(v94 - 1) <= 0xFFFDu )
          {
            v95 = *((unsigned __int16 *)this + 93);
            if ( (unsigned __int16)(v95 - 1) <= 0xFFFDu )
            {
              if ( v94 % v66 )
              {
                if ( v95 > v66 )
                {
                  v96 = v66 * (v94 / v66 + 1) - v94;
                  if ( v96 > 0 )
                  {
                    *((_WORD *)this + 91) = v94 + v96;
                    *((_WORD *)this + 93) = v95 - v96;
                  }
                }
              }
            }
          }
          v97 = *((unsigned __int16 *)this + 92);
          if ( (unsigned __int16)(v97 - 1) <= 0xFFFDu )
          {
            v98 = *((unsigned __int16 *)this + 94);
            if ( (unsigned __int16)(v98 - 1) <= 0xFFFDu )
            {
              if ( v97 % v66 )
              {
                if ( v98 > v66 )
                {
                  v99 = v66 * (v97 / v66 + 1) - v97;
                  if ( v99 > 0 )
                  {
                    *((_WORD *)this + 92) = v97 + v99;
                    *((_WORD *)this + 94) = v98 - v99;
                  }
                }
              }
            }
          }
          v100 = *((unsigned __int16 *)this + 95);
          if ( (unsigned __int16)(v100 - 1) <= 0xFFFDu )
          {
            v101 = *((unsigned __int16 *)this + 97);
            if ( (unsigned __int16)(v101 - 1) <= 0xFFFDu )
            {
              if ( v100 % v66 )
              {
                if ( v101 > v66 )
                {
                  v102 = v66 * (v100 / v66 + 1) - v100;
                  if ( v102 > 0 )
                  {
                    *((_WORD *)this + 95) = v102 + v100;
                    *((_WORD *)this + 97) = v101 - v102;
                  }
                }
              }
            }
          }
          v103 = *((unsigned __int16 *)this + 96);
          if ( (unsigned __int16)(v103 - 1) <= 0xFFFDu )
          {
            v104 = *((unsigned __int16 *)this + 98);
            if ( (unsigned __int16)(v104 - 1) <= 0xFFFDu )
            {
              if ( v103 % v66 )
              {
                if ( v104 > v66 )
                {
                  v105 = v66 * (v103 / v66 + 1) - v103;
                  if ( v105 > 0 )
                  {
                    *((_WORD *)this + 96) = v105 + v103;
                    *((_WORD *)this + 98) = v104 - v105;
                  }
                }
              }
            }
          }
LABEL_177:
          if ( *((_DWORD *)this + 133) )
          {
            if ( !*((_DWORD *)this + 136) )
            {
              v106 = *((_DWORD *)this + 135);
              if ( (unsigned int)(v106 - 2) <= 2 )
              {
                v162 = 0;
                v159 = _mm_add_epi32(
                         _mm_shuffle_epi32(_mm_cvtsi32_si128(*((_DWORD *)this + 42614)), 0),
                         _mm_loadu_si128((const __m128i *)((char *)this + 154040)));
                if ( v106 > 0 )
                {
                  v107 = 0;
                  v108 = (unsigned int)v106;
                  do
                  {
                    *(float *)((char *)&v162 + v107 * 4) = (float)(*(_DWORD *)((char *)&v159
                                                                             + v107 * 4
                                                                             + this
                                                                             - (LibRaw *)&v159
                                                                             + 186880)
                                                                 - v159.m128i_i32[v107]);
                    ++v107;
                    --v108;
                  }
                  while ( v108 );
                }
                v109 = *(float *)&v162;
                v110 = *(float *)&v162;
                if ( v106 > 1 )
                {
                  v111 = (float *)&v162 + 1;
                  v112 = (unsigned int)(v106 - 1);
                  do
                  {
                    v109 = fminf(*v111, v109);
                    v110 = fmaxf(*v111++, v110);
                    --v112;
                  }
                  while ( v112 );
                }
                if ( v109 > 1.0 && (float)(v109 * 20.0) > v110 )
                {
                  v113 = 0;
                  if ( v106 > 0 )
                  {
                    v114 = (float *)((char *)this + 153060);
                    do
                    {
                      v115 = *(float *)((char *)v114 + (char *)&v162 - (char *)this - 153060) / v110;
                      *(v114 - 4) = *(v114 - 4) / v115;
                      *v114 = *v114 / v115;
                      ++v113;
                      ++v114;
                    }
                    while ( v113 < *((_DWORD *)this + 135) );
                  }
                  *((_DWORD *)this + 38222) = (int)(float)((float)*((int *)this + 34116) + v110);
                }
              }
            }
            if ( *((_DWORD *)this + 133)
              && *((_DWORD *)this + 131) == 47
              && !stricmp_0((const char *)this + 460, "DMC-LX100") )
            {
              *((_WORD *)this + 11) = 4288;
            }
          }
          if ( *((_DWORD *)this + 133) && *((_DWORD *)this + 131) == 32 && !stricmp_0((const char *)this + 460, "SL2") )
            *((_WORD *)this + 10) -= 16;
          if ( *((_DWORD *)this + 131) == 63 )
          {
            if ( *((_DWORD *)this + 133) )
            {
              v116 = *((_WORD *)this + 9);
              switch ( v116 )
              {
                case 3984:
                  *((_WORD *)this + 11) = 3925;
                  goto LABEL_236;
                case 4288:
                  *((_WORD *)this + 11) = 4256;
                  goto LABEL_236;
                case 4928:
                  if ( *((_WORD *)this + 10) < 0xCD0u )
                    *((_WORD *)this + 11) = 4920;
                  goto LABEL_236;
              }
              if ( v116 != 5504 )
                goto LABEL_236;
              v117 = 5472;
              if ( *((_WORD *)this + 10) > 0xE50u )
                v117 = 5496;
LABEL_235:
              *((_WORD *)this + 11) = v117;
              goto LABEL_236;
            }
            if ( *((void (__fastcall **)(LibRaw *__hidden))this + 95898) == LibRaw::sony_arq_load_raw )
            {
              v118 = *((_WORD *)this + 9);
              if ( v118 <= 0x2EE0u )
                v119 = v118 - 32;
              else
                v119 = v118 - 64;
              *((_WORD *)this + 11) = v119;
            }
            if ( (!strnicmp_0((const char *)this + 268, "ILCE-7RM", 8u)
               || !stricmp_0((const char *)this + 268, "ILCA-99M2"))
              && ((v120 = *((_WORD *)this + 9), v121 = v120, v120 == 5216) || v120 == 6304)
              || !stricmp_0((const char *)this + 268, "ILCE-7R")
              && (v121 = *((_WORD *)this + 9), v121 >= 0x11E4u)
              && v121 < 0x139Cu
              || !stricmp_0((const char *)this + 268, "ILCE-7") && (v121 = *((_WORD *)this + 9), v121 == 3968)
              || (!strnicmp_0((const char *)this + 268, "ILCE-7M", 7u)
               || !stricmp_0((const char *)this + 268, "ILCE-9")
               || *((_QWORD *)this + 168) == 294)
              && (v121 = *((_WORD *)this + 9), v121 > 0xEA6u)
              && v121 < 0x1018u
              || !strnicmp_0((const char *)this + 268, "ILCE-7S", 7u) && (v121 = *((_WORD *)this + 9), v121 == 2816) )
            {
              v117 = v121 - 32;
              goto LABEL_235;
            }
          }
LABEL_236:
          v122 = *((_DWORD *)this + 131);
          if ( v122 == 49 && *((_DWORD *)this + 132) == 4 && (*((_BYTE *)this + 5344) & 1) != 0 )
          {
            *((_DWORD *)this + 132) = 1;
            *(_QWORD *)((char *)this + 540) = 4;
            *((_WORD *)this + 12) += 2;
            *((_WORD *)this + 13) += 2;
            *((_WORD *)this + 11) -= 4;
            *((_WORD *)this + 10) -= 4;
            *((_DWORD *)this + 95334) = 1;
            *((_QWORD *)this + 95899) = *((_QWORD *)this + 95898);
            *((_QWORD *)this + 95898) = LibRaw::pentax_4shot_load_raw;
          }
          v123 = 4;
          if ( !*((_DWORD *)this + 133) )
          {
            if ( v122 == 31 )
            {
              if ( !strcmp_0((const char *)this + 268, "Credo 50") )
              {
                *((_DWORD *)this + 38265) = 1075881087;
                *((_DWORD *)this + 38267) = 1067907222;
                *((_DWORD *)this + 38268) = 1065353216;
                *((_DWORD *)this + 38266) = 1065353216;
              }
            }
            else if ( v122 == 18
                   && (!strncmp_0((const char *)this + 268, "S20Pro", 6u)
                    || !strncmp_0((const char *)this + 268, "F700", 4u)) )
            {
              *((_WORD *)this + 9) >>= 1;
              *((_QWORD *)this + 95898) = LibRaw::unpacked_load_raw_fuji_f700s20;
            }
          }
          if ( *((void (__fastcall **)(LibRaw *__hidden))this + 95898) == LibRaw::packed_load_raw )
          {
            if ( *((_DWORD *)this + 131) == 43
              && !*((_DWORD *)this + 95384)
              && (!strnicmp_0((const char *)this + 268, "D810", 4u) || !stricmp_0((const char *)this + 268, "D4S"))
              && 2 * *((_DWORD *)this + 95370) == 3 * *((unsigned __int16 *)this + 8) * *((unsigned __int16 *)this + 9) )
            {
              *((_DWORD *)this + 95384) = 80;
            }
            if ( *((void (__fastcall **)(LibRaw *__hidden))this + 95898) == LibRaw::packed_load_raw
              && *((_DWORD *)this + 131) == 63 )
            {
              if ( *((_DWORD *)this + 38222) > 0xFFFu )
                *((_DWORD *)this + 38222) = 4095;
              v124 = *((_DWORD *)this + 38220);
              if ( v124 > 0x100 || *((_DWORD *)this + 34116) > 0x100u )
              {
                *((_DWORD *)this + 38220) = v124 >> 2;
                *((_DWORD *)this + 34116) >>= 2;
                *((_DWORD *)this + 34117) >>= 2;
                *((_DWORD *)this + 34118) >>= 2;
                *((_DWORD *)this + 34119) >>= 2;
                for ( i = 0; i < *((_DWORD *)this + 34120) * *((_DWORD *)this + 34121); ++i )
                  *((_DWORD *)this + i + 34122) >>= 2;
              }
            }
          }
          if ( *((void (__fastcall **)(LibRaw *__hidden))this + 95898) == LibRaw::nikon_yuv_load_raw )
          {
            *((_QWORD *)this + 95898) = LibRaw::nikon_load_sraw;
            *((_DWORD *)this + 38220) = 0;
            memset((char *)this + 136464, 0, 0x4020u);
            *(_QWORD *)((char *)this + 540) = 3;
            *((_DWORD *)this + 95377) = 3;
            v126 = 0;
            v127 = (_WORD *)((char *)this + 5392);
            v7 = DOUBLE_1_0;
            do
            {
              v128 = (double)v126 / 3072.0;
              *v127 = (int)(fmax(
                              0.0,
                              1.0
                            - exp_0(
                                v128 * 0.0579342238397656
                              - v128 * 3.28163551282665 * v128
                              - v128 * -8.431360048426781 * v128 * v128
                              - v128 * 10.3533181861023 * v128 * v128 * v128))
                          * 16383.0);
              ++v126;
              ++v127;
            }
            while ( v126 <= 3072 );
            v129 = 0;
            for ( j = 0; j < 48; j += 16 )
            {
              *(float *)((char *)this + j + 153172) = (float)(v129 == 0);
              *(float *)((char *)this + j + 153176) = (float)(v129 == 1);
              *(float *)((char *)this + j + 153180) = (float)(v129 == 2);
              *(float *)((char *)this + j + 153184) = (float)(v129++ == 3);
            }
          }
          else
          {
            v7 = DOUBLE_1_0;
          }
          v131 = (void (__fastcall *)(LibRaw *__hidden))*((_QWORD *)this + 95898);
          if ( (v131 == LibRaw::nikon_load_raw
             || v131 == LibRaw::packed_load_raw
             || v131 == LibRaw::nikon_load_padded_packed_raw)
            && *((_DWORD *)this + 131) == 43 )
          {
            if ( strncmp_0((const char *)this + 268, "COOLPIX", 7u) )
            {
              if ( *((_DWORD *)this + 95378) == 12 )
              {
                *((_DWORD *)this + 38222) = 4095;
                *((_DWORD *)this + 38220) >>= 2;
                *((_DWORD *)this + 34116) >>= 2;
                *((_DWORD *)this + 34117) >>= 2;
                *((_DWORD *)this + 34118) >>= 2;
                *((_DWORD *)this + 34119) >>= 2;
                for ( k = 0; k < *((_DWORD *)this + 34121) * *((_DWORD *)this + 34120); ++k )
                  *((_DWORD *)this + k + 34122) >>= 2;
              }
            }
          }
          v133 = *((_DWORD *)this + 131);
          if ( *((void (__fastcall **)(LibRaw *__hidden))this + 95898) == LibRaw::nikon_load_sraw )
          {
            *((_DWORD *)this + 48085) = 9;
LABEL_291:
            v134 = 5;
            goto LABEL_292;
          }
          if ( v133 == 8 )
          {
            if ( *((_DWORD *)this + 493) >= 8u && *((_DWORD *)this + 494) )
            {
              *((_DWORD *)this + 48085) = 3;
              goto LABEL_291;
            }
          }
          else if ( v133 == 43 )
          {
            if ( *((_DWORD *)this + 549) == 1 )
            {
              v134 = 5;
              *((_DWORD *)this + 48085) = 5;
LABEL_292:
              v135 = *((_DWORD *)this + 38223);
              if ( v135 < 0 )
              {
                if ( *((_DWORD *)this + 133) )
                {
                  v135 = *((_DWORD *)this + 34122) - v135;
                  *((_DWORD *)this + 38223) = v135;
                  *((_DWORD *)this + 38224) = *((_DWORD *)this + 34123) - *((_DWORD *)this + 38224);
                  *((_DWORD *)this + 38225) = *((_DWORD *)this + 34124) - *((_DWORD *)this + 38225);
                  v136 = *((_DWORD *)this + 34125);
                }
                else
                {
                  v135 = *((_DWORD *)this + 34116) - v135;
                  *((_DWORD *)this + 38223) = v135;
                  *((_DWORD *)this + 38224) = *((_DWORD *)this + 34117) - *((_DWORD *)this + 38224);
                  *((_DWORD *)this + 38225) = *((_DWORD *)this + 34118) - *((_DWORD *)this + 38225);
                  v136 = *((_DWORD *)this + 34119);
                }
                *((_DWORD *)this + 38226) = v136 - *((_DWORD *)this + 38226);
              }
              if ( v133 == 43 )
              {
                if ( !v135 )
                {
                  v137 = *((_DWORD *)this + 38222);
                  if ( (unsigned int)v137 > 0x400
                    && *((void (__fastcall **)(LibRaw *__hidden))this + 95898) != LibRaw::nikon_load_sraw )
                  {
                    v138 = (float)v137 / 1.0700001;
                    *((_DWORD *)this + 38226) = (int)v138;
                    *((_DWORD *)this + 38225) = (int)v138;
                    *((_DWORD *)this + 38224) = (int)v138;
                    *((_DWORD *)this + 38223) = (int)v138;
                  }
                }
              }
              else if ( v133 == 49 && *((_QWORD *)this + 168) == 77012 )
              {
                v152 = (int *)((char *)this + 186964);
                do
                {
                  if ( v152[1] )
                  {
                    *v152 = (int)(float)((float)*v152 * 1.0503);
                    v152[2] = (int)(float)((float)v152[2] * 2.2867);
                  }
                  if ( v152[5] )
                  {
                    v152[4] = (int)(float)((float)v152[4] * 1.0503);
                    v152[6] = (int)(float)((float)v152[6] * 2.2867);
                  }
                  if ( v152[9] )
                  {
                    v152[8] = (int)(float)((float)v152[8] * 1.0503);
                    v152[10] = (int)(float)((float)v152[10] * 2.2867);
                  }
                  if ( v152[13] )
                  {
                    v152[12] = (int)(float)((float)v152[12] * 1.0503);
                    v152[14] = (int)(float)((float)v152[14] * 2.2867);
                  }
                  if ( v152[17] )
                  {
                    v152[16] = (int)(float)((float)v152[16] * 1.0503);
                    v152[18] = (int)(float)((float)v152[18] * 2.2867);
                  }
                  v152 += 20;
                  --v134;
                }
                while ( v134 );
                v153 = (float *)((char *)this + 191064);
                do
                {
                  if ( *(v153 - 1) > 0.0 )
                  {
                    *v153 = *v153 * 1.0503;
                    v153[2] = v153[2] * 2.2867;
                  }
                  if ( v153[4] > 0.0 )
                  {
                    v153[5] = v153[5] * 1.0503;
                    v153[7] = v153[7] * 2.2867;
                  }
                  if ( v153[9] > 0.0 )
                  {
                    v153[10] = v153[10] * 1.0503;
                    v153[12] = v153[12] * 2.2867;
                  }
                  if ( v153[14] > 0.0 )
                  {
                    v153[15] = v153[15] * 1.0503;
                    v153[17] = v153[17] * 2.2867;
                  }
                  if ( v153[19] > 0.0 )
                  {
                    v153[20] = v153[20] * 1.0503;
                    v153[22] = v153[22] * 2.2867;
                  }
                  if ( v153[24] > 0.0 )
                  {
                    v153[25] = v153[25] * 1.0503;
                    v153[27] = v153[27] * 2.2867;
                  }
                  if ( v153[29] > 0.0 )
                  {
                    v153[30] = v153[30] * 1.0503;
                    v153[32] = v153[32] * 2.2867;
                  }
                  if ( v153[34] > 0.0 )
                  {
                    v153[35] = v153[35] * 1.0503;
                    v153[37] = v153[37] * 2.2867;
                  }
                  if ( v153[39] > 0.0 )
                  {
                    v153[40] = v153[40] * 1.0503;
                    v153[42] = v153[42] * 2.2867;
                  }
                  if ( v153[44] > 0.0 )
                  {
                    v153[45] = v153[45] * 1.0503;
                    v153[47] = v153[47] * 2.2867;
                  }
                  if ( v153[49] > 0.0 )
                  {
                    v153[50] = v153[50] * 1.0503;
                    v153[52] = v153[52] * 2.2867;
                  }
                  if ( v153[54] > 0.0 )
                  {
                    v153[55] = v153[55] * 1.0503;
                    v153[57] = v153[57] * 2.2867;
                  }
                  if ( v153[59] > 0.0 )
                  {
                    v153[60] = v153[60] * 1.0503;
                    v153[62] = v153[62] * 2.2867;
                  }
                  if ( v153[64] > 0.0 )
                  {
                    v153[65] = v153[65] * 1.0503;
                    v153[67] = v153[67] * 2.2867;
                  }
                  if ( v153[69] > 0.0 )
                  {
                    v153[70] = v153[70] * 1.0503;
                    v153[72] = v153[72] * 2.2867;
                  }
                  if ( v153[74] > 0.0 )
                  {
                    v153[75] = v153[75] * 1.0503;
                    v153[77] = v153[77] * 2.2867;
                  }
                  v153 += 80;
                  --v123;
                }
                while ( v123 );
                *((float *)this + 38265) = (float)*((int *)this + 46745);
                *((float *)this + 38266) = (float)*((int *)this + 46746);
                *((float *)this + 38267) = (float)*((int *)this + 46747);
                *((float *)this + 38268) = (float)*((int *)this + 46748);
              }
              if ( *((void (__fastcall **)(LibRaw *__hidden))this + 95898) == LibRaw::panasonic_load_raw
                && *((_DWORD *)this + 131) == 47 )
              {
                v139 = *((_DWORD *)this + 95330);
                if ( v139 )
                {
                  v140 = *((_DWORD *)this + 95331);
                  if ( v140 )
                  {
                    v141 = *((_DWORD *)this + 95332);
                    if ( v141 )
                    {
                      v142 = *((_DWORD *)this + 95397);
                      if ( v142 == 5 )
                        *((_DWORD *)this + 95336) = 0;
                      v143 = 0;
                      if ( v142 == 4 )
                        v143 = 15;
                      v144 = v143 + v139;
                      v145 = v143 + v140;
                      v146 = v143 + v141;
                      if ( v143 + v140 <= (unsigned int)(v143 + v139) )
                        v139 = v140;
                      if ( v143 + v139 <= v145 )
                        v140 = v139;
                      v147 = v140 + v143;
                      if ( v140 + v143 > v146 )
                        v147 = v146;
                      *((_DWORD *)this + 34116) = v144 - v147;
                      v148 = v145 - v147;
                      *((_DWORD *)this + 34117) = v148;
                      *((_DWORD *)this + 34118) = v146 - v147;
                      *((_DWORD *)this + 34119) = v148;
                      *((_DWORD *)this + 38220) = v147;
                    }
                  }
                }
              }
              if ( *((_DWORD *)this + 38416) )
              {
                v149 = (void *)*((_QWORD *)this + 19207);
                if ( v149 )
                  LibRaw::free(this, v149);
                v150 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 40LL))(*((_QWORD *)this + 47659));
                v151 = *((unsigned int *)this + 38416);
                if ( v151 >= v150 - *((_QWORD *)this + 47663) )
                  v151 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 40LL))(*((_QWORD *)this
                                                                                                  + 47659))
                       - *((_QWORD *)this + 47663);
                if ( (unsigned __int64)(v151 - 1) > 0xFFFFFFE )
                {
                  *((_QWORD *)this + 19207) = 0;
                }
                else
                {
                  *((_QWORD *)this + 19207) = LibRaw::calloc(this, v151, 1u);
                  *((_DWORD *)this + 38416) = v151;
                  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 47659) + 24LL))(
                    *((_QWORD *)this + 47659),
                    *((_QWORD *)this + 47663),
                    0);
                  (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**((_QWORD **)this + 47659) + 16LL))(
                    *((_QWORD *)this + 47659),
                    *((_QWORD *)this + 19207),
                    v151,
                    1);
                }
              }
              *((_DWORD *)this + 1346) |= 2u;
              goto LABEL_376;
            }
          }
          else if ( v133 == 49 && (*((_BYTE *)this + 3921) & 1) != 0 )
          {
            *((_DWORD *)this + 48085) = 17;
            goto LABEL_291;
          }
          *((_DWORD *)this + 48085) = 0;
          goto LABEL_291;
        }
        v69 = 0;
      }
      v70 = 0;
      v71 = *((_WORD *)this + 13);
      if ( (v71 & 1) != 0 )
      {
        *((_WORD *)this + 13) = v71 + 1;
        --*((_WORD *)this + 11);
        v70 = 1;
      }
      v72 = 0;
      v73 = 0;
      v74 = 2 * v69;
      if ( _isa_available < 5 )
      {
        for ( m = 0; m < 32; m += 2 )
        {
          v72 |= ((v67 >> ((-2 * (v70 + (v73 & 1))) & 2 | (2 * (v74 + (v73 & 0xFE))) & 0x1C)) & 3) << m;
          ++v73;
        }
      }
      else
      {
        _XMM12 = _mm_shuffle_epi32(_mm_cvtsi32_si128(v67), 0);
        si128 = (__m128)_mm_load_si128((const __m128i *)&_xmm);
        __asm { vpsrlvd xmm0, xmm12, xmm0 }
        _XMM0 = _mm_and_ps(_XMM0, si128);
        __asm { vpsllvd xmm1, xmm0, cs:__xmm@0000000e0000000c0000000a00000008 }
        __asm { vpsrlvd xmm0, xmm12, xmm3 }
        _XMM0 = _mm_and_ps(_XMM0, si128);
        __asm { vpsllvd xmm0, xmm0, cs:__xmm@00000016000000140000001200000010 }
        v83 = _mm_or_ps(_XMM1, _XMM0);
        __asm { vpsrlvd xmm0, xmm12, xmm2 }
        _XMM0 = _mm_and_ps(_XMM0, si128);
        __asm { vpsllvd xmm0, xmm0, cs:__xmm@0000001e0000001c0000001a00000018 }
        v87 = _mm_or_ps(v83, _XMM0);
        __asm { vpsrlvd xmm0, xmm12, xmm7 }
        _XMM0 = _mm_and_ps(_XMM0, si128);
        __asm { vpsllvd xmm0, xmm0, cs:__xmm@00000006000000040000000200000000 }
        v91 = _mm_or_ps(v87, _XMM0);
        v92 = _mm_or_ps(v91, (__m128)_mm_srli_si128((__m128i)v91, 8));
        v72 = _mm_cvtsi128_si32((__m128i)_mm_or_ps(v92, (__m128)_mm_srli_si128((__m128i)v92, 4)));
      }
      *((_DWORD *)this + 136) = v72;
      goto LABEL_152;
    }
    v16 = *((_DWORD *)this + 131);
    if ( v16 == 18 )
    {
      if ( !strcmp_0((const char *)this + 460, "S3Pro")
        || !strcmp_0((const char *)this + 460, "S5Pro")
        || !strcmp_0((const char *)this + 460, "S2Pro") )
      {
LABEL_39:
        *(_DWORD *)((char *)this + 186) = 0;
        *(_DWORD *)((char *)this + 182) = -1;
      }
    }
    else if ( v16 == 8
           && !*((_WORD *)this + 91)
           && !*((_WORD *)this + 92)
           && *((unsigned __int16 *)this + 93) < 4 * *((unsigned __int16 *)this + 9) / 5 )
    {
      goto LABEL_39;
    }
    if ( *((_DWORD *)this + 131) == 63
      && !strcmp_0((const char *)this + 460, "DSC-F828")
      && (*((_DWORD *)this + 1336) & 0x10000) == 0 )
    {
      *((_DWORD *)this + 38261) = 0;
      *((_QWORD *)this + 19131) = 1065353216;
      *((_DWORD *)this + 38264) = 0;
      memset((char *)this + 186964, 0, 0x1000u);
      memset((char *)this + 191060, 0, 0x500u);
    }
    goto LABEL_44;
  }
  v6 = 0;
  v7 = DOUBLE_1_0;
LABEL_376:
  if ( *((_DWORD *)this + 132) )
  {
    *((_QWORD *)this + 95897) = LibRaw::write_ppm_tiff;
    v154 = *((_WORD *)this + 11);
    v155 = v154;
    if ( *((void (__fastcall **)(LibRaw *__hidden))this + 95898) == LibRaw::kodak_ycbcr_load_raw )
    {
      *((_WORD *)this + 10) += *((_WORD *)this + 10) & 1;
      v155 = v154 + (v154 & 1);
      *((_WORD *)this + 11) = v155;
      v154 = v155;
    }
    v156 = *((_DWORD *)this + 136);
    if ( v156 )
    {
      if ( *((_DWORD *)this + 1292)
        || *((float *)this + 1291) != 0.0
        || *((double *)this + 633) != v7
        || *((double *)this + 635) != v7 )
      {
        v157 = (char *)this + 381336;
        *((_WORD *)this + 190674) = 1;
        v6 = 1;
        if ( v156 >= 0x3E8 )
        {
          v155 = v154 & 0xFFFE;
          *((_WORD *)this + 11) = v154 & 0xFFFE;
          *((_WORD *)this + 10) &= ~1u;
        }
        goto LABEL_386;
      }
      v155 = v154;
    }
    v157 = (char *)this + 381336;
    *((_WORD *)this + 190674) = 0;
LABEL_386:
    *((_WORD *)this + 14) = (v6 + *((unsigned __int16 *)this + 10)) >> v6;
    *((_WORD *)this + 15) = (v6 + v155) >> v6;
    memmove((char *)this + 194224, (char *)this + 5392, 0x2DA98u);
    memmove((char *)this + 194024, (char *)this + 16, 0xB8u);
    memmove((char *)this + 193584, (char *)this + 200, 0x1B8u);
    memmove((char *)this + 194208, v157, 0x10u);
    *((_DWORD *)this + 1346) |= 4u;
    return 0;
  }
  return 4294967294LL;
}

```

## disassembly

```asm
0x18000adf0  mov     rax, rsp
0x18000adf3  push    rdi
0x18000adf4  push    r12
0x18000adf6  push    r13
0x18000adf8  push    r14
0x18000adfa  push    r15
0x18000adfc  sub     rsp, 0E0h
0x18000ae03  mov     [rsp+108h+var_C0], 0FFFFFFFFFFFFFFFEh
0x18000ae0c  mov     [rax+18h], rbx
0x18000ae10  mov     [rax+20h], rsi
0x18000ae14  movaps  xmmword ptr [rax-38h], xmm6
0x18000ae18  movaps  xmmword ptr [rax-48h], xmm7
0x18000ae1c  movaps  xmmword ptr [rax-58h], xmm8
0x18000ae21  movaps  xmmword ptr [rax-68h], xmm9
0x18000ae26  movaps  xmmword ptr [rax-78h], xmm10
0x18000ae2b  movaps  xmmword ptr [rax-88h], xmm11
0x18000ae33  movaps  [rsp+108h+var_98], xmm12
0x18000ae39  mov     rax, cs:__security_cookie
0x18000ae40  xor     rax, rsp
0x18000ae43  mov     [rsp+108h+var_A0], rax
0x18000ae48  mov     rbx, rdx
0x18000ae4b  mov     rdi, rcx
0x18000ae4e  mov     [rsp+108h+var_D8], rcx
0x18000ae53  test    rdx, rdx
0x18000ae56  jnz     short loc_18000AE62
0x18000ae58  mov     eax, 2
0x18000ae5d  jmp     loc_18000CF8E
0x18000ae62  mov     rax, [rdx]
0x18000ae65  mov     rcx, rbx
0x18000ae68  mov     rax, [rax+8]
0x18000ae6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae71  test    eax, eax
0x18000ae73  jz      loc_18000CF89
0x18000ae79  mov     rax, [rbx]
0x18000ae7c  mov     rcx, rbx
0x18000ae7f  mov     rax, [rax+28h]
0x18000ae83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae88  cmp     rax, 7FFFFFFFh
0x18000ae8e  jle     short loc_18000AEAB
0x18000ae90  mov     rax, [rbx]
0x18000ae93  mov     rcx, rbx
0x18000ae96  mov     rax, [rax+28h]
0x18000ae9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae9f  cmp     rax, 7FFFFFFFh
0x18000aea5  jg      loc_18000CF7B
0x18000aeab  mov     rcx, rdi; this
0x18000aeae  call    ?recycle@LibRaw@@QEAAXXZ; LibRaw::recycle(void)
0x18000aeb3  mov     rax, [rdi+0BB470h]
0x18000aeba  test    rax, rax
0x18000aebd  jz      short loc_18000AEE4
0x18000aebf  mov     rcx, rdi
0x18000aec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aec7  cmp     eax, 1
0x18000aeca  jnz     short loc_18000AEE4
0x18000aecc  xor     ebx, ebx
0x18000aece  mov     r12d, 1
0x18000aed4  movsd   xmm7, cs:__real@3ff0000000000000
0x18000aedc  xorps   xmm6, xmm6
0x18000aedf  jmp     loc_18000CDFA
0x18000aee4  mov     [rdi+5D158h], rbx
0x18000aeeb  or      dword ptr [rdi+1508h], 1
0x18000aef2  mov     rcx, rdi; this
0x18000aef5  call    ?identify@LibRaw@@IEAAXXZ; LibRaw::identify(void)
0x18000aefa  cmp     word ptr [rdi+5D1A6h], 0
0x18000af02  jnz     short loc_18000AF0D
0x18000af04  cmp     dword ptr [rdi+5D240h], 0
0x18000af0b  jz      short loc_18000AF4B
0x18000af0d  cmp     dword ptr [rdi+214h], 0
0x18000af14  jnz     short loc_18000AF4B
0x18000af16  mov     rax, [rdi+0BB4D0h]
0x18000af1d  lea     r13, ?unpacked_load_raw@LibRaw@@IEAAXXZ; LibRaw::unpacked_load_raw(void)
0x18000af24  cmp     rax, r13
0x18000af27  jz      short loc_18000AF52
0x18000af29  lea     rcx, ?unpacked_load_raw_FujiDBP@LibRaw@@IEAAXXZ; LibRaw::unpacked_load_raw_FujiDBP(void)
0x18000af30  cmp     rax, rcx
0x18000af33  jz      short loc_18000AF52
0x18000af35  lea     rcx, ?unpacked_load_raw_fuji_f700s20@LibRaw@@IEAAXXZ; LibRaw::unpacked_load_raw_fuji_f700s20(void)
0x18000af3c  cmp     rax, rcx
0x18000af3f  jz      short loc_18000AF52
0x18000af41  mov     eax, 0FFFFFFFEh
0x18000af46  jmp     loc_18000CF8E
0x18000af4b  lea     r13, ?unpacked_load_raw@LibRaw@@IEAAXXZ; LibRaw::unpacked_load_raw(void)
0x18000af52  mov     r8d, [rdi+2F2E0h]
0x18000af59  cmp     r8d, 8
0x18000af5d  jge     loc_18000B032
0x18000af63  mov     r9d, [rdi+2F2D0h]
0x18000af6a  test    r9d, r9d
0x18000af6d  jnz     short loc_18000AF80
0x18000af6f  mov     ecx, r8d
0x18000af72  cmp     qword ptr [rdi+5D180h], 0
0x18000af7a  jnz     short loc_18000AF80
0x18000af7c  xor     ebx, ebx
0x18000af7e  jmp     short loc_18000AFB9
0x18000af80  xor     ebx, ebx
0x18000af82  mov     edx, ebx
0x18000af84  mov     ecx, r8d
0x18000af87  test    r8d, r8d
0x18000af8a  jle     short loc_18000AFB9
0x18000af8c  mov     r10, [rdi+5D180h]
0x18000af93  lea     rax, [rdi+2F2F4h]
0x18000af9a  nop     word ptr [rax+rax+00h]
0x18000afa0  cmp     [rax+0Ch], r10
0x18000afa4  jnz     short loc_18000AFAF
0x18000afa6  cmp     [rax], r9d
0x18000afa9  jz      loc_18000B034
0x18000afaf  inc     edx
0x18000afb1  add     rax, 20h ; ' '
0x18000afb5  cmp     edx, ecx
0x18000afb7  jl      short loc_18000AFA0
0x18000afb9  movsxd  rdx, ecx
0x18000afbc  lea     rcx, [rdx+1798h]
0x18000afc3  shl     rcx, 5
0x18000afc7  mov     rax, [rdi+5D180h]
0x18000afce  mov     [rcx+rdi], rax
0x18000afd2  shl     rdx, 5
0x18000afd6  mov     eax, [rdi+2F2D0h]
0x18000afdc  mov     [rdx+rdi+2F2F4h], eax
0x18000afe3  mov     r14d, 0FFFFh
0x18000afe9  mov     [rdx+rdi+2F2F0h], r14w
0x18000aff2  mov     eax, [rdi+5D23Ch]
0x18000aff8  mov     [rdx+rdi+2F2E8h], eax
0x18000afff  mov     eax, [rdi+5D238h]
0x18000b005  mov     [rdx+rdi+2F2F8h], eax
0x18000b00c  movzx   eax, word ptr [rdi+2F2CCh]
0x18000b013  mov     [rdx+rdi+2F2ECh], ax
0x18000b01b  movzx   eax, word ptr [rdi+2F2CEh]
0x18000b022  mov     [rdx+rdi+2F2EEh], ax
0x18000b02a  inc     dword ptr [rdi+2F2E0h]
0x18000b030  jmp     short loc_18000B03A
0x18000b032  xor     ebx, ebx
0x18000b034  mov     r14d, 0FFFFh
0x18000b03a  mov     byte ptr [rdi+393h], 0
0x18000b041  mov     rax, [rdi+0BB478h]
0x18000b048  test    rax, rax
0x18000b04b  jz      short loc_18000B055
0x18000b04d  mov     rcx, rdi
0x18000b050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b055  cmp     dword ptr [rdi+214h], 0
0x18000b05c  jnz     loc_18000B16E
0x18000b062  mov     eax, [rdi+20Ch]
0x18000b068  cmp     eax, 12h
0x18000b06b  jnz     short loc_18000B0B4
0x18000b06d  lea     rdx, aS3pro; "S3Pro"
0x18000b074  lea     rcx, [rdi+1CCh]; Str1
0x18000b07b  call    strcmp_0
0x18000b080  test    eax, eax
0x18000b082  jz      short loc_18000B0EF
0x18000b084  lea     rdx, aS5pro; "S5Pro"
0x18000b08b  lea     rcx, [rdi+1CCh]; Str1
0x18000b092  call    strcmp_0
0x18000b097  test    eax, eax
0x18000b099  jz      short loc_18000B0EF
0x18000b09b  lea     rdx, aS2pro; "S2Pro"
0x18000b0a2  lea     rcx, [rdi+1CCh]; Str1
0x18000b0a9  call    strcmp_0
0x18000b0ae  test    eax, eax
0x18000b0b0  jnz     short loc_18000B103
0x18000b0b2  jmp     short loc_18000B0EF
0x18000b0b4  cmp     eax, 8
0x18000b0b7  jnz     short loc_18000B103
0x18000b0b9  cmp     word ptr [rdi+0B6h], 0
0x18000b0c1  jnz     short loc_18000B103
0x18000b0c3  cmp     word ptr [rdi+0B8h], 0
0x18000b0cb  jnz     short loc_18000B103
0x18000b0cd  movzx   ecx, word ptr [rdi+12h]
0x18000b0d1  shl     ecx, 2
0x18000b0d4  mov     eax, 66666667h
0x18000b0d9  imul    ecx
0x18000b0db  sar     edx, 1
0x18000b0dd  mov     eax, edx
0x18000b0df  shr     eax, 1Fh
0x18000b0e2  add     edx, eax
0x18000b0e4  movzx   eax, word ptr [rdi+0BAh]
0x18000b0eb  cmp     eax, edx
0x18000b0ed  jge     short loc_18000B103
0x18000b0ef  mov     dword ptr [rdi+0BAh], 0
0x18000b0f9  mov     dword ptr [rdi+0B6h], 0FFFFFFFFh
0x18000b103  cmp     dword ptr [rdi+20Ch], 3Fh ; '?'
0x18000b10a  jnz     short loc_18000B16E
0x18000b10c  lea     rcx, [rdi+1CCh]; Str1
0x18000b113  lea     rdx, aDscF828; "DSC-F828"
0x18000b11a  call    strcmp_0
0x18000b11f  test    eax, eax
0x18000b121  jnz     short loc_18000B16E
0x18000b123  test    dword ptr [rdi+14E0h], 10000h
0x18000b12d  jnz     short loc_18000B16E
0x18000b12f  mov     [rdi+255D4h], ebx
0x18000b135  mov     qword ptr [rdi+255D8h], 3F800000h
0x18000b140  mov     [rdi+255E0h], ebx
0x18000b146  lea     rcx, [rdi+2DA54h]; void *
0x18000b14d  xor     edx, edx; Val
0x18000b14f  mov     r8d, 1000h; Size
0x18000b155  call    memset
0x18000b15a  lea     rcx, [rdi+2EA54h]; void *
0x18000b161  xor     edx, edx; Val
0x18000b163  mov     r8d, 500h; Size
0x18000b169  call    memset
0x18000b16e  lea     rax, ?nikon_load_raw@LibRaw@@IEAAXXZ; LibRaw::nikon_load_raw(void)
0x18000b175  cmp     [rdi+0BB4D0h], rax
0x18000b17c  jnz     short loc_18000B186
0x18000b17e  mov     rcx, rdi; this
0x18000b181  call    ?nikon_read_curve@LibRaw@@IEAAXXZ; LibRaw::nikon_read_curve(void)
0x18000b186  lea     rax, ?lossless_jpeg_load_raw@LibRaw@@IEAAXXZ; LibRaw::lossless_jpeg_load_raw(void)
0x18000b18d  cmp     [rdi+0BB4D0h], rax
0x18000b194  jnz     loc_18000B255
0x18000b19a  cmp     word ptr [rdi+7EEh], 0
0x18000b1a2  jz      loc_18000B255
0x18000b1a8  cmp     dword ptr [rdi+20Ch], 1Dh
0x18000b1af  jnz     loc_18000B255
0x18000b1b5  mov     r8d, 9; MaxCount
0x18000b1bb  lea     rdx, aEosD2000; "EOS D2000"
0x18000b1c2  lea     rcx, [rdi+10Ch]; String1
0x18000b1c9  call    _strnicmp_0
0x18000b1ce  test    eax, eax
0x18000b1d0  jz      short loc_18000B1EF
0x18000b1d2  mov     r8d, 9; MaxCount
0x18000b1d8  lea     rdx, aEosD6000; "EOS D6000"
0x18000b1df  lea     rcx, [rdi+10Ch]; String1
0x18000b1e6  call    _strnicmp_0
0x18000b1eb  test    eax, eax
0x18000b1ed  jnz     short loc_18000B255
0x18000b1ef  mov     [rdi+25530h], ebx
0x18000b1f5  mov     dword ptr [rdi+25538h], 1195h
0x18000b1ff  lea     rcx, [rdi+21510h]; void *
0x18000b206  xor     edx, edx; Val
0x18000b208  mov     r8d, 4020h; Size
0x18000b20e  call    memset
0x18000b213  xorps   xmm0, xmm0
0x18000b216  movups  xmmword ptr [rdi+34h], xmm0
0x18000b21a  movups  xmmword ptr [rdi+44h], xmm0
0x18000b21e  movups  xmmword ptr [rdi+54h], xmm0
0x18000b222  movups  xmmword ptr [rdi+64h], xmm0
0x18000b226  movups  xmmword ptr [rdi+74h], xmm0
0x18000b22a  movups  xmmword ptr [rdi+84h], xmm0
0x18000b231  movups  xmmword ptr [rdi+94h], xmm0
0x18000b238  movups  xmmword ptr [rdi+0A4h], xmm0
0x18000b23f  mov     r12d, 1
0x18000b245  mov     [rdi+40h], r12d
0x18000b249  or      dword ptr [rdi+5D260h], 200h
0x18000b253  jmp     short loc_18000B25B
0x18000b255  mov     r12d, 1
0x18000b25b  lea     rax, ?panasonic_load_raw@LibRaw@@IEAAXXZ; LibRaw::panasonic_load_raw(void)
0x18000b262  cmp     [rdi+0BB4D0h], rax
0x18000b269  jnz     loc_18000B3FE
0x18000b26f  mov     r9d, [rdi+5D294h]
0x18000b276  lea     eax, [r9-6]
0x18000b27a  cmp     eax, 1
0x18000b27d  ja      loc_18000B3FE
0x18000b283  mov     eax, [rdi+5D188h]
0x18000b289  mov     [rdi+21510h], eax
0x18000b28f  mov     ecx, [rdi+5D18Ch]
0x18000b295  mov     [rdi+21514h], ecx
0x18000b29b  mov     eax, [rdi+5D190h]
0x18000b2a1  mov     [rdi+21518h], eax
0x18000b2a7  mov     [rdi+2151Ch], ecx
0x18000b2ad  mov     qword ptr [rdi+21520h], 0
0x18000b2b8  mov     [rdi+25530h], ebx
0x18000b2be  mov     edx, [rdi+25544h]
0x18000b2c4  mov     r8d, [rdi+25540h]
0x18000b2cb  mov     ecx, [rdi+2553Ch]
0x18000b2d1  mov     eax, r8d
0x18000b2d4  cmp     r8d, edx
0x18000b2d7  cmovle  eax, edx
0x18000b2da  cmp     ecx, eax
0x18000b2dc  jg      short loc_18000B2E7
0x18000b2de  mov     ecx, edx
0x18000b2e0  cmp     r8d, edx
0x18000b2e3  cmovg   ecx, r8d
0x18000b2e7  mov     [rdi+25538h], ecx
0x18000b2ed  cmp     r9d, 6
0x18000b2f1  jnz     loc_18000B3AE
0x18000b2f7  movzx   esi, word ptr [rdi+12h]
0x18000b2fb  mov     eax, 0BA2E8BA3h
0x18000b300  mul     esi
0x18000b302  mov     r15d, edx
0x18000b305  shr     r15d, 3
0x18000b309  mov     eax, 24924925h
0x18000b30e  mul     esi
0x18000b310  sub     esi, edx
0x18000b312  shr     esi, 1
0x18000b314  add     esi, edx
0x18000b316  shr     esi, 3
0x18000b319  mov     r10d, [rdi+5D228h]
0x18000b320  test    r10, r10
0x18000b323  jnz     short loc_18000B342
0x18000b325  mov     rcx, [rdi+5D158h]
0x18000b32c  mov     rax, [rcx]
0x18000b32f  mov     rax, [rax+28h]
0x18000b333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b338  mov     r10, rax
0x18000b33b  sub     r10, [rdi+5D200h]
0x18000b342  movzx   r9d, word ptr [rdi+12h]
0x18000b347  mov     eax, 0BA2E8BA3h
0x18000b34c  mul     r9d
0x18000b34f  shr     edx, 3
0x18000b352  imul    r8d, edx, 0Bh
0x18000b356  cmp     r9d, r8d
0x18000b359  jnz     short loc_18000B36F
0x18000b35b  movzx   edx, word ptr [rdi+10h]
0x18000b35f  shl     r15d, 4
  ... truncated ...
```
