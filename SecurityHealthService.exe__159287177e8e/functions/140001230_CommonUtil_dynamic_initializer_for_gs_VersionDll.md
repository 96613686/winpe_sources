# CommonUtil::_dynamic_initializer_for__gs_VersionDll__

- ea: `0x140001230`
- end: `0x14000124a`
- name: `CommonUtil::_dynamic_initializer_for__gs_VersionDll__`
- size: `26`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140011110`

## pseudocode

```c
__int64 CommonUtil::_dynamic_initializer_for__gs_VersionDll__()
{
  return MpRegisterForInitializationAtStartup(
           qword_14001B9B8,
           CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnInitialize,
           CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnDestroy);
}

```

## disassembly

```asm
0x140001230  lea     r8, ?OnDestroy@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy@VCMpVersionDllWrapper@CommonUtil@@@CommonUtil@@@CommonUtil@@CAXPEAUtagMP_AT_STARTUP_TYPE@@@Z; CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnDestroy(tagMP_AT_STARTUP_TYPE *)
0x140001237  lea     rdx, ?OnInitialize@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy@VCMpVersionDllWrapper@CommonUtil@@@CommonUtil@@@CommonUtil@@CAJPEAUtagMP_AT_STARTUP_TYPE@@@Z; CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnInitialize(tagMP_AT_STARTUP_TYPE *)
0x14000123e  lea     rcx, qword_14001B9B8
0x140001245  jmp     MpRegisterForInitializationAtStartup
```
