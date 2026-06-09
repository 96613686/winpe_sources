# CAudioTimeCompression::ProcessInput(int,uchar *)

- ea: `0x18004f4c0`
- end: `0x18004f7ef`
- name: `?ProcessInput@CAudioTimeCompression@@QEAAJHPEAE@Z`
- size: `815`
- prototype: `__int64 __fastcall(CAudioTimeCompression *__hidden this, int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18004f800`

## callees

- `0x180001360`
- `0x18004ed70`
- `0x18004f210`
- `0x18004f4c0`
- `0x18004fbb0`
- `0x18004ff10`
- `0x1800504f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f7cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f7cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f4ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f4ea`

## pseudocode

```c
__int64 __fastcall CAudioTimeCompression::ProcessInput(CAudioTimeCompression *this, int a2, unsigned __int8 *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  int v7; // esi
  _DWORD *v8; // rcx
  int v9; // eax
  int *v10; // rcx
  int v11; // r10d
  __int64 v12; // rdx
  int v13; // eax
  unsigned __int8 *v14; // r8
  int *v15; // rdx
  __int64 v16; // r11
  __int64 v17; // rsi
  __m128d v18; // xmm0
  int v19; // ecx
  __int64 v20; // r8
  int *v21; // r9
  __int64 i; // r10
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 v26; // rbp
  __int64 v27; // rcx
  __int64 v28; // rdx
  unsigned __int8 *v29; // r8
  __m128d v30; // xmm0
  int v31; // ecx
  __int64 v33; // [rsp+70h] [rbp+8h] BYREF
  char *v34; // [rsp+88h] [rbp+20h]

  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 224);
  v34 = (char *)this + 224;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  if ( !*((_BYTE *)this + 22) )
  {
    v7 = CAudioTimeCompression::Start(this);
    if ( v7 < 0 )
      goto LABEL_34;
  }
  if ( a2 > 49152 )
  {
    v7 = -2147024809;
    goto LABEL_34;
  }
  v7 = Chunk::Append(*((Chunk **)this + 10), a2 / *((unsigned __int16 *)this + 8), a3, *((_DWORD *)this + 18));
  if ( v7 < 0 )
    goto LABEL_34;
  if ( *((_QWORD *)this + 11) )
  {
LABEL_10:
    v10 = (int *)*((_QWORD *)this + 11);
    if ( !(*(_QWORD *)v10 + v10[2]) )
    {
      v11 = *((_DWORD *)this + 13);
      v12 = *((_QWORD *)this + 10);
      v13 = *(_DWORD *)(v12 + 8);
      if ( v13 < v11 )
        goto LABEL_33;
      if ( v13 <= 0 )
        v14 = 0;
      else
        v14 = *(unsigned __int8 **)(v12 + 24);
      v7 = Chunk::Append((Chunk *)v10, v11, v14, 0);
      if ( v7 < 0 )
        goto LABEL_34;
      *((_QWORD *)this + 13) += *((int *)this + 19);
      *((_QWORD *)this + 27) = 0;
    }
    v15 = (int *)*((_QWORD *)this + 11);
    v16 = *((int *)this + 14);
    v17 = *(_QWORD *)v15 + v15[2] - v16;
    v18 = 0;
    v18.m128d_f64[0] = (double)(int)v17 * *((double *)this + 3);
    v19 = (int)v18.m128d_f64[0];
    if ( (double)v19 != v18.m128d_f64[0] )
      v18.m128d_f64[0] = (double)(!(_mm_movemask_pd(_mm_unpacklo_pd(v18, v18)) & 1) + v19);
    v20 = (unsigned int)(int)v18.m128d_f64[0];
    v33 = v20;
    v21 = (int *)*((_QWORD *)this + 10);
    for ( i = *((int *)this + 16); v20 + i + *((int *)this + 13) <= *(_QWORD *)v21 + v21[2]; i = *((int *)this + 16) )
    {
      v23 = v20 - (int)i;
      v24 = (int)i + v20;
      v25 = 0;
      if ( v23 >= 0 )
        v25 = v23;
      CAudioTimeCompression::findMaxCorrelationFFT2(
        this,
        (struct Chunk *)v15,
        v17,
        (struct Chunk *)v21,
        v25,
        v24,
        &v33,
        v16);
      v26 = v33;
      CAudioTimeCompression::blend(
        this,
        *((struct Chunk **)this + 10),
        v33,
        *((struct Chunk **)this + 11),
        v17,
        *((_DWORD *)this + 14));
      v27 = *((_QWORD *)this + 10);
      v28 = v26 + *((int *)this + 14) - *(_QWORD *)v27;
      if ( v28 < 0 || v28 >= *(int *)(v27 + 8) )
        v29 = 0;
      else
        v29 = (unsigned __int8 *)(*(_QWORD *)(v27 + 24) + v28 * *(int *)(v27 + 12));
      v7 = Chunk::Append(
             *((Chunk **)this + 11),
             *((_DWORD *)this + 19),
             v29,
             **((_DWORD **)this + 11) + *(_DWORD *)(*((_QWORD *)this + 11) + 8LL) - *((_DWORD *)this + 24));
      if ( v7 < 0 )
        goto LABEL_34;
      *((_QWORD *)this + 13) += *((int *)this + 19);
      *((_QWORD *)this + 27) = v26;
      v15 = (int *)*((_QWORD *)this + 11);
      v16 = *((int *)this + 14);
      v17 = *(_QWORD *)v15 + v15[2] - v16;
      v30 = 0;
      v30.m128d_f64[0] = (double)(int)v17 * *((double *)this + 3);
      v31 = (int)v30.m128d_f64[0];
      if ( (double)v31 != v30.m128d_f64[0] )
        v30.m128d_f64[0] = (double)(!(_mm_movemask_pd(_mm_unpacklo_pd(v30, v30)) & 1) + v31);
      v20 = (unsigned int)(int)v30.m128d_f64[0];
      v33 = v20;
      v21 = (int *)*((_QWORD *)this + 10);
    }
LABEL_33:
    v7 = 0;
    goto LABEL_34;
  }
  v8 = operator new(0x20u);
  v33 = (__int64)v8;
  if ( !v8 )
  {
    *((_QWORD *)this + 11) = 0;
    v7 = -2147024882;
    goto LABEL_34;
  }
  v9 = *((unsigned __int16 *)this + 8);
  *(_QWORD *)v8 = 0;
  v8[2] = 0;
  v8[3] = v9;
  v8[4] = 24522 * v9;
  *((_QWORD *)v8 + 3) = 0;
  *((_QWORD *)this + 11) = v8;
  v7 = Chunk::Init((Chunk *)v8);
  if ( v7 >= 0 )
  {
    *((_QWORD *)this + 12) = 0;
    *((_QWORD *)this + 13) = 0;
    goto LABEL_10;
  }
LABEL_34:
  LeaveCriticalSection(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004f4c0  mov     [rsp+arg_8], rbx
0x18004f4c5  push    rbp
0x18004f4c6  push    rsi
0x18004f4c7  push    rdi
0x18004f4c8  push    r14
0x18004f4ca  push    r15
0x18004f4cc  sub     rsp, 40h
0x18004f4d0  mov     r14, r8
0x18004f4d3  mov     ebp, edx
0x18004f4d5  mov     rdi, rcx
0x18004f4d8  lea     rbx, [rcx+0E0h]
0x18004f4df  mov     [rsp+68h+arg_18], rbx
0x18004f4e7  mov     rcx, rbx; lpCriticalSection
0x18004f4ea  call    cs:__imp_EnterCriticalSection
0x18004f4f1  nop     dword ptr [rax+rax+00h]
0x18004f4f6  nop
0x18004f4f7  cmp     byte ptr [rdi+16h], 0
0x18004f4fb  jnz     short loc_18004F50F
0x18004f4fd  mov     rcx, rdi; this
0x18004f500  call    ?Start@CAudioTimeCompression@@IEAAJXZ; CAudioTimeCompression::Start(void)
0x18004f505  mov     esi, eax
0x18004f507  test    eax, eax
0x18004f509  js      loc_18004F7CC
0x18004f50f  cmp     ebp, 0C000h
0x18004f515  jle     short loc_18004F521
0x18004f517  mov     esi, 80070057h
0x18004f51c  jmp     loc_18004F7CC
0x18004f521  movzx   ecx, word ptr [rdi+10h]
0x18004f525  mov     eax, ebp
0x18004f527  cdq
0x18004f528  idiv    ecx
0x18004f52a  mov     edx, eax; int
0x18004f52c  mov     r9d, [rdi+48h]; int
0x18004f530  mov     r8, r14; unsigned __int8 *
0x18004f533  mov     rcx, [rdi+50h]; this
0x18004f537  call    ?Append@Chunk@@QEAAJHPEAEH@Z; Chunk::Append(int,uchar *,int)
0x18004f53c  mov     esi, eax
0x18004f53e  test    eax, eax
0x18004f540  js      loc_18004F7CC
0x18004f546  xor     r14d, r14d
0x18004f549  cmp     [rdi+58h], r14
0x18004f54d  jnz     short loc_18004F5A1
0x18004f54f  mov     ecx, 20h ; ' '; Size
0x18004f554  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004f559  mov     rcx, rax; this
0x18004f55c  mov     [rsp+68h+arg_0], rax
0x18004f561  test    rax, rax
0x18004f564  jz      short loc_18004F5CC
0x18004f566  movzx   eax, word ptr [rdi+10h]
0x18004f56a  mov     [rcx], r14
0x18004f56d  mov     [rcx+8], r14d
0x18004f571  mov     [rcx+0Ch], eax
0x18004f574  imul    eax, 5FCAh
0x18004f57a  mov     [rcx+10h], eax
0x18004f57d  mov     [rcx+18h], r14
0x18004f581  mov     [rdi+58h], rcx
0x18004f585  test    rcx, rcx
0x18004f588  jz      short loc_18004F5D0
0x18004f58a  call    ?Init@Chunk@@QEAAJXZ; Chunk::Init(void)
0x18004f58f  mov     esi, eax
0x18004f591  test    eax, eax
0x18004f593  js      loc_18004F7CC
0x18004f599  mov     [rdi+60h], r14
0x18004f59d  mov     [rdi+68h], r14
0x18004f5a1  mov     rcx, [rdi+58h]; this
0x18004f5a5  movsxd  rax, dword ptr [rcx+8]
0x18004f5a9  add     rax, [rcx]
0x18004f5ac  jnz     short loc_18004F601
0x18004f5ae  mov     r10d, [rdi+34h]
0x18004f5b2  mov     rdx, [rdi+50h]
0x18004f5b6  mov     eax, [rdx+8]
0x18004f5b9  cmp     eax, r10d
0x18004f5bc  jl      loc_18004F7C9
0x18004f5c2  test    eax, eax
0x18004f5c4  jle     short loc_18004F5DA
0x18004f5c6  mov     r8, [rdx+18h]
0x18004f5ca  jmp     short loc_18004F5DD
0x18004f5cc  mov     [rdi+58h], r14
0x18004f5d0  mov     esi, 8007000Eh
0x18004f5d5  jmp     loc_18004F7CC
0x18004f5da  mov     r8, r14; unsigned __int8 *
0x18004f5dd  xor     r9d, r9d; int
0x18004f5e0  mov     edx, r10d; int
0x18004f5e3  call    ?Append@Chunk@@QEAAJHPEAEH@Z; Chunk::Append(int,uchar *,int)
0x18004f5e8  mov     esi, eax
0x18004f5ea  test    eax, eax
0x18004f5ec  js      loc_18004F7CC
0x18004f5f2  movsxd  rax, dword ptr [rdi+4Ch]
0x18004f5f6  add     [rdi+68h], rax
0x18004f5fa  mov     [rdi+0D8h], r14
0x18004f601  mov     rdx, [rdi+58h]; struct Chunk *
0x18004f605  movsxd  r11, dword ptr [rdi+38h]
0x18004f609  movsxd  rsi, dword ptr [rdx+8]
0x18004f60d  sub     rsi, r11
0x18004f610  add     rsi, [rdx]
0x18004f613  xorps   xmm0, xmm0
0x18004f616  cvtsi2sd xmm0, rsi
0x18004f61b  mulsd   xmm0, qword ptr [rdi+18h]
0x18004f620  cvttsd2si rcx, xmm0
0x18004f625  xorps   xmm1, xmm1
0x18004f628  mov     r15, 8000000000000000h
0x18004f632  cmp     rcx, r15
0x18004f635  jz      short loc_18004F65E
0x18004f637  xorps   xmm1, xmm1
0x18004f63a  cvtsi2sd xmm1, rcx
0x18004f63f  ucomisd xmm1, xmm0
0x18004f643  jz      short loc_18004F65E
0x18004f645  unpcklpd xmm0, xmm0
0x18004f649  movmskpd eax, xmm0
0x18004f64d  and     eax, 1
0x18004f650  xor     eax, 1
0x18004f653  add     rcx, rax
0x18004f656  xorps   xmm0, xmm0
0x18004f659  cvtsi2sd xmm0, rcx
0x18004f65e  cvttsd2si r8, xmm0
0x18004f663  mov     [rsp+68h+arg_0], r8
0x18004f668  mov     r9, [rdi+50h]; struct Chunk *
0x18004f66c  movsxd  r10, dword ptr [rdi+40h]
0x18004f670  movsxd  rcx, dword ptr [rdi+34h]
0x18004f674  lea     rax, [r8+r10]
0x18004f678  add     rcx, rax
0x18004f67b  movsxd  rax, dword ptr [r9+8]
0x18004f67f  add     rax, [r9]
0x18004f682  cmp     rcx, rax
0x18004f685  jg      loc_18004F7C9
0x18004f68b  nop     dword ptr [rax+rax+00h]
0x18004f690  movsxd  rax, r10d
0x18004f693  mov     rcx, r8
0x18004f696  sub     rcx, rax
0x18004f699  lea     r8, [rax+r8]
0x18004f69d  mov     rax, r14
0x18004f6a0  cmovns  rax, rcx
0x18004f6a4  mov     [rsp+68h+var_30], r11d; int
0x18004f6a9  lea     rcx, [rsp+68h+arg_0]
0x18004f6ae  mov     [rsp+68h+var_38], rcx; __int64 *
0x18004f6b3  mov     [rsp+68h+var_40], r8; __int64
0x18004f6b8  mov     [rsp+68h+var_48], rax; __int64
0x18004f6bd  mov     r8, rsi; __int64
0x18004f6c0  mov     rcx, rdi; this
0x18004f6c3  call    ?findMaxCorrelationFFT2@CAudioTimeCompression@@IEAAJPEAVChunk@@_J0_J2PEA_JH@Z; CAudioTimeCompression::findMaxCorrelationFFT2(Chunk *,__int64,Chunk *,__int64,__int64,__int64 *,int)
0x18004f6c8  mov     eax, [rdi+38h]
0x18004f6cb  mov     dword ptr [rsp+68h+var_40], eax; int
0x18004f6cf  mov     [rsp+68h+var_48], rsi; __int64
0x18004f6d4  mov     r9, [rdi+58h]; struct Chunk *
0x18004f6d8  mov     rbp, [rsp+68h+arg_0]
0x18004f6dd  mov     r8, rbp; __int64
0x18004f6e0  mov     rdx, [rdi+50h]; struct Chunk *
0x18004f6e4  mov     rcx, rdi; this
0x18004f6e7  call    ?blend@CAudioTimeCompression@@IEAAXPEAVChunk@@_J01H@Z; CAudioTimeCompression::blend(Chunk *,__int64,Chunk *,__int64,int)
0x18004f6ec  mov     r10, [rdi+58h]
0x18004f6f0  mov     r9d, [r10+8]
0x18004f6f4  sub     r9d, [rdi+60h]
0x18004f6f8  add     r9d, [r10]; int
0x18004f6fb  mov     rcx, [rdi+50h]
0x18004f6ff  movsxd  rdx, dword ptr [rdi+38h]
0x18004f703  sub     rdx, [rcx]
0x18004f706  add     rdx, rbp
0x18004f709  js      short loc_18004F722
0x18004f70b  movsxd  rax, dword ptr [rcx+8]
0x18004f70f  cmp     rdx, rax
0x18004f712  jge     short loc_18004F722
0x18004f714  movsxd  r8, dword ptr [rcx+0Ch]
0x18004f718  imul    r8, rdx
0x18004f71c  add     r8, [rcx+18h]
0x18004f720  jmp     short loc_18004F725
0x18004f722  mov     r8, r14; unsigned __int8 *
0x18004f725  mov     edx, [rdi+4Ch]; int
0x18004f728  mov     rcx, r10; this
0x18004f72b  call    ?Append@Chunk@@QEAAJHPEAEH@Z; Chunk::Append(int,uchar *,int)
0x18004f730  mov     esi, eax
0x18004f732  test    eax, eax
0x18004f734  js      loc_18004F7CC
0x18004f73a  movsxd  rax, dword ptr [rdi+4Ch]
0x18004f73e  add     [rdi+68h], rax
0x18004f742  mov     [rdi+0D8h], rbp
0x18004f749  mov     rdx, [rdi+58h]
0x18004f74d  movsxd  r11, dword ptr [rdi+38h]
0x18004f751  movsxd  rsi, dword ptr [rdx+8]
0x18004f755  sub     rsi, r11
0x18004f758  add     rsi, [rdx]
0x18004f75b  xorps   xmm0, xmm0
0x18004f75e  cvtsi2sd xmm0, rsi
0x18004f763  mulsd   xmm0, qword ptr [rdi+18h]
0x18004f768  cvttsd2si rcx, xmm0
0x18004f76d  xorps   xmm1, xmm1
0x18004f770  cmp     rcx, r15
0x18004f773  jz      short loc_18004F79C
0x18004f775  xorps   xmm1, xmm1
0x18004f778  cvtsi2sd xmm1, rcx
0x18004f77d  ucomisd xmm1, xmm0
0x18004f781  jz      short loc_18004F79C
0x18004f783  unpcklpd xmm0, xmm0
0x18004f787  movmskpd eax, xmm0
0x18004f78b  and     eax, 1
0x18004f78e  xor     eax, 1
0x18004f791  add     rcx, rax
0x18004f794  xorps   xmm0, xmm0
0x18004f797  cvtsi2sd xmm0, rcx
0x18004f79c  cvttsd2si r8, xmm0
0x18004f7a1  mov     [rsp+68h+arg_0], r8
0x18004f7a6  mov     r9, [rdi+50h]
0x18004f7aa  movsxd  r10, dword ptr [rdi+40h]
0x18004f7ae  movsxd  rcx, dword ptr [rdi+34h]
0x18004f7b2  lea     rax, [r8+r10]
0x18004f7b6  add     rcx, rax
0x18004f7b9  movsxd  rax, dword ptr [r9+8]
0x18004f7bd  add     rax, [r9]
0x18004f7c0  cmp     rcx, rax
0x18004f7c3  jle     loc_18004F690
0x18004f7c9  mov     esi, r14d
0x18004f7cc  mov     rcx, rbx; lpCriticalSection
0x18004f7cf  call    cs:__imp_LeaveCriticalSection
0x18004f7d6  nop     dword ptr [rax+rax+00h]
0x18004f7db  mov     eax, esi
0x18004f7dd  mov     rbx, [rsp+68h+arg_8]
0x18004f7e2  add     rsp, 40h
0x18004f7e6  pop     r15
0x18004f7e8  pop     r14
0x18004f7ea  pop     rdi
0x18004f7eb  pop     rsi
0x18004f7ec  pop     rbp
0x18004f7ed  retn
```
