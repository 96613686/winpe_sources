# BinaryOperationOnTwoSameOperandTypeExpressionTemplate<RelationalOrEqualityZeroNodeSetExpression<String>,BooleanExpressionBase,String>::Evaluate(XPathEvaluationContext *,bool &)

- ea: `0x180008490`
- end: `0x180008557`
- name: `?Evaluate@?$BinaryOperationOnTwoSameOperandTypeExpressionTemplate@V?$RelationalOrEqualityZeroNodeSetExpression@VString@@@@VBooleanExpressionBase@@VString@@@@UEAAJPEAVXPathEvaluationContext@@AEA_N@Z`
- size: `199`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180008490`
- `0x180010fac`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall BinaryOperationOnTwoSameOperandTypeExpressionTemplate<RelationalOrEqualityZeroNodeSetExpression<String>,BooleanExpressionBase,String>::Evaluate(
        __int64 a1,
        __int64 a2,
        _BYTE *a3)
{
  __int64 v4; // rcx
  int v7; // ebx
  __int64 (__fastcall *v8)(__int64 *, __int64 *); // r8
  __int64 v10; // [rsp+20h] [rbp-10h] BYREF
  __int64 v11; // [rsp+28h] [rbp-8h] BYREF
  __int64 v12; // [rsp+50h] [rbp+20h] BYREF
  __int64 v13; // [rsp+68h] [rbp+38h] BYREF

  v13 = 0;
  v4 = *(_QWORD *)(a1 + 24);
  v12 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v4 + 64LL))(v4, a2, &v13);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**(_QWORD **)(a1 + 32) + 64LL))(
           *(_QWORD *)(a1 + 32),
           a2,
           &v12);
    if ( v7 >= 0 )
    {
      v8 = *(__int64 (__fastcall **)(__int64 *, __int64 *))(a1 + 16);
      v10 = v12;
      if ( v12 )
        _InterlockedIncrement((volatile signed __int32 *)(v12 - 8));
      v11 = v13;
      if ( v13 )
        _InterlockedIncrement((volatile signed __int32 *)(v13 - 8));
      *a3 = v8(&v11, &v10);
      v7 = 0;
    }
  }
  String::Reset((String *)&v12);
  String::Reset((String *)&v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180008490  mov     [rsp-18h+arg_8], rbx
0x180008495  mov     [rsp-18h+arg_10], rsi
0x18000849a  push    rbp
0x18000849b  push    rdi
0x18000849c  push    r14
0x18000849e  mov     rbp, rsp
0x1800084a1  sub     rsp, 30h
0x1800084a5  mov     rdi, rcx
0x1800084a8  mov     [rbp+arg_18], 0
0x1800084b0  mov     rcx, [rcx+18h]
0x1800084b4  mov     r14, r8
0x1800084b7  mov     [rbp+arg_0], 0
0x1800084bf  lea     r8, [rbp+arg_18]
0x1800084c3  mov     rsi, rdx
0x1800084c6  mov     rax, [rcx]
0x1800084c9  mov     rax, [rax+40h]
0x1800084cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084d2  mov     ebx, eax
0x1800084d4  test    eax, eax
0x1800084d6  js      short loc_180008530
0x1800084d8  mov     rcx, [rdi+20h]
0x1800084dc  lea     r8, [rbp+arg_0]
0x1800084e0  mov     rdx, rsi
0x1800084e3  mov     rax, [rcx]
0x1800084e6  mov     rax, [rax+40h]
0x1800084ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084ef  mov     ebx, eax
0x1800084f1  test    eax, eax
0x1800084f3  js      short loc_180008530
0x1800084f5  mov     rax, [rbp+arg_0]
0x1800084f9  mov     r8, [rdi+10h]
0x1800084fd  mov     [rbp+var_10], rax
0x180008501  test    rax, rax
0x180008504  jz      short loc_18000850A
0x180008506  lock inc dword ptr [rax-8]
0x18000850a  mov     rcx, [rbp+arg_18]
0x18000850e  mov     [rbp+var_8], rcx
0x180008512  test    rcx, rcx
0x180008515  jz      short loc_18000851B
0x180008517  lock inc dword ptr [rcx-8]
0x18000851b  lea     rdx, [rbp+var_10]
0x18000851f  mov     rax, r8
0x180008522  lea     rcx, [rbp+var_8]
0x180008526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000852b  mov     [r14], al
0x18000852e  xor     ebx, ebx
0x180008530  lea     rcx, [rbp+arg_0]; this
0x180008534  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x180008539  lea     rcx, [rbp+arg_18]; this
0x18000853d  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x180008542  mov     rsi, [rsp+30h+arg_10]
0x180008547  mov     eax, ebx
0x180008549  mov     rbx, [rsp+30h+arg_8]
0x18000854e  add     rsp, 30h
0x180008552  pop     r14
0x180008554  pop     rdi
0x180008555  pop     rbp
0x180008556  retn
```
