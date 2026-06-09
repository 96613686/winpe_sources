# ReadStreamMuxConfig

- ea: `0x180037490`
- end: `0x180037925`
- name: `ReadStreamMuxConfig`
- size: `1173`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180019d60`

## callees

- `0x1800363f0`
- `0x180036c60`
- `0x180037410`
- `0x180037490`

## pseudocode

```c
__int64 __fastcall ReadStreamMuxConfig(__int64 a1, __int64 a2)
{
  bool v4; // zf
  int v6; // eax
  int v7; // eax
  unsigned int v8; // edx
  unsigned int v9; // r12d
  int v10; // r15d
  int v11; // eax
  unsigned int v12; // r14d
  __int64 v13; // r13
  _DWORD *v14; // rsi
  unsigned int v15; // ecx
  int v16; // eax
  unsigned int v17; // ecx
  unsigned int v18; // edi
  __int64 v19; // rdx
  _DWORD *v20; // rcx
  __int128 *v21; // rax
  __int128 v22; // xmm0
  int v23; // eax
  int v24; // edi
  unsigned int v25; // [rsp+60h] [rbp+8h]
  unsigned int Value; // [rsp+68h] [rbp+10h] BYREF

  if ( !*(_DWORD *)a1 )
    FillBitCache((int *)a1, 1u);
  v4 = ((*(_DWORD *)(a1 + 4) >> --*(_DWORD *)a1) & 1) == 0;
  *(_DWORD *)(a2 + 16) = (*(_DWORD *)(a1 + 4) >> *(_DWORD *)a1) & 1;
  if ( v4 )
  {
    *(_DWORD *)(a2 + 20) = 0;
  }
  else
  {
    if ( !*(_DWORD *)a1 )
      FillBitCache((int *)a1, 1u);
    v4 = ((*(_DWORD *)(a1 + 4) >> --*(_DWORD *)a1) & 1) == 0;
    *(_DWORD *)(a2 + 20) = (*(_DWORD *)(a1 + 4) >> *(_DWORD *)a1) & 1;
    if ( !v4 )
      return 2;
  }
  if ( *(_DWORD *)(a2 + 16) == 1 )
    LatmGetValue(a1);
  if ( !*(_DWORD *)a1 )
    FillBitCache((int *)a1, 1u);
  v4 = ((*(_DWORD *)(a1 + 4) >> --*(_DWORD *)a1) & 1) == 0;
  *(_DWORD *)(a2 + 24) = (*(_DWORD *)(a1 + 4) >> *(_DWORD *)a1) & 1;
  if ( v4 )
    return 2;
  if ( *(_DWORD *)a1 < 6u )
    FillBitCache((int *)a1, 6u);
  *(_DWORD *)a1 -= 6;
  v6 = ((*(_DWORD *)(a1 + 4) >> *(_DWORD *)a1) & 0x3F) + 1;
  *(_DWORD *)(a2 + 28) = v6;
  if ( v6 != 1 )
    return 2;
  if ( *(_DWORD *)a1 < 4u )
    FillBitCache((int *)a1, 4u);
  *(_DWORD *)a1 -= 4;
  v7 = ((*(_DWORD *)(a1 + 4) >> *(_DWORD *)a1) & 0xF) + 1;
  *(_DWORD *)(a2 + 32) = v7;
  if ( v7 != 1 )
    return 2;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v25 = 0;
  do
  {
    if ( *(_DWORD *)a1 < 3u )
    {
      FillBitCache((int *)a1, 3u);
      v8 = v25;
    }
    *(_DWORD *)a1 -= 3;
    v11 = ((*(_DWORD *)(a1 + 4) >> *(_DWORD *)a1) & 7) + 1;
    *(_DWORD *)(a2 + 36) = v11;
    if ( v11 != 1 )
      return 2;
    v12 = 0;
    v13 = v8;
    do
    {
      v14 = (_DWORD *)(a2 + 300 * (v13 + v12));
      v14[18] = v10;
      v14[19] = 0;
      if ( v8 || v12 )
      {
        if ( !*(_DWORD *)a1 )
          FillBitCache((int *)a1, 1u);
        v4 = ((*(_DWORD *)(a1 + 4) >> --*(_DWORD *)a1) & 1) == 0;
        *(_DWORD *)(a2 + 40) = (*(_DWORD *)(a1 + 4) >> *(_DWORD *)a1) & 1;
        if ( !v4 )
        {
          v19 = 2;
          v20 = v14 + 20;
          v21 = (__int128 *)(a2 + 300 * (v13 + v12 - 1) + 80);
          do
          {
            v20 += 32;
            v22 = *v21;
            v21 += 8;
            *((_OWORD *)v20 - 8) = v22;
            *((_OWORD *)v20 - 7) = *(v21 - 7);
            *((_OWORD *)v20 - 6) = *(v21 - 6);
            *((_OWORD *)v20 - 5) = *(v21 - 5);
            *((_OWORD *)v20 - 4) = *(v21 - 4);
            *((_OWORD *)v20 - 3) = *(v21 - 3);
            *((_OWORD *)v20 - 2) = *(v21 - 2);
            *((_OWORD *)v20 - 1) = *(v21 - 1);
            --v19;
          }
          while ( v19 );
          *(_OWORD *)v20 = *v21;
          v20[4] = *((_DWORD *)v21 + 4);
          goto LABEL_45;
        }
      }
      else
      {
        *(_DWORD *)(a2 + 40) = 0;
      }
      if ( *(_DWORD *)(a2 + 16) )
      {
        Value = LatmGetValue(a1);
        v14[89] = 8 * (*(_DWORD *)(a1 + 16) - *(_DWORD *)(a1 + 24)) - *(_DWORD *)a1;
        v9 = AudioSpecificConfig((int *)a1, (__int64)(v14 + 20), &Value);
        if ( v9 )
          return v9;
        v15 = Value;
        v14[90] = 8 * (*(_DWORD *)(a1 + 16) - *(_DWORD *)(a1 + 24)) - *(_DWORD *)a1;
        if ( v15 )
        {
          v16 = *(_DWORD *)a1;
          if ( *(_DWORD *)a1 < v15 )
          {
            v17 = v15 - v16;
            *(_DWORD *)a1 = 0;
            *(_QWORD *)(a1 + 16) += (unsigned __int64)v17 >> 3;
            if ( *(_QWORD *)(a1 + 16) > *(_QWORD *)(a1 + 8) )
            {
              *(_QWORD *)(a1 + 16) = *(_QWORD *)(a1 + 24);
              *(_DWORD *)(a1 + 44) = 1;
            }
            v18 = v17 & 7;
            if ( (v17 & 7) == 0 )
            {
LABEL_46:
              FillBitCache((int *)a1, 3u);
              goto LABEL_47;
            }
            FillBitCache((int *)a1, v18);
            *(_DWORD *)a1 -= v18;
          }
          else
          {
            *(_DWORD *)a1 = v16 - v15;
          }
        }
      }
      else
      {
        v14[89] = 8 * (*(_DWORD *)(a1 + 16) - *(_DWORD *)(a1 + 24)) - *(_DWORD *)a1;
        v9 = AudioSpecificConfig((int *)a1, (__int64)(v14 + 20), 0);
        if ( v9 )
          return v9;
        v14[90] = 8 * (*(_DWORD *)(a1 + 16) - *(_DWORD *)(a1 + 24)) - *(_DWORD *)a1;
      }
LABEL_45:
      if ( *(_DWORD *)a1 < 3u )
        goto LABEL_46;
LABEL_47:
      *(_DWORD *)a1 -= 3;
      v4 = ((*(_DWORD *)(a1 + 4) >> *(_DWORD *)a1) & 7) == 0;
      v14[16] = (*(_DWORD *)(a1 + 4) >> *(_DWORD *)a1) & 7;
      if ( !v4 )
        return 2;
      if ( *(_DWORD *)a1 < 8u )
        FillBitCache((int *)a1, 8u);
      *(_DWORD *)a1 -= 8;
      v14[17] = (unsigned __int8)(*(_DWORD *)(a1 + 4) >> *(_DWORD *)a1);
      if ( !*(_DWORD *)(a2 + 24) && v12 && v14[20] == 6 )
        return 2;
      v8 = v25;
      ++v10;
      ++v12;
    }
    while ( v12 < *(_DWORD *)(a2 + 36) );
    v8 = v25 + 1;
    v25 = v8;
  }
  while ( v8 < *(_DWORD *)(a2 + 32) );
  if ( !*(_DWORD *)a1 )
    FillBitCache((int *)a1, 1u);
  v4 = ((*(_DWORD *)(a1 + 4) >> --*(_DWORD *)a1) & 1) == 0;
  *(_DWORD *)(a2 + 44) = (*(_DWORD *)(a1 + 4) >> *(_DWORD *)a1) & 1;
  if ( !v4 )
  {
    if ( *(_DWORD *)(a2 + 16) == 1 )
    {
      *(_DWORD *)(a2 + 48) = LatmGetValue(a1);
    }
    else
    {
      v23 = 0;
      do
      {
        *(_DWORD *)(a2 + 48) = v23 << 8;
        if ( !*(_DWORD *)a1 )
          FillBitCache((int *)a1, 1u);
        v24 = (*(_DWORD *)(a1 + 4) >> --*(_DWORD *)a1) & 1;
        if ( *(_DWORD *)a1 < 8u )
          FillBitCache((int *)a1, 8u);
        *(_DWORD *)a1 -= 8;
        v23 = (unsigned __int8)(*(_DWORD *)(a1 + 4) >> *(_DWORD *)a1) + *(_DWORD *)(a2 + 48);
        *(_DWORD *)(a2 + 48) = v23;
      }
      while ( v24 );
    }
  }
  if ( !*(_DWORD *)a1 )
    FillBitCache((int *)a1, 1u);
  v4 = ((*(_DWORD *)(a1 + 4) >> --*(_DWORD *)a1) & 1) == 0;
  *(_QWORD *)(a2 + 52) = (*(_DWORD *)(a1 + 4) >> *(_DWORD *)a1) & 1;
  if ( !v4 )
  {
    if ( *(_DWORD *)a1 < 8u )
      FillBitCache((int *)a1, 8u);
    *(_DWORD *)a1 -= 8;
    *(_DWORD *)(a2 + 56) = (unsigned __int8)(*(_DWORD *)(a1 + 4) >> *(_DWORD *)a1);
  }
  return v9;
}

```

## disassembly

```asm
0x180037490  push    rbx
0x180037492  push    rbp
0x180037493  push    rdi
0x180037494  push    r12
0x180037496  sub     rsp, 38h
0x18003749a  cmp     dword ptr [rcx], 1
0x18003749d  mov     rbp, rdx
0x1800374a0  mov     rbx, rcx
0x1800374a3  jnb     short loc_1800374AF
0x1800374a5  mov     edx, 1
0x1800374aa  call    FillBitCache
0x1800374af  dec     dword ptr [rbx]
0x1800374b1  xor     edi, edi
0x1800374b3  mov     eax, [rbx+4]
0x1800374b6  mov     ecx, [rbx]
0x1800374b8  shr     eax, cl
0x1800374ba  and     eax, 1
0x1800374bd  mov     [rbp+10h], eax
0x1800374c0  jz      short loc_1800374F9
0x1800374c2  cmp     dword ptr [rbx], 1
0x1800374c5  jnb     short loc_1800374D4
0x1800374c7  mov     edx, 1
0x1800374cc  mov     rcx, rbx
0x1800374cf  call    FillBitCache
0x1800374d4  dec     dword ptr [rbx]
0x1800374d6  mov     eax, [rbx+4]
0x1800374d9  mov     ecx, [rbx]
0x1800374db  shr     eax, cl
0x1800374dd  and     eax, 1
0x1800374e0  mov     [rbp+14h], eax
0x1800374e3  jz      short loc_1800374FC
0x1800374e5  mov     r12d, 2
0x1800374eb  mov     eax, r12d
0x1800374ee  add     rsp, 38h
0x1800374f2  pop     r12
0x1800374f4  pop     rdi
0x1800374f5  pop     rbp
0x1800374f6  pop     rbx
0x1800374f7  retn
0x1800374f9  mov     [rbp+14h], edi
0x1800374fc  cmp     dword ptr [rbp+10h], 1
0x180037500  jnz     short loc_18003750A
0x180037502  mov     rcx, rbx
0x180037505  call    LatmGetValue
0x18003750a  cmp     dword ptr [rbx], 1
0x18003750d  jnb     short loc_18003751C
0x18003750f  mov     edx, 1
0x180037514  mov     rcx, rbx
0x180037517  call    FillBitCache
0x18003751c  dec     dword ptr [rbx]
0x18003751e  mov     eax, [rbx+4]
0x180037521  mov     ecx, [rbx]
0x180037523  shr     eax, cl
0x180037525  and     eax, 1
0x180037528  mov     [rbp+18h], eax
0x18003752b  jz      short loc_1800374E5
0x18003752d  cmp     dword ptr [rbx], 6
0x180037530  jnb     short loc_18003753F
0x180037532  mov     edx, 6
0x180037537  mov     rcx, rbx
0x18003753a  call    FillBitCache
0x18003753f  add     dword ptr [rbx], 0FFFFFFFAh
0x180037542  mov     eax, [rbx+4]
0x180037545  mov     ecx, [rbx]
0x180037547  shr     eax, cl
0x180037549  and     eax, 3Fh
0x18003754c  inc     eax
0x18003754e  mov     [rbp+1Ch], eax
0x180037551  cmp     eax, 1
0x180037554  jnz     short loc_1800374E5
0x180037556  cmp     dword ptr [rbx], 4
0x180037559  jnb     short loc_180037568
0x18003755b  mov     edx, 4
0x180037560  mov     rcx, rbx
0x180037563  call    FillBitCache
0x180037568  add     dword ptr [rbx], 0FFFFFFFCh
0x18003756b  mov     eax, [rbx+4]
0x18003756e  mov     ecx, [rbx]
0x180037570  shr     eax, cl
0x180037572  and     eax, 0Fh
0x180037575  inc     eax
0x180037577  mov     [rbp+20h], eax
0x18003757a  cmp     eax, 1
0x18003757d  jnz     loc_1800374E5
0x180037583  mov     [rsp+58h+arg_10], rsi
0x180037588  mov     edx, edi
0x18003758a  mov     [rsp+58h+var_28], r13
0x18003758f  mov     r12d, edi
0x180037592  mov     [rsp+58h+var_30], r14
0x180037597  mov     [rsp+58h+var_38], r15
0x18003759c  mov     r15d, edi
0x18003759f  mov     [rsp+58h+arg_0], edx
0x1800375a3  cmp     dword ptr [rbx], 3
0x1800375a6  jnb     short loc_1800375B9
0x1800375a8  mov     edx, 3
0x1800375ad  mov     rcx, rbx
0x1800375b0  call    FillBitCache
0x1800375b5  mov     edx, [rsp+58h+arg_0]
0x1800375b9  add     dword ptr [rbx], 0FFFFFFFDh
0x1800375bc  mov     eax, [rbx+4]
0x1800375bf  mov     ecx, [rbx]
0x1800375c1  shr     eax, cl
0x1800375c3  and     eax, 7
0x1800375c6  inc     eax
0x1800375c8  mov     [rbp+24h], eax
0x1800375cb  cmp     eax, 1
0x1800375ce  jnz     loc_1800378FD
0x1800375d4  mov     r14d, edi
0x1800375d7  mov     r13d, edx
0x1800375da  jmp     short loc_1800375E2
0x1800375e0  xor     edi, edi
0x1800375e2  mov     eax, r14d
0x1800375e5  add     rax, r13
0x1800375e8  imul    rsi, rax, 12Ch
0x1800375ef  add     rsi, rbp
0x1800375f2  mov     [rsi+48h], r15d
0x1800375f6  mov     [rsi+4Ch], edi
0x1800375f9  test    edx, edx
0x1800375fb  jnz     short loc_180037607
0x1800375fd  test    r14d, r14d
0x180037600  jnz     short loc_180037607
0x180037602  mov     [rbp+28h], edi
0x180037605  jmp     short loc_18003762E
0x180037607  cmp     dword ptr [rbx], 1
0x18003760a  jnb     short loc_180037619
0x18003760c  mov     edx, 1
0x180037611  mov     rcx, rbx
0x180037614  call    FillBitCache
0x180037619  dec     dword ptr [rbx]
0x18003761b  mov     eax, [rbx+4]
0x18003761e  mov     ecx, [rbx]
0x180037620  shr     eax, cl
0x180037622  and     eax, 1
0x180037625  mov     [rbp+28h], eax
0x180037628  jnz     loc_180037722
0x18003762e  cmp     dword ptr [rbp+10h], 0
0x180037632  mov     rcx, rbx
0x180037635  jnz     short loc_180037675
0x180037637  mov     eax, [rbx+10h]
0x18003763a  lea     rdx, [rsi+50h]
0x18003763e  sub     eax, [rbx+18h]
0x180037641  xor     r8d, r8d
0x180037644  shl     eax, 3
0x180037647  sub     eax, [rbx]
0x180037649  mov     [rsi+164h], eax
0x18003764f  call    AudioSpecificConfig
0x180037654  mov     r12d, eax
0x180037657  test    eax, eax
0x180037659  jnz     loc_180037903
0x18003765f  mov     ecx, [rbx+10h]
0x180037662  sub     ecx, [rbx+18h]
0x180037665  shl     ecx, 3
0x180037668  sub     ecx, [rbx]
0x18003766a  mov     [rsi+168h], ecx
0x180037670  jmp     loc_18003779F
0x180037675  call    LatmGetValue
0x18003767a  mov     [rsp+58h+arg_8], eax
0x18003767e  lea     r8, [rsp+58h+arg_8]
0x180037683  mov     eax, [rbx+10h]
0x180037686  lea     rdx, [rsi+50h]
0x18003768a  sub     eax, [rbx+18h]
0x18003768d  mov     rcx, rbx
0x180037690  shl     eax, 3
0x180037693  sub     eax, [rbx]
0x180037695  mov     [rsi+164h], eax
0x18003769b  call    AudioSpecificConfig
0x1800376a0  mov     r12d, eax
0x1800376a3  test    eax, eax
0x1800376a5  jnz     loc_180037903
0x1800376ab  mov     eax, [rbx+10h]
0x1800376ae  sub     eax, [rbx+18h]
0x1800376b1  mov     ecx, [rsp+58h+arg_8]
0x1800376b5  shl     eax, 3
0x1800376b8  sub     eax, [rbx]
0x1800376ba  mov     [rsi+168h], eax
0x1800376c0  test    ecx, ecx
0x1800376c2  jz      loc_18003779F
0x1800376c8  mov     eax, [rbx]
0x1800376ca  cmp     eax, ecx
0x1800376cc  jb      short loc_1800376D7
0x1800376ce  sub     eax, ecx
0x1800376d0  mov     [rbx], eax
0x1800376d2  jmp     loc_18003779F
0x1800376d7  sub     ecx, eax
0x1800376d9  mov     dword ptr [rbx], 0
0x1800376df  mov     eax, ecx
0x1800376e1  shr     rax, 3
0x1800376e5  add     [rbx+10h], rax
0x1800376e9  mov     rax, [rbx+10h]
0x1800376ed  mov     edi, ecx
0x1800376ef  cmp     rax, [rbx+8]
0x1800376f3  jbe     short loc_180037704
0x1800376f5  mov     rax, [rbx+18h]
0x1800376f9  mov     [rbx+10h], rax
0x1800376fd  mov     dword ptr [rbx+2Ch], 1
0x180037704  and     edi, 7
0x180037707  jz      loc_1800377A4
0x18003770d  test    edi, edi
0x18003770f  jz      short loc_18003771B
0x180037711  mov     edx, edi
0x180037713  mov     rcx, rbx
0x180037716  call    FillBitCache
0x18003771b  sub     [rbx], edi
0x18003771d  jmp     loc_18003779F
0x180037722  lea     ecx, [r14-1]
0x180037726  mov     edx, 2
0x18003772b  add     rcx, r13
0x18003772e  imul    rax, rcx, 12Ch
0x180037735  lea     rcx, [rsi+50h]
0x180037739  add     rax, 50h ; 'P'
0x18003773d  add     rax, rbp
0x180037740  lea     rcx, [rcx+80h]
0x180037747  movups  xmm0, xmmword ptr [rax]
0x18003774a  lea     rax, [rax+80h]
0x180037751  movups  xmmword ptr [rcx-80h], xmm0
0x180037755  movups  xmm1, xmmword ptr [rax-70h]
0x180037759  movups  xmmword ptr [rcx-70h], xmm1
0x18003775d  movups  xmm0, xmmword ptr [rax-60h]
0x180037761  movups  xmmword ptr [rcx-60h], xmm0
0x180037765  movups  xmm1, xmmword ptr [rax-50h]
0x180037769  movups  xmmword ptr [rcx-50h], xmm1
0x18003776d  movups  xmm0, xmmword ptr [rax-40h]
0x180037771  movups  xmmword ptr [rcx-40h], xmm0
0x180037775  movups  xmm1, xmmword ptr [rax-30h]
0x180037779  movups  xmmword ptr [rcx-30h], xmm1
0x18003777d  movups  xmm0, xmmword ptr [rax-20h]
0x180037781  movups  xmmword ptr [rcx-20h], xmm0
0x180037785  movups  xmm1, xmmword ptr [rax-10h]
0x180037789  movups  xmmword ptr [rcx-10h], xmm1
0x18003778d  sub     rdx, 1
0x180037791  jnz     short loc_180037740
0x180037793  movups  xmm0, xmmword ptr [rax]
0x180037796  movups  xmmword ptr [rcx], xmm0
0x180037799  mov     eax, [rax+10h]
0x18003779c  mov     [rcx+10h], eax
0x18003779f  cmp     dword ptr [rbx], 3
0x1800377a2  jnb     short loc_1800377B1
0x1800377a4  mov     edx, 3
0x1800377a9  mov     rcx, rbx
0x1800377ac  call    FillBitCache
0x1800377b1  add     dword ptr [rbx], 0FFFFFFFDh
0x1800377b4  mov     eax, [rbx+4]
0x1800377b7  mov     ecx, [rbx]
0x1800377b9  shr     eax, cl
0x1800377bb  and     eax, 7
0x1800377be  mov     [rsi+40h], eax
0x1800377c1  jnz     loc_1800378FD
0x1800377c7  cmp     dword ptr [rbx], 8
0x1800377ca  jnb     short loc_1800377D9
0x1800377cc  mov     edx, 8
0x1800377d1  mov     rcx, rbx
0x1800377d4  call    FillBitCache
0x1800377d9  add     dword ptr [rbx], 0FFFFFFF8h
0x1800377dc  mov     eax, [rbx+4]
0x1800377df  mov     ecx, [rbx]
0x1800377e1  shr     eax, cl
0x1800377e3  movzx   eax, al
0x1800377e6  mov     [rsi+44h], eax
0x1800377e9  cmp     dword ptr [rbp+18h], 0
0x1800377ed  jnz     short loc_1800377FE
0x1800377ef  test    r14d, r14d
0x1800377f2  jz      short loc_1800377FE
0x1800377f4  cmp     dword ptr [rsi+50h], 6
0x1800377f8  jz      loc_1800378FD
0x1800377fe  mov     edx, [rsp+58h+arg_0]
0x180037802  inc     r15d
0x180037805  inc     r14d
0x180037808  cmp     r14d, [rbp+24h]
0x18003780c  jb      loc_1800375E0
0x180037812  inc     edx
0x180037814  mov     [rsp+58h+arg_0], edx
0x180037818  cmp     edx, [rbp+20h]
0x18003781b  jnb     short loc_180037824
0x18003781d  xor     edi, edi
0x18003781f  jmp     loc_1800375A3
0x180037824  cmp     dword ptr [rbx], 1
0x180037827  jnb     short loc_180037836
0x180037829  mov     edx, 1
0x18003782e  mov     rcx, rbx
0x180037831  call    FillBitCache
0x180037836  dec     dword ptr [rbx]
0x180037838  mov     eax, [rbx+4]
0x18003783b  mov     ecx, [rbx]
0x18003783d  shr     eax, cl
0x18003783f  and     eax, 1
0x180037842  mov     [rbp+2Ch], eax
0x180037845  jz      short loc_1800378AF
0x180037847  cmp     dword ptr [rbp+10h], 1
0x18003784b  jnz     short loc_18003785A
0x18003784d  mov     rcx, rbx
0x180037850  call    LatmGetValue
0x180037855  mov     [rbp+30h], eax
0x180037858  jmp     short loc_1800378AF
0x18003785a  xor     eax, eax
0x18003785c  nop     dword ptr [rax+00h]
0x180037860  shl     eax, 8
0x180037863  mov     [rbp+30h], eax
0x180037866  cmp     dword ptr [rbx], 1
0x180037869  jnb     short loc_180037878
0x18003786b  mov     edx, 1
  ... truncated ...
```
