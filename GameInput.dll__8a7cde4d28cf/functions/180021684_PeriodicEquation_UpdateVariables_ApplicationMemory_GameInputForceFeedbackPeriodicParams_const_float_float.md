# PeriodicEquation::UpdateVariables(ApplicationMemory &,GameInputForceFeedbackPeriodicParams const *,float,float)

- ea: `0x180021684`
- end: `0x180021a2a`
- name: `?UpdateVariables@PeriodicEquation@@IEAAJAEAVApplicationMemory@@PEBUGameInputForceFeedbackPeriodicParams@@MM@Z`
- size: `934`
- prototype: `__int64 __usercall@<rax>(PeriodicEquation *__hidden this@<rcx>, struct ApplicationMemory *@<rdx>, const struct GameInputForceFeedbackPeriodicParams *@<r8>, float@<xmm3>, float)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180021d70`

## callees

- `0x180001304`
- `0x180017e70`
- `0x18001e93c`
- `0x18001fa3c`
- `0x180020718`
- `0x180021684`

## pseudocode

```c
__int64 __fastcall PeriodicEquation::UpdateVariables(
        PeriodicEquation *this,
        struct ApplicationMemory *a2,
        const struct GameInputForceFeedbackPeriodicParams *a3,
        float a4,
        float a5)
{
  char *v5; // r15
  unsigned int updated; // edi
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rcx
  __int16 *v13; // rdx
  __m128i v15; // xmm1
  unsigned __int16 v16; // ax
  void *v17; // r8
  __m128i v18; // xmm0
  float v19; // xmm6_4
  float v20; // xmm2_4
  unsigned int v21; // ecx
  __m128i v22; // xmm0
  unsigned int v23; // ecx
  unsigned int v24; // edx
  unsigned int v25; // eax
  float v26; // xmm1_4
  unsigned int v27; // esi
  unsigned __int16 v28; // ax
  void *v29; // r8
  unsigned int v30; // edi
  unsigned __int16 v31; // ax
  void *v32; // r8
  int v33; // esi
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 *v36[2]; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v37; // [rsp+90h] [rbp+30h] BYREF
  int v38; // [rsp+A0h] [rbp+40h] BYREF

  v5 = (char *)this + 112;
  updated = Equation::UpdateCommonVariables(
              this,
              a2,
              (const struct GameInputForceFeedbackPeriodicParams *)((char *)a3 + 48),
              a4,
              a5,
              (PeriodicEquation *)((char *)this + 112));
  if ( (updated & 0x80000000) != 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      return updated;
    v12 = qword_180069010;
    if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
      return updated;
    v38 = 35;
    v13 = &word_18005A9B6;
LABEL_6:
    v36[0] = (__int64 *)"onecore\\xbox\\gameinput\\feedback\\gipequationmanager\\PeriodicEquation.cpp";
    v37 = updated;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v12,
      (unsigned __int8 *)v13,
      v10,
      v11,
      v36,
      (__int64)&v38,
      (__int64)&v37);
    return updated;
  }
  updated = Equation::UpdateEnvelopeVariables(this, a2, a3, (struct Equation::EnvelopeVariables *)(v5 + 8));
  if ( (updated & 0x80000000) != 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      return updated;
    v12 = qword_180069010;
    if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
      return updated;
    v38 = 36;
    v13 = &word_18005BB1E;
    goto LABEL_6;
  }
  v15 = (__m128i)*((unsigned int *)a3 + 21);
  if ( *((float *)this + 38) != *(float *)v15.m128i_i32 )
  {
    v16 = Equation::LookupVariableAddress(this, L"OFFSET");
    if ( v16 == 0xFFFF )
      return 2147549183LL;
    updated = ApplicationMemory::UpdateVariable(a2, v16, v17, _mm_cvtsi128_si32(v15));
    if ( (updated & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return updated;
      v12 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        return updated;
      v38 = 42;
      v13 = &word_18005E4B6;
      goto LABEL_6;
    }
    *((_DWORD *)this + 38) = *((_DWORD *)a3 + 21);
  }
  v18 = (__m128i)*((unsigned int *)a3 + 19);
  v19 = 0.0;
  v20 = FLOAT_N1_0;
  v21 = _mm_cvtsi128_si32(v18);
  if ( (unsigned __int8)(v21 >> 23) != 0xFF
    && ((unsigned __int8)(v21 >> 23) || (v21 & 0x7FFFFF) == 0)
    && *(float *)v18.m128i_i32 > 0.0 )
  {
    v20 = (float)(*(float *)(*((_QWORD *)this + 5) + 4LL) * 1000000.0) / *(float *)v18.m128i_i32;
    v22 = (__m128i)*((unsigned int *)a3 + 20);
    v23 = _mm_cvtsi128_si32(v22);
    if ( (unsigned __int8)(v23 >> 23) != 0xFF && ((unsigned __int8)(v23 >> 23) || (v23 & 0x7FFFFF) == 0) )
    {
      *(float *)v22.m128i_i32 = *(float *)v22.m128i_i32 / 360.0;
      v24 = _mm_cvtsi128_si32(v22);
      v25 = v24 >> 23;
      if ( (unsigned __int8)(v24 >> 23) < 0x96u )
      {
        if ( (unsigned __int8)v25 >= 0x7Fu )
          LODWORD(v26) = v24 & (-1 << (-106 - v25));
        else
          v26 = 0.0;
      }
      else
      {
        v26 = *(float *)v22.m128i_i32;
      }
      v19 = (float)(*(float *)v22.m128i_i32 - v26) * v20;
    }
  }
  v27 = (int)v20;
  if ( *((_DWORD *)this + 40) != (int)v20 )
  {
    v28 = Equation::LookupVariableAddress(this, L"PERIOD");
    if ( v28 == 0xFFFF )
      return 2147549183LL;
    updated = ApplicationMemory::UpdateVariable(a2, v28, v29, v27);
    if ( (updated & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return updated;
      v12 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        return updated;
      v38 = 67;
      v13 = (__int16 *)&unk_18005D440;
      goto LABEL_6;
    }
    *((_DWORD *)this + 40) = v27;
  }
  v30 = (int)v19;
  if ( *((_DWORD *)this + 39) == (int)v19 )
    return 0;
  v31 = Equation::LookupVariableAddress(this, L"PHASE");
  if ( v31 == 0xFFFF )
    return 2147549183LL;
  v33 = ApplicationMemory::UpdateVariable(a2, v31, v32, v30);
  if ( v33 >= 0 )
  {
    *((_DWORD *)this + 39) = v30;
    *((_QWORD *)this + 10) = 0;
    return 0;
  }
  if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
  {
    v37 = v33;
    v36[0] = (__int64 *)"onecore\\xbox\\gameinput\\feedback\\gipequationmanager\\PeriodicEquation.cpp";
    v38 = 76;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_180069010,
      (unsigned __int8 *)&dword_18005B73C,
      v34,
      v35,
      v36,
      (__int64)&v38,
      (__int64)&v37);
  }
  return (unsigned int)v33;
}

```

## disassembly

```asm
0x180021684  mov     rax, rsp
0x180021687  mov     [rax+10h], rbx
0x18002168b  push    rbp
0x18002168c  push    rsi
0x18002168d  push    rdi
0x18002168e  push    r14
0x180021690  push    r15
0x180021692  mov     rbp, rsp
0x180021695  sub     rsp, 60h
0x180021699  movss   xmm0, [rbp+arg_20]
0x18002169e  lea     r15, [rcx+70h]
0x1800216a2  mov     rsi, r8
0x1800216a5  mov     [rax-60h], r15
0x1800216a9  add     r8, 30h ; '0'; struct GameInputForceFeedbackMagnitude *
0x1800216ad  movss   dword ptr [rax-68h], xmm0
0x1800216b2  movaps  xmmword ptr [rax-38h], xmm6
0x1800216b6  mov     r14, rdx
0x1800216b9  mov     rbx, rcx
0x1800216bc  call    ?UpdateCommonVariables@Equation@@IEAAJAEAVApplicationMemory@@PEBUGameInputForceFeedbackMagnitude@@MMPEAUCommonVariables@1@@Z; Equation::UpdateCommonVariables(ApplicationMemory &,GameInputForceFeedbackMagnitude const *,float,float,Equation::CommonVariables *)
0x1800216c1  mov     edi, eax
0x1800216c3  test    eax, eax
0x1800216c5  jns     short loc_180021733
0x1800216c7  mov     ecx, cs:dword_180069000
0x1800216cd  cmp     ecx, 2
0x1800216d0  jbe     short loc_18002172C
0x1800216d2  mov     rdx, cs:qword_180069018
0x1800216d9  mov     rcx, cs:qword_180069010
0x1800216e0  test    cl, 8
0x1800216e3  jz      short loc_18002172C
0x1800216e5  mov     rax, rdx
0x1800216e8  and     eax, 8
0x1800216eb  cmp     rax, rdx
0x1800216ee  jnz     short loc_18002172C
0x1800216f0  mov     [rbp+arg_10], 23h ; '#'
0x1800216f7  lea     rdx, word_18005A9B6
0x1800216fe  lea     rax, aOnecoreXboxGam_34; "onecore\\xbox\\gameinput\\feedback\\gip"...
0x180021705  mov     [rbp+var_20], rax
0x180021709  lea     rax, [rbp+arg_0]
0x18002170d  mov     [rsp+60h+var_30], rax
0x180021712  lea     rax, [rbp+arg_10]
0x180021716  mov     [rsp+60h+var_38], rax
0x18002171b  lea     rax, [rbp+var_20]
0x18002171f  mov     [rsp+60h+var_40], rax
0x180021724  mov     [rbp+arg_0], edi
0x180021727  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002172c  mov     eax, edi
0x18002172e  jmp     loc_180021A10
0x180021733  lea     r9, [r15+8]; struct Equation::EnvelopeVariables *
0x180021737  mov     r8, rsi; struct GameInputForceFeedbackEnvelope *
0x18002173a  mov     rdx, r14; struct ApplicationMemory *
0x18002173d  mov     rcx, rbx; this
0x180021740  call    ?UpdateEnvelopeVariables@Equation@@IEAAJAEAVApplicationMemory@@PEBUGameInputForceFeedbackEnvelope@@PEAUEnvelopeVariables@1@@Z; Equation::UpdateEnvelopeVariables(ApplicationMemory &,GameInputForceFeedbackEnvelope const *,Equation::EnvelopeVariables *)
0x180021745  mov     edi, eax
0x180021747  test    eax, eax
0x180021749  jns     short loc_180021787
0x18002174b  mov     ecx, cs:dword_180069000
0x180021751  cmp     ecx, 2
0x180021754  jbe     short loc_18002172C
0x180021756  mov     rdx, cs:qword_180069018
0x18002175d  mov     rcx, cs:qword_180069010
0x180021764  test    cl, 8
0x180021767  jz      short loc_18002172C
0x180021769  mov     rax, rdx
0x18002176c  and     eax, 8
0x18002176f  cmp     rax, rdx
0x180021772  jnz     short loc_18002172C
0x180021774  mov     [rbp+arg_10], 24h ; '$'
0x18002177b  lea     rdx, word_18005BB1E
0x180021782  jmp     loc_1800216FE
0x180021787  movss   xmm1, dword ptr [rsi+54h]
0x18002178c  mov     r15d, 0FFFFh
0x180021792  movss   xmm0, dword ptr [rbx+98h]
0x18002179a  ucomiss xmm0, xmm1
0x18002179d  jp      short loc_1800217A5
0x18002179f  jz      loc_180021825
0x1800217a5  lea     rdx, aOffset; "OFFSET"
0x1800217ac  mov     rcx, rbx; this
0x1800217af  call    ?LookupVariableAddress@Equation@@IEAAGPEBG@Z; Equation::LookupVariableAddress(ushort const *)
0x1800217b4  cmp     ax, r15w
0x1800217b8  jz      loc_180021A0B
0x1800217be  movd    r9d, xmm1; unsigned int
0x1800217c3  movzx   edx, ax; unsigned __int16
0x1800217c6  mov     rcx, r14; this
0x1800217c9  call    ?UpdateVariable@ApplicationMemory@@QEAAJGPEAXI@Z; ApplicationMemory::UpdateVariable(ushort,void *,uint)
0x1800217ce  mov     edi, eax
0x1800217d0  test    eax, eax
0x1800217d2  jns     short loc_18002181C
0x1800217d4  mov     ecx, cs:dword_180069000
0x1800217da  cmp     ecx, 2
0x1800217dd  jbe     loc_18002172C
0x1800217e3  mov     rdx, cs:qword_180069018
0x1800217ea  mov     rcx, cs:qword_180069010
0x1800217f1  test    cl, 8
0x1800217f4  jz      loc_18002172C
0x1800217fa  mov     rax, rdx
0x1800217fd  and     eax, 8
0x180021800  cmp     rax, rdx
0x180021803  jnz     loc_18002172C
0x180021809  mov     [rbp+arg_10], 2Ah ; '*'
0x180021810  lea     rdx, word_18005E4B6
0x180021817  jmp     loc_1800216FE
0x18002181c  mov     eax, [rsi+54h]
0x18002181f  mov     [rbx+98h], eax
0x180021825  movss   xmm0, dword ptr [rsi+4Ch]
0x18002182a  xorps   xmm6, xmm6
0x18002182d  movss   xmm2, cs:__real@bf800000
0x180021835  movd    ecx, xmm0
0x180021839  mov     eax, ecx
0x18002183b  shr     eax, 17h
0x18002183e  cmp     al, 0FFh
0x180021840  jz      loc_1800218CA
0x180021846  mov     edx, 7FFFFFh
0x18002184b  test    al, al
0x18002184d  jnz     short loc_180021853
0x18002184f  test    edx, ecx
0x180021851  jnz     short loc_1800218CA
0x180021853  comiss  xmm0, xmm6
0x180021856  jbe     short loc_1800218CA
0x180021858  mov     rax, [rbx+28h]
0x18002185c  movss   xmm2, dword ptr [rax+4]
0x180021861  mulss   xmm2, cs:__real@49742400
0x180021869  divss   xmm2, xmm0
0x18002186d  movss   xmm0, dword ptr [rsi+50h]
0x180021872  movd    ecx, xmm0
0x180021876  mov     eax, ecx
0x180021878  shr     eax, 17h
0x18002187b  cmp     al, 0FFh
0x18002187d  jz      short loc_1800218CA
0x18002187f  test    al, al
0x180021881  jnz     short loc_180021887
0x180021883  test    edx, ecx
0x180021885  jnz     short loc_1800218CA
0x180021887  divss   xmm0, cs:__real@43b40000
0x18002188f  mov     ecx, 96h
0x180021894  movd    edx, xmm0
0x180021898  mov     eax, edx
0x18002189a  shr     eax, 17h
0x18002189d  cmp     al, cl
0x18002189f  jb      short loc_1800218A6
0x1800218a1  movaps  xmm1, xmm0
0x1800218a4  jmp     short loc_1800218BF
0x1800218a6  cmp     al, 7Fh
0x1800218a8  jnb     short loc_1800218AF
0x1800218aa  xorps   xmm1, xmm1
0x1800218ad  jmp     short loc_1800218BF
0x1800218af  movzx   eax, al
0x1800218b2  sub     ecx, eax
0x1800218b4  or      eax, 0FFFFFFFFh
0x1800218b7  shl     eax, cl
0x1800218b9  and     eax, edx
0x1800218bb  movd    xmm1, eax
0x1800218bf  movaps  xmm6, xmm0
0x1800218c2  subss   xmm6, xmm1
0x1800218c6  mulss   xmm6, xmm2
0x1800218ca  cvttss2si rsi, xmm2
0x1800218cf  cmp     [rbx+0A0h], esi
0x1800218d5  jz      short loc_180021952
0x1800218d7  lea     rdx, aPeriod; "PERIOD"
0x1800218de  mov     rcx, rbx; this
0x1800218e1  call    ?LookupVariableAddress@Equation@@IEAAGPEBG@Z; Equation::LookupVariableAddress(ushort const *)
0x1800218e6  cmp     ax, r15w
0x1800218ea  jz      loc_180021A0B
0x1800218f0  mov     r9d, esi; unsigned int
0x1800218f3  movzx   edx, ax; unsigned __int16
0x1800218f6  mov     rcx, r14; this
0x1800218f9  call    ?UpdateVariable@ApplicationMemory@@QEAAJGPEAXI@Z; ApplicationMemory::UpdateVariable(ushort,void *,uint)
0x1800218fe  mov     edi, eax
0x180021900  test    eax, eax
0x180021902  jns     short loc_18002194C
0x180021904  mov     ecx, cs:dword_180069000
0x18002190a  cmp     ecx, 2
0x18002190d  jbe     loc_18002172C
0x180021913  mov     rdx, cs:qword_180069018
0x18002191a  mov     rcx, cs:qword_180069010
0x180021921  test    cl, 8
0x180021924  jz      loc_18002172C
0x18002192a  mov     rax, rdx
0x18002192d  and     eax, 8
0x180021930  cmp     rax, rdx
0x180021933  jnz     loc_18002172C
0x180021939  mov     [rbp+arg_10], 43h ; 'C'
0x180021940  lea     rdx, unk_18005D440
0x180021947  jmp     loc_1800216FE
0x18002194c  mov     [rbx+0A0h], esi
0x180021952  cvttss2si rdi, xmm6
0x180021957  cmp     [rbx+9Ch], edi
0x18002195d  jz      loc_180021A07
0x180021963  lea     rdx, aPhase; "PHASE"
0x18002196a  mov     rcx, rbx; this
0x18002196d  call    ?LookupVariableAddress@Equation@@IEAAGPEBG@Z; Equation::LookupVariableAddress(ushort const *)
0x180021972  cmp     ax, r15w
0x180021976  jz      loc_180021A0B
0x18002197c  mov     r9d, edi; unsigned int
0x18002197f  movzx   edx, ax; unsigned __int16
0x180021982  mov     rcx, r14; this
0x180021985  call    ?UpdateVariable@ApplicationMemory@@QEAAJGPEAXI@Z; ApplicationMemory::UpdateVariable(ushort,void *,uint)
0x18002198a  mov     esi, eax
0x18002198c  test    eax, eax
0x18002198e  jns     short loc_1800219F9
0x180021990  mov     ecx, cs:dword_180069000
0x180021996  cmp     ecx, 2
0x180021999  jbe     short loc_1800219F5
0x18002199b  mov     rdx, cs:qword_180069018
0x1800219a2  mov     rcx, cs:qword_180069010
0x1800219a9  test    cl, 8
0x1800219ac  jz      short loc_1800219F5
0x1800219ae  mov     rax, rdx
0x1800219b1  and     eax, 8
0x1800219b4  cmp     rax, rdx
0x1800219b7  jnz     short loc_1800219F5
0x1800219b9  lea     rax, aOnecoreXboxGam_34; "onecore\\xbox\\gameinput\\feedback\\gip"...
0x1800219c0  mov     [rbp+arg_0], esi
0x1800219c3  mov     [rbp+var_20], rax
0x1800219c7  lea     rdx, dword_18005B73C
0x1800219ce  lea     rax, [rbp+arg_0]
0x1800219d2  mov     [rbp+arg_10], 4Ch ; 'L'
0x1800219d9  mov     [rsp+60h+var_30], rax
0x1800219de  lea     rax, [rbp+arg_10]
0x1800219e2  mov     [rsp+60h+var_38], rax
0x1800219e7  lea     rax, [rbp+var_20]
0x1800219eb  mov     [rsp+60h+var_40], rax
0x1800219f0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800219f5  mov     eax, esi
0x1800219f7  jmp     short loc_180021A10
0x1800219f9  mov     [rbx+9Ch], edi
0x1800219ff  mov     qword ptr [rbx+50h], 0
0x180021a07  xor     eax, eax
0x180021a09  jmp     short loc_180021A10
0x180021a0b  mov     eax, 8000FFFFh
0x180021a10  mov     rbx, [rsp+60h+arg_8]
0x180021a18  movaps  xmm6, [rsp+60h+var_10]
0x180021a1d  add     rsp, 60h
0x180021a21  pop     r15
0x180021a23  pop     r14
0x180021a25  pop     rdi
0x180021a26  pop     rsi
0x180021a27  pop     rbp
0x180021a28  retn
```
