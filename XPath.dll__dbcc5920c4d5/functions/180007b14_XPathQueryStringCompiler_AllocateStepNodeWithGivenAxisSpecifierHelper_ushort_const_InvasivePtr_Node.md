# XPathQueryStringCompiler::AllocateStepNodeWithGivenAxisSpecifierHelper(ushort const *,InvasivePtr<Node> &)

- ea: `0x180007b14`
- end: `0x180007db1`
- name: `?AllocateStepNodeWithGivenAxisSpecifierHelper@XPathQueryStringCompiler@@AEAAJPEBGAEAV?$InvasivePtr@VNode@@@@@Z`
- size: `669`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180007ac0`
- `0x180007ae0`
- `0x180007b00`
- `0x180007dc0`

## callees

- `0x18000595c`
- `0x180005998`
- `0x1800079a0`
- `0x180007a00`
- `0x180007a60`
- `0x180007b14`
- `0x180008294`
- `0x18000a240`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::AllocateStepNodeWithGivenAxisSpecifierHelper(
        __int64 a1,
        unsigned __int16 *a2,
        __int64 a3)
{
  int Token; // ebx
  struct Node *v5; // rbx
  struct Node *v6; // rdi
  struct Node *v7; // rsi
  __int64 v9; // [rsp+20h] [rbp-30h] BYREF
  __int64 v10; // [rsp+28h] [rbp-28h] BYREF
  __int64 v11; // [rsp+30h] [rbp-20h] BYREF
  struct Node *v12; // [rsp+38h] [rbp-18h] BYREF
  struct Node *v13; // [rsp+40h] [rbp-10h] BYREF
  struct Node *v14; // [rsp+48h] [rbp-8h] BYREF
  __int64 v15; // [rsp+70h] [rbp+20h] BYREF
  __int64 v16; // [rsp+88h] [rbp+38h] BYREF

  v9 = 0;
  v11 = 0;
  v16 = 0;
  v15 = 0;
  v10 = 0;
  Token = XPathQueryStringCompiler::CreateToken(a2, 31, (__int64)&v9);
  if ( Token < 0
    || (Token = XPathQueryStringCompiler::CreateToken(L"::", 32, (__int64)&v11), Token < 0)
    || (Token = XPathQueryStringCompiler::CreateToken(L"node", 33, (__int64)&v16), Token < 0)
    || (Token = XPathQueryStringCompiler::CreateToken(L"(", 34, (__int64)&v15), Token < 0)
    || (Token = XPathQueryStringCompiler::CreateToken(L")", 35, (__int64)&v10), Token < 0) )
  {
    InvasivePtr<Node>::Reset(&v10);
    InvasivePtr<Node>::Reset(&v15);
    InvasivePtr<Node>::Reset(&v16);
    InvasivePtr<Node>::Reset(&v11);
    InvasivePtr<Node>::Reset(&v9);
    return (unsigned int)Token;
  }
  else
  {
    v14 = 0;
    v13 = 0;
    v12 = 0;
    v5 = AxisSpecifier__AxisName_DoubleColon::Allocate();
    InvasivePtr<Node>::Reset(&v14);
    v14 = v5;
    if ( v5
      && (v6 = NodeTest__NodeType_OpenParanthesis_CloseParanthesis::Allocate(),
          InvasivePtr<Node>::Reset(&v13),
          (v13 = v6) != 0)
      && (v7 = Step__AxisSpecifier_NodeTest::Allocate(), InvasivePtr<Node>::Reset(&v12), (v12 = v7) != 0) )
    {
      InvasivePtr<Node>::operator=<Node>(&v7[2], v5);
      InvasivePtr<Token>::operator=(&v5[2], &v9);
      InvasivePtr<Token>::operator=(v9 + 8, &v11);
      InvasivePtr<Node>::operator=<Node>(&v5[1], v6);
      InvasivePtr<Token>::operator=(&v6[2], &v16);
      InvasivePtr<Token>::operator=(v16 + 8, &v15);
      InvasivePtr<Token>::operator=(v15 + 8, &v10);
      InvasivePtr<Node>::operator=<Node>(a3, v7);
      InvasivePtr<Node>::Reset(&v12);
      InvasivePtr<Node>::Reset(&v13);
      InvasivePtr<Node>::Reset(&v14);
      InvasivePtr<Node>::Reset(&v10);
      InvasivePtr<Node>::Reset(&v15);
      InvasivePtr<Node>::Reset(&v16);
      InvasivePtr<Node>::Reset(&v11);
      InvasivePtr<Node>::Reset(&v9);
      return 0;
    }
    else
    {
      InvasivePtr<Node>::Reset(&v12);
      InvasivePtr<Node>::Reset(&v13);
      InvasivePtr<Node>::Reset(&v14);
      InvasivePtr<Node>::Reset(&v10);
      InvasivePtr<Node>::Reset(&v15);
      InvasivePtr<Node>::Reset(&v16);
      InvasivePtr<Node>::Reset(&v11);
      InvasivePtr<Node>::Reset(&v9);
      return 2147942414LL;
    }
  }
}

```

## disassembly

```asm
0x180007b14  mov     [rsp-18h+arg_8], rbx
0x180007b19  mov     [rsp-18h+arg_10], rsi
0x180007b1e  mov     [rsp-18h+arg_0], rcx
0x180007b23  push    rbp
0x180007b24  push    rdi
0x180007b25  push    r14
0x180007b27  mov     rbp, rsp
0x180007b2a  sub     rsp, 50h
0x180007b2e  mov     r14, r8
0x180007b31  mov     [rbp+var_30], 0
0x180007b39  mov     rcx, rdx; unsigned __int16 *
0x180007b3c  mov     [rbp+var_20], 0
0x180007b44  lea     r8, [rbp+var_30]
0x180007b48  mov     [rbp+arg_18], 0
0x180007b50  mov     edx, 1Fh
0x180007b55  mov     [rbp+arg_0], 0
0x180007b5d  mov     [rbp+var_28], 0
0x180007b65  call    ?CreateToken@XPathQueryStringCompiler@@CAJPEBGW4SymbolType@@AEAV?$InvasivePtr@VToken@@@@@Z; XPathQueryStringCompiler::CreateToken(ushort const *,SymbolType,InvasivePtr<Token> &)
0x180007b6a  mov     ebx, eax
0x180007b6c  test    eax, eax
0x180007b6e  js      loc_180007D6D
0x180007b74  lea     r8, [rbp+var_20]
0x180007b78  mov     edx, 20h ; ' '
0x180007b7d  lea     rcx, asc_180017178; "::"
0x180007b84  call    ?CreateToken@XPathQueryStringCompiler@@CAJPEBGW4SymbolType@@AEAV?$InvasivePtr@VToken@@@@@Z; XPathQueryStringCompiler::CreateToken(ushort const *,SymbolType,InvasivePtr<Token> &)
0x180007b89  mov     ebx, eax
0x180007b8b  test    eax, eax
0x180007b8d  js      loc_180007D6D
0x180007b93  lea     r8, [rbp+arg_18]
0x180007b97  mov     edx, 21h ; '!'
0x180007b9c  lea     rcx, aNode; "node"
0x180007ba3  call    ?CreateToken@XPathQueryStringCompiler@@CAJPEBGW4SymbolType@@AEAV?$InvasivePtr@VToken@@@@@Z; XPathQueryStringCompiler::CreateToken(ushort const *,SymbolType,InvasivePtr<Token> &)
0x180007ba8  mov     ebx, eax
0x180007baa  test    eax, eax
0x180007bac  js      loc_180007D6D
0x180007bb2  lea     r8, [rbp+arg_0]
0x180007bb6  mov     edx, 22h ; '"'
0x180007bbb  lea     rcx, asc_180017180; "("
0x180007bc2  call    ?CreateToken@XPathQueryStringCompiler@@CAJPEBGW4SymbolType@@AEAV?$InvasivePtr@VToken@@@@@Z; XPathQueryStringCompiler::CreateToken(ushort const *,SymbolType,InvasivePtr<Token> &)
0x180007bc7  mov     ebx, eax
0x180007bc9  test    eax, eax
0x180007bcb  js      loc_180007D6D
0x180007bd1  lea     r8, [rbp+var_28]
0x180007bd5  mov     edx, 23h ; '#'
0x180007bda  lea     rcx, asc_180017184; ")"
0x180007be1  call    ?CreateToken@XPathQueryStringCompiler@@CAJPEBGW4SymbolType@@AEAV?$InvasivePtr@VToken@@@@@Z; XPathQueryStringCompiler::CreateToken(ushort const *,SymbolType,InvasivePtr<Token> &)
0x180007be6  mov     ebx, eax
0x180007be8  test    eax, eax
0x180007bea  js      loc_180007D6D
0x180007bf0  mov     [rbp+var_8], 0
0x180007bf8  mov     [rbp+var_10], 0
0x180007c00  mov     [rbp+var_18], 0
0x180007c08  call    ?Allocate@AxisSpecifier__AxisName_DoubleColon@@SAPEAVNode@@XZ; AxisSpecifier__AxisName_DoubleColon::Allocate(void)
0x180007c0d  lea     rcx, [rbp+var_8]
0x180007c11  mov     rbx, rax
0x180007c14  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007c19  mov     [rbp+var_8], rbx
0x180007c1d  test    rbx, rbx
0x180007c20  jz      loc_180007D1E
0x180007c26  call    ?Allocate@NodeTest__NodeType_OpenParanthesis_CloseParanthesis@@SAPEAVNode@@XZ; NodeTest__NodeType_OpenParanthesis_CloseParanthesis::Allocate(void)
0x180007c2b  lea     rcx, [rbp+var_10]
0x180007c2f  mov     rdi, rax
0x180007c32  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007c37  mov     [rbp+var_10], rdi
0x180007c3b  test    rdi, rdi
0x180007c3e  jz      loc_180007D1E
0x180007c44  call    ?Allocate@Step__AxisSpecifier_NodeTest@@SAPEAVNode@@XZ; Step__AxisSpecifier_NodeTest::Allocate(void)
0x180007c49  lea     rcx, [rbp+var_18]
0x180007c4d  mov     rsi, rax
0x180007c50  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007c55  mov     [rbp+var_18], rsi
0x180007c59  test    rsi, rsi
0x180007c5c  jz      loc_180007D1E
0x180007c62  lea     rcx, [rsi+10h]
0x180007c66  mov     rdx, rbx
0x180007c69  call    ??$?4VNode@@@?$InvasivePtr@VNode@@@@QEAAAEAV0@PEAVNode@@@Z; InvasivePtr<Node>::operator=<Node>(Node *)
0x180007c6e  lea     rcx, [rbx+10h]
0x180007c72  lea     rdx, [rbp+var_30]
0x180007c76  call    ??4?$InvasivePtr@VToken@@@@QEAAAEAV0@AEBV0@@Z; InvasivePtr<Token>::operator=(InvasivePtr<Token> const &)
0x180007c7b  mov     rcx, [rbp+var_30]
0x180007c7f  lea     rdx, [rbp+var_20]
0x180007c83  add     rcx, 8
0x180007c87  call    ??4?$InvasivePtr@VToken@@@@QEAAAEAV0@AEBV0@@Z; InvasivePtr<Token>::operator=(InvasivePtr<Token> const &)
0x180007c8c  lea     rcx, [rbx+8]
0x180007c90  mov     rdx, rdi
0x180007c93  call    ??$?4VNode@@@?$InvasivePtr@VNode@@@@QEAAAEAV0@PEAVNode@@@Z; InvasivePtr<Node>::operator=<Node>(Node *)
0x180007c98  lea     rcx, [rdi+10h]
0x180007c9c  lea     rdx, [rbp+arg_18]
0x180007ca0  call    ??4?$InvasivePtr@VToken@@@@QEAAAEAV0@AEBV0@@Z; InvasivePtr<Token>::operator=(InvasivePtr<Token> const &)
0x180007ca5  mov     rcx, [rbp+arg_18]
0x180007ca9  lea     rdx, [rbp+arg_0]
0x180007cad  add     rcx, 8
0x180007cb1  call    ??4?$InvasivePtr@VToken@@@@QEAAAEAV0@AEBV0@@Z; InvasivePtr<Token>::operator=(InvasivePtr<Token> const &)
0x180007cb6  mov     rcx, [rbp+arg_0]
0x180007cba  lea     rdx, [rbp+var_28]
0x180007cbe  add     rcx, 8
0x180007cc2  call    ??4?$InvasivePtr@VToken@@@@QEAAAEAV0@AEBV0@@Z; InvasivePtr<Token>::operator=(InvasivePtr<Token> const &)
0x180007cc7  mov     rdx, rsi
0x180007cca  mov     rcx, r14
0x180007ccd  call    ??$?4VNode@@@?$InvasivePtr@VNode@@@@QEAAAEAV0@PEAVNode@@@Z; InvasivePtr<Node>::operator=<Node>(Node *)
0x180007cd2  lea     rcx, [rbp+var_18]
0x180007cd6  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007cdb  lea     rcx, [rbp+var_10]
0x180007cdf  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007ce4  lea     rcx, [rbp+var_8]
0x180007ce8  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007ced  lea     rcx, [rbp+var_28]
0x180007cf1  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007cf6  lea     rcx, [rbp+arg_0]
0x180007cfa  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007cff  lea     rcx, [rbp+arg_18]
0x180007d03  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007d08  lea     rcx, [rbp+var_20]
0x180007d0c  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007d11  lea     rcx, [rbp+var_30]
0x180007d15  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007d1a  xor     eax, eax
0x180007d1c  jmp     short loc_180007D9C
0x180007d1e  lea     rcx, [rbp+var_18]
0x180007d22  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007d27  lea     rcx, [rbp+var_10]
0x180007d2b  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007d30  lea     rcx, [rbp+var_8]
0x180007d34  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007d39  lea     rcx, [rbp+var_28]
0x180007d3d  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007d42  lea     rcx, [rbp+arg_0]
0x180007d46  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007d4b  lea     rcx, [rbp+arg_18]
0x180007d4f  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007d54  lea     rcx, [rbp+var_20]
0x180007d58  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007d5d  lea     rcx, [rbp+var_30]
0x180007d61  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007d66  mov     eax, 8007000Eh
0x180007d6b  jmp     short loc_180007D9C
0x180007d6d  lea     rcx, [rbp+var_28]
0x180007d71  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007d76  lea     rcx, [rbp+arg_0]
0x180007d7a  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007d7f  lea     rcx, [rbp+arg_18]
0x180007d83  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007d88  lea     rcx, [rbp+var_20]
0x180007d8c  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007d91  lea     rcx, [rbp+var_30]
0x180007d95  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180007d9a  mov     eax, ebx
0x180007d9c  lea     r11, [rsp+50h+var_s0]
0x180007da1  mov     rbx, [r11+28h]
0x180007da5  mov     rsi, [r11+30h]
0x180007da9  mov     rsp, r11
0x180007dac  pop     r14
0x180007dae  pop     rdi
0x180007daf  pop     rbp
0x180007db0  retn
```
