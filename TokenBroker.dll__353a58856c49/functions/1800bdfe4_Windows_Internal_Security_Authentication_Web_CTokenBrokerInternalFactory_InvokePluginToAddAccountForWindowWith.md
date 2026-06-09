# Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::InvokePluginToAddAccountForWindowWithPropertiesAsyncInternal(IUnknown *,uint,Windows::Security::Credentials::IWebAccountProvider *,Windows::Foundation::Collections::IPropertySet *,Windows::Foundation::IAsyncAction * *)

- ea: `0x1800bdfe4`
- end: `0x1800be56f`
- name: `?InvokePluginToAddAccountForWindowWithPropertiesAsyncInternal@CTokenBrokerInternalFactory@Web@Authentication@Security@Internal@Windows@@AEAAJPEAUIUnknown@@IPEAUIWebAccountProvider@Credentials@46@PEAUIPropertySet@Collections@Foundation@6@PEAPEAUIAsyncAction@Foundation@6@@Z`
- size: `1419`
- prototype: `int(Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory *__hidden this, struct IUnknown *, unsigned int, struct Windows::Security::Credentials::IWebAccountProvider *, struct Windows::Foundation::Collections::IPropertySet *, struct Windows::Foundation::IAsyncAction **)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800bdf00`
- `0x1800bdf70`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x18000bd70`
- `0x180010a70`
- `0x18001e700`
- `0x180020c60`
- `0x180021750`
- `0x180023a80`
- `0x180024000`
- `0x180024118`
- `0x18002ea84`
- `0x18002fbf0`
- `0x1800372d0`
- `0x180040980`
- `0x1800455a4`
- `0x180056174`
- `0x18005f394`
- `0x18008e690`
- `0x1800b687c`
- `0x1800b7ccc`
- `0x1800b9628`
- `0x1800ba418`
- `0x1800bdfe4`
- `0x1800c3f38`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800be2d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800be2d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be33e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be485`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be505`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be33e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be485`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be505`

## string_xrefs

- `0x1800be07b`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800be0c1`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800be106`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800be16a`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800be1d2`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800be24e`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800be322`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800be445`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800be051`: `Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::InvokePluginToAddAccountForWindowWithPropertiesAsyncInternal`
- `0x1800be01b`: `TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::InvokePluginToAddAccountForWindowWithPropertiesAsyncInternal(
        Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory *this,
        struct IUnknown *a2,
        int a3,
        struct Windows::Security::Credentials::IWebAccountProvider *a4,
        struct Windows::Foundation::Collections::IPropertySet *a5,
        struct Windows::Foundation::IAsyncAction **a6)
{
  __int64 v9; // rcx
  __int64 v11; // rdx
  Windows::Internal::Security::Authentication::Web::CallerContext *v12; // rax
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // eax
  const struct _tlgProvider_t *v16; // rbx
  int v17; // r9d
  __int64 v18; // rax
  __int64 v19; // r8
  int v20; // ebx
  int v21; // [rsp+20h] [rbp-398h]
  int v22; // [rsp+20h] [rbp-398h]
  int v23; // [rsp+40h] [rbp-378h] BYREF
  int v24[2]; // [rsp+48h] [rbp-370h] BYREF
  HSTRING string; // [rsp+50h] [rbp-368h] BYREF
  _BYTE v26[8]; // [rsp+58h] [rbp-360h] BYREF
  __int64 v27; // [rsp+60h] [rbp-358h]
  Windows::Internal::Security::Authentication::Web::CallerContext *v28; // [rsp+68h] [rbp-350h] BYREF
  std::_Ref_count_base *v29; // [rsp+70h] [rbp-348h]
  struct Windows::Foundation::Collections::IPropertySet *v30; // [rsp+78h] [rbp-340h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp-338h] BYREF
  char v32; // [rsp+88h] [rbp-330h]
  int v33; // [rsp+90h] [rbp-328h] BYREF
  __int64 v34; // [rsp+94h] [rbp-324h]
  void *v35[2]; // [rsp+A0h] [rbp-318h] BYREF
  _QWORD v36[34]; // [rsp+B0h] [rbp-308h] BYREF
  __int64 v37; // [rsp+1C0h] [rbp-1F8h]
  _BYTE v38[400]; // [rsp+200h] [rbp-1B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+0h]

  v23 = a3;
  wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v36,
    "TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties");
  v36[0] = &TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties::`vftable';
  TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties::StartActivity((TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties *)v36);
  Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(
    v9,
    (__int64)v26,
    a2,
    "Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::InvokePluginToAddAccountForWindowWith"
    "PropertiesAsyncInternal",
    0);
  if ( !a6 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x867,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v21);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v26);
    TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties::~TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties((TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties *)v36);
    return 2147942487LL;
  }
  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x868,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v21);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v26);
    TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties::~TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties((TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties *)v36);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x869,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v21);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v26);
    TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties::~TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties((TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties *)v36);
    return 2147942487LL;
  }
  v11 = v27;
  v27 = 0;
  std::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>(
    &v28,
    v11);
  v12 = v28;
  if ( !v28 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x86C,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x8007000ELL,
      v21);
    if ( v29 )
      std::_Ref_count_base::_Decref(v29);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v26);
    TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties::~TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties((TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties *)v36);
    return 2147942414LL;
  }
  if ( !*(_BYTE *)v28 )
  {
    v13 = Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(v28, a2, 0, 0);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x86F,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
        (const char *)(unsigned int)v13,
        v21);
      if ( v29 )
        std::_Ref_count_base::_Decref(v29);
LABEL_15:
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v26);
      TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties::~TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties((TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties *)v36);
      return v14;
    }
    v12 = v28;
  }
  TokenHandle = 0;
  v32 = 0;
  v15 = Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(
          &TokenHandle,
          *((_QWORD *)v12 + 2));
  v14 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x873,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v15,
      v21);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    if ( v29 )
      std::_Ref_count_base::_Decref(v29);
    goto LABEL_15;
  }
  string = 0;
  if ( !(*(unsigned int (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *, HSTRING *))(*(_QWORD *)a4 + 48LL))(
          a4,
          &string) )
  {
    v16 = TbLogProvider::Provider();
    if ( *(_DWORD *)v16 > 5u )
    {
      *(_QWORD *)v24 = WindowsGetStringRawBuffer(string, 0);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v16,
        (unsigned int)&word_18014E65E,
        v37 + 8,
        v17,
        (__int64)v24);
    }
  }
  if ( Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer(v28) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x880,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070005LL,
      v21);
    if ( string )
      WindowsDeleteString(string);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    if ( v29 )
      std::_Ref_count_base::_Decref(v29);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v26);
    TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties::~TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties((TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties *)v36);
    return 2147942405LL;
  }
  else
  {
    *(_QWORD *)v24 = a4;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v24);
    v30 = a5;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v30);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::AsyncImpersonator(v35);
    v18 = lambda_93a84700f30b8480d77e105bfc0ae1b3_::_lambda_93a84700f30b8480d77e105bfc0ae1b3__0(
            (unsigned int)v38,
            (unsigned int)v35,
            (unsigned int)v36,
            (unsigned int)&v23,
            (__int64)v24,
            (__int64)&v30,
            (__int64)&v28);
    v33 = 3;
    v34 = 128;
    v20 = Windows::Internal::MakeAsyncAction_Microsoft::WRL::AsyncCausalityOptions__Windows::Internal::Security::Authentication::Web::AddAccountAsyncActionName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows::Internal::ComTaskPoolHandler__lambda_93a84700f30b8480d77e105bfc0ae1b3___(
            &v33,
            a6,
            v19,
            v18);
    lambda_93a84700f30b8480d77e105bfc0ae1b3_::__lambda_93a84700f30b8480d77e105bfc0ae1b3_((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)v38);
    if ( v20 >= 0 )
    {
      wil::ActivityBase<WamClientLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(v36);
      Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)v35);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v24);
      if ( string )
        WindowsDeleteString(string);
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
      if ( v29 )
        std::_Ref_count_base::_Decref(v29);
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v26);
      TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties::~TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties((TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties *)v36);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x89A,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
        (const char *)(unsigned int)v20,
        v22);
      Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)v35);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v24);
      if ( string )
        WindowsDeleteString(string);
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
      if ( v29 )
        std::_Ref_count_base::_Decref(v29);
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v26);
      TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties::~TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties((TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties *)v36);
      return (unsigned int)v20;
    }
  }
}

```

## disassembly

```asm
0x1800bdfe4  mov     [rsp+arg_0], rbx
0x1800bdfe9  push    rsi
0x1800bdfea  push    rdi
0x1800bdfeb  push    r14
0x1800bdfed  sub     rsp, 3A0h
0x1800bdff4  mov     rax, cs:__security_cookie
0x1800bdffb  xor     rax, rsp
0x1800bdffe  mov     [rsp+3B8h+var_28], rax
0x1800be006  mov     rdi, r9
0x1800be009  mov     ebx, r8d
0x1800be00c  mov     rsi, rdx
0x1800be00f  mov     [rsp+3B8h+var_378], ebx
0x1800be013  mov     r14, [rsp+3B8h+arg_28]
0x1800be01b  lea     rdx, aTokenbrokerint_20; "TokenBrokerInternalInvokePluginToAddAcc"...
0x1800be022  lea     rcx, [rsp+3B8h+var_308]
0x1800be02a  call    ??0?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800be02f  lea     rax, ??_7TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties::`vftable'
0x1800be036  mov     [rsp+3B8h+var_308], rax
0x1800be03e  lea     rcx, [rsp+3B8h+var_308]; this
0x1800be046  call    ?StartActivity@TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties@TbLogProvider@@QEAAXXZ; TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties::StartActivity(void)
0x1800be04b  nop
0x1800be04c  mov     byte ptr [rsp+3B8h+var_398], 0; int
0x1800be051  lea     r9, aWindowsInterna_1; "Windows::Internal::Security::Authentica"...
0x1800be058  mov     r8, rsi
0x1800be05b  lea     rdx, [rsp+3B8h+var_360]
0x1800be060  call    ?ProfileCaller@CWamCallerProfiler@Web@Authentication@Security@Internal@Windows@@QEAA?AVCWamProfilerThreadScope@23456@PEAUIUnknown@@PEBD_N@Z; Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(IUnknown *,char const *,bool)
0x1800be065  nop
0x1800be066  test    r14, r14
0x1800be069  jnz     short loc_1800BE0AC
0x1800be06b  mov     rcx, [rsp+3B8h]; this
0x1800be073  mov     ebx, 80070057h
0x1800be078  mov     r9d, ebx; char *
0x1800be07b  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800be082  mov     edx, 867h; void *
0x1800be087  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be08c  nop
0x1800be08d  lea     rcx, [rsp+3B8h+var_360]; this
0x1800be092  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800be097  nop
0x1800be098  lea     rcx, [rsp+3B8h+var_308]; this
0x1800be0a0  call    ??1TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties::~TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties(void)
0x1800be0a5  mov     eax, ebx
0x1800be0a7  jmp     loc_1800BE54A
0x1800be0ac  test    rdi, rdi
0x1800be0af  jnz     short loc_1800BE0F2
0x1800be0b1  mov     rcx, [rsp+3B8h]; this
0x1800be0b9  mov     ebx, 80070057h
0x1800be0be  mov     r9d, ebx; char *
0x1800be0c1  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800be0c8  mov     edx, 868h; void *
0x1800be0cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be0d2  nop
0x1800be0d3  lea     rcx, [rsp+3B8h+var_360]; this
0x1800be0d8  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800be0dd  nop
0x1800be0de  lea     rcx, [rsp+3B8h+var_308]; this
0x1800be0e6  call    ??1TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties::~TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties(void)
0x1800be0eb  mov     eax, ebx
0x1800be0ed  jmp     loc_1800BE54A
0x1800be0f2  test    ebx, ebx
0x1800be0f4  jnz     short loc_1800BE137
0x1800be0f6  mov     rcx, [rsp+3B8h]; this
0x1800be0fe  mov     ebx, 80070057h
0x1800be103  mov     r9d, ebx; char *
0x1800be106  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800be10d  mov     edx, 869h; void *
0x1800be112  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be117  nop
0x1800be118  lea     rcx, [rsp+3B8h+var_360]; this
0x1800be11d  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800be122  nop
0x1800be123  lea     rcx, [rsp+3B8h+var_308]; this
0x1800be12b  call    ??1TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties::~TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties(void)
0x1800be130  mov     eax, ebx
0x1800be132  jmp     loc_1800BE54A
0x1800be137  mov     rdx, [rsp+3B8h+var_358]
0x1800be13c  mov     [rsp+3B8h+var_358], 0
0x1800be145  lea     rcx, [rsp+3B8h+var_350]
0x1800be14a  call    ??$?0VCallerContext@Web@Authentication@Security@Internal@Windows@@$0A@@?$shared_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@@std@@QEAA@PEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; std::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x1800be14f  nop
0x1800be150  mov     rax, [rsp+3B8h+var_350]
0x1800be155  test    rax, rax
0x1800be158  jnz     short loc_1800BE1AB
0x1800be15a  mov     rcx, [rsp+3B8h]; this
0x1800be162  mov     ebx, 8007000Eh
0x1800be167  mov     r9d, ebx; char *
0x1800be16a  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800be171  mov     edx, 86Ch; void *
0x1800be176  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be17b  nop
0x1800be17c  mov     rcx, [rsp+3B8h+var_348]; this
0x1800be181  test    rcx, rcx
0x1800be184  jz      short loc_1800BE18C
0x1800be186  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800be18b  nop
0x1800be18c  lea     rcx, [rsp+3B8h+var_360]; this
0x1800be191  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800be196  nop
0x1800be197  lea     rcx, [rsp+3B8h+var_308]; this
0x1800be19f  call    ??1TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties::~TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties(void)
0x1800be1a4  mov     eax, ebx
0x1800be1a6  jmp     loc_1800BE54A
0x1800be1ab  cmp     byte ptr [rax], 0
0x1800be1ae  jnz     short loc_1800BE218
0x1800be1b0  xor     r9d, r9d; bool
0x1800be1b3  xor     r8d, r8d; unsigned __int64
0x1800be1b6  mov     rdx, rsi; struct IUnknown *
0x1800be1b9  mov     rcx, rax; this
0x1800be1bc  call    ?Initialize@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUnknown@@_K_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(IUnknown *,unsigned __int64,bool)
0x1800be1c1  mov     ebx, eax
0x1800be1c3  test    eax, eax
0x1800be1c5  jns     short loc_1800BE213
0x1800be1c7  mov     rcx, [rsp+3B8h]; this
0x1800be1cf  mov     r9d, eax; char *
0x1800be1d2  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800be1d9  mov     edx, 86Fh; void *
0x1800be1de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be1e3  nop
0x1800be1e4  mov     rcx, [rsp+3B8h+var_348]; this
0x1800be1e9  test    rcx, rcx
0x1800be1ec  jz      short loc_1800BE1F4
0x1800be1ee  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800be1f3  nop
0x1800be1f4  lea     rcx, [rsp+3B8h+var_360]; this
0x1800be1f9  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800be1fe  nop
0x1800be1ff  lea     rcx, [rsp+3B8h+var_308]; this
0x1800be207  call    ??1TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties::~TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties(void)
0x1800be20c  mov     eax, ebx
0x1800be20e  jmp     loc_1800BE54A
0x1800be213  mov     rax, [rsp+3B8h+var_350]
0x1800be218  mov     [rsp+3B8h+TokenHandle], 0
0x1800be224  mov     [rsp+3B8h+var_330], 0
0x1800be22c  mov     rdx, [rax+10h]; unsigned __int64
0x1800be230  lea     rcx, [rsp+3B8h+TokenHandle]; TokenHandle
0x1800be238  call    ?Impersonate@ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAAJ_K@Z; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(unsigned __int64)
0x1800be23d  mov     ebx, eax
0x1800be23f  test    eax, eax
0x1800be241  jns     short loc_1800BE29D
0x1800be243  mov     rcx, [rsp+3B8h]; this
0x1800be24b  mov     r9d, eax; char *
0x1800be24e  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800be255  mov     edx, 873h; void *
0x1800be25a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be25f  nop
0x1800be260  lea     rcx, [rsp+3B8h+TokenHandle]; this
0x1800be268  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800be26d  nop
0x1800be26e  mov     rcx, [rsp+3B8h+var_348]; this
0x1800be273  test    rcx, rcx
0x1800be276  jz      short loc_1800BE27E
0x1800be278  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800be27d  nop
0x1800be27e  lea     rcx, [rsp+3B8h+var_360]; this
0x1800be283  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800be288  nop
0x1800be289  lea     rcx, [rsp+3B8h+var_308]; this
0x1800be291  call    ??1TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties::~TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties(void)
0x1800be296  mov     eax, ebx
0x1800be298  jmp     loc_1800BE54A
0x1800be29d  mov     [rsp+3B8h+string], 0
0x1800be2a6  mov     rax, [rdi]
0x1800be2a9  lea     rdx, [rsp+3B8h+string]
0x1800be2ae  mov     rcx, rdi
0x1800be2b1  mov     rax, [rax+30h]
0x1800be2b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be2ba  test    eax, eax
0x1800be2bc  jnz     short loc_1800BE304
0x1800be2be  call    ?Provider@TbLogProvider@@SAPEBU_tlgProvider_t@@XZ; TbLogProvider::Provider(void)
0x1800be2c3  mov     rbx, rax
0x1800be2c6  mov     ecx, [rax]
0x1800be2c8  cmp     ecx, 5
0x1800be2cb  jbe     short loc_1800BE304
0x1800be2cd  xor     edx, edx; length
0x1800be2cf  mov     rcx, [rsp+3B8h+string]; string
0x1800be2d4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800be2da  mov     qword ptr [rsp+3B8h+var_370], rax
0x1800be2df  mov     r8, [rsp+3B8h+var_1F8]
0x1800be2e7  add     r8, 8
0x1800be2eb  lea     rax, [rsp+3B8h+var_370]
0x1800be2f0  mov     qword ptr [rsp+3B8h+var_398], rax; int
0x1800be2f5  lea     rdx, word_18014E65E
0x1800be2fc  mov     rcx, rbx
0x1800be2ff  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800be304  mov     rcx, [rsp+3B8h+var_350]; this
0x1800be309  call    ?IsCallerAppContainer@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBA_NXZ; Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer(void)
0x1800be30e  test    al, al
0x1800be310  jz      short loc_1800BE382
0x1800be312  mov     rcx, [rsp+3B8h]; this
0x1800be31a  mov     ebx, 80070005h
0x1800be31f  mov     r9d, ebx; char *
0x1800be322  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800be329  mov     edx, 880h; void *
0x1800be32e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be333  nop
0x1800be334  mov     rcx, [rsp+3B8h+string]; string
0x1800be339  test    rcx, rcx
0x1800be33c  jz      short loc_1800BE345
0x1800be33e  call    cs:__imp_WindowsDeleteString
0x1800be344  nop
0x1800be345  lea     rcx, [rsp+3B8h+TokenHandle]; this
0x1800be34d  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800be352  nop
0x1800be353  mov     rcx, [rsp+3B8h+var_348]; this
0x1800be358  test    rcx, rcx
0x1800be35b  jz      short loc_1800BE363
0x1800be35d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800be362  nop
0x1800be363  lea     rcx, [rsp+3B8h+var_360]; this
0x1800be368  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800be36d  nop
0x1800be36e  lea     rcx, [rsp+3B8h+var_308]; this
0x1800be376  call    ??1TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties::~TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties(void)
0x1800be37b  mov     eax, ebx
0x1800be37d  jmp     loc_1800BE54A
0x1800be382  mov     qword ptr [rsp+3B8h+var_370], rdi
0x1800be387  lea     rcx, [rsp+3B8h+var_370]
0x1800be38c  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800be391  nop
0x1800be392  mov     rax, [rsp+3B8h+arg_20]
0x1800be39a  mov     [rsp+3B8h+var_340], rax
0x1800be39f  lea     rcx, [rsp+3B8h+var_340]
0x1800be3a4  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800be3a9  nop
0x1800be3aa  lea     rcx, [rsp+3B8h+var_318]; TokenHandle
0x1800be3b2  call    ??0AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::AsyncImpersonator(void)
0x1800be3b7  nop
0x1800be3b8  lea     rax, [rsp+3B8h+var_350]
0x1800be3bd  mov     [rsp+3B8h+var_388], rax
0x1800be3c2  lea     rax, [rsp+3B8h+var_340]
0x1800be3c7  mov     [rsp+3B8h+var_390], rax
0x1800be3cc  lea     rax, [rsp+3B8h+var_370]
0x1800be3d1  mov     qword ptr [rsp+3B8h+var_398], rax; int
0x1800be3d6  lea     r9, [rsp+3B8h+var_378]
0x1800be3db  lea     r8, [rsp+3B8h+var_308]
0x1800be3e3  lea     rdx, [rsp+3B8h+var_318]
0x1800be3eb  lea     rcx, [rsp+3B8h+var_1B8]
0x1800be3f3  call    _lambda_93a84700f30b8480d77e105bfc0ae1b3____lambda_93a84700f30b8480d77e105bfc0ae1b3__0
0x1800be3f8  nop
0x1800be3f9  mov     [rsp+3B8h+var_328], 3
0x1800be404  mov     [rsp+3B8h+var_324], 80h
0x1800be410  mov     r9, rax
0x1800be413  mov     rdx, r14
0x1800be416  lea     rcx, [rsp+3B8h+var_328]
0x1800be41e  call    Windows__Internal__MakeAsyncAction_Microsoft__WRL__AsyncCausalityOptions__Windows__Internal__Security__Authentication__Web__AddAccountAsyncActionName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows__Internal__ComTaskPoolHandler__lambda_93a84700f30b8480d77e105bfc0ae1b3___
0x1800be423  mov     ebx, eax
0x1800be425  lea     rcx, [rsp+3B8h+var_1B8]; this
0x1800be42d  call    _lambda_93a84700f30b8480d77e105bfc0ae1b3_____lambda_93a84700f30b8480d77e105bfc0ae1b3_
0x1800be432  test    ebx, ebx
0x1800be434  jns     loc_1800BE4C9
0x1800be43a  mov     rcx, [rsp+3B8h]; this
0x1800be442  mov     r9d, ebx; char *
0x1800be445  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800be44c  mov     edx, 89Ah; void *
0x1800be451  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be456  nop
0x1800be457  lea     rcx, [rsp+3B8h+var_318]; this
0x1800be45f  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x1800be464  nop
0x1800be465  lea     rcx, [rsp+3B8h+var_340]
0x1800be46a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800be46f  nop
0x1800be470  lea     rcx, [rsp+3B8h+var_370]
0x1800be475  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800be47a  nop
0x1800be47b  mov     rcx, [rsp+3B8h+string]; string
0x1800be480  test    rcx, rcx
0x1800be483  jz      short loc_1800BE48C
0x1800be485  call    cs:__imp_WindowsDeleteString
0x1800be48b  nop
0x1800be48c  lea     rcx, [rsp+3B8h+TokenHandle]; this
0x1800be494  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800be499  nop
0x1800be49a  mov     rcx, [rsp+3B8h+var_348]; this
0x1800be49f  test    rcx, rcx
0x1800be4a2  jz      short loc_1800BE4AA
0x1800be4a4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800be4a9  nop
0x1800be4aa  lea     rcx, [rsp+3B8h+var_360]; this
0x1800be4af  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800be4b4  nop
0x1800be4b5  lea     rcx, [rsp+3B8h+var_308]; this
0x1800be4bd  call    ??1TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties::~TokenBrokerInternalInvokePluginToAddAccountForWindowWithProperties(void)
0x1800be4c2  mov     eax, ebx
0x1800be4c4  jmp     loc_1800BE54A
0x1800be4c9  lea     rcx, [rsp+3B8h+var_308]
0x1800be4d1  call    ?IgnoreCurrentThread@?$ActivityBase@VWamClientLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WamClientLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x1800be4d6  nop
0x1800be4d7  lea     rcx, [rsp+3B8h+var_318]; this
0x1800be4df  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x1800be4e4  nop
0x1800be4e5  lea     rcx, [rsp+3B8h+var_340]
0x1800be4ea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800be4ef  nop
0x1800be4f0  lea     rcx, [rsp+3B8h+var_370]
0x1800be4f5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800be4fa  nop
0x1800be4fb  mov     rcx, [rsp+3B8h+string]; string
0x1800be500  test    rcx, rcx
0x1800be503  jz      short loc_1800BE50C
  ... truncated ...
```
