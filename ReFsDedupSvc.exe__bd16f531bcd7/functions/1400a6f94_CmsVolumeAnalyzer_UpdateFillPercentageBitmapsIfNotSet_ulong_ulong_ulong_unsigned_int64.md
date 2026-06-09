# CmsVolumeAnalyzer::UpdateFillPercentageBitmapsIfNotSet(ulong,ulong,ulong,unsigned __int64)

- ea: `0x1400a6f94`
- end: `0x1400a708b`
- name: `?UpdateFillPercentageBitmapsIfNotSet@CmsVolumeAnalyzer@@QEAAXKKK_K@Z`
- size: `247`
- prototype: `void __usercall(CmsVolumeAnalyzer *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1400a6e84`

## callees

- `0x1400a6f94`
- `0x1400a7094`

## import_xrefs

- `ntdll!RtlFindClearBits` at `0x1400a7006`
- `ntdll!RtlFindClearBits` at `0x1400a7006`
- `ntdll!RtlFindSetBits` at `0x1400a702a`
- `ntdll!RtlFindSetBits` at `0x1400a702a`
- `ntdll!RtlInitializeBitMap` at `0x1400a6fc3`
- `ntdll!RtlInitializeBitMap` at `0x1400a6fc3`

## pseudocode

```c

```
