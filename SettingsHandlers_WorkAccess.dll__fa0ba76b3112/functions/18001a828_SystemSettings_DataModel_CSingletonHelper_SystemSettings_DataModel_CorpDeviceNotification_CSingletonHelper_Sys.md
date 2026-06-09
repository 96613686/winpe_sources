# SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::~CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>(void)

- ea: `0x18001a828`
- end: `0x18001a883`
- name: `??1?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAA@XZ`
- size: `91`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001acbc`
- `0x18001b930`
- `0x180051320`
- `0x180051340`
- `0x180051420`

## callees

- `0x18001ab34`
- `0x18001ed10`
- `0x18001ed44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a850`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a860`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a850`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a860`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::~CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>(
        __int64 a1)
{
  SystemSettings::DataModel::AutoMTAUsageCookie::Release((SystemSettings::DataModel::AutoMTAUsageCookie *)(a1 + 216));
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(a1 + 200);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 160));
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 112));
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>,0>>::~_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>,0>>(a1 + 40);
  return CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(a1 + 16);
}

```

## disassembly

```asm
0x18001a828  push    rbx
0x18001a82a  sub     rsp, 20h
0x18001a82e  mov     rbx, rcx
0x18001a831  add     rcx, 0D8h; this
0x18001a838  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x18001a83d  lea     rcx, [rbx+0C8h]
0x18001a844  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18001a849  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x18001a850  call    cs:__imp_DeleteCriticalSection
0x18001a857  nop     dword ptr [rax+rax+00h]
0x18001a85c  lea     rcx, [rbx+70h]; lpCriticalSection
0x18001a860  call    cs:__imp_DeleteCriticalSection
0x18001a867  nop     dword ptr [rax+rax+00h]
0x18001a86c  lea     rcx, [rbx+28h]
0x18001a870  call    ??1?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>,0>>::~_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>,0>>(void)
0x18001a875  lea     rcx, [rbx+10h]
0x18001a879  add     rsp, 20h
0x18001a87d  pop     rbx
0x18001a87e  jmp     ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
```
