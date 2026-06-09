# CPropertyCache::`scalar deleting destructor'(uint)

- ea: `0x180002ab8`
- end: `0x180002ad7`
- name: `??_GCPropertyCache@@QEAAPEAXI@Z`
- size: `31`
- prototype: `void *__fastcall(CPropertyCache *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800029e0`
- `0x180002b00`
- `0x180004188`
- `0x180004360`

## callees

- `0x1800010f0`
- `0x18000fee8`

## pseudocode

```c
CPropertyCache *__fastcall CPropertyCache::`scalar deleting destructor'(CPropertyCache *this)
{
  CPropertyCache::~CPropertyCache(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002ab8  push    rbx
0x180002aba  sub     rsp, 20h
0x180002abe  mov     rbx, rcx
0x180002ac1  call    ??1CPropertyCache@@QEAA@XZ; CPropertyCache::~CPropertyCache(void)
0x180002ac6  mov     rcx, rbx; Block
0x180002ac9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002ace  mov     rax, rbx
0x180002ad1  add     rsp, 20h
0x180002ad5  pop     rbx
0x180002ad6  retn
```
