# Input::ActiveRecommendation::PaintFlatLocation(Input::OddFilter<uchar,130,130> &,Input::LowFilter<int> const &)

- ea: `0x180044b90`
- end: `0x180046547`
- name: `?PaintFlatLocation@ActiveRecommendation@Input@@UEAA?AVNullAPI@2@AEAV?$OddFilter@E$0IC@$0IC@@2@AEBU?$LowFilter@H@2@@Z`
- size: `6583`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180003180`
- `0x180007b70`
- `0x18000df20`
- `0x18000e0c0`
- `0x18000e3b0`
- `0x18000e4b0`
- `0x1800267b0`
- `0x180038d10`
- `0x180044b90`
- `0x18006cd00`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__controlfp_s` at `0x180045f4c`
- `api-ms-win-crt-private-l1-1-0!_o__controlfp_s` at `0x180045f4c`

## pseudocode

```c
_OWORD *__fastcall Input::ActiveRecommendation::PaintFlatLocation(__int64 a1, _OWORD *a2, __int64 a3, _DWORD *a4)
{
  unsigned int v4; // r13d
  unsigned int v5; // r12d
  float v6; // xmm7_4
  float v7; // xmm13_4
  float v8; // xmm6_4
  float v9; // xmm14_4
  float v10; // xmm8_4
  float v11; // xmm12_4
  int v12; // eax
  Input::ClearUnit *v13; // rbx
  Input::ClearUnit *v14; // r15
  Input::ClearUnit *v15; // rdi
  float *v16; // r14
  Input::ClearUnit *v17; // rsi
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 (__fastcall *v20)(__int64, __int64, int *); // rax
  unsigned int v21; // r8d
  unsigned int v22; // r9d
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 (__fastcall *v25)(__int64, float *, __int64); // rax
  __int64 v26; // r12
  void (__fastcall *v27)(__int64, Input::ClearUnit *); // rax
  int v28; // eax
  int v29; // ecx
  unsigned int v30; // eax
  int v31; // eax
  unsigned int v32; // r8d
  unsigned int v33; // r9d
  unsigned int v34; // ecx
  unsigned int v35; // r12d
  int v36; // eax
  unsigned int v37; // r12d
  unsigned __int16 (__fastcall *MixedProvider)(char *, _QWORD); // rax
  struct Input::PartialMessage *v39; // r12
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // r12
  __int64 (__fastcall *v43)(_QWORD, __int64, bool *); // rax
  __int64 *v44; // rax
  _OWORD *v45; // r13
  __int64 v46; // rcx
  __int128 v47; // xmm0
  int v48; // eax
  double v49; // xmm6_8
  __int128 v50; // xmm2
  __int128 v51; // xmm3
  __int128 v52; // xmm4
  __int128 v53; // xmm5
  __int128 v54; // xmm1
  __int128 v55; // xmm1
  __int128 v56; // xmm0
  __int128 v57; // xmm1
  __int128 v58; // xmm0
  __int128 v59; // xmm1
  __int128 v60; // xmm0
  unsigned int v62; // [rsp+28h] [rbp-E0h]
  __int16 v63; // [rsp+2Ch] [rbp-DCh]
  signed int v64; // [rsp+30h] [rbp-D8h]
  int v65; // [rsp+34h] [rbp-D4h]
  int v66; // [rsp+38h] [rbp-D0h]
  unsigned int v67; // [rsp+3Ch] [rbp-CCh]
  int v68; // [rsp+40h] [rbp-C8h]
  int v69; // [rsp+44h] [rbp-C4h]
  int v70; // [rsp+48h] [rbp-C0h]
  __int64 v71; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v72; // [rsp+58h] [rbp-B0h]
  _DWORD *v73; // [rsp+60h] [rbp-A8h]
  __int64 v74; // [rsp+68h] [rbp-A0h]
  __int64 v75; // [rsp+70h] [rbp-98h]
  _OWORD *v76; // [rsp+78h] [rbp-90h]
  __int64 v77; // [rsp+80h] [rbp-88h]
  unsigned __int8 *v78; // [rsp+88h] [rbp-80h]
  void **v79; // [rsp+90h] [rbp-78h] BYREF
  bool v80[4]; // [rsp+98h] [rbp-70h] BYREF
  unsigned int v81; // [rsp+9Ch] [rbp-6Ch] BYREF
  double v82; // [rsp+A0h] [rbp-68h] BYREF
  int v83; // [rsp+A8h] [rbp-60h] BYREF
  float v84; // [rsp+ACh] [rbp-5Ch] BYREF
  Input::ClearUnit *v85; // [rsp+B0h] [rbp-58h] BYREF
  int v86; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v87; // [rsp+C0h] [rbp-48h] BYREF
  __int128 v88; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v89[20]; // [rsp+D8h] [rbp-30h]
  int v90; // [rsp+F8h] [rbp-10h] BYREF
  int v91; // [rsp+FCh] [rbp-Ch]
  int v92; // [rsp+100h] [rbp-8h]
  int v93; // [rsp+104h] [rbp-4h]
  int v94; // [rsp+108h] [rbp+0h]
  int v95; // [rsp+10Ch] [rbp+4h]
  int v96; // [rsp+110h] [rbp+8h]
  int v97; // [rsp+114h] [rbp+Ch]
  int v98; // [rsp+118h] [rbp+10h]
  int v99; // [rsp+11Ch] [rbp+14h]
  int v100; // [rsp+120h] [rbp+18h]
  int v101; // [rsp+124h] [rbp+1Ch]
  int v102; // [rsp+128h] [rbp+20h]
  int v103; // [rsp+12Ch] [rbp+24h]
  int v104; // [rsp+130h] [rbp+28h]
  int v105; // [rsp+134h] [rbp+2Ch]
  __int128 v106; // [rsp+138h] [rbp+30h] BYREF
  __int128 v107; // [rsp+148h] [rbp+40h]
  __int128 v108; // [rsp+158h] [rbp+50h]
  __int128 v109; // [rsp+168h] [rbp+60h]
  _BYTE v110[48]; // [rsp+178h] [rbp+70h]
  __int64 v111; // [rsp+1A8h] [rbp+A0h]
  int v112; // [rsp+1B0h] [rbp+A8h]
  unsigned __int8 *retaddr; // [rsp+2A0h] [rbp+198h]

  v75 = a1;
  v73 = a4;
  LOWORD(v4) = 0;
  v65 = 0;
  v5 = 0;
  v64 = 0;
  v66 = 0;
  v6 = 0.0;
  v80[0] = 0;
  LODWORD(v72) = 0;
  v78 = 0;
  v7 = 0.0;
  v70 = 0;
  v8 = 0.0;
  v69 = 0;
  v9 = 0.0;
  v68 = 0;
  v10 = 0.0;
  v84 = 0.0;
  v11 = 0.0;
  v67 = 0;
  v71 = 0;
  v81 = 0;
  v77 = a3;
  v76 = a2;
  LODWORD(v74) = 0;
  v82 = 0.0;
  v79 = &Area::IntegralRecord::EnhanceComprehensiveEvent::`vftable';
  v12 = Area::IntegralRecord::WrapMixedMessage(
          (Area::IntegralRecord *)&v79,
          (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
          0x4C9B8F15u,
          0xD76u,
          0);
  v13 = v85;
  v14 = v85;
  v15 = v85;
  v16 = (float *)v85;
  v17 = v85;
  while ( 1 )
  {
    switch ( v12 )
    {
      case 10:
        v5 = (unsigned __int16)(v4 + v81);
        v83 = 0;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0xCE7AB21D,
                0x5030000u,
                v5);
        continue;
      case 11:
        LOWORD(v5) = v5 + 1;
        IntegralRelation::OddMap = ScatteredInformation::StripedSeries ^ 0x157E9386;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0xDD8596B6,
                0xC000007u,
                v5);
        continue;
      case 13:
        Paper::LogicalControl = *((float *)Input::ClearUnit::OrderIntegralObject((Input::ClearUnit *)((char *)v13 + 7640))
                                + 13)
                              * 0.0625;
        *((float *)v17 + 277) = *((float *)v17 + 277) + 1.0;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x78278283u,
                0xC000598E,
                v62);
        continue;
      case 17:
        v81 = IntegralRelation::OddMap * v69;
        v64 = *(_DWORD *)v14;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x476C3A5Au,
                0x16B00u,
                v62);
        continue;
      case 20:
        LOWORD(v5) = v5 - 1;
        Paper::SlowInformation = 22827;
        *(_DWORD *)v89 = 0;
        Paper::LogicalControl = Paper::LogicalControl + 1.0;
        v88 = 0;
        *(__m128i *)&v89[4] = _mm_load_si128((const __m128i *)&_xmm);
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0xB2172C46,
                0xAB80000u,
                v5);
        continue;
      case 22:
        Paper::ImportantTopic::AcquireLogicalOperation(93);
        v81 = v64;
        v5 = (unsigned __int16)v64
           * *((unsigned __int16 *)&ScatteredInformation::StripedSeries + 4 * (Paper::SlowInformation & 0xF) + 4);
        Paper::LogicalControl = (float)(int)Paper::ImportantTopic::IterateIntegratedLibrary(
                                              &Paper::SlowInformation,
                                              0x13Bu);
        v10 = FLOAT_5_9580384e8;
        v81 = Paper::ImportantTopic::IterateIntegratedLibrary(&Paper::SlowInformation, 0x16Eu);
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x89D39B55,
                0x12000005u,
                v5);
        continue;
      case 24:
        if ( v82 >= 0.0 )
        {
          Paper::ImportantTopic::AcquireLogicalOperation(39);
          v32 = 741760484;
          v33 = 536871312;
          v81 = IntegralRelation::CoordinatedArray
              + *((_DWORD *)&ScatteredInformation::StripedSeries + 2 * (Paper::SlowInformation & 0xF) + 2);
          if ( v67 >= 0x1E )
          {
            v32 = -934194593;
            v33 = 1879050932;
          }
          Paper::LogicalControl = v10 * 0.25;
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  v32,
                  v33,
                  v62);
        }
        else
        {
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0x84D4E68A,
                  0x20000021u,
                  v62);
        }
        continue;
      case 25:
        v67 += 2;
        v81 = 48967;
        Paper::SlowInformation = (int)(v8 * 0.25);
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x1DA14F3u,
                0xF30000CD,
                v62);
        continue;
      case 26:
        if ( v82 == 1.0 )
        {
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0xD92BAD66,
                  0x460000C5u,
                  v62);
        }
        else
        {
          ++v81;
          v64 = *(_DWORD *)v14;
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0x2074752Bu,
                  0x10008CECu,
                  v62);
        }
        continue;
      case 30:
        ++Paper::SlowInformation;
        v64 = 0;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x1B8D13EDu,
                0x89FBC00u,
                v62);
        continue;
      case 31:
        v4 = (int)(v10 * 0.03125);
        v5 = (int)(Paper::LogicalControl * 0.5);
        if ( v82 >= 0.0 )
        {
          *((_DWORD *)v15 + 8) = *v16 > 21.484375;
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0xF682068D,
                  0x6910000u,
                  v5);
        }
        else
        {
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0x88C76486,
                  0xE00000A1,
                  v5);
        }
        continue;
      case 32:
        v81 = 33173;
        v28 = Paper::ImportantTopic::IterateIntegratedLibrary(&v81, 0x8Au);
        v29 = *((_DWORD *)&ScatteredInformation::StripedSeries + 2 * (Paper::SlowInformation & 0xF) + 2);
        Paper::LogicalControl = (float)v28;
        Paper::SlowInformation = *v73 * v29 - 1;
        *(_OWORD *)v15 = *((_OWORD *)v17 + 69);
        *((_QWORD *)v15 + 2) = *((_QWORD *)v17 + 140);
        *((_DWORD *)v15 + 6) = *((_DWORD *)v17 + 282);
        *((_DWORD *)v15 + 7) = 0;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0xD7EB16B5,
                0xC9A600u,
                v62);
        continue;
      case 33:
        v90 = 539504696;
        v5 = 17491;
        v71 = 0xAAAAAAAAA9A2A9B5uLL;
        LOWORD(v4) = v4 + 1;
        v91 = 528408;
        v92 = 573190714;
        v93 = 34214426;
        v94 = 606876732;
        v95 = 67900444;
        v96 = 640562750;
        v97 = 101586462;
        v98 = 657405759;
        v99 = 118429471;
        v100 = 623719741;
        v101 = 84743453;
        v102 = 590033723;
        v103 = 51057435;
        v104 = 556347705;
        v105 = 17371417;
        v71 = ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(
                (__int64)&ScatteredInformation::StripedSeries,
                &v71,
                (__int64)&v90);
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0xDFC40672,
                0x1F000u,
                0x4453u);
        continue;
      case 34:
        LOWORD(v4) = v4 + 2;
        v8 = FLOAT_2_8519824e8;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x9CEE36E2,
                0x16u,
                v62);
        continue;
      case 35:
        *((_QWORD *)&ScatteredInformation::StripedSeries
        + (unsigned __int8)((LODWORD((&ScatteredInformation::PaintShortTermException)[v67 / 2])
                           ^ IntegralRelation::OddMap)
                          / 0x9D28AF)
        - v67
        + 1) = *((_QWORD *)&ScatteredInformation::StripedSeries
               + (unsigned __int8)((*((_DWORD *)&ScatteredInformation::PaintShortTermException + v67 + 1)
                                  ^ IntegralRelation::OddMap)
                                 / 0x9D28AF)
               - v67);
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0xB834ECF3,
                0x50000CEDu,
                v62);
        continue;
      case 37:
        LOWORD(v5) = v5 + 2;
        Paper::SlowInformation = v65 - *v73;
        Paper::LogicalControl = v11 - Paper::LogicalControl;
        if ( v6 > v8 && *(float *)&v74 > v7 && v69 == 1 && v84 > v10 && v11 > v9 )
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0xF6258929,
                  0x39C0000u,
                  v5);
        else
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0xECABC584,
                  0x20000C00u,
                  v5);
        continue;
      case 40:
        LOWORD(v4) = (unsigned __int8)v81;
        Paper::SlowInformation = -(unsigned __int16)v5;
        v9 = (float)(1399290 * v68);
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x19BC3097u,
                0x3A00000Bu,
                v62);
        continue;
      case 41:
        LOWORD(v4) = *(_WORD *)v73 - v70;
        v5 = (int)(v11 * 0.0625);
        Paper::SlowInformation = (int)(v8 * 0.125);
        v67 = 0;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x4F3355D0u,
                0xDD4400u,
                v5);
        continue;
      case 42:
        v5 = (unsigned __int16)v81 * (unsigned __int16)v68;
        LOWORD(v4) = Paper::SlowInformation * v69;
        v80[0] = (IntegralRelation::OddMap ^ (unsigned int)v72) != 3069071;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x66772361u,
                0xCA8C0002,
                v5);
        continue;
      case 43:
        v37 = *((_DWORD *)v13 + 1877);
        MixedProvider = (unsigned __int16 (__fastcall *)(char *, _QWORD))GenerateMixedProvider(
                                                                           0x3F3FBFFF4000C0E0LL,
                                                                           3515105322LL,
                                                                           11694,
                                                                           &ScatteredInformation::StripedSeries);
        v5 = MixedProvider((char *)v17 + 1132, v37);
        v6 = *((float *)v13 - 51)
           - *((float *)Input::ClearUnit::OrderIntegralObject((Input::ClearUnit *)((char *)v13 + 22920)) + 9);
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x886CFCC0,
                0xF0000095,
                v5);
        continue;
      case 45:
        v5 = 11694;
        Paper::LogicalControl = 0.75;
        v66 = 0;
        Paper::SlowInformation = 10589;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x508685CEu,
                0x84u,
                0x2DAEu);
        continue;
      case 46:
        LOWORD(v5) = v5 - 1;
        v31 = *v73 * v69;
        Paper::SlowInformation = v69 + IntegralRelation::CoordinatedArray;
        v81 = v31;
        v78 = retaddr;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x7EF8CB38u,
                0x5A54000Du,
                v5);
        continue;
      case 47:
        --Paper::SlowInformation;
        Paper::ImportantTopic::AcquireLogicalOperation(50);
        ++v66;
        Paper::LogicalControl = Paper::LogicalControl + -1.0;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0xE7699388,
                0x655600u,
                v62);
        continue;
      case 48:
        LOWORD(v4) = 0;
        v21 = 692596633;
        v22 = 956321638;
        if ( v66 >= 1 )
        {
          v21 = -1964792668;
          v22 = -830078976;
        }
        goto LABEL_21;
      case 52:
        v16[4] = v16[4] - 1.0;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x2F2746EAu,
                0x3E200u,
                v62);
        continue;
      case 57:
        Paper::ImportantTopic::AcquireLogicalOperation(70);
        *(float *)&v74 = FLOAT_5_7405018e8;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x3B8B8173u,
                0xAADB00u,
                v62);
        continue;
      case 63:
        v30 = Paper::ImportantTopic::IterateIntegratedLibrary(&v84, 0x154u);
        --v81;
        Paper::SlowInformation = v30;
        LOWORD(v4) = v4 - 1;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x166D52B2u,
                0x7220000u,
                v62);
        continue;
      case 64:
        v5 = (unsigned __int16)IntegralRelation::CoordinatedArray * *(unsigned __int16 *)v73;
        v4 = (int)(v9 * 0.25);
        v7 = (float)(2812149 * v70);
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x75E0ECAAu,
                0x51000015u,
                v5);
        continue;
      case 66:
        LOWORD(v5) = v5 - 1;
        IntegralRelation::OddMap = ScatteredInformation::StripedSeries ^ 0x157E9386;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x79C1CB95u,
                0xD000067u,
                v5);
        continue;
      case 68:
        if ( v82 >= 0.0 )
        {
          v65 = 0;
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0xFBA6FDD7,
                  0x39C000u,
                  v62);
        }
        else
        {
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0xADA834C6,
                  0xFA000016,
                  v62);
        }
        continue;
      case 71:
        ++Paper::SlowInformation;
        v26 = *(_QWORD *)(v75 + 537632);
        v4 = (int)(v84 * 0.125);
        v27 = (void (__fastcall *)(__int64, Input::ClearUnit *))GenerateMixedProvider(
                                                                  0xBF7FDF3F008060B0uLL,
                                                                  1371807978,
                                                                  11694,
                                                                  &ScatteredInformation::StripedSeries);
        v27(v26, v17);
        v5 = v62;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x16DFC8F5u,
                0xA3A00000,
                v62);
        continue;
      case 74:
        v80[0] = 0;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x12A59F79u,
                0x6D7F0033u,
                v62);
        continue;
      case 75:
        Paper::SlowInformation = 18393;
        Paper::LogicalControl = Paper::LogicalControl + v8;
        if ( *((_DWORD *)v15 + 8) == 1
          || Input::AvailablePermission::CharacterizeStripedObject(*(Input::AvailablePermission **)(v75 + 537632), *v16) )
        {
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0x2D2905F2u,
                  0x940000AF,
                  v62);
        }
        else
        {
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0xAAB0C53A,
                  0x629D0000u,
                  v62);
        }
        continue;
      case 77:
        v65 = (int)(*((float *)v13 + 7358) * 0.03125);
        *((_DWORD *)v17 + 283) = *((_DWORD *)v13 + 3999);
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x2BF8C7EEu,
                0x60B000u,
                v62);
        continue;
      case 78:
        v4 = (unsigned __int16)(qword_18012A008 + v71);
        Paper::LogicalControl = v10;
        v5 = qword_18012A008 + v4;
        v81 = 4272;
        v16 = (float *)((char *)v13 + 7640 * v64 + 7424);
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x5E3F068Eu,
                0x8A40000u,
                (unsigned int)qword_18012A008 + v4);
        continue;
      case 79:
        LOWORD(v4) = v66 - v64;
        v81 = v65;
        *(_QWORD *)((char *)v15 + 20) = -1;
        *(_QWORD *)v15 = 0;
        *((_QWORD *)v15 + 1) = 0;
        *((_DWORD *)v15 + 4) = 0;
        *(_QWORD *)((char *)v15 + 28) = 0;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0xE234F0CD,
                0x17A50000u,
                v62);
        continue;
      case 80:
        v81 = v64;
        v5 = (unsigned __int16)v71 * (unsigned __int16)v72;
        v68 = 212;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x876C827u,
                0xC0000628,
                v5);
        continue;
      case 81:
        LODWORD(v72) = -68437796;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x766BDCECu,
                0xCEE20000,
                v62);
        continue;
      case 83:
        v7 = *((float *)v13 + 5917) + *((float *)v13 + 1859);
        v82 = (float)(*((float *)v13 + 5739) * *((float *)v13 + 3821));
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x8E81E971,
                0xAABB0000,
                v62);
        continue;
      case 84:
        v5 = (unsigned __int16)(word_180129CE0 + v81);
        LOWORD(v4) = 25043;
        Paper::LogicalControl = v10;
        Paper::SlowInformation = 3673;
        v80[0] = 1;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x31688058u,
                0xD200088B,
                v5);
        continue;
      case 86:
        v81 = v71;
        Paper::ImportantTopic::AcquireLogicalOperation(32);
        Paper::ImportantTopic::AcquireLogicalOperation(97);
        if ( v82 >= 0.0 )
        {
          v69 = 1;
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0x82524269,
                  0xAB380000,
                  v62);
        }
        else
        {
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0xCA07D11A,
                  0xAC4A0004,
                  v62);
        }
        continue;
      case 88:
        v70 = *v78;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x5AFB0E30u,
                0xC7A00000,
                v62);
        continue;
      case 89:
        ++Paper::SlowInformation;
        v90 = 923746055;
        v91 = 656355095;
        v34 = IntegralRelation::OddMap + *v73;
        LOWORD(v62) = 30712;
        v86 = 0;
        v87 = v71;
        Paper::SlowInformation = v34;
        v85 = (Input::ClearUnit *)0xEF8F2FCFF09060B0LL;
        v92 = 906903046;
        v93 = 639512086;
        v94 = 890060037;
        v95 = 622669077;
        v96 = 873217028;
        v97 = 605826068;
        v98 = 856374019;
        v99 = 588983059;
        v100 = 839531010;
        v101 = 572140050;
        v102 = 822688001;
        v103 = 555297041;
        v104 = 805844992;
        v105 = 538454032;
        *(_QWORD *)&v106 = 0x271F2F17370F3F07LL;
        *((_QWORD *)&v106 + 1) = 0x261E2E16360E3E06LL;
        *(_QWORD *)&v107 = 0x251D2D15350D3D05LL;
        *((_QWORD *)&v107 + 1) = 0x241C2C14340C3C04LL;
        *(_QWORD *)&v108 = 0x231B2B13330B3B03LL;
        *((_QWORD *)&v108 + 1) = 0x221A2A12320A3A02LL;
        *(_QWORD *)&v109 = 0x2119291131093901LL;
        *((_QWORD *)&v109 + 1) = 0x2018281030083800LL;
        v35 = ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(
                (__int64)&ScatteredInformation::StripedSeries,
                &v87,
                (__int64)&v90)
            ^ 0xAAAAAAAA;
        v36 = ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(
                (__int64)&ScatteredInformation::StripedSeries,
                (__int64 *)&v85,
                (__int64)&v106);
        _o__controlfp_s(&v86, (v36 ^ 0xAAAAAAAA) - IntegralRelation::OddMap, v35);
        v5 = v62;
        LOWORD(v4) = v63;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0xD2982A0C,
                0x19090000u,
                v62);
        continue;
      case 90:
        v45 = v76;
        v46 = 7640LL * v64;
        *(_OWORD *)&v110[8] = v88;
        *((_QWORD *)&v47 + 1) = v88;
        *(_OWORD *)&v110[24] = *(_OWORD *)v89;
        *(_DWORD *)&v110[40] = *(_DWORD *)&v89[16];
        *(_DWORD *)&v110[44] = v65;
        v48 = 0;
        v49 = *(double *)((char *)v13 + v46 + 7488);
        v50 = *(_OWORD *)((char *)v13 + v46 + 7424);
        v111 = 0;
        v51 = *(_OWORD *)((char *)v13 + v46 + 7440);
        v52 = *(_OWORD *)((char *)v13 + v46 + 7456);
        v53 = *(_OWORD *)((char *)v13 + v46 + 7472);
        v54 = *(_OWORD *)&v110[32];
        *(double *)&v47 = v49;
        *v76 = v50;
        v45[1] = v51;
        v45[2] = v52;
        v45[3] = v53;
        v45[4] = v47;
        v45[5] = *(_OWORD *)&v110[16];
        *(_QWORD *)&v47 = v111;
        v45[6] = v54;
        *((_QWORD *)v45 + 14) = v47;
        goto LABEL_104;
      case 91:
        Paper::ImportantTopic::AcquireLogicalOperation(75);
        ++Paper::SlowInformation;
        ++v81;
        Paper::LogicalControl = v6 - v8;
        v25 = (__int64 (__fastcall *)(__int64, float *, __int64))GenerateMixedProvider(
                                                                   0x1FDF7FDFA0208040LL,
                                                                   4049895434LL,
                                                                   v23,
                                                                   v24);
        v17 = (Input::ClearUnit *)v25(v75 + 384768, v16, v77);
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0xE804C391,
                0xB0000673,
                v62);
        continue;
      case 92:
        --Paper::SlowInformation;
        v5 = 0;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x5C116DD1u,
                0xA0007FE4,
                0);
        continue;
      case 93:
        v81 = (unsigned __int16)v4 - (unsigned __int16)v71;
        if ( v82 == 1.0 )
        {
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0x8332FB8E,
                  0xCCDD00u,
                  v62);
        }
        else
        {
          Input::EllipticActivity::IssueGeneralLicense(v17, v73, 11694, &ScatteredInformation::StripedSeries);
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0xF86FA841,
                  0xB004F742,
                  v62);
        }
        continue;
      case 94:
        *((_DWORD *)v17 + 282) = *((_DWORD *)v13 + 7639) * v70;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x6EFF0C48u,
                0xD0B0000u,
                v62);
        continue;
      case 96:
        v81 = qword_18012A008 - v68;
        if ( v82 >= 0.0 )
        {
          Paper::LogicalControl = 0.875;
          if ( v82 == 1.0 )
          {
            v12 = Area::IntegralRecord::WrapMixedMessage(
                    (Area::IntegralRecord *)&v79,
                    (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                    0x23112DA7u,
                    0xA60800u,
                    v62);
          }
          else
          {
            v14 = (Input::ClearUnit *)&v83;
            v12 = Area::IntegralRecord::WrapMixedMessage(
                    (Area::IntegralRecord *)&v79,
                    (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                    0x24FA15A6u,
                    0x50000019u,
                    v62);
          }
        }
        else
        {
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0x1961D155u,
                  0xDC000000,
                  v62);
        }
        continue;
      case 101:
        LOWORD(v4) = v4 - 1;
        v15 = (Input::ClearUnit *)&v89[36 * v66 - 16];
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0xDE233D8B,
                0x7700008u,
                v62);
        continue;
      case 103:
        v5 = (unsigned __int16)(IntegralRelation::OddMap + v67);
        ++v65;
        Paper::LogicalControl = Paper::LogicalControl + 1.0;
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x39397B1Cu,
                0x28000067u,
                v5);
        continue;
      case 104:
        v5 = 0;
        v14 = (Input::ClearUnit *)((char *)v14 + 4);
        v62 = 0;
        v21 = -1037930857;
        v22 = 25886720;
        if ( v14 == (Input::ClearUnit *)&v84 )
          v21 = 2001065800;
        LOWORD(v4) = 15578;
        if ( v14 == (Input::ClearUnit *)&v84 )
          v22 = 15749888;
LABEL_21:
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                v21,
                v22,
                v62);
        break;
      case 106:
        v5 = (unsigned __int16)(v4 + v65);
        v6 = (float)(1399290 * v70);
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x20CD4A41u,
                0x30007596u,
                v5);
        continue;
      case 109:
        v16[1] = v16[1] + 1.0;
        v80[0] = *((_BYTE *)Input::ClearUnit::OrderIntegralObject((Input::ClearUnit *)((char *)v13 + 7640)) + 924) != *((_BYTE *)v13 + 16916);
        v39 = Input::ClearUnit::OrderIntegralObject((Input::ClearUnit *)((char *)v13 + 22920));
        if ( *((_BYTE *)v39 + 28) == *((_BYTE *)Input::ClearUnit::OrderIntegralObject(v13) + 924) )
        {
          v5 = v62;
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0xF3C89EA4,
                  0x275000u,
                  v62);
        }
        else
        {
          v42 = *((int *)v13 + 1913);
          v4 = IntegralRelation::CoordinatedArray;
          v43 = (__int64 (__fastcall *)(_QWORD, __int64, bool *))GenerateMixedProvider(
                                                                   0xBFFF7F7F800040E0uLL,
                                                                   1363443882,
                                                                   v40,
                                                                   v41);
          v44 = (__int64 *)v43(v4, v42, v80);
          v5 = v62;
          LOWORD(v4) = v63;
          qword_180129C78 = *v44;
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0xC396E42F,
                  0x63600u,
                  v62);
        }
        continue;
      case 111:
        if ( v82 == 1.0 )
        {
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0x96794F78,
                  0x9BEC0000,
                  v62);
        }
        else
        {
          Paper::ImportantTopic::AcquireLogicalOperation(90);
          v20 = (__int64 (__fastcall *)(__int64, __int64, int *))GenerateMixedProvider(
                                                                   0x3FDF9F9F804000C0LL,
                                                                   3513016394LL,
                                                                   v18,
                                                                   v19);
          v13 = (Input::ClearUnit *)v20(v75 + 64, v77, &v83);
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0x8B9B61E5,
                  0x66BA00u,
                  v62);
        }
        continue;
      case 113:
        LOWORD(v4) = -32307;
        ++Paper::SlowInformation;
        v81 = v67;
        v5 = 0;
        v84 = (float)(2812149 * v68);
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x791686F8u,
                0xA000000A,
                0);
        continue;
      case 114:
        LOWORD(v4) = v4 + 1;
        Paper::LogicalControl = 1.0;
        if ( v80[0] )
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0x1A3500DDu,
                  0x58630000u,
                  v62);
        else
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0xDF43501F,
                  0xE51A00u,
                  v62);
        continue;
      case 118:
        v5 = 0;
        v11 = FLOAT_2_969064e8;
        v81 = Paper::ImportantTopic::IterateIntegratedLibrary(&v82, 0x129u);
        v12 = Area::IntegralRecord::WrapMixedMessage(
                (Area::IntegralRecord *)&v79,
                (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                0x563B60B7u,
                0xDDFF0000,
                0);
        continue;
      case 120:
        LOWORD(v5) = v5 + 2;
        v81 = v66 - qword_18012A008;
        if ( (unsigned int)v64 > 1 )
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0x8154CEA7,
                  0xA4000002,
                  v5);
        else
          v12 = Area::IntegralRecord::WrapMixedMessage(
                  (Area::IntegralRecord *)&v79,
                  (struct Area::IntegralRecord::LongTermLocation *)0x30416752,
                  0x767CAFFu,
                  0x149000u,
                  v5);
        continue;
      default:
        v45 = v76;
        v55 = v107;
        v48 = v112;
        *v76 = v106;
        v56 = v108;
        v45[1] = v55;
        v57 = v109;
        v45[2] = v56;
        v58 = *(_OWORD *)v110;
        v45[3] = v57;
        v59 = *(_OWORD *)&v110[16];
        v45[4] = v58;
        v60 = *(_OWORD *)&v110[32];
        v45[5] = v59;
        *(_QWORD *)&v59 = v111;
        v45[6] = v60;
        *((_QWORD *)v45 + 14) = v59;
LABEL_104:
        *((_DWORD *)v45 + 30) = v48;
        return v45;
    }
  }
}

```

## disassembly

```asm
0x180044b90  mov     rax, rsp
0x180044b93  mov     [rax+18h], rbx
0x180044b97  push    rbp
0x180044b98  push    rsi
0x180044b99  push    rdi
0x180044b9a  push    r12
0x180044b9c  push    r13
0x180044b9e  push    r14
0x180044ba0  push    r15
0x180044ba2  lea     rbp, [rax-198h]
0x180044ba9  sub     rsp, 260h
0x180044bb0  movaps  xmmword ptr [rax-48h], xmm6
0x180044bb4  movaps  xmmword ptr [rax-58h], xmm7
0x180044bb8  movaps  xmmword ptr [rax-68h], xmm8
0x180044bbd  movaps  xmmword ptr [rax-78h], xmm9
0x180044bc2  movaps  xmmword ptr [rax-88h], xmm10
0x180044bca  movaps  xmmword ptr [rax-98h], xmm11
0x180044bd2  movaps  xmmword ptr [rax-0A8h], xmm12
0x180044bda  movaps  xmmword ptr [rax-0B8h], xmm13
0x180044be2  movaps  xmmword ptr [rax-0C8h], xmm14
0x180044bea  movaps  xmmword ptr [rax-0D8h], xmm15
0x180044bf2  mov     rax, cs:__security_cookie
0x180044bf9  xor     rax, rsp
0x180044bfc  mov     [rbp+190h+var_E0], rax
0x180044c03  mov     [rsp+290h+var_228], rcx
0x180044c08  lea     rax, ??_7EnhanceComprehensiveEvent@IntegralRecord@Area@@6B@; const Area::IntegralRecord::EnhanceComprehensiveEvent::`vftable'
0x180044c0f  xor     ecx, ecx
0x180044c11  mov     [rsp+290h+var_238], r9
0x180044c16  movzx   r13d, cx
0x180044c1a  mov     [rsp+290h+var_264], ecx
0x180044c1e  movzx   r12d, cx
0x180044c22  mov     [rsp+290h+var_268], ecx
0x180044c26  mov     [rsp+290h+var_260], ecx
0x180044c2a  xorps   xmm7, xmm7
0x180044c2d  mov     [rbp+190h+var_200], cl
0x180044c30  xorps   xmm9, xmm9
0x180044c34  mov     dword ptr [rsp+290h+var_240], ecx
0x180044c38  mov     r9d, 0D76h; unsigned int
0x180044c3e  mov     [rbp+190h+var_210], rcx
0x180044c42  xorps   xmm13, xmm13
0x180044c46  mov     dword ptr [rsp+290h+var_250], ecx
0x180044c4a  xorps   xmm6, xmm6
0x180044c4d  mov     [rsp+290h+var_254], ecx
0x180044c51  xorps   xmm14, xmm14
0x180044c55  mov     [rsp+290h+var_258], ecx
0x180044c59  xorps   xmm8, xmm8
0x180044c5d  mov     [rbp+190h+var_1EC], ecx
0x180044c60  xorps   xmm12, xmm12
0x180044c64  mov     [rsp+290h+var_25C], ecx
0x180044c68  mov     [rsp+290h+var_248], rcx
0x180044c6d  mov     [rbp+190h+var_1FC], ecx
0x180044c70  lea     rcx, [rbp+190h+var_208]; this
0x180044c74  mov     [rsp+290h+var_218], r8
0x180044c79  mov     r8d, 4C9B8F15h; unsigned int
0x180044c7f  mov     [rsp+290h+var_220], rdx
0x180044c84  mov     edx, 30416752h; struct Area::IntegralRecord::LongTermLocation *
0x180044c89  mov     [rsp+290h+var_26C], r13d
0x180044c8e  mov     [rsp+290h+var_270], r12d; unsigned int
0x180044c93  movss   dword ptr [rsp+290h+var_230], xmm7
0x180044c99  movsd   [rbp+190h+var_1F8], xmm9
0x180044c9f  mov     [rbp+190h+var_208], rax
0x180044ca3  call    ?WrapMixedMessage@IntegralRecord@Area@@YAHAEAULongTermLocation@12@III@Z; Area::IntegralRecord::WrapMixedMessage(Area::IntegralRecord::LongTermLocation &,uint,uint,uint)
0x180044ca8  movsd   xmm11, cs:__real@3ff0000000000000
0x180044cb1  movss   xmm10, cs:__real@3f800000
0x180044cba  movsd   xmm15, cs:__real@3fd0000000000000
0x180044cc3  mov     rbx, [rbp+190h+var_1E8]
0x180044cc7  mov     r15, [rbp+190h+var_1E8]
0x180044ccb  mov     rdi, [rbp+190h+var_1E8]
0x180044ccf  mov     r14, [rbp+190h+var_1E8]
0x180044cd3  mov     rsi, [rbp+190h+var_1E8]
0x180044cd7  movsd   xmm2, cs:__real@3fb0000000000000
0x180044cdf  lea     r9, ?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x180044ce6  movss   xmm0, cs:__real@4d87fe3d
0x180044cee  lea     r11, cs:180000000h
0x180044cf5  movsd   xmm3, cs:__real@3fc0000000000000
0x180044cfd  add     eax, 0FFFFFFF6h; switch 111 cases
0x180044d00  movss   xmm5, cs:__real@41abe000
0x180044d08  mov     r10d, 61D3h
0x180044d0e  movsd   xmm4, cs:__real@3fe0000000000000
0x180044d16  mov     r8d, 2DAEh
0x180044d1c  movsd   xmm1, cs:__real@3fa0000000000000
0x180044d24  mov     edx, 0FFFFh
0x180044d29  cmp     eax, 6Eh
0x180044d2c  ja      def_180044D48; jumptable 0000000180044D48 default case, cases 12,14-16,18,19,21,23,27-29,36,38,39,44,49-51,53-56,58-62,65,67,69,70,72,73,76,82,85,87,95,97-100,102,105,107,108,110,112,115-117,119
0x180044d32  cdqe
0x180044d34  movzx   eax, ds:(byte_1800464D8 - 180000000h)[r11+rax]
0x180044d3d  mov     ecx, ds:(jpt_180044D48 - 180000000h)[r11+rax*4]
0x180044d45  add     rcx, r11
0x180044d48  jmp     rcx; switch jump
0x180044d4a  dec     cs:?SlowInformation@Paper@@3IA; jumptable 0000000180044D48 case 92
0x180044d50  lea     rcx, [rbp+190h+var_208]; this
0x180044d54  xor     eax, eax
0x180044d56  mov     r8d, 5C116DD1h; unsigned int
0x180044d5c  mov     r9d, 0A0007FE4h; unsigned int
0x180044d62  mov     [rsp+290h+var_270], eax; unsigned int
0x180044d66  mov     edx, 30416752h; struct Area::IntegralRecord::LongTermLocation *
0x180044d6b  mov     r12d, eax
0x180044d6e  call    ?WrapMixedMessage@IntegralRecord@Area@@YAHAEAULongTermLocation@12@III@Z; Area::IntegralRecord::WrapMixedMessage(Area::IntegralRecord::LongTermLocation &,uint,uint,uint)
0x180044d73  jmp     loc_180044CD7
0x180044d78  movzx   r12d, word ptr [rbp+190h+var_1FC]; jumptable 0000000180044D48 case 10
0x180044d7d  lea     rcx, [rbp+190h+var_208]; this
0x180044d81  add     r12w, r13w
0x180044d85  xor     eax, eax
0x180044d87  mov     r8d, 0CE7AB21Dh; unsigned int
0x180044d8d  mov     [rsp+290h+var_270], r12d; unsigned int
0x180044d92  mov     r9d, 5030000h; unsigned int
0x180044d98  mov     [rbp+190h+var_1F0], eax
0x180044d9b  mov     edx, 30416752h; struct Area::IntegralRecord::LongTermLocation *
0x180044da0  call    ?WrapMixedMessage@IntegralRecord@Area@@YAHAEAULongTermLocation@12@III@Z; Area::IntegralRecord::WrapMixedMessage(Area::IntegralRecord::LongTermLocation &,uint,uint,uint)
0x180044da5  jmp     loc_180044CD7
0x180044daa  movsd   xmm0, [rbp+190h+var_1F8]; jumptable 0000000180044D48 case 111
0x180044daf  ucomisd xmm0, xmm11
0x180044db4  jp      short loc_180044DD7
0x180044db6  jnz     short loc_180044DD7
0x180044db8  mov     r8d, 96794F78h; unsigned int
0x180044dbe  lea     rcx, [rbp+190h+var_208]; this
0x180044dc2  mov     r9d, 9BEC0000h; unsigned int
0x180044dc8  mov     edx, 30416752h; struct Area::IntegralRecord::LongTermLocation *
0x180044dcd  call    ?WrapMixedMessage@IntegralRecord@Area@@YAHAEAULongTermLocation@12@III@Z; Area::IntegralRecord::WrapMixedMessage(Area::IntegralRecord::LongTermLocation &,uint,uint,uint)
0x180044dd2  jmp     loc_180044CD7
0x180044dd7  mov     ecx, 5Ah ; 'Z'; int
0x180044ddc  call    ?AcquireLogicalOperation@ImportantTopic@Paper@@SAXH@Z; Paper::ImportantTopic::AcquireLogicalOperation(int)
0x180044de1  mov     edx, 0D164604Ah
0x180044de6  mov     rcx, 3FDF9F9F804000C0h
0x180044df0  call    GenerateMixedProvider
0x180044df5  mov     rcx, [rsp+290h+var_228]
0x180044dfa  lea     r8, [rbp+190h+var_1F0]
0x180044dfe  mov     rdx, [rsp+290h+var_218]
0x180044e03  add     rcx, 40h ; '@'
0x180044e07  call    cs:__guard_dispatch_icall_fptr
0x180044e0d  mov     r8d, 8B9B61E5h; unsigned int
0x180044e13  lea     rcx, [rbp+190h+var_208]; this
0x180044e17  mov     r9d, 66BA00h; unsigned int
0x180044e1d  mov     edx, 30416752h; struct Area::IntegralRecord::LongTermLocation *
0x180044e22  mov     rbx, rax
0x180044e25  call    ?WrapMixedMessage@IntegralRecord@Area@@YAHAEAULongTermLocation@12@III@Z; Area::IntegralRecord::WrapMixedMessage(Area::IntegralRecord::LongTermLocation &,uint,uint,uint)
0x180044e2a  jmp     loc_180044CD7
0x180044e2f  movss   xmm0, cs:?LogicalControl@Paper@@3MA; jumptable 0000000180044D48 case 20
0x180044e37  lea     rcx, [rbp+190h+var_208]; this
0x180044e3b  movdqa  xmm1, cs:__xmm@0000000000000000ffffffffffffffff
0x180044e43  addss   xmm0, xmm10
0x180044e48  add     r12w, dx
0x180044e4c  mov     cs:?SlowInformation@Paper@@3IA, 592Bh; uint Paper::SlowInformation
0x180044e56  mov     r8d, 0B2172C46h; unsigned int
0x180044e5c  mov     [rsp+290h+var_270], r12d; unsigned int
0x180044e61  mov     r9d, 0AB80000h; unsigned int
0x180044e67  mov     dword ptr [rbp+190h+var_1C0], 0
0x180044e6e  mov     edx, 30416752h; struct Area::IntegralRecord::LongTermLocation *
0x180044e73  movss   cs:?LogicalControl@Paper@@3MA, xmm0; float Paper::LogicalControl
0x180044e7b  xorps   xmm0, xmm0
0x180044e7e  movups  [rbp+190h+var_1D0], xmm0
0x180044e82  movdqu  [rbp+190h+var_1C0+4], xmm1
0x180044e87  call    ?WrapMixedMessage@IntegralRecord@Area@@YAHAEAULongTermLocation@12@III@Z; Area::IntegralRecord::WrapMixedMessage(Area::IntegralRecord::LongTermLocation &,uint,uint,uint)
0x180044e8c  jmp     loc_180044CD7
0x180044e91  comisd  xmm9, [rbp+190h+var_1F8]; jumptable 0000000180044D48 case 68
0x180044e97  lea     rcx, [rbp+190h+var_208]; this
0x180044e9b  mov     edx, 30416752h; struct Area::IntegralRecord::LongTermLocation *
0x180044ea0  jbe     short loc_180044EB8
0x180044ea2  mov     r8d, 0ADA834C6h; unsigned int
0x180044ea8  mov     r9d, 0FA000016h; unsigned int
0x180044eae  call    ?WrapMixedMessage@IntegralRecord@Area@@YAHAEAULongTermLocation@12@III@Z; Area::IntegralRecord::WrapMixedMessage(Area::IntegralRecord::LongTermLocation &,uint,uint,uint)
0x180044eb3  jmp     loc_180044CD7
0x180044eb8  xor     eax, eax
0x180044eba  mov     r8d, 0FBA6FDD7h; unsigned int
0x180044ec0  mov     r9d, 39C000h; unsigned int
0x180044ec6  mov     [rsp+290h+var_264], eax
0x180044eca  call    ?WrapMixedMessage@IntegralRecord@Area@@YAHAEAULongTermLocation@12@III@Z; Area::IntegralRecord::WrapMixedMessage(Area::IntegralRecord::LongTermLocation &,uint,uint,uint)
0x180044ecf  jmp     loc_180044CD7
0x180044ed4  mov     eax, dword ptr cs:qword_18012A008; jumptable 0000000180044D48 case 96
0x180044eda  sub     eax, [rsp+290h+var_258]
0x180044ede  movsd   xmm0, [rbp+190h+var_1F8]
0x180044ee3  comisd  xmm9, xmm0
0x180044ee8  mov     [rbp+190h+var_1FC], eax
0x180044eeb  jbe     short loc_180044F0C
0x180044eed  mov     r8d, 1961D155h; unsigned int
0x180044ef3  lea     rcx, [rbp+190h+var_208]; this
0x180044ef7  mov     r9d, 0DC000000h; unsigned int
0x180044efd  mov     edx, 30416752h; struct Area::IntegralRecord::LongTermLocation *
0x180044f02  call    ?WrapMixedMessage@IntegralRecord@Area@@YAHAEAULongTermLocation@12@III@Z; Area::IntegralRecord::WrapMixedMessage(Area::IntegralRecord::LongTermLocation &,uint,uint,uint)
0x180044f07  jmp     loc_180044CD7
0x180044f0c  ucomisd xmm0, xmm11
0x180044f11  mov     cs:?LogicalControl@Paper@@3MA, 3F600000h; float Paper::LogicalControl
0x180044f1b  jp      short loc_180044F3E
0x180044f1d  jnz     short loc_180044F3E
0x180044f1f  mov     r8d, 23112DA7h; unsigned int
0x180044f25  lea     rcx, [rbp+190h+var_208]; this
0x180044f29  mov     r9d, 0A60800h; unsigned int
0x180044f2f  mov     edx, 30416752h; struct Area::IntegralRecord::LongTermLocation *
0x180044f34  call    ?WrapMixedMessage@IntegralRecord@Area@@YAHAEAULongTermLocation@12@III@Z; Area::IntegralRecord::WrapMixedMessage(Area::IntegralRecord::LongTermLocation &,uint,uint,uint)
0x180044f39  jmp     loc_180044CD7
0x180044f3e  mov     r8d, 24FA15A6h; unsigned int
0x180044f44  lea     rcx, [rbp+190h+var_208]; this
0x180044f48  mov     r9d, 50000019h; unsigned int
0x180044f4e  lea     r15, [rbp+190h+var_1F0]
0x180044f52  mov     edx, 30416752h; struct Area::IntegralRecord::LongTermLocation *
0x180044f57  call    ?WrapMixedMessage@IntegralRecord@Area@@YAHAEAULongTermLocation@12@III@Z; Area::IntegralRecord::WrapMixedMessage(Area::IntegralRecord::LongTermLocation &,uint,uint,uint)
0x180044f5c  jmp     loc_180044CD7
0x180044f61  mov     eax, [rsp+290h+var_254]; jumptable 0000000180044D48 case 17
0x180044f65  lea     rcx, [rbp+190h+var_208]; this
0x180044f69  imul    eax, cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x180044f70  mov     r8d, 476C3A5Ah; unsigned int
0x180044f76  mov     r9d, 16B00h; unsigned int
0x180044f7c  mov     edx, 30416752h; struct Area::IntegralRecord::LongTermLocation *
0x180044f81  mov     [rbp+190h+var_1FC], eax
0x180044f84  mov     eax, [r15]
0x180044f87  mov     [rsp+290h+var_268], eax
0x180044f8b  call    ?WrapMixedMessage@IntegralRecord@Area@@YAHAEAULongTermLocation@12@III@Z; Area::IntegralRecord::WrapMixedMessage(Area::IntegralRecord::LongTermLocation &,uint,uint,uint)
0x180044f90  jmp     loc_180044CD7
0x180044f95  movzx   r12d, r8w; jumptable 0000000180044D48 case 45
0x180044f99  mov     cs:?LogicalControl@Paper@@3MA, 3F400000h; float Paper::LogicalControl
0x180044fa3  xor     eax, eax
0x180044fa5  mov     [rsp+290h+var_270], r12d; unsigned int
0x180044faa  mov     r8d, 508685CEh; unsigned int
0x180044fb0  mov     [rsp+290h+var_260], eax
0x180044fb4  mov     r9d, 84h; unsigned int
0x180044fba  mov     cs:?SlowInformation@Paper@@3IA, 295Dh; uint Paper::SlowInformation
0x180044fc4  mov     edx, 30416752h; struct Area::IntegralRecord::LongTermLocation *
0x180044fc9  lea     rcx, [rbp+190h+var_208]; this
0x180044fcd  call    ?WrapMixedMessage@IntegralRecord@Area@@YAHAEAULongTermLocation@12@III@Z; Area::IntegralRecord::WrapMixedMessage(Area::IntegralRecord::LongTermLocation &,uint,uint,uint)
0x180044fd2  jmp     loc_180044CD7
0x180044fd7  xor     eax, eax; jumptable 0000000180044D48 case 48
0x180044fd9  lea     rcx, [rbp+190h+var_208]; this
0x180044fdd  cmp     [rsp+290h+var_260], 1
0x180044fe2  mov     edx, 8AE3A4A4h
0x180044fe7  mov     r13d, eax
0x180044fea  mov     [rsp+290h+var_26C], eax
0x180044fee  mov     r8d, 29482F99h
0x180044ff4  mov     eax, 0CE860000h
0x180044ff9  mov     r9d, 39004F66h
0x180044fff  cmovge  r8d, edx; unsigned int
0x180045003  mov     edx, 30416752h; struct Area::IntegralRecord::LongTermLocation *
0x180045008  cmovge  r9d, eax; unsigned int
0x18004500c  call    ?WrapMixedMessage@IntegralRecord@Area@@YAHAEAULongTermLocation@12@III@Z; Area::IntegralRecord::WrapMixedMessage(Area::IntegralRecord::LongTermLocation &,uint,uint,uint)
0x180045011  jmp     loc_180044CD7
0x180045016  movsxd  rax, [rsp+290h+var_260]; jumptable 0000000180044D48 case 101
0x18004501b  lea     rdi, [rbp+190h+var_1D0]
0x18004501f  add     r13w, dx
0x180045023  mov     r8d, 0DE233D8Bh; unsigned int
0x180045029  mov     r9d, 7700008h; unsigned int
0x18004502f  mov     [rsp+290h+var_26C], r13d
0x180045034  mov     edx, 30416752h; struct Area::IntegralRecord::LongTermLocation *
0x180045039  lea     rcx, [rax+rax*8]
0x18004503d  lea     rdi, [rdi+rcx*4]
0x180045041  lea     rcx, [rbp+190h+var_208]; this
0x180045045  call    ?WrapMixedMessage@IntegralRecord@Area@@YAHAEAULongTermLocation@12@III@Z; Area::IntegralRecord::WrapMixedMessage(Area::IntegralRecord::LongTermLocation &,uint,uint,uint)
0x18004504a  jmp     loc_180044CD7
0x18004504f  mov     eax, [rsp+290h+var_260]; jumptable 0000000180044D48 case 120
0x180045053  add     r12w, 2
0x180045058  sub     eax, dword ptr cs:qword_18012A008
0x18004505e  cmp     [rsp+290h+var_268], 1
0x180045063  mov     [rbp+190h+var_1FC], eax
0x180045066  mov     [rsp+290h+var_270], r12d; unsigned int
0x18004506b  ja      short loc_18004508C
0x18004506d  mov     r8d, 767CAFFh; unsigned int
0x180045073  lea     rcx, [rbp+190h+var_208]; this
0x180045077  mov     r9d, 149000h; unsigned int
0x18004507d  mov     edx, 30416752h; struct Area::IntegralRecord::LongTermLocation *
0x180045082  call    ?WrapMixedMessage@IntegralRecord@Area@@YAHAEAULongTermLocation@12@III@Z; Area::IntegralRecord::WrapMixedMessage(Area::IntegralRecord::LongTermLocation &,uint,uint,uint)
0x180045087  jmp     loc_180044CD7
0x18004508c  mov     r8d, 8154CEA7h; unsigned int
0x180045092  lea     rcx, [rbp+190h+var_208]; this
0x180045096  mov     r9d, 0A4000002h; unsigned int
0x18004509c  mov     edx, 30416752h; struct Area::IntegralRecord::LongTermLocation *
0x1800450a1  call    ?WrapMixedMessage@IntegralRecord@Area@@YAHAEAULongTermLocation@12@III@Z; Area::IntegralRecord::WrapMixedMessage(Area::IntegralRecord::LongTermLocation &,uint,uint,uint)
0x1800450a6  jmp     loc_180044CD7
0x1800450ab  movss   xmm0, cs:?LogicalControl@Paper@@3MA; jumptable 0000000180044D48 case 103
0x1800450b3  lea     rcx, [rbp+190h+var_208]; this
0x1800450b7  movzx   r12d, word ptr [rsp+290h+var_25C]
0x1800450bd  addss   xmm0, xmm10
0x1800450c2  add     r12w, word ptr cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x1800450ca  mov     r8d, 39397B1Ch; unsigned int
0x1800450d0  inc     [rsp+290h+var_264]
0x1800450d4  mov     r9d, 28000067h; unsigned int
0x1800450da  mov     edx, 30416752h; struct Area::IntegralRecord::LongTermLocation *
0x1800450df  mov     [rsp+290h+var_270], r12d; unsigned int
0x1800450e4  movss   cs:?LogicalControl@Paper@@3MA, xmm0; float Paper::LogicalControl
0x1800450ec  call    ?WrapMixedMessage@IntegralRecord@Area@@YAHAEAULongTermLocation@12@III@Z; Area::IntegralRecord::WrapMixedMessage(Area::IntegralRecord::LongTermLocation &,uint,uint,uint)
0x1800450f1  jmp     loc_180044CD7
0x1800450f6  mov     rcx, cs:qword_18012A008; jumptable 0000000180044D48 case 78
0x1800450fd  mov     r8d, 5E3F068Eh; unsigned int
0x180045103  movzx   r13d, word ptr [rsp+290h+var_248]
0x180045109  mov     r9d, 8A40000h; unsigned int
0x18004510f  movsxd  rax, [rsp+290h+var_268]
0x180045114  add     r13w, cx
0x180045118  imul    r14, rax, 1DD8h
0x18004511f  movss   cs:?LogicalControl@Paper@@3MA, xmm8; float Paper::LogicalControl
0x180045128  mov     edx, 30416752h; struct Area::IntegralRecord::LongTermLocation *
0x18004512d  mov     [rsp+290h+var_26C], r13d
0x180045132  lea     r12d, [rcx+r13]
0x180045136  mov     [rbp+190h+var_1FC], 10B0h
0x18004513d  add     r14, 1D00h
0x180045144  mov     [rsp+290h+var_270], r12d; unsigned int
0x180045149  add     r14, rbx
0x18004514c  lea     rcx, [rbp+190h+var_208]; this
0x180045150  call    ?WrapMixedMessage@IntegralRecord@Area@@YAHAEAULongTermLocation@12@III@Z; Area::IntegralRecord::WrapMixedMessage(Area::IntegralRecord::LongTermLocation &,uint,uint,uint)
0x180045155  jmp     loc_180044CD7
0x18004515a  mov     eax, [rsp+290h+var_264]; jumptable 0000000180044D48 case 79
0x18004515e  lea     rcx, [rbp+190h+var_208]; this
0x180045162  movzx   r13d, word ptr [rsp+290h+var_260]
0x180045168  mov     r8d, 0E234F0CDh; unsigned int
  ... truncated ...
```
