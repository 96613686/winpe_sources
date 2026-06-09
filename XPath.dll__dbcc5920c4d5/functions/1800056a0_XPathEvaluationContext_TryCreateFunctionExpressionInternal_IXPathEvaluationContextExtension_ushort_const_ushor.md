# XPathEvaluationContext::TryCreateFunctionExpressionInternal(IXPathEvaluationContextExtension *,ushort const *,ushort const *,List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x1800056a0`
- end: `0x180005825`
- name: `?TryCreateFunctionExpressionInternal@XPathEvaluationContext@@SAJPEAUIXPathEvaluationContextExtension@@PEBG1AEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `389`
- prototype: `__int64 __fastcall(__int64 *, __int64, char *, __int64, struct XPathExpressionBase **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180005550`
- `0x180009164`

## callees

- `0x1800010b8`
- `0x1800010c4`
- `0x1800020b4`
- `0x180004960`
- `0x180004d24`
- `0x1800056a0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathEvaluationContext::TryCreateFunctionExpressionInternal(
        __int64 *a1,
        __int64 a2,
        char *a3,
        __int64 a4,
        struct XPathExpressionBase **a5)
{
  unsigned __int16 i; // ax
  unsigned __int16 *v10; // rcx
  int v11; // r9d
  int v12; // edx
  __int64 (__fastcall *v13)(__int64, struct XPathExpressionBase **); // rax
  int v14; // eax
  unsigned int v15; // ecx
  unsigned __int64 v17; // rdi
  _QWORD *v18; // rbx
  __int64 j; // r8
  __int64 v20; // rax
  int ExpressionWrapper; // edi
  struct IUnknown *v22[9]; // [rsp+40h] [rbp-48h] BYREF

  for ( i = 0; ; ++i )
  {
    if ( i >= 0x1Bu )
      goto LABEL_12;
    v10 = (unsigned __int16 *)a3;
    do
    {
      v11 = *(unsigned __int16 *)((char *)v10 + (char *)(&off_180019000)[2 * i] - a3);
      v12 = *v10 - v11;
      if ( v12 )
        break;
      ++v10;
    }
    while ( v11 );
    if ( !v12 )
      break;
  }
  v13 = (__int64 (__fastcall *)(__int64, struct XPathExpressionBase **))*(&funcs_180005714 + 2 * i);
  if ( !v13 )
  {
LABEL_12:
    if ( a1 )
    {
      v17 = *(unsigned int *)(a4 + 20);
      if ( (_DWORD)v17 )
      {
        v18 = operator new[](saturated_mul(v17, 8u));
        if ( !v18 )
        {
          operator delete(0);
          return 2147942414LL;
        }
        for ( j = 0; (unsigned int)j < *(_DWORD *)(a4 + 20); j = (unsigned int)(j + 1) )
          v18[j] = *(_QWORD *)(*(_QWORD *)(a4 + 8) + 8 * j);
      }
      else
      {
        LODWORD(v17) = 0;
        v18 = 0;
      }
      v20 = *a1;
      v22[0] = 0;
      ExpressionWrapper = (*(__int64 (__fastcall **)(__int64 *, __int64, char *, _QWORD, _QWORD *, struct IUnknown **))(v20 + 24))(
                            a1,
                            a2,
                            a3,
                            (unsigned int)v17,
                            v18,
                            v22);
      if ( ExpressionWrapper < 0 )
        goto LABEL_21;
      if ( !ExpressionWrapper && v22[0] )
      {
        ExpressionWrapper = XPathEvaluationContext::CreateExpressionWrapper(v22[0], a5);
        if ( ExpressionWrapper >= 0 )
          ExpressionWrapper = 0;
LABEL_21:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v22);
        operator delete(v18);
        return (unsigned int)ExpressionWrapper;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v22);
      operator delete(v18);
    }
    return 1;
  }
  v14 = v13(a4, a5);
  v15 = 0;
  if ( v14 < 0 )
    return (unsigned int)v14;
  return v15;
}

```

## disassembly

```asm
0x1800056a0  push    rbx
0x1800056a2  push    rbp
0x1800056a3  push    rsi
0x1800056a4  push    rdi
0x1800056a5  push    r12
0x1800056a7  push    r14
0x1800056a9  push    r15
0x1800056ab  sub     rsp, 50h
0x1800056af  xor     eax, eax
0x1800056b1  lea     r11, off_180019000; "last"
0x1800056b8  mov     rsi, r9
0x1800056bb  mov     rbp, r8
0x1800056be  mov     r15, rdx
0x1800056c1  mov     r14, rcx
0x1800056c4  lea     r12d, [rax+1]
0x1800056c8  cmp     ax, 1Bh
0x1800056cc  jnb     short loc_180005727
0x1800056ce  movzx   r8d, ax
0x1800056d2  mov     rcx, rbp
0x1800056d5  add     r8, r8
0x1800056d8  mov     r10, [r11+r8*8]
0x1800056dc  sub     r10, rbp
0x1800056df  movzx   edx, word ptr [rcx]
0x1800056e2  movzx   r9d, word ptr [rcx+r10]
0x1800056e7  sub     edx, r9d
0x1800056ea  jnz     short loc_1800056F5
0x1800056ec  add     rcx, 2
0x1800056f0  test    r9d, r9d
0x1800056f3  jnz     short loc_1800056DF
0x1800056f5  test    edx, edx
0x1800056f7  jz      short loc_1800056FF
0x1800056f9  add     ax, r12w
0x1800056fd  jmp     short loc_1800056C8
0x1800056ff  mov     rax, (funcs_180005714 - 180019000h)[r11+r8*8]
0x180005704  test    rax, rax
0x180005707  jz      short loc_180005727
0x180005709  mov     rdx, [rsp+88h+arg_20]
0x180005711  mov     rcx, rsi
0x180005714  call    _guard_dispatch_icall$thunk$10345483385596137414; FunctionZeroArityExpressionTemplate<LastFunctionExpression,NumberExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *) ...
0x180005719  xor     ecx, ecx
0x18000571b  test    eax, eax
0x18000571d  cmovs   ecx, eax
0x180005720  mov     eax, ecx
0x180005722  jmp     loc_180005816
0x180005727  test    r14, r14
0x18000572a  jz      loc_180005813
0x180005730  mov     edi, [rsi+14h]
0x180005733  test    edi, edi
0x180005735  jz      short loc_18000578C
0x180005737  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000573e  mov     eax, 8
0x180005743  mul     rdi
0x180005746  cmovb   rax, rcx
0x18000574a  mov     rcx, rax; unsigned __int64
0x18000574d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180005752  mov     rbx, rax
0x180005755  test    rax, rax
0x180005758  jnz     short loc_18000576C
0x18000575a  mov     rcx, rax; Block
0x18000575d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005762  mov     eax, 8007000Eh
0x180005767  jmp     loc_180005816
0x18000576c  xor     r8d, r8d
0x18000576f  cmp     [rsi+14h], r8d
0x180005773  jbe     short loc_180005790
0x180005775  mov     rax, [rsi+8]
0x180005779  mov     rcx, [rax+r8*8]
0x18000577d  mov     [rbx+r8*8], rcx
0x180005781  add     r8d, r12d
0x180005784  cmp     r8d, [rsi+14h]
0x180005788  jb      short loc_180005775
0x18000578a  jmp     short loc_180005790
0x18000578c  xor     edi, edi
0x18000578e  xor     ebx, ebx
0x180005790  mov     rax, [r14]
0x180005793  lea     rcx, [rsp+88h+var_48]
0x180005798  mov     [rsp+88h+var_60], rcx
0x18000579d  mov     r9d, edi
0x1800057a0  mov     r8, rbp
0x1800057a3  mov     [rsp+88h+var_48], 0
0x1800057ac  mov     rdx, r15
0x1800057af  mov     [rsp+88h+var_68], rbx
0x1800057b4  mov     rax, [rax+18h]
0x1800057b8  mov     rcx, r14
0x1800057bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057c0  mov     edi, eax
0x1800057c2  test    eax, eax
0x1800057c4  jns     short loc_1800057DC
0x1800057c6  lea     rcx, [rsp+88h+var_48]
0x1800057cb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800057d0  mov     rcx, rbx; Block
0x1800057d3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800057d8  mov     eax, edi
0x1800057da  jmp     short loc_180005816
0x1800057dc  test    edi, edi
0x1800057de  jnz     short loc_180005801
0x1800057e0  mov     rcx, [rsp+88h+var_48]; struct IUnknown *
0x1800057e5  test    rcx, rcx
0x1800057e8  jz      short loc_180005801
0x1800057ea  mov     rdx, [rsp+88h+arg_20]; struct XPathExpressionBase **
0x1800057f2  call    ?CreateExpressionWrapper@XPathEvaluationContext@@CAJPEAUIUnknown@@PEAPEAVXPathExpressionBase@@@Z; XPathEvaluationContext::CreateExpressionWrapper(IUnknown *,XPathExpressionBase * *)
0x1800057f7  mov     edi, eax
0x1800057f9  test    eax, eax
0x1800057fb  js      short loc_1800057C6
0x1800057fd  xor     edi, edi
0x1800057ff  jmp     short loc_1800057C6
0x180005801  lea     rcx, [rsp+88h+var_48]
0x180005806  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000580b  mov     rcx, rbx; Block
0x18000580e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005813  mov     eax, r12d
0x180005816  add     rsp, 50h
0x18000581a  pop     r15
0x18000581c  pop     r14
0x18000581e  pop     r12
0x180005820  pop     rdi
0x180005821  pop     rsi
0x180005822  pop     rbp
0x180005823  pop     rbx
0x180005824  retn
```
