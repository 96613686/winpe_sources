# Art::Path2DSegmentVisitor::Path2DSegmentVisitor(Art::Path2D const &,unsigned __int64,unsigned __int64,Art::GelGeometry::InstanceData const *,uchar)

- ea: `0x180106a28`
- end: `0x180106ef0`
- name: `??0Path2DSegmentVisitor@Art@@QEAA@AEBVPath2D@1@_K1PEBVInstanceData@GelGeometry@1@E@Z`
- size: `1224`
- prototype: `__int64 __usercall@<rax>(Art::Path2DSegmentVisitor *__hidden this@<rcx>, const struct Art::Path2D *@<rdx>, unsigned __int64@<r8>, unsigned __int64@<r9>, const struct Art::GelGeometry::InstanceData *, unsigned __int8)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180104edc`
- `0x180237470`

## callees

- `0x1800b8cf0`
- `0x1800e92c0`
- `0x180106a28`
- `0x180107c00`
- `0x180279050`
- `0x18028a9c0`

## import_xrefs

- `gfx!?Instance@IManager@Cache@@SAAEAU12@XZ` at `0x180106e0b`
- `gfx!?Instance@IManager@Cache@@SAAEAU12@XZ` at `0x180106e0b`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x180106a6b`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x180106a6b`
- `gfx!?Create@ITransformedPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBUIPath@2@AEBU?$TAffine3x3@N@Math@@@Z` at `0x180106c31`
- `gfx!?Create@ITransformedPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBUIPath@2@AEBU?$TAffine3x3@N@Math@@@Z` at `0x180106cc1`
- `gfx!?Create@ITransformedPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBUIPath@2@AEBU?$TAffine3x3@N@Math@@@Z` at `0x180106c31`
- `gfx!?Create@ITransformedPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBUIPath@2@AEBU?$TAffine3x3@N@Math@@@Z` at `0x180106cc1`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180106b34`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180106de1`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180106b34`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180106de1`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180106b70`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180106b81`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180106d44`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180106d55`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180106b70`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180106b81`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180106d44`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180106d55`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x180106b46`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x180106df3`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x180106b46`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x180106df3`

## pseudocode

```c
Art::Path2DSegmentVisitor *__fastcall Art::Path2DSegmentVisitor::Path2DSegmentVisitor(
        Art::Path2DSegmentVisitor *this,
        const struct Art::Path2D *a2,
        int a3,
        int a4,
        void **p_Src,
        unsigned __int8 a6)
{
  unsigned __int64 v7; // rdi
  const struct Art::GelGeometry::InstanceData *v10; // r14
  unsigned int v11; // r8d
  double v12; // xmm1_8
  double i; // xmm2_8
  __int64 v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // edx
  void *v17; // rdx
  void *v18; // rdx
  unsigned int v19; // esi
  __int64 v20; // rdi
  __int64 v21; // rax
  __int64 v22; // rdx
  double v23; // xmm2_8
  __int64 *v24; // rax
  __int64 v25; // rdi
  __int64 v26; // rcx
  double v27; // xmm2_8
  __int64 *v28; // rax
  __int64 v29; // rsi
  __int64 v30; // rcx
  void *v31; // rdx
  int v33; // edx
  unsigned __int64 v34; // rax
  Mso::Memory *v35; // rax
  __int64 v36; // rax
  __int64 *v37; // rax
  __int64 v38; // rdi
  const struct Art::GelGeometry::InstanceData *v39; // rcx
  void *Src; // [rsp+38h] [rbp-81h] BYREF
  unsigned int v41; // [rsp+40h] [rbp-79h]
  unsigned int v42; // [rsp+44h] [rbp-75h]
  int v43; // [rsp+48h] [rbp-71h]
  unsigned __int8 v44; // [rsp+4Ch] [rbp-6Dh]
  void **v45; // [rsp+50h] [rbp-69h] BYREF
  Mso::Memory *v46; // [rsp+58h] [rbp-61h] BYREF
  int v47; // [rsp+60h] [rbp-59h]
  unsigned int v48; // [rsp+64h] [rbp-55h]
  int v49; // [rsp+68h] [rbp-51h]
  char v50; // [rsp+6Ch] [rbp-4Dh]
  double v51; // [rsp+70h] [rbp-49h] BYREF
  __int128 v52; // [rsp+78h] [rbp-41h]
  double v53; // [rsp+88h] [rbp-31h]
  __int128 v54; // [rsp+90h] [rbp-29h]
  __int64 v55; // [rsp+A0h] [rbp-19h]
  __int64 v56; // [rsp+A8h] [rbp-11h] BYREF
  _QWORD v57[10]; // [rsp+B0h] [rbp-9h] BYREF
  int v58; // [rsp+118h] [rbp+5Fh] BYREF

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
      v12 = (double)a4 / (double)(int)*((_QWORD *)a2 + 4);
    *((double *)this + 13) = v12;
    if ( !v10 )
      goto LABEL_17;
    p_Src = &Src;
    Src = 0;
    v14 = *((unsigned int *)v10 + 12);
    v41 = v14;
    v15 = *((_DWORD *)v10 + 13) & 0x80000000;
    v42 = v15;
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
      goto LABEL_52;
    }
    v17 = Mso::Memory::AllocateEx((Mso::Memory *)v16, 0, v11);
    if ( v17 )
      break;
    ThrowOOM();
LABEL_12:
    ;
  }
  while ( 1 )
  {
    Src = v17;
    v42 = a4 | v42 & 0x80000000;
    Ofc::TMoveConstructRange<Art::TextFontSize,1>::Do(*((void **)v10 + 5), v17);
    v15 = v42;
    v14 = v41;
LABEL_41:
    v33 = *((_DWORD *)v10 + 14);
    v43 = v33;
    LOBYTE(v11) = a6;
    v44 = a6;
    v57[0] = &Art::PresetPathFactoryState::`vftable';
    v57[1] = this;
    v45 = &Art::PresetPathInfo::`vftable';
    p_Src = (void **)&v46;
    v46 = 0;
    v47 = v14;
    v48 = v15 & 0x80000000;
    if ( !(_DWORD)v14 )
      break;
    v34 = 4LL * (unsigned int)v14;
    if ( v34 <= v7 )
      v7 = (unsigned int)v34;
    a4 = (unsigned int)v7 >> 2;
    if ( (unsigned int)v7 >> 2 >= (unsigned int)v14 )
    {
      v35 = (Mso::Memory *)Mso::Memory::AllocateEx((Mso::Memory *)(unsigned int)v7, 0, v11);
      if ( v35 )
      {
        v46 = v35;
        v48 = a4 | v48 & 0x80000000;
        Ofc::TMoveConstructRange<Art::TextFontSize,1>::Do(Src, v35);
        LOBYTE(v11) = v44;
        v33 = v43;
      }
      else
      {
        ThrowOOM();
      }
      break;
    }
LABEL_52:
    Ofc::COutOfMemoryException::ThrowTag(0x1E318643u);
  }
  v49 = v33;
  v50 = v11;
  v55 = 0;
  v36 = Cache::IManager::Instance(v14);
  v37 = (__int64 *)(*(__int64 (__fastcall **)(__int64, void ***, void *, void ***, _QWORD *))(*(_QWORD *)v36 + 40LL))(
                     v36,
                     &p_Src,
                     &Art::c_presetPathCacheDescriptor,
                     &v45,
                     v57);
  v38 = *v37;
  *v37 = 0;
  v39 = (const struct Art::GelGeometry::InstanceData *)p_Src;
  if ( p_Src )
  {
    p_Src = 0;
    (*(void (__fastcall **)(const struct Art::GelGeometry::InstanceData *))(*(_QWORD *)v39 + 8LL))(v39);
  }
  v55 = 0;
  v57[2] = v38;
  if ( !v38 )
  {
    if ( v46 )
      Mso::Memory::Free(v46, v18);
    if ( Src )
      Mso::Memory::Free((Mso::Memory *)Src, v18);
LABEL_17:
    v19 = 0;
    while ( 1 )
    {
      v20 = v19 >= *((_DWORD *)a2 + 4) ? 0LL : *((_QWORD *)a2 + 1) + 16LL * v19;
      ++v19;
      if ( !v20 )
        break;
      if ( *(_QWORD *)(v20 + 8) <= 1u )
        Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::DemandInit(v20);
      v21 = *(_QWORD *)(v20 + 8);
      if ( v21 )
        (*(void (__fastcall **)(__int64, Art::Path2DSegmentVisitor *))(v21 + 56))(v20, this);
    }
    Art::Path2DSegmentVisitor::FinalizePath(this);
    if ( v10 )
    {
      v22 = *((_QWORD *)this + 10);
      if ( v22 )
      {
        v23 = (double)(int)*((_QWORD *)v10 + 3) / (double)(int)*((_QWORD *)v10 + 1);
        v51 = (double)(int)*((_QWORD *)v10 + 2) / (double)(int)*(_QWORD *)v10;
        v53 = v23;
        v54 = 0;
        v52 = 0;
        v24 = (__int64 *)GEL::ITransformedPath::Create(&p_Src, v22, &v51);
        v25 = *v24;
        *v24 = 0;
        v26 = *((_QWORD *)this + 10);
        if ( v26 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
        *((_QWORD *)this + 10) = v25;
        if ( p_Src )
          (*((void (__fastcall **)(void **))*p_Src + 1))(p_Src);
      }
    }
    return this;
  }
  v27 = (double)(int)*((_QWORD *)v10 + 3) / (double)(int)*((_QWORD *)v10 + 1);
  v51 = (double)(int)*((_QWORD *)v10 + 2) / (double)(int)*(_QWORD *)v10;
  v53 = v27;
  v54 = 0;
  v52 = 0;
  v28 = (__int64 *)GEL::ITransformedPath::Create(&v56, v38, &v51);
  v29 = *v28;
  *v28 = 0;
  v30 = *((_QWORD *)this + 10);
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
  *((_QWORD *)this + 10) = v29;
  if ( v56 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 8LL))(v56);
  v58 = 0;
  LODWORD(p_Src) = 0;
  (*(void (__fastcall **)(_QWORD, int *, void ***))(**((_QWORD **)this + 10) + 184LL))(
    *((_QWORD *)this + 10),
    &v58,
    &p_Src);
  *((_BYTE *)this + 92) = (int)p_Src > 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 8LL))(v38);
  if ( v46 )
    Mso::Memory::Free(v46, v31);
  if ( Src )
    Mso::Memory::Free((Mso::Memory *)Src, v31);
  return this;
}

```

## disassembly

```asm
0x180106a28  mov     [rsp-8+arg_10], rbx
0x180106a2d  mov     [rsp-8+arg_0], rcx
0x180106a32  push    rbp
0x180106a33  push    rsi
0x180106a34  push    rdi
0x180106a35  push    r12
0x180106a37  push    r13
0x180106a39  push    r14
0x180106a3b  push    r15
0x180106a3d  lea     rbp, [rsp-17h]
0x180106a42  sub     rsp, 0D0h
0x180106a49  mov     rsi, r9
0x180106a4c  mov     rdi, r8
0x180106a4f  mov     r15, rdx
0x180106a52  mov     rbx, rcx
0x180106a55  mov     r14, [rbp+47h+arg_20]
0x180106a59  lea     rax, ??_7Path2DSegmentVisitor@Art@@6B@; const Art::Path2DSegmentVisitor::`vftable'
0x180106a60  mov     [rcx], rax
0x180106a63  mov     [rcx+8], rdx
0x180106a67  add     rcx, 10h
0x180106a6b  call    cs:__imp_??0PathBuilder@GEL@@QEAA@XZ; GEL::PathBuilder::PathBuilder(void)
0x180106a71  xor     r12d, r12d
0x180106a74  mov     [rbx+50h], r12
0x180106a78  mov     eax, [r15+28h]
0x180106a7c  mov     [rbx+58h], eax
0x180106a7f  mov     [rbx+5Ch], r12b
0x180106a83  mov     al, [r15+2Dh]
0x180106a87  mov     [rbx+5Dh], al
0x180106a8a  cmp     [r15+2Ch], r12b
0x180106a8e  setz    al
0x180106a91  mov     [rbx+5Eh], al
0x180106a94  movsd   xmm1, cs:__real@3ff0000000000000
0x180106a9c  cmp     [r15+18h], r12
0x180106aa0  jnz     loc_180106B4D
0x180106aa6  movaps  xmm2, xmm1
0x180106aa9  movsd   qword ptr [rbx+60h], xmm2
0x180106aae  cmp     [r15+20h], r12
0x180106ab2  jz      short loc_180106AC9
0x180106ab4  xorps   xmm1, xmm1
0x180106ab7  cvtsi2sd xmm1, rsi
0x180106abc  xorps   xmm0, xmm0
0x180106abf  cvtsi2sd xmm0, qword ptr [r15+20h]
0x180106ac5  divsd   xmm1, xmm0
0x180106ac9  movsd   qword ptr [rbx+68h], xmm1
0x180106ace  test    r14, r14
0x180106ad1  jz      loc_180106B87
0x180106ad7  lea     rax, ??_7PresetPathInfo@Art@@6B@; const Art::PresetPathInfo::`vftable'
0x180106ade  mov     [rsp+100h+var_D0], rax
0x180106ae3  lea     rax, [rsp+100h+Src]
0x180106ae8  mov     [rbp+47h+arg_20], rax
0x180106aec  mov     [rsp+100h+Src], r12
0x180106af1  mov     ecx, [r14+30h]
0x180106af5  mov     [rbp+47h+var_C0], ecx
0x180106af8  mov     eax, [r14+34h]
0x180106afc  mov     r13d, 80000000h
0x180106b02  and     eax, r13d
0x180106b05  mov     [rbp+47h+var_BC], eax
0x180106b08  mov     edi, 0FFFFFFFFh
0x180106b0d  test    ecx, ecx
0x180106b0f  jz      loc_180106D82
0x180106b15  mov     eax, ecx
0x180106b17  shl     rax, 2
0x180106b1b  mov     edx, edi
0x180106b1d  cmp     rax, rdi
0x180106b20  cmovbe  edx, eax
0x180106b23  mov     esi, edx
0x180106b25  shr     esi, 2
0x180106b28  cmp     esi, ecx
0x180106b2a  jb      loc_180106E73
0x180106b30  mov     ecx, edx
0x180106b32  xor     edx, edx
0x180106b34  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x180106b3a  mov     rdx, rax
0x180106b3d  test    rax, rax
0x180106b40  jnz     loc_180106E91
0x180106b46  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x180106b4c  nop
0x180106b4d  xorps   xmm2, xmm2
0x180106b50  cvtsi2sd xmm2, rdi
0x180106b55  xorps   xmm0, xmm0
0x180106b58  cvtsi2sd xmm0, qword ptr [r15+18h]
0x180106b5e  divsd   xmm2, xmm0
0x180106b62  jmp     loc_180106AA9
0x180106b67  mov     rcx, [rbp+47h+var_A8]
0x180106b6b  test    rcx, rcx
0x180106b6e  jz      short loc_180106B77
0x180106b70  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180106b76  nop
0x180106b77  mov     rcx, [rsp+100h+Src]
0x180106b7c  test    rcx, rcx
0x180106b7f  jz      short loc_180106B87
0x180106b81  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180106b87  mov     esi, r12d
0x180106b8a  cmp     esi, [r15+10h]
0x180106b8e  jnb     loc_180106D7A
0x180106b94  mov     edi, esi
0x180106b96  shl     rdi, 4
0x180106b9a  add     rdi, [r15+8]
0x180106b9e  inc     esi
0x180106ba0  test    rdi, rdi
0x180106ba3  jz      short loc_180106BCB
0x180106ba5  cmp     qword ptr [rdi+8], 1
0x180106baa  jbe     loc_180106EE2
0x180106bb0  mov     rax, [rdi+8]
0x180106bb4  test    rax, rax
0x180106bb7  jz      short loc_180106B8A
0x180106bb9  mov     rdx, rbx
0x180106bbc  mov     rcx, rdi
0x180106bbf  mov     rax, [rax+38h]
0x180106bc3  call    cs:__guard_dispatch_icall_fptr
0x180106bc9  jmp     short loc_180106B8A
0x180106bcb  mov     rcx, rbx; this
0x180106bce  call    ?FinalizePath@Path2DSegmentVisitor@Art@@IEAAXXZ; Art::Path2DSegmentVisitor::FinalizePath(void)
0x180106bd3  test    r14, r14
0x180106bd6  jz      loc_180106D5C
0x180106bdc  mov     rdx, [rbx+50h]
0x180106be0  test    rdx, rdx
0x180106be3  jz      loc_180106D5C
0x180106be9  xorps   xmm2, xmm2
0x180106bec  cvtsi2sd xmm2, qword ptr [r14+18h]
0x180106bf2  xorps   xmm0, xmm0
0x180106bf5  cvtsi2sd xmm0, qword ptr [r14+8]
0x180106bfb  divsd   xmm2, xmm0
0x180106bff  xorps   xmm1, xmm1
0x180106c02  cvtsi2sd xmm1, qword ptr [r14+10h]
0x180106c08  xorps   xmm0, xmm0
0x180106c0b  cvtsi2sd xmm0, qword ptr [r14]
0x180106c10  divsd   xmm1, xmm0
0x180106c14  movsd   [rbp+47h+var_90], xmm1
0x180106c19  movsd   [rbp+47h+var_78], xmm2
0x180106c1e  xorps   xmm0, xmm0
0x180106c21  movups  [rbp+47h+var_70], xmm0
0x180106c25  movups  [rbp+47h+var_88], xmm0
0x180106c29  lea     r8, [rbp+47h+var_90]
0x180106c2d  lea     rcx, [rbp+47h+arg_20]
0x180106c31  call    cs:__imp_?Create@ITransformedPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBUIPath@2@AEBU?$TAffine3x3@N@Math@@@Z; GEL::ITransformedPath::Create(GEL::IPath const &,Math::TAffine3x3<double> const &)
0x180106c37  mov     rdi, [rax]
0x180106c3a  mov     [rax], r12
0x180106c3d  mov     rcx, [rbx+50h]
0x180106c41  test    rcx, rcx
0x180106c44  jz      short loc_180106C53
0x180106c46  mov     rax, [rcx]
0x180106c49  mov     rax, [rax+8]
0x180106c4d  call    cs:__guard_dispatch_icall_fptr
0x180106c53  mov     [rbx+50h], rdi
0x180106c57  mov     rcx, [rbp+47h+arg_20]
0x180106c5b  test    rcx, rcx
0x180106c5e  jz      loc_180106D5C
0x180106c64  mov     rax, [rcx]
0x180106c67  mov     rax, [rax+8]
0x180106c6b  call    cs:__guard_dispatch_icall_fptr
0x180106c71  jmp     loc_180106D5C
0x180106c76  xorps   xmm2, xmm2
0x180106c79  cvtsi2sd xmm2, qword ptr [r14+18h]
0x180106c7f  xorps   xmm0, xmm0
0x180106c82  cvtsi2sd xmm0, qword ptr [r14+8]
0x180106c88  divsd   xmm2, xmm0
0x180106c8c  xorps   xmm1, xmm1
0x180106c8f  cvtsi2sd xmm1, qword ptr [r14+10h]
0x180106c95  xorps   xmm0, xmm0
0x180106c98  cvtsi2sd xmm0, qword ptr [r14]
0x180106c9d  divsd   xmm1, xmm0
0x180106ca1  movsd   [rbp+47h+var_90], xmm1
0x180106ca6  movsd   [rbp+47h+var_78], xmm2
0x180106cab  xorps   xmm0, xmm0
0x180106cae  movups  [rbp+47h+var_70], xmm0
0x180106cb2  movups  [rbp+47h+var_88], xmm0
0x180106cb6  lea     r8, [rbp+47h+var_90]
0x180106cba  mov     rdx, rdi
0x180106cbd  lea     rcx, [rbp+47h+var_58]
0x180106cc1  call    cs:__imp_?Create@ITransformedPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBUIPath@2@AEBU?$TAffine3x3@N@Math@@@Z; GEL::ITransformedPath::Create(GEL::IPath const &,Math::TAffine3x3<double> const &)
0x180106cc7  mov     rsi, [rax]
0x180106cca  mov     [rax], r12
0x180106ccd  mov     rcx, [rbx+50h]
0x180106cd1  test    rcx, rcx
0x180106cd4  jz      short loc_180106CE3
0x180106cd6  mov     rax, [rcx]
0x180106cd9  mov     rax, [rax+8]
0x180106cdd  call    cs:__guard_dispatch_icall_fptr
0x180106ce3  mov     [rbx+50h], rsi
0x180106ce7  mov     rcx, [rbp+47h+var_58]
0x180106ceb  test    rcx, rcx
0x180106cee  jz      short loc_180106CFD
0x180106cf0  mov     rax, [rcx]
0x180106cf3  mov     rax, [rax+8]
0x180106cf7  call    cs:__guard_dispatch_icall_fptr
0x180106cfd  mov     [rbp+47h+arg_8], r12d
0x180106d01  mov     dword ptr [rbp+47h+arg_20], r12d
0x180106d05  mov     rcx, [rbx+50h]
0x180106d09  mov     rax, [rcx]
0x180106d0c  lea     r8, [rbp+47h+arg_20]
0x180106d10  lea     rdx, [rbp+47h+arg_8]
0x180106d14  mov     rax, [rax+0B8h]
0x180106d1b  call    cs:__guard_dispatch_icall_fptr
0x180106d21  cmp     dword ptr [rbp+47h+arg_20], r12d
0x180106d25  setnle  al
0x180106d28  mov     [rbx+5Ch], al
0x180106d2b  mov     rax, [rdi]
0x180106d2e  mov     rcx, rdi
0x180106d31  mov     rax, [rax+8]
0x180106d35  call    cs:__guard_dispatch_icall_fptr
0x180106d3b  mov     rcx, [rbp+47h+var_A8]
0x180106d3f  test    rcx, rcx
0x180106d42  jz      short loc_180106D4B
0x180106d44  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180106d4a  nop
0x180106d4b  mov     rcx, [rsp+100h+Src]
0x180106d50  test    rcx, rcx
0x180106d53  jz      short loc_180106D5C
0x180106d55  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180106d5b  nop
0x180106d5c  mov     rax, rbx
0x180106d5f  mov     rbx, [rsp+100h+arg_10]
0x180106d67  add     rsp, 0D0h
0x180106d6e  pop     r15
0x180106d70  pop     r14
0x180106d72  pop     r13
0x180106d74  pop     r12
0x180106d76  pop     rdi
0x180106d77  pop     rsi
0x180106d78  pop     rbp
0x180106d79  retn
0x180106d7a  mov     rdi, r12
0x180106d7d  jmp     loc_180106B9E
0x180106d82  mov     edx, [r14+38h]
0x180106d86  mov     [rbp+47h+var_B8], edx
0x180106d89  mov     r8b, [rbp+47h+arg_28]
0x180106d8d  mov     [rbp+47h+var_B4], r8b
0x180106d91  lea     r9, ??_7PresetPathFactoryState@Art@@6B@; const Art::PresetPathFactoryState::`vftable'
0x180106d98  mov     [rbp+47h+var_50], r9
0x180106d9c  mov     [rbp+47h+var_48], rbx
0x180106da0  lea     r9, ??_7PresetPathInfo@Art@@6B@; const Art::PresetPathInfo::`vftable'
0x180106da7  mov     [rbp+47h+var_B0], r9
0x180106dab  lea     r9, [rbp+47h+var_A8]
0x180106daf  mov     [rbp+47h+arg_20], r9
0x180106db3  mov     [rbp+47h+var_A8], r12
0x180106db7  mov     [rbp+47h+var_A0], ecx
0x180106dba  and     eax, r13d
0x180106dbd  mov     [rbp+47h+var_9C], eax
0x180106dc0  test    ecx, ecx
0x180106dc2  jz      short loc_180106E00
0x180106dc4  mov     eax, ecx
0x180106dc6  shl     rax, 2
0x180106dca  cmp     rax, rdi
0x180106dcd  cmovbe  edi, eax
0x180106dd0  mov     esi, edi
0x180106dd2  shr     esi, 2
0x180106dd5  cmp     esi, ecx
0x180106dd7  jb      loc_180106E81
0x180106ddd  mov     ecx, edi
0x180106ddf  xor     edx, edx
0x180106de1  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x180106de7  mov     rdx, rax; void *
0x180106dea  test    rax, rax
0x180106ded  jnz     loc_180106EB9
0x180106df3  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x180106df9  nop
0x180106dfa  nop     word ptr [rax+rax+00h]
0x180106e00  mov     [rbp+47h+var_98], edx
0x180106e03  mov     [rbp+47h+var_94], r8b
0x180106e07  mov     [rbp+47h+var_60], r12
0x180106e0b  call    cs:__imp_?Instance@IManager@Cache@@SAAEAU12@XZ; Cache::IManager::Instance(void)
0x180106e11  mov     r10, rax
0x180106e14  mov     rcx, [rax]
0x180106e17  mov     rax, [rcx+28h]
0x180106e1b  lea     rcx, [rbp+47h+var_50]
0x180106e1f  mov     [rsp+100h+var_E0], rcx
0x180106e24  lea     r9, [rbp+47h+var_B0]
0x180106e28  lea     r8, ?c_presetPathCacheDescriptor@Art@@3UCacheDescriptor@Cache@@B; Cache::CacheDescriptor const Art::c_presetPathCacheDescriptor
0x180106e2f  lea     rdx, [rbp+47h+arg_20]
0x180106e33  mov     rcx, r10
0x180106e36  call    cs:__guard_dispatch_icall_fptr
0x180106e3c  mov     rdi, [rax]
0x180106e3f  mov     [rax], r12
0x180106e42  mov     rcx, [rbp+47h+arg_20]
0x180106e46  test    rcx, rcx
0x180106e49  jz      short loc_180106E5D
0x180106e4b  mov     [rbp+47h+arg_20], r12
0x180106e4f  mov     rax, [rcx]
0x180106e52  mov     rax, [rax+8]
0x180106e56  call    cs:__guard_dispatch_icall_fptr
0x180106e5c  nop
0x180106e5d  mov     [rbp+47h+var_60], r12
0x180106e61  mov     [rbp+47h+var_40], rdi
0x180106e65  test    rdi, rdi
0x180106e68  jnz     loc_180106C76
0x180106e6e  jmp     loc_180106B67
0x180106e73  mov     ecx, 1E318643h; unsigned int
0x180106e78  call    ?ThrowTag@COutOfMemoryException@Ofc@@SAXK@Z; Ofc::COutOfMemoryException::ThrowTag(ulong)
0x180106e7d  nop
0x180106e7e  jmp     short $+2
0x180106e80  nop
0x180106e81  mov     ecx, 1E318643h; unsigned int
0x180106e86  call    ?ThrowTag@COutOfMemoryException@Ofc@@SAXK@Z; Ofc::COutOfMemoryException::ThrowTag(ulong)
0x180106e8b  nop
0x180106e8c  jmp     short loc_180106E90
0x180106e90  nop
0x180106e91  mov     [rsp+100h+Src], rdx
0x180106e96  mov     eax, [rbp+47h+var_BC]
0x180106e99  and     eax, r13d
  ... truncated ...
```
