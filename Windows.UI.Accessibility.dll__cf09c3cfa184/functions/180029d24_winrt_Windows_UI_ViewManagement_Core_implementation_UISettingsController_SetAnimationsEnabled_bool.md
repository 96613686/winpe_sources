# winrt::Windows::UI::ViewManagement::Core::implementation::UISettingsController::SetAnimationsEnabled(bool)

- ea: `0x180029d24`
- end: `0x180029dba`
- name: `?SetAnimationsEnabled@UISettingsController@implementation@Core@ViewManagement@UI@Windows@winrt@@QEAAX_N@Z`
- size: `150`
- prototype: `void __fastcall(winrt::Windows::UI::ViewManagement::Core::implementation::UISettingsController *__hidden this, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029d00`

## callees

- `0x180028fc0`
- `0x180029bfc`
- `0x180029d24`
- `0x18002a130`
- `0x18002a62c`
- `0x18002d6d8`
- `0x18002d900`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029d7b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029d7b`

## string_xrefs

- `0x180029d47`: `Software\Microsoft\Accessibility`
- `0x180029d8d`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.ui.viewmanagement.core.uisettingscontroller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::Windows::UI::ViewManagement::Core::implementation::UISettingsController::SetAnimationsEnabled(
        winrt::Windows::UI::ViewManagement::Core::implementation::UISettingsController *this,
        unsigned __int8 a2)
{
  int v2; // ebx
  const struct _WNF_STATE_NAME *v3; // rdx
  HKEY *OneCoreRegistryKey; // rax
  unsigned int v5; // eax
  unsigned int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  winrt::Windows::UI::ViewManagement::Core::implementation::UISettingsController *Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY v9; // [rsp+50h] [rbp+18h] BYREF

  Data = this;
  v2 = a2;
  if ( ExperienceUtil::IsDesktop(this) )
  {
    anonymous_namespace_::SetAnimationsDesktop(v2);
  }
  else
  {
    LODWORD(Data) = v2;
    OneCoreRegistryKey = (HKEY *)winrt::Windows::UI::ViewManagement::Core::implementation::GetOneCoreRegistryKey(
                                   &v9,
                                   (unsigned int)L"Software\\Microsoft\\Accessibility");
    v5 = RegSetValueExW(*OneCoreRegistryKey, L"EnableAnimations", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v5 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.ui.viewmanagement.core.u"
                      "isettingscontroller.cpp",
        (const char *)v5,
        lpData);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v9);
  }
  wil::wnf_publish((wil *)&WNF_EOA_UISETTINGS_CHANGED, v3);
}

```

## disassembly

```asm
0x180029d24  mov     [rsp+Data], rcx
0x180029d29  push    rbx
0x180029d2a  sub     rsp, 30h
0x180029d2e  movzx   ebx, dl
0x180029d31  call    ?IsDesktop@ExperienceUtil@@YA_NXZ; ExperienceUtil::IsDesktop(void)
0x180029d36  test    al, al
0x180029d38  jz      short loc_180029D43
0x180029d3a  mov     cl, bl
0x180029d3c  call    _anonymous_namespace___SetAnimationsDesktop
0x180029d41  jmp     short loc_180029DA9
0x180029d43  mov     dword ptr [rsp+38h+Data], ebx
0x180029d47  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Accessibility"
0x180029d4e  lea     rcx, [rsp+38h+arg_10]
0x180029d53  call    ?GetOneCoreRegistryKey@implementation@Core@ViewManagement@UI@Windows@winrt@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; winrt::Windows::UI::ViewManagement::Core::implementation::GetOneCoreRegistryKey(ushort const *)
0x180029d58  nop
0x180029d59  mov     r9d, 4; dwType
0x180029d5f  mov     [rsp+38h+cbData], r9d; cbData
0x180029d64  lea     rcx, [rsp+38h+Data]
0x180029d69  mov     [rsp+38h+lpData], rcx; unsigned int
0x180029d6e  xor     r8d, r8d; Reserved
0x180029d71  lea     rdx, aEnableanimatio; "EnableAnimations"
0x180029d78  mov     rcx, [rax]; hKey
0x180029d7b  call    cs:__imp_RegSetValueExW
0x180029d81  mov     rcx, [rsp+38h]; this
0x180029d86  test    eax, eax
0x180029d88  jz      short loc_180029D9F
0x180029d8a  mov     r9d, eax; char *
0x180029d8d  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\accessibletech\\ex"...
0x180029d94  mov     edx, 43h ; 'C'; void *
0x180029d99  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180029d9f  lea     rcx, [rsp+38h+arg_10]
0x180029da4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180029da9  lea     rcx, WNF_EOA_UISETTINGS_CHANGED; this
0x180029db0  add     rsp, 30h
0x180029db4  pop     rbx
0x180029db5  jmp     ?wnf_publish@wil@@YAXAEBU_WNF_STATE_NAME@@@Z; wil::wnf_publish(_WNF_STATE_NAME const &)
```
