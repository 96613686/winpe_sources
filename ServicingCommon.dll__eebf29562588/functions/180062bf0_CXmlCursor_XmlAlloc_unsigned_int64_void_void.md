# CXmlCursor::XmlAlloc(unsigned __int64,void * *,void *)

- ea: `0x180062bf0`
- end: `0x180062c8a`
- name: `?XmlAlloc@CXmlCursor@@KAJ_KPEAPEAXPEAX@Z`
- size: `154`
- prototype: `__int64 __fastcall(SIZE_T Size, void **, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x18001f554`
- `0x1800293a0`
- `0x180062bf0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180062c22`
- `ntdll!RtlAllocateHeap` at `0x180062c22`

## string_xrefs

- `0x180062c36`: `onecore\base\xml\udom_xmlwalker.h`
- `0x180062c50`: `CXmlCursor::XmlAlloc`
- `0x180062c61`: `*ppvAlloc = RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->ProcessHeap), 0, cb)`

## pseudocode

```c

```
