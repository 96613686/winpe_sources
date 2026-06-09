# Windows::Security::Authentication::Web::CWebAuthOperation::RuntimeClassInitialize(HSTRING__ *,HSTRING__ *,_AUTH_BROKER_CLIENT_CONTEXT *,uint,int,Windows::Security::Authentication::Web::WebAuthenticationOptions)

- ea: `0x18001a9e0`
- end: `0x18001ab63`
- name: `?RuntimeClassInitialize@CWebAuthOperation@Web@Authentication@Security@Windows@@QEAAJPEAUHSTRING__@@0PEAU_AUTH_BROKER_CLIENT_CONTEXT@@IHW4WebAuthenticationOptions@2345@@Z`
- size: `387`
- prototype: `HRESULT __fastcall(Windows::Security::Authentication::Web::CWebAuthOperation *this, HSTRING__ *TargetUri, HSTRING__ *EndUri, _AUTH_BROKER_CLIENT_CONTEXT *ClientContext, unsigned int BrokerFlags, int UseSsoAppContainer, Windows::Security::Authentication::Web::WebAuthenticationOptions options)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800161c0`

## callees

- `0x1800045c0`
- `0x1800060b8`
- `0x180008068`
- `0x18000e300`
- `0x18000f34c`
- `0x180012b88`
- `0x180015cd8`
- `0x18001a9e0`
- `0x18001af68`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001aad8`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001aad8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aaea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aaea`

## pseudocode

```c
__int64 __fastcall Windows::Security::Authentication::Web::CWebAuthOperation::RuntimeClassInitialize(
        Windows::Security::Authentication::Web::CWebAuthOperation *this,
        HSTRING__ *TargetUri,
        HSTRING__ *EndUri,
        _AUTH_BROKER_CLIENT_CONTEXT *ClientContext,
        unsigned int BrokerFlags,
        int UseSsoAppContainer,
        Windows::Security::Authentication::Web::WebAuthenticationOptions options)
{
  WebAuthBridgeTelemetry::WamBridgeBrokerActivity *p_m_WamBridgeBrokerActivity; // rsi
  signed int v10; // ebx
  __int64 v11; // rdx
  const _GUID *v12; // r8
  _AUTH_BROKER_CLIENT_CONTEXT *m_ClientContext; // rdx
  unsigned int v14; // ecx
  Windows::Security::Authentication::Web::WebAuthenticationOptions v15; // eax
  HANDLE Event; // rax
  signed int LastError; // eax
  TraceLoggingThreadActivity<&g_hMyWABTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider> *v18; // rax
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (__cdecl*)(void *),&LocalFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > packageName; // [rsp+50h] [rbp+8h] BYREF
  HSTRING__ *other; // [rsp+58h] [rbp+10h] BYREF
  HSTRING__ *v22; // [rsp+60h] [rbp+18h] BYREF
  wchar_t *m_ptr; // [rsp+68h] [rbp+20h] BYREF

  v22 = EndUri;
  other = TargetUri;
  p_m_WamBridgeBrokerActivity = &this->m_WamBridgeBrokerActivity;
  WebAuthBridgeTelemetry::WamBridgeBrokerActivity::StartActivity(&this->m_WamBridgeBrokerActivity);
  v10 = 0;
  *(_QWORD *)&this->m_ResponseStatus = 1;
  this->hrThreadInit = 0;
  this->m_ResponseHr = 0;
  Windows::Internal::String::Initialize(&this->m_TargetUri, &other);
  Windows::Internal::String::Initialize(&this->m_EndUri, &v22);
  this->m_WebAuthActivity = 0;
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &this->m_MutexHandle,
    0);
  this->m_ClientContext = ClientContext;
  AddRefAuthBrokerClientContext(ClientContext, v11, v12);
  m_ClientContext = this->m_ClientContext;
  packageName.m_ptr = 0;
  if ( (int)GetAuthBrokerClientAppContainerStringInfo(2, m_ClientContext->tokenHandle, &packageName.m_ptr) >= 0 )
  {
    m_ptr = packageName.m_ptr;
    WebAuthBridgeTelemetry::WamBridgeBrokerActivity::CallingAppPackageName<unsigned short *>(
      p_m_WamBridgeBrokerActivity,
      (const wchar_t *const *)&m_ptr);
  }
  v14 = BrokerFlags;
  v15 = options;
  this->m_BrokerFlags = BrokerFlags;
  this->m_WebAuthOptions = v15;
  this->m_BrokerFlags = v14 | LOWORD(ClientContext->flags);
  this->m_UseSsoAppContainer = UseSsoAppContainer;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  this->m_hThreadReady = Event;
  if ( !Event )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
  }
  v18 = (TraceLoggingThreadActivity<&g_hMyWABTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider> *)operator new(0x28u, &std::nothrow);
  if ( v18 )
  {
    v18->m_State = TlgStateCreated;
    v18->m_HasRelatedId = 0;
    this->m_WebAuthActivity = v18;
    if ( v10 >= 0 )
      v10 = this->Start(&this->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > > >);
  }
  else
  {
    this->m_WebAuthActivity = 0;
    v10 = -2147024882;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&packageName);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001a9e0  mov     [rsp+arg_10], EndUri
0x18001a9e5  mov     [rsp+other], TargetUri
0x18001a9ea  push    rbx
0x18001a9eb  push    rbp
0x18001a9ec  push    rsi
0x18001a9ed  push    rdi
0x18001a9ee  sub     rsp, 28h
0x18001a9f2  lea     rsi, [this+118h]
0x18001a9f9  mov     rdi, this
0x18001a9fc  mov     this, rsi; this
0x18001a9ff  mov     rbp, ClientContext
0x18001aa02  call    ?StartActivity@WamBridgeBrokerActivity@WebAuthBridgeTelemetry@@QEAAXXZ; WebAuthBridgeTelemetry::WamBridgeBrokerActivity::StartActivity(void)
0x18001aa07  xor     ebx, ebx
0x18001aa09  mov     qword ptr [rdi+0E4h], 1
0x18001aa14  lea     this, [rdi+0C8h]; this
0x18001aa1b  mov     [rdi+0B8h], ebx
0x18001aa21  lea     TargetUri, [rsp+48h+other]; other
0x18001aa26  mov     [rdi+0E0h], ebx
0x18001aa2c  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x18001aa31  lea     this, [rdi+0D0h]; this
0x18001aa38  lea     TargetUri, [rsp+48h+arg_10]; other
0x18001aa3d  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x18001aa42  lea     this, [rdi+108h]; this
0x18001aa49  mov     [rdi+0C0h], rbx
0x18001aa50  xor     edx, edx; ptr
0x18001aa52  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001aa57  mov     this, rbp; clientContext
0x18001aa5a  mov     [rdi+0F0h], rbp
0x18001aa61  call    ?AddRefAuthBrokerClientContext@@YAXPEAU_AUTH_BROKER_CLIENT_CONTEXT@@@Z; AddRefAuthBrokerClientContext(_AUTH_BROKER_CLIENT_CONTEXT *)
0x18001aa66  mov     TargetUri, [rdi+0F0h]
0x18001aa6d  lea     EndUri, [rsp+48h+packageName]; string
0x18001aa72  mov     [rsp+48h+packageName.m_ptr], rbx
0x18001aa77  lea     ecx, [rbx+2]; infoType
0x18001aa7a  mov     TargetUri, [TargetUri+20h]; clientTokenHandle
0x18001aa7e  call    ?GetAuthBrokerClientAppContainerStringInfo@@YAJW4ClientAppContainerStringInfoType@@PEAXPEAPEAG@Z; GetAuthBrokerClientAppContainerStringInfo(ClientAppContainerStringInfoType,void *,ushort * *)
0x18001aa83  test    eax, eax
0x18001aa85  js      short loc_18001AA9E
0x18001aa87  mov     rax, [rsp+48h+packageName.m_ptr]
0x18001aa8c  lea     TargetUri, [rsp+48h+arg_18]; packageName
0x18001aa91  mov     this, rsi; this
0x18001aa94  mov     [rsp+48h+arg_18], rax
0x18001aa99  call    ??$CallingAppPackageName@PEAG@WamBridgeBrokerActivity@WebAuthBridgeTelemetry@@QEAAX$$QEAPEAG@Z; WebAuthBridgeTelemetry::WamBridgeBrokerActivity::CallingAppPackageName<ushort *>(ushort * &&)
0x18001aa9e  mov     ecx, [rsp+48h+arg_20]
0x18001aaa2  mov     r9d, 1F0003h; dwDesiredAccess
0x18001aaa8  mov     eax, [rsp+48h+arg_30]
0x18001aaaf  xor     r8d, r8d; dwFlags
0x18001aab2  mov     [rdi+0FCh], ecx
0x18001aab8  xor     edx, edx; lpName
0x18001aaba  mov     [rdi+104h], eax
0x18001aac0  movzx   eax, word ptr [rbp+4]
0x18001aac4  or      eax, ecx
0x18001aac6  xor     ecx, ecx; lpEventAttributes
0x18001aac8  mov     [rdi+0FCh], eax
0x18001aace  mov     eax, [rsp+48h+arg_28]
0x18001aad2  mov     [rdi+100h], eax
0x18001aad8  call    cs:__imp_CreateEventExW
0x18001aade  mov     [rdi+0B0h], rax
0x18001aae5  test    rax, rax
0x18001aae8  jnz     short loc_18001AAFF
0x18001aaea  call    cs:__imp_GetLastError
0x18001aaf0  mov     ebx, eax
0x18001aaf2  test    eax, eax
0x18001aaf4  jle     short loc_18001AAFF
0x18001aaf6  movzx   ebx, ax
0x18001aaf9  or      ebx, 80070000h
0x18001aaff  lea     TargetUri, ?nothrow@std@@3Unothrow_t@1@B; __formal
0x18001ab06  mov     ecx, 28h ; '('; count
0x18001ab0b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001ab10  test    rax, rax
0x18001ab13  jz      short loc_18001AB3E
0x18001ab15  mov     dword ptr [rax], 0
0x18001ab1b  mov     byte ptr [rax+4], 0
0x18001ab1f  mov     [rdi+0C0h], rax
0x18001ab26  test    ebx, ebx
0x18001ab28  js      short loc_18001AB4E
0x18001ab2a  lea     this, [rdi+10h]
0x18001ab2e  mov     rax, [this]
0x18001ab31  mov     rax, [rax+68h]
0x18001ab35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab3a  mov     ebx, eax
0x18001ab3c  jmp     short loc_18001AB4E
0x18001ab3e  mov     qword ptr [rdi+0C0h], 0
0x18001ab49  mov     ebx, 8007000Eh
0x18001ab4e  lea     this, [rsp+48h+packageName]; this
0x18001ab53  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001ab58  mov     eax, ebx
0x18001ab5a  add     rsp, 28h
0x18001ab5e  pop     rdi
0x18001ab5f  pop     rsi
0x18001ab60  pop     rbp
0x18001ab61  pop     rbx
0x18001ab62  retn
```
