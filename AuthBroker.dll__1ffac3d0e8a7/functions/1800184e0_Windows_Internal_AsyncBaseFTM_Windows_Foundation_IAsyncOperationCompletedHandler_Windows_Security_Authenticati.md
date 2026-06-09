# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x1800184e0`
- end: `0x180018675`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `405`
- prototype: `__int64 __fastcall(Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180006060`
- `0x180015bb4`
- `0x180016fc8`
- `0x18001810c`
- `0x1800184e0`
- `0x18001867c`
- `0x180018c58`
- `0x180018fe4`
- `0x18001b568`
- `0x18001b598`
- `0x18001b63c`
- `0x18001b760`
- `0x18001b858`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800185f3`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800185f3`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800185c4`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800185c4`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this)
{
  unsigned int v1; // edi
  unsigned int v3; // edx
  volatile Microsoft::WRL::Details::AsyncStatusInternal currentStatus; // ecx
  const _GUID *v5; // rdx
  bool v6; // dl
  Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::WebAuthenticationResult *> *ptr; // rdi
  HRESULT v8; // eax
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *v9; // rcx
  Microsoft::WRL::ComPtr<IAsyncInfo> asyncInfo; // [rsp+30h] [rbp-20h] BYREF
  AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *> > b1; // [rsp+38h] [rbp-18h] BYREF
  Microsoft::WRL::Details::AsyncStatusInternal current; // [rsp+70h] [rbp+20h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *> > completedDelegateLocal; // [rsp+78h] [rbp+28h] BYREF
  Microsoft::WRL::ComPtr<IRpcOptions> spRpcOptions; // [rsp+80h] [rbp+30h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::WebAuthenticationResult *> > operationInterface; // [rsp+88h] [rbp+38h] BYREF

  v1 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    this,
    _Completed);
  if ( this->completedDelegateLockCount_ > 0 && _InterlockedExchangeAdd(&this->cCallbackMade_, v3) + 1 == v3 )
  {
    asyncInfo.ptr_ = this;
    Microsoft::WRL::ComPtr<IAsyncInfo>::InternalAddRef(&asyncInfo);
    operationInterface.ptr_ = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(this);
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::WebAuthenticationResult *>>(
                &asyncInfo,
                (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::WebAuthenticationResult *> > >)&operationInterface) >= 0 )
    {
      currentStatus = this->currentStatus_;
      current = _Undefined;
      _InterlockedCompareExchange((volatile signed __int32 *)&current, currentStatus, -2);
      completedDelegateLocal.ptr_ = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&completedDelegateLocal);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>>::CopyLocal(
                  &this->completedDelegate_,
                  v5,
                  (void **)&completedDelegateLocal.ptr_) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(this);
        spRpcOptions.ptr_ = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spRpcOptions);
        RpcOptionsHelper::GetRpcOptions(completedDelegateLocal.ptr_, v6, &spRpcOptions.ptr_);
        b1.spStream_.ptr_ = 0;
        b1.hr_ = 0;
        if ( spRpcOptions.ptr_ && completedDelegateLocal.ptr_ )
        {
          ptr = operationInterface.ptr_;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&b1);
          b1.hr_ = CreateStreamOnHGlobal(0, 1, &b1.spStream_.ptr_);
          if ( b1.hr_ >= 0 )
            b1.hr_ = CoMarshalInterface(b1.spStream_.ptr_, &GUID_00000000_0000_0000_c000_000000000046, ptr, 0, 0, 1u);
        }
        else
        {
          b1.hr_ = -2147467262;
        }
        v8 = completedDelegateLocal.ptr_->Invoke(
               completedDelegateLocal.ptr_,
               operationInterface.ptr_,
               (ABI::Windows::Foundation::AsyncStatus)current);
        v1 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(
               v8,
               completedDelegateLocal.ptr_,
               this->completedDelegateBucketAssist_);
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(this);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(v9);
        AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>>(&b1);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spRpcOptions);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&completedDelegateLocal);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&operationInterface);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&asyncInfo);
  }
  return v1;
}

```

## disassembly

```asm
0x1800184e0  push    rbp
0x1800184e2  push    rbx
0x1800184e3  push    rdi
0x1800184e4  mov     rbp, rsp
0x1800184e7  sub     rsp, 50h
0x1800184eb  xor     edi, edi
0x1800184ed  mov     rbx, this
0x1800184f0  lea     edx, [rdi+1]; newState
0x1800184f3  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x1800184f8  cmp     [rbx+88h], edi
0x1800184fe  jle     loc_18001866B
0x180018504  mov     eax, edx
0x180018506  lock xadd [rbx+10h], eax
0x18001850b  inc     eax
0x18001850d  cmp     eax, edx
0x18001850f  jnz     loc_18001866B
0x180018515  lea     this, [rbp+asyncInfo]; this
0x180018519  mov     [rbp+asyncInfo.ptr_], rbx
0x18001851d  call    ?InternalAddRef@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IAsyncInfo>::InternalAddRef(void)
0x180018522  mov     this, rbx; this
0x180018525  mov     [rbp+operationInterface.ptr_], rdi
0x180018529  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x18001852e  lea     rdx, [rbp+operationInterface]; p
0x180018532  lea     this, [rbp+asyncInfo]; this
0x180018536  call    ??$As@U?$IAsyncOperation@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::WebAuthenticationResult *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::WebAuthenticationResult *>>>)
0x18001853b  test    eax, eax
0x18001853d  js      loc_180018659
0x180018543  mov     ecx, [rbx+38h]
0x180018546  mov     [rbp+current], 0FFFFFFFEh
0x18001854d  mov     eax, [rbp+current]
0x180018550  lock cmpxchg [rbp+current], ecx
0x180018555  lea     this, [rbp+completedDelegateLocal]; this
0x180018559  mov     [rbp+completedDelegateLocal.ptr_], rdi
0x18001855d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018562  lea     this, [rbx+78h]; this
0x180018566  lea     r8, [rbp+completedDelegateLocal]; riid
0x18001856a  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>>::CopyLocal(_GUID const &,void * *)
0x18001856f  test    eax, eax
0x180018571  js      loc_180018650
0x180018577  mov     this, rbx; this
0x18001857a  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x18001857f  lea     this, [rbp+spRpcOptions]; this
0x180018583  mov     [rbp+spRpcOptions.ptr_], rdi
0x180018587  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001858c  mov     this, [rbp+completedDelegateLocal.ptr_]; pInterface
0x180018590  lea     r8, [rbp+spRpcOptions]; pInterface
0x180018594  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x180018599  mov     [rbp+b1.spStream_.ptr_], rdi
0x18001859d  mov     [rbp+b1.hr_], edi
0x1800185a0  cmp     [rbp+spRpcOptions.ptr_], rdi
0x1800185a4  jz      short loc_1800185FE
0x1800185a6  cmp     [rbp+completedDelegateLocal.ptr_], rdi
0x1800185aa  jz      short loc_1800185FE
0x1800185ac  mov     rdi, [rbp+operationInterface.ptr_]
0x1800185b0  lea     this, [rbp+b1]; this
0x1800185b4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800185b9  lea     r8, [rbp+b1]; ppstm
0x1800185bd  mov     edx, 1; fDeleteOnRelease
0x1800185c2  xor     ecx, ecx; hGlobal
0x1800185c4  call    cs:__imp_CreateStreamOnHGlobal
0x1800185ca  mov     [rbp+b1.hr_], eax
0x1800185cd  test    eax, eax
0x1800185cf  js      short loc_180018605
0x1800185d1  mov     this, [rbp+b1.spStream_.ptr_]; pStm
0x1800185d5  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800185dc  mov     [rsp+50h+mshlflags], 1; mshlflags
0x1800185e4  xor     r9d, r9d; dwDestContext
0x1800185e7  mov     r8, rdi; pUnk
0x1800185ea  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x1800185f3  call    cs:__imp_CoMarshalInterface
0x1800185f9  mov     [rbp+b1.hr_], eax
0x1800185fc  jmp     short loc_180018605
0x1800185fe  mov     [rbp+b1.hr_], 80004002h
0x180018605  mov     this, [rbp+completedDelegateLocal.ptr_]
0x180018609  mov     r8d, [rbp+current]
0x18001860d  mov     rdx, [rbp+operationInterface.ptr_]
0x180018611  mov     rax, [this]
0x180018614  mov     rax, [rax+18h]
0x180018618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001861d  mov     r8, [rbx+80h]; pfnBucketAssist
0x180018624  mov     ecx, eax; hrIn
0x180018626  mov     rdx, [rbp+completedDelegateLocal.ptr_]; handler
0x18001862a  call    ?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18001862f  mov     this, rbx; this
0x180018632  mov     edi, eax
0x180018634  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x180018639  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x18001863e  lea     this, [rbp+b1]; this
0x180018642  call    ??1?$AutoStubBias@U?$IAsyncOperation@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>>(void)
0x180018647  lea     this, [rbp+spRpcOptions]; this
0x18001864b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018650  lea     this, [rbp+completedDelegateLocal]; this
0x180018654  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018659  lea     this, [rbp+operationInterface]; this
0x18001865d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018662  lea     this, [rbp+asyncInfo]; this
0x180018666  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001866b  mov     eax, edi
0x18001866d  add     rsp, 50h
0x180018671  pop     rdi
0x180018672  pop     rbx
0x180018673  pop     rbp
0x180018674  retn
```
