# Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::IsShowProviderInSelectionUi(Windows::Security::Credentials::IWebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider *,uchar *)

- ea: `0x180083f90`
- end: `0x180084591`
- name: `?IsShowProviderInSelectionUi@CTokenBrokerInternalFactory@Web@Authentication@Security@Internal@Windows@@UEAAJPEAUIWebAccountProvider@Credentials@46@0PEAE@Z`
- size: `1537`
- prototype: `int(Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory *__hidden this, struct Windows::Security::Credentials::IWebAccountProvider *, struct Windows::Security::Credentials::IWebAccountProvider *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x18000bd70`
- `0x18001e700`
- `0x180020620`
- `0x180020c60`
- `0x180021750`
- `0x1800228a8`
- `0x1800231c0`
- `0x180023a80`
- `0x18002d940`
- `0x18002ea84`
- `0x180031270`
- `0x18003d940`
- `0x18005fdcc`
- `0x180083f90`
- `0x180084598`
- `0x18008e690`
- `0x1800c4198`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084277`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008431d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800843ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800843c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008449c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800844b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084516`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084532`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084277`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008431d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800843ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800843c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008449c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800844b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084516`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084532`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18008442e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18008442e`

## string_xrefs

- `0x18008402a`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x180084070`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800840b6`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x180084111`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x180084176`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800841e1`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18008425b`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800842f6`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18008438f`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x180084480`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x180084000`: `Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::IsShowProviderInSelectionUi`
- `0x180083fbd`: `TokenBrokerInternalIsShowProviderInSelectionUi`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::IsShowProviderInSelectionUi(
        unsigned __int64 this,
        __int64 (__fastcall ***a2)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *),
        struct Windows::Security::Credentials::IWebAccountProvider *a3,
        bool *a4)
{
  struct IUnknown *v8; // rdi
  __int64 v9; // rcx
  __int64 *v11; // rbx
  int v12; // eax
  unsigned int v13; // edi
  int v14; // eax
  unsigned int v15; // edi
  int v16; // eax
  unsigned int v17; // edi
  __int64 (__fastcall *v18)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *); // rdi
  int v19; // eax
  int v20; // eax
  int v21; // eax
  unsigned int v22; // ebx
  int v23; // [rsp+20h] [rbp-1F8h]
  Windows::Internal::Security::Authentication::Web::CallerContext *v24; // [rsp+30h] [rbp-1E8h] BYREF
  __int64 v25; // [rsp+38h] [rbp-1E0h] BYREF
  HSTRING string; // [rsp+40h] [rbp-1D8h] BYREF
  _BYTE v27[8]; // [rsp+48h] [rbp-1D0h] BYREF
  _BYTE v28[8]; // [rsp+50h] [rbp-1C8h] BYREF
  HSTRING v29; // [rsp+58h] [rbp-1C0h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-1B8h] BYREF
  char v31; // [rsp+68h] [rbp-1B0h]
  HSTRING string2[4]; // [rsp+70h] [rbp-1A8h] BYREF
  _QWORD v33[42]; // [rsp+90h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v33,
    "TokenBrokerInternalIsShowProviderInSelectionUi");
  v33[0] = &TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi::`vftable';
  TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi::StartActivity((TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi *)v33);
  v8 = (struct IUnknown *)(this & -(__int64)(this != 40));
  LOBYTE(v23) = 0;
  Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(
    v9,
    v27,
    v8,
    "Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::IsShowProviderInSelectionUi");
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x477,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v23);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v27);
    TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi::~TokenBrokerInternalIsShowProviderInSelectionUi((TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi *)v33);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x478,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v23);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v27);
    TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi::~TokenBrokerInternalIsShowProviderInSelectionUi((TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi *)v33);
    return 2147942487LL;
  }
  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x479,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v23);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v27);
    TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi::~TokenBrokerInternalIsShowProviderInSelectionUi((TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi *)v33);
    return 2147942487LL;
  }
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v24, v28);
  v11 = (__int64 *)v24;
  if ( !v24 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47C,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x8007000ELL,
      v23);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v24,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v27);
    TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi::~TokenBrokerInternalIsShowProviderInSelectionUi((TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi *)v33);
    return 2147942414LL;
  }
  if ( !*(_BYTE *)v24 )
  {
    v12 = Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(v24, v8, 0, 0);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x47F,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
        (const char *)(unsigned int)v12,
        v23);
      wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
        &v24,
        0);
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v27);
      TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi::~TokenBrokerInternalIsShowProviderInSelectionUi((TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi *)v33);
      return v13;
    }
  }
  TokenHandle = 0;
  v31 = 0;
  v14 = Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(&TokenHandle, v11[2]);
  v15 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x483,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v14,
      v23);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v24,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v27);
    TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi::~TokenBrokerInternalIsShowProviderInSelectionUi((TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi *)v33);
    return v15;
  }
  *a4 = 0;
  string = 0;
  v16 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *), HSTRING *))(*a2)[6])(
          a2,
          &string);
  v17 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48F,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v16,
      v23);
    if ( string )
      WindowsDeleteString(string);
LABEL_27:
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v24,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v27);
    TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi::~TokenBrokerInternalIsShowProviderInSelectionUi((TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi *)v33);
    return v17;
  }
  v25 = 0;
  v18 = **a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  v19 = v18(
          (struct Windows::Security::Credentials::IWebAccountProvider *)a2,
          &GUID_4a01eb05_4e42_41d4_b518_e008a5163614,
          &v25);
  v17 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x491,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v19,
      v23);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
    if ( string )
      WindowsDeleteString(string);
    goto LABEL_27;
  }
  v29 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 56LL))(v25, &v29);
  v17 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x493,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v20,
      v23);
    if ( v29 )
      WindowsDeleteString(v29);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
    if ( string )
      WindowsDeleteString(string);
    goto LABEL_27;
  }
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)string2,
    L"https://login.microsoft.com");
  if ( CompareProviderIds(string, string2[0]) && WindowsIsStringEmpty(v29) )
  {
    *a4 = (unsigned int)Windows::Internal::Security::Authentication::TokenBroker::PluginManager::GetBuiltInProviderType((int (__fastcall ***)(_QWORD, GUID *, __int64 *))a3)
        - 1 <= 1;
LABEL_39:
    wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v33);
    if ( v29 )
      WindowsDeleteString(v29);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
    if ( string )
      WindowsDeleteString(string);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v24,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v27);
    TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi::~TokenBrokerInternalIsShowProviderInSelectionUi((TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi *)v33);
    return 0;
  }
  v21 = Windows::Internal::Security::Authentication::TokenBroker::PluginManagerInternal::CompareProviders(
          (struct Windows::Internal::Security::Authentication::Web::CallerContext *)v11,
          (struct Windows::Security::Credentials::IWebAccountProvider *)a2,
          a3,
          (unsigned __int8 *)a4);
  v22 = v21;
  if ( v21 >= 0 )
    goto LABEL_39;
  if ( v21 == -2146893805 )
  {
    *a4 = 0;
    goto LABEL_39;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4A0,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
    (const char *)(unsigned int)v21,
    v23);
  if ( v29 )
    WindowsDeleteString(v29);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  if ( string )
    WindowsDeleteString(string);
  Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
  wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
    &v24,
    0);
  Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v27);
  TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi::~TokenBrokerInternalIsShowProviderInSelectionUi((TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi *)v33);
  return v22;
}

```

## disassembly

```asm
0x180083f90  push    rbx
0x180083f92  push    rsi
0x180083f93  push    rdi
0x180083f94  push    r14
0x180083f96  push    r15
0x180083f98  sub     rsp, 1F0h
0x180083f9f  mov     rax, cs:__security_cookie
0x180083fa6  xor     rax, rsp
0x180083fa9  mov     [rsp+218h+var_38], rax
0x180083fb1  mov     rsi, r9
0x180083fb4  mov     r15, r8
0x180083fb7  mov     r14, rdx
0x180083fba  mov     rbx, rcx
0x180083fbd  lea     rdx, aTokenbrokerint_27; "TokenBrokerInternalIsShowProviderInSele"...
0x180083fc4  lea     rcx, [rsp+218h+var_188]
0x180083fcc  call    ??0?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180083fd1  lea     rax, ??_7TokenBrokerInternalIsShowProviderInSelectionUi@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi::`vftable'
0x180083fd8  mov     [rsp+218h+var_188], rax
0x180083fe0  lea     rcx, [rsp+218h+var_188]; this
0x180083fe8  call    ?StartActivity@TokenBrokerInternalIsShowProviderInSelectionUi@TbLogProvider@@QEAAXXZ; TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi::StartActivity(void)
0x180083fed  nop
0x180083fee  lea     rax, [rbx-28h]
0x180083ff2  neg     rax
0x180083ff5  sbb     rdi, rdi
0x180083ff8  and     rdi, rbx
0x180083ffb  mov     byte ptr [rsp+218h+var_1F8], 0; int
0x180084000  lea     r9, aWindowsInterna_62; "Windows::Internal::Security::Authentica"...
0x180084007  mov     r8, rdi
0x18008400a  lea     rdx, [rsp+218h+var_1D0]
0x18008400f  call    ?ProfileCaller@CWamCallerProfiler@Web@Authentication@Security@Internal@Windows@@QEAA?AVCWamProfilerThreadScope@23456@PEAUIUnknown@@PEBD_N@Z; Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(IUnknown *,char const *,bool)
0x180084014  nop
0x180084015  test    r14, r14
0x180084018  jnz     short loc_18008405B
0x18008401a  mov     rcx, [rsp+218h]; this
0x180084022  mov     ebx, 80070057h
0x180084027  mov     r9d, ebx; char *
0x18008402a  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180084031  mov     edx, 477h; void *
0x180084036  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008403b  nop
0x18008403c  lea     rcx, [rsp+218h+var_1D0]; this
0x180084041  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x180084046  nop
0x180084047  lea     rcx, [rsp+218h+var_188]; this
0x18008404f  call    ??1TokenBrokerInternalIsShowProviderInSelectionUi@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi::~TokenBrokerInternalIsShowProviderInSelectionUi(void)
0x180084054  mov     eax, ebx
0x180084056  jmp     loc_180084571
0x18008405b  test    r15, r15
0x18008405e  jnz     short loc_1800840A1
0x180084060  mov     rcx, [rsp+218h]; this
0x180084068  mov     ebx, 80070057h
0x18008406d  mov     r9d, ebx; char *
0x180084070  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180084077  mov     edx, 478h; void *
0x18008407c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084081  nop
0x180084082  lea     rcx, [rsp+218h+var_1D0]; this
0x180084087  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18008408c  nop
0x18008408d  lea     rcx, [rsp+218h+var_188]; this
0x180084095  call    ??1TokenBrokerInternalIsShowProviderInSelectionUi@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi::~TokenBrokerInternalIsShowProviderInSelectionUi(void)
0x18008409a  mov     eax, ebx
0x18008409c  jmp     loc_180084571
0x1800840a1  test    rsi, rsi
0x1800840a4  jnz     short loc_1800840E7
0x1800840a6  mov     rcx, [rsp+218h]; this
0x1800840ae  mov     ebx, 80070057h
0x1800840b3  mov     r9d, ebx; char *
0x1800840b6  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800840bd  mov     edx, 479h; void *
0x1800840c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800840c7  nop
0x1800840c8  lea     rcx, [rsp+218h+var_1D0]; this
0x1800840cd  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800840d2  nop
0x1800840d3  lea     rcx, [rsp+218h+var_188]; this
0x1800840db  call    ??1TokenBrokerInternalIsShowProviderInSelectionUi@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi::~TokenBrokerInternalIsShowProviderInSelectionUi(void)
0x1800840e0  mov     eax, ebx
0x1800840e2  jmp     loc_180084571
0x1800840e7  lea     rdx, [rsp+218h+var_1C8]
0x1800840ec  lea     rcx, [rsp+218h+var_1E8]
0x1800840f1  call    ??0?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x1800840f6  nop
0x1800840f7  mov     rbx, [rsp+218h+var_1E8]
0x1800840fc  test    rbx, rbx
0x1800840ff  jnz     short loc_18008414F
0x180084101  mov     rcx, [rsp+218h]; this
0x180084109  mov     ebx, 8007000Eh
0x18008410e  mov     r9d, ebx; char *
0x180084111  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180084118  mov     edx, 47Ch; void *
0x18008411d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084122  nop
0x180084123  xor     edx, edx
0x180084125  lea     rcx, [rsp+218h+var_1E8]
0x18008412a  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18008412f  nop
0x180084130  lea     rcx, [rsp+218h+var_1D0]; this
0x180084135  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18008413a  nop
0x18008413b  lea     rcx, [rsp+218h+var_188]; this
0x180084143  call    ??1TokenBrokerInternalIsShowProviderInSelectionUi@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi::~TokenBrokerInternalIsShowProviderInSelectionUi(void)
0x180084148  mov     eax, ebx
0x18008414a  jmp     loc_180084571
0x18008414f  cmp     byte ptr [rbx], 0
0x180084152  jnz     short loc_1800841B4
0x180084154  xor     r9d, r9d; bool
0x180084157  xor     r8d, r8d; unsigned __int64
0x18008415a  mov     rdx, rdi; struct IUnknown *
0x18008415d  mov     rcx, rbx; this
0x180084160  call    ?Initialize@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUnknown@@_K_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(IUnknown *,unsigned __int64,bool)
0x180084165  mov     edi, eax
0x180084167  test    eax, eax
0x180084169  jns     short loc_1800841B4
0x18008416b  mov     rcx, [rsp+218h]; this
0x180084173  mov     r9d, eax; char *
0x180084176  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18008417d  mov     edx, 47Fh; void *
0x180084182  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084187  nop
0x180084188  xor     edx, edx
0x18008418a  lea     rcx, [rsp+218h+var_1E8]
0x18008418f  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x180084194  nop
0x180084195  lea     rcx, [rsp+218h+var_1D0]; this
0x18008419a  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18008419f  nop
0x1800841a0  lea     rcx, [rsp+218h+var_188]; this
0x1800841a8  call    ??1TokenBrokerInternalIsShowProviderInSelectionUi@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi::~TokenBrokerInternalIsShowProviderInSelectionUi(void)
0x1800841ad  mov     eax, edi
0x1800841af  jmp     loc_180084571
0x1800841b4  mov     [rsp+218h+TokenHandle], 0
0x1800841bd  mov     [rsp+218h+var_1B0], 0
0x1800841c2  mov     rdx, [rbx+10h]; unsigned __int64
0x1800841c6  lea     rcx, [rsp+218h+TokenHandle]; TokenHandle
0x1800841cb  call    ?Impersonate@ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAAJ_K@Z; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(unsigned __int64)
0x1800841d0  mov     edi, eax
0x1800841d2  test    eax, eax
0x1800841d4  jns     short loc_18008422A
0x1800841d6  mov     rcx, [rsp+218h]; this
0x1800841de  mov     r9d, eax; char *
0x1800841e1  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800841e8  mov     edx, 483h; void *
0x1800841ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800841f2  nop
0x1800841f3  lea     rcx, [rsp+218h+TokenHandle]; this
0x1800841f8  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800841fd  nop
0x1800841fe  xor     edx, edx
0x180084200  lea     rcx, [rsp+218h+var_1E8]
0x180084205  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18008420a  nop
0x18008420b  lea     rcx, [rsp+218h+var_1D0]; this
0x180084210  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x180084215  nop
0x180084216  lea     rcx, [rsp+218h+var_188]; this
0x18008421e  call    ??1TokenBrokerInternalIsShowProviderInSelectionUi@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi::~TokenBrokerInternalIsShowProviderInSelectionUi(void)
0x180084223  mov     eax, edi
0x180084225  jmp     loc_180084571
0x18008422a  mov     byte ptr [rsi], 0
0x18008422d  mov     [rsp+218h+string], 0
0x180084236  mov     rax, [r14]
0x180084239  lea     rdx, [rsp+218h+string]
0x18008423e  mov     rcx, r14
0x180084241  mov     rax, [rax+30h]
0x180084245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008424a  mov     edi, eax
0x18008424c  test    eax, eax
0x18008424e  jns     short loc_1800842B5
0x180084250  mov     rcx, [rsp+218h]; this
0x180084258  mov     r9d, eax; char *
0x18008425b  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180084262  mov     edx, 48Fh; void *
0x180084267  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008426c  nop
0x18008426d  mov     rcx, [rsp+218h+string]; string
0x180084272  test    rcx, rcx
0x180084275  jz      short loc_18008427E
0x180084277  call    cs:__imp_WindowsDeleteString
0x18008427d  nop
0x18008427e  lea     rcx, [rsp+218h+TokenHandle]; this
0x180084283  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x180084288  nop
0x180084289  xor     edx, edx
0x18008428b  lea     rcx, [rsp+218h+var_1E8]
0x180084290  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x180084295  nop
0x180084296  lea     rcx, [rsp+218h+var_1D0]; this
0x18008429b  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800842a0  nop
0x1800842a1  lea     rcx, [rsp+218h+var_188]; this
0x1800842a9  call    ??1TokenBrokerInternalIsShowProviderInSelectionUi@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi::~TokenBrokerInternalIsShowProviderInSelectionUi(void)
0x1800842ae  mov     eax, edi
0x1800842b0  jmp     loc_180084571
0x1800842b5  mov     [rsp+218h+var_1E0], 0
0x1800842be  mov     rax, [r14]
0x1800842c1  mov     rdi, [rax]
0x1800842c4  lea     rcx, [rsp+218h+var_1E0]
0x1800842c9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800842ce  lea     r8, [rsp+218h+var_1E0]
0x1800842d3  lea     rdx, _GUID_4a01eb05_4e42_41d4_b518_e008a5163614
0x1800842da  mov     rcx, r14
0x1800842dd  mov     rax, rdi
0x1800842e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800842e5  mov     edi, eax
0x1800842e7  test    eax, eax
0x1800842e9  jns     short loc_18008435B
0x1800842eb  mov     rcx, [rsp+218h]; this
0x1800842f3  mov     r9d, eax; char *
0x1800842f6  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800842fd  mov     edx, 491h; void *
0x180084302  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084307  nop
0x180084308  lea     rcx, [rsp+218h+var_1E0]
0x18008430d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180084312  nop
0x180084313  mov     rcx, [rsp+218h+string]; string
0x180084318  test    rcx, rcx
0x18008431b  jz      short loc_180084324
0x18008431d  call    cs:__imp_WindowsDeleteString
0x180084323  nop
0x180084324  lea     rcx, [rsp+218h+TokenHandle]; this
0x180084329  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x18008432e  nop
0x18008432f  xor     edx, edx
0x180084331  lea     rcx, [rsp+218h+var_1E8]
0x180084336  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18008433b  nop
0x18008433c  lea     rcx, [rsp+218h+var_1D0]; this
0x180084341  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x180084346  nop
0x180084347  lea     rcx, [rsp+218h+var_188]; this
0x18008434f  call    ??1TokenBrokerInternalIsShowProviderInSelectionUi@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi::~TokenBrokerInternalIsShowProviderInSelectionUi(void)
0x180084354  mov     eax, edi
0x180084356  jmp     loc_180084571
0x18008435b  mov     [rsp+218h+var_1C0], 0
0x180084364  mov     rcx, [rsp+218h+var_1E0]
0x180084369  mov     rax, [rcx]
0x18008436c  lea     rdx, [rsp+218h+var_1C0]
0x180084371  mov     rax, [rax+38h]
0x180084375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008437a  mov     edi, eax
0x18008437c  test    eax, eax
0x18008437e  jns     loc_180084405
0x180084384  mov     rcx, [rsp+218h]; this
0x18008438c  mov     r9d, eax; char *
0x18008438f  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180084396  mov     edx, 493h; void *
0x18008439b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800843a0  nop
0x1800843a1  mov     rcx, [rsp+218h+var_1C0]; string
0x1800843a6  test    rcx, rcx
0x1800843a9  jz      short loc_1800843B2
0x1800843ab  call    cs:__imp_WindowsDeleteString
0x1800843b1  nop
0x1800843b2  lea     rcx, [rsp+218h+var_1E0]
0x1800843b7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800843bc  nop
0x1800843bd  mov     rcx, [rsp+218h+string]; string
0x1800843c2  test    rcx, rcx
0x1800843c5  jz      short loc_1800843CE
0x1800843c7  call    cs:__imp_WindowsDeleteString
0x1800843cd  nop
0x1800843ce  lea     rcx, [rsp+218h+TokenHandle]; this
0x1800843d3  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800843d8  nop
0x1800843d9  xor     edx, edx
0x1800843db  lea     rcx, [rsp+218h+var_1E8]
0x1800843e0  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x1800843e5  nop
0x1800843e6  lea     rcx, [rsp+218h+var_1D0]; this
0x1800843eb  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800843f0  nop
0x1800843f1  lea     rcx, [rsp+218h+var_188]; this
0x1800843f9  call    ??1TokenBrokerInternalIsShowProviderInSelectionUi@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalIsShowProviderInSelectionUi::~TokenBrokerInternalIsShowProviderInSelectionUi(void)
0x1800843fe  mov     eax, edi
0x180084400  jmp     loc_180084571
0x180084405  mov     rdx, cs:off_18012B2F8; unsigned __int16 *
0x18008440c  lea     rcx, [rsp+218h+string2]; this
0x180084411  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180084416  mov     rdx, [rsp+218h+string2]; string2
0x18008441b  mov     rcx, [rsp+218h+string]; string1
0x180084420  call    ?CompareProviderIds@@YA_NPEAUHSTRING__@@0@Z; CompareProviderIds(HSTRING__ *,HSTRING__ *)
0x180084425  test    al, al
0x180084427  jz      short loc_18008444F
0x180084429  mov     rcx, [rsp+218h+var_1C0]; string
0x18008442e  call    cs:__imp_WindowsIsStringEmpty
0x180084434  test    eax, eax
0x180084436  jz      short loc_18008444F
0x180084438  mov     rcx, r15
0x18008443b  call    ?GetBuiltInProviderType@PluginManager@TokenBroker@Authentication@Security@Internal@Windows@@SA?AW4BuiltInProviderType@23456@PEAUIWebAccountProvider@Credentials@46@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginManager::GetBuiltInProviderType(Windows::Security::Credentials::IWebAccountProvider *)
0x180084440  dec     eax
0x180084442  cmp     eax, 1
0x180084445  setbe   al
0x180084448  mov     [rsi], al
0x18008444a  jmp     loc_1800844FE
0x18008444f  mov     r9, rsi; unsigned __int8 *
0x180084452  mov     r8, r15; struct Windows::Security::Credentials::IWebAccountProvider *
0x180084455  mov     rdx, r14; struct Windows::Security::Credentials::IWebAccountProvider *
0x180084458  mov     rcx, rbx; this
  ... truncated ...
```
