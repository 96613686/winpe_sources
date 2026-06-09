# LibRaw::copy_mem_image(void *,int,int)

- ea: `0x180007250`
- end: `0x1800076f0`
- name: `?copy_mem_image@LibRaw@@QEAAHPEAXHH@Z`
- size: `1184`
- prototype: `__int64 __fastcall(LibRaw *__hidden this, void *, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007710`

## callees

- `0x180007250`
- `0x1800269c0`
- `0x180028f50`

## pseudocode

```c
__int64 __fastcall LibRaw::copy_mem_image(LibRaw *this, char *a2, int a3, int a4)
{
  __int64 v6; // r11
  unsigned __int16 *v7; // rbp
  unsigned __int16 *v8; // r13
  int v9; // r9d
  int v10; // ecx
  int v11; // r10d
  int v12; // eax
  _DWORD *v13; // r11
  __int64 v14; // rbx
  __int64 v15; // rdx
  int v16; // ecx
  int v17; // r8d
  _DWORD *v18; // rax
  bool v19; // zf
  _WORD *v20; // r14
  _WORD *v21; // r15
  unsigned __int16 v22; // cx
  unsigned __int16 v23; // dx
  int v24; // esi
  int v25; // r12d
  int v26; // ebx
  int v27; // r15d
  int v28; // eax
  int v29; // r11d
  unsigned __int16 v30; // cx
  char *v31; // rdx
  __int64 v32; // r10
  int v33; // eax
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 v36; // r10
  int v37; // eax
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // r10
  int v41; // r9d
  __int64 v42; // r8
  __int64 v43; // r10
  int v44; // r9d
  __int64 v45; // r8
  __int16 v46; // [rsp+30h] [rbp-58h]
  unsigned __int16 v47; // [rsp+32h] [rbp-56h]
  unsigned __int16 v48; // [rsp+34h] [rbp-54h]
  int v49; // [rsp+38h] [rbp-50h]
  int v50; // [rsp+3Ch] [rbp-4Ch]
  __int16 v51; // [rsp+90h] [rbp+8h]

  if ( (*((_DWORD *)this + 1346) & 0xFFFFFFFu) < 0x400 )
    return 4294967292LL;
  v6 = *((_QWORD *)this + 47669);
  v7 = (unsigned __int16 *)((char *)this + 22);
  if ( v6 )
  {
    v8 = (unsigned __int16 *)((char *)this + 20);
    v9 = 0x2000;
    v10 = (int)(float)((float)(*v7 * *((unsigned __int16 *)this + 10)) * *((float *)this + 1320));
    v11 = v10 / 2;
    if ( !*((_WORD *)this + 190675) )
      v11 = v10;
    if ( (*((_DWORD *)this + 1294) & 0xFFFFFFFD) == 0 )
    {
      v8 = (unsigned __int16 *)((char *)this + 20);
      if ( !*((_DWORD *)this + 1322) )
      {
        v12 = *((_DWORD *)this + 135);
        v8 = (unsigned __int16 *)((char *)this + 20);
        v9 = 0;
        if ( v12 > 0 )
        {
          v13 = (_DWORD *)(v6 + 32764);
          v14 = (unsigned int)v12;
          do
          {
            v15 = 0x1FFF;
            v16 = 0;
            v17 = 0x1FFF;
            v18 = v13;
            do
            {
              v16 += *v18;
              if ( v16 > v11 )
                break;
              --v17;
              --v15;
              --v18;
            }
            while ( v15 > 32 );
            if ( v9 < v17 )
              v9 = v17;
            v13 += 0x2000;
            --v14;
          }
          while ( v14 );
          v8 = (unsigned __int16 *)((char *)this + 20);
        }
      }
    }
    LibRaw::gamma_curve(
      this,
      *((double *)this + 637),
      *((double *)this + 638),
      2,
      (int)(float)((float)(8 * v9) / *((float *)this + 1290)));
  }
  else
  {
    v8 = (unsigned __int16 *)((char *)this + 20);
  }
  v19 = (*((_BYTE *)this + 48) & 4) == 0;
  v20 = (_WORD *)((char *)this + 28);
  v21 = (_WORD *)((char *)this + 30);
  v22 = *v7;
  v23 = *v8;
  v51 = *((_WORD *)this + 14);
  v46 = *((_WORD *)this + 15);
  v47 = v22;
  v48 = *v8;
  *((_WORD *)this + 14) = *v8;
  *((_WORD *)this + 15) = v22;
  if ( !v19 )
  {
    *v7 = v23;
    *v8 = v22;
  }
  v24 = LibRaw::flip_index(this, 0, 0);
  v25 = LibRaw::flip_index(this, 0, 1) - v24;
  v26 = LibRaw::flip_index(this, 0, *v7);
  v50 = LibRaw::flip_index(this, 1, 0) - v26;
  v49 = 0;
  if ( *v8 )
  {
    v27 = 0;
    do
    {
      v28 = *((_DWORD *)this + 1308);
      v29 = 0;
      v30 = *v7;
      v31 = &a2[v27];
      if ( a4 )
      {
        if ( v28 == 8 )
        {
          if ( v30 )
          {
            v32 = 4LL * v24;
            do
            {
              v33 = *((_DWORD *)this + 135) - 1;
              v34 = v33;
              if ( v33 >= 0 )
              {
                v35 = 2 * (v32 + v33);
                do
                {
                  v35 -= 2;
                  *v31++ = *((_BYTE *)this + 2 * *(unsigned __int16 *)(*((_QWORD *)this + 1) + v35 + 2) + 5393);
                  --v34;
                }
                while ( v34 >= 0 );
              }
              ++v29;
              v24 += v25;
              v32 += 4LL * v25;
            }
            while ( v29 < *v7 );
          }
        }
        else if ( v30 )
        {
          v36 = 4LL * v24;
          do
          {
            v37 = *((_DWORD *)this + 135) - 1;
            v38 = v37;
            if ( v37 >= 0 )
            {
              v39 = 2 * (v36 + v37);
              do
              {
                v39 -= 2;
                *(_WORD *)v31 = *((_WORD *)this + *(unsigned __int16 *)(*((_QWORD *)this + 1) + v39 + 2) + 2696);
                v31 += 2;
                --v38;
              }
              while ( v38 >= 0 );
            }
            ++v29;
            v24 += v25;
            v36 += 4LL * v25;
          }
          while ( v29 < *v7 );
        }
      }
      else if ( v28 == 8 )
      {
        if ( v30 )
        {
          v40 = 8LL * v24;
          do
          {
            v41 = 0;
            if ( *((int *)this + 135) > 0 )
            {
              v42 = v40;
              do
              {
                v42 += 2;
                ++v41;
                *v31++ = *((_BYTE *)this + 2 * *(unsigned __int16 *)(*((_QWORD *)this + 1) + v42 - 2) + 5393);
              }
              while ( v41 < *((_DWORD *)this + 135) );
            }
            ++v29;
            v24 += v25;
            v40 += 8LL * v25;
          }
          while ( v29 < *v7 );
        }
      }
      else if ( v30 )
      {
        v43 = 8LL * v24;
        do
        {
          v44 = 0;
          if ( *((int *)this + 135) > 0 )
          {
            v45 = v43;
            do
            {
              v45 += 2;
              ++v44;
              *(_WORD *)v31 = *((_WORD *)this + *(unsigned __int16 *)(*((_QWORD *)this + 1) + v45 - 2) + 2696);
              v31 += 2;
            }
            while ( v44 < *((_DWORD *)this + 135) );
          }
          ++v29;
          v24 += v25;
          v43 += 8LL * v25;
        }
        while ( v29 < *v7 );
      }
      v27 += a3;
      v24 += v50;
      ++v49;
    }
    while ( v49 < *v8 );
    v20 = (_WORD *)((char *)this + 28);
    v21 = (_WORD *)((char *)this + 30);
    v7 = (unsigned __int16 *)((char *)this + 22);
    v8 = (unsigned __int16 *)((char *)this + 20);
  }
  *v20 = v51;
  *v21 = v46;
  *v7 = v47;
  *v8 = v48;
  return 0;
}

```

## disassembly

```asm
0x180007250  mov     [rsp+arg_18], r9d
0x180007255  mov     [rsp+arg_10], r8d
0x18000725a  mov     [rsp+arg_8], rdx
0x18000725f  push    rdi
0x180007260  sub     rsp, 80h
0x180007267  mov     eax, [rcx+1508h]
0x18000726d  mov     rdi, rcx
0x180007270  and     eax, 0FFFFFFFh
0x180007275  cmp     eax, 400h
0x18000727a  jnb     short loc_18000728A
0x18000727c  mov     eax, 0FFFFFFFCh
0x180007281  add     rsp, 80h
0x180007288  pop     rdi
0x180007289  retn
0x18000728a  mov     r11, [rcx+5D1A8h]
0x180007291  mov     [rsp+88h+var_10], rbx
0x180007296  mov     [rsp+88h+var_18], rbp
0x18000729b  lea     rbp, [rcx+16h]
0x18000729f  mov     [rsp+88h+var_20], rsi
0x1800072a4  mov     [rsp+88h+var_28], r12
0x1800072a9  mov     [rsp+88h+var_30], r13
0x1800072ae  mov     [rsp+88h+var_38], r14
0x1800072b3  mov     [rsp+88h+var_40], r15
0x1800072b8  test    r11, r11
0x1800072bb  jz      loc_1800073BE
0x1800072c1  movzx   ecx, word ptr [rcx+14h]
0x1800072c5  lea     r13, [rdi+14h]
0x1800072c9  movzx   eax, word ptr [rbp+0]
0x1800072cd  mov     r9d, 2000h
0x1800072d3  imul    ecx, eax
0x1800072d6  movd    xmm0, ecx
0x1800072da  cvtdq2ps xmm0, xmm0
0x1800072dd  mulss   xmm0, dword ptr [rdi+14A0h]
0x1800072e5  cvttss2si ecx, xmm0
0x1800072e9  mov     eax, ecx
0x1800072eb  cdq
0x1800072ec  sub     eax, edx
0x1800072ee  sar     eax, 1
0x1800072f0  cmp     word ptr [rdi+5D1A6h], 0
0x1800072f8  mov     r10d, eax
0x1800072fb  cmovz   r10d, ecx
0x1800072ff  test    dword ptr [rdi+1438h], 0FFFFFFFDh
0x180007309  jnz     short loc_18000737F
0x18000730b  cmp     dword ptr [rdi+14A8h], 0
0x180007312  lea     r13, [rdi+14h]
0x180007316  jnz     short loc_18000737F
0x180007318  mov     eax, [rdi+21Ch]
0x18000731e  lea     r13, [rdi+14h]
0x180007322  xor     r9d, r9d
0x180007325  test    eax, eax
0x180007327  jle     short loc_18000737F
0x180007329  add     r11, 7FFCh
0x180007330  mov     ebx, eax
0x180007332  nop     dword ptr [rax+00h]
0x180007336  nop     word ptr [rax+rax+00000000h]
0x180007340  mov     edx, 1FFFh
0x180007345  xor     ecx, ecx
0x180007347  mov     r8d, edx
0x18000734a  mov     rax, r11
0x18000734d  nop     dword ptr [rax]
0x180007350  add     ecx, [rax]
0x180007352  cmp     ecx, r10d
0x180007355  jg      short loc_180007367
0x180007357  dec     r8d
0x18000735a  dec     rdx
0x18000735d  sub     rax, 4
0x180007361  cmp     rdx, 20h ; ' '
0x180007365  jg      short loc_180007350
0x180007367  cmp     r9d, r8d
0x18000736a  cmovl   r9d, r8d
0x18000736e  add     r11, 8000h
0x180007375  sub     rbx, 1
0x180007379  jnz     short loc_180007340
0x18000737b  lea     r13, [rdi+14h]
0x18000737f  movsd   xmm2, qword ptr [rdi+13F0h]; double
0x180007387  lea     eax, ds:0[r9*8]
0x18000738f  movsd   xmm1, qword ptr [rdi+13E8h]; double
0x180007397  mov     r9d, 2; int
0x18000739d  movd    xmm0, eax
0x1800073a1  mov     rcx, rdi; this
0x1800073a4  cvtdq2ps xmm0, xmm0
0x1800073a7  divss   xmm0, dword ptr [rdi+1428h]
0x1800073af  cvttss2si eax, xmm0
0x1800073b3  mov     [rsp+88h+var_68], eax; int
0x1800073b7  call    ?gamma_curve@LibRaw@@IEAAXNNHH@Z; LibRaw::gamma_curve(double,double,int,int)
0x1800073bc  jmp     short loc_1800073C2
0x1800073be  lea     r13, [rcx+14h]
0x1800073c2  test    byte ptr [rdi+30h], 4
0x1800073c6  lea     r14, [rdi+1Ch]
0x1800073ca  movzx   eax, word ptr [r14]
0x1800073ce  lea     r15, [rdi+1Eh]
0x1800073d2  movzx   ecx, word ptr [rbp+0]
0x1800073d6  movzx   edx, word ptr [r13+0]
0x1800073db  mov     [rsp+88h+arg_0], ax
0x1800073e3  movzx   eax, word ptr [r15]
0x1800073e7  mov     [rsp+88h+var_58], ax
0x1800073ec  mov     [rsp+88h+var_56], cx
0x1800073f1  mov     [rsp+88h+var_54], dx
0x1800073f6  mov     [r14], dx
0x1800073fa  mov     [r15], cx
0x1800073fe  jz      short loc_180007409
0x180007400  mov     [rbp+0], dx
0x180007404  mov     [r13+0], cx
0x180007409  xor     r8d, r8d; int
0x18000740c  xor     edx, edx; int
0x18000740e  mov     rcx, rdi; this
0x180007411  call    ?flip_index@LibRaw@@IEAAHHH@Z; LibRaw::flip_index(int,int)
0x180007416  xor     edx, edx; int
0x180007418  mov     r8d, 1; int
0x18000741e  mov     rcx, rdi; this
0x180007421  mov     esi, eax
0x180007423  call    ?flip_index@LibRaw@@IEAAHHH@Z; LibRaw::flip_index(int,int)
0x180007428  movzx   r8d, word ptr [rbp+0]; int
0x18000742d  mov     r12d, eax
0x180007430  xor     edx, edx; int
0x180007432  mov     rcx, rdi; this
0x180007435  sub     r12d, esi
0x180007438  call    ?flip_index@LibRaw@@IEAAHHH@Z; LibRaw::flip_index(int,int)
0x18000743d  xor     r8d, r8d; int
0x180007440  mov     edx, 1; int
0x180007445  mov     rcx, rdi; this
0x180007448  mov     ebx, eax
0x18000744a  call    ?flip_index@LibRaw@@IEAAHHH@Z; LibRaw::flip_index(int,int)
0x18000744f  sub     eax, ebx
0x180007451  xor     r8d, r8d
0x180007454  mov     [rsp+88h+var_4C], eax
0x180007458  mov     [rsp+88h+var_50], r8d
0x18000745d  cmp     r8w, [r13+0]
0x180007462  jnb     loc_18000769A
0x180007468  movsxd  r14, r12d
0x18000746b  mov     r15d, r8d
0x18000746e  xchg    ax, ax
0x180007470  mov     eax, [rdi+1470h]
0x180007476  mov     r11d, r8d
0x180007479  movzx   ecx, word ptr [rbp+0]
0x18000747d  movsxd  rdx, r15d
0x180007480  add     rdx, [rsp+88h+arg_8]
0x180007488  cmp     [rsp+88h+arg_18], 0
0x180007490  movsxd  r10, esi
0x180007493  jz      loc_18000758A
0x180007499  cmp     eax, 8
0x18000749c  jnz     short loc_180007518
0x18000749e  cmp     r8w, cx
0x1800074a2  jnb     loc_180007661
0x1800074a8  lea     r10, ds:0[r10*4]
0x1800074b0  lea     rbx, ds:0[r14*4]
0x1800074b8  nop     dword ptr [rax+rax+00000000h]
0x1800074c0  mov     eax, [rdi+21Ch]
0x1800074c6  sub     eax, 1
0x1800074c9  movsxd  r8, eax
0x1800074cc  js      short loc_180007501
0x1800074ce  lea     r9, [r10+r8]
0x1800074d2  add     r9, r9
0x1800074d5  nop     word ptr [rax+rax+00000000h]
0x1800074e0  mov     rax, [rdi+8]
0x1800074e4  lea     r9, [r9-2]
0x1800074e8  movzx   ecx, word ptr [rax+r9+2]
0x1800074ee  movzx   eax, byte ptr [rdi+rcx*2+1511h]
0x1800074f6  mov     [rdx], al
0x1800074f8  inc     rdx
0x1800074fb  sub     r8, 1
0x1800074ff  jns     short loc_1800074E0
0x180007501  movzx   eax, word ptr [rbp+0]
0x180007505  inc     r11d
0x180007508  add     esi, r12d
0x18000750b  add     r10, rbx
0x18000750e  cmp     r11d, eax
0x180007511  jl      short loc_1800074C0
0x180007513  jmp     loc_180007661
0x180007518  cmp     r8w, cx
0x18000751c  jnb     loc_180007661
0x180007522  lea     r10, ds:0[r10*4]
0x18000752a  lea     rbx, ds:0[r14*4]
0x180007532  mov     eax, [rdi+21Ch]
0x180007538  sub     eax, 1
0x18000753b  movsxd  r8, eax
0x18000753e  js      short loc_180007573
0x180007540  lea     r9, [r10+r8]
0x180007544  add     r9, r9
0x180007547  nop     word ptr [rax+rax+00000000h]
0x180007550  mov     rax, [rdi+8]
0x180007554  lea     r9, [r9-2]
0x180007558  movzx   ecx, word ptr [rax+r9+2]
0x18000755e  movzx   eax, word ptr [rdi+rcx*2+1510h]
0x180007566  mov     [rdx], ax
0x180007569  add     rdx, 2
0x18000756d  sub     r8, 1
0x180007571  jns     short loc_180007550
0x180007573  movzx   eax, word ptr [rbp+0]
0x180007577  inc     r11d
0x18000757a  add     esi, r12d
0x18000757d  add     r10, rbx
0x180007580  cmp     r11d, eax
0x180007583  jl      short loc_180007532
0x180007585  jmp     loc_180007661
0x18000758a  cmp     eax, 8
0x18000758d  jnz     short loc_1800075FE
0x18000758f  cmp     r8w, cx
0x180007593  jnb     loc_180007661
0x180007599  lea     r10, ds:0[r10*8]
0x1800075a1  lea     rbx, ds:0[r14*8]
0x1800075a9  nop     dword ptr [rax+00000000h]
0x1800075b0  cmp     dword ptr [rdi+21Ch], 0
0x1800075b7  mov     r9d, r8d
0x1800075ba  jle     short loc_1800075EA
0x1800075bc  mov     r8, r10
0x1800075bf  nop
0x1800075c0  mov     rax, [rdi+8]
0x1800075c4  lea     r8, [r8+2]
0x1800075c8  inc     r9d
0x1800075cb  movzx   ecx, word ptr [rax+r8-2]
0x1800075d1  movzx   eax, byte ptr [rdi+rcx*2+1511h]
0x1800075d9  mov     [rdx], al
0x1800075db  inc     rdx
0x1800075de  cmp     r9d, [rdi+21Ch]
0x1800075e5  jl      short loc_1800075C0
0x1800075e7  xor     r8d, r8d
0x1800075ea  movzx   eax, word ptr [rbp+0]
0x1800075ee  inc     r11d
0x1800075f1  add     esi, r12d
0x1800075f4  add     r10, rbx
0x1800075f7  cmp     r11d, eax
0x1800075fa  jl      short loc_1800075B0
0x1800075fc  jmp     short loc_180007661
0x1800075fe  cmp     r8w, cx
0x180007602  jnb     short loc_180007661
0x180007604  lea     r10, ds:0[r10*8]
0x18000760c  lea     rbx, ds:0[r14*8]
0x180007614  cmp     dword ptr [rdi+21Ch], 0
0x18000761b  mov     r9d, r8d
0x18000761e  jle     short loc_18000764F
0x180007620  mov     r8, r10
0x180007623  mov     rax, [rdi+8]
0x180007627  lea     r8, [r8+2]
0x18000762b  inc     r9d
0x18000762e  movzx   ecx, word ptr [rax+r8-2]
0x180007634  movzx   eax, word ptr [rdi+rcx*2+1510h]
0x18000763c  mov     [rdx], ax
0x18000763f  add     rdx, 2
0x180007643  cmp     r9d, [rdi+21Ch]
0x18000764a  jl      short loc_180007623
0x18000764c  xor     r8d, r8d
0x18000764f  movzx   eax, word ptr [rbp+0]
0x180007653  inc     r11d
0x180007656  add     esi, r12d
0x180007659  add     r10, rbx
0x18000765c  cmp     r11d, eax
0x18000765f  jl      short loc_180007614
0x180007661  mov     ecx, [rsp+88h+var_50]
0x180007665  mov     r8d, 0
0x18000766b  add     r15d, [rsp+88h+arg_10]
0x180007673  inc     ecx
0x180007675  add     esi, [rsp+88h+var_4C]
0x180007679  movzx   eax, word ptr [r13+0]
0x18000767e  mov     [rsp+88h+var_50], ecx
0x180007682  cmp     ecx, eax
0x180007684  jl      loc_180007470
0x18000768a  lea     r14, [rdi+1Ch]
0x18000768e  lea     r15, [rdi+1Eh]
0x180007692  lea     rbp, [rdi+16h]
0x180007696  lea     r13, [rdi+14h]
0x18000769a  movzx   eax, [rsp+88h+arg_0]
0x1800076a2  mov     r12, [rsp+88h+var_28]
0x1800076a7  mov     rsi, [rsp+88h+var_20]
0x1800076ac  mov     rbx, [rsp+88h+var_10]
0x1800076b1  mov     [r14], ax
0x1800076b5  movzx   eax, [rsp+88h+var_58]
0x1800076ba  mov     r14, [rsp+88h+var_38]
0x1800076bf  mov     [r15], ax
0x1800076c3  movzx   eax, [rsp+88h+var_56]
0x1800076c8  mov     r15, [rsp+88h+var_40]
0x1800076cd  mov     [rbp+0], ax
0x1800076d1  movzx   eax, [rsp+88h+var_54]
0x1800076d6  mov     rbp, [rsp+88h+var_18]
0x1800076db  mov     [r13+0], ax
0x1800076e0  xor     eax, eax
0x1800076e2  mov     r13, [rsp+88h+var_30]
0x1800076e7  add     rsp, 80h
0x1800076ee  pop     rdi
0x1800076ef  retn
```
