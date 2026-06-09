# XPathQueryStringCompiler::ProcessStepNode(Node *,Node *,Node *)

- ea: `0x18000a094`
- end: `0x18000a202`
- name: `?ProcessStepNode@XPathQueryStringCompiler@@AEAAJPEAVNode@@00@Z`
- size: `366`
- prototype: `__int64 __fastcall(XPathQueryStringCompiler *__hidden this, struct Node *, struct Node *, struct Node *)`
- caller_count: `4`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001fe0`
- `0x180002000`
- `0x180002020`
- `0x180002040`

## callees

- `0x180004b84`
- `0x1800054e0`
- `0x1800059d4`
- `0x1800066f0`
- `0x18000835c`
- `0x18000a094`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::ProcessStepNode(
        XPathQueryStringCompiler *this,
        struct Node *a2,
        struct Node *a3,
        struct Node *a4)
{
  struct IUnknown **v4; // r14
  _DWORD *v5; // rsi
  int v9; // ebx
  __int64 (__fastcall *v10)(); // r15
  int v11; // eax
  struct IUnknown *v12; // r15
  struct IUnknown *v14; // [rsp+30h] [rbp-40h] BYREF
  __int64 (__fastcall *v15)(); // [rsp+38h] [rbp-38h] BYREF
  int v16; // [rsp+40h] [rbp-30h]
  __int128 v17; // [rsp+48h] [rbp-28h] BYREF
  unsigned int v18; // [rsp+58h] [rbp-18h]
  __int64 v19; // [rsp+60h] [rbp-10h] BYREF
  int v20; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v21; // [rsp+B8h] [rbp+48h] BYREF

  v4 = (struct IUnknown **)*((_QWORD *)this + 5);
  v5 = (_DWORD *)((char *)this + 48);
  v14 = 0;
  if ( a2 )
  {
    v15 = 0;
    *((_QWORD *)this + 5) = &v15;
    v16 = 7;
    *v5 = 0;
    v9 = XPathQueryStringCompiler::Dispatch(this, a2);
    if ( v9 < 0 )
      goto LABEL_13;
    v10 = v15;
    v11 = v16;
  }
  else
  {
    v10 = StepIteratorTemplate<ChildAxisStepIterator>::Allocate;
    v11 = 1;
  }
  *v5 = 1;
  *((_QWORD *)this + 5) = &v17;
  v20 = v11;
  v19 = 0;
  *((_DWORD *)this + 8) = 2;
  v17 = 0;
  *((_QWORD *)this + 3) = &v20;
  v9 = XPathQueryStringCompiler::Dispatch(this, a3);
  if ( v9 >= 0 )
  {
    v12 = (struct IUnknown *)((__int64 (__fastcall *)(__int128 *, char *, _QWORD, __int64 *))v10)(
                               &v17,
                               (char *)&v17 + 8,
                               v18,
                               &v19);
    InvasivePtr<UnionExpressionIterator>::Reset(&v14);
    v14 = v12;
    if ( v12 )
    {
      if ( a4 )
      {
        v21 = 0;
        InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(&v21, (__int64)v12);
        *((_DWORD *)this + 8) = 7;
        *((_QWORD *)this + 3) = &v21;
        *v5 = 5;
        *((_QWORD *)this + 5) = v4;
        v9 = XPathQueryStringCompiler::Dispatch(this, a4);
        InvasivePtr<UnionExpressionIterator>::Reset(&v21);
      }
      else if ( *v4 != &v12[1] )
      {
        ATL::AtlComPtrAssign(v4, v12 + 1);
      }
    }
    else
    {
      v9 = -2147024882;
    }
  }
  XPathQueryStringCompiler::NodeTestDispatchResult::~NodeTestDispatchResult((XPathQueryStringCompiler::NodeTestDispatchResult *)&v17);
LABEL_13:
  InvasivePtr<UnionExpressionIterator>::Reset(&v14);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000a094  mov     [rsp-38h+arg_10], rbx
0x18000a099  push    rbp
0x18000a09a  push    rsi
0x18000a09b  push    rdi
0x18000a09c  push    r12
0x18000a09e  push    r13
0x18000a0a0  push    r14
0x18000a0a2  push    r15
0x18000a0a4  mov     rbp, rsp
0x18000a0a7  sub     rsp, 70h
0x18000a0ab  mov     r14, [rcx+28h]
0x18000a0af  lea     rsi, [rcx+30h]
0x18000a0b3  xor     r15d, r15d
0x18000a0b6  mov     r12, r9
0x18000a0b9  mov     [rbp+var_40], r15
0x18000a0bd  mov     r13, r8
0x18000a0c0  mov     rdi, rcx
0x18000a0c3  test    rdx, rdx
0x18000a0c6  jz      short loc_18000A0F6
0x18000a0c8  lea     rax, [rbp+var_38]
0x18000a0cc  mov     [rbp+var_38], r15
0x18000a0d0  mov     [rcx+28h], rax
0x18000a0d4  mov     [rbp+var_30], 7
0x18000a0db  mov     [rsi], r15d
0x18000a0de  call    ?Dispatch@XPathQueryStringCompiler@@QEAAJPEAVNode@@@Z; XPathQueryStringCompiler::Dispatch(Node *)
0x18000a0e3  mov     ebx, eax
0x18000a0e5  test    eax, eax
0x18000a0e7  js      loc_18000A1DF
0x18000a0ed  mov     r15, [rbp+var_38]
0x18000a0f1  mov     eax, [rbp+var_30]
0x18000a0f4  jmp     short loc_18000A102
0x18000a0f6  lea     r15, ?Allocate@?$StepIteratorTemplate@VChildAxisStepIterator@@@@SAPEAVXPathNodeIteratorBase@@AEAVString@@0W4XPathNodeType@@0@Z; StepIteratorTemplate<ChildAxisStepIterator>::Allocate(String &,String &,XPathNodeType,String &)
0x18000a0fd  mov     eax, 1
0x18000a102  mov     dword ptr [rsi], 1
0x18000a108  lea     rcx, [rbp+var_28]
0x18000a10c  mov     [rdi+28h], rcx
0x18000a110  xorps   xmm0, xmm0
0x18000a113  mov     [rbp+arg_0], eax
0x18000a116  mov     rcx, rdi; this
0x18000a119  lea     rax, [rbp+arg_0]
0x18000a11d  mov     [rbp+var_10], 0
0x18000a125  mov     rdx, r13; struct Node *
0x18000a128  mov     dword ptr [rdi+20h], 2
0x18000a12f  movdqu  [rbp+var_28], xmm0
0x18000a134  mov     [rdi+18h], rax
0x18000a138  call    ?Dispatch@XPathQueryStringCompiler@@QEAAJPEAVNode@@@Z; XPathQueryStringCompiler::Dispatch(Node *)
0x18000a13d  mov     ebx, eax
0x18000a13f  test    eax, eax
0x18000a141  js      loc_18000A1D6
0x18000a147  mov     r8d, [rbp+var_18]
0x18000a14b  lea     r9, [rbp+var_10]
0x18000a14f  lea     rdx, [rbp+var_28+8]
0x18000a153  mov     rax, r15
0x18000a156  lea     rcx, [rbp+var_28]
0x18000a15a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a15f  lea     rcx, [rbp+var_40]
0x18000a163  mov     r15, rax
0x18000a166  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x18000a16b  mov     [rbp+var_40], r15
0x18000a16f  test    r15, r15
0x18000a172  jnz     short loc_18000A17B
0x18000a174  mov     ebx, 8007000Eh
0x18000a179  jmp     short loc_18000A1D6
0x18000a17b  test    r12, r12
0x18000a17e  jz      short loc_18000A1C5
0x18000a180  mov     rdx, r15
0x18000a183  mov     [rbp+arg_8], 0
0x18000a18b  lea     rcx, [rbp+arg_8]
0x18000a18f  call    ??$?4VXPathNodeIteratorBase@@@?$InvasivePtr@VXPathNodeIteratorBase@@@@QEAAAEAV0@PEAVXPathNodeIteratorBase@@@Z; InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(XPathNodeIteratorBase *)
0x18000a194  mov     dword ptr [rdi+20h], 7
0x18000a19b  lea     rax, [rbp+arg_8]
0x18000a19f  mov     [rdi+18h], rax
0x18000a1a3  mov     rdx, r12; struct Node *
0x18000a1a6  mov     rcx, rdi; this
0x18000a1a9  mov     dword ptr [rsi], 5
0x18000a1af  mov     [rdi+28h], r14
0x18000a1b3  call    ?Dispatch@XPathQueryStringCompiler@@QEAAJPEAVNode@@@Z; XPathQueryStringCompiler::Dispatch(Node *)
0x18000a1b8  lea     rcx, [rbp+arg_8]
0x18000a1bc  mov     ebx, eax
0x18000a1be  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x18000a1c3  jmp     short loc_18000A1D6
0x18000a1c5  lea     rdx, [r15+8]; struct IUnknown *
0x18000a1c9  cmp     [r14], rdx
0x18000a1cc  jz      short loc_18000A1D6
0x18000a1ce  mov     rcx, r14; struct IUnknown **
0x18000a1d1  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000a1d6  lea     rcx, [rbp+var_28]; this
0x18000a1da  call    ??1NodeTestDispatchResult@XPathQueryStringCompiler@@QEAA@XZ; XPathQueryStringCompiler::NodeTestDispatchResult::~NodeTestDispatchResult(void)
0x18000a1df  lea     rcx, [rbp+var_40]
0x18000a1e3  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x18000a1e8  mov     eax, ebx
0x18000a1ea  mov     rbx, [rsp+70h+arg_10]
0x18000a1f2  add     rsp, 70h
0x18000a1f6  pop     r15
0x18000a1f8  pop     r14
0x18000a1fa  pop     r13
0x18000a1fc  pop     r12
0x18000a1fe  pop     rdi
0x18000a1ff  pop     rsi
0x18000a200  pop     rbp
0x18000a201  retn
```
