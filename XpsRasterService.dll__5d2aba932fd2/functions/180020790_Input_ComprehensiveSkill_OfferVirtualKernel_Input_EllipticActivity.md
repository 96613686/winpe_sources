# Input::ComprehensiveSkill::OfferVirtualKernel(Input::EllipticActivity &)

- ea: `0x180020790`
- end: `0x1800223ff`
- name: `?OfferVirtualKernel@ComprehensiveSkill@Input@@QEAAXAEAVEllipticActivity@2@@Z`
- size: `7279`
- prototype: `void __fastcall(Input::ComprehensiveSkill *__hidden this, struct Input::EllipticActivity *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180023a20`

## callees

- `0x180003180`
- `0x180003ca0`
- `0x18000df20`
- `0x18000e0c0`
- `0x18000e4b0`
- `0x18001ee30`
- `0x18001f0d0`
- `0x180020790`
- `0x1800bf3b0`

## pseudocode

```c
void __fastcall Input::ComprehensiveSkill::OfferVirtualKernel(
        Input::ComprehensiveSkill *this,
        struct Input::EllipticActivity *a2,
        __int64 a3,
        __int64 a4)
{
  float v6; // xmm13_4
  float v7; // xmm12_4
  int v8; // r13d
  int v9; // edi
  int v10; // esi
  float v11; // xmm15_4
  float v12; // xmm11_4
  float v13; // xmm9_4
  unsigned int v14; // r12d
  int v15; // r14d
  float v16; // xmm10_4
  void (__fastcall *MixedProvider)(int *, __int64, __int64, __int64); // rax
  float v18; // xmm6_4
  float v19; // xmm14_4
  float v20; // xmm7_4
  float v21; // xmm1_4
  float v22; // xmm2_4
  float v23; // xmm3_4
  float v24; // xmm4_4
  float v25; // xmm0_4
  float v26; // xmm5_4
  __int64 i; // r9
  __int64 v28; // r8
  __int16 v29; // ax
  unsigned int v30; // edx
  unsigned __int16 v31; // ax
  __int64 v32; // rdx
  int v33; // r9d
  __int64 v34; // rdx
  _BYTE *v35; // r8
  float v36; // xmm0_4
  float v37; // xmm0_4
  float v38; // xmm0_4
  float v39; // xmm0_4
  unsigned int v40; // ecx
  int v41; // eax
  unsigned __int16 v42; // ax
  int v43; // edx
  __int64 v44; // rcx
  int v45; // eax
  __int64 (__fastcall *v46)(Input::ComprehensiveSkill *, _QWORD, _QWORD); // rax
  __int16 v47; // ax
  unsigned int v48; // edx
  unsigned int v49; // r8d
  __int16 v50; // cx
  unsigned int v51; // edx
  int v52; // ecx
  unsigned int v53; // [rsp+38h] [rbp-D0h]
  float v54; // [rsp+3Ch] [rbp-CCh]
  float v55; // [rsp+40h] [rbp-C8h]
  float v56; // [rsp+44h] [rbp-C4h]
  float v57; // [rsp+48h] [rbp-C0h]
  float v58; // [rsp+4Ch] [rbp-BCh]
  float v59; // [rsp+50h] [rbp-B8h]
  float v60; // [rsp+54h] [rbp-B4h]
  float v61; // [rsp+58h] [rbp-B0h]
  float v62; // [rsp+5Ch] [rbp-ACh]
  int v63; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v64; // [rsp+64h] [rbp-A4h] BYREF
  float X; // [rsp+68h] [rbp-A0h] BYREF
  float v66[3]; // [rsp+6Ch] [rbp-9Ch] BYREF
  int v67; // [rsp+78h] [rbp-90h] BYREF
  int v68; // [rsp+7Ch] [rbp-8Ch]
  int v69; // [rsp+80h] [rbp-88h]
  int v70; // [rsp+84h] [rbp-84h]
  unsigned int v71; // [rsp+88h] [rbp-80h]
  int v72; // [rsp+8Ch] [rbp-7Ch]
  int v73; // [rsp+90h] [rbp-78h]
  unsigned int v74; // [rsp+98h] [rbp-70h]
  unsigned int v75; // [rsp+9Ch] [rbp-6Ch]
  int v76; // [rsp+A0h] [rbp-68h]
  unsigned int v77; // [rsp+A4h] [rbp-64h]
  int v78; // [rsp+A8h] [rbp-60h]
  int v79; // [rsp+ACh] [rbp-5Ch]
  int v80; // [rsp+B0h] [rbp-58h]
  int v81; // [rsp+B4h] [rbp-54h]
  int v82; // [rsp+B8h] [rbp-50h]
  int v83; // [rsp+BCh] [rbp-4Ch]
  int v84; // [rsp+C0h] [rbp-48h]
  unsigned int v85; // [rsp+C4h] [rbp-44h]
  int v86; // [rsp+C8h] [rbp-40h]
  unsigned int v87; // [rsp+CCh] [rbp-3Ch]
  unsigned int v88; // [rsp+D0h] [rbp-38h]
  int v89; // [rsp+D4h] [rbp-34h]
  int v90; // [rsp+D8h] [rbp-30h]
  int v91; // [rsp+DCh] [rbp-2Ch]
  unsigned int v92; // [rsp+E0h] [rbp-28h]
  int v93; // [rsp+E4h] [rbp-24h]
  int v94; // [rsp+E8h] [rbp-20h]
  int v95; // [rsp+ECh] [rbp-1Ch]
  int v96; // [rsp+F0h] [rbp-18h]
  int v97; // [rsp+F4h] [rbp-14h]
  int v98; // [rsp+F8h] [rbp-10h]
  int v99; // [rsp+FCh] [rbp-Ch]
  int v100; // [rsp+100h] [rbp-8h]
  int v101; // [rsp+104h] [rbp-4h]
  int v102; // [rsp+108h] [rbp+0h]
  int v103; // [rsp+10Ch] [rbp+4h]
  int v104; // [rsp+110h] [rbp+8h]
  int v105; // [rsp+114h] [rbp+Ch]
  int v106; // [rsp+118h] [rbp+10h]
  int v107; // [rsp+11Ch] [rbp+14h]
  int v108; // [rsp+120h] [rbp+18h]
  unsigned int v109; // [rsp+124h] [rbp+1Ch]
  unsigned int v110; // [rsp+128h] [rbp+20h]
  int v111; // [rsp+12Ch] [rbp+24h]
  int v112; // [rsp+130h] [rbp+28h]
  unsigned int v113; // [rsp+134h] [rbp+2Ch]
  unsigned int v114; // [rsp+138h] [rbp+30h]
  int v115; // [rsp+13Ch] [rbp+34h]
  unsigned int v116; // [rsp+140h] [rbp+38h]

  v59 = 0.0;
  v53 = 0;
  X = 0.0;
  v66[0] = 0.0;
  v60 = 0.0;
  v58 = 0.0;
  v6 = 0.0;
  v61 = 0.0;
  v7 = 0.0;
  v56 = 0.0;
  v8 = 0;
  v57 = 0.0;
  v9 = 0;
  v55 = 0.0;
  v10 = 0;
  v54 = 0.0;
  v11 = 0.0;
  v62 = 0.0;
  v12 = 0.0;
  v13 = 0.0;
  v14 = 0;
  v15 = 0;
  v16 = 0.0;
  MixedProvider = (void (__fastcall *)(int *, __int64, __int64, __int64))GenerateMixedProvider(
                                                                           0x9FBF3FBF80C020C0uLL,
                                                                           1896136810,
                                                                           a3,
                                                                           a4);
  MixedProvider(&v67, 51, 55337, 15);
  v18 = 0.0;
  v19 = FLOAT_1_0;
  v20 = 0.0;
  v21 = 0.0;
  LOWORD(v63) = 0;
  v22 = 0.0;
  v64 = 0;
  v23 = 0.0;
  v24 = 0.0;
  v25 = 0.0;
  v26 = 0.0;
  for ( i = (unsigned int)(*(&v67 + (unsigned __int16)(-23973 * (v112 + v107)))
                         + *(&v67 + (unsigned int)(v90 - 29964))
                         - 31155);
        ;
        i = (unsigned int)(*(&v67 + 14946 - v88 - v74) + *(&v67 + (unsigned int)(26916 - v67)) - 25573) )
  {
LABEL_2:
    v28 = v53;
    while ( 2 )
    {
      switch ( (int)i )
      {
        case 0:
          v20 = FLOAT_1_25;
          LOWORD(v63) = v9 + v8;
          v9 = 0;
          i = (unsigned __int16)(-18819
                               * *((_WORD *)&v67
                                 + 2
                                 * ((*(&v67 + v92 + v94 - 32056) + *(&v67 + (unsigned __int16)(9751 * v78)))
                                  / 0x1246u)));
          continue;
        case 2:
          Paper::ImportantTopic::AcquireLogicalOperation(40);
          v23 = v59;
          if ( v60 <= v6 )
          {
            v32 = (unsigned int)(*(&v67 + 16657 - v101 - v75) - 22674);
            v33 = *(&v67 + (unsigned int)(*(&v67 + 14119 - v74) - 815)) - 18662;
          }
          else
          {
            v32 = (unsigned int)(11233 - *(&v67 + v113 / 0x599));
            v33 = *(&v67 + (unsigned __int16)(24971 * (v95 + v94))) - 6063;
          }
          i = (unsigned int)(*(&v67 + v32) + v33);
          goto LABEL_6;
        case 3:
          LOWORD(v63) = 30049;
          v14 = v15;
          i = (unsigned __int16)(-23557
                               * (*((_WORD *)&v67
                                  + 2
                                  * (unsigned int)(37626
                                                 - *(&v67 + (unsigned int)(44772 - v80 - v81))
                                                 - *(&v67 + (unsigned int)(445 - v95))))
                                + *((_WORD *)&v67
                                  + 2
                                  * ((*(&v67 + v88 / 0x31) + *(&v67 + (unsigned int)(v115 - 10543 + v102)))
                                   / 0x376u))));
          goto LABEL_2;
        case 5:
          v18 = v18 + v19;
          v6 = 0.0;
          LOWORD(v63) = v63 + 1;
          i = (unsigned __int16)(2764
                               * (*((_WORD *)&v67
                                  + 2
                                  * (unsigned int)(*(&v67 + (unsigned __int16)(-21433 * (v83 + v69)))
                                                 + *(&v67 + (unsigned int)(5290 - v98))
                                                 - 15112))
                                + *((_WORD *)&v67
                                  + 2
                                  * (unsigned __int16)(-26656
                                                     * (*((_WORD *)&v67 + 2 * ((v112 + v87) / 0x455))
                                                      + *((_WORD *)&v67 + 2 * (unsigned __int16)(3234 * (v98 + v71))))))));
          goto LABEL_2;
        case 6:
          v40 = v75;
          v41 = v114 - 23535;
          *((float *)a2 + 276) = v12;
          i = (*(&v67 + 2 * v71 / 0xB3) + *(&v67 + (unsigned __int16)(3907 * *((_WORD *)&v67 + 2 * v41 + 2 * v40))))
            / 0x28Fu;
          goto LABEL_2;
        case 12:
          ++v10;
          i = (*(&v67 + (unsigned int)(44675 - *(&v67 + v74 / 0x3AC) - *(&v67 + v87 / 0x189)))
             + *(&v67
               + (unsigned int)(*(&v67 + v85 + v100 - 15556) - 11861 + *(&v67 + (unsigned int)(31152 - v103 - v101)))))
            / 0xA8u;
          goto LABEL_2;
        case 13:
          LOWORD(v63) = qword_18012A008 - *((_WORD *)a2 + 562);
          v61 = v6 + v23;
          v19 = FLOAT_1_0;
          i = (unsigned int)(*(&v67
                             + *(&v67
                               + (*(&v67 + 10539 - v75) + *(&v67 + *(&v67 + (v84 + v82) / 0x465u) / 0x8E0u)) / 0x9B2u)
                             / 0x405u)
                           + *(&v67 + v114 + v68 - 22611)
                           - 32723);
          goto LABEL_2;
        case 16:
          ++Paper::SlowInformation;
          if ( v22 <= v7 )
            i = (unsigned int)(2316
                             - *(&v67
                               + (unsigned int)(860 - *(&v67 + (unsigned int)(*(&v67 + (v100 + v74) / 0x25A) - 28400)))));
          else
            i = (unsigned __int16)(8285 * *((_WORD *)&v67 + 2 * (*(&v67 + (unsigned int)(25057 - v73 - v96)) / 0x440u)));
          continue;
        case 19:
          Paper::SlowInformation = 15252;
          Paper::LogicalControl = Paper::LogicalControl + v19;
          return;
        case 25:
          LOWORD(v63) = v15 + v9;
          v18 = FLOAT_1_125;
          v20 = Paper::LogicalControl - *((float *)a2 + 280);
          if ( X == 0.0 )
          {
            v16 = FLOAT_1_1754944eN38;
          }
          else
          {
            if ( X < 0.0 )
              v39 = o_sqrtf_0(X);
            else
              v39 = fsqrt(X);
            v16 = v62 / v39;
          }
          v21 = v55;
          v22 = v58;
          v23 = v59;
          v24 = v57;
          v25 = v54;
          v26 = v56;
          v28 = v53;
          i = (unsigned int)(32270 - *(&v67 + (unsigned int)(12832 - *(&v67 + 28758 - v70 - v71))));
          continue;
        case 26:
          v26 = v7 + v23;
          v25 = v54;
          Paper::SlowInformation = (int)(v7 * 0.25);
          v56 = v7 + v23;
          LOWORD(v63) = -(__int16)v28;
          i = (*(&v67 + (unsigned __int16)(-15544 * v105))
             + *(&v67
               + (unsigned __int16)(-2327
                                  * (*((_WORD *)&v67 + 2 * (v116 / 0x5DD))
                                   + *((_WORD *)&v67 + 2 * (unsigned int)(v70 - 29659 + v102))))))
            / 0x1E6u;
          goto LABEL_2;
        case 27:
          v6 = v60;
          Paper::LogicalControl = 3.25;
          i = *(&v67 + (v71 + v73) / 0x1FF) / 0x8Eu;
          goto LABEL_2;
        case 29:
          if ( v15 < 256 )
          {
            i = (unsigned int)(14086
                             - *(&v67
                               + (unsigned __int16)(-1413
                                                  * (*((_WORD *)&v67 + 2 * (*(&v67 + (v93 + v97) / 0x631u) / 0x2F0u))
                                                   + *((_WORD *)&v67
                                                     + 2 * (unsigned int)(21042 - *(&v67 + (v67 + v89) / 0x44Au)))))));
            goto LABEL_2;
          }
          i = (*(&v67 + (unsigned __int16)(-31721 * (v81 + v69)))
             + *(&v67 + (unsigned __int16)(18228 * *((_WORD *)&v67 + 2 * (unsigned __int16)(24996 * v105)))))
            / 0x242u;
          continue;
        case 32:
          v18 = v6 * 0.0;
          LODWORD(v25) = Input::ComprehensiveSkill::OrderDetailedMode<Data::HighDescription<float *>,signed char const *>(
                           (__int64)this,
                           (__int64)a2 + 672,
                           0x180000000uLL + 72LL * v15 + 870432,
                           72).m128_u32[0];
          v22 = v58;
          v23 = v59;
          v24 = v57;
          v26 = v56;
          v21 = v55;
          v54 = v25;
          i = (unsigned int)(46176
                           - *(&v67
                             + (unsigned int)(*(&v67 + v85 / 0x394)
                                            - 25985
                                            + *(&v67
                                              + (unsigned int)(*(&v67 + v71 / 0xB3)
                                                             + *(&v67 + (unsigned __int16)((_WORD)v108 << 15))
                                                             - 55667))))
                           - *(&v67 + (unsigned __int16)(-7564 * v67)));
          goto LABEL_2;
        case 34:
          Paper::SlowInformation = (unsigned __int16)v63 + (unsigned __int16)IntegralRelation::CoordinatedArray;
          if ( v10 >= v15 )
            i = *(&v67 + v109 / 0x3BA) / 0x2A4u;
          else
            i = (unsigned int)(*(&v67 + (unsigned int)(*(&v67 + v75 / 0x32A) + *(&v67 + 48140 - v70 - v92) - 47276))
                             - 7231);
          continue;
        case 35:
          v18 = v13 * v6;
          Paper::ImportantTopic::AcquireLogicalOperation(64);
          v49 = v75;
          v50 = v75 + v83;
          v23 = v59;
          *((_DWORD *)a2 + 282) = (__int16)v8;
          i = (*(&v67 + v49 - 10508)
             + *(&v67
               + (unsigned int)(*(&v67 + (unsigned __int16)(-9516 * v50)) + *(&v67 + (unsigned int)(v82 - 16109))
                                                                          - 16395)))
            / 0x6C1u;
          goto LABEL_6;
        case 40:
          Paper::LogicalControl = v25;
          v18 = v20 - v7;
          v14 = 0;
          LOWORD(v63) = *((_WORD *)a2 + 548) * *((_WORD *)a2 + 550);
          i = (unsigned int)(22814
                           - *(&v67
                             + (unsigned int)(54011
                                            - *(&v67 + (unsigned int)(v83 - 15123 + v115))
                                            - *(&v67 + (unsigned int)(35540 - v76 - v102)))));
          continue;
        case 42:
          v34 = 45LL * v9;
          v18 = *((float *)a2 + 280) - v13;
          v20 = v13 - *((float *)a2 + 279);
          v35 = (char *)&Input::ComprehensiveSkill::OddMessage + v34;
          break;
        case 44:
          v8 = v10;
          --Paper::SlowInformation;
          LOWORD(v63) = v9 * *((_WORD *)a2 + 562);
          i = *(&v67
              + (unsigned int)(22116
                             - *(&v67
                               + (unsigned __int16)(-3107
                                                  * (*((_WORD *)&v67 + 2 * ((v99 + v101) / 0x415u))
                                                   + *((_WORD *)&v67 + 2 * (unsigned __int16)(-23942 * v74)))))
                             - *(&v67 + (unsigned __int16)(943 * (v74 + v70)))))
            / 0x454u;
          goto LABEL_2;
        case 45:
          ++Paper::SlowInformation;
          v22 = v58;
          v23 = v59;
          LODWORD(v24) = Input::ComprehensiveSkill::OrderDetailedMode<Data::HighDescription<float *>,signed char const *>(
                           (__int64)this,
                           (__int64)a2 + 960,
                           (__int64)qword_1800D4800,
                           30).m128_u32[0];
          v57 = v24;
          i = (unsigned int)(18399
                           - *(&v67
                             + (unsigned int)(30378 - *(&v67 + (unsigned int)(3253 - *(&v67 + (v91 + v67) / 0x4CCu)))))
                           - *(&v67 + 50542 - v92 - v78));
          goto LABEL_8;
        case 46:
          v7 = 0.0;
          i = (unsigned int)(32332 - *(&v67 + (unsigned int)(*(&v67 + v102 + v74 - 17315) - 17270)));
          continue;
        case 51:
          LOWORD(v63) = v10 + v63;
          v64 = v28 + (unsigned __int16)v63;
          Paper::LogicalControl = v13 - v26;
          v62 = (float)(v21 + v66[0]) + v24;
          v25 = v54;
          i = (*(&v67 + (unsigned int)(v78 - 28796)) + *(&v67 + *(&v67 + (unsigned int)(25022 - v103)) / 0x396u))
            / 0x935u;
          goto LABEL_2;
        case 52:
          v10 = 0;
          v20 = v60 * *((float *)a2 + 279);
          v64 = qword_18012A008 * *((_DWORD *)a2 + 281);
          i = (unsigned __int16)(8404
                               * (*((_WORD *)&v67 + 2 * (unsigned int)(28441 - *(&v67 + (unsigned int)(v83 - 7777))))
                                + *((_WORD *)&v67
                                  + 2 * (unsigned int)(*(&v67 + v75 - 10492) - 46649 + *(&v67 + v82 + v109 - 30388)))));
          continue;
        case 55:
          Paper::SlowInformation = v8 - v64;
          Paper::SlowInformation = Paper::ImportantTopic::IterateIntegratedLibrary(&v63, 0x87u);
          v23 = v59;
          if ( v9 >= 25 )
            i = *(&v67 + (unsigned int)(*(&v67 + v109 / 0x34A) + *(&v67 + 3356 - v110) - 18412)) / 0x6Au;
          else
            i = (unsigned __int16)(-26182
                                 * *((_WORD *)&v67
                                   + 2 * (unsigned __int16)(3265 * *((_WORD *)&v67 + 2 * (28968 - v84 - v71)))));
          goto LABEL_6;
        case 56:
          v18 = FLOAT_3_75;
          Paper::LogicalControl = 3.125;
          Paper::SlowInformation = 10474;
          v64 = (int)(v13 * 0.0625);
          v23 = v59;
          ++v9;
          Paper::SlowInformation = Paper::ImportantTopic::IterateIntegratedLibrary(&X, 0x1E1u);
          i = (unsigned int)(*(&v67 + 22780 - v86 - v74) - 14337);
          goto LABEL_6;
        case 57:
          v64 = Paper::ImportantTopic::IterateIntegratedLibrary(v66, 0x102u);
          Paper::SlowInformation = v14;
          v23 = v59;
          LODWORD(X) = Input::ComprehensiveSkill::DefineShortTermControl<Data::HighDescription<float *>>(
                         (__int64)this,
                         (__int64)a2,
                         270).m128_u32[0];
          i = (unsigned int)(33769
                           - *(&v67 + (unsigned int)(*(&v67 + v114 / 0x1A4) - 2267))
                           - *(&v67 + (unsigned int)(v108 + v69 - 33082)));
          goto LABEL_6;
        case 58:
          v43 = v93;
          v20 = v7 + v23;
          v44 = (unsigned int)(v101 - 6073);
          v45 = v88 - 29236;
          *((float *)a2 + 278) = v16;
          i = (unsigned int)(*(&v67
                             + (unsigned __int16)(1015
                                                * (*((_WORD *)&v67 + 2 * v44)
                                                 + *((_WORD *)&v67 + 2 * (unsigned int)(v45 + v43)))))
                           - 28940);
          continue;
        case 60:
          v28 = 0;
          v18 = FLOAT_3_875;
          LOWORD(v63) = v15;
          v53 = 0;
          i = (unsigned int)(9682 - *(&v67 + *(&v67 + v74 + v108 - 18172) / 0x2E9Fu));
          continue;
        case 64:
          v21 = 0.0;
          LOWORD(v63) = v63 + 1;
          v55 = 0.0;
          i = (unsigned int)(12065
                           - *(&v67
                             + (unsigned __int16)(11046
                                                * (*((_WORD *)&v67 + 2 * (v110 / 0xDE))
                                                 + *((_WORD *)&v67
                                                   + 2
                                                   * (unsigned __int16)(7518
                                                                      * (*((_WORD *)&v67 + 2 * (v116 / 0x579))
                                                                       + *((_WORD *)&v67 + 2 * ((v75 + v101) / 0x2F5))))))))
                           - *(&v67
                             + (unsigned int)(*(&v67 + (unsigned int)(35758 - v115 - v93))
                                            - 15181
                                            + *(&v67 + (v92 + v104) / 0x46C))));
          goto LABEL_2;
        case 65:
          ++v15;
          i = (unsigned int)(*(&v67
                             + (unsigned int)(12716
                                            - *(&v67 + (unsigned int)(v83 - 30908 + v99))
                                            - *(&v67 + (unsigned int)(v90 - 29960))))
                           + *(&v67 + (unsigned int)(v103 + v111 - 39039))
                           - 35059);
          continue;
        case 66:
          v21 = v21 + v19;
          v51 = v108 + v116;
          v52 = v95;
          *((_DWORD *)a2 + 283) = *((_DWORD *)a2 + 277);
          v55 = v21;
          i = (unsigned int)(*(&v67 + (unsigned int)(16127 - *(&v67 + v51 / 0x5C6)))
                           + *(&v67 + (unsigned int)(v72 + v52 - 13194))
                           - 58611);
          continue;
        case 67:
          Paper::ImportantTopic::AcquireLogicalOperation(19);
          v18 = (float)(v18 - 0.0) - v19;
          v29 = Paper::ImportantTopic::IterateIntegratedLibrary(&v64, 0x264u);
          v30 = v99 + v75;
          v21 = v55;
          v22 = v58;
          v23 = v59;
          v24 = v57;
          v25 = v54;
          v26 = v56;
          LOWORD(v63) = v29;
          v31 = 14791 * (v69 + v90);
          *((_QWORD *)a2 + 138) = 0;
          *((_QWORD *)a2 + 139) = 0;
          *((_DWORD *)a2 + 280) = 0;
          *(_QWORD *)((char *)a2 + 1124) = -1;
          i = (*(&v67
               + (unsigned __int16)(-30225
                                  * (*((_WORD *)&v67 + 2 * (v77 / 0x1AF)) + *((_WORD *)&v67 + 2 * (v30 / 0x2B0)))))
             + *(&v67 + (unsigned int)(23967 - *(&v67 + v31) - *(&v67 + (unsigned int)(9637 - v68)))))
            / 0x143u;
          goto LABEL_2;
        case 68:
          LOWORD(v63) = v10 - v14;
          v8 = 0;
          i = (unsigned int)(8668 - *(&v67 + (unsigned int)(*(&v67 + (v99 + v92) / 0x702) - 29968)));
          continue;
        case 69:
          Paper::LogicalControl = Paper::LogicalControl + -1.0;
          v18 = v22 * 0.03125;
          if ( v11 == 0.0 )
          {
            v12 = FLOAT_1_1754944eN38;
          }
          else
          {
            if ( v11 < 0.0 )
            {
              v37 = o_sqrtf_0(v11);
              v22 = v58;
            }
            else
            {
              v37 = fsqrt(v11);
            }
            v12 = v61 / v37;
          }
          v21 = v55;
          v23 = v59;
          v24 = v57;
          v25 = v54;
          v26 = v56;
          i = (*(&v67 + (unsigned int)(*(&v67 + v92 / 0x2A60) + *(&v67 + (unsigned int)(28462 - v93)) - 37578))
             + *(&v67
               + (unsigned int)(44518
                              - *(&v67 + (unsigned __int16)(6727 * (v97 + v83)))
                              - *(&v67 + (unsigned int)(12777 - v72)))))
            / 0x498u;
          goto LABEL_2;
        case 70:
          LOWORD(v63) = v63 + 2;
          Paper::ImportantTopic::AcquireLogicalOperation(97);
          v23 = v59;
          v42 = 22650 * (v78 + v68);
          *((float *)a2 + 277) = v13;
          i = (unsigned __int16)(-10202 * *((_WORD *)&v67 + 2 * v42));
          goto LABEL_6;
        case 72:
          v64 = Paper::SlowInformation - LODWORD(qword_180129C98[Paper::SlowInformation & 0xF]);
          v23 = v59;
          LODWORD(v66[0]) = Input::ComprehensiveSkill::OrderDetailedMode<Data::HighDescription<float *>,signed char const *>(
                              (__int64)this,
                              (__int64)a2,
                              (__int64)&Input::ComprehensiveSkill::CommonTime,
                              168).m128_u32[0];
          i = (unsigned int)(33701 - *(&v67 + v109 + v75 - 24806) - *(&v67 + (v108 + v84) / 0x329u));
          goto LABEL_6;
        case 73:
          v20 = v25;
          Paper::LogicalControl = 1.75;
          v36 = *((float *)a2 + 283) * 0.5;
          Paper::LogicalControl = v36;
          LODWORD(v22) = Input::ComprehensiveSkill::OrderDetailedMode<Data::HighDescription<float *>,signed char const *>(
                           (__int64)this,
                           (__int64)a2 + 300,
                           (__int64)&Input::ComprehensiveSkill::OptimalSkill + 195 * v10,
                           195).m128_u32[0];
          v23 = v59;
          v58 = v22;
          i = (unsigned int)(8715
                           - *(&v67
                             + (unsigned int)(19398
                                            - *(&v67
                                              + (unsigned int)(22773
                                                             - *(&v67
                                                               + (unsigned __int16)(4084
                                                                                  * *((_WORD *)&v67
                                                                                    + 2 * v101
                                                                                    + 2 * v113
                                                                                    - 46598)))
                                                             - *(&v67 + (unsigned int)(v98 - 5252))))
                                            - *(&v67 + (unsigned int)(v98 - 28362 + v99)))));
          goto LABEL_7;
        case 74:
          v7 = v22;
          v18 = v18 + -1.0;
          v64 = IntegralRelation::CoordinatedArray * v14;
          i = (unsigned __int16)(1300
                               * *((_WORD *)&v67
                                 + 2
                                 * (unsigned __int16)(2275
                                                    * (*((_WORD *)&v67 + 2 * (unsigned int)(v73 - 22702))
                                                     + *((_WORD *)&v67 + 2 * (unsigned __int16)(23304 * (v92 + v90)))))));
          continue;
        case 77:
          Paper::SlowInformation += v9;
          Paper::LogicalControl = v13 * v22;
          Paper::LogicalControl = *((float *)a2 + 278) - v66[0];
          v46 = (__int64 (__fastcall *)(Input::ComprehensiveSkill *, _QWORD, _QWORD))GenerateMixedProvider(
                                                                                       0x9F1FFFBF00E000C0uLL,
                                                                                       1906573418,
                                                                                       v28,
                                                                                       i);
          v47 = v46(this, v53, v14);
          v48 = v75 + v71;
          v23 = v59;
          *((_DWORD *)a2 + 281) = v47;
          i = (unsigned int)(34552
                           - *(&v67 + (unsigned int)(6148 - *(&v67 + (unsigned __int16)(12021 * (v72 + v86)))))
                           - *(&v67 + v48 / 0x283));
          goto LABEL_6;
        case 82:
          v18 = X - *((float *)a2 + 280);
          Paper::ImportantTopic::IterateIntegratedLibrary((char *)a2 + 1100, 0x8Bu);
          Paper::LogicalControl = v57 - v6;
          v64 = Paper::SlowInformation + *((_DWORD *)a2 + 282);
          if ( X == 0.0 )
          {
            v13 = FLOAT_1_1754944eN38;
            v26 = v56;
          }
          else
          {
            if ( X < 0.0 )
              v38 = o_sqrtf_0(X);
            else
              v38 = fsqrt(X);
            v26 = v56;
            v13 = v56 / v38;
          }
          v22 = v58;
          v23 = v59;
          v24 = v57;
          v25 = v54;
          v21 = v55;
          i = (unsigned __int16)(2484
                               * (*((_WORD *)&v67 + 2 * (unsigned int)(*(&v67 + v116 / 0x259) - 2711))
                                + *((_WORD *)&v67
                                  + 2
                                  * (unsigned int)(4361
                                                 - *(&v67
                                                   + (unsigned __int16)(21938
                                                                      * (*((_WORD *)&v67 + 2 * (49710 - v92 - v106))
                                                                       + *((_WORD *)&v67 + 2 * ((v90 + v78) / 0xC17u)))))))));
          goto LABEL_2;
        case 85:
          v18 = v20 - 0.0;
          LODWORD(v23) = Input::ComprehensiveSkill::OrderDetailedMode<Data::HighDescription<float *>,signed char const *>(
                           (__int64)this,
                           (__int64)a2,
                           (__int64)&Input::ComprehensiveSkill::AsyncTime,
                           75).m128_u32[0];
          v59 = v23;
          i = *(&v67 + v113 + v68 - 26813) / 0x13C7u;
          goto LABEL_6;
        case 86:
          Paper::LogicalControl = v18 * v24;
          v23 = v59;
          LODWORD(v60) = Input::ComprehensiveSkill::OrderDetailedMode<Data::HighDescription<float *>,signed char const *>(
                           (__int64)this,
                           (__int64)a2 + 300,
                           (__int64)&Input::ComprehensiveSkill::OddMessage + 45 * v9,
                           45).m128_u32[0];
          i = (*(&v67 + (unsigned int)(*(&v67 + 12830 - v85) - 14068))
             + *(&v67 + (unsigned int)(*(&v67 + v109 / 0x137) - 19017 + *(&v67 + (v69 + v88) / 0x854))))
            / 0x88Au;
          goto LABEL_6;
        case 88:
          v21 = v25;
          v55 = v25;
          i = (unsigned int)(*(&v67
                             + (unsigned __int16)(15762
                                                * (*((_WORD *)&v67 + 2 * (unsigned int)(v83 - 7790))
                                                 + *((_WORD *)&v67 + 2 * ((v90 + v99) / 0x531u)))))
                           + *(&v67 + (unsigned int)(30713 - *(&v67 + (unsigned int)(25792 - v82 - v68))))
                           - 8496);
          goto LABEL_2;
        case 90:
          if ( v25 > v21 )
          {
            i = (unsigned int)(*(&v67
                               + (unsigned int)(*(&v67 + (unsigned __int16)(6876 * v81))
                                              - 19311
                                              + *(&v67 + 34345 - v77 - v99)))
                             + *(&v67 + (v81 + v76) / 0x614u)
                             - 4132);
            goto LABEL_2;
          }
          i = (*(&v67 + v92 - 21690) + *(&v67 + (unsigned int)(v67 - 26865))) / 0xFBu;
          continue;
        case 91:
          v28 = (unsigned int)v9;
          --v64;
          v53 = v9;
          i = (*(&v67 + (unsigned __int16)(-6129 * v84))
             + *(&v67
               + (unsigned int)(49486
                              - *(&v67
                                + (*(&v67 + v113 + v83 - 24995) + *(&v67 + (unsigned __int16)(25119 * (v79 + v68))))
                                / 0x242u)
                              - *(&v67 + (unsigned int)(24998 - *(&v67 + (unsigned int)(v93 - 60649 + v76)))))))
            / 0x2D2u;
          continue;
        case 92:
          if ( *((_WORD *)a2 + 550) )
          {
            if ( v9 >= *((_DWORD *)a2 + 275) )
            {
              if ( v24 == *((float *)a2 + 279) )
                i = (unsigned __int16)(2185 * *((_WORD *)&v67 + 2 * (unsigned int)(*(&v67 + v116 - 20975) - 23126)));
              else
                i = (unsigned int)(*(&v67
                                   + (unsigned __int16)(-914 * *((_WORD *)&v67 + 2 * (unsigned int)(v111 - 14049))))
                                 + *(&v67 + (unsigned int)(2350 - v96))
                                 - 25417);
            }
            else
            {
              i = (unsigned int)(21768 - *(&v67 + (unsigned __int16)(-30822 * v106)));
            }
          }
          else
          {
            i = (*(&v67 + v88 / 0xD0)
               + *(&v67 + (unsigned int)(5530 - *(&v67 + v109 - 14263) - *(&v67 + (unsigned int)(25022 - v103)))))
              / 0x191u;
          }
          continue;
        case 99:
          Paper::SlowInformation = LODWORD(qword_180129C98[Paper::SlowInformation & 0xF]) * v10;
          Paper::ImportantTopic::AcquireLogicalOperation(13);
          LODWORD(v11) = Input::ComprehensiveSkill::DefineShortTermControl<Data::HighDescription<float *>>(
                           (__int64)this,
                           (__int64)a2,
                           120).m128_u32[0];
          v23 = v59;
          i = *(&v67
              + (unsigned int)(4619
                             - *(&v67
                               + (*(&v67 + v104 + v109 - 18608) + *(&v67 + (unsigned int)(v102 - 12828 + v68))) / 0x25Du)
                             - *(&v67 + (unsigned int)(56797 - v106 - v78))))
            / 0x760u;
LABEL_6:
          v22 = v58;
LABEL_7:
          v24 = v57;
LABEL_8:
          v25 = v54;
          v26 = v56;
          v21 = v55;
          goto LABEL_2;
        case 100:
          Paper::SlowInformation = 14479;
          v20 = *((float *)a2 + 283) - Paper::LogicalControl;
          LOWORD(v63) = (int)(v23 * 0.0625);
          if ( v10 < 104 )
          {
            v25 = v54;
            i = *(&v67 + *(&v67 + (unsigned int)(18564 - v91)) / 0x187u) / 0x8Fu;
            continue;
          }
          v25 = v54;
          i = (unsigned __int16)(11604
                               * (*((_WORD *)&v67
                                  + 2
                                  * (unsigned int)(*(&v67 + (unsigned __int16)(347 * (v102 + v98)))
                                                 + *(&v67 + v116 + v95 - 21422)
                                                 - 31774))
                                + *((_WORD *)&v67
                                  + 2
                                  * (unsigned int)(*(&v67
                                                   + (unsigned int)(*(&v67 + (unsigned __int16)(32 * v84))
                                                                  - 26937
                                                                  + *(&v67 + v95 + v87 - 17688)))
                                                 + *(&v67 + (unsigned int)(58380 - v80 - v106))
                                                 - 29354))));
          goto LABEL_2;
        case 102:
          Paper::ImportantTopic::AcquireLogicalOperation(26);
          v21 = v55;
          v22 = v58;
          v23 = v59;
          v15 = 0;
          v24 = v57;
          v25 = v54;
          v26 = v56;
          i = (unsigned int)(17309
                           - *(&v67 + (*(&v67 + (unsigned int)(v86 - 8635)) + *(&v67 + v103 + v114 - 37965)) / 0x532u));
          goto LABEL_2;
        default:
          return;
      }
      break;
    }
    while ( *v35 == v35[(_QWORD)&Input::ComprehensiveSkill::OptimalSkill
                      + 195LL * v10
                      - v34
                      - (_QWORD)&Input::ComprehensiveSkill::OddMessage] )
    {
      if ( ++v35 - ((char *)&Input::ComprehensiveSkill::OddMessage + v34) >= 45 )
      {
        i = (unsigned int)(29135 - *(&v67 + (unsigned int)(v106 + v90 - 57934)));
        goto LABEL_2;
      }
    }
  }
}

```

## disassembly

```asm
0x180020790  mov     rax, rsp
0x180020793  mov     [rax+8], rbx
0x180020797  mov     [rax+18h], rsi
0x18002079b  mov     [rax+20h], rdi
0x18002079f  push    rbp
0x1800207a0  push    r12
0x1800207a2  push    r13
0x1800207a4  push    r14
0x1800207a6  push    r15
0x1800207a8  lea     rbp, [rax-118h]
0x1800207af  sub     rsp, 1F0h
0x1800207b6  movaps  xmmword ptr [rax-38h], xmm6
0x1800207ba  movaps  xmmword ptr [rax-48h], xmm7
0x1800207be  movaps  xmmword ptr [rax-58h], xmm8
0x1800207c3  movaps  xmmword ptr [rax-68h], xmm9
0x1800207c8  movaps  xmmword ptr [rax-78h], xmm10
0x1800207cd  movaps  xmmword ptr [rax-88h], xmm11
0x1800207d5  movaps  xmmword ptr [rax-98h], xmm12
0x1800207dd  movaps  xmmword ptr [rax-0A8h], xmm13
0x1800207e5  movaps  xmmword ptr [rax-0B8h], xmm14
0x1800207ed  movaps  xmmword ptr [rax-0C8h], xmm15
0x1800207f5  mov     rax, cs:__security_cookie
0x1800207fc  xor     rax, rsp
0x1800207ff  mov     [rbp+110h+var_D0], rax
0x180020803  xorps   xmm8, xmm8
0x180020807  mov     rbx, rdx
0x18002080a  xor     edx, edx
0x18002080c  movss   [rsp+210h+var_1C8], xmm8
0x180020813  mov     [rsp+210h+var_1E0], edx
0x180020817  mov     r15, rcx
0x18002081a  mov     [rsp+210h+X], edx
0x18002081e  xorps   xmm1, xmm1
0x180020821  mov     [rsp+210h+var_1AC], edx
0x180020825  mov     rcx, 9FBF3FBF80C020C0h
0x18002082f  mov     edx, 7104C06Ah
0x180020834  movss   [rsp+210h+var_1C4], xmm8
0x18002083b  movss   [rsp+210h+var_1CC], xmm8
0x180020842  xorps   xmm13, xmm13
0x180020846  movss   [rsp+210h+var_1C0], xmm8
0x18002084d  xorps   xmm12, xmm12
0x180020851  movss   [rsp+210h+var_1D4], xmm8
0x180020858  xor     r13d, r13d
0x18002085b  movss   [rsp+210h+var_1D0], xmm1
0x180020861  xor     edi, edi
0x180020863  movss   [rsp+210h+var_1D8], xmm8
0x18002086a  xor     esi, esi
0x18002086c  movss   [rsp+210h+var_1DC], xmm8
0x180020873  xorps   xmm15, xmm15
0x180020877  movss   [rsp+210h+var_1BC], xmm8
0x18002087e  xorps   xmm11, xmm11
0x180020882  xorps   xmm9, xmm9
0x180020886  xor     r12d, r12d
0x180020889  xor     r14d, r14d
0x18002088c  xorps   xmm10, xmm10
0x180020890  call    GenerateMixedProvider
0x180020895  lea     edx, [rdi+33h]
0x180020898  mov     r8d, 0D829h
0x18002089e  lea     r9d, [r13+0Fh]
0x1800208a2  lea     rcx, [rsp+210h+var_1A0]
0x1800208a7  call    cs:__guard_dispatch_icall_fptr
0x1800208ad  mov     ecx, [rbp+110h+var_FC]
0x1800208b0  xor     r11d, r11d
0x1800208b3  add     ecx, [rbp+110h+var_E8]
0x1800208b6  xorps   xmm6, xmm6
0x1800208b9  movss   xmm14, cs:__real@3f800000
0x1800208c2  xorps   xmm7, xmm7
0x1800208c5  imul    eax, ecx, 0FFFFA25Bh
0x1800208cb  xorps   xmm1, xmm1
0x1800208ce  mov     word ptr [rsp+210h+var_1B8], r11w
0x1800208d4  xorps   xmm2, xmm2
0x1800208d7  mov     [rsp+210h+var_1B4], r11d
0x1800208dc  xorps   xmm3, xmm3
0x1800208df  xorps   xmm4, xmm4
0x1800208e2  xorps   xmm0, xmm0
0x1800208e5  xorps   xmm5, xmm5
0x1800208e8  movzx   edx, ax
0x1800208eb  mov     eax, [rbp+110h+var_140]
0x1800208ee  add     eax, 0FFFF8AF4h
0x1800208f3  mov     r9d, [rsp+rax*4+210h+var_1A0]
0x1800208f8  add     r9d, 0FFFF864Dh
0x1800208ff  add     r9d, [rsp+rdx*4+210h+var_1A0]
0x180020904  lea     r10, cs:180000000h
0x18002090b  mov     r8d, [rsp+210h+var_1E0]
0x180020910  lea     rdx, ?OddMessage@ComprehensiveSkill@Input@@0QAY0CN@$$CBCA; signed char const (near * Input::ComprehensiveSkill::OddMessage)[45]
0x180020917  nop     word ptr [rax+rax+00000000h]
0x180020920  cmp     r9d, 66h; switch 103 cases
0x180020924  ja      def_180020941; jumptable 0000000180020941 default case, cases 1,4,7-11,14,15,17,18,20-24,28,30,31,33,36-39,41,43,47-50,53,54,59,61-63,71,75,76,78-81,83,84,87,89,93-98,101
0x18002092a  movsxd  rax, r9d
0x18002092d  movzx   eax, ds:(byte_180022398 - 180000000h)[r10+rax]
0x180020936  mov     ecx, ds:(jpt_180020941 - 180000000h)[r10+rax*4]
0x18002093e  add     rcx, r10
0x180020941  jmp     rcx; switch jump
0x180020943  mov     ecx, 13h; jumptable 0000000180020941 case 67
0x180020948  call    ?AcquireLogicalOperation@ImportantTopic@Paper@@SAXH@Z; Paper::ImportantTopic::AcquireLogicalOperation(int)
0x18002094d  subss   xmm6, xmm8
0x180020952  mov     edx, 264h; unsigned int
0x180020957  lea     rcx, [rsp+210h+var_1B4]; void *
0x18002095c  subss   xmm6, xmm14
0x180020961  call    ?IterateIntegratedLibrary@ImportantTopic@Paper@@SAHPEAXI@Z; Paper::ImportantTopic::IterateIntegratedLibrary(void *,uint)
0x180020966  mov     ecx, [rbp+110h+var_140]
0x180020969  xor     r11d, r11d
0x18002096c  add     ecx, [rsp+210h+var_198]
0x180020970  mov     r9d, 5D9Fh
0x180020976  mov     edx, [rbp+110h+var_17C]
0x180020979  add     edx, [rbp+110h+var_11C]
0x18002097c  movss   xmm1, [rsp+210h+var_1D8]
0x180020982  movss   xmm2, [rsp+210h+var_1CC]
0x180020988  movss   xmm3, [rsp+210h+var_1C8]
0x18002098e  movss   xmm4, [rsp+210h+var_1D0]
0x180020994  movss   xmm0, [rsp+210h+var_1DC]
0x18002099a  movss   xmm5, [rsp+210h+var_1D4]
0x1800209a0  mov     word ptr [rsp+210h+var_1B8], ax
0x1800209a5  imul    eax, ecx, 39C7h
0x1800209ab  mov     [rbx+450h], r11
0x1800209b2  mov     [rbx+458h], r11
0x1800209b9  mov     [rbx+460h], r11d
0x1800209c0  mov     qword ptr [rbx+464h], 0FFFFFFFFFFFFFFFFh
0x1800209cb  movzx   ecx, ax
0x1800209ce  mov     eax, 25A5h
0x1800209d3  sub     eax, [rsp+210h+var_19C]
0x1800209d7  sub     r9d, [rsp+rcx*4+210h+var_1A0]
0x1800209dc  sub     r9d, [rsp+rax*4+210h+var_1A0]
0x1800209e1  mov     eax, 2FA0BE83h
0x1800209e6  mov     ecx, [rbp+110h+var_174]
0x1800209e9  mul     edx
0x1800209eb  mov     r9d, [rsp+r9*4+210h+var_1A0]
0x1800209f0  mov     eax, 301C82ADh
0x1800209f5  shr     edx, 7
0x1800209f8  mov     r8d, edx
0x1800209fb  mul     ecx
0x1800209fd  sub     ecx, edx
0x1800209ff  shr     ecx, 1
0x180020a01  lea     eax, [rdx+rcx]
0x180020a04  mov     ecx, [rsp+r8*4+210h+var_1A0]
0x180020a09  shr     eax, 8
0x180020a0c  add     ecx, [rsp+rax*4+210h+var_1A0]
0x180020a10  imul    eax, ecx, 0FFFF89EFh
0x180020a16  movzx   ecx, ax
0x180020a19  mov     eax, 95CBB0BFh
0x180020a1e  add     r9d, [rsp+rcx*4+210h+var_1A0]
0x180020a23  mul     r9d
0x180020a26  sub     r9d, edx
0x180020a29  shr     r9d, 1
0x180020a2c  add     r9d, edx
0x180020a2f  shr     r9d, 8
0x180020a33  jmp     loc_180020904
0x180020a38  movaps  xmm6, xmm7; jumptable 0000000180020941 case 85
0x180020a3b  lea     r8, ?AsyncTime@ComprehensiveSkill@Input@@0QBCB; signed char const near * const Input::ComprehensiveSkill::AsyncTime
0x180020a42  mov     r9d, 4Bh ; 'K'
0x180020a48  subss   xmm6, xmm8
0x180020a4d  mov     rdx, rbx
0x180020a50  mov     rcx, r15
0x180020a53  call    ??$OrderDetailedMode@V?$HighDescription@PEAM@Data@@PEBC@ComprehensiveSkill@Input@@QEBAMV?$HighDescription@PEAM@Data@@PEBCH@Z; Input::ComprehensiveSkill::OrderDetailedMode<Data::HighDescription<float *>,signed char const *>(Data::HighDescription<float *>,signed char const *,int)
0x180020a58  mov     ecx, [rsp+210h+var_19C]
0x180020a5c  movaps  xmm3, xmm0
0x180020a5f  mov     eax, [rbp+110h+var_E4]
0x180020a62  add     eax, 0FFFF9743h
0x180020a67  movss   [rsp+210h+var_1C8], xmm0
0x180020a6d  add     ecx, eax
0x180020a6f  mov     eax, 0CF1B0D19h
0x180020a74  mul     [rsp+rcx*4+210h+var_1A0]
0x180020a78  mov     r9d, edx
0x180020a7b  shr     r9d, 0Ch
0x180020a7f  movss   xmm2, [rsp+210h+var_1CC]
0x180020a85  movss   xmm4, [rsp+210h+var_1D0]
0x180020a8b  movss   xmm0, [rsp+210h+var_1DC]
0x180020a91  xor     r11d, r11d
0x180020a94  movss   xmm5, [rsp+210h+var_1D4]
0x180020a9a  movss   xmm1, [rsp+210h+var_1D8]
0x180020aa0  jmp     loc_180020904
0x180020aa5  mov     eax, [rbp+110h+var_190]; jumptable 0000000180020941 case 5
0x180020aa8  addss   xmm6, xmm14
0x180020aad  add     eax, [rbp+110h+var_120]
0x180020ab0  movaps  xmm13, xmm8
0x180020ab4  mov     edx, [rbp+110h+var_14C]
0x180020ab7  add     edx, [rbp+110h+var_E8]
0x180020aba  inc     word ptr [rsp+210h+var_1B8]
0x180020abf  imul    ecx, eax, 0CA2h
0x180020ac5  mov     eax, 3B183CF1h
0x180020aca  mul     edx
0x180020acc  movzx   r8d, cx
0x180020ad0  shr     edx, 8
0x180020ad3  mov     ecx, [rsp+r8*4+210h+var_1A0]
0x180020ad8  add     ecx, [rsp+rdx*4+210h+var_1A0]
0x180020adc  imul    eax, ecx, 0FFFF97E0h
0x180020ae2  mov     ecx, [rsp+210h+var_198]
0x180020ae6  add     ecx, [rbp+110h+var_15C]
0x180020ae9  movzx   r8d, ax
0x180020aed  imul    eax, ecx, 0FFFFAC47h
0x180020af3  mov     ecx, [rsp+r8*4+210h+var_1A0]
0x180020af8  movzx   edx, ax
0x180020afb  mov     eax, 14AAh
0x180020b00  sub     eax, [rbp+110h+var_120]
0x180020b03  mov     eax, [rsp+rax*4+210h+var_1A0]
0x180020b07  add     eax, 0FFFFC4F8h
0x180020b0c  add     eax, [rsp+rdx*4+210h+var_1A0]
0x180020b10  add     ecx, [rsp+rax*4+210h+var_1A0]
0x180020b14  imul    eax, ecx, 0ACCh
0x180020b1a  movzx   r9d, ax
0x180020b1e  jmp     loc_18002090B
0x180020b23  mov     ecx, [rbp+110h+var_F8]; jumptable 0000000180020941 case 60
0x180020b26  mov     r9d, 25D2h
0x180020b2c  mov     eax, [rbp+110h+var_180]
0x180020b2f  mov     r8d, r11d
0x180020b32  movss   xmm6, cs:__real@40780000
0x180020b3a  add     eax, 0FFFFB904h
0x180020b3f  add     ecx, eax
0x180020b41  mov     word ptr [rsp+210h+var_1B8], r14w
0x180020b47  mov     eax, 5F6DCCD3h
0x180020b4c  mov     [rsp+210h+var_1E0], r11d
0x180020b51  mov     ecx, [rsp+rcx*4+210h+var_1A0]
0x180020b55  mul     ecx
0x180020b57  sub     ecx, edx
0x180020b59  shr     ecx, 1
0x180020b5b  add     ecx, edx
0x180020b5d  shr     ecx, 0Dh
0x180020b60  sub     r9d, [rsp+rcx*4+210h+var_1A0]
0x180020b65  jmp     loc_180020910
0x180020b6a  mov     ecx, [rbp+110h+var_180]; jumptable 0000000180020941 case 46
0x180020b6d  mov     r9d, 7E4Ch
0x180020b73  add     ecx, 0FFFFBC5Dh
0x180020b79  movaps  xmm12, xmm8
0x180020b7d  add     ecx, [rbp+110h+var_110]
0x180020b80  mov     ecx, [rsp+rcx*4+210h+var_1A0]
0x180020b84  sub     ecx, 4376h
0x180020b8a  sub     r9d, [rsp+rcx*4+210h+var_1A0]
0x180020b8f  jmp     loc_180020920
0x180020b94  mov     edx, [rbp+110h+var_138]; jumptable 0000000180020941 case 68
0x180020b97  movzx   eax, si
0x180020b9a  add     edx, [rbp+110h+var_11C]
0x180020b9d  sub     ax, r12w
0x180020ba1  mov     word ptr [rsp+210h+var_1B8], ax
0x180020ba6  mov     r9d, 21DCh
0x180020bac  mov     eax, 921F64BFh
0x180020bb1  mov     r13d, r11d
0x180020bb4  mul     edx
0x180020bb6  shr     edx, 0Ah
0x180020bb9  mov     ecx, [rsp+rdx*4+210h+var_1A0]
0x180020bbd  sub     ecx, 7510h
0x180020bc3  sub     r9d, [rsp+rcx*4+210h+var_1A0]
0x180020bc8  jmp     loc_180020910
0x180020bcd  mov     ecx, [rbp+110h+var_138]; jumptable 0000000180020941 case 0
0x180020bd0  lea     eax, [rdi+r13]
0x180020bd4  movss   xmm7, cs:__real@3fa00000
0x180020bdc  add     ecx, 0FFFF82C8h
0x180020be2  mov     word ptr [rsp+210h+var_1B8], ax
0x180020be7  mov     edi, r11d
0x180020bea  imul    eax, [rbp+110h+var_170], 2617h
0x180020bf1  movzx   edx, ax
0x180020bf4  mov     eax, [rbp+110h+var_130]
0x180020bf7  add     eax, ecx
0x180020bf9  mov     ecx, [rsp+rdx*4+210h+var_1A0]
0x180020bfd  add     ecx, [rsp+rax*4+210h+var_1A0]
0x180020c01  mov     eax, 7013435h
0x180020c06  mul     ecx
0x180020c08  shr     edx, 7
0x180020c0b  imul    ecx, [rsp+rdx*4+210h+var_1A0], 0FFFFB67Dh
0x180020c13  movzx   r9d, cx
0x180020c17  jmp     loc_180020910
0x180020c1c  mov     eax, r13d; jumptable 0000000180020941 case 55
0x180020c1f  lea     rcx, [rsp+210h+var_1B8]; void *
0x180020c24  sub     eax, [rsp+210h+var_1B4]
0x180020c28  mov     edx, 87h; unsigned int
0x180020c2d  mov     cs:?SlowInformation@Paper@@3IA, eax; uint Paper::SlowInformation
0x180020c33  call    ?IterateIntegratedLibrary@ImportantTopic@Paper@@SAHPEAXI@Z; Paper::ImportantTopic::IterateIntegratedLibrary(void *,uint)
0x180020c38  mov     cs:?SlowInformation@Paper@@3IA, eax; uint Paper::SlowInformation
0x180020c3e  cmp     edi, 19h
0x180020c41  jge     short loc_180020C70
0x180020c43  movss   xmm3, [rsp+210h+var_1C8]
0x180020c49  mov     eax, 7128h
0x180020c4e  sub     eax, [rbp+110h+var_158]
0x180020c51  sub     eax, [rbp+110h+var_190]
0x180020c54  imul    ecx, [rsp+rax*4+210h+var_1A0], 0CC1h
0x180020c5c  movzx   eax, cx
0x180020c5f  imul    ecx, [rsp+rax*4+210h+var_1A0], 0FFFF99BAh
0x180020c67  movzx   r9d, cx
0x180020c6b  jmp     loc_180020A7F
0x180020c70  mov     ecx, [rbp+110h+var_F4]
0x180020c73  mov     eax, 3755BD1Dh
0x180020c78  movss   xmm3, [rsp+210h+var_1C8]
0x180020c7e  mul     ecx
0x180020c80  mov     eax, 0D1Ch
0x180020c85  sub     eax, [rbp+110h+var_F0]
0x180020c88  sub     ecx, edx
0x180020c8a  shr     ecx, 1
0x180020c8c  add     edx, ecx
0x180020c8e  shr     edx, 9
0x180020c91  mov     ecx, [rsp+rax*4+210h+var_1A0]
0x180020c95  mov     eax, 3521CFB3h
0x180020c9a  add     ecx, 0FFFFB814h
0x180020ca0  add     ecx, [rsp+rdx*4+210h+var_1A0]
0x180020ca4  mov     r9d, [rsp+rcx*4+210h+var_1A0]
0x180020ca9  mul     r9d
0x180020cac  sub     r9d, edx
0x180020caf  shr     r9d, 1
0x180020cb2  add     r9d, edx
0x180020cb5  shr     r9d, 6
0x180020cb9  jmp     loc_180020A7F
0x180020cbe  movsxd  rax, edi; jumptable 0000000180020941 case 86
0x180020cc1  movaps  xmm0, xmm6
  ... truncated ...
```
