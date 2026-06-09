# CScanner::MoveOn(void)

- ea: `0x1004425b0`
- end: `0x100442714`
- name: `?MoveOn@CScanner@@IEAAJXZ`
- size: `356`
- prototype: `__int64 __fastcall(CScanner *__hidden this)`
- caller_count: `5`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x10042ad30`
- `0x10042b700`
- `0x10042d050`
- `0x10042ed70`
- `0x1004422f0`

## callees

- `0x10043ef20`
- `0x10043efe0`
- `0x100441700`
- `0x100442350`
- `0x1004425b0`
- `0x100444130`

## pseudocode

```c
__int64 __fastcall CScanner::MoveOn(CScanner *this)
{
  struct CScanner::CChain *v1; // rdi
  __int64 *v3; // r14
  struct CScanner::CChain *v4; // rbx
  int v5; // eax
  struct CScanner::CChain *v7; // rbx
  bool v8; // r15
  __int64 v9; // rbp
  int Vertex; // eax
  __int64 v11; // rbp

  v1 = 0;
  v3 = 0;
  if ( *((_DWORD *)this + 51) != 1 )
    v3 = *(__int64 **)(*((_QWORD *)this + 26) + 8LL);
  v4 = 0;
  if ( *((_DWORD *)this + 99) != 1 )
    v4 = *(struct CScanner::CChain **)(*((_QWORD *)this + 50) + 8LL);
  if ( v3 )
  {
    if ( v4 )
    {
      v5 = CScanner::CVertex::CompareWith(*(_QWORD *)(*((_QWORD *)v4 + 1) + 24LL), *v3);
      if ( v5 == 1 || !v5 && *(_QWORD *)(*((_QWORD *)v4 + 1) + 24LL) == *((_QWORD *)v4 + 2) )
        return CScanner::ProcessCandidate(this, v4);
      CScanner::CChainList::Pop((CScanner *)((char *)this + 8));
      v7 = (struct CScanner::CChain *)*((_QWORD *)this + 36);
      v8 = 0;
      v9 = *v3;
      if ( !v7 )
        return CScanner::CJunction::ProcessAtHead(
                 (CScanner *)((char *)this + 296),
                 (struct CScanner::CChain *)v3,
                 v1,
                 v7,
                 v8);
      while ( 1 )
      {
        Vertex = CScanner::CVertex::LocateVertex(*((_QWORD *)v7 + 1), v9);
        if ( Vertex != 1 )
          break;
        v1 = v7;
        v7 = (struct CScanner::CChain *)*((_QWORD *)v7 + 3);
        if ( !v7 )
          return CScanner::CJunction::ProcessAtHead(
                   (CScanner *)((char *)this + 296),
                   (struct CScanner::CChain *)v3,
                   v1,
                   v7,
                   v8);
      }
    }
    else
    {
      CScanner::CChainList::Pop((CScanner *)((char *)this + 8));
      v7 = (struct CScanner::CChain *)*((_QWORD *)this + 36);
      v8 = 0;
      v11 = *v3;
      if ( !v7 )
        return CScanner::CJunction::ProcessAtHead(
                 (CScanner *)((char *)this + 296),
                 (struct CScanner::CChain *)v3,
                 v1,
                 v7,
                 v8);
      while ( 1 )
      {
        Vertex = CScanner::CVertex::LocateVertex(*((_QWORD *)v7 + 1), v11);
        if ( Vertex != 1 )
          break;
        v1 = v7;
        v7 = (struct CScanner::CChain *)*((_QWORD *)v7 + 3);
        if ( !v7 )
          return CScanner::CJunction::ProcessAtHead(
                   (CScanner *)((char *)this + 296),
                   (struct CScanner::CChain *)v3,
                   v1,
                   v7,
                   v8);
      }
    }
    v8 = Vertex == 0;
    return CScanner::CJunction::ProcessAtHead(
             (CScanner *)((char *)this + 296),
             (struct CScanner::CChain *)v3,
             v1,
             v7,
             v8);
  }
  if ( v4 )
    return CScanner::ProcessCandidate(this, v4);
  *((_BYTE *)this + 513) = 1;
  return 0;
}

```

## disassembly

```asm
0x1004425b0  mov     [rsp+arg_8], rbx
0x1004425b5  mov     [rsp+arg_10], rbp
0x1004425ba  push    rsi
0x1004425bb  push    rdi
0x1004425bc  push    r14
0x1004425be  sub     rsp, 30h
0x1004425c2  xor     edi, edi
0x1004425c4  mov     rsi, rcx
0x1004425c7  cmp     dword ptr [rcx+0CCh], 1
0x1004425ce  mov     r14d, edi
0x1004425d1  jz      short loc_1004425DE
0x1004425d3  mov     rax, [rcx+0D0h]
0x1004425da  mov     r14, [rax+8]
0x1004425de  cmp     dword ptr [rcx+18Ch], 1
0x1004425e5  mov     rbx, rdi
0x1004425e8  jz      short loc_1004425F5
0x1004425ea  mov     rax, [rcx+190h]
0x1004425f1  mov     rbx, [rax+8]
0x1004425f5  test    r14, r14
0x1004425f8  jz      loc_1004426F4
0x1004425fe  mov     [rsp+48h+arg_0], r15
0x100442603  test    rbx, rbx
0x100442606  jz      loc_100442690
0x10044260c  mov     rax, [rbx+8]
0x100442610  mov     rdx, [r14]
0x100442613  mov     rcx, [rax+18h]
0x100442617  call    ?CompareWith@CVertex@CScanner@@QEBA?AW4COMPARISON@RobustIntersections@@PEBV12@@Z; CScanner::CVertex::CompareWith(CScanner::CVertex const *)
0x10044261c  cmp     eax, 1
0x10044261f  jz      short loc_100442633
0x100442621  test    eax, eax
0x100442623  jnz     short loc_100442656
0x100442625  mov     rcx, [rbx+8]
0x100442629  mov     rax, [rbx+10h]
0x10044262d  cmp     [rcx+18h], rax
0x100442631  jnz     short loc_100442656
0x100442633  mov     rdx, rbx; struct CScanner::CChain *
0x100442636  mov     rcx, rsi; this
0x100442639  call    ?ProcessCandidate@CScanner@@IEAAJPEAVCChain@1@@Z; CScanner::ProcessCandidate(CScanner::CChain *)
0x10044263e  mov     r15, [rsp+48h+arg_0]
0x100442643  mov     rbx, [rsp+48h+arg_8]
0x100442648  mov     rbp, [rsp+48h+arg_10]
0x10044264d  add     rsp, 30h
0x100442651  pop     r14
0x100442653  pop     rdi
0x100442654  pop     rsi
0x100442655  retn
0x100442656  lea     rcx, [rsi+8]; this
0x10044265a  call    ?Pop@CChainList@CScanner@@QEAAXXZ; CScanner::CChainList::Pop(void)
0x10044265f  mov     rbx, [rsi+120h]
0x100442666  xor     r15b, r15b
0x100442669  mov     rbp, [r14]
0x10044266c  test    rbx, rbx
0x10044266f  jz      short loc_1004426D5
0x100442671  mov     rcx, [rbx+8]
0x100442675  mov     rdx, rbp
0x100442678  call    ?LocateVertex@CVertex@CScanner@@QEBA?AW4SIDEINDICATOR@CLineSegmentIntersection@RobustIntersections@@PEBV12@@Z; CScanner::CVertex::LocateVertex(CScanner::CVertex const *)
0x10044267d  cmp     eax, 1
0x100442680  jnz     short loc_1004426CF
0x100442682  mov     rdi, rbx
0x100442685  mov     rbx, [rbx+18h]
0x100442689  test    rbx, rbx
0x10044268c  jnz     short loc_100442671
0x10044268e  jmp     short loc_1004426D5
0x100442690  add     rcx, 8; this
0x100442694  call    ?Pop@CChainList@CScanner@@QEAAXXZ; CScanner::CChainList::Pop(void)
0x100442699  mov     rbx, [rsi+120h]
0x1004426a0  xor     r15b, r15b
0x1004426a3  mov     rbp, [r14]
0x1004426a6  test    rbx, rbx
0x1004426a9  jz      short loc_1004426D5
0x1004426ab  nop     dword ptr [rax+rax+00h]
0x1004426b0  mov     rcx, [rbx+8]
0x1004426b4  mov     rdx, rbp
0x1004426b7  call    ?LocateVertex@CVertex@CScanner@@QEBA?AW4SIDEINDICATOR@CLineSegmentIntersection@RobustIntersections@@PEBV12@@Z; CScanner::CVertex::LocateVertex(CScanner::CVertex const *)
0x1004426bc  cmp     eax, 1
0x1004426bf  jnz     short loc_1004426CF
0x1004426c1  mov     rdi, rbx
0x1004426c4  mov     rbx, [rbx+18h]
0x1004426c8  test    rbx, rbx
0x1004426cb  jnz     short loc_1004426B0
0x1004426cd  jmp     short loc_1004426D5
0x1004426cf  test    eax, eax
0x1004426d1  setz    r15b
0x1004426d5  lea     rcx, [rsi+128h]; this
0x1004426dc  mov     [rsp+48h+var_28], r15b; bool
0x1004426e1  mov     r9, rbx; struct CScanner::CChain *
0x1004426e4  mov     r8, rdi; struct CScanner::CChain *
0x1004426e7  mov     rdx, r14; struct CScanner::CChain *
0x1004426ea  call    ?ProcessAtHead@CJunction@CScanner@@QEAAJPEAVCChain@2@00_N@Z; CScanner::CJunction::ProcessAtHead(CScanner::CChain *,CScanner::CChain *,CScanner::CChain *,bool)
0x1004426ef  jmp     loc_10044263E
0x1004426f4  test    rbx, rbx
0x1004426f7  jz      short loc_100442706
0x1004426f9  mov     rdx, rbx; struct CScanner::CChain *
0x1004426fc  call    ?ProcessCandidate@CScanner@@IEAAJPEAVCChain@1@@Z; CScanner::ProcessCandidate(CScanner::CChain *)
0x100442701  jmp     loc_100442643
0x100442706  mov     byte ptr [rcx+201h], 1
0x10044270d  mov     eax, edi
0x10044270f  jmp     loc_100442643
```
