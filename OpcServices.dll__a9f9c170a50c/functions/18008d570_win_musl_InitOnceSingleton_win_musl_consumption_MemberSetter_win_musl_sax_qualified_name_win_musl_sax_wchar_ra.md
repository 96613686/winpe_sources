# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DefaultType>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::DefaultType>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::DefaultType>)

- ea: `0x18008d570`
- end: `0x18008d713`
- name: `??$Get@V?$SingletonInitializer@VDefaultType@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VDefaultType@Model@win_musl@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VDefaultType@Model@win_musl@@@341@@Z`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18008d430`

## callees

- `0x1800517a0`
- `0x180079ca0`
- `0x18008d570`
- `0x1800ad644`
- `0x1800cd38c`
- `0x1800cd66c`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18008d5c1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18008d5c1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18008d69f`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18008d69f`

## string_xrefs

- `0x18008d6d1`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DefaultType>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::DefaultType>>()
{
  win_musl::detail *v0; // rcx
  win_musl::detail *v1; // rcx
  unsigned int v3; // eax
  unsigned int LastErrorAsFailHR; // [rsp+30h] [rbp-D8h]
  BOOL fPending[2]; // [rsp+48h] [rbp-C0h] BYREF
  LPVOID Context; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v7[3]; // [rsp+58h] [rbp-B0h] BYREF
  int v8; // [rsp+70h] [rbp-98h]
  _BYTE pExceptionObject[160]; // [rsp+78h] [rbp-90h] BYREF

  v7[1] = -2;
  fPending[0] = 0;
  Context = 0;
  if ( !InitOnceBeginInitialize(
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DefaultType>>::store'::`2'::s_storage,
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
    v7[2] = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DefaultType>>::store'::`2'::s_storage;
    v8 = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::DefaultType>::operator()(
      v0,
      v7);
    Context = (LPVOID)v7[0];
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DefaultType>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DefaultType>>::store'::`2'::s_storage,
            0,
            Context) )
    {
      v3 = win_musl::detail::GetLastErrorAsFailHR(v1);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1F5u,
        v3,
        (struct win_musl::TStringEllipseBase *)L"InitOnceComplete() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  return Context;
}

```

## disassembly

```asm
0x18008d570  mov     rax, rsp
0x18008d573  push    rbp
0x18008d574  lea     rbp, [rax-28h]
0x18008d578  sub     rsp, 120h
0x18008d57f  mov     [rsp+120h+var_C8], 0FFFFFFFFFFFFFFFEh
0x18008d588  mov     [rax+8], rdi
0x18008d58c  mov     rax, cs:__security_cookie
0x18008d593  xor     rax, rsp
0x18008d596  mov     [rbp+20h+var_10], rax
0x18008d59a  mov     [rsp+120h+fPending], 0
0x18008d5a2  mov     [rsp+120h+Context], 0
0x18008d5ab  lea     r9, [rsp+120h+Context]; lpContext
0x18008d5b0  lea     r8, [rsp+120h+fPending]; fPending
0x18008d5b5  xor     edx, edx; dwFlags
0x18008d5b7  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VDefaultType@Model@win_musl@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DefaultType>>::store(void)'::`2'::s_storage
0x18008d5be  mov     rcx, rdi; lpInitOnce
0x18008d5c1  call    cs:__imp_InitOnceBeginInitialize
0x18008d5c7  test    eax, eax
0x18008d5c9  jnz     short loc_18008D612
0x18008d5cb  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18008d5d0  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x18008d5d7  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x18008d5dc  mov     [rsp+120h+var_F8], eax; unsigned int
0x18008d5e0  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x18008d5e8  lea     r9, word_18013A0B6
0x18008d5ef  lea     r8, aNoFilename; "(no filename)"
0x18008d5f6  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18008d5fb  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18008d600  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18008d607  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18008d60c  call    _CxxThrowException_0
0x18008d612  cmp     [rsp+120h+fPending], 0
0x18008d617  jz      loc_18008D6A9
0x18008d61d  mov     qword ptr [rsp+120h+var_C0], rdi
0x18008d622  mov     [rsp+120h+var_B8], 0
0x18008d62a  lea     rdx, [rsp+120h+var_D0]
0x18008d62f  call    ??R?$SingletonInitializer@VDefaultType@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$auto_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::DefaultType>::operator()(void)
0x18008d634  nop
0x18008d635  mov     rax, [rsp+120h+var_D0]
0x18008d63a  mov     [rsp+120h+Context], rax
0x18008d63f  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VDefaultType@Model@win_musl@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x18008d646  call    atexit
0x18008d64b  test    eax, eax
0x18008d64d  jz      short loc_18008D695
0x18008d64f  lea     rax, aAtexitFailed; "atexit() failed"
0x18008d656  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x18008d65b  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x18008d663  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x18008d66b  lea     r9, word_18013A0B6
0x18008d672  lea     r8, aNoFilename; "(no filename)"
0x18008d679  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18008d67e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18008d683  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18008d68a  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18008d68f  call    _CxxThrowException_0
0x18008d695  mov     r8, [rsp+120h+Context]; lpContext
0x18008d69a  xor     edx, edx; dwFlags
0x18008d69c  mov     rcx, rdi; lpInitOnce
0x18008d69f  call    cs:__imp_InitOnceComplete
0x18008d6a5  test    eax, eax
0x18008d6a7  jz      short loc_18008D6CB
0x18008d6a9  mov     rax, [rsp+120h+Context]
0x18008d6ae  mov     rcx, [rbp+20h+var_10]
0x18008d6b2  xor     rcx, rsp; StackCookie
0x18008d6b5  call    __security_check_cookie
0x18008d6ba  mov     rdi, [rsp+120h+arg_0]
0x18008d6c2  add     rsp, 120h
0x18008d6c9  pop     rbp
0x18008d6ca  retn
0x18008d6cb  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18008d6d0  nop
0x18008d6d1  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x18008d6d8  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x18008d6dd  mov     [rsp+120h+var_F8], eax; unsigned int
0x18008d6e1  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x18008d6e9  lea     r9, word_18013A0B6
0x18008d6f0  lea     r8, aNoFilename; "(no filename)"
0x18008d6f7  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18008d6fc  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18008d701  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18008d708  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18008d70d  call    _CxxThrowException_0
```
