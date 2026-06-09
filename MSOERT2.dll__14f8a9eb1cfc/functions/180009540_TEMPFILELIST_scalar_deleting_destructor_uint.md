# TEMPFILELIST::`scalar deleting destructor'(uint)

- ea: `0x180009540`
- end: `0x18000956f`
- name: `??_GTEMPFILELIST@@EEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(TEMPFILELIST *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001fbc`
- `0x18000948c`
- `0x180009540`

## pseudocode

```c
TEMPFILELIST *__fastcall TEMPFILELIST::`scalar deleting destructor'(TEMPFILELIST *this, char a2)
{
  TEMPFILELIST::~TEMPFILELIST(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180009540  mov     [rsp+arg_0], rbx
0x180009545  push    rdi
0x180009546  sub     rsp, 20h
0x18000954a  mov     ebx, edx
0x18000954c  mov     rdi, rcx
0x18000954f  call    ??1TEMPFILELIST@@EEAA@XZ; TEMPFILELIST::~TEMPFILELIST(void)
0x180009554  test    bl, 1
0x180009557  jz      short loc_180009561
0x180009559  mov     rcx, rdi; Block
0x18000955c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009561  mov     rbx, [rsp+28h+arg_0]
0x180009566  mov     rax, rdi
0x180009569  add     rsp, 20h
0x18000956d  pop     rdi
0x18000956e  retn
```
