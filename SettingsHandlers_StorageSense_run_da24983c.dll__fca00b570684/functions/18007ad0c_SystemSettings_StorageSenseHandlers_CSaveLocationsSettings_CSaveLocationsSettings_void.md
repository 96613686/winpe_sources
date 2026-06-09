# SystemSettings::StorageSenseHandlers::CSaveLocationsSettings::~CSaveLocationsSettings(void)

- ea: `0x18007ad0c`
- end: `0x18007adee`
- name: `??1CSaveLocationsSettings@StorageSenseHandlers@SystemSettings@@UEAA@XZ`
- size: `226`
- prototype: `void __fastcall(SystemSettings::StorageSenseHandlers::CSaveLocationsSettings *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007ae40`

## callees

- `0x18000c964`
- `0x180017d04`
- `0x18001f53c`
- `0x180046988`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007adc0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007adc9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007adc0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007adc9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ad9a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ad9a`

## pseudocode

```c
void __fastcall SystemSettings::StorageSenseHandlers::CSaveLocationsSettings::~CSaveLocationsSettings(
        SystemSettings::StorageSenseHandlers::CSaveLocationsSettings *this)
{
  char *v2; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &SystemSettings::StorageSenseHandlers::CSaveLocationsSettings::`vftable'{for `SystemSettings::DataModel::ISettingItem'};
  *((_QWORD *)this + 1) = &SystemSettings::StorageSenseHandlers::CSaveLocationsSettings::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &SystemSettings::StorageSenseHandlers::CSaveLocationsSettings::`vftable'{for `SystemSettings::DataModel::ISettingItemTelemetry'};
  *((_QWORD *)this + 3) = &SystemSettings::StorageSenseHandlers::CSaveLocationsSettings::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 4) = &SystemSettings::StorageSenseHandlers::CSaveLocationsSettings::`vftable'{for `SystemSettings::DataModel::ISettingItem2'};
  *((_QWORD *)this + 5) = &SystemSettings::StorageSenseHandlers::CSaveLocationsSettings::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 26) = &SystemSettings::StorageSenseHandlers::CSaveLocationsSettings::`vftable';
  SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::StorageSenseHandlers::VolumeUpdateNotification>::Unregister(
    this,
    ((unsigned __int64)this + 208) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease((char *)this + 1288);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1296));
  v2 = (char *)this + 1296;
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v2);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1336));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1296));
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease((char *)this + 1288);
  SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::~CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>(this);
}

```

## disassembly

```asm
0x18007ad0c  mov     [rsp+arg_8], rbx
0x18007ad11  mov     [rsp+arg_10], rsi
0x18007ad16  push    rdi
0x18007ad17  sub     rsp, 20h
0x18007ad1b  mov     rsi, rcx
0x18007ad1e  lea     rax, ??_7CSaveLocationsSettings@StorageSenseHandlers@SystemSettings@@6BISettingItem@DataModel@2@@; const SystemSettings::StorageSenseHandlers::CSaveLocationsSettings::`vftable'{for `SystemSettings::DataModel::ISettingItem'}
0x18007ad25  mov     [rcx], rax
0x18007ad28  lea     rax, ??_7CSaveLocationsSettings@StorageSenseHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UISettingItemTelemetry@DataModel@SystemSettings@@UISettingsAppNotification@67@UISettingItem2@67@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::StorageSenseHandlers::CSaveLocationsSettings::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x18007ad2f  mov     [rcx+8], rax
0x18007ad33  lea     rax, ??_7CSaveLocationsSettings@StorageSenseHandlers@SystemSettings@@6BISettingItemTelemetry@DataModel@2@@; const SystemSettings::StorageSenseHandlers::CSaveLocationsSettings::`vftable'{for `SystemSettings::DataModel::ISettingItemTelemetry'}
0x18007ad3a  mov     [rcx+10h], rax
0x18007ad3e  lea     rax, ??_7CSaveLocationsSettings@StorageSenseHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UISettingsAppNotification@DataModel@SystemSettings@@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::StorageSenseHandlers::CSaveLocationsSettings::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x18007ad45  mov     [rcx+18h], rax
0x18007ad49  lea     rax, ??_7CSaveLocationsSettings@StorageSenseHandlers@SystemSettings@@6BISettingItem2@DataModel@2@@; const SystemSettings::StorageSenseHandlers::CSaveLocationsSettings::`vftable'{for `SystemSettings::DataModel::ISettingItem2'}
0x18007ad50  mov     [rcx+20h], rax
0x18007ad54  lea     rax, ??_7CSaveLocationsSettings@StorageSenseHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const SystemSettings::StorageSenseHandlers::CSaveLocationsSettings::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18007ad5b  mov     [rcx+28h], rax
0x18007ad5f  lea     r8, [rcx+0D0h]
0x18007ad66  lea     rax, ??_7CSaveLocationsSettings@StorageSenseHandlers@SystemSettings@@6B@; const SystemSettings::StorageSenseHandlers::CSaveLocationsSettings::`vftable'
0x18007ad6d  mov     [r8], rax
0x18007ad70  mov     rax, rcx
0x18007ad73  neg     rax
0x18007ad76  sbb     rdx, rdx
0x18007ad79  and     rdx, r8
0x18007ad7c  call    ?Unregister@?$CSingletonHelper@W4VolumeUpdateNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::VolumeUpdateNotification>::Unregister(SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::VolumeUpdateNotification>::CCallback *)
0x18007ad81  lea     rdi, [rsi+508h]
0x18007ad88  mov     rcx, rdi
0x18007ad8b  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18007ad90  lea     rbx, [rsi+510h]
0x18007ad97  mov     rcx, rbx; lpCriticalSection
0x18007ad9a  call    cs:__imp_EnterCriticalSection
0x18007ada0  mov     [rsp+28h+arg_0], rbx
0x18007ada5  lea     rcx, [rsp+28h+arg_0]; this
0x18007adaa  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18007adaf  lea     rcx, [rsp+28h+arg_0]; this
0x18007adb4  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18007adb9  lea     rcx, [rsi+538h]; lpCriticalSection
0x18007adc0  call    cs:__imp_DeleteCriticalSection
0x18007adc6  mov     rcx, rbx; lpCriticalSection
0x18007adc9  call    cs:__imp_DeleteCriticalSection
0x18007adcf  mov     rcx, rdi
0x18007add2  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18007add7  mov     rcx, rsi; this
0x18007adda  mov     rbx, [rsp+28h+arg_8]
0x18007addf  mov     rsi, [rsp+28h+arg_10]
0x18007ade4  add     rsp, 20h
0x18007ade8  pop     rdi
0x18007ade9  jmp     ??1?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAUIUser@System@Windows@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAA@XZ; SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::~CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>(void)
```
