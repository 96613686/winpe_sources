# XPathQueryStringCompiler::ProcessNode(AbbreviatedAbsoluteLocationPath__DoubleSlash_RelativeLocationPath *)

- ea: `0x180009390`
- end: `0x18000943f`
- name: `?ProcessNode@XPathQueryStringCompiler@@QEAAJPEAVAbbreviatedAbsoluteLocationPath__DoubleSlash_RelativeLocationPath@@@Z`
- size: `175`
- prototype: `__int64 __fastcall(XPathQueryStringCompiler *__hidden this, struct AbbreviatedAbsoluteLocationPath__DoubleSlash_RelativeLocationPath *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001a00`

## callees

- `0x1800062fc`
- `0x180006798`
- `0x180008294`
- `0x18000835c`
- `0x180009390`
- `0x18000a240`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::ProcessNode(
        XPathQueryStringCompiler *this,
        struct AbbreviatedAbsoluteLocationPath__DoubleSlash_RelativeLocationPath *a2)
{
  int Token; // ebx
  struct Node *v5; // r8
  struct Node *lpVtbl; // rbx
  Node v8; // [rsp+20h] [rbp-78h] BYREF
  struct Node v9; // [rsp+58h] [rbp-40h] BYREF
  struct Node *v10; // [rsp+B0h] [rbp+18h] BYREF

  v10 = 0;
  Token = XPathQueryStringCompiler::CreateToken(L"/", 30, (__int64)&v10);
  if ( Token >= 0 )
  {
    v5 = (struct Node *)*((_QWORD *)a2 + 2);
    lpVtbl = (struct Node *)v5[1].lpVtbl;
    XPathQueryStringCompiler::SimplifiedLocationPathNode::SimplifiedLocationPathNode(
      (XPathQueryStringCompiler::SimplifiedLocationPathNode *)&v9,
      v10,
      v5);
    XPathQueryStringCompiler::SimplifiedLocationPathNode::SimplifiedLocationPathNode(
      (XPathQueryStringCompiler::SimplifiedLocationPathNode *)&v8,
      &v9,
      lpVtbl);
    Token = XPathQueryStringCompiler::Dispatch(this, &v8);
    XPathQueryStringCompiler::SimplifiedLocationPathNode::~SimplifiedLocationPathNode(&v8);
    XPathQueryStringCompiler::SimplifiedLocationPathNode::~SimplifiedLocationPathNode(&v9);
  }
  InvasivePtr<Node>::Reset(&v10);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x180009390  mov     rax, rsp
0x180009393  mov     [rax+8], rbx
0x180009397  mov     [rax+10h], rsi
0x18000939b  push    rdi
0x18000939c  sub     rsp, 90h
0x1800093a3  mov     rdi, rdx
0x1800093a6  mov     qword ptr [rax+18h], 0
0x1800093ae  mov     rsi, rcx
0x1800093b1  lea     r8, [rax+18h]
0x1800093b5  mov     edx, 1Eh
0x1800093ba  lea     rcx, asc_18001715C; "/"
0x1800093c1  call    ?CreateToken@XPathQueryStringCompiler@@CAJPEBGW4SymbolType@@AEAV?$InvasivePtr@VToken@@@@@Z; XPathQueryStringCompiler::CreateToken(ushort const *,SymbolType,InvasivePtr<Token> &)
0x1800093c6  mov     ebx, eax
0x1800093c8  test    eax, eax
0x1800093ca  js      short loc_18000941B
0x1800093cc  mov     r8, [rdi+10h]; struct Node *
0x1800093d0  lea     rcx, [rsp+98h+var_40]; this
0x1800093d5  mov     rdx, [rsp+98h+arg_10]; struct Node *
0x1800093dd  mov     rbx, [r8+8]
0x1800093e1  call    ??0SimplifiedLocationPathNode@XPathQueryStringCompiler@@QEAA@PEAVNode@@0@Z; XPathQueryStringCompiler::SimplifiedLocationPathNode::SimplifiedLocationPathNode(Node *,Node *)
0x1800093e6  mov     r8, rbx; struct Node *
0x1800093e9  lea     rdx, [rsp+98h+var_40]; struct Node *
0x1800093ee  lea     rcx, [rsp+98h+var_78]; this
0x1800093f3  call    ??0SimplifiedLocationPathNode@XPathQueryStringCompiler@@QEAA@PEAVNode@@0@Z; XPathQueryStringCompiler::SimplifiedLocationPathNode::SimplifiedLocationPathNode(Node *,Node *)
0x1800093f8  lea     rdx, [rsp+98h+var_78]; struct Node *
0x1800093fd  mov     rcx, rsi; this
0x180009400  call    ?Dispatch@XPathQueryStringCompiler@@QEAAJPEAVNode@@@Z; XPathQueryStringCompiler::Dispatch(Node *)
0x180009405  lea     rcx, [rsp+98h+var_78]; this
0x18000940a  mov     ebx, eax
0x18000940c  call    ??1SimplifiedLocationPathNode@XPathQueryStringCompiler@@UEAA@XZ; XPathQueryStringCompiler::SimplifiedLocationPathNode::~SimplifiedLocationPathNode(void)
0x180009411  lea     rcx, [rsp+98h+var_40]; this
0x180009416  call    ??1SimplifiedLocationPathNode@XPathQueryStringCompiler@@UEAA@XZ; XPathQueryStringCompiler::SimplifiedLocationPathNode::~SimplifiedLocationPathNode(void)
0x18000941b  lea     rcx, [rsp+98h+arg_10]
0x180009423  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180009428  lea     r11, [rsp+98h+var_8]
0x180009430  mov     eax, ebx
0x180009432  mov     rbx, [r11+10h]
0x180009436  mov     rsi, [r11+18h]
0x18000943a  mov     rsp, r11
0x18000943d  pop     rdi
0x18000943e  retn
```
