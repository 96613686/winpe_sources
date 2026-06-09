# StepIteratorBase::Reset(XPathEvaluationContext *)

- ea: `0x18000d8a0`
- end: `0x18000d96a`
- name: `?Reset@StepIteratorBase@@UEAAJPEAVXPathEvaluationContext@@@Z`
- size: `202`
- prototype: `int(StepIteratorBase *__hidden this, struct XPathEvaluationContext *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800020b4`
- `0x1800052bc`
- `0x18000d8a0`
- `0x18000e5e0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall StepIteratorBase::Reset(StepIteratorBase *this, struct XPathEvaluationContext *a2)
{
  struct XPathNavigatorInternal *ContextNode; // rax
  int v5; // edi
  const unsigned __int16 *v6; // rbp
  const unsigned __int16 *v7; // rdx
  struct XPathNavigatorInternal *v8; // rax
  __int64 v10; // [rsp+50h] [rbp+8h] BYREF

  *((_WORD *)this + 12) = 1;
  *(_QWORD *)((char *)this + 28) = 0;
  v10 = 0;
  ContextNode = XPathEvaluationContext::QueryContextNode(a2);
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)ContextNode + 24LL))(*(_QWORD *)ContextNode, &v10);
  if ( v5 >= 0 )
  {
    v6 = &qword_180016F98;
    v7 = &qword_180016F98;
    if ( *((_QWORD *)this + 8) )
      v7 = (const unsigned __int16 *)*((_QWORD *)this + 8);
    v5 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, char *))(*(_QWORD *)v10 + 24LL))(
           v10,
           v7,
           (char *)this + 80);
    if ( v5 >= 0 )
    {
      if ( *((_QWORD *)this + 9) )
        v6 = (const unsigned __int16 *)*((_QWORD *)this + 9);
      v5 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, char *))(*(_QWORD *)v10 + 24LL))(
             v10,
             v6,
             (char *)this + 88);
      if ( v5 >= 0 )
      {
        v8 = XPathEvaluationContext::QueryContextNode(a2);
        v5 = XPathNavigatorInternal::InitializePositionTo((struct IUnknown **)this + 5, v8);
      }
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000d8a0  push    rbx
0x18000d8a2  push    rbp
0x18000d8a3  push    rsi
0x18000d8a4  push    rdi
0x18000d8a5  sub     rsp, 28h
0x18000d8a9  mov     rbx, rcx
0x18000d8ac  mov     word ptr [rcx+18h], 1
0x18000d8b2  mov     qword ptr [rcx+1Ch], 0
0x18000d8ba  mov     rsi, rdx
0x18000d8bd  mov     rcx, rdx; this
0x18000d8c0  mov     [rsp+48h+arg_0], 0
0x18000d8c9  call    ?QueryContextNode@XPathEvaluationContext@@QEAAAEAVXPathNavigatorInternal@@XZ; XPathEvaluationContext::QueryContextNode(void)
0x18000d8ce  lea     rdx, [rsp+48h+arg_0]
0x18000d8d3  mov     rcx, [rax]
0x18000d8d6  mov     rax, [rcx]
0x18000d8d9  mov     rax, [rax+18h]
0x18000d8dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8e2  mov     edi, eax
0x18000d8e4  test    eax, eax
0x18000d8e6  js      short loc_18000D955
0x18000d8e8  mov     rcx, [rsp+48h+arg_0]
0x18000d8ed  lea     rbp, qword_180016F98
0x18000d8f4  cmp     qword ptr [rbx+40h], 0
0x18000d8f9  lea     r8, [rbx+50h]
0x18000d8fd  mov     rdx, rbp
0x18000d900  cmovnz  rdx, [rbx+40h]
0x18000d905  mov     rax, [rcx]
0x18000d908  mov     rax, [rax+18h]
0x18000d90c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d911  mov     edi, eax
0x18000d913  test    eax, eax
0x18000d915  js      short loc_18000D955
0x18000d917  mov     rcx, [rsp+48h+arg_0]
0x18000d91c  lea     r8, [rbx+58h]
0x18000d920  cmp     qword ptr [rbx+48h], 0
0x18000d925  cmovnz  rbp, [rbx+48h]
0x18000d92a  mov     rax, [rcx]
0x18000d92d  mov     rdx, rbp
0x18000d930  mov     rax, [rax+18h]
0x18000d934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d939  mov     edi, eax
0x18000d93b  test    eax, eax
0x18000d93d  js      short loc_18000D955
0x18000d93f  mov     rcx, rsi; this
0x18000d942  call    ?QueryContextNode@XPathEvaluationContext@@QEAAAEAVXPathNavigatorInternal@@XZ; XPathEvaluationContext::QueryContextNode(void)
0x18000d947  mov     rdx, rax; struct XPathNavigatorInternal *
0x18000d94a  lea     rcx, [rbx+28h]; this
0x18000d94e  call    ?InitializePositionTo@XPathNavigatorInternal@@QEAAJAEAV1@@Z; XPathNavigatorInternal::InitializePositionTo(XPathNavigatorInternal &)
0x18000d953  mov     edi, eax
0x18000d955  lea     rcx, [rsp+48h+arg_0]
0x18000d95a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d95f  mov     eax, edi
0x18000d961  add     rsp, 28h
0x18000d965  pop     rdi
0x18000d966  pop     rsi
0x18000d967  pop     rbp
0x18000d968  pop     rbx
0x18000d969  retn
```
