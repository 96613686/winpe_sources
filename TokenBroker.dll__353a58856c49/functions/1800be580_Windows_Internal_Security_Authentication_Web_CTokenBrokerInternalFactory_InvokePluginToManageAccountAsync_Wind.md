# Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::InvokePluginToManageAccountAsync(Windows::Security::Credentials::IWebAccount *,Windows::Foundation::IAsyncAction * *)

- ea: `0x1800be580`
- end: `0x1800bebcc`
- name: `?InvokePluginToManageAccountAsync@CTokenBrokerInternalFactory@Web@Authentication@Security@Internal@Windows@@UEAAJPEAUIWebAccount@Credentials@46@PEAPEAUIAsyncAction@Foundation@6@@Z`
- size: `1612`
- prototype: `int(Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory *__hidden this, struct Windows::Security::Credentials::IWebAccount *, struct Windows::Foundation::IAsyncAction **)`
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

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
- `0x180057440`
- `0x18005f394`
- `0x18008169c`
- `0x18008e690`
- `0x1800b69ac`
- `0x1800b780c`
- `0x1800b9550`
- `0x1800ba444`
- `0x1800be580`
- `0x1800c3fd0`
- `0x1800e5718`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800be8b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800be8b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be928`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be9c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800beaeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800beb65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be928`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be9c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800beaeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800beb65`

## string_xrefs

- `0x1800be618`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800be65e`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800be6bc`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800be720`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800be78d`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800be800`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800be901`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800be9a2`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800beaab`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800be5ee`: `Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::InvokePluginToManageAccountAsync`
- `0x1800be5ab`: `TokenBrokerInternalInvokePluginToManageAccount`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::InvokePluginToManageAccountAsync(
        unsigned __int64 this,
        struct Windows::Security::Credentials::IWebAccount *a2,
        struct Windows::Foundation::IAsyncAction **a3)
{
  struct IUnknown *v6; // rsi
  __int64 v7; // rcx
  unsigned __int64 *v8; // r8
  int UserContextFromWebAccount; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  Windows::Internal::Security::Authentication::Web::CallerContext *v13; // rax
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  unsigned int (__fastcall *v17)(struct Windows::Security::Credentials::IWebAccount *, __int64 *); // rbx
  const struct _tlgProvider_t *v18; // rbx
  int v19; // r9d
  HWND *v20; // rdx
  HWND *v21; // r8
  int ClientWindowHandle; // eax
  int v23; // ebx
  __int64 v24; // rax
  __int64 v25; // r8
  int v26; // [rsp+20h] [rbp-388h]
  int v27; // [rsp+20h] [rbp-388h]
  __int64 v28; // [rsp+30h] [rbp-378h] BYREF
  HSTRING string; // [rsp+38h] [rbp-370h] BYREF
  int v30[2]; // [rsp+40h] [rbp-368h] BYREF
  _BYTE v31[8]; // [rsp+48h] [rbp-360h] BYREF
  __int64 v32; // [rsp+50h] [rbp-358h]
  Windows::Internal::Security::Authentication::Web::CallerContext *v33; // [rsp+58h] [rbp-350h] BYREF
  std::_Ref_count_base *v34; // [rsp+60h] [rbp-348h]
  struct IUnknown v35; // [rsp+68h] [rbp-340h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-338h] BYREF
  char v37; // [rsp+78h] [rbp-330h]
  unsigned __int64 v38; // [rsp+80h] [rbp-328h] BYREF
  int v39; // [rsp+88h] [rbp-320h] BYREF
  __int64 v40; // [rsp+8Ch] [rbp-31Ch]
  void *v41[3]; // [rsp+98h] [rbp-310h] BYREF
  _QWORD v42[34]; // [rsp+B0h] [rbp-2F8h] BYREF
  __int64 v43; // [rsp+1C0h] [rbp-1E8h]
  _BYTE v44[384]; // [rsp+200h] [rbp-1A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+0h]

  wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v42,
    "TokenBrokerInternalInvokePluginToManageAccount");
  v42[0] = &TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount::`vftable';
  TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount::StartActivity((TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount *)v42);
  v6 = (struct IUnknown *)(this & -(__int64)(this != 40));
  Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(
    v7,
    (__int64)v31,
    v6,
    "Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::InvokePluginToManageAccountAsync",
    0);
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24B,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v26);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v31);
    TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount::~TokenBrokerInternalInvokePluginToManageAccount((TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount *)v42);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24C,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v26);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v31);
    TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount::~TokenBrokerInternalInvokePluginToManageAccount((TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount *)v42);
    return 2147942487LL;
  }
  v38 = 0;
  UserContextFromWebAccount = Windows::Internal::Security::Authentication::TokenBroker::GetUserContextFromWebAccount(
                                a2,
                                (struct Windows::Security::Credentials::IWebAccount *)&v38,
                                v8);
  v11 = UserContextFromWebAccount;
  if ( UserContextFromWebAccount < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24F,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)UserContextFromWebAccount,
      v26);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v31);
    TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount::~TokenBrokerInternalInvokePluginToManageAccount((TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount *)v42);
    return v11;
  }
  v12 = v32;
  v32 = 0;
  std::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>(
    &v33,
    v12);
  v13 = v33;
  if ( !v33 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x252,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x8007000ELL,
      v26);
    if ( v34 )
      std::_Ref_count_base::_Decref(v34);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v31);
    TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount::~TokenBrokerInternalInvokePluginToManageAccount((TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount *)v42);
    return 2147942414LL;
  }
  if ( !*(_BYTE *)v33 )
  {
    v14 = Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(v33, v6, v38, 0);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x255,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
        (const char *)(unsigned int)v14,
        v26);
      if ( v34 )
        std::_Ref_count_base::_Decref(v34);
LABEL_15:
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v31);
      TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount::~TokenBrokerInternalInvokePluginToManageAccount((TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount *)v42);
      return v15;
    }
    v13 = v33;
  }
  TokenHandle = 0;
  v37 = 0;
  v16 = Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(
          &TokenHandle,
          *((_QWORD *)v13 + 2));
  v15 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x259,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v16,
      v26);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    if ( v34 )
      std::_Ref_count_base::_Decref(v34);
    goto LABEL_15;
  }
  string = 0;
  v28 = 0;
  v17 = *(unsigned int (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *, __int64 *))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  if ( !v17(a2, &v28) && !(*(unsigned int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v28 + 48LL))(v28, &string) )
  {
    v18 = TbLogProvider::Provider();
    if ( *(_DWORD *)v18 > 5u )
    {
      *(_QWORD *)v30 = WindowsGetStringRawBuffer(string, 0);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v18,
        (unsigned int)&byte_18014BC9F,
        v43 + 8,
        v19,
        (__int64)v30);
    }
  }
  if ( Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer(v33) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x268,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070005LL,
      v26);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    if ( string )
      WindowsDeleteString(string);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    if ( v34 )
      std::_Ref_count_base::_Decref(v34);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v31);
    TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount::~TokenBrokerInternalInvokePluginToManageAccount((TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount *)v42);
    return 2147942405LL;
  }
  v35.lpVtbl = 0;
  if ( (int)CallerIdentity::GetCoreWindowHandleForCurrentThread((CallerIdentity *)&v35, v20) < 0 )
  {
    ClientWindowHandle = Windows::Internal::Security::Authentication::TokenBroker::GetClientWindowHandle(
                           (Windows::Internal::Security::Authentication::TokenBroker *)v6,
                           &v35,
                           v21);
    v23 = ClientWindowHandle;
    if ( ClientWindowHandle < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26E,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
        (const char *)(unsigned int)ClientWindowHandle,
        v26);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
      if ( string )
        WindowsDeleteString(string);
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
      if ( v34 )
        std::_Ref_count_base::_Decref(v34);
LABEL_37:
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v31);
      TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount::~TokenBrokerInternalInvokePluginToManageAccount((TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount *)v42);
      return (unsigned int)v23;
    }
  }
  *(_QWORD *)v30 = a2;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v30);
  Windows::Internal::Security::Authentication::Web::AsyncImpersonator::AsyncImpersonator(v41);
  v24 = lambda_4ef58c21b0f4058fd20490411884590d_::_lambda_4ef58c21b0f4058fd20490411884590d__0(
          (unsigned int)v44,
          (unsigned int)v41,
          (unsigned int)v42,
          (unsigned int)&v35,
          (__int64)v30,
          (__int64)&v33);
  v39 = 3;
  v40 = 128;
  v23 = Windows::Internal::MakeAsyncAction_Microsoft::WRL::AsyncCausalityOptions__Windows::Internal::Security::Authentication::Web::ManageAccountAsyncActionName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows::Internal::ComTaskPoolHandler__lambda_4ef58c21b0f4058fd20490411884590d___(
          &v39,
          a3,
          v25,
          v24);
  lambda_4ef58c21b0f4058fd20490411884590d_::__lambda_4ef58c21b0f4058fd20490411884590d_((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)v44);
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x287,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v23,
      v27);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)v41);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    if ( string )
      WindowsDeleteString(string);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    if ( v34 )
      std::_Ref_count_base::_Decref(v34);
    goto LABEL_37;
  }
  wil::ActivityBase<WamClientLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(v42);
  Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)v41);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  if ( string )
    WindowsDeleteString(string);
  Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
  if ( v34 )
    std::_Ref_count_base::_Decref(v34);
  Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v31);
  TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount::~TokenBrokerInternalInvokePluginToManageAccount((TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount *)v42);
  return 0;
}

```

## disassembly

```asm
0x1800be580  mov     [rsp+arg_18], rbx
0x1800be585  push    rsi
0x1800be586  push    rdi
0x1800be587  push    r14
0x1800be589  sub     rsp, 390h
0x1800be590  mov     rax, cs:__security_cookie
0x1800be597  xor     rax, rsp
0x1800be59a  mov     [rsp+3A8h+var_28], rax
0x1800be5a2  mov     r14, r8
0x1800be5a5  mov     rdi, rdx
0x1800be5a8  mov     rbx, rcx
0x1800be5ab  lea     rdx, aTokenbrokerint_16; "TokenBrokerInternalInvokePluginToManage"...
0x1800be5b2  lea     rcx, [rsp+3A8h+var_2F8]
0x1800be5ba  call    ??0?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800be5bf  lea     rax, ??_7TokenBrokerInternalInvokePluginToManageAccount@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount::`vftable'
0x1800be5c6  mov     [rsp+3A8h+var_2F8], rax
0x1800be5ce  lea     rcx, [rsp+3A8h+var_2F8]; this
0x1800be5d6  call    ?StartActivity@TokenBrokerInternalInvokePluginToManageAccount@TbLogProvider@@QEAAXXZ; TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount::StartActivity(void)
0x1800be5db  nop
0x1800be5dc  lea     rax, [rbx-28h]
0x1800be5e0  neg     rax
0x1800be5e3  sbb     rsi, rsi
0x1800be5e6  and     rsi, rbx
0x1800be5e9  mov     byte ptr [rsp+3A8h+var_388], 0; int
0x1800be5ee  lea     r9, aWindowsInterna_70; "Windows::Internal::Security::Authentica"...
0x1800be5f5  mov     r8, rsi
0x1800be5f8  lea     rdx, [rsp+3A8h+var_360]
0x1800be5fd  call    ?ProfileCaller@CWamCallerProfiler@Web@Authentication@Security@Internal@Windows@@QEAA?AVCWamProfilerThreadScope@23456@PEAUIUnknown@@PEBD_N@Z; Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(IUnknown *,char const *,bool)
0x1800be602  nop
0x1800be603  test    r14, r14
0x1800be606  jnz     short loc_1800BE649
0x1800be608  mov     rcx, [rsp+3A8h]; this
0x1800be610  mov     ebx, 80070057h
0x1800be615  mov     r9d, ebx; char *
0x1800be618  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800be61f  mov     edx, 24Bh; void *
0x1800be624  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be629  nop
0x1800be62a  lea     rcx, [rsp+3A8h+var_360]; this
0x1800be62f  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800be634  nop
0x1800be635  lea     rcx, [rsp+3A8h+var_2F8]; this
0x1800be63d  call    ??1TokenBrokerInternalInvokePluginToManageAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount::~TokenBrokerInternalInvokePluginToManageAccount(void)
0x1800be642  mov     eax, ebx
0x1800be644  jmp     loc_1800BEBA7
0x1800be649  test    rdi, rdi
0x1800be64c  jnz     short loc_1800BE68F
0x1800be64e  mov     rcx, [rsp+3A8h]; this
0x1800be656  mov     ebx, 80070057h
0x1800be65b  mov     r9d, ebx; char *
0x1800be65e  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800be665  mov     edx, 24Ch; void *
0x1800be66a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be66f  nop
0x1800be670  lea     rcx, [rsp+3A8h+var_360]; this
0x1800be675  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800be67a  nop
0x1800be67b  lea     rcx, [rsp+3A8h+var_2F8]; this
0x1800be683  call    ??1TokenBrokerInternalInvokePluginToManageAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount::~TokenBrokerInternalInvokePluginToManageAccount(void)
0x1800be688  mov     eax, ebx
0x1800be68a  jmp     loc_1800BEBA7
0x1800be68f  mov     [rsp+3A8h+var_328], 0
0x1800be69b  lea     rdx, [rsp+3A8h+var_328]; struct Windows::Security::Credentials::IWebAccount *
0x1800be6a3  mov     rcx, rdi; this
0x1800be6a6  call    ?GetUserContextFromWebAccount@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIWebAccount@Credentials@35@AEA_K@Z; Windows::Internal::Security::Authentication::TokenBroker::GetUserContextFromWebAccount(Windows::Security::Credentials::IWebAccount *,unsigned __int64 &)
0x1800be6ab  mov     ebx, eax
0x1800be6ad  test    eax, eax
0x1800be6af  jns     short loc_1800BE6ED
0x1800be6b1  mov     rcx, [rsp+3A8h]; this
0x1800be6b9  mov     r9d, eax; char *
0x1800be6bc  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800be6c3  mov     edx, 24Fh; void *
0x1800be6c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be6cd  nop
0x1800be6ce  lea     rcx, [rsp+3A8h+var_360]; this
0x1800be6d3  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800be6d8  nop
0x1800be6d9  lea     rcx, [rsp+3A8h+var_2F8]; this
0x1800be6e1  call    ??1TokenBrokerInternalInvokePluginToManageAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount::~TokenBrokerInternalInvokePluginToManageAccount(void)
0x1800be6e6  mov     eax, ebx
0x1800be6e8  jmp     loc_1800BEBA7
0x1800be6ed  mov     rdx, [rsp+3A8h+var_358]
0x1800be6f2  mov     [rsp+3A8h+var_358], 0
0x1800be6fb  lea     rcx, [rsp+3A8h+var_350]
0x1800be700  call    ??$?0VCallerContext@Web@Authentication@Security@Internal@Windows@@$0A@@?$shared_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@@std@@QEAA@PEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; std::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x1800be705  nop
0x1800be706  mov     rax, [rsp+3A8h+var_350]
0x1800be70b  test    rax, rax
0x1800be70e  jnz     short loc_1800BE761
0x1800be710  mov     rcx, [rsp+3A8h]; this
0x1800be718  mov     ebx, 8007000Eh
0x1800be71d  mov     r9d, ebx; char *
0x1800be720  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800be727  mov     edx, 252h; void *
0x1800be72c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be731  nop
0x1800be732  mov     rcx, [rsp+3A8h+var_348]; this
0x1800be737  test    rcx, rcx
0x1800be73a  jz      short loc_1800BE742
0x1800be73c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800be741  nop
0x1800be742  lea     rcx, [rsp+3A8h+var_360]; this
0x1800be747  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800be74c  nop
0x1800be74d  lea     rcx, [rsp+3A8h+var_2F8]; this
0x1800be755  call    ??1TokenBrokerInternalInvokePluginToManageAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount::~TokenBrokerInternalInvokePluginToManageAccount(void)
0x1800be75a  mov     eax, ebx
0x1800be75c  jmp     loc_1800BEBA7
0x1800be761  cmp     byte ptr [rax], 0
0x1800be764  jnz     short loc_1800BE7D3
0x1800be766  xor     r9d, r9d; bool
0x1800be769  mov     r8, [rsp+3A8h+var_328]; unsigned __int64
0x1800be771  mov     rdx, rsi; struct IUnknown *
0x1800be774  mov     rcx, rax; this
0x1800be777  call    ?Initialize@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUnknown@@_K_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(IUnknown *,unsigned __int64,bool)
0x1800be77c  mov     ebx, eax
0x1800be77e  test    eax, eax
0x1800be780  jns     short loc_1800BE7CE
0x1800be782  mov     rcx, [rsp+3A8h]; this
0x1800be78a  mov     r9d, eax; char *
0x1800be78d  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800be794  mov     edx, 255h; void *
0x1800be799  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be79e  nop
0x1800be79f  mov     rcx, [rsp+3A8h+var_348]; this
0x1800be7a4  test    rcx, rcx
0x1800be7a7  jz      short loc_1800BE7AF
0x1800be7a9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800be7ae  nop
0x1800be7af  lea     rcx, [rsp+3A8h+var_360]; this
0x1800be7b4  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800be7b9  nop
0x1800be7ba  lea     rcx, [rsp+3A8h+var_2F8]; this
0x1800be7c2  call    ??1TokenBrokerInternalInvokePluginToManageAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount::~TokenBrokerInternalInvokePluginToManageAccount(void)
0x1800be7c7  mov     eax, ebx
0x1800be7c9  jmp     loc_1800BEBA7
0x1800be7ce  mov     rax, [rsp+3A8h+var_350]
0x1800be7d3  mov     [rsp+3A8h+TokenHandle], 0
0x1800be7dc  mov     [rsp+3A8h+var_330], 0
0x1800be7e1  mov     rdx, [rax+10h]; unsigned __int64
0x1800be7e5  lea     rcx, [rsp+3A8h+TokenHandle]; TokenHandle
0x1800be7ea  call    ?Impersonate@ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAAJ_K@Z; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(unsigned __int64)
0x1800be7ef  mov     ebx, eax
0x1800be7f1  test    eax, eax
0x1800be7f3  jns     short loc_1800BE84C
0x1800be7f5  mov     rcx, [rsp+3A8h]; this
0x1800be7fd  mov     r9d, eax; char *
0x1800be800  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800be807  mov     edx, 259h; void *
0x1800be80c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be811  nop
0x1800be812  lea     rcx, [rsp+3A8h+TokenHandle]; this
0x1800be817  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800be81c  nop
0x1800be81d  mov     rcx, [rsp+3A8h+var_348]; this
0x1800be822  test    rcx, rcx
0x1800be825  jz      short loc_1800BE82D
0x1800be827  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800be82c  nop
0x1800be82d  lea     rcx, [rsp+3A8h+var_360]; this
0x1800be832  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800be837  nop
0x1800be838  lea     rcx, [rsp+3A8h+var_2F8]; this
0x1800be840  call    ??1TokenBrokerInternalInvokePluginToManageAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount::~TokenBrokerInternalInvokePluginToManageAccount(void)
0x1800be845  mov     eax, ebx
0x1800be847  jmp     loc_1800BEBA7
0x1800be84c  mov     [rsp+3A8h+string], 0
0x1800be855  mov     [rsp+3A8h+var_378], 0
0x1800be85e  mov     rax, [rdi]
0x1800be861  mov     rbx, [rax+30h]
0x1800be865  lea     rcx, [rsp+3A8h+var_378]
0x1800be86a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800be86f  lea     rdx, [rsp+3A8h+var_378]
0x1800be874  mov     rcx, rdi
0x1800be877  mov     rax, rbx
0x1800be87a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be87f  test    eax, eax
0x1800be881  jnz     short loc_1800BE8E3
0x1800be883  mov     rcx, [rsp+3A8h+var_378]
0x1800be888  mov     rax, [rcx]
0x1800be88b  lea     rdx, [rsp+3A8h+string]
0x1800be890  mov     rax, [rax+30h]
0x1800be894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be899  test    eax, eax
0x1800be89b  jnz     short loc_1800BE8E3
0x1800be89d  call    ?Provider@TbLogProvider@@SAPEBU_tlgProvider_t@@XZ; TbLogProvider::Provider(void)
0x1800be8a2  mov     rbx, rax
0x1800be8a5  mov     ecx, [rax]
0x1800be8a7  cmp     ecx, 5
0x1800be8aa  jbe     short loc_1800BE8E3
0x1800be8ac  xor     edx, edx; length
0x1800be8ae  mov     rcx, [rsp+3A8h+string]; string
0x1800be8b3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800be8b9  mov     qword ptr [rsp+3A8h+var_368], rax
0x1800be8be  mov     r8, [rsp+3A8h+var_1E8]
0x1800be8c6  add     r8, 8
0x1800be8ca  lea     rax, [rsp+3A8h+var_368]
0x1800be8cf  mov     qword ptr [rsp+3A8h+var_388], rax; int
0x1800be8d4  lea     rdx, byte_18014BC9F
0x1800be8db  mov     rcx, rbx
0x1800be8de  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800be8e3  mov     rcx, [rsp+3A8h+var_350]; this
0x1800be8e8  call    ?IsCallerAppContainer@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBA_NXZ; Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer(void)
0x1800be8ed  test    al, al
0x1800be8ef  jz      short loc_1800BE969
0x1800be8f1  mov     rcx, [rsp+3A8h]; this
0x1800be8f9  mov     ebx, 80070005h
0x1800be8fe  mov     r9d, ebx; char *
0x1800be901  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800be908  mov     edx, 268h; void *
0x1800be90d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be912  nop
0x1800be913  lea     rcx, [rsp+3A8h+var_378]
0x1800be918  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800be91d  nop
0x1800be91e  mov     rcx, [rsp+3A8h+string]; string
0x1800be923  test    rcx, rcx
0x1800be926  jz      short loc_1800BE92F
0x1800be928  call    cs:__imp_WindowsDeleteString
0x1800be92e  nop
0x1800be92f  lea     rcx, [rsp+3A8h+TokenHandle]; this
0x1800be934  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800be939  nop
0x1800be93a  mov     rcx, [rsp+3A8h+var_348]; this
0x1800be93f  test    rcx, rcx
0x1800be942  jz      short loc_1800BE94A
0x1800be944  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800be949  nop
0x1800be94a  lea     rcx, [rsp+3A8h+var_360]; this
0x1800be94f  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800be954  nop
0x1800be955  lea     rcx, [rsp+3A8h+var_2F8]; this
0x1800be95d  call    ??1TokenBrokerInternalInvokePluginToManageAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount::~TokenBrokerInternalInvokePluginToManageAccount(void)
0x1800be962  mov     eax, ebx
0x1800be964  jmp     loc_1800BEBA7
0x1800be969  mov     [rsp+3A8h+var_340.lpVtbl], 0
0x1800be972  lea     rcx, [rsp+3A8h+var_340]; this
0x1800be977  call    ?GetCoreWindowHandleForCurrentThread@CallerIdentity@@YAJPEAPEAUHWND__@@@Z; CallerIdentity::GetCoreWindowHandleForCurrentThread(HWND__ * *)
0x1800be97c  test    eax, eax
0x1800be97e  jns     loc_1800BEA0A
0x1800be984  lea     rdx, [rsp+3A8h+var_340]; struct IUnknown *
0x1800be989  mov     rcx, rsi; this
0x1800be98c  call    ?GetClientWindowHandle@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEAPEAUHWND__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetClientWindowHandle(IUnknown *,HWND__ * *)
0x1800be991  mov     ebx, eax
0x1800be993  test    eax, eax
0x1800be995  jns     short loc_1800BEA0A
0x1800be997  mov     rcx, [rsp+3A8h]; this
0x1800be99f  mov     r9d, eax; char *
0x1800be9a2  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800be9a9  mov     edx, 26Eh; void *
0x1800be9ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be9b3  nop
0x1800be9b4  lea     rcx, [rsp+3A8h+var_378]
0x1800be9b9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800be9be  nop
0x1800be9bf  mov     rcx, [rsp+3A8h+string]; string
0x1800be9c4  test    rcx, rcx
0x1800be9c7  jz      short loc_1800BE9D0
0x1800be9c9  call    cs:__imp_WindowsDeleteString
0x1800be9cf  nop
0x1800be9d0  lea     rcx, [rsp+3A8h+TokenHandle]; this
0x1800be9d5  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800be9da  nop
0x1800be9db  mov     rcx, [rsp+3A8h+var_348]; this
0x1800be9e0  test    rcx, rcx
0x1800be9e3  jz      short loc_1800BE9EB
0x1800be9e5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800be9ea  nop
0x1800be9eb  lea     rcx, [rsp+3A8h+var_360]; this
0x1800be9f0  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800be9f5  nop
0x1800be9f6  lea     rcx, [rsp+3A8h+var_2F8]; this
0x1800be9fe  call    ??1TokenBrokerInternalInvokePluginToManageAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToManageAccount::~TokenBrokerInternalInvokePluginToManageAccount(void)
0x1800bea03  mov     eax, ebx
0x1800bea05  jmp     loc_1800BEBA7
0x1800bea0a  mov     qword ptr [rsp+3A8h+var_368], rdi
0x1800bea0f  lea     rcx, [rsp+3A8h+var_368]
0x1800bea14  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800bea19  nop
0x1800bea1a  lea     rcx, [rsp+3A8h+var_310]; TokenHandle
0x1800bea22  call    ??0AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::AsyncImpersonator(void)
0x1800bea27  nop
0x1800bea28  lea     rax, [rsp+3A8h+var_350]
0x1800bea2d  mov     [rsp+3A8h+var_380], rax
0x1800bea32  lea     rax, [rsp+3A8h+var_368]
0x1800bea37  mov     qword ptr [rsp+3A8h+var_388], rax; int
0x1800bea3c  lea     r9, [rsp+3A8h+var_340]
0x1800bea41  lea     r8, [rsp+3A8h+var_2F8]
0x1800bea49  lea     rdx, [rsp+3A8h+var_310]
0x1800bea51  lea     rcx, [rsp+3A8h+var_1A8]
0x1800bea59  call    _lambda_4ef58c21b0f4058fd20490411884590d____lambda_4ef58c21b0f4058fd20490411884590d__0
0x1800bea5e  nop
0x1800bea5f  mov     [rsp+3A8h+var_320], 3
0x1800bea6a  mov     [rsp+3A8h+var_31C], 80h
0x1800bea76  mov     r9, rax
0x1800bea79  mov     rdx, r14
0x1800bea7c  lea     rcx, [rsp+3A8h+var_320]
0x1800bea84  call    Windows__Internal__MakeAsyncAction_Microsoft__WRL__AsyncCausalityOptions__Windows__Internal__Security__Authentication__Web__ManageAccountAsyncActionName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows__Internal__ComTaskPoolHandler__lambda_4ef58c21b0f4058fd20490411884590d___
0x1800bea89  mov     ebx, eax
0x1800bea8b  lea     rcx, [rsp+3A8h+var_1A8]; this
  ... truncated ...
```
