# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::FixedDocumentSequence>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::FixedDocumentSequence>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::FixedDocumentSequence>)

- ea: `0x1800a5864`
- end: `0x1800a5a24`
- name: `??$Get@V?$SingletonInitializer@VFixedDocumentSequence@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VFixedDocumentSequence@Model@win_musl@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VFixedDocumentSequence@Model@win_musl@@@341@@Z`
- size: `448`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800a544c`
- `0x1800a5658`

## callees

- `0x180012450`
- `0x1800a5864`
- `0x1800ad884`
- `0x180115e70`
- `0x180118898`
- `0x180134b70`
- `0x180134f20`
- `0x1801359ce`
- `0x18018c58c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800a5989`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800a5989`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800a58ab`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800a58ab`

## string_xrefs

- `0x1800a59e2`: `InitOnceComplete() failed`

## pseudocode

```c
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::FixedDocumentSequence>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::FixedDocumentSequence>>()
{
  win_musl::detail *v0; // rcx
  int LastErrorAsFailHR; // eax
  win_musl::detail *v2; // rcx
  int v4; // eax
  WINBOOL fPending; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID Context; // [rsp+48h] [rbp-B8h] BYREF
  void *v7; // [rsp+50h] [rbp-B0h] BYREF
  union _RTL_RUN_ONCE *v8; // [rsp+58h] [rbp-A8h] BYREF
  int v9; // [rsp+60h] [rbp-A0h]
  _BYTE pExceptionObject[160]; // [rsp+70h] [rbp-90h] BYREF

  fPending = 0;
  Context = 0;
  if ( !InitOnceBeginInitialize(
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::FixedDocumentSequence>>::store'::`2'::s_storage,
          0,
          &fPending,
          &Context) )
  {
    LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR(v0);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)pExceptionObject,
      0x1DCu,
      LastErrorAsFailHR,
      (__int64)L"InitOnceBeginInitialize() failed");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( fPending )
  {
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::FixedDocumentSequence>>::store'::`2'::s_storage;
    v9 = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::FixedDocumentSequence>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::FixedDocumentSequence>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)pExceptionObject,
        0x1EAu,
        -2147024882,
        (__int64)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::FixedDocumentSequence>>::store'::`2'::s_storage,
            0,
            Context) )
    {
      v4 = win_musl::detail::GetLastErrorAsFailHR(v2);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)pExceptionObject,
        0x1F5u,
        v4,
        (__int64)L"InitOnceComplete() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v7 = 0;
    v8 = 0;
    win_musl::unique_ptr<win_musl::MemberBindings<Z::sax::Uqualified_name::Z::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>'::`2'::PageBodyReceiverTraitsWithTypeList,win_dox::AXAEBVOpcPartUri,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder>,Z::sax::wchar_range> const>::~unique_ptr<win_musl::MemberBindings<Z::sax::Uqualified_name::Z::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>'::`2'::PageBodyReceiverTraitsWithTypeList,win_dox::AXAEBVOpcPartUri,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder>,Z::sax::wchar_range> const>(&v7);
    win_musl::InitOnceGuard::~InitOnceGuard((win_musl::InitOnceGuard *)&v8);
  }
  return Context;
}

```

## disassembly

```asm
0x1800a5864  mov     [rsp-8+arg_0], rdi
0x1800a5869  push    rbp
0x1800a586a  lea     rbp, [rsp-20h]
0x1800a586f  sub     rsp, 120h
0x1800a5876  mov     rax, cs:__security_cookie
0x1800a587d  xor     rax, rsp
0x1800a5880  mov     [rbp+20h+var_10], rax
0x1800a5884  mov     [rsp+120h+fPending], 0
0x1800a588c  mov     [rsp+120h+Context], 0
0x1800a5895  lea     r9, [rsp+120h+Context]; lpContext
0x1800a589a  lea     r8, [rsp+120h+fPending]; fPending
0x1800a589f  xor     edx, edx; dwFlags
0x1800a58a1  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VFixedDocumentSequence@Model@win_musl@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::FixedDocumentSequence>>::store(void)'::`2'::s_storage
0x1800a58a8  mov     rcx, rdi; lpInitOnce
0x1800a58ab  call    cs:__imp_InitOnceBeginInitialize
0x1800a58b1  test    eax, eax
0x1800a58b3  jnz     short loc_1800A58FC
0x1800a58b5  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800a58ba  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x1800a58c1  mov     [rsp+120h+var_F0], rcx; __int64
0x1800a58c6  mov     [rsp+120h+var_F8], eax; int
0x1800a58ca  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x1800a58d2  lea     r9, Src
0x1800a58d9  lea     r8, aNoFilename; "(no filename)"
0x1800a58e0  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800a58e5  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a58ea  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a58f1  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800a58f6  call    _CxxThrowException_0
0x1800a58fc  cmp     [rsp+120h+fPending], 0
0x1800a5901  jz      loc_1800A59BA
0x1800a5907  mov     [rsp+120h+var_C8], rdi
0x1800a590c  mov     [rsp+120h+var_C0], 0
0x1800a5914  lea     rdx, [rsp+120h+var_D0]
0x1800a5919  call    ??R?$SingletonInitializer@VFixedDocumentSequence@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$unique_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$default_delete@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::FixedDocumentSequence>::operator()(void)
0x1800a591e  nop
0x1800a591f  mov     rax, [rsp+120h+var_D0]
0x1800a5924  mov     [rsp+120h+Context], rax
0x1800a5929  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VFixedDocumentSequence@Model@win_musl@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x1800a5930  call    atexit
0x1800a5935  test    eax, eax
0x1800a5937  jz      short loc_1800A597F
0x1800a5939  lea     rax, aAtexitFailed; "atexit() failed"
0x1800a5940  mov     [rsp+120h+var_F0], rax; __int64
0x1800a5945  mov     [rsp+120h+var_F8], 8007000Eh; int
0x1800a594d  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x1800a5955  lea     r9, Src
0x1800a595c  lea     r8, aNoFilename; "(no filename)"
0x1800a5963  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800a5968  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a596d  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a5974  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800a5979  call    _CxxThrowException_0
0x1800a597f  mov     r8, [rsp+120h+Context]; lpContext
0x1800a5984  xor     edx, edx; dwFlags
0x1800a5986  mov     rcx, rdi; lpInitOnce
0x1800a5989  call    cs:__imp_InitOnceComplete
0x1800a598f  test    eax, eax
0x1800a5991  jz      short loc_1800A59DC
0x1800a5993  mov     [rsp+120h+var_D0], 0
0x1800a599c  mov     [rsp+120h+var_C8], 0
0x1800a59a5  lea     rcx, [rsp+120h+var_D0]
0x1800a59aa  call    ??1?$unique_ptr@$$CBU?$MemberBindings@V?$MemberSetterOnReceiver@UPageBodyReceiverTraitsWithTypeList@?1???$ParsePage@UMsXpsBuilderTraits@xpsom@@@win_musl@@YAXAEBVOpcPartUri@win_dox@@V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VFixedPageBodyBuilder@xpsom@@@Z@Uqualified_name@sax@2@Uwchar_range@sax@2@@win_musl@@@win_musl@@U?$default_delete@$$CBU?$MemberBindings@V?$MemberSetterOnReceiver@UPageBodyReceiverTraitsWithTypeList@?1???$ParsePage@UMsXpsBuilderTraits@xpsom@@@win_musl@@YAXAEBVOpcPartUri@win_dox@@V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VFixedPageBodyBuilder@xpsom@@@Z@Uqualified_name@sax@2@Uwchar_range@sax@2@@win_musl@@@win_musl@@@std@@@std@@QEAA@XZ; std::unique_ptr<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const,std::default_delete<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const>>::~unique_ptr<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const,std::default_delete<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const>>(void)
0x1800a59af  nop
0x1800a59b0  lea     rcx, [rsp+120h+var_C8]; this
0x1800a59b5  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x1800a59ba  mov     rax, [rsp+120h+Context]
0x1800a59bf  mov     rcx, [rbp+20h+var_10]
0x1800a59c3  xor     rcx, rsp; StackCookie
0x1800a59c6  call    __security_check_cookie
0x1800a59cb  mov     rdi, [rsp+120h+arg_0]
0x1800a59d3  add     rsp, 120h
0x1800a59da  pop     rbp
0x1800a59db  retn
0x1800a59dc  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800a59e1  nop
0x1800a59e2  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x1800a59e9  mov     [rsp+120h+var_F0], rcx; __int64
0x1800a59ee  mov     [rsp+120h+var_F8], eax; int
0x1800a59f2  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x1800a59fa  lea     r9, Src
0x1800a5a01  lea     r8, aNoFilename; "(no filename)"
0x1800a5a08  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800a5a0d  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a5a12  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a5a19  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800a5a1e  call    _CxxThrowException_0
```
