# ReadStreamMuxConfig

- ea: `0x18005d308`
- end: `0x18005d729`
- name: `ReadStreamMuxConfig`
- size: `1057`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18005d170`

## callees

- `0x18003df38`
- `0x18003e3ec`
- `0x18003e4f0`
- `0x18005d094`
- `0x18005d100`
- `0x18005d308`

## pseudocode

```c
__int64 __fastcall ReadStreamMuxConfig(_DWORD *a1, __int64 a2)
{
  unsigned int v4; // eax
  int v5; // eax
  int v6; // eax
  bool v7; // zf
  int v8; // eax
  int v9; // eax
  unsigned int v10; // esi
  int v11; // edx
  unsigned int i; // r13d
  int v13; // eax
  unsigned int j; // r14d
  unsigned __int64 v15; // rbp
  int v16; // eax
  _DWORD *v17; // rcx
  _DWORD *v18; // rcx
  int v19; // eax
  int v20; // edx
  __int64 v21; // rdx
  _OWORD *v22; // rcx
  _OWORD *v23; // rax
  __int128 v24; // xmm1
  unsigned int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // ebp
  int v30; // [rsp+60h] [rbp+8h]
  int Value; // [rsp+68h] [rbp+10h] BYREF

  if ( !*a1 )
    FillBitCache(a1, 1);
  v4 = a1[1];
  v5 = (v4 >> --*a1) & 1;
  *(_DWORD *)(a2 + 16) = v5;
  if ( v5 )
  {
    if ( !*a1 )
      FillBitCache(a1, 1);
    v6 = (a1[1] >> --*a1) & 1;
  }
  else
  {
    v6 = 0;
  }
  *(_DWORD *)(a2 + 20) = v6;
  if ( v6 )
    return 2;
  if ( *(_DWORD *)(a2 + 16) == 1 )
    LatmGetValue(a1);
  if ( !*a1 )
    FillBitCache(a1, 1);
  v7 = ((a1[1] >> --*a1) & 1) == 0;
  *(_DWORD *)(a2 + 24) = (a1[1] >> *a1) & 1;
  if ( v7 )
    return 2;
  if ( *a1 < 6u )
    FillBitCache(a1, 6);
  *a1 -= 6;
  v8 = ((a1[1] >> *a1) & 0x3F) + 1;
  *(_DWORD *)(a2 + 28) = v8;
  if ( v8 != 1 )
    return 2;
  if ( *a1 < 4u )
    FillBitCache(a1, 4);
  *a1 -= 4;
  v9 = ((a1[1] >> *a1) & 0xF) + 1;
  *(_DWORD *)(a2 + 32) = v9;
  if ( v9 != 1 )
  {
    return 2;
  }
  else
  {
    v10 = 0;
    v11 = 0;
    v30 = 0;
    for ( i = 0; i < *(_DWORD *)(a2 + 32); ++i )
    {
      if ( *a1 < 3u )
      {
        FillBitCache(a1, 3);
        v11 = v30;
      }
      *a1 -= 3;
      v13 = ((a1[1] >> *a1) & 7) + 1;
      *(_DWORD *)(a2 + 36) = v13;
      if ( v13 != 1 )
        return 2;
      for ( j = 0; j < *(_DWORD *)(a2 + 36); ++j )
      {
        v15 = 300 * (i + (unsigned __int64)j);
        *(_DWORD *)(a2 + v15 + 72) = v11;
        *(_DWORD *)(a2 + v15 + 76) = 0;
        if ( i || j )
        {
          if ( !*a1 )
            FillBitCache(a1, 1);
          v16 = (a1[1] >> --*a1) & 1;
        }
        else
        {
          v16 = 0;
        }
        *(_DWORD *)(a2 + 40) = v16;
        if ( v16 )
        {
          v21 = 2;
          v22 = (_OWORD *)(v15 + a2 + 80);
          v23 = (_OWORD *)(a2 + 300 * (i + (unsigned __int64)(j - 1)) + 80);
          do
          {
            *v22 = *v23;
            v22[1] = v23[1];
            v22[2] = v23[2];
            v22[3] = v23[3];
            v22[4] = v23[4];
            v22[5] = v23[5];
            v22[6] = v23[6];
            v24 = v23[7];
            v23 += 8;
            v22[7] = v24;
            v22 += 8;
            --v21;
          }
          while ( v21 );
          *v22 = *v23;
          *((_DWORD *)v22 + 4) = *((_DWORD *)v23 + 4);
        }
        else if ( *(_DWORD *)(a2 + 16) )
        {
          Value = LatmGetValue(a1);
          *(_DWORD *)(a2 + v15 + 356) = GetTotalNumberOfBitsRead(a1);
          v10 = AudioSpecificConfig(v18, (int *)(v15 + a2 + 80), &Value);
          if ( v10 )
            return v10;
          v19 = GetTotalNumberOfBitsRead(a1);
          v20 = Value;
          *(_DWORD *)(a2 + v15 + 360) = v19;
          if ( v20 )
            SkipBitBufBits();
        }
        else
        {
          *(_DWORD *)(a2 + v15 + 356) = GetTotalNumberOfBitsRead(a1);
          v10 = AudioSpecificConfig(v17, (int *)(v15 + a2 + 80), 0);
          if ( v10 )
            return v10;
          *(_DWORD *)(a2 + v15 + 360) = GetTotalNumberOfBitsRead(a1);
        }
        if ( *a1 < 3u )
          FillBitCache(a1, 3);
        *a1 -= 3;
        v7 = ((a1[1] >> *a1) & 7) == 0;
        *(_DWORD *)(a2 + v15 + 64) = (a1[1] >> *a1) & 7;
        if ( !v7 )
          return 2;
        if ( *a1 < 8u )
          FillBitCache(a1, 8);
        *a1 -= 8;
        *(_DWORD *)(a2 + v15 + 68) = (unsigned __int8)(a1[1] >> *a1);
        if ( !*(_DWORD *)(a2 + 24) && j && *(_DWORD *)(v15 + a2 + 80) == 6 )
          return 2;
        v11 = ++v30;
      }
    }
    if ( !*a1 )
      FillBitCache(a1, 1);
    v25 = a1[1];
    v26 = (v25 >> --*a1) & 1;
    *(_DWORD *)(a2 + 44) = v26;
    if ( v26 )
    {
      if ( *(_DWORD *)(a2 + 16) == 1 )
      {
        *(_DWORD *)(a2 + 48) = LatmGetValue(a1);
      }
      else
      {
        v27 = 0;
        do
        {
          *(_DWORD *)(a2 + 48) = v27 << 8;
          if ( !*a1 )
            FillBitCache(a1, 1);
          v28 = (a1[1] >> --*a1) & 1;
          if ( *a1 < 8u )
            FillBitCache(a1, 8);
          *a1 -= 8;
          v27 = (unsigned __int8)(a1[1] >> *a1) + *(_DWORD *)(a2 + 48);
          *(_DWORD *)(a2 + 48) = v27;
        }
        while ( v28 );
      }
    }
    if ( !*a1 )
      FillBitCache(a1, 1);
    v7 = ((a1[1] >> --*a1) & 1) == 0;
    *(_QWORD *)(a2 + 52) = (a1[1] >> *a1) & 1;
    if ( !v7 )
    {
      if ( *a1 < 8u )
        FillBitCache(a1, 8);
      *a1 -= 8;
      *(_DWORD *)(a2 + 56) = (unsigned __int8)(a1[1] >> *a1);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18005d308  mov     [rsp+arg_10], rbx
0x18005d30d  push    rbp
0x18005d30e  push    rsi
0x18005d30f  push    rdi
0x18005d310  push    r12
0x18005d312  push    r13
0x18005d314  push    r14
0x18005d316  push    r15
0x18005d318  sub     rsp, 20h
0x18005d31c  mov     r12d, 1
0x18005d322  mov     rdi, rdx
0x18005d325  mov     rbx, rcx
0x18005d328  cmp     [rcx], r12d
0x18005d32b  jnb     short loc_18005D335
0x18005d32d  mov     edx, r12d
0x18005d330  call    FillBitCache
0x18005d335  mov     eax, [rbx+4]
0x18005d338  or      ebp, 0FFFFFFFFh
0x18005d33b  add     [rbx], ebp
0x18005d33d  mov     ecx, [rbx]
0x18005d33f  shr     eax, cl
0x18005d341  and     eax, r12d
0x18005d344  mov     [rdi+10h], eax
0x18005d347  jz      short loc_18005D367
0x18005d349  cmp     [rbx], r12d
0x18005d34c  jnb     short loc_18005D359
0x18005d34e  mov     edx, r12d
0x18005d351  mov     rcx, rbx
0x18005d354  call    FillBitCache
0x18005d359  add     [rbx], ebp
0x18005d35b  mov     eax, [rbx+4]
0x18005d35e  mov     ecx, [rbx]
0x18005d360  shr     eax, cl
0x18005d362  and     eax, r12d
0x18005d365  jmp     short loc_18005D369
0x18005d367  xor     eax, eax
0x18005d369  mov     [rdi+14h], eax
0x18005d36c  test    eax, eax
0x18005d36e  jnz     loc_18005D70C
0x18005d374  cmp     [rdi+10h], r12d
0x18005d378  jnz     short loc_18005D382
0x18005d37a  mov     rcx, rbx
0x18005d37d  call    LatmGetValue
0x18005d382  cmp     [rbx], r12d
0x18005d385  jnb     short loc_18005D392
0x18005d387  mov     edx, r12d
0x18005d38a  mov     rcx, rbx
0x18005d38d  call    FillBitCache
0x18005d392  add     [rbx], ebp
0x18005d394  mov     eax, [rbx+4]
0x18005d397  mov     ecx, [rbx]
0x18005d399  shr     eax, cl
0x18005d39b  and     eax, r12d
0x18005d39e  mov     [rdi+18h], eax
0x18005d3a1  jz      loc_18005D70C
0x18005d3a7  cmp     dword ptr [rbx], 6
0x18005d3aa  jnb     short loc_18005D3B9
0x18005d3ac  mov     edx, 6
0x18005d3b1  mov     rcx, rbx
0x18005d3b4  call    FillBitCache
0x18005d3b9  add     dword ptr [rbx], 0FFFFFFFAh
0x18005d3bc  mov     eax, [rbx+4]
0x18005d3bf  mov     ecx, [rbx]
0x18005d3c1  shr     eax, cl
0x18005d3c3  and     eax, 3Fh
0x18005d3c6  inc     eax
0x18005d3c8  mov     [rdi+1Ch], eax
0x18005d3cb  cmp     eax, r12d
0x18005d3ce  jnz     loc_18005D70C
0x18005d3d4  mov     edx, 4
0x18005d3d9  cmp     [rbx], edx
0x18005d3db  jnb     short loc_18005D3E5
0x18005d3dd  mov     rcx, rbx
0x18005d3e0  call    FillBitCache
0x18005d3e5  add     dword ptr [rbx], 0FFFFFFFCh
0x18005d3e8  mov     eax, [rbx+4]
0x18005d3eb  mov     ecx, [rbx]
0x18005d3ed  shr     eax, cl
0x18005d3ef  and     eax, 0Fh
0x18005d3f2  inc     eax
0x18005d3f4  mov     [rdi+20h], eax
0x18005d3f7  cmp     eax, r12d
0x18005d3fa  jnz     loc_18005D70C
0x18005d400  xor     esi, esi
0x18005d402  xor     edx, edx
0x18005d404  mov     [rsp+58h+arg_0], edx
0x18005d408  xor     r13d, r13d
0x18005d40b  lea     r15d, [rsi+8]
0x18005d40f  cmp     r13d, [rdi+20h]
0x18005d413  jnb     loc_18005D637
0x18005d419  cmp     dword ptr [rbx], 3
0x18005d41c  jnb     short loc_18005D42F
0x18005d41e  mov     edx, 3
0x18005d423  mov     rcx, rbx
0x18005d426  call    FillBitCache
0x18005d42b  mov     edx, [rsp+58h+arg_0]
0x18005d42f  add     dword ptr [rbx], 0FFFFFFFDh
0x18005d432  mov     eax, [rbx+4]
0x18005d435  mov     ecx, [rbx]
0x18005d437  shr     eax, cl
0x18005d439  and     eax, 7
0x18005d43c  inc     eax
0x18005d43e  mov     [rdi+24h], eax
0x18005d441  cmp     eax, r12d
0x18005d444  jnz     loc_18005D70C
0x18005d44a  xor     r14d, r14d
0x18005d44d  cmp     r14d, [rdi+24h]
0x18005d451  jnb     loc_18005D62F
0x18005d457  mov     r15d, r13d
0x18005d45a  mov     eax, r14d
0x18005d45d  add     rax, r15
0x18005d460  imul    rbp, rax, 12Ch
0x18005d467  mov     [rdi+rbp+48h], edx
0x18005d46b  mov     dword ptr [rdi+rbp+4Ch], 0
0x18005d473  test    r13d, r13d
0x18005d476  jnz     short loc_18005D481
0x18005d478  test    r14d, r14d
0x18005d47b  jnz     short loc_18005D481
0x18005d47d  xor     eax, eax
0x18005d47f  jmp     short loc_18005D49D
0x18005d481  cmp     [rbx], r12d
0x18005d484  jnb     short loc_18005D491
0x18005d486  mov     edx, r12d
0x18005d489  mov     rcx, rbx
0x18005d48c  call    FillBitCache
0x18005d491  dec     dword ptr [rbx]
0x18005d493  mov     eax, [rbx+4]
0x18005d496  mov     ecx, [rbx]
0x18005d498  shr     eax, cl
0x18005d49a  and     eax, r12d
0x18005d49d  lea     r12, [rdi+50h]
0x18005d4a1  mov     [rdi+28h], eax
0x18005d4a4  add     r12, rbp
0x18005d4a7  test    eax, eax
0x18005d4a9  jnz     loc_18005D539
0x18005d4af  mov     rcx, rbx
0x18005d4b2  cmp     [rdi+10h], eax
0x18005d4b5  jnz     short loc_18005D4EC
0x18005d4b7  call    GetTotalNumberOfBitsRead
0x18005d4bc  xor     r8d, r8d
0x18005d4bf  mov     [rdi+rbp+164h], eax
0x18005d4c6  mov     rdx, r12
0x18005d4c9  call    AudioSpecificConfig
0x18005d4ce  mov     esi, eax
0x18005d4d0  test    eax, eax
0x18005d4d2  jnz     loc_18005D711
0x18005d4d8  mov     rcx, rbx
0x18005d4db  call    GetTotalNumberOfBitsRead
0x18005d4e0  mov     [rdi+rbp+168h], eax
0x18005d4e7  jmp     loc_18005D5B0
0x18005d4ec  call    LatmGetValue
0x18005d4f1  mov     rcx, rbx
0x18005d4f4  mov     [rsp+58h+arg_8], eax
0x18005d4f8  call    GetTotalNumberOfBitsRead
0x18005d4fd  lea     r8, [rsp+58h+arg_8]
0x18005d502  mov     [rdi+rbp+164h], eax
0x18005d509  mov     rdx, r12
0x18005d50c  call    AudioSpecificConfig
0x18005d511  mov     esi, eax
0x18005d513  test    eax, eax
0x18005d515  jnz     loc_18005D711
0x18005d51b  mov     rcx, rbx
0x18005d51e  call    GetTotalNumberOfBitsRead
0x18005d523  mov     edx, [rsp+58h+arg_8]
0x18005d527  mov     [rdi+rbp+168h], eax
0x18005d52e  test    edx, edx
0x18005d530  jz      short loc_18005D5B0
0x18005d532  call    SkipBitBufBits
0x18005d537  jmp     short loc_18005D5B0
0x18005d539  lea     ecx, [r14-1]
0x18005d53d  mov     edx, 2
0x18005d542  add     rcx, r15
0x18005d545  imul    rax, rcx, 12Ch
0x18005d54c  mov     rcx, r12
0x18005d54f  lea     r8d, [rdx+7Eh]
0x18005d553  add     rax, 50h ; 'P'
0x18005d557  add     rax, rdi
0x18005d55a  movups  xmm0, xmmword ptr [rax]
0x18005d55d  movups  xmmword ptr [rcx], xmm0
0x18005d560  movups  xmm1, xmmword ptr [rax+10h]
0x18005d564  movups  xmmword ptr [rcx+10h], xmm1
0x18005d568  movups  xmm0, xmmword ptr [rax+20h]
0x18005d56c  movups  xmmword ptr [rcx+20h], xmm0
0x18005d570  movups  xmm1, xmmword ptr [rax+30h]
0x18005d574  movups  xmmword ptr [rcx+30h], xmm1
0x18005d578  movups  xmm0, xmmword ptr [rax+40h]
0x18005d57c  movups  xmmword ptr [rcx+40h], xmm0
0x18005d580  movups  xmm1, xmmword ptr [rax+50h]
0x18005d584  movups  xmmword ptr [rcx+50h], xmm1
0x18005d588  movups  xmm0, xmmword ptr [rax+60h]
0x18005d58c  movups  xmmword ptr [rcx+60h], xmm0
0x18005d590  movups  xmm1, xmmword ptr [rax+70h]
0x18005d594  add     rax, r8
0x18005d597  movups  xmmword ptr [rcx+70h], xmm1
0x18005d59b  add     rcx, r8
0x18005d59e  sub     rdx, 1
0x18005d5a2  jnz     short loc_18005D55A
0x18005d5a4  movups  xmm0, xmmword ptr [rax]
0x18005d5a7  movups  xmmword ptr [rcx], xmm0
0x18005d5aa  mov     eax, [rax+10h]
0x18005d5ad  mov     [rcx+10h], eax
0x18005d5b0  cmp     dword ptr [rbx], 3
0x18005d5b3  jnb     short loc_18005D5C2
0x18005d5b5  mov     edx, 3
0x18005d5ba  mov     rcx, rbx
0x18005d5bd  call    FillBitCache
0x18005d5c2  add     dword ptr [rbx], 0FFFFFFFDh
0x18005d5c5  mov     eax, [rbx+4]
0x18005d5c8  mov     ecx, [rbx]
0x18005d5ca  shr     eax, cl
0x18005d5cc  and     eax, 7
0x18005d5cf  mov     [rdi+rbp+40h], eax
0x18005d5d3  jnz     loc_18005D70C
0x18005d5d9  mov     r15d, 8
0x18005d5df  cmp     [rbx], r15d
0x18005d5e2  jnb     short loc_18005D5EF
0x18005d5e4  mov     edx, r15d
0x18005d5e7  mov     rcx, rbx
0x18005d5ea  call    FillBitCache
0x18005d5ef  add     dword ptr [rbx], 0FFFFFFF8h
0x18005d5f2  mov     eax, [rbx+4]
0x18005d5f5  mov     ecx, [rbx]
0x18005d5f7  shr     eax, cl
0x18005d5f9  movzx   eax, al
0x18005d5fc  mov     [rdi+rbp+44h], eax
0x18005d600  cmp     dword ptr [rdi+18h], 0
0x18005d604  jnz     short loc_18005D616
0x18005d606  test    r14d, r14d
0x18005d609  jz      short loc_18005D616
0x18005d60b  cmp     dword ptr [r12], 6
0x18005d610  jz      loc_18005D70C
0x18005d616  mov     edx, [rsp+58h+arg_0]
0x18005d61a  mov     r12d, 1
0x18005d620  add     edx, r12d
0x18005d623  mov     [rsp+58h+arg_0], edx
0x18005d627  add     r14d, r12d
0x18005d62a  jmp     loc_18005D44D
0x18005d62f  add     r13d, r12d
0x18005d632  jmp     loc_18005D40F
0x18005d637  cmp     [rbx], r12d
0x18005d63a  jnb     short loc_18005D647
0x18005d63c  mov     edx, r12d
0x18005d63f  mov     rcx, rbx
0x18005d642  call    FillBitCache
0x18005d647  mov     eax, [rbx+4]
0x18005d64a  or      ebp, 0FFFFFFFFh
0x18005d64d  add     [rbx], ebp
0x18005d64f  mov     ecx, [rbx]
0x18005d651  shr     eax, cl
0x18005d653  and     eax, r12d
0x18005d656  mov     [rdi+2Ch], eax
0x18005d659  jz      short loc_18005D6C2
0x18005d65b  cmp     [rdi+10h], r12d
0x18005d65f  jnz     short loc_18005D66E
0x18005d661  mov     rcx, rbx
0x18005d664  call    LatmGetValue
0x18005d669  mov     [rdi+30h], eax
0x18005d66c  jmp     short loc_18005D6C2
0x18005d66e  xor     eax, eax
0x18005d670  shl     eax, 8
0x18005d673  mov     [rdi+30h], eax
0x18005d676  cmp     [rbx], r12d
0x18005d679  jnb     short loc_18005D686
0x18005d67b  mov     edx, r12d
0x18005d67e  mov     rcx, rbx
0x18005d681  call    FillBitCache
0x18005d686  add     [rbx], ebp
0x18005d688  mov     ecx, [rbx]
0x18005d68a  mov     ebp, [rbx+4]
0x18005d68d  shr     ebp, cl
0x18005d68f  and     ebp, r12d
0x18005d692  cmp     ecx, r15d
0x18005d695  jnb     short loc_18005D6A2
0x18005d697  mov     edx, r15d
0x18005d69a  mov     rcx, rbx
0x18005d69d  call    FillBitCache
0x18005d6a2  add     dword ptr [rbx], 0FFFFFFF8h
0x18005d6a5  mov     ecx, [rbx]
0x18005d6a7  mov     eax, [rbx+4]
0x18005d6aa  shr     eax, cl
0x18005d6ac  movzx   ecx, al
0x18005d6af  mov     eax, [rdi+30h]
0x18005d6b2  add     eax, ecx
0x18005d6b4  test    ebp, ebp
0x18005d6b6  mov     [rdi+30h], eax
0x18005d6b9  mov     ebp, 0FFFFFFFFh
0x18005d6be  jnz     short loc_18005D670
0x18005d6c0  or      ebp, ebp
0x18005d6c2  cmp     [rbx], r12d
0x18005d6c5  jnb     short loc_18005D6D2
0x18005d6c7  mov     edx, r12d
0x18005d6ca  mov     rcx, rbx
0x18005d6cd  call    FillBitCache
0x18005d6d2  add     [rbx], ebp
0x18005d6d4  mov     eax, [rbx+4]
0x18005d6d7  mov     ecx, [rbx]
0x18005d6d9  shr     eax, cl
0x18005d6db  and     eax, r12d
0x18005d6de  mov     dword ptr [rdi+38h], 0
0x18005d6e5  mov     [rdi+34h], eax
  ... truncated ...
```
