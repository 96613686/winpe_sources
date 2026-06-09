# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::FixedDocument>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::FixedDocument>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::FixedDocument>)

- ea: `0x180002bf0`
- end: `0x180002dce`
- name: `??$Get@V?$SingletonInitializer@VFixedDocument@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VFixedDocument@Model@win_musl@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VFixedDocument@Model@win_musl@@@341@@Z`
- size: `478`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180002bbc`

## callees

- `0x180002bf0`
- `0x180002dec`
- `0x180012450`
- `0x1800228a4`
- `0x1800e331c`
- `0x1800e3d94`
- `0x180115e70`
- `0x180134b70`
- `0x180134f20`
- `0x1801359ce`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180002cc2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180002cc2`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180002c3c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180002c3c`

## string_xrefs

- `0x180002d8c`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::FixedDocument>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::FixedDocument>>()
{
  const char *v0; // rdx
  win_musl::detail *v1; // rcx
  unsigned int v2; // r8d
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  win_musl::detail *v5; // rcx
  int LastErrorAsFailHR; // eax
  int v8; // eax
  WINBOOL fPending; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID Context; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v11; // [rsp+50h] [rbp-B0h]
  union _RTL_RUN_ONCE *v12; // [rsp+58h] [rbp-A8h]
  int v13; // [rsp+60h] [rbp-A0h]
  _BYTE pExceptionObject[160]; // [rsp+70h] [rbp-90h] BYREF

  fPending = 0;
  Context = 0;
  if ( !InitOnceBeginInitialize(
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::FixedDocument>>::store'::`2'::s_storage,
          0,
          &fPending,
          &Context) )
  {
    LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR(v1);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)pExceptionObject,
      0x1DCu,
      LastErrorAsFailHR,
      (__int64)L"InitOnceBeginInitialize() failed");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( fPending )
  {
    v12 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::FixedDocument>>::store'::`2'::s_storage;
    v13 = 0;
    v3 = operator new(0x38u, v0, v2);
    v11 = v3;
    if ( v3 )
      v4 = (_QWORD *)__0__MemberBindings_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParseRemoteDictionaryResource_UMsXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VResourceDictionaryBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___win_musl__QEAA_XZ(v3);
    else
      v4 = 0;
    v11 = v4;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::BindMembers<win_musl::Model::FixedDocument>(v4);
    ___sort_V___Vector_iterator_V___Vector_val_U___Simple_types_U__MemberBinding_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UOpenXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___win_musl___std___std___std___std__YAXV___Vector_iterator_V___Vector_val_U___Simple_types_U__MemberBinding_V__MemberSetterOnReceiver_UPageBodyReceiverTraitsWithTypeList__1____ParsePage_UOpenXpsBuilderTraits_xpsom___win_musl__YAXAEBVOpcPartUri_win_dox__V__scope_PEAUIStream__U__const_policies_Ucom_policies_win_scope___win_scope___win_scope__VFixedPageBodyBuilder_xpsom___Z_Uqualified_name_sax_2_Uwchar_range_sax_2__win_musl___win_musl___std___std___0_0_Z(
      *v4,
      v4[1]);
    v11 = v4;
    Context = v4;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::FixedDocument>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)pExceptionObject,
        0x1EAu,
        -2147024882,
        (__int64)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::FixedDocument>>::store'::`2'::s_storage,
            0,
            Context) )
    {
      v8 = win_musl::detail::GetLastErrorAsFailHR(v5);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)pExceptionObject,
        0x1F5u,
        v8,
        (__int64)L"InitOnceComplete() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  return Context;
}

```

## disassembly

```asm
0x180002bf0  mov     [rsp-8+arg_0], rbx
0x180002bf5  mov     [rsp-8+arg_8], rsi
0x180002bfa  push    rbp
0x180002bfb  lea     rbp, [rsp-20h]
0x180002c00  sub     rsp, 120h
0x180002c07  mov     rax, cs:__security_cookie
0x180002c0e  xor     rax, rsp
0x180002c11  mov     [rbp+20h+var_10], rax
0x180002c15  mov     [rsp+120h+fPending], 0
0x180002c1d  mov     [rsp+120h+Context], 0
0x180002c26  lea     r9, [rsp+120h+Context]; lpContext
0x180002c2b  lea     r8, [rsp+120h+fPending]; fPending
0x180002c30  xor     edx, edx; dwFlags
0x180002c32  lea     rsi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VFixedDocument@Model@win_musl@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::FixedDocument>>::store(void)'::`2'::s_storage
0x180002c39  mov     rcx, rsi; lpInitOnce
0x180002c3c  call    cs:__imp_InitOnceBeginInitialize
0x180002c42  test    eax, eax
0x180002c44  jz      loc_180002CFA
0x180002c4a  cmp     [rsp+120h+fPending], 0
0x180002c4f  jz      short loc_180002CD0
0x180002c51  mov     [rsp+120h+var_C8], rsi
0x180002c56  mov     [rsp+120h+var_C0], 0
0x180002c5e  mov     ecx, 38h ; '8'; unsigned __int64
0x180002c63  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x180002c68  mov     [rsp+120h+var_D0], rax
0x180002c6d  test    rax, rax
0x180002c70  jz      loc_180002CF6
0x180002c76  mov     rcx, rax
0x180002c79  call    ??0?$MemberBindings@V?$MemberSetterOnReceiver@UPageBodyReceiverTraitsWithTypeList@?1???$ParseRemoteDictionaryResource@UMsXpsBuilderTraits@xpsom@@@win_musl@@YAXAEBVOpcPartUri@win_dox@@V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VResourceDictionaryBuilder@xpsom@@@Z@Uqualified_name@sax@2@Uwchar_range@sax@2@@win_musl@@@win_musl@@QEAA@XZ; win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParseRemoteDictionaryResource<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::ResourceDictionaryBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>>::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParseRemoteDictionaryResource<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::ResourceDictionaryBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>>(void)
0x180002c7e  mov     rbx, rax
0x180002c81  mov     [rsp+120h+var_D0], rbx
0x180002c86  mov     rcx, rbx
0x180002c89  call    ??$BindMembers@VFixedDocument@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@KAXPEAUMemberBindings_t@012@PEAVFixedDocument@Model@2@@Z; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::BindMembers<win_musl::Model::FixedDocument>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t *,win_musl::Model::FixedDocument *)
0x180002c8e  mov     rdx, [rbx+8]
0x180002c92  mov     rcx, [rbx]
0x180002c95  call    ??$sort@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U?$MemberBinding@V?$MemberSetterOnReceiver@UPageBodyReceiverTraitsWithTypeList@?1???$ParsePage@UOpenXpsBuilderTraits@xpsom@@@win_musl@@YAXAEBVOpcPartUri@win_dox@@V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VFixedPageBodyBuilder@xpsom@@@Z@Uqualified_name@sax@2@Uwchar_range@sax@2@@win_musl@@@win_musl@@@std@@@std@@@std@@@std@@YAXV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U?$MemberBinding@V?$MemberSetterOnReceiver@UPageBodyReceiverTraitsWithTypeList@?1???$ParsePage@UOpenXpsBuilderTraits@xpsom@@@win_musl@@YAXAEBVOpcPartUri@win_dox@@V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VFixedPageBodyBuilder@xpsom@@@Z@Uqualified_name@sax@2@Uwchar_range@sax@2@@win_musl@@@win_musl@@@std@@@std@@@0@0@Z; std::sort<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<win_musl::MemberBinding<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::OpenXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>>>>>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<win_musl::MemberBinding<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::OpenXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>>>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<win_musl::MemberBinding<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::OpenXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>>>>>)
0x180002c9a  mov     [rsp+120h+var_D0], rbx
0x180002c9f  mov     [rsp+120h+Context], rbx
0x180002ca4  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VFixedDocument@Model@win_musl@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x180002cab  call    atexit
0x180002cb0  test    eax, eax
0x180002cb2  jnz     loc_180002D41
0x180002cb8  mov     r8, [rsp+120h+Context]; lpContext
0x180002cbd  xor     edx, edx; dwFlags
0x180002cbf  mov     rcx, rsi; lpInitOnce
0x180002cc2  call    cs:__imp_InitOnceComplete
0x180002cc8  test    eax, eax
0x180002cca  jz      loc_180002D87
0x180002cd0  mov     rax, [rsp+120h+Context]
0x180002cd5  mov     rcx, [rbp+20h+var_10]
0x180002cd9  xor     rcx, rsp; StackCookie
0x180002cdc  call    __security_check_cookie
0x180002ce1  lea     r11, [rsp+120h+var_s0]
0x180002ce9  mov     rbx, [r11+10h]
0x180002ced  mov     rsi, [r11+18h]
0x180002cf1  mov     rsp, r11
0x180002cf4  pop     rbp
0x180002cf5  retn
0x180002cf6  xor     ebx, ebx
0x180002cf8  jmp     short loc_180002C81
0x180002cfa  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180002cff  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x180002d06  mov     [rsp+120h+var_F0], rcx; __int64
0x180002d0b  mov     [rsp+120h+var_F8], eax; int
0x180002d0f  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x180002d17  lea     r9, Src
0x180002d1e  lea     r8, aNoFilename; "(no filename)"
0x180002d25  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180002d2a  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180002d2f  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180002d36  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180002d3b  call    _CxxThrowException_0
0x180002d41  lea     rax, aAtexitFailed; "atexit() failed"
0x180002d48  mov     [rsp+120h+var_F0], rax; __int64
0x180002d4d  mov     [rsp+120h+var_F8], 8007000Eh; int
0x180002d55  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x180002d5d  lea     r9, Src
0x180002d64  lea     r8, aNoFilename; "(no filename)"
0x180002d6b  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180002d70  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180002d75  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180002d7c  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180002d81  call    _CxxThrowException_0
0x180002d87  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180002d8c  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x180002d93  mov     [rsp+120h+var_F0], rcx; __int64
0x180002d98  mov     [rsp+120h+var_F8], eax; int
0x180002d9c  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x180002da4  lea     r9, Src
0x180002dab  lea     r8, aNoFilename; "(no filename)"
0x180002db2  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180002db7  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180002dbc  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180002dc3  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180002dc8  call    _CxxThrowException_0
```
