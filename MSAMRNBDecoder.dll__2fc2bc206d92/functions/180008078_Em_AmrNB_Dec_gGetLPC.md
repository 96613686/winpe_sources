# Em_AmrNB_Dec_gGetLPC

- ea: `0x180008078`
- end: `0x1800085ad`
- name: `Em_AmrNB_Dec_gGetLPC`
- size: `1333`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180003800`
- `0x1800051e0`

## callees

- `0x180001400`
- `0x180007e64`
- `0x180007eb4`
- `0x180008048`
- `0x180008078`
- `0x180008834`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_gGetLPC(unsigned int a1, __int64 a2, unsigned __int16 **a3, __int64 a4)
{
  unsigned __int16 *v8; // r9
  __int64 v9; // rdx
  unsigned __int16 *v10; // r8
  _WORD *v11; // rcx
  __int16 v12; // ax
  __int64 v13; // rcx
  __int16 v14; // ax
  _WORD *v15; // rdx
  unsigned int v16; // ecx
  __int64 v17; // rdx
  __int16 v18; // ax
  __int16 v19; // ax
  __int16 v20; // ax
  __int16 v21; // ax
  __int16 v22; // ax
  __int16 v23; // ax
  __int16 v24; // ax
  __int16 v25; // ax
  __int64 v26; // rcx
  __int16 v27; // ax
  _WORD *v28; // rdx
  __int64 v29; // rcx
  __int16 v30; // ax
  _WORD *v31; // rdx
  __int64 v32; // rbx
  __int64 v33; // r8
  int v34; // eax
  int v35; // ecx
  int v36; // edx
  int v37; // eax
  int v38; // eax
  int i; // r9d
  __int64 v40; // rcx
  __int16 *v41; // rcx
  __int64 *v42; // rdi
  __int64 *v43; // r10
  unsigned __int16 *v44; // r9
  __int64 v45; // rdx
  unsigned __int16 *v46; // r8
  unsigned __int16 *v47; // r9
  int v48; // eax
  __int64 v49; // rcx
  __int64 v50; // rdx
  __int16 v51; // ax
  int v52; // edx
  int v53; // eax
  int v54; // eax
  int m; // r9d
  __int64 v56; // rcx
  __int64 j; // rdx
  int v58; // r8d
  int v59; // eax
  int v60; // eax
  int k; // r9d
  __int64 v62; // rcx
  __int16 v64; // [rsp+20h] [rbp-30h] BYREF
  __int16 v65; // [rsp+22h] [rbp-2Eh]
  __int16 v66; // [rsp+24h] [rbp-2Ch]
  __int16 v67; // [rsp+26h] [rbp-2Ah]
  __int16 v68; // [rsp+28h] [rbp-28h]
  __int16 v69; // [rsp+2Ah] [rbp-26h]
  __int16 v70; // [rsp+2Ch] [rbp-24h]
  __int16 v71; // [rsp+2Eh] [rbp-22h]
  __int16 v72; // [rsp+30h] [rbp-20h]
  __int16 v73; // [rsp+32h] [rbp-1Eh]
  _WORD v74[4]; // [rsp+34h] [rbp-1Ch] BYREF
  __int16 v75; // [rsp+3Ch] [rbp-14h]
  __int16 v76; // [rsp+3Eh] [rbp-12h]
  __int16 v77; // [rsp+40h] [rbp-10h]
  __int16 v78; // [rsp+42h] [rbp-Eh]
  __int16 v79; // [rsp+44h] [rbp-Ch]
  __int16 v80; // [rsp+46h] [rbp-Ah]

  if ( a1 == 7 )
  {
    v8 = *a3;
    v9 = **a3;
    v10 = *a3 + 1;
    *a3 = v10;
    v11 = (_WORD *)(8 * v9 + 108226);
    v64 = Em_AmrNB_Dec_MR122LsfCB1[4 * v9];
    v65 = v11[3221225472LL];
    v74[0] = v11[3221225473LL];
    v12 = v11[3221225474LL];
    v13 = *v10;
    v74[1] = v12;
    *a3 = v8 + 2;
    v14 = Em_AmrNB_Dec_MR122LsfCB2[4 * v13];
    v15 = (_WORD *)(8 * v13 + 93570);
    v16 = v8[2];
    v66 = v14;
    v67 = v15[3221225472LL];
    v74[2] = v15[3221225473LL];
    v74[3] = v15[3221225474LL];
    *a3 = v8 + 3;
    v17 = 4 * (v16 >> 1);
    v18 = Em_AmrNB_Dec_MR122LsfCB3[v17];
    if ( (v16 & 1) != 0 )
    {
      if ( v18 == (__int16)0x8000 )
        v20 = 0x7FFF;
      else
        v20 = -v18;
      v68 = v20;
      v21 = word_18001ACF2[v17];
      if ( v21 == (__int16)0x8000 )
        v22 = 0x7FFF;
      else
        v22 = -v21;
      v69 = v22;
      v23 = word_18001ACF4[v17];
      if ( v23 == (__int16)0x8000 )
        v24 = 0x7FFF;
      else
        v24 = -v23;
      v75 = v24;
      v25 = word_18001ACF6[v17];
      if ( v25 == (__int16)0x8000 )
        v19 = 0x7FFF;
      else
        v19 = -v25;
    }
    else
    {
      v68 = Em_AmrNB_Dec_MR122LsfCB3[4 * (v16 >> 1)];
      v69 = word_18001ACF2[v17];
      v75 = word_18001ACF4[v17];
      v19 = word_18001ACF6[v17];
    }
    v26 = v8[3];
    *a3 = v8 + 4;
    v76 = v19;
    v27 = Em_AmrNB_Dec_MR122LsfCB4[4 * v26];
    v28 = (_WORD *)(8 * v26 + 89234);
    v29 = v8[4];
    v70 = v27;
    v71 = v28[3221225472LL];
    v77 = v28[3221225473LL];
    v30 = v28[3221225474LL];
    v31 = (_WORD *)(8 * v29 + 92818);
    v78 = v30;
    *a3 = v8 + 5;
    LODWORD(v32) = 0;
    v33 = 0;
    v72 = Em_AmrNB_Dec_MR122LsfCB5[4 * v29];
    v73 = v31[3221225472LL];
    v79 = v31[3221225473LL];
    v80 = v31[3221225474LL];
    do
    {
      v34 = (__int16)((21299 * *(__int16 *)(a2 + 2 * v33 + 60)) >> 15) + Em_AmrNB_Dec_MeanLsfMR122[v33];
      if ( v34 <= 0x7FFF )
      {
        if ( v34 < -32768 )
          LOWORD(v34) = 0x8000;
      }
      else
      {
        LOWORD(v34) = 0x7FFF;
      }
      v35 = (__int16)v74[v33];
      v36 = (__int16)v34;
      v37 = (__int16)v34 + *(&v64 + v33);
      *(_WORD *)(a2 + 2 * v33 + 60) = v74[v33];
      if ( v37 <= 0x7FFF )
      {
        if ( v37 < -32768 )
          LOWORD(v37) = 0x8000;
      }
      else
      {
        LOWORD(v37) = 0x7FFF;
      }
      *(&v64 + v33) = v37;
      v38 = v36 + v35;
      if ( v36 + v35 <= 0x7FFF )
      {
        if ( v38 < -32768 )
          LOWORD(v38) = 0x8000;
      }
      else
      {
        LOWORD(v38) = 0x7FFF;
      }
      v74[v33++] = v38;
    }
    while ( v33 != 10 );
    Em_AmrNB_Dec_ReorderLsf(&v64);
    Em_AmrNB_Dec_ReorderLsf(v74);
    for ( i = 1; i <= 10; ++i )
    {
      v40 = 10LL - (unsigned int)i;
      *(_WORD *)(a2 + 2 * v40) = v74[v40];
    }
    Em_AmrNB_Dec_LsfToLsp(&v64, a4 + 24);
    v41 = v74;
LABEL_66:
    Em_AmrNB_Dec_LsfToLsp(v41, a4 + 68);
    Em_AmrNB_Dec_interpolateLsp(a1, a4, a2 + 80);
    do
    {
      Em_AmrNB_Dec_LspToLpc(a4 + 2LL * (int)v32);
      LODWORD(v32) = v32 + 11;
    }
    while ( (_DWORD)v32 != 44 );
    return 0;
  }
  if ( a1 <= 1 )
  {
    v42 = Em_AmrNB_Dec_MR475MR515LsfCB3;
  }
  else
  {
    v42 = Em_AmrNB_Dec_LsfCB3;
    if ( a1 == 5 )
    {
      v43 = Em_AmrNB_Dec_MR795LsfCB1;
      goto LABEL_38;
    }
  }
  v43 = Em_AmrNB_Dec_LsfCB1;
LABEL_38:
  v44 = *a3;
  v32 = 0;
  v45 = **a3;
  v46 = *a3 + 1;
  *a3 = v46;
  v47 = v44 + 2;
  v64 = *((_WORD *)v43 + 3 * v45);
  v65 = *((_WORD *)v43 + 3 * v45 + 1);
  v66 = *((_WORD *)v43 + 3 * v45 + 2);
  v48 = *v46;
  *a3 = v47;
  v49 = (unsigned int)(3 * v48);
  if ( a1 <= 1 )
    v49 = (unsigned int)(6 * v48);
  v50 = *v47;
  v67 = Em_AmrNB_Dec_LsfCB2[v49];
  v68 = word_1800196E2[v49];
  v69 = word_1800196E4[v49];
  *a3 = v47 + 1;
  v70 = v42[v50];
  v71 = WORD1(v42[v50]);
  v51 = WORD2(v42[v50]);
  v73 = HIWORD(v42[v50]);
  v72 = v51;
  if ( a1 != 8 )
  {
    for ( j = 0; j != 10; ++j )
    {
      v58 = Em_AmrNB_Dec_MeanLsf[j] + (__int16)((*(__int16 *)(a2 + 2 * j + 60) * Em_AmrNB_Dec_PredFactor[j]) >> 15);
      if ( v58 <= 0x7FFF )
      {
        if ( v58 < -32768 )
          LOWORD(v58) = 0x8000;
      }
      else
      {
        LOWORD(v58) = 0x7FFF;
      }
      v59 = *(&v64 + j);
      *(_WORD *)(a2 + 2 * j + 60) = v59;
      v60 = v59 + (__int16)v58;
      if ( v60 <= 0x7FFF )
      {
        if ( v60 < -32768 )
          LOWORD(v60) = 0x8000;
      }
      else
      {
        LOWORD(v60) = 0x7FFF;
      }
      *(&v64 + j) = v60;
    }
    Em_AmrNB_Dec_ReorderLsf(&v64);
    for ( k = 1; k <= 10; ++k )
    {
      v62 = 10LL - (unsigned int)k;
      *(_WORD *)(a2 + 2 * v62) = *(&v64 + v62);
    }
    v41 = &v64;
    goto LABEL_66;
  }
  do
  {
    v52 = *(__int16 *)(a2 + 2 * v32 + 60) + Em_AmrNB_Dec_MeanLsf[v32];
    if ( v52 <= 0x7FFF )
    {
      if ( v52 < -32768 )
        LOWORD(v52) = 0x8000;
    }
    else
    {
      LOWORD(v52) = 0x7FFF;
    }
    v53 = *(&v64 + v32);
    *(_WORD *)(a2 + 2 * v32 + 60) = v53;
    v54 = v53 + (__int16)v52;
    if ( v54 <= 0x7FFF )
    {
      if ( v54 < -32768 )
        LOWORD(v54) = 0x8000;
    }
    else
    {
      LOWORD(v54) = 0x7FFF;
    }
    *(&v64 + v32++) = v54;
  }
  while ( v32 != 10 );
  Em_AmrNB_Dec_ReorderLsf(&v64);
  for ( m = 1; m <= 10; ++m )
  {
    v56 = 10LL - (unsigned int)m;
    *(_WORD *)(a2 + 2 * v56) = *(&v64 + v56);
  }
  Em_AmrNB_Dec_LsfToLsp(&v64, a4);
  return 0;
}

```

## disassembly

```asm
0x180008078  push    rbp
0x18000807a  push    rbx
0x18000807b  push    rsi
0x18000807c  push    rdi
0x18000807d  push    r12
0x18000807f  push    r14
0x180008081  push    r15
0x180008083  mov     rbp, rsp
0x180008086  sub     rsp, 50h
0x18000808a  mov     rax, cs:__security_cookie
0x180008091  xor     rax, rsp
0x180008094  mov     [rbp+var_8], rax
0x180008098  mov     r12, r9
0x18000809b  mov     r15, r8
0x18000809e  mov     rsi, rdx
0x1800080a1  mov     r14d, ecx
0x1800080a4  cmp     ecx, 7
0x1800080a7  jnz     loc_180008342
0x1800080ad  mov     r9, [r8]
0x1800080b0  lea     r11, cs:180000000h
0x1800080b7  mov     r10d, 7FFFh
0x1800080bd  movzx   edx, word ptr [r9]
0x1800080c1  lea     r8, [r9+2]
0x1800080c5  mov     [r15], r8
0x1800080c8  lea     rbx, [r9+6]
0x1800080cc  movzx   eax, ds:rva Em_AmrNB_Dec_MR122LsfCB1[r11+rdx*8]
0x1800080d5  lea     rcx, ds:1A6C2h[rdx*8]
0x1800080dd  mov     [rbp+var_30], ax
0x1800080e1  movzx   eax, word ptr [rcx+r11]
0x1800080e6  mov     [rbp+var_2E], ax
0x1800080ea  movzx   eax, word ptr [rcx+r11+2]
0x1800080f0  mov     [rbp+var_1C], ax
0x1800080f4  movzx   eax, word ptr [rcx+r11+4]
0x1800080fa  movzx   ecx, word ptr [r8]
0x1800080fe  lea     r8, [r9+4]
0x180008102  mov     [rbp+var_1A], ax
0x180008106  mov     r9d, 0FFFF8000h
0x18000810c  mov     [r15], r8
0x18000810f  movzx   eax, ds:rva Em_AmrNB_Dec_MR122LsfCB2[r11+rcx*8]
0x180008118  lea     rdx, ds:16D82h[rcx*8]
0x180008120  movzx   ecx, word ptr [r8]
0x180008124  mov     [rbp+var_2C], ax
0x180008128  movzx   eax, word ptr [rdx+r11]
0x18000812d  mov     [rbp+var_2A], ax
0x180008131  movzx   eax, word ptr [rdx+r11+2]
0x180008137  mov     [rbp+var_18], ax
0x18000813b  movzx   eax, word ptr [rdx+r11+4]
0x180008141  mov     [rbp+var_16], ax
0x180008145  mov     eax, ecx
0x180008147  shr     eax, 1
0x180008149  shl     eax, 2
0x18000814c  mov     [r15], rbx
0x18000814f  mov     edx, eax
0x180008151  movzx   eax, ds:rva Em_AmrNB_Dec_MR122LsfCB3[r11+rax*2]
0x18000815a  test    cl, 1
0x18000815d  jnz     short loc_180008188
0x18000815f  mov     [rbp+var_28], ax
0x180008163  movzx   eax, ds:rva word_18001ACF2[r11+rdx*2]
0x18000816c  mov     [rbp+var_26], ax
0x180008170  movzx   eax, ds:rva word_18001ACF4[r11+rdx*2]
0x180008179  mov     [rbp+var_14], ax
0x18000817d  movzx   eax, ds:rva word_18001ACF6[r11+rdx*2]
0x180008186  jmp     short loc_1800081EB
0x180008188  cmp     ax, r9w
0x18000818c  jnz     short loc_180008194
0x18000818e  movzx   eax, r10w
0x180008192  jmp     short loc_180008197
0x180008194  neg     ax
0x180008197  mov     [rbp+var_28], ax
0x18000819b  movzx   eax, ds:rva word_18001ACF2[r11+rdx*2]
0x1800081a4  cmp     ax, r9w
0x1800081a8  jnz     short loc_1800081B0
0x1800081aa  movzx   eax, r10w
0x1800081ae  jmp     short loc_1800081B3
0x1800081b0  neg     ax
0x1800081b3  mov     [rbp+var_26], ax
0x1800081b7  movzx   eax, ds:rva word_18001ACF4[r11+rdx*2]
0x1800081c0  cmp     ax, r9w
0x1800081c4  jnz     short loc_1800081CC
0x1800081c6  movzx   eax, r10w
0x1800081ca  jmp     short loc_1800081CF
0x1800081cc  neg     ax
0x1800081cf  mov     [rbp+var_14], ax
0x1800081d3  movzx   eax, ds:rva word_18001ACF6[r11+rdx*2]
0x1800081dc  cmp     ax, r9w
0x1800081e0  jnz     short loc_1800081E8
0x1800081e2  movzx   eax, r10w
0x1800081e6  jmp     short loc_1800081EB
0x1800081e8  neg     ax
0x1800081eb  movzx   ecx, word ptr [rbx]
0x1800081ee  lea     r8, [rbx+2]
0x1800081f2  mov     [r15], r8
0x1800081f5  mov     [rbp+var_12], ax
0x1800081f9  movzx   eax, ds:rva Em_AmrNB_Dec_MR122LsfCB4[r11+rcx*8]
0x180008202  lea     rdx, ds:15C92h[rcx*8]
0x18000820a  movzx   ecx, word ptr [r8]
0x18000820e  mov     [rbp+var_24], ax
0x180008212  movzx   eax, word ptr [rdx+r11]
0x180008217  mov     [rbp+var_22], ax
0x18000821b  movzx   eax, word ptr [rdx+r11+2]
0x180008221  mov     [rbp+var_10], ax
0x180008225  movzx   eax, word ptr [rdx+r11+4]
0x18000822b  lea     rdx, ds:16A92h[rcx*8]
0x180008233  mov     [rbp+var_E], ax
0x180008237  lea     rax, [rbx+4]
0x18000823b  mov     [r15], rax
0x18000823e  xor     ebx, ebx
0x180008240  movzx   eax, ds:rva Em_AmrNB_Dec_MR122LsfCB5[r11+rcx*8]
0x180008249  mov     r8d, ebx
0x18000824c  mov     [rbp+var_20], ax
0x180008250  movzx   eax, word ptr [rdx+r11]
0x180008255  mov     [rbp+var_1E], ax
0x180008259  movzx   eax, word ptr [rdx+r11+2]
0x18000825f  mov     [rbp+var_C], ax
0x180008263  movzx   eax, word ptr [rdx+r11+4]
0x180008269  mov     [rbp+var_A], ax
0x18000826d  movsx   eax, word ptr [rsi+r8*2+3Ch]
0x180008273  imul    ecx, eax, 5333h
0x180008279  movsx   eax, ds:rva Em_AmrNB_Dec_MeanLsfMR122[r11+r8*2]
0x180008282  sar     ecx, 0Fh
0x180008285  movsx   edx, cx
0x180008288  add     eax, edx
0x18000828a  cmp     eax, r10d
0x18000828d  jle     short loc_180008295
0x18000828f  movzx   eax, r10w
0x180008293  jmp     short loc_18000829D
0x180008295  cmp     eax, r9d
0x180008298  jge     short loc_18000829D
0x18000829a  mov     eax, r9d
0x18000829d  movsx   ecx, [rbp+r8*2+var_1C]
0x1800082a3  movsx   edx, ax
0x1800082a6  movsx   eax, [rbp+r8*2+var_30]
0x1800082ac  add     eax, edx
0x1800082ae  mov     [rsi+r8*2+3Ch], cx
0x1800082b4  cmp     eax, r10d
0x1800082b7  jle     short loc_1800082BF
0x1800082b9  movzx   eax, r10w
0x1800082bd  jmp     short loc_1800082C7
0x1800082bf  cmp     eax, r9d
0x1800082c2  jge     short loc_1800082C7
0x1800082c4  mov     eax, r9d
0x1800082c7  mov     [rbp+r8*2+var_30], ax
0x1800082cd  lea     eax, [rdx+rcx]
0x1800082d0  cmp     eax, r10d
0x1800082d3  jle     short loc_1800082DB
0x1800082d5  movzx   eax, r10w
0x1800082d9  jmp     short loc_1800082E3
0x1800082db  cmp     eax, r9d
0x1800082de  jge     short loc_1800082E3
0x1800082e0  mov     eax, r9d
0x1800082e3  mov     [rbp+r8*2+var_1C], ax
0x1800082e9  inc     r8
0x1800082ec  cmp     r8, 0Ah
0x1800082f0  jnz     loc_18000826D
0x1800082f6  lea     rcx, [rbp+var_30]
0x1800082fa  call    Em_AmrNB_Dec_ReorderLsf
0x1800082ff  lea     rcx, [rbp+var_1C]
0x180008303  call    Em_AmrNB_Dec_ReorderLsf
0x180008308  mov     r9d, 1
0x18000830e  mov     eax, r9d
0x180008311  mov     ecx, 0Ah
0x180008316  sub     rcx, rax
0x180008319  inc     r9d
0x18000831c  movzx   eax, [rbp+rcx*2+var_1C]
0x180008321  mov     [rsi+rcx*2], ax
0x180008325  cmp     r9d, 0Ah
0x180008329  jle     short loc_18000830E
0x18000832b  lea     rdx, [r12+18h]
0x180008330  lea     rcx, [rbp+var_30]
0x180008334  call    Em_AmrNB_Dec_LsfToLsp
0x180008339  lea     rcx, [rbp+var_1C]
0x18000833d  jmp     loc_180008563
0x180008342  cmp     r14d, 1
0x180008346  jbe     short loc_18000835E
0x180008348  lea     rdi, Em_AmrNB_Dec_LsfCB3
0x18000834f  cmp     r14d, 5
0x180008353  jnz     short loc_180008365
0x180008355  lea     r10, Em_AmrNB_Dec_MR795LsfCB1
0x18000835c  jmp     short loc_18000836C
0x18000835e  lea     rdi, Em_AmrNB_Dec_MR475MR515LsfCB3
0x180008365  lea     r10, Em_AmrNB_Dec_LsfCB1
0x18000836c  mov     r9, [r8]
0x18000836f  xor     ebx, ebx
0x180008371  movzx   edx, word ptr [r9]
0x180008375  lea     r8, [r9+2]
0x180008379  mov     [r15], r8
0x18000837c  add     r9, 4
0x180008380  lea     rcx, [rdx+rdx*2]
0x180008384  movzx   eax, word ptr [r10+rcx*2]
0x180008389  mov     [rbp+var_30], ax
0x18000838d  movzx   eax, word ptr [r10+rcx*2+2]
0x180008393  lea     rcx, [rdx+rdx*2]
0x180008397  mov     [rbp+var_2E], ax
0x18000839b  movzx   eax, word ptr [r10+rcx*2+4]
0x1800083a1  mov     [rbp+var_2C], ax
0x1800083a5  movzx   eax, word ptr [r8]
0x1800083a9  mov     [r15], r9
0x1800083ac  lea     ecx, [rax+rax*2]
0x1800083af  test    r14d, r14d
0x1800083b2  jz      short loc_1800083BA
0x1800083b4  cmp     r14d, 1
0x1800083b8  jnz     short loc_1800083BC
0x1800083ba  add     ecx, ecx
0x1800083bc  movzx   edx, word ptr [r9]
0x1800083c0  lea     r11, cs:180000000h
0x1800083c7  movzx   eax, ds:rva Em_AmrNB_Dec_LsfCB2[r11+rcx*2]
0x1800083d0  mov     r10d, 7FFFh
0x1800083d6  mov     [rbp+var_2A], ax
0x1800083da  movzx   eax, ds:rva word_1800196E2[r11+rcx*2]
0x1800083e3  mov     [rbp+var_28], ax
0x1800083e7  movzx   eax, ds:rva word_1800196E4[r11+rcx*2]
0x1800083f0  lea     rcx, ds:0[rdx*4]
0x1800083f8  mov     [rbp+var_26], ax
0x1800083fc  lea     rax, [r9+2]
0x180008400  mov     [r15], rax
0x180008403  mov     r9d, 0FFFF8000h
0x180008409  movzx   eax, word ptr [rdi+rcx*2]
0x18000840d  mov     [rbp+var_24], ax
0x180008411  movzx   eax, word ptr [rdi+rcx*2+2]
0x180008416  mov     [rbp+var_22], ax
0x18000841a  movzx   eax, word ptr [rdi+rcx*2+4]
0x18000841f  movzx   ecx, word ptr [rdi+rdx*8+6]
0x180008424  mov     [rbp+var_1E], cx
0x180008428  mov     [rbp+var_20], ax
0x18000842c  cmp     r14d, 8
0x180008430  jnz     loc_1800084C6
0x180008436  movsx   edx, ds:rva Em_AmrNB_Dec_MeanLsf[r11+rbx*2]
0x18000843f  movsx   eax, word ptr [rsi+rbx*2+3Ch]
0x180008444  add     edx, eax
0x180008446  cmp     edx, r10d
0x180008449  jle     short loc_180008451
0x18000844b  movzx   edx, r10w
0x18000844f  jmp     short loc_180008459
0x180008451  cmp     edx, r9d
0x180008454  jge     short loc_180008459
0x180008456  mov     edx, r9d
0x180008459  movsx   eax, [rbp+rbx*2+var_30]
0x18000845e  mov     [rsi+rbx*2+3Ch], ax
0x180008463  mov     ecx, eax
0x180008465  movsx   eax, dx
0x180008468  add     eax, ecx
0x18000846a  cmp     eax, r10d
0x18000846d  jle     short loc_180008475
0x18000846f  movzx   eax, r10w
0x180008473  jmp     short loc_18000847D
0x180008475  cmp     eax, r9d
0x180008478  jge     short loc_18000847D
0x18000847a  mov     eax, r9d
0x18000847d  mov     [rbp+rbx*2+var_30], ax
0x180008482  inc     rbx
0x180008485  cmp     rbx, 0Ah
0x180008489  jnz     short loc_180008436
0x18000848b  lea     rcx, [rbp+var_30]
0x18000848f  call    Em_AmrNB_Dec_ReorderLsf
0x180008494  lea     r9d, [rbx-9]
0x180008498  mov     eax, r9d
0x18000849b  mov     ecx, 0Ah
0x1800084a0  sub     rcx, rax
0x1800084a3  inc     r9d
0x1800084a6  movzx   eax, [rbp+rcx*2+var_30]
0x1800084ab  mov     [rsi+rcx*2], ax
0x1800084af  cmp     r9d, 0Ah
0x1800084b3  jle     short loc_180008498
0x1800084b5  mov     rdx, r12
0x1800084b8  lea     rcx, [rbp+var_30]
0x1800084bc  call    Em_AmrNB_Dec_LsfToLsp
0x1800084c1  jmp     loc_180008590
0x1800084c6  mov     rdx, rbx
0x1800084c9  movsx   eax, word ptr [rsi+rdx*2+3Ch]
0x1800084ce  movsx   ecx, ds:rva Em_AmrNB_Dec_PredFactor[r11+rdx*2]
0x1800084d7  imul    ecx, eax
0x1800084da  movsx   eax, ds:rva Em_AmrNB_Dec_MeanLsf[r11+rdx*2]
0x1800084e3  sar     ecx, 0Fh
0x1800084e6  movsx   r8d, cx
0x1800084ea  add     r8d, eax
0x1800084ed  cmp     r8d, r10d
0x1800084f0  jle     short loc_1800084F8
0x1800084f2  movzx   r8d, r10w
0x1800084f6  jmp     short loc_180008500
0x1800084f8  cmp     r8d, r9d
0x1800084fb  jge     short loc_180008500
0x1800084fd  mov     r8d, r9d
0x180008500  movsx   eax, [rbp+rdx*2+var_30]
0x180008505  mov     [rsi+rdx*2+3Ch], ax
0x18000850a  mov     ecx, eax
0x18000850c  movsx   eax, r8w
0x180008510  add     eax, ecx
0x180008512  cmp     eax, r10d
0x180008515  jle     short loc_18000851D
0x180008517  movzx   eax, r10w
0x18000851b  jmp     short loc_180008525
0x18000851d  cmp     eax, r9d
0x180008520  jge     short loc_180008525
0x180008522  mov     eax, r9d
0x180008525  mov     [rbp+rdx*2+var_30], ax
0x18000852a  inc     rdx
0x18000852d  cmp     rdx, 0Ah
0x180008531  jnz     short loc_1800084C9
0x180008533  lea     rcx, [rbp+var_30]
0x180008537  call    Em_AmrNB_Dec_ReorderLsf
  ... truncated ...
```
