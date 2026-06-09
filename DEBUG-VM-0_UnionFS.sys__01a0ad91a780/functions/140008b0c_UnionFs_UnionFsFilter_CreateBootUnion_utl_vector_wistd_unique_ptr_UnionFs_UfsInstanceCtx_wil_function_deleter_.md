# UnionFs::UnionFsFilter::CreateBootUnion(utl::vector<wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>>,utl::allocator<wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>>>> const &,UnionFs::StackEventTracer &)

- ea: `0x140008b0c`
- end: `0x140008c2f`
- name: `?CreateBootUnion@UnionFsFilter@UnionFs@@AEAAJAEBV?$vector@V?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000b1e8`

## callees

- `0x140008b0c`
- `0x140008c38`
- `0x1400093cc`
- `0x140056c7c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008b86`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008bf6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008c10`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008b86`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008bf6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008c10`

## string_xrefs

- `0x140008b53`: `PUSH: CreateBootUnionConfigMessage`
- `0x140008b64`: `UnionFs::UnionFsFilter::CreateBootUnion`
- `0x140008bd6`: `UnionFs::UnionFsFilter::CreateBootUnion`

## pseudocode

```c

```
