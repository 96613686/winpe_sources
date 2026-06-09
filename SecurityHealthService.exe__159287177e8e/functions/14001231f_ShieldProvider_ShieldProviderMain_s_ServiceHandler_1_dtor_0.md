# _ShieldProvider::ShieldProviderMain::s_ServiceHandler_::_1_::dtor$0

- ea: `0x14001231f`
- end: `0x14001232b`
- name: `_ShieldProvider::ShieldProviderMain::s_ServiceHandler_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140003680`

## pseudocode

```c
void __fastcall ShieldProvider::ShieldProviderMain::s_ServiceHandler_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CommonUtil::CGenericAutoScopeLock<CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>>::~CGenericAutoScopeLock<CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>>(a2 + 48);
}

```

## disassembly

```asm
0x14001231f  lea     rcx, [rdx+30h]
0x140012326  jmp     ??1?$CGenericAutoScopeLock@V?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoScopeLock<CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>>::~CGenericAutoScopeLock<CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>>(void)
```
