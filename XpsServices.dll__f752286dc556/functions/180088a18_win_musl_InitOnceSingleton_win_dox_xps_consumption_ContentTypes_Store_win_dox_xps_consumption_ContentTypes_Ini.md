# win_musl::InitOnceSingleton_win_dox::xps_consumption::ContentTypes::Store__win_dox::xps_consumption::ContentTypes::InitOnce_::_2_::UniqueIdentifier_::Get__win_dox::xps_consumption::ContentTypes::InitOnce_::_2_::Initializer_

- ea: `0x180088a18`
- end: `0x180088c5c`
- name: `win_musl::InitOnceSingleton_win_dox::xps_consumption::ContentTypes::Store__win_dox::xps_consumption::ContentTypes::InitOnce_::_2_::UniqueIdentifier_::Get__win_dox::xps_consumption::ContentTypes::InitOnce_::_2_::Initializer_`
- size: `580`
- prototype: ``
- caller_count: `12`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800878dc`
- `0x18008806c`
- `0x1800c6b80`
- `0x1800c7c80`
- `0x1800c8b54`
- `0x1800c92a4`
- `0x1800d58f0`
- `0x1800d5b9c`
- `0x180112938`
- `0x180112bd4`
- `0x1801941dc`
- `0x18019d97c`

## callees

- `0x180012450`
- `0x18003c7f8`
- `0x180088a18`
- `0x1800c33b0`
- `0x180115e70`
- `0x180134b70`
- `0x180134f20`
- `0x18013545a`
- `0x1801355e4`
- `0x1801359ce`
- `0x1801c7010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180088adf`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180088adf`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180088a64`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180088a64`

## string_xrefs

- `0x180088af2`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton_win_dox::xps_consumption::ContentTypes::Store__win_dox::xps_consumption::ContentTypes::InitOnce_::_2_::UniqueIdentifier_::Get__win_dox::xps_consumption::ContentTypes::InitOnce_::_2_::Initializer_()
{
  win_musl::detail *v0; // rcx
  unsigned int v1; // r8d
  win_musl::detail *v3; // rcx
  int v4; // edi
  int LastErrorAsFailHR; // eax
  WINBOOL fPending; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID Context; // [rsp+48h] [rbp-B8h] BYREF
  const char *v8; // [rsp+50h] [rbp-B0h] BYREF
  char v9; // [rsp+58h] [rbp-A8h]
  int v10; // [rsp+59h] [rbp-A7h]
  __int16 v11; // [rsp+5Dh] [rbp-A3h]
  char v12; // [rsp+5Fh] [rbp-A1h]
  _QWORD v13[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v14; // [rsp+70h] [rbp-90h]
  void **pExceptionObject; // [rsp+80h] [rbp-80h] BYREF
  __int128 v16; // [rsp+88h] [rbp-78h] BYREF
  _DWORD v17[2]; // [rsp+98h] [rbp-68h] BYREF
  const char *v18; // [rsp+A0h] [rbp-60h]
  _BYTE v19[56]; // [rsp+A8h] [rbp-58h] BYREF
  GUID v20; // [rsp+E0h] [rbp-20h]
  int v21; // [rsp+108h] [rbp+8h]

  fPending = 0;
  Context = 0;
  if ( !InitOnceBeginInitialize(&stru_180229280, 0, &fPending, &Context) )
  {
    LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR(v0);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)&pExceptionObject,
      0x1DCu,
      LastErrorAsFailHR,
      (__int64)L"InitOnceBeginInitialize() failed");
    throw (SplException::THResultException *)&pExceptionObject;
  }
  if ( fPending )
  {
    v13[1] = &stru_180229280;
    v14 = 0;
    win_dox::xps_consumption::ContentTypes::InitOnce_::_2_::Initializer::operator()((__int64)v0, (char *)v13, v1);
    Context = (LPVOID)v13[0];
    if ( atexit(win_musl::InitOnceSingleton_win_dox::xps_consumption::ContentTypes::Store__win_dox::xps_consumption::ContentTypes::InitOnce_::_2_::UniqueIdentifier_::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)&pExceptionObject,
        0x1EAu,
        -2147024882,
        (__int64)L"atexit() failed");
      throw (SplException::THResultException *)&pExceptionObject;
    }
    if ( !InitOnceComplete(&stru_180229280, 0, Context) )
    {
      v4 = win_musl::detail::GetLastErrorAsFailHR(v3);
      win_musl::DebugLogHelper("(no filename)", &Src, 501, 1024, v4, L"InitOnceComplete() failed");
      pExceptionObject = &std::exception::`vftable';
      v16 = 0;
      v8 = "Unexpected HRESULT returned by API";
      v9 = 1;
      v10 = 0;
      v11 = 0;
      v12 = 0;
      o___std_exception_copy_0(&v8, &v16);
      memset_0(v19, 0, 0x68u);
      v18 = "(no filename)";
      v17[1] = 501;
      v21 = -1;
      pExceptionObject = &SplException::THResultException::`vftable';
      v17[0] = -2147467259;
      if ( v4 )
        v17[0] = v4;
      v20 = GUID_NULL;
      if ( SplException::Functions )
        v21 = SplException::Functions(v17);
      throw (SplException::THResultException *)&pExceptionObject;
    }
  }
  return Context;
}

```

## disassembly

```asm
0x180088a18  mov     [rsp-8+arg_0], rbx
0x180088a1d  mov     [rsp-8+arg_8], rdi
0x180088a22  push    rbp
0x180088a23  lea     rbp, [rsp-30h]
0x180088a28  sub     rsp, 130h
0x180088a2f  mov     rax, cs:__security_cookie
0x180088a36  xor     rax, rsp
0x180088a39  mov     [rbp+30h+var_10], rax
0x180088a3d  mov     [rsp+130h+fPending], 0
0x180088a45  mov     [rsp+130h+Context], 0
0x180088a4e  lea     r9, [rsp+130h+Context]; lpContext
0x180088a53  lea     r8, [rsp+130h+fPending]; fPending
0x180088a58  xor     edx, edx; dwFlags
0x180088a5a  lea     rbx, stru_180229280
0x180088a61  mov     rcx, rbx; lpInitOnce
0x180088a64  call    cs:__imp_InitOnceBeginInitialize
0x180088a6a  test    eax, eax
0x180088a6c  jz      loc_180088BD3
0x180088a72  cmp     [rsp+130h+fPending], 0
0x180088a77  jnz     short loc_180088A9F
0x180088a79  mov     rax, [rsp+130h+Context]
0x180088a7e  mov     rcx, [rbp+30h+var_10]
0x180088a82  xor     rcx, rsp; StackCookie
0x180088a85  call    __security_check_cookie
0x180088a8a  lea     r11, [rsp+130h+var_s0]
0x180088a92  mov     rbx, [r11+10h]
0x180088a96  mov     rdi, [r11+18h]
0x180088a9a  mov     rsp, r11
0x180088a9d  pop     rbp
0x180088a9e  retn
0x180088a9f  mov     [rsp+130h+var_C8], rbx
0x180088aa4  mov     [rsp+130h+var_C0], 0
0x180088aac  lea     rdx, [rsp+130h+var_D0]
0x180088ab1  call    _win_dox__xps_consumption__ContentTypes__InitOnce____2___Initializer__operator__
0x180088ab6  nop
0x180088ab7  mov     rax, [rsp+130h+var_D0]
0x180088abc  mov     [rsp+130h+Context], rax
0x180088ac1  lea     rcx, win_musl__InitOnceSingleton_win_dox__xps_consumption__ContentTypes__Store__win_dox__xps_consumption__ContentTypes__InitOnce____2___UniqueIdentifier___Cleanup; void (__cdecl *)()
0x180088ac8  call    atexit
0x180088acd  test    eax, eax
0x180088acf  jnz     loc_180088C18
0x180088ad5  mov     r8, [rsp+130h+Context]; lpContext
0x180088ada  xor     edx, edx; dwFlags
0x180088adc  mov     rcx, rbx; lpInitOnce
0x180088adf  call    cs:__imp_InitOnceComplete
0x180088ae5  test    eax, eax
0x180088ae7  jz      short loc_180088AEB
0x180088ae9  jmp     short loc_180088A79
0x180088aeb  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180088af0  mov     edi, eax
0x180088af2  lea     rax, aInitoncecomple; "InitOnceComplete() failed"
0x180088af9  mov     qword ptr [rsp+130h+var_108], rax
0x180088afe  mov     [rsp+130h+var_110], edi
0x180088b02  mov     r9d, 400h
0x180088b08  mov     r8d, 1F5h
0x180088b0e  lea     rdx, Src
0x180088b15  lea     rbx, aNoFilename; "(no filename)"
0x180088b1c  mov     rcx, rbx
0x180088b1f  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x180088b24  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180088b2b  mov     [rbp+30h+pExceptionObject], rax
0x180088b2f  xorps   xmm0, xmm0
0x180088b32  movups  [rbp+30h+var_A8], xmm0
0x180088b36  lea     rax, aUnexpectedHres; "Unexpected HRESULT returned by API"
0x180088b3d  mov     [rsp+130h+var_E0], rax
0x180088b42  mov     [rsp+130h+var_D8], 1
0x180088b47  xor     eax, eax
0x180088b49  mov     [rsp+130h+var_D7], eax
0x180088b4d  mov     [rsp+130h+var_D3], ax
0x180088b52  mov     [rsp+130h+var_D1], al
0x180088b56  lea     rdx, [rbp+30h+var_A8]
0x180088b5a  lea     rcx, [rsp+130h+var_E0]
0x180088b5f  call    _o___std_exception_copy_0
0x180088b64  xor     edx, edx; Val
0x180088b66  lea     r8d, [rdx+68h]; Size
0x180088b6a  lea     rcx, [rbp+30h+var_88]; void *
0x180088b6e  call    memset_0
0x180088b73  mov     [rbp+30h+var_90], rbx
0x180088b77  mov     [rbp+30h+var_94], 1F5h
0x180088b7e  mov     [rbp+30h+var_28], 0FFFFFFFFh
0x180088b85  lea     rax, ??_7THResultException@SplException@@6B@; const SplException::THResultException::`vftable'
0x180088b8c  mov     [rbp+30h+pExceptionObject], rax
0x180088b90  mov     [rbp+30h+var_98], 80004005h
0x180088b97  test    edi, edi
0x180088b99  jz      short loc_180088B9E
0x180088b9b  mov     [rbp+30h+var_98], edi
0x180088b9e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180088ba5  movdqu  [rbp+30h+var_50], xmm0
0x180088baa  mov     rax, cs:?Functions@SplException@@3UExceptionTableFunctions@1@A; SplException::ExceptionTableFunctions SplException::Functions
0x180088bb1  test    rax, rax
0x180088bb4  jz      short loc_180088BC2
0x180088bb6  lea     rcx, [rbp+30h+var_98]
0x180088bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088bbf  mov     [rbp+30h+var_28], eax
0x180088bc2  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180088bc9  lea     rcx, [rbp+30h+pExceptionObject]; pExceptionObject
0x180088bcd  call    _CxxThrowException_0
0x180088bd3  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180088bd8  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x180088bdf  mov     [rsp+130h+var_100], rcx; __int64
0x180088be4  mov     [rsp+130h+var_108], eax; int
0x180088be8  mov     [rsp+130h+var_110], 1DCh; unsigned int
0x180088bf0  lea     r9, Src
0x180088bf7  lea     r8, aNoFilename; "(no filename)"
0x180088bfe  lea     rcx, [rbp+30h+pExceptionObject]; this
0x180088c02  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180088c07  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180088c0e  lea     rcx, [rbp+30h+pExceptionObject]; pExceptionObject
0x180088c12  call    _CxxThrowException_0
0x180088c18  lea     rax, aAtexitFailed; "atexit() failed"
0x180088c1f  mov     [rsp+130h+var_100], rax; __int64
0x180088c24  mov     [rsp+130h+var_108], 8007000Eh; int
0x180088c2c  mov     [rsp+130h+var_110], 1EAh; unsigned int
0x180088c34  lea     r9, Src
0x180088c3b  lea     r8, aNoFilename; "(no filename)"
0x180088c42  lea     rcx, [rbp+30h+pExceptionObject]; this
0x180088c46  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180088c4b  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180088c52  lea     rcx, [rbp+30h+pExceptionObject]; pExceptionObject
0x180088c56  call    _CxxThrowException_0
```
