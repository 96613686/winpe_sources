# sub_14007EFAC

- ea: `0x14007efac`
- end: `0x14007f42e`
- name: `sub_14007EFAC`
- size: `1154`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `19`
- callee_count: `6`
- tags: ``

## callers

- `0x1400321a0`
- `0x140032af4`
- `0x140036e80`
- `0x1400381d8`
- `0x140038310`
- `0x140038448`
- `0x14003d560`
- `0x14003dcb8`
- `0x140089cf0`
- `0x140098d00`
- `0x140099060`
- `0x14009a500`
- `0x14009c040`
- `0x14009c740`
- `0x14009c7b0`
- `0x14009c890`
- `0x14009d000`
- `0x1400c76b0`
- `0x1400c7db0`

## callees

- `0x14007c340`
- `0x14007efac`
- `0x140082660`
- `0x140082930`
- `0x1400c7ae0`
- `0x1400c7b70`

## pseudocode

```c
__int64 __fastcall sub_14007EFAC(__int64 a1)
{
  __int64 v1; // rdi
  unsigned __int64 v2; // r13
  __int64 v3; // rsi
  char v4; // al
  __int64 v5; // rdx
  int v6; // ebx
  struct HINSTANCE__ **v7; // rdx
  __int64 v8; // r14
  char v9; // al
  unsigned __int64 v10; // rcx
  __int64 v11; // r12
  __int64 v12; // rbx
  unsigned __int16 v13; // r8
  unsigned __int64 v14; // r15
  int v15; // edi
  unsigned int v16; // r9d
  char *v17; // rbx
  unsigned int v18; // r8d
  int v19; // edx
  int v20; // ecx
  unsigned int v21; // r9d
  int v22; // r8d
  int v23; // edx
  int v24; // ecx
  unsigned int v25; // r8d
  int v26; // r9d
  unsigned __int64 v27; // rcx
  int v28; // edx
  char *v29; // r8
  unsigned __int64 *v30; // r10
  char v31; // al
  char *v32; // r8
  unsigned __int64 v33; // rax
  unsigned __int64 v34; // r8
  unsigned __int64 *v35; // r10
  _BYTE *v36; // r11
  char v37; // al
  unsigned __int64 *v38; // r10
  unsigned __int64 v39; // r15
  int v40; // r11d
  unsigned __int64 *v41; // r14
  char *v42; // rsi
  unsigned __int64 v43; // r13
  __int64 v44; // rax
  int v45; // r10d
  unsigned int v46; // r9d
  int v47; // r8d
  unsigned int v48; // r11d
  int v49; // r10d
  int v50; // r8d
  int v51; // r9d
  unsigned int v52; // r10d
  int v53; // r8d
  int v54; // ecx
  _BYTE *v55; // rcx
  char v56; // al
  __int64 v57; // rcx
  void *v58; // rsp
  char v60; // [rsp+20h] [rbp+0h]
  __int64 v61; // [rsp+28h] [rbp+8h]
  unsigned __int64 v62; // [rsp+30h] [rbp+10h] BYREF
  unsigned __int64 v63; // [rsp+38h] [rbp+18h] BYREF
  __int64 v64; // [rsp+40h] [rbp+20h]
  struct HINSTANCE__ *v65; // [rsp+48h] [rbp+28h] BYREF
  __int64 v66; // [rsp+50h] [rbp+30h]
  char *v67; // [rsp+58h] [rbp+38h]
  __int64 v68; // [rsp+60h] [rbp+40h] BYREF
  unsigned __int64 v69; // [rsp+70h] [rbp+50h]
  __int64 v70; // [rsp+78h] [rbp+58h]

  v1 = *(_QWORD *)(a1 + 16);
  v2 = *(_DWORD *)(a1 + 24) & 0xFFFFFFF;
  v3 = a1;
  v4 = *(_BYTE *)(a1 + 4);
  v5 = *(_DWORD *)(a1 + 28) & 0xFFFFFFF;
  v6 = *(_DWORD *)a1;
  v65 = (struct HINSTANCE__ *)v2;
  v70 = a1;
  v60 = v4;
  v66 = v1;
  v64 = v1;
  v8 = sub_14007C340(a1, v5);
  v68 = v8;
  v9 = 0;
  v10 = (unsigned __int64)&_ImageBase;
  v11 = 8;
  if ( v2 )
  {
    v12 = v6 & 0xFFFFFFF;
    v13 = HIWORD(v64);
    LOWORD(v61) = v1;
    *(_DWORD *)((char *)&v61 + 2) = *(_DWORD *)((char *)&v64 + 2);
    v10 = (unsigned int)~(_DWORD)v12;
    HIWORD(v61) = HIWORD(v64);
    v63 = (unsigned int)v12;
    v67 = (char *)&_ImageBase + v12;
    v62 = 0;
    v14 = v2 & 7;
    if ( (v2 & 7) != 0 )
    {
      v63 = 0;
      v18 = v10 ^ ((unsigned int)v12 >> 8) ^ (WORD1(v64) * __ROL4__(v12 - HIWORD(v64), 6));
      v19 = v12 ^ ((unsigned __int16)v66 * __ROR4__(HIDWORD(v61) - v18, 23) - __ROR4__(v18, 22));
      v20 = v18 ^ (WORD2(v64) * (HIWORD(v64) + __ROR4__(~v19, 4)));
      v21 = v19 ^ (WORD2(v64) * __ROR4__(v20 - v61, 3) - __ROR4__(v20, 11));
      v22 = v20 ^ ((v21 >> 9) + WORD1(v64) * __ROL4__((unsigned __int16)v66 ^ v21, 3));
      v23 = v21 ^ (__ROR4__(v22, 3) + (unsigned __int16)v66 * __ROR4__(HIDWORD(v61) - v22, 3));
      v24 = v22 ^ (HIWORD(v64) * (WORD1(v64) ^ v23)) ^ __ROR4__(v23, 5);
      v25 = v23 ^ ((unsigned __int16)v66 * (__ROR4__(v24, 9) - WORD2(v64)));
      v26 = v24 ^ ((v25 >> 6) + WORD1(v64) * ((unsigned __int16)v66 ^ v25));
      v27 = v2 & 7;
      v17 = v67;
      v28 = v25 ^ (__ROR4__(v26, 31) + (unsigned __int16)v66 * __ROR4__(HIDWORD(v61) ^ v26, 4));
      v29 = v67;
      v30 = &v63;
      do
      {
        v31 = *v29++;
        *(_BYTE *)v30 = v31;
        v30 = (unsigned __int64 *)((char *)v30 + 1);
        --v27;
      }
      while ( v27 );
      v7 = (struct HINSTANCE__ **)(HIDWORD(v63) ^ (unsigned int)v28);
      v10 = v63;
      v32 = (char *)&v62 + v14;
      v15 = HIDWORD(v63);
      v16 = v63 ^ v26;
      v62 = __PAIR64__((unsigned int)v7, v16);
      v33 = 8 - v14;
      if ( v14 != 8 )
      {
        do
        {
          *v32++ = 0;
          --v33;
        }
        while ( v33 );
        v7 = (struct HINSTANCE__ **)HIDWORD(v62);
        v16 = v62;
      }
      v34 = v2 & 7;
      v35 = &v62;
      v36 = (_BYTE *)v8;
      do
      {
        v37 = *(_BYTE *)v35;
        v35 = (unsigned __int64 *)((char *)v35 + 1);
        *v36++ = v37;
        --v34;
      }
      while ( v34 );
      v13 = HIWORD(v64);
    }
    else
    {
      v7 = (struct HINSTANCE__ **)HIDWORD(v62);
      v15 = v12;
      v16 = v62;
      v17 = (char *)&_ImageBase + v12;
    }
    v69 = 0;
    v38 = (unsigned __int64 *)(v14 + v8);
    v67 = &v17[v14];
    v39 = v2 >> 3;
    if ( v2 >> 3 )
    {
      v40 = (unsigned __int16)v66;
      v41 = v38;
      v42 = v67;
      v43 = v69;
      LODWORD(v63) = v13;
      do
      {
        v44 = *(_QWORD *)v42;
        v42 += 8;
        v45 = v16
            ^ v44
            ^ (((unsigned int)v7 ^ HIDWORD(v44)) >> 8)
            ^ (WORD1(v64) * __ROL4__(((unsigned int)v7 ^ HIDWORD(v44)) - v63, 6));
        v46 = (unsigned int)v7 ^ HIDWORD(v44) ^ (v40 * __ROR4__(HIDWORD(v61) - v45, 23) - __ROR4__(v45, 22));
        v47 = v45 ^ (WORD2(v64) * (v63 + __ROR4__(~v46, 4)));
        v48 = v46 ^ (WORD2(v64) * __ROR4__(v47 - v61, 3) - __ROR4__(v47, 11));
        v49 = v47 ^ ((v48 >> 9) + WORD1(v64) * __ROL4__((unsigned __int16)v66 ^ v48, 3));
        v50 = v48 ^ (__ROR4__(v49, 3) + (unsigned __int16)v66 * __ROR4__(HIDWORD(v61) - v49, 3));
        v40 = (unsigned __int16)v66;
        v51 = v49 ^ (v63 * (v50 ^ WORD1(v64))) ^ __ROR4__(v50, 5);
        v52 = v50 ^ ((unsigned __int16)v66 * (__ROR4__(v51, 9) - WORD2(v64)));
        v53 = v51 ^ ((v52 >> 6) + WORD1(v64) * (v52 ^ (unsigned __int16)v66));
        v16 = v10 ^ v53;
        LODWORD(v62) = v10 ^ v53;
        v10 = (unsigned int)v44;
        ++v43;
        v7 = (struct HINSTANCE__ **)(v15
                                   ^ v52
                                   ^ (__ROR4__(v53, 31) + (unsigned __int16)v66 * __ROR4__(HIDWORD(v61) ^ v53, 4)));
        v15 = HIDWORD(v44);
        HIDWORD(v62) = (_DWORD)v7;
        *v41++ = v62;
      }
      while ( v43 < v39 );
      v3 = v70;
      v8 = v68;
      v2 = (unsigned __int64)v65;
    }
    v9 = *(_BYTE *)(v8 + v2 - 1);
  }
  if ( v9 != v60 )
    sub_140082930(v10);
  v54 = *(_DWORD *)(v3 + 8);
  if ( (v54 & 0xFFFFFFF) != 0 )
  {
    v65 = &_ImageBase;
    v7 = &v65;
    v55 = (_BYTE *)(v8 + (v54 & 0xFFFFFFF));
    do
    {
      v56 = *(_BYTE *)v7;
      v7 = (struct HINSTANCE__ **)((char *)v7 + 1);
      *v55++ = v56;
      --v11;
    }
    while ( v11 );
  }
  v57 = *(unsigned int *)(v3 + 12);
  if ( (v57 & 0xFFFFFFF) != 0 )
    v58 = alloca(sub_1400C7B70(v57 & 0xFFFFFFF, v7));
  v68 = 0;
  v65 = 0;
  sub_140082660(v57, v8, &v68, &v65);
  return v8;
}

```

## disassembly

```asm
0x14007efac  push    rbp
0x14007efae  push    rbx
0x14007efaf  push    rsi
0x14007efb0  push    rdi
0x14007efb1  push    r12
0x14007efb3  push    r13
0x14007efb5  push    r14
0x14007efb7  push    r15
0x14007efb9  sub     rsp, 98h
0x14007efc0  lea     rbp, [rsp+20h]
0x14007efc5  mov     rax, cs:__security_cookie
0x14007efcc  xor     rax, rbp
0x14007efcf  mov     [rbp+0B0h+var_50], rax
0x14007efd3  mov     r13d, [rcx+18h]
0x14007efd7  mov     r15d, 0FFFFFFFh
0x14007efdd  mov     rdi, [rcx+10h]
0x14007efe1  and     r13d, r15d
0x14007efe4  mov     edx, [rcx+1Ch]
0x14007efe7  mov     rsi, rcx
0x14007efea  mov     al, [rcx+4]
0x14007efed  and     rdx, r15
0x14007eff0  mov     ebx, [rcx]
0x14007eff2  mov     [rbp+0B0h+var_88], r13
0x14007eff6  mov     [rbp+0B0h+var_58], rcx
0x14007effa  mov     [rbp+0B0h+var_B0], al
0x14007effd  mov     [rbp+0B0h+var_80], rdi
0x14007f001  mov     [rbp+0B0h+var_90], rdi
0x14007f005  call    sub_14007C340
0x14007f00a  mov     r14, rax
0x14007f00d  mov     [rbp+0B0h+var_70], rax
0x14007f011  xor     al, al
0x14007f013  lea     rcx, __ImageBase
0x14007f01a  mov     r12d, 8
0x14007f020  test    r13, r13
0x14007f023  jz      loc_14007F38C
0x14007f029  movzx   edx, word ptr [rbp+0B0h+var_90+2]
0x14007f02d  and     ebx, r15d
0x14007f030  movzx   r9d, word ptr [rbp+0B0h+var_90+4]
0x14007f035  mov     r15d, r13d
0x14007f038  movzx   r8d, word ptr [rbp+0B0h+var_90+6]
0x14007f03d  mov     r10d, ebx
0x14007f040  mov     word ptr [rbp+0B0h+var_A8], di
0x14007f044  lea     rax, [rbx+rcx]
0x14007f048  mov     word ptr [rbp+0B0h+var_A8+2], dx
0x14007f04c  mov     ecx, ebx
0x14007f04e  mov     word ptr [rbp+0B0h+var_A4], r9w
0x14007f053  not     ecx
0x14007f055  mov     word ptr [rbp+0B0h+var_A4+2], r8w
0x14007f05a  mov     [rbp+0B0h+var_98], r10
0x14007f05e  mov     [rbp+0B0h+var_78], rax
0x14007f062  mov     [rbp+0B0h+var_A0], 0
0x14007f06a  and     r15d, 7
0x14007f06e  jnz     short loc_14007F082
0x14007f070  mov     edx, dword ptr [rbp+0B0h+var_A0+4]
0x14007f073  mov     edi, r10d
0x14007f076  mov     r9d, dword ptr [rbp+0B0h+var_A0]
0x14007f07a  mov     rbx, rax
0x14007f07d  jmp     loc_14007F1EC
0x14007f082  movzx   ebx, word ptr [rbp+0B0h+var_80]
0x14007f086  mov     edi, edx
0x14007f088  mov     r11d, r8d
0x14007f08b  mov     [rbp+0B0h+var_98], 0
0x14007f093  mov     r8d, r10d
0x14007f096  mov     eax, r10d
0x14007f099  sub     r8d, r11d
0x14007f09c  shr     eax, 8
0x14007f09f  rol     r8d, 6
0x14007f0a3  imul    r8d, edx
0x14007f0a7  mov     edx, [rbp+0B0h+var_A4]
0x14007f0aa  xor     r8d, eax
0x14007f0ad  xor     r8d, ecx
0x14007f0b0  sub     edx, r8d
0x14007f0b3  mov     eax, r8d
0x14007f0b6  ror     edx, 17h
0x14007f0b9  imul    edx, ebx
0x14007f0bc  ror     eax, 16h
0x14007f0bf  sub     edx, eax
0x14007f0c1  xor     edx, r10d
0x14007f0c4  mov     r10d, r9d
0x14007f0c7  mov     ecx, edx
0x14007f0c9  not     ecx
0x14007f0cb  ror     ecx, 4
0x14007f0ce  add     ecx, r11d
0x14007f0d1  imul    ecx, r9d
0x14007f0d5  xor     ecx, r8d
0x14007f0d8  mov     r9d, ecx
0x14007f0db  mov     eax, ecx
0x14007f0dd  sub     r9d, [rbp+0B0h+var_A8]
0x14007f0e1  ror     eax, 0Bh
0x14007f0e4  ror     r9d, 3
0x14007f0e8  imul    r9d, r10d
0x14007f0ec  sub     r9d, eax
0x14007f0ef  xor     r9d, edx
0x14007f0f2  mov     edx, [rbp+0B0h+var_A4]
0x14007f0f5  mov     r8d, r9d
0x14007f0f8  mov     eax, r9d
0x14007f0fb  xor     r8d, ebx
0x14007f0fe  shr     eax, 9
0x14007f101  rol     r8d, 3
0x14007f105  imul    r8d, edi
0x14007f109  add     r8d, eax
0x14007f10c  xor     r8d, ecx
0x14007f10f  sub     edx, r8d
0x14007f112  mov     eax, r8d
0x14007f115  ror     edx, 3
0x14007f118  imul    edx, ebx
0x14007f11b  ror     eax, 3
0x14007f11e  add     edx, eax
0x14007f120  xor     edx, r9d
0x14007f123  mov     ecx, edx
0x14007f125  mov     eax, edx
0x14007f127  xor     eax, edi
0x14007f129  ror     ecx, 5
0x14007f12c  imul    eax, r11d
0x14007f130  xor     ecx, eax
0x14007f132  xor     ecx, r8d
0x14007f135  mov     r8d, ecx
0x14007f138  ror     r8d, 9
0x14007f13c  sub     r8d, r10d
0x14007f13f  imul    r8d, ebx
0x14007f143  xor     r8d, edx
0x14007f146  mov     r9d, r8d
0x14007f149  mov     eax, r8d
0x14007f14c  xor     r9d, ebx
0x14007f14f  shr     eax, 6
0x14007f152  imul    r9d, edi
0x14007f156  add     r9d, eax
0x14007f159  xor     r9d, ecx
0x14007f15c  mov     rcx, r15
0x14007f15f  mov     edx, r9d
0x14007f162  mov     eax, r9d
0x14007f165  xor     edx, [rbp+0B0h+var_A4]
0x14007f168  ror     edx, 4
0x14007f16b  imul    edx, ebx
0x14007f16e  mov     rbx, [rbp+0B0h+var_78]
0x14007f172  ror     eax, 1Fh
0x14007f175  add     edx, eax
0x14007f177  xor     edx, r8d
0x14007f17a  mov     r8, rbx
0x14007f17d  lea     r10, [rbp+0B0h+var_98]
0x14007f181  mov     al, [r8]
0x14007f184  inc     r8
0x14007f187  mov     [r10], al
0x14007f18a  inc     r10
0x14007f18d  sub     rcx, 1
0x14007f191  jnz     short loc_14007F181
0x14007f193  xor     edx, dword ptr [rbp+0B0h+var_98+4]
0x14007f196  lea     r8, [rbp+0B0h+var_A0]
0x14007f19a  mov     rcx, [rbp+0B0h+var_98]
0x14007f19e  lea     r8, [r8+r15]
0x14007f1a2  mov     edi, dword ptr [rbp+0B0h+var_98+4]
0x14007f1a5  xor     r9d, ecx
0x14007f1a8  mov     rax, r12
0x14007f1ab  mov     dword ptr [rbp+0B0h+var_A0], r9d
0x14007f1af  mov     dword ptr [rbp+0B0h+var_A0+4], edx
0x14007f1b2  sub     rax, r15
0x14007f1b5  jz      short loc_14007F1CB
0x14007f1b7  mov     byte ptr [r8], 0
0x14007f1bb  inc     r8
0x14007f1be  sub     rax, 1
0x14007f1c2  jnz     short loc_14007F1B7
0x14007f1c4  mov     edx, dword ptr [rbp+0B0h+var_A0+4]
0x14007f1c7  mov     r9d, dword ptr [rbp+0B0h+var_A0]
0x14007f1cb  mov     r8, r15
0x14007f1ce  lea     r10, [rbp+0B0h+var_A0]
0x14007f1d2  mov     r11, r14
0x14007f1d5  mov     al, [r10]
0x14007f1d8  inc     r10
0x14007f1db  mov     [r11], al
0x14007f1de  inc     r11
0x14007f1e1  sub     r8, 1
0x14007f1e5  jnz     short loc_14007F1D5
0x14007f1e7  movzx   r8d, word ptr [rbp+0B0h+var_90+6]
0x14007f1ec  lea     rax, [r15+rbx]
0x14007f1f0  mov     [rbp+0B0h+var_60], 0
0x14007f1f8  lea     r10, [r15+r14]
0x14007f1fc  mov     [rbp+0B0h+var_78], rax
0x14007f200  mov     r15, r13
0x14007f203  shr     r15, 3
0x14007f207  test    r15, r15
0x14007f20a  jz      loc_14007F381
0x14007f210  movzx   r11d, word ptr [rbp+0B0h+var_80]
0x14007f215  mov     r14, r10
0x14007f218  mov     rsi, [rbp+0B0h+var_78]
0x14007f21c  mov     r13, [rbp+0B0h+var_60]
0x14007f220  movzx   eax, r8w
0x14007f224  mov     dword ptr [rbp+0B0h+var_98], eax
0x14007f227  mov     rax, [rsi]
0x14007f22a  add     rsi, r12
0x14007f22d  mov     rbx, rax
0x14007f230  shr     rbx, 20h
0x14007f234  mov     r8d, ebx
0x14007f237  xor     r8d, edx
0x14007f23a  movzx   edx, word ptr [rbp+0B0h+var_90+2]
0x14007f23e  mov     r10d, r8d
0x14007f241  sub     r10d, dword ptr [rbp+0B0h+var_98]
0x14007f245  rol     r10d, 6
0x14007f249  imul    r10d, edx
0x14007f24d  mov     edx, r8d
0x14007f250  shr     edx, 8
0x14007f253  xor     r10d, edx
0x14007f256  xor     r10d, eax
0x14007f259  xor     r10d, r9d
0x14007f25c  mov     r9d, [rbp+0B0h+var_A4]
0x14007f260  sub     r9d, r10d
0x14007f263  mov     edx, r10d
0x14007f266  ror     edx, 16h
0x14007f269  ror     r9d, 17h
0x14007f26d  imul    r9d, r11d
0x14007f271  sub     r9d, edx
0x14007f274  movzx   edx, word ptr [rbp+0B0h+var_90+4]
0x14007f278  xor     r9d, r8d
0x14007f27b  mov     r8d, r9d
0x14007f27e  not     r8d
0x14007f281  ror     r8d, 4
0x14007f285  add     r8d, dword ptr [rbp+0B0h+var_98]
0x14007f289  imul    r8d, edx
0x14007f28d  xor     r8d, r10d
0x14007f290  mov     r11d, r8d
0x14007f293  sub     r11d, [rbp+0B0h+var_A8]
0x14007f297  ror     r11d, 3
0x14007f29b  imul    r11d, edx
0x14007f29f  mov     edx, r8d
0x14007f2a2  ror     edx, 0Bh
0x14007f2a5  sub     r11d, edx
0x14007f2a8  movzx   edx, word ptr [rbp+0B0h+var_90+2]
0x14007f2ac  xor     r11d, r9d
0x14007f2af  movzx   r9d, word ptr [rbp+0B0h+var_80]
0x14007f2b4  mov     r10d, r11d
0x14007f2b7  xor     r10d, r9d
0x14007f2ba  rol     r10d, 3
0x14007f2be  imul    r10d, edx
0x14007f2c2  mov     edx, r11d
0x14007f2c5  shr     edx, 9
0x14007f2c8  add     r10d, edx
0x14007f2cb  xor     r10d, r8d
0x14007f2ce  mov     r8d, [rbp+0B0h+var_A4]
0x14007f2d2  sub     r8d, r10d
0x14007f2d5  mov     edx, r10d
0x14007f2d8  ror     r8d, 3
0x14007f2dc  imul    r8d, r9d
0x14007f2e0  ror     edx, 3
0x14007f2e3  add     r8d, edx
0x14007f2e6  movzx   edx, word ptr [rbp+0B0h+var_90+2]
0x14007f2ea  xor     r8d, r11d
0x14007f2ed  movzx   r11d, word ptr [rbp+0B0h+var_80]
0x14007f2f2  xor     edx, r8d
0x14007f2f5  mov     r9d, r8d
0x14007f2f8  imul    edx, dword ptr [rbp+0B0h+var_98]
0x14007f2fc  ror     r9d, 5
0x14007f300  xor     r9d, edx
0x14007f303  movzx   edx, word ptr [rbp+0B0h+var_90+4]
0x14007f307  xor     r9d, r10d
0x14007f30a  mov     r10d, r9d
0x14007f30d  ror     r10d, 9
0x14007f311  sub     r10d, edx
0x14007f314  movzx   edx, word ptr [rbp+0B0h+var_90+2]
0x14007f318  imul    r10d, r11d
0x14007f31c  xor     r10d, r8d
0x14007f31f  mov     r8d, r11d
0x14007f322  xor     r8d, r10d
0x14007f325  imul    r8d, edx
0x14007f329  mov     edx, r10d
0x14007f32c  shr     edx, 6
0x14007f32f  add     r8d, edx
0x14007f332  xor     r8d, r9d
0x14007f335  mov     r9d, r8d
0x14007f338  xor     r9d, ecx
0x14007f33b  mov     edx, r8d
0x14007f33e  mov     dword ptr [rbp+0B0h+var_A0], r9d
0x14007f342  xor     edx, [rbp+0B0h+var_A4]
0x14007f345  mov     ecx, eax
0x14007f347  ror     edx, 4
0x14007f34a  inc     r13
0x14007f34d  imul    edx, r11d
0x14007f351  ror     r8d, 1Fh
0x14007f355  add     edx, r8d
0x14007f358  xor     edx, r10d
0x14007f35b  xor     edx, edi
0x14007f35d  mov     edi, ebx
0x14007f35f  mov     dword ptr [rbp+0B0h+var_A0+4], edx
0x14007f362  mov     rax, [rbp+0B0h+var_A0]
0x14007f366  mov     [r14], rax
0x14007f369  add     r14, r12
0x14007f36c  cmp     r13, r15
0x14007f36f  jb      loc_14007F227
0x14007f375  mov     rsi, [rbp+0B0h+var_58]
0x14007f379  mov     r14, [rbp+0B0h+var_70]
0x14007f37d  mov     r13, [rbp+0B0h+var_88]
0x14007f381  mov     al, [r14+r13-1]
0x14007f386  mov     r15d, 0FFFFFFFh
0x14007f38c  cmp     al, [rbp+0B0h+var_B0]
0x14007f38f  jz      short loc_14007F396
0x14007f391  call    sub_140082930
0x14007f396  mov     ecx, [rsi+8]
0x14007f399  test    r15d, ecx
0x14007f39c  jz      short loc_14007F3C3
0x14007f39e  lea     rax, __ImageBase
0x14007f3a5  and     rcx, r15
0x14007f3a8  mov     [rbp+0B0h+var_88], rax
  ... truncated ...
```
