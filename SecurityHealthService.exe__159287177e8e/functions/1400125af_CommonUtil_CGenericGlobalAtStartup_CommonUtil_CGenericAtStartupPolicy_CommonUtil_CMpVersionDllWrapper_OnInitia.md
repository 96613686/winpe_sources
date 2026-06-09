# _CommonUtil::CGenericGlobalAtStartup_CommonUtil::CGenericAtStartupPolicy_CommonUtil::CMpVersionDllWrapper___::OnInitializeCallback_::_1_::dtor$1

- ea: `0x1400125af`
- end: `0x1400125bb`
- name: `_CommonUtil::CGenericGlobalAtStartup_CommonUtil::CGenericAtStartupPolicy_CommonUtil::CMpVersionDllWrapper___::OnInitializeCallback_::_1_::dtor$1`
- size: `12`
- prototype: `BOOL __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140003bf4`

## pseudocode

```c
BOOL __fastcall CommonUtil::CGenericGlobalAtStartup_CommonUtil::CGenericAtStartupPolicy_CommonUtil::CMpVersionDllWrapper___::OnInitializeCallback_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  return CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>((HMODULE *)(a2 + 40));
}

```

## disassembly

```asm
0x1400125af  lea     rcx, [rdx+28h]
0x1400125b6  jmp     ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
```
