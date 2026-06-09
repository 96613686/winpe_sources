# StepIteratorTemplate<FollowingSiblingAxisStepIterator>::Allocate(String &,String &,XPathNodeType,String &)

- ea: `0x1800076d0`
- end: `0x18000774c`
- name: `?Allocate@?$StepIteratorTemplate@VFollowingSiblingAxisStepIterator@@@@SAPEAVXPathNodeIteratorBase@@AEAVString@@0W4XPathNodeType@@0@Z`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001078`
- `0x180006440`
- `0x1800076d0`
- `0x180008b0c`
- `0x18001180a`

## pseudocode

```c
StepIteratorBase *__fastcall StepIteratorTemplate<FollowingSiblingAxisStepIterator>::Allocate(
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
  *(_QWORD *)v9 = &FollowingSiblingAxisStepIterator::`vftable'{for `IXPathNodeIterator'};
  *((_QWORD *)v9 + 1) = &AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'};
  StepIteratorBase::Initialize((__int64)v9, a1, a2, a3, a4);
  return v9;
}

```

## disassembly

```asm
0x1800076d0  push    rbx
0x1800076d2  push    rbp
0x1800076d3  push    rsi
0x1800076d4  push    rdi
0x1800076d5  push    r14
0x1800076d7  sub     rsp, 30h
0x1800076db  mov     r14, rcx
0x1800076de  mov     rdi, r9
0x1800076e1  mov     ecx, 68h ; 'h'; Size
0x1800076e6  mov     esi, r8d
0x1800076e9  mov     rbp, rdx
0x1800076ec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800076f1  mov     rbx, rax
0x1800076f4  test    rax, rax
0x1800076f7  jz      short loc_18000773C
0x1800076f9  xor     edx, edx; Val
0x1800076fb  mov     rcx, rax; void *
0x1800076fe  lea     r8d, [rdx+68h]; Size
0x180007702  call    memset_0
0x180007707  mov     rcx, rbx; this
0x18000770a  call    ??0StepIteratorBase@@IEAA@XZ; StepIteratorBase::StepIteratorBase(void)
0x18000770f  lea     rax, ??_7FollowingSiblingAxisStepIterator@@6BIXPathNodeIterator@@@; const FollowingSiblingAxisStepIterator::`vftable'{for `IXPathNodeIterator'}
0x180007716  mov     [rsp+58h+var_38], rdi
0x18000771b  mov     [rbx], rax
0x18000771e  mov     r9d, esi
0x180007721  lea     rax, ??_7AncestorOrSelfAxisStepIterator@@6BXPathExpressionBase@@@; const AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'}
0x180007728  mov     r8, rbp
0x18000772b  mov     rdx, r14
0x18000772e  mov     [rbx+8], rax
0x180007732  mov     rcx, rbx
0x180007735  call    ?Initialize@StepIteratorBase@@IEAAXAEAVString@@0W4XPathNodeType@@0@Z; StepIteratorBase::Initialize(String &,String &,XPathNodeType,String &)
0x18000773a  jmp     short loc_18000773E
0x18000773c  xor     ebx, ebx
0x18000773e  mov     rax, rbx
0x180007741  add     rsp, 30h
0x180007745  pop     r14
0x180007747  pop     rdi
0x180007748  pop     rsi
0x180007749  pop     rbp
0x18000774a  pop     rbx
0x18000774b  retn
```
