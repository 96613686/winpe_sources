# AppInstallItemTracker::~AppInstallItemTracker(void)

- ea: `0x18001b74c`
- end: `0x18001b7d2`
- name: `??1AppInstallItemTracker@@UEAA@XZ`
- size: `134`
- prototype: `void __fastcall(AppInstallItemTracker *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001c090`

## callees

- `0x180005c74`
- `0x18000760c`
- `0x1800109dc`
- `0x1800155f4`
- `0x18001b74c`
- `0x18001c43c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b7a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b7a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AppInstallItemTracker::~AppInstallItemTracker(AppInstallItemTracker *this)
{
  void *v2; // rdx
  std::_Ref_count_base *v3; // rcx

  *(_QWORD *)this = &AppInstallItemTracker::`vftable';
  *((_QWORD *)this + 1) = &AppInstallItemTracker::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>'};
  *((_QWORD *)this + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 3) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAgileObject>'};
  *((_QWORD *)this + 4) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  AppInstallItemTracker::Cleanup(this);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 128);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    (wil::details **)this + 13,
    v2);
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 11);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>((__int64)this);
}

```

## disassembly

```asm
0x18001b74c  push    rbx
0x18001b74e  sub     rsp, 20h
0x18001b752  lea     rax, ??_7AppInstallItemTracker@@6B@; const AppInstallItemTracker::`vftable'
0x18001b759  mov     rbx, rcx
0x18001b75c  mov     [rcx], rax
0x18001b75f  lea     rax, ??_7AppInstallItemTracker@@6B?$ITypedEventHandler@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIInspectable@@@Foundation@Windows@@@; const AppInstallItemTracker::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>'}
0x18001b766  mov     [rcx+8], rax
0x18001b76a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$ITypedEventHandler@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>'}
0x18001b771  mov     [rcx+10h], rax
0x18001b775  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$ITypedEventHandler@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAgileObject@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAgileObject>'}
0x18001b77c  mov     [rcx+18h], rax
0x18001b780  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$ITypedEventHandler@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001b787  mov     [rcx+20h], rax
0x18001b78b  call    ?Cleanup@AppInstallItemTracker@@QEAAXXZ; AppInstallItemTracker::Cleanup(void)
0x18001b790  lea     rcx, [rbx+80h]
0x18001b797  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b79c  lea     rcx, [rbx+68h]
0x18001b7a0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001b7a5  mov     rcx, [rbx+60h]; string
0x18001b7a9  call    cs:__imp_WindowsDeleteString
0x18001b7af  mov     qword ptr [rbx+60h], 0
0x18001b7b7  mov     rcx, [rbx+58h]; this
0x18001b7bb  test    rcx, rcx
0x18001b7be  jz      short loc_18001B7C5
0x18001b7c0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001b7c5  mov     rcx, rbx
0x18001b7c8  add     rsp, 20h
0x18001b7cc  pop     rbx
0x18001b7cd  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$ITypedEventHandler@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>(void)
```
