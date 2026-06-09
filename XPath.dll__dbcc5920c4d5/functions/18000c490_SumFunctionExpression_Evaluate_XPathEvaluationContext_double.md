# SumFunctionExpression::Evaluate(XPathEvaluationContext *,double &)

- ea: `0x18000c490`
- end: `0x18000c542`
- name: `?Evaluate@SumFunctionExpression@@UEAAJPEAVXPathEvaluationContext@@AEAN@Z`
- size: `178`
- prototype: `__int64 __fastcall(SumFunctionExpression *__hidden this, struct XPathEvaluationContext *, double *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000a894`
- `0x18000c490`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall SumFunctionExpression::Evaluate(
        SumFunctionExpression *this,
        struct XPathEvaluationContext *a2,
        double *a3)
{
  unsigned __int64 v4; // kr00_8
  __int64 *v5; // rbx
  __int64 result; // rax
  __int64 v7; // rax
  struct XPathNavigatorInternal *v8; // rax
  double v9; // [rsp+40h] [rbp+8h] BYREF

  v4 = **((_QWORD **)this + 3);
  v5 = (__int64 *)((v4 - 8) & ((unsigned __int128)-(__int128)v4 >> 64));
  result = (*(__int64 (__fastcall **)(__int64 *, struct XPathEvaluationContext *))(*v5 + 96))(v5, a2);
  if ( (int)result >= 0 )
  {
    *a3 = 0.0;
    for ( result = (*(__int64 (__fastcall **)(_QWORD))(*v5 + 48))((v4 - 8) & ((unsigned __int128)-(__int128)v4 >> 64));
          (_DWORD)result != 1;
          result = (*(__int64 (__fastcall **)(_QWORD))(*v5 + 48))((v4 - 8) & ((unsigned __int128)-(__int128)v4 >> 64)) )
    {
      if ( (int)result < 0 )
        return result;
      v7 = *v5;
      v9 = 0.0;
      v8 = (struct XPathNavigatorInternal *)(*(__int64 (__fastcall **)(_QWORD))(v7 + 72))((v4 - 8) & ((unsigned __int128)-(__int128)v4 >> 64));
      result = ConversionFunctions::ConvertFromNavigatorValue(v8, &v9);
      if ( (int)result < 0 )
        return result;
      *a3 = v9 + *a3;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000c490  mov     [rsp+arg_8], rbx
0x18000c495  push    rdi
0x18000c496  sub     rsp, 30h
0x18000c49a  mov     rax, [rcx+18h]
0x18000c49e  mov     rdi, r8
0x18000c4a1  movaps  [rsp+38h+var_18], xmm6
0x18000c4a6  mov     rcx, [rax]
0x18000c4a9  lea     rax, [rcx-8]
0x18000c4ad  neg     rcx
0x18000c4b0  sbb     rbx, rbx
0x18000c4b3  and     rbx, rax
0x18000c4b6  mov     rcx, rbx
0x18000c4b9  mov     rax, [rbx]
0x18000c4bc  mov     rax, [rax+60h]
0x18000c4c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4c5  test    eax, eax
0x18000c4c7  js      short loc_18000C532
0x18000c4c9  mov     qword ptr [rdi], 0
0x18000c4d0  mov     rcx, rbx
0x18000c4d3  mov     rax, [rbx]
0x18000c4d6  mov     rax, [rax+30h]
0x18000c4da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4df  xorps   xmm6, xmm6
0x18000c4e2  cmp     eax, 1
0x18000c4e5  jz      short loc_18000C530
0x18000c4e7  test    eax, eax
0x18000c4e9  js      short loc_18000C532
0x18000c4eb  mov     rax, [rbx]
0x18000c4ee  mov     rcx, rbx
0x18000c4f1  movsd   [rsp+38h+arg_0], xmm6
0x18000c4f7  mov     rax, [rax+48h]
0x18000c4fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c500  mov     rcx, rax; struct XPathNavigatorInternal *
0x18000c503  lea     rdx, [rsp+38h+arg_0]; double *
0x18000c508  call    ?ConvertFromNavigatorValue@ConversionFunctions@@SAJAEAVXPathNavigatorInternal@@AEAN@Z; ConversionFunctions::ConvertFromNavigatorValue(XPathNavigatorInternal &,double &)
0x18000c50d  test    eax, eax
0x18000c50f  js      short loc_18000C532
0x18000c511  movsd   xmm0, [rsp+38h+arg_0]
0x18000c517  mov     rcx, rbx
0x18000c51a  addsd   xmm0, qword ptr [rdi]
0x18000c51e  movsd   qword ptr [rdi], xmm0
0x18000c522  mov     rax, [rbx]
0x18000c525  mov     rax, [rax+30h]
0x18000c529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c52e  jmp     short loc_18000C4E2
0x18000c530  xor     eax, eax
0x18000c532  mov     rbx, [rsp+38h+arg_8]
0x18000c537  movaps  xmm6, [rsp+38h+var_18]
0x18000c53c  add     rsp, 30h
0x18000c540  pop     rdi
0x18000c541  retn
```
