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
        __int64 a3)
{
  float v5; // xmm13_4
  float v6; // xmm12_4
  int v7; // r13d
  int v8; // edi
  int v9; // esi
  float v10; // xmm15_4
  float v11; // xmm11_4
  float v12; // xmm9_4
  unsigned int v13; // r12d
  int v14; // r14d
  float v15; // xmm10_4
  void (__fastcall *MixedProvider)(int *, __int64, __int64, __int64); // rax
  float v17; // xmm6_4
  float v18; // xmm14_4
  float v19; // xmm7_4
  float v20; // xmm1_4
  float v21; // xmm2_4
  float v22; // xmm3_4
  float v23; // xmm4_4
  double v24; // xmm0_8
  float v25; // xmm5_4
  unsigned int i; // r9d
  __int64 v27; // r8
  __int16 v28; // ax
  unsigned int v29; // edx
  unsigned __int16 v30; // ax
  double v31; // xmm0_8
  double v32; // xmm0_8
  __int64 v33; // rdx
  int v34; // r9d
  __int64 v35; // rdx
  _BYTE *v36; // r8
  float v37; // xmm0_4
  double v38; // xmm0_8
  double v39; // xmm0_8
  float v40; // xmm0_4
  double v41; // xmm0_8
  float v42; // xmm0_4
  double v43; // xmm0_8
  double v44; // xmm0_8
  float v45; // xmm0_4
  unsigned int v46; // ecx
  int v47; // eax
  unsigned __int16 v48; // ax
  int v49; // edx
  __int64 v50; // rcx
  int v51; // eax
  __int64 (__fastcall *v52)(Input::ComprehensiveSkill *, _QWORD, _QWORD); // rax
  __int16 v53; // ax
  unsigned int v54; // edx
  unsigned int v55; // r8d
  __int16 v56; // cx
  unsigned int v57; // edx
  int v58; // ecx
  unsigned int v59; // [rsp+38h] [rbp-D0h]
  int v60; // [rsp+3Ch] [rbp-CCh]
  float v61; // [rsp+40h] [rbp-C8h]
  float v62; // [rsp+44h] [rbp-C4h]
  float v63; // [rsp+48h] [rbp-C0h]
  float v64; // [rsp+4Ch] [rbp-BCh]
  float v65; // [rsp+50h] [rbp-B8h]
  float v66; // [rsp+54h] [rbp-B4h]
  float v67; // [rsp+58h] [rbp-B0h]
  float v68; // [rsp+5Ch] [rbp-ACh]
  int v69; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v70; // [rsp+64h] [rbp-A4h] BYREF
  float X; // [rsp+68h] [rbp-A0h] BYREF
  float v72[3]; // [rsp+6Ch] [rbp-9Ch] BYREF
  int v73; // [rsp+78h] [rbp-90h] BYREF
  int v74; // [rsp+7Ch] [rbp-8Ch]
  int v75; // [rsp+80h] [rbp-88h]
  int v76; // [rsp+84h] [rbp-84h]
  unsigned int v77; // [rsp+88h] [rbp-80h]
  int v78; // [rsp+8Ch] [rbp-7Ch]
  int v79; // [rsp+90h] [rbp-78h]
  unsigned int v80; // [rsp+98h] [rbp-70h]
  unsigned int v81; // [rsp+9Ch] [rbp-6Ch]
  int v82; // [rsp+A0h] [rbp-68h]
  unsigned int v83; // [rsp+A4h] [rbp-64h]
  int v84; // [rsp+A8h] [rbp-60h]
  int v85; // [rsp+ACh] [rbp-5Ch]
  int v86; // [rsp+B0h] [rbp-58h]
  int v87; // [rsp+B4h] [rbp-54h]
  int v88; // [rsp+B8h] [rbp-50h]
  int v89; // [rsp+BCh] [rbp-4Ch]
  int v90; // [rsp+C0h] [rbp-48h]
  unsigned int v91; // [rsp+C4h] [rbp-44h]
  int v92; // [rsp+C8h] [rbp-40h]
  unsigned int v93; // [rsp+CCh] [rbp-3Ch]
  unsigned int v94; // [rsp+D0h] [rbp-38h]
  int v95; // [rsp+D4h] [rbp-34h]
  int v96; // [rsp+D8h] [rbp-30h]
  int v97; // [rsp+DCh] [rbp-2Ch]
  unsigned int v98; // [rsp+E0h] [rbp-28h]
  int v99; // [rsp+E4h] [rbp-24h]
  int v100; // [rsp+E8h] [rbp-20h]
  int v101; // [rsp+ECh] [rbp-1Ch]
  int v102; // [rsp+F0h] [rbp-18h]
  int v103; // [rsp+F4h] [rbp-14h]
  int v104; // [rsp+F8h] [rbp-10h]
  int v105; // [rsp+FCh] [rbp-Ch]
  int v106; // [rsp+100h] [rbp-8h]
  int v107; // [rsp+104h] [rbp-4h]
  int v108; // [rsp+108h] [rbp+0h]
  int v109; // [rsp+10Ch] [rbp+4h]
  int v110; // [rsp+110h] [rbp+8h]
  int v111; // [rsp+114h] [rbp+Ch]
  int v112; // [rsp+118h] [rbp+10h]
  int v113; // [rsp+11Ch] [rbp+14h]
  int v114; // [rsp+120h] [rbp+18h]
  unsigned int v115; // [rsp+124h] [rbp+1Ch]
  unsigned int v116; // [rsp+128h] [rbp+20h]
  int v117; // [rsp+12Ch] [rbp+24h]
  int v118; // [rsp+130h] [rbp+28h]
  unsigned int v119; // [rsp+134h] [rbp+2Ch]
  unsigned int v120; // [rsp+138h] [rbp+30h]
  int v121; // [rsp+13Ch] [rbp+34h]
  unsigned int v122; // [rsp+140h] [rbp+38h]

  v65 = 0.0;
  v59 = 0;
  X = 0.0;
  v72[0] = 0.0;
  v66 = 0.0;
  v64 = 0.0;
  v5 = 0.0;
  v67 = 0.0;
  v6 = 0.0;
  v62 = 0.0;
  v7 = 0;
  v63 = 0.0;
  v8 = 0;
  v61 = 0.0;
  v9 = 0;
  v60 = 0;
  v10 = 0.0;
  v68 = 0.0;
  v11 = 0.0;
  v12 = 0.0;
  v13 = 0;
  v14 = 0;
  v15 = 0.0;
  MixedProvider = (void (__fastcall *)(int *, __int64, __int64, __int64))GenerateMixedProvider(
                                                                           0x9FBF3FBF80C020C0uLL,
                                                                           1896136810,
                                                                           a3);
  MixedProvider(&v73, 51, 55337, 15);
  v17 = 0.0;
  v18 = FLOAT_1_0;
  v19 = 0.0;
  v20 = 0.0;
  LOWORD(v69) = 0;
  v21 = 0.0;
  v70 = 0;
  v22 = 0.0;
  v23 = 0.0;
  LODWORD(v24) = 0;
  v25 = 0.0;
  for ( i = *(&v73 + (unsigned __int16)(-23973 * (v118 + v113))) + *(&v73 + (unsigned int)(v96 - 29964)) - 31155;
        ;
        i = *(&v73 + 14946 - v94 - v80) + *(&v73 + (unsigned int)(26916 - v73)) - 25573 )
  {
LABEL_2:
    v27 = v59;
    while ( 2 )
    {
      switch ( i )
      {
        case 0u:
          v19 = FLOAT_1_25;
          LOWORD(v69) = v8 + v7;
          v8 = 0;
          i = (unsigned __int16)(-18819
                               * *((_WORD *)&v73
                                 + 2
                                 * ((*(&v73 + v98 + v100 - 32056) + *(&v73 + (unsigned __int16)(9751 * v84)))
                                  / 0x1246u)));
          continue;
        case 2u:
          Paper::ImportantTopic::AcquireLogicalOperation(40);
          v22 = v65;
          if ( v66 <= v5 )
          {
            v33 = (unsigned int)(*(&v73 + 16657 - v107 - v81) - 22674);
            v34 = *(&v73 + (unsigned int)(*(&v73 + 14119 - v80) - 815)) - 18662;
          }
          else
          {
            v33 = (unsigned int)(11233 - *(&v73 + v119 / 0x599));
            v34 = *(&v73 + (unsigned __int16)(24971 * (v101 + v100))) - 6063;
          }
          i = *(&v73 + v33) + v34;
          goto LABEL_6;
        case 3u:
          LOWORD(v69) = 30049;
          v13 = v14;
          i = (unsigned __int16)(-23557
                               * (*((_WORD *)&v73
                                  + 2
                                  * (unsigned int)(37626
                                                 - *(&v73 + (unsigned int)(44772 - v86 - v87))
                                                 - *(&v73 + (unsigned int)(445 - v101))))
                                + *((_WORD *)&v73
                                  + 2
                                  * ((*(&v73 + v94 / 0x31) + *(&v73 + (unsigned int)(v121 - 10543 + v108)))
                                   / 0x376u))));
          goto LABEL_2;
        case 5u:
          v17 = v17 + v18;
          v5 = 0.0;
          LOWORD(v69) = v69 + 1;
          i = (unsigned __int16)(2764
                               * (*((_WORD *)&v73
                                  + 2
                                  * (unsigned int)(*(&v73 + (unsigned __int16)(-21433 * (v89 + v75)))
                                                 + *(&v73 + (unsigned int)(5290 - v104))
                                                 - 15112))
                                + *((_WORD *)&v73
                                  + 2
                                  * (unsigned __int16)(-26656
                                                     * (*((_WORD *)&v73 + 2 * ((v118 + v93) / 0x455))
                                                      + *((_WORD *)&v73 + 2 * (unsigned __int16)(3234 * (v104 + v77))))))));
          goto LABEL_2;
        case 6u:
          v46 = v81;
          v47 = v120 - 23535;
          *((float *)a2 + 276) = v11;
          i = (*(&v73 + 2 * v77 / 0xB3) + *(&v73 + (unsigned __int16)(3907 * *((_WORD *)&v73 + 2 * v47 + 2 * v46))))
            / 0x28Fu;
          goto LABEL_2;
        case 0xCu:
          ++v9;
          i = (*(&v73 + (unsigned int)(44675 - *(&v73 + v80 / 0x3AC) - *(&v73 + v93 / 0x189)))
             + *(&v73
               + (unsigned int)(*(&v73 + v91 + v106 - 15556) - 11861 + *(&v73 + (unsigned int)(31152 - v109 - v107)))))
            / 0xA8u;
          goto LABEL_2;
        case 0xDu:
          LOWORD(v69) = qword_18012A008 - *((_WORD *)a2 + 562);
          v67 = v5 + v22;
          v18 = FLOAT_1_0;
          i = *(&v73
              + *(&v73 + (*(&v73 + 10539 - v81) + *(&v73 + *(&v73 + (v90 + v88) / 0x465u) / 0x8E0u)) / 0x9B2u) / 0x405u)
            + *(&v73 + v120 + v74 - 22611)
            - 32723;
          goto LABEL_2;
        case 0x10u:
          ++Paper::SlowInformation;
          if ( v21 <= v6 )
            i = 2316 - *(&v73 + (unsigned int)(860 - *(&v73 + (unsigned int)(*(&v73 + (v106 + v80) / 0x25A) - 28400))));
          else
            i = (unsigned __int16)(8285 * *((_WORD *)&v73 + 2 * (*(&v73 + (unsigned int)(25057 - v79 - v102)) / 0x440u)));
          continue;
        case 0x13u:
          Paper::SlowInformation = 15252;
          Paper::LogicalControl = Paper::LogicalControl + v18;
          return;
        case 0x19u:
          LOWORD(v69) = v14 + v8;
          v17 = FLOAT_1_125;
          v19 = Paper::LogicalControl - *((float *)a2 + 280);
          if ( X == 0.0 )
          {
            v15 = FLOAT_1_1754944eN38;
          }
          else
          {
            if ( X < 0.0 )
              v45 = o_sqrtf_0(X);
            else
              v45 = fsqrt(X);
            v15 = v68 / v45;
          }
          v20 = v61;
          v21 = v64;
          v22 = v65;
          v23 = v63;
          LODWORD(v24) = v60;
          v25 = v62;
          v27 = v59;
          i = 32270 - *(&v73 + (unsigned int)(12832 - *(&v73 + 28758 - v76 - v77)));
          continue;
        case 0x1Au:
          v25 = v6 + v22;
          LODWORD(v24) = v60;
          Paper::SlowInformation = (int)(v6 * 0.25);
          v62 = v6 + v22;
          LOWORD(v69) = -(__int16)v27;
          i = (*(&v73 + (unsigned __int16)(-15544 * v111))
             + *(&v73
               + (unsigned __int16)(-2327
                                  * (*((_WORD *)&v73 + 2 * (v122 / 0x5DD))
                                   + *((_WORD *)&v73 + 2 * (unsigned int)(v76 - 29659 + v108))))))
            / 0x1E6u;
          goto LABEL_2;
        case 0x1Bu:
          v5 = v66;
          Paper::LogicalControl = 3.25;
          i = *(&v73 + (v77 + v79) / 0x1FF) / 0x8Eu;
          goto LABEL_2;
        case 0x1Du:
          if ( v14 < 256 )
          {
            i = 14086
              - *(&v73
                + (unsigned __int16)(-1413
                                   * (*((_WORD *)&v73 + 2 * (*(&v73 + (v99 + v103) / 0x631u) / 0x2F0u))
                                    + *((_WORD *)&v73 + 2 * (unsigned int)(21042 - *(&v73 + (v73 + v95) / 0x44Au))))));
            goto LABEL_2;
          }
          i = (*(&v73 + (unsigned __int16)(-31721 * (v87 + v75)))
             + *(&v73 + (unsigned __int16)(18228 * *((_WORD *)&v73 + 2 * (unsigned __int16)(24996 * v111)))))
            / 0x242u;
          continue;
        case 0x20u:
          v17 = v5 * 0.0;
          v24 = Input::ComprehensiveSkill::OrderDetailedMode<Data::HighDescription<float *>,signed char const *>(
                  this,
                  (char *)a2 + 672,
                  0x180000000LL + 72LL * v14 + 870432,
                  72);
          v21 = v64;
          v22 = v65;
          v23 = v63;
          v25 = v62;
          v20 = v61;
          v60 = LODWORD(v24);
          i = 46176
            - *(&v73
              + (unsigned int)(*(&v73 + v91 / 0x394)
                             - 25985
                             + *(&v73
                               + (unsigned int)(*(&v73 + v77 / 0xB3)
                                              + *(&v73 + (unsigned __int16)((_WORD)v114 << 15))
                                              - 55667))))
            - *(&v73 + (unsigned __int16)(-7564 * v73));
          goto LABEL_2;
        case 0x22u:
          Paper::SlowInformation = (unsigned __int16)v69 + (unsigned __int16)IntegralRelation::CoordinatedArray;
          if ( v9 >= v14 )
            i = *(&v73 + v115 / 0x3BA) / 0x2A4u;
          else
            i = *(&v73 + (unsigned int)(*(&v73 + v81 / 0x32A) + *(&v73 + 48140 - v76 - v98) - 47276)) - 7231;
          continue;
        case 0x23u:
          v17 = v12 * v5;
          Paper::ImportantTopic::AcquireLogicalOperation(64);
          v55 = v81;
          v56 = v81 + v89;
          v22 = v65;
          *((_DWORD *)a2 + 282) = (__int16)v7;
          i = (*(&v73 + v55 - 10508)
             + *(&v73
               + (unsigned int)(*(&v73 + (unsigned __int16)(-9516 * v56)) + *(&v73 + (unsigned int)(v88 - 16109))
                                                                          - 16395)))
            / 0x6C1u;
          goto LABEL_6;
        case 0x28u:
          Paper::LogicalControl = *(float *)&v24;
          v17 = v19 - v6;
          v13 = 0;
          LOWORD(v69) = *((_WORD *)a2 + 548) * *((_WORD *)a2 + 550);
          i = 22814
            - *(&v73
              + (unsigned int)(54011
                             - *(&v73 + (unsigned int)(v89 - 15123 + v121))
                             - *(&v73 + (unsigned int)(35540 - v82 - v108))));
          continue;
        case 0x2Au:
          v35 = 45LL * v8;
          v17 = *((float *)a2 + 280) - v12;
          v19 = v12 - *((float *)a2 + 279);
          v36 = (char *)&Input::ComprehensiveSkill::OddMessage + v35;
          break;
        case 0x2Cu:
          v7 = v9;
          --Paper::SlowInformation;
          LOWORD(v69) = v8 * *((_WORD *)a2 + 562);
          i = *(&v73
              + (unsigned int)(22116
                             - *(&v73
                               + (unsigned __int16)(-3107
                                                  * (*((_WORD *)&v73 + 2 * ((v105 + v107) / 0x415u))
                                                   + *((_WORD *)&v73 + 2 * (unsigned __int16)(-23942 * v80)))))
                             - *(&v73 + (unsigned __int16)(943 * (v80 + v76)))))
            / 0x454u;
          goto LABEL_2;
        case 0x2Du:
          ++Paper::SlowInformation;
          v44 = Input::ComprehensiveSkill::OrderDetailedMode<Data::HighDescription<float *>,signed char const *>(
                  this,
                  (char *)a2 + 960,
                  qword_1800D4800,
                  30);
          v21 = v64;
          v22 = v65;
          v23 = *(float *)&v44;
          v63 = *(float *)&v44;
          i = 18399
            - *(&v73 + (unsigned int)(30378 - *(&v73 + (unsigned int)(3253 - *(&v73 + (v97 + v73) / 0x4CCu)))))
            - *(&v73 + 50542 - v98 - v84);
          goto LABEL_8;
        case 0x2Eu:
          v6 = 0.0;
          i = 32332 - *(&v73 + (unsigned int)(*(&v73 + v108 + v80 - 17315) - 17270));
          continue;
        case 0x33u:
          LOWORD(v69) = v9 + v69;
          v70 = v27 + (unsigned __int16)v69;
          Paper::LogicalControl = v12 - v25;
          v68 = (float)(v20 + v72[0]) + v23;
          LODWORD(v24) = v60;
          i = (*(&v73 + (unsigned int)(v84 - 28796)) + *(&v73 + *(&v73 + (unsigned int)(25022 - v109)) / 0x396u))
            / 0x935u;
          goto LABEL_2;
        case 0x34u:
          v9 = 0;
          v19 = v66 * *((float *)a2 + 279);
          v70 = qword_18012A008 * *((_DWORD *)a2 + 281);
          i = (unsigned __int16)(8404
                               * (*((_WORD *)&v73 + 2 * (unsigned int)(28441 - *(&v73 + (unsigned int)(v89 - 7777))))
                                + *((_WORD *)&v73
                                  + 2 * (unsigned int)(*(&v73 + v81 - 10492) - 46649 + *(&v73 + v88 + v115 - 30388)))));
          continue;
        case 0x37u:
          Paper::SlowInformation = v7 - v70;
          Paper::SlowInformation = Paper::ImportantTopic::IterateIntegratedLibrary(&v69, 0x87u);
          v22 = v65;
          if ( v8 >= 25 )
            i = *(&v73 + (unsigned int)(*(&v73 + v115 / 0x34A) + *(&v73 + 3356 - v116) - 18412)) / 0x6Au;
          else
            i = (unsigned __int16)(-26182
                                 * *((_WORD *)&v73
                                   + 2 * (unsigned __int16)(3265 * *((_WORD *)&v73 + 2 * (28968 - v90 - v77)))));
          goto LABEL_6;
        case 0x38u:
          v17 = FLOAT_3_75;
          Paper::LogicalControl = 3.125;
          Paper::SlowInformation = 10474;
          v70 = (int)(v12 * 0.0625);
          v22 = v65;
          ++v8;
          Paper::SlowInformation = Paper::ImportantTopic::IterateIntegratedLibrary(&X, 0x1E1u);
          i = *(&v73 + 22780 - v92 - v80) - 14337;
          goto LABEL_6;
        case 0x39u:
          v70 = Paper::ImportantTopic::IterateIntegratedLibrary(v72, 0x102u);
          Paper::SlowInformation = v13;
          v41 = Input::ComprehensiveSkill::DefineShortTermControl<Data::HighDescription<float *>>(this, a2, 270);
          v22 = v65;
          X = *(float *)&v41;
          i = 33769
            - *(&v73 + (unsigned int)(*(&v73 + v120 / 0x1A4) - 2267))
            - *(&v73 + (unsigned int)(v114 + v75 - 33082));
          goto LABEL_6;
        case 0x3Au:
          v49 = v99;
          v19 = v6 + v22;
          v50 = (unsigned int)(v107 - 6073);
          v51 = v94 - 29236;
          *((float *)a2 + 278) = v15;
          i = *(&v73
              + (unsigned __int16)(1015 * (*((_WORD *)&v73 + 2 * v50) + *((_WORD *)&v73 + 2 * (unsigned int)(v51 + v49)))))
            - 28940;
          continue;
        case 0x3Cu:
          v27 = 0;
          v17 = FLOAT_3_875;
          LOWORD(v69) = v14;
          v59 = 0;
          i = 9682 - *(&v73 + *(&v73 + v80 + v114 - 18172) / 0x2E9Fu);
          continue;
        case 0x40u:
          v20 = 0.0;
          LOWORD(v69) = v69 + 1;
          v61 = 0.0;
          i = 12065
            - *(&v73
              + (unsigned __int16)(11046
                                 * (*((_WORD *)&v73 + 2 * (v116 / 0xDE))
                                  + *((_WORD *)&v73
                                    + 2
                                    * (unsigned __int16)(7518
                                                       * (*((_WORD *)&v73 + 2 * (v122 / 0x579))
                                                        + *((_WORD *)&v73 + 2 * ((v81 + v107) / 0x2F5))))))))
            - *(&v73
              + (unsigned int)(*(&v73 + (unsigned int)(35758 - v121 - v99)) - 15181 + *(&v73 + (v98 + v110) / 0x46C)));
          goto LABEL_2;
        case 0x41u:
          ++v14;
          i = *(&v73
              + (unsigned int)(12716
                             - *(&v73 + (unsigned int)(v89 - 30908 + v105))
                             - *(&v73 + (unsigned int)(v96 - 29960))))
            + *(&v73 + (unsigned int)(v109 + v117 - 39039))
            - 35059;
          continue;
        case 0x42u:
          v20 = v20 + v18;
          v57 = v114 + v122;
          v58 = v101;
          *((_DWORD *)a2 + 283) = *((_DWORD *)a2 + 277);
          v61 = v20;
          i = *(&v73 + (unsigned int)(16127 - *(&v73 + v57 / 0x5C6)))
            + *(&v73 + (unsigned int)(v78 + v58 - 13194))
            - 58611;
          continue;
        case 0x43u:
          Paper::ImportantTopic::AcquireLogicalOperation(19);
          v17 = (float)(v17 - 0.0) - v18;
          v28 = Paper::ImportantTopic::IterateIntegratedLibrary(&v70, 0x264u);
          v29 = v105 + v81;
          v20 = v61;
          v21 = v64;
          v22 = v65;
          v23 = v63;
          LODWORD(v24) = v60;
          v25 = v62;
          LOWORD(v69) = v28;
          v30 = 14791 * (v75 + v96);
          *((_QWORD *)a2 + 138) = 0;
          *((_QWORD *)a2 + 139) = 0;
          *((_DWORD *)a2 + 280) = 0;
          *(_QWORD *)((char *)a2 + 1124) = -1;
          i = (*(&v73
               + (unsigned __int16)(-30225
                                  * (*((_WORD *)&v73 + 2 * (v83 / 0x1AF)) + *((_WORD *)&v73 + 2 * (v29 / 0x2B0)))))
             + *(&v73 + (unsigned int)(23967 - *(&v73 + v30) - *(&v73 + (unsigned int)(9637 - v74)))))
            / 0x143u;
          goto LABEL_2;
        case 0x44u:
          LOWORD(v69) = v9 - v13;
          v7 = 0;
          i = 8668 - *(&v73 + (unsigned int)(*(&v73 + (v105 + v98) / 0x702) - 29968));
          continue;
        case 0x45u:
          Paper::LogicalControl = Paper::LogicalControl + -1.0;
          v17 = v21 * 0.03125;
          if ( v10 == 0.0 )
          {
            v11 = FLOAT_1_1754944eN38;
          }
          else
          {
            if ( v10 < 0.0 )
            {
              v40 = o_sqrtf_0(v10);
              v21 = v64;
            }
            else
            {
              v40 = fsqrt(v10);
            }
            v11 = v67 / v40;
          }
          v20 = v61;
          v22 = v65;
          v23 = v63;
          LODWORD(v24) = v60;
          v25 = v62;
          i = (*(&v73 + (unsigned int)(*(&v73 + v98 / 0x2A60) + *(&v73 + (unsigned int)(28462 - v99)) - 37578))
             + *(&v73
               + (unsigned int)(44518
                              - *(&v73 + (unsigned __int16)(6727 * (v103 + v89)))
                              - *(&v73 + (unsigned int)(12777 - v78)))))
            / 0x498u;
          goto LABEL_2;
        case 0x46u:
          LOWORD(v69) = v69 + 2;
          Paper::ImportantTopic::AcquireLogicalOperation(97);
          v22 = v65;
          v48 = 22650 * (v84 + v74);
          *((float *)a2 + 277) = v12;
          i = (unsigned __int16)(-10202 * *((_WORD *)&v73 + 2 * v48));
          goto LABEL_6;
        case 0x48u:
          v70 = Paper::SlowInformation - LODWORD(qword_180129C98[Paper::SlowInformation & 0xF]);
          v43 = Input::ComprehensiveSkill::OrderDetailedMode<Data::HighDescription<float *>,signed char const *>(
                  this,
                  a2,
                  &Input::ComprehensiveSkill::CommonTime,
                  168);
          v22 = v65;
          v72[0] = *(float *)&v43;
          i = 33701 - *(&v73 + v115 + v81 - 24806) - *(&v73 + (v114 + v90) / 0x329u);
          goto LABEL_6;
        case 0x49u:
          v19 = *(float *)&v24;
          Paper::LogicalControl = 1.75;
          v37 = *((float *)a2 + 283) * 0.5;
          Paper::LogicalControl = v37;
          v38 = Input::ComprehensiveSkill::OrderDetailedMode<Data::HighDescription<float *>,signed char const *>(
                  this,
                  (char *)a2 + 300,
                  (char *)&Input::ComprehensiveSkill::OptimalSkill + 195 * v9,
                  195);
          v21 = *(float *)&v38;
          v22 = v65;
          v64 = *(float *)&v38;
          i = 8715
            - *(&v73
              + (unsigned int)(19398
                             - *(&v73
                               + (unsigned int)(22773
                                              - *(&v73
                                                + (unsigned __int16)(4084
                                                                   * *((_WORD *)&v73 + 2 * v107 + 2 * v119 - 46598)))
                                              - *(&v73 + (unsigned int)(v104 - 5252))))
                             - *(&v73 + (unsigned int)(v104 - 28362 + v105))));
          goto LABEL_7;
        case 0x4Au:
          v6 = v21;
          v17 = v17 + -1.0;
          v70 = IntegralRelation::CoordinatedArray * v13;
          i = (unsigned __int16)(1300
                               * *((_WORD *)&v73
                                 + 2
                                 * (unsigned __int16)(2275
                                                    * (*((_WORD *)&v73 + 2 * (unsigned int)(v79 - 22702))
                                                     + *((_WORD *)&v73 + 2 * (unsigned __int16)(23304 * (v98 + v96)))))));
          continue;
        case 0x4Du:
          Paper::SlowInformation += v8;
          Paper::LogicalControl = v12 * v21;
          Paper::LogicalControl = *((float *)a2 + 278) - v72[0];
          v52 = (__int64 (__fastcall *)(Input::ComprehensiveSkill *, _QWORD, _QWORD))GenerateMixedProvider(
                                                                                       0x9F1FFFBF00E000C0uLL,
                                                                                       1906573418,
                                                                                       v27);
          v53 = v52(this, v59, v13);
          v54 = v81 + v77;
          v22 = v65;
          *((_DWORD *)a2 + 281) = v53;
          i = 34552
            - *(&v73 + (unsigned int)(6148 - *(&v73 + (unsigned __int16)(12021 * (v78 + v92)))))
            - *(&v73 + v54 / 0x283);
          goto LABEL_6;
        case 0x52u:
          v17 = X - *((float *)a2 + 280);
          Paper::ImportantTopic::IterateIntegratedLibrary((char *)a2 + 1100, 0x8Bu);
          Paper::LogicalControl = v63 - v5;
          v70 = Paper::SlowInformation + *((_DWORD *)a2 + 282);
          if ( X == 0.0 )
          {
            v12 = FLOAT_1_1754944eN38;
            v25 = v62;
          }
          else
          {
            if ( X < 0.0 )
              v42 = o_sqrtf_0(X);
            else
              v42 = fsqrt(X);
            v25 = v62;
            v12 = v62 / v42;
          }
          v21 = v64;
          v22 = v65;
          v23 = v63;
          LODWORD(v24) = v60;
          v20 = v61;
          i = (unsigned __int16)(2484
                               * (*((_WORD *)&v73 + 2 * (unsigned int)(*(&v73 + v122 / 0x259) - 2711))
                                + *((_WORD *)&v73
                                  + 2
                                  * (unsigned int)(4361
                                                 - *(&v73
                                                   + (unsigned __int16)(21938
                                                                      * (*((_WORD *)&v73 + 2 * (49710 - v98 - v112))
                                                                       + *((_WORD *)&v73 + 2 * ((v96 + v84) / 0xC17u)))))))));
          goto LABEL_2;
        case 0x55u:
          v17 = v19 - 0.0;
          v31 = Input::ComprehensiveSkill::OrderDetailedMode<Data::HighDescription<float *>,signed char const *>(
                  this,
                  a2,
                  &Input::ComprehensiveSkill::AsyncTime,
                  75);
          v22 = *(float *)&v31;
          v65 = *(float *)&v31;
          i = *(&v73 + v119 + v74 - 26813) / 0x13C7u;
          goto LABEL_6;
        case 0x56u:
          Paper::LogicalControl = v17 * v23;
          v32 = Input::ComprehensiveSkill::OrderDetailedMode<Data::HighDescription<float *>,signed char const *>(
                  this,
                  (char *)a2 + 300,
                  (char *)&Input::ComprehensiveSkill::OddMessage + 45 * v8,
                  45);
          v22 = v65;
          v66 = *(float *)&v32;
          i = (*(&v73 + (unsigned int)(*(&v73 + 12830 - v91) - 14068))
             + *(&v73 + (unsigned int)(*(&v73 + v115 / 0x137) - 19017 + *(&v73 + (v75 + v94) / 0x854))))
            / 0x88Au;
          goto LABEL_6;
        case 0x58u:
          v20 = *(float *)&v24;
          v61 = *(float *)&v24;
          i = *(&v73
              + (unsigned __int16)(15762
                                 * (*((_WORD *)&v73 + 2 * (unsigned int)(v89 - 7790))
                                  + *((_WORD *)&v73 + 2 * ((v96 + v105) / 0x531u)))))
            + *(&v73 + (unsigned int)(30713 - *(&v73 + (unsigned int)(25792 - v88 - v74))))
            - 8496;
          goto LABEL_2;
        case 0x5Au:
          if ( *(float *)&v24 > v20 )
          {
            i = *(&v73 + (unsigned int)(*(&v73 + (unsigned __int16)(6876 * v87)) - 19311 + *(&v73 + 34345 - v83 - v105)))
              + *(&v73 + (v87 + v82) / 0x614u)
              - 4132;
            goto LABEL_2;
          }
          i = (*(&v73 + v98 - 21690) + *(&v73 + (unsigned int)(v73 - 26865))) / 0xFBu;
          continue;
        case 0x5Bu:
          v27 = (unsigned int)v8;
          --v70;
          v59 = v8;
          i = (*(&v73 + (unsigned __int16)(-6129 * v90))
             + *(&v73
               + (unsigned int)(49486
                              - *(&v73
                                + (*(&v73 + v119 + v89 - 24995) + *(&v73 + (unsigned __int16)(25119 * (v85 + v74))))
                                / 0x242u)
                              - *(&v73 + (unsigned int)(24998 - *(&v73 + (unsigned int)(v99 - 60649 + v82)))))))
            / 0x2D2u;
          continue;
        case 0x5Cu:
          if ( *((_WORD *)a2 + 550) )
          {
            if ( v8 >= *((_DWORD *)a2 + 275) )
            {
              if ( v23 == *((float *)a2 + 279) )
                i = (unsigned __int16)(2185 * *((_WORD *)&v73 + 2 * (unsigned int)(*(&v73 + v122 - 20975) - 23126)));
              else
                i = *(&v73 + (unsigned __int16)(-914 * *((_WORD *)&v73 + 2 * (unsigned int)(v117 - 14049))))
                  + *(&v73 + (unsigned int)(2350 - v102))
                  - 25417;
            }
            else
            {
              i = 21768 - *(&v73 + (unsigned __int16)(-30822 * v112));
            }
          }
          else
          {
            i = (*(&v73 + v94 / 0xD0)
               + *(&v73 + (unsigned int)(5530 - *(&v73 + v115 - 14263) - *(&v73 + (unsigned int)(25022 - v109)))))
              / 0x191u;
          }
          continue;
        case 0x63u:
          Paper::SlowInformation = LODWORD(qword_180129C98[Paper::SlowInformation & 0xF]) * v9;
          Paper::ImportantTopic::AcquireLogicalOperation(13);
          v39 = Input::ComprehensiveSkill::DefineShortTermControl<Data::HighDescription<float *>>(this, a2, 120);
          v10 = *(float *)&v39;
          v22 = v65;
          i = *(&v73
              + (unsigned int)(4619
                             - *(&v73
                               + (*(&v73 + v110 + v115 - 18608) + *(&v73 + (unsigned int)(v108 - 12828 + v74))) / 0x25Du)
                             - *(&v73 + (unsigned int)(56797 - v112 - v84))))
            / 0x760u;
LABEL_6:
          v21 = v64;
LABEL_7:
          v23 = v63;
LABEL_8:
          LODWORD(v24) = v60;
          v25 = v62;
          v20 = v61;
          goto LABEL_2;
        case 0x64u:
          Paper::SlowInformation = 14479;
          v19 = *((float *)a2 + 283) - Paper::LogicalControl;
          LOWORD(v69) = (int)(v22 * 0.0625);
          if ( v9 < 104 )
          {
            LODWORD(v24) = v60;
            i = *(&v73 + *(&v73 + (unsigned int)(18564 - v97)) / 0x187u) / 0x8Fu;
            continue;
          }
          LODWORD(v24) = v60;
          i = (unsigned __int16)(11604
                               * (*((_WORD *)&v73
                                  + 2
                                  * (unsigned int)(*(&v73 + (unsigned __int16)(347 * (v108 + v104)))
                                                 + *(&v73 + v122 + v101 - 21422)
                                                 - 31774))
                                + *((_WORD *)&v73
                                  + 2
                                  * (unsigned int)(*(&v73
                                                   + (unsigned int)(*(&v73 + (unsigned __int16)(32 * v90))
                                                                  - 26937
                                                                  + *(&v73 + v101 + v93 - 17688)))
                                                 + *(&v73 + (unsigned int)(58380 - v86 - v112))
                                                 - 29354))));
          goto LABEL_2;
        case 0x66u:
          Paper::ImportantTopic::AcquireLogicalOperation(26);
          v20 = v61;
          v21 = v64;
          v22 = v65;
          v14 = 0;
          v23 = v63;
          LODWORD(v24) = v60;
          v25 = v62;
          i = 17309 - *(&v73 + (*(&v73 + (unsigned int)(v92 - 8635)) + *(&v73 + v109 + v120 - 37965)) / 0x532u);
          goto LABEL_2;
        default:
          return;
      }
      break;
    }
    while ( *v36 == v36[(_QWORD)&Input::ComprehensiveSkill::OptimalSkill
                      + 195LL * v9
                      - v35
                      - (_QWORD)&Input::ComprehensiveSkill::OddMessage] )
    {
      if ( ++v36 - ((char *)&Input::ComprehensiveSkill::OddMessage + v35) >= 45 )
      {
        i = 29135 - *(&v73 + (unsigned int)(v112 + v96 - 57934));
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
