# drcDec_readLoudnessInfoSet(CDK_BITSTREAM *,LOUDNESS_INFO_SET *)

- ea: `0x180078174`
- end: `0x1800783f2`
- name: `?drcDec_readLoudnessInfoSet@@YA?AW4DRC_ERROR@@PEAUCDK_BITSTREAM@@PEAULOUDNESS_INFO_SET@@@Z`
- size: `638`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180070940`

## callees

- `0x1800110c0`
- `0x18004d320`
- `0x18004dd14`
- `0x180077174`
- `0x180077570`
- `0x180078174`
- `0x180096060`

## pseudocode

```c
__int64 __fastcall drcDec_readLoudnessInfoSet(_DWORD *a1, char *a2, __int64 a3)
{
  __int64 result; // rax
  unsigned int v6; // edi
  char v7; // al
  bool v8; // zf
  BOOL v9; // r14d
  __int64 v10; // r8
  unsigned __int8 v11; // al
  __int64 v12; // r8
  int v13; // r14d
  char v14; // cl
  int v15; // esi
  __int128 v16; // xmm1
  __int64 v17; // rcx
  int v18; // eax
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  char v24; // cl
  int v25; // esi
  __int128 v26; // xmm1
  __int64 v27; // rcx
  int v28; // eax
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  unsigned __int8 v34; // al
  __int128 Buf1; // [rsp+20h] [rbp-59h] BYREF
  __int128 v36; // [rsp+30h] [rbp-49h]
  __int128 v37; // [rsp+40h] [rbp-39h]
  __int128 v38; // [rsp+50h] [rbp-29h]
  __int128 v39; // [rsp+60h] [rbp-19h]
  __int128 v40; // [rsp+70h] [rbp-9h]
  __int128 v41; // [rsp+80h] [rbp+7h]
  int v42; // [rsp+90h] [rbp+17h]

  if ( !a2 )
    return 4294967196LL;
  v6 = 0;
  v7 = CDKreadBits(a1, 6, a3);
  v8 = *a2 == v7;
  *a2 = v7;
  v9 = !v8;
  v11 = CDKreadBits(a1, 6, v10);
  v8 = a2[3] == (char)v11;
  a2[3] = v11;
  v13 = !v8 || v9;
  v14 = 12;
  if ( (unsigned __int8)*a2 < 0xCu )
    v14 = *a2;
  v15 = 0;
  a2[2] = v14;
  while ( v15 < (unsigned __int8)*a2 )
  {
    memset_0(&Buf1, 0, 0x74u);
    result = readLoudnessInfo(a1, 0, &Buf1);
    v6 = result;
    if ( (_DWORD)result )
      return result;
    if ( v15 < 12 )
    {
      if ( !v13 )
        v13 = memcmp_0(&Buf1, &a2[116 * v15 + 8], 0x74u) != 0;
      v16 = v36;
      v17 = 116LL * v15;
      v18 = v42;
      *(_OWORD *)&a2[v17 + 8] = Buf1;
      v19 = v37;
      *(_OWORD *)&a2[v17 + 24] = v16;
      v20 = v38;
      *(_OWORD *)&a2[v17 + 40] = v19;
      v21 = v39;
      *(_OWORD *)&a2[v17 + 56] = v20;
      v22 = v40;
      *(_OWORD *)&a2[v17 + 72] = v21;
      v23 = v41;
      *(_OWORD *)&a2[v17 + 88] = v22;
      *(_OWORD *)&a2[v17 + 104] = v23;
      *(_DWORD *)&a2[v17 + 120] = v18;
    }
    ++v15;
  }
  v24 = 12;
  if ( (unsigned __int8)a2[3] < 0xCu )
    v24 = a2[3];
  v25 = 0;
  a2[5] = v24;
  while ( v25 < (unsigned __int8)a2[3] )
  {
    memset_0(&Buf1, 0, 0x74u);
    result = readLoudnessInfo(a1, 0, &Buf1);
    v6 = result;
    if ( (_DWORD)result )
      return result;
    if ( v25 < 12 )
    {
      if ( !v13 )
        v13 = memcmp_0(&Buf1, &a2[116 * v25 + 1400], 0x74u) != 0;
      v26 = v36;
      v27 = 116LL * v25;
      v28 = v42;
      *(_OWORD *)&a2[v27 + 1400] = Buf1;
      v29 = v37;
      *(_OWORD *)&a2[v27 + 1416] = v26;
      v30 = v38;
      *(_OWORD *)&a2[v27 + 1432] = v29;
      v31 = v39;
      *(_OWORD *)&a2[v27 + 1448] = v30;
      v32 = v40;
      *(_OWORD *)&a2[v27 + 1464] = v31;
      v33 = v41;
      *(_OWORD *)&a2[v27 + 1480] = v32;
      *(_OWORD *)&a2[v27 + 1496] = v33;
      *(_DWORD *)&a2[v27 + 1512] = v28;
    }
    ++v25;
  }
  v34 = CDKreadBits(a1, 1, v12);
  v8 = a2[2792] == (char)v34;
  a2[2792] = v34;
  a2[2832] = v13 | !v8;
  if ( !v34 )
    return v6;
  result = readLoudnessInfoSetExtension(a1, a2);
  v6 = result;
  if ( !(_DWORD)result )
    return v6;
  return result;
}

```

## disassembly

```asm
0x180078174  mov     [rsp-8+arg_10], rbx
0x180078179  mov     [rsp-8+arg_18], rsi
0x18007817e  push    rbp
0x18007817f  push    rdi
0x180078180  push    r13
0x180078182  push    r14
0x180078184  push    r15
0x180078186  lea     rbp, [rsp-37h]
0x18007818b  sub     rsp, 0B0h
0x180078192  mov     rax, cs:__security_cookie
0x180078199  xor     rax, rsp
0x18007819c  mov     [rbp+57h+var_30], rax
0x1800781a0  mov     rbx, rdx
0x1800781a3  mov     r15, rcx
0x1800781a6  test    rdx, rdx
0x1800781a9  jnz     short loc_1800781B3
0x1800781ab  lea     eax, [rdx-64h]
0x1800781ae  jmp     loc_1800783C9
0x1800781b3  xor     edi, edi
0x1800781b5  lea     esi, [rdi+6]
0x1800781b8  mov     edx, esi
0x1800781ba  call    CDKreadBits
0x1800781bf  xor     r14d, r14d
0x1800781c2  mov     edx, esi
0x1800781c4  cmp     [rbx], al
0x1800781c6  mov     rcx, r15
0x1800781c9  mov     [rbx], al
0x1800781cb  setnz   r14b
0x1800781cf  call    CDKreadBits
0x1800781d4  xor     ecx, ecx
0x1800781d6  lea     r13d, [rdi+74h]
0x1800781da  cmp     [rbx+3], al
0x1800781dd  mov     [rbx+3], al
0x1800781e0  movzx   eax, byte ptr [rbx]
0x1800781e3  setnz   cl
0x1800781e6  or      r14d, ecx
0x1800781e9  lea     ecx, [rdi+0Ch]
0x1800781ec  cmp     eax, ecx
0x1800781ee  cmovb   ecx, eax
0x1800781f1  xor     esi, esi
0x1800781f3  mov     [rbx+2], cl
0x1800781f6  movzx   eax, byte ptr [rbx]
0x1800781f9  cmp     esi, eax
0x1800781fb  jge     loc_1800782A5
0x180078201  mov     r8, r13; Size
0x180078204  lea     rcx, [rbp+57h+Buf1]; void *
0x180078208  xor     edx, edx; Val
0x18007820a  call    memset_0
0x18007820f  lea     r8, [rbp+57h+Buf1]
0x180078213  xor     edx, edx
0x180078215  mov     rcx, r15
0x180078218  call    _readLoudnessInfo
0x18007821d  mov     edi, eax
0x18007821f  test    eax, eax
0x180078221  jnz     loc_1800783C9
0x180078227  cmp     esi, 0Ch
0x18007822a  jge     short loc_18007829E
0x18007822c  test    r14d, r14d
0x18007822f  jnz     short loc_180078251
0x180078231  movsxd  rcx, esi
0x180078234  mov     r8, r13; Size
0x180078237  imul    rdx, rcx, 74h ; 't'
0x18007823b  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18007823f  add     rdx, 8
0x180078243  add     rdx, rbx; Buf2
0x180078246  call    memcmp_0
0x18007824b  test    eax, eax
0x18007824d  setnz   r14b
0x180078251  movaps  xmm0, [rbp+57h+Buf1]
0x180078255  movaps  xmm1, [rbp+57h+var_A0]
0x180078259  movsxd  rax, esi
0x18007825c  imul    rcx, rax, 74h ; 't'
0x180078260  mov     eax, [rbp+57h+var_40]
0x180078263  movups  xmmword ptr [rcx+rbx+8], xmm0
0x180078268  movaps  xmm0, [rbp+57h+var_90]
0x18007826c  movups  xmmword ptr [rcx+rbx+18h], xmm1
0x180078271  movaps  xmm1, [rbp+57h+var_80]
0x180078275  movups  xmmword ptr [rcx+rbx+28h], xmm0
0x18007827a  movaps  xmm0, [rbp+57h+var_70]
0x18007827e  movups  xmmword ptr [rcx+rbx+38h], xmm1
0x180078283  movaps  xmm1, [rbp+57h+var_60]
0x180078287  movups  xmmword ptr [rcx+rbx+48h], xmm0
0x18007828c  movaps  xmm0, [rbp+57h+var_50]
0x180078290  movups  xmmword ptr [rcx+rbx+58h], xmm1
0x180078295  movups  xmmword ptr [rcx+rbx+68h], xmm0
0x18007829a  mov     [rcx+rbx+78h], eax
0x18007829e  inc     esi
0x1800782a0  jmp     loc_1800781F6
0x1800782a5  movzx   eax, byte ptr [rbx+3]
0x1800782a9  mov     ecx, 0Ch
0x1800782ae  cmp     eax, ecx
0x1800782b0  cmovb   ecx, eax
0x1800782b3  xor     esi, esi
0x1800782b5  mov     [rbx+5], cl
0x1800782b8  movzx   eax, byte ptr [rbx+3]
0x1800782bc  cmp     esi, eax
0x1800782be  jge     loc_180078387
0x1800782c4  mov     r8, r13; Size
0x1800782c7  lea     rcx, [rbp+57h+Buf1]; void *
0x1800782cb  xor     edx, edx; Val
0x1800782cd  call    memset_0
0x1800782d2  lea     r8, [rbp+57h+Buf1]
0x1800782d6  xor     edx, edx
0x1800782d8  mov     rcx, r15
0x1800782db  call    _readLoudnessInfo
0x1800782e0  mov     edi, eax
0x1800782e2  test    eax, eax
0x1800782e4  jnz     loc_1800783C9
0x1800782ea  cmp     esi, 0Ch
0x1800782ed  jge     loc_180078380
0x1800782f3  test    r14d, r14d
0x1800782f6  jnz     short loc_18007831B
0x1800782f8  movsxd  rax, esi
0x1800782fb  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800782ff  imul    rdx, rax, 74h ; 't'
0x180078303  mov     r8, r13; Size
0x180078306  add     rdx, 578h
0x18007830d  add     rdx, rbx; Buf2
0x180078310  call    memcmp_0
0x180078315  test    eax, eax
0x180078317  setnz   r14b
0x18007831b  movaps  xmm0, [rbp+57h+Buf1]
0x18007831f  movaps  xmm1, [rbp+57h+var_A0]
0x180078323  movsxd  rax, esi
0x180078326  imul    rcx, rax, 74h ; 't'
0x18007832a  mov     eax, [rbp+57h+var_40]
0x18007832d  movups  xmmword ptr [rcx+rbx+578h], xmm0
0x180078335  movaps  xmm0, [rbp+57h+var_90]
0x180078339  movups  xmmword ptr [rcx+rbx+588h], xmm1
0x180078341  movaps  xmm1, [rbp+57h+var_80]
0x180078345  movups  xmmword ptr [rcx+rbx+598h], xmm0
0x18007834d  movaps  xmm0, [rbp+57h+var_70]
0x180078351  movups  xmmword ptr [rcx+rbx+5A8h], xmm1
0x180078359  movaps  xmm1, [rbp+57h+var_60]
0x18007835d  movups  xmmword ptr [rcx+rbx+5B8h], xmm0
0x180078365  movaps  xmm0, [rbp+57h+var_50]
0x180078369  movups  xmmword ptr [rcx+rbx+5C8h], xmm1
0x180078371  movups  xmmword ptr [rcx+rbx+5D8h], xmm0
0x180078379  mov     [rcx+rbx+5E8h], eax
0x180078380  inc     esi
0x180078382  jmp     loc_1800782B8
0x180078387  mov     edx, 1
0x18007838c  mov     rcx, r15
0x18007838f  call    CDKreadBits
0x180078394  mov     r8b, [rbx+0AE8h]
0x18007839b  cmp     r8b, al
0x18007839e  mov     [rbx+0AE8h], al
0x1800783a4  setnz   r8b
0x1800783a8  or      r8b, r14b
0x1800783ab  mov     [rbx+0B10h], r8b
0x1800783b2  test    al, al
0x1800783b4  jz      short loc_1800783C7
0x1800783b6  mov     rdx, rbx
0x1800783b9  mov     rcx, r15
0x1800783bc  call    _readLoudnessInfoSetExtension
0x1800783c1  mov     edi, eax
0x1800783c3  test    eax, eax
0x1800783c5  jnz     short loc_1800783C9
0x1800783c7  mov     eax, edi
0x1800783c9  mov     rcx, [rbp+57h+var_30]
0x1800783cd  xor     rcx, rsp; StackCookie
0x1800783d0  call    __security_check_cookie
0x1800783d5  lea     r11, [rsp+0D0h+var_20]
0x1800783dd  mov     rbx, [r11+40h]
0x1800783e1  mov     rsi, [r11+48h]
0x1800783e5  mov     rsp, r11
0x1800783e8  pop     r15
0x1800783ea  pop     r14
0x1800783ec  pop     r13
0x1800783ee  pop     rdi
0x1800783ef  pop     rbp
0x1800783f0  retn
```
