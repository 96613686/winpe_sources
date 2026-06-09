# CScanner::CJunction::ProcessAtHead(CScanner::CChain *,CScanner::CChain *,CScanner::CChain *,bool)

- ea: `0x100441700`
- end: `0x1004418db`
- name: `?ProcessAtHead@CJunction@CScanner@@QEAAJPEAVCChain@2@00_N@Z`
- size: `475`
- prototype: `__int64 __usercall@<rax>(CScanner::CJunction *__hidden this@<rcx>, struct CScanner::CChain *@<rdx>, struct CScanner::CChain *@<r8>, struct CScanner::CChain *@<r9>, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1004425b0`

## callees

- `0x10043ef20`
- `0x100440470`
- `0x1004412e0`
- `0x1004415c0`
- `0x100441700`
- `0x100443920`
- `0x100443da0`
- `0x100444130`

## pseudocode

```c
__int64 __fastcall CScanner::CJunction::ProcessAtHead(
        CScanner::CJunction *this,
        struct CScanner::CChain *a2,
        struct CScanner::CChain *a3,
        struct CScanner::CChain *a4,
        bool a5)
{
  struct CScanner::CChain *v5; // rbx
  __int64 v7; // rax
  bool v8; // zf
  __int64 v9; // rax
  __int64 v10; // rbp
  int v11; // esi
  int v12; // ebx
  unsigned int v13; // eax
  __int64 v14; // rbx
  struct CScanner::CChain *v15; // rax
  __int64 v16; // rdx
  struct CScanner::CChain *v17; // rbx
  CScanner::CChainList *v18; // rsi
  __int64 v19; // rdx
  struct CScanner::CChain *v21; // [rsp+30h] [rbp+8h] BYREF

  v5 = a4;
  if ( *(_QWORD *)a2 == *((_QWORD *)a2 + 2) )
  {
    v7 = *((_WORD *)a2 + 36) & 1;
    ++*((_DWORD *)this + v7 + 16);
  }
  else
  {
    *((_QWORD *)this + 4) = a2;
    *((_QWORD *)this + 3) = a2;
  }
  v8 = !a5;
  v9 = *(_QWORD *)a2;
  *(_QWORD *)this = *(_QWORD *)a2;
  *((_QWORD *)this + 9) = *(_QWORD *)(v9 + 96);
  *(_WORD *)((char *)this + 89) = 0;
  *((_BYTE *)this + 88) = 0;
  *((_QWORD *)this + 6) = a4;
  *((_QWORD *)this + 5) = a3;
  if ( !v8 )
  {
    v21 = 0;
    *((_QWORD *)this + 1) = a4;
    *((_QWORD *)this + 2) = a4;
    if ( !a4 )
      goto LABEL_13;
    while ( 1 )
    {
      v10 = *((_QWORD *)this + 7);
      v11 = CScanner::CChain::SplitAtIncidentVertex(
              v5,
              *(const struct CScanner::CVertex **)this,
              (struct CScanner::CIntersectionPool *)(v10 + 464),
              &v21);
      if ( v11 >= 0
        && (_mm_lfence(),
            v12 = *((_DWORD *)v5 + 19),
            v13 = CHeap<CScanner::CCandidateChain,6>::BubbleUp(v10 + 392),
            v13 == v12) )
      {
        _mm_lfence();
        CHeap<CScanner::CCandidateChain,6>::PushDown(v10 + 392, v13);
      }
      else if ( v11 < 0 )
      {
        return (unsigned int)v11;
      }
      if ( !v21 )
        return 2148734217LL;
      CScanner::CJunction::InsertHead(this, v21);
      v14 = *((_QWORD *)this + 2);
      if ( (*(_BYTE *)(v14 + 72) & 0x20) == 0 )
        break;
      v15 = *(struct CScanner::CChain **)(v14 + 24);
      *((_QWORD *)this + 2) = v15;
      v5 = v15;
      if ( !v15 )
        goto LABEL_13;
    }
    if ( v14 )
      *((_QWORD *)this + 6) = *(_QWORD *)(v14 + 24);
    else
LABEL_13:
      *((_QWORD *)this + 6) = 0;
  }
  v16 = *((_QWORD *)this + 7);
  v17 = 0;
  v18 = (CScanner::CChainList *)(v16 + 8);
  if ( *(_DWORD *)(v16 + 204) != 1 )
    v17 = *(struct CScanner::CChain **)(*(_QWORD *)(v16 + 208) + 8LL);
  while ( v17 && !(unsigned int)CScanner::CVertex::CompareWith(*(_QWORD *)this, *(_QWORD *)v17) )
  {
    CScanner::CChainList::Pop(v18);
    CScanner::CJunction::InsertHead(this, v17);
    v19 = *((_QWORD *)this + 7);
    v17 = 0;
    v18 = (CScanner::CChainList *)(v19 + 8);
    if ( *(_DWORD *)(v19 + 204) != 1 )
      v17 = *(struct CScanner::CChain **)(*(_QWORD *)(v19 + 208) + 8LL);
  }
  return CScanner::CJunction::Flush((__int64 **)this);
}

```

## disassembly

```asm
0x100441700  mov     [rsp+arg_18], rbx
0x100441705  push    rdi
0x100441706  sub     rsp, 20h
0x10044170a  mov     rax, [rdx+10h]
0x10044170e  mov     rbx, r9
0x100441711  mov     rdi, rcx
0x100441714  cmp     [rdx], rax
0x100441717  jnz     short loc_100441726
0x100441719  movzx   eax, word ptr [rdx+48h]
0x10044171d  and     eax, 1
0x100441720  inc     dword ptr [rcx+rax*4+40h]
0x100441724  jmp     short loc_10044172E
0x100441726  mov     [rcx+20h], rdx
0x10044172a  mov     [rcx+18h], rdx
0x10044172e  cmp     [rsp+28h+arg_20], 0
0x100441733  mov     rax, [rdx]
0x100441736  mov     [rcx], rax
0x100441739  mov     [rsp+28h+arg_8], rbp
0x10044173e  mov     [rsp+28h+arg_10], rsi
0x100441743  mov     rax, [rax+60h]
0x100441747  mov     [rcx+48h], rax
0x10044174b  mov     word ptr [rcx+59h], 0
0x100441751  mov     byte ptr [rcx+58h], 0
0x100441755  mov     [rcx+30h], rbx
0x100441759  mov     [rcx+28h], r8
0x10044175d  jz      loc_100441819
0x100441763  mov     [rsp+28h+arg_0], 0
0x10044176c  mov     [rcx+8], rbx
0x100441770  mov     [rcx+10h], rbx
0x100441774  test    rbx, rbx
0x100441777  jz      loc_100441811
0x10044177d  nop     dword ptr [rax]
0x100441780  mov     rbp, [rdi+38h]
0x100441784  lea     r9, [rsp+28h+arg_0]; struct CScanner::CChain **
0x100441789  mov     rdx, [rdi]; struct CScanner::CVertex *
0x10044178c  mov     rcx, rbx; this
0x10044178f  lea     r8, [rbp+1D0h]; struct CScanner::CIntersectionPool *
0x100441796  call    ?SplitAtIncidentVertex@CChain@CScanner@@QEAAJPEBVCVertex@2@AEAVCIntersectionPool@2@AEAPEAV12@@Z; CScanner::CChain::SplitAtIncidentVertex(CScanner::CVertex const *,CScanner::CIntersectionPool &,CScanner::CChain * &)
0x10044179b  mov     esi, eax
0x10044179d  test    eax, eax
0x10044179f  js      short loc_1004417CC
0x1004417a1  lfence
0x1004417a4  mov     ebx, [rbx+4Ch]
0x1004417a7  lea     rcx, [rbp+188h]
0x1004417ae  mov     edx, ebx
0x1004417b0  call    ?BubbleUp@?$CHeap@VCCandidateChain@CScanner@@$05@@AEAAII@Z; CHeap<CScanner::CCandidateChain,6>::BubbleUp(uint)
0x1004417b5  cmp     eax, ebx
0x1004417b7  jnz     short loc_1004417CC
0x1004417b9  lfence
0x1004417bc  mov     edx, eax
0x1004417be  lea     rcx, [rbp+188h]
0x1004417c5  call    ?PushDown@?$CHeap@VCCandidateChain@CScanner@@$05@@AEAAXI@Z; CHeap<CScanner::CCandidateChain,6>::PushDown(uint)
0x1004417ca  jmp     short loc_1004417D4
0x1004417cc  test    esi, esi
0x1004417ce  js      loc_1004418C1
0x1004417d4  mov     rdx, [rsp+28h+arg_0]; struct CScanner::CChain *
0x1004417d9  test    rdx, rdx
0x1004417dc  jz      loc_1004418BA
0x1004417e2  mov     rcx, rdi; this
0x1004417e5  call    ?InsertHead@CJunction@CScanner@@QEAAXPEAVCChain@2@@Z; CScanner::CJunction::InsertHead(CScanner::CChain *)
0x1004417ea  mov     rbx, [rdi+10h]
0x1004417ee  movzx   eax, byte ptr [rbx+48h]
0x1004417f2  shr     al, 5
0x1004417f5  test    al, 1
0x1004417f7  jz      loc_1004418C5
0x1004417fd  mov     rax, [rbx+18h]
0x100441801  mov     [rdi+10h], rax
0x100441805  mov     rbx, rax
0x100441808  test    rax, rax
0x10044180b  jnz     loc_100441780
0x100441811  mov     qword ptr [rdi+30h], 0
0x100441819  mov     rdx, [rdi+38h]
0x10044181d  xor     ebx, ebx
0x10044181f  cmp     dword ptr [rdx+0CCh], 1
0x100441826  lea     rsi, [rdx+8]
0x10044182a  jz      short loc_100441837
0x10044182c  mov     rax, [rdx+0D0h]
0x100441833  mov     rbx, [rax+8]
0x100441837  test    rbx, rbx
0x10044183a  jz      short loc_10044189D
0x10044183c  mov     rdx, [rbx]
0x10044183f  mov     rcx, [rdi]
0x100441842  call    ?CompareWith@CVertex@CScanner@@QEBA?AW4COMPARISON@RobustIntersections@@PEBV12@@Z; CScanner::CVertex::CompareWith(CScanner::CVertex const *)
0x100441847  test    eax, eax
0x100441849  jnz     short loc_10044189D
0x10044184b  mov     rcx, rsi; this
0x10044184e  call    ?Pop@CChainList@CScanner@@QEAAXXZ; CScanner::CChainList::Pop(void)
0x100441853  mov     rdx, rbx; struct CScanner::CChain *
0x100441856  mov     rcx, rdi; this
0x100441859  call    ?InsertHead@CJunction@CScanner@@QEAAXPEAVCChain@2@@Z; CScanner::CJunction::InsertHead(CScanner::CChain *)
0x10044185e  mov     rdx, [rdi+38h]
0x100441862  xor     ebx, ebx
0x100441864  cmp     dword ptr [rdx+0CCh], 1
0x10044186b  lea     rsi, [rdx+8]
0x10044186f  jz      short loc_10044187C
0x100441871  mov     rax, [rdx+0D0h]
0x100441878  mov     rbx, [rax+8]
0x10044187c  test    rbx, rbx
0x10044187f  jz      short loc_10044189D
0x100441881  mov     rdx, [rbx]
0x100441884  mov     rcx, [rdi]
0x100441887  call    ?CompareWith@CVertex@CScanner@@QEBA?AW4COMPARISON@RobustIntersections@@PEBV12@@Z; CScanner::CVertex::CompareWith(CScanner::CVertex const *)
0x10044188c  test    eax, eax
0x10044188e  jnz     short loc_10044189D
0x100441890  mov     rcx, rsi; this
0x100441893  call    ?Pop@CChainList@CScanner@@QEAAXXZ; CScanner::CChainList::Pop(void)
0x100441898  test    rbx, rbx
0x10044189b  jnz     short loc_100441853
0x10044189d  mov     rcx, rdi; this
0x1004418a0  call    ?Flush@CJunction@CScanner@@QEAAJXZ; CScanner::CJunction::Flush(void)
0x1004418a5  mov     rsi, [rsp+28h+arg_10]
0x1004418aa  mov     rbp, [rsp+28h+arg_8]
0x1004418af  mov     rbx, [rsp+28h+arg_18]
0x1004418b4  add     rsp, 20h
0x1004418b8  pop     rdi
0x1004418b9  retn
0x1004418ba  mov     eax, 80131509h
0x1004418bf  jmp     short loc_1004418A5
0x1004418c1  mov     eax, esi
0x1004418c3  jmp     short loc_1004418A5
0x1004418c5  test    rbx, rbx
0x1004418c8  jz      loc_100441811
0x1004418ce  mov     rax, [rbx+18h]
0x1004418d2  mov     [rdi+30h], rax
0x1004418d6  jmp     loc_100441819
```
