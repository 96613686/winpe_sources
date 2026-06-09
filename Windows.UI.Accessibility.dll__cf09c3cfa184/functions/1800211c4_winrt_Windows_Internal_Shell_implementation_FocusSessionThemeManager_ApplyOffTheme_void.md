# winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::ApplyOffTheme(void)

- ea: `0x1800211c4`
- end: `0x180021306`
- name: `?ApplyOffTheme@FocusSessionThemeManager@implementation@Shell@Internal@Windows@winrt@@AEAAXXZ`
- size: `322`
- prototype: `void __fastcall(winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager *__hidden this)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800226ec`
- `0x1800227ac`

## callees

- `0x180008f88`
- `0x18000dfc0`
- `0x180018ea0`
- `0x18001ba10`
- `0x18001f9d4`
- `0x1800211c4`
- `0x1800215d0`
- `0x18002165c`
- `0x180021f24`
- `0x180022098`
- `0x18002220c`
- `0x180022380`
- `0x180022968`
- `0x1800229f8`
- `0x180023898`
- `0x18002d0ec`
- `0x18002db04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800211e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800211e8`

## string_xrefs

- `0x18002124f`: `TaskbarBadges`
- `0x180021274`: `TaskbarFlashing`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::ApplyOffTheme(
        winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager *this)
{
  char *v2; // rbx
  _QWORD *v3; // rax
  __int64 v4; // rdx
  unsigned __int8 v5; // al
  __int64 v6; // rcx
  unsigned __int8 v7; // al
  __int64 v8; // rcx
  bool v9; // dl
  __int64 v10; // rcx
  __int64 v11; // rcx
  _BYTE v12[8]; // [rsp+20h] [rbp-40h] BYREF
  _BYTE v13[8]; // [rsp+28h] [rbp-38h] BYREF
  int v14; // [rsp+30h] [rbp-30h] BYREF
  char *v15; // [rsp+38h] [rbp-28h] BYREF
  __int128 v16; // [rsp+40h] [rbp-20h] BYREF

  v2 = (char *)this + 144;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  v15 = v2;
  v3 = (_QWORD *)winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::CurrentThemeId(this, &v16);
  v4 = *v3 - 0x49D4C056081F9981LL;
  if ( *v3 == 0x49D4C056081F9981LL )
    v4 = v3[1] - _mm_srli_si128((__m128i)xmmword_18003A1A8, 8).m128i_u64[0];
  if ( v4 )
  {
    winrt::make<winrt::Windows::Internal::Shell::implementation::FocusSessionOffTheme,>(v13);
    if ( (unsigned __int8)winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionActiveTheme>::IsHideTaskbarBadgesEnabled(v13) )
    {
      v5 = winrt::impl::consume_Windows_Internal_Shell_IFocusSessionOffTheme<winrt::Windows::Internal::Shell::IFocusSessionOffTheme>::PreviousTaskbarBadgesEnabled(v13);
      anonymous_namespace_::SetRegistryBoolValue(v6, L"TaskbarBadges", v5);
    }
    if ( (unsigned __int8)winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionActiveTheme>::IsHideTaskbarFlashesEnabled(v13) )
    {
      v7 = winrt::impl::consume_Windows_Internal_Shell_IFocusSessionOffTheme<winrt::Windows::Internal::Shell::IFocusSessionOffTheme>::PreviousTaskbarFlashesEnabled(v13);
      anonymous_namespace_::SetRegistryBoolValue(v8, L"TaskbarFlashing", v7);
    }
    if ( (unsigned __int8)winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionOffTheme>::IsMuteNotificationsEnabled(v13) )
      winrt::Windows::Internal::Shell::implementation::ApplyFocusQuietMoment(0, v9);
    if ( (unsigned __int8)winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionActiveTheme>::IsStartFocusTimerEnabled(v13) )
      anonymous_namespace_::StopClockAppFocusSession(v10);
    v16 = xmmword_18003A1A8;
    winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::CurrentThemeId(
      this,
      (const struct winrt::guid *)&v16);
    v14 = 0;
    wil::wnf_publish<int>(v11, &v14);
    v12[0] = 0;
    winrt::Windows::Internal::Shell::implementation::FocusSessionTelemetry::IsFocusEnabled<bool>(v12);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v13);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v15);
}

```

## disassembly

```asm
0x1800211c4  mov     [rsp-8+arg_8], rbx
0x1800211c9  mov     [rsp-8+arg_10], rdi
0x1800211ce  push    rbp
0x1800211cf  mov     rbp, rsp
0x1800211d2  sub     rsp, 60h
0x1800211d6  movaps  [rsp+60h+var_10], xmm6
0x1800211db  mov     rdi, rcx
0x1800211de  lea     rbx, [rcx+90h]
0x1800211e5  mov     rcx, rbx; lpCriticalSection
0x1800211e8  call    cs:__imp_EnterCriticalSection
0x1800211ee  mov     [rbp+var_28], rbx
0x1800211f2  movups  xmm6, cs:xmmword_18003A1A8
0x1800211f9  lea     rdx, [rbp+var_20]
0x1800211fd  mov     rcx, rdi
0x180021200  call    ?CurrentThemeId@FocusSessionThemeManager@implementation@Shell@Internal@Windows@winrt@@QEAA?AUguid@6@XZ; winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::CurrentThemeId(void)
0x180021205  mov     rdx, [rax]
0x180021208  movq    rcx, xmm6
0x18002120d  sub     rdx, rcx
0x180021210  jnz     short loc_180021223
0x180021212  mov     rdx, [rax+8]
0x180021216  psrldq  xmm6, 8
0x18002121b  movq    rax, xmm6
0x180021220  sub     rdx, rax
0x180021223  test    rdx, rdx
0x180021226  jz      loc_1800212E6
0x18002122c  lea     rcx, [rbp+var_38]
0x180021230  call    ??$make@UFocusSessionOffTheme@implementation@Shell@Internal@Windows@winrt@@$$V@winrt@@YA?A_PXZ
0x180021235  nop
0x180021236  lea     rcx, [rbp+var_38]
0x18002123a  call    ?IsHideTaskbarBadgesEnabled@?$consume_Windows_Internal_Shell_IFocusSessionTheme@UFocusSessionActiveTheme@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionActiveTheme>::IsHideTaskbarBadgesEnabled(void)
0x18002123f  test    al, al
0x180021241  jz      short loc_18002125B
0x180021243  lea     rcx, [rbp+var_38]
0x180021247  call    ?PreviousTaskbarBadgesEnabled@?$consume_Windows_Internal_Shell_IFocusSessionOffTheme@UIFocusSessionOffTheme@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_IFocusSessionOffTheme<winrt::Windows::Internal::Shell::IFocusSessionOffTheme>::PreviousTaskbarBadgesEnabled(void)
0x18002124c  mov     r8b, al
0x18002124f  lea     rdx, aTaskbarbadges; "TaskbarBadges"
0x180021256  call    _anonymous_namespace___SetRegistryBoolValue
0x18002125b  lea     rcx, [rbp+var_38]
0x18002125f  call    ?IsHideTaskbarFlashesEnabled@?$consume_Windows_Internal_Shell_IFocusSessionTheme@UFocusSessionActiveTheme@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionActiveTheme>::IsHideTaskbarFlashesEnabled(void)
0x180021264  test    al, al
0x180021266  jz      short loc_180021280
0x180021268  lea     rcx, [rbp+var_38]
0x18002126c  call    ?PreviousTaskbarFlashesEnabled@?$consume_Windows_Internal_Shell_IFocusSessionOffTheme@UIFocusSessionOffTheme@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_IFocusSessionOffTheme<winrt::Windows::Internal::Shell::IFocusSessionOffTheme>::PreviousTaskbarFlashesEnabled(void)
0x180021271  mov     r8b, al
0x180021274  lea     rdx, aTaskbarflashin; "TaskbarFlashing"
0x18002127b  call    _anonymous_namespace___SetRegistryBoolValue
0x180021280  lea     rcx, [rbp+var_38]
0x180021284  call    ?IsMuteNotificationsEnabled@?$consume_Windows_Internal_Shell_IFocusSessionTheme@UFocusSessionOffTheme@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionOffTheme>::IsMuteNotificationsEnabled(void)
0x180021289  test    al, al
0x18002128b  jz      short loc_180021294
0x18002128d  xor     ecx, ecx; this
0x18002128f  call    ?ApplyFocusQuietMoment@implementation@Shell@Internal@Windows@winrt@@YAX_N@Z; winrt::Windows::Internal::Shell::implementation::ApplyFocusQuietMoment(bool)
0x180021294  lea     rcx, [rbp+var_38]
0x180021298  call    ?IsStartFocusTimerEnabled@?$consume_Windows_Internal_Shell_IFocusSessionTheme@UFocusSessionActiveTheme@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionActiveTheme>::IsStartFocusTimerEnabled(void)
0x18002129d  test    al, al
0x18002129f  jz      short loc_1800212A6
0x1800212a1  call    _anonymous_namespace___StopClockAppFocusSession
0x1800212a6  movups  xmm0, cs:xmmword_18003A1A8
0x1800212ad  movdqu  [rbp+var_20], xmm0
0x1800212b2  lea     rdx, [rbp+var_20]; struct winrt::guid *
0x1800212b6  mov     rcx, rdi; this
0x1800212b9  call    ?CurrentThemeId@FocusSessionThemeManager@implementation@Shell@Internal@Windows@winrt@@AEAAXAEBUguid@6@@Z; winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::CurrentThemeId(winrt::guid const &)
0x1800212be  mov     [rbp+var_30], 0
0x1800212c5  lea     rdx, [rbp+var_30]
0x1800212c9  call    ??$wnf_publish@H@wil@@YAXAEBU_WNF_STATE_NAME@@AEBH@Z; wil::wnf_publish<int>(_WNF_STATE_NAME const &,int const &)
0x1800212ce  mov     [rbp+var_40], 0
0x1800212d2  lea     rcx, [rbp+var_40]
0x1800212d6  call    ??$IsFocusEnabled@_N@FocusSessionTelemetry@implementation@Shell@Internal@Windows@winrt@@SAX$$QEA_N@Z; winrt::Windows::Internal::Shell::implementation::FocusSessionTelemetry::IsFocusEnabled<bool>(bool &&)
0x1800212db  nop
0x1800212dc  lea     rcx, [rbp+var_38]
0x1800212e0  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1800212e5  nop
0x1800212e6  lea     rcx, [rbp+var_28]
0x1800212ea  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800212ef  lea     r11, [rsp+60h+var_s0]
0x1800212f4  mov     rbx, [r11+18h]
0x1800212f8  mov     rdi, [r11+20h]
0x1800212fc  movaps  xmm6, [rsp+60h+var_10]
0x180021301  mov     rsp, r11
0x180021304  pop     rbp
0x180021305  retn
```
