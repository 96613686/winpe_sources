# RelationalOrEqualityOneNodeSetExpression<String>::Evaluate(XPathEvaluationContext *,bool &)

- ea: `0x1800087c0`
- end: `0x18000894a`
- name: `?Evaluate@?$RelationalOrEqualityOneNodeSetExpression@VString@@@@UEAAJPEAVXPathEvaluationContext@@AEA_N@Z`
- size: `394`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180007ee4`
- `0x1800087c0`
- `0x18000e594`
- `0x180010ee0`
- `0x180010fac`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall RelationalOrEqualityOneNodeSetExpression<String>::Evaluate(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 result; // rax
  __int64 v7; // rcx
  int v8; // eax
  XPathNavigatorInternal *v9; // rax
  int Value; // ebx
  unsigned __int16 **v11; // r8
  unsigned __int16 **v12; // rdx
  char v13; // al
  unsigned __int16 *v14; // [rsp+20h] [rbp-10h] BYREF
  __int64 v15; // [rsp+28h] [rbp-8h] BYREF
  __int64 v16; // [rsp+50h] [rbp+20h] BYREF
  unsigned __int16 *v17; // [rsp+68h] [rbp+38h] BYREF

  result = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 96LL))(*(_QWORD *)(a1 + 32));
  if ( (int)result >= 0 )
  {
    *a3 = 0;
    while ( 1 )
    {
      result = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 48LL))(*(_QWORD *)(a1 + 32));
      if ( (_DWORD)result == 1 )
        return 0;
      if ( (int)result < 0 )
        return result;
      v7 = *(_QWORD *)(a1 + 40);
      v17 = 0;
      v16 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 **))(*(_QWORD *)v7 + 64LL))(v7, a2, &v17);
      if ( v8 < 0 )
        break;
      v9 = (XPathNavigatorInternal *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 72LL))(*(_QWORD *)(a1 + 32));
      v14 = 0;
      Value = XPathNavigatorInternal::GetValue(v9, (const unsigned __int16 **)&v14);
      if ( Value < 0 )
        goto LABEL_25;
      Value = String::Initialize((String *)&v16, v14);
      if ( Value < 0 )
        goto LABEL_25;
      if ( *(_BYTE *)(a1 + 16) )
      {
        v14 = v17;
        if ( v17 )
          _InterlockedIncrement((volatile signed __int32 *)v17 - 2);
        v15 = v16;
        if ( v16 )
          _InterlockedIncrement((volatile signed __int32 *)(v16 - 8));
        v11 = &v14;
        v12 = (unsigned __int16 **)&v15;
      }
      else
      {
        v15 = v16;
        if ( v16 )
          _InterlockedIncrement((volatile signed __int32 *)(v16 - 8));
        v14 = v17;
        if ( v17 )
          _InterlockedIncrement((volatile signed __int32 *)v17 - 2);
        v11 = (unsigned __int16 **)&v15;
        v12 = &v14;
      }
      v13 = RelationalOrEqualityOneNodeSetOperandExpressionBase<RelationalOrEqualityOneNodeSetExpression<String>,String>::ApplyOperatorFunc(
              a1,
              v12,
              v11);
      *a3 = v13;
      if ( v13 )
      {
        String::Reset((String *)&v16);
        String::Reset((String *)&v17);
        return 0;
      }
      String::Reset((String *)&v16);
      String::Reset((String *)&v17);
    }
    Value = v8;
LABEL_25:
    String::Reset((String *)&v16);
    String::Reset((String *)&v17);
    return (unsigned int)Value;
  }
  return result;
}

```

## disassembly

```asm
0x1800087c0  mov     [rsp-18h+arg_8], rbx
0x1800087c5  mov     [rsp-18h+arg_10], rsi
0x1800087ca  push    rbp
0x1800087cb  push    rdi
0x1800087cc  push    r14
0x1800087ce  mov     rbp, rsp
0x1800087d1  sub     rsp, 30h
0x1800087d5  mov     rdi, rcx
0x1800087d8  mov     rsi, r8
0x1800087db  mov     rcx, [rcx+20h]
0x1800087df  mov     r14, rdx
0x1800087e2  mov     rax, [rcx]
0x1800087e5  mov     rax, [rax+60h]
0x1800087e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087ee  test    eax, eax
0x1800087f0  js      loc_18000891F
0x1800087f6  mov     byte ptr [rsi], 0
0x1800087f9  mov     rcx, [rdi+20h]
0x1800087fd  mov     rax, [rcx]
0x180008800  mov     rax, [rax+30h]
0x180008804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008809  cmp     eax, 1
0x18000880c  jz      loc_18000891D
0x180008812  test    eax, eax
0x180008814  js      loc_18000891F
0x18000881a  mov     rcx, [rdi+28h]
0x18000881e  lea     r8, [rbp+arg_18]
0x180008822  mov     [rbp+arg_18], 0
0x18000882a  mov     rdx, r14
0x18000882d  mov     [rbp+arg_0], 0
0x180008835  mov     rax, [rcx]
0x180008838  mov     rax, [rax+40h]
0x18000883c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008841  test    eax, eax
0x180008843  js      loc_180008932
0x180008849  mov     rcx, [rdi+20h]
0x18000884d  mov     rax, [rcx]
0x180008850  mov     rax, [rax+48h]
0x180008854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008859  lea     rdx, [rbp+var_10]; unsigned __int16 **
0x18000885d  mov     [rbp+var_10], 0
0x180008865  mov     rcx, rax; this
0x180008868  call    ?GetValue@XPathNavigatorInternal@@QEAAJPEAPEBG@Z; XPathNavigatorInternal::GetValue(ushort const * *)
0x18000886d  mov     ebx, eax
0x18000886f  test    eax, eax
0x180008871  js      loc_180008934
0x180008877  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x18000887b  lea     rcx, [rbp+arg_0]; this
0x18000887f  call    ?Initialize@String@@QEAAJPEBG@Z; String::Initialize(ushort const *)
0x180008884  mov     ebx, eax
0x180008886  test    eax, eax
0x180008888  js      loc_180008934
0x18000888e  cmp     byte ptr [rdi+10h], 0
0x180008892  jz      short loc_1800088C0
0x180008894  mov     rax, [rbp+arg_18]
0x180008898  mov     [rbp+var_10], rax
0x18000889c  test    rax, rax
0x18000889f  jz      short loc_1800088A5
0x1800088a1  lock inc dword ptr [rax-8]
0x1800088a5  mov     rax, [rbp+arg_0]
0x1800088a9  mov     [rbp+var_8], rax
0x1800088ad  test    rax, rax
0x1800088b0  jz      short loc_1800088B6
0x1800088b2  lock inc dword ptr [rax-8]
0x1800088b6  lea     r8, [rbp+var_10]
0x1800088ba  lea     rdx, [rbp+var_8]
0x1800088be  jmp     short loc_1800088EA
0x1800088c0  mov     rax, [rbp+arg_0]
0x1800088c4  mov     [rbp+var_8], rax
0x1800088c8  test    rax, rax
0x1800088cb  jz      short loc_1800088D1
0x1800088cd  lock inc dword ptr [rax-8]
0x1800088d1  mov     rax, [rbp+arg_18]
0x1800088d5  mov     [rbp+var_10], rax
0x1800088d9  test    rax, rax
0x1800088dc  jz      short loc_1800088E2
0x1800088de  lock inc dword ptr [rax-8]
0x1800088e2  lea     r8, [rbp+var_8]
0x1800088e6  lea     rdx, [rbp+var_10]
0x1800088ea  mov     rcx, rdi
0x1800088ed  call    ?ApplyOperatorFunc@?$RelationalOrEqualityOneNodeSetOperandExpressionBase@V?$RelationalOrEqualityOneNodeSetExpression@VString@@@@VString@@@@IEAA_NVString@@0@Z; RelationalOrEqualityOneNodeSetOperandExpressionBase<RelationalOrEqualityOneNodeSetExpression<String>,String>::ApplyOperatorFunc(String,String)
0x1800088f2  mov     [rsi], al
0x1800088f4  lea     rcx, [rbp+arg_0]; this
0x1800088f8  test    al, al
0x1800088fa  jnz     short loc_18000890F
0x1800088fc  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x180008901  lea     rcx, [rbp+arg_18]; this
0x180008905  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000890a  jmp     loc_1800087F9
0x18000890f  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x180008914  lea     rcx, [rbp+arg_18]; this
0x180008918  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000891d  xor     eax, eax
0x18000891f  mov     rbx, [rsp+30h+arg_8]
0x180008924  mov     rsi, [rsp+30h+arg_10]
0x180008929  add     rsp, 30h
0x18000892d  pop     r14
0x18000892f  pop     rdi
0x180008930  pop     rbp
0x180008931  retn
0x180008932  mov     ebx, eax
0x180008934  lea     rcx, [rbp+arg_0]; this
0x180008938  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000893d  lea     rcx, [rbp+arg_18]; this
0x180008941  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x180008946  mov     eax, ebx
0x180008948  jmp     short loc_18000891F
```
