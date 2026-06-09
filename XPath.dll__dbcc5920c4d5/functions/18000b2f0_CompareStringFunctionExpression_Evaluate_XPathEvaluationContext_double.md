# CompareStringFunctionExpression::Evaluate(XPathEvaluationContext *,double &)

- ea: `0x18000b2f0`
- end: `0x18000b53e`
- name: `?Evaluate@CompareStringFunctionExpression@@UEAAJPEAVXPathEvaluationContext@@AEAN@Z`
- size: `590`
- prototype: `__int64 __fastcall(CompareStringFunctionExpression *__hidden this, struct XPathEvaluationContext *, double *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800083b4`
- `0x18000b2f0`
- `0x180010fac`
- `0x180011840`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b4f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b4f0`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000b4e6`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000b4e6`

## pseudocode

```c
__int64 __fastcall CompareStringFunctionExpression::Evaluate(
        CompareStringFunctionExpression *this,
        struct XPathEvaluationContext *a2,
        double *a3)
{
  __int64 *v3; // rax
  __int64 v6; // rcx
  int v7; // ebx
  unsigned int v8; // edi
  DWORD v9; // r12d
  __int64 v10; // rax
  unsigned __int16 i; // bx
  __int64 v12; // rsi
  const WCHAR *v14; // rcx
  const WCHAR *lpString2; // r10
  const WCHAR *v16; // r8
  int v17; // eax
  signed int LastError; // eax
  LPCWSTR lpLocaleName; // [rsp+50h] [rbp-19h] BYREF
  LPCWCH v20; // [rsp+58h] [rbp-11h] BYREF
  LPCWCH lpString1; // [rsp+60h] [rbp-9h] BYREF
  const WCHAR *v22; // [rsp+68h] [rbp-1h] BYREF
  double *v23; // [rsp+70h] [rbp+7h]
  __int64 v24; // [rsp+78h] [rbp+Fh]
  char v25; // [rsp+80h] [rbp+17h]

  v3 = (__int64 *)*((_QWORD *)this + 3);
  lpString1 = 0;
  v20 = 0;
  lpLocaleName = 0;
  v6 = *v3;
  v23 = a3;
  v7 = (*(__int64 (__fastcall **)(__int64, struct XPathEvaluationContext *, LPCWCH *))(*(_QWORD *)v6 + 64LL))(
         v6,
         a2,
         &lpString1);
  if ( v7 < 0
    || (v7 = (*(__int64 (__fastcall **)(_QWORD, struct XPathEvaluationContext *, LPCWCH *))(**(_QWORD **)(*((_QWORD *)this + 3) + 8LL)
                                                                                          + 64LL))(
               *(_QWORD *)(*((_QWORD *)this + 3) + 8LL),
               a2,
               &v20),
        v7 < 0)
    || (v7 = (*(__int64 (__fastcall **)(_QWORD, struct XPathEvaluationContext *, LPCWSTR *))(**(_QWORD **)(*((_QWORD *)this + 3) + 16LL)
                                                                                           + 64LL))(
               *(_QWORD *)(*((_QWORD *)this + 3) + 16LL),
               a2,
               &lpLocaleName),
        v7 < 0) )
  {
LABEL_15:
    String::Reset((String *)&lpLocaleName);
    String::Reset((String *)&v20);
    String::Reset((String *)&lpString1);
    return (unsigned int)v7;
  }
  v8 = 3;
  v24 = 0;
  v9 = 0;
  v25 = 0;
LABEL_5:
  if ( v8 < *((_DWORD *)this + 9) )
  {
    v10 = *((_QWORD *)this + 3);
    v22 = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD, struct XPathEvaluationContext *, const WCHAR **))(**(_QWORD **)(v10 + 8LL * v8)
                                                                                            + 64LL))(
           *(_QWORD *)(v10 + 8LL * v8),
           a2,
           &v22);
    if ( v7 >= 0 )
    {
      for ( i = 0; i < 9u; ++i )
      {
        v12 = 16LL * (__int16)i;
        if ( WideCharStringTemplate<String>::Equals(
               &v22,
               *(const WCHAR **)((char *)&CompareStringFunctionExpression::s_rgFlagMnemonic + v12)) )
        {
          if ( !*((_BYTE *)&v24 + (__int16)i) )
          {
            v9 |= *(_DWORD *)((char *)&CompareStringFunctionExpression::s_rgFlagMnemonic + v12 + 8);
            *((_BYTE *)&v24 + (__int16)i) = 1;
            String::Reset((String *)&v22);
            ++v8;
            goto LABEL_5;
          }
          break;
        }
      }
      v7 = -2147024809;
    }
    String::Reset((String *)&v22);
    goto LABEL_15;
  }
  v14 = &qword_180016F98;
  lpString2 = &qword_180016F98;
  if ( v20 )
    lpString2 = v20;
  v16 = &qword_180016F98;
  if ( lpString1 )
    v16 = lpString1;
  if ( lpLocaleName )
    v14 = lpLocaleName;
  v17 = CompareStringEx(v14, v9, v16, -1, lpString2, -1, 0, 0, 0);
  if ( !v17 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = LastError;
    goto LABEL_15;
  }
  *v23 = (double)(v17 - 2);
  String::Reset((String *)&lpLocaleName);
  String::Reset((String *)&v20);
  String::Reset((String *)&lpString1);
  return 0;
}

```

## disassembly

```asm
0x18000b2f0  mov     [rsp-8+arg_18], rbx
0x18000b2f5  push    rbp
0x18000b2f6  push    rsi
0x18000b2f7  push    rdi
0x18000b2f8  push    r12
0x18000b2fa  push    r13
0x18000b2fc  push    r14
0x18000b2fe  push    r15
0x18000b300  lea     rbp, [rsp-27h]
0x18000b305  sub     rsp, 90h
0x18000b30c  mov     rax, cs:__security_cookie
0x18000b313  xor     rax, rsp
0x18000b316  mov     [rbp+57h+var_38], rax
0x18000b31a  mov     rax, [rcx+18h]
0x18000b31e  xor     esi, esi
0x18000b320  mov     [rbp+57h+lpString1], rsi
0x18000b324  mov     r15, rcx
0x18000b327  mov     [rbp+57h+var_68], rsi
0x18000b32b  mov     r13, rdx
0x18000b32e  mov     [rbp+57h+lpLocaleName], rsi
0x18000b332  mov     rcx, [rax]
0x18000b335  mov     [rbp+57h+var_50], r8
0x18000b339  lea     r8, [rbp+57h+lpString1]
0x18000b33d  mov     rax, [rcx]
0x18000b340  mov     rax, [rax+40h]
0x18000b344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b349  mov     ebx, eax
0x18000b34b  test    eax, eax
0x18000b34d  js      loc_18000B453
0x18000b353  mov     rax, [r15+18h]
0x18000b357  lea     r8, [rbp+57h+var_68]
0x18000b35b  mov     rdx, r13
0x18000b35e  mov     rcx, [rax+8]
0x18000b362  mov     rax, [rcx]
0x18000b365  mov     rax, [rax+40h]
0x18000b369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b36e  mov     ebx, eax
0x18000b370  test    eax, eax
0x18000b372  js      loc_18000B453
0x18000b378  mov     rax, [r15+18h]
0x18000b37c  lea     r8, [rbp+57h+lpLocaleName]
0x18000b380  mov     rdx, r13
0x18000b383  mov     rcx, [rax+10h]
0x18000b387  mov     rax, [rcx]
0x18000b38a  mov     rax, [rax+40h]
0x18000b38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b393  mov     ebx, eax
0x18000b395  test    eax, eax
0x18000b397  js      loc_18000B453
0x18000b39d  xor     eax, eax
0x18000b39f  lea     edi, [rsi+3]
0x18000b3a2  mov     [rbp+57h+var_48], rax
0x18000b3a6  mov     r12d, esi
0x18000b3a9  mov     [rbp+57h+var_40], al
0x18000b3ac  cmp     edi, [r15+24h]
0x18000b3b0  jnb     loc_18000B497
0x18000b3b6  mov     rax, [r15+18h]
0x18000b3ba  lea     r8, [rbp+57h+var_58]
0x18000b3be  mov     [rbp+57h+var_58], rsi
0x18000b3c2  mov     rdx, r13
0x18000b3c5  mov     ecx, edi
0x18000b3c7  mov     rcx, [rax+rcx*8]
0x18000b3cb  mov     rax, [rcx]
0x18000b3ce  mov     rax, [rax+40h]
0x18000b3d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3d7  mov     ebx, eax
0x18000b3d9  test    eax, eax
0x18000b3db  js      short loc_18000B44A
0x18000b3dd  mov     ebx, esi
0x18000b3df  cmp     bx, 9
0x18000b3e3  jnb     short loc_18000B445
0x18000b3e5  lea     rax, ?s_rgFlagMnemonic@CompareStringFunctionExpression@@2QBUFlagMnemonicEntry@1@B; CompareStringFunctionExpression::FlagMnemonicEntry const near * const CompareStringFunctionExpression::s_rgFlagMnemonic
0x18000b3ec  movsx   r14, bx
0x18000b3f0  mov     rsi, r14
0x18000b3f3  lea     rcx, [rbp+57h+var_58]
0x18000b3f7  shl     rsi, 4
0x18000b3fb  mov     rdx, [rsi+rax]
0x18000b3ff  call    ?Equals@?$WideCharStringTemplate@VString@@@@QEBA_NPEBG@Z; WideCharStringTemplate<String>::Equals(ushort const *)
0x18000b404  test    al, al
0x18000b406  jnz     short loc_18000B40D
0x18000b408  inc     bx
0x18000b40b  jmp     short loc_18000B3DF
0x18000b40d  or      eax, 0FFFFFFFFh
0x18000b410  cmp     bx, ax
0x18000b413  jz      short loc_18000B445
0x18000b415  cmp     byte ptr [rbp+r14+57h+var_48], 0
0x18000b41b  jnz     short loc_18000B445
0x18000b41d  lea     rax, ?s_rgFlagMnemonic@CompareStringFunctionExpression@@2QBUFlagMnemonicEntry@1@B; CompareStringFunctionExpression::FlagMnemonicEntry const near * const CompareStringFunctionExpression::s_rgFlagMnemonic
0x18000b424  mov     ebx, 1
0x18000b429  or      r12d, [rsi+rax+8]
0x18000b42e  lea     rcx, [rbp+57h+var_58]; this
0x18000b432  mov     byte ptr [rbp+r14+57h+var_48], bl
0x18000b437  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000b43c  add     edi, ebx
0x18000b43e  xor     esi, esi
0x18000b440  jmp     loc_18000B3AC
0x18000b445  mov     ebx, 80070057h
0x18000b44a  lea     rcx, [rbp+57h+var_58]; this
0x18000b44e  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000b453  lea     rcx, [rbp+57h+lpLocaleName]; this
0x18000b457  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000b45c  lea     rcx, [rbp+57h+var_68]; this
0x18000b460  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000b465  lea     rcx, [rbp+57h+lpString1]; this
0x18000b469  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000b46e  mov     eax, ebx
0x18000b470  mov     rcx, [rbp+57h+var_38]
0x18000b474  xor     rcx, rsp; StackCookie
0x18000b477  call    __security_check_cookie
0x18000b47c  mov     rbx, [rsp+0C0h+arg_18]
0x18000b484  add     rsp, 90h
0x18000b48b  pop     r15
0x18000b48d  pop     r14
0x18000b48f  pop     r13
0x18000b491  pop     r12
0x18000b493  pop     rdi
0x18000b494  pop     rsi
0x18000b495  pop     rbp
0x18000b496  retn
0x18000b497  mov     rax, [rbp+57h+var_68]
0x18000b49b  lea     rcx, qword_180016F98
0x18000b4a2  test    rax, rax
0x18000b4a5  mov     [rsp+0C0h+lParam], rsi; lParam
0x18000b4aa  mov     r10, rcx
0x18000b4ad  mov     [rsp+0C0h+lpReserved], rsi; lpReserved
0x18000b4b2  cmovnz  r10, rax
0x18000b4b6  mov     [rsp+0C0h+lpVersionInformation], rsi; lpVersionInformation
0x18000b4bb  mov     rax, [rbp+57h+lpString1]
0x18000b4bf  mov     r8, rcx
0x18000b4c2  test    rax, rax
0x18000b4c5  cmovnz  r8, rax; lpString1
0x18000b4c9  mov     rax, [rbp+57h+lpLocaleName]
0x18000b4cd  test    rax, rax
0x18000b4d0  cmovnz  rcx, rax; lpLocaleName
0x18000b4d4  or      edx, 0FFFFFFFFh
0x18000b4d7  mov     [rsp+0C0h+cchCount2], edx; cchCount2
0x18000b4db  mov     r9d, edx; cchCount1
0x18000b4de  mov     edx, r12d; dwCmpFlags
0x18000b4e1  mov     [rsp+0C0h+lpString2], r10; lpString2
0x18000b4e6  call    cs:__imp_CompareStringEx
0x18000b4ec  test    eax, eax
0x18000b4ee  jnz     short loc_18000B509
0x18000b4f0  call    cs:__imp_GetLastError
0x18000b4f6  test    eax, eax
0x18000b4f8  jle     short loc_18000B502
0x18000b4fa  movzx   eax, ax
0x18000b4fd  or      eax, 80070000h
0x18000b502  mov     ebx, eax
0x18000b504  jmp     loc_18000B453
0x18000b509  add     eax, 0FFFFFFFEh
0x18000b50c  lea     rcx, [rbp+57h+lpLocaleName]; this
0x18000b510  movd    xmm0, eax
0x18000b514  mov     rax, [rbp+57h+var_50]
0x18000b518  cvtdq2pd xmm0, xmm0
0x18000b51c  movsd   qword ptr [rax], xmm0
0x18000b520  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000b525  lea     rcx, [rbp+57h+var_68]; this
0x18000b529  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000b52e  lea     rcx, [rbp+57h+lpString1]; this
0x18000b532  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000b537  xor     eax, eax
0x18000b539  jmp     loc_18000B470
```
