# TEMPFILEINFO::`vector deleting destructor'(uint)

- ea: `0x180009500`
- end: `0x18000952f`
- name: `??_ETEMPFILEINFO@@EEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(TEMPFILEINFO *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001fbc`
- `0x1800093f0`
- `0x180009500`

## pseudocode

```c
TEMPFILEINFO *__fastcall TEMPFILEINFO::`vector deleting destructor'(TEMPFILEINFO *this, char a2)
{
  TEMPFILEINFO::~TEMPFILEINFO(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180009500  mov     [rsp+arg_0], rbx
0x180009505  push    rdi
0x180009506  sub     rsp, 20h
0x18000950a  mov     ebx, edx
0x18000950c  mov     rdi, rcx
0x18000950f  call    ??1TEMPFILEINFO@@EEAA@XZ; TEMPFILEINFO::~TEMPFILEINFO(void)
0x180009514  test    bl, 1
0x180009517  jz      short loc_180009521
0x180009519  mov     rcx, rdi; Block
0x18000951c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009521  mov     rbx, [rsp+28h+arg_0]
0x180009526  mov     rax, rdi
0x180009529  add     rsp, 20h
0x18000952d  pop     rdi
0x18000952e  retn
```
