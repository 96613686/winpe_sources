# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureTime>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureTime>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureTime>)

- ea: `0x180107314`
- end: `0x1801074de`
- name: `??$Get@V?$SingletonInitializer@VSignatureTime@Model@win_dox@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VSignatureTime@Model@win_dox@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VSignatureTime@Model@win_dox@@@341@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180108970`

## callees

- `0x1800517a0`
- `0x180079ca0`
- `0x180098e2c`
- `0x1800ad628`
- `0x1800cd38c`
- `0x1800cd66c`
- `0x180107314`
- `0x1801084b4`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180107365`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180107365`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180107443`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180107443`

## string_xrefs

- `0x18010749c`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureTime>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureTime>>()
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
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureTime>>::store'::`2'::s_storage,
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
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureTime>>::store'::`2'::s_storage;
    LODWORD(v9) = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureTime>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureTime>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureTime>>::store'::`2'::s_storage,
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
0x180107314  mov     rax, rsp
0x180107317  push    rbp
0x180107318  lea     rbp, [rax-28h]
0x18010731c  sub     rsp, 120h
0x180107323  mov     [rsp+120h+var_B8], 0FFFFFFFFFFFFFFFEh
0x18010732c  mov     [rax+8], rdi
0x180107330  mov     rax, cs:__security_cookie
0x180107337  xor     rax, rsp
0x18010733a  mov     [rbp+20h+var_10], rax
0x18010733e  mov     [rsp+120h+fPending], 0
0x180107346  mov     [rsp+120h+Context], 0
0x18010734f  lea     r9, [rsp+120h+Context]; lpContext
0x180107354  lea     r8, [rsp+120h+fPending]; fPending
0x180107359  xor     edx, edx; dwFlags
0x18010735b  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VSignatureTime@Model@win_dox@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureTime>>::store(void)'::`2'::s_storage
0x180107362  mov     rcx, rdi; lpInitOnce
0x180107365  call    cs:__imp_InitOnceBeginInitialize
0x18010736b  test    eax, eax
0x18010736d  jnz     short loc_1801073B6
0x18010736f  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180107374  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x18010737b  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180107380  mov     [rsp+120h+var_F8], eax; unsigned int
0x180107384  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x18010738c  lea     r9, word_18013A0B6
0x180107393  lea     r8, aNoFilename; "(no filename)"
0x18010739a  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18010739f  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1801073a4  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1801073ab  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1801073b0  call    _CxxThrowException_0
0x1801073b6  cmp     [rsp+120h+fPending], 0
0x1801073bb  jz      loc_180107474
0x1801073c1  mov     [rsp+120h+var_C8], rdi
0x1801073c6  mov     dword ptr [rsp+120h+var_C0], 0
0x1801073ce  lea     rdx, [rsp+120h+var_D0]
0x1801073d3  call    ??R?$SingletonInitializer@VSignatureTime@Model@win_dox@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$auto_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureTime>::operator()(void)
0x1801073d8  nop
0x1801073d9  mov     rax, [rsp+120h+var_D0]
0x1801073de  mov     [rsp+120h+Context], rax
0x1801073e3  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VSignatureTime@Model@win_dox@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x1801073ea  call    atexit
0x1801073ef  test    eax, eax
0x1801073f1  jz      short loc_180107439
0x1801073f3  lea     rax, aAtexitFailed; "atexit() failed"
0x1801073fa  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x1801073ff  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x180107407  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x18010740f  lea     r9, word_18013A0B6
0x180107416  lea     r8, aNoFilename; "(no filename)"
0x18010741d  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180107422  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180107427  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18010742e  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180107433  call    _CxxThrowException_0
0x180107439  mov     r8, [rsp+120h+Context]; lpContext
0x18010743e  xor     edx, edx; dwFlags
0x180107440  mov     rcx, rdi; lpInitOnce
0x180107443  call    cs:__imp_InitOnceComplete
0x180107449  test    eax, eax
0x18010744b  jz      short loc_180107496
0x18010744d  mov     [rsp+120h+var_D0], 0
0x180107456  mov     [rsp+120h+var_C8], 0
0x18010745f  lea     rcx, [rsp+120h+var_D0]
0x180107464  call    ??1?$auto_ptr@UMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@QEAA@XZ; std::auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>::~auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>(void)
0x180107469  nop
0x18010746a  lea     rcx, [rsp+120h+var_C8]; this
0x18010746f  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x180107474  mov     rax, [rsp+120h+Context]
0x180107479  mov     rcx, [rbp+20h+var_10]
0x18010747d  xor     rcx, rsp; StackCookie
0x180107480  call    __security_check_cookie
0x180107485  mov     rdi, [rsp+120h+arg_0]
0x18010748d  add     rsp, 120h
0x180107494  pop     rbp
0x180107495  retn
0x180107496  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18010749b  nop
0x18010749c  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x1801074a3  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x1801074a8  mov     [rsp+120h+var_F8], eax; unsigned int
0x1801074ac  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x1801074b4  lea     r9, word_18013A0B6
0x1801074bb  lea     r8, aNoFilename; "(no filename)"
0x1801074c2  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1801074c7  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1801074cc  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1801074d3  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1801074d8  call    _CxxThrowException_0
```
