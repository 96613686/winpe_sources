# LiftedXamlHostBehavior::PrepareForFirstEntranceAnimation(void)

- ea: `0x18004881c`
- end: `0x18004891f`
- name: `?PrepareForFirstEntranceAnimation@LiftedXamlHostBehavior@@AEAAXXZ`
- size: `259`
- prototype: `void __fastcall(LiftedXamlHostBehavior *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180044d80`

## callees

- `0x1800041c4`
- `0x180007c58`
- `0x18000d0f0`
- `0x18001047c`
- `0x180017124`
- `0x180038b48`
- `0x1800401ac`
- `0x180040620`
- `0x180045ab0`
- `0x18004881c`

## string_xrefs

- `0x1800488e9`: `pcshell\shell\uxframe\dll\LiftedXamlHostBehavior.h`
- `0x18004890d`: `pcshell\shell\uxframe\dll\LiftedXamlHostBehavior.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall LiftedXamlHostBehavior::PrepareForFirstEntranceAnimation(LiftedXamlHostBehavior *this)
{
  _DWORD *v2; // rbx
  __int64 v3; // rax
  unsigned int v4; // eax
  unsigned int v5; // eax
  int v6[6]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LiftedXamlHostBehavior *v8; // [rsp+40h] [rbp+8h] BYREF
  char v9; // [rsp+48h] [rbp+10h] BYREF

  v8 = this;
  v2 = (_DWORD *)((char *)this + 128);
  XamlHostTelemetry::PrepareForFirstEntranceAnimation<LiftedXamlHostBehavior *,enum UXFrameHelpers::PropertyKeys::Invocation::XamlHostBehavior::AnimationTypeName &>(
    &v8,
    (char *)this + 128);
  switch ( *v2 )
  {
    case 1:
      winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::Content(
        (char *)this + 72,
        &v9);
      winrt::Microsoft::UI::Xaml::Hosting::ElementCompositionPreview::GetElementVisual((const struct winrt::Microsoft::UI::Xaml::UIElement *)&v8);
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v9);
      v3 = LiftedXamlHostBehavior::CalculateDismissedOffset(this, v6);
      winrt::impl::consume_Microsoft_UI_Composition_IVisual<winrt::Microsoft::UI::Composition::IVisual>::Offset(&v8, v3);
      *((_DWORD *)this + 46) = 1;
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v8);
      break;
    case 2:
      *((_DWORD *)this + 46) = 1;
      v4 = wil::verify_hresult<long>(2147500033LL);
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x29A,
        (unsigned int)"pcshell\\shell\\uxframe\\dll\\LiftedXamlHostBehavior.h",
        (const char *)v4,
        v6[0]);
    case 3:
      *((_DWORD *)this + 46) = 1;
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl) )
      {
        v5 = wil::verify_hresult<long>(2147500033LL);
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x2A5,
          (unsigned int)"pcshell\\shell\\uxframe\\dll\\LiftedXamlHostBehavior.h",
          (const char *)v5,
          v6[0]);
      }
      break;
  }
}

```

## disassembly

```asm
0x18004881c  mov     [rsp+arg_10], rbx
0x180048821  push    rdi
0x180048822  sub     rsp, 30h
0x180048826  mov     rdi, rcx
0x180048829  mov     [rsp+38h+arg_0], rcx
0x18004882e  lea     rbx, [rcx+80h]
0x180048835  mov     rdx, rbx
0x180048838  lea     rcx, [rsp+38h+arg_0]
0x18004883d  call    ??$PrepareForFirstEntranceAnimation@PEAVLiftedXamlHostBehavior@@AEAW4AnimationTypeName@XamlHostBehavior@Invocation@PropertyKeys@UXFrameHelpers@@@XamlHostTelemetry@@SAX$$QEAPEAVLiftedXamlHostBehavior@@AEAW4AnimationTypeName@XamlHostBehavior@Invocation@PropertyKeys@UXFrameHelpers@@@Z; XamlHostTelemetry::PrepareForFirstEntranceAnimation<LiftedXamlHostBehavior *,UXFrameHelpers::PropertyKeys::Invocation::XamlHostBehavior::AnimationTypeName &>(LiftedXamlHostBehavior * &&,UXFrameHelpers::PropertyKeys::Invocation::XamlHostBehavior::AnimationTypeName &)
0x180048842  cmp     dword ptr [rbx], 1
0x180048845  jnz     short loc_1800488A7
0x180048847  lea     rcx, [rdi+48h]
0x18004884b  lea     rdx, [rsp+38h+arg_8]
0x180048850  call    ?Content@?$consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::Content(void)
0x180048855  nop
0x180048856  mov     rdx, rax
0x180048859  lea     rcx, [rsp+38h+arg_0]; struct winrt::Microsoft::UI::Xaml::UIElement *
0x18004885e  call    ?GetElementVisual@ElementCompositionPreview@Hosting@Xaml@UI@Microsoft@winrt@@SA@AEBUUIElement@3456@@Z; winrt::Microsoft::UI::Xaml::Hosting::ElementCompositionPreview::GetElementVisual(winrt::Microsoft::UI::Xaml::UIElement const &)
0x180048863  nop
0x180048864  lea     rcx, [rsp+38h+arg_8]; this
0x180048869  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004886e  lea     rdx, [rsp+38h+var_18]
0x180048873  mov     rcx, rdi
0x180048876  call    ?CalculateDismissedOffset@LiftedXamlHostBehavior@@AEAA?AUfloat3@Numerics@Foundation@Windows@winrt@@XZ; LiftedXamlHostBehavior::CalculateDismissedOffset(void)
0x18004887b  mov     rdx, rax
0x18004887e  lea     rcx, [rsp+38h+arg_0]
0x180048883  call    ?Offset@?$consume_Microsoft_UI_Composition_IVisual@UIVisual@Composition@UI@Microsoft@winrt@@@impl@winrt@@QEBA@AEBUfloat3@Numerics@Foundation@Windows@3@@Z; winrt::impl::consume_Microsoft_UI_Composition_IVisual<winrt::Microsoft::UI::Composition::IVisual>::Offset(winrt::Windows::Foundation::Numerics::float3 const &)
0x180048888  mov     dword ptr [rdi+0B8h], 1
0x180048892  lea     rcx, [rsp+38h+arg_0]; this
0x180048897  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004889c  mov     rbx, [rsp+38h+arg_10]
0x1800488a1  add     rsp, 30h
0x1800488a5  pop     rdi
0x1800488a6  retn
0x1800488a7  cmp     dword ptr [rbx], 2
0x1800488aa  jz      short loc_1800488CD
0x1800488ac  cmp     dword ptr [rbx], 3
0x1800488af  jnz     short loc_18004889C
0x1800488b1  mov     dword ptr [rdi+0B8h], 1
0x1800488bb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x1800488c2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x1800488c7  test    al, al
0x1800488c9  jz      short loc_1800488FB
0x1800488cb  jmp     short loc_18004889C
0x1800488cd  mov     dword ptr [rdi+0B8h], 1
0x1800488d7  mov     ecx, 80004001h
0x1800488dc  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800488e1  mov     r9d, eax; char *
0x1800488e4  mov     rcx, [rsp+38h]; this
0x1800488e9  lea     r8, aPcshellShellUx_8; "pcshell\\shell\\uxframe\\dll\\LiftedXam"...
0x1800488f0  mov     edx, 29Ah; void *
0x1800488f5  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800488fb  mov     ecx, 80004001h
0x180048900  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180048905  mov     r9d, eax; char *
0x180048908  mov     rcx, [rsp+38h]; this
0x18004890d  lea     r8, aPcshellShellUx_8; "pcshell\\shell\\uxframe\\dll\\LiftedXam"...
0x180048914  mov     edx, 2A5h; void *
0x180048919  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
```
