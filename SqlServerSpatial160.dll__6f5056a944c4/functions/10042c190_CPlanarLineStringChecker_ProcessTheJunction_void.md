# CPlanarLineStringChecker::ProcessTheJunction(void)

- ea: `0x10042c190`
- end: `0x10042c2b6`
- name: `?ProcessTheJunction@CPlanarLineStringChecker@@UEAAJXZ`
- size: `294`
- prototype: `__int64 __fastcall(CPlanarLineStringChecker *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path`

## callees

- `0x10042c190`
- `0x10042c2c0`
- `0x100441c90`

## pseudocode

```c
__int64 __fastcall CPlanarLineStringChecker::ProcessTheJunction(CPlanarLineStringChecker *this)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  int v4; // eax
  __int64 i; // rbx
  __int64 v6; // rbx
  const struct CScanner::CVertex *v7; // r8

  if ( *((_BYTE *)this + 648) )
    CScanner::ClassifyFillOnly(this);
  if ( *((_DWORD *)this + 90) )
  {
    v2 = *((_QWORD *)this + 46);
    v3 = 0xFFFFFFFFLL;
    if ( BYTE4(v2) == 1 )
      v3 = (unsigned int)v2;
    (*(void (__fastcall **)(CPlanarLineStringChecker *, __int64, __int64, __int64))(*(_QWORD *)this + 104LL))(
      this,
      5,
      v3,
      0xFFFFFFFFLL);
  }
  v4 = *((_DWORD *)this + 146);
  for ( i = *((_QWORD *)this + 40); !v4; i = *(_QWORD *)(i + 24) )
  {
    if ( !i )
      break;
    if ( (*(_BYTE *)(i + 72) & 0x20) != 0 )
      (*(void (__fastcall **)(CPlanarLineStringChecker *, __int64, _QWORD, _QWORD))(*(_QWORD *)this + 104LL))(
        this,
        12,
        (unsigned int)g_attributesTable & *(_DWORD *)(*(_QWORD *)(i + 16) + 104LL),
        (unsigned int)g_attributesTable & *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(i + 24) + 16LL) + 104LL));
    if ( *(_QWORD *)i != *(_QWORD *)(i + 16) && (*(_WORD *)(i + 72) & 0x4840) == 0 )
      CPlanarLineStringChecker::CheckOrientationConsistency(
        this,
        (const struct CScanner::CChain *)i,
        *(const struct CScanner::CVertex **)(*(_QWORD *)i + 24LL));
    v4 = *((_DWORD *)this + 146);
  }
  v6 = *((_QWORD *)this + 38);
  if ( !v4 )
  {
    do
    {
      if ( !v6 )
        break;
      v7 = *(const struct CScanner::CVertex **)(v6 + 16);
      if ( *(const struct CScanner::CVertex **)v6 != v7 && (*(_WORD *)(v6 + 72) & 0x4840) == 0 )
        CPlanarLineStringChecker::CheckOrientationConsistency(this, (const struct CScanner::CChain *)v6, v7);
      v6 = *(_QWORD *)(v6 + 24);
    }
    while ( !*((_DWORD *)this + 146) );
  }
  return 0;
}

```

## disassembly

```asm
0x10042c190  mov     [rsp+arg_0], rbx
0x10042c195  mov     [rsp+arg_8], rsi
0x10042c19a  push    rdi
0x10042c19b  sub     rsp, 20h
0x10042c19f  cmp     byte ptr [rcx+288h], 0
0x10042c1a6  mov     rdi, rcx
0x10042c1a9  jz      short loc_10042C1B0
0x10042c1ab  call    ?ClassifyFillOnly@CScanner@@QEAAXXZ; CScanner::ClassifyFillOnly(void)
0x10042c1b0  cmp     dword ptr [rdi+168h], 0
0x10042c1b7  jbe     short loc_10042C1E7
0x10042c1b9  mov     rdx, [rdi+170h]
0x10042c1c0  mov     r8d, 0FFFFFFFFh
0x10042c1c6  mov     rax, rdx
0x10042c1c9  mov     r9d, 0FFFFFFFFh
0x10042c1cf  shr     rax, 20h
0x10042c1d3  mov     rcx, rdi
0x10042c1d6  cmp     al, 1
0x10042c1d8  mov     rax, [rdi]
0x10042c1db  cmovz   r8d, edx
0x10042c1df  mov     edx, 5
0x10042c1e4  call    qword ptr [rax+68h]
0x10042c1e7  mov     eax, [rdi+248h]
0x10042c1ed  mov     esi, 4840h
0x10042c1f2  mov     rbx, [rdi+140h]
0x10042c1f9  test    eax, eax
0x10042c1fb  jnz     short loc_10042C26D
0x10042c1fd  nop     dword ptr [rax]
0x10042c200  test    rbx, rbx
0x10042c203  jz      short loc_10042C26D
0x10042c205  movzx   eax, byte ptr [rbx+48h]
0x10042c209  shr     al, 5
0x10042c20c  test    al, 1
0x10042c20e  jz      short loc_10042C241
0x10042c210  mov     rax, [rbx+18h]
0x10042c214  mov     edx, 0Ch
0x10042c219  mov     r10, [rdi]
0x10042c21c  mov     rcx, [rax+10h]
0x10042c220  mov     rax, [rbx+10h]
0x10042c224  mov     r9d, [rcx+68h]
0x10042c228  mov     rcx, rdi
0x10042c22b  mov     r8d, [rax+68h]
0x10042c22f  and     r8d, cs:?g_attributesTable@@3QBUCAttribute@@B; CAttribute const near * const g_attributesTable
0x10042c236  and     r9d, cs:?g_attributesTable@@3QBUCAttribute@@B; CAttribute const near * const g_attributesTable
0x10042c23d  call    qword ptr [r10+68h]
0x10042c241  mov     r8, [rbx]
0x10042c244  cmp     r8, [rbx+10h]
0x10042c248  jz      short loc_10042C25F
0x10042c24a  test    [rbx+48h], si
0x10042c24e  jnz     short loc_10042C25F
0x10042c250  mov     r8, [r8+18h]; struct CScanner::CVertex *
0x10042c254  mov     rdx, rbx; struct CScanner::CChain *
0x10042c257  mov     rcx, rdi; this
0x10042c25a  call    ?CheckOrientationConsistency@CPlanarLineStringChecker@@IEAAXPEBVCChain@CScanner@@PEBVCVertex@3@@Z; CPlanarLineStringChecker::CheckOrientationConsistency(CScanner::CChain const *,CScanner::CVertex const *)
0x10042c25f  mov     eax, [rdi+248h]
0x10042c265  mov     rbx, [rbx+18h]
0x10042c269  test    eax, eax
0x10042c26b  jz      short loc_10042C200
0x10042c26d  mov     rbx, [rdi+130h]
0x10042c274  test    eax, eax
0x10042c276  jnz     short loc_10042C2A4
0x10042c278  test    rbx, rbx
0x10042c27b  jz      short loc_10042C2A4
0x10042c27d  mov     r8, [rbx+10h]; struct CScanner::CVertex *
0x10042c281  cmp     [rbx], r8
0x10042c284  jz      short loc_10042C297
0x10042c286  test    [rbx+48h], si
0x10042c28a  jnz     short loc_10042C297
0x10042c28c  mov     rdx, rbx; struct CScanner::CChain *
0x10042c28f  mov     rcx, rdi; this
0x10042c292  call    ?CheckOrientationConsistency@CPlanarLineStringChecker@@IEAAXPEBVCChain@CScanner@@PEBVCVertex@3@@Z; CPlanarLineStringChecker::CheckOrientationConsistency(CScanner::CChain const *,CScanner::CVertex const *)
0x10042c297  cmp     dword ptr [rdi+248h], 0
0x10042c29e  mov     rbx, [rbx+18h]
0x10042c2a2  jz      short loc_10042C278
0x10042c2a4  mov     rbx, [rsp+28h+arg_0]
0x10042c2a9  xor     eax, eax
0x10042c2ab  mov     rsi, [rsp+28h+arg_8]
0x10042c2b0  add     rsp, 20h
0x10042c2b4  pop     rdi
0x10042c2b5  retn
```
