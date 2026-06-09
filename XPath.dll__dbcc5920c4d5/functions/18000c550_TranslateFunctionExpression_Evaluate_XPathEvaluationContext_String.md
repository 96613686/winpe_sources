# TranslateFunctionExpression::Evaluate(XPathEvaluationContext *,String &)

- ea: `0x18000c550`
- end: `0x18000c739`
- name: `?Evaluate@TranslateFunctionExpression@@UEAAJPEAVXPathEvaluationContext@@AEAVString@@@Z`
- size: `489`
- prototype: `__int64 __fastcall(TranslateFunctionExpression *this, struct XPathEvaluationContext *, struct String *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000a640`
- `0x18000a690`
- `0x18000c550`
- `0x180010ee0`
- `0x180010f98`
- `0x180010fac`
- `0x180011840`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall TranslateFunctionExpression::Evaluate(
        TranslateFunctionExpression *this,
        struct XPathEvaluationContext *a2,
        struct String *a3)
{
  _QWORD *v3; // rax
  int v7; // ebx
  __int64 v8; // rbx
  unsigned int CCH; // eax
  const unsigned __int16 *v10; // r8
  __int64 v11; // r9
  const unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // rcx
  unsigned int v14; // eax
  const unsigned __int16 *v15; // rcx
  const unsigned __int16 *v16; // rdx
  int v17; // edi
  __int64 v19; // [rsp+20h] [rbp-40h] BYREF
  const unsigned __int16 *v20; // [rsp+28h] [rbp-38h] BYREF
  const unsigned __int16 *v21; // [rsp+30h] [rbp-30h] BYREF
  __int16 v22; // [rsp+38h] [rbp-28h] BYREF
  char v23; // [rsp+3Ah] [rbp-26h]
  int v24; // [rsp+3Ch] [rbp-24h]
  unsigned __int16 *v25; // [rsp+40h] [rbp-20h]
  int v26; // [rsp+48h] [rbp-18h]

  v3 = (_QWORD *)*((_QWORD *)this + 3);
  v19 = 0;
  v21 = 0;
  v20 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, struct XPathEvaluationContext *, __int64 *))(*(_QWORD *)*v3 + 64LL))(
         *v3,
         a2,
         &v19);
  if ( v7 < 0 )
    goto LABEL_23;
  v7 = (*(__int64 (__fastcall **)(_QWORD, struct XPathEvaluationContext *, const unsigned __int16 **))(**(_QWORD **)(*((_QWORD *)this + 3) + 8LL) + 64LL))(
         *(_QWORD *)(*((_QWORD *)this + 3) + 8LL),
         a2,
         &v21);
  if ( v7 < 0 )
    goto LABEL_23;
  v7 = (*(__int64 (__fastcall **)(_QWORD, struct XPathEvaluationContext *, const unsigned __int16 **))(**(_QWORD **)(*((_QWORD *)this + 3) + 16LL) + 64LL))(
         *(_QWORD *)(*((_QWORD *)this + 3) + 16LL),
         a2,
         &v20);
  if ( v7 < 0 )
    goto LABEL_23;
  v25 = (unsigned __int16 *)&v22;
  v23 = 0;
  v8 = 0;
  v24 = 2;
  v26 = 0;
  v22 = 0;
  while ( 2 )
  {
    if ( (unsigned int)v8 >= String::QueryCCH((String *)&v19) )
    {
      v7 = String::Initialize(a3, v25);
      BUFFER::~BUFFER((BUFFER *)&v22);
LABEL_23:
      String::Reset((String *)&v20);
      String::Reset((String *)&v21);
      String::Reset((String *)&v19);
      return (unsigned int)v7;
    }
    while ( 1 )
    {
      CCH = String::QueryCCH((String *)&v21);
      if ( (unsigned int)v11 >= CCH )
        break;
      v12 = &qword_180016F98;
      v13 = &qword_180016F98;
      if ( v10 )
        v12 = v10;
      if ( v21 )
        v13 = v21;
      if ( v12[v8] == v13[v11] )
      {
        v14 = String::QueryCCH((String *)&v20);
        if ( (unsigned int)v11 < v14 )
        {
          v15 = &qword_180016F98;
          if ( v20 )
            v15 = v20;
          v16 = &v15[v11];
          goto LABEL_19;
        }
        goto LABEL_20;
      }
    }
    if ( !v10 )
      v10 = &qword_180016F98;
    v16 = &v10[v8];
LABEL_19:
    v17 = STRU::Append((STRU *)&v22, v16, 1u, v11);
    if ( v17 >= 0 )
    {
LABEL_20:
      v8 = (unsigned int)(v8 + 1);
      continue;
    }
    break;
  }
  BUFFER::~BUFFER((BUFFER *)&v22);
  String::Reset((String *)&v20);
  String::Reset((String *)&v21);
  String::Reset((String *)&v19);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18000c550  push    rbp
0x18000c552  push    rbx
0x18000c553  push    rsi
0x18000c554  push    rdi
0x18000c555  push    r14
0x18000c557  mov     rbp, rsp
0x18000c55a  sub     rsp, 60h
0x18000c55e  mov     rax, cs:__security_cookie
0x18000c565  xor     rax, rsp
0x18000c568  mov     [rbp+var_10], rax
0x18000c56c  mov     rax, [rcx+18h]
0x18000c570  mov     rdi, rcx
0x18000c573  mov     [rbp+var_40], 0
0x18000c57b  mov     r14, r8
0x18000c57e  mov     [rbp+var_30], 0
0x18000c586  lea     r8, [rbp+var_40]
0x18000c58a  mov     [rbp+var_38], 0
0x18000c592  mov     rsi, rdx
0x18000c595  mov     rcx, [rax]
0x18000c598  mov     rax, [rcx]
0x18000c59b  mov     rax, [rax+40h]
0x18000c59f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5a4  mov     ebx, eax
0x18000c5a6  test    eax, eax
0x18000c5a8  js      loc_18000C705
0x18000c5ae  mov     rax, [rdi+18h]
0x18000c5b2  lea     r8, [rbp+var_30]
0x18000c5b6  mov     rdx, rsi
0x18000c5b9  mov     rcx, [rax+8]
0x18000c5bd  mov     rax, [rcx]
0x18000c5c0  mov     rax, [rax+40h]
0x18000c5c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5c9  mov     ebx, eax
0x18000c5cb  test    eax, eax
0x18000c5cd  js      loc_18000C705
0x18000c5d3  mov     rax, [rdi+18h]
0x18000c5d7  lea     r8, [rbp+var_38]
0x18000c5db  mov     rdx, rsi
0x18000c5de  mov     rcx, [rax+10h]
0x18000c5e2  mov     rax, [rcx]
0x18000c5e5  mov     rax, [rax+40h]
0x18000c5e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5ee  mov     ebx, eax
0x18000c5f0  test    eax, eax
0x18000c5f2  js      loc_18000C705
0x18000c5f8  mov     r8, [rbp+var_40]
0x18000c5fc  lea     rax, [rbp+var_28]
0x18000c600  mov     [rbp+var_20], rax
0x18000c604  xor     eax, eax
0x18000c606  mov     [rbp+var_26], 0
0x18000c60a  xor     ebx, ebx
0x18000c60c  mov     [rbp+var_24], 2
0x18000c613  mov     [rbp+var_18], 0
0x18000c61a  lea     esi, [rax+1]
0x18000c61d  mov     [rbp+var_28], ax
0x18000c621  lea     rcx, [rbp+var_40]; this
0x18000c625  call    ?QueryCCH@String@@QEBAKXZ; String::QueryCCH(void)
0x18000c62a  cmp     ebx, eax
0x18000c62c  jnb     loc_18000C6EE
0x18000c632  xor     r9d, r9d
0x18000c635  lea     rcx, [rbp+var_30]; this
0x18000c639  call    ?QueryCCH@String@@QEBAKXZ; String::QueryCCH(void)
0x18000c63e  cmp     r9d, eax
0x18000c641  jnb     short loc_18000C699
0x18000c643  mov     rax, [rbp+var_30]
0x18000c647  lea     rdx, qword_180016F98
0x18000c64e  test    r8, r8
0x18000c651  lea     rcx, qword_180016F98
0x18000c658  cmovnz  rdx, r8
0x18000c65c  test    rax, rax
0x18000c65f  cmovnz  rcx, rax
0x18000c663  movzx   eax, word ptr [rcx+r9*2]
0x18000c668  cmp     [rdx+rbx*2], ax
0x18000c66c  jz      short loc_18000C673
0x18000c66e  add     r9d, esi
0x18000c671  jmp     short loc_18000C635
0x18000c673  lea     rcx, [rbp+var_38]; this
0x18000c677  call    ?QueryCCH@String@@QEBAKXZ; String::QueryCCH(void)
0x18000c67c  cmp     r9d, eax
0x18000c67f  jnb     short loc_18000C6BF
0x18000c681  mov     rax, [rbp+var_38]
0x18000c685  lea     rcx, qword_180016F98
0x18000c68c  test    rax, rax
0x18000c68f  cmovnz  rcx, rax
0x18000c693  lea     rdx, [rcx+r9*2]
0x18000c697  jmp     short loc_18000C6A9
0x18000c699  test    r8, r8
0x18000c69c  jnz     short loc_18000C6A5
0x18000c69e  lea     r8, qword_180016F98
0x18000c6a5  lea     rdx, [r8+rbx*2]; unsigned __int16 *
0x18000c6a9  mov     r8d, esi; unsigned int
0x18000c6ac  lea     rcx, [rbp+var_28]; this
0x18000c6b0  call    ?Append@STRU@@QEAAJPEBGKK@Z; STRU::Append(ushort const *,ulong,ulong)
0x18000c6b5  mov     edi, eax
0x18000c6b7  test    eax, eax
0x18000c6b9  js      short loc_18000C6C6
0x18000c6bb  mov     r8, [rbp+var_40]
0x18000c6bf  add     ebx, esi
0x18000c6c1  jmp     loc_18000C621
0x18000c6c6  lea     rcx, [rbp+var_28]; this
0x18000c6ca  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000c6cf  lea     rcx, [rbp+var_38]; this
0x18000c6d3  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000c6d8  lea     rcx, [rbp+var_30]; this
0x18000c6dc  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000c6e1  lea     rcx, [rbp+var_40]; this
0x18000c6e5  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000c6ea  mov     eax, edi
0x18000c6ec  jmp     short loc_18000C722
0x18000c6ee  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x18000c6f2  mov     rcx, r14; this
0x18000c6f5  call    ?Initialize@String@@QEAAJPEBG@Z; String::Initialize(ushort const *)
0x18000c6fa  lea     rcx, [rbp+var_28]; this
0x18000c6fe  mov     ebx, eax
0x18000c700  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000c705  lea     rcx, [rbp+var_38]; this
0x18000c709  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000c70e  lea     rcx, [rbp+var_30]; this
0x18000c712  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000c717  lea     rcx, [rbp+var_40]; this
0x18000c71b  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000c720  mov     eax, ebx
0x18000c722  mov     rcx, [rbp+var_10]
0x18000c726  xor     rcx, rsp; StackCookie
0x18000c729  call    __security_check_cookie
0x18000c72e  add     rsp, 60h
0x18000c732  pop     r14
0x18000c734  pop     rdi
0x18000c735  pop     rsi
0x18000c736  pop     rbx
0x18000c737  pop     rbp
0x18000c738  retn
```
