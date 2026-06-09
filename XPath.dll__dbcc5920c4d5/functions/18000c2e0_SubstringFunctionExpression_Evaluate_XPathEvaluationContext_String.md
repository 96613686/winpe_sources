# SubstringFunctionExpression::Evaluate(XPathEvaluationContext *,String &)

- ea: `0x18000c2e0`
- end: `0x18000c480`
- name: `?Evaluate@SubstringFunctionExpression@@UEAAJPEAVXPathEvaluationContext@@AEAVString@@@Z`
- size: `416`
- prototype: `__int64 __fastcall(SubstringFunctionExpression *this, struct XPathEvaluationContext *, struct String *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000c2e0`
- `0x18000c750`
- `0x180010ee0`
- `0x180010f08`
- `0x180010f98`
- `0x180010fac`
- `0x180012010`

## import_xrefs

- `msvcrt!_isnan` at `0x18000c371`
- `msvcrt!_isnan` at `0x18000c418`
- `msvcrt!_isnan` at `0x18000c371`
- `msvcrt!_isnan` at `0x18000c418`

## pseudocode

```c
__int64 __fastcall SubstringFunctionExpression::Evaluate(
        SubstringFunctionExpression *this,
        struct XPathEvaluationContext *a2,
        struct String *a3)
{
  _QWORD *v6; // rax
  int v7; // ebx
  unsigned int v8; // esi
  unsigned int CCH; // eax
  unsigned int v10; // ebx
  const unsigned __int16 *v11; // rcx
  int v12; // eax
  double v13; // xmm6_8
  const unsigned __int16 *v14; // rcx
  unsigned int v15; // eax
  double v17[2]; // [rsp+20h] [rbp-30h] BYREF
  const unsigned __int16 *v18; // [rsp+80h] [rbp+30h] BYREF
  double X; // [rsp+98h] [rbp+48h] BYREF

  String::Reset(a3);
  v6 = (_QWORD *)*((_QWORD *)this + 3);
  v18 = 0;
  X = 0.0;
  v17[0] = 0.0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, struct XPathEvaluationContext *, const unsigned __int16 **))(*(_QWORD *)*v6 + 64LL))(
         *v6,
         a2,
         &v18);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, struct XPathEvaluationContext *, double *))(**(_QWORD **)(*((_QWORD *)this + 3) + 8LL)
                                                                                      + 72LL))(
           *(_QWORD *)(*((_QWORD *)this + 3) + 8LL),
           a2,
           &X);
    if ( v7 >= 0 )
    {
      if ( !_isnan(X) )
      {
        X = RoundFunctionExpression::Round(X);
        v8 = (int)fmax(0.0, X - 1.0);
        CCH = String::QueryCCH((String *)&v18);
        v10 = CCH - v8;
        if ( CCH != v8 )
        {
          if ( *((_DWORD *)this + 9) == 2 )
          {
            v11 = &qword_180016F98;
            if ( v18 )
              v11 = v18;
            v12 = String::Initialize(a3, &v11[v8]);
            goto LABEL_9;
          }
          v12 = (*(__int64 (__fastcall **)(_QWORD, struct XPathEvaluationContext *, double *))(**(_QWORD **)(*((_QWORD *)this + 3) + 16LL)
                                                                                             + 72LL))(
                  *(_QWORD *)(*((_QWORD *)this + 3) + 16LL),
                  a2,
                  v17);
          if ( v12 < 0 )
          {
LABEL_9:
            v7 = v12;
            goto LABEL_18;
          }
          v17[0] = RoundFunctionExpression::Round(v17[0]);
          v13 = v17[0] + X;
          if ( !_isnan(v17[0] + X) )
          {
            v14 = &qword_180016F98;
            v15 = (int)fmax(0.0, v13);
            if ( v15 >= v10 )
              v15 = v10;
            if ( v18 )
              v14 = v18;
            v12 = String::Initialize(a3, &v14[v8], v15);
            goto LABEL_9;
          }
        }
      }
      v7 = 0;
    }
  }
LABEL_18:
  String::Reset((String *)&v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000c2e0  mov     [rsp-28h+arg_8], rbx
0x18000c2e5  push    rbp
0x18000c2e6  push    rsi
0x18000c2e7  push    rdi
0x18000c2e8  push    r14
0x18000c2ea  push    r15
0x18000c2ec  mov     rbp, rsp
0x18000c2ef  sub     rsp, 50h
0x18000c2f3  mov     rdi, rcx
0x18000c2f6  movaps  [rsp+50h+var_10], xmm6
0x18000c2fb  mov     rcx, r8; this
0x18000c2fe  movaps  [rsp+50h+var_20], xmm7
0x18000c303  mov     r15, r8
0x18000c306  mov     r14, rdx
0x18000c309  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000c30e  mov     rax, [rdi+18h]
0x18000c312  lea     r8, [rbp+arg_0]
0x18000c316  xorps   xmm7, xmm7
0x18000c319  mov     [rbp+arg_0], 0
0x18000c321  movsd   [rbp+X], xmm7
0x18000c326  mov     rdx, r14
0x18000c329  movsd   [rbp+var_30], xmm7
0x18000c32e  mov     rcx, [rax]
0x18000c331  mov     rax, [rcx]
0x18000c334  mov     rax, [rax+40h]
0x18000c338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c33d  mov     ebx, eax
0x18000c33f  test    eax, eax
0x18000c341  js      loc_18000C457
0x18000c347  mov     rax, [rdi+18h]
0x18000c34b  lea     r8, [rbp+X]
0x18000c34f  mov     rdx, r14
0x18000c352  mov     rcx, [rax+8]
0x18000c356  mov     rax, [rcx]
0x18000c359  mov     rax, [rax+48h]
0x18000c35d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c362  mov     ebx, eax
0x18000c364  test    eax, eax
0x18000c366  js      loc_18000C457
0x18000c36c  movsd   xmm0, [rbp+X]; X
0x18000c371  call    cs:__imp__isnan
0x18000c377  test    eax, eax
0x18000c379  jnz     loc_18000C455
0x18000c37f  movsd   xmm0, [rbp+X]; double
0x18000c384  call    ?Round@RoundFunctionExpression@@SANN@Z; RoundFunctionExpression::Round(double)
0x18000c389  movsd   [rbp+X], xmm0
0x18000c38e  lea     rcx, [rbp+arg_0]; this
0x18000c392  subsd   xmm0, cs:__real@3ff0000000000000
0x18000c39a  xorps   xmm1, xmm1
0x18000c39d  maxsd   xmm1, xmm0
0x18000c3a1  cvttsd2si rsi, xmm1
0x18000c3a6  call    ?QueryCCH@String@@QEBAKXZ; String::QueryCCH(void)
0x18000c3ab  mov     ebx, eax
0x18000c3ad  sub     ebx, esi
0x18000c3af  jz      loc_18000C455
0x18000c3b5  cmp     dword ptr [rdi+24h], 2
0x18000c3b9  jnz     short loc_18000C3DF
0x18000c3bb  mov     rax, [rbp+arg_0]
0x18000c3bf  lea     rcx, qword_180016F98
0x18000c3c6  test    rax, rax
0x18000c3c9  cmovnz  rcx, rax
0x18000c3cd  mov     eax, esi
0x18000c3cf  lea     rdx, [rcx+rax*2]; unsigned __int16 *
0x18000c3d3  mov     rcx, r15; this
0x18000c3d6  call    ?Initialize@String@@QEAAJPEBG@Z; String::Initialize(ushort const *)
0x18000c3db  mov     ebx, eax
0x18000c3dd  jmp     short loc_18000C457
0x18000c3df  mov     rax, [rdi+18h]
0x18000c3e3  lea     r8, [rbp+var_30]
0x18000c3e7  mov     rdx, r14
0x18000c3ea  mov     rcx, [rax+10h]
0x18000c3ee  mov     rax, [rcx]
0x18000c3f1  mov     rax, [rax+48h]
0x18000c3f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3fa  test    eax, eax
0x18000c3fc  js      short loc_18000C3DB
0x18000c3fe  movsd   xmm0, [rbp+var_30]; double
0x18000c403  call    ?Round@RoundFunctionExpression@@SANN@Z; RoundFunctionExpression::Round(double)
0x18000c408  movaps  xmm6, xmm0
0x18000c40b  movsd   [rbp+var_30], xmm0
0x18000c410  addsd   xmm6, [rbp+X]
0x18000c415  movaps  xmm0, xmm6; X
0x18000c418  call    cs:__imp__isnan
0x18000c41e  test    eax, eax
0x18000c420  jnz     short loc_18000C455
0x18000c422  maxsd   xmm7, xmm6
0x18000c426  lea     rcx, qword_180016F98
0x18000c42d  cvttsd2si rax, xmm7
0x18000c432  cmp     eax, ebx
0x18000c434  cmovnb  eax, ebx
0x18000c437  mov     r8d, eax; unsigned __int64
0x18000c43a  mov     rax, [rbp+arg_0]
0x18000c43e  test    rax, rax
0x18000c441  cmovnz  rcx, rax
0x18000c445  mov     eax, esi
0x18000c447  lea     rdx, [rcx+rax*2]; Src
0x18000c44b  mov     rcx, r15; this
0x18000c44e  call    ?Initialize@String@@QEAAJPEBG_K@Z; String::Initialize(ushort const *,unsigned __int64)
0x18000c453  jmp     short loc_18000C3DB
0x18000c455  xor     ebx, ebx
0x18000c457  lea     rcx, [rbp+arg_0]; this
0x18000c45b  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000c460  movaps  xmm6, [rsp+50h+var_10]
0x18000c465  mov     eax, ebx
0x18000c467  mov     rbx, [rsp+50h+arg_8]
0x18000c46f  movaps  xmm7, [rsp+50h+var_20]
0x18000c474  add     rsp, 50h
0x18000c478  pop     r15
0x18000c47a  pop     r14
0x18000c47c  pop     rdi
0x18000c47d  pop     rsi
0x18000c47e  pop     rbp
0x18000c47f  retn
```
