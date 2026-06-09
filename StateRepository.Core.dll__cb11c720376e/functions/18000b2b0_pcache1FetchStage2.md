# pcache1FetchStage2

- ea: `0x18000b2b0`
- end: `0x18000b564`
- name: `pcache1FetchStage2`
- size: `692`
- prototype: `__int64 __fastcall(__int64 *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000b240`

## callees

- `0x1800089f0`
- `0x18000b0dc`
- `0x18000b2b0`
- `0x18000bf20`
- `0x18000c00c`
- `0x18009a010`

## pseudocode

```c
__int64 __fastcall pcache1FetchStage2(__int64 *a1, unsigned int a2, __int64 a3)
{
  __int64 v3; // rbp
  __int64 v5; // rdx
  __int64 v7; // rcx
  int v8; // r14d
  int v9; // r10d
  int v10; // r11d
  __int64 v11; // r9
  __int64 v12; // rbp
  __int64 v13; // r9
  __int64 *v14; // rdx
  __int64 i; // rax
  __int64 v16; // rax
  __int64 v17; // rcx
  unsigned int v18; // edx
  __int64 v19; // rdx
  _QWORD *v20; // rax
  unsigned int v22; // edi
  int v23; // eax

  v3 = *a1;
  v5 = *((unsigned int *)a1 + 14);
  v7 = (unsigned int)dword_1800B5CDC;
  v8 = a3;
  v9 = dword_1800B5CB0;
  v10 = dword_1800B5CAC;
  v11 = DWORD2(xmmword_1800B5AE0);
  if ( (_DWORD)a3 == 1 )
  {
    v22 = *((_DWORD *)a1 + 13);
    a3 = (unsigned int)v5 - v22;
    if ( (unsigned int)a3 >= *(_DWORD *)(v3 + 16) || (unsigned int)a3 >= *((_DWORD *)a1 + 10) )
      return 0;
    if ( !dword_1800B5CB0 || (v23 = dword_1800B5CDC, *((_DWORD *)a1 + 4) + *((_DWORD *)a1 + 5) > dword_1800B5CAC) )
      v23 = DWORD2(xmmword_1800B5AE0);
    if ( v23 && v22 < (unsigned int)a3 )
      return 0;
  }
  if ( (unsigned int)v5 >= *((_DWORD *)a1 + 15) )
  {
    pcache1ResizeHash(a1);
    v7 = (unsigned int)dword_1800B5CDC;
    v9 = dword_1800B5CB0;
    v10 = dword_1800B5CAC;
    v11 = DWORD2(xmmword_1800B5AE0);
  }
  if ( *((_DWORD *)a1 + 7) )
  {
    a3 = *(_QWORD *)(v3 + 72);
    if ( !*(_WORD *)(a3 + 22) )
    {
      if ( (unsigned int)(*((_DWORD *)a1 + 14) + 1) >= *((_DWORD *)a1 + 9) )
        goto LABEL_19;
      if ( !v9 || *((_DWORD *)a1 + 4) + *((_DWORD *)a1 + 5) > v10 )
        v7 = (unsigned int)v11;
      if ( (_DWORD)v7 )
      {
LABEL_19:
        v13 = *(_QWORD *)(a3 + 32);
        v14 = (__int64 *)(*(_QWORD *)(v13 + 64) + 8LL * (unsigned int)(*(_DWORD *)(a3 + 16) % *(_DWORD *)(v13 + 60)));
        for ( i = *v14; i != a3; i = *(_QWORD *)(i + 24) )
          v14 = (__int64 *)(i + 24);
        *v14 = *(_QWORD *)(i + 24);
        --*(_DWORD *)(v13 + 56);
        *(_QWORD *)(*(_QWORD *)(a3 + 48) + 40LL) = *(_QWORD *)(a3 + 40);
        *(_QWORD *)(*(_QWORD *)(a3 + 40) + 48LL) = *(_QWORD *)(a3 + 48);
        v16 = *(_QWORD *)(a3 + 32);
        *(_QWORD *)(a3 + 40) = 0;
        --*(_DWORD *)(v16 + 52);
        v17 = *(_QWORD *)(a3 + 32);
        if ( *(_DWORD *)(v17 + 24) == *((_DWORD *)a1 + 6) )
        {
          *(_DWORD *)(v3 + 20) += *((_DWORD *)a1 + 7) - *(_DWORD *)(v17 + 28);
          goto LABEL_23;
        }
        pcache1FreePage(a3);
      }
    }
  }
  if ( a1[9] || !*((_DWORD *)a1 + 14) && (unsigned int)pcache1InitBulk(a1, v5, a3, v11) )
  {
    a3 = a1[9];
    a1[9] = *(_QWORD *)(a3 + 24);
    *(_QWORD *)(a3 + 24) = 0;
LABEL_17:
    ++*(_DWORD *)a1[1];
    if ( !a3 )
      return a3;
LABEL_23:
    ++*((_DWORD *)a1 + 14);
    v18 = a2 % *((_DWORD *)a1 + 15);
    *(_DWORD *)(a3 + 16) = a2;
    v19 = 8LL * v18;
    v20 = *(_QWORD **)(a3 + 8);
    *(_QWORD *)(a3 + 24) = *(_QWORD *)(v19 + a1[8]);
    *(_QWORD *)(a3 + 32) = a1;
    *(_QWORD *)(a3 + 40) = 0;
    *v20 = 0;
    *(_QWORD *)(v19 + a1[8]) = a3;
    if ( a2 > *((_DWORD *)a1 + 11) )
      *((_DWORD *)a1 + 11) = a2;
    return a3;
  }
  if ( v8 == 1 && qword_1800B5AF8 )
  {
    qword_1800B5AF8(v7, v5, a3, v11);
    v12 = pcache1Alloc(*((_DWORD *)a1 + 6));
  }
  else
  {
    v12 = pcache1Alloc(*((_DWORD *)a1 + 6));
    if ( v8 != 1 )
      goto LABEL_15;
  }
  if ( qword_1800B5B00 )
    qword_1800B5B00();
LABEL_15:
  if ( v12 )
  {
    a3 = v12 + *((int *)a1 + 4);
    *(_QWORD *)a3 = v12;
    *(_QWORD *)(a3 + 8) = a3 + 56;
    *(_DWORD *)(a3 + 20) = 0;
    *(_QWORD *)(a3 + 48) = 0;
    goto LABEL_17;
  }
  return 0;
}

```

## disassembly

```asm
0x18000b2b0  push    rbx
0x18000b2b2  push    rbp
0x18000b2b3  push    rsi
0x18000b2b4  push    rdi
0x18000b2b5  push    r14
0x18000b2b7  sub     rsp, 20h
0x18000b2bb  mov     rbp, [rcx]
0x18000b2be  mov     esi, edx
0x18000b2c0  mov     edx, [rcx+38h]
0x18000b2c3  mov     rbx, rcx
0x18000b2c6  mov     ecx, cs:dword_1800B5CDC
0x18000b2cc  mov     r14d, r8d
0x18000b2cf  mov     r10d, cs:dword_1800B5CB0
0x18000b2d6  mov     r11d, cs:dword_1800B5CAC
0x18000b2dd  mov     r9d, dword ptr cs:xmmword_1800B5AE0+8
0x18000b2e4  cmp     r8d, 1
0x18000b2e8  jz      loc_18000B48F
0x18000b2ee  cmp     edx, [rbx+3Ch]
0x18000b2f1  jnb     loc_18000B467
0x18000b2f7  cmp     dword ptr [rbx+1Ch], 0
0x18000b2fb  jz      short loc_18000B327
0x18000b2fd  mov     r8, [rbp+48h]
0x18000b301  cmp     word ptr [r8+16h], 0
0x18000b307  jnz     short loc_18000B327
0x18000b309  mov     eax, [rbx+38h]
0x18000b30c  inc     eax
0x18000b30e  cmp     eax, [rbx+24h]
0x18000b311  jnb     loc_18000B3A0
0x18000b317  test    r10d, r10d
0x18000b31a  jnz     loc_18000B543
0x18000b320  mov     ecx, r9d
0x18000b323  test    ecx, ecx
0x18000b325  jnz     short loc_18000B3A0
0x18000b327  xor     edi, edi
0x18000b329  cmp     qword ptr [rbx+48h], 0
0x18000b32e  jnz     loc_18000B4CE
0x18000b334  cmp     dword ptr [rbx+38h], 0
0x18000b338  jnz     short loc_18000B34A
0x18000b33a  mov     rcx, rbx
0x18000b33d  call    pcache1InitBulk
0x18000b342  test    eax, eax
0x18000b344  jnz     loc_18000B4CE
0x18000b34a  cmp     r14d, 1
0x18000b34e  jz      loc_18000B4FD
0x18000b354  mov     ecx, [rbx+18h]
0x18000b357  call    pcache1Alloc
0x18000b35c  mov     rbp, rax
0x18000b35f  cmp     r14d, 1
0x18000b363  jz      loc_18000B4E3
0x18000b369  test    rbp, rbp
0x18000b36c  jz      loc_18000B51F
0x18000b372  movsxd  r8, dword ptr [rbx+10h]
0x18000b376  add     r8, rbp
0x18000b379  lea     rax, [r8+38h]
0x18000b37d  mov     [r8], rbp
0x18000b380  mov     [r8+8], rax
0x18000b384  mov     dword ptr [r8+14h], 0
0x18000b38c  mov     [r8+30h], rdi
0x18000b390  mov     rax, [rbx+8]
0x18000b394  inc     dword ptr [rax]
0x18000b396  test    r8, r8
0x18000b399  jnz     short loc_18000B416
0x18000b39b  jmp     loc_18000B454
0x18000b3a0  mov     r9, [r8+20h]
0x18000b3a4  xor     edx, edx
0x18000b3a6  mov     eax, [r8+10h]
0x18000b3aa  div     dword ptr [r9+3Ch]
0x18000b3ae  mov     rax, [r9+40h]
0x18000b3b2  lea     rdx, [rax+rdx*8]
0x18000b3b6  mov     rax, [rdx]
0x18000b3b9  cmp     rax, r8
0x18000b3bc  jz      short loc_18000B3CD
0x18000b3be  xchg    ax, ax
0x18000b3c0  lea     rdx, [rax+18h]
0x18000b3c4  mov     rax, [rax+18h]
0x18000b3c8  cmp     rax, r8
0x18000b3cb  jnz     short loc_18000B3C0
0x18000b3cd  mov     rax, [rax+18h]
0x18000b3d1  xor     edi, edi
0x18000b3d3  mov     [rdx], rax
0x18000b3d6  dec     dword ptr [r9+38h]
0x18000b3da  mov     rax, [r8+28h]
0x18000b3de  mov     rdx, [r8+30h]
0x18000b3e2  mov     [rdx+28h], rax
0x18000b3e6  mov     rdx, [r8+28h]
0x18000b3ea  mov     rax, [r8+30h]
0x18000b3ee  mov     [rdx+30h], rax
0x18000b3f2  mov     rax, [r8+20h]
0x18000b3f6  mov     [r8+28h], rdi
0x18000b3fa  dec     dword ptr [rax+34h]
0x18000b3fd  mov     rcx, [r8+20h]
0x18000b401  mov     eax, [rbx+18h]
0x18000b404  cmp     [rcx+18h], eax
0x18000b407  jnz     loc_18000B557
0x18000b40d  mov     eax, [rbx+1Ch]
0x18000b410  sub     eax, [rcx+1Ch]
0x18000b413  add     [rbp+14h], eax
0x18000b416  inc     dword ptr [rbx+38h]
0x18000b419  xor     edx, edx
0x18000b41b  mov     eax, esi
0x18000b41d  div     dword ptr [rbx+3Ch]
0x18000b420  mov     [r8+10h], esi
0x18000b424  mov     rax, [rbx+40h]
0x18000b428  lea     rdx, ds:0[rdx*8]
0x18000b430  mov     rcx, [rdx+rax]
0x18000b434  mov     rax, [r8+8]
0x18000b438  mov     [r8+18h], rcx
0x18000b43c  mov     [r8+20h], rbx
0x18000b440  mov     [r8+28h], rdi
0x18000b444  mov     [rax], rdi
0x18000b447  mov     rax, [rbx+40h]
0x18000b44b  mov     [rdx+rax], r8
0x18000b44f  cmp     esi, [rbx+2Ch]
0x18000b452  ja      short loc_18000B462
0x18000b454  mov     rax, r8
0x18000b457  add     rsp, 20h
0x18000b45b  pop     r14
0x18000b45d  pop     rdi
0x18000b45e  pop     rsi
0x18000b45f  pop     rbp
0x18000b460  pop     rbx
0x18000b461  retn
0x18000b462  mov     [rbx+2Ch], esi
0x18000b465  jmp     short loc_18000B454
0x18000b467  mov     rcx, rbx
0x18000b46a  call    pcache1ResizeHash
0x18000b46f  mov     ecx, cs:dword_1800B5CDC
0x18000b475  mov     r10d, cs:dword_1800B5CB0
0x18000b47c  mov     r11d, cs:dword_1800B5CAC
0x18000b483  mov     r9d, dword ptr cs:xmmword_1800B5AE0+8
0x18000b48a  jmp     loc_18000B2F7
0x18000b48f  mov     edi, [rbx+34h]
0x18000b492  mov     r8d, edx
0x18000b495  sub     r8d, edi
0x18000b498  cmp     r8d, [rbp+10h]
0x18000b49c  jnb     short loc_18000B4C1
0x18000b49e  cmp     r8d, [rbx+28h]
0x18000b4a2  jnb     short loc_18000B4C1
0x18000b4a4  test    r10d, r10d
0x18000b4a7  jnz     loc_18000B52D
0x18000b4ad  mov     eax, r9d
0x18000b4b0  test    eax, eax
0x18000b4b2  jz      loc_18000B2EE
0x18000b4b8  cmp     edi, r8d
0x18000b4bb  jnb     loc_18000B2EE
0x18000b4c1  xor     eax, eax
0x18000b4c3  add     rsp, 20h
0x18000b4c7  pop     r14
0x18000b4c9  pop     rdi
0x18000b4ca  pop     rsi
0x18000b4cb  pop     rbp
0x18000b4cc  pop     rbx
0x18000b4cd  retn
0x18000b4ce  mov     r8, [rbx+48h]
0x18000b4d2  mov     rax, [r8+18h]
0x18000b4d6  mov     [rbx+48h], rax
0x18000b4da  mov     [r8+18h], rdi
0x18000b4de  jmp     loc_18000B390
0x18000b4e3  mov     rax, cs:qword_1800B5B00
0x18000b4ea  test    rax, rax
0x18000b4ed  jz      loc_18000B369
0x18000b4f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4f8  jmp     loc_18000B369
0x18000b4fd  mov     rax, cs:qword_1800B5AF8
0x18000b504  test    rax, rax
0x18000b507  jz      loc_18000B354
0x18000b50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b512  mov     ecx, [rbx+18h]
0x18000b515  call    pcache1Alloc
0x18000b51a  mov     rbp, rax
0x18000b51d  jmp     short loc_18000B4E3
0x18000b51f  mov     rax, rdi
0x18000b522  add     rsp, 20h
0x18000b526  pop     r14
0x18000b528  pop     rdi
0x18000b529  pop     rsi
0x18000b52a  pop     rbp
0x18000b52b  pop     rbx
0x18000b52c  retn
0x18000b52d  mov     eax, [rbx+14h]
0x18000b530  add     eax, [rbx+10h]
0x18000b533  cmp     eax, r11d
0x18000b536  mov     eax, ecx
0x18000b538  jle     loc_18000B4B0
0x18000b53e  jmp     loc_18000B4AD
0x18000b543  mov     eax, [rbx+14h]
0x18000b546  add     eax, [rbx+10h]
0x18000b549  cmp     eax, r11d
0x18000b54c  jle     loc_18000B323
0x18000b552  jmp     loc_18000B320
0x18000b557  mov     rcx, r8
0x18000b55a  call    pcache1FreePage
0x18000b55f  jmp     loc_18000B329
```
