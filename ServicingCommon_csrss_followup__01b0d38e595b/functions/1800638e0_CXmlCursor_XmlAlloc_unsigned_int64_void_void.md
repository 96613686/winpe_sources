# CXmlCursor::XmlAlloc(unsigned __int64,void * *,void *)

- ea: `0x1800638e0`
- end: `0x18006397a`
- name: `?XmlAlloc@CXmlCursor@@KAJ_KPEAPEAXPEAX@Z`
- size: `154`
- prototype: `__int64 __fastcall(SIZE_T Size, void **, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x1800217cc`
- `0x18002d2b0`
- `0x1800638e0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180063912`
- `ntdll!RtlAllocateHeap` at `0x180063912`

## string_xrefs

- `0x180063926`: `onecore\base\xml\udom_xmlwalker.h`
- `0x180063940`: `CXmlCursor::XmlAlloc`
- `0x180063951`: `*ppvAlloc = RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->ProcessHeap), 0, cb)`

## pseudocode

```c

```
