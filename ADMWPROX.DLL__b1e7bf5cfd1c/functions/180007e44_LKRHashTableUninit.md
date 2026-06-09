# LKRHashTableUninit

- ea: `0x180007e44`
- end: `0x180007f13`
- name: `LKRHashTableUninit`
- size: `207`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180006e00`
- `0x180007c70`

## callees

- `0x180001124`
- `0x180007604`
- `0x180007e44`

## pseudocode

```c
void LKRHashTableUninit()
{
  ALLOC_CACHE_HANDLER *v0; // rbx
  ALLOC_CACHE_HANDLER *v1; // rbx
  ALLOC_CACHE_HANDLER *v2; // rbx
  ALLOC_CACHE_HANDLER *v3; // rbx
  ALLOC_CACHE_HANDLER *v4; // rbx

  v0 = CLKRLinearHashTable::sm_palloc;
  if ( CLKRLinearHashTable::sm_palloc )
  {
    ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((void **)CLKRLinearHashTable::sm_palloc);
    operator delete(v0);
    CLKRLinearHashTable::sm_palloc = 0;
  }
  v1 = CNodeClump::sm_palloc;
  if ( CNodeClump::sm_palloc )
  {
    ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((void **)CNodeClump::sm_palloc);
    operator delete(v1);
    CNodeClump::sm_palloc = 0;
  }
  v2 = CSmallSegment::sm_palloc;
  if ( CSmallSegment::sm_palloc )
  {
    ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((void **)CSmallSegment::sm_palloc);
    operator delete(v2);
    CSmallSegment::sm_palloc = 0;
  }
  v3 = CMediumSegment::sm_palloc;
  if ( CMediumSegment::sm_palloc )
  {
    ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((void **)CMediumSegment::sm_palloc);
    operator delete(v3);
    CMediumSegment::sm_palloc = 0;
  }
  v4 = CLargeSegment::sm_palloc;
  if ( CLargeSegment::sm_palloc )
  {
    ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((void **)CLargeSegment::sm_palloc);
    operator delete(v4);
    CLargeSegment::sm_palloc = 0;
  }
}

```

## disassembly

```asm
0x180007e44  push    rbx
0x180007e46  sub     rsp, 20h
0x180007e4a  mov     rbx, cs:?sm_palloc@CLKRLinearHashTable@@1PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CLKRLinearHashTable::sm_palloc
0x180007e51  test    rbx, rbx
0x180007e54  jz      short loc_180007E71
0x180007e56  mov     rcx, rbx; this
0x180007e59  call    ??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x180007e5e  mov     rcx, rbx; Block
0x180007e61  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007e66  mov     cs:?sm_palloc@CLKRLinearHashTable@@1PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * CLKRLinearHashTable::sm_palloc
0x180007e71  mov     rbx, cs:?sm_palloc@CNodeClump@@1PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CNodeClump::sm_palloc
0x180007e78  test    rbx, rbx
0x180007e7b  jz      short loc_180007E98
0x180007e7d  mov     rcx, rbx; this
0x180007e80  call    ??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x180007e85  mov     rcx, rbx; Block
0x180007e88  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007e8d  mov     cs:?sm_palloc@CNodeClump@@1PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * CNodeClump::sm_palloc
0x180007e98  mov     rbx, cs:?sm_palloc@CSmallSegment@@1PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CSmallSegment::sm_palloc
0x180007e9f  test    rbx, rbx
0x180007ea2  jz      short loc_180007EBF
0x180007ea4  mov     rcx, rbx; this
0x180007ea7  call    ??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x180007eac  mov     rcx, rbx; Block
0x180007eaf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007eb4  mov     cs:?sm_palloc@CSmallSegment@@1PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * CSmallSegment::sm_palloc
0x180007ebf  mov     rbx, cs:?sm_palloc@CMediumSegment@@1PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CMediumSegment::sm_palloc
0x180007ec6  test    rbx, rbx
0x180007ec9  jz      short loc_180007EE6
0x180007ecb  mov     rcx, rbx; this
0x180007ece  call    ??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x180007ed3  mov     rcx, rbx; Block
0x180007ed6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007edb  mov     cs:?sm_palloc@CMediumSegment@@1PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * CMediumSegment::sm_palloc
0x180007ee6  mov     rbx, cs:?sm_palloc@CLargeSegment@@1PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CLargeSegment::sm_palloc
0x180007eed  test    rbx, rbx
0x180007ef0  jz      short loc_180007F0D
0x180007ef2  mov     rcx, rbx; this
0x180007ef5  call    ??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x180007efa  mov     rcx, rbx; Block
0x180007efd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007f02  mov     cs:?sm_palloc@CLargeSegment@@1PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * CLargeSegment::sm_palloc
0x180007f0d  add     rsp, 20h
0x180007f11  pop     rbx
0x180007f12  retn
```
