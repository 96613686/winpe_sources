# LiftedXamlHostBehavior::OnWindowMessage(uint,unsigned __int64,__int64)

- ea: `0x180047570`
- end: `0x18004777b`
- name: `?OnWindowMessage@LiftedXamlHostBehavior@@UEAA?AW4WindowMessageHandlingResult@@I_K_J@Z`
- size: `523`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002b20`
- `0x1800041c4`
- `0x18001049c`
- `0x18002cc80`
- `0x18003e2b8`
- `0x1800418f0`
- `0x180045724`
- `0x180045804`
- `0x180047570`
- `0x18004a138`
- `0x18004a344`

## import_xrefs

- `USER32!SetFocus` at `0x180047716`
- `USER32!SetFocus` at `0x180047716`
- `USER32!GetClientRect` at `0x180047635`
- `USER32!GetClientRect` at `0x180047635`

## string_xrefs

- `0x1800475aa`: `pcshell\shell\uxframe\dll\LiftedXamlHostBehavior.h`

## pseudocode

```c
__int64 __fastcall LiftedXamlHostBehavior::OnWindowMessage(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  char v7; // al
  unsigned int v8; // r15d
  __int64 v9; // rbx
  bool v10; // zf
  bool v11; // r14
  __int64 v12; // rax
  struct tagRECT *p_Rect; // rdx
  __int64 v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rax
  int v19; // [rsp+20h] [rbp-30h] BYREF
  _DWORD v20[4]; // [rsp+28h] [rbp-28h] BYREF
  struct tagRECT Rect; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  v7 = 0;
  v19 = 0;
  if ( !*(_QWORD *)(a1 + 56) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x4D,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\LiftedXamlHostBehavior.h",
      (const char *)a4);
  v8 = 0;
  if ( a2 == 6 )
  {
    LiftedXamlHostBehavior::FailFastIfMidInitialization((LiftedXamlHostBehavior *)a1);
    if ( a3 && *(_QWORD *)(a1 + 72) )
    {
      v15 = *(_QWORD *)winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::SiteBridge(
                         a1 + 72,
                         &v19);
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v19);
      if ( v15 )
      {
        v16 = winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::SiteBridge(
                a1 + 72,
                &v19);
        winrt::impl::consume_Microsoft_UI_Content_IDesktopSiteBridge<winrt::Microsoft::UI::Content::DesktopChildSiteBridge>::Show(v16);
        winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v19);
        SetFocus(*(HWND *)(a1 + 64));
        v19 = 1;
        v17 = winrt::Microsoft::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest::XamlSourceFocusNavigationRequest(
                (winrt::Microsoft::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest *)&Rect,
                (const enum winrt::Microsoft::UI::Xaml::Hosting::XamlSourceFocusNavigationReason *)&v19);
        winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::NavigateFocus(
          a1 + 72,
          v20,
          v17);
        winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)v20);
        winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&Rect);
      }
      return 1;
    }
  }
  else if ( a2 == 71 && (*(_BYTE *)(a4 + 32) & 1) == 0 )
  {
    v9 = a1 + 72;
    v11 = 0;
    if ( *(_QWORD *)(a1 + 72) )
    {
      v10 = *(_QWORD *)winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::SiteBridge(
                         a1 + 72,
                         &v19) == 0;
      v7 = 1;
      if ( !v10 )
        v11 = 1;
    }
    if ( (v7 & 1) != 0 )
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v19);
    if ( v11 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OverlappedWindowBehavior>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OverlappedWindowBehavior>::GetImpl'::`2'::impl) )
      {
        Rect = 0;
        GetClientRect(*(HWND *)(a1 + 56), &Rect);
        v12 = winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::SiteBridge(
                v9,
                &v19);
        v20[0] = Rect.left;
        v20[1] = Rect.top;
        v20[2] = Rect.right - Rect.left;
        v20[3] = Rect.bottom - Rect.top;
        p_Rect = (struct tagRECT *)v20;
      }
      else
      {
        v12 = winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::SiteBridge(
                v9,
                &v19);
        *(_QWORD *)&Rect.left = 0;
        Rect.right = *(_DWORD *)(a4 + 24);
        Rect.bottom = *(_DWORD *)(a4 + 28);
        p_Rect = &Rect;
      }
      winrt::impl::consume_Microsoft_UI_Content_IDesktopSiteBridge<winrt::Microsoft::UI::Content::DesktopChildSiteBridge>::MoveAndResize(
        v12,
        p_Rect);
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v19);
      v14 = winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::SiteBridge(
              v9,
              &v19);
      winrt::impl::consume_Microsoft_UI_Content_IDesktopSiteBridge<winrt::Microsoft::UI::Content::DesktopChildSiteBridge>::Show(v14);
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v19);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180047570  mov     [rsp-28h+arg_8], rbx
0x180047575  push    rbp
0x180047576  push    rsi
0x180047577  push    r13
0x180047579  push    r14
0x18004757b  push    r15
0x18004757d  mov     rbp, rsp
0x180047580  sub     rsp, 50h
0x180047584  mov     rax, cs:__security_cookie
0x18004758b  xor     rax, rsp
0x18004758e  mov     [rbp+var_8], rax
0x180047592  mov     r13, r9
0x180047595  mov     rbx, r8
0x180047598  mov     rsi, rcx
0x18004759b  xor     eax, eax
0x18004759d  mov     [rbp+var_30], eax
0x1800475a0  cmp     [rcx+38h], rax
0x1800475a4  jnz     short loc_1800475BA
0x1800475a6  mov     rcx, [rbp+28h]; this
0x1800475aa  lea     r8, aPcshellShellUx_8; "pcshell\\shell\\uxframe\\dll\\LiftedXam"...
0x1800475b1  lea     edx, [rax+4Dh]; void *
0x1800475b4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800475ba  xor     r15d, r15d
0x1800475bd  cmp     edx, 6
0x1800475c0  jz      loc_1800476C1
0x1800475c6  cmp     edx, 47h ; 'G'
0x1800475c9  jnz     loc_180047757
0x1800475cf  test    byte ptr [r9+20h], 1
0x1800475d4  jnz     loc_180047757
0x1800475da  lea     rbx, [rcx+48h]
0x1800475de  cmp     [rbx], rax
0x1800475e1  jz      short loc_1800475FD
0x1800475e3  lea     rdx, [rbp+var_30]
0x1800475e7  mov     rcx, rbx
0x1800475ea  call    ?SiteBridge@?$consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::SiteBridge(void)
0x1800475ef  cmp     [rax], r15
0x1800475f2  lea     eax, [r15+1]
0x1800475f6  jz      short loc_1800475FD
0x1800475f8  mov     r14b, al
0x1800475fb  jmp     short loc_180047600
0x1800475fd  xor     r14b, r14b
0x180047600  test    al, 1
0x180047602  jz      short loc_18004760D
0x180047604  lea     rcx, [rbp+var_30]; this
0x180047608  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004760d  test    r14b, r14b
0x180047610  jz      loc_180047757
0x180047616  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OverlappedWindowBehavior@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OverlappedWindowBehavior@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OverlappedWindowBehavior> `wil::Feature<__WilFeatureTraits_Feature_OverlappedWindowBehavior>::GetImpl(void)'::`2'::impl
0x18004761d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OverlappedWindowBehavior@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OverlappedWindowBehavior>::__private_IsEnabled(void)
0x180047622  test    al, al
0x180047624  jz      short loc_18004766C
0x180047626  xorps   xmm0, xmm0
0x180047629  movups  xmmword ptr [rbp+Rect.left], xmm0
0x18004762d  lea     rdx, [rbp+Rect]; lpRect
0x180047631  mov     rcx, [rsi+38h]; hWnd
0x180047635  call    cs:__imp_GetClientRect
0x18004763b  lea     rdx, [rbp+var_30]
0x18004763f  mov     rcx, rbx
0x180047642  call    ?SiteBridge@?$consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::SiteBridge(void)
0x180047647  mov     edx, [rbp+Rect.left]
0x18004764a  mov     [rbp+var_28], edx
0x18004764d  mov     r8d, [rbp+Rect.top]
0x180047651  mov     [rbp+var_24], r8d
0x180047655  mov     ecx, [rbp+Rect.right]
0x180047658  sub     ecx, edx
0x18004765a  mov     [rbp+var_20], ecx
0x18004765d  mov     ecx, [rbp+Rect.bottom]
0x180047660  sub     ecx, r8d
0x180047663  mov     [rbp+var_1C], ecx
0x180047666  lea     rdx, [rbp+var_28]
0x18004766a  jmp     short loc_18004768E
0x18004766c  lea     rdx, [rbp+var_30]
0x180047670  mov     rcx, rbx
0x180047673  call    ?SiteBridge@?$consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::SiteBridge(void)
0x180047678  mov     qword ptr [rbp+Rect.left], r15
0x18004767c  mov     ecx, [r13+18h]
0x180047680  mov     [rbp+Rect.right], ecx
0x180047683  mov     ecx, [r13+1Ch]
0x180047687  mov     [rbp+Rect.bottom], ecx
0x18004768a  lea     rdx, [rbp+Rect]
0x18004768e  mov     rcx, rax
0x180047691  call    ?MoveAndResize@?$consume_Microsoft_UI_Content_IDesktopSiteBridge@UDesktopChildSiteBridge@Content@UI@Microsoft@winrt@@@impl@winrt@@QEBA@AEBURectInt32@Graphics@Windows@3@@Z; winrt::impl::consume_Microsoft_UI_Content_IDesktopSiteBridge<winrt::Microsoft::UI::Content::DesktopChildSiteBridge>::MoveAndResize(winrt::Windows::Graphics::RectInt32 const &)
0x180047696  lea     rcx, [rbp+var_30]; this
0x18004769a  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004769f  lea     rdx, [rbp+var_30]
0x1800476a3  mov     rcx, rbx
0x1800476a6  call    ?SiteBridge@?$consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::SiteBridge(void)
0x1800476ab  mov     rcx, rax
0x1800476ae  call    ?Show@?$consume_Microsoft_UI_Content_IDesktopSiteBridge@UDesktopChildSiteBridge@Content@UI@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_UI_Content_IDesktopSiteBridge<winrt::Microsoft::UI::Content::DesktopChildSiteBridge>::Show(void)
0x1800476b3  lea     rcx, [rbp+var_30]; this
0x1800476b7  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x1800476bc  jmp     loc_180047757
0x1800476c1  call    ?FailFastIfMidInitialization@LiftedXamlHostBehavior@@AEAAXXZ; LiftedXamlHostBehavior::FailFastIfMidInitialization(void)
0x1800476c6  test    rbx, rbx
0x1800476c9  jz      loc_180047757
0x1800476cf  lea     r14, [rsi+48h]
0x1800476d3  cmp     [r14], r15
0x1800476d6  jz      short loc_180047757
0x1800476d8  lea     rdx, [rbp+var_30]
0x1800476dc  mov     rcx, r14
0x1800476df  call    ?SiteBridge@?$consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::SiteBridge(void)
0x1800476e4  mov     rbx, [rax]
0x1800476e7  lea     rcx, [rbp+var_30]; this
0x1800476eb  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x1800476f0  test    rbx, rbx
0x1800476f3  jz      short loc_180047751
0x1800476f5  lea     rdx, [rbp+var_30]
0x1800476f9  mov     rcx, r14
0x1800476fc  call    ?SiteBridge@?$consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::SiteBridge(void)
0x180047701  mov     rcx, rax
0x180047704  call    ?Show@?$consume_Microsoft_UI_Content_IDesktopSiteBridge@UDesktopChildSiteBridge@Content@UI@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_UI_Content_IDesktopSiteBridge<winrt::Microsoft::UI::Content::DesktopChildSiteBridge>::Show(void)
0x180047709  lea     rcx, [rbp+var_30]; this
0x18004770d  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180047712  mov     rcx, [rsi+40h]; hWnd
0x180047716  call    cs:__imp_SetFocus
0x18004771c  mov     [rbp+var_30], 1
0x180047723  lea     rdx, [rbp+var_30]; enum winrt::Microsoft::UI::Xaml::Hosting::XamlSourceFocusNavigationReason *
0x180047727  lea     rcx, [rbp+Rect]; this
0x18004772b  call    ??0XamlSourceFocusNavigationRequest@Hosting@Xaml@UI@Microsoft@winrt@@QEAA@AEBW4XamlSourceFocusNavigationReason@12345@@Z; winrt::Microsoft::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest::XamlSourceFocusNavigationRequest(winrt::Microsoft::UI::Xaml::Hosting::XamlSourceFocusNavigationReason const &)
0x180047730  mov     r8, rax
0x180047733  lea     rdx, [rbp+var_28]
0x180047737  mov     rcx, r14
0x18004773a  call    ?NavigateFocus@?$consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Microsoft@winrt@@@impl@winrt@@QEBA@AEBUXamlSourceFocusNavigationRequest@Hosting@Xaml@UI@Microsoft@3@@Z; winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::NavigateFocus(winrt::Microsoft::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest const &)
0x18004773f  lea     rcx, [rbp+var_28]; this
0x180047743  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180047748  lea     rcx, [rbp+Rect]; this
0x18004774c  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180047751  mov     r15d, 1
0x180047757  mov     eax, r15d
0x18004775a  mov     rcx, [rbp+var_8]
0x18004775e  xor     rcx, rsp; StackCookie
0x180047761  call    __security_check_cookie
0x180047766  mov     rbx, [rsp+50h+arg_8]
0x18004776e  add     rsp, 50h
0x180047772  pop     r15
0x180047774  pop     r14
0x180047776  pop     r13
0x180047778  pop     rsi
0x180047779  pop     rbp
0x18004777a  retn
```
