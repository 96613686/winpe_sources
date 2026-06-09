# Windows::Security::Authentication::Web::CWebAuthOperation::LaunchWAMBridge(void)

- ea: `0x180019484`
- end: `0x1800197dc`
- name: `?LaunchWAMBridge@CWebAuthOperation@Web@Authentication@Security@Windows@@QEAAXXZ`
- size: `856`
- prototype: `void __fastcall(Windows::Security::Authentication::Web::CWebAuthOperation *this)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b900`

## callees

- `0x1800011b4`
- `0x1800012c4`
- `0x1800013fc`
- `0x1800045c0`
- `0x180004d00`
- `0x180004f00`
- `0x1800054bc`
- `0x180006060`
- `0x18000611c`
- `0x18001261c`
- `0x180016018`
- `0x1800183f0`
- `0x1800193b4`
- `0x18001941c`
- `0x180019484`
- `0x18001b7c8`
- `0x18001ecc8`
- `0x18001ed50`
- `0x18001f2c8`
- `0x18001f624`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001961f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001961f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180019725`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180019725`
- `OLEAUT32!__imp_SysFreeString` at `0x1800197ac`
- `OLEAUT32!__imp_SysFreeString` at `0x1800197ac`
- `urlmon!CreateUri` at `0x180019634`
- `urlmon!CreateUri` at `0x180019634`

## pseudocode

```c
void __fastcall Windows::Security::Authentication::Web::CWebAuthOperation::LaunchWAMBridge(
        Windows::Security::Authentication::Web::CWebAuthOperation *this)
{
  Windows::Security::Authentication::Web::WebAuthenticationOptions m_WebAuthOptions; // eax
  int *p_m_UseSsoAppContainer; // rsi
  unsigned int *p_m_BrokerFlags; // r14
  WebAuthBridgeTelemetry::WamBridgeBrokerActivity *p_m_WamBridgeBrokerActivity; // r15
  TraceLoggingThreadActivity<&g_hMyWABTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider> *m_WebAuthActivity; // rdi
  bool v7; // zf
  const _GUID *p_m_CapturedRelatedId; // r9
  const _tlgProvider_t *v9; // rcx
  const _GUID *v10; // r8
  const _GUID *v11; // r9
  __int64 v12; // rdx
  bool v13; // r8
  HRESULT WebTokenRequestResultFromWAMRequest; // eax
  const wchar_t *StringRawBuffer; // rax
  const _tlgProvider_t *v16; // rcx
  const _GUID *v17; // r8
  const _GUID *v18; // r9
  Microsoft::WRL::CancelTransitionPolicy v19; // r8d
  void *v20; // r9
  HRESULT m_ResponseHr; // edx
  TraceLoggingThreadActivity<&g_hMyWABTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider> *v22; // rdi
  Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequest> tokenRequest; // [rsp+40h] [rbp-20h] BYREF
  wchar_t *telAppPfn; // [rsp+48h] [rbp-18h] BYREF
  ATL::CComBSTR telStartDomain; // [rsp+50h] [rbp-10h] BYREF
  ATL::CComPtr<IUri> telStartUri; // [rsp+58h] [rbp-8h] BYREF
  _tlgWrapSz<unsigned short> webAuthOptions; // [rsp+A0h] [rbp+40h] BYREF
  _tlgWrapperByVal<4> v28; // [rsp+A8h] [rbp+48h] BYREF
  _tlgWrapperByVal<4> v29; // [rsp+B0h] [rbp+50h] BYREF
  Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult> requestResult; // [rsp+B8h] [rbp+58h] BYREF

  m_WebAuthOptions = this->m_WebAuthOptions;
  p_m_UseSsoAppContainer = &this->m_UseSsoAppContainer;
  p_m_BrokerFlags = &this->m_BrokerFlags;
  tokenRequest.ptr_ = 0;
  p_m_WamBridgeBrokerActivity = &this->m_WamBridgeBrokerActivity;
  requestResult.ptr_ = 0;
  telStartUri.p = 0;
  telStartDomain.m_str = 0;
  telAppPfn = 0;
  LODWORD(webAuthOptions.Psz) = m_WebAuthOptions;
  WebAuthBridgeTelemetry::WamBridgeBrokerActivity::LaunchWamBridgeParams<unsigned int &,int &,int>(
    &this->m_WamBridgeBrokerActivity,
    &this->m_BrokerFlags,
    &this->m_UseSsoAppContainer,
    (int *)&webAuthOptions);
  m_WebAuthActivity = this->m_WebAuthActivity;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMyWABTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(m_WebAuthActivity);
  if ( Tlgg_hMyWABTraceLoggingProviderProv.LevelPlus1 > 5
    && tlgKeywordOn(&Tlgg_hMyWABTraceLoggingProviderProv, 0x400000000000uLL) )
  {
    v7 = !m_WebAuthActivity->m_HasRelatedId;
    LODWORD(webAuthOptions.Psz) = this->m_WebAuthOptions;
    v28.Value = *p_m_UseSsoAppContainer;
    v29.Value = *p_m_BrokerFlags;
    if ( v7
      || (p_m_CapturedRelatedId = &m_WebAuthActivity->m_CapturedRelatedId, !m_WebAuthActivity->m_CapturedRelatedId.Data1)
      && !*(_DWORD *)&m_WebAuthActivity->m_CapturedRelatedId.Data2
      && !*(_DWORD *)m_WebAuthActivity->m_CapturedRelatedId.Data4
      && !*(_DWORD *)&m_WebAuthActivity->m_CapturedRelatedId.Data4[4] )
    {
      p_m_CapturedRelatedId = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      &Tlgg_hMyWABTraceLoggingProviderProv,
      &tlgEvent_6._tlgChannel,
      &m_WebAuthActivity->m_Id,
      p_m_CapturedRelatedId,
      &v29,
      &v28,
      (const _tlgWrapperByVal<4> *)&webAuthOptions);
  }
  if ( (int)GetAuthBrokerClientAppContainerStringInfo(2, this->m_ClientContext->tokenHandle, &telAppPfn) >= 0
    && Tlgg_hMyWABTraceLoggingProviderProv.LevelPlus1 > 5
    && tlgKeywordOn(&Tlgg_hMyWABTraceLoggingProviderProv, 0x400000000000uLL) )
  {
    webAuthOptions.Psz = telAppPfn;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v9,
      &tlgEvent_5._tlgChannel,
      v10,
      v11,
      &webAuthOptions);
  }
  if ( (*p_m_BrokerFlags & 0x20000) != 0 )
  {
    WebAuthBridgeTelemetry::WamBridgeBrokerActivity::LaunchSilentModeWAB(p_m_WamBridgeBrokerActivity);
    WebTokenRequestResultFromWAMRequest = Windows::Security::Authentication::Web::CWebAuthOperation::LaunchSilentModeWAB(
                                            this,
                                            v12,
                                            v13);
    goto LABEL_24;
  }
  WebAuthBridgeTelemetry::WamBridgeBrokerActivity::LaunchUIModeWAB(p_m_WamBridgeBrokerActivity);
  StringRawBuffer = WindowsGetStringRawBuffer(this->m_TargetUri._hstring, 0);
  if ( CreateUri(StringRawBuffer, 0x2000u, 0, &telStartUri.p) >= 0
    && telStartUri.p->GetHost(telStartUri.p, (wchar_t **)&telStartDomain) >= 0
    && Tlgg_hMyWABTraceLoggingProviderProv.LevelPlus1 > 5
    && tlgKeywordOn(&Tlgg_hMyWABTraceLoggingProviderProv, 0x400000000000uLL) )
  {
    webAuthOptions.Psz = telStartDomain.m_str;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v16,
      &tlgEvent_4._tlgChannel,
      v17,
      v18,
      &webAuthOptions);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&tokenRequest);
  WebTokenRequestResultFromWAMRequest = Windows::Security::Authentication::Web::CWebAuthOperation::ConvertWABOperationToWAMRequest(
                                          this,
                                          &tokenRequest.ptr_);
  if ( WebTokenRequestResultFromWAMRequest >= 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&requestResult);
    WebTokenRequestResultFromWAMRequest = Windows::Security::Authentication::Web::CWebAuthOperation::GetWebTokenRequestResultFromWAMRequest(
                                            this,
                                            tokenRequest.ptr_,
                                            &requestResult.ptr_);
    if ( WebTokenRequestResultFromWAMRequest >= 0 )
    {
      WebTokenRequestResultFromWAMRequest = Windows::Security::Authentication::Web::CWebAuthOperation::PopulateWABResponseFromWAMResult(
                                              this,
                                              requestResult.ptr_);
LABEL_24:
      if ( WebTokenRequestResultFromWAMRequest >= 0 )
        goto $Exit_19;
    }
  }
  this->m_ResponseHr = WebTokenRequestResultFromWAMRequest;
$Exit_19:
  FreeAuthBrokerClientAppContainerString(ClientAppContainerPackageFullNameInfo, telAppPfn);
  Windows::Security::Authentication::Web::CWebAuthOperation::CleanupLocalMutex(this);
  m_ResponseHr = this->m_ResponseHr;
  if ( m_ResponseHr < 0 )
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
      &this->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > > >,
      m_ResponseHr,
      v19,
      v20);
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(&this->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > > >);
  v22 = this->m_WebAuthActivity;
  if ( v22->m_HasRelatedId )
    EventActivityIdControl(4u, &v22->m_CapturedRelatedId);
  v22->m_State = TlgStateStopped;
  if ( Tlgg_hMyWABTraceLoggingProviderProv.LevelPlus1 > 5
    && tlgKeywordOn(&Tlgg_hMyWABTraceLoggingProviderProv, 0x400000000000uLL) )
  {
    LODWORD(webAuthOptions.Psz) = this->m_ResponseErrorDetail;
    v28.Value = this->m_ResponseHr;
    v29.Value = this->m_ResponseStatus;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      &Tlgg_hMyWABTraceLoggingProviderProv,
      &tlgEvent_3._tlgChannel,
      &v22->m_Id,
      0,
      &v29,
      &v28,
      (const _tlgWrapperByVal<4> *)&webAuthOptions);
  }
  wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    p_m_WamBridgeBrokerActivity,
    this->m_ResponseHr);
  SysFreeString(telStartDomain.m_str);
  ATL::CComPtrBase<IUri>::~CComPtrBase<IUri>(&telStartUri);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&requestResult);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&tokenRequest);
}

```

## disassembly

```asm
0x180019484  push    rbp
0x180019486  push    rbx
0x180019487  push    rsi
0x180019488  push    rdi
0x180019489  push    r13
0x18001948b  push    r14
0x18001948d  push    r15
0x18001948f  mov     rbp, rsp
0x180019492  sub     rsp, 60h
0x180019496  mov     eax, [this+104h]
0x18001949c  lea     rsi, [this+100h]
0x1800194a3  lea     r14, [this+0FCh]
0x1800194aa  mov     [rbp+tokenRequest.ptr_], 0
0x1800194b2  lea     r15, [this+118h]
0x1800194b9  mov     [rbp+requestResult.ptr_], 0
0x1800194c1  mov     rbx, this
0x1800194c4  mov     [rbp+telStartUri.p], 0
0x1800194cc  mov     r8, rsi; useSsoAppContainer
0x1800194cf  mov     [rbp+telStartDomain.m_str], 0
0x1800194d7  mov     rdx, r14; brokerFlags
0x1800194da  mov     [rbp+telAppPfn], 0
0x1800194e2  mov     this, r15; this
0x1800194e5  mov     dword ptr [rbp+webAuthOptions], eax
0x1800194e8  lea     r9, [rbp+webAuthOptions]; webAuthOptions
0x1800194ec  call    ??$LaunchWamBridgeParams@AEAIAEAHH@WamBridgeBrokerActivity@WebAuthBridgeTelemetry@@QEAAXAEAIAEAH$$QEAH@Z; WebAuthBridgeTelemetry::WamBridgeBrokerActivity::LaunchWamBridgeParams<uint &,int &,int>(uint &,int &,int &&)
0x1800194f1  mov     rdi, [rbx+0C0h]
0x1800194f8  mov     this, rdi; this
0x1800194fb  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hMyWABTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMyWABTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x180019500  mov     eax, cs:_Tlgg_hMyWABTraceLoggingProviderProv.LevelPlus1
0x180019506  lea     r13, _Tlgg_hMyWABTraceLoggingProviderProv
0x18001950d  cmp     eax, 5
0x180019510  jbe     loc_180019596
0x180019516  mov     rdx, 400000000000h; keyword
0x180019520  mov     this, r13; hProvider
0x180019523  call    _tlgKeywordOn
0x180019528  test    al, al
0x18001952a  jz      short loc_180019596
0x18001952c  cmp     byte ptr [rdi+4], 0; __annotation("_TlgWrite:|91|_tlgActivity.Provider()|("WebAuthBridgeActivityStart")=~^*m_WebAuthActivity^~|"brokerFlags"=|"useSsoAppContainer"=|"webAuthOptions"=")
0x180019530  mov     eax, [rbx+104h]
0x180019536  mov     dword ptr [rbp+webAuthOptions], eax
0x180019539  mov     eax, [rsi]
0x18001953b  mov     [rbp+arg_8.Value], eax
0x18001953e  mov     eax, [r14]
0x180019541  mov     [rbp+arg_10.Value], eax
0x180019544  jz      short loc_180019565
0x180019546  lea     r9, [rdi+18h]
0x18001954a  cmp     dword ptr [r9], 0
0x18001954e  jnz     short loc_180019568
0x180019550  cmp     dword ptr [r9+4], 0
0x180019555  jnz     short loc_180019568
0x180019557  cmp     dword ptr [r9+8], 0
0x18001955c  jnz     short loc_180019568
0x18001955e  cmp     dword ptr [r9+0Ch], 0
0x180019563  jnz     short loc_180019568
0x180019565  xor     r9d, r9d; <writerArgs_1>
0x180019568  lea     rax, [rbp+webAuthOptions]
0x18001956c  mov     this, r13; hProvider
0x18001956f  mov     [rsp+60h+var_30], rax; <wrappedArgs_2>
0x180019574  lea     r8, [rdi+8]; <writerArgs_0>
0x180019578  lea     rax, [rbp+arg_8]
0x18001957c  mov     [rsp+60h+var_38], rax; <wrappedArgs_1>
0x180019581  lea     rdx, _tlgEvent_6._tlgChannel; pEventMetadata
0x180019588  lea     rax, [rbp+arg_10]
0x18001958c  mov     [rsp+60h+var_40], rax; <wrappedArgs_0>
0x180019591  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180019596  mov     rdx, [rbx+0F0h]
0x18001959d  lea     r8, [rbp+telAppPfn]; string
0x1800195a1  mov     esi, 2
0x1800195a6  mov     ecx, esi; infoType
0x1800195a8  mov     rdx, [rdx+20h]; clientTokenHandle
0x1800195ac  call    ?GetAuthBrokerClientAppContainerStringInfo@@YAJW4ClientAppContainerStringInfoType@@PEAXPEAPEAG@Z; GetAuthBrokerClientAppContainerStringInfo(ClientAppContainerStringInfoType,void *,ushort * *)
0x1800195b1  test    eax, eax
0x1800195b3  js      short loc_1800195F3
0x1800195b5  mov     eax, cs:_Tlgg_hMyWABTraceLoggingProviderProv.LevelPlus1
0x1800195bb  cmp     eax, 5
0x1800195be  jbe     short loc_1800195F3
0x1800195c0  mov     rdx, 400000000000h; keyword
0x1800195ca  mov     this, r13; hProvider
0x1800195cd  call    _tlgKeywordOn
0x1800195d2  test    al, al
0x1800195d4  jz      short loc_1800195F3
0x1800195d6  mov     rax, [rbp+telAppPfn]; __annotation("_TlgWrite:|104|g_hMyWABTraceLoggingProvider|"WebAuthBridgePackagePfn"=|"packagePfn"=")
0x1800195da  lea     rdx, _tlgEvent_5._tlgChannel; <wrappedArgs_0>
0x1800195e1  mov     [rbp+webAuthOptions], rax
0x1800195e5  lea     rax, [rbp+webAuthOptions]
0x1800195e9  mov     [rsp+60h+var_40], rax; <writerArgs_0>
0x1800195ee  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800195f3  test    dword ptr [r14], 20000h
0x1800195fa  mov     this, r15; this
0x1800195fd  jz      short loc_180019611
0x1800195ff  call    ?LaunchSilentModeWAB@WamBridgeBrokerActivity@WebAuthBridgeTelemetry@@QEAAXXZ; WebAuthBridgeTelemetry::WamBridgeBrokerActivity::LaunchSilentModeWAB(void)
0x180019604  mov     this, rbx; this
0x180019607  call    ?LaunchSilentModeWAB@CWebAuthOperation@Web@Authentication@Security@Windows@@AEAAJXZ; Windows::Security::Authentication::Web::CWebAuthOperation::LaunchSilentModeWAB(void)
0x18001960c  jmp     loc_1800196D6
0x180019611  call    ?LaunchUIModeWAB@WamBridgeBrokerActivity@WebAuthBridgeTelemetry@@QEAAXXZ; WebAuthBridgeTelemetry::WamBridgeBrokerActivity::LaunchUIModeWAB(void)
0x180019616  mov     this, [rbx+0C8h]; string
0x18001961d  xor     edx, edx; length
0x18001961f  call    cs:__imp_WindowsGetStringRawBuffer
0x180019625  lea     r9, [rbp+telStartUri]; ppURI
0x180019629  xor     r8d, r8d; dwReserved
0x18001962c  mov     this, rax; pwzURI
0x18001962f  mov     edx, 2000h; dwFlags
0x180019634  call    cs:__imp_CreateUri
0x18001963a  test    eax, eax
0x18001963c  js      short loc_180019694
0x18001963e  mov     this, [rbp+telStartUri.p]
0x180019642  lea     rdx, [rbp+telStartDomain]
0x180019646  mov     rax, [this]
0x180019649  mov     rax, [rax+68h]
0x18001964d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019652  test    eax, eax
0x180019654  js      short loc_180019694
0x180019656  mov     eax, cs:_Tlgg_hMyWABTraceLoggingProviderProv.LevelPlus1
0x18001965c  cmp     eax, 5
0x18001965f  jbe     short loc_180019694
0x180019661  mov     rdx, 400000000000h; keyword
0x18001966b  mov     this, r13; hProvider
0x18001966e  call    _tlgKeywordOn
0x180019673  test    al, al
0x180019675  jz      short loc_180019694
0x180019677  mov     rax, [rbp+telStartDomain.m_str]; __annotation("_TlgWrite:|134|g_hMyWABTraceLoggingProvider|"WebAuthBridgeStartURLDomain"=|"startURLDomain"=")
0x18001967b  lea     rdx, _tlgEvent_4._tlgChannel; <wrappedArgs_0>
0x180019682  mov     [rbp+webAuthOptions], rax
0x180019686  lea     rax, [rbp+webAuthOptions]
0x18001968a  mov     [rsp+60h+var_40], rax; <writerArgs_0>
0x18001968f  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180019694  lea     this, [rbp+tokenRequest]; this
0x180019698  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001969d  lea     rdx, [rbp+tokenRequest]; ppWebTokenRequest
0x1800196a1  mov     this, rbx; this
0x1800196a4  call    ?ConvertWABOperationToWAMRequest@CWebAuthOperation@Web@Authentication@Security@Windows@@AEAAJPEAPEAUIWebTokenRequest@Core@2345@@Z; Windows::Security::Authentication::Web::CWebAuthOperation::ConvertWABOperationToWAMRequest(Windows::Security::Authentication::Web::Core::IWebTokenRequest * *)
0x1800196a9  test    eax, eax
0x1800196ab  js      short loc_1800196DA
0x1800196ad  lea     this, [rbp+requestResult]; this
0x1800196b1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800196b6  mov     rdx, [rbp+tokenRequest.ptr_]; pWebTokenRequest
0x1800196ba  lea     r8, [rbp+requestResult]; ppTokenResult
0x1800196be  mov     this, rbx; this
0x1800196c1  call    ?GetWebTokenRequestResultFromWAMRequest@CWebAuthOperation@Web@Authentication@Security@Windows@@AEAAJPEAUIWebTokenRequest@Core@2345@PEAPEAUIWebTokenRequestResult@72345@@Z; Windows::Security::Authentication::Web::CWebAuthOperation::GetWebTokenRequestResultFromWAMRequest(Windows::Security::Authentication::Web::Core::IWebTokenRequest *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult * *)
0x1800196c6  test    eax, eax
0x1800196c8  js      short loc_1800196DA
0x1800196ca  mov     rdx, [rbp+requestResult.ptr_]; pTokenResult
0x1800196ce  mov     this, rbx; this
0x1800196d1  call    ?PopulateWABResponseFromWAMResult@CWebAuthOperation@Web@Authentication@Security@Windows@@AEAAJPEAUIWebTokenRequestResult@Core@2345@@Z; Windows::Security::Authentication::Web::CWebAuthOperation::PopulateWABResponseFromWAMResult(Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *)
0x1800196d6  test    eax, eax
0x1800196d8  jns     short $Exit_19
0x1800196da  mov     [rbx+0E0h], eax
0x1800196e0  mov     rdx, [rbp+telAppPfn]; string
0x1800196e4  mov     ecx, esi; infoType
0x1800196e6  call    ?FreeAuthBrokerClientAppContainerString@@YAXW4ClientAppContainerStringInfoType@@PEAG@Z; FreeAuthBrokerClientAppContainerString(ClientAppContainerStringInfoType,ushort *)
0x1800196eb  mov     this, rbx; this
0x1800196ee  call    ?CleanupLocalMutex@CWebAuthOperation@Web@Authentication@Security@Windows@@QEAAXXZ; Windows::Security::Authentication::Web::CWebAuthOperation::CleanupLocalMutex(void)
0x1800196f3  mov     edx, [rbx+0E0h]; error
0x1800196f9  test    edx, edx
0x1800196fb  jns     short loc_180019706
0x1800196fd  lea     this, [rbx+10h]; this
0x180019701  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x180019706  lea     this, [rbx+10h]; this
0x18001970a  call    ?FireCompletion@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)
0x18001970f  mov     rdi, [rbx+0C0h]
0x180019716  cmp     byte ptr [rdi+4], 0
0x18001971a  jz      short loc_18001972B
0x18001971c  lea     rdx, [rdi+18h]; ActivityId
0x180019720  mov     ecx, 4; ControlCode
0x180019725  call    cs:__imp_EventActivityIdControl
0x18001972b  mov     [rdi], esi
0x18001972d  mov     eax, cs:_Tlgg_hMyWABTraceLoggingProviderProv.LevelPlus1
0x180019733  cmp     eax, 5
0x180019736  jbe     short loc_18001979A
0x180019738  mov     rdx, 400000000000h; keyword
0x180019742  mov     this, r13; hProvider
0x180019745  call    _tlgKeywordOn
0x18001974a  test    al, al
0x18001974c  jz      short loc_18001979A
0x18001974e  mov     eax, [rbx+0E8h]; __annotation("_TlgWrite:|181|_tlgActivity.Provider()|("WebAuthBridgeActivityStop")=~^*m_WebAuthActivity^~|"responseStatus"=|"responseHr"=|"responseErrorDetail"=")
0x180019754  lea     r8, [rdi+8]; <writerArgs_0>
0x180019758  mov     dword ptr [rbp+webAuthOptions], eax
0x18001975b  lea     rdx, _tlgEvent_3._tlgChannel; pEventMetadata
0x180019762  mov     eax, [rbx+0E0h]
0x180019768  xor     r9d, r9d; <writerArgs_1>
0x18001976b  mov     [rbp+arg_8.Value], eax
0x18001976e  mov     this, r13; hProvider
0x180019771  mov     eax, [rbx+0E4h]
0x180019777  mov     [rbp+arg_10.Value], eax
0x18001977a  lea     rax, [rbp+webAuthOptions]
0x18001977e  mov     [rsp+60h+var_30], rax; <wrappedArgs_2>
0x180019783  lea     rax, [rbp+arg_8]
0x180019787  mov     [rsp+60h+var_38], rax; <wrappedArgs_1>
0x18001978c  lea     rax, [rbp+arg_10]
0x180019790  mov     [rsp+60h+var_40], rax; <wrappedArgs_0>
0x180019795  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001979a  mov     edx, [rbx+0E0h]; hr
0x1800197a0  mov     this, r15; this
0x1800197a3  call    ?Stop@?$ActivityBase@VWebAuthBridgeLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800197a8  mov     this, [rbp+telStartDomain.m_str]; bstrString
0x1800197ac  call    cs:__imp_SysFreeString
0x1800197b2  lea     this, [rbp+telStartUri]; this
0x1800197b6  call    ??1?$CComPtrBase@UIUri@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUri>::~CComPtrBase<IUri>(void)
0x1800197bb  lea     this, [rbp+requestResult]; this
0x1800197bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800197c4  lea     this, [rbp+tokenRequest]; this
0x1800197c8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800197cd  add     rsp, 60h
0x1800197d1  pop     r15
0x1800197d3  pop     r14
0x1800197d5  pop     r13
0x1800197d7  pop     rdi
0x1800197d8  pop     rsi
0x1800197d9  pop     rbx
0x1800197da  pop     rbp
0x1800197db  retn
```
