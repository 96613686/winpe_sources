# Windows::Networking::UX::Internal::WlanInterface::GetConfigurableEapMethods(Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::IWiFiEapMethod *> * *)

- ea: `0x18003e608`
- end: `0x18003e803`
- name: `?GetConfigurableEapMethods@WlanInterface@Internal@UX@Networking@Windows@@QEAAJPEAPEAU?$IVectorView@PEAUIWiFiEapMethod@UX@Networking@Windows@@@Collections@Foundation@5@@Z`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026b50`

## callees

- `0x180003ed0`
- `0x180004a70`
- `0x180008e30`
- `0x180009d90`
- `0x18000de4c`
- `0x18001d4d4`
- `0x180035ca0`
- `0x18003e608`
- `0x180049628`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e709`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e709`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e793`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e793`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18003e784`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18003e784`

## string_xrefs

- `0x18003e6a4`: `SYSTEM\ControlSet001\Services\RasMan\PPP\EAP`
- `0x18003e6fb`: `SYSTEM\ControlSet001\Services\EapHost\Methods`
- `0x18003e735`: `SYSTEM\ControlSet001\Services\EapHost\Methods`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::WlanInterface::GetConfigurableEapMethods(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 *v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rcx
  int ConfigurableEapMethods; // ebx
  LSTATUS v9; // eax
  int v10; // esi
  DWORD i; // edx
  __int64 v12; // rcx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[512]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v16[512]; // [rsp+440h] [rbp+340h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
  v5 = (__int64 *)(a1 + 1408);
  *a2 = 0;
  if ( *v5 )
    goto LABEL_16;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v5, a2, a3);
  ConfigurableEapMethods = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Networking::UX::IWiFiEapMethod,Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::IWiFiEapMethod *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IWiFiEapMethod *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IWiFiEapMethod *>,0>>(
                             v6,
                             v5);
  if ( ConfigurableEapMethods >= 0 )
  {
    ConfigurableEapMethods = Windows::Networking::UX::Internal::WlanInterface::_GetConfigurableEapMethods(
                               v7,
                               L"SYSTEM\\ControlSet001\\Services\\RasMan\\PPP\\EAP",
                               L"FriendlyName",
                               *v5);
    if ( ConfigurableEapMethods >= 0 )
    {
      hKey = 0;
      memset_0(Name, 0, sizeof(Name));
      memset_0(v16, 0, sizeof(v16));
      v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\ControlSet001\\Services\\EapHost\\Methods", 0, 0x20019u, &hKey);
      ConfigurableEapMethods = v9;
      if ( v9 > 0 )
        ConfigurableEapMethods = (unsigned __int16)v9 | 0x80070000;
      if ( ConfigurableEapMethods >= 0 )
      {
        v10 = 1;
        for ( i = 0; !RegEnumKeyW(hKey, i, Name, 0x200u); i = v10++ )
        {
          if ( StringCchPrintfW(v16, 0x200u, L"%s\\%s", L"SYSTEM\\ControlSet001\\Services\\EapHost\\Methods", Name) >= 0 )
            ConfigurableEapMethods = Windows::Networking::UX::Internal::WlanInterface::_GetConfigurableEapMethods(
                                       v12,
                                       v16,
                                       L"PeerFriendlyName",
                                       *v5);
        }
      }
      RegCloseKey(hKey);
      if ( ConfigurableEapMethods >= 0 )
LABEL_16:
        ConfigurableEapMethods = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)*v5 + 64LL))(*v5, a2);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      106,
      &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
      (unsigned int)ConfigurableEapMethods);
  return (unsigned int)ConfigurableEapMethods;
}

```

## disassembly

```asm
0x18003e608  mov     [rsp-8+arg_10], rbx
0x18003e60d  push    rbp
0x18003e60e  push    rsi
0x18003e60f  push    rdi
0x18003e610  push    r13
0x18003e612  push    r14
0x18003e614  lea     rbp, [rsp-750h]
0x18003e61c  sub     rsp, 850h
0x18003e623  mov     rax, cs:__security_cookie
0x18003e62a  xor     rax, rsp
0x18003e62d  mov     [rbp+770h+var_30], rax
0x18003e634  mov     r14, rdx
0x18003e637  mov     rdi, rcx
0x18003e63a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e641  lea     r13, WPP_GLOBAL_Control
0x18003e648  cmp     rcx, r13
0x18003e64b  jz      short loc_18003E668
0x18003e64d  test    byte ptr [rcx+1Ch], 40h
0x18003e651  jz      short loc_18003E668
0x18003e653  mov     rcx, [rcx+10h]
0x18003e657  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18003e65e  mov     edx, 69h ; 'i'
0x18003e663  call    WPP_SF_
0x18003e668  add     rdi, 580h
0x18003e66f  mov     qword ptr [r14], 0
0x18003e676  cmp     qword ptr [rdi], 0
0x18003e67a  jnz     loc_18003E79D
0x18003e680  mov     rcx, rdi
0x18003e683  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003e688  mov     rdx, rdi
0x18003e68b  call    ??$CreateExternalObjectVector@UIWiFiEapMethod@UX@Networking@Windows@@V?$AgileVector@PEAUIWiFiEapMethod@UX@Networking@Windows@@U?$DefaultEqualityPredicate@PEAUIWiFiEapMethod@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIWiFiEapMethod@UX@Networking@Windows@@@6784@$0A@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAUIWiFiEapMethod@UX@Networking@Windows@@U?$DefaultEqualityPredicate@PEAUIWiFiEapMethod@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIWiFiEapMethod@UX@Networking@Windows@@@6784@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Networking::UX::IWiFiEapMethod,Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::IWiFiEapMethod *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IWiFiEapMethod *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IWiFiEapMethod *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::IWiFiEapMethod *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IWiFiEapMethod *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IWiFiEapMethod *>,0> * *)
0x18003e690  mov     ebx, eax
0x18003e692  test    eax, eax
0x18003e694  js      loc_18003E7B1
0x18003e69a  mov     r9, [rdi]
0x18003e69d  lea     r8, aFriendlyname; "FriendlyName"
0x18003e6a4  lea     rdx, aSystemControls_0; "SYSTEM\\ControlSet001\\Services\\RasMan"...
0x18003e6ab  call    ?_GetConfigurableEapMethods@WlanInterface@Internal@UX@Networking@Windows@@IEAAJPEBG0PEAV?$AgileVector@PEAUIWiFiEapMethod@UX@Networking@Windows@@U?$DefaultEqualityPredicate@PEAUIWiFiEapMethod@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIWiFiEapMethod@UX@Networking@Windows@@@6784@$0A@@2Collections@Foundation@5@@Z; Windows::Networking::UX::Internal::WlanInterface::_GetConfigurableEapMethods(ushort const *,ushort const *,Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::IWiFiEapMethod *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IWiFiEapMethod *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IWiFiEapMethod *>,0> *)
0x18003e6b0  mov     ebx, eax
0x18003e6b2  test    eax, eax
0x18003e6b4  js      loc_18003E7B1
0x18003e6ba  mov     ebx, 400h
0x18003e6bf  mov     [rsp+870h+hKey], 0
0x18003e6c8  mov     r8d, ebx; Size
0x18003e6cb  lea     rcx, [rsp+870h+Name]; void *
0x18003e6d0  xor     edx, edx; Val
0x18003e6d2  call    memset_0
0x18003e6d7  mov     r8d, ebx; Size
0x18003e6da  lea     rcx, [rbp+770h+var_430]; void *
0x18003e6e1  xor     edx, edx; Val
0x18003e6e3  call    memset_0
0x18003e6e8  lea     rax, [rsp+870h+hKey]
0x18003e6ed  mov     r9d, 20019h; samDesired
0x18003e6f3  xor     r8d, r8d; ulOptions
0x18003e6f6  mov     [rsp+870h+phkResult], rax; phkResult
0x18003e6fb  lea     rdx, SubKey; "SYSTEM\\ControlSet001\\Services\\EapHos"...
0x18003e702  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003e709  call    cs:__imp_RegOpenKeyExW
0x18003e70f  mov     ebx, eax
0x18003e711  test    eax, eax
0x18003e713  jle     short loc_18003E71E
0x18003e715  movzx   ebx, ax
0x18003e718  or      ebx, 80070000h
0x18003e71e  test    ebx, ebx
0x18003e720  js      short loc_18003E78E
0x18003e722  mov     esi, 1
0x18003e727  xor     edx, edx
0x18003e729  jmp     short loc_18003E774
0x18003e72b  lea     rax, [rsp+870h+Name]
0x18003e730  mov     edx, 200h; unsigned __int64
0x18003e735  lea     r9, SubKey; "SYSTEM\\ControlSet001\\Services\\EapHos"...
0x18003e73c  mov     [rsp+870h+phkResult], rax
0x18003e741  lea     r8, aSS; "%s\\%s"
0x18003e748  lea     rcx, [rbp+770h+var_430]; unsigned __int16 *
0x18003e74f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003e754  test    eax, eax
0x18003e756  js      short loc_18003E770
0x18003e758  mov     r9, [rdi]
0x18003e75b  lea     r8, aPeerfriendlyna; "PeerFriendlyName"
0x18003e762  lea     rdx, [rbp+770h+var_430]
0x18003e769  call    ?_GetConfigurableEapMethods@WlanInterface@Internal@UX@Networking@Windows@@IEAAJPEBG0PEAV?$AgileVector@PEAUIWiFiEapMethod@UX@Networking@Windows@@U?$DefaultEqualityPredicate@PEAUIWiFiEapMethod@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIWiFiEapMethod@UX@Networking@Windows@@@6784@$0A@@2Collections@Foundation@5@@Z; Windows::Networking::UX::Internal::WlanInterface::_GetConfigurableEapMethods(ushort const *,ushort const *,Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::IWiFiEapMethod *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IWiFiEapMethod *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IWiFiEapMethod *>,0> *)
0x18003e76e  mov     ebx, eax
0x18003e770  mov     edx, esi; dwIndex
0x18003e772  inc     esi
0x18003e774  mov     rcx, [rsp+870h+hKey]; hKey
0x18003e779  lea     r8, [rsp+870h+Name]; lpName
0x18003e77e  mov     r9d, 200h; cchName
0x18003e784  call    cs:__imp_RegEnumKeyW
0x18003e78a  test    eax, eax
0x18003e78c  jz      short loc_18003E72B
0x18003e78e  mov     rcx, [rsp+870h+hKey]; hKey
0x18003e793  call    cs:__imp_RegCloseKey
0x18003e799  test    ebx, ebx
0x18003e79b  js      short loc_18003E7B1
0x18003e79d  mov     rcx, [rdi]
0x18003e7a0  mov     rdx, r14
0x18003e7a3  mov     rax, [rcx]
0x18003e7a6  mov     rax, [rax+40h]
0x18003e7aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e7af  mov     ebx, eax
0x18003e7b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e7b8  cmp     rcx, r13
0x18003e7bb  jz      short loc_18003E7DB
0x18003e7bd  test    byte ptr [rcx+1Ch], 40h
0x18003e7c1  jz      short loc_18003E7DB
0x18003e7c3  mov     rcx, [rcx+10h]
0x18003e7c7  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18003e7ce  mov     edx, 6Ah ; 'j'
0x18003e7d3  mov     r9d, ebx
0x18003e7d6  call    WPP_SF_d
0x18003e7db  mov     eax, ebx
0x18003e7dd  mov     rcx, [rbp+770h+var_30]
0x18003e7e4  xor     rcx, rsp; StackCookie
0x18003e7e7  call    __security_check_cookie
0x18003e7ec  mov     rbx, [rsp+870h+arg_10]
0x18003e7f4  add     rsp, 850h
0x18003e7fb  pop     r14
0x18003e7fd  pop     r13
0x18003e7ff  pop     rdi
0x18003e800  pop     rsi
0x18003e801  pop     rbp
0x18003e802  retn
```
