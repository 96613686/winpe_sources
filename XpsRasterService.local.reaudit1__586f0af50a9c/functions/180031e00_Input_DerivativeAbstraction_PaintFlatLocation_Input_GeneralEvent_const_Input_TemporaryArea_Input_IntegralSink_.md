# Input::DerivativeAbstraction::PaintFlatLocation(Input::GeneralEvent const &,Input::TemporaryArea<Input::IntegralSink<short,11,int>> const &,Input::LowFilter<float> const &,Input::QuickestTopic const &)

- ea: `0x180031e00`
- end: `0x180032ca2`
- name: `?PaintFlatLocation@DerivativeAbstraction@Input@@QEAAMAEBVGeneralEvent@2@AEBV?$TemporaryArea@V?$IntegralSink@F$0L@H@Input@@@2@AEBU?$LowFilter@M@2@AEBVQuickestTopic@2@@Z`
- size: `3746`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: ``

## callers

- `0x1800333b0`

## callees

- `0x180003180`
- `0x180007b70`
- `0x18000df20`
- `0x18000e0c0`
- `0x18000e4b0`
- `0x18001eff0`
- `0x18001f070`
- `0x18001f1b0`
- `0x18001f210`
- `0x18001f270`
- `0x18001f2b0`
- `0x18001f2f0`
- `0x18001f330`
- `0x18001f370`
- `0x18001f420`
- `0x18001f4c0`
- `0x1800315d0`
- `0x180031600`
- `0x180031630`
- `0x180031660`
- `0x1800316a0`
- `0x1800316e0`
- `0x180031720`
- `0x180031770`
- `0x180031810`
- `0x180031e00`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__controlfp_s` at `0x1800329af`
- `api-ms-win-crt-private-l1-1-0!_o__controlfp_s` at `0x1800329af`

## pseudocode

```c
double __fastcall Input::DerivativeAbstraction::PaintFlatLocation(
        __int64 a1,
        __int64 a2,
        _WORD *a3,
        float *a4,
        _DWORD *a5)
{
  int v6; // r12d
  unsigned int v7; // r13d
  int v8; // r15d
  float v9; // xmm11_4
  float v10; // xmm12_4
  float v11; // xmm9_4
  float v12; // xmm7_4
  float v13; // xmm10_4
  float v14; // xmm8_4
  float v15; // xmm14_4
  unsigned int v16; // ebx
  float v17; // xmm6_4
  int v18; // esi
  bool v19; // r14
  unsigned int v20; // eax
  int v21; // eax
  unsigned int v22; // eax
  __int16 v23; // cx
  __int16 v24; // ax
  __int16 v25; // cx
  __int16 v26; // cx
  __int16 v27; // ax
  __int16 v28; // cx
  __int16 v29; // ax
  __int16 v30; // cx
  bool v31; // zf
  void (__fastcall *v32)(__int64, __int64, int *); // rax
  float (__fastcall *MixedProvider)(__int64, float *, _DWORD *); // rax
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // eax
  unsigned int v38; // eax
  unsigned int v39; // eax
  unsigned int v40; // eax
  unsigned int v41; // eax
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  unsigned int v46; // eax
  unsigned int v47; // eax
  unsigned int v48; // eax
  unsigned int v49; // ebx
  int v50; // eax
  unsigned int v51; // eax
  unsigned int v52; // eax
  unsigned int v53; // eax
  unsigned int v54; // eax
  unsigned int v55; // eax
  unsigned int v56; // eax
  double result; // xmm0_8
  bool v58; // [rsp+28h] [rbp-E0h]
  unsigned int v59; // [rsp+2Ch] [rbp-DCh]
  int v60; // [rsp+30h] [rbp-D8h]
  __int64 v61; // [rsp+38h] [rbp-D0h] BYREF
  float *v62; // [rsp+40h] [rbp-C8h]
  __int64 v63; // [rsp+48h] [rbp-C0h]
  unsigned __int8 *v64; // [rsp+50h] [rbp-B8h]
  __int64 v65; // [rsp+58h] [rbp-B0h]
  __int16 v66; // [rsp+60h] [rbp-A8h] BYREF
  int v67; // [rsp+68h] [rbp-A0h] BYREF
  int v68; // [rsp+6Ch] [rbp-9Ch]
  float v69; // [rsp+70h] [rbp-98h] BYREF
  float v70; // [rsp+74h] [rbp-94h] BYREF
  __int64 v71; // [rsp+78h] [rbp-90h] BYREF
  __int64 v72; // [rsp+80h] [rbp-88h] BYREF
  unsigned __int64 v73; // [rsp+88h] [rbp-80h] BYREF
  int v74; // [rsp+98h] [rbp-70h] BYREF
  int v75; // [rsp+9Ch] [rbp-6Ch]
  int v76; // [rsp+A0h] [rbp-68h]
  int v77; // [rsp+A4h] [rbp-64h]
  int v78; // [rsp+A8h] [rbp-60h]
  int v79; // [rsp+ACh] [rbp-5Ch]
  int v80; // [rsp+B0h] [rbp-58h]
  int v81; // [rsp+B4h] [rbp-54h]
  int v82; // [rsp+B8h] [rbp-50h]
  int v83; // [rsp+BCh] [rbp-4Ch]
  int v84; // [rsp+C0h] [rbp-48h]
  int v85; // [rsp+C4h] [rbp-44h]
  int v86; // [rsp+C8h] [rbp-40h]
  int v87; // [rsp+CCh] [rbp-3Ch]
  int v88; // [rsp+D0h] [rbp-38h]
  int v89; // [rsp+D4h] [rbp-34h]
  _DWORD v90[16]; // [rsp+D8h] [rbp-30h] BYREF
  unsigned __int8 *retaddr; // [rsp+1D0h] [rbp+C8h]

  v65 = a2;
  v63 = a1;
  v62 = a4;
  v6 = 0;
  v70 = 0.0;
  v7 = 0;
  v58 = 0;
  v60 = 0;
  v64 = 0;
  v8 = 0;
  v69 = 0.0;
  v9 = 0.0;
  v10 = 0.0;
  v59 = 0;
  v11 = 0.0;
  v61 = 0;
  v12 = 0.0;
  LOBYTE(v66) = 0;
  v13 = 0.0;
  v14 = 0.0;
  v15 = 0.0;
  v16 = 0;
  v17 = 0.0;
  LOBYTE(v18) = 0;
  v19 = 0;
  v20 = Ratio::ReflectScatteredTime<1,22>(88, 113);
  v21 = Ratio::IssueSpecialServer<2,2>(112, v20) ^ 0x55;
  while ( 2 )
  {
    switch ( v21 )
    {
      case 2:
        --Paper::SlowInformation;
        v14 = FLOAT_8_5512013e8;
        v21 = Ratio::SecureLogicalActivity<2,2>(7);
        continue;
      case 5:
        Paper::SlowInformation = (unsigned __int8)v18
                               * *((unsigned __int8 *)&ScatteredInformation::StripedSeries
                                 + 8 * (Paper::SlowInformation & 0xF)
                                 + 8);
        switch ( *a5 )
        {
          case 2:
            v30 = -a3[3];
            LOWORD(v67) = -a3[1];
            v24 = *a3;
            LOWORD(v68) = v30;
            v25 = a3[2];
            break;
          case 3:
            v28 = -a3[2];
            LOWORD(v67) = -*a3;
            v29 = a3[1];
            LOWORD(v68) = v28;
            v24 = -v29;
            v25 = -a3[3];
            break;
          case 4:
            v26 = a3[3];
            LOWORD(v67) = a3[1];
            v27 = *a3;
            LOWORD(v68) = v26;
            v24 = -v27;
            v25 = -a3[2];
            break;
          default:
            v23 = a3[2];
            LOWORD(v67) = *a3;
            v24 = a3[1];
            LOWORD(v68) = v23;
            v25 = a3[3];
            break;
        }
        v31 = a5[1] == 1;
        HIWORD(v68) = v25;
        HIWORD(v67) = v24;
        if ( v31 )
        {
          HIWORD(v67) = -v24;
          HIWORD(v68) = -v25;
        }
        v21 = Ratio::SecureLogicalActivity<2,4>(100);
        continue;
      case 6:
        v15 = FLOAT_5_5002003e8;
        Paper::LogicalControl = v11 * 0.125;
        v41 = Ratio::VisitGeneralRatio<1,96>(11);
        v21 = Ratio::SecureLogicalActivity<1,0>(49, v41) ^ 0x20;
        continue;
      case 7:
        v72 = v61;
        LODWORD(v71) = 0;
        v74 = 923746055;
        v75 = 656355095;
        v17 = (float)(v17 + v14) + 1.0;
        LOBYTE(v18) = 24;
        v76 = 906903046;
        v77 = 639512086;
        v78 = 890060037;
        v79 = 622669077;
        v80 = 873217028;
        v81 = 605826068;
        v82 = 856374019;
        v83 = 588983059;
        Paper::LogicalControl = v17 * v14;
        v84 = 839531010;
        v85 = 572140050;
        v86 = 822688001;
        v87 = 555297041;
        v88 = 805844992;
        v89 = 538454032;
        v73 = 0xEF8F2FCFF09060B0uLL;
        v90[0] = 923746055;
        v90[1] = 656355095;
        v90[2] = 906903046;
        v90[3] = 639512086;
        v90[4] = 890060037;
        v90[5] = 622669077;
        v90[6] = 873217028;
        v90[7] = 605826068;
        v90[8] = 856374019;
        v90[9] = 588983059;
        v90[10] = 839531010;
        v90[11] = 572140050;
        v90[12] = 822688001;
        v90[13] = 555297041;
        v90[14] = 805844992;
        v90[15] = 538454032;
        v49 = ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(
                &ScatteredInformation::StripedSeries,
                &v72,
                &v74)
            ^ 0xAAAAAAAA;
        v50 = ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(
                &ScatteredInformation::StripedSeries,
                &v73,
                v90);
        _o__controlfp_s(&v71, (v50 ^ 0xAAAAAAAA) - IntegralRelation::OddMap, v49);
        v21 = Ratio::SecureLogicalActivity<2,5>(67);
        v16 = v59;
        continue;
      case 9:
        LOBYTE(v66) = v8 * IntegralRelation::OddMap;
        Paper::SlowInformation = Paper::ImportantTopic::IterateIntegratedLibrary(&Paper::LogicalControl, 0x1BFu);
        IntegralRelation::OddMap = ScatteredInformation::StripedSeries ^ 0x157E9386;
        v48 = Ratio::ReflectScatteredTime<2,0>(2);
        v21 = Ratio::IssueSpecialServer<1,1>(59, v48) ^ 4;
        continue;
      case 10:
        ++Paper::SlowInformation;
        v17 = v17 + 1.0;
        LOBYTE(v18) = -90;
        Paper::ImportantTopic::AcquireLogicalOperation(5);
        v16 += 2;
        v59 = v16;
        Ratio::VisitGeneralRatio<1,96>(24);
        v21 = Ratio::SecureLogicalActivity<2,4>(29) ^ 1;
        continue;
      case 11:
        v17 = v17 + 1.0;
        Paper::ImportantTopic::AcquireLogicalOperation(36);
        v58 = 1;
        v43 = Ratio::VisitGeneralRatio<1,96>(214);
        v21 = Ratio::SecureLogicalActivity<2,3>(42, v43) ^ 0x6F;
        continue;
      case 12:
        *(_QWORD *)&result = LODWORD(FLOAT_0_73000002);
        break;
      case 13:
        LOBYTE(v66) = v16;
        v17 = v12 * Paper::LogicalControl;
        LOBYTE(v18) = 0;
        MixedProvider = (float (__fastcall *)(__int64, float *, _DWORD *))GenerateMixedProvider(
                                                                            0x7FBFBF5FE0C08060LL,
                                                                            2432974986LL,
                                                                            0x7F7F3FFFC0E080E0LL);
        v70 = MixedProvider(v63, v62, a5);
        v34 = Ratio::VisitGeneralRatio<1,96>(228);
        v21 = Ratio::SecureLogicalActivity<2,0>(153, v34) ^ 0xDB;
        continue;
      case 14:
        *(_QWORD *)&result = LODWORD(FLOAT_0_33000001);
        break;
      case 17:
        Paper::SlowInformation = (unsigned __int8)v66;
        Paper::SlowInformation = Paper::ImportantTopic::IterateIntegratedLibrary(&v70, 0x2DDu);
        Paper::LogicalControl = 1.25;
        if ( v69 > v10 && v11 > v9 && v7 == 1 && v12 > v14 && v15 > v13 )
        {
          v21 = Ratio::SecureLogicalActivity<2,4>(19);
        }
        else
        {
          v42 = Ratio::ReflectScatteredTime<1,22>(8, 61);
          v21 = Ratio::IssueSpecialServer<2,2>(25, v42) ^ 0x21;
        }
        continue;
      case 20:
        LOBYTE(v18) = IntegralRelation::OddMap;
        v16 = 0;
        v17 = v17 * v13;
        LOBYTE(v66) = -13;
        v59 = 0;
        v47 = Ratio::VisitGeneralRatio<1,96>(42);
        v21 = Ratio::SecureLogicalActivity<2,1>(45, v47) ^ 0x31;
        continue;
      case 21:
        v60 = -73659211;
        v18 = (int)(Paper::LogicalControl * 0.5);
        v35 = Ratio::ReflectScatteredTime<2,0>(106);
        v21 = Ratio::IssueSpecialServer<1,1>(39, v35) ^ 1;
        continue;
      case 28:
        Paper::ImportantTopic::AcquireLogicalOperation(7);
        LOBYTE(v18) = v61 - v66;
        v17 = FLOAT_1_875;
        Paper::ImportantTopic::AcquireLogicalOperation(40);
        if ( v16 >= 0x1E )
          v21 = Ratio::SecureLogicalActivity<2,0>(13, 4);
        else
          v21 = Ratio::SecureLogicalActivity<2,1>(15, 76);
        continue;
      case 29:
        Paper::ImportantTopic::AcquireLogicalOperation(7);
        v17 = v17 * v10;
        Paper::LogicalControl = (float)(int)Paper::ImportantTopic::IterateIntegratedLibrary(
                                              &Paper::SlowInformation,
                                              0xA2u);
        v6 = *v64;
        v21 = Ratio::SecureLogicalActivity<2,4>(52);
        continue;
      case 31:
        ++Paper::SlowInformation;
        v12 = (float)(4041074 * v8);
        v21 = Ratio::SecureLogicalActivity<2,4>(212);
        continue;
      case 37:
        v18 = (int)(v17 * 0.125);
        if ( v19 )
        {
          v21 = Ratio::SecureLogicalActivity<2,4>(15);
        }
        else
        {
          v67 = *(_DWORD *)a3;
          v68 = *((_DWORD *)a3 + 1);
          v17 = (float)(unsigned __int8)v66;
          v22 = Ratio::VisitGeneralRatio<2,8>(12);
          v21 = Ratio::SecureLogicalActivity<1,0>(3, v22) ^ 6;
        }
        continue;
      case 38:
        v64 = retaddr;
        LOBYTE(v66) = 43;
        v36 = Ratio::ReflectScatteredTime<1,22>(0, 8);
        v21 = Ratio::IssueSpecialServer<1,1>(4, v36) ^ 0x19;
        continue;
      case 39:
        Paper::SlowInformation = v7;
        if ( v62[1] <= v17 )
        {
          v12 = v12 + -1.0;
          v8 = (int)(v70 * 0.25);
          v56 = Ratio::ReflectScatteredTime<2,75>(20);
          v21 = Ratio::IssueSpecialServer<2,2>(114, v56) ^ 0x5E;
        }
        else
        {
          v21 = Ratio::SecureLogicalActivity<2,2>(232);
        }
        continue;
      case 41:
        Paper::LogicalControl = Paper::LogicalControl + -1.0;
        if ( v19 )
        {
          v21 = Ratio::SecureLogicalActivity<2,5>(66);
        }
        else
        {
          v69 = (float)(2585866 * v6);
          v21 = Ratio::SecureLogicalActivity<2,4>(123);
        }
        continue;
      case 44:
        v8 = 61332;
        v19 = !v19;
        v6 += v7;
        if ( (unsigned __int8)v66 <= (unsigned __int8)v60 )
        {
          v55 = Ratio::ReflectScatteredTime<1,22>(127, 24);
          v21 = Ratio::IssueSpecialServer<1,1>(14, v55) ^ 0x31;
        }
        else
        {
          v54 = Ratio::ReflectScatteredTime<1,22>(41, 16);
          v21 = Ratio::IssueSpecialServer<2,2>(30, v54) ^ 1;
        }
        continue;
      case 45:
        LOBYTE(v18) = Paper::SlowInformation * qword_18012A008;
        if ( v17 == v62[1] )
        {
          v21 = Ratio::SecureLogicalActivity<2,4>(32);
        }
        else
        {
          v17 = v17 + v11;
          LOBYTE(v18) = Paper::SlowInformation * qword_18012A008 + 1;
          v8 = -v6;
          v53 = Ratio::VisitGeneralRatio<2,48>(5);
          v21 = Ratio::SecureLogicalActivity<2,0>(3, v53) ^ 8;
        }
        continue;
      case 48:
        v11 = FLOAT_8_2596666e8;
        LOBYTE(v66) = IntegralRelation::CoordinatedArray;
        Ratio::VisitGeneralRatio<2,34>(6);
        v21 = Ratio::SecureLogicalActivity<2,4>(60) ^ 0x23;
        continue;
      case 53:
        Paper::SlowInformation = Paper::ImportantTopic::IterateIntegratedLibrary(&Paper::SlowInformation, 0xB6u);
        LOBYTE(v18) = Paper::ImportantTopic::IterateIntegratedLibrary(&v66, 0x7Eu);
        v38 = Paper::ImportantTopic::IterateIntegratedLibrary(&v69, 0x28Bu);
        LOBYTE(v66) = v66 - 1;
        v10 = FLOAT_5_2570022e8;
        Paper::SlowInformation = v38;
        v39 = Ratio::ReflectScatteredTime<1,22>(41, 82);
        v21 = Ratio::IssueSpecialServer<1,1>(46, v39) ^ 0x1E;
        continue;
      case 56:
        Paper::SlowInformation = (unsigned __int8)v66 * (unsigned __int8)v7;
        if ( v19 )
        {
          v51 = Ratio::ReflectScatteredTime<1,22>(0, 15);
          v21 = Ratio::IssueSpecialServer<2,2>(1, v51) ^ 6;
        }
        else
        {
          v58 = (IntegralRelation::OddMap ^ v60) != 5857510;
          v52 = Ratio::VisitGeneralRatio<2,153>(110);
          v21 = Ratio::SecureLogicalActivity<2,1>(244, v52) ^ 0xB1;
        }
        continue;
      case 59:
        v8 = 212;
        Ratio::VisitGeneralRatio<1,96>(117);
        v21 = Ratio::SecureLogicalActivity<2,4>(111) ^ 0x46;
        continue;
      case 60:
        if ( v19 )
        {
          v21 = Ratio::SecureLogicalActivity<2,4>(14);
        }
        else
        {
          v7 = 1;
          v17 = v12 - v69;
          LOBYTE(v66) = (int)(v11 * 0.03125);
          v21 = Ratio::SecureLogicalActivity<1,0>(84, 111);
        }
        continue;
      case 61:
        IntegralRelation::OddMap = ScatteredInformation::StripedSeries ^ 0x157E9386;
        v46 = Ratio::ReflectScatteredTime<1,22>(32, 10);
        v21 = Ratio::IssueSpecialServer<1,1>(5, v46) ^ 0x11;
        continue;
      case 62:
        v9 = (float)(4041074 * v6);
        v37 = Ratio::ReflectScatteredTime<2,37>(105);
        v21 = Ratio::IssueSpecialServer<1,1>(31, v37) ^ 0x2A;
        continue;
      case 63:
        if ( v19 )
        {
          v21 = Ratio::SecureLogicalActivity<2,0>(5, 0);
        }
        else
        {
          v61 = 0xAAAAAAAAA9A2A9B5uLL;
          v74 = 539504696;
          v75 = 528408;
          v76 = 573190714;
          v77 = 34214426;
          v78 = 606876732;
          v79 = 67900444;
          v80 = 640562750;
          v81 = 101586462;
          v82 = 657405759;
          v83 = 118429471;
          v84 = 623719741;
          v85 = 84743453;
          v86 = 590033723;
          v87 = 51057435;
          v88 = 556347705;
          v89 = 17371417;
          v61 = ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(
                  &ScatteredInformation::StripedSeries,
                  &v61,
                  &v74);
          v21 = Ratio::SecureLogicalActivity<2,4>(9);
        }
        continue;
      case 65:
        v13 = (float)(2585866 * v8);
        v40 = Ratio::VisitGeneralRatio<1,96>(7);
        v21 = Ratio::SecureLogicalActivity<2,7>(6, v40) ^ 4;
        continue;
      case 66:
        v58 = 0;
        v17 = v13 * v9;
        Paper::SlowInformation = v6 * (v7 - (unsigned __int8)v66);
        Ratio::VisitGeneralRatio<1,96>(14);
        v21 = Ratio::SecureLogicalActivity<2,4>(14) ^ 0x1B;
        continue;
      case 67:
        *((_QWORD *)&ScatteredInformation::StripedSeries
        + (unsigned __int8)((*((_DWORD *)&ScatteredInformation::PaintShortTermException + v16) ^ IntegralRelation::OddMap)
                          / 0x9D28AF)
        - v16
        + 1) = *((_QWORD *)&ScatteredInformation::StripedSeries
               + (unsigned __int8)((*((_DWORD *)&ScatteredInformation::PaintShortTermException + v16 + 1)
                                  ^ IntegralRelation::OddMap)
                                 / 0x9D28AF)
               - v16);
        v21 = Ratio::SecureLogicalActivity<2,0>(25, 19);
        continue;
      case 68:
        v17 = v14;
        if ( v19 )
        {
          v21 = Ratio::SecureLogicalActivity<2,4>(28);
        }
        else
        {
          v17 = Paper::LogicalControl - v14;
          v32 = (void (__fastcall *)(__int64, __int64, int *))GenerateMixedProvider(
                                                                0x7F7F3FFFC0E080E0LL,
                                                                2445590570LL,
                                                                0x7F7F3FFFC0E080E0LL);
          v32(v63, v65, &v67);
          v21 = Ratio::SecureLogicalActivity<2,0>(30, 19);
        }
        continue;
      case 69:
        LOBYTE(v66) = (int)(*v62 * 0.25);
        if ( v19 )
        {
          v44 = Ratio::ReflectScatteredTime<2,11>(14);
          v21 = Ratio::IssueSpecialServer<1,1>(21, v44) ^ 0x1F;
        }
        else if ( v58 )
        {
          v45 = Ratio::VisitGeneralRatio<1,96>(65);
          v21 = Ratio::SecureLogicalActivity<2,1>(102, v45) ^ 0x5B;
        }
        else
        {
          v21 = Ratio::SecureLogicalActivity<2,4>(45);
        }
        continue;
      case 71:
        *(_QWORD *)&result = LODWORD(v70);
        break;
      default:
        result = 0.0;
        break;
    }
    return result;
  }
}

```

## disassembly

```asm
0x180031e00  mov     rax, rsp
0x180031e03  mov     [rax+8], rbx
0x180031e07  mov     [rax+10h], rsi
0x180031e0b  mov     [rax+20h], rdi
0x180031e0f  push    rbp
0x180031e10  push    r12
0x180031e12  push    r13
0x180031e14  push    r14
0x180031e16  push    r15
0x180031e18  lea     rbp, [rax-0C8h]
0x180031e1f  sub     rsp, 1A0h
0x180031e26  movaps  xmmword ptr [rax-38h], xmm6
0x180031e2a  movaps  xmmword ptr [rax-48h], xmm7
0x180031e2e  movaps  xmmword ptr [rax-58h], xmm8
0x180031e33  movaps  xmmword ptr [rax-68h], xmm9
0x180031e38  movaps  xmmword ptr [rax-78h], xmm10
0x180031e3d  movaps  xmmword ptr [rax-88h], xmm11
0x180031e45  movaps  xmmword ptr [rax-98h], xmm12
0x180031e4d  movaps  xmmword ptr [rax-0A8h], xmm14
0x180031e55  mov     rax, cs:__security_cookie
0x180031e5c  xor     rax, rsp
0x180031e5f  mov     [rbp+0C0h+var_B0], rax
0x180031e63  xor     eax, eax
0x180031e65  mov     [rsp+1C0h+var_170], rdx
0x180031e6a  mov     [rsp+1C0h+var_180], rcx
0x180031e6f  mov     rdi, r8
0x180031e72  mov     [rsp+1C0h+var_188], r9
0x180031e77  mov     r12d, eax
0x180031e7a  mov     [rsp+1C0h+var_154], 0
0x180031e82  mov     r13d, eax
0x180031e85  lea     edx, [rax+71h]
0x180031e88  mov     byte ptr [rsp+1C0h+var_1A0], 0
0x180031e8d  lea     ecx, [rax+58h]
0x180031e90  mov     dword ptr [rsp+1C0h+var_198], eax
0x180031e94  mov     [rsp+1C0h+var_178], rax
0x180031e99  mov     r15d, eax
0x180031e9c  mov     [rsp+1C0h+var_158], eax
0x180031ea0  xorps   xmm11, xmm11
0x180031ea4  xorps   xmm12, xmm12
0x180031ea8  mov     [rsp+1C0h+var_19C], eax
0x180031eac  xorps   xmm9, xmm9
0x180031eb0  mov     [rsp+1C0h+var_190], rax
0x180031eb5  xorps   xmm7, xmm7
0x180031eb8  mov     byte ptr [rsp+1C0h+var_168], al
0x180031ebc  xorps   xmm10, xmm10
0x180031ec0  xorps   xmm8, xmm8
0x180031ec4  xorps   xmm14, xmm14
0x180031ec8  mov     ebx, eax
0x180031eca  xorps   xmm6, xmm6
0x180031ecd  xor     sil, sil
0x180031ed0  xor     r14b, r14b
0x180031ed3  call    ??$ReflectScatteredTime@$00$0BG@@Ratio@@SAIII@Z; Ratio::ReflectScatteredTime<1,22>(uint,uint)
0x180031ed8  mov     edx, eax
0x180031eda  mov     ecx, 70h ; 'p'
0x180031edf  call    ??$IssueSpecialServer@$01$01@Ratio@@SAIII@Z; Ratio::IssueSpecialServer<2,2>(uint,uint)
0x180031ee4  xor     eax, 55h
0x180031ee7  movsd   xmm1, cs:__real@3fd0000000000000
0x180031eef  lea     r11, ?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x180031ef6  movss   xmm2, cs:__real@bf800000
0x180031efe  lea     r10, cs:180000000h
0x180031f05  add     eax, 0FFFFFFFEh; switch 70 cases
0x180031f08  mov     r9, 7FBFBF5FE0C08060h
0x180031f12  mov     r8, 7F7F3FFFC0E080E0h
0x180031f1c  mov     rdx, 0AAAAAAAAA9A2A9B5h
0x180031f26  cmp     eax, 45h
0x180031f29  ja      def_180031F45; jumptable 0000000180031F45 default case, cases 3,4,8,15,16,18,19,22-27,30,32-36,40,42,43,46,47,49-52,54,55,57,58,64,70
0x180031f2f  cdqe
0x180031f31  movzx   eax, ds:(byte_180032C5C - 180000000h)[r10+rax]
0x180031f3a  mov     ecx, ds:(jpt_180031F45 - 180000000h)[r10+rax*4]
0x180031f42  add     rcx, r10
0x180031f45  jmp     rcx; switch jump
0x180031f47  xorps   xmm0, xmm0; jumptable 0000000180031F45 case 37
0x180031f4a  cvtss2sd xmm0, xmm6
0x180031f4e  mulsd   xmm0, cs:__real@3fc0000000000000
0x180031f56  cvttsd2si esi, xmm0
0x180031f5a  test    r14b, r14b
0x180031f5d  jz      short loc_180031F71
0x180031f5f  mov     edx, 8
0x180031f64  lea     ecx, [rdx+7]
0x180031f67  call    ??$SecureLogicalActivity@$01$03@Ratio@@SAIII@Z; Ratio::SecureLogicalActivity<2,4>(uint,uint)
0x180031f6c  jmp     loc_180031EE7
0x180031f71  movzx   eax, byte ptr [rsp+1C0h+var_168]
0x180031f76  mov     edx, 4
0x180031f7b  movd    xmm6, eax
0x180031f7f  lea     ecx, [rdx+8]
0x180031f82  movzx   eax, word ptr [rdi]
0x180031f85  mov     word ptr [rsp+1C0h+var_160], ax
0x180031f8a  movzx   eax, word ptr [rdi+2]
0x180031f8e  mov     word ptr [rsp+1C0h+var_160+2], ax
0x180031f93  movzx   eax, word ptr [rdi+4]
0x180031f97  mov     word ptr [rsp+1C0h+var_15C], ax
0x180031f9c  movzx   eax, word ptr [rdi+6]
0x180031fa0  mov     word ptr [rsp+1C0h+var_15C+2], ax
0x180031fa5  cvtdq2ps xmm6, xmm6
0x180031fa8  call    ??$VisitGeneralRatio@$01$07@Ratio@@SAIII@Z; Ratio::VisitGeneralRatio<2,8>(uint,uint)
0x180031fad  mov     edx, eax
0x180031faf  mov     ecx, 3
0x180031fb4  call    ??$SecureLogicalActivity@$00$0A@@Ratio@@SAIII@Z; Ratio::SecureLogicalActivity<1,0>(uint,uint)
0x180031fb9  xor     eax, 6
0x180031fbc  jmp     loc_180031EE7
0x180031fc1  mov     eax, cs:?SlowInformation@Paper@@3IA; jumptable 0000000180031F45 case 5
0x180031fc7  mov     rdx, [rbp+0C0h+arg_20]
0x180031fce  and     eax, 0Fh
0x180031fd1  movzx   ecx, byte ptr [r11+rax*8+8]
0x180031fd7  movzx   eax, sil
0x180031fdb  imul    ecx, eax
0x180031fde  mov     cs:?SlowInformation@Paper@@3IA, ecx; uint Paper::SlowInformation
0x180031fe4  mov     ecx, [rdx]
0x180031fe6  sub     ecx, 2
0x180031fe9  jz      short loc_180032058
0x180031feb  sub     ecx, 1
0x180031fee  jz      short loc_180032031
0x180031ff0  cmp     ecx, 1
0x180031ff3  jz      short loc_180032010
0x180031ff5  movzx   eax, word ptr [rdi]
0x180031ff8  movzx   ecx, word ptr [rdi+4]
0x180031ffc  mov     word ptr [rsp+1C0h+var_160], ax
0x180032001  movzx   eax, word ptr [rdi+2]
0x180032005  mov     word ptr [rsp+1C0h+var_15C], cx
0x18003200a  movzx   ecx, word ptr [rdi+6]
0x18003200e  jmp     short loc_180032077
0x180032010  movzx   eax, word ptr [rdi+2]
0x180032014  movzx   ecx, word ptr [rdi+6]
0x180032018  mov     word ptr [rsp+1C0h+var_160], ax
0x18003201d  movzx   eax, word ptr [rdi]
0x180032020  mov     word ptr [rsp+1C0h+var_15C], cx
0x180032025  neg     ax
0x180032028  movzx   ecx, word ptr [rdi+4]
0x18003202c  neg     cx
0x18003202f  jmp     short loc_180032077
0x180032031  movzx   eax, word ptr [rdi]
0x180032034  movzx   ecx, word ptr [rdi+4]
0x180032038  neg     ax
0x18003203b  neg     cx
0x18003203e  mov     word ptr [rsp+1C0h+var_160], ax
0x180032043  movzx   eax, word ptr [rdi+2]
0x180032047  mov     word ptr [rsp+1C0h+var_15C], cx
0x18003204c  neg     ax
0x18003204f  movzx   ecx, word ptr [rdi+6]
0x180032053  neg     cx
0x180032056  jmp     short loc_180032077
0x180032058  movzx   eax, word ptr [rdi+2]
0x18003205c  movzx   ecx, word ptr [rdi+6]
0x180032060  neg     ax
0x180032063  neg     cx
0x180032066  mov     word ptr [rsp+1C0h+var_160], ax
0x18003206b  movzx   eax, word ptr [rdi]
0x18003206e  mov     word ptr [rsp+1C0h+var_15C], cx
0x180032073  movzx   ecx, word ptr [rdi+4]
0x180032077  cmp     dword ptr [rdx+4], 1
0x18003207b  mov     word ptr [rsp+1C0h+var_15C+2], cx
0x180032080  mov     word ptr [rsp+1C0h+var_160+2], ax
0x180032085  jnz     short loc_180032097
0x180032087  neg     ax
0x18003208a  neg     cx
0x18003208d  mov     word ptr [rsp+1C0h+var_160+2], ax
0x180032092  mov     word ptr [rsp+1C0h+var_15C+2], cx
0x180032097  mov     edx, 20h ; ' '
0x18003209c  lea     ecx, [rdx+44h]
0x18003209f  call    ??$SecureLogicalActivity@$01$03@Ratio@@SAIII@Z; Ratio::SecureLogicalActivity<2,4>(uint,uint)
0x1800320a4  jmp     loc_180031EE7
0x1800320a9  movaps  xmm6, xmm8; jumptable 0000000180031F45 case 68
0x1800320ad  cmp     r14b, 1
0x1800320b1  jnz     short loc_1800320C5
0x1800320b3  mov     edx, 3Ah ; ':'
0x1800320b8  lea     ecx, [rdx-1Eh]
0x1800320bb  call    ??$SecureLogicalActivity@$01$03@Ratio@@SAIII@Z; Ratio::SecureLogicalActivity<2,4>(uint,uint)
0x1800320c0  jmp     loc_180031EE7
0x1800320c5  movss   xmm6, cs:?LogicalControl@Paper@@3MA; float Paper::LogicalControl
0x1800320cd  mov     edx, 91C4C02Ah
0x1800320d2  mov     rcx, r8
0x1800320d5  subss   xmm6, xmm8
0x1800320da  call    GenerateMixedProvider
0x1800320df  mov     rdx, [rsp+1C0h+var_170]
0x1800320e4  lea     r8, [rsp+1C0h+var_160]
0x1800320e9  mov     rcx, [rsp+1C0h+var_180]
0x1800320ee  call    cs:__guard_dispatch_icall_fptr
0x1800320f4  mov     edx, 13h
0x1800320f9  lea     ecx, [rdx+0Bh]
0x1800320fc  call    ??$SecureLogicalActivity@$01$0A@@Ratio@@SAIII@Z; Ratio::SecureLogicalActivity<2,0>(uint,uint)
0x180032101  jmp     loc_180031EE7
0x180032106  movaps  xmm6, xmm7; jumptable 0000000180031F45 case 13
0x180032109  mov     byte ptr [rsp+1C0h+var_168], bl
0x18003210d  mulss   xmm6, cs:?LogicalControl@Paper@@3MA; float Paper::LogicalControl
0x180032115  mov     edx, 9104408Ah
0x18003211a  mov     rcx, r9
0x18003211d  xor     sil, sil
0x180032120  call    GenerateMixedProvider
0x180032125  mov     r8, [rbp+0C0h+arg_20]
0x18003212c  mov     rdx, [rsp+1C0h+var_188]
0x180032131  mov     rcx, [rsp+1C0h+var_180]
0x180032136  call    cs:__guard_dispatch_icall_fptr
0x18003213c  mov     edx, 0DFh
0x180032141  movss   [rsp+1C0h+var_154], xmm0
0x180032147  lea     ecx, [rdx+5]
0x18003214a  call    ??$VisitGeneralRatio@$00$0GA@@Ratio@@SAIII@Z; Ratio::VisitGeneralRatio<1,96>(uint,uint)
0x18003214f  mov     edx, eax
0x180032151  mov     ecx, 99h
0x180032156  call    ??$SecureLogicalActivity@$01$0A@@Ratio@@SAIII@Z; Ratio::SecureLogicalActivity<2,0>(uint,uint)
0x18003215b  xor     eax, 0DBh
0x180032160  jmp     loc_180031EE7
0x180032165  movzx   eax, byte ptr [rsp+1C0h+var_168]; jumptable 0000000180031F45 case 66
0x18003216a  mov     ecx, r13d
0x18003216d  sub     ecx, eax
0x18003216f  mov     byte ptr [rsp+1C0h+var_1A0], 0
0x180032174  imul    ecx, r12d
0x180032178  mov     edx, 17h
0x18003217d  movaps  xmm6, xmm10
0x180032181  mulss   xmm6, xmm11
0x180032186  mov     cs:?SlowInformation@Paper@@3IA, ecx; uint Paper::SlowInformation
0x18003218c  lea     ecx, [rdx-9]
0x18003218f  call    ??$VisitGeneralRatio@$00$0GA@@Ratio@@SAIII@Z; Ratio::VisitGeneralRatio<1,96>(uint,uint)
0x180032194  mov     edx, eax
0x180032196  mov     ecx, 0Eh
0x18003219b  call    ??$SecureLogicalActivity@$01$03@Ratio@@SAIII@Z; Ratio::SecureLogicalActivity<2,4>(uint,uint)
0x1800321a0  xor     eax, 1Bh
0x1800321a3  jmp     loc_180031EE7
0x1800321a8  movss   xmm0, cs:?LogicalControl@Paper@@3MA; jumptable 0000000180031F45 case 21
0x1800321b0  mov     edx, 37h ; '7'
0x1800321b5  cvtps2pd xmm0, xmm0
0x1800321b8  mov     dword ptr [rsp+1C0h+var_198], 0FB9C0CB5h
0x1800321c0  lea     ecx, [rdx+33h]
0x1800321c3  mulsd   xmm0, cs:__real@3fe0000000000000
0x1800321cb  cvttsd2si esi, xmm0
0x1800321cf  call    ??$ReflectScatteredTime@$01$0A@@Ratio@@SAIII@Z; Ratio::ReflectScatteredTime<2,0>(uint,uint)
0x1800321d4  mov     edx, eax
0x1800321d6  mov     ecx, 27h ; '''
0x1800321db  call    ??$IssueSpecialServer@$00$00@Ratio@@SAIII@Z; Ratio::IssueSpecialServer<1,1>(uint,uint)
0x1800321e0  xor     eax, 1
0x1800321e3  jmp     loc_180031EE7
0x1800321e8  mov     rax, [rbp+0C8h]; jumptable 0000000180031F45 case 38
0x1800321ef  mov     edx, 8
0x1800321f4  xor     ecx, ecx
0x1800321f6  mov     [rsp+1C0h+var_178], rax
0x1800321fb  mov     byte ptr [rsp+1C0h+var_168], 2Bh ; '+'
0x180032200  call    ??$ReflectScatteredTime@$00$0BG@@Ratio@@SAIII@Z; Ratio::ReflectScatteredTime<1,22>(uint,uint)
0x180032205  mov     edx, eax
0x180032207  mov     ecx, 4
0x18003220c  call    ??$IssueSpecialServer@$00$00@Ratio@@SAIII@Z; Ratio::IssueSpecialServer<1,1>(uint,uint)
0x180032211  xor     eax, 19h
0x180032214  jmp     loc_180031EE7
0x180032219  mov     ecx, 7; jumptable 0000000180031F45 case 29
0x18003221e  call    ?AcquireLogicalOperation@ImportantTopic@Paper@@SAXH@Z; Paper::ImportantTopic::AcquireLogicalOperation(int)
0x180032223  mov     edx, 0A2h; unsigned int
0x180032228  mulss   xmm6, xmm12
0x18003222d  lea     rcx, ?SlowInformation@Paper@@3IA; void *
0x180032234  call    ?IterateIntegratedLibrary@ImportantTopic@Paper@@SAHPEAXI@Z; Paper::ImportantTopic::IterateIntegratedLibrary(void *,uint)
0x180032239  mov     edx, 8
0x18003223e  movd    xmm0, eax
0x180032242  mov     rax, [rsp+1C0h+var_178]
0x180032247  lea     ecx, [rdx+2Ch]
0x18003224a  cvtdq2ps xmm0, xmm0
0x18003224d  movss   cs:?LogicalControl@Paper@@3MA, xmm0; float Paper::LogicalControl
0x180032255  movzx   r12d, byte ptr [rax]
0x180032259  call    ??$SecureLogicalActivity@$01$03@Ratio@@SAIII@Z; Ratio::SecureLogicalActivity<2,4>(uint,uint)
0x18003225e  jmp     loc_180031EE7
0x180032263  cmp     r14b, 1; jumptable 0000000180031F45 case 60
0x180032267  jnz     short loc_18003227B
0x180032269  mov     edx, 5
0x18003226e  lea     ecx, [rdx+9]
0x180032271  call    ??$SecureLogicalActivity@$01$03@Ratio@@SAIII@Z; Ratio::SecureLogicalActivity<2,4>(uint,uint)
0x180032276  jmp     loc_180031EE7
0x18003227b  xorps   xmm0, xmm0
0x18003227e  mov     edx, 6Fh ; 'o'
0x180032283  cvtss2sd xmm0, xmm9
0x180032288  lea     ecx, [rdx-1Bh]
0x18003228b  lea     r13d, [rdx-6Eh]
0x18003228f  movaps  xmm6, xmm7
0x180032292  mulsd   xmm0, cs:__real@3fa0000000000000
0x18003229a  subss   xmm6, [rsp+1C0h+var_158]
0x1800322a0  cvttsd2si eax, xmm0
0x1800322a4  mov     byte ptr [rsp+1C0h+var_168], al
0x1800322a8  call    ??$SecureLogicalActivity@$00$0A@@Ratio@@SAIII@Z; Ratio::SecureLogicalActivity<1,0>(uint,uint)
0x1800322ad  jmp     loc_180031EE7
0x1800322b2  mov     edx, 11h; jumptable 0000000180031F45 case 59
0x1800322b7  lea     ecx, [rdx+64h]
0x1800322ba  lea     r15d, [rcx+5Fh]
0x1800322be  call    ??$VisitGeneralRatio@$00$0GA@@Ratio@@SAIII@Z; Ratio::VisitGeneralRatio<1,96>(uint,uint)
0x1800322c3  mov     edx, eax
0x1800322c5  lea     ecx, [r15-65h]
0x1800322c9  call    ??$SecureLogicalActivity@$01$03@Ratio@@SAIII@Z; Ratio::SecureLogicalActivity<2,4>(uint,uint)
0x1800322ce  xor     eax, 46h
0x1800322d1  jmp     loc_180031EE7
0x1800322d6  movss   xmm0, cs:?LogicalControl@Paper@@3MA; jumptable 0000000180031F45 case 41
0x1800322de  addss   xmm0, xmm2
0x1800322e2  movss   cs:?LogicalControl@Paper@@3MA, xmm0; float Paper::LogicalControl
0x1800322ea  test    r14b, r14b
0x1800322ed  jz      short loc_180032301
0x1800322ef  mov     edx, 7Ah ; 'z'
0x1800322f4  lea     ecx, [rdx-38h]
0x1800322f7  call    ??$SecureLogicalActivity@$01$04@Ratio@@SAIII@Z; Ratio::SecureLogicalActivity<2,5>(uint,uint)
0x1800322fc  jmp     loc_180031EE7
0x180032301  imul    ecx, r12d, 27750Ah
0x180032308  xorps   xmm0, xmm0
0x18003230b  mov     edx, 45h ; 'E'
0x180032310  cvtsi2ss xmm0, rcx
0x180032315  lea     ecx, [rdx+36h]
0x180032318  movss   [rsp+1C0h+var_158], xmm0
0x18003231e  call    ??$SecureLogicalActivity@$01$03@Ratio@@SAIII@Z; Ratio::SecureLogicalActivity<2,4>(uint,uint)
0x180032323  jmp     loc_180031EE7
  ... truncated ...
```
