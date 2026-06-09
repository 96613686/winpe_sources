# __crt_strtox::convert_decimal_string_to_floating_type_common(__crt_strtox::floating_point_string const &,__crt_strtox::floating_point_value const &)

- ea: `0x180020290`
- end: `0x1800220df`
- name: `?convert_decimal_string_to_floating_type_common@__crt_strtox@@YA?AW4SLD_STATUS@@AEBUfloating_point_string@1@AEBVfloating_point_value@1@@Z`
- size: `7759`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18001dfd0`
- `0x18001e140`

## callees

- `0x180007700`
- `0x18000be9c`
- `0x18000bfbc`
- `0x1800150e0`
- `0x180016750`
- `0x18001fd18`
- `0x18001fd54`
- `0x18001fd90`
- `0x180020130`
- `0x180020290`
- `0x180024220`
- `0x1800245e0`

## pseudocode

```c
__int64 __fastcall __crt_strtox::convert_decimal_string_to_floating_type_common(
        __int64 a1,
        __crt_strtox::floating_point_value *a2)
{
  int v2; // r10d
  bool v3; // cf
  __int64 v4; // r9
  __int64 v5; // rdx
  unsigned int v6; // r14d
  unsigned int v7; // eax
  unsigned __int64 v8; // r15
  unsigned int v9; // r13d
  size_t v10; // r8
  unsigned __int8 *v11; // r10
  unsigned __int64 v12; // r8
  __int64 v13; // rdx
  unsigned __int64 v14; // rcx
  unsigned int v15; // edx
  __int64 v16; // rcx
  unsigned __int64 v17; // r15
  int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // r12d
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rdi
  __int64 v24; // rsi
  __int64 v25; // rbx
  unsigned int v26; // r10d
  __int64 v27; // r10
  __int64 v28; // rdx
  unsigned __int64 v29; // rcx
  char v30; // al
  __int64 v31; // rbx
  __int64 v32; // rdx
  unsigned __int64 v33; // rcx
  unsigned int v34; // r12d
  _DWORD *v35; // rcx
  _DWORD *v36; // rdx
  unsigned __int64 v37; // r11
  __int64 v38; // rsi
  __int64 v39; // rbx
  __int64 v40; // rax
  unsigned __int64 v41; // rdx
  __int64 v42; // rdx
  __int64 v43; // rax
  int v44; // r13d
  unsigned int v45; // eax
  __int64 v46; // rdx
  unsigned __int64 v47; // rcx
  __int64 v48; // rcx
  unsigned __int64 v49; // rdx
  unsigned int v50; // ecx
  unsigned int v51; // eax
  unsigned int v52; // r15d
  int v53; // r13d
  __int64 v54; // rax
  __int64 v55; // rsi
  __int64 v56; // rbx
  unsigned int v57; // r10d
  __int64 v58; // r10
  __int64 v59; // rdx
  unsigned __int64 v60; // rcx
  char v61; // al
  __int64 v62; // rbx
  __int64 v63; // rdx
  unsigned __int64 v64; // rcx
  unsigned int v65; // r15d
  _DWORD *v66; // r12
  _DWORD *v67; // r13
  unsigned __int64 v68; // r11
  __int64 v69; // rsi
  unsigned int v70; // r8d
  __int64 v71; // rdi
  __int64 v72; // rax
  unsigned __int64 v73; // rdx
  __int64 v74; // rdx
  __int64 v75; // rax
  unsigned int v76; // ecx
  int v77; // eax
  __int64 v78; // r10
  __int64 v79; // rdx
  unsigned __int64 v80; // rcx
  unsigned __int64 *v81; // r8
  char v82; // al
  unsigned int v84; // ecx
  __int64 v85; // rcx
  int v86; // eax
  int v87; // eax
  bool v88; // zf
  unsigned __int8 *v89; // rbx
  unsigned int v90; // r15d
  unsigned __int64 v91; // r12
  unsigned int v92; // r13d
  unsigned __int64 v93; // r8
  __int64 v94; // rdx
  unsigned __int64 v95; // rcx
  unsigned int v96; // r8d
  __int64 v97; // rdx
  unsigned __int64 v98; // rcx
  int v99; // eax
  unsigned int v100; // eax
  unsigned int v101; // ecx
  int v102; // eax
  __int64 v103; // rdi
  __int64 v104; // rsi
  __int64 v105; // rbx
  unsigned int v106; // r10d
  rsize_t v107; // r9
  unsigned int *v108; // r8
  unsigned __int64 v109; // r8
  __int64 v110; // r10
  __int64 v111; // rdx
  unsigned __int64 v112; // rcx
  char v113; // al
  __int64 v114; // rbx
  __int64 v115; // rdx
  unsigned __int64 v116; // rcx
  _DWORD *v117; // rdx
  unsigned int v118; // ebx
  _DWORD *v119; // rcx
  unsigned int v120; // eax
  __int64 v121; // r9
  _DWORD *v122; // r15
  __int64 v123; // rsi
  unsigned __int64 v124; // r11
  unsigned int v125; // r8d
  __int64 v126; // rdi
  __int64 v127; // rax
  unsigned __int64 v128; // rdx
  __int64 v129; // rdx
  unsigned __int64 v130; // rcx
  int v131; // r13d
  unsigned int v132; // eax
  unsigned __int64 v133; // r8
  __int64 v134; // rdx
  unsigned __int64 v135; // rcx
  unsigned int v136; // r8d
  __int64 v137; // rcx
  unsigned __int64 v138; // rdx
  unsigned int v139; // r13d
  unsigned int v140; // r12d
  bool v141; // sf
  unsigned int v142; // eax
  unsigned int v143; // ecx
  int v144; // eax
  __int64 v145; // rdi
  __int64 v146; // rsi
  __int64 v147; // rbx
  unsigned int v148; // r10d
  char v149; // al
  unsigned __int64 v150; // r8
  __int64 v151; // r10
  __int64 v152; // rdx
  unsigned __int64 v153; // rcx
  __int64 v154; // rbx
  _DWORD *v155; // r8
  rsize_t v156; // r9
  unsigned __int64 v157; // r8
  __int64 v158; // rdx
  unsigned __int64 v159; // rcx
  unsigned int *v160; // rdx
  unsigned int v161; // ebx
  unsigned int *v162; // rcx
  unsigned int v163; // eax
  __int64 v164; // r9
  _QWORD *v165; // r13
  __int64 v166; // rsi
  unsigned __int64 v167; // r11
  unsigned int v168; // r8d
  __int64 v169; // rdi
  __int64 v170; // rax
  unsigned __int64 v171; // rdx
  __int64 v172; // rdx
  unsigned __int64 v173; // rcx
  int v174; // r12d
  int v175; // eax
  unsigned int v176; // edx
  unsigned __int64 v177; // r8
  __int64 v178; // r10
  __int64 v179; // rdx
  unsigned __int64 v180; // rcx
  char v181; // bl
  __int64 v182; // rdx
  int v183; // eax
  int v184; // eax
  unsigned int v185; // ecx
  __int64 v186; // rcx
  int v187; // eax
  int v188; // eax
  unsigned int v189; // ebx
  unsigned int v190; // esi
  unsigned int v191; // r8d
  int v192; // ecx
  int v193; // ecx
  unsigned int v194; // edx
  __int64 v195; // r11
  __int64 v196; // rax
  __int64 v197; // rcx
  int v198; // r10d
  int v199; // r9d
  unsigned int v200; // ecx
  __int64 v201; // rax
  unsigned int v202; // edi
  unsigned int v203; // eax
  unsigned int v204; // r10d
  __int64 v205; // rdx
  bool v206; // cl
  __int64 v207; // rdx
  unsigned int v208; // r9d
  unsigned int v209; // r10d
  unsigned int v210; // r9d
  int v211; // ecx
  int v212; // ecx
  unsigned int v213; // edx
  __int64 v214; // r11
  __int64 v215; // rax
  __int64 v216; // rcx
  int v217; // edi
  int v218; // r8d
  __int64 v219; // rcx
  unsigned __int64 v220; // rdx
  __int64 v221; // r9
  int v222; // ecx
  int v223; // ecx
  unsigned int v224; // ecx
  int v225; // ecx
  char v226; // cl
  unsigned int v227; // r11d
  unsigned int v228; // ebx
  __int64 v229; // r8
  unsigned __int64 v230; // r10
  __crt_strtox::floating_point_value *v231; // [rsp+20h] [rbp-E0h]
  unsigned int v232; // [rsp+30h] [rbp-D0h]
  unsigned int v233; // [rsp+30h] [rbp-D0h]
  int v234; // [rsp+30h] [rbp-D0h]
  unsigned int v235; // [rsp+30h] [rbp-D0h]
  int v236; // [rsp+34h] [rbp-CCh]
  unsigned int v237; // [rsp+34h] [rbp-CCh]
  unsigned int v238; // [rsp+34h] [rbp-CCh]
  int v239; // [rsp+38h] [rbp-C8h]
  int v240; // [rsp+38h] [rbp-C8h]
  unsigned int v241; // [rsp+3Ch] [rbp-C4h]
  unsigned int v242; // [rsp+3Ch] [rbp-C4h]
  unsigned int v243; // [rsp+3Ch] [rbp-C4h]
  unsigned int v244; // [rsp+40h] [rbp-C0h]
  _DWORD *v245; // [rsp+48h] [rbp-B8h]
  int v246; // [rsp+48h] [rbp-B8h]
  unsigned int v247; // [rsp+50h] [rbp-B0h]
  unsigned int v248; // [rsp+50h] [rbp-B0h]
  _DWORD *v251; // [rsp+68h] [rbp-98h]
  _DWORD *v252; // [rsp+68h] [rbp-98h]
  unsigned int *v253; // [rsp+68h] [rbp-98h]
  unsigned __int8 *v254; // [rsp+70h] [rbp-90h]
  unsigned __int8 *v255; // [rsp+78h] [rbp-88h]
  _BYTE v256[460]; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v257; // [rsp+250h] [rbp+150h] BYREF
  _DWORD Destination[115]; // [rsp+254h] [rbp+154h] BYREF
  unsigned int v259; // [rsp+420h] [rbp+320h] BYREF
  _DWORD v260[115]; // [rsp+424h] [rbp+324h] BYREF
  unsigned int v261; // [rsp+5F0h] [rbp+4F0h] BYREF
  unsigned int v262[115]; // [rsp+5F4h] [rbp+4F4h] BYREF
  unsigned int v263; // [rsp+7C0h] [rbp+6C0h]
  _DWORD Src[115]; // [rsp+7C4h] [rbp+6C4h] BYREF
  unsigned int v265; // [rsp+990h] [rbp+890h]
  _DWORD Source[115]; // [rsp+994h] [rbp+894h] BYREF

  v2 = *(_DWORD *)a1;
  v3 = *((_BYTE *)a2 + 8) != 0;
  v4 = a1;
  v5 = *(unsigned int *)(a1 + 4);
  v247 = v3 ? 54 : 25;
  v259 = 0;
  if ( v2 < 0 )
    v2 = 0;
  v6 = 0;
  v7 = v2;
  LODWORD(v8) = 0;
  if ( v2 >= (unsigned int)v5 )
    v7 = v5;
  v9 = 0;
  v10 = v7 + a1 + 8;
  v232 = v2 - v7;
  v255 = (unsigned __int8 *)v10;
  v11 = (unsigned __int8 *)(a1 + 8);
  v254 = (unsigned __int8 *)(v5 + a1 + 8);
  v244 = (_DWORD)v254 - v10;
  if ( a1 + 8 != v10 )
  {
    do
    {
      if ( v9 == 9 )
      {
        if ( v6 )
        {
          LODWORD(v12) = 0;
          LODWORD(v4) = 0;
          do
          {
            v13 = (unsigned int)v4;
            v4 = (unsigned int)(v4 + 1);
            v14 = (unsigned int)v12 + 1000000000LL * (unsigned int)v260[v13];
            v260[v13] = v14;
            v12 = HIDWORD(v14);
          }
          while ( (_DWORD)v4 != v6 );
          if ( HIDWORD(v14) )
          {
            if ( v259 >= 0x73 )
            {
              v6 = 0;
              v259 = 0;
            }
            else
            {
              v260[v259] = HIDWORD(v14);
              v6 = ++v259;
            }
          }
          else
          {
            v6 = v259;
          }
          v10 = (size_t)v255;
        }
        if ( (_DWORD)v8 )
        {
          v15 = 0;
          if ( v6 )
          {
            do
            {
              v16 = v15++;
              v17 = (unsigned int)v260[v16] + (unsigned __int64)(unsigned int)v8;
              v260[v16] = v17;
              v6 = v259;
              v8 = HIDWORD(v17);
            }
            while ( v15 != v259 );
          }
          if ( (_DWORD)v8 )
          {
            if ( v6 >= 0x73 )
            {
              v6 = 0;
              v259 = 0;
            }
            else
            {
              v260[v6] = v8;
              v6 = ++v259;
            }
          }
        }
        LODWORD(v8) = 0;
        v9 = 0;
      }
      v18 = *v11;
      ++v9;
      ++v11;
      LODWORD(v8) = v18 + 10 * v8;
    }
    while ( v11 != (unsigned __int8 *)v10 );
    if ( v9 )
    {
      v19 = v9 / 0xA;
      v20 = v9 / 0xA;
      v241 = v9 / 0xA;
      if ( v9 / 0xA )
      {
        while ( 1 )
        {
          v21 = v20;
          if ( v20 > 0x26 )
            v21 = 38;
          v236 = v21;
          v22 = (unsigned int)(v21 - 1);
          v23 = (unsigned int)v22;
          v24 = (unsigned __int8)byte_180029E23[4 * v22];
          v25 = (unsigned __int8)byte_180029E22[4 * v22];
          v263 = v24 + (unsigned __int8)byte_180029E22[4 * v22];
          memset(Src, 0, v25 * 4);
          memmove(
            &Src[v25],
            (char *)&`__crt_strtox::multiply_by_power_of_ten'::`2'::large_power_data
          + 4 * (unsigned __int16)`__crt_strtox::multiply_by_power_of_ten'::`2'::large_power_indices[2 * v23],
            4 * v24);
          v26 = v263;
          if ( v263 > 1 )
          {
            if ( v6 > 1 )
            {
              v34 = v6;
              v35 = Src;
              if ( v263 < v6 )
                v34 = v263;
              else
                v35 = v260;
              v251 = v35;
              v36 = v260;
              if ( v263 >= v6 )
                v36 = Src;
              LODWORD(v37) = 0;
              v245 = v36;
              v261 = 0;
              v4 = 0;
              if ( v263 < v6 )
                v26 = v6;
              v6 = 0;
              while ( 1 )
              {
                v38 = (unsigned int)v35[(unsigned int)v4];
                if ( (_DWORD)v38 )
                {
                  v10 = (unsigned int)v4;
                  if ( v26 )
                  {
                    while ( (_DWORD)v10 != 115 )
                    {
                      v39 = (unsigned int)v10;
                      if ( (_DWORD)v10 == v6 )
                      {
                        v262[(unsigned int)v10] = 0;
                        v261 = v10 + 1;
                      }
                      v40 = (unsigned int)(v10 - v4);
                      v10 = (unsigned int)(v10 + 1);
                      v41 = v262[v39] + (unsigned int)v37 + v38 * (unsigned int)v36[v40];
                      v262[v39] = v41;
                      v6 = v261;
                      v37 = HIDWORD(v41);
                      if ( (_DWORD)v10 - (_DWORD)v4 == v26 )
                        break;
                      v36 = v245;
                    }
                    if ( (_DWORD)v37 )
                    {
                      while ( (_DWORD)v10 != 115 )
                      {
                        v42 = (unsigned int)v10;
                        if ( (_DWORD)v10 == v6 )
                        {
                          v262[(unsigned int)v10] = 0;
                          v261 = v10 + 1;
                        }
                        v43 = v262[(unsigned int)v10];
                        v10 = (unsigned int)(v10 + 1);
                        v262[v42] = v43 + v37;
                        v6 = v261;
                        LODWORD(v37) = (v43 + (unsigned __int64)(unsigned int)v37) >> 32;
                        if ( !(_DWORD)v37 )
                          goto LABEL_75;
                      }
LABEL_98:
                      v6 = 0;
                      v259 = 0;
                      goto LABEL_99;
                    }
                  }
LABEL_75:
                  LODWORD(v37) = 0;
                  if ( (_DWORD)v10 == 115 )
                    goto LABEL_98;
                  v35 = v251;
                  v36 = v245;
                }
                else if ( (_DWORD)v4 == v6 )
                {
                  v6 = v4 + 1;
                  v262[(unsigned int)v4] = 0;
                  v261 = v4 + 1;
                }
                v4 = (unsigned int)(v4 + 1);
                if ( (_DWORD)v4 == v34 )
                {
                  v10 = 4LL * v6;
                  v259 = v6;
                  if ( v10 )
                  {
                    if ( v10 > 0x1CC )
                    {
                      memset(v260, 0, sizeof(v260));
                      *errno() = 34;
                      invalid_parameter_noinfo();
                    }
                    else
                    {
                      memmove(v260, v262, v10);
                    }
                    v6 = v259;
                  }
                  v20 = v241;
                  goto LABEL_84;
                }
              }
            }
            v31 = v260[0];
            v10 = 4LL * v263;
            v259 = v263;
            v6 = v263;
            if ( v10 )
            {
              if ( v10 > 0x1CC )
              {
                memset(v260, 0, sizeof(v260));
                *errno() = 34;
                invalid_parameter_noinfo();
              }
              else
              {
                memmove(v260, Src, v10);
              }
              v6 = v259;
            }
            if ( !(_DWORD)v31 )
            {
LABEL_31:
              v6 = 0;
              v259 = 0;
LABEL_84:
              v30 = 1;
              goto LABEL_85;
            }
            if ( (_DWORD)v31 == 1 || !v6 )
              goto LABEL_84;
            LODWORD(v10) = 0;
            LODWORD(v4) = 0;
            do
            {
              v32 = (unsigned int)v4;
              v4 = (unsigned int)(v4 + 1);
              v33 = (unsigned int)v10 + v31 * (unsigned int)v260[v32];
              v260[v32] = v33;
              v10 = HIDWORD(v33);
            }
            while ( (_DWORD)v4 != v6 );
          }
          else
          {
            if ( !Src[0] )
              goto LABEL_31;
            if ( Src[0] == 1 || !v6 )
              goto LABEL_84;
            LODWORD(v10) = 0;
            LODWORD(v4) = 0;
            v27 = Src[0];
            do
            {
              v28 = (unsigned int)v4;
              v4 = (unsigned int)(v4 + 1);
              v29 = (unsigned int)v10 + v27 * (unsigned int)v260[v28];
              v260[v28] = v29;
              v10 = HIDWORD(v29);
            }
            while ( (_DWORD)v4 != v6 );
          }
          if ( !(_DWORD)v10 )
          {
            v6 = v259;
            goto LABEL_84;
          }
          if ( v259 < 0x73 )
          {
            v260[v259] = v10;
            v6 = ++v259;
            goto LABEL_84;
          }
          v6 = 0;
          v259 = 0;
          v30 = 0;
LABEL_85:
          if ( !v30 )
            goto LABEL_98;
          v20 -= v236;
          v241 = v20;
          if ( !v20 )
          {
            v19 = v9 / 0xA;
            break;
          }
        }
      }
      v44 = v9 - 10 * v19;
      if ( v44 )
      {
        v45 = `__crt_strtox::multiply_by_power_of_ten'::`2'::small_powers_of_ten[v44 - 1];
        if ( !v45 )
          goto LABEL_98;
        if ( v45 != 1 && v6 )
        {
          LODWORD(v10) = 0;
          LODWORD(v4) = 0;
          do
          {
            v46 = (unsigned int)v4;
            v4 = (unsigned int)(v4 + 1);
            v47 = (unsigned int)v10 + v45 * (unsigned __int64)(unsigned int)v260[v46];
            v260[v46] = v47;
            v10 = HIDWORD(v47);
          }
          while ( (_DWORD)v4 != v6 );
          if ( HIDWORD(v47) )
          {
            if ( v259 >= 0x73 )
              goto LABEL_98;
            v260[v259] = HIDWORD(v47);
            v6 = ++v259;
          }
          else
          {
            v6 = v259;
          }
        }
      }
LABEL_99:
      if ( (_DWORD)v8 )
      {
        v10 = 0;
        if ( v6 )
        {
          do
          {
            v48 = (unsigned int)v10;
            v10 = (unsigned int)(v10 + 1);
            v49 = (unsigned int)v260[v48] + (unsigned __int64)(unsigned int)v8;
            v260[v48] = v49;
            v6 = v259;
            LODWORD(v8) = HIDWORD(v49);
          }
          while ( (_DWORD)v10 != v259 );
        }
        if ( (_DWORD)v8 )
        {
          if ( v6 >= 0x73 )
          {
            v6 = 0;
            v259 = 0;
          }
          else
          {
            v260[v6] = v8;
            v6 = ++v259;
          }
        }
      }
    }
  }
  v50 = v232;
  if ( !v232 )
    goto LABEL_182;
  v51 = v232 / 0xA;
  v52 = v232 / 0xA;
  v242 = v232 / 0xA;
  if ( !(v232 / 0xA) )
    goto LABEL_167;
  do
  {
    v53 = v52;
    if ( v52 > 0x26 )
      v53 = 38;
    v239 = v53;
    v54 = (unsigned int)(v53 - 1);
    v55 = (unsigned __int8)byte_180029E23[4 * v54];
    v56 = (unsigned __int8)byte_180029E22[4 * v54];
    v263 = v55 + (unsigned __int8)byte_180029E22[4 * v54];
    memset(Src, 0, v56 * 4);
    memmove(
      &Src[v56],
      (char *)&`__crt_strtox::multiply_by_power_of_ten'::`2'::large_power_data
    + 4 * (unsigned __int16)`__crt_strtox::multiply_by_power_of_ten'::`2'::large_power_indices[2 * (v53 - 1)],
      4 * v55);
    v57 = v263;
    if ( v263 > 1 )
    {
      if ( v6 > 1 )
      {
        v65 = v6;
        v66 = Src;
        if ( v263 >= v6 )
          v66 = v260;
        v67 = v260;
        if ( v263 >= v6 )
          v67 = Src;
        else
          v65 = v263;
        LODWORD(v68) = 0;
        v261 = 0;
        LODWORD(v4) = 0;
        if ( v263 < v6 )
          v57 = v6;
        v6 = 0;
        do
        {
          v69 = (unsigned int)v66[(unsigned int)v4];
          if ( (_DWORD)v69 )
          {
            v70 = v4;
            if ( v57 )
            {
              do
              {
                if ( v70 == 115 )
                  break;
                v71 = v70;
                if ( v70 == v6 )
                {
                  v262[v70] = 0;
                  v261 = v70 + 1;
                }
                v72 = v70 - (unsigned int)v4;
                ++v70;
                v73 = v262[v71] + (unsigned int)v68 + v69 * (unsigned int)v67[v72];
                v262[v71] = v73;
                v6 = v261;
                v68 = HIDWORD(v73);
              }
              while ( v70 - (_DWORD)v4 != v57 );
              if ( (_DWORD)v68 )
              {
                while ( v70 != 115 )
                {
                  v74 = v70;
                  if ( v70 == v6 )
                  {
                    v262[v70] = 0;
                    v261 = v70 + 1;
                  }
                  v75 = v262[v70++];
                  v262[v74] = v75 + v68;
                  v6 = v261;
                  LODWORD(v68) = (v75 + (unsigned __int64)(unsigned int)v68) >> 32;
                  if ( !(_DWORD)v68 )
                    goto LABEL_155;
                }
LABEL_177:
                v81 = *(unsigned __int64 **)a2;
                v82 = *(_BYTE *)(a1 + 776);
                if ( *((_BYTE *)a2 + 8) )
                  *v81 = *v81 & 0x7FF0000000000000LL
                       | ((-(__int64)(v82 != 0) & 0x8000000000000000uLL) + 0x7FF0000000000000LL) & 0xFFF0000000000000uLL;
                else
                  *(_DWORD *)v81 = *(_DWORD *)v81 & 0x7F800000 | (v82 != 0 ? -8388608 : 2139095040) & 0xFF800000;
                return 3;
              }
            }
LABEL_155:
            LODWORD(v68) = 0;
            if ( v70 == 115 )
              goto LABEL_177;
          }
          else if ( (_DWORD)v4 == v6 )
          {
            v6 = v4 + 1;
            v262[(unsigned int)v4] = 0;
            v261 = v4 + 1;
          }
          v4 = (unsigned int)(v4 + 1);
        }
        while ( (_DWORD)v4 != v65 );
        v10 = 4LL * v6;
        v259 = v6;
        if ( v10 )
        {
          if ( v10 > 0x1CC )
          {
            memset(v260, 0, sizeof(v260));
            *errno() = 34;
            invalid_parameter_noinfo();
          }
          else
          {
            memmove(v260, v262, v10);
          }
          v6 = v259;
        }
        v52 = v242;
        v53 = v239;
        goto LABEL_163;
      }
      v62 = v260[0];
      v10 = 4LL * v263;
      v259 = v263;
      v6 = v263;
      if ( v10 )
      {
        if ( v10 > 0x1CC )
        {
          memset(v260, 0, sizeof(v260));
          *errno() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memmove(v260, Src, v10);
        }
        v6 = v259;
      }
      if ( !(_DWORD)v62 )
      {
LABEL_112:
        v6 = 0;
        v259 = 0;
        goto LABEL_163;
      }
      if ( (_DWORD)v62 == 1 || !v6 )
        goto LABEL_163;
      LODWORD(v10) = 0;
      LODWORD(v4) = 0;
      do
      {
        v63 = (unsigned int)v4;
        v4 = (unsigned int)(v4 + 1);
        v64 = (unsigned int)v10 + v62 * (unsigned int)v260[v63];
        v260[v63] = v64;
        v10 = HIDWORD(v64);
      }
      while ( (_DWORD)v4 != v6 );
    }
    else
    {
      if ( !Src[0] )
        goto LABEL_112;
      if ( Src[0] == 1 || !v6 )
        goto LABEL_163;
      LODWORD(v10) = 0;
      LODWORD(v4) = 0;
      v58 = Src[0];
      do
      {
        v59 = (unsigned int)v4;
        v4 = (unsigned int)(v4 + 1);
        v60 = (unsigned int)v10 + v58 * (unsigned int)v260[v59];
        v260[v59] = v60;
        v10 = HIDWORD(v60);
      }
      while ( (_DWORD)v4 != v6 );
    }
    if ( (_DWORD)v10 )
    {
      if ( v259 >= 0x73 )
      {
        v6 = 0;
        v259 = 0;
        v61 = 0;
        goto LABEL_164;
      }
      v260[v259] = v10;
      v6 = ++v259;
    }
    else
    {
      v6 = v259;
    }
LABEL_163:
    v61 = 1;
LABEL_164:
    if ( !v61 )
      goto LABEL_177;
    v52 -= v53;
    v242 = v52;
  }
  while ( v52 );
  v51 = v232 / 0xA;
  v50 = v232;
LABEL_167:
  v76 = v50 - 10 * v51;
  if ( !v76 )
    goto LABEL_182;
  v77 = `__crt_strtox::multiply_by_power_of_ten'::`2'::small_powers_of_ten[v76 - 1];
  if ( !v77 )
  {
    v6 = 0;
    v259 = 0;
    goto LABEL_183;
  }
  if ( v77 == 1 )
  {
LABEL_182:
    if ( !v6 )
      goto LABEL_183;
    v85 = v6 - 1;
    v88 = !_BitScanReverse((unsigned int *)&v86, v260[v85]);
    if ( v88 )
      v87 = 0;
    else
      v87 = v86 + 1;
    v84 = v87 + 32 * v85;
  }
  else
  {
    if ( v6 )
    {
      LODWORD(v10) = 0;
      LODWORD(v4) = 0;
      v78 = (unsigned int)`__crt_strtox::multiply_by_power_of_ten'::`2'::small_powers_of_ten[v76 - 1];
      do
      {
        v79 = (unsigned int)v4;
        v4 = (unsigned int)(v4 + 1);
        v80 = (unsigned int)v10 + v78 * (unsigned int)v260[v79];
        v260[v79] = v80;
        v10 = HIDWORD(v80);
      }
      while ( (_DWORD)v4 != v6 );
      if ( HIDWORD(v80) )
      {
        if ( v259 >= 0x73 )
          goto LABEL_177;
        v260[v259] = HIDWORD(v80);
        v6 = ++v259;
      }
      else
      {
        v6 = v259;
      }
      goto LABEL_182;
    }
LABEL_183:
    v84 = 0;
  }
  v243 = v84;
  if ( v84 >= v247 )
  {
    v88 = v244 == 0;
LABEL_453:
    LOBYTE(v4) = !v88;
    v231 = a2;
    v205 = v84;
LABEL_454:
    LOBYTE(v10) = *(_BYTE *)(a1 + 776);
    return __crt_strtox::assemble_floating_point_value_from_big_integer(&v259, v205, v10, v4, v231);
  }
  v88 = v244 == 0;
  if ( !v244 )
    goto LABEL_453;
  v89 = v255;
  v90 = 0;
  LODWORD(v91) = 0;
  v257 = 0;
  v92 = 0;
  if ( v255 == v254 )
    goto LABEL_284;
  while ( 2 )
  {
    if ( v92 == 9 )
    {
      if ( !v90 )
        goto LABEL_200;
      LODWORD(v93) = 0;
      LODWORD(v4) = 0;
      do
      {
        v94 = (unsigned int)v4;
        v4 = (unsigned int)(v4 + 1);
        v95 = (unsigned int)v93 + 1000000000LL * (unsigned int)Destination[v94];
        Destination[v94] = v95;
        v93 = HIDWORD(v95);
      }
      while ( (_DWORD)v4 != v90 );
      if ( HIDWORD(v95) )
      {
        if ( v257 < 0x73 )
        {
          Destination[v257] = HIDWORD(v95);
          v90 = ++v257;
          goto LABEL_200;
        }
        v265 = 0;
        v257 = 0;
        memcpy_s(Destination, 0x1CCu, Source, 0);
      }
      v90 = v257;
LABEL_200:
      if ( (_DWORD)v91 )
      {
        v96 = 0;
        if ( v90 )
        {
          do
          {
            v97 = v96++;
            v98 = (unsigned int)v91 + (unsigned __int64)(unsigned int)Destination[v97];
            Destination[v97] = v98;
            v90 = v257;
            v91 = HIDWORD(v98);
          }
          while ( v96 != v257 );
        }
        if ( (_DWORD)v91 )
        {
          if ( v90 >= 0x73 )
          {
            v265 = 0;
            v257 = 0;
            memcpy_s(Destination, 0x1CCu, Source, 0);
            v90 = 0;
          }
          else
          {
            Destination[v90] = v91;
            v90 = ++v257;
          }
        }
      }
      LODWORD(v91) = 0;
      v92 = 0;
    }
    v99 = *v89;
    ++v92;
    ++v89;
    LODWORD(v91) = v99 + 10 * v91;
    if ( v89 != v254 )
      continue;
    break;
  }
  if ( !v92 )
    goto LABEL_284;
  v100 = v92 / 0xA;
  v101 = v92 / 0xA;
  v237 = v92 / 0xA;
  if ( !(v92 / 0xA) )
    goto LABEL_265;
  while ( 2 )
  {
    v102 = v101;
    if ( v101 > 0x26 )
      v102 = 38;
    v240 = v102;
    v103 = (unsigned int)(v102 - 1);
    v104 = (unsigned __int8)byte_180029E23[4 * v103];
    v105 = (unsigned __int8)byte_180029E22[4 * v103];
    v263 = v104 + (unsigned __int8)byte_180029E22[4 * v103];
    memset(Src, 0, v105 * 4);
    memmove(
      &Src[v105],
      (char *)&`__crt_strtox::multiply_by_power_of_ten'::`2'::large_power_data
    + 4 * (unsigned __int16)`__crt_strtox::multiply_by_power_of_ten'::`2'::large_power_indices[2 * v103],
      4 * v104);
    v106 = v263;
    if ( v263 <= 1 )
    {
      if ( !Src[0] )
      {
        v265 = 0;
        v257 = 0;
LABEL_216:
        v107 = 0;
        v108 = Source;
LABEL_259:
        memcpy_s(Destination, 0x1CCu, v108, v107);
LABEL_260:
        v90 = v257;
LABEL_261:
        v113 = 1;
        goto LABEL_262;
      }
      if ( Src[0] == 1 || !v90 )
        goto LABEL_261;
      LODWORD(v109) = 0;
      LODWORD(v4) = 0;
      v110 = Src[0];
      do
      {
        v111 = (unsigned int)v4;
        v4 = (unsigned int)(v4 + 1);
        v112 = (unsigned int)v109 + v110 * (unsigned int)Destination[v111];
        Destination[v111] = v112;
        v109 = HIDWORD(v112);
      }
      while ( (_DWORD)v4 != v90 );
      if ( !HIDWORD(v112) )
        goto LABEL_260;
      if ( v257 < 0x73 )
      {
LABEL_223:
        Destination[v257] = v109;
        v90 = ++v257;
        goto LABEL_261;
      }
LABEL_224:
      v265 = 0;
      v257 = 0;
      memcpy_s(Destination, 0x1CCu, Source, 0);
      v113 = 0;
      v90 = 0;
      goto LABEL_262;
    }
    if ( v90 <= 1 )
    {
      v114 = Destination[0];
      v257 = v263;
      memcpy_s(Destination, 0x1CCu, Src, 4LL * v263);
      if ( !(_DWORD)v114 )
      {
        v265 = 0;
        v257 = 0;
        goto LABEL_216;
      }
      v90 = v257;
      if ( (_DWORD)v114 == 1 )
        goto LABEL_261;
      LODWORD(v109) = 0;
      LODWORD(v4) = 0;
      do
      {
        v115 = (unsigned int)v4;
        v4 = (unsigned int)(v4 + 1);
        v116 = (unsigned int)v109 + v114 * (unsigned int)Destination[v115];
        Destination[v115] = v116;
        v109 = HIDWORD(v116);
      }
      while ( (_DWORD)v4 != v90 );
      if ( !HIDWORD(v116) )
        goto LABEL_260;
      if ( v257 < 0x73 )
        goto LABEL_223;
      goto LABEL_224;
    }
    v117 = Src;
    v118 = v90;
    if ( v263 < v90 )
      v118 = v263;
    else
      v117 = Destination;
    v252 = v117;
    v119 = Destination;
    v233 = v118;
    if ( v263 < v90 )
      v106 = v90;
    else
      v119 = Src;
    v120 = 0;
    v121 = 0;
    v261 = 0;
    v122 = v119;
    while ( 2 )
    {
      v123 = (unsigned int)v117[v121];
      if ( !(_DWORD)v123 )
      {
        if ( (_DWORD)v121 == v120 )
        {
          v262[v121] = 0;
          v120 = v121 + 1;
          v261 = v121 + 1;
        }
LABEL_257:
        v121 = (unsigned int)(v121 + 1);
        if ( (_DWORD)v121 == v118 )
        {
          v108 = v262;
          v107 = 4LL * v120;
          v257 = v120;
          goto LABEL_259;
        }
        continue;
      }
      break;
    }
    LODWORD(v124) = 0;
    v125 = v121;
    if ( v106 )
    {
      do
      {
        if ( v125 == 115 )
          break;
        v126 = v125;
        if ( v125 == v120 )
        {
          v262[v125] = 0;
          v261 = v125 + 1;
        }
        v127 = v125 - (unsigned int)v121;
        ++v125;
        v128 = (unsigned int)v124 + v262[v126] + v123 * (unsigned int)v122[v127];
        v262[v126] = v128;
        v124 = HIDWORD(v128);
        v120 = v261;
      }
      while ( v125 - (_DWORD)v121 != v106 );
      if ( (_DWORD)v124 )
      {
        do
        {
          if ( v125 == 115 )
            break;
          v129 = v125;
          if ( v125 == v120 )
          {
            v262[v125] = 0;
            v261 = v125 + 1;
          }
          ++v125;
          v130 = (unsigned int)v124 + (unsigned __int64)v262[v129];
          v262[v129] = v130;
          v120 = v261;
          LODWORD(v124) = HIDWORD(v130);
        }
        while ( HIDWORD(v130) );
      }
      v118 = v233;
    }
    if ( v125 != 115 )
    {
      v117 = v252;
      goto LABEL_257;
    }
    v265 = 0;
    v257 = 0;
    memcpy_s(Destination, 0x1CCu, Source, 0);
    v90 = 0;
    v113 = 0;
LABEL_262:
    if ( !v113 )
      goto LABEL_275;
    v88 = v237 == v240;
    v101 = v237 - v240;
    v237 -= v240;
    if ( !v88 )
      continue;
    break;
  }
  v100 = v92 / 0xA;
LABEL_265:
  v131 = v92 - 10 * v100;
  if ( v131 )
  {
    v132 = `__crt_strtox::multiply_by_power_of_ten'::`2'::small_powers_of_ten[v131 - 1];
    if ( !v132 )
      goto LABEL_275;
    if ( v132 == 1 || !v90 )
      goto LABEL_277;
    LODWORD(v133) = 0;
    LODWORD(v4) = 0;
    do
    {
      v134 = (unsigned int)v4;
      v4 = (unsigned int)(v4 + 1);
      v135 = (unsigned int)v133 + v132 * (unsigned __int64)(unsigned int)Destination[v134];
      Destination[v134] = v135;
      v133 = HIDWORD(v135);
    }
    while ( (_DWORD)v4 != v90 );
    if ( HIDWORD(v135) )
    {
      if ( v257 < 0x73 )
      {
        Destination[v257] = HIDWORD(v135);
        v90 = ++v257;
        goto LABEL_277;
      }
LABEL_275:
      v265 = 0;
      v257 = 0;
      memcpy_s(Destination, 0x1CCu, Source, 0);
    }
    v90 = v257;
  }
LABEL_277:
  if ( (_DWORD)v91 )
  {
    v136 = 0;
    if ( v90 )
    {
      do
      {
        v137 = v136++;
        v138 = (unsigned int)v91 + (unsigned __int64)(unsigned int)Destination[v137];
        Destination[v137] = v138;
        v90 = v257;
        LODWORD(v91) = HIDWORD(v138);
      }
      while ( v136 != v257 );
    }
    if ( (_DWORD)v91 )
    {
      if ( v90 >= 0x73 )
      {
        v265 = 0;
        v257 = 0;
        memcpy_s(Destination, 0x1CCu, Source, 0);
        v90 = 0;
      }
      else
      {
        Destination[v90] = v91;
        v90 = ++v257;
      }
    }
  }
LABEL_284:
  v139 = 1;
  *(_QWORD *)v262 = 1;
  v234 = 1;
  v140 = v244 - *(_DWORD *)a1;
  v141 = *(int *)a1 < 0;
  v261 = 1;
  if ( !v141 )
    v140 = v244;
  v142 = v140 / 0xA;
  v143 = v140 / 0xA;
  v238 = v140 / 0xA;
  if ( v140 / 0xA )
  {
LABEL_287:
    v144 = v143;
    if ( v143 > 0x26 )
      v144 = 38;
    v246 = v144;
    v145 = (unsigned int)(v144 - 1);
    v146 = (unsigned __int8)byte_180029E23[4 * v145];
    v147 = (unsigned __int8)byte_180029E22[4 * v145];
    v265 = v146 + (unsigned __int8)byte_180029E22[4 * v145];
    memset(Source, 0, v147 * 4);
    memmove(
      &Source[v147],
      (char *)&`__crt_strtox::multiply_by_power_of_ten'::`2'::large_power_data
    + 4 * (unsigned __int16)`__crt_strtox::multiply_by_power_of_ten'::`2'::large_power_indices[2 * v145],
      4 * v146);
    v148 = v265;
    if ( v265 <= 1 )
    {
      if ( !Source[0] )
      {
        v263 = 0;
        v261 = 0;
        memcpy_s(v262, 0x1CCu, Src, 0);
        goto LABEL_292;
      }
      if ( Source[0] != 1 && v139 )
      {
        LODWORD(v150) = 0;
        LODWORD(v4) = 0;
        v151 = Source[0];
        do
        {
          v152 = (unsigned int)v4;
          v4 = (unsigned int)(v4 + 1);
          v153 = (unsigned int)v150 + v151 * v262[v152];
          v262[v152] = v153;
          v150 = HIDWORD(v153);
        }
        while ( (_DWORD)v4 != v139 );
        if ( HIDWORD(v153) )
        {
          if ( v261 >= 0x73 )
            goto LABEL_313;
          v262[v261] = HIDWORD(v153);
          v139 = ++v261;
        }
        else
        {
LABEL_292:
          v139 = v261;
        }
        v234 = v139;
      }
      v149 = 1;
      goto LABEL_343;
    }
    if ( v139 <= 1 )
    {
      v154 = v262[0];
      v261 = v265;
      memcpy_s(v262, 0x1CCu, Source, 4LL * v265);
      if ( !(_DWORD)v154 )
      {
        v265 = 0;
        v155 = Source;
        v261 = 0;
        v156 = 0;
LABEL_339:
        memcpy_s(v262, 0x1CCu, v155, v156);
LABEL_340:
        v139 = v261;
LABEL_341:
        v234 = v139;
LABEL_342:
        v149 = 1;
        goto LABEL_343;
      }
      v139 = v261;
      v234 = v261;
      if ( (_DWORD)v154 == 1 || !v261 )
        goto LABEL_342;
      LODWORD(v157) = 0;
      LODWORD(v4) = 0;
      do
      {
        v158 = (unsigned int)v4;
        v4 = (unsigned int)(v4 + 1);
        v159 = (unsigned int)v157 + v154 * v262[v158];
        v262[v158] = v159;
        v157 = HIDWORD(v159);
      }
      while ( (_DWORD)v4 != v139 );
      if ( !HIDWORD(v159) )
        goto LABEL_340;
      if ( v261 < 0x73 )
      {
        v262[v261] = HIDWORD(v159);
        v139 = ++v261;
        goto LABEL_341;
      }
LABEL_313:
      v265 = 0;
      v261 = 0;
      memcpy_s(v262, 0x1CCu, Source, 0);
      v139 = v261;
      v149 = 0;
      v234 = v261;
      goto LABEL_343;
    }
    v160 = Source;
    v161 = v139;
    if ( v265 < v139 )
      v161 = v265;
    else
      v160 = v262;
    v253 = v160;
    v162 = v262;
    v235 = v161;
    if ( v265 < v139 )
      v148 = v139;
    else
      v162 = Source;
    v163 = 0;
    v164 = 0;
    v263 = 0;
    v165 = v162;
    while ( 1 )
    {
      v166 = v160[v164];
      if ( (_DWORD)v166 )
      {
        LODWORD(v167) = 0;
        v168 = v164;
        if ( v148 )
        {
          do
          {
            if ( v168 == 115 )
              break;
            v169 = v168;
            if ( v168 == v163 )
            {
              Src[v168] = 0;
              v263 = v168 + 1;
            }
            v170 = v168 - (unsigned int)v164;
            ++v168;
            v171 = (unsigned int)Src[v169] + (unsigned int)v167 + v166 * *((unsigned int *)v165 + v170);
            Src[v169] = v171;
            v167 = HIDWORD(v171);
            v163 = v263;
          }
          while ( v168 - (_DWORD)v164 != v148 );
          if ( (_DWORD)v167 )
          {
            do
            {
              if ( v168 == 115 )
                break;
              v172 = v168;
              if ( v168 == v163 )
              {
                Src[v168] = 0;
                v263 = v168 + 1;
              }
              ++v168;
              v173 = (unsigned int)Src[v172] + (unsigned __int64)(unsigned int)v167;
              Src[v172] = v173;
              v163 = v263;
              LODWORD(v167) = HIDWORD(v173);
            }
            while ( HIDWORD(v173) );
          }
          v161 = v235;
        }
        if ( v168 == 115 )
        {
          v261 = 0;
          memcpy_s(v262, 0x1CCu, v256, 0);
          v139 = v261;
          v149 = 0;
          v234 = v261;
LABEL_343:
          if ( !v149 )
            goto LABEL_362;
          v88 = v238 == v246;
          v143 = v238 - v246;
          v238 -= v246;
          if ( v88 )
          {
            v142 = v140 / 0xA;
            break;
          }
          goto LABEL_287;
        }
        v160 = v253;
      }
      else if ( (_DWORD)v164 == v163 )
      {
        Src[v164] = 0;
        v163 = v164 + 1;
        v263 = v164 + 1;
      }
      v164 = (unsigned int)(v164 + 1);
      if ( (_DWORD)v164 == v161 )
      {
        v155 = Src;
        v156 = 4LL * v163;
        v261 = v163;
        goto LABEL_339;
      }
    }
  }
  v174 = v140 - 10 * v142;
  if ( !v174 )
    goto LABEL_351;
  v175 = `__crt_strtox::multiply_by_power_of_ten'::`2'::small_powers_of_ten[v174 - 1];
  if ( !v175 )
  {
    v261 = 0;
    memcpy_s(v262, 0x1CCu, v256, 0);
    goto LABEL_349;
  }
  if ( v175 == 1 || !v139 )
    goto LABEL_351;
  LODWORD(v177) = 0;
  LODWORD(v4) = 0;
  v178 = (unsigned int)`__crt_strtox::multiply_by_power_of_ten'::`2'::small_powers_of_ten[v174 - 1];
  do
  {
    v179 = (unsigned int)v4;
    v4 = (unsigned int)(v4 + 1);
    v180 = (unsigned int)v177 + v178 * v262[v179];
    v262[v179] = v180;
    v177 = HIDWORD(v180);
  }
  while ( (_DWORD)v4 != v139 );
  if ( !HIDWORD(v180) )
  {
LABEL_349:
    v139 = v261;
    goto LABEL_350;
  }
  if ( v261 >= 0x73 )
  {
LABEL_362:
    v261 = 0;
    memcpy_s(v262, 0x1CCu, v256, 0);
    v181 = *(_BYTE *)(a1 + 776);
    if ( *((_BYTE *)a2 + 8) )
      *(_QWORD *)__crt_strtox::floating_point_value::as_double(a2) = -(__int64)(v181 != 0) & 0x8000000000000000uLL;
    else
      *(_DWORD *)__crt_strtox::floating_point_value::as_float(a2) = v181 != 0 ? 0x80000000 : 0;
    return 2;
  }
  else
  {
    v262[v261] = HIDWORD(v180);
    v139 = ++v261;
LABEL_350:
    v234 = v139;
LABEL_351:
    if ( v90 )
    {
      v182 = v90 - 1;
      v88 = !_BitScanReverse((unsigned int *)&v183, Destination[v182]);
      if ( v88 )
        v184 = 0;
      else
        v184 = v183 + 1;
      v176 = v184 + 32 * v182;
    }
    else
    {
      v176 = 0;
    }
    if ( v139 )
    {
      v186 = v139 - 1;
      v88 = !_BitScanReverse((unsigned int *)&v187, v262[v186]);
      if ( v88 )
        v188 = 0;
      else
        v188 = v187 + 1;
      v185 = v188 + 32 * v186;
    }
    else
    {
      v185 = 0;
    }
    v10 = 0xFFFFFFFFLL;
    v189 = v176 < v185 ? v185 - v176 : 0;
    if ( v189 )
    {
      v190 = v189 & 0x1F;
      v191 = v189 >> 5;
      v88 = !_BitScanReverse((unsigned int *)&v192, Destination[v90 - 1]);
      if ( v88 )
        v193 = 0;
      else
        v193 = v192 + 1;
      if ( v191 + v90 > 0x73 || (v194 = v90 + v191 + (v190 > 32 - v193), v194 > 0x73) )
      {
        v257 = 0;
        memcpy_s(Destination, 0x1CCu, v256, 0);
        v90 = v257;
      }
      else
      {
        v195 = v194 - 1;
        if ( (_DWORD)v195 != v191 - 1 )
        {
          while ( 1 )
          {
            v196 = (unsigned int)v195 - v191;
            v197 = (unsigned int)(v196 - 1);
            v198 = (unsigned int)v196 >= v90 ? 0 : Destination[v196];
            v199 = (unsigned int)v197 >= v90 ? 0 : Destination[v197];
            v4 = ((((unsigned int)(1LL << (32 - (unsigned __int8)v190)) - 1) & v198) << v190)
               | ((~((unsigned int)(1LL << (32 - (unsigned __int8)v190)) - 1) & v199) >> (32 - v190));
            Destination[v195] = v4;
            v195 = (unsigned int)(v195 - 1);
            if ( (_DWORD)v195 == v191 - 1 )
              break;
            v90 = v257;
          }
          v139 = v234;
        }
        v200 = 0;
        if ( v191 )
        {
          do
          {
            v201 = v200++;
            Destination[v201] = 0;
          }
          while ( v200 != v191 );
        }
        v90 = v194;
        v257 = v194;
      }
      v10 = 0xFFFFFFFFLL;
    }
    v202 = v243;
    v203 = v247 - v243;
    v248 = v203;
    v204 = v203;
    if ( v243 )
    {
      if ( v189 > v203 )
      {
        LOBYTE(v4) = 1;
        v231 = a2;
        v205 = v243;
        goto LABEL_454;
      }
      v204 = v203 - v189;
    }
    if ( v90 > v139 )
      goto LABEL_409;
    if ( v90 < v139 )
    {
      v206 = 1;
      goto LABEL_410;
    }
    v207 = v90 - 1;
    if ( !v90 )
      goto LABEL_409;
    do
    {
      if ( Destination[v207] != v262[v207] )
        break;
      v207 = (unsigned int)(v207 - 1);
    }
    while ( (_DWORD)v207 != -1 );
    if ( (_DWORD)v207 == -1 )
LABEL_409:
      v206 = 0;
    else
      v206 = Destination[v207] <= v262[v207];
LABEL_410:
    v208 = v204;
    if ( v206 )
      ++v189;
    v209 = v204 & 0x1F;
    v210 = v208 >> 5;
    v88 = !_BitScanReverse((unsigned int *)&v211, Destination[v90 - 1]);
    if ( v88 )
      v212 = 0;
    else
      v212 = v211 + 1;
    if ( v210 + v90 > 0x73 || (v213 = v90 + v210 + (v209 > 32 - v212), v213 > 0x73) )
    {
      v257 = 0;
      memcpy_s(Destination, 0x1CCu, v256, 0);
    }
    else
    {
      v214 = v213 - 1;
      if ( (_DWORD)v214 != v210 - 1 )
      {
        while ( 1 )
        {
          v215 = (unsigned int)v214 - v210;
          v216 = (unsigned int)(v215 - 1);
          v217 = (unsigned int)v215 >= v90 ? 0 : Destination[v215];
          v218 = (unsigned int)v216 >= v90 ? 0 : Destination[v216];
          v10 = ((((unsigned int)(1LL << (32 - (unsigned __int8)v209)) - 1) & v217) << v209)
              | ((~((unsigned int)(1LL << (32 - (unsigned __int8)v209)) - 1) & v218) >> (32 - v209));
          Destination[v214] = v10;
          v214 = (unsigned int)(v214 - 1);
          if ( (_DWORD)v214 == v210 - 1 )
            break;
          v90 = v257;
        }
        v202 = v243;
      }
      v219 = 0;
      if ( v210 )
      {
        do
        {
          Destination[v219] = 0;
          v219 = (unsigned int)(v219 + 1);
        }
        while ( (_DWORD)v219 != v210 );
      }
      v257 = v213;
    }
    v220 = __crt_strtox::divide(
             (__crt_strtox *)&v257,
             (struct __crt_strtox::big_integer *)&v261,
             (const struct __crt_strtox::big_integer *)v10);
    LOBYTE(v221) = v257 == 0;
    if ( v220 <= 0xFFFFFFFF )
    {
      v88 = !_BitScanReverse((unsigned int *)&v225, v220);
      if ( v88 )
        v224 = 0;
      else
        v224 = v225 + 1;
    }
    else
    {
      v88 = !_BitScanReverse((unsigned int *)&v222, HIDWORD(v220));
      if ( v88 )
        v223 = 0;
      else
        v223 = v222 + 1;
      v224 = v223 + 32;
    }
    if ( v224 > v248 )
    {
      v226 = v224 - v248;
      LOBYTE(v221) = !v257 && (((1LL << v226) - 1) & v220) == 0;
      v220 >>= v226;
    }
    v227 = 0;
    v228 = ~v189;
    if ( v6 )
      v227 = v260[0];
    v229 = 0;
    if ( v6 > 1 )
      v229 = v260[1];
    if ( v202 )
      v228 = v202 - 2;
    v230 = (v227 + ((unsigned __int64)(unsigned int)v229 << 32)) << v248;
    LOBYTE(v229) = *(_BYTE *)(a1 + 776);
    return __crt_strtox::assemble_floating_point_value(v220 + v230, v228, v229, v221, a2);
  }
}

```

## disassembly

```asm
0x180020290  mov     [rsp-8+arg_10], rbx
0x180020295  push    rbp
0x180020296  push    rsi
0x180020297  push    rdi
0x180020298  push    r12
0x18002029a  push    r13
0x18002029c  push    r14
0x18002029e  push    r15
0x1800202a0  lea     rbp, [rsp-0A70h]
0x1800202a8  sub     rsp, 0B70h
0x1800202af  mov     rax, cs:__security_cookie
0x1800202b6  xor     rax, rsp
0x1800202b9  mov     [rbp+0AA0h+var_40], rax
0x1800202c0  mov     al, [rdx+8]
0x1800202c3  lea     rbx, cs:180000000h
0x1800202ca  mov     r10d, [rcx]
0x1800202cd  neg     al
0x1800202cf  mov     r9, rcx
0x1800202d2  mov     [rsp+0BA0h+var_B40], rdx
0x1800202d7  mov     edx, [rcx+4]
0x1800202da  sbb     eax, eax
0x1800202dc  and     eax, 1Dh
0x1800202df  mov     [rsp+0BA0h+var_B48], rcx
0x1800202e4  add     eax, 19h
0x1800202e7  xor     r11d, r11d
0x1800202ea  test    r10d, r10d
0x1800202ed  mov     [rsp+0BA0h+var_B50], eax
0x1800202f1  lea     r8, [r9+8]
0x1800202f5  mov     [rbp+0AA0h+var_780], r11d
0x1800202fc  cmovs   r10d, r11d
0x180020300  mov     r14d, r11d
0x180020303  cmp     r10d, edx
0x180020306  lea     edi, [r11+26h]
0x18002030a  mov     eax, r10d
0x18002030d  mov     r15d, r11d
0x180020310  cmovnb  eax, edx
0x180020313  mov     r13d, r11d
0x180020316  sub     r10d, eax
0x180020319  mov     ecx, eax
0x18002031b  add     r8, rcx
0x18002031e  mov     [rsp+0BA0h+var_B70], r10d
0x180020323  lea     rax, [r9+8]
0x180020327  mov     [rsp+0BA0h+var_B28], r8
0x18002032c  add     rax, rdx
0x18002032f  lea     r10, [r9+8]
0x180020333  mov     [rsp+0BA0h+var_B30], rax
0x180020338  sub     eax, r8d
0x18002033b  mov     [rsp+0BA0h+var_B60], eax
0x18002033f  cmp     r10, r8
0x180020342  jz      loc_18002098F
0x180020348  cmp     r13d, 9
0x18002034c  jnz     loc_180020440
0x180020352  test    r14d, r14d
0x180020355  jz      short loc_1800203D1
0x180020357  mov     r8d, r11d
0x18002035a  mov     r9d, r11d
0x18002035d  mov     edx, r9d
0x180020360  inc     r9d
0x180020363  mov     eax, [rbp+rdx*4+0AA0h+var_77C]
0x18002036a  imul    rcx, rax, 3B9ACA00h
0x180020371  mov     eax, r8d
0x180020374  add     rcx, rax
0x180020377  mov     r8, rcx
0x18002037a  mov     [rbp+rdx*4+0AA0h+var_77C], ecx
0x180020381  shr     r8, 20h
0x180020385  cmp     r9d, r14d
0x180020388  jnz     short loc_18002035D
0x18002038a  test    r8d, r8d
0x18002038d  jz      short loc_1800203C5
0x18002038f  cmp     [rbp+0AA0h+var_780], 73h ; 's'
0x180020396  jnb     short loc_1800203B9
0x180020398  mov     eax, [rbp+0AA0h+var_780]
0x18002039e  mov     [rbp+rax*4+0AA0h+var_77C], r8d
0x1800203a6  mov     r14d, [rbp+0AA0h+var_780]
0x1800203ad  inc     r14d
0x1800203b0  mov     [rbp+0AA0h+var_780], r14d
0x1800203b7  jmp     short loc_1800203CC
0x1800203b9  mov     r14d, r11d
0x1800203bc  mov     [rbp+0AA0h+var_780], r11d
0x1800203c3  jmp     short loc_1800203CC
0x1800203c5  mov     r14d, [rbp+0AA0h+var_780]
0x1800203cc  mov     r8, [rsp+0BA0h+var_B28]
0x1800203d1  test    r15d, r15d
0x1800203d4  jz      short loc_18002043A
0x1800203d6  mov     edx, r11d
0x1800203d9  test    r14d, r14d
0x1800203dc  jz      short loc_180020407
0x1800203de  mov     ecx, edx
0x1800203e0  inc     edx
0x1800203e2  mov     r15d, r15d
0x1800203e5  mov     eax, [rbp+rcx*4+0AA0h+var_77C]
0x1800203ec  add     r15, rax
0x1800203ef  mov     [rbp+rcx*4+0AA0h+var_77C], r15d
0x1800203f7  mov     r14d, [rbp+0AA0h+var_780]
0x1800203fe  shr     r15, 20h
0x180020402  cmp     edx, r14d
0x180020405  jnz     short loc_1800203DE
0x180020407  test    r15d, r15d
0x18002040a  jz      short loc_18002043A
0x18002040c  cmp     r14d, 73h ; 's'
0x180020410  jnb     short loc_180020430
0x180020412  mov     eax, r14d
0x180020415  mov     [rbp+rax*4+0AA0h+var_77C], r15d
0x18002041d  mov     r14d, [rbp+0AA0h+var_780]
0x180020424  inc     r14d
0x180020427  mov     [rbp+0AA0h+var_780], r14d
0x18002042e  jmp     short loc_18002043A
0x180020430  mov     r14d, r11d
0x180020433  mov     [rbp+0AA0h+var_780], r11d
0x18002043a  mov     r15d, r11d
0x18002043d  mov     r13d, r11d
0x180020440  movzx   eax, byte ptr [r10]
0x180020444  lea     ecx, [r15+r15*4]
0x180020448  inc     r13d
0x18002044b  inc     r10
0x18002044e  lea     r15d, [rax+rcx*2]
0x180020452  cmp     r10, r8
0x180020455  jnz     loc_180020348
0x18002045b  test    r13d, r13d
0x18002045e  jz      loc_18002098F
0x180020464  mov     eax, 0CCCCCCCDh
0x180020469  mul     r13d
0x18002046c  mov     eax, edx
0x18002046e  shr     eax, 3
0x180020471  mov     [rsp+0BA0h+var_B68], eax
0x180020475  mov     r12d, eax
0x180020478  mov     [rsp+0BA0h+var_B64], eax
0x18002047c  test    eax, eax
0x18002047e  jz      loc_180020868
0x180020484  mov     eax, r12d
0x180020487  cmp     r12d, edi
0x18002048a  cmova   eax, edi
0x18002048d  xor     edx, edx; Val
0x18002048f  mov     [rsp+0BA0h+var_B6C], eax
0x180020493  dec     eax
0x180020495  mov     edi, eax
0x180020497  movzx   ecx, ds:rva byte_180029E22[rbx+rax*4]
0x18002049f  movzx   esi, ds:rva byte_180029E23[rbx+rax*4]
0x1800204a7  mov     ebx, ecx
0x1800204a9  shl     rbx, 2
0x1800204ad  mov     r8, rbx; Size
0x1800204b0  lea     eax, [rsi+rcx]
0x1800204b3  lea     rcx, [rbp+0AA0h+Src]; void *
0x1800204ba  mov     [rbp+0AA0h+var_3E0], eax
0x1800204c0  call    memset
0x1800204c5  lea     rcx, cs:180000000h
0x1800204cc  shl     rsi, 2
0x1800204d0  movzx   eax, ds:rva ?large_power_indices@?1??multiply_by_power_of_ten@__crt_strtox@@YA_NAEAUbig_integer@2@I@Z@4QBUunpack_index@?1??12@YA_N0I@Z@B[rcx+rdi*4]; `__crt_strtox::multiply_by_power_of_ten(__crt_strtox::big_integer &,uint)'::`2'::unpack_index const near * const `__crt_strtox::multiply_by_power_of_ten(__crt_strtox::big_integer &,uint)'::`2'::large_power_indices ...
0x1800204d8  lea     rdx, rva ?large_power_data@?1??multiply_by_power_of_ten@__crt_strtox@@YA_NAEAUbig_integer@2@I@Z@4QBIB[rcx]; uint const near * const `__crt_strtox::multiply_by_power_of_ten(__crt_strtox::big_integer &,uint)'::`2'::large_power_data ...
0x1800204df  lea     rcx, [rbp+0AA0h+Src]
0x1800204e6  mov     r8, rsi; Size
0x1800204e9  add     rcx, rbx; void *
0x1800204ec  lea     rdx, [rdx+rax*4]; Src
0x1800204f0  call    memmove
0x1800204f5  mov     r10d, [rbp+0AA0h+var_3E0]
0x1800204fc  cmp     r10d, 1
0x180020500  ja      loc_1800205B7
0x180020506  mov     eax, [rbp+0AA0h+Src]
0x18002050c  xor     r11d, r11d
0x18002050f  test    eax, eax
0x180020511  jnz     short loc_180020522
0x180020513  mov     r14d, r11d
0x180020516  mov     [rbp+0AA0h+var_780], r11d
0x18002051d  jmp     loc_18002083E
0x180020522  cmp     eax, 1
0x180020525  jz      loc_18002083E
0x18002052b  test    r14d, r14d
0x18002052e  jz      loc_18002083E
0x180020534  mov     r8d, r11d
0x180020537  mov     r9d, r11d
0x18002053a  mov     r10, rax
0x18002053d  mov     edx, r9d
0x180020540  inc     r9d
0x180020543  mov     eax, r8d
0x180020546  mov     ecx, [rbp+rdx*4+0AA0h+var_77C]
0x18002054d  imul    rcx, r10
0x180020551  add     rcx, rax
0x180020554  mov     r8, rcx
0x180020557  mov     [rbp+rdx*4+0AA0h+var_77C], ecx
0x18002055e  shr     r8, 20h
0x180020562  cmp     r9d, r14d
0x180020565  jnz     short loc_18002053D
0x180020567  test    r8d, r8d
0x18002056a  jz      short loc_1800205AB
0x18002056c  cmp     [rbp+0AA0h+var_780], 73h ; 's'
0x180020573  jnb     short loc_180020599
0x180020575  mov     eax, [rbp+0AA0h+var_780]
0x18002057b  mov     [rbp+rax*4+0AA0h+var_77C], r8d
0x180020583  mov     r14d, [rbp+0AA0h+var_780]
0x18002058a  inc     r14d
0x18002058d  mov     [rbp+0AA0h+var_780], r14d
0x180020594  jmp     loc_18002083E
0x180020599  mov     r14d, r11d
0x18002059c  mov     [rbp+0AA0h+var_780], r11d
0x1800205a3  mov     al, r11b
0x1800205a6  jmp     loc_180020840
0x1800205ab  mov     r14d, [rbp+0AA0h+var_780]
0x1800205b2  jmp     loc_18002083E
0x1800205b7  cmp     r14d, 1
0x1800205bb  ja      loc_180020675
0x1800205c1  mov     ebx, [rbp+0AA0h+var_77C]
0x1800205c7  mov     r8, r10
0x1800205ca  shl     r8, 2; Size
0x1800205ce  xor     r11d, r11d
0x1800205d1  mov     [rbp+0AA0h+var_780], r10d
0x1800205d8  mov     r14d, r10d
0x1800205db  test    r8, r8
0x1800205de  jz      short loc_180020623
0x1800205e0  mov     eax, 1CCh
0x1800205e5  lea     rcx, [rbp+0AA0h+var_77C]; void *
0x1800205ec  cmp     r8, rax
0x1800205ef  ja      short loc_1800205FF
0x1800205f1  lea     rdx, [rbp+0AA0h+Src]; Src
0x1800205f8  call    memmove
0x1800205fd  jmp     short loc_180020619
0x1800205ff  mov     r8, rax; Size
0x180020602  xor     edx, edx; Val
0x180020604  call    memset
0x180020609  call    _errno
0x18002060e  mov     dword ptr [rax], 22h ; '"'
0x180020614  call    _invalid_parameter_noinfo
0x180020619  mov     r14d, [rbp+0AA0h+var_780]
0x180020620  xor     r11d, r11d
0x180020623  test    ebx, ebx
0x180020625  jz      loc_180020513
0x18002062b  cmp     ebx, 1
0x18002062e  jz      loc_18002083E
0x180020634  test    r14d, r14d
0x180020637  jz      loc_18002083E
0x18002063d  mov     r8d, r11d
0x180020640  mov     r9d, r11d
0x180020643  mov     r10, rbx
0x180020646  mov     edx, r9d
0x180020649  inc     r9d
0x18002064c  mov     eax, r8d
0x18002064f  mov     ecx, [rbp+rdx*4+0AA0h+var_77C]
0x180020656  imul    rcx, r10
0x18002065a  add     rcx, rax
0x18002065d  mov     r8, rcx
0x180020660  mov     [rbp+rdx*4+0AA0h+var_77C], ecx
0x180020667  shr     r8, 20h
0x18002066b  cmp     r9d, r14d
0x18002066e  jnz     short loc_180020646
0x180020670  jmp     loc_180020567
0x180020675  cmp     r10d, r14d
0x180020678  lea     rdx, [rbp+0AA0h+var_77C]
0x18002067f  mov     r12d, r14d
0x180020682  lea     rcx, [rbp+0AA0h+Src]
0x180020689  cmovnb  rcx, rdx
0x18002068d  lea     r8, [rbp+0AA0h+Src]
0x180020694  cmovb   r12d, r10d
0x180020698  mov     [rsp+0BA0h+var_B38], rcx
0x18002069d  setb    al
0x1800206a0  lea     rdx, [rbp+0AA0h+var_77C]
0x1800206a7  cmovnb  rdx, r8
0x1800206ab  xor     r11d, r11d
0x1800206ae  test    al, al
0x1800206b0  mov     [rsp+0BA0h+var_B58], rdx
0x1800206b5  mov     [rbp+0AA0h+var_5B0], r11d
0x1800206bc  mov     r9d, r11d
0x1800206bf  cmovnz  r10d, r14d
0x1800206c3  mov     r14d, r11d
0x1800206c6  test    r12d, r12d
0x1800206c9  jz      loc_1800207E3
0x1800206cf  mov     eax, r9d
0x1800206d2  mov     esi, [rcx+rax*4]
0x1800206d5  test    esi, esi
0x1800206d7  jnz     short loc_1800206FA
0x1800206d9  cmp     r9d, r14d
0x1800206dc  jnz     loc_1800207D7
0x1800206e2  lea     r14d, [r9+1]
0x1800206e6  mov     [rbp+rax*4+0AA0h+var_5AC], r11d
0x1800206ee  mov     [rbp+0AA0h+var_5B0], r14d
0x1800206f5  jmp     loc_1800207D7
0x1800206fa  mov     r8d, r9d
0x1800206fd  test    r10d, r10d
0x180020700  jz      loc_1800207C0
0x180020706  mov     edi, r9d
0x180020709  neg     edi
0x18002070b  cmp     r8d, 73h ; 's'
0x18002070f  jz      short loc_18002076E
0x180020711  mov     ebx, r8d
0x180020714  cmp     r8d, r14d
0x180020717  jnz     short loc_18002072B
0x180020719  and     [rbp+rbx*4+0AA0h+var_5AC], 0
0x180020721  lea     eax, [r8+1]
0x180020725  mov     [rbp+0AA0h+var_5B0], eax
0x18002072b  lea     eax, [rdi+r8]
0x18002072f  inc     r8d
0x180020732  mov     edx, [rdx+rax*4]
0x180020735  mov     eax, r11d
0x180020738  imul    rdx, rsi
0x18002073c  add     rdx, rax
0x18002073f  mov     eax, [rbp+rbx*4+0AA0h+var_5AC]
0x180020746  add     rdx, rax
0x180020749  lea     eax, [rdi+r8]
0x18002074d  mov     r11, rdx
0x180020750  mov     [rbp+rbx*4+0AA0h+var_5AC], edx
0x180020757  mov     r14d, [rbp+0AA0h+var_5B0]
0x18002075e  shr     r11, 20h
  ... truncated ...
```
