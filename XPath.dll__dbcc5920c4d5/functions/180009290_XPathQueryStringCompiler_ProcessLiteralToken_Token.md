# XPathQueryStringCompiler::ProcessLiteralToken(Token *)

- ea: `0x180009290`
- end: `0x180009388`
- name: `?ProcessLiteralToken@XPathQueryStringCompiler@@AEAAJPEAVToken@@@Z`
- size: `248`
- prototype: `__int64 __fastcall(XPathQueryStringCompiler *__hidden this, struct Token *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x1800068d8`
- `0x180007f5c`
- `0x180009290`
- `0x180010f08`
- `0x180010f98`
- `0x180010fac`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::ProcessLiteralToken(XPathQueryStringCompiler *this, struct Token *a2)
{
  __int64 v2; // rsi
  unsigned int CCH; // eax
  const unsigned __int16 **v4; // rcx
  const unsigned __int16 *v5; // rdx
  int v6; // edi
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF
  __int64 v11; // [rsp+38h] [rbp+10h] BYREF

  v2 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  v10 = 0;
  CCH = String::QueryCCH((struct Token *)((char *)a2 + 48));
  v5 = &qword_180016F98;
  if ( *v4 )
    v5 = *v4;
  v6 = String::Initialize((String *)&v10, v5 + 1, CCH - 2);
  if ( v6 >= 0 )
  {
    v11 = v10;
    if ( v10 )
      _InterlockedIncrement((volatile signed __int32 *)(v10 - 8));
    v7 = operator new(0x18u);
    v8 = v7;
    if ( v7 )
    {
      v7[1] = 0;
      v7[2] = 0;
      *v7 = &SimpleIUnknownImpl<IXPathExpression>::`vftable';
      *((_DWORD *)v7 + 2) = 1;
      ModuleRefCounter::AddRef();
      v8[2] = 0;
      *v8 = &StringLiteralExpression::`vftable';
      String::operator=(v8 + 2, &v11);
    }
    else
    {
      v8 = 0;
    }
    String::Reset((String *)&v11);
    ATL::CComPtrBase<StepCompositionIterator>::Attach(v2, v8);
  }
  String::Reset((String *)&v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009290  mov     [rsp+arg_10], rbx
0x180009295  mov     [rsp+arg_18], rsi
0x18000929a  push    rdi
0x18000929b  sub     rsp, 20h
0x18000929f  mov     rsi, [rcx+28h]
0x1800092a3  mov     qword ptr [rcx+28h], 0
0x1800092ab  lea     rcx, [rdx+30h]; this
0x1800092af  mov     [rsp+28h+arg_0], 0
0x1800092b8  call    ?QueryCCH@String@@QEBAKXZ; String::QueryCCH(void)
0x1800092bd  cmp     qword ptr [rcx], 0
0x1800092c1  lea     rdx, qword_180016F98
0x1800092c8  cmovnz  rdx, [rcx]
0x1800092cc  lea     rcx, [rsp+28h+arg_0]; this
0x1800092d1  add     rdx, 2; Src
0x1800092d5  lea     r8d, [rax-2]; unsigned __int64
0x1800092d9  call    ?Initialize@String@@QEAAJPEBG_K@Z; String::Initialize(ushort const *,unsigned __int64)
0x1800092de  mov     edi, eax
0x1800092e0  test    eax, eax
0x1800092e2  js      loc_18000936C
0x1800092e8  mov     rax, [rsp+28h+arg_0]
0x1800092ed  mov     [rsp+28h+arg_8], rax
0x1800092f2  test    rax, rax
0x1800092f5  jz      short loc_1800092FB
0x1800092f7  lock inc dword ptr [rax-8]
0x1800092fb  mov     ecx, 18h; Size
0x180009300  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009305  mov     rbx, rax
0x180009308  test    rax, rax
0x18000930b  jz      short loc_180009355
0x18000930d  mov     qword ptr [rax+8], 0
0x180009315  mov     qword ptr [rax+10h], 0
0x18000931d  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180009324  mov     [rbx], rax
0x180009327  mov     dword ptr [rbx+8], 1
0x18000932e  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180009333  lea     rax, ??_7StringLiteralExpression@@6B@; const StringLiteralExpression::`vftable'
0x18000933a  mov     qword ptr [rbx+10h], 0
0x180009342  lea     rcx, [rbx+10h]
0x180009346  mov     [rbx], rax
0x180009349  lea     rdx, [rsp+28h+arg_8]
0x18000934e  call    ??4String@@QEAAAEAV0@AEBV0@@Z; String::operator=(String const &)
0x180009353  jmp     short loc_180009357
0x180009355  xor     ebx, ebx
0x180009357  lea     rcx, [rsp+28h+arg_8]; this
0x18000935c  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x180009361  mov     rdx, rbx
0x180009364  mov     rcx, rsi
0x180009367  call    ?Attach@?$CComPtrBase@VStepCompositionIterator@@@ATL@@QEAAXPEAVStepCompositionIterator@@@Z; ATL::CComPtrBase<StepCompositionIterator>::Attach(StepCompositionIterator *)
0x18000936c  lea     rcx, [rsp+28h+arg_0]; this
0x180009371  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x180009376  mov     rbx, [rsp+28h+arg_10]
0x18000937b  mov     eax, edi
0x18000937d  mov     rsi, [rsp+28h+arg_18]
0x180009382  add     rsp, 20h
0x180009386  pop     rdi
0x180009387  retn
```
