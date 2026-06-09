# PopupWindowBehavior::SelectBehaviorsBasedOnValueSet(void)

- ea: `0x18002aa84`
- end: `0x18002ad9e`
- name: `?SelectBehaviorsBasedOnValueSet@PopupWindowBehavior@@AEAAXXZ`
- size: `794`
- prototype: `void __fastcall(PopupWindowBehavior *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting`

## callers

- `0x180027f60`

## callees

- `0x180002b20`
- `0x1800043f4`
- `0x1800088ac`
- `0x18000d0f0`
- `0x18000d810`
- `0x180017124`
- `0x18001f48c`
- `0x18001fcf4`
- `0x18001fe98`
- `0x18001ff14`
- `0x180020818`
- `0x1800208c8`
- `0x180020978`
- `0x180020ad8`
- `0x180023814`
- `0x1800238b4`
- `0x180027b88`
- `0x18002aa84`
- `0x18002da24`
- `0x18005a010`

## string_xrefs

- `0x18002ac72`: `pcshell\shell\uxframe\dll\PopupWindowBehavior.h`
- `0x18002ad8c`: `pcshell\shell\uxframe\dll\PopupWindowBehavior.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall PopupWindowBehavior::SelectBehaviorsBasedOnValueSet(PopupWindowBehavior *this)
{
  std::_Ref_count_base *v2; // r14
  std::_Ref_count_base *v3; // rdi
  std::_Ref_count_base *v4; // rcx
  std::_Ref_count_base *v5; // r14
  std::_Ref_count_base *v6; // rcx
  std::_Ref_count_base *v7; // r14
  unsigned int v8; // eax
  const char *v9; // [rsp+28h] [rbp-28h]
  int v10; // [rsp+30h] [rbp-20h] BYREF
  char v11; // [rsp+34h] [rbp-1Ch]
  std::_Ref_count_base *v12[2]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  winrt::hstring::hstring((winrt::hstring *)&v10, L"DismissPolicy");
  try_get_enum_from_valueset<enum UXFrameHelpers::PropertyKeys::Invocation::Popup::DismissPolicyName>(
    v12,
    &v10,
    (char *)this + 48);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v10);
  if ( BYTE4(v12[0]) )
    *((_DWORD *)this + 17) = v12[0];
  winrt::hstring::hstring((winrt::hstring *)v12, L"UserCloseAllowed");
  *((_BYTE *)this + 72) = ValueSetUtils::details::get_bool_or<winrt::Windows::Foundation::Collections::ValueSet>(
                            v12,
                            (_QWORD *)this + 6,
                            1);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v12);
  winrt::hstring::hstring((winrt::hstring *)v12, L"Personality");
  try_get_enum_from_valueset<enum UXFrameHelpers::PropertyKeys::Invocation::Popup::PersonalityName>(
    &v10,
    v12,
    (char *)this + 48);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v12);
  if ( !v11 || !v10 )
  {
    *(_OWORD *)v12 = 0;
    std::make_shared<AnchoredPopupPositioningBehavior,>(v12);
    v7 = v12[0];
    (**(void (__fastcall ***)(std::_Ref_count_base *, _QWORD, char *, _QWORD))v12[0])(
      v12[0],
      *((_QWORD *)this + 5),
      (char *)this + 48,
      *((_QWORD *)this + 3));
    v3 = v12[1];
    if ( v12[1] )
      _InterlockedIncrement((volatile signed __int32 *)v12[1] + 2);
    *((_QWORD *)this + 26) = v7;
    v6 = (std::_Ref_count_base *)*((_QWORD *)this + 27);
    *((_QWORD *)this + 27) = v3;
    if ( !v6 )
      goto LABEL_22;
LABEL_21:
    std::_Ref_count_base::_Decref(v6);
    goto LABEL_22;
  }
  if ( v10 != 1 )
  {
    if ( v10 != 2 )
    {
      v8 = wil::verify_hresult<long>(2147942487LL);
      wil::details::in1diag3::FailFast_HrMsg(
        retaddr,
        (void *)0x320,
        (unsigned int)"pcshell\\shell\\uxframe\\dll\\PopupWindowBehavior.h",
        (const char *)v8,
        (int)"Unknown popup personality",
        v9);
    }
    *(_OWORD *)v12 = 0;
    std::make_shared<FullscreenPositioningBehavior,>(v12);
    v2 = v12[0];
    (**(void (__fastcall ***)(std::_Ref_count_base *, _QWORD, char *, _QWORD))v12[0])(
      v12[0],
      *((_QWORD *)this + 5),
      (char *)this + 48,
      *((_QWORD *)this + 3));
    v3 = v12[1];
    if ( v12[1] )
      _InterlockedIncrement((volatile signed __int32 *)v12[1] + 2);
    *((_QWORD *)this + 26) = v2;
    v4 = (std::_Ref_count_base *)*((_QWORD *)this + 27);
    *((_QWORD *)this + 27) = v3;
    if ( v4 )
      std::_Ref_count_base::_Decref(v4);
    goto LABEL_22;
  }
  winrt::hstring::hstring((winrt::hstring *)v12, L"Edge");
  try_get_enum_from_valueset<enum UXFrameHelpers::PropertyKeys::Invocation::Popup::EdgeName>(
    &v10,
    v12,
    (char *)this + 48);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v12);
  if ( !v11 )
  {
    wil::details::in1diag3::FailFast_IfMsg(
      retaddr,
      (void *)0x313,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\PopupWindowBehavior.h",
      (const char *)1,
      (bool)"Missing edge for edge popup",
      v9);
    goto LABEL_24;
  }
  *(_OWORD *)v12 = 0;
  std::make_shared<EdgeFlyoutPositioningBehavior,>(v12);
  v5 = v12[0];
  EdgeFlyoutPositioningBehavior::Initialize(
    v12[0],
    *((_QWORD *)this + 5),
    (char *)this + 48,
    v10 != 0,
    *((_QWORD *)this + 3));
  v3 = v12[1];
  if ( v12[1] )
    _InterlockedIncrement((volatile signed __int32 *)v12[1] + 2);
  *((_QWORD *)this + 26) = v5;
  v6 = (std::_Ref_count_base *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = v3;
  if ( v6 )
    goto LABEL_21;
LABEL_22:
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
LABEL_24:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl) )
  {
    winrt::hstring::hstring((winrt::hstring *)v12, L"ActivationBehavior");
    try_get_enum_from_valueset<enum UXFrameHelpers::PropertyKeys::Invocation::Popup::ActivationBehaviorName>(
      &v10,
      v12,
      (char *)this + 48);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v12);
    if ( v11 )
    {
      *((_DWORD *)this + 19) = *(_DWORD *)std::optional<enum UXFrameHelpers::PropertyKeys::Invocation::Popup::ActivationBehaviorName>::value(&v10);
      *((_BYTE *)this + 80) = 1;
      *(_WORD *)((char *)this + 81) = *(_WORD *)((char *)v12 + 5);
      *((_BYTE *)this + 83) = HIBYTE(v12[0]);
    }
  }
}

```

## disassembly

```asm
0x18002aa84  mov     [rsp-18h+arg_8], rbx
0x18002aa89  mov     [rsp-18h+arg_10], rsi
0x18002aa8e  push    rbp
0x18002aa8f  push    rdi
0x18002aa90  push    r14
0x18002aa92  mov     rbp, rsp
0x18002aa95  sub     rsp, 50h
0x18002aa99  mov     rax, cs:__security_cookie
0x18002aaa0  xor     rax, rsp
0x18002aaa3  mov     [rbp+var_8], rax
0x18002aaa7  mov     rbx, rcx
0x18002aaaa  lea     rdx, aDismisspolicy; "DismissPolicy"
0x18002aab1  lea     rcx, [rbp+var_20]; this
0x18002aab5  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x18002aaba  nop
0x18002aabb  lea     rsi, [rbx+30h]
0x18002aabf  mov     r8, rsi
0x18002aac2  lea     rdx, [rbp+var_20]
0x18002aac6  lea     rcx, [rbp+var_18]
0x18002aaca  call    ??$try_get_enum_from_valueset@W4DismissPolicyName@Popup@Invocation@PropertyKeys@UXFrameHelpers@@@@YA?AV?$optional@W4DismissPolicyName@Popup@Invocation@PropertyKeys@UXFrameHelpers@@@std@@AEBUhstring@winrt@@AEBUValueSet@Collections@Foundation@Windows@3@@Z; try_get_enum_from_valueset<UXFrameHelpers::PropertyKeys::Invocation::Popup::DismissPolicyName>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x18002aacf  nop
0x18002aad0  lea     rcx, [rbp+var_20]
0x18002aad4  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18002aad9  cmp     byte ptr [rbp+var_18+4], 0
0x18002aadd  jz      short loc_18002AAE5
0x18002aadf  mov     eax, dword ptr [rbp+var_18]
0x18002aae2  mov     [rbx+44h], eax
0x18002aae5  lea     rdx, aUsercloseallow; "UserCloseAllowed"
0x18002aaec  lea     rcx, [rbp+var_18]; this
0x18002aaf0  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x18002aaf5  nop
0x18002aaf6  mov     r8b, 1
0x18002aaf9  mov     rdx, rsi
0x18002aafc  lea     rcx, [rbp+var_18]
0x18002ab00  call    ??$get_bool_or@UValueSet@Collections@Foundation@Windows@winrt@@@details@ValueSetUtils@@YA_NAEBUhstring@winrt@@AEBUValueSet@Collections@Foundation@Windows@3@_N@Z; ValueSetUtils::details::get_bool_or<winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &,bool)
0x18002ab05  mov     [rbx+48h], al
0x18002ab08  lea     rcx, [rbp+var_18]
0x18002ab0c  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18002ab11  lea     rdx, aPersonality; "Personality"
0x18002ab18  lea     rcx, [rbp+var_18]; this
0x18002ab1c  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x18002ab21  nop
0x18002ab22  mov     r8, rsi
0x18002ab25  lea     rdx, [rbp+var_18]
0x18002ab29  lea     rcx, [rbp+var_20]
0x18002ab2d  call    ??$try_get_enum_from_valueset@W4PersonalityName@Popup@Invocation@PropertyKeys@UXFrameHelpers@@@@YA?AV?$optional@W4PersonalityName@Popup@Invocation@PropertyKeys@UXFrameHelpers@@@std@@AEBUhstring@winrt@@AEBUValueSet@Collections@Foundation@Windows@3@@Z; try_get_enum_from_valueset<UXFrameHelpers::PropertyKeys::Invocation::Popup::PersonalityName>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x18002ab32  nop
0x18002ab33  lea     rcx, [rbp+var_18]
0x18002ab37  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18002ab3c  cmp     [rbp+var_1C], 0
0x18002ab40  jz      loc_18002AC85
0x18002ab46  mov     ecx, [rbp+var_20]
0x18002ab49  test    ecx, ecx
0x18002ab4b  jz      loc_18002AC85
0x18002ab51  sub     ecx, 1
0x18002ab54  jz      short loc_18002ABBF
0x18002ab56  cmp     ecx, 1
0x18002ab59  jnz     loc_18002AD6F
0x18002ab5f  xorps   xmm0, xmm0
0x18002ab62  movups  xmmword ptr [rbp+var_18], xmm0
0x18002ab66  lea     rcx, [rbp+var_18]
0x18002ab6a  call    ??$make_shared@VFullscreenPositioningBehavior@@$$V@std@@YA?AV?$shared_ptr@VFullscreenPositioningBehavior@@@0@XZ; std::make_shared<FullscreenPositioningBehavior,>(void)
0x18002ab6f  nop
0x18002ab70  mov     r14, [rbp+var_18]
0x18002ab74  mov     rax, [r14]
0x18002ab77  mov     r9, [rbx+18h]
0x18002ab7b  mov     r8, rsi
0x18002ab7e  mov     rdx, [rbx+28h]
0x18002ab82  mov     rcx, r14
0x18002ab85  mov     rax, [rax]
0x18002ab88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab8d  mov     rdi, [rbp+var_18+8]
0x18002ab91  test    rdi, rdi
0x18002ab94  jz      short loc_18002AB9A
0x18002ab96  lock inc dword ptr [rdi+8]
0x18002ab9a  mov     [rbx+0D0h], r14
0x18002aba1  mov     rcx, [rbx+0D8h]; this
0x18002aba8  mov     [rbx+0D8h], rdi
0x18002abaf  test    rcx, rcx
0x18002abb2  jz      short loc_18002ABBA
0x18002abb4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002abb9  nop
0x18002abba  jmp     loc_18002ACE0
0x18002abbf  lea     rdx, aEdge; "Edge"
0x18002abc6  lea     rcx, [rbp+var_18]; this
0x18002abca  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x18002abcf  nop
0x18002abd0  mov     r8, rsi
0x18002abd3  lea     rdx, [rbp+var_18]
0x18002abd7  lea     rcx, [rbp+var_20]
0x18002abdb  call    ??$try_get_enum_from_valueset@W4EdgeName@Popup@Invocation@PropertyKeys@UXFrameHelpers@@@@YA?AV?$optional@W4EdgeName@Popup@Invocation@PropertyKeys@UXFrameHelpers@@@std@@AEBUhstring@winrt@@AEBUValueSet@Collections@Foundation@Windows@3@@Z; try_get_enum_from_valueset<UXFrameHelpers::PropertyKeys::Invocation::Popup::EdgeName>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x18002abe0  nop
0x18002abe1  lea     rcx, [rbp+var_18]
0x18002abe5  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18002abea  cmp     [rbp+var_1C], 0
0x18002abee  jz      short loc_18002AC5C
0x18002abf0  xorps   xmm0, xmm0
0x18002abf3  movups  xmmword ptr [rbp+var_18], xmm0
0x18002abf7  lea     rcx, [rbp+var_18]
0x18002abfb  call    ??$make_shared@VEdgeFlyoutPositioningBehavior@@$$V@std@@YA?AV?$shared_ptr@VEdgeFlyoutPositioningBehavior@@@0@XZ; std::make_shared<EdgeFlyoutPositioningBehavior,>(void)
0x18002ac00  xor     r9d, r9d
0x18002ac03  cmp     [rbp+var_20], r9d
0x18002ac07  setnz   r9b
0x18002ac0b  mov     rax, [rbx+18h]
0x18002ac0f  mov     qword ptr [rsp+50h+var_30], rax
0x18002ac14  mov     r8, rsi
0x18002ac17  mov     rdx, [rbx+28h]
0x18002ac1b  mov     r14, [rbp+var_18]
0x18002ac1f  mov     rcx, r14
0x18002ac22  call    ?Initialize@EdgeFlyoutPositioningBehavior@@QEAAXPEAUHWND__@@AEBUValueSet@Collections@Foundation@Windows@winrt@@W4PositioningType@@PEAVWindowingBehaviorClient@@@Z; EdgeFlyoutPositioningBehavior::Initialize(HWND__ *,winrt::Windows::Foundation::Collections::ValueSet const &,PositioningType,WindowingBehaviorClient *)
0x18002ac27  mov     rdi, [rbp+var_18+8]
0x18002ac2b  test    rdi, rdi
0x18002ac2e  jz      short loc_18002AC34
0x18002ac30  lock inc dword ptr [rdi+8]
0x18002ac34  mov     [rbx+0D0h], r14
0x18002ac3b  mov     rcx, [rbx+0D8h]; this
0x18002ac42  mov     [rbx+0D8h], rdi
0x18002ac49  test    rcx, rcx
0x18002ac4c  jz      loc_18002ACE0
0x18002ac52  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002ac57  jmp     loc_18002ACE0
0x18002ac5c  mov     rcx, [rbp+18h]; this
0x18002ac60  lea     rax, aMissingEdgeFor; "Missing edge for edge popup"
0x18002ac67  mov     qword ptr [rsp+50h+var_30], rax; bool
0x18002ac6c  mov     r9d, 1; char *
0x18002ac72  lea     r8, aPcshellShellUx_4; "pcshell\\shell\\uxframe\\dll\\PopupWind"...
0x18002ac79  mov     edx, 313h; void *
0x18002ac7e  call    ?FailFast_IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfMsg(void *,uint,char const *,bool,char const *,...)
0x18002ac83  jmp     short loc_18002ACED
0x18002ac85  xorps   xmm0, xmm0
0x18002ac88  movups  xmmword ptr [rbp+var_18], xmm0
0x18002ac8c  lea     rcx, [rbp+var_18]
0x18002ac90  call    ??$make_shared@VAnchoredPopupPositioningBehavior@@$$V@std@@YA?AV?$shared_ptr@VAnchoredPopupPositioningBehavior@@@0@XZ; std::make_shared<AnchoredPopupPositioningBehavior,>(void)
0x18002ac95  nop
0x18002ac96  mov     r14, [rbp+var_18]
0x18002ac9a  mov     rax, [r14]
0x18002ac9d  mov     r9, [rbx+18h]
0x18002aca1  mov     r8, rsi
0x18002aca4  mov     rdx, [rbx+28h]
0x18002aca8  mov     rcx, r14
0x18002acab  mov     rax, [rax]
0x18002acae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acb3  mov     rdi, [rbp+var_18+8]
0x18002acb7  test    rdi, rdi
0x18002acba  jz      short loc_18002ACC0
0x18002acbc  lock inc dword ptr [rdi+8]
0x18002acc0  mov     [rbx+0D0h], r14
0x18002acc7  mov     rcx, [rbx+0D8h]; this
0x18002acce  mov     [rbx+0D8h], rdi
0x18002acd5  test    rcx, rcx
0x18002acd8  jz      short loc_18002ACE0
0x18002acda  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002acdf  nop
0x18002ace0  test    rdi, rdi
0x18002ace3  jz      short loc_18002ACED
0x18002ace5  mov     rcx, rdi; this
0x18002ace8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002aced  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x18002acf4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x18002acf9  test    al, al
0x18002acfb  jz      short loc_18002AD4E
0x18002acfd  lea     rdx, aActivationbeha; "ActivationBehavior"
0x18002ad04  lea     rcx, [rbp+var_18]; this
0x18002ad08  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x18002ad0d  nop
0x18002ad0e  mov     r8, rsi
0x18002ad11  lea     rdx, [rbp+var_18]
0x18002ad15  lea     rcx, [rbp+var_20]
0x18002ad19  call    ??$try_get_enum_from_valueset@W4ActivationBehaviorName@Popup@Invocation@PropertyKeys@UXFrameHelpers@@@@YA?AV?$optional@W4ActivationBehaviorName@Popup@Invocation@PropertyKeys@UXFrameHelpers@@@std@@AEBUhstring@winrt@@AEBUValueSet@Collections@Foundation@Windows@3@@Z; try_get_enum_from_valueset<UXFrameHelpers::PropertyKeys::Invocation::Popup::ActivationBehaviorName>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x18002ad1e  nop
0x18002ad1f  lea     rcx, [rbp+var_18]
0x18002ad23  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18002ad28  cmp     [rbp+var_1C], 0
0x18002ad2c  jz      short loc_18002AD4E
0x18002ad2e  lea     rcx, [rbp+var_20]
0x18002ad32  call    ?value@?$optional@W4ActivationBehaviorName@Popup@Invocation@PropertyKeys@UXFrameHelpers@@@std@@QEGAAAEAW4ActivationBehaviorName@Popup@Invocation@PropertyKeys@UXFrameHelpers@@XZ; std::optional<UXFrameHelpers::PropertyKeys::Invocation::Popup::ActivationBehaviorName>::value(void)
0x18002ad37  mov     eax, [rax]
0x18002ad39  mov     [rbx+4Ch], eax
0x18002ad3c  mov     byte ptr [rbx+50h], 1
0x18002ad40  movzx   eax, word ptr [rbp+var_18+5]
0x18002ad44  mov     [rbx+51h], ax
0x18002ad48  mov     al, byte ptr [rbp+var_18+7]
0x18002ad4b  mov     [rbx+53h], al
0x18002ad4e  mov     rcx, [rbp+var_8]
0x18002ad52  xor     rcx, rsp; StackCookie
0x18002ad55  call    __security_check_cookie
0x18002ad5a  lea     r11, [rsp+50h+var_s0]
0x18002ad5f  mov     rbx, [r11+28h]
0x18002ad63  mov     rsi, [r11+30h]
0x18002ad67  mov     rsp, r11
0x18002ad6a  pop     r14
0x18002ad6c  pop     rdi
0x18002ad6d  pop     rbp
0x18002ad6e  retn
0x18002ad6f  mov     ecx, 80070057h
0x18002ad74  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002ad79  mov     r9d, eax; char *
0x18002ad7c  mov     rcx, [rbp+18h]; this
0x18002ad80  lea     rax, aUnknownPopupPe; "Unknown popup personality"
0x18002ad87  mov     qword ptr [rsp+50h+var_30], rax; int
0x18002ad8c  lea     r8, aPcshellShellUx_4; "pcshell\\shell\\uxframe\\dll\\PopupWind"...
0x18002ad93  mov     edx, 320h; void *
0x18002ad98  call    ?FailFast_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_HrMsg(void *,uint,char const *,long,char const *,...)
```
