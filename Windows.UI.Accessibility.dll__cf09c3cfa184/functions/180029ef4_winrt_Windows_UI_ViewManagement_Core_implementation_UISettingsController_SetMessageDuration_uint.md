# winrt::Windows::UI::ViewManagement::Core::implementation::UISettingsController::SetMessageDuration(uint)

- ea: `0x180029ef4`
- end: `0x180029fae`
- name: `?SetMessageDuration@UISettingsController@implementation@Core@ViewManagement@UI@Windows@winrt@@QEAAXI@Z`
- size: `186`
- prototype: `void __fastcall(winrt::Windows::UI::ViewManagement::Core::implementation::UISettingsController *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029ed0`

## callees

- `0x18000ea34`
- `0x180028fc0`
- `0x180029ef4`
- `0x18002a130`
- `0x18002a62c`
- `0x18002d6d8`
- `0x18002d900`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029f6f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029f6f`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180029f1a`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180029f1a`

## string_xrefs

- `0x180029f3b`: `Software\Microsoft\Accessibility`
- `0x180029f29`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.ui.viewmanagement.core.uisettingscontroller.cpp`
- `0x180029f81`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.ui.viewmanagement.core.uisettingscontroller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::Windows::UI::ViewManagement::Core::implementation::UISettingsController::SetMessageDuration(
        winrt::Windows::UI::ViewManagement::Core::implementation::UISettingsController *this,
        int a2)
{
  const struct _WNF_STATE_NAME *v2; // rdx
  const char *v3; // r9
  HKEY *OneCoreRegistryKey; // rax
  unsigned int v5; // eax
  unsigned int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  winrt::Windows::UI::ViewManagement::Core::implementation::UISettingsController *v8; // [rsp+40h] [rbp+8h] BYREF
  PVOID pvParam; // [rsp+48h] [rbp+10h] BYREF

  LODWORD(pvParam) = a2;
  v8 = this;
  if ( ExperienceUtil::IsDesktop(this) )
  {
    if ( !SystemParametersInfoW(0x2017u, 0, (PVOID)(unsigned int)pvParam, 3u) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xFB,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.ui.viewmanagement.core.u"
                      "isettingscontroller.cpp",
        v3);
  }
  else
  {
    OneCoreRegistryKey = (HKEY *)winrt::Windows::UI::ViewManagement::Core::implementation::GetOneCoreRegistryKey(
                                   (PHKEY)&v8,
                                   (unsigned int)L"Software\\Microsoft\\Accessibility");
    v5 = RegSetValueExW(*OneCoreRegistryKey, L"MessageDuration", 0, 4u, (const BYTE *)&pvParam, 4u);
    if ( v5 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x105,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.ui.viewmanagement.core.u"
                      "isettingscontroller.cpp",
        (const char *)v5,
        lpData);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v8);
  }
  wil::wnf_publish((wil *)&WNF_EOA_UISETTINGS_CHANGED, v2);
}

```

## disassembly

```asm
0x180029ef4  mov     dword ptr [rsp+pvParam], edx
0x180029ef8  mov     [rsp+arg_0], rcx
0x180029efd  sub     rsp, 38h
0x180029f01  call    ?IsDesktop@ExperienceUtil@@YA_NXZ; ExperienceUtil::IsDesktop(void)
0x180029f06  test    al, al
0x180029f08  jz      short loc_180029F3B
0x180029f0a  mov     r8d, dword ptr [rsp+38h+pvParam]; pvParam
0x180029f0f  xor     edx, edx; uiParam
0x180029f11  lea     r9d, [rdx+3]; fWinIni
0x180029f15  mov     ecx, 2017h; uiAction
0x180029f1a  call    cs:__imp_SystemParametersInfoW
0x180029f20  test    eax, eax
0x180029f22  jnz     short loc_180029F9D
0x180029f24  mov     rcx, [rsp+38h]; this
0x180029f29  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\accessibletech\\ex"...
0x180029f30  mov     edx, 0FBh; void *
0x180029f35  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180029f3b  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Accessibility"
0x180029f42  lea     rcx, [rsp+38h+arg_0]
0x180029f47  call    ?GetOneCoreRegistryKey@implementation@Core@ViewManagement@UI@Windows@winrt@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; winrt::Windows::UI::ViewManagement::Core::implementation::GetOneCoreRegistryKey(ushort const *)
0x180029f4c  nop
0x180029f4d  mov     r9d, 4; dwType
0x180029f53  mov     [rsp+38h+cbData], r9d; cbData
0x180029f58  lea     rcx, [rsp+38h+pvParam]
0x180029f5d  mov     [rsp+38h+lpData], rcx; unsigned int
0x180029f62  xor     r8d, r8d; Reserved
0x180029f65  lea     rdx, aMessageduratio; "MessageDuration"
0x180029f6c  mov     rcx, [rax]; hKey
0x180029f6f  call    cs:__imp_RegSetValueExW
0x180029f75  mov     rcx, [rsp+38h]; this
0x180029f7a  test    eax, eax
0x180029f7c  jz      short loc_180029F93
0x180029f7e  mov     r9d, eax; char *
0x180029f81  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\accessibletech\\ex"...
0x180029f88  mov     edx, 105h; void *
0x180029f8d  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180029f93  lea     rcx, [rsp+38h+arg_0]
0x180029f98  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180029f9d  lea     rcx, WNF_EOA_UISETTINGS_CHANGED; this
0x180029fa4  call    ?wnf_publish@wil@@YAXAEBU_WNF_STATE_NAME@@@Z; wil::wnf_publish(_WNF_STATE_NAME const &)
0x180029fa9  add     rsp, 38h
0x180029fad  retn
```
