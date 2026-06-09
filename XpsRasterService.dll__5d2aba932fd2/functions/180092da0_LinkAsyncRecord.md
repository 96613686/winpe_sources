# LinkAsyncRecord

- ea: `0x180092da0`
- end: `0x180093a9d`
- name: `LinkAsyncRecord`
- size: `3325`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180091ec0`

## callees

- `0x180003180`
- `0x180054440`
- `0x180087c20`
- `0x180087ce0`
- `0x180087f90`
- `0x18008b060`
- `0x18008f1e0`
- `0x18008fdd0`
- `0x180091f80`
- `0x180092da0`

## pseudocode

```c
char __fastcall LinkAsyncRecord(_DWORD *a1, __int64 a2, __int64 *a3, __int64 a4, __int64 a5)
{
  int v5; // eax
  int v6; // r12d
  __int64 v7; // rdi
  __int64 v8; // r14
  __int64 *v9; // r15
  __int64 v10; // rbx
  __int64 v12; // rdx
  int v13; // edx
  __int64 v14; // rax
  __m128i si128; // xmm11
  __m128i v16; // xmm12
  __m128i v17; // xmm13
  __m128i v18; // xmm14
  signed int v19; // esi
  int v20; // r13d
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int64 v23; // r15
  int v24; // r14d
  bool v25; // zf
  __int64 v26; // rax
  __int16 *v27; // r9
  char *v28; // r10
  char *v29; // r11
  __int16 *v30; // rbx
  char *v31; // rdi
  __int16 *v32; // r13
  char *v33; // rdx
  __int64 v34; // rcx
  __m128i inserted; // xmm2
  __int64 v36; // rcx
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
  __m128i v48; // xmm1
  __m128i v49; // xmm3
  __m128i v50; // xmm1
  __m128i v51; // xmm3
  int v52; // eax
  int v53; // ecx
  __int64 v54; // rax
  char *v55; // rdx
  char *v56; // r8
  __int16 *v57; // r9
  char *v58; // r10
  __int16 *v59; // r11
  char *v60; // rdi
  __int16 *v61; // rsi
  __int64 v62; // r13
  __int64 v63; // rbx
  __m128i v64; // xmm4
  __m128i v65; // xmm4
  __m128i v66; // xmm1
  __m128i v67; // xmm1
  __m128i v68; // xmm2
  __m128i v69; // xmm2
  __m128i v70; // xmm3
  __m128i v71; // xmm3
  __m128i v72; // xmm5
  __m128i v73; // xmm5
  __m128i v74; // xmm6
  __m128i v75; // xmm7
  __m128i v76; // xmm8
  __m128i v77; // xmm6
  __m128i v78; // xmm7
  __m128i v79; // xmm8
  __m128i v80; // xmm10
  __m128i v81; // xmm9
  __m128i v82; // xmm2
  __int64 v83; // rax
  __int16 *v84; // r9
  char *v85; // r10
  char *v86; // r11
  __int16 *v87; // rbx
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
  __int64 v113; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v114; // [rsp+48h] [rbp-B8h] BYREF
  char v115; // [rsp+4Ch] [rbp-B4h]
  __int16 *v116; // [rsp+50h] [rbp-B0h]
  signed int v117; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v118; // [rsp+60h] [rbp-A0h]
  __int64 v119; // [rsp+68h] [rbp-98h]
  char *v120; // [rsp+70h] [rbp-90h]
  char *v121; // [rsp+78h] [rbp-88h]
  __int16 *v122; // [rsp+80h] [rbp-80h]
  char *v123; // [rsp+88h] [rbp-78h]
  char *v124; // [rsp+90h] [rbp-70h]
  char *v125; // [rsp+98h] [rbp-68h]
  char *v126; // [rsp+A0h] [rbp-60h]
  __int64 v127; // [rsp+A8h] [rbp-58h]
  __int64 *v128; // [rsp+B0h] [rbp-50h]
  union __m128i v129; // [rsp+C0h] [rbp-40h] BYREF
  union __m128i v130; // [rsp+D0h] [rbp-30h] BYREF
  union __m128i v131; // [rsp+E0h] [rbp-20h] BYREF
  union __m128i v132; // [rsp+F0h] [rbp-10h] BYREF
  union __m128i v133; // [rsp+100h] [rbp+0h] BYREF
  union __m128i v134; // [rsp+110h] [rbp+10h] BYREF
  union __m128i v135; // [rsp+120h] [rbp+20h] BYREF
  union __m128i v136; // [rsp+130h] [rbp+30h] BYREF
  _OWORD v137[2]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v138; // [rsp+160h] [rbp+60h] BYREF
  __int128 v139; // [rsp+170h] [rbp+70h] BYREF
  __int128 v140; // [rsp+180h] [rbp+80h]
  __int128 v141; // [rsp+190h] [rbp+90h]
  __int128 v142; // [rsp+1A0h] [rbp+A0h]

  v5 = a1[1];
  v6 = 0;
  v7 = a5;
  v8 = a4;
  v127 = a4;
  v9 = a3;
  v128 = a3;
  v10 = a2;
  v119 = a2;
  v118 = a5;
  v113 = 0;
  v117 = 0;
  Binary::Definition::GenerateAsyncServer((unsigned int)&v114, 5, 4, 4, v5 + 3);
  v12 = 0;
  if ( v115 )
    v12 = v114;
  Binary::Policy::MixedRelation<Binary::Policy::SlowSource,2>(&v117, v12);
  Binary::Definition::GenerateAsyncServer((unsigned int)&v114, 5, 4, 4, *a1 + 3);
  v13 = 0;
  if ( v115 )
    v13 = v114;
  LOBYTE(v14) = Binary::Policy::ReviseCommonBinary<Binary::Policy::SlowSource,2>((int *)&v113, v13);
  if ( *(int *)(a5 + 12) >= 11 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v16 = _mm_load_si128((const __m128i *)&_xmm);
    v17 = _mm_load_si128((const __m128i *)&_xmm);
    v18 = _mm_load_si128((const __m128i *)&_xmm);
    v114 = 0;
    if ( *(int *)(a5 + 8) <= 0 )
      return v14;
    v19 = v117;
    v20 = v113;
    while ( 1 )
    {
      v21 = *(_OWORD *)(v10 + 16);
      v139 = 0;
      v140 = 0;
      v141 = 0;
      v142 = 0;
      v22 = *(_OWORD *)v10;
      v137[1] = v21;
      v137[0] = v22;
      Binary::Policy::HelpSynchronousQuantity<Binary::Policy::SmoothArticle,2>(&v139, v9, (int *)v137);
      v138 = 0;
      Binary::Policy::CompleteOperation::TargetDigitalRegion(v8, &v138);
      v23 = 0;
      v24 = 0;
      if ( (unsigned int)v19 > 3 )
      {
        v19 &= 0x80000003;
        LODWORD(v116) = v19;
        if ( v19 < 0 )
        {
          v19 = (((_BYTE)v19 - 1) | 0xFFFFFFFC) + 1;
          LODWORD(v116) = v19;
        }
        v25 = v19 == 0;
        if ( v19 >= 0 )
          goto LABEL_15;
        v19 += 4;
      }
      LODWORD(v116) = v19;
      v25 = v19 == 0;
LABEL_15:
      if ( !v25 )
      {
        v26 = (__int64)v20 << 6;
        v27 = (__int16 *)((char *)&word_1800DE482 + v26);
        v28 = &Binary::Policy::SlowSource::OddOperation[v26];
        v29 = &byte_1800DE484[v26];
        v30 = (__int16 *)((char *)&word_1800DE486 + v26);
        v31 = &byte_1800DE488[v26];
        v32 = (__int16 *)((char *)&word_1800DE48A + v26);
        v33 = &byte_1800DE48C[v26];
        v120 = &byte_1800DE48C[v26];
        v116 = (__int16 *)(0x180000000LL + v26 + 910478);
        do
        {
          v34 = (__int64)v19 << 6;
          inserted = _mm_insert_epi16(
                       _mm_insert_epi16(
                         _mm_insert_epi16(
                           _mm_insert_epi16(
                             _mm_insert_epi16(
                               _mm_insert_epi16(
                                 _mm_insert_epi16(
                                   _mm_cvtsi32_si128(*(unsigned __int16 *)&Binary::Policy::SlowSource::OddOperation[v34]),
                                   *(unsigned __int16 *)((char *)&word_1800DE482 + v34),
                                   1),
                                 *(unsigned __int16 *)&byte_1800DE484[v34],
                                 2),
                               *(unsigned __int16 *)((char *)&word_1800DE486 + v34),
                               3),
                             *(unsigned __int16 *)&byte_1800DE488[v34],
                             4),
                           *(unsigned __int16 *)((char *)&word_1800DE48A + v34),
                           5),
                         *(unsigned __int16 *)&byte_1800DE48C[v34],
                         6),
                       *(unsigned __int16 *)((char *)&word_1800DE48E + v34),
                       7);
          v36 = 2LL * v24;
          v37 = _mm_cvtsi32_si128(*(__int16 *)v28);
          v38 = _mm_cvtsi32_si128(*v27);
          v39 = _mm_add_epi16(
                  _mm_mullo_epi16(
                    _mm_shuffle_epi32(_mm_unpacklo_epi16(v37, v37), 0),
                    _mm_loadu_si128((const __m128i *)(v36 + v139))),
                  _mm_mullo_epi16(
                    _mm_shuffle_epi32(_mm_unpacklo_epi16(v38, v38), 0),
                    _mm_loadu_si128((const __m128i *)(v36 + *((_QWORD *)&v139 + 1)))));
          v40 = _mm_cvtsi32_si128(*(__int16 *)v29);
          v41 = _mm_add_epi16(
                  v39,
                  _mm_mullo_epi16(
                    _mm_shuffle_epi32(_mm_unpacklo_epi16(v40, v40), 0),
                    _mm_loadu_si128((const __m128i *)(v36 + v140))));
          v42 = _mm_cvtsi32_si128(*v30);
          v43 = _mm_add_epi16(
                  v41,
                  _mm_mullo_epi16(
                    _mm_shuffle_epi32(_mm_unpacklo_epi16(v42, v42), 0),
                    _mm_loadu_si128((const __m128i *)(v36 + *((_QWORD *)&v140 + 1)))));
          v44 = _mm_cvtsi32_si128(*(__int16 *)v31);
          v45 = _mm_add_epi16(
                  v43,
                  _mm_mullo_epi16(
                    _mm_shuffle_epi32(_mm_unpacklo_epi16(v44, v44), 0),
                    _mm_loadu_si128((const __m128i *)(v36 + v141))));
          v46 = _mm_cvtsi32_si128(*v32);
          v47 = _mm_add_epi16(
                  v45,
                  _mm_mullo_epi16(
                    _mm_shuffle_epi32(_mm_unpacklo_epi16(v46, v46), 0),
                    _mm_loadu_si128((const __m128i *)(v36 + *((_QWORD *)&v141 + 1)))));
          v48 = _mm_cvtsi32_si128(*(__int16 *)v33);
          v49 = _mm_add_epi16(
                  v47,
                  _mm_mullo_epi16(
                    _mm_shuffle_epi32(_mm_unpacklo_epi16(v48, v48), 0),
                    _mm_loadu_si128((const __m128i *)(v36 + v142))));
          v50 = _mm_cvtsi32_si128(*v116);
          v51 = _mm_mullo_epi16(
                  _mm_srli_epi16(
                    _mm_add_epi16(
                      v49,
                      _mm_mullo_epi16(
                        _mm_shuffle_epi32(_mm_unpacklo_epi16(v50, v50), 0),
                        _mm_loadu_si128((const __m128i *)(v36 + *((_QWORD *)&v142 + 1))))),
                    6u),
                  inserted);
          *(_BYTE *)(v23 + *((_QWORD *)&v138 + 1)) = (unsigned __int16)(_mm_extract_epi16(v51, 7)
                                                                      + _mm_cvtsi128_si32(_mm_srli_si128(v51, 12))
                                                                      + _mm_extract_epi16(v51, 5)
                                                                      + _mm_cvtsi128_si32(_mm_srli_si128(v51, 8))
                                                                      + _mm_extract_epi16(v51, 3)
                                                                      + _mm_cvtsi128_si32(_mm_srli_si128(v51, 4))
                                                                      + _mm_extract_epi16(v51, 1)
                                                                      + _mm_cvtsi128_si32(v51)) >> 8;
          v24 += Binary::Policy::SlowSource::GlobalCase[v19];
          v52 = v19 + 1;
          v33 = v120;
          v19 = 0;
          if ( v52 < 4 )
            v19 = v52;
          ++v6;
          ++v23;
        }
        while ( v19 );
        v10 = v119;
        v19 = 0;
        v20 = v113;
        v7 = v118;
        LODWORD(v116) = 0;
      }
      v53 = *(_DWORD *)(v7 + 12);
      if ( v6 < v53 - 7 )
      {
        v54 = (__int64)v20 << 6;
        v55 = &Binary::Policy::SlowSource::OddOperation[v54];
        v56 = &byte_1800DE484[v54];
        v124 = &Binary::Policy::SlowSource::OddOperation[v54];
        v125 = &byte_1800DE484[v54];
        v57 = (__int16 *)((char *)&word_1800DE486 + v54);
        v58 = &byte_1800DE488[v54];
        v126 = (char *)&word_1800DE486 + v54;
        v121 = &byte_1800DE488[v54];
        v59 = (__int16 *)((char *)&word_1800DE48A + v54);
        v60 = &byte_1800DE48C[v54];
        v122 = (__int16 *)((char *)&word_1800DE48A + v54);
        v61 = (__int16 *)((char *)&word_1800DE482 + v54);
        v123 = &byte_1800DE48C[v54];
        v62 = 2LL * v24;
        v63 = v118;
        v120 = (char *)(0x180000000LL + v54 + 910478);
        do
        {
          v64 = _mm_cvtsi32_si128(*v61);
          v65 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v64, v64), 0);
          v66 = _mm_cvtsi32_si128(*(__int16 *)v55);
          v67 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v66, v66), 0);
          v68 = _mm_cvtsi32_si128(*(__int16 *)v56);
          v69 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v68, v68), 0);
          v70 = _mm_cvtsi32_si128(*v57);
          v71 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v70, v70), 0);
          v72 = _mm_cvtsi32_si128(*(__int16 *)v58);
          v73 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v72, v72), 0);
          v74 = _mm_cvtsi32_si128(*v59);
          v75 = _mm_cvtsi32_si128(*(__int16 *)v60);
          v76 = _mm_cvtsi32_si128(*(__int16 *)v120);
          v77 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v74, v74), 0);
          v78 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v75, v75), 0);
          v79 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v76, v76), 0);
          v80 = _mm_srli_epi16(
                  _mm_add_epi16(
                    _mm_add_epi16(
                      _mm_add_epi16(
                        _mm_add_epi16(
                          _mm_add_epi16(
                            _mm_add_epi16(
                              _mm_add_epi16(
                                _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v139 + v62)), v67),
                                _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(*((_QWORD *)&v139 + 1) + v62)), v65)),
                              _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v140 + v62)), v69)),
                            _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(*((_QWORD *)&v140 + 1) + v62)), v71)),
                          _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v141 + v62)), v73)),
                        _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(*((_QWORD *)&v141 + 1) + v62)), v77)),
                      _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v142 + v62)), v78)),
                    _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(*((_QWORD *)&v142 + 1) + v62)), v79)),
                  6u);
          v81 = _mm_srli_epi16(
                  _mm_add_epi16(
                    _mm_add_epi16(
                      _mm_add_epi16(
                        _mm_add_epi16(
                          _mm_add_epi16(
                            _mm_add_epi16(
                              _mm_add_epi16(
                                _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v139 + v62 + 16)), v67),
                                _mm_mullo_epi16(
                                  _mm_loadu_si128((const __m128i *)(*((_QWORD *)&v139 + 1) + v62 + 16)),
                                  v65)),
                              _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v140 + v62 + 16)), v69)),
                            _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(*((_QWORD *)&v140 + 1) + v62 + 16)), v71)),
                          _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v141 + v62 + 16)), v73)),
                        _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(*((_QWORD *)&v141 + 1) + v62 + 16)), v77)),
                      _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(v142 + v62 + 16)), v78)),
                    _mm_mullo_epi16(_mm_loadu_si128((const __m128i *)(*((_QWORD *)&v142 + 1) + v62 + 16)), v79)),
                  6u);
          v129 = _mm_mullo_epi16(si128, v80);
          v130 = _mm_mullo_epi16(_mm_or_si128(_mm_slli_si128(v81, 14), _mm_srli_si128(v80, 2)), v16);
          v131 = _mm_mullo_epi16(_mm_or_si128(_mm_slli_si128(v81, 12), _mm_srli_si128(v80, 4)), v17);
          v132 = _mm_mullo_epi16(_mm_or_si128(_mm_slli_si128(v81, 10), _mm_srli_si128(v80, 6)), v18);
          v133 = _mm_mullo_epi16(_mm_or_si128(_mm_slli_si128(v81, 6), _mm_srli_si128(v80, 10)), si128);
          v134 = _mm_mullo_epi16(_mm_or_si128(_mm_slli_si128(v81, 4), _mm_srli_si128(v80, 12)), v16);
          v135 = _mm_mullo_epi16(_mm_or_si128(_mm_slli_si128(v81, 2), _mm_srli_si128(v80, 14)), v17);
          v136 = _mm_mullo_epi16(v18, v81);
          TreatCoordinatedPackage(&v129, &v130, &v131, &v132, &v133, &v134, &v135, &v136);
          v82 = _mm_srli_epi16(
                  _mm_add_epi16(
                    _mm_add_epi16(
                      _mm_add_epi16(_mm_load_si128(&v136), v135),
                      _mm_add_epi16(_mm_load_si128(&v134), v133)),
                    _mm_add_epi16(
                      _mm_add_epi16(_mm_load_si128(&v132), v131),
                      _mm_add_epi16(_mm_load_si128(&v130), v129))),
                  8u);
          v62 += 20;
          v55 = v124;
          v56 = v125;
          v6 += 8;
          v57 = (__int16 *)v126;
          v24 += 10;
          v58 = v121;
          v59 = v122;
          v60 = v123;
          *(_BYTE *)(v23 + *((_QWORD *)&v138 + 1)) = _mm_cvtsi128_si32(v82);
          *(_BYTE *)(v23 + *((_QWORD *)&v138 + 1) + 1) = _mm_cvtsi128_si32(_mm_srli_si128(v82, 2));
          *(_BYTE *)(v23 + *((_QWORD *)&v138 + 1) + 2) = _mm_cvtsi128_si32(_mm_srli_si128(v82, 4));
          *(_BYTE *)(v23 + *((_QWORD *)&v138 + 1) + 3) = _mm_cvtsi128_si32(_mm_srli_si128(v82, 6));
          *(_BYTE *)(v23 + *((_QWORD *)&v138 + 1) + 4) = _mm_cvtsi128_si32(_mm_srli_si128(v82, 8));
          *(_BYTE *)(v23 + *((_QWORD *)&v138 + 1) + 5) = _mm_cvtsi128_si32(_mm_srli_si128(v82, 10));
          *(_BYTE *)(v23 + *((_QWORD *)&v138 + 1) + 6) = _mm_cvtsi128_si32(_mm_srli_si128(v82, 12));
          *(_BYTE *)(v23 + *((_QWORD *)&v138 + 1) + 7) = _mm_cvtsi128_si32(_mm_srli_si128(v82, 14));
          v23 += 8;
          v53 = *(_DWORD *)(v63 + 12);
        }
        while ( v6 < v53 - 7 );
        v10 = v119;
        v19 = (int)v116;
        v20 = v113;
        v7 = v118;
      }
      if ( v6 < v53 )
      {
        v83 = (__int64)v20 << 6;
        v84 = (__int16 *)((char *)&word_1800DE482 + v83);
        v85 = &Binary::Policy::SlowSource::OddOperation[v83];
        v86 = &byte_1800DE484[v83];
        v87 = (__int16 *)((char *)&word_1800DE486 + v83);
        v88 = &byte_1800DE488[v83];
        v89 = (char *)&word_1800DE48A + v83;
        v121 = (char *)&word_1800DE48A + v83;
        v123 = &byte_1800DE48C[v83];
        v122 = (__int16 *)(0x180000000LL + v83 + 910478);
        do
        {
          v90 = (__int64)v19 << 6;
          v91 = _mm_insert_epi16(
                  _mm_insert_epi16(
                    _mm_insert_epi16(
                      _mm_insert_epi16(
                        _mm_insert_epi16(
                          _mm_insert_epi16(
                            _mm_insert_epi16(
                              _mm_cvtsi32_si128(*(unsigned __int16 *)&Binary::Policy::SlowSource::OddOperation[v90]),
                              *(unsigned __int16 *)((char *)&word_1800DE482 + v90),
                              1),
                            *(unsigned __int16 *)&byte_1800DE484[v90],
                            2),
                          *(unsigned __int16 *)((char *)&word_1800DE486 + v90),
                          3),
                        *(unsigned __int16 *)&byte_1800DE488[v90],
                        4),
                      *(unsigned __int16 *)((char *)&word_1800DE48A + v90),
                      5),
                    *(unsigned __int16 *)&byte_1800DE48C[v90],
                    6),
                  *(unsigned __int16 *)((char *)&word_1800DE48E + v90),
                  7);
          v92 = 2LL * v24;
          v93 = _mm_cvtsi32_si128(*v84);
          v94 = _mm_cvtsi32_si128(*(__int16 *)v85);
          v95 = _mm_add_epi16(
                  _mm_mullo_epi16(
                    _mm_shuffle_epi32(_mm_unpacklo_epi16(v93, v93), 0),
                    _mm_loadu_si128((const __m128i *)(v92 + *((_QWORD *)&v139 + 1)))),
                  _mm_mullo_epi16(
                    _mm_shuffle_epi32(_mm_unpacklo_epi16(v94, v94), 0),
                    _mm_loadu_si128((const __m128i *)(v92 + v139))));
          v96 = _mm_cvtsi32_si128(*(__int16 *)v86);
          v97 = _mm_add_epi16(
                  v95,
                  _mm_mullo_epi16(
                    _mm_shuffle_epi32(_mm_unpacklo_epi16(v96, v96), 0),
                    _mm_loadu_si128((const __m128i *)(v92 + v140))));
          v98 = _mm_cvtsi32_si128(*v87);
          v99 = _mm_add_epi16(
                  v97,
                  _mm_mullo_epi16(
                    _mm_shuffle_epi32(_mm_unpacklo_epi16(v98, v98), 0),
                    _mm_loadu_si128((const __m128i *)(v92 + *((_QWORD *)&v140 + 1)))));
          v100 = _mm_cvtsi32_si128(*(__int16 *)v88);
          v101 = _mm_add_epi16(
                   v99,
                   _mm_mullo_epi16(
                     _mm_shuffle_epi32(_mm_unpacklo_epi16(v100, v100), 0),
                     _mm_loadu_si128((const __m128i *)(v92 + v141))));
          v102 = _mm_cvtsi32_si128(*(__int16 *)v89);
          v103 = _mm_add_epi16(
                   v101,
                   _mm_mullo_epi16(
                     _mm_shuffle_epi32(_mm_unpacklo_epi16(v102, v102), 0),
                     _mm_loadu_si128((const __m128i *)(v92 + *((_QWORD *)&v141 + 1)))));
          v104 = _mm_cvtsi32_si128(*(__int16 *)v123);
          v105 = _mm_add_epi16(
                   v103,
                   _mm_mullo_epi16(
                     _mm_shuffle_epi32(_mm_unpacklo_epi16(v104, v104), 0),
                     _mm_loadu_si128((const __m128i *)(v92 + v142))));
          v106 = _mm_cvtsi32_si128(*v122);
          ++v23;
          v107 = _mm_mullo_epi16(
                   _mm_srli_epi16(
                     _mm_add_epi16(
                       v105,
                       _mm_mullo_epi16(
                         _mm_shuffle_epi32(_mm_unpacklo_epi16(v106, v106), 0),
                         _mm_loadu_si128((const __m128i *)(v92 + *((_QWORD *)&v142 + 1))))),
                     6u),
                   v91);
          ++v6;
          *(_BYTE *)(v23 + *((_QWORD *)&v138 + 1) - 1) = (unsigned __int16)(_mm_extract_epi16(v107, 7)
                                                                          + _mm_cvtsi128_si32(_mm_srli_si128(v107, 12))
                                                                          + _mm_extract_epi16(v107, 5)
                                                                          + _mm_cvtsi128_si32(_mm_srli_si128(v107, 8))
                                                                          + _mm_extract_epi16(v107, 3)
                                                                          + _mm_cvtsi128_si32(_mm_srli_si128(v107, 4))
                                                                          + _mm_extract_epi16(v107, 1)
                                                                          + _mm_cvtsi128_si32(v107)) >> 8;
          v24 += Binary::Policy::SlowSource::GlobalCase[v19];
          v108 = v19 + 1;
          v89 = v121;
          v19 = 0;
          if ( v108 < 4 )
            v19 = v108;
        }
        while ( v6 < *(_DWORD *)(v7 + 12) );
        v10 = v119;
        v20 = v113;
      }
      v8 = v127;
      Binary::Policy::CompleteOperation::MoveVirtualAddition(v127, &v138);
      v6 = 0;
      LOBYTE(v14) = v20;
      v109 = 0;
      if ( Binary::Policy::SlowSource::GlobalCase[v20] > 0 )
      {
        v110 = *(_DWORD *)(v10 + 24);
        do
        {
          if ( ++*(_DWORD *)v10 < v110 )
          {
            v14 = *(_QWORD *)(v10 + 16) + *(_QWORD *)(v10 + 8);
            *(_QWORD *)(v10 + 8) = v14;
          }
          else
          {
            *(_DWORD *)v10 = 0;
            *(_QWORD *)(v10 + 8) = 0;
          }
          ++v109;
        }
        while ( v109 < Binary::Policy::SlowSource::GlobalCase[v20] );
      }
      ++v20;
      v9 = v128;
      if ( v20 >= 4 )
        v20 = 0;
      v111 = (int)++v114 < *(_DWORD *)(v7 + 8);
      v19 = v117;
      LODWORD(v113) = v20;
      if ( !v111 )
        return v14;
    }
  }
  v138 = *(_OWORD *)a1;
  LOBYTE(v14) = Binary::Policy::MarkQuickestList<Binary::Policy::SlowSource,2>(&v138, v10, v9, v8, a5);
  return v14;
}

```

## disassembly

```asm
0x180092da0  push    rbp
0x180092da2  push    rbx
0x180092da3  push    rsi
0x180092da4  push    rdi
0x180092da5  push    r12
0x180092da7  push    r14
0x180092da9  push    r15
0x180092dab  lea     rbp, [rsp-160h]
0x180092db3  sub     rsp, 260h
0x180092dba  mov     rax, cs:__security_cookie
0x180092dc1  xor     rax, rsp
0x180092dc4  mov     [rbp+190h+var_E0], rax
0x180092dcb  mov     eax, [rcx+4]
0x180092dce  xor     r12d, r12d
0x180092dd1  mov     rdi, [rbp+190h+arg_20]
0x180092dd8  mov     r14, r9
0x180092ddb  mov     [rbp+190h+var_1E8], r9
0x180092ddf  mov     r15, r8
0x180092de2  mov     r9d, 4
0x180092de8  mov     [rbp+190h+var_1E0], r8
0x180092dec  mov     rbx, rdx
0x180092def  mov     [rsp+290h+var_228], rdx
0x180092df4  mov     rsi, rcx
0x180092df7  mov     [rsp+290h+var_230], rdi
0x180092dfc  add     eax, 3
0x180092dff  mov     [rsp+290h+var_250], r12
0x180092e04  lea     edx, [r12+5]
0x180092e09  mov     [rsp+290h+var_238], r12d
0x180092e0e  mov     r8d, r9d
0x180092e11  mov     dword ptr [rsp+290h+var_270], eax
0x180092e15  lea     rcx, [rsp+290h+var_248]
0x180092e1a  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x180092e1f  cmp     [rsp+290h+var_244], r12b
0x180092e24  lea     rcx, [rsp+290h+var_238]
0x180092e29  mov     edx, r12d
0x180092e2c  cmovnz  edx, [rsp+290h+var_248]
0x180092e31  call    ??$MixedRelation@VSlowSource@Policy@Binary@@$01@Policy@Binary@@YAXAEAHH@Z; Binary::Policy::MixedRelation<Binary::Policy::SlowSource,2>(int &,int)
0x180092e36  mov     eax, [rsi]
0x180092e38  lea     edx, [r12+5]
0x180092e3d  mov     r9d, 4
0x180092e43  lea     rcx, [rsp+290h+var_248]
0x180092e48  add     eax, 3
0x180092e4b  mov     r8d, r9d
0x180092e4e  mov     dword ptr [rsp+290h+var_270], eax
0x180092e52  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x180092e57  cmp     [rsp+290h+var_244], r12b
0x180092e5c  lea     rcx, [rsp+290h+var_250]
0x180092e61  mov     edx, r12d
0x180092e64  cmovnz  edx, [rsp+290h+var_248]
0x180092e69  call    ??$ReviseCommonBinary@VSlowSource@Policy@Binary@@$01@Policy@Binary@@YAXAEAV?$RightAbstraction@$03@Data@@H@Z; Binary::Policy::ReviseCommonBinary<Binary::Policy::SlowSource,2>(Data::RightAbstraction<4> &,int)
0x180092e6e  cmp     dword ptr [rdi+0Ch], 0Bh
0x180092e72  jge     short loc_180092E97
0x180092e74  movups  xmm0, xmmword ptr [rsi]
0x180092e77  mov     r9, r14
0x180092e7a  mov     [rsp+290h+var_270], rdi
0x180092e7f  mov     r8, r15
0x180092e82  lea     rcx, [rbp+190h+var_130]
0x180092e86  mov     rdx, rbx
0x180092e89  movaps  [rbp+190h+var_130], xmm0
0x180092e8d  call    ??$MarkQuickestList@VSlowSource@Policy@Binary@@$01@Policy@Binary@@YAXV?$ShortTermResolution@H@Data@@AEAVCompleteResolution@3@AEBV?$HighDescription@PEAG@3@AEAVCompleteOperation@01@AEBV23@@Z; Binary::Policy::MarkQuickestList<Binary::Policy::SlowSource,2>(Data::ShortTermResolution<int>,Data::CompleteResolution &,Data::HighDescription<ushort *> const &,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &)
0x180092e92  jmp     loc_180093A7C
0x180092e97  movaps  [rsp+290h+var_A0], xmm11
0x180092ea0  movdqa  xmm11, cs:__xmm@0000000000030012001b000f00010000
0x180092ea9  movaps  [rsp+290h+var_B0], xmm12
0x180092eb2  movdqa  xmm12, cs:__xmm@00000000000700160018000b00000000
0x180092ebb  movaps  [rsp+290h+var_C0], xmm13
0x180092ec4  movdqa  xmm13, cs:__xmm@00000000000b00180016000700000000
0x180092ecd  movaps  [rsp+290h+var_D0], xmm14
0x180092ed6  movdqa  xmm14, cs:__xmm@00000001000f001b0012000300000000
0x180092edf  mov     [rsp+290h+var_248], r12d
0x180092ee4  cmp     [rdi+8], r12d
0x180092ee8  jle     loc_180093A58
0x180092eee  mov     esi, [rsp+290h+var_238]
0x180092ef2  mov     [rsp+290h+var_38], r13
0x180092efa  mov     r13d, dword ptr [rsp+290h+var_250]
0x180092eff  movaps  [rsp+290h+var_50], xmm6
0x180092f07  movaps  [rsp+290h+var_60], xmm7
0x180092f0f  movaps  [rsp+290h+var_70], xmm8
0x180092f18  movaps  [rsp+290h+var_80], xmm9
0x180092f21  movaps  [rsp+290h+var_90], xmm10
0x180092f2a  mov     dword ptr [rsp+290h+var_250], r13d
0x180092f2f  nop
0x180092f30  movups  xmm1, xmmword ptr [rbx+10h]
0x180092f34  lea     r8, [rbp+190h+var_150]
0x180092f38  mov     rdx, r15
0x180092f3b  xorps   xmm0, xmm0
0x180092f3e  lea     rcx, [rbp+190h+var_120]
0x180092f42  movups  [rbp+190h+var_120], xmm0
0x180092f46  movups  [rbp+190h+var_110], xmm0
0x180092f4d  movups  [rbp+190h+var_100], xmm0
0x180092f54  movups  [rbp+190h+var_F0], xmm0
0x180092f5b  movups  xmm0, xmmword ptr [rbx]
0x180092f5e  movaps  [rbp+190h+var_140], xmm1
0x180092f62  movaps  [rbp+190h+var_150], xmm0
0x180092f66  call    ??$HelpSynchronousQuantity@VSmoothArticle@Policy@Binary@@$01@Policy@Binary@@YAXQEAV?$HighDescription@PEAG@Data@@AEBV23@VCompleteResolution@3@@Z; Binary::Policy::HelpSynchronousQuantity<Binary::Policy::SmoothArticle,2>(Data::HighDescription<ushort *> * const,Data::HighDescription<ushort *> const &,Data::CompleteResolution)
0x180092f6b  xorps   xmm0, xmm0
0x180092f6e  lea     rdx, [rbp+190h+var_130]
0x180092f72  mov     r8, rdi
0x180092f75  mov     rcx, r14
0x180092f78  movups  [rbp+190h+var_130], xmm0
0x180092f7c  call    ?TargetDigitalRegion@CompleteOperation@Policy@Binary@@QEAA?AV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@AEBV?$ShortTermResolution@H@Data@@@Z; Binary::Policy::CompleteOperation::TargetDigitalRegion(Data::ShortTermResolution<int> const &)
0x180092f81  xor     r15d, r15d
0x180092f84  mov     r14d, r12d
0x180092f87  cmp     esi, 3
0x180092f8a  jbe     short loc_180092FAA
0x180092f8c  and     esi, 80000003h
0x180092f92  mov     dword ptr [rsp+290h+var_240], esi
0x180092f96  jge     short loc_180092FA3
0x180092f98  dec     esi
0x180092f9a  or      esi, 0FFFFFFFCh
0x180092f9d  inc     esi
0x180092f9f  mov     dword ptr [rsp+290h+var_240], esi
0x180092fa3  test    esi, esi
0x180092fa5  jns     short loc_180092FB0
0x180092fa7  add     esi, 4
0x180092faa  mov     dword ptr [rsp+290h+var_240], esi
0x180092fae  test    esi, esi
0x180092fb0  jz      loc_180093254
0x180092fb6  lea     rcx, cs:180000000h
0x180092fbd  movsxd  rax, r13d
0x180092fc0  shl     rax, 6
0x180092fc4  lea     r9, rva word_1800DE482[rcx]
0x180092fcb  add     r9, rax
0x180092fce  lea     r10, rva ?OddOperation@SlowSource@Policy@Binary@@2V?$OneContext@V?$OneContext@G$07$00$0A@$0BA@@Data@@$03$00$0A@$0BAA@@Data@@B[rcx]; Data::OneContext<Data::OneContext<ushort,8,1,0,16>,4,1,0,256> const Binary::Policy::SlowSource::OddOperation ...
0x180092fd5  add     r10, rax
0x180092fd8  lea     r11, rva byte_1800DE484[rcx]
0x180092fdf  add     r11, rax
0x180092fe2  lea     rbx, rva word_1800DE486[rcx]
0x180092fe9  add     rbx, rax
0x180092fec  lea     rdi, rva byte_1800DE488[rcx]
0x180092ff3  add     rdi, rax
0x180092ff6  lea     r13, rva word_1800DE48A[rcx]
0x180092ffd  add     r13, rax
0x180093000  lea     rdx, rva byte_1800DE48C[rcx]
0x180093007  add     rdx, rax
0x18009300a  lea     rax, [rax+0DE48Eh]
0x180093011  add     rax, rcx
0x180093014  mov     [rsp+290h+var_220], rdx
0x180093019  mov     [rsp+290h+var_240], rax
0x18009301e  xchg    ax, ax
0x180093020  lea     rax, cs:180000000h
0x180093027  movsxd  r8, esi
0x18009302a  mov     rcx, r8
0x18009302d  shl     rcx, 6
0x180093031  movzx   eax, word ptr [rcx+rax+0DE480h]
0x180093039  movd    xmm2, eax
0x18009303d  lea     rax, cs:180000000h
0x180093044  pinsrw  xmm2, word ptr [rcx+rax+0DE482h], 1
0x18009304e  pinsrw  xmm2, word ptr [rcx+rax+0DE484h], 2
0x180093058  pinsrw  xmm2, word ptr [rcx+rax+0DE486h], 3
0x180093062  pinsrw  xmm2, word ptr [rcx+rax+0DE488h], 4
0x18009306c  pinsrw  xmm2, word ptr [rcx+rax+0DE48Ah], 5
0x180093076  pinsrw  xmm2, word ptr [rcx+rax+0DE48Ch], 6
0x180093080  pinsrw  xmm2, word ptr [rcx+rax+0DE48Eh], 7
0x18009308a  movsxd  rax, r14d
0x18009308d  lea     rcx, [rax+rax]
0x180093091  movsx   eax, word ptr [r10]
0x180093095  movd    xmm3, eax
0x180093099  mov     rax, qword ptr [rbp+190h+var_120]
0x18009309d  punpcklwd xmm3, xmm3
0x1800930a1  pshufd  xmm3, xmm3, 0
0x1800930a6  movdqu  xmm0, xmmword ptr [rcx+rax]
0x1800930ab  movsx   eax, word ptr [r9]
0x1800930af  pmullw  xmm3, xmm0
0x1800930b3  movd    xmm1, eax
0x1800930b7  mov     rax, qword ptr [rbp+190h+var_120+8]
0x1800930bb  punpcklwd xmm1, xmm1
0x1800930bf  pshufd  xmm1, xmm1, 0
0x1800930c4  movdqu  xmm0, xmmword ptr [rcx+rax]
0x1800930c9  movsx   eax, word ptr [r11]
0x1800930cd  pmullw  xmm1, xmm0
0x1800930d1  paddw   xmm3, xmm1
0x1800930d5  movd    xmm1, eax
0x1800930d9  mov     rax, qword ptr [rbp+190h+var_110]
0x1800930e0  punpcklwd xmm1, xmm1
0x1800930e4  pshufd  xmm1, xmm1, 0
0x1800930e9  movdqu  xmm0, xmmword ptr [rcx+rax]
0x1800930ee  movsx   eax, word ptr [rbx]
0x1800930f1  pmullw  xmm1, xmm0
0x1800930f5  paddw   xmm3, xmm1
0x1800930f9  movd    xmm1, eax
0x1800930fd  mov     rax, qword ptr [rbp+190h+var_110+8]
0x180093104  punpcklwd xmm1, xmm1
0x180093108  pshufd  xmm1, xmm1, 0
0x18009310d  movdqu  xmm0, xmmword ptr [rcx+rax]
0x180093112  movsx   eax, word ptr [rdi]
0x180093115  pmullw  xmm1, xmm0
0x180093119  paddw   xmm3, xmm1
0x18009311d  movd    xmm1, eax
0x180093121  mov     rax, qword ptr [rbp+190h+var_100]
0x180093128  punpcklwd xmm1, xmm1
0x18009312c  pshufd  xmm1, xmm1, 0
0x180093131  movdqu  xmm0, xmmword ptr [rcx+rax]
0x180093136  movsx   eax, word ptr [r13+0]
0x18009313b  pmullw  xmm1, xmm0
0x18009313f  paddw   xmm3, xmm1
0x180093143  movd    xmm1, eax
0x180093147  mov     rax, qword ptr [rbp+190h+var_100+8]
0x18009314e  punpcklwd xmm1, xmm1
0x180093152  pshufd  xmm1, xmm1, 0
0x180093157  movdqu  xmm0, xmmword ptr [rcx+rax]
0x18009315c  movsx   eax, word ptr [rdx]
0x18009315f  pmullw  xmm1, xmm0
0x180093163  paddw   xmm3, xmm1
0x180093167  movd    xmm1, eax
0x18009316b  mov     rax, qword ptr [rbp+190h+var_F0]
0x180093172  punpcklwd xmm1, xmm1
0x180093176  pshufd  xmm1, xmm1, 0
0x18009317b  movdqu  xmm0, xmmword ptr [rcx+rax]
0x180093180  mov     rax, [rsp+290h+var_240]
0x180093185  pmullw  xmm1, xmm0
0x180093189  movsx   eax, word ptr [rax]
0x18009318c  paddw   xmm3, xmm1
0x180093190  movd    xmm1, eax
0x180093194  mov     rax, qword ptr [rbp+190h+var_F0+8]
0x18009319b  punpcklwd xmm1, xmm1
0x18009319f  pshufd  xmm1, xmm1, 0
0x1800931a4  movdqu  xmm0, xmmword ptr [rcx+rax]
0x1800931a9  pmullw  xmm1, xmm0
0x1800931ad  paddw   xmm3, xmm1
0x1800931b1  psrlw   xmm3, 6
0x1800931b6  pmullw  xmm3, xmm2
0x1800931ba  pextrw  ecx, xmm3, 1
0x1800931bf  movd    edx, xmm3
0x1800931c3  movdqa  xmm0, xmm3
0x1800931c7  psrldq  xmm0, 4
0x1800931cc  movd    eax, xmm0
0x1800931d0  movdqa  xmm0, xmm3
0x1800931d4  add     edx, ecx
0x1800931d6  psrldq  xmm0, 8
0x1800931db  pextrw  ecx, xmm3, 3
0x1800931e0  add     edx, eax
0x1800931e2  movd    eax, xmm0
0x1800931e6  movdqa  xmm0, xmm3
0x1800931ea  psrldq  xmm0, 0Ch
0x1800931ef  add     edx, ecx
0x1800931f1  add     edx, eax
0x1800931f3  movd    eax, xmm0
0x1800931f7  pextrw  ecx, xmm3, 5
0x1800931fc  add     edx, ecx
0x1800931fe  add     edx, eax
0x180093200  mov     rax, qword ptr [rbp+190h+var_130+8]
0x180093204  pextrw  ecx, xmm3, 7
0x180093209  add     edx, ecx
0x18009320b  shr     edx, 8
0x18009320e  mov     [r15+rax], dl
0x180093212  lea     rax, cs:180000000h
0x180093219  add     r14d, ds:rva ?GlobalCase@SlowSource@Policy@Binary@@2V?$StripedCategory@H$03@Data@@B[rax+r8*4]; Data::StripedCategory<int,4> const Binary::Policy::SlowSource::GlobalCase ...
0x180093221  lea     eax, [rsi+1]
0x180093224  mov     rdx, [rsp+290h+var_220]
0x180093229  xor     esi, esi
0x18009322b  cmp     eax, 4
0x18009322e  cmovl   esi, eax
0x180093231  inc     r12d
0x180093234  inc     r15
0x180093237  test    esi, esi
0x180093239  jnz     loc_180093020
0x18009323f  mov     rbx, [rsp+290h+var_228]
0x180093244  xor     esi, esi
0x180093246  mov     r13d, dword ptr [rsp+290h+var_250]
0x18009324b  mov     rdi, [rsp+290h+var_230]
0x180093250  mov     dword ptr [rsp+290h+var_240], esi
0x180093254  mov     ecx, [rdi+0Ch]
0x180093257  lea     eax, [rcx-7]
0x18009325a  cmp     r12d, eax
0x18009325d  jge     loc_1800936F2
0x180093263  lea     rbx, cs:180000000h
0x18009326a  movsxd  rax, r13d
0x18009326d  shl     rax, 6
0x180093271  lea     rsi, rva word_1800DE482[rbx]
0x180093278  lea     rdx, rva ?OddOperation@SlowSource@Policy@Binary@@2V?$OneContext@V?$OneContext@G$07$00$0A@$0BA@@Data@@$03$00$0A@$0BAA@@Data@@B[rbx]; Data::OneContext<Data::OneContext<ushort,8,1,0,16>,4,1,0,256> const Binary::Policy::SlowSource::OddOperation ...
0x18009327f  movsxd  rcx, r14d
0x180093282  add     rdx, rax
0x180093285  lea     r8, rva byte_1800DE484[rbx]
0x18009328c  add     r8, rax
0x18009328f  mov     [rbp+190h+var_200], rdx
0x180093293  lea     r9, rva word_1800DE486[rbx]
0x18009329a  mov     [rbp+190h+var_1F8], r8
0x18009329e  add     r9, rax
0x1800932a1  lea     r10, rva byte_1800DE488[rbx]
0x1800932a8  add     r10, rax
0x1800932ab  mov     [rbp+190h+var_1F0], r9
0x1800932af  lea     r11, rva word_1800DE48A[rbx]
0x1800932b6  mov     [rsp+290h+var_218], r10
0x1800932bb  add     r11, rax
0x1800932be  lea     rdi, rva byte_1800DE48C[rbx]
0x1800932c5  add     rdi, rax
0x1800932c8  mov     [rbp+190h+var_210], r11
0x1800932cc  add     rsi, rax
0x1800932cf  mov     [rbp+190h+var_208], rdi
0x1800932d3  lea     rax, [rax+0DE48Eh]
0x1800932da  add     rax, rbx
0x1800932dd  lea     r13, [rcx+rcx]
0x1800932e1  mov     rbx, [rsp+290h+var_230]
0x1800932e6  mov     [rsp+290h+var_220], rax
0x1800932eb  nop     dword ptr [rax+rax+00h]
0x1800932f0  movsx   eax, word ptr [rsi]
0x1800932f3  mov     rcx, qword ptr [rbp+190h+var_F0]
0x1800932fa  movd    xmm4, eax
0x1800932fe  movsx   eax, word ptr [rdx]
  ... truncated ...
```
