# MbbUtilWwanToMbbSetLteAttachContext(_WWAN_SET_LTE_ATTACH *,_MBB_SET_MS_CONTEXT_LTE_ATTACH_CONFIG * *,ulong *)

- ea: `0x140022030`
- end: `0x140022404`
- name: `?MbbUtilWwanToMbbSetLteAttachContext@@YAJPEAU_WWAN_SET_LTE_ATTACH@@PEAPEAU_MBB_SET_MS_CONTEXT_LTE_ATTACH_CONFIG@@PEAK@Z`
- size: `980`
- prototype: `__int64 __fastcall(struct _WWAN_SET_LTE_ATTACH *, struct _MBB_SET_MS_CONTEXT_LTE_ATTACH_CONFIG **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140014a30`

## callees

- `0x140001db8`
- `0x140020d40`
- `0x140022030`
- `0x140048340`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002220e`
- `ntoskrnl!ExAllocatePool2` at `0x14002220e`

## pseudocode

```c
__int64 __fastcall MbbUtilWwanToMbbSetLteAttachContext(
        struct _WWAN_SET_LTE_ATTACH *a1,
        struct _MBB_SET_MS_CONTEXT_LTE_ATTACH_CONFIG **a2,
        unsigned int *a3)
{
  unsigned int v4; // edi
  unsigned int v5; // r15d
  unsigned int v6; // r14d
  __int64 v7; // r8
  __int64 v8; // r11
  _WORD *v9; // rax
  __int64 v10; // rdx
  unsigned int v11; // ecx
  size_t *v12; // rbx
  _WORD *v13; // rax
  __int64 v14; // rdx
  size_t *v15; // r10
  _WORD *v16; // rax
  __int64 v17; // rdx
  size_t *v18; // rcx
  unsigned int v19; // eax
  unsigned __int8 *Pool2; // rax
  unsigned __int8 *v21; // rdi
  int v23; // edx
  __int64 v24; // rax
  __int64 v25; // r14
  unsigned int v26; // eax
  __int64 v27; // r13
  __int64 v28; // r15
  int *v29; // r12
  __int64 v30; // rax
  int v31; // ecx
  __int64 v32; // rax
  int v33; // ecx
  unsigned int v34; // ebx
  int v35; // eax
  int v36; // eax
  int v37; // eax
  size_t Size; // [rsp+28h] [rbp-51h]
  size_t Sizea; // [rsp+28h] [rbp-51h]
  size_t Sizeb; // [rsp+28h] [rbp-51h]
  int v41; // [rsp+30h] [rbp-49h]
  unsigned int v42; // [rsp+34h] [rbp-45h]
  unsigned int v43[2]; // [rsp+38h] [rbp-41h]
  int v44; // [rsp+40h] [rbp-39h]
  unsigned int *v45; // [rsp+48h] [rbp-31h]
  struct _MBB_SET_MS_CONTEXT_LTE_ATTACH_CONFIG **v46; // [rsp+50h] [rbp-29h]
  size_t v47[2]; // [rsp+58h] [rbp-21h] BYREF
  __int64 v48; // [rsp+68h] [rbp-11h]
  size_t v49[2]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v50; // [rsp+80h] [rbp+7h]
  size_t v51[2]; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v52; // [rsp+98h] [rbp+1Fh]

  v45 = a3;
  v46 = a2;
  *(_QWORD *)v43 = 0;
  *a3 = 0;
  v4 = 0;
  v44 = 0;
  v5 = 32;
  v48 = 0;
  v41 = 32;
  v6 = 32;
  *(_OWORD *)v47 = 0;
  v50 = 0;
  *(_OWORD *)v49 = 0;
  v52 = 0;
  *(_OWORD *)v51 = 0;
  *a2 = 0;
  do
  {
    v7 = v4;
    v8 = 1288LL * v4;
    v43[v4] = 44;
    v9 = (_WORD *)((char *)a1 + v8 + 8);
    if ( !v9 )
      return (unsigned int)-1073741811;
    v10 = 101;
    do
    {
      if ( !*v9 )
        break;
      ++v9;
      --v10;
    }
    while ( v10 );
    v11 = v10 == 0 ? 0xC000000D : 0;
    if ( !v10 )
      return v11;
    v12 = &v47[v4];
    if ( v12 )
      *v12 = 2 * ((101 - v10) & -(__int64)(v10 != 0));
    v13 = (_WORD *)((char *)a1 + v8 + 210);
    if ( !v13 )
      return (unsigned int)-1073741811;
    v14 = 256;
    do
    {
      if ( !*v13 )
        break;
      ++v13;
      --v14;
    }
    while ( v14 );
    v11 = v14 == 0 ? 0xC000000D : 0;
    if ( !v14 )
      return v11;
    v15 = &v49[v4];
    if ( v15 )
      *v15 = 2 * ((256 - v14) & -(__int64)(v14 != 0));
    v16 = (_WORD *)((char *)a1 + v8 + 722);
    if ( !v16 )
      return (unsigned int)-1073741811;
    v17 = 256;
    do
    {
      if ( !*v16 )
        break;
      ++v16;
      --v17;
    }
    while ( v17 );
    v11 = v17 == 0 ? 0xC000000D : 0;
    if ( !v17 )
      return v11;
    v18 = &v51[v4];
    if ( v18 )
      *v18 = 2 * ((256 - v17) & -(__int64)(v17 != 0));
    ++v4;
    v19 = ((*(_DWORD *)v12 + 3) & 0xFFFFFFFC)
        + ((*(_DWORD *)v18 + 3) & 0xFFFFFFFC)
        + ((*(_DWORD *)v15 + 3) & 0xFFFFFFFC)
        + 44;
    v6 += v19;
    v43[v7] = v19;
    v42 = v6;
  }
  while ( v4 < 3 );
  Pool2 = (unsigned __int8 *)ExAllocatePool2(64, v6, 1683505741);
  v21 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  memset(Pool2, 0, v6);
  v24 = *((int *)a1 + 315);
  if ( (unsigned int)v24 > 2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v23) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v23,
        3,
        53,
        (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
        *((_DWORD *)a1 + 315));
    }
    return 3221225485LL;
  }
  else
  {
    *((_DWORD *)v21 + 1) = 3;
    v25 = 0;
    *(_DWORD *)v21 = dword_14004EF90[v24];
    do
    {
      v26 = v43[v25];
      v27 = v5;
      *(_DWORD *)&v21[8 * v25 + 8] = v5;
      v28 = 1288 * v25;
      *(_DWORD *)&v21[8 * v25 + 12] = v26;
      v29 = (int *)&v21[v27];
      v30 = *((int *)a1 + 322 * v25 + 316);
      if ( (unsigned int)v30 > 3 )
        v31 = 5;
      else
        v31 = dword_14004EFA0[v30];
      *v29 = v31;
      v29[1] = *(_DWORD *)((char *)a1 + v28 + 1272);
      v32 = *(int *)((char *)a1 + v28 + 1280);
      if ( (unsigned int)v32 > 5 )
        v33 = 5;
      else
        v33 = dword_14004EFB0[v32];
      v29[2] = v33;
      v34 = v43[v25];
      LODWORD(Size) = v47[v25];
      v35 = MbbUtilWriteStringToBuffer(
              &v21[v27],
              v34,
              44,
              (struct _MBB_STRING *)&v21[v27 + 12],
              (const unsigned __int8 *)a1 + v28 + 8,
              Size);
      LODWORD(Sizea) = v49[v25];
      v36 = MbbUtilWriteStringToBuffer(
              &v21[v27],
              v34,
              v35,
              (struct _MBB_STRING *)&v21[v27 + 20],
              (const unsigned __int8 *)a1 + v28 + 210,
              Sizea);
      LODWORD(Sizeb) = v51[v25];
      MbbUtilWriteStringToBuffer(
        &v21[v27],
        v34,
        v36,
        (struct _MBB_STRING *)&v21[v27 + 28],
        (const unsigned __int8 *)a1 + v28 + 722,
        Sizeb);
      v29[9] = *(_DWORD *)((char *)a1 + v28 + 1236);
      ++v25;
      v37 = *(_DWORD *)((char *)a1 + v28 + 1240);
      v5 = v34 + v41;
      v29[10] = v37;
      v41 += v34;
    }
    while ( v25 != 3 );
    *v45 = v42;
    *v46 = (struct _MBB_SET_MS_CONTEXT_LTE_ATTACH_CONFIG *)v21;
    return 0;
  }
}

```

## disassembly

```asm
0x140022030  mov     [rsp-8+arg_18], rbx
0x140022035  push    rbp
0x140022036  push    rsi
0x140022037  push    rdi
0x140022038  push    r12
0x14002203a  push    r13
0x14002203c  push    r14
0x14002203e  push    r15
0x140022040  lea     rbp, [rsp-27h]
0x140022045  sub     rsp, 0A0h
0x14002204c  xorps   xmm0, xmm0
0x14002204f  mov     [rbp+57h+var_88], r8
0x140022053  mov     rsi, rcx
0x140022056  mov     [rbp+57h+var_80], rdx
0x14002205a  xor     ecx, ecx
0x14002205c  xorps   xmm1, xmm1
0x14002205f  xor     r12d, r12d
0x140022062  mov     qword ptr [rbp+57h+var_98], rcx
0x140022066  mov     [r8], r12d
0x140022069  mov     edi, r12d
0x14002206c  mov     [rbp+57h+var_90], ecx
0x14002206f  mov     r13d, 0C000000Dh
0x140022075  lea     r15d, [rcx+20h]
0x140022079  mov     [rbp+57h+var_68], rcx
0x14002207d  mov     [rbp+57h+var_A0], r15d
0x140022081  mov     r14d, r15d
0x140022084  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x140022088  mov     [rbp+57h+var_50], rcx
0x14002208c  movups  xmmword ptr [rbp+57h+var_60], xmm1
0x140022090  mov     [rbp+57h+var_38], rcx
0x140022094  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x140022098  mov     [rdx], r12
0x14002209b  mov     r8d, edi
0x14002209e  lea     rax, [rsi+8]
0x1400220a2  imul    r11, r8, 508h
0x1400220a9  mov     [rbp+r8*4+57h+var_98], 2Ch ; ','
0x1400220b2  add     rax, r11
0x1400220b5  jz      loc_1400223E3
0x1400220bb  mov     edx, 65h ; 'e'
0x1400220c0  cmp     [rax], r12w
0x1400220c4  jz      short loc_1400220D0
0x1400220c6  add     rax, 2
0x1400220ca  sub     rdx, 1
0x1400220ce  jnz     short loc_1400220C0
0x1400220d0  mov     rax, rdx
0x1400220d3  neg     rax
0x1400220d6  mov     eax, 65h ; 'e'
0x1400220db  sbb     ecx, ecx
0x1400220dd  sub     rax, rdx
0x1400220e0  neg     rdx
0x1400220e3  not     ecx
0x1400220e5  sbb     r9, r9
0x1400220e8  and     r9, rax
0x1400220eb  and     ecx, r13d
0x1400220ee  js      loc_1400223E6
0x1400220f4  lea     rbx, [rbp+57h+var_78]
0x1400220f8  lea     rbx, [rbx+r8*8]
0x1400220fc  test    rbx, rbx
0x1400220ff  jz      short loc_140022108
0x140022101  lea     rax, [r9+r9]
0x140022105  mov     [rbx], rax
0x140022108  lea     rax, [rsi+0D2h]
0x14002210f  add     rax, r11
0x140022112  jz      loc_1400223E3
0x140022118  mov     edx, 100h
0x14002211d  cmp     [rax], r12w
0x140022121  jz      short loc_14002212D
0x140022123  add     rax, 2
0x140022127  sub     rdx, 1
0x14002212b  jnz     short loc_14002211D
0x14002212d  mov     rax, rdx
0x140022130  neg     rax
0x140022133  mov     eax, 100h
0x140022138  sbb     ecx, ecx
0x14002213a  sub     rax, rdx
0x14002213d  neg     rdx
0x140022140  not     ecx
0x140022142  sbb     r9, r9
0x140022145  and     r9, rax
0x140022148  and     ecx, r13d
0x14002214b  js      loc_1400223E6
0x140022151  lea     r10, [rbp+57h+var_60]
0x140022155  lea     r10, [r10+r8*8]
0x140022159  test    r10, r10
0x14002215c  jz      short loc_140022165
0x14002215e  lea     rax, [r9+r9]
0x140022162  mov     [r10], rax
0x140022165  lea     rax, [rsi+2D2h]
0x14002216c  add     rax, r11
0x14002216f  jz      loc_1400223E3
0x140022175  mov     r9d, 100h
0x14002217b  mov     edx, r9d
0x14002217e  cmp     [rax], r12w
0x140022182  jz      short loc_14002218E
0x140022184  add     rax, 2
0x140022188  sub     rdx, 1
0x14002218c  jnz     short loc_14002217E
0x14002218e  mov     rax, rdx
0x140022191  neg     rax
0x140022194  mov     rax, r9
0x140022197  sbb     ecx, ecx
0x140022199  sub     rax, rdx
0x14002219c  neg     rdx
0x14002219f  not     ecx
0x1400221a1  sbb     r9, r9
0x1400221a4  and     r9, rax
0x1400221a7  and     ecx, r13d
0x1400221aa  js      loc_1400223E6
0x1400221b0  lea     rcx, [rbp+57h+var_48]
0x1400221b4  lea     rcx, [rcx+r8*8]
0x1400221b8  test    rcx, rcx
0x1400221bb  jz      short loc_1400221C4
0x1400221bd  lea     rax, [r9+r9]
0x1400221c1  mov     [rcx], rax
0x1400221c4  mov     ecx, [rcx]
0x1400221c6  mov     edx, 0FFFFFFFCh
0x1400221cb  mov     eax, [rbx]
0x1400221cd  add     ecx, 3
0x1400221d0  add     eax, 3
0x1400221d3  and     ecx, edx
0x1400221d5  and     eax, edx
0x1400221d7  inc     edi
0x1400221d9  add     ecx, eax
0x1400221db  mov     eax, [r10]
0x1400221de  add     eax, 3
0x1400221e1  and     eax, edx
0x1400221e3  add     eax, 2Ch ; ','
0x1400221e6  add     eax, ecx
0x1400221e8  add     r14d, eax
0x1400221eb  mov     [rbp+r8*4+57h+var_98], eax
0x1400221f0  mov     [rbp+57h+var_9C], r14d
0x1400221f4  cmp     edi, 3
0x1400221f7  jb      loc_14002209B
0x1400221fd  mov     r8d, 6458424Dh
0x140022203  mov     edx, r14d
0x140022206  mov     ecx, 40h ; '@'
0x14002220b  mov     ebx, r14d
0x14002220e  call    cs:__imp_ExAllocatePool2
0x140022215  nop     dword ptr [rax+rax+00h]
0x14002221a  mov     rdi, rax
0x14002221d  test    rax, rax
0x140022220  jnz     short loc_14002222C
0x140022222  mov     eax, 0C000009Ah
0x140022227  jmp     loc_1400223E8
0x14002222c  mov     r8, rbx; Size
0x14002222f  xor     edx, edx; Val
0x140022231  mov     rcx, rdi; void *
0x140022234  call    memset
0x140022239  movsxd  rax, dword ptr [rsi+4ECh]
0x140022240  cmp     eax, 2
0x140022243  ja      loc_1400223A2
0x140022249  lea     rdx, cs:140000000h
0x140022250  mov     dword ptr [rdi+4], 3
0x140022257  mov     eax, ds:rva dword_14004EF90[rdx+rax*4]
0x14002225e  mov     r14, r12
0x140022261  mov     [rdi], eax
0x140022263  mov     eax, [rbp+r14*4+57h+var_98]
0x140022268  mov     r13d, r15d
0x14002226b  mov     [rdi+r14*8+8], r15d
0x140022270  imul    r15, r14, 508h
0x140022277  mov     [rdi+r14*8+0Ch], eax
0x14002227c  lea     r12, [rdi+r13]
0x140022280  movsxd  rax, dword ptr [r15+rsi+4F0h]
0x140022288  cmp     eax, 3
0x14002228b  ja      short loc_140022296
0x14002228d  mov     ecx, ds:rva dword_14004EFA0[rdx+rax*4]
0x140022294  jmp     short loc_14002229B
0x140022296  mov     ecx, 5
0x14002229b  mov     [r12], ecx
0x14002229f  mov     eax, [r15+rsi+4F8h]
0x1400222a7  mov     [r12+4], eax
0x1400222ac  movsxd  rax, dword ptr [r15+rsi+500h]
0x1400222b4  cmp     eax, 5
0x1400222b7  ja      short loc_1400222C2
0x1400222b9  mov     ecx, ds:rva dword_14004EFB0[rdx+rax*4]
0x1400222c0  jmp     short loc_1400222C7
0x1400222c2  mov     ecx, 5
0x1400222c7  mov     [r12+8], ecx
0x1400222cc  lea     r9, [r13+0Ch]
0x1400222d0  mov     eax, dword ptr [rbp+r14*8+57h+var_78]
0x1400222d5  lea     rcx, [rsi+8]
0x1400222d9  mov     ebx, [rbp+r14*4+57h+var_98]
0x1400222de  add     rcx, r15
0x1400222e1  mov     dword ptr [rsp+0D0h+Size], eax; Size
0x1400222e5  add     r9, rdi; struct _MBB_STRING *
0x1400222e8  mov     [rsp+0D0h+Src], rcx; Src
0x1400222ed  mov     r8d, 2Ch ; ','; unsigned int
0x1400222f3  mov     rcx, r12; unsigned __int8 *
0x1400222f6  mov     edx, ebx; unsigned int
0x1400222f8  call    ?MbbUtilWriteStringToBuffer@@YAKPEAEKKPEAU_MBB_STRING@@PEBEK@Z; MbbUtilWriteStringToBuffer(uchar *,ulong,ulong,_MBB_STRING *,uchar const *,ulong)
0x1400222fd  mov     r8d, eax; unsigned int
0x140022300  lea     rcx, [rsi+0D2h]
0x140022307  mov     eax, dword ptr [rbp+r14*8+57h+var_60]
0x14002230c  lea     r9, [r13+14h]
0x140022310  add     rcx, r15
0x140022313  mov     dword ptr [rsp+0D0h+Size], eax; Size
0x140022317  mov     [rsp+0D0h+Src], rcx; Src
0x14002231c  add     r9, rdi; struct _MBB_STRING *
0x14002231f  mov     rcx, r12; unsigned __int8 *
0x140022322  mov     edx, ebx; unsigned int
0x140022324  call    ?MbbUtilWriteStringToBuffer@@YAKPEAEKKPEAU_MBB_STRING@@PEBEK@Z; MbbUtilWriteStringToBuffer(uchar *,ulong,ulong,_MBB_STRING *,uchar const *,ulong)
0x140022329  mov     r8d, eax; unsigned int
0x14002232c  lea     rcx, [rsi+2D2h]
0x140022333  mov     eax, dword ptr [rbp+r14*8+57h+var_48]
0x140022338  lea     r9, [r13+1Ch]
0x14002233c  add     rcx, r15
0x14002233f  mov     dword ptr [rsp+0D0h+Size], eax; Size
0x140022343  mov     [rsp+0D0h+Src], rcx; Src
0x140022348  add     r9, rdi; struct _MBB_STRING *
0x14002234b  mov     rcx, r12; unsigned __int8 *
0x14002234e  mov     edx, ebx; unsigned int
0x140022350  call    ?MbbUtilWriteStringToBuffer@@YAKPEAEKKPEAU_MBB_STRING@@PEBEK@Z; MbbUtilWriteStringToBuffer(uchar *,ulong,ulong,_MBB_STRING *,uchar const *,ulong)
0x140022355  mov     eax, [r15+rsi+4D4h]
0x14002235d  lea     rdx, cs:140000000h
0x140022364  mov     [r12+24h], eax
0x140022369  inc     r14
0x14002236c  mov     eax, [r15+rsi+4D8h]
0x140022374  mov     r15d, [rbp+57h+var_A0]
0x140022378  add     r15d, ebx
0x14002237b  mov     [r12+28h], eax
0x140022380  mov     [rbp+57h+var_A0], r15d
0x140022384  cmp     r14, 3
0x140022388  jnz     loc_140022263
0x14002238e  mov     eax, [rbp+57h+var_9C]
0x140022391  mov     rcx, [rbp+57h+var_88]
0x140022395  mov     [rcx], eax
0x140022397  mov     rax, [rbp+57h+var_80]
0x14002239b  mov     [rax], rdi
0x14002239e  xor     eax, eax
0x1400223a0  jmp     short loc_1400223E8
0x1400223a2  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400223a9  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400223b0  jz      short loc_1400223DE
0x1400223b2  lea     rcx, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x1400223b9  mov     dword ptr [rsp+0D0h+Size], eax
0x1400223bd  mov     [rsp+0D0h+Src], rcx
0x1400223c2  mov     r9d, 35h ; '5'
0x1400223c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400223cf  mov     dl, 2
0x1400223d1  lea     r8d, [r9-32h]
0x1400223d5  mov     rcx, [rcx+40h]
0x1400223d9  call    WPP_RECORDER_SF_d
0x1400223de  mov     eax, r13d
0x1400223e1  jmp     short loc_1400223E8
0x1400223e3  mov     ecx, r13d
0x1400223e6  mov     eax, ecx
0x1400223e8  mov     rbx, [rsp+0D0h+arg_18]
0x1400223f0  add     rsp, 0A0h
0x1400223f7  pop     r15
0x1400223f9  pop     r14
0x1400223fb  pop     r13
0x1400223fd  pop     r12
0x1400223ff  pop     rdi
0x140022400  pop     rsi
0x140022401  pop     rbp
0x140022402  retn
```
