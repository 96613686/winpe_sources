# UnionFs::UfsUnionCtx::FindAndStatItemInLayersPriv(_UNICODE_STRING const &,_UNICODE_STRING const &,UnionFs::Utils::StatItemFlags,UnionFs::FindAndStatResults &,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA *)

- ea: `0x1400612fc`
- end: `0x1400617ba`
- name: `?FindAndStatItemInLayersPriv@UfsUnionCtx@UnionFs@@AEBAJAEBU_UNICODE_STRING@@0W4StatItemFlags@Utils@2@AEAUFindAndStatResults@2@AEAVStackEventTracer@2@PEAU_FLT_CALLBACK_DATA@@@Z`
- size: `1214`
- prototype: `int __high(const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, enum UnionFs::Utils::StatItemFlags, struct UnionFs::FindAndStatResults *, struct UnionFs::StackEventTracer *, struct _FLT_CALLBACK_DATA *)`
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x1400611a4`
- `0x1400617c0`

## callees

- `0x14000227c`
- `0x14000efa0`
- `0x14000f81c`
- `0x140036268`
- `0x140044074`
- `0x140056c44`
- `0x140056c7c`
- `0x1400612fc`
- `0x1400779fc`
- `0x1400782bc`
- `0x140079d44`
- `0x140079f68`
- `0x14007a0c0`
- `0x14007b2b0`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400615ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006169d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006170b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006174b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400617a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400615ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006169d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006170b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006174b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400617a7`
- `ntoskrnl!PsGetHostSilo` at `0x140061457`
- `ntoskrnl!PsGetHostSilo` at `0x140061457`

## string_xrefs

- `0x14006175e`: `PUSH: Creating layer path`
- `0x140061596`: `status == STATUS_OBJECT_PATH_NOT_FOUND`

## pseudocode

```c

```
