# XPathQueryStringCompiler::ProcessNode(VariableReference__DollarSign_QName *)

- ea: `0x180009b1c`
- end: `0x180009bf3`
- name: `?ProcessNode@XPathQueryStringCompiler@@QEAAJPEAVVariableReference__DollarSign_QName@@@Z`
- size: `215`
- prototype: `int(XPathQueryStringCompiler *__hidden this, struct VariableReference__DollarSign_QName *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800020a0`

## callees

- `0x18000588c`
- `0x180006770`
- `0x18000835c`
- `0x180009b1c`
- `0x18000a3a8`
- `0x18000f690`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::ProcessNode(XPathQueryStringCompiler *this, Node *a2)
{
  struct XPathExpressionBase **v3; // rbp
  struct Node *AddRef; // rdx
  int v6; // ebx
  unsigned __int16 *v7; // rdx
  unsigned __int16 *v8; // r8
  int VariableReferenceExpressionInternal; // eax
  unsigned int Length; // ebx
  unsigned int v11; // eax
  unsigned __int16 *v13; // [rsp+20h] [rbp-38h] BYREF
  unsigned __int16 *v14; // [rsp+28h] [rbp-30h]

  v3 = (struct XPathExpressionBase **)*((_QWORD *)this + 5);
  AddRef = (struct Node *)a2[2].lpVtbl->AddRef;
  *((_QWORD *)this + 5) = &v13;
  v13 = 0;
  v14 = 0;
  *((_DWORD *)this + 12) = 8;
  v6 = XPathQueryStringCompiler::Dispatch(this, AddRef);
  if ( v6 >= 0 )
  {
    v7 = (unsigned __int16 *)&qword_180016F98;
    v8 = (unsigned __int16 *)&qword_180016F98;
    if ( v14 )
      v8 = v14;
    if ( v13 )
      v7 = v13;
    VariableReferenceExpressionInternal = XPathEvaluationContext::TryCreateVariableReferenceExpressionInternal(
                                            *((struct IXPathEvaluationContextExtension **)this + 7),
                                            v7,
                                            v8,
                                            v3);
    v6 = VariableReferenceExpressionInternal;
    if ( VariableReferenceExpressionInternal >= 0 )
    {
      if ( VariableReferenceExpressionInternal == 1 )
      {
        Length = Node::GetLength(a2);
        v11 = ((__int64 (__fastcall *)(Node *))a2->lpVtbl->Release)(a2);
        if ( (int)ExceptionHelpers::SetCompilationException((const unsigned __int16 **)this + 2, v11, Length, 0x68u) >= 0 )
          v6 = -2147024809;
        else
          v6 = 1;
      }
      else
      {
        v6 = 0;
      }
    }
  }
  XPathQueryStringCompiler::QNameDispatchResult::~QNameDispatchResult((XPathQueryStringCompiler::QNameDispatchResult *)&v13);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009b1c  push    rbx
0x180009b1e  push    rbp
0x180009b1f  push    rsi
0x180009b20  push    rdi
0x180009b21  sub     rsp, 38h
0x180009b25  mov     rax, [rdx+10h]
0x180009b29  mov     rsi, rdx
0x180009b2c  mov     rbp, [rcx+28h]
0x180009b30  mov     rdi, rcx
0x180009b33  mov     rdx, [rax+8]; struct Node *
0x180009b37  lea     rax, [rsp+58h+var_38]
0x180009b3c  mov     [rcx+28h], rax
0x180009b40  mov     [rsp+58h+var_38], 0
0x180009b49  mov     [rsp+58h+var_30], 0
0x180009b52  mov     dword ptr [rcx+30h], 8
0x180009b59  call    ?Dispatch@XPathQueryStringCompiler@@QEAAJPEAVNode@@@Z; XPathQueryStringCompiler::Dispatch(Node *)
0x180009b5e  mov     ebx, eax
0x180009b60  test    eax, eax
0x180009b62  js      short loc_180009BDE
0x180009b64  mov     rax, [rsp+58h+var_30]
0x180009b69  lea     rdx, qword_180016F98
0x180009b70  mov     rcx, [rdi+38h]; struct IXPathEvaluationContextExtension *
0x180009b74  test    rax, rax
0x180009b77  mov     r8, rdx
0x180009b7a  mov     r9, rbp; struct XPathExpressionBase **
0x180009b7d  cmovnz  r8, rax; unsigned __int16 *
0x180009b81  mov     rax, [rsp+58h+var_38]
0x180009b86  test    rax, rax
0x180009b89  cmovnz  rdx, rax; unsigned __int16 *
0x180009b8d  call    ?TryCreateVariableReferenceExpressionInternal@XPathEvaluationContext@@SAJPEAUIXPathEvaluationContextExtension@@PEBG1PEAPEAVXPathExpressionBase@@@Z; XPathEvaluationContext::TryCreateVariableReferenceExpressionInternal(IXPathEvaluationContextExtension *,ushort const *,ushort const *,XPathExpressionBase * *)
0x180009b92  mov     ebx, eax
0x180009b94  test    eax, eax
0x180009b96  js      short loc_180009BDE
0x180009b98  cmp     eax, 1
0x180009b9b  jnz     short loc_180009BDC
0x180009b9d  mov     rcx, rsi; this
0x180009ba0  call    ?GetLength@Node@@QEAAKXZ; Node::GetLength(void)
0x180009ba5  mov     rcx, [rsi]
0x180009ba8  mov     ebx, eax
0x180009baa  mov     rax, [rcx+10h]
0x180009bae  mov     rcx, rsi
0x180009bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bb6  lea     rcx, [rdi+10h]; struct String *
0x180009bba  mov     r9d, 68h ; 'h'; unsigned int
0x180009bc0  mov     r8d, ebx; unsigned int
0x180009bc3  mov     edx, eax; unsigned int
0x180009bc5  call    ?SetCompilationException@ExceptionHelpers@@SAJAEAVString@@KKI@Z; ExceptionHelpers::SetCompilationException(String &,ulong,ulong,uint)
0x180009bca  test    eax, eax
0x180009bcc  jns     short loc_180009BD5
0x180009bce  mov     ebx, 1
0x180009bd3  jmp     short loc_180009BDE
0x180009bd5  mov     ebx, 80070057h
0x180009bda  jmp     short loc_180009BDE
0x180009bdc  xor     ebx, ebx
0x180009bde  lea     rcx, [rsp+58h+var_38]; this
0x180009be3  call    ??1QNameDispatchResult@XPathQueryStringCompiler@@QEAA@XZ; XPathQueryStringCompiler::QNameDispatchResult::~QNameDispatchResult(void)
0x180009be8  mov     eax, ebx
0x180009bea  add     rsp, 38h
0x180009bee  pop     rdi
0x180009bef  pop     rsi
0x180009bf0  pop     rbp
0x180009bf1  pop     rbx
0x180009bf2  retn
```
