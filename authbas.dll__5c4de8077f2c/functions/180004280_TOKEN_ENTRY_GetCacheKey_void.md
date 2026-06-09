# TOKEN_ENTRY::GetCacheKey(void)

- ea: `0x180004280`
- end: `0x180004285`
- name: `?GetCacheKey@TOKEN_ENTRY@@UEBAPEAVIHttpCacheKey@@XZ`
- size: `5`
- prototype: `struct IHttpCacheKey *__fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
struct IHttpCacheKey *__fastcall TOKEN_ENTRY::GetCacheKey(TOKEN_ENTRY *this)
{
  return (TOKEN_ENTRY *)((char *)this + 120);
}

```

## disassembly

```asm
0x180004280  lea     rax, [rcx+78h]
0x180004284  retn
```
