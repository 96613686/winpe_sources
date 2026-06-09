# SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenCommandsSyncArgs>::~CSingletonHelper<SystemSettings::PenSettings::PenCommandsSyncArgs>(void)

- ea: `0x180034974`
- end: `0x1800349c3`
- name: `??1?$CSingletonHelper@W4PenCommandsSyncArgs@PenSettings@SystemSettings@@@DataModel@SystemSettings@@UEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035550`
- `0x180051154`
- `0x180054cc0`
- `0x18005c1a0`
- `0x18005c1e0`
- `0x18005c240`
- `0x18005c260`

## callees

- `0x1800204dc`
- `0x18002d7e8`
- `0x18002d814`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003499c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800349a6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003499c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800349a6`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PenSettings::PenCommandsSyncArgs>::~CSingletonHelper<enum SystemSettings::PenSettings::PenCommandsSyncArgs>(
        __int64 a1)
{
  SystemSettings::DataModel::AutoMTAUsageCookie::Release((SystemSettings::DataModel::AutoMTAUsageCookie *)(a1 + 216));
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(a1 + 200);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 160));
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 112));
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::CCallback *>,0>>::~_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::CCallback *>,0>>(a1 + 40);
  return CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(a1 + 16);
}

```

## disassembly

```asm
0x180034974  push    rbx
0x180034976  sub     rsp, 20h
0x18003497a  mov     rbx, rcx
0x18003497d  add     rcx, 0D8h; this
0x180034984  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x180034989  lea     rcx, [rbx+0C8h]
0x180034990  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180034995  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x18003499c  call    cs:__imp_DeleteCriticalSection
0x1800349a2  lea     rcx, [rbx+70h]; lpCriticalSection
0x1800349a6  call    cs:__imp_DeleteCriticalSection
0x1800349ac  lea     rcx, [rbx+28h]
0x1800349b0  call    ??1?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@AEAUPenButtonAppPickerNotificationItem@PenSettings@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@AEAUPenButtonAppPickerNotificationItem@PenSettings@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@AEAUPenButtonAppPickerNotificationItem@PenSettings@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@AEAUPenButtonAppPickerNotificationItem@PenSettings@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@AEAUPenButtonAppPickerNotificationItem@PenSettings@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::CCallback *>,0>>::~_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::CCallback *>,0>>(void)
0x1800349b5  lea     rcx, [rbx+10h]
0x1800349b9  add     rsp, 20h
0x1800349bd  pop     rbx
0x1800349be  jmp     ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
```
