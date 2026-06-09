# Input::ComprehensiveSkill::PullTemporaryClient(int,int)

- ea: `0x1800224a0`
- end: `0x180022a2f`
- name: `?PullTemporaryClient@ComprehensiveSkill@Input@@QEAAFHH@Z`
- size: `1423`
- prototype: `__int16 __fastcall(Input::ComprehensiveSkill *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001f5c0`

## callees

- `0x180003180`
- `0x180007b70`
- `0x18000e4b0`
- `0x1800224a0`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__controlfp_s` at `0x1800227f4`
- `api-ms-win-crt-private-l1-1-0!_o__controlfp_s` at `0x1800227f4`

## pseudocode

```c
__int64 __fastcall Input::ComprehensiveSkill::PullTemporaryClient(
        Input::ComprehensiveSkill *this,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rdi
  __int64 v5; // r8
  const unsigned int near *const *v6; // r9
  int v7; // r10d
  unsigned int k; // ebx
  unsigned int v9; // ecx
  __int64 v10; // r8
  __int64 v11; // rcx
  void (__fastcall *v12)(_QWORD, __int64); // rax
  void (__fastcall *v13)(__int16 (__fastcall *)(Input::ComprehensiveSkill *__hidden, int, int), unsigned __int64, __int64); // rax
  unsigned __int16 v15; // r14
  const unsigned int near *const *v16; // r9
  int v17; // r11d
  unsigned int i; // r10d
  unsigned int v19; // ecx
  __int64 v20; // r8
  __int64 v21; // rcx
  int v22; // edi
  unsigned int v23; // ebx
  int v24; // eax
  void (__fastcall *MixedProvider)(__int16 (__fastcall *)(Input::ComprehensiveSkill *__hidden, int, int), unsigned __int64, __int64); // rax
  __int64 v26; // r8
  const unsigned int near *const *v27; // r9
  int v28; // r11d
  unsigned int j; // r10d
  unsigned int v30; // ecx
  __int64 v31; // r8
  __int64 v32; // rcx
  __int64 v33; // rax
  unsigned int v34; // r9d
  unsigned int v35; // r10d
  void (__fastcall *v36)(__int16 (__fastcall *)(Input::ComprehensiveSkill *__hidden, int, int), unsigned __int64, __int64); // rax
  int v37; // [rsp+20h] [rbp-59h] BYREF
  __int64 v38; // [rsp+28h] [rbp-51h] BYREF
  __int64 v39; // [rsp+30h] [rbp-49h] BYREF
  _DWORD v40[16]; // [rsp+40h] [rbp-39h] BYREF
  _DWORD v41[16]; // [rsp+80h] [rbp+7h] BYREF
  _BYTE *retaddr; // [rsp+D8h] [rbp+5Fh]

  v4 = (int)a2;
  if ( a2 > 0x17 )
  {
    if ( a2 == 24 )
    {
      v15 = a3 + 1001;
      if ( (IntegralRelation::OddMap ^ 0xFBFC93DE) != 0x39FF8D
        || *retaddr == (unsigned __int8)((IntegralRelation::OddMap ^ 0xB3F57F27) / 0x5A96AF) )
      {
        v16 = &ScatteredInformation::PaintShortTermException;
        v17 = ScatteredInformation::StripedSeries ^ 0x157E9386;
        for ( i = 0; i < 0x1E; i += 2 )
        {
          v19 = *((_DWORD *)v16++ + 1);
          v20 = (unsigned __int8)((v17 ^ v19) / 0x9D28AF) - i - 1;
          v21 = (unsigned __int8)(((unsigned int)v17 ^ *((_DWORD *)v16 - 2)) / 0x9D28AF) - i;
          *((_QWORD *)&ScatteredInformation::StripedSeries + v21 + 1) = *((_QWORD *)&ScatteredInformation::StripedSeries
                                                                        + v20
                                                                        + 1);
        }
        v37 = 0;
        v38 = 0x2F5FFFFF008080D0LL;
        v40[0] = 923746055;
        v22 = ScatteredInformation::StripedSeries ^ 0x157E9386;
        v39 = 0xEF8F2FCFF09060B0uLL;
        IntegralRelation::OddMap = ScatteredInformation::StripedSeries ^ 0x157E9386;
        v40[1] = 656355095;
        v40[2] = 906903046;
        v40[3] = 639512086;
        v40[4] = 890060037;
        v40[5] = 622669077;
        v40[6] = 873217028;
        v40[7] = 605826068;
        v40[8] = 856374019;
        v40[9] = 588983059;
        v40[10] = 839531010;
        v40[11] = 572140050;
        v40[12] = 822688001;
        v40[13] = 555297041;
        v40[14] = 805844992;
        v40[15] = 538454032;
        v41[0] = 923746055;
        v41[1] = 656355095;
        v41[2] = 906903046;
        v41[3] = 639512086;
        v41[4] = 890060037;
        v41[5] = 622669077;
        v41[6] = 873217028;
        v41[7] = 605826068;
        v41[8] = 856374019;
        v41[9] = 588983059;
        v41[10] = 839531010;
        v41[11] = 572140050;
        v41[12] = 822688001;
        v41[13] = 555297041;
        v41[14] = 805844992;
        v41[15] = 538454032;
        v23 = ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(
                (__int64)&ScatteredInformation::StripedSeries,
                &v38,
                (__int64)v40)
            ^ 0xAAAAAAAA;
        v24 = ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(
                (__int64)&ScatteredInformation::StripedSeries,
                &v39,
                (__int64)v41);
        _o__controlfp_s(&v37, (v24 ^ 0xAAAAAAAA) - v22, v23);
      }
      MixedProvider = (void (__fastcall *)(__int16 (__fastcall *)(Input::ComprehensiveSkill *__hidden, int, int), unsigned __int64, __int64))GenerateMixedProvider(0xFBFDF7FE070E050LL, 3775144106LL, a3, a4);
      MixedProvider(
        Input::ComprehensiveSkill::PullTemporaryClient,
        (unsigned __int64)Input::ComprehensiveSkill::PullTemporaryClient ^ 0x26A5BB,
        1484203);
      return v15;
    }
    else
    {
      if ( *retaddr == (unsigned __int8)((IntegralRelation::OddMap ^ 0xBC9398F3) / 0x598638)
        || (v26 = IntegralRelation::OddMap ^ 0xFBA46DDD, (_DWORD)v26 != 6357390) )
      {
        v27 = &ScatteredInformation::PaintShortTermException;
        v28 = ScatteredInformation::StripedSeries ^ 0x157E9386;
        for ( j = 0; j < 0x1E; j += 2 )
        {
          v30 = *((_DWORD *)v27++ + 1);
          v31 = (unsigned __int8)((v28 ^ v30) / 0x9D28AF) - j - 1;
          v32 = (unsigned __int8)(((unsigned int)v28 ^ *((_DWORD *)v27 - 2)) / 0x9D28AF) - j;
          *((_QWORD *)&ScatteredInformation::StripedSeries + v32 + 1) = *((_QWORD *)&ScatteredInformation::StripedSeries
                                                                        + v31
                                                                        + 1);
        }
        IntegralRelation::OddMap = ScatteredInformation::StripedSeries ^ 0x157E9386;
        v33 = GenerateMixedProvider(0xFF7F9F7F00A000D0uLL, 298082474, v31, v27);
        v34 = IntegralRelation::OddMap;
        v26 = v33;
        v35 = 0;
        while ( *(_BYTE *)v26 != (unsigned __int8)((IntegralRelation::OddMap ^ 0xE48A768E) / 0x9D28AF)
             || *(_BYTE *)(v26 + 1) != (unsigned __int8)((IntegralRelation::OddMap ^ 0x80A19D34) / 0x9D28AF)
             || *(_BYTE *)(v26 + 2) != (unsigned __int8)((IntegralRelation::OddMap ^ 0x861CF870) / 0x9D28AF)
             || *(_BYTE *)(v26 + 3) != (unsigned __int8)((IntegralRelation::OddMap ^ 0xE2EEE854) / 0x9D28AF) )
        {
          ++v35;
          ++v26;
          if ( v35 >= 0x258 )
            goto LABEL_27;
        }
        retaddr = (_BYTE *)v26;
        v34 = IntegralRelation::OddMap;
LABEL_27:
        a4 = v34 + 16;
        IntegralRelation::OddMap = a4;
      }
      v36 = (void (__fastcall *)(__int16 (__fastcall *)(Input::ComprehensiveSkill *__hidden, int, int), unsigned __int64, __int64))GenerateMixedProvider(0x8F5F5FBFC070C030uLL, 1642373226, v26, a4);
      v36(
        Input::ComprehensiveSkill::PullTemporaryClient,
        (unsigned __int64)Input::ComprehensiveSkill::PullTemporaryClient ^ 0x26619E,
        1466766);
      return 0;
    }
  }
  else
  {
    _mm_lfence();
    if ( *retaddr == (unsigned __int8)((IntegralRelation::OddMap ^ 0xDEE2F4E7) / 0x2EA01F)
      || (v5 = IntegralRelation::OddMap ^ 0xFBC31CDA, (_DWORD)v5 != 422025) )
    {
      v6 = &ScatteredInformation::PaintShortTermException;
      v7 = ScatteredInformation::StripedSeries ^ 0x157E9386;
      for ( k = 0; k < 0x1E; k += 2 )
      {
        v9 = *((_DWORD *)v6++ + 1);
        v10 = (unsigned __int8)((v7 ^ v9) / 0x9D28AF) - k - 1;
        v11 = (unsigned __int8)(((unsigned int)v7 ^ *((_DWORD *)v6 - 2)) / 0x9D28AF) - k;
        *((_QWORD *)&ScatteredInformation::StripedSeries + v11 + 1) = *((_QWORD *)&ScatteredInformation::StripedSeries
                                                                      + v10
                                                                      + 1);
      }
      IntegralRelation::OddMap = ScatteredInformation::StripedSeries ^ 0x157E9386;
      v12 = (void (__fastcall *)(_QWORD, __int64))GenerateMixedProvider(0x3F9FBF3F20C02070LL, 3508814058LL, v10, v6);
      v12(0, 104);
    }
    v13 = (void (__fastcall *)(__int16 (__fastcall *)(Input::ComprehensiveSkill *__hidden, int, int), unsigned __int64, __int64))GenerateMixedProvider(0x2FEFBF7FC080E000LL, 3243524266LL, v5, a4);
    v13(
      Input::ComprehensiveSkill::PullTemporaryClient,
      (unsigned __int64)Input::ComprehensiveSkill::PullTemporaryClient ^ 0x1BA817,
      763911);
    return *((unsigned __int16 *)Input::ComprehensiveSkill::QuickestOperation + v4);
  }
}

```

## disassembly

```asm
0x1800224a0  mov     [rsp-8+arg_8], rbx
0x1800224a5  mov     [rsp-8+arg_10], rsi
0x1800224aa  mov     [rsp-8+arg_18], rdi
0x1800224af  push    rbp
0x1800224b0  lea     rbp, [rsp-57h]
0x1800224b5  sub     rsp, 0D0h
0x1800224bc  mov     rax, cs:__security_cookie
0x1800224c3  xor     rax, rsp
0x1800224c6  mov     [rbp+57h+var_10], rax
0x1800224ca  movsxd  rdi, edx
0x1800224cd  cmp     edi, 17h
0x1800224d0  ja      loc_1800225EE
0x1800224d6  lfence
0x1800224d9  mov     r8d, cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x1800224e0  mov     eax, 0AFB2ACDh
0x1800224e5  mov     ecx, r8d
0x1800224e8  xor     ecx, 0DEE2F4E7h
0x1800224ee  mul     ecx
0x1800224f0  mov     rax, [rbp+5Fh]
0x1800224f4  shr     edx, 11h
0x1800224f7  cmp     [rax], dl
0x1800224f9  jz      short loc_18002250F
0x1800224fb  xor     r8d, 0FBC31CDAh
0x180022502  cmp     r8d, 67089h
0x180022509  jz      loc_1800225A9
0x18002250f  mov     r10d, cs:?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x180022516  lea     r9, ?PaintShortTermException@ScatteredInformation@@2QBIB; uint const near * const ScatteredInformation::PaintShortTermException
0x18002251d  xor     r10d, 157E9386h
0x180022524  lea     rsi, ?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x18002252b  xor     ebx, ebx
0x18002252d  nop     dword ptr [rax]
0x180022530  mov     ecx, [r9+4]
0x180022534  lea     r9, [r9+8]
0x180022538  xor     ecx, r10d
0x18002253b  mov     eax, 68404C21h
0x180022540  mul     ecx
0x180022542  mov     ecx, [r9-8]
0x180022546  mov     eax, 68404C21h
0x18002254b  xor     ecx, r10d
0x18002254e  shr     edx, 16h
0x180022551  movzx   r8d, dl
0x180022555  mul     ecx
0x180022557  sub     r8d, ebx
0x18002255a  shr     edx, 16h
0x18002255d  dec     r8d
0x180022560  movzx   ecx, dl
0x180022563  sub     ecx, ebx
0x180022565  add     ebx, 2
0x180022568  mov     rax, [rsi+r8*8+8]
0x18002256d  mov     [rsi+rcx*8+8], rax
0x180022572  cmp     ebx, 1Eh
0x180022575  jb      short loc_180022530
0x180022577  mov     eax, cs:?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x18002257d  mov     edx, 0D12440EAh
0x180022582  xor     eax, 157E9386h
0x180022587  mov     rcx, 3F9FBF3F20C02070h
0x180022591  mov     cs:?OddMap@IntegralRelation@@2IA, eax; uint IntegralRelation::OddMap
0x180022597  call    GenerateMixedProvider
0x18002259c  mov     edx, 68h ; 'h'
0x1800225a1  xor     ecx, ecx
0x1800225a3  call    cs:__guard_dispatch_icall_fptr
0x1800225a9  mov     edx, 0C15440AAh
0x1800225ae  mov     rcx, 2FEFBF7FC080E000h
0x1800225b8  call    GenerateMixedProvider
0x1800225bd  lea     rdx, ?PullTemporaryClient@ComprehensiveSkill@Input@@QEAAFHH@Z; Input::ComprehensiveSkill::PullTemporaryClient(int,int)
0x1800225c4  mov     r8d, 0BA807h
0x1800225ca  xor     rdx, 1BA817h
0x1800225d1  lea     rcx, ?PullTemporaryClient@ComprehensiveSkill@Input@@QEAAFHH@Z; Input::ComprehensiveSkill::PullTemporaryClient(int,int)
0x1800225d8  call    cs:__guard_dispatch_icall_fptr
0x1800225de  lea     rcx, ?QuickestOperation@ComprehensiveSkill@Input@@0V?$OneContext@F$0BJ@$00$0A@$0DC@@Data@@B; Data::OneContext<short,25,1,0,50> const Input::ComprehensiveSkill::QuickestOperation
0x1800225e5  movzx   eax, word ptr [rcx+rdi*2]
0x1800225e9  jmp     loc_180022A0A
0x1800225ee  cmp     edi, 18h
0x1800225f1  jnz     loc_180022840
0x1800225f7  mov     ecx, cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x1800225fd  mov     eax, ecx
0x1800225ff  xor     eax, 0FBFC93DEh
0x180022604  mov     [rsp+0D0h+arg_0], r14
0x18002260c  lea     r14d, [r8+3E9h]
0x180022613  cmp     eax, 39FF8Dh
0x180022618  jnz     short loc_18002263C
0x18002261a  xor     ecx, 0B3F57F27h
0x180022620  mov     eax, 69B922D9h
0x180022625  mul     ecx
0x180022627  mov     rax, [rbp+5Fh]
0x18002262b  sub     ecx, edx
0x18002262d  shr     ecx, 1
0x18002262f  add     ecx, edx
0x180022631  shr     ecx, 16h
0x180022634  cmp     [rax], cl
0x180022636  jnz     loc_1800227FA
0x18002263c  mov     r11d, cs:?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x180022643  lea     r9, ?PaintShortTermException@ScatteredInformation@@2QBIB; uint const near * const ScatteredInformation::PaintShortTermException
0x18002264a  xor     r11d, 157E9386h
0x180022651  lea     rsi, ?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x180022658  xor     ebx, ebx
0x18002265a  mov     r10d, ebx
0x18002265d  nop     dword ptr [rax]
0x180022660  mov     ecx, [r9+4]
0x180022664  lea     r9, [r9+8]
0x180022668  xor     ecx, r11d
0x18002266b  mov     eax, 68404C21h
0x180022670  mul     ecx
0x180022672  mov     ecx, [r9-8]
0x180022676  mov     eax, 68404C21h
0x18002267b  xor     ecx, r11d
0x18002267e  shr     edx, 16h
0x180022681  movzx   r8d, dl
0x180022685  mul     ecx
0x180022687  sub     r8d, r10d
0x18002268a  shr     edx, 16h
0x18002268d  dec     r8d
0x180022690  movzx   ecx, dl
0x180022693  sub     ecx, r10d
0x180022696  add     r10d, 2
0x18002269a  mov     rax, [rsi+r8*8+8]
0x18002269f  mov     [rsi+rcx*8+8], rax
0x1800226a4  cmp     r10d, 1Eh
0x1800226a8  jb      short loc_180022660
0x1800226aa  mov     edi, cs:?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x1800226b0  lea     r8, [rbp+57h+var_90]
0x1800226b4  mov     rax, 2F5FFFFF008080D0h
0x1800226be  mov     [rbp+57h+var_B0], ebx
0x1800226c1  mov     [rbp+57h+var_A8], rax
0x1800226c5  lea     rdx, [rbp+57h+var_A8]
0x1800226c9  mov     rax, 0EF8F2FCFF09060B0h
0x1800226d3  mov     [rbp+57h+var_90], 370F3F07h
0x1800226da  xor     edi, 157E9386h
0x1800226e0  mov     [rbp+57h+var_A0], rax
0x1800226e4  mov     rcx, rsi
0x1800226e7  mov     cs:?OddMap@IntegralRelation@@2IA, edi; uint IntegralRelation::OddMap
0x1800226ed  mov     [rbp+57h+var_8C], 271F2F17h
0x1800226f4  mov     [rbp+57h+var_88], 360E3E06h
0x1800226fb  mov     [rbp+57h+var_84], 261E2E16h
0x180022702  mov     [rbp+57h+var_80], 350D3D05h
0x180022709  mov     [rbp+57h+var_7C], 251D2D15h
0x180022710  mov     [rbp+57h+var_78], 340C3C04h
0x180022717  mov     [rbp+57h+var_74], 241C2C14h
0x18002271e  mov     [rbp+57h+var_70], 330B3B03h
0x180022725  mov     [rbp+57h+var_6C], 231B2B13h
0x18002272c  mov     [rbp+57h+var_68], 320A3A02h
0x180022733  mov     [rbp+57h+var_64], 221A2A12h
0x18002273a  mov     [rbp+57h+var_60], 31093901h
0x180022741  mov     [rbp+57h+var_5C], 21192911h
0x180022748  mov     [rbp+57h+var_58], 30083800h
0x18002274f  mov     [rbp+57h+var_54], 20182810h
0x180022756  mov     [rbp+57h+var_50], 370F3F07h
0x18002275d  mov     [rbp+57h+var_4C], 271F2F17h
0x180022764  mov     [rbp+57h+var_48], 360E3E06h
0x18002276b  mov     [rbp+57h+var_44], 261E2E16h
0x180022772  mov     [rbp+57h+var_40], 350D3D05h
0x180022779  mov     [rbp+57h+var_3C], 251D2D15h
0x180022780  mov     [rbp+57h+var_38], 340C3C04h
0x180022787  mov     [rbp+57h+var_34], 241C2C14h
0x18002278e  mov     [rbp+57h+var_30], 330B3B03h
0x180022795  mov     [rbp+57h+var_2C], 231B2B13h
0x18002279c  mov     [rbp+57h+var_28], 320A3A02h
0x1800227a3  mov     [rbp+57h+var_24], 221A2A12h
0x1800227aa  mov     [rbp+57h+var_20], 31093901h
0x1800227b1  mov     [rbp+57h+var_1C], 21192911h
0x1800227b8  mov     [rbp+57h+var_18], 30083800h
0x1800227bf  mov     [rbp+57h+var_14], 20182810h
0x1800227c6  call    ??$WriteConstructStrategy@_K$0EA@@ScatteredInformation@@AEBA_KAEB_KAEAY0EA@$$CBE@Z; ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(unsigned __int64 const &,uchar const (&)[64])
0x1800227cb  mov     rbx, rax
0x1800227ce  lea     r8, [rbp+57h+var_50]
0x1800227d2  lea     rdx, [rbp+57h+var_A0]
0x1800227d6  mov     rcx, rsi
0x1800227d9  xor     ebx, 0AAAAAAAAh
0x1800227df  call    ??$WriteConstructStrategy@_K$0EA@@ScatteredInformation@@AEBA_KAEB_KAEAY0EA@$$CBE@Z; ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(unsigned __int64 const &,uchar const (&)[64])
0x1800227e4  xor     eax, 0AAAAAAAAh
0x1800227e9  lea     rcx, [rbp+57h+var_B0]
0x1800227ed  sub     eax, edi
0x1800227ef  mov     r8d, ebx
0x1800227f2  mov     edx, eax
0x1800227f4  call    cs:__imp__o__controlfp_s
0x1800227fa  mov     edx, 0E10420AAh
0x1800227ff  mov     rcx, 0FBFDF7FE070E050h
0x180022809  call    GenerateMixedProvider
0x18002280e  lea     rdx, ?PullTemporaryClient@ComprehensiveSkill@Input@@QEAAFHH@Z; Input::ComprehensiveSkill::PullTemporaryClient(int,int)
0x180022815  mov     r8d, 16A5ABh
0x18002281b  xor     rdx, 26A5BBh
0x180022822  lea     rcx, ?PullTemporaryClient@ComprehensiveSkill@Input@@QEAAFHH@Z; Input::ComprehensiveSkill::PullTemporaryClient(int,int)
0x180022829  call    cs:__guard_dispatch_icall_fptr
0x18002282f  movzx   eax, r14w
0x180022833  mov     r14, [rsp+0D0h+arg_0]
0x18002283b  jmp     loc_180022A0A
0x180022840  mov     r8d, cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x180022847  mov     eax, 5B8181FFh
0x18002284c  mov     ecx, r8d
0x18002284f  xor     ebx, ebx
0x180022851  xor     ecx, 0BC9398F3h
0x180022857  mul     ecx
0x180022859  mov     rax, [rbp+5Fh]
0x18002285d  shr     edx, 15h
0x180022860  cmp     [rax], dl
0x180022862  jz      short loc_180022878
0x180022864  xor     r8d, 0FBA46DDDh
0x18002286b  cmp     r8d, 61018Eh
0x180022872  jz      loc_1800229D2
0x180022878  mov     r11d, cs:?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x18002287f  lea     r9, ?PaintShortTermException@ScatteredInformation@@2QBIB; uint const near * const ScatteredInformation::PaintShortTermException
0x180022886  xor     r11d, 157E9386h
0x18002288d  lea     rsi, ?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x180022894  mov     r10d, ebx
0x180022897  nop     word ptr [rax+rax+00000000h]
0x1800228a0  mov     ecx, [r9+4]
0x1800228a4  lea     r9, [r9+8]
0x1800228a8  xor     ecx, r11d
0x1800228ab  mov     eax, 68404C21h
0x1800228b0  mul     ecx
0x1800228b2  mov     ecx, [r9-8]
0x1800228b6  mov     eax, 68404C21h
0x1800228bb  xor     ecx, r11d
0x1800228be  shr     edx, 16h
0x1800228c1  movzx   r8d, dl
0x1800228c5  mul     ecx
0x1800228c7  sub     r8d, r10d
0x1800228ca  shr     edx, 16h
0x1800228cd  dec     r8d
0x1800228d0  movzx   ecx, dl
0x1800228d3  sub     ecx, r10d
0x1800228d6  add     r10d, 2
0x1800228da  mov     rax, [rsi+r8*8+8]
0x1800228df  mov     [rsi+rcx*8+8], rax
0x1800228e4  cmp     r10d, 1Eh
0x1800228e8  jb      short loc_1800228A0
0x1800228ea  mov     eax, cs:?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x1800228f0  lea     rdi, [rbp+5Fh]
0x1800228f4  xor     eax, 157E9386h
0x1800228f9  mov     edx, 11C460AAh
0x1800228fe  mov     rcx, 0FF7F9F7F00A000D0h
0x180022908  mov     cs:?OddMap@IntegralRelation@@2IA, eax; uint IntegralRelation::OddMap
0x18002290e  call    GenerateMixedProvider
0x180022913  mov     r9d, cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x18002291a  mov     r8, rax
0x18002291d  mov     ecx, r9d
0x180022920  mov     eax, 68404C21h
0x180022925  xor     ecx, 0E48A768Eh
0x18002292b  mov     r10d, ebx
0x18002292e  mul     ecx
0x180022930  mov     r11d, edx
0x180022933  shr     r11d, 16h
0x180022937  cmp     [r8], r11b
0x18002293a  jnz     short loc_180022987
0x18002293c  mov     ecx, r9d
0x18002293f  mov     eax, 68404C21h
0x180022944  xor     ecx, 80A19D34h
0x18002294a  mul     ecx
0x18002294c  shr     edx, 16h
0x18002294f  cmp     [r8+1], dl
0x180022953  jnz     short loc_180022987
0x180022955  mov     ecx, r9d
0x180022958  mov     eax, 68404C21h
0x18002295d  xor     ecx, 861CF870h
0x180022963  mul     ecx
0x180022965  shr     edx, 16h
0x180022968  cmp     [r8+2], dl
0x18002296c  jnz     short loc_180022987
0x18002296e  mov     ecx, r9d
0x180022971  mov     eax, 68404C21h
0x180022976  xor     ecx, 0E2EEE854h
0x18002297c  mul     ecx
0x18002297e  shr     edx, 16h
0x180022981  cmp     [r8+3], dl
0x180022985  jz      short loc_180022998
0x180022987  inc     r10d
0x18002298a  inc     r8
0x18002298d  cmp     r10d, 258h
0x180022994  jb      short loc_180022937
0x180022996  jmp     short loc_1800229C7
0x180022998  mov     [rdi], r8
0x18002299b  xorps   xmm0, xmm0
0x18002299e  movups  xmmword ptr [rdi+8], xmm0
0x1800229a2  xor     eax, eax
0x1800229a4  movups  xmmword ptr [rdi+18h], xmm0
0x1800229a8  movups  xmmword ptr [rdi+28h], xmm0
0x1800229ac  movups  xmmword ptr [rdi+38h], xmm0
0x1800229b0  movups  xmmword ptr [rdi+48h], xmm0
0x1800229b4  movups  xmmword ptr [rdi+58h], xmm0
0x1800229b8  movups  xmmword ptr [rdi+68h], xmm0
0x1800229bc  mov     [rdi+78h], rax
0x1800229c0  mov     r9d, cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x1800229c7  add     r9d, 10h
0x1800229cb  mov     cs:?OddMap@IntegralRelation@@2IA, r9d; uint IntegralRelation::OddMap
0x1800229d2  mov     edx, 61E4A06Ah
0x1800229d7  mov     rcx, 8F5F5FBFC070C030h
0x1800229e1  call    GenerateMixedProvider
0x1800229e6  lea     rdx, ?PullTemporaryClient@ComprehensiveSkill@Input@@QEAAFHH@Z; Input::ComprehensiveSkill::PullTemporaryClient(int,int)
0x1800229ed  mov     r8d, 16618Eh
0x1800229f3  xor     rdx, 26619Eh
0x1800229fa  lea     rcx, ?PullTemporaryClient@ComprehensiveSkill@Input@@QEAAFHH@Z; Input::ComprehensiveSkill::PullTemporaryClient(int,int)
0x180022a01  call    cs:__guard_dispatch_icall_fptr
0x180022a07  movzx   eax, bx
0x180022a0a  mov     rcx, [rbp+57h+var_10]
0x180022a0e  xor     rcx, rsp; StackCookie
0x180022a11  call    __security_check_cookie
0x180022a16  lea     r11, [rsp+0D0h+var_s0]
0x180022a1e  mov     rbx, [r11+18h]
0x180022a22  mov     rsi, [r11+20h]
0x180022a26  mov     rdi, [r11+28h]
  ... truncated ...
```
