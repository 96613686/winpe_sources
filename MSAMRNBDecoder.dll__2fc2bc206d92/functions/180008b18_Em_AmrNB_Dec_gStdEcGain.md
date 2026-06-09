# Em_AmrNB_Dec_gStdEcGain

- ea: `0x180008b18`
- end: `0x180008e40`
- name: `Em_AmrNB_Dec_gStdEcGain`
- size: `808`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003800`

## callees

- `0x180004c4c`
- `0x180008b18`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_gStdEcGain(__int16 *a1, __int64 a2)
{
  __int16 v4; // ax
  __int16 v5; // cx
  __int16 v6; // dx
  int v7; // esi
  __int16 v8; // ax
  __int16 v9; // r8
  bool v10; // zf
  __int16 v11; // dx
  int v12; // ecx
  bool v13; // cc
  int i; // r8d
  __int64 v15; // r11
  int v16; // eax
  __int64 j; // rcx
  int v18; // r11d
  int v19; // esi
  __int64 v20; // r8
  __int64 v21; // rcx
  __int16 v22; // r8
  __int16 v23; // cx
  __int16 v24; // cx
  __int16 v25; // r11
  __int16 v26; // ax

  v4 = Em_AmrNB_Dec_gMedian(a1 + 539);
  v5 = a1[543];
  v6 = 0x4000;
  if ( v4 <= v5 )
    v5 = v4;
  if ( v5 <= 0x4000 )
    v6 = v5;
  v7 = (v6 * word_1800165D6[a1[526]]) >> 15;
  *(_WORD *)(a2 + 1302) = v7;
  v8 = Em_AmrNB_Dec_gMedian(a1 + 534);
  v9 = a1[538];
  if ( v8 <= v9 )
    v9 = v8;
  v10 = *(_WORD *)(a2 + 1306) == 7;
  *(_WORD *)(a2 + 1304) = (v9 * word_180016CAE[a1[526]]) >> 15;
  v11 = 0x7FFF;
  if ( v10 )
  {
    v12 = 2 * (__int16)v7;
    if ( v12 == (__int16)(2 * v7) )
      goto LABEL_14;
    v13 = (__int16)v7 <= 0;
  }
  else
  {
    v12 = 2 * a1[204];
    if ( v12 == (__int16)(2 * a1[204]) )
      goto LABEL_14;
    v13 = a1[204] <= 0;
  }
  LOWORD(v12) = 0x7FFF;
  if ( v13 )
    LOWORD(v12) = 0x8000;
LABEL_14:
  for ( i = *(__int16 *)(a2 + 1296); i < 40; *(_WORD *)(a2 + 2 * v15 + 88) = v16 )
  {
    v15 = i;
    v16 = (__int16)(((__int16)v12 * *(__int16 *)(a2 + 2LL * (i - *(__int16 *)(a2 + 1296)) + 88)) >> 15)
        + *(__int16 *)(a2 + 2LL * i + 88);
    if ( v16 <= 0x7FFF )
    {
      if ( v16 < -32768 )
        LOWORD(v16) = 0x8000;
    }
    else
    {
      LOWORD(v16) = 0x7FFF;
    }
    ++i;
  }
  for ( j = 0; j != 4; ++j )
  {
    a1[j + 539] = a1[j + 540];
    a1[j + 534] = a1[j + 535];
  }
  LOWORD(v18) = 0;
  a1[543] = *(_WORD *)(a2 + 1302);
  LOWORD(v19) = 0;
  v20 = 0;
  a1[538] = *(_WORD *)(a2 + 1304);
  do
  {
    v18 = a1[v20 + 212] + (__int16)v18;
    if ( v18 <= 0x7FFF )
    {
      if ( v18 < -32768 )
        LOWORD(v18) = 0x8000;
    }
    else
    {
      LOWORD(v18) = 0x7FFF;
    }
    v19 = a1[v20 + 216] + (__int16)v19;
    if ( v19 <= 0x7FFF )
    {
      if ( v19 < -32768 )
        LOWORD(v19) = 0x8000;
    }
    else
    {
      LOWORD(v19) = 0x7FFF;
    }
    ++v20;
  }
  while ( v20 != 4 );
  v21 = 3;
  do
  {
    a1[v21 + 212] = a1[v21 + 211];
    a1[v21 + 216] = a1[v21 + 215];
    --v21;
  }
  while ( v21 );
  v22 = -14336;
  if ( (__int16)((__int16)v18 << 13 >> 15) >= -14336 )
    v22 = (__int16)v18 << 13 >> 15;
  v23 = -2381;
  a1[212] = v22;
  if ( (__int16)((__int16)v19 << 13 >> 15) >= -2381 )
    v23 = (__int16)v19 << 13 >> 15;
  a1[216] = v23;
  v24 = 13017;
  if ( *(_WORD *)(a2 + 1306) || (*(_BYTE *)(a2 + 1308) & 1) != 0 )
  {
    a1[204] = *(_WORD *)(a2 + 1302);
    if ( *(__int16 *)(a2 + 1302) > 13017 )
      a1[204] = 13017;
  }
  v25 = *(_WORD *)(a2 + 1306);
  v26 = *(_WORD *)(a2 + 1302);
  *(_WORD *)(a2 + 1300) = v26;
  if ( v25 == 7 )
  {
    v24 = v26;
  }
  else
  {
    if ( v26 <= 13017 )
      v24 = v26;
    else
      *(_WORD *)(a2 + 1300) = 13017;
    if ( v25 == 6 && a1[313] > 45 )
      v24 >>= 2;
  }
  if ( 2 * v24 == (__int16)(2 * v24) )
  {
    v11 = 2 * v24;
  }
  else if ( v24 <= 0 )
  {
    v11 = 0x8000;
  }
  *(_WORD *)(a2 + 1300) = v11;
  if ( v25 == 5 )
  {
    *(_QWORD *)(a2 + 1320) += 4LL;
  }
  else if ( v25 || (*(_BYTE *)(a2 + 1308) & 1) == 0 )
  {
    *(_QWORD *)(a2 + 1320) += 2LL;
  }
  return 0;
}

```

## disassembly

```asm
0x180008b18  push    rbx
0x180008b1a  push    rbp
0x180008b1b  push    rsi
0x180008b1c  push    rdi
0x180008b1d  push    r14
0x180008b1f  sub     rsp, 20h
0x180008b23  mov     rbx, rdx
0x180008b26  mov     rdi, rcx
0x180008b29  mov     r14d, 5
0x180008b2f  add     rcx, 436h; Src
0x180008b36  mov     edx, r14d
0x180008b39  call    Em_AmrNB_Dec_gMedian
0x180008b3e  movzx   ecx, word ptr [rdi+43Eh]
0x180008b45  mov     edx, 4000h
0x180008b4a  cmp     ax, cx
0x180008b4d  cmovle  cx, ax
0x180008b51  cmp     cx, dx
0x180008b54  jg      short loc_180008B59
0x180008b56  movzx   edx, cx
0x180008b59  movsx   rax, word ptr [rdi+41Ch]
0x180008b61  lea     rbp, cs:180000000h
0x180008b68  lea     rcx, [rdi+42Ch]; Src
0x180008b6f  movsx   esi, ss:rva word_1800165D6[rbp+rax*2]
0x180008b77  movsx   eax, dx
0x180008b7a  mov     edx, r14d
0x180008b7d  imul    esi, eax
0x180008b80  sar     esi, 0Fh
0x180008b83  mov     [rbx+516h], si
0x180008b8a  call    Em_AmrNB_Dec_gMedian
0x180008b8f  movzx   r8d, word ptr [rdi+434h]
0x180008b97  mov     r9d, 0FFFF8000h
0x180008b9d  movsx   rcx, word ptr [rdi+41Ch]
0x180008ba5  cmp     ax, r8w
0x180008ba9  cmovle  r8w, ax
0x180008bae  xor     r10d, r10d
0x180008bb1  movsx   eax, r8w
0x180008bb5  movsx   edx, ss:rva word_180016CAE[rbp+rcx*2]
0x180008bbd  imul    edx, eax
0x180008bc0  sar     edx, 0Fh
0x180008bc3  cmp     word ptr [rbx+51Ah], 7
0x180008bcb  mov     [rbx+518h], dx
0x180008bd2  mov     edx, 7FFFh
0x180008bd7  jnz     short loc_180008BEA
0x180008bd9  movsx   ecx, si
0x180008bdc  add     ecx, ecx
0x180008bde  movsx   eax, cx
0x180008be1  cmp     ecx, eax
0x180008be3  jz      short loc_180008C09
0x180008be5  test    si, si
0x180008be8  jmp     short loc_180008C02
0x180008bea  movsx   r8d, word ptr [rdi+198h]
0x180008bf2  mov     ecx, r8d
0x180008bf5  add     ecx, ecx
0x180008bf7  movsx   eax, cx
0x180008bfa  cmp     ecx, eax
0x180008bfc  jz      short loc_180008C09
0x180008bfe  test    r8w, r8w
0x180008c02  mov     ecx, edx
0x180008c04  cmovle  cx, r9w
0x180008c09  movsx   r8d, word ptr [rbx+510h]
0x180008c11  cmp     r8d, 28h ; '('
0x180008c15  jge     short loc_180008C62
0x180008c17  movsx   esi, cx
0x180008c1a  movsx   eax, word ptr [rbx+510h]
0x180008c21  mov     ecx, r8d
0x180008c24  sub     ecx, eax
0x180008c26  movsxd  r11, r8d
0x180008c29  movsxd  rax, ecx
0x180008c2c  movsx   ecx, word ptr [rbx+rax*2+58h]
0x180008c31  movsx   eax, word ptr [rbx+r11*2+58h]
0x180008c37  imul    ecx, esi
0x180008c3a  sar     ecx, 0Fh
0x180008c3d  movsx   ecx, cx
0x180008c40  add     eax, ecx
0x180008c42  cmp     eax, edx
0x180008c44  jle     short loc_180008C4B
0x180008c46  movzx   eax, dx
0x180008c49  jmp     short loc_180008C53
0x180008c4b  cmp     eax, r9d
0x180008c4e  jge     short loc_180008C53
0x180008c50  mov     eax, r9d
0x180008c53  inc     r8d
0x180008c56  mov     [rbx+r11*2+58h], ax
0x180008c5c  cmp     r8d, 28h ; '('
0x180008c60  jl      short loc_180008C1A
0x180008c62  mov     rcx, r10
0x180008c65  movzx   eax, word ptr [rdi+rcx*2+438h]
0x180008c6d  mov     [rdi+rcx*2+436h], ax
0x180008c75  movzx   eax, word ptr [rdi+rcx*2+42Eh]
0x180008c7d  mov     [rdi+rcx*2+42Ch], ax
0x180008c85  inc     rcx
0x180008c88  cmp     rcx, 4
0x180008c8c  jnz     short loc_180008C65
0x180008c8e  movzx   eax, word ptr [rbx+516h]
0x180008c95  movzx   r11d, r10w
0x180008c99  mov     [rdi+43Eh], ax
0x180008ca0  movzx   esi, r10w
0x180008ca4  movzx   eax, word ptr [rbx+518h]
0x180008cab  mov     r8, r10
0x180008cae  mov     [rdi+434h], ax
0x180008cb5  movsx   ecx, word ptr [rdi+r8*2+1A8h]
0x180008cbe  movsx   r11d, r11w
0x180008cc2  add     r11d, ecx
0x180008cc5  cmp     r11d, edx
0x180008cc8  jle     short loc_180008CCF
0x180008cca  mov     r11d, edx
0x180008ccd  jmp     short loc_180008CD8
0x180008ccf  cmp     r11d, r9d
0x180008cd2  jge     short loc_180008CD8
0x180008cd4  movzx   r11d, r9w
0x180008cd8  movsx   ecx, word ptr [rdi+r8*2+1B0h]
0x180008ce1  movsx   esi, si
0x180008ce4  add     esi, ecx
0x180008ce6  cmp     esi, edx
0x180008ce8  jle     short loc_180008CEE
0x180008cea  mov     esi, edx
0x180008cec  jmp     short loc_180008CF7
0x180008cee  cmp     esi, r9d
0x180008cf1  jge     short loc_180008CF7
0x180008cf3  movzx   esi, r9w
0x180008cf7  inc     r8
0x180008cfa  cmp     r8, 4
0x180008cfe  jnz     short loc_180008CB5
0x180008d00  lea     ecx, [r8-1]
0x180008d04  movzx   eax, word ptr [rdi+rcx*2+1A6h]
0x180008d0c  mov     [rdi+rcx*2+1A8h], ax
0x180008d14  movzx   eax, word ptr [rdi+rcx*2+1AEh]
0x180008d1c  mov     [rdi+rcx*2+1B0h], ax
0x180008d24  sub     rcx, 1
0x180008d28  jnz     short loc_180008D04
0x180008d2a  movsx   ecx, r11w
0x180008d2e  mov     r8d, 0FFFFC800h
0x180008d34  shl     ecx, 0Dh
0x180008d37  movsx   eax, si
0x180008d3a  shl     eax, 0Dh
0x180008d3d  sar     ecx, 0Fh
0x180008d40  sar     eax, 0Fh
0x180008d43  cmp     r8w, cx
0x180008d47  jg      short loc_180008D4D
0x180008d49  movzx   r8d, cx
0x180008d4d  mov     ecx, 0FFFFF6B3h
0x180008d52  mov     [rdi+1A8h], r8w
0x180008d5a  cmp     cx, ax
0x180008d5d  jg      short loc_180008D62
0x180008d5f  movzx   ecx, ax
0x180008d62  mov     [rdi+1B0h], cx
0x180008d69  mov     ecx, 32D9h
0x180008d6e  cmp     [rbx+51Ah], r10w
0x180008d76  jnz     short loc_180008D81
0x180008d78  test    byte ptr [rbx+51Ch], 1
0x180008d7f  jz      short loc_180008D9F
0x180008d81  movzx   eax, word ptr [rbx+516h]
0x180008d88  mov     [rdi+198h], ax
0x180008d8f  cmp     [rbx+516h], cx
0x180008d96  jle     short loc_180008D9F
0x180008d98  mov     [rdi+198h], cx
0x180008d9f  movzx   r11d, word ptr [rbx+51Ah]
0x180008da7  movzx   eax, word ptr [rbx+516h]
0x180008dae  mov     [rbx+514h], ax
0x180008db5  cmp     r11w, 7
0x180008dba  jz      short loc_180008DE4
0x180008dbc  cmp     ax, cx
0x180008dbf  jle     short loc_180008DCA
0x180008dc1  mov     [rbx+514h], cx
0x180008dc8  jmp     short loc_180008DCD
0x180008dca  movzx   ecx, ax
0x180008dcd  cmp     r11w, 6
0x180008dd2  jnz     short loc_180008DE7
0x180008dd4  cmp     word ptr [rdi+272h], 2Dh ; '-'
0x180008ddc  jle     short loc_180008DE7
0x180008dde  sar     cx, 2
0x180008de2  jmp     short loc_180008DE7
0x180008de4  movzx   ecx, ax
0x180008de7  movsx   r8d, cx
0x180008deb  add     r8d, r8d
0x180008dee  movsx   eax, r8w
0x180008df2  cmp     r8d, eax
0x180008df5  jz      short loc_180008E01
0x180008df7  test    cx, cx
0x180008dfa  cmovle  dx, r9w
0x180008dff  jmp     short loc_180008E05
0x180008e01  movzx   edx, r8w
0x180008e05  mov     [rbx+514h], dx
0x180008e0c  cmp     r11w, r14w
0x180008e10  jnz     short loc_180008E1C
0x180008e12  add     qword ptr [rbx+528h], 4
0x180008e1a  jmp     short loc_180008E33
0x180008e1c  test    r11w, r11w
0x180008e20  jnz     short loc_180008E2B
0x180008e22  test    byte ptr [rbx+51Ch], 1
0x180008e29  jnz     short loc_180008E33
0x180008e2b  add     qword ptr [rbx+528h], 2
0x180008e33  xor     eax, eax
0x180008e35  add     rsp, 20h
0x180008e39  pop     r14
0x180008e3b  pop     rdi
0x180008e3c  pop     rsi
0x180008e3d  pop     rbp
0x180008e3e  pop     rbx
0x180008e3f  retn
```
