# AppInstallItemTracker::AppInstallItemTracker(std::shared_ptr<GlobalTrackerWithTimeoutAndCancel>,Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem>)

- ea: `0x18001abe4`
- end: `0x18001ae3d`
- name: `??0AppInstallItemTracker@@QEAA@V?$shared_ptr@VGlobalTrackerWithTimeoutAndCancel@@@std@@V?$ComPtr@UIAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Z`
- size: `601`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180019f10`

## callees

- `0x18000760c`
- `0x18000b50c`
- `0x180010150`
- `0x1800109dc`
- `0x180012f10`
- `0x180015074`
- `0x18001ab40`
- `0x18001abe4`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ad09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ad09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ad4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ad4c`

## string_xrefs

- `0x18001ad34`: `onecoreuap\enduser\winstore\installservice\lib\downloadandinstallpendingupdatesworker.cpp`
- `0x18001ad8a`: `onecoreuap\enduser\winstore\installservice\lib\downloadandinstallpendingupdatesworker.cpp`
- `0x18001adc4`: `onecoreuap\enduser\winstore\installservice\lib\downloadandinstallpendingupdatesworker.cpp`
- `0x18001ae02`: `onecoreuap\enduser\winstore\installservice\lib\downloadandinstallpendingupdatesworker.cpp`
- `0x18001ad7d`: `AppInstallItemTracker::AppInstallItemTracker`

## pseudocode

```c
_QWORD *__fastcall AppInstallItemTracker::AppInstallItemTracker(_QWORD *a1, __int64 a2, __int64 *a3)
{
  _QWORD *v6; // r14
  HSTRING *v7; // rbp
  __int64 v8; // rcx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD *); // rbx
  int v11; // eax
  int v12; // eax
  int v13; // eax
  std::_Ref_count_base *v14; // rcx
  int v16; // [rsp+20h] [rbp-68h]
  int v17; // [rsp+20h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  int v19; // [rsp+A8h] [rbp+20h] BYREF

  v6 = a1 + 1;
  a1[1] = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>(a1 + 3);
  a1[9] = 1;
  *a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable';
  *v6 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>'};
  a1[2] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>'};
  a1[3] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAgileObject>'};
  a1[4] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *a1 = &AppInstallItemTracker::`vftable';
  *v6 = &AppInstallItemTracker::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>'};
  a1[2] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>'};
  a1[3] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAgileObject>'};
  a1[4] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  std::shared_ptr<GlobalTrackerWithTimeoutAndCancel>::shared_ptr<GlobalTrackerWithTimeoutAndCancel>(a1 + 10, a2);
  v7 = (HSTRING *)(a1 + 12);
  a1[12] = 0;
  v19 = 1;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    a1 + 13,
    &v19);
  v8 = *a3;
  a1[16] = *a3;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  v9 = *a3;
  v10 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)*a3 + 48LL);
  WindowsDeleteString(*v7);
  *v7 = 0;
  v11 = v10(v9, a1 + 12);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAE,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\downloadandinstallpendingupdatesworker.cpp",
      (const char *)(unsigned int)v11,
      v16);
  WindowsGetStringRawBuffer(*v7, 0);
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\downloadandinstallpendingupdatesworker.cpp",
    0xAFu,
    "AppInstallItemTracker::AppInstallItemTracker",
    -1,
    L"Tracking ProductId: %s",
    0,
    0);
  v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD *))(*(_QWORD *)a1[16] + 112LL))(a1[16], v6, a1 + 15);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB0,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\downloadandinstallpendingupdatesworker.cpp",
      (const char *)(unsigned int)v12,
      v17);
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD *))(*(_QWORD *)a1[16] + 128LL))(a1[16], v6, a1 + 14);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB1,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\downloadandinstallpendingupdatesworker.cpp",
      (const char *)(unsigned int)v13,
      v17);
  v14 = *(std::_Ref_count_base **)(a2 + 8);
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a3);
  return a1;
}

```

## disassembly

```asm
0x18001abe4  mov     [rsp+arg_10], r8
0x18001abe9  mov     [rsp+arg_8], rdx
0x18001abee  mov     [rsp+arg_0], rcx
0x18001abf3  push    rbx
0x18001abf4  push    rbp
0x18001abf5  push    rsi
0x18001abf6  push    rdi
0x18001abf7  push    r13
0x18001abf9  push    r14
0x18001abfb  push    r15
0x18001abfd  sub     rsp, 50h
0x18001ac01  mov     r15, r8
0x18001ac04  mov     r13, rdx
0x18001ac07  mov     rsi, rcx
0x18001ac0a  lea     r14, [rcx+8]
0x18001ac0e  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>::`vftable'
0x18001ac15  mov     [r14], rax
0x18001ac18  lea     rcx, [r14+10h]
0x18001ac1c  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>(void)
0x18001ac21  mov     ebx, 1
0x18001ac26  mov     [rsi+48h], rbx
0x18001ac2a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$ITypedEventHandler@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'
0x18001ac31  mov     [rsi], rax
0x18001ac34  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$ITypedEventHandler@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ITypedEventHandler@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIInspectable@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>'}
0x18001ac3b  mov     [r14], rax
0x18001ac3e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$ITypedEventHandler@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>'}
0x18001ac45  mov     [rsi+10h], rax
0x18001ac49  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$ITypedEventHandler@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAgileObject@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAgileObject>'}
0x18001ac50  mov     [rsi+18h], rax
0x18001ac54  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$ITypedEventHandler@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001ac5b  mov     [rsi+20h], rax
0x18001ac5f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001ac66  test    rcx, rcx
0x18001ac69  jz      short loc_18001AC78
0x18001ac6b  mov     rax, [rcx]
0x18001ac6e  mov     rax, [rax+8]
0x18001ac72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac77  nop
0x18001ac78  lea     rax, ??_7AppInstallItemTracker@@6B@; const AppInstallItemTracker::`vftable'
0x18001ac7f  mov     [rsi], rax
0x18001ac82  lea     rax, ??_7AppInstallItemTracker@@6B?$ITypedEventHandler@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIInspectable@@@Foundation@Windows@@@; const AppInstallItemTracker::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>'}
0x18001ac89  mov     [r14], rax
0x18001ac8c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$ITypedEventHandler@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>'}
0x18001ac93  mov     [rsi+10h], rax
0x18001ac97  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$ITypedEventHandler@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAgileObject@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAgileObject>'}
0x18001ac9e  mov     [rsi+18h], rax
0x18001aca2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$ITypedEventHandler@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001aca9  mov     [rsi+20h], rax
0x18001acad  lea     rcx, [rsi+50h]
0x18001acb1  mov     rdx, r13
0x18001acb4  call    ??0?$shared_ptr@VGlobalTrackerWithTimeoutAndCancel@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<GlobalTrackerWithTimeoutAndCancel>::shared_ptr<GlobalTrackerWithTimeoutAndCancel>(std::shared_ptr<GlobalTrackerWithTimeoutAndCancel> const &)
0x18001acb9  nop
0x18001acba  lea     rbp, [rsi+60h]
0x18001acbe  mov     qword ptr [rbp+0], 0
0x18001acc6  mov     [rsp+88h+arg_18], ebx
0x18001accd  lea     rcx, [rsi+68h]
0x18001acd1  lea     rdx, [rsp+88h+arg_18]
0x18001acd9  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x18001acde  nop
0x18001acdf  mov     rcx, [r15]
0x18001ace2  mov     [rsi+80h], rcx
0x18001ace9  test    rcx, rcx
0x18001acec  jz      short loc_18001ACFB
0x18001acee  mov     rax, [rcx]
0x18001acf1  mov     rax, [rax+8]
0x18001acf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acfa  nop
0x18001acfb  mov     rdi, [r15]
0x18001acfe  mov     rax, [rdi]
0x18001ad01  mov     rbx, [rax+30h]
0x18001ad05  mov     rcx, [rbp+0]; string
0x18001ad09  call    cs:__imp_WindowsDeleteString
0x18001ad0f  mov     qword ptr [rbp+0], 0
0x18001ad17  mov     rdx, rbp
0x18001ad1a  mov     rcx, rdi
0x18001ad1d  mov     rax, rbx
0x18001ad20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad25  mov     rcx, [rsp+88h]; this
0x18001ad2d  test    eax, eax
0x18001ad2f  jns     short loc_18001AD46
0x18001ad31  mov     r9d, eax; char *
0x18001ad34  lea     r8, aOnecoreuapEndu_10; "onecoreuap\\enduser\\winstore\\installs"...
0x18001ad3b  mov     edx, 0AEh; void *
0x18001ad40  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ad46  xor     edx, edx; length
0x18001ad48  mov     rcx, [rbp+0]; string
0x18001ad4c  call    cs:__imp_WindowsGetStringRawBuffer
0x18001ad52  mov     [rsp+88h+var_48], rax
0x18001ad57  mov     [rsp+88h+var_50], 0; unsigned __int16 *
0x18001ad60  mov     [rsp+88h+var_58], 0; char *
0x18001ad69  lea     rax, aTrackingProduc; "Tracking ProductId: %s"
0x18001ad70  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x18001ad75  mov     [rsp+88h+var_68], 0FFFFFFFFh; int
0x18001ad7d  lea     r9, aAppinstallitem_1; "AppInstallItemTracker::AppInstallItemTr"...
0x18001ad84  mov     r8d, 0AFh; unsigned int
0x18001ad8a  lea     rdx, aOnecoreuapEndu_10; "onecoreuap\\enduser\\winstore\\installs"...
0x18001ad91  mov     ecx, 3; unsigned int
0x18001ad96  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18001ad9b  mov     rcx, [rsi+80h]
0x18001ada2  mov     rax, [rcx]
0x18001ada5  lea     r8, [rsi+78h]
0x18001ada9  mov     rdx, r14
0x18001adac  mov     rax, [rax+70h]
0x18001adb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001adb5  mov     rcx, [rsp+88h]; this
0x18001adbd  test    eax, eax
0x18001adbf  jns     short loc_18001ADD6
0x18001adc1  mov     r9d, eax; char *
0x18001adc4  lea     r8, aOnecoreuapEndu_10; "onecoreuap\\enduser\\winstore\\installs"...
0x18001adcb  mov     edx, 0B0h; void *
0x18001add0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001add6  mov     rcx, [rsi+80h]
0x18001addd  mov     rax, [rcx]
0x18001ade0  lea     r8, [rsi+70h]
0x18001ade4  mov     rdx, r14
0x18001ade7  mov     rax, [rax+80h]
0x18001adee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001adf3  mov     rcx, [rsp+88h]; this
0x18001adfb  test    eax, eax
0x18001adfd  jns     short loc_18001AE14
0x18001adff  mov     r9d, eax; char *
0x18001ae02  lea     r8, aOnecoreuapEndu_10; "onecoreuap\\enduser\\winstore\\installs"...
0x18001ae09  mov     edx, 0B1h; void *
0x18001ae0e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ae14  mov     rcx, [r13+8]; this
0x18001ae18  test    rcx, rcx
0x18001ae1b  jz      short loc_18001AE23
0x18001ae1d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001ae22  nop
0x18001ae23  mov     rcx, r15
0x18001ae26  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ae2b  mov     rax, rsi
0x18001ae2e  add     rsp, 50h
0x18001ae32  pop     r15
0x18001ae34  pop     r14
0x18001ae36  pop     r13
0x18001ae38  pop     rdi
0x18001ae39  pop     rsi
0x18001ae3a  pop     rbp
0x18001ae3b  pop     rbx
0x18001ae3c  retn
```
