# StepIteratorTemplate<AncestorOrSelfAxisStepIterator>::Allocate(String &,String &,XPathNodeType,String &)

- ea: `0x180007390`
- end: `0x18000740c`
- name: `?Allocate@?$StepIteratorTemplate@VAncestorOrSelfAxisStepIterator@@@@SAPEAVXPathNodeIteratorBase@@AEAVString@@0W4XPathNodeType@@0@Z`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c8d0`

## callees

- `0x180001078`
- `0x180006440`
- `0x180007390`
- `0x180008b0c`
- `0x18001180a`

## pseudocode

```c
StepIteratorBase *__fastcall StepIteratorTemplate<AncestorOrSelfAxisStepIterator>::Allocate(
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
  *(_QWORD *)v9 = &AncestorOrSelfAxisStepIterator::`vftable'{for `IXPathNodeIterator'};
  *((_QWORD *)v9 + 1) = &AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'};
  StepIteratorBase::Initialize((__int64)v9, a1, a2, a3, a4);
  return v9;
}

```

## disassembly

```asm
0x180007390  push    rbx
0x180007392  push    rbp
0x180007393  push    rsi
0x180007394  push    rdi
0x180007395  push    r14
0x180007397  sub     rsp, 30h
0x18000739b  mov     r14, rcx
0x18000739e  mov     rdi, r9
0x1800073a1  mov     ecx, 68h ; 'h'; Size
0x1800073a6  mov     esi, r8d
0x1800073a9  mov     rbp, rdx
0x1800073ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800073b1  mov     rbx, rax
0x1800073b4  test    rax, rax
0x1800073b7  jz      short loc_1800073FC
0x1800073b9  xor     edx, edx; Val
0x1800073bb  mov     rcx, rax; void *
0x1800073be  lea     r8d, [rdx+68h]; Size
0x1800073c2  call    memset_0
0x1800073c7  mov     rcx, rbx; this
0x1800073ca  call    ??0StepIteratorBase@@IEAA@XZ; StepIteratorBase::StepIteratorBase(void)
0x1800073cf  lea     rax, ??_7AncestorOrSelfAxisStepIterator@@6BIXPathNodeIterator@@@; const AncestorOrSelfAxisStepIterator::`vftable'{for `IXPathNodeIterator'}
0x1800073d6  mov     [rsp+58h+var_38], rdi
0x1800073db  mov     [rbx], rax
0x1800073de  mov     r9d, esi
0x1800073e1  lea     rax, ??_7AncestorOrSelfAxisStepIterator@@6BXPathExpressionBase@@@; const AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'}
0x1800073e8  mov     r8, rbp
0x1800073eb  mov     rdx, r14
0x1800073ee  mov     [rbx+8], rax
0x1800073f2  mov     rcx, rbx
0x1800073f5  call    ?Initialize@StepIteratorBase@@IEAAXAEAVString@@0W4XPathNodeType@@0@Z; StepIteratorBase::Initialize(String &,String &,XPathNodeType,String &)
0x1800073fa  jmp     short loc_1800073FE
0x1800073fc  xor     ebx, ebx
0x1800073fe  mov     rax, rbx
0x180007401  add     rsp, 30h
0x180007405  pop     r14
0x180007407  pop     rdi
0x180007408  pop     rsi
0x180007409  pop     rbp
0x18000740a  pop     rbx
0x18000740b  retn
```
