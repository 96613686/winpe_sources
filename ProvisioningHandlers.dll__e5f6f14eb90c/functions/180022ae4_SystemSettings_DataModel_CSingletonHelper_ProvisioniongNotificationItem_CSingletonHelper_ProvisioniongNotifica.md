# SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::~CSingletonHelper<ProvisioniongNotificationItem &>(void)

- ea: `0x180022ae4`
- end: `0x180022b3f`
- name: `??1?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@UEAA@XZ`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022c18`
- `0x180022eb0`

## callees

- `0x18001b330`
- `0x18001b9a0`
- `0x180022b48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022b0c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022b1c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022b0c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022b1c`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::~CSingletonHelper<ProvisioniongNotificationItem &>(
        __int64 a1)
{
  SystemSettings::DataModel::AutoMTAUsageCookie::Release((SystemSettings::DataModel::AutoMTAUsageCookie *)(a1 + 216));
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(a1 + 200);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 160));
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 112));
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>,0>>::~_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>,0>>(a1 + 40);
  return CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(a1 + 16);
}

```

## disassembly

```asm
0x180022ae4  push    rbx
0x180022ae6  sub     rsp, 20h
0x180022aea  mov     rbx, rcx
0x180022aed  add     rcx, 0D8h; this
0x180022af4  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x180022af9  lea     rcx, [rbx+0C8h]
0x180022b00  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180022b05  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x180022b0c  call    cs:__imp_DeleteCriticalSection
0x180022b13  nop     dword ptr [rax+rax+00h]
0x180022b18  lea     rcx, [rbx+70h]; lpCriticalSection
0x180022b1c  call    cs:__imp_DeleteCriticalSection
0x180022b23  nop     dword ptr [rax+rax+00h]
0x180022b28  lea     rcx, [rbx+28h]
0x180022b2c  call    ??1?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>,0>>::~_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>,0>>(void)
0x180022b31  lea     rcx, [rbx+10h]
0x180022b35  add     rsp, 20h
0x180022b39  pop     rbx
0x180022b3a  jmp     ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
```
