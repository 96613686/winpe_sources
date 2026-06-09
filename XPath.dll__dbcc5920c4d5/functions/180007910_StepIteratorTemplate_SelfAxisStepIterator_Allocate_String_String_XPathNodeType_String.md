# StepIteratorTemplate<SelfAxisStepIterator>::Allocate(String &,String &,XPathNodeType,String &)

- ea: `0x180007910`
- end: `0x18000798c`
- name: `?Allocate@?$StepIteratorTemplate@VSelfAxisStepIterator@@@@SAPEAVXPathNodeIteratorBase@@AEAVString@@0W4XPathNodeType@@0@Z`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001078`
- `0x180006440`
- `0x180007910`
- `0x180008b0c`
- `0x18001180a`

## pseudocode

```c
StepIteratorBase *__fastcall StepIteratorTemplate<SelfAxisStepIterator>::Allocate(
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
  *(_QWORD *)v9 = &SelfAxisStepIterator::`vftable'{for `IXPathNodeIterator'};
  *((_QWORD *)v9 + 1) = &AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'};
  StepIteratorBase::Initialize((__int64)v9, a1, a2, a3, a4);
  return v9;
}

```

## disassembly

```asm
0x180007910  push    rbx
0x180007912  push    rbp
0x180007913  push    rsi
0x180007914  push    rdi
0x180007915  push    r14
0x180007917  sub     rsp, 30h
0x18000791b  mov     r14, rcx
0x18000791e  mov     rdi, r9
0x180007921  mov     ecx, 68h ; 'h'; Size
0x180007926  mov     esi, r8d
0x180007929  mov     rbp, rdx
0x18000792c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007931  mov     rbx, rax
0x180007934  test    rax, rax
0x180007937  jz      short loc_18000797C
0x180007939  xor     edx, edx; Val
0x18000793b  mov     rcx, rax; void *
0x18000793e  lea     r8d, [rdx+68h]; Size
0x180007942  call    memset_0
0x180007947  mov     rcx, rbx; this
0x18000794a  call    ??0StepIteratorBase@@IEAA@XZ; StepIteratorBase::StepIteratorBase(void)
0x18000794f  lea     rax, ??_7SelfAxisStepIterator@@6BIXPathNodeIterator@@@; const SelfAxisStepIterator::`vftable'{for `IXPathNodeIterator'}
0x180007956  mov     [rsp+58h+var_38], rdi
0x18000795b  mov     [rbx], rax
0x18000795e  mov     r9d, esi
0x180007961  lea     rax, ??_7AncestorOrSelfAxisStepIterator@@6BXPathExpressionBase@@@; const AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'}
0x180007968  mov     r8, rbp
0x18000796b  mov     rdx, r14
0x18000796e  mov     [rbx+8], rax
0x180007972  mov     rcx, rbx
0x180007975  call    ?Initialize@StepIteratorBase@@IEAAXAEAVString@@0W4XPathNodeType@@0@Z; StepIteratorBase::Initialize(String &,String &,XPathNodeType,String &)
0x18000797a  jmp     short loc_18000797E
0x18000797c  xor     ebx, ebx
0x18000797e  mov     rax, rbx
0x180007981  add     rsp, 30h
0x180007985  pop     r14
0x180007987  pop     rdi
0x180007988  pop     rsi
0x180007989  pop     rbp
0x18000798a  pop     rbx
0x18000798b  retn
```
