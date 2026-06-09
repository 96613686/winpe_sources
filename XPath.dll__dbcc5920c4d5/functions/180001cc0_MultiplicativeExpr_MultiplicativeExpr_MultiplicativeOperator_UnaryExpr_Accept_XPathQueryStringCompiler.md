# MultiplicativeExpr__MultiplicativeExpr_MultiplicativeOperator_UnaryExpr::Accept(XPathQueryStringCompiler *)

- ea: `0x180001cc0`
- end: `0x180001d2f`
- name: `?Accept@MultiplicativeExpr__MultiplicativeExpr_MultiplicativeOperator_UnaryExpr@@UEAAJPEAVXPathQueryStringCompiler@@@Z`
- size: `111`
- prototype: `int(MultiplicativeExpr__MultiplicativeExpr_MultiplicativeOperator_UnaryExpr *__hidden this, struct XPathQueryStringCompiler *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001cc0`
- `0x1800083b4`
- `0x180008d28`

## pseudocode

```c
__int64 __fastcall MultiplicativeExpr__MultiplicativeExpr_MultiplicativeOperator_UnaryExpr::Accept(
        MultiplicativeExpr__MultiplicativeExpr_MultiplicativeOperator_UnaryExpr *this,
        struct XPathQueryStringCompiler *a2)
{
  struct Node *v2; // rbp
  unsigned __int16 v4; // bx
  struct NodeVtbl *lpVtbl; // rsi
  struct Node *AddRef; // r15

  v2 = (struct Node *)*((_QWORD *)this + 2);
  v4 = 0;
  lpVtbl = v2[1].lpVtbl;
  AddRef = (struct Node *)lpVtbl->AddRef;
  while ( v4 < 3u )
  {
    if ( WideCharStringTemplate<String>::Equals((const WCHAR **)&lpVtbl->Invoke, (&off_1800191B0)[2 * v4]) )
      return XPathQueryStringCompiler::ProcessBinaryArithmeticExpression(
               a2,
               v2,
               AddRef,
               (double (*)(double, double))*(&off_1800191B0 + 2 * v4 + 1));
    ++v4;
  }
  return 0;
}

```

## disassembly

```asm
0x180001cc0  push    rbx
0x180001cc2  push    rbp
0x180001cc3  push    rsi
0x180001cc4  push    rdi
0x180001cc5  push    r12
0x180001cc7  push    r14
0x180001cc9  push    r15
0x180001ccb  sub     rsp, 20h
0x180001ccf  mov     rbp, [rcx+10h]
0x180001cd3  lea     r12, off_1800191B0; "*"
0x180001cda  mov     r14, rdx
0x180001cdd  xor     ebx, ebx
0x180001cdf  mov     rsi, [rbp+8]
0x180001ce3  mov     r15, [rsi+8]
0x180001ce7  cmp     bx, 3
0x180001ceb  jnb     short loc_180001D1E
0x180001ced  movzx   edi, bx
0x180001cf0  lea     rcx, [rsi+30h]
0x180001cf4  add     rdi, rdi
0x180001cf7  mov     rdx, [r12+rdi*8]
0x180001cfb  call    ?Equals@?$WideCharStringTemplate@VString@@@@QEBA_NPEBG@Z; WideCharStringTemplate<String>::Equals(ushort const *)
0x180001d00  test    al, al
0x180001d02  jnz     short loc_180001D09
0x180001d04  inc     bx
0x180001d07  jmp     short loc_180001CE7
0x180001d09  mov     r9, [r12+rdi*8+8]; double (*)(double, double)
0x180001d0e  mov     r8, r15; struct Node *
0x180001d11  mov     rdx, rbp; struct Node *
0x180001d14  mov     rcx, r14; this
0x180001d17  call    ?ProcessBinaryArithmeticExpression@XPathQueryStringCompiler@@AEAAJPEAVNode@@0P6ANNN@Z@Z; XPathQueryStringCompiler::ProcessBinaryArithmeticExpression(Node *,Node *,double (*)(double,double))
0x180001d1c  jmp     short loc_180001D20
0x180001d1e  xor     eax, eax
0x180001d20  add     rsp, 20h
0x180001d24  pop     r15
0x180001d26  pop     r14
0x180001d28  pop     r12
0x180001d2a  pop     rdi
0x180001d2b  pop     rsi
0x180001d2c  pop     rbp
0x180001d2d  pop     rbx
0x180001d2e  retn
```
