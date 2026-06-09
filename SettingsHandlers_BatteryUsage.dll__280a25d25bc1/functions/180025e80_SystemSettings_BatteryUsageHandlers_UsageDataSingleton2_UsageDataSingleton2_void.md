# SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::~UsageDataSingleton2(void)

- ea: `0x180025e80`
- end: `0x180025f46`
- name: `??1UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@UEAA@XZ`
- size: `198`
- prototype: `void __fastcall(SystemSettings::BatteryUsageHandlers::UsageDataSingleton2 *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180026080`
- `0x180059d50`

## callees

- `0x180004cfc`
- `0x180024020`
- `0x1800256e0`
- `0x180025710`
- `0x180025c0c`
- `0x180025c94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025f33`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025f33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025f00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025f00`

## pseudocode

```c
void __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::~UsageDataSingleton2(
        SystemSettings::BatteryUsageHandlers::UsageDataSingleton2 *this)
{
  __int64 v2; // rdx
  __int64 v3; // rdx

  *(_QWORD *)this = &SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::`vftable';
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,SystemSettings::StorageSenseHandlers::ApplicationIdentity>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,SystemSettings::StorageSenseHandlers::ApplicationIdentity>,void *>>>(
    (char *)this + 696,
    (char *)this + 696);
  SrumCache<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>::~SrumCache<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>(
    (__int64)this + 552,
    v2);
  SrumCache<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>::~SrumCache<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>(
    (__int64)this + 416,
    v3);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
    (char *)this + 400,
    (char *)this + 400);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 392);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 384);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 376);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 368);
  WindowsDeleteString(*((HSTRING *)this + 40));
  *((_QWORD *)this + 40) = 0;
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
    (char *)this + 288,
    (char *)this + 288);
  std::_Tree<std::_Tmap_traits<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>>>,0>>((void **)this + 34);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::~CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>((__int64)this);
}

```

## disassembly

```asm
0x180025e80  push    rbx
0x180025e82  sub     rsp, 20h
0x180025e86  lea     rax, ??_7UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@6B@; const SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::`vftable'
0x180025e8d  mov     rbx, rcx
0x180025e90  mov     [rcx], rax
0x180025e93  add     rcx, 2B8h
0x180025e9a  mov     rdx, rcx
0x180025e9d  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UApplicationIdentity@StorageSenseHandlers@SystemSettings@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UApplicationIdentity@StorageSenseHandlers@SystemSettings@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UApplicationIdentity@StorageSenseHandlers@SystemSettings@@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,SystemSettings::StorageSenseHandlers::ApplicationIdentity>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,SystemSettings::StorageSenseHandlers::ApplicationIdentity>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,SystemSettings::StorageSenseHandlers::ApplicationIdentity>,void *>> &)
0x180025ea2  lea     rcx, [rbx+228h]
0x180025ea9  call    ??1?$SrumCache@UAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@@@QEAA@XZ; SrumCache<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>::~SrumCache<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>(void)
0x180025eae  lea     rcx, [rbx+1A0h]
0x180025eb5  call    ??1?$SrumCache@UAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@@@QEAA@XZ; SrumCache<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>::~SrumCache<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>(void)
0x180025eba  lea     rcx, [rbx+190h]
0x180025ec1  mov     rdx, rcx
0x180025ec4  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x180025ec9  lea     rcx, [rbx+188h]
0x180025ed0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025ed5  lea     rcx, [rbx+180h]
0x180025edc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025ee1  lea     rcx, [rbx+178h]
0x180025ee8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025eed  lea     rcx, [rbx+170h]
0x180025ef4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025ef9  mov     rcx, [rbx+140h]; string
0x180025f00  call    cs:__imp_WindowsDeleteString
0x180025f06  lea     rcx, [rbx+120h]
0x180025f0d  mov     qword ptr [rbx+140h], 0
0x180025f18  mov     rdx, rcx
0x180025f1b  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x180025f20  lea     rcx, [rbx+110h]
0x180025f27  call    ??1?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@WRL@Microsoft@@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>>>,0>>(void)
0x180025f2c  lea     rcx, [rbx+0E8h]; lpCriticalSection
0x180025f33  call    cs:__imp_DeleteCriticalSection
0x180025f39  mov     rcx, rbx
0x180025f3c  add     rsp, 20h
0x180025f40  pop     rbx
0x180025f41  jmp     ??1?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@UEAA@XZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::~CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>(void)
```
