# XPathEvaluationContext::SetContextState(XPathNodeIteratorBase *)

- ea: `0x180005510`
- end: `0x18000553f`
- name: `?SetContextState@XPathEvaluationContext@@AEAAPEAVXPathNodeIteratorBase@@PEAV2@@Z`
- size: `47`
- prototype: `struct XPathNodeIteratorBase *__fastcall(XPathEvaluationContext *__hidden this, struct XPathNodeIteratorBase *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c7cc`
- `0x18000c830`

## callees

- `0x1800054e0`
- `0x180005510`

## pseudocode

```c
struct XPathNodeIteratorBase *__fastcall XPathEvaluationContext::SetContextState(
        XPathEvaluationContext *this,
        struct XPathNodeIteratorBase *a2)
{
  __int64 v2; // rbx
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 3);
  v4 = v2;
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 16));
  *((_QWORD *)this + 3) = a2;
  InvasivePtr<UnionExpressionIterator>::Reset(&v4);
  return (struct XPathNodeIteratorBase *)v2;
}

```

## disassembly

```asm
0x180005510  push    rbx
0x180005512  sub     rsp, 20h
0x180005516  mov     rbx, [rcx+18h]
0x18000551a  mov     [rsp+28h+arg_0], rbx
0x18000551f  test    rbx, rbx
0x180005522  jz      short loc_180005528
0x180005524  lock inc dword ptr [rbx+10h]
0x180005528  mov     [rcx+18h], rdx
0x18000552c  lea     rcx, [rsp+28h+arg_0]
0x180005531  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x180005536  mov     rax, rbx
0x180005539  add     rsp, 20h
0x18000553d  pop     rbx
0x18000553e  retn
```
