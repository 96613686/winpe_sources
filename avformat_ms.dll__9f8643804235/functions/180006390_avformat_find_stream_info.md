# avformat_find_stream_info

- ea: `0x180006390`
- end: `0x1800078f6`
- name: `avformat_find_stream_info`
- size: `5478`
- prototype: ``
- caller_count: `0`
- callee_count: `46`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002e70`
- `0x1800049e0`
- `0x180006390`
- `0x180007dd8`
- `0x180008910`
- `0x180009154`
- `0x180009280`
- `0x18000952c`
- `0x180009840`
- `0x180009d9c`
- `0x180009e0c`
- `0x18000a054`
- `0x18000a20c`
- `0x18000a920`
- `0x18000b410`
- `0x18000b4f8`
- `0x18000b7f8`
- `0x18001b9f6`
- `0x18001ba14`
- `0x18001ba26`
- `0x18001ba2c`
- `0x18001ba3e`
- `0x18001ba44`
- `0x18001ba62`
- `0x18001ba68`
- `0x18001ba6e`
- `0x18001ba8c`
- `0x18001ba98`
- `0x18001ba9e`
- `0x18001baaa`
- `0x18001bae0`
- `0x18001baec`
- `0x18001bb58`
- `0x18001bb64`
- `0x18001bb6a`
- `0x18001bb82`
- `0x18001bba0`
- `0x18001bba6`
- `0x18001bbe8`
- `0x18001bc66`
- `0x18001bc8a`
- `0x18001bc96`
- `0x18001bdc0`
- `0x18001bdd2`
- `0x18001bdf6`
- `0x18001bed0`

## string_xrefs

- `0x180006613`: `threads`
- `0x1800064db`: `Before avformat_find_stream_info() pos: %lld bytes read:%lld seeks:%d nb_streams:%d\n`
- `0x1800066b8`: `Failed to open codec in %s\n`
- `0x180007005`: `Failed to open codec in %s\n`
- `0x1800070c0`: `Stream #%d: not enough frames to estimate rate; consider increasing probesize\n`
- `0x180007576`: `Could not find codec parameters for stream %d (%s): %s\nConsider increasing the value for the 'analyzeduration' (%lld) and 'probesize' (%lld) options\n`
- `0x1800078ae`: `After avformat_find_stream_info() pos: %lld bytes read:%lld seeks:%d frames:%d\n`

## pseudocode

```c
__int64 __fastcall avformat_find_stream_info(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  int v3; // r14d
  __int64 v6; // rcx
  const char *v7; // rax
  __int64 v8; // r15
  unsigned __int64 v9; // rsi
  const char **v10; // rcx
  int v11; // ebx
  const char *v12; // rcx
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rsi
  __int64 v16; // rax
  __int64 v17; // rbx
  __int64 v18; // r15
  __int64 v19; // rax
  int v20; // ecx
  const char *name; // rax
  __int64 v22; // r12
  __int64 *v23; // r14
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 *v26; // r8
  __int64 v27; // r13
  __int64 v28; // r12
  int v29; // esi
  __int64 v30; // rbx
  int v31; // eax
  int v32; // ecx
  __int64 v33; // r8
  __int64 v34; // rcx
  __int64 v35; // rdx
  int v36; // eax
  bool v37; // zf
  __int64 v38; // rsi
  int v39; // eax
  __int64 v40; // r15
  __int64 v41; // rbx
  __int64 v42; // r13
  __int64 v43; // rax
  int v44; // edx
  __int64 v45; // r8
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // r10
  int v49; // edx
  int v50; // r9d
  __int64 v51; // rcx
  __int64 v52; // r12
  __int64 v53; // rcx
  __int64 v54; // rdx
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // rax
  __int64 v58; // rcx
  __int64 v59; // rsi
  __int64 v60; // rcx
  signed __int64 v61; // rsi
  bool v62; // sf
  unsigned __int64 v63; // rsi
  __int64 v64; // rdx
  __int64 v65; // rdx
  __int64 v66; // r9
  __int64 v67; // rdx
  __int64 v68; // r9
  __int64 v69; // r8
  __int64 v70; // rax
  BOOL v71; // r10d
  __int64 v72; // rcx
  unsigned __int64 v73; // rcx
  __int64 v74; // rax
  int v75; // eax
  __int64 v76; // rax
  __int64 v77; // r9
  __int64 v78; // r15
  __int64 v79; // rbx
  __int64 v80; // r14
  __int64 v81; // rsi
  __int64 v82; // r9
  __int64 v83; // rbx
  __int64 v84; // r14
  __int64 v85; // rsi
  __int64 v86; // r12
  __int64 v87; // r13
  __int64 v88; // r8
  unsigned __int64 *v89; // r8
  __int64 v90; // r9
  __int64 i; // rbx
  __int64 v92; // rdx
  unsigned int v93; // r14d
  __int64 v94; // rsi
  __int64 v95; // r15
  unsigned int v96; // eax
  int v97; // ebx
  unsigned int v98; // r12d
  __int64 v99; // rcx
  __int64 v100; // r10
  __int64 v101; // rcx
  __int64 v102; // r9
  __int64 v103; // rbx
  double v104; // xmm6_8
  int v105; // r13d
  int j; // r12d
  int v107; // eax
  __int64 v108; // rcx
  double v109; // xmm7_8
  double v110; // xmm0_8
  double v111; // xmm0_8
  __int64 v112; // rax
  __int64 v113; // rcx
  __int64 v114; // rax
  __int64 v115; // rcx
  __int64 v116; // r8
  int v117; // r8d
  __int64 v118; // rcx
  __int64 v119; // rsi
  __int64 v120; // rbx
  _DWORD *v121; // rdx
  __int64 v122; // rsi
  __int64 v123; // rcx
  _QWORD *v124; // rax
  _QWORD *v125; // r12
  __int64 v126; // r13
  __int64 v127; // r15
  const char *v128; // rdx
  __int64 v129; // r8
  __int64 v130; // rax
  __int64 v131; // rbx
  __int64 v132; // rax
  __int64 v133; // rax
  __int64 k; // r15
  __int64 v135; // rbx
  __int64 v136; // rax
  __int64 *v137; // rsi
  __int64 v138; // rax
  __int64 v139; // rax
  __int64 v140; // rcx
  __int64 m; // rbx
  __int64 v142; // rsi
  __int64 v143; // rcx
  int v144; // eax
  __int64 v145; // rbx
  __int64 v146; // rax
  int v148; // [rsp+48h] [rbp-C0h]
  int v149; // [rsp+4Ch] [rbp-BCh]
  int v150; // [rsp+50h] [rbp-B8h]
  __int64 v151; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v152; // [rsp+60h] [rbp-A8h]
  unsigned int v153; // [rsp+68h] [rbp-A0h]
  BOOL v154; // [rsp+6Ch] [rbp-9Ch]
  unsigned __int64 v155; // [rsp+70h] [rbp-98h] BYREF
  __int64 v156; // [rsp+78h] [rbp-90h]
  const char *v157; // [rsp+80h] [rbp-88h] BYREF
  __int64 v158; // [rsp+88h] [rbp-80h]
  __int64 v159; // [rsp+90h] [rbp-78h]
  __int64 v160; // [rsp+98h] [rbp-70h]
  __int64 v161; // [rsp+A0h] [rbp-68h]
  __int64 v162; // [rsp+A8h] [rbp-60h]
  unsigned __int64 v163; // [rsp+B0h] [rbp-58h]
  __int64 v164; // [rsp+B8h] [rbp-50h]
  unsigned __int64 v165; // [rsp+C0h] [rbp-48h]
  __int64 v166; // [rsp+C8h] [rbp-40h]
  __int64 v167; // [rsp+D0h] [rbp-38h]
  __int64 v168; // [rsp+D8h] [rbp-30h]
  char v169[256]; // [rsp+E8h] [rbp-20h] BYREF

  v2 = *(_QWORD *)(a1 + 512);
  v3 = 0;
  v156 = a2;
  v149 = 0;
  v6 = *(_QWORD *)(a1 + 32);
  v158 = v2;
  v7 = (const char *)avio_seek(v6, 0, 1);
  v8 = *(_QWORD *)(a1 + 136);
  v9 = *(_QWORD *)(a1 + 144);
  v157 = v7;
  v153 = *(_DWORD *)(a1 + 44);
  v168 = v9;
  v159 = v8;
  v154 = v8 > 0;
  av_opt_set_int(a1, "skip_clear", 1);
  v155 = v9;
  v160 = v9;
  if ( !v9 )
  {
    v10 = *(const char ***)(a1 + 8);
    v168 = 5000000;
    v160 = 30000000;
    v11 = strcmp(*v10, "flv");
    if ( !strcmp(**(const char ***)(a1 + 8), "mpeg")
      || (v12 = **(const char ***)(a1 + 8),
          v155 = (-(__int64)(v11 != 0) & 0xFFFFFFFFFAEF00C0uLL) + 90000000,
          !strcmp(v12, "mpegts")) )
    {
      v155 = 7000000;
    }
  }
  v13 = *(_QWORD *)(a1 + 32);
  if ( v13 )
  {
    v14 = avio_seek(*(_QWORD *)(a1 + 32), 0, 1);
    av_log(
      a1,
      48,
      "Before avformat_find_stream_info() pos: %lld bytes read:%lld seeks:%d nb_streams:%d\n",
      v14,
      *(_QWORD *)(v13 + 232),
      *(_DWORD *)(v13 + 248),
      *(_DWORD *)(a1 + 44));
  }
  v15 = 0;
  if ( *(_DWORD *)(a1 + 44) )
  {
    do
    {
      v16 = *(_QWORD *)(a1 + 48);
      v151 = 0;
      v17 = *(_QWORD *)(v16 + 8 * v15);
      v18 = *(_QWORD *)(v17 + 248);
      if ( !*(_QWORD *)(v17 + 816) && (*(_BYTE *)(a1 + 128) & 0x20) == 0 && *(int *)(v17 + 352) <= 0 )
      {
        v19 = av_parser_init(*(unsigned int *)(*(_QWORD *)(v17 + 16) + 4LL));
        v20 = *(_DWORD *)(v17 + 808);
        *(_QWORD *)(v17 + 816) = v19;
        if ( v19 )
        {
          if ( v20 == 2 )
          {
            *(_DWORD *)(v19 + 184) |= 1u;
          }
          else if ( v20 == 5 )
          {
            *(_DWORD *)(v19 + 184) |= 0x1000u;
          }
        }
        else if ( v20 )
        {
          name = (const char *)avcodec_get_name(*(unsigned int *)(*(_QWORD *)(v17 + 16) + 4LL));
          av_log(a1, 40, "parser not found for codec %s, packets or times may be invalid.\n", name);
        }
      }
      v3 = avcodec_parameters_to_context(v18, *(_QWORD *)(v17 + 16));
      if ( v3 < 0 )
        goto LABEL_318;
      if ( *(int *)(v17 + 352) <= 0 )
        *(_DWORD *)(v17 + 256) = 1;
      v22 = sub_180009D9C(a1, v17, *(unsigned int *)(*(_QWORD *)(v17 + 16) + 4LL));
      v23 = &v151;
      if ( a2 )
        v23 = (__int64 *)(a2 + 8 * v15);
      av_dict_set(v23, "threads", "1", 0);
      av_dict_set(v23, "lowres", "0", 0);
      v24 = *(_QWORD *)(a1 + 336);
      if ( v24 )
        av_dict_set(v23, "codec_whitelist", v24, 0);
      if ( (!(unsigned int)sub_18000A054(v17, 0) && *(_DWORD *)(v17 + 352) <= (int)v25 || **(_DWORD **)(v17 + 16) == 3)
        && v22
        && *(_QWORD *)(v18 + 16) == v25 )
      {
        _mm_lfence();
        v26 = &v151;
        if ( a2 )
          v26 = (__int64 *)(a2 + 8 * v15);
        if ( (int)avcodec_open2(v18, v22, v26) < 0 )
        {
          _mm_lfence();
          av_log(a1, 24, "Failed to open codec in %s\n", "avformat_find_stream_info");
        }
      }
      if ( !a2 )
        av_dict_free(&v151);
      v15 = (unsigned int)(v15 + 1);
    }
    while ( (unsigned int)v15 < *(_DWORD *)(a1 + 44) );
    v8 = v159;
    v3 = 0;
  }
  v27 = 0;
  v152 = 0;
  if ( !(unsigned int)sub_180002E70(a1 + 216) )
  {
    while ( 1 )
    {
      v28 = 0;
      v150 = 0;
      if ( *(_DWORD *)(a1 + 44) )
      {
        do
        {
          v29 = 20;
          v30 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8 * v28);
          if ( !(unsigned int)sub_18000A054(v30, 0) )
            break;
          if ( (double)(int)*(_QWORD *)(v30 + 32) / (double)(int)HIDWORD(*(_QWORD *)(v30 + 32)) > 0.0005 )
            v29 = 40;
          v31 = sub_18000B410(a1, v30);
          v32 = *(_DWORD *)(a1 + 208);
          v33 = 0;
          if ( v32 < 0 )
            v32 = v31 != 0 ? v29 : 0;
          if ( (*(_DWORD *)(v30 + 64) & 0x400) == 0 )
            v33 = (unsigned int)v32;
          v34 = *(_QWORD *)(v30 + 312);
          v35 = *(char *)(*(_QWORD *)(a1 + 8) + 16LL) >= 0 ? *(unsigned int *)(v34 + 16) : *(_QWORD *)(v34 + 48) / 2LL;
          if ( (!*(_DWORD *)(v30 + 204) || !*(_DWORD *)(v30 + 88)) && !**(_DWORD **)(v30 + 16) && (int)v35 < (int)v33
            || *(_DWORD *)(v34 + 56) && (int)v35 < 2 && !*(_DWORD *)(*(_QWORD *)(v30 + 248) + 172LL)
            || !*(_QWORD *)(*(_QWORD *)(v30 + 248) + 72LL)
            && (!*(_DWORD *)(v30 + 272) || *(_QWORD *)(v30 + 264))
            && (unsigned int)sub_180009280(v30, v35, v33) )
          {
            break;
          }
          if ( *(_QWORD *)(v30 + 832) == 0x8000000000000000uLL
            && (*(char *)(*(_QWORD *)(a1 + 8) + 16LL) >= 0 || *(_DWORD *)(v30 + 808) == 5) )
          {
            v36 = 1;
            if ( (*(_DWORD *)(v30 + 64) & 0x400) == 0 )
              v36 = *(_DWORD *)(a1 + 256);
            if ( *(_DWORD *)(v30 + 824) < v36 && **(_DWORD **)(v30 + 16) < 2u )
              break;
          }
          v28 = (unsigned int)(v28 + 1);
        }
        while ( (unsigned int)v28 < *(_DWORD *)(a1 + 44) );
        v8 = v159;
        v3 = v149;
        v150 = v28;
      }
      LODWORD(v151) = 0;
      if ( (_DWORD)v28 == *(_DWORD *)(a1 + 44) && !*(_DWORD *)(a1 + 536) )
      {
        v37 = (*(_BYTE *)(a1 + 40) & 1) == 0;
        LODWORD(v151) = 1;
        if ( v37 )
        {
          v148 = v3;
          av_log(a1, 48, "All info found\n");
          goto LABEL_205;
        }
      }
      if ( v27 >= v8 )
      {
        _mm_lfence();
        v148 = v3;
        av_log(a1, 48, "Probe buffer size limit of %lld bytes reached\n", v8);
        for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 44); i = (unsigned int)(i + 1) )
        {
          v92 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8 * i);
          if ( !*(_DWORD *)(v92 + 204)
            && *(int *)(*(_QWORD *)(v92 + 312) + 16LL) <= 1
            && !**(_DWORD **)(v92 + 16)
            && strcmp(**(const char ***)(a1 + 8), "image2") )
          {
            av_log(a1, 24, "Stream #%d: not enough frames to estimate rate; consider increasing probesize\n", i);
          }
        }
        goto LABEL_163;
      }
      v38 = v158;
      v39 = sub_18000A920(a1, v158);
      v148 = v39;
      v3 = v39;
      if ( v39 != -11 )
        break;
      v3 = v149;
LABEL_161:
      if ( (unsigned int)sub_180002E70(a1 + 216) )
        goto LABEL_162;
    }
    if ( v39 < 0 )
    {
      v83 = 0;
      if ( *(_DWORD *)(a1 + 44) )
      {
        v84 = v156;
        do
        {
          v85 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8 * v83);
          v86 = *(_QWORD *)(v85 + 248);
          if ( !(unsigned int)sub_18000A054(v85, 0) )
          {
            v87 = sub_180009D9C(a1, v85, *(unsigned int *)(*(_QWORD *)(v85 + 16) + 4LL));
            if ( v87 )
            {
              if ( !*(_QWORD *)(v86 + 16) )
              {
                v88 = *(_QWORD *)(a1 + 336);
                v155 = 0;
                if ( v88 )
                  av_dict_set(&v155, "codec_whitelist", v88, 0);
                if ( !v84 || (v89 = (unsigned __int64 *)(v84 + 8 * v83), (unsigned int)v83 >= v153) )
                  v89 = &v155;
                if ( (int)avcodec_open2(v86, v87, v89) < 0 )
                {
                  _mm_lfence();
                  av_log(a1, 24, "Failed to open codec in %s\n", "avformat_find_stream_info");
                }
                av_dict_free(&v155);
              }
            }
          }
          if ( *(_QWORD *)(a1 + 480) && !(unsigned int)sub_18000A20C(v85) )
            sub_18000B7F8(a1, (unsigned int)v83, v90);
          v83 = (unsigned int)(v83 + 1);
        }
        while ( (unsigned int)v83 < *(_DWORD *)(a1 + 44) );
        v3 = v148;
      }
      goto LABEL_163;
    }
    if ( (*(_BYTE *)(a1 + 128) & 0x40) != 0 )
    {
      v40 = v38;
    }
    else
    {
      _mm_lfence();
      v148 = avpriv_packet_list_put(a1 + 480, v38, 0, 0);
      v3 = v148;
      if ( v148 < 0 )
        goto LABEL_173;
      _mm_lfence();
      v40 = *(_QWORD *)(a1 + 488) + 8LL;
    }
    _mm_lfence();
    v41 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL * *(int *)(v40 + 36));
    if ( (*(_DWORD *)(v41 + 64) & 0x400) == 0 )
      v152 = *(int *)(v40 + 32) + v27;
    v42 = *(_QWORD *)(v41 + 248);
    if ( !*(_DWORD *)(v41 + 256) )
    {
      v148 = avcodec_parameters_to_context(*(_QWORD *)(v41 + 248), *(_QWORD *)(v41 + 16));
      v3 = v148;
      if ( v148 < 0 )
        goto LABEL_173;
      *(_DWORD *)(v41 + 256) = 1;
    }
    v43 = *(_QWORD *)(v40 + 16);
    if ( v43 != 0x8000000000000000uLL )
    {
      v44 = *(_DWORD *)(v41 + 824);
      if ( v44 > 1 )
      {
        v45 = *(_QWORD *)(v41 + 312);
        v46 = *(_QWORD *)(v45 + 88);
        if ( v46 != 0x8000000000000000uLL && v46 >= v43 )
        {
          _mm_lfence();
          av_log(
            a1,
            48,
            "Non-increasing DTS in stream %d: packet %d with DTS %lld, packet %d with DTS %lld\n",
            *(_DWORD *)(v41 + 8),
            *(_DWORD *)(v45 + 96),
            v46,
            v44,
            *(_QWORD *)(v40 + 16));
          *(_QWORD *)(*(_QWORD *)(v41 + 312) + 88LL) = 0x8000000000000000uLL;
          *(_QWORD *)(*(_QWORD *)(v41 + 312) + 72LL) = 0x8000000000000000uLL;
        }
        v47 = *(_QWORD *)(v41 + 312);
        v48 = *(_QWORD *)(v47 + 88);
        if ( v48 != 0x8000000000000000uLL )
        {
          v49 = *(_DWORD *)(v47 + 80);
          v50 = *(_DWORD *)(v47 + 96);
          if ( v50 > v49
            && (*(_QWORD *)(v40 + 16) - v48) / 0x3E8uLL > (v48 - *(_QWORD *)(v47 + 72)) / (unsigned __int64)(v50 - v49) )
          {
            _mm_lfence();
            av_log(
              a1,
              24,
              "DTS discontinuity in stream %d: packet %d with DTS %lld, packet %d with DTS %lld\n",
              *(_DWORD *)(v41 + 8),
              v50,
              v48,
              *(_DWORD *)(v41 + 824),
              *(_QWORD *)(v40 + 16));
            *(_QWORD *)(*(_QWORD *)(v41 + 312) + 88LL) = 0x8000000000000000uLL;
            *(_QWORD *)(*(_QWORD *)(v41 + 312) + 72LL) = 0x8000000000000000uLL;
          }
        }
        v51 = *(_QWORD *)(v41 + 312);
        if ( *(_QWORD *)(v51 + 72) == 0x8000000000000000uLL )
        {
          *(_QWORD *)(v51 + 72) = *(_QWORD *)(v40 + 16);
          *(_DWORD *)(*(_QWORD *)(v41 + 312) + 80LL) = *(_DWORD *)(v41 + 824);
        }
        *(_QWORD *)(*(_QWORD *)(v41 + 312) + 88LL) = *(_QWORD *)(v40 + 16);
        *(_DWORD *)(*(_QWORD *)(v41 + 312) + 96LL) = *(_DWORD *)(v41 + 824);
      }
    }
    if ( *(int *)(v41 + 824) <= 1 )
    {
LABEL_146:
      if ( !**(_DWORD **)(v41 + 16) )
      {
        _mm_lfence();
        sub_18000952C(a1, v41, *(_QWORD *)(v40 + 16));
        v76 = *(_QWORD *)(v40 + 8);
        if ( *(_QWORD *)(v40 + 16) != v76
          && *(_QWORD *)(v40 + 16) != 0x8000000000000000uLL
          && v76 != 0x8000000000000000uLL )
        {
          *(_DWORD *)(*(_QWORD *)(v41 + 312) + 56LL) = 1;
        }
      }
      if ( !*(_QWORD *)(*(_QWORD *)(v41 + 248) + 72LL) )
      {
        _mm_lfence();
        v3 = sub_180009154(a1, v41, v40);
        if ( v3 < 0 )
        {
LABEL_173:
          _mm_lfence();
          av_packet_unref(v38);
          goto LABEL_318;
        }
      }
      _mm_lfence();
      if ( v156 && (unsigned int)v28 < v153 )
        v77 = v156 + 8LL * (unsigned int)v28;
      else
        v77 = 0;
      sub_18000B4F8(a1, v41, v40, v77);
      if ( (*(_BYTE *)(a1 + 128) & 0x40) != 0 )
      {
        _mm_lfence();
        av_packet_unref(v38);
      }
      ++*(_DWORD *)(v41 + 824);
      v27 = v152;
      v3 = v149 + 1;
      v8 = v159;
      ++v149;
      goto LABEL_161;
    }
    v52 = 0;
    if ( *(int *)(v41 + 36) > 0 )
    {
      v53 = *(_QWORD *)(v41 + 312);
      v54 = *(_QWORD *)(v41 + 32);
      v161 = 0xF424000000001LL;
      v52 = av_rescale_q(*(_QWORD *)(v53 + 40), v54, 0xF424000000001LL);
    }
    if ( *(int *)(v41 + 88) > 0 )
    {
      v55 = *(_QWORD *)(v41 + 88);
      v56 = *(int *)(v41 + 824);
      v163 = __PAIR64__(v55, HIDWORD(v55));
      v162 = 0xF424000000001LL;
      if ( v52 <= av_rescale_q(v56, __PAIR64__(v55, HIDWORD(v55)), 0xF424000000001LL) )
      {
        v57 = *(_QWORD *)(v41 + 88);
        v165 = __PAIR64__(v57, HIDWORD(v57));
        v58 = *(int *)(v41 + 824);
        v164 = 0xF424000000001LL;
        v52 = av_rescale_q(v58, __PAIR64__(v57, HIDWORD(v57)), 0xF424000000001LL);
      }
    }
    if ( !v52 && *(int *)(v41 + 824) > 30 )
    {
      v59 = *(_QWORD *)(v41 + 312);
      v60 = *(_QWORD *)(v59 + 72);
      if ( v60 != 0x8000000000000000uLL )
      {
        v61 = *(_QWORD *)(v59 + 88);
        if ( v61 != 0x8000000000000000uLL )
        {
          v62 = v60 < 0;
          if ( v60 <= 0 )
          {
            if ( v61 >= v60 + 0x7FFFFFFFFFFFFFFFLL )
            {
              v63 = 0x7FFFFFFFFFFFFFFFLL;
LABEL_115:
              v64 = *(_QWORD *)(v41 + 32);
              v166 = 0xF424000000001LL;
              if ( av_rescale_q(v63, v64, 0xF424000000001LL) >= 0 )
              {
                _mm_lfence();
                v65 = *(_QWORD *)(v41 + 32);
                v167 = 0xF424000000001LL;
                v52 = av_rescale_q(v63, v65, 0xF424000000001LL);
              }
              v38 = v158;
              goto LABEL_118;
            }
            v62 = v60 < 0;
          }
          if ( v62 || v61 > (__int64)(v60 + 0x8000000000000000uLL) )
            v63 = v61 - v60;
          else
            v63 = 0x8000000000000000uLL;
          goto LABEL_115;
        }
      }
      v38 = v158;
    }
LABEL_118:
    if ( (_DWORD)v151 )
    {
      v66 = v168;
    }
    else
    {
      v66 = v155;
      if ( *(_DWORD *)(v42 + 12) == 3 )
        v66 = v160;
    }
    if ( v52 >= v66 )
    {
      _mm_lfence();
      av_log(a1, 40, "max_analyze_duration %lld reached at %lld microseconds st:%d\n", v66, v52, *(_DWORD *)(v40 + 36));
      if ( (*(_BYTE *)(a1 + 128) & 0x40) != 0 )
      {
        _mm_lfence();
        av_packet_unref(v38);
      }
      goto LABEL_163;
    }
    v67 = *(_QWORD *)(v40 + 64);
    if ( v67 > 0 )
    {
      v68 = *(_QWORD *)(v41 + 312);
      v69 = *(_QWORD *)(v68 + 40);
      if ( v67 < 0x7FFFFFFFFFFFFFFFLL - v69 )
      {
        v70 = *(_QWORD *)(v41 + 848);
        v71 = v70 && (*(_BYTE *)(v70 + 24) & 0x10) != 0;
        if ( *(_DWORD *)(v42 + 12) != 3
          || (v72 = *(_QWORD *)(v40 + 8), v72 == 0x8000000000000000uLL)
          || *(_QWORD *)(v41 + 40) == 0x8000000000000000uLL
          || v72 < *(_QWORD *)(v41 + 40)
          || (v73 = v72 - *(_QWORD *)(v41 + 40), v73 >= 0x7FFFFFFFFFFFFFFFLL) )
        {
          v73 = v69 + v67;
        }
        else if ( (__int64)v73 > v69 + v67 )
        {
          v73 = v69 + v67;
        }
        *(_QWORD *)(v68 + 40) = v73;
        v74 = *(_QWORD *)(v41 + 816);
        if ( v74 && *(_DWORD *)(v41 + 808) && v71 )
          v75 = *(_DWORD *)(v74 + 44) + 1;
        else
          v75 = 2;
        *(_QWORD *)(*(_QWORD *)(v41 + 312) + 48LL) += v75;
      }
    }
    LODWORD(v28) = v150;
    goto LABEL_146;
  }
LABEL_162:
  v3 = -1414092869;
  v148 = -1414092869;
  av_log(a1, 48, "interrupted\n");
LABEL_163:
  if ( v154 )
  {
    v78 = *(_QWORD *)(a1 + 512);
    av_packet_unref(v78);
    v79 = 0;
    if ( *(_DWORD *)(a1 + 44) )
    {
      v80 = v156;
      do
      {
        v81 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8 * v79);
        if ( *(_DWORD *)(*(_QWORD *)(v81 + 312) + 60LL) == 1 )
        {
          v82 = v80 && (unsigned int)v79 < v153 ? v80 + 8 * v79 : 0LL;
          if ( (int)sub_18000B4F8(a1, *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8 * v79), v78, v82) < 0 )
          {
            _mm_lfence();
            av_log(a1, 32, "decoding for stream %d failed\n", *(_DWORD *)(v81 + 8));
          }
        }
        v79 = (unsigned int)(v79 + 1);
      }
      while ( (unsigned int)v79 < *(_DWORD *)(a1 + 44) );
      v3 = v148;
    }
  }
LABEL_205:
  sub_180009840(a1);
  v37 = *(_DWORD *)(a1 + 44) == 0;
  v154 = 0;
  if ( v37 )
    goto LABEL_262;
  v93 = v154;
  do
  {
    v94 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL * v93);
    v95 = *(_QWORD *)(v94 + 248);
    if ( !*(_DWORD *)(v95 + 12) )
    {
      if ( *(_DWORD *)(v95 + 24) == 13 && !*(_DWORD *)(v95 + 28) && !*(_DWORD *)(v95 + 648) )
      {
        v96 = avcodec_pix_fmt_to_codec_tag(*(unsigned int *)(v95 + 136));
        v97 = *(_DWORD *)(v95 + 136);
        v98 = v96;
        if ( (unsigned int)avpriv_pix_fmt_find(0, v96) == v97 )
          *(_DWORD *)(v95 + 28) = v98;
      }
      v99 = *(_QWORD *)(v94 + 312);
      v100 = *(_QWORD *)(v99 + 48);
      if ( v100 )
      {
        if ( !*(_DWORD *)(v94 + 88) )
        {
          v101 = *(_QWORD *)(v99 + 40);
          if ( v101 )
          {
            v102 = *(int *)(v94 + 32);
            v103 = *(_QWORD *)(v95 + 100);
            v104 = 0.01;
            v105 = 0;
            v160 = v103;
            if ( v101 >= 0x7FFFFFFFFFFFFFFFLL / v102 / 2
              || v100 >= 0x7FFFFFFFFFFFFFFFLL / *(int *)(v94 + 36)
              || v101 < 0 )
            {
              goto LABEL_260;
            }
            _mm_lfence();
            av_reduce(v94 + 88, v94 + 92, v100 * *(int *)(v94 + 36), 2 * v101 * v102, 60000);
            for ( j = 0; j < 399; ++j )
            {
              v107 = sub_180009E0C((unsigned int)j);
              v108 = *(_QWORD *)(v94 + 88);
              LODWORD(v151) = v107;
              v109 = (double)v107 / 12012.0;
              v110 = fabs((double)(int)v108 / (double)SHIDWORD(v108) / v109 - 1.0);
              if ( v104 > v110 )
              {
                v105 = v151;
                v104 = v110;
              }
              if ( (*(_BYTE *)(*(_QWORD *)(a1 + 8) + 64LL) & 2) != 0 && (int)v103 > 0 && SHIDWORD(v160) > 0 )
              {
                v111 = fabs((double)(int)v103 / (double)SHIDWORD(v160) / v109 - 1.0);
                if ( v104 > v111 )
                {
                  v105 = v151;
                  v104 = v111;
                }
              }
            }
            if ( v105 )
              av_reduce(v94 + 88, v94 + 92, v105, 12012, 0x7FFFFFFF);
          }
        }
      }
      if ( *(_DWORD *)(v94 + 204) )
        goto LABEL_244;
      v112 = *(_QWORD *)(v94 + 848);
      if ( !v112 || (v37 = (*(_BYTE *)(v112 + 24) & 0x10) == 0, LODWORD(v156) = 2, v37) )
        LODWORD(v156) = 1;
      v113 = *(_QWORD *)(v95 + 100);
      HIDWORD(v156) = 1;
      v114 = av_mul_q(v113, v156);
      if ( (_DWORD)v114 && HIDWORD(v114) )
      {
        v115 = *(_QWORD *)(v94 + 32);
        v116 = (int)v114 * (__int64)(int)v115 - SHIDWORD(v115) * (__int64)SHIDWORD(v114);
        if ( v116 )
        {
          v117 = ((int)v114 >> 31) ^ (SHIDWORD(v115) >> 31) ^ (v116 >> 63) | 1;
        }
        else
        {
          if ( HIDWORD(v115) || !(_DWORD)v115 )
            goto LABEL_242;
          v117 = ((int)v115 >> 31) - (SHIDWORD(v114) >> 31);
        }
        if ( v117 <= 0 )
        {
LABEL_242:
          *(_QWORD *)(v94 + 204) = v114;
LABEL_244:
          *(_QWORD *)(*(_QWORD *)(v94 + 16) + 88LL) = *(_QWORD *)(v95 + 100);
          if ( *(_DWORD *)(v94 + 740) && *(_DWORD *)(v94 + 744) )
          {
            v118 = *(_QWORD *)(v94 + 740);
            LODWORD(v152) = *(_DWORD *)(v95 + 116);
            HIDWORD(v152) = *(_DWORD *)(v95 + 112);
            *(_QWORD *)(v94 + 72) = av_mul_q(v118, v152);
          }
          goto LABEL_260;
        }
      }
      *(_DWORD *)(v94 + 204) = *(_DWORD *)(v94 + 36);
      *(_DWORD *)(v94 + 208) = *(_DWORD *)(v94 + 32);
      goto LABEL_244;
    }
    if ( *(_DWORD *)(v95 + 12) == 1 )
    {
      if ( !*(_DWORD *)(v95 + 648) )
        *(_DWORD *)(v95 + 648) = av_get_bits_per_sample(*(unsigned int *)(v95 + 24));
      switch ( *(_DWORD *)(v95 + 388) )
      {
        case 1:
          *(_DWORD *)(v94 + 64) = 512;
          break;
        case 2:
          *(_DWORD *)(v94 + 64) = 256;
          break;
        case 3:
          *(_DWORD *)(v94 + 64) = 128;
          break;
        case 5:
          *(_DWORD *)(v94 + 64) = 8;
          break;
        case 8:
          *(_DWORD *)(v94 + 64) = 32;
          break;
      }
    }
LABEL_260:
    ++v93;
  }
  while ( v93 < *(_DWORD *)(a1 + 44) );
  v3 = v148;
LABEL_262:
  if ( v159 )
    sub_180008910(a1, v157);
  av_opt_set_int(a1, "skip_clear", 0);
  if ( v3 >= 0 )
  {
    if ( *(_DWORD *)(a1 + 44) )
      v3 = -1;
    v148 = v3;
  }
  v119 = 0;
  if ( *(_DWORD *)(a1 + 44) )
  {
    while ( 1 )
    {
      v120 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8 * v119);
      if ( !*(_DWORD *)(v120 + 256) )
      {
        v121 = *(_DWORD **)(v120 + 16);
        if ( *v121 == 1 && v121[11] == -1 )
          v121[11] = *(_DWORD *)(*(_QWORD *)(v120 + 248) + 348LL);
        v148 = avcodec_parameters_to_context(*(_QWORD *)(v120 + 248), *(_QWORD *)(v120 + 16));
        v3 = v148;
        if ( v148 < 0 )
          break;
      }
      if ( (unsigned int)sub_18000A054(v120, &v157) )
      {
        v3 = 0;
        v148 = 0;
      }
      else
      {
        avcodec_string(v169, 256, *(_QWORD *)(v120 + 248), 0);
        av_log(
          a1,
          24,
          "Could not find codec parameters for stream %d (%s): %s\n"
          "Consider increasing the value for the 'analyzeduration' (%lld) and 'probesize' (%lld) options\n",
          v119,
          v169,
          v157,
          *(_QWORD *)(a1 + 144),
          *(_QWORD *)(a1 + 136));
      }
      v119 = (unsigned int)(v119 + 1);
      if ( (unsigned int)v119 >= *(_DWORD *)(a1 + 44) )
        goto LABEL_278;
    }
  }
  else
  {
LABEL_278:
    v122 = 0;
    if ( *(_DWORD *)(a1 + 72) )
    {
      v123 = *(_QWORD *)(a1 + 104);
      if ( v123 > 0 && *(_QWORD *)(a1 + 96) < 0x7FFFFFFFFFFFFFFFLL - v123 )
      {
        if ( *(_QWORD *)(a1 + 96) != 0x8000000000000000uLL )
          v122 = *(_QWORD *)(a1 + 96);
        v122 += v123;
      }
      v124 = (_QWORD *)av_memdup(*(_QWORD *)(a1 + 80), 8LL * *(unsigned int *)(a1 + 72));
      v125 = v124;
      if ( !v124 )
      {
        v3 = -12;
        goto LABEL_318;
      }
      qsort(v124, *(unsigned int *)(a1 + 72), 8u, CompareFunction);
      v126 = 0;
      if ( *(_DWORD *)(a1 + 72) )
      {
        do
        {
          v127 = v125[v126];
          if ( *(_QWORD *)(v127 + 24) == 0x8000000000000000uLL )
          {
            v128 = (const char *)(v127 + 8);
            v157 = (const char *)(v127 + 8);
            if ( v122 )
            {
              v129 = *(_QWORD *)v128;
              v152 = 0xF424000000001LL;
              v130 = av_rescale_q(v122, 0xF424000000001LL, v129);
              v128 = v157;
              v131 = v130;
            }
            else
            {
              v131 = 0x7FFFFFFFFFFFFFFFLL;
            }
            v132 = (unsigned int)(v126 + 1);
            if ( (unsigned int)v132 < *(_DWORD *)(a1 + 72) )
            {
              v133 = av_rescale_q(*(_QWORD *)(v125[v132] + 16LL), *(_QWORD *)(v125[v132] + 8LL), *(_QWORD *)v128);
              if ( v133 > *(_QWORD *)(v127 + 16) && v133 < v131 )
                v131 = v133;
            }
            if ( v131 == 0x7FFFFFFFFFFFFFFFLL || v131 < *(_QWORD *)(v127 + 16) )
              v131 = *(_QWORD *)(v127 + 16);
            *(_QWORD *)(v127 + 24) = v131;
          }
          v126 = (unsigned int)(v126 + 1);
        }
        while ( (unsigned int)v126 < *(_DWORD *)(a1 + 72) );
        v3 = v148;
      }
      av_free(v125);
    }
    for ( k = 0; (unsigned int)k < *(_DWORD *)(a1 + 44); *(_DWORD *)(v135 + 256) = 0 )
    {
      v135 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8 * k);
      if ( *(_DWORD *)(v135 + 256) )
      {
        v3 = avcodec_parameters_from_context(*(_QWORD *)(v135 + 16), *(_QWORD *)(v135 + 248));
        if ( v3 < 0 )
          break;
        v136 = *(_QWORD *)(v135 + 248);
        if ( *(int *)(v136 + 448) > 0 || *(__int64 *)(v136 + 464) > 0 || *(_QWORD *)(v136 + 472) )
        {
          v137 = (__int64 *)av_cpb_properties_alloc(&v157);
          if ( v137 )
          {
            v138 = *(int *)(*(_QWORD *)(v135 + 248) + 448LL);
            if ( (int)v138 > 0 )
              v137[3] = v138;
            v139 = *(_QWORD *)(*(_QWORD *)(v135 + 248) + 472LL);
            if ( v139 > 0 )
              v137[1] = v139;
            v140 = *(_QWORD *)(*(_QWORD *)(v135 + 248) + 464LL);
            if ( v140 > 0 )
              *v137 = v140;
            if ( !av_packet_side_data_add(
                    *(_QWORD *)(v135 + 16) + 32LL,
                    *(_QWORD *)(v135 + 16) + 40LL,
                    10,
                    v137,
                    v157,
                    0) )
              av_free(v137);
          }
        }
      }
      k = (unsigned int)(k + 1);
    }
  }
LABEL_318:
  for ( m = 0; (unsigned int)m < *(_DWORD *)(a1 + 44); m = (unsigned int)(m + 1) )
  {
    v142 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8 * m);
    v143 = *(_QWORD *)(v142 + 312);
    if ( v143 )
    {
      av_freep(v143 + 32);
      av_freep(v142 + 312);
    }
    if ( (unsigned int)avcodec_is_open(*(_QWORD *)(v142 + 248)) )
    {
      v144 = sub_180007DD8(v142);
      if ( v144 < 0 && v3 >= 0 )
        v3 = v144;
    }
    av_bsf_free(v142 + 264);
  }
  v145 = *(_QWORD *)(a1 + 32);
  if ( v145 )
  {
    v146 = avio_seek(*(_QWORD *)(a1 + 32), 0, 1);
    av_log(
      a1,
      48,
      "After avformat_find_stream_info() pos: %lld bytes read:%lld seeks:%d frames:%d\n",
      v146,
      *(_QWORD *)(v145 + 232),
      *(_DWORD *)(v145 + 248),
      v149);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180006390  mov     rax, rsp
0x180006393  mov     [rax+18h], rbx
0x180006397  push    rbp
0x180006398  push    rsi
0x180006399  push    rdi
0x18000639a  push    r12
0x18000639c  push    r13
0x18000639e  push    r14
0x1800063a0  push    r15
0x1800063a2  lea     rbp, [rax-158h]
0x1800063a9  sub     rsp, 220h
0x1800063b0  movaps  xmmword ptr [rax-48h], xmm6
0x1800063b4  movaps  xmmword ptr [rax-58h], xmm7
0x1800063b8  movaps  xmmword ptr [rax-68h], xmm8
0x1800063bd  mov     rax, cs:__security_cookie
0x1800063c4  xor     rax, rsp
0x1800063c7  mov     [rbp+150h+var_70], rax
0x1800063ce  mov     rax, [rcx+200h]
0x1800063d5  xor     r14d, r14d
0x1800063d8  mov     r13, rdx
0x1800063db  mov     [rsp+250h+var_1E0], rdx
0x1800063e0  mov     rdi, rcx
0x1800063e3  mov     [rsp+250h+var_20C], r14d
0x1800063e8  mov     rcx, [rcx+20h]
0x1800063ec  xor     edx, edx
0x1800063ee  lea     r8d, [r14+1]
0x1800063f2  mov     [rbp+150h+var_1D0], rax
0x1800063f6  call    avio_seek
0x1800063fb  mov     r15, [rdi+88h]
0x180006402  lea     r9d, [r14+1]
0x180006406  mov     rsi, [rdi+90h]
0x18000640d  lea     rdx, aSkipClear; "skip_clear"
0x180006414  mov     [rsp+250h+var_1D8], rax
0x180006419  mov     r8d, r9d
0x18000641c  mov     eax, [rdi+2Ch]
0x18000641f  mov     rcx, rdi
0x180006422  mov     dword ptr [rsp+250h+var_1F0], eax
0x180006426  xor     eax, eax
0x180006428  test    r15, r15
0x18000642b  mov     [rbp+150h+var_180], rsi
0x18000642f  mov     [rbp+150h+var_1C8], r15
0x180006433  setnle  al
0x180006436  mov     dword ptr [rsp+250h+var_1F0+4], eax
0x18000643a  call    av_opt_set_int
0x18000643f  mov     [rsp+250h+var_1E8], rsi
0x180006444  mov     [rbp+150h+var_1C0], rsi
0x180006448  test    rsi, rsi
0x18000644b  jnz     short loc_1800064C1
0x18000644d  mov     rcx, [rdi+8]
0x180006451  lea     rdx, aFlv; "flv"
0x180006458  mov     [rbp+150h+var_180], 4C4B40h
0x180006460  mov     [rbp+150h+var_1C0], 1C9C380h
0x180006468  mov     rcx, [rcx]; Str1
0x18000646b  call    strcmp
0x180006470  mov     rcx, [rdi+8]
0x180006474  lea     rdx, aMpeg; "mpeg"
0x18000647b  mov     ebx, eax
0x18000647d  mov     rcx, [rcx]; Str1
0x180006480  call    strcmp
0x180006485  test    eax, eax
0x180006487  jz      short loc_1800064B8
0x180006489  mov     rcx, [rdi+8]
0x18000648d  lea     rdx, aMpegts; "mpegts"
0x180006494  neg     ebx
0x180006496  sbb     rsi, rsi
0x180006499  mov     rcx, [rcx]; Str1
0x18000649c  and     rsi, 0FFFFFFFFFAEF00C0h
0x1800064a3  add     rsi, 55D4A80h
0x1800064aa  mov     [rsp+250h+var_1E8], rsi
0x1800064af  call    strcmp
0x1800064b4  test    eax, eax
0x1800064b6  jnz     short loc_1800064C1
0x1800064b8  mov     [rsp+250h+var_1E8], 6ACFC0h
0x1800064c1  mov     rbx, [rdi+20h]
0x1800064c5  test    rbx, rbx
0x1800064c8  jz      short loc_18000650C
0x1800064ca  xor     edx, edx
0x1800064cc  mov     rcx, rbx
0x1800064cf  lea     r8d, [rdx+1]
0x1800064d3  call    avio_seek
0x1800064d8  mov     ecx, [rdi+2Ch]
0x1800064db  lea     r8, aBeforeAvformat; "Before avformat_find_stream_info() pos:"...
0x1800064e2  mov     dword ptr [rsp+250h+var_220], ecx
0x1800064e6  mov     r9, rax
0x1800064e9  mov     ecx, [rbx+0F8h]
0x1800064ef  mov     edx, 30h ; '0'
0x1800064f4  mov     dword ptr [rsp+250h+var_228], ecx
0x1800064f8  mov     rcx, [rbx+0E8h]
0x1800064ff  mov     [rsp+250h+var_230], rcx
0x180006504  mov     rcx, rdi
0x180006507  call    av_log
0x18000650c  xor     esi, esi
0x18000650e  lea     r12d, [rsi+28h]
0x180006512  cmp     [rdi+2Ch], esi
0x180006515  jbe     loc_1800066F0
0x18000651b  mov     rax, [rdi+30h]
0x18000651f  mov     [rsp+250h+var_200], 0
0x180006528  mov     rbx, [rax+rsi*8]
0x18000652c  cmp     qword ptr [rbx+330h], 0
0x180006534  mov     r15, [rbx+0F8h]
0x18000653b  jnz     short loc_1800065AF
0x18000653d  test    byte ptr [rdi+80h], 20h
0x180006544  jnz     short loc_1800065AF
0x180006546  cmp     dword ptr [rbx+160h], 0
0x18000654d  jg      short loc_1800065AF
0x18000654f  mov     rcx, [rbx+10h]
0x180006553  mov     ecx, [rcx+4]
0x180006556  call    av_parser_init
0x18000655b  mov     ecx, [rbx+328h]
0x180006561  mov     [rbx+330h], rax
0x180006568  test    rax, rax
0x18000656b  jz      short loc_18000658A
0x18000656d  cmp     ecx, 2
0x180006570  jnz     short loc_18000657B
0x180006572  or      dword ptr [rax+0B8h], 1
0x180006579  jmp     short loc_1800065AF
0x18000657b  cmp     ecx, 5
0x18000657e  jnz     short loc_1800065AF
0x180006580  bts     dword ptr [rax+0B8h], 0Ch
0x180006588  jmp     short loc_1800065AF
0x18000658a  test    ecx, ecx
0x18000658c  jz      short loc_1800065AF
0x18000658e  mov     rcx, [rbx+10h]
0x180006592  mov     ecx, [rcx+4]
0x180006595  call    avcodec_get_name
0x18000659a  mov     r9, rax
0x18000659d  lea     r8, aParserNotFound; "parser not found for codec %s, packets "...
0x1800065a4  mov     edx, r12d
0x1800065a7  mov     rcx, rdi
0x1800065aa  call    av_log
0x1800065af  mov     rdx, [rbx+10h]
0x1800065b3  mov     rcx, r15
0x1800065b6  call    avcodec_parameters_to_context
0x1800065bb  mov     r14d, eax
0x1800065be  test    eax, eax
0x1800065c0  js      loc_180007807
0x1800065c6  cmp     dword ptr [rbx+160h], 0
0x1800065cd  jg      short loc_1800065D9
0x1800065cf  mov     dword ptr [rbx+100h], 1
0x1800065d9  mov     r8, [rbx+10h]
0x1800065dd  mov     rdx, rbx
0x1800065e0  mov     rcx, rdi
0x1800065e3  mov     r8d, [r8+4]
0x1800065e7  call    sub_180009D9C
0x1800065ec  lea     rdx, ds:0[rsi*8]
0x1800065f4  mov     r12, rax
0x1800065f7  add     rdx, r13
0x1800065fa  lea     r14, [rsp+250h+var_200]
0x1800065ff  test    r13, r13
0x180006602  lea     r8, a1; "1"
0x180006609  cmovnz  r14, rdx
0x18000660d  xor     r9d, r9d
0x180006610  mov     rcx, r14
0x180006613  lea     rdx, aThreads; "threads"
0x18000661a  call    av_dict_set
0x18000661f  xor     r9d, r9d
0x180006622  lea     r8, a0; "0"
0x180006629  lea     rdx, aLowres; "lowres"
0x180006630  mov     rcx, r14
0x180006633  call    av_dict_set
0x180006638  mov     r8, [rdi+150h]
0x18000663f  test    r8, r8
0x180006642  jz      short loc_180006656
0x180006644  xor     r9d, r9d
0x180006647  lea     rdx, aCodecWhitelist; "codec_whitelist"
0x18000664e  mov     rcx, r14
0x180006651  call    av_dict_set
0x180006656  xor     edx, edx
0x180006658  mov     rcx, rbx
0x18000665b  call    sub_18000A054
0x180006660  test    eax, eax
0x180006662  jnz     short loc_18000666C
0x180006664  cmp     [rbx+160h], edx
0x18000666a  jle     short loc_180006675
0x18000666c  mov     rax, [rbx+10h]
0x180006670  cmp     dword ptr [rax], 3
0x180006673  jnz     short loc_1800066C7
0x180006675  test    r12, r12
0x180006678  jz      short loc_1800066C7
0x18000667a  cmp     [r15+10h], rdx
0x18000667e  jnz     short loc_1800066C7
0x180006680  lfence
0x180006683  lea     rcx, ds:0[rsi*8]
0x18000668b  mov     rdx, r12
0x18000668e  add     rcx, r13
0x180006691  lea     r8, [rsp+250h+var_200]
0x180006696  test    r13, r13
0x180006699  cmovnz  r8, rcx
0x18000669d  mov     rcx, r15
0x1800066a0  call    avcodec_open2
0x1800066a5  test    eax, eax
0x1800066a7  jns     short loc_1800066C7
0x1800066a9  lfence
0x1800066ac  lea     r9, aAvformatFindSt_0; "avformat_find_stream_info"
0x1800066b3  mov     edx, 18h
0x1800066b8  lea     r8, aFailedToOpenCo; "Failed to open codec in %s\n"
0x1800066bf  mov     rcx, rdi
0x1800066c2  call    av_log
0x1800066c7  test    r13, r13
0x1800066ca  jnz     short loc_1800066D6
0x1800066cc  lea     rcx, [rsp+250h+var_200]
0x1800066d1  call    av_dict_free
0x1800066d6  inc     esi
0x1800066d8  mov     r12d, 28h ; '('
0x1800066de  cmp     esi, [rdi+2Ch]
0x1800066e1  jb      loc_18000651B
0x1800066e7  mov     r15, [rbp+150h+var_1C8]
0x1800066eb  mov     r14d, [rsp+250h+var_20C]
0x1800066f0  xor     r13d, r13d
0x1800066f3  lea     rcx, [rdi+0D8h]
0x1800066fa  mov     [rsp+250h+var_1F8], r13
0x1800066ff  call    sub_180002E70
0x180006704  test    eax, eax
0x180006706  jnz     loc_180006E69
0x18000670c  movsd   xmm6, cs:qword_180021760
0x180006714  xor     r12d, r12d
0x180006717  xor     esi, esi
0x180006719  mov     dword ptr [rsp+250h+var_208], r12d
0x18000671e  cmp     [rdi+2Ch], esi
0x180006721  jbe     loc_180006893
0x180006727  mov     r14, 8000000000000000h
0x180006731  lea     r15d, [r12+28h]
0x180006736  mov     rax, [rdi+30h]
0x18000673a  xor     edx, edx
0x18000673c  mov     esi, 14h
0x180006741  mov     rbx, [rax+r12*8]
0x180006745  mov     rcx, rbx
0x180006748  call    sub_18000A054
0x18000674d  test    eax, eax
0x18000674f  jz      loc_180006883
0x180006755  mov     rax, [rbx+20h]
0x180006759  mov     rdx, rbx
0x18000675c  mov     rcx, rdi
0x18000675f  movd    xmm1, eax
0x180006763  shr     rax, 20h
0x180006767  cvtdq2pd xmm1, xmm1
0x18000676b  movd    xmm0, eax
0x18000676f  cvtdq2pd xmm0, xmm0
0x180006773  divsd   xmm1, xmm0
0x180006777  comisd  xmm1, xmm6
0x18000677b  cmova   esi, r15d
0x18000677f  call    sub_18000B410
0x180006784  mov     ecx, [rdi+0D0h]
0x18000678a  neg     eax
0x18000678c  mov     rax, [rdi+8]
0x180006790  sbb     edx, edx
0x180006792  and     edx, esi
0x180006794  xor     esi, esi
0x180006796  test    ecx, ecx
0x180006798  mov     r8d, esi
0x18000679b  cmovs   ecx, edx
0x18000679e  test    dword ptr [rbx+40h], 400h
0x1800067a5  cmovz   r8d, ecx
0x1800067a9  test    byte ptr [rax+10h], 80h
0x1800067ad  mov     rcx, [rbx+138h]
0x1800067b4  jz      short loc_1800067C7
0x1800067b6  mov     rax, [rcx+30h]
0x1800067ba  cqo
0x1800067bc  sub     rax, rdx
0x1800067bf  sar     rax, 1
0x1800067c2  mov     rdx, rax
0x1800067c5  jmp     short loc_1800067CA
0x1800067c7  mov     edx, [rcx+10h]
0x1800067ca  cmp     [rbx+0CCh], esi
0x1800067d0  jz      short loc_1800067D7
0x1800067d2  cmp     [rbx+58h], esi
0x1800067d5  jnz     short loc_1800067E8
0x1800067d7  mov     rax, [rbx+10h]
0x1800067db  cmp     [rax], esi
0x1800067dd  jnz     short loc_1800067E8
0x1800067df  cmp     edx, r8d
0x1800067e2  jl      loc_180006885
0x1800067e8  cmp     [rcx+38h], esi
0x1800067eb  jz      short loc_180006805
0x1800067ed  cmp     edx, 2
0x1800067f0  jge     short loc_180006805
0x1800067f2  mov     rax, [rbx+0F8h]
0x1800067f9  cmp     [rax+0ACh], esi
0x1800067ff  jz      loc_180006885
0x180006805  mov     rax, [rbx+0F8h]
0x18000680c  cmp     [rax+48h], rsi
0x180006810  jnz     short loc_18000682F
0x180006812  cmp     [rbx+110h], esi
0x180006818  jz      short loc_180006823
0x18000681a  cmp     [rbx+108h], rsi
0x180006821  jz      short loc_18000682F
0x180006823  mov     rcx, rbx
0x180006826  call    sub_180009280
0x18000682b  test    eax, eax
0x18000682d  jnz     short loc_180006885
0x18000682f  cmp     [rbx+340h], r14
0x180006836  jnz     short loc_180006874
0x180006838  mov     rax, [rdi+8]
0x18000683c  test    byte ptr [rax+10h], 80h
0x180006840  jz      short loc_18000684B
0x180006842  cmp     dword ptr [rbx+328h], 5
0x180006849  jnz     short loc_180006874
0x18000684b  test    dword ptr [rbx+40h], 400h
0x180006852  mov     eax, 1
0x180006857  jnz     short loc_18000685F
  ... truncated ...
```
