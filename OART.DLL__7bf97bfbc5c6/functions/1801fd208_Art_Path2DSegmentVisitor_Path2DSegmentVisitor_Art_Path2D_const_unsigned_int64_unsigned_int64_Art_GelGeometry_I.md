# Art::Path2DSegmentVisitor::Path2DSegmentVisitor(Art::Path2D const &,unsigned __int64,unsigned __int64,Art::GelGeometry::InstanceData const *,uchar)

- ea: `0x1801fd208`
- end: `0x1801fd6c1`
- name: `??0Path2DSegmentVisitor@Art@@QEAA@AEBVPath2D@1@_K1PEBVInstanceData@GelGeometry@1@E@Z`
- size: `1209`
- prototype: `__int64 __usercall@<rax>(Art::Path2DSegmentVisitor *__hidden this@<rcx>, const struct Art::Path2D *@<rdx>, unsigned __int64@<r8>, unsigned __int64@<r9>, const struct Art::GelGeometry::InstanceData *, unsigned __int8)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1801fc544`
- `0x180416e40`

## callees

- `0x180071720`
- `0x1800edb5c`
- `0x1801616e0`
- `0x1801e8ee0`
- `0x1801fd208`
- `0x1804d297c`

## import_xrefs

- `gfx!?Instance@IManager@Cache@@SAAEAU12@XZ` at `0x1801fd628`
- `gfx!?Instance@IManager@Cache@@SAAEAU12@XZ` at `0x1801fd628`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x1801fd24b`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x1801fd24b`
- `gfx!?Create@ITransformedPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBUIPath@2@AEBU?$TAffine3x3@N@Math@@@Z` at `0x1801fd411`
- `gfx!?Create@ITransformedPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBUIPath@2@AEBU?$TAffine3x3@N@Math@@@Z` at `0x1801fd4a1`
- `gfx!?Create@ITransformedPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBUIPath@2@AEBU?$TAffine3x3@N@Math@@@Z` at `0x1801fd411`
- `gfx!?Create@ITransformedPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBUIPath@2@AEBU?$TAffine3x3@N@Math@@@Z` at `0x1801fd4a1`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1801fd314`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1801fd5e4`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1801fd314`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1801fd5e4`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801fd350`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801fd361`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801fd524`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801fd535`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801fd350`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801fd361`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801fd524`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801fd535`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1801fd326`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1801fd5f2`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1801fd326`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1801fd5f2`

## pseudocode

```c
Art::Path2DSegmentVisitor *__fastcall Art::Path2DSegmentVisitor::Path2DSegmentVisitor(
        Art::Path2DSegmentVisitor *this,
        const struct Art::Path2D *a2,
        int a3,
        unsigned int a4,
        void **p_Src,
        unsigned __int8 a6)
{
  __int64 v7; // rdi
  const struct Art::GelGeometry::InstanceData *v10; // r14
  unsigned int v11; // r8d
  double v12; // xmm1_8
  double i; // xmm2_8
  __int64 v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // edx
  void *v17; // rax
  void *v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rdx
  double v21; // xmm2_8
  __int64 *v22; // rax
  __int64 v23; // rdi
  __int64 v24; // rcx
  double v25; // xmm2_8
  __int64 *v26; // rax
  __int64 v27; // rsi
  __int64 v28; // rcx
  void *v29; // rdx
  int v31; // edx
  unsigned __int64 v32; // rax
  Mso::Memory *v33; // rax
  __int64 v34; // rax
  __int64 *v35; // rax
  __int64 v36; // rdi
  const struct Art::GelGeometry::InstanceData *v37; // rcx
  void *Src; // [rsp+38h] [rbp-81h] BYREF
  unsigned int v39; // [rsp+40h] [rbp-79h]
  unsigned int v40; // [rsp+44h] [rbp-75h]
  int v41; // [rsp+48h] [rbp-71h]
  unsigned __int8 v42; // [rsp+4Ch] [rbp-6Dh]
  void **v43; // [rsp+50h] [rbp-69h] BYREF
  Mso::Memory *v44; // [rsp+58h] [rbp-61h] BYREF
  int v45; // [rsp+60h] [rbp-59h]
  unsigned int v46; // [rsp+64h] [rbp-55h]
  int v47; // [rsp+68h] [rbp-51h]
  char v48; // [rsp+6Ch] [rbp-4Dh]
  double v49; // [rsp+70h] [rbp-49h] BYREF
  __int128 v50; // [rsp+78h] [rbp-41h]
  double v51; // [rsp+88h] [rbp-31h]
  __int128 v52; // [rsp+90h] [rbp-29h]
  __int64 v53; // [rsp+A0h] [rbp-19h]
  __int64 v54; // [rsp+A8h] [rbp-11h] BYREF
  _QWORD v55[10]; // [rsp+B0h] [rbp-9h] BYREF
  int v56; // [rsp+118h] [rbp+5Fh] BYREF

  LODWORD(v7) = a3;
  v10 = (const struct Art::GelGeometry::InstanceData *)p_Src;
  *(_QWORD *)this = &Art::Path2DSegmentVisitor::`vftable';
  *((_QWORD *)this + 1) = a2;
  GEL::PathBuilder::PathBuilder((Art::Path2DSegmentVisitor *)((char *)this + 16));
  *((_QWORD *)this + 10) = 0;
  *((_DWORD *)this + 22) = *((_DWORD *)a2 + 10);
  *((_BYTE *)this + 92) = 0;
  *((_BYTE *)this + 93) = *((_BYTE *)a2 + 45);
  *((_BYTE *)this + 94) = *((_BYTE *)a2 + 44) == 0;
  v12 = DOUBLE_1_0;
  if ( *((_QWORD *)a2 + 3) )
    goto LABEL_12;
  for ( i = DOUBLE_1_0; ; i = (double)(int)v7 / (double)(int)*((_QWORD *)a2 + 3) )
  {
    *((double *)this + 12) = i;
    if ( *((_QWORD *)a2 + 4) )
      v12 = (double)(int)a4 / (double)(int)*((_QWORD *)a2 + 4);
    *((double *)this + 13) = v12;
    if ( !v10 )
      goto LABEL_17;
    p_Src = &Src;
    Src = 0;
    v14 = *((unsigned int *)v10 + 12);
    v39 = v14;
    v15 = *((_DWORD *)v10 + 13) & 0x80000000;
    v40 = v15;
    v7 = 0xFFFFFFFFLL;
    if ( !(_DWORD)v14 )
      goto LABEL_41;
    v16 = -1;
    if ( 4 * (unsigned __int64)(unsigned int)v14 <= 0xFFFFFFFF )
      v16 = 4 * v14;
    a4 = v16 >> 2;
    if ( v16 >> 2 < (unsigned int)v14 )
    {
      Ofc::COutOfMemoryException::ThrowTag(0x1E318643u);
      goto LABEL_53;
    }
    v17 = Mso::Memory::AllocateEx((Mso::Memory *)v16, 0, v11);
    if ( v17 )
      break;
    ThrowOOM();
LABEL_12:
    ;
  }
  Src = v17;
  v40 = a4 | v40 & 0x80000000;
  Ofc::TMoveConstructRange<Art::TextFontSize,1>::Do(*((void **)v10 + 5), v17);
  v15 = v40;
  v14 = v39;
LABEL_41:
  v31 = *((_DWORD *)v10 + 14);
  v41 = v31;
  LOBYTE(v11) = a6;
  v42 = a6;
  v55[0] = &Art::PresetPathFactoryState::`vftable';
  v55[1] = this;
  v43 = &Art::PresetPathInfo::`vftable';
  p_Src = (void **)&v44;
  v44 = 0;
  v45 = v14;
  v46 = v15 & 0x80000000;
  if ( (_DWORD)v14 )
  {
    v32 = 4LL * (unsigned int)v14;
    if ( v32 <= 0xFFFFFFFF )
      v7 = (unsigned int)v32;
    a4 = (unsigned int)v7 >> 2;
    if ( (unsigned int)v7 >> 2 >= (unsigned int)v14 )
    {
      v33 = (Mso::Memory *)Mso::Memory::AllocateEx((Mso::Memory *)(unsigned int)v7, 0, v11);
      if ( !v33 )
      {
        ThrowOOM();
        __debugbreak();
      }
      v44 = v33;
      v46 = a4 | v46 & 0x80000000;
      Ofc::TMoveConstructRange<Art::TextFontSize,1>::Do(Src, v33);
      LOBYTE(v11) = v42;
      v31 = v41;
      goto LABEL_48;
    }
LABEL_53:
    Ofc::COutOfMemoryException::ThrowTag(0x1E318643u);
    goto LABEL_54;
  }
LABEL_48:
  v47 = v31;
  v48 = v11;
  v53 = 0;
  v34 = Cache::IManager::Instance(v14);
  v35 = (__int64 *)(*(__int64 (__fastcall **)(__int64, void ***, void *, void ***, _QWORD *))(*(_QWORD *)v34 + 40LL))(
                     v34,
                     &p_Src,
                     &Art::c_presetPathCacheDescriptor,
                     &v43,
                     v55);
  v36 = *v35;
  *v35 = 0;
  v37 = (const struct Art::GelGeometry::InstanceData *)p_Src;
  if ( p_Src )
  {
    p_Src = 0;
    (*(void (__fastcall **)(const struct Art::GelGeometry::InstanceData *))(*(_QWORD *)v37 + 8LL))(v37);
  }
  v53 = 0;
  v55[2] = v36;
  if ( v36 )
  {
    v25 = (double)(int)*((_QWORD *)v10 + 3) / (double)(int)*((_QWORD *)v10 + 1);
    v49 = (double)(int)*((_QWORD *)v10 + 2) / (double)(int)*(_QWORD *)v10;
    v51 = v25;
    v52 = 0;
    v50 = 0;
    v26 = (__int64 *)GEL::ITransformedPath::Create(&v54, v36, &v49);
    v27 = *v26;
    *v26 = 0;
    v28 = *((_QWORD *)this + 10);
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
    *((_QWORD *)this + 10) = v27;
    if ( v54 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 8LL))(v54);
    v56 = 0;
    LODWORD(p_Src) = 0;
    (*(void (__fastcall **)(_QWORD, int *, void ***))(**((_QWORD **)this + 10) + 184LL))(
      *((_QWORD *)this + 10),
      &v56,
      &p_Src);
    *((_BYTE *)this + 92) = (int)p_Src > 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 8LL))(v36);
    if ( v44 )
      Mso::Memory::Free(v44, v29);
    if ( Src )
      Mso::Memory::Free((Mso::Memory *)Src, v29);
  }
  else
  {
    if ( v44 )
      Mso::Memory::Free(v44, v18);
    if ( Src )
      Mso::Memory::Free((Mso::Memory *)Src, v18);
LABEL_17:
    a4 = 0;
    while ( 1 )
    {
      v7 = a4 >= *((_DWORD *)a2 + 4) ? 0LL : *((_QWORD *)a2 + 1) + 16LL * a4;
      ++a4;
      if ( !v7 )
        break;
      if ( *(_QWORD *)(v7 + 8) <= 1u )
LABEL_54:
        Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::DemandInit(v7);
      v19 = *(_QWORD *)(v7 + 8);
      if ( v19 )
        (*(void (__fastcall **)(__int64, Art::Path2DSegmentVisitor *))(v19 + 56))(v7, this);
    }
    Art::Path2DSegmentVisitor::FinalizePath(this);
    if ( v10 )
    {
      v20 = *((_QWORD *)this + 10);
      if ( v20 )
      {
        v21 = (double)(int)*((_QWORD *)v10 + 3) / (double)(int)*((_QWORD *)v10 + 1);
        v49 = (double)(int)*((_QWORD *)v10 + 2) / (double)(int)*(_QWORD *)v10;
        v51 = v21;
        v52 = 0;
        v50 = 0;
        v22 = (__int64 *)GEL::ITransformedPath::Create(&p_Src, v20, &v49);
        v23 = *v22;
        *v22 = 0;
        v24 = *((_QWORD *)this + 10);
        if ( v24 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
        *((_QWORD *)this + 10) = v23;
        if ( p_Src )
          (*((void (__fastcall **)(void **))*p_Src + 1))(p_Src);
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x1801fd208  mov     [rsp-8+arg_10], rbx
0x1801fd20d  mov     [rsp-8+arg_0], rcx
0x1801fd212  push    rbp
0x1801fd213  push    rsi
0x1801fd214  push    rdi
0x1801fd215  push    r12
0x1801fd217  push    r13
0x1801fd219  push    r14
0x1801fd21b  push    r15
0x1801fd21d  lea     rbp, [rsp-17h]
0x1801fd222  sub     rsp, 0D0h
0x1801fd229  mov     rsi, r9
0x1801fd22c  mov     rdi, r8
0x1801fd22f  mov     r15, rdx
0x1801fd232  mov     rbx, rcx
0x1801fd235  mov     r14, [rbp+47h+arg_20]
0x1801fd239  lea     rax, ??_7Path2DSegmentVisitor@Art@@6B@; const Art::Path2DSegmentVisitor::`vftable'
0x1801fd240  mov     [rcx], rax
0x1801fd243  mov     [rcx+8], rdx
0x1801fd247  add     rcx, 10h
0x1801fd24b  call    cs:__imp_??0PathBuilder@GEL@@QEAA@XZ; GEL::PathBuilder::PathBuilder(void)
0x1801fd251  xor     r12d, r12d
0x1801fd254  mov     [rbx+50h], r12
0x1801fd258  mov     eax, [r15+28h]
0x1801fd25c  mov     [rbx+58h], eax
0x1801fd25f  mov     [rbx+5Ch], r12b
0x1801fd263  mov     al, [r15+2Dh]
0x1801fd267  mov     [rbx+5Dh], al
0x1801fd26a  cmp     [r15+2Ch], r12b
0x1801fd26e  setz    al
0x1801fd271  mov     [rbx+5Eh], al
0x1801fd274  movsd   xmm1, cs:__real@3ff0000000000000
0x1801fd27c  cmp     [r15+18h], r12
0x1801fd280  jnz     loc_1801FD32D
0x1801fd286  movaps  xmm2, xmm1
0x1801fd289  movsd   qword ptr [rbx+60h], xmm2
0x1801fd28e  cmp     [r15+20h], r12
0x1801fd292  jz      short loc_1801FD2A9
0x1801fd294  xorps   xmm1, xmm1
0x1801fd297  cvtsi2sd xmm1, rsi
0x1801fd29c  xorps   xmm0, xmm0
0x1801fd29f  cvtsi2sd xmm0, qword ptr [r15+20h]
0x1801fd2a5  divsd   xmm1, xmm0
0x1801fd2a9  movsd   qword ptr [rbx+68h], xmm1
0x1801fd2ae  test    r14, r14
0x1801fd2b1  jz      loc_1801FD367
0x1801fd2b7  lea     rax, ??_7PresetPathInfo@Art@@6B@; const Art::PresetPathInfo::`vftable'
0x1801fd2be  mov     [rsp+100h+var_D0], rax
0x1801fd2c3  lea     rax, [rsp+100h+Src]
0x1801fd2c8  mov     [rbp+47h+arg_20], rax
0x1801fd2cc  mov     [rsp+100h+Src], r12
0x1801fd2d1  mov     ecx, [r14+30h]
0x1801fd2d5  mov     [rbp+47h+var_C0], ecx
0x1801fd2d8  mov     eax, [r14+34h]
0x1801fd2dc  mov     r13d, 80000000h
0x1801fd2e2  and     eax, r13d
0x1801fd2e5  mov     [rbp+47h+var_BC], eax
0x1801fd2e8  mov     edi, 0FFFFFFFFh
0x1801fd2ed  test    ecx, ecx
0x1801fd2ef  jz      loc_1801FD585
0x1801fd2f5  mov     eax, ecx
0x1801fd2f7  shl     rax, 2
0x1801fd2fb  mov     edx, edi
0x1801fd2fd  cmp     rax, rdi
0x1801fd300  cmovbe  edx, eax
0x1801fd303  mov     esi, edx
0x1801fd305  shr     esi, 2
0x1801fd308  cmp     esi, ecx
0x1801fd30a  jb      loc_1801FD696
0x1801fd310  mov     ecx, edx
0x1801fd312  xor     edx, edx
0x1801fd314  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1801fd31a  mov     rdx, rax; void *
0x1801fd31d  test    rax, rax
0x1801fd320  jnz     loc_1801FD562
0x1801fd326  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x1801fd32c  nop
0x1801fd32d  xorps   xmm2, xmm2
0x1801fd330  cvtsi2sd xmm2, rdi
0x1801fd335  xorps   xmm0, xmm0
0x1801fd338  cvtsi2sd xmm0, qword ptr [r15+18h]
0x1801fd33e  divsd   xmm2, xmm0
0x1801fd342  jmp     loc_1801FD289
0x1801fd347  mov     rcx, [rbp+47h+var_A8]
0x1801fd34b  test    rcx, rcx
0x1801fd34e  jz      short loc_1801FD357
0x1801fd350  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1801fd356  nop
0x1801fd357  mov     rcx, [rsp+100h+Src]
0x1801fd35c  test    rcx, rcx
0x1801fd35f  jz      short loc_1801FD367
0x1801fd361  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1801fd367  mov     esi, r12d
0x1801fd36a  cmp     esi, [r15+10h]
0x1801fd36e  jnb     loc_1801FD55A
0x1801fd374  mov     edi, esi
0x1801fd376  shl     rdi, 4
0x1801fd37a  add     rdi, [r15+8]
0x1801fd37e  inc     esi
0x1801fd380  test    rdi, rdi
0x1801fd383  jz      short loc_1801FD3AB
0x1801fd385  cmp     qword ptr [rdi+8], 1
0x1801fd38a  jbe     loc_1801FD6B3
0x1801fd390  mov     rax, [rdi+8]
0x1801fd394  test    rax, rax
0x1801fd397  jz      short loc_1801FD36A
0x1801fd399  mov     rdx, rbx
0x1801fd39c  mov     rcx, rdi
0x1801fd39f  mov     rax, [rax+38h]
0x1801fd3a3  call    cs:__guard_dispatch_icall_fptr
0x1801fd3a9  jmp     short loc_1801FD36A
0x1801fd3ab  mov     rcx, rbx; this
0x1801fd3ae  call    ?FinalizePath@Path2DSegmentVisitor@Art@@IEAAXXZ; Art::Path2DSegmentVisitor::FinalizePath(void)
0x1801fd3b3  test    r14, r14
0x1801fd3b6  jz      loc_1801FD53C
0x1801fd3bc  mov     rdx, [rbx+50h]
0x1801fd3c0  test    rdx, rdx
0x1801fd3c3  jz      loc_1801FD53C
0x1801fd3c9  xorps   xmm2, xmm2
0x1801fd3cc  cvtsi2sd xmm2, qword ptr [r14+18h]
0x1801fd3d2  xorps   xmm0, xmm0
0x1801fd3d5  cvtsi2sd xmm0, qword ptr [r14+8]
0x1801fd3db  divsd   xmm2, xmm0
0x1801fd3df  xorps   xmm1, xmm1
0x1801fd3e2  cvtsi2sd xmm1, qword ptr [r14+10h]
0x1801fd3e8  xorps   xmm0, xmm0
0x1801fd3eb  cvtsi2sd xmm0, qword ptr [r14]
0x1801fd3f0  divsd   xmm1, xmm0
0x1801fd3f4  movsd   [rbp+47h+var_90], xmm1
0x1801fd3f9  movsd   [rbp+47h+var_78], xmm2
0x1801fd3fe  xorps   xmm0, xmm0
0x1801fd401  movups  [rbp+47h+var_70], xmm0
0x1801fd405  movups  [rbp+47h+var_88], xmm0
0x1801fd409  lea     r8, [rbp+47h+var_90]
0x1801fd40d  lea     rcx, [rbp+47h+arg_20]
0x1801fd411  call    cs:__imp_?Create@ITransformedPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBUIPath@2@AEBU?$TAffine3x3@N@Math@@@Z; GEL::ITransformedPath::Create(GEL::IPath const &,Math::TAffine3x3<double> const &)
0x1801fd417  mov     rdi, [rax]
0x1801fd41a  mov     [rax], r12
0x1801fd41d  mov     rcx, [rbx+50h]
0x1801fd421  test    rcx, rcx
0x1801fd424  jz      short loc_1801FD433
0x1801fd426  mov     rax, [rcx]
0x1801fd429  mov     rax, [rax+8]
0x1801fd42d  call    cs:__guard_dispatch_icall_fptr
0x1801fd433  mov     [rbx+50h], rdi
0x1801fd437  mov     rcx, [rbp+47h+arg_20]
0x1801fd43b  test    rcx, rcx
0x1801fd43e  jz      loc_1801FD53C
0x1801fd444  mov     rax, [rcx]
0x1801fd447  mov     rax, [rax+8]
0x1801fd44b  call    cs:__guard_dispatch_icall_fptr
0x1801fd451  jmp     loc_1801FD53C
0x1801fd456  xorps   xmm2, xmm2
0x1801fd459  cvtsi2sd xmm2, qword ptr [r14+18h]
0x1801fd45f  xorps   xmm0, xmm0
0x1801fd462  cvtsi2sd xmm0, qword ptr [r14+8]
0x1801fd468  divsd   xmm2, xmm0
0x1801fd46c  xorps   xmm1, xmm1
0x1801fd46f  cvtsi2sd xmm1, qword ptr [r14+10h]
0x1801fd475  xorps   xmm0, xmm0
0x1801fd478  cvtsi2sd xmm0, qword ptr [r14]
0x1801fd47d  divsd   xmm1, xmm0
0x1801fd481  movsd   [rbp+47h+var_90], xmm1
0x1801fd486  movsd   [rbp+47h+var_78], xmm2
0x1801fd48b  xorps   xmm0, xmm0
0x1801fd48e  movups  [rbp+47h+var_70], xmm0
0x1801fd492  movups  [rbp+47h+var_88], xmm0
0x1801fd496  lea     r8, [rbp+47h+var_90]
0x1801fd49a  mov     rdx, rdi
0x1801fd49d  lea     rcx, [rbp+47h+var_58]
0x1801fd4a1  call    cs:__imp_?Create@ITransformedPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBUIPath@2@AEBU?$TAffine3x3@N@Math@@@Z; GEL::ITransformedPath::Create(GEL::IPath const &,Math::TAffine3x3<double> const &)
0x1801fd4a7  mov     rsi, [rax]
0x1801fd4aa  mov     [rax], r12
0x1801fd4ad  mov     rcx, [rbx+50h]
0x1801fd4b1  test    rcx, rcx
0x1801fd4b4  jz      short loc_1801FD4C3
0x1801fd4b6  mov     rax, [rcx]
0x1801fd4b9  mov     rax, [rax+8]
0x1801fd4bd  call    cs:__guard_dispatch_icall_fptr
0x1801fd4c3  mov     [rbx+50h], rsi
0x1801fd4c7  mov     rcx, [rbp+47h+var_58]
0x1801fd4cb  test    rcx, rcx
0x1801fd4ce  jz      short loc_1801FD4DD
0x1801fd4d0  mov     rax, [rcx]
0x1801fd4d3  mov     rax, [rax+8]
0x1801fd4d7  call    cs:__guard_dispatch_icall_fptr
0x1801fd4dd  mov     [rbp+47h+arg_8], r12d
0x1801fd4e1  mov     dword ptr [rbp+47h+arg_20], r12d
0x1801fd4e5  mov     rcx, [rbx+50h]
0x1801fd4e9  mov     rax, [rcx]
0x1801fd4ec  lea     r8, [rbp+47h+arg_20]
0x1801fd4f0  lea     rdx, [rbp+47h+arg_8]
0x1801fd4f4  mov     rax, [rax+0B8h]
0x1801fd4fb  call    cs:__guard_dispatch_icall_fptr
0x1801fd501  cmp     dword ptr [rbp+47h+arg_20], r12d
0x1801fd505  setnle  al
0x1801fd508  mov     [rbx+5Ch], al
0x1801fd50b  mov     rax, [rdi]
0x1801fd50e  mov     rcx, rdi
0x1801fd511  mov     rax, [rax+8]
0x1801fd515  call    cs:__guard_dispatch_icall_fptr
0x1801fd51b  mov     rcx, [rbp+47h+var_A8]
0x1801fd51f  test    rcx, rcx
0x1801fd522  jz      short loc_1801FD52B
0x1801fd524  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1801fd52a  nop
0x1801fd52b  mov     rcx, [rsp+100h+Src]
0x1801fd530  test    rcx, rcx
0x1801fd533  jz      short loc_1801FD53C
0x1801fd535  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1801fd53b  nop
0x1801fd53c  mov     rax, rbx
0x1801fd53f  mov     rbx, [rsp+100h+arg_10]
0x1801fd547  add     rsp, 0D0h
0x1801fd54e  pop     r15
0x1801fd550  pop     r14
0x1801fd552  pop     r13
0x1801fd554  pop     r12
0x1801fd556  pop     rdi
0x1801fd557  pop     rsi
0x1801fd558  pop     rbp
0x1801fd559  retn
0x1801fd55a  mov     rdi, r12
0x1801fd55d  jmp     loc_1801FD37E
0x1801fd562  mov     [rsp+100h+Src], rdx
0x1801fd567  mov     eax, [rbp+47h+var_BC]
0x1801fd56a  and     eax, r13d
0x1801fd56d  or      eax, esi
0x1801fd56f  mov     [rbp+47h+var_BC], eax
0x1801fd572  mov     r8d, [rbp+47h+var_C0]
0x1801fd576  mov     rcx, [r14+28h]; Src
0x1801fd57a  call    ?Do@?$TMoveConstructRange@VTextFontSize@Art@@$00@Ofc@@SAXPEAE0K@Z; Ofc::TMoveConstructRange<Art::TextFontSize,1>::Do(uchar *,uchar *,ulong)
0x1801fd57f  mov     eax, [rbp+47h+var_BC]
0x1801fd582  mov     ecx, [rbp+47h+var_C0]
0x1801fd585  mov     edx, [r14+38h]
0x1801fd589  mov     [rbp+47h+var_B8], edx
0x1801fd58c  mov     r8b, [rbp+47h+arg_28]
0x1801fd590  mov     [rbp+47h+var_B4], r8b
0x1801fd594  lea     r9, ??_7PresetPathFactoryState@Art@@6B@; const Art::PresetPathFactoryState::`vftable'
0x1801fd59b  mov     [rbp+47h+var_50], r9
0x1801fd59f  mov     [rbp+47h+var_48], rbx
0x1801fd5a3  lea     r9, ??_7PresetPathInfo@Art@@6B@; const Art::PresetPathInfo::`vftable'
0x1801fd5aa  mov     [rbp+47h+var_B0], r9
0x1801fd5ae  lea     r9, [rbp+47h+var_A8]
0x1801fd5b2  mov     [rbp+47h+arg_20], r9
0x1801fd5b6  mov     [rbp+47h+var_A8], r12
0x1801fd5ba  mov     [rbp+47h+var_A0], ecx
0x1801fd5bd  and     eax, r13d
0x1801fd5c0  mov     [rbp+47h+var_9C], eax
0x1801fd5c3  test    ecx, ecx
0x1801fd5c5  jz      short loc_1801FD61D
0x1801fd5c7  mov     eax, ecx
0x1801fd5c9  shl     rax, 2
0x1801fd5cd  cmp     rax, rdi
0x1801fd5d0  cmovbe  edi, eax
0x1801fd5d3  mov     esi, edi
0x1801fd5d5  shr     esi, 2
0x1801fd5d8  cmp     esi, ecx
0x1801fd5da  jb      loc_1801FD6A5
0x1801fd5e0  mov     ecx, edi
0x1801fd5e2  xor     edx, edx
0x1801fd5e4  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1801fd5ea  mov     rdx, rax; void *
0x1801fd5ed  test    rax, rax
0x1801fd5f0  jnz     short loc_1801FD5F9
0x1801fd5f2  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x1801fd5f8  int     3; Trap to Debugger
0x1801fd5f9  mov     [rbp+47h+var_A8], rdx
0x1801fd5fd  mov     eax, [rbp+47h+var_9C]
0x1801fd600  and     eax, r13d
0x1801fd603  or      eax, esi
0x1801fd605  mov     [rbp+47h+var_9C], eax
0x1801fd608  mov     r8d, [rbp+47h+var_A0]
0x1801fd60c  mov     rcx, [rsp+100h+Src]; Src
0x1801fd611  call    ?Do@?$TMoveConstructRange@VTextFontSize@Art@@$00@Ofc@@SAXPEAE0K@Z; Ofc::TMoveConstructRange<Art::TextFontSize,1>::Do(uchar *,uchar *,ulong)
0x1801fd616  mov     r8b, [rbp+47h+var_B4]
0x1801fd61a  mov     edx, [rbp+47h+var_B8]
0x1801fd61d  mov     [rbp+47h+var_98], edx
0x1801fd620  mov     [rbp+47h+var_94], r8b
0x1801fd624  mov     [rbp+47h+var_60], r12
0x1801fd628  call    cs:__imp_?Instance@IManager@Cache@@SAAEAU12@XZ; Cache::IManager::Instance(void)
0x1801fd62e  mov     r10, rax
0x1801fd631  mov     rcx, [rax]
0x1801fd634  mov     rax, [rcx+28h]
0x1801fd638  lea     rcx, [rbp+47h+var_50]
0x1801fd63c  mov     [rsp+100h+var_E0], rcx
0x1801fd641  lea     r9, [rbp+47h+var_B0]
0x1801fd645  lea     r8, ?c_presetPathCacheDescriptor@Art@@3UCacheDescriptor@Cache@@B; Cache::CacheDescriptor const Art::c_presetPathCacheDescriptor
0x1801fd64c  lea     rdx, [rbp+47h+arg_20]
0x1801fd650  mov     rcx, r10
0x1801fd653  call    cs:__guard_dispatch_icall_fptr
0x1801fd659  mov     rdi, [rax]
0x1801fd65c  mov     [rax], r12
0x1801fd65f  mov     rcx, [rbp+47h+arg_20]
0x1801fd663  test    rcx, rcx
0x1801fd666  jz      short loc_1801FD680
0x1801fd668  mov     [rbp+47h+arg_20], r12
0x1801fd66c  mov     rax, [rcx]
0x1801fd66f  mov     rax, [rax+8]
0x1801fd673  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```
