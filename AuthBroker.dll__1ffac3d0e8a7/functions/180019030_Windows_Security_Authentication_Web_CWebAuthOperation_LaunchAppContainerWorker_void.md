# Windows::Security::Authentication::Web::CWebAuthOperation::LaunchAppContainerWorker(void)

- ea: `0x180019030`
- end: `0x1800192db`
- name: `?LaunchAppContainerWorker@CWebAuthOperation@Web@Authentication@Security@Windows@@QEAAXXZ`
- size: `683`
- prototype: `void __fastcall(Windows::Security::Authentication::Web::CWebAuthOperation *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b900`

## callees

- `0x1800011b4`
- `0x180001280`
- `0x1800013fc`
- `0x180003330`
- `0x180004d00`
- `0x180006060`
- `0x180012b88`
- `0x180016130`
- `0x1800183f0`
- `0x180019030`
- `0x18001b7c8`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800191c2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800191c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800191a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800191a1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001923d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001923d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180019192`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180019192`

## pseudocode

```c
void __fastcall Windows::Security::Authentication::Web::CWebAuthOperation::LaunchAppContainerWorker(
        Windows::Security::Authentication::Web::CWebAuthOperation *this)
{
  TraceLoggingThreadActivity<&g_hMyWABTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider> *m_WebAuthActivity; // rbx
  const _GUID *p_m_CapturedRelatedId; // r9
  HRESULT LastError; // eax
  Microsoft::WRL::CancelTransitionPolicy v5; // r8d
  void *v6; // r9
  Windows::Security::Authentication::Web::AsyncMapping *ptr; // rbx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  HANDLE Thread; // rax
  __int64 v10; // rdx
  const _GUID *v11; // r8
  _AUTH_BROKER_CLIENT_CONTEXT *m_ClientContext; // rcx
  HRESULT m_ResponseHr; // edx
  TraceLoggingThreadActivity<&g_hMyWABTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider> *v14; // rbx
  Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::AsyncMapping> AsyncMap; // [rsp+40h] [rbp-10h] BYREF
  _tlgWrapperByVal<4> v16; // [rsp+80h] [rbp+30h] BYREF
  _tlgWrapperByVal<4> v17; // [rsp+88h] [rbp+38h] BYREF
  _tlgWrapperByVal<4> v18; // [rsp+90h] [rbp+40h] BYREF
  Microsoft::WRL::ComPtr<IAuthBrokerUIContext> spUiContext; // [rsp+98h] [rbp+48h] BYREF

  m_WebAuthActivity = this->m_WebAuthActivity;
  AsyncMap.ptr_ = 0;
  spUiContext.ptr_ = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMyWABTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(m_WebAuthActivity);
  if ( Tlgg_hMyWABTraceLoggingProviderProv.LevelPlus1 > 5
    && tlgKeywordOn(&Tlgg_hMyWABTraceLoggingProviderProv, 0x400000000000uLL) )
  {
    if ( !m_WebAuthActivity->m_HasRelatedId
      || (p_m_CapturedRelatedId = &m_WebAuthActivity->m_CapturedRelatedId, !m_WebAuthActivity->m_CapturedRelatedId.Data1)
      && !*(_DWORD *)&m_WebAuthActivity->m_CapturedRelatedId.Data2
      && !*(_DWORD *)m_WebAuthActivity->m_CapturedRelatedId.Data4
      && !*(_DWORD *)&m_WebAuthActivity->m_CapturedRelatedId.Data4[4] )
    {
      p_m_CapturedRelatedId = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &Tlgg_hMyWABTraceLoggingProviderProv,
      &tlgEvent_2._tlgChannel,
      &m_WebAuthActivity->m_Id,
      p_m_CapturedRelatedId);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&AsyncMap);
  LastError = Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Authentication::Web::AsyncMapping,Windows::Security::Authentication::Web::AsyncMapping,>(&AsyncMap.ptr_);
  if ( LastError < 0 )
    goto LABEL_11;
  ptr = AsyncMap.ptr_;
  LastError = Windows::Internal::String::Initialize(&AsyncMap.ptr_->TargetUri, &this->m_TargetUri._hstring);
  if ( LastError < 0 )
    goto LABEL_11;
  LastError = Windows::Internal::String::Initialize(&ptr->EndUri, &this->m_EndUri._hstring);
  if ( LastError < 0 )
    goto LABEL_11;
  ptr->ResponseHr = 0;
  *(_QWORD *)&ptr->ResponseStatus = 1;
  ptr->pAuthOp = this;
  ptr->ClientContext = this->m_ClientContext;
  ptr->BrokerFlags = this->m_BrokerFlags;
  ptr->UseSsoAppContainer = this->m_UseSsoAppContainer;
  ptr->ActivityID = this->m_WebAuthActivity->m_Id;
  QueryInterface = ptr->QueryInterface;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spUiContext);
  LastError = QueryInterface(ptr, &GUID_8e2eb5ad_c7e1_4bfb_98fe_5aa21c1a55de, (void **)&spUiContext.ptr_);
  if ( LastError < 0 )
    goto LABEL_11;
  Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)ActivateAppContainer, spUiContext.ptr_, 0, &this->m_ThreadId);
  ptr->hThreadHandle = Thread;
  if ( !Thread )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_11:
    this->m_ResponseHr = LastError;
    goto $Cleanup_4;
  }
  WaitForSingleObject(Thread, 0xFFFFFFFF);
  m_ClientContext = this->m_ClientContext;
  if ( m_ClientContext )
  {
    FreeAuthBrokerClientContext(m_ClientContext, v10, v11);
    this->m_ClientContext = 0;
  }
  this->m_ResponseHr = ptr->ResponseHr;
  this->m_ResponseStatus = ptr->ResponseStatus;
  this->m_ResponseErrorDetail = ptr->ResponseErrorDetail;
  Windows::Internal::String::Initialize(&this->m_ResponseData, &ptr->ResponseData._hstring);
$Cleanup_4:
  m_ResponseHr = this->m_ResponseHr;
  if ( m_ResponseHr < 0 )
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
      &this->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > > >,
      m_ResponseHr,
      v5,
      v6);
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(&this->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > > >);
  v14 = this->m_WebAuthActivity;
  if ( v14->m_HasRelatedId )
    EventActivityIdControl(4u, &v14->m_CapturedRelatedId);
  v14->m_State = TlgStateStopped;
  if ( Tlgg_hMyWABTraceLoggingProviderProv.LevelPlus1 > 5
    && tlgKeywordOn(&Tlgg_hMyWABTraceLoggingProviderProv, 0x400000000000uLL) )
  {
    v16.Value = this->m_ResponseErrorDetail;
    v17.Value = this->m_ResponseHr;
    v18.Value = this->m_ResponseStatus;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      &Tlgg_hMyWABTraceLoggingProviderProv,
      &tlgEvent_1._tlgChannel,
      &v14->m_Id,
      0,
      &v18,
      &v17,
      &v16);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spUiContext);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&AsyncMap);
}

```

## disassembly

```asm
0x180019030  push    rbp
0x180019032  push    rbx
0x180019033  push    rsi
0x180019034  push    rdi
0x180019035  push    r14
0x180019037  mov     rbp, rsp
0x18001903a  sub     rsp, 50h
0x18001903e  mov     rbx, [this+0C0h]
0x180019045  mov     rsi, this
0x180019048  xor     r14d, r14d
0x18001904b  mov     this, rbx; this
0x18001904e  mov     [rbp+AsyncMap.ptr_], r14
0x180019052  mov     [rbp+spUiContext.ptr_], r14
0x180019056  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hMyWABTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMyWABTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x18001905b  mov     eax, cs:_Tlgg_hMyWABTraceLoggingProviderProv.LevelPlus1
0x180019061  cmp     eax, 5
0x180019064  jbe     short loc_1800190BB
0x180019066  mov     rdx, 400000000000h; keyword
0x180019070  lea     this, _Tlgg_hMyWABTraceLoggingProviderProv; hProvider
0x180019077  call    _tlgKeywordOn
0x18001907c  test    al, al
0x18001907e  jz      short loc_1800190BB
0x180019080  cmp     [rbx+4], r14b; __annotation("_TlgWrite:|454|_tlgActivity.Provider()|("WebAuthActivityStart")=~^*m_WebAuthActivity^~")
0x180019084  jz      short loc_1800190A1
0x180019086  lea     r9, [rbx+18h]
0x18001908a  cmp     [r9], r14d
0x18001908d  jnz     short loc_1800190A4
0x18001908f  cmp     [r9+4], r14d
0x180019093  jnz     short loc_1800190A4
0x180019095  cmp     [r9+8], r14d
0x180019099  jnz     short loc_1800190A4
0x18001909b  cmp     [r9+0Ch], r14d
0x18001909f  jnz     short loc_1800190A4
0x1800190a1  mov     r9, r14; <writerArgs_1>
0x1800190a4  lea     r8, [rbx+8]; <writerArgs_0>
0x1800190a8  lea     rdx, _tlgEvent_2._tlgChannel; pEventMetadata
0x1800190af  lea     this, _Tlgg_hMyWABTraceLoggingProviderProv; hProvider
0x1800190b6  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800190bb  lea     this, [rbp+AsyncMap]; this
0x1800190bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800190c4  lea     this, [rbp+AsyncMap]; result
0x1800190c8  call    ??$MakeAndInitialize@VAsyncMapping@Web@Authentication@Security@Windows@@V12345@$$V@Details@WRL@Microsoft@@YAJPEAPEAVAsyncMapping@Web@Authentication@Security@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Authentication::Web::AsyncMapping,Windows::Security::Authentication::Web::AsyncMapping,>(Windows::Security::Authentication::Web::AsyncMapping * *)
0x1800190cd  test    eax, eax
0x1800190cf  jns     short loc_1800190DC
0x1800190d1  mov     [rsi+0E0h], eax
0x1800190d7  jmp     $Cleanup_4
0x1800190dc  mov     rbx, [rbp+AsyncMap.ptr_]
0x1800190e0  lea     rdx, [rsi+0C8h]; other
0x1800190e7  lea     this, [rbx+38h]; this
0x1800190eb  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x1800190f0  test    eax, eax
0x1800190f2  js      short loc_1800190D1
0x1800190f4  lea     rdx, [rsi+0D0h]; other
0x1800190fb  lea     this, [rbx+40h]; this
0x1800190ff  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180019104  test    eax, eax
0x180019106  js      short loc_1800190D1
0x180019108  mov     [rbx+50h], r14d
0x18001910c  lea     this, [rbp+spUiContext]; this
0x180019110  mov     qword ptr [rbx+54h], 1
0x180019118  mov     [rbx+30h], rsi
0x18001911c  mov     rax, [rsi+0F0h]
0x180019123  mov     [rbx+60h], rax
0x180019127  mov     eax, [rsi+0FCh]
0x18001912d  mov     [rbx+70h], eax
0x180019130  mov     eax, [rsi+100h]
0x180019136  mov     [rbx+74h], eax
0x180019139  mov     rax, [rsi+0C0h]
0x180019140  movups  xmm0, xmmword ptr [rax+8]
0x180019144  movdqu  xmmword ptr [rbx+78h], xmm0
0x180019149  mov     rax, [rbx]
0x18001914c  mov     rdi, [rax]
0x18001914f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019154  lea     r8, [rbp+spUiContext]
0x180019158  mov     this, rbx
0x18001915b  lea     rdx, _GUID_8e2eb5ad_c7e1_4bfb_98fe_5aa21c1a55de
0x180019162  mov     rax, rdi
0x180019165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001916a  test    eax, eax
0x18001916c  js      loc_1800190D1
0x180019172  mov     r9, [rbp+spUiContext.ptr_]; lpParameter
0x180019176  lea     rax, [rsi+0F8h]
0x18001917d  mov     [rsp+50h+lpThreadId], rax; lpThreadId
0x180019182  lea     r8, ?ActivateAppContainer@@YAKPEAX@Z; lpStartAddress
0x180019189  xor     edx, edx; dwStackSize
0x18001918b  mov     [rsp+50h+dwCreationFlags], r14d; dwCreationFlags
0x180019190  xor     ecx, ecx; lpThreadAttributes
0x180019192  call    cs:__imp_CreateThread
0x180019198  mov     [rbx+68h], rax
0x18001919c  test    rax, rax
0x18001919f  jnz     short loc_1800191BC
0x1800191a1  call    cs:__imp_GetLastError
0x1800191a7  test    eax, eax
0x1800191a9  jle     loc_1800190D1
0x1800191af  movzx   eax, ax
0x1800191b2  or      eax, 80070000h
0x1800191b7  jmp     loc_1800190D1
0x1800191bc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800191bf  mov     this, rax; hHandle
0x1800191c2  call    cs:__imp_WaitForSingleObject
0x1800191c8  mov     this, [rsi+0F0h]; clientContext
0x1800191cf  test    this, this
0x1800191d2  jz      short loc_1800191E0
0x1800191d4  call    ?FreeAuthBrokerClientContext@@YAXPEAU_AUTH_BROKER_CLIENT_CONTEXT@@@Z; FreeAuthBrokerClientContext(_AUTH_BROKER_CLIENT_CONTEXT *)
0x1800191d9  mov     [rsi+0F0h], r14
0x1800191e0  mov     eax, [rbx+50h]
0x1800191e3  lea     rdx, [rbx+48h]; other
0x1800191e7  mov     [rsi+0E0h], eax
0x1800191ed  lea     this, [rsi+0D8h]; this
0x1800191f4  mov     eax, [rbx+54h]
0x1800191f7  mov     [rsi+0E4h], eax
0x1800191fd  mov     eax, [rbx+58h]
0x180019200  mov     [rsi+0E8h], eax
0x180019206  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x18001920b  mov     edx, [rsi+0E0h]; error
0x180019211  test    edx, edx
0x180019213  jns     short loc_18001921E
0x180019215  lea     this, [rsi+10h]; this
0x180019219  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x18001921e  lea     this, [rsi+10h]; this
0x180019222  call    ?FireCompletion@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)
0x180019227  mov     rbx, [rsi+0C0h]
0x18001922e  cmp     [rbx+4], r14b
0x180019232  jz      short loc_180019243
0x180019234  lea     rdx, [rbx+18h]; ActivityId
0x180019238  mov     ecx, 4; ControlCode
0x18001923d  call    cs:__imp_EventActivityIdControl
0x180019243  mov     dword ptr [rbx], 2
0x180019249  mov     eax, cs:_Tlgg_hMyWABTraceLoggingProviderProv.LevelPlus1
0x18001924f  cmp     eax, 5
0x180019252  jbe     short loc_1800192BE
0x180019254  mov     rdx, 400000000000h; keyword
0x18001925e  lea     this, _Tlgg_hMyWABTraceLoggingProviderProv; hProvider
0x180019265  call    _tlgKeywordOn
0x18001926a  test    al, al
0x18001926c  jz      short loc_1800192BE
0x18001926e  mov     eax, [rsi+0E8h]; __annotation("_TlgWrite:|533|_tlgActivity.Provider()|("WebAuthActivityStop")=~^*m_WebAuthActivity^~|"responseStatus"=|"responseHr"=|"responseErrorDetail"=")
0x180019274  lea     r8, [rbx+8]; <writerArgs_0>
0x180019278  mov     [rbp+arg_0.Value], eax
0x18001927b  lea     rdx, _tlgEvent_1._tlgChannel; pEventMetadata
0x180019282  mov     eax, [rsi+0E0h]
0x180019288  lea     this, _Tlgg_hMyWABTraceLoggingProviderProv; hProvider
0x18001928f  mov     [rbp+arg_8.Value], eax
0x180019292  xor     r9d, r9d; <writerArgs_1>
0x180019295  mov     eax, [rsi+0E4h]
0x18001929b  mov     [rbp+arg_10.Value], eax
0x18001929e  lea     rax, [rbp+arg_0]
0x1800192a2  mov     [rsp+50h+var_20], rax; <wrappedArgs_2>
0x1800192a7  lea     rax, [rbp+arg_8]
0x1800192ab  mov     [rsp+50h+lpThreadId], rax; <wrappedArgs_1>
0x1800192b0  lea     rax, [rbp+arg_10]
0x1800192b4  mov     qword ptr [rsp+50h+dwCreationFlags], rax; <wrappedArgs_0>
0x1800192b9  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800192be  lea     this, [rbp+spUiContext]; this
0x1800192c2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800192c7  lea     this, [rbp+AsyncMap]; this
0x1800192cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800192d0  add     rsp, 50h
0x1800192d4  pop     r14
0x1800192d6  pop     rdi
0x1800192d7  pop     rsi
0x1800192d8  pop     rbx
0x1800192d9  pop     rbp
0x1800192da  retn
```
