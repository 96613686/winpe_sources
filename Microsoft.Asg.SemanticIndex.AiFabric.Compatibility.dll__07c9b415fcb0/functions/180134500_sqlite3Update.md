# sqlite3Update

- ea: `0x180134500`
- end: `0x180136b6e`
- name: `sqlite3Update`
- size: `9838`
- prototype: ``
- caller_count: `3`
- callee_count: `60`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800c5b40`
- `0x180136ef0`
- `0x180174050`

## callees

- `0x1800b99d0`
- `0x1800bd4b0`
- `0x1800c2410`
- `0x1800c6d20`
- `0x1800cf1f0`
- `0x1800d1180`
- `0x1800d1790`
- `0x1800d3b60`
- `0x1800d51e0`
- `0x1800d8230`
- `0x1800d8770`
- `0x1800f4540`
- `0x1800fdf90`
- `0x180103b10`
- `0x180104880`
- `0x180104990`
- `0x180105d30`
- `0x180106020`
- `0x180108840`
- `0x1801089d0`
- `0x180108a90`
- `0x18010b290`
- `0x18010ca80`
- `0x18010e050`
- `0x18010fd20`
- `0x180110050`
- `0x180111600`
- `0x1801138a0`
- `0x180114a70`
- `0x180114ba0`
- `0x180115870`
- `0x180118b50`
- `0x18011c960`
- `0x18011caa0`
- `0x18011d210`
- `0x18011e380`
- `0x18011f080`
- `0x18011f340`
- `0x180127eb0`
- `0x18012a170`
- `0x180130eb0`
- `0x1801314e0`
- `0x180132d10`
- `0x180134500`
- `0x1801379a0`
- `0x180137a80`
- `0x180137af0`
- `0x180137bf0`
- `0x180137ff0`
- `0x180138070`

## string_xrefs

- `0x180134b8d`: `cannot UPDATE generated column "%s"`
- `0x180136afe`: `rows updated`

## pseudocode

```c
__int64 __fastcall sqlite3Update(
        __int64 *a1,
        __int64 a2,
        int *a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v8; // rbx
  int *v9; // rsi
  int *v11; // r15
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // r12
  __int64 v15; // rdx
  signed int v16; // edi
  __int64 v17; // rax
  _QWORD *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rbx
  int v21; // r10d
  int v22; // edx
  int v23; // r14d
  bool v24; // zf
  __int64 v25; // r11
  __int64 v26; // rcx
  int v27; // r9d
  int v28; // r8d
  int v29; // edx
  int v30; // eax
  __int64 v31; // r14
  __int64 v32; // rcx
  __int64 v33; // rbx
  __int64 v34; // rax
  _DWORD *v35; // rsi
  int v36; // ecx
  __int64 v37; // rdx
  __int64 v38; // rax
  __int64 v39; // rax
  char v40; // si
  unsigned __int8 v41; // r15
  int v42; // r14d
  __int64 v43; // r15
  char v44; // di
  unsigned __int8 *v45; // rcx
  unsigned __int8 i; // al
  int v47; // r11d
  __int64 v48; // rbx
  __int64 v49; // r10
  int *v50; // rsi
  unsigned __int8 *v51; // r8
  __int64 v52; // r9
  unsigned __int8 v53; // dl
  __int64 v54; // rax
  __int64 v55; // rdi
  const char *v56; // r9
  __int64 v57; // rcx
  int v58; // eax
  unsigned __int8 v59; // di
  int v60; // edi
  int v61; // ebx
  __int64 v62; // r9
  __int64 v63; // rax
  __int64 v64; // r8
  __int64 v65; // rdx
  __int64 result; // rax
  __int64 v67; // rsi
  _DWORD *v68; // rdx
  __int16 v69; // ax
  __int64 v70; // r8
  int v71; // esi
  __int64 v72; // r14
  int v73; // r12d
  __int64 v74; // rbx
  _DWORD *v75; // r15
  _BYTE *v76; // r14
  __int64 v77; // rdx
  __int64 v78; // rcx
  int v79; // eax
  int v80; // esi
  int v81; // edi
  __int64 v82; // rcx
  int v83; // eax
  __int64 *v84; // r10
  __int64 v85; // rdx
  __int64 v86; // r8
  bool v87; // di
  __int64 *v88; // rbx
  unsigned int v89; // ecx
  int v90; // eax
  int v91; // eax
  int v92; // edx
  int v93; // edi
  int v94; // ecx
  char v95; // al
  __int64 *v96; // r10
  __int64 v97; // rax
  __int64 v98; // r11
  unsigned int v99; // ebx
  int v100; // r13d
  unsigned int v101; // eax
  __int64 v102; // rcx
  __int64 v103; // rcx
  __int64 v104; // rax
  unsigned int v105; // edi
  int v106; // edx
  __int64 v107; // r15
  unsigned int v108; // eax
  __int64 v109; // rcx
  __int64 v110; // rax
  int v111; // esi
  __int64 v112; // rbx
  unsigned __int64 v113; // r8
  __int64 v114; // rdx
  int v115; // ecx
  int v116; // eax
  int v117; // eax
  int v118; // ebx
  int v119; // edx
  __int64 v120; // rcx
  int v121; // edx
  __int64 v122; // rcx
  __int64 v123; // rax
  __int64 v124; // rcx
  __int64 v125; // rax
  int v126; // ecx
  __int64 v127; // rax
  __int64 v128; // r8
  __int64 v129; // rcx
  __int64 v130; // rax
  __int16 v131; // ax
  __int64 v132; // rax
  int v133; // eax
  __int64 *v134; // rcx
  __int64 *v135; // rcx
  __int16 v136; // si
  int v137; // r12d
  __int64 v138; // rcx
  __int64 v139; // rcx
  __int64 v140; // rax
  __int64 v141; // r15
  int v142; // r9d
  int v143; // ecx
  __int64 v144; // rdx
  __int16 v145; // si
  int v146; // edi
  __int64 v147; // rsi
  __int64 v148; // rax
  __int64 v149; // rdi
  __int64 v150; // rsi
  unsigned int v151; // edi
  unsigned int v152; // r14d
  __int64 v153; // rdx
  __int64 v154; // rcx
  __int64 v155; // rax
  __int64 v156; // rcx
  unsigned int v157; // r14d
  int v158; // eax
  __int64 v159; // rcx
  __int64 v160; // rax
  int v161; // esi
  int v162; // edi
  int v163; // edx
  _BYTE *v164; // rcx
  int v165; // edx
  __int64 *v166; // rax
  unsigned int v167; // ebx
  unsigned int v168; // edx
  __int64 v169; // rcx
  __int64 *v170; // rdi
  int v171; // esi
  unsigned int v172; // esi
  __int64 v173; // rbx
  unsigned int v174; // eax
  int v175; // ecx
  __int64 v176; // rcx
  __int64 v177; // rax
  __int64 v178; // rdx
  unsigned int v179; // ebx
  __int64 v180; // rcx
  unsigned int v181; // ebx
  __int64 v182; // rcx
  __int64 v183; // rax
  __int64 v184; // rcx
  __int16 v185; // ax
  int v186; // ebx
  unsigned int v187; // esi
  int v188; // edi
  __int64 v189; // rcx
  int v190; // edx
  __int64 v191; // rcx
  __int64 v192; // rax
  __int64 v193; // rcx
  int v194; // edx
  __int64 v195; // rcx
  __int64 v196; // rax
  unsigned int v197; // edx
  __int64 v198; // rcx
  __int64 v199; // rax
  __int64 v200; // rcx
  __int64 v201; // rcx
  __int64 v202; // rax
  __int64 v203; // rcx
  int v204; // edx
  __int64 v205; // rcx
  __int64 v206; // rax
  __int64 v207; // rcx
  __int64 v208; // r9
  __int64 v209; // rax
  int v210; // esi
  int v211; // edi
  __int64 v212; // rcx
  __int64 v213; // rax
  __int64 v214; // rbx
  __int64 v215; // r13
  int *v216; // rsi
  __int64 RowTrigger; // rax
  int v218; // esi
  signed int v219; // ebx
  __int64 v220; // rdi
  int v221; // r13d
  __int16 v222; // r11
  __int16 v223; // dx
  int v224; // r10d
  __int16 v225; // cx
  __int16 v226; // ax
  int v227; // edx
  __int64 v228; // rcx
  __int64 v229; // rcx
  __int64 v230; // rax
  __int64 v231; // rcx
  __int64 v232; // rcx
  __int64 v233; // rax
  __int64 v234; // r15
  int v235; // edi
  __int64 v236; // rbx
  __int64 v237; // r14
  __int64 v238; // rax
  signed int v239; // r9d
  signed int v240; // esi
  unsigned int v241; // ebx
  unsigned int v242; // edi
  int v243; // r13d
  __int64 v244; // rcx
  __int64 *v245; // rsi
  __int64 v246; // rdi
  unsigned int v247; // ebx
  __int64 v248; // rcx
  int v249; // eax
  __int16 v250; // r8
  __int64 v251; // rcx
  __int16 v252; // ax
  int v253; // edx
  __int64 v254; // rcx
  __int64 v255; // rcx
  __int64 v256; // rax
  __int64 v257; // rbx
  unsigned int v258; // eax
  int v259; // ecx
  __int64 v260; // rdx
  __int64 v261; // rcx
  __int64 v262; // rax
  __int64 v263; // rcx
  __int64 v264; // rax
  unsigned int v265; // eax
  int v266; // ebx
  int v267; // edi
  __int64 v268; // r12
  __int16 v269; // r8
  int v270; // eax
  __int64 v271; // rcx
  int v272; // eax
  __int64 v273; // rcx
  __int64 v274; // rax
  unsigned int v275; // edx
  __int64 v276; // rcx
  __int64 v277; // rax
  int v278; // ebx
  __int64 v279; // rcx
  unsigned int v280; // edx
  __int64 v281; // rcx
  __int64 v282; // rcx
  __int64 v283; // rax
  __int64 v284; // rcx
  __int64 v285; // rax
  int v286; // eax
  __int64 v287; // rbx
  __int64 v288; // r13
  int *v289; // r12
  __int64 v290; // rax
  unsigned int v291; // edx
  __int64 v292; // rcx
  __int64 v293; // rcx
  __int64 v294; // rax
  __int64 *v295; // rbx
  __int64 v296; // rcx
  int v297; // r13d
  int v298; // eax
  __int64 v299; // rcx
  unsigned int v300; // edx
  __int64 v301; // rcx
  __int64 v302; // rax
  __int64 v303; // rcx
  int v304; // edx
  unsigned int v305; // [rsp+28h] [rbp-E0h]
  unsigned int v306; // [rsp+40h] [rbp-C8h]
  char v307; // [rsp+78h] [rbp-90h]
  unsigned int v308; // [rsp+7Ch] [rbp-8Ch]
  unsigned __int8 v309; // [rsp+80h] [rbp-88h]
  unsigned __int8 v310; // [rsp+81h] [rbp-87h]
  unsigned int v311; // [rsp+84h] [rbp-84h]
  char v313; // [rsp+90h] [rbp-78h]
  unsigned int v314; // [rsp+94h] [rbp-74h]
  int v315; // [rsp+98h] [rbp-70h]
  int v316; // [rsp+9Ch] [rbp-6Ch]
  unsigned int v317; // [rsp+A0h] [rbp-68h]
  __int64 v318; // [rsp+A8h] [rbp-60h]
  unsigned int v319; // [rsp+B0h] [rbp-58h] BYREF
  unsigned int v320; // [rsp+B4h] [rbp-54h]
  unsigned int v321; // [rsp+B8h] [rbp-50h]
  __int64 v322; // [rsp+C0h] [rbp-48h]
  int *v323; // [rsp+C8h] [rbp-40h]
  int v324; // [rsp+D0h] [rbp-38h]
  int v325; // [rsp+D4h] [rbp-34h]
  __int64 v326; // [rsp+D8h] [rbp-30h]
  int v327; // [rsp+E0h] [rbp-28h]
  unsigned int v328; // [rsp+E4h] [rbp-24h]
  int v329; // [rsp+E8h] [rbp-20h] BYREF
  int v330; // [rsp+ECh] [rbp-1Ch]
  __int64 v331; // [rsp+F0h] [rbp-18h]
  __int64 v332; // [rsp+F8h] [rbp-10h]
  int v333; // [rsp+100h] [rbp-8h]
  int v334; // [rsp+104h] [rbp-4h]
  int v335; // [rsp+108h] [rbp+0h]
  int v336; // [rsp+10Ch] [rbp+4h]
  __int64 v337; // [rsp+110h] [rbp+8h]
  __int64 v338; // [rsp+118h] [rbp+10h]
  __int64 v339; // [rsp+120h] [rbp+18h]
  int v340; // [rsp+128h] [rbp+20h] BYREF
  unsigned int v341; // [rsp+12Ch] [rbp+24h]
  int v342; // [rsp+130h] [rbp+28h]
  int v343; // [rsp+134h] [rbp+2Ch]
  __int64 v344; // [rsp+138h] [rbp+30h]
  __int64 v345; // [rsp+140h] [rbp+38h]
  int v346; // [rsp+148h] [rbp+40h]
  unsigned int v347; // [rsp+14Ch] [rbp+44h]
  _DWORD *v348; // [rsp+150h] [rbp+48h]
  void *v349; // [rsp+158h] [rbp+50h]
  __int64 v350; // [rsp+160h] [rbp+58h]
  int v351; // [rsp+168h] [rbp+60h]
  __int64 v352; // [rsp+170h] [rbp+68h]
  __int64 v353; // [rsp+178h] [rbp+70h]
  __int64 *v354; // [rsp+180h] [rbp+78h]
  __int64 v355; // [rsp+188h] [rbp+80h]
  _QWORD v356[2]; // [rsp+190h] [rbp+88h] BYREF
  __int128 v357; // [rsp+1A0h] [rbp+98h]
  int v358; // [rsp+1B0h] [rbp+A8h]
  __int16 v359; // [rsp+1B4h] [rbp+ACh]
  __int16 v360; // [rsp+1B6h] [rbp+AEh]
  __int64 v361; // [rsp+1B8h] [rbp+B0h]
  _QWORD v362[3]; // [rsp+1C0h] [rbp+B8h] BYREF
  __int128 v363; // [rsp+1D8h] [rbp+D0h]
  int v364; // [rsp+1E8h] [rbp+E0h]
  __int64 v365; // [rsp+1ECh] [rbp+E4h]
  int v366; // [rsp+1F4h] [rbp+ECh]
  int v367; // [rsp+1F8h] [rbp+F0h] BYREF

  v8 = a4;
  v9 = a3;
  v345 = a6;
  v11 = (int *)a2;
  v350 = a7;
  v332 = a2;
  v12 = *a1;
  v339 = a8;
  v338 = a4;
  v323 = a3;
  v341 = 0;
  v353 = 0;
  v352 = 0;
  v343 = -1;
  v327 = 0;
  v321 = 0;
  LOWORD(v324) = 0;
  v367 = 0;
  v342 = 1;
  v347 = 0;
  v311 = 0;
  v320 = 0;
  v334 = 0;
  v351 = 0;
  v333 = 0;
  v314 = 0;
  v355 = 0;
  v354 = 0;
  v344 = v12;
  if ( *((_DWORD *)a1 + 12) )
    goto LABEL_90;
  v13 = sqlite3SrcListLookup(a1, v11);
  v337 = v13;
  v14 = v13;
  if ( !v13 )
    goto LABEL_90;
  v15 = *(_QWORD *)(v13 + 96);
  v16 = -32768;
  v319 = -32768;
  if ( v15 )
  {
    v17 = *a1;
    v16 = 0;
    v319 = 0;
    v18 = (_QWORD *)(*(_QWORD *)(v17 + 32) + 24LL);
    if ( *v18 != v15 )
    {
      do
      {
        ++v16;
        v18 += 4;
      }
      while ( *v18 != v15 );
      v319 = v16;
    }
  }
  if ( (*(_QWORD *)(v14 + 88) || (v19 = *(_QWORD *)(*(_QWORD *)(*a1 + 32) + 56LL)) != 0 && *(_QWORD *)(v19 + 64))
    && !*((_BYTE *)a1 + 221) )
  {
    v20 = triggersReallyExist((_DWORD)a1, v14, 129, (_DWORD)v9, (__int64)&v340);
    v331 = v20;
    v346 = v340;
  }
  else
  {
    v20 = 0;
    v346 = 0;
    v331 = 0;
  }
  v307 = *(_BYTE *)(v14 + 63);
  if ( *v11 <= 1 )
    v316 = 0;
  else
    v316 = *v9;
  if ( (*(_BYTE *)(v14 + 63) == 1 || *(__int16 *)(v14 + 54) <= 0) && (unsigned int)viewGetColumnNames(a1, v14)
    || (unsigned int)sqlite3IsReadOnly(a1, v14, v20) )
  {
    goto LABEL_89;
  }
  v21 = *((_DWORD *)a1 + 13);
  v22 = v21;
  v308 = v21;
  v335 = v21;
  v23 = v21 + 1;
  *((_DWORD *)a1 + 13) = v21 + 1;
  v24 = *(_BYTE *)(v14 + 48) >= 0;
  v336 = v21 + 1;
  if ( v24 )
  {
    v25 = 0;
    v326 = 0;
  }
  else
  {
    v25 = sqlite3PrimaryKeyIndex(v14);
    v326 = v25;
  }
  v26 = *(_QWORD *)(v14 + 16);
  v27 = 0;
  v329 = 0;
  if ( v26 )
  {
    v28 = v23;
    v29 = v23;
    do
    {
      v30 = v29;
      if ( v25 != v26 )
      {
        v29 = v28;
        v30 = v21;
      }
      ++v27;
      v21 = v30;
      v28 = v29 + 1;
      *((_DWORD *)a1 + 13) = ++v29;
      v26 = *(_QWORD *)(v26 + 40);
    }
    while ( v26 );
    v22 = v335;
    v329 = v27;
    v308 = v30;
  }
  v31 = v339;
  if ( v339 )
  {
    v21 = *(_DWORD *)(v339 + 76);
    v308 = v21;
    v336 = *(_DWORD *)(v339 + 80);
    *((_DWORD *)a1 + 13) = v22;
  }
  v32 = v344;
  v11[19] = v21;
  v33 = v27;
  v34 = sqlite3DbMallocRawNN(v32, v27 + 4LL * (v27 + *(__int16 *)(v14 + 54) + 1) + 2);
  v322 = v34;
  if ( !v34 )
    goto LABEL_89;
  v348 = (_DWORD *)(v34 + 4LL * *(__int16 *)(v14 + 54));
  v35 = &v348[v33 + 1];
  v349 = v35;
  memset(v35, 1, v33 + 1);
  *((_BYTE *)v35 + v33 + 1) = 0;
  v36 = 0;
  if ( *(__int16 *)(v14 + 54) > 0 )
  {
    v37 = v322;
    do
    {
      v38 = v36++;
      *(_DWORD *)(v37 + 4 * v38) = -1;
    }
    while ( v36 < *(__int16 *)(v14 + 54) );
  }
  v39 = a1[2];
  v365 = 0;
  v366 = 0;
  v362[0] = a1;
  v362[1] = v11;
  v362[2] = v31;
  v364 = 512;
  v318 = v39;
  v363 = 0;
  if ( !v39 )
  {
    if ( !a1[21] && (*(_BYTE *)(*a1 + 96) & 8) == 0 )
      *((_BYTE *)a1 + 35) = 1;
    v318 = sqlite3VdbeCreate(a1);
    if ( !v318 )
    {
      v9 = v323;
      goto LABEL_88;
    }
  }
  v40 = 0;
  v41 = 0;
  v313 = 0;
  v309 = 0;
  v42 = 0;
  if ( *v323 <= 0 )
  {
LABEL_78:
    v59 = v41 + v40;
    v310 = v41 + v40;
    if ( (*(_BYTE *)(v14 + 48) & 0x60) != 0 )
    {
      do
      {
        v60 = 0;
        v61 = 0;
        if ( *(__int16 *)(v14 + 54) <= 0 )
          break;
        v62 = v322;
        do
        {
          if ( *(int *)(v62 + 4LL * v61) < 0 )
          {
            v63 = *(_QWORD *)(v14 + 8);
            if ( (*(_BYTE *)(v63 + 24LL * v61 + 18) & 0x60) != 0 )
            {
              v64 = *(unsigned __int16 *)(v63 + 24LL * v61 + 16);
              if ( (_WORD)v64 )
              {
                if ( *(_BYTE *)(v14 + 63) )
                {
                  v65 = 0;
                }
                else
                {
                  v68 = *(_DWORD **)(v14 + 80);
                  if ( v68 )
                  {
                    if ( *v68 >= (int)v64 )
                      v65 = *(_QWORD *)&v68[8 * v64 - 6];
                    else
                      v65 = 0;
                  }
                  else
                  {
                    v65 = 0;
                  }
                }
              }
              else
              {
                v65 = 0;
              }
              v356[0] = 0;
              v358 = 0;
              v69 = 0;
              v359 = 0;
              v360 = 0;
              v356[1] = checkConstraintExprNode;
              v361 = v62;
              v357 = 0;
              if ( v65 )
              {
                sqlite3WalkExprNN(v356);
                v69 = v359;
                v62 = v322;
              }
              if ( !v41 )
                v69 &= ~2u;
              if ( v69 )
              {
                v60 = 1;
                *(_DWORD *)(v62 + 4LL * v61) = 99999;
              }
            }
          }
          ++v61;
        }
        while ( v61 < *(__int16 *)(v14 + 54) );
      }
      while ( v60 );
      v59 = v41 + v40;
    }
    v70 = v322;
    *(_QWORD *)(v332 + 88) = (*(_BYTE *)(v14 + 63) != 1) - 1LL;
    v71 = sqlite3FkRequired(a1, v14, v70, v59);
    v330 = v71;
    if ( a5 == 5 )
      v367 = 1;
    v72 = v337;
    v73 = 0;
    v74 = *(_QWORD *)(v337 + 16);
    if ( v74 )
    {
      v75 = v348;
      v76 = (char *)v349 + 1;
      v77 = v322;
      while ( 1 )
      {
        if ( v59
          || v71 > 1
          || (_mm_lfence(), v74 == v326)
          || (v78 = *(_QWORD *)(v74 + 72)) != 0
          && (v79 = sqlite3ExprReferencesUpdatedColumn(v78, v322, v309), v77 = v322, v79) )
        {
          v80 = ++*((_DWORD *)a1 + 14);
          *((_DWORD *)a1 + 14) = v80 + *(unsigned __int16 *)(v74 + 96);
        }
        else
        {
          v80 = 0;
          v81 = 0;
          if ( !*(_WORD *)(v74 + 94) )
            goto LABEL_130;
          while ( 1 )
          {
            v82 = *(__int16 *)(*(_QWORD *)(v74 + 8) + 2LL * v81);
            if ( (v82 & 0x8000u) != 0LL )
            {
              v83 = sqlite3ExprReferencesUpdatedColumn(*(_QWORD *)(32LL * v81 + *(_QWORD *)(v74 + 80) + 8), v322, v309);
              v77 = v322;
            }
            else
            {
              v83 = *(_DWORD *)(v77 + 4 * v82) >= 0;
            }
            if ( v83 )
              break;
            if ( ++v81 >= *(unsigned __int16 *)(v74 + 94) )
              goto LABEL_130;
          }
          v80 = ++*((_DWORD *)a1 + 14);
          *((_DWORD *)a1 + 14) = v80 + *(unsigned __int16 *)(v74 + 96);
          if ( a5 == 11 && *(_BYTE *)(v74 + 98) == 5 )
            v367 = 1;
        }
        if ( !v80 )
LABEL_130:
          *v76 = 0;
        v59 = v310;
        ++v73;
        *v75 = v80;
        ++v76;
        v74 = *(_QWORD *)(v74 + 40);
        ++v75;
        v71 = v330;
        if ( !v74 )
        {
          v72 = v337;
          break;
        }
      }
    }
    v84 = a1;
    v85 = (__int64)v348;
    *(_DWORD *)(v85 + 4LL * v73) = ++*((_DWORD *)a1 + 14);
    if ( v367 )
    {
      memset(v349, 1, v329 + 1);
      v84 = a1;
    }
    if ( !*((_BYTE *)v84 + 30) )
      *(_DWORD *)(v318 + 200) |= 0x10u;
    v86 = v331;
    v87 = v331 || v71;
    v88 = v84;
    v89 = v319;
    if ( v84[21] )
      v88 = (__int64 *)v84[21];
    v90 = *((_DWORD *)v88 + 33);
    if ( !_bittest(&v90, v319) )
    {
      *((_DWORD *)v88 + 33) = v90 | (1 << v319);
      if ( v89 == 1 )
      {
        sqlite3OpenTempDatabase(v88);
        LOBYTE(v89) = v319;
        v84 = a1;
        v86 = v331;
      }
    }
    v91 = *((_DWORD *)v88 + 32);
    *((_BYTE *)v88 + 32) |= v87;
    *((_DWORD *)v88 + 32) = v91 | (1 << v89);
    if ( *(_BYTE *)(v72 + 63) == 1 )
    {
      v93 = v333;
    }
    else
    {
      v92 = *((_DWORD *)v84 + 14) + 1;
      v311 = v92;
      v320 = v92;
      v93 = v348[v73];
      v333 = v93;
      *((_DWORD *)v84 + 14) = v92;
      if ( v313 || v86 || (v94 = v92, v71) )
      {
        v94 = v92 + *(__int16 *)(v72 + 54);
        v351 = v92 + 1;
        *((_DWORD *)v84 + 14) = v94;
      }
      if ( v310 || v86 || v71 )
      {
        v320 = ++v94;
        *((_DWORD *)v84 + 14) = v94;
      }
      v334 = v94 + 1;
      *((_DWORD *)v84 + 14) = v94 + *(__int16 *)(v72 + 54);
    }
    v95 = v307;
    if ( v307 == 2 )
    {
      v355 = v84[46];
      v84[46] = *(_QWORD *)v72;
      v95 = 2;
      v354 = v84;
    }
    if ( !v316 )
    {
      if ( v95 == 2 )
      {
        sqlite3MaterializeView((_DWORD)v84, v72, v338, v345, v350, v308);
        v345 = 0;
        v350 = 0;
      }
      if ( (unsigned int)sqlite3ResolveExprNames(v362, v338) )
        goto LABEL_529;
    }
    if ( *(_BYTE *)(v72 + 63) == 1 )
    {
      v9 = v323;
      v11 = (int *)v332;
      updateVirtualTable((_DWORD)a1, v332, v72, (_DWORD)v323, v352, v322, v338, a5);
      goto LABEL_531;
    }
    v96 = a1;
    v97 = v344;
    v98 = v339;
    v99 = *((_DWORD *)a1 + 17) - 1;
    *((_DWORD *)a1 + 17) = v99;
    v100 = v99;
    v328 = v99;
    v325 = v99;
    if ( (*(_QWORD *)(v97 + 48) & 0x100000000LL) != 0
      && !a1[22]
      && !*((_BYTE *)a1 + 30)
      && !*((_BYTE *)a1 + 219)
      && !v98 )
    {
      v347 = *((_DWORD *)a1 + 14) + 1;
      v101 = v347;
      *((_DWORD *)a1 + 14) = v347;
      sqlite3VdbeAddOp2(v318, 71, 0, v101);
      v96 = a1;
      v98 = v339;
    }
    v340 = -1;
    if ( !v316 && *(char *)(v72 + 48) >= 0 )
    {
      v102 = *(int *)(v318 + 144);
      if ( *(_DWORD *)(v318 + 148) > (int)v102 )
      {
        *(_DWORD *)(v318 + 144) = v102 + 1;
        v103 = 3 * v102;
        v104 = *(_QWORD *)(v318 + 136);
        *(_QWORD *)(v104 + 8 * v103) = 75;
        *(_DWORD *)(v104 + 8 * v103 + 8) = v93;
        *(_DWORD *)(v104 + 8 * v103 + 12) = v311;
        *(_QWORD *)(v104 + 8 * v103 + 16) = 0;
      }
      else
      {
        growOp3(v318, 75, 0, v93, v311);
        v96 = a1;
      }
      v105 = *((_DWORD *)v96 + 13);
      v106 = v333;
      v317 = v105;
      *((_DWORD *)v96 + 13) = v105 + 1;
      v107 = *(int *)(v318 + 144);
      v319 = v107;
      if ( *(_DWORD *)(v318 + 148) > (int)v107 )
      {
        v109 = 3 * v107;
        *(_DWORD *)(v318 + 144) = v107 + 1;
        v110 = *(_QWORD *)(v318 + 136);
        *(_DWORD *)(v110 + 8 * v109) = 118;
        *(_DWORD *)(v110 + 8 * v109 + 4) = v105;
        *(_DWORD *)(v110 + 8 * v109 + 8) = 0;
        *(_DWORD *)(v110 + 8 * v109 + 12) = v106;
        *(_QWORD *)(v110 + 8 * v109 + 16) = 0;
      }
      else
      {
        v108 = growOp3(v318, 118, v105, 0, v106);
        v96 = a1;
        LODWORD(v107) = v108;
        v319 = v108;
      }
      if ( v339 )
        goto LABEL_180;
      goto LABEL_206;
    }
    v114 = v326;
    if ( v326 )
      v115 = *(unsigned __int16 *)(v326 + 94);
    else
      v115 = 0;
    v116 = *((_DWORD *)v96 + 14);
    v324 = v115;
    v115 = (__int16)v115;
    v113 = (unsigned int)(v116 + 1);
    v321 = v116 + 1;
    v314 = v316 + (__int16)v115 + v116 + 1;
    *((_DWORD *)v96 + 14) = v314;
    if ( v98 )
    {
      v317 = 0;
      v105 = 0;
      v319 = 0;
      LODWORD(v107) = 0;
      if ( !v316 )
      {
LABEL_180:
        v111 = 1;
        v315 = 1;
        v353 = 0;
        sqlite3ExprIfFalse(v96, v338, v99, 16);
        LODWORD(v112) = v345;
        v113 = v308;
        v342 = 0;
        v350 = v345;
LABEL_227:
        if ( *(char *)(v72 + 48) < 0 )
        {
          v145 = v324;
          v146 = 0;
          if ( (__int16)v324 > 0 )
          {
            v147 = 0;
            do
            {
              sqlite3ExprCodeGetColumnOfTable(v318, v337, v308, *(__int16 *)(v147 + *(_QWORD *)(v326 + 8)), v146 + v321);
              ++v146;
              v147 += 2;
            }
            while ( v146 < (__int16)v324 );
            LODWORD(v112) = v350;
            LODWORD(v107) = v319;
            v100 = v325;
            v145 = v324;
          }
          v137 = v315;
          if ( !v315 )
          {
            v150 = *(_QWORD *)(v326 + 32);
            if ( !v150 )
              v150 = computeIndexAffStr(v344, v326);
            v141 = v318;
            v151 = (__int16)v324;
            v152 = v321;
            v153 = *(int *)(v318 + 144);
            if ( *(_DWORD *)(v318 + 148) > (int)v153 )
            {
              v154 = 3 * v153;
              *(_DWORD *)(v318 + 144) = v153 + 1;
              v155 = *(_QWORD *)(v318 + 136);
              *(_DWORD *)(v155 + 8 * v154) = 97;
              *(_DWORD *)(v155 + 8 * v154 + 4) = v152;
              *(_DWORD *)(v155 + 8 * v154 + 8) = v151;
              *(_DWORD *)(v155 + 8 * v154 + 12) = v314;
              *(_QWORD *)(v155 + 8 * v154 + 16) = 0;
            }
            else
            {
              v153 = (unsigned int)growOp3(v318, 97, v321, (__int16)v324, v314);
            }
            sqlite3VdbeChangeP4(v318, v153, v150, v151);
            v156 = *(int *)(v318 + 144);
            if ( *(_DWORD *)(v318 + 148) > (int)v156 )
            {
              v158 = v156 + 1;
              v157 = v317;
              v159 = 3 * v156;
              *(_DWORD *)(v318 + 144) = v158;
              v160 = *(_QWORD *)(v318 + 136);
              *(_DWORD *)(v160 + 8 * v159 + 8) = v314;
              *(_DWORD *)(v160 + 8 * v159 + 12) = v321;
              *(_DWORD *)(v160 + 8 * v159) = 64906;
              *(_DWORD *)(v160 + 8 * v159 + 4) = v317;
              *(_DWORD *)(v160 + 8 * v159 + 16) = v151;
            }
            else
            {
              v305 = v152;
              v157 = v317;
              addOp4IntSlow(v318, 138, v317, v314, v305, v151);
            }
LABEL_257:
            if ( v339 )
            {
LABEL_287:
              v170 = a1;
              v171 = v316;
              goto LABEL_288;
            }
            if ( !v316 && v137 != 2 )
              sqlite3WhereEnd(v353);
            v161 = HIDWORD(v345);
            if ( v307 != 2 )
            {
              v162 = 0;
              if ( v137 )
              {
                v163 = v335;
                v164 = v349;
                if ( (int)v112 >= 0 )
                  *((_BYTE *)v349 + (int)v112 - v335) = 0;
                if ( v161 >= 0 )
                  v164[v161 - v163] = 0;
                if ( v137 == 2 && v329 - (v161 >= 0) > 0 )
                  v162 = sqlite3VdbeAddOp0(v141, 15);
              }
              sqlite3OpenTableAndIndices((_DWORD)a1, v337, 113, 0, v335, (__int64)v349, (__int64)&v319, (__int64)&v329);
              if ( v162 )
              {
                v165 = *(_DWORD *)(v141 + 144);
                if ( v162 == v165 - 1 )
                {
                  *(_DWORD *)(v141 + 144) = v165 - 1;
                }
                else
                {
                  if ( *(_BYTE *)(*(_QWORD *)v141 + 103LL) )
                    v166 = &qword_1803DCAC0;
                  else
                    v166 = (__int64 *)(*(_QWORD *)(v141 + 136) + 24LL * v162);
                  *((_DWORD *)v166 + 2) = v165;
                }
              }
            }
            if ( v137 )
            {
              v24 = (_DWORD)v112 == v308;
              v167 = v328;
              if ( !v24 && v161 != v308 )
                sqlite3VdbeAddOp4Int(v141, 28, v308, v328, v314, v327);
              if ( v137 != 1 )
              {
                v100 = *((_DWORD *)a1 + 17) - 1;
                v325 = v100;
                *((_DWORD *)a1 + 17) = v100;
              }
              v168 = v311;
              v169 = *(int *)(v141 + 144);
              if ( v326 )
                v168 = v314;
              if ( *(_DWORD *)(v141 + 148) > (int)v169 )
              {
                *(_DWORD *)(v141 + 144) = v169 + 1;
                v176 = 3 * v169;
                v177 = *(_QWORD *)(v141 + 136);
                *(_DWORD *)(v177 + 8 * v176) = 50;
                *(_DWORD *)(v177 + 8 * v176 + 4) = v168;
                *(_DWORD *)(v177 + 8 * v176 + 8) = v167;
                *(_DWORD *)(v177 + 8 * v176 + 12) = 0;
                *(_QWORD *)(v177 + 8 * v176 + 16) = 0;
              }
              else
              {
                growOp3(v141, 50, v168, v167, 0);
              }
              goto LABEL_287;
            }
            v178 = v326;
            v171 = v316;
            if ( v326 || v316 )
            {
              v170 = a1;
              v100 = *((_DWORD *)a1 + 17) - 1;
              *((_DWORD *)a1 + 17) = v100;
              v180 = *(int *)(v141 + 144);
              v325 = v100;
              if ( *(_DWORD *)(v141 + 148) > (int)v180 )
              {
                v181 = v328;
                *(_DWORD *)(v141 + 144) = v180 + 1;
                v182 = 3 * v180;
                v183 = *(_QWORD *)(v141 + 136);
                *(_DWORD *)(v183 + 8 * v182) = 36;
                *(_DWORD *)(v183 + 8 * v182 + 4) = v157;
                *(_QWORD *)(v183 + 8 * v182 + 8) = v181;
                *(_QWORD *)(v183 + 8 * v182 + 16) = 0;
              }
              else
              {
                growOp3(v141, 36, v157, v328, 0);
                v178 = v326;
              }
              v184 = *(int *)(v141 + 144);
              v341 = *(_DWORD *)(v141 + 144);
              if ( !v316 )
              {
                if ( *(_DWORD *)(v141 + 148) > (int)v184 )
                {
                  v197 = v314;
                  *(_DWORD *)(v141 + 144) = v184 + 1;
                  v198 = 3 * v184;
                  v199 = *(_QWORD *)(v141 + 136);
                  *(_DWORD *)(v199 + 8 * v198) = 134;
                  *(_DWORD *)(v199 + 8 * v198 + 4) = v157;
                  *(_QWORD *)(v199 + 8 * v198 + 8) = v314;
                  *(_QWORD *)(v199 + 8 * v198 + 16) = 0;
                }
                else
                {
                  growOp3(v141, 134, v157, v314, 0);
                  v197 = v314;
                }
                v200 = *(int *)(v141 + 144);
                v113 = v308;
                if ( *(_DWORD *)(v141 + 148) > (int)v200 )
                {
                  *(_DWORD *)(v141 + 144) = v200 + 1;
                  v201 = 3 * v200;
                  v202 = *(_QWORD *)(v141 + 136);
                  *(_DWORD *)(v202 + 8 * v201) = 64796;
                  *(_DWORD *)(v202 + 8 * v201 + 4) = v308;
                  *(_DWORD *)(v202 + 8 * v201 + 8) = v100;
                  *(_DWORD *)(v202 + 8 * v201 + 12) = v197;
                  *(_DWORD *)(v202 + 8 * v201 + 16) = 0;
                }
                else
                {
                  addOp4IntSlow(v141, 28, v308, v100, v197, 0);
                }
LABEL_288:
                if ( v309 )
                {
                  v24 = v171 == 0;
                  v172 = v320;
                  if ( v24 )
                  {
                    if ( v170[2] )
                    {
                      v173 = v352;
                      v174 = sqlite3ExprCodeTarget(v170, v352, v320, 0);
                      v113 = v174;
                      if ( v174 != v172 )
                      {
                        if ( !v173 )
                          goto LABEL_326;
                        while ( 1 )
                        {
                          v175 = *(_DWORD *)(v173 + 4);
                          if ( (v175 & 0x82000) == 0 )
                            break;
                          if ( (v175 & 0x80000) != 0 )
                          {
                            v173 = *(_QWORD *)(*(_QWORD *)(v173 + 32) + 8LL);
                          }
                          else
                          {
                            if ( *(_BYTE *)v173 != 113 )
                              break;
                            v173 = *(_QWORD *)(v173 + 16);
                          }
                          if ( !v173 )
                            goto LABEL_326;
                        }
                        if ( (v175 & 0x400000) != 0 || *(_BYTE *)v173 == 0xB0 )
                          sqlite3VdbeAddOp2(v170[2], 80, v174, v172);
                        else
LABEL_326:
                          sqlite3VdbeAddOp2(v170[2], 81, v174, v172);
                      }
                    }
                  }
                  else
                  {
                    v203 = *(int *)(v141 + 144);
                    if ( *(_DWORD *)(v141 + 148) > (int)v203 )
                    {
                      v204 = v343;
                      *(_DWORD *)(v141 + 144) = v203 + 1;
                      v205 = 3 * v203;
                      v206 = *(_QWORD *)(v141 + 136);
                      *(_DWORD *)(v206 + 8 * v205) = 94;
                      *(_DWORD *)(v206 + 8 * v205 + 4) = v157;
                      *(_DWORD *)(v206 + 8 * v205 + 8) = v204;
                      *(_DWORD *)(v206 + 8 * v205 + 12) = v172;
                      *(_QWORD *)(v206 + 8 * v205 + 16) = 0;
                    }
                    else
                    {
                      growOp3(v141, 94, v157, v343, v320);
                    }
                  }
                  v207 = *(int *)(v141 + 144);
                  if ( *(_DWORD *)(v141 + 148) > (int)v207 )
                  {
                    v208 = 0;
                    *(_DWORD *)(v141 + 144) = v207 + 1;
                    v212 = 3 * v207;
                    v213 = *(_QWORD *)(v141 + 136);
                    *(_DWORD *)(v213 + 8 * v212) = 13;
                    *(_DWORD *)(v213 + 8 * v212 + 4) = v172;
                    *(_QWORD *)(v213 + 8 * v212 + 8) = 0;
                    *(_QWORD *)(v213 + 8 * v212 + 16) = 0;
LABEL_336:
                    if ( v313 )
                    {
                      if ( !v330 )
                      {
LABEL_339:
                        v210 = 0;
LABEL_340:
                        v211 = 0;
                        v329 = v210;
                        if ( *(_BYTE *)(v337 + 63) == 2 )
                        {
                          v211 = -1;
                        }
                        else
                        {
                          v214 = v331;
                          if ( v331 )
                          {
                            v215 = v337;
                            v216 = v323;
                            do
                            {
                              if ( *(_BYTE *)(v214 + 16) == 0x81
                                && (*(_BYTE *)(v214 + 17) & 3) != 0
                                && (unsigned int)checkColumnOverlap(*(_QWORD *)(v214 + 32), v216, v113, v208) )
                              {
                                if ( *(_BYTE *)(v214 + 18) )
                                {
                                  v211 = -1;
                                }
                                else
                                {
                                  RowTrigger = getRowTrigger(a1, v214, v215, a5);
                                  if ( RowTrigger )
                                    v211 |= *(_DWORD *)(RowTrigger + 28);
                                }
                              }
                              v214 = *(_QWORD *)(v214 + 64);
                            }
                            while ( v214 );
                            v210 = v329;
                            v208 = 0;
                            v100 = v325;
                            v157 = v317;
                            v137 = v315;
                          }
                        }
                        v218 = v211 | v210;
                        v219 = 0;
                        v220 = v337;
                        if ( *(__int16 *)(v337 + 54) > 0 )
                        {
                          v221 = v351;
                          while ( 1 )
                          {
                            v113 = *(_QWORD *)(v220 + 8);
                            v222 = *(_WORD *)(v113 + 24LL * v219 + 18);
                            if ( (*(_BYTE *)(v220 + 48) & 0x20) != 0 && (v219 & 0x8000u) == 0 )
                            {
                              v223 = v208;
                              v224 = v208;
                              if ( (__int16)v219 > 0 )
                              {
                                v113 += 18LL;
                                v208 = (unsigned int)(__int16)v219;
                                v224 = (__int16)v219;
                                do
                                {
                                  v24 = (*(_BYTE *)v113 & 0x20) == 0;
                                  v225 = v223 + 1;
                                  v113 += 24LL;
                                  if ( !v24 )
                                    v225 = v223;
                                  v223 = v225;
                                  --v208;
                                }
                                while ( v208 );
                              }
                              v226 = (*(_BYTE *)(*(_QWORD *)(v220 + 8) + 24LL * v224 + 18) & 0x20) != 0
                                   ? v224 + *(_WORD *)(v220 + 56) - v223
                                   : v223;
                            }
                            else
                            {
                              v226 = v219;
                            }
                            v227 = v221 + v226;
                            if ( v218 == -1 || v219 < 32 && _bittest(&v218, v219) )
                              break;
                            if ( (v222 & 1) != 0 )
                              break;
                            v228 = *(int *)(v318 + 144);
                            if ( *(_DWORD *)(v318 + 148) <= (int)v228 )
                            {
                              growOp3(v318, 75, 0, v227, v208);
LABEL_377:
                              v208 = 0;
                              goto LABEL_378;
                            }
                            *(_DWORD *)(v318 + 144) = v228 + 1;
                            v229 = 3 * v228;
                            v230 = *(_QWORD *)(v318 + 136);
                            *(_QWORD *)(v230 + 8 * v229) = 75;
                            *(_DWORD *)(v230 + 8 * v229 + 8) = v227;
                            *(_DWORD *)(v230 + 8 * v229 + 12) = v208;
                            *(_QWORD *)(v230 + 8 * v229 + 16) = v208;
LABEL_378:
                            if ( ++v219 >= *(__int16 *)(v220 + 54) )
                            {
                              v100 = v325;
                              v157 = v317;
                              v137 = v315;
                              goto LABEL_380;
                            }
                          }
                          sqlite3ExprCodeGetColumnOfTable(v318, v220, v308, v219, v227);
                          goto LABEL_377;
                        }
LABEL_380:
                        if ( !v309 && !v326 )
                        {
                          v231 = *(int *)(v318 + 144);
                          if ( *(_DWORD *)(v318 + 148) > (int)v231 )
                          {
                            *(_DWORD *)(v318 + 144) = v231 + 1;
                            v232 = 3 * v231;
                            v233 = *(_QWORD *)(v318 + 136);
                            *(_DWORD *)(v233 + 8 * v232 + 4) = v311;
                            *(_DWORD *)(v233 + 8 * v232 + 8) = v320;
                            *(_DWORD *)(v233 + 8 * v232) = 80;
                            *(_DWORD *)(v233 + 8 * v232 + 12) = v208;
                            *(_QWORD *)(v233 + 8 * v232 + 16) = v208;
                          }
                          else
                          {
                            growOp3(v318, 80, v311, v320, v208);
                          }
                        }
                        v209 = v331;
LABEL_386:
                        v234 = v337;
                        v235 = 0;
                        if ( *(_BYTE *)(v337 + 63) != 2 )
                        {
                          v236 = v209;
                          if ( v209 )
                          {
                            v237 = v337;
                            do
                            {
                              if ( *(_BYTE *)(v236 + 16) == 0x81
                                && (*(_BYTE *)(v236 + 17) & 1) != 0
                                && (unsigned int)checkColumnOverlap(*(_QWORD *)(v236 + 32), v323, v113, v208) )
                              {
                                if ( *(_BYTE *)(v236 + 18) )
                                {
                                  v235 = -1;
                                }
                                else
                                {
                                  v238 = getRowTrigger(a1, v236, v237, a5);
                                  if ( v238 )
                                    v235 |= *(_DWORD *)(v238 + 32);
                                }
                              }
                              v236 = *(_QWORD *)(v236 + 64);
                            }
                            while ( v236 );
                            v100 = v325;
                            v157 = v317;
                            v137 = v315;
                          }
                          v234 = v337;
                          v340 = v235;
                        }
                        LOWORD(v239) = *(_WORD *)(v234 + 54);
                        v240 = 0;
                        v241 = v334;
                        v242 = v334;
                        if ( (__int16)v239 > 0 )
                        {
                          v243 = v340;
                          while ( 1 )
                          {
                            if ( v240 == *(__int16 *)(v234 + 52) )
                            {
                              v244 = *(int *)(v318 + 144);
                              if ( *(_DWORD *)(v318 + 148) > (int)v244 )
                                goto LABEL_441;
                            }
                            else
                            {
                              v250 = *(_WORD *)(*(_QWORD *)(v234 + 8) + 24LL * v240 + 18);
                              if ( (v250 & 0x60) != 0 )
                              {
                                if ( (v250 & 0x20) != 0 )
                                  --v242;
                                goto LABEL_404;
                              }
                              v251 = *(int *)(v322 + 4LL * v240);
                              if ( (int)v251 >= 0 )
                              {
                                if ( v316 )
                                {
                                  v252 = v324;
                                  if ( v307 == 2 )
                                    v252 = v239;
                                  v253 = v251 + v252;
                                  v254 = *(int *)(v318 + 144);
                                  if ( *(_DWORD *)(v318 + 148) > (int)v254 )
                                  {
                                    *(_DWORD *)(v318 + 144) = v254 + 1;
                                    v255 = 3 * v254;
                                    v256 = *(_QWORD *)(v318 + 136);
                                    *(_DWORD *)(v256 + 8 * v255) = 94;
                                    *(_DWORD *)(v256 + 8 * v255 + 4) = v157;
                                    *(_DWORD *)(v256 + 8 * v255 + 8) = v253;
                                    *(_DWORD *)(v256 + 8 * v255 + 12) = v242;
                                    *(_QWORD *)(v256 + 8 * v255 + 16) = 0;
                                  }
                                  else
                                  {
                                    _mm_lfence();
                                    growOp3(v318, 94, v157, v253, v242);
                                  }
                                }
                                else
                                {
                                  _mm_lfence();
                                  if ( a1[2] )
                                  {
                                    v257 = *(_QWORD *)&v323[8 * v251 + 2];
                                    v258 = sqlite3ExprCodeTarget(a1, v257, v242, a1);
                                    if ( v258 != v242 )
                                    {
                                      if ( !v257 )
                                        goto LABEL_432;
                                      while ( 1 )
                                      {
                                        v259 = *(_DWORD *)(v257 + 4);
                                        if ( (v259 & 0x82000) == 0 )
                                          break;
                                        if ( (v259 & 0x80000) != 0 )
                                        {
                                          v257 = *(_QWORD *)(*(_QWORD *)(v257 + 32) + 8LL);
                                        }
                                        else
                                        {
                                          if ( *(_BYTE *)v257 != 113 )
                                            break;
                                          v257 = *(_QWORD *)(v257 + 16);
                                        }
                                        if ( !v257 )
                                          goto LABEL_432;
                                      }
                                      if ( (v259 & 0x400000) != 0 || *(_BYTE *)v257 == 0xB0 )
                                        v260 = 80;
                                      else
LABEL_432:
                                        v260 = 81;
                                      sqlite3VdbeAddOp2(a1[2], v260, v258, v242);
                                    }
                                  }
                                }
                                goto LABEL_404;
                              }
                              if ( (v346 & 1) == 0 || v240 > 31 || _bittest(&v243, v240) )
                              {
                                sqlite3ExprCodeGetColumnOfTable(v318, v234, v308, v240, v242);
                                v342 = 0;
                                goto LABEL_404;
                              }
                              v244 = *(int *)(v318 + 144);
                              if ( *(_DWORD *)(v318 + 148) > (int)v244 )
                              {
LABEL_441:
                                *(_DWORD *)(v318 + 144) = v244 + 1;
                                v261 = 3 * v244;
                                v262 = *(_QWORD *)(v318 + 136);
                                *(_QWORD *)(v262 + 8 * v261) = 75;
                                *(_DWORD *)(v262 + 8 * v261 + 8) = v242;
                                *(_DWORD *)(v262 + 8 * v261 + 12) = 0;
                                *(_QWORD *)(v262 + 8 * v261 + 16) = 0;
                                goto LABEL_404;
                              }
                            }
                            growOp3(v318, 75, 0, v242, 0);
LABEL_404:
                            v239 = *(__int16 *)(v234 + 54);
                            ++v240;
                            ++v242;
                            if ( v240 >= v239 )
                            {
                              v100 = v325;
                              v137 = v315;
                              v241 = v334;
                              break;
                            }
                          }
                        }
                        v245 = a1;
                        if ( (*(_BYTE *)(v234 + 48) & 0x60) != 0 )
                          sqlite3ComputeGeneratedColumns(a1, v241, v234);
                        if ( (v346 & 1) == 0 )
                        {
                          if ( v307 == 2 )
                            goto LABEL_498;
LABEL_462:
                          sqlite3GenerateConstraintChecks(
                            (_DWORD)a1,
                            v234,
                            (_DWORD)v348,
                            v308,
                            v336,
                            v320,
                            v311,
                            v310,
                            a5,
                            v100,
                            (__int64)&v367,
                            v322,
                            0);
                          if ( v367 || v310 )
                          {
                            v246 = v318;
                            v271 = *(int *)(v318 + 144);
                            v272 = *(_DWORD *)(v318 + 148);
                            if ( v326 )
                            {
                              if ( v272 > (int)v271 )
                              {
                                *(_DWORD *)(v318 + 144) = v271 + 1;
                                v273 = 3 * v271;
                                v274 = *(_QWORD *)(v318 + 136);
                                *(_DWORD *)(v274 + 8 * v273 + 12) = v314;
                                *(_DWORD *)(v274 + 8 * v273 + 16) = v327;
                                *(_DWORD *)(v274 + 8 * v273) = 64796;
                                *(_DWORD *)(v274 + 8 * v273 + 4) = v308;
                                *(_DWORD *)(v274 + 8 * v273 + 8) = v100;
                              }
                              else
                              {
                                addOp4IntSlow(v318, 28, v308, v100, v314, v327);
                              }
                            }
                            else
                            {
                              if ( v272 > (int)v271 )
                              {
                                v275 = v311;
                                *(_DWORD *)(v318 + 144) = v271 + 1;
                                v276 = 3 * v271;
                                v277 = *(_QWORD *)(v318 + 136);
                                *(_DWORD *)(v277 + 8 * v276) = 31;
                                *(_DWORD *)(v277 + 8 * v276 + 4) = v308;
                                *(_DWORD *)(v277 + 8 * v276 + 8) = v100;
                                *(_DWORD *)(v277 + 8 * v276 + 12) = v311;
                                *(_QWORD *)(v277 + 8 * v276 + 16) = 0;
                                goto LABEL_473;
                              }
                              growOp3(v318, 31, v308, v100, v311);
                            }
                          }
                          else
                          {
                            v246 = v318;
                          }
                          v275 = v311;
LABEL_473:
                          v278 = v330;
                          if ( v330 )
                            sqlite3FkCheck((_DWORD)a1, v234, v275, 0, v322, v310);
                          sqlite3GenerateRowIndexDelete((_DWORD)a1, v234, v308, v336, (__int64)v348, -1);
                          if ( v342 )
                          {
                            v279 = *(int *)(v246 + 144);
                            if ( *(_DWORD *)(v246 + 148) > (int)v279 )
                            {
                              v280 = v308;
                              *(_DWORD *)(v246 + 144) = v279 + 1;
                              v282 = 3 * v279;
                              v283 = *(_QWORD *)(v246 + 136);
                              *(_DWORD *)(v283 + 8 * v282) = 143;
                              *(_DWORD *)(v283 + 8 * v282 + 4) = v308;
                              *(_QWORD *)(v283 + 8 * v282 + 8) = 0;
                              *(_QWORD *)(v283 + 8 * v282 + 16) = 0;
LABEL_479:
                              if ( v278 > 1 || v310 )
                              {
                                v281 = *(int *)(v246 + 144);
                                if ( *(_DWORD *)(v246 + 148) > (int)v281 )
                                {
                                  *(_DWORD *)(v246 + 144) = v281 + 1;
                                  v284 = 3 * v281;
                                  v285 = *(_QWORD *)(v246 + 136);
                                  *(_DWORD *)(v285 + 8 * v284) = 130;
                                  *(_DWORD *)(v285 + 8 * v284 + 4) = v280;
                                  *(_QWORD *)(v285 + 8 * v284 + 8) = 0;
                                  *(_QWORD *)(v285 + 8 * v284 + 16) = 0;
                                }
                                else
                                {
                                  growOp3(v246, 130, v280, 0, 0);
                                }
                              }
                              if ( v278 )
                                sqlite3FkCheck((_DWORD)a1, v234, 0, v320, v322, v310);
                              v286 = 4;
                              if ( v137 == 2 )
                                v286 = 6;
                              sqlite3CompleteInsertion((_DWORD)a1, v234, v308, v336, v320, (__int64)v348, v286, 0, 0);
                              if ( !v278 )
                                goto LABEL_499;
                              if ( (*(_DWORD *)(*a1 + 48) & 0x4000LL) == 0 )
                                goto LABEL_499;
                              v287 = *(_QWORD *)(findElementWithHash(*(_QWORD *)(v234 + 96) + 80LL, *(_QWORD *)v234, 0)
                                               + 16);
                              if ( !v287 )
                                goto LABEL_499;
                              v288 = v322;
                              v289 = v323;
                              do
                              {
                                if ( (unsigned int)fkParentIsModified(v234, v287, v288, v310) )
                                {
                                  v290 = fkActionTrigger(a1, v234, v287, v289);
                                  if ( v290 )
                                    sqlite3CodeRowTriggerDirect((_DWORD)a1, v290, v234, v311, 2, 0);
                                }
                                v287 = *(_QWORD *)(v287 + 24);
                              }
                              while ( v287 );
                              v100 = v325;
                              v157 = v317;
                              v137 = v315;
LABEL_498:
                              v246 = v318;
LABEL_499:
                              v247 = a5;
                              goto LABEL_500;
                            }
                            growOp3(v246, 143, v308, 0, 0);
                          }
                          v280 = v308;
                          goto LABEL_479;
                        }
                        v246 = v318;
                        sqlite3TableAffinity(v318, v234, v241);
                        v247 = a5;
                        sqlite3CodeRowTrigger((_DWORD)a1, v331, 129, (_DWORD)v323, 1, v234, v311, a5, v100);
                        if ( v307 == 2 )
                        {
LABEL_500:
                          v291 = v347;
                          if ( v347 )
                          {
                            v292 = *(int *)(v246 + 144);
                            if ( *(_DWORD *)(v246 + 148) > (int)v292 )
                            {
                              *(_DWORD *)(v246 + 144) = v292 + 1;
                              v293 = 3 * v292;
                              v294 = *(_QWORD *)(v246 + 136);
                              *(_DWORD *)(v294 + 8 * v293) = 86;
                              *(_DWORD *)(v294 + 8 * v293 + 4) = v291;
                              *(_QWORD *)(v294 + 8 * v293 + 8) = 1;
                              *(_QWORD *)(v294 + 8 * v293 + 16) = 0;
                            }
                            else
                            {
                              growOp3(v246, 86, v347, 1, 0);
                            }
                          }
                          v9 = v323;
                          if ( v331 )
                          {
                            v306 = v247;
                            v295 = a1;
                            sqlite3CodeRowTrigger((_DWORD)a1, v331, 129, (_DWORD)v323, 2, v234, v311, v306, v100);
                          }
                          else
                          {
                            v295 = a1;
                          }
                          if ( v137 != 1 )
                          {
                            v296 = *(_QWORD *)(v246 + 24);
                            v297 = ~v100;
                            v298 = *(_DWORD *)(v296 + 68) + *(_DWORD *)(v296 + 72);
                            if ( v137 == 2 )
                            {
                              if ( v298 >= 0 )
                                *(_DWORD *)(*(_QWORD *)(v296 + 80) + 4LL * v297) = *(_DWORD *)(v246 + 144);
                              else
                                resizeResolveLabel(v296, v246, (unsigned int)v297);
                              sqlite3WhereEnd(v353);
                            }
                            else
                            {
                              if ( v298 >= 0 )
                                *(_DWORD *)(*(_QWORD *)(v296 + 80) + 4LL * v297) = *(_DWORD *)(v246 + 144);
                              else
                                resizeResolveLabel(v296, v246, (unsigned int)v297);
                              v299 = *(int *)(v246 + 144);
                              if ( *(_DWORD *)(v246 + 148) > (int)v299 )
                              {
                                v300 = v341;
                                *(_DWORD *)(v246 + 144) = v299 + 1;
                                v301 = 3 * v299;
                                v302 = *(_QWORD *)(v246 + 136);
                                *(_DWORD *)(v302 + 8 * v301) = 39;
                                *(_DWORD *)(v302 + 8 * v301 + 4) = v157;
                                *(_QWORD *)(v302 + 8 * v301 + 8) = v300;
                                *(_QWORD *)(v302 + 8 * v301 + 16) = 0;
                              }
                              else
                              {
                                growOp3(v246, 39, v157, v341, 0);
                              }
                            }
                          }
                          v303 = *(_QWORD *)(v246 + 24);
                          v304 = ~v328;
                          if ( *(_DWORD *)(v303 + 68) + *(_DWORD *)(v303 + 72) >= 0 )
                            *(_DWORD *)(*(_QWORD *)(v303 + 80) + 4LL * v304) = *(_DWORD *)(v246 + 144);
                          else
                            resizeResolveLabel(v303, v246, (unsigned int)v304);
                          if ( !*((_BYTE *)v295 + 30) && !v295[22] && !v339 && v295[20] )
                            autoIncrementEnd(v295);
                          if ( v347 )
                            sqlite3CodeChangeCount(v246, v347, "rows updated");
                          goto LABEL_530;
                        }
                        v248 = *(int *)(v318 + 144);
                        v249 = *(_DWORD *)(v318 + 148);
                        if ( v326 )
                        {
                          if ( v249 <= (int)v248 )
                          {
                            addOp4IntSlow(v318, 28, v308, v100, v314, v327);
LABEL_448:
                            v265 = v334;
                            v266 = 0;
                            v267 = v334;
                            if ( *(__int16 *)(v234 + 54) > 0 )
                            {
                              v268 = v322;
                              do
                              {
                                v269 = *(_WORD *)(*(_QWORD *)(v234 + 8) + 24LL * v266 + 18);
                                if ( (v269 & 0x60) != 0 )
                                {
                                  v270 = v267 - 1;
                                  if ( (v269 & 0x20) == 0 )
                                    v270 = v267;
                                  v267 = v270;
                                }
                                else if ( *(int *)(v268 + 4LL * v266) < 0 && v266 != *(__int16 *)(v234 + 52) )
                                {
                                  sqlite3ExprCodeGetColumnOfTable(v318, v234, v308, v266, v267);
                                }
                                ++v266;
                                ++v267;
                              }
                              while ( v266 < *(__int16 *)(v234 + 54) );
                              v157 = v317;
                              v137 = v315;
                              v245 = a1;
                              v265 = v334;
                            }
                            if ( (*(_BYTE *)(v234 + 48) & 0x60) != 0 )
                              sqlite3ComputeGeneratedColumns(v245, v265, v234);
                            goto LABEL_462;
                          }
                          *(_DWORD *)(v318 + 144) = v248 + 1;
                          v263 = 3 * v248;
                          v264 = *(_QWORD *)(v318 + 136);
                          *(_DWORD *)(v264 + 8 * v263 + 4) = v308;
                          *(_DWORD *)(v264 + 8 * v263 + 12) = v314;
                          *(_DWORD *)(v264 + 8 * v263 + 16) = v327;
                          *(_DWORD *)(v264 + 8 * v263) = 64796;
                        }
                        else
                        {
                          if ( v249 <= (int)v248 )
                          {
                            growOp3(v318, 31, v308, v100, v311);
                            goto LABEL_448;
                          }
                          *(_DWORD *)(v318 + 144) = v248 + 1;
                          v263 = 3 * v248;
                          v264 = *(_QWORD *)(v318 + 136);
                          *(_DWORD *)(v264 + 8 * v263 + 4) = v308;
                          *(_DWORD *)(v264 + 8 * v263 + 12) = v311;
                          *(_DWORD *)(v264 + 8 * v263) = 31;
                          *(_QWORD *)(v264 + 8 * v263 + 16) = 0;
                        }
                        *(_DWORD *)(v264 + 8 * v263 + 8) = v100;
                        goto LABEL_448;
                      }
                    }
                    else if ( !v330 )
                    {
                      v209 = v331;
                      if ( !v331 )
                        goto LABEL_386;
                      goto LABEL_339;
                    }
                    v210 = sqlite3FkOldmask(v170, v337, v113, 0);
                    v208 = 0;
                    goto LABEL_340;
                  }
                  growOp3(v141, 13, v172, 0, 0);
                }
                v208 = 0;
                goto LABEL_336;
              }
              if ( v307 == 2 )
                goto LABEL_288;
              if ( v178 )
              {
                v185 = v324;
                v186 = 0;
                v187 = v321;
                v188 = (__int16)v324;
                if ( (__int16)v324 > 0 )
                {
                  do
                  {
                    v189 = *(int *)(v141 + 144);
                    v190 = v187 + v186;
                    if ( *(_DWORD *)(v141 + 148) > (int)v189 )
                    {
                      *(_DWORD *)(v141 + 144) = v189 + 1;
                      v191 = 3 * v189;
                      v192 = *(_QWORD *)(v141 + 136);
                      *(_DWORD *)(v192 + 8 * v191) = 94;
                      *(_DWORD *)(v192 + 8 * v191 + 4) = v157;
                      *(_DWORD *)(v192 + 8 * v191 + 8) = v186;
                      *(_DWORD *)(v192 + 8 * v191 + 12) = v190;
                      *(_QWORD *)(v192 + 8 * v191 + 16) = 0;
                    }
                    else
                    {
                      growOp3(v141, 94, v157, v186, v190);
                    }
                    ++v186;
                  }
                  while ( v186 < v188 );
                  v185 = v324;
                }
                v193 = *(int *)(v141 + 144);
                v113 = v308;
                v194 = v185;
                if ( *(_DWORD *)(v141 + 148) > (int)v193 )
                {
                  *(_DWORD *)(v141 + 144) = v193 + 1;
                  v195 = 3 * v193;
                  v196 = *(_QWORD *)(v141 + 136);
                  *(_DWORD *)(v196 + 8 * v195) = 64796;
                  *(_DWORD *)(v196 + 8 * v195 + 4) = v308;
                  *(_DWORD *)(v196 + 8 * v195 + 8) = v100;
                  *(_DWORD *)(v196 + 8 * v195 + 12) = v187;
                  *(_DWORD *)(v196 + 8 * v195 + 16) = v194;
                }
                else
                {
                  addOp4IntSlow(v141, 28, v308, v100, v187, v185);
                }
                goto LABEL_287;
              }
              v179 = v311;
              sqlite3VdbeAddOp2(v141, 135, v157, v311);
            }
            else
            {
              sqlite3VdbeAddOp2(v141, 36, v157, v328);
              v170 = a1;
              v179 = v311;
              v100 = *((_DWORD *)a1 + 17) - 1;
              v325 = v100;
              *((_DWORD *)a1 + 17) = v100;
              v341 = sqlite3VdbeAddOp2(v141, 135, v157, v311);
            }
            sqlite3VdbeAddOp3(v141, 31, v308, v100, v179);
            goto LABEL_288;
          }
          if ( (_DWORD)v107 )
          {
            if ( *(_BYTE *)(*(_QWORD *)v318 + 103LL) )
            {
              v141 = v318;
            }
            else
            {
              v148 = (int)v107;
              v141 = v318;
              v149 = *(_QWORD *)(v318 + 136) + 24 * v148;
              freeP4(*(_QWORD *)v318, (unsigned int)*(char *)(v149 + 1), *(_QWORD *)(v149 + 16));
              *(_WORD *)v149 = 187;
              *(_QWORD *)(v149 + 16) = 0;
            }
            v327 = v145;
            v314 = v321;
          }
          else
          {
            v141 = v318;
            v327 = v145;
            v314 = v321;
          }
LABEL_256:
          v157 = v317;
          goto LABEL_257;
        }
        v138 = *(int *)(v318 + 144);
        if ( *(_DWORD *)(v318 + 148) > (int)v138 )
        {
          *(_DWORD *)(v318 + 144) = v138 + 1;
          v139 = 3 * v138;
          v140 = *(_QWORD *)(v318 + 136);
          *(_DWORD *)(v140 + 8 * v139 + 4) = v113;
          v113 = v311;
          *(_DWORD *)(v140 + 8 * v139 + 8) = v311;
          *(_DWORD *)(v140 + 8 * v139) = 135;
          *(_DWORD *)(v140 + 8 * v139 + 12) = 0;
          *(_QWORD *)(v140 + 8 * v139 + 16) = 0;
        }
        else
        {
          growOp3(v318, 135, v113, v311, 0);
          v113 = v311;
        }
        if ( !v111 )
        {
          v141 = v318;
          v142 = v333;
          v143 = *((_DWORD *)a1 + 14) + 1;
          *((_DWORD *)a1 + 14) = v143;
          v348[v73] = v143;
          sqlite3VdbeAddOp3(v318, 128, v105, v142, v113);
          v137 = v315;
          goto LABEL_256;
        }
        if ( (_DWORD)v107 )
        {
          v144 = (unsigned int)v107;
          v141 = v318;
          sqlite3VdbeChangeToNoop(v318, v144, v113);
          v137 = v315;
          goto LABEL_256;
        }
        v137 = v315;
LABEL_255:
        v141 = v318;
        goto LABEL_256;
      }
    }
    else
    {
      if ( v307 == 2 )
        v117 = *(__int16 *)(v72 + 54);
      else
        v117 = 0;
      v105 = *((_DWORD *)v96 + 13);
      v118 = v316 + v117 + v115;
      v317 = v105;
      *((_DWORD *)v96 + 13) = v105 + 1;
      if ( v114 )
      {
        v119 = v115 - 1;
        v120 = *(int *)(v318 + 144);
        v121 = v113 + v119;
        if ( *(_DWORD *)(v318 + 148) > (int)v120 )
        {
          *(_DWORD *)(v318 + 144) = v120 + 1;
          v122 = 3 * v120;
          v123 = *(_QWORD *)(v318 + 136);
          *(_QWORD *)(v123 + 8 * v122) = 75;
          *(_DWORD *)(v123 + 8 * v122 + 8) = v113;
          *(_DWORD *)(v123 + 8 * v122 + 12) = v121;
          *(_QWORD *)(v123 + 8 * v122 + 16) = 0;
        }
        else
        {
          growOp3(v318, 75, 0, v113, v121);
        }
      }
      v107 = *(int *)(v318 + 144);
      v319 = v107;
      if ( *(_DWORD *)(v318 + 148) > (int)v107 )
      {
        v124 = 3 * v107;
        *(_DWORD *)(v318 + 144) = v107 + 1;
        v125 = *(_QWORD *)(v318 + 136);
        *(_DWORD *)(v125 + 8 * v124) = 118;
        *(_DWORD *)(v125 + 8 * v124 + 4) = v105;
        *(_DWORD *)(v125 + 8 * v124 + 8) = v118;
        *(_DWORD *)(v125 + 8 * v124 + 12) = 0;
        *(_QWORD *)(v125 + 8 * v124 + 16) = 0;
      }
      else
      {
        LODWORD(v107) = growOp3(v318, 118, v105, v118, 0);
        v319 = v107;
      }
      v126 = v326;
      if ( v326 )
      {
        v127 = sqlite3KeyInfoOfIndex(a1, v326);
        v128 = v127;
        if ( v127 )
        {
          *(_WORD *)(v127 + 8) = v118;
          if ( *(_BYTE *)(*(_QWORD *)v318 + 103LL) )
          {
            if ( !*(_QWORD *)(*(_QWORD *)v318 + 760LL) )
            {
              v24 = (*(_DWORD *)v127)-- == 1;
              if ( v24 )
                sqlite3DbNNFreeNN(*(_QWORD *)(v127 + 16), v127);
            }
          }
          else
          {
            v129 = 3LL * *(int *)(v318 + 144);
            v130 = *(_QWORD *)(v318 + 136);
            *(_BYTE *)(v130 + 8 * v129 - 23) = -8;
            *(_QWORD *)(v130 + 8 * v129 - 8) = v128;
          }
        }
        v126 = v326;
      }
      if ( !v316 )
      {
LABEL_206:
        v131 = 4;
        if ( !*((_BYTE *)a1 + 30)
          && !v331
          && !v330
          && !v310
          && !v367
          && (!v338 || (*(_DWORD *)(v338 + 4) & 0x400000) == 0) )
        {
          v131 = 12;
        }
        v132 = sqlite3WhereBegin((_DWORD)a1, v332, v338, 0, 0, 0, v131, v336);
        v353 = v132;
        if ( v132 )
        {
          v112 = *(_QWORD *)(v132 + 40);
          v111 = *(unsigned __int8 *)(v132 + 66);
          v113 = v308;
          v133 = *(_DWORD *)(v132 + 68) & 1;
          v350 = v112;
          v345 = v112;
          v315 = v111;
          v342 = v133;
          if ( v111 != 1 )
          {
            v134 = a1;
            if ( a1[21] )
              v134 = (__int64 *)a1[21];
            *((_BYTE *)v134 + 32) = 1;
            if ( v111 == 2 && v112 >= 0 && HIDWORD(v112) != v308 && *((_BYTE *)v349 + HIDWORD(v112) - v335) )
            {
              v111 = 0;
              v315 = 0;
            }
          }
          goto LABEL_227;
        }
LABEL_529:
        v9 = v323;
LABEL_530:
        v11 = (int *)v332;
LABEL_531:
        if ( v354 )
          v354[46] = v355;
        goto LABEL_88;
      }
      updateFromSelect((_DWORD)a1, v105, v126, (_DWORD)v323, v332, v338);
      v113 = v321;
      v96 = a1;
      if ( v307 == 2 )
        v308 = v105;
    }
    v135 = v96;
    v136 = v324;
    LODWORD(v112) = v345;
    v137 = 0;
    if ( v96[21] )
      v135 = (__int64 *)v96[21];
    v315 = 0;
    v314 = v113;
    *((_BYTE *)v135 + 32) = 1;
    v327 = v136;
    goto LABEL_255;
  }
  v43 = v16;
  v9 = v323;
  while ( 2 )
  {
    v44 = 0;
    v45 = *(unsigned __int8 **)&v9[8 * v42 + 4];
    if ( v45 )
    {
      for ( i = *v45; *v45; i = *v45 )
      {
        ++v45;
        v44 += *((_BYTE *)qword_18026E880 + i);
      }
    }
    if ( !v316 && (unsigned int)sqlite3ResolveExprNames(v362, *(_QWORD *)&v9[8 * v42 + 2]) )
      goto LABEL_87;
    v47 = 0;
    v48 = 0;
    if ( *(__int16 *)(v14 + 54) <= 0 )
    {
      v55 = v322;
      goto LABEL_60;
    }
    v49 = *(_QWORD *)(v14 + 8);
    v50 = &v9[8 * v42];
    while ( *(_BYTE *)(v49 + 14) != v44 )
    {
LABEL_57:
      ++v47;
      ++v48;
      v49 += 24;
      if ( v47 >= *(unsigned __int16 *)(v14 + 54) )
      {
        v55 = v322;
        goto LABEL_59;
      }
    }
    v51 = (unsigned __int8 *)*((_QWORD *)v50 + 2);
    v52 = *(_QWORD *)v49 - (_QWORD)v51;
    while ( 1 )
    {
      v53 = v51[v52];
      v54 = *v51;
      if ( v53 == (_BYTE)v54 )
        break;
      if ( *((unsigned __int8 *)qword_18026E880 + v51[v52]) != *((unsigned __int8 *)qword_18026E880 + v54) )
        goto LABEL_57;
LABEL_56:
      ++v51;
    }
    if ( v53 )
      goto LABEL_56;
    if ( v47 == *(__int16 *)(v14 + 52) )
    {
      v55 = v322;
      v309 = 1;
      v343 = v42;
      v352 = *(_QWORD *)&v323[8 * v42 + 2];
      *(_DWORD *)(v322 + 4 * v48) = v42;
      goto LABEL_59;
    }
    if ( v326 && (*(_BYTE *)(*(_QWORD *)(v14 + 8) + 24 * v48 + 18) & 1) != 0 )
    {
      v55 = v322;
      v313 = 1;
      *(_DWORD *)(v322 + 4 * v48) = v42;
      goto LABEL_59;
    }
    v57 = *(_QWORD *)(v14 + 8);
    if ( (*(_BYTE *)(v57 + 24 * v48 + 18) & 0x60) != 0 )
    {
      sqlite3ErrorMsg(a1, "cannot UPDATE generated column \"%s\"", *(const char **)(v57 + 24LL * v47));
LABEL_86:
      v9 = v323;
      goto LABEL_87;
    }
    v55 = v322;
    *(_DWORD *)(v322 + 4 * v48) = v42;
LABEL_59:
    v9 = v323;
LABEL_60:
    if ( v47 < *(__int16 *)(v14 + 54) )
    {
      if ( v48 >= 0 )
      {
        _mm_lfence();
        v56 = *(const char **)(*(_QWORD *)(v14 + 8) + 24 * v48);
      }
      else
      {
        v56 = "ROWID";
      }
LABEL_73:
      v58 = sqlite3AuthCheck(
              (_DWORD)a1,
              23,
              *(_QWORD *)v14,
              (_DWORD)v56,
              *(_QWORD *)(32 * v43 + *(_QWORD *)(v344 + 32)));
      if ( v58 == 1 )
        goto LABEL_86;
      if ( v58 == 2 )
        *(_DWORD *)(v55 + 4 * v48) = -1;
      v9 = v323;
      if ( ++v42 >= *v323 )
      {
        v40 = v313;
        v41 = v309;
        goto LABEL_78;
      }
      continue;
    }
    break;
  }
  if ( !v326 && (unsigned int)sqlite3IsRowid(*(_QWORD *)&v9[8 * v42 + 4]) )
  {
    v56 = "ROWID";
    v48 = -1;
    v309 = 1;
    v343 = v42;
    v352 = *(_QWORD *)&v9[8 * v42 + 2];
    goto LABEL_73;
  }
  sqlite3ErrorMsg(a1, "no such column: %s", *(const char **)&v9[8 * v42 + 4]);
  *((_BYTE *)a1 + 29) = 1;
LABEL_87:
  v11 = (int *)v332;
LABEL_88:
  sqlite3DbFreeNN(v344);
LABEL_89:
  v8 = v338;
LABEL_90:
  result = sqlite3SrcListDelete(v344, v11);
  if ( v9 )
  {
    v67 = v344;
    result = exprListDeleteNN(v344);
  }
  else
  {
    v67 = v344;
  }
  if ( v8 )
    return sqlite3ExprDeleteNN(v67, v8);
  return result;
}

```

## disassembly

```asm
0x180134500  mov     r11, rsp
0x180134503  push    rbp
0x180134504  push    rbx
0x180134505  push    rsi
0x180134506  lea     rbp, [r11-148h]
0x18013450d  sub     rsp, 230h
0x180134514  mov     rax, cs:__security_cookie
0x18013451b  xor     rax, rsp
0x18013451e  mov     [rbp+140h+var_48], rax
0x180134525  mov     rax, [rbp+140h+arg_28]
0x18013452c  mov     rbx, r9
0x18013452f  mov     [r11-30h], r13
0x180134533  mov     rsi, r8
0x180134536  mov     [rbp+140h+var_108], rax
0x18013453a  mov     r13, rcx
0x18013453d  mov     rax, [rbp+140h+arg_30]
0x180134544  mov     [r11-38h], r14
0x180134548  xor     r14d, r14d
0x18013454b  mov     [r11-40h], r15
0x18013454f  mov     r15, rdx
0x180134552  mov     [rbp+140h+var_E8], rax
0x180134556  mov     rax, [rbp+140h+arg_38]
0x18013455d  mov     [rbp+140h+var_150], rdx
0x180134561  mov     rdx, [rcx]
0x180134564  mov     [rbp+140h+var_128], rax
0x180134568  mov     [rbp+140h+var_130], rbx
0x18013456c  mov     [rbp+140h+var_180], r8
0x180134570  mov     [rbp+140h+var_1C0], rcx
0x180134574  mov     [rbp+140h+var_11C], r14d
0x180134578  mov     [rbp+140h+var_D0], r14
0x18013457c  mov     [rbp+140h+var_D8], r14
0x180134580  mov     [rbp+140h+var_114], 0FFFFFFFFh
0x180134587  mov     [rbp+140h+var_168], r14d
0x18013458b  mov     [rbp+140h+var_190], r14d
0x18013458f  mov     word ptr [rbp+140h+var_178], r14w
0x180134594  mov     [rbp+140h+var_50], r14d
0x18013459b  mov     [rbp+140h+var_118], 1
0x1801345a2  mov     [rbp+140h+var_FC], r14d
0x1801345a6  mov     [rsp+7Ch], r14d
0x1801345ab  mov     [rbp+140h+var_194], r14d
0x1801345af  mov     [rbp+140h+var_144], r14d
0x1801345b3  mov     [rbp+140h+var_E0], r14d
0x1801345b7  mov     [rbp+140h+var_148], r14d
0x1801345bb  mov     [rbp+140h+var_1B4], r14d
0x1801345bf  mov     [rbp+140h+var_C0], r14
0x1801345c6  mov     [rbp+140h+var_C8], r14
0x1801345ca  mov     [rbp+140h+var_110], rdx
0x1801345ce  cmp     [rcx+30h], r14d
0x1801345d2  jnz     loc_180134BCD
0x1801345d8  mov     rdx, r15
0x1801345db  mov     [r11-28h], r12
0x1801345df  call    sqlite3SrcListLookup
0x1801345e4  mov     [rbp+140h+var_138], rax
0x1801345e8  mov     r12, rax
0x1801345eb  test    rax, rax
0x1801345ee  jz      loc_180134BC5
0x1801345f4  mov     rdx, [rax+60h]
0x1801345f8  mov     [rsp+228h], rdi
0x180134600  mov     edi, 0FFFF8000h
0x180134605  mov     [rbp+140h+var_198], edi
0x180134608  test    rdx, rdx
0x18013460b  jz      short loc_180134633
0x18013460d  mov     rax, [r13+0]
0x180134611  mov     edi, r14d
0x180134614  mov     [rbp+140h+var_198], r14d
0x180134618  mov     rcx, [rax+20h]
0x18013461c  add     rcx, 18h
0x180134620  cmp     [rcx], rdx
0x180134623  jz      short loc_180134633
0x180134625  inc     edi
0x180134627  lea     rcx, [rcx+20h]
0x18013462b  cmp     [rcx], rdx
0x18013462e  jnz     short loc_180134625
0x180134630  mov     [rbp+140h+var_198], edi
0x180134633  cmp     [r12+58h], r14
0x180134638  jnz     short loc_180134651
0x18013463a  mov     rax, [r13+0]
0x18013463e  mov     rcx, [rax+20h]
0x180134642  mov     rax, [rcx+38h]
0x180134646  test    rax, rax
0x180134649  jz      short loc_18013465A
0x18013464b  cmp     [rax+40h], r14
0x18013464f  jz      short loc_18013465A
0x180134651  cmp     [r13+0DDh], r14b
0x180134658  jz      short loc_180134667
0x18013465a  mov     rbx, r14
0x18013465d  mov     [rbp+140h+var_100], r14d
0x180134661  mov     [rbp+140h+var_158], rbx
0x180134665  jmp     short loc_180134691
0x180134667  lea     rax, [rbp+140h+var_120]
0x18013466b  mov     r9, rsi
0x18013466e  mov     r8d, 81h
0x180134674  mov     [rsp+240h+var_220], rax
0x180134679  mov     rdx, r12
0x18013467c  mov     rcx, r13
0x18013467f  call    triggersReallyExist
0x180134684  mov     rbx, rax
0x180134687  mov     [rbp+140h+var_158], rax
0x18013468b  mov     eax, [rbp+140h+var_120]
0x18013468e  mov     [rbp+140h+var_100], eax
0x180134691  cmp     dword ptr [r15], 1
0x180134695  movzx   ecx, byte ptr [r12+3Fh]
0x18013469b  mov     [rsp+240h+var_1D0], cl
0x18013469f  jle     short loc_1801346A8
0x1801346a1  mov     eax, [rsi]
0x1801346a3  mov     [rbp+140h+var_1AC], eax
0x1801346a6  jmp     short loc_1801346AC
0x1801346a8  mov     [rbp+140h+var_1AC], r14d
0x1801346ac  cmp     cl, 1
0x1801346af  jz      short loc_1801346B9
0x1801346b1  cmp     [r12+36h], r14w
0x1801346b7  jg      short loc_1801346CC
0x1801346b9  mov     rdx, r12
0x1801346bc  mov     rcx, r13
0x1801346bf  call    viewGetColumnNames
0x1801346c4  test    eax, eax
0x1801346c6  jnz     loc_180134BB9
0x1801346cc  mov     r8, rbx
0x1801346cf  mov     rdx, r12
0x1801346d2  mov     rcx, r13
0x1801346d5  call    sqlite3IsReadOnly
0x1801346da  test    eax, eax
0x1801346dc  jnz     loc_180134BB9
0x1801346e2  mov     r10d, [r13+34h]
0x1801346e6  mov     edx, r10d
0x1801346e9  mov     [rsp+240h+var_1CC], r10d
0x1801346ee  mov     [rbp+140h+var_140], edx
0x1801346f1  lea     r14d, [r10+1]
0x1801346f5  mov     [r13+34h], r14d
0x1801346f9  test    byte ptr [r12+30h], 80h
0x1801346ff  mov     [rbp+140h+var_13C], r14d
0x180134703  jnz     short loc_180134710
0x180134705  xor     eax, eax
0x180134707  mov     r11d, eax
0x18013470a  mov     [rbp+140h+var_170], rax
0x18013470e  jmp     short loc_180134721
0x180134710  mov     rcx, r12
0x180134713  call    sqlite3PrimaryKeyIndex
0x180134718  mov     r11, rax
0x18013471b  mov     [rbp+140h+var_170], rax
0x18013471f  xor     eax, eax
0x180134721  mov     rcx, [r12+10h]
0x180134726  mov     r9d, eax
0x180134729  mov     [rbp+140h+var_160], eax
0x18013472c  test    rcx, rcx
0x18013472f  jz      short loc_180134772
0x180134731  mov     r8d, r14d
0x180134734  mov     edx, r14d
0x180134737  nop     word ptr [rax+rax+00000000h]
0x180134740  cmp     r11, rcx
0x180134743  mov     eax, edx
0x180134745  cmovnz  edx, r8d
0x180134749  cmovnz  eax, r10d
0x18013474d  inc     r9d
0x180134750  mov     r10d, eax
0x180134753  lea     r8d, [rdx+1]
0x180134757  mov     [r13+34h], r8d
0x18013475b  mov     edx, r8d
0x18013475e  mov     rcx, [rcx+28h]
0x180134762  test    rcx, rcx
0x180134765  jnz     short loc_180134740
0x180134767  mov     edx, [rbp+140h+var_140]
0x18013476a  mov     [rbp+140h+var_160], r9d
0x18013476e  mov     [rsp+240h+var_1CC], eax
0x180134772  mov     r14, [rbp+140h+var_128]
0x180134776  test    r14, r14
0x180134779  jz      short loc_18013478F
0x18013477b  mov     r10d, [r14+4Ch]
0x18013477f  mov     eax, [r14+50h]
0x180134783  mov     [rsp+240h+var_1CC], r10d
0x180134788  mov     [rbp+140h+var_13C], eax
0x18013478b  mov     [r13+34h], edx
0x18013478f  mov     rcx, [rbp+140h+var_110]
0x180134793  mov     [r15+4Ch], r10d
0x180134797  movsx   eax, word ptr [r12+36h]
0x18013479d  inc     eax
0x18013479f  movsxd  rbx, r9d
0x1801347a2  add     eax, r9d
0x1801347a5  cdqe
0x1801347a7  lea     rdx, ds:2[rax*4]
0x1801347af  add     rdx, rbx
0x1801347b2  call    sqlite3DbMallocRawNN
0x1801347b7  mov     [rbp+140h+var_188], rax
0x1801347bb  mov     rcx, rax
0x1801347be  test    rax, rax
0x1801347c1  jz      loc_180134BB9
0x1801347c7  movsx   rax, word ptr [r12+36h]
0x1801347cd  lea     r8, [rbx+1]; Size
0x1801347d1  mov     edx, 1; Val
0x1801347d6  lea     rax, [rcx+rax*4]
0x1801347da  lea     rsi, [rax+4]
0x1801347de  mov     [rbp+140h+var_F8], rax
0x1801347e2  lea     rsi, [rsi+rbx*4]
0x1801347e6  mov     rcx, rsi; void *
0x1801347e9  mov     [rbp+140h+var_F0], rsi
0x1801347ed  call    memset
0x1801347f2  xor     r10d, r10d
0x1801347f5  mov     byte ptr [rbx+rsi+1], 0
0x1801347fa  mov     ecx, r10d
0x1801347fd  cmp     r10w, [r12+36h]
0x180134803  jge     short loc_180134826
0x180134805  mov     rdx, [rbp+140h+var_188]
0x180134809  nop     dword ptr [rax+00000000h]
0x180134810  movsxd  rax, ecx
0x180134813  inc     ecx
0x180134815  mov     dword ptr [rdx+rax*4], 0FFFFFFFFh
0x18013481c  movsx   eax, word ptr [r12+36h]
0x180134822  cmp     ecx, eax
0x180134824  jl      short loc_180134810
0x180134826  mov     rax, [r13+10h]
0x18013482a  xorps   xmm0, xmm0
0x18013482d  mov     [rbp+140h+var_5C], r10
0x180134834  mov     [rbp+140h+var_54], r10d
0x18013483b  mov     [rbp+140h+var_88], r13
0x180134842  mov     [rbp+140h+var_80], r15
0x180134849  mov     [rbp+140h+var_78], r14
0x180134850  mov     [rbp+140h+var_60], 200h
0x18013485a  mov     [rbp+140h+var_1A0], rax
0x18013485e  movdqu  [rbp+140h+var_70], xmm0
0x180134866  test    rax, rax
0x180134869  jnz     short loc_18013489B
0x18013486b  cmp     [r13+0A8h], r10
0x180134872  jnz     short loc_180134883
0x180134874  mov     rax, [r13+0]
0x180134878  test    byte ptr [rax+60h], 8
0x18013487c  jnz     short loc_180134883
0x18013487e  mov     byte ptr [r13+23h], 1
0x180134883  mov     rcx, r13
0x180134886  call    sqlite3VdbeCreate
0x18013488b  mov     [rbp+140h+var_1A0], rax
0x18013488f  test    rax, rax
0x180134892  jz      loc_180136B37
0x180134898  xor     r10d, r10d
0x18013489b  mov     rax, [rbp+140h+var_180]
0x18013489f  xor     sil, sil
0x1801348a2  xor     r15b, r15b
0x1801348a5  mov     [rbp+140h+var_1B8], sil
0x1801348a9  mov     [rsp+78h], r15b
0x1801348ae  mov     r14d, r10d
0x1801348b1  cmp     dword ptr [rax], 0
0x1801348b4  jle     loc_180134B11
0x1801348ba  movsxd  r15, edi
0x1801348bd  mov     rsi, rax
0x1801348c0  movsxd  rax, r14d
0x1801348c3  lea     rdx, qword_18026E880
0x1801348ca  shl     rax, 5
0x1801348ce  xor     dil, dil
0x1801348d1  mov     rcx, [rax+rsi+10h]
0x1801348d6  test    rcx, rcx
0x1801348d9  jz      short loc_180134902
0x1801348db  movzx   eax, byte ptr [rcx]
0x1801348de  test    al, al
0x1801348e0  jz      short loc_180134902
0x1801348e2  nop     dword ptr [rax+00h]
0x1801348e6  nop     word ptr [rax+rax+00000000h]
0x1801348f0  movzx   eax, al
0x1801348f3  lea     rcx, [rcx+1]
0x1801348f7  add     dil, [rax+rdx]
0x1801348fb  movzx   eax, byte ptr [rcx]
0x1801348fe  test    al, al
0x180134900  jnz     short loc_1801348F0
0x180134902  cmp     [rbp+140h+var_1AC], 0
0x180134906  jnz     short loc_18013492B
0x180134908  movsxd  rdx, r14d
0x18013490b  lea     rcx, [rbp+140h+var_88]
0x180134912  shl     rdx, 5
0x180134916  mov     rdx, [rdx+rsi+8]
0x18013491b  call    sqlite3ResolveExprNames
0x180134920  test    eax, eax
0x180134922  jnz     loc_180134BA8
0x180134928  xor     r10d, r10d
0x18013492b  mov     r11d, r10d
0x18013492e  mov     rbx, r10
0x180134931  cmp     r10w, [r12+36h]
0x180134937  jge     loc_180134A8F
0x18013493d  mov     r10, [r12+8]
0x180134942  movsxd  rax, r14d
0x180134945  shl     rax, 5
0x180134949  add     rsi, rax
0x18013494c  nop     dword ptr [rax+00h]
0x180134950  cmp     [r10+0Eh], dil
0x180134954  jnz     short loc_1801349C9
0x180134956  mov     r8, [rsi+10h]
0x18013495a  mov     r9, [r10]
0x18013495d  sub     r9, r8
0x180134960  movzx   edx, byte ptr [r9+r8]
0x180134965  movzx   eax, byte ptr [r8]
0x180134969  cmp     dl, al
0x18013496b  jnz     short loc_1801349A7
0x18013496d  test    dl, dl
0x18013496f  jnz     short loc_1801349C4
0x180134971  movsx   eax, word ptr [r12+34h]
0x180134977  cmp     r11d, eax
0x18013497a  jnz     loc_180134A46
0x180134980  mov     rsi, [rbp+140h+var_180]
0x180134984  mov     rdi, [rbp+140h+var_188]
0x180134988  movsxd  rax, r14d
0x18013498b  shl     rax, 5
0x18013498f  mov     byte ptr [rsp+78h], 1
0x180134994  mov     [rbp+140h+var_114], r14d
  ... truncated ...
```
