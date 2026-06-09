# BufferedRead

- ea: `0x180003f50`
- end: `0x1800041b9`
- name: `BufferedRead`
- size: `617`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, char *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180003f50`
- `0x180014880`
- `0x180017365`

## import_xrefs

- `WINMM!mmioSeek` at `0x1800040ff`
- `WINMM!mmioSeek` at `0x1800040ff`

## pseudocode

```c
__int64 __fastcall BufferedRead(__int64 a1, int a2, unsigned int a3, char *a4)
{
  char *v4; // r15
  int v5; // r14d
  __int64 v9; // rbx
  __int64 v10; // rax
  int v11; // ecx
  int *v12; // r8
  int v13; // edx
  LONG v14; // r9d
  int v15; // ecx
  int v16; // r10d
  bool v17; // zf
  int v18; // eax
  LONG *v19; // r11
  unsigned int *v20; // rdi
  int v21; // edx
  __int64 v22; // r13
  int *v23; // r8
  int v24; // r15d
  int *v25; // r9
  int v26; // r10d
  LONG v27; // r8d
  signed int v28; // eax
  __int64 v29; // rcx
  LONG v30; // edx
  __int64 v31; // rax
  int v32; // edx
  int v33; // ecx
  int v34; // edi
  char *v36; // [rsp+88h] [rbp+20h]

  v36 = a4;
  v4 = a4;
  v5 = a3;
  if ( (int)a3 <= 0 )
    return a3;
LABEL_2:
  if ( a2 >= *(_DWORD *)(a1 + 44) )
    return a3;
  LODWORD(v9) = 0;
  while ( (int)v9 < *(_DWORD *)a1 )
  {
    v10 = 16LL * (unsigned int)v9;
    v11 = *(_DWORD *)(v10 + a1 + 56);
    if ( v11 >= 0 && v11 <= a2 && *(_DWORD *)(v10 + a1 + 60) + v11 > a2 )
    {
LABEL_42:
      v32 = *(_DWORD *)(a1 + 16LL * (int)v9 + 56);
      if ( v32 < 0 )
        return 0;
      if ( a2 < v32 )
        return 0;
      v33 = *(_DWORD *)(a1 + 16LL * (int)v9 + 60);
      if ( a2 - v32 > v33 )
        return 0;
      v34 = v5;
      if ( v5 >= v33 - a2 + v32 )
        v34 = v33 - a2 + v32;
      memmove_0(
        v4,
        (const void *)(a2 + *(_QWORD *)(a1 + 16 * ((int)v9 + 4LL)) - *(int *)(a1 + 16LL * (int)v9 + 56)),
        v34);
      v4 += v34;
      v5 -= v34;
      a2 += v34;
      v36 = v4;
      if ( v5 <= 0 )
        return a3;
      goto LABEL_2;
    }
    LODWORD(v9) = v9 + 1;
  }
  v12 = *(int **)(a1 + 32);
  v9 = *(int *)(a1 + 48);
  if ( !v12 )
    goto LABEL_34;
  v13 = *(_DWORD *)(a1 + 40);
  v14 = 0;
  v15 = 0;
  if ( v13 < 0 )
  {
LABEL_19:
    v17 = v13 == *v12;
  }
  else
  {
    v16 = 0;
    while ( 1 )
    {
      v17 = v13 == *v12;
      if ( v13 >= *v12 )
        break;
      if ( v16 >= *v12 )
        goto LABEL_21;
      v14 = v12[3 * v13 + 3];
      v15 = v12[3 * v13 + 4] + 8;
      if ( v14 <= a2 && a2 < v15 + v14 )
        goto LABEL_21;
      v18 = -1;
      if ( a2 >= v14 )
        v18 = 1;
      ++v16;
      v13 += v18;
      if ( v13 < 0 )
        goto LABEL_19;
    }
  }
  if ( v17 )
  {
LABEL_34:
    v27 = a2 - a2 % *(_DWORD *)(a1 + 4);
    v19 = (LONG *)(16 * v9 + a1 + 56);
    v20 = (unsigned int *)(16 * v9 + a1 + 60);
    v22 = *(int *)(a1 + 48);
    *v19 = v27;
    v28 = *(_DWORD *)(a1 + 44) - v27;
    if ( v28 >= *(_DWORD *)(a1 + 4) )
      v28 = *(_DWORD *)(a1 + 4);
    *v20 = v28;
    goto LABEL_37;
  }
LABEL_21:
  if ( v13 < 0 || v15 > *(_DWORD *)(a1 + 4) )
    goto LABEL_34;
  v19 = (LONG *)(16 * v9 + a1 + 56);
  v20 = (unsigned int *)(16 * v9 + a1 + 60);
  v21 = v13 + 1;
  v22 = *(int *)(a1 + 48);
  *v19 = v14;
  *v20 = v15;
  v23 = *(int **)(a1 + 32);
  if ( v21 >= *v23 )
  {
    v25 = *(int **)(a1 + 32);
    goto LABEL_31;
  }
  v24 = *(_DWORD *)(16 * v9 + a1 + 56);
  while ( v23[3 * v21 + 3] < v15 + v24 )
  {
LABEL_29:
    v23 = *(int **)(a1 + 32);
    ++v21;
    v25 = v23;
    if ( v21 >= *v23 )
      goto LABEL_30;
  }
  v25 = v23;
  if ( v23[3 * v21 + 3] == v15 + v24 )
  {
    v26 = v23[3 * v21 + 4] + 8;
    if ( v26 <= *(_DWORD *)(a1 + 4) - v15 )
    {
      v15 += v26;
      *v20 = v15;
      goto LABEL_29;
    }
  }
LABEL_30:
  v4 = v36;
LABEL_31:
  if ( v21 < *v25 )
    *(_DWORD *)(a1 + 40) = v21;
LABEL_37:
  v29 = *(_QWORD *)(a1 + 16);
  v30 = *v19;
  v31 = *(_QWORD *)(v29 + 16);
  if ( v31 )
    *(_DWORD *)(v31 + 372) = v30;
  else
    mmioSeek(*(HMMIO *)(v29 + 8), v30, 0);
  if ( shfileRead(*(_QWORD *)(a1 + 16), *(char **)(a1 + 16 * (v22 + 4)), *v20) == *v20 )
  {
    *(_DWORD *)(a1 + 48) = ((int)v9 + 1) % *(_DWORD *)a1;
    goto LABEL_42;
  }
  return 0;
}

```

## disassembly

```asm
0x180003f50  mov     [rsp+arg_18], r9
0x180003f55  push    rbx
0x180003f56  push    rbp
0x180003f57  push    rsi
0x180003f58  push    rdi
0x180003f59  push    r12
0x180003f5b  push    r13
0x180003f5d  push    r14
0x180003f5f  push    r15
0x180003f61  sub     rsp, 28h
0x180003f65  mov     r15, r9
0x180003f68  mov     r14d, r8d
0x180003f6b  mov     ebp, edx
0x180003f6d  mov     rsi, rcx
0x180003f70  mov     r12d, r8d
0x180003f73  test    r8d, r8d
0x180003f76  jle     loc_1800041A1
0x180003f7c  mov     r11d, 1
0x180003f82  cmp     ebp, [rsi+2Ch]
0x180003f85  jge     loc_1800041A1
0x180003f8b  xor     ebx, ebx
0x180003f8d  cmp     ebx, [rsi]
0x180003f8f  jge     short loc_180003FB4
0x180003f91  mov     eax, ebx
0x180003f93  shl     rax, 4
0x180003f97  mov     ecx, [rax+rsi+38h]
0x180003f9b  test    ecx, ecx
0x180003f9d  js      short loc_180003FAF
0x180003f9f  cmp     ecx, ebp
0x180003fa1  jg      short loc_180003FAF
0x180003fa3  add     ecx, [rax+rsi+3Ch]
0x180003fa7  cmp     ecx, ebp
0x180003fa9  jg      loc_18000412D
0x180003faf  add     ebx, r11d
0x180003fb2  jmp     short loc_180003F8D
0x180003fb4  mov     r8, [rsi+20h]
0x180003fb8  movsxd  rbx, dword ptr [rsi+30h]
0x180003fbc  test    r8, r8
0x180003fbf  jz      loc_1800040AA
0x180003fc5  mov     edx, [rsi+28h]
0x180003fc8  xor     r9d, r9d
0x180003fcb  xor     ecx, ecx
0x180003fcd  test    edx, edx
0x180003fcf  js      short loc_18000400F
0x180003fd1  xor     r10d, r10d
0x180003fd4  cmp     edx, [r8]
0x180003fd7  jge     short loc_180004012
0x180003fd9  cmp     r10d, [r8]
0x180003fdc  jge     short loc_180004018
0x180003fde  mov     eax, edx
0x180003fe0  lea     rcx, [rax+rax*2]
0x180003fe4  mov     r9d, [r8+rcx*4+0Ch]
0x180003fe9  mov     ecx, [r8+rcx*4+10h]
0x180003fee  add     ecx, 8
0x180003ff1  cmp     r9d, ebp
0x180003ff4  jg      short loc_180003FFE
0x180003ff6  lea     eax, [rcx+r9]
0x180003ffa  cmp     ebp, eax
0x180003ffc  jl      short loc_180004018
0x180003ffe  or      eax, 0FFFFFFFFh
0x180004001  cmp     ebp, r9d
0x180004004  cmovge  eax, r11d
0x180004008  add     r10d, r11d
0x18000400b  add     edx, eax
0x18000400d  jns     short loc_180003FD4
0x18000400f  cmp     edx, [r8]
0x180004012  jz      loc_1800040AA
0x180004018  test    edx, edx
0x18000401a  js      loc_1800040AA
0x180004020  cmp     ecx, [rsi+4]
0x180004023  jg      loc_1800040AA
0x180004029  mov     rax, rbx
0x18000402c  lea     r11, [rsi+38h]
0x180004030  shl     rax, 4
0x180004034  lea     rdi, [rsi+3Ch]
0x180004038  add     r11, rax
0x18000403b  add     rdi, rax
0x18000403e  inc     edx
0x180004040  mov     r13, rbx
0x180004043  mov     [r11], r9d
0x180004046  mov     [rdi], ecx
0x180004048  mov     r8, [rsi+20h]
0x18000404c  cmp     edx, [r8]
0x18000404f  jge     short loc_1800040A5
0x180004051  mov     r15d, [rax+rsi+38h]
0x180004056  movsxd  rax, edx
0x180004059  lea     r10, [rax+rax*2]
0x18000405d  lea     eax, [rcx+r15]
0x180004061  cmp     [r8+r10*4+0Ch], eax
0x180004066  jl      short loc_180004085
0x180004068  mov     r9, r8
0x18000406b  jnz     short loc_180004093
0x18000406d  mov     r10d, [r8+r10*4+10h]
0x180004072  mov     eax, [rsi+4]
0x180004075  add     r10d, 8
0x180004079  sub     eax, ecx
0x18000407b  cmp     r10d, eax
0x18000407e  jg      short loc_180004093
0x180004080  add     ecx, r10d
0x180004083  mov     [rdi], ecx
0x180004085  mov     r8, [rsi+20h]
0x180004089  inc     edx
0x18000408b  mov     r9, r8
0x18000408e  cmp     edx, [r8]
0x180004091  jl      short loc_180004056
0x180004093  mov     r15, [rsp+68h+arg_18]
0x18000409b  cmp     edx, [r9]
0x18000409e  jge     short loc_1800040E0
0x1800040a0  mov     [rsi+28h], edx
0x1800040a3  jmp     short loc_1800040E0
0x1800040a5  mov     r9, r8
0x1800040a8  jmp     short loc_18000409B
0x1800040aa  mov     eax, ebp
0x1800040ac  lea     r11, [rsi+38h]
0x1800040b0  cdq
0x1800040b1  lea     rdi, [rsi+3Ch]
0x1800040b5  idiv    dword ptr [rsi+4]
0x1800040b8  mov     rcx, rbx
0x1800040bb  mov     r8d, ebp
0x1800040be  shl     rcx, 4
0x1800040c2  sub     r8d, edx
0x1800040c5  add     r11, rcx
0x1800040c8  add     rdi, rcx
0x1800040cb  mov     r13, rbx
0x1800040ce  mov     [r11], r8d
0x1800040d1  mov     eax, [rsi+2Ch]
0x1800040d4  sub     eax, r8d
0x1800040d7  cmp     eax, [rsi+4]
0x1800040da  cmovge  eax, [rsi+4]
0x1800040de  mov     [rdi], eax
0x1800040e0  mov     rcx, [rsi+10h]
0x1800040e4  mov     edx, [r11]; lOffset
0x1800040e7  mov     rax, [rcx+10h]
0x1800040eb  test    rax, rax
0x1800040ee  jz      short loc_1800040F8
0x1800040f0  mov     [rax+174h], edx
0x1800040f6  jmp     short loc_180004105
0x1800040f8  mov     rcx, [rcx+8]; hmmio
0x1800040fc  xor     r8d, r8d; iOrigin
0x1800040ff  call    cs:__imp_mmioSeek
0x180004105  mov     r8d, [rdi]
0x180004108  lea     rdx, [r13+4]
0x18000410c  mov     rcx, [rsi+10h]
0x180004110  add     rdx, rdx
0x180004113  mov     rdx, [rsi+rdx*8]
0x180004117  call    shfileRead
0x18000411c  cmp     eax, [rdi]
0x18000411e  jnz     loc_1800041B5
0x180004124  lea     eax, [rbx+1]
0x180004127  cdq
0x180004128  idiv    dword ptr [rsi]
0x18000412a  mov     [rsi+30h], edx
0x18000412d  movsxd  r8, ebx
0x180004130  mov     rax, r8
0x180004133  add     rax, rax
0x180004136  movsxd  rdx, dword ptr [rsi+rax*8+38h]
0x18000413b  test    edx, edx
0x18000413d  js      short loc_1800041B5
0x18000413f  cmp     ebp, edx
0x180004141  jl      short loc_1800041B5
0x180004143  mov     ecx, [rsi+rax*8+3Ch]
0x180004147  mov     eax, ebp
0x180004149  sub     eax, edx
0x18000414b  cmp     eax, ecx
0x18000414d  jg      short loc_1800041B5
0x18000414f  sub     ecx, ebp
0x180004151  mov     edi, r14d
0x180004154  lea     eax, [rcx+rdx]
0x180004157  cmp     r14d, eax
0x18000415a  lea     rcx, [r8+4]
0x18000415e  cmovge  edi, eax
0x180004161  mov     rax, rdx
0x180004164  add     rcx, rcx
0x180004167  movsxd  rbx, edi
0x18000416a  mov     r8, rbx; Size
0x18000416d  mov     rdx, [rsi+rcx*8]
0x180004171  mov     rcx, r15; void *
0x180004174  sub     rdx, rax
0x180004177  movsxd  rax, ebp
0x18000417a  add     rdx, rax; Src
0x18000417d  call    memmove_0
0x180004182  add     r15, rbx
0x180004185  sub     r14d, edi
0x180004188  add     ebp, edi
0x18000418a  mov     [rsp+68h+arg_18], r15
0x180004192  mov     r11d, 1
0x180004198  test    r14d, r14d
0x18000419b  jg      loc_180003F82
0x1800041a1  mov     eax, r12d
0x1800041a4  add     rsp, 28h
0x1800041a8  pop     r15
0x1800041aa  pop     r14
0x1800041ac  pop     r13
0x1800041ae  pop     r12
0x1800041b0  pop     rdi
0x1800041b1  pop     rsi
0x1800041b2  pop     rbp
0x1800041b3  pop     rbx
0x1800041b4  retn
0x1800041b5  xor     eax, eax
0x1800041b7  jmp     short loc_1800041A4
```
