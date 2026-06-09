# XPathQueryStringCompiler::Select(IXPathEvaluationContextExtension *,ushort const *,IXPathNavigator *,IXPathNodeIterator * *)

- ea: `0x18000a280`
- end: `0x18000a3a1`
- name: `?Select@XPathQueryStringCompiler@@UEAAJPEAUIXPathEvaluationContextExtension@@PEBGPEAUIXPathNavigator@@PEAPEAUIXPathNodeIterator@@@Z`
- size: `289`
- prototype: `__int64 __fastcall(XPathQueryStringCompiler *this, struct IUnknown *, const unsigned __int16 *, struct IXPathNavigator *, struct IXPathNodeIterator **)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800020b4`
- `0x180005124`
- `0x1800054e0`
- `0x1800080b8`
- `0x180008bdc`
- `0x18000a280`
- `0x18000a3a8`
- `0x180010ee0`
- `0x180010f98`
- `0x180010fac`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::Select(
        XPathQueryStringCompiler *this,
        struct IUnknown *a2,
        const unsigned __int16 *a3,
        struct IXPathNavigator *a4,
        struct IXPathNodeIterator **a5)
{
  int v8; // ebx
  struct IXPathNodeIterator *v9; // rbx
  unsigned int CCH; // eax
  int v11; // edi
  bool v12; // zf
  struct XPathEvaluationContext *v14; // [rsp+20h] [rbp-20h] BYREF
  struct IXPathNodeIterator *v15; // [rsp+28h] [rbp-18h] BYREF
  XPathExpressionBase *v16[2]; // [rsp+30h] [rbp-10h] BYREF

  v16[0] = 0;
  v8 = XPathQueryStringCompiler::CompileInternal(this, a2, a3, (struct IUnknown **)v16);
  if ( v8 >= 0 )
  {
    v9 = v16[0];
    v14 = 0;
    if ( XPathExpressionBase::IsNodeSet(v16[0]) )
    {
      v11 = XPathEvaluationContext::CreateInstance((struct IXPathEvaluationContextExtension *)a2, a4, &v14);
      if ( v11 >= 0 )
      {
        if ( v9 )
        {
          v12 = v9 == (struct IXPathNodeIterator *)8;
          v9 = (struct IXPathNodeIterator *)((char *)v9 - 8);
          v15 = v9;
          if ( !v12 )
            _InterlockedIncrement((volatile signed __int32 *)v9 + 4);
        }
        else
        {
          v15 = 0;
        }
        v11 = (*(__int64 (__fastcall **)(struct IXPathNodeIterator *, struct XPathEvaluationContext *))(*(_QWORD *)v9 + 96LL))(
                v9,
                v14);
        if ( v11 >= 0 )
        {
          v15 = 0;
          *a5 = v9;
          InvasivePtr<UnionExpressionIterator>::Reset(&v15);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
          v8 = 0;
          goto LABEL_16;
        }
        InvasivePtr<UnionExpressionIterator>::Reset(&v15);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
      v8 = v11;
    }
    else
    {
      v8 = String::Initialize((String *)&v14, a3);
      if ( v8 >= 0 )
      {
        CCH = String::QueryCCH((String *)&v14);
        v8 = ExceptionHelpers::SetCompilationException((struct String *)&v14, 0, CCH, 0x6Cu);
        if ( v8 >= 0 )
          v8 = -2147024809;
      }
      String::Reset((String *)&v14);
    }
  }
LABEL_16:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v16);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000a280  push    rbp
0x18000a282  push    rbx
0x18000a283  push    rsi
0x18000a284  push    rdi
0x18000a285  push    r14
0x18000a287  mov     rbp, rsp
0x18000a28a  sub     rsp, 40h
0x18000a28e  mov     r14, r9
0x18000a291  mov     [rbp+var_10], 0
0x18000a299  lea     r9, [rbp+var_10]; struct XPathExpressionBase **
0x18000a29d  mov     rdi, r8
0x18000a2a0  mov     rsi, rdx
0x18000a2a3  call    ?CompileInternal@XPathQueryStringCompiler@@AEAAJPEAUIXPathEvaluationContextExtension@@PEBGPEAPEAVXPathExpressionBase@@@Z; XPathQueryStringCompiler::CompileInternal(IXPathEvaluationContextExtension *,ushort const *,XPathExpressionBase * *)
0x18000a2a8  mov     ebx, eax
0x18000a2aa  test    eax, eax
0x18000a2ac  js      loc_18000A38B
0x18000a2b2  mov     rbx, [rbp+var_10]
0x18000a2b6  mov     rcx, rbx; this
0x18000a2b9  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x18000a2be  mov     [rbp+var_20], 0
0x18000a2c6  test    al, al
0x18000a2c8  jnz     short loc_18000A30D
0x18000a2ca  mov     rdx, rdi; unsigned __int16 *
0x18000a2cd  lea     rcx, [rbp+var_20]; this
0x18000a2d1  call    ?Initialize@String@@QEAAJPEBG@Z; String::Initialize(ushort const *)
0x18000a2d6  mov     ebx, eax
0x18000a2d8  test    eax, eax
0x18000a2da  js      short loc_18000A302
0x18000a2dc  lea     rcx, [rbp+var_20]; this
0x18000a2e0  call    ?QueryCCH@String@@QEBAKXZ; String::QueryCCH(void)
0x18000a2e5  xor     edx, edx; unsigned int
0x18000a2e7  lea     rcx, [rbp+var_20]; struct String *
0x18000a2eb  mov     r8d, eax; unsigned int
0x18000a2ee  lea     r9d, [rdx+6Ch]; unsigned int
0x18000a2f2  call    ?SetCompilationException@ExceptionHelpers@@SAJAEAVString@@KKI@Z; ExceptionHelpers::SetCompilationException(String &,ulong,ulong,uint)
0x18000a2f7  mov     ebx, eax
0x18000a2f9  test    eax, eax
0x18000a2fb  js      short loc_18000A302
0x18000a2fd  mov     ebx, 80070057h
0x18000a302  lea     rcx, [rbp+var_20]; this
0x18000a306  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000a30b  jmp     short loc_18000A38B
0x18000a30d  lea     r8, [rbp+var_20]; struct XPathEvaluationContext **
0x18000a311  mov     rdx, r14; struct IXPathNavigator *
0x18000a314  mov     rcx, rsi; struct IXPathEvaluationContextExtension *
0x18000a317  call    ?CreateInstance@XPathEvaluationContext@@SAJPEAUIXPathEvaluationContextExtension@@PEAUIXPathNavigator@@PEAPEAV1@@Z; XPathEvaluationContext::CreateInstance(IXPathEvaluationContextExtension *,IXPathNavigator *,XPathEvaluationContext * *)
0x18000a31c  mov     edi, eax
0x18000a31e  test    eax, eax
0x18000a320  jns     short loc_18000A32F
0x18000a322  lea     rcx, [rbp+var_20]
0x18000a326  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000a32b  mov     ebx, edi
0x18000a32d  jmp     short loc_18000A38B
0x18000a32f  test    rbx, rbx
0x18000a332  jz      short loc_18000A344
0x18000a334  add     rbx, 0FFFFFFFFFFFFFFF8h
0x18000a338  mov     [rbp+var_18], rbx
0x18000a33c  jz      short loc_18000A348
0x18000a33e  lock inc dword ptr [rbx+10h]
0x18000a342  jmp     short loc_18000A348
0x18000a344  mov     [rbp+var_18], rbx
0x18000a348  mov     rax, [rbx]
0x18000a34b  mov     rcx, rbx
0x18000a34e  mov     rdx, [rbp+var_20]
0x18000a352  mov     rax, [rax+60h]
0x18000a356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a35b  lea     rcx, [rbp+var_18]
0x18000a35f  mov     edi, eax
0x18000a361  test    eax, eax
0x18000a363  jns     short loc_18000A36C
0x18000a365  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x18000a36a  jmp     short loc_18000A322
0x18000a36c  mov     rax, [rbp+arg_20]
0x18000a370  mov     [rbp+var_18], 0
0x18000a378  mov     [rax], rbx
0x18000a37b  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x18000a380  lea     rcx, [rbp+var_20]
0x18000a384  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000a389  xor     ebx, ebx
0x18000a38b  lea     rcx, [rbp+var_10]
0x18000a38f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000a394  mov     eax, ebx
0x18000a396  add     rsp, 40h
0x18000a39a  pop     r14
0x18000a39c  pop     rdi
0x18000a39d  pop     rsi
0x18000a39e  pop     rbx
0x18000a39f  pop     rbp
0x18000a3a0  retn
```
