# CAudioTimeCompression::OnInputFormatChange(int,int)

- ea: `0x18004f270`
- end: `0x18004f4b5`
- name: `?OnInputFormatChange@CAudioTimeCompression@@IEAAJHH@Z`
- size: `581`
- prototype: `__int64 __fastcall(CAudioTimeCompression *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18004fae0`

## callees

- `0x180002154`
- `0x18004f270`
- `0x18004fd30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x18004f3d6`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x18004f3d6`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18004f3bd`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18004f3bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f49d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f49d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f28b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f28b`

## pseudocode

```c
__int64 __fastcall CAudioTimeCompression::OnInputFormatChange(CAudioTimeCompression *this, unsigned int a2, int a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  unsigned int v7; // edi
  __int16 v8; // ax
  __m128d v9; // xmm0
  int v10; // eax
  int v11; // ecx
  int v12; // eax
  __m128d v13; // xmm0
  int v14; // ecx
  bool v15; // zf
  int v16; // eax
  void *v17; // rcx
  void *v18; // rax
  int v19; // edx
  int v20; // esi
  double v21; // xmm0_8
  __int64 v22; // rcx

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 224);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  if ( *((_BYTE *)this + 22) )
  {
    v7 = -2147418113;
  }
  else
  {
    v8 = 2;
    v9 = 0;
    *((_DWORD *)this + 2) = a2;
    if ( !a3 )
      v8 = 6;
    *((_WORD *)this + 9) = 32;
    *((_WORD *)this + 3) = v8;
    v10 = (unsigned __int16)(4 * v8);
    *((_WORD *)this + 8) = v10;
    *((_DWORD *)this + 3) = a2 * v10;
    v9.m128d_f64[0] = (double)(int)(*((_DWORD *)this + 10) * a2) * 0.001 + 0.5;
    v11 = (int)v9.m128d_f64[0];
    if ( (double)v11 != v9.m128d_f64[0] )
      v9.m128d_f64[0] = (double)(v11 - (_mm_movemask_pd(_mm_unpacklo_pd(v9, v9)) & 1));
    v12 = (int)v9.m128d_f64[0];
    v13 = 0;
    *((_DWORD *)this + 13) = v12;
    v13.m128d_f64[0] = (double)(int)(*((_DWORD *)this + 11) * a2) * 0.001;
    v14 = (int)v13.m128d_f64[0];
    if ( (double)v14 != v13.m128d_f64[0] )
      v13.m128d_f64[0] = (double)(v14 - (_mm_movemask_pd(_mm_unpacklo_pd(v13, v13)) & 1));
    v15 = *(_DWORD *)this == 0;
    *((_DWORD *)this + 14) = (int)v13.m128d_f64[0];
    if ( !v15 )
    {
      if ( a2 > 0xBB80 )
      {
        if ( a2 != 96000 )
        {
          v7 = -2147467259;
          goto LABEL_26;
        }
        v16 = (int)v13.m128d_f64[0] & 0xFFF8;
      }
      else
      {
        v16 = (int)v13.m128d_f64[0] & 0xFFFFC;
      }
      *((_DWORD *)this + 14) = v16;
    }
    v17 = (void *)*((_QWORD *)this + 14);
    *((_DWORD *)this + 16) = (a2 >> 1) / 0x14;
    if ( v17 )
      _aligned_free(v17);
    v18 = _aligned_malloc(4LL * *((int *)this + 14), 0x10u);
    *((_QWORD *)this + 14) = v18;
    if ( v18 )
    {
      v19 = *((_DWORD *)this + 14);
      if ( v19 > 0 )
      {
        v20 = 0;
        do
        {
          v21 = cos((double)v20 * 6.283185307179586 / (double)(2 * v19 - 1));
          v22 = v20++;
          *(float *)&v21 = (0.5 - v21 * 0.5) * (0.5 - v21 * 0.5);
          *(_DWORD *)(*((_QWORD *)this + 14) + 4 * v22) = LODWORD(v21);
          v19 = *((_DWORD *)this + 14);
        }
        while ( v20 < v19 );
      }
      v7 = CAudioTimeCompression::allocTemps(this, v19, 2 * *((_DWORD *)this + 16));
    }
    else
    {
      v7 = -2147024882;
    }
  }
LABEL_26:
  LeaveCriticalSection(v3);
  return v7;
}

```

## disassembly

```asm
0x18004f270  push    rbx
0x18004f272  push    rbp
0x18004f273  push    rsi
0x18004f274  push    rdi
0x18004f275  sub     rsp, 48h
0x18004f279  lea     rbx, [rcx+0E0h]
0x18004f280  mov     rdi, rcx
0x18004f283  mov     rcx, rbx; lpCriticalSection
0x18004f286  mov     ebp, r8d
0x18004f289  mov     esi, edx
0x18004f28b  call    cs:__imp_EnterCriticalSection
0x18004f292  nop     dword ptr [rax+rax+00h]
0x18004f297  cmp     byte ptr [rdi+16h], 0
0x18004f29b  jz      short loc_18004F2A7
0x18004f29d  mov     edi, 8000FFFFh
0x18004f2a2  jmp     loc_18004F49A
0x18004f2a7  movsd   xmm2, cs:__real@3f50624dd2f1a9fc
0x18004f2af  mov     eax, 2
0x18004f2b4  xorps   xmm0, xmm0
0x18004f2b7  movaps  [rsp+68h+var_48], xmm7
0x18004f2bc  movsd   xmm7, cs:__real@3fe0000000000000
0x18004f2c4  test    ebp, ebp
0x18004f2c6  mov     ecx, 6
0x18004f2cb  mov     [rdi+8], esi
0x18004f2ce  cmovz   ax, cx
0x18004f2d2  mov     word ptr [rdi+12h], 20h ; ' '
0x18004f2d8  mov     [rdi+6], ax
0x18004f2dc  mov     rdx, 8000000000000000h
0x18004f2e6  shl     ax, 2
0x18004f2ea  xorps   xmm1, xmm1
0x18004f2ed  movzx   eax, ax
0x18004f2f0  mov     [rdi+10h], ax
0x18004f2f4  imul    eax, esi
0x18004f2f7  mov     [rdi+0Ch], eax
0x18004f2fa  mov     eax, esi
0x18004f2fc  imul    eax, [rdi+28h]
0x18004f300  cvtsi2sd xmm0, rax
0x18004f305  mulsd   xmm0, xmm2
0x18004f309  addsd   xmm0, xmm7
0x18004f30d  cvttsd2si rcx, xmm0
0x18004f312  cmp     rcx, rdx
0x18004f315  jz      short loc_18004F33B
0x18004f317  xorps   xmm1, xmm1
0x18004f31a  cvtsi2sd xmm1, rcx
0x18004f31f  ucomisd xmm1, xmm0
0x18004f323  jz      short loc_18004F33B
0x18004f325  unpcklpd xmm0, xmm0
0x18004f329  movmskpd eax, xmm0
0x18004f32d  xorps   xmm0, xmm0
0x18004f330  and     eax, 1
0x18004f333  sub     rcx, rax
0x18004f336  cvtsi2sd xmm0, rcx
0x18004f33b  cvttsd2si eax, xmm0
0x18004f33f  xorps   xmm0, xmm0
0x18004f342  xorps   xmm1, xmm1
0x18004f345  mov     [rdi+34h], eax
0x18004f348  mov     eax, esi
0x18004f34a  imul    eax, [rdi+2Ch]
0x18004f34e  cvtsi2sd xmm0, rax
0x18004f353  mulsd   xmm0, xmm2
0x18004f357  cvttsd2si rcx, xmm0
0x18004f35c  cmp     rcx, rdx
0x18004f35f  jz      short loc_18004F385
0x18004f361  xorps   xmm1, xmm1
0x18004f364  cvtsi2sd xmm1, rcx
0x18004f369  ucomisd xmm1, xmm0
0x18004f36d  jz      short loc_18004F385
0x18004f36f  unpcklpd xmm0, xmm0
0x18004f373  movmskpd eax, xmm0
0x18004f377  xorps   xmm0, xmm0
0x18004f37a  and     eax, 1
0x18004f37d  sub     rcx, rax
0x18004f380  cvtsi2sd xmm0, rcx
0x18004f385  cmp     dword ptr [rdi], 0
0x18004f388  cvttsd2si eax, xmm0
0x18004f38c  mov     [rdi+38h], eax
0x18004f38f  jz      short loc_18004F3A5
0x18004f391  cmp     esi, 0BB80h
0x18004f397  ja      loc_18004F477
0x18004f39d  and     eax, 0FFFFCh
0x18004f3a2  mov     [rdi+38h], eax
0x18004f3a5  mov     rcx, [rdi+70h]; Block
0x18004f3a9  mov     eax, 0CCCCCCCDh
0x18004f3ae  shr     esi, 1
0x18004f3b0  mul     esi
0x18004f3b2  shr     edx, 4
0x18004f3b5  mov     [rdi+40h], edx
0x18004f3b8  test    rcx, rcx
0x18004f3bb  jz      short loc_18004F3C9
0x18004f3bd  call    cs:__imp__aligned_free
0x18004f3c4  nop     dword ptr [rax+rax+00h]
0x18004f3c9  movsxd  rcx, dword ptr [rdi+38h]
0x18004f3cd  mov     edx, 10h; Alignment
0x18004f3d2  shl     rcx, 2; Size
0x18004f3d6  call    cs:__imp__aligned_malloc
0x18004f3dd  nop     dword ptr [rax+rax+00h]
0x18004f3e2  mov     [rdi+70h], rax
0x18004f3e6  test    rax, rax
0x18004f3e9  jz      loc_18004F490
0x18004f3ef  mov     edx, [rdi+38h]
0x18004f3f2  test    edx, edx
0x18004f3f4  jle     short loc_18004F464
0x18004f3f6  movaps  [rsp+68h+var_38], xmm6
0x18004f3fb  xor     esi, esi
0x18004f3fd  movsd   xmm6, cs:__real@401921fb54442d18
0x18004f405  nop     word ptr [rax+rax+00000000h]
0x18004f410  lea     eax, ds:0FFFFFFFFFFFFFFFFh[rdx*2]
0x18004f417  movd    xmm0, esi
0x18004f41b  cvtdq2pd xmm0, xmm0
0x18004f41f  movd    xmm1, eax
0x18004f423  cvtdq2pd xmm1, xmm1
0x18004f427  mulsd   xmm0, xmm6
0x18004f42b  divsd   xmm0, xmm1; X
0x18004f42f  call    cos
0x18004f434  mov     rax, [rdi+70h]
0x18004f438  movaps  xmm1, xmm7
0x18004f43b  mulsd   xmm0, xmm7
0x18004f43f  movsxd  rcx, esi
0x18004f442  inc     esi
0x18004f444  subsd   xmm1, xmm0
0x18004f448  xorps   xmm0, xmm0
0x18004f44b  mulsd   xmm1, xmm1
0x18004f44f  cvtsd2ss xmm0, xmm1
0x18004f453  movss   dword ptr [rax+rcx*4], xmm0
0x18004f458  mov     edx, [rdi+38h]; int
0x18004f45b  cmp     esi, edx
0x18004f45d  jl      short loc_18004F410
0x18004f45f  movaps  xmm6, [rsp+68h+var_38]
0x18004f464  mov     r8d, [rdi+40h]
0x18004f468  mov     rcx, rdi; this
0x18004f46b  add     r8d, r8d; int
0x18004f46e  call    ?allocTemps@CAudioTimeCompression@@IEAAJHH@Z; CAudioTimeCompression::allocTemps(int,int)
0x18004f473  mov     edi, eax
0x18004f475  jmp     short loc_18004F495
0x18004f477  cmp     esi, 17700h
0x18004f47d  jnz     short loc_18004F489
0x18004f47f  and     eax, 0FFF8h
0x18004f484  jmp     loc_18004F3A2
0x18004f489  mov     edi, 80004005h
0x18004f48e  jmp     short loc_18004F495
0x18004f490  mov     edi, 8007000Eh
0x18004f495  movaps  xmm7, [rsp+68h+var_48]
0x18004f49a  mov     rcx, rbx; lpCriticalSection
0x18004f49d  call    cs:__imp_LeaveCriticalSection
0x18004f4a4  nop     dword ptr [rax+rax+00h]
0x18004f4a9  mov     eax, edi
0x18004f4ab  add     rsp, 48h
0x18004f4af  pop     rdi
0x18004f4b0  pop     rsi
0x18004f4b1  pop     rbp
0x18004f4b2  pop     rbx
0x18004f4b3  retn
```
