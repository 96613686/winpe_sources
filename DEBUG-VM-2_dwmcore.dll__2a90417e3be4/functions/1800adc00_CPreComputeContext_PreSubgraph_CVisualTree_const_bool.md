# CPreComputeContext::PreSubgraph(CVisualTree const *,bool *)

- ea: `0x1800adc00`
- end: `0x1800ae8f6`
- name: `?PreSubgraph@CPreComputeContext@@QEAAJPEBVCVisualTree@@PEA_N@Z`
- size: `3318`
- prototype: `__int64 __fastcall(CPreComputeContext *__hidden this, const struct CVisualTree *, bool *)`
- caller_count: `1`
- callee_count: `56`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800acdc0`

## callees

- `0x1800192ac`
- `0x180019f14`
- `0x18001ad30`
- `0x18001be0c`
- `0x18003abec`
- `0x180042854`
- `0x180042de0`
- `0x180064ef0`
- `0x180070c48`
- `0x18008c400`
- `0x180090b80`
- `0x18009157c`
- `0x180091c30`
- `0x180092080`
- `0x1800983d0`
- `0x18009de70`
- `0x18009df40`
- `0x18009e0f8`
- `0x18009e864`
- `0x18009f0f8`
- `0x1800a0388`
- `0x1800a11e4`
- `0x1800a7f30`
- `0x1800a8fd0`
- `0x1800ab450`
- `0x1800adc00`
- `0x1800d2900`
- `0x1800d31c4`
- `0x1800ee630`
- `0x1800f0f10`
- `0x1801223ac`
- `0x18014bf70`
- `0x18014c170`
- `0x180152410`
- `0x1801582d0`
- `0x18015dd30`
- `0x180166640`
- `0x180167264`
- `0x18017e414`
- `0x180186964`
- `0x18019e4fc`
- `0x1801a6774`
- `0x1801a7f68`
- `0x1801afa34`
- `0x1801bd410`
- `0x1801c6ca4`
- `0x1801c7d18`
- `0x1801c9ed4`
- `0x1801d35d8`
- `0x1801e81c8`

## string_xrefs

- `0x1800ade3a`: `onecoreuap\windows\dwm\dwmcore\engine\precomputecontext.cpp`
- `0x1800ae086`: `onecoreuap\windows\dwm\dwmcore\engine\precomputecontext.cpp`
- `0x1800ae177`: `onecoreuap\windows\dwm\dwmcore\engine\precomputecontext.cpp`
- `0x1800ae18f`: `onecoreuap\windows\dwm\dwmcore\engine\precomputecontext.cpp`
- `0x1800ae2a6`: `onecoreuap\windows\dwm\dwmcore\engine\precomputecontext.cpp`
- `0x1800ae41b`: `onecoreuap\windows\dwm\dwmcore\engine\precomputecontext.cpp`
- `0x1800ae4db`: `onecoreuap\windows\dwm\dwmcore\engine\precomputecontext.cpp`
- `0x1800ae641`: `onecoreuap\windows\dwm\dwmcore\engine\precomputecontext.cpp`
- `0x1800ae6eb`: `onecoreuap\windows\dwm\dwmcore\engine\precomputecontext.cpp`
- `0x1800ae72c`: `onecoreuap\windows\dwm\dwmcore\engine\precomputecontext.cpp`
- `0x1800ae883`: `PreCompute-BailWithBackdropsStillInSubtree`

## pseudocode

```c
__int64 __fastcall CPreComputeContext::PreSubgraph(CPreComputeContext *this, const struct CVisualTree *a2, bool *a3)
{
  __int64 v3; // r12
  __int64 v5; // rax
  __int64 *v7; // r14
  const struct CVisualTree *v8; // r15
  unsigned __int8 (__fastcall *v9)(const struct CVisualTree *); // rax
  struct _LIST_ENTRY **p_Blink; // rbx
  struct _LIST_ENTRY *TreeDataListHead; // rax
  struct _LIST_ENTRY *Flink; // rcx
  char v13; // al
  _DWORD *v14; // r8
  __int64 v15; // rcx
  bool v16; // zf
  __int64 v17; // rdx
  __int64 *v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rdi
  __int64 v23; // rdi
  const struct CVisualTree **v24; // rcx
  const struct CVisualTree **v25; // rsi
  const struct CVisualTree **i; // rbx
  __int64 v27; // rdx
  char v28; // al
  int v29; // eax
  unsigned int v30; // ebx
  _DWORD *v32; // rdx
  int v33; // eax
  struct CLightStack *v34; // rcx
  _QWORD *v35; // r12
  unsigned int v36; // r15d
  __int64 j; // rdi
  __int64 v38; // rax
  _BYTE *v39; // rbx
  __int64 v40; // rax
  int v41; // eax
  unsigned int v42; // ebx
  char v43; // al
  struct D2D_VECTOR_3F *UnoptimizedBounds; // rdx
  __int64 v45; // rcx
  CPreComputeContext *v46; // rcx
  __int64 v47; // rbx
  __int64 v48; // rdi
  int v49; // eax
  unsigned int v50; // r15d
  CTreeData *v51; // r12
  char v52; // bl
  int v53; // eax
  bool *v54; // rdi
  struct CPreComputeSubTreeContext *v55; // rbx
  struct CPreComputeSubTreeContext *v56; // rdi
  struct CVisual *v57; // r8
  int v58; // eax
  unsigned int v59; // r15d
  __int64 v60; // rax
  __int64 v61; // r8
  char v62; // al
  float v63; // xmm0_4
  int v64; // eax
  unsigned int v65; // ebx
  float v66; // xmm6_4
  float v67; // xmm7_4
  float v68; // xmm1_4
  float v69; // xmm0_4
  int v70; // eax
  unsigned int v71; // ebx
  __int64 TopByReference; // rax
  __int64 v73; // rdx
  float *v74; // rax
  const struct D2D_VECTOR_2F *v75; // r8
  struct CWindowBackgroundTreatment *WindowBackgroundTreatmentInternal; // rbx
  __int64 v77; // r10
  const struct CMILMatrix *v78; // rax
  __int64 v79; // r10
  __int64 v80; // rcx
  _BYTE *v81; // rdx
  CBspPreComputeHelper *v82; // rbx
  CBspPreComputeHelper *v83; // rdi
  const struct CVisualTree *v84; // rdx
  const struct CVisual *v85; // r9
  int v86; // eax
  unsigned int v87; // esi
  __int128 v88; // xmm0
  int v89; // eax
  unsigned int v90; // ebx
  __int64 v91; // rax
  int v92; // eax
  unsigned int v93; // ebx
  FLOAT v94; // xmm0_4
  __int64 v95; // rcx
  __int64 v96; // rbx
  __int64 v97; // rdi
  struct CTreeData *TreeData; // rax
  __int64 v99; // rbx
  __int64 v100; // rax
  int v101; // [rsp+20h] [rbp-E0h]
  int v102; // [rsp+20h] [rbp-E0h]
  int v103; // [rsp+20h] [rbp-E0h]
  const struct CVisualTree *v105; // [rsp+38h] [rbp-C8h] BYREF
  float v106; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v107[2]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v108[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v109[24]; // [rsp+60h] [rbp-A0h] BYREF
  struct D2D_VECTOR_3F v110[2]; // [rsp+78h] [rbp-88h] BYREF
  int v111[2]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE *v112; // [rsp+98h] [rbp-68h]
  char *v113; // [rsp+A0h] [rbp-60h]
  _BYTE v114[32]; // [rsp+A8h] [rbp-58h] BYREF
  char v115; // [rsp+C8h] [rbp-38h] BYREF
  int v116; // [rsp+D0h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v3 = *((_QWORD *)this + 192);
  v5 = *(_QWORD *)a2;
  v7 = (__int64 *)*((_QWORD *)this + 191);
  v8 = a2;
  v105 = a2;
  v9 = *(unsigned __int8 (__fastcall **)(const struct CVisualTree *))(v5 + 192);
  v116 = 0;
  *(_QWORD *)&v110[0].x = v3;
  if ( v9(a2) )
  {
    p_Blink = (struct _LIST_ENTRY **)(v7 + 40);
  }
  else
  {
    p_Blink = 0;
    TreeDataListHead = CVisual::GetTreeDataListHead((CVisual *)v7);
    if ( TreeDataListHead )
    {
      Flink = TreeDataListHead->Flink;
      if ( TreeDataListHead->Flink != TreeDataListHead )
      {
        while ( (const struct CVisualTree *)Flink[2].Flink != v8 )
        {
          Flink = Flink->Flink;
          if ( Flink == TreeDataListHead )
            goto LABEL_9;
        }
        p_Blink = &Flink[-22].Blink;
      }
    }
  }
LABEL_9:
  *a3 = 0;
  v13 = (*(__int64 (__fastcall **)(const struct CVisualTree *))(*(_QWORD *)v8 + 192LL))(v8);
  v14 = (_DWORD *)v7[28];
  v15 = 0;
  if ( !v13 )
    p_Blink = 0;
  v16 = (*v14 & 0x8000000) == 0;
  *(_QWORD *)v109 = p_Blink;
  if ( v16 )
    goto LABEL_25;
  v17 = (unsigned int)v14[1];
  if ( (_DWORD)v17 )
  {
    while ( *((_BYTE *)v14 + v15 + 8) != 5 )
    {
      v15 = (unsigned int)(v15 + 1);
      if ( (unsigned int)v15 >= (unsigned int)v17 )
        goto LABEL_15;
    }
  }
  else
  {
LABEL_15:
    if ( (unsigned int)v15 >= (unsigned int)v17 )
    {
      v18 = 0;
      goto LABEL_18;
    }
  }
  v18 = (__int64 *)((char *)&v14[2 * v15] + ((v17 + 15) & 0xFFFFFFFFFFFFFFF8uLL));
LABEL_18:
  v19 = *v18;
  if ( v19 )
  {
    v20 = *(_QWORD *)(v19 + 72);
    if ( v20 )
    {
      if ( *(_BYTE *)(v20 + 96) )
      {
        detail::vector_facade<CPreComputeSubTreeContext,detail::buffer_impl<CPreComputeSubTreeContext,3,1,detail::liberal_expansion_policy>>::emplace_back<CVisualTree *>(this);
        if ( !CPreComputeSubTreeContext::BeginWalk((CPreComputeSubTreeContext *)(*((_QWORD *)this + 1) - 352LL), v8) )
        {
          v21 = *(_QWORD *)this;
          v22 = *((_QWORD *)this + 1);
          while ( v21 != v22 )
          {
            CTreeDirty::SetFullDirty(*(CTreeDirty **)(v21 + 320));
            v21 += 352;
          }
          return 0;
        }
      }
    }
  }
LABEL_25:
  v23 = 0;
  v24 = *(const struct CVisualTree ***)this;
  v25 = (const struct CVisualTree **)*((_QWORD *)this + 1);
  v108[0] = *(_QWORD *)this;
  if ( g_pComposition )
    v23 = *((_QWORD *)g_pComposition + 110);
  for ( i = v24; i != v25; i += 44 )
  {
    CVisual::EnsureTreeData((CVisual *)v7, i[41]);
    if ( CPreComputeSubTreeContext::IsDirtyCollectionEnabled((CPreComputeSubTreeContext *)i) )
      *(_QWORD *)(v27 + 208) = v23;
  }
  if ( (*(unsigned __int8 (__fastcall **)(__int64 *, __int64))(*v7 + 64))(v7, 72) )
  {
    v28 = *((_BYTE *)v7 + 96);
    if ( v28 < 0 )
      *((_BYTE *)v7 + 96) = v28 | 4;
  }
  if ( (v7[12] & 0x20000000) != 0 )
  {
    v106 = *((float *)v7 + 52);
    v29 = CWatermarkStack<enum MilBitmapInterpolationMode::Enum,64,2,10>::Push((char *)this + 1080, &v106);
    v30 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18B,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\precomputecontext.cpp",
        (const char *)(unsigned int)v29,
        v101);
      return v30;
    }
  }
  v32 = 0;
  v33 = *((_DWORD *)this + 272);
  if ( v33 )
    v32 = (_DWORD *)(*((_QWORD *)this + 135) + 4LL * (unsigned int)(v33 - 1));
  if ( *((_DWORD *)v7 + 26) != *v32 )
  {
    *((_DWORD *)v7 + 26) = *(_DWORD *)((__int64 (*)(void))CWatermarkStack<enum MilBackfaceVisibility::Enum,64,2,10>::GetTopByReference)();
    CVisual::OnOuterTransformChanged((CVisual *)v7);
  }
  if ( *((_DWORD *)v7 + 26) == 1 )
    *a3 = 1;
  if ( *((int *)v7 + 65) > 0 || *((int *)v7 + 64) > 0 )
    *a3 = 1;
  CVisual::UpdateLayoutSize((CVisual *)v7);
  v34 = (CPreComputeContext *)((char *)this + 1176);
  if ( (unsigned int)((v7[34] - v7[33]) >> 3) || (unsigned int)((v7[37] - v7[36]) >> 3) )
  {
    v107[0] = 0;
    v35 = v107;
    v107[1] = 1;
    while ( 2 )
    {
      v36 = *(_DWORD *)v35;
      for ( j = 0; ; j = (unsigned int)(j + 1) )
      {
        v38 = v36 ? v7[37] - v7[36] : v7[34] - v7[33];
        if ( (unsigned int)j >= (unsigned int)(v38 >> 3) )
          break;
        if ( (unsigned int)j < (unsigned int)CVisual::GetLightsCount(v7, v36) )
        {
          if ( v36 )
            v40 = v7[36];
          else
            v40 = v7[33];
          v39 = *(_BYTE **)(v40 + 8 * j);
        }
        else
        {
          v39 = 0;
        }
        if ( v39[80] )
        {
          if ( (*(unsigned __int8 (__fastcall **)(_BYTE *, const struct CVisualTree *, __int64 *))(*(_QWORD *)v39 + 248LL))(
                 v39,
                 v105,
                 v7) )
          {
            v41 = CLightStack::Push((char *)this + 1176, v39, v36);
            v42 = v41;
            if ( v41 < 0 )
            {
              MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v41, 0x4Bu, 0);
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1AF,
                (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\precomputecontext.cpp",
                (const char *)v42,
                v102);
              return v42;
            }
          }
        }
      }
      v35 = (_QWORD *)((char *)v35 + 4);
      if ( v35 != v108 )
        continue;
      break;
    }
    v8 = v105;
    v34 = (CPreComputeContext *)((char *)this + 1176);
    v3 = *(_QWORD *)&v110[0].x;
  }
  if ( (*(_DWORD *)(v7[27] + 4) & 0x2000000) != 0 )
  {
    v43 = *((_BYTE *)v7 + 96);
    if ( (v43 & 0xC0) != 0 )
      *((_BYTE *)v7 + 96) = v43 | 4;
  }
  if ( v3 && (*(_BYTE *)(v3 + 96) & 2) != 0 )
    *((_BYTE *)v7 + 96) |= 2u;
  if ( (v7[12] & 6) == 2 && CVisual::IsAffectedByNonAmbientLights((CVisual *)v7, v8, v34) )
    *((_BYTE *)v7 + 96) = *((_BYTE *)v7 + 96) ^ 2 | 4;
  if ( *((char *)v7 + 102) < 0 )
  {
    UnoptimizedBounds = v110;
    v45 = *(_QWORD *)(v108[0] + 320LL);
    if ( *(_BYTE *)(v45 + 2324) )
      *(_OWORD *)&v110[0].x = TMilRect<float,D2D_RECT_F,D3D_RECT_F,RectUniqueness::NotNeeded>::sc_rcInfinite;
    else
      UnoptimizedBounds = (struct D2D_VECTOR_3F *)CTreeDirty::GetUnoptimizedBounds(v45, v110);
    CWatermarkStack<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>,64,2,10>::Push(
      (char *)this + 1408,
      UnoptimizedBounds);
    if ( (*(unsigned __int8 (__fastcall **)(const struct CVisualTree *))(*(_QWORD *)v8 + 192LL))(v8) )
    {
      if ( (unsigned __int8)CVisualTree::_IsInTree(v8, v7, 2) )
        CPreComputeContext::AddVisualToBVIPreRenderList(this, (struct CVisual *)v7);
    }
  }
  if ( (v7[12] & 0xD3) != 0 )
    *a3 = 1;
  if ( CVisual::Has3DContent((CVisual *)v7) )
    ++*((_DWORD *)v25 - 4);
  if ( (v7[12] & 4) != 0 )
  {
    if ( (v7[12] & 1) != 0 && !*((_DWORD *)v25 - 3) )
    {
      v47 = *(_QWORD *)this;
      v48 = *((_QWORD *)this + 1);
      while ( v47 != v48 )
      {
        if ( !*(_DWORD *)(v47 + 340) && !*(_BYTE *)(*(_QWORD *)(v47 + 320) + 2324LL) )
        {
          v49 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v7 + 224))(v7, v47);
          v50 = v49;
          if ( v49 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x539,
              (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\precomputecontext.cpp",
              (const char *)(unsigned int)v49,
              v101);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x20F,
              (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\precomputecontext.cpp",
              (const char *)v50,
              v103);
            return v50;
          }
        }
        v47 += 352;
      }
      v8 = v105;
    }
    ++*((_DWORD *)v25 - 3);
  }
  v51 = *(CTreeData **)v109;
  v52 = 0;
  if ( !*(_QWORD *)v109 )
  {
    v54 = a3;
LABEL_112:
    if ( !*v54 )
    {
LABEL_114:
      if ( *((char *)v7 + 102) >= 0 && (*((_BYTE *)v7 + 103) & 2) == 0 && ((v7[12] & 8) == 0 || *((_DWORD *)v25 - 3)) )
        goto LABEL_129;
      goto LABEL_118;
    }
    goto LABEL_113;
  }
  v53 = *((_DWORD *)v7 + 24);
  if ( (v53 & 0x8000) != 0 )
  {
    *a3 = 1;
    goto LABEL_113;
  }
  v54 = a3;
  if ( !*a3 )
  {
    if ( (*((_BYTE *)v7 + 100) & 0x20) != 0 && (v53 & 0x1000) != 0 )
    {
      *a3 = 1;
      goto LABEL_113;
    }
    if ( (v53 & 0x2000) != 0 )
    {
      CVisual::EnsureWorldTransform((CVisual *)v7, v8, *(struct CTreeData **)v109);
      if ( CTreeData::WorldTransformChangedInCurrentFrame(v51) )
        *a3 = 1;
      v52 = 1;
    }
    goto LABEL_112;
  }
LABEL_113:
  *((_DWORD *)v7 + 24) &= 0xFFFE00FF;
  *((_BYTE *)v7 + 96) = *((_DWORD *)v7 + 24) | 0x10;
  if ( !*a3 )
    goto LABEL_114;
LABEL_118:
  v55 = *(struct CPreComputeSubTreeContext **)this;
  v56 = (struct CPreComputeSubTreeContext *)*((_QWORD *)this + 1);
  while ( v55 != v56 )
  {
    if ( v7 == *((__int64 **)*(v25 - 3) + 9) )
      v57 = 0;
    else
      v57 = (struct CVisual *)v7[11];
    v58 = CPreComputeContext::ProcessVisualsWorldTransformAndClip(
            v46,
            (struct CVisual *)v7,
            v57,
            v55,
            (struct CMILMatrix *)v111);
    v59 = v58;
    if ( v58 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x261,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\precomputecontext.cpp",
        (const char *)(unsigned int)v58,
        v101);
      return v59;
    }
    v55 = (struct CPreComputeSubTreeContext *)((char *)v55 + 352);
  }
  v52 = 1;
  if ( (v7[12] & 8) != 0 )
    CPreComputeContext::CollectAdditionalDirtyRectsForSubTrees(this, (struct CVisual *)v7);
  v8 = v105;
LABEL_129:
  if ( !v51 )
    goto LABEL_144;
  if ( !v52 && (CVisual::HasInputSink((CVisual *)v7) || (*((_BYTE *)v7 + 102) & 4) != 0) )
    CVisual::EnsureWorldTransform((CVisual *)v7, v8, v51);
  if ( (v7[12] & 0x60000) != 0 )
  {
    v60 = (*(__int64 (__fastcall **)(const struct CVisualTree *))(*(_QWORD *)v8 + 224LL))(v8);
    if ( v60 )
    {
      LOBYTE(v61) = *((_DWORD *)v25 - 3) != 0;
      (*(void (__fastcall **)(__int64, __int64 *, __int64, _QWORD))(*(_QWORD *)v60 + 40LL))(
        v60,
        v7,
        v61,
        (*((_DWORD *)v7 + 24) >> 17) & 3);
    }
  }
  if ( CVisual::HasInputSink((CVisual *)v7) )
  {
    *(_QWORD *)v109 = CVisual::GetInputHandle((CVisual *)v7);
    CWatermarkStack<void *,2,2,10>::Push((char *)this + 1152, v109);
    *((_BYTE *)v7 + 100) |= 8u;
    v62 = (*((_BYTE *)v7 + 100) & 0x20) != 0;
    if ( v62 == *((_BYTE *)this + 1592) )
      goto LABEL_144;
    *((_BYTE *)this + 1592) = v62;
    goto LABEL_143;
  }
  if ( (*((_BYTE *)v7 + 100) & 0x20) != 0 && !*((_BYTE *)this + 1592) )
  {
    *((_BYTE *)this + 1592) = 1;
LABEL_143:
    *((_BYTE *)v7 + 100) |= 0x10u;
  }
LABEL_144:
  if ( (*((_BYTE *)v7 + 102) & 0x10) != 0 )
  {
    if ( (*(_DWORD *)(v7[27] + 4) & 0x40000) != 0 )
    {
      v63 = CVisual::CalculateWorldRenderingScale((CVisual *)v7);
      if ( v63 > 0.00000011920929 )
      {
        v106 = CVisual::GetWorldRenderingScaleOverride((CVisual *)v7) / v63;
        v64 = CWatermarkStack<float,2,2,10>::Push((char *)this + 1104, &v106);
        v65 = v64;
        if ( v64 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2BC,
            (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\precomputecontext.cpp",
            (const char *)(unsigned int)v64,
            v101);
          return v65;
        }
        *((_BYTE *)v7 + 100) |= 2u;
      }
    }
    if ( (*(_DWORD *)(v7[27] + 4) & 0x20000) != 0 )
    {
      CVisual::GetWorldUpVectorOverride((CVisual *)v7, v110);
      CMILMatrix::Transform3DVector((CMILMatrix *)v111, (struct D2D_VECTOR_3F *)v109, v110);
      v66 = *(float *)&v109[4];
      v67 = *(float *)v109;
      v68 = (float)(v66 * v66) + (float)(v67 * v67);
      v69 = v68 < 0.0 ? sqrtf_0(v68) : fsqrt(v68);
      if ( v69 > 0.00000011920929 )
      {
        *(float *)&v105 = v67 / v69;
        *((float *)&v105 + 1) = v66 / v69;
        v70 = CWatermarkStack<D2D_VECTOR_2F,2,2,10>::Push((char *)this + 1128, &v105);
        v71 = v70;
        if ( v70 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2D4,
            (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\precomputecontext.cpp",
            (const char *)(unsigned int)v70,
            v101);
          return v71;
        }
        *((_BYTE *)v7 + 100) |= 4u;
      }
    }
  }
  if ( (*((_BYTE *)v7 + 102) & 4) != 0 && v51 && CTreeData::WorldTransformChangedInCurrentFrame(v51) )
  {
    TopByReference = CWatermarkStack<CBspNode *,64,2,10>::GetTopByReference((char *)this + 1128);
    v74 = (float *)CWatermarkStack<enum MilBackfaceVisibility::Enum,64,2,10>::GetTopByReference(
                     (char *)this + 1104,
                     v73,
                     TopByReference);
    CVisual::IssueContextUpdateNotification((CVisual *)v7, *v74, v75);
  }
  if ( (*(_DWORD *)v7[28] & 0x800000) != 0 )
  {
    WindowBackgroundTreatmentInternal = CVisual::GetWindowBackgroundTreatmentInternal((CVisual *)v7);
    CWindowBackgroundTreatment::InvalidateExistingBounds(WindowBackgroundTreatmentInternal);
    v77 = v108[0];
    *((_BYTE *)WindowBackgroundTreatmentInternal + 301) = 1;
    v78 = CMatrixStack::GetTopByReference((CMatrixStack *)(v77 + 272));
    CWindowBackgroundTreatment::SetWorldTransform(WindowBackgroundTreatmentInternal, v78, 1);
    if ( *((_QWORD *)WindowBackgroundTreatmentInternal + 38) )
    {
      v80 = *(_QWORD *)(v79 + 320);
      v81 = v109;
      if ( *(_BYTE *)(v80 + 2324) )
        *(_OWORD *)v109 = TMilRect<float,D2D_RECT_F,D3D_RECT_F,RectUniqueness::NotNeeded>::sc_rcInfinite;
      else
        v81 = (_BYTE *)CTreeDirty::GetUnoptimizedBounds(v80, v109);
      CWatermarkStack<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>,64,2,10>::Push(
        (char *)this + 1408,
        v81);
      if ( (*(unsigned __int8 (__fastcall **)(const struct CVisualTree *))(*(_QWORD *)v8 + 192LL))(v8) )
      {
        if ( (unsigned __int8)CVisualTree::_IsInTree(v8, v7, 2) )
          CPreComputeContext::AddVisualToBVIPreRenderList(this, (struct CVisual *)v7);
      }
    }
  }
  v82 = *(CBspPreComputeHelper **)this;
  v83 = (CBspPreComputeHelper *)*((_QWORD *)this + 1);
  while ( v82 != v83 )
  {
    v84 = (const struct CVisualTree *)*((_QWORD *)v82 + 41);
    if ( v7 == *((__int64 **)v84 + 9) )
      v85 = 0;
    else
      v85 = (const struct CVisual *)v7[11];
    v86 = CBspPreComputeHelper::PreComputePreSubgraph(v82, v84, (struct CVisual *)v7, v85);
    v87 = v86;
    if ( v86 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x31A,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\precomputecontext.cpp",
        (const char *)(unsigned int)v86,
        v101);
      return v87;
    }
    v82 = (CBspPreComputeHelper *)((char *)v82 + 352);
  }
  if ( (v7[12] & 1) != 0 )
  {
    if ( CCommonRegistryData::EnableDwmMoveRectHints
      && (*(unsigned __int8 (__fastcall **)(const struct CVisualTree *))(*(_QWORD *)v8 + 192LL))(v8)
      && (unsigned __int8)CMILMatrix::IsTranslate<1>(v111) )
    {
      v88 = *((_OWORD *)v7 + 9);
      *(_QWORD *)v109 = v7;
      *(_OWORD *)&v109[8] = v88;
      CWatermarkStack<CPreComputeContext::MoveRectHintData::MoveBounds,64,2,10>::Push((char *)this + 1432, v109);
    }
    if ( (*(unsigned __int8 (__fastcall **)(__int64 *, __int64))(*v7 + 64))(v7, 130) )
    {
      v89 = CSceneVisual::Get3DContentBounds(v7, v7 + 21);
      v90 = v89;
      if ( v89 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32D,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\precomputecontext.cpp",
          (const char *)(unsigned int)v89,
          v101);
        return v90;
      }
    }
    else
    {
      v91 = *v7;
      *(_OWORD *)v109 = 0;
      v92 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(v91 + 240))(v7, v109);
      v93 = v92;
      if ( v92 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x337,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\precomputecontext.cpp",
          (const char *)(unsigned int)v92,
          v101);
        return v93;
      }
      if ( CVisual::HasProjectedShadowReceivers((CVisual *)v7) )
      {
        v94 = *((float *)v7 + 35);
        v110[0].z = *((FLOAT *)v7 + 34);
        v110[1].x = v94;
        *(_QWORD *)&v110[0].x = 0;
        TMilRect<float,D2D_RECT_F,D3D_RECT_F,RectUniqueness::NotNeeded>::UnionUnsafe(v109, v110);
      }
      *(_OWORD *)(v7 + 21) = *(_OWORD *)v109;
      v7[23] = 0;
    }
  }
  v95 = v7[31];
  if ( v95 && (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v95 + 64LL))(v95, 143) )
  {
    v96 = *(_QWORD *)this;
    v97 = *((_QWORD *)this + 1);
    while ( v96 != v97 )
    {
      *(_OWORD *)v109 = 0;
      CBaseClipStack::Top(v96 + 296, v109);
      TreeData = CVisual::FindTreeData((CVisual *)v7, *(const struct CVisualTree **)(v96 + 328));
      CTreeData::SetSuperWetInkClip(TreeData, v109);
      v96 += 352;
    }
  }
  if ( dword_1803B9890 && !*a3 && (*((int *)v7 + 64) > 0 || *((int *)v7 + 65) > 0) )
  {
    v99 = DwmDbg::DbgString::DbgString((DwmDbg::DbgString *)v109, word_1802D2E32);
    v108[0] = 0;
    v108[1] = v8;
    *(_QWORD *)v111 = v114;
    v112 = v114;
    v113 = &v115;
    detail::vector_facade<CVisualTreePath::VisualTreePathUnit,detail::buffer_impl<CVisualTreePath::VisualTreePathUnit,2,1,detail::liberal_expansion_policy>>::push_back(
      v111,
      v108);
    v100 = DwmDbg::DbgString::DbgString((DwmDbg::DbgString *)v110, "PreCompute-BailWithBackdropsStillInSubtree");
    DwmDbg::Backdrops::LogTreeWalkEtwEvent(v100, v7, v8, v111, v99);
    detail::vector_facade<CVisualTreePath::VisualTreePathUnit,detail::buffer_impl<CVisualTreePath::VisualTreePathUnit,2,1,detail::liberal_expansion_policy>>::~vector_facade<CVisualTreePath::VisualTreePathUnit,detail::buffer_impl<CVisualTreePath::VisualTreePathUnit,2,1,detail::liberal_expansion_policy>>(v111);
  }
  return 0;
}

```

## disassembly

```asm
0x1800adc00  push    rbp
0x1800adc02  push    rbx
0x1800adc03  push    rdi
0x1800adc04  push    r12
0x1800adc06  push    r13
0x1800adc08  push    r14
0x1800adc0a  push    r15
0x1800adc0c  lea     rbp, [rsp-20h]
0x1800adc11  sub     rsp, 120h
0x1800adc18  mov     rax, cs:__security_cookie
0x1800adc1f  xor     rax, rsp
0x1800adc22  mov     [rbp+50h+var_70], rax
0x1800adc26  mov     r12, [rcx+600h]
0x1800adc2d  mov     r13, rcx
0x1800adc30  mov     rax, [rdx]
0x1800adc33  mov     rdi, r8
0x1800adc36  mov     r14, [rcx+5F8h]
0x1800adc3d  mov     r15, rdx
0x1800adc40  mov     rcx, rdx
0x1800adc43  mov     [rsp+150h+var_120], r8
0x1800adc48  mov     [rsp+150h+var_118], rdx
0x1800adc4d  mov     rax, [rax+0C0h]
0x1800adc54  mov     [rbp+50h+var_80], 0
0x1800adc5b  mov     qword ptr [rsp+150h+var_D8.x], r12
0x1800adc60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adc65  test    al, al
0x1800adc67  jz      short loc_1800ADC72
0x1800adc69  lea     rbx, [r14+140h]
0x1800adc70  jmp     short loc_1800ADCA7
0x1800adc72  mov     rcx, r14; this
0x1800adc75  xor     ebx, ebx
0x1800adc77  call    ?GetTreeDataListHead@CVisual@@QEBAPEAU_LIST_ENTRY@@XZ; CVisual::GetTreeDataListHead(void)
0x1800adc7c  test    rax, rax
0x1800adc7f  jz      short loc_1800ADCA7
0x1800adc81  mov     rcx, [rax]
0x1800adc84  cmp     rcx, rax
0x1800adc87  jz      short loc_1800ADCA7
0x1800adc89  nop     dword ptr [rax+00000000h]
0x1800adc90  cmp     [rcx+20h], r15
0x1800adc94  jz      short loc_1800ADCA0
0x1800adc96  mov     rcx, [rcx]
0x1800adc99  cmp     rcx, rax
0x1800adc9c  jnz     short loc_1800ADC90
0x1800adc9e  jmp     short loc_1800ADCA7
0x1800adca0  lea     rbx, [rcx-158h]
0x1800adca7  mov     [rsp+150h+arg_18], rsi
0x1800adcaf  mov     rcx, r15
0x1800adcb2  movaps  [rsp+150h+var_40], xmm6
0x1800adcba  mov     byte ptr [rdi], 0
0x1800adcbd  mov     rax, [r15]
0x1800adcc0  movaps  [rsp+150h+var_50], xmm7
0x1800adcc8  movaps  [rsp+150h+var_60], xmm8
0x1800adcd1  mov     rax, [rax+0C0h]
0x1800adcd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adcdd  mov     r8, [r14+0E0h]
0x1800adce4  xor     ecx, ecx
0x1800adce6  test    al, al
0x1800adce8  cmovz   rbx, rcx
0x1800adcec  test    dword ptr [r8], 8000000h
0x1800adcf3  mov     qword ptr [rsp+150h+var_F0], rbx
0x1800adcf8  jz      loc_1800ADD8E
0x1800adcfe  mov     edx, [r8+4]
0x1800add02  test    edx, edx
0x1800add04  jz      short loc_1800ADD14
0x1800add06  cmp     byte ptr [rcx+r8+8], 5
0x1800add0c  jz      short loc_1800ADD18
0x1800add0e  inc     ecx
0x1800add10  cmp     ecx, edx
0x1800add12  jb      short loc_1800ADD06
0x1800add14  cmp     ecx, edx
0x1800add16  jnb     short loc_1800ADD29
0x1800add18  lea     rax, [rdx+0Fh]
0x1800add1c  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800add20  add     rax, r8
0x1800add23  lea     rdx, [rax+rcx*8]
0x1800add27  jmp     short loc_1800ADD2B
0x1800add29  xor     edx, edx
0x1800add2b  mov     rdx, [rdx]
0x1800add2e  test    rdx, rdx
0x1800add31  jz      short loc_1800ADD8E
0x1800add33  mov     rax, [rdx+48h]
0x1800add37  test    rax, rax
0x1800add3a  jz      short loc_1800ADD8E
0x1800add3c  cmp     byte ptr [rax+60h], 0
0x1800add40  jz      short loc_1800ADD8E
0x1800add42  mov     rcx, r13
0x1800add45  call    ??$emplace_back@PEAVCVisualTree@@@?$vector_facade@VCPreComputeSubTreeContext@@V?$buffer_impl@VCPreComputeSubTreeContext@@$02$00Vliberal_expansion_policy@detail@@@detail@@@detail@@QEAAXPEAVCVisualTree@@@Z; detail::vector_facade<CPreComputeSubTreeContext,detail::buffer_impl<CPreComputeSubTreeContext,3,1,detail::liberal_expansion_policy>>::emplace_back<CVisualTree *>(CVisualTree *)
0x1800add4a  mov     rcx, [r13+8]
0x1800add4e  mov     rdx, r15; struct CVisualTree *
0x1800add51  sub     rcx, 160h; this
0x1800add58  call    ?BeginWalk@CPreComputeSubTreeContext@@AEAA_NPEBVCVisualTree@@@Z; CPreComputeSubTreeContext::BeginWalk(CVisualTree const *)
0x1800add5d  test    al, al
0x1800add5f  jnz     short loc_1800ADD8E
0x1800add61  mov     rbx, [r13+0]
0x1800add65  mov     rdi, [r13+8]
0x1800add69  nop     dword ptr [rax+00000000h]
0x1800add70  cmp     rbx, rdi
0x1800add73  jz      loc_1800AE8B4
0x1800add79  mov     rcx, [rbx+140h]; this
0x1800add80  call    ?SetFullDirty@CTreeDirty@@QEAAXXZ; CTreeDirty::SetFullDirty(void)
0x1800add85  add     rbx, 160h
0x1800add8c  jmp     short loc_1800ADD70
0x1800add8e  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x1800add95  xor     edi, edi
0x1800add97  mov     rcx, [r13+0]
0x1800add9b  mov     rsi, [r13+8]
0x1800add9f  mov     [rsp+150h+var_100], rcx
0x1800adda4  test    rax, rax
0x1800adda7  jz      short loc_1800ADDB0
0x1800adda9  mov     rdi, [rax+370h]
0x1800addb0  mov     rbx, rcx
0x1800addb3  mov     rcx, r14; this
0x1800addb6  cmp     rbx, rsi
0x1800addb9  jz      short loc_1800ADDE6
0x1800addbb  mov     rdx, [rbx+148h]; struct CVisualTree *
0x1800addc2  call    ?EnsureTreeData@CVisual@@QEAAPEAVCTreeData@@PEBVCVisualTree@@@Z; CVisual::EnsureTreeData(CVisualTree const *)
0x1800addc7  mov     rcx, rbx; this
0x1800addca  mov     rdx, rax
0x1800addcd  call    ?IsDirtyCollectionEnabled@CPreComputeSubTreeContext@@AEBA_NXZ; CPreComputeSubTreeContext::IsDirtyCollectionEnabled(void)
0x1800addd2  test    al, al
0x1800addd4  jz      short loc_1800ADDDD
0x1800addd6  mov     [rdx+0D0h], rdi
0x1800adddd  add     rbx, 160h
0x1800adde4  jmp     short loc_1800ADDB3
0x1800adde6  mov     rax, [r14]
0x1800adde9  mov     edx, 48h ; 'H'
0x1800addee  mov     rax, [rax+40h]
0x1800addf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800addf7  test    al, al
0x1800addf9  jz      short loc_1800ADE0A
0x1800addfb  movzx   eax, byte ptr [r14+60h]
0x1800ade00  test    al, al
0x1800ade02  jns     short loc_1800ADE0A
0x1800ade04  or      al, 4
0x1800ade06  mov     [r14+60h], al
0x1800ade0a  test    dword ptr [r14+60h], 20000000h
0x1800ade12  jz      short loc_1800ADE55
0x1800ade14  mov     eax, [r14+0D0h]
0x1800ade1b  lea     rcx, [r13+438h]
0x1800ade22  lea     rdx, [rsp+150h+var_110]
0x1800ade27  mov     [rsp+150h+var_110], eax
0x1800ade2b  call    ?Push@?$CWatermarkStack@W4Enum@MilBitmapInterpolationMode@@$0EA@$01$09@@QEAAJAEBW4Enum@MilBitmapInterpolationMode@@@Z; CWatermarkStack<MilBitmapInterpolationMode::Enum,64,2,10>::Push(MilBitmapInterpolationMode::Enum const &)
0x1800ade30  mov     ebx, eax
0x1800ade32  test    eax, eax
0x1800ade34  jns     short loc_1800ADE55
0x1800ade36  mov     rcx, [rbp+58h]; this
0x1800ade3a  lea     r8, aOnecoreuapWind_217; "onecoreuap\\windows\\dwm\\dwmcore\\engi"...
0x1800ade41  mov     r9d, eax; char *
0x1800ade44  mov     edx, 18Bh; void *
0x1800ade49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ade4e  mov     eax, ebx
0x1800ade50  jmp     loc_1800AE8B6
0x1800ade55  lea     rcx, [r13+438h]
0x1800ade5c  xor     edx, edx
0x1800ade5e  mov     eax, [rcx+8]
0x1800ade61  test    eax, eax
0x1800ade63  jz      short loc_1800ADE6F
0x1800ade65  lea     edx, [rax-1]
0x1800ade68  mov     rax, [rcx]
0x1800ade6b  lea     rdx, [rax+rdx*4]
0x1800ade6f  mov     eax, [rdx]
0x1800ade71  cmp     [r14+68h], eax
0x1800ade75  jz      short loc_1800ADE8A
0x1800ade77  call    ?GetTopByReference@?$CWatermarkStack@W4Enum@MilBackfaceVisibility@@$0EA@$01$09@@QEBAPEBW4Enum@MilBackfaceVisibility@@XZ; CWatermarkStack<MilBackfaceVisibility::Enum,64,2,10>::GetTopByReference(void)
0x1800ade7c  mov     ecx, [rax]
0x1800ade7e  mov     [r14+68h], ecx
0x1800ade82  mov     rcx, r14; this
0x1800ade85  call    ?OnOuterTransformChanged@CVisual@@AEAAXXZ; CVisual::OnOuterTransformChanged(void)
0x1800ade8a  cmp     dword ptr [r14+68h], 1
0x1800ade8f  mov     rax, [rsp+150h+var_120]
0x1800ade94  jnz     short loc_1800ADE99
0x1800ade96  mov     byte ptr [rax], 1
0x1800ade99  cmp     dword ptr [r14+104h], 0
0x1800adea1  jg      short loc_1800ADEAD
0x1800adea3  cmp     dword ptr [r14+100h], 0
0x1800adeab  jle     short loc_1800ADEB0
0x1800adead  mov     byte ptr [rax], 1
0x1800adeb0  mov     rcx, r14; this
0x1800adeb3  call    ?UpdateLayoutSize@CVisual@@IEAAXXZ; CVisual::UpdateLayoutSize(void)
0x1800adeb8  mov     rax, [r14+110h]
0x1800adebf  lea     rcx, [r13+498h]
0x1800adec6  sub     rax, [r14+108h]
0x1800adecd  sar     rax, 3
0x1800aded1  test    eax, eax
0x1800aded3  jnz     short loc_1800ADEEF
0x1800aded5  mov     rax, [r14+128h]
0x1800adedc  sub     rax, [r14+120h]
0x1800adee3  sar     rax, 3
0x1800adee7  test    eax, eax
0x1800adee9  jz      loc_1800ADFD1
0x1800adeef  mov     [rsp+150h+var_108], 0
0x1800adef7  lea     r12, [rsp+150h+var_108]
0x1800adefc  mov     [rsp+150h+var_104], 1
0x1800adf04  mov     r15d, [r12]
0x1800adf08  xor     edi, edi
0x1800adf0a  nop     word ptr [rax+rax+00h]
0x1800adf10  test    r15d, r15d
0x1800adf13  jnz     short loc_1800ADF25
0x1800adf15  mov     rax, [r14+110h]
0x1800adf1c  sub     rax, [r14+108h]
0x1800adf23  jmp     short loc_1800ADF33
0x1800adf25  mov     rax, [r14+128h]
0x1800adf2c  sub     rax, [r14+120h]
0x1800adf33  sar     rax, 3
0x1800adf37  cmp     edi, eax
0x1800adf39  jnb     short loc_1800ADFAE
0x1800adf3b  mov     edx, r15d
0x1800adf3e  mov     rcx, r14
0x1800adf41  call    ?GetLightsCount@CVisual@@QEBAIW4LightBehavior@@@Z; CVisual::GetLightsCount(LightBehavior)
0x1800adf46  cmp     edi, eax
0x1800adf48  jb      short loc_1800ADF4E
0x1800adf4a  xor     ebx, ebx
0x1800adf4c  jmp     short loc_1800ADF67
0x1800adf4e  test    r15d, r15d
0x1800adf51  jnz     short loc_1800ADF5C
0x1800adf53  mov     rax, [r14+108h]
0x1800adf5a  jmp     short loc_1800ADF63
0x1800adf5c  mov     rax, [r14+120h]
0x1800adf63  mov     rbx, [rax+rdi*8]
0x1800adf67  cmp     byte ptr [rbx+50h], 0
0x1800adf6b  jz      short loc_1800ADFA7
0x1800adf6d  mov     rax, [rbx]
0x1800adf70  mov     r8, r14
0x1800adf73  mov     rdx, [rsp+150h+var_118]
0x1800adf78  mov     rcx, rbx
0x1800adf7b  mov     rax, [rax+0F8h]
0x1800adf82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adf87  test    al, al
0x1800adf89  jz      short loc_1800ADFA7
0x1800adf8b  mov     r8d, r15d
0x1800adf8e  lea     rcx, [r13+498h]
0x1800adf95  mov     rdx, rbx
0x1800adf98  call    ?Push@CLightStack@@QEAAJPEAVCLight@@W4LightBehavior@@@Z; CLightStack::Push(CLight *,LightBehavior)
0x1800adf9d  mov     ebx, eax
0x1800adf9f  test    eax, eax
0x1800adfa1  js      loc_1800AE05F
0x1800adfa7  inc     edi
0x1800adfa9  jmp     loc_1800ADF10
0x1800adfae  add     r12, 4
0x1800adfb2  lea     rax, [rsp+150h+var_100]
0x1800adfb7  cmp     r12, rax
0x1800adfba  jnz     loc_1800ADF04
0x1800adfc0  mov     r15, [rsp+150h+var_118]
0x1800adfc5  lea     rcx, [r13+498h]
0x1800adfcc  mov     r12, qword ptr [rsp+150h+var_D8.x]
0x1800adfd1  mov     rax, [r14+0D8h]
0x1800adfd8  test    dword ptr [rax+4], 2000000h
0x1800adfdf  jz      short loc_1800ADFF0
0x1800adfe1  movzx   eax, byte ptr [r14+60h]
0x1800adfe6  test    al, 0C0h
0x1800adfe8  jz      short loc_1800ADFF0
0x1800adfea  or      al, 4
0x1800adfec  mov     [r14+60h], al
0x1800adff0  test    r12, r12
0x1800adff3  jz      short loc_1800AE002
0x1800adff5  test    byte ptr [r12+60h], 2
0x1800adffb  jz      short loc_1800AE002
0x1800adffd  or      byte ptr [r14+60h], 2
0x1800ae002  movzx   eax, byte ptr [r14+60h]
0x1800ae007  and     al, 6
0x1800ae009  cmp     al, 2
0x1800ae00b  jnz     short loc_1800AE02C
0x1800ae00d  mov     r8, rcx; struct CLightStack *
0x1800ae010  mov     rdx, r15; struct CVisualTree *
0x1800ae013  mov     rcx, r14; this
0x1800ae016  call    ?IsAffectedByNonAmbientLights@CVisual@@QEAA_NPEBVCVisualTree@@PEAVCLightStack@@@Z; CVisual::IsAffectedByNonAmbientLights(CVisualTree const *,CLightStack *)
0x1800ae01b  test    al, al
0x1800ae01d  jz      short loc_1800AE02C
0x1800ae01f  movzx   eax, byte ptr [r14+60h]
0x1800ae024  xor     al, 2
0x1800ae026  or      al, 4
0x1800ae028  mov     [r14+60h], al
0x1800ae02c  cmp     byte ptr [r14+66h], 0
0x1800ae031  jge     loc_1800AE0EB
0x1800ae037  mov     rcx, [rsp+150h+var_100]
0x1800ae03c  lea     rdx, [rsp+150h+var_D8]
0x1800ae041  mov     rcx, [rcx+140h]
0x1800ae048  cmp     byte ptr [rcx+914h], 0
0x1800ae04f  jz      short loc_1800AE0A1
0x1800ae051  movups  xmm0, cs:?sc_rcInfinite@?$TMilRect@MUD2D_RECT_F@@UD3D_RECT_F@@UNotNeeded@RectUniqueness@@@@2V1@B; TMilRect<float,D2D_RECT_F,D3D_RECT_F,RectUniqueness::NotNeeded> const TMilRect<float,D2D_RECT_F,D3D_RECT_F,RectUniqueness::NotNeeded>::sc_rcInfinite
0x1800ae058  movups  xmmword ptr [rsp+150h+var_D8.x], xmm0
0x1800ae05d  jmp     short loc_1800AE0A9
0x1800ae05f  mov     [rsp+150h+var_128], 0; void *
0x1800ae068  mov     r9d, ebx; int
0x1800ae06b  xor     r8d, r8d; unsigned int
0x1800ae06e  mov     dword ptr [rsp+150h+var_130], 4Bh ; 'K'; int
0x1800ae076  xor     edx, edx; int *
0x1800ae078  mov     ecx, 14h; unsigned int
0x1800ae07d  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800ae082  mov     rcx, [rbp+58h]; this
0x1800ae086  lea     r8, aOnecoreuapWind_217; "onecoreuap\\windows\\dwm\\dwmcore\\engi"...
0x1800ae08d  mov     r9d, ebx; char *
0x1800ae090  mov     edx, 1AFh; void *
0x1800ae095  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ae09a  mov     eax, ebx
0x1800ae09c  jmp     loc_1800AE8B6
0x1800ae0a1  call    ?GetUnoptimizedBounds@CTreeDirty@@QEBA?AV?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@XZ; CTreeDirty::GetUnoptimizedBounds(void)
0x1800ae0a6  mov     rdx, rax
0x1800ae0a9  lea     rcx, [r13+580h]
0x1800ae0b0  call    ?Push@?$CWatermarkStack@V?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@$0EA@$01$09@@QEAAJAEBV?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@@Z; CWatermarkStack<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>,64,2,10>::Push(TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const &)
  ... truncated ...
```
