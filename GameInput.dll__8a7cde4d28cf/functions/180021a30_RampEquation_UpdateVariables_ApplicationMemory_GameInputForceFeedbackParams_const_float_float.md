# RampEquation::UpdateVariables(ApplicationMemory &,GameInputForceFeedbackParams const *,float,float)

- ea: `0x180021a30`
- end: `0x180021d60`
- name: `?UpdateVariables@RampEquation@@EEAAJAEAVApplicationMemory@@PEBUGameInputForceFeedbackParams@@MM@Z`
- size: `816`
- prototype: `__int64 __usercall@<rax>(RampEquation *__hidden this@<rcx>, struct ApplicationMemory *@<rdx>, const struct GameInputForceFeedbackParams *@<r8>, float@<xmm3>, float)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001304`
- `0x180017e70`
- `0x18001e93c`
- `0x18001fa3c`
- `0x180020718`
- `0x180021a30`

## pseudocode

```c
__int64 __fastcall RampEquation::UpdateVariables(
        RampEquation *this,
        struct ApplicationMemory *a2,
        const struct GameInputForceFeedbackParams *a3,
        float a4,
        unsigned int a5)
{
  char *v5; // rsi
  unsigned int updated; // edi
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rcx
  __int16 *v13; // rdx
  __m128i v15; // xmm6
  __m128i v16; // xmm8
  __m128i v17; // xmm7
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned __int16 v20; // ax
  void *v21; // r8
  __m128i v22; // xmm0
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned __int16 v25; // ax
  void *v26; // r8
  const char *v27; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v28; // [rsp+B0h] [rbp+30h] BYREF
  int v29; // [rsp+C0h] [rbp+40h] BYREF

  v5 = (char *)this + 112;
  updated = Equation::UpdateCommonVariables(
              this,
              a2,
              (const struct GameInputForceFeedbackParams *)((char *)a3 + 56),
              a4,
              a5,
              (RampEquation *)((char *)this + 112));
  if ( (updated & 0x80000000) != 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      return updated;
    v12 = qword_180069010;
    if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
      return updated;
    v29 = 20;
    v13 = (__int16 *)&unk_18005B3C0;
LABEL_6:
    v27 = "onecore\\xbox\\gameinput\\feedback\\gipequationmanager\\RampEquation.cpp";
    v28 = updated;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v12,
      (unsigned __int8 *)v13,
      v10,
      v11,
      (__int64 **)&v27,
      (__int64)&v29,
      (__int64)&v28);
    return updated;
  }
  updated = Equation::UpdateEnvelopeVariables(
              this,
              a2,
              (const struct GameInputForceFeedbackParams *)((char *)a3 + 8),
              (struct Equation::EnvelopeVariables *)(v5 + 8));
  if ( (updated & 0x80000000) != 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      return updated;
    v12 = qword_180069010;
    if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
      return updated;
    v29 = 21;
    v13 = word_18005A59A;
    goto LABEL_6;
  }
  v15 = (__m128i)*((unsigned int *)a3 + 14);
  v16 = 0;
  v17 = (__m128i)LODWORD(FLOAT_N1_0);
  v18 = _mm_cvtsi128_si32(v15);
  if ( (unsigned __int8)(v18 >> 23) == 0xFF && (v18 & 0x7FFFFF) != 0
    || (v19 = _mm_cvtsi128_si32(v15), !(unsigned __int8)(v19 >> 23)) && (v19 & 0x7FFFFF) != 0 )
  {
    v15 = 0;
  }
  else if ( *(float *)v15.m128i_i32 < -1.0 )
  {
    v15 = (__m128i)LODWORD(FLOAT_N1_0);
    goto LABEL_20;
  }
  if ( *(float *)v15.m128i_i32 > 1.0 )
    v15 = (__m128i)LODWORD(FLOAT_1_0);
LABEL_20:
  if ( *((float *)this + 38) != *(float *)v15.m128i_i32 )
  {
    v20 = Equation::LookupVariableAddress(this, L"RAMPSTART");
    if ( v20 == 0xFFFF )
      return 2147549183LL;
    updated = ApplicationMemory::UpdateVariable(a2, v20, v21, _mm_cvtsi128_si32(v15));
    if ( (updated & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return updated;
      v12 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        return updated;
      v29 = 30;
      v13 = word_18005CA0A;
      goto LABEL_6;
    }
    *((_DWORD *)this + 38) = v15.m128i_i32[0];
    *((_QWORD *)this + 10) = 0;
  }
  v22 = (__m128i)*((unsigned int *)a3 + 21);
  v23 = _mm_cvtsi128_si32(v22);
  if ( (unsigned __int8)(v23 >> 23) == 0xFF && (v23 & 0x7FFFFF) != 0 )
    goto LABEL_36;
  v24 = _mm_cvtsi128_si32(v22);
  if ( !(unsigned __int8)(v24 >> 23) && (v24 & 0x7FFFFF) != 0 )
    goto LABEL_36;
  if ( *(float *)v22.m128i_i32 >= -1.0 )
  {
    v16 = (__m128i)*((unsigned int *)a3 + 21);
LABEL_36:
    if ( *(float *)v16.m128i_i32 <= 1.0 )
      v17 = v16;
    else
      v17 = (__m128i)LODWORD(FLOAT_1_0);
  }
  if ( *((float *)this + 39) == *(float *)v17.m128i_i32 )
    return 0;
  v25 = Equation::LookupVariableAddress(this, L"RAMPEND");
  if ( v25 != 0xFFFF )
  {
    updated = ApplicationMemory::UpdateVariable(a2, v25, v26, _mm_cvtsi128_si32(v17));
    if ( (updated & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return updated;
      v12 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        return updated;
      v29 = 40;
      v13 = (__int16 *)byte_18005DE8B;
      goto LABEL_6;
    }
    *((_DWORD *)this + 39) = v17.m128i_i32[0];
    *((_QWORD *)this + 10) = 0;
    return 0;
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x180021a30  mov     rax, rsp
0x180021a33  mov     [rax+10h], rbx
0x180021a37  mov     [rax+20h], rsi
0x180021a3b  push    rbp
0x180021a3c  push    rdi
0x180021a3d  push    r12
0x180021a3f  push    r14
0x180021a41  push    r15
0x180021a43  mov     rbp, rsp
0x180021a46  sub     rsp, 80h
0x180021a4d  movss   xmm0, [rbp+arg_20]
0x180021a52  lea     rsi, [rcx+70h]
0x180021a56  movaps  xmmword ptr [rax-38h], xmm6
0x180021a5a  mov     r15, r8
0x180021a5d  mov     [rax-80h], rsi
0x180021a61  add     r8, 38h ; '8'; struct GameInputForceFeedbackMagnitude *
0x180021a65  movaps  xmmword ptr [rax-48h], xmm7
0x180021a69  mov     r12, rdx
0x180021a6c  movss   [rsp+80h+var_60], xmm0; float
0x180021a72  mov     rbx, rcx
0x180021a75  movaps  xmmword ptr [rax-58h], xmm8
0x180021a7a  call    ?UpdateCommonVariables@Equation@@IEAAJAEAVApplicationMemory@@PEBUGameInputForceFeedbackMagnitude@@MMPEAUCommonVariables@1@@Z; Equation::UpdateCommonVariables(ApplicationMemory &,GameInputForceFeedbackMagnitude const *,float,float,Equation::CommonVariables *)
0x180021a7f  mov     edi, eax
0x180021a81  test    eax, eax
0x180021a83  jns     short loc_180021AF1
0x180021a85  mov     ecx, cs:dword_180069000
0x180021a8b  cmp     ecx, 2
0x180021a8e  jbe     short loc_180021AEA
0x180021a90  mov     rdx, cs:qword_180069018
0x180021a97  mov     rcx, cs:qword_180069010
0x180021a9e  test    cl, 8
0x180021aa1  jz      short loc_180021AEA
0x180021aa3  mov     rax, rdx
0x180021aa6  and     eax, 8
0x180021aa9  cmp     rax, rdx
0x180021aac  jnz     short loc_180021AEA
0x180021aae  mov     [rbp+arg_10], 14h
0x180021ab5  lea     rdx, unk_18005B3C0
0x180021abc  lea     rax, aOnecoreXboxGam_5; "onecore\\xbox\\gameinput\\feedback\\gip"...
0x180021ac3  mov     [rbp+var_40], rax
0x180021ac7  lea     rax, [rbp+arg_0]
0x180021acb  mov     [rsp+80h+var_50], rax
0x180021ad0  lea     rax, [rbp+arg_10]
0x180021ad4  mov     [rsp+80h+var_58], rax
0x180021ad9  lea     rax, [rbp+var_40]
0x180021add  mov     qword ptr [rsp+80h+var_60], rax
0x180021ae2  mov     [rbp+arg_0], edi
0x180021ae5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180021aea  mov     eax, edi
0x180021aec  jmp     loc_180021D34
0x180021af1  lea     r9, [rsi+8]; struct Equation::EnvelopeVariables *
0x180021af5  mov     rdx, r12; struct ApplicationMemory *
0x180021af8  lea     r8, [r15+8]; struct GameInputForceFeedbackEnvelope *
0x180021afc  mov     rcx, rbx; this
0x180021aff  call    ?UpdateEnvelopeVariables@Equation@@IEAAJAEAVApplicationMemory@@PEBUGameInputForceFeedbackEnvelope@@PEAUEnvelopeVariables@1@@Z; Equation::UpdateEnvelopeVariables(ApplicationMemory &,GameInputForceFeedbackEnvelope const *,Equation::EnvelopeVariables *)
0x180021b04  mov     edi, eax
0x180021b06  test    eax, eax
0x180021b08  jns     short loc_180021B46
0x180021b0a  mov     ecx, cs:dword_180069000
0x180021b10  cmp     ecx, 2
0x180021b13  jbe     short loc_180021AEA
0x180021b15  mov     rdx, cs:qword_180069018
0x180021b1c  mov     rcx, cs:qword_180069010
0x180021b23  test    cl, 8
0x180021b26  jz      short loc_180021AEA
0x180021b28  mov     rax, rdx
0x180021b2b  and     eax, 8
0x180021b2e  cmp     rax, rdx
0x180021b31  jnz     short loc_180021AEA
0x180021b33  mov     [rbp+arg_10], 15h
0x180021b3a  lea     rdx, word_18005A59A
0x180021b41  jmp     loc_180021ABC
0x180021b46  movss   xmm6, dword ptr [r15+38h]
0x180021b4c  xorps   xmm8, xmm8
0x180021b50  movss   xmm7, cs:__real@bf800000
0x180021b58  mov     esi, 7FFFFFh
0x180021b5d  movd    ecx, xmm6
0x180021b61  mov     eax, ecx
0x180021b63  shr     eax, 17h
0x180021b66  cmp     al, 0FFh
0x180021b68  jnz     short loc_180021B6E
0x180021b6a  test    esi, ecx
0x180021b6c  jnz     short loc_180021B87
0x180021b6e  movd    ecx, xmm6
0x180021b72  mov     eax, ecx
0x180021b74  shr     eax, 17h
0x180021b77  test    al, al
0x180021b79  jnz     loc_180021C2B
0x180021b7f  test    esi, ecx
0x180021b81  jz      loc_180021C2B
0x180021b87  xorps   xmm6, xmm6
0x180021b8a  comiss  xmm6, cs:__real@3f800000
0x180021b91  jbe     short loc_180021B9B
0x180021b93  movss   xmm6, cs:__real@3f800000
0x180021b9b  movss   xmm0, dword ptr [rbx+98h]
0x180021ba3  mov     r14d, 0FFFFh
0x180021ba9  ucomiss xmm0, xmm6
0x180021bac  jp      short loc_180021BB4
0x180021bae  jz      loc_180021C4C
0x180021bb4  lea     rdx, aRampstart; "RAMPSTART"
0x180021bbb  mov     rcx, rbx; this
0x180021bbe  call    ?LookupVariableAddress@Equation@@IEAAGPEBG@Z; Equation::LookupVariableAddress(ushort const *)
0x180021bc3  cmp     ax, r14w
0x180021bc7  jz      loc_180021D2F
0x180021bcd  movd    r9d, xmm6; unsigned int
0x180021bd2  movzx   edx, ax; unsigned __int16
0x180021bd5  mov     rcx, r12; this
0x180021bd8  call    ?UpdateVariable@ApplicationMemory@@QEAAJGPEAXI@Z; ApplicationMemory::UpdateVariable(ushort,void *,uint)
0x180021bdd  mov     edi, eax
0x180021bdf  test    eax, eax
0x180021be1  jns     short loc_180021C3C
0x180021be3  mov     ecx, cs:dword_180069000
0x180021be9  cmp     ecx, 2
0x180021bec  jbe     loc_180021AEA
0x180021bf2  mov     rdx, cs:qword_180069018
0x180021bf9  mov     rcx, cs:qword_180069010
0x180021c00  test    cl, 8
0x180021c03  jz      loc_180021AEA
0x180021c09  mov     rax, rdx
0x180021c0c  and     eax, 8
0x180021c0f  cmp     rax, rdx
0x180021c12  jnz     loc_180021AEA
0x180021c18  mov     [rbp+arg_10], 1Eh
0x180021c1f  lea     rdx, word_18005CA0A
0x180021c26  jmp     loc_180021ABC
0x180021c2b  comiss  xmm7, xmm6
0x180021c2e  jbe     loc_180021B8A
0x180021c34  movaps  xmm6, xmm7
0x180021c37  jmp     loc_180021B9B
0x180021c3c  movss   dword ptr [rbx+98h], xmm6
0x180021c44  mov     qword ptr [rbx+50h], 0
0x180021c4c  movss   xmm0, dword ptr [r15+54h]
0x180021c52  movd    ecx, xmm0
0x180021c56  mov     eax, ecx
0x180021c58  shr     eax, 17h
0x180021c5b  cmp     al, 0FFh
0x180021c5d  jnz     short loc_180021C63
0x180021c5f  test    esi, ecx
0x180021c61  jnz     short loc_180021C7D
0x180021c63  movd    ecx, xmm0
0x180021c67  mov     eax, ecx
0x180021c69  shr     eax, 17h
0x180021c6c  test    al, al
0x180021c6e  jnz     short loc_180021C74
0x180021c70  test    esi, ecx
0x180021c72  jnz     short loc_180021C7D
0x180021c74  comiss  xmm7, xmm0
0x180021c77  ja      short loc_180021C95
0x180021c79  movaps  xmm8, xmm0
0x180021c7d  comiss  xmm8, cs:__real@3f800000
0x180021c85  jbe     short loc_180021C91
0x180021c87  movss   xmm7, cs:__real@3f800000
0x180021c8f  jmp     short loc_180021C95
0x180021c91  movaps  xmm7, xmm8
0x180021c95  movss   xmm0, dword ptr [rbx+9Ch]
0x180021c9d  ucomiss xmm0, xmm7
0x180021ca0  jp      short loc_180021CA8
0x180021ca2  jz      loc_180021D2B
0x180021ca8  lea     rdx, aRampend; "RAMPEND"
0x180021caf  mov     rcx, rbx; this
0x180021cb2  call    ?LookupVariableAddress@Equation@@IEAAGPEBG@Z; Equation::LookupVariableAddress(ushort const *)
0x180021cb7  cmp     ax, r14w
0x180021cbb  jz      short loc_180021D2F
0x180021cbd  movd    r9d, xmm7; unsigned int
0x180021cc2  movzx   edx, ax; unsigned __int16
0x180021cc5  mov     rcx, r12; this
0x180021cc8  call    ?UpdateVariable@ApplicationMemory@@QEAAJGPEAXI@Z; ApplicationMemory::UpdateVariable(ushort,void *,uint)
0x180021ccd  mov     edi, eax
0x180021ccf  test    eax, eax
0x180021cd1  jns     short loc_180021D1B
0x180021cd3  mov     ecx, cs:dword_180069000
0x180021cd9  cmp     ecx, 2
0x180021cdc  jbe     loc_180021AEA
0x180021ce2  mov     rdx, cs:qword_180069018
0x180021ce9  mov     rcx, cs:qword_180069010
0x180021cf0  test    cl, 8
0x180021cf3  jz      loc_180021AEA
0x180021cf9  mov     rax, rdx
0x180021cfc  and     eax, 8
0x180021cff  cmp     rax, rdx
0x180021d02  jnz     loc_180021AEA
0x180021d08  mov     [rbp+arg_10], 28h ; '('
0x180021d0f  lea     rdx, byte_18005DE8B
0x180021d16  jmp     loc_180021ABC
0x180021d1b  movss   dword ptr [rbx+9Ch], xmm7
0x180021d23  mov     qword ptr [rbx+50h], 0
0x180021d2b  xor     eax, eax
0x180021d2d  jmp     short loc_180021D34
0x180021d2f  mov     eax, 8000FFFFh
0x180021d34  movaps  xmm6, [rsp+80h+var_10]
0x180021d39  lea     r11, [rsp+80h+var_s0]
0x180021d41  mov     rbx, [r11+38h]
0x180021d45  mov     rsi, [r11+48h]
0x180021d49  movaps  xmm8, xmmword ptr [r11-30h]
0x180021d4e  movaps  xmm7, [rsp+80h+var_20]
0x180021d53  mov     rsp, r11
0x180021d56  pop     r15
0x180021d58  pop     r14
0x180021d5a  pop     r12
0x180021d5c  pop     rdi
0x180021d5d  pop     rbp
0x180021d5e  retn
```
