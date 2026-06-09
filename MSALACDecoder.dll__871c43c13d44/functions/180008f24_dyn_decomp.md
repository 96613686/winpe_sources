# dyn_decomp

- ea: `0x180008f24`
- end: `0x18000925e`
- name: `dyn_decomp`
- size: `826`
- prototype: `__int64 __fastcall(_DWORD *, __int64 *, _DWORD *, int, int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007798`

## callees

- `0x180001eac`
- `0x180008dd8`
- `0x180008f24`

## pseudocode

```c
__int64 __fastcall dyn_decomp(_DWORD *a1, __int64 *a2, _DWORD *a3, int a4, int a5, unsigned int *a6)
{
  int v7; // edx
  int v8; // r12d
  int v9; // r13d
  unsigned int v10; // r15d
  __int64 v11; // r10
  unsigned int v12; // r8d
  unsigned int v13; // r14d
  unsigned int v14; // edi
  int v15; // edx
  unsigned int v16; // ebx
  unsigned int v17; // ecx
  int i; // edx
  unsigned int v19; // ecx
  int _32bit; // eax
  _DWORD *v21; // r10
  _DWORD *v22; // r10
  unsigned int v23; // eax
  int j; // edx
  unsigned int v25; // r8d
  unsigned int v26; // eax
  int k; // r9d
  int v28; // r14d
  unsigned int v29; // edx
  unsigned int v30; // r8d
  int v31; // eax
  bool v32; // sf
  bool v33; // of
  unsigned int v34; // edi
  unsigned int v35; // edx
  int v37; // [rsp+30h] [rbp-68h]
  unsigned int v38; // [rsp+34h] [rbp-64h]
  unsigned int v39; // [rsp+38h] [rbp-60h]
  unsigned int v40; // [rsp+3Ch] [rbp-5Ch]
  __int64 v41; // [rsp+40h] [rbp-58h]
  unsigned int v42; // [rsp+A0h] [rbp+8h] BYREF
  int v43; // [rsp+A8h] [rbp+10h]
  _DWORD *v44; // [rsp+B0h] [rbp+18h]
  int v45; // [rsp+B8h] [rbp+20h]

  v45 = a4;
  v44 = a3;
  if ( !a2 || !a3 || !a6 )
    return 4294967246LL;
  v7 = a1[2];
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = *a2;
  v12 = a1[3];
  v13 = 8 * (*((_DWORD *)a2 + 2) - *(_DWORD *)a2);
  *a6 = 0;
  v14 = *((_DWORD *)a2 + 4);
  v43 = v7;
  v15 = a1[4];
  v40 = v14;
  v42 = v14;
  v16 = a1[1];
  v39 = v12;
  v37 = v15;
  v38 = v13;
  v41 = v11;
  if ( a4 <= 0 )
    goto LABEL_37;
  while ( v14 + 31 <= v13 )
  {
    v17 = 0x80000000;
    for ( i = 0; i < 32; ++i )
    {
      if ( (v17 & ((v16 >> 9) + 3)) != 0 )
        break;
      v17 >>= 1;
    }
    v19 = 31 - i;
    if ( 31 - i >= v12 )
      v19 = v12;
    _32bit = dyn_get_32bit(v11, (unsigned int)&v42, (1 << v19) - 1, v19, a5);
    v21 = v44;
    ++v9;
    *v44 = ((unsigned int)(_32bit + v8 + 1) >> 1) * (-((_32bit + v8) & 1) | 1);
    v22 = v21 + 1;
    v44 = v22;
    if ( _32bit > 0xFFFF )
    {
      v16 = 0xFFFF;
LABEL_13:
      v14 = v42;
      v8 = 0;
      goto LABEL_14;
    }
    v16 += v43 * (_32bit + v8) - ((v16 * v43) >> 9);
    if ( (v16 & 0x3FFFFFFF) >= 0x80 )
      goto LABEL_13;
    if ( v9 >= v45 )
    {
      v14 = v42;
      goto LABEL_37;
    }
    v23 = 0x80000000;
    for ( j = 0; j < 32; ++j )
    {
      if ( (v23 & v16) != 0 )
        break;
      v23 >>= 1;
    }
    v14 = v42;
    if ( v42 + 31 > v13 )
      break;
    v25 = (*(unsigned __int8 *)(((unsigned __int64)v42 >> 3) + v41 + 3)
         | ((*(unsigned __int8 *)(((unsigned __int64)v42 >> 3) + v41 + 2)
           | (((*(unsigned __int8 *)(((unsigned __int64)v42 >> 3) + v41) << 8)
             | *(unsigned __int8 *)(((unsigned __int64)v42 >> 3) + v41 + 1)) << 8)) << 8)) << (v42 & 7);
    v26 = 0x80000000;
    for ( k = 0; k < 32; ++k )
    {
      if ( (v26
          & ~((*(unsigned __int8 *)(((unsigned __int64)v42 >> 3) + v41 + 3)
             | ((*(unsigned __int8 *)(((unsigned __int64)v42 >> 3) + v41 + 2)
               | (((*(unsigned __int8 *)(((unsigned __int64)v42 >> 3) + v41) << 8)
                 | *(unsigned __int8 *)(((unsigned __int64)v42 >> 3) + v41 + 1)) << 8)) << 8)) << (v42 & 7))) != 0 )
        break;
      v26 >>= 1;
    }
    if ( (unsigned int)k < 9 )
    {
      v29 = ((v16 + 16) >> 6) - 24 + j;
      v30 = v25 << (k + 1) >> (32 - v29);
      v14 = v29 + k + v42;
      v28 = k * (v37 & ((1 << v29) - 1)) + v30 - 1;
      if ( v30 >= 2 )
        ++v14;
      else
        v28 = k * (v37 & ((1 << v29) - 1));
    }
    else
    {
      v28 = (unsigned __int16)(v25 >> 7);
      v14 = v42 + 25;
    }
    v42 = v14;
    if ( v28 + v9 > v45 )
      break;
    v31 = 0;
    if ( v28 > 0 )
    {
      do
      {
        ++v9;
        ++v31;
      }
      while ( v31 < v28 );
      memset_0(v22, 0, 4LL * v28);
      v44 += v28;
    }
    v16 = 0;
    v33 = __OFSUB__(v28, 0xFFFF);
    v32 = v28 - 0xFFFF < 0;
    v13 = v38;
    v8 = v32 ^ v33;
LABEL_14:
    if ( v9 >= v45 )
      goto LABEL_37;
    LODWORD(v11) = v41;
    v12 = v39;
  }
  v10 = -50;
LABEL_37:
  v34 = v14 - v40;
  *a6 = v34;
  if ( v34 )
  {
    v35 = v34 + *((_DWORD *)a2 + 4);
    *a2 += (unsigned __int64)v35 >> 3;
    *((_DWORD *)a2 + 4) = v35 & 7;
  }
  if ( *a2 > (unsigned __int64)a2[1] )
    return (unsigned int)-50;
  return v10;
}

```

## disassembly

```asm
0x180008f24  mov     r11, rsp
0x180008f27  mov     [r11+20h], r9d
0x180008f2b  mov     [r11+18h], r8
0x180008f2f  push    rbx
0x180008f30  push    rbp
0x180008f31  push    rsi
0x180008f32  push    rdi
0x180008f33  push    r12
0x180008f35  push    r13
0x180008f37  push    r14
0x180008f39  push    r15
0x180008f3b  sub     rsp, 58h
0x180008f3f  mov     eax, r9d
0x180008f42  mov     rsi, rdx
0x180008f45  test    rdx, rdx
0x180008f48  jz      loc_180009248
0x180008f4e  test    r8, r8
0x180008f51  jz      loc_180009248
0x180008f57  mov     rbx, [rsp+98h+arg_28]
0x180008f5f  test    rbx, rbx
0x180008f62  jz      loc_180009248
0x180008f68  mov     edx, [rcx+8]
0x180008f6b  xor     r12d, r12d
0x180008f6e  mov     r14d, [rsi+8]
0x180008f72  xor     r13d, r13d
0x180008f75  sub     r14d, [rsi]
0x180008f78  xor     r15d, r15d
0x180008f7b  mov     r10, [rsi]
0x180008f7e  mov     r8d, [rcx+0Ch]
0x180008f82  lea     ebp, [r12-32h]
0x180008f87  shl     r14d, 3
0x180008f8b  mov     dword ptr [rbx], 0
0x180008f91  mov     ebx, [rsi+10h]
0x180008f94  mov     edi, ebx
0x180008f96  mov     [rsp+98h+arg_8], edx
0x180008f9d  mov     edx, [rcx+10h]
0x180008fa0  mov     [rsp+98h+var_5C], ebx
0x180008fa4  mov     [r11+8], ebx
0x180008fa8  mov     ebx, [rcx+4]
0x180008fab  mov     [rsp+98h+var_60], r8d
0x180008fb0  mov     [rsp+98h+var_68], edx
0x180008fb4  mov     [rsp+98h+var_64], r14d
0x180008fb9  mov     [rsp+98h+var_58], r10
0x180008fbe  test    eax, eax
0x180008fc0  jle     loc_180009214
0x180008fc6  lea     eax, [rdi+1Fh]
0x180008fc9  cmp     eax, r14d
0x180008fcc  ja      loc_180009211
0x180008fd2  mov     eax, ebx
0x180008fd4  mov     ecx, 80000000h
0x180008fd9  shr     eax, 9
0x180008fdc  add     eax, 3
0x180008fdf  xor     edx, edx
0x180008fe1  test    eax, ecx
0x180008fe3  jnz     short loc_180008FEE
0x180008fe5  shr     ecx, 1
0x180008fe7  inc     edx
0x180008fe9  cmp     edx, 20h ; ' '
0x180008fec  jl      short loc_180008FE1
0x180008fee  mov     eax, [rsp+98h+arg_20]
0x180008ff5  mov     ecx, 1Fh
0x180008ffa  sub     ecx, edx
0x180008ffc  mov     [rsp+98h+var_78], eax
0x180009000  cmp     ecx, r8d
0x180009003  lea     rdx, [rsp+98h+arg_0]
0x18000900b  cmovnb  ecx, r8d
0x18000900f  mov     r8d, 1
0x180009015  shl     r8d, cl
0x180009018  mov     r9d, ecx
0x18000901b  dec     r8d
0x18000901e  mov     rcx, r10
0x180009021  call    dyn_get_32bit
0x180009026  mov     r10, [rsp+98h+arg_10]
0x18000902e  lea     r8d, [rax+r12]
0x180009032  mov     r12d, 1
0x180009038  mov     edx, r8d
0x18000903b  lea     ecx, [r8+1]
0x18000903f  and     edx, r12d
0x180009042  shr     ecx, 1
0x180009044  neg     edx
0x180009046  add     r13d, r12d
0x180009049  or      edx, r12d
0x18000904c  imul    edx, ecx
0x18000904f  mov     [r10], edx
0x180009052  add     r10, 4
0x180009056  mov     [rsp+98h+arg_10], r10
0x18000905e  cmp     eax, 0FFFFh
0x180009063  jle     short loc_180009091
0x180009065  mov     ebx, 0FFFFh
0x18000906a  mov     edi, [rsp+98h+arg_0]
0x180009071  xor     r12d, r12d
0x180009074  cmp     r13d, [rsp+98h+arg_18]
0x18000907c  jge     loc_180009214
0x180009082  mov     r10, [rsp+98h+var_58]
0x180009087  mov     r8d, [rsp+98h+var_60]
0x18000908c  jmp     loc_180008FC6
0x180009091  imul    r8d, [rsp+98h+arg_8]
0x18000909a  mov     eax, [rsp+98h+arg_8]
0x1800090a1  imul    eax, ebx
0x1800090a4  shr     eax, 9
0x1800090a7  sub     r8d, eax
0x1800090aa  add     ebx, r8d
0x1800090ad  mov     eax, ebx
0x1800090af  and     eax, 3FFFFFFFh
0x1800090b4  cmp     eax, 80h
0x1800090b9  jnb     short loc_18000906A
0x1800090bb  mov     r11d, [rsp+98h+arg_18]
0x1800090c3  cmp     r13d, r11d
0x1800090c6  jge     loc_180009208
0x1800090cc  mov     eax, 80000000h
0x1800090d1  xor     edx, edx
0x1800090d3  test    ebx, eax
0x1800090d5  jnz     short loc_1800090E1
0x1800090d7  shr     eax, 1
0x1800090d9  add     edx, r12d
0x1800090dc  cmp     edx, 20h ; ' '
0x1800090df  jl      short loc_1800090D3
0x1800090e1  mov     edi, [rsp+98h+arg_0]
0x1800090e8  lea     eax, [rdi+1Fh]
0x1800090eb  cmp     eax, r14d
0x1800090ee  ja      loc_180009211
0x1800090f4  mov     r9, [rsp+98h+var_58]
0x1800090f9  mov     ecx, edi
0x1800090fb  shr     rcx, 3
0x1800090ff  movzx   eax, byte ptr [rcx+r9]
0x180009104  movzx   r8d, byte ptr [rcx+r9+1]
0x18000910a  shl     eax, 8
0x18000910d  or      r8d, eax
0x180009110  movzx   eax, byte ptr [rcx+r9+2]
0x180009116  shl     r8d, 8
0x18000911a  or      r8d, eax
0x18000911d  movzx   eax, byte ptr [rcx+r9+3]
0x180009123  shl     r8d, 8
0x180009127  mov     ecx, edi
0x180009129  and     ecx, 7
0x18000912c  or      r8d, eax
0x18000912f  shl     r8d, cl
0x180009132  mov     eax, 80000000h
0x180009137  mov     ecx, r8d
0x18000913a  xor     r9d, r9d
0x18000913d  not     ecx
0x18000913f  test    ecx, eax
0x180009141  jnz     short loc_18000914E
0x180009143  shr     eax, 1
0x180009145  add     r9d, r12d
0x180009148  cmp     r9d, 20h ; ' '
0x18000914c  jl      short loc_18000913F
0x18000914e  cmp     r9d, 9
0x180009152  jb      short loc_180009161
0x180009154  shr     r8d, 7
0x180009158  movzx   r14d, r8w
0x18000915c  add     edi, 19h
0x18000915f  jmp     short loc_1800091AC
0x180009161  lea     ecx, [r9+1]
0x180009165  shl     r8d, cl
0x180009168  lea     eax, [rbx+10h]
0x18000916b  shr     eax, 6
0x18000916e  mov     ecx, 20h ; ' '
0x180009173  add     eax, 0FFFFFFE8h
0x180009176  add     edx, eax
0x180009178  sub     ecx, edx
0x18000917a  shr     r8d, cl
0x18000917d  mov     ecx, edx
0x18000917f  lea     eax, [rdx+r9]
0x180009183  add     edi, eax
0x180009185  mov     eax, r12d
0x180009188  shl     eax, cl
0x18000918a  lea     r14d, [r8-1]
0x18000918e  sub     eax, r12d
0x180009191  and     eax, [rsp+98h+var_68]
0x180009195  imul    eax, r9d
0x180009199  add     r14d, eax
0x18000919c  cmp     r8d, 2
0x1800091a0  jnb     short loc_1800091AA
0x1800091a2  sub     r14d, r8d
0x1800091a5  add     r14d, r12d
0x1800091a8  jmp     short loc_1800091AC
0x1800091aa  inc     edi
0x1800091ac  lea     eax, [r14+r13]
0x1800091b0  mov     [rsp+98h+arg_0], edi
0x1800091b7  cmp     eax, r11d
0x1800091ba  jg      short loc_180009211
0x1800091bc  xor     eax, eax
0x1800091be  test    r14d, r14d
0x1800091c1  jle     short loc_1800091EE
0x1800091c3  add     r13d, r12d
0x1800091c6  add     eax, r12d
0x1800091c9  cmp     eax, r14d
0x1800091cc  jl      short loc_1800091C3
0x1800091ce  movsxd  rbx, r14d
0x1800091d1  xor     edx, edx; Val
0x1800091d3  shl     rbx, 2
0x1800091d7  mov     rcx, r10; void *
0x1800091da  mov     r8, rbx
0x1800091dd  and     r8, 0FFFFFFFFFFFFFFFCh; Size
0x1800091e1  call    memset_0
0x1800091e6  add     [rsp+98h+arg_10], rbx
0x1800091ee  xor     r12d, r12d
0x1800091f1  xor     ebx, ebx
0x1800091f3  cmp     r14d, 0FFFFh
0x1800091fa  mov     r14d, [rsp+98h+var_64]
0x1800091ff  setl    r12b
0x180009203  jmp     loc_180009074
0x180009208  mov     edi, [rsp+98h+arg_0]
0x18000920f  jmp     short loc_180009214
0x180009211  mov     r15d, ebp
0x180009214  mov     rax, [rsp+98h+arg_28]
0x18000921c  sub     edi, [rsp+98h+var_5C]
0x180009220  mov     [rax], edi
0x180009222  jz      short loc_180009238
0x180009224  mov     edx, [rsi+10h]
0x180009227  add     edx, edi
0x180009229  mov     ecx, edx
0x18000922b  shr     rcx, 3
0x18000922f  add     [rsi], rcx
0x180009232  and     edx, 7
0x180009235  mov     [rsi+10h], edx
0x180009238  mov     rcx, [rsi+8]
0x18000923c  cmp     [rsi], rcx
0x18000923f  cmova   r15d, ebp
0x180009243  mov     eax, r15d
0x180009246  jmp     short loc_18000924D
0x180009248  mov     eax, 0FFFFFFCEh
0x18000924d  add     rsp, 58h
0x180009251  pop     r15
0x180009253  pop     r14
0x180009255  pop     r13
0x180009257  pop     r12
0x180009259  pop     rdi
0x18000925a  pop     rsi
0x18000925b  pop     rbp
0x18000925c  pop     rbx
0x18000925d  retn
```
