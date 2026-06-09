# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::GetExternalLinkControl(void)

- ea: `0x180011b80`
- end: `0x180012159`
- name: `?GetExternalLinkControl@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@IEAA?AUHyperlinkButton@Controls@Xaml@UI@67@XZ`
- size: `1497`
- prototype: `__int64 *__fastcall(_DWORD *, __int64 *)`
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180017a90`
- `0x1800209d4`

## callees

- `0x1800021e4`
- `0x180002d55`
- `0x180002d91`
- `0x18000b058`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18000bbe8`
- `0x18000cba4`
- `0x18000ee78`
- `0x18000f3bc`
- `0x180010464`
- `0x180011b80`
- `0x180012b2c`
- `0x180013188`
- `0x180013818`
- `0x180013860`
- `0x1800138a8`
- `0x18002d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011c86`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011db6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001205e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011c86`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011db6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001205e`

## string_xrefs

- `0x180011c60`: `ExternalLink`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::GetExternalLinkControl(
        _DWORD *a1,
        __int64 *a2)
{
  void *v4; // rbx
  int v5; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v7; // edx
  __int64 *v8; // rcx
  struct winrt::impl::shared_hstring_header *v9; // rdi
  unsigned int v10; // r15d
  const void *v11; // rbx
  int v12; // r15d
  void *v13; // rbx
  int v14; // eax
  HANDLE v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 (__fastcall ***v18)(_QWORD, void *, LPVOID *); // rcx
  int v19; // eax
  LPVOID v20; // rbx
  int v21; // eax
  __int64 (__fastcall ***v22)(_QWORD, void *, LPVOID *); // rcx
  int v23; // eax
  LPVOID v24; // rbx
  int v25; // eax
  __int64 (__fastcall ***v26)(_QWORD, void *, LPVOID *); // rcx
  int v27; // eax
  LPVOID v28; // rbx
  int v29; // eax
  _QWORD *v30; // rdi
  LPVOID v31; // rcx
  void *v32; // rbx
  int v33; // r14d
  HANDLE v34; // rax
  __int64 (__fastcall ***v35)(_QWORD, void *, LPVOID *); // rcx
  int v36; // eax
  LPVOID v37; // rbx
  int v38; // eax
  LPVOID v40; // [rsp+20h] [rbp-59h] BYREF
  __int128 v41; // [rsp+28h] [rbp-51h]
  __int64 v42; // [rsp+38h] [rbp-41h] BYREF
  int v43; // [rsp+40h] [rbp-39h]
  _OWORD v44[2]; // [rsp+50h] [rbp-29h] BYREF
  __int64 *v45; // [rsp+70h] [rbp-9h] BYREF
  struct winrt::impl::shared_hstring_header *v46; // [rsp+78h] [rbp-1h]
  int v47; // [rsp+80h] [rbp+7h]
  LPVOID lpMem; // [rsp+E0h] [rbp+67h] BYREF
  __int64 *v49; // [rsp+E8h] [rbp+6Fh]
  void (__fastcall ***v50)(_QWORD, void *, void **); // [rsp+F0h] [rbp+77h] BYREF
  void *v51; // [rsp+F8h] [rbp+7Fh] BYREF

  v49 = a2;
  v43 = 0;
  winrt::Windows::UI::Xaml::Controls::TextBlock::TextBlock((winrt::Windows::UI::Xaml::Controls::TextBlock *)&v50);
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::FontSize(&v50);
  LODWORD(lpMem) = 0;
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::HorizontalAlignment(
    &v50,
    &lpMem);
  LODWORD(lpMem) = 0;
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::VerticalAlignment(
    &v50,
    &lpMem);
  LODWORD(lpMem) = 2;
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::TextWrapping(
    &v50,
    &lpMem);
  *(_QWORD *)&v44[0] = *(_QWORD *)(*(__int64 (__fastcall **)(_DWORD *, LPVOID *))(*(_QWORD *)a1 + 48LL))(a1, &lpMem);
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::Text(
    &v50,
    v44);
  v4 = lpMem;
  if ( lpMem )
  {
    v5 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v5 )
    {
      if ( v5 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v4);
    }
  }
  *((_QWORD *)&v44[0] + 1) = 0xC00000001LL;
  *((_QWORD *)&v44[1] + 1) = L"ExternalLink";
  *(_QWORD *)&v44[0] = (char *)v44 + 8;
  if ( v50 )
  {
    v51 = 0;
    (**v50)(v50, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IDependencyObject>, &v51);
    lpMem = v51;
  }
  else
  {
    lpMem = 0;
  }
  winrt::Windows::UI::Xaml::Automation::AutomationProperties::SetAutomationId(
    (const struct winrt::Windows::UI::Xaml::DependencyObject *)&lpMem,
    (const struct winrt::param::hstring *)v44);
  if ( lpMem )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&lpMem);
  v9 = *(struct winrt::impl::shared_hstring_header **)(*(__int64 (__fastcall **)(_DWORD *, LPVOID *))(*(_QWORD *)a1 + 56LL))(
                                                        a1,
                                                        &lpMem);
  if ( !v9 )
    goto LABEL_12;
  if ( (*(_BYTE *)v9 & 1) != 0 )
  {
    v10 = *((_DWORD *)v9 + 1);
    if ( !v10 )
    {
LABEL_12:
      v9 = 0;
      goto LABEL_17;
    }
    v11 = (const void *)*((_QWORD *)v9 + 2);
    v9 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v10, v7);
    memcpy_s((char *)v9 + 28, 2LL * v10, v11, 2LL * v10);
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)v9 + 6);
  }
LABEL_17:
  v46 = v9;
  v12 = a1[20];
  v47 = v12;
  v13 = lpMem;
  if ( lpMem )
  {
    v14 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v14 )
    {
      if ( v14 < 0 )
        abort();
    }
    else
    {
      v15 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v15, 0, v13);
    }
  }
  *a2 = 0;
  v51 = 0;
  lpMem = 0;
  v40 = &v51;
  *(_QWORD *)&v41 = &lpMem;
  v45 = &qword_18003C198;
  _InterlockedIncrement64(&qword_18003C198);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::HyperlinkButton,winrt::Windows::UI::Xaml::Controls::IHyperlinkButtonFactory> )
  {
    `winrt::Windows::UI::Xaml::Controls::HyperlinkButton::HyperlinkButton'::`2'::_lambda_1_::operator()(
      &v40,
      &v42,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::HyperlinkButton,winrt::Windows::UI::Xaml::Controls::IHyperlinkButtonFactory>);
    _InterlockedAdd64(&qword_18003C198, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_18003C198, 0xFFFFFFFFFFFFFFFFuLL);
    ___call_AEAV_lambda_1___1___0HyperlinkButton_Controls_Xaml_UI_Windows_winrt__QEAA_XZ____factory_cache_entry_UHyperlinkButton_Controls_Xaml_UI_Windows_winrt__UIHyperlinkButtonFactory_23456__impl_winrt__QEAA_A_PAEAV_lambda_1___1___0HyperlinkButton_Controls_Xaml_UI_Windows_2_QEAA_XZ__Z(
      v8,
      (__int64)&v42,
      (__int64)&v40);
  }
  if ( a2 == &v42 )
  {
    v17 = v42;
  }
  else
  {
    if ( *a2 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(a2);
    v16 = v42;
    v17 = 0;
    v42 = 0;
    *a2 = v16;
  }
  if ( v17 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v42);
  if ( lpMem )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&lpMem);
  if ( v51 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v51);
  v43 = 3;
  v18 = (__int64 (__fastcall ***)(_QWORD, void *, LPVOID *))*a2;
  lpMem = 0;
  if ( v18 )
  {
    v19 = (**v18)(v18, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IControl>, &lpMem);
    v20 = lpMem;
  }
  else
  {
    v19 = 0;
    v20 = 0;
  }
  LODWORD(v40) = 0;
  v41 = 0;
  if ( v19 < 0 )
    winrt::throw_hresult((unsigned int)v19, &v40);
  LODWORD(v40) = 0;
  v41 = 0;
  memset(v44, 0, sizeof(v44));
  v21 = (*(__int64 (__fastcall **)(LPVOID, _OWORD *))(*(_QWORD *)v20 + 248LL))(v20, v44);
  if ( v21 < 0 )
    winrt::throw_hresult((unsigned int)v21, &v40);
  if ( v20 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&lpMem);
  v22 = (__int64 (__fastcall ***)(_QWORD, void *, LPVOID *))*a2;
  lpMem = 0;
  if ( v22 )
  {
    v23 = (**v22)(v22, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IFrameworkElement>, &lpMem);
    v24 = lpMem;
  }
  else
  {
    v23 = 0;
    v24 = 0;
  }
  LODWORD(v40) = 0;
  v41 = 0;
  if ( v23 < 0 )
    winrt::throw_hresult((unsigned int)v23, &v40);
  LODWORD(v40) = 0;
  v41 = 0;
  v44[0] = 0;
  v44[1] = _mm_load_si128((const __m128i *)&_xmm);
  v25 = (*(__int64 (__fastcall **)(LPVOID, _OWORD *))(*(_QWORD *)v24 + 256LL))(v24, v44);
  if ( v25 < 0 )
    winrt::throw_hresult((unsigned int)v25, &v40);
  if ( v24 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&lpMem);
  v26 = (__int64 (__fastcall ***)(_QWORD, void *, LPVOID *))*a2;
  lpMem = 0;
  if ( v26 )
  {
    v27 = (**v26)(v26, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IContentControl>, &lpMem);
    v28 = lpMem;
  }
  else
  {
    v27 = 0;
    v28 = 0;
  }
  LODWORD(v40) = 0;
  v41 = 0;
  if ( v27 < 0 )
    winrt::throw_hresult((unsigned int)v27, &v40);
  LODWORD(v40) = 0;
  v41 = 0;
  v29 = (*(__int64 (__fastcall **)(LPVOID, void (__fastcall ***)(_QWORD, void *, void **)))(*(_QWORD *)v28 + 56LL))(
          v28,
          v50);
  if ( v29 < 0 )
    winrt::throw_hresult((unsigned int)v29, &v40);
  if ( v28 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&lpMem);
  v46 = 0;
  v40 = v9;
  LODWORD(v41) = v12;
  lpMem = &v40;
  v30 = operator new(0x20u);
  lpMem = v30;
  *((_DWORD *)v30 + 2) = 1;
  v31 = v40;
  v40 = 0;
  v30[2] = v31;
  *((_DWORD *)v30 + 6) = v41;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *v30 = off_18002E540;
  v45 = v30;
  v43 = 7;
  v32 = v40;
  if ( v40 )
  {
    v33 = _InterlockedDecrement((volatile signed __int32 *)v40 + 6);
    if ( v33 )
    {
      if ( v33 < 0 )
        abort();
    }
    else
    {
      v34 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v34, 0, v32);
    }
    v40 = 0;
  }
  v51 = 0;
  v35 = (__int64 (__fastcall ***)(_QWORD, void *, LPVOID *))*a2;
  lpMem = 0;
  if ( v35 )
  {
    v36 = (**v35)(v35, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::Primitives::IButtonBase>, &lpMem);
    v37 = lpMem;
  }
  else
  {
    v36 = 0;
    v37 = 0;
  }
  LODWORD(v44[0]) = 0;
  *(_OWORD *)((char *)v44 + 8) = 0;
  if ( v36 < 0 )
    winrt::throw_hresult((unsigned int)v36, v44);
  LODWORD(v44[0]) = 0;
  *(_OWORD *)((char *)v44 + 8) = 0;
  v38 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *, void **))(*(_QWORD *)v37 + 112LL))(v37, v30, &v51);
  if ( v38 < 0 )
    winrt::throw_hresult((unsigned int)v38, v44);
  if ( v37 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&lpMem);
  winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v45);
  if ( v50 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v50);
  return a2;
}

```

## disassembly

```asm
0x180011b80  mov     [rsp-8+arg_8], rdx
0x180011b85  push    rbp
0x180011b86  push    rbx
0x180011b87  push    rsi
0x180011b88  push    rdi
0x180011b89  push    r12
0x180011b8b  push    r13
0x180011b8d  push    r14
0x180011b8f  push    r15
0x180011b91  lea     rbp, [rsp-1Fh]
0x180011b96  sub     rsp, 98h
0x180011b9d  mov     rsi, rdx
0x180011ba0  mov     r12, rcx
0x180011ba3  xor     r13d, r13d
0x180011ba6  mov     [rbp+57h+var_90], r13d
0x180011baa  lea     rcx, [rbp+57h+arg_10]; this
0x180011bae  call    ??0TextBlock@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ; winrt::Windows::UI::Xaml::Controls::TextBlock::TextBlock(void)
0x180011bb3  nop
0x180011bb4  movsd   xmm1, cs:__real@402c000000000000
0x180011bbc  lea     rcx, [rbp+57h+arg_10]
0x180011bc0  call    ?FontSize@?$consume_Windows_UI_Xaml_Controls_ITextBlock@UITextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@N@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::FontSize(double)
0x180011bc5  mov     dword ptr [rbp+57h+lpMem], r13d
0x180011bc9  lea     rdx, [rbp+57h+lpMem]
0x180011bcd  lea     rcx, [rbp+57h+arg_10]
0x180011bd1  call    ?HorizontalAlignment@?$consume_Windows_UI_Xaml_IFrameworkElement@UTextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBW40Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::HorizontalAlignment(winrt::Windows::UI::Xaml::HorizontalAlignment const &)
0x180011bd6  mov     dword ptr [rbp+57h+lpMem], r13d
0x180011bda  lea     rdx, [rbp+57h+lpMem]
0x180011bde  lea     rcx, [rbp+57h+arg_10]
0x180011be2  call    ?VerticalAlignment@?$consume_Windows_UI_Xaml_IFrameworkElement@UTextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBW40Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::VerticalAlignment(winrt::Windows::UI::Xaml::VerticalAlignment const &)
0x180011be7  mov     dword ptr [rbp+57h+lpMem], 2
0x180011bee  lea     rdx, [rbp+57h+lpMem]
0x180011bf2  lea     rcx, [rbp+57h+arg_10]
0x180011bf6  call    ?TextWrapping@?$consume_Windows_UI_Xaml_Controls_ITextBlock@UITextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBW40Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::TextWrapping(winrt::Windows::UI::Xaml::TextWrapping const &)
0x180011bfb  mov     rax, [r12]
0x180011bff  lea     rdx, [rbp+57h+lpMem]
0x180011c03  mov     rcx, r12
0x180011c06  mov     rax, [rax+30h]
0x180011c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c0f  nop
0x180011c10  mov     rax, [rax]
0x180011c13  mov     qword ptr [rbp+57h+var_80], rax
0x180011c17  lea     rdx, [rbp+57h+var_80]
0x180011c1b  lea     rcx, [rbp+57h+arg_10]
0x180011c1f  call    ?Text@?$consume_Windows_UI_Xaml_Controls_ITextBlock@UITextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::Text(winrt::param::hstring const &)
0x180011c24  nop
0x180011c25  mov     rbx, [rbp+57h+lpMem]
0x180011c29  or      r14, 0FFFFFFFFFFFFFFFFh
0x180011c2d  test    rbx, rbx
0x180011c30  jz      short loc_180011C52
0x180011c32  mov     eax, r14d
0x180011c35  lock xadd [rbx+18h], eax
0x180011c3a  sub     eax, 1
0x180011c3d  jnz     short loc_180011C82
0x180011c3f  nop
0x180011c40  call    WINRT_IMPL_GetProcessHeap
0x180011c45  mov     rcx, rax; hHeap
0x180011c48  mov     r8, rbx; lpMem
0x180011c4b  xor     edx, edx; dwFlags
0x180011c4d  call    WINRT_IMPL_HeapFree
0x180011c52  mov     dword ptr [rbp+57h+var_80+8], 1
0x180011c59  mov     dword ptr [rbp+57h+var_80+0Ch], 0Ch
0x180011c60  lea     rax, aExternallink; "ExternalLink"
0x180011c67  mov     [rbp+57h+var_68], rax
0x180011c6b  lea     rax, [rbp+57h+var_80+8]
0x180011c6f  mov     qword ptr [rbp+57h+var_80], rax
0x180011c73  mov     rcx, [rbp+57h+arg_10]
0x180011c77  test    rcx, rcx
0x180011c7a  jnz     short loc_180011C8D
0x180011c7c  mov     [rbp+57h+lpMem], r13
0x180011c80  jmp     short loc_180011CAF
0x180011c82  test    eax, eax
0x180011c84  jns     short loc_180011C52
0x180011c86  call    cs:__imp_abort
0x180011c8d  mov     [rbp+57h+arg_18], r13
0x180011c91  mov     rax, [rcx]
0x180011c94  lea     r8, [rbp+57h+arg_18]
0x180011c98  lea     rdx, ??$guid_v@UIDependencyObject@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::IDependencyObject>
0x180011c9f  mov     rax, [rax]
0x180011ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ca7  mov     rax, [rbp+57h+arg_18]
0x180011cab  mov     [rbp+57h+lpMem], rax
0x180011caf  lea     rdx, [rbp+57h+var_80]; struct winrt::param::hstring *
0x180011cb3  lea     rcx, [rbp+57h+lpMem]; struct winrt::Windows::UI::Xaml::DependencyObject *
0x180011cb7  call    ?SetAutomationId@AutomationProperties@Automation@Xaml@UI@Windows@winrt@@SA@AEBUDependencyObject@3456@AEBUhstring@param@6@@Z; winrt::Windows::UI::Xaml::Automation::AutomationProperties::SetAutomationId(winrt::Windows::UI::Xaml::DependencyObject const &,winrt::param::hstring const &)
0x180011cbc  nop
0x180011cbd  cmp     [rbp+57h+lpMem], r13
0x180011cc1  jz      short loc_180011CCC
0x180011cc3  lea     rcx, [rbp+57h+lpMem]
0x180011cc7  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180011ccc  mov     rax, [r12]
0x180011cd0  lea     rdx, [rbp+57h+lpMem]
0x180011cd4  mov     rcx, r12
0x180011cd7  mov     rax, [rax+38h]
0x180011cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ce0  nop
0x180011ce1  mov     rdi, [rax]
0x180011ce4  test    rdi, rdi
0x180011ce7  jnz     short loc_180011CEE
0x180011ce9  mov     rdi, r13
0x180011cec  jmp     short loc_180011D26
0x180011cee  test    byte ptr [rdi], 1
0x180011cf1  jnz     short loc_180011CF9
0x180011cf3  lock inc dword ptr [rdi+18h]
0x180011cf7  jmp     short loc_180011D26
0x180011cf9  mov     r15d, [rdi+4]
0x180011cfd  test    r15d, r15d
0x180011d00  jz      short loc_180011CE9
0x180011d02  mov     rbx, [rdi+10h]
0x180011d06  mov     ecx, r15d; this
0x180011d09  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180011d0e  mov     rdi, rax
0x180011d11  mov     edx, r15d
0x180011d14  add     rdx, rdx; DestinationSize
0x180011d17  lea     rcx, [rax+1Ch]; Destination
0x180011d1b  mov     r9, rdx; SourceSize
0x180011d1e  mov     r8, rbx; Source
0x180011d21  call    memcpy_s
0x180011d26  mov     [rbp+57h+var_58], rdi
0x180011d2a  mov     r15d, [r12+50h]
0x180011d2f  mov     [rbp+57h+var_50], r15d
0x180011d33  mov     rbx, [rbp+57h+lpMem]
0x180011d37  test    rbx, rbx
0x180011d3a  jz      short loc_180011D5C
0x180011d3c  mov     eax, r14d
0x180011d3f  lock xadd [rbx+18h], eax
0x180011d44  sub     eax, 1
0x180011d47  jnz     short loc_180011DB2
0x180011d49  nop
0x180011d4a  call    WINRT_IMPL_GetProcessHeap
0x180011d4f  mov     rcx, rax; hHeap
0x180011d52  mov     r8, rbx; lpMem
0x180011d55  xor     edx, edx; dwFlags
0x180011d57  call    WINRT_IMPL_HeapFree
0x180011d5c  mov     [rsi], r13
0x180011d5f  mov     [rbp+57h+arg_18], r13
0x180011d63  mov     [rbp+57h+lpMem], r13
0x180011d67  lea     rax, [rbp+57h+arg_18]
0x180011d6b  mov     [rbp+57h+var_B0], rax
0x180011d6f  lea     rax, [rbp+57h+lpMem]
0x180011d73  mov     qword ptr [rbp+57h+var_A8], rax
0x180011d77  lea     rax, qword_18003C198
0x180011d7e  mov     [rbp+57h+var_60], rax
0x180011d82  lock inc cs:qword_18003C198
0x180011d8a  cmp     cs:??$factory_cache_entry_v@UHyperlinkButton@Controls@Xaml@UI@Windows@winrt@@UIHyperlinkButtonFactory@23456@@impl@winrt@@3U?$factory_cache_entry@UHyperlinkButton@Controls@Xaml@UI@Windows@winrt@@UIHyperlinkButtonFactory@23456@@12@A, r13; factory_cache_entry<winrt::Windows::UI::Xaml::Controls::HyperlinkButton,winrt::Windows::UI::Xaml::Controls::IHyperlinkButtonFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::HyperlinkButton,winrt::Windows::UI::Xaml::Controls::IHyperlinkButtonFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::HyperlinkButton,winrt::Windows::UI::Xaml::Controls::IHyperlinkButtonFactory>
0x180011d91  jz      short loc_180011DBD
0x180011d93  lea     r8, ??$factory_cache_entry_v@UHyperlinkButton@Controls@Xaml@UI@Windows@winrt@@UIHyperlinkButtonFactory@23456@@impl@winrt@@3U?$factory_cache_entry@UHyperlinkButton@Controls@Xaml@UI@Windows@winrt@@UIHyperlinkButtonFactory@23456@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Controls::HyperlinkButton,winrt::Windows::UI::Xaml::Controls::IHyperlinkButtonFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::HyperlinkButton,winrt::Windows::UI::Xaml::Controls::IHyperlinkButtonFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::HyperlinkButton,winrt::Windows::UI::Xaml::Controls::IHyperlinkButtonFactory>
0x180011d9a  lea     rdx, [rbp+57h+var_98]
0x180011d9e  lea     rcx, [rbp+57h+var_B0]
0x180011da2  call    ??R_lambda_1_@?1???0HyperlinkButton@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ@QEBA@AEBUIHyperlinkButtonFactory@23456@@Z; `winrt::Windows::UI::Xaml::Controls::HyperlinkButton::HyperlinkButton(void)'::`2'::_lambda_1_::operator()(winrt::Windows::UI::Xaml::Controls::IHyperlinkButtonFactory const &)
0x180011da7  nop
0x180011da8  lock add cs:qword_18003C198, r14
0x180011db0  jmp     short loc_180011DD2
0x180011db2  test    eax, eax
0x180011db4  jns     short loc_180011D5C
0x180011db6  call    cs:__imp_abort
0x180011dbd  lock add cs:qword_18003C198, r14
0x180011dc5  lea     r8, [rbp+57h+var_B0]
0x180011dc9  lea     rdx, [rbp+57h+var_98]
0x180011dcd  call    ??$call@AEAV_lambda_1_@?1???0HyperlinkButton@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ@@?$factory_cache_entry@UHyperlinkButton@Controls@Xaml@UI@Windows@winrt@@UIHyperlinkButtonFactory@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1???0HyperlinkButton@Controls@Xaml@UI@Windows@2@QEAA@XZ@@Z
0x180011dd2  lea     rax, [rbp+57h+var_98]
0x180011dd6  cmp     rsi, rax
0x180011dd9  jz      short loc_180011DF8
0x180011ddb  cmp     [rsi], r13
0x180011dde  jz      short loc_180011DE8
0x180011de0  mov     rcx, rsi
0x180011de3  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180011de8  mov     rcx, [rbp+57h+var_98]
0x180011dec  mov     rax, r13
0x180011def  mov     [rbp+57h+var_98], rax
0x180011df3  mov     [rsi], rcx
0x180011df6  jmp     short loc_180011DFC
0x180011df8  mov     rax, [rbp+57h+var_98]
0x180011dfc  test    rax, rax
0x180011dff  jz      short loc_180011E0B
0x180011e01  lea     rcx, [rbp+57h+var_98]
0x180011e05  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180011e0a  nop
0x180011e0b  cmp     [rbp+57h+lpMem], r13
0x180011e0f  jz      short loc_180011E1B
0x180011e11  lea     rcx, [rbp+57h+lpMem]
0x180011e15  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180011e1a  nop
0x180011e1b  cmp     [rbp+57h+arg_18], r13
0x180011e1f  jz      short loc_180011E2B
0x180011e21  lea     rcx, [rbp+57h+arg_18]
0x180011e25  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180011e2a  nop
0x180011e2b  mov     [rbp+57h+var_90], 3
0x180011e32  mov     rcx, [rsi]
0x180011e35  mov     [rbp+57h+lpMem], r13
0x180011e39  test    rcx, rcx
0x180011e3c  jnz     short loc_180011E46
0x180011e3e  mov     eax, r13d
0x180011e41  mov     rbx, r13
0x180011e44  jmp     short loc_180011E64
0x180011e46  mov     rax, [rcx]
0x180011e49  lea     r8, [rbp+57h+lpMem]
0x180011e4d  lea     rdx, ??$guid_v@UIControl@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IControl>
0x180011e54  mov     rax, [rax]
0x180011e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e5c  mov     rbx, [rbp+57h+lpMem]
0x180011e60  mov     [rbp+57h+lpMem], rbx
0x180011e64  mov     dword ptr [rbp+57h+var_B0], r13d
0x180011e68  xorps   xmm0, xmm0
0x180011e6b  movdqu  [rbp+57h+var_A8], xmm0
0x180011e70  test    eax, eax
0x180011e72  js      loc_180012105
0x180011e78  mov     dword ptr [rbp+57h+var_B0], r13d
0x180011e7c  movdqu  [rbp+57h+var_A8], xmm0
0x180011e81  movaps  [rbp+57h+var_80], xmm0
0x180011e85  xorps   xmm1, xmm1
0x180011e88  movaps  xmmword ptr [rbp-19h], xmm1
0x180011e8c  mov     rax, [rbx]
0x180011e8f  lea     rdx, [rbp+57h+var_80]
0x180011e93  mov     rcx, rbx
0x180011e96  mov     rax, [rax+0F8h]
0x180011e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ea2  test    eax, eax
0x180011ea4  js      loc_180012111
0x180011eaa  test    rbx, rbx
0x180011ead  jz      short loc_180011EB8
0x180011eaf  lea     rcx, [rbp+57h+lpMem]
0x180011eb3  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180011eb8  mov     rcx, [rsi]
0x180011ebb  mov     [rbp+57h+lpMem], r13
0x180011ebf  test    rcx, rcx
0x180011ec2  jnz     short loc_180011ECC
0x180011ec4  mov     eax, r13d
0x180011ec7  mov     rbx, r13
0x180011eca  jmp     short loc_180011EEA
0x180011ecc  mov     rax, [rcx]
0x180011ecf  lea     r8, [rbp+57h+lpMem]
0x180011ed3  lea     rdx, ??$guid_v@UIFrameworkElement@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::IFrameworkElement>
0x180011eda  mov     rax, [rax]
0x180011edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ee2  mov     rbx, [rbp+57h+lpMem]
0x180011ee6  mov     [rbp+57h+lpMem], rbx
0x180011eea  mov     dword ptr [rbp+57h+var_B0], r13d
0x180011eee  xorps   xmm0, xmm0
0x180011ef1  movdqu  [rbp+57h+var_A8], xmm0
0x180011ef6  test    eax, eax
0x180011ef8  js      loc_18001211D
0x180011efe  mov     dword ptr [rbp+57h+var_B0], r13d
0x180011f02  movdqu  [rbp+57h+var_A8], xmm0
0x180011f07  movaps  [rbp+57h+var_80], xmm0
0x180011f0b  movdqa  xmm1, cs:__xmm@40380000000000000000000000000000
0x180011f13  movaps  xmmword ptr [rbp-19h], xmm1
0x180011f17  mov     rax, [rbx]
0x180011f1a  lea     rdx, [rbp+57h+var_80]
0x180011f1e  mov     rcx, rbx
0x180011f21  mov     rax, [rax+100h]
0x180011f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f2d  test    eax, eax
0x180011f2f  js      loc_180012129
0x180011f35  test    rbx, rbx
0x180011f38  jz      short loc_180011F43
0x180011f3a  lea     rcx, [rbp+57h+lpMem]
0x180011f3e  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180011f43  mov     rcx, [rsi]
0x180011f46  mov     [rbp+57h+lpMem], r13
0x180011f4a  test    rcx, rcx
0x180011f4d  jnz     short loc_180011F57
0x180011f4f  mov     eax, r13d
0x180011f52  mov     rbx, r13
0x180011f55  jmp     short loc_180011F75
0x180011f57  mov     rax, [rcx]
0x180011f5a  lea     r8, [rbp+57h+lpMem]
0x180011f5e  lea     rdx, ??$guid_v@UIContentControl@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IContentControl>
0x180011f65  mov     rax, [rax]
0x180011f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f6d  mov     rbx, [rbp+57h+lpMem]
0x180011f71  mov     [rbp+57h+lpMem], rbx
0x180011f75  mov     dword ptr [rbp+57h+var_B0], r13d
0x180011f79  xorps   xmm0, xmm0
0x180011f7c  movdqu  [rbp+57h+var_A8], xmm0
0x180011f81  test    eax, eax
0x180011f83  js      loc_180012135
0x180011f89  mov     dword ptr [rbp+57h+var_B0], r13d
0x180011f8d  movdqu  [rbp+57h+var_A8], xmm0
0x180011f92  mov     rax, [rbx]
0x180011f95  mov     rdx, [rbp+57h+arg_10]
0x180011f99  mov     rcx, rbx
0x180011f9c  mov     rax, [rax+38h]
0x180011fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fa5  test    eax, eax
0x180011fa7  js      loc_180012141
0x180011fad  test    rbx, rbx
0x180011fb0  jz      short loc_180011FBB
0x180011fb2  lea     rcx, [rbp+57h+lpMem]
0x180011fb6  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180011fbb  mov     [rbp+57h+var_58], r13
0x180011fbf  mov     [rbp+57h+var_B0], rdi
0x180011fc3  mov     dword ptr [rbp+57h+var_A8], r15d
0x180011fc7  lea     rax, [rbp+57h+var_B0]
0x180011fcb  mov     [rbp+57h+lpMem], rax
0x180011fcf  mov     ecx, 20h ; ' '; Size
0x180011fd4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011fd9  mov     rdi, rax
0x180011fdc  mov     [rbp+57h+lpMem], rax
0x180011fe0  mov     dword ptr [rax+8], 1
  ... truncated ...
```
