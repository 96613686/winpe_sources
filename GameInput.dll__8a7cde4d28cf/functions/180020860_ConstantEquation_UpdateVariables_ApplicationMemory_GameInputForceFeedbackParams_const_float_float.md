# ConstantEquation::UpdateVariables(ApplicationMemory &,GameInputForceFeedbackParams const *,float,float)

- ea: `0x180020860`
- end: `0x180020974`
- name: `?UpdateVariables@ConstantEquation@@EEAAJAEAVApplicationMemory@@PEBUGameInputForceFeedbackParams@@MM@Z`
- size: `276`
- prototype: `__int64 __usercall@<rax>(ConstantEquation *__hidden this@<rcx>, struct ApplicationMemory *@<rdx>, const struct GameInputForceFeedbackParams *@<r8>, float@<xmm3>, float)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001304`
- `0x18001e93c`
- `0x18001fa3c`
- `0x180020860`

## pseudocode

```c
__int64 __fastcall ConstantEquation::UpdateVariables(
        ConstantEquation *this,
        struct ApplicationMemory *a2,
        const struct GameInputForceFeedbackParams *a3,
        float a4,
        unsigned int a5)
{
  char *v5; // r15
  unsigned int updated; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rcx
  unsigned __int8 *v13; // rdx
  const char *v15; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v16; // [rsp+80h] [rbp+30h] BYREF
  int v17; // [rsp+90h] [rbp+40h] BYREF

  v5 = (char *)this + 112;
  updated = Equation::UpdateCommonVariables(
              this,
              a2,
              (const struct GameInputForceFeedbackParams *)((char *)a3 + 56),
              a4,
              a5,
              (ConstantEquation *)((char *)this + 112));
  if ( (updated & 0x80000000) != 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      return updated;
    v12 = qword_180069010;
    if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
      return updated;
    v17 = 33;
    v13 = (unsigned __int8 *)&word_18005E28E;
LABEL_6:
    v15 = "onecore\\xbox\\gameinput\\feedback\\gipequationmanager\\ConstantEquation.cpp";
    v16 = updated;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v12,
      v13,
      v10,
      v11,
      (__int64 **)&v15,
      (__int64)&v17,
      (__int64)&v16);
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
    v17 = 34;
    v13 = (unsigned __int8 *)&dword_18005E7E4;
    goto LABEL_6;
  }
  return 0;
}

```

## disassembly

```asm
0x180020860  mov     [rsp-28h+arg_8], rbx
0x180020865  push    rbp
0x180020866  push    rsi
0x180020867  push    rdi
0x180020868  push    r14
0x18002086a  push    r15
0x18002086c  mov     rbp, rsp
0x18002086f  sub     rsp, 50h
0x180020873  movss   xmm0, [rbp+arg_20]
0x180020878  lea     r15, [rcx+70h]
0x18002087c  mov     rsi, r8
0x18002087f  mov     [rsp+50h+var_28], r15; struct Equation::CommonVariables *
0x180020884  add     r8, 38h ; '8'; struct GameInputForceFeedbackMagnitude *
0x180020888  movss   [rsp+50h+var_30], xmm0; float
0x18002088e  mov     r14, rdx
0x180020891  mov     rdi, rcx
0x180020894  call    ?UpdateCommonVariables@Equation@@IEAAJAEAVApplicationMemory@@PEBUGameInputForceFeedbackMagnitude@@MMPEAUCommonVariables@1@@Z; Equation::UpdateCommonVariables(ApplicationMemory &,GameInputForceFeedbackMagnitude const *,float,float,Equation::CommonVariables *)
0x180020899  mov     ebx, eax
0x18002089b  test    eax, eax
0x18002089d  jns     short loc_180020908
0x18002089f  mov     ecx, cs:dword_180069000
0x1800208a5  cmp     ecx, 2
0x1800208a8  jbe     short loc_180020904
0x1800208aa  mov     rdx, cs:qword_180069018
0x1800208b1  mov     rcx, cs:qword_180069010
0x1800208b8  test    cl, 8
0x1800208bb  jz      short loc_180020904
0x1800208bd  mov     rax, rdx
0x1800208c0  and     eax, 8
0x1800208c3  cmp     rax, rdx
0x1800208c6  jnz     short loc_180020904
0x1800208c8  mov     [rbp+arg_10], 21h ; '!'
0x1800208cf  lea     rdx, word_18005E28E
0x1800208d6  lea     rax, aOnecoreXboxGam_44; "onecore\\xbox\\gameinput\\feedback\\gip"...
0x1800208dd  mov     [rbp+var_10], rax
0x1800208e1  lea     rax, [rbp+arg_0]
0x1800208e5  mov     [rsp+50h+var_20], rax
0x1800208ea  lea     rax, [rbp+arg_10]
0x1800208ee  mov     [rsp+50h+var_28], rax
0x1800208f3  lea     rax, [rbp+var_10]
0x1800208f7  mov     qword ptr [rsp+50h+var_30], rax
0x1800208fc  mov     [rbp+arg_0], ebx
0x1800208ff  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180020904  mov     eax, ebx
0x180020906  jmp     short loc_18002095F
0x180020908  lea     r9, [r15+8]; struct Equation::EnvelopeVariables *
0x18002090c  mov     rdx, r14; struct ApplicationMemory *
0x18002090f  lea     r8, [rsi+8]; struct GameInputForceFeedbackEnvelope *
0x180020913  mov     rcx, rdi; this
0x180020916  call    ?UpdateEnvelopeVariables@Equation@@IEAAJAEAVApplicationMemory@@PEBUGameInputForceFeedbackEnvelope@@PEAUEnvelopeVariables@1@@Z; Equation::UpdateEnvelopeVariables(ApplicationMemory &,GameInputForceFeedbackEnvelope const *,Equation::EnvelopeVariables *)
0x18002091b  mov     ebx, eax
0x18002091d  test    eax, eax
0x18002091f  jns     short loc_18002095D
0x180020921  mov     ecx, cs:dword_180069000
0x180020927  cmp     ecx, 2
0x18002092a  jbe     short loc_180020904
0x18002092c  mov     rdx, cs:qword_180069018
0x180020933  mov     rcx, cs:qword_180069010
0x18002093a  test    cl, 8
0x18002093d  jz      short loc_180020904
0x18002093f  mov     rax, rdx
0x180020942  and     eax, 8
0x180020945  cmp     rax, rdx
0x180020948  jnz     short loc_180020904
0x18002094a  mov     [rbp+arg_10], 22h ; '"'
0x180020951  lea     rdx, dword_18005E7E4
0x180020958  jmp     loc_1800208D6
0x18002095d  xor     eax, eax
0x18002095f  mov     rbx, [rsp+50h+arg_8]
0x180020967  add     rsp, 50h
0x18002096b  pop     r15
0x18002096d  pop     r14
0x18002096f  pop     rdi
0x180020970  pop     rsi
0x180020971  pop     rbp
0x180020972  retn
```
