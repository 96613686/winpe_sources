# CVideoObjectDecoder::decodeVOPComplexityInfo(void)

- ea: `0x18002f614`
- end: `0x180031a4a`
- name: `?decodeVOPComplexityInfo@CVideoObjectDecoder@@AEAAXXZ`
- size: `9270`
- prototype: `void __fastcall(CVideoObjectDecoder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ebd0`

## callees

- `0x180002cc0`
- `0x18002f614`

## pseudocode

```c
void __fastcall CVideoObjectDecoder::decodeVOPComplexityInfo(CVideoObjectDecoder *this)
{
  int v2; // eax
  unsigned int *v3; // r9
  int v4; // r11d
  unsigned int *v5; // r8
  __int64 v6; // rax
  unsigned int v7; // eax
  unsigned int v8; // r10d
  int v9; // ecx
  unsigned int *v10; // r9
  int v11; // r11d
  unsigned int *v12; // r8
  __int64 v13; // rax
  unsigned int v14; // eax
  unsigned int v15; // r10d
  int v16; // ecx
  unsigned int *v17; // r9
  int v18; // r11d
  unsigned int *v19; // r8
  __int64 v20; // rax
  unsigned int v21; // eax
  unsigned int v22; // r10d
  int v23; // ecx
  unsigned int *v24; // r9
  int v25; // r11d
  unsigned int *v26; // r8
  __int64 v27; // rax
  unsigned int v28; // eax
  unsigned int v29; // r10d
  int v30; // ecx
  unsigned int *v31; // r9
  int v32; // r11d
  unsigned int *v33; // r8
  __int64 v34; // rax
  unsigned int v35; // eax
  unsigned int v36; // r10d
  int v37; // ecx
  unsigned int *v38; // r9
  int v39; // r11d
  unsigned int *v40; // r8
  __int64 v41; // rax
  unsigned int v42; // eax
  unsigned int v43; // r10d
  int v44; // ecx
  unsigned int *v45; // r9
  int v46; // r11d
  unsigned int *v47; // r8
  __int64 v48; // rax
  unsigned int v49; // eax
  unsigned int v50; // r10d
  int v51; // ecx
  unsigned int *v52; // r9
  int v53; // r11d
  unsigned int *v54; // r8
  __int64 v55; // rax
  unsigned int v56; // eax
  unsigned int v57; // r10d
  int v58; // ecx
  unsigned int *v59; // r9
  int v60; // r11d
  unsigned int *v61; // r8
  __int64 v62; // rax
  unsigned int v63; // eax
  unsigned int v64; // r10d
  int v65; // ecx
  unsigned int *v66; // r9
  int v67; // r11d
  unsigned int *v68; // r8
  __int64 v69; // rax
  unsigned int v70; // eax
  unsigned int v71; // r10d
  int v72; // ecx
  unsigned int *v73; // r9
  int v74; // r11d
  unsigned int *v75; // r8
  __int64 v76; // rax
  unsigned int v77; // eax
  unsigned int v78; // r10d
  int v79; // ecx
  unsigned int *v80; // r9
  int v81; // r11d
  unsigned int *v82; // r8
  __int64 v83; // rax
  unsigned int v84; // eax
  unsigned int v85; // r10d
  int v86; // ecx
  _DWORD *v87; // r9
  int v88; // r10d
  _DWORD *v89; // r8
  __int64 v90; // rax
  unsigned int v91; // edi
  __int64 v92; // rdx
  int v93; // ecx
  int v94; // eax
  char *v95; // rbx
  CInputBitStream *v96; // r9
  int v97; // r11d
  unsigned int *v98; // r8
  __int64 v99; // rax
  unsigned int v100; // eax
  unsigned int v101; // r10d
  int v102; // ecx
  unsigned int *v103; // r9
  int v104; // r11d
  unsigned int *v105; // r8
  __int64 v106; // rax
  unsigned int v107; // eax
  unsigned int v108; // r10d
  int v109; // ecx
  unsigned int *v110; // r9
  int v111; // r11d
  unsigned int *v112; // r8
  __int64 v113; // rax
  unsigned int v114; // eax
  unsigned int v115; // r10d
  int v116; // ecx
  unsigned int *v117; // r9
  int v118; // r11d
  unsigned int *v119; // r8
  __int64 v120; // rax
  unsigned int v121; // eax
  unsigned int v122; // r10d
  int v123; // ecx
  unsigned int *v124; // r9
  int v125; // r11d
  unsigned int *v126; // r8
  __int64 v127; // rax
  unsigned int v128; // eax
  unsigned int v129; // r10d
  int v130; // ecx
  unsigned int *v131; // r9
  int v132; // r11d
  unsigned int *v133; // r8
  __int64 v134; // rax
  unsigned int v135; // eax
  unsigned int v136; // r10d
  int v137; // ecx
  unsigned int *v138; // r9
  int v139; // r11d
  unsigned int *v140; // r8
  __int64 v141; // rax
  unsigned int v142; // eax
  unsigned int v143; // r10d
  int v144; // ecx
  unsigned int *v145; // r9
  int v146; // r11d
  unsigned int *v147; // r8
  __int64 v148; // rax
  unsigned int v149; // eax
  unsigned int v150; // r10d
  int v151; // ecx
  unsigned int *v152; // r9
  int v153; // r11d
  unsigned int *v154; // r8
  __int64 v155; // rax
  unsigned int v156; // eax
  unsigned int v157; // r10d
  int v158; // ecx
  unsigned int *v159; // r9
  int v160; // r11d
  unsigned int *v161; // r8
  __int64 v162; // rax
  unsigned int v163; // eax
  unsigned int v164; // r10d
  int v165; // ecx
  unsigned int *v166; // r9
  int v167; // r11d
  unsigned int *v168; // r8
  __int64 v169; // rax
  unsigned int v170; // eax
  unsigned int v171; // r10d
  int v172; // ecx
  unsigned int *v173; // r9
  int v174; // r11d
  unsigned int *v175; // r8
  __int64 v176; // rax
  unsigned int v177; // eax
  unsigned int v178; // r10d
  int v179; // ecx
  unsigned int *v180; // r9
  int v181; // r11d
  unsigned int *v182; // r8
  __int64 v183; // rax
  unsigned int v184; // eax
  unsigned int v185; // r10d
  int v186; // ecx
  unsigned int *v187; // r9
  int v188; // r11d
  unsigned int *v189; // r8
  __int64 v190; // rax
  unsigned int v191; // eax
  unsigned int v192; // r10d
  int v193; // ecx
  unsigned int *v194; // r9
  int v195; // r11d
  unsigned int *v196; // r8
  __int64 v197; // rax
  unsigned int v198; // eax
  unsigned int v199; // r10d
  int v200; // ecx
  unsigned int *v201; // r9
  int v202; // r11d
  unsigned int *v203; // r8
  __int64 v204; // rax
  unsigned int v205; // eax
  unsigned int v206; // r10d
  int v207; // ecx
  unsigned int *v208; // r9
  int v209; // r11d
  unsigned int *v210; // r8
  __int64 v211; // rax
  unsigned int v212; // eax
  unsigned int v213; // r10d
  int v214; // ecx
  unsigned int *v215; // r9
  int v216; // r11d
  unsigned int *v217; // r8
  __int64 v218; // rax
  unsigned int v219; // eax
  unsigned int v220; // r10d
  int v221; // ecx
  bool v222; // zf
  unsigned int v223; // eax
  unsigned int v224; // r10d
  __int64 v225; // rax
  unsigned int *v226; // r9
  int v227; // r11d
  unsigned int *v228; // r8
  __int64 v229; // rax
  unsigned int v230; // r10d
  __int64 v231; // rax
  unsigned int v232; // eax
  CInputBitStream *v233; // r9
  int v234; // r11d
  unsigned int *v235; // r8
  __int64 v236; // rax
  unsigned int v237; // eax
  unsigned int v238; // r10d
  int v239; // ecx
  unsigned int *v240; // r9
  int v241; // r11d
  unsigned int *v242; // r8
  __int64 v243; // rax
  unsigned int v244; // eax
  unsigned int v245; // r10d
  int v246; // ecx
  unsigned int *v247; // r9
  int v248; // r11d
  unsigned int *v249; // r8
  __int64 v250; // rax
  unsigned int v251; // eax
  unsigned int v252; // r10d
  int v253; // ecx
  unsigned int *v254; // r9
  int v255; // r11d
  unsigned int *v256; // r8
  __int64 v257; // rax
  unsigned int v258; // eax
  unsigned int v259; // r10d
  int v260; // ecx
  unsigned int *v261; // r9
  int v262; // r11d
  unsigned int *v263; // r8
  __int64 v264; // rax
  unsigned int v265; // eax
  unsigned int v266; // r10d
  int v267; // ecx
  unsigned int *v268; // r9
  int v269; // r11d
  unsigned int *v270; // r8
  __int64 v271; // rax
  unsigned int v272; // eax
  unsigned int v273; // r10d
  int v274; // ecx
  unsigned int *v275; // r9
  int v276; // r11d
  unsigned int *v277; // r8
  __int64 v278; // rax
  unsigned int v279; // eax
  unsigned int v280; // r10d
  int v281; // ecx
  unsigned int *v282; // r9
  int v283; // r11d
  unsigned int *v284; // r8
  __int64 v285; // rax
  unsigned int v286; // eax
  unsigned int v287; // r10d
  int v288; // ecx
  unsigned int *v289; // r9
  int v290; // r11d
  unsigned int *v291; // r8
  __int64 v292; // rax
  unsigned int v293; // eax
  unsigned int v294; // r10d
  int v295; // ecx
  unsigned int *v296; // r9
  int v297; // r11d
  unsigned int *v298; // r8
  __int64 v299; // rax
  unsigned int v300; // eax
  unsigned int v301; // r10d
  int v302; // ecx
  unsigned int *v303; // r9
  int v304; // r11d
  unsigned int *v305; // r8
  __int64 v306; // rax
  unsigned int v307; // eax
  unsigned int v308; // r10d
  int v309; // ecx
  unsigned int *v310; // r9
  int v311; // r11d
  unsigned int *v312; // r8
  __int64 v313; // rax
  unsigned int v314; // eax
  unsigned int v315; // r10d
  int v316; // ecx
  unsigned int *v317; // r9
  int v318; // r11d
  unsigned int *v319; // r8
  __int64 v320; // rax
  unsigned int v321; // eax
  unsigned int v322; // r10d
  int v323; // ecx
  unsigned int *v324; // r9
  int v325; // r11d
  unsigned int *v326; // r8
  __int64 v327; // rax
  unsigned int v328; // eax
  unsigned int v329; // r10d
  int v330; // ecx
  unsigned int *v331; // r9
  int v332; // r11d
  unsigned int *v333; // r8
  __int64 v334; // rax
  unsigned int v335; // eax
  unsigned int v336; // r10d
  int v337; // ecx
  unsigned int *v338; // r9
  int v339; // r11d
  unsigned int *v340; // r8
  __int64 v341; // rax
  unsigned int v342; // eax
  unsigned int v343; // r10d
  int v344; // ecx
  unsigned int *v345; // r9
  int v346; // r11d
  unsigned int *v347; // r8
  __int64 v348; // rax
  unsigned int v349; // eax
  unsigned int v350; // r10d
  int v351; // ecx
  unsigned int *v352; // r9
  int v353; // r11d
  unsigned int *v354; // r8
  __int64 v355; // rax
  unsigned int v356; // eax
  unsigned int v357; // r10d
  int v358; // ecx
  unsigned int *v359; // r9
  int v360; // r11d
  unsigned int *v361; // r8
  __int64 v362; // rax
  unsigned int v363; // eax
  unsigned int v364; // r10d
  int v365; // ecx
  unsigned int *v366; // r9
  int v367; // r11d
  unsigned int *v368; // r8
  __int64 v369; // rax
  int v370; // ecx

  if ( !*((_DWORD *)this + 71) )
  {
    v2 = *((_DWORD *)this + 210);
    if ( !v2 )
    {
      if ( (*((_DWORD *)this + 72) & 0x200000) == 0 )
        goto LABEL_14;
      v3 = (unsigned int *)*((_QWORD *)this + 675);
      if ( v3[5] || (v4 = v3[2], v5 = v3 + 4, (unsigned int)(8 * v4) < 8) && *v5 + 8 * v4 < 8 )
      {
        v3[5] = 1;
      }
      else
      {
        v6 = *v5;
        if ( (unsigned int)v6 >= 8 )
        {
          v7 = v6 - 8;
LABEL_9:
          *v5 = v7;
          goto LABEL_14;
        }
        v8 = 8 - v6;
        if ( v4 >= 4 )
        {
          v9 = *(unsigned __int8 *)(*(_QWORD *)v3 + 3LL)
             | ((*(unsigned __int8 *)(*(_QWORD *)v3 + 2LL)
               | ((*(unsigned __int8 *)(*(_QWORD *)v3 + 1LL) | (**(unsigned __int8 **)v3 << 8)) << 8)) << 8);
          *(_QWORD *)v3 += 4LL;
          v3[2] = v4 - 4;
          v7 = 32 - v8;
          v3[3] = v9;
          goto LABEL_9;
        }
        CInputBitStream::finalLoad((CInputBitStream *)v3, v3[3] & *((_DWORD *)&GetMask + v6), v8);
      }
LABEL_14:
      if ( (*((_DWORD *)this + 72) & 0x100000) == 0 )
        goto LABEL_25;
      v10 = (unsigned int *)*((_QWORD *)this + 675);
      if ( v10[5] || (v11 = v10[2], v12 = v10 + 4, (unsigned int)(8 * v11) < 8) && *v12 + 8 * v11 < 8 )
      {
        v10[5] = 1;
      }
      else
      {
        v13 = *v12;
        if ( (unsigned int)v13 >= 8 )
        {
          v14 = v13 - 8;
LABEL_20:
          *v12 = v14;
          goto LABEL_25;
        }
        v15 = 8 - v13;
        if ( v11 >= 4 )
        {
          v16 = *(unsigned __int8 *)(*(_QWORD *)v10 + 3LL)
              | ((*(unsigned __int8 *)(*(_QWORD *)v10 + 2LL)
                | ((*(unsigned __int8 *)(*(_QWORD *)v10 + 1LL) | (**(unsigned __int8 **)v10 << 8)) << 8)) << 8);
          *(_QWORD *)v10 += 4LL;
          v10[2] = v11 - 4;
          v14 = 32 - v15;
          v10[3] = v16;
          goto LABEL_20;
        }
        CInputBitStream::finalLoad(*((CInputBitStream **)this + 675), v10[3] & *((_DWORD *)&GetMask + v13), v15);
      }
LABEL_25:
      if ( (*((_DWORD *)this + 72) & 0x80000) == 0 )
        goto LABEL_36;
      v17 = (unsigned int *)*((_QWORD *)this + 675);
      if ( v17[5] || (v18 = v17[2], v19 = v17 + 4, (unsigned int)(8 * v18) < 8) && *v19 + 8 * v18 < 8 )
      {
        v17[5] = 1;
      }
      else
      {
        v20 = *v19;
        if ( (unsigned int)v20 >= 8 )
        {
          v21 = v20 - 8;
LABEL_31:
          *v19 = v21;
          goto LABEL_36;
        }
        v22 = 8 - v20;
        if ( v18 >= 4 )
        {
          v23 = *(unsigned __int8 *)(*(_QWORD *)v17 + 3LL)
              | ((*(unsigned __int8 *)(*(_QWORD *)v17 + 2LL)
                | (((**(unsigned __int8 **)v17 << 8) | *(unsigned __int8 *)(*(_QWORD *)v17 + 1LL)) << 8)) << 8);
          *(_QWORD *)v17 += 4LL;
          v17[2] = v18 - 4;
          v21 = 32 - v22;
          v17[3] = v23;
          goto LABEL_31;
        }
        CInputBitStream::finalLoad(*((CInputBitStream **)this + 675), v17[3] & *((_DWORD *)&GetMask + v20), v22);
      }
LABEL_36:
      if ( (*((_DWORD *)this + 72) & 0x40000) == 0 )
        goto LABEL_47;
      v24 = (unsigned int *)*((_QWORD *)this + 675);
      if ( v24[5] || (v25 = v24[2], v26 = v24 + 4, (unsigned int)(8 * v25) < 8) && *v26 + 8 * v25 < 8 )
      {
        v24[5] = 1;
      }
      else
      {
        v27 = *v26;
        if ( (unsigned int)v27 >= 8 )
        {
          v28 = v27 - 8;
LABEL_42:
          *v26 = v28;
          goto LABEL_47;
        }
        v29 = 8 - v27;
        if ( v25 >= 4 )
        {
          v30 = *(unsigned __int8 *)(*(_QWORD *)v24 + 3LL)
              | ((*(unsigned __int8 *)(*(_QWORD *)v24 + 2LL)
                | (((**(unsigned __int8 **)v24 << 8) | *(unsigned __int8 *)(*(_QWORD *)v24 + 1LL)) << 8)) << 8);
          *(_QWORD *)v24 += 4LL;
          v24[2] = v25 - 4;
          v28 = 32 - v29;
          v24[3] = v30;
          goto LABEL_42;
        }
        CInputBitStream::finalLoad(*((CInputBitStream **)this + 675), v24[3] & *((_DWORD *)&GetMask + v27), v29);
      }
LABEL_47:
      if ( (*((_DWORD *)this + 72) & 0x20000) == 0 )
        goto LABEL_58;
      v31 = (unsigned int *)*((_QWORD *)this + 675);
      if ( v31[5] || (v32 = v31[2], v33 = v31 + 4, (unsigned int)(8 * v32) < 8) && *v33 + 8 * v32 < 8 )
      {
        v31[5] = 1;
      }
      else
      {
        v34 = *v33;
        if ( (unsigned int)v34 >= 8 )
        {
          v35 = v34 - 8;
LABEL_53:
          *v33 = v35;
          goto LABEL_58;
        }
        v36 = 8 - v34;
        if ( v32 >= 4 )
        {
          v37 = *(unsigned __int8 *)(*(_QWORD *)v31 + 3LL)
              | ((*(unsigned __int8 *)(*(_QWORD *)v31 + 2LL)
                | ((*(unsigned __int8 *)(*(_QWORD *)v31 + 1LL) | (**(unsigned __int8 **)v31 << 8)) << 8)) << 8);
          *(_QWORD *)v31 += 4LL;
          v31[2] = v32 - 4;
          v35 = 32 - v36;
          v31[3] = v37;
          goto LABEL_53;
        }
        CInputBitStream::finalLoad(*((CInputBitStream **)this + 675), v31[3] & *((_DWORD *)&GetMask + v34), v36);
      }
LABEL_58:
      if ( (*((_DWORD *)this + 72) & 0x10000) == 0 )
        goto LABEL_69;
      v38 = (unsigned int *)*((_QWORD *)this + 675);
      if ( v38[5] || (v39 = v38[2], v40 = v38 + 4, (unsigned int)(8 * v39) < 8) && *v40 + 8 * v39 < 8 )
      {
        v38[5] = 1;
      }
      else
      {
        v41 = *v40;
        if ( (unsigned int)v41 >= 8 )
        {
          v42 = v41 - 8;
LABEL_64:
          *v40 = v42;
          goto LABEL_69;
        }
        v43 = 8 - v41;
        if ( v39 >= 4 )
        {
          v44 = *(unsigned __int8 *)(*(_QWORD *)v38 + 3LL)
              | ((*(unsigned __int8 *)(*(_QWORD *)v38 + 2LL)
                | (((**(unsigned __int8 **)v38 << 8) | *(unsigned __int8 *)(*(_QWORD *)v38 + 1LL)) << 8)) << 8);
          *(_QWORD *)v38 += 4LL;
          v38[2] = v39 - 4;
          v42 = 32 - v43;
          v38[3] = v44;
          goto LABEL_64;
        }
        CInputBitStream::finalLoad(*((CInputBitStream **)this + 675), v38[3] & *((_DWORD *)&GetMask + v41), v43);
      }
LABEL_69:
      if ( (*((_DWORD *)this + 72) & 0x8000) == 0 )
        goto LABEL_80;
      v45 = (unsigned int *)*((_QWORD *)this + 675);
      if ( v45[5] || (v46 = v45[2], v47 = v45 + 4, (unsigned int)(8 * v46) < 8) && *v47 + 8 * v46 < 8 )
      {
        v45[5] = 1;
      }
      else
      {
        v48 = *v47;
        if ( (unsigned int)v48 >= 8 )
        {
          v49 = v48 - 8;
LABEL_75:
          *v47 = v49;
          goto LABEL_80;
        }
        v50 = 8 - v48;
        if ( v46 >= 4 )
        {
          v51 = *(unsigned __int8 *)(*(_QWORD *)v45 + 3LL)
              | ((*(unsigned __int8 *)(*(_QWORD *)v45 + 2LL)
                | (((**(unsigned __int8 **)v45 << 8) | *(unsigned __int8 *)(*(_QWORD *)v45 + 1LL)) << 8)) << 8);
          *(_QWORD *)v45 += 4LL;
          v45[2] = v46 - 4;
          v49 = 32 - v50;
          v45[3] = v51;
          goto LABEL_75;
        }
        CInputBitStream::finalLoad(*((CInputBitStream **)this + 675), v45[3] & *((_DWORD *)&GetMask + v48), v50);
      }
LABEL_80:
      if ( (*((_DWORD *)this + 72) & 0x1000) == 0 )
        goto LABEL_91;
      v52 = (unsigned int *)*((_QWORD *)this + 675);
      if ( v52[5] || (v53 = v52[2], v54 = v52 + 4, (unsigned int)(8 * v53) < 8) && *v54 + 8 * v53 < 8 )
      {
        v52[5] = 1;
      }
      else
      {
        v55 = *v54;
        if ( (unsigned int)v55 >= 8 )
        {
          v56 = v55 - 8;
LABEL_86:
          *v54 = v56;
          goto LABEL_91;
        }
        v57 = 8 - v55;
        if ( v53 >= 4 )
        {
          v58 = *(unsigned __int8 *)(*(_QWORD *)v52 + 3LL)
              | ((*(unsigned __int8 *)(*(_QWORD *)v52 + 2LL)
                | (((**(unsigned __int8 **)v52 << 8) | *(unsigned __int8 *)(*(_QWORD *)v52 + 1LL)) << 8)) << 8);
          *(_QWORD *)v52 += 4LL;
          v52[2] = v53 - 4;
          v56 = 32 - v57;
          v52[3] = v58;
          goto LABEL_86;
        }
        CInputBitStream::finalLoad(*((CInputBitStream **)this + 675), v52[3] & *((_DWORD *)&GetMask + v55), v57);
      }
LABEL_91:
      if ( (*((_DWORD *)this + 72) & 0x800) == 0 )
        goto LABEL_102;
      v59 = (unsigned int *)*((_QWORD *)this + 675);
      if ( v59[5] || (v60 = v59[2], v61 = v59 + 4, (unsigned int)(8 * v60) < 8) && *v61 + 8 * v60 < 8 )
      {
        v59[5] = 1;
      }
      else
      {
        v62 = *v61;
        if ( (unsigned int)v62 >= 8 )
        {
          v63 = v62 - 8;
LABEL_97:
          *v61 = v63;
          goto LABEL_102;
        }
        v64 = 8 - v62;
        if ( v60 >= 4 )
        {
          v65 = *(unsigned __int8 *)(*(_QWORD *)v59 + 3LL)
              | ((*(unsigned __int8 *)(*(_QWORD *)v59 + 2LL)
                | (((**(unsigned __int8 **)v59 << 8) | *(unsigned __int8 *)(*(_QWORD *)v59 + 1LL)) << 8)) << 8);
          *(_QWORD *)v59 += 4LL;
          v59[2] = v60 - 4;
          v63 = 32 - v64;
          v59[3] = v65;
          goto LABEL_97;
        }
        CInputBitStream::finalLoad(*((CInputBitStream **)this + 675), v59[3] & *((_DWORD *)&GetMask + v62), v64);
      }
LABEL_102:
      if ( (*((_DWORD *)this + 72) & 0x400) == 0 )
        goto LABEL_113;
      v66 = (unsigned int *)*((_QWORD *)this + 675);
      if ( v66[5] || (v67 = v66[2], v68 = v66 + 4, (unsigned int)(8 * v67) < 8) && *v68 + 8 * v67 < 8 )
      {
        v66[5] = 1;
      }
      else
      {
        v69 = *v68;
        if ( (unsigned int)v69 >= 8 )
        {
          v70 = v69 - 8;
LABEL_108:
          *v68 = v70;
          goto LABEL_113;
        }
        v71 = 8 - v69;
        if ( v67 >= 4 )
        {
          v72 = *(unsigned __int8 *)(*(_QWORD *)v66 + 3LL)
              | ((*(unsigned __int8 *)(*(_QWORD *)v66 + 2LL)
                | (((**(unsigned __int8 **)v66 << 8) | *(unsigned __int8 *)(*(_QWORD *)v66 + 1LL)) << 8)) << 8);
          *(_QWORD *)v66 += 4LL;
          v66[2] = v67 - 4;
          v70 = 32 - v71;
          v66[3] = v72;
          goto LABEL_108;
        }
        CInputBitStream::finalLoad(*((CInputBitStream **)this + 675), v66[3] & *((_DWORD *)&GetMask + v69), v71);
      }
LABEL_113:
      if ( (*((_DWORD *)this + 72) & 0x200) == 0 )
        goto LABEL_124;
      v73 = (unsigned int *)*((_QWORD *)this + 675);
      if ( v73[5] || (v74 = v73[2], v75 = v73 + 4, (unsigned int)(8 * v74) < 8) && *v75 + 8 * v74 < 8 )
      {
        v73[5] = 1;
      }
      else
      {
        v76 = *v75;
        if ( (unsigned int)v76 >= 8 )
        {
          v77 = v76 - 8;
LABEL_119:
          *v75 = v77;
          goto LABEL_124;
        }
        v78 = 8 - v76;
        if ( v74 >= 4 )
        {
          v79 = *(unsigned __int8 *)(*(_QWORD *)v73 + 3LL)
              | ((*(unsigned __int8 *)(*(_QWORD *)v73 + 2LL)
                | (((**(unsigned __int8 **)v73 << 8) | *(unsigned __int8 *)(*(_QWORD *)v73 + 1LL)) << 8)) << 8);
          *(_QWORD *)v73 += 4LL;
          v73[2] = v74 - 4;
          v77 = 32 - v78;
          v73[3] = v79;
          goto LABEL_119;
        }
        CInputBitStream::finalLoad(*((CInputBitStream **)this + 675), v73[3] & *((_DWORD *)&GetMask + v76), v78);
      }
LABEL_124:
      if ( (*((_DWORD *)this + 72) & 0x100) == 0 )
        goto LABEL_135;
      v80 = (unsigned int *)*((_QWORD *)this + 675);
      if ( v80[5] || (v81 = v80[2], v82 = v80 + 4, (unsigned int)(8 * v81) < 4) && *v82 + 8 * v81 < 4 )
      {
        v80[5] = 1;
      }
      else
      {
        v83 = *v82;
        if ( (unsigned int)v83 >= 4 )
        {
          v84 = v83 - 4;
LABEL_130:
          *v82 = v84;
          goto LABEL_135;
        }
        v85 = 4 - v83;
        if ( v81 >= 4 )
        {
          v86 = *(unsigned __int8 *)(*(_QWORD *)v80 + 3LL)
              | ((*(unsigned __int8 *)(*(_QWORD *)v80 + 2LL)
                | (((**(unsigned __int8 **)v80 << 8) | *(unsigned __int8 *)(*(_QWORD *)v80 + 1LL)) << 8)) << 8);
          *(_QWORD *)v80 += 4LL;
          v80[2] = v81 - 4;
          v84 = 32 - v85;
          v80[3] = v86;
          goto LABEL_130;
        }
        CInputBitStream::finalLoad(*((CInputBitStream **)this + 675), v80[3] & *((_DWORD *)&GetMask + v83), v85);
      }
LABEL_135:
      if ( (*((_BYTE *)this + 288) & 2) == 0 )
        return;
      v87 = (_DWORD *)*((_QWORD *)this + 675);
      if ( !v87[5] )
      {
        v88 = v87[2];
        v89 = v87 + 4;
        if ( (unsigned int)(8 * v88) >= 8 || (unsigned int)(*v89 + 8 * v88) >= 8 )
        {
          v90 = (unsigned int)*v89;
          if ( (unsigned int)v90 < 8 )
          {
            v91 = 8 - v90;
            if ( v88 >= 4 )
            {
              v92 = *(_QWORD *)v87;
              v93 = *(unsigned __int8 *)(*(_QWORD *)v87 + 1LL);
              v94 = **(unsigned __int8 **)v87 << 8;
LABEL_623:
              v370 = *(unsigned __int8 *)(v92 + 3) | ((*(unsigned __int8 *)(v92 + 2) | ((v94 | v93) << 8)) << 8);
              *(_QWORD *)v87 = v92 + 4;
              *v89 = 32 - v91;
              v87[2] = v88 - 4;
              v87[3] = v370;
              return;
            }
LABEL_624:
            CInputBitStream::finalLoad((CInputBitStream *)v87, v87[3] & *((_DWORD *)&GetMask + v90), v91);
            return;
          }
          goto LABEL_620;
        }
      }
LABEL_625:
      v87[5] = 1;
      return;
    }
    if ( v2 == 1 )
    {
      v95 = (char *)this + 288;
      if ( (*((_DWORD *)this + 72) & 0x200000) == 0 )
        goto LABEL_155;
      v96 = (CInputBitStream *)*((_QWORD *)this + 675);
      if ( !*((_DWORD *)v96 + 5) )
      {
        v97 = *((_DWORD *)v96 + 2);
        v98 = (unsigned int *)((char *)v96 + 16);
        if ( (unsigned int)(8 * v97) >= 8 )
        {
LABEL_148:
          v99 = *v98;
          if ( (unsigned int)v99 >= 8 )
          {
            v100 = v99 - 8;
LABEL_150:
            *v98 = v100;
            goto LABEL_155;
          }
          v101 = 8 - v99;
          if ( v97 >= 4 )
          {
            v102 = *(unsigned __int8 *)(*(_QWORD *)v96 + 3LL)
                 | ((*(unsigned __int8 *)(*(_QWORD *)v96 + 2LL)
                   | ((*(unsigned __int8 *)(*(_QWORD *)v96 + 1LL) | (**(unsigned __int8 **)v96 << 8)) << 8)) << 8);
            *(_QWORD *)v96 += 4LL;
            *((_DWORD *)v96 + 2) = v97 - 4;
            v100 = 32 - v101;
            *((_DWORD *)v96 + 3) = v102;
            goto LABEL_150;
          }
          CInputBitStream::finalLoad(v96, *((_DWORD *)v96 + 3) & *((_DWORD *)&GetMask + v99), v101);
LABEL_155:
          if ( (*(_DWORD *)v95 & 0x100000) == 0 )
            goto LABEL_167;
          v103 = (unsigned int *)*((_QWORD *)this + 675);
          if ( !v103[5] )
          {
            v104 = v103[2];
            v105 = v103 + 4;
            if ( (unsigned int)(8 * v104) >= 8 )
            {
LABEL_160:
              v106 = *v105;
              if ( (unsigned int)v106 >= 8 )
              {
                v107 = v106 - 8;
LABEL_162:
                *v105 = v107;
                goto LABEL_167;
              }
              v108 = 8 - v106;
              if ( v104 >= 4 )
              {
                v109 = *(unsigned __int8 *)(*(_QWORD *)v103 + 3LL)
                     | ((*(unsigned __int8 *)(*(_QWORD *)v103 + 2LL)
                       | ((*(unsigned __int8 *)(*(_QWORD *)v103 + 1LL) | (**(unsigned __int8 **)v103 << 8)) << 8)) << 8);
                *(_QWORD *)v103 += 4LL;
                v103[2] = v104 - 4;
                v107 = 32 - v108;
                v103[3] = v109;
                goto LABEL_162;
              }
              CInputBitStream::finalLoad(
                *((CInputBitStream **)this + 675),
                v103[3] & *((_DWORD *)&GetMask + v106),
                v108);
LABEL_167:
              if ( (*(_DWORD *)v95 & 0x80000) == 0 )
                goto LABEL_179;
              v110 = (unsigned int *)*((_QWORD *)this + 675);
              if ( !v110[5] )
              {
                v111 = v110[2];
                v112 = v110 + 4;
                if ( (unsigned int)(8 * v111) >= 8 )
                {
LABEL_172:
                  v113 = *v112;
                  if ( (unsigned int)v113 >= 8 )
                  {
                    v114 = v113 - 8;
LABEL_174:
                    *v112 = v114;
                    goto LABEL_179;
                  }
                  v115 = 8 - v113;
                  if ( v111 >= 4 )
                  {
                    v116 = *(unsigned __int8 *)(*(_QWORD *)v110 + 3LL)
                         | ((*(unsigned __int8 *)(*(_QWORD *)v110 + 2LL)
                           | ((*(unsigned __int8 *)(*(_QWORD *)v110 + 1LL) | (**(unsigned __int8 **)v110 << 8)) << 8)) << 8);
                    *(_QWORD *)v110 += 4LL;
                    v110[2] = v111 - 4;
                    v114 = 32 - v115;
                    v110[3] = v116;
                    goto LABEL_174;
                  }
                  CInputBitStream::finalLoad(
                    *((CInputBitStream **)this + 675),
                    v110[3] & *((_DWORD *)&GetMask + v113),
                    v115);
LABEL_179:
                  if ( (*(_DWORD *)v95 & 0x40000) == 0 )
                    goto LABEL_191;
                  v117 = (unsigned int *)*((_QWORD *)this + 675);
                  if ( !v117[5] )
                  {
                    v118 = v117[2];
                    v119 = v117 + 4;
                    if ( (unsigned int)(8 * v118) >= 8 )
                    {
LABEL_184:
                      v120 = *v119;
                      if ( (unsigned int)v120 >= 8 )
                      {
                        v121 = v120 - 8;
LABEL_186:
                        *v119 = v121;
                        goto LABEL_191;
                      }
                      v122 = 8 - v120;
                      if ( v118 >= 4 )
                      {
                        v123 = *(unsigned __int8 *)(*(_QWORD *)v117 + 3LL)
                             | ((*(unsigned __int8 *)(*(_QWORD *)v117 + 2LL)
                               | (((**(unsigned __int8 **)v117 << 8) | *(unsigned __int8 *)(*(_QWORD *)v117 + 1LL)) << 8)) << 8);
                        *(_QWORD *)v117 += 4LL;
                        v117[2] = v118 - 4;
                        v121 = 32 - v122;
                        v117[3] = v123;
                        goto LABEL_186;
                      }
                      CInputBitStream::finalLoad(
                        *((CInputBitStream **)this + 675),
                        v117[3] & *((_DWORD *)&GetMask + v120),
                        v122);
LABEL_191:
                      if ( (*(_DWORD *)v95 & 0x20000) == 0 )
                        goto LABEL_203;
                      v124 = (unsigned int *)*((_QWORD *)this + 675);
                      if ( !v124[5] )
                      {
                        v125 = v124[2];
                        v126 = v124 + 4;
                        if ( (unsigned int)(8 * v125) >= 8 )
                        {
LABEL_196:
                          v127 = *v126;
                          if ( (unsigned int)v127 >= 8 )
                          {
                            v128 = v127 - 8;
LABEL_198:
                            *v126 = v128;
                            goto LABEL_203;
                          }
                          v129 = 8 - v127;
                          if ( v125 >= 4 )
                          {
                            v130 = *(unsigned __int8 *)(*(_QWORD *)v124 + 3LL)
                                 | ((*(unsigned __int8 *)(*(_QWORD *)v124 + 2LL)
                                   | (((**(unsigned __int8 **)v124 << 8) | *(unsigned __int8 *)(*(_QWORD *)v124 + 1LL)) << 8)) << 8);
                            *(_QWORD *)v124 += 4LL;
                            v124[2] = v125 - 4;
                            v128 = 32 - v129;
                            v124[3] = v130;
                            goto LABEL_198;
                          }
                          CInputBitStream::finalLoad(
                            *((CInputBitStream **)this + 675),
                            v124[3] & *((_DWORD *)&GetMask + v127),
                            v129);
LABEL_203:
                          if ( (*(_DWORD *)v95 & 0x10000) == 0 )
                            goto LABEL_215;
                          v131 = (unsigned int *)*((_QWORD *)this + 675);
                          if ( !v131[5] )
                          {
                            v132 = v131[2];
                            v133 = v131 + 4;
                            if ( (unsigned int)(8 * v132) >= 8 )
                            {
LABEL_208:
                              v134 = *v133;
                              if ( (unsigned int)v134 >= 8 )
                              {
                                v135 = v134 - 8;
LABEL_210:
                                *v133 = v135;
                                goto LABEL_215;
                              }
                              v136 = 8 - v134;
                              if ( v132 >= 4 )
                              {
                                v137 = *(unsigned __int8 *)(*(_QWORD *)v131 + 3LL)
                                     | ((*(unsigned __int8 *)(*(_QWORD *)v131 + 2LL)
                                       | ((*(unsigned __int8 *)(*(_QWORD *)v131 + 1LL)
                                         | (**(unsigned __int8 **)v131 << 8)) << 8)) << 8);
                                *(_QWORD *)v131 += 4LL;
                                v131[2] = v132 - 4;
                                v135 = 32 - v136;
                                v131[3] = v137;
                                goto LABEL_210;
                              }
                              CInputBitStream::finalLoad(
                                *((CInputBitStream **)this + 675),
                                v131[3] & *((_DWORD *)&GetMask + v134),
                                v136);
LABEL_215:
                              if ( (*(_DWORD *)v95 & 0x8000) == 0 )
                                goto LABEL_227;
                              v138 = (unsigned int *)*((_QWORD *)this + 675);
                              if ( !v138[5] )
                              {
                                v139 = v138[2];
                                v140 = v138 + 4;
                                if ( (unsigned int)(8 * v139) >= 8 )
                                {
LABEL_220:
                                  v141 = *v140;
                                  if ( (unsigned int)v141 >= 8 )
                                  {
                                    v142 = v141 - 8;
LABEL_222:
                                    *v140 = v142;
                                    goto LABEL_227;
                                  }
                                  v143 = 8 - v141;
                                  if ( v139 >= 4 )
                                  {
                                    v144 = *(unsigned __int8 *)(*(_QWORD *)v138 + 3LL)
                                         | ((*(unsigned __int8 *)(*(_QWORD *)v138 + 2LL)
                                           | ((*(unsigned __int8 *)(*(_QWORD *)v138 + 1LL)
                                             | (**(unsigned __int8 **)v138 << 8)) << 8)) << 8);
                                    *(_QWORD *)v138 += 4LL;
                                    v138[2] = v139 - 4;
                                    v142 = 32 - v143;
                                    v138[3] = v144;
                                    goto LABEL_222;
                                  }
                                  CInputBitStream::finalLoad(
                                    *((CInputBitStream **)this + 675),
                                    v138[3] & *((_DWORD *)&GetMask + v141),
                                    v143);
LABEL_227:
                                  if ( (*(_DWORD *)v95 & 0x1000) == 0 )
                                    goto LABEL_239;
                                  v145 = (unsigned int *)*((_QWORD *)this + 675);
                                  if ( !v145[5] )
                                  {
                                    v146 = v145[2];
                                    v147 = v145 + 4;
                                    if ( (unsigned int)(8 * v146) >= 8 )
                                    {
LABEL_232:
                                      v148 = *v147;
                                      if ( (unsigned int)v148 >= 8 )
                                      {
                                        v149 = v148 - 8;
LABEL_234:
                                        *v147 = v149;
                                        goto LABEL_239;
                                      }
                                      v150 = 8 - v148;
                                      if ( v146 >= 4 )
                                      {
                                        v151 = *(unsigned __int8 *)(*(_QWORD *)v145 + 3LL)
                                             | ((*(unsigned __int8 *)(*(_QWORD *)v145 + 2LL)
                                               | (((**(unsigned __int8 **)v145 << 8)
                                                 | *(unsigned __int8 *)(*(_QWORD *)v145 + 1LL)) << 8)) << 8);
                                        *(_QWORD *)v145 += 4LL;
                                        v145[2] = v146 - 4;
                                        v149 = 32 - v150;
                                        v145[3] = v151;
                                        goto LABEL_234;
                                      }
                                      CInputBitStream::finalLoad(
                                        *((CInputBitStream **)this + 675),
                                        v145[3] & *((_DWORD *)&GetMask + v148),
                                        v150);
LABEL_239:
                                      if ( (*(_DWORD *)v95 & 0x800) == 0 )
                                        goto LABEL_251;
                                      v152 = (unsigned int *)*((_QWORD *)this + 675);
                                      if ( !v152[5] )
                                      {
                                        v153 = v152[2];
                                        v154 = v152 + 4;
                                        if ( (unsigned int)(8 * v153) >= 8 )
                                        {
LABEL_244:
                                          v155 = *v154;
                                          if ( (unsigned int)v155 >= 8 )
                                          {
                                            v156 = v155 - 8;
LABEL_246:
                                            *v154 = v156;
                                            goto LABEL_251;
                                          }
                                          v157 = 8 - v155;
                                          if ( v153 >= 4 )
                                          {
                                            v158 = *(unsigned __int8 *)(*(_QWORD *)v152 + 3LL)
                                                 | ((*(unsigned __int8 *)(*(_QWORD *)v152 + 2LL)
                                                   | (((**(unsigned __int8 **)v152 << 8)
                                                     | *(unsigned __int8 *)(*(_QWORD *)v152 + 1LL)) << 8)) << 8);
                                            *(_QWORD *)v152 += 4LL;
                                            v152[2] = v153 - 4;
                                            v156 = 32 - v157;
                                            v152[3] = v158;
                                            goto LABEL_246;
                                          }
                                          CInputBitStream::finalLoad(
                                            *((CInputBitStream **)this + 675),
                                            v152[3] & *((_DWORD *)&GetMask + v155),
                                            v157);
LABEL_251:
                                          if ( (*(_DWORD *)v95 & 0x400) == 0 )
                                            goto LABEL_263;
                                          v159 = (unsigned int *)*((_QWORD *)this + 675);
                                          if ( !v159[5] )
                                          {
                                            v160 = v159[2];
                                            v161 = v159 + 4;
                                            if ( (unsigned int)(8 * v160) >= 8 )
                                            {
LABEL_256:
                                              v162 = *v161;
                                              if ( (unsigned int)v162 >= 8 )
                                              {
                                                v163 = v162 - 8;
LABEL_258:
                                                *v161 = v163;
                                                goto LABEL_263;
                                              }
                                              v164 = 8 - v162;
                                              if ( v160 >= 4 )
                                              {
                                                v165 = *(unsigned __int8 *)(*(_QWORD *)v159 + 3LL)
                                                     | ((*(unsigned __int8 *)(*(_QWORD *)v159 + 2LL)
                                                       | (((**(unsigned __int8 **)v159 << 8)
                                                         | *(unsigned __int8 *)(*(_QWORD *)v159 + 1LL)) << 8)) << 8);
                                                *(_QWORD *)v159 += 4LL;
                                                v159[2] = v160 - 4;
                                                v163 = 32 - v164;
                                                v159[3] = v165;
                                                goto LABEL_258;
                                              }
                                              CInputBitStream::finalLoad(
                                                *((CInputBitStream **)this + 675),
                                                v159[3] & *((_DWORD *)&GetMask + v162),
                                                v164);
LABEL_263:
                                              if ( (*(_DWORD *)v95 & 0x200) == 0 )
                                                goto LABEL_275;
                                              v166 = (unsigned int *)*((_QWORD *)this + 675);
                                              if ( !v166[5] )
                                              {
                                                v167 = v166[2];
                                                v168 = v166 + 4;
                                                if ( (unsigned int)(8 * v167) >= 8 )
                                                {
LABEL_268:
                                                  v169 = *v168;
                                                  if ( (unsigned int)v169 >= 8 )
                                                  {
                                                    v170 = v169 - 8;
LABEL_270:
                                                    *v168 = v170;
                                                    goto LABEL_275;
                                                  }
                                                  v171 = 8 - v169;
                                                  if ( v167 >= 4 )
                                                  {
                                                    v172 = *(unsigned __int8 *)(*(_QWORD *)v166 + 3LL)
                                                         | ((*(unsigned __int8 *)(*(_QWORD *)v166 + 2LL)
                                                           | ((*(unsigned __int8 *)(*(_QWORD *)v166 + 1LL)
                                                             | (**(unsigned __int8 **)v166 << 8)) << 8)) << 8);
                                                    *(_QWORD *)v166 += 4LL;
                                                    v166[2] = v167 - 4;
                                                    v170 = 32 - v171;
                                                    v166[3] = v172;
                                                    goto LABEL_270;
                                                  }
                                                  CInputBitStream::finalLoad(
                                                    *((CInputBitStream **)this + 675),
                                                    v166[3] & *((_DWORD *)&GetMask + v169),
                                                    v171);
LABEL_275:
                                                  if ( (*(_DWORD *)v95 & 0x100) == 0 )
                                                    goto LABEL_287;
                                                  v173 = (unsigned int *)*((_QWORD *)this + 675);
                                                  if ( !v173[5] )
                                                  {
                                                    v174 = v173[2];
                                                    v175 = v173 + 4;
                                                    if ( (unsigned int)(8 * v174) >= 4 )
                                                    {
LABEL_280:
                                                      v176 = *v175;
                                                      if ( (unsigned int)v176 >= 4 )
                                                      {
                                                        v177 = v176 - 4;
LABEL_282:
                                                        *v175 = v177;
                                                        goto LABEL_287;
                                                      }
                                                      v178 = 4 - v176;
                                                      if ( v174 >= 4 )
                                                      {
                                                        v179 = *(unsigned __int8 *)(*(_QWORD *)v173 + 3LL)
                                                             | ((*(unsigned __int8 *)(*(_QWORD *)v173 + 2LL)
                                                               | (((**(unsigned __int8 **)v173 << 8)
                                                                 | *(unsigned __int8 *)(*(_QWORD *)v173 + 1LL)) << 8)) << 8);
                                                        *(_QWORD *)v173 += 4LL;
                                                        v173[2] = v174 - 4;
                                                        v177 = 32 - v178;
                                                        v173[3] = v179;
                                                        goto LABEL_282;
                                                      }
                                                      CInputBitStream::finalLoad(
                                                        *((CInputBitStream **)this + 675),
                                                        v173[3] & *((_DWORD *)&GetMask + v176),
                                                        v178);
LABEL_287:
                                                      if ( (*(_DWORD *)v95 & 0x4000) == 0 )
                                                        goto LABEL_299;
                                                      v180 = (unsigned int *)*((_QWORD *)this + 675);
                                                      if ( !v180[5] )
                                                      {
                                                        v181 = v180[2];
                                                        v182 = v180 + 4;
                                                        if ( (unsigned int)(8 * v181) >= 8 )
                                                        {
LABEL_292:
                                                          v183 = *v182;
                                                          if ( (unsigned int)v183 >= 8 )
                                                          {
                                                            v184 = v183 - 8;
LABEL_294:
                                                            *v182 = v184;
                                                            goto LABEL_299;
                                                          }
                                                          v185 = 8 - v183;
                                                          if ( v181 >= 4 )
                                                          {
                                                            v186 = *(unsigned __int8 *)(*(_QWORD *)v180 + 3LL)
                                                                 | ((*(unsigned __int8 *)(*(_QWORD *)v180 + 2LL)
                                                                   | ((*(unsigned __int8 *)(*(_QWORD *)v180 + 1LL)
                                                                     | (**(unsigned __int8 **)v180 << 8)) << 8)) << 8);
                                                            *(_QWORD *)v180 += 4LL;
                                                            v180[2] = v181 - 4;
                                                            v184 = 32 - v185;
                                                            v180[3] = v186;
                                                            goto LABEL_294;
                                                          }
                                                          CInputBitStream::finalLoad(
                                                            *((CInputBitStream **)this + 675),
                                                            v180[3] & *((_DWORD *)&GetMask + v183),
                                                            v185);
LABEL_299:
                                                          if ( (*(_DWORD *)v95 & 0x2000) == 0 )
                                                            goto LABEL_311;
                                                          v187 = (unsigned int *)*((_QWORD *)this + 675);
                                                          if ( !v187[5] )
                                                          {
                                                            v188 = v187[2];
                                                            v189 = v187 + 4;
                                                            if ( (unsigned int)(8 * v188) >= 8 )
                                                            {
LABEL_304:
                                                              v190 = *v189;
                                                              if ( (unsigned int)v190 >= 8 )
                                                              {
                                                                v191 = v190 - 8;
LABEL_306:
                                                                *v189 = v191;
                                                                goto LABEL_311;
                                                              }
                                                              v192 = 8 - v190;
                                                              if ( v188 >= 4 )
                                                              {
                                                                v193 = *(unsigned __int8 *)(*(_QWORD *)v187 + 3LL)
                                                                     | ((*(unsigned __int8 *)(*(_QWORD *)v187 + 2LL)
                                                                       | (((**(unsigned __int8 **)v187 << 8)
                                                                         | *(unsigned __int8 *)(*(_QWORD *)v187 + 1LL)) << 8)) << 8);
                                                                *(_QWORD *)v187 += 4LL;
                                                                v187[2] = v188 - 4;
                                                                v191 = 32 - v192;
                                                                v187[3] = v193;
                                                                goto LABEL_306;
                                                              }
                                                              CInputBitStream::finalLoad(
                                                                *((CInputBitStream **)this + 675),
                                                                v187[3] & *((_DWORD *)&GetMask + v190),
                                                                v192);
LABEL_311:
                                                              if ( *v95 >= 0 )
                                                                goto LABEL_323;
                                                              v194 = (unsigned int *)*((_QWORD *)this + 675);
                                                              if ( !v194[5] )
                                                              {
                                                                v195 = v194[2];
                                                                v196 = v194 + 4;
                                                                if ( (unsigned int)(8 * v195) >= 8 )
                                                                {
LABEL_316:
                                                                  v197 = *v196;
                                                                  if ( (unsigned int)v197 >= 8 )
                                                                  {
                                                                    v198 = v197 - 8;
LABEL_318:
                                                                    *v196 = v198;
                                                                    goto LABEL_323;
                                                                  }
                                                                  v199 = 8 - v197;
                                                                  if ( v195 >= 4 )
                                                                  {
                                                                    v200 = *(unsigned __int8 *)(*(_QWORD *)v194 + 3LL)
                                                                         | ((*(unsigned __int8 *)(*(_QWORD *)v194 + 2LL)
                                                                           | (((**(unsigned __int8 **)v194 << 8)
                                                                             | *(unsigned __int8 *)(*(_QWORD *)v194 + 1LL)) << 8)) << 8);
                                                                    *(_QWORD *)v194 += 4LL;
                                                                    v194[2] = v195 - 4;
                                                                    v198 = 32 - v199;
                                                                    v194[3] = v200;
                                                                    goto LABEL_318;
                                                                  }
                                                                  CInputBitStream::finalLoad(
                                                                    *((CInputBitStream **)this + 675),
                                                                    v194[3] & *((_DWORD *)&GetMask + v197),
                                                                    v199);
LABEL_323:
                                                                  if ( (*v95 & 0x40) == 0 )
                                                                    goto LABEL_335;
                                                                  v201 = (unsigned int *)*((_QWORD *)this + 675);
                                                                  if ( !v201[5] )
                                                                  {
                                                                    v202 = v201[2];
                                                                    v203 = v201 + 4;
                                                                    if ( (unsigned int)(8 * v202) >= 8 )
                                                                    {
LABEL_328:
                                                                      v204 = *v203;
                                                                      if ( (unsigned int)v204 >= 8 )
                                                                      {
                                                                        v205 = v204 - 8;
LABEL_330:
                                                                        *v203 = v205;
                                                                        goto LABEL_335;
                                                                      }
                                                                      v206 = 8 - v204;
                                                                      if ( v202 >= 4 )
                                                                      {
                                                                        v207 = *(unsigned __int8 *)(*(_QWORD *)v201 + 3LL)
                                                                             | ((*(unsigned __int8 *)(*(_QWORD *)v201 + 2LL)
                                                                               | (((**(unsigned __int8 **)v201 << 8)
                                                                                 | *(unsigned __int8 *)(*(_QWORD *)v201 + 1LL)) << 8)) << 8);
                                                                        *(_QWORD *)v201 += 4LL;
                                                                        v201[2] = v202 - 4;
                                                                        v205 = 32 - v206;
                                                                        v201[3] = v207;
                                                                        goto LABEL_330;
                                                                      }
                                                                      CInputBitStream::finalLoad(
                                                                        *((CInputBitStream **)this + 675),
                                                                        v201[3] & *((_DWORD *)&GetMask + v204),
                                                                        v206);
LABEL_335:
                                                                      if ( (*v95 & 0x10) == 0 )
                                                                        goto LABEL_347;
                                                                      v208 = (unsigned int *)*((_QWORD *)this + 675);
                                                                      if ( !v208[5] )
                                                                      {
                                                                        v209 = v208[2];
                                                                        v210 = v208 + 4;
                                                                        if ( (unsigned int)(8 * v209) >= 8 )
                                                                        {
LABEL_340:
                                                                          v211 = *v210;
                                                                          if ( (unsigned int)v211 >= 8 )
                                                                          {
                                                                            v212 = v211 - 8;
LABEL_342:
                                                                            *v210 = v212;
                                                                            goto LABEL_347;
                                                                          }
                                                                          v213 = 8 - v211;
                                                                          if ( v209 >= 4 )
                                                                          {
                                                                            v214 = *(unsigned __int8 *)(*(_QWORD *)v208 + 3LL)
                                                                                 | ((*(unsigned __int8 *)(*(_QWORD *)v208 + 2LL)
                                                                                   | (((**(unsigned __int8 **)v208 << 8)
                                                                                     | *(unsigned __int8 *)(*(_QWORD *)v208 + 1LL)) << 8)) << 8);
                                                                            *(_QWORD *)v208 += 4LL;
                                                                            v208[2] = v209 - 4;
                                                                            v212 = 32 - v213;
                                                                            v208[3] = v214;
                                                                            goto LABEL_342;
                                                                          }
                                                                          CInputBitStream::finalLoad(
                                                                            *((CInputBitStream **)this + 675),
                                                                            v208[3] & *((_DWORD *)&GetMask + v211),
                                                                            v213);
LABEL_347:
                                                                          if ( (*v95 & 8) == 0 )
                                                                            goto LABEL_359;
                                                                          v215 = (unsigned int *)*((_QWORD *)this + 675);
                                                                          if ( !v215[5] )
                                                                          {
                                                                            v216 = v215[2];
                                                                            v217 = v215 + 4;
                                                                            if ( (unsigned int)(8 * v216) >= 8 )
                                                                            {
LABEL_352:
                                                                              v218 = *v217;
                                                                              if ( (unsigned int)v218 < 8 )
                                                                              {
                                                                                v220 = 8 - v218;
                                                                                if ( v216 < 4 )
                                                                                {
                                                                                  CInputBitStream::finalLoad(
                                                                                    *((CInputBitStream **)this + 675),
                                                                                    v215[3]
                                                                                  & *((_DWORD *)&GetMask + v218),
                                                                                    v220);
                                                                                  goto LABEL_359;
                                                                                }
                                                                                v221 = *(unsigned __int8 *)(*(_QWORD *)v215 + 3LL)
                                                                                     | ((*(unsigned __int8 *)(*(_QWORD *)v215 + 2LL)
                                                                                       | (((**(unsigned __int8 **)v215 << 8)
                                                                                         | *(unsigned __int8 *)(*(_QWORD *)v215 + 1LL)) << 8)) << 8);
                                                                                *(_QWORD *)v215 += 4LL;
                                                                                v215[2] = v216 - 4;
                                                                                v219 = 32 - v220;
                                                                                v215[3] = v221;
                                                                              }
                                                                              else
                                                                              {
                                                                                v219 = v218 - 8;
                                                                              }
                                                                              *v217 = v219;
LABEL_359:
                                                                              v222 = (*v95 & 4) == 0;
                                                                              goto LABEL_604;
                                                                            }
                                                                            if ( *v217 + 8 * v216 >= 8 )
                                                                            {
                                                                              v95 = (char *)this + 288;
                                                                              goto LABEL_352;
                                                                            }
                                                                          }
                                                                          v215[5] = 1;
                                                                          goto LABEL_359;
                                                                        }
                                                                        if ( *v210 + 8 * v209 >= 8 )
                                                                        {
                                                                          v95 = (char *)this + 288;
                                                                          goto LABEL_340;
                                                                        }
                                                                      }
                                                                      v208[5] = 1;
                                                                      goto LABEL_347;
                                                                    }
                                                                    if ( *v203 + 8 * v202 >= 8 )
                                                                    {
                                                                      v95 = (char *)this + 288;
                                                                      goto LABEL_328;
                                                                    }
                                                                  }
                                                                  v201[5] = 1;
                                                                  goto LABEL_335;
                                                                }
                                                                if ( *v196 + 8 * v195 >= 8 )
                                                                {
                                                                  v95 = (char *)this + 288;
                                                                  goto LABEL_316;
                                                                }
                                                              }
                                                              v194[5] = 1;
                                                              goto LABEL_323;
                                                            }
                                                            if ( *v189 + 8 * v188 >= 8 )
                                                            {
                                                              v95 = (char *)this + 288;
                                                              goto LABEL_304;
                                                            }
                                                          }
                                                          v187[5] = 1;
                                                          goto LABEL_311;
                                                        }
                                                        if ( *v182 + 8 * v181 >= 8 )
                                                        {
                                                          v95 = (char *)this + 288;
                                                          goto LABEL_292;
                                                        }
                                                      }
                                                      v180[5] = 1;
                                                      goto LABEL_299;
                                                    }
                                                    if ( *v175 + 8 * v174 >= 4 )
                                                    {
                                                      v95 = (char *)this + 288;
                                                      goto LABEL_280;
                                                    }
                                                  }
                                                  v173[5] = 1;
                                                  goto LABEL_287;
                                                }
                                                if ( *v168 + 8 * v167 >= 8 )
                                                {
                                                  v95 = (char *)this + 288;
                                                  goto LABEL_268;
                                                }
                                              }
                                              v166[5] = 1;
                                              goto LABEL_275;
                                            }
                                            if ( *v161 + 8 * v160 >= 8 )
                                            {
                                              v95 = (char *)this + 288;
                                              goto LABEL_256;
                                            }
                                          }
                                          v159[5] = 1;
                                          goto LABEL_263;
                                        }
                                        if ( *v154 + 8 * v153 >= 8 )
                                        {
                                          v95 = (char *)this + 288;
                                          goto LABEL_244;
                                        }
                                      }
                                      v152[5] = 1;
                                      goto LABEL_251;
                                    }
                                    if ( *v147 + 8 * v146 >= 8 )
                                    {
                                      v95 = (char *)this + 288;
                                      goto LABEL_232;
                                    }
                                  }
                                  v145[5] = 1;
                                  goto LABEL_239;
                                }
                                if ( *v140 + 8 * v139 >= 8 )
                                {
                                  v95 = (char *)this + 288;
                                  goto LABEL_220;
                                }
                              }
                              v138[5] = 1;
                              goto LABEL_227;
                            }
                            if ( *v133 + 8 * v132 >= 8 )
                            {
                              v95 = (char *)this + 288;
                              goto LABEL_208;
                            }
                          }
                          v131[5] = 1;
                          goto LABEL_215;
                        }
                        if ( *v126 + 8 * v125 >= 8 )
                        {
                          v95 = (char *)this + 288;
                          goto LABEL_196;
                        }
                      }
                      v124[5] = 1;
                      goto LABEL_203;
                    }
                    if ( *v119 + 8 * v118 >= 8 )
                    {
                      v95 = (char *)this + 288;
                      goto LABEL_184;
                    }
                  }
                  v117[5] = 1;
                  goto LABEL_191;
                }
                if ( *v112 + 8 * v111 >= 8 )
                {
                  v95 = (char *)this + 288;
                  goto LABEL_172;
                }
              }
              v110[5] = 1;
              goto LABEL_179;
            }
            if ( *v105 + 8 * v104 >= 8 )
            {
              v95 = (char *)this + 288;
              goto LABEL_160;
            }
          }
          v103[5] = 1;
          goto LABEL_167;
        }
        if ( *v98 + 8 * v97 >= 8 )
        {
          v95 = (char *)this + 288;
          goto LABEL_148;
        }
      }
      *((_DWORD *)v96 + 5) = 1;
      goto LABEL_155;
    }
    if ( v2 != 2 )
      return;
    v95 = (char *)this + 288;
    if ( (*((_DWORD *)this + 72) & 0x200000) == 0 )
      goto LABEL_387;
    v233 = (CInputBitStream *)*((_QWORD *)this + 675);
    if ( !*((_DWORD *)v233 + 5) )
    {
      v234 = *((_DWORD *)v233 + 2);
      v235 = (unsigned int *)((char *)v233 + 16);
      if ( (unsigned int)(8 * v234) >= 8 )
      {
LABEL_380:
        v236 = *v235;
        if ( (unsigned int)v236 >= 8 )
        {
          v237 = v236 - 8;
LABEL_382:
          *v235 = v237;
          goto LABEL_387;
        }
        v238 = 8 - v236;
        if ( v234 >= 4 )
        {
          v239 = *(unsigned __int8 *)(*(_QWORD *)v233 + 3LL)
               | ((*(unsigned __int8 *)(*(_QWORD *)v233 + 2LL)
                 | ((*(unsigned __int8 *)(*(_QWORD *)v233 + 1LL) | (**(unsigned __int8 **)v233 << 8)) << 8)) << 8);
          *(_QWORD *)v233 += 4LL;
          *((_DWORD *)v233 + 2) = v234 - 4;
          v237 = 32 - v238;
          *((_DWORD *)v233 + 3) = v239;
          goto LABEL_382;
        }
        CInputBitStream::finalLoad(v233, *((_DWORD *)v233 + 3) & *((_DWORD *)&GetMask + v236), v238);
LABEL_387:
        if ( (*(_DWORD *)v95 & 0x100000) == 0 )
          goto LABEL_399;
        v240 = (unsigned int *)*((_QWORD *)this + 675);
        if ( !v240[5] )
        {
          v241 = v240[2];
          v242 = v240 + 4;
          if ( (unsigned int)(8 * v241) >= 8 )
          {
LABEL_392:
            v243 = *v242;
            if ( (unsigned int)v243 >= 8 )
            {
              v244 = v243 - 8;
LABEL_394:
              *v242 = v244;
              goto LABEL_399;
            }
            v245 = 8 - v243;
            if ( v241 >= 4 )
            {
              v246 = *(unsigned __int8 *)(*(_QWORD *)v240 + 3LL)
                   | ((*(unsigned __int8 *)(*(_QWORD *)v240 + 2LL)
                     | (((**(unsigned __int8 **)v240 << 8) | *(unsigned __int8 *)(*(_QWORD *)v240 + 1LL)) << 8)) << 8);
              *(_QWORD *)v240 += 4LL;
              v240[2] = v241 - 4;
              v244 = 32 - v245;
              v240[3] = v246;
              goto LABEL_394;
            }
            CInputBitStream::finalLoad(*((CInputBitStream **)this + 675), v240[3] & *((_DWORD *)&GetMask + v243), v245);
LABEL_399:
            if ( (*(_DWORD *)v95 & 0x80000) == 0 )
              goto LABEL_411;
            v247 = (unsigned int *)*((_QWORD *)this + 675);
            if ( !v247[5] )
            {
              v248 = v247[2];
              v249 = v247 + 4;
              if ( (unsigned int)(8 * v248) >= 8 )
              {
LABEL_404:
                v250 = *v249;
                if ( (unsigned int)v250 >= 8 )
                {
                  v251 = v250 - 8;
LABEL_406:
                  *v249 = v251;
                  goto LABEL_411;
                }
                v252 = 8 - v250;
                if ( v248 >= 4 )
                {
                  v253 = *(unsigned __int8 *)(*(_QWORD *)v247 + 3LL)
                       | ((*(unsigned __int8 *)(*(_QWORD *)v247 + 2LL)
                         | (((**(unsigned __int8 **)v247 << 8) | *(unsigned __int8 *)(*(_QWORD *)v247 + 1LL)) << 8)) << 8);
                  *(_QWORD *)v247 += 4LL;
                  v247[2] = v248 - 4;
                  v251 = 32 - v252;
                  v247[3] = v253;
                  goto LABEL_406;
                }
                CInputBitStream::finalLoad(
                  *((CInputBitStream **)this + 675),
                  v247[3] & *((_DWORD *)&GetMask + v250),
                  v252);
LABEL_411:
                if ( (*(_DWORD *)v95 & 0x40000) == 0 )
                  goto LABEL_423;
                v254 = (unsigned int *)*((_QWORD *)this + 675);
                if ( !v254[5] )
                {
                  v255 = v254[2];
                  v256 = v254 + 4;
                  if ( (unsigned int)(8 * v255) >= 8 )
                  {
LABEL_416:
                    v257 = *v256;
                    if ( (unsigned int)v257 >= 8 )
                    {
                      v258 = v257 - 8;
LABEL_418:
                      *v256 = v258;
                      goto LABEL_423;
                    }
                    v259 = 8 - v257;
                    if ( v255 >= 4 )
                    {
                      v260 = *(unsigned __int8 *)(*(_QWORD *)v254 + 3LL)
                           | ((*(unsigned __int8 *)(*(_QWORD *)v254 + 2LL)
                             | ((*(unsigned __int8 *)(*(_QWORD *)v254 + 1LL) | (**(unsigned __int8 **)v254 << 8)) << 8)) << 8);
                      *(_QWORD *)v254 += 4LL;
                      v254[2] = v255 - 4;
                      v258 = 32 - v259;
                      v254[3] = v260;
                      goto LABEL_418;
                    }
                    CInputBitStream::finalLoad(
                      *((CInputBitStream **)this + 675),
                      v254[3] & *((_DWORD *)&GetMask + v257),
                      v259);
LABEL_423:
                    if ( (*(_DWORD *)v95 & 0x20000) == 0 )
                      goto LABEL_435;
                    v261 = (unsigned int *)*((_QWORD *)this + 675);
                    if ( !v261[5] )
                    {
                      v262 = v261[2];
                      v263 = v261 + 4;
                      if ( (unsigned int)(8 * v262) >= 8 )
                      {
LABEL_428:
                        v264 = *v263;
                        if ( (unsigned int)v264 >= 8 )
                        {
                          v265 = v264 - 8;
LABEL_430:
                          *v263 = v265;
                          goto LABEL_435;
                        }
                        v266 = 8 - v264;
                        if ( v262 >= 4 )
                        {
                          v267 = *(unsigned __int8 *)(*(_QWORD *)v261 + 3LL)
                               | ((*(unsigned __int8 *)(*(_QWORD *)v261 + 2LL)
                                 | ((*(unsigned __int8 *)(*(_QWORD *)v261 + 1LL) | (**(unsigned __int8 **)v261 << 8)) << 8)) << 8);
                          *(_QWORD *)v261 += 4LL;
                          v261[2] = v262 - 4;
                          v265 = 32 - v266;
                          v261[3] = v267;
                          goto LABEL_430;
                        }
                        CInputBitStream::finalLoad(
                          *((CInputBitStream **)this + 675),
                          v261[3] & *((_DWORD *)&GetMask + v264),
                          v266);
LABEL_435:
                        if ( (*(_DWORD *)v95 & 0x10000) == 0 )
                          goto LABEL_447;
                        v268 = (unsigned int *)*((_QWORD *)this + 675);
                        if ( !v268[5] )
                        {
                          v269 = v268[2];
                          v270 = v268 + 4;
                          if ( (unsigned int)(8 * v269) >= 8 )
                          {
LABEL_440:
                            v271 = *v270;
                            if ( (unsigned int)v271 >= 8 )
                            {
                              v272 = v271 - 8;
LABEL_442:
                              *v270 = v272;
                              goto LABEL_447;
                            }
                            v273 = 8 - v271;
                            if ( v269 >= 4 )
                            {
                              v274 = *(unsigned __int8 *)(*(_QWORD *)v268 + 3LL)
                                   | ((*(unsigned __int8 *)(*(_QWORD *)v268 + 2LL)
                                     | (((**(unsigned __int8 **)v268 << 8) | *(unsigned __int8 *)(*(_QWORD *)v268 + 1LL)) << 8)) << 8);
                              *(_QWORD *)v268 += 4LL;
                              v268[2] = v269 - 4;
                              v272 = 32 - v273;
                              v268[3] = v274;
                              goto LABEL_442;
                            }
                            CInputBitStream::finalLoad(
                              *((CInputBitStream **)this + 675),
                              v268[3] & *((_DWORD *)&GetMask + v271),
                              v273);
LABEL_447:
                            if ( (*(_DWORD *)v95 & 0x8000) == 0 )
                              goto LABEL_459;
                            v275 = (unsigned int *)*((_QWORD *)this + 675);
                            if ( !v275[5] )
                            {
                              v276 = v275[2];
                              v277 = v275 + 4;
                              if ( (unsigned int)(8 * v276) >= 8 )
                              {
LABEL_452:
                                v278 = *v277;
                                if ( (unsigned int)v278 >= 8 )
                                {
                                  v279 = v278 - 8;
LABEL_454:
                                  *v277 = v279;
                                  goto LABEL_459;
                                }
                                v280 = 8 - v278;
                                if ( v276 >= 4 )
                                {
                                  v281 = *(unsigned __int8 *)(*(_QWORD *)v275 + 3LL)
                                       | ((*(unsigned __int8 *)(*(_QWORD *)v275 + 2LL)
                                         | (((**(unsigned __int8 **)v275 << 8)
                                           | *(unsigned __int8 *)(*(_QWORD *)v275 + 1LL)) << 8)) << 8);
                                  *(_QWORD *)v275 += 4LL;
                                  v275[2] = v276 - 4;
                                  v279 = 32 - v280;
                                  v275[3] = v281;
                                  goto LABEL_454;
                                }
                                CInputBitStream::finalLoad(
                                  *((CInputBitStream **)this + 675),
                                  v275[3] & *((_DWORD *)&GetMask + v278),
                                  v280);
LABEL_459:
                                if ( (*(_DWORD *)v95 & 0x1000) == 0 )
                                  goto LABEL_471;
                                v282 = (unsigned int *)*((_QWORD *)this + 675);
                                if ( !v282[5] )
                                {
                                  v283 = v282[2];
                                  v284 = v282 + 4;
                                  if ( (unsigned int)(8 * v283) >= 8 )
                                  {
LABEL_464:
                                    v285 = *v284;
                                    if ( (unsigned int)v285 >= 8 )
                                    {
                                      v286 = v285 - 8;
LABEL_466:
                                      *v284 = v286;
                                      goto LABEL_471;
                                    }
                                    v287 = 8 - v285;
                                    if ( v283 >= 4 )
                                    {
                                      v288 = *(unsigned __int8 *)(*(_QWORD *)v282 + 3LL)
                                           | ((*(unsigned __int8 *)(*(_QWORD *)v282 + 2LL)
                                             | (((**(unsigned __int8 **)v282 << 8)
                                               | *(unsigned __int8 *)(*(_QWORD *)v282 + 1LL)) << 8)) << 8);
                                      *(_QWORD *)v282 += 4LL;
                                      v282[2] = v283 - 4;
                                      v286 = 32 - v287;
                                      v282[3] = v288;
                                      goto LABEL_466;
                                    }
                                    CInputBitStream::finalLoad(
                                      *((CInputBitStream **)this + 675),
                                      v282[3] & *((_DWORD *)&GetMask + v285),
                                      v287);
LABEL_471:
                                    if ( (*(_DWORD *)v95 & 0x800) == 0 )
                                      goto LABEL_483;
                                    v289 = (unsigned int *)*((_QWORD *)this + 675);
                                    if ( !v289[5] )
                                    {
                                      v290 = v289[2];
                                      v291 = v289 + 4;
                                      if ( (unsigned int)(8 * v290) >= 8 )
                                      {
LABEL_476:
                                        v292 = *v291;
                                        if ( (unsigned int)v292 >= 8 )
                                        {
                                          v293 = v292 - 8;
LABEL_478:
                                          *v291 = v293;
                                          goto LABEL_483;
                                        }
                                        v294 = 8 - v292;
                                        if ( v290 >= 4 )
                                        {
                                          v295 = *(unsigned __int8 *)(*(_QWORD *)v289 + 3LL)
                                               | ((*(unsigned __int8 *)(*(_QWORD *)v289 + 2LL)
                                                 | ((*(unsigned __int8 *)(*(_QWORD *)v289 + 1LL)
                                                   | (**(unsigned __int8 **)v289 << 8)) << 8)) << 8);
                                          *(_QWORD *)v289 += 4LL;
                                          v289[2] = v290 - 4;
                                          v293 = 32 - v294;
                                          v289[3] = v295;
                                          goto LABEL_478;
                                        }
                                        CInputBitStream::finalLoad(
                                          *((CInputBitStream **)this + 675),
                                          v289[3] & *((_DWORD *)&GetMask + v292),
                                          v294);
LABEL_483:
                                        if ( (*(_DWORD *)v95 & 0x400) == 0 )
                                          goto LABEL_495;
                                        v296 = (unsigned int *)*((_QWORD *)this + 675);
                                        if ( !v296[5] )
                                        {
                                          v297 = v296[2];
                                          v298 = v296 + 4;
                                          if ( (unsigned int)(8 * v297) >= 8 )
                                          {
LABEL_488:
                                            v299 = *v298;
                                            if ( (unsigned int)v299 >= 8 )
                                            {
                                              v300 = v299 - 8;
LABEL_490:
                                              *v298 = v300;
                                              goto LABEL_495;
                                            }
                                            v301 = 8 - v299;
                                            if ( v297 >= 4 )
                                            {
                                              v302 = *(unsigned __int8 *)(*(_QWORD *)v296 + 3LL)
                                                   | ((*(unsigned __int8 *)(*(_QWORD *)v296 + 2LL)
                                                     | (((**(unsigned __int8 **)v296 << 8)
                                                       | *(unsigned __int8 *)(*(_QWORD *)v296 + 1LL)) << 8)) << 8);
                                              *(_QWORD *)v296 += 4LL;
                                              v296[2] = v297 - 4;
                                              v300 = 32 - v301;
                                              v296[3] = v302;
                                              goto LABEL_490;
                                            }
                                            CInputBitStream::finalLoad(
                                              *((CInputBitStream **)this + 675),
                                              v296[3] & *((_DWORD *)&GetMask + v299),
                                              v301);
LABEL_495:
                                            if ( (*(_DWORD *)v95 & 0x200) == 0 )
                                              goto LABEL_507;
                                            v303 = (unsigned int *)*((_QWORD *)this + 675);
                                            if ( !v303[5] )
                                            {
                                              v304 = v303[2];
                                              v305 = v303 + 4;
                                              if ( (unsigned int)(8 * v304) >= 8 )
                                              {
LABEL_500:
                                                v306 = *v305;
                                                if ( (unsigned int)v306 >= 8 )
                                                {
                                                  v307 = v306 - 8;
LABEL_502:
                                                  *v305 = v307;
                                                  goto LABEL_507;
                                                }
                                                v308 = 8 - v306;
                                                if ( v304 >= 4 )
                                                {
                                                  v309 = *(unsigned __int8 *)(*(_QWORD *)v303 + 3LL)
                                                       | ((*(unsigned __int8 *)(*(_QWORD *)v303 + 2LL)
                                                         | (((**(unsigned __int8 **)v303 << 8)
                                                           | *(unsigned __int8 *)(*(_QWORD *)v303 + 1LL)) << 8)) << 8);
                                                  *(_QWORD *)v303 += 4LL;
                                                  v303[2] = v304 - 4;
                                                  v307 = 32 - v308;
                                                  v303[3] = v309;
                                                  goto LABEL_502;
                                                }
                                                CInputBitStream::finalLoad(
                                                  *((CInputBitStream **)this + 675),
                                                  v303[3] & *((_DWORD *)&GetMask + v306),
                                                  v308);
LABEL_507:
                                                if ( (*(_DWORD *)v95 & 0x100) == 0 )
                                                  goto LABEL_519;
                                                v310 = (unsigned int *)*((_QWORD *)this + 675);
                                                if ( !v310[5] )
                                                {
                                                  v311 = v310[2];
                                                  v312 = v310 + 4;
                                                  if ( (unsigned int)(8 * v311) >= 4 )
                                                  {
LABEL_512:
                                                    v313 = *v312;
                                                    if ( (unsigned int)v313 >= 4 )
                                                    {
                                                      v314 = v313 - 4;
LABEL_514:
                                                      *v312 = v314;
                                                      goto LABEL_519;
                                                    }
                                                    v315 = 4 - v313;
                                                    if ( v311 >= 4 )
                                                    {
                                                      v316 = *(unsigned __int8 *)(*(_QWORD *)v310 + 3LL)
                                                           | ((*(unsigned __int8 *)(*(_QWORD *)v310 + 2LL)
                                                             | (((**(unsigned __int8 **)v310 << 8)
                                                               | *(unsigned __int8 *)(*(_QWORD *)v310 + 1LL)) << 8)) << 8);
                                                      *(_QWORD *)v310 += 4LL;
                                                      v310[2] = v311 - 4;
                                                      v314 = 32 - v315;
                                                      v310[3] = v316;
                                                      goto LABEL_514;
                                                    }
                                                    CInputBitStream::finalLoad(
                                                      *((CInputBitStream **)this + 675),
                                                      v310[3] & *((_DWORD *)&GetMask + v313),
                                                      v315);
LABEL_519:
                                                    if ( (*(_DWORD *)v95 & 0x4000) == 0 )
                                                      goto LABEL_531;
                                                    v317 = (unsigned int *)*((_QWORD *)this + 675);
                                                    if ( !v317[5] )
                                                    {
                                                      v318 = v317[2];
                                                      v319 = v317 + 4;
                                                      if ( (unsigned int)(8 * v318) >= 8 )
                                                      {
LABEL_524:
                                                        v320 = *v319;
                                                        if ( (unsigned int)v320 >= 8 )
                                                        {
                                                          v321 = v320 - 8;
LABEL_526:
                                                          *v319 = v321;
                                                          goto LABEL_531;
                                                        }
                                                        v322 = 8 - v320;
                                                        if ( v318 >= 4 )
                                                        {
                                                          v323 = *(unsigned __int8 *)(*(_QWORD *)v317 + 3LL)
                                                               | ((*(unsigned __int8 *)(*(_QWORD *)v317 + 2LL)
                                                                 | (((**(unsigned __int8 **)v317 << 8)
                                                                   | *(unsigned __int8 *)(*(_QWORD *)v317 + 1LL)) << 8)) << 8);
                                                          *(_QWORD *)v317 += 4LL;
                                                          v317[2] = v318 - 4;
                                                          v321 = 32 - v322;
                                                          v317[3] = v323;
                                                          goto LABEL_526;
                                                        }
                                                        CInputBitStream::finalLoad(
                                                          *((CInputBitStream **)this + 675),
                                                          v317[3] & *((_DWORD *)&GetMask + v320),
                                                          v322);
LABEL_531:
                                                        if ( (*(_DWORD *)v95 & 0x2000) == 0 )
                                                          goto LABEL_543;
                                                        v324 = (unsigned int *)*((_QWORD *)this + 675);
                                                        if ( !v324[5] )
                                                        {
                                                          v325 = v324[2];
                                                          v326 = v324 + 4;
                                                          if ( (unsigned int)(8 * v325) >= 8 )
                                                          {
LABEL_536:
                                                            v327 = *v326;
                                                            if ( (unsigned int)v327 >= 8 )
                                                            {
                                                              v328 = v327 - 8;
LABEL_538:
                                                              *v326 = v328;
                                                              goto LABEL_543;
                                                            }
                                                            v329 = 8 - v327;
                                                            if ( v325 >= 4 )
                                                            {
                                                              v330 = *(unsigned __int8 *)(*(_QWORD *)v324 + 3LL)
                                                                   | ((*(unsigned __int8 *)(*(_QWORD *)v324 + 2LL)
                                                                     | (((**(unsigned __int8 **)v324 << 8)
                                                                       | *(unsigned __int8 *)(*(_QWORD *)v324 + 1LL)) << 8)) << 8);
                                                              *(_QWORD *)v324 += 4LL;
                                                              v324[2] = v325 - 4;
                                                              v328 = 32 - v329;
                                                              v324[3] = v330;
                                                              goto LABEL_538;
                                                            }
                                                            CInputBitStream::finalLoad(
                                                              *((CInputBitStream **)this + 675),
                                                              v324[3] & *((_DWORD *)&GetMask + v327),
                                                              v329);
LABEL_543:
                                                            if ( *v95 >= 0 )
                                                              goto LABEL_555;
                                                            v331 = (unsigned int *)*((_QWORD *)this + 675);
                                                            if ( !v331[5] )
                                                            {
                                                              v332 = v331[2];
                                                              v333 = v331 + 4;
                                                              if ( (unsigned int)(8 * v332) >= 8 )
                                                              {
LABEL_548:
                                                                v334 = *v333;
                                                                if ( (unsigned int)v334 >= 8 )
                                                                {
                                                                  v335 = v334 - 8;
LABEL_550:
                                                                  *v333 = v335;
                                                                  goto LABEL_555;
                                                                }
                                                                v336 = 8 - v334;
                                                                if ( v332 >= 4 )
                                                                {
                                                                  v337 = *(unsigned __int8 *)(*(_QWORD *)v331 + 3LL)
                                                                       | ((*(unsigned __int8 *)(*(_QWORD *)v331 + 2LL)
                                                                         | (((**(unsigned __int8 **)v331 << 8)
                                                                           | *(unsigned __int8 *)(*(_QWORD *)v331 + 1LL)) << 8)) << 8);
                                                                  *(_QWORD *)v331 += 4LL;
                                                                  v331[2] = v332 - 4;
                                                                  v335 = 32 - v336;
                                                                  v331[3] = v337;
                                                                  goto LABEL_550;
                                                                }
                                                                CInputBitStream::finalLoad(
                                                                  *((CInputBitStream **)this + 675),
                                                                  v331[3] & *((_DWORD *)&GetMask + v334),
                                                                  v336);
LABEL_555:
                                                                if ( (*v95 & 0x40) == 0 )
                                                                  goto LABEL_567;
                                                                v338 = (unsigned int *)*((_QWORD *)this + 675);
                                                                if ( !v338[5] )
                                                                {
                                                                  v339 = v338[2];
                                                                  v340 = v338 + 4;
                                                                  if ( (unsigned int)(8 * v339) >= 8 )
                                                                  {
LABEL_560:
                                                                    v341 = *v340;
                                                                    if ( (unsigned int)v341 >= 8 )
                                                                    {
                                                                      v342 = v341 - 8;
LABEL_562:
                                                                      *v340 = v342;
                                                                      goto LABEL_567;
                                                                    }
                                                                    v343 = 8 - v341;
                                                                    if ( v339 >= 4 )
                                                                    {
                                                                      v344 = *(unsigned __int8 *)(*(_QWORD *)v338 + 3LL)
                                                                           | ((*(unsigned __int8 *)(*(_QWORD *)v338 + 2LL)
                                                                             | (((**(unsigned __int8 **)v338 << 8)
                                                                               | *(unsigned __int8 *)(*(_QWORD *)v338 + 1LL)) << 8)) << 8);
                                                                      *(_QWORD *)v338 += 4LL;
                                                                      v338[2] = v339 - 4;
                                                                      v342 = 32 - v343;
                                                                      v338[3] = v344;
                                                                      goto LABEL_562;
                                                                    }
                                                                    CInputBitStream::finalLoad(
                                                                      *((CInputBitStream **)this + 675),
                                                                      v338[3] & *((_DWORD *)&GetMask + v341),
                                                                      v343);
LABEL_567:
                                                                    if ( (*v95 & 0x10) == 0 )
                                                                      goto LABEL_579;
                                                                    v345 = (unsigned int *)*((_QWORD *)this + 675);
                                                                    if ( !v345[5] )
                                                                    {
                                                                      v346 = v345[2];
                                                                      v347 = v345 + 4;
                                                                      if ( (unsigned int)(8 * v346) >= 8 )
                                                                      {
LABEL_572:
                                                                        v348 = *v347;
                                                                        if ( (unsigned int)v348 >= 8 )
                                                                        {
                                                                          v349 = v348 - 8;
LABEL_574:
                                                                          *v347 = v349;
                                                                          goto LABEL_579;
                                                                        }
                                                                        v350 = 8 - v348;
                                                                        if ( v346 >= 4 )
                                                                        {
                                                                          v351 = *(unsigned __int8 *)(*(_QWORD *)v345 + 3LL)
                                                                               | ((*(unsigned __int8 *)(*(_QWORD *)v345 + 2LL)
                                                                                 | (((**(unsigned __int8 **)v345 << 8)
                                                                                   | *(unsigned __int8 *)(*(_QWORD *)v345 + 1LL)) << 8)) << 8);
                                                                          *(_QWORD *)v345 += 4LL;
                                                                          v345[2] = v346 - 4;
                                                                          v349 = 32 - v350;
                                                                          v345[3] = v351;
                                                                          goto LABEL_574;
                                                                        }
                                                                        CInputBitStream::finalLoad(
                                                                          *((CInputBitStream **)this + 675),
                                                                          v345[3] & *((_DWORD *)&GetMask + v348),
                                                                          v350);
LABEL_579:
                                                                        if ( (*v95 & 8) == 0 )
                                                                          goto LABEL_591;
                                                                        v352 = (unsigned int *)*((_QWORD *)this + 675);
                                                                        if ( !v352[5] )
                                                                        {
                                                                          v353 = v352[2];
                                                                          v354 = v352 + 4;
                                                                          if ( (unsigned int)(8 * v353) >= 8 )
                                                                          {
LABEL_584:
                                                                            v355 = *v354;
                                                                            if ( (unsigned int)v355 >= 8 )
                                                                            {
                                                                              v356 = v355 - 8;
LABEL_586:
                                                                              *v354 = v356;
                                                                              goto LABEL_591;
                                                                            }
                                                                            v357 = 8 - v355;
                                                                            if ( v353 >= 4 )
                                                                            {
                                                                              v358 = *(unsigned __int8 *)(*(_QWORD *)v352 + 3LL)
                                                                                   | ((*(unsigned __int8 *)(*(_QWORD *)v352 + 2LL)
                                                                                     | (((**(unsigned __int8 **)v352 << 8)
                                                                                       | *(unsigned __int8 *)(*(_QWORD *)v352 + 1LL)) << 8)) << 8);
                                                                              *(_QWORD *)v352 += 4LL;
                                                                              v352[2] = v353 - 4;
                                                                              v356 = 32 - v357;
                                                                              v352[3] = v358;
                                                                              goto LABEL_586;
                                                                            }
                                                                            CInputBitStream::finalLoad(
                                                                              *((CInputBitStream **)this + 675),
                                                                              v352[3] & *((_DWORD *)&GetMask + v355),
                                                                              v357);
LABEL_591:
                                                                            if ( (*v95 & 4) == 0 )
                                                                              goto LABEL_603;
                                                                            v359 = (unsigned int *)*((_QWORD *)this + 675);
                                                                            if ( !v359[5] )
                                                                            {
                                                                              v360 = v359[2];
                                                                              v361 = v359 + 4;
                                                                              if ( (unsigned int)(8 * v360) >= 8 )
                                                                              {
LABEL_596:
                                                                                v362 = *v361;
                                                                                if ( (unsigned int)v362 < 8 )
                                                                                {
                                                                                  v364 = 8 - v362;
                                                                                  if ( v360 < 4 )
                                                                                  {
                                                                                    CInputBitStream::finalLoad(
                                                                                      *((CInputBitStream **)this + 675),
                                                                                      v359[3]
                                                                                    & *((_DWORD *)&GetMask + v362),
                                                                                      v364);
                                                                                    goto LABEL_603;
                                                                                  }
                                                                                  v365 = *(unsigned __int8 *)(*(_QWORD *)v359 + 3LL)
                                                                                       | ((*(unsigned __int8 *)(*(_QWORD *)v359 + 2LL)
                                                                                         | ((*(unsigned __int8 *)(*(_QWORD *)v359 + 1LL)
                                                                                           | (**(unsigned __int8 **)v359 << 8)) << 8)) << 8);
                                                                                  *(_QWORD *)v359 += 4LL;
                                                                                  v359[2] = v360 - 4;
                                                                                  v363 = 32 - v364;
                                                                                  v359[3] = v365;
                                                                                }
                                                                                else
                                                                                {
                                                                                  v363 = v362 - 8;
                                                                                }
                                                                                *v361 = v363;
LABEL_603:
                                                                                v222 = (*v95 & 0x20) == 0;
LABEL_604:
                                                                                if ( v222 )
                                                                                  goto LABEL_366;
                                                                                v366 = (unsigned int *)*((_QWORD *)this + 675);
                                                                                if ( !v366[5] )
                                                                                {
                                                                                  v367 = v366[2];
                                                                                  v368 = v366 + 4;
                                                                                  if ( (unsigned int)(8 * v367) >= 8 )
                                                                                  {
LABEL_609:
                                                                                    v369 = *v368;
                                                                                    if ( (unsigned int)v369 >= 8 )
                                                                                    {
                                                                                      v223 = v369 - 8;
LABEL_361:
                                                                                      *v368 = v223;
                                                                                      goto LABEL_366;
                                                                                    }
                                                                                    v224 = 8 - v369;
                                                                                    if ( v367 >= 4 )
                                                                                    {
                                                                                      v225 = *(_QWORD *)v366 + 4LL;
                                                                                      v366[3] = *(unsigned __int8 *)(*(_QWORD *)v366 + 3LL)
                                                                                              | ((*(unsigned __int8 *)(*(_QWORD *)v366 + 2LL)
                                                                                                | (((**(unsigned __int8 **)v366 << 8)
                                                                                                  | *(unsigned __int8 *)(*(_QWORD *)v366 + 1LL)) << 8)) << 8);
                                                                                      *(_QWORD *)v366 = v225;
                                                                                      v366[2] = v367 - 4;
                                                                                      v223 = 32 - v224;
                                                                                      goto LABEL_361;
                                                                                    }
                                                                                    CInputBitStream::finalLoad(
                                                                                      *((CInputBitStream **)this + 675),
                                                                                      v366[3]
                                                                                    & *((_DWORD *)&GetMask + v369),
                                                                                      v224);
LABEL_366:
                                                                                    if ( (*v95 & 2) == 0 )
                                                                                      goto LABEL_615;
                                                                                    v226 = (unsigned int *)*((_QWORD *)this + 675);
                                                                                    if ( !v226[5] )
                                                                                    {
                                                                                      v227 = v226[2];
                                                                                      v228 = v226 + 4;
                                                                                      if ( (unsigned int)(8 * v227) >= 8 )
                                                                                      {
LABEL_371:
                                                                                        v229 = *v228;
                                                                                        if ( (unsigned int)v229 >= 8 )
                                                                                        {
                                                                                          v232 = v229 - 8;
                                                                                          goto LABEL_612;
                                                                                        }
                                                                                        v230 = 8 - v229;
                                                                                        if ( v227 >= 4 )
                                                                                        {
                                                                                          v231 = *(_QWORD *)v226 + 4LL;
                                                                                          v226[3] = *(unsigned __int8 *)(*(_QWORD *)v226 + 3LL) | ((*(unsigned __int8 *)(*(_QWORD *)v226 + 2LL) | ((*(unsigned __int8 *)(*(_QWORD *)v226 + 1LL) | (**(unsigned __int8 **)v226 << 8)) << 8)) << 8);
                                                                                          *(_QWORD *)v226 = v231;
                                                                                          v226[2] = v227 - 4;
                                                                                          v232 = 32 - v230;
LABEL_612:
                                                                                          *v228 = v232;
                                                                                          goto LABEL_615;
                                                                                        }
                                                                                        CInputBitStream::finalLoad(
                                                                                          *((CInputBitStream **)this
                                                                                          + 675),
                                                                                          v226[3]
                                                                                        & *((_DWORD *)&GetMask + v229),
                                                                                          v230);
LABEL_615:
                                                                                        if ( (*v95 & 1) == 0 )
                                                                                          return;
                                                                                        v87 = (_DWORD *)*((_QWORD *)this + 675);
                                                                                        if ( !v87[5] )
                                                                                        {
                                                                                          v88 = v87[2];
                                                                                          v89 = v87 + 4;
                                                                                          if ( (unsigned int)(8 * v88) >= 8
                                                                                            || (unsigned int)(*v89 + 8 * v88) >= 8 )
                                                                                          {
                                                                                            v90 = (unsigned int)*v89;
                                                                                            if ( (unsigned int)v90 < 8 )
                                                                                            {
                                                                                              v91 = 8 - v90;
                                                                                              if ( v88 >= 4 )
                                                                                              {
                                                                                                v92 = *(_QWORD *)v87;
                                                                                                v94 = *(unsigned __int8 *)(*(_QWORD *)v87 + 1LL);
                                                                                                v93 = **(unsigned __int8 **)v87 << 8;
                                                                                                goto LABEL_623;
                                                                                              }
                                                                                              goto LABEL_624;
                                                                                            }
LABEL_620:
                                                                                            *v89 = v90 - 8;
                                                                                            return;
                                                                                          }
                                                                                        }
                                                                                        goto LABEL_625;
                                                                                      }
                                                                                      if ( *v228 + 8 * v227 >= 8 )
                                                                                      {
                                                                                        v95 = (char *)this + 288;
                                                                                        goto LABEL_371;
                                                                                      }
                                                                                    }
                                                                                    v226[5] = 1;
                                                                                    goto LABEL_615;
                                                                                  }
                                                                                  if ( *v368 + 8 * v367 >= 8 )
                                                                                  {
                                                                                    v95 = (char *)this + 288;
                                                                                    goto LABEL_609;
                                                                                  }
                                                                                }
                                                                                v366[5] = 1;
                                                                                goto LABEL_366;
                                                                              }
                                                                              if ( *v361 + 8 * v360 >= 8 )
                                                                              {
                                                                                v95 = (char *)this + 288;
                                                                                goto LABEL_596;
                                                                              }
                                                                            }
                                                                            v359[5] = 1;
                                                                            goto LABEL_603;
                                                                          }
                                                                          if ( *v354 + 8 * v353 >= 8 )
                                                                          {
                                                                            v95 = (char *)this + 288;
                                                                            goto LABEL_584;
                                                                          }
                                                                        }
                                                                        v352[5] = 1;
                                                                        goto LABEL_591;
                                                                      }
                                                                      if ( *v347 + 8 * v346 >= 8 )
                                                                      {
                                                                        v95 = (char *)this + 288;
                                                                        goto LABEL_572;
                                                                      }
                                                                    }
                                                                    v345[5] = 1;
                                                                    goto LABEL_579;
                                                                  }
                                                                  if ( *v340 + 8 * v339 >= 8 )
                                                                  {
                                                                    v95 = (char *)this + 288;
                                                                    goto LABEL_560;
                                                                  }
                                                                }
                                                                v338[5] = 1;
                                                                goto LABEL_567;
                                                              }
                                                              if ( *v333 + 8 * v332 >= 8 )
                                                              {
                                                                v95 = (char *)this + 288;
                                                                goto LABEL_548;
                                                              }
                                                            }
                                                            v331[5] = 1;
                                                            goto LABEL_555;
                                                          }
                                                          if ( *v326 + 8 * v325 >= 8 )
                                                          {
                                                            v95 = (char *)this + 288;
                                                            goto LABEL_536;
                                                          }
                                                        }
                                                        v324[5] = 1;
                                                        goto LABEL_543;
                                                      }
                                                      if ( *v319 + 8 * v318 >= 8 )
                                                      {
                                                        v95 = (char *)this + 288;
                                                        goto LABEL_524;
                                                      }
                                                    }
                                                    v317[5] = 1;
                                                    goto LABEL_531;
                                                  }
                                                  if ( *v312 + 8 * v311 >= 4 )
                                                  {
                                                    v95 = (char *)this + 288;
                                                    goto LABEL_512;
                                                  }
                                                }
                                                v310[5] = 1;
                                                goto LABEL_519;
                                              }
                                              if ( *v305 + 8 * v304 >= 8 )
                                              {
                                                v95 = (char *)this + 288;
                                                goto LABEL_500;
                                              }
                                            }
                                            v303[5] = 1;
                                            goto LABEL_507;
                                          }
                                          if ( *v298 + 8 * v297 >= 8 )
                                          {
                                            v95 = (char *)this + 288;
                                            goto LABEL_488;
                                          }
                                        }
                                        v296[5] = 1;
                                        goto LABEL_495;
                                      }
                                      if ( *v291 + 8 * v290 >= 8 )
                                      {
                                        v95 = (char *)this + 288;
                                        goto LABEL_476;
                                      }
                                    }
                                    v289[5] = 1;
                                    goto LABEL_483;
                                  }
                                  if ( *v284 + 8 * v283 >= 8 )
                                  {
                                    v95 = (char *)this + 288;
                                    goto LABEL_464;
                                  }
                                }
                                v282[5] = 1;
                                goto LABEL_471;
                              }
                              if ( *v277 + 8 * v276 >= 8 )
                              {
                                v95 = (char *)this + 288;
                                goto LABEL_452;
                              }
                            }
                            v275[5] = 1;
                            goto LABEL_459;
                          }
                          if ( *v270 + 8 * v269 >= 8 )
                          {
                            v95 = (char *)this + 288;
                            goto LABEL_440;
                          }
                        }
                        v268[5] = 1;
                        goto LABEL_447;
                      }
                      if ( *v263 + 8 * v262 >= 8 )
                      {
                        v95 = (char *)this + 288;
                        goto LABEL_428;
                      }
                    }
                    v261[5] = 1;
                    goto LABEL_435;
                  }
                  if ( *v256 + 8 * v255 >= 8 )
                  {
                    v95 = (char *)this + 288;
                    goto LABEL_416;
                  }
                }
                v254[5] = 1;
                goto LABEL_423;
              }
              if ( *v249 + 8 * v248 >= 8 )
              {
                v95 = (char *)this + 288;
                goto LABEL_404;
              }
            }
            v247[5] = 1;
            goto LABEL_411;
          }
          if ( *v242 + 8 * v241 >= 8 )
          {
            v95 = (char *)this + 288;
            goto LABEL_392;
          }
        }
        v240[5] = 1;
        goto LABEL_399;
      }
      if ( *v235 + 8 * v234 >= 8 )
      {
        v95 = (char *)this + 288;
        goto LABEL_380;
      }
    }
    *((_DWORD *)v233 + 5) = 1;
    goto LABEL_387;
  }
}

```

## disassembly

```asm
0x18002f614  push    rbx
0x18002f616  push    rbp
0x18002f617  push    rsi
0x18002f618  push    rdi
0x18002f619  push    r12
0x18002f61b  push    r13
0x18002f61d  push    r14
0x18002f61f  push    r15
0x18002f621  sub     rsp, 28h
0x18002f625  xor     r13d, r13d
0x18002f628  mov     rsi, rcx
0x18002f62b  cmp     [rcx+11Ch], r13d
0x18002f632  jnz     loc_180031A39
0x18002f638  mov     eax, [rcx+348h]
0x18002f63e  lea     ebp, [r13+1]
0x18002f642  test    eax, eax
0x18002f644  jnz     loc_18002FEC8
0x18002f64a  test    dword ptr [rcx+120h], 200000h
0x18002f654  lea     r14d, [r13+4]
0x18002f658  lea     r12d, [r13+20h]
0x18002f65c  lea     r15, ?GetMask@@3QBKB; ulong const near * const GetMask
0x18002f663  lea     edi, [rax+8]
0x18002f666  jz      loc_18002F707
0x18002f66c  mov     r9, [rcx+1518h]
0x18002f673  cmp     [r9+14h], r13d
0x18002f677  jnz     loc_18002F703
0x18002f67d  mov     r11d, [r9+8]
0x18002f681  lea     r8, [r9+10h]
0x18002f685  lea     ecx, ds:0[r11*8]
0x18002f68d  cmp     ecx, edi
0x18002f68f  jnb     short loc_18002F698
0x18002f691  add     ecx, [r8]
0x18002f694  cmp     ecx, edi
0x18002f696  jb      short loc_18002F703
0x18002f698  mov     eax, [r8]
0x18002f69b  cmp     eax, edi
0x18002f69d  jb      short loc_18002F6A7
0x18002f69f  add     eax, 0FFFFFFF8h
0x18002f6a2  mov     [r8], eax
0x18002f6a5  jmp     short loc_18002F707
0x18002f6a7  mov     r10d, edi
0x18002f6aa  sub     r10d, eax
0x18002f6ad  cmp     r11d, r14d
0x18002f6b0  jl      short loc_18002F6EE
0x18002f6b2  mov     rdx, [r9]
0x18002f6b5  movzx   eax, byte ptr [rdx+1]
0x18002f6b9  movzx   ecx, byte ptr [rdx]
0x18002f6bc  shl     ecx, 8
0x18002f6bf  or      ecx, eax
0x18002f6c1  movzx   eax, byte ptr [rdx+2]
0x18002f6c5  shl     ecx, 8
0x18002f6c8  or      ecx, eax
0x18002f6ca  movzx   eax, byte ptr [rdx+3]
0x18002f6ce  shl     ecx, 8
0x18002f6d1  or      ecx, eax
0x18002f6d3  lea     rax, [rdx+4]
0x18002f6d7  mov     [r9], rax
0x18002f6da  lea     eax, [r11-4]
0x18002f6de  mov     [r9+8], eax
0x18002f6e2  mov     eax, r12d
0x18002f6e5  sub     eax, r10d
0x18002f6e8  mov     [r9+0Ch], ecx
0x18002f6ec  jmp     short loc_18002F6A2
0x18002f6ee  mov     edx, [r15+rax*4]
0x18002f6f2  mov     r8d, r10d; unsigned int
0x18002f6f5  and     edx, [r9+0Ch]; unsigned int
0x18002f6f9  mov     rcx, r9; this
0x18002f6fc  call    ?finalLoad@CInputBitStream@@AEAAKKK@Z; CInputBitStream::finalLoad(ulong,ulong)
0x18002f701  jmp     short loc_18002F707
0x18002f703  mov     [r9+14h], ebp
0x18002f707  test    dword ptr [rsi+120h], 100000h
0x18002f711  jz      loc_18002F7B2
0x18002f717  mov     r9, [rsi+1518h]
0x18002f71e  cmp     [r9+14h], r13d
0x18002f722  jnz     loc_18002F7AE
0x18002f728  mov     r11d, [r9+8]
0x18002f72c  lea     r8, [r9+10h]
0x18002f730  lea     ecx, ds:0[r11*8]
0x18002f738  cmp     ecx, edi
0x18002f73a  jnb     short loc_18002F743
0x18002f73c  add     ecx, [r8]
0x18002f73f  cmp     ecx, edi
0x18002f741  jb      short loc_18002F7AE
0x18002f743  mov     eax, [r8]
0x18002f746  cmp     eax, edi
0x18002f748  jb      short loc_18002F752
0x18002f74a  add     eax, 0FFFFFFF8h
0x18002f74d  mov     [r8], eax
0x18002f750  jmp     short loc_18002F7B2
0x18002f752  mov     r10d, edi
0x18002f755  sub     r10d, eax
0x18002f758  cmp     r11d, r14d
0x18002f75b  jl      short loc_18002F799
0x18002f75d  mov     rdx, [r9]
0x18002f760  movzx   eax, byte ptr [rdx+1]
0x18002f764  movzx   ecx, byte ptr [rdx]
0x18002f767  shl     ecx, 8
0x18002f76a  or      ecx, eax
0x18002f76c  movzx   eax, byte ptr [rdx+2]
0x18002f770  shl     ecx, 8
0x18002f773  or      ecx, eax
0x18002f775  movzx   eax, byte ptr [rdx+3]
0x18002f779  shl     ecx, 8
0x18002f77c  or      ecx, eax
0x18002f77e  lea     rax, [rdx+4]
0x18002f782  mov     [r9], rax
0x18002f785  lea     eax, [r11-4]
0x18002f789  mov     [r9+8], eax
0x18002f78d  mov     eax, r12d
0x18002f790  sub     eax, r10d
0x18002f793  mov     [r9+0Ch], ecx
0x18002f797  jmp     short loc_18002F74D
0x18002f799  mov     edx, [r15+rax*4]
0x18002f79d  mov     r8d, r10d; unsigned int
0x18002f7a0  and     edx, [r9+0Ch]; unsigned int
0x18002f7a4  mov     rcx, r9; this
0x18002f7a7  call    ?finalLoad@CInputBitStream@@AEAAKKK@Z; CInputBitStream::finalLoad(ulong,ulong)
0x18002f7ac  jmp     short loc_18002F7B2
0x18002f7ae  mov     [r9+14h], ebp
0x18002f7b2  test    dword ptr [rsi+120h], 80000h
0x18002f7bc  jz      loc_18002F85D
0x18002f7c2  mov     r9, [rsi+1518h]
0x18002f7c9  cmp     [r9+14h], r13d
0x18002f7cd  jnz     loc_18002F859
0x18002f7d3  mov     r11d, [r9+8]
0x18002f7d7  lea     r8, [r9+10h]
0x18002f7db  lea     ecx, ds:0[r11*8]
0x18002f7e3  cmp     ecx, edi
0x18002f7e5  jnb     short loc_18002F7EE
0x18002f7e7  add     ecx, [r8]
0x18002f7ea  cmp     ecx, edi
0x18002f7ec  jb      short loc_18002F859
0x18002f7ee  mov     eax, [r8]
0x18002f7f1  cmp     eax, edi
0x18002f7f3  jb      short loc_18002F7FD
0x18002f7f5  add     eax, 0FFFFFFF8h
0x18002f7f8  mov     [r8], eax
0x18002f7fb  jmp     short loc_18002F85D
0x18002f7fd  mov     r10d, edi
0x18002f800  sub     r10d, eax
0x18002f803  cmp     r11d, r14d
0x18002f806  jl      short loc_18002F844
0x18002f808  mov     rdx, [r9]
0x18002f80b  movzx   eax, byte ptr [rdx]
0x18002f80e  movzx   ecx, byte ptr [rdx+1]
0x18002f812  shl     eax, 8
0x18002f815  or      ecx, eax
0x18002f817  movzx   eax, byte ptr [rdx+2]
0x18002f81b  shl     ecx, 8
0x18002f81e  or      ecx, eax
0x18002f820  movzx   eax, byte ptr [rdx+3]
0x18002f824  shl     ecx, 8
0x18002f827  or      ecx, eax
0x18002f829  lea     rax, [rdx+4]
0x18002f82d  mov     [r9], rax
0x18002f830  lea     eax, [r11-4]
0x18002f834  mov     [r9+8], eax
0x18002f838  mov     eax, r12d
0x18002f83b  sub     eax, r10d
0x18002f83e  mov     [r9+0Ch], ecx
0x18002f842  jmp     short loc_18002F7F8
0x18002f844  mov     edx, [r15+rax*4]
0x18002f848  mov     r8d, r10d; unsigned int
0x18002f84b  and     edx, [r9+0Ch]; unsigned int
0x18002f84f  mov     rcx, r9; this
0x18002f852  call    ?finalLoad@CInputBitStream@@AEAAKKK@Z; CInputBitStream::finalLoad(ulong,ulong)
0x18002f857  jmp     short loc_18002F85D
0x18002f859  mov     [r9+14h], ebp
0x18002f85d  test    dword ptr [rsi+120h], 40000h
0x18002f867  jz      loc_18002F908
0x18002f86d  mov     r9, [rsi+1518h]
0x18002f874  cmp     [r9+14h], r13d
0x18002f878  jnz     loc_18002F904
0x18002f87e  mov     r11d, [r9+8]
0x18002f882  lea     r8, [r9+10h]
0x18002f886  lea     ecx, ds:0[r11*8]
0x18002f88e  cmp     ecx, edi
0x18002f890  jnb     short loc_18002F899
0x18002f892  add     ecx, [r8]
0x18002f895  cmp     ecx, edi
0x18002f897  jb      short loc_18002F904
0x18002f899  mov     eax, [r8]
0x18002f89c  cmp     eax, edi
0x18002f89e  jb      short loc_18002F8A8
0x18002f8a0  add     eax, 0FFFFFFF8h
0x18002f8a3  mov     [r8], eax
0x18002f8a6  jmp     short loc_18002F908
0x18002f8a8  mov     r10d, edi
0x18002f8ab  sub     r10d, eax
0x18002f8ae  cmp     r11d, r14d
0x18002f8b1  jl      short loc_18002F8EF
0x18002f8b3  mov     rdx, [r9]
0x18002f8b6  movzx   eax, byte ptr [rdx]
0x18002f8b9  movzx   ecx, byte ptr [rdx+1]
0x18002f8bd  shl     eax, 8
0x18002f8c0  or      ecx, eax
0x18002f8c2  movzx   eax, byte ptr [rdx+2]
0x18002f8c6  shl     ecx, 8
0x18002f8c9  or      ecx, eax
0x18002f8cb  movzx   eax, byte ptr [rdx+3]
0x18002f8cf  shl     ecx, 8
0x18002f8d2  or      ecx, eax
0x18002f8d4  lea     rax, [rdx+4]
0x18002f8d8  mov     [r9], rax
0x18002f8db  lea     eax, [r11-4]
0x18002f8df  mov     [r9+8], eax
0x18002f8e3  mov     eax, r12d
0x18002f8e6  sub     eax, r10d
0x18002f8e9  mov     [r9+0Ch], ecx
0x18002f8ed  jmp     short loc_18002F8A3
0x18002f8ef  mov     edx, [r15+rax*4]
0x18002f8f3  mov     r8d, r10d; unsigned int
0x18002f8f6  and     edx, [r9+0Ch]; unsigned int
0x18002f8fa  mov     rcx, r9; this
0x18002f8fd  call    ?finalLoad@CInputBitStream@@AEAAKKK@Z; CInputBitStream::finalLoad(ulong,ulong)
0x18002f902  jmp     short loc_18002F908
0x18002f904  mov     [r9+14h], ebp
0x18002f908  test    dword ptr [rsi+120h], 20000h
0x18002f912  jz      loc_18002F9B3
0x18002f918  mov     r9, [rsi+1518h]
0x18002f91f  cmp     [r9+14h], r13d
0x18002f923  jnz     loc_18002F9AF
0x18002f929  mov     r11d, [r9+8]
0x18002f92d  lea     r8, [r9+10h]
0x18002f931  lea     ecx, ds:0[r11*8]
0x18002f939  cmp     ecx, edi
0x18002f93b  jnb     short loc_18002F944
0x18002f93d  add     ecx, [r8]
0x18002f940  cmp     ecx, edi
0x18002f942  jb      short loc_18002F9AF
0x18002f944  mov     eax, [r8]
0x18002f947  cmp     eax, edi
0x18002f949  jb      short loc_18002F953
0x18002f94b  add     eax, 0FFFFFFF8h
0x18002f94e  mov     [r8], eax
0x18002f951  jmp     short loc_18002F9B3
0x18002f953  mov     r10d, edi
0x18002f956  sub     r10d, eax
0x18002f959  cmp     r11d, r14d
0x18002f95c  jl      short loc_18002F99A
0x18002f95e  mov     rdx, [r9]
0x18002f961  movzx   eax, byte ptr [rdx+1]
0x18002f965  movzx   ecx, byte ptr [rdx]
0x18002f968  shl     ecx, 8
0x18002f96b  or      ecx, eax
0x18002f96d  movzx   eax, byte ptr [rdx+2]
0x18002f971  shl     ecx, 8
0x18002f974  or      ecx, eax
0x18002f976  movzx   eax, byte ptr [rdx+3]
0x18002f97a  shl     ecx, 8
0x18002f97d  or      ecx, eax
0x18002f97f  lea     rax, [rdx+4]
0x18002f983  mov     [r9], rax
0x18002f986  lea     eax, [r11-4]
0x18002f98a  mov     [r9+8], eax
0x18002f98e  mov     eax, r12d
0x18002f991  sub     eax, r10d
0x18002f994  mov     [r9+0Ch], ecx
0x18002f998  jmp     short loc_18002F94E
0x18002f99a  mov     edx, [r15+rax*4]
0x18002f99e  mov     r8d, r10d; unsigned int
0x18002f9a1  and     edx, [r9+0Ch]; unsigned int
0x18002f9a5  mov     rcx, r9; this
0x18002f9a8  call    ?finalLoad@CInputBitStream@@AEAAKKK@Z; CInputBitStream::finalLoad(ulong,ulong)
0x18002f9ad  jmp     short loc_18002F9B3
0x18002f9af  mov     [r9+14h], ebp
0x18002f9b3  test    dword ptr [rsi+120h], 10000h
0x18002f9bd  jz      loc_18002FA5E
0x18002f9c3  mov     r9, [rsi+1518h]
0x18002f9ca  cmp     [r9+14h], r13d
0x18002f9ce  jnz     loc_18002FA5A
0x18002f9d4  mov     r11d, [r9+8]
0x18002f9d8  lea     r8, [r9+10h]
0x18002f9dc  lea     ecx, ds:0[r11*8]
0x18002f9e4  cmp     ecx, edi
0x18002f9e6  jnb     short loc_18002F9EF
0x18002f9e8  add     ecx, [r8]
0x18002f9eb  cmp     ecx, edi
0x18002f9ed  jb      short loc_18002FA5A
0x18002f9ef  mov     eax, [r8]
0x18002f9f2  cmp     eax, edi
0x18002f9f4  jb      short loc_18002F9FE
0x18002f9f6  add     eax, 0FFFFFFF8h
0x18002f9f9  mov     [r8], eax
0x18002f9fc  jmp     short loc_18002FA5E
0x18002f9fe  mov     r10d, edi
0x18002fa01  sub     r10d, eax
0x18002fa04  cmp     r11d, r14d
0x18002fa07  jl      short loc_18002FA45
0x18002fa09  mov     rdx, [r9]
0x18002fa0c  movzx   eax, byte ptr [rdx]
0x18002fa0f  movzx   ecx, byte ptr [rdx+1]
0x18002fa13  shl     eax, 8
0x18002fa16  or      ecx, eax
0x18002fa18  movzx   eax, byte ptr [rdx+2]
0x18002fa1c  shl     ecx, 8
0x18002fa1f  or      ecx, eax
0x18002fa21  movzx   eax, byte ptr [rdx+3]
0x18002fa25  shl     ecx, 8
0x18002fa28  or      ecx, eax
  ... truncated ...
```
