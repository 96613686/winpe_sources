# SystemXamlHostBehavior::ParseExperienceValueSet(winrt::Windows::Foundation::Collections::ValueSet const &)

- ea: `0x180047a98`
- end: `0x180047ca9`
- name: `?ParseExperienceValueSet@SystemXamlHostBehavior@@AEAAXAEBUValueSet@Collections@Foundation@Windows@winrt@@@Z`
- size: `529`
- prototype: `void __fastcall(SystemXamlHostBehavior *__hidden this, const struct winrt::Windows::Foundation::Collections::ValueSet *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18004a400`

## callees

- `0x180002b20`
- `0x1800043f4`
- `0x18000d810`
- `0x180020cac`
- `0x180022150`
- `0x180023814`
- `0x180047a98`

## string_xrefs

- `0x180047bf0`: `pcshell\shell\uxframe\dll\SystemXamlHostBehavior.h`
- `0x180047c2c`: `pcshell\shell\uxframe\dll\SystemXamlHostBehavior.h`
- `0x180047c68`: `pcshell\shell\uxframe\dll\SystemXamlHostBehavior.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall SystemXamlHostBehavior::ParseExperienceValueSet(
        SystemXamlHostBehavior *this,
        const struct winrt::Windows::Foundation::Collections::ValueSet *a2)
{
  const char *v4; // [rsp+28h] [rbp-28h]
  _BYTE v5[8]; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v6[8]; // [rsp+38h] [rbp-18h] BYREF
  _BYTE v7[8]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  winrt::hstring::hstring((winrt::hstring *)v6, L"AnimationType");
  ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(v7, v6, a2);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v6);
  if ( (unsigned __int8)winrt::operator==(v7, L"None") )
  {
LABEL_17:
    *((_DWORD *)this + 32) = 0;
    goto LABEL_18;
  }
  if ( !(unsigned __int8)winrt::operator==(v7, L"Slide") )
  {
    if ( (unsigned __int8)winrt::operator==(v7, L"Fade") )
      wil::details::in1diag3::FailFast_HrMsg(
        retaddr,
        (void *)0x220,
        (unsigned int)"pcshell\\shell\\uxframe\\dll\\SystemXamlHostBehavior.h",
        (const char *)0x80004001LL,
        (int)"Stock fade animations aren't implemented yet",
        v4);
    if ( (unsigned __int8)winrt::operator==(v7, L"Custom") )
      wil::details::in1diag3::FailFast_HrMsg(
        retaddr,
        (void *)0x225,
        (unsigned int)"pcshell\\shell\\uxframe\\dll\\SystemXamlHostBehavior.h",
        (const char *)0x80004001LL,
        (int)"Custom animations aren't implemented yet",
        v4);
    goto LABEL_17;
  }
  *((_DWORD *)this + 32) = 1;
  winrt::hstring::hstring((winrt::hstring *)v5, L"SlideAnimationDirection");
  ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(v6, v5, a2);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v5);
  if ( (unsigned __int8)winrt::operator==(v6, L"Left") )
  {
    *((_DWORD *)this + 33) = 0;
  }
  else if ( (unsigned __int8)winrt::operator==(v6, L"Right") )
  {
    *((_DWORD *)this + 33) = 1;
  }
  else if ( (unsigned __int8)winrt::operator==(v6, L"Up") )
  {
    *((_DWORD *)this + 33) = 2;
  }
  else
  {
    if ( !(unsigned __int8)winrt::operator==(v6, L"Down") )
      wil::details::in1diag3::FailFast_HrMsg(
        retaddr,
        (void *)0x21A,
        (unsigned int)"pcshell\\shell\\uxframe\\dll\\SystemXamlHostBehavior.h",
        (const char *)0x80070057LL,
        (int)"Must specify a valid SlideAnimationDirection if an AnimationType==Slide",
        v4);
    *((_DWORD *)this + 33) = 3;
  }
  winrt::handle_type<winrt::impl::hstring_traits>::close(v6);
LABEL_18:
  winrt::handle_type<winrt::impl::hstring_traits>::close(v7);
}

```

## disassembly

```asm
0x180047a98  mov     [rsp-8+arg_10], rbx
0x180047a9d  mov     [rsp-8+arg_18], rdi
0x180047aa2  push    rbp
0x180047aa3  mov     rbp, rsp
0x180047aa6  sub     rsp, 50h
0x180047aaa  mov     rax, cs:__security_cookie
0x180047ab1  xor     rax, rsp
0x180047ab4  mov     [rbp+var_8], rax
0x180047ab8  mov     rdi, rdx
0x180047abb  mov     rbx, rcx
0x180047abe  lea     rdx, aAnimationtype; "AnimationType"
0x180047ac5  lea     rcx, [rbp+var_18]; this
0x180047ac9  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x180047ace  nop
0x180047acf  mov     r8, rdi
0x180047ad2  lea     rdx, [rbp+var_18]
0x180047ad6  lea     rcx, [rbp+var_10]
0x180047ada  call    ??$try_get_value@Uhstring@winrt@@UValueSet@Collections@Foundation@Windows@2@@ValueSetUtils@@YA?AUhstring@winrt@@AEBU12@AEBUValueSet@Collections@Foundation@Windows@2@@Z; ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x180047adf  nop
0x180047ae0  lea     rcx, [rbp+var_18]
0x180047ae4  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180047ae9  lea     rdx, aNone; "None"
0x180047af0  lea     rcx, [rbp+var_10]
0x180047af4  call    ??8winrt@@YA_NAEBUhstring@0@PEB_W@Z; winrt::operator==(winrt::hstring const &,wchar_t const *)
0x180047af9  test    al, al
0x180047afb  jnz     loc_180047C7A
0x180047b01  lea     rdx, aSlide; "Slide"
0x180047b08  lea     rcx, [rbp+var_10]
0x180047b0c  call    ??8winrt@@YA_NAEBUhstring@0@PEB_W@Z; winrt::operator==(winrt::hstring const &,wchar_t const *)
0x180047b11  test    al, al
0x180047b13  jz      loc_180047C02
0x180047b19  mov     dword ptr [rbx+80h], 1
0x180047b23  lea     rdx, aSlideanimation; "SlideAnimationDirection"
0x180047b2a  lea     rcx, [rbp+var_20]; this
0x180047b2e  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x180047b33  nop
0x180047b34  mov     r8, rdi
0x180047b37  lea     rdx, [rbp+var_20]
0x180047b3b  lea     rcx, [rbp+var_18]
0x180047b3f  call    ??$try_get_value@Uhstring@winrt@@UValueSet@Collections@Foundation@Windows@2@@ValueSetUtils@@YA?AUhstring@winrt@@AEBU12@AEBUValueSet@Collections@Foundation@Windows@2@@Z; ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x180047b44  nop
0x180047b45  lea     rcx, [rbp+var_20]
0x180047b49  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180047b4e  lea     rdx, aLeft; "Left"
0x180047b55  lea     rcx, [rbp+var_18]
0x180047b59  call    ??8winrt@@YA_NAEBUhstring@0@PEB_W@Z; winrt::operator==(winrt::hstring const &,wchar_t const *)
0x180047b5e  test    al, al
0x180047b60  jz      short loc_180047B6E
0x180047b62  mov     dword ptr [rbx+84h], 0
0x180047b6c  jmp     short loc_180047BCC
0x180047b6e  lea     rdx, aRight; "Right"
0x180047b75  lea     rcx, [rbp+var_18]
0x180047b79  call    ??8winrt@@YA_NAEBUhstring@0@PEB_W@Z; winrt::operator==(winrt::hstring const &,wchar_t const *)
0x180047b7e  test    al, al
0x180047b80  jz      short loc_180047B8E
0x180047b82  mov     dword ptr [rbx+84h], 1
0x180047b8c  jmp     short loc_180047BCC
0x180047b8e  lea     rdx, aUp; "Up"
0x180047b95  lea     rcx, [rbp+var_18]
0x180047b99  call    ??8winrt@@YA_NAEBUhstring@0@PEB_W@Z; winrt::operator==(winrt::hstring const &,wchar_t const *)
0x180047b9e  test    al, al
0x180047ba0  jz      short loc_180047BAE
0x180047ba2  mov     dword ptr [rbx+84h], 2
0x180047bac  jmp     short loc_180047BCC
0x180047bae  lea     rdx, aDown; "Down"
0x180047bb5  lea     rcx, [rbp+var_18]
0x180047bb9  call    ??8winrt@@YA_NAEBUhstring@0@PEB_W@Z; winrt::operator==(winrt::hstring const &,wchar_t const *)
0x180047bbe  test    al, al
0x180047bc0  jz      short loc_180047BDA
0x180047bc2  mov     dword ptr [rbx+84h], 3
0x180047bcc  lea     rcx, [rbp+var_18]
0x180047bd0  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180047bd5  jmp     loc_180047C84
0x180047bda  mov     rcx, [rbp+8]; this
0x180047bde  lea     rax, aMustSpecifyAVa; "Must specify a valid SlideAnimationDire"...
0x180047be5  mov     qword ptr [rsp+50h+var_30], rax; int
0x180047bea  mov     r9d, 80070057h; char *
0x180047bf0  lea     r8, aPcshellShellUx_3; "pcshell\\shell\\uxframe\\dll\\SystemXam"...
0x180047bf7  mov     edx, 21Ah; void *
0x180047bfc  call    ?FailFast_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_HrMsg(void *,uint,char const *,long,char const *,...)
0x180047c02  lea     rdx, aFade; "Fade"
0x180047c09  lea     rcx, [rbp+var_10]
0x180047c0d  call    ??8winrt@@YA_NAEBUhstring@0@PEB_W@Z; winrt::operator==(winrt::hstring const &,wchar_t const *)
0x180047c12  test    al, al
0x180047c14  jz      short loc_180047C3E
0x180047c16  mov     rcx, [rbp+8]; this
0x180047c1a  lea     rax, aStockFadeAnima; "Stock fade animations aren't implemente"...
0x180047c21  mov     qword ptr [rsp+50h+var_30], rax; int
0x180047c26  mov     r9d, 80004001h; char *
0x180047c2c  lea     r8, aPcshellShellUx_3; "pcshell\\shell\\uxframe\\dll\\SystemXam"...
0x180047c33  mov     edx, 220h; void *
0x180047c38  call    ?FailFast_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_HrMsg(void *,uint,char const *,long,char const *,...)
0x180047c3e  lea     rdx, aCustom; "Custom"
0x180047c45  lea     rcx, [rbp+var_10]
0x180047c49  call    ??8winrt@@YA_NAEBUhstring@0@PEB_W@Z; winrt::operator==(winrt::hstring const &,wchar_t const *)
0x180047c4e  test    al, al
0x180047c50  jz      short loc_180047C7A
0x180047c52  mov     rcx, [rbp+8]; this
0x180047c56  lea     rax, aCustomAnimatio; "Custom animations aren't implemented ye"...
0x180047c5d  mov     qword ptr [rsp+50h+var_30], rax; int
0x180047c62  mov     r9d, 80004001h; char *
0x180047c68  lea     r8, aPcshellShellUx_3; "pcshell\\shell\\uxframe\\dll\\SystemXam"...
0x180047c6f  mov     edx, 225h; void *
0x180047c74  call    ?FailFast_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_HrMsg(void *,uint,char const *,long,char const *,...)
0x180047c7a  mov     dword ptr [rbx+80h], 0
0x180047c84  lea     rcx, [rbp+var_10]
0x180047c88  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180047c8d  mov     rcx, [rbp+var_8]
0x180047c91  xor     rcx, rsp; StackCookie
0x180047c94  call    __security_check_cookie
0x180047c99  mov     rbx, [rsp+50h+arg_10]
0x180047c9e  mov     rdi, [rsp+50h+arg_18]
0x180047ca3  add     rsp, 50h
0x180047ca7  pop     rbp
0x180047ca8  retn
```
