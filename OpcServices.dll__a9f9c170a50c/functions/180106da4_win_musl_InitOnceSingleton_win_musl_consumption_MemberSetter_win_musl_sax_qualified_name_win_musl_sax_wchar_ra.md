# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::ObjectBlob>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::ObjectBlob>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::ObjectBlob>)

- ea: `0x180106da4`
- end: `0x180106f6e`
- name: `??$Get@V?$SingletonInitializer@VObjectBlob@Model@win_dox@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VObjectBlob@Model@win_dox@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VObjectBlob@Model@win_dox@@@341@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180108b54`

## callees

- `0x1800517a0`
- `0x180079ca0`
- `0x180098e2c`
- `0x1800ad628`
- `0x1800cd38c`
- `0x1800cd66c`
- `0x180106da4`
- `0x180108234`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180106df5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180106df5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180106ed3`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180106ed3`

## string_xrefs

- `0x180106f2c`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::ObjectBlob>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::ObjectBlob>>()
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
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::ObjectBlob>>::store'::`2'::s_storage,
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
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::ObjectBlob>>::store'::`2'::s_storage;
    LODWORD(v9) = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::ObjectBlob>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::ObjectBlob>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::ObjectBlob>>::store'::`2'::s_storage,
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
0x180106da4  mov     rax, rsp
0x180106da7  push    rbp
0x180106da8  lea     rbp, [rax-28h]
0x180106dac  sub     rsp, 120h
0x180106db3  mov     [rsp+120h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180106dbc  mov     [rax+8], rdi
0x180106dc0  mov     rax, cs:__security_cookie
0x180106dc7  xor     rax, rsp
0x180106dca  mov     [rbp+20h+var_10], rax
0x180106dce  mov     [rsp+120h+fPending], 0
0x180106dd6  mov     [rsp+120h+Context], 0
0x180106ddf  lea     r9, [rsp+120h+Context]; lpContext
0x180106de4  lea     r8, [rsp+120h+fPending]; fPending
0x180106de9  xor     edx, edx; dwFlags
0x180106deb  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VObjectBlob@Model@win_dox@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::ObjectBlob>>::store(void)'::`2'::s_storage
0x180106df2  mov     rcx, rdi; lpInitOnce
0x180106df5  call    cs:__imp_InitOnceBeginInitialize
0x180106dfb  test    eax, eax
0x180106dfd  jnz     short loc_180106E46
0x180106dff  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180106e04  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x180106e0b  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180106e10  mov     [rsp+120h+var_F8], eax; unsigned int
0x180106e14  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x180106e1c  lea     r9, word_18013A0B6
0x180106e23  lea     r8, aNoFilename; "(no filename)"
0x180106e2a  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180106e2f  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180106e34  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180106e3b  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180106e40  call    _CxxThrowException_0
0x180106e46  cmp     [rsp+120h+fPending], 0
0x180106e4b  jz      loc_180106F04
0x180106e51  mov     [rsp+120h+var_C8], rdi
0x180106e56  mov     dword ptr [rsp+120h+var_C0], 0
0x180106e5e  lea     rdx, [rsp+120h+var_D0]
0x180106e63  call    ??R?$SingletonInitializer@VObjectBlob@Model@win_dox@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$auto_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::ObjectBlob>::operator()(void)
0x180106e68  nop
0x180106e69  mov     rax, [rsp+120h+var_D0]
0x180106e6e  mov     [rsp+120h+Context], rax
0x180106e73  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VObjectBlob@Model@win_dox@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x180106e7a  call    atexit
0x180106e7f  test    eax, eax
0x180106e81  jz      short loc_180106EC9
0x180106e83  lea     rax, aAtexitFailed; "atexit() failed"
0x180106e8a  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x180106e8f  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x180106e97  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x180106e9f  lea     r9, word_18013A0B6
0x180106ea6  lea     r8, aNoFilename; "(no filename)"
0x180106ead  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180106eb2  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180106eb7  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180106ebe  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180106ec3  call    _CxxThrowException_0
0x180106ec9  mov     r8, [rsp+120h+Context]; lpContext
0x180106ece  xor     edx, edx; dwFlags
0x180106ed0  mov     rcx, rdi; lpInitOnce
0x180106ed3  call    cs:__imp_InitOnceComplete
0x180106ed9  test    eax, eax
0x180106edb  jz      short loc_180106F26
0x180106edd  mov     [rsp+120h+var_D0], 0
0x180106ee6  mov     [rsp+120h+var_C8], 0
0x180106eef  lea     rcx, [rsp+120h+var_D0]
0x180106ef4  call    ??1?$auto_ptr@UMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@QEAA@XZ; std::auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>::~auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>(void)
0x180106ef9  nop
0x180106efa  lea     rcx, [rsp+120h+var_C8]; this
0x180106eff  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x180106f04  mov     rax, [rsp+120h+Context]
0x180106f09  mov     rcx, [rbp+20h+var_10]
0x180106f0d  xor     rcx, rsp; StackCookie
0x180106f10  call    __security_check_cookie
0x180106f15  mov     rdi, [rsp+120h+arg_0]
0x180106f1d  add     rsp, 120h
0x180106f24  pop     rbp
0x180106f25  retn
0x180106f26  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180106f2b  nop
0x180106f2c  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x180106f33  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180106f38  mov     [rsp+120h+var_F8], eax; unsigned int
0x180106f3c  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x180106f44  lea     r9, word_18013A0B6
0x180106f4b  lea     r8, aNoFilename; "(no filename)"
0x180106f52  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180106f57  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180106f5c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180106f63  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180106f68  call    _CxxThrowException_0
```
