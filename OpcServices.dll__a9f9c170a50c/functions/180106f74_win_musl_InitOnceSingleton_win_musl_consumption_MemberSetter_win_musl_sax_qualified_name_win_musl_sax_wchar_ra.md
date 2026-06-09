# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperties>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureProperties>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureProperties>)

- ea: `0x180106f74`
- end: `0x18010713e`
- name: `??$Get@V?$SingletonInitializer@VSignatureProperties@Model@win_dox@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VSignatureProperties@Model@win_dox@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VSignatureProperties@Model@win_dox@@@341@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180108800`

## callees

- `0x1800517a0`
- `0x180079ca0`
- `0x180098e2c`
- `0x1800ad628`
- `0x1800cd38c`
- `0x1800cd66c`
- `0x180106f74`
- `0x180108340`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180106fc5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180106fc5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1801070a3`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1801070a3`

## string_xrefs

- `0x1801070fc`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperties>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureProperties>>()
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
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperties>>::store'::`2'::s_storage,
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
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperties>>::store'::`2'::s_storage;
    LODWORD(v9) = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureProperties>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperties>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperties>>::store'::`2'::s_storage,
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
0x180106f74  mov     rax, rsp
0x180106f77  push    rbp
0x180106f78  lea     rbp, [rax-28h]
0x180106f7c  sub     rsp, 120h
0x180106f83  mov     [rsp+120h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180106f8c  mov     [rax+8], rdi
0x180106f90  mov     rax, cs:__security_cookie
0x180106f97  xor     rax, rsp
0x180106f9a  mov     [rbp+20h+var_10], rax
0x180106f9e  mov     [rsp+120h+fPending], 0
0x180106fa6  mov     [rsp+120h+Context], 0
0x180106faf  lea     r9, [rsp+120h+Context]; lpContext
0x180106fb4  lea     r8, [rsp+120h+fPending]; fPending
0x180106fb9  xor     edx, edx; dwFlags
0x180106fbb  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VSignatureProperties@Model@win_dox@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperties>>::store(void)'::`2'::s_storage
0x180106fc2  mov     rcx, rdi; lpInitOnce
0x180106fc5  call    cs:__imp_InitOnceBeginInitialize
0x180106fcb  test    eax, eax
0x180106fcd  jnz     short loc_180107016
0x180106fcf  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180106fd4  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x180106fdb  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180106fe0  mov     [rsp+120h+var_F8], eax; unsigned int
0x180106fe4  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x180106fec  lea     r9, word_18013A0B6
0x180106ff3  lea     r8, aNoFilename; "(no filename)"
0x180106ffa  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180106fff  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180107004  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18010700b  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180107010  call    _CxxThrowException_0
0x180107016  cmp     [rsp+120h+fPending], 0
0x18010701b  jz      loc_1801070D4
0x180107021  mov     [rsp+120h+var_C8], rdi
0x180107026  mov     dword ptr [rsp+120h+var_C0], 0
0x18010702e  lea     rdx, [rsp+120h+var_D0]
0x180107033  call    ??R?$SingletonInitializer@VSignatureProperties@Model@win_dox@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$auto_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureProperties>::operator()(void)
0x180107038  nop
0x180107039  mov     rax, [rsp+120h+var_D0]
0x18010703e  mov     [rsp+120h+Context], rax
0x180107043  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VSignatureProperties@Model@win_dox@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x18010704a  call    atexit
0x18010704f  test    eax, eax
0x180107051  jz      short loc_180107099
0x180107053  lea     rax, aAtexitFailed; "atexit() failed"
0x18010705a  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x18010705f  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x180107067  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x18010706f  lea     r9, word_18013A0B6
0x180107076  lea     r8, aNoFilename; "(no filename)"
0x18010707d  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180107082  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180107087  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18010708e  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180107093  call    _CxxThrowException_0
0x180107099  mov     r8, [rsp+120h+Context]; lpContext
0x18010709e  xor     edx, edx; dwFlags
0x1801070a0  mov     rcx, rdi; lpInitOnce
0x1801070a3  call    cs:__imp_InitOnceComplete
0x1801070a9  test    eax, eax
0x1801070ab  jz      short loc_1801070F6
0x1801070ad  mov     [rsp+120h+var_D0], 0
0x1801070b6  mov     [rsp+120h+var_C8], 0
0x1801070bf  lea     rcx, [rsp+120h+var_D0]
0x1801070c4  call    ??1?$auto_ptr@UMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@QEAA@XZ; std::auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>::~auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>(void)
0x1801070c9  nop
0x1801070ca  lea     rcx, [rsp+120h+var_C8]; this
0x1801070cf  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x1801070d4  mov     rax, [rsp+120h+Context]
0x1801070d9  mov     rcx, [rbp+20h+var_10]
0x1801070dd  xor     rcx, rsp; StackCookie
0x1801070e0  call    __security_check_cookie
0x1801070e5  mov     rdi, [rsp+120h+arg_0]
0x1801070ed  add     rsp, 120h
0x1801070f4  pop     rbp
0x1801070f5  retn
0x1801070f6  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1801070fb  nop
0x1801070fc  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x180107103  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180107108  mov     [rsp+120h+var_F8], eax; unsigned int
0x18010710c  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x180107114  lea     r9, word_18013A0B6
0x18010711b  lea     r8, aNoFilename; "(no filename)"
0x180107122  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180107127  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18010712c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180107133  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180107138  call    _CxxThrowException_0
```
