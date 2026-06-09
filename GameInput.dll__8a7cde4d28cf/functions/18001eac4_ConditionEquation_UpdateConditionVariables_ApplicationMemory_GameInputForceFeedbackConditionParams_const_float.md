# ConditionEquation::UpdateConditionVariables(ApplicationMemory &,GameInputForceFeedbackConditionParams const *,float,float,ConditionEquation::ConditionVariables *)

- ea: `0x18001eac4`
- end: `0x18001ef90`
- name: `?UpdateConditionVariables@ConditionEquation@@IEAAJAEAVApplicationMemory@@PEBUGameInputForceFeedbackConditionParams@@MMPEAUConditionVariables@1@@Z`
- size: `1228`
- prototype: `__int64 __usercall@<rax>(ConditionEquation *__hidden this@<rcx>, struct ApplicationMemory *@<rdx>, const struct GameInputForceFeedbackConditionParams *@<r8>, float@<xmm3>, float, struct ConditionEquation::ConditionVariables *)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800207b0`
- `0x180021d80`

## callees

- `0x180001304`
- `0x180017e70`
- `0x18001e93c`
- `0x18001eac4`
- `0x180020718`

## pseudocode

```c
__int64 __fastcall ConditionEquation::UpdateConditionVariables(
        ConditionEquation *this,
        struct ApplicationMemory *a2,
        const struct GameInputForceFeedbackConditionParams *a3,
        float a4,
        float a5,
        struct ConditionEquation::ConditionVariables *a6)
{
  unsigned int updated; // edi
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rcx
  char *v13; // rdx
  __m128i v15; // xmm7
  __m128i v16; // xmm6
  unsigned __int16 v17; // ax
  void *v18; // r8
  __m128i v19; // xmm7
  unsigned __int16 v20; // ax
  void *v21; // r8
  __m128i v22; // xmm7
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned __int16 v25; // ax
  void *v26; // r8
  __m128i v27; // xmm0
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned __int16 v30; // ax
  void *v31; // r8
  __m128i v32; // xmm1
  unsigned __int16 v33; // ax
  void *v34; // r8
  const char *v35; // [rsp+40h] [rbp-40h] BYREF
  int v36; // [rsp+C0h] [rbp+40h] BYREF

  updated = Equation::UpdateCommonVariables(this, a2, a3, a4, a5, a6);
  if ( (updated & 0x80000000) != 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      return updated;
    v12 = qword_180069010;
    if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
      return updated;
    v36 = 48;
    v13 = &byte_18005BFBF;
LABEL_6:
    v35 = "onecore\\xbox\\gameinput\\feedback\\gipequationmanager\\ConditionEquation.cpp";
    LODWORD(a6) = updated;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v12,
      (unsigned __int8 *)v13,
      v10,
      v11,
      (__int64 **)&v35,
      (__int64)&v36,
      (__int64)&a6);
    return updated;
  }
  v15 = (__m128i)*((unsigned int *)a3 + 7);
  v16 = 0;
  if ( (unsigned __int8)((unsigned int)_mm_cvtsi128_si32(v15) >> 23) == 0xFF
    || COERCE_FLOAT(_mm_cvtsi128_si32(v15) & 0x7FFFFFFF) > 100000.0 )
  {
    if ( *(float *)v15.m128i_i32 <= 0.0 )
      v15 = (__m128i)LODWORD(FLOAT_N100000_0);
    else
      v15 = (__m128i)LODWORD(FLOAT_100000_0);
  }
  if ( *((float *)this + 30) != *(float *)v15.m128i_i32 )
  {
    v17 = Equation::LookupVariableAddress(this, L"POSITIVECOEFFICIENT");
    if ( v17 == 0xFFFF )
      return 2147549183LL;
    updated = ApplicationMemory::UpdateVariable(a2, v17, v18, _mm_cvtsi128_si32(v15));
    if ( (updated & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return updated;
      v12 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        return updated;
      v36 = 57;
      v13 = (char *)&dword_18005BDDC;
      goto LABEL_6;
    }
    *((_DWORD *)this + 30) = v15.m128i_i32[0];
  }
  v19 = (__m128i)*((unsigned int *)a3 + 8);
  if ( (unsigned __int8)((unsigned int)_mm_cvtsi128_si32(v19) >> 23) == 0xFF
    || COERCE_FLOAT(_mm_cvtsi128_si32(v19) & 0x7FFFFFFF) > 100000.0 )
  {
    if ( *(float *)v19.m128i_i32 <= 0.0 )
      v19 = (__m128i)LODWORD(FLOAT_N100000_0);
    else
      v19 = (__m128i)LODWORD(FLOAT_100000_0);
  }
  if ( *((float *)this + 31) != *(float *)v19.m128i_i32 )
  {
    v20 = Equation::LookupVariableAddress(this, L"NEGATIVECOEFFICIENT");
    if ( v20 == 0xFFFF )
      return 2147549183LL;
    updated = ApplicationMemory::UpdateVariable(a2, v20, v21, _mm_cvtsi128_si32(v19));
    if ( (updated & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return updated;
      v12 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        return updated;
      v36 = 66;
      v13 = &byte_18005AD7F;
      goto LABEL_6;
    }
    *((_DWORD *)this + 31) = v19.m128i_i32[0];
  }
  v22 = (__m128i)*((unsigned int *)a3 + 9);
  v23 = _mm_cvtsi128_si32(v22);
  if ( (unsigned __int8)(v23 >> 23) == 0xFF && (v23 & 0x7FFFFF) != 0
    || (v24 = _mm_cvtsi128_si32(v22), !(unsigned __int8)(v24 >> 23)) && (v24 & 0x7FFFFF) != 0 )
  {
    v22 = 0;
  }
  else if ( *(float *)v22.m128i_i32 < 0.0 )
  {
    v22 = 0;
    goto LABEL_41;
  }
  if ( *(float *)v22.m128i_i32 > 1.0 )
    v22 = (__m128i)LODWORD(FLOAT_1_0);
LABEL_41:
  if ( *((float *)this + 32) != *(float *)v22.m128i_i32 )
  {
    v25 = Equation::LookupVariableAddress(this, L"POSITIVESATURATION");
    if ( v25 == 0xFFFF )
      return 2147549183LL;
    updated = ApplicationMemory::UpdateVariable(a2, v25, v26, _mm_cvtsi128_si32(v22));
    if ( (updated & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return updated;
      v12 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        return updated;
      v36 = 75;
      v13 = byte_18005CD71;
      goto LABEL_6;
    }
    *((_DWORD *)this + 32) = v22.m128i_i32[0];
  }
  v27 = (__m128i)*((unsigned int *)a3 + 10);
  v28 = _mm_cvtsi128_si32(v27);
  if ( (unsigned __int8)(v28 >> 23) == 0xFF && (v28 & 0x7FFFFF) != 0 )
    goto LABEL_57;
  v29 = _mm_cvtsi128_si32(v27);
  if ( !(unsigned __int8)(v29 >> 23) && (v29 & 0x7FFFFF) != 0 )
    goto LABEL_57;
  if ( *(float *)v27.m128i_i32 >= 0.0 )
  {
    v16 = (__m128i)*((unsigned int *)a3 + 10);
LABEL_57:
    if ( *(float *)v16.m128i_i32 > 1.0 )
      v16 = (__m128i)LODWORD(FLOAT_1_0);
  }
  if ( *((float *)this + 33) != *(float *)v16.m128i_i32 )
  {
    v30 = Equation::LookupVariableAddress(this, L"NEGATIVESATURATION");
    if ( v30 == 0xFFFF )
      return 2147549183LL;
    updated = ApplicationMemory::UpdateVariable(a2, v30, v31, _mm_cvtsi128_si32(v16));
    if ( (updated & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return updated;
      v12 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        return updated;
      v36 = 84;
      v13 = byte_18005CDEB;
      goto LABEL_6;
    }
    *((_DWORD *)this + 33) = v16.m128i_i32[0];
  }
  v32 = (__m128i)*((unsigned int *)a3 + 11);
  if ( *((float *)this + 34) == *(float *)v32.m128i_i32 )
    return 0;
  v33 = Equation::LookupVariableAddress(this, L"DEADBAND");
  if ( v33 != 0xFFFF )
  {
    updated = ApplicationMemory::UpdateVariable(a2, v33, v34, _mm_cvtsi128_si32(v32));
    if ( (updated & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return updated;
      v12 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        return updated;
      v36 = 93;
      v13 = byte_18005E5EB;
      goto LABEL_6;
    }
    *((_DWORD *)this + 34) = *((_DWORD *)a3 + 11);
    return 0;
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x18001eac4  mov     rax, rsp
0x18001eac7  mov     [rax+8], rbx
0x18001eacb  mov     [rax+10h], rsi
0x18001eacf  push    rbp
0x18001ead0  push    rdi
0x18001ead1  push    r13
0x18001ead3  push    r14
0x18001ead5  push    r15
0x18001ead7  mov     rbp, rsp
0x18001eada  sub     rsp, 80h
0x18001eae1  movss   xmm0, [rbp+arg_20]
0x18001eae6  mov     rsi, r8
0x18001eae9  movaps  xmmword ptr [rax-38h], xmm6
0x18001eaed  mov     r14, rdx
0x18001eaf0  movaps  xmmword ptr [rax-48h], xmm7
0x18001eaf4  mov     rbx, rcx
0x18001eaf7  movaps  xmmword ptr [rax-58h], xmm8
0x18001eafc  mov     rax, [rbp+arg_28]
0x18001eb00  mov     [rsp+80h+var_58], rax; struct Equation::CommonVariables *
0x18001eb05  movss   [rsp+80h+var_60], xmm0; float
0x18001eb0b  call    ?UpdateCommonVariables@Equation@@IEAAJAEAVApplicationMemory@@PEBUGameInputForceFeedbackMagnitude@@MMPEAUCommonVariables@1@@Z; Equation::UpdateCommonVariables(ApplicationMemory &,GameInputForceFeedbackMagnitude const *,float,float,Equation::CommonVariables *)
0x18001eb10  mov     edi, eax
0x18001eb12  test    eax, eax
0x18001eb14  jns     short loc_18001EB82
0x18001eb16  mov     ecx, cs:dword_180069000
0x18001eb1c  cmp     ecx, 2
0x18001eb1f  jbe     short loc_18001EB7B
0x18001eb21  mov     rdx, cs:qword_180069018
0x18001eb28  mov     rcx, cs:qword_180069010
0x18001eb2f  test    cl, 8
0x18001eb32  jz      short loc_18001EB7B
0x18001eb34  mov     rax, rdx
0x18001eb37  and     eax, 8
0x18001eb3a  cmp     rax, rdx
0x18001eb3d  jnz     short loc_18001EB7B
0x18001eb3f  mov     [rbp+arg_10], 30h ; '0'
0x18001eb46  lea     rdx, byte_18005BFBF
0x18001eb4d  lea     rax, aOnecoreXboxGam_38; "onecore\\xbox\\gameinput\\feedback\\gip"...
0x18001eb54  mov     [rbp+var_40], rax
0x18001eb58  lea     rax, [rbp+arg_28]
0x18001eb5c  mov     [rsp+80h+var_50], rax
0x18001eb61  lea     rax, [rbp+arg_10]
0x18001eb65  mov     [rsp+80h+var_58], rax
0x18001eb6a  lea     rax, [rbp+var_40]
0x18001eb6e  mov     qword ptr [rsp+80h+var_60], rax
0x18001eb73  mov     dword ptr [rbp+arg_28], edi
0x18001eb76  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001eb7b  mov     eax, edi
0x18001eb7d  jmp     loc_18001EF64
0x18001eb82  movss   xmm7, dword ptr [rsi+1Ch]
0x18001eb87  xorps   xmm6, xmm6
0x18001eb8a  movss   xmm8, cs:__real@47c35000
0x18001eb93  mov     r15d, 7FFFFFFFh
0x18001eb99  movd    eax, xmm7
0x18001eb9d  shr     eax, 17h
0x18001eba0  cmp     al, 0FFh
0x18001eba2  jz      short loc_18001EBB5
0x18001eba4  movd    eax, xmm7
0x18001eba8  and     eax, r15d
0x18001ebab  movd    xmm0, eax
0x18001ebaf  comiss  xmm8, xmm0
0x18001ebb3  jnb     short loc_18001EBC8
0x18001ebb5  comiss  xmm7, xmm6
0x18001ebb8  jbe     short loc_18001EBC0
0x18001ebba  movaps  xmm7, xmm8
0x18001ebbe  jmp     short loc_18001EBC8
0x18001ebc0  movss   xmm7, cs:__real@c7c35000
0x18001ebc8  movss   xmm0, dword ptr [rbx+78h]
0x18001ebcd  mov     r13d, 0FFFFh
0x18001ebd3  ucomiss xmm0, xmm7
0x18001ebd6  jp      short loc_18001EBDA
0x18001ebd8  jz      short loc_18001EC56
0x18001ebda  lea     rdx, aPositivecoeffi; "POSITIVECOEFFICIENT"
0x18001ebe1  mov     rcx, rbx; this
0x18001ebe4  call    ?LookupVariableAddress@Equation@@IEAAGPEBG@Z; Equation::LookupVariableAddress(ushort const *)
0x18001ebe9  cmp     ax, r13w
0x18001ebed  jz      loc_18001EF5F
0x18001ebf3  movd    r9d, xmm7; unsigned int
0x18001ebf8  movzx   edx, ax; unsigned __int16
0x18001ebfb  mov     rcx, r14; this
0x18001ebfe  call    ?UpdateVariable@ApplicationMemory@@QEAAJGPEAXI@Z; ApplicationMemory::UpdateVariable(ushort,void *,uint)
0x18001ec03  mov     edi, eax
0x18001ec05  test    eax, eax
0x18001ec07  jns     short loc_18001EC51
0x18001ec09  mov     ecx, cs:dword_180069000
0x18001ec0f  cmp     ecx, 2
0x18001ec12  jbe     loc_18001EB7B
0x18001ec18  mov     rdx, cs:qword_180069018
0x18001ec1f  mov     rcx, cs:qword_180069010
0x18001ec26  test    cl, 8
0x18001ec29  jz      loc_18001EB7B
0x18001ec2f  mov     rax, rdx
0x18001ec32  and     eax, 8
0x18001ec35  cmp     rax, rdx
0x18001ec38  jnz     loc_18001EB7B
0x18001ec3e  mov     [rbp+arg_10], 39h ; '9'
0x18001ec45  lea     rdx, dword_18005BDDC
0x18001ec4c  jmp     loc_18001EB4D
0x18001ec51  movss   dword ptr [rbx+78h], xmm7
0x18001ec56  movss   xmm7, dword ptr [rsi+20h]
0x18001ec5b  movd    eax, xmm7
0x18001ec5f  shr     eax, 17h
0x18001ec62  cmp     al, 0FFh
0x18001ec64  jz      short loc_18001EC77
0x18001ec66  movd    eax, xmm7
0x18001ec6a  and     eax, r15d
0x18001ec6d  movd    xmm0, eax
0x18001ec71  comiss  xmm8, xmm0
0x18001ec75  jnb     short loc_18001EC8A
0x18001ec77  comiss  xmm7, xmm6
0x18001ec7a  jbe     short loc_18001EC82
0x18001ec7c  movaps  xmm7, xmm8
0x18001ec80  jmp     short loc_18001EC8A
0x18001ec82  movss   xmm7, cs:__real@c7c35000
0x18001ec8a  movss   xmm0, dword ptr [rbx+7Ch]
0x18001ec8f  ucomiss xmm0, xmm7
0x18001ec92  jp      short loc_18001EC96
0x18001ec94  jz      short loc_18001ED12
0x18001ec96  lea     rdx, aNegativecoeffi; "NEGATIVECOEFFICIENT"
0x18001ec9d  mov     rcx, rbx; this
0x18001eca0  call    ?LookupVariableAddress@Equation@@IEAAGPEBG@Z; Equation::LookupVariableAddress(ushort const *)
0x18001eca5  cmp     ax, r13w
0x18001eca9  jz      loc_18001EF5F
0x18001ecaf  movd    r9d, xmm7; unsigned int
0x18001ecb4  movzx   edx, ax; unsigned __int16
0x18001ecb7  mov     rcx, r14; this
0x18001ecba  call    ?UpdateVariable@ApplicationMemory@@QEAAJGPEAXI@Z; ApplicationMemory::UpdateVariable(ushort,void *,uint)
0x18001ecbf  mov     edi, eax
0x18001ecc1  test    eax, eax
0x18001ecc3  jns     short loc_18001ED0D
0x18001ecc5  mov     ecx, cs:dword_180069000
0x18001eccb  cmp     ecx, 2
0x18001ecce  jbe     loc_18001EB7B
0x18001ecd4  mov     rdx, cs:qword_180069018
0x18001ecdb  mov     rcx, cs:qword_180069010
0x18001ece2  test    cl, 8
0x18001ece5  jz      loc_18001EB7B
0x18001eceb  mov     rax, rdx
0x18001ecee  and     eax, 8
0x18001ecf1  cmp     rax, rdx
0x18001ecf4  jnz     loc_18001EB7B
0x18001ecfa  mov     [rbp+arg_10], 42h ; 'B'
0x18001ed01  lea     rdx, byte_18005AD7F
0x18001ed08  jmp     loc_18001EB4D
0x18001ed0d  movss   dword ptr [rbx+7Ch], xmm7
0x18001ed12  movss   xmm7, dword ptr [rsi+24h]
0x18001ed17  mov     r15d, 7FFFFFh
0x18001ed1d  movss   xmm8, cs:__real@3f800000
0x18001ed26  movd    ecx, xmm7
0x18001ed2a  mov     eax, ecx
0x18001ed2c  shr     eax, 17h
0x18001ed2f  cmp     al, 0FFh
0x18001ed31  jnz     short loc_18001ED38
0x18001ed33  test    r15d, ecx
0x18001ed36  jnz     short loc_18001ED52
0x18001ed38  movd    ecx, xmm7
0x18001ed3c  mov     eax, ecx
0x18001ed3e  shr     eax, 17h
0x18001ed41  test    al, al
0x18001ed43  jnz     loc_18001EDE9
0x18001ed49  test    r15d, ecx
0x18001ed4c  jz      loc_18001EDE9
0x18001ed52  xorps   xmm7, xmm7
0x18001ed55  comiss  xmm7, xmm8
0x18001ed59  jbe     short loc_18001ED5F
0x18001ed5b  movaps  xmm7, xmm8
0x18001ed5f  movss   xmm0, dword ptr [rbx+80h]
0x18001ed67  ucomiss xmm0, xmm7
0x18001ed6a  jp      short loc_18001ED72
0x18001ed6c  jz      loc_18001EE02
0x18001ed72  lea     rdx, aPositivesatura; "POSITIVESATURATION"
0x18001ed79  mov     rcx, rbx; this
0x18001ed7c  call    ?LookupVariableAddress@Equation@@IEAAGPEBG@Z; Equation::LookupVariableAddress(ushort const *)
0x18001ed81  cmp     ax, r13w
0x18001ed85  jz      loc_18001EF5F
0x18001ed8b  movd    r9d, xmm7; unsigned int
0x18001ed90  movzx   edx, ax; unsigned __int16
0x18001ed93  mov     rcx, r14; this
0x18001ed96  call    ?UpdateVariable@ApplicationMemory@@QEAAJGPEAXI@Z; ApplicationMemory::UpdateVariable(ushort,void *,uint)
0x18001ed9b  mov     edi, eax
0x18001ed9d  test    eax, eax
0x18001ed9f  jns     short loc_18001EDFA
0x18001eda1  mov     ecx, cs:dword_180069000
0x18001eda7  cmp     ecx, 2
0x18001edaa  jbe     loc_18001EB7B
0x18001edb0  mov     rdx, cs:qword_180069018
0x18001edb7  mov     rcx, cs:qword_180069010
0x18001edbe  test    cl, 8
0x18001edc1  jz      loc_18001EB7B
0x18001edc7  mov     rax, rdx
0x18001edca  and     eax, 8
0x18001edcd  cmp     rax, rdx
0x18001edd0  jnz     loc_18001EB7B
0x18001edd6  mov     [rbp+arg_10], 4Bh ; 'K'
0x18001eddd  lea     rdx, byte_18005CD71
0x18001ede4  jmp     loc_18001EB4D
0x18001ede9  comiss  xmm6, xmm7
0x18001edec  jbe     loc_18001ED55
0x18001edf2  xorps   xmm7, xmm7
0x18001edf5  jmp     loc_18001ED5F
0x18001edfa  movss   dword ptr [rbx+80h], xmm7
0x18001ee02  movss   xmm0, dword ptr [rsi+28h]
0x18001ee07  movd    ecx, xmm0
0x18001ee0b  mov     eax, ecx
0x18001ee0d  shr     eax, 17h
0x18001ee10  cmp     al, 0FFh
0x18001ee12  jnz     short loc_18001EE19
0x18001ee14  test    r15d, ecx
0x18001ee17  jnz     short loc_18001EE33
0x18001ee19  movd    ecx, xmm0
0x18001ee1d  mov     eax, ecx
0x18001ee1f  shr     eax, 17h
0x18001ee22  test    al, al
0x18001ee24  jnz     short loc_18001EE2B
0x18001ee26  test    r15d, ecx
0x18001ee29  jnz     short loc_18001EE33
0x18001ee2b  comiss  xmm6, xmm0
0x18001ee2e  ja      short loc_18001EE3D
0x18001ee30  movaps  xmm6, xmm0
0x18001ee33  comiss  xmm6, xmm8
0x18001ee37  jbe     short loc_18001EE3D
0x18001ee39  movaps  xmm6, xmm8
0x18001ee3d  movss   xmm0, dword ptr [rbx+84h]
0x18001ee45  ucomiss xmm0, xmm6
0x18001ee48  jp      short loc_18001EE4C
0x18001ee4a  jz      short loc_18001EECB
0x18001ee4c  lea     rdx, aNegativesatura; "NEGATIVESATURATION"
0x18001ee53  mov     rcx, rbx; this
0x18001ee56  call    ?LookupVariableAddress@Equation@@IEAAGPEBG@Z; Equation::LookupVariableAddress(ushort const *)
0x18001ee5b  cmp     ax, r13w
0x18001ee5f  jz      loc_18001EF5F
0x18001ee65  movd    r9d, xmm6; unsigned int
0x18001ee6a  movzx   edx, ax; unsigned __int16
0x18001ee6d  mov     rcx, r14; this
0x18001ee70  call    ?UpdateVariable@ApplicationMemory@@QEAAJGPEAXI@Z; ApplicationMemory::UpdateVariable(ushort,void *,uint)
0x18001ee75  mov     edi, eax
0x18001ee77  test    eax, eax
0x18001ee79  jns     short loc_18001EEC3
0x18001ee7b  mov     ecx, cs:dword_180069000
0x18001ee81  cmp     ecx, 2
0x18001ee84  jbe     loc_18001EB7B
0x18001ee8a  mov     rdx, cs:qword_180069018
0x18001ee91  mov     rcx, cs:qword_180069010
0x18001ee98  test    cl, 8
0x18001ee9b  jz      loc_18001EB7B
0x18001eea1  mov     rax, rdx
0x18001eea4  and     eax, 8
0x18001eea7  cmp     rax, rdx
0x18001eeaa  jnz     loc_18001EB7B
0x18001eeb0  mov     [rbp+arg_10], 54h ; 'T'
0x18001eeb7  lea     rdx, byte_18005CDEB
0x18001eebe  jmp     loc_18001EB4D
0x18001eec3  movss   dword ptr [rbx+84h], xmm6
0x18001eecb  movss   xmm1, dword ptr [rsi+2Ch]
0x18001eed0  movss   xmm0, dword ptr [rbx+88h]
0x18001eed8  ucomiss xmm0, xmm1
0x18001eedb  jp      short loc_18001EEDF
0x18001eedd  jz      short loc_18001EF5B
0x18001eedf  lea     rdx, aDeadband; "DEADBAND"
0x18001eee6  mov     rcx, rbx; this
0x18001eee9  call    ?LookupVariableAddress@Equation@@IEAAGPEBG@Z; Equation::LookupVariableAddress(ushort const *)
0x18001eeee  cmp     ax, r13w
0x18001eef2  jz      short loc_18001EF5F
0x18001eef4  movd    r9d, xmm1; unsigned int
0x18001eef9  movzx   edx, ax; unsigned __int16
0x18001eefc  mov     rcx, r14; this
0x18001eeff  call    ?UpdateVariable@ApplicationMemory@@QEAAJGPEAXI@Z; ApplicationMemory::UpdateVariable(ushort,void *,uint)
0x18001ef04  mov     edi, eax
0x18001ef06  test    eax, eax
0x18001ef08  jns     short loc_18001EF52
0x18001ef0a  mov     ecx, cs:dword_180069000
0x18001ef10  cmp     ecx, 2
0x18001ef13  jbe     loc_18001EB7B
0x18001ef19  mov     rdx, cs:qword_180069018
0x18001ef20  mov     rcx, cs:qword_180069010
0x18001ef27  test    cl, 8
0x18001ef2a  jz      loc_18001EB7B
0x18001ef30  mov     rax, rdx
0x18001ef33  and     eax, 8
0x18001ef36  cmp     rax, rdx
0x18001ef39  jnz     loc_18001EB7B
0x18001ef3f  mov     [rbp+arg_10], 5Dh ; ']'
0x18001ef46  lea     rdx, byte_18005E5EB
0x18001ef4d  jmp     loc_18001EB4D
0x18001ef52  mov     eax, [rsi+2Ch]
0x18001ef55  mov     [rbx+88h], eax
0x18001ef5b  xor     eax, eax
0x18001ef5d  jmp     short loc_18001EF64
0x18001ef5f  mov     eax, 8000FFFFh
0x18001ef64  movaps  xmm6, [rsp+80h+var_10]
0x18001ef69  lea     r11, [rsp+80h+var_s0]
0x18001ef71  mov     rbx, [r11+30h]
0x18001ef75  mov     rsi, [r11+38h]
0x18001ef79  movaps  xmm8, xmmword ptr [r11-30h]
0x18001ef7e  movaps  xmm7, [rsp+80h+var_20]
0x18001ef83  mov     rsp, r11
0x18001ef86  pop     r15
0x18001ef88  pop     r14
0x18001ef8a  pop     r13
0x18001ef8c  pop     rdi
  ... truncated ...
```
