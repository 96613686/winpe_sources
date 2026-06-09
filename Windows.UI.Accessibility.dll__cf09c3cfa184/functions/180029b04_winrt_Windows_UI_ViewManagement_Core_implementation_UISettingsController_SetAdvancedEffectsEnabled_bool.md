# winrt::Windows::UI::ViewManagement::Core::implementation::UISettingsController::SetAdvancedEffectsEnabled(bool)

- ea: `0x180029b04`
- end: `0x180029bf4`
- name: `?SetAdvancedEffectsEnabled@UISettingsController@implementation@Core@ViewManagement@UI@Windows@winrt@@QEAAX_N@Z`
- size: `240`
- prototype: `void __fastcall(winrt::Windows::UI::ViewManagement::Core::implementation::UISettingsController *__hidden this, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029ae0`

## callees

- `0x180028fc0`
- `0x180029b04`
- `0x18002a130`
- `0x18002a62c`
- `0x18002d628`
- `0x18002d6d8`
- `0x18002d900`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029b51`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029ba9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029b51`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029ba9`

## string_xrefs

- `0x180029b63`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.ui.viewmanagement.core.uisettingscontroller.cpp`
- `0x180029bbb`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.ui.viewmanagement.core.uisettingscontroller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::Windows::UI::ViewManagement::Core::implementation::UISettingsController::SetAdvancedEffectsEnabled(
        winrt::Windows::UI::ViewManagement::Core::implementation::UISettingsController *this,
        unsigned __int8 a2)
{
  HKEY *DesktopRegistryKey; // rax
  unsigned int v3; // eax
  HKEY *OneCoreRegistryKey; // rax
  unsigned int v5; // eax
  const struct _WNF_STATE_NAME *v6; // rdx
  const struct _WNF_STATE_NAME *v7; // rdx
  unsigned int lpData; // [rsp+20h] [rbp-18h]
  unsigned int lpDataa; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  winrt::Windows::UI::ViewManagement::Core::implementation::UISettingsController *v11; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+48h] [rbp+10h] BYREF

  v11 = this;
  Data = a2;
  if ( ExperienceUtil::IsDesktop(this) )
  {
    DesktopRegistryKey = (HKEY *)winrt::Windows::UI::ViewManagement::Core::implementation::GetDesktopRegistryKey(
                                   (unsigned int)&v11,
                                   L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Themes\\Personalize");
    v3 = RegSetValueExW(*DesktopRegistryKey, L"EnableTransparency", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v3 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xC4,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.ui.viewmanagement.core.u"
                      "isettingscontroller.cpp",
        (const char *)v3,
        lpData);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v11);
  }
  else
  {
    OneCoreRegistryKey = (HKEY *)winrt::Windows::UI::ViewManagement::Core::implementation::GetOneCoreRegistryKey(
                                   (PHKEY)&v11,
                                   (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Themes\\Personalize");
    v5 = RegSetValueExW(*OneCoreRegistryKey, L"EnableTransparency", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v5 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xD0,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.ui.viewmanagement.core.u"
                      "isettingscontroller.cpp",
        (const char *)v5,
        lpDataa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v11);
    wil::wnf_publish((wil *)WNF_SHEL_SYSTEM_THEMECOLOR_CHANGED, v6);
    wil::wnf_publish((wil *)&WNF_SHEL_TRANSPARENCY_EFFECTS_CHANGED, v7);
  }
}

```

## disassembly

```asm
0x180029b04  mov     [rsp+arg_0], rcx
0x180029b09  sub     rsp, 38h
0x180029b0d  movzx   eax, dl
0x180029b10  mov     [rsp+38h+Data], eax
0x180029b14  call    ?IsDesktop@ExperienceUtil@@YA_NXZ; ExperienceUtil::IsDesktop(void)
0x180029b19  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180029b20  lea     rcx, [rsp+38h+arg_0]; unsigned int
0x180029b25  test    al, al
0x180029b27  jz      short loc_180029B81
0x180029b29  call    ?GetDesktopRegistryKey@implementation@Core@ViewManagement@UI@Windows@winrt@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; winrt::Windows::UI::ViewManagement::Core::implementation::GetDesktopRegistryKey(ushort const *)
0x180029b2e  nop
0x180029b2f  mov     r9d, 4; dwType
0x180029b35  mov     [rsp+38h+cbData], r9d; cbData
0x180029b3a  lea     rcx, [rsp+38h+Data]
0x180029b3f  mov     [rsp+38h+lpData], rcx; unsigned int
0x180029b44  xor     r8d, r8d; Reserved
0x180029b47  lea     rdx, aEnabletranspar; "EnableTransparency"
0x180029b4e  mov     rcx, [rax]; hKey
0x180029b51  call    cs:__imp_RegSetValueExW
0x180029b57  mov     rcx, [rsp+38h]; this
0x180029b5c  test    eax, eax
0x180029b5e  jz      short loc_180029B75
0x180029b60  mov     r9d, eax; char *
0x180029b63  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\accessibletech\\ex"...
0x180029b6a  mov     edx, 0C4h; void *
0x180029b6f  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180029b75  lea     rcx, [rsp+38h+arg_0]
0x180029b7a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180029b7f  jmp     short loc_180029BEF
0x180029b81  call    ?GetOneCoreRegistryKey@implementation@Core@ViewManagement@UI@Windows@winrt@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; winrt::Windows::UI::ViewManagement::Core::implementation::GetOneCoreRegistryKey(ushort const *)
0x180029b86  nop
0x180029b87  mov     r9d, 4; dwType
0x180029b8d  mov     [rsp+38h+cbData], r9d; cbData
0x180029b92  lea     rcx, [rsp+38h+Data]
0x180029b97  mov     [rsp+38h+lpData], rcx; unsigned int
0x180029b9c  xor     r8d, r8d; Reserved
0x180029b9f  lea     rdx, aEnabletranspar; "EnableTransparency"
0x180029ba6  mov     rcx, [rax]; hKey
0x180029ba9  call    cs:__imp_RegSetValueExW
0x180029baf  mov     rcx, [rsp+38h]; this
0x180029bb4  test    eax, eax
0x180029bb6  jz      short loc_180029BCD
0x180029bb8  mov     r9d, eax; char *
0x180029bbb  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\accessibletech\\ex"...
0x180029bc2  mov     edx, 0D0h; void *
0x180029bc7  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180029bcd  lea     rcx, [rsp+38h+arg_0]
0x180029bd2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180029bd7  lea     rcx, WNF_SHEL_SYSTEM_THEMECOLOR_CHANGED; this
0x180029bde  call    ?wnf_publish@wil@@YAXAEBU_WNF_STATE_NAME@@@Z; wil::wnf_publish(_WNF_STATE_NAME const &)
0x180029be3  lea     rcx, WNF_SHEL_TRANSPARENCY_EFFECTS_CHANGED; this
0x180029bea  call    ?wnf_publish@wil@@YAXAEBU_WNF_STATE_NAME@@@Z; wil::wnf_publish(_WNF_STATE_NAME const &)
0x180029bef  add     rsp, 38h
0x180029bf3  retn
```
