# PCreateFeatureItem

- ea: `0x18005b0e4`
- end: `0x18005b2bd`
- name: `PCreateFeatureItem`
- size: `473`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180058d70`
- `0x180058e00`
- `0x180058e30`
- `0x1800596e0`
- `0x180059ef0`
- `0x18005b448`

## callees

- `0x18005a54c`
- `0x18005b0e4`
- `0x18005b3a4`

## pseudocode

```c
__int64 __fastcall PCreateFeatureItem(__int64 a1, int a2)
{
  int v2; // r8d
  char v5; // al
  char v6; // cl
  char *v7; // rdx
  char *v8; // rcx
  signed __int64 v9; // r10
  int v10; // r9d
  int v11; // eax
  __int64 v12; // rbp
  __int64 ListItem; // rbx
  __int128 v14; // xmm6
  __int64 v15; // rax
  int v16; // eax

  v2 = 0;
  if ( a2 == 0xFFFF )
  {
    v5 = *(_BYTE *)(a1 + 692);
    if ( v5 == 42 )
      v6 = *(_BYTE *)(a1 + 693);
    else
      v6 = *(_BYTE *)(a1 + 692);
    v7 = (char *)((a1 + 693LL - (v5 != 42)) & -(__int64)(v6 != 0));
    if ( !v7 )
      return 0;
    if ( off_1800720B0 )
    {
      do
      {
        v8 = (&off_1800720B0)[2 * v2];
        v9 = v7 - v8;
        do
        {
          v10 = (unsigned __int8)v8[v9];
          v11 = (unsigned __int8)*v8 - v10;
          if ( v11 )
            break;
          ++v8;
        }
        while ( v10 );
        if ( !v11 )
          break;
        ++v2;
      }
      while ( (&off_1800720B0)[2 * v2] );
    }
    if ( (&off_1800720B0)[2 * v2] )
      *(_BYTE *)(LODWORD((&off_1800720B0)[2 * v2 + 1]) + a1 + 540) = 1;
  }
  else
  {
    if ( off_1800720B0 )
    {
      do
      {
        if ( a2 == LODWORD((&off_1800720B0)[2 * v2 + 1]) )
          break;
        ++v2;
      }
      while ( (&off_1800720B0)[2 * v2] );
    }
    v7 = (&off_1800720B0)[2 * v2];
    if ( !v7 )
      return 0;
  }
  v12 = 2LL * v2;
  if ( LODWORD((&off_1800720B0)[2 * v2 + 1]) == 0xFFFF || (ListItem = *(_QWORD *)(a1 + 152)) == 0 )
  {
LABEL_22:
    v14 = *(_OWORD *)(a1 + 576);
    *(_QWORD *)(a1 + 584) = v7;
    v15 = -1;
    do
      ++v15;
    while ( v7[v15] );
    *(_DWORD *)(a1 + 580) = v15;
    ListItem = PvCreateListItem(a1, a1 + 152, 96);
    *(_OWORD *)(a1 + 576) = v14;
    if ( !ListItem )
      return ListItem;
  }
  else
  {
    while ( *(_DWORD *)(ListItem + 48) != LODWORD((&off_1800720B0)[2 * v2 + 1]) )
    {
      ListItem = *(_QWORD *)ListItem;
      if ( !ListItem )
        goto LABEL_22;
    }
  }
  if ( a2 != 0xFFFF
    || !*(_DWORD *)(a1 + 596)
    || *(_QWORD *)(ListItem + 32)
    || !(unsigned int)IParseXlation(a1, ListItem + 24) )
  {
    if ( !*(_DWORD *)(ListItem + 84) )
    {
      *(_DWORD *)(ListItem + 84) = *((_DWORD *)&off_1800720B0 + 2 * v12 + 3);
      v16 = (int)(&off_1800720B0)[v12 + 1];
      *(_DWORD *)(ListItem + 48) = v16;
      if ( v16 == 6 || v16 == 0xFFFF && *(_DWORD *)(a1 + 60) )
        *(_DWORD *)(ListItem + 52) = 1;
    }
    return ListItem;
  }
  return 0;
}

```

## disassembly

```asm
0x18005b0e4  push    rbx
0x18005b0e6  push    rbp
0x18005b0e7  push    rsi
0x18005b0e8  push    rdi
0x18005b0e9  push    r12
0x18005b0eb  push    r14
0x18005b0ed  sub     rsp, 38h
0x18005b0f1  xor     r8d, r8d
0x18005b0f4  movaps  [rsp+68h+var_48], xmm6
0x18005b0f9  mov     r12d, 0FFFFh
0x18005b0ff  mov     r14d, edx
0x18005b102  mov     rsi, rcx
0x18005b105  cmp     edx, r12d
0x18005b108  jnz     loc_18005B1A4
0x18005b10e  mov     al, [rcx+2B4h]
0x18005b114  cmp     al, 2Ah ; '*'
0x18005b116  jnz     short loc_18005B120
0x18005b118  mov     cl, [rcx+2B5h]
0x18005b11e  jmp     short loc_18005B122
0x18005b120  mov     cl, al
0x18005b122  sub     al, 2Ah ; '*'
0x18005b124  neg     al
0x18005b126  sbb     rax, rax
0x18005b129  add     rax, 2B5h
0x18005b12f  add     rax, rsi
0x18005b132  neg     cl
0x18005b134  sbb     rdx, rdx
0x18005b137  and     rdx, rax
0x18005b13a  jz      loc_18005B2A9
0x18005b140  cmp     cs:off_1800720B0, r8; "PageSize"
0x18005b147  lea     rdi, off_1800720B0; "PageSize"
0x18005b14e  jz      short loc_18005B189
0x18005b150  movsxd  rax, r8d
0x18005b153  mov     r10, rdx
0x18005b156  add     rax, rax
0x18005b159  mov     rcx, [rdi+rax*8]
0x18005b15d  sub     r10, rcx
0x18005b160  movzx   eax, byte ptr [rcx]
0x18005b163  movzx   r9d, byte ptr [rcx+r10]
0x18005b168  sub     eax, r9d
0x18005b16b  jnz     short loc_18005B175
0x18005b16d  inc     rcx
0x18005b170  test    r9d, r9d
0x18005b173  jnz     short loc_18005B160
0x18005b175  test    eax, eax
0x18005b177  jz      short loc_18005B189
0x18005b179  inc     r8d
0x18005b17c  movsxd  rax, r8d
0x18005b17f  add     rax, rax
0x18005b182  cmp     qword ptr [rdi+rax*8], 0
0x18005b187  jnz     short loc_18005B150
0x18005b189  movsxd  rax, r8d
0x18005b18c  add     rax, rax
0x18005b18f  cmp     qword ptr [rdi+rax*8], 0
0x18005b194  jz      short loc_18005B1E4
0x18005b196  mov     eax, [rdi+rax*8+8]
0x18005b19a  mov     byte ptr [rax+rsi+21Ch], 1
0x18005b1a2  jmp     short loc_18005B1E4
0x18005b1a4  cmp     cs:off_1800720B0, r8; "PageSize"
0x18005b1ab  lea     rdi, off_1800720B0; "PageSize"
0x18005b1b2  jz      short loc_18005B1D1
0x18005b1b4  movsxd  rax, r8d
0x18005b1b7  add     rax, rax
0x18005b1ba  cmp     r14d, [rdi+rax*8+8]
0x18005b1bf  jz      short loc_18005B1D1
0x18005b1c1  inc     r8d
0x18005b1c4  movsxd  rax, r8d
0x18005b1c7  add     rax, rax
0x18005b1ca  cmp     qword ptr [rdi+rax*8], 0
0x18005b1cf  jnz     short loc_18005B1B4
0x18005b1d1  movsxd  rax, r8d
0x18005b1d4  add     rax, rax
0x18005b1d7  mov     rdx, [rdi+rax*8]
0x18005b1db  test    rdx, rdx
0x18005b1de  jz      loc_18005B2A9
0x18005b1e4  movsxd  rbp, r8d
0x18005b1e7  add     rbp, rbp
0x18005b1ea  cmp     [rdi+rbp*8+8], r12d
0x18005b1ef  jz      short loc_18005B20E
0x18005b1f1  mov     rbx, [rsi+98h]
0x18005b1f8  test    rbx, rbx
0x18005b1fb  jz      short loc_18005B20E
0x18005b1fd  mov     eax, [rdi+rbp*8+8]
0x18005b201  cmp     [rbx+30h], eax
0x18005b204  jz      short loc_18005B254
0x18005b206  mov     rbx, [rbx]
0x18005b209  test    rbx, rbx
0x18005b20c  jnz     short loc_18005B201
0x18005b20e  movups  xmm6, xmmword ptr [rsi+240h]
0x18005b215  mov     [rsi+248h], rdx
0x18005b21c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005b220  inc     rax
0x18005b223  cmp     byte ptr [rdx+rax], 0
0x18005b227  jnz     short loc_18005B220
0x18005b229  lea     rdx, [rsi+98h]
0x18005b230  mov     [rsi+244h], eax
0x18005b236  mov     r8d, 60h ; '`'
0x18005b23c  mov     rcx, rsi
0x18005b23f  call    PvCreateListItem
0x18005b244  mov     rbx, rax
0x18005b247  movdqu  xmmword ptr [rsi+240h], xmm6
0x18005b24f  test    rax, rax
0x18005b252  jz      short loc_18005B2A4
0x18005b254  cmp     r14d, r12d
0x18005b257  jnz     short loc_18005B279
0x18005b259  cmp     dword ptr [rsi+254h], 0
0x18005b260  jz      short loc_18005B279
0x18005b262  cmp     qword ptr [rbx+20h], 0
0x18005b267  jnz     short loc_18005B279
0x18005b269  lea     rdx, [rbx+18h]
0x18005b26d  mov     rcx, rsi
0x18005b270  call    IParseXlation
0x18005b275  test    eax, eax
0x18005b277  jnz     short loc_18005B2A9
0x18005b279  cmp     dword ptr [rbx+54h], 0
0x18005b27d  jnz     short loc_18005B2A4
0x18005b27f  mov     eax, [rdi+rbp*8+0Ch]
0x18005b283  mov     [rbx+54h], eax
0x18005b286  mov     eax, [rdi+rbp*8+8]
0x18005b28a  mov     [rbx+30h], eax
0x18005b28d  cmp     eax, 6
0x18005b290  jz      short loc_18005B29D
0x18005b292  cmp     eax, r12d
0x18005b295  jnz     short loc_18005B2A4
0x18005b297  cmp     dword ptr [rsi+3Ch], 0
0x18005b29b  jz      short loc_18005B2A4
0x18005b29d  mov     dword ptr [rbx+34h], 1
0x18005b2a4  mov     rax, rbx
0x18005b2a7  jmp     short loc_18005B2AB
0x18005b2a9  xor     eax, eax
0x18005b2ab  movaps  xmm6, [rsp+68h+var_48]
0x18005b2b0  add     rsp, 38h
0x18005b2b4  pop     r14
0x18005b2b6  pop     r12
0x18005b2b8  pop     rdi
0x18005b2b9  pop     rsi
0x18005b2ba  pop     rbp
0x18005b2bb  pop     rbx
0x18005b2bc  retn
```
