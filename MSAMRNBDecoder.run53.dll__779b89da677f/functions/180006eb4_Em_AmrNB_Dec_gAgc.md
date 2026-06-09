# Em_AmrNB_Dec_gAgc

- ea: `0x180006eb4`
- end: `0x180007131`
- name: `Em_AmrNB_Dec_gAgc`
- size: `637`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180003800`
- `0x180004dd0`

## callees

- `0x180006764`
- `0x1800067ac`
- `0x180006808`
- `0x18000688c`
- `0x18000694c`
- `0x18000698c`
- `0x180006e3c`
- `0x180006eb4`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_gAgc(__int64 a1, __int64 a2, __int64 a3, __int16 a4)
{
  __int64 v5; // r13
  __int16 v6; // bx
  __int16 v8; // bp
  int loop_gAgc; // eax
  __int16 v10; // r14
  unsigned int v11; // r8d
  int v12; // eax
  int v13; // edi
  int v14; // eax
  unsigned __int16 v15; // ax
  unsigned __int16 v16; // r14
  __int16 v17; // ax
  int v18; // eax
  int v19; // ecx
  char v20; // al
  int v21; // r9d
  int v22; // r9d
  int v23; // r8d
  int v24; // eax
  __int64 v25; // r8
  int v26; // eax
  __int16 v27; // r10
  int v28; // r8d
  __int64 v29; // rcx
  __int16 v30; // ax
  unsigned __int16 v31; // r9
  int v32; // r11d
  int v33; // r10d
  int v34; // edx
  int v35; // eax
  __int64 v36; // rcx
  int v37; // r9d
  int v38; // eax
  int v39; // eax

  v5 = a1;
  v6 = -a4;
  if ( a4 > 0 )
    v6 = a4;
  v8 = (unsigned __int16)a4 >> 15;
  loop_gAgc = Em_AmrNB_Dec_first_loop_gAgc(a3, (unsigned __int16)v6);
  if ( loop_gAgc > 0 )
  {
    v10 = Em_AmrNB_Dec_norm_l((unsigned int)loop_gAgc) - 1;
    v12 = Em_AmrNB_Dec_L_shl(v11, v10);
    v13 = v12 + 0x8000;
    if ( v12 >= 0 && (v12 ^ v13) < 0 )
      HIWORD(v13) = 0x7FFF;
    v14 = Em_AmrNB_Dec_first_loop_gAgc(a2, (unsigned __int16)v6);
    if ( v14 > 0 )
    {
      v16 = v10 - Em_AmrNB_Dec_norm_l((unsigned int)v14);
      v17 = Em_AmrNB_Dec_div_s(HIWORD(v13));
      v18 = Em_AmrNB_Dec_L_shr((unsigned int)(v17 << 7), v16);
      if ( v18 > 0 )
      {
        v20 = Em_AmrNB_Dec_norm_l((unsigned int)v18);
        v22 = v21 << v20;
        v23 = v22 >> 1;
        if ( ((30 - v20) & 1) != 0 )
          v23 = v22;
        v24 = v23 >> 9;
        v25 = (unsigned int)(v23 >> 10);
        LOWORD(v25) = v25 & 0x7FFF;
        v26 = Em_AmrNB_Dec_L_msu(
                (unsigned int)(Em_AmrNB_Dec_InvSqrtTable[(__int16)(HIWORD(v24) - 16)] << 16),
                (unsigned __int16)(Em_AmrNB_Dec_InvSqrtTable[(__int16)(HIWORD(v24) - 16)]
                                 - Em_AmrNB_Dec_InvSqrtTable[(__int16)(HIWORD(v24) - 16) + 1]),
                v25);
        v27 >>= 1;
        v28 = v26 >> (v27 + 1) << 9;
        v19 = v28 + 0x8000;
        if ( ((v26 >> (v27 + 1)) & 0x400000) == 0 && (v28 ^ v19) < 0 )
          HIWORD(v19) = 0x7FFF;
      }
      else
      {
        HIWORD(v19) = 0;
      }
      v15 = HIWORD(v19);
    }
    else
    {
      v15 = 0;
    }
    if ( v8 == 1 )
    {
      Em_AmrNB_Dec_mult(v15);
      v29 = *(unsigned __int16 *)(v5 + 466);
      if ( v6 > 0 )
      {
        do
        {
          v30 = Em_AmrNB_Dec_mult(v29);
          v29 = (unsigned int)(v33 + v30);
          if ( (int)v29 <= 0x7FFF )
          {
            if ( (int)v29 < v32 )
              v29 = (unsigned __int16)v32;
          }
          else
          {
            v29 = 0x7FFF;
          }
          v34 = (__int16)v29 * *(__int16 *)(a3 + 2LL * v31);
          v35 = 2 * v34;
          if ( v34 == 0x40000000 )
            v35 = 0x7FFFFFFF;
          *(_WORD *)(a3 + 2LL * v31) = v35 >> 13;
        }
        while ( (__int16)(v31 + 1) < v6 );
        v5 = a1;
      }
      *(_WORD *)(v5 + 466) = v29;
    }
    else
    {
      v36 = 0;
      if ( v6 > 0 )
      {
        v37 = (__int16)v15;
        do
        {
          v38 = v37 * *(__int16 *)(a3 + 2 * v36);
          if ( v38 == 0x40000000 )
            v39 = 0x7FFFFFFF;
          else
            v39 = 2 * v38;
          *(_WORD *)(a3 + 2 * v36) = v39 >> 13;
          v36 = (unsigned int)(v36 + 1);
        }
        while ( (int)v36 < v6 );
      }
    }
  }
  else if ( v8 == 1 )
  {
    *(_WORD *)(v5 + 466) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180006eb4  mov     [rsp+arg_0], rcx
0x180006eb9  push    rbx
0x180006eba  push    rbp
0x180006ebb  push    rsi
0x180006ebc  push    rdi
0x180006ebd  push    r12
0x180006ebf  push    r13
0x180006ec1  push    r14
0x180006ec3  push    r15
0x180006ec5  sub     rsp, 28h
0x180006ec9  movzx   ebx, r9w
0x180006ecd  movzx   ebp, r9w
0x180006ed1  mov     r12, rdx
0x180006ed4  mov     r13, rcx
0x180006ed7  neg     bx
0x180006eda  mov     rcx, r8
0x180006edd  mov     r15, r8
0x180006ee0  cmovs   bx, r9w
0x180006ee5  shr     bp, 0Fh
0x180006ee9  movzx   edx, bx
0x180006eec  call    Em_AmrNB_Dec_first_loop_gAgc
0x180006ef1  mov     r8d, eax
0x180006ef4  test    eax, eax
0x180006ef6  jg      short loc_180006F15
0x180006ef8  mov     esi, 1
0x180006efd  cmp     bp, si
0x180006f00  jnz     loc_18000711E
0x180006f06  xor     eax, eax
0x180006f08  mov     [r13+1D2h], ax
0x180006f10  jmp     loc_18000711E
0x180006f15  mov     ecx, r8d
0x180006f18  call    Em_AmrNB_Dec_norm_l
0x180006f1d  movzx   r14d, ax
0x180006f21  mov     esi, 1
0x180006f26  sub     r14w, si
0x180006f2a  mov     ecx, r8d
0x180006f2d  movzx   edx, r14w
0x180006f31  call    Em_AmrNB_Dec_L_shl
0x180006f36  mov     edx, 7FFFFFFFh
0x180006f3b  lea     edi, [rax+8000h]
0x180006f41  test    eax, eax
0x180006f43  js      short loc_180006F4C
0x180006f45  mov     ecx, edi
0x180006f47  xor     ecx, eax
0x180006f49  cmovl   edi, edx
0x180006f4c  movzx   edx, bx
0x180006f4f  mov     rcx, r12
0x180006f52  call    Em_AmrNB_Dec_first_loop_gAgc
0x180006f57  mov     r9d, eax
0x180006f5a  test    eax, eax
0x180006f5c  jg      short loc_180006F6B
0x180006f5e  xor     eax, eax
0x180006f60  mov     r12d, 7FFFFFFFh
0x180006f66  jmp     loc_180007053
0x180006f6b  mov     ecx, r9d
0x180006f6e  sar     edi, 10h
0x180006f71  call    Em_AmrNB_Dec_norm_l
0x180006f76  movzx   ecx, ax
0x180006f79  mov     r12d, 7FFFFFFFh
0x180006f7f  shl     r9d, cl
0x180006f82  lea     edx, [r9+8000h]
0x180006f89  test    r9d, r9d
0x180006f8c  js      short loc_180006F98
0x180006f8e  mov     r8d, edx
0x180006f91  xor     r8d, r9d
0x180006f94  cmovl   edx, r12d
0x180006f98  sub     r14w, cx
0x180006f9c  sar     edx, 10h
0x180006f9f  movzx   ecx, di
0x180006fa2  call    Em_AmrNB_Dec_div_s
0x180006fa7  movsx   ecx, ax
0x180006faa  movzx   edx, r14w
0x180006fae  shl     ecx, 7
0x180006fb1  call    Em_AmrNB_Dec_L_shr
0x180006fb6  mov     r9d, eax
0x180006fb9  test    eax, eax
0x180006fbb  jg      short loc_180006FC7
0x180006fbd  mov     ecx, 7E00h
0x180006fc2  jmp     loc_18000704D
0x180006fc7  mov     ecx, r9d
0x180006fca  call    Em_AmrNB_Dec_norm_l
0x180006fcf  movzx   ecx, ax
0x180006fd2  mov     edx, 7FFFh
0x180006fd7  shl     r9d, cl
0x180006fda  mov     r10d, 1Eh
0x180006fe0  sub     r10w, ax
0x180006fe4  mov     r8d, r9d
0x180006fe7  sar     r8d, 1
0x180006fea  test    sil, r10b
0x180006fed  cmovnz  r8d, r9d
0x180006ff1  sar     r8d, 9
0x180006ff5  mov     eax, r8d
0x180006ff8  sar     r8d, 1
0x180006ffb  sar     eax, 10h
0x180006ffe  and     r8w, dx
0x180007002  sub     ax, 10h
0x180007006  movsx   rcx, ax
0x18000700a  lea     rax, Em_AmrNB_Dec_InvSqrtTable
0x180007011  movzx   edx, word ptr [rax+rcx*2]
0x180007015  sub     dx, [rax+rcx*2+2]
0x18000701a  movsx   ecx, word ptr [rax+rcx*2]
0x18000701e  shl     ecx, 10h
0x180007021  call    Em_AmrNB_Dec_L_msu
0x180007026  sar     r10w, 1
0x18000702a  mov     r8d, eax
0x18000702d  lea     ecx, [rsi+r10]
0x180007031  sar     r8d, cl
0x180007034  shl     r8d, 9
0x180007038  lea     ecx, [r8+8000h]
0x18000703f  test    r8d, r8d
0x180007042  js      short loc_18000704D
0x180007044  mov     eax, ecx
0x180007046  xor     eax, r8d
0x180007049  cmovl   ecx, r12d
0x18000704d  sar     ecx, 10h
0x180007050  movzx   eax, cx
0x180007053  cmp     bp, si
0x180007056  jnz     loc_1800070EC
0x18000705c  mov     edx, 0CCCh
0x180007061  movzx   ecx, ax
0x180007064  call    Em_AmrNB_Dec_mult
0x180007069  movzx   ecx, word ptr [r13+1D2h]
0x180007071  xor     r9d, r9d
0x180007074  xor     edx, edx
0x180007076  cmp     dx, bx
0x180007079  jge     short loc_1800070E2
0x18000707b  movsx   r10d, ax
0x18000707f  mov     r11d, 0FFFF8000h
0x180007085  mov     r13d, 7FFFh
0x18000708b  mov     edx, 7333h
0x180007090  call    Em_AmrNB_Dec_mult
0x180007095  movsx   ecx, ax
0x180007098  add     ecx, r10d
0x18000709b  cmp     ecx, r13d
0x18000709e  jle     short loc_1800070A5
0x1800070a0  mov     ecx, r13d
0x1800070a3  jmp     short loc_1800070AE
0x1800070a5  cmp     ecx, r11d
0x1800070a8  jge     short loc_1800070AE
0x1800070aa  movzx   ecx, r11w
0x1800070ae  movsx   eax, cx
0x1800070b1  movzx   r8d, r9w
0x1800070b5  movsx   edx, word ptr [r15+r8*2]
0x1800070ba  imul    edx, eax
0x1800070bd  lea     eax, [rdx+rdx]
0x1800070c0  cmp     edx, 40000000h
0x1800070c6  jnz     short loc_1800070CB
0x1800070c8  mov     eax, r12d
0x1800070cb  sar     eax, 0Dh
0x1800070ce  add     r9w, si
0x1800070d2  mov     [r15+r8*2], ax
0x1800070d7  cmp     r9w, bx
0x1800070db  jl      short loc_18000708B
0x1800070dd  mov     r13, [rsp+68h+arg_0]
0x1800070e2  mov     [r13+1D2h], cx
0x1800070ea  jmp     short loc_18000711E
0x1800070ec  movsx   edx, bx
0x1800070ef  xor     ecx, ecx
0x1800070f1  test    edx, edx
0x1800070f3  jle     short loc_18000711E
0x1800070f5  movsx   r9d, ax
0x1800070f9  movsx   eax, word ptr [r15+rcx*2]
0x1800070fe  imul    eax, r9d
0x180007102  cmp     eax, 40000000h
0x180007107  jz      short loc_18000710D
0x180007109  add     eax, eax
0x18000710b  jmp     short loc_180007110
0x18000710d  mov     eax, r12d
0x180007110  sar     eax, 0Dh
0x180007113  mov     [r15+rcx*2], ax
0x180007118  add     ecx, esi
0x18000711a  cmp     ecx, edx
0x18000711c  jl      short loc_1800070F9
0x18000711e  xor     eax, eax
0x180007120  add     rsp, 28h
0x180007124  pop     r15
0x180007126  pop     r14
0x180007128  pop     r13
0x18000712a  pop     r12
0x18000712c  pop     rdi
0x18000712d  pop     rsi
0x18000712e  pop     rbp
0x18000712f  pop     rbx
0x180007130  retn
```
