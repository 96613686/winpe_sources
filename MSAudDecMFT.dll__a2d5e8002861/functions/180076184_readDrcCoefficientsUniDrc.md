# _readDrcCoefficientsUniDrc

- ea: `0x180076184`
- end: `0x18007653f`
- name: `_readDrcCoefficientsUniDrc`
- size: `955`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180076548`
- `0x1800783f8`

## callees

- `0x1800110c0`
- `0x180012264`
- `0x18004d320`
- `0x180075e7c`
- `0x180076184`
- `0x180077000`

## pseudocode

```c
__int64 __fastcall readDrcCoefficientsUniDrc(_DWORD *a1, unsigned int a2, __int64 a3)
{
  __int64 v6; // r8
  char v7; // al
  __int64 v8; // r8
  char v9; // r15
  int v10; // eax
  int v11; // r12d
  char v12; // cl
  int v13; // esi
  __int64 result; // rax
  __int128 v15; // xmm1
  __int64 v16; // rcx
  __int64 v17; // xmm0_8
  int v18; // ecx
  int v19; // edx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // r8
  unsigned __int8 v23; // al
  int v24; // esi
  __int64 v25; // r8
  unsigned __int8 v26; // al
  int v27; // esi
  __int64 v28; // r8
  unsigned __int8 v29; // al
  int v30; // esi
  int v31; // r14d
  __int64 v32; // r8
  __int64 v33; // r8
  __int64 v34; // r8
  __int64 v35; // r8
  int v36; // eax
  int v37; // r15d
  char v38; // cl
  int v39; // esi
  __int128 v40; // xmm1
  __int64 v41; // rcx
  __int64 v42; // xmm0_8
  int v43; // [rsp+30h] [rbp-40h] BYREF
  __int128 v44; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v45[22]; // [rsp+48h] [rbp-28h] BYREF

  v43 = -1;
  *(_BYTE *)a3 = CDKreadBits(a1, 4, a3);
  v7 = CDKreadBits(a1, 1, v6);
  *(_BYTE *)(a3 + 1) = v7;
  if ( v7 == 1 )
    *(_WORD *)(a3 + 2) = CDKreadBits(a1, 15, v8) + 1;
  if ( a2 )
  {
    if ( (unsigned __int8)CDKreadBits(a1, 1, v8) )
    {
      v23 = CDKreadBits(a1, 4, v22);
      *(_BYTE *)(a3 + 4) = v23;
      if ( (unsigned int)v23 + 1 > 0x10 )
        return 4294967199LL;
      v24 = 0;
      while ( v24 < *(unsigned __int8 *)(a3 + 4) )
      {
        ++v24;
        result = readCustomDrcCharacteristic(a1, 0, v24 + a3 + 5, a3 + 44LL * v24 + 24);
        if ( (_DWORD)result )
          return result;
      }
    }
    if ( (unsigned __int8)CDKreadBits(a1, 1, v22) )
    {
      v26 = CDKreadBits(a1, 4, v25);
      *(_BYTE *)(a3 + 728) = v26;
      if ( (unsigned int)v26 + 1 > 0x10 )
        return 4294967199LL;
      v27 = 0;
      while ( v27 < *(unsigned __int8 *)(a3 + 728) )
      {
        ++v27;
        result = readCustomDrcCharacteristic(a1, 1, v27 + a3 + 729, a3 + 44 * (v27 + 17LL));
        if ( (_DWORD)result )
          return result;
      }
    }
    if ( (unsigned __int8)CDKreadBits(a1, 1, v25) )
    {
      v29 = CDKreadBits(a1, 4, v28);
      v30 = 0;
      v31 = v29;
      if ( v29 )
      {
        do
        {
          if ( (unsigned __int8)CDKreadBits(a1, 1, v28) )
            CDKpushFor(a1, 5);
          if ( (unsigned __int8)CDKreadBits(a1, 1, v32) )
            CDKpushFor(a1, 5);
          if ( (unsigned __int8)CDKreadBits(a1, 1, v33) )
            CDKpushFor(a1, 5);
          if ( (unsigned __int8)CDKreadBits(a1, 1, v34) )
            CDKpushFor(a1, 5);
          ++v30;
        }
        while ( v30 < v31 );
      }
    }
    *(_BYTE *)(a3 + 1452) = CDKreadBits(a1, 6, v28);
    v36 = CDKreadBits(a1, 6, v35);
    v37 = v36;
    v38 = 12;
    if ( v36 < 12 )
      v38 = v36;
    v39 = 0;
    *(_BYTE *)(a3 + 1453) = v38;
    while ( v39 < v37 )
    {
      memset(v45, 0, sizeof(v45));
      v44 = 0;
      result = readGainSet(a1, a2, &v43, &v44);
      if ( (_DWORD)result )
        return result;
      if ( v39 < 12 )
      {
        v40 = *(_OWORD *)v45;
        v41 = 38LL * v39;
        *(_OWORD *)(v41 + a3 + 1454) = v44;
        v42 = *(_QWORD *)&v45[14];
        *(_OWORD *)(v41 + a3 + 1470) = v40;
        *(_QWORD *)(v41 + a3 + 1484) = v42;
      }
      ++v39;
    }
    goto LABEL_13;
  }
  v9 = 0;
  *(_BYTE *)(a3 + 4) = 0;
  *(_BYTE *)(a3 + 728) = 0;
  v10 = CDKreadBits(a1, 6, v8);
  v11 = v10;
  v12 = 12;
  if ( v10 < 12 )
    v12 = v10;
  v13 = 0;
  *(_BYTE *)(a3 + 1453) = v12;
  while ( v13 < v11 )
  {
    memset(v45, 0, sizeof(v45));
    v44 = 0;
    result = readGainSet(a1, 0, &v43, &v44);
    if ( (_DWORD)result )
      return result;
    v9 += BYTE8(v44);
    if ( v13 < 12 )
    {
      v15 = *(_OWORD *)v45;
      v16 = 38LL * v13;
      *(_OWORD *)(v16 + a3 + 1454) = v44;
      v17 = *(_QWORD *)&v45[14];
      *(_OWORD *)(v16 + a3 + 1470) = v15;
      *(_QWORD *)(v16 + a3 + 1484) = v17;
    }
    ++v13;
  }
  *(_BYTE *)(a3 + 1452) = v9;
LABEL_13:
  v18 = 0;
  *(_QWORD *)(a3 + 1910) = -1;
  *(_DWORD *)(a3 + 1918) = -1;
  if ( *(_BYTE *)(a3 + 1453) )
  {
    do
    {
      v19 = 0;
      v20 = 38LL * v18;
      if ( *(_BYTE *)(v20 + a3 + 1462) )
      {
        do
        {
          v21 = *(unsigned __int8 *)(v20 + v19 + a3 + 1464);
          if ( (unsigned __int8)v21 < 0xCu )
            *(_BYTE *)(v21 + a3 + 1910) = v18;
          ++v19;
        }
        while ( v19 < *(unsigned __int8 *)(v20 + a3 + 1462) );
      }
      ++v18;
    }
    while ( v18 < *(unsigned __int8 *)(a3 + 1453) );
  }
  return 0;
}

```

## disassembly

```asm
0x180076184  mov     [rsp-28h+arg_8], rbx
0x180076189  mov     [rsp-28h+arg_18], rsi
0x18007618e  push    rbp
0x18007618f  push    rdi
0x180076190  push    r12
0x180076192  push    r14
0x180076194  push    r15
0x180076196  mov     rbp, rsp
0x180076199  sub     rsp, 70h
0x18007619d  mov     rax, cs:__security_cookie
0x1800761a4  xor     rax, rsp
0x1800761a7  mov     [rbp+var_10], rax
0x1800761ab  mov     r12d, edx
0x1800761ae  mov     [rbp+var_40], 0FFFFFFFFh
0x1800761b5  mov     r14d, 4
0x1800761bb  mov     rbx, r8
0x1800761be  mov     edx, r14d
0x1800761c1  mov     rdi, rcx
0x1800761c4  call    CDKreadBits
0x1800761c9  lea     r15d, [r14-3]
0x1800761cd  mov     [rbx], al
0x1800761cf  mov     edx, r15d
0x1800761d2  mov     rcx, rdi
0x1800761d5  call    CDKreadBits
0x1800761da  mov     [rbx+1], al
0x1800761dd  cmp     al, r15b
0x1800761e0  jnz     short loc_1800761F6
0x1800761e2  lea     edx, [r14+0Bh]
0x1800761e6  mov     rcx, rdi
0x1800761e9  call    CDKreadBits
0x1800761ee  add     ax, r15w
0x1800761f2  mov     [rbx+2], ax
0x1800761f6  mov     rcx, rdi
0x1800761f9  test    r12d, r12d
0x1800761fc  jnz     loc_180076334
0x180076202  xor     r15d, r15d
0x180076205  lea     edx, [r12+6]
0x18007620a  mov     [rbx+4], r15b
0x18007620e  mov     [rbx+2D8h], r15b
0x180076215  call    CDKreadBits
0x18007621a  lea     r14d, [r15+0Ch]
0x18007621e  mov     r12d, eax
0x180076221  cmp     eax, r14d
0x180076224  mov     ecx, r14d
0x180076227  cmovl   ecx, eax
0x18007622a  xor     esi, esi
0x18007622c  mov     [rbx+5ADh], cl
0x180076232  cmp     esi, r12d
0x180076235  jge     short loc_18007629F
0x180076237  xorps   xmm0, xmm0
0x18007623a  lea     r9, [rbp+var_38]
0x18007623e  xor     eax, eax
0x180076240  lea     r8, [rbp+var_40]
0x180076244  movups  xmmword ptr [rbp+var_28], xmm0
0x180076248  xor     edx, edx
0x18007624a  mov     qword ptr [rbp+var_28+0Eh], rax
0x18007624e  mov     rcx, rdi
0x180076251  movups  [rbp+var_38], xmm0
0x180076255  call    _readGainSet
0x18007625a  test    eax, eax
0x18007625c  jnz     loc_18007630E
0x180076262  movzx   eax, byte ptr [rbp+var_38+8]
0x180076266  add     r15d, eax
0x180076269  cmp     esi, r14d
0x18007626c  jge     short loc_18007629B
0x18007626e  movups  xmm0, [rbp+var_38]
0x180076272  movsxd  rax, esi
0x180076275  movups  xmm1, xmmword ptr [rbp+var_28]
0x180076279  imul    rcx, rax, 26h ; '&'
0x18007627d  movups  xmmword ptr [rcx+rbx+5AEh], xmm0
0x180076285  movsd   xmm0, qword ptr [rbp+var_28+0Eh]
0x18007628a  movups  xmmword ptr [rcx+rbx+5BEh], xmm1
0x180076292  movsd   qword ptr [rcx+rbx+5CCh], xmm0
0x18007629b  inc     esi
0x18007629d  jmp     short loc_180076232
0x18007629f  mov     [rbx+5ACh], r15b
0x1800762a6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800762aa  xor     ecx, ecx
0x1800762ac  mov     [rbx+776h], rax
0x1800762b3  mov     [rbx+77Eh], eax
0x1800762b9  cmp     [rbx+5ADh], cl
0x1800762bf  jbe     short loc_18007630C
0x1800762c1  movsxd  rax, ecx
0x1800762c4  xor     edx, edx
0x1800762c6  imul    r8, rax, 26h ; '&'
0x1800762ca  cmp     [r8+rbx+5B6h], dl
0x1800762d2  jbe     short loc_1800762FF
0x1800762d4  movsxd  rax, edx
0x1800762d7  add     rax, r8
0x1800762da  movzx   r9d, byte ptr [rax+rbx+5B8h]
0x1800762e3  cmp     r9b, r14b
0x1800762e6  jnb     short loc_1800762F0
0x1800762e8  mov     [r9+rbx+776h], cl
0x1800762f0  movzx   eax, byte ptr [r8+rbx+5B6h]
0x1800762f9  inc     edx
0x1800762fb  cmp     edx, eax
0x1800762fd  jl      short loc_1800762D4
0x1800762ff  movzx   eax, byte ptr [rbx+5ADh]
0x180076306  inc     ecx
0x180076308  cmp     ecx, eax
0x18007630a  jl      short loc_1800762C1
0x18007630c  xor     eax, eax
0x18007630e  mov     rcx, [rbp+var_10]
0x180076312  xor     rcx, rsp; StackCookie
0x180076315  call    __security_check_cookie
0x18007631a  lea     r11, [rsp+70h+var_s0]
0x18007631f  mov     rbx, [r11+38h]
0x180076323  mov     rsi, [r11+48h]
0x180076327  mov     rsp, r11
0x18007632a  pop     r15
0x18007632c  pop     r14
0x18007632e  pop     r12
0x180076330  pop     rdi
0x180076331  pop     rbp
0x180076332  retn
0x180076334  mov     edx, r15d
0x180076337  call    CDKreadBits
0x18007633c  test    al, al
0x18007633e  jz      short loc_18007638A
0x180076340  mov     edx, r14d
0x180076343  mov     rcx, rdi
0x180076346  call    CDKreadBits
0x18007634b  mov     [rbx+4], al
0x18007634e  movzx   eax, al
0x180076351  add     eax, r15d
0x180076354  cmp     eax, 10h
0x180076357  ja      short loc_1800763B5
0x180076359  xor     esi, esi
0x18007635b  movzx   eax, byte ptr [rbx+4]
0x18007635f  cmp     esi, eax
0x180076361  jge     short loc_18007638A
0x180076363  inc     esi
0x180076365  lea     r8, [rbx+5]
0x180076369  movsxd  rcx, esi
0x18007636c  xor     edx, edx
0x18007636e  imul    r9, rcx, 2Ch ; ','
0x180076372  add     r8, rcx
0x180076375  mov     rcx, rdi
0x180076378  add     r9, 18h
0x18007637c  add     r9, rbx
0x18007637f  call    _readCustomDrcCharacteristic
0x180076384  test    eax, eax
0x180076386  jz      short loc_18007635B
0x180076388  jmp     short loc_18007630E
0x18007638a  mov     edx, r15d
0x18007638d  mov     rcx, rdi
0x180076390  call    CDKreadBits
0x180076395  test    al, al
0x180076397  jz      short loc_1800763FA
0x180076399  mov     edx, r14d
0x18007639c  mov     rcx, rdi
0x18007639f  call    CDKreadBits
0x1800763a4  mov     [rbx+2D8h], al
0x1800763aa  movzx   eax, al
0x1800763ad  add     eax, r15d
0x1800763b0  cmp     eax, 10h
0x1800763b3  jbe     short loc_1800763BF
0x1800763b5  mov     eax, 0FFFFFF9Fh
0x1800763ba  jmp     loc_18007630E
0x1800763bf  xor     esi, esi
0x1800763c1  movzx   eax, byte ptr [rbx+2D8h]
0x1800763c8  cmp     esi, eax
0x1800763ca  jge     short loc_1800763FA
0x1800763cc  inc     esi
0x1800763ce  lea     r8, [rbx+2D9h]
0x1800763d5  movsxd  rcx, esi
0x1800763d8  mov     edx, r15d
0x1800763db  add     r8, rcx
0x1800763de  lea     rax, [rcx+11h]
0x1800763e2  mov     rcx, rdi
0x1800763e5  imul    r9, rax, 2Ch ; ','
0x1800763e9  add     r9, rbx
0x1800763ec  call    _readCustomDrcCharacteristic
0x1800763f1  test    eax, eax
0x1800763f3  jz      short loc_1800763C1
0x1800763f5  jmp     loc_18007630E
0x1800763fa  mov     edx, r15d
0x1800763fd  mov     rcx, rdi
0x180076400  call    CDKreadBits
0x180076405  test    al, al
0x180076407  jz      loc_18007649A
0x18007640d  mov     edx, r14d
0x180076410  mov     rcx, rdi
0x180076413  call    CDKreadBits
0x180076418  xor     esi, esi
0x18007641a  movzx   r14d, al
0x18007641e  test    al, al
0x180076420  jz      short loc_18007649A
0x180076422  mov     edx, r15d
0x180076425  mov     rcx, rdi
0x180076428  call    CDKreadBits
0x18007642d  test    al, al
0x18007642f  jz      short loc_18007643E
0x180076431  mov     edx, 5
0x180076436  mov     rcx, rdi
0x180076439  call    CDKpushFor
0x18007643e  mov     edx, r15d
0x180076441  mov     rcx, rdi
0x180076444  call    CDKreadBits
0x180076449  test    al, al
0x18007644b  jz      short loc_18007645A
0x18007644d  mov     edx, 5
0x180076452  mov     rcx, rdi
0x180076455  call    CDKpushFor
0x18007645a  mov     edx, r15d
0x18007645d  mov     rcx, rdi
0x180076460  call    CDKreadBits
0x180076465  test    al, al
0x180076467  jz      short loc_180076476
0x180076469  mov     edx, 5
0x18007646e  mov     rcx, rdi
0x180076471  call    CDKpushFor
0x180076476  mov     edx, r15d
0x180076479  mov     rcx, rdi
0x18007647c  call    CDKreadBits
0x180076481  test    al, al
0x180076483  jz      short loc_180076492
0x180076485  mov     edx, 5
0x18007648a  mov     rcx, rdi
0x18007648d  call    CDKpushFor
0x180076492  add     esi, r15d
0x180076495  cmp     esi, r14d
0x180076498  jl      short loc_180076422
0x18007649a  mov     edx, 6
0x18007649f  mov     rcx, rdi
0x1800764a2  call    CDKreadBits
0x1800764a7  mov     edx, 6
0x1800764ac  mov     [rbx+5ACh], al
0x1800764b2  mov     rcx, rdi
0x1800764b5  call    CDKreadBits
0x1800764ba  mov     r14d, 0Ch
0x1800764c0  mov     r15d, eax
0x1800764c3  cmp     eax, r14d
0x1800764c6  mov     ecx, r14d
0x1800764c9  cmovl   ecx, eax
0x1800764cc  xor     esi, esi
0x1800764ce  mov     [rbx+5ADh], cl
0x1800764d4  cmp     esi, r15d
0x1800764d7  jge     loc_1800762A6
0x1800764dd  xorps   xmm0, xmm0
0x1800764e0  lea     r9, [rbp+var_38]
0x1800764e4  xor     eax, eax
0x1800764e6  lea     r8, [rbp+var_40]
0x1800764ea  movups  xmmword ptr [rbp+var_28], xmm0
0x1800764ee  mov     edx, r12d
0x1800764f1  mov     qword ptr [rbp+var_28+0Eh], rax
0x1800764f5  mov     rcx, rdi
0x1800764f8  movups  [rbp+var_38], xmm0
0x1800764fc  call    _readGainSet
0x180076501  test    eax, eax
0x180076503  jnz     loc_18007630E
0x180076509  cmp     esi, r14d
0x18007650c  jge     short loc_18007653B
0x18007650e  movups  xmm0, [rbp+var_38]
0x180076512  movsxd  rax, esi
0x180076515  movups  xmm1, xmmword ptr [rbp+var_28]
0x180076519  imul    rcx, rax, 26h ; '&'
0x18007651d  movups  xmmword ptr [rcx+rbx+5AEh], xmm0
0x180076525  movsd   xmm0, qword ptr [rbp+var_28+0Eh]
0x18007652a  movups  xmmword ptr [rcx+rbx+5BEh], xmm1
0x180076532  movsd   qword ptr [rcx+rbx+5CCh], xmm0
0x18007653b  inc     esi
0x18007653d  jmp     short loc_1800764D4
```
