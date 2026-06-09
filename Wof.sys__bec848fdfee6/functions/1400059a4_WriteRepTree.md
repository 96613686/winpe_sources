# WriteRepTree

- ea: `0x1400059a4`
- end: `0x140005d8e`
- name: `WriteRepTree`
- size: `1002`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000bed4`

## callees

- `0x1400059a4`
- `0x140005d94`
- `0x140007228`
- `0x140011560`
- `0x1400116c0`
- `0x1400119c0`

## pseudocode

```c
void *__fastcall WriteRepTree(__int64 a1, _BYTE *a2, unsigned __int8 *a3, int a4)
{
  size_t v5; // r13
  __int64 v7; // r14
  size_t v8; // rdi
  int v9; // r8d
  int v10; // ecx
  int v11; // edx
  __int64 v12; // r9
  __int64 v13; // rax
  unsigned __int16 v14; // dx
  __int64 v15; // rcx
  __int16 v16; // cx
  __int64 v17; // rax
  __int64 v18; // r10
  __int64 v19; // r10
  __int64 v20; // r11
  int v21; // ebx
  int v22; // r11d
  int v23; // ecx
  __int64 v24; // rdx
  unsigned __int8 *v25; // rdi
  char v26; // r10
  char v27; // r10
  int v28; // r11d
  int v30; // r8d
  char v31; // dl
  int v32; // r11d
  __int64 v33; // rax
  int i; // ecx
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 j; // rdx
  __int64 v38; // rcx
  __int16 v39; // ax
  unsigned __int64 v40; // r10
  char v41; // [rsp+20h] [rbp-E0h]
  _BYTE v43[24]; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v44[10]; // [rsp+50h] [rbp-B0h]
  _OWORD v45[3]; // [rsp+78h] [rbp-88h] BYREF
  _WORD v46[48]; // [rsp+B0h] [rbp-50h] BYREF

  v5 = a4;
  v7 = a1;
  memset(v45, 0, sizeof(v45));
  memset(v46, 0, sizeof(v46));
  v41 = a2[v5];
  v8 = v5;
  a2[v5] = 123;
  v9 = 0;
  if ( (int)v5 <= 0 )
    goto LABEL_13;
  do
  {
    v10 = v9 + 1;
    v11 = 0;
    v12 = (unsigned __int8)a2[v9];
    if ( a2[v9 + 1] == (_BYTE)v12 )
    {
      do
      {
        ++v10;
        ++v11;
      }
      while ( a2[v10] == (_BYTE)v12 );
      if ( v11 >= 4 )
      {
        if ( (_BYTE)v12 )
        {
          if ( v11 > 5 )
            v11 = 5;
          v33 = *((unsigned __int8 *)&qword_140013210[2] + a3[v9] - v12 + 1);
          ++v46[v33];
          ++v46[19];
          goto LABEL_9;
        }
        if ( v11 > 51 )
        {
          v11 = 51;
        }
        else if ( v11 <= 19 )
        {
          ++v46[17];
          goto LABEL_9;
        }
        ++v46[18];
LABEL_9:
        v9 = v11 + v9 - 1;
        goto LABEL_11;
      }
    }
    v13 = *((unsigned __int8 *)&qword_140013210[2] + a3[v9] - v12 + 1);
    ++v46[v13];
LABEL_11:
    ++v9;
  }
  while ( v9 < (int)v5 );
  v7 = a1;
  v8 = v5;
LABEL_13:
  while ( 1 )
  {
    *(_DWORD *)(v7 + 9580) = 20;
    *(_QWORD *)(v7 + 2520) = v46;
    v14 = 0;
    *(_BYTE *)(v7 + 9586) = 0;
    *(_QWORD *)(v7 + 2536) = v43;
    *(_WORD *)(v7 + 9584) = 0;
    *(_WORD *)(v7 + 2546) = 0;
    do
    {
      *(_BYTE *)(v14 + *(_QWORD *)(v7 + 2536)) = 0;
      if ( v46[v14] )
      {
        v15 = *(__int16 *)(v7 + 9584);
        *(_WORD *)(v7 + 9584) = v15 + 1;
        *(_WORD *)(v7 + 2 * v15 + 2546) = v14;
      }
      ++v14;
    }
    while ( (__int16)v14 < 20 );
    v16 = *(_WORD *)(v7 + 9584);
    if ( v16 >= 2 )
      break;
    v17 = *(__int16 *)(v7 + 2546);
    if ( !v16 )
    {
      *((_WORD *)v45 + v17) = 0;
      goto LABEL_20;
    }
    if ( (_WORD)v17 )
      v46[0] = 1;
    else
      v46[1] = 1;
  }
  make_tree2(v7, 20, v46, v45);
  for ( i = 0; i < 20; ++i )
  {
    if ( v43[i] >= 0x12u )
      goto LABEL_20;
  }
  v44[0] = 0;
  v35 = 1;
  do
  {
    v36 = v35 + 1;
    *((_WORD *)v44 + v36) = 2 * (*((_WORD *)v44 + v35) + *(_WORD *)(v7 + 2 * v35 + 9544));
    ++v35;
  }
  while ( v36 != 17 );
  for ( j = 0; j != 20; ++j )
  {
    v38 = (char)v43[j];
    v39 = *((_WORD *)v44 + v38);
    *((_WORD *)v45 + j) = v39;
    *((_WORD *)v44 + v38) = v39 + 1;
  }
LABEL_20:
  v18 = 0;
  do
  {
    output_bits(v7, 4, (char)v43[v18]);
    v18 = v19 + 1;
  }
  while ( v18 != v20 );
  v21 = 0;
  if ( (int)v5 > 0 )
  {
    while ( 2 )
    {
      v22 = 0;
      v23 = v21 + 1;
      v24 = (unsigned __int8)a2[v21];
      if ( a2[v21 + 1] != (_BYTE)v24 )
        goto LABEL_26;
      do
      {
        ++v23;
        ++v22;
      }
      while ( a2[v23] == (_BYTE)v24 );
      if ( v22 >= 4 )
      {
        if ( (_BYTE)v24 )
        {
          v26 = 19;
        }
        else
        {
          if ( v22 > 51 )
            v22 = 51;
          v26 = (v22 > 19) + 17;
        }
        v25 = &a3[v21];
      }
      else
      {
LABEL_26:
        v25 = &a3[v21];
        v26 = *((_BYTE *)&qword_140013210[2] + *v25 - v24 + 1);
      }
      output_bits(v7, v43[v26], *((unsigned __int16 *)v45 + v26));
      switch ( v27 )
      {
        case 17:
          v30 = v28 - 4;
          v31 = 4;
          break;
        case 18:
          v30 = v28 - 20;
          v31 = 5;
          break;
        case 19:
          output_bits(v7, 1, v28 - 4);
          v40 = *v25 - (unsigned __int64)(unsigned __int8)a2[v21];
          v30 = *((unsigned __int16 *)v45 + *((char *)&qword_140013210[2] + v40 + 1));
          v31 = v43[*((char *)&qword_140013210[2] + v40 + 1)];
          break;
        default:
          goto LABEL_30;
      }
      output_bits(v7, v31, v30);
      v21 = v32 + v21 - 1;
LABEL_30:
      if ( ++v21 >= (int)v5 )
      {
        v8 = v5;
        break;
      }
      continue;
    }
  }
  a2[v8] = v41;
  return memmove(a3, a2, v8);
}

```

## disassembly

```asm
0x1400059a4  push    rbp
0x1400059a6  push    rbx
0x1400059a7  push    rsi
0x1400059a8  push    rdi
0x1400059a9  push    r12
0x1400059ab  push    r13
0x1400059ad  push    r14
0x1400059af  push    r15
0x1400059b1  lea     rbp, [rsp-28h]
0x1400059b6  sub     rsp, 128h
0x1400059bd  mov     rax, cs:__security_cookie
0x1400059c4  xor     rax, rsp
0x1400059c7  mov     [rbp+60h+var_50], rax
0x1400059cb  xorps   xmm0, xmm0
0x1400059ce  mov     [rsp+160h+var_138], rcx
0x1400059d3  mov     r15, rdx
0x1400059d6  movsxd  r13, r9d
0x1400059d9  xor     edx, edx; Val
0x1400059db  mov     r12, r8
0x1400059de  mov     r14, rcx
0x1400059e1  lea     rcx, [rbp+60h+var_B0]; void *
0x1400059e5  movups  [rsp+160h+var_E8], xmm0
0x1400059ea  lea     r8d, [rdx+60h]; Size
0x1400059ee  movups  [rbp+60h+var_D8], xmm0
0x1400059f2  movups  [rbp+60h+var_C8], xmm0
0x1400059f6  call    memset
0x1400059fb  mov     al, [r13+r15+0]
0x140005a00  xor     esi, esi
0x140005a02  mov     [rsp+160h+var_140], al
0x140005a06  mov     rdi, r13
0x140005a09  mov     byte ptr [r13+r15+0], 7Bh ; '{'
0x140005a0f  mov     r8d, esi
0x140005a12  lea     ebx, [rsi+1]
0x140005a15  lea     r11d, [rsi+33h]
0x140005a19  test    r13d, r13d
0x140005a1c  jle     short loc_140005A9B
0x140005a1e  lea     edi, [rsi+5]
0x140005a21  lea     r14, qword_140013210
0x140005a28  lea     ecx, [r8+1]
0x140005a2c  movsxd  r10, r8d
0x140005a2f  movsxd  rax, ecx
0x140005a32  mov     edx, esi
0x140005a34  movzx   r9d, byte ptr [r10+r15]
0x140005a39  cmp     [rax+r15], r9b
0x140005a3d  jnz     short loc_140005A78
0x140005a3f  add     ecx, ebx
0x140005a41  add     edx, ebx
0x140005a43  movsxd  rax, ecx
0x140005a46  cmp     [rax+r15], r9b
0x140005a4a  jz      short loc_140005A3F
0x140005a4c  cmp     edx, 4
0x140005a4f  jl      short loc_140005A78
0x140005a51  test    r9b, r9b
0x140005a54  jnz     loc_140005C6D
0x140005a5a  cmp     edx, r11d
0x140005a5d  jg      loc_140005D21
0x140005a63  cmp     edx, 13h
0x140005a66  jle     loc_140005C23
0x140005a6c  add     [rbp+60h+var_8C], bx
0x140005a70  dec     r8d
0x140005a73  add     r8d, edx
0x140005a76  jmp     short loc_140005A8B
0x140005a78  movzx   ecx, byte ptr [r10+r12]
0x140005a7d  sub     rcx, r9
0x140005a80  movzx   eax, byte ptr [rcx+r14+11h]
0x140005a86  add     [rbp+rax*2+60h+var_B0], bx
0x140005a8b  add     r8d, ebx
0x140005a8e  cmp     r8d, r13d
0x140005a91  jl      short loc_140005A28
0x140005a93  mov     r14, [rsp+160h+var_138]
0x140005a98  mov     rdi, r13
0x140005a9b  mov     r11d, 14h
0x140005aa1  lea     rax, [rbp+60h+var_B0]
0x140005aa5  mov     [r14+256Ch], r11d
0x140005aac  mov     [r14+9D8h], rax
0x140005ab3  mov     edx, esi
0x140005ab5  lea     rax, [rsp+160h+var_128]
0x140005aba  mov     [r14+2572h], sil
0x140005ac1  mov     [r14+9E8h], rax
0x140005ac8  mov     [r14+2570h], si
0x140005ad0  mov     [r14+9F2h], si
0x140005ad8  mov     rax, [r14+9E8h]
0x140005adf  movzx   ecx, dx
0x140005ae2  mov     [rcx+rax], sil
0x140005ae6  cmp     [rbp+rcx*2+60h+var_B0], si
0x140005aeb  jz      short loc_140005B09
0x140005aed  movsx   rcx, word ptr [r14+2570h]
0x140005af5  lea     eax, [rbx+rcx]
0x140005af8  mov     [r14+2570h], ax
0x140005b00  mov     [r14+rcx*2+9F2h], dx
0x140005b09  add     dx, bx
0x140005b0c  cmp     dx, r11w
0x140005b10  jl      short loc_140005AD8
0x140005b12  movzx   ecx, word ptr [r14+2570h]
0x140005b1a  cmp     cx, 2
0x140005b1e  jge     loc_140005C99
0x140005b24  movsx   rax, word ptr [r14+9F2h]
0x140005b2c  test    cx, cx
0x140005b2f  jnz     loc_140005D29
0x140005b35  mov     word ptr [rsp+rax*2+160h+var_E8], si
0x140005b3a  mov     r10, rsi
0x140005b3d  movsx   r8d, [rsp+r10+160h+var_128]
0x140005b43  mov     edx, 4
0x140005b48  mov     rcx, r14
0x140005b4b  call    output_bits
0x140005b50  add     r10, rbx
0x140005b53  cmp     r10, r11
0x140005b56  jnz     short loc_140005B3D
0x140005b58  mov     ebx, esi
0x140005b5a  test    r13d, r13d
0x140005b5d  jle     loc_140005BEC
0x140005b63  mov     r11d, esi
0x140005b66  lea     ecx, [rbx+1]
0x140005b69  movsxd  rsi, ebx
0x140005b6c  movsxd  rax, ecx
0x140005b6f  movzx   edx, byte ptr [rsi+r15]
0x140005b74  cmp     [rax+r15], dl
0x140005b78  jnz     short loc_140005B92
0x140005b7a  inc     ecx
0x140005b7c  inc     r11d
0x140005b7f  movsxd  rax, ecx
0x140005b82  cmp     [rax+r15], dl
0x140005b86  jz      short loc_140005B7A
0x140005b88  cmp     r11d, 4
0x140005b8c  jge     loc_140005C44
0x140005b92  lea     rdi, [rsi+r12]
0x140005b96  movzx   ecx, byte ptr [rdi]
0x140005b99  lea     rax, qword_140013210
0x140005ba0  sub     rcx, rdx
0x140005ba3  mov     r10b, [rcx+rax+11h]
0x140005ba8  movsx   rax, r10b
0x140005bac  mov     rcx, r14
0x140005baf  movzx   r8d, word ptr [rsp+rax*2+160h+var_E8]
0x140005bb5  movsx   edx, [rsp+rax+160h+var_128]
0x140005bba  call    output_bits
0x140005bbf  cmp     r10b, 11h
0x140005bc3  jz      short loc_140005C2C
0x140005bc5  cmp     r10b, 12h
0x140005bc9  jz      loc_140005C8E
0x140005bcf  cmp     r10b, 13h
0x140005bd3  jz      loc_140005D54
0x140005bd9  inc     ebx
0x140005bdb  mov     esi, 0
0x140005be0  cmp     ebx, r13d
0x140005be3  jl      loc_140005B63
0x140005be9  mov     rdi, r13
0x140005bec  mov     al, [rsp+160h+var_140]
0x140005bf0  mov     r8, rdi; Size
0x140005bf3  mov     rdx, r15; Src
0x140005bf6  mov     [rdi+r15], al
0x140005bfa  mov     rcx, r12; void *
0x140005bfd  call    memmove
0x140005c02  mov     rcx, [rbp+60h+var_50]
0x140005c06  xor     rcx, rsp; StackCookie
0x140005c09  call    __security_check_cookie
0x140005c0e  add     rsp, 128h
0x140005c15  pop     r15
0x140005c17  pop     r14
0x140005c19  pop     r13
0x140005c1b  pop     r12
0x140005c1d  pop     rdi
0x140005c1e  pop     rsi
0x140005c1f  pop     rbx
0x140005c20  pop     rbp
0x140005c21  retn
0x140005c23  add     [rbp+60h+var_8E], bx
0x140005c27  jmp     loc_140005A70
0x140005c2c  lea     r8d, [r11-4]
0x140005c30  mov     edx, 4
0x140005c35  mov     rcx, r14
0x140005c38  call    output_bits
0x140005c3d  dec     ebx
0x140005c3f  add     ebx, r11d
0x140005c42  jmp     short loc_140005BD9
0x140005c44  test    dl, dl
0x140005c46  jnz     loc_140005D40
0x140005c4c  mov     eax, 33h ; '3'
0x140005c51  cmp     r11d, eax
0x140005c54  cmovg   r11d, eax
0x140005c58  cmp     r11d, 13h
0x140005c5c  setnle  r10b
0x140005c60  add     r10b, 11h
0x140005c64  lea     rdi, [r12+rsi]
0x140005c68  jmp     loc_140005BA8
0x140005c6d  movzx   ecx, byte ptr [r10+r12]
0x140005c72  cmp     edx, edi
0x140005c74  cmovg   edx, edi
0x140005c77  sub     rcx, r9
0x140005c7a  movzx   eax, byte ptr [rcx+r14+11h]
0x140005c80  add     [rbp+rax*2+60h+var_B0], bx
0x140005c85  add     [rbp+60h+var_8A], bx
0x140005c89  jmp     loc_140005A70
0x140005c8e  lea     r8d, [r11-14h]
0x140005c92  mov     edx, 5
0x140005c97  jmp     short loc_140005C35
0x140005c99  mov     edx, r11d
0x140005c9c  lea     r9, [rsp+160h+var_E8]
0x140005ca1  lea     r8, [rbp+60h+var_B0]
0x140005ca5  mov     rcx, r14
0x140005ca8  call    make_tree2
0x140005cad  mov     ecx, esi
0x140005caf  mov     r11d, 14h
0x140005cb5  cmp     ecx, r11d
0x140005cb8  jge     short loc_140005CCC
0x140005cba  movsxd  rax, ecx
0x140005cbd  cmp     [rsp+rax+160h+var_128], 12h
0x140005cc2  jnb     loc_140005B3A
0x140005cc8  add     ecx, ebx
0x140005cca  jmp     short loc_140005CB5
0x140005ccc  mov     [rsp+160h+var_110], esi
0x140005cd0  mov     rcx, rbx
0x140005cd3  movzx   eax, word ptr [rsp+rcx*2+160h+var_110]
0x140005cd8  lea     rdx, [rcx+1]
0x140005cdc  movzx   ecx, word ptr [r14+rcx*2+2548h]
0x140005ce5  add     cx, ax
0x140005ce8  add     cx, cx
0x140005ceb  mov     word ptr [rsp+rdx*2+160h+var_110], cx
0x140005cf0  mov     rcx, rdx
0x140005cf3  cmp     rdx, 11h
0x140005cf7  jnz     short loc_140005CD3
0x140005cf9  mov     rdx, rsi
0x140005cfc  movsx   rcx, [rsp+rdx+160h+var_128]
0x140005d02  movzx   eax, word ptr [rsp+rcx*2+160h+var_110]
0x140005d07  mov     word ptr [rsp+rdx*2+160h+var_E8], ax
0x140005d0c  add     ax, bx
0x140005d0f  add     rdx, rbx
0x140005d12  mov     word ptr [rsp+rcx*2+160h+var_110], ax
0x140005d17  cmp     rdx, r11
0x140005d1a  jnz     short loc_140005CFC
0x140005d1c  jmp     loc_140005B3A
0x140005d21  mov     edx, r11d
0x140005d24  jmp     loc_140005A6C
0x140005d29  test    ax, ax
0x140005d2c  jnz     short loc_140005D37
0x140005d2e  mov     [rbp+60h+var_AE], bx
0x140005d32  jmp     loc_140005AA1
0x140005d37  mov     [rbp+60h+var_B0], bx
0x140005d3b  jmp     loc_140005AA1
0x140005d40  mov     eax, 5
0x140005d45  mov     r10b, 13h
0x140005d48  cmp     r11d, eax
0x140005d4b  cmovg   r11d, eax
0x140005d4f  jmp     loc_140005C64
0x140005d54  lea     r8d, [r11-4]
0x140005d58  mov     edx, 1
0x140005d5d  mov     rcx, r14
0x140005d60  call    output_bits
0x140005d65  movzx   eax, byte ptr [rsi+r15]
0x140005d6a  movzx   r10d, byte ptr [rdi]
0x140005d6e  sub     r10, rax
0x140005d71  lea     rax, qword_140013210
0x140005d78  movsx   rax, byte ptr [r10+rax+11h]
0x140005d7e  movzx   r8d, word ptr [rsp+rax*2+160h+var_E8]
0x140005d84  movsx   edx, [rsp+rax+160h+var_128]
0x140005d89  jmp     loc_140005C35
```
