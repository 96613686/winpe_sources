# StepCompositionIterator::StepCompositionIterator(XPathNodeIteratorBase *,XPathNodeIteratorBase *,bool)

- ea: `0x1800063d4`
- end: `0x180006438`
- name: `??0StepCompositionIterator@@QEAA@PEAVXPathNodeIteratorBase@@0_N@Z`
- size: `100`
- prototype: `StepCompositionIterator *__fastcall(StepCompositionIterator *__hidden this, struct XPathNodeIteratorBase *, struct XPathNodeIteratorBase *, bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009f24`
- `0x18000c8d0`

## callees

- `0x1800032f4`
- `0x1800063d4`

## pseudocode

```c
StepCompositionIterator *__fastcall StepCompositionIterator::StepCompositionIterator(
        StepCompositionIterator *this,
        struct XPathNodeIteratorBase *a2,
        struct XPathNodeIteratorBase *a3,
        char a4)
{
  XPathNodeIteratorBase::XPathNodeIteratorBase(this);
  *((_BYTE *)this + 24) = a4;
  *(_QWORD *)this = &StepCompositionIterator::`vftable'{for `IXPathNodeIterator'};
  *((_QWORD *)this + 1) = &StepCompositionIterator::`vftable'{for `XPathExpressionBase'};
  *((_BYTE *)this + 25) = 1;
  *((_QWORD *)this + 4) = a2;
  if ( a2 )
    _InterlockedIncrement((volatile signed __int32 *)a2 + 4);
  *((_QWORD *)this + 5) = a3;
  if ( a3 )
    _InterlockedIncrement((volatile signed __int32 *)a3 + 4);
  *((_QWORD *)this + 6) = 0;
  return this;
}

```

## disassembly

```asm
0x1800063d4  push    rbx
0x1800063d6  push    rbp
0x1800063d7  push    rsi
0x1800063d8  push    rdi
0x1800063d9  sub     rsp, 28h
0x1800063dd  mov     bl, r9b
0x1800063e0  mov     rsi, r8
0x1800063e3  mov     rbp, rdx
0x1800063e6  mov     rdi, rcx
0x1800063e9  call    ??0XPathNodeIteratorBase@@QEAA@XZ; XPathNodeIteratorBase::XPathNodeIteratorBase(void)
0x1800063ee  mov     [rdi+18h], bl
0x1800063f1  lea     rax, ??_7StepCompositionIterator@@6BIXPathNodeIterator@@@; const StepCompositionIterator::`vftable'{for `IXPathNodeIterator'}
0x1800063f8  mov     [rdi], rax
0x1800063fb  lea     rax, ??_7StepCompositionIterator@@6BXPathExpressionBase@@@; const StepCompositionIterator::`vftable'{for `XPathExpressionBase'}
0x180006402  mov     [rdi+8], rax
0x180006406  mov     byte ptr [rdi+19h], 1
0x18000640a  mov     [rdi+20h], rbp
0x18000640e  test    rbp, rbp
0x180006411  jz      short loc_180006417
0x180006413  lock inc dword ptr [rbp+10h]
0x180006417  mov     [rdi+28h], rsi
0x18000641b  test    rsi, rsi
0x18000641e  jz      short loc_180006424
0x180006420  lock inc dword ptr [rsi+10h]
0x180006424  mov     qword ptr [rdi+30h], 0
0x18000642c  mov     rax, rdi
0x18000642f  add     rsp, 28h
0x180006433  pop     rdi
0x180006434  pop     rsi
0x180006435  pop     rbp
0x180006436  pop     rbx
0x180006437  retn
```
