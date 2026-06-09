# SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::~CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>(void)

- ea: `0x180019f30`
- end: `0x180019f7f`
- name: `??1?$CSingletonHelper@W4BatterySaverCallbackSetting@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@UEAA@XZ`
- size: `79`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `20`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a8e4`
- `0x18001b2b0`
- `0x18001b7b0`
- `0x18001ba70`
- `0x18001bab0`
- `0x180030790`
- `0x18003468c`
- `0x180034960`
- `0x1800404ec`
- `0x180045f54`
- `0x18004839b`
- `0x18004990e`
- `0x18004a6e0`
- `0x18004a700`
- `0x18004a740`
- `0x18004a760`
- `0x18004a7c0`
- `0x18004a7e0`
- `0x18004a800`
- `0x18004a860`

## callees

- `0x180011f78`
- `0x180026bf0`
- `0x1800271c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019f58`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019f62`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019f58`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019f62`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::~CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>(
        __int64 a1)
{
  SystemSettings::DataModel::AutoMTAUsageCookie::Release((SystemSettings::DataModel::AutoMTAUsageCookie *)(a1 + 216));
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(a1 + 200);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 160));
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 112));
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::CCallback *>,0>>::~_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::CCallback *>,0>>((_QWORD *)(a1 + 40));
  return CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(a1 + 16);
}

```

## disassembly

```asm
0x180019f30  push    rbx
0x180019f32  sub     rsp, 20h
0x180019f36  mov     rbx, rcx
0x180019f39  add     rcx, 0D8h; this
0x180019f40  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x180019f45  lea     rcx, [rbx+0C8h]
0x180019f4c  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180019f51  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x180019f58  call    cs:__imp_DeleteCriticalSection
0x180019f5e  lea     rcx, [rbx+70h]; lpCriticalSection
0x180019f62  call    cs:__imp_DeleteCriticalSection
0x180019f68  lea     rcx, [rbx+28h]
0x180019f6c  call    ??1?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4BatterySaverInfoType@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4BatterySaverInfoType@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4BatterySaverInfoType@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4BatterySaverInfoType@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4BatterySaverInfoType@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::CCallback *>,0>>::~_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::CCallback *>,0>>(void)
0x180019f71  lea     rcx, [rbx+10h]
0x180019f75  add     rsp, 20h
0x180019f79  pop     rbx
0x180019f7a  jmp     ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
```
