# BinaryOperationOnTwoSameOperandTypeExpressionTemplate<RelationalOrEqualityZeroNodeSetExpression<double>,BooleanExpressionBase,double>::Evaluate(XPathEvaluationContext *,bool &)

- ea: `0x180008400`
- end: `0x180008484`
- name: `?Evaluate@?$BinaryOperationOnTwoSameOperandTypeExpressionTemplate@V?$RelationalOrEqualityZeroNodeSetExpression@N@@VBooleanExpressionBase@@N@@UEAAJPEAVXPathEvaluationContext@@AEA_N@Z`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180008400`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall BinaryOperationOnTwoSameOperandTypeExpressionTemplate<RelationalOrEqualityZeroNodeSetExpression<double>,BooleanExpressionBase,double>::Evaluate(
        __int64 a1,
        __int64 a2,
        _BYTE *a3)
{
  __int64 v4; // rcx
  __int64 result; // rax
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF
  __int64 v9; // [rsp+48h] [rbp+20h] BYREF

  v4 = *(_QWORD *)(a1 + 24);
  v9 = 0;
  v8 = 0;
  result = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v4 + 72LL))(v4, a2, &v9);
  if ( (int)result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**(_QWORD **)(a1 + 32) + 72LL))(
               *(_QWORD *)(a1 + 32),
               a2,
               &v8);
    if ( (int)result >= 0 )
    {
      *a3 = (*(__int64 (**)(void))(a1 + 16))();
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008400  mov     rax, rsp
0x180008403  mov     [rax+10h], rbx
0x180008407  mov     [rax+18h], rsi
0x18000840b  push    rdi
0x18000840c  sub     rsp, 20h
0x180008410  xorps   xmm0, xmm0
0x180008413  mov     rbx, rcx
0x180008416  mov     rcx, [rcx+18h]
0x18000841a  mov     rsi, r8
0x18000841d  movsd   qword ptr [rax+20h], xmm0
0x180008422  lea     r8, [rsp+28h+arg_18]
0x180008427  movsd   qword ptr [rax+8], xmm0
0x18000842c  mov     rdi, rdx
0x18000842f  mov     rax, [rcx]
0x180008432  mov     rax, [rax+48h]
0x180008436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000843b  test    eax, eax
0x18000843d  js      short loc_180008474
0x18000843f  mov     rcx, [rbx+20h]
0x180008443  lea     r8, [rsp+28h+arg_0]
0x180008448  mov     rdx, rdi
0x18000844b  mov     rax, [rcx]
0x18000844e  mov     rax, [rax+48h]
0x180008452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008457  test    eax, eax
0x180008459  js      short loc_180008474
0x18000845b  movsd   xmm1, [rsp+28h+arg_0]
0x180008461  movsd   xmm0, [rsp+28h+arg_18]
0x180008467  mov     rax, [rbx+10h]
0x18000846b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008470  mov     [rsi], al
0x180008472  xor     eax, eax
0x180008474  mov     rbx, [rsp+28h+arg_8]
0x180008479  mov     rsi, [rsp+28h+arg_10]
0x18000847e  add     rsp, 20h
0x180008482  pop     rdi
0x180008483  retn
```
