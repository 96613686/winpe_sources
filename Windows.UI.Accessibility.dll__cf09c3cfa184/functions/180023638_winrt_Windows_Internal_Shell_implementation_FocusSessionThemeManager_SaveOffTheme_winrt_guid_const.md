# winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::SaveOffTheme(winrt::guid const &)

- ea: `0x180023638`
- end: `0x18002371b`
- name: `?SaveOffTheme@FocusSessionThemeManager@implementation@Shell@Internal@Windows@winrt@@AEAAXAEBUguid@6@@Z`
- size: `227`
- prototype: `void(winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager *__hidden this, const struct winrt::guid *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800210c4`

## callees

- `0x18000dfc0`
- `0x180012b78`
- `0x180018ea0`
- `0x180021f24`
- `0x180021fdc`
- `0x180022098`
- `0x180022150`
- `0x18002220c`
- `0x1800222c4`
- `0x180022380`
- `0x180022438`
- `0x1800229b8`
- `0x180022a48`
- `0x180023638`
- `0x18002d83c`

## string_xrefs

- `0x180023699`: `TaskbarBadges`
- `0x1800236d1`: `TaskbarFlashing`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::SaveOffTheme(
        winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager *this,
        const struct winrt::guid *a2)
{
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 v5; // rcx
  char v6; // r8
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rcx
  char v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rdx
  winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager *v13; // [rsp+30h] [rbp+10h] BYREF
  char v14; // [rsp+40h] [rbp+20h] BYREF

  v13 = this;
  winrt::make<winrt::Windows::Internal::Shell::implementation::FocusSessionOffTheme,>(&v14);
  winrt::Windows::Internal::Shell::FocusSessionActiveTheme::FocusSessionActiveTheme(
    (winrt::Windows::Internal::Shell::FocusSessionActiveTheme *)&v13,
    a2);
  LOBYTE(v3) = winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionActiveTheme>::IsStartFocusTimerEnabled(&v13);
  winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionOffTheme>::IsStartFocusTimerEnabled(
    &v14,
    v3);
  LOBYTE(v4) = winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionActiveTheme>::IsHideTaskbarBadgesEnabled(&v13);
  winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionOffTheme>::IsHideTaskbarBadgesEnabled(
    &v14,
    v4);
  if ( (unsigned __int8)winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionActiveTheme>::IsHideTaskbarBadgesEnabled(&v13) )
  {
    LOBYTE(v7) = anonymous_namespace_::GetRegistryBoolValue(v5, L"TaskbarBadges", v6);
    winrt::impl::consume_Windows_Internal_Shell_IFocusSessionOffTheme<winrt::Windows::Internal::Shell::IFocusSessionOffTheme>::PreviousTaskbarBadgesEnabled(
      &v14,
      v7);
  }
  LOBYTE(v8) = winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionActiveTheme>::IsHideTaskbarFlashesEnabled(&v13);
  winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionOffTheme>::IsHideTaskbarFlashesEnabled(
    &v14,
    v8);
  if ( (unsigned __int8)winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionActiveTheme>::IsHideTaskbarFlashesEnabled(&v13) )
  {
    LOBYTE(v11) = anonymous_namespace_::GetRegistryBoolValue(v9, L"TaskbarFlashing", v10);
    winrt::impl::consume_Windows_Internal_UI_Notifications_IQuietHoursSettingsInterop<winrt::Windows::Internal::UI::Notifications::IQuietHoursSettingsInterop>::FocusQuietMomentApplicable(
      &v14,
      v11);
  }
  LOBYTE(v12) = winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionOffTheme>::IsMuteNotificationsEnabled(&v13);
  winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionOffTheme>::IsMuteNotificationsEnabled(
    &v14,
    v12);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v13);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v14);
}

```

## disassembly

```asm
0x180023638  mov     [rsp-8+arg_8], rbx
0x18002363d  mov     [rsp-8+arg_0], rcx
0x180023642  push    rbp
0x180023643  mov     rbp, rsp
0x180023646  sub     rsp, 20h
0x18002364a  mov     rbx, rdx
0x18002364d  lea     rcx, [rbp+arg_10]
0x180023651  call    ??$make@UFocusSessionOffTheme@implementation@Shell@Internal@Windows@winrt@@$$V@winrt@@YA?A_PXZ
0x180023656  nop
0x180023657  mov     rdx, rbx; struct winrt::guid *
0x18002365a  lea     rcx, [rbp+arg_0]; this
0x18002365e  call    ??0FocusSessionActiveTheme@Shell@Internal@Windows@winrt@@QEAA@AEBUguid@4@@Z; winrt::Windows::Internal::Shell::FocusSessionActiveTheme::FocusSessionActiveTheme(winrt::guid const &)
0x180023663  nop
0x180023664  lea     rcx, [rbp+arg_0]
0x180023668  call    ?IsStartFocusTimerEnabled@?$consume_Windows_Internal_Shell_IFocusSessionTheme@UFocusSessionActiveTheme@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionActiveTheme>::IsStartFocusTimerEnabled(void)
0x18002366d  mov     dl, al
0x18002366f  lea     rcx, [rbp+arg_10]
0x180023673  call    ?IsStartFocusTimerEnabled@?$consume_Windows_Internal_Shell_IFocusSessionTheme@UFocusSessionOffTheme@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@_N@Z; winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionOffTheme>::IsStartFocusTimerEnabled(bool)
0x180023678  lea     rcx, [rbp+arg_0]
0x18002367c  call    ?IsHideTaskbarBadgesEnabled@?$consume_Windows_Internal_Shell_IFocusSessionTheme@UFocusSessionActiveTheme@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionActiveTheme>::IsHideTaskbarBadgesEnabled(void)
0x180023681  mov     dl, al
0x180023683  lea     rcx, [rbp+arg_10]
0x180023687  call    ?IsHideTaskbarBadgesEnabled@?$consume_Windows_Internal_Shell_IFocusSessionTheme@UFocusSessionOffTheme@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@_N@Z; winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionOffTheme>::IsHideTaskbarBadgesEnabled(bool)
0x18002368c  lea     rcx, [rbp+arg_0]
0x180023690  call    ?IsHideTaskbarBadgesEnabled@?$consume_Windows_Internal_Shell_IFocusSessionTheme@UFocusSessionActiveTheme@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionActiveTheme>::IsHideTaskbarBadgesEnabled(void)
0x180023695  test    al, al
0x180023697  jz      short loc_1800236B0
0x180023699  lea     rdx, aTaskbarbadges; "TaskbarBadges"
0x1800236a0  call    _anonymous_namespace___GetRegistryBoolValue
0x1800236a5  mov     dl, al
0x1800236a7  lea     rcx, [rbp+arg_10]
0x1800236ab  call    ?PreviousTaskbarBadgesEnabled@?$consume_Windows_Internal_Shell_IFocusSessionOffTheme@UIFocusSessionOffTheme@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@_N@Z; winrt::impl::consume_Windows_Internal_Shell_IFocusSessionOffTheme<winrt::Windows::Internal::Shell::IFocusSessionOffTheme>::PreviousTaskbarBadgesEnabled(bool)
0x1800236b0  lea     rcx, [rbp+arg_0]
0x1800236b4  call    ?IsHideTaskbarFlashesEnabled@?$consume_Windows_Internal_Shell_IFocusSessionTheme@UFocusSessionActiveTheme@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionActiveTheme>::IsHideTaskbarFlashesEnabled(void)
0x1800236b9  mov     dl, al
0x1800236bb  lea     rcx, [rbp+arg_10]
0x1800236bf  call    ?IsHideTaskbarFlashesEnabled@?$consume_Windows_Internal_Shell_IFocusSessionTheme@UFocusSessionOffTheme@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@_N@Z; winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionOffTheme>::IsHideTaskbarFlashesEnabled(bool)
0x1800236c4  lea     rcx, [rbp+arg_0]
0x1800236c8  call    ?IsHideTaskbarFlashesEnabled@?$consume_Windows_Internal_Shell_IFocusSessionTheme@UFocusSessionActiveTheme@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionActiveTheme>::IsHideTaskbarFlashesEnabled(void)
0x1800236cd  test    al, al
0x1800236cf  jz      short loc_1800236E8
0x1800236d1  lea     rdx, aTaskbarflashin; "TaskbarFlashing"
0x1800236d8  call    _anonymous_namespace___GetRegistryBoolValue
0x1800236dd  mov     dl, al
0x1800236df  lea     rcx, [rbp+arg_10]
0x1800236e3  call    ?FocusQuietMomentApplicable@?$consume_Windows_Internal_UI_Notifications_IQuietHoursSettingsInterop@UIQuietHoursSettingsInterop@Notifications@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@_N@Z; winrt::impl::consume_Windows_Internal_UI_Notifications_IQuietHoursSettingsInterop<winrt::Windows::Internal::UI::Notifications::IQuietHoursSettingsInterop>::FocusQuietMomentApplicable(bool)
0x1800236e8  lea     rcx, [rbp+arg_0]
0x1800236ec  call    ?IsMuteNotificationsEnabled@?$consume_Windows_Internal_Shell_IFocusSessionTheme@UFocusSessionOffTheme@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionOffTheme>::IsMuteNotificationsEnabled(void)
0x1800236f1  mov     dl, al
0x1800236f3  lea     rcx, [rbp+arg_10]
0x1800236f7  call    ?IsMuteNotificationsEnabled@?$consume_Windows_Internal_Shell_IFocusSessionTheme@UFocusSessionOffTheme@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@_N@Z; winrt::impl::consume_Windows_Internal_Shell_IFocusSessionTheme<winrt::Windows::Internal::Shell::FocusSessionOffTheme>::IsMuteNotificationsEnabled(bool)
0x1800236fc  nop
0x1800236fd  lea     rcx, [rbp+arg_0]
0x180023701  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180023706  nop
0x180023707  lea     rcx, [rbp+arg_10]
0x18002370b  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180023710  mov     rbx, [rsp+20h+arg_8]
0x180023715  add     rsp, 20h
0x180023719  pop     rbp
0x18002371a  retn
```
