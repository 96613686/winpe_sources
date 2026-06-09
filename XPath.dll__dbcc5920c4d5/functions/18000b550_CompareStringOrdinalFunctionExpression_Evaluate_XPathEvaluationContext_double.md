# CompareStringOrdinalFunctionExpression::Evaluate(XPathEvaluationContext *,double &)

- ea: `0x18000b550`
- end: `0x18000b67f`
- name: `?Evaluate@CompareStringOrdinalFunctionExpression@@UEAAJPEAVXPathEvaluationContext@@AEAN@Z`
- size: `303`
- prototype: `__int64 __fastcall(CompareStringOrdinalFunctionExpression *__hidden this, struct XPathEvaluationContext *, double *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000b550`
- `0x180010fac`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b61d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b61d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b613`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b613`

## pseudocode

```c
__int64 __fastcall CompareStringOrdinalFunctionExpression::Evaluate(
        CompareStringOrdinalFunctionExpression *this,
        struct XPathEvaluationContext *a2,
        double *a3)
{
  _QWORD *v3; // rax
  signed int v7; // ebx
  const WCHAR *v8; // rcx
  const WCHAR *v9; // r8
  int v10; // eax
  signed int LastError; // eax
  LPCWCH lpString1[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int8 v14; // [rsp+60h] [rbp+20h] BYREF
  LPCWCH lpString2; // [rsp+78h] [rbp+38h] BYREF

  v3 = (_QWORD *)*((_QWORD *)this + 3);
  lpString1[0] = 0;
  lpString2 = 0;
  v14 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, struct XPathEvaluationContext *, LPCWCH *))(*(_QWORD *)*v3 + 64LL))(
         *v3,
         a2,
         lpString1);
  if ( v7 < 0 )
    goto LABEL_11;
  v7 = (*(__int64 (__fastcall **)(_QWORD, struct XPathEvaluationContext *, LPCWCH *))(**(_QWORD **)(*((_QWORD *)this + 3)
                                                                                                  + 8LL)
                                                                                    + 64LL))(
         *(_QWORD *)(*((_QWORD *)this + 3) + 8LL),
         a2,
         &lpString2);
  if ( v7 < 0 )
    goto LABEL_11;
  v7 = (*(__int64 (__fastcall **)(_QWORD, struct XPathEvaluationContext *, unsigned __int8 *))(**(_QWORD **)(*((_QWORD *)this + 3) + 16LL)
                                                                                             + 80LL))(
         *(_QWORD *)(*((_QWORD *)this + 3) + 16LL),
         a2,
         &v14);
  if ( v7 < 0 )
    goto LABEL_11;
  v8 = &qword_180016F98;
  v9 = &qword_180016F98;
  if ( lpString2 )
    v9 = lpString2;
  if ( lpString1[0] )
    v8 = lpString1[0];
  v10 = CompareStringOrdinal(v8, -1, v9, -1, v14);
  if ( !v10 )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
LABEL_11:
    String::Reset((String *)&lpString2);
    String::Reset((String *)lpString1);
    return (unsigned int)v7;
  }
  *a3 = (double)(v10 - 2);
  String::Reset((String *)&lpString2);
  String::Reset((String *)lpString1);
  return 0;
}

```

## disassembly

```asm
0x18000b550  mov     [rsp-18h+arg_8], rbx
0x18000b555  mov     [rsp-18h+arg_10], rsi
0x18000b55a  push    rbp
0x18000b55b  push    rdi
0x18000b55c  push    r14
0x18000b55e  mov     rbp, rsp
0x18000b561  sub     rsp, 40h
0x18000b565  mov     rax, [rcx+18h]
0x18000b569  mov     rsi, rcx
0x18000b56c  mov     [rbp+lpString1], 0
0x18000b574  mov     r14, r8
0x18000b577  mov     [rbp+lpString2], 0
0x18000b57f  lea     r8, [rbp+lpString1]
0x18000b583  mov     [rbp+arg_0], 0
0x18000b587  mov     rdi, rdx
0x18000b58a  mov     rcx, [rax]
0x18000b58d  mov     rax, [rcx]
0x18000b590  mov     rax, [rax+40h]
0x18000b594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b599  mov     ebx, eax
0x18000b59b  test    eax, eax
0x18000b59d  js      loc_18000B632
0x18000b5a3  mov     rax, [rsi+18h]
0x18000b5a7  lea     r8, [rbp+lpString2]
0x18000b5ab  mov     rdx, rdi
0x18000b5ae  mov     rcx, [rax+8]
0x18000b5b2  mov     rax, [rcx]
0x18000b5b5  mov     rax, [rax+40h]
0x18000b5b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5be  mov     ebx, eax
0x18000b5c0  test    eax, eax
0x18000b5c2  js      short loc_18000B632
0x18000b5c4  mov     rax, [rsi+18h]
0x18000b5c8  lea     r8, [rbp+arg_0]
0x18000b5cc  mov     rdx, rdi
0x18000b5cf  mov     rcx, [rax+10h]
0x18000b5d3  mov     rax, [rcx]
0x18000b5d6  mov     rax, [rax+50h]
0x18000b5da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5df  mov     ebx, eax
0x18000b5e1  test    eax, eax
0x18000b5e3  js      short loc_18000B632
0x18000b5e5  mov     rax, [rbp+lpString2]
0x18000b5e9  lea     rcx, qword_180016F98
0x18000b5f0  movzx   edx, [rbp+arg_0]
0x18000b5f4  test    rax, rax
0x18000b5f7  mov     r8, rcx
0x18000b5fa  mov     [rsp+40h+bIgnoreCase], edx; bIgnoreCase
0x18000b5fe  cmovnz  r8, rax; lpString2
0x18000b602  mov     rax, [rbp+lpString1]
0x18000b606  test    rax, rax
0x18000b609  cmovnz  rcx, rax; lpString1
0x18000b60d  or      edx, 0FFFFFFFFh; cchCount1
0x18000b610  mov     r9d, edx; cchCount2
0x18000b613  call    cs:__imp_CompareStringOrdinal
0x18000b619  test    eax, eax
0x18000b61b  jnz     short loc_18000B659
0x18000b61d  call    cs:__imp_GetLastError
0x18000b623  mov     ebx, eax
0x18000b625  test    eax, eax
0x18000b627  jle     short loc_18000B632
0x18000b629  movzx   ebx, ax
0x18000b62c  or      ebx, 80070000h
0x18000b632  lea     rcx, [rbp+lpString2]; this
0x18000b636  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000b63b  lea     rcx, [rbp+lpString1]; this
0x18000b63f  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000b644  mov     eax, ebx
0x18000b646  mov     rbx, [rsp+40h+arg_8]
0x18000b64b  mov     rsi, [rsp+40h+arg_10]
0x18000b650  add     rsp, 40h
0x18000b654  pop     r14
0x18000b656  pop     rdi
0x18000b657  pop     rbp
0x18000b658  retn
0x18000b659  add     eax, 0FFFFFFFEh
0x18000b65c  lea     rcx, [rbp+lpString2]; this
0x18000b660  movd    xmm0, eax
0x18000b664  cvtdq2pd xmm0, xmm0
0x18000b668  movsd   qword ptr [r14], xmm0
0x18000b66d  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000b672  lea     rcx, [rbp+lpString1]; this
0x18000b676  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000b67b  xor     eax, eax
0x18000b67d  jmp     short loc_18000B646
```
