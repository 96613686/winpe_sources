# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<CloudExperienceHostAPI::ILicensingPolicyHelper,CloudExperienceHostAPI::INetworkingHelper,CloudExperienceHostAPI::IOobeHelper,CloudExperienceHostAPI::IOobeHelper2,CloudExperienceHostAPI::IOobeDataHelper,CloudExperienceHostAPI::ISystemPowerHelper,CloudExperienceHostAPI::IWebAuthHelper,CloudExperienceHostAPI::INavigationAccessPolicyHelper,CloudExperienceHostAPI::IHtmlFileHelper,CloudExperienceHostAPI::ITimeZoneHelper,CloudExperienceHostAPI::IWnfSynchronization,CloudExperienceHostAPI::IAppPackageHelper,CloudExperienceHostAPI::IFlightDataHelper,CloudExperienceHostAPI::IMediaAccessPolicyHelper,CloudExperienceHostAPI::ISystemInformation,CloudExperienceHostAPI::IWwanHelper,CloudExperienceHostAPI::ILogonStatsHelper,CloudExperienceHostAPI::IOobeDriverInstaller,CloudExperienceHostAPI::IKeyboardInjectionHelper>,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x1800a1980`
- end: `0x1800a19ea`
- name: `?GetIids@?$ActivationFactory@U?$Implements@UILicensingPolicyHelper@CloudExperienceHostAPI@@UINetworkingHelper@2@UIOobeHelper@2@UIOobeHelper2@2@UIOobeDataHelper@2@UISystemPowerHelper@2@UIWebAuthHelper@2@UINavigationAccessPolicyHelper@2@UIHtmlFileHelper@2@UITimeZoneHelper@2@UIWnfSynchronization@2@UIAppPackageHelper@2@UIFlightDataHelper@2@UIMediaAccessPolicyHelper@2@UISystemInformation@2@UIWwanHelper@2@UILogonStatsHelper@2@UIOobeDriverInstaller@2@UIKeyboardInjectionHelper@2@@WRL@Microsoft@@VFtmBase@23@VNil@Details@23@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `20`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a19f0`
- `0x1800a1a00`
- `0x1800a1a10`
- `0x1800a1a20`
- `0x1800a1a30`
- `0x1800a1a40`
- `0x1800a1a50`
- `0x1800a1a60`
- `0x1800a1a70`
- `0x1800a1a80`
- `0x1800a1a90`
- `0x1800a1aa0`
- `0x1800a1ab0`
- `0x1800a1ac0`
- `0x1800a1ad0`
- `0x1800a1ae0`
- `0x1800a1b00`
- `0x1800a1b20`
- `0x1800a1b40`
- `0x1800a1c00`

## callees

- `0x1800a11b0`
- `0x1800a1980`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a19a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a19a2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<CloudExperienceHostAPI::ILicensingPolicyHelper,CloudExperienceHostAPI::INetworkingHelper,CloudExperienceHostAPI::IOobeHelper,CloudExperienceHostAPI::IOobeHelper2,CloudExperienceHostAPI::IOobeDataHelper,CloudExperienceHostAPI::ISystemPowerHelper,CloudExperienceHostAPI::IWebAuthHelper,CloudExperienceHostAPI::INavigationAccessPolicyHelper,CloudExperienceHostAPI::IHtmlFileHelper,CloudExperienceHostAPI::ITimeZoneHelper,CloudExperienceHostAPI::IWnfSynchronization,CloudExperienceHostAPI::IAppPackageHelper,CloudExperienceHostAPI::IFlightDataHelper,CloudExperienceHostAPI::IMediaAccessPolicyHelper,CloudExperienceHostAPI::ISystemInformation,CloudExperienceHostAPI::IWwanHelper,CloudExperienceHostAPI::ILogonStatsHelper,CloudExperienceHostAPI::IOobeDriverInstaller,CloudExperienceHostAPI::IKeyboardInjectionHelper>,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x140u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_00000035_0000_0000_c000_000000000046;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<CloudExperienceHostAPI::ILicensingPolicyHelper,CloudExperienceHostAPI::INetworkingHelper,CloudExperienceHostAPI::IOobeHelper,CloudExperienceHostAPI::IOobeHelper2,CloudExperienceHostAPI::IOobeDataHelper,CloudExperienceHostAPI::ISystemPowerHelper,CloudExperienceHostAPI::IWebAuthHelper,CloudExperienceHostAPI::INavigationAccessPolicyHelper,CloudExperienceHostAPI::IHtmlFileHelper,CloudExperienceHostAPI::ITimeZoneHelper,CloudExperienceHostAPI::IWnfSynchronization,CloudExperienceHostAPI::IAppPackageHelper,CloudExperienceHostAPI::IFlightDataHelper,CloudExperienceHostAPI::IMediaAccessPolicyHelper,CloudExperienceHostAPI::ISystemInformation,CloudExperienceHostAPI::IWwanHelper,CloudExperienceHostAPI::ILogonStatsHelper,CloudExperienceHostAPI::IOobeDriverInstaller,CloudExperienceHostAPI::IKeyboardInjectionHelper>>,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 20;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x1800a1980  mov     [rsp+arg_0], rbx
0x1800a1985  push    rdi
0x1800a1986  sub     rsp, 20h
0x1800a198a  mov     qword ptr [r8], 0
0x1800a1991  mov     ecx, 140h; cb
0x1800a1996  mov     dword ptr [rdx], 0
0x1800a199c  mov     rbx, r8
0x1800a199f  mov     rdi, rdx
0x1800a19a2  call    cs:__imp_CoTaskMemAlloc
0x1800a19a8  mov     r8, rax
0x1800a19ab  test    rax, rax
0x1800a19ae  jnz     short loc_1800A19B7
0x1800a19b0  mov     eax, 8007000Eh
0x1800a19b5  jmp     short loc_1800A19DF
0x1800a19b7  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x1800a19be  lea     rdx, [rsp+28h+arg_8]
0x1800a19c3  mov     [rsp+28h+arg_8], 1
0x1800a19cb  movdqu  xmmword ptr [rax], xmm0
0x1800a19cf  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$00U?$ImplementsMarker@U?$Implements@UILicensingPolicyHelper@CloudExperienceHostAPI@@UINetworkingHelper@2@UIOobeHelper@2@UIOobeHelper2@2@UIOobeDataHelper@2@UISystemPowerHelper@2@UIWebAuthHelper@2@UINavigationAccessPolicyHelper@2@UIHtmlFileHelper@2@UITimeZoneHelper@2@UIWnfSynchronization@2@UIAppPackageHelper@2@UIFlightDataHelper@2@UIMediaAccessPolicyHelper@2@UISystemInformation@2@UIWwanHelper@2@UILogonStatsHelper@2@UIOobeDriverInstaller@2@UIKeyboardInjectionHelper@2@@WRL@Microsoft@@@Details@23@VFtmBase@23@VNil@523@V7523@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<CloudExperienceHostAPI::ILicensingPolicyHelper,CloudExperienceHostAPI::INetworkingHelper,CloudExperienceHostAPI::IOobeHelper,CloudExperienceHostAPI::IOobeHelper2,CloudExperienceHostAPI::IOobeDataHelper,CloudExperienceHostAPI::ISystemPowerHelper,CloudExperienceHostAPI::IWebAuthHelper,CloudExperienceHostAPI::INavigationAccessPolicyHelper,CloudExperienceHostAPI::IHtmlFileHelper,CloudExperienceHostAPI::ITimeZoneHelper,CloudExperienceHostAPI::IWnfSynchronization,CloudExperienceHostAPI::IAppPackageHelper,CloudExperienceHostAPI::IFlightDataHelper,CloudExperienceHostAPI::IMediaAccessPolicyHelper,CloudExperienceHostAPI::ISystemInformation,CloudExperienceHostAPI::IWwanHelper,CloudExperienceHostAPI::ILogonStatsHelper,CloudExperienceHostAPI::IOobeDriverInstaller,CloudExperienceHostAPI::IKeyboardInjectionHelper>>,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x1800a19d4  mov     dword ptr [rdi], 14h
0x1800a19da  xor     eax, eax
0x1800a19dc  mov     [rbx], r8
0x1800a19df  mov     rbx, [rsp+28h+arg_0]
0x1800a19e4  add     rsp, 20h
0x1800a19e8  pop     rdi
0x1800a19e9  retn
```
