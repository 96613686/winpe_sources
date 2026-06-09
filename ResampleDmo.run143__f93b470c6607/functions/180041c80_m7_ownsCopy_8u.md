# m7_ownsCopy_8u

- ea: `0x180041c80`
- end: `0x18004204b`
- name: `m7_ownsCopy_8u`
- size: `971`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180016454`

## callees

- `0x180041c80`

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
    v52 = qword_1800B4260;
    v53 = a1;
    v54 = a3;
    v55 = a3;
    v56 = (unsigned __int64)qword_1800B4260;
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
0x180041c80  push    rsi
0x180041c81  push    rdi
0x180041c82  push    rbx
0x180041c83  push    rbp
0x180041c84  mov     rbp, rsp
0x180041c87  mov     rdi, rcx
0x180041c8a  mov     rsi, rdx
0x180041c8d  mov     rdx, r8
0x180041c90  mov     r9, rsi
0x180041c93  movsxd  r10, edx
0x180041c96  test    r10, r10
0x180041c99  jz      short loc_180041CDC
0x180041c9b  cmp     r10, 40h ; '@'
0x180041c9f  jge     short loc_180041CFD
0x180041ca1  cmp     r10, 8
0x180041ca5  jl      short loc_180041CE4
0x180041ca7  lea     r8, [r10+r9]
0x180041cab  mov     rbx, [r10+rdi-8]
0x180041cb0  and     r8, 7
0x180041cb4  mov     [r10+r9-8], rbx
0x180041cb9  sub     r10, r8
0x180041cbc  sub     r10, 8
0x180041cc0  jl      short loc_180041CD0
0x180041cc2  mov     rbx, [r10+rdi]
0x180041cc6  mov     [r10+r9], rbx
0x180041cca  sub     r10, 8
0x180041cce  jge     short loc_180041CC2
0x180041cd0  add     r10, 8
0x180041cd4  jz      short loc_180041CDC
0x180041cd6  mov     rbx, [rdi]
0x180041cd9  mov     [r9], rbx
0x180041cdc  mov     rax, rsi
0x180041cdf  pop     rbp
0x180041ce0  pop     rbx
0x180041ce1  pop     rdi
0x180041ce2  pop     rsi
0x180041ce3  retn
0x180041ce4  movzx   ebx, byte ptr [r10+rdi-1]
0x180041cea  mov     [r10+r9-1], bl
0x180041cef  sub     r10, 1
0x180041cf3  jnz     short loc_180041CE4
0x180041cf5  mov     rax, rsi
0x180041cf8  pop     rbp
0x180041cf9  pop     rbx
0x180041cfa  pop     rdi
0x180041cfb  pop     rsi
0x180041cfc  retn
0x180041cfd  test    r9, 0Fh
0x180041d04  jnz     loc_180041DC1
0x180041d0a  cmp     r10, 80000h
0x180041d11  jge     loc_180041E49
0x180041d17  test    rdi, 0Fh
0x180041d1e  jnz     loc_180041DFE
0x180041d24  sub     r10, 40h ; '@'
0x180041d28  movdqa  xmm0, xmmword ptr [rdi]
0x180041d2c  movdqa  xmm1, xmmword ptr [rdi+10h]
0x180041d31  movdqa  xmm2, xmmword ptr [rdi+20h]
0x180041d36  movdqa  xmm3, xmmword ptr [rdi+30h]
0x180041d3b  add     rdi, 40h ; '@'
0x180041d3f  movdqa  xmmword ptr [r9], xmm0
0x180041d44  movdqa  xmmword ptr [r9+10h], xmm1
0x180041d4a  movdqa  xmmword ptr [r9+20h], xmm2
0x180041d50  movdqa  xmmword ptr [r9+30h], xmm3
0x180041d56  add     r9, 40h ; '@'
0x180041d5a  sub     r10, 40h ; '@'
0x180041d5e  jge     short loc_180041D28
0x180041d60  add     r10, 40h ; '@'
0x180041d64  jz      short loc_180041DB9
0x180041d66  sub     r10, 10h
0x180041d6a  jl      short loc_180041DAF
0x180041d6c  movdqa  xmm0, xmmword ptr [rdi]
0x180041d70  add     rdi, 10h
0x180041d74  movdqa  xmmword ptr [r9], xmm0
0x180041d79  add     r9, 10h
0x180041d7d  sub     r10, 10h
0x180041d81  jl      short loc_180041DAF
0x180041d83  movdqa  xmm0, xmmword ptr [rdi]
0x180041d87  add     rdi, 10h
0x180041d8b  movdqa  xmmword ptr [r9], xmm0
0x180041d90  add     r9, 10h
0x180041d94  sub     r10, 10h
0x180041d98  jl      short loc_180041DAF
0x180041d9a  movdqa  xmm0, xmmword ptr [rdi]
0x180041d9e  add     rdi, 10h
0x180041da2  movdqa  xmmword ptr [r9], xmm0
0x180041da7  add     r9, 10h
0x180041dab  sub     r10, 10h
0x180041daf  add     r10, 10h
0x180041db3  jnz     loc_180041CA1
0x180041db9  mov     rax, rsi
0x180041dbc  pop     rbp
0x180041dbd  pop     rbx
0x180041dbe  pop     rdi
0x180041dbf  pop     rsi
0x180041dc0  retn
0x180041dc1  movdqu  xmm0, xmmword ptr [rdi]
0x180041dc5  mov     rcx, r9
0x180041dc8  and     rcx, 0Fh
0x180041dcc  movdqu  xmmword ptr [r9], xmm0
0x180041dd1  sub     rcx, 10h
0x180041dd5  sub     rdi, rcx
0x180041dd8  sub     r9, rcx
0x180041ddb  add     r10, rcx
0x180041dde  cmp     r10, 40h ; '@'
0x180041de2  jl      loc_180041CA1
0x180041de8  test    rdi, 0Fh
0x180041def  jz      loc_180041D24
0x180041df5  cmp     r10, 80000h
0x180041dfc  jge     short loc_180041E49
0x180041dfe  sub     r10, 40h ; '@'
0x180041e02  lddqu   xmm0, xmmword ptr [rdi]
0x180041e06  movdqa  xmmword ptr [r9], xmm0
0x180041e0b  lddqu   xmm0, xmmword ptr [rdi+10h]
0x180041e10  movdqa  xmmword ptr [r9+10h], xmm0
0x180041e16  lddqu   xmm0, xmmword ptr [rdi+20h]
0x180041e1b  movdqa  xmmword ptr [r9+20h], xmm0
0x180041e21  lddqu   xmm0, xmmword ptr [rdi+30h]
0x180041e26  add     rdi, 40h ; '@'
0x180041e2a  movdqa  xmmword ptr [r9+30h], xmm0
0x180041e30  add     r9, 40h ; '@'
0x180041e34  sub     r10, 40h ; '@'
0x180041e38  jge     short loc_180041E02
0x180041e3a  add     r10, 40h ; '@'
0x180041e3e  jg      loc_180041CA1
0x180041e44  jmp     loc_180041CDC
0x180041e49  lea     rbx, qword_1800B4260
0x180041e50  sub     rsp, 48h
0x180041e54  mov     [rsp+48h+var_38], rax
0x180041e59  mov     [rsp+48h+var_30], rbx
0x180041e5e  mov     [rsp+48h+var_28], rcx
0x180041e63  mov     [rsp+48h+var_20], rdx
0x180041e68  mov     [rsp+48h+var_18], r8
0x180041e6d  mov     [rsp+48h+var_10], rbx
0x180041e72  xor     eax, eax
0x180041e74  cpuid
0x180041e76  cmp     ebx, 756E6547h
0x180041e7c  jnz     loc_180041F72
0x180041e82  cmp     edx, 49656E69h
0x180041e88  jnz     loc_180041F72
0x180041e8e  cmp     ecx, 6C65746Eh
0x180041e94  jnz     loc_180041F72
0x180041e9a  cmp     eax, 4
0x180041e9d  jl      short loc_180041EB5
0x180041e9f  mov     eax, 4
0x180041ea4  xor     ecx, ecx
0x180041ea6  cpuid
0x180041ea8  shr     eax, 1Ah
0x180041eab  add     eax, 1
0x180041eae  mov     [rsp+48h+var_8], rax
0x180041eb3  jmp     short loc_180041EBE
0x180041eb5  mov     [rsp+48h+var_8], 1
0x180041ebe  mov     eax, 2
0x180041ec3  cpuid
0x180041ec5  cmp     al, 1
0x180041ec7  jnz     loc_180041F72
0x180041ecd  test    eax, 80000000h
0x180041ed2  jz      short loc_180041ED6
0x180041ed4  xor     eax, eax
0x180041ed6  test    ebx, 80000000h
0x180041edc  jz      short loc_180041EE0
0x180041ede  xor     ebx, ebx
0x180041ee0  test    ecx, 80000000h
0x180041ee6  jz      short loc_180041EEA
0x180041ee8  xor     ecx, ecx
0x180041eea  test    edx, 80000000h
0x180041ef0  jz      short loc_180041EF4
0x180041ef2  xor     edx, edx
0x180041ef4  mov     r8, rsp
0x180041ef7  test    eax, eax
0x180041ef9  jz      short loc_180041F07
0x180041efb  mov     [r8], eax
0x180041efe  add     r8, 4
0x180041f02  mov     eax, 3
0x180041f07  test    ebx, ebx
0x180041f09  jz      short loc_180041F15
0x180041f0b  mov     [r8], ebx
0x180041f0e  add     r8, 4
0x180041f12  add     eax, 4
0x180041f15  test    ecx, ecx
0x180041f17  jz      short loc_180041F23
0x180041f19  mov     [r8], ecx
0x180041f1c  add     r8, 4
0x180041f20  add     eax, 4
0x180041f23  test    edx, edx
0x180041f25  jz      short loc_180041F2D
0x180041f27  mov     [r8], edx
0x180041f2a  add     eax, 4
0x180041f2d  mov     rbx, [rsp+48h+var_10]
0x180041f32  test    eax, eax
0x180041f34  jz      short loc_180041F72
0x180041f36  movzx   edx, byte ptr [rbx]
0x180041f39  test    edx, edx
0x180041f3b  jz      short loc_180041F72
0x180041f3d  add     rbx, 2
0x180041f41  mov     ecx, eax
0x180041f43  cmp     dl, byte ptr [rsp+rcx+48h+var_48]
0x180041f46  jz      short loc_180041F4F
0x180041f48  sub     ecx, 1
0x180041f4b  jnz     short loc_180041F43
0x180041f4d  jmp     short loc_180041F36
0x180041f4f  movzx   eax, byte ptr [rbx-1]
0x180041f53  mov     ecx, eax
0x180041f55  shr     eax, 4
0x180041f58  and     ecx, 0Fh
0x180041f5b  add     ecx, 12h
0x180041f5e  shl     rax, cl
0x180041f61  mov     rcx, [rsp+48h+var_8]
0x180041f66  xor     edx, edx
0x180041f68  div     rcx
0x180041f6b  mov     [rsp+48h+var_10], rax
0x180041f70  jmp     short loc_180041F7B
0x180041f72  mov     [rsp+48h+var_10], 0FFFFFFFFFFFFFFFFh
0x180041f7b  mov     rax, [rsp+48h+var_38]
0x180041f80  mov     rbx, [rsp+48h+var_30]
0x180041f85  mov     rcx, [rsp+48h+var_28]
0x180041f8a  mov     rdx, [rsp+48h+var_20]
0x180041f8f  mov     r8, [rsp+48h+var_18]
0x180041f94  mov     rbx, [rsp+48h+var_10]
0x180041f99  add     rsp, 48h
0x180041f9d  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180041fa1  jz      loc_180041D17
0x180041fa7  shr     rbx, 1
0x180041faa  cmp     r10, rbx
0x180041fad  jl      loc_180041D17
0x180041fb3  sub     r10, 40000h
0x180041fba  jl      short loc_180041FF8
0x180041fbc  mov     r8d, 800h
0x180041fc2  movzx   ebx, byte ptr [rdi]
0x180041fc5  add     rdi, 80h
0x180041fcc  sub     r8d, 1
0x180041fd0  jnz     short loc_180041FC2
0x180041fd2  sub     rdi, 40000h
0x180041fd9  mov     r8d, 40000h
0x180041fdf  movdqu  xmm0, xmmword ptr [rdi]
0x180041fe3  add     rdi, 10h
0x180041fe7  movntdq xmmword ptr [r9], xmm0
0x180041fec  add     r9, 10h
0x180041ff0  sub     r8d, 10h
0x180041ff4  jnz     short loc_180041FDF
0x180041ff6  jmp     short loc_180041FB3
0x180041ff8  add     r10, 40000h
0x180041fff  jz      short loc_180042046
0x180042001  mov     r8, r10
0x180042004  jmp     short loc_18004200B
0x180042006  movzx   ebx, byte ptr [r8+rdi]
0x18004200b  sub     r8, 80h
0x180042012  jge     short loc_180042006
0x180042014  sub     r10, 10h
0x180042018  jl      short loc_180042031
0x18004201a  movdqu  xmm0, xmmword ptr [rdi]
0x18004201e  add     rdi, 10h
0x180042022  movntdq xmmword ptr [r9], xmm0
0x180042027  add     r9, 10h
0x18004202b  sub     r10, 10h
0x18004202f  jge     short loc_18004201A
0x180042031  sfence
0x180042034  add     r10, 10h
0x180042038  jnz     loc_180041CA1
0x18004203e  mov     rax, rsi
0x180042041  pop     rbp
0x180042042  pop     rbx
0x180042043  pop     rdi
0x180042044  pop     rsi
0x180042045  retn
0x180042046  sfence
0x180042049  jmp     short loc_18004203E
```
