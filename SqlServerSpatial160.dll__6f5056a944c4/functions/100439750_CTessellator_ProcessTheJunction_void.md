# CTessellator::ProcessTheJunction(void)

- ea: `0x100439750`
- end: `0x100439ae3`
- name: `?ProcessTheJunction@CTessellator@@UEAAJXZ`
- size: `915`
- prototype: `__int64 __fastcall(CTessellator *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path`

## callees

- `0x100439750`
- `0x100439af0`
- `0x100439c50`
- `0x100439ff0`
- `0x10043a190`
- `0x10043a330`
- `0x10043a4a0`
- `0x100441c90`

## pseudocode

```c
__int64 __fastcall CTessellator::ProcessTheJunction(CTessellator *this)
{
  struct CScanner::CChain *v1; // rsi
  unsigned int v3; // r14d
  __int64 i; // rdi
  __int64 j; // r13
  __int64 k; // rbp
  __int64 m; // r15
  __int64 v8; // rbx
  char *v9; // rax
  __int64 v10; // r14
  int v11; // eax
  struct CTessellator::CVertexRef *v12; // r8
  unsigned int v13; // eax
  bool v14; // zf
  __int64 v15; // rdx
  __int64 v16; // rdi
  __int64 v17; // rax
  __int64 v18; // rbx
  __int64 n; // rcx
  struct CTessellator::CVertexRef *v21; // [rsp+50h] [rbp+8h] BYREF

  v1 = 0;
  v3 = 0;
  CScanner::ClassifyFillOnly(this);
  for ( i = *((_QWORD *)this + 40); i; i = *(_QWORD *)(i + 24) )
  {
    if ( (*(_WORD *)(i + 72) & 0x2600) == 0 )
      break;
  }
  for ( j = *((_QWORD *)this + 41); j; j = *(_QWORD *)(j + 32) )
  {
    if ( (*(_WORD *)(j + 72) & 0x2600) == 0 )
      break;
  }
  for ( k = *((_QWORD *)this + 38); k; k = *(_QWORD *)(k + 24) )
  {
    if ( (*(_WORD *)(k + 72) & 0x2600) == 0 )
      break;
  }
  for ( m = *((_QWORD *)this + 39); m; m = *(_QWORD *)(m + 32) )
  {
    if ( (*(_WORD *)(m + 72) & 0x2600) == 0 )
      break;
  }
  if ( i )
  {
    if ( !k )
    {
LABEL_49:
      if ( (((unsigned __int8)~HIBYTE(*(unsigned __int16 *)(i + 72))
           ^ (unsigned __int8)~(*(unsigned __int16 *)(i + 72) >> 12))
          & 1) != 0 )
      {
        if ( k )
        {
          *(_QWORD *)(i + 56) = *(_QWORD *)(k + 56);
          *(_QWORD *)(k + 56) = 0;
          if ( i == j )
            return v3;
          for ( i = *(_QWORD *)(i + 24); i; i = *(_QWORD *)(i + 24) )
          {
            if ( (*(_WORD *)(i + 72) & 0x2600) == 0 )
              break;
          }
          v1 = (struct CScanner::CChain *)j;
        }
        else
        {
          v3 = CTessellator::SplitTheBand(this, (struct CScanner::CChain *)i, (struct CScanner::CChain *)j);
          if ( (v3 & 0x80000000) != 0 )
            return v3;
          _mm_lfence();
          for ( i = *(_QWORD *)(i + 24); i; i = *(_QWORD *)(i + 24) )
          {
            if ( (*(_WORD *)(i + 72) & 0x2600) == 0 )
              break;
          }
          if ( i != j )
          {
            _mm_lfence();
            for ( n = *(_QWORD *)(j + 32); n; n = *(_QWORD *)(n + 32) )
            {
              if ( (*(_WORD *)(n + 72) & 0x2600) == 0 )
                break;
            }
            v1 = (struct CScanner::CChain *)n;
          }
        }
        if ( !i )
          return v3;
      }
      else
      {
        v1 = (struct CScanner::CChain *)j;
      }
      if ( v1 )
        return (unsigned int)CTessellator::CreateBands(this, (struct CScanner::CChain *)i, v1);
      return v3;
    }
  }
  else if ( !k )
  {
    return v3;
  }
  if ( !m )
    return (unsigned int)-2146233079;
  v8 = k;
  v9 = (char *)this + 536;
  do
  {
    v10 = *(_QWORD *)(v8 + 16);
    v21 = 0;
    v11 = SQL_Memblock<CTessellator::CVertexRef>::Allocate(v9, &v21);
    v12 = v21;
    if ( v11 >= 0 )
    {
      *(_QWORD *)v21 = v10;
      *((_QWORD *)v12 + 2) = 0;
      *((_QWORD *)v12 + 1) = 0;
    }
    if ( !v12 )
      return (unsigned int)-2147024882;
    if ( (((unsigned __int8)~HIBYTE(*(unsigned __int16 *)(v8 + 72))
         ^ (unsigned __int8)~(*(unsigned __int16 *)(v8 + 72) >> 12))
        & 1) != 0 )
      v13 = CTessellator::ProcessAsRight(this, (struct CScanner::CChain *)v8, v12);
    else
      v13 = CTessellator::ProcessAsLeft(this, (struct CScanner::CChain *)v8, v12);
    v3 = v13;
    if ( m == v8 )
      break;
    v8 = *(_QWORD *)(v8 + 24);
    v14 = v8 == 0;
    if ( v8 )
    {
      do
      {
        if ( (*(_WORD *)(v8 + 72) & 0x2600) == 0 )
          break;
        v8 = *(_QWORD *)(v8 + 24);
      }
      while ( v8 );
      v14 = v8 == 0;
    }
    v9 = (char *)this + 536;
  }
  while ( !v14 );
  if ( (v3 & 0x80000000) != 0 )
    return v3;
  if ( i )
    goto LABEL_49;
  if ( (((unsigned __int8)~HIBYTE(*(unsigned __int16 *)(k + 72))
       ^ (unsigned __int8)~(*(unsigned __int16 *)(k + 72) >> 12))
      & 1) == 0 )
    return v3;
  v3 = 0;
  if ( k == m )
    return (unsigned int)-2146233079;
  v15 = *(_QWORD *)(k + 56);
  v16 = *(_QWORD *)(m + 56);
  if ( !v15 || !v16 )
    return (unsigned int)-2146233079;
  v17 = *(_QWORD *)(v15 + 8);
  if ( v17 )
  {
    *(_QWORD *)(v17 + 16) = v16;
    *(_QWORD *)(v16 + 8) = v17;
    SQL_Memblock<CTessellator::CVertexRef>::Free((char *)this + 536);
    return v3;
  }
  v18 = *((_QWORD *)this + 42);
  if ( !v18 )
    return (unsigned int)-2146233079;
  while ( (*(_WORD *)(v18 + 72) & 0x2600) != 0 )
  {
    v18 = *(_QWORD *)(v18 + 32);
    if ( !v18 )
      return (unsigned int)-2146233079;
  }
  if ( *(_QWORD *)(v18 + 56) )
    SQL_Memblock<CTessellator::CVertexRef>::Free((char *)this + 536);
  *(_QWORD *)(v18 + 56) = v16;
  *(_QWORD *)(v16 + 8) = 0;
  return v3;
}

```

## disassembly

```asm
0x100439750  mov     [rsp+arg_8], rbx
0x100439755  mov     [rsp+arg_10], rbp
0x10043975a  mov     [rsp+arg_18], rsi
0x10043975f  push    rdi
0x100439760  push    r12
0x100439762  push    r13
0x100439764  push    r14
0x100439766  push    r15
0x100439768  sub     rsp, 20h
0x10043976c  xor     esi, esi
0x10043976e  mov     r12, rcx
0x100439771  mov     r14d, esi
0x100439774  call    ?ClassifyFillOnly@CScanner@@QEAAXXZ; CScanner::ClassifyFillOnly(void)
0x100439779  mov     rdi, [r12+140h]
0x100439781  mov     ebx, 2600h
0x100439786  test    rdi, rdi
0x100439789  jz      short loc_1004397A5
0x10043978b  nop     dword ptr [rax+rax+00h]
0x100439790  movzx   eax, word ptr [rdi+48h]
0x100439794  and     ax, bx
0x100439797  cmp     si, ax
0x10043979a  jz      short loc_1004397A5
0x10043979c  mov     rdi, [rdi+18h]
0x1004397a0  test    rdi, rdi
0x1004397a3  jnz     short loc_100439790
0x1004397a5  mov     r13, [r12+148h]
0x1004397ad  test    r13, r13
0x1004397b0  jz      short loc_1004397C8
0x1004397b2  movzx   eax, word ptr [r13+48h]
0x1004397b7  and     ax, bx
0x1004397ba  cmp     si, ax
0x1004397bd  jz      short loc_1004397C8
0x1004397bf  mov     r13, [r13+20h]
0x1004397c3  test    r13, r13
0x1004397c6  jnz     short loc_1004397B2
0x1004397c8  mov     rbp, [r12+130h]
0x1004397d0  test    rbp, rbp
0x1004397d3  jz      short loc_1004397F5
0x1004397d5  nop     word ptr [rax+rax+00000000h]
0x1004397e0  movzx   eax, word ptr [rbp+48h]
0x1004397e4  and     ax, bx
0x1004397e7  cmp     si, ax
0x1004397ea  jz      short loc_1004397F5
0x1004397ec  mov     rbp, [rbp+18h]
0x1004397f0  test    rbp, rbp
0x1004397f3  jnz     short loc_1004397E0
0x1004397f5  mov     r15, [r12+138h]
0x1004397fd  test    r15, r15
0x100439800  jz      short loc_100439818
0x100439802  movzx   eax, word ptr [r15+48h]
0x100439807  and     ax, bx
0x10043980a  cmp     si, ax
0x10043980d  jz      short loc_100439818
0x10043980f  mov     r15, [r15+20h]
0x100439813  test    r15, r15
0x100439816  jnz     short loc_100439802
0x100439818  test    rdi, rdi
0x10043981b  jnz     short loc_100439828
0x10043981d  test    rbp, rbp
0x100439820  jz      loc_100439AC3
0x100439826  jmp     short loc_100439831
0x100439828  test    rbp, rbp
0x10043982b  jz      loc_1004399D8
0x100439831  test    r15, r15
0x100439834  jnz     short loc_100439841
0x100439836  mov     r14d, 80131509h
0x10043983c  jmp     loc_100439AC3
0x100439841  mov     rbx, rbp
0x100439844  test    rbp, rbp
0x100439847  jz      loc_1004398F8
0x10043984d  lea     rax, [r12+218h]
0x100439855  nop     word ptr [rax+rax+00000000h]
0x100439860  mov     r14, [rbx+10h]
0x100439864  lea     rdx, [rsp+48h+arg_0]
0x100439869  mov     rcx, rax
0x10043986c  mov     [rsp+48h+arg_0], rsi
0x100439871  call    ?Allocate@?$SQL_Memblock@VCVertexRef@CTessellator@@@@QEAAJPEAPEAVCVertexRef@CTessellator@@@Z; SQL_Memblock<CTessellator::CVertexRef>::Allocate(CTessellator::CVertexRef * *)
0x100439876  mov     r8, [rsp+48h+arg_0]; struct CTessellator::CVertexRef *
0x10043987b  test    eax, eax
0x10043987d  js      short loc_10043988A
0x10043987f  mov     [r8], r14
0x100439882  mov     [r8+10h], rsi
0x100439886  mov     [r8+8], rsi
0x10043988a  test    r8, r8
0x10043988d  jz      loc_10043996E
0x100439893  movzx   eax, word ptr [rbx+48h]
0x100439897  mov     rdx, rbx; struct CScanner::CChain *
0x10043989a  mov     ecx, eax
0x10043989c  shr     eax, 8
0x10043989f  shr     ecx, 0Ch
0x1004398a2  not     eax
0x1004398a4  not     ecx
0x1004398a6  xor     ecx, eax
0x1004398a8  test    cl, 1
0x1004398ab  mov     rcx, r12; this
0x1004398ae  jz      short loc_1004398B7
0x1004398b0  call    ?ProcessAsRight@CTessellator@@QEAAJPEAVCChain@CScanner@@PEAVCVertexRef@1@@Z; CTessellator::ProcessAsRight(CScanner::CChain *,CTessellator::CVertexRef *)
0x1004398b5  jmp     short loc_1004398BC
0x1004398b7  call    ?ProcessAsLeft@CTessellator@@QEAAJPEAVCChain@CScanner@@PEAVCVertexRef@1@@Z; CTessellator::ProcessAsLeft(CScanner::CChain *,CTessellator::CVertexRef *)
0x1004398bc  mov     r14d, eax
0x1004398bf  cmp     r15, rbx
0x1004398c2  jz      short loc_1004398F8
0x1004398c4  mov     rbx, [rbx+18h]
0x1004398c8  test    rbx, rbx
0x1004398cb  jz      short loc_1004398EA
0x1004398cd  mov     ecx, 2600h
0x1004398d2  movzx   eax, word ptr [rbx+48h]
0x1004398d6  and     ax, cx
0x1004398d9  cmp     si, ax
0x1004398dc  jz      short loc_1004398E7
0x1004398de  mov     rbx, [rbx+18h]
0x1004398e2  test    rbx, rbx
0x1004398e5  jnz     short loc_1004398D2
0x1004398e7  test    rbx, rbx
0x1004398ea  lea     rax, [r12+218h]
0x1004398f2  jnz     loc_100439860
0x1004398f8  test    r14d, r14d
0x1004398fb  js      loc_100439AC3
0x100439901  test    rdi, rdi
0x100439904  jnz     loc_1004399D3
0x10043990a  movzx   eax, word ptr [rbp+48h]
0x10043990e  mov     ecx, eax
0x100439910  shr     eax, 8
0x100439913  shr     ecx, 0Ch
0x100439916  not     eax
0x100439918  not     ecx
0x10043991a  xor     ecx, eax
0x10043991c  test    cl, 1
0x10043991f  jz      loc_100439AC3
0x100439925  mov     r14d, esi
0x100439928  cmp     rbp, r15
0x10043992b  jz      loc_100439836
0x100439931  mov     rdx, [rbp+38h]
0x100439935  mov     rdi, [r15+38h]
0x100439939  test    rdx, rdx
0x10043993c  jz      loc_100439836
0x100439942  test    rdi, rdi
0x100439945  jz      loc_100439836
0x10043994b  mov     rax, [rdx+8]
0x10043994f  test    rax, rax
0x100439952  jz      short loc_100439979
0x100439954  mov     [rax+10h], rdi
0x100439958  lea     rcx, [r12+218h]
0x100439960  mov     [rdi+8], rax
0x100439964  call    ?Free@?$SQL_Memblock@VCVertexRef@CTessellator@@@@QEAAXPEAVCVertexRef@CTessellator@@@Z; SQL_Memblock<CTessellator::CVertexRef>::Free(CTessellator::CVertexRef *)
0x100439969  jmp     loc_100439AC3
0x10043996e  mov     r14d, 8007000Eh
0x100439974  jmp     loc_100439AC3
0x100439979  mov     rbx, [r12+150h]
0x100439981  test    rbx, rbx
0x100439984  jz      loc_100439836
0x10043998a  mov     ecx, 2600h
0x10043998f  nop
0x100439990  movzx   eax, word ptr [rbx+48h]
0x100439994  and     ax, cx
0x100439997  cmp     si, ax
0x10043999a  jz      short loc_1004399B0
0x10043999c  mov     rbx, [rbx+20h]
0x1004399a0  test    rbx, rbx
0x1004399a3  jnz     short loc_100439990
0x1004399a5  mov     r14d, 80131509h
0x1004399ab  jmp     loc_100439AC3
0x1004399b0  mov     rdx, [rbx+38h]
0x1004399b4  test    rdx, rdx
0x1004399b7  jz      short loc_1004399C6
0x1004399b9  lea     rcx, [r12+218h]
0x1004399c1  call    ?Free@?$SQL_Memblock@VCVertexRef@CTessellator@@@@QEAAXPEAVCVertexRef@CTessellator@@@Z; SQL_Memblock<CTessellator::CVertexRef>::Free(CTessellator::CVertexRef *)
0x1004399c6  mov     [rbx+38h], rdi
0x1004399ca  mov     [rdi+8], rsi
0x1004399ce  jmp     loc_100439AC3
0x1004399d3  mov     ebx, 2600h
0x1004399d8  movzx   eax, word ptr [rdi+48h]
0x1004399dc  mov     ecx, eax
0x1004399de  shr     eax, 8
0x1004399e1  shr     ecx, 0Ch
0x1004399e4  not     eax
0x1004399e6  not     ecx
0x1004399e8  xor     ecx, eax
0x1004399ea  test    cl, 1
0x1004399ed  jnz     short loc_1004399F7
0x1004399ef  mov     rsi, r13
0x1004399f2  jmp     loc_100439AAD
0x1004399f7  test    rbp, rbp
0x1004399fa  jz      short loc_100439A3A
0x1004399fc  mov     rax, [rbp+38h]
0x100439a00  mov     [rdi+38h], rax
0x100439a04  mov     [rbp+38h], rsi
0x100439a08  cmp     rdi, r13
0x100439a0b  jz      loc_100439AC3
0x100439a11  mov     rdi, [rdi+18h]
0x100439a15  test    rdi, rdi
0x100439a18  jz      short loc_100439A35
0x100439a1a  nop     word ptr [rax+rax+00h]
0x100439a20  movzx   eax, word ptr [rdi+48h]
0x100439a24  and     ax, bx
0x100439a27  cmp     si, ax
0x100439a2a  jz      short loc_100439A35
0x100439a2c  mov     rdi, [rdi+18h]
0x100439a30  test    rdi, rdi
0x100439a33  jnz     short loc_100439A20
0x100439a35  mov     rsi, r13
0x100439a38  jmp     short loc_100439AA8
0x100439a3a  mov     r8, r13; struct CScanner::CChain *
0x100439a3d  mov     rdx, rdi; struct CScanner::CChain *
0x100439a40  mov     rcx, r12; this
0x100439a43  call    ?SplitTheBand@CTessellator@@QEAAJPEAVCChain@CScanner@@0@Z; CTessellator::SplitTheBand(CScanner::CChain *,CScanner::CChain *)
0x100439a48  mov     r14d, eax
0x100439a4b  test    eax, eax
0x100439a4d  js      short loc_100439AC3
0x100439a4f  lfence
0x100439a52  mov     rdi, [rdi+18h]
0x100439a56  test    rdi, rdi
0x100439a59  jz      short loc_100439A75
0x100439a5b  nop     dword ptr [rax+rax+00h]
0x100439a60  movzx   ecx, word ptr [rdi+48h]
0x100439a64  and     cx, bx
0x100439a67  cmp     si, cx
0x100439a6a  jz      short loc_100439A75
0x100439a6c  mov     rdi, [rdi+18h]
0x100439a70  test    rdi, rdi
0x100439a73  jnz     short loc_100439A60
0x100439a75  cmp     rdi, r13
0x100439a78  jz      short loc_100439AA8
0x100439a7a  lfence
0x100439a7d  mov     rcx, [r13+20h]
0x100439a81  test    rcx, rcx
0x100439a84  jz      short loc_100439AA5
0x100439a86  nop     word ptr [rax+rax+00000000h]
0x100439a90  movzx   eax, word ptr [rcx+48h]
0x100439a94  and     ax, bx
0x100439a97  cmp     si, ax
0x100439a9a  jz      short loc_100439AA5
0x100439a9c  mov     rcx, [rcx+20h]
0x100439aa0  test    rcx, rcx
0x100439aa3  jnz     short loc_100439A90
0x100439aa5  mov     rsi, rcx
0x100439aa8  test    rdi, rdi
0x100439aab  jz      short loc_100439AC3
0x100439aad  test    rsi, rsi
0x100439ab0  jz      short loc_100439AC3
0x100439ab2  mov     r8, rsi; struct CScanner::CChain *
0x100439ab5  mov     rdx, rdi; struct CScanner::CChain *
0x100439ab8  mov     rcx, r12; this
0x100439abb  call    ?CreateBands@CTessellator@@QEAAJPEAVCChain@CScanner@@0@Z; CTessellator::CreateBands(CScanner::CChain *,CScanner::CChain *)
0x100439ac0  mov     r14d, eax
0x100439ac3  mov     rbx, [rsp+48h+arg_8]
0x100439ac8  mov     eax, r14d
0x100439acb  mov     rbp, [rsp+48h+arg_10]
0x100439ad0  mov     rsi, [rsp+48h+arg_18]
0x100439ad5  add     rsp, 20h
0x100439ad9  pop     r15
0x100439adb  pop     r14
0x100439add  pop     r13
0x100439adf  pop     r12
0x100439ae1  pop     rdi
0x100439ae2  retn
```
