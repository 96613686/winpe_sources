# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::BodyStackPanelLoadedHandler(winrt::Windows::Foundation::IInspectable const &,winrt::Windows::UI::Xaml::RoutedEventArgs const &)

- ea: `0x18001d568`
- end: `0x18001db23`
- name: `?BodyStackPanelLoadedHandler@FirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAXAEBUIInspectable@Foundation@67@AEBURoutedEventArgs@Xaml@UI@67@@Z`
- size: `1467`
- prototype: `void __fastcall(winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog *this, const struct IInspectable *, const struct winrt::Windows::UI::Xaml::RoutedEventArgs *, const char *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001eb90`

## callees

- `0x180002d55`
- `0x180002d91`
- `0x18000b058`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18000bbe8`
- `0x18000c4f0`
- `0x180019390`
- `0x18001b214`
- `0x18001b4fc`
- `0x18001d568`
- `0x18001eaec`
- `0x180022de4`
- `0x180023530`
- `0x18002d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001d7c7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001d7c7`

## string_xrefs

- `0x18001daa5`: `shellcommon\shell\networkux\firewallux\lib\firewallnotificationdialog.cpp`
- `0x18001dac3`: `shellcommon\shell\networkux\firewallux\lib\firewallnotificationdialog.cpp`
- `0x18001daed`: `shellcommon\shell\networkux\firewallux\lib\firewallnotificationdialog.cpp`
- `0x18001daff`: `shellcommon\shell\networkux\firewallux\lib\firewallnotificationdialog.cpp`
- `0x18001db11`: `shellcommon\shell\networkux\firewallux\lib\firewallnotificationdialog.cpp`
- `0x18001d84d`: `CommandSpace`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::BodyStackPanelLoadedHandler(
        winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog *this,
        const struct IInspectable *a2,
        const struct winrt::Windows::UI::Xaml::RoutedEventArgs *a3,
        const char *a4)
{
  struct IInspectableVtbl *lpVtbl; // rcx
  char v5; // r12
  struct winrt::impl::shared_hstring_header *v6; // r15
  int v7; // eax
  char v8; // al
  struct winrt::impl::shared_hstring_header *v9; // rsi
  int v10; // r13d
  volatile signed __int32 *v11; // rbx
  struct winrt::impl::shared_hstring_header *v12; // rdi
  struct winrt::impl::shared_hstring_header *v13; // r14
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v19; // edx
  struct winrt::impl::shared_hstring_header *v20; // rbx
  unsigned int v21; // edx
  const char *v22; // r9
  LPVOID v23; // rbx
  struct winrt::impl::shared_hstring_header *v24; // rdi
  unsigned int v25; // edx
  winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog *v26; // rdi
  const char *v27; // r9
  _QWORD *v28; // r14
  __int64 v29; // rcx
  struct winrt::impl::shared_hstring_header *v30; // rdi
  const char *v31; // r9
  void (__fastcall ***v32)(_QWORD, void *, struct winrt::impl::shared_hstring_header **); // r12
  void (__fastcall ***v33)(_QWORD, void *, struct winrt::impl::shared_hstring_header **); // rcx
  struct winrt::impl::shared_hstring_header *v34; // rcx
  struct winrt::impl::shared_hstring_header **v35; // rdx
  struct winrt::impl::shared_hstring_header *v36; // rax
  struct winrt::impl::shared_hstring_header *v37; // rcx
  struct winrt::impl::shared_hstring_header **v38; // rdx
  struct winrt::impl::shared_hstring_header *v39; // rax
  LPVOID lpMem; // [rsp+20h] [rbp-48h] BYREF
  __int64 v41; // [rsp+28h] [rbp-40h] BYREF
  struct winrt::impl::shared_hstring_header *v42; // [rsp+30h] [rbp-38h] BYREF
  struct winrt::impl::shared_hstring_header *v43; // [rsp+38h] [rbp-30h] BYREF
  void (__fastcall ***v44)(_QWORD, void *, struct winrt::impl::shared_hstring_header **); // [rsp+40h] [rbp-28h] BYREF
  int v45; // [rsp+48h] [rbp-20h] BYREF
  __int128 v46; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  struct winrt::impl::shared_hstring_header *v49; // [rsp+B8h] [rbp+50h] BYREF
  struct winrt::impl::shared_hstring_header *v50; // [rsp+C0h] [rbp+58h] BYREF
  struct winrt::impl::shared_hstring_header *v51; // [rsp+C8h] [rbp+60h] BYREF

  HIDWORD(v50) = HIDWORD(a3);
  LODWORD(v50) = 0;
  v42 = 0;
  lpVtbl = a2->lpVtbl;
  v5 = 1;
  if ( a2->lpVtbl )
  {
    v50 = 0;
    v45 = 0;
    v46 = 0;
    v7 = (*(__int64 (__fastcall **)(struct IInspectableVtbl *, void *, struct winrt::impl::shared_hstring_header **))lpVtbl->QueryInterface)(
           lpVtbl,
           &winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IStackPanel>,
           &v50);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, &v45);
    v6 = v50;
    v42 = v50;
    if ( v50 )
    {
      v8 = 0;
      goto LABEL_7;
    }
  }
  else
  {
    v6 = 0;
    v42 = 0;
  }
  v8 = 1;
LABEL_7:
  if ( v8 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC2,
      (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewallnotificationdialog.cpp",
      a4);
  v9 = 0;
  v10 = 6;
  v51 = 0;
  if ( v6 )
  {
    v50 = 0;
    (**(void (__fastcall ***)(struct winrt::impl::shared_hstring_header *, void *, struct winrt::impl::shared_hstring_header **))v6)(
      v6,
      &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IDependencyObject>,
      &v50);
    v49 = v50;
  }
  else
  {
    v49 = 0;
  }
  v11 = (volatile signed __int32 *)v50;
  while ( !v9 )
  {
    winrt::Windows::UI::Xaml::Media::VisualTreeHelper::GetParent((const struct winrt::Windows::UI::Xaml::DependencyObject *)&v43);
    v12 = v43;
    if ( !v43 )
      goto LABEL_39;
    v50 = 0;
    (**(void (__fastcall ***)(struct winrt::impl::shared_hstring_header *, void *, struct winrt::impl::shared_hstring_header **))v43)(
      v43,
      &winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IScrollViewer>,
      &v50);
    v9 = v50;
    v13 = v50;
    v51 = v50;
    if ( !v50 )
      goto LABEL_20;
    lpMem = 0;
    v50 = 0;
    v14 = (**(__int64 (__fastcall ***)(struct winrt::impl::shared_hstring_header *, void *, struct winrt::impl::shared_hstring_header **))v9)(
            v9,
            &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IFrameworkElement>,
            &v50);
    v45 = 0;
    v46 = 0;
    if ( v14 < 0 )
      winrt::throw_hresult((unsigned int)v14, &v45);
    v45 = 0;
    v46 = 0;
    v15 = (*(__int64 (__fastcall **)(struct winrt::impl::shared_hstring_header *, LPVOID *))(*(_QWORD *)v50 + 264LL))(
            v50,
            &lpMem);
    if ( v15 < 0 )
      winrt::throw_hresult((unsigned int)v15, &v45);
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v50);
    v11 = (volatile signed __int32 *)lpMem;
    v10 |= 9u;
    if ( !lpMem
      || *((_DWORD *)lpMem + 1) != 19
      || (v16 = wmemcmp(*((const wchar_t **)lpMem + 2), L"ContentScrollViewer", 0x13u), LOBYTE(v50) = 0, v16) )
    {
LABEL_20:
      LOBYTE(v50) = 1;
    }
    if ( (v10 & 1) != 0 )
    {
      v10 &= ~1u;
      if ( v11 )
      {
        v17 = _InterlockedDecrement(v11 + 6);
        if ( v17 )
        {
          if ( v17 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v11);
        }
        v11 = 0;
      }
    }
    if ( (_BYTE)v50 )
    {
      if ( v49 )
        winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v49);
      v49 = v12;
      if ( v12 )
        (*(void (__fastcall **)(struct winrt::impl::shared_hstring_header *))(*(_QWORD *)v12 + 8LL))(v12);
      if ( v13 )
        winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v51);
      v9 = 0;
      v51 = 0;
    }
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v43);
  }
  v5 = 0;
LABEL_39:
  if ( v5 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xD6,
      (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewallnotificationdialog.cpp",
      a4);
  if ( v9 )
  {
    v43 = 0;
    (**(void (__fastcall ***)(struct winrt::impl::shared_hstring_header *, void *, struct winrt::impl::shared_hstring_header **))v9)(
      v9,
      &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IDependencyObject>,
      &v43);
    v50 = v43;
  }
  else
  {
    v50 = 0;
  }
  winrt::Windows::UI::Xaml::Media::VisualTreeHelper::GetParent((const struct winrt::Windows::UI::Xaml::DependencyObject *)&v41);
  if ( v50 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v50);
  v20 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0xC, v19);
  memcpy_s((char *)v20 + 28, 0x18u, L"CommandSpace", 0x18u);
  v43 = v20;
  TryGetChildWithName<winrt::Windows::UI::Xaml::Controls::Grid,winrt::Windows::UI::Xaml::DependencyObject>(
    &lpMem,
    &v41,
    &v43);
  v23 = lpMem;
  if ( !lpMem )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xDB,
      (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewallnotificationdialog.cpp",
      v22);
  v24 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0xD, v21);
  memcpy_s((char *)v24 + 28, 0x1Au, L"PrimaryButton", 0x1Au);
  v50 = v24;
  v26 = (winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog *)TryGetChildWithName<winrt::Windows::UI::Xaml::Controls::Button,winrt::Windows::UI::Xaml::Controls::Grid>(&v44, &lpMem, &v50);
  v28 = (_QWORD *)((char *)this + 464);
  if ( (winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog *)((char *)this + 464) != v26 )
  {
    if ( *v28 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref((char *)this + 464);
    v29 = *(_QWORD *)v26;
    *(_QWORD *)v26 = 0;
    *v28 = v29;
  }
  if ( v44 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v44);
  if ( !*v28 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xDD,
      (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewallnotificationdialog.cpp",
      v27);
  v30 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0xF, v25);
  memcpy_s((char *)v30 + 28, 0x1Eu, L"SecondaryButton", 0x1Eu);
  v50 = v30;
  TryGetChildWithName<winrt::Windows::UI::Xaml::Controls::Button,winrt::Windows::UI::Xaml::Controls::Grid>(
    &v44,
    &lpMem,
    &v50);
  v32 = v44;
  if ( !v44 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xDF,
      (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewallnotificationdialog.cpp",
      v31);
  v33 = (void (__fastcall ***)(_QWORD, void *, struct winrt::impl::shared_hstring_header **))*v28;
  v50 = 0;
  if ( v33 )
  {
    (**v33)(v33, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IControl>, &v50);
    v34 = v50;
  }
  else
  {
    v34 = 0;
  }
  v35 = (struct winrt::impl::shared_hstring_header **)*((_QWORD *)this + 60);
  if ( v35 == *((struct winrt::impl::shared_hstring_header ***)this + 61) )
  {
    std::vector<winrt::Windows::UI::Xaml::Controls::Control>::_Emplace_reallocate<winrt::Windows::UI::Xaml::Controls::Control>(
      (char *)this + 472,
      v35,
      &v50);
    v36 = v50;
  }
  else
  {
    v36 = 0;
    v50 = 0;
    *v35 = v34;
    *((_QWORD *)this + 60) += 8LL;
  }
  if ( v36 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v50);
  v50 = 0;
  if ( v32 )
  {
    (**v32)(v32, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IControl>, &v50);
    v37 = v50;
  }
  else
  {
    v37 = 0;
  }
  v38 = (struct winrt::impl::shared_hstring_header **)*((_QWORD *)this + 60);
  if ( v38 == *((struct winrt::impl::shared_hstring_header ***)this + 61) )
  {
    std::vector<winrt::Windows::UI::Xaml::Controls::Control>::_Emplace_reallocate<winrt::Windows::UI::Xaml::Controls::Control>(
      (char *)this + 472,
      v38,
      &v50);
    v39 = v50;
  }
  else
  {
    v39 = 0;
    v50 = 0;
    *v38 = v37;
    *((_QWORD *)this + 60) += 8LL;
  }
  if ( v39 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v50);
  winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::_TryFindAndUpdateAllowCommandEnabled(
    this,
    (__int64)v38);
  if ( v32 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v44);
  if ( v23 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&lpMem);
  if ( v41 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v41);
  if ( v49 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v49);
  if ( v9 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v51);
  if ( v6 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v42);
}

```

## disassembly

```asm
0x18001d568  mov     [rsp-40h+arg_10], r8
0x18001d56d  mov     [rsp-40h+arg_0], rcx
0x18001d572  push    rbp
0x18001d573  push    rbx
0x18001d574  push    rsi
0x18001d575  push    rdi
0x18001d576  push    r12
0x18001d578  push    r13
0x18001d57a  push    r14
0x18001d57c  push    r15
0x18001d57e  mov     rbp, rsp
0x18001d581  sub     rsp, 68h
0x18001d585  mov     dword ptr [rbp+arg_10], 0
0x18001d58c  mov     [rbp+var_38], 0
0x18001d594  mov     rcx, [rdx]
0x18001d597  mov     r12b, 1
0x18001d59a  test    rcx, rcx
0x18001d59d  jnz     short loc_18001D5A8
0x18001d59f  xor     r15d, r15d
0x18001d5a2  mov     [rbp+var_38], r15
0x18001d5a6  jmp     short loc_18001D5EA
0x18001d5a8  mov     [rbp+arg_10], 0
0x18001d5b0  mov     [rbp+var_20], 0
0x18001d5b7  xorps   xmm0, xmm0
0x18001d5ba  movdqu  [rbp+var_18], xmm0
0x18001d5bf  mov     rax, [rcx]
0x18001d5c2  lea     r8, [rbp+arg_10]
0x18001d5c6  lea     rdx, ??$guid_v@UIStackPanel@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IStackPanel>
0x18001d5cd  mov     rax, [rax]
0x18001d5d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5d5  test    eax, eax
0x18001d5d7  js      loc_18001DAB7
0x18001d5dd  mov     r15, [rbp+arg_10]
0x18001d5e1  mov     [rbp+var_38], r15
0x18001d5e5  test    r15, r15
0x18001d5e8  jnz     short loc_18001D5EF
0x18001d5ea  mov     al, r12b
0x18001d5ed  jmp     short loc_18001D5F1
0x18001d5ef  xor     al, al
0x18001d5f1  mov     rcx, [rbp+40h]; this
0x18001d5f5  test    al, al
0x18001d5f7  jnz     loc_18001DAC3
0x18001d5fd  xor     esi, esi
0x18001d5ff  lea     r13d, [rsi+6]
0x18001d603  mov     [rbp+arg_18], rsi
0x18001d607  test    r15, r15
0x18001d60a  jnz     short loc_18001D612
0x18001d60c  mov     [rbp+arg_8], r15
0x18001d610  jmp     short loc_18001D63B
0x18001d612  mov     [rbp+arg_10], 0
0x18001d61a  mov     rax, [r15]
0x18001d61d  lea     r8, [rbp+arg_10]
0x18001d621  lea     rdx, ??$guid_v@UIDependencyObject@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::IDependencyObject>
0x18001d628  mov     rcx, r15
0x18001d62b  mov     rax, [rax]
0x18001d62e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d633  mov     rax, [rbp+arg_10]
0x18001d637  mov     [rbp+arg_8], rax
0x18001d63b  mov     rbx, [rbp+arg_10]
0x18001d63f  test    rsi, rsi
0x18001d642  jnz     loc_18001D7D0
0x18001d648  lea     rdx, [rbp+arg_8]
0x18001d64c  lea     rcx, [rbp+var_30]; struct winrt::Windows::UI::Xaml::DependencyObject *
0x18001d650  call    ?GetParent@VisualTreeHelper@Media@Xaml@UI@Windows@winrt@@SA@AEBUDependencyObject@3456@@Z; winrt::Windows::UI::Xaml::Media::VisualTreeHelper::GetParent(winrt::Windows::UI::Xaml::DependencyObject const &)
0x18001d655  nop
0x18001d656  mov     rdi, [rbp+var_30]
0x18001d65a  test    rdi, rdi
0x18001d65d  jz      loc_18001D7CE
0x18001d663  mov     [rbp+arg_10], rsi
0x18001d667  mov     rax, [rdi]
0x18001d66a  lea     r8, [rbp+arg_10]
0x18001d66e  lea     rdx, ??$guid_v@UIScrollViewer@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IScrollViewer>
0x18001d675  mov     rcx, rdi
0x18001d678  mov     rax, [rax]
0x18001d67b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d680  mov     rsi, [rbp+arg_10]
0x18001d684  mov     r14, rsi
0x18001d687  mov     [rbp+arg_18], rsi
0x18001d68b  test    rsi, rsi
0x18001d68e  jz      loc_18001D73D
0x18001d694  mov     [rbp+lpMem], 0
0x18001d69c  mov     [rbp+arg_10], 0
0x18001d6a4  mov     rax, [rsi]
0x18001d6a7  lea     r8, [rbp+arg_10]
0x18001d6ab  lea     rdx, ??$guid_v@UIFrameworkElement@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::IFrameworkElement>
0x18001d6b2  mov     rcx, rsi
0x18001d6b5  mov     rax, [rax]
0x18001d6b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6bd  mov     rcx, [rbp+arg_10]
0x18001d6c1  mov     [rbp+arg_10], rcx
0x18001d6c5  mov     [rbp+var_20], 0
0x18001d6cc  xorps   xmm0, xmm0
0x18001d6cf  movdqu  [rbp+var_18], xmm0
0x18001d6d4  test    eax, eax
0x18001d6d6  js      loc_18001DAE1
0x18001d6dc  mov     [rbp+var_20], 0
0x18001d6e3  movdqu  [rbp+var_18], xmm0
0x18001d6e8  mov     rax, [rcx]
0x18001d6eb  lea     rdx, [rbp+lpMem]
0x18001d6ef  mov     rax, [rax+108h]
0x18001d6f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6fb  test    eax, eax
0x18001d6fd  js      loc_18001DAD5
0x18001d703  lea     rcx, [rbp+arg_10]
0x18001d707  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001d70c  mov     rbx, [rbp+lpMem]
0x18001d710  or      r13d, 9
0x18001d714  test    rbx, rbx
0x18001d717  jz      short loc_18001D73D
0x18001d719  cmp     dword ptr [rbx+4], 13h
0x18001d71d  jnz     short loc_18001D73D
0x18001d71f  mov     r8d, 13h; N
0x18001d725  lea     rdx, aContentscrollv; "ContentScrollViewer"
0x18001d72c  mov     rcx, [rbx+10h]; S1
0x18001d730  call    wmemcmp
0x18001d735  test    eax, eax
0x18001d737  mov     byte ptr [rbp+arg_10], 0
0x18001d73b  jz      short loc_18001D741
0x18001d73d  mov     byte ptr [rbp+arg_10], r12b
0x18001d741  test    r12b, r13b
0x18001d744  jz      short loc_18001D777
0x18001d746  and     r13d, 0FFFFFFFEh
0x18001d74a  test    rbx, rbx
0x18001d74d  jz      short loc_18001D777
0x18001d74f  or      eax, 0FFFFFFFFh
0x18001d752  lock xadd [rbx+18h], eax
0x18001d757  sub     eax, 1
0x18001d75a  jnz     short loc_18001D771
0x18001d75c  nop
0x18001d75d  call    WINRT_IMPL_GetProcessHeap
0x18001d762  mov     rcx, rax; hHeap
0x18001d765  mov     r8, rbx; lpMem
0x18001d768  xor     edx, edx; dwFlags
0x18001d76a  call    WINRT_IMPL_HeapFree
0x18001d76f  jmp     short loc_18001D775
0x18001d771  test    eax, eax
0x18001d773  js      short loc_18001D7C7
0x18001d775  xor     ebx, ebx
0x18001d777  cmp     byte ptr [rbp+arg_10], 0
0x18001d77b  jz      short loc_18001D7B9
0x18001d77d  cmp     [rbp+arg_8], 0
0x18001d782  jz      short loc_18001D78D
0x18001d784  lea     rcx, [rbp+arg_8]
0x18001d788  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001d78d  mov     [rbp+arg_8], rdi
0x18001d791  test    rdi, rdi
0x18001d794  jz      short loc_18001D7A5
0x18001d796  mov     rax, [rdi]
0x18001d799  mov     rcx, rdi
0x18001d79c  mov     rax, [rax+8]
0x18001d7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7a5  test    r14, r14
0x18001d7a8  jz      short loc_18001D7B3
0x18001d7aa  lea     rcx, [rbp+arg_18]
0x18001d7ae  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001d7b3  xor     esi, esi
0x18001d7b5  mov     [rbp+arg_18], rsi
0x18001d7b9  lea     rcx, [rbp+var_30]
0x18001d7bd  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001d7c2  jmp     loc_18001D63F
0x18001d7c7  call    cs:__imp_abort
0x18001d7ce  jmp     short loc_18001D7D3
0x18001d7d0  xor     r12b, r12b
0x18001d7d3  mov     rcx, [rbp+40h]; this
0x18001d7d7  test    r12b, r12b
0x18001d7da  jnz     loc_18001DAED
0x18001d7e0  test    rsi, rsi
0x18001d7e3  jnz     short loc_18001D7EB
0x18001d7e5  mov     [rbp+arg_10], rsi
0x18001d7e9  jmp     short loc_18001D814
0x18001d7eb  mov     [rbp+var_30], 0
0x18001d7f3  mov     rax, [rsi]
0x18001d7f6  lea     r8, [rbp+var_30]
0x18001d7fa  lea     rdx, ??$guid_v@UIDependencyObject@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::IDependencyObject>
0x18001d801  mov     rcx, rsi
0x18001d804  mov     rax, [rax]
0x18001d807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d80c  mov     rax, [rbp+var_30]
0x18001d810  mov     [rbp+arg_10], rax
0x18001d814  lea     rdx, [rbp+arg_10]
0x18001d818  lea     rcx, [rbp+var_40]; struct winrt::Windows::UI::Xaml::DependencyObject *
0x18001d81c  call    ?GetParent@VisualTreeHelper@Media@Xaml@UI@Windows@winrt@@SA@AEBUDependencyObject@3456@@Z; winrt::Windows::UI::Xaml::Media::VisualTreeHelper::GetParent(winrt::Windows::UI::Xaml::DependencyObject const &)
0x18001d821  nop
0x18001d822  xor     r12d, r12d
0x18001d825  cmp     [rbp+arg_10], r12
0x18001d829  jz      short loc_18001D834
0x18001d82b  lea     rcx, [rbp+arg_10]
0x18001d82f  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001d834  mov     ecx, 0Ch; this
0x18001d839  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18001d83e  mov     rbx, rax
0x18001d841  lea     rcx, [rax+1Ch]; Destination
0x18001d845  mov     edx, 18h; DestinationSize
0x18001d84a  mov     r9d, edx; SourceSize
0x18001d84d  lea     r8, aCommandspace; "CommandSpace"
0x18001d854  call    memcpy_s
0x18001d859  mov     [rbp+var_30], rbx
0x18001d85d  lea     r8, [rbp+var_30]
0x18001d861  lea     rdx, [rbp+var_40]
0x18001d865  lea     rcx, [rbp+lpMem]
0x18001d869  call    ??$TryGetChildWithName@UGrid@Controls@Xaml@UI@Windows@winrt@@UDependencyObject@3456@@@YA?AUGrid@Controls@Xaml@UI@Windows@winrt@@AEAUDependencyObject@2345@Uhstring@5@@Z; TryGetChildWithName<winrt::Windows::UI::Xaml::Controls::Grid,winrt::Windows::UI::Xaml::DependencyObject>(winrt::Windows::UI::Xaml::DependencyObject &,winrt::hstring)
0x18001d86e  nop
0x18001d86f  mov     rbx, [rbp+lpMem]
0x18001d873  test    rbx, rbx
0x18001d876  setz    al
0x18001d879  mov     rcx, [rbp+40h]; this
0x18001d87d  test    al, al
0x18001d87f  jnz     loc_18001DAFF
0x18001d885  mov     ecx, 0Dh; this
0x18001d88a  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18001d88f  mov     rdi, rax
0x18001d892  lea     rcx, [rax+1Ch]; Destination
0x18001d896  mov     edx, 1Ah; DestinationSize
0x18001d89b  mov     r9d, edx; SourceSize
0x18001d89e  lea     r8, aPrimarybutton; "PrimaryButton"
0x18001d8a5  call    memcpy_s
0x18001d8aa  mov     [rbp+arg_10], rdi
0x18001d8ae  lea     r8, [rbp+arg_10]
0x18001d8b2  lea     rdx, [rbp+lpMem]
0x18001d8b6  lea     rcx, [rbp+var_28]
0x18001d8ba  call    ??$TryGetChildWithName@UButton@Controls@Xaml@UI@Windows@winrt@@UGrid@23456@@@YA?AUButton@Controls@Xaml@UI@Windows@winrt@@AEAUGrid@12345@Uhstring@5@@Z; TryGetChildWithName<winrt::Windows::UI::Xaml::Controls::Button,winrt::Windows::UI::Xaml::Controls::Grid>(winrt::Windows::UI::Xaml::Controls::Grid &,winrt::hstring)
0x18001d8bf  mov     rdi, rax
0x18001d8c2  mov     r13, [rbp+arg_0]
0x18001d8c6  lea     r14, [r13+1D0h]
0x18001d8cd  cmp     r14, rax
0x18001d8d0  jz      short loc_18001D8E8
0x18001d8d2  cmp     [r14], r12
0x18001d8d5  jz      short loc_18001D8DF
0x18001d8d7  mov     rcx, r14
0x18001d8da  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001d8df  mov     rcx, [rdi]
0x18001d8e2  mov     [rdi], r12
0x18001d8e5  mov     [r14], rcx
0x18001d8e8  cmp     [rbp+var_28], r12
0x18001d8ec  jz      short loc_18001D8F7
0x18001d8ee  lea     rcx, [rbp+var_28]
0x18001d8f2  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001d8f7  mov     rcx, [rbp+40h]; this
0x18001d8fb  cmp     [r14], r12
0x18001d8fe  jz      loc_18001DB11
0x18001d904  mov     ecx, 0Fh; this
0x18001d909  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18001d90e  mov     rdi, rax
0x18001d911  lea     rcx, [rax+1Ch]; Destination
0x18001d915  mov     edx, 1Eh; DestinationSize
0x18001d91a  mov     r9d, edx; SourceSize
0x18001d91d  lea     r8, aSecondarybutto; "SecondaryButton"
0x18001d924  call    memcpy_s
0x18001d929  mov     [rbp+arg_10], rdi
0x18001d92d  lea     r8, [rbp+arg_10]
0x18001d931  lea     rdx, [rbp+lpMem]
0x18001d935  lea     rcx, [rbp+var_28]
0x18001d939  call    ??$TryGetChildWithName@UButton@Controls@Xaml@UI@Windows@winrt@@UGrid@23456@@@YA?AUButton@Controls@Xaml@UI@Windows@winrt@@AEAUGrid@12345@Uhstring@5@@Z; TryGetChildWithName<winrt::Windows::UI::Xaml::Controls::Button,winrt::Windows::UI::Xaml::Controls::Grid>(winrt::Windows::UI::Xaml::Controls::Grid &,winrt::hstring)
0x18001d93e  nop
0x18001d93f  mov     r12, [rbp+var_28]
0x18001d943  test    r12, r12
0x18001d946  setz    al
0x18001d949  mov     rcx, [rbp+40h]; this
0x18001d94d  test    al, al
0x18001d94f  jnz     loc_18001DAA5
0x18001d955  lea     rdi, [r13+1D8h]
0x18001d95c  mov     rcx, [r14]
0x18001d95f  xor     r14d, r14d
0x18001d962  mov     [rbp+arg_10], r14
0x18001d966  test    rcx, rcx
0x18001d969  jnz     short loc_18001D970
0x18001d96b  mov     ecx, r14d
0x18001d96e  jmp     short loc_18001D98E
0x18001d970  mov     rax, [rcx]
0x18001d973  lea     r8, [rbp+arg_10]
0x18001d977  lea     rdx, ??$guid_v@UIControl@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IControl>
0x18001d97e  mov     rax, [rax]
0x18001d981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d986  mov     rcx, [rbp+arg_10]
0x18001d98a  mov     [rbp+arg_10], rcx
0x18001d98e  mov     rdx, [rdi+8]
0x18001d992  cmp     rdx, [rdi+10h]
0x18001d996  jz      short loc_18001D9A9
0x18001d998  mov     rax, r14
0x18001d99b  mov     [rbp+arg_10], rax
0x18001d99f  mov     [rdx], rcx
0x18001d9a2  add     qword ptr [rdi+8], 8
0x18001d9a7  jmp     short loc_18001D9B9
0x18001d9a9  lea     r8, [rbp+arg_10]
0x18001d9ad  mov     rcx, rdi
0x18001d9b0  call    ??$_Emplace_reallocate@UControl@Controls@Xaml@UI@Windows@winrt@@@?$vector@UControl@Controls@Xaml@UI@Windows@winrt@@V?$allocator@UControl@Controls@Xaml@UI@Windows@winrt@@@std@@@std@@AEAAPEAUControl@Controls@Xaml@UI@Windows@winrt@@QEAU234567@$$QEAU234567@@Z; std::vector<winrt::Windows::UI::Xaml::Controls::Control>::_Emplace_reallocate<winrt::Windows::UI::Xaml::Controls::Control>(winrt::Windows::UI::Xaml::Controls::Control * const,winrt::Windows::UI::Xaml::Controls::Control &&)
0x18001d9b5  mov     rax, [rbp+arg_10]
0x18001d9b9  test    rax, rax
0x18001d9bc  jz      short loc_18001D9C7
0x18001d9be  lea     rcx, [rbp+arg_10]
0x18001d9c2  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001d9c7  mov     [rbp+arg_10], r14
0x18001d9cb  test    r12, r12
0x18001d9ce  jnz     short loc_18001D9D5
0x18001d9d0  mov     rcx, r14
0x18001d9d3  jmp     short loc_18001D9F7
0x18001d9d5  mov     rax, [r12]
0x18001d9d9  lea     r8, [rbp+arg_10]
0x18001d9dd  lea     rdx, ??$guid_v@UIControl@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IControl>
0x18001d9e4  mov     rcx, r12
  ... truncated ...
```
