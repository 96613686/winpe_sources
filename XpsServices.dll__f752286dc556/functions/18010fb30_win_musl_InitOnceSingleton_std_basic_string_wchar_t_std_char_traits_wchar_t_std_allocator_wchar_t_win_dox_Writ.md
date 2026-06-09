# win_musl::InitOnceSingleton_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t_____win_dox::WritePageToStream_::_2_::SignatureStringSingletonIdentifier_::Get__win_dox::WritePageToStream_::_2_::SignatureStringSingletonInitializer_

- ea: `0x18010fb30`
- end: `0x18010fcf0`
- name: `win_musl::InitOnceSingleton_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t_____win_dox::WritePageToStream_::_2_::SignatureStringSingletonIdentifier_::Get__win_dox::WritePageToStream_::_2_::SignatureStringSingletonInitializer_`
- size: `448`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180054360`

## callees

- `0x180012450`
- `0x1800ad884`
- `0x18010fb30`
- `0x180115e70`
- `0x180134b70`
- `0x180134f20`
- `0x1801359ce`
- `0x1801a7e08`
- `0x1801a8128`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18010fc55`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18010fc55`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18010fb77`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18010fb77`

## string_xrefs

- `0x18010fcae`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t_____win_dox::WritePageToStream_::_2_::SignatureStringSingletonIdentifier_::Get__win_dox::WritePageToStream_::_2_::SignatureStringSingletonInitializer_()
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
  if ( !InitOnceBeginInitialize(&stru_1802291B8, 0, &fPending, &Context) )
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
    v8 = &stru_1802291B8;
    v9 = 0;
    win_dox::WritePageToStream_::_2_::SignatureStringSingletonInitializer::operator()(v0, &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t_____win_dox::WritePageToStream_::_2_::SignatureStringSingletonIdentifier_::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)pExceptionObject,
        0x1EAu,
        -2147024882,
        (__int64)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(&stru_1802291B8, 0, Context) )
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
    std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(&v7);
    win_musl::InitOnceGuard::~InitOnceGuard((win_musl::InitOnceGuard *)&v8);
  }
  return Context;
}

```

## disassembly

```asm
0x18010fb30  mov     [rsp-8+arg_0], rdi
0x18010fb35  push    rbp
0x18010fb36  lea     rbp, [rsp-20h]
0x18010fb3b  sub     rsp, 120h
0x18010fb42  mov     rax, cs:__security_cookie
0x18010fb49  xor     rax, rsp
0x18010fb4c  mov     [rbp+20h+var_10], rax
0x18010fb50  mov     [rsp+120h+fPending], 0
0x18010fb58  mov     [rsp+120h+Context], 0
0x18010fb61  lea     r9, [rsp+120h+Context]; lpContext
0x18010fb66  lea     r8, [rsp+120h+fPending]; fPending
0x18010fb6b  xor     edx, edx; dwFlags
0x18010fb6d  lea     rdi, stru_1802291B8
0x18010fb74  mov     rcx, rdi; lpInitOnce
0x18010fb77  call    cs:__imp_InitOnceBeginInitialize
0x18010fb7d  test    eax, eax
0x18010fb7f  jnz     short loc_18010FBC8
0x18010fb81  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18010fb86  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x18010fb8d  mov     [rsp+120h+var_F0], rcx; __int64
0x18010fb92  mov     [rsp+120h+var_F8], eax; int
0x18010fb96  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x18010fb9e  lea     r9, Src
0x18010fba5  lea     r8, aNoFilename; "(no filename)"
0x18010fbac  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18010fbb1  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18010fbb6  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18010fbbd  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18010fbc2  call    _CxxThrowException_0
0x18010fbc8  cmp     [rsp+120h+fPending], 0
0x18010fbcd  jz      loc_18010FC86
0x18010fbd3  mov     [rsp+120h+var_C8], rdi
0x18010fbd8  mov     [rsp+120h+var_C0], 0
0x18010fbe0  lea     rdx, [rsp+120h+var_D0]
0x18010fbe5  call    _win_dox__WritePageToStream____2___SignatureStringSingletonInitializer__operator__
0x18010fbea  nop
0x18010fbeb  mov     rax, [rsp+120h+var_D0]
0x18010fbf0  mov     [rsp+120h+Context], rax
0x18010fbf5  lea     rcx, win_musl__InitOnceSingleton_std__basic_string_wchar_t_std__char_traits_wchar_t__std__allocator_wchar_t_____win_dox__WritePageToStream____2___SignatureStringSingletonIdentifier___Cleanup; void (__cdecl *)()
0x18010fbfc  call    atexit
0x18010fc01  test    eax, eax
0x18010fc03  jz      short loc_18010FC4B
0x18010fc05  lea     rax, aAtexitFailed; "atexit() failed"
0x18010fc0c  mov     [rsp+120h+var_F0], rax; __int64
0x18010fc11  mov     [rsp+120h+var_F8], 8007000Eh; int
0x18010fc19  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x18010fc21  lea     r9, Src
0x18010fc28  lea     r8, aNoFilename; "(no filename)"
0x18010fc2f  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18010fc34  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18010fc39  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18010fc40  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18010fc45  call    _CxxThrowException_0
0x18010fc4b  mov     r8, [rsp+120h+Context]; lpContext
0x18010fc50  xor     edx, edx; dwFlags
0x18010fc52  mov     rcx, rdi; lpInitOnce
0x18010fc55  call    cs:__imp_InitOnceComplete
0x18010fc5b  test    eax, eax
0x18010fc5d  jz      short loc_18010FCA8
0x18010fc5f  mov     [rsp+120h+var_D0], 0
0x18010fc68  mov     [rsp+120h+var_C8], 0
0x18010fc71  lea     rcx, [rsp+120h+var_D0]
0x18010fc76  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x18010fc7b  nop
0x18010fc7c  lea     rcx, [rsp+120h+var_C8]; this
0x18010fc81  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x18010fc86  mov     rax, [rsp+120h+Context]
0x18010fc8b  mov     rcx, [rbp+20h+var_10]
0x18010fc8f  xor     rcx, rsp; StackCookie
0x18010fc92  call    __security_check_cookie
0x18010fc97  mov     rdi, [rsp+120h+arg_0]
0x18010fc9f  add     rsp, 120h
0x18010fca6  pop     rbp
0x18010fca7  retn
0x18010fca8  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18010fcad  nop
0x18010fcae  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x18010fcb5  mov     [rsp+120h+var_F0], rcx; __int64
0x18010fcba  mov     [rsp+120h+var_F8], eax; int
0x18010fcbe  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x18010fcc6  lea     r9, Src
0x18010fccd  lea     r8, aNoFilename; "(no filename)"
0x18010fcd4  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18010fcd9  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18010fcde  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18010fce5  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18010fcea  call    _CxxThrowException_0
```
