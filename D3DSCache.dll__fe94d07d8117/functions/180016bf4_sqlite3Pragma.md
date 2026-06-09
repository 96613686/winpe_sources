# sqlite3Pragma

- ea: `0x180016bf4`
- end: `0x18001a6f6`
- name: `sqlite3Pragma`
- size: `15106`
- prototype: ``
- caller_count: `1`
- callee_count: `119`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001bc30`

## callees

- `0x180007a00`
- `0x18000b4bc`
- `0x180012470`
- `0x180014464`
- `0x1800156f4`
- `0x180015754`
- `0x180016b18`
- `0x180016bf4`
- `0x180020410`
- `0x180027eb0`
- `0x18002817c`
- `0x18002b81c`
- `0x18002b840`
- `0x18002b938`
- `0x18002e290`
- `0x18003183c`
- `0x180033050`
- `0x1800337f4`
- `0x180034900`
- `0x180036430`
- `0x180036770`
- `0x1800367a0`
- `0x1800369e4`
- `0x180037880`
- `0x180038974`
- `0x180038c94`
- `0x180038e54`
- `0x18003ab40`
- `0x18003aca0`
- `0x18003ad5c`
- `0x18003af40`
- `0x18003b5b4`
- `0x18003b8a0`
- `0x18003be78`
- `0x18003bff4`
- `0x18003c5f4`
- `0x18003c8d4`
- `0x18003d480`
- `0x18003da90`
- `0x18003e4f8`
- `0x18003e68c`
- `0x18003f5a8`
- `0x18003ff28`
- `0x180041574`
- `0x180041894`
- `0x180041c54`
- `0x180042078`
- `0x1800421bc`
- `0x180042260`
- `0x18004242c`

## string_xrefs

- `0x18001a18f`: `not a writable directory`
- `0x18001a63d`: `Safety level may not be changed inside a transaction`

## pseudocode

```c
__int64 __fastcall sqlite3Pragma(_QWORD **a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  _QWORD *v5; // r13
  _QWORD **v8; // rdi
  __int64 result; // rax
  __int64 v10; // r15
  __int64 v11; // r8
  int v12; // ebx
  char *v13; // rsi
  unsigned __int8 *v14; // r14
  __int64 v15; // rcx
  const char **v16; // rax
  __int64 v17; // rcx
  __int64 (__fastcall *v18)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // r10
  int v19; // eax
  int v20; // ebx
  __int64 v21; // rcx
  __int64 v22; // rax
  int v23; // ebx
  int v24; // eax
  const char **v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r10
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // rdx
  __int64 v39; // rcx
  unsigned __int64 v40; // rbx
  __int64 v41; // rbx
  int v42; // eax
  unsigned int AutoVacuum; // edi
  int v44; // ebx
  _DWORD *v45; // rax
  unsigned int v46; // r12d
  __int64 v47; // rdx
  unsigned int v48; // edi
  __int64 v49; // rcx
  __int64 v50; // r10
  unsigned int v51; // r11d
  __int64 v52; // rdi
  unsigned int v53; // ebx
  _DWORD *v54; // rax
  int Int32; // eax
  __int64 v56; // rdx
  int v57; // ebx
  bool v58; // zf
  __int64 v59; // rbx
  char Boolean; // al
  __int64 v61; // rcx
  __int64 v62; // rbx
  unsigned __int64 v63; // rcx
  unsigned int v64; // ecx
  unsigned int v65; // ecx
  unsigned int v66; // ecx
  __int64 v67; // rax
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // rax
  unsigned int v71; // ebx
  __int64 v72; // rax
  __int64 **v73; // rbx
  unsigned int v74; // esi
  unsigned __int8 v75; // al
  unsigned int i; // ebx
  __int64 v77; // rcx
  __int64 v78; // rax
  __int64 v79; // r8
  __int64 v80; // r9
  __int64 v81; // rdx
  unsigned int v82; // ecx
  unsigned int v83; // ecx
  unsigned int v84; // ecx
  unsigned int v85; // ecx
  unsigned int v86; // ecx
  unsigned int v87; // ecx
  unsigned int v88; // ecx
  unsigned int v89; // ecx
  __int64 v90; // rax
  __int64 v91; // rbx
  unsigned int v92; // eax
  __int64 v93; // rbx
  unsigned int v94; // edi
  __int64 v95; // r9
  __int64 v96; // rax
  unsigned int v97; // eax
  const char **v98; // rbx
  bool v99; // cf
  __int64 v100; // r9
  unsigned int v101; // esi
  __int64 v102; // rdx
  __int64 v103; // rcx
  unsigned int v104; // ebx
  __int64 v105; // rax
  unsigned int v106; // ebx
  __int64 v107; // rax
  __int64 v108; // rdi
  _QWORD *v109; // rdi
  __int64 v110; // rax
  __int64 v111; // rbx
  unsigned int v112; // eax
  unsigned int v113; // r9d
  __int64 v114; // rdx
  unsigned int v115; // eax
  __int64 v116; // rcx
  int v117; // esi
  __int64 v118; // rcx
  __int64 v119; // rdx
  __int64 v120; // r8
  int v121; // eax
  __int64 v122; // r8
  int v123; // r10d
  int v124; // eax
  int v125; // ecx
  _QWORD *v126; // rcx
  __int64 Table; // rax
  int v128; // eax
  __int64 v129; // rcx
  const char **v130; // rbx
  int v131; // ecx
  int v132; // r8d
  int v133; // ecx
  __int64 j; // rax
  __int64 v135; // rax
  int v136; // r8d
  __int64 v137; // rsi
  int v138; // r14d
  const char **v139; // r8
  __int64 v140; // rbx
  __int64 v141; // rax
  const char **v142; // rcx
  int v143; // eax
  int v144; // edx
  int v145; // r13d
  int k; // edi
  int v147; // r9d
  int v148; // ebx
  __int64 v149; // rax
  __int64 v150; // rbx
  unsigned int v151; // ebx
  char *v152; // rdx
  char **m; // rbx
  char v154; // dl
  __int64 v155; // rcx
  int v156; // r11d
  _DWORD *v157; // rax
  int v158; // ebx
  __int64 v159; // rax
  __int64 v160; // r8
  __int64 v161; // rax
  int v162; // eax
  __int64 v163; // r9
  unsigned int v164; // eax
  __int64 v165; // rcx
  __int64 v166; // rax
  __int64 v167; // rax
  int v168; // ecx
  _QWORD *v169; // rax
  __int64 v170; // rdx
  __int64 v171; // rdx
  int v172; // eax
  int *v173; // rax
  int v174; // r9d
  _QWORD *v175; // r8
  __int64 v176; // rsi
  __int64 v177; // rdx
  __int64 v178; // rcx
  __int64 n; // rdx
  int v180; // ecx
  unsigned int v181; // ebx
  __int64 v182; // rax
  __int64 v183; // r10
  __int64 v184; // r14
  _QWORD *v185; // rdi
  unsigned int v186; // esi
  __int64 v187; // rax
  unsigned int v188; // r9d
  const char ***v189; // rdx
  __int64 v190; // rcx
  const char **v191; // rax
  unsigned int v192; // r13d
  unsigned int v193; // ebx
  __int64 Op; // rax
  __int64 v195; // rax
  __int64 v196; // rbx
  __int64 v197; // rax
  const char **v198; // rbx
  unsigned int TempRange; // eax
  __int64 v200; // r10
  int v201; // edx
  int v202; // edi
  const char *v203; // r13
  int v204; // eax
  int v205; // r9d
  int v206; // edx
  int ii; // r8d
  int v208; // eax
  int v209; // r9d
  unsigned int v210; // ebx
  __int64 v211; // rax
  __int64 v212; // rax
  int v213; // ebx
  int v214; // r15d
  __int64 v215; // r13
  unsigned int v216; // r14d
  __int64 v217; // rdx
  int v218; // r8d
  __int64 v219; // rcx
  BOOL v220; // r8d
  int v221; // r11d
  int v222; // edx
  int v223; // eax
  _BYTE *v224; // r9
  int v225; // r8d
  __int64 v226; // rax
  __int64 v227; // rdx
  __int64 v228; // r8
  __int16 v229; // ax
  unsigned int v230; // ecx
  const char **v231; // rax
  unsigned int v232; // r9d
  int v233; // ecx
  int v234; // r10d
  __int64 v235; // rax
  int v236; // edx
  __int64 v237; // rax
  __int64 v238; // rdx
  __int64 v239; // r10
  __int64 v240; // r11
  __int64 v241; // rax
  char v242; // dl
  int v243; // ecx
  int v244; // eax
  const char *v245; // rdx
  const char **v246; // rax
  const char **v247; // rcx
  int v248; // eax
  unsigned int v249; // r15d
  int v250; // ebx
  const char **v251; // r13
  __int64 v252; // rax
  char *v253; // rbx
  int v254; // ecx
  __int64 v255; // r8
  int v256; // edx
  const char **v257; // r13
  int v258; // r14d
  unsigned int v259; // ebx
  int v260; // r14d
  unsigned int v261; // ebx
  unsigned int v262; // edx
  int v263; // r13d
  unsigned int v264; // ebx
  __int64 v265; // rax
  unsigned int v266; // r14d
  int v267; // edi
  __int64 v268; // rax
  unsigned int v269; // ebx
  __int64 v270; // rax
  int v271; // r8d
  __int64 v272; // rax
  __int64 v273; // rdx
  int v274; // ebx
  __int64 v275; // rax
  _QWORD *v276; // rax
  __int64 v277; // r8
  _QWORD *v278; // rsi
  int v279; // r14d
  __int64 v280; // rbx
  __int64 ElementWithHash; // rax
  __int64 v282; // rax
  __int64 *v283; // rax
  __int64 v284; // rax
  unsigned int v285; // ebx
  __int64 v286; // rax
  __int64 v287; // rax
  __int64 v288; // rax
  __int64 v289; // r8
  __int64 v290; // rax
  int v291; // r9d
  unsigned int v292; // ecx
  unsigned int v293; // ecx
  unsigned int v294; // ecx
  unsigned int v295; // ecx
  _QWORD *v296; // rdx
  int v297; // r8d
  __int64 v298; // rsi
  __int64 v299; // rax
  __int64 v300; // rbx
  int v301; // edx
  __int64 v302; // rsi
  __int64 v303; // rax
  __int64 v304; // rbx
  int v305; // eax
  int v306; // ecx
  __int64 v307; // rax
  unsigned int v308; // edi
  int v309; // eax
  int v310; // r9d
  int v311; // r8d
  const char *v312; // rdi
  __int64 v313; // rcx
  __int64 v314; // rdx
  int v315; // eax
  int v316; // eax
  int mm; // r8d
  int v318; // r8d
  __int64 *v319; // rcx
  __int64 v320; // rax
  __int64 v321; // rdi
  __int64 v322; // rcx
  __int64 v323; // r8
  int v324; // r8d
  int v325; // edi
  __int64 v326; // rax
  unsigned int v327; // edx
  int v328; // eax
  int v329; // r14d
  int v330; // ecx
  _QWORD *kk; // rbx
  unsigned int v332; // ecx
  unsigned int v333; // ecx
  unsigned int v334; // ecx
  int v335; // ebx
  int v336; // edi
  __int64 nn; // rbx
  __int64 v338; // rbx
  int v339; // ecx
  __int64 v340; // rdx
  int v341; // eax
  __int64 i1; // rax
  __int64 v343; // rax
  int v344; // edx
  unsigned int v345; // r9d
  __int64 v346; // rcx
  int v347; // r8d
  int v348; // r8d
  __int64 v349; // rdx
  int TempReg; // ebx
  __int64 v351; // rdx
  int v352; // r9d
  __int64 v353; // rax
  __int64 v354; // rdx
  int v355; // r9d
  int v356; // r10d
  unsigned int v357; // ecx
  unsigned int v358; // ecx
  unsigned int v359; // ecx
  unsigned int v360; // ecx
  unsigned int v361; // ecx
  unsigned int v362; // ecx
  unsigned int v363; // ecx
  unsigned int v364; // ecx
  int v365; // ecx
  int v366; // ecx
  __int64 v367; // rcx
  __int64 v368; // rcx
  int v369; // eax
  int v370; // r8d
  __int64 v371; // rax
  __int64 v372; // rax
  __int64 v373; // rax
  const char **v374; // rdx
  int v375; // eax
  const char **v376; // r14
  __int64 v377; // rdi
  __int64 v378; // rcx
  int v379; // edi
  __int64 v380; // rcx
  __int64 v381; // rsi
  _QWORD *jj; // rax
  __int64 v383; // r8
  __int64 v384; // rax
  __int64 v385; // rax
  __int64 *v386; // r14
  const char *v387; // rax
  __int64 v388; // rcx
  int v389; // ebx
  int v390; // esi
  int v391; // edi
  __int64 v392; // rax
  __int64 v393; // rax
  __int64 v394; // rbx
  signed int v395; // edx
  __int64 v396; // rax
  int v397; // ecx
  __int64 v398; // rsi
  signed int v399; // r8d
  __int64 v400; // r14
  __int16 v401; // ax
  int v402; // edi
  __int64 v403; // rax
  __int64 v404; // r9
  unsigned int v405; // r11d
  __int64 v406; // rax
  int v407; // r10d
  int v408; // r11d
  int v409; // r8d
  __int64 v410; // r9
  const char *v411; // r8
  char SafetyLevel; // al
  __int64 v413; // rcx
  __int64 v414; // rdx
  int v415; // eax
  __int64 v416; // [rsp+20h] [rbp-E0h]
  __int64 v417; // [rsp+20h] [rbp-E0h]
  __int64 v418; // [rsp+20h] [rbp-E0h]
  int v419; // [rsp+20h] [rbp-E0h]
  __int64 v420; // [rsp+28h] [rbp-D8h]
  __int64 v421; // [rsp+28h] [rbp-D8h]
  __int64 v422; // [rsp+28h] [rbp-D8h]
  int v423; // [rsp+28h] [rbp-D8h]
  int v424; // [rsp+30h] [rbp-D0h]
  int v425; // [rsp+30h] [rbp-D0h]
  __int64 v426; // [rsp+38h] [rbp-C8h]
  int v427; // [rsp+40h] [rbp-C0h]
  int v428; // [rsp+48h] [rbp-B8h]
  unsigned int v429; // [rsp+60h] [rbp-A0h] BYREF
  int v430; // [rsp+64h] [rbp-9Ch] BYREF
  int IndexKey; // [rsp+68h] [rbp-98h]
  unsigned int v432; // [rsp+6Ch] [rbp-94h] BYREF
  int v433; // [rsp+70h] [rbp-90h]
  __int64 v434; // [rsp+78h] [rbp-88h] BYREF
  __int64 v435; // [rsp+80h] [rbp-80h]
  __int64 Index; // [rsp+88h] [rbp-78h]
  const char **v437; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v438; // [rsp+98h] [rbp-68h]
  char v439; // [rsp+9Ch] [rbp-64h]
  int v440; // [rsp+A0h] [rbp-60h]
  const char **v441; // [rsp+A8h] [rbp-58h]
  int v442; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v443; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int8 *v444; // [rsp+C0h] [rbp-40h]
  unsigned int v445; // [rsp+C8h] [rbp-38h]
  int v446; // [rsp+CCh] [rbp-34h] BYREF
  unsigned int v447; // [rsp+D0h] [rbp-30h]
  __int64 v448; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v449; // [rsp+E0h] [rbp-20h]
  unsigned int v450; // [rsp+E8h] [rbp-18h]
  int v451; // [rsp+ECh] [rbp-14h]
  char *v452; // [rsp+F0h] [rbp-10h]
  _QWORD *v453; // [rsp+F8h] [rbp-8h]
  __int64 v454; // [rsp+100h] [rbp+0h] BYREF
  __int64 v455; // [rsp+108h] [rbp+8h]
  __int64 v456; // [rsp+110h] [rbp+10h]
  _QWORD **v457; // [rsp+118h] [rbp+18h]
  _QWORD v458[3]; // [rsp+120h] [rbp+20h]
  __int128 v459; // [rsp+138h] [rbp+38h] BYREF
  __int128 v460; // [rsp+148h] [rbp+48h]

  v5 = *a1;
  v459 = 0;
  v448 = (__int64)v5;
  v460 = 0;
  Index = a4;
  v453 = (_QWORD *)a3;
  v8 = a1;
  v457 = a1;
  result = sqlite3GetVdbe(a1);
  v456 = result;
  v10 = result;
  if ( result )
  {
    sqlite3VdbeAddOp3(result, 166, 1, 1, 0);
    result = (__int64)*v8;
    *((_DWORD *)v8 + 14) = 2;
    if ( *(_DWORD *)(a3 + 8) )
    {
      if ( *(_BYTE *)(result + 197) )
        return sqlite3ErrorMsg(v8, "corrupt database");
      result = sqlite3FindDb(result, a2, v11);
      v447 = result;
      v12 = result;
      if ( (int)result < 0 )
        return sqlite3ErrorMsg(v8, "unknown database %T", a2);
      a2 = a3;
    }
    else
    {
      v12 = *(unsigned __int8 *)(result + 196);
      v447 = v12;
    }
    v13 = 0;
    if ( v12 >= 0 )
    {
      result = v5[4];
      v443 = result;
      if ( v12 != 1 || (result = sqlite3OpenTempDatabase(v8), !(_DWORD)result) )
      {
        if ( a2 )
        {
          v14 = (unsigned __int8 *)sqlite3DbStrNDup(v5, *(_QWORD *)a2, *(unsigned int *)(a2 + 8));
          result = sqlite3Dequote(v14);
          if ( v15 )
          {
            v435 = 32LL * v12;
            if ( a5 )
            {
              v13 = (char *)sqlite3MPrintf(v5, "-%T", Index);
              v449 = (__int64)v13;
            }
            else if ( Index )
            {
              v449 = sqlite3DbStrNDup(v5, *(_QWORD *)Index, *(unsigned int *)(Index + 8));
              v13 = (char *)v449;
              sqlite3Dequote(v449);
            }
            else
            {
              v449 = 0;
            }
            if ( *((_DWORD *)v453 + 2) )
              v16 = *(const char ***)(v443 + v435);
            else
              v16 = 0;
            v17 = (__int64)*v8;
            v441 = v16;
            v18 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(v17 + 512);
            if ( v18 && !*(_BYTE *)(v17 + 197) && !*((_BYTE *)v8 + 308) )
            {
              v19 = v18(*(_QWORD *)(v17 + 520), 19, v14, v13, v16, v8[47]);
              v433 = v19;
              if ( v19 == 1 )
              {
                sqlite3ErrorMsg(v8, "not authorized");
                v19 = 1;
                *((_DWORD *)v8 + 6) = 23;
              }
              else if ( (v19 & 0xFFFFFFFD) != 0 )
              {
                sqlite3ErrorMsg(v8, "authorizer malfunction");
                v19 = 1;
                *((_DWORD *)v8 + 6) = 1;
              }
              if ( v19 )
                goto LABEL_719;
            }
            *(_QWORD *)&v459 = 0;
            *((_QWORD *)&v459 + 1) = v14;
            v460 = (unsigned __int64)v13;
            *((_DWORD *)v5 + 166) = 0;
            if ( !(unsigned int)sqlite3SafetyCheckOk(v5) )
            {
              v20 = 21;
              sqlite3_log(
                21,
                "%s at line %d of [%.10s]",
                "misuse",
                183844,
                "96c92aba00c8375bc32fafcdf12429c58bd8aabfcadab6683e35bbb9cdebf19e");
LABEL_38:
              if ( (_QWORD)v459 )
              {
                sqlite3ErrorMsg(v8, "%s", (const char *)v459);
                sqlite3_free(v459);
              }
              ++*((_DWORD *)v8 + 12);
              *((_DWORD *)v8 + 6) = v20;
              goto LABEL_719;
            }
            v21 = v5[3];
            v433 = 1;
            sqlite3_mutex_enter(v21);
            v22 = sqlite3DbNameToBtree(v5, v441);
            v437 = (const char **)v22;
            if ( v22 )
            {
              sqlite3BtreeEnter(v22);
              v23 = *((_DWORD *)v5 + 166);
              v24 = sqlite3OsFileControl(*(_QWORD *)(*(_QWORD *)v437[1] + 72LL), 14, &v459);
              v25 = v437;
              v433 = v24;
              *((_DWORD *)v5 + 166) = v23;
              sqlite3BtreeLeave(v25);
              v12 = v447;
            }
            sqlite3_mutex_leave(v5[3]);
            if ( !v433 )
            {
              sqlite3VdbeSetNumCols(v10, 1);
              sqlite3VdbeSetColName(v10, 0, 0, v459, -1);
              returnSingleText(v10, v459);
              sqlite3_free(v459);
              goto LABEL_719;
            }
            if ( v433 != 12 )
            {
              v20 = v433;
              goto LABEL_38;
            }
            v26 = pragmaLocate(v14);
            v437 = (const char **)v26;
            v29 = v26;
            if ( !v26 )
              goto LABEL_719;
            if ( (*(_BYTE *)(v26 + 9) & 1) != 0 )
            {
              if ( (unsigned int)sqlite3ReadSchema(v8) )
                goto LABEL_719;
              v29 = (__int64)v437;
            }
            if ( (*(_BYTE *)(v29 + 9) & 2) == 0 && ((*(_BYTE *)(v29 + 9) & 4) == 0 || !v13) )
            {
              setPragmaResultColumnNames(v10, v29);
              v29 = (__int64)v437;
            }
            v30 = *(unsigned __int8 *)(v29 + 8);
            if ( v30 <= 0x16 )
            {
              if ( v30 != 22 )
              {
                if ( v30 <= 0xC )
                {
                  if ( v30 == 12 )
                  {
                    *((_DWORD *)v8 + 14) = 3;
                    for ( i = 0; (signed int)i < *((_DWORD *)v5 + 10); ++i )
                    {
                      v77 = *(_QWORD *)(32LL * (int)i + v5[4] + 8);
                      if ( v77 )
                      {
                        v78 = sqlite3PagerFilename(**(_QWORD **)(v77 + 8), 1);
                        sqlite3VdbeMultiLoad(v10, v81, "iss", i, *(_QWORD *)(v79 + v80), v78, v424, v426, v427, v428);
                      }
                    }
                    goto LABEL_719;
                  }
                  if ( v30 <= 7 )
                  {
                    if ( v30 == 7 )
                    {
                      v42 = 0;
                      if ( v13 )
                      {
                        v430 = 1;
                        Int32 = sqlite3GetInt32(v13, &v430);
                        v57 = v430;
                        if ( Int32 )
                          sqlite3BtreeSetSpillSize(*(_QWORD *)(v443 + v435 + 8), (unsigned int)v430);
                        v58 = v57 == 0;
                        v59 = v5[6];
                        LOBYTE(v56) = !v58;
                        Boolean = sqlite3GetBoolean(v13, v56);
                        v61 = v59;
                        v62 = v59 | 0x20;
                        v63 = v61 & 0xFFFFFFFFFFFFFFDFuLL;
                        if ( !Boolean )
                          v62 = v63;
                        v5[6] = v62;
                        goto LABEL_101;
                      }
                      if ( (v5[6] & 0x20) != 0 )
                        v42 = sqlite3BtreeSetSpillSize(*(_QWORD *)(v443 + v435 + 8), 0);
LABEL_547:
                      v35 = v42;
                      goto LABEL_718;
                    }
                    v31 = v30 - 1;
                    if ( !v31 )
                    {
                      Index = 0;
                      if ( v13 && !(unsigned int)sqlite3DecOrHexToI64(v13) )
                        *((_DWORD *)v5 + 186) = Index & 0x7FFFFFFF;
                      v35 = *((int *)v5 + 186);
                      goto LABEL_718;
                    }
                    v32 = v31 - 1;
                    if ( v32 )
                    {
                      v33 = v32 - 1;
                      if ( v33 )
                      {
                        v34 = v33 - 1;
                        if ( v34 )
                        {
                          if ( v34 == 2 )
                          {
                            if ( !v13 )
                            {
                              v35 = *(int *)(*(_QWORD *)(v443 + v435 + 24) + 116LL);
LABEL_718:
                              returnSingleInt(v10, v35);
                              goto LABEL_719;
                            }
                            v430 = 0;
                            sqlite3GetInt32(v13, &v430);
                            v36 = v435;
                            v37 = v443;
                            *(_DWORD *)(*(_QWORD *)(v443 + v435 + 24) + 116LL) = v430;
                            v38 = *(_QWORD *)(v37 + v36 + 24);
                            v39 = *(_QWORD *)(v37 + v36 + 8);
LABEL_242:
                            sqlite3BtreeSetCacheSize(v39, *(unsigned int *)(v38 + 116));
                            goto LABEL_719;
                          }
LABEL_613:
                          if ( v13 )
                          {
                            v429 = 0;
                            sqlite3GetInt32(v13, &v429);
                            sqlite3_busy_timeout(v5, v429);
                          }
                          v35 = *((int *)v5 + 187);
                          goto LABEL_718;
                        }
                        if ( !v13 )
                        {
                          setPragmaResultColumnNames(v10, v29);
                          v35 = (v5[6] & (unsigned __int64)v437[2]) != 0;
                          goto LABEL_718;
                        }
                        v40 = *(_QWORD *)(v29 + 16) & 0xFFFFFFFFFFFFBFFFuLL;
                        if ( *((_BYTE *)v5 + 101) )
                          v40 = *(_QWORD *)(v29 + 16);
                        if ( (unsigned __int8)sqlite3GetBoolean(v13, 0) )
                        {
                          if ( (v40 & 1) == 0 || (v5[6] & 0x10000000) == 0 )
                            v5[6] |= v40;
                        }
                        else
                        {
                          v5[6] &= ~v40;
                          if ( v40 == 0x80000 )
                          {
                            v5[96] = 0;
                          }
                          else if ( (v40 & 1) != 0 && !(unsigned int)sqlite3_stricmp(v13, "reset") )
                          {
                            sqlite3ResetAllSchemasOfConnection(v5);
                          }
                        }
                        sqlite3VdbeAddOp3(v10, 166, 0, 0, 0);
LABEL_101:
                        setAllPagerFlags(v5);
                        goto LABEL_719;
                      }
                      v41 = *(_QWORD *)(v443 + v435 + 8);
                      if ( v13 )
                      {
                        AutoVacuum = getAutoVacuum(v13);
                        *((_BYTE *)v5 + 106) = AutoVacuum;
                        if ( !(unsigned int)sqlite3BtreeSetAutoVacuum(v41, AutoVacuum) && AutoVacuum - 1 <= 1 )
                        {
                          v44 = *(_DWORD *)(v10 + 144);
                          v45 = (_DWORD *)sqlite3VdbeAddOpList(v10, 5, qword_1800B7500);
                          v46 = v447;
                          v47 = v447;
                          v45[14] = v44 + 4;
                          v45[27] = AutoVacuum - 1;
                          v45[1] = v46;
                          v45[7] = v46;
                          v45[25] = v46;
                          sqlite3VdbeUsesBtree(v10, v47);
                        }
                        goto LABEL_719;
                      }
                      v42 = sqlite3BtreeGetAutoVacuum(*(_QWORD *)(v443 + v435 + 8));
                      goto LABEL_547;
                    }
                    v48 = *(_DWORD *)(v29 + 16);
                    v429 = v48;
                    sqlite3VdbeUsesBtree(v10, (unsigned int)v12);
                    if ( v13 && (*(_BYTE *)(v50 + 9) & 8) == 0 )
                    {
                      v430 = 0;
                      v52 = sqlite3VdbeAddOpList(v49, v51, &qword_1800B61E0);
                      *(_DWORD *)(v52 + 4) = v12;
                      *(_DWORD *)(v52 + 28) = v12;
                      v53 = v429;
                      *(_DWORD *)(v52 + 32) = v429;
                      sqlite3GetInt32(v13, &v430);
                      *(_DWORD *)(v52 + 36) = v430;
                      *(_WORD *)(v52 + 26) = 1;
                      if ( v53 == 1 && (v5[6] & 0x10000000) != 0 )
                        *(_BYTE *)(v52 + 24) = -69;
                      goto LABEL_719;
                    }
                    v54 = (_DWORD *)sqlite3VdbeAddOpList(v49, 3, qword_1800B6FF8);
                    v54[1] = v12;
                    v54[7] = v12;
                    v54[9] = v48;
LABEL_88:
                    sqlite3VdbeReusable(v10);
                    goto LABEL_719;
                  }
                  v64 = v30 - 8;
                  if ( !v64 )
                  {
                    if ( v13 )
                    {
                      v75 = sqlite3GetBoolean(v13, 0);
                      sqlite3RegisterLikeFunctions(v5, v75);
                    }
                    goto LABEL_719;
                  }
                  v65 = v64 - 1;
                  if ( v65 )
                  {
                    v66 = v65 - 1;
                    if ( !v66 )
                    {
                      *((_DWORD *)v8 + 14) = 1;
                      v71 = 0;
                      v72 = sqlite3_compileoption_get(0);
                      if ( v72 )
                      {
                        do
                        {
                          ++v71;
                          sqlite3VdbeAddOp4(v10, 117, 0, 1, 0, v72, 0);
                          sqlite3VdbeAddOp3(v10, 84, 1, 1, 0);
                          v72 = sqlite3_compileoption_get(v71);
                        }
                        while ( v72 );
                        v5 = (_QWORD *)v448;
                      }
                      goto LABEL_88;
                    }
                    if ( v66 != 1 )
                      goto LABEL_613;
                    v67 = sqlite3MutexAlloc(11);
                    sqlite3_mutex_enter(v67);
                    if ( !v13 )
                    {
                      v68 = sqlite3_data_directory;
LABEL_637:
                      returnSingleText(v10, v68);
LABEL_642:
                      v372 = sqlite3MutexAlloc(11);
                      sqlite3_mutex_leave(v372);
                      goto LABEL_719;
                    }
                    if ( !*v13
                      || (v69 = *v5,
                          v430 = 0,
                          !(*(unsigned int (__fastcall **)(__int64, char *, __int64, int *))(v69 + 56))(
                             v69,
                             v13,
                             1,
                             &v430))
                      && v430 )
                    {
                      sqlite3_free(sqlite3_data_directory);
                      v70 = 0;
                      if ( *v13 )
                        v70 = sqlite3_mprintf("%s", v13);
                      sqlite3_data_directory = v70;
                      goto LABEL_642;
                    }
                    goto LABEL_641;
                  }
                  *((_DWORD *)v8 + 14) = 2;
                  v73 = (__int64 **)v5[79];
                  if ( !v73 )
                    goto LABEL_719;
                  v74 = 0;
                  do
                  {
                    sqlite3VdbeMultiLoad(v10, 1, "is", v74, *v73[2], v420, v424, v426, v427, v428);
                    v73 = (__int64 **)*v73;
                    ++v74;
                  }
                  while ( v73 );
LABEL_704:
                  v13 = (char *)v449;
                  goto LABEL_719;
                }
                v82 = v30 - 13;
                if ( !v82 )
                {
                  sqlite3VdbeUsesBtree(v10, (unsigned int)v12);
                  if ( !v13 )
                  {
                    *((_DWORD *)v8 + 14) += v156;
                    v157 = (_DWORD *)sqlite3VdbeAddOpList(v155, 9, qword_1800B6600);
                    v157[1] = v12;
                    v157[7] = v12;
                    v157[37] = -2000;
                    goto LABEL_719;
                  }
                  v430 = 0;
                  sqlite3GetInt32(v13, &v430);
                  v158 = sqlite3AbsInt32((unsigned int)v430);
                  sqlite3BeginWriteOperation(v8, 0, v447);
                  sqlite3VdbeAddOp3(v10, 100, v447, 3, v158);
                  v159 = v435;
                  v160 = v443;
                  *(_DWORD *)(*(_QWORD *)(v443 + v435 + 24) + 116LL) = v158;
                  v38 = *(_QWORD *)(v160 + v159 + 24);
                  v39 = *(_QWORD *)(v160 + v159 + 8);
                  goto LABEL_242;
                }
                v83 = v82 - 1;
                if ( v83 )
                {
                  v84 = v83 - 1;
                  if ( !v84 )
                  {
                    _mm_lfence();
                    v124 = *((_DWORD *)v8 + 14);
                    v125 = v124 + 1;
                    v124 += 5;
                    *((_DWORD *)v8 + 14) = v124;
                    v433 = v125;
                    v442 = v124;
                    v126 = *(_QWORD **)(*(_QWORD *)(v435 + v5[4] + 24) + 16LL);
                    if ( v126 )
                    {
                      v444 = v14;
                      do
                      {
                        if ( v13 )
                        {
                          Table = sqlite3LocateTable(v8, 0, v13, v441);
                          v126 = 0;
                        }
                        else
                        {
                          Table = v126[2];
                          v126 = (_QWORD *)*v126;
                        }
                        v453 = v126;
                        v435 = Table;
                        if ( Table && !*(_BYTE *)(Table + 63) && *(_QWORD *)(Table + 72) )
                        {
                          v128 = sqlite3SchemaToIndex(v5, *(_QWORD *)(Table + 96));
                          v129 = v5[4];
                          IndexKey = v128;
                          v130 = *(const char ***)(32LL * v128 + v129);
                          v441 = v130;
                          sqlite3CodeVerifySchema(v8, (unsigned int)v128);
                          sqlite3TableLock((_DWORD)v8, IndexKey, *(_DWORD *)(v435 + 40), 0, *(_QWORD *)v435);
                          v131 = v435;
                          v132 = v442 + *(__int16 *)(v435 + 54);
                          if ( *((_DWORD *)v8 + 14) < v132 )
                            *((_DWORD *)v8 + 14) = v132;
                          sqlite3OpenTable((_DWORD)v8, 0, IndexKey, v131, 112);
                          sqlite3VdbeAddOp4(v10, 117, 0, v433, 0, *(_QWORD *)v435, 0);
                          v133 = 1;
                          for ( j = *(_QWORD *)(v435 + 72); ; j = *(_QWORD *)(Index + 8) )
                          {
                            Index = j;
                            v432 = v133;
                            if ( !j )
                              break;
                            v135 = sqlite3FindTable(v5, *(_QWORD *)(j + 16), v130);
                            v437 = (const char **)v135;
                            if ( v135 )
                            {
                              v136 = *(_DWORD *)(v135 + 40);
                              v417 = *(_QWORD *)v135;
                              v443 = 0;
                              sqlite3TableLock((_DWORD)v8, IndexKey, v136, 0, v417);
                              if ( (unsigned int)sqlite3FkLocateIndex(
                                                   (_DWORD)v8,
                                                   (_DWORD)v437,
                                                   Index,
                                                   (unsigned int)&v443,
                                                   0) )
                                goto LABEL_719;
                              if ( v443 )
                              {
                                sqlite3VdbeAddOp3(v10, 112, v432, *(_DWORD *)(v443 + 88), IndexKey);
                                sqlite3VdbeSetP4KeyInfo(v8, v443);
                              }
                              else
                              {
                                sqlite3OpenTable((_DWORD)v8, v432, IndexKey, (_DWORD)v437, 112);
                              }
                            }
                            v133 = v432 + 1;
                          }
                          if ( *((_DWORD *)v8 + 13) < v133 )
                            *((_DWORD *)v8 + 13) = v133;
                          LODWORD(v452) = sqlite3VdbeAddOp3(v10, 36, 0, 0, 0);
                          IndexKey = 1;
                          v455 = *(_QWORD *)(v435 + 72);
                          if ( v455 )
                          {
                            v137 = v435;
                            v138 = v442;
                            v438 = v433 + 2;
                            v445 = v433 + 1;
                            do
                            {
                              v139 = v130;
                              v140 = v455;
                              v141 = sqlite3FindTable(v5, *(_QWORD *)(v455 + 16), v139);
                              v434 = v141;
                              v443 = 0;
                              v142 = 0;
                              v437 = 0;
                              if ( v141 )
                              {
                                sqlite3FkLocateIndex((_DWORD)v8, v141, v140, (unsigned int)&v443, (__int64)&v437);
                                v142 = v437;
                              }
                              v143 = *((_DWORD *)v8 + 17) - 1;
                              *((_DWORD *)v8 + 17) = v143;
                              v144 = v138 + *(_DWORD *)(v140 + 40);
                              v432 = v143;
                              if ( *((_DWORD *)v8 + 14) < v144 )
                                *((_DWORD *)v8 + 14) = v144;
                              v430 = *(_DWORD *)(v140 + 40);
                              if ( v430 > 0 )
                              {
                                v145 = v442;
                                for ( k = 0; k < v430; ++k )
                                {
                                  if ( v142 )
                                    v147 = *((_DWORD *)v142 + k);
                                  else
                                    v147 = *(_DWORD *)(v140 + 16 * (k + 4LL));
                                  sqlite3ExprCodeGetColumnOfTable(v10, v137, 0, v147, k + v145);
                                  sqlite3VdbeAddOp3(v10, 50, k + v145, v432, 0);
                                  v140 = v455;
                                  v142 = v437;
                                  v430 = *(_DWORD *)(v455 + 40);
                                }
                                v5 = (_QWORD *)v448;
                                v8 = v457;
                                v138 = v442;
                              }
                              if ( v443 )
                              {
                                v148 = *(_DWORD *)(v140 + 40);
                                v149 = sqlite3IndexAffinityStr(v5, v443);
                                sqlite3VdbeAddOp4(v10, 96, v138, v148, 0, v149, v430);
                                v140 = v455;
                                sqlite3VdbeAddOp4Int(v10, 29, IndexKey, v432, v138, *(_DWORD *)(v455 + 40));
                              }
                              else if ( v434 )
                              {
                                sqlite3VdbeAddOp3(v10, 30, IndexKey, *(_DWORD *)(v10 + 144) + 2, v138);
                                sqlite3VdbeAddOp3(v10, 9, 0, v432, 0);
                              }
                              sqlite3VdbeAddOp3(v10, (*(_DWORD *)(v137 + 48) & 0x80u) != 0 ? 75 : 135, 0, v445, 0);
                              LODWORD(v418) = IndexKey - 1;
                              sqlite3VdbeMultiLoad(
                                v10,
                                v438,
                                "siX",
                                *(_QWORD *)(v140 + 16),
                                v418,
                                v422,
                                v425,
                                v426,
                                v427,
                                v428);
                              sqlite3VdbeAddOp3(v10, 84, v433, 4, 0);
                              sqlite3VdbeResolveLabel(v10, v432);
                              sqlite3DbFree(v5, v437);
                              v150 = *(_QWORD *)(v140 + 8);
                              ++IndexKey;
                              v58 = v150 == 0;
                              v455 = v150;
                              v130 = v441;
                            }
                            while ( !v58 );
                            v14 = v444;
                            v13 = (char *)v449;
                          }
                          v151 = (unsigned int)v452;
                          sqlite3VdbeAddOp3(v10, 39, 0, (_DWORD)v452 + 1, 0);
                          *(_DWORD *)(sqlite3VdbeGetOp(v10, v151) + 8) = *(_DWORD *)(v10 + 144);
                          v126 = v453;
                        }
                      }
                      while ( v126 );
                    }
                    goto LABEL_719;
                  }
                  v85 = v84 - 1;
                  if ( !v85 )
                  {
                    if ( !v13 )
                      goto LABEL_719;
                    v110 = sqlite3FindTable(v5, v13, v441);
                    v434 = v110;
                    if ( !v110 )
                      goto LABEL_719;
                    if ( *(_BYTE *)(v110 + 63) )
                      goto LABEL_719;
                    v111 = *(_QWORD *)(v110 + 72);
                    if ( !v111 )
                      goto LABEL_719;
                    v112 = sqlite3SchemaToIndex(v5, *(_QWORD *)(v110 + 96));
                    v432 = v113;
                    *((_DWORD *)v8 + 14) = 8;
                    sqlite3CodeVerifySchema(v8, v112);
                    v115 = v432;
                    v116 = 0;
                    do
                    {
                      v117 = 0;
                      if ( *(int *)(v111 + 40) > 0 )
                      {
                        do
                        {
                          LOBYTE(v116) = *(_BYTE *)(v111 + 45);
                          actionName(v116, v114, v117);
                          LOBYTE(v118) = *(_BYTE *)(v111 + 46);
                          v121 = actionName(v118, v119, v120);
                          LODWORD(v416) = v117;
                          sqlite3VdbeMultiLoad(
                            v10,
                            1,
                            "iissssss",
                            v432,
                            v416,
                            *(_QWORD *)(v111 + 16),
                            *(_QWORD *)(*(_QWORD *)(v434 + 8) + 24LL * *(int *)(v111 + 16 * (v122 + 4))),
                            *(_QWORD *)(v111 + 16 * v122 + 72),
                            v121,
                            v123);
                          ++v117;
                        }
                        while ( v117 < *(_DWORD *)(v111 + 40) );
                        v115 = v432;
                        v116 = 0;
                      }
                      v111 = *(_QWORD *)(v111 + 8);
                      v432 = ++v115;
                    }
                    while ( v111 );
                    goto LABEL_703;
                  }
                  v86 = v85 - 1;
                  if ( !v86 )
                  {
                    v106 = (*((_DWORD *)v5 + 11) >> 5) & 1;
                    *((_DWORD *)v8 + 14) = 6;
                    v107 = 0;
                    Index = 0;
                    do
                    {
                      v108 = qword_1800C75C0[v107];
                      if ( v108 )
                      {
                        do
                        {
                          pragmaFunclistLine(v10, v108, 1, v106);
                          v108 = *(_QWORD *)(v108 + 64);
                        }
                        while ( v108 );
                        v107 = Index;
                      }
                      Index = ++v107;
                    }
                    while ( v107 != 23 );
                    v109 = (_QWORD *)v5[76];
                    v13 = (char *)v449;
                    while ( v109 )
                    {
                      pragmaFunclistLine(v10, v109[2], 0, v106);
                      v109 = (_QWORD *)*v109;
                    }
                    goto LABEL_719;
                  }
                  v87 = v86 - 1;
                  if ( v87 )
                  {
                    v88 = v87 - 1;
                    if ( !v88 )
                    {
                      v430 = 0;
                      if ( !v13 || !(unsigned int)sqlite3GetInt32(v13, &v430) || v430 <= 0 )
                        v430 = 0x7FFFFFFF;
                      sqlite3BeginWriteOperation(v8, 0, (unsigned int)v12);
                      sqlite3VdbeAddOp3(v10, 71, v430, 1, 0);
                      v104 = sqlite3VdbeAddOp3(v10, 62, v12, 0, 0);
                      sqlite3VdbeAddOp3(v10, 84, 1, 0, 0);
                      sqlite3VdbeAddOp3(v10, 86, 1, -1, 0);
                      sqlite3VdbeAddOp3(v10, 59, 1, v104, 0);
                      *(_DWORD *)(sqlite3VdbeGetOp(v10, v104) + 8) = *(_DWORD *)(v10 + 144);
                      goto LABEL_719;
                    }
                    v89 = v88 - 1;
                    if ( v89 )
                    {
                      if ( v89 != 1 )
                        goto LABEL_613;
                      if ( !v13 )
                        goto LABEL_719;
                      v90 = sqlite3FindTable(v5, v13, v441);
                      v91 = v90;
                      if ( !v90 )
                        goto LABEL_719;
                      v92 = sqlite3SchemaToIndex(v5, *(_QWORD *)(v90 + 96));
                      *((_DWORD *)v8 + 14) = 5;
                      sqlite3CodeVerifySchema(v8, v92);
                      v93 = *(_QWORD *)(v91 + 16);
                      v94 = 0;
                      if ( !v93 )
                        goto LABEL_719;
                      do
                      {
                        v58 = *(_QWORD *)(v93 + 72) == 0;
                        v458[0] = "c";
                        v458[1] = "u";
                        LODWORD(v426) = !v58;
                        v458[2] = "pk";
                        LODWORD(v420) = *(_BYTE *)(v93 + 98) != 0;
                        sqlite3VdbeMultiLoad(
                          v10,
                          1,
                          "isisi",
                          v94,
                          *(_QWORD *)v93,
                          v420,
                          v458[*(_DWORD *)(v93 + 100) & 3],
                          v426,
                          v427,
                          v428);
                        v93 = *(_QWORD *)(v93 + 40);
                        ++v94;
                      }
                      while ( v93 );
                      goto LABEL_704;
                    }
                    if ( !v13 )
                      goto LABEL_719;
                    Index = sqlite3FindIndex(v5, v13, v441);
                    v95 = Index;
                    if ( !Index )
                    {
                      v96 = sqlite3LocateTable(v8, 2, v13, v441);
                      if ( !v96 )
                        goto LABEL_719;
                      if ( *(char *)(v96 + 48) >= 0 )
                        goto LABEL_719;
                      Index = sqlite3PrimaryKeyIndex(v96);
                      v95 = Index;
                      if ( !Index )
                        goto LABEL_719;
                    }
                    v97 = sqlite3SchemaToIndex(v5, *(_QWORD *)(v95 + 48));
                    v98 = v437;
                    v99 = v437[2] != 0;
                    v430 = *(unsigned __int16 *)((v99 ? 2 : 0) + v100 + 94);
                    *((_DWORD *)v8 + 14) = v99 ? 6 : 3;
                    v434 = *(_QWORD *)(v100 + 24);
                    sqlite3CodeVerifySchema(v8, v97);
                    if ( !v430 )
                      goto LABEL_719;
                    v101 = 0;
                    v444 = v14;
                    do
                    {
                      v102 = *(__int16 *)(*(_QWORD *)(Index + 8) + 2LL * v101);
                      if ( (v102 & 0x8000u) == 0LL )
                        v103 = *(_QWORD *)(*(_QWORD *)(v434 + 8) + 24 * v102);
                      else
                        v103 = 0;
                      LODWORD(v416) = *(__int16 *)(*(_QWORD *)(Index + 8) + 2LL * v101);
                      sqlite3VdbeMultiLoad(v10, 1, "iisX", v101, v416, v103, v424, v426, v427, v428);
                      if ( v98[2] )
                      {
                        LODWORD(v421) = v101 < *(unsigned __int16 *)(Index + 94);
                        sqlite3VdbeMultiLoad(
                          v10,
                          4,
                          "isiX",
                          *(unsigned __int8 *)(*(_QWORD *)(Index + 56) + v101),
                          *(_QWORD *)(*(_QWORD *)(Index + 64) + 8LL * v101),
                          v421,
                          v424,
                          v426,
                          v427,
                          v428);
                      }
                      sqlite3VdbeAddOp3(v10, 84, 1, *((_DWORD *)v8 + 14), 0);
                      ++v101;
                    }
                    while ( (int)v101 < v430 );
                    goto LABEL_702;
                  }
                  Index = 0;
                  if ( v13 && !(unsigned int)sqlite3DecOrHexToI64(v13) )
                    sqlite3_hard_heap_limit64(-1);
                  v105 = sqlite3_hard_heap_limit64(-1);
LABEL_717:
                  v35 = v105;
                  goto LABEL_718;
                }
                if ( v13 )
                {
                  if ( (*((_BYTE *)v5 + 44) & 0x40) == 0 )
                  {
                    for ( m = &off_1800AB640; *m; m += 2 )
                    {
                      if ( !(unsigned int)sqlite3StrICmp(v13, *m) )
                      {
                        v154 = 2;
                        if ( *((_BYTE *)m + 8) )
                          v154 = *((_BYTE *)m + 8);
                        *(_BYTE *)(*(_QWORD *)(v5[4] + 24LL) + 113LL) = v154;
                        sqlite3SetTextEncoding(v5);
                        break;
                      }
                    }
                    if ( !*m )
                      sqlite3ErrorMsg(v8, "unsupported encoding: %s", v13);
                  }
                  goto LABEL_719;
                }
                if ( !(unsigned int)sqlite3ReadSchema(v8) )
                {
                  v152 = (&off_1800AB640)[2 * *((unsigned __int8 *)*v8 + 100)];
LABEL_498:
                  returnSingleText(v10, v152);
                }
LABEL_719:
                result = sqlite3DbFreeNN(v5, v14);
                if ( v13 )
                  return sqlite3DbFreeNN(v5, v13);
                return result;
              }
              v161 = *v14;
              v435 = 0;
              v439 = *((_BYTE *)qword_1800ADCF0 + v161);
              LODWORD(v443) = v439 == 113;
              v58 = *v453 == 0;
              *((_DWORD *)v8 + 14) = 6;
              if ( v58 )
                v12 = -1;
              v162 = 100;
              v433 = 100;
              v432 = 100;
              v447 = v12;
              if ( v13 )
              {
                if ( (unsigned int)sqlite3GetInt32(*(_QWORD *)Index, &v432) )
                {
                  v162 = v432;
                  v433 = v432;
                  if ( (int)v432 > 0 )
                    goto LABEL_254;
                  v162 = 100;
                }
                else
                {
                  if ( v12 < 0 )
                    v163 = 0;
                  else
                    v163 = *(_QWORD *)(32LL * v12 + v5[4]);
                  v435 = sqlite3LocateTable(v8, 0, v13, v163);
                  v162 = v432;
                }
                v433 = v162;
              }
LABEL_254:
              sqlite3VdbeAddOp3(v10, 71, v162 - 1, 1, 0);
              v164 = 0;
              v451 = 0;
              if ( *((int *)v5 + 10) > 0 )
              {
                v444 = v14;
                do
                {
                  if ( v12 < 0 || v164 == v12 )
                  {
                    sqlite3CodeVerifySchema(v8, v164);
                    v165 = 32LL * v451;
                    *((_BYTE *)v8 + 35) = 0;
                    v166 = v5[4];
                    v434 = v165;
                    v167 = *(_QWORD *)(v165 + v166 + 24);
                    v168 = 0;
                    Index = v167;
                    v169 = *(_QWORD **)(v167 + 16);
                    if ( v169 )
                    {
                      do
                      {
                        v170 = v169[2];
                        if ( !v435 || v435 == v170 )
                        {
                          if ( *(char *)(v170 + 48) >= 0 )
                            ++v168;
                          v171 = *(_QWORD *)(v170 + 16);
                          while ( v171 )
                          {
                            v171 = *(_QWORD *)(v171 + 40);
                            ++v168;
                          }
                        }
                        v169 = (_QWORD *)*v169;
                      }
                      while ( v169 );
                      if ( v168 )
                      {
                        v172 = v168 + 1;
                        if ( !v435 )
                          v172 = v168;
                        v173 = (int *)sqlite3DbMallocRawNN(v5, 4LL * v172 + 4);
                        if ( !v173 )
                          break;
                        v174 = 0;
                        if ( v435 )
                        {
                          v174 = 1;
                          v173[1] = 0;
                        }
                        v175 = *(_QWORD **)(Index + 16);
                        if ( v175 )
                        {
                          v176 = v435;
                          do
                          {
                            v177 = v175[2];
                            if ( !v176 || v176 == v177 )
                            {
                              if ( *(char *)(v177 + 48) >= 0 )
                              {
                                v178 = v174++;
                                v173[v178 + 1] = *(_DWORD *)(v177 + 40);
                              }
                              for ( n = *(_QWORD *)(v177 + 16); n; n = *(_QWORD *)(n + 40) )
                                v173[++v174] = *(_DWORD *)(n + 88);
                            }
                            v175 = (_QWORD *)*v175;
                          }
                          while ( v175 );
                          v13 = (char *)v449;
                        }
                        *v173 = v174;
                        if ( *((_DWORD *)v8 + 14) < v174 + 8 )
                          *((_DWORD *)v8 + 14) = v174 + 8;
                        *((_BYTE *)v8 + 31) = 0;
                        *((_DWORD *)v8 + 10) = 0;
                        sqlite3VdbeAddOp4(v10, 155, 1, v174, 8, (__int64)v173, -14);
                        sqlite3VdbeChangeP5(v10, (unsigned __int8)v451);
                        v181 = sqlite3VdbeAddOp3(v180, 50, 2, 0, 0);
                        v182 = sqlite3MPrintf(v5, "*** in database %s ***\n", *(const char **)(v5[4] + v434));
                        sqlite3VdbeAddOp4(v10, 117, 0, 3, 0, v182, -6);
                        sqlite3VdbeAddOp3(v10, 111, 2, 3, 3);
                        integrityCheckResultRow(v10);
                        *(_DWORD *)(sqlite3VdbeGetOp(v10, v181) + 8) = *(_DWORD *)(v10 + 144);
                        sqlite3VdbeAddOp4(v10, 117, 0, 2, 0, (__int64)"wrong # of entries in index ", 0);
                        v183 = 0;
                        if ( *(_QWORD *)(Index + 16) )
                        {
                          v184 = v435;
                          v185 = *(_QWORD **)(Index + 16);
                          v186 = v435 != 0;
                          do
                          {
                            v187 = v185[2];
                            if ( !v184 || v184 == v187 )
                            {
                              v58 = *(_BYTE *)(v187 + 48) >= 0;
                              v188 = v186;
                              v432 = v186;
                              if ( v58 )
                              {
                                ++v186;
                                v189 = (const char ***)(v187 + 16);
                              }
                              else
                              {
                                v190 = *(_QWORD *)(v187 + 16);
                                if ( v190 )
                                {
                                  do
                                  {
                                    v189 = (const char ***)(v187 + 16);
                                    if ( (*(_DWORD *)(v190 + 100) & 3) == 2 )
                                      break;
                                    v190 = *(_QWORD *)(v190 + 40);
                                    v432 = ++v188;
                                  }
                                  while ( v190 );
                                }
                                else
                                {
                                  v189 = (const char ***)(v187 + 16);
                                }
                              }
                              v191 = *v189;
                              v437 = v191;
                              if ( v191 )
                              {
                                v192 = v186 + 8;
                                do
                                {
                                  if ( !v191[9] )
                                  {
                                    v193 = sqlite3VdbeAddOp3(v10, 53, v192, 0, v188 + 8);
                                    sqlite3VdbeAddOp4(v10, 117, 0, 4, 0, (__int64)*v437, 0);
                                    sqlite3VdbeAddOp3(v10, 111, 4, 2, 3);
                                    integrityCheckResultRow(v10);
                                    Op = sqlite3VdbeGetOp(v10, v193);
                                    v183 = 0;
                                    *(_DWORD *)(Op + 8) = *(_DWORD *)(v10 + 144);
                                    v191 = v437;
                                  }
                                  v191 = (const char **)v191[5];
                                  ++v186;
                                  v188 = v432;
                                  ++v192;
                                  v437 = v191;
                                }
                                while ( v191 );
                                v184 = v435;
                              }
                            }
                            v185 = (_QWORD *)*v185;
                          }
                          while ( v185 );
                          v14 = v444;
                          v5 = (_QWORD *)v448;
                          v8 = v457;
                          v13 = (char *)v449;
                        }
                        v195 = Index;
                        v196 = *(_QWORD *)(Index + 16);
                        v434 = v196;
                        if ( v196 )
                        {
                          v197 = v435;
                          do
                          {
                            v198 = *(const char ***)(v196 + 16);
                            v441 = v198;
                            v446 = v183;
                            v442 = v183;
                            if ( (!v197 || (const char **)v197 == v198) && *((_BYTE *)v198 + 63) == (_BYTE)v183 )
                            {
                              if ( v439 == 113 || *((char *)v198 + 48) >= 0 )
                              {
                                v455 = v183;
                                v432 = v183;
                              }
                              else
                              {
                                v455 = sqlite3PrimaryKeyIndex(v198);
                                TempRange = sqlite3GetTempRange(v8, *(unsigned __int16 *)(v455 + 94));
                                v201 = *(unsigned __int16 *)(v200 + 94) - 1;
                                v432 = TempRange;
                                sqlite3VdbeAddOp3(v10, 75, 1, TempRange, TempRange + v201);
                                v183 = 0;
                              }
                              sqlite3OpenTableAndIndices(
                                (_DWORD)v8,
                                (_DWORD)v198,
                                112,
                                0,
                                1,
                                v183,
                                (__int64)&v446,
                                (__int64)&v442);
                              sqlite3VdbeAddOp3(v10, 71, 0, 7, 0);
                              if ( v198[2] )
                              {
                                v202 = 8;
                                v203 = v198[2];
                                do
                                {
                                  sqlite3VdbeAddOp3(v10, 71, 0, v202, 0);
                                  v203 = (const char *)*((_QWORD *)v203 + 5);
                                  ++v202;
                                }
                                while ( v203 );
                                v5 = (_QWORD *)v448;
                                v8 = v457;
                                v198 = v441;
                              }
                              sqlite3VdbeAddOp3(v10, 36, v446, 0, 0);
                              v204 = sqlite3VdbeAddOp3(v10, 86, 7, 1, 0);
                              v58 = *((_BYTE *)v198 + 48) >= 0;
                              LODWORD(v453) = v204;
                              if ( v58 )
                              {
                                v205 = *((__int16 *)v198 + 27);
                                v206 = -1;
                                if ( v205 > 0 )
                                {
                                  for ( ii = 0; ii < v205; ++ii )
                                  {
                                    v208 = v206 + 1;
                                    if ( (v198[1][24 * ii + 18] & 0x20) != 0 )
                                      v208 = v206;
                                    v206 = v208;
                                  }
                                }
                                v209 = v206 - 1;
                                if ( v206 != *((__int16 *)v198 + 26) )
                                  v209 = v206;
                              }
                              else
                              {
                                v209 = *(unsigned __int16 *)(sqlite3PrimaryKeyIndex(v198) + 96) - 1;
                              }
                              if ( v209 >= 0 )
                              {
                                sqlite3VdbeAddOp3(v10, 94, v446, v209, 3);
                                sqlite3VdbeTypeofColumn(v10, 3);
                              }
                              if ( v439 != 113 && v455 )
                              {
                                v210 = sqlite3VdbeAddOp4Int(v10, 41, v446, 0, v432, *(unsigned __int16 *)(v455 + 94));
                                sqlite3VdbeAddOp3(v10, 50, v432, 0, 0);
                                v211 = sqlite3MPrintf(v5, "row not in PRIMARY KEY order for %s", *v441);
                                sqlite3VdbeAddOp4(v10, 117, 0, 3, 0, v211, -6);
                                integrityCheckResultRow(v10);
                                *(_DWORD *)(sqlite3VdbeGetOp(v10, v210) + 8) = *(_DWORD *)(v10 + 144);
                                v212 = sqlite3VdbeGetOp(v10, v210 + 1);
                                v213 = 0;
                                *(_DWORD *)(v212 + 8) = *(_DWORD *)(v10 + 144);
                                if ( *(_WORD *)(v455 + 94) )
                                {
                                  v214 = v446;
                                  v215 = v455;
                                  v216 = v432;
                                  do
                                  {
                                    sqlite3ExprCodeLoadIndexColumn((_DWORD)v8, v215, v214, v213, v216 + v213);
                                    ++v213;
                                  }
                                  while ( v213 < *(unsigned __int16 *)(v215 + 94) );
                                  v14 = v444;
                                  v10 = v456;
                                  v5 = (_QWORD *)v448;
                                  v198 = v441;
                                }
                                else
                                {
                                  v198 = v441;
                                }
                              }
                              v217 = 0;
                              v218 = (_DWORD)v198[6] & 0x10000;
                              v450 = 0;
                              v430 = v218;
                              if ( *((__int16 *)v198 + 27) > 0 )
                              {
                                while ( (_DWORD)v217 == *((__int16 *)v198 + 26) )
                                {
LABEL_376:
                                  v244 = *((__int16 *)v198 + 27);
                                  v217 = (unsigned int)(v217 + 1);
                                  v450 = v217;
                                  if ( (int)v217 >= v244 )
                                  {
                                    v444 = v14;
                                    goto LABEL_378;
                                  }
                                }
                                v219 = (__int64)&v198[1][24 * (int)v217];
                                v437 = (const char **)v219;
                                if ( v218 )
                                {
                                  v220 = (*(_DWORD *)(v219 + 8) & 0xF0u) > 0x10;
                                  LODWORD(v452) = v220;
                                }
                                else if ( *(char *)(v219 + 12) <= 65 )
                                {
                                  v220 = 0;
                                  LODWORD(v452) = 0;
                                }
                                else
                                {
                                  v220 = 1;
                                  LODWORD(v452) = 1;
                                }
                                if ( (*(_BYTE *)(v219 + 8) & 0xF) != 0 || v220 )
                                {
                                  v58 = (*(_BYTE *)(v219 + 18) & 0x20) == 0;
                                  IndexKey = 5;
                                  if ( v58 )
                                  {
                                    if ( *(_WORD *)(v219 + 16) )
                                    {
                                      v454 = 0;
                                      v223 = sqlite3ColumnExpr(v198, v219);
                                      LOBYTE(v224) = *v224;
                                      LOBYTE(v225) = *((_BYTE *)v5 + 100);
                                      sqlite3ValueFromExpr((_DWORD)v5, v223, v225, (_DWORD)v224, (__int64)&v454);
                                      if ( v454 )
                                      {
                                        IndexKey = *((unsigned __int8 *)qword_1800B9DC0 + (*(_WORD *)(v454 + 20) & 0x3F));
                                        sqlite3ValueFree();
                                      }
                                      v217 = v450;
                                    }
                                    v58 = *((_BYTE *)v198 + 48) >= 0;
                                    v440 = v446;
                                    if ( v58 )
                                    {
                                      v229 = sqlite3TableColumnToStorage(v198, v217);
                                      v221 = v440;
                                    }
                                    else
                                    {
                                      v226 = sqlite3PrimaryKeyIndex(v198);
                                      v229 = sqlite3TableColumnToIndex(v226, v227, v228);
                                    }
                                    v222 = v229;
                                    LODWORD(v444) = v229;
                                  }
                                  else
                                  {
                                    sqlite3ExprCodeGetColumnOfTable(v10, (_DWORD)v441, v446, v217, 3);
                                    v221 = -1;
                                    v440 = -1;
                                    v222 = 3;
                                    LODWORD(v444) = 3;
                                  }
                                  v429 = *((_DWORD *)v8 + 17) - 1;
                                  v230 = v429 - 1;
                                  v231 = v437;
                                  *((_DWORD *)v8 + 17) = v429 - 1;
                                  v438 = v230;
                                  if ( ((_BYTE)v231[1] & 0xF) != 0 )
                                  {
                                    LODWORD(v454) = sqlite3VdbeAddOp4Int(v10, 18, v221, v230, v222, IndexKey);
                                    if ( v440 >= 0 )
                                    {
                                      sqlite3VdbeChangeP5(v10, 13);
                                      sqlite3VdbeAddOp3(v233, 94, v234, (_DWORD)v444, 3);
                                      sqlite3ColumnDefault(v10, v441, v450, 3);
                                      v445 = sqlite3VdbeAddOp3(v10, 51, 3, v438, 0);
                                    }
                                    else
                                    {
                                      sqlite3VdbeChangeP5(v10, 15);
                                      v445 = v232;
                                    }
                                    v235 = sqlite3MPrintf(v5, "NULL value in %s.%s", *v441, *v437);
                                    sqlite3VdbeAddOp4(v10, 117, 0, 3, 0, v235, -6);
                                    v236 = (int)v452;
                                    if ( (_DWORD)v452 )
                                    {
                                      sqlite3VdbeAddOp3(v10, 9, 0, v429, 0);
                                      v237 = sqlite3VdbeGetOp(v10, (unsigned int)v454);
                                      v238 = v445;
                                      *(_DWORD *)(v237 + 8) = *(_DWORD *)(v10 + 144);
                                      *(_DWORD *)(sqlite3VdbeGetOp(v10, v238) + 8) = *(_DWORD *)(v10 + 144);
                                      v231 = v437;
                                      v230 = v438;
                                      goto LABEL_362;
                                    }
                                    v231 = v437;
                                    v230 = v438;
                                  }
                                  else
                                  {
LABEL_362:
                                    v236 = (int)v452;
                                  }
                                  if ( v430 )
                                  {
                                    if ( v236 )
                                    {
                                      sqlite3VdbeAddOp4Int(v10, 18, v440, v230, (_DWORD)v444, IndexKey);
                                      sqlite3VdbeChangeP5(
                                        v10,
                                        *((unsigned __int8 *)&qword_1800B7588[1]
                                        + ((*((_DWORD *)v437 + 2) >> 4) & 0xFu)
                                        + 7));
                                      v241 = sqlite3MPrintf(
                                               v5,
                                               "non-%s value in %s.%s",
                                               *(const char **)(v240
                                                              + 8LL * (((*(_DWORD *)(v239 + 8) >> 4) & 0xFu) - 1)
                                                              + 812560),
                                               *v441,
                                               *(const char **)&v441[1][24 * v450]);
                                      goto LABEL_373;
                                    }
                                  }
                                  else
                                  {
                                    v242 = *((_BYTE *)v231 + 12);
                                    if ( v242 == 66 )
                                    {
                                      sqlite3VdbeAddOp4Int(v10, 18, v440, v230, (_DWORD)v444, IndexKey);
                                      sqlite3VdbeChangeP5(v10, 28);
                                      v241 = sqlite3MPrintf(
                                               v5,
                                               "NUMERIC value in %s.%s",
                                               *v441,
                                               *(_QWORD *)&v441[1][24 * v450]);
                                    }
                                    else
                                    {
                                      if ( v242 < 67 )
                                        goto LABEL_374;
                                      sqlite3VdbeAddOp4Int(v10, 18, v440, v230, (_DWORD)v444, IndexKey);
                                      sqlite3VdbeChangeP5(v10, 27);
                                      if ( v440 >= 0 )
                                        sqlite3ExprCodeGetColumnOfTable(v243, (_DWORD)v441, v446, v450, 3);
                                      sqlite3VdbeAddOp4(v10, 96, 3, 1, 0, (__int64)"C", -1);
                                      sqlite3VdbeAddOp4Int(v10, 18, -1, v438, 3, IndexKey);
                                      sqlite3VdbeChangeP5(v10, 28);
                                      v241 = sqlite3MPrintf(
                                               v5,
                                               "TEXT value in %s.%s",
                                               *v441,
                                               *(_QWORD *)&v441[1][24 * v450]);
                                    }
LABEL_373:
                                    sqlite3VdbeAddOp4(v10, 117, 0, 3, 0, v241, -6);
                                  }
LABEL_374:
                                  sqlite3VdbeResolveLabel(v10, v429);
                                  integrityCheckResultRow(v10);
                                  sqlite3VdbeResolveLabel(v10, v438);
                                  LODWORD(v217) = v450;
                                  v198 = v441;
                                }
                                v218 = v430;
                                goto LABEL_376;
                              }
LABEL_378:
                              v245 = v198[4];
                              if ( v245 && (v5[6] & 0x200LL) == 0 )
                              {
                                v246 = (const char **)sqlite3ExprListDup(v5, v245, 0);
                                v437 = v246;
                                v247 = v246;
                                if ( !*((_BYTE *)v5 + 103) )
                                {
                                  v429 = *((_DWORD *)v8 + 17) - 1;
                                  v445 = v429 - 1;
                                  *((_DWORD *)v8 + 17) = v429 - 1;
                                  *((_DWORD *)v8 + 16) = v446 + 1;
                                  v248 = *(_DWORD *)v246 - 1;
                                  if ( *(_DWORD *)v247 - 1 > 0 )
                                  {
                                    v249 = v429;
                                    v250 = v248;
                                    v251 = v247;
                                    do
                                      sqlite3ExprIfFalse(v8, v251[4 * (unsigned int)v250-- + 1], v249, 0);
                                    while ( v250 > 0 );
                                    v14 = v444;
                                    v10 = v456;
                                    v5 = (_QWORD *)v448;
                                    v198 = v441;
                                    v247 = v437;
                                  }
                                  sqlite3ExprIfTrue(v8, v247[1], v445, 16);
                                  sqlite3VdbeResolveLabel(v10, v429);
                                  *((_DWORD *)v8 + 16) = 0;
                                  v252 = sqlite3MPrintf(v5, "CHECK constraint failed in %s", *v198);
                                  sqlite3VdbeAddOp4(v10, 117, 0, 3, 0, v252, -6);
                                  integrityCheckResultRow(v10);
                                  sqlite3VdbeResolveLabel(v10, v445);
                                  v247 = v437;
                                }
                                sqlite3ExprListDeleteGeneric(v5, v247);
                              }
                              if ( v439 != 113 )
                              {
                                v253 = (char *)v198[2];
                                v254 = 0;
                                v440 = 0;
                                v255 = 0;
                                v452 = v253;
                                v256 = -1;
                                if ( v253 )
                                {
                                  v257 = v441;
                                  do
                                  {
                                    v258 = *((_DWORD *)v8 + 17) - 1;
                                    v429 = 0;
                                    *((_DWORD *)v8 + 17) = v258;
                                    if ( (char *)v455 != v253 )
                                    {
                                      IndexKey = sqlite3GenerateIndexKey(
                                                   (_DWORD)v8,
                                                   (_DWORD)v253,
                                                   v446,
                                                   0,
                                                   0,
                                                   (__int64)&v429,
                                                   v255,
                                                   v256);
                                      v437 = (const char **)v253;
                                      sqlite3VdbeAddOp3(v10, 86, v440 + 8, 1, 0);
                                      v423 = *((unsigned __int16 *)v253 + 48);
                                      LODWORD(v454) = v442 + v440;
                                      v259 = sqlite3VdbeAddOp4Int(v10, 29, v442 + v440, v258, IndexKey, v423);
                                      sqlite3VdbeAddOp4(v10, 117, 0, 3, 0, (__int64)"row ", 0);
                                      sqlite3VdbeAddOp3(v10, 111, 7, 3, 3);
                                      sqlite3VdbeAddOp4(v10, 117, 0, 4, 0, (__int64)" missing from index ", 0);
                                      sqlite3VdbeAddOp3(v10, 111, 4, 3, 3);
                                      v430 = sqlite3VdbeAddOp4(v10, 117, 0, 4, 0, *(_QWORD *)v452, 0);
                                      sqlite3VdbeAddOp3(v10, 111, 4, 3, 3);
                                      v445 = integrityCheckResultRow(v10);
                                      *(_DWORD *)(sqlite3VdbeGetOp(v10, v259) + 8) = *(_DWORD *)(v10 + 144);
                                      if ( *((char *)v257 + 48) < 0 )
                                      {
                                        v260 = IndexKey;
                                      }
                                      else
                                      {
                                        sqlite3VdbeAddOp3(v10, 142, v454, 3, 0);
                                        v260 = IndexKey;
                                        v261 = sqlite3VdbeAddOp3(
                                                 v10,
                                                 53,
                                                 3,
                                                 0,
                                                 (unsigned int)*((unsigned __int16 *)v452 + 48) + IndexKey - 1);
                                        sqlite3VdbeAddOp4(
                                          v10,
                                          117,
                                          0,
                                          3,
                                          0,
                                          (__int64)"rowid not at end-of-record for row ",
                                          0);
                                        sqlite3VdbeAddOp3(v10, 111, 7, 3, 3);
                                        sqlite3VdbeAddOp4(v10, 117, 0, 4, 0, (__int64)" of index ", 0);
                                        sqlite3VdbeAddOp3(v10, 9, 0, v430 - 1, 0);
                                        *(_DWORD *)(sqlite3VdbeGetOp(v10, v261) + 8) = *(_DWORD *)(v10 + 144);
                                      }
                                      v253 = v452;
                                      v262 = 0;
                                      v438 = 0;
                                      if ( *((_WORD *)v452 + 47) )
                                      {
                                        v263 = 0;
                                        do
                                        {
                                          if ( *(char **)(*((_QWORD *)v253 + 8) + 8LL * v263) != "BINARY" )
                                          {
                                            if ( !v262 )
                                            {
                                              v438 = *((_DWORD *)v8 + 17) - 1;
                                              *((_DWORD *)v8 + 17) = v438;
                                            }
                                            sqlite3VdbeAddOp3(v10, 94, v440 + v442, v263, 3);
                                            sqlite3VdbeAddOp3(v10, 52, 3, v438, v260 + v263);
                                            v262 = v438;
                                          }
                                          ++v263;
                                        }
                                        while ( v263 < *((unsigned __int16 *)v253 + 47) );
                                        v257 = v441;
                                        if ( v262 )
                                        {
                                          v264 = sqlite3VdbeAddOp3(v10, 9, 0, 0, 0);
                                          sqlite3VdbeResolveLabel(v10, v438);
                                          sqlite3VdbeAddOp4(v10, 117, 0, 3, 0, (__int64)"row ", 0);
                                          sqlite3VdbeAddOp3(v10, 111, 7, 3, 3);
                                          sqlite3VdbeAddOp4(v10, 117, 0, 4, 0, (__int64)" values differ from index ", 0);
                                          sqlite3VdbeAddOp3(v10, 9, 0, v430 - 1, 0);
                                          v265 = sqlite3VdbeGetOp(v10, v264);
                                          v253 = v452;
                                          *(_DWORD *)(v265 + 8) = *(_DWORD *)(v10 + 144);
                                        }
                                      }
                                      if ( v253[98] )
                                      {
                                        v266 = *((_DWORD *)v8 + 17) - 1;
                                        *((_DWORD *)v8 + 17) = v266;
                                        if ( *((_WORD *)v253 + 47) )
                                        {
                                          v267 = 0;
                                          do
                                          {
                                            v268 = *((_QWORD *)v253 + 1);
                                            if ( *(__int16 *)(v268 + 2LL * v267) < 0
                                              || (v257[1][24 * *(__int16 *)(v268 + 2LL * v267) + 8] & 0xF) == 0 )
                                            {
                                              sqlite3VdbeAddOp3(v10, 50, v267 + IndexKey, v266, 0);
                                            }
                                            ++v267;
                                          }
                                          while ( v267 < *((unsigned __int16 *)v253 + 47) );
                                          v8 = v457;
                                        }
                                        v269 = sqlite3VdbeAddOp3(v10, 39, v440 + v442, 0, 0);
                                        sqlite3VdbeAddOp3(v10, 9, 0, v266, 0);
                                        v270 = sqlite3VdbeGetOp(v10, v269);
                                        v253 = v452;
                                        v271 = v440 + v442;
                                        *(_DWORD *)(v270 + 8) = *(_DWORD *)(v10 + 144);
                                        sqlite3VdbeAddOp4Int(
                                          v10,
                                          41,
                                          v271,
                                          v266,
                                          IndexKey,
                                          *((unsigned __int16 *)v253 + 47));
                                        sqlite3VdbeAddOp4(v10, 117, 0, 3, 0, (__int64)"non-unique entry in index ", 0);
                                        sqlite3VdbeAddOp3(v10, 9, 0, v430, 0);
                                        sqlite3VdbeResolveLabel(v10, v266);
                                      }
                                      v272 = sqlite3VdbeGetOp(v10, v445);
                                      v273 = v429;
                                      *(_DWORD *)(v272 + 8) = *(_DWORD *)(v10 + 144);
                                      sqlite3ResolvePartIdxLabel(v8, v273);
                                      v254 = v440;
                                      v256 = IndexKey;
                                      v255 = (__int64)v437;
                                    }
                                    v253 = (char *)*((_QWORD *)v253 + 5);
                                    ++v254;
                                    v452 = v253;
                                    v440 = v254;
                                  }
                                  while ( v253 );
                                  v14 = v444;
                                  v5 = (_QWORD *)v448;
                                }
                              }
                              v274 = (int)v453;
                              sqlite3VdbeAddOp3(v10, 39, v446, (_DWORD)v453, 0);
                              v275 = sqlite3VdbeGetOp(v10, (unsigned int)(v274 - 1));
                              v183 = 0;
                              *(_DWORD *)(v275 + 8) = *(_DWORD *)(v10 + 144);
                              if ( v455 )
                                sqlite3ReleaseTempRange(v8, v432, *(unsigned __int16 *)(v455 + 94));
                              v197 = v435;
                            }
                            v196 = *(_QWORD *)v434;
                            v434 = v196;
                          }
                          while ( v196 );
                          v13 = (char *)v449;
                          v195 = Index;
                        }
                        v276 = *(_QWORD **)(v195 + 16);
                        if ( v276 )
                        {
                          v277 = v435;
                          v278 = v276;
                          v279 = v451;
                          do
                          {
                            v280 = v278[2];
                            if ( (!v277 || v277 == v280) && *(_BYTE *)(v280 + 63) == 1 )
                            {
                              if ( *(__int16 *)(v280 + 54) > (__int16)v183
                                || (ElementWithHash = findElementWithHash(v5 + 69, **(_QWORD **)(v280 + 72), 0),
                                    LOWORD(v183) = 0,
                                    *(_QWORD *)(ElementWithHash + 16)) )
                              {
                                sqlite3ViewGetColumnNames(v8, v280);
                                v282 = *(_QWORD *)(v280 + 80);
                                LOWORD(v183) = 0;
                                if ( v282 )
                                {
                                  v283 = *(__int64 **)(v282 + 16);
                                  if ( v283 )
                                  {
                                    v284 = *v283;
                                    if ( v284 )
                                    {
                                      if ( *(int *)v284 >= 4 && *(_QWORD *)(v284 + 192) )
                                      {
                                        sqlite3VdbeAddOp3(v10, 174, v279, 3, v443);
                                        ++*(_DWORD *)(v280 + 44);
                                        sqlite3VdbeAppendP4(v10, v280, 4294967280LL);
                                        v285 = sqlite3VdbeAddOp3(v10, 50, 3, 0, 0);
                                        integrityCheckResultRow(v10);
                                        v286 = sqlite3VdbeGetOp(v10, v285);
                                        LOWORD(v183) = 0;
                                        *(_DWORD *)(v286 + 8) = *(_DWORD *)(v10 + 144);
                                      }
                                    }
                                  }
                                }
                              }
                              v277 = v435;
                            }
                            v278 = (_QWORD *)*v278;
                          }
                          while ( v278 );
                          v14 = v444;
                          v13 = (char *)v449;
                        }
                        v12 = v447;
                      }
                    }
                    v164 = v451;
                  }
                  v451 = ++v164;
                }
                while ( (signed int)v164 < *((_DWORD *)v5 + 10) );
              }
              v287 = sqlite3VdbeAddOpList(v10, 7, qword_1800B6C10);
              if ( v287 )
              {
                *(_DWORD *)(v287 + 8) = 1 - v433;
                *(_QWORD *)(v287 + 64) = "ok";
                *(_BYTE *)(v287 + 49) = -1;
                *(_BYTE *)(v287 + 121) = -1;
                v288 = sqlite3ErrStr(11);
                *(_QWORD *)(v289 + 136) = v288;
              }
              v290 = sqlite3VdbeGetOp(v10, 0);
              *(_DWORD *)(v290 + 12) = v291;
              goto LABEL_719;
            }
            if ( (_BYTE)v30 == 34 )
            {
              sqlite3_db_release_memory(v5);
              goto LABEL_719;
            }
            if ( (unsigned __int8)v30 > 0x22u )
            {
              v357 = v30 - 35;
              if ( !v357 )
              {
                v434 = 0;
                if ( v13 && !(unsigned int)sqlite3DecOrHexToI64(v13) )
                  sqlite3_soft_heap_limit64(v434);
                v105 = sqlite3_soft_heap_limit64(-1);
                goto LABEL_717;
              }
              v358 = v357 - 1;
              if ( !v358 )
              {
                if ( !v13 )
                {
                  v35 = *(unsigned __int8 *)(v443 + v435 + 16) - 1LL;
                  goto LABEL_718;
                }
                if ( !*((_BYTE *)v5 + 101) )
                {
                  sqlite3ErrorMsg(v8, "Safety level may not be changed inside a transaction");
                  goto LABEL_719;
                }
                if ( v12 != 1 )
                {
                  LOBYTE(v28) = 1;
                  SafetyLevel = getSafetyLevel(v13, 0, v28);
                  v413 = v435;
                  v414 = v443;
                  v415 = (SafetyLevel + 1) & 7;
                  if ( !v415 )
                    LOBYTE(v415) = 1;
                  *(_BYTE *)(v443 + v435 + 16) = v415;
                  *(_BYTE *)(v414 + v413 + 17) = 1;
                  goto LABEL_101;
                }
                goto LABEL_719;
              }
              v359 = v358 - 1;
              if ( !v359 )
              {
                if ( !v13 )
                  goto LABEL_719;
                sqlite3CodeVerifyNamedSchema(v8, v441);
                v393 = sqlite3LocateTable(v8, 2, v13, v441);
                v434 = v393;
                v394 = v393;
                if ( !v393 )
                  goto LABEL_719;
                Index = sqlite3PrimaryKeyIndex(v393);
                *((_DWORD *)v8 + 14) = 7;
                sqlite3ViewGetColumnNames(v8, v394);
                LOWORD(v395) = *(_WORD *)(v394 + 54);
                if ( (__int16)v395 <= 0 )
                  goto LABEL_719;
                v396 = *(_QWORD *)(v394 + 8);
                v397 = 0;
                v398 = v434;
                v399 = 0;
                v444 = v14;
                v400 = v396;
                v430 = 0;
                v429 = 0;
                do
                {
                  v401 = *(_WORD *)(v400 + 18);
                  if ( (v401 & 0x62) == 0 || v437[2] )
                  {
                    if ( (v401 & 1) != 0 )
                    {
                      v402 = 1;
                      if ( Index && (__int16)v395 >= 1 )
                      {
                        do
                        {
                          if ( *(__int16 *)(*(_QWORD *)(Index + 8) + 2LL * v402 - 2) == v399 )
                            break;
                          ++v402;
                        }
                        while ( v402 <= (__int16)v395 );
                      }
                    }
                    else
                    {
                      v402 = 0;
                    }
                    v403 = sqlite3ColumnExpr(v398, v400);
                    if ( v405 < 2 && v403 )
                      v434 = *(_QWORD *)(v403 + 8);
                    else
                      v434 = v404;
                    v406 = sqlite3ColumnType(v400, &Src);
                    v410 = (unsigned int)(v409 - v430);
                    v411 = "issisii";
                    if ( !v437[2] )
                      v411 = "issisi";
                    sqlite3VdbeMultiLoad(v10, 1, v411, v410, *(_QWORD *)v400, v406, v407, v434, v402, v408);
                    v399 = v429;
                    v397 = v430;
                  }
                  else
                  {
                    v430 = ++v397;
                  }
                  v395 = *(__int16 *)(v398 + 54);
                  ++v399;
                  v400 += 24;
                  v429 = v399;
                }
                while ( v399 < v395 );
LABEL_702:
                v14 = v444;
LABEL_703:
                v5 = (_QWORD *)v448;
                goto LABEL_704;
              }
              v360 = v359 - 1;
              if ( !v360 )
              {
                v374 = v441;
                *((_DWORD *)v8 + 14) = 6;
                sqlite3CodeVerifyNamedSchema(v8, v374);
                v375 = 0;
                v433 = 0;
                if ( *((int *)v5 + 10) > 0 )
                {
                  v444 = v14;
                  v376 = v441;
                  do
                  {
                    v377 = v375;
                    if ( !v376 || !(unsigned int)sqlite3_stricmp(v376, *(_QWORD *)(32LL * v375 + v5[4])) )
                    {
                      v378 = *(_QWORD *)(32 * v377 + v5[4] + 24);
                      v379 = *(_DWORD *)(v378 + 12);
                      v380 = v378 + 8;
                      if ( v379 )
                      {
                        v381 = v433;
LABEL_657:
                        for ( jj = *(_QWORD **)(v380 + 8); jj; jj = (_QWORD *)*jj )
                        {
                          v383 = jj[2];
                          if ( !*(_WORD *)(v383 + 54) )
                          {
                            --v379;
                            v384 = sqlite3MPrintf(v5, "SELECT*FROM\"%w\"", *(_QWORD *)v383);
                            v456 = v384;
                            if ( v384 )
                            {
                              v434 = 0;
                              sqlite3LockAndPrepare((_DWORD)v5, v384, -1, 0, 0, (__int64)&v434, 0);
                              sqlite3_finalize(v434);
                              sqlite3DbFree(v5, v456);
                            }
                            if ( *((_BYTE *)v5 + 103) )
                            {
                              sqlite3ErrorMsg(v5[44], "out of memory");
                              *(_DWORD *)(v5[44] + 24LL) = 7;
                            }
                            v380 = *(_QWORD *)(32 * v381 + v5[4] + 24) + 8LL;
                            if ( v379 )
                              goto LABEL_657;
                            break;
                          }
                        }
                        v13 = (char *)v449;
                      }
                      v385 = *(_QWORD *)(v380 + 8);
                      v434 = v385;
                      if ( v385 )
                      {
                        do
                        {
                          v386 = *(__int64 **)(v385 + 16);
                          if ( !v13 || !(unsigned int)sqlite3_stricmp(v13, *v386) )
                          {
                            if ( *((_BYTE *)v386 + 63) == 2 )
                            {
                              v387 = "view";
                            }
                            else if ( *((_BYTE *)v386 + 63) == 1 )
                            {
                              v387 = "virtual";
                            }
                            else
                            {
                              v387 = "shadow";
                              if ( (v386[6] & 0x1000) == 0 )
                                v387 = "table";
                            }
                            v388 = *v386;
                            v389 = *((__int16 *)v386 + 27);
                            v390 = *((_DWORD *)v386 + 12) >> 7;
                            v391 = HIWORD(*((_DWORD *)v386 + 12)) & 1;
                            Index = (__int64)v387;
                            v392 = sqlite3PreferredTableName(v388);
                            LODWORD(v426) = v390 & 1;
                            sqlite3VdbeMultiLoad(
                              v10,
                              1,
                              "sssiii",
                              *(_QWORD *)(32LL * v433 + v5[4]),
                              v392,
                              Index,
                              v389,
                              v426,
                              v391,
                              v428);
                            v13 = (char *)v449;
                          }
                          v385 = *(_QWORD *)v434;
                          v434 = v385;
                        }
                        while ( v385 );
                        v376 = v441;
                      }
                    }
                    v375 = v433 + 1;
                    v433 = v375;
                  }
                  while ( v375 < *((_DWORD *)v5 + 10) );
                  v14 = v444;
                }
                goto LABEL_719;
              }
              v361 = v360 - 1;
              if ( !v361 )
              {
                if ( v13 )
                {
                  changeTempStorage(v8, v13);
                  goto LABEL_719;
                }
                v35 = *((unsigned __int8 *)v5 + 102);
                goto LABEL_718;
              }
              v362 = v361 - 1;
              if ( !v362 )
              {
                v371 = sqlite3MutexAlloc(11);
                sqlite3_mutex_enter(v371);
                if ( !v13 )
                {
                  v68 = sqlite3_temp_directory;
                  goto LABEL_637;
                }
                if ( !*v13
                  || (v429 = 0,
                      !(*(unsigned int (__fastcall **)(_QWORD, char *, __int64, unsigned int *))(*v5 + 56LL))(
                         *v5,
                         v13,
                         1,
                         &v429))
                  && v429 )
                {
                  if ( *((_BYTE *)v5 + 102) <= 1u )
                    invalidateTempStorage(v8);
                  sqlite3_free(sqlite3_temp_directory);
                  v373 = 0;
                  if ( *v13 )
                    v373 = sqlite3_mprintf("%s", v13);
                  sqlite3_temp_directory = v373;
                  goto LABEL_642;
                }
LABEL_641:
                sqlite3ErrorMsg(v8, "not a writable directory");
                goto LABEL_642;
              }
              v363 = v362 - 1;
              if ( !v363 )
              {
                v434 = 0;
                if ( v13 && !(unsigned int)sqlite3DecOrHexToI64(v13) )
                  sqlite3_limit(v5, 11, v434 & 0x7FFFFFFF);
                v42 = sqlite3_limit(v5, 11, 0xFFFFFFFFLL);
                goto LABEL_547;
              }
              v364 = v363 - 1;
              if ( !v364 )
              {
                if ( v13 )
                {
                  v429 = 0;
                  sqlite3GetInt32(v13, &v429);
                  sqlite3_wal_autocheckpoint(v5, v429);
                }
                if ( (__int64 (__fastcall *)())v5[45] == sqlite3WalDefaultHook )
                  v42 = *((_DWORD *)v5 + 92);
                else
                  v42 = 0;
                goto LABEL_547;
              }
              if ( v364 != 1 )
                goto LABEL_613;
              v365 = 12;
              if ( *v453 )
                v365 = v12;
              LODWORD(v443) = v365;
              v366 = 0;
              if ( v13 )
              {
                if ( (unsigned int)sqlite3StrICmp(v13, "full") )
                {
                  if ( (unsigned int)sqlite3StrICmp(v367, "restart") )
                  {
                    v369 = sqlite3StrICmp(v368, "truncate");
                    v366 = 0;
                    if ( !v369 )
                      v366 = 3;
                  }
                  else
                  {
                    v366 = 2;
                  }
                }
                else
                {
                  v366 = 1;
                }
              }
              v370 = v443;
              *((_DWORD *)v8 + 14) = 3;
              sqlite3VdbeAddOp3(v10, 3, v370, v366, 1);
              v310 = 3;
              v419 = 0;
              goto LABEL_529;
            }
            if ( (unsigned __int8)v30 <= 0x1Du )
            {
              if ( (_BYTE)v30 == 29 )
              {
                *((_DWORD *)v8 + 14) = 1;
                for ( kk = (_QWORD *)v5[70]; kk; kk = (_QWORD *)*kk )
                  sqlite3VdbeMultiLoad(v10, 1, "s", *(_QWORD *)(kk[2] + 8LL), v416, v420, v424, v426, v427, v428);
                goto LABEL_719;
              }
              v292 = v30 - 23;
              if ( v292 )
              {
                v293 = v292 - 1;
                if ( !v293 )
                {
                  v319 = *(__int64 **)(*(_QWORD *)(v443 + v435 + 8) + 8LL);
                  v320 = -2;
                  v434 = -2;
                  v321 = *v319;
                  if ( v13 )
                  {
                    sqlite3DecOrHexToI64(v13);
                    v320 = -1;
                  }
                  if ( v320 >= -1 )
                  {
                    v322 = *(_QWORD *)(v321 + 296);
                    *(_QWORD *)(v321 + 208) = v320;
                    if ( v322 )
                      *(_QWORD *)(v322 + 32) = v320;
                  }
                  v35 = *(_QWORD *)(v321 + 208);
                  goto LABEL_718;
                }
                v294 = v293 - 2;
                if ( v294 )
                {
                  v295 = v294 - 1;
                  if ( v295 )
                  {
                    if ( v295 != 1 )
                      goto LABEL_613;
                    v448 = 0;
                    if ( v13 )
                    {
                      sqlite3DecOrHexToI64(v13);
                      Index = v448;
                      v296 = v453;
                      if ( *((_DWORD *)v453 + 2) )
                      {
                        v301 = *((_DWORD *)v5 + 10) - 1;
                        v429 = v301;
                        if ( v301 >= 0 )
                        {
                          v302 = Index;
                          do
                          {
                            v303 = *(_QWORD *)(32LL * (unsigned int)v301 + v5[4] + 8);
                            v434 = v303;
                            if ( v303 && v301 == v12 )
                            {
                              v304 = *(_QWORD *)(v303 + 8);
                              sqlite3BtreeEnter(v303);
                              *(_QWORD *)(*(_QWORD *)v304 + 160LL) = v302;
                              pagerFixMaplimit();
                              sqlite3BtreeLeave(v434);
                              v301 = v429;
                              v302 = v448;
                            }
                            v12 = v447;
                            v429 = --v301;
                          }
                          while ( v301 >= 0 );
                          goto LABEL_467;
                        }
                      }
                      else
                      {
                        v5[8] = v448;
                        v297 = *((_DWORD *)v5 + 10) - 1;
                        v429 = v297;
                        if ( v297 >= 0 )
                        {
                          v298 = Index;
                          do
                          {
                            v299 = *(_QWORD *)(32LL * (unsigned int)v297 + v5[4] + 8);
                            v434 = v299;
                            if ( v299 && (v297 == v12 || !*((_DWORD *)v296 + 2)) )
                            {
                              v300 = *(_QWORD *)(v299 + 8);
                              sqlite3BtreeEnter(v299);
                              *(_QWORD *)(*(_QWORD *)v300 + 160LL) = v298;
                              pagerFixMaplimit();
                              sqlite3BtreeLeave(v434);
                              v296 = v453;
                              v297 = v429;
                              v298 = v448;
                            }
                            v12 = v447;
                            v429 = --v297;
                          }
                          while ( v297 >= 0 );
LABEL_467:
                          v13 = (char *)v449;
                        }
                      }
                    }
                    v448 = -1;
                    v305 = sqlite3_file_control(v5, v441, 18, &v448);
                    if ( v305 )
                    {
                      if ( v305 != 12 )
                      {
                        ++*((_DWORD *)v8 + 12);
                        *((_DWORD *)v8 + 6) = v305;
                      }
                      goto LABEL_719;
                    }
                    v35 = v448;
                    goto LABEL_718;
                  }
                  v434 = 0;
                  sqlite3CodeVerifySchema(v8, (unsigned int)v12);
                  v306 = *((_DWORD *)v8 + 14) + 1;
                  *((_DWORD *)v8 + 14) = v306;
                  v307 = *v14;
                  v429 = v306;
                  if ( *((_BYTE *)qword_1800ADCF0 + v307) == 112 )
                  {
                    sqlite3VdbeAddOp3(v10, 178, v12, v306, 0);
                    v308 = v429;
                  }
                  else
                  {
                    if ( !v13 || (unsigned int)sqlite3DecOrHexToI64(v13) || (v309 = v434, v434 < 0) )
                    {
                      v309 = 0;
                    }
                    else if ( v434 > 4294967294LL )
                    {
                      v309 = -2;
                    }
                    v308 = v429;
                    sqlite3VdbeAddOp3(v10, 179, v12, v429, v309);
                  }
                  v419 = 0;
                  v310 = 1;
                  v311 = v308;
LABEL_482:
                  sqlite3VdbeAddOp3(v10, 84, v311, v310, v419);
                  goto LABEL_719;
                }
                v312 = "exclusive";
                if ( !v13 )
                  goto LABEL_487;
                if ( !(unsigned int)sqlite3StrICmp(v13, "exclusive") )
                {
                  v314 = 1;
                  goto LABEL_488;
                }
                v315 = sqlite3StrICmp(v313, "normal");
                v314 = 0;
                if ( v315 )
LABEL_487:
                  v314 = 0xFFFFFFFFLL;
LABEL_488:
                if ( !*((_DWORD *)v453 + 2) )
                {
                  if ( (_DWORD)v314 == -1 )
                  {
                    v316 = *((unsigned __int8 *)v5 + 105);
LABEL_495:
                    if ( v316 != 1 )
                      v312 = "normal";
                    v152 = (char *)v312;
                    goto LABEL_498;
                  }
                  for ( mm = 2; mm < *((_DWORD *)v5 + 10); mm = v318 + 1 )
                    sqlite3PagerLockingMode(**(_QWORD **)(*(_QWORD *)(32LL * mm + v5[4] + 8) + 8LL), v314);
                  *((_BYTE *)v5 + 105) = v314;
                }
                v316 = sqlite3PagerLockingMode(**(_QWORD **)(*(_QWORD *)(v443 + v435 + 8) + 8LL), v314);
                goto LABEL_495;
              }
              v323 = 0;
              if ( v13 )
              {
                LODWORD(v443) = sqlite3Strlen30(v13, v27, 0);
                v325 = v324;
                v326 = sqlite3JournalModename(0);
                if ( v326 )
                {
                  v444 = v14;
                  while ( 1 )
                  {
                    v328 = sqlite3_strnicmp(v13, v326, v327);
                    v323 = 0;
                    if ( !v328 )
                      break;
                    v326 = sqlite3JournalModename((unsigned int)++v325);
                    v327 = v443;
                    if ( !v326 )
                      goto LABEL_517;
                  }
                  if ( v325 == 2 )
                  {
                    if ( (v5[6] & 0x10000000) != 0 )
                      goto LABEL_517;
                  }
                  else
                  {
                    v444 = v14;
                    if ( v325 == -1 )
                      goto LABEL_518;
                  }
LABEL_520:
                  if ( *((_DWORD *)v5 + 10) - 1 >= 0 )
                  {
                    v329 = *((_DWORD *)v5 + 10) - 1;
                    do
                    {
                      if ( *(_QWORD *)(32LL * (unsigned int)v329 + v5[4] + 8) != v323
                        && (v329 == v12 || *((_DWORD *)v453 + 2) == (_DWORD)v323) )
                      {
                        sqlite3VdbeUsesBtree(v10, (unsigned int)v329);
                        sqlite3VdbeAddOp3(v330, 4, v329, 1, v325);
                        v323 = 0;
                      }
                      --v329;
                    }
                    while ( v329 >= 0 );
                    v14 = v444;
                    v13 = (char *)v449;
                  }
                  v419 = v323;
                  v310 = 1;
LABEL_529:
                  v311 = 1;
                  goto LABEL_482;
                }
              }
              v444 = v14;
LABEL_517:
              v325 = -1;
LABEL_518:
              if ( *((_DWORD *)v453 + 2) == (_DWORD)v323 )
              {
                v12 = v323;
                *((_DWORD *)v453 + 2) = 1;
              }
              goto LABEL_520;
            }
            v332 = v30 - 30;
            if ( v332 )
            {
              v333 = v332 - 1;
              if ( !v333 )
              {
                v338 = *(_QWORD *)(v443 + v435 + 8);
                if ( v13 )
                {
                  v429 = 0;
                  sqlite3GetInt32(v13, &v429);
                  v340 = v429;
                  *((_DWORD *)v5 + 29) = v429;
                  if ( (unsigned int)sqlite3BtreeSetPageSize(v338, v340, 0, 0) == 7 )
                    sqlite3OomFault(v5);
                  goto LABEL_719;
                }
                if ( v338 )
                  v339 = *(_DWORD *)(*(_QWORD *)(v338 + 8) + 52LL);
                else
                  v339 = 0;
                v35 = v339;
                goto LABEL_718;
              }
              v334 = v333 - 1;
              if ( v334 )
              {
                if ( v334 != 1 )
                  goto LABEL_613;
                v335 = -1;
                v336 = 0;
                v434 = *(_QWORD *)(v443 + v435 + 8);
                if ( v13 )
                {
                  if ( (unsigned int)sqlite3_stricmp(v13, "fast") )
                    v335 = (unsigned __int8)sqlite3GetBoolean(v13, 0);
                  else
                    v335 = 2;
                }
                if ( !*((_DWORD *)v453 + 2) && v335 >= 0 && *((int *)v5 + 10) > 0 )
                {
                  do
                    sqlite3BtreeSecureDelete(*(_QWORD *)(32LL * v336++ + v5[4] + 8), (unsigned int)v335);
                  while ( v336 < *((_DWORD *)v5 + 10) );
                }
                v42 = sqlite3BtreeSecureDelete(v434, (unsigned int)v335);
                goto LABEL_547;
              }
              for ( nn = 0; nn != 67; ++nn )
                sqlite3VdbeMultiLoad(v10, 1, "s", (&off_1800AA7D0)[3 * nn], v416, v420, v424, v426, v427, v428);
              goto LABEL_704;
            }
            if ( v13 )
            {
              v429 = 0;
              sqlite3GetInt32(v13, &v429);
              IndexKey = v429;
              if ( (v429 & 2) == 0 )
                goto LABEL_719;
              v430 = 0;
              v433 = 0;
              if ( (v429 & 0x10) == 0 )
              {
                v438 = 0;
                goto LABEL_564;
              }
            }
            else
            {
              v430 = 0;
              IndexKey = 65534;
              v433 = 0;
            }
            v438 = (unsigned int)(*((_DWORD *)v5 + 186) - 1) > 0x7CE ? 0x7D0 : 0;
LABEL_564:
            v432 = *((_DWORD *)v8 + 13);
            *((_DWORD *)v8 + 13) = v432 + 1;
            if ( v441 )
            {
              v341 = v12;
              v442 = v12;
            }
            else
            {
              v341 = *((_DWORD *)v5 + 10) - 1;
              v442 = v341;
              if ( v12 > v341 )
              {
LABEL_595:
                sqlite3VdbeAddOp3(v10, 166, 0, 0, 0);
                if ( !*((_BYTE *)v5 + 103) )
                {
                  if ( v438 )
                  {
                    if ( v433 > 100 )
                    {
                      v353 = sqlite3VdbeGetOp(v10, 0);
                      v356 = *(_DWORD *)(v10 + 144);
                      if ( v356 > 0 )
                      {
                        do
                        {
                          if ( *(_BYTE *)(v353 + 24 * v354) == 0x94 )
                            *(_DWORD *)(v353 + 24 * v354 + 8) = v355;
                          v354 = (unsigned int)(v354 + 1);
                        }
                        while ( (int)v354 < v356 );
                      }
                    }
                  }
                }
                goto LABEL_719;
              }
            }
            do
            {
              if ( v12 != 1 )
              {
                sqlite3CodeVerifySchema(v8, (unsigned int)v12);
                for ( i1 = *(_QWORD *)(*(_QWORD *)(32LL * v12 + v5[4] + 24) + 16LL); ; i1 = *(_QWORD *)v434 )
                {
                  v434 = i1;
                  if ( !i1 )
                    break;
                  v343 = *(_QWORD *)(i1 + 16);
                  Index = v343;
                  if ( !*(_BYTE *)(v343 + 63) && (unsigned int)sqlite3_strnicmp(*(_QWORD *)v343, "sqlite_", 7) )
                  {
                    v344 = Index;
                    v345 = 0;
                    v429 = 0;
                    v346 = *(_QWORD *)(Index + 16);
                    v347 = *(unsigned __int16 *)(Index + 58);
                    v445 = v347;
                    if ( v346 )
                    {
                      do
                      {
                        ++v345;
                        if ( *(char *)(v346 + 100) >= 0 )
                          v347 = -1;
                        v346 = *(_QWORD *)(v346 + 40);
                      }
                      while ( v346 );
                      v429 = v345;
                      v445 = v347;
                    }
                    if ( (*(_DWORD *)(Index + 48) & 0x100) != 0
                      || (IndexKey & 0x10000) != 0
                      || *(_QWORD *)(Index + 16) && (v347 & 0x8000u) != 0 )
                    {
                      if ( ++v430 == 2 )
                      {
                        sqlite3BeginWriteOperation(v8, 0, (unsigned int)v12);
                        v344 = Index;
                        v345 = v429;
                      }
                      v433 += v345 + 1;
                      sqlite3OpenTable((_DWORD)v8, v432, v12, v344, 112);
                      if ( (v445 & 0x8000u) != 0 )
                      {
                        v429 = IndexKey & 1;
                        sqlite3VdbeAddOp3(v10, 36, v432, *(_DWORD *)(v10 + 144) + v429 + 2, 0);
                      }
                      else
                      {
                        if ( (__int16)v445 < 33 )
                          v348 = -1;
                        else
                          v348 = (__int16)v445 - 33;
                        v429 = IndexKey & 1;
                        sqlite3VdbeAddOp4Int(v10, 33, v432, *(_DWORD *)(v10 + 144) + v429 + 2, v348, (__int16)v445 + 33);
                      }
                      v349 = sqlite3MPrintf(
                               v5,
                               "ANALYZE \"%w\".\"%w\"",
                               *(_QWORD *)(32LL * v12 + v5[4]),
                               *(_QWORD *)Index);
                      if ( v429 )
                      {
                        TempReg = sqlite3GetTempReg(v8);
                        sqlite3VdbeAddOp4(v10, 117, 0, TempReg, v352, v351, -6);
                        sqlite3VdbeAddOp3(v10, 84, TempReg, 1, 0);
                        v12 = v447;
                      }
                      else
                      {
                        sqlite3VdbeAddOp4(v10, 148, v438 != 0 ? 2 : 0, v438, 0, v349, -6);
                      }
                    }
                  }
                }
                v341 = v442;
              }
              v447 = ++v12;
            }
            while ( v12 <= v341 );
            v13 = (char *)v449;
            goto LABEL_595;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180016bf4  push    rbp
0x180016bf6  push    rbx
0x180016bf7  push    rsi
0x180016bf8  push    rdi
0x180016bf9  push    r12
0x180016bfb  push    r13
0x180016bfd  push    r14
0x180016bff  push    r15
0x180016c01  lea     rbp, [rsp-68h]
0x180016c06  sub     rsp, 168h
0x180016c0d  mov     rax, cs:__security_cookie
0x180016c14  xor     rax, rsp
0x180016c17  mov     [rbp+0A0h+var_48], rax
0x180016c1b  mov     r13, [rcx]
0x180016c1e  xorps   xmm0, xmm0
0x180016c21  movups  [rbp+0A0h+var_68], xmm0
0x180016c25  mov     [rbp+0A0h+var_C8], r13
0x180016c29  mov     rsi, r8
0x180016c2c  movups  [rbp+0A0h+var_58], xmm0
0x180016c30  mov     [rbp+0A0h+var_118], r9
0x180016c34  mov     r14, rdx
0x180016c37  mov     [rbp+0A0h+var_A8], r8
0x180016c3b  mov     rdi, rcx
0x180016c3e  mov     [rbp+0A0h+var_88], rcx
0x180016c42  call    sqlite3GetVdbe
0x180016c47  xor     ebx, ebx
0x180016c49  mov     [rbp+0A0h+var_90], rax
0x180016c4d  mov     r15, rax
0x180016c50  test    rax, rax
0x180016c53  jz      loc_18001A6D6
0x180016c59  lea     r12d, [rbx+1]
0x180016c5d  mov     dword ptr [rsp+1A0h+var_180], ebx
0x180016c61  mov     r9d, r12d
0x180016c64  mov     r8d, r12d
0x180016c67  mov     edx, 0A6h
0x180016c6c  mov     rcx, rax
0x180016c6f  call    sqlite3VdbeAddOp3
0x180016c74  mov     rax, [rdi]
0x180016c77  mov     dword ptr [rdi+38h], 2
0x180016c7e  cmp     [rsi+8], ebx
0x180016c81  jbe     short loc_180016CCF
0x180016c83  cmp     [rax+0C5h], bl
0x180016c89  jz      short loc_180016C9F
0x180016c8b  lea     rdx, aCorruptDatabas; "corrupt database"
0x180016c92  mov     rcx, rdi
0x180016c95  call    sqlite3ErrorMsg
0x180016c9a  jmp     loc_18001A6D6
0x180016c9f  mov     rdx, r14
0x180016ca2  mov     rcx, rax
0x180016ca5  call    sqlite3FindDb
0x180016caa  mov     [rbp+0A0h+var_D0], eax
0x180016cad  mov     ebx, eax
0x180016caf  test    eax, eax
0x180016cb1  jns     short loc_180016CCA
0x180016cb3  mov     r8, r14
0x180016cb6  lea     rdx, aUnknownDatabas_0; "unknown database %T"
0x180016cbd  mov     rcx, rdi
0x180016cc0  call    sqlite3ErrorMsg
0x180016cc5  jmp     loc_18001A6D6
0x180016cca  mov     r14, rsi
0x180016ccd  jmp     short loc_180016CD9
0x180016ccf  movzx   ebx, byte ptr [rax+0C4h]
0x180016cd6  mov     [rbp+0A0h+var_D0], ebx
0x180016cd9  xor     esi, esi
0x180016cdb  test    ebx, ebx
0x180016cdd  js      loc_18001A6D6
0x180016ce3  mov     rax, [r13+20h]
0x180016ce7  mov     [rbp+0A0h+var_E8], rax
0x180016ceb  cmp     ebx, r12d
0x180016cee  jnz     short loc_180016D00
0x180016cf0  mov     rcx, rdi
0x180016cf3  call    sqlite3OpenTempDatabase
0x180016cf8  test    eax, eax
0x180016cfa  jnz     loc_18001A6D6
0x180016d00  test    r14, r14
0x180016d03  jz      loc_18001A6D6
0x180016d09  mov     r8d, [r14+8]
0x180016d0d  mov     rcx, r13
0x180016d10  mov     rdx, [r14]
0x180016d13  call    sqlite3DbStrNDup
0x180016d18  mov     rcx, rax
0x180016d1b  mov     r14, rax
0x180016d1e  call    sqlite3Dequote
0x180016d23  test    rcx, rcx
0x180016d26  jz      loc_18001A6D6
0x180016d2c  movsxd  rax, ebx
0x180016d2f  shl     rax, 5
0x180016d33  mov     [rbp+0A0h+var_120], rax
0x180016d37  cmp     [rbp+0A0h+arg_20], esi
0x180016d3d  jz      short loc_180016D5B
0x180016d3f  mov     r8, [rbp+0A0h+var_118]
0x180016d43  lea     rdx, aT; "-%T"
0x180016d4a  mov     rcx, r13
0x180016d4d  call    sqlite3MPrintf
0x180016d52  mov     rsi, rax
0x180016d55  mov     [rbp+0A0h+var_C0], rax
0x180016d59  jmp     short loc_180016D88
0x180016d5b  mov     rax, [rbp+0A0h+var_118]
0x180016d5f  test    rax, rax
0x180016d62  jz      short loc_180016D84
0x180016d64  mov     r8d, [rax+8]
0x180016d68  mov     rcx, r13
0x180016d6b  mov     rdx, [rax]
0x180016d6e  call    sqlite3DbStrNDup
0x180016d73  mov     rcx, rax
0x180016d76  mov     [rbp+0A0h+var_C0], rax
0x180016d7a  mov     rsi, rax
0x180016d7d  call    sqlite3Dequote
0x180016d82  jmp     short loc_180016D88
0x180016d84  mov     [rbp+0A0h+var_C0], rsi
0x180016d88  mov     rax, [rbp+0A0h+var_A8]
0x180016d8c  xor     edx, edx
0x180016d8e  cmp     [rax+8], edx
0x180016d91  jbe     short loc_180016DA1
0x180016d93  mov     rax, [rbp+0A0h+var_120]
0x180016d97  mov     rcx, [rbp+0A0h+var_E8]
0x180016d9b  mov     rax, [rcx+rax]
0x180016d9f  jmp     short loc_180016DA4
0x180016da1  mov     rax, rdx
0x180016da4  mov     rcx, [rdi]
0x180016da7  mov     [rbp+0A0h+var_F8], rax
0x180016dab  mov     r10, [rcx+200h]
0x180016db2  test    r10, r10
0x180016db5  jz      loc_180016E42
0x180016dbb  cmp     [rcx+0C5h], dl
0x180016dc1  jnz     short loc_180016E42
0x180016dc3  cmp     [rdi+134h], dl
0x180016dc9  jnz     short loc_180016E42
0x180016dcb  mov     rdx, [rdi+178h]
0x180016dd2  mov     r9, rsi
0x180016dd5  mov     rcx, [rcx+208h]
0x180016ddc  mov     r8, r14
0x180016ddf  mov     [rsp+1A0h+var_178], rdx
0x180016de4  mov     edx, 13h
0x180016de9  mov     [rsp+1A0h+var_180], rax
0x180016dee  mov     rax, r10
0x180016df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016df6  mov     [rsp+1A0h+var_130], eax
0x180016dfa  cmp     eax, r12d
0x180016dfd  jnz     short loc_180016E1B
0x180016dff  lea     rdx, aNotAuthorized; "not authorized"
0x180016e06  mov     rcx, rdi
0x180016e09  call    sqlite3ErrorMsg
0x180016e0e  mov     eax, [rsp+1A0h+var_130]
0x180016e12  mov     dword ptr [rdi+18h], 17h
0x180016e19  jmp     short loc_180016E38
0x180016e1b  test    eax, 0FFFFFFFDh
0x180016e20  jz      short loc_180016E38
0x180016e22  lea     rdx, aAuthorizerMalf; "authorizer malfunction"
0x180016e29  mov     rcx, rdi
0x180016e2c  call    sqlite3ErrorMsg
0x180016e31  mov     eax, r12d
0x180016e34  mov     [rdi+18h], r12d
0x180016e38  xor     edx, edx
0x180016e3a  test    eax, eax
0x180016e3c  jnz     loc_18001A6BB
0x180016e42  mov     qword ptr [rbp+0A0h+var_68], rdx
0x180016e46  mov     rcx, r13
0x180016e49  mov     qword ptr [rbp+0A0h+var_68+8], r14
0x180016e4d  mov     qword ptr [rbp+0A0h+var_58], rsi
0x180016e51  mov     qword ptr [rbp+0A0h+var_58+8], rdx
0x180016e55  mov     [r13+298h], edx
0x180016e5c  call    sqlite3SafetyCheckOk
0x180016e61  test    eax, eax
0x180016e63  jnz     short loc_180016E96
0x180016e65  lea     rax, a20240523132527+14h; "96c92aba00c8375bc32fafcdf12429c58bd8aab"...
0x180016e6c  mov     ebx, 15h
0x180016e71  mov     ecx, ebx
0x180016e73  mov     [rsp+1A0h+var_180], rax
0x180016e78  mov     r9d, 2CE24h
0x180016e7e  lea     r8, aMisuse; "misuse"
0x180016e85  lea     rdx, aSAtLineDOf10s; "%s at line %d of [%.10s]"
0x180016e8c  call    sqlite3_log
0x180016e91  jmp     loc_180016F53
0x180016e96  mov     rcx, [r13+18h]
0x180016e9a  mov     [rsp+1A0h+var_130], r12d
0x180016e9f  call    sqlite3_mutex_enter
0x180016ea4  mov     rdx, [rbp+0A0h+var_F8]
0x180016ea8  mov     rcx, r13
0x180016eab  call    sqlite3DbNameToBtree
0x180016eb0  mov     [rbp+0A0h+var_110], rax
0x180016eb4  test    rax, rax
0x180016eb7  jz      short loc_180016EFC
0x180016eb9  mov     rcx, rax
0x180016ebc  call    sqlite3BtreeEnter
0x180016ec1  mov     rax, [rbp+0A0h+var_110]
0x180016ec5  lea     r8, [rbp+0A0h+var_68]
0x180016ec9  mov     ebx, [r13+298h]
0x180016ed0  mov     rcx, [rax+8]
0x180016ed4  mov     rdx, [rcx]
0x180016ed7  mov     rcx, [rdx+48h]
0x180016edb  mov     edx, 0Eh
0x180016ee0  call    sqlite3OsFileControl
0x180016ee5  mov     rcx, [rbp+0A0h+var_110]
0x180016ee9  mov     [rsp+1A0h+var_130], eax
0x180016eed  mov     [r13+298h], ebx
0x180016ef4  call    sqlite3BtreeLeave
0x180016ef9  mov     ebx, [rbp+0A0h+var_D0]
0x180016efc  mov     rcx, [r13+18h]
0x180016f00  call    sqlite3_mutex_leave
0x180016f05  mov     eax, [rsp+1A0h+var_130]
0x180016f09  test    eax, eax
0x180016f0b  jnz     short loc_180016F4C
0x180016f0d  mov     edx, r12d
0x180016f10  mov     rcx, r15
0x180016f13  call    sqlite3VdbeSetNumCols
0x180016f18  mov     r9, qword ptr [rbp+0A0h+var_68]
0x180016f1c  xor     r8d, r8d
0x180016f1f  xor     edx, edx
0x180016f21  mov     [rsp+1A0h+var_180], 0FFFFFFFFFFFFFFFFh
0x180016f2a  mov     rcx, r15
0x180016f2d  call    sqlite3VdbeSetColName
0x180016f32  mov     rdx, qword ptr [rbp+0A0h+var_68]
0x180016f36  mov     rcx, r15
0x180016f39  call    returnSingleText
0x180016f3e  mov     rcx, qword ptr [rbp+0A0h+var_68]
0x180016f42  call    sqlite3_free
0x180016f47  jmp     loc_18001A6BB
0x180016f4c  cmp     eax, 0Ch
0x180016f4f  jz      short loc_180016F80
0x180016f51  mov     ebx, eax
0x180016f53  mov     r8, qword ptr [rbp+0A0h+var_68]
0x180016f57  test    r8, r8
0x180016f5a  jz      short loc_180016F74
0x180016f5c  lea     rdx, aS_10; "%s"
0x180016f63  mov     rcx, rdi
0x180016f66  call    sqlite3ErrorMsg
0x180016f6b  mov     rcx, qword ptr [rbp+0A0h+var_68]
0x180016f6f  call    sqlite3_free
0x180016f74  add     [rdi+30h], r12d
0x180016f78  mov     [rdi+18h], ebx
0x180016f7b  jmp     loc_18001A6BB
0x180016f80  mov     rcx, r14
0x180016f83  call    pragmaLocate
0x180016f88  mov     [rbp+0A0h+var_110], rax
0x180016f8c  mov     r10, rax
0x180016f8f  test    rax, rax
0x180016f92  jz      loc_18001A6BB
0x180016f98  test    [rax+9], r12b
0x180016f9c  jz      short loc_180016FB2
0x180016f9e  mov     rcx, rdi
0x180016fa1  call    sqlite3ReadSchema
0x180016fa6  test    eax, eax
0x180016fa8  jnz     loc_18001A6BB
0x180016fae  mov     r10, [rbp+0A0h+var_110]
0x180016fb2  mov     r11d, 2
0x180016fb8  test    [r10+9], r11b
0x180016fbc  jnz     short loc_180016FDF
0x180016fbe  test    byte ptr [r10+9], 4
0x180016fc3  jz      short loc_180016FCA
0x180016fc5  test    rsi, rsi
0x180016fc8  jnz     short loc_180016FDF
0x180016fca  mov     rdx, r10
0x180016fcd  mov     rcx, r15
0x180016fd0  call    setPragmaResultColumnNames
0x180016fd5  mov     r10, [rbp+0A0h+var_110]
0x180016fd9  mov     r11d, 2
0x180016fdf  movzx   ecx, byte ptr [r10+8]
0x180016fe4  cmp     ecx, 16h
0x180016fe7  ja      loc_1800195C9
0x180016fed  jz      loc_1800180BC
0x180016ff3  mov     eax, 0Ch
0x180016ff8  cmp     ecx, eax
0x180016ffa  ja      loc_180017533
0x180017000  jz      loc_1800174CA
0x180017006  cmp     ecx, 7
0x180017009  ja      loc_180017348
0x18001700f  jz      loc_1800172BC
0x180017015  sub     ecx, r12d
0x180017018  jz      loc_18001727E
0x18001701e  sub     ecx, r12d
0x180017021  jz      loc_1800171D8
0x180017027  sub     ecx, r12d
0x18001702a  jz      loc_180017148
0x180017030  sub     ecx, r12d
0x180017033  jz      short loc_18001708F
0x180017035  cmp     ecx, r11d
0x180017038  jnz     loc_180019FEA
0x18001703e  xor     eax, eax
0x180017040  test    rsi, rsi
0x180017043  jnz     short loc_18001705B
0x180017045  mov     rax, [rbp+0A0h+var_120]
0x180017049  mov     rcx, [rbp+0A0h+var_E8]
0x18001704d  mov     rax, [rcx+rax+18h]
0x180017052  movsxd  rdx, dword ptr [rax+74h]
0x180017056  jmp     loc_18001A6B3
0x18001705b  lea     rdx, [rsp+1A0h+var_13C]
0x180017060  mov     [rsp+1A0h+var_13C], eax
0x180017064  mov     rcx, rsi
0x180017067  call    sqlite3GetInt32
0x18001706c  mov     r8, [rbp+0A0h+var_120]
0x180017070  mov     r9, [rbp+0A0h+var_E8]
0x180017074  mov     eax, [rsp+1A0h+var_13C]
0x180017078  mov     rcx, [r9+r8+18h]
0x18001707d  mov     [rcx+74h], eax
0x180017080  mov     rdx, [r9+r8+18h]
0x180017085  mov     rcx, [r9+r8+8]
0x18001708a  jmp     loc_1800180AF
0x18001708f  xor     eax, eax
0x180017091  test    rsi, rsi
  ... truncated ...
```
