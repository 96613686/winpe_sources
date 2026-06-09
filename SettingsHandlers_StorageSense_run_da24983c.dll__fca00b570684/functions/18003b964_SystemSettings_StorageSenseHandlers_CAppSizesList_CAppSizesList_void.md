# SystemSettings::StorageSenseHandlers::CAppSizesList::~CAppSizesList(void)

- ea: `0x18003b964`
- end: `0x18003bbef`
- name: `??1CAppSizesList@StorageSenseHandlers@SystemSettings@@UEAA@XZ`
- size: `651`
- prototype: `void __fastcall(SystemSettings::StorageSenseHandlers::CAppSizesList *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003ccc0`
- `0x180071838`

## callees

- `0x18000c964`
- `0x180017cdc`
- `0x1800292a8`
- `0x1800343ec`
- `0x18003b5d0`
- `0x18003b964`
- `0x180046474`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003bac4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003bad1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003bac4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003bad1`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x18003baac`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x18003baac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bade`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003baf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bbc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bade`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003baf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bbc0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003ba0b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003ba0b`

## pseudocode

```c
void __fastcall SystemSettings::StorageSenseHandlers::CAppSizesList::~CAppSizesList(
        SystemSettings::StorageSenseHandlers::CAppSizesList *this)
{
  char *v2; // r15
  char *v3; // r12
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  *(_QWORD *)this = &SystemSettings::StorageSenseHandlers::CAppSizesList::`vftable'{for `SystemSettings::DataModel::ISettingItem'};
  *((_QWORD *)this + 1) = &SystemSettings::StorageSenseHandlers::CAppSizesList::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &SystemSettings::StorageSenseHandlers::CAppSizesList::`vftable'{for `SystemSettings::DataModel::ISettingItemTelemetry'};
  *((_QWORD *)this + 3) = &SystemSettings::StorageSenseHandlers::CAppSizesList::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 4) = &SystemSettings::StorageSenseHandlers::CAppSizesList::`vftable'{for `SystemSettings::DataModel::ISettingItem2'};
  *((_QWORD *)this + 5) = &SystemSettings::StorageSenseHandlers::CAppSizesList::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v2 = (char *)this + 232;
  *((_QWORD *)this + 29) = &SystemSettings::StorageSenseHandlers::CAppSizesList::`vftable'{for `SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback'};
  *((_QWORD *)this + 33) = &SystemSettings::StorageSenseHandlers::CAppSizesList::`vftable'{for `SystemSettings::DataModel::CSingletonHelper<unsigned char *>::CNoCallback'};
  *((_QWORD *)this + 37) = &SystemSettings::StorageSenseHandlers::CAppSizesList::`vftable'{for `SystemSettings::StorageSenseHandlers::CAppEnumerationMode'};
  v3 = (char *)this + 320;
  *((_QWORD *)this + 40) = &SystemSettings::StorageSenseHandlers::CAppSizesList::`vftable'{for `SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppLayoutChangedNotification *>::CCallback'};
  *((_BYTE *)this + 1032) = 1;
  while ( _InterlockedCompareExchange((volatile signed __int32 *)this + 266, 0, 0) )
    Sleep(0x64u);
  v4 = *((_QWORD *)this + 112);
  if ( v4 )
  {
    SystemSettings::DataModel::CSingletonHelper<unsigned char *>::Unregister(v4, (char *)this + 856);
    *((_QWORD *)this + 112) = 0;
  }
  v5 = *((_QWORD *)this + 119);
  if ( v5 )
  {
    SystemSettings::DataModel::CSingletonHelper<unsigned char *>::Unregister(v5, (char *)this + 912);
    *((_QWORD *)this + 119) = 0;
  }
  v6 = *((_QWORD *)this + 126);
  if ( v6 )
  {
    SystemSettings::DataModel::CSingletonHelper<unsigned char *>::Unregister(v6, (char *)this + 968);
    *((_QWORD *)this + 126) = 0;
  }
  SystemSettings::DataModel::CSingletonHelper<unsigned char *>::Unregister((char *)this + 360, v2);
  SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::RecommendationNotificationBase> const &>::Unregister(
    *((_QWORD *)this + 98),
    v3);
  if ( *((_QWORD *)this + 44) )
  {
    CoDecrementMTAUsage();
    *((_QWORD *)this + 44) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1112));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1072));
  WindowsDeleteString(*((HSTRING *)this + 132));
  *((_QWORD *)this + 132) = 0;
  WindowsDeleteString(*((HSTRING *)this + 131));
  *((_QWORD *)this + 131) = 0;
  *((_QWORD *)this + 121) = &SystemSettings::StorageSenseHandlers::CAppSizesList::DriveListener::`vftable';
  WindowsDeleteString(*((HSTRING *)this + 125));
  *((_QWORD *)this + 125) = 0;
  *((_QWORD *)this + 114) = &SystemSettings::StorageSenseHandlers::CAppSizesList::FilterListener::`vftable';
  WindowsDeleteString(*((HSTRING *)this + 118));
  *((_QWORD *)this + 118) = 0;
  *((_QWORD *)this + 107) = &SystemSettings::StorageSenseHandlers::CAppSizesList::SortListener::`vftable';
  WindowsDeleteString(*((HSTRING *)this + 111));
  *((_QWORD *)this + 111) = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)this + 848);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease((char *)this + 840);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease((char *)this + 832);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease((char *)this + 824);
  WindowsDeleteString(*((HSTRING *)this + 101));
  *((_QWORD *)this + 101) = 0;
  SystemSettings::StorageSenseHandlers::CAppListHelper::~CAppListHelper((SystemSettings::StorageSenseHandlers::CAppSizesList *)((char *)this + 360));
  *((_QWORD *)this + 37) = &SystemSettings::StorageSenseHandlers::CAppEnumerationMode::`vftable';
  WindowsDeleteString(*((HSTRING *)this + 38));
  *((_QWORD *)this + 38) = 0;
  SystemSettings::DataModel::CCollectionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::~CCollectionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>(this);
}

```

## disassembly

```asm
0x18003b964  mov     [rsp+arg_8], rbx
0x18003b969  mov     [rsp+arg_10], rbp
0x18003b96e  push    rsi
0x18003b96f  push    rdi
0x18003b970  push    r12
0x18003b972  push    r14
0x18003b974  push    r15
0x18003b976  sub     rsp, 20h
0x18003b97a  mov     rbx, rcx
0x18003b97d  lea     rax, ??_7CAppSizesList@StorageSenseHandlers@SystemSettings@@6BISettingItem@DataModel@2@@; const SystemSettings::StorageSenseHandlers::CAppSizesList::`vftable'{for `SystemSettings::DataModel::ISettingItem'}
0x18003b984  mov     [rcx], rax
0x18003b987  lea     rax, ??_7CAppSizesList@StorageSenseHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UISettingItemTelemetry@DataModel@SystemSettings@@UISettingsAppNotification@67@UISettingItem2@67@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::StorageSenseHandlers::CAppSizesList::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x18003b98e  mov     [rcx+8], rax
0x18003b992  lea     rax, ??_7CAppSizesList@StorageSenseHandlers@SystemSettings@@6BISettingItemTelemetry@DataModel@2@@; const SystemSettings::StorageSenseHandlers::CAppSizesList::`vftable'{for `SystemSettings::DataModel::ISettingItemTelemetry'}
0x18003b999  mov     [rcx+10h], rax
0x18003b99d  lea     rax, ??_7CAppSizesList@StorageSenseHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UISettingsAppNotification@DataModel@SystemSettings@@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::StorageSenseHandlers::CAppSizesList::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x18003b9a4  mov     [rcx+18h], rax
0x18003b9a8  lea     rax, ??_7CAppSizesList@StorageSenseHandlers@SystemSettings@@6BISettingItem2@DataModel@2@@; const SystemSettings::StorageSenseHandlers::CAppSizesList::`vftable'{for `SystemSettings::DataModel::ISettingItem2'}
0x18003b9af  mov     [rcx+20h], rax
0x18003b9b3  lea     rax, ??_7CAppSizesList@StorageSenseHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const SystemSettings::StorageSenseHandlers::CAppSizesList::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003b9ba  mov     [rcx+28h], rax
0x18003b9be  lea     r15, [rcx+0E8h]
0x18003b9c5  lea     rax, ??_7CAppSizesList@StorageSenseHandlers@SystemSettings@@6BCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@2@@; const SystemSettings::StorageSenseHandlers::CAppSizesList::`vftable'{for `SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback'}
0x18003b9cc  mov     [r15], rax
0x18003b9cf  lea     rax, ??_7CAppSizesList@StorageSenseHandlers@SystemSettings@@6BCNoCallback@?$CSingletonHelper@PEAE@DataModel@2@@; const SystemSettings::StorageSenseHandlers::CAppSizesList::`vftable'{for `SystemSettings::DataModel::CSingletonHelper<uchar *>::CNoCallback'}
0x18003b9d6  mov     [rcx+108h], rax
0x18003b9dd  lea     rax, ??_7CAppSizesList@StorageSenseHandlers@SystemSettings@@6BCAppEnumerationMode@12@@; const SystemSettings::StorageSenseHandlers::CAppSizesList::`vftable'{for `SystemSettings::StorageSenseHandlers::CAppEnumerationMode'}
0x18003b9e4  mov     [rcx+128h], rax
0x18003b9eb  lea     r12, [rcx+140h]
0x18003b9f2  lea     rax, ??_7CAppSizesList@StorageSenseHandlers@SystemSettings@@6BCCallback@?$CSingletonHelper@PEAUAppLayoutChangedNotification@StorageSenseHandlers@SystemSettings@@@DataModel@2@@; const SystemSettings::StorageSenseHandlers::CAppSizesList::`vftable'{for `SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppLayoutChangedNotification *>::CCallback'}
0x18003b9f9  mov     [r12], rax
0x18003b9fd  mov     byte ptr [rcx+408h], 1
0x18003ba04  jmp     short loc_18003BA11
0x18003ba06  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18003ba0b  call    cs:__imp_Sleep
0x18003ba11  xor     ecx, ecx
0x18003ba13  xor     eax, eax
0x18003ba15  lock cmpxchg [rbx+428h], ecx
0x18003ba1d  jnz     short loc_18003BA06
0x18003ba1f  lea     rdi, [rbx+358h]
0x18003ba26  mov     rcx, [rdi+28h]
0x18003ba2a  test    rcx, rcx
0x18003ba2d  jz      short loc_18003BA3F
0x18003ba2f  mov     rdx, rdi
0x18003ba32  call    ?Unregister@?$CSingletonHelper@PEAE@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z; SystemSettings::DataModel::CSingletonHelper<uchar *>::Unregister(SystemSettings::DataModel::CSingletonHelper<uchar *>::CCallback *)
0x18003ba37  mov     qword ptr [rdi+28h], 0
0x18003ba3f  lea     rsi, [rbx+390h]
0x18003ba46  mov     rcx, [rsi+28h]
0x18003ba4a  test    rcx, rcx
0x18003ba4d  jz      short loc_18003BA5F
0x18003ba4f  mov     rdx, rsi
0x18003ba52  call    ?Unregister@?$CSingletonHelper@PEAE@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z; SystemSettings::DataModel::CSingletonHelper<uchar *>::Unregister(SystemSettings::DataModel::CSingletonHelper<uchar *>::CCallback *)
0x18003ba57  mov     qword ptr [rsi+28h], 0
0x18003ba5f  lea     r14, [rbx+3C8h]
0x18003ba66  mov     rcx, [r14+28h]
0x18003ba6a  test    rcx, rcx
0x18003ba6d  jz      short loc_18003BA7F
0x18003ba6f  mov     rdx, r14
0x18003ba72  call    ?Unregister@?$CSingletonHelper@PEAE@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z; SystemSettings::DataModel::CSingletonHelper<uchar *>::Unregister(SystemSettings::DataModel::CSingletonHelper<uchar *>::CCallback *)
0x18003ba77  mov     qword ptr [r14+28h], 0
0x18003ba7f  lea     rbp, [rbx+168h]
0x18003ba86  mov     rdx, r15
0x18003ba89  mov     rcx, rbp
0x18003ba8c  call    ?Unregister@?$CSingletonHelper@PEAE@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z; SystemSettings::DataModel::CSingletonHelper<uchar *>::Unregister(SystemSettings::DataModel::CSingletonHelper<uchar *>::CCallback *)
0x18003ba91  mov     rdx, r12
0x18003ba94  mov     rcx, [rbx+310h]
0x18003ba9b  call    ?Unregister@?$CSingletonHelper@AEBV?$shared_ptr@URecommendationNotificationBase@StorageSenseHandlers@SystemSettings@@@std@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z; SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::RecommendationNotificationBase> const &>::Unregister(SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::RecommendationNotificationBase> const &>::CCallback *)
0x18003baa0  mov     rcx, [rbx+160h]
0x18003baa7  test    rcx, rcx
0x18003baaa  jz      short loc_18003BABD
0x18003baac  call    cs:__imp_CoDecrementMTAUsage
0x18003bab2  mov     qword ptr [rbx+160h], 0
0x18003babd  lea     rcx, [rbx+458h]; lpCriticalSection
0x18003bac4  call    cs:__imp_DeleteCriticalSection
0x18003baca  lea     rcx, [rbx+430h]; lpCriticalSection
0x18003bad1  call    cs:__imp_DeleteCriticalSection
0x18003bad7  mov     rcx, [rbx+420h]; string
0x18003bade  call    cs:__imp_WindowsDeleteString
0x18003bae4  mov     qword ptr [rbx+420h], 0
0x18003baef  mov     rcx, [rbx+418h]; string
0x18003baf6  call    cs:__imp_WindowsDeleteString
0x18003bafc  mov     qword ptr [rbx+418h], 0
0x18003bb07  lea     rax, ??_7DriveListener@CAppSizesList@StorageSenseHandlers@SystemSettings@@6B@; const SystemSettings::StorageSenseHandlers::CAppSizesList::DriveListener::`vftable'
0x18003bb0e  mov     [r14], rax
0x18003bb11  mov     rcx, [r14+20h]; string
0x18003bb15  call    cs:__imp_WindowsDeleteString
0x18003bb1b  mov     qword ptr [r14+20h], 0
0x18003bb23  lea     rax, ??_7FilterListener@CAppSizesList@StorageSenseHandlers@SystemSettings@@6B@; const SystemSettings::StorageSenseHandlers::CAppSizesList::FilterListener::`vftable'
0x18003bb2a  mov     [rsi], rax
0x18003bb2d  mov     rcx, [rsi+20h]; string
0x18003bb31  call    cs:__imp_WindowsDeleteString
0x18003bb37  mov     qword ptr [rsi+20h], 0
0x18003bb3f  lea     rax, ??_7SortListener@CAppSizesList@StorageSenseHandlers@SystemSettings@@6B@; const SystemSettings::StorageSenseHandlers::CAppSizesList::SortListener::`vftable'
0x18003bb46  mov     [rdi], rax
0x18003bb49  mov     rcx, [rdi+20h]; string
0x18003bb4d  call    cs:__imp_WindowsDeleteString
0x18003bb53  mov     qword ptr [rdi+20h], 0
0x18003bb5b  lea     rcx, [rbx+350h]
0x18003bb62  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003bb67  lea     rcx, [rbx+348h]
0x18003bb6e  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18003bb73  lea     rcx, [rbx+340h]
0x18003bb7a  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18003bb7f  lea     rcx, [rbx+338h]
0x18003bb86  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18003bb8b  mov     rcx, [rbx+328h]; string
0x18003bb92  call    cs:__imp_WindowsDeleteString
0x18003bb98  mov     qword ptr [rbx+328h], 0
0x18003bba3  mov     rcx, rbp; this
0x18003bba6  call    ??1CAppListHelper@StorageSenseHandlers@SystemSettings@@UEAA@XZ; SystemSettings::StorageSenseHandlers::CAppListHelper::~CAppListHelper(void)
0x18003bbab  lea     rax, ??_7CAppEnumerationMode@StorageSenseHandlers@SystemSettings@@6B@; const SystemSettings::StorageSenseHandlers::CAppEnumerationMode::`vftable'
0x18003bbb2  mov     [rbx+128h], rax
0x18003bbb9  mov     rcx, [rbx+130h]; string
0x18003bbc0  call    cs:__imp_WindowsDeleteString
0x18003bbc6  mov     qword ptr [rbx+130h], 0
0x18003bbd1  mov     rcx, rbx; this
0x18003bbd4  mov     rbx, [rsp+48h+arg_8]
0x18003bbd9  mov     rbp, [rsp+48h+arg_10]
0x18003bbde  add     rsp, 20h
0x18003bbe2  pop     r15
0x18003bbe4  pop     r14
0x18003bbe6  pop     r12
0x18003bbe8  pop     rdi
0x18003bbe9  pop     rsi
0x18003bbea  jmp     ??1?$CCollectionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAA@XZ; SystemSettings::DataModel::CCollectionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::~CCollectionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>(void)
```
