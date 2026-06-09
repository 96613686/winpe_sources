# SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::~BackgroundCapabilitySingleton(void)

- ea: `0x180025dd8`
- end: `0x180025e52`
- name: `??1BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@UEAA@XZ`
- size: `122`
- prototype: `void __fastcall(SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180026000`
- `0x180059cb0`

## callees

- `0x180004cfc`
- `0x180024020`
- `0x180025c64`
- `0x180025dd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025df2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025df2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025e27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025e27`

## pseudocode

```c
void __fastcall SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::~BackgroundCapabilitySingleton(
        SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 304));
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 296);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 288);
  v2 = (void *)*((_QWORD *)this + 34);
  *((_QWORD *)this + 34) = 0;
  if ( v2 )
    CoTaskMemFree(v2);
  std::_Tree<std::_Tmap_traits<std::wstring const,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring const,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>>>,0>>((void **)this + 31);
  std::_Tree<std::_Tmap_traits<std::wstring const,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring const,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>>>,0>>((void **)this + 29);
  SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::~CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>((__int64)this);
}

```

## disassembly

```asm
0x180025dd8  push    rbx
0x180025dda  sub     rsp, 20h
0x180025dde  lea     rax, ??_7BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@6B@; const SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::`vftable'
0x180025de5  mov     rbx, rcx
0x180025de8  mov     [rcx], rax
0x180025deb  add     rcx, 130h; lpCriticalSection
0x180025df2  call    cs:__imp_DeleteCriticalSection
0x180025df8  lea     rcx, [rbx+128h]
0x180025dff  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025e04  lea     rcx, [rbx+120h]
0x180025e0b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025e10  mov     rcx, [rbx+110h]; pv
0x180025e17  mov     qword ptr [rbx+110h], 0
0x180025e22  test    rcx, rcx
0x180025e25  jz      short loc_180025E2D
0x180025e27  call    cs:__imp_CoTaskMemFree
0x180025e2d  lea     rcx, [rbx+0F8h]
0x180025e34  call    ??1?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring const,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring const,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>>>,0>>(void)
0x180025e39  lea     rcx, [rbx+0E8h]
0x180025e40  call    ??1?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring const,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring const,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>>>,0>>(void)
0x180025e45  mov     rcx, rbx
0x180025e48  add     rsp, 20h
0x180025e4c  pop     rbx
0x180025e4d  jmp     ??1?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@UEAA@XZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::~CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>(void)
```
