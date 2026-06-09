# _anonymous_namespace_::ApplyUapTextScale

- ea: `0x1800290dc`
- end: `0x180029168`
- name: `_anonymous_namespace_::ApplyUapTextScale`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029fc0`

## callees

- `0x180028fc0`
- `0x1800290dc`
- `0x18002a130`
- `0x18002a62c`
- `0x18002d628`
- `0x18002d6d8`
- `0x18002d900`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029129`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029129`

## string_xrefs

- `0x1800290e9`: `Software\Microsoft\Accessibility`
- `0x18002913b`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.ui.viewmanagement.core.uisettingscontroller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall anonymous_namespace_::ApplyUapTextScale(ExperienceUtil *a1)
{
  unsigned int v1; // eax
  const struct _WNF_STATE_NAME *v2; // rdx
  unsigned int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  Data = (int)a1;
  if ( ExperienceUtil::IsDesktop(a1) )
    winrt::Windows::UI::ViewManagement::Core::implementation::GetDesktopRegistryKey(
      (unsigned int)&hKey,
      L"Software\\Microsoft\\Accessibility");
  else
    winrt::Windows::UI::ViewManagement::Core::implementation::GetOneCoreRegistryKey(
      &hKey,
      (unsigned int)L"Software\\Microsoft\\Accessibility");
  v1 = RegSetValueExW(hKey, L"TextScaleFactor", 0, 4u, (const BYTE *)&Data, 4u);
  if ( v1 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xA7,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.ui.viewmanagement.core.uis"
                    "ettingscontroller.cpp",
      (const char *)v1,
      lpData);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::wnf_publish((wil *)&WNF_EOA_UISETTINGS_CHANGED, v2);
}

```

## disassembly

```asm
0x1800290dc  sub     rsp, 38h
0x1800290e0  mov     [rsp+38h+Data], ecx
0x1800290e4  call    ?IsDesktop@ExperienceUtil@@YA_NXZ; ExperienceUtil::IsDesktop(void)
0x1800290e9  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Accessibility"
0x1800290f0  lea     rcx, [rsp+38h+hKey]; unsigned int
0x1800290f5  test    al, al
0x1800290f7  jz      short loc_180029100
0x1800290f9  call    ?GetDesktopRegistryKey@implementation@Core@ViewManagement@UI@Windows@winrt@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; winrt::Windows::UI::ViewManagement::Core::implementation::GetDesktopRegistryKey(ushort const *)
0x1800290fe  jmp     short loc_180029105
0x180029100  call    ?GetOneCoreRegistryKey@implementation@Core@ViewManagement@UI@Windows@winrt@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; winrt::Windows::UI::ViewManagement::Core::implementation::GetOneCoreRegistryKey(ushort const *)
0x180029105  mov     rcx, [rsp+38h+hKey]; hKey
0x18002910a  mov     r9d, 4; dwType
0x180029110  mov     [rsp+38h+cbData], r9d; cbData
0x180029115  lea     rax, [rsp+38h+Data]
0x18002911a  mov     [rsp+38h+lpData], rax; unsigned int
0x18002911f  xor     r8d, r8d; Reserved
0x180029122  lea     rdx, ValueName; "TextScaleFactor"
0x180029129  call    cs:__imp_RegSetValueExW
0x18002912f  mov     rcx, [rsp+38h]; this
0x180029134  test    eax, eax
0x180029136  jz      short loc_18002914D
0x180029138  mov     r9d, eax; char *
0x18002913b  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\accessibletech\\ex"...
0x180029142  mov     edx, 0A7h; void *
0x180029147  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18002914d  lea     rcx, [rsp+38h+hKey]
0x180029152  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180029157  lea     rcx, WNF_EOA_UISETTINGS_CHANGED; this
0x18002915e  call    ?wnf_publish@wil@@YAXAEBU_WNF_STATE_NAME@@@Z; wil::wnf_publish(_WNF_STATE_NAME const &)
0x180029163  add     rsp, 38h
0x180029167  retn
```
