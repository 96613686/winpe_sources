# XPathQueryStringCompiler::SimplifiedLocationPathNode::SimplifiedLocationPathNode(Node *,Node *)

- ea: `0x1800062fc`
- end: `0x180006374`
- name: `??0SimplifiedLocationPathNode@XPathQueryStringCompiler@@QEAA@PEAVNode@@0@Z`
- size: `120`
- prototype: `__int64 __fastcall(XPathQueryStringCompiler::SimplifiedLocationPathNode *__hidden this, struct Node *, struct Node *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007dc0`
- `0x180009390`

## callees

- `0x18000595c`

## pseudocode

```c
XPathQueryStringCompiler::SimplifiedLocationPathNode *__fastcall XPathQueryStringCompiler::SimplifiedLocationPathNode::SimplifiedLocationPathNode(
        XPathQueryStringCompiler::SimplifiedLocationPathNode *this,
        struct Node *a2,
        struct Node *a3)
{
  _QWORD *v5; // rcx

  *(_QWORD *)this = &Node::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 1;
  *((_DWORD *)this + 7) = -1;
  *((_DWORD *)this + 8) = 2;
  *(_QWORD *)this = &XPathQueryStringCompiler::SimplifiedLocationPathNode::`vftable';
  v5 = (_QWORD *)((char *)this + 40);
  *v5 = 0;
  *((_QWORD *)this + 6) = 0;
  InvasivePtr<Node>::operator=<Node>(v5, a2);
  InvasivePtr<Node>::operator=<Node>((char *)this + 48, a3);
  return this;
}

```

## disassembly

```asm
0x1800062fc  mov     [rsp+arg_0], rbx
0x180006301  mov     [rsp+arg_8], rsi
0x180006306  push    rdi
0x180006307  sub     rsp, 20h
0x18000630b  mov     rsi, rcx
0x18000630e  lea     rax, ??_7Node@@6B@; const Node::`vftable'
0x180006315  mov     [rcx], rax
0x180006318  mov     rdi, r8
0x18000631b  xor     r8d, r8d
0x18000631e  lea     rax, ??_7SimplifiedLocationPathNode@XPathQueryStringCompiler@@6B@; const XPathQueryStringCompiler::SimplifiedLocationPathNode::`vftable'
0x180006325  mov     [rcx+8], r8
0x180006329  mov     [rcx+10h], r8
0x18000632d  mov     dword ptr [rcx+18h], 1
0x180006334  mov     dword ptr [rcx+1Ch], 0FFFFFFFFh
0x18000633b  mov     dword ptr [rcx+20h], 2
0x180006342  mov     [rcx], rax
0x180006345  add     rcx, 28h ; '('
0x180006349  mov     [rcx], r8
0x18000634c  mov     [rsi+30h], r8
0x180006350  call    ??$?4VNode@@@?$InvasivePtr@VNode@@@@QEAAAEAV0@PEAVNode@@@Z; InvasivePtr<Node>::operator=<Node>(Node *)
0x180006355  mov     rdx, rdi
0x180006358  lea     rcx, [rsi+30h]
0x18000635c  call    ??$?4VNode@@@?$InvasivePtr@VNode@@@@QEAAAEAV0@PEAVNode@@@Z; InvasivePtr<Node>::operator=<Node>(Node *)
0x180006361  mov     rbx, [rsp+28h+arg_0]
0x180006366  mov     rax, rsi
0x180006369  mov     rsi, [rsp+28h+arg_8]
0x18000636e  add     rsp, 20h
0x180006372  pop     rdi
0x180006373  retn
```
