# EncodeFaxLinesMmrCompression

- ea: `0x18003a074`
- end: `0x18003a468`
- name: `EncodeFaxLinesMmrCompression`
- size: `1012`
- prototype: `__int64 __fastcall(__int64, char *, unsigned int, unsigned int, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180035d78`

## callees

- `0x18003a074`
- `0x18003a5ec`
- `0x18003a6ac`
- `0x18003cc80`
- `0x18003cde4`
- `0x18003d4b2`

## pseudocode

```c
__int64 __fastcall EncodeFaxLinesMmrCompression(__int64 a1, char *a2, unsigned int a3, unsigned int a4, int *a5)
{
  char *v5; // r13
  unsigned int v9; // r14d
  unsigned int WhiteRun; // edi
  unsigned int v11; // ebp
  int v12; // edx
  int BlackRun; // eax
  unsigned int v14; // ecx
  int v15; // r8d
  unsigned int v16; // ecx
  unsigned int v17; // edx
  int v18; // eax
  char v19; // cl
  unsigned int v20; // r12d
  int v21; // eax
  unsigned int v22; // ecx
  int v23; // edx
  __int64 *v24; // r13
  __int64 *v25; // r8
  __int64 v26; // r12
  char v27; // bp
  int v28; // eax
  int v29; // eax
  unsigned int v30; // r13d
  int v31; // eax
  unsigned int v32; // edi
  __int64 result; // rax
  int v34; // edx
  char *v35; // [rsp+20h] [rbp-48h]
  unsigned int v36; // [rsp+70h] [rbp+8h]

  v5 = *(char **)(a1 + 32);
  v35 = v5;
  v36 = 0;
LABEL_2:
  if ( *(_QWORD *)(a1 + 1592) < *(_QWORD *)(a1 + 1608) || (unsigned int)GrowCompBitsBuffer(a1) )
  {
    v9 = 0;
    if ( *a2 >= 0 )
      WhiteRun = FindWhiteRun(a2, 0, a3);
    else
      WhiteRun = 0;
    if ( *v5 >= 0 )
      v11 = FindWhiteRun(v5, 0, a3);
    else
      v11 = 0;
    while ( *(_QWORD *)(a1 + 1592) < *(_QWORD *)(a1 + 1608) || (unsigned int)GrowCompBitsBuffer(a1) )
    {
      if ( (int)v11 < (int)a3 )
      {
        if ( (((unsigned __int8)v5[(__int64)(int)v11 >> 3] >> (~(_BYTE)v11 & 7)) & 1) != 0 )
          BlackRun = FindBlackRun(v5, v11, a3);
        else
          BlackRun = FindWhiteRun(v5, v11, a3);
        v12 = BlackRun + v11;
      }
      else
      {
        v12 = a3;
      }
      if ( v12 >= (int)WhiteRun )
      {
        v16 = WhiteRun - v11;
        if ( WhiteRun - v11 + 3 > 6 )
        {
          if ( (int)WhiteRun < (int)a3 )
          {
            if ( (((unsigned __int8)a2[(__int64)(int)WhiteRun >> 3] >> (~(_BYTE)WhiteRun & 7)) & 1) != 0 )
              v21 = FindBlackRun(a2, WhiteRun, a3);
            else
              v21 = FindWhiteRun(a2, WhiteRun, a3);
            v20 = v21 + WhiteRun;
          }
          else
          {
            v20 = a3;
          }
          v22 = *(_DWORD *)(a1 + 1584) - 3;
          *(_DWORD *)(a1 + 1580) |= 1 << (*(_BYTE *)(a1 + 1584) - 3);
          v23 = *(_DWORD *)(a1 + 1580);
          *(_DWORD *)(a1 + 1584) = v22;
          if ( v22 <= 0x10 )
          {
            *(_BYTE *)(*(_QWORD *)(a1 + 1592))++ = HIBYTE(v23);
            *(_BYTE *)(*(_QWORD *)(a1 + 1592))++ = *(_BYTE *)(a1 + 1582);
            *(_DWORD *)(a1 + 1580) <<= 16;
            *(_DWORD *)(a1 + 1584) += 16;
          }
          if ( WhiteRun && (((unsigned __int8)a2[(__int64)(int)v9 >> 3] >> (~(_BYTE)v9 & 7)) & 1) != 0 )
          {
            v24 = (__int64 *)::a5;
            v25 = qword_180044F40;
          }
          else
          {
            v24 = qword_180044F40;
            v25 = (__int64 *)::a5;
          }
          OutputRun(a1, WhiteRun - v9, v25);
          OutputRun(a1, v20 - WhiteRun, v24);
          v5 = v35;
          v9 = v20;
        }
        else
        {
          v17 = *(_DWORD *)(a1 + 1584) - *((unsigned __int16 *)&qword_1800450E0[1] + 2 * (int)v16 + 2);
          v18 = *((unsigned __int16 *)&qword_1800450E0[1] + 2 * (int)v16 + 3);
          v19 = *(_BYTE *)(a1 + 1584) - *((_WORD *)&qword_1800450E0[1] + 2 * (int)v16 + 2);
          *(_DWORD *)(a1 + 1584) = v17;
          *(_DWORD *)(a1 + 1580) |= v18 << v19;
          if ( v17 <= 0x10 )
          {
            *(_BYTE *)(*(_QWORD *)(a1 + 1592))++ = HIBYTE(*(_DWORD *)(a1 + 1580));
            *(_BYTE *)(*(_QWORD *)(a1 + 1592))++ = *(_BYTE *)(a1 + 1582);
            *(_DWORD *)(a1 + 1580) <<= 16;
            *(_DWORD *)(a1 + 1584) += 16;
          }
          v9 = WhiteRun;
        }
      }
      else
      {
        v14 = *(_DWORD *)(a1 + 1584) - 4;
        *(_DWORD *)(a1 + 1580) |= 1 << (*(_BYTE *)(a1 + 1584) - 4);
        v15 = *(_DWORD *)(a1 + 1580);
        *(_DWORD *)(a1 + 1584) = v14;
        if ( v14 <= 0x10 )
        {
          *(_BYTE *)(*(_QWORD *)(a1 + 1592))++ = HIBYTE(v15);
          *(_BYTE *)(*(_QWORD *)(a1 + 1592))++ = *(_BYTE *)(a1 + 1582);
          *(_DWORD *)(a1 + 1580) <<= 16;
          *(_DWORD *)(a1 + 1584) += 16;
        }
        v9 = v12;
      }
      if ( (int)v9 >= (int)a3 )
      {
        v32 = v36 + 1;
        v36 = v32;
        if ( v32 < a4 )
        {
          v5 = a2;
          v35 = a2;
          a2 += *(unsigned int *)(a1 + 1692);
          goto LABEL_2;
        }
        memcpy_0(*(void **)(a1 + 32), a2, (int)a3 / 8);
        result = 1;
        *(_DWORD *)(a1 + 848) += v32;
        v34 = *(_DWORD *)(a1 + 1592) - *(_DWORD *)(a1 + 1600);
        *a5 = v34;
        *(_DWORD *)(a1 + 856) = v34;
        return result;
      }
      v26 = (__int64)(int)v9 >> 3;
      v27 = ~(_BYTE)v9 & 7;
      if ( (((unsigned __int8)a2[v26] >> v27) & 1) != 0 )
        v28 = FindBlackRun(a2, v9, a3);
      else
        v28 = FindWhiteRun(a2, v9, a3);
      WhiteRun = v28 + v9;
      if ( (((unsigned __int8)a2[v26] >> v27) & 1) != 0 )
        v29 = FindWhiteRun(v5, v9, a3);
      else
        v29 = FindBlackRun(v5, v9, a3);
      v30 = v29 + v9;
      if ( (((unsigned __int8)a2[v26] >> v27) & 1) != 0 )
        v31 = FindBlackRun(v35, v30, a3);
      else
        v31 = FindWhiteRun(v35, v30, a3);
      v11 = v31 + v30;
      v5 = v35;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003a074  mov     [rsp+arg_8], rbx
0x18003a079  mov     [rsp+arg_18], r9d
0x18003a07e  push    rbp
0x18003a07f  push    rsi
0x18003a080  push    rdi
0x18003a081  push    r12
0x18003a083  push    r13
0x18003a085  push    r14
0x18003a087  push    r15
0x18003a089  sub     rsp, 30h
0x18003a08d  mov     r13, [rcx+20h]
0x18003a091  lea     r12, qword_1800450E0
0x18003a098  mov     [rsp+68h+var_48], r13
0x18003a09d  mov     esi, r8d
0x18003a0a0  mov     r15, rdx
0x18003a0a3  mov     [rsp+68h+arg_0], 0
0x18003a0ab  mov     rbx, rcx
0x18003a0ae  mov     rax, [rbx+648h]
0x18003a0b5  cmp     [rbx+638h], rax
0x18003a0bc  jb      short loc_18003A0CE
0x18003a0be  mov     rcx, rbx
0x18003a0c1  call    GrowCompBitsBuffer
0x18003a0c6  test    eax, eax
0x18003a0c8  jz      loc_18003A40D
0x18003a0ce  xor     r14d, r14d
0x18003a0d1  cmp     [r15], r14b
0x18003a0d4  jge     short loc_18003A0DA
0x18003a0d6  xor     edi, edi
0x18003a0d8  jmp     short loc_18003A0E9
0x18003a0da  mov     r8d, esi
0x18003a0dd  xor     edx, edx
0x18003a0df  mov     rcx, r15
0x18003a0e2  call    FindWhiteRun
0x18003a0e7  mov     edi, eax
0x18003a0e9  cmp     [r13+0], r14b
0x18003a0ed  jge     short loc_18003A0F3
0x18003a0ef  xor     ebp, ebp
0x18003a0f1  jmp     short loc_18003A102
0x18003a0f3  mov     r8d, esi
0x18003a0f6  xor     edx, edx
0x18003a0f8  mov     rcx, r13
0x18003a0fb  call    FindWhiteRun
0x18003a100  mov     ebp, eax
0x18003a102  mov     rcx, [rbx+648h]
0x18003a109  cmp     [rbx+638h], rcx
0x18003a110  jb      short loc_18003A122
0x18003a112  mov     rcx, rbx
0x18003a115  call    GrowCompBitsBuffer
0x18003a11a  test    eax, eax
0x18003a11c  jz      loc_18003A40D
0x18003a122  cmp     ebp, esi
0x18003a124  jl      short loc_18003A12A
0x18003a126  mov     edx, esi
0x18003a128  jmp     short loc_18003A15A
0x18003a12a  mov     cl, bpl
0x18003a12d  movsxd  rax, ebp
0x18003a130  sar     rax, 3
0x18003a134  not     cl
0x18003a136  and     cl, 7
0x18003a139  mov     r8d, esi
0x18003a13c  mov     edx, ebp
0x18003a13e  mov     al, [rax+r13]
0x18003a142  shr     al, cl
0x18003a144  mov     rcx, r13
0x18003a147  test    al, 1
0x18003a149  jz      short loc_18003A152
0x18003a14b  call    FindBlackRun
0x18003a150  jmp     short loc_18003A157
0x18003a152  call    FindWhiteRun
0x18003a157  lea     edx, [rax+rbp]
0x18003a15a  cmp     edx, edi
0x18003a15c  jge     short loc_18003A1C7
0x18003a15e  mov     ecx, [rbx+630h]
0x18003a164  mov     eax, 1
0x18003a169  add     ecx, 0FFFFFFFCh
0x18003a16c  shl     eax, cl
0x18003a16e  or      [rbx+62Ch], eax
0x18003a174  mov     r8d, [rbx+62Ch]
0x18003a17b  mov     [rbx+630h], ecx
0x18003a181  cmp     ecx, 10h
0x18003a184  ja      short loc_18003A1BF
0x18003a186  mov     rax, [rbx+638h]
0x18003a18d  shr     r8d, 18h
0x18003a191  mov     [rax], r8b
0x18003a194  inc     qword ptr [rbx+638h]
0x18003a19b  mov     rcx, [rbx+638h]
0x18003a1a2  mov     al, [rbx+62Eh]
0x18003a1a8  mov     [rcx], al
0x18003a1aa  inc     qword ptr [rbx+638h]
0x18003a1b1  shl     dword ptr [rbx+62Ch], 10h
0x18003a1b8  add     dword ptr [rbx+630h], 10h
0x18003a1bf  mov     r14d, edx
0x18003a1c2  jmp     loc_18003A345
0x18003a1c7  mov     ecx, edi
0x18003a1c9  sub     ecx, ebp
0x18003a1cb  lea     eax, [rcx+3]
0x18003a1ce  cmp     eax, 6
0x18003a1d1  ja      short loc_18003A244
0x18003a1d3  mov     edx, [rbx+630h]
0x18003a1d9  movsxd  rcx, ecx
0x18003a1dc  movzx   eax, word ptr [r12+rcx*4+0Ch]
0x18003a1e2  sub     edx, eax
0x18003a1e4  movzx   eax, word ptr [r12+rcx*4+0Eh]
0x18003a1ea  mov     ecx, edx
0x18003a1ec  mov     [rbx+630h], edx
0x18003a1f2  shl     eax, cl
0x18003a1f4  or      [rbx+62Ch], eax
0x18003a1fa  mov     ecx, [rbx+62Ch]
0x18003a200  cmp     edx, 10h
0x18003a203  ja      short loc_18003A23C
0x18003a205  mov     rax, [rbx+638h]
0x18003a20c  shr     ecx, 18h
0x18003a20f  mov     [rax], cl
0x18003a211  inc     qword ptr [rbx+638h]
0x18003a218  mov     rcx, [rbx+638h]
0x18003a21f  mov     al, [rbx+62Eh]
0x18003a225  mov     [rcx], al
0x18003a227  inc     qword ptr [rbx+638h]
0x18003a22e  shl     dword ptr [rbx+62Ch], 10h
0x18003a235  add     dword ptr [rbx+630h], 10h
0x18003a23c  mov     r14d, edi
0x18003a23f  jmp     loc_18003A345
0x18003a244  cmp     edi, esi
0x18003a246  jl      short loc_18003A24D
0x18003a248  mov     r12d, esi
0x18003a24b  jmp     short loc_18003A27E
0x18003a24d  mov     cl, dil
0x18003a250  movsxd  rax, edi
0x18003a253  sar     rax, 3
0x18003a257  not     cl
0x18003a259  and     cl, 7
0x18003a25c  mov     r8d, esi
0x18003a25f  mov     edx, edi
0x18003a261  mov     al, [rax+r15]
0x18003a265  shr     al, cl
0x18003a267  mov     rcx, r15
0x18003a26a  test    al, 1
0x18003a26c  jz      short loc_18003A275
0x18003a26e  call    FindBlackRun
0x18003a273  jmp     short loc_18003A27A
0x18003a275  call    FindWhiteRun
0x18003a27a  lea     r12d, [rax+rdi]
0x18003a27e  mov     ecx, [rbx+630h]
0x18003a284  mov     eax, 1
0x18003a289  add     ecx, 0FFFFFFFDh
0x18003a28c  shl     eax, cl
0x18003a28e  or      [rbx+62Ch], eax
0x18003a294  mov     edx, [rbx+62Ch]
0x18003a29a  mov     [rbx+630h], ecx
0x18003a2a0  cmp     ecx, 10h
0x18003a2a3  ja      short loc_18003A2DC
0x18003a2a5  mov     rax, [rbx+638h]
0x18003a2ac  shr     edx, 18h
0x18003a2af  mov     [rax], dl
0x18003a2b1  inc     qword ptr [rbx+638h]
0x18003a2b8  mov     rcx, [rbx+638h]
0x18003a2bf  mov     al, [rbx+62Eh]
0x18003a2c5  mov     [rcx], al
0x18003a2c7  inc     qword ptr [rbx+638h]
0x18003a2ce  shl     dword ptr [rbx+62Ch], 10h
0x18003a2d5  add     dword ptr [rbx+630h], 10h
0x18003a2dc  test    edi, edi
0x18003a2de  jz      short loc_18003A309
0x18003a2e0  movsxd  rax, r14d
0x18003a2e3  mov     cl, r14b
0x18003a2e6  sar     rax, 3
0x18003a2ea  not     cl
0x18003a2ec  and     cl, 7
0x18003a2ef  mov     al, [rax+r15]
0x18003a2f3  shr     al, cl
0x18003a2f5  test    al, 1
0x18003a2f7  jz      short loc_18003A309
0x18003a2f9  lea     r13, a5; "\b5"
0x18003a300  lea     r8, qword_180044F40
0x18003a307  jmp     short loc_18003A317
0x18003a309  lea     r13, qword_180044F40
0x18003a310  lea     r8, a5; "\b5"
0x18003a317  mov     ebp, r12d
0x18003a31a  mov     rcx, rbx
0x18003a31d  sub     ebp, edi
0x18003a31f  sub     edi, r14d
0x18003a322  mov     edx, edi
0x18003a324  call    OutputRun
0x18003a329  mov     r8, r13
0x18003a32c  mov     edx, ebp
0x18003a32e  mov     rcx, rbx
0x18003a331  call    OutputRun
0x18003a336  mov     r13, [rsp+68h+var_48]
0x18003a33b  mov     r14d, r12d
0x18003a33e  lea     r12, qword_1800450E0
0x18003a345  cmp     r14d, esi
0x18003a348  jge     loc_18003A3E4
0x18003a34e  movsxd  r12, r14d
0x18003a351  mov     bpl, r14b
0x18003a354  sar     r12, 3
0x18003a358  not     bpl
0x18003a35b  and     bpl, 7
0x18003a35f  mov     r8d, esi
0x18003a362  mov     cl, bpl
0x18003a365  mov     edx, r14d
0x18003a368  mov     al, [r12+r15]
0x18003a36c  shr     al, cl
0x18003a36e  mov     rcx, r15
0x18003a371  test    al, 1
0x18003a373  jz      short loc_18003A37C
0x18003a375  call    FindBlackRun
0x18003a37a  jmp     short loc_18003A381
0x18003a37c  call    FindWhiteRun
0x18003a381  lea     edi, [rax+r14]
0x18003a385  mov     cl, bpl
0x18003a388  mov     al, [r12+r15]
0x18003a38c  mov     r8d, esi
0x18003a38f  shr     al, cl
0x18003a391  mov     edx, r14d
0x18003a394  mov     rcx, r13
0x18003a397  test    al, 1
0x18003a399  jnz     short loc_18003A3A2
0x18003a39b  call    FindBlackRun
0x18003a3a0  jmp     short loc_18003A3A7
0x18003a3a2  call    FindWhiteRun
0x18003a3a7  lea     r13d, [rax+r14]
0x18003a3ab  mov     cl, bpl
0x18003a3ae  mov     al, [r12+r15]
0x18003a3b2  mov     r8d, esi
0x18003a3b5  shr     al, cl
0x18003a3b7  mov     edx, r13d
0x18003a3ba  mov     rcx, [rsp+68h+var_48]
0x18003a3bf  test    al, 1
0x18003a3c1  jz      short loc_18003A3CA
0x18003a3c3  call    FindBlackRun
0x18003a3c8  jmp     short loc_18003A3CF
0x18003a3ca  call    FindWhiteRun
0x18003a3cf  lea     ebp, [rax+r13]
0x18003a3d3  mov     r13, [rsp+68h+var_48]
0x18003a3d8  lea     r12, qword_1800450E0
0x18003a3df  jmp     loc_18003A102
0x18003a3e4  mov     edi, [rsp+68h+arg_0]
0x18003a3e8  inc     edi
0x18003a3ea  mov     [rsp+68h+arg_0], edi
0x18003a3ee  cmp     edi, [rsp+68h+arg_18]
0x18003a3f5  jnb     short loc_18003A411
0x18003a3f7  mov     eax, [rbx+69Ch]
0x18003a3fd  mov     r13, r15
0x18003a400  mov     [rsp+68h+var_48], r15
0x18003a405  add     r15, rax
0x18003a408  jmp     loc_18003A0AE
0x18003a40d  xor     eax, eax
0x18003a40f  jmp     short loc_18003A452
0x18003a411  mov     rcx, [rbx+20h]; void *
0x18003a415  mov     eax, esi
0x18003a417  cdq
0x18003a418  and     edx, 7
0x18003a41b  add     eax, edx
0x18003a41d  mov     rdx, r15; Src
0x18003a420  sar     eax, 3
0x18003a423  movsxd  r8, eax; Size
0x18003a426  call    memcpy_0
0x18003a42b  mov     rcx, [rsp+68h+arg_20]
0x18003a433  mov     eax, 1
0x18003a438  add     [rbx+350h], edi
0x18003a43e  mov     edx, [rbx+638h]
0x18003a444  sub     edx, [rbx+640h]
0x18003a44a  mov     [rcx], edx
0x18003a44c  mov     [rbx+358h], edx
0x18003a452  mov     rbx, [rsp+68h+arg_8]
0x18003a457  add     rsp, 30h
0x18003a45b  pop     r15
0x18003a45d  pop     r14
0x18003a45f  pop     r13
0x18003a461  pop     r12
0x18003a463  pop     rdi
0x18003a464  pop     rsi
0x18003a465  pop     rbp
0x18003a466  retn
```
