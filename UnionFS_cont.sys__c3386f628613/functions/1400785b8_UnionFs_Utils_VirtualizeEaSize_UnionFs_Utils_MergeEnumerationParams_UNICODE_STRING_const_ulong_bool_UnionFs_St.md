# UnionFs::Utils::VirtualizeEaSize(UnionFs::Utils::MergeEnumerationParams &,_UNICODE_STRING const &,ulong *,bool *,UnionFs::StackEventTracer &)

- ea: `0x1400785b8`
- end: `0x1400787ce`
- name: `?VirtualizeEaSize@Utils@UnionFs@@YAJAEAUMergeEnumerationParams@12@AEBU_UNICODE_STRING@@PEAKPEA_NAEAVStackEventTracer@2@@Z`
- size: `534`
- prototype: `int(UnionFs::Utils *__hidden this, struct UnionFs::Utils::MergeEnumerationParams *, const struct _UNICODE_STRING *, unsigned int *, bool *, struct UnionFs::StackEventTracer *)`
- caller_count: `6`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140071180`
- `0x140071424`
- `0x140071b50`
- `0x140071df4`
- `0x140072050`
- `0x140072838`

## callees

- `0x14000f7fc`
- `0x140023a3c`
- `0x1400438e4`
- `0x140056afc`
- `0x14006a3cc`
- `0x14006a554`
- `0x1400785b8`
- `0x140079c48`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14007870c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140078779`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007870c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140078779`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140078718`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140078785`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140078718`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140078785`

## string_xrefs

- `0x140078633`: `PUSH: Combining directory path, final name with realloc`
- `0x140078663`: `PUSH: Combining directory path, final name with no realloc`

## pseudocode

```c

```
