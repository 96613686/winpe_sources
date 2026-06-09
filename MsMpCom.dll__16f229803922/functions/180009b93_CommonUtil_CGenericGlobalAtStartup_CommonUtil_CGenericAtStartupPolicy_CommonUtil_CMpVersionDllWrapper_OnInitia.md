# _CommonUtil::CGenericGlobalAtStartup_CommonUtil::CGenericAtStartupPolicy_CommonUtil::CMpVersionDllWrapper___::OnInitializeCallback_::_1_::dtor$1

- ea: `0x180009b93`
- end: `0x180009b9f`
- name: `_CommonUtil::CGenericGlobalAtStartup_CommonUtil::CGenericAtStartupPolicy_CommonUtil::CMpVersionDllWrapper___::OnInitializeCallback_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180006000`

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
0x180009b93  lea     rcx, [rdx+28h]
0x180009b9a  jmp     ??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)
```
