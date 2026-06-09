# StepIteratorTemplate<DescendantOrSelfAxisStepIterator>::Allocate(String &,String &,XPathNodeType,String &)

- ea: `0x1800075c0`
- end: `0x180007635`
- name: `?Allocate@?$StepIteratorTemplate@VDescendantOrSelfAxisStepIterator@@@@SAPEAVXPathNodeIteratorBase@@AEAVString@@0W4XPathNodeType@@0@Z`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c8d0`

## callees

- `0x180001078`
- `0x180006440`
- `0x1800075c0`
- `0x180008b0c`

## pseudocode

```c
__int64 __fastcall StepIteratorTemplate<DescendantOrSelfAxisStepIterator>::Allocate(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4)
{
  StepIteratorBase *v8; // rax
  __int64 v9; // rbx

  v8 = (StepIteratorBase *)operator new(0x70u);
  v9 = (__int64)v8;
  if ( !v8 )
    return 0;
  StepIteratorBase::StepIteratorBase(v8);
  *(_DWORD *)(v9 + 104) = 0;
  *(_QWORD *)v9 = &DescendantOrSelfAxisStepIterator::`vftable'{for `IXPathNodeIterator'};
  *(_QWORD *)(v9 + 8) = &AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'};
  StepIteratorBase::Initialize(v9, a1, a2, a3, a4);
  return v9;
}

```

## disassembly

```asm
0x1800075c0  push    rbx
0x1800075c2  push    rbp
0x1800075c3  push    rsi
0x1800075c4  push    rdi
0x1800075c5  push    r14
0x1800075c7  sub     rsp, 30h
0x1800075cb  mov     r14, rcx
0x1800075ce  mov     rdi, r9
0x1800075d1  mov     ecx, 70h ; 'p'; Size
0x1800075d6  mov     esi, r8d
0x1800075d9  mov     rbp, rdx
0x1800075dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800075e1  mov     rbx, rax
0x1800075e4  test    rax, rax
0x1800075e7  jz      short loc_180007625
0x1800075e9  mov     rcx, rax; this
0x1800075ec  call    ??0StepIteratorBase@@IEAA@XZ; StepIteratorBase::StepIteratorBase(void)
0x1800075f1  lea     rax, ??_7DescendantOrSelfAxisStepIterator@@6BIXPathNodeIterator@@@; const DescendantOrSelfAxisStepIterator::`vftable'{for `IXPathNodeIterator'}
0x1800075f8  mov     dword ptr [rbx+68h], 0
0x1800075ff  mov     [rbx], rax
0x180007602  mov     r9d, esi
0x180007605  lea     rax, ??_7AncestorOrSelfAxisStepIterator@@6BXPathExpressionBase@@@; const AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'}
0x18000760c  mov     [rsp+58h+var_38], rdi
0x180007611  mov     r8, rbp
0x180007614  mov     [rbx+8], rax
0x180007618  mov     rdx, r14
0x18000761b  mov     rcx, rbx
0x18000761e  call    ?Initialize@StepIteratorBase@@IEAAXAEAVString@@0W4XPathNodeType@@0@Z; StepIteratorBase::Initialize(String &,String &,XPathNodeType,String &)
0x180007623  jmp     short loc_180007627
0x180007625  xor     ebx, ebx
0x180007627  mov     rax, rbx
0x18000762a  add     rsp, 30h
0x18000762e  pop     r14
0x180007630  pop     rdi
0x180007631  pop     rsi
0x180007632  pop     rbp
0x180007633  pop     rbx
0x180007634  retn
```
