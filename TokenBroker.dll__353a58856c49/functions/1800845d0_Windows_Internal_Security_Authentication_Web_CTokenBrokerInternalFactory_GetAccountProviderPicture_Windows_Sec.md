# Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::GetAccountProviderPicture(Windows::Security::Credentials::IWebAccountProvider *,Windows::Storage::Streams::IRandomAccessStream * *)

- ea: `0x1800845d0`
- end: `0x180084a85`
- name: `?GetAccountProviderPicture@CTokenBrokerInternalFactory@Web@Authentication@Security@Internal@Windows@@UEAAJPEAUIWebAccountProvider@Credentials@46@PEAPEAUIRandomAccessStream@Streams@Storage@6@@Z`
- size: `1205`
- prototype: `__int64 __fastcall(unsigned __int64 this, struct Windows::Security::Credentials::IWebAccountProvider *, struct Windows::Storage::Streams::IRandomAccessStream **)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000bd40`
- `0x18000bd70`
- `0x18001e700`
- `0x180020620`
- `0x180020c60`
- `0x180021750`
- `0x1800228a8`
- `0x1800231c0`
- `0x180023a80`
- `0x180026728`
- `0x18002ea84`
- `0x1800845d0`
- `0x180084a8c`
- `0x18008e690`
- `0x18009af30`
- `0x1800c3e08`
- `0x1800dae5c`
- `0x1801081a8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084863`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800848af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008492f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084940`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800849b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800849c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084a13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084a24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084863`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800848af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008492f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084940`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800849b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800849c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084a13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084a24`

## string_xrefs

- `0x18008465f`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800846a2`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800846f7`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18008474f`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800847b3`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18008481b`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x180084893`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x180084913`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x180084999`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x180084635`: `Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::GetAccountProviderPicture`
- `0x1800845fb`: `TokenBrokerInternalGetAccountProviderPicture`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::GetAccountProviderPicture(
        unsigned __int64 this,
        struct Windows::Security::Credentials::IWebAccountProvider *a2,
        struct Windows::Storage::Streams::IRandomAccessStream **a3)
{
  struct IUnknown *v6; // rdi
  __int64 v7; // rcx
  unsigned __int64 *v8; // r8
  int UserContextFromProvider; // eax
  unsigned int v11; // ebx
  unsigned __int64 *v12; // rbx
  int v13; // eax
  unsigned int v14; // edi
  int v15; // eax
  unsigned int v16; // edi
  int DefaultAccountLogo; // eax
  unsigned int v18; // ebx
  int v19; // eax
  int StreamFromFile; // eax
  int v21; // [rsp+20h] [rbp-1C8h]
  Windows::Internal::Security::Authentication::Web::CallerContext *v22; // [rsp+30h] [rbp-1B8h] BYREF
  HSTRING string; // [rsp+38h] [rbp-1B0h] BYREF
  HSTRING v24; // [rsp+40h] [rbp-1A8h] BYREF
  _BYTE v25[8]; // [rsp+48h] [rbp-1A0h] BYREF
  _BYTE v26[8]; // [rsp+50h] [rbp-198h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-190h] BYREF
  char v28; // [rsp+60h] [rbp-188h]
  unsigned __int64 v29; // [rsp+68h] [rbp-180h] BYREF
  _QWORD v30[42]; // [rsp+70h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v30,
    "TokenBrokerInternalGetAccountProviderPicture");
  v30[0] = &TbLogProvider::TokenBrokerInternalGetAccountProviderPicture::`vftable';
  TbLogProvider::TokenBrokerInternalGetAccountProviderPicture::StartActivity((TbLogProvider::TokenBrokerInternalGetAccountProviderPicture *)v30);
  v6 = (struct IUnknown *)(this & -(__int64)(this != 40));
  LOBYTE(v21) = 0;
  Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(
    v7,
    v25,
    v6,
    "Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::GetAccountProviderPicture");
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x400,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v21);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v25);
    TbLogProvider::TokenBrokerInternalGetAccountProviderPicture::~TokenBrokerInternalGetAccountProviderPicture((TbLogProvider::TokenBrokerInternalGetAccountProviderPicture *)v30);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x401,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v21);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v25);
    TbLogProvider::TokenBrokerInternalGetAccountProviderPicture::~TokenBrokerInternalGetAccountProviderPicture((TbLogProvider::TokenBrokerInternalGetAccountProviderPicture *)v30);
    return 2147942487LL;
  }
  v29 = 0;
  UserContextFromProvider = Windows::Internal::Security::Authentication::TokenBroker::GetUserContextFromProvider(
                              a2,
                              (struct Windows::Security::Credentials::IWebAccountProvider *)&v29,
                              v8);
  v11 = UserContextFromProvider;
  if ( UserContextFromProvider < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x405,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)UserContextFromProvider,
      v21);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v25);
    TbLogProvider::TokenBrokerInternalGetAccountProviderPicture::~TokenBrokerInternalGetAccountProviderPicture((TbLogProvider::TokenBrokerInternalGetAccountProviderPicture *)v30);
    return v11;
  }
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v22, v26);
  v12 = (unsigned __int64 *)v22;
  if ( !v22 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x408,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x8007000ELL,
      v21);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v22,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v25);
    TbLogProvider::TokenBrokerInternalGetAccountProviderPicture::~TokenBrokerInternalGetAccountProviderPicture((TbLogProvider::TokenBrokerInternalGetAccountProviderPicture *)v30);
    return 2147942414LL;
  }
  if ( !*(_BYTE *)v22 )
  {
    v13 = Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(v22, v6, v29, 0);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x40B,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
        (const char *)(unsigned int)v13,
        v21);
      wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
        &v22,
        0);
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v25);
      TbLogProvider::TokenBrokerInternalGetAccountProviderPicture::~TokenBrokerInternalGetAccountProviderPicture((TbLogProvider::TokenBrokerInternalGetAccountProviderPicture *)v30);
      return v14;
    }
  }
  TokenHandle = 0;
  v28 = 0;
  v15 = Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(&TokenHandle, v12[2]);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40F,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v15,
      v21);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v22,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v25);
    TbLogProvider::TokenBrokerInternalGetAccountProviderPicture::~TokenBrokerInternalGetAccountProviderPicture((TbLogProvider::TokenBrokerInternalGetAccountProviderPicture *)v30);
    return v16;
  }
  WindowsDeleteString(0);
  string = 0;
  DefaultAccountLogo = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetDefaultAccountLogo(
                         (struct Windows::Internal::Security::Authentication::Web::CallerContext *)v12,
                         a2,
                         &string);
  v18 = DefaultAccountLogo;
  if ( DefaultAccountLogo < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x417,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)DefaultAccountLogo,
      v21);
    if ( string )
      WindowsDeleteString(string);
LABEL_29:
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v22,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v25);
    TbLogProvider::TokenBrokerInternalGetAccountProviderPicture::~TokenBrokerInternalGetAccountProviderPicture((TbLogProvider::TokenBrokerInternalGetAccountProviderPicture *)v30);
    return v18;
  }
  v24 = 0;
  v19 = Windows::Internal::Security::Authentication::TokenBroker::PluginManager::ResolveMRTResourceString(
          &string,
          (struct Windows::Internal::String *)&v24);
  v18 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41C,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v19,
      v21);
    if ( v24 )
      WindowsDeleteString(v24);
    if ( string )
      WindowsDeleteString(string);
    goto LABEL_29;
  }
  StreamFromFile = GetStreamFromFile(&v24, a3);
  v18 = StreamFromFile;
  if ( StreamFromFile < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41F,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)StreamFromFile,
      v21);
    if ( v24 )
      WindowsDeleteString(v24);
    if ( string )
      WindowsDeleteString(string);
    goto LABEL_29;
  }
  wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v30);
  if ( v24 )
    WindowsDeleteString(v24);
  if ( string )
    WindowsDeleteString(string);
  Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
  wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
    &v22,
    0);
  Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v25);
  TbLogProvider::TokenBrokerInternalGetAccountProviderPicture::~TokenBrokerInternalGetAccountProviderPicture((TbLogProvider::TokenBrokerInternalGetAccountProviderPicture *)v30);
  return 0;
}

```

## disassembly

```asm
0x1800845d0  mov     [rsp+arg_18], rbx
0x1800845d5  push    rsi
0x1800845d6  push    rdi
0x1800845d7  push    r14
0x1800845d9  sub     rsp, 1D0h
0x1800845e0  mov     rax, cs:__security_cookie
0x1800845e7  xor     rax, rsp
0x1800845ea  mov     [rsp+1E8h+var_28], rax
0x1800845f2  mov     r14, r8
0x1800845f5  mov     rsi, rdx
0x1800845f8  mov     rbx, rcx
0x1800845fb  lea     rdx, aTokenbrokerint_29; "TokenBrokerInternalGetAccountProviderPi"...
0x180084602  lea     rcx, [rsp+1E8h+var_178]
0x180084607  call    ??0?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18008460c  lea     rax, ??_7TokenBrokerInternalGetAccountProviderPicture@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalGetAccountProviderPicture::`vftable'
0x180084613  mov     [rsp+1E8h+var_178], rax
0x180084618  lea     rcx, [rsp+1E8h+var_178]; this
0x18008461d  call    ?StartActivity@TokenBrokerInternalGetAccountProviderPicture@TbLogProvider@@QEAAXXZ; TbLogProvider::TokenBrokerInternalGetAccountProviderPicture::StartActivity(void)
0x180084622  nop
0x180084623  lea     rax, [rbx-28h]
0x180084627  neg     rax
0x18008462a  sbb     rdi, rdi
0x18008462d  and     rdi, rbx
0x180084630  mov     byte ptr [rsp+1E8h+var_1C8], 0; int
0x180084635  lea     r9, aWindowsInterna_42; "Windows::Internal::Security::Authentica"...
0x18008463c  mov     r8, rdi
0x18008463f  lea     rdx, [rsp+1E8h+var_1A0]
0x180084644  call    ?ProfileCaller@CWamCallerProfiler@Web@Authentication@Security@Internal@Windows@@QEAA?AVCWamProfilerThreadScope@23456@PEAUIUnknown@@PEBD_N@Z; Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(IUnknown *,char const *,bool)
0x180084649  nop
0x18008464a  test    rsi, rsi
0x18008464d  jnz     short loc_18008468D
0x18008464f  mov     rcx, [rsp+1E8h]; this
0x180084657  mov     ebx, 80070057h
0x18008465c  mov     r9d, ebx; char *
0x18008465f  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180084666  mov     edx, 400h; void *
0x18008466b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084670  nop
0x180084671  lea     rcx, [rsp+1E8h+var_1A0]; this
0x180084676  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18008467b  nop
0x18008467c  lea     rcx, [rsp+1E8h+var_178]; this
0x180084681  call    ??1TokenBrokerInternalGetAccountProviderPicture@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetAccountProviderPicture::~TokenBrokerInternalGetAccountProviderPicture(void)
0x180084686  mov     eax, ebx
0x180084688  jmp     loc_180084A60
0x18008468d  test    r14, r14
0x180084690  jnz     short loc_1800846D0
0x180084692  mov     rcx, [rsp+1E8h]; this
0x18008469a  mov     ebx, 80070057h
0x18008469f  mov     r9d, ebx; char *
0x1800846a2  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800846a9  mov     edx, 401h; void *
0x1800846ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800846b3  nop
0x1800846b4  lea     rcx, [rsp+1E8h+var_1A0]; this
0x1800846b9  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800846be  nop
0x1800846bf  lea     rcx, [rsp+1E8h+var_178]; this
0x1800846c4  call    ??1TokenBrokerInternalGetAccountProviderPicture@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetAccountProviderPicture::~TokenBrokerInternalGetAccountProviderPicture(void)
0x1800846c9  mov     eax, ebx
0x1800846cb  jmp     loc_180084A60
0x1800846d0  mov     [rsp+1E8h+var_180], 0
0x1800846d9  lea     rdx, [rsp+1E8h+var_180]; struct Windows::Security::Credentials::IWebAccountProvider *
0x1800846de  mov     rcx, rsi; this
0x1800846e1  call    ?GetUserContextFromProvider@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIWebAccountProvider@Credentials@35@AEA_K@Z; Windows::Internal::Security::Authentication::TokenBroker::GetUserContextFromProvider(Windows::Security::Credentials::IWebAccountProvider *,unsigned __int64 &)
0x1800846e6  mov     ebx, eax
0x1800846e8  test    eax, eax
0x1800846ea  jns     short loc_180084725
0x1800846ec  mov     rcx, [rsp+1E8h]; this
0x1800846f4  mov     r9d, eax; char *
0x1800846f7  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800846fe  mov     edx, 405h; void *
0x180084703  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084708  nop
0x180084709  lea     rcx, [rsp+1E8h+var_1A0]; this
0x18008470e  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x180084713  nop
0x180084714  lea     rcx, [rsp+1E8h+var_178]; this
0x180084719  call    ??1TokenBrokerInternalGetAccountProviderPicture@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetAccountProviderPicture::~TokenBrokerInternalGetAccountProviderPicture(void)
0x18008471e  mov     eax, ebx
0x180084720  jmp     loc_180084A60
0x180084725  lea     rdx, [rsp+1E8h+var_198]
0x18008472a  lea     rcx, [rsp+1E8h+var_1B8]
0x18008472f  call    ??0?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x180084734  nop
0x180084735  mov     rbx, [rsp+1E8h+var_1B8]
0x18008473a  test    rbx, rbx
0x18008473d  jnz     short loc_18008478A
0x18008473f  mov     rcx, [rsp+1E8h]; this
0x180084747  mov     ebx, 8007000Eh
0x18008474c  mov     r9d, ebx; char *
0x18008474f  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180084756  mov     edx, 408h; void *
0x18008475b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084760  nop
0x180084761  xor     edx, edx
0x180084763  lea     rcx, [rsp+1E8h+var_1B8]
0x180084768  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18008476d  nop
0x18008476e  lea     rcx, [rsp+1E8h+var_1A0]; this
0x180084773  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x180084778  nop
0x180084779  lea     rcx, [rsp+1E8h+var_178]; this
0x18008477e  call    ??1TokenBrokerInternalGetAccountProviderPicture@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetAccountProviderPicture::~TokenBrokerInternalGetAccountProviderPicture(void)
0x180084783  mov     eax, ebx
0x180084785  jmp     loc_180084A60
0x18008478a  cmp     byte ptr [rbx], 0
0x18008478d  jnz     short loc_1800847EE
0x18008478f  xor     r9d, r9d; bool
0x180084792  mov     r8, [rsp+1E8h+var_180]; unsigned __int64
0x180084797  mov     rdx, rdi; struct IUnknown *
0x18008479a  mov     rcx, rbx; this
0x18008479d  call    ?Initialize@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUnknown@@_K_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(IUnknown *,unsigned __int64,bool)
0x1800847a2  mov     edi, eax
0x1800847a4  test    eax, eax
0x1800847a6  jns     short loc_1800847EE
0x1800847a8  mov     rcx, [rsp+1E8h]; this
0x1800847b0  mov     r9d, eax; char *
0x1800847b3  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800847ba  mov     edx, 40Bh; void *
0x1800847bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800847c4  nop
0x1800847c5  xor     edx, edx
0x1800847c7  lea     rcx, [rsp+1E8h+var_1B8]
0x1800847cc  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x1800847d1  nop
0x1800847d2  lea     rcx, [rsp+1E8h+var_1A0]; this
0x1800847d7  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800847dc  nop
0x1800847dd  lea     rcx, [rsp+1E8h+var_178]; this
0x1800847e2  call    ??1TokenBrokerInternalGetAccountProviderPicture@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetAccountProviderPicture::~TokenBrokerInternalGetAccountProviderPicture(void)
0x1800847e7  mov     eax, edi
0x1800847e9  jmp     loc_180084A60
0x1800847ee  mov     [rsp+1E8h+TokenHandle], 0
0x1800847f7  mov     [rsp+1E8h+var_188], 0
0x1800847fc  mov     rdx, [rbx+10h]; unsigned __int64
0x180084800  lea     rcx, [rsp+1E8h+TokenHandle]; TokenHandle
0x180084805  call    ?Impersonate@ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAAJ_K@Z; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(unsigned __int64)
0x18008480a  mov     edi, eax
0x18008480c  test    eax, eax
0x18008480e  jns     short loc_180084861
0x180084810  mov     rcx, [rsp+1E8h]; this
0x180084818  mov     r9d, eax; char *
0x18008481b  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180084822  mov     edx, 40Fh; void *
0x180084827  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008482c  nop
0x18008482d  lea     rcx, [rsp+1E8h+TokenHandle]; this
0x180084832  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x180084837  nop
0x180084838  xor     edx, edx
0x18008483a  lea     rcx, [rsp+1E8h+var_1B8]
0x18008483f  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x180084844  nop
0x180084845  lea     rcx, [rsp+1E8h+var_1A0]; this
0x18008484a  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18008484f  nop
0x180084850  lea     rcx, [rsp+1E8h+var_178]; this
0x180084855  call    ??1TokenBrokerInternalGetAccountProviderPicture@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetAccountProviderPicture::~TokenBrokerInternalGetAccountProviderPicture(void)
0x18008485a  mov     eax, edi
0x18008485c  jmp     loc_180084A60
0x180084861  xor     ecx, ecx; string
0x180084863  call    cs:__imp_WindowsDeleteString
0x180084869  mov     [rsp+1E8h+string], 0
0x180084872  lea     r8, [rsp+1E8h+string]; HSTRING *
0x180084877  mov     rdx, rsi; struct Windows::Security::Credentials::IWebAccountProvider *
0x18008487a  mov     rcx, rbx; this
0x18008487d  call    ?GetDefaultAccountLogo@PluginRegistrationInternal@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAVCallerContext@Web@3456@PEAUIWebAccountProvider@Credentials@46@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetDefaultAccountLogo(Windows::Internal::Security::Authentication::Web::CallerContext *,Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ * *)
0x180084882  mov     ebx, eax
0x180084884  test    eax, eax
0x180084886  jns     short loc_1800848EA
0x180084888  mov     rcx, [rsp+1E8h]; this
0x180084890  mov     r9d, eax; char *
0x180084893  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18008489a  mov     edx, 417h; void *
0x18008489f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800848a4  nop
0x1800848a5  mov     rcx, [rsp+1E8h+string]; string
0x1800848aa  test    rcx, rcx
0x1800848ad  jz      short loc_1800848B6
0x1800848af  call    cs:__imp_WindowsDeleteString
0x1800848b5  nop
0x1800848b6  lea     rcx, [rsp+1E8h+TokenHandle]; this
0x1800848bb  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800848c0  nop
0x1800848c1  xor     edx, edx
0x1800848c3  lea     rcx, [rsp+1E8h+var_1B8]
0x1800848c8  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x1800848cd  nop
0x1800848ce  lea     rcx, [rsp+1E8h+var_1A0]; this
0x1800848d3  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800848d8  nop
0x1800848d9  lea     rcx, [rsp+1E8h+var_178]; this
0x1800848de  call    ??1TokenBrokerInternalGetAccountProviderPicture@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetAccountProviderPicture::~TokenBrokerInternalGetAccountProviderPicture(void)
0x1800848e3  mov     eax, ebx
0x1800848e5  jmp     loc_180084A60
0x1800848ea  mov     [rsp+1E8h+var_1A8], 0
0x1800848f3  lea     rdx, [rsp+1E8h+var_1A8]; this
0x1800848f8  lea     rcx, [rsp+1E8h+string]; HSTRING *
0x1800848fd  call    ?ResolveMRTResourceString@PluginManager@TokenBroker@Authentication@Security@Internal@Windows@@SAJAEBVString@56@AEAV756@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginManager::ResolveMRTResourceString(Windows::Internal::String const &,Windows::Internal::String &)
0x180084902  mov     ebx, eax
0x180084904  test    eax, eax
0x180084906  jns     short loc_18008497B
0x180084908  mov     rcx, [rsp+1E8h]; this
0x180084910  mov     r9d, eax; char *
0x180084913  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18008491a  mov     edx, 41Ch; void *
0x18008491f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084924  nop
0x180084925  mov     rcx, [rsp+1E8h+var_1A8]; string
0x18008492a  test    rcx, rcx
0x18008492d  jz      short loc_180084936
0x18008492f  call    cs:__imp_WindowsDeleteString
0x180084935  nop
0x180084936  mov     rcx, [rsp+1E8h+string]; string
0x18008493b  test    rcx, rcx
0x18008493e  jz      short loc_180084947
0x180084940  call    cs:__imp_WindowsDeleteString
0x180084946  nop
0x180084947  lea     rcx, [rsp+1E8h+TokenHandle]; this
0x18008494c  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x180084951  nop
0x180084952  xor     edx, edx
0x180084954  lea     rcx, [rsp+1E8h+var_1B8]
0x180084959  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18008495e  nop
0x18008495f  lea     rcx, [rsp+1E8h+var_1A0]; this
0x180084964  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x180084969  nop
0x18008496a  lea     rcx, [rsp+1E8h+var_178]; this
0x18008496f  call    ??1TokenBrokerInternalGetAccountProviderPicture@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetAccountProviderPicture::~TokenBrokerInternalGetAccountProviderPicture(void)
0x180084974  mov     eax, ebx
0x180084976  jmp     loc_180084A60
0x18008497b  mov     rdx, r14; struct Windows::Storage::Streams::IRandomAccessStream **
0x18008497e  lea     rcx, [rsp+1E8h+var_1A8]; struct Windows::Internal::String *
0x180084983  call    ?GetStreamFromFile@@YAJAEAVString@Internal@Windows@@PEAPEAUIRandomAccessStream@Streams@Storage@3@@Z; GetStreamFromFile(Windows::Internal::String &,Windows::Storage::Streams::IRandomAccessStream * *)
0x180084988  mov     ebx, eax
0x18008498a  test    eax, eax
0x18008498c  jns     short loc_1800849FE
0x18008498e  mov     rcx, [rsp+1E8h]; this
0x180084996  mov     r9d, eax; char *
0x180084999  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800849a0  mov     edx, 41Fh; void *
0x1800849a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800849aa  nop
0x1800849ab  mov     rcx, [rsp+1E8h+var_1A8]; string
0x1800849b0  test    rcx, rcx
0x1800849b3  jz      short loc_1800849BC
0x1800849b5  call    cs:__imp_WindowsDeleteString
0x1800849bb  nop
0x1800849bc  mov     rcx, [rsp+1E8h+string]; string
0x1800849c1  test    rcx, rcx
0x1800849c4  jz      short loc_1800849CD
0x1800849c6  call    cs:__imp_WindowsDeleteString
0x1800849cc  nop
0x1800849cd  lea     rcx, [rsp+1E8h+TokenHandle]; this
0x1800849d2  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800849d7  nop
0x1800849d8  xor     edx, edx
0x1800849da  lea     rcx, [rsp+1E8h+var_1B8]
0x1800849df  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x1800849e4  nop
0x1800849e5  lea     rcx, [rsp+1E8h+var_1A0]; this
0x1800849ea  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800849ef  nop
0x1800849f0  lea     rcx, [rsp+1E8h+var_178]; this
0x1800849f5  call    ??1TokenBrokerInternalGetAccountProviderPicture@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetAccountProviderPicture::~TokenBrokerInternalGetAccountProviderPicture(void)
0x1800849fa  mov     eax, ebx
0x1800849fc  jmp     short loc_180084A60
0x1800849fe  lea     rcx, [rsp+1E8h+var_178]
0x180084a03  call    ?Stop@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180084a08  nop
0x180084a09  mov     rcx, [rsp+1E8h+var_1A8]; string
0x180084a0e  test    rcx, rcx
0x180084a11  jz      short loc_180084A1A
0x180084a13  call    cs:__imp_WindowsDeleteString
0x180084a19  nop
0x180084a1a  mov     rcx, [rsp+1E8h+string]; string
0x180084a1f  test    rcx, rcx
0x180084a22  jz      short loc_180084A2B
0x180084a24  call    cs:__imp_WindowsDeleteString
0x180084a2a  nop
0x180084a2b  lea     rcx, [rsp+1E8h+TokenHandle]; this
0x180084a30  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x180084a35  nop
0x180084a36  xor     edx, edx
0x180084a38  lea     rcx, [rsp+1E8h+var_1B8]
0x180084a3d  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x180084a42  nop
0x180084a43  lea     rcx, [rsp+1E8h+var_1A0]; this
0x180084a48  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x180084a4d  nop
0x180084a4e  lea     rcx, [rsp+1E8h+var_178]; this
0x180084a53  call    ??1TokenBrokerInternalGetAccountProviderPicture@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetAccountProviderPicture::~TokenBrokerInternalGetAccountProviderPicture(void)
0x180084a58  xor     eax, eax
0x180084a5a  jmp     short loc_180084A60
0x180084a5c  mov     eax, dword ptr [rsp+1E8h+var_1B8]
0x180084a60  mov     rcx, [rsp+1E8h+var_28]
0x180084a68  xor     rcx, rsp; StackCookie
0x180084a6b  call    __security_check_cookie
  ... truncated ...
```
