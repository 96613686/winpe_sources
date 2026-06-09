# DIGEST_CONTEXT_CACHE_ENTRY::`vector deleting destructor'(uint)

- ea: `0x180004890`
- end: `0x1800048c7`
- name: `??_EDIGEST_CONTEXT_CACHE_ENTRY@@EEAAPEAXI@Z`
- size: `55`
- prototype: `void *__fastcall(DIGEST_CONTEXT_CACHE_ENTRY *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000482c`
- `0x180004890`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x1800048b3`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x1800048b3`

## pseudocode

```c
DIGEST_CONTEXT_CACHE_ENTRY *__fastcall DIGEST_CONTEXT_CACHE_ENTRY::`vector deleting destructor'(
        DIGEST_CONTEXT_CACHE_ENTRY *this,
        char a2)
{
  DIGEST_CONTEXT_CACHE_ENTRY::~DIGEST_CONTEXT_CACHE_ENTRY(this);
  if ( (a2 & 1) != 0 )
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)DIGEST_CONTEXT_CACHE_ENTRY::sm_pachDigestContextCacheEntry, this);
  return this;
}

```

## disassembly

```asm
0x180004890  mov     [rsp+arg_0], rbx
0x180004895  push    rdi
0x180004896  sub     rsp, 20h
0x18000489a  mov     ebx, edx
0x18000489c  mov     rdi, rcx
0x18000489f  call    ??1DIGEST_CONTEXT_CACHE_ENTRY@@EEAA@XZ; DIGEST_CONTEXT_CACHE_ENTRY::~DIGEST_CONTEXT_CACHE_ENTRY(void)
0x1800048a4  test    bl, 1
0x1800048a7  jz      short loc_1800048B9
0x1800048a9  mov     rcx, cs:?sm_pachDigestContextCacheEntry@DIGEST_CONTEXT_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * DIGEST_CONTEXT_CACHE_ENTRY::sm_pachDigestContextCacheEntry
0x1800048b0  mov     rdx, rdi
0x1800048b3  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x1800048b9  mov     rbx, [rsp+28h+arg_0]
0x1800048be  mov     rax, rdi
0x1800048c1  add     rsp, 20h
0x1800048c5  pop     rdi
0x1800048c6  retn
```
