# XPathQueryStringCompiler::ProcessFunctionCallNode(Node *,Token *,Node *)

- ea: `0x180009164`
- end: `0x180009288`
- name: `?ProcessFunctionCallNode@XPathQueryStringCompiler@@AEAAJPEAVNode@@PEAVToken@@0@Z`
- size: `292`
- prototype: `__int64 __fastcall(XPathQueryStringCompiler *this, struct Node *, struct Token *, struct Node *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001c80`
- `0x180001ca0`

## callees

- `0x180004bdc`
- `0x1800056a0`
- `0x18000835c`
- `0x180009164`
- `0x18000a3a8`
- `0x18000f690`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::ProcessFunctionCallNode(
        XPathQueryStringCompiler *this,
        struct Node *a2,
        struct Token *a3,
        struct Node *a4)
{
  struct XPathExpressionBase **v4; // rbp
  int v8; // ebx
  const unsigned __int16 *v9; // r8
  int FunctionExpressionInternal; // esi
  unsigned int v11; // ebx
  unsigned int v12; // eax
  int v13; // eax
  unsigned int Length; // ebx
  unsigned int v15; // eax
  int v17; // [rsp+30h] [rbp-48h] BYREF
  __int128 v18; // [rsp+38h] [rbp-40h] BYREF
  __int64 v19; // [rsp+48h] [rbp-30h]

  v4 = (struct XPathExpressionBase **)*((_QWORD *)this + 5);
  v17 = 0;
  v19 = 0;
  *((_QWORD *)this + 5) = 0;
  v18 = 0;
  if ( !a4
    || (v17 = 1,
        *((_QWORD *)this + 5) = &v17,
        *((_DWORD *)this + 12) = 6,
        v8 = XPathQueryStringCompiler::Dispatch(this, a4),
        v8 >= 0) )
  {
    v9 = &qword_180016F98;
    if ( *((_QWORD *)a3 + 6) )
      v9 = (const unsigned __int16 *)*((_QWORD *)a3 + 6);
    FunctionExpressionInternal = XPathEvaluationContext::TryCreateFunctionExpressionInternal(
                                   *((_QWORD *)this + 7),
                                   (int)&qword_180016F98,
                                   (int)v9,
                                   (int)&v18,
                                   v4);
    if ( FunctionExpressionInternal >= 0 )
    {
      if ( FunctionExpressionInternal == 1 )
      {
        Length = Node::GetLength(a2);
        v15 = ((__int64 (__fastcall *)(struct Node *))a2->lpVtbl->Release)(a2);
        if ( (int)ExceptionHelpers::SetCompilationException((const unsigned __int16 **)this + 2, v15, Length, 0x66u) >= 0 )
          v8 = -2147024809;
        else
          v8 = 1;
      }
      else
      {
        v8 = 0;
      }
    }
    else
    {
      v11 = Node::GetLength(a2);
      v12 = ((__int64 (__fastcall *)(struct Node *))a2->lpVtbl->Release)(a2);
      v13 = ExceptionHelpers::SetCompilationException((const unsigned __int16 **)this + 2, v12, v11, 0x67u);
      if ( v13 >= 0 )
        v8 = FunctionExpressionInternal;
      else
        v8 = v13;
    }
  }
  List<ATL::CComPtr<XPathExpressionBase>>::Clear(&v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180009164  mov     rax, rsp
0x180009167  push    rbx
0x180009168  push    rbp
0x180009169  push    rsi
0x18000916a  push    rdi
0x18000916b  push    r14
0x18000916d  sub     rsp, 50h
0x180009171  mov     rbp, [rcx+28h]
0x180009175  xorps   xmm0, xmm0
0x180009178  mov     dword ptr [rax-48h], 0
0x18000917f  mov     rsi, r8
0x180009182  mov     qword ptr [rax-30h], 0
0x18000918a  mov     r14, rdx
0x18000918d  mov     qword ptr [rcx+28h], 0
0x180009195  mov     rdi, rcx
0x180009198  movdqu  xmmword ptr [rax-40h], xmm0
0x18000919d  test    r9, r9
0x1800091a0  jz      short loc_1800091CA
0x1800091a2  mov     dword ptr [rax-48h], 1
0x1800091a9  lea     rax, [rax-48h]
0x1800091ad  mov     rdx, r9; struct Node *
0x1800091b0  mov     [rcx+28h], rax
0x1800091b4  mov     dword ptr [rcx+30h], 6
0x1800091bb  call    ?Dispatch@XPathQueryStringCompiler@@QEAAJPEAVNode@@@Z; XPathQueryStringCompiler::Dispatch(Node *)
0x1800091c0  mov     ebx, eax
0x1800091c2  test    eax, eax
0x1800091c4  js      loc_180009271
0x1800091ca  cmp     qword ptr [rsi+30h], 0
0x1800091cf  lea     rdx, qword_180016F98; int
0x1800091d6  mov     rcx, [rdi+38h]; int
0x1800091da  lea     r9, [rsp+78h+var_40]; int
0x1800091df  mov     r8, rdx
0x1800091e2  mov     [rsp+78h+var_58], rbp; struct XPathExpressionBase **
0x1800091e7  cmovnz  r8, [rsi+30h]; int
0x1800091ec  call    ?TryCreateFunctionExpressionInternal@XPathEvaluationContext@@SAJPEAUIXPathEvaluationContextExtension@@PEBG1AEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z; XPathEvaluationContext::TryCreateFunctionExpressionInternal(IXPathEvaluationContextExtension *,ushort const *,ushort const *,List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)
0x1800091f1  mov     esi, eax
0x1800091f3  test    eax, eax
0x1800091f5  jns     short loc_180009230
0x1800091f7  mov     rcx, r14; this
0x1800091fa  call    ?GetLength@Node@@QEAAKXZ; Node::GetLength(void)
0x1800091ff  mov     rcx, [r14]
0x180009202  mov     ebx, eax
0x180009204  mov     rax, [rcx+10h]
0x180009208  mov     rcx, r14
0x18000920b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009210  lea     rcx, [rdi+10h]; struct String *
0x180009214  mov     r9d, 67h ; 'g'; unsigned int
0x18000921a  mov     r8d, ebx; unsigned int
0x18000921d  mov     edx, eax; unsigned int
0x18000921f  call    ?SetCompilationException@ExceptionHelpers@@SAJAEAVString@@KKI@Z; ExceptionHelpers::SetCompilationException(String &,ulong,ulong,uint)
0x180009224  test    eax, eax
0x180009226  jns     short loc_18000922C
0x180009228  mov     ebx, eax
0x18000922a  jmp     short loc_180009271
0x18000922c  mov     ebx, esi
0x18000922e  jmp     short loc_180009271
0x180009230  cmp     esi, 1
0x180009233  jnz     short loc_18000926F
0x180009235  mov     rcx, r14; this
0x180009238  call    ?GetLength@Node@@QEAAKXZ; Node::GetLength(void)
0x18000923d  mov     rcx, [r14]
0x180009240  mov     ebx, eax
0x180009242  mov     rax, [rcx+10h]
0x180009246  mov     rcx, r14
0x180009249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000924e  lea     rcx, [rdi+10h]; struct String *
0x180009252  mov     r8d, ebx; unsigned int
0x180009255  lea     r9d, [rsi+65h]; unsigned int
0x180009259  mov     edx, eax; unsigned int
0x18000925b  call    ?SetCompilationException@ExceptionHelpers@@SAJAEAVString@@KKI@Z; ExceptionHelpers::SetCompilationException(String &,ulong,ulong,uint)
0x180009260  test    eax, eax
0x180009262  jns     short loc_180009268
0x180009264  mov     ebx, esi
0x180009266  jmp     short loc_180009271
0x180009268  mov     ebx, 80070057h
0x18000926d  jmp     short loc_180009271
0x18000926f  xor     ebx, ebx
0x180009271  lea     rcx, [rsp+78h+var_40]
0x180009276  call    ?Clear@?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAXXZ; List<ATL::CComPtr<XPathExpressionBase>>::Clear(void)
0x18000927b  mov     eax, ebx
0x18000927d  add     rsp, 50h
0x180009281  pop     r14
0x180009283  pop     rdi
0x180009284  pop     rsi
0x180009285  pop     rbp
0x180009286  pop     rbx
0x180009287  retn
```
