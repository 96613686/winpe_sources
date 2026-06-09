# HGetFeatureAttribute

- ea: `0x180029918`
- end: `0x180029d69`
- name: `HGetFeatureAttribute`
- size: `1105`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, void *, int, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180021ba0`
- `0x18002c5b0`

## callees

- `0x180029918`
- `0x18002ab58`
- `0x18002abf8`
- `0x18002fac0`
- `0x18005c434`

## string_xrefs

- `0x180029c0f`: `OpenUIType`
- `0x180029c67`: `OpenGroupType`

## pseudocode

```c
__int64 __fastcall HGetFeatureAttribute(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int8 *a4,
        _DWORD *a5,
        void *a6,
        unsigned int a7,
        _DWORD *a8)
{
  __int64 v10; // rbp
  __int64 v11; // rdi
  unsigned int *KeywordMatchFeature; // rdx
  unsigned int v13; // eax
  _DWORD *v14; // rcx
  unsigned int v15; // r8d
  unsigned int v16; // eax
  _BYTE *v17; // rsi
  char **v18; // r14
  signed int v19; // ebp
  int v20; // r13d
  int v21; // r15d
  char *v22; // rdx
  __int64 v23; // r12
  unsigned int v24; // r12d
  char *v25; // rdx
  __int64 v26; // r12
  unsigned int v27; // r12d
  unsigned __int8 *v29; // rax
  int v30; // r9d
  int v31; // r8d
  __int64 v32; // rdi
  char *v33; // r8
  int v34; // ecx
  int v35; // eax
  unsigned int v36; // eax
  _DWORD *v37; // r8
  __int64 v38; // rdi
  unsigned __int8 *v39; // rax
  int v40; // r10d
  int v41; // r9d
  __int64 v42; // rax
  __int64 v43; // rdi
  unsigned __int8 *v44; // rax
  int v45; // r10d
  int v46; // r9d
  __int64 v47; // rdi
  unsigned __int8 *v48; // rax
  int v49; // r9d
  int v50; // r8d
  char *v51; // r8
  int v52; // edx
  int v53; // eax
  int v54; // [rsp+98h] [rbp+10h] BYREF

  v54 = 0;
  if ( *(_DWORD *)(a1 + 56) )
    v10 = a1 + *(unsigned int *)(a1 + 56);
  else
    v10 = 0;
  if ( *(_DWORD *)(a1 + 60) )
    v11 = a1 + *(unsigned int *)(a1 + 60);
  else
    v11 = 0;
  if ( !v10 || !v11 )
    return 2147500037LL;
  if ( !a3 )
    return 2147942487LL;
  KeywordMatchFeature = (unsigned int *)PInternalGetKeywordMatchFeature(v10, a3, 0, &v54);
  if ( !KeywordMatchFeature )
    return 2147942487LL;
  v13 = *(_DWORD *)(v11 + 200);
  if ( v13 && (v14 = (_DWORD *)(a1 + v13)) != 0 && (v15 = *(_DWORD *)(v11 + 196), v16 = 0, v15) )
  {
    while ( v14[1] == 8 || v14[3] != v54 || v14[4] != 255 )
    {
      ++v16;
      v14 += 6;
      if ( v16 >= v15 )
        goto LABEL_18;
    }
  }
  else
  {
LABEL_18:
    v14 = 0;
  }
  if ( a4 )
  {
    if ( *a4 == 68 )
    {
      v29 = a4;
      do
      {
        v30 = v29["DisplayName" - (char *)a4];
        v31 = *v29 - v30;
        if ( v31 )
          break;
        ++v29;
      }
      while ( v30 );
      if ( !v31 )
      {
        if ( KeywordMatchFeature[3] )
        {
          v14 = (_DWORD *)(a1 + KeywordMatchFeature[3]);
          if ( v14 )
          {
            v32 = -1;
            do
              ++v32;
            while ( *((_WORD *)v14 + v32) );
            return HGetSingleData(v14, a6, a7, (__int64)a8);
          }
        }
        return 2147500037LL;
      }
      v33 = (char *)("DefaultOption" - (char *)a4);
      do
      {
        v34 = (unsigned __int8)v33[(_QWORD)a4];
        v35 = *a4 - v34;
        if ( v35 )
          break;
        ++a4;
      }
      while ( v34 );
      if ( !v35 )
      {
        v36 = KeywordMatchFeature[5];
        if ( v36 < KeywordMatchFeature[13]
          && (v37 = (_DWORD *)(*(_QWORD *)(v10 + 328) + KeywordMatchFeature[14] + KeywordMatchFeature[12] * v36)) != 0
          || KeywordMatchFeature[13] && (v37 = (_DWORD *)(*(_QWORD *)(v10 + 328) + KeywordMatchFeature[14])) != 0 )
        {
          if ( *v37 )
            v14 = (_DWORD *)(a1 + (unsigned int)*v37);
          else
            v14 = 0;
          v38 = -1;
          do
            ++v38;
          while ( *((_BYTE *)v14 + v38) );
          return HGetSingleData(v14, a6, a7, (__int64)a8);
        }
        return 2147500037LL;
      }
    }
    else if ( *a4 == 79 )
    {
      v39 = a4;
      do
      {
        v40 = v39["OpenUIType" - (char *)a4];
        v41 = *v39 - v40;
        if ( v41 )
          break;
        ++v39;
      }
      while ( v40 );
      if ( !v41 )
      {
        v42 = 0;
        if ( KeywordMatchFeature[8] <= 2 )
          v42 = KeywordMatchFeature[8];
        v14 = (_DWORD *)(0x180000000LL + 10 * v42 + 414872);
        v43 = -1;
        do
          ++v43;
        while ( *((_BYTE *)v14 + v43) );
        return HGetSingleData(v14, a6, a7, (__int64)a8);
      }
      v44 = a4;
      do
      {
        v45 = v44["OpenGroupType" - (char *)a4];
        v46 = *v44 - v45;
        if ( v46 )
          break;
        ++v44;
      }
      while ( v45 );
      if ( !v46 )
      {
        v14 = (_DWORD *)(0x180000000LL + (KeywordMatchFeature[11] != 2 ? 414838LL : 414808LL));
        v47 = -1;
        do
          ++v47;
        while ( *((_BYTE *)v14 + v47) );
        return HGetSingleData(v14, a6, a7, (__int64)a8);
      }
      v48 = a4;
      do
      {
        v49 = v48["OrderDependencyValue" - (char *)a4];
        v50 = *v48 - v49;
        if ( v50 )
          break;
        ++v48;
      }
      while ( v49 );
      if ( v50 )
      {
        v51 = (char *)("OrderDependencySection" - (char *)a4);
        do
        {
          v52 = (unsigned __int8)v51[(_QWORD)a4];
          v53 = *a4 - v52;
          if ( v53 )
            break;
          ++a4;
        }
        while ( v52 );
        if ( !v53 && v14 )
          return HGetOrderDepSection(v14, a5, a6, a7, a8);
      }
      else if ( v14 )
      {
        return HGetSingleData(v14, a6, a7, (__int64)a8);
      }
    }
    return 2147942487LL;
  }
  if ( a5 )
    *a5 = 5;
  v17 = a6;
  v18 = &off_18005FC90;
  v19 = a7;
  v20 = 0;
  v21 = 6;
  if ( v14 )
  {
    do
    {
      v25 = *v18;
      v26 = -1;
      do
        ++v26;
      while ( v25[v26] );
      v27 = v26 + 1;
      if ( v17 && v19 >= (int)v27 )
      {
        memcpy_0(v17, v25, v27);
        v17 += v27;
      }
      v19 -= v27;
      v20 += v27;
      v18 += 2;
      --v21;
    }
    while ( v21 );
  }
  else
  {
    do
    {
      if ( !*((_DWORD *)v18 + 2) )
      {
        v22 = *v18;
        v23 = -1;
        do
          ++v23;
        while ( v22[v23] );
        v24 = v23 + 1;
        if ( v17 && v19 >= (int)v24 )
        {
          memcpy_0(v17, v22, v24);
          v17 += v24;
        }
        v19 -= v24;
        v20 += v24;
      }
      v18 += 2;
      --v21;
    }
    while ( v21 );
  }
  if ( a8 )
    *a8 = v20 + 1;
  if ( !v17 || v19 - 1 < 0 )
    return 2147942414LL;
  *v17 = 0;
  return 0;
}

```

## disassembly

```asm
0x180029918  mov     [rsp+arg_8], edx
0x18002991c  mov     r11, rsp
0x18002991f  push    rbx
0x180029920  push    rbp
0x180029921  push    rsi
0x180029922  push    rdi
0x180029923  push    r12
0x180029925  push    r13
0x180029927  push    r14
0x180029929  push    r15
0x18002992b  sub     rsp, 48h
0x18002992f  xor     r12d, r12d
0x180029932  mov     rbx, r9
0x180029935  mov     rax, r8
0x180029938  mov     rsi, rcx
0x18002993b  mov     [r11+10h], r12d
0x18002993f  cmp     [rcx+38h], r12d
0x180029943  jz      short loc_18002994D
0x180029945  mov     ebp, [rcx+38h]
0x180029948  add     rbp, rcx
0x18002994b  jmp     short loc_180029950
0x18002994d  mov     rbp, r12
0x180029950  cmp     [rcx+3Ch], r12d
0x180029954  jz      short loc_18002995E
0x180029956  mov     edi, [rcx+3Ch]
0x180029959  add     rdi, rsi
0x18002995c  jmp     short loc_180029961
0x18002995e  mov     rdi, r12
0x180029961  test    rbp, rbp
0x180029964  jz      loc_180029D53
0x18002996a  test    rdi, rdi
0x18002996d  jz      loc_180029D53
0x180029973  test    rax, rax
0x180029976  jz      loc_180029D4C
0x18002997c  lea     r9, [rsp+88h+arg_8]
0x180029984  xor     r8d, r8d
0x180029987  mov     rdx, rax
0x18002998a  mov     rcx, rbp
0x18002998d  call    PInternalGetKeywordMatchFeature
0x180029992  mov     rdx, rax
0x180029995  test    rax, rax
0x180029998  jz      loc_180029D4C
0x18002999e  mov     eax, [rdi+0C8h]
0x1800299a4  test    eax, eax
0x1800299a6  jz      short loc_1800299E6
0x1800299a8  mov     ecx, eax
0x1800299aa  add     rcx, rsi
0x1800299ad  jz      short loc_1800299E6
0x1800299af  mov     r8d, [rdi+0C4h]
0x1800299b6  mov     eax, r12d
0x1800299b9  test    r8d, r8d
0x1800299bc  jz      short loc_1800299E6
0x1800299be  mov     r9d, [rsp+88h+arg_8]
0x1800299c6  cmp     dword ptr [rcx+4], 8
0x1800299ca  jz      short loc_1800299DB
0x1800299cc  cmp     [rcx+0Ch], r9d
0x1800299d0  jnz     short loc_1800299DB
0x1800299d2  cmp     dword ptr [rcx+10h], 0FFh
0x1800299d9  jz      short loc_1800299E9
0x1800299db  inc     eax
0x1800299dd  add     rcx, 18h
0x1800299e1  cmp     eax, r8d
0x1800299e4  jb      short loc_1800299C6
0x1800299e6  mov     rcx, r12
0x1800299e9  test    rbx, rbx
0x1800299ec  jnz     loc_180029AE7
0x1800299f2  mov     rax, [rsp+88h+arg_20]
0x1800299fa  test    rax, rax
0x1800299fd  jz      short loc_180029A05
0x1800299ff  mov     dword ptr [rax], 5
0x180029a05  mov     rsi, [rsp+88h+arg_28]
0x180029a0d  lea     r14, off_18005FC90; "DisplayName"
0x180029a14  mov     ebp, [rsp+88h+arg_30]
0x180029a1b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180029a1f  mov     r13d, r12d
0x180029a22  mov     r15d, 6
0x180029a28  test    rcx, rcx
0x180029a2b  jnz     short loc_180029A76
0x180029a2d  cmp     [r14+8], r12d
0x180029a31  jnz     short loc_180029A6A
0x180029a33  mov     rdx, [r14]; Src
0x180029a36  mov     r12, rdi
0x180029a39  inc     r12
0x180029a3c  cmp     byte ptr [rdx+r12], 0
0x180029a41  jnz     short loc_180029A39
0x180029a43  inc     r12d
0x180029a46  test    rsi, rsi
0x180029a49  jz      short loc_180029A61
0x180029a4b  cmp     ebp, r12d
0x180029a4e  jl      short loc_180029A61
0x180029a50  mov     r8d, r12d; Size
0x180029a53  mov     rcx, rsi; void *
0x180029a56  mov     ebx, r12d
0x180029a59  call    memcpy_0
0x180029a5e  add     rsi, rbx
0x180029a61  sub     ebp, r12d
0x180029a64  add     r13d, r12d
0x180029a67  xor     r12d, r12d
0x180029a6a  add     r14, 10h
0x180029a6e  add     r15d, 0FFFFFFFFh
0x180029a72  jnz     short loc_180029A2D
0x180029a74  jmp     short loc_180029AB4
0x180029a76  mov     rdx, [r14]; Src
0x180029a79  mov     r12, rdi
0x180029a7c  inc     r12
0x180029a7f  cmp     byte ptr [rdx+r12], 0
0x180029a84  jnz     short loc_180029A7C
0x180029a86  inc     r12d
0x180029a89  test    rsi, rsi
0x180029a8c  jz      short loc_180029AA4
0x180029a8e  cmp     ebp, r12d
0x180029a91  jl      short loc_180029AA4
0x180029a93  mov     r8d, r12d; Size
0x180029a96  mov     rcx, rsi; void *
0x180029a99  mov     ebx, r12d
0x180029a9c  call    memcpy_0
0x180029aa1  add     rsi, rbx
0x180029aa4  sub     ebp, r12d
0x180029aa7  add     r13d, r12d
0x180029aaa  add     r14, 10h
0x180029aae  add     r15d, 0FFFFFFFFh
0x180029ab2  jnz     short loc_180029A76
0x180029ab4  mov     rcx, [rsp+88h+arg_38]
0x180029abc  test    rcx, rcx
0x180029abf  jz      short loc_180029AC7
0x180029ac1  lea     eax, [r13+1]
0x180029ac5  mov     [rcx], eax
0x180029ac7  test    rsi, rsi
0x180029aca  jz      short loc_180029ADD
0x180029acc  lea     eax, [rbp-1]
0x180029acf  test    eax, eax
0x180029ad1  js      short loc_180029ADD
0x180029ad3  mov     byte ptr [rsi], 0
0x180029ad6  xor     eax, eax
0x180029ad8  jmp     loc_180029D58
0x180029add  mov     eax, 8007000Eh
0x180029ae2  jmp     loc_180029D58
0x180029ae7  cmp     byte ptr [rbx], 44h ; 'D'
0x180029aea  jnz     loc_180029C06
0x180029af0  lea     rcx, kstrDisplayName; "DisplayName"
0x180029af7  mov     rax, rbx
0x180029afa  sub     rcx, rbx
0x180029afd  movzx   r8d, byte ptr [rax]
0x180029b01  movzx   r9d, byte ptr [rax+rcx]
0x180029b06  sub     r8d, r9d
0x180029b09  jnz     short loc_180029B13
0x180029b0b  inc     rax
0x180029b0e  test    r9d, r9d
0x180029b11  jnz     short loc_180029AFD
0x180029b13  test    r8d, r8d
0x180029b16  jnz     short loc_180029B80
0x180029b18  cmp     [rdx+0Ch], r12d
0x180029b1c  jz      loc_180029D53
0x180029b22  mov     ecx, [rdx+0Ch]
0x180029b25  add     rcx, rsi; Src
0x180029b28  jz      loc_180029D53
0x180029b2e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180029b32  inc     rdi
0x180029b35  cmp     [rcx+rdi*2], r12w
0x180029b3a  jnz     short loc_180029B32
0x180029b3c  lea     r8d, ds:2[rdi*2]
0x180029b44  mov     edx, 6
0x180029b49  mov     rax, [rsp+88h+arg_38]
0x180029b51  mov     r9, [rsp+88h+arg_20]
0x180029b59  mov     [rsp+88h+var_58], rax; __int64
0x180029b5e  mov     eax, [rsp+88h+arg_30]
0x180029b65  mov     [rsp+88h+var_60], eax; int
0x180029b69  mov     rax, [rsp+88h+arg_28]
0x180029b71  mov     [rsp+88h+var_68], rax; void *
0x180029b76  call    HGetSingleData
0x180029b7b  jmp     loc_180029D58
0x180029b80  lea     r8, kstrDefOption; "DefaultOption"
0x180029b87  sub     r8, rbx
0x180029b8a  movzx   eax, byte ptr [rbx]
0x180029b8d  movzx   ecx, byte ptr [rbx+r8]
0x180029b92  sub     eax, ecx
0x180029b94  jnz     short loc_180029B9D
0x180029b96  inc     rbx
0x180029b99  test    ecx, ecx
0x180029b9b  jnz     short loc_180029B8A
0x180029b9d  test    eax, eax
0x180029b9f  jnz     loc_180029D4C
0x180029ba5  mov     eax, [rdx+14h]
0x180029ba8  cmp     eax, [rdx+34h]
0x180029bab  jnb     short loc_180029BC0
0x180029bad  imul    eax, [rdx+30h]
0x180029bb1  add     eax, [rdx+38h]
0x180029bb4  mov     r8d, eax
0x180029bb7  add     r8, [rbp+148h]
0x180029bbe  jnz     short loc_180029BDB
0x180029bc0  cmp     [rdx+34h], r12d
0x180029bc4  jbe     loc_180029D53
0x180029bca  mov     r8d, [rdx+38h]
0x180029bce  add     r8, [rbp+148h]
0x180029bd5  jz      loc_180029D53
0x180029bdb  cmp     [r8], r12d
0x180029bde  jz      short loc_180029BE8
0x180029be0  mov     ecx, [r8]
0x180029be3  add     rcx, rsi
0x180029be6  jmp     short loc_180029BEB
0x180029be8  mov     rcx, r12
0x180029beb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180029bef  inc     rdi
0x180029bf2  cmp     [rcx+rdi], r12b
0x180029bf6  jnz     short loc_180029BEF
0x180029bf8  lea     r8d, [rdi+1]
0x180029bfc  mov     edx, 5
0x180029c01  jmp     loc_180029B49
0x180029c06  cmp     byte ptr [rbx], 4Fh ; 'O'
0x180029c09  jnz     loc_180029D4C
0x180029c0f  lea     r8, kstrOpenUIType; "OpenUIType"
0x180029c16  mov     rax, rbx
0x180029c19  sub     r8, rbx
0x180029c1c  movzx   r9d, byte ptr [rax]
0x180029c20  movzx   r10d, byte ptr [rax+r8]
0x180029c25  sub     r9d, r10d
0x180029c28  jnz     short loc_180029C32
0x180029c2a  inc     rax
0x180029c2d  test    r10d, r10d
0x180029c30  jnz     short loc_180029C1C
0x180029c32  test    r9d, r9d
0x180029c35  jnz     short loc_180029C67
0x180029c37  cmp     dword ptr [rdx+20h], 2
0x180029c3b  mov     eax, r12d
0x180029c3e  cmovbe  eax, [rdx+20h]
0x180029c42  lea     rcx, [rax+rax*4]
0x180029c46  lea     rcx, ds:65498h[rcx*2]
0x180029c4e  lea     rax, cs:180000000h
0x180029c55  add     rcx, rax
0x180029c58  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180029c5c  inc     rdi
0x180029c5f  cmp     [rcx+rdi], r12b
0x180029c63  jnz     short loc_180029C5C
0x180029c65  jmp     short loc_180029BF8
0x180029c67  lea     r8, kstrOpenGroupType; "OpenGroupType"
0x180029c6e  mov     rax, rbx
0x180029c71  sub     r8, rbx
0x180029c74  movzx   r9d, byte ptr [rax]
0x180029c78  movzx   r10d, byte ptr [rax+r8]
0x180029c7d  sub     r9d, r10d
0x180029c80  jnz     short loc_180029C8A
0x180029c82  inc     rax
0x180029c85  test    r10d, r10d
0x180029c88  jnz     short loc_180029C74
0x180029c8a  test    r9d, r9d
0x180029c8d  jnz     short loc_180029CC0
0x180029c8f  mov     eax, [rdx+2Ch]
0x180029c92  sub     eax, 2
0x180029c95  neg     eax
0x180029c97  lea     rax, cs:180000000h
0x180029c9e  sbb     rcx, rcx
0x180029ca1  and     ecx, 1Eh
0x180029ca4  lea     rcx, [rcx+65458h]
0x180029cab  add     rcx, rax
0x180029cae  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180029cb2  inc     rdi
0x180029cb5  cmp     [rcx+rdi], r12b
0x180029cb9  jnz     short loc_180029CB2
0x180029cbb  jmp     loc_180029BF8
0x180029cc0  lea     rdx, kstrOrderDepValue; "OrderDependencyValue"
0x180029cc7  mov     rax, rbx
0x180029cca  sub     rdx, rbx
0x180029ccd  movzx   r8d, byte ptr [rax]
0x180029cd1  movzx   r9d, byte ptr [rax+rdx]
0x180029cd6  sub     r8d, r9d
0x180029cd9  jnz     short loc_180029CE3
0x180029cdb  inc     rax
0x180029cde  test    r9d, r9d
0x180029ce1  jnz     short loc_180029CCD
0x180029ce3  test    r8d, r8d
0x180029ce6  jnz     short loc_180029CFA
0x180029ce8  test    rcx, rcx
0x180029ceb  jz      short loc_180029D4C
0x180029ced  lea     edx, [r8+3]
0x180029cf1  lea     r8d, [rdx+1]
0x180029cf5  jmp     loc_180029B49
0x180029cfa  lea     r8, kstrOrderDepSect; "OrderDependencySection"
0x180029d01  sub     r8, rbx
0x180029d04  movzx   eax, byte ptr [rbx]
0x180029d07  movzx   edx, byte ptr [rbx+r8]
0x180029d0c  sub     eax, edx
0x180029d0e  jnz     short loc_180029D17
0x180029d10  inc     rbx
0x180029d13  test    edx, edx
0x180029d15  jnz     short loc_180029D04
0x180029d17  test    eax, eax
0x180029d19  jnz     short loc_180029D4C
0x180029d1b  test    rcx, rcx
0x180029d1e  jz      short loc_180029D4C
0x180029d20  mov     rax, [rsp+88h+arg_38]
0x180029d28  mov     r9d, [rsp+88h+arg_30]
0x180029d30  mov     r8, [rsp+88h+arg_28]
0x180029d38  mov     rdx, [rsp+88h+arg_20]
0x180029d40  mov     [rsp+88h+var_68], rax
0x180029d45  call    HGetOrderDepSection
0x180029d4a  jmp     short loc_180029D58
0x180029d4c  mov     eax, 80070057h
0x180029d51  jmp     short loc_180029D58
0x180029d53  mov     eax, 80004005h
0x180029d58  add     rsp, 48h
  ... truncated ...
```
