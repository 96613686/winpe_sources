# CScanner::CJunction::Flush(void)

- ea: `0x1004412e0`
- end: `0x1004415b1`
- name: `?Flush@CJunction@CScanner@@QEAAJXZ`
- size: `721`
- prototype: `__int64 __fastcall(CScanner::CJunction *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x100441700`
- `0x1004418f0`

## callees

- `0x1004412e0`
- `0x100441b00`
- `0x100442b30`
- `0x100442e30`
- `0x100443ae0`
- `0x100443be0`
- `0x100443da0`

## pseudocode

```c
__int64 __fastcall CScanner::CJunction::Flush(__int64 **this)
{
  __int64 *i; // rcx
  __int64 *j; // rdx
  struct CScanner::CChain *v4; // rcx
  struct CScanner::CChain *v5; // rsi
  struct CScanner::CChain *v6; // rbx
  __int64 *v7; // rbx
  __int64 *v8; // rbp
  __int64 v9; // rax
  __int64 v10; // rcx
  struct CScanner::CChain *v11; // rdx
  CScanner *v12; // rcx
  __int64 result; // rax
  __int64 *v14; // rcx
  __int64 v15; // xmm0_8
  __int64 k; // xmm1_8
  _QWORD *v17; // rax
  __int64 *m; // rcx
  _QWORD *v19; // rax
  int v20; // ebx
  __int64 *v21; // rbp
  __int64 *v22; // rax
  __int64 *v23; // rcx
  __int64 *v24; // rsi
  __int64 *v25; // r14
  __int64 *v26; // rsi

  if ( *((_BYTE *)this + 88) )
  {
    for ( i = this[3]; i; i = (__int64 *)i[3] )
    {
      *(_QWORD *)(*i + 96) = this[9];
      if ( i == this[4] )
        break;
    }
    for ( j = this[1]; j; j = (__int64 *)j[3] )
    {
      *(_QWORD *)(j[2] + 96) = this[9];
      if ( j == this[2] )
        break;
    }
  }
  v4 = (struct CScanner::CChain *)this[1];
  if ( v4 )
  {
    while ( 1 )
    {
      v5 = (struct CScanner::CChain *)this[2];
      if ( v4 == v5 )
        break;
      v6 = v4;
      while ( (*((_BYTE *)v6 + 72) & 0x20) != 0 )
      {
        v6 = (struct CScanner::CChain *)*((_QWORD *)v6 + 3);
        if ( !v6 )
          goto LABEL_16;
      }
      if ( v6 != v4 )
        CScanner::ResolveBundleAttributes((CScanner *)this[7], v4, v6);
LABEL_16:
      v4 = (struct CScanner::CChain *)*((_QWORD *)v6 + 3);
      if ( !v4 )
      {
        v5 = (struct CScanner::CChain *)this[2];
        break;
      }
    }
    v7 = this[1];
    v8 = this[7];
    v9 = *((_QWORD *)v5 + 3);
    v10 = v7[4];
    if ( v10 )
      *(_QWORD *)(v10 + 24) = v9;
    else
      v8[36] = v9;
    if ( v9 )
      *(_QWORD *)(v9 + 32) = v10;
    v7[4] = 0;
    *((_QWORD *)v5 + 3) = 0;
    do
    {
      CHeap<CScanner::CCandidateChain,6>::RemoveByIndex(v8 + 49, *((unsigned int *)v7 + 19));
      if ( v7 == (__int64 *)v5 )
        break;
      v7 = (__int64 *)v7[3];
    }
    while ( v7 );
  }
  v11 = (struct CScanner::CChain *)this[3];
  v12 = (CScanner *)this[7];
  if ( v11 )
  {
    result = CScanner::SplitAtIntersections(
               v12,
               v11,
               (struct CScanner::CChain *)this[4],
               (struct CScanner::CChain *)this[5],
               (struct CScanner::CChain *)this[6]);
    if ( (int)result < 0 )
      return result;
  }
  else
  {
    result = CScanner::SplitPairAtIntersection(
               v12,
               (struct CScanner::CChain *)this[5],
               (struct CScanner::CChain *)this[6]);
    if ( (int)result < 0 )
      return result;
  }
  v14 = this[3];
  v15 = **this;
  for ( k = (*this)[1]; v14; v14 = (__int64 *)v14[3] )
  {
    v17 = (_QWORD *)*v14;
    *v17 = v15;
    v17[1] = k;
    if ( v14 == this[4] )
      break;
  }
  for ( m = this[1]; m; m = (__int64 *)m[3] )
  {
    v19 = (_QWORD *)m[2];
    *v19 = v15;
    v19[1] = k;
    if ( m == this[2] )
      break;
  }
  result = (*(__int64 (__fastcall **)(__int64 *))(*this[7] + 88))(this[7]);
  v20 = result;
  if ( (int)result >= 0 )
  {
    v21 = this[3];
    if ( !v21 )
      goto LABEL_52;
    v22 = this[5];
    v23 = this[6];
    v24 = this[7];
    v25 = this[4];
    if ( v22 )
      v22[3] = (__int64)v21;
    v21[4] = (__int64)v22;
    if ( v25 )
      v25[3] = (__int64)v23;
    if ( v23 )
      v23[4] = (__int64)v25;
    if ( !v22 )
      v24[36] = (__int64)v21;
    v26 = v24 + 49;
    do
    {
      v20 = 0;
      if ( *((_DWORD *)v26 + 1) == *(_DWORD *)v26 )
      {
        v20 = CAutoArray<CScanner::CCandidateChain,7,Default_Allocator<CScanner::CCandidateChain>>::Grow(v26);
        if ( v20 < 0 )
          break;
      }
      *(_QWORD *)(v26[1] + 8LL * (unsigned int)(*((_DWORD *)v26 + 1))++) = v21;
      _mm_lfence();
      *((_DWORD *)v21 + 19) = *((_DWORD *)v26 + 1) - 1;
      CHeap<CScanner::CCandidateChain,6>::BubbleUp(v26);
      if ( v21 == v25 )
        break;
      v21 = (__int64 *)v21[3];
    }
    while ( v21 );
    if ( v20 >= 0 )
    {
LABEL_52:
      this[2] = 0;
      this[1] = 0;
      this[4] = 0;
      this[3] = 0;
      this[6] = 0;
      this[5] = 0;
      *this = 0;
      this[8] = 0;
      *(_WORD *)((char *)this + 89) = 0;
    }
    return (unsigned int)v20;
  }
  return result;
}

```

## disassembly

```asm
0x1004412e0  push    rdi
0x1004412e2  push    r15
0x1004412e4  sub     rsp, 38h
0x1004412e8  cmp     byte ptr [rcx+58h], 0
0x1004412ec  mov     rdi, rcx
0x1004412ef  jz      short loc_10044134B
0x1004412f1  mov     rcx, [rcx+18h]
0x1004412f5  test    rcx, rcx
0x1004412f8  jz      short loc_10044131A
0x1004412fa  nop     word ptr [rax+rax+00h]
0x100441300  mov     rdx, [rcx]
0x100441303  mov     rax, [rdi+48h]
0x100441307  mov     [rdx+60h], rax
0x10044130b  cmp     rcx, [rdi+20h]
0x10044130f  jz      short loc_10044131A
0x100441311  mov     rcx, [rcx+18h]
0x100441315  test    rcx, rcx
0x100441318  jnz     short loc_100441300
0x10044131a  mov     rdx, [rdi+8]
0x10044131e  test    rdx, rdx
0x100441321  jz      short loc_10044134B
0x100441323  nop     dword ptr [rax+00h]
0x100441327  nop     word ptr [rax+rax+00000000h]
0x100441330  mov     rcx, [rdx+10h]
0x100441334  mov     rax, [rdi+48h]
0x100441338  mov     [rcx+60h], rax
0x10044133c  cmp     rdx, [rdi+10h]
0x100441340  jz      short loc_10044134B
0x100441342  mov     rdx, [rdx+18h]
0x100441346  test    rdx, rdx
0x100441349  jnz     short loc_100441330
0x10044134b  mov     rcx, [rdi+8]
0x10044134f  xor     r15d, r15d
0x100441352  mov     [rsp+48h+arg_0], rbx
0x100441357  mov     [rsp+48h+arg_8], rbp
0x10044135c  mov     [rsp+48h+arg_10], rsi
0x100441361  test    rcx, rcx
0x100441364  jz      loc_10044140D
0x10044136a  nop     word ptr [rax+rax+00h]
0x100441370  mov     rsi, [rdi+10h]
0x100441374  cmp     rcx, rsi
0x100441377  jz      short loc_1004413B8
0x100441379  mov     rbx, rcx
0x10044137c  test    rcx, rcx
0x10044137f  jz      short loc_1004413AB
0x100441381  movzx   eax, byte ptr [rbx+48h]
0x100441385  shr     al, 5
0x100441388  test    al, 1
0x10044138a  jz      short loc_100441397
0x10044138c  mov     rbx, [rbx+18h]
0x100441390  test    rbx, rbx
0x100441393  jnz     short loc_100441381
0x100441395  jmp     short loc_1004413AB
0x100441397  cmp     rbx, rcx
0x10044139a  jz      short loc_1004413AB
0x10044139c  mov     rdx, rcx; struct CScanner::CChain *
0x10044139f  mov     r8, rbx; struct CScanner::CChain *
0x1004413a2  mov     rcx, [rdi+38h]; this
0x1004413a6  call    ?ResolveBundleAttributes@CScanner@@IEAAXPEAVCChain@1@0@Z; CScanner::ResolveBundleAttributes(CScanner::CChain *,CScanner::CChain *)
0x1004413ab  mov     rcx, [rbx+18h]
0x1004413af  test    rcx, rcx
0x1004413b2  jnz     short loc_100441370
0x1004413b4  mov     rsi, [rdi+10h]
0x1004413b8  mov     rbx, [rdi+8]
0x1004413bc  mov     rbp, [rdi+38h]
0x1004413c0  mov     rax, [rsi+18h]
0x1004413c4  mov     rcx, [rbx+20h]
0x1004413c8  test    rcx, rcx
0x1004413cb  jnz     short loc_1004413D6
0x1004413cd  mov     [rbp+120h], rax
0x1004413d4  jmp     short loc_1004413DA
0x1004413d6  mov     [rcx+18h], rax
0x1004413da  test    rax, rax
0x1004413dd  jz      short loc_1004413E3
0x1004413df  mov     [rax+20h], rcx
0x1004413e3  mov     [rbx+20h], r15
0x1004413e7  mov     [rsi+18h], r15
0x1004413eb  nop     dword ptr [rax+rax+00h]
0x1004413f0  mov     edx, [rbx+4Ch]
0x1004413f3  lea     rcx, [rbp+188h]
0x1004413fa  call    ?RemoveByIndex@?$CHeap@VCCandidateChain@CScanner@@$05@@AEAAXI@Z; CHeap<CScanner::CCandidateChain,6>::RemoveByIndex(uint)
0x1004413ff  cmp     rbx, rsi
0x100441402  jz      short loc_10044140D
0x100441404  mov     rbx, [rbx+18h]
0x100441408  test    rbx, rbx
0x10044140b  jnz     short loc_1004413F0
0x10044140d  mov     rdx, [rdi+18h]; struct CScanner::CChain *
0x100441411  mov     r8, [rdi+30h]; struct CScanner::CChain *
0x100441415  mov     rax, [rdi+28h]
0x100441419  mov     rcx, [rdi+38h]; this
0x10044141d  test    rdx, rdx
0x100441420  jz      short loc_10044143C
0x100441422  mov     [rsp+48h+var_28], r8; struct CScanner::CChain *
0x100441427  mov     r9, rax; struct CScanner::CChain *
0x10044142a  mov     r8, [rdi+20h]; struct CScanner::CChain *
0x10044142e  call    ?SplitAtIntersections@CScanner@@IEAAJPEAVCChain@1@000@Z; CScanner::SplitAtIntersections(CScanner::CChain *,CScanner::CChain *,CScanner::CChain *,CScanner::CChain *)
0x100441433  test    eax, eax
0x100441435  jns     short loc_10044144C
0x100441437  jmp     loc_10044159A
0x10044143c  mov     rdx, rax; struct CScanner::CChain *
0x10044143f  call    ?SplitPairAtIntersection@CScanner@@IEAAJPEAVCChain@1@0@Z; CScanner::SplitPairAtIntersection(CScanner::CChain *,CScanner::CChain *)
0x100441444  test    eax, eax
0x100441446  js      loc_10044159A
0x10044144c  mov     rax, [rdi]
0x10044144f  mov     rcx, [rdi+18h]
0x100441453  movsd   xmm0, qword ptr [rax]
0x100441457  movsd   xmm1, qword ptr [rax+8]
0x10044145c  test    rcx, rcx
0x10044145f  jz      short loc_10044148B
0x100441461  nop     dword ptr [rax+00h]
0x100441465  nop     word ptr [rax+rax+00000000h]
0x100441470  mov     rax, [rcx]
0x100441473  movsd   qword ptr [rax], xmm0
0x100441477  movsd   qword ptr [rax+8], xmm1
0x10044147c  cmp     rcx, [rdi+20h]
0x100441480  jz      short loc_10044148B
0x100441482  mov     rcx, [rcx+18h]
0x100441486  test    rcx, rcx
0x100441489  jnz     short loc_100441470
0x10044148b  mov     rcx, [rdi+8]
0x10044148f  test    rcx, rcx
0x100441492  jz      short loc_1004414BC
0x100441494  nop     dword ptr [rax+00h]
0x100441498  nop     dword ptr [rax+rax+00000000h]
0x1004414a0  mov     rax, [rcx+10h]
0x1004414a4  movsd   qword ptr [rax], xmm0
0x1004414a8  movsd   qword ptr [rax+8], xmm1
0x1004414ad  cmp     rcx, [rdi+10h]
0x1004414b1  jz      short loc_1004414BC
0x1004414b3  mov     rcx, [rcx+18h]
0x1004414b7  test    rcx, rcx
0x1004414ba  jnz     short loc_1004414A0
0x1004414bc  mov     rcx, [rdi+38h]
0x1004414c0  mov     rax, [rcx]
0x1004414c3  call    qword ptr [rax+58h]
0x1004414c6  mov     ebx, eax
0x1004414c8  test    eax, eax
0x1004414ca  js      loc_10044159A
0x1004414d0  mov     rbp, [rdi+18h]
0x1004414d4  test    rbp, rbp
0x1004414d7  jz      loc_100441574
0x1004414dd  mov     rax, [rdi+28h]
0x1004414e1  mov     rcx, [rdi+30h]
0x1004414e5  mov     rsi, [rdi+38h]
0x1004414e9  mov     [rsp+48h+var_18], r14
0x1004414ee  mov     r14, [rdi+20h]
0x1004414f2  test    rax, rax
0x1004414f5  jz      short loc_1004414FB
0x1004414f7  mov     [rax+18h], rbp
0x1004414fb  mov     [rbp+20h], rax
0x1004414ff  test    r14, r14
0x100441502  jz      short loc_100441508
0x100441504  mov     [r14+18h], rcx
0x100441508  test    rcx, rcx
0x10044150b  jz      short loc_100441511
0x10044150d  mov     [rcx+20h], r14
0x100441511  test    rax, rax
0x100441514  jnz     short loc_10044151D
0x100441516  mov     [rsi+120h], rbp
0x10044151d  add     rsi, 188h
0x100441524  mov     eax, [rsi]
0x100441526  mov     ebx, r15d
0x100441529  cmp     [rsi+4], eax
0x10044152c  jnz     short loc_10044153C
0x10044152e  mov     rcx, rsi
0x100441531  call    ?Grow@?$CAutoArray@VCCandidateChain@CScanner@@$06V?$Default_Allocator@VCCandidateChain@CScanner@@@@@@AEAAJXZ; CAutoArray<CScanner::CCandidateChain,7,Default_Allocator<CScanner::CCandidateChain>>::Grow(void)
0x100441536  mov     ebx, eax
0x100441538  test    eax, eax
0x10044153a  js      short loc_10044156B
0x10044153c  mov     ecx, [rsi+4]
0x10044153f  mov     rax, [rsi+8]
0x100441543  mov     [rax+rcx*8], rbp
0x100441547  inc     dword ptr [rsi+4]
0x10044154a  lfence
0x10044154d  mov     edx, [rsi+4]
0x100441550  mov     rcx, rsi
0x100441553  dec     edx
0x100441555  mov     [rbp+4Ch], edx
0x100441558  call    ?BubbleUp@?$CHeap@VCCandidateChain@CScanner@@$05@@AEAAII@Z; CHeap<CScanner::CCandidateChain,6>::BubbleUp(uint)
0x10044155d  cmp     rbp, r14
0x100441560  jz      short loc_10044156B
0x100441562  mov     rbp, [rbp+18h]
0x100441566  test    rbp, rbp
0x100441569  jnz     short loc_100441524
0x10044156b  mov     r14, [rsp+48h+var_18]
0x100441570  test    ebx, ebx
0x100441572  js      short loc_100441598
0x100441574  mov     [rdi+10h], r15
0x100441578  mov     [rdi+8], r15
0x10044157c  mov     [rdi+20h], r15
0x100441580  mov     [rdi+18h], r15
0x100441584  mov     [rdi+30h], r15
0x100441588  mov     [rdi+28h], r15
0x10044158c  mov     [rdi], r15
0x10044158f  mov     [rdi+40h], r15
0x100441593  mov     [rdi+59h], r15w
0x100441598  mov     eax, ebx
0x10044159a  mov     rsi, [rsp+48h+arg_10]
0x10044159f  mov     rbp, [rsp+48h+arg_8]
0x1004415a4  mov     rbx, [rsp+48h+arg_0]
0x1004415a9  add     rsp, 38h
0x1004415ad  pop     r15
0x1004415af  pop     rdi
0x1004415b0  retn
```
