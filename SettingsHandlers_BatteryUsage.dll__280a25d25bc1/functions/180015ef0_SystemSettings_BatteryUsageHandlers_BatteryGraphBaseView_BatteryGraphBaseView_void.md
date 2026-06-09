# SystemSettings::BatteryUsageHandlers::BatteryGraphBaseView::~BatteryGraphBaseView(void)

- ea: `0x180015ef0`
- end: `0x180016067`
- name: `??1BatteryGraphBaseView@BatteryUsageHandlers@SystemSettings@@UEAA@XZ`
- size: `375`
- prototype: `void __fastcall(SystemSettings::BatteryUsageHandlers::BatteryGraphBaseView *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800166d0`
- `0x180056cf8`

## callees

- `0x18000d4dc`
- `0x18000dda4`
- `0x180010cdc`
- `0x180015ef0`
- `0x18001e4e8`
- `0x18001e52c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015f7e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015f7e`

## pseudocode

```c
void __fastcall SystemSettings::BatteryUsageHandlers::BatteryGraphBaseView::~BatteryGraphBaseView(
        SystemSettings::BatteryUsageHandlers::BatteryGraphBaseView *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &SystemSettings::BatteryUsageHandlers::BatteryGraphBaseView::`vftable'{for `SystemSettings::DataModel::ISettingItem'};
  *((_QWORD *)this + 1) = &SystemSettings::BatteryUsageHandlers::AppList2::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CListSetting>::`vftable'{for `SystemSettings::DataModel::ISettingItemTelemetry'};
  *((_QWORD *)this + 3) = &SystemSettings::BatteryUsageHandlers::EnergyUsageGraphDayView::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 4) = &SystemSettings::BatteryUsageHandlers::DisplayTimeBase2::`vftable'{for `SystemSettings::DataModel::ISettingItem2'};
  *((_QWORD *)this + 5) = &SystemSettings::BatteryUsageHandlers::AppSearchFilter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 27) = &SystemSettings::BatteryUsageHandlers::BatteryGraphBaseView::`vftable';
  dword_18007A320 = -1;
  dword_18007A300 = 0;
  SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::Unregister(
    (__int64)&SystemSettings::BatteryUsageHandlers::g_BatteryGraphSingleton,
    ((unsigned __int64)this + 216) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64),
    (__int64)this + 216);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
  v2 = (void *)*((_QWORD *)this + 64);
  if ( v2 )
  {
    std::_Deallocate<16>(v2, (struct std::nothrow_t *)(8 * ((__int64)(*((_QWORD *)this + 66) - (_QWORD)v2) >> 3)));
    *((_QWORD *)this + 64) = 0;
    *((_QWORD *)this + 65) = 0;
    *((_QWORD *)this + 66) = 0;
  }
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>((__int64)this + 488);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>((__int64)this + 464);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>((__int64)this + 440);
  std::vector<int>::_Tidy((char *)this + 416);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>((__int64)this + 392);
  std::vector<int>::_Tidy((char *)this + 368);
  std::vector<int>::_Tidy((char *)this + 344);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>((__int64)this + 320);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>((__int64)this + 296);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>((__int64)this + 272);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>((__int64)this + 248);
  SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::~CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>(this);
}

```

## disassembly

```asm
0x180015ef0  push    rbx
0x180015ef2  sub     rsp, 20h
0x180015ef6  mov     rbx, rcx
0x180015ef9  lea     rax, ??_7BatteryGraphBaseView@BatteryUsageHandlers@SystemSettings@@6BISettingItem@DataModel@2@@; const SystemSettings::BatteryUsageHandlers::BatteryGraphBaseView::`vftable'{for `SystemSettings::DataModel::ISettingItem'}
0x180015f00  mov     [rcx], rax
0x180015f03  lea     rax, ??_7AppList2@BatteryUsageHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UISettingItemTelemetry@DataModel@SystemSettings@@UISettingsAppNotification@67@UISettingItem2@67@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::BatteryUsageHandlers::AppList2::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x180015f0a  mov     [rcx+8], rax
0x180015f0e  lea     rax, ??_7?$CGenericAsyncHelper@VCListSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@6BISettingItemTelemetry@12@@; const SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CListSetting>::`vftable'{for `SystemSettings::DataModel::ISettingItemTelemetry'}
0x180015f15  mov     [rcx+10h], rax
0x180015f19  lea     rax, ??_7EnergyUsageGraphDayView@BatteryUsageHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UISettingsAppNotification@DataModel@SystemSettings@@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::BatteryUsageHandlers::EnergyUsageGraphDayView::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x180015f20  mov     [rcx+18h], rax
0x180015f24  lea     rax, ??_7DisplayTimeBase2@BatteryUsageHandlers@SystemSettings@@6BISettingItem2@DataModel@2@@; const SystemSettings::BatteryUsageHandlers::DisplayTimeBase2::`vftable'{for `SystemSettings::DataModel::ISettingItem2'}
0x180015f2b  mov     [rcx+20h], rax
0x180015f2f  lea     rax, ??_7AppSearchFilter@BatteryUsageHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const SystemSettings::BatteryUsageHandlers::AppSearchFilter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180015f36  mov     [rcx+28h], rax
0x180015f3a  lea     r8, [rcx+0D8h]
0x180015f41  lea     rax, ??_7BatteryGraphBaseView@BatteryUsageHandlers@SystemSettings@@6B@; const SystemSettings::BatteryUsageHandlers::BatteryGraphBaseView::`vftable'
0x180015f48  mov     [r8], rax
0x180015f4b  mov     cs:dword_18007A320, 0FFFFFFFFh
0x180015f55  mov     cs:dword_18007A300, 0
0x180015f5f  mov     rax, rcx
0x180015f62  neg     rax
0x180015f65  sbb     rdx, rdx
0x180015f68  and     rdx, r8
0x180015f6b  lea     rcx, ?g_BatteryGraphSingleton@BatteryUsageHandlers@SystemSettings@@3VCBatteryGraphSingleton@12@A; SystemSettings::BatteryUsageHandlers::CBatteryGraphSingleton SystemSettings::BatteryUsageHandlers::g_BatteryGraphSingleton
0x180015f72  call    ?Unregister@?$CSingletonHelper@W4BatteryGraphNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::Unregister(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback *)
0x180015f77  lea     rcx, [rbx+238h]; lpCriticalSection
0x180015f7e  call    cs:__imp_DeleteCriticalSection
0x180015f84  mov     rcx, [rbx+200h]
0x180015f8b  test    rcx, rcx
0x180015f8e  jz      short loc_180015FD6
0x180015f90  mov     rax, [rbx+210h]
0x180015f97  sub     rax, rcx
0x180015f9a  sar     rax, 3
0x180015f9e  mov     rdx, 6DB6DB6DB6DB6DB7h
0x180015fa8  imul    rax, rdx
0x180015fac  imul    rdx, rax, 38h ; '8'
0x180015fb0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015fb5  mov     qword ptr [rbx+200h], 0
0x180015fc0  mov     qword ptr [rbx+208h], 0
0x180015fcb  mov     qword ptr [rbx+210h], 0
0x180015fd6  lea     rcx, [rbx+1E8h]
0x180015fdd  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUAppIdentity@BatteryUsageHandlers@SystemSettings@@V?$vector@UTimeRange@BatteryUsageHandlers@SystemSettings@@V?$allocator@UTimeRange@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>(void)
0x180015fe2  lea     rcx, [rbx+1D0h]
0x180015fe9  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUAppIdentity@BatteryUsageHandlers@SystemSettings@@V?$vector@UTimeRange@BatteryUsageHandlers@SystemSettings@@V?$allocator@UTimeRange@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>(void)
0x180015fee  lea     rcx, [rbx+1B8h]
0x180015ff5  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUAppIdentity@BatteryUsageHandlers@SystemSettings@@V?$vector@UTimeRange@BatteryUsageHandlers@SystemSettings@@V?$allocator@UTimeRange@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>(void)
0x180015ffa  lea     rcx, [rbx+1A0h]
0x180016001  call    ?_Tidy@?$vector@HV?$allocator@H@std@@@std@@AEAAXXZ; std::vector<int>::_Tidy(void)
0x180016006  lea     rcx, [rbx+188h]
0x18001600d  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUAppIdentity@BatteryUsageHandlers@SystemSettings@@V?$vector@UTimeRange@BatteryUsageHandlers@SystemSettings@@V?$allocator@UTimeRange@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>(void)
0x180016012  lea     rcx, [rbx+170h]
0x180016019  call    ?_Tidy@?$vector@HV?$allocator@H@std@@@std@@AEAAXXZ; std::vector<int>::_Tidy(void)
0x18001601e  lea     rcx, [rbx+158h]
0x180016025  call    ?_Tidy@?$vector@HV?$allocator@H@std@@@std@@AEAAXXZ; std::vector<int>::_Tidy(void)
0x18001602a  lea     rcx, [rbx+140h]
0x180016031  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUAppIdentity@BatteryUsageHandlers@SystemSettings@@V?$vector@UTimeRange@BatteryUsageHandlers@SystemSettings@@V?$allocator@UTimeRange@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>(void)
0x180016036  lea     rcx, [rbx+128h]
0x18001603d  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUAppIdentity@BatteryUsageHandlers@SystemSettings@@V?$vector@UTimeRange@BatteryUsageHandlers@SystemSettings@@V?$allocator@UTimeRange@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>(void)
0x180016042  lea     rcx, [rbx+110h]
0x180016049  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUAppIdentity@BatteryUsageHandlers@SystemSettings@@V?$vector@UTimeRange@BatteryUsageHandlers@SystemSettings@@V?$allocator@UTimeRange@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>(void)
0x18001604e  lea     rcx, [rbx+0F8h]
0x180016055  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUAppIdentity@BatteryUsageHandlers@SystemSettings@@V?$vector@UTimeRange@BatteryUsageHandlers@SystemSettings@@V?$allocator@UTimeRange@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity const,std::vector<SystemSettings::BatteryUsageHandlers::TimeRange>>>>>>>(void)
0x18001605a  mov     rcx, rbx; this
0x18001605d  add     rsp, 20h
0x180016061  pop     rbx
0x180016062  jmp     ??1?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAA@XZ; SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::~CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>(void)
```
