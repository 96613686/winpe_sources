# ShieldProvider::PathAdder::`vector deleting destructor'(uint)

- ea: `0x140003d24`
- end: `0x140003d6f`
- name: `??_EPathAdder@ShieldProvider@@UEAAPEAXI@Z`
- size: `75`
- prototype: `char *__fastcall(ShieldProvider::PathAdder *this, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140003c80`

## callees

- `0x1400015f4`
- `0x140003d24`
- `0x1400074cc`

## pseudocode

```c
char *__fastcall ShieldProvider::PathAdder::`vector deleting destructor'(ShieldProvider::PathAdder *this, char a2)
{
  ShieldProvider::PathAdder::~PathAdder(this);
  *(_QWORD *)this = &IRefCounted::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete((char *)this - 32);
  return (char *)this - 32;
}

```

## disassembly

```asm
0x140003d24  mov     [rsp+arg_0], rbx
0x140003d29  mov     [rsp+arg_8], rsi
0x140003d2e  push    rdi
0x140003d2f  sub     rsp, 20h
0x140003d33  mov     edi, edx
0x140003d35  mov     rbx, rcx
0x140003d38  call    ??1PathAdder@ShieldProvider@@UEAA@XZ; ShieldProvider::PathAdder::~PathAdder(void)
0x140003d3d  lea     rax, ??_7IRefCounted@@6B@; const IRefCounted::`vftable'
0x140003d44  mov     [rbx], rax
0x140003d47  test    dil, 1
0x140003d4b  jz      short loc_140003D5B
0x140003d4d  mov     edx, 28h ; '('; unsigned __int64
0x140003d52  lea     rcx, [rbx-20h]; void *
0x140003d56  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003d5b  mov     rsi, [rsp+28h+arg_8]
0x140003d60  lea     rax, [rbx-20h]
0x140003d64  mov     rbx, [rsp+28h+arg_0]
0x140003d69  add     rsp, 20h
0x140003d6d  pop     rdi
0x140003d6e  retn
```
