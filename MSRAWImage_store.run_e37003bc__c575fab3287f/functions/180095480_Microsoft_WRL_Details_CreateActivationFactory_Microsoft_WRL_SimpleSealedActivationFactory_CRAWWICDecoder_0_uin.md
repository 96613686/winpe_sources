# Microsoft::WRL::Details::CreateActivationFactory<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180095480`
- end: `0x180095528`
- name: `??$CreateActivationFactory@V?$SimpleSealedActivationFactory@VCRAWWICDecoder@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180095480`
- `0x180095788`
- `0x180095fd8`
- `0x1800969e0`
- `0x180096d4c`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateActivationFactory<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>>(
        _BYTE *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int CanCastTo; // edi
  __int64 result; // rax
  volatile int *v10; // rdx
  __int64 v11; // r10
  _QWORD v12[3]; // [rsp+20h] [rbp-18h] BYREF

  v12[0] = 0;
  CanCastTo = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>,Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>,>(v12);
  if ( CanCastTo < 0 )
  {
    if ( !v12[0] )
      return (unsigned int)CanCastTo;
LABEL_3:
    Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release();
    return (unsigned int)CanCastTo;
  }
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(
                v12[0],
                a3,
                a4);
  if ( CanCastTo < 0 )
  {
    if ( !v11 )
      return (unsigned int)CanCastTo;
    goto LABEL_3;
  }
  if ( (*a1 & 4) == 0 )
    Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(v11 + 12), v10);
  *(_DWORD *)(v11 + 32) = *(_DWORD *)a1;
  result = 0;
  *(_QWORD *)(v11 + 24) = a2;
  return result;
}

```

## disassembly

```asm
0x180095480  mov     rax, rsp
0x180095483  mov     [rax+8], rbx
0x180095487  mov     [rax+10h], rbp
0x18009548b  mov     [rax+18h], rsi
0x18009548f  mov     [rax+20h], rdi
0x180095493  push    r14
0x180095495  sub     rsp, 30h
0x180095499  mov     rbx, rcx
0x18009549c  mov     qword ptr [rax-18h], 0
0x1800954a4  lea     rcx, [rax-18h]
0x1800954a8  mov     rbp, r9
0x1800954ab  mov     r14, r8
0x1800954ae  mov     rsi, rdx
0x1800954b1  call    ??$MakeAndInitialize@V?$SimpleSealedActivationFactory@VCRAWWICDecoder@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleSealedActivationFactory@VCRAWWICDecoder@@$0A@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>,Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0>,>(Microsoft::WRL::SimpleSealedActivationFactory<CRAWWICDecoder,0> * *)
0x1800954b6  mov     edi, eax
0x1800954b8  test    eax, eax
0x1800954ba  jns     short loc_1800954CF
0x1800954bc  mov     rcx, [rsp+38h+var_18]
0x1800954c1  test    rcx, rcx
0x1800954c4  jz      short loc_1800954CB
0x1800954c6  call    ?Release@?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x1800954cb  mov     eax, edi
0x1800954cd  jmp     short loc_18009550C
0x1800954cf  mov     r10, [rsp+38h+var_18]
0x1800954d4  mov     r8, rbp
0x1800954d7  mov     rcx, r10
0x1800954da  mov     rdx, r14
0x1800954dd  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@VNil@Details@23@V5623@V5623@V5623@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(_GUID const &,void * *,bool *)
0x1800954e2  mov     edi, eax
0x1800954e4  test    eax, eax
0x1800954e6  jns     short loc_1800954F2
0x1800954e8  test    r10, r10
0x1800954eb  jz      short loc_1800954CB
0x1800954ed  mov     rcx, r10
0x1800954f0  jmp     short loc_1800954C6
0x1800954f2  test    byte ptr [rbx], 4
0x1800954f5  jnz     short loc_180095500
0x1800954f7  lea     rcx, [r10+0Ch]; this
0x1800954fb  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x180095500  mov     eax, [rbx]
0x180095502  mov     [r10+20h], eax
0x180095506  xor     eax, eax
0x180095508  mov     [r10+18h], rsi
0x18009550c  mov     rbx, [rsp+38h+arg_0]
0x180095511  mov     rbp, [rsp+38h+arg_8]
0x180095516  mov     rsi, [rsp+38h+arg_10]
0x18009551b  mov     rdi, [rsp+38h+arg_18]
0x180095520  add     rsp, 30h
0x180095524  pop     r14
0x180095526  retn
```
