# XPathEvaluationContext::CreateInstance(IXPathEvaluationContextExtension *,IXPathNavigator *,XPathEvaluationContext * *)

- ea: `0x180005124`
- end: `0x1800051fd`
- name: `?CreateInstance@XPathEvaluationContext@@SAJPEAUIXPathEvaluationContextExtension@@PEAUIXPathNavigator@@PEAPEAV1@@Z`
- size: `217`
- prototype: `static int(struct IXPathEvaluationContextExtension *, struct IXPathNavigator *, struct XPathEvaluationContext **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a280`

## callees

- `0x180001078`
- `0x1800020b4`
- `0x1800021a4`
- `0x180004b84`
- `0x180005124`
- `0x18000e6e8`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathEvaluationContext::CreateInstance(
        struct IXPathEvaluationContextExtension *a1,
        struct IUnknown *a2,
        struct XPathEvaluationContext **a3)
{
  char *v6; // rbx
  int v7; // edi
  char *v9; // [rsp+68h] [rbp+20h] BYREF

  v6 = (char *)operator new(0x38u);
  if ( !v6 )
  {
    v7 = -2147024882;
    goto LABEL_9;
  }
  *(_QWORD *)v6 = &SimpleIUnknownImpl<IXPathEvaluationContext>::`vftable';
  *((_DWORD *)v6 + 2) = 1;
  ModuleRefCounter::AddRef();
  *(_QWORD *)v6 = &XPathEvaluationContext::`vftable';
  *((_QWORD *)v6 + 2) = a1;
  if ( a1 )
    (*(void (__fastcall **)(struct IXPathEvaluationContextExtension *))(*(_QWORD *)a1 + 8LL))(a1);
  *((_QWORD *)v6 + 3) = 0;
  *((_QWORD *)v6 + 4) = 0;
  *((_DWORD *)v6 + 10) = 0;
  *((_DWORD *)v6 + 11) = 7;
  v6[48] = 0;
  v6[48] = 0;
  v9 = v6;
  if ( *((struct IUnknown **)v6 + 4) != a2 )
    ATL::AtlComPtrAssign((struct IUnknown **)v6 + 4, a2);
  v7 = XPathNavigatorInternal::ResetToRoot((XPathNavigatorInternal *)(v6 + 32));
  if ( v7 >= 0 )
  {
    *a3 = (struct XPathEvaluationContext *)v6;
    v7 = 0;
LABEL_9:
    v9 = 0;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v9);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180005124  push    rbx
0x180005126  push    rsi
0x180005127  push    rdi
0x180005128  push    r14
0x18000512a  sub     rsp, 28h
0x18000512e  mov     rdi, rcx
0x180005131  mov     r14, r8
0x180005134  mov     ecx, 38h ; '8'; Size
0x180005139  mov     rsi, rdx
0x18000513c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005141  mov     rbx, rax
0x180005144  test    rax, rax
0x180005147  jz      loc_1800051D9
0x18000514d  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathEvaluationContext@@@@6B@; const SimpleIUnknownImpl<IXPathEvaluationContext>::`vftable'
0x180005154  mov     [rbx], rax
0x180005157  mov     dword ptr [rbx+8], 1
0x18000515e  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180005163  lea     rax, ??_7XPathEvaluationContext@@6B@; const XPathEvaluationContext::`vftable'
0x18000516a  mov     [rbx], rax
0x18000516d  mov     [rbx+10h], rdi
0x180005171  test    rdi, rdi
0x180005174  jz      short loc_180005185
0x180005176  mov     rax, [rdi]
0x180005179  mov     rcx, rdi
0x18000517c  mov     rax, [rax+8]
0x180005180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005185  mov     qword ptr [rbx+18h], 0
0x18000518d  lea     rdi, [rbx+20h]
0x180005191  mov     qword ptr [rbx+20h], 0
0x180005199  mov     dword ptr [rbx+28h], 0
0x1800051a0  mov     dword ptr [rbx+2Ch], 7
0x1800051a7  mov     byte ptr [rbx+30h], 0
0x1800051ab  mov     byte ptr [rdi+10h], 0
0x1800051af  mov     [rsp+48h+arg_18], rbx
0x1800051b4  cmp     [rdi], rsi
0x1800051b7  jz      short loc_1800051C4
0x1800051b9  mov     rdx, rsi; struct IUnknown *
0x1800051bc  mov     rcx, rdi; struct IUnknown **
0x1800051bf  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800051c4  mov     rcx, rdi; this
0x1800051c7  call    ?ResetToRoot@XPathNavigatorInternal@@QEAAJXZ; XPathNavigatorInternal::ResetToRoot(void)
0x1800051cc  mov     edi, eax
0x1800051ce  test    eax, eax
0x1800051d0  js      short loc_1800051E7
0x1800051d2  mov     [r14], rbx
0x1800051d5  xor     edi, edi
0x1800051d7  jmp     short loc_1800051DE
0x1800051d9  mov     edi, 8007000Eh
0x1800051de  mov     [rsp+48h+arg_18], 0
0x1800051e7  lea     rcx, [rsp+48h+arg_18]
0x1800051ec  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800051f1  mov     eax, edi
0x1800051f3  add     rsp, 28h
0x1800051f7  pop     r14
0x1800051f9  pop     rdi
0x1800051fa  pop     rsi
0x1800051fb  pop     rbx
0x1800051fc  retn
```
