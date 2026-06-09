# Direction::Unit::EarlyRatio::SendNullAbstraction(Direction::AvailableArray &,Setting::QuickSDK &,Setting::CommonInformation *)

- ea: `0x18006d020`
- end: `0x18006db72`
- name: `?SendNullAbstraction@EarlyRatio@Unit@Direction@@UEAA?AW4Result@Setting@@AEAVAvailableArray@3@AEAVQuickSDK@5@PEAVCommonInformation@5@@Z`
- size: `2898`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180003180`
- `0x18000df20`
- `0x18000e010`
- `0x18000e0c0`
- `0x18000e100`
- `0x18000e4b0`
- `0x180017af0`
- `0x18004d1d0`
- `0x18006cf80`
- `0x18006d020`
- `0x1800bf3b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Direction::Unit::EarlyRatio::SendNullAbstraction(
        __int64 a1,
        struct Direction::AvailableArray *a2,
        __int64 a3,
        struct Setting::CommonInformation *a4)
{
  struct Setting::CommonInformation *v4; // r14
  unsigned int v6; // edi
  unsigned int v7; // ebx
  float v8; // xmm6_4
  __int16 v9; // r12
  __int16 v10; // r13
  float v11; // xmm7_4
  unsigned __int16 v12; // r15
  int v13; // eax
  __int64 v14; // rcx
  unsigned int v15; // edx
  struct Data::Stack::OddMenu *v16; // r14
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rdi
  __int64 v20; // rdx
  __int64 v21; // rax
  unsigned __int64 v22; // rcx
  Direction::Unit::DetailedVersion *v23; // rax
  __int64 v24; // rcx
  bool v25; // al
  __int64 v26; // rbx
  __int64 (__fastcall *MixedProvider)(__int64); // rax
  __int64 v28; // rbx
  unsigned __int8 (__fastcall *v29)(__int64); // rax
  float v30; // xmm0_4
  unsigned int *v32; // [rsp+28h] [rbp-E0h]
  int v33; // [rsp+30h] [rbp-D8h]
  struct Setting::CommonInformation *v34; // [rsp+38h] [rbp-D0h]
  __int128 v37; // [rsp+68h] [rbp-A0h]
  __int128 v38; // [rsp+78h] [rbp-90h]
  __int128 v39; // [rsp+88h] [rbp-80h]
  __m256i v40; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v41; // [rsp+D8h] [rbp-30h]
  __int128 v42; // [rsp+E8h] [rbp-20h]
  unsigned int v43[2]; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v44; // [rsp+100h] [rbp-8h] BYREF
  _QWORD v45[2]; // [rsp+108h] [rbp+0h] BYREF
  __int128 v46; // [rsp+118h] [rbp+10h] BYREF
  __int128 v47; // [rsp+128h] [rbp+20h]
  __int128 v48; // [rsp+138h] [rbp+30h]
  __int128 v49; // [rsp+148h] [rbp+40h]
  __int128 v50; // [rsp+158h] [rbp+50h]
  __m256i v51; // [rsp+168h] [rbp+60h]
  __int128 v52; // [rsp+188h] [rbp+80h]
  __int128 v53; // [rsp+198h] [rbp+90h]
  __int128 v54; // [rsp+1A8h] [rbp+A0h]
  _DWORD v55[3]; // [rsp+1B8h] [rbp+B0h] BYREF
  __int64 v56; // [rsp+1C4h] [rbp+BCh]
  int v57; // [rsp+1CCh] [rbp+C4h]
  int v58; // [rsp+1D0h] [rbp+C8h]
  int v59; // [rsp+1D4h] [rbp+CCh]

  v4 = a4;
  v34 = a4;
  v6 = 0;
  v7 = 0;
  *(_QWORD *)v43 = &Area::IntegralRecord::StoreRightQuality::`vftable';
  v55[0] = 7084;
  v55[1] = 2655;
  v55[2] = 590;
  v56 = 2652;
  v57 = 590;
  v58 = 1771;
  v59 = 1105;
  v8 = 0.0;
  v9 = 0;
  v10 = 0;
  v11 = 0.0;
  v12 = 0;
  v13 = Area::IntegralRecord::MoveEvenAssignment(
          (Area::IntegralRecord *)0x80000668LL,
          0x247B773Du,
          (unsigned int)v43,
          (struct Area::IntegralRecord::LongTermLocation *)v55,
          0);
  while ( 1 )
  {
    switch ( v13 )
    {
      case 1:
        Paper::LogicalControl = Paper::LogicalControl + 1.0;
        --Paper::SlowInformation;
        v26 = *(_QWORD *)(v44 + 8);
        MixedProvider = (__int64 (__fastcall *)(__int64))GenerateMixedProvider(
                                                           0x1F9FBF3FE0808040LL,
                                                           4045684970LL,
                                                           0x3FF2000000000000LL,
                                                           4009754828LL);
        v7 = MixedProvider(v26);
        LODWORD(v32) = v7;
        v13 = Area::IntegralRecord::MoveEvenAssignment(
                (Area::IntegralRecord *)0xC00004BCLL,
                0x58C12978u,
                (unsigned int)v43,
                (struct Area::IntegralRecord::LongTermLocation *)v55,
                v32);
        continue;
      case 4:
        v12 = WORD4(v48) - WORD6(v48);
        v11 = (float)(int)Paper::ImportantTopic::IterateIntegratedLibrary((void *)(a3 + 40), 0x279u);
        v45[0] = &MixedInformation::`vftable';
        v13 = Area::IntegralRecord::MoveEvenAssignment(
                (Area::IntegralRecord *)0xCC900000LL,
                0x2AA4D7D3u,
                (unsigned int)v43,
                (struct Area::IntegralRecord::LongTermLocation *)v55,
                v32);
        continue;
      case 11:
        v30 = *(double *)(a3 + 16);
        *((double *)&v49 + 1) = v30;
        *((double *)&v50 + 1) = (float)((float)*((double *)&v50 + 1) + *(double *)(a3 + 32));
        v13 = Area::IntegralRecord::MoveEvenAssignment(
                (Area::IntegralRecord *)0x40000202,
                0x680DA810u,
                (unsigned int)v43,
                (struct Area::IntegralRecord::LongTermLocation *)v55,
                v32);
        continue;
      case 14:
        v10 = v9;
        Paper::LogicalControl = v11;
        v7 = 4;
        v9 = -12960;
        LODWORD(v32) = 4;
        v13 = Area::IntegralRecord::MoveEvenAssignment(
                (Area::IntegralRecord *)0xA9480004LL,
                0x5259BF11u,
                (unsigned int)v43,
                (struct Area::IntegralRecord::LongTermLocation *)v55,
                v32);
        continue;
      case 15:
        v10 = -29343;
        v13 = Area::IntegralRecord::MoveEvenAssignment(
                (Area::IntegralRecord *)0x5A0F600,
                0x87513ADB,
                (unsigned int)v43,
                (struct Area::IntegralRecord::LongTermLocation *)v55,
                v32);
        continue;
      case 21:
        v12 = WORD2(v47);
        v7 = 2;
        LODWORD(v32) = 2;
        v13 = Area::IntegralRecord::MoveEvenAssignment(
                (Area::IntegralRecord *)0xCD70000,
                0xDE46E812,
                (unsigned int)v43,
                (struct Area::IntegralRecord::LongTermLocation *)v55,
                v32);
        continue;
      case 22:
        Paper::ImportantTopic::AcquireLogicalOperation(82);
        v11 = (float)*(double *)(a3 + 24) * *((double *)&v46 + 1);
        v12 = IntegralRelation::OddMap;
        Paper::ImportantTopic::AcquireLogicalOperation(58);
        v13 = Area::IntegralRecord::MoveEvenAssignment(
                (Area::IntegralRecord *)0x8A000002LL,
                0x45C4DEE2u,
                (unsigned int)v43,
                (struct Area::IntegralRecord::LongTermLocation *)v55,
                v32);
        continue;
      case 23:
        *((double *)&v46 + 1) = DOUBLE_1_0;
        if ( *(_DWORD *)(a3 + 88) >= SLODWORD(qword_180129C98[Paper::SlowInformation & 0xF]) )
        {
          qword_180129C70 = *(_QWORD *)Paper::ImportantTopic::AttachEvenSector(*(int *)(a3 + 12), 0, (void *)(a3 + 52));
          LOBYTE(v48) = *(double *)(a3 + 40) * 0.0625 != 0.0;
          v13 = Area::IntegralRecord::MoveEvenAssignment(
                  (Area::IntegralRecord *)0x83000012LL,
                  0x3111A6F5u,
                  (unsigned int)v43,
                  (struct Area::IntegralRecord::LongTermLocation *)v55,
                  v32);
        }
        else
        {
          v13 = Area::IntegralRecord::MoveEvenAssignment(
                  (Area::IntegralRecord *)0x580000A7,
                  0xF12F8589,
                  (unsigned int)v43,
                  (struct Area::IntegralRecord::LongTermLocation *)v55,
                  v32);
        }
        continue;
      case 25:
        ++v9;
        Paper::ImportantTopic::AcquireLogicalOperation(4);
        Paper::SlowInformation = qword_18012A008 * v12 + 1;
        BYTE3(v38) = 0;
        HIDWORD(v39) = 0;
        memset(&v40.m256i_u64[1], 0, 24);
        *((_QWORD *)&v37 + 1) = *(_QWORD *)a3;
        *((_QWORD *)&v41 + 1) = *(_QWORD *)(a3 + 60);
        *(_QWORD *)&v42 = *(_QWORD *)(a3 + 68);
        *((_QWORD *)&v42 + 1) = *(unsigned int *)(a3 + 76);
        *(_QWORD *)&v41 = *(_QWORD *)(a3 + 96);
        LOBYTE(v38) = *(_BYTE *)(a3 + 49);
        *(_WORD *)((char *)&v38 + 1) = *(unsigned __int8 *)(a3 + 48);
        v40.m256i_i64[0] = *(unsigned int *)(a3 + 80);
        DWORD2(v38) = *(_DWORD *)(a3 + 52);
        LODWORD(v39) = *(_DWORD *)(a3 + 56);
        *(_QWORD *)((char *)&v39 + 4) = *(unsigned int *)(a3 + 84);
        DWORD1(v38) = *(_DWORD *)(a3 + 92);
        HIDWORD(v38) = *(_DWORD *)(a3 + 88);
        *(_QWORD *)&v37 = *(_QWORD *)(a3 + 8);
        v46 = *(_OWORD *)(a3 + 32);
        v47 = v37;
        v48 = v38;
        v49 = v39;
        v50 = 0u;
        v51 = v40;
        v52 = 0u;
        v53 = v41;
        v54 = v42;
        v13 = Area::IntegralRecord::MoveEvenAssignment(
                (Area::IntegralRecord *)0xACAE0000LL,
                0xC26AE25F,
                (unsigned int)v43,
                (struct Area::IntegralRecord::LongTermLocation *)v55,
                v32);
        continue;
      case 27:
        if ( v9 == *(_WORD *)(a3 + 4) )
        {
          v13 = Area::IntegralRecord::MoveEvenAssignment(
                  (Area::IntegralRecord *)0x260000AC,
                  0x6102C7C8u,
                  (unsigned int)v43,
                  (struct Area::IntegralRecord::LongTermLocation *)v55,
                  v32);
        }
        else
        {
          *((double *)&v46 + 1) = (float)(Paper::LogicalControl * *(double *)(a3 + 32));
          *((double *)&v50 + 1) = v8;
          *(_QWORD *)(a3 + 40) = 0x3FF2000000000000LL;
          if ( v9 == WORD4(v48) )
            v13 = Area::IntegralRecord::MoveEvenAssignment(
                    (Area::IntegralRecord *)0xEE0095AELL,
                    0xDDB065F3,
                    (unsigned int)v43,
                    (struct Area::IntegralRecord::LongTermLocation *)v55,
                    v32);
          else
            v13 = Area::IntegralRecord::MoveEvenAssignment(
                    (Area::IntegralRecord *)0x1EB90000,
                    0x82F0E8EE,
                    (unsigned int)v43,
                    (struct Area::IntegralRecord::LongTermLocation *)v55,
                    v32);
        }
        continue;
      case 28:
        v9 = v12;
        ++v10;
        v25 = v44 && *(_BYTE *)(v44 + 16) && *(_QWORD *)(v44 + 8) && *(int *)v44 > 0;
        v14 = 3221225606LL;
        if ( !v25 )
          v14 = 4009754828LL;
        v15 = 413757098;
        if ( !v25 )
          v15 = -1376788709;
        goto LABEL_14;
      case 29:
        if ( *((double *)&v50 + 1) <= (float)*(double *)(a3 + 32) )
        {
          *(double *)(a3 + 24) = (float)*(double *)&v46;
          v13 = Area::IntegralRecord::MoveEvenAssignment(
                  (Area::IntegralRecord *)0xB0000025LL,
                  0x20D600DEu,
                  (unsigned int)v43,
                  (struct Area::IntegralRecord::LongTermLocation *)v55,
                  v32);
        }
        else
        {
          v13 = Area::IntegralRecord::MoveEvenAssignment(
                  (Area::IntegralRecord *)0xEF00000CLL,
                  0x81E89EA2,
                  (unsigned int)v43,
                  (struct Area::IntegralRecord::LongTermLocation *)v55,
                  v32);
        }
        continue;
      case 30:
        v8 = FLOAT_0_875;
        v10 = v12;
        Paper::LogicalControl = (float)v12;
        if ( (*(int (__fastcall **)(struct Direction::AvailableArray *, unsigned __int64, __int64, __int64))(*(_QWORD *)a2 + 16LL))(
               a2,
               0x180000000uLL,
               0x3FF2000000000000LL,
               4009754828LL) <= 0 )
          v13 = Area::IntegralRecord::MoveEvenAssignment(
                  (Area::IntegralRecord *)0x300002AA,
                  0x419CBCAFu,
                  (unsigned int)v43,
                  (struct Area::IntegralRecord::LongTermLocation *)v55,
                  v32);
        else
          v13 = Area::IntegralRecord::MoveEvenAssignment(
                  (Area::IntegralRecord *)0x20240000,
                  0xDEE0F0CC,
                  (unsigned int)v43,
                  (struct Area::IntegralRecord::LongTermLocation *)v55,
                  v32);
        continue;
      case 34:
        v11 = v11 + -1.0;
        v10 = 0;
        v7 = 7;
        LODWORD(v32) = 7;
        v13 = Area::IntegralRecord::MoveEvenAssignment(
                (Area::IntegralRecord *)0x30000B8,
                0xE58F05BA,
                (unsigned int)v43,
                (struct Area::IntegralRecord::LongTermLocation *)v55,
                v32);
        continue;
      case 35:
        Paper::ImportantTopic::AcquireLogicalOperation(52);
        v9 = Paper::ImportantTopic::IterateIntegratedLibrary((void *)(a3 + 16), 0x1B2u);
        Data::Stack::ConstructInstruction<Direction::Unit::DetailedVersion,64>::CallComplexSkill(&v44);
        v13 = Area::IntegralRecord::MoveEvenAssignment(
                (Area::IntegralRecord *)0x69000067,
                0x316F43BAu,
                (unsigned int)v43,
                (struct Area::IntegralRecord::LongTermLocation *)v55,
                v32);
        continue;
      case 36:
        v12 = v10 - *(_WORD *)a3;
        v28 = *(_QWORD *)(v44 + 8);
        v29 = (unsigned __int8 (__fastcall *)(__int64))GenerateMixedProvider(
                                                         0xFF7FDF9FC0C0C0C0uLL,
                                                         298065994,
                                                         0x3FF2000000000000LL,
                                                         4009754828LL);
        if ( v29(v28) )
        {
          v7 = (unsigned int)v32;
          v13 = Area::IntegralRecord::MoveEvenAssignment(
                  (Area::IntegralRecord *)0x17D90000,
                  0x1290524Au,
                  (unsigned int)v43,
                  (struct Area::IntegralRecord::LongTermLocation *)v55,
                  v32);
        }
        else
        {
          v7 = (unsigned int)v32;
          v13 = Area::IntegralRecord::MoveEvenAssignment(
                  (Area::IntegralRecord *)0xB533800,
                  0xB365D1Fu,
                  (unsigned int)v43,
                  (struct Area::IntegralRecord::LongTermLocation *)v55,
                  v32);
        }
        continue;
      case 38:
        return v7;
      case 40:
        v8 = v8 + 1.0;
        if ( Direction::UniqueBinary::LoopOptimalOperation(
               *(Direction::UniqueBinary **)(v44 + 8),
               (const struct Binary::ActiveCategory *)&v46) )
        {
          v13 = Area::IntegralRecord::MoveEvenAssignment(
                  (Area::IntegralRecord *)0x20000002,
                  0x5D2AA25Eu,
                  (unsigned int)v43,
                  (struct Area::IntegralRecord::LongTermLocation *)v55,
                  v32);
        }
        else
        {
          v13 = Area::IntegralRecord::MoveEvenAssignment(
                  (Area::IntegralRecord *)0xA0000208LL,
                  0xC414E9CD,
                  (unsigned int)v43,
                  (struct Area::IntegralRecord::LongTermLocation *)v55,
                  v32);
        }
        continue;
      case 43:
        v9 = *(_WORD *)a3 + v10;
        v8 = v8 * 0.25;
        Paper::LogicalControl = *(double *)(a3 + 40);
        v7 = 8;
        LODWORD(v32) = 8;
        v13 = Area::IntegralRecord::MoveEvenAssignment(
                (Area::IntegralRecord *)0x5338000B,
                0x6E8E2DA7u,
                (unsigned int)v43,
                (struct Area::IntegralRecord::LongTermLocation *)v55,
                v32);
        continue;
      case 46:
        v9 += IntegralRelation::OddMap;
        ++v12;
        v11 = v8 * 0.03125;
        v14 = 1714880512;
        if ( v4 )
          v14 = 1610614389;
        v15 = 907222798;
        if ( v4 )
          v15 = -1733870630;
LABEL_14:
        v13 = Area::IntegralRecord::MoveEvenAssignment(
                (Area::IntegralRecord *)v14,
                v15,
                (unsigned int)v43,
                (struct Area::IntegralRecord::LongTermLocation *)v55,
                v32);
        break;
      case 47:
        if ( *(_DWORD *)a3 >= *(_DWORD *)(a3 + 4) )
        {
          *(_BYTE *)(a3 + 48) = *(unsigned __int8 *)(a3 + 48) + (unsigned __int8)v48 != 0;
          v11 = *(double *)(a3 + 40) - v8;
          v13 = Area::IntegralRecord::MoveEvenAssignment(
                  (Area::IntegralRecord *)0x66E40004,
                  0xAE6B514F,
                  (unsigned int)v43,
                  (struct Area::IntegralRecord::LongTermLocation *)v55,
                  v32);
        }
        else
        {
          v13 = Area::IntegralRecord::MoveEvenAssignment(
                  (Area::IntegralRecord *)0x98C20011LL,
                  0x23C4093u,
                  (unsigned int)v43,
                  (struct Area::IntegralRecord::LongTermLocation *)v55,
                  v32);
        }
        continue;
      case 48:
        v11 = FLOAT_4_0;
        v8 = *(double *)(a3 + 32) - (float)*((double *)&v50 + 1);
        v16 = *(struct Data::Stack::OddMenu **)(a1 + 8);
        v17 = 0;
        v33 = v6 | 1;
        HIDWORD(v32) = v6 | 1;
        v18 = (**(__int64 (__fastcall ***)(struct Data::Stack::OddMenu *, __int64, __int64, __int64))v16)(
                v16,
                46528,
                0x3FF2000000000000LL,
                4009754828LL);
        v19 = v18;
        if ( v18 )
        {
          v20 = v18 + 32;
          v21 = ((_BYTE)v18 + 32) & 0x3F;
          v22 = 64 - v21;
          if ( !v21 )
            v22 = 0;
          if ( v22 > 0xB5A0 || (v23 = (Direction::Unit::DetailedVersion *)(v20 + v22), 46496 - v22 < 0xB560) )
            v23 = 0;
          *(_DWORD *)v19 = 1;
          *(_QWORD *)(v19 + 8) = v23;
          *(_BYTE *)(v19 + 16) = 0;
          *(_QWORD *)(v19 + 24) = v16;
          v17 = v19;
          if ( *(_BYTE *)(v19 + 16) || !v23 )
          {
            v44 = v19;
            if ( v19 )
              ++*(_DWORD *)v19;
          }
          else
          {
            Direction::Unit::DetailedVersion::DetailedVersion(v23, v34, a2, v16);
            *(_BYTE *)(v19 + 16) = 1;
            v44 = v19;
            ++*(_DWORD *)v19;
          }
        }
        else
        {
          v44 = 0;
        }
        v6 = v33 & 0xFFFFFFFE;
        if ( v17 )
        {
          if ( (int)--*(_DWORD *)v17 <= 0 )
          {
            v24 = *(_QWORD *)(v17 + 8);
            if ( v24 )
              (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 16LL))(v24, 0);
            *(_QWORD *)(v17 + 8) = 0;
            (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v17 + 24) + 8LL))(*(_QWORD *)(v17 + 24), v17);
          }
        }
        v7 = (unsigned int)v32;
        v4 = v34;
        v13 = Area::IntegralRecord::MoveEvenAssignment(
                (Area::IntegralRecord *)0x40000919,
                0xB0686828,
                (unsigned int)v43,
                (struct Area::IntegralRecord::LongTermLocation *)v55,
                v32);
        continue;
      case 50:
        Paper::LogicalControl = *((double *)&v46 + 1);
        v12 = *(_WORD *)(a3 + 12);
        v4 = (struct Setting::CommonInformation *)v45;
        v34 = (struct Setting::CommonInformation *)v45;
        v13 = Area::IntegralRecord::MoveEvenAssignment(
                (Area::IntegralRecord *)0x50000667,
                0xBC161F1B,
                (unsigned int)v43,
                (struct Area::IntegralRecord::LongTermLocation *)v55,
                v32);
        continue;
      default:
        return 0;
    }
  }
}

```

## disassembly

```asm
0x18006d020  mov     rax, rsp
0x18006d023  push    rbp
0x18006d024  push    rbx
0x18006d025  push    rsi
0x18006d026  push    rdi
0x18006d027  push    r12
0x18006d029  push    r13
0x18006d02b  push    r14
0x18006d02d  push    r15
0x18006d02f  lea     rbp, [rax-168h]
0x18006d036  sub     rsp, 228h
0x18006d03d  movaps  xmmword ptr [rax-58h], xmm6
0x18006d041  movaps  xmmword ptr [rax-68h], xmm7
0x18006d045  movaps  xmmword ptr [rax-78h], xmm9
0x18006d04a  movaps  xmmword ptr [rax-88h], xmm10
0x18006d052  mov     rax, cs:__security_cookie
0x18006d059  xor     rax, rsp
0x18006d05c  mov     [rbp+160h+var_90], rax
0x18006d063  mov     r14, r9
0x18006d066  mov     [rsp+260h+var_230], r9
0x18006d06b  mov     rsi, r8
0x18006d06e  mov     [rsp+260h+var_228], rdx
0x18006d073  mov     qword ptr [rsp+260h+var_218], rcx
0x18006d078  xor     ecx, ecx
0x18006d07a  mov     edi, ecx
0x18006d07c  mov     dword ptr [rsp+260h+var_240+4], ecx
0x18006d080  mov     ebx, ecx
0x18006d082  mov     dword ptr [rsp+260h+var_240], ecx; unsigned int *
0x18006d086  lea     rax, ??_7StoreRightQuality@IntegralRecord@Area@@6B@; const Area::IntegralRecord::StoreRightQuality::`vftable'
0x18006d08d  mov     qword ptr [rbp+160h+var_170], rax
0x18006d091  mov     [rbp+160h+var_B0], 1BACh
0x18006d09b  mov     [rbp+160h+var_AC], 0A5Fh
0x18006d0a5  mov     [rbp+160h+var_A8], 24Eh
0x18006d0af  mov     [rbp+160h+var_A4], 0A5Ch
0x18006d0ba  mov     [rbp+160h+var_9C], 24Eh
0x18006d0c4  mov     [rbp+160h+var_98], 6EBh
0x18006d0ce  mov     [rbp+160h+var_94], 451h
0x18006d0d8  xorps   xmm6, xmm6
0x18006d0db  movzx   r12d, cx
0x18006d0df  mov     r13d, ecx
0x18006d0e2  xorps   xmm7, xmm7
0x18006d0e5  movzx   r15d, cx
0x18006d0e9  lea     r9, [rbp+160h+var_B0]; struct Area::IntegralRecord::LongTermLocation *
0x18006d0f0  lea     r8, [rbp+160h+var_170]; unsigned int
0x18006d0f4  mov     edx, 247B773Dh; unsigned int
0x18006d0f9  mov     ecx, 80000668h; this
0x18006d0fe  call    ?MoveEvenAssignment@IntegralRecord@Area@@YAHIIAEAULongTermLocation@12@PEAI@Z; Area::IntegralRecord::MoveEvenAssignment(uint,uint,Area::IntegralRecord::LongTermLocation &,uint *)
0x18006d103  xorps   xmm9, xmm9
0x18006d107  movsd   xmm10, cs:__real@3ff0000000000000
0x18006d110  mov     r8, 3FF2000000000000h
0x18006d11a  mov     r10d, 0ADEFDF1Bh
0x18006d120  mov     r9d, 0EF0000CCh
0x18006d126  mov     r11d, 60000675h
0x18006d12c  lea     rdx, cs:180000000h
0x18006d133  dec     eax; switch 50 cases
0x18006d135  cmp     eax, 31h
0x18006d138  ja      def_18006D152; jumptable 000000018006D152 default case, cases 2,3,5-10,12,13,16-20,24,26,31-33,37,39,41,42,44,45,49
0x18006d13e  cdqe
0x18006d140  movzx   eax, ds:(byte_18006DB40 - 180000000h)[rdx+rax]
0x18006d148  mov     ecx, ds:(jpt_18006D152 - 180000000h)[rdx+rax*4]
0x18006d14f  add     rcx, rdx
0x18006d152  jmp     rcx; switch jump
0x18006d154  movzx   r13d, r12w; jumptable 000000018006D152 case 14
0x18006d158  movss   cs:?LogicalControl@Paper@@3MA, xmm7; float Paper::LogicalControl
0x18006d160  mov     ebx, 4
0x18006d165  mov     r12d, 0CD60h
0x18006d16b  mov     dword ptr [rsp+260h+var_240], ebx; unsigned int *
0x18006d16f  mov     ecx, 0A9480004h; this
0x18006d174  mov     edx, 5259BF11h; unsigned int
0x18006d179  lea     r8, [rbp+160h+var_170]; unsigned int
0x18006d17d  lea     r9, [rbp+160h+var_B0]; struct Area::IntegralRecord::LongTermLocation *
0x18006d184  call    ?MoveEvenAssignment@IntegralRecord@Area@@YAHIIAEAULongTermLocation@12@PEAI@Z; Area::IntegralRecord::MoveEvenAssignment(uint,uint,Area::IntegralRecord::LongTermLocation &,uint *)
0x18006d189  jmp     short loc_18006D110
0x18006d18b  movss   xmm6, cs:__real@3f600000; jumptable 000000018006D152 case 30
0x18006d193  movzx   r13d, r15w
0x18006d197  xorps   xmm0, xmm0
0x18006d19a  cvtsi2ss xmm0, r13
0x18006d19f  movss   cs:?LogicalControl@Paper@@3MA, xmm0; float Paper::LogicalControl
0x18006d1a7  mov     rcx, [rsp+260h+var_228]
0x18006d1ac  mov     rax, [rcx]
0x18006d1af  mov     rax, [rax+10h]
0x18006d1b3  call    cs:__guard_dispatch_icall_fptr
0x18006d1b9  test    eax, eax
0x18006d1bb  jle     short loc_18006D1DC
0x18006d1bd  mov     ecx, 20240000h; this
0x18006d1c2  mov     edx, 0DEE0F0CCh; unsigned int
0x18006d1c7  lea     r8, [rbp+160h+var_170]; unsigned int
0x18006d1cb  lea     r9, [rbp+160h+var_B0]; struct Area::IntegralRecord::LongTermLocation *
0x18006d1d2  call    ?MoveEvenAssignment@IntegralRecord@Area@@YAHIIAEAULongTermLocation@12@PEAI@Z; Area::IntegralRecord::MoveEvenAssignment(uint,uint,Area::IntegralRecord::LongTermLocation &,uint *)
0x18006d1d7  jmp     loc_18006D110
0x18006d1dc  mov     ecx, 300002AAh; this
0x18006d1e1  mov     edx, 419CBCAFh; unsigned int
0x18006d1e6  lea     r8, [rbp+160h+var_170]; unsigned int
0x18006d1ea  lea     r9, [rbp+160h+var_B0]; struct Area::IntegralRecord::LongTermLocation *
0x18006d1f1  call    ?MoveEvenAssignment@IntegralRecord@Area@@YAHIIAEAULongTermLocation@12@PEAI@Z; Area::IntegralRecord::MoveEvenAssignment(uint,uint,Area::IntegralRecord::LongTermLocation &,uint *)
0x18006d1f6  jmp     loc_18006D110
0x18006d1fb  addss   xmm7, cs:__real@bf800000; jumptable 000000018006D152 case 34
0x18006d203  xor     r13d, r13d
0x18006d206  mov     ebx, 7
0x18006d20b  mov     dword ptr [rsp+260h+var_240], ebx; unsigned int *
0x18006d20f  mov     ecx, 30000B8h; this
0x18006d214  mov     edx, 0E58F05BAh; unsigned int
0x18006d219  lea     r8, [rbp+160h+var_170]; unsigned int
0x18006d21d  lea     r9, [rbp+160h+var_B0]; struct Area::IntegralRecord::LongTermLocation *
0x18006d224  call    ?MoveEvenAssignment@IntegralRecord@Area@@YAHIIAEAULongTermLocation@12@PEAI@Z; Area::IntegralRecord::MoveEvenAssignment(uint,uint,Area::IntegralRecord::LongTermLocation &,uint *)
0x18006d229  jmp     loc_18006D110
0x18006d22e  inc     r12w; jumptable 000000018006D152 case 25
0x18006d232  mov     ecx, 4; int
0x18006d237  call    ?AcquireLogicalOperation@ImportantTopic@Paper@@SAXH@Z; Paper::ImportantTopic::AcquireLogicalOperation(int)
0x18006d23c  movzx   eax, r15w
0x18006d240  imul    eax, dword ptr cs:qword_18012A008
0x18006d247  inc     eax
0x18006d249  mov     cs:?SlowInformation@Paper@@3IA, eax; uint Paper::SlowInformation
0x18006d24f  xor     eax, eax
0x18006d251  mov     word ptr [rsp+260h+var_1F0+2], ax
0x18006d256  mov     [rbp+160h+var_1BC], eax
0x18006d259  mov     [rbp+160h+var_174], eax
0x18006d25c  xorps   xmm0, xmm0
0x18006d25f  movups  [rbp+160h+var_1D8], xmm0
0x18006d263  movsd   [rbp+160h+var_1C8], xmm9
0x18006d269  xorps   xmm1, xmm1
0x18006d26c  movdqu  [rbp+160h+var_1B8], xmm1
0x18006d271  movdqu  [rbp+160h+var_1A8], xmm0
0x18006d276  mov     [rbp+160h+var_198], rax
0x18006d27a  mov     eax, [rsi]
0x18006d27c  mov     dword ptr [rsp+260h+var_1F8], eax
0x18006d280  mov     eax, [rsi+4]
0x18006d283  mov     [rsp+260h+var_1F4], eax
0x18006d287  mov     eax, [rsi+3Ch]
0x18006d28a  mov     [rbp+160h+var_188], eax
0x18006d28d  mov     eax, [rsi+40h]
0x18006d290  mov     [rbp+160h+var_184], eax
0x18006d293  mov     eax, [rsi+44h]
0x18006d296  mov     [rbp+160h+var_180], eax
0x18006d299  mov     eax, [rsi+48h]
0x18006d29c  mov     [rbp+160h+var_17C], eax
0x18006d29f  mov     eax, [rsi+4Ch]
0x18006d2a2  mov     [rbp+160h+var_178], eax
0x18006d2a5  mov     rax, [rsi+60h]
0x18006d2a9  mov     [rbp+160h+var_190], rax
0x18006d2ad  movzx   eax, byte ptr [rsi+31h]
0x18006d2b1  mov     byte ptr [rsp+260h+var_1F0], al
0x18006d2b5  movzx   eax, byte ptr [rsi+30h]
0x18006d2b9  mov     byte ptr [rsp+260h+var_1F0+1], al
0x18006d2bd  mov     eax, [rsi+50h]
0x18006d2c0  mov     [rbp+160h+var_1C0], eax
0x18006d2c3  mov     eax, [rsi+34h]
0x18006d2c6  mov     [rsp+260h+var_1E8], eax
0x18006d2ca  mov     eax, [rsi+38h]
0x18006d2cd  mov     [rbp+160h+var_1E0], eax
0x18006d2d0  mov     eax, [rsi+54h]
0x18006d2d3  mov     [rbp+160h+var_1DC], eax
0x18006d2d6  mov     eax, [rsi+5Ch]
0x18006d2d9  mov     [rsp+260h+var_1EC], eax
0x18006d2dd  mov     eax, [rsi+58h]
0x18006d2e0  mov     [rsp+260h+var_1E4], eax
0x18006d2e4  movups  xmm0, xmmword ptr [rsi+20h]
0x18006d2e8  movups  [rsp+260h+var_218+8], xmm0
0x18006d2ed  mov     eax, [rsi+8]
0x18006d2f0  mov     [rsp+260h+var_200], eax
0x18006d2f4  mov     eax, [rsi+0Ch]
0x18006d2f7  mov     [rsp+260h+var_1FC], eax
0x18006d2fb  lea     rcx, [rbp+160h+var_150]
0x18006d2ff  lea     rax, [rsp+260h+var_218+8]
0x18006d304  movups  xmm0, xmmword ptr [rax]
0x18006d307  movups  xmmword ptr [rcx], xmm0
0x18006d30a  movups  xmm1, xmmword ptr [rax+10h]
0x18006d30e  movups  xmmword ptr [rcx+10h], xmm1
0x18006d312  movups  xmm0, xmmword ptr [rax+20h]
0x18006d316  movups  xmmword ptr [rcx+20h], xmm0
0x18006d31a  movups  xmm1, xmmword ptr [rax+30h]
0x18006d31e  movups  xmmword ptr [rcx+30h], xmm1
0x18006d322  movups  xmm0, xmmword ptr [rax+40h]
0x18006d326  movups  xmmword ptr [rcx+40h], xmm0
0x18006d32a  movups  xmm1, xmmword ptr [rax+50h]
0x18006d32e  movups  xmmword ptr [rcx+50h], xmm1
0x18006d332  movups  xmm0, xmmword ptr [rax+60h]
0x18006d336  movups  xmmword ptr [rcx+60h], xmm0
0x18006d33a  movups  xmm1, xmmword ptr [rax+70h]
0x18006d33e  movups  xmmword ptr [rcx+70h], xmm1
0x18006d342  movups  xmm0, xmmword ptr [rax+80h]
0x18006d349  movups  xmmword ptr [rcx+80h], xmm0
0x18006d350  movups  xmm1, xmmword ptr [rax+90h]
0x18006d357  movups  xmmword ptr [rcx+90h], xmm1
0x18006d35e  mov     ecx, 0ACAE0000h; this
0x18006d363  mov     edx, 0C26AE25Fh; unsigned int
0x18006d368  lea     r8, [rbp+160h+var_170]; unsigned int
0x18006d36c  lea     r9, [rbp+160h+var_B0]; struct Area::IntegralRecord::LongTermLocation *
0x18006d373  call    ?MoveEvenAssignment@IntegralRecord@Area@@YAHIIAEAULongTermLocation@12@PEAI@Z; Area::IntegralRecord::MoveEvenAssignment(uint,uint,Area::IntegralRecord::LongTermLocation &,uint *)
0x18006d378  jmp     loc_18006D110
0x18006d37d  movzx   r15d, [rbp+160h+var_128]; jumptable 000000018006D152 case 4
0x18006d382  sub     r15w, [rbp+160h+var_124]
0x18006d387  lea     rcx, [rsi+28h]; void *
0x18006d38b  mov     edx, 279h; unsigned int
0x18006d390  call    ?IterateIntegratedLibrary@ImportantTopic@Paper@@SAHPEAXI@Z; Paper::ImportantTopic::IterateIntegratedLibrary(void *,uint)
0x18006d395  movd    xmm7, eax
0x18006d399  cvtdq2ps xmm7, xmm7
0x18006d39c  lea     rax, ??_7MixedInformation@@6B@; const MixedInformation::`vftable'
0x18006d3a3  mov     [rbp+160h+var_160], rax
0x18006d3a7  mov     ecx, 0CC900000h; this
0x18006d3ac  mov     edx, 2AA4D7D3h; unsigned int
0x18006d3b1  lea     r8, [rbp+160h+var_170]; unsigned int
0x18006d3b5  lea     r9, [rbp+160h+var_B0]; struct Area::IntegralRecord::LongTermLocation *
0x18006d3bc  call    ?MoveEvenAssignment@IntegralRecord@Area@@YAHIIAEAULongTermLocation@12@PEAI@Z; Area::IntegralRecord::MoveEvenAssignment(uint,uint,Area::IntegralRecord::LongTermLocation &,uint *)
0x18006d3c1  jmp     loc_18006D110
0x18006d3c6  add     r12w, word ptr cs:?OddMap@IntegralRelation@@2IA; jumptable 000000018006D152 case 46
0x18006d3ce  inc     r15w
0x18006d3d2  xorps   xmm0, xmm0
0x18006d3d5  cvtss2sd xmm0, xmm6
0x18006d3d9  mulsd   xmm0, cs:__real@3fa0000000000000
0x18006d3e1  cvtpd2ps xmm7, xmm0
0x18006d3e5  mov     ecx, 66370000h
0x18006d3ea  test    r14, r14
0x18006d3ed  cmovnz  ecx, r11d; this
0x18006d3f1  mov     edx, 36131F0Eh
0x18006d3f6  mov     eax, 98A73BDAh
0x18006d3fb  cmovnz  edx, eax; unsigned int
0x18006d3fe  lea     r8, [rbp+160h+var_170]; unsigned int
0x18006d402  lea     r9, [rbp+160h+var_B0]; struct Area::IntegralRecord::LongTermLocation *
0x18006d409  call    ?MoveEvenAssignment@IntegralRecord@Area@@YAHIIAEAULongTermLocation@12@PEAI@Z; Area::IntegralRecord::MoveEvenAssignment(uint,uint,Area::IntegralRecord::LongTermLocation &,uint *)
0x18006d40e  jmp     loc_18006D110
0x18006d413  movsd   xmm0, [rbp+160h+var_148]; jumptable 000000018006D152 case 50
0x18006d418  cvtpd2ps xmm0, xmm0
0x18006d41c  movss   cs:?LogicalControl@Paper@@3MA, xmm0; float Paper::LogicalControl
0x18006d424  movzx   r15d, word ptr [rsi+0Ch]
0x18006d429  lea     r14, [rbp+160h+var_160]
0x18006d42d  mov     [rsp+260h+var_230], r14
0x18006d432  mov     ecx, 50000667h; this
0x18006d437  mov     edx, 0BC161F1Bh; unsigned int
0x18006d43c  lea     r8, [rbp+160h+var_170]; unsigned int
0x18006d440  lea     r9, [rbp+160h+var_B0]; struct Area::IntegralRecord::LongTermLocation *
0x18006d447  call    ?MoveEvenAssignment@IntegralRecord@Area@@YAHIIAEAULongTermLocation@12@PEAI@Z; Area::IntegralRecord::MoveEvenAssignment(uint,uint,Area::IntegralRecord::LongTermLocation &,uint *)
0x18006d44c  jmp     loc_18006D110
0x18006d451  movss   xmm7, cs:__real@40800000; jumptable 000000018006D152 case 48
0x18006d459  movsd   xmm0, [rbp+160h+var_108]
0x18006d45e  cvtpd2ps xmm0, xmm0
0x18006d462  cvtps2pd xmm1, xmm0
0x18006d465  movsd   xmm2, qword ptr [rsi+20h]
0x18006d46a  subsd   xmm2, xmm1
0x18006d46e  cvtpd2ps xmm6, xmm2
0x18006d472  mov     rax, qword ptr [rsp+260h+var_218]
0x18006d477  mov     r14, [rax+8]
0x18006d47b  xor     ebx, ebx
0x18006d47d  mov     [rsp+260h+var_220], rbx
0x18006d482  or      edi, 1
0x18006d485  mov     dword ptr [rsp+260h+var_238], edi
0x18006d489  mov     dword ptr [rsp+260h+var_240+4], edi
0x18006d48d  mov     rax, [r14]
0x18006d490  mov     edx, 0B5C0h
0x18006d495  mov     rcx, r14
0x18006d498  mov     rax, [rax]
0x18006d49b  call    cs:__guard_dispatch_icall_fptr
0x18006d4a1  mov     rdi, rax
0x18006d4a4  test    rax, rax
0x18006d4a7  jz      loc_18006D538
0x18006d4ad  lea     rdx, [rax+20h]
0x18006d4b1  mov     rax, rdx
0x18006d4b4  and     eax, 3Fh
0x18006d4b7  mov     ecx, 40h ; '@'
0x18006d4bc  sub     rcx, rax
0x18006d4bf  test    rax, rax
0x18006d4c2  cmovz   rcx, rax
0x18006d4c6  cmp     rcx, 0B5A0h
0x18006d4cd  ja      short loc_18006D4E3
0x18006d4cf  mov     eax, 0B5A0h
0x18006d4d4  sub     rax, rcx
0x18006d4d7  cmp     rax, 0B560h
0x18006d4dd  lea     rax, [rdx+rcx]
0x18006d4e1  jnb     short loc_18006D4E6
0x18006d4e3  mov     rax, rbx
0x18006d4e6  mov     dword ptr [rdi], 1
0x18006d4ec  mov     [rdi+8], rax
0x18006d4f0  mov     [rdi+10h], bl
0x18006d4f3  mov     [rdi+18h], r14
0x18006d4f7  mov     [rsp+260h+var_220], rdi
0x18006d4fc  mov     rbx, rdi
0x18006d4ff  cmp     byte ptr [rdi+10h], 0
0x18006d503  jnz     short loc_18006D52B
0x18006d505  mov     rcx, rax; this
0x18006d508  test    rax, rax
0x18006d50b  jz      short loc_18006D52B
0x18006d50d  mov     r9, r14; struct Data::Stack::OddMenu *
0x18006d510  mov     r8, [rsp+260h+var_228]; struct Direction::AvailableArray *
0x18006d515  mov     rdx, [rsp+260h+var_230]; struct Setting::CommonInformation *
0x18006d51a  call    ??0DetailedVersion@Unit@Direction@@QEAA@PEAVCommonInformation@Setting@@AEAVAvailableArray@2@AEAVOddMenu@Stack@Data@@@Z; Direction::Unit::DetailedVersion::DetailedVersion(Setting::CommonInformation *,Direction::AvailableArray &,Data::Stack::OddMenu &)
0x18006d51f  mov     byte ptr [rdi+10h], 1
0x18006d523  mov     [rbp+160h+var_168], rdi
0x18006d527  inc     dword ptr [rbx]
0x18006d529  jmp     short loc_18006D541
0x18006d52b  mov     [rbp+160h+var_168], rbx
0x18006d52f  test    rbx, rbx
0x18006d532  jz      short loc_18006D541
0x18006d534  inc     dword ptr [rbx]
0x18006d536  jmp     short loc_18006D541
0x18006d538  mov     [rsp+260h+var_220], rbx
0x18006d53d  mov     [rbp+160h+var_168], rbx
0x18006d541  mov     edi, dword ptr [rsp+260h+var_238]
0x18006d545  and     edi, 0FFFFFFFEh
0x18006d548  test    rbx, rbx
0x18006d54b  jz      short loc_18006D589
  ... truncated ...
```
