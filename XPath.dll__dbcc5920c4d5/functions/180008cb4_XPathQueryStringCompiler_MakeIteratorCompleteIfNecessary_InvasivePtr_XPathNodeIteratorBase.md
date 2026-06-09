# XPathQueryStringCompiler::MakeIteratorCompleteIfNecessary(InvasivePtr<XPathNodeIteratorBase> &)

- ea: `0x180008cb4`
- end: `0x180008d22`
- name: `?MakeIteratorCompleteIfNecessary@XPathQueryStringCompiler@@CAJAEAV?$InvasivePtr@VXPathNodeIteratorBase@@@@@Z`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008c24`
- `0x1800094f4`

## callees

- `0x1800054e0`
- `0x1800059d4`
- `0x1800081e4`
- `0x180008cb4`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::MakeIteratorCompleteIfNecessary(struct XPathNodeIteratorBase **a1)
{
  struct XPathNodeIteratorBase *v2; // rcx
  int v3; // ebx
  struct XPathNodeIteratorBase *v5; // [rsp+30h] [rbp+8h] BYREF

  if ( !(*(unsigned __int8 (__fastcall **)(struct XPathNodeIteratorBase *))(*(_QWORD *)*a1 + 80LL))(*a1) )
  {
    v2 = *a1;
    v5 = 0;
    v3 = CompletionIterator::CreateInstance(v2, &v5);
    if ( v3 < 0 )
    {
      InvasivePtr<UnionExpressionIterator>::Reset(&v5);
      return (unsigned int)v3;
    }
    InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(a1, (__int64)v5);
    InvasivePtr<UnionExpressionIterator>::Reset(&v5);
  }
  return 0;
}

```

## disassembly

```asm
0x180008cb4  mov     [rsp+arg_8], rbx
0x180008cb9  push    rdi
0x180008cba  sub     rsp, 20h
0x180008cbe  mov     rdi, rcx
0x180008cc1  mov     rcx, [rcx]
0x180008cc4  mov     rax, [rcx]
0x180008cc7  mov     rax, [rax+50h]
0x180008ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cd0  test    al, al
0x180008cd2  jnz     short loc_180008D15
0x180008cd4  mov     rcx, [rdi]; struct XPathNodeIteratorBase *
0x180008cd7  lea     rdx, [rsp+28h+arg_0]; struct XPathNodeIteratorBase **
0x180008cdc  mov     [rsp+28h+arg_0], 0
0x180008ce5  call    ?CreateInstance@CompletionIterator@@SAJPEAVXPathNodeIteratorBase@@PEAPEAV2@@Z; CompletionIterator::CreateInstance(XPathNodeIteratorBase *,XPathNodeIteratorBase * *)
0x180008cea  mov     ebx, eax
0x180008cec  test    eax, eax
0x180008cee  jns     short loc_180008CFE
0x180008cf0  lea     rcx, [rsp+28h+arg_0]
0x180008cf5  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x180008cfa  mov     eax, ebx
0x180008cfc  jmp     short loc_180008D17
0x180008cfe  mov     rdx, [rsp+28h+arg_0]
0x180008d03  mov     rcx, rdi
0x180008d06  call    ??$?4VXPathNodeIteratorBase@@@?$InvasivePtr@VXPathNodeIteratorBase@@@@QEAAAEAV0@PEAVXPathNodeIteratorBase@@@Z; InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(XPathNodeIteratorBase *)
0x180008d0b  lea     rcx, [rsp+28h+arg_0]
0x180008d10  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x180008d15  xor     eax, eax
0x180008d17  mov     rbx, [rsp+28h+arg_8]
0x180008d1c  add     rsp, 20h
0x180008d20  pop     rdi
0x180008d21  retn
```
