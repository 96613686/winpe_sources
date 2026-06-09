# Input::ComprehensiveSkill::RunFlatMessage(Input::EllipticActivity &,float)

- ea: `0x180022c20`
- end: `0x1800232e4`
- name: `?RunFlatMessage@ComprehensiveSkill@Input@@QEAAXAEAVEllipticActivity@2@M@Z`
- size: `1732`
- prototype: `void __fastcall(Input::ComprehensiveSkill *__hidden this, struct Input::EllipticActivity *, float)`
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x1800203c0`

## callees

- `0x180003180`
- `0x180003ca0`
- `0x18000df20`
- `0x18000e0c0`
- `0x18000e4b0`
- `0x18001ee30`
- `0x18001eff0`
- `0x18001f070`
- `0x18001f0d0`
- `0x18001f1b0`
- `0x18001f1e0`
- `0x18001f210`
- `0x18001f240`
- `0x18001f270`
- `0x18001f2b0`
- `0x18001f2f0`
- `0x18001f330`
- `0x18001f370`
- `0x18001f420`
- `0x18001f470`
- `0x18001f4c0`
- `0x18001f560`
- `0x180022c20`
- `0x1800bf3b0`

## pseudocode

```c
void __fastcall Input::ComprehensiveSkill::RunFlatMessage(
        Input::ComprehensiveSkill *this,
        struct Input::EllipticActivity *a2,
        float a3)
{
  unsigned __int64 v3; // rsi
  float v6; // xmm6_4
  float v8; // xmm15_4
  float v9; // xmm13_4
  float v10; // xmm8_4
  __m128 v11; // xmm9
  __m128 v12; // xmm7
  int v13; // ebp
  int v14; // eax
  unsigned int v15; // eax
  double v16; // xmm0_8
  __int64 v17; // rax
  __int64 v18; // rcx
  float v19; // xmm0_4
  unsigned __int64 v20; // rax
  double v21; // xmm0_8
  unsigned int v22; // eax
  __m128d v23; // xmm0
  unsigned int v24; // eax
  float v25; // xmm1_4
  float v26; // xmm6_4
  float v27; // xmm0_4
  unsigned int v28; // eax
  unsigned __int64 v29; // rax
  double v30; // xmm0_8
  unsigned int v31; // eax
  unsigned int v32; // eax
  __int64 v33; // rbx
  __int64 (__fastcall *MixedProvider)(_QWORD, __int64, char *); // rax
  unsigned int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // eax
  double v38; // xmm0_8
  void (__fastcall *v39)(_QWORD); // rax
  double v40; // xmm0_8
  float v41; // [rsp+20h] [rbp-F8h]
  float v42; // [rsp+24h] [rbp-F4h]
  float v43; // [rsp+28h] [rbp-F0h] BYREF

  v3 = 0;
  v43 = 0.0;
  v6 = 0.0;
  v42 = 0.0;
  v41 = 0.0;
  v8 = 0.0;
  v9 = 0.0;
  v10 = 0.0;
  v11 = 0;
  v12 = 0;
  LOBYTE(v13) = 0;
  Ratio::VisitGeneralRatio<2,34>(9);
  v14 = Ratio::SecureLogicalActivity<2,2>(51) ^ 0x20;
  while ( 2 )
  {
    switch ( v14 )
    {
      case 16:
        Paper::LogicalControl = (float)(int)Paper::ImportantTopic::IterateIntegratedLibrary((char *)a2 + 1128, 0x293u);
        v11 = (__m128)COERCE_UNSIGNED_INT64(
                        Input::ComprehensiveSkill::DefineShortTermControl<Data::HighDescription<float *>>(
                          this,
                          (char *)a2 + 960,
                          30));
        v24 = Ratio::ReflectScatteredTime<2,22>(11);
        v14 = Ratio::IssueSpecialServer<1,1>(12, v24) ^ 0x1D;
        continue;
      case 17:
        --v3;
        v25 = v11.m128_f32[0] + v10;
        if ( (float)(v11.m128_f32[0] + v10) == 0.0 )
        {
          v26 = FLOAT_1_1754944eN38;
        }
        else
        {
          if ( v25 < 0.0 )
            v27 = o_sqrtf_0(v25);
          else
            v27 = fsqrt(v25);
          v26 = (float)(v9 + v8) / v27;
        }
        v43 = v26;
        Ratio::VisitGeneralRatio<1,96>(23);
        v6 = v42;
        v14 = Ratio::SecureLogicalActivity<2,4>(34) ^ 0x3A;
        continue;
      case 18:
        v36 = Ratio::ReflectScatteredTime<1,22>(62, 44);
        v14 = Ratio::IssueSpecialServer<1,1>(11, v36) ^ 0x1A;
        continue;
      case 19:
        ++Paper::SlowInformation;
        if ( (_BYTE)v13 )
        {
          v15 = Ratio::ReflectScatteredTime<2,37>(3);
          v14 = Ratio::IssueSpecialServer<2,2>(25, v15) ^ 9;
        }
        else
        {
          v12 = (__m128)LODWORD(FLOAT_2_5);
          v16 = Input::ComprehensiveSkill::OrderDetailedMode<Data::HighDescription<float *>,signed char const *>(
                  this,
                  a2,
                  &Input::ComprehensiveSkill::CommonTime,
                  168);
          v8 = *(float *)&v16;
          v14 = Ratio::SecureLogicalActivity<2,4>(35);
        }
        continue;
      case 21:
        v33 = Paper::SlowInformation & 0xF;
        MixedProvider = (__int64 (__fastcall *)(_QWORD, __int64, char *))GenerateMixedProvider(
                                                                           0x7FBF7F3F40C040A0LL,
                                                                           2432991466LL,
                                                                           0x7FBF7F3F40C040A0LL);
        qword_180129C78 = *(_QWORD *)MixedProvider(0, qword_180129C98[v33], (char *)a2 + 1120);
        *((float *)a2 + 277) = v41;
        v35 = Ratio::VisitGeneralRatio<2,40>(37);
        v14 = Ratio::SecureLogicalActivity<1,0>(25, v35) ^ 5;
        continue;
      case 22:
        Paper::ImportantTopic::IterateIntegratedLibrary(&v43, 0x129u);
        v12 = v11;
        v12.m128_f32[0] = v11.m128_f32[0] * *((float *)a2 + 280);
        Paper::ImportantTopic::AcquireLogicalOperation(46);
        *((float *)a2 + 280) = (float)(v6 * 0.27970001) + (float)(v43 * 0.74479997);
        v32 = Ratio::ReflectScatteredTime<2,37>(109);
        v14 = Ratio::IssueSpecialServer<2,2>(21, v32) ^ 0x35;
        continue;
      case 24:
        v6 = a3 - 50.0;
        Paper::LogicalControl = v8 - v11.m128_f32[0];
        v42 = a3 - 50.0;
        v41 = v11.m128_f32[0] * 0.03125;
        v28 = Ratio::VisitGeneralRatio<1,96>(45);
        v14 = Ratio::SecureLogicalActivity<2,7>(31, v28) ^ 4;
        continue;
      case 25:
        v23 = _mm_cvtps_pd((__m128)LODWORD(v41));
        ++v3;
        v23.m128d_f64[0] = v23.m128d_f64[0] * 0.03125;
        v12 = _mm_cvtpd_ps(v23);
        v41 = v12.m128_f32[0];
        v12.m128_f32[0] = v12.m128_f32[0] * *((float *)a2 + 278);
        Paper::SlowInformation = (int)(a3 * 0.03125);
        v23.m128d_f64[0] = Input::ComprehensiveSkill::DefineShortTermControl<Data::HighDescription<float *>>(
                             this,
                             a2,
                             168);
        v10 = *(float *)v23.m128d_f64;
        Ratio::VisitGeneralRatio<1,96>(31);
        v14 = Ratio::SecureLogicalActivity<2,2>(53) ^ 0x25;
        continue;
      case 27:
        v29 = 0;
        v30 = v10 * 0.0625;
        if ( v30 >= 9.223372036854776e18 )
        {
          v30 = v30 - 9.223372036854776e18;
          if ( v30 < 9.223372036854776e18 )
            v29 = 0x8000000000000000uLL;
        }
        v3 = v29 + (unsigned int)(int)v30;
        *((float *)a2 + 279) = v43;
        v31 = Ratio::ReflectScatteredTime<2,53>(20);
        v14 = Ratio::IssueSpecialServer<1,1>(48, v31) ^ 0x26;
        continue;
      case 28:
        v17 = Paper::SlowInformation & 0xF;
        v18 = v3 - qword_180129C98[v17];
        if ( v18 < 0 )
        {
          v20 = v18 & 1 | ((v3 - qword_180129C98[v17]) >> 1);
          v19 = (float)(int)v20 + (float)(int)v20;
        }
        else
        {
          v19 = (float)(int)v18;
        }
        v12 = (__m128)LODWORD(FLOAT_1_75);
        Paper::LogicalControl = v19;
        Paper::SlowInformation = IntegralRelation::OddMap;
        Paper::LogicalControl = *((float *)a2 + 278) * 0.125;
        v21 = Input::ComprehensiveSkill::OrderDetailedMode<Data::HighDescription<float *>,signed char const *>(
                this,
                (char *)a2 + 960,
                qword_1800D4800,
                30);
        v9 = *(float *)&v21;
        v22 = Ratio::ReflectScatteredTime<1,22>(19, 28);
        v14 = Ratio::IssueSpecialServer<2,2>(30, v22) ^ 7;
        continue;
      case 29:
        v10 = *((float *)a2 + 1) * *((float *)a2 + 1);
        if ( v12.m128_f32[0] <= a3 )
        {
          v38 = *((float *)a2 + 283);
          *((_DWORD *)a2 + 280) = *((_DWORD *)a2 + 271);
          a3 = v38 * 0.03125;
          v14 = Ratio::SecureLogicalActivity<2,4>(63);
        }
        else
        {
          v37 = Ratio::ReflectScatteredTime<2,22>(38);
          v14 = Ratio::IssueSpecialServer<1,1>(44, v37) ^ 0x37;
        }
        continue;
      case 30:
        v39 = (void (__fastcall *)(_QWORD))GenerateMixedProvider(
                                             0x3FFF7F7F800000E0LL,
                                             3510927530LL,
                                             0x7FBF7F3F40C040A0LL);
        v39(0);
        v40 = *(float *)a2 * 0.5;
        if ( v40 >= 9.223372036854776e18 )
          v40 = v40 - 9.223372036854776e18;
        *((_DWORD *)a2 + 281) = v3 + qword_18012A008;
        v13 = (int)v40;
        v14 = Ratio::SecureLogicalActivity<2,1>(22, 7);
        continue;
      case 31:
        v11 = v12;
        v11.m128_f32[0] = v12.m128_f32[0] + v9;
        Ratio::VisitGeneralRatio<2,17>(6);
        v14 = Ratio::SecureLogicalActivity<2,4>(9) ^ 0x17;
        continue;
      case 32:
        Paper::SlowInformation = 59846;
        Paper::LogicalControl = Paper::LogicalControl + -1.0;
        break;
      default:
        return;
    }
    break;
  }
}

```

## disassembly

```asm
0x180022c20  mov     rax, rsp
0x180022c23  push    rbp
0x180022c24  push    rsi
0x180022c25  push    rdi
0x180022c26  push    r12
0x180022c28  push    r13
0x180022c2a  push    r14
0x180022c2c  push    r15
0x180022c2e  sub     rsp, 0E0h
0x180022c35  movaps  xmmword ptr [rax-48h], xmm6
0x180022c39  movaps  xmmword ptr [rax-58h], xmm7
0x180022c3d  movaps  xmmword ptr [rax-68h], xmm8
0x180022c42  movaps  xmmword ptr [rax-78h], xmm9
0x180022c47  movaps  xmmword ptr [rax-88h], xmm10
0x180022c4f  movaps  xmmword ptr [rax-98h], xmm11
0x180022c57  movaps  [rsp+118h+var_A8], xmm12
0x180022c5d  movaps  [rsp+118h+var_B8], xmm13
0x180022c63  movaps  [rsp+118h+var_C8], xmm14
0x180022c69  movaps  [rsp+118h+var_D8], xmm15
0x180022c6f  mov     rax, cs:__security_cookie
0x180022c76  xor     rax, rsp
0x180022c79  mov     [rsp+118h+var_E8], rax
0x180022c7e  xor     esi, esi
0x180022c80  mov     [rsp+118h+var_F0], 0
0x180022c88  mov     rdi, rdx
0x180022c8b  mov     r14, rcx
0x180022c8e  xorps   xmm11, xmm11
0x180022c92  xorps   xmm6, xmm6
0x180022c95  movss   [rsp+118h+var_F4], xmm6
0x180022c9b  movaps  xmm12, xmm2
0x180022c9f  lea     edx, [rsi+1]
0x180022ca2  movss   [rsp+118h+var_F8], xmm11
0x180022ca9  lea     ecx, [rsi+9]
0x180022cac  xorps   xmm15, xmm15
0x180022cb0  xorps   xmm13, xmm13
0x180022cb4  xorps   xmm8, xmm8
0x180022cb8  xorps   xmm9, xmm9
0x180022cbc  xorps   xmm7, xmm7
0x180022cbf  mov     ebp, esi
0x180022cc1  call    ??$VisitGeneralRatio@$01$0CC@@Ratio@@SAIII@Z; Ratio::VisitGeneralRatio<2,34>(uint,uint)
0x180022cc6  mov     edx, eax
0x180022cc8  lea     ecx, [rsi+33h]
0x180022ccb  call    ??$SecureLogicalActivity@$01$01@Ratio@@SAIII@Z; Ratio::SecureLogicalActivity<2,2>(uint,uint)
0x180022cd0  movsd   xmm14, cs:__real@3fa0000000000000
0x180022cd9  lea     r15, cs:180000000h
0x180022ce0  movsd   xmm10, cs:__real@43e0000000000000
0x180022ce9  xor     eax, 20h
0x180022cec  mov     r12, 8000000000000000h
0x180022cf6  mov     [rsp+118h+arg_18], rbx
0x180022cfe  mov     r13, 3FFF7F7F800000E0h
0x180022d08  add     eax, 0FFFFFFF0h; switch 17 cases
0x180022d0b  mov     r8, 7FBF7F3F40C040A0h
0x180022d15  cmp     eax, 10h
0x180022d18  ja      def_180022D2B; jumptable 0000000180022D2B default case, cases 20,23,26
0x180022d1e  cdqe
0x180022d20  mov     ecx, ds:(jpt_180022D2B - 180000000h)[r15+rax*4]
0x180022d28  add     rcx, r15
0x180022d2b  jmp     rcx; switch jump
0x180022d2d  inc     cs:?SlowInformation@Paper@@3IA; jumptable 0000000180022D2B case 19
0x180022d33  test    bpl, bpl
0x180022d36  jz      short loc_180022D56
0x180022d38  mov     edx, 13h
0x180022d3d  lea     ecx, [rdx-10h]
0x180022d40  call    ??$ReflectScatteredTime@$01$0CF@@Ratio@@SAIII@Z; Ratio::ReflectScatteredTime<2,37>(uint,uint)
0x180022d45  mov     edx, eax
0x180022d47  mov     ecx, 19h
0x180022d4c  call    ??$IssueSpecialServer@$01$01@Ratio@@SAIII@Z; Ratio::IssueSpecialServer<2,2>(uint,uint)
0x180022d51  xor     eax, 9
0x180022d54  jmp     short loc_180022D08
0x180022d56  movss   xmm7, cs:__real@40200000
0x180022d5e  lea     r8, ?CommonTime@ComprehensiveSkill@Input@@0QBCB; signed char const near * const Input::ComprehensiveSkill::CommonTime
0x180022d65  mov     r9d, 0A8h
0x180022d6b  mov     rdx, rdi
0x180022d6e  mov     rcx, r14
0x180022d71  call    ??$OrderDetailedMode@V?$HighDescription@PEAM@Data@@PEBC@ComprehensiveSkill@Input@@QEBAMV?$HighDescription@PEAM@Data@@PEBCH@Z; Input::ComprehensiveSkill::OrderDetailedMode<Data::HighDescription<float *>,signed char const *>(Data::HighDescription<float *>,signed char const *,int)
0x180022d76  mov     edx, 3Fh ; '?'
0x180022d7b  movaps  xmm15, xmm0
0x180022d7f  lea     ecx, [rdx-1Ch]
0x180022d82  call    ??$SecureLogicalActivity@$01$03@Ratio@@SAIII@Z; Ratio::SecureLogicalActivity<2,4>(uint,uint)
0x180022d87  jmp     loc_180022D08
0x180022d8c  mov     eax, cs:?SlowInformation@Paper@@3IA; jumptable 0000000180022D2B case 28
0x180022d92  mov     rcx, rsi
0x180022d95  and     eax, 0Fh
0x180022d98  xorps   xmm0, xmm0
0x180022d9b  sub     rcx, rva qword_180129C98[r15+rax*8]
0x180022da3  js      short loc_180022DAC
0x180022da5  cvtsi2ss xmm0, rcx
0x180022daa  jmp     short loc_180022DC1
0x180022dac  mov     rax, rcx
0x180022daf  and     ecx, 1
0x180022db2  shr     rax, 1
0x180022db5  or      rax, rcx
0x180022db8  cvtsi2ss xmm0, rax
0x180022dbd  addss   xmm0, xmm0
0x180022dc1  mov     eax, cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x180022dc7  lea     rdx, [rdi+3C0h]
0x180022dce  movss   xmm7, cs:__real@3fe00000
0x180022dd6  lea     r8, qword_1800D4800
0x180022ddd  movss   cs:?LogicalControl@Paper@@3MA, xmm0; float Paper::LogicalControl
0x180022de5  mov     r9d, 1Eh
0x180022deb  mov     cs:?SlowInformation@Paper@@3IA, eax; uint Paper::SlowInformation
0x180022df1  mov     rcx, r14
0x180022df4  movss   xmm0, dword ptr [rdi+458h]
0x180022dfc  cvtps2pd xmm0, xmm0
0x180022dff  mulsd   xmm0, cs:__real@3fc0000000000000
0x180022e07  cvtpd2ps xmm0, xmm0
0x180022e0b  movss   cs:?LogicalControl@Paper@@3MA, xmm0; float Paper::LogicalControl
0x180022e13  call    ??$OrderDetailedMode@V?$HighDescription@PEAM@Data@@PEBC@ComprehensiveSkill@Input@@QEBAMV?$HighDescription@PEAM@Data@@PEBCH@Z; Input::ComprehensiveSkill::OrderDetailedMode<Data::HighDescription<float *>,signed char const *>(Data::HighDescription<float *>,signed char const *,int)
0x180022e18  mov     edx, 1Ch
0x180022e1d  movaps  xmm13, xmm0
0x180022e21  lea     ecx, [rdx-9]
0x180022e24  call    ??$ReflectScatteredTime@$00$0BG@@Ratio@@SAIII@Z; Ratio::ReflectScatteredTime<1,22>(uint,uint)
0x180022e29  mov     edx, eax
0x180022e2b  mov     ecx, 1Eh
0x180022e30  call    ??$IssueSpecialServer@$01$01@Ratio@@SAIII@Z; Ratio::IssueSpecialServer<2,2>(uint,uint)
0x180022e35  xor     eax, 7
0x180022e38  jmp     loc_180022D08
0x180022e3d  movss   xmm0, [rsp+118h+var_F8]; jumptable 0000000180022D2B case 25
0x180022e43  mov     r8d, 0A8h
0x180022e49  cvtps2pd xmm0, xmm0
0x180022e4c  mov     rdx, rdi
0x180022e4f  mov     rcx, r14
0x180022e52  inc     rsi
0x180022e55  mulsd   xmm0, xmm14
0x180022e5a  cvtpd2ps xmm0, xmm0
0x180022e5e  movaps  xmm7, xmm0
0x180022e61  movss   [rsp+118h+var_F8], xmm0
0x180022e67  mulss   xmm7, dword ptr [rdi+458h]
0x180022e6f  xorps   xmm0, xmm0
0x180022e72  cvtss2sd xmm0, xmm12
0x180022e77  mulsd   xmm0, xmm14
0x180022e7c  cvttsd2si rax, xmm0
0x180022e81  mov     cs:?SlowInformation@Paper@@3IA, eax; uint Paper::SlowInformation
0x180022e87  call    ??$DefineShortTermControl@V?$HighDescription@PEAM@Data@@@ComprehensiveSkill@Input@@QEBAMV?$HighDescription@PEAM@Data@@H@Z; Input::ComprehensiveSkill::DefineShortTermControl<Data::HighDescription<float *>>(Data::HighDescription<float *>,int)
0x180022e8c  mov     edx, 1
0x180022e91  movaps  xmm8, xmm0
0x180022e95  lea     ecx, [rdx+1Eh]
0x180022e98  call    ??$VisitGeneralRatio@$00$0GA@@Ratio@@SAIII@Z; Ratio::VisitGeneralRatio<1,96>(uint,uint)
0x180022e9d  mov     edx, eax
0x180022e9f  mov     ecx, 35h ; '5'
0x180022ea4  call    ??$SecureLogicalActivity@$01$01@Ratio@@SAIII@Z; Ratio::SecureLogicalActivity<2,2>(uint,uint)
0x180022ea9  xor     eax, 25h
0x180022eac  jmp     loc_180022D08
0x180022eb1  lea     rcx, [rdi+468h]; jumptable 0000000180022D2B case 16
0x180022eb8  mov     edx, 293h; unsigned int
0x180022ebd  call    ?IterateIntegratedLibrary@ImportantTopic@Paper@@SAHPEAXI@Z; Paper::ImportantTopic::IterateIntegratedLibrary(void *,uint)
0x180022ec2  lea     rdx, [rdi+3C0h]
0x180022ec9  mov     r8d, 1Eh
0x180022ecf  mov     rcx, r14
0x180022ed2  movd    xmm0, eax
0x180022ed6  cvtdq2ps xmm0, xmm0
0x180022ed9  movss   cs:?LogicalControl@Paper@@3MA, xmm0; float Paper::LogicalControl
0x180022ee1  call    ??$DefineShortTermControl@V?$HighDescription@PEAM@Data@@@ComprehensiveSkill@Input@@QEBAMV?$HighDescription@PEAM@Data@@H@Z; Input::ComprehensiveSkill::DefineShortTermControl<Data::HighDescription<float *>>(Data::HighDescription<float *>,int)
0x180022ee6  mov     edx, 6
0x180022eeb  movaps  xmm9, xmm0
0x180022eef  lea     ecx, [rdx+5]
0x180022ef2  call    ??$ReflectScatteredTime@$01$0BG@@Ratio@@SAIII@Z; Ratio::ReflectScatteredTime<2,22>(uint,uint)
0x180022ef7  mov     edx, eax
0x180022ef9  mov     ecx, 0Ch
0x180022efe  call    ??$IssueSpecialServer@$00$00@Ratio@@SAIII@Z; Ratio::IssueSpecialServer<1,1>(uint,uint)
0x180022f03  xor     eax, 1Dh
0x180022f06  jmp     loc_180022D08
0x180022f0b  movaps  xmm1, xmm9; jumptable 0000000180022D2B case 17
0x180022f0f  dec     rsi
0x180022f12  addss   xmm1, xmm8
0x180022f17  ucomiss xmm1, xmm11
0x180022f1b  jp      short loc_180022F29
0x180022f1d  jnz     short loc_180022F29
0x180022f1f  movss   xmm6, cs:__real@00800000
0x180022f27  jmp     short loc_180022F4F
0x180022f29  xorps   xmm0, xmm0
0x180022f2c  movaps  xmm6, xmm13
0x180022f30  ucomiss xmm0, xmm1
0x180022f33  addss   xmm6, xmm15
0x180022f38  ja      short loc_180022F43
0x180022f3a  xorps   xmm0, xmm0
0x180022f3d  sqrtss  xmm0, xmm1
0x180022f41  jmp     short loc_180022F4B
0x180022f43  movaps  xmm0, xmm1; X
0x180022f46  call    _o_sqrtf_0
0x180022f4b  divss   xmm6, xmm0
0x180022f4f  mov     edx, 3Ah ; ':'
0x180022f54  movss   [rsp+118h+var_F0], xmm6
0x180022f5a  lea     ecx, [rdx-23h]
0x180022f5d  call    ??$VisitGeneralRatio@$00$0GA@@Ratio@@SAIII@Z; Ratio::VisitGeneralRatio<1,96>(uint,uint)
0x180022f62  mov     edx, eax
0x180022f64  mov     ecx, 22h ; '"'
0x180022f69  call    ??$SecureLogicalActivity@$01$03@Ratio@@SAIII@Z; Ratio::SecureLogicalActivity<2,4>(uint,uint)
0x180022f6e  movss   xmm6, [rsp+118h+var_F4]
0x180022f74  xor     eax, 3Ah
0x180022f77  jmp     loc_180022D08
0x180022f7c  xorps   xmm0, xmm0; jumptable 0000000180022D2B case 24
0x180022f7f  movaps  xmm1, xmm15
0x180022f83  cvtss2sd xmm0, xmm9
0x180022f88  mov     edx, 0Dh
0x180022f8d  movaps  xmm6, xmm12
0x180022f91  subss   xmm1, xmm9
0x180022f96  subss   xmm6, cs:__real@42480000
0x180022f9e  mulsd   xmm0, xmm14
0x180022fa3  lea     ecx, [rdx+20h]
0x180022fa6  movss   cs:?LogicalControl@Paper@@3MA, xmm1; float Paper::LogicalControl
0x180022fae  movss   [rsp+118h+var_F4], xmm6
0x180022fb4  cvtpd2ps xmm0, xmm0
0x180022fb8  movss   [rsp+118h+var_F8], xmm0
0x180022fbe  call    ??$VisitGeneralRatio@$00$0GA@@Ratio@@SAIII@Z; Ratio::VisitGeneralRatio<1,96>(uint,uint)
0x180022fc3  mov     edx, eax
0x180022fc5  mov     ecx, 1Fh
0x180022fca  call    ??$SecureLogicalActivity@$01$06@Ratio@@SAIII@Z; Ratio::SecureLogicalActivity<2,7>(uint,uint)
0x180022fcf  xor     eax, 4
0x180022fd2  jmp     loc_180022D08
0x180022fd7  xorps   xmm0, xmm0; jumptable 0000000180022D2B case 27
0x180022fda  xor     eax, eax
0x180022fdc  cvtss2sd xmm0, xmm8
0x180022fe1  mulsd   xmm0, cs:__real@3fb0000000000000
0x180022fe9  comisd  xmm0, xmm10
0x180022fee  jb      short loc_180022FFF
0x180022ff0  subsd   xmm0, xmm10
0x180022ff5  comisd  xmm0, xmm10
0x180022ffa  jnb     short loc_180022FFF
0x180022ffc  mov     rax, r12
0x180022fff  cvttsd2si rsi, xmm0
0x180023004  mov     edx, 3Eh ; '>'
0x180023009  lea     ecx, [rdx-2Ah]
0x18002300c  movss   xmm0, [rsp+118h+var_F0]
0x180023012  add     rsi, rax
0x180023015  movss   dword ptr [rdi+45Ch], xmm0
0x18002301d  call    ??$ReflectScatteredTime@$01$0DF@@Ratio@@SAIII@Z; Ratio::ReflectScatteredTime<2,53>(uint,uint)
0x180023022  mov     edx, eax
0x180023024  mov     ecx, 30h ; '0'
0x180023029  call    ??$IssueSpecialServer@$00$00@Ratio@@SAIII@Z; Ratio::IssueSpecialServer<1,1>(uint,uint)
0x18002302e  xor     eax, 26h
0x180023031  jmp     loc_180022D08
0x180023036  mov     edx, 129h; jumptable 0000000180022D2B case 22
0x18002303b  lea     rcx, [rsp+118h+var_F0]; void *
0x180023040  call    ?IterateIntegratedLibrary@ImportantTopic@Paper@@SAHPEAXI@Z; Paper::ImportantTopic::IterateIntegratedLibrary(void *,uint)
0x180023045  movaps  xmm7, xmm9
0x180023049  mov     ecx, 2Eh ; '.'; int
0x18002304e  mulss   xmm7, dword ptr [rdi+460h]
0x180023056  call    ?AcquireLogicalOperation@ImportantTopic@Paper@@SAXH@Z; Paper::ImportantTopic::AcquireLogicalOperation(int)
0x18002305b  movss   xmm0, [rsp+118h+var_F0]
0x180023061  movaps  xmm1, xmm6
0x180023064  mulss   xmm1, cs:__real@3e8f34d7
0x18002306c  mov     edx, 57h ; 'W'
0x180023071  mulss   xmm0, cs:__real@3f3eab36
0x180023079  lea     ecx, [rdx+16h]
0x18002307c  addss   xmm1, xmm0
0x180023080  movss   dword ptr [rdi+460h], xmm1
0x180023088  call    ??$ReflectScatteredTime@$01$0CF@@Ratio@@SAIII@Z; Ratio::ReflectScatteredTime<2,37>(uint,uint)
0x18002308d  mov     edx, eax
0x18002308f  mov     ecx, 15h
0x180023094  call    ??$IssueSpecialServer@$01$01@Ratio@@SAIII@Z; Ratio::IssueSpecialServer<2,2>(uint,uint)
0x180023099  xor     eax, 35h
0x18002309c  jmp     loc_180022D08
0x1800230a1  mov     ebx, cs:?SlowInformation@Paper@@3IA; jumptable 0000000180022D2B case 21
0x1800230a7  mov     edx, 910480EAh
0x1800230ac  mov     rcx, r8
0x1800230af  and     ebx, 0Fh
0x1800230b2  call    GenerateMixedProvider
0x1800230b7  mov     rdx, rva qword_180129C98[r15+rbx*8]
0x1800230bf  lea     r8, [rdi+460h]
0x1800230c6  xor     ecx, ecx
0x1800230c8  call    cs:__guard_dispatch_icall_fptr
0x1800230ce  movss   xmm0, [rsp+118h+var_F8]
0x1800230d4  mov     edx, 0Ah
0x1800230d9  mov     rcx, [rax]
0x1800230dc  mov     cs:qword_180129C78, rcx
0x1800230e3  lea     ecx, [rdx+1Bh]
0x1800230e6  movss   dword ptr [rdi+454h], xmm0
0x1800230ee  call    ??$VisitGeneralRatio@$01$0CI@@Ratio@@SAIII@Z; Ratio::VisitGeneralRatio<2,40>(uint,uint)
0x1800230f3  mov     edx, eax
0x1800230f5  mov     ecx, 19h
0x1800230fa  call    ??$SecureLogicalActivity@$00$0A@@Ratio@@SAIII@Z; Ratio::SecureLogicalActivity<1,0>(uint,uint)
0x1800230ff  xor     eax, 5
0x180023102  jmp     loc_180022D08
0x180023107  mov     edx, 2Ch ; ','; jumptable 0000000180022D2B case 18
0x18002310c  lea     ecx, [rdx+12h]
0x18002310f  call    ??$ReflectScatteredTime@$00$0BG@@Ratio@@SAIII@Z; Ratio::ReflectScatteredTime<1,22>(uint,uint)
0x180023114  mov     edx, eax
0x180023116  mov     ecx, 0Bh
0x18002311b  call    ??$IssueSpecialServer@$00$00@Ratio@@SAIII@Z; Ratio::IssueSpecialServer<1,1>(uint,uint)
0x180023120  xor     eax, 1Ah
0x180023123  jmp     loc_180022D08
0x180023128  comiss  xmm7, xmm12; jumptable 0000000180022D2B case 29
0x18002312c  movss   xmm8, dword ptr [rdi+4]
0x180023132  mulss   xmm8, xmm8
0x180023137  jbe     short loc_18002315A
0x180023139  mov     edx, 5
0x18002313e  lea     ecx, [rdx+21h]
0x180023141  call    ??$ReflectScatteredTime@$01$0BG@@Ratio@@SAIII@Z; Ratio::ReflectScatteredTime<2,22>(uint,uint)
0x180023146  mov     edx, eax
0x180023148  mov     ecx, 2Ch ; ','
0x18002314d  call    ??$IssueSpecialServer@$00$00@Ratio@@SAIII@Z; Ratio::IssueSpecialServer<1,1>(uint,uint)
0x180023152  xor     eax, 37h
0x180023155  jmp     loc_180022D08
0x18002315a  movss   xmm0, dword ptr [rdi+46Ch]
0x180023162  mov     edx, 2Ah ; '*'
0x180023167  mov     eax, [rdi+43Ch]
0x18002316d  cvtps2pd xmm0, xmm0
0x180023170  mov     [rdi+460h], eax
0x180023176  lea     ecx, [rdx+15h]
  ... truncated ...
```
