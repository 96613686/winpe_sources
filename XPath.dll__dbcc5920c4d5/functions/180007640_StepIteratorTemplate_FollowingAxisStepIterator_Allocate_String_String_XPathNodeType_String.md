# StepIteratorTemplate<FollowingAxisStepIterator>::Allocate(String &,String &,XPathNodeType,String &)

- ea: `0x180007640`
- end: `0x1800076bc`
- name: `?Allocate@?$StepIteratorTemplate@VFollowingAxisStepIterator@@@@SAPEAVXPathNodeIteratorBase@@AEAVString@@0W4XPathNodeType@@0@Z`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001078`
- `0x180006440`
- `0x180007640`
- `0x180008b0c`
- `0x18001180a`

## pseudocode

```c
StepIteratorBase *__fastcall StepIteratorTemplate<FollowingAxisStepIterator>::Allocate(
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
  *(_QWORD *)v9 = &FollowingAxisStepIterator::`vftable'{for `IXPathNodeIterator'};
  *((_QWORD *)v9 + 1) = &AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'};
  StepIteratorBase::Initialize((__int64)v9, a1, a2, a3, a4);
  return v9;
}

```

## disassembly

```asm
0x180007640  push    rbx
0x180007642  push    rbp
0x180007643  push    rsi
0x180007644  push    rdi
0x180007645  push    r14
0x180007647  sub     rsp, 30h
0x18000764b  mov     r14, rcx
0x18000764e  mov     rdi, r9
0x180007651  mov     ecx, 68h ; 'h'; Size
0x180007656  mov     esi, r8d
0x180007659  mov     rbp, rdx
0x18000765c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007661  mov     rbx, rax
0x180007664  test    rax, rax
0x180007667  jz      short loc_1800076AC
0x180007669  xor     edx, edx; Val
0x18000766b  mov     rcx, rax; void *
0x18000766e  lea     r8d, [rdx+68h]; Size
0x180007672  call    memset_0
0x180007677  mov     rcx, rbx; this
0x18000767a  call    ??0StepIteratorBase@@IEAA@XZ; StepIteratorBase::StepIteratorBase(void)
0x18000767f  lea     rax, ??_7FollowingAxisStepIterator@@6BIXPathNodeIterator@@@; const FollowingAxisStepIterator::`vftable'{for `IXPathNodeIterator'}
0x180007686  mov     [rsp+58h+var_38], rdi
0x18000768b  mov     [rbx], rax
0x18000768e  mov     r9d, esi
0x180007691  lea     rax, ??_7AncestorOrSelfAxisStepIterator@@6BXPathExpressionBase@@@; const AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'}
0x180007698  mov     r8, rbp
0x18000769b  mov     rdx, r14
0x18000769e  mov     [rbx+8], rax
0x1800076a2  mov     rcx, rbx
0x1800076a5  call    ?Initialize@StepIteratorBase@@IEAAXAEAVString@@0W4XPathNodeType@@0@Z; StepIteratorBase::Initialize(String &,String &,XPathNodeType,String &)
0x1800076aa  jmp     short loc_1800076AE
0x1800076ac  xor     ebx, ebx
0x1800076ae  mov     rax, rbx
0x1800076b1  add     rsp, 30h
0x1800076b5  pop     r14
0x1800076b7  pop     rdi
0x1800076b8  pop     rsi
0x1800076b9  pop     rbp
0x1800076ba  pop     rbx
0x1800076bb  retn
```
