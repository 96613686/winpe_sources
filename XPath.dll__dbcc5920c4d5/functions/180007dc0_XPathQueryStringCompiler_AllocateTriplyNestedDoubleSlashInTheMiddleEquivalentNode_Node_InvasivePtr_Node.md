# XPathQueryStringCompiler::AllocateTriplyNestedDoubleSlashInTheMiddleEquivalentNode(Node *,InvasivePtr<Node> &)

- ea: `0x180007dc0`
- end: `0x180007edb`
- name: `?AllocateTriplyNestedDoubleSlashInTheMiddleEquivalentNode@XPathQueryStringCompiler@@AEAAJPEAVNode@@AEAV?$InvasivePtr@VNode@@@@@Z`
- size: `283`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x18000595c`
- `0x1800062fc`
- `0x180007b14`
- `0x180007dc0`
- `0x18000a240`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::AllocateTriplyNestedDoubleSlashInTheMiddleEquivalentNode(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  struct Node *v3; // rdi
  struct Node *AddRef; // rsi
  int StepNodeWithGivenAxisSpecifierHelper; // ebx
  XPathQueryStringCompiler::SimplifiedLocationPathNode *v7; // rax
  struct Node *v8; // rbx
  XPathQueryStringCompiler::SimplifiedLocationPathNode *v9; // rax
  __int64 v10; // rbx
  struct Node *v12[2]; // [rsp+20h] [rbp-10h] BYREF
  struct Node *v13; // [rsp+58h] [rbp+28h] BYREF
  __int64 v14; // [rsp+68h] [rbp+38h] BYREF

  v3 = *(struct Node **)(a2 + 16);
  v12[0] = 0;
  AddRef = (struct Node *)v3[1].lpVtbl->AddRef;
  StepNodeWithGivenAxisSpecifierHelper = XPathQueryStringCompiler::AllocateStepNodeWithGivenAxisSpecifierHelper(
                                           a1,
                                           L"descendant-or-self",
                                           (__int64)v12);
  if ( StepNodeWithGivenAxisSpecifierHelper >= 0 )
  {
    v13 = 0;
    v7 = (XPathQueryStringCompiler::SimplifiedLocationPathNode *)operator new(0x38u);
    if ( v7 )
      v8 = (struct Node *)XPathQueryStringCompiler::SimplifiedLocationPathNode::SimplifiedLocationPathNode(
                            v7,
                            v3,
                            v12[0]);
    else
      v8 = 0;
    InvasivePtr<Node>::Reset(&v13);
    v13 = v8;
    if ( v8 )
    {
      v14 = 0;
      v9 = (XPathQueryStringCompiler::SimplifiedLocationPathNode *)operator new(0x38u);
      if ( v9 )
        v10 = XPathQueryStringCompiler::SimplifiedLocationPathNode::SimplifiedLocationPathNode(v9, v8, AddRef);
      else
        v10 = 0;
      InvasivePtr<Node>::Reset(&v14);
      v14 = v10;
      if ( v10 )
      {
        InvasivePtr<Node>::operator=<Node>(a3, v10);
        InvasivePtr<Node>::Reset(&v14);
        InvasivePtr<Node>::Reset(&v13);
        StepNodeWithGivenAxisSpecifierHelper = 0;
        goto LABEL_13;
      }
      InvasivePtr<Node>::Reset(&v14);
    }
    InvasivePtr<Node>::Reset(&v13);
    StepNodeWithGivenAxisSpecifierHelper = -2147024882;
  }
LABEL_13:
  InvasivePtr<Node>::Reset(v12);
  return (unsigned int)StepNodeWithGivenAxisSpecifierHelper;
}

```

## disassembly

```asm
0x180007dc0  mov     [rsp-18h+arg_0], rbx
0x180007dc5  mov     [rsp-18h+arg_10], rsi
0x180007dca  push    rbp
0x180007dcb  push    rdi
0x180007dcc  push    r14
0x180007dce  mov     rbp, rsp
0x180007dd1  sub     rsp, 30h
0x180007dd5  mov     rdi, [rdx+10h]
0x180007dd9  mov     r14, r8
0x180007ddc  lea     r8, [rbp+var_10]
0x180007de0  mov     [rbp+var_10], 0
0x180007de8  lea     rdx, aDescendantOrSe; "descendant-or-self"
0x180007def  mov     rax, [rdi+8]
0x180007df3  mov     rsi, [rax+8]
0x180007df7  call    ?AllocateStepNodeWithGivenAxisSpecifierHelper@XPathQueryStringCompiler@@AEAAJPEBGAEAV?$InvasivePtr@VNode@@@@@Z; XPathQueryStringCompiler::AllocateStepNodeWithGivenAxisSpecifierHelper(ushort const *,InvasivePtr<Node> &)
0x180007dfc  mov     ebx, eax
0x180007dfe  test    eax, eax
0x180007e00  js      loc_180007EBD
0x180007e06  mov     ecx, 38h ; '8'; Size
0x180007e0b  mov     [rbp+arg_8], 0
0x180007e13  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007e18  test    rax, rax
0x180007e1b  jz      short loc_180007E31
0x180007e1d  mov     r8, [rbp+var_10]; struct Node *
0x180007e21  mov     rdx, rdi; struct Node *
0x180007e24  mov     rcx, rax; this
0x180007e27  call    ??0SimplifiedLocationPathNode@XPathQueryStringCompiler@@QEAA@PEAVNode@@0@Z; XPathQueryStringCompiler::SimplifiedLocationPathNode::SimplifiedLocationPathNode(Node *,Node *)
0x180007e2c  mov     rbx, rax
0x180007e2f  jmp     short loc_180007E33
0x180007e31  xor     ebx, ebx
0x180007e33  lea     rcx, [rbp+arg_8]
0x180007e37  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007e3c  mov     [rbp+arg_8], rbx
0x180007e40  test    rbx, rbx
0x180007e43  jnz     short loc_180007E55
0x180007e45  lea     rcx, [rbp+arg_8]
0x180007e49  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007e4e  mov     ebx, 8007000Eh
0x180007e53  jmp     short loc_180007EBD
0x180007e55  mov     ecx, 38h ; '8'; Size
0x180007e5a  mov     [rbp+arg_18], 0
0x180007e62  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007e67  test    rax, rax
0x180007e6a  jz      short loc_180007E7F
0x180007e6c  mov     r8, rsi; struct Node *
0x180007e6f  mov     rdx, rbx; struct Node *
0x180007e72  mov     rcx, rax; this
0x180007e75  call    ??0SimplifiedLocationPathNode@XPathQueryStringCompiler@@QEAA@PEAVNode@@0@Z; XPathQueryStringCompiler::SimplifiedLocationPathNode::SimplifiedLocationPathNode(Node *,Node *)
0x180007e7a  mov     rbx, rax
0x180007e7d  jmp     short loc_180007E81
0x180007e7f  xor     ebx, ebx
0x180007e81  lea     rcx, [rbp+arg_18]
0x180007e85  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007e8a  mov     [rbp+arg_18], rbx
0x180007e8e  test    rbx, rbx
0x180007e91  jnz     short loc_180007E9E
0x180007e93  lea     rcx, [rbp+arg_18]
0x180007e97  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007e9c  jmp     short loc_180007E45
0x180007e9e  mov     rdx, rbx
0x180007ea1  mov     rcx, r14
0x180007ea4  call    ??$?4VNode@@@?$InvasivePtr@VNode@@@@QEAAAEAV0@PEAVNode@@@Z; InvasivePtr<Node>::operator=<Node>(Node *)
0x180007ea9  lea     rcx, [rbp+arg_18]
0x180007ead  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007eb2  lea     rcx, [rbp+arg_8]
0x180007eb6  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007ebb  xor     ebx, ebx
0x180007ebd  lea     rcx, [rbp+var_10]
0x180007ec1  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007ec6  mov     rsi, [rsp+30h+arg_10]
0x180007ecb  mov     eax, ebx
0x180007ecd  mov     rbx, [rsp+30h+arg_0]
0x180007ed2  add     rsp, 30h
0x180007ed6  pop     r14
0x180007ed8  pop     rdi
0x180007ed9  pop     rbp
0x180007eda  retn
```
