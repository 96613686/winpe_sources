# SRCacheManager::`scalar deleting destructor'(uint)

- ea: `0x18000d534`
- end: `0x18000d558`
- name: `??_GSRCacheManager@@QEAAPEAXI@Z`
- size: `36`
- prototype: `void *__fastcall(SRCacheManager *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000d6f0`
- `0x18000d8b0`

## callees

- `0x1800022a0`
- `0x18000d504`

## pseudocode

```c
SRCacheManager *__fastcall SRCacheManager::`scalar deleting destructor'(SRCacheManager *this)
{
  SRCacheManager::~SRCacheManager(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000d534  push    rbx
0x18000d536  sub     rsp, 20h
0x18000d53a  mov     rbx, rcx
0x18000d53d  call    ??1SRCacheManager@@QEAA@XZ; SRCacheManager::~SRCacheManager(void)
0x18000d542  mov     edx, 18h; unsigned __int64
0x18000d547  mov     rcx, rbx; void *
0x18000d54a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d54f  mov     rax, rbx
0x18000d552  add     rsp, 20h
0x18000d556  pop     rbx
0x18000d557  retn
```
