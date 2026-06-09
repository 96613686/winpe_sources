# PWGRCore::CPWGRStreamWriter::`vector deleting destructor'(uint)

- ea: `0x18000a390`
- end: `0x18000a3c4`
- name: `??_ECPWGRStreamWriter@PWGRCore@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(PWGRCore::CPWGRStreamWriter *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001b30`
- `0x18000a22c`
- `0x18000a390`

## pseudocode

```c
PWGRCore::CPWGRStreamWriter *__fastcall PWGRCore::CPWGRStreamWriter::`vector deleting destructor'(
        PWGRCore::CPWGRStreamWriter *this,
        char a2)
{
  PWGRCore::CPWGRStreamWriter::~CPWGRStreamWriter(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000a390  mov     [rsp+arg_0], rbx
0x18000a395  push    rdi
0x18000a396  sub     rsp, 20h
0x18000a39a  mov     ebx, edx
0x18000a39c  mov     rdi, rcx
0x18000a39f  call    ??1CPWGRStreamWriter@PWGRCore@@UEAA@XZ; PWGRCore::CPWGRStreamWriter::~CPWGRStreamWriter(void)
0x18000a3a4  test    bl, 1
0x18000a3a7  jz      short loc_18000A3B6
0x18000a3a9  mov     edx, 48h ; 'H'; unsigned __int64
0x18000a3ae  mov     rcx, rdi; void *
0x18000a3b1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a3b6  mov     rbx, [rsp+28h+arg_0]
0x18000a3bb  mov     rax, rdi
0x18000a3be  add     rsp, 20h
0x18000a3c2  pop     rdi
0x18000a3c3  retn
```
