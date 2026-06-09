# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::_GetWarningInfobar(void)

- ea: `0x1800226a8`
- end: `0x18002293c`
- name: `?_GetWarningInfobar@FirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@AEAA?AV?$optional@UStackPanel@Controls@Xaml@UI@Windows@winrt@@@std@@XZ`
- size: `660`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18001e0b0`

## callees

- `0x180002d55`
- `0x180002d91`
- `0x180007940`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18000ed88`
- `0x18000ff68`
- `0x18000ffac`
- `0x180012df8`
- `0x180013188`
- `0x18001ca68`
- `0x1800226a8`
- `0x18002d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022813`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022813`

## string_xrefs

- `0x1800227e9`: `ReadOnlyInfobar`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::_GetWarningInfobar(
        __int64 a1,
        __int64 a2)
{
  _QWORD *ResourceString; // rax
  int v4; // eax
  void *v5; // rdi
  int v6; // eax
  HANDLE ProcessHeap; // rax
  int v8; // eax
  int v9; // eax
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rdi
  __int64 v13; // rcx
  __int64 v14; // rax
  void *v16; // [rsp+28h] [rbp-38h] BYREF
  __int64 v17; // [rsp+30h] [rbp-30h] BYREF
  __m256i v18; // [rsp+38h] [rbp-28h] BYREF
  __int64 v19; // [rsp+80h] [rbp+20h] BYREF
  __int64 v20; // [rsp+90h] [rbp+30h] BYREF
  LPVOID lpMem; // [rsp+98h] [rbp+38h] BYREF

  if ( *(_BYTE *)(a1 + 525) )
  {
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    winrt::Windows::UI::Xaml::Controls::StackPanel::StackPanel((winrt::Windows::UI::Xaml::Controls::StackPanel *)&v20);
    *(_OWORD *)v18.m256i_i8 = 0;
    *(__m128i *)&v18.m256i_u64[2] = _mm_load_si128((const __m128i *)&_xmm);
    winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::StackPanel>::Margin(
      &v20,
      &v18);
    winrt::Microsoft::UI::Xaml::Controls::InfoBar::InfoBar((winrt::Microsoft::UI::Xaml::Controls::InfoBar *)&v19);
    ResourceString = (_QWORD *)GetResourceString(&lpMem, 170);
    v18.m256i_i32[0] = 0;
    *(_OWORD *)&v18.m256i_u64[1] = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v19 + 72LL))(v19, *ResourceString);
    if ( v4 < 0 )
      winrt::throw_hresult((unsigned int)v4, &v18);
    v5 = lpMem;
    if ( lpMem )
    {
      v6 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v6 )
      {
        if ( v6 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v5);
      }
    }
    v18.m256i_i32[0] = 0;
    *(_OWORD *)&v18.m256i_u64[1] = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 104LL))(v19, 2);
    if ( v8 < 0 )
      winrt::throw_hresult((unsigned int)v8, &v18);
    v18.m256i_i32[0] = 0;
    *(_OWORD *)&v18.m256i_u64[1] = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v19 + 152LL))(v19, 0);
    if ( v9 < 0 )
      winrt::throw_hresult((unsigned int)v9, &v18);
    v18.m256i_i32[0] = 0;
    *(_OWORD *)&v18.m256i_u64[1] = 0;
    LOBYTE(v10) = 1;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 56LL))(v19, v10);
    if ( v11 < 0 )
      winrt::throw_hresult((unsigned int)v11, &v18);
    v18.m256i_i64[1] = 0xF00000001LL;
    v18.m256i_i64[3] = (__int64)L"ReadOnlyInfobar";
    v18.m256i_i64[0] = (__int64)&v18.m256i_i64[1];
    if ( v19 )
    {
      v16 = 0;
      (**(void (__fastcall ***)(__int64, void *, void **))v19)(
        v19,
        &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IDependencyObject>,
        &v16);
      lpMem = v16;
    }
    else
    {
      lpMem = 0;
    }
    winrt::Windows::UI::Xaml::Automation::AutomationProperties::SetAutomationId(
      (const struct winrt::Windows::UI::Xaml::DependencyObject *)&lpMem,
      (const struct winrt::param::hstring *)&v18);
    if ( lpMem )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&lpMem);
    v12 = winrt::impl::consume_Windows_UI_Xaml_Controls_IPanel<winrt::Windows::UI::Xaml::Controls::Grid>::Children(
            &v20,
            &v17);
    if ( v19 )
    {
      v16 = 0;
      (**(void (__fastcall ***)(__int64, void *, void **))v19)(
        v19,
        &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IUIElement>,
        &v16);
      lpMem = v16;
    }
    else
    {
      lpMem = 0;
    }
    winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Xaml::Controls::ColumnDefinition>,winrt::Windows::UI::Xaml::Controls::ColumnDefinition>::Append(
      v12,
      &lpMem);
    if ( lpMem )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&lpMem);
    if ( v17 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v17);
    v13 = v20;
    v14 = 0;
    v20 = 0;
    *(_QWORD *)a2 = v13;
    *(_BYTE *)(a2 + 8) = 1;
    if ( v19 )
    {
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v19);
      v14 = v20;
    }
    if ( v14 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v20);
  }
  return a2;
}

```

## disassembly

```asm
0x1800226a8  mov     [rsp-18h+arg_8], rbx
0x1800226ad  push    rbp
0x1800226ae  push    rsi
0x1800226af  push    rdi
0x1800226b0  mov     rbp, rsp
0x1800226b3  sub     rsp, 60h
0x1800226b7  mov     rbx, rdx
0x1800226ba  xor     esi, esi
0x1800226bc  cmp     [rcx+20Dh], sil
0x1800226c3  jz      short loc_1800226CE
0x1800226c5  mov     [rdx+8], sil
0x1800226c9  jmp     loc_1800228F9
0x1800226ce  lea     rcx, [rbp+arg_10]; this
0x1800226d2  call    ??0StackPanel@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ; winrt::Windows::UI::Xaml::Controls::StackPanel::StackPanel(void)
0x1800226d7  nop
0x1800226d8  xorps   xmm0, xmm0
0x1800226db  movups  [rbp+var_28], xmm0
0x1800226df  movdqa  xmm1, cs:__xmm@40240000000000000000000000000000
0x1800226e7  movups  [rbp+var_18], xmm1
0x1800226eb  lea     rdx, [rbp+var_28]
0x1800226ef  lea     rcx, [rbp+arg_10]
0x1800226f3  call    ?Margin@?$consume_Windows_UI_Xaml_IFrameworkElement@UStackPanel@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUThickness@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::StackPanel>::Margin(winrt::Windows::UI::Xaml::Thickness const &)
0x1800226f8  lea     rcx, [rbp+arg_0]; this
0x1800226fc  call    ??0InfoBar@Controls@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::Controls::InfoBar::InfoBar(void)
0x180022701  nop
0x180022702  mov     edx, 0AAh
0x180022707  lea     rcx, [rbp+lpMem]
0x18002270b  call    ?GetResourceString@@YA?AUhstring@winrt@@I@Z; GetResourceString(uint)
0x180022710  mov     r8, rax
0x180022713  mov     rcx, [rbp+arg_0]
0x180022717  mov     dword ptr [rbp+var_28], esi
0x18002271a  xorps   xmm0, xmm0
0x18002271d  movdqu  [rbp+var_28+8], xmm0
0x180022722  mov     rdx, [rcx]
0x180022725  mov     rax, [rdx+48h]
0x180022729  mov     rdx, [r8]
0x18002272c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022731  test    eax, eax
0x180022733  js      loc_180022918
0x180022739  mov     rdi, [rbp+lpMem]
0x18002273d  test    rdi, rdi
0x180022740  jz      short loc_180022766
0x180022742  or      eax, 0FFFFFFFFh
0x180022745  lock xadd [rdi+18h], eax
0x18002274a  sub     eax, 1
0x18002274d  jnz     loc_18002280B
0x180022753  nop
0x180022754  call    WINRT_IMPL_GetProcessHeap
0x180022759  mov     rcx, rax; hHeap
0x18002275c  mov     r8, rdi; lpMem
0x18002275f  xor     edx, edx; dwFlags
0x180022761  call    WINRT_IMPL_HeapFree
0x180022766  mov     rcx, [rbp+arg_0]
0x18002276a  mov     dword ptr [rbp+var_28], esi
0x18002276d  xorps   xmm0, xmm0
0x180022770  movdqu  [rbp+var_28+8], xmm0
0x180022775  mov     rax, [rcx]
0x180022778  mov     edx, 2
0x18002277d  mov     rax, [rax+68h]
0x180022781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022786  test    eax, eax
0x180022788  js      loc_180022924
0x18002278e  mov     rcx, [rbp+arg_0]
0x180022792  mov     dword ptr [rbp+var_28], esi
0x180022795  xorps   xmm0, xmm0
0x180022798  movdqu  [rbp+var_28+8], xmm0
0x18002279d  mov     rax, [rcx]
0x1800227a0  xor     edx, edx
0x1800227a2  mov     rax, [rax+98h]
0x1800227a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227ae  test    eax, eax
0x1800227b0  js      loc_180022930
0x1800227b6  mov     rcx, [rbp+arg_0]
0x1800227ba  mov     dword ptr [rbp+var_28], esi
0x1800227bd  xorps   xmm0, xmm0
0x1800227c0  movdqu  [rbp+var_28+8], xmm0
0x1800227c5  mov     rax, [rcx]
0x1800227c8  mov     dl, 1
0x1800227ca  mov     rax, [rax+38h]
0x1800227ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227d3  test    eax, eax
0x1800227d5  js      loc_18002290C
0x1800227db  mov     dword ptr [rbp+var_28+8], 1
0x1800227e2  mov     dword ptr [rbp+var_28+0Ch], 0Fh
0x1800227e9  lea     rax, aReadonlyinfoba; "ReadOnlyInfobar"
0x1800227f0  mov     qword ptr [rbp+var_18+8], rax
0x1800227f4  lea     rax, [rbp+var_28+8]
0x1800227f8  mov     qword ptr [rbp+var_28], rax
0x1800227fc  mov     rcx, [rbp+arg_0]
0x180022800  test    rcx, rcx
0x180022803  jnz     short loc_18002281A
0x180022805  mov     [rbp+lpMem], rsi
0x180022809  jmp     short loc_18002283C
0x18002280b  test    eax, eax
0x18002280d  jns     loc_180022766
0x180022813  call    cs:__imp_abort
0x18002281a  mov     [rbp+var_38], rsi
0x18002281e  mov     rax, [rcx]
0x180022821  lea     r8, [rbp+var_38]
0x180022825  lea     rdx, ??$guid_v@UIDependencyObject@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::IDependencyObject>
0x18002282c  mov     rax, [rax]
0x18002282f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022834  mov     rax, [rbp+var_38]
0x180022838  mov     [rbp+lpMem], rax
0x18002283c  lea     rdx, [rbp+var_28]; struct winrt::param::hstring *
0x180022840  lea     rcx, [rbp+lpMem]; struct winrt::Windows::UI::Xaml::DependencyObject *
0x180022844  call    ?SetAutomationId@AutomationProperties@Automation@Xaml@UI@Windows@winrt@@SA@AEBUDependencyObject@3456@AEBUhstring@param@6@@Z; winrt::Windows::UI::Xaml::Automation::AutomationProperties::SetAutomationId(winrt::Windows::UI::Xaml::DependencyObject const &,winrt::param::hstring const &)
0x180022849  nop
0x18002284a  cmp     [rbp+lpMem], rsi
0x18002284e  jz      short loc_180022859
0x180022850  lea     rcx, [rbp+lpMem]
0x180022854  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180022859  lea     rdx, [rbp+var_30]
0x18002285d  lea     rcx, [rbp+arg_10]
0x180022861  call    ?Children@?$consume_Windows_UI_Xaml_Controls_IPanel@UGrid@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Xaml_Controls_IPanel<winrt::Windows::UI::Xaml::Controls::Grid>::Children(void)
0x180022866  mov     rdi, rax
0x180022869  mov     rcx, [rbp+arg_0]
0x18002286d  test    rcx, rcx
0x180022870  jnz     short loc_180022878
0x180022872  mov     [rbp+lpMem], rsi
0x180022876  jmp     short loc_18002289A
0x180022878  mov     [rbp+var_38], rsi
0x18002287c  mov     rax, [rcx]
0x18002287f  lea     r8, [rbp+var_38]
0x180022883  lea     rdx, ??$guid_v@UIUIElement@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::IUIElement>
0x18002288a  mov     rax, [rax]
0x18002288d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022892  mov     rax, [rbp+var_38]
0x180022896  mov     [rbp+lpMem], rax
0x18002289a  lea     rdx, [rbp+lpMem]
0x18002289e  mov     rcx, rdi
0x1800228a1  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@UColumnDefinition@Controls@Xaml@UI@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UColumnDefinition@Controls@Xaml@UI@45@@impl@winrt@@QEBA@AEBUColumnDefinition@Controls@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Xaml::Controls::ColumnDefinition>,winrt::Windows::UI::Xaml::Controls::ColumnDefinition>::Append(winrt::Windows::UI::Xaml::Controls::ColumnDefinition const &)
0x1800228a6  nop
0x1800228a7  cmp     [rbp+lpMem], rsi
0x1800228ab  jz      short loc_1800228B7
0x1800228ad  lea     rcx, [rbp+lpMem]
0x1800228b1  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x1800228b6  nop
0x1800228b7  cmp     [rbp+var_30], rsi
0x1800228bb  jz      short loc_1800228C6
0x1800228bd  lea     rcx, [rbp+var_30]
0x1800228c1  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x1800228c6  mov     rcx, [rbp+arg_10]
0x1800228ca  mov     rax, rsi
0x1800228cd  mov     [rbp+arg_10], rax
0x1800228d1  mov     [rbx], rcx
0x1800228d4  mov     byte ptr [rbx+8], 1
0x1800228d8  cmp     [rbp+arg_0], rsi
0x1800228dc  jz      short loc_1800228EB
0x1800228de  lea     rcx, [rbp+arg_0]
0x1800228e2  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x1800228e7  mov     rax, [rbp+arg_10]
0x1800228eb  test    rax, rax
0x1800228ee  jz      short loc_1800228F9
0x1800228f0  lea     rcx, [rbp+arg_10]
0x1800228f4  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x1800228f9  mov     rax, rbx
0x1800228fc  mov     rbx, [rsp+60h+arg_8]
0x180022904  add     rsp, 60h
0x180022908  pop     rdi
0x180022909  pop     rsi
0x18002290a  pop     rbp
0x18002290b  retn
0x18002290c  lea     rdx, [rbp+var_28]
0x180022910  mov     ecx, eax
0x180022912  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180022918  lea     rdx, [rbp+var_28]
0x18002291c  mov     ecx, eax
0x18002291e  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180022924  lea     rdx, [rbp+var_28]
0x180022928  mov     ecx, eax
0x18002292a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180022930  lea     rdx, [rbp+var_28]
0x180022934  mov     ecx, eax
0x180022936  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
