# SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::~CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>(void)

- ea: `0x180024020`
- end: `0x18002406f`
- name: `??1?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@UEAA@XZ`
- size: `79`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `14`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800242d4`
- `0x180024398`
- `0x180024580`
- `0x180025dd8`
- `0x180025e58`
- `0x180025e80`
- `0x180025f4c`
- `0x1800553a0`
- `0x180057387`
- `0x18005745a`
- `0x180057485`
- `0x180058429`
- `0x18005873c`
- `0x180058873`

## callees

- `0x180010030`
- `0x1800101f8`
- `0x180024180`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024048`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024052`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024048`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024052`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::~CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>(
        __int64 a1)
{
  SystemSettings::DataModel::AutoMTAUsageCookie::Release((SystemSettings::DataModel::AutoMTAUsageCookie *)(a1 + 216));
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(a1 + 200);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 160));
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 112));
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback *>,0>>::~_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback *>,0>>(a1 + 40);
  return CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(a1 + 16);
}

```

## disassembly

```asm
0x180024020  push    rbx
0x180024022  sub     rsp, 20h
0x180024026  mov     rbx, rcx
0x180024029  add     rcx, 0D8h; this
0x180024030  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x180024035  lea     rcx, [rbx+0C8h]
0x18002403c  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180024041  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x180024048  call    cs:__imp_DeleteCriticalSection
0x18002404e  lea     rcx, [rbx+70h]; lpCriticalSection
0x180024052  call    cs:__imp_DeleteCriticalSection
0x180024058  lea     rcx, [rbx+28h]
0x18002405c  call    ??1?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4BatteryGraphNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4BatteryGraphNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4BatteryGraphNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4BatteryGraphNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4BatteryGraphNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback *>,0>>::~_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback *>,0>>(void)
0x180024061  lea     rcx, [rbx+10h]
0x180024065  add     rsp, 20h
0x180024069  pop     rbx
0x18002406a  jmp     ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
```
