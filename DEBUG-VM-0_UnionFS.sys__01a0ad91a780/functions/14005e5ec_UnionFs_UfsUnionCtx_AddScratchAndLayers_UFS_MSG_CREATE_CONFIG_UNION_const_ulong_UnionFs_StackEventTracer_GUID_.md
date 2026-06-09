# UnionFs::UfsUnionCtx::AddScratchAndLayers(UFS_MSG_CREATE_CONFIG_UNION const &,ulong,UnionFs::StackEventTracer &,_GUID const *)

- ea: `0x14005e5ec`
- end: `0x14005f1b3`
- name: `?AddScratchAndLayers@UfsUnionCtx@UnionFs@@AEAAJAEBUUFS_MSG_CREATE_CONFIG_UNION@@KAEAVStackEventTracer@2@PEBU_GUID@@@Z`
- size: `3015`
- prototype: `int(UnionFs::UfsUnionCtx *__hidden this, const struct UFS_MSG_CREATE_CONFIG_UNION *, unsigned int, struct UnionFs::StackEventTracer *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x140062fd4`

## callees

- `0x14000f81c`
- `0x14001f4c8`
- `0x1400210fc`
- `0x140027764`
- `0x14002a0f8`
- `0x140035f78`
- `0x140043a64`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x14005d3ac`
- `0x14005e5ec`
- `0x1400675d4`
- `0x14006ef20`
- `0x14006f3fc`
- `0x140079f68`
- `0x14007b2b0`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14005e6a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ec6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ed03`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005edc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005eea3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ef37`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005efbf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f101`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f158`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e6a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ec6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ed03`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005edc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005eea3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ef37`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005efbf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f101`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f158`
- `FLTMGR!FltAdjustDeviceStackSizeForIoRedirection` at `0x14005ea60`
- `FLTMGR!FltAdjustDeviceStackSizeForIoRedirection` at `0x14005ea60`
- `FLTMGR!FltIsIoRedirectionAllowed` at `0x14005ea38`
- `FLTMGR!FltIsIoRedirectionAllowed` at `0x14005ea38`
- `FLTMGR!FltObjectReference` at `0x14005e9e6`
- `FLTMGR!FltObjectReference` at `0x14005e9e6`
- `FLTMGR!FltReleaseContext` at `0x14005ebb9`
- `FLTMGR!FltReleaseContext` at `0x14005ed5f`
- `FLTMGR!FltReleaseContext` at `0x14005ee0e`
- `FLTMGR!FltReleaseContext` at `0x14005ebb9`
- `FLTMGR!FltReleaseContext` at `0x14005ed5f`
- `FLTMGR!FltReleaseContext` at `0x14005ee0e`
- `FLTMGR!FltObjectDereference` at `0x14005e9fa`
- `FLTMGR!FltObjectDereference` at `0x14005ebdb`
- `FLTMGR!FltObjectDereference` at `0x14005ec2a`
- `FLTMGR!FltObjectDereference` at `0x14005ec3e`
- `FLTMGR!FltObjectDereference` at `0x14005ecc0`
- `FLTMGR!FltObjectDereference` at `0x14005ecd4`
- `FLTMGR!FltObjectDereference` at `0x14005ed80`
- `FLTMGR!FltObjectDereference` at `0x14005ed94`
- `FLTMGR!FltObjectDereference` at `0x14005ee60`
- `FLTMGR!FltObjectDereference` at `0x14005ee74`
- `FLTMGR!FltObjectDereference` at `0x14005eef4`
- `FLTMGR!FltObjectDereference` at `0x14005ef08`
- `FLTMGR!FltObjectDereference` at `0x14005ef7c`
- `FLTMGR!FltObjectDereference` at `0x14005ef90`
- `FLTMGR!FltObjectDereference` at `0x14005f129`
- `FLTMGR!FltObjectDereference` at `0x14005e9fa`
- `FLTMGR!FltObjectDereference` at `0x14005ebdb`
- `FLTMGR!FltObjectDereference` at `0x14005ec2a`
- `FLTMGR!FltObjectDereference` at `0x14005ec3e`
- `FLTMGR!FltObjectDereference` at `0x14005ecc0`
- `FLTMGR!FltObjectDereference` at `0x14005ecd4`
- `FLTMGR!FltObjectDereference` at `0x14005ed80`
- `FLTMGR!FltObjectDereference` at `0x14005ed94`
- `FLTMGR!FltObjectDereference` at `0x14005ee60`
- `FLTMGR!FltObjectDereference` at `0x14005ee74`
- `FLTMGR!FltObjectDereference` at `0x14005eef4`
- `FLTMGR!FltObjectDereference` at `0x14005ef08`
- `FLTMGR!FltObjectDereference` at `0x14005ef7c`
- `FLTMGR!FltObjectDereference` at `0x14005ef90`
- `FLTMGR!FltObjectDereference` at `0x14005f129`

## string_xrefs

- `0x14005f168`: `ORIGIN: Layers already exist`
- `0x14005e6c8`: `UnionConfig.LayerCount == layerRootIds.size()`

## pseudocode

```c

```
