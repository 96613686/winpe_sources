# _CSurrogate::LoadDllServer_::_1_::dtor$1

- ea: `0x14000fc42`
- end: `0x14000fc4e`
- name: `_CSurrogate::LoadDllServer_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000409c`

## pseudocode

```c
void __fastcall CSurrogate::LoadDllServer_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CommonUtil::CGenericAutoScopeLock<CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>>::~CGenericAutoScopeLock<CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>>(a2 + 64);
}

```

## disassembly

```asm
0x14000fc42  lea     rcx, [rdx+40h]
0x14000fc49  jmp     ??1?$CGenericAutoScopeLock@V?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoScopeLock<CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>>::~CGenericAutoScopeLock<CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>>(void)
```
