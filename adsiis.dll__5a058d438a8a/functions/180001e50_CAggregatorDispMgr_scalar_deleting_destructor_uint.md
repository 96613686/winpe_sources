# CAggregatorDispMgr::`scalar deleting destructor'(uint)

- ea: `0x180001e50`
- end: `0x180001e6f`
- name: `??_GCAggregatorDispMgr@@QEAAPEAXI@Z`
- size: `31`
- prototype: `void *__fastcall(CAggregatorDispMgr *__hidden this, unsigned int)`
- caller_count: `20`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001dcc`
- `0x180001ed0`
- `0x1800029e0`
- `0x180002b00`
- `0x180004188`
- `0x180004360`
- `0x1800080a8`
- `0x18000816c`
- `0x180009240`
- `0x180009350`
- `0x180009428`
- `0x1800094f8`
- `0x180009624`
- `0x18000978c`
- `0x18000dbf0`
- `0x18000dc6c`
- `0x18000e14c`
- `0x18000e2e0`
- `0x18000f740`
- `0x18000f7ac`

## callees

- `0x1800010f0`
- `0x180016af4`

## pseudocode

```c
CAggregatorDispMgr *__fastcall CAggregatorDispMgr::`scalar deleting destructor'(CAggregatorDispMgr *this)
{
  CAggregatorDispMgr::~CAggregatorDispMgr(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180001e50  push    rbx
0x180001e52  sub     rsp, 20h
0x180001e56  mov     rbx, rcx
0x180001e59  call    ??1CAggregatorDispMgr@@QEAA@XZ; CAggregatorDispMgr::~CAggregatorDispMgr(void)
0x180001e5e  mov     rcx, rbx; Block
0x180001e61  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001e66  mov     rax, rbx
0x180001e69  add     rsp, 20h
0x180001e6d  pop     rbx
0x180001e6e  retn
```
