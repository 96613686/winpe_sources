# XPathEvaluationContext::`vector deleting destructor'(uint)

- ea: `0x1800035f0`
- end: `0x18000361f`
- name: `??_EXPathEvaluationContext@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(XPathEvaluationContext *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x1800010b8`
- `0x1800033e8`
- `0x1800035f0`

## pseudocode

```c
XPathEvaluationContext *__fastcall XPathEvaluationContext::`vector deleting destructor'(
        XPathEvaluationContext *this,
        char a2)
{
  XPathEvaluationContext::~XPathEvaluationContext(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800035f0  mov     [rsp+arg_0], rbx
0x1800035f5  push    rdi
0x1800035f6  sub     rsp, 20h
0x1800035fa  mov     ebx, edx
0x1800035fc  mov     rdi, rcx
0x1800035ff  call    ??1XPathEvaluationContext@@UEAA@XZ; XPathEvaluationContext::~XPathEvaluationContext(void)
0x180003604  test    bl, 1
0x180003607  jz      short loc_180003611
0x180003609  mov     rcx, rdi; Block
0x18000360c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003611  mov     rbx, [rsp+28h+arg_0]
0x180003616  mov     rax, rdi
0x180003619  add     rsp, 20h
0x18000361d  pop     rdi
0x18000361e  retn
```
