# winrt::Windows::UI::ViewManagement::Core::implementation::UISettingsController::SetAutoHideScrollBars(bool)

- ea: `0x180029de4`
- end: `0x180029ec6`
- name: `?SetAutoHideScrollBars@UISettingsController@implementation@Core@ViewManagement@UI@Windows@winrt@@QEAAX_N@Z`
- size: `226`
- prototype: `void __fastcall(winrt::Windows::UI::ViewManagement::Core::implementation::UISettingsController *__hidden this, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029dc0`

## callees

- `0x180028fc0`
- `0x180029de4`
- `0x18002a130`
- `0x18002a62c`
- `0x18002d628`
- `0x18002d6d8`
- `0x18002d900`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029e32`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029e87`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029e32`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029e87`

## string_xrefs

- `0x180029e58`: `Software\Microsoft\Accessibility`
- `0x180029e03`: `Control Panel\Accessibility`
- `0x180029e44`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.ui.viewmanagement.core.uisettingscontroller.cpp`
- `0x180029e99`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.ui.viewmanagement.core.uisettingscontroller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::Windows::UI::ViewManagement::Core::implementation::UISettingsController::SetAutoHideScrollBars(
        winrt::Windows::UI::ViewManagement::Core::implementation::UISettingsController *this,
        unsigned __int8 a2)
{
  int v2; // ebx
  bool IsDesktop; // al
  HKEY *DesktopRegistryKey; // rax
  unsigned int v5; // eax
  HKEY *OneCoreRegistryKey; // rax
  unsigned int v7; // eax
  const struct _WNF_STATE_NAME *v8; // rdx
  unsigned int lpData; // [rsp+20h] [rbp-18h]
  unsigned int lpDataa; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  winrt::Windows::UI::ViewManagement::Core::implementation::UISettingsController *Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY v13; // [rsp+50h] [rbp+18h] BYREF

  Data = this;
  v2 = a2;
  IsDesktop = ExperienceUtil::IsDesktop(this);
  LODWORD(Data) = v2;
  if ( IsDesktop )
  {
    DesktopRegistryKey = (HKEY *)winrt::Windows::UI::ViewManagement::Core::implementation::GetDesktopRegistryKey(
                                   (unsigned int)&v13,
                                   L"Control Panel\\Accessibility");
    v5 = RegSetValueExW(*DesktopRegistryKey, L"DynamicScrollbars", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v5 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x50,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.ui.viewmanagement.core.u"
                      "isettingscontroller.cpp",
        (const char *)v5,
        lpData);
  }
  else
  {
    OneCoreRegistryKey = (HKEY *)winrt::Windows::UI::ViewManagement::Core::implementation::GetOneCoreRegistryKey(
                                   &v13,
                                   (unsigned int)L"Software\\Microsoft\\Accessibility");
    v7 = RegSetValueExW(*OneCoreRegistryKey, L"DynamicScrollbars", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v7 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x5C,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.ui.viewmanagement.core.u"
                      "isettingscontroller.cpp",
        (const char *)v7,
        lpDataa);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v13);
  wil::wnf_publish((wil *)&WNF_EOA_UISETTINGS_CHANGED, v8);
}

```

## disassembly

```asm
0x180029de4  mov     [rsp+Data], rcx
0x180029de9  push    rbx
0x180029dea  sub     rsp, 30h
0x180029dee  movzx   ebx, dl
0x180029df1  call    ?IsDesktop@ExperienceUtil@@YA_NXZ; ExperienceUtil::IsDesktop(void)
0x180029df6  mov     dword ptr [rsp+38h+Data], ebx
0x180029dfa  lea     rcx, [rsp+38h+arg_10]; unsigned int
0x180029dff  test    al, al
0x180029e01  jz      short loc_180029E58
0x180029e03  lea     rdx, aControlPanelAc; "Control Panel\\Accessibility"
0x180029e0a  call    ?GetDesktopRegistryKey@implementation@Core@ViewManagement@UI@Windows@winrt@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; winrt::Windows::UI::ViewManagement::Core::implementation::GetDesktopRegistryKey(ushort const *)
0x180029e0f  nop
0x180029e10  mov     r9d, 4; dwType
0x180029e16  mov     [rsp+38h+cbData], r9d; cbData
0x180029e1b  lea     rcx, [rsp+38h+Data]
0x180029e20  mov     [rsp+38h+lpData], rcx; unsigned int
0x180029e25  xor     r8d, r8d; Reserved
0x180029e28  lea     rdx, aDynamicscrollb; "DynamicScrollbars"
0x180029e2f  mov     rcx, [rax]; hKey
0x180029e32  call    cs:__imp_RegSetValueExW
0x180029e38  mov     rcx, [rsp+38h]; this
0x180029e3d  test    eax, eax
0x180029e3f  jz      short loc_180029E56
0x180029e41  mov     r9d, eax; char *
0x180029e44  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\accessibletech\\ex"...
0x180029e4b  mov     edx, 50h ; 'P'; void *
0x180029e50  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180029e56  jmp     short loc_180029EAB
0x180029e58  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Accessibility"
0x180029e5f  call    ?GetOneCoreRegistryKey@implementation@Core@ViewManagement@UI@Windows@winrt@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; winrt::Windows::UI::ViewManagement::Core::implementation::GetOneCoreRegistryKey(ushort const *)
0x180029e64  nop
0x180029e65  mov     r9d, 4; dwType
0x180029e6b  mov     [rsp+38h+cbData], r9d; cbData
0x180029e70  lea     rcx, [rsp+38h+Data]
0x180029e75  mov     [rsp+38h+lpData], rcx; unsigned int
0x180029e7a  xor     r8d, r8d; Reserved
0x180029e7d  lea     rdx, aDynamicscrollb; "DynamicScrollbars"
0x180029e84  mov     rcx, [rax]; hKey
0x180029e87  call    cs:__imp_RegSetValueExW
0x180029e8d  mov     rcx, [rsp+38h]; this
0x180029e92  test    eax, eax
0x180029e94  jz      short loc_180029EAB
0x180029e96  mov     r9d, eax; char *
0x180029e99  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\accessibletech\\ex"...
0x180029ea0  mov     edx, 5Ch ; '\'; void *
0x180029ea5  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180029eab  lea     rcx, [rsp+38h+arg_10]
0x180029eb0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180029eb5  lea     rcx, WNF_EOA_UISETTINGS_CHANGED; this
0x180029ebc  add     rsp, 30h
0x180029ec0  pop     rbx
0x180029ec1  jmp     ?wnf_publish@wil@@YAXAEBU_WNF_STATE_NAME@@@Z; wil::wnf_publish(_WNF_STATE_NAME const &)
```
