# CPreComputeContext::PostSubgraph(CVisualTree const *,bool *)

- ea: `0x1800ae8fc`
- end: `0x1800af1c0`
- name: `?PostSubgraph@CPreComputeContext@@QEAAJPEBVCVisualTree@@PEA_N@Z`
- size: `2244`
- prototype: `__int64 __fastcall(CPreComputeContext *__hidden this, const struct CVisualTree *, bool *)`
- caller_count: `1`
- callee_count: `41`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800acdc0`

## callees

- `0x1800192ac`
- `0x18001ad30`
- `0x18003abec`
- `0x180040728`
- `0x180042854`
- `0x18005e990`
- `0x18005f8c0`
- `0x18008c730`
- `0x180092080`
- `0x180093660`
- `0x18009d0b0`
- `0x18009e0f8`
- `0x1800a7f30`
- `0x1800a801c`
- `0x1800a8fd0`
- `0x1800ae8fc`
- `0x1800d1f10`
- `0x1800d2900`
- `0x1800d2b10`
- `0x1801491d0`
- `0x180151660`
- `0x180152410`
- `0x180153c80`
- `0x180166670`
- `0x1801671d0`
- `0x180171130`
- `0x18017a3d0`
- `0x18017dda0`
- `0x180181dd0`
- `0x180183200`
- `0x180185850`
- `0x1801b28a8`
- `0x1801bac98`
- `0x180228490`
- `0x18022943c`
- `0x180229718`
- `0x18022976c`
- `0x1802328b8`
- `0x1802328ec`
- `0x1802766f8`
- `0x1802b6010`

## import_xrefs

- `ext-ms-win-compositor-hosting-l1-3-0!NotifyInputSinkTransformChanged` at `0x1800af0e0`
- `ext-ms-win-compositor-hosting-l1-3-0!NotifyInputSinkTransformChanged` at `0x1800af0e0`
- `ext-ms-win-compositor-hosting-l1-2-1!NotifyInputSinkParented` at `0x1800aeff5`
- `ext-ms-win-compositor-hosting-l1-2-1!NotifyInputSinkParented` at `0x1800aeff5`

## string_xrefs

- `0x1800ae9be`: `onecoreuap\windows\dwm\dwmcore\engine\precomputecontext.cpp`
- `0x1800af0ba`: `onecoreuap\windows\dwm\dwmcore\engine\precomputecontext.cpp`
- `0x1800af120`: `onecoreuap\windows\dwm\dwmcore\engine\precomputecontext.cpp`
- `0x1800aef7e`: `PreCompute-AddedDirtyRectInPostSubgraph`

## pseudocode

```c
__int64 __fastcall CPreComputeContext::PostSubgraph(CPreComputeContext *this, const struct CVisualTree *a2, bool *a3)
{
  __int64 v3; // r12
  __int64 v4; // r13
  __int64 v6; // rsi
  __int64 v8; // rax
  __int64 v10; // r13
  const struct CVisualTree *v11; // rdx
  int v12; // ebx
  __int64 v13; // rdx
  char v15; // al
  bool *v16; // r8
  const struct CVisual *TransformParent; // rax
  bool *v18; // r8
  __int64 v19; // rbx
  const struct CVisual *v20; // r12
  __int64 v21; // rdi
  bool v22; // r9
  int v23; // edx
  int v24; // ecx
  float v25; // xmm5_4
  float v26; // xmm2_4
  float v27; // xmm4_4
  __int32 v28; // xmm1_4
  float v29; // xmm7_4
  float v30; // xmm3_4
  float v31; // xmm6_4
  char v32; // al
  int v33; // eax
  int v34; // ebx
  bool HasInputSink; // al
  int v36; // r10d
  int v37; // ebx
  char v38; // al
  int v39; // ecx
  bool v40; // al
  int v41; // r8d
  int v42; // ecx
  int v43; // edx
  int v44; // ecx
  int v45; // ecx
  unsigned int v46; // r8d
  __int64 v47; // rbx
  __int64 v48; // rdi
  struct _LIST_ENTRY *v49; // r12
  struct _LIST_ENTRY **p_Blink; // r9
  struct _LIST_ENTRY *TreeDataListHead; // rax
  struct _LIST_ENTRY *i; // rcx
  int v53; // eax
  __int64 v54; // r9
  __int64 v55; // rdi
  CVisualTreePath *v56; // rbx
  __int64 v57; // rax
  CTreeData *v58; // rdi
  void *InputHandle; // rbx
  _QWORD *TopByReference; // rax
  char IsEnabled; // al
  char v62; // cl
  int v63; // edi
  __int64 v64; // rdx
  CPreComputeSubTreeContext *v65; // rbx
  CPreComputeSubTreeContext *v66; // rdi
  const struct CVisual *Parent; // rax
  struct CVisual *v68; // rdx
  CBspPreComputeHelper *v69; // rcx
  int v70; // eax
  unsigned int v71; // r15d
  int v72; // [rsp+20h] [rbp-E0h]
  bool v73; // [rsp+50h] [rbp-B0h]
  _DWORD v74[4]; // [rsp+60h] [rbp-A0h] BYREF
  CTreeData *TreeData; // [rsp+70h] [rbp-90h]
  __int64 v76; // [rsp+78h] [rbp-88h] BYREF
  _OWORD v77[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v78; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v79; // [rsp+B0h] [rbp-50h]
  void *v80; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v81[72]; // [rsp+C8h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v3 = *((_QWORD *)this + 192);
  v4 = *((_QWORD *)this + 1);
  v6 = *((_QWORD *)this + 191);
  TreeData = 0;
  v8 = *(_QWORD *)a2;
  v76 = v3;
  v10 = v4 - 352;
  if ( (*(unsigned __int8 (__fastcall **)(const struct CVisualTree *))(v8 + 192))(a2) )
    TreeData = CVisual::FindTreeData((CVisual *)v6, a2);
  *a3 = 1;
  if ( *(_BYTE *)(v10 + 345) )
    goto LABEL_125;
  v12 = CLightStack::PopLightsFromVisual((CPreComputeContext *)((char *)this + 1176), (const struct CVisual *)v6, a2);
  if ( v12 < 0 )
  {
    v13 = 899;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\precomputecontext.cpp",
      (const char *)(unsigned int)v12,
      v72);
    return (unsigned int)v12;
  }
  v15 = *(_BYTE *)(v6 + 96);
  v73 = 0;
  if ( (v15 & 1) != 0 )
  {
    if ( CVisual::ResolveTransformParent((CVisual *)v6, v11) )
    {
      TransformParent = CVisual::GetTransformParent((CVisual *)v6, a2, v16);
      v19 = *(_QWORD *)this;
      v20 = TransformParent;
      v21 = *((_QWORD *)this + 1);
      while ( v19 != v21 )
      {
        if ( v20 != CVisual::GetTransformParent((CVisual *)v6, *(const struct CVisualTree **)(v19 + 328), v18) )
        {
          v22 = 1;
          goto LABEL_16;
        }
        v19 += 352;
      }
      v22 = 0;
    }
    else
    {
      v20 = 0;
      v22 = 0;
    }
LABEL_16:
    v12 = CVisual::ConvertInnerToOuterBounds((CVisual *)v6, a2, v20, v22);
    if ( v12 < 0 )
    {
      v13 = 930;
      goto LABEL_6;
    }
    v73 = 1;
    if ( CCommonRegistryData::EnableDwmMoveRectHints )
    {
      if ( (*(unsigned __int8 (__fastcall **)(const struct CVisualTree *))(*(_QWORD *)a2 + 192LL))(a2) )
      {
        memset(v77, 0, 24);
        v79 = *(_OWORD *)&_mm_unpackhi_pd(*(__m128d *)((char *)v77 + 8), *(__m128d *)((char *)v77 + 8));
        v78 = v77[0];
        CWatermarkStack<CPreComputeContext::MoveRectHintData::MoveBounds,64,2,10>::TopOrDefault(
          (char *)this + 1432,
          v77,
          &v78);
        if ( *(_QWORD *)&v77[0] == v6 )
        {
          v25 = *(float *)(v6 + 144);
          v26 = *((float *)v77 + 2);
          v27 = *(float *)(v6 + 152) - v25;
          COERCE_FLOAT(v28 = _mm_load_si128((const __m128i *)&_xmm).m128i_i32[0]);
          if ( COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(*(float *)&v77[1] - *((float *)v77 + 2)) - v27) & v28) <= 0.000081380211 )
          {
            v29 = *(float *)(v6 + 148);
            v30 = *((float *)v77 + 3);
            v31 = *(float *)(v6 + 156) - v29;
            if ( COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(*((float *)&v77[1] + 1) - *((float *)v77 + 3)) - v31) & v28) <= 0.000081380211
              && (COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v77 + 2) - v25) & v28) > 0.000081380211
               || COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v77 + 3) - v29) & v28) > 0.000081380211) )
            {
              v32 = *((_BYTE *)this + 1480);
              if ( v32 && (float)(v31 * v27) <= (float)(*((float *)this + 369) * *((float *)this + 368)) )
              {
                LOBYTE(v24) = 0;
              }
              else
              {
                *((_DWORD *)this + 364) = DWORD2(v77[0]);
                LOBYTE(v24) = 1;
                *((float *)this + 365) = v30;
                *((float *)this + 366) = v25;
                *((float *)this + 367) = v29;
                *((float *)this + 368) = v27;
                *((float *)this + 369) = v31;
                if ( !v32 )
                  *((_BYTE *)this + 1480) = 1;
              }
              if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x20) != 0 )
              {
                *(float *)v74 = v26;
                *(float *)&v74[1] = v30;
                *(float *)&v74[2] = v25 - v26;
                *(float *)&v74[3] = v29 - v30;
                McTemplateU0xtnnn_EventWriteTransfer(v24, v23, v6, (unsigned __int8)v24);
              }
            }
          }
          v33 = *((_DWORD *)this + 360);
          if ( v33 )
            *((_DWORD *)this + 360) = v33 - 1;
        }
      }
    }
    *(_BYTE *)(v6 + 96) &= ~1u;
    v15 = *(_BYTE *)(v6 + 96);
    v3 = v76;
  }
  if ( (v15 & 0x10) != 0 )
  {
    v34 = (int)(*(_DWORD *)(v6 + 96) << 15) >> 23;
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v6 + 272LL))(v6) && (v34 & 1) == 0 )
      CVisual::HasSingleD2DBitmapOrPrimitiveGroup((CVisual *)v6);
    CVisual::Has3DContent((CVisual *)v6);
    (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 344LL))(v6);
    CVisual::HasPixelSnappedContent((CVisual *)v6);
    HasInputSink = CVisual::HasInputSink((CVisual *)v6);
    v37 = v36 | 0x10;
    if ( !HasInputSink )
      v37 = v36;
    v38 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 280LL))(v6);
    v39 = v37 | 0x40;
    if ( !v38 )
      v39 = v37;
    *(_DWORD *)(v6 + 96) = (v39 << 8) ^ (*(_DWORD *)(v6 + 96) ^ (v39 << 8)) & 0xFFFE00FF;
  }
  if ( v3 )
  {
    v40 = CVisual::HasInputSink((CVisual *)v6);
    v41 = *(_DWORD *)(v3 + 96);
    v42 = 32;
    if ( (*(_BYTE *)(v6 + 102) & 4) == 0 )
      v42 = 32 * v40;
    v43 = v42 | 0x80;
    if ( (*(_DWORD *)(v6 + 96) & 0x60000) == 0 )
      v43 = v42;
    v44 = v43 | 0x100;
    if ( (*(_DWORD *)(v6 + 96) & *(_DWORD *)(v3 + 96) & 0x100) == 0 )
      v44 = v43;
    v45 = *(_DWORD *)(v6 + 96) | v41 | (v44 << 8);
    v46 = v45 ^ (v45 ^ v41) & 0xFFFE00FF;
    *(_DWORD *)(v3 + 96) = v46;
    if ( (v46 & 1) != 0 )
      TMil3DRect<float,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>,D3D_RECT_F,MilPointAndSizeF,RectUniqueness::NotNeeded>::UnionUnsafe(
        v3 + 168,
        v6 + 144);
  }
  if ( (*(_BYTE *)(v6 + 103) & 2) != 0 )
  {
    v12 = CPreComputeContext::ProcessPostSubgraphWindowBackdropInput(this, (struct CVisual *)v6);
    if ( v12 < 0 )
    {
      v13 = 1130;
      goto LABEL_6;
    }
  }
  v47 = *(_QWORD *)this;
  v48 = *((_QWORD *)this + 1);
  while ( v47 != v48 )
  {
    v49 = *(struct _LIST_ENTRY **)(v47 + 328);
    if ( ((unsigned __int8 (__fastcall *)(struct _LIST_ENTRY *))v49->Flink[12].Flink)(v49) )
    {
      p_Blink = (struct _LIST_ENTRY **)(v6 + 320);
    }
    else
    {
      TreeDataListHead = CVisual::GetTreeDataListHead((CVisual *)v6);
      if ( TreeDataListHead )
      {
        for ( i = TreeDataListHead->Flink; i != TreeDataListHead; i = i->Flink )
        {
          if ( i[2].Flink == v49 )
          {
            p_Blink = &i[-22].Blink;
            break;
          }
        }
      }
    }
    if ( *((_BYTE *)p_Blink + 8) )
    {
      v53 = *(_DWORD *)(v47 + 280);
      if ( v53 )
        *(_DWORD *)(v47 + 280) = v53 - 1;
      *((_BYTE *)p_Blink + 8) = 0;
    }
    if ( *((_BYTE *)p_Blink + 9) )
    {
      CBaseClipStack::Pop((CBaseClipStack *)(v47 + 296));
      *(_BYTE *)(v54 + 9) = 0;
    }
    v47 += 352;
  }
  if ( (*(_BYTE *)(v6 + 100) & 4) != 0 )
    CWatermarkStack<D2D_VECTOR_2F,2,2,10>::Pop((char *)this + 1128);
  if ( (*(_BYTE *)(v6 + 100) & 2) != 0 )
    CWatermarkStack<void *,2,2,10>::Pop((char *)this + 1104);
  if ( (*(_BYTE *)(v6 + 100) & 8) != 0 )
    CWatermarkStack<void *,2,2,10>::Pop((char *)this + 1152);
  if ( (*(_BYTE *)(v6 + 100) & 0x10) != 0 )
    *((_BYTE *)this + 1592) = *((_BYTE *)this + 1592) == 0;
  if ( *(char *)(v6 + 102) < 0 )
  {
    v12 = CPreComputeContext::ProcessPostSubgraphBackdropInput(this, (struct CVisual *)v6, v73);
    if ( v12 < 0 )
    {
      v13 = 1178;
      goto LABEL_6;
    }
  }
  if ( (**(_DWORD **)(v6 + 224) & 0x800000) != 0 )
  {
    v12 = CPreComputeContext::ProcessPostSubgraphWindowBackgroundTreatment(this, (struct CVisual *)v6, v73);
    if ( v12 < 0 )
    {
      v13 = 1183;
      goto LABEL_6;
    }
  }
  if ( (*(_BYTE *)(v6 + 96) & 4) != 0 )
  {
    --*(_DWORD *)(v10 + 340);
    v12 = CPreComputeContext::AddLocalBoundsToSubTreesDirtyRegion(this, (struct CVisual *)v6);
    if ( v12 < 0 )
    {
      v13 = 1191;
      goto LABEL_6;
    }
    if ( dword_1803B9890 && (*(int *)(v6 + 256) > 0 || *(int *)(v6 + 260) > 0) )
    {
      v55 = DwmDbg::DbgString::DbgString((DwmDbg::DbgString *)&v76, word_1802D2E32);
      v56 = CVisualTreePath::CVisualTreePath((CVisualTreePath *)&v80, a2);
      v57 = DwmDbg::DbgString::DbgString((DwmDbg::DbgString *)v74, "PreCompute-AddedDirtyRectInPostSubgraph");
      DwmDbg::Backdrops::LogTreeWalkEtwEvent(v57, v6, a2, v56, v55);
      detail::vector_facade<CVisualTreePath::VisualTreePathUnit,detail::buffer_impl<CVisualTreePath::VisualTreePathUnit,2,1,detail::liberal_expansion_policy>>::~vector_facade<CVisualTreePath::VisualTreePathUnit,detail::buffer_impl<CVisualTreePath::VisualTreePathUnit,2,1,detail::liberal_expansion_policy>>(&v80);
    }
  }
  v58 = TreeData;
  if ( TreeData )
  {
    InputHandle = CVisual::GetInputHandle((CVisual *)v6);
    if ( InputHandle )
    {
      if ( ((*(_BYTE *)(v6 + 100) & 0x20) != 0 || *((_BYTE *)this + 1592))
        && (unsigned __int8)IsNotifyInputSinkParentedPresent() )
      {
        TopByReference = (_QWORD *)CWatermarkStack<CBspNode *,64,2,10>::GetTopByReference((char *)this + 1152);
        NotifyInputSinkParented(InputHandle, *TopByReference);
      }
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Comp_Racy>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Comp_Racy>::GetImpl'::`2'::impl);
      v62 = *(_BYTE *)(v6 + 100) & 0x20;
      if ( IsEnabled )
      {
        if ( v62 || CTreeData::WorldTransformChangedInCurrentFrame(v58) )
        {
          memset_0(&v80, 0, 0x48u);
          v80 = InputHandle;
          CopyInputTransform((CTreeData *)((char *)v58 + 272), (struct tagINPUT_TRANSFORM *)v81);
          v63 = DynArray<COMPOSITION_INPUT_SINK_TRANSFORM,0>::AddMultipleAndSet((char *)this + 1488, &v80);
          if ( v63 < 0 )
          {
            v64 = 1238;
LABEL_110:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v64,
              (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\precomputecontext.cpp",
              (const char *)(unsigned int)v63,
              v72);
            return (unsigned int)v63;
          }
LABEL_111:
          if ( (unsigned __int8)IsNotifyInputSinkTransformChangedPresent() )
            NotifyInputSinkTransformChanged(InputHandle, v81);
        }
      }
      else if ( v62 || CTreeData::WorldTransformChangedInCurrentFrame(v58) )
      {
        memset_0(&v80, 0, 0x48u);
        v80 = InputHandle;
        CopyInputTransform((CTreeData *)((char *)v58 + 272), (struct tagINPUT_TRANSFORM *)v81);
        v63 = DynArray<COMPOSITION_INPUT_SINK_TRANSFORM,0>::AddMultipleAndSet((char *)this + 1488, &v80);
        if ( v63 < 0 )
        {
          v64 = 1258;
          goto LABEL_110;
        }
        goto LABEL_111;
      }
    }
    *(_BYTE *)(v6 + 100) &= ~0x20u;
  }
  v65 = *(CPreComputeSubTreeContext **)this;
  v66 = (CPreComputeSubTreeContext *)*((_QWORD *)this + 1);
  while ( v65 != v66 )
  {
    Parent = CPreComputeSubTreeContext::GetParent(v65, (struct CVisual *)v6);
    v70 = CBspPreComputeHelper::PreComputePostSubgraph(v69, v68, Parent);
    v71 = v70;
    if ( v70 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4FC,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\precomputecontext.cpp",
        (const char *)(unsigned int)v70,
        v72);
      return v71;
    }
    v65 = (CPreComputeSubTreeContext *)((char *)v65 + 352);
  }
  if ( (*(_DWORD *)(v6 + 96) & 0x20000000) != 0 )
    CWatermarkStack<D2D_VECTOR_2F,2,2,10>::Pop((char *)this + 1080);
  if ( CVisual::Has3DContent((CVisual *)v6) )
    --*(_DWORD *)(v10 + 336);
  *(_BYTE *)(v6 + 100) &= 0xE0u;
  *(_BYTE *)(v6 + 96) = 0;
  if ( *(_QWORD *)(*(_QWORD *)(v10 + 328) + 72LL) != v6 )
    return 0;
  CPreComputeSubTreeContext::EndWalk((CPreComputeSubTreeContext *)v10, 0);
LABEL_125:
  detail::vector_facade<CPreComputeSubTreeContext,detail::buffer_impl<CPreComputeSubTreeContext,3,1,detail::liberal_expansion_policy>>::pop_back(this);
  return 0;
}

```

## disassembly

```asm
0x1800ae8fc  mov     rax, rsp
0x1800ae8ff  mov     [rax+20h], rbx
0x1800ae903  push    rbp
0x1800ae904  push    rsi
0x1800ae905  push    rdi
0x1800ae906  push    r12
0x1800ae908  push    r13
0x1800ae90a  push    r14
0x1800ae90c  push    r15
0x1800ae90e  lea     rbp, [rsp-50h]
0x1800ae913  sub     rsp, 150h
0x1800ae91a  movaps  xmmword ptr [rax-48h], xmm6
0x1800ae91e  movaps  xmmword ptr [rax-58h], xmm7
0x1800ae922  movaps  xmmword ptr [rax-68h], xmm8
0x1800ae927  mov     rax, cs:__security_cookie
0x1800ae92e  xor     rax, rsp
0x1800ae931  mov     [rbp+80h+var_70], rax
0x1800ae935  mov     r12, [rcx+600h]
0x1800ae93c  xor     eax, eax
0x1800ae93e  mov     r13, [rcx+8]
0x1800ae942  mov     r14, rcx
0x1800ae945  mov     rsi, [rcx+5F8h]
0x1800ae94c  mov     rbx, r8
0x1800ae94f  mov     [rsp+180h+var_110], rax
0x1800ae954  mov     rcx, rdx
0x1800ae957  mov     rax, [rdx]
0x1800ae95a  mov     r15, rdx
0x1800ae95d  mov     [rsp+180h+var_108], r12
0x1800ae962  add     r13, 0FFFFFFFFFFFFFEA0h
0x1800ae969  mov     rax, [rax+0C0h]
0x1800ae970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae975  test    al, al
0x1800ae977  jz      short loc_1800AE989
0x1800ae979  mov     rdx, r15; struct CVisualTree *
0x1800ae97c  mov     rcx, rsi; this
0x1800ae97f  call    ?FindTreeData@CVisual@@QEBAPEAVCTreeData@@PEBVCVisualTree@@@Z; CVisual::FindTreeData(CVisualTree const *)
0x1800ae984  mov     [rsp+180h+var_110], rax
0x1800ae989  mov     byte ptr [rbx], 1
0x1800ae98c  cmp     byte ptr [r13+159h], 0
0x1800ae994  jnz     loc_1800AF180
0x1800ae99a  lea     rcx, [r14+498h]; this
0x1800ae9a1  mov     r8, r15; struct CVisualTree *
0x1800ae9a4  mov     rdx, rsi; struct CVisual *
0x1800ae9a7  call    ?PopLightsFromVisual@CLightStack@@QEAAJPEBVCVisual@@PEBVCVisualTree@@@Z; CLightStack::PopLightsFromVisual(CVisual const *,CVisualTree const *)
0x1800ae9ac  mov     ebx, eax
0x1800ae9ae  test    eax, eax
0x1800ae9b0  jns     short loc_1800AE9D4
0x1800ae9b2  mov     edx, 383h; void *
0x1800ae9b7  mov     rcx, [rbp+88h]; this
0x1800ae9be  lea     r8, aOnecoreuapWind_217; "onecoreuap\\windows\\dwm\\dwmcore\\engi"...
0x1800ae9c5  mov     r9d, ebx; char *
0x1800ae9c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ae9cd  mov     eax, ebx
0x1800ae9cf  jmp     loc_1800AF18A
0x1800ae9d4  mov     al, [rsi+60h]
0x1800ae9d7  mov     [rsp+180h+var_130], 0
0x1800ae9dc  test    al, 1
0x1800ae9de  jz      loc_1800AEC4E
0x1800ae9e4  mov     rcx, rsi; this
0x1800ae9e7  call    ?ResolveTransformParent@CVisual@@IEBA_NPEBVCVisualTree@@@Z; CVisual::ResolveTransformParent(CVisualTree const *)
0x1800ae9ec  test    al, al
0x1800ae9ee  jz      short loc_1800AEA2C
0x1800ae9f0  mov     rdx, r15; struct CVisualTree *
0x1800ae9f3  mov     rcx, rsi; this
0x1800ae9f6  call    ?GetTransformParent@CVisual@@QEBAPEBV1@PEBVCVisualTree@@PEA_N@Z; CVisual::GetTransformParent(CVisualTree const *,bool *)
0x1800ae9fb  mov     rbx, [r14]
0x1800ae9fe  mov     r12, rax
0x1800aea01  mov     rdi, [r14+8]
0x1800aea05  cmp     rbx, rdi
0x1800aea08  jz      short loc_1800AEA34
0x1800aea0a  mov     rdx, [rbx+148h]; struct CVisualTree *
0x1800aea11  mov     rcx, rsi; this
0x1800aea14  call    ?GetTransformParent@CVisual@@QEBAPEBV1@PEBVCVisualTree@@PEA_N@Z; CVisual::GetTransformParent(CVisualTree const *,bool *)
0x1800aea19  cmp     r12, rax
0x1800aea1c  jnz     short loc_1800AEA27
0x1800aea1e  add     rbx, 160h
0x1800aea25  jmp     short loc_1800AEA05
0x1800aea27  mov     r9b, 1
0x1800aea2a  jmp     short loc_1800AEA39
0x1800aea2c  xor     r12d, r12d
0x1800aea2f  mov     r9b, r12b
0x1800aea32  jmp     short loc_1800AEA39
0x1800aea34  mov     r9b, [rsp+180h+var_130]; bool
0x1800aea39  mov     r8, r12; struct CVisual *
0x1800aea3c  mov     rdx, r15; struct CVisualTree *
0x1800aea3f  mov     rcx, rsi; this
0x1800aea42  call    ?ConvertInnerToOuterBounds@CVisual@@IEAAJPEBVCVisualTree@@PEAV1@_N@Z; CVisual::ConvertInnerToOuterBounds(CVisualTree const *,CVisual *,bool)
0x1800aea47  mov     ebx, eax
0x1800aea49  test    eax, eax
0x1800aea4b  jns     short loc_1800AEA57
0x1800aea4d  mov     edx, 3A2h
0x1800aea52  jmp     loc_1800AE9B7
0x1800aea57  cmp     cs:?EnableDwmMoveRectHints@CCommonRegistryData@@2V?$CRegistryKey@_N_N@details@@B, 0; details::CRegistryKey<bool,bool> const CCommonRegistryData::EnableDwmMoveRectHints
0x1800aea5e  mov     [rsp+180h+var_130], 1
0x1800aea63  jz      loc_1800AEC42
0x1800aea69  mov     rax, [r15]
0x1800aea6c  mov     rcx, r15
0x1800aea6f  mov     rax, [rax+0C0h]
0x1800aea76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aea7b  test    al, al
0x1800aea7d  jz      loc_1800AEC42
0x1800aea83  xorps   xmm1, xmm1
0x1800aea86  lea     rcx, [r14+598h]
0x1800aea8d  movups  [rbp+80h+var_100+8], xmm1
0x1800aea91  xor     eax, eax
0x1800aea93  lea     r8, [rbp+80h+var_E0]
0x1800aea97  unpckhpd xmm1, xmm1
0x1800aea9b  lea     rdx, [rbp+80h+var_100]
0x1800aea9f  mov     qword ptr [rbp+80h+var_100], rax
0x1800aeaa3  movups  xmm0, [rbp+80h+var_100]
0x1800aeaa7  movsd   [rbp+80h+var_D0], xmm1
0x1800aeaac  movaps  [rbp+80h+var_E0], xmm0
0x1800aeab0  call    ?TopOrDefault@?$CWatermarkStack@UMoveBounds@MoveRectHintData@CPreComputeContext@@$0EA@$01$09@@QEBA?AUMoveBounds@MoveRectHintData@CPreComputeContext@@U234@@Z; CWatermarkStack<CPreComputeContext::MoveRectHintData::MoveBounds,64,2,10>::TopOrDefault(CPreComputeContext::MoveRectHintData::MoveBounds)
0x1800aeab5  cmp     qword ptr [rbp+80h+var_100], rsi
0x1800aeab9  jnz     loc_1800AEC42
0x1800aeabf  movss   xmm0, [rbp+80h+var_F0]
0x1800aeac4  movss   xmm5, dword ptr [rsi+90h]
0x1800aeacc  movss   xmm4, dword ptr [rsi+98h]
0x1800aead4  movss   xmm2, dword ptr [rbp+80h+var_100+8]
0x1800aead9  subss   xmm4, xmm5
0x1800aeadd  movdqa  xmm1, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x1800aeae5  subss   xmm0, xmm2
0x1800aeae9  movss   xmm8, cs:__real@38aaaaab
0x1800aeaf2  subss   xmm0, xmm4
0x1800aeaf6  andps   xmm0, xmm1
0x1800aeaf9  comiss  xmm8, xmm0
0x1800aeafd  jb      loc_1800AEC2E
0x1800aeb03  movss   xmm0, [rbp+80h+var_EC]
0x1800aeb08  movss   xmm7, dword ptr [rsi+94h]
0x1800aeb10  movss   xmm6, dword ptr [rsi+9Ch]
0x1800aeb18  movss   xmm3, dword ptr [rbp+80h+var_100+0Ch]
0x1800aeb1d  subss   xmm6, xmm7
0x1800aeb21  subss   xmm0, xmm3
0x1800aeb25  subss   xmm0, xmm6
0x1800aeb29  andps   xmm0, xmm1
0x1800aeb2c  comiss  xmm8, xmm0
0x1800aeb30  jb      loc_1800AEC2E
0x1800aeb36  movaps  xmm0, xmm2
0x1800aeb39  subss   xmm0, xmm5
0x1800aeb3d  andps   xmm0, xmm1
0x1800aeb40  comiss  xmm8, xmm0
0x1800aeb44  jb      short loc_1800AEB5A
0x1800aeb46  movaps  xmm0, xmm3
0x1800aeb49  subss   xmm0, xmm7
0x1800aeb4d  andps   xmm0, xmm1
0x1800aeb50  comiss  xmm8, xmm0
0x1800aeb54  jnb     loc_1800AEC2E
0x1800aeb5a  mov     al, [r14+5C8h]
0x1800aeb61  test    al, al
0x1800aeb63  jz      short loc_1800AEB83
0x1800aeb65  movss   xmm0, dword ptr [r14+5C4h]
0x1800aeb6e  movaps  xmm1, xmm6
0x1800aeb71  mulss   xmm0, dword ptr [r14+5C0h]
0x1800aeb7a  mulss   xmm1, xmm4
0x1800aeb7e  comiss  xmm1, xmm0
0x1800aeb81  jbe     short loc_1800AEBC8
0x1800aeb83  movss   dword ptr [r14+5B0h], xmm2
0x1800aeb8c  mov     cl, 1
0x1800aeb8e  movss   dword ptr [r14+5B4h], xmm3
0x1800aeb97  movss   dword ptr [r14+5B8h], xmm5
0x1800aeba0  movss   dword ptr [r14+5BCh], xmm7
0x1800aeba9  movss   dword ptr [r14+5C0h], xmm4
0x1800aebb2  movss   dword ptr [r14+5C4h], xmm6
0x1800aebbb  test    al, al
0x1800aebbd  jnz     short loc_1800AEBCA
0x1800aebbf  mov     [r14+5C8h], cl
0x1800aebc6  jmp     short loc_1800AEBCA
0x1800aebc8  xor     cl, cl
0x1800aebca  mov     al, byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits
0x1800aebd0  and     al, 20h
0x1800aebd2  mov     byte ptr [rsp+180h+var_128], al
0x1800aebd6  jz      short loc_1800AEC2E
0x1800aebd8  lea     rax, [rsp+180h+var_128]
0x1800aebdd  movzx   r9d, cl
0x1800aebe1  mov     [rsp+180h+var_138], rax
0x1800aebe6  subss   xmm5, xmm2
0x1800aebea  subss   xmm7, xmm3
0x1800aebee  movss   [rsp+180h+var_120], xmm2
0x1800aebf4  lea     rax, [rsp+180h+var_118]
0x1800aebf9  movss   [rsp+180h+var_11C], xmm3
0x1800aebff  mov     [rsp+180h+var_148], rax
0x1800aec04  mov     r8, rsi
0x1800aec07  lea     rax, [rsp+180h+var_120]
0x1800aec0c  movss   [rsp+180h+var_128], xmm4
0x1800aec12  mov     [rsp+180h+var_158], rax
0x1800aec17  movss   [rsp+180h+var_118], xmm5
0x1800aec1d  movss   [rsp+180h+var_114], xmm7
0x1800aec23  movss   [rsp+180h+var_124], xmm6
0x1800aec29  call    McTemplateU0xtnnn_EventWriteTransfer
0x1800aec2e  mov     eax, [r14+5A0h]
0x1800aec35  test    eax, eax
0x1800aec37  jz      short loc_1800AEC42
0x1800aec39  dec     eax
0x1800aec3b  mov     [r14+5A0h], eax
0x1800aec42  and     byte ptr [rsi+60h], 0FEh
0x1800aec46  mov     al, [rsi+60h]
0x1800aec49  mov     r12, [rsp+180h+var_108]
0x1800aec4e  test    al, 10h
0x1800aec50  jz      loc_1800AED1C
0x1800aec56  mov     rax, [rsi]
0x1800aec59  mov     rcx, rsi
0x1800aec5c  mov     ebx, [rsi+60h]
0x1800aec5f  shl     ebx, 0Fh
0x1800aec62  sar     ebx, 17h
0x1800aec65  mov     rax, [rax+110h]
0x1800aec6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aec71  test    al, al
0x1800aec73  jz      short loc_1800AEC97
0x1800aec75  test    bl, 1
0x1800aec78  jnz     short loc_1800AEC93
0x1800aec7a  mov     rcx, rsi; this
0x1800aec7d  call    ?HasSingleD2DBitmapOrPrimitiveGroup@CVisual@@QEBA_NXZ; CVisual::HasSingleD2DBitmapOrPrimitiveGroup(void)
0x1800aec82  test    al, al
0x1800aec84  jnz     short loc_1800AEC8E
0x1800aec86  or      ebx, 101h
0x1800aec8c  jmp     short loc_1800AEC97
0x1800aec8e  or      ebx, 1
0x1800aec91  jmp     short loc_1800AEC97
0x1800aec93  bts     ebx, 8
0x1800aec97  mov     rcx, rsi; this
0x1800aec9a  call    ?Has3DContent@CVisual@@IEBA_NXZ; CVisual::Has3DContent(void)
0x1800aec9f  mov     edi, ebx
0x1800aeca1  mov     rcx, rsi
0x1800aeca4  or      edi, 2
0x1800aeca7  test    al, al
0x1800aeca9  mov     rax, [rsi]
0x1800aecac  cmovz   edi, ebx
0x1800aecaf  mov     rax, [rax+158h]
0x1800aecb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aecbb  mov     ebx, edi
0x1800aecbd  mov     rcx, rsi; this
0x1800aecc0  or      ebx, 4
0x1800aecc3  test    al, al
0x1800aecc5  cmovz   ebx, edi
0x1800aecc8  call    ?HasPixelSnappedContent@CVisual@@IEBA_NXZ; CVisual::HasPixelSnappedContent(void)
0x1800aeccd  mov     r10d, ebx
0x1800aecd0  mov     rcx, rsi; this
0x1800aecd3  or      r10d, 8
0x1800aecd7  test    al, al
0x1800aecd9  cmovz   r10d, ebx
0x1800aecdd  call    ?HasInputSink@CVisual@@QEBA_NXZ; CVisual::HasInputSink(void)
0x1800aece2  mov     ebx, r10d
0x1800aece5  mov     rcx, rsi
0x1800aece8  or      ebx, 10h
0x1800aeceb  test    al, al
0x1800aeced  mov     rax, [rsi]
0x1800aecf0  cmovz   ebx, r10d
0x1800aecf4  mov     rax, [rax+118h]
0x1800aecfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aed00  mov     ecx, ebx
0x1800aed02  or      ecx, 40h
0x1800aed05  test    al, al
0x1800aed07  cmovz   ecx, ebx
0x1800aed0a  shl     ecx, 8
0x1800aed0d  mov     eax, ecx
0x1800aed0f  xor     eax, [rsi+60h]
0x1800aed12  and     eax, 0FFFE00FFh
0x1800aed17  xor     eax, ecx
0x1800aed19  mov     [rsi+60h], eax
0x1800aed1c  test    r12, r12
0x1800aed1f  jz      short loc_1800AEDA0
0x1800aed21  mov     rcx, rsi; this
0x1800aed24  call    ?HasInputSink@CVisual@@QEBA_NXZ; CVisual::HasInputSink(void)
0x1800aed29  mov     r8d, [r12+60h]
0x1800aed2e  mov     ecx, 20h ; ' '
0x1800aed33  movzx   r10d, al
0x1800aed37  mov     eax, r8d
0x1800aed3a  shl     r10d, 5
0x1800aed3e  test    byte ptr [rsi+66h], 4
0x1800aed42  cmovz   ecx, r10d
0x1800aed46  mov     edx, ecx
0x1800aed48  bts     edx, 7
0x1800aed4c  test    dword ptr [rsi+60h], 60000h
0x1800aed53  cmovz   edx, ecx
0x1800aed56  and     eax, [rsi+60h]
0x1800aed59  bt      eax, 8
0x1800aed5d  mov     ecx, edx
0x1800aed5f  setb    al
0x1800aed62  bts     ecx, 8
0x1800aed66  test    al, al
0x1800aed68  cmovz   ecx, edx
0x1800aed6b  shl     ecx, 8
0x1800aed6e  or      ecx, r8d
0x1800aed71  or      ecx, [rsi+60h]
0x1800aed74  xor     r8d, ecx
0x1800aed77  and     r8d, 0FFFE00FFh
0x1800aed7e  xor     r8d, ecx
0x1800aed81  mov     [r12+60h], r8d
0x1800aed86  test    r8b, 1
0x1800aed8a  jz      short loc_1800AEDA0
0x1800aed8c  lea     rdx, [rsi+90h]
0x1800aed93  lea     rcx, [r12+0A8h]
0x1800aed9b  call    ?UnionUnsafe@?$TMil3DRect@MV?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@UD3D_RECT_F@@UMilPointAndSizeF@@UNotNeeded@RectUniqueness@@@@QEAA_NAEBV1@@Z; TMil3DRect<float,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>,D3D_RECT_F,MilPointAndSizeF,RectUniqueness::NotNeeded>::UnionUnsafe(TMil3DRect<float,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>,D3D_RECT_F,MilPointAndSizeF,RectUniqueness::NotNeeded> const &)
0x1800aeda0  test    byte ptr [rsi+67h], 2
0x1800aeda4  jz      short loc_1800AEDC4
0x1800aeda6  mov     rdx, rsi; struct CVisual *
0x1800aeda9  mov     rcx, r14; this
0x1800aedac  call    ?ProcessPostSubgraphWindowBackdropInput@CPreComputeContext@@AEAAJPEAVCVisual@@@Z; CPreComputeContext::ProcessPostSubgraphWindowBackdropInput(CVisual *)
0x1800aedb1  xor     r12d, r12d
0x1800aedb4  mov     ebx, eax
  ... truncated ...
```
