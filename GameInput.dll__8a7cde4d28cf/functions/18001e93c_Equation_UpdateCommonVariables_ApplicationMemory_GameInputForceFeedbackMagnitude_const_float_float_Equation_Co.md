# Equation::UpdateCommonVariables(ApplicationMemory &,GameInputForceFeedbackMagnitude const *,float,float,Equation::CommonVariables *)

- ea: `0x18001e93c`
- end: `0x18001eabd`
- name: `?UpdateCommonVariables@Equation@@IEAAJAEAVApplicationMemory@@PEBUGameInputForceFeedbackMagnitude@@MMPEAUCommonVariables@1@@Z`
- size: `385`
- prototype: `__int64 __usercall@<rax>(Equation *__hidden this@<rcx>, struct ApplicationMemory *@<rdx>, const struct GameInputForceFeedbackMagnitude *@<r8>, float@<xmm3>, float, struct Equation::CommonVariables *)`
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001eac4`
- `0x180020860`
- `0x180021684`
- `0x180021a30`

## callees

- `0x180001304`
- `0x180017e70`
- `0x18001e93c`
- `0x180020718`
- `0x18004d010`

## pseudocode

```c
__int64 __fastcall Equation::UpdateCommonVariables(
        Equation *this,
        struct ApplicationMemory *a2,
        const struct GameInputForceFeedbackMagnitude *a3,
        float a4,
        unsigned int a5,
        struct Equation::CommonVariables *a6)
{
  __m128i v6; // xmm0
  struct Equation::CommonVariables *v9; // rdi
  unsigned __int16 v10; // ax
  void *v11; // r8
  unsigned int updated; // ebx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rcx
  unsigned __int8 *v16; // rdx
  __m128i v18; // xmm6
  unsigned __int16 v19; // ax
  void *v20; // r8
  const char *v21; // [rsp+40h] [rbp-28h] BYREF
  int v22; // [rsp+A0h] [rbp+38h] BYREF

  *(double *)v6.m128i_i64 = (*(double (__fastcall **)(Equation *, const struct GameInputForceFeedbackMagnitude *))(*(_QWORD *)this + 40LL))(
                              this,
                              a3);
  v9 = a6;
  if ( *(float *)a6 != *(float *)v6.m128i_i32 )
  {
    v10 = Equation::LookupVariableAddress(this, L"GAIN");
    if ( v10 == 0xFFFF )
      return 2147549183LL;
    updated = ApplicationMemory::UpdateVariable(a2, v10, v11, _mm_cvtsi128_si32(v6));
    if ( (updated & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return updated;
      v15 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        return updated;
      v22 = 241;
      v16 = (unsigned __int8 *)&word_18005BE56;
LABEL_8:
      v21 = "onecore\\xbox\\gameinput\\feedback\\gipequationmanager\\Equation.cpp";
      LODWORD(a6) = updated;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v15,
        v16,
        v13,
        v14,
        (__int64 **)&v21,
        (__int64)&v22,
        (__int64)&a6);
      return updated;
    }
    *(_DWORD *)v9 = v6.m128i_i32[0];
  }
  v18 = (__m128i)a5;
  if ( *((float *)v9 + 1) == *(float *)&a5 )
    return 0;
  v19 = Equation::LookupVariableAddress(this, L"DEVICEGAIN");
  if ( v19 != 0xFFFF )
  {
    updated = ApplicationMemory::UpdateVariable(a2, v19, v20, _mm_cvtsi128_si32(v18));
    if ( (updated & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return updated;
      v15 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        return updated;
      v22 = 250;
      v16 = (unsigned __int8 *)byte_18005A979;
      goto LABEL_8;
    }
    *((_DWORD *)v9 + 1) = v18.m128i_i32[0];
    return 0;
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x18001e93c  push    rbp
0x18001e93e  push    rbx
0x18001e93f  push    rsi
0x18001e940  push    rdi
0x18001e941  push    r14
0x18001e943  push    r15
0x18001e945  mov     rbp, rsp
0x18001e948  sub     rsp, 68h
0x18001e94c  mov     rax, [rcx]
0x18001e94f  mov     r14, rdx
0x18001e952  movaps  xmm2, xmm3
0x18001e955  movaps  [rsp+68h+var_18], xmm6
0x18001e95a  mov     rdx, r8
0x18001e95d  mov     rsi, rcx
0x18001e960  mov     rax, [rax+28h]
0x18001e964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e969  mov     rdi, [rbp+arg_28]
0x18001e96d  movaps  xmm6, xmm0
0x18001e970  mov     r15d, 0FFFFh
0x18001e976  movss   xmm1, dword ptr [rdi]
0x18001e97a  ucomiss xmm1, xmm6
0x18001e97d  jp      short loc_18001E985
0x18001e97f  jz      loc_18001EA24
0x18001e985  lea     rdx, aGain; "GAIN"
0x18001e98c  mov     rcx, rsi; this
0x18001e98f  call    ?LookupVariableAddress@Equation@@IEAAGPEBG@Z; Equation::LookupVariableAddress(ushort const *)
0x18001e994  cmp     ax, r15w
0x18001e998  jz      loc_18001EAA5
0x18001e99e  movd    r9d, xmm6; unsigned int
0x18001e9a3  movzx   edx, ax; unsigned __int16
0x18001e9a6  mov     rcx, r14; this
0x18001e9a9  call    ?UpdateVariable@ApplicationMemory@@QEAAJGPEAXI@Z; ApplicationMemory::UpdateVariable(ushort,void *,uint)
0x18001e9ae  mov     ebx, eax
0x18001e9b0  test    eax, eax
0x18001e9b2  jns     short loc_18001EA20
0x18001e9b4  mov     ecx, cs:dword_180069000
0x18001e9ba  cmp     ecx, 2
0x18001e9bd  jbe     short loc_18001EA19
0x18001e9bf  mov     rdx, cs:qword_180069018
0x18001e9c6  mov     rcx, cs:qword_180069010
0x18001e9cd  test    cl, 8
0x18001e9d0  jz      short loc_18001EA19
0x18001e9d2  mov     rax, rdx
0x18001e9d5  and     eax, 8
0x18001e9d8  cmp     rax, rdx
0x18001e9db  jnz     short loc_18001EA19
0x18001e9dd  mov     [rbp+arg_0], 0F1h
0x18001e9e4  lea     rdx, word_18005BE56
0x18001e9eb  lea     rax, aOnecoreXboxGam_14; "onecore\\xbox\\gameinput\\feedback\\gip"...
0x18001e9f2  mov     [rbp+var_28], rax
0x18001e9f6  lea     rax, [rbp+arg_28]
0x18001e9fa  mov     [rsp+68h+var_38], rax
0x18001e9ff  lea     rax, [rbp+arg_0]
0x18001ea03  mov     [rsp+68h+var_40], rax
0x18001ea08  lea     rax, [rbp+var_28]
0x18001ea0c  mov     [rsp+68h+var_48], rax
0x18001ea11  mov     dword ptr [rbp+arg_28], ebx
0x18001ea14  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001ea19  mov     eax, ebx
0x18001ea1b  jmp     loc_18001EAAA
0x18001ea20  movss   dword ptr [rdi], xmm6
0x18001ea24  movss   xmm0, dword ptr [rdi+4]
0x18001ea29  movss   xmm6, [rbp+arg_20]
0x18001ea2e  ucomiss xmm0, xmm6
0x18001ea31  jp      short loc_18001EA35
0x18001ea33  jz      short loc_18001EAA1
0x18001ea35  lea     rdx, aDevicegain; "DEVICEGAIN"
0x18001ea3c  mov     rcx, rsi; this
0x18001ea3f  call    ?LookupVariableAddress@Equation@@IEAAGPEBG@Z; Equation::LookupVariableAddress(ushort const *)
0x18001ea44  cmp     ax, r15w
0x18001ea48  jz      short loc_18001EAA5
0x18001ea4a  movd    r9d, xmm6; unsigned int
0x18001ea4f  movzx   edx, ax; unsigned __int16
0x18001ea52  mov     rcx, r14; this
0x18001ea55  call    ?UpdateVariable@ApplicationMemory@@QEAAJGPEAXI@Z; ApplicationMemory::UpdateVariable(ushort,void *,uint)
0x18001ea5a  mov     ebx, eax
0x18001ea5c  test    eax, eax
0x18001ea5e  jns     short loc_18001EA9C
0x18001ea60  mov     ecx, cs:dword_180069000
0x18001ea66  cmp     ecx, 2
0x18001ea69  jbe     short loc_18001EA19
0x18001ea6b  mov     rdx, cs:qword_180069018
0x18001ea72  mov     rcx, cs:qword_180069010
0x18001ea79  test    cl, 8
0x18001ea7c  jz      short loc_18001EA19
0x18001ea7e  mov     rax, rdx
0x18001ea81  and     eax, 8
0x18001ea84  cmp     rax, rdx
0x18001ea87  jnz     short loc_18001EA19
0x18001ea89  mov     [rbp+arg_0], 0FAh
0x18001ea90  lea     rdx, byte_18005A979
0x18001ea97  jmp     loc_18001E9EB
0x18001ea9c  movss   dword ptr [rdi+4], xmm6
0x18001eaa1  xor     eax, eax
0x18001eaa3  jmp     short loc_18001EAAA
0x18001eaa5  mov     eax, 8000FFFFh
0x18001eaaa  movaps  xmm6, [rsp+68h+var_18]
0x18001eaaf  add     rsp, 68h
0x18001eab3  pop     r15
0x18001eab5  pop     r14
0x18001eab7  pop     rdi
0x18001eab8  pop     rsi
0x18001eab9  pop     rbx
0x18001eaba  pop     rbp
0x18001eabb  retn
```
