# XPathQueryStringCompiler::MakeIteratorCompleteIfNecessary(ATL::CComPtr<XPathExpressionBase> &)

- ea: `0x180008c24`
- end: `0x180008cad`
- name: `?MakeIteratorCompleteIfNecessary@XPathQueryStringCompiler@@CAJAEAV?$CComPtr@VXPathExpressionBase@@@ATL@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(struct IUnknown **)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001b20`
- `0x1800080b8`
- `0x180008d28`
- `0x1800097cc`

## callees

- `0x180004b84`
- `0x1800054e0`
- `0x180008bdc`
- `0x180008c24`
- `0x180008cb4`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::MakeIteratorCompleteIfNecessary(struct IUnknown **a1)
{
  unsigned __int64 v2; // r8
  int IteratorCompleteIfNecessary; // edi
  struct IUnknown *v5; // rdx
  unsigned __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  if ( XPathExpressionBase::IsNodeSet((XPathExpressionBase *)*a1) )
  {
    v2 = (unsigned __int64)&(*a1)[-1] & -(__int64)(*a1 != 0);
    v6 = v2;
    if ( v2 )
      _InterlockedIncrement((volatile signed __int32 *)(v2 + 16));
    IteratorCompleteIfNecessary = XPathQueryStringCompiler::MakeIteratorCompleteIfNecessary(&v6);
    if ( IteratorCompleteIfNecessary < 0 )
    {
      InvasivePtr<UnionExpressionIterator>::Reset(&v6);
      return (unsigned int)IteratorCompleteIfNecessary;
    }
    v5 = (struct IUnknown *)((v6 + 8) & ((unsigned __int128)-(__int128)v6 >> 64));
    if ( *a1 != v5 )
      ATL::AtlComPtrAssign(a1, v5);
    InvasivePtr<UnionExpressionIterator>::Reset(&v6);
  }
  return 0;
}

```

## disassembly

```asm
0x180008c24  mov     [rsp+arg_8], rbx
0x180008c29  push    rdi
0x180008c2a  sub     rsp, 20h
0x180008c2e  mov     rbx, rcx
0x180008c31  mov     rcx, [rcx]; this
0x180008c34  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x180008c39  test    al, al
0x180008c3b  jz      short loc_180008CA0
0x180008c3d  mov     rax, [rbx]
0x180008c40  lea     rdx, [rax-8]
0x180008c44  neg     rax
0x180008c47  sbb     r8, r8
0x180008c4a  and     r8, rdx
0x180008c4d  mov     [rsp+28h+arg_0], r8
0x180008c52  jz      short loc_180008C59
0x180008c54  lock inc dword ptr [r8+10h]
0x180008c59  lea     rcx, [rsp+28h+arg_0]
0x180008c5e  call    ?MakeIteratorCompleteIfNecessary@XPathQueryStringCompiler@@CAJAEAV?$InvasivePtr@VXPathNodeIteratorBase@@@@@Z; XPathQueryStringCompiler::MakeIteratorCompleteIfNecessary(InvasivePtr<XPathNodeIteratorBase> &)
0x180008c63  mov     edi, eax
0x180008c65  test    eax, eax
0x180008c67  jns     short loc_180008C77
0x180008c69  lea     rcx, [rsp+28h+arg_0]
0x180008c6e  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x180008c73  mov     eax, edi
0x180008c75  jmp     short loc_180008CA2
0x180008c77  mov     rax, [rsp+28h+arg_0]
0x180008c7c  lea     rcx, [rax+8]
0x180008c80  neg     rax
0x180008c83  sbb     rdx, rdx
0x180008c86  and     rdx, rcx; struct IUnknown *
0x180008c89  cmp     [rbx], rdx
0x180008c8c  jz      short loc_180008C96
0x180008c8e  mov     rcx, rbx; struct IUnknown **
0x180008c91  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180008c96  lea     rcx, [rsp+28h+arg_0]
0x180008c9b  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x180008ca0  xor     eax, eax
0x180008ca2  mov     rbx, [rsp+28h+arg_8]
0x180008ca7  add     rsp, 20h
0x180008cab  pop     rdi
0x180008cac  retn
```
