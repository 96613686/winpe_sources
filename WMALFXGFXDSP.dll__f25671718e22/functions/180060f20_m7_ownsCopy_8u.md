# m7_ownsCopy_8u

- ea: `0x180060f20`
- end: `0x1800612eb`
- name: `m7_ownsCopy_8u`
- size: `971`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180024d24`

## callees

- `0x180060f20`

## pseudocode

```c
__m128i *__fastcall m7_ownsCopy_8u(const __m128i *a1, __m128i *a2, __int64 a3)
{
  __int64 v3; // rax
  const __m128i *v4; // rdi
  __m128i *v6; // r9
  __int64 v7; // r10
  __int64 v8; // r10
  char v9; // cc
  __int64 j; // r10
  __int64 v12; // r10
  __m128i si128; // xmm0
  __m128i v14; // xmm1
  __m128i v15; // xmm2
  __m128i v16; // xmm3
  __int64 v17; // r10
  __int64 v18; // r10
  __m128i v19; // xmm0
  __m128i v20; // xmm0
  __m128i v21; // xmm0
  __int64 v22; // r10
  __m128i v23; // xmm0
  int *v39; // r8
  char *v40; // rbx
  char v41; // dl
  __int64 v42; // rcx
  int v43; // r8d
  int v44; // r8d
  __m128i v45; // xmm0
  __int64 v46; // r10
  __int64 v47; // r8
  __int64 i; // r10
  __m128i v49; // xmm0
  int v50; // [rsp+0h] [rbp-48h] BYREF
  _BYTE v51[20]; // [rsp+4h] [rbp-44h] BYREF
  __int64 *v52; // [rsp+18h] [rbp-30h]
  const __m128i *v53; // [rsp+20h] [rbp-28h]
  __int64 v54; // [rsp+28h] [rbp-20h]
  __int64 v55; // [rsp+30h] [rbp-18h]
  unsigned __int64 v56; // [rsp+38h] [rbp-10h]
  unsigned __int64 v57; // [rsp+40h] [rbp-8h]

  v4 = a1;
  v6 = a2;
  v7 = (int)a3;
  if ( !(_DWORD)a3 )
    return a2;
  if ( (int)a3 >= 64LL )
  {
    if ( ((unsigned __int8)a2 & 0xF) != 0 )
    {
      *a2 = _mm_loadu_si128(a1);
      a1 = (const __m128i *)(((unsigned __int8)a2 & 0xF) - 16LL);
      v4 = (const __m128i *)((char *)v4 - (__int64)a1);
      v6 = (__m128i *)((char *)a2 - (char *)a1);
      v7 = (__int64)a1->m128i_i64 + (int)a3;
      if ( v7 < 64 )
        goto LABEL_3;
      if ( ((unsigned __int8)v4 & 0xF) == 0 )
      {
LABEL_14:
        v12 = v7 - 64;
        do
        {
          si128 = _mm_load_si128(v4);
          v14 = _mm_load_si128(v4 + 1);
          v15 = _mm_load_si128(v4 + 2);
          v16 = _mm_load_si128(v4 + 3);
          v4 += 4;
          *v6 = si128;
          v6[1] = v14;
          v6[2] = v15;
          v6[3] = v16;
          v6 += 4;
          v9 = v12 < 64;
          v12 -= 64;
        }
        while ( !v9 );
        v17 = v12 + 64;
        if ( !v17 )
          return a2;
        v9 = v17 < 16;
        v18 = v17 - 16;
        if ( !v9 )
        {
          v19 = _mm_load_si128(v4++);
          *v6++ = v19;
          v9 = v18 < 16;
          v18 -= 16;
          if ( !v9 )
          {
            v20 = _mm_load_si128(v4++);
            *v6++ = v20;
            v9 = v18 < 16;
            v18 -= 16;
            if ( !v9 )
            {
              v21 = _mm_load_si128(v4++);
              *v6++ = v21;
              v18 -= 16;
            }
          }
        }
        v7 = v18 + 16;
        if ( !v7 )
          return a2;
        goto LABEL_3;
      }
      if ( v7 < 0x80000 )
        goto LABEL_26;
    }
    else if ( (int)a3 < 0x80000LL )
    {
      goto LABEL_13;
    }
    *(_QWORD *)&v51[12] = v3;
    v52 = qword_1801B7340;
    v53 = a1;
    v54 = a3;
    v55 = a3;
    v56 = (unsigned __int64)qword_1801B7340;
    _RAX = 0;
    __asm { cpuid }
    if ( (_DWORD)_RBX == 1970169159 && (_DWORD)_RDX == 1231384169 && (_DWORD)_RCX == 1818588270 )
    {
      if ( (int)_RAX < 4 )
      {
        v57 = 1;
      }
      else
      {
        _RAX = 4;
        __asm { cpuid }
        v57 = ((unsigned int)_RAX >> 26) + 1;
      }
      _RAX = 2;
      __asm { cpuid }
      if ( (_BYTE)_RAX == 1 )
      {
        if ( (int)_RAX < 0 )
          LODWORD(_RAX) = 0;
        if ( (int)_RBX < 0 )
          LODWORD(_RBX) = 0;
        if ( (int)_RCX < 0 )
          LODWORD(_RCX) = 0;
        if ( (int)_RDX < 0 )
          LODWORD(_RDX) = 0;
        v39 = &v50;
        if ( (_DWORD)_RAX )
        {
          v50 = _RAX;
          v39 = (int *)v51;
          LODWORD(_RAX) = 3;
        }
        if ( (_DWORD)_RBX )
        {
          *v39++ = _RBX;
          LODWORD(_RAX) = _RAX + 4;
        }
        if ( (_DWORD)_RCX )
        {
          *v39++ = _RCX;
          LODWORD(_RAX) = _RAX + 4;
        }
        if ( (_DWORD)_RDX )
        {
          *v39 = _RDX;
          LODWORD(_RAX) = _RAX + 4;
        }
        v40 = (char *)v56;
        if ( (_DWORD)_RAX )
        {
LABEL_54:
          v41 = *v40;
          if ( *v40 )
          {
            v40 += 2;
            v42 = (unsigned int)_RAX;
            while ( v41 != v51[v42 - 4] )
            {
              v42 = (unsigned int)(v42 - 1);
              if ( !(_DWORD)v42 )
                goto LABEL_54;
            }
            v56 = ((unsigned __int64)((unsigned __int8)*(v40 - 1) >> 4) << ((*(v40 - 1) & 0xFu) + 18)) / v57;
LABEL_61:
            if ( v56 != -1 && v7 >= (__int64)(v56 >> 1) )
            {
              while ( 1 )
              {
                v9 = v7 < 0x40000;
                v7 -= 0x40000;
                if ( v9 )
                  break;
                v43 = 2048;
                do
                {
                  v4 += 8;
                  --v43;
                }
                while ( v43 );
                v4 -= 0x4000;
                v44 = 0x40000;
                do
                {
                  v45 = _mm_loadu_si128(v4++);
                  _mm_stream_si128(v6++, v45);
                  v44 -= 16;
                }
                while ( v44 );
              }
              v46 = v7 + 0x40000;
              if ( v46 )
              {
                v47 = v46;
                do
                {
                  v9 = v47 < 128;
                  v47 -= 128;
                }
                while ( !v9 );
                v9 = v46 < 16;
                for ( i = v46 - 16; !v9; i -= 16 )
                {
                  v49 = _mm_loadu_si128(v4++);
                  _mm_stream_si128(v6++, v49);
                  v9 = i < 16;
                }
                _mm_sfence();
                v7 = i + 16;
                if ( v7 )
                  goto LABEL_3;
              }
              else
              {
                _mm_sfence();
              }
              return a2;
            }
LABEL_13:
            if ( ((unsigned __int8)v4 & 0xF) == 0 )
              goto LABEL_14;
LABEL_26:
            v22 = v7 - 64;
            do
            {
              *v6 = _mm_lddqu_si128(v4);
              v6[1] = _mm_lddqu_si128(v4 + 1);
              v6[2] = _mm_lddqu_si128(v4 + 2);
              v23 = _mm_lddqu_si128(v4 + 3);
              v4 += 4;
              v6[3] = v23;
              v6 += 4;
              v9 = v22 < 64;
              v22 -= 64;
            }
            while ( !v9 );
            v9 = (v22 + 64 < 0) ^ __OFADD__(64, v22) | (v22 == -64);
            v7 = v22 + 64;
            if ( !v9 )
              goto LABEL_3;
            return a2;
          }
        }
      }
    }
    v56 = -1;
    goto LABEL_61;
  }
LABEL_3:
  if ( v7 >= 8 )
  {
    *(__int64 *)((char *)&v6->m128i_i64[-1] + v7) = *(__int64 *)((char *)&v4->m128i_i64[-1] + v7);
    v8 = v7 - (((_BYTE)v7 + (_BYTE)v6) & 7);
    v9 = v8 < 8;
    for ( j = v8 - 8; !v9; j -= 8 )
    {
      *(__int64 *)((char *)v6->m128i_i64 + j) = *(__int64 *)((char *)v4->m128i_i64 + j);
      v9 = j < 8;
    }
    if ( j != -8 )
      v6->m128i_i64[0] = v4->m128i_i64[0];
    return a2;
  }
  do
  {
    v6->m128i_i8[v7 - 1] = v4->m128i_i8[v7 - 1];
    --v7;
  }
  while ( v7 );
  return a2;
}

```

## disassembly

```asm
0x180060f20  push    rsi
0x180060f21  push    rdi
0x180060f22  push    rbx
0x180060f23  push    rbp
0x180060f24  mov     rbp, rsp
0x180060f27  mov     rdi, rcx
0x180060f2a  mov     rsi, rdx
0x180060f2d  mov     rdx, r8
0x180060f30  mov     r9, rsi
0x180060f33  movsxd  r10, edx
0x180060f36  test    r10, r10
0x180060f39  jz      short loc_180060F7C
0x180060f3b  cmp     r10, 40h ; '@'
0x180060f3f  jge     short loc_180060F9D
0x180060f41  cmp     r10, 8
0x180060f45  jl      short loc_180060F84
0x180060f47  lea     r8, [r10+r9]
0x180060f4b  mov     rbx, [r10+rdi-8]
0x180060f50  and     r8, 7
0x180060f54  mov     [r10+r9-8], rbx
0x180060f59  sub     r10, r8
0x180060f5c  sub     r10, 8
0x180060f60  jl      short loc_180060F70
0x180060f62  mov     rbx, [r10+rdi]
0x180060f66  mov     [r10+r9], rbx
0x180060f6a  sub     r10, 8
0x180060f6e  jge     short loc_180060F62
0x180060f70  add     r10, 8
0x180060f74  jz      short loc_180060F7C
0x180060f76  mov     rbx, [rdi]
0x180060f79  mov     [r9], rbx
0x180060f7c  mov     rax, rsi
0x180060f7f  pop     rbp
0x180060f80  pop     rbx
0x180060f81  pop     rdi
0x180060f82  pop     rsi
0x180060f83  retn
0x180060f84  movzx   ebx, byte ptr [r10+rdi-1]
0x180060f8a  mov     [r10+r9-1], bl
0x180060f8f  sub     r10, 1
0x180060f93  jnz     short loc_180060F84
0x180060f95  mov     rax, rsi
0x180060f98  pop     rbp
0x180060f99  pop     rbx
0x180060f9a  pop     rdi
0x180060f9b  pop     rsi
0x180060f9c  retn
0x180060f9d  test    r9, 0Fh
0x180060fa4  jnz     loc_180061061
0x180060faa  cmp     r10, 80000h
0x180060fb1  jge     loc_1800610E9
0x180060fb7  test    rdi, 0Fh
0x180060fbe  jnz     loc_18006109E
0x180060fc4  sub     r10, 40h ; '@'
0x180060fc8  movdqa  xmm0, xmmword ptr [rdi]
0x180060fcc  movdqa  xmm1, xmmword ptr [rdi+10h]
0x180060fd1  movdqa  xmm2, xmmword ptr [rdi+20h]
0x180060fd6  movdqa  xmm3, xmmword ptr [rdi+30h]
0x180060fdb  add     rdi, 40h ; '@'
0x180060fdf  movdqa  xmmword ptr [r9], xmm0
0x180060fe4  movdqa  xmmword ptr [r9+10h], xmm1
0x180060fea  movdqa  xmmword ptr [r9+20h], xmm2
0x180060ff0  movdqa  xmmword ptr [r9+30h], xmm3
0x180060ff6  add     r9, 40h ; '@'
0x180060ffa  sub     r10, 40h ; '@'
0x180060ffe  jge     short loc_180060FC8
0x180061000  add     r10, 40h ; '@'
0x180061004  jz      short loc_180061059
0x180061006  sub     r10, 10h
0x18006100a  jl      short loc_18006104F
0x18006100c  movdqa  xmm0, xmmword ptr [rdi]
0x180061010  add     rdi, 10h
0x180061014  movdqa  xmmword ptr [r9], xmm0
0x180061019  add     r9, 10h
0x18006101d  sub     r10, 10h
0x180061021  jl      short loc_18006104F
0x180061023  movdqa  xmm0, xmmword ptr [rdi]
0x180061027  add     rdi, 10h
0x18006102b  movdqa  xmmword ptr [r9], xmm0
0x180061030  add     r9, 10h
0x180061034  sub     r10, 10h
0x180061038  jl      short loc_18006104F
0x18006103a  movdqa  xmm0, xmmword ptr [rdi]
0x18006103e  add     rdi, 10h
0x180061042  movdqa  xmmword ptr [r9], xmm0
0x180061047  add     r9, 10h
0x18006104b  sub     r10, 10h
0x18006104f  add     r10, 10h
0x180061053  jnz     loc_180060F41
0x180061059  mov     rax, rsi
0x18006105c  pop     rbp
0x18006105d  pop     rbx
0x18006105e  pop     rdi
0x18006105f  pop     rsi
0x180061060  retn
0x180061061  movdqu  xmm0, xmmword ptr [rdi]
0x180061065  mov     rcx, r9
0x180061068  and     rcx, 0Fh
0x18006106c  movdqu  xmmword ptr [r9], xmm0
0x180061071  sub     rcx, 10h
0x180061075  sub     rdi, rcx
0x180061078  sub     r9, rcx
0x18006107b  add     r10, rcx
0x18006107e  cmp     r10, 40h ; '@'
0x180061082  jl      loc_180060F41
0x180061088  test    rdi, 0Fh
0x18006108f  jz      loc_180060FC4
0x180061095  cmp     r10, 80000h
0x18006109c  jge     short loc_1800610E9
0x18006109e  sub     r10, 40h ; '@'
0x1800610a2  lddqu   xmm0, xmmword ptr [rdi]
0x1800610a6  movdqa  xmmword ptr [r9], xmm0
0x1800610ab  lddqu   xmm0, xmmword ptr [rdi+10h]
0x1800610b0  movdqa  xmmword ptr [r9+10h], xmm0
0x1800610b6  lddqu   xmm0, xmmword ptr [rdi+20h]
0x1800610bb  movdqa  xmmword ptr [r9+20h], xmm0
0x1800610c1  lddqu   xmm0, xmmword ptr [rdi+30h]
0x1800610c6  add     rdi, 40h ; '@'
0x1800610ca  movdqa  xmmword ptr [r9+30h], xmm0
0x1800610d0  add     r9, 40h ; '@'
0x1800610d4  sub     r10, 40h ; '@'
0x1800610d8  jge     short loc_1800610A2
0x1800610da  add     r10, 40h ; '@'
0x1800610de  jg      loc_180060F41
0x1800610e4  jmp     loc_180060F7C
0x1800610e9  lea     rbx, qword_1801B7340
0x1800610f0  sub     rsp, 48h
0x1800610f4  mov     [rsp+48h+var_38], rax
0x1800610f9  mov     [rsp+48h+var_30], rbx
0x1800610fe  mov     [rsp+48h+var_28], rcx
0x180061103  mov     [rsp+48h+var_20], rdx
0x180061108  mov     [rsp+48h+var_18], r8
0x18006110d  mov     [rsp+48h+var_10], rbx
0x180061112  xor     eax, eax
0x180061114  cpuid
0x180061116  cmp     ebx, 756E6547h
0x18006111c  jnz     loc_180061212
0x180061122  cmp     edx, 49656E69h
0x180061128  jnz     loc_180061212
0x18006112e  cmp     ecx, 6C65746Eh
0x180061134  jnz     loc_180061212
0x18006113a  cmp     eax, 4
0x18006113d  jl      short loc_180061155
0x18006113f  mov     eax, 4
0x180061144  xor     ecx, ecx
0x180061146  cpuid
0x180061148  shr     eax, 1Ah
0x18006114b  add     eax, 1
0x18006114e  mov     [rsp+48h+var_8], rax
0x180061153  jmp     short loc_18006115E
0x180061155  mov     [rsp+48h+var_8], 1
0x18006115e  mov     eax, 2
0x180061163  cpuid
0x180061165  cmp     al, 1
0x180061167  jnz     loc_180061212
0x18006116d  test    eax, 80000000h
0x180061172  jz      short loc_180061176
0x180061174  xor     eax, eax
0x180061176  test    ebx, 80000000h
0x18006117c  jz      short loc_180061180
0x18006117e  xor     ebx, ebx
0x180061180  test    ecx, 80000000h
0x180061186  jz      short loc_18006118A
0x180061188  xor     ecx, ecx
0x18006118a  test    edx, 80000000h
0x180061190  jz      short loc_180061194
0x180061192  xor     edx, edx
0x180061194  mov     r8, rsp
0x180061197  test    eax, eax
0x180061199  jz      short loc_1800611A7
0x18006119b  mov     [r8], eax
0x18006119e  add     r8, 4
0x1800611a2  mov     eax, 3
0x1800611a7  test    ebx, ebx
0x1800611a9  jz      short loc_1800611B5
0x1800611ab  mov     [r8], ebx
0x1800611ae  add     r8, 4
0x1800611b2  add     eax, 4
0x1800611b5  test    ecx, ecx
0x1800611b7  jz      short loc_1800611C3
0x1800611b9  mov     [r8], ecx
0x1800611bc  add     r8, 4
0x1800611c0  add     eax, 4
0x1800611c3  test    edx, edx
0x1800611c5  jz      short loc_1800611CD
0x1800611c7  mov     [r8], edx
0x1800611ca  add     eax, 4
0x1800611cd  mov     rbx, [rsp+48h+var_10]
0x1800611d2  test    eax, eax
0x1800611d4  jz      short loc_180061212
0x1800611d6  movzx   edx, byte ptr [rbx]
0x1800611d9  test    edx, edx
0x1800611db  jz      short loc_180061212
0x1800611dd  add     rbx, 2
0x1800611e1  mov     ecx, eax
0x1800611e3  cmp     dl, byte ptr [rsp+rcx+48h+var_48]
0x1800611e6  jz      short loc_1800611EF
0x1800611e8  sub     ecx, 1
0x1800611eb  jnz     short loc_1800611E3
0x1800611ed  jmp     short loc_1800611D6
0x1800611ef  movzx   eax, byte ptr [rbx-1]
0x1800611f3  mov     ecx, eax
0x1800611f5  shr     eax, 4
0x1800611f8  and     ecx, 0Fh
0x1800611fb  add     ecx, 12h
0x1800611fe  shl     rax, cl
0x180061201  mov     rcx, [rsp+48h+var_8]
0x180061206  xor     edx, edx
0x180061208  div     rcx
0x18006120b  mov     [rsp+48h+var_10], rax
0x180061210  jmp     short loc_18006121B
0x180061212  mov     [rsp+48h+var_10], 0FFFFFFFFFFFFFFFFh
0x18006121b  mov     rax, [rsp+48h+var_38]
0x180061220  mov     rbx, [rsp+48h+var_30]
0x180061225  mov     rcx, [rsp+48h+var_28]
0x18006122a  mov     rdx, [rsp+48h+var_20]
0x18006122f  mov     r8, [rsp+48h+var_18]
0x180061234  mov     rbx, [rsp+48h+var_10]
0x180061239  add     rsp, 48h
0x18006123d  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180061241  jz      loc_180060FB7
0x180061247  shr     rbx, 1
0x18006124a  cmp     r10, rbx
0x18006124d  jl      loc_180060FB7
0x180061253  sub     r10, 40000h
0x18006125a  jl      short loc_180061298
0x18006125c  mov     r8d, 800h
0x180061262  movzx   ebx, byte ptr [rdi]
0x180061265  add     rdi, 80h
0x18006126c  sub     r8d, 1
0x180061270  jnz     short loc_180061262
0x180061272  sub     rdi, 40000h
0x180061279  mov     r8d, 40000h
0x18006127f  movdqu  xmm0, xmmword ptr [rdi]
0x180061283  add     rdi, 10h
0x180061287  movntdq xmmword ptr [r9], xmm0
0x18006128c  add     r9, 10h
0x180061290  sub     r8d, 10h
0x180061294  jnz     short loc_18006127F
0x180061296  jmp     short loc_180061253
0x180061298  add     r10, 40000h
0x18006129f  jz      short loc_1800612E6
0x1800612a1  mov     r8, r10
0x1800612a4  jmp     short loc_1800612AB
0x1800612a6  movzx   ebx, byte ptr [r8+rdi]
0x1800612ab  sub     r8, 80h
0x1800612b2  jge     short loc_1800612A6
0x1800612b4  sub     r10, 10h
0x1800612b8  jl      short loc_1800612D1
0x1800612ba  movdqu  xmm0, xmmword ptr [rdi]
0x1800612be  add     rdi, 10h
0x1800612c2  movntdq xmmword ptr [r9], xmm0
0x1800612c7  add     r9, 10h
0x1800612cb  sub     r10, 10h
0x1800612cf  jge     short loc_1800612BA
0x1800612d1  sfence
0x1800612d4  add     r10, 10h
0x1800612d8  jnz     loc_180060F41
0x1800612de  mov     rax, rsi
0x1800612e1  pop     rbp
0x1800612e2  pop     rbx
0x1800612e3  pop     rdi
0x1800612e4  pop     rsi
0x1800612e5  retn
0x1800612e6  sfence
0x1800612e9  jmp     short loc_1800612DE
```
