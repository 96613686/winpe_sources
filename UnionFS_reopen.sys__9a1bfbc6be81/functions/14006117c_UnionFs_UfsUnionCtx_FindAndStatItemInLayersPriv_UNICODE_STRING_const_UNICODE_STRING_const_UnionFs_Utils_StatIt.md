# UnionFs::UfsUnionCtx::FindAndStatItemInLayersPriv(_UNICODE_STRING const &,_UNICODE_STRING const &,UnionFs::Utils::StatItemFlags,UnionFs::FindAndStatResults &,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA *)

- ea: `0x14006117c`
- end: `0x14006163a`
- name: `?FindAndStatItemInLayersPriv@UfsUnionCtx@UnionFs@@AEBAJAEBU_UNICODE_STRING@@0W4StatItemFlags@Utils@2@AEAUFindAndStatResults@2@AEAVStackEventTracer@2@PEAU_FLT_CALLBACK_DATA@@@Z`
- size: `1214`
- prototype: `int __high(const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, enum UnionFs::Utils::StatItemFlags, struct UnionFs::FindAndStatResults *, struct UnionFs::StackEventTracer *, struct _FLT_CALLBACK_DATA *)`
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x140061024`
- `0x140061640`

## callees

- `0x14000227c`
- `0x14000efd0`
- `0x14000f7fc`
- `0x140036128`
- `0x140043ef4`
- `0x140056ac4`
- `0x140056afc`
- `0x14006117c`
- `0x140077710`
- `0x140077f94`
- `0x140079a24`
- `0x140079c48`
- `0x140079da0`
- `0x14007af90`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006144a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006151d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006158b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400615cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061627`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006144a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006151d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006158b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400615cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061627`
- `ntoskrnl!PsGetHostSilo` at `0x1400612d7`
- `ntoskrnl!PsGetHostSilo` at `0x1400612d7`

## string_xrefs

- `0x1400615de`: `PUSH: Creating layer path`
- `0x140061416`: `status == STATUS_OBJECT_PATH_NOT_FOUND`

## pseudocode

```c

```
