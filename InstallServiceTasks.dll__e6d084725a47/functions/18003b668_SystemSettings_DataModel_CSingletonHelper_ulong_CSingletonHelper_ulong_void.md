# SystemSettings::DataModel::CSingletonHelper<ulong>::~CSingletonHelper<ulong>(void)

- ea: `0x18003b668`
- end: `0x18003b6b7`
- name: `??1?$CSingletonHelper@K@DataModel@SystemSettings@@UEAA@XZ`
- size: `79`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003bac0`
- `0x180045a40`

## callees

- `0x18003b73c`
- `0x18003d900`
- `0x18003da68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003b690`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003b69a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003b690`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003b69a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<unsigned long>::~CSingletonHelper<unsigned long>(
        __int64 a1)
{
  SystemSettings::DataModel::AutoMTAUsageCookie::Release((SystemSettings::DataModel::AutoMTAUsageCookie *)(a1 + 216));
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(a1 + 200);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 160));
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 112));
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *>,0>>::~_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *>,0>>(a1 + 40);
  return CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(a1 + 16);
}

```

## disassembly

```asm
0x18003b668  push    rbx
0x18003b66a  sub     rsp, 20h
0x18003b66e  mov     rbx, rcx
0x18003b671  add     rcx, 0D8h; this
0x18003b678  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x18003b67d  lea     rcx, [rbx+0C8h]
0x18003b684  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18003b689  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x18003b690  call    cs:__imp_DeleteCriticalSection
0x18003b696  lea     rcx, [rbx+70h]; lpCriticalSection
0x18003b69a  call    cs:__imp_DeleteCriticalSection
0x18003b6a0  lea     rcx, [rbx+28h]
0x18003b6a4  call    ??1?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *>,0>>::~_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *>,0>>(void)
0x18003b6a9  lea     rcx, [rbx+10h]
0x18003b6ad  add     rsp, 20h
0x18003b6b1  pop     rbx
0x18003b6b2  jmp     ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
```
