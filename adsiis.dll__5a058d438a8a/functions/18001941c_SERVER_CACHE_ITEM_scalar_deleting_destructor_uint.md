# SERVER_CACHE_ITEM::`scalar deleting destructor'(uint)

- ea: `0x18001941c`
- end: `0x18001943b`
- name: `??_GSERVER_CACHE_ITEM@@QEAAPEAXI@Z`
- size: `31`
- prototype: `void *__fastcall(SERVER_CACHE_ITEM *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180019354`
- `0x18001945c`

## callees

- `0x1800010f0`
- `0x1800193c0`

## pseudocode

```c
SERVER_CACHE_ITEM *__fastcall SERVER_CACHE_ITEM::`scalar deleting destructor'(SERVER_CACHE_ITEM *this)
{
  SERVER_CACHE_ITEM::~SERVER_CACHE_ITEM(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001941c  push    rbx
0x18001941e  sub     rsp, 20h
0x180019422  mov     rbx, rcx
0x180019425  call    ??1SERVER_CACHE_ITEM@@QEAA@XZ; SERVER_CACHE_ITEM::~SERVER_CACHE_ITEM(void)
0x18001942a  mov     rcx, rbx; Block
0x18001942d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019432  mov     rax, rbx
0x180019435  add     rsp, 20h
0x180019439  pop     rbx
0x18001943a  retn
```
