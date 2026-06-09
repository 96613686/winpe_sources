# SystemSettings::BatteryUsageHandlers::UsageDataSingleton::~UsageDataSingleton(void)

- ea: `0x180025f4c`
- end: `0x180025ff4`
- name: `??1UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@UEAA@XZ`
- size: `168`
- prototype: `void __fastcall(SystemSettings::BatteryUsageHandlers::UsageDataSingleton *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800260c0`
- `0x180059d70`

## callees

- `0x180004cfc`
- `0x180024020`
- `0x180025710`
- `0x180025c0c`
- `0x180025d54`
- `0x180025d70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025fe1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025fe1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025fb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025fb1`

## pseudocode

```c
void __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton::~UsageDataSingleton(
        SystemSettings::BatteryUsageHandlers::UsageDataSingleton *this,
        __int64 a2)
{
  *(_QWORD *)this = &SystemSettings::BatteryUsageHandlers::UsageDataSingleton::`vftable';
  SrumCache<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>::~SrumCache<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>(
    (__int64)this + 424,
    a2);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
    (char *)this + 408,
    (char *)this + 408);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 400);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 392);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 384);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 376);
  WindowsDeleteString(*((HSTRING *)this + 41));
  *((_QWORD *)this + 41) = 0;
  std::map<std::wstring const,std::wstring>::~map<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>>((char *)this + 288);
  std::map<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>>::~map<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>>>>((void **)this + 34);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::~CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>((__int64)this);
}

```

## disassembly

```asm
0x180025f4c  push    rbx
0x180025f4e  sub     rsp, 20h
0x180025f52  lea     rax, ??_7UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@6B@; const SystemSettings::BatteryUsageHandlers::UsageDataSingleton::`vftable'
0x180025f59  mov     rbx, rcx
0x180025f5c  mov     [rcx], rax
0x180025f5f  add     rcx, 1A8h
0x180025f66  call    ??1?$SrumCache@UAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@@@QEAA@XZ; SrumCache<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>::~SrumCache<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>(void)
0x180025f6b  lea     rcx, [rbx+198h]
0x180025f72  mov     rdx, rcx
0x180025f75  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x180025f7a  lea     rcx, [rbx+190h]
0x180025f81  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025f86  lea     rcx, [rbx+188h]
0x180025f8d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025f92  lea     rcx, [rbx+180h]
0x180025f99  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025f9e  lea     rcx, [rbx+178h]
0x180025fa5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025faa  mov     rcx, [rbx+148h]; string
0x180025fb1  call    cs:__imp_WindowsDeleteString
0x180025fb7  lea     rcx, [rbx+120h]
0x180025fbe  mov     qword ptr [rbx+148h], 0
0x180025fc9  call    ??1?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring const,std::wstring>::~map<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>>(void)
0x180025fce  lea     rcx, [rbx+110h]
0x180025fd5  call    ??1?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@WRL@Microsoft@@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@WRL@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>>::~map<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>>>>(void)
0x180025fda  lea     rcx, [rbx+0E8h]; lpCriticalSection
0x180025fe1  call    cs:__imp_DeleteCriticalSection
0x180025fe7  mov     rcx, rbx
0x180025fea  add     rsp, 20h
0x180025fee  pop     rbx
0x180025fef  jmp     ??1?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@UEAA@XZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::~CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>(void)
```
