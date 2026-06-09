# LibRaw::copy_line_to_bayer(fuji_compressed_block *,int,int,int)

- ea: `0x180012240`
- end: `0x1800123eb`
- name: `?copy_line_to_bayer@LibRaw@@IEAAXPEAUfuji_compressed_block@@HHH@Z`
- size: `427`
- prototype: `void __fastcall(LibRaw *__hidden this, struct fuji_compressed_block *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180013a50`

## callees

- `0x180012240`

## pseudocode

```c
void __fastcall LibRaw::copy_line_to_bayer(
        LibRaw *this,
        struct fuji_compressed_block *a2,
        int a3,
        int a4,
        unsigned int a5)
{
  unsigned int v5; // r10d
  __m128i si128; // xmm2
  int v7; // r9d
  __int64 v9; // rbp
  int v10; // eax
  int v11; // ecx
  __int64 v12; // rax
  __m128i v13; // xmm1
  __m128i v14; // xmm0
  _WORD *v15; // r14
  __int64 *v16; // r11
  __int64 v17; // rsi
  _WORD *v18; // r8
  unsigned __int64 v19; // rdx
  __int64 v20; // r9
  int v21; // eax
  __int64 v22; // rcx
  unsigned __int64 v23; // rax
  _DWORD v24[4]; // [rsp+0h] [rbp-A8h]
  __m128i v25; // [rsp+10h] [rbp-98h]
  __int64 v26; // [rsp+20h] [rbp-88h]
  __m128i v27; // [rsp+28h] [rbp-80h]
  __int64 v28; // [rsp+38h] [rbp-70h]
  _OWORD v29[6]; // [rsp+40h] [rbp-68h] BYREF

  v5 = *((_DWORD *)this + 136);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v7 = *((_DWORD *)this + 95393) * a4;
  v24[0] = v5 & 3;
  v9 = 6;
  v24[1] = (v5 >> 2) & 3;
  v24[3] = (unsigned __int8)v5 >> 6;
  v24[2] = (v5 >> 4) & 3;
  v10 = a3 * *((unsigned __int16 *)this + 9);
  v27 = _mm_add_epi64(_mm_loadu_si128((const __m128i *)((char *)a2 + 2760)), si128);
  v25 = _mm_add_epi64(_mm_loadu_si128((const __m128i *)a2 + 179), si128);
  v11 = v7 + 6 * v10;
  v12 = *((_QWORD *)this + 24190);
  v13 = _mm_add_epi64(_mm_loadu_si128((const __m128i *)a2 + 176), si128);
  v29[0] = _mm_add_epi64(_mm_loadu_si128((const __m128i *)a2 + 175), si128);
  v14 = _mm_loadu_si128((const __m128i *)a2 + 177);
  v29[1] = v13;
  v15 = (_WORD *)(v12 + 2LL * v11);
  v28 = *((_QWORD *)a2 + 347) + 2LL;
  v16 = (__int64 *)v29;
  v26 = *((_QWORD *)a2 + 360) + 2LL;
  v17 = 0;
  v29[2] = _mm_add_epi64(v14, si128);
  do
  {
    if ( a5 )
    {
      v18 = v15;
      v19 = 0;
      v20 = a5;
      do
      {
        v21 = v24[2 * (v17 & 1) + (v19 & 1)];
        if ( v21 )
        {
          if ( v21 == 2 )
            v22 = v25.m128i_i64[v17 >> 1];
          else
            v22 = *v16;
        }
        else
        {
          v22 = v27.m128i_i64[v17 >> 1];
        }
        v23 = v19++;
        *v18++ = *(_WORD *)(v22 + 2 * (v23 >> 1));
        --v20;
      }
      while ( v20 );
    }
    ++v17;
    ++v16;
    v15 += *((unsigned __int16 *)this + 9);
    --v9;
  }
  while ( v9 );
}

```

## disassembly

```asm
0x180012240  push    rbx
0x180012242  push    rbp
0x180012243  push    rsi
0x180012244  push    rdi
0x180012245  push    r13
0x180012247  push    r14
0x180012249  push    r15
0x18001224b  sub     rsp, 70h
0x18001224f  mov     r10d, [rcx+220h]
0x180012256  mov     r11, rdx
0x180012259  movdqa  xmm2, cs:__xmm@00000000000000020000000000000002
0x180012261  mov     eax, r10d
0x180012264  imul    r9d, [rcx+5D284h]
0x18001226c  and     eax, 3
0x18001226f  mov     r15d, [rsp+0A8h+arg_20]
0x180012277  mov     r13, rcx
0x18001227a  movdqu  xmm0, xmmword ptr [r11+0AC8h]
0x180012283  mov     [rsp+0A8h+var_A8], eax
0x180012286  mov     eax, r10d
0x180012289  movdqu  xmm1, xmmword ptr [r11+0B30h]
0x180012292  shr     eax, 2
0x180012295  mov     ebp, 6
0x18001229a  and     eax, 3
0x18001229d  paddq   xmm0, xmm2
0x1800122a1  mov     [rsp+0A8h+var_A4], eax
0x1800122a5  paddq   xmm1, xmm2
0x1800122a9  mov     eax, r10d
0x1800122ac  shr     r10d, 6
0x1800122b0  shr     eax, 4
0x1800122b3  and     r10d, 3
0x1800122b7  and     eax, 3
0x1800122ba  mov     [rsp+0A8h+var_9C], r10d
0x1800122bf  mov     [rsp+0A8h+var_A0], eax
0x1800122c3  movzx   eax, word ptr [rcx+12h]
0x1800122c7  imul    eax, r8d
0x1800122cb  movdqu  [rsp+0A8h+var_80], xmm0
0x1800122d1  movdqu  xmm0, xmmword ptr [r11+0AF0h]
0x1800122da  movdqu  [rsp+0A8h+var_98], xmm1
0x1800122e0  movdqu  xmm1, xmmword ptr [r11+0B00h]
0x1800122e9  lea     eax, [rax+rax*2]
0x1800122ec  lea     ecx, [r9+rax*2]
0x1800122f0  paddq   xmm0, xmm2
0x1800122f4  mov     rax, [r13+2F3F0h]
0x1800122fb  paddq   xmm1, xmm2
0x1800122ff  movdqu  [rsp+0A8h+var_68], xmm0
0x180012305  movsxd  rdx, ecx
0x180012308  movdqu  xmm0, xmmword ptr [r11+0B10h]
0x180012311  movdqu  [rsp+0A8h+var_58], xmm1
0x180012317  lea     r14, [rax+rdx*2]
0x18001231b  mov     rax, [r11+0AD8h]
0x180012322  add     rax, 2
0x180012326  paddq   xmm0, xmm2
0x18001232a  mov     [rsp+0A8h+var_70], rax
0x18001232f  mov     rax, [r11+0B40h]
0x180012336  lea     r11, [rsp+0A8h+var_68]
0x18001233b  add     rax, 2
0x18001233f  mov     [rsp+0A8h+var_88], rax
0x180012344  xor     esi, esi
0x180012346  movdqu  [rsp+0A8h+var_48], xmm0
0x18001234c  nop     dword ptr [rax+00h]
0x180012350  test    r15d, r15d
0x180012353  jz      short loc_1800123C2
0x180012355  mov     r10, rsi
0x180012358  lea     rbx, [rsp+0A8h+var_98]
0x18001235d  and     r10d, 1
0x180012361  lea     rdi, [rsp+0A8h+var_80]
0x180012366  mov     rax, rsi
0x180012369  add     r10, r10
0x18001236c  sar     rax, 1
0x18001236f  mov     r8, r14
0x180012372  xor     edx, edx
0x180012374  mov     r9, r15
0x180012377  lea     rbx, [rbx+rax*8]
0x18001237b  lea     rdi, [rdi+rax*8]
0x18001237f  nop
0x180012380  mov     rcx, rdx
0x180012383  and     ecx, 1
0x180012386  add     rcx, r10
0x180012389  mov     eax, [rsp+rcx*4+0A8h+var_A8]
0x18001238c  test    eax, eax
0x18001238e  jz      short loc_1800123A4
0x180012390  sub     eax, 1
0x180012393  jz      short loc_18001239F
0x180012395  cmp     eax, 1
0x180012398  jnz     short loc_18001239F
0x18001239a  mov     rcx, [rbx]
0x18001239d  jmp     short loc_1800123A7
0x18001239f  mov     rcx, [r11]
0x1800123a2  jmp     short loc_1800123A7
0x1800123a4  mov     rcx, [rdi]
0x1800123a7  mov     rax, rdx
0x1800123aa  inc     rdx
0x1800123ad  shr     rax, 1
0x1800123b0  movzx   eax, word ptr [rcx+rax*2]
0x1800123b4  mov     [r8], ax
0x1800123b8  add     r8, 2
0x1800123bc  sub     r9, 1
0x1800123c0  jnz     short loc_180012380
0x1800123c2  movzx   eax, word ptr [r13+12h]
0x1800123c7  inc     rsi
0x1800123ca  add     r11, 8
0x1800123ce  lea     r14, [r14+rax*2]
0x1800123d2  sub     rbp, 1
0x1800123d6  jnz     loc_180012350
0x1800123dc  add     rsp, 70h
0x1800123e0  pop     r15
0x1800123e2  pop     r14
0x1800123e4  pop     r13
0x1800123e6  pop     rdi
0x1800123e7  pop     rsi
0x1800123e8  pop     rbp
0x1800123e9  pop     rbx
0x1800123ea  retn
```
