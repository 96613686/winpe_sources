# winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::ApplyActiveTheme(winrt::guid const &)

- ea: `0x1800210c4`
- end: `0x1800211bc`
- name: `?ApplyActiveTheme@FocusSessionThemeManager@implementation@Shell@Internal@Windows@winrt@@AEAAXAEBUguid@6@@Z`
- size: `248`
- prototype: `void(winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager *__hidden this, const struct winrt::guid *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800226ec`

## callees

- `0x180008f88`
- `0x18000dfc0`
- `0x180012b78`
- `0x18001ba10`
- `0x18001f9d4`
- `0x1800210c4`
- `0x1800215d0`
- `0x18002165c`
- `0x180021f24`
- `0x180022098`
- `0x18002220c`
- `0x180023638`
- `0x18002d0ec`
- `0x18002db04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800210e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800210e3`

## string_xrefs

- `0x180021137`: `TaskbarBadges`
- `0x180021153`: `TaskbarFlashing`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::ApplyActiveTheme(
        winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager *this,
        const struct winrt::guid *a2)
{
  char *v4; // rbx
  _QWORD *v5; // rax
  winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  bool v9; // dl
  winrt::Windows::Internal::Shell::implementation *v10; // rcx
  __int64 v11; // rcx
  _BYTE v12[16]; // [rsp+20h] [rbp-10h] BYREF
  int v13; // [rsp+50h] [rbp+20h] BYREF
  char v14; // [rsp+60h] [rbp+30h] BYREF
  char *v15; // [rsp+68h] [rbp+38h] BYREF

  v4 = (char *)this + 144;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  v15 = v4;
  v5 = (_QWORD *)winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::CurrentThemeId(this, v12);
  v6 = (winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager *)(*v5 - *(_QWORD *)a2);
  if ( *v5 == *(_QWORD *)a2 )
    v6 = (winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager *)(v5[1] - *((_QWORD *)a2 + 1));
  if ( v6 )
  {
    winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::SaveOffTheme(v6, a2);
    winrt::Windows::Internal::Shell::FocusSessionActiveTheme::FocusSessionActiveTheme(
      (winrt::Windows::Internal::Shell::FocusSessionActiveTheme *)&v14,
      a2);
    if ( (unsigned __int8)winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionActiveTheme>::IsHideTaskbarBadgesEnabled(&v14) )
      anonymous_namespace_::SetRegistryBoolValue(v7, L"TaskbarBadges", 0);
    if ( (unsigned __int8)winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionActiveTheme>::IsHideTaskbarFlashesEnabled(&v14) )
      anonymous_namespace_::SetRegistryBoolValue(v8, L"TaskbarFlashing", 0);
    if ( (unsigned __int8)winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionOffTheme>::IsMuteNotificationsEnabled(&v14) )
    {
      LOBYTE(v10) = 1;
      winrt::Windows::Internal::Shell::implementation::ApplyFocusQuietMoment(v10, v9);
    }
    winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::CurrentThemeId(this, a2);
    v13 = 0;
    wil::wnf_publish<int>(v11, &v13);
    LOBYTE(v13) = 1;
    winrt::Windows::Internal::Shell::implementation::FocusSessionTelemetry::IsFocusEnabled<bool>(&v13);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v14);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v15);
}

```

## disassembly

```asm
0x1800210c4  mov     [rsp-18h+arg_8], rbx
0x1800210c9  push    rbp
0x1800210ca  push    rsi
0x1800210cb  push    rdi
0x1800210cc  mov     rbp, rsp
0x1800210cf  sub     rsp, 30h
0x1800210d3  mov     rdi, rdx
0x1800210d6  mov     rsi, rcx
0x1800210d9  lea     rbx, [rcx+90h]
0x1800210e0  mov     rcx, rbx; lpCriticalSection
0x1800210e3  call    cs:__imp_EnterCriticalSection
0x1800210e9  mov     [rbp+arg_18], rbx
0x1800210ed  lea     rdx, [rbp+var_10]
0x1800210f1  mov     rcx, rsi
0x1800210f4  call    ?CurrentThemeId@FocusSessionThemeManager@implementation@Shell@Internal@Windows@winrt@@QEAA?AUguid@6@XZ; winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::CurrentThemeId(void)
0x1800210f9  mov     rcx, [rax]
0x1800210fc  sub     rcx, [rdi]
0x1800210ff  jnz     short loc_180021109
0x180021101  mov     rcx, [rax+8]
0x180021105  sub     rcx, [rdi+8]; this
0x180021109  test    rcx, rcx
0x18002110c  jz      loc_1800211A6
0x180021112  mov     rdx, rdi; struct winrt::guid *
0x180021115  call    ?SaveOffTheme@FocusSessionThemeManager@implementation@Shell@Internal@Windows@winrt@@AEAAXAEBUguid@6@@Z; winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::SaveOffTheme(winrt::guid const &)
0x18002111a  mov     rdx, rdi; struct winrt::guid *
0x18002111d  lea     rcx, [rbp+arg_10]; this
0x180021121  call    ??0FocusSessionActiveTheme@Shell@Internal@Windows@winrt@@QEAA@AEBUguid@4@@Z; winrt::Windows::Internal::Shell::FocusSessionActiveTheme::FocusSessionActiveTheme(winrt::guid const &)
0x180021126  nop
0x180021127  lea     rcx, [rbp+arg_10]
0x18002112b  call    ?IsHideTaskbarBadgesEnabled@?$consume_Windows_Internal_Shell_IFocusSessionTheme@UFocusSessionActiveTheme@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionActiveTheme>::IsHideTaskbarBadgesEnabled(void)
0x180021130  test    al, al
0x180021132  jz      short loc_180021143
0x180021134  xor     r8d, r8d
0x180021137  lea     rdx, aTaskbarbadges; "TaskbarBadges"
0x18002113e  call    _anonymous_namespace___SetRegistryBoolValue
0x180021143  lea     rcx, [rbp+arg_10]
0x180021147  call    ?IsHideTaskbarFlashesEnabled@?$consume_Windows_Internal_Shell_IFocusSessionTheme@UFocusSessionActiveTheme@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionActiveTheme>::IsHideTaskbarFlashesEnabled(void)
0x18002114c  test    al, al
0x18002114e  jz      short loc_18002115F
0x180021150  xor     r8d, r8d
0x180021153  lea     rdx, aTaskbarflashin; "TaskbarFlashing"
0x18002115a  call    _anonymous_namespace___SetRegistryBoolValue
0x18002115f  lea     rcx, [rbp+arg_10]
0x180021163  call    ?IsMuteNotificationsEnabled@?$consume_Windows_Internal_Shell_IFocusSessionTheme@UFocusSessionOffTheme@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionOffTheme>::IsMuteNotificationsEnabled(void)
0x180021168  test    al, al
0x18002116a  jz      short loc_180021173
0x18002116c  mov     cl, 1; this
0x18002116e  call    ?ApplyFocusQuietMoment@implementation@Shell@Internal@Windows@winrt@@YAX_N@Z; winrt::Windows::Internal::Shell::implementation::ApplyFocusQuietMoment(bool)
0x180021173  mov     rdx, rdi; struct winrt::guid *
0x180021176  mov     rcx, rsi; this
0x180021179  call    ?CurrentThemeId@FocusSessionThemeManager@implementation@Shell@Internal@Windows@winrt@@AEAAXAEBUguid@6@@Z; winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::CurrentThemeId(winrt::guid const &)
0x18002117e  mov     [rbp+arg_0], 0
0x180021185  lea     rdx, [rbp+arg_0]
0x180021189  call    ??$wnf_publish@H@wil@@YAXAEBU_WNF_STATE_NAME@@AEBH@Z; wil::wnf_publish<int>(_WNF_STATE_NAME const &,int const &)
0x18002118e  mov     byte ptr [rbp+arg_0], 1
0x180021192  lea     rcx, [rbp+arg_0]
0x180021196  call    ??$IsFocusEnabled@_N@FocusSessionTelemetry@implementation@Shell@Internal@Windows@winrt@@SAX$$QEA_N@Z; winrt::Windows::Internal::Shell::implementation::FocusSessionTelemetry::IsFocusEnabled<bool>(bool &&)
0x18002119b  nop
0x18002119c  lea     rcx, [rbp+arg_10]
0x1800211a0  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1800211a5  nop
0x1800211a6  lea     rcx, [rbp+arg_18]
0x1800211aa  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800211af  mov     rbx, [rsp+30h+arg_8]
0x1800211b4  add     rsp, 30h
0x1800211b8  pop     rdi
0x1800211b9  pop     rsi
0x1800211ba  pop     rbp
0x1800211bb  retn
```
