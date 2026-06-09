# UnionFs::UfsUnionCtx::AddScratchAndLayers(UFS_MSG_CREATE_CONFIG_UNION const &,ulong,UnionFs::StackEventTracer &,_GUID const *)

- ea: `0x14005e46c`
- end: `0x14005f033`
- name: `?AddScratchAndLayers@UfsUnionCtx@UnionFs@@AEAAJAEBUUFS_MSG_CREATE_CONFIG_UNION@@KAEAVStackEventTracer@2@PEBU_GUID@@@Z`
- size: `3015`
- prototype: `int(UnionFs::UfsUnionCtx *__hidden this, const struct UFS_MSG_CREATE_CONFIG_UNION *, unsigned int, struct UnionFs::StackEventTracer *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x140062e54`

## callees

- `0x14000f7fc`
- `0x14001f428`
- `0x14002105c`
- `0x1400276c4`
- `0x14002a058`
- `0x140035e38`
- `0x1400438e4`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x14005d22c`
- `0x14005e46c`
- `0x140067454`
- `0x14006ed30`
- `0x14006f20c`
- `0x140079c48`
- `0x14007af90`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14005e520`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005eaed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005eb83`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ec43`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ed23`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005edb7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ee3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ef81`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005efd8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e520`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005eaed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005eb83`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ec43`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ed23`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005edb7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ee3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ef81`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005efd8`
- `FLTMGR!FltAdjustDeviceStackSizeForIoRedirection` at `0x14005e8e0`
- `FLTMGR!FltAdjustDeviceStackSizeForIoRedirection` at `0x14005e8e0`
- `FLTMGR!FltIsIoRedirectionAllowed` at `0x14005e8b8`
- `FLTMGR!FltIsIoRedirectionAllowed` at `0x14005e8b8`
- `FLTMGR!FltObjectReference` at `0x14005e866`
- `FLTMGR!FltObjectReference` at `0x14005e866`
- `FLTMGR!FltReleaseContext` at `0x14005ea39`
- `FLTMGR!FltReleaseContext` at `0x14005ebdf`
- `FLTMGR!FltReleaseContext` at `0x14005ec8e`
- `FLTMGR!FltReleaseContext` at `0x14005ea39`
- `FLTMGR!FltReleaseContext` at `0x14005ebdf`
- `FLTMGR!FltReleaseContext` at `0x14005ec8e`
- `FLTMGR!FltObjectDereference` at `0x14005e87a`
- `FLTMGR!FltObjectDereference` at `0x14005ea5b`
- `FLTMGR!FltObjectDereference` at `0x14005eaaa`
- `FLTMGR!FltObjectDereference` at `0x14005eabe`
- `FLTMGR!FltObjectDereference` at `0x14005eb40`
- `FLTMGR!FltObjectDereference` at `0x14005eb54`
- `FLTMGR!FltObjectDereference` at `0x14005ec00`
- `FLTMGR!FltObjectDereference` at `0x14005ec14`
- `FLTMGR!FltObjectDereference` at `0x14005ece0`
- `FLTMGR!FltObjectDereference` at `0x14005ecf4`
- `FLTMGR!FltObjectDereference` at `0x14005ed74`
- `FLTMGR!FltObjectDereference` at `0x14005ed88`
- `FLTMGR!FltObjectDereference` at `0x14005edfc`
- `FLTMGR!FltObjectDereference` at `0x14005ee10`
- `FLTMGR!FltObjectDereference` at `0x14005efa9`
- `FLTMGR!FltObjectDereference` at `0x14005e87a`
- `FLTMGR!FltObjectDereference` at `0x14005ea5b`
- `FLTMGR!FltObjectDereference` at `0x14005eaaa`
- `FLTMGR!FltObjectDereference` at `0x14005eabe`
- `FLTMGR!FltObjectDereference` at `0x14005eb40`
- `FLTMGR!FltObjectDereference` at `0x14005eb54`
- `FLTMGR!FltObjectDereference` at `0x14005ec00`
- `FLTMGR!FltObjectDereference` at `0x14005ec14`
- `FLTMGR!FltObjectDereference` at `0x14005ece0`
- `FLTMGR!FltObjectDereference` at `0x14005ecf4`
- `FLTMGR!FltObjectDereference` at `0x14005ed74`
- `FLTMGR!FltObjectDereference` at `0x14005ed88`
- `FLTMGR!FltObjectDereference` at `0x14005edfc`
- `FLTMGR!FltObjectDereference` at `0x14005ee10`
- `FLTMGR!FltObjectDereference` at `0x14005efa9`

## string_xrefs

- `0x14005efe8`: `ORIGIN: Layers already exist`
- `0x14005e548`: `UnionConfig.LayerCount == layerRootIds.size()`

## pseudocode

```c

```
