# StartsWithFunctionExpression::Evaluate(XPathEvaluationContext *,bool &)

- ea: `0x18000bed0`
- end: `0x18000bfbc`
- name: `?Evaluate@StartsWithFunctionExpression@@UEAAJPEAVXPathEvaluationContext@@AEA_N@Z`
- size: `236`
- prototype: `__int64 __fastcall(StartsWithFunctionExpression *__hidden this, struct XPathEvaluationContext *, bool *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000bed0`
- `0x180010f98`
- `0x180010fac`
- `0x180011816`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall StartsWithFunctionExpression::Evaluate(
        StartsWithFunctionExpression *this,
        struct XPathEvaluationContext *a2,
        bool *a3)
{
  _QWORD *v3; // rax
  int v7; // ebx
  unsigned int CCH; // eax
  unsigned int v9; // edx
  bool v10; // al
  unsigned int v11; // eax
  const wchar_t *v12; // rdx
  const wchar_t *v13; // r9
  __int64 v15; // [rsp+40h] [rbp+20h] BYREF
  __int64 v16; // [rsp+58h] [rbp+38h] BYREF

  v3 = (_QWORD *)*((_QWORD *)this + 3);
  v16 = 0;
  v15 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, struct XPathEvaluationContext *, __int64 *))(*(_QWORD *)*v3 + 64LL))(
         *v3,
         a2,
         &v16);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, struct XPathEvaluationContext *, __int64 *))(**(_QWORD **)(*((_QWORD *)this + 3) + 8LL)
                                                                                       + 64LL))(
           *(_QWORD *)(*((_QWORD *)this + 3) + 8LL),
           a2,
           &v15);
    if ( v7 >= 0 )
    {
      String::QueryCCH((String *)&v15);
      CCH = String::QueryCCH((String *)&v16);
      if ( CCH >= v9 )
      {
        v11 = String::QueryCCH((String *)&v15);
        v10 = wcsncmp_0(v13, v12, v11) == 0;
      }
      else
      {
        v10 = 0;
      }
      *a3 = v10;
      v7 = 0;
    }
  }
  String::Reset((String *)&v15);
  String::Reset((String *)&v16);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000bed0  mov     [rsp-18h+arg_8], rbx
0x18000bed5  mov     [rsp-18h+arg_10], rsi
0x18000beda  push    rbp
0x18000bedb  push    rdi
0x18000bedc  push    r14
0x18000bede  mov     rbp, rsp
0x18000bee1  sub     rsp, 20h
0x18000bee5  mov     rax, [rcx+18h]
0x18000bee9  mov     r14, rcx
0x18000beec  mov     [rbp+arg_18], 0
0x18000bef4  mov     rdi, r8
0x18000bef7  mov     [rbp+arg_0], 0
0x18000beff  lea     r8, [rbp+arg_18]
0x18000bf03  mov     rsi, rdx
0x18000bf06  mov     rcx, [rax]
0x18000bf09  mov     rax, [rcx]
0x18000bf0c  mov     rax, [rax+40h]
0x18000bf10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf15  mov     ebx, eax
0x18000bf17  test    eax, eax
0x18000bf19  js      short loc_18000BF95
0x18000bf1b  mov     rax, [r14+18h]
0x18000bf1f  lea     r8, [rbp+arg_0]
0x18000bf23  mov     rdx, rsi
0x18000bf26  mov     rcx, [rax+8]
0x18000bf2a  mov     rax, [rcx]
0x18000bf2d  mov     rax, [rax+40h]
0x18000bf31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf36  mov     ebx, eax
0x18000bf38  test    eax, eax
0x18000bf3a  js      short loc_18000BF95
0x18000bf3c  lea     rcx, [rbp+arg_0]; this
0x18000bf40  call    ?QueryCCH@String@@QEBAKXZ; String::QueryCCH(void)
0x18000bf45  lea     rcx, [rbp+arg_18]; this
0x18000bf49  mov     edx, eax
0x18000bf4b  call    ?QueryCCH@String@@QEBAKXZ; String::QueryCCH(void)
0x18000bf50  cmp     eax, edx
0x18000bf52  jnb     short loc_18000BF58
0x18000bf54  xor     al, al
0x18000bf56  jmp     short loc_18000BF91
0x18000bf58  mov     rax, [rbp+arg_0]
0x18000bf5c  lea     r9, qword_180016F98
0x18000bf63  test    rax, rax
0x18000bf66  lea     rcx, [rbp+arg_0]; this
0x18000bf6a  mov     rdx, r9
0x18000bf6d  cmovnz  rdx, rax
0x18000bf71  mov     rax, [rbp+arg_18]
0x18000bf75  test    rax, rax
0x18000bf78  cmovnz  r9, rax
0x18000bf7c  call    ?QueryCCH@String@@QEBAKXZ; String::QueryCCH(void)
0x18000bf81  mov     r8d, eax; MaxCount
0x18000bf84  mov     rcx, r9; String1
0x18000bf87  call    wcsncmp_0
0x18000bf8c  test    eax, eax
0x18000bf8e  setz    al
0x18000bf91  mov     [rdi], al
0x18000bf93  xor     ebx, ebx
0x18000bf95  lea     rcx, [rbp+arg_0]; this
0x18000bf99  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000bf9e  lea     rcx, [rbp+arg_18]; this
0x18000bfa2  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000bfa7  mov     rsi, [rsp+20h+arg_10]
0x18000bfac  mov     eax, ebx
0x18000bfae  mov     rbx, [rsp+20h+arg_8]
0x18000bfb3  add     rsp, 20h
0x18000bfb7  pop     r14
0x18000bfb9  pop     rdi
0x18000bfba  pop     rbp
0x18000bfbb  retn
```
