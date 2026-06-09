# RelationalOrEqualityOneNodeSetExpression<double>::Evaluate(XPathEvaluationContext *,bool &)

- ea: `0x1800086b0`
- end: `0x1800087b0`
- name: `?Evaluate@?$RelationalOrEqualityOneNodeSetExpression@N@@UEAAJPEAVXPathEvaluationContext@@AEA_N@Z`
- size: `256`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800086b0`
- `0x18000a894`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall RelationalOrEqualityOneNodeSetExpression<double>::Evaluate(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 result; // rax
  __int64 v7; // rcx
  struct XPathNavigatorInternal *v8; // rax
  char v9; // al
  double v10; // [rsp+40h] [rbp+8h] BYREF
  __int64 v11; // [rsp+58h] [rbp+20h] BYREF

  result = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 96LL))(*(_QWORD *)(a1 + 32));
  if ( (int)result >= 0 )
  {
    *a3 = 0;
    for ( result = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 48LL))(*(_QWORD *)(a1 + 32));
          (_DWORD)result != 1;
          result = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 48LL))(*(_QWORD *)(a1 + 32)) )
    {
      if ( (int)result < 0 )
        return result;
      v7 = *(_QWORD *)(a1 + 40);
      v11 = 0;
      v10 = 0.0;
      result = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v7 + 72LL))(v7, a2, &v11);
      if ( (int)result < 0 )
        return result;
      v8 = (struct XPathNavigatorInternal *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 72LL))(*(_QWORD *)(a1 + 32));
      result = ConversionFunctions::ConvertFromNavigatorValue(v8, &v10);
      if ( (int)result < 0 )
        return result;
      v9 = (*(__int64 (**)(void))(a1 + 24))();
      *a3 = v9;
      if ( v9 )
        break;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800086b0  mov     [rsp+arg_8], rbx
0x1800086b5  mov     [rsp+arg_10], rsi
0x1800086ba  push    rdi
0x1800086bb  sub     rsp, 30h
0x1800086bf  mov     rbx, rcx
0x1800086c2  movaps  [rsp+38h+var_18], xmm6
0x1800086c7  mov     rcx, [rcx+20h]
0x1800086cb  mov     rdi, r8
0x1800086ce  mov     rsi, rdx
0x1800086d1  mov     rax, [rcx]
0x1800086d4  mov     rax, [rax+60h]
0x1800086d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086dd  test    eax, eax
0x1800086df  js      loc_18000879B
0x1800086e5  mov     byte ptr [rdi], 0
0x1800086e8  mov     rcx, [rbx+20h]
0x1800086ec  mov     rax, [rcx]
0x1800086ef  mov     rax, [rax+30h]
0x1800086f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086f8  xorps   xmm6, xmm6
0x1800086fb  cmp     eax, 1
0x1800086fe  jz      loc_180008799
0x180008704  test    eax, eax
0x180008706  js      loc_18000879B
0x18000870c  mov     rcx, [rbx+28h]
0x180008710  lea     r8, [rsp+38h+arg_18]
0x180008715  movsd   [rsp+38h+arg_18], xmm6
0x18000871b  mov     rdx, rsi
0x18000871e  movsd   [rsp+38h+arg_0], xmm6
0x180008724  mov     rax, [rcx]
0x180008727  mov     rax, [rax+48h]
0x18000872b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008730  test    eax, eax
0x180008732  js      short loc_18000879B
0x180008734  mov     rcx, [rbx+20h]
0x180008738  mov     rax, [rcx]
0x18000873b  mov     rax, [rax+48h]
0x18000873f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008744  mov     rcx, rax; struct XPathNavigatorInternal *
0x180008747  lea     rdx, [rsp+38h+arg_0]; double *
0x18000874c  call    ?ConvertFromNavigatorValue@ConversionFunctions@@SAJAEAVXPathNavigatorInternal@@AEAN@Z; ConversionFunctions::ConvertFromNavigatorValue(XPathNavigatorInternal &,double &)
0x180008751  test    eax, eax
0x180008753  js      short loc_18000879B
0x180008755  cmp     byte ptr [rbx+10h], 0
0x180008759  mov     rax, [rbx+18h]
0x18000875d  jz      short loc_18000876D
0x18000875f  movsd   xmm1, [rsp+38h+arg_18]
0x180008765  movsd   xmm0, [rsp+38h+arg_0]
0x18000876b  jmp     short loc_180008779
0x18000876d  movsd   xmm1, [rsp+38h+arg_0]
0x180008773  movsd   xmm0, [rsp+38h+arg_18]
0x180008779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000877e  mov     [rdi], al
0x180008780  test    al, al
0x180008782  jnz     short loc_180008799
0x180008784  mov     rcx, [rbx+20h]
0x180008788  mov     rax, [rcx]
0x18000878b  mov     rax, [rax+30h]
0x18000878f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008794  jmp     loc_1800086FB
0x180008799  xor     eax, eax
0x18000879b  mov     rbx, [rsp+38h+arg_8]
0x1800087a0  mov     rsi, [rsp+38h+arg_10]
0x1800087a5  movaps  xmm6, [rsp+38h+var_18]
0x1800087aa  add     rsp, 30h
0x1800087ae  pop     rdi
0x1800087af  retn
```
