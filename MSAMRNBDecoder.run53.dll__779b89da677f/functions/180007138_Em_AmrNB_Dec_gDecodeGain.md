# Em_AmrNB_Dec_gDecodeGain

- ea: `0x180007138`
- end: `0x1800079e7`
- name: `Em_AmrNB_Dec_gDecodeGain`
- size: `2223`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180003800`

## callees

- `0x180004afc`
- `0x180004bb4`
- `0x180004d24`
- `0x180006808`
- `0x18000694c`
- `0x180007138`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_gDecodeGain(_WORD *a1, __int64 a2)
{
  __int16 v4; // dx
  __int16 v5; // bp
  int v6; // ecx
  bool v7; // cc
  __int16 v8; // r8
  __int16 i; // r8
  __int64 v10; // r9
  int v11; // eax
  int v12; // r8d
  unsigned __int16 v13; // r9
  unsigned int v14; // r13d
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // eax
  _WORD *v19; // rdx
  int v20; // r9d
  __int64 v21; // r8
  __int64 v22; // rdx
  unsigned __int16 v23; // r13
  __int16 v24; // r12
  int v25; // r14d
  __int16 v26; // dx
  int v27; // eax
  unsigned int v28; // eax
  __int16 v29; // r11
  int v30; // r12d
  unsigned __int16 *v31; // rdx
  __int64 v32; // rcx
  unsigned __int16 *v33; // rax
  int v34; // r8d
  _WORD *v35; // rdx
  unsigned __int16 v36; // cx
  int v37; // r9d
  unsigned __int16 v38; // r8
  __int16 v39; // dx
  int v40; // r9d
  signed int v41; // eax
  int v42; // r14d
  __int64 v43; // rcx
  __int16 v44; // ax
  _WORD *v45; // rcx
  __int64 v46; // rdx
  __int16 v47; // ax
  int v48; // edx
  __int64 v49; // r8
  int v50; // edx
  int v51; // ecx
  int v52; // eax
  int v53; // eax
  int v54; // r12d
  __int64 v55; // rdx
  int v56; // ecx
  __int64 v57; // rdx
  __int16 v58; // ax
  __int16 v59; // ax
  __int64 v60; // rcx
  __int16 v61; // cx
  __int16 v62; // dx
  __int16 v63; // ax
  __int16 v65; // [rsp+70h] [rbp+8h]
  __int16 v67; // [rsp+80h] [rbp+18h]
  int v68; // [rsp+88h] [rbp+20h]
  unsigned int v69; // [rsp+88h] [rbp+20h]

  if ( *(_WORD *)(a2 + 1306) == 7 )
  {
    v4 = Em_AmrNB_Dec_qua_gain_pitch[*(unsigned __int16 *)(*(_QWORD *)(a2 + 1320) - 22LL)] & 0xFFFC;
    if ( a1[527] && v4 > (__int16)a1[529] )
      v4 = a1[529];
    v5 = 0x7FFF;
    v6 = 2 * v4;
    if ( v6 == (__int16)(2 * v4) )
      goto LABEL_11;
    v7 = v4 <= 0;
    goto LABEL_9;
  }
  v8 = a1[204];
  v4 = 0;
  v5 = 0x7FFF;
  v6 = 2 * v8;
  if ( v6 != (__int16)v6 )
  {
    v7 = v8 <= 0;
LABEL_9:
    LOWORD(v6) = 0x7FFF;
    if ( v7 )
      LOWORD(v6) = 0x8000;
  }
LABEL_11:
  for ( i = *(_WORD *)(a2 + 1296); i < 40; *(_WORD *)(a2 + 2 * v10 + 88) = v11 )
  {
    v10 = i;
    v11 = (__int16)(((__int16)v6 * *(__int16 *)(a2 + 2LL * (i - *(__int16 *)(a2 + 1296)) + 88)) >> 15)
        + *(__int16 *)(a2 + 2LL * i + 88);
    if ( v11 <= 0x7FFF )
    {
      if ( v11 < -32768 )
        LOWORD(v11) = 0x8000;
    }
    else
    {
      LOWORD(v11) = 0x7FFF;
    }
    ++i;
  }
  v12 = 0;
  v13 = 0;
  while ( 1 )
  {
    v14 = 0x7FFFFFFF;
    v15 = *(__int16 *)(a2 + 2LL * v13 + 88);
    v12 += 2 * v15 * v15;
    if ( v12 < 0 )
      break;
    if ( (__int16)++v13 >= 40 )
      goto LABEL_22;
  }
  v12 = 0x7FFFFFFF;
LABEL_22:
  if ( *(_WORD *)(a2 + 1306) == 7 )
  {
    v16 = v12 + 0x8000;
    *(_WORD *)(a2 + 1302) = v4;
    if ( (v12 ^ (v12 + 0x8000)) < 0 )
      HIWORD(v16) = 0x7FFF;
    v17 = 26214 * SHIWORD(v16);
    if ( v17 != 0x40000000 )
      v14 = 2 * v17;
    v18 = Em_AmrNB_Dec_gLog2(v14);
    v19 = *(_WORD **)(a2 + 1320);
    v20 = 74 * (__int16)a1[217] + 44 * ((__int16)a1[218] + 2 * (__int16)a1[216]) + 24 * (__int16)a1[219] - v18 + 2749821;
    v21 = (unsigned __int16)(3 * *v19);
    *(_QWORD *)(a2 + 1320) = v19 + 1;
    v22 = (unsigned int)(v20 >> 2);
    LOWORD(v22) = v22 & 0x7FFF;
    v23 = Em_AmrNB_Dec_qua_gain_code[v21];
    v24 = Em_AmrNB_Dec_qua_gain_code[(unsigned __int16)(v21 + 1)];
    LOWORD(v25) = Em_AmrNB_Dec_qua_gain_code[(unsigned __int16)(v21 + 2)];
    Em_AmrNB_Dec_gPow2((unsigned __int16)(v20 >> 17), v22);
    v26 = Em_AmrNB_Dec_mult(v23);
    v27 = 2 * v26;
    if ( v27 != (__int16)v27 )
    {
      LOWORD(v27) = 0x7FFF;
      if ( v26 <= 0 )
        LOWORD(v27) = 0x8000;
    }
    goto LABEL_60;
  }
  v28 = Em_AmrNB_Dec_gLog2((unsigned int)v12);
  v68 = Em_AmrNB_Dec_Mpy_32_16(v28, 40876);
  v30 = v68;
  switch ( v29 )
  {
    case 5:
      v31 = *(unsigned __int16 **)(a2 + 1320);
      v69 = 9;
      v32 = *v31;
      v33 = v31 + 1;
      *(_QWORD *)(a2 + 1320) = v31 + 1;
      *(_WORD *)(a2 + 1302) = Em_AmrNB_Dec_qua_gain_pitch[v32];
      LOWORD(v31) = v31[1];
      *(_QWORD *)(a2 + 1320) = v33 + 1;
      LOWORD(v31) = 3 * (_WORD)v31;
      v65 = Em_AmrNB_Dec_qua_gain_code[(unsigned __int16)v31];
      v34 = 2183936;
      v67 = Em_AmrNB_Dec_qua_gain_code[(unsigned __int16)((_WORD)v31 + 1)];
      LOWORD(v25) = Em_AmrNB_Dec_qua_gain_code[(unsigned __int16)((_WORD)v31 + 2)];
      goto LABEL_53;
    case 6:
      v34 = 2134784;
      break;
    case 4:
      v34 = 2085632;
      break;
    case 3:
      v34 = 2065152;
      break;
    default:
      v35 = *(_WORD **)(a2 + 1320);
      if ( v29 )
      {
        v43 = (unsigned __int16)(4 * *v35);
        *(_QWORD *)(a2 + 1320) = v35 + 1;
        v44 = Em_AmrNB_Dec_GainTableForLowRates[v43];
        LOWORD(v43) = v43 + 1;
        *(_WORD *)(a2 + 1302) = v44;
        v65 = Em_AmrNB_Dec_GainTableForLowRates[(unsigned __int16)v43];
        v67 = Em_AmrNB_Dec_GainTableForLowRates[(unsigned __int16)(v43 + 1)];
        LOWORD(v25) = Em_AmrNB_Dec_GainTableForLowRates[(unsigned __int16)(v43 + 2)];
      }
      else
      {
        if ( (*(_WORD *)(a2 + 1308) & 1) != 0 )
        {
          v36 = 2 * ((*(_WORD *)(a2 + 1308) & 1) + 2 * *(v35 - 4));
        }
        else
        {
          v36 = 4 * *v35;
          *(_QWORD *)(a2 + 1320) = v35 + 1;
        }
        *(_WORD *)(a2 + 1302) = Em_AmrNB_Dec_table_gain_MR475[v36];
        v65 = word_180017BA2[v36];
        v37 = Em_AmrNB_Dec_gLog2((unsigned int)v65);
        v38 = (v37 >> 1) & 0x7FFF;
        v39 = v38 >> 5;
        if ( ((v37 >> 1) & 0x10) != 0 )
          ++v39;
        v40 = v37 >> 16;
        v67 = v39 + (((_WORD)v40 - 12) << 10);
        v41 = (unsigned int)Em_AmrNB_Dec_Mpy_32_16(2 * ((unsigned int)v38 + (((__int16)v40 - 12) << 15)), 24660) << 13;
        v42 = v41 + 0x8000;
        if ( v41 >= 0 && (v41 ^ v42) < 0 )
          v42 = 0x7FFFFFFF;
        v30 = v68;
        v25 = v42 >> 16;
      }
      v34 = 2134784;
      goto LABEL_52;
  }
  v45 = *(_WORD **)(a2 + 1320);
  v46 = (unsigned __int16)(4 * *v45);
  *(_QWORD *)(a2 + 1320) = v45 + 1;
  v47 = Em_AmrNB_Dec_GainTableForHighRates[v46];
  LOWORD(v46) = v46 + 1;
  *(_WORD *)(a2 + 1302) = v47;
  v65 = Em_AmrNB_Dec_GainTableForHighRates[(unsigned __int16)v46];
  v67 = Em_AmrNB_Dec_GainTableForHighRates[(unsigned __int16)(v46 + 1)];
  LOWORD(v25) = Em_AmrNB_Dec_GainTableForHighRates[(unsigned __int16)(v46 + 2)];
LABEL_52:
  v69 = 10;
LABEL_53:
  v48 = v30 + v34;
  v49 = 0;
  v50 = v48 << 9;
  do
  {
    v51 = (__int16)a1[v49 + 212];
    v52 = Em_AmrNB_Dec_PredCoeffs[v49++];
    v50 += v52 * v51;
  }
  while ( v49 != 4 );
  v53 = 10878;
  if ( v29 != 4 )
    v53 = 10886;
  v54 = v53 * (__int16)(v50 >> 15);
  v55 = (unsigned int)(v54 >> 9);
  LOWORD(v55) = v55 & 0x7FFF;
  v56 = v65 * (__int16)Em_AmrNB_Dec_gPow2(14, v55);
  if ( v56 != 0x40000000 )
    v14 = 2 * v56;
  v57 = v69;
  LOWORD(v57) = v69 - (v54 >> 24);
  v24 = v67;
  v27 = (int)Em_AmrNB_Dec_L_shr(v14, v57) >> 16;
LABEL_60:
  *(_WORD *)(a2 + 1304) = v27;
  a1[215] = a1[214];
  a1[214] = a1[213];
  a1[213] = a1[212];
  a1[212] = v25;
  a1[219] = a1[218];
  a1[218] = a1[217];
  a1[217] = a1[216];
  a1[216] = v24;
  if ( a1[527] )
  {
    v58 = a1[529];
    if ( *(__int16 *)(a2 + 1302) > v58 )
      *(_WORD *)(a2 + 1302) = v58;
    v59 = a1[530];
    if ( *(__int16 *)(a2 + 1304) > v59 )
      *(_WORD *)(a2 + 1304) = v59;
  }
  v60 = 0;
  a1[530] = *(_WORD *)(a2 + 1304);
  a1[529] = *(_WORD *)(a2 + 1302);
  do
  {
    a1[v60 + 539] = a1[v60 + 540];
    a1[v60 + 534] = a1[v60 + 535];
    ++v60;
  }
  while ( v60 != 4 );
  v61 = 13017;
  a1[543] = *(_WORD *)(a2 + 1302);
  a1[538] = *(_WORD *)(a2 + 1304);
  a1[220] = a1[221];
  a1[221] = a1[222];
  a1[222] = a1[223];
  a1[223] = a1[224];
  a1[224] = a1[225];
  a1[225] = a1[226];
  a1[226] = a1[227];
  a1[227] = a1[228];
  a1[228] = *(_WORD *)(a2 + 1302);
  a1[205] = a1[206];
  a1[206] = a1[207];
  a1[207] = a1[208];
  a1[208] = a1[209];
  a1[209] = a1[210];
  a1[210] = a1[211];
  a1[211] = *(_WORD *)(a2 + 1304);
  if ( *(_WORD *)(a2 + 1306) || (*(_BYTE *)(a2 + 1308) & 1) != 0 )
  {
    a1[204] = *(_WORD *)(a2 + 1302);
    if ( *(__int16 *)(a2 + 1302) > 13017 )
      a1[204] = 13017;
  }
  v62 = *(_WORD *)(a2 + 1306);
  v63 = *(_WORD *)(a2 + 1302);
  *(_WORD *)(a2 + 1300) = v63;
  if ( v62 == 7 )
  {
    v61 = v63;
  }
  else
  {
    if ( v63 <= 13017 )
      v61 = v63;
    else
      *(_WORD *)(a2 + 1300) = 13017;
    if ( v62 == 6 && (__int16)a1[313] > 45 )
      v61 >>= 2;
  }
  if ( 2 * v61 == (__int16)(2 * v61) )
  {
    v5 = 2 * v61;
  }
  else if ( v61 <= 0 )
  {
    v5 = 0x8000;
  }
  *(_WORD *)(a2 + 1300) = v5;
  return 0;
}

```

## disassembly

```asm
0x180007138  mov     [rsp+arg_8], rdx
0x18000713d  push    rbx
0x18000713e  push    rbp
0x18000713f  push    rsi
0x180007140  push    rdi
0x180007141  push    r12
0x180007143  push    r13
0x180007145  push    r14
0x180007147  push    r15
0x180007149  sub     rsp, 28h
0x18000714d  xor     esi, esi
0x18000714f  lea     r12, cs:180000000h
0x180007156  cmp     word ptr [rdx+51Ah], 7
0x18000715e  mov     rbx, rdx
0x180007161  mov     rdi, rcx
0x180007164  jnz     short loc_1800071B2
0x180007166  mov     rax, [rdx+528h]
0x18000716d  movzx   r8d, word ptr [rax-16h]
0x180007172  movzx   edx, ds:rva Em_AmrNB_Dec_qua_gain_pitch[r12+r8*2]
0x18000717b  and     dx, 0FFFCh
0x18000717f  cmp     [rcx+41Eh], si
0x180007186  jz      short loc_180007196
0x180007188  movzx   eax, word ptr [rcx+422h]
0x18000718f  cmp     dx, ax
0x180007192  cmovg   dx, ax
0x180007196  movsx   ecx, dx
0x180007199  mov     ebp, 7FFFh
0x18000719e  add     ecx, ecx
0x1800071a0  mov     r15d, 0FFFF8000h
0x1800071a6  movsx   eax, cx
0x1800071a9  cmp     ecx, eax
0x1800071ab  jz      short loc_1800071DE
0x1800071ad  test    dx, dx
0x1800071b0  jmp     short loc_1800071D7
0x1800071b2  movsx   r8d, word ptr [rcx+198h]
0x1800071ba  mov     edx, esi
0x1800071bc  mov     ecx, r8d
0x1800071bf  mov     ebp, 7FFFh
0x1800071c4  add     ecx, ecx
0x1800071c6  mov     r15d, 0FFFF8000h
0x1800071cc  movsx   eax, cx
0x1800071cf  cmp     ecx, eax
0x1800071d1  jz      short loc_1800071DE
0x1800071d3  test    r8w, r8w
0x1800071d7  mov     ecx, ebp
0x1800071d9  cmovle  cx, r15w
0x1800071de  movzx   r8d, word ptr [rbx+510h]
0x1800071e6  mov     r14d, 1
0x1800071ec  cmp     r8w, 28h ; '('
0x1800071f1  jge     short loc_180007244
0x1800071f3  movsx   r10d, cx
0x1800071f7  movsx   eax, word ptr [rbx+510h]
0x1800071fe  movsx   ecx, r8w
0x180007202  sub     ecx, eax
0x180007204  movsx   r9, r8w
0x180007208  movsxd  rax, ecx
0x18000720b  movsx   ecx, word ptr [rbx+rax*2+58h]
0x180007210  movsx   eax, word ptr [rbx+r9*2+58h]
0x180007216  imul    ecx, r10d
0x18000721a  sar     ecx, 0Fh
0x18000721d  movsx   ecx, cx
0x180007220  add     eax, ecx
0x180007222  cmp     eax, ebp
0x180007224  jle     short loc_18000722B
0x180007226  movzx   eax, bp
0x180007229  jmp     short loc_180007233
0x18000722b  cmp     eax, r15d
0x18000722e  jge     short loc_180007233
0x180007230  mov     eax, r15d
0x180007233  add     r8w, r14w
0x180007237  mov     [rbx+r9*2+58h], ax
0x18000723d  cmp     r8w, 28h ; '('
0x180007242  jl      short loc_1800071F7
0x180007244  mov     r8d, esi
0x180007247  movzx   r9d, si
0x18000724b  movzx   eax, r9w
0x18000724f  mov     r13d, 7FFFFFFFh
0x180007255  movsx   ecx, word ptr [rbx+rax*2+58h]
0x18000725a  imul    ecx, ecx
0x18000725d  lea     r8d, [r8+rcx*2]
0x180007261  test    r8d, r8d
0x180007264  js      short loc_180007273
0x180007266  add     r9w, r14w
0x18000726a  cmp     r9w, 28h ; '('
0x18000726f  jl      short loc_18000724B
0x180007271  jmp     short loc_180007276
0x180007273  mov     r8d, r13d
0x180007276  movzx   r11d, word ptr [rbx+51Ah]
0x18000727e  cmp     r11w, 7
0x180007283  jnz     loc_1800073A4
0x180007289  lea     ecx, [r8+8000h]
0x180007290  mov     [rbx+516h], dx
0x180007297  mov     eax, ecx
0x180007299  xor     eax, r8d
0x18000729c  cmovl   ecx, r13d
0x1800072a0  sar     ecx, 10h
0x1800072a3  movsx   eax, cx
0x1800072a6  imul    ecx, eax, 6666h
0x1800072ac  cmp     ecx, 40000000h
0x1800072b2  jz      short loc_1800072B8
0x1800072b4  lea     r13d, [rcx+rcx]
0x1800072b8  mov     ecx, r13d
0x1800072bb  call    Em_AmrNB_Dec_gLog2
0x1800072c0  movsx   edx, word ptr [rdi+1B0h]
0x1800072c7  movsx   ecx, word ptr [rdi+1B4h]
0x1800072ce  lea     edx, [rcx+rdx*2]
0x1800072d1  movsx   ecx, word ptr [rdi+1B2h]
0x1800072d8  imul    r8d, edx, 2Ch ; ','
0x1800072dc  imul    edx, ecx, 4Ah ; 'J'
0x1800072df  movsx   ecx, word ptr [rdi+1B6h]
0x1800072e6  add     r8d, edx
0x1800072e9  lea     edx, [rcx+rcx*2]
0x1800072ec  lea     r9d, [r8+rdx*8]
0x1800072f0  mov     rdx, [rbx+528h]
0x1800072f7  sub     r9d, eax
0x1800072fa  add     r9d, 29F57Dh
0x180007301  movzx   ecx, word ptr [rdx]
0x180007304  movzx   eax, cx
0x180007307  add     ax, ax
0x18000730a  add     cx, ax
0x18000730d  lea     rax, [rdx+2]
0x180007311  movzx   r8d, cx
0x180007315  mov     edx, r9d
0x180007318  mov     [rbx+528h], rax
0x18000731f  sar     edx, 2
0x180007322  sar     r9d, 11h
0x180007326  and     dx, bp
0x180007329  movzx   r13d, ds:rva Em_AmrNB_Dec_qua_gain_code[r12+r8*2]
0x180007332  movzx   ecx, r9w
0x180007336  add     r8w, r14w
0x18000733a  movzx   eax, r8w
0x18000733e  lea     r8, cs:180000000h
0x180007345  movzx   r12d, ds:rva Em_AmrNB_Dec_qua_gain_code[r12+rax*2]
0x18000734e  add     ax, r14w
0x180007352  movzx   eax, ax
0x180007355  movzx   r14d, ds:rva Em_AmrNB_Dec_qua_gain_code[r8+rax*2]
0x18000735e  call    Em_AmrNB_Dec_gPow2
0x180007363  movsx   edx, ax
0x180007366  shl     edx, 4
0x180007369  movsx   ecx, dx
0x18000736c  cmp     edx, ecx
0x18000736e  jz      short loc_18000737A
0x180007370  test    ax, ax
0x180007373  mov     edx, ebp
0x180007375  cmovle  dx, r15w
0x18000737a  movzx   ecx, r13w
0x18000737e  call    Em_AmrNB_Dec_mult
0x180007383  movsx   edx, ax
0x180007386  mov     eax, edx
0x180007388  add     eax, eax
0x18000738a  movsx   ecx, ax
0x18000738d  cmp     eax, ecx
0x18000738f  jz      loc_180007749
0x180007395  test    dx, dx
0x180007398  mov     eax, ebp
0x18000739a  cmovle  ax, r15w
0x18000739f  jmp     loc_180007749
0x1800073a4  mov     ecx, r8d
0x1800073a7  mov     r14d, 0FFFF9FACh
0x1800073ad  call    Em_AmrNB_Dec_gLog2
0x1800073b2  mov     ecx, eax
0x1800073b4  movzx   edx, r14w
0x1800073b8  call    Em_AmrNB_Dec_Mpy_32_16
0x1800073bd  mov     [rsp+68h+arg_18], eax
0x1800073c4  mov     r12d, eax
0x1800073c7  cmp     r11w, 5
0x1800073cc  jnz     loc_180007472
0x1800073d2  mov     rdx, [rbx+528h]
0x1800073d9  lea     r8, cs:180000000h
0x1800073e0  mov     [rsp+68h+arg_18], 9
0x1800073eb  movzx   ecx, word ptr [rdx]
0x1800073ee  lea     rax, [rdx+2]
0x1800073f2  mov     [rbx+528h], rax
0x1800073f9  movzx   ecx, ds:rva Em_AmrNB_Dec_qua_gain_pitch[r8+rcx*2]
0x180007402  mov     [rbx+516h], cx
0x180007409  movzx   edx, word ptr [rax]
0x18000740c  add     rax, 2
0x180007410  movzx   ecx, dx
0x180007413  mov     [rbx+528h], rax
0x18000741a  add     cx, cx
0x18000741d  add     dx, cx
0x180007420  movzx   ecx, dx
0x180007423  movzx   r10d, ds:rva Em_AmrNB_Dec_qua_gain_code[r8+rcx*2]
0x18000742c  mov     [rsp+68h+arg_0], r10w
0x180007432  mov     r10d, 1
0x180007438  add     cx, r10w
0x18000743c  movzx   eax, cx
0x18000743f  movzx   r9d, ds:rva Em_AmrNB_Dec_qua_gain_code[r8+rax*2]
0x180007448  add     ax, r10w
0x18000744c  movzx   eax, ax
0x18000744f  mov     r8d, 215300h
0x180007455  mov     [rsp+68h+arg_10], r9d
0x18000745d  lea     r9, cs:180000000h
0x180007464  movzx   r14d, ds:rva Em_AmrNB_Dec_qua_gain_code[r9+rax*2]
0x18000746d  jmp     loc_1800076B7
0x180007472  cmp     r11w, 6
0x180007477  jz      loc_180007630
0x18000747d  mov     edx, 4
0x180007482  cmp     r11w, dx
0x180007486  jz      loc_180007628
0x18000748c  cmp     r11w, 3
0x180007491  jz      loc_180007620
0x180007497  mov     rdx, [rbx+528h]
0x18000749e  test    r11w, r11w
0x1800074a2  jnz     loc_1800075A7
0x1800074a8  movzx   eax, word ptr [rbx+51Ch]
0x1800074af  mov     r14d, 1
0x1800074b5  test    r14b, al
0x1800074b8  jnz     short loc_1800074CE
0x1800074ba  movzx   ecx, word ptr [rdx]
0x1800074bd  lea     rax, [rdx+2]
0x1800074c1  shl     cx, 2
0x1800074c5  mov     [rbx+528h], rax
0x1800074cc  jmp     short loc_1800074DF
0x1800074ce  movzx   ecx, word ptr [rdx-8]
0x1800074d2  and     ax, r14w
0x1800074d6  add     cx, cx
0x1800074d9  add     cx, ax
0x1800074dc  add     cx, cx
0x1800074df  movzx   ecx, cx
0x1800074e2  lea     r8, cs:180000000h
0x1800074e9  movzx   eax, ds:rva Em_AmrNB_Dec_table_gain_MR475[r8+rcx*2]
0x1800074f2  mov     [rbx+516h], ax
0x1800074f9  movsx   eax, ds:rva word_180017BA2[r8+rcx*2]
0x180007502  mov     ecx, eax
0x180007504  mov     [rsp+68h+arg_0], ax
0x180007509  call    Em_AmrNB_Dec_gLog2
0x18000750e  mov     r8d, eax
0x180007511  mov     r9d, eax
0x180007514  sar     r8d, 1
0x180007517  and     r8w, bp
0x18000751b  movzx   edx, r8w
0x18000751f  shr     dx, 5
0x180007523  test    r8b, 10h
0x180007527  jz      short loc_18000752D
0x180007529  add     dx, r14w
0x18000752d  sar     r9d, 10h
0x180007531  mov     r10d, 0Ch
0x180007537  movzx   ecx, r9w
0x18000753b  mov     eax, 400h
0x180007540  sub     cx, r10w
0x180007544  cwde
0x180007545  movsx   r12d, cx
0x180007549  imul    r12d, eax
0x18000754d  movsx   ecx, r9w
0x180007551  sub     ecx, r10d
0x180007554  movzx   eax, r8w
0x180007558  shl     ecx, 0Fh
0x18000755b  add     ecx, eax
0x18000755d  add     r12w, dx
0x180007561  add     ecx, ecx
0x180007563  mov     edx, 6054h
0x180007568  mov     [rsp+68h+arg_10], r12d
0x180007570  call    Em_AmrNB_Dec_Mpy_32_16
0x180007575  shl     eax, 0Dh
0x180007578  lea     r14d, [rax+8000h]
0x18000757f  test    eax, eax
0x180007581  js      short loc_18000758C
0x180007583  mov     ecx, r14d
0x180007586  xor     ecx, eax
0x180007588  cmovl   r14d, r13d
0x18000758c  mov     r12d, [rsp+68h+arg_18]
0x180007594  lea     r9, cs:180000000h
0x18000759b  sar     r14d, 10h
0x18000759f  mov     r10d, 1
0x1800075a5  jmp     short loc_180007615
0x1800075a7  movzx   eax, word ptr [rdx]
0x1800075aa  lea     r9, cs:180000000h
0x1800075b1  shl     ax, 2
0x1800075b5  mov     r10d, 1
0x1800075bb  movzx   ecx, ax
0x1800075be  lea     rax, [rdx+2]
0x1800075c2  mov     [rbx+528h], rax
0x1800075c9  movzx   eax, ds:rva Em_AmrNB_Dec_GainTableForLowRates[r9+rcx*2]
0x1800075d2  add     cx, r10w
0x1800075d6  mov     [rbx+516h], ax
0x1800075dd  movzx   edx, cx
0x1800075e0  movzx   eax, ds:rva Em_AmrNB_Dec_GainTableForLowRates[r9+rdx*2]
0x1800075e9  add     dx, r10w
0x1800075ed  mov     [rsp+68h+arg_0], ax
0x1800075f2  movzx   eax, dx
0x1800075f5  add     dx, r10w
0x1800075f9  movzx   eax, ds:rva Em_AmrNB_Dec_GainTableForLowRates[r9+rax*2]
0x180007602  mov     [rsp+68h+arg_10], eax
0x180007609  movzx   eax, dx
0x18000760c  movzx   r14d, ds:rva Em_AmrNB_Dec_GainTableForLowRates[r9+rax*2]
0x180007615  mov     r8d, 209300h
0x18000761b  jmp     loc_1800076AB
0x180007620  mov     r8d, 1F8300h
0x180007626  jmp     short loc_180007636
0x180007628  mov     r8d, 1FD300h
0x18000762e  jmp     short loc_180007636
0x180007630  mov     r8d, 209300h
0x180007636  mov     rcx, [rbx+528h]
0x18000763d  lea     r9, cs:180000000h
0x180007644  mov     r10d, 1
0x18000764a  movzx   eax, word ptr [rcx]
0x18000764d  shl     ax, 2
0x180007651  movzx   edx, ax
0x180007654  lea     rax, [rcx+2]
  ... truncated ...
```
