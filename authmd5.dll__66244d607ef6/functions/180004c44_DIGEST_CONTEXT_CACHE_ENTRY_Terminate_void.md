# DIGEST_CONTEXT_CACHE_ENTRY::Terminate(void)

- ea: `0x180004c44`
- end: `0x180004c78`
- name: `?Terminate@DIGEST_CONTEXT_CACHE_ENTRY@@SAXXZ`
- size: `52`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x1800042d0`
- `0x180004650`

## callees

- `0x180001064`
- `0x180004c44`

## import_xrefs

- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x180004c59`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x180004c59`

## pseudocode

```c
void DIGEST_CONTEXT_CACHE_ENTRY::Terminate(void)
{
  void *v0; // rbx

  v0 = DIGEST_CONTEXT_CACHE_ENTRY::sm_pachDigestContextCacheEntry;
  if ( DIGEST_CONTEXT_CACHE_ENTRY::sm_pachDigestContextCacheEntry )
  {
    ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((ALLOC_CACHE_HANDLER *)DIGEST_CONTEXT_CACHE_ENTRY::sm_pachDigestContextCacheEntry);
    operator delete(v0);
    DIGEST_CONTEXT_CACHE_ENTRY::sm_pachDigestContextCacheEntry = 0;
  }
}

```

## disassembly

```asm
0x180004c44  push    rbx
0x180004c46  sub     rsp, 20h
0x180004c4a  mov     rbx, cs:?sm_pachDigestContextCacheEntry@DIGEST_CONTEXT_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * DIGEST_CONTEXT_CACHE_ENTRY::sm_pachDigestContextCacheEntry
0x180004c51  test    rbx, rbx
0x180004c54  jz      short loc_180004C72
0x180004c56  mov     rcx, rbx
0x180004c59  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x180004c5f  mov     rcx, rbx; Block
0x180004c62  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004c67  mov     cs:?sm_pachDigestContextCacheEntry@DIGEST_CONTEXT_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * DIGEST_CONTEXT_CACHE_ENTRY::sm_pachDigestContextCacheEntry
0x180004c72  add     rsp, 20h
0x180004c76  pop     rbx
0x180004c77  retn
```
