# StepIteratorTemplate<ParentAxisStepIterator>::Allocate(String &,String &,XPathNodeType,String &)

- ea: `0x1800077f0`
- end: `0x18000786c`
- name: `?Allocate@?$StepIteratorTemplate@VParentAxisStepIterator@@@@SAPEAVXPathNodeIteratorBase@@AEAVString@@0W4XPathNodeType@@0@Z`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001078`
- `0x180006440`
- `0x1800077f0`
- `0x180008b0c`
- `0x18001180a`

## pseudocode

```c
StepIteratorBase *__fastcall StepIteratorTemplate<ParentAxisStepIterator>::Allocate(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4)
{
  StepIteratorBase *v8; // rax
  StepIteratorBase *v9; // rbx

  v8 = (StepIteratorBase *)operator new(0x68u);
  v9 = v8;
  if ( !v8 )
    return 0;
  memset_0(v8, 0, 0x68u);
  StepIteratorBase::StepIteratorBase(v9);
  *(_QWORD *)v9 = &ParentAxisStepIterator::`vftable'{for `IXPathNodeIterator'};
  *((_QWORD *)v9 + 1) = &AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'};
  StepIteratorBase::Initialize((__int64)v9, a1, a2, a3, a4);
  return v9;
}

```

## disassembly

```asm
0x1800077f0  push    rbx
0x1800077f2  push    rbp
0x1800077f3  push    rsi
0x1800077f4  push    rdi
0x1800077f5  push    r14
0x1800077f7  sub     rsp, 30h
0x1800077fb  mov     r14, rcx
0x1800077fe  mov     rdi, r9
0x180007801  mov     ecx, 68h ; 'h'; Size
0x180007806  mov     esi, r8d
0x180007809  mov     rbp, rdx
0x18000780c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007811  mov     rbx, rax
0x180007814  test    rax, rax
0x180007817  jz      short loc_18000785C
0x180007819  xor     edx, edx; Val
0x18000781b  mov     rcx, rax; void *
0x18000781e  lea     r8d, [rdx+68h]; Size
0x180007822  call    memset_0
0x180007827  mov     rcx, rbx; this
0x18000782a  call    ??0StepIteratorBase@@IEAA@XZ; StepIteratorBase::StepIteratorBase(void)
0x18000782f  lea     rax, ??_7ParentAxisStepIterator@@6BIXPathNodeIterator@@@; const ParentAxisStepIterator::`vftable'{for `IXPathNodeIterator'}
0x180007836  mov     [rsp+58h+var_38], rdi
0x18000783b  mov     [rbx], rax
0x18000783e  mov     r9d, esi
0x180007841  lea     rax, ??_7AncestorOrSelfAxisStepIterator@@6BXPathExpressionBase@@@; const AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'}
0x180007848  mov     r8, rbp
0x18000784b  mov     rdx, r14
0x18000784e  mov     [rbx+8], rax
0x180007852  mov     rcx, rbx
0x180007855  call    ?Initialize@StepIteratorBase@@IEAAXAEAVString@@0W4XPathNodeType@@0@Z; StepIteratorBase::Initialize(String &,String &,XPathNodeType,String &)
0x18000785a  jmp     short loc_18000785E
0x18000785c  xor     ebx, ebx
0x18000785e  mov     rax, rbx
0x180007861  add     rsp, 30h
0x180007865  pop     r14
0x180007867  pop     rdi
0x180007868  pop     rsi
0x180007869  pop     rbp
0x18000786a  pop     rbx
0x18000786b  retn
```
