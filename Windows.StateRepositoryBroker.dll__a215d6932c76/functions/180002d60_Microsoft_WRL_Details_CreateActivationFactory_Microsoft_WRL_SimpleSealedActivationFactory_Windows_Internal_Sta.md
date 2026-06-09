# Microsoft::WRL::Details::CreateActivationFactory<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180002d60`
- end: `0x180002deb`
- name: `??$CreateActivationFactory@V?$SimpleSealedActivationFactory@VAppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `139`
- prototype: `__int64 __fastcall(_BYTE *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002d60`
- `0x180003244`
- `0x1800045a8`
- `0x180005c50`
- `0x180006270`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateActivationFactory<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>>(
        _BYTE *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int CanCastTo; // edi
  __int64 result; // rax
  volatile int *v10; // rdx
  __int64 v11; // r10
  _QWORD v12[7]; // [rsp+20h] [rbp-38h] BYREF

  v12[0] = 0;
  CanCastTo = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>,Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>,>(v12);
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
0x180002d60  push    rbx
0x180002d62  push    rbp
0x180002d63  push    rsi
0x180002d64  push    rdi
0x180002d65  push    r14
0x180002d67  sub     rsp, 30h
0x180002d6b  mov     rbx, rcx
0x180002d6e  mov     [rsp+58h+var_38], 0
0x180002d77  lea     rcx, [rsp+58h+var_38]
0x180002d7c  mov     rbp, r9
0x180002d7f  mov     r14, r8
0x180002d82  mov     rsi, rdx
0x180002d85  call    ??$MakeAndInitialize@V?$SimpleSealedActivationFactory@VAppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleSealedActivationFactory@VAppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@$0A@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>,Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>,>(Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0> * *)
0x180002d8a  mov     edi, eax
0x180002d8c  test    eax, eax
0x180002d8e  jns     short loc_180002DA3
0x180002d90  mov     rcx, [rsp+58h+var_38]
0x180002d95  test    rcx, rcx
0x180002d98  jz      short loc_180002D9F
0x180002d9a  call    ?Release@?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180002d9f  mov     eax, edi
0x180002da1  jmp     short loc_180002DE0
0x180002da3  mov     r10, [rsp+58h+var_38]
0x180002da8  mov     r8, rbp
0x180002dab  mov     rcx, r10
0x180002dae  mov     rdx, r14
0x180002db1  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@VNil@Details@23@V5623@V5623@V5623@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(_GUID const &,void * *,bool *)
0x180002db6  mov     edi, eax
0x180002db8  test    eax, eax
0x180002dba  jns     short loc_180002DC6
0x180002dbc  test    r10, r10
0x180002dbf  jz      short loc_180002D9F
0x180002dc1  mov     rcx, r10
0x180002dc4  jmp     short loc_180002D9A
0x180002dc6  test    byte ptr [rbx], 4
0x180002dc9  jnz     short loc_180002DD4
0x180002dcb  lea     rcx, [r10+0Ch]; this
0x180002dcf  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x180002dd4  mov     eax, [rbx]
0x180002dd6  mov     [r10+20h], eax
0x180002dda  xor     eax, eax
0x180002ddc  mov     [r10+18h], rsi
0x180002de0  add     rsp, 30h
0x180002de4  pop     r14
0x180002de6  pop     rdi
0x180002de7  pop     rsi
0x180002de8  pop     rbp
0x180002de9  pop     rbx
0x180002dea  retn
```
