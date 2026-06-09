# NResampler::`scalar deleting destructor'(uint)

- ea: `0x180008e50`
- end: `0x180008e74`
- name: `??_GNResampler@@QEAAPEAXI@Z`
- size: `36`
- prototype: `void *__fastcall(NResampler *__hidden this, unsigned int)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180006cd0`
- `0x180006f00`
- `0x1800079bc`
- `0x1800087e0`
- `0x180008da0`
- `0x18000a590`
- `0x18006ea4c`
- `0x18006eac0`

## callees

- `0x1800085d0`
- `0x180008e7c`

## pseudocode

```c
NResampler *__fastcall NResampler::`scalar deleting destructor'(NResampler *this)
{
  NResampler::free(this);
  auFree(this);
  return this;
}

```

## disassembly

```asm
0x180008e50  push    rbx
0x180008e52  sub     rsp, 20h
0x180008e56  mov     rbx, rcx
0x180008e59  call    ?free@NResampler@@AEAAXXZ; NResampler::free(void)
0x180008e5e  mov     edx, 10h
0x180008e63  mov     rcx, rbx
0x180008e66  call    auFree
0x180008e6b  mov     rax, rbx
0x180008e6e  add     rsp, 20h
0x180008e72  pop     rbx
0x180008e73  retn
```
