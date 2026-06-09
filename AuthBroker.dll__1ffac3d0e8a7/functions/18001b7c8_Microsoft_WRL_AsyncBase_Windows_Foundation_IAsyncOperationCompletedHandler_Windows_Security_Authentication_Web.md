# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)

- ea: `0x18001b7c8`
- end: `0x18001b852`
- name: `?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z`
- size: `138`
- prototype: `bool __fastcall(Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this, const HRESULT error, Microsoft::WRL::CancelTransitionPolicy error, void *cancelBehavior)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019030`
- `0x180019484`
- `0x18001b900`

## callees

- `0x180006060`
- `0x18001b760`
- `0x18001b7c8`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x18001b7ed`
- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x18001b7ed`

## pseudocode

```c
bool __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this,
        signed __int32 error,
        Microsoft::WRL::CancelTransitionPolicy a3,
        void *cancelBehavior)
{
  bool v4; // bl
  HRESULT (__fastcall *TraceOperationRelation)(Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, Windows::Foundation::Diagnostics::CausalityTraceLevel, Windows::Foundation::Diagnostics::CausalitySource, _GUID, unsigned __int64, Windows::Foundation::Diagnostics::CausalityRelation); // rax
  GUID v8; // [rsp+40h] [rbp-18h] BYREF

  v4 = 0;
  if ( !_InterlockedCompareExchange(&this->errorCode_, error, 0) )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&this->errorInfo_);
    GetRestrictedErrorInfo(&this->errorInfo_);
    v4 = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
           this,
           _Error);
    if ( v4 )
    {
      if ( Microsoft::WRL::gCausality )
      {
        TraceOperationRelation = Microsoft::WRL::gCausality->TraceOperationRelation;
        v8 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
        ((void (__fastcall *)(Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *, int))TraceOperationRelation)(
          Microsoft::WRL::gCausality,
          2,
          2,
          &v8,
          this,
          4);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18001b7c8  mov     [rsp+arg_0], rbx
0x18001b7cd  push    rdi
0x18001b7ce  sub     rsp, 50h
0x18001b7d2  xor     bl, bl
0x18001b7d4  mov     rdi, this
0x18001b7d7  xor     eax, eax
0x18001b7d9  lock cmpxchg [this+3Ch], error
0x18001b7de  jnz     short loc_18001B845
0x18001b7e0  add     this, 30h ; '0'; this
0x18001b7e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b7e9  lea     this, [rdi+30h]
0x18001b7ed  call    cs:__imp_GetRestrictedErrorInfo
0x18001b7f3  mov     error, 3; newState
0x18001b7f8  mov     this, rdi; this
0x18001b7fb  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x18001b800  mov     bl, al
0x18001b802  test    al, al
0x18001b804  jz      short loc_18001B845
0x18001b806  mov     this, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18001b80d  test    this, this
0x18001b810  jz      short loc_18001B845
0x18001b812  mov     rdx, [this]
0x18001b815  lea     r9, [rsp+58h+var_18]
0x18001b81a  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18001b821  mov     [rsp+58h+var_30], 4
0x18001b829  mov     [rsp+58h+var_38], rdi
0x18001b82e  mov     rax, [rdx+40h]
0x18001b832  mov     error, 2
0x18001b837  mov     r8d, error
0x18001b83a  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm0
0x18001b840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b845  mov     al, bl
0x18001b847  mov     rbx, [rsp+58h+arg_0]
0x18001b84c  add     rsp, 50h
0x18001b850  pop     rdi
0x18001b851  retn
```
