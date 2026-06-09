# win_musl::InitOnceSingleton_xpsutil::string_pool__xpsutil::string_pool::getInstance_::_2_::StringPoolSingletonIdentifier_::Get__xpsutil::string_pool::getInstance_::_2_::StringPoolSingletonInitializer_

- ea: `0x18001ad1c`
- end: `0x18001aedc`
- name: `win_musl::InitOnceSingleton_xpsutil::string_pool__xpsutil::string_pool::getInstance_::_2_::StringPoolSingletonIdentifier_::Get__xpsutil::string_pool::getInstance_::_2_::StringPoolSingletonInitializer_`
- size: `448`
- prototype: ``
- caller_count: `11`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001a9e8`
- `0x18001aad8`
- `0x18001aba8`
- `0x18001b788`
- `0x18002facc`
- `0x18002fb78`
- `0x18002fbb4`
- `0x18009b8b4`
- `0x1800adeb4`
- `0x1801671b4`
- `0x18017b294`

## callees

- `0x180012450`
- `0x18001ad1c`
- `0x1800ad884`
- `0x180115e70`
- `0x180134b70`
- `0x180134f20`
- `0x1801359ce`
- `0x1801b52e4`
- `0x1801b5300`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001ae5f`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001ae5f`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001ad63`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001ad63`

## string_xrefs

- `0x18001ae9a`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton_xpsutil::string_pool__xpsutil::string_pool::getInstance_::_2_::StringPoolSingletonIdentifier_::Get__xpsutil::string_pool::getInstance_::_2_::StringPoolSingletonInitializer_()
{
  win_musl::detail *v0; // rcx
  int LastErrorAsFailHR; // eax
  win_musl::detail *v3; // rcx
  int v4; // eax
  WINBOOL fPending; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID Context; // [rsp+48h] [rbp-B8h] BYREF
  void *v7; // [rsp+50h] [rbp-B0h] BYREF
  union _RTL_RUN_ONCE *v8; // [rsp+58h] [rbp-A8h] BYREF
  int v9; // [rsp+60h] [rbp-A0h]
  _BYTE pExceptionObject[160]; // [rsp+70h] [rbp-90h] BYREF

  fPending = 0;
  Context = 0;
  if ( !InitOnceBeginInitialize(&InitOnce, 0, &fPending, &Context) )
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
    v8 = &InitOnce;
    v9 = 0;
    xpsutil::string_pool::getInstance_::_2_::StringPoolSingletonInitializer::operator()(v0, &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton_xpsutil::string_pool__xpsutil::string_pool::getInstance_::_2_::StringPoolSingletonIdentifier_::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)pExceptionObject,
        0x1EAu,
        -2147024882,
        (__int64)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(&InitOnce, 0, Context) )
    {
      v4 = win_musl::detail::GetLastErrorAsFailHR(v3);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)pExceptionObject,
        0x1F5u,
        v4,
        (__int64)L"InitOnceComplete() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v7 = 0;
    v8 = 0;
    std::unique_ptr<xpsutil::string_pool>::~unique_ptr<xpsutil::string_pool>(&v7);
    win_musl::InitOnceGuard::~InitOnceGuard((win_musl::InitOnceGuard *)&v8);
  }
  return Context;
}

```

## disassembly

```asm
0x18001ad1c  mov     [rsp-8+arg_0], rdi
0x18001ad21  push    rbp
0x18001ad22  lea     rbp, [rsp-20h]
0x18001ad27  sub     rsp, 120h
0x18001ad2e  mov     rax, cs:__security_cookie
0x18001ad35  xor     rax, rsp
0x18001ad38  mov     [rbp+20h+var_10], rax
0x18001ad3c  mov     [rsp+120h+fPending], 0
0x18001ad44  mov     [rsp+120h+Context], 0
0x18001ad4d  lea     r9, [rsp+120h+Context]; lpContext
0x18001ad52  lea     r8, [rsp+120h+fPending]; fPending
0x18001ad57  xor     edx, edx; dwFlags
0x18001ad59  lea     rdi, InitOnce
0x18001ad60  mov     rcx, rdi; lpInitOnce
0x18001ad63  call    cs:__imp_InitOnceBeginInitialize
0x18001ad69  test    eax, eax
0x18001ad6b  jz      short loc_18001AD96
0x18001ad6d  cmp     [rsp+120h+fPending], 0
0x18001ad72  jnz     short loc_18001ADDD
0x18001ad74  mov     rax, [rsp+120h+Context]
0x18001ad79  mov     rcx, [rbp+20h+var_10]
0x18001ad7d  xor     rcx, rsp; StackCookie
0x18001ad80  call    __security_check_cookie
0x18001ad85  mov     rdi, [rsp+120h+arg_0]
0x18001ad8d  add     rsp, 120h
0x18001ad94  pop     rbp
0x18001ad95  retn
0x18001ad96  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18001ad9b  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x18001ada2  mov     [rsp+120h+var_F0], rcx; __int64
0x18001ada7  mov     [rsp+120h+var_F8], eax; int
0x18001adab  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x18001adb3  lea     r9, Src
0x18001adba  lea     r8, aNoFilename; "(no filename)"
0x18001adc1  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18001adc6  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18001adcb  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18001add2  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18001add7  call    _CxxThrowException_0
0x18001addd  mov     [rsp+120h+var_C8], rdi
0x18001ade2  mov     [rsp+120h+var_C0], 0
0x18001adea  lea     rdx, [rsp+120h+var_D0]
0x18001adef  call    _xpsutil__string_pool__getInstance____2___StringPoolSingletonInitializer__operator__
0x18001adf4  nop
0x18001adf5  mov     rax, [rsp+120h+var_D0]
0x18001adfa  mov     [rsp+120h+Context], rax
0x18001adff  lea     rcx, win_musl__InitOnceSingleton_xpsutil__string_pool__xpsutil__string_pool__getInstance____2___StringPoolSingletonIdentifier___Cleanup; void (__cdecl *)()
0x18001ae06  call    atexit
0x18001ae0b  test    eax, eax
0x18001ae0d  jz      short loc_18001AE55
0x18001ae0f  lea     rax, aAtexitFailed; "atexit() failed"
0x18001ae16  mov     [rsp+120h+var_F0], rax; __int64
0x18001ae1b  mov     [rsp+120h+var_F8], 8007000Eh; int
0x18001ae23  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x18001ae2b  lea     r9, Src
0x18001ae32  lea     r8, aNoFilename; "(no filename)"
0x18001ae39  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18001ae3e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18001ae43  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18001ae4a  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18001ae4f  call    _CxxThrowException_0
0x18001ae55  mov     r8, [rsp+120h+Context]; lpContext
0x18001ae5a  xor     edx, edx; dwFlags
0x18001ae5c  mov     rcx, rdi; lpInitOnce
0x18001ae5f  call    cs:__imp_InitOnceComplete
0x18001ae65  test    eax, eax
0x18001ae67  jz      short loc_18001AE95
0x18001ae69  mov     [rsp+120h+var_D0], 0
0x18001ae72  mov     [rsp+120h+var_C8], 0
0x18001ae7b  lea     rcx, [rsp+120h+var_D0]
0x18001ae80  call    ??1?$unique_ptr@Vstring_pool@xpsutil@@U?$default_delete@Vstring_pool@xpsutil@@@std@@@std@@QEAA@XZ; std::unique_ptr<xpsutil::string_pool>::~unique_ptr<xpsutil::string_pool>(void)
0x18001ae85  nop
0x18001ae86  lea     rcx, [rsp+120h+var_C8]; this
0x18001ae8b  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x18001ae90  jmp     loc_18001AD74
0x18001ae95  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18001ae9a  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x18001aea1  mov     [rsp+120h+var_F0], rcx; __int64
0x18001aea6  mov     [rsp+120h+var_F8], eax; int
0x18001aeaa  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x18001aeb2  lea     r9, Src
0x18001aeb9  lea     r8, aNoFilename; "(no filename)"
0x18001aec0  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18001aec5  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18001aeca  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18001aed1  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18001aed6  call    _CxxThrowException_0
```
