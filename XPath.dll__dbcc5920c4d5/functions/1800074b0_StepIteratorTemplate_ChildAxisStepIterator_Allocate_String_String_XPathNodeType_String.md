# StepIteratorTemplate<ChildAxisStepIterator>::Allocate(String &,String &,XPathNodeType,String &)

- ea: `0x1800074b0`
- end: `0x18000752c`
- name: `?Allocate@?$StepIteratorTemplate@VChildAxisStepIterator@@@@SAPEAVXPathNodeIteratorBase@@AEAVString@@0W4XPathNodeType@@0@Z`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001078`
- `0x180006440`
- `0x1800074b0`
- `0x180008b0c`
- `0x18001180a`

## pseudocode

```c
StepIteratorBase *__fastcall StepIteratorTemplate<ChildAxisStepIterator>::Allocate(
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
  *(_QWORD *)v9 = &ChildAxisStepIterator::`vftable'{for `IXPathNodeIterator'};
  *((_QWORD *)v9 + 1) = &AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'};
  StepIteratorBase::Initialize((__int64)v9, a1, a2, a3, a4);
  return v9;
}

```

## disassembly

```asm
0x1800074b0  push    rbx
0x1800074b2  push    rbp
0x1800074b3  push    rsi
0x1800074b4  push    rdi
0x1800074b5  push    r14
0x1800074b7  sub     rsp, 30h
0x1800074bb  mov     r14, rcx
0x1800074be  mov     rdi, r9
0x1800074c1  mov     ecx, 68h ; 'h'; Size
0x1800074c6  mov     esi, r8d
0x1800074c9  mov     rbp, rdx
0x1800074cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800074d1  mov     rbx, rax
0x1800074d4  test    rax, rax
0x1800074d7  jz      short loc_18000751C
0x1800074d9  xor     edx, edx; Val
0x1800074db  mov     rcx, rax; void *
0x1800074de  lea     r8d, [rdx+68h]; Size
0x1800074e2  call    memset_0
0x1800074e7  mov     rcx, rbx; this
0x1800074ea  call    ??0StepIteratorBase@@IEAA@XZ; StepIteratorBase::StepIteratorBase(void)
0x1800074ef  lea     rax, ??_7ChildAxisStepIterator@@6BIXPathNodeIterator@@@; const ChildAxisStepIterator::`vftable'{for `IXPathNodeIterator'}
0x1800074f6  mov     [rsp+58h+var_38], rdi
0x1800074fb  mov     [rbx], rax
0x1800074fe  mov     r9d, esi
0x180007501  lea     rax, ??_7AncestorOrSelfAxisStepIterator@@6BXPathExpressionBase@@@; const AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'}
0x180007508  mov     r8, rbp
0x18000750b  mov     rdx, r14
0x18000750e  mov     [rbx+8], rax
0x180007512  mov     rcx, rbx
0x180007515  call    ?Initialize@StepIteratorBase@@IEAAXAEAVString@@0W4XPathNodeType@@0@Z; StepIteratorBase::Initialize(String &,String &,XPathNodeType,String &)
0x18000751a  jmp     short loc_18000751E
0x18000751c  xor     ebx, ebx
0x18000751e  mov     rax, rbx
0x180007521  add     rsp, 30h
0x180007525  pop     r14
0x180007527  pop     rdi
0x180007528  pop     rsi
0x180007529  pop     rbp
0x18000752a  pop     rbx
0x18000752b  retn
```
