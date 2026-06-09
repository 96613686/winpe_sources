# XPathQueryStringCompiler::CreateToken(ushort const *,SymbolType,InvasivePtr<Token> &)

- ea: `0x180008294`
- end: `0x180008344`
- name: `?CreateToken@XPathQueryStringCompiler@@CAJPEBGW4SymbolType@@AEAV?$InvasivePtr@VToken@@@@@Z`
- size: `176`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180007b14`
- `0x180009390`

## callees

- `0x180001078`
- `0x180005998`
- `0x1800064a8`
- `0x180008294`
- `0x18000a240`
- `0x180010ee0`
- `0x180010fac`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::CreateToken(unsigned __int16 *a1, int a2, __int64 a3)
{
  int v5; // ebx
  void *v6; // rax
  __int64 v7; // rbx
  __int64 v9[3]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v10; // [rsp+58h] [rbp+20h] BYREF

  v10 = 0;
  v9[0] = 0;
  v5 = String::Initialize((String *)v9, a1);
  if ( v5 >= 0 )
  {
    v6 = operator new(0x38u);
    if ( v6 )
      v7 = Token::Token((__int64)v6, v9, a2, 0);
    else
      v7 = 0;
    InvasivePtr<Node>::Reset(&v10);
    v10 = v7;
    if ( v7 )
    {
      InvasivePtr<Token>::operator=(a3, &v10);
      v5 = 0;
    }
    else
    {
      v5 = -2147024882;
    }
  }
  String::Reset((String *)v9);
  InvasivePtr<Node>::Reset(&v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180008294  mov     rax, rsp
0x180008297  mov     [rax+8], rbx
0x18000829b  mov     [rax+10h], rsi
0x18000829f  push    rdi
0x1800082a0  sub     rsp, 30h
0x1800082a4  mov     esi, edx
0x1800082a6  mov     qword ptr [rax+20h], 0
0x1800082ae  mov     rdx, rcx; unsigned __int16 *
0x1800082b1  mov     qword ptr [rax-18h], 0
0x1800082b9  lea     rcx, [rax-18h]; this
0x1800082bd  mov     rdi, r8
0x1800082c0  call    ?Initialize@String@@QEAAJPEBG@Z; String::Initialize(ushort const *)
0x1800082c5  mov     ebx, eax
0x1800082c7  test    eax, eax
0x1800082c9  js      short loc_18000831E
0x1800082cb  mov     ecx, 38h ; '8'; Size
0x1800082d0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800082d5  test    rax, rax
0x1800082d8  jz      short loc_1800082F2
0x1800082da  xor     r9d, r9d
0x1800082dd  lea     rdx, [rsp+38h+var_18]
0x1800082e2  mov     r8d, esi
0x1800082e5  mov     rcx, rax
0x1800082e8  call    ??0Token@@QEAA@AEAVString@@W4SymbolType@@K@Z; Token::Token(String &,SymbolType,ulong)
0x1800082ed  mov     rbx, rax
0x1800082f0  jmp     short loc_1800082F4
0x1800082f2  xor     ebx, ebx
0x1800082f4  lea     rcx, [rsp+38h+arg_18]
0x1800082f9  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x1800082fe  mov     [rsp+38h+arg_18], rbx
0x180008303  test    rbx, rbx
0x180008306  jnz     short loc_18000830F
0x180008308  mov     ebx, 8007000Eh
0x18000830d  jmp     short loc_18000831E
0x18000830f  lea     rdx, [rsp+38h+arg_18]
0x180008314  mov     rcx, rdi
0x180008317  call    ??4?$InvasivePtr@VToken@@@@QEAAAEAV0@AEBV0@@Z; InvasivePtr<Token>::operator=(InvasivePtr<Token> const &)
0x18000831c  xor     ebx, ebx
0x18000831e  lea     rcx, [rsp+38h+var_18]; this
0x180008323  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x180008328  lea     rcx, [rsp+38h+arg_18]
0x18000832d  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180008332  mov     rsi, [rsp+38h+arg_8]
0x180008337  mov     eax, ebx
0x180008339  mov     rbx, [rsp+38h+arg_0]
0x18000833e  add     rsp, 30h
0x180008342  pop     rdi
0x180008343  retn
```
