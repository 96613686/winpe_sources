# CProgramCfg_Read

- ea: `0x180037930`
- end: `0x180037e0c`
- name: `CProgramCfg_Read`
- size: `1244`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800371b0`
- `0x180074560`

## callees

- `0x1800021a8`
- `0x1800363f0`
- `0x1800364b0`
- `0x180037930`

## pseudocode

```c
__int64 __fastcall CProgramCfg_Read(_BYTE *a1, int *a2)
{
  char v4; // al
  char v5; // al
  char v6; // al
  __int16 v7; // bp
  __int64 v8; // rsi
  __int16 v9; // si
  __int64 v10; // rbp
  __int16 v11; // si
  __int64 v12; // rbp
  __int16 v13; // si
  __int64 v14; // rax
  __int16 v15; // si
  __int64 v16; // rax
  __int16 v17; // si
  __int64 v18; // rbp
  __int16 v19; // si
  unsigned int v20; // eax

  if ( !a1 || !a2 )
    return 2147942487LL;
  memset_0(a1, 0, 0xB1u);
  if ( (unsigned int)*a2 < 4 )
    FillBitCache(a2, 4u);
  *a2 -= 4;
  *a1 = ((unsigned int)a2[1] >> *a2) & 0xF;
  if ( (unsigned int)*a2 < 2 )
    FillBitCache(a2, 2u);
  *a2 -= 2;
  a1[1] = ((unsigned int)a2[1] >> *a2) & 3;
  if ( (unsigned int)*a2 < 4 )
    FillBitCache(a2, 4u);
  *a2 -= 4;
  a1[2] = ((unsigned int)a2[1] >> *a2) & 0xF;
  if ( (unsigned int)*a2 < 4 )
    FillBitCache(a2, 4u);
  *a2 -= 4;
  a1[3] = ((unsigned int)a2[1] >> *a2) & 0xF;
  if ( (unsigned int)*a2 < 4 )
    FillBitCache(a2, 4u);
  *a2 -= 4;
  a1[4] = ((unsigned int)a2[1] >> *a2) & 0xF;
  if ( (unsigned int)*a2 < 4 )
    FillBitCache(a2, 4u);
  *a2 -= 4;
  a1[5] = ((unsigned int)a2[1] >> *a2) & 0xF;
  if ( (unsigned int)*a2 < 2 )
    FillBitCache(a2, 2u);
  *a2 -= 2;
  a1[6] = ((unsigned int)a2[1] >> *a2) & 3;
  if ( (unsigned int)*a2 < 3 )
    FillBitCache(a2, 3u);
  *a2 -= 3;
  a1[7] = ((unsigned int)a2[1] >> *a2) & 7;
  if ( (unsigned int)*a2 < 4 )
    FillBitCache(a2, 4u);
  *a2 -= 4;
  a1[8] = ((unsigned int)a2[1] >> *a2) & 0xF;
  if ( !*a2 )
    FillBitCache(a2, 1u);
  v4 = ((unsigned int)a2[1] >> --*a2) & 1;
  a1[9] = v4;
  if ( v4 )
  {
    if ( (unsigned int)*a2 < 4 )
      FillBitCache(a2, 4u);
    *a2 -= 4;
    a1[10] = ((unsigned int)a2[1] >> *a2) & 0xF;
  }
  if ( !*a2 )
    FillBitCache(a2, 1u);
  v5 = ((unsigned int)a2[1] >> --*a2) & 1;
  a1[11] = v5;
  if ( v5 )
  {
    if ( (unsigned int)*a2 < 4 )
      FillBitCache(a2, 4u);
    *a2 -= 4;
    a1[12] = ((unsigned int)a2[1] >> *a2) & 0xF;
  }
  if ( !*a2 )
    FillBitCache(a2, 1u);
  v6 = ((unsigned int)a2[1] >> --*a2) & 1;
  a1[13] = v6;
  if ( v6 )
  {
    if ( (unsigned int)*a2 < 2 )
      FillBitCache(a2, 2u);
    *a2 -= 2;
    a1[14] = ((unsigned int)a2[1] >> *a2) & 3;
    if ( !*a2 )
      FillBitCache(a2, 1u);
    a1[15] = ((unsigned int)a2[1] >> --*a2) & 1;
  }
  v7 = 0;
  if ( a1[3] )
  {
    do
    {
      if ( !*a2 )
        FillBitCache(a2, 1u);
      --*a2;
      v8 = v7;
      a1[v7 + 16] = ((unsigned int)a2[1] >> *a2) & 1;
      if ( (unsigned int)*a2 < 4 )
        FillBitCache(a2, 4u);
      *a2 -= 4;
      ++v7;
      a1[v8 + 32] = ((unsigned int)a2[1] >> *a2) & 0xF;
    }
    while ( v7 < (unsigned __int8)a1[3] );
  }
  v9 = 0;
  if ( a1[4] )
  {
    do
    {
      if ( !*a2 )
        FillBitCache(a2, 1u);
      --*a2;
      v10 = v9;
      a1[v9 + 48] = ((unsigned int)a2[1] >> *a2) & 1;
      if ( (unsigned int)*a2 < 4 )
        FillBitCache(a2, 4u);
      *a2 -= 4;
      ++v9;
      a1[v10 + 64] = ((unsigned int)a2[1] >> *a2) & 0xF;
    }
    while ( v9 < (unsigned __int8)a1[4] );
  }
  v11 = 0;
  if ( a1[5] )
  {
    do
    {
      if ( !*a2 )
        FillBitCache(a2, 1u);
      --*a2;
      v12 = v11;
      a1[v11 + 80] = ((unsigned int)a2[1] >> *a2) & 1;
      if ( (unsigned int)*a2 < 4 )
        FillBitCache(a2, 4u);
      *a2 -= 4;
      ++v11;
      a1[v12 + 96] = ((unsigned int)a2[1] >> *a2) & 0xF;
    }
    while ( v11 < (unsigned __int8)a1[5] );
  }
  v13 = 0;
  if ( a1[6] )
  {
    do
    {
      if ( (unsigned int)*a2 < 4 )
        FillBitCache(a2, 4u);
      *a2 -= 4;
      v14 = v13++;
      a1[v14 + 112] = ((unsigned int)a2[1] >> *a2) & 0xF;
    }
    while ( v13 < (unsigned __int8)a1[6] );
  }
  v15 = 0;
  if ( a1[7] )
  {
    do
    {
      if ( (unsigned int)*a2 < 4 )
        FillBitCache(a2, 4u);
      *a2 -= 4;
      v16 = v15++;
      a1[v16 + 128] = ((unsigned int)a2[1] >> *a2) & 0xF;
    }
    while ( v15 < (unsigned __int8)a1[7] );
  }
  v17 = 0;
  if ( a1[8] )
  {
    do
    {
      if ( !*a2 )
        FillBitCache(a2, 1u);
      --*a2;
      v18 = v17;
      a1[v17 + 144] = ((unsigned int)a2[1] >> *a2) & 1;
      if ( (unsigned int)*a2 < 4 )
        FillBitCache(a2, 4u);
      *a2 -= 4;
      ++v17;
      a1[v18 + 160] = ((unsigned int)a2[1] >> *a2) & 0xF;
    }
    while ( v17 < (unsigned __int8)a1[8] );
  }
  if ( a2[10] )
    SkipBitBufBits(a2);
  else
    *a2 &= 0xFFFFFFF8;
  if ( (unsigned int)*a2 < 8 )
    FillBitCache(a2, 8u);
  *a2 -= 8;
  v19 = 0;
  v20 = (unsigned int)a2[1] >> *a2;
  a1[176] = v20;
  if ( (_BYTE)v20 )
  {
    do
    {
      if ( (unsigned int)*a2 < 8 )
        FillBitCache(a2, 8u);
      *a2 -= 8;
      ++v19;
    }
    while ( v19 < (unsigned __int8)a1[176] );
  }
  return 0;
}

```

## disassembly

```asm
0x180037930  mov     [rsp+arg_10], rbx
0x180037935  push    rdi
0x180037936  sub     rsp, 20h
0x18003793a  mov     rbx, rdx
0x18003793d  mov     rdi, rcx
0x180037940  test    rcx, rcx
0x180037943  jz      loc_180037DFB
0x180037949  test    rdx, rdx
0x18003794c  jz      loc_180037DFB
0x180037952  mov     [rsp+28h+arg_0], rbp
0x180037957  xor     edx, edx; Val
0x180037959  mov     r8d, 0B1h; Size
0x18003795f  mov     [rsp+28h+arg_8], rsi
0x180037964  call    memset_0
0x180037969  cmp     dword ptr [rbx], 4
0x18003796c  jnb     short loc_18003797B
0x18003796e  mov     edx, 4
0x180037973  mov     rcx, rbx
0x180037976  call    FillBitCache
0x18003797b  add     dword ptr [rbx], 0FFFFFFFCh
0x18003797e  mov     eax, [rbx+4]
0x180037981  mov     ecx, [rbx]
0x180037983  shr     eax, cl
0x180037985  and     al, 0Fh
0x180037987  mov     [rdi], al
0x180037989  cmp     dword ptr [rbx], 2
0x18003798c  jnb     short loc_18003799B
0x18003798e  mov     edx, 2
0x180037993  mov     rcx, rbx
0x180037996  call    FillBitCache
0x18003799b  add     dword ptr [rbx], 0FFFFFFFEh
0x18003799e  mov     eax, [rbx+4]
0x1800379a1  mov     ecx, [rbx]
0x1800379a3  shr     eax, cl
0x1800379a5  and     al, 3
0x1800379a7  mov     [rdi+1], al
0x1800379aa  cmp     dword ptr [rbx], 4
0x1800379ad  jnb     short loc_1800379BC
0x1800379af  mov     edx, 4
0x1800379b4  mov     rcx, rbx
0x1800379b7  call    FillBitCache
0x1800379bc  add     dword ptr [rbx], 0FFFFFFFCh
0x1800379bf  mov     eax, [rbx+4]
0x1800379c2  mov     ecx, [rbx]
0x1800379c4  shr     eax, cl
0x1800379c6  and     al, 0Fh
0x1800379c8  mov     [rdi+2], al
0x1800379cb  cmp     dword ptr [rbx], 4
0x1800379ce  jnb     short loc_1800379DD
0x1800379d0  mov     edx, 4
0x1800379d5  mov     rcx, rbx
0x1800379d8  call    FillBitCache
0x1800379dd  add     dword ptr [rbx], 0FFFFFFFCh
0x1800379e0  mov     eax, [rbx+4]
0x1800379e3  mov     ecx, [rbx]
0x1800379e5  shr     eax, cl
0x1800379e7  and     al, 0Fh
0x1800379e9  mov     [rdi+3], al
0x1800379ec  cmp     dword ptr [rbx], 4
0x1800379ef  jnb     short loc_1800379FE
0x1800379f1  mov     edx, 4
0x1800379f6  mov     rcx, rbx
0x1800379f9  call    FillBitCache
0x1800379fe  add     dword ptr [rbx], 0FFFFFFFCh
0x180037a01  mov     eax, [rbx+4]
0x180037a04  mov     ecx, [rbx]
0x180037a06  shr     eax, cl
0x180037a08  and     al, 0Fh
0x180037a0a  mov     [rdi+4], al
0x180037a0d  cmp     dword ptr [rbx], 4
0x180037a10  jnb     short loc_180037A1F
0x180037a12  mov     edx, 4
0x180037a17  mov     rcx, rbx
0x180037a1a  call    FillBitCache
0x180037a1f  add     dword ptr [rbx], 0FFFFFFFCh
0x180037a22  mov     eax, [rbx+4]
0x180037a25  mov     ecx, [rbx]
0x180037a27  shr     eax, cl
0x180037a29  and     al, 0Fh
0x180037a2b  mov     [rdi+5], al
0x180037a2e  cmp     dword ptr [rbx], 2
0x180037a31  jnb     short loc_180037A40
0x180037a33  mov     edx, 2
0x180037a38  mov     rcx, rbx
0x180037a3b  call    FillBitCache
0x180037a40  add     dword ptr [rbx], 0FFFFFFFEh
0x180037a43  mov     eax, [rbx+4]
0x180037a46  mov     ecx, [rbx]
0x180037a48  shr     eax, cl
0x180037a4a  and     al, 3
0x180037a4c  mov     [rdi+6], al
0x180037a4f  cmp     dword ptr [rbx], 3
0x180037a52  jnb     short loc_180037A61
0x180037a54  mov     edx, 3
0x180037a59  mov     rcx, rbx
0x180037a5c  call    FillBitCache
0x180037a61  add     dword ptr [rbx], 0FFFFFFFDh
0x180037a64  mov     eax, [rbx+4]
0x180037a67  mov     ecx, [rbx]
0x180037a69  shr     eax, cl
0x180037a6b  and     al, 7
0x180037a6d  mov     [rdi+7], al
0x180037a70  cmp     dword ptr [rbx], 4
0x180037a73  jnb     short loc_180037A82
0x180037a75  mov     edx, 4
0x180037a7a  mov     rcx, rbx
0x180037a7d  call    FillBitCache
0x180037a82  add     dword ptr [rbx], 0FFFFFFFCh
0x180037a85  mov     eax, [rbx+4]
0x180037a88  mov     ecx, [rbx]
0x180037a8a  shr     eax, cl
0x180037a8c  and     al, 0Fh
0x180037a8e  mov     [rdi+8], al
0x180037a91  cmp     dword ptr [rbx], 1
0x180037a94  jnb     short loc_180037AA3
0x180037a96  mov     edx, 1
0x180037a9b  mov     rcx, rbx
0x180037a9e  call    FillBitCache
0x180037aa3  dec     dword ptr [rbx]
0x180037aa5  mov     eax, [rbx+4]
0x180037aa8  mov     ecx, [rbx]
0x180037aaa  shr     eax, cl
0x180037aac  and     al, 1
0x180037aae  mov     [rdi+9], al
0x180037ab1  jz      short loc_180037AD4
0x180037ab3  cmp     dword ptr [rbx], 4
0x180037ab6  jnb     short loc_180037AC5
0x180037ab8  mov     edx, 4
0x180037abd  mov     rcx, rbx
0x180037ac0  call    FillBitCache
0x180037ac5  add     dword ptr [rbx], 0FFFFFFFCh
0x180037ac8  mov     eax, [rbx+4]
0x180037acb  mov     ecx, [rbx]
0x180037acd  shr     eax, cl
0x180037acf  and     al, 0Fh
0x180037ad1  mov     [rdi+0Ah], al
0x180037ad4  cmp     dword ptr [rbx], 1
0x180037ad7  jnb     short loc_180037AE6
0x180037ad9  mov     edx, 1
0x180037ade  mov     rcx, rbx
0x180037ae1  call    FillBitCache
0x180037ae6  dec     dword ptr [rbx]
0x180037ae8  mov     eax, [rbx+4]
0x180037aeb  mov     ecx, [rbx]
0x180037aed  shr     eax, cl
0x180037aef  and     al, 1
0x180037af1  mov     [rdi+0Bh], al
0x180037af4  jz      short loc_180037B17
0x180037af6  cmp     dword ptr [rbx], 4
0x180037af9  jnb     short loc_180037B08
0x180037afb  mov     edx, 4
0x180037b00  mov     rcx, rbx
0x180037b03  call    FillBitCache
0x180037b08  add     dword ptr [rbx], 0FFFFFFFCh
0x180037b0b  mov     eax, [rbx+4]
0x180037b0e  mov     ecx, [rbx]
0x180037b10  shr     eax, cl
0x180037b12  and     al, 0Fh
0x180037b14  mov     [rdi+0Ch], al
0x180037b17  cmp     dword ptr [rbx], 1
0x180037b1a  jnb     short loc_180037B29
0x180037b1c  mov     edx, 1
0x180037b21  mov     rcx, rbx
0x180037b24  call    FillBitCache
0x180037b29  dec     dword ptr [rbx]
0x180037b2b  mov     eax, [rbx+4]
0x180037b2e  mov     ecx, [rbx]
0x180037b30  shr     eax, cl
0x180037b32  and     al, 1
0x180037b34  mov     [rdi+0Dh], al
0x180037b37  jz      short loc_180037B7A
0x180037b39  cmp     dword ptr [rbx], 2
0x180037b3c  jnb     short loc_180037B4B
0x180037b3e  mov     edx, 2
0x180037b43  mov     rcx, rbx
0x180037b46  call    FillBitCache
0x180037b4b  add     dword ptr [rbx], 0FFFFFFFEh
0x180037b4e  mov     eax, [rbx+4]
0x180037b51  mov     ecx, [rbx]
0x180037b53  shr     eax, cl
0x180037b55  and     al, 3
0x180037b57  mov     [rdi+0Eh], al
0x180037b5a  cmp     dword ptr [rbx], 1
0x180037b5d  jnb     short loc_180037B6C
0x180037b5f  mov     edx, 1
0x180037b64  mov     rcx, rbx
0x180037b67  call    FillBitCache
0x180037b6c  dec     dword ptr [rbx]
0x180037b6e  mov     eax, [rbx+4]
0x180037b71  mov     ecx, [rbx]
0x180037b73  shr     eax, cl
0x180037b75  and     al, 1
0x180037b77  mov     [rdi+0Fh], al
0x180037b7a  xor     ebp, ebp
0x180037b7c  cmp     [rdi+3], bpl
0x180037b80  jbe     short loc_180037BD5
0x180037b82  cmp     dword ptr [rbx], 1
0x180037b85  jnb     short loc_180037B94
0x180037b87  mov     edx, 1
0x180037b8c  mov     rcx, rbx
0x180037b8f  call    FillBitCache
0x180037b94  dec     dword ptr [rbx]
0x180037b96  mov     eax, [rbx+4]
0x180037b99  mov     ecx, [rbx]
0x180037b9b  shr     eax, cl
0x180037b9d  and     al, 1
0x180037b9f  movsx   rsi, bp
0x180037ba3  mov     [rsi+rdi+10h], al
0x180037ba7  cmp     dword ptr [rbx], 4
0x180037baa  jnb     short loc_180037BB9
0x180037bac  mov     edx, 4
0x180037bb1  mov     rcx, rbx
0x180037bb4  call    FillBitCache
0x180037bb9  add     dword ptr [rbx], 0FFFFFFFCh
0x180037bbc  inc     bp
0x180037bbf  mov     eax, [rbx+4]
0x180037bc2  mov     ecx, [rbx]
0x180037bc4  shr     eax, cl
0x180037bc6  and     al, 0Fh
0x180037bc8  mov     [rsi+rdi+20h], al
0x180037bcc  movzx   eax, byte ptr [rdi+3]
0x180037bd0  cmp     bp, ax
0x180037bd3  jl      short loc_180037B82
0x180037bd5  xor     esi, esi
0x180037bd7  cmp     [rdi+4], sil
0x180037bdb  jbe     short loc_180037C33
0x180037bdd  nop     dword ptr [rax]
0x180037be0  cmp     dword ptr [rbx], 1
0x180037be3  jnb     short loc_180037BF2
0x180037be5  mov     edx, 1
0x180037bea  mov     rcx, rbx
0x180037bed  call    FillBitCache
0x180037bf2  dec     dword ptr [rbx]
0x180037bf4  mov     eax, [rbx+4]
0x180037bf7  mov     ecx, [rbx]
0x180037bf9  shr     eax, cl
0x180037bfb  and     al, 1
0x180037bfd  movsx   rbp, si
0x180037c01  mov     [rbp+rdi+30h], al
0x180037c05  cmp     dword ptr [rbx], 4
0x180037c08  jnb     short loc_180037C17
0x180037c0a  mov     edx, 4
0x180037c0f  mov     rcx, rbx
0x180037c12  call    FillBitCache
0x180037c17  add     dword ptr [rbx], 0FFFFFFFCh
0x180037c1a  inc     si
0x180037c1d  mov     eax, [rbx+4]
0x180037c20  mov     ecx, [rbx]
0x180037c22  shr     eax, cl
0x180037c24  and     al, 0Fh
0x180037c26  mov     [rbp+rdi+40h], al
0x180037c2a  movzx   eax, byte ptr [rdi+4]
0x180037c2e  cmp     si, ax
0x180037c31  jl      short loc_180037BE0
0x180037c33  xor     esi, esi
0x180037c35  cmp     [rdi+5], sil
0x180037c39  jbe     short loc_180037C93
0x180037c3b  nop     dword ptr [rax+rax+00h]
0x180037c40  cmp     dword ptr [rbx], 1
0x180037c43  jnb     short loc_180037C52
0x180037c45  mov     edx, 1
0x180037c4a  mov     rcx, rbx
0x180037c4d  call    FillBitCache
0x180037c52  dec     dword ptr [rbx]
0x180037c54  mov     eax, [rbx+4]
0x180037c57  mov     ecx, [rbx]
0x180037c59  shr     eax, cl
0x180037c5b  and     al, 1
0x180037c5d  movsx   rbp, si
0x180037c61  mov     [rbp+rdi+50h], al
0x180037c65  cmp     dword ptr [rbx], 4
0x180037c68  jnb     short loc_180037C77
0x180037c6a  mov     edx, 4
0x180037c6f  mov     rcx, rbx
0x180037c72  call    FillBitCache
0x180037c77  add     dword ptr [rbx], 0FFFFFFFCh
0x180037c7a  inc     si
0x180037c7d  mov     eax, [rbx+4]
0x180037c80  mov     ecx, [rbx]
0x180037c82  shr     eax, cl
0x180037c84  and     al, 0Fh
0x180037c86  mov     [rbp+rdi+60h], al
0x180037c8a  movzx   eax, byte ptr [rdi+5]
0x180037c8e  cmp     si, ax
0x180037c91  jl      short loc_180037C40
0x180037c93  xor     esi, esi
0x180037c95  cmp     [rdi+6], sil
0x180037c99  jbe     short loc_180037CD3
0x180037c9b  nop     dword ptr [rax+rax+00h]
0x180037ca0  cmp     dword ptr [rbx], 4
0x180037ca3  jnb     short loc_180037CB2
0x180037ca5  mov     edx, 4
0x180037caa  mov     rcx, rbx
0x180037cad  call    FillBitCache
0x180037cb2  add     dword ptr [rbx], 0FFFFFFFCh
0x180037cb5  mov     ecx, [rbx]
0x180037cb7  mov     edx, [rbx+4]
0x180037cba  shr     edx, cl
0x180037cbc  movsx   rax, si
0x180037cc0  and     dl, 0Fh
  ... truncated ...
```
