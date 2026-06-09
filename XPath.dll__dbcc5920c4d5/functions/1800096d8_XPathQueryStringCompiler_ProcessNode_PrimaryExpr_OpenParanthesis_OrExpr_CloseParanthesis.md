# XPathQueryStringCompiler::ProcessNode(PrimaryExpr__OpenParanthesis_OrExpr_CloseParanthesis *)

- ea: `0x1800096d8`
- end: `0x1800097c4`
- name: `?ProcessNode@XPathQueryStringCompiler@@QEAAJPEAVPrimaryExpr__OpenParanthesis_OrExpr_CloseParanthesis@@@Z`
- size: `236`
- prototype: `__int64 __fastcall(XPathQueryStringCompiler *__hidden this, struct PrimaryExpr__OpenParanthesis_OrExpr_CloseParanthesis *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001f00`

## callees

- `0x180001078`
- `0x1800032f4`
- `0x1800054e0`
- `0x180007f5c`
- `0x18000835c`
- `0x180008bdc`
- `0x1800096d8`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::ProcessNode(
        XPathQueryStringCompiler *this,
        struct PrimaryExpr__OpenParanthesis_OrExpr_CloseParanthesis *a2)
{
  __int64 *v2; // r14
  __int64 result; // rax
  volatile signed __int32 *v4; // rdi
  __int64 v5; // rsi
  XPathNodeIteratorBase *v6; // rax
  XPathNodeIteratorBase *v7; // rbx
  volatile signed __int32 *v8; // [rsp+50h] [rbp+8h] BYREF

  v2 = (__int64 *)*((_QWORD *)this + 5);
  result = XPathQueryStringCompiler::Dispatch(this, *(struct Node **)(*((_QWORD *)a2 + 2) + 8LL));
  if ( (int)result >= 0 )
  {
    if ( XPathExpressionBase::IsNodeSet((XPathExpressionBase *)*v2) )
    {
      v4 = (volatile signed __int32 *)((*v2 - 8) & -(__int64)(*v2 != 0));
      v8 = v4;
      if ( v4 )
      {
        v5 = (__int64)(v4 + 4);
        _InterlockedIncrement(v4 + 4);
      }
      else
      {
        v5 = 16;
      }
      if ( !(*(unsigned __int8 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 88LL))(v4) )
      {
        v6 = (XPathNodeIteratorBase *)operator new(0x20u);
        v7 = v6;
        if ( v6 )
        {
          XPathNodeIteratorBase::XPathNodeIteratorBase(v6);
          *(_QWORD *)v7 = &ForwardAxisIterator::`vftable'{for `IXPathNodeIterator'};
          *((_QWORD *)v7 + 1) = &ForwardAxisIterator::`vftable'{for `XPathExpressionBase'};
          *((_QWORD *)v7 + 3) = v4;
          if ( v4 )
            _InterlockedIncrement((volatile signed __int32 *)v5);
        }
        else
        {
          v7 = 0;
        }
        ATL::CComPtrBase<StepCompositionIterator>::Attach(v2, ((unsigned __int64)v7 + 8) & -(__int64)(v7 != 0));
        if ( !*v2 )
        {
          InvasivePtr<UnionExpressionIterator>::Reset(&v8);
          return 2147942414LL;
        }
      }
      InvasivePtr<UnionExpressionIterator>::Reset(&v8);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800096d8  push    rbx
0x1800096da  push    rsi
0x1800096db  push    rdi
0x1800096dc  push    r14
0x1800096de  sub     rsp, 28h
0x1800096e2  mov     rdx, [rdx+10h]
0x1800096e6  mov     r14, [rcx+28h]
0x1800096ea  mov     rdx, [rdx+8]; struct Node *
0x1800096ee  call    ?Dispatch@XPathQueryStringCompiler@@QEAAJPEAVNode@@@Z; XPathQueryStringCompiler::Dispatch(Node *)
0x1800096f3  test    eax, eax
0x1800096f5  js      loc_1800097BA
0x1800096fb  mov     rcx, [r14]; this
0x1800096fe  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x180009703  test    al, al
0x180009705  jz      loc_1800097B8
0x18000970b  mov     rax, [r14]
0x18000970e  lea     rcx, [rax-8]
0x180009712  neg     rax
0x180009715  sbb     rdi, rdi
0x180009718  and     rdi, rcx
0x18000971b  mov     [rsp+48h+arg_0], rdi
0x180009720  jz      short loc_18000972B
0x180009722  lea     rsi, [rdi+10h]
0x180009726  lock inc dword ptr [rsi]
0x180009729  jmp     short loc_180009730
0x18000972b  mov     esi, 10h
0x180009730  mov     rax, [rdi]
0x180009733  mov     rcx, rdi
0x180009736  mov     rax, [rax+58h]
0x18000973a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000973f  test    al, al
0x180009741  jnz     short loc_1800097AE
0x180009743  mov     ecx, 20h ; ' '; Size
0x180009748  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000974d  mov     rbx, rax
0x180009750  test    rax, rax
0x180009753  jz      short loc_180009780
0x180009755  mov     rcx, rax; this
0x180009758  call    ??0XPathNodeIteratorBase@@QEAA@XZ; XPathNodeIteratorBase::XPathNodeIteratorBase(void)
0x18000975d  lea     rax, ??_7ForwardAxisIterator@@6BIXPathNodeIterator@@@; const ForwardAxisIterator::`vftable'{for `IXPathNodeIterator'}
0x180009764  mov     [rbx], rax
0x180009767  lea     rax, ??_7ForwardAxisIterator@@6BXPathExpressionBase@@@; const ForwardAxisIterator::`vftable'{for `XPathExpressionBase'}
0x18000976e  mov     [rbx+8], rax
0x180009772  mov     [rbx+18h], rdi
0x180009776  test    rdi, rdi
0x180009779  jz      short loc_180009782
0x18000977b  lock inc dword ptr [rsi]
0x18000977e  jmp     short loc_180009782
0x180009780  xor     ebx, ebx
0x180009782  lea     rax, [rbx+8]
0x180009786  mov     rcx, r14
0x180009789  neg     rbx
0x18000978c  sbb     rdx, rdx
0x18000978f  and     rdx, rax
0x180009792  call    ?Attach@?$CComPtrBase@VStepCompositionIterator@@@ATL@@QEAAXPEAVStepCompositionIterator@@@Z; ATL::CComPtrBase<StepCompositionIterator>::Attach(StepCompositionIterator *)
0x180009797  cmp     qword ptr [r14], 0
0x18000979b  jnz     short loc_1800097AE
0x18000979d  lea     rcx, [rsp+48h+arg_0]
0x1800097a2  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x1800097a7  mov     eax, 8007000Eh
0x1800097ac  jmp     short loc_1800097BA
0x1800097ae  lea     rcx, [rsp+48h+arg_0]
0x1800097b3  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x1800097b8  xor     eax, eax
0x1800097ba  add     rsp, 28h
0x1800097be  pop     r14
0x1800097c0  pop     rdi
0x1800097c1  pop     rsi
0x1800097c2  pop     rbx
0x1800097c3  retn
```
