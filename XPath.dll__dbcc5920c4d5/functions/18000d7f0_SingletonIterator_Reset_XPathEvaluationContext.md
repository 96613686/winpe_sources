# SingletonIterator::Reset(XPathEvaluationContext *)

- ea: `0x18000d7f0`
- end: `0x18000d83c`
- name: `?Reset@SingletonIterator@@UEAAJPEAVXPathEvaluationContext@@@Z`
- size: `76`
- prototype: `int(SingletonIterator *__hidden this, struct XPathEvaluationContext *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800052bc`
- `0x18000d7f0`
- `0x18000e5e0`
- `0x18000e6e8`

## pseudocode

```c
__int64 __fastcall SingletonIterator::Reset(struct IUnknown **this, struct XPathEvaluationContext *a2)
{
  struct XPathNavigatorInternal *ContextNode; // rax
  __int64 result; // rax

  ContextNode = XPathEvaluationContext::QueryContextNode(a2);
  result = XPathNavigatorInternal::InitializePositionTo(this + 4, ContextNode);
  if ( (int)result >= 0 )
  {
    if ( !*((_BYTE *)this + 24)
      || (result = XPathNavigatorInternal::ResetToRoot((XPathNavigatorInternal *)(this + 4)), (int)result >= 0) )
    {
      *((_DWORD *)this + 7) = 0;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d7f0  mov     [rsp+arg_0], rbx
0x18000d7f5  push    rdi
0x18000d7f6  sub     rsp, 20h
0x18000d7fa  mov     rbx, rcx
0x18000d7fd  mov     rcx, rdx; this
0x18000d800  call    ?QueryContextNode@XPathEvaluationContext@@QEAAAEAVXPathNavigatorInternal@@XZ; XPathEvaluationContext::QueryContextNode(void)
0x18000d805  mov     rdx, rax; struct XPathNavigatorInternal *
0x18000d808  lea     rcx, [rbx+20h]; this
0x18000d80c  call    ?InitializePositionTo@XPathNavigatorInternal@@QEAAJAEAV1@@Z; XPathNavigatorInternal::InitializePositionTo(XPathNavigatorInternal &)
0x18000d811  test    eax, eax
0x18000d813  js      short loc_18000D831
0x18000d815  cmp     byte ptr [rbx+18h], 0
0x18000d819  jz      short loc_18000D828
0x18000d81b  lea     rcx, [rbx+20h]; this
0x18000d81f  call    ?ResetToRoot@XPathNavigatorInternal@@QEAAJXZ; XPathNavigatorInternal::ResetToRoot(void)
0x18000d824  test    eax, eax
0x18000d826  js      short loc_18000D831
0x18000d828  mov     dword ptr [rbx+1Ch], 0
0x18000d82f  xor     eax, eax
0x18000d831  mov     rbx, [rsp+28h+arg_0]
0x18000d836  add     rsp, 20h
0x18000d83a  pop     rdi
0x18000d83b  retn
```
