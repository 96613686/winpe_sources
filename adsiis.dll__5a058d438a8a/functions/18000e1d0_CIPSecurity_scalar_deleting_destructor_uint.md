# CIPSecurity::`scalar deleting destructor'(uint)

- ea: `0x18000e1d0`
- end: `0x18000e1ef`
- name: `??_GCIPSecurity@@QEAAPEAXI@Z`
- size: `31`
- prototype: `void *__fastcall(CIPSecurity *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e2e0`
- `0x18000e490`
- `0x18000ea80`

## callees

- `0x1800010f0`
- `0x18000e14c`

## pseudocode

```c
CIPSecurity *__fastcall CIPSecurity::`scalar deleting destructor'(CIPSecurity *this)
{
  CIPSecurity::~CIPSecurity(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000e1d0  push    rbx
0x18000e1d2  sub     rsp, 20h
0x18000e1d6  mov     rbx, rcx
0x18000e1d9  call    ??1CIPSecurity@@QEAA@XZ; CIPSecurity::~CIPSecurity(void)
0x18000e1de  mov     rcx, rbx; Block
0x18000e1e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e1e6  mov     rax, rbx
0x18000e1e9  add     rsp, 20h
0x18000e1ed  pop     rbx
0x18000e1ee  retn
```
