# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *> *)

- ea: `0x180019f10`
- end: `0x18001a038`
- name: `?PutOnComplete@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAU?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@3@@Z`
- size: `296`
- prototype: `HRESULT __fastcall(Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this, Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *> *completeHandler)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006060`
- `0x180018050`
- `0x180019f10`
- `0x18001b5e8`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180019f91`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180019f91`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this,
        Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *> *completeHandler)
{
  int AgileReference; // edi
  WaitForCompletion::__l2::FTMEventDelegate **p_completedDelegate; // rdi
  volatile Microsoft::WRL::Details::AsyncStatusInternal currentStatus; // ecx
  signed __int32 v8[8]; // [rsp+0h] [rbp-20h] BYREF
  Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> v9; // [rsp+50h] [rbp+30h] BYREF
  Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> v10; // [rsp+58h] [rbp+38h] BYREF

  AgileReference = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForDelegateCall(this);
  if ( AgileReference >= 0 )
  {
    if ( _InterlockedIncrement(&this->cCompleteDelegateAssigned_) != 1 )
      return (unsigned int)-2147483624;
    p_completedDelegate = (WaitForCompletion::__l2::FTMEventDelegate **)&this->completedDelegate_;
    v10.ptr_ = 0;
    v9.ptr_ = (WaitForCompletion::__l2::FTMEventDelegate *)this->completedDelegate_.m_agileRef.ptr_;
    this->completedDelegate_.m_agileRef.ptr_ = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
    if ( completeHandler )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&this->completedDelegate_);
      AgileReference = RoGetAgileReference(
                         0,
                         &GUID_3c1ec44c_e942_54e5_bcd3_e329c951f595,
                         completeHandler,
                         &this->completedDelegate_);
      if ( AgileReference < 0 )
        return (unsigned int)AgileReference;
    }
    else
    {
      v9.ptr_ = *p_completedDelegate;
      v10.ptr_ = 0;
      *p_completedDelegate = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
      AgileReference = 0;
    }
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceDelegateAssigned(this);
    if ( completeHandler )
    {
      this->completedDelegateBucketAssist_ = completeHandler->Invoke;
      _InterlockedIncrement(&this->completedDelegateLockCount_);
    }
    _InterlockedOr(v8, 0);
    currentStatus = this->currentStatus_;
    LODWORD(v9.ptr_) = -2;
    _InterlockedCompareExchange((volatile signed __int32 *)&v9, currentStatus, -2);
    if ( (unsigned int)(LODWORD(v9.ptr_) - 1) <= 3 )
      this->FireCompletion(this);
  }
  return (unsigned int)AgileReference;
}

```

## disassembly

```asm
0x180019f10  mov     [rsp-18h+arg_0], rbx
0x180019f15  push    rbp
0x180019f16  push    rsi
0x180019f17  push    rdi
0x180019f18  mov     rbp, rsp
0x180019f1b  sub     rsp, 20h
0x180019f1f  mov     rsi, completeHandler
0x180019f22  mov     rbx, this
0x180019f25  call    ?CheckValidStateForDelegateCall@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAJXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForDelegateCall(void)
0x180019f2a  mov     edi, eax
0x180019f2c  test    eax, eax
0x180019f2e  js      loc_18001A029
0x180019f34  mov     eax, 1
0x180019f39  lock xadd [rbx+14h], eax
0x180019f3e  inc     eax
0x180019f40  cmp     eax, 1
0x180019f43  jnz     loc_18001A024
0x180019f49  lea     rdi, [rbx+78h]
0x180019f4d  mov     [rbp+arg_18.ptr_], 0
0x180019f55  mov     rax, [rdi]
0x180019f58  lea     this, [rbp+arg_10]; this
0x180019f5c  mov     [rbp+arg_10.ptr_], rax
0x180019f60  mov     qword ptr [rdi], 0
0x180019f67  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019f6c  lea     this, [rbp+arg_18]; this
0x180019f70  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019f75  test    rsi, rsi
0x180019f78  jz      short loc_180019FA3
0x180019f7a  mov     this, rdi; this
0x180019f7d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019f82  mov     r9, rdi
0x180019f85  lea     completeHandler, _GUID_3c1ec44c_e942_54e5_bcd3_e329c951f595
0x180019f8c  mov     r8, rsi
0x180019f8f  xor     ecx, ecx
0x180019f91  call    cs:__imp_RoGetAgileReference
0x180019f97  mov     edi, eax
0x180019f99  test    eax, eax
0x180019f9b  js      loc_18001A029
0x180019fa1  jmp     short loc_180019FCD
0x180019fa3  mov     rax, [rdi]
0x180019fa6  lea     this, [rbp+arg_10]; this
0x180019faa  mov     [rbp+arg_10.ptr_], rax
0x180019fae  mov     [rbp+arg_18.ptr_], 0
0x180019fb6  mov     qword ptr [rdi], 0
0x180019fbd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019fc2  lea     this, [rbp+arg_18]; this
0x180019fc6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019fcb  xor     edi, edi
0x180019fcd  mov     this, rbx; this
0x180019fd0  call    ?TraceDelegateAssigned@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceDelegateAssigned(void)
0x180019fd5  test    rsi, rsi
0x180019fd8  jz      short loc_180019FEF
0x180019fda  mov     rax, [rsi]
0x180019fdd  mov     this, [rax+18h]
0x180019fe1  mov     [rbx+80h], this
0x180019fe8  lock inc dword ptr [rbx+88h]
0x180019fef  lock or [rsp+20h+var_20], 0
0x180019ff4  mov     ecx, [rbx+38h]
0x180019ff7  mov     dword ptr [rbp+arg_10.ptr_], 0FFFFFFFEh
0x180019ffe  mov     eax, dword ptr [rbp+arg_10.ptr_]
0x18001a001  lock cmpxchg dword ptr [rbp+arg_10.ptr_], ecx
0x18001a006  mov     ecx, dword ptr [rbp+arg_10.ptr_]
0x18001a009  dec     ecx
0x18001a00b  cmp     ecx, 3
0x18001a00e  ja      short loc_18001A029
0x18001a010  mov     rax, [rbx]
0x18001a013  mov     this, rbx
0x18001a016  mov     rax, [rax+80h]
0x18001a01d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a022  jmp     short loc_18001A029
0x18001a024  mov     edi, 80000018h
0x18001a029  mov     rbx, [rsp+20h+arg_0]
0x18001a02e  mov     eax, edi
0x18001a030  add     rsp, 20h
0x18001a034  pop     rdi
0x18001a035  pop     rsi
0x18001a036  pop     rbp
0x18001a037  retn
```
