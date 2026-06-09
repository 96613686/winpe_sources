# ReplaceSpecialSink

- ea: `0x180094b90`
- end: `0x180095966`
- name: `ReplaceSpecialSink`
- size: `3542`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180091ef0`

## callees

- `0x180003180`
- `0x180054440`
- `0x180087c20`
- `0x180087ce0`
- `0x180087f90`
- `0x18008f4f0`
- `0x18008fd30`
- `0x180091d90`
- `0x180091f80`
- `0x180094b90`

## pseudocode

```c
__int64 __fastcall ReplaceSpecialSink(_DWORD *a1, __int128 *a2, __int64 a3, __int64 a4, __int64 a5)
{
  int v5; // eax
  int v6; // r12d
  __int64 v7; // rdi
  __int64 v8; // r14
  __int64 v9; // r15
  __int128 *v10; // rsi
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 result; // rax
  signed int v15; // ebx
  int v16; // r13d
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int64 v19; // r15
  int v20; // r14d
  bool v21; // zf
  __int64 v22; // rax
  __int16 *v23; // r9
  char *v24; // r10
  char *v25; // r11
  __int16 *v26; // rsi
  char *v27; // rdi
  __int16 *v28; // r13
  char *v29; // rdx
  __int64 v30; // rcx
  __m128i inserted; // xmm2
  __int64 v32; // rcx
  __m128i v33; // xmm3
  __m128i v34; // xmm1
  __m128i v35; // xmm3
  __m128i v36; // xmm1
  __m128i v37; // xmm3
  __m128i v38; // xmm1
  __m128i v39; // xmm3
  __m128i v40; // xmm1
  __m128i v41; // xmm3
  __m128i v42; // xmm1
  __m128i v43; // xmm3
  __m128i v44; // xmm1
  __m128i v45; // xmm3
  __m128i v46; // xmm1
  __m128i v47; // xmm3
  int v48; // eax
  int v49; // ecx
  __m128i si128; // xmm14
  __m128i v51; // xmm15
  __int64 v52; // rax
  char *v53; // rdx
  char *v54; // r8
  __int16 *v55; // r9
  char *v56; // r10
  __int16 *v57; // r11
  char *v58; // rdi
  __int16 *v59; // rbx
  __int64 v60; // r13
  __int64 v61; // rsi
  __m128i v62; // xmm12
  __m128i v63; // xmm12
  __m128i v64; // xmm5
  __m128i v65; // xmm5
  __m128i v66; // xmm6
  __m128i v67; // xmm6
  __m128i v68; // xmm7
  __m128i v69; // xmm7
  __m128i v70; // xmm8
  __m128i v71; // xmm9
  __m128i v72; // xmm10
  __m128i v73; // xmm11
  __m128i v74; // xmm8
  __m128i v75; // xmm9
  __m128i v76; // xmm10
  __m128i v77; // xmm11
  __m128i v78; // xmm13
  __m128i v79; // xmm4
  __m128i v80; // xmm3
  __m128i v81; // xmm2
  __m128i v82; // xmm2
  __int64 v83; // rax
  __int16 *v84; // r9
  char *v85; // r10
  char *v86; // r11
  __int16 *v87; // rsi
  char *v88; // r13
  char *v89; // rdx
  __int64 v90; // rcx
  __m128i v91; // xmm2
  __int64 v92; // rcx
  __m128i v93; // xmm3
  __m128i v94; // xmm1
  __m128i v95; // xmm3
  __m128i v96; // xmm1
  __m128i v97; // xmm3
  __m128i v98; // xmm1
  __m128i v99; // xmm3
  __m128i v100; // xmm1
  __m128i v101; // xmm3
  __m128i v102; // xmm1
  __m128i v103; // xmm3
  __m128i v104; // xmm1
  __m128i v105; // xmm3
  __m128i v106; // xmm1
  __m128i v107; // xmm3
  int v108; // eax
  int v109; // ecx
  int v110; // r8d
  bool v111; // cc
  __int64 v112; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v113; // [rsp+48h] [rbp-B8h] BYREF
  char v114; // [rsp+4Ch] [rbp-B4h]
  __int16 *v115; // [rsp+50h] [rbp-B0h]
  signed int v116; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v117; // [rsp+60h] [rbp-A0h]
  __int128 *v118; // [rsp+68h] [rbp-98h]
  char *v119; // [rsp+70h] [rbp-90h]
  char *v120; // [rsp+78h] [rbp-88h]
  __int16 *v121; // [rsp+80h] [rbp-80h]
  char *v122; // [rsp+88h] [rbp-78h]
  char *v123; // [rsp+90h] [rbp-70h]
  char *v124; // [rsp+98h] [rbp-68h]
  char *v125; // [rsp+A0h] [rbp-60h]
  __int64 v126; // [rsp+A8h] [rbp-58h]
  __int64 v127; // [rsp+B0h] [rbp-50h]
  union __m128i v128; // [rsp+C0h] [rbp-40h] BYREF
  union __m128i v129; // [rsp+D0h] [rbp-30h] BYREF
  union __m128i v130; // [rsp+E0h] [rbp-20h] BYREF
  union __m128i v131; // [rsp+F0h] [rbp-10h] BYREF
  union __m128i v132; // [rsp+100h] [rbp+0h] BYREF
  union __m128i v133; // [rsp+110h] [rbp+10h] BYREF
  union __m128i v134; // [rsp+120h] [rbp+20h] BYREF
  union __m128i v135; // [rsp+130h] [rbp+30h] BYREF
  _OWORD v136[2]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v137; // [rsp+160h] [rbp+60h] BYREF
  __int128 v138; // [rsp+170h] [rbp+70h] BYREF
  __int128 v139; // [rsp+180h] [rbp+80h]
  __int128 v140; // [rsp+190h] [rbp+90h]
  __int128 v141; // [rsp+1A0h] [rbp+A0h]

  v5 = a1[1];
  v6 = 0;
  v7 = a5;
  v8 = a4;
  v126 = a4;
  v9 = a3;
  v127 = a3;
  v10 = a2;
  v118 = a2;
  v117 = a5;
  v112 = 0;
  v116 = 0;
  Binary::Definition::GenerateAsyncServer((unsigned int)&v113, 5, 2, 2, v5 + 3);
  v12 = 0;
  if ( v114 )
    v12 = v113;
  Binary::Policy::MixedRelation<Binary::Policy::SmoothArticle,2>(&v116, v12);
  Binary::Definition::GenerateAsyncServer((unsigned int)&v113, 5, 2, 2, *a1 + 3);
  v13 = 0;
  if ( v114 )
    v13 = v113;
  result = Binary::Policy::ReviseCommonBinary<Binary::Policy::NewMode,2>(&v112, v13);
  if ( *(int *)(a5 + 12) < 9 )
  {
    v137 = *(_OWORD *)a1;
    return Binary::Policy::MarkQuickestList<Binary::Policy::SmoothArticle,2>(
             (unsigned int)&v137,
             (_DWORD)v10,
             v9,
             v8,
             a5);
  }
  v113 = 0;
  if ( *(int *)(a5 + 8) > 0 )
  {
    v15 = v116;
    v16 = v112;
    do
    {
      v17 = v10[1];
      v138 = 0;
      v139 = 0;
      v140 = 0;
      v141 = 0;
      v18 = *v10;
      v136[1] = v17;
      v136[0] = v18;
      Binary::Policy::HelpSynchronousQuantity<Binary::Policy::SmoothArticle,2>(&v138, v9, v136);
      v137 = 0;
      Binary::Policy::CompleteOperation::TargetDigitalRegion(v8, &v137, v7);
      v19 = 0;
      v20 = 0;
      if ( (unsigned int)v15 > 1 )
      {
        v15 &= 0x80000001;
        LODWORD(v115) = v15;
        if ( v15 < 0 )
        {
          v15 = (((_BYTE)v15 - 1) | 0xFFFFFFFE) + 1;
          LODWORD(v115) = v15;
        }
        v21 = v15 == 0;
        if ( v15 >= 0 )
          goto LABEL_15;
        v15 += 2;
      }
      LODWORD(v115) = v15;
      v21 = v15 == 0;
LABEL_15:
      if ( !v21 )
      {
        v22 = (__int64)v16 << 6;
        v23 = (__int16 *)((char *)&word_1800DE702 + v22);
        v24 = &Binary::Policy::SmoothArticle::OddOperation[v22];
        v25 = &byte_1800DE704[v22];
        v26 = (__int16 *)((char *)&word_1800DE706 + v22);
        v27 = &byte_1800DE708[v22];
        v28 = (__int16 *)((char *)&word_1800DE70A + v22);
        v29 = &byte_1800DE70C[v22];
        v119 = &byte_1800DE70C[v22];
        v115 = (__int16 *)(0x180000000LL + v22 + 911118);
        do
        {
          v30 = (__int64)v15 << 6;
          inserted = _mm_insert_epi16(
                       _mm_insert_epi16(
                         _mm_insert_epi16(
                           _mm_insert_epi16(
                             _mm_insert_epi16(
                               _mm_insert_epi16(
                                 _mm_insert_epi16(
                                   _mm_cvtsi32_si128(*(unsigned __int16 *)&Binary::Policy::SmoothArticle::OddOperation[v30]),
                                   *(unsigned __int16 *)((char *)&word_1800DE702 + v30),
                                   1),
                                 *(unsigned __int16 *)&byte_1800DE704[v30],
                                 2),
                               *(unsigned __int16 *)((char *)&word_1800DE706 + v30),
                               3),
                             *(unsigned __int16 *)&byte_1800DE708[v30],
                             4),
                           *(unsigned __int16 *)((char *)&word_1800DE70A + v30),
                           5),
                         *(unsigned __int16 *)&byte_1800DE70C[v30],
                         6),
                       *(unsigned __int16 *)((char *)&word_1800DE70E + v30),
                       7);
          v32 = 2LL * v20;
          v33 = _mm_cvtsi32_si128(*(__int16 *)v24);
          v34 = _mm_cvtsi32_si128(*v23);
          v35 = _mm_add_epi16(
                  _mm_mullo_epi16(
                    _mm_shuffle_epi32(_mm_unpacklo_epi16(v33, v33), 0),
                    _mm_loadu_si128((const __m128i *)(v138 + v32))),
                  _mm_mullo_epi16(
                    _mm_shuffle_epi32(_mm_unpacklo_epi16(v34, v34), 0),
                    _mm_loadu_si128((const __m128i *)(*((_QWORD *)&v138 + 1) + v32))));
          v36 = _mm_cvtsi32_si128(*(__int16 *)v25);
          v37 = _mm_add_epi16(
                  v35,
                  _mm_mullo_epi16(
                    _mm_shuffle_epi32(_mm_unpacklo_epi16(v36, v36), 0),
                    _mm_loadu_si128((const __m128i *)(v139 + v32))));
          v38 = _mm_cvtsi32_si128(*v26);
          v39 = _mm_add_epi16(
                  v37,
                  _mm_mullo_epi16(
                    _mm_shuffle_epi32(_mm_unpacklo_epi16(v38, v38), 0),
                    _mm_loadu_si128((const __m128i *)(*((_QWORD *)&v139 + 1) + v32))));
          v40 = _mm_cvtsi32_si128(*(__int16 *)v27);
          v41 = _mm_add_epi16(
                  v39,
                  _mm_mullo_epi16(
                    _mm_shuffle_epi32(_mm_unpacklo_epi16(v40, v40), 0),
                    _mm_loadu_si128((const __m128i *)(v140 + v32))));
          v42 = _mm_cvtsi32_si128(*v28);
          v43 = _mm_add_epi16(
                  v41,
                  _mm_mullo_epi16(
                    _mm_shuffle_epi32(_mm_unpacklo_epi16(v42, v42), 0),
                    _mm_loadu_si128((const __m128i *)(*((_QWORD *)&v140 + 1) + v32))));
          v44 = _mm_cvtsi32_si128(*(__int16 *)v29);
          v45 = _mm_add_epi16(
                  v43,
                  _mm_mullo_epi16(
                    _mm_shuffle_epi32(_mm_unpacklo_epi16(v44, v44), 0),
                    _mm_loadu_si128((const __m128i *)(v141 + v32))));
          v46 = _mm_cvtsi32_si128(*v115);
          v47 = _mm_mullo_epi16(
                  _mm_srli_epi16(
                    _mm_add_epi16(
                      v45,
                      _mm_mullo_epi16(
                        _mm_shuffle_epi32(_mm_unpacklo_epi16(v46, v46), 0),
                        _mm_loadu_si128((const __m128i *)(*((_QWORD *)&v141 + 1) + v32)))),
                    6u),
                  inserted);
          *(_BYTE *)(*((_QWORD *)&v137 + 1) + v19) = (unsigned __int16)(_mm_extract_epi16(v47, 7)
                                                                      + _mm_cvtsi128_si32(_mm_srli_si128(v47, 12))
                                                                      + _mm_extract_epi16(v47, 5)
                                                                      + _mm_cvtsi128_si32(_mm_srli_si128(v47, 8))
                                                                      + _mm_extract_epi16(v47, 3)
                                                                      + _mm_cvtsi128_si32(_mm_srli_si128(v47, 4))
                                                                      + _mm_extract_epi16(v47, 1)
                                                                      + _mm_cvtsi128_si32(v47)) >> 8;
          v20 += Binary::Policy::SmoothArticle::GlobalCase[v15];
          v48 = v15 + 1;
          v29 = v119;
          v15 = 0;
          if ( v48 < 2 )
            v15 = v48;
          ++v6;
          ++v19;
        }
        while ( v15 );
        v10 = v118;
        v15 = 0;
        v16 = v112;
        v7 = v117;
        LODWORD(v115) = 0;
      }
      v49 = *(_DWORD *)(v7 + 12);
      if ( v6 < v49 - 7 )
      {
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        v51 = _mm_load_si128((const __m128i *)&_xmm);
        v52 = (__int64)v16 << 6;
        v53 = &Binary::Policy::SmoothArticle::OddOperation[v52];
        v54 = &byte_1800DE704[v52];
        v123 = &Binary::Policy::SmoothArticle::OddOperation[v52];
        v124 = &byte_1800DE704[v52];
        v55 = (__int16 *)((char *)&word_1800DE706 + v52);
        v56 = &byte_1800DE708[v52];
        v125 = (char *)&word_1800DE706 + v52;
        v120 = &byte_1800DE708[v52];
        v57 = (__int16 *)((char *)&word_1800DE70A + v52);
        v58 = &byte_1800DE70C[v52];
        v121 = (__int16 *)((char *)&word_1800DE70A + v52);
        v59 = (__int16 *)((char *)&word_1800DE702 + v52);
        v122 = &byte_1800DE70C[v52];
        v60 = 2LL * v20 + 20;
        v61 = v117;
        v119 = (char *)(0x180000000LL + v52 + 911118);
        do
        {
          v62 = _mm_cvtsi32_si128(*v59);
          v63 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v62, v62), 0);
          v64 = _mm_cvtsi32_si128(*(__int16 *)v53);
          v65 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v64, v64), 0);
          v66 = _mm_cvtsi32_si128(*(__int16 *)v54);
          v67 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v66, v66), 0);
          v68 = _mm_cvtsi32_si128(*v55);
          v69 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v68, v68), 0);
          v70 = _mm_cvtsi32_si128(*(__int16 *)v56);
          v71 = _mm_cvtsi32_si128(*v57);
          v72 = _mm_cvtsi32_si128(*(__int16 *)v58);
          v73 = _mm_cvtsi32_si128(*(__int16 *)v119);
          v74 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v70, v70), 0);
          v75 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v71, v71), 0);
          v76 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v72, v72), 0);
          v77 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v73, v73), 0);
          v78 = _mm_srli_epi16(
                  _mm_add_epi16(
                    _mm_add_epi16(
                      _mm_add_epi16(
                        _mm_add_epi16(
                          _mm_add_epi16(
                            _mm_add_epi16(
                              _mm_add_epi16(
                                _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v138 + v60 - 20)), v65),
                                _mm_mullo_epi16(
                                  _mm_loadu_si128((const __m128i *)(*((_QWORD *)&v138 + 1) + v60 - 20)),
                                  v63)),
                              _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v139 + v60 - 20)), v67)),
                            _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(*((_QWORD *)&v139 + 1) + v60 - 20)), v69)),
                          _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v140 + v60 - 20)), v74)),
                        _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(*((_QWORD *)&v140 + 1) + v60 - 20)), v75)),
                      _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v141 + v60 - 20)), v76)),
                    _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(*((_QWORD *)&v141 + 1) + v60 - 20)), v77)),
                  6u);
          v79 = _mm_srli_epi16(
                  _mm_add_epi16(
                    _mm_add_epi16(
                      _mm_add_epi16(
                        _mm_add_epi16(
                          _mm_add_epi16(
                            _mm_add_epi16(
                              _mm_add_epi16(
                                _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v138 + v60 - 10)), v65),
                                _mm_mullo_epi16(
                                  _mm_loadu_si128((const __m128i *)(*((_QWORD *)&v138 + 1) + v60 - 10)),
                                  v63)),
                              _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v139 + v60 - 10)), v67)),
                            _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(*((_QWORD *)&v139 + 1) + v60 - 10)), v69)),
                          _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v140 + v60 - 10)), v74)),
                        _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(*((_QWORD *)&v140 + 1) + v60 - 10)), v75)),
                      _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v141 + v60 - 10)), v76)),
                    _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(*((_QWORD *)&v141 + 1) + v60 - 10)), v77)),
                  6u);
          v80 = _mm_srli_epi16(
                  _mm_add_epi16(
                    _mm_add_epi16(
                      _mm_add_epi16(
                        _mm_add_epi16(
                          _mm_add_epi16(
                            _mm_add_epi16(
                              _mm_add_epi16(
                                _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(*((_QWORD *)&v138 + 1) + v60)), v63),
                                _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v138 + v60)), v65)),
                              _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v139 + v60)), v67)),
                            _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(*((_QWORD *)&v139 + 1) + v60)), v69)),
                          _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v140 + v60)), v74)),
                        _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(*((_QWORD *)&v140 + 1) + v60)), v75)),
                      _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v141 + v60)), v76)),
                    _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(*((_QWORD *)&v141 + 1) + v60)), v77)),
                  6u);
          v81 = _mm_srli_epi16(
                  _mm_add_epi16(
                    _mm_add_epi16(
                      _mm_add_epi16(
                        _mm_add_epi16(
                          _mm_add_epi16(
                            _mm_add_epi16(
                              _mm_add_epi16(
                                _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v138 + v60 + 16)), v65),
                                _mm_mullo_epi16(
                                  _mm_loadu_si128((const __m128i *)(*((_QWORD *)&v138 + 1) + v60 + 16)),
                                  v63)),
                              _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v139 + v60 + 16)), v67)),
                            _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(*((_QWORD *)&v139 + 1) + v60 + 16)), v69)),
                          _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v140 + v60 + 16)), v74)),
                        _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(*((_QWORD *)&v140 + 1) + v60 + 16)), v75)),
                      _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v141 + v60 + 16)), v76)),
                    _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(*((_QWORD *)&v141 + 1) + v60 + 16)), v77)),
                  6u);
          v128 = _mm_mullo_epi16(si128, v78);
          v129 = _mm_mullo_epi16(_mm_or_si128(_mm_slli_si128(v79, 4), _mm_srli_si128(v78, 6)), v51);
          v130 = _mm_mullo_epi16(si128, v79);
          v131 = _mm_mullo_epi16(_mm_or_si128(_mm_slli_si128(v80, 4), _mm_srli_si128(v79, 6)), v51);
          v132 = _mm_mullo_epi16(si128, v80);
          v133 = _mm_mullo_epi16(_mm_or_si128(_mm_slli_si128(v81, 10), _mm_srli_si128(v80, 6)), v51);
          v134 = _mm_mullo_epi16(_mm_or_si128(_mm_slli_si128(v81, 6), _mm_srli_si128(v80, 10)), si128);
          v135 = _mm_mullo_epi16(v51, v81);
          TreatCoordinatedPackage(&v128, &v129, &v130, &v131, &v132, &v133, &v134, &v135);
          v60 += 40;
          v6 += 8;
          v20 += 20;
          v82 = _mm_srli_epi16(
                  _mm_add_epi16(
                    _mm_add_epi16(
                      _mm_add_epi16(_mm_load_si128(&v135), v134),
                      _mm_add_epi16(_mm_load_si128(&v133), v132)),
                    _mm_add_epi16(
                      _mm_add_epi16(_mm_load_si128(&v131), v130),
                      _mm_add_epi16(_mm_load_si128(&v129), v128))),
                  8u);
          *(_BYTE *)(*((_QWORD *)&v137 + 1) + v19) = _mm_cvtsi128_si32(v82);
          *(_BYTE *)(*((_QWORD *)&v137 + 1) + v19 + 1) = _mm_cvtsi128_si32(_mm_srli_si128(v82, 2));
          *(_BYTE *)(*((_QWORD *)&v137 + 1) + v19 + 2) = _mm_cvtsi128_si32(_mm_srli_si128(v82, 4));
          *(_BYTE *)(*((_QWORD *)&v137 + 1) + v19 + 3) = _mm_cvtsi128_si32(_mm_srli_si128(v82, 6));
          *(_BYTE *)(*((_QWORD *)&v137 + 1) + v19 + 4) = _mm_cvtsi128_si32(_mm_srli_si128(v82, 8));
          *(_BYTE *)(*((_QWORD *)&v137 + 1) + v19 + 5) = _mm_cvtsi128_si32(_mm_srli_si128(v82, 10));
          *(_BYTE *)(*((_QWORD *)&v137 + 1) + v19 + 6) = _mm_cvtsi128_si32(_mm_srli_si128(v82, 12));
          *(_BYTE *)(*((_QWORD *)&v137 + 1) + v19 + 7) = _mm_cvtsi128_si32(_mm_srli_si128(v82, 14));
          v19 += 8;
          v49 = *(_DWORD *)(v61 + 12);
          v53 = v123;
          v54 = v124;
          v55 = (__int16 *)v125;
          v56 = v120;
          v57 = v121;
          v58 = v122;
        }
        while ( v6 < v49 - 7 );
        v15 = (int)v115;
        v10 = v118;
        v16 = v112;
        v7 = v117;
      }
      if ( v6 < v49 )
      {
        v83 = (__int64)v16 << 6;
        v84 = (__int16 *)((char *)&word_1800DE702 + v83);
        v85 = &Binary::Policy::SmoothArticle::OddOperation[v83];
        v86 = &byte_1800DE704[v83];
        v87 = (__int16 *)((char *)&word_1800DE706 + v83);
        v88 = &byte_1800DE708[v83];
        v89 = (char *)&word_1800DE70A + v83;
        v120 = (char *)&word_1800DE70A + v83;
        v122 = &byte_1800DE70C[v83];
        v121 = (__int16 *)(0x180000000LL + v83 + 911118);
        do
        {
          v90 = (__int64)v15 << 6;
          v91 = _mm_insert_epi16(
                  _mm_insert_epi16(
                    _mm_insert_epi16(
                      _mm_insert_epi16(
                        _mm_insert_epi16(
                          _mm_insert_epi16(
                            _mm_insert_epi16(
                              _mm_cvtsi32_si128(*(unsigned __int16 *)&Binary::Policy::SmoothArticle::OddOperation[v90]),
                              *(unsigned __int16 *)((char *)&word_1800DE702 + v90),
                              1),
                            *(unsigned __int16 *)&byte_1800DE704[v90],
                            2),
                          *(unsigned __int16 *)((char *)&word_1800DE706 + v90),
                          3),
                        *(unsigned __int16 *)&byte_1800DE708[v90],
                        4),
                      *(unsigned __int16 *)((char *)&word_1800DE70A + v90),
                      5),
                    *(unsigned __int16 *)&byte_1800DE70C[v90],
                    6),
                  *(unsigned __int16 *)((char *)&word_1800DE70E + v90),
                  7);
          v92 = 2LL * v20;
          v93 = _mm_cvtsi32_si128(*(__int16 *)v85);
          v94 = _mm_cvtsi32_si128(*v84);
          v95 = _mm_add_epi16(
                  _mm_mullo_epi16(
                    _mm_shuffle_epi32(_mm_unpacklo_epi16(v93, v93), 0),
                    _mm_loadu_si128((const __m128i *)(v92 + v138))),
                  _mm_mullo_epi16(
                    _mm_shuffle_epi32(_mm_unpacklo_epi16(v94, v94), 0),
                    _mm_loadu_si128((const __m128i *)(*((_QWORD *)&v138 + 1) + v92))));
          v96 = _mm_cvtsi32_si128(*(__int16 *)v86);
          v97 = _mm_add_epi16(
                  v95,
                  _mm_mullo_epi16(
                    _mm_shuffle_epi32(_mm_unpacklo_epi16(v96, v96), 0),
                    _mm_loadu_si128((const __m128i *)(v92 + v139))));
          v98 = _mm_cvtsi32_si128(*v87);
          v99 = _mm_add_epi16(
                  v97,
                  _mm_mullo_epi16(
                    _mm_shuffle_epi32(_mm_unpacklo_epi16(v98, v98), 0),
                    _mm_loadu_si128((const __m128i *)(v92 + *((_QWORD *)&v139 + 1)))));
          v100 = _mm_cvtsi32_si128(*(__int16 *)v88);
          v101 = _mm_add_epi16(
                   v99,
                   _mm_mullo_epi16(
                     _mm_shuffle_epi32(_mm_unpacklo_epi16(v100, v100), 0),
                     _mm_loadu_si128((const __m128i *)(v92 + v140))));
          v102 = _mm_cvtsi32_si128(*(__int16 *)v89);
          v103 = _mm_add_epi16(
                   v101,
                   _mm_mullo_epi16(
                     _mm_shuffle_epi32(_mm_unpacklo_epi16(v102, v102), 0),
                     _mm_loadu_si128((const __m128i *)(v92 + *((_QWORD *)&v140 + 1)))));
          v104 = _mm_cvtsi32_si128(*(__int16 *)v122);
          v105 = _mm_add_epi16(
                   v103,
                   _mm_mullo_epi16(
                     _mm_shuffle_epi32(_mm_unpacklo_epi16(v104, v104), 0),
                     _mm_loadu_si128((const __m128i *)(v92 + v141))));
          v106 = _mm_cvtsi32_si128(*v121);
          ++v19;
          v107 = _mm_mullo_epi16(
                   _mm_srli_epi16(
                     _mm_add_epi16(
                       v105,
                       _mm_mullo_epi16(
                         _mm_shuffle_epi32(_mm_unpacklo_epi16(v106, v106), 0),
                         _mm_loadu_si128((const __m128i *)(v92 + *((_QWORD *)&v141 + 1))))),
                     6u),
                   v91);
          ++v6;
          *(_BYTE *)(*((_QWORD *)&v137 + 1) + v19 - 1) = (unsigned __int16)(_mm_extract_epi16(v107, 7)
                                                                          + _mm_cvtsi128_si32(_mm_srli_si128(v107, 12))
                                                                          + _mm_extract_epi16(v107, 5)
                                                                          + _mm_cvtsi128_si32(_mm_srli_si128(v107, 8))
                                                                          + _mm_extract_epi16(v107, 3)
                                                                          + _mm_cvtsi128_si32(_mm_srli_si128(v107, 4))
                                                                          + _mm_extract_epi16(v107, 1)
                                                                          + _mm_cvtsi128_si32(v107)) >> 8;
          v20 += Binary::Policy::SmoothArticle::GlobalCase[v15];
          v108 = v15 + 1;
          v89 = v120;
          v15 = 0;
          if ( v108 < 2 )
            v15 = v108;
        }
        while ( v6 < *(_DWORD *)(v7 + 12) );
        v10 = v118;
        v16 = v112;
      }
      v8 = v126;
      Binary::Policy::CompleteOperation::MoveVirtualAddition(v126, &v137);
      v6 = 0;
      result = v16;
      v109 = 0;
      if ( Binary::Policy::SmoothArticle::GlobalCase[v16] > 0 )
      {
        v110 = *((_DWORD *)v10 + 6);
        do
        {
          if ( ++*(_DWORD *)v10 < v110 )
          {
            result = *((_QWORD *)v10 + 2) + *((_QWORD *)v10 + 1);
            *((_QWORD *)v10 + 1) = result;
          }
          else
          {
            *(_DWORD *)v10 = 0;
            *((_QWORD *)v10 + 1) = 0;
          }
          ++v109;
        }
        while ( v109 < Binary::Policy::SmoothArticle::GlobalCase[v16] );
      }
      ++v16;
      v9 = v127;
      if ( v16 >= 2 )
        v16 = 0;
      v111 = (int)++v113 < *(_DWORD *)(v7 + 8);
      v15 = v116;
      LODWORD(v112) = v16;
    }
    while ( v111 );
  }
  return result;
}

```

## disassembly

```asm
0x180094b90  push    rbp
0x180094b92  push    rbx
0x180094b93  push    rsi
0x180094b94  push    rdi
0x180094b95  push    r12
0x180094b97  push    r14
0x180094b99  push    r15
0x180094b9b  lea     rbp, [rsp-170h]
0x180094ba3  sub     rsp, 270h
0x180094baa  mov     rax, cs:__security_cookie
0x180094bb1  xor     rax, rsp
0x180094bb4  mov     [rbp+1A0h+var_F0], rax
0x180094bbb  mov     eax, [rcx+4]
0x180094bbe  xor     r12d, r12d
0x180094bc1  mov     rdi, [rbp+1A0h+arg_20]
0x180094bc8  mov     r14, r9
0x180094bcb  mov     [rbp+1A0h+var_1F8], r9
0x180094bcf  mov     r15, r8
0x180094bd2  mov     r9d, 2
0x180094bd8  mov     [rbp+1A0h+var_1F0], r8
0x180094bdc  mov     rsi, rdx
0x180094bdf  mov     [rsp+2A0h+var_238], rdx
0x180094be4  mov     rbx, rcx
0x180094be7  mov     [rsp+2A0h+var_240], rdi
0x180094bec  add     eax, 3
0x180094bef  mov     [rsp+2A0h+var_260], r12
0x180094bf4  lea     edx, [r12+5]
0x180094bf9  mov     [rsp+2A0h+var_248], r12d
0x180094bfe  mov     r8d, r9d
0x180094c01  mov     dword ptr [rsp+2A0h+var_280], eax
0x180094c05  lea     rcx, [rsp+2A0h+var_258]
0x180094c0a  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x180094c0f  cmp     [rsp+2A0h+var_254], r12b
0x180094c14  lea     rcx, [rsp+2A0h+var_248]
0x180094c19  mov     edx, r12d
0x180094c1c  cmovnz  edx, [rsp+2A0h+var_258]
0x180094c21  call    ??$MixedRelation@VSmoothArticle@Policy@Binary@@$01@Policy@Binary@@YAXAEAHH@Z; Binary::Policy::MixedRelation<Binary::Policy::SmoothArticle,2>(int &,int)
0x180094c26  mov     eax, [rbx]
0x180094c28  lea     edx, [r12+5]
0x180094c2d  mov     r9d, 2
0x180094c33  lea     rcx, [rsp+2A0h+var_258]
0x180094c38  add     eax, 3
0x180094c3b  mov     r8d, r9d
0x180094c3e  mov     dword ptr [rsp+2A0h+var_280], eax
0x180094c42  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x180094c47  cmp     [rsp+2A0h+var_254], r12b
0x180094c4c  lea     rcx, [rsp+2A0h+var_260]
0x180094c51  mov     edx, r12d
0x180094c54  cmovnz  edx, [rsp+2A0h+var_258]
0x180094c59  call    ??$ReviseCommonBinary@VNewMode@Policy@Binary@@$01@Policy@Binary@@YAXAEAV?$RightAbstraction@$01@Data@@H@Z; Binary::Policy::ReviseCommonBinary<Binary::Policy::NewMode,2>(Data::RightAbstraction<2> &,int)
0x180094c5e  cmp     dword ptr [rdi+0Ch], 9
0x180094c62  jge     short loc_180094C87
0x180094c64  movups  xmm0, xmmword ptr [rbx]
0x180094c67  mov     r9, r14
0x180094c6a  mov     [rsp+2A0h+var_280], rdi
0x180094c6f  mov     r8, r15
0x180094c72  lea     rcx, [rbp+1A0h+var_140]
0x180094c76  mov     rdx, rsi
0x180094c79  movaps  [rbp+1A0h+var_140], xmm0
0x180094c7d  call    ??$MarkQuickestList@VSmoothArticle@Policy@Binary@@$01@Policy@Binary@@YAXV?$ShortTermResolution@H@Data@@AEAVCompleteResolution@3@AEBV?$HighDescription@PEAG@3@AEAVCompleteOperation@01@AEBV23@@Z; Binary::Policy::MarkQuickestList<Binary::Policy::SmoothArticle,2>(Data::ShortTermResolution<int>,Data::CompleteResolution &,Data::HighDescription<ushort *> const &,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &)
0x180094c82  jmp     loc_180095945
0x180094c87  mov     [rsp+2A0h+var_258], r12d
0x180094c8c  cmp     [rdi+8], r12d
0x180094c90  jle     loc_180095945
0x180094c96  mov     ebx, [rsp+2A0h+var_248]
0x180094c9a  mov     [rsp+2A0h+var_38], r13
0x180094ca2  mov     r13d, dword ptr [rsp+2A0h+var_260]
0x180094ca7  movaps  [rsp+2A0h+var_50], xmm6
0x180094caf  movaps  [rsp+2A0h+var_60], xmm7
0x180094cb7  movaps  [rsp+2A0h+var_70], xmm8
0x180094cc0  movaps  [rsp+2A0h+var_80], xmm9
0x180094cc9  movaps  [rsp+2A0h+var_90], xmm10
0x180094cd2  movaps  [rsp+2A0h+var_A0], xmm11
0x180094cdb  movaps  [rsp+2A0h+var_B0], xmm12
0x180094ce4  movaps  [rsp+2A0h+var_C0], xmm13
0x180094ced  movaps  [rsp+2A0h+var_D0], xmm14
0x180094cf6  movaps  [rsp+2A0h+var_E0], xmm15
0x180094cff  mov     dword ptr [rsp+2A0h+var_260], r13d
0x180094d04  nop     dword ptr [rax+00h]
0x180094d08  nop     dword ptr [rax+rax+00000000h]
0x180094d10  movups  xmm1, xmmword ptr [rsi+10h]
0x180094d14  lea     r8, [rbp+1A0h+var_160]
0x180094d18  mov     rdx, r15
0x180094d1b  xorps   xmm0, xmm0
0x180094d1e  lea     rcx, [rbp+1A0h+var_130]
0x180094d22  movups  [rbp+1A0h+var_130], xmm0
0x180094d26  movups  [rbp+1A0h+var_120], xmm0
0x180094d2d  movups  [rbp+1A0h+var_110], xmm0
0x180094d34  movups  [rbp+1A0h+var_100], xmm0
0x180094d3b  movups  xmm0, xmmword ptr [rsi]
0x180094d3e  movaps  [rbp+1A0h+var_150], xmm1
0x180094d42  movaps  [rbp+1A0h+var_160], xmm0
0x180094d46  call    ??$HelpSynchronousQuantity@VSmoothArticle@Policy@Binary@@$01@Policy@Binary@@YAXQEAV?$HighDescription@PEAG@Data@@AEBV23@VCompleteResolution@3@@Z; Binary::Policy::HelpSynchronousQuantity<Binary::Policy::SmoothArticle,2>(Data::HighDescription<ushort *> * const,Data::HighDescription<ushort *> const &,Data::CompleteResolution)
0x180094d4b  xorps   xmm0, xmm0
0x180094d4e  lea     rdx, [rbp+1A0h+var_140]
0x180094d52  mov     r8, rdi
0x180094d55  mov     rcx, r14
0x180094d58  movups  [rbp+1A0h+var_140], xmm0
0x180094d5c  call    ?TargetDigitalRegion@CompleteOperation@Policy@Binary@@QEAA?AV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@AEBV?$ShortTermResolution@H@Data@@@Z; Binary::Policy::CompleteOperation::TargetDigitalRegion(Data::ShortTermResolution<int> const &)
0x180094d61  xor     r15d, r15d
0x180094d64  mov     r14d, r12d
0x180094d67  cmp     ebx, 1
0x180094d6a  jbe     short loc_180094D8A
0x180094d6c  and     ebx, 80000001h
0x180094d72  mov     dword ptr [rsp+2A0h+var_250], ebx
0x180094d76  jge     short loc_180094D83
0x180094d78  dec     ebx
0x180094d7a  or      ebx, 0FFFFFFFEh
0x180094d7d  inc     ebx
0x180094d7f  mov     dword ptr [rsp+2A0h+var_250], ebx
0x180094d83  test    ebx, ebx
0x180094d85  jns     short loc_180094D90
0x180094d87  add     ebx, 2
0x180094d8a  mov     dword ptr [rsp+2A0h+var_250], ebx
0x180094d8e  test    ebx, ebx
0x180094d90  jz      loc_180095034
0x180094d96  lea     rcx, cs:180000000h
0x180094d9d  movsxd  rax, r13d
0x180094da0  shl     rax, 6
0x180094da4  lea     r9, rva word_1800DE702[rcx]
0x180094dab  add     r9, rax
0x180094dae  lea     r10, rva ?OddOperation@SmoothArticle@Policy@Binary@@2V?$OneContext@V?$OneContext@G$07$00$0A@$0BA@@Data@@$01$00$0A@$0IA@@Data@@B[rcx]; Data::OneContext<Data::OneContext<ushort,8,1,0,16>,2,1,0,128> const Binary::Policy::SmoothArticle::OddOperation ...
0x180094db5  add     r10, rax
0x180094db8  lea     r11, rva byte_1800DE704[rcx]
0x180094dbf  add     r11, rax
0x180094dc2  lea     rsi, rva word_1800DE706[rcx]
0x180094dc9  add     rsi, rax
0x180094dcc  lea     rdi, rva byte_1800DE708[rcx]
0x180094dd3  add     rdi, rax
0x180094dd6  lea     r13, rva word_1800DE70A[rcx]
0x180094ddd  add     r13, rax
0x180094de0  lea     rdx, rva byte_1800DE70C[rcx]
0x180094de7  add     rdx, rax
0x180094dea  lea     rax, [rax+0DE70Eh]
0x180094df1  add     rax, rcx
0x180094df4  mov     [rsp+2A0h+var_230], rdx
0x180094df9  mov     [rsp+2A0h+var_250], rax
0x180094dfe  xchg    ax, ax
0x180094e00  lea     rax, cs:180000000h
0x180094e07  movsxd  r8, ebx
0x180094e0a  mov     rcx, r8
0x180094e0d  shl     rcx, 6
0x180094e11  movzx   eax, word ptr [rcx+rax+0DE700h]
0x180094e19  movd    xmm2, eax
0x180094e1d  lea     rax, cs:180000000h
0x180094e24  pinsrw  xmm2, word ptr [rcx+rax+0DE702h], 1
0x180094e2e  pinsrw  xmm2, word ptr [rcx+rax+0DE704h], 2
0x180094e38  pinsrw  xmm2, word ptr [rcx+rax+0DE706h], 3
0x180094e42  pinsrw  xmm2, word ptr [rcx+rax+0DE708h], 4
0x180094e4c  pinsrw  xmm2, word ptr [rcx+rax+0DE70Ah], 5
0x180094e56  pinsrw  xmm2, word ptr [rcx+rax+0DE70Ch], 6
0x180094e60  pinsrw  xmm2, word ptr [rcx+rax+0DE70Eh], 7
0x180094e6a  movsxd  rax, r14d
0x180094e6d  lea     rcx, [rax+rax]
0x180094e71  movsx   eax, word ptr [r10]
0x180094e75  movd    xmm3, eax
0x180094e79  mov     rax, qword ptr [rbp+1A0h+var_130]
0x180094e7d  punpcklwd xmm3, xmm3
0x180094e81  pshufd  xmm3, xmm3, 0
0x180094e86  movdqu  xmm0, xmmword ptr [rax+rcx]
0x180094e8b  movsx   eax, word ptr [r9]
0x180094e8f  pmullw  xmm3, xmm0
0x180094e93  movd    xmm1, eax
0x180094e97  mov     rax, qword ptr [rbp+1A0h+var_130+8]
0x180094e9b  punpcklwd xmm1, xmm1
0x180094e9f  pshufd  xmm1, xmm1, 0
0x180094ea4  movdqu  xmm0, xmmword ptr [rax+rcx]
0x180094ea9  movsx   eax, word ptr [r11]
0x180094ead  pmullw  xmm1, xmm0
0x180094eb1  paddw   xmm3, xmm1
0x180094eb5  movd    xmm1, eax
0x180094eb9  mov     rax, qword ptr [rbp+1A0h+var_120]
0x180094ec0  punpcklwd xmm1, xmm1
0x180094ec4  pshufd  xmm1, xmm1, 0
0x180094ec9  movdqu  xmm0, xmmword ptr [rax+rcx]
0x180094ece  movsx   eax, word ptr [rsi]
0x180094ed1  pmullw  xmm1, xmm0
0x180094ed5  paddw   xmm3, xmm1
0x180094ed9  movd    xmm1, eax
0x180094edd  mov     rax, qword ptr [rbp+1A0h+var_120+8]
0x180094ee4  punpcklwd xmm1, xmm1
0x180094ee8  pshufd  xmm1, xmm1, 0
0x180094eed  movdqu  xmm0, xmmword ptr [rax+rcx]
0x180094ef2  movsx   eax, word ptr [rdi]
0x180094ef5  pmullw  xmm1, xmm0
0x180094ef9  paddw   xmm3, xmm1
0x180094efd  movd    xmm1, eax
0x180094f01  mov     rax, qword ptr [rbp+1A0h+var_110]
0x180094f08  punpcklwd xmm1, xmm1
0x180094f0c  pshufd  xmm1, xmm1, 0
0x180094f11  movdqu  xmm0, xmmword ptr [rax+rcx]
0x180094f16  movsx   eax, word ptr [r13+0]
0x180094f1b  pmullw  xmm1, xmm0
0x180094f1f  paddw   xmm3, xmm1
0x180094f23  movd    xmm1, eax
0x180094f27  mov     rax, qword ptr [rbp+1A0h+var_110+8]
0x180094f2e  punpcklwd xmm1, xmm1
0x180094f32  pshufd  xmm1, xmm1, 0
0x180094f37  movdqu  xmm0, xmmword ptr [rax+rcx]
0x180094f3c  movsx   eax, word ptr [rdx]
0x180094f3f  pmullw  xmm1, xmm0
0x180094f43  paddw   xmm3, xmm1
0x180094f47  movd    xmm1, eax
0x180094f4b  mov     rax, qword ptr [rbp+1A0h+var_100]
0x180094f52  punpcklwd xmm1, xmm1
0x180094f56  pshufd  xmm1, xmm1, 0
0x180094f5b  movdqu  xmm0, xmmword ptr [rax+rcx]
0x180094f60  mov     rax, [rsp+2A0h+var_250]
0x180094f65  pmullw  xmm1, xmm0
0x180094f69  movsx   eax, word ptr [rax]
0x180094f6c  paddw   xmm3, xmm1
0x180094f70  movd    xmm1, eax
0x180094f74  mov     rax, qword ptr [rbp+1A0h+var_100+8]
0x180094f7b  punpcklwd xmm1, xmm1
0x180094f7f  pshufd  xmm1, xmm1, 0
0x180094f84  movdqu  xmm0, xmmword ptr [rax+rcx]
0x180094f89  pmullw  xmm1, xmm0
0x180094f8d  paddw   xmm3, xmm1
0x180094f91  psrlw   xmm3, 6
0x180094f96  pmullw  xmm3, xmm2
0x180094f9a  pextrw  ecx, xmm3, 1
0x180094f9f  movd    edx, xmm3
0x180094fa3  movdqa  xmm0, xmm3
0x180094fa7  psrldq  xmm0, 4
0x180094fac  movd    eax, xmm0
0x180094fb0  movdqa  xmm0, xmm3
0x180094fb4  add     edx, ecx
0x180094fb6  psrldq  xmm0, 8
0x180094fbb  pextrw  ecx, xmm3, 3
0x180094fc0  add     edx, eax
0x180094fc2  movd    eax, xmm0
0x180094fc6  movdqa  xmm0, xmm3
0x180094fca  psrldq  xmm0, 0Ch
0x180094fcf  add     edx, ecx
0x180094fd1  add     edx, eax
0x180094fd3  movd    eax, xmm0
0x180094fd7  pextrw  ecx, xmm3, 5
0x180094fdc  add     edx, ecx
0x180094fde  add     edx, eax
0x180094fe0  mov     rax, qword ptr [rbp+1A0h+var_140+8]
0x180094fe4  pextrw  ecx, xmm3, 7
0x180094fe9  add     edx, ecx
0x180094feb  shr     edx, 8
0x180094fee  mov     [rax+r15], dl
0x180094ff2  lea     rax, cs:180000000h
0x180094ff9  add     r14d, ds:rva ?GlobalCase@SmoothArticle@Policy@Binary@@2V?$StripedCategory@H$01@Data@@B[rax+r8*4]; Data::StripedCategory<int,2> const Binary::Policy::SmoothArticle::GlobalCase ...
0x180095001  lea     eax, [rbx+1]
0x180095004  mov     rdx, [rsp+2A0h+var_230]
0x180095009  xor     ebx, ebx
0x18009500b  cmp     eax, 2
0x18009500e  cmovl   ebx, eax
0x180095011  inc     r12d
0x180095014  inc     r15
0x180095017  test    ebx, ebx
0x180095019  jnz     loc_180094E00
0x18009501f  mov     rsi, [rsp+2A0h+var_238]
0x180095024  xor     ebx, ebx
0x180095026  mov     r13d, dword ptr [rsp+2A0h+var_260]
0x18009502b  mov     rdi, [rsp+2A0h+var_240]
0x180095030  mov     dword ptr [rsp+2A0h+var_250], ebx
0x180095034  mov     ecx, [rdi+0Ch]
0x180095037  lea     eax, [rcx-7]
0x18009503a  cmp     r12d, eax
0x18009503d  jge     loc_1800955B2
0x180095043  movdqa  xmm14, cs:__xmm@000100040009000e0010000c00060002
0x18009504c  lea     rsi, cs:180000000h
0x180095053  movdqa  xmm15, cs:__xmm@00020006000c0010000e000900040001
0x18009505c  lea     rbx, rva word_1800DE702[rsi]
0x180095063  movsxd  rax, r13d
0x180095066  lea     rdx, rva ?OddOperation@SmoothArticle@Policy@Binary@@2V?$OneContext@V?$OneContext@G$07$00$0A@$0BA@@Data@@$01$00$0A@$0IA@@Data@@B[rsi]; Data::OneContext<Data::OneContext<ushort,8,1,0,16>,2,1,0,128> const Binary::Policy::SmoothArticle::OddOperation ...
0x18009506d  shl     rax, 6
0x180095071  lea     r8, rva byte_1800DE704[rsi]
0x180095078  add     rdx, rax
0x18009507b  movsxd  rcx, r14d
0x18009507e  add     r8, rax
0x180095081  mov     [rbp+1A0h+var_210], rdx
0x180095085  lea     r9, rva word_1800DE706[rsi]
0x18009508c  mov     [rbp+1A0h+var_208], r8
0x180095090  add     r9, rax
0x180095093  lea     r10, rva byte_1800DE708[rsi]
0x18009509a  add     r10, rax
0x18009509d  mov     [rbp+1A0h+var_200], r9
0x1800950a1  lea     r11, rva word_1800DE70A[rsi]
0x1800950a8  mov     [rsp+2A0h+var_228], r10
0x1800950ad  add     r11, rax
0x1800950b0  lea     rdi, rva byte_1800DE70C[rsi]
0x1800950b7  add     rdi, rax
0x1800950ba  mov     [rbp+1A0h+var_220], r11
0x1800950be  add     rbx, rax
0x1800950c1  mov     [rbp+1A0h+var_218], rdi
0x1800950c5  lea     rax, [rax+0DE70Eh]
0x1800950cc  add     rax, rsi
0x1800950cf  lea     r13, ds:14h[rcx*2]
0x1800950d7  mov     rsi, [rsp+2A0h+var_240]
0x1800950dc  mov     [rsp+2A0h+var_230], rax
0x1800950e1  movsx   eax, word ptr [rbx]
0x1800950e4  mov     rcx, qword ptr [rbp+1A0h+var_100]
0x1800950eb  movd    xmm12, eax
0x1800950f0  movsx   eax, word ptr [rdx]
0x1800950f3  mov     rdx, qword ptr [rbp+1A0h+var_110+8]
  ... truncated ...
```
