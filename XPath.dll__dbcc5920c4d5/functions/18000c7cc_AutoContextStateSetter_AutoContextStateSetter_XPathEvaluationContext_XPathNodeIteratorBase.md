# AutoContextStateSetter::AutoContextStateSetter(XPathEvaluationContext *,XPathNodeIteratorBase *)

- ea: `0x18000c7cc`
- end: `0x18000c82a`
- name: `??0AutoContextStateSetter@@QEAA@PEAVXPathEvaluationContext@@PEAVXPathNodeIteratorBase@@@Z`
- size: `94`
- prototype: `AutoContextStateSetter *(AutoContextStateSetter *__hidden this, struct XPathEvaluationContext *, struct XPathNodeIteratorBase *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d350`
- `0x18000d410`

## callees

- `0x180005510`
- `0x1800059d4`
- `0x18000c7cc`
- `0x180012010`

## pseudocode

```c
AutoContextStateSetter *__fastcall AutoContextStateSetter::AutoContextStateSetter(
        AutoContextStateSetter *this,
        struct XPathEvaluationContext *a2,
        struct XPathNodeIteratorBase *a3)
{
  struct XPathNodeIteratorBase *v5; // rax

  *(_QWORD *)this = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct XPathEvaluationContext *))(*(_QWORD *)a2 + 8LL))(a2);
  *((_QWORD *)this + 1) = 0;
  v5 = XPathEvaluationContext::SetContextState(*(XPathEvaluationContext **)this, a3);
  InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>((_QWORD *)this + 1, (__int64)v5);
  return this;
}

```

## disassembly

```asm
0x18000c7cc  mov     [rsp+arg_0], rbx
0x18000c7d1  mov     [rsp+arg_8], rsi
0x18000c7d6  push    rdi
0x18000c7d7  sub     rsp, 20h
0x18000c7db  mov     [rcx], rdx
0x18000c7de  mov     rsi, r8
0x18000c7e1  mov     rdi, rcx
0x18000c7e4  test    rdx, rdx
0x18000c7e7  jz      short loc_18000C7F8
0x18000c7e9  mov     rax, [rdx]
0x18000c7ec  mov     rcx, rdx
0x18000c7ef  mov     rax, [rax+8]
0x18000c7f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7f8  mov     qword ptr [rdi+8], 0
0x18000c800  mov     rdx, rsi; struct XPathNodeIteratorBase *
0x18000c803  mov     rcx, [rdi]; this
0x18000c806  call    ?SetContextState@XPathEvaluationContext@@AEAAPEAVXPathNodeIteratorBase@@PEAV2@@Z; XPathEvaluationContext::SetContextState(XPathNodeIteratorBase *)
0x18000c80b  mov     rdx, rax
0x18000c80e  lea     rcx, [rdi+8]
0x18000c812  call    ??$?4VXPathNodeIteratorBase@@@?$InvasivePtr@VXPathNodeIteratorBase@@@@QEAAAEAV0@PEAVXPathNodeIteratorBase@@@Z; InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(XPathNodeIteratorBase *)
0x18000c817  mov     rbx, [rsp+28h+arg_0]
0x18000c81c  mov     rax, rdi
0x18000c81f  mov     rsi, [rsp+28h+arg_8]
0x18000c824  add     rsp, 20h
0x18000c828  pop     rdi
0x18000c829  retn
```
