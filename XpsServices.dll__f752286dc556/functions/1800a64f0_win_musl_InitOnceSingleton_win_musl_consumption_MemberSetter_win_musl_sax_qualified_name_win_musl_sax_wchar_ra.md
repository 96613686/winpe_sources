# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DocumentReference>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::DocumentReference>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::DocumentReference>)

- ea: `0x1800a64f0`
- end: `0x1800a66b0`
- name: `??$Get@V?$SingletonInitializer@VDocumentReference@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VDocumentReference@Model@win_musl@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VDocumentReference@Model@win_musl@@@341@@Z`
- size: `448`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800a6430`

## callees

- `0x180012450`
- `0x1800a64f0`
- `0x1800ad884`
- `0x180115e70`
- `0x180118898`
- `0x180134b70`
- `0x180134f20`
- `0x1801359ce`
- `0x18018c4cc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800a6615`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800a6615`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800a6537`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800a6537`

## string_xrefs

- `0x1800a666e`: `InitOnceComplete() failed`

## pseudocode

```c
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DocumentReference>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::DocumentReference>>()
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
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DocumentReference>>::store'::`2'::s_storage,
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
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DocumentReference>>::store'::`2'::s_storage;
    v9 = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::DocumentReference>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DocumentReference>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)pExceptionObject,
        0x1EAu,
        -2147024882,
        (__int64)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DocumentReference>>::store'::`2'::s_storage,
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
0x1800a64f0  mov     [rsp-8+arg_0], rdi
0x1800a64f5  push    rbp
0x1800a64f6  lea     rbp, [rsp-20h]
0x1800a64fb  sub     rsp, 120h
0x1800a6502  mov     rax, cs:__security_cookie
0x1800a6509  xor     rax, rsp
0x1800a650c  mov     [rbp+20h+var_10], rax
0x1800a6510  mov     [rsp+120h+fPending], 0
0x1800a6518  mov     [rsp+120h+Context], 0
0x1800a6521  lea     r9, [rsp+120h+Context]; lpContext
0x1800a6526  lea     r8, [rsp+120h+fPending]; fPending
0x1800a652b  xor     edx, edx; dwFlags
0x1800a652d  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VDocumentReference@Model@win_musl@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DocumentReference>>::store(void)'::`2'::s_storage
0x1800a6534  mov     rcx, rdi; lpInitOnce
0x1800a6537  call    cs:__imp_InitOnceBeginInitialize
0x1800a653d  test    eax, eax
0x1800a653f  jnz     short loc_1800A6588
0x1800a6541  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800a6546  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x1800a654d  mov     [rsp+120h+var_F0], rcx; __int64
0x1800a6552  mov     [rsp+120h+var_F8], eax; int
0x1800a6556  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x1800a655e  lea     r9, Src
0x1800a6565  lea     r8, aNoFilename; "(no filename)"
0x1800a656c  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800a6571  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a6576  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a657d  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800a6582  call    _CxxThrowException_0
0x1800a6588  cmp     [rsp+120h+fPending], 0
0x1800a658d  jz      loc_1800A6646
0x1800a6593  mov     [rsp+120h+var_C8], rdi
0x1800a6598  mov     [rsp+120h+var_C0], 0
0x1800a65a0  lea     rdx, [rsp+120h+var_D0]
0x1800a65a5  call    ??R?$SingletonInitializer@VDocumentReference@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$unique_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$default_delete@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::DocumentReference>::operator()(void)
0x1800a65aa  nop
0x1800a65ab  mov     rax, [rsp+120h+var_D0]
0x1800a65b0  mov     [rsp+120h+Context], rax
0x1800a65b5  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VDocumentReference@Model@win_musl@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x1800a65bc  call    atexit
0x1800a65c1  test    eax, eax
0x1800a65c3  jz      short loc_1800A660B
0x1800a65c5  lea     rax, aAtexitFailed; "atexit() failed"
0x1800a65cc  mov     [rsp+120h+var_F0], rax; __int64
0x1800a65d1  mov     [rsp+120h+var_F8], 8007000Eh; int
0x1800a65d9  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x1800a65e1  lea     r9, Src
0x1800a65e8  lea     r8, aNoFilename; "(no filename)"
0x1800a65ef  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800a65f4  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a65f9  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a6600  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800a6605  call    _CxxThrowException_0
0x1800a660b  mov     r8, [rsp+120h+Context]; lpContext
0x1800a6610  xor     edx, edx; dwFlags
0x1800a6612  mov     rcx, rdi; lpInitOnce
0x1800a6615  call    cs:__imp_InitOnceComplete
0x1800a661b  test    eax, eax
0x1800a661d  jz      short loc_1800A6668
0x1800a661f  mov     [rsp+120h+var_D0], 0
0x1800a6628  mov     [rsp+120h+var_C8], 0
0x1800a6631  lea     rcx, [rsp+120h+var_D0]
0x1800a6636  call    ??1?$unique_ptr@$$CBU?$MemberBindings@V?$MemberSetterOnReceiver@UPageBodyReceiverTraitsWithTypeList@?1???$ParsePage@UMsXpsBuilderTraits@xpsom@@@win_musl@@YAXAEBVOpcPartUri@win_dox@@V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VFixedPageBodyBuilder@xpsom@@@Z@Uqualified_name@sax@2@Uwchar_range@sax@2@@win_musl@@@win_musl@@U?$default_delete@$$CBU?$MemberBindings@V?$MemberSetterOnReceiver@UPageBodyReceiverTraitsWithTypeList@?1???$ParsePage@UMsXpsBuilderTraits@xpsom@@@win_musl@@YAXAEBVOpcPartUri@win_dox@@V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VFixedPageBodyBuilder@xpsom@@@Z@Uqualified_name@sax@2@Uwchar_range@sax@2@@win_musl@@@win_musl@@@std@@@std@@QEAA@XZ; std::unique_ptr<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const,std::default_delete<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const>>::~unique_ptr<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const,std::default_delete<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const>>(void)
0x1800a663b  nop
0x1800a663c  lea     rcx, [rsp+120h+var_C8]; this
0x1800a6641  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x1800a6646  mov     rax, [rsp+120h+Context]
0x1800a664b  mov     rcx, [rbp+20h+var_10]
0x1800a664f  xor     rcx, rsp; StackCookie
0x1800a6652  call    __security_check_cookie
0x1800a6657  mov     rdi, [rsp+120h+arg_0]
0x1800a665f  add     rsp, 120h
0x1800a6666  pop     rbp
0x1800a6667  retn
0x1800a6668  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800a666d  nop
0x1800a666e  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x1800a6675  mov     [rsp+120h+var_F0], rcx; __int64
0x1800a667a  mov     [rsp+120h+var_F8], eax; int
0x1800a667e  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x1800a6686  lea     r9, Src
0x1800a668d  lea     r8, aNoFilename; "(no filename)"
0x1800a6694  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800a6699  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a669e  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a66a5  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800a66aa  call    _CxxThrowException_0
```
