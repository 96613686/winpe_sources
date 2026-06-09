# ABO_NODE::Terminate(void)

- ea: `0x1800040cc`
- end: `0x18000413a`
- name: `?Terminate@ABO_NODE@@SAXXZ`
- size: `110`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180004140`

## callees

- `0x1800029d0`
- `0x1800040cc`

## import_xrefs

- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18000411b`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18000411b`
- `iisutil!??1BIG_REF_TRACE@@QEAA@XZ` at `0x1800040f3`
- `iisutil!??1BIG_REF_TRACE@@QEAA@XZ` at `0x1800040f3`
- `iisutil!?Terminate@BIG_REF_TRACE@@QEAAJXZ` at `0x1800040de`
- `iisutil!?Terminate@BIG_REF_TRACE@@QEAAJXZ` at `0x1800040de`

## pseudocode

```c
void ABO_NODE::Terminate(void)
{
  void *v0; // rbx
  void *v1; // rbx

  if ( ABO_NODE::sm_pBigRefTrace )
  {
    BIG_REF_TRACE::Terminate((BIG_REF_TRACE *)ABO_NODE::sm_pBigRefTrace);
    v0 = ABO_NODE::sm_pBigRefTrace;
    if ( ABO_NODE::sm_pBigRefTrace )
    {
      BIG_REF_TRACE::~BIG_REF_TRACE((BIG_REF_TRACE *)ABO_NODE::sm_pBigRefTrace);
      operator delete(v0);
    }
    ABO_NODE::sm_pBigRefTrace = 0;
  }
  v1 = ABO_NODE::sm_pachAboNodes;
  if ( ABO_NODE::sm_pachAboNodes )
  {
    ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((ALLOC_CACHE_HANDLER *)ABO_NODE::sm_pachAboNodes);
    operator delete(v1);
    ABO_NODE::sm_pachAboNodes = 0;
  }
}

```

## disassembly

```asm
0x1800040cc  push    rbx
0x1800040ce  sub     rsp, 20h
0x1800040d2  mov     rcx, cs:?sm_pBigRefTrace@ABO_NODE@@0PEAVBIG_REF_TRACE@@EA; BIG_REF_TRACE * ABO_NODE::sm_pBigRefTrace
0x1800040d9  test    rcx, rcx
0x1800040dc  jz      short loc_18000410C
0x1800040de  call    cs:__imp_?Terminate@BIG_REF_TRACE@@QEAAJXZ; BIG_REF_TRACE::Terminate(void)
0x1800040e4  mov     rbx, cs:?sm_pBigRefTrace@ABO_NODE@@0PEAVBIG_REF_TRACE@@EA; BIG_REF_TRACE * ABO_NODE::sm_pBigRefTrace
0x1800040eb  test    rbx, rbx
0x1800040ee  jz      short loc_180004101
0x1800040f0  mov     rcx, rbx
0x1800040f3  call    cs:__imp_??1BIG_REF_TRACE@@QEAA@XZ; BIG_REF_TRACE::~BIG_REF_TRACE(void)
0x1800040f9  mov     rcx, rbx; Block
0x1800040fc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004101  mov     cs:?sm_pBigRefTrace@ABO_NODE@@0PEAVBIG_REF_TRACE@@EA, 0; BIG_REF_TRACE * ABO_NODE::sm_pBigRefTrace
0x18000410c  mov     rbx, cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * ABO_NODE::sm_pachAboNodes
0x180004113  test    rbx, rbx
0x180004116  jz      short loc_180004134
0x180004118  mov     rcx, rbx
0x18000411b  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x180004121  mov     rcx, rbx; Block
0x180004124  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004129  mov     cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * ABO_NODE::sm_pachAboNodes
0x180004134  add     rsp, 20h
0x180004138  pop     rbx
0x180004139  retn
```
