# LiftedXamlHostBehavior::ParseExperienceValueSet(winrt::Windows::Foundation::Collections::ValueSet const &)

- ea: `0x180047848`
- end: `0x180047a8f`
- name: `?ParseExperienceValueSet@LiftedXamlHostBehavior@@AEAAXAEBUValueSet@Collections@Foundation@Windows@winrt@@@Z`
- size: `583`
- prototype: `void __fastcall(LiftedXamlHostBehavior *__hidden this, const struct winrt::Windows::Foundation::Collections::ValueSet *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18004a3c0`

## callees

- `0x180002b20`
- `0x1800043f4`
- `0x18000d0f0`
- `0x18000d810`
- `0x180017124`
- `0x180020cac`
- `0x180022150`
- `0x180023814`
- `0x180047848`

## string_xrefs

- `0x180047a1f`: `pcshell\shell\uxframe\dll\LiftedXamlHostBehavior.h`
- `0x180047a4e`: `pcshell\shell\uxframe\dll\LiftedXamlHostBehavior.h`
- `0x180047a7d`: `pcshell\shell\uxframe\dll\LiftedXamlHostBehavior.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall LiftedXamlHostBehavior::ParseExperienceValueSet(
        LiftedXamlHostBehavior *this,
        const struct winrt::Windows::Foundation::Collections::ValueSet *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  const char *v7; // [rsp+28h] [rbp-28h]
  _BYTE v8[8]; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v9[8]; // [rsp+38h] [rbp-18h] BYREF
  _BYTE v10[8]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  winrt::hstring::hstring((winrt::hstring *)v9, L"AnimationType");
  ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(v10, v9, a2);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v9);
  if ( (unsigned __int8)winrt::operator==(v10, L"None") )
    goto LABEL_16;
  if ( (unsigned __int8)winrt::operator==(v10, L"Slide") )
  {
    *((_DWORD *)this + 32) = 1;
    winrt::hstring::hstring((winrt::hstring *)v8, L"SlideAnimationDirection");
    ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(v9, v8, a2);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v8);
    if ( (unsigned __int8)winrt::operator==(v9, L"Left") )
    {
      *((_DWORD *)this + 33) = 0;
    }
    else if ( (unsigned __int8)winrt::operator==(v9, L"Right") )
    {
      *((_DWORD *)this + 33) = 1;
    }
    else if ( (unsigned __int8)winrt::operator==(v9, L"Up") )
    {
      *((_DWORD *)this + 33) = 2;
    }
    else
    {
      if ( !(unsigned __int8)winrt::operator==(v9, L"Down") )
      {
        v5 = wil::verify_hresult<long>(2147942487LL);
        wil::details::in1diag3::FailFast_HrMsg(
          retaddr,
          (void *)0x31E,
          (unsigned int)"pcshell\\shell\\uxframe\\dll\\LiftedXamlHostBehavior.h",
          (const char *)v5,
          (int)"Must specify a valid SlideAnimationDirection if an AnimationType==Slide",
          v7);
      }
      *((_DWORD *)this + 33) = 3;
    }
    winrt::handle_type<winrt::impl::hstring_traits>::close(v9);
    goto LABEL_17;
  }
  if ( (unsigned __int8)winrt::operator==(v10, L"Fade") )
  {
    v6 = wil::verify_hresult<long>(2147500033LL);
    wil::details::in1diag3::FailFast_HrMsg(
      retaddr,
      (void *)0x324,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\LiftedXamlHostBehavior.h",
      (const char *)v6,
      (int)"Stock fade animations aren't implemented yet",
      v7);
  }
  if ( !(unsigned __int8)winrt::operator==(v10, L"Custom") )
  {
LABEL_16:
    *((_DWORD *)this + 32) = 0;
    goto LABEL_17;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl) )
  {
    v4 = wil::verify_hresult<long>(2147500033LL);
    wil::details::in1diag3::FailFast_HrMsg(
      retaddr,
      (void *)0x32F,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\LiftedXamlHostBehavior.h",
      (const char *)v4,
      (int)"Custom animations aren't implemented yet",
      v7);
  }
  *((_DWORD *)this + 32) = 3;
LABEL_17:
  winrt::handle_type<winrt::impl::hstring_traits>::close(v10);
}

```

## disassembly

```asm
0x180047848  mov     [rsp-8+arg_10], rbx
0x18004784d  mov     [rsp-8+arg_18], rdi
0x180047852  push    rbp
0x180047853  mov     rbp, rsp
0x180047856  sub     rsp, 50h
0x18004785a  mov     rax, cs:__security_cookie
0x180047861  xor     rax, rsp
0x180047864  mov     [rbp+var_8], rax
0x180047868  mov     rdi, rdx
0x18004786b  mov     rbx, rcx
0x18004786e  lea     rdx, aAnimationtype; "AnimationType"
0x180047875  lea     rcx, [rbp+var_18]; this
0x180047879  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x18004787e  nop
0x18004787f  mov     r8, rdi
0x180047882  lea     rdx, [rbp+var_18]
0x180047886  lea     rcx, [rbp+var_10]
0x18004788a  call    ??$try_get_value@Uhstring@winrt@@UValueSet@Collections@Foundation@Windows@2@@ValueSetUtils@@YA?AUhstring@winrt@@AEBU12@AEBUValueSet@Collections@Foundation@Windows@2@@Z; ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x18004788f  nop
0x180047890  lea     rcx, [rbp+var_18]
0x180047894  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180047899  lea     rdx, aNone; "None"
0x1800478a0  lea     rcx, [rbp+var_10]
0x1800478a4  call    ??8winrt@@YA_NAEBUhstring@0@PEB_W@Z; winrt::operator==(winrt::hstring const &,wchar_t const *)
0x1800478a9  test    al, al
0x1800478ab  jnz     loc_1800479D3
0x1800478b1  lea     rdx, aSlide; "Slide"
0x1800478b8  lea     rcx, [rbp+var_10]
0x1800478bc  call    ??8winrt@@YA_NAEBUhstring@0@PEB_W@Z; winrt::operator==(winrt::hstring const &,wchar_t const *)
0x1800478c1  test    al, al
0x1800478c3  jz      loc_18004798B
0x1800478c9  mov     dword ptr [rbx+80h], 1
0x1800478d3  lea     rdx, aSlideanimation; "SlideAnimationDirection"
0x1800478da  lea     rcx, [rbp+var_20]; this
0x1800478de  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x1800478e3  nop
0x1800478e4  mov     r8, rdi
0x1800478e7  lea     rdx, [rbp+var_20]
0x1800478eb  lea     rcx, [rbp+var_18]
0x1800478ef  call    ??$try_get_value@Uhstring@winrt@@UValueSet@Collections@Foundation@Windows@2@@ValueSetUtils@@YA?AUhstring@winrt@@AEBU12@AEBUValueSet@Collections@Foundation@Windows@2@@Z; ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x1800478f4  nop
0x1800478f5  lea     rcx, [rbp+var_20]
0x1800478f9  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800478fe  lea     rdx, aLeft; "Left"
0x180047905  lea     rcx, [rbp+var_18]
0x180047909  call    ??8winrt@@YA_NAEBUhstring@0@PEB_W@Z; winrt::operator==(winrt::hstring const &,wchar_t const *)
0x18004790e  test    al, al
0x180047910  jz      short loc_18004791E
0x180047912  mov     dword ptr [rbx+84h], 0
0x18004791c  jmp     short loc_180047980
0x18004791e  lea     rdx, aRight; "Right"
0x180047925  lea     rcx, [rbp+var_18]
0x180047929  call    ??8winrt@@YA_NAEBUhstring@0@PEB_W@Z; winrt::operator==(winrt::hstring const &,wchar_t const *)
0x18004792e  test    al, al
0x180047930  jz      short loc_18004793E
0x180047932  mov     dword ptr [rbx+84h], 1
0x18004793c  jmp     short loc_180047980
0x18004793e  lea     rdx, aUp; "Up"
0x180047945  lea     rcx, [rbp+var_18]
0x180047949  call    ??8winrt@@YA_NAEBUhstring@0@PEB_W@Z; winrt::operator==(winrt::hstring const &,wchar_t const *)
0x18004794e  test    al, al
0x180047950  jz      short loc_18004795E
0x180047952  mov     dword ptr [rbx+84h], 2
0x18004795c  jmp     short loc_180047980
0x18004795e  lea     rdx, aDown; "Down"
0x180047965  lea     rcx, [rbp+var_18]
0x180047969  call    ??8winrt@@YA_NAEBUhstring@0@PEB_W@Z; winrt::operator==(winrt::hstring const &,wchar_t const *)
0x18004796e  test    al, al
0x180047970  jz      loc_180047A31
0x180047976  mov     dword ptr [rbx+84h], 3
0x180047980  lea     rcx, [rbp+var_18]
0x180047984  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180047989  jmp     short loc_1800479DD
0x18004798b  lea     rdx, aFade; "Fade"
0x180047992  lea     rcx, [rbp+var_10]
0x180047996  call    ??8winrt@@YA_NAEBUhstring@0@PEB_W@Z; winrt::operator==(winrt::hstring const &,wchar_t const *)
0x18004799b  test    al, al
0x18004799d  jnz     loc_180047A60
0x1800479a3  lea     rdx, aCustom; "Custom"
0x1800479aa  lea     rcx, [rbp+var_10]
0x1800479ae  call    ??8winrt@@YA_NAEBUhstring@0@PEB_W@Z; winrt::operator==(winrt::hstring const &,wchar_t const *)
0x1800479b3  test    al, al
0x1800479b5  jz      short loc_1800479D3
0x1800479b7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x1800479be  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x1800479c3  test    al, al
0x1800479c5  jz      short loc_180047A02
0x1800479c7  mov     dword ptr [rbx+80h], 3
0x1800479d1  jmp     short loc_1800479DD
0x1800479d3  mov     dword ptr [rbx+80h], 0
0x1800479dd  lea     rcx, [rbp+var_10]
0x1800479e1  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800479e6  mov     rcx, [rbp+var_8]
0x1800479ea  xor     rcx, rsp; StackCookie
0x1800479ed  call    __security_check_cookie
0x1800479f2  mov     rbx, [rsp+50h+arg_10]
0x1800479f7  mov     rdi, [rsp+50h+arg_18]
0x1800479fc  add     rsp, 50h
0x180047a00  pop     rbp
0x180047a01  retn
0x180047a02  mov     ecx, 80004001h
0x180047a07  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180047a0c  mov     r9d, eax; char *
0x180047a0f  mov     rcx, [rbp+8]; this
0x180047a13  lea     rax, aCustomAnimatio; "Custom animations aren't implemented ye"...
0x180047a1a  mov     qword ptr [rsp+50h+var_30], rax; int
0x180047a1f  lea     r8, aPcshellShellUx_8; "pcshell\\shell\\uxframe\\dll\\LiftedXam"...
0x180047a26  mov     edx, 32Fh; void *
0x180047a2b  call    ?FailFast_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_HrMsg(void *,uint,char const *,long,char const *,...)
0x180047a31  mov     ecx, 80070057h
0x180047a36  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180047a3b  mov     r9d, eax; char *
0x180047a3e  mov     rcx, [rbp+8]; this
0x180047a42  lea     rax, aMustSpecifyAVa; "Must specify a valid SlideAnimationDire"...
0x180047a49  mov     qword ptr [rsp+50h+var_30], rax; int
0x180047a4e  lea     r8, aPcshellShellUx_8; "pcshell\\shell\\uxframe\\dll\\LiftedXam"...
0x180047a55  mov     edx, 31Eh; void *
0x180047a5a  call    ?FailFast_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_HrMsg(void *,uint,char const *,long,char const *,...)
0x180047a60  mov     ecx, 80004001h
0x180047a65  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180047a6a  mov     r9d, eax; char *
0x180047a6d  mov     rcx, [rbp+8]; this
0x180047a71  lea     rax, aStockFadeAnima; "Stock fade animations aren't implemente"...
0x180047a78  mov     qword ptr [rsp+50h+var_30], rax; int
0x180047a7d  lea     r8, aPcshellShellUx_8; "pcshell\\shell\\uxframe\\dll\\LiftedXam"...
0x180047a84  mov     edx, 324h; void *
0x180047a89  call    ?FailFast_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_HrMsg(void *,uint,char const *,long,char const *,...)
```
