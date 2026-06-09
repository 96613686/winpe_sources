# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::OnVisiblityToggled(void)

- ea: `0x18001fac4`
- end: `0x18001fd59`
- name: `?OnVisiblityToggled@FirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAXXZ`
- size: `661`
- prototype: `void __fastcall(winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18001ec20`

## callees

- `0x180002d55`
- `0x180002d91`
- `0x180007940`
- `0x18000b24c`
- `0x18000b5d0`
- `0x180010430`
- `0x180013818`
- `0x18001ad24`
- `0x18001dc3c`
- `0x18001f898`
- `0x18001fac4`
- `0x18002098c`
- `0x18002d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001fbfe`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001fd1d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001fbfe`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001fd1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fcfa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fcfa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fb27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fb27`

## string_xrefs

- `0x18001fd3b`: `shellcommon\shell\networkux\firewallux\lib\Utils.h`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::OnVisiblityToggled(
        winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog *this)
{
  int v2; // eax
  struct _RTL_CRITICAL_SECTION *v3; // r15
  _BYTE *v4; // r14
  __int64 v5; // rsi
  __int64 i; // rdi
  __int64 (__fastcall ***v7)(_QWORD, void *, __int64 *); // rcx
  __int64 v8; // rbx
  int v9; // eax
  void *v10; // rdi
  int v11; // eax
  __int64 v12; // rsi
  __int64 j; // rdi
  __int64 (__fastcall ***v14)(_QWORD, void *, __int64 *); // rcx
  int v15; // eax
  int v16; // eax
  HANDLE ProcessHeap; // rax
  struct winrt::impl::shared_hstring_header *v18; // [rsp+20h] [rbp-20h] BYREF
  __int128 v19; // [rsp+28h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  __int64 v21; // [rsp+80h] [rbp+40h] BYREF
  LPVOID lpMem; // [rsp+88h] [rbp+48h] BYREF
  __int64 v23; // [rsp+90h] [rbp+50h] BYREF

  if ( !_InterlockedCompareExchange8((volatile signed __int8 *)this + 596, 1, 0) )
  {
    if ( *((_DWORD *)this + 20) )
    {
      if ( *((_DWORD *)this + 20) != 1 )
        wil::details::in1diag3::FailFast_UnexpectedMsg(
          retaddr,
          (void *)0x3B,
          (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\Utils.h",
          "Unexpected dialog type",
          (const char *)v18);
      v2 = 1;
    }
    else
    {
      v2 = 0;
    }
    LODWORD(v21) = 16;
    HIDWORD(v21) = v2;
    NetworkingTriageScenario::FirewallUX::NotificationDialogShowMoreExpanded((const struct NetworkingTriageScenario::FirewallUX::RequiredFields *)&v21);
  }
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 552);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 552));
  v4 = (char *)this + 595;
  if ( *((_BYTE *)this + 595) )
  {
    *v4 = 0;
    v5 = *((_QWORD *)this + 8);
    for ( i = *((_QWORD *)this + 7); i != v5; i += 8 )
    {
      LODWORD(v21) = 0;
      winrt::impl::consume_Windows_UI_Xaml_IUIElement<winrt::Windows::UI::Xaml::IUIElement>::Visibility(i, &v21);
    }
    v7 = *(__int64 (__fastcall ****)(_QWORD, void *, __int64 *))winrt::impl::consume_Windows_UI_Xaml_Controls_IContentControl<winrt::Windows::UI::Xaml::Controls::Button>::Content(
                                                                  (char *)this + 456,
                                                                  &v23);
    v21 = 0;
    if ( v7 )
    {
      LODWORD(v18) = 0;
      v19 = 0;
      v9 = (**v7)(v7, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::ITextBlock>, &v21);
      if ( v9 < 0 )
        winrt::throw_hresult((unsigned int)v9, &v18);
      v8 = v21;
    }
    else
    {
      v8 = 0;
    }
    v18 = *GetResourceString((struct winrt::impl::shared_hstring_header **)&lpMem, 0xB5u);
    winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::Text(
      &v21,
      &v18);
    v10 = lpMem;
    if ( lpMem )
    {
      v11 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v11 )
      {
        if ( v11 < 0 )
          abort();
        goto LABEL_29;
      }
LABEL_28:
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v10);
LABEL_29:
      lpMem = 0;
    }
  }
  else
  {
    *v4 = 1;
    v12 = *((_QWORD *)this + 8);
    for ( j = *((_QWORD *)this + 7); j != v12; j += 8 )
    {
      LODWORD(v21) = 1;
      winrt::impl::consume_Windows_UI_Xaml_IUIElement<winrt::Windows::UI::Xaml::IUIElement>::Visibility(j, &v21);
    }
    v14 = *(__int64 (__fastcall ****)(_QWORD, void *, __int64 *))winrt::impl::consume_Windows_UI_Xaml_Controls_IContentControl<winrt::Windows::UI::Xaml::Controls::Button>::Content(
                                                                   (char *)this + 456,
                                                                   &v23);
    v21 = 0;
    if ( v14 )
    {
      LODWORD(v18) = 0;
      v19 = 0;
      v15 = (**v14)(v14, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::ITextBlock>, &v21);
      if ( v15 < 0 )
        winrt::throw_hresult((unsigned int)v15, &v18);
      v8 = v21;
    }
    else
    {
      v8 = 0;
    }
    v18 = *GetResourceString((struct winrt::impl::shared_hstring_header **)&lpMem, 0xB4u);
    winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::Text(
      &v21,
      &v18);
    v10 = lpMem;
    if ( lpMem )
    {
      v16 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v16 )
      {
        if ( v16 < 0 )
          abort();
        goto LABEL_29;
      }
      goto LABEL_28;
    }
  }
  if ( v8 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v21);
  if ( v23 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v23);
  FirewallUxTelemetry::ExpandButtonClicked<bool &>(v4);
  if ( v3 )
    LeaveCriticalSection(v3);
}

```

## disassembly

```asm
0x18001fac4  mov     [rsp-38h+arg_18], rbx
0x18001fac9  push    rbp
0x18001faca  push    rsi
0x18001facb  push    rdi
0x18001facc  push    r12
0x18001face  push    r13
0x18001fad0  push    r14
0x18001fad2  push    r15
0x18001fad4  mov     rbp, rsp
0x18001fad7  sub     rsp, 40h
0x18001fadb  mov     rbx, rcx
0x18001fade  xor     eax, eax
0x18001fae0  lea     r13d, [rax+1]
0x18001fae4  xor     r12d, r12d
0x18001fae7  lock cmpxchg [rcx+254h], r13b
0x18001faf0  jnz     short loc_18001FB1D
0x18001faf2  cmp     [rcx+50h], r12d
0x18001faf6  jnz     short loc_18001FAFD
0x18001faf8  mov     eax, r12d
0x18001fafb  jmp     short loc_18001FB0A
0x18001fafd  cmp     [rcx+50h], r13d
0x18001fb01  jnz     loc_18001FD30
0x18001fb07  mov     eax, r13d
0x18001fb0a  mov     dword ptr [rbp+arg_0], 10h
0x18001fb11  mov     dword ptr [rbp+arg_0+4], eax
0x18001fb14  lea     rcx, [rbp+arg_0]; struct NetworkingTriageScenario::FirewallUX::RequiredFields *
0x18001fb18  call    ?NotificationDialogShowMoreExpanded@FirewallUX@NetworkingTriageScenario@@SAXAEBURequiredFields@12@@Z; NetworkingTriageScenario::FirewallUX::NotificationDialogShowMoreExpanded(NetworkingTriageScenario::FirewallUX::RequiredFields const &)
0x18001fb1d  lea     r15, [rbx+228h]
0x18001fb24  mov     rcx, r15; lpCriticalSection
0x18001fb27  call    cs:__imp_EnterCriticalSection
0x18001fb2d  lea     r14, [rbx+253h]
0x18001fb34  cmp     [r14], r12b
0x18001fb37  jz      loc_18001FC05
0x18001fb3d  mov     [r14], r12b
0x18001fb40  mov     rsi, [rbx+40h]
0x18001fb44  mov     rdi, [rbx+38h]
0x18001fb48  jmp     short loc_18001FB5E
0x18001fb4a  mov     dword ptr [rbp+arg_0], r12d
0x18001fb4e  lea     rdx, [rbp+arg_0]
0x18001fb52  mov     rcx, rdi
0x18001fb55  call    ?Visibility@?$consume_Windows_UI_Xaml_IUIElement@UIUIElement@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBW40Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IUIElement<winrt::Windows::UI::Xaml::IUIElement>::Visibility(winrt::Windows::UI::Xaml::Visibility const &)
0x18001fb5a  add     rdi, 8
0x18001fb5e  cmp     rdi, rsi
0x18001fb61  jnz     short loc_18001FB4A
0x18001fb63  lea     rcx, [rbx+1C8h]
0x18001fb6a  lea     rdx, [rbp+arg_10]
0x18001fb6e  call    ?Content@?$consume_Windows_UI_Xaml_Controls_IContentControl@UButton@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Xaml_Controls_IContentControl<winrt::Windows::UI::Xaml::Controls::Button>::Content(void)
0x18001fb73  mov     rcx, [rax]
0x18001fb76  mov     [rbp+arg_0], r12
0x18001fb7a  test    rcx, rcx
0x18001fb7d  jnz     short loc_18001FB84
0x18001fb7f  mov     rbx, r12
0x18001fb82  jmp     short loc_18001FBB6
0x18001fb84  mov     dword ptr [rbp+var_20], r12d
0x18001fb88  xorps   xmm0, xmm0
0x18001fb8b  movdqu  [rbp+var_18], xmm0
0x18001fb90  mov     rax, [rcx]
0x18001fb93  lea     r8, [rbp+arg_0]
0x18001fb97  lea     rdx, ??$guid_v@UITextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::ITextBlock>
0x18001fb9e  mov     rax, [rax]
0x18001fba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fba6  test    eax, eax
0x18001fba8  js      loc_18001FD4D
0x18001fbae  mov     rbx, [rbp+arg_0]
0x18001fbb2  mov     [rbp+arg_0], rbx
0x18001fbb6  mov     edx, 0B5h
0x18001fbbb  lea     rcx, [rbp+lpMem]
0x18001fbbf  call    ?GetResourceString@@YA?AUhstring@winrt@@I@Z; GetResourceString(uint)
0x18001fbc4  mov     rcx, [rax]
0x18001fbc7  mov     [rbp+var_20], rcx
0x18001fbcb  lea     rdx, [rbp+var_20]
0x18001fbcf  lea     rcx, [rbp+arg_0]
0x18001fbd3  call    ?Text@?$consume_Windows_UI_Xaml_Controls_ITextBlock@UITextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::Text(winrt::param::hstring const &)
0x18001fbd8  mov     rdi, [rbp+lpMem]
0x18001fbdc  test    rdi, rdi
0x18001fbdf  jz      loc_18001FCCD
0x18001fbe5  or      eax, 0FFFFFFFFh
0x18001fbe8  lock xadd [rdi+18h], eax
0x18001fbed  sub     eax, r13d
0x18001fbf0  jz      loc_18001FCB6
0x18001fbf6  test    eax, eax
0x18001fbf8  jns     loc_18001FCC9
0x18001fbfe  call    cs:__imp_abort
0x18001fc05  mov     [r14], r13b
0x18001fc08  mov     rsi, [rbx+40h]
0x18001fc0c  mov     rdi, [rbx+38h]
0x18001fc10  jmp     short loc_18001FC26
0x18001fc12  mov     dword ptr [rbp+arg_0], r13d
0x18001fc16  lea     rdx, [rbp+arg_0]
0x18001fc1a  mov     rcx, rdi
0x18001fc1d  call    ?Visibility@?$consume_Windows_UI_Xaml_IUIElement@UIUIElement@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBW40Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IUIElement<winrt::Windows::UI::Xaml::IUIElement>::Visibility(winrt::Windows::UI::Xaml::Visibility const &)
0x18001fc22  add     rdi, 8
0x18001fc26  cmp     rdi, rsi
0x18001fc29  jnz     short loc_18001FC12
0x18001fc2b  lea     rcx, [rbx+1C8h]
0x18001fc32  lea     rdx, [rbp+arg_10]
0x18001fc36  call    ?Content@?$consume_Windows_UI_Xaml_Controls_IContentControl@UButton@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Xaml_Controls_IContentControl<winrt::Windows::UI::Xaml::Controls::Button>::Content(void)
0x18001fc3b  mov     rcx, [rax]
0x18001fc3e  mov     [rbp+arg_0], r12
0x18001fc42  test    rcx, rcx
0x18001fc45  jnz     short loc_18001FC4C
0x18001fc47  mov     rbx, r12
0x18001fc4a  jmp     short loc_18001FC7E
0x18001fc4c  mov     dword ptr [rbp+var_20], r12d
0x18001fc50  xorps   xmm0, xmm0
0x18001fc53  movdqu  [rbp+var_18], xmm0
0x18001fc58  mov     rax, [rcx]
0x18001fc5b  lea     r8, [rbp+arg_0]
0x18001fc5f  lea     rdx, ??$guid_v@UITextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::ITextBlock>
0x18001fc66  mov     rax, [rax]
0x18001fc69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc6e  test    eax, eax
0x18001fc70  js      loc_18001FD24
0x18001fc76  mov     rbx, [rbp+arg_0]
0x18001fc7a  mov     [rbp+arg_0], rbx
0x18001fc7e  mov     edx, 0B4h
0x18001fc83  lea     rcx, [rbp+lpMem]
0x18001fc87  call    ?GetResourceString@@YA?AUhstring@winrt@@I@Z; GetResourceString(uint)
0x18001fc8c  mov     rcx, [rax]
0x18001fc8f  mov     [rbp+var_20], rcx
0x18001fc93  lea     rdx, [rbp+var_20]
0x18001fc97  lea     rcx, [rbp+arg_0]
0x18001fc9b  call    ?Text@?$consume_Windows_UI_Xaml_Controls_ITextBlock@UITextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::Text(winrt::param::hstring const &)
0x18001fca0  mov     rdi, [rbp+lpMem]
0x18001fca4  test    rdi, rdi
0x18001fca7  jz      short loc_18001FCCD
0x18001fca9  or      eax, 0FFFFFFFFh
0x18001fcac  lock xadd [rdi+18h], eax
0x18001fcb1  sub     eax, r13d
0x18001fcb4  jnz     short loc_18001FD19
0x18001fcb6  nop
0x18001fcb7  call    WINRT_IMPL_GetProcessHeap
0x18001fcbc  mov     rcx, rax; hHeap
0x18001fcbf  mov     r8, rdi; lpMem
0x18001fcc2  xor     edx, edx; dwFlags
0x18001fcc4  call    WINRT_IMPL_HeapFree
0x18001fcc9  mov     [rbp+lpMem], r12
0x18001fccd  test    rbx, rbx
0x18001fcd0  jz      short loc_18001FCDB
0x18001fcd2  lea     rcx, [rbp+arg_0]
0x18001fcd6  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001fcdb  cmp     [rbp+arg_10], r12
0x18001fcdf  jz      short loc_18001FCEA
0x18001fce1  lea     rcx, [rbp+arg_10]
0x18001fce5  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001fcea  mov     rcx, r14
0x18001fced  call    ??$ExpandButtonClicked@AEA_N@FirewallUxTelemetry@@SAXAEA_N@Z; FirewallUxTelemetry::ExpandButtonClicked<bool &>(bool &)
0x18001fcf2  test    r15, r15
0x18001fcf5  jz      short loc_18001FD01
0x18001fcf7  mov     rcx, r15; lpCriticalSection
0x18001fcfa  call    cs:__imp_LeaveCriticalSection
0x18001fd00  nop
0x18001fd01  mov     rbx, [rsp+40h+arg_18]
0x18001fd09  add     rsp, 40h
0x18001fd0d  pop     r15
0x18001fd0f  pop     r14
0x18001fd11  pop     r13
0x18001fd13  pop     r12
0x18001fd15  pop     rdi
0x18001fd16  pop     rsi
0x18001fd17  pop     rbp
0x18001fd18  retn
0x18001fd19  test    eax, eax
0x18001fd1b  jns     short loc_18001FCC9
0x18001fd1d  call    cs:__imp_abort
0x18001fd24  lea     rdx, [rbp+var_20]
0x18001fd28  mov     ecx, eax
0x18001fd2a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001fd30  mov     rcx, [rbp+38h]; this
0x18001fd34  lea     r9, aUnexpectedDial; "Unexpected dialog type"
0x18001fd3b  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\networkux\\firewall"...
0x18001fd42  mov     edx, 3Bh ; ';'; void *
0x18001fd47  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
0x18001fd4d  lea     rdx, [rbp+var_20]
0x18001fd51  mov     ecx, eax
0x18001fd53  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
