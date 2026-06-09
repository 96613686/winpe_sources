# SpringEquation::UpdateVariables(ApplicationMemory &,GameInputForceFeedbackParams const *,float,float)

- ea: `0x180021d80`
- end: `0x180021f36`
- name: `?UpdateVariables@SpringEquation@@EEAAJAEAVApplicationMemory@@PEBUGameInputForceFeedbackParams@@MM@Z`
- size: `438`
- prototype: `__int64 __usercall@<rax>(SpringEquation *__hidden this@<rcx>, struct ApplicationMemory *@<rdx>, const struct GameInputForceFeedbackParams *@<r8>, float@<xmm3>, float)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180001304`
- `0x180017e70`
- `0x18001eac4`
- `0x180020718`
- `0x180021d80`

## pseudocode

```c
__int64 __fastcall SpringEquation::UpdateVariables(
        SpringEquation *this,
        struct ApplicationMemory *a2,
        const struct GameInputForceFeedbackParams *a3,
        float a4,
        float a5)
{
  unsigned int updated; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rcx
  char *v12; // rdx
  __m128i v14; // xmm0
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  __m128i v17; // xmm6
  unsigned __int16 v18; // ax
  void *v19; // r8
  const char *v20; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v21; // [rsp+80h] [rbp+20h] BYREF
  int v22; // [rsp+90h] [rbp+30h] BYREF

  updated = ConditionEquation::UpdateConditionVariables(
              this,
              a2,
              (const struct GameInputForceFeedbackParams *)((char *)a3 + 8),
              a4,
              a5,
              (SpringEquation *)((char *)this + 112));
  if ( (updated & 0x80000000) != 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      return updated;
    v11 = qword_180069010;
    if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
      return updated;
    v22 = 23;
    v12 = byte_18005E251;
LABEL_6:
    v20 = "onecore\\xbox\\gameinput\\feedback\\gipequationmanager\\SpringEquation.cpp";
    v21 = updated;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v11,
      (unsigned __int8 *)v12,
      v9,
      v10,
      (__int64 **)&v20,
      (__int64)&v22,
      (__int64)&v21);
    return updated;
  }
  v14 = (__m128i)*((unsigned int *)a3 + 14);
  v15 = _mm_cvtsi128_si32(v14);
  if ( (unsigned __int8)(v15 >> 23) == 0xFF && (v15 & 0x7FFFFF) != 0
    || (v16 = _mm_cvtsi128_si32(v14), !(unsigned __int8)(v16 >> 23)) && (v16 & 0x7FFFFF) != 0 )
  {
    v14 = 0;
  }
  else
  {
    v17 = (__m128i)LODWORD(FLOAT_N1_0);
    if ( *(float *)v14.m128i_i32 < -1.0 )
      goto LABEL_16;
  }
  v17 = (__m128i)LODWORD(FLOAT_1_0);
  if ( *(float *)v14.m128i_i32 <= 1.0 )
    v17 = v14;
LABEL_16:
  if ( *((float *)this + 36) != *(float *)v17.m128i_i32 )
  {
    v18 = Equation::LookupVariableAddress(this, L"CENTEROFFSET");
    if ( v18 == 0xFFFF )
      return 2147549183LL;
    updated = ApplicationMemory::UpdateVariable(a2, v18, v19, _mm_cvtsi128_si32(v17));
    if ( (updated & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return updated;
      v11 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        return updated;
      v22 = 30;
      v12 = byte_18005D025;
      goto LABEL_6;
    }
    *((_DWORD *)this + 36) = v17.m128i_i32[0];
  }
  return 0;
}

```

## disassembly

```asm
0x180021d80  mov     [rsp-18h+arg_8], rbx
0x180021d85  mov     [rsp-18h+arg_18], rsi
0x180021d8a  push    rbp
0x180021d8b  push    rdi
0x180021d8c  push    r14
0x180021d8e  mov     rbp, rsp
0x180021d91  sub     rsp, 60h
0x180021d95  movss   xmm0, [rbp+arg_20]
0x180021d9a  lea     rax, [rcx+70h]
0x180021d9e  mov     rsi, r8
0x180021da1  mov     [rsp+60h+var_38], rax; struct ConditionEquation::ConditionVariables *
0x180021da6  add     r8, 8; struct GameInputForceFeedbackConditionParams *
0x180021daa  movss   [rsp+60h+var_40], xmm0; float
0x180021db0  movaps  [rsp+60h+var_10], xmm6
0x180021db5  mov     r14, rdx
0x180021db8  mov     rdi, rcx
0x180021dbb  call    ?UpdateConditionVariables@ConditionEquation@@IEAAJAEAVApplicationMemory@@PEBUGameInputForceFeedbackConditionParams@@MMPEAUConditionVariables@1@@Z; ConditionEquation::UpdateConditionVariables(ApplicationMemory &,GameInputForceFeedbackConditionParams const *,float,float,ConditionEquation::ConditionVariables *)
0x180021dc0  mov     ebx, eax
0x180021dc2  test    eax, eax
0x180021dc4  jns     short loc_180021E32
0x180021dc6  mov     ecx, cs:dword_180069000
0x180021dcc  cmp     ecx, 2
0x180021dcf  jbe     short loc_180021E2B
0x180021dd1  mov     rdx, cs:qword_180069018
0x180021dd8  mov     rcx, cs:qword_180069010
0x180021ddf  test    cl, 8
0x180021de2  jz      short loc_180021E2B
0x180021de4  mov     rax, rdx
0x180021de7  and     eax, 8
0x180021dea  cmp     rax, rdx
0x180021ded  jnz     short loc_180021E2B
0x180021def  mov     [rbp+arg_10], 17h
0x180021df6  lea     rdx, byte_18005E251
0x180021dfd  lea     rax, aOnecoreXboxGam_22; "onecore\\xbox\\gameinput\\feedback\\gip"...
0x180021e04  mov     [rbp+var_20], rax
0x180021e08  lea     rax, [rbp+arg_0]
0x180021e0c  mov     [rsp+60h+var_30], rax
0x180021e11  lea     rax, [rbp+arg_10]
0x180021e15  mov     [rsp+60h+var_38], rax
0x180021e1a  lea     rax, [rbp+var_20]
0x180021e1e  mov     qword ptr [rsp+60h+var_40], rax
0x180021e23  mov     [rbp+arg_0], ebx
0x180021e26  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180021e2b  mov     eax, ebx
0x180021e2d  jmp     loc_180021F1B
0x180021e32  movss   xmm0, dword ptr [rsi+38h]
0x180021e37  mov     edx, 7FFFFFh
0x180021e3c  movd    ecx, xmm0
0x180021e40  mov     eax, ecx
0x180021e42  shr     eax, 17h
0x180021e45  cmp     al, 0FFh
0x180021e47  jnz     short loc_180021E4D
0x180021e49  test    edx, ecx
0x180021e4b  jnz     short loc_180021E5E
0x180021e4d  movd    ecx, xmm0
0x180021e51  mov     eax, ecx
0x180021e53  shr     eax, 17h
0x180021e56  test    al, al
0x180021e58  jnz     short loc_180021E63
0x180021e5a  test    edx, ecx
0x180021e5c  jz      short loc_180021E63
0x180021e5e  xorps   xmm0, xmm0
0x180021e61  jmp     short loc_180021E70
0x180021e63  movss   xmm6, cs:__real@bf800000
0x180021e6b  comiss  xmm6, xmm0
0x180021e6e  ja      short loc_180021E80
0x180021e70  movss   xmm6, cs:__real@3f800000
0x180021e78  comiss  xmm0, xmm6
0x180021e7b  ja      short loc_180021E80
0x180021e7d  movaps  xmm6, xmm0
0x180021e80  movss   xmm0, dword ptr [rdi+90h]
0x180021e88  ucomiss xmm0, xmm6
0x180021e8b  jp      short loc_180021E93
0x180021e8d  jz      loc_180021F19
0x180021e93  lea     rdx, aCenteroffset; "CENTEROFFSET"
0x180021e9a  mov     rcx, rdi; this
0x180021e9d  call    ?LookupVariableAddress@Equation@@IEAAGPEBG@Z; Equation::LookupVariableAddress(ushort const *)
0x180021ea2  mov     ecx, 0FFFFh
0x180021ea7  cmp     ax, cx
0x180021eaa  jnz     short loc_180021EB3
0x180021eac  mov     eax, 8000FFFFh
0x180021eb1  jmp     short loc_180021F1B
0x180021eb3  movd    r9d, xmm6; unsigned int
0x180021eb8  movzx   edx, ax; unsigned __int16
0x180021ebb  mov     rcx, r14; this
0x180021ebe  call    ?UpdateVariable@ApplicationMemory@@QEAAJGPEAXI@Z; ApplicationMemory::UpdateVariable(ushort,void *,uint)
0x180021ec3  mov     ebx, eax
0x180021ec5  test    eax, eax
0x180021ec7  jns     short loc_180021F11
0x180021ec9  mov     ecx, cs:dword_180069000
0x180021ecf  cmp     ecx, 2
0x180021ed2  jbe     loc_180021E2B
0x180021ed8  mov     rdx, cs:qword_180069018
0x180021edf  mov     rcx, cs:qword_180069010
0x180021ee6  test    cl, 8
0x180021ee9  jz      loc_180021E2B
0x180021eef  mov     rax, rdx
0x180021ef2  and     eax, 8
0x180021ef5  cmp     rax, rdx
0x180021ef8  jnz     loc_180021E2B
0x180021efe  mov     [rbp+arg_10], 1Eh
0x180021f05  lea     rdx, byte_18005D025
0x180021f0c  jmp     loc_180021DFD
0x180021f11  movss   dword ptr [rdi+90h], xmm6
0x180021f19  xor     eax, eax
0x180021f1b  movaps  xmm6, [rsp+60h+var_10]
0x180021f20  lea     r11, [rsp+60h+var_s0]
0x180021f25  mov     rbx, [r11+28h]
0x180021f29  mov     rsi, [r11+38h]
0x180021f2d  mov     rsp, r11
0x180021f30  pop     r14
0x180021f32  pop     rdi
0x180021f33  pop     rbp
0x180021f34  retn
```
