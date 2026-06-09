# CProgramCfg_Read

- ea: `0x18005d730`
- end: `0x18005dbe1`
- name: `CProgramCfg_Read`
- size: `1201`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18003dd44`

## callees

- `0x18003e3ec`
- `0x18004dd14`
- `0x18005d094`
- `0x18005d730`

## pseudocode

```c
__int64 __fastcall CProgramCfg_Read(_BYTE *a1, unsigned int *a2)
{
  unsigned int v4; // eax
  char v5; // al
  char v6; // al
  char v7; // al
  __int16 v8; // si
  __int64 v9; // rbp
  __int16 v10; // si
  __int64 v11; // rbp
  __int16 v12; // si
  __int64 v13; // rbp
  __int16 v14; // si
  __int64 v15; // rax
  __int16 v16; // si
  __int64 v17; // rax
  __int16 v18; // si
  __int64 v19; // rbp
  unsigned int v20; // ecx
  unsigned int v21; // eax
  __int16 v22; // si
  unsigned int v23; // eax

  if ( !a1 || !a2 )
    return 2147942487LL;
  memset_0(a1, 0, 0xB1u);
  if ( *a2 < 4 )
    FillBitCache(a2, 4);
  v4 = a2[1];
  *a2 -= 4;
  *a1 = (v4 >> *a2) & 0xF;
  if ( *a2 < 2 )
    FillBitCache(a2, 2);
  *a2 -= 2;
  a1[1] = (a2[1] >> *a2) & 3;
  if ( *a2 < 4 )
    FillBitCache(a2, 4);
  *a2 -= 4;
  a1[2] = (a2[1] >> *a2) & 0xF;
  if ( *a2 < 4 )
    FillBitCache(a2, 4);
  *a2 -= 4;
  a1[3] = (a2[1] >> *a2) & 0xF;
  if ( *a2 < 4 )
    FillBitCache(a2, 4);
  *a2 -= 4;
  a1[4] = (a2[1] >> *a2) & 0xF;
  if ( *a2 < 4 )
    FillBitCache(a2, 4);
  *a2 -= 4;
  a1[5] = (a2[1] >> *a2) & 0xF;
  if ( *a2 < 2 )
    FillBitCache(a2, 2);
  *a2 -= 2;
  a1[6] = (a2[1] >> *a2) & 3;
  if ( *a2 < 3 )
    FillBitCache(a2, 3);
  *a2 -= 3;
  a1[7] = (a2[1] >> *a2) & 7;
  if ( *a2 < 4 )
    FillBitCache(a2, 4);
  *a2 -= 4;
  a1[8] = (a2[1] >> *a2) & 0xF;
  if ( !*a2 )
    FillBitCache(a2, 1);
  v5 = (a2[1] >> --*a2) & 1;
  a1[9] = v5;
  if ( v5 )
  {
    if ( *a2 < 4 )
      FillBitCache(a2, 4);
    *a2 -= 4;
    a1[10] = (a2[1] >> *a2) & 0xF;
  }
  if ( !*a2 )
    FillBitCache(a2, 1);
  v6 = (a2[1] >> --*a2) & 1;
  a1[11] = v6;
  if ( v6 )
  {
    if ( *a2 < 4 )
      FillBitCache(a2, 4);
    *a2 -= 4;
    a1[12] = (a2[1] >> *a2) & 0xF;
  }
  if ( !*a2 )
    FillBitCache(a2, 1);
  v7 = (a2[1] >> --*a2) & 1;
  a1[13] = v7;
  if ( v7 )
  {
    if ( *a2 < 2 )
      FillBitCache(a2, 2);
    *a2 -= 2;
    a1[14] = (a2[1] >> *a2) & 3;
    if ( !*a2 )
      FillBitCache(a2, 1);
    a1[15] = (a2[1] >> --*a2) & 1;
  }
  v8 = 0;
  if ( a1[3] )
  {
    do
    {
      if ( !*a2 )
        FillBitCache(a2, 1);
      --*a2;
      v9 = v8;
      a1[v8 + 16] = (a2[1] >> *a2) & 1;
      if ( *a2 < 4 )
        FillBitCache(a2, 4);
      *a2 -= 4;
      ++v8;
      a1[v9 + 32] = (a2[1] >> *a2) & 0xF;
    }
    while ( v8 < (unsigned __int8)a1[3] );
  }
  v10 = 0;
  if ( a1[4] )
  {
    do
    {
      if ( !*a2 )
        FillBitCache(a2, 1);
      --*a2;
      v11 = v10;
      a1[v10 + 48] = (a2[1] >> *a2) & 1;
      if ( *a2 < 4 )
        FillBitCache(a2, 4);
      *a2 -= 4;
      ++v10;
      a1[v11 + 64] = (a2[1] >> *a2) & 0xF;
    }
    while ( v10 < (unsigned __int8)a1[4] );
  }
  v12 = 0;
  if ( a1[5] )
  {
    do
    {
      if ( !*a2 )
        FillBitCache(a2, 1);
      --*a2;
      v13 = v12;
      a1[v12 + 80] = (a2[1] >> *a2) & 1;
      if ( *a2 < 4 )
        FillBitCache(a2, 4);
      *a2 -= 4;
      ++v12;
      a1[v13 + 96] = (a2[1] >> *a2) & 0xF;
    }
    while ( v12 < (unsigned __int8)a1[5] );
  }
  v14 = 0;
  if ( a1[6] )
  {
    do
    {
      if ( *a2 < 4 )
        FillBitCache(a2, 4);
      *a2 -= 4;
      v15 = v14++;
      a1[v15 + 112] = (a2[1] >> *a2) & 0xF;
    }
    while ( v14 < (unsigned __int8)a1[6] );
  }
  v16 = 0;
  if ( a1[7] )
  {
    do
    {
      if ( *a2 < 4 )
        FillBitCache(a2, 4);
      *a2 -= 4;
      v17 = v16++;
      a1[v17 + 128] = (a2[1] >> *a2) & 0xF;
    }
    while ( v16 < (unsigned __int8)a1[7] );
  }
  v18 = 0;
  if ( a1[8] )
  {
    do
    {
      if ( !*a2 )
        FillBitCache(a2, 1);
      --*a2;
      v19 = v18;
      a1[v18 + 144] = (a2[1] >> *a2) & 1;
      if ( *a2 < 4 )
        FillBitCache(a2, 4);
      *a2 -= 4;
      ++v18;
      a1[v19 + 160] = (a2[1] >> *a2) & 0xF;
    }
    while ( v18 < (unsigned __int8)a1[8] );
  }
  v20 = a2[10];
  v21 = *a2;
  if ( v20 )
    SkipBitBufBits(a2, ((_BYTE)v21 + (_BYTE)v20) & 7);
  else
    *a2 = v21 & 0xFFFFFFF8;
  if ( *a2 < 8 )
    FillBitCache(a2, 8);
  *a2 -= 8;
  v22 = 0;
  v23 = a2[1] >> *a2;
  a1[176] = v23;
  if ( (_BYTE)v23 )
  {
    do
    {
      if ( *a2 < 8 )
        FillBitCache(a2, 8);
      *a2 -= 8;
      ++v22;
    }
    while ( v22 < (unsigned __int8)a1[176] );
  }
  return 0;
}

```

## disassembly

```asm
0x18005d730  push    rbx
0x18005d732  push    rbp
0x18005d733  push    rsi
0x18005d734  push    rdi
0x18005d735  push    r13
0x18005d737  push    r14
0x18005d739  push    r15
0x18005d73b  sub     rsp, 20h
0x18005d73f  mov     rbx, rdx
0x18005d742  mov     rdi, rcx
0x18005d745  test    rcx, rcx
0x18005d748  jz      loc_18005DBCC
0x18005d74e  test    rdx, rdx
0x18005d751  jz      loc_18005DBCC
0x18005d757  xor     edx, edx; Val
0x18005d759  mov     r8d, 0B1h; Size
0x18005d75f  call    memset_0
0x18005d764  mov     r14d, 4
0x18005d76a  cmp     [rbx], r14d
0x18005d76d  jnb     short loc_18005D77A
0x18005d76f  mov     edx, r14d
0x18005d772  mov     rcx, rbx
0x18005d775  call    FillBitCache
0x18005d77a  mov     eax, [rbx+4]
0x18005d77d  mov     r13d, 0FFFFFFFCh
0x18005d783  add     [rbx], r13d
0x18005d786  mov     r15b, 0Fh
0x18005d789  mov     ecx, [rbx]
0x18005d78b  mov     esi, 2
0x18005d790  shr     eax, cl
0x18005d792  and     al, r15b
0x18005d795  mov     [rdi], al
0x18005d797  cmp     [rbx], esi
0x18005d799  jnb     short loc_18005D7A5
0x18005d79b  mov     edx, esi
0x18005d79d  mov     rcx, rbx
0x18005d7a0  call    FillBitCache
0x18005d7a5  add     dword ptr [rbx], 0FFFFFFFEh
0x18005d7a8  mov     ebp, 3
0x18005d7ad  mov     eax, [rbx+4]
0x18005d7b0  mov     ecx, [rbx]
0x18005d7b2  shr     eax, cl
0x18005d7b4  and     al, bpl
0x18005d7b7  mov     [rdi+1], al
0x18005d7ba  cmp     [rbx], r14d
0x18005d7bd  jnb     short loc_18005D7CA
0x18005d7bf  mov     edx, r14d
0x18005d7c2  mov     rcx, rbx
0x18005d7c5  call    FillBitCache
0x18005d7ca  add     [rbx], r13d
0x18005d7cd  mov     eax, [rbx+4]
0x18005d7d0  mov     ecx, [rbx]
0x18005d7d2  shr     eax, cl
0x18005d7d4  and     al, r15b
0x18005d7d7  mov     [rdi+2], al
0x18005d7da  cmp     [rbx], r14d
0x18005d7dd  jnb     short loc_18005D7EA
0x18005d7df  mov     edx, r14d
0x18005d7e2  mov     rcx, rbx
0x18005d7e5  call    FillBitCache
0x18005d7ea  add     [rbx], r13d
0x18005d7ed  mov     eax, [rbx+4]
0x18005d7f0  mov     ecx, [rbx]
0x18005d7f2  shr     eax, cl
0x18005d7f4  and     al, r15b
0x18005d7f7  mov     [rdi+3], al
0x18005d7fa  cmp     [rbx], r14d
0x18005d7fd  jnb     short loc_18005D80A
0x18005d7ff  mov     edx, r14d
0x18005d802  mov     rcx, rbx
0x18005d805  call    FillBitCache
0x18005d80a  add     [rbx], r13d
0x18005d80d  mov     eax, [rbx+4]
0x18005d810  mov     ecx, [rbx]
0x18005d812  shr     eax, cl
0x18005d814  and     al, r15b
0x18005d817  mov     [rdi+4], al
0x18005d81a  cmp     [rbx], r14d
0x18005d81d  jnb     short loc_18005D82A
0x18005d81f  mov     edx, r14d
0x18005d822  mov     rcx, rbx
0x18005d825  call    FillBitCache
0x18005d82a  add     [rbx], r13d
0x18005d82d  mov     eax, [rbx+4]
0x18005d830  mov     ecx, [rbx]
0x18005d832  shr     eax, cl
0x18005d834  and     al, r15b
0x18005d837  mov     [rdi+5], al
0x18005d83a  cmp     [rbx], esi
0x18005d83c  jnb     short loc_18005D848
0x18005d83e  mov     edx, esi
0x18005d840  mov     rcx, rbx
0x18005d843  call    FillBitCache
0x18005d848  add     dword ptr [rbx], 0FFFFFFFEh
0x18005d84b  mov     eax, [rbx+4]
0x18005d84e  mov     ecx, [rbx]
0x18005d850  shr     eax, cl
0x18005d852  and     al, bpl
0x18005d855  mov     [rdi+6], al
0x18005d858  cmp     [rbx], ebp
0x18005d85a  jnb     short loc_18005D866
0x18005d85c  mov     edx, ebp
0x18005d85e  mov     rcx, rbx
0x18005d861  call    FillBitCache
0x18005d866  add     dword ptr [rbx], 0FFFFFFFDh
0x18005d869  mov     eax, [rbx+4]
0x18005d86c  mov     ecx, [rbx]
0x18005d86e  shr     eax, cl
0x18005d870  and     al, 7
0x18005d872  mov     [rdi+7], al
0x18005d875  cmp     [rbx], r14d
0x18005d878  jnb     short loc_18005D885
0x18005d87a  mov     edx, r14d
0x18005d87d  mov     rcx, rbx
0x18005d880  call    FillBitCache
0x18005d885  add     [rbx], r13d
0x18005d888  mov     eax, [rbx+4]
0x18005d88b  mov     ecx, [rbx]
0x18005d88d  shr     eax, cl
0x18005d88f  and     al, r15b
0x18005d892  mov     r15d, 1
0x18005d898  mov     [rdi+8], al
0x18005d89b  cmp     [rbx], r15d
0x18005d89e  jnb     short loc_18005D8AB
0x18005d8a0  mov     edx, r15d
0x18005d8a3  mov     rcx, rbx
0x18005d8a6  call    FillBitCache
0x18005d8ab  dec     dword ptr [rbx]
0x18005d8ad  mov     eax, [rbx+4]
0x18005d8b0  mov     ecx, [rbx]
0x18005d8b2  shr     eax, cl
0x18005d8b4  and     al, r15b
0x18005d8b7  mov     [rdi+9], al
0x18005d8ba  jz      short loc_18005D8DB
0x18005d8bc  cmp     [rbx], r14d
0x18005d8bf  jnb     short loc_18005D8CC
0x18005d8c1  mov     edx, r14d
0x18005d8c4  mov     rcx, rbx
0x18005d8c7  call    FillBitCache
0x18005d8cc  add     [rbx], r13d
0x18005d8cf  mov     eax, [rbx+4]
0x18005d8d2  mov     ecx, [rbx]
0x18005d8d4  shr     eax, cl
0x18005d8d6  and     al, 0Fh
0x18005d8d8  mov     [rdi+0Ah], al
0x18005d8db  cmp     [rbx], r15d
0x18005d8de  jnb     short loc_18005D8EB
0x18005d8e0  mov     edx, r15d
0x18005d8e3  mov     rcx, rbx
0x18005d8e6  call    FillBitCache
0x18005d8eb  dec     dword ptr [rbx]
0x18005d8ed  mov     eax, [rbx+4]
0x18005d8f0  mov     ecx, [rbx]
0x18005d8f2  shr     eax, cl
0x18005d8f4  and     al, r15b
0x18005d8f7  mov     [rdi+0Bh], al
0x18005d8fa  jz      short loc_18005D91B
0x18005d8fc  cmp     [rbx], r14d
0x18005d8ff  jnb     short loc_18005D90C
0x18005d901  mov     edx, r14d
0x18005d904  mov     rcx, rbx
0x18005d907  call    FillBitCache
0x18005d90c  add     [rbx], r13d
0x18005d90f  mov     eax, [rbx+4]
0x18005d912  mov     ecx, [rbx]
0x18005d914  shr     eax, cl
0x18005d916  and     al, 0Fh
0x18005d918  mov     [rdi+0Ch], al
0x18005d91b  cmp     [rbx], r15d
0x18005d91e  jnb     short loc_18005D92B
0x18005d920  mov     edx, r15d
0x18005d923  mov     rcx, rbx
0x18005d926  call    FillBitCache
0x18005d92b  dec     dword ptr [rbx]
0x18005d92d  mov     eax, [rbx+4]
0x18005d930  mov     ecx, [rbx]
0x18005d932  shr     eax, cl
0x18005d934  and     al, r15b
0x18005d937  mov     [rdi+0Dh], al
0x18005d93a  jz      short loc_18005D979
0x18005d93c  cmp     [rbx], esi
0x18005d93e  jnb     short loc_18005D94A
0x18005d940  mov     edx, esi
0x18005d942  mov     rcx, rbx
0x18005d945  call    FillBitCache
0x18005d94a  add     dword ptr [rbx], 0FFFFFFFEh
0x18005d94d  mov     eax, [rbx+4]
0x18005d950  mov     ecx, [rbx]
0x18005d952  shr     eax, cl
0x18005d954  and     al, bpl
0x18005d957  mov     [rdi+0Eh], al
0x18005d95a  cmp     [rbx], r15d
0x18005d95d  jnb     short loc_18005D96A
0x18005d95f  mov     edx, r15d
0x18005d962  mov     rcx, rbx
0x18005d965  call    FillBitCache
0x18005d96a  dec     dword ptr [rbx]
0x18005d96c  mov     eax, [rbx+4]
0x18005d96f  mov     ecx, [rbx]
0x18005d971  shr     eax, cl
0x18005d973  and     al, r15b
0x18005d976  mov     [rdi+0Fh], al
0x18005d979  xor     esi, esi
0x18005d97b  cmp     [rdi+3], sil
0x18005d97f  jbe     short loc_18005D9D2
0x18005d981  cmp     [rbx], r15d
0x18005d984  jnb     short loc_18005D991
0x18005d986  mov     edx, r15d
0x18005d989  mov     rcx, rbx
0x18005d98c  call    FillBitCache
0x18005d991  dec     dword ptr [rbx]
0x18005d993  mov     eax, [rbx+4]
0x18005d996  mov     ecx, [rbx]
0x18005d998  shr     eax, cl
0x18005d99a  and     al, r15b
0x18005d99d  movsx   rbp, si
0x18005d9a1  mov     [rdi+rbp+10h], al
0x18005d9a5  cmp     [rbx], r14d
0x18005d9a8  jnb     short loc_18005D9B5
0x18005d9aa  mov     edx, r14d
0x18005d9ad  mov     rcx, rbx
0x18005d9b0  call    FillBitCache
0x18005d9b5  add     [rbx], r13d
0x18005d9b8  add     si, r15w
0x18005d9bc  mov     ecx, [rbx]
0x18005d9be  mov     eax, [rbx+4]
0x18005d9c1  shr     eax, cl
0x18005d9c3  and     al, 0Fh
0x18005d9c5  mov     [rdi+rbp+20h], al
0x18005d9c9  movzx   ecx, byte ptr [rdi+3]
0x18005d9cd  cmp     si, cx
0x18005d9d0  jl      short loc_18005D981
0x18005d9d2  xor     esi, esi
0x18005d9d4  cmp     [rdi+4], sil
0x18005d9d8  jbe     short loc_18005DA2B
0x18005d9da  cmp     [rbx], r15d
0x18005d9dd  jnb     short loc_18005D9EA
0x18005d9df  mov     edx, r15d
0x18005d9e2  mov     rcx, rbx
0x18005d9e5  call    FillBitCache
0x18005d9ea  dec     dword ptr [rbx]
0x18005d9ec  mov     eax, [rbx+4]
0x18005d9ef  mov     ecx, [rbx]
0x18005d9f1  shr     eax, cl
0x18005d9f3  and     al, r15b
0x18005d9f6  movsx   rbp, si
0x18005d9fa  mov     [rdi+rbp+30h], al
0x18005d9fe  cmp     [rbx], r14d
0x18005da01  jnb     short loc_18005DA0E
0x18005da03  mov     edx, r14d
0x18005da06  mov     rcx, rbx
0x18005da09  call    FillBitCache
0x18005da0e  add     [rbx], r13d
0x18005da11  add     si, r15w
0x18005da15  mov     ecx, [rbx]
0x18005da17  mov     eax, [rbx+4]
0x18005da1a  shr     eax, cl
0x18005da1c  and     al, 0Fh
0x18005da1e  mov     [rdi+rbp+40h], al
0x18005da22  movzx   ecx, byte ptr [rdi+4]
0x18005da26  cmp     si, cx
0x18005da29  jl      short loc_18005D9DA
0x18005da2b  xor     esi, esi
0x18005da2d  cmp     [rdi+5], sil
0x18005da31  jbe     short loc_18005DA84
0x18005da33  cmp     [rbx], r15d
0x18005da36  jnb     short loc_18005DA43
0x18005da38  mov     edx, r15d
0x18005da3b  mov     rcx, rbx
0x18005da3e  call    FillBitCache
0x18005da43  dec     dword ptr [rbx]
0x18005da45  mov     eax, [rbx+4]
0x18005da48  mov     ecx, [rbx]
0x18005da4a  shr     eax, cl
0x18005da4c  and     al, r15b
0x18005da4f  movsx   rbp, si
0x18005da53  mov     [rdi+rbp+50h], al
0x18005da57  cmp     [rbx], r14d
0x18005da5a  jnb     short loc_18005DA67
0x18005da5c  mov     edx, r14d
0x18005da5f  mov     rcx, rbx
0x18005da62  call    FillBitCache
0x18005da67  add     [rbx], r13d
0x18005da6a  add     si, r15w
0x18005da6e  mov     ecx, [rbx]
0x18005da70  mov     eax, [rbx+4]
0x18005da73  shr     eax, cl
0x18005da75  and     al, 0Fh
0x18005da77  mov     [rdi+rbp+60h], al
0x18005da7b  movzx   ecx, byte ptr [rdi+5]
0x18005da7f  cmp     si, cx
0x18005da82  jl      short loc_18005DA33
0x18005da84  xor     esi, esi
0x18005da86  cmp     [rdi+6], sil
0x18005da8a  jbe     short loc_18005DABE
0x18005da8c  cmp     [rbx], r14d
0x18005da8f  jnb     short loc_18005DA9C
0x18005da91  mov     edx, r14d
0x18005da94  mov     rcx, rbx
0x18005da97  call    FillBitCache
  ... truncated ...
```
