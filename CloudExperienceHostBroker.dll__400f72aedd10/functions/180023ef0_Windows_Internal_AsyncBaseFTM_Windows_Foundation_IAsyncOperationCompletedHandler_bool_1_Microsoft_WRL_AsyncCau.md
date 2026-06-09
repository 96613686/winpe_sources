# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostBroker::Account::VerifyLocalAccountCredsOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180023ef0`
- end: `0x18002408b`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?VerifyLocalAccountCredsOperationName@Account@CloudExperienceHostBroker@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800241f0`

## callees

- `0x180002a3c`
- `0x1800034d0`
- `0x1800035a0`
- `0x1800054b0`
- `0x180005a30`
- `0x180006388`
- `0x180006d30`
- `0x180007858`
- `0x18000793c`
- `0x18000815c`
- `0x180009388`
- `0x18001ff70`
- `0x180023ef0`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180024004`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180024004`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180023fd5`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180023fd5`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostBroker::Account::VerifyLocalAccountCredsOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  unsigned int v2; // edi
  unsigned int v3; // edx
  __int64 v4; // rcx
  __int64 v5; // rdx
  bool v6; // dl
  IUnknown *v7; // rdi
  unsigned int v8; // eax
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64); // [rsp+30h] [rbp-20h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-18h] BYREF
  HRESULT v12; // [rsp+40h] [rbp-10h]
  unsigned int v13; // [rsp+70h] [rbp+20h] BYREF
  struct IUnknown *v14; // [rsp+78h] [rbp+28h] BYREF
  struct IRpcOptions *v15; // [rsp+80h] [rbp+30h] BYREF
  LPUNKNOWN pUnk; // [rsp+88h] [rbp+38h] BYREF

  v2 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostBroker::Account::UpdateSecurityQuestionsAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    a1,
    1);
  if ( *(int *)(v4 + 136) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 16), v3) + 1 == v3 )
  {
    v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))v4;
    Microsoft::WRL::ComPtr<IAsyncInfo>::InternalAddRef(&v10);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostBroker::LocalNgc::CreateLocalPinAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<bool>>(&v10, (__int64)&pUnk) >= 0 )
    {
      v13 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v13, *(_DWORD *)(a1 + 56), -2);
      v14 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::CopyLocal(
                  a1 + 120,
                  v5,
                  &v14) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<bool> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
        v15 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
        RpcOptionsHelper::GetRpcOptions(v14, v6, &v15);
        ppstm = 0;
        v12 = 0;
        if ( v15 && v14 )
        {
          v7 = pUnk;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppstm);
          v12 = CreateStreamOnHGlobal(0, 1, &ppstm);
          if ( v12 >= 0 )
            v12 = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v7, 0, 0, 1u);
        }
        else
        {
          v12 = -2147467262;
        }
        v8 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v14->lpVtbl[1].QueryInterface)(
               v14,
               pUnk,
               v13);
        v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(
               v8,
               v14,
               *(_QWORD *)(a1 + 128));
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<bool> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostBroker::LocalNgc::CreateLocalPinAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
        AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>(&ppstm);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
  }
  return v2;
}

```

## disassembly

```asm
0x180023ef0  push    rbp
0x180023ef2  push    rbx
0x180023ef3  push    rdi
0x180023ef4  mov     rbp, rsp
0x180023ef7  sub     rsp, 50h
0x180023efb  mov     rbx, rcx
0x180023efe  xor     edi, edi
0x180023f00  lea     edx, [rdi+1]
0x180023f03  call    ?TransitionToState@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?UpdateSecurityQuestionsAsyncActionName@Account@CloudExperienceHostBroker@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostBroker::Account::UpdateSecurityQuestionsAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x180023f08  cmp     [rcx+88h], edi
0x180023f0e  jle     loc_180024081
0x180023f14  mov     eax, edx
0x180023f16  lock xadd [rcx+10h], eax
0x180023f1b  inc     eax
0x180023f1d  cmp     eax, edx
0x180023f1f  jnz     loc_180024081
0x180023f25  mov     [rbp+var_20], rcx
0x180023f29  lea     rcx, [rbp+var_20]
0x180023f2d  call    ?InternalAddRef@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IAsyncInfo>::InternalAddRef(void)
0x180023f32  nop
0x180023f33  mov     [rbp+pUnk], rdi
0x180023f37  mov     rcx, rbx
0x180023f3a  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?CreateLocalPinAsyncActionName@LocalNgc@CloudExperienceHostBroker@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostBroker::LocalNgc::CreateLocalPinAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x180023f3f  lea     rdx, [rbp+pUnk]
0x180023f43  lea     rcx, [rbp+var_20]
0x180023f47  call    ??$As@U?$IAsyncOperation@_N@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@_N@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<bool>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<bool>>>)
0x180023f4c  test    eax, eax
0x180023f4e  js      loc_18002406E
0x180023f54  mov     [rbp+arg_0], 0FFFFFFFEh
0x180023f5b  mov     ecx, [rbx+38h]
0x180023f5e  mov     eax, [rbp+arg_0]
0x180023f61  lock cmpxchg [rbp+arg_0], ecx
0x180023f66  mov     [rbp+arg_8], rdi
0x180023f6a  lea     rcx, [rbp+arg_8]
0x180023f6e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180023f73  lea     rcx, [rbx+78h]
0x180023f77  lea     r8, [rbp+arg_8]
0x180023f7b  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::CopyLocal(_GUID const &,void * *)
0x180023f80  test    eax, eax
0x180023f82  js      loc_180024064
0x180023f88  mov     rcx, rbx
0x180023f8b  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@_N@Collections@Foundation@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<bool> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x180023f90  mov     [rbp+arg_10], rdi
0x180023f94  lea     rcx, [rbp+arg_10]
0x180023f98  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180023f9d  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x180023fa1  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180023fa5  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x180023faa  mov     [rbp+ppstm], rdi
0x180023fae  mov     [rbp+var_10], edi
0x180023fb1  cmp     [rbp+arg_10], rdi
0x180023fb5  jz      short loc_18002400F
0x180023fb7  cmp     [rbp+arg_8], rdi
0x180023fbb  jz      short loc_18002400F
0x180023fbd  mov     rdi, [rbp+pUnk]
0x180023fc1  lea     rcx, [rbp+ppstm]
0x180023fc5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180023fca  lea     r8, [rbp+ppstm]; ppstm
0x180023fce  mov     edx, 1; fDeleteOnRelease
0x180023fd3  xor     ecx, ecx; hGlobal
0x180023fd5  call    cs:__imp_CreateStreamOnHGlobal
0x180023fdb  mov     [rbp+var_10], eax
0x180023fde  test    eax, eax
0x180023fe0  js      short loc_180024016
0x180023fe2  mov     [rsp+50h+mshlflags], 1; mshlflags
0x180023fea  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x180023ff3  xor     r9d, r9d; dwDestContext
0x180023ff6  mov     r8, rdi; pUnk
0x180023ff9  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180024000  mov     rcx, [rbp+ppstm]; pStm
0x180024004  call    cs:__imp_CoMarshalInterface
0x18002400a  mov     [rbp+var_10], eax
0x18002400d  jmp     short loc_180024016
0x18002400f  mov     [rbp+var_10], 80004002h
0x180024016  mov     rcx, [rbp+arg_8]
0x18002401a  mov     rax, [rcx]
0x18002401d  mov     r8d, [rbp+arg_0]
0x180024021  mov     rdx, [rbp+pUnk]
0x180024025  mov     rax, [rax+18h]
0x180024029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002402e  mov     r8, [rbx+80h]
0x180024035  mov     rdx, [rbp+arg_8]
0x180024039  mov     ecx, eax
0x18002403b  call    ?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180024040  mov     edi, eax
0x180024042  mov     rcx, rbx
0x180024045  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@_N@Collections@Foundation@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<bool> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x18002404a  call    ?TraceCompletionNotificationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?CreateLocalPinAsyncActionName@LocalNgc@CloudExperienceHostBroker@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostBroker::LocalNgc::CreateLocalPinAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x18002404f  nop
0x180024050  lea     rcx, [rbp+ppstm]
0x180024054  call    ??1?$AutoStubBias@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>(void)
0x180024059  nop
0x18002405a  lea     rcx, [rbp+arg_10]
0x18002405e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024063  nop
0x180024064  lea     rcx, [rbp+arg_8]
0x180024068  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002406d  nop
0x18002406e  lea     rcx, [rbp+pUnk]
0x180024072  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024077  nop
0x180024078  lea     rcx, [rbp+var_20]
0x18002407c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024081  mov     eax, edi
0x180024083  add     rsp, 50h
0x180024087  pop     rdi
0x180024088  pop     rbx
0x180024089  pop     rbp
0x18002408a  retn
```
