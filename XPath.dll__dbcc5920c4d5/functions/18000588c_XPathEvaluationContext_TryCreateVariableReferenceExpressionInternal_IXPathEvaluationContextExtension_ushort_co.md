# XPathEvaluationContext::TryCreateVariableReferenceExpressionInternal(IXPathEvaluationContextExtension *,ushort const *,ushort const *,XPathExpressionBase * *)

- ea: `0x18000588c`
- end: `0x1800058f7`
- name: `?TryCreateVariableReferenceExpressionInternal@XPathEvaluationContext@@SAJPEAUIXPathEvaluationContextExtension@@PEBG1PEAPEAVXPathExpressionBase@@@Z`
- size: `107`
- prototype: `static int(struct IXPathEvaluationContextExtension *, const unsigned __int16 *, const unsigned __int16 *, struct XPathExpressionBase **)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005830`
- `0x180009b1c`

## callees

- `0x1800020b4`
- `0x180004d24`
- `0x18000588c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathEvaluationContext::TryCreateVariableReferenceExpressionInternal(
        struct IXPathEvaluationContextExtension *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IUnknown ***a4)
{
  __int64 v5; // rax
  int ExpressionWrapper; // ebx
  struct IUnknown *v8; // [rsp+40h] [rbp+8h] BYREF

  if ( !a1 )
    return 1;
  v5 = *(_QWORD *)a1;
  v8 = 0;
  ExpressionWrapper = (*(__int64 (__fastcall **)(struct IXPathEvaluationContextExtension *, const unsigned __int16 *, const unsigned __int16 *, struct IUnknown **))(v5 + 32))(
                        a1,
                        a2,
                        a3,
                        &v8);
  if ( ExpressionWrapper >= 0 )
  {
    if ( ExpressionWrapper
      || (ExpressionWrapper = XPathEvaluationContext::CreateExpressionWrapper(v8, a4), ExpressionWrapper >= 0) )
    {
      ExpressionWrapper = 0;
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v8);
  return (unsigned int)ExpressionWrapper;
}

```

## disassembly

```asm
0x18000588c  mov     [rsp+arg_8], rbx
0x180005891  push    rdi
0x180005892  sub     rsp, 30h
0x180005896  mov     rdi, r9
0x180005899  test    rcx, rcx
0x18000589c  jz      short loc_1800058E7
0x18000589e  mov     rax, [rcx]
0x1800058a1  lea     r9, [rsp+38h+arg_0]
0x1800058a6  mov     [rsp+38h+arg_0], 0
0x1800058af  mov     rax, [rax+20h]
0x1800058b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058b8  mov     ebx, eax
0x1800058ba  test    eax, eax
0x1800058bc  jns     short loc_1800058CC
0x1800058be  lea     rcx, [rsp+38h+arg_0]
0x1800058c3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800058c8  mov     eax, ebx
0x1800058ca  jmp     short loc_1800058EC
0x1800058cc  test    ebx, ebx
0x1800058ce  jnz     short loc_1800058E3
0x1800058d0  mov     rcx, [rsp+38h+arg_0]; struct IUnknown *
0x1800058d5  mov     rdx, rdi; struct XPathExpressionBase **
0x1800058d8  call    ?CreateExpressionWrapper@XPathEvaluationContext@@CAJPEAUIUnknown@@PEAPEAVXPathExpressionBase@@@Z; XPathEvaluationContext::CreateExpressionWrapper(IUnknown *,XPathExpressionBase * *)
0x1800058dd  mov     ebx, eax
0x1800058df  test    eax, eax
0x1800058e1  js      short loc_1800058BE
0x1800058e3  xor     ebx, ebx
0x1800058e5  jmp     short loc_1800058BE
0x1800058e7  mov     eax, 1
0x1800058ec  mov     rbx, [rsp+38h+arg_8]
0x1800058f1  add     rsp, 30h
0x1800058f5  pop     rdi
0x1800058f6  retn
```
