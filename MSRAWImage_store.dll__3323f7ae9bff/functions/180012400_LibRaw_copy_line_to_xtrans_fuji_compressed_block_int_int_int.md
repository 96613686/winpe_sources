# LibRaw::copy_line_to_xtrans(fuji_compressed_block *,int,int,int)

- ea: `0x180012400`
- end: `0x1800125cf`
- name: `?copy_line_to_xtrans@LibRaw@@IEAAXPEAUfuji_compressed_block@@HHH@Z`
- size: `463`
- prototype: `void __fastcall(LibRaw *this, struct fuji_compressed_block *, int, int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180013a50`

## callees

- `0x180012400`

## pseudocode

```c
void __fastcall LibRaw::copy_line_to_xtrans(
        LibRaw *this,
        struct fuji_compressed_block *a2,
        int a3,
        int a4,
        unsigned int a5)
{
  __m128i si128; // xmm2
  __int64 *v6; // rbx
  int v7; // r9d
  __int64 v9; // rdi
  int v10; // eax
  int v11; // ecx
  __int64 v12; // rax
  __m128i v13; // xmm1
  _WORD *v14; // r12
  __m128i v15; // xmm0
  __int64 v16; // r13
  unsigned int v17; // r8d
  unsigned int v18; // r10d
  _WORD *v19; // r11
  __int64 v20; // rcx
  __int64 v21; // r9
  unsigned int v22; // kr00_4
  unsigned int v23; // kr04_4
  bool v24; // zf
  __int64 v25; // [rsp+0h] [rbp-A8h]
  __m128i v26; // [rsp+8h] [rbp-A0h]
  __int64 v27; // [rsp+18h] [rbp-90h]
  __m128i v28; // [rsp+20h] [rbp-88h]
  __int64 v29; // [rsp+30h] [rbp-78h]
  _OWORD v30[7]; // [rsp+38h] [rbp-70h] BYREF

  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v6 = (__int64 *)v30;
  v7 = *((_DWORD *)this + 95393) * a4;
  v9 = 0;
  v10 = a3 * *((unsigned __int16 *)this + 9);
  v25 = 6;
  v28 = _mm_add_epi64(_mm_loadu_si128((const __m128i *)((char *)a2 + 2760)), si128);
  v11 = v7 + 6 * v10;
  v12 = *((_QWORD *)this + 24190);
  v26 = _mm_add_epi64(_mm_loadu_si128((const __m128i *)a2 + 179), si128);
  v13 = _mm_loadu_si128((const __m128i *)a2 + 176);
  v30[0] = _mm_add_epi64(_mm_loadu_si128((const __m128i *)a2 + 175), si128);
  v14 = (_WORD *)(v12 + 2LL * v11);
  v29 = *((_QWORD *)a2 + 347) + 2LL;
  v15 = _mm_add_epi64(_mm_loadu_si128((const __m128i *)a2 + 177), si128);
  v27 = *((_QWORD *)a2 + 360) + 2LL;
  v16 = 0;
  v30[1] = _mm_add_epi64(v13, si128);
  v30[2] = v15;
  do
  {
    v17 = 0;
    if ( a5 )
    {
      v18 = 0;
      v19 = v14;
      do
      {
        v20 = v9 + v17 % 6;
        if ( *((_BYTE *)this + v20 + 584) )
        {
          if ( *((_BYTE *)this + v20 + 584) == 2 )
            v21 = v26.m128i_i64[v16 >> 1];
          else
            v21 = *v6;
        }
        else
        {
          v21 = v28.m128i_i64[v16 >> 1];
        }
        v22 = v17++;
        v23 = v18;
        v18 += 2;
        *v19++ = *(_WORD *)(v21 + 2LL * (int)(((v22 % 3) >> 1) + ((v23 / 3) & 0x7FFFFFFE | (v22 % 3) & 1)));
      }
      while ( v17 < a5 );
    }
    ++v16;
    ++v6;
    v9 += 6;
    v24 = v25-- == 1;
    v14 += *((unsigned __int16 *)this + 9);
  }
  while ( !v24 );
}

```

## disassembly

```asm
0x180012400  mov     [rsp+arg_8], rbx
0x180012405  push    rbp
0x180012406  push    rsi
0x180012407  push    rdi
0x180012408  push    r12
0x18001240a  push    r13
0x18001240c  push    r14
0x18001240e  push    r15
0x180012410  sub     rsp, 70h
0x180012414  movdqa  xmm2, cs:__xmm@00000000000000020000000000000002
0x18001241c  lea     rbx, [rsp+0A8h+var_70]
0x180012421  movzx   eax, word ptr [rcx+12h]
0x180012425  mov     r10, rdx
0x180012428  imul    r9d, [rcx+5D284h]
0x180012430  mov     rbp, rcx
0x180012433  mov     r15d, [rsp+0A8h+arg_20]
0x18001243b  xor     edi, edi
0x18001243d  imul    eax, r8d
0x180012441  movdqu  xmm0, xmmword ptr [r10+0AC8h]
0x18001244a  mov     [rsp+0A8h+var_A8], 6
0x180012452  movdqu  xmm1, xmmword ptr [r10+0B30h]
0x18001245b  paddq   xmm0, xmm2
0x18001245f  movdqu  [rsp+0A8h+var_88], xmm0
0x180012465  movdqu  xmm0, xmmword ptr [r10+0AF0h]
0x18001246e  lea     eax, [rax+rax*2]
0x180012471  lea     ecx, [r9+rax*2]
0x180012475  paddq   xmm1, xmm2
0x180012479  mov     rax, [rbp+2F3F0h]
0x180012480  paddq   xmm0, xmm2
0x180012484  movdqu  [rsp+0A8h+var_A0], xmm1
0x18001248a  movsxd  rdx, ecx
0x18001248d  movdqu  xmm1, xmmword ptr [r10+0B00h]
0x180012496  movdqu  [rsp+0A8h+var_70], xmm0
0x18001249c  lea     r12, [rax+rdx*2]
0x1800124a0  mov     rax, [r10+0AD8h]
0x1800124a7  movdqu  xmm0, xmmword ptr [r10+0B10h]
0x1800124b0  add     rax, 2
0x1800124b4  mov     [rsp+0A8h+var_78], rax
0x1800124b9  paddq   xmm1, xmm2
0x1800124bd  mov     rax, [r10+0B40h]
0x1800124c4  paddq   xmm0, xmm2
0x1800124c8  add     rax, 2
0x1800124cc  mov     [rsp+0A8h+var_90], rax
0x1800124d1  xor     r13d, r13d
0x1800124d4  movdqu  [rsp+0A8h+var_60], xmm1
0x1800124da  movdqu  [rsp+0A8h+var_50], xmm0
0x1800124e0  xor     r8d, r8d
0x1800124e3  test    r15d, r15d
0x1800124e6  jz      loc_180012599
0x1800124ec  mov     rax, r13
0x1800124ef  lea     rsi, [rsp+0A8h+var_A0]
0x1800124f4  sar     rax, 1
0x1800124f7  lea     r14, [rsp+0A8h+var_88]
0x1800124fc  xor     r10d, r10d
0x1800124ff  mov     r11, r12
0x180012502  lea     rsi, [rsi+rax*8]
0x180012506  lea     r14, [r14+rax*8]
0x18001250a  nop     word ptr [rax+rax+00h]
0x180012510  mov     eax, 0AAAAAAABh
0x180012515  mul     r8d
0x180012518  mov     eax, r8d
0x18001251b  shr     edx, 2
0x18001251e  lea     ecx, [rdx+rdx*2]
0x180012521  add     ecx, ecx
0x180012523  sub     eax, ecx
0x180012525  mov     ecx, eax
0x180012527  add     rcx, rdi
0x18001252a  movsx   eax, byte ptr [rcx+rbp+248h]
0x180012532  test    eax, eax
0x180012534  jz      short loc_18001254A
0x180012536  sub     eax, 1
0x180012539  jz      short loc_180012545
0x18001253b  cmp     eax, 1
0x18001253e  jnz     short loc_180012545
0x180012540  mov     r9, [rsi]
0x180012543  jmp     short loc_18001254D
0x180012545  mov     r9, [rbx]
0x180012548  jmp     short loc_18001254D
0x18001254a  mov     r9, [r14]
0x18001254d  mov     eax, 0AAAAAAABh
0x180012552  mov     ecx, r8d
0x180012555  mul     r8d
0x180012558  inc     r8d
0x18001255b  shr     edx, 1
0x18001255d  lea     eax, [rdx+rdx*2]
0x180012560  sub     ecx, eax
0x180012562  mov     eax, 0AAAAAAABh
0x180012567  mul     r10d
0x18001256a  mov     eax, ecx
0x18001256c  add     r10d, 2
0x180012570  and     eax, 1
0x180012573  shr     ecx, 1
0x180012575  shr     edx, 1
0x180012577  and     edx, 7FFFFFFEh
0x18001257d  or      eax, edx
0x18001257f  add     eax, ecx
0x180012581  cdqe
0x180012583  movzx   ecx, word ptr [r9+rax*2]
0x180012588  mov     [r11], cx
0x18001258c  add     r11, 2
0x180012590  cmp     r8d, r15d
0x180012593  jb      loc_180012510
0x180012599  movzx   eax, word ptr [rbp+12h]
0x18001259d  inc     r13
0x1800125a0  add     rbx, 8
0x1800125a4  add     rdi, 6
0x1800125a8  sub     [rsp+0A8h+var_A8], 1
0x1800125ad  lea     r12, [r12+rax*2]
0x1800125b1  jnz     loc_1800124E0
0x1800125b7  mov     rbx, [rsp+0A8h+arg_8]
0x1800125bf  add     rsp, 70h
0x1800125c3  pop     r15
0x1800125c5  pop     r14
0x1800125c7  pop     r13
0x1800125c9  pop     r12
0x1800125cb  pop     rdi
0x1800125cc  pop     rsi
0x1800125cd  pop     rbp
0x1800125ce  retn
```
