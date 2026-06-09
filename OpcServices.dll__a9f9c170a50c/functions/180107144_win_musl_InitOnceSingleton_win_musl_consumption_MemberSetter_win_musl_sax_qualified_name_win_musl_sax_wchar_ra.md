# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperty>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureProperty>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureProperty>)

- ea: `0x180107144`
- end: `0x18010730e`
- name: `??$Get@V?$SingletonInitializer@VSignatureProperty@Model@win_dox@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VSignatureProperty@Model@win_dox@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VSignatureProperty@Model@win_dox@@@341@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180108890`

## callees

- `0x1800517a0`
- `0x180079ca0`
- `0x180098e2c`
- `0x1800ad628`
- `0x1800cd38c`
- `0x1800cd66c`
- `0x180107144`
- `0x180108400`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180107195`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180107195`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180107273`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180107273`

## string_xrefs

- `0x1801072cc`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperty>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureProperty>>()
{
  win_musl::detail *v0; // rcx
  win_musl::detail *v1; // rcx
  unsigned int LastErrorAsFailHR; // [rsp+30h] [rbp-D8h]
  unsigned int v4; // [rsp+30h] [rbp-D8h]
  BOOL fPending[2]; // [rsp+48h] [rbp-C0h] BYREF
  LPVOID Context; // [rsp+50h] [rbp-B8h] BYREF
  void *v7; // [rsp+58h] [rbp-B0h] BYREF
  union _RTL_RUN_ONCE *v8; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v9; // [rsp+68h] [rbp-A0h]
  __int64 v10; // [rsp+70h] [rbp-98h]
  _BYTE pExceptionObject[160]; // [rsp+78h] [rbp-90h] BYREF

  v10 = -2;
  fPending[0] = 0;
  Context = 0;
  if ( !InitOnceBeginInitialize(
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperty>>::store'::`2'::s_storage,
          0,
          fPending,
          &Context) )
  {
    LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR(v0);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x1DCu,
      LastErrorAsFailHR,
      (struct win_musl::TStringEllipseBase *)L"InitOnceBeginInitialize() failed");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( fPending[0] )
  {
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperty>>::store'::`2'::s_storage;
    LODWORD(v9) = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureProperty>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperty>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperty>>::store'::`2'::s_storage,
            0,
            Context) )
    {
      v4 = win_musl::detail::GetLastErrorAsFailHR(v1);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1F5u,
        v4,
        (struct win_musl::TStringEllipseBase *)L"InitOnceComplete() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v7 = 0;
    v8 = 0;
    std::auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>::~auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>(&v7);
    win_musl::InitOnceGuard::~InitOnceGuard((win_musl::InitOnceGuard *)&v8);
  }
  return Context;
}

```

## disassembly

```asm
0x180107144  mov     rax, rsp
0x180107147  push    rbp
0x180107148  lea     rbp, [rax-28h]
0x18010714c  sub     rsp, 120h
0x180107153  mov     [rsp+120h+var_B8], 0FFFFFFFFFFFFFFFEh
0x18010715c  mov     [rax+8], rdi
0x180107160  mov     rax, cs:__security_cookie
0x180107167  xor     rax, rsp
0x18010716a  mov     [rbp+20h+var_10], rax
0x18010716e  mov     [rsp+120h+fPending], 0
0x180107176  mov     [rsp+120h+Context], 0
0x18010717f  lea     r9, [rsp+120h+Context]; lpContext
0x180107184  lea     r8, [rsp+120h+fPending]; fPending
0x180107189  xor     edx, edx; dwFlags
0x18010718b  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VSignatureProperty@Model@win_dox@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperty>>::store(void)'::`2'::s_storage
0x180107192  mov     rcx, rdi; lpInitOnce
0x180107195  call    cs:__imp_InitOnceBeginInitialize
0x18010719b  test    eax, eax
0x18010719d  jnz     short loc_1801071E6
0x18010719f  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1801071a4  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x1801071ab  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x1801071b0  mov     [rsp+120h+var_F8], eax; unsigned int
0x1801071b4  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x1801071bc  lea     r9, word_18013A0B6
0x1801071c3  lea     r8, aNoFilename; "(no filename)"
0x1801071ca  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1801071cf  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1801071d4  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1801071db  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1801071e0  call    _CxxThrowException_0
0x1801071e6  cmp     [rsp+120h+fPending], 0
0x1801071eb  jz      loc_1801072A4
0x1801071f1  mov     [rsp+120h+var_C8], rdi
0x1801071f6  mov     dword ptr [rsp+120h+var_C0], 0
0x1801071fe  lea     rdx, [rsp+120h+var_D0]
0x180107203  call    ??R?$SingletonInitializer@VSignatureProperty@Model@win_dox@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$auto_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureProperty>::operator()(void)
0x180107208  nop
0x180107209  mov     rax, [rsp+120h+var_D0]
0x18010720e  mov     [rsp+120h+Context], rax
0x180107213  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VSignatureProperty@Model@win_dox@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x18010721a  call    atexit
0x18010721f  test    eax, eax
0x180107221  jz      short loc_180107269
0x180107223  lea     rax, aAtexitFailed; "atexit() failed"
0x18010722a  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x18010722f  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x180107237  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x18010723f  lea     r9, word_18013A0B6
0x180107246  lea     r8, aNoFilename; "(no filename)"
0x18010724d  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180107252  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180107257  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18010725e  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180107263  call    _CxxThrowException_0
0x180107269  mov     r8, [rsp+120h+Context]; lpContext
0x18010726e  xor     edx, edx; dwFlags
0x180107270  mov     rcx, rdi; lpInitOnce
0x180107273  call    cs:__imp_InitOnceComplete
0x180107279  test    eax, eax
0x18010727b  jz      short loc_1801072C6
0x18010727d  mov     [rsp+120h+var_D0], 0
0x180107286  mov     [rsp+120h+var_C8], 0
0x18010728f  lea     rcx, [rsp+120h+var_D0]
0x180107294  call    ??1?$auto_ptr@UMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@QEAA@XZ; std::auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>::~auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>(void)
0x180107299  nop
0x18010729a  lea     rcx, [rsp+120h+var_C8]; this
0x18010729f  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x1801072a4  mov     rax, [rsp+120h+Context]
0x1801072a9  mov     rcx, [rbp+20h+var_10]
0x1801072ad  xor     rcx, rsp; StackCookie
0x1801072b0  call    __security_check_cookie
0x1801072b5  mov     rdi, [rsp+120h+arg_0]
0x1801072bd  add     rsp, 120h
0x1801072c4  pop     rbp
0x1801072c5  retn
0x1801072c6  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1801072cb  nop
0x1801072cc  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x1801072d3  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x1801072d8  mov     [rsp+120h+var_F8], eax; unsigned int
0x1801072dc  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x1801072e4  lea     r9, word_18013A0B6
0x1801072eb  lea     r8, aNoFilename; "(no filename)"
0x1801072f2  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1801072f7  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1801072fc  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180107303  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180107308  call    _CxxThrowException_0
```
