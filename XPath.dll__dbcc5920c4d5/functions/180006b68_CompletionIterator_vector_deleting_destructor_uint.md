# CompletionIterator::`vector deleting destructor'(uint)

- ea: `0x180006b68`
- end: `0x180006b97`
- name: `??_ECompletionIterator@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(CompletionIterator *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006960`

## callees

- `0x1800010b8`
- `0x180006618`
- `0x180006b68`

## pseudocode

```c
CompletionIterator *__fastcall CompletionIterator::`vector deleting destructor'(CompletionIterator *this, char a2)
{
  CompletionIterator::~CompletionIterator(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180006b68  mov     [rsp+arg_0], rbx
0x180006b6d  push    rdi
0x180006b6e  sub     rsp, 20h
0x180006b72  mov     ebx, edx
0x180006b74  mov     rdi, rcx
0x180006b77  call    ??1CompletionIterator@@UEAA@XZ; CompletionIterator::~CompletionIterator(void)
0x180006b7c  test    bl, 1
0x180006b7f  jz      short loc_180006B89
0x180006b81  mov     rcx, rdi; Block
0x180006b84  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006b89  mov     rbx, [rsp+28h+arg_0]
0x180006b8e  mov     rax, rdi
0x180006b91  add     rsp, 20h
0x180006b95  pop     rdi
0x180006b96  retn
```
