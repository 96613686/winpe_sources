# CCreateRootSignatureValidator::Validate(D3D12_ROOT_SIGNATURE_DESC2 const *,D3D12_ROOT_SIGNATURE_FLAGS,bool,bool,bool,bool,D3D12_RESOURCE_BINDING_TIER,D3D_FEATURE_LEVEL)

- ea: `0x18002f374`
- end: `0x18002fcdf`
- name: `?Validate@CCreateRootSignatureValidator@@QEAAJPEBUD3D12_ROOT_SIGNATURE_DESC2@@W4D3D12_ROOT_SIGNATURE_FLAGS@@_N222W4D3D12_RESOURCE_BINDING_TIER@@W4D3D_FEATURE_LEVEL@@@Z`
- size: `2411`
- prototype: `__int64 __fastcall(CCreateRootSignatureValidator *__hidden this, const struct D3D12_ROOT_SIGNATURE_DESC2 *, enum D3D12_ROOT_SIGNATURE_FLAGS, bool, bool, bool, bool, enum D3D12_RESOURCE_BINDING_TIER, enum D3D_FEATURE_LEVEL)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1800b8200`

## callees

- `0x18000b920`
- `0x18002ef50`
- `0x18002f374`
- `0x18002fce8`
- `0x18002fd70`
- `0x180031c8c`
- `0x18006a2e0`
- `0x1800a901c`
- `0x1800bb480`
- `0x1800bb4d0`
- `0x1800bb98c`

## string_xrefs

- `0x1802338f5`: `Root Signature Parameter [%d], Descriptor Table Range [%d], for %s, specifies -1 for NumDescriptors, which means an unbounded array size.  This is not supported for %s on a %s level device.`
- `0x1802338be`: `Root descriptors created at D3D_FEATURE_LEVEL_1_0_CORE must not use sampler descriptor ranges.`
- `0x18002fa7b`: `Root signatures at D3D_FEATURE_LEVEL_1_0_CORE must not use D3D12_DESCRIPTOR_RANGE_FLAG_DESCRIPTORS_STATIC_KEEPING_BUFFER_BOUNDS_CHECKS flag since bounds checking isn't supported.`
- `0x18002fc66`: `Root Signature size exceeds maximum of %d 32-bit units (with system reserved space for tools enabled - not counting that, applications only have %d available).  Costs in units: Descriptor Tables cost %d each, Root CBVs cost %d each, Root SRVs cost %d each, Root UAVs cost %d each, and Root Constants cost 1 per 32-bit value.`
- `0x18002fc9a`: `Root Signature size exceeds maximum of %d 32-bit units.  Costs in units: Descriptor Tables cost %d each, Root CBVs cost %d each, Root SRVs cost %d each, Root UAVs cost %d each, and Root Constants cost 1 per 32-bit value.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCreateRootSignatureValidator::Validate(
        CCreateRootSignatureValidator *this,
        const struct D3D12_ROOT_SIGNATURE_DESC2 *a2,
        enum D3D12_ROOT_SIGNATURE_FLAGS a3,
        char a4,
        bool a5,
        bool a6,
        bool a7,
        enum D3D12_RESOURCE_BINDING_TIER a8,
        enum D3D_FEATURE_LEVEL a9)
{
  const struct D3D12_ROOT_SIGNATURE_DESC2 *v9; // rsi
  unsigned int v10; // r14d
  unsigned int v11; // edi
  __int64 *v12; // rcx
  int v13; // r8d
  unsigned int i; // eax
  _DWORD *v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rsi
  int v19; // r12d
  __int64 j; // rax
  int *v21; // r9
  unsigned int v22; // edi
  int v23; // eax
  int v24; // r12d
  unsigned int v25; // r14d
  __int64 FirstIntersectingInterval; // r8
  __int64 *v27; // rax
  _QWORD *v28; // rdx
  int v29; // edx
  int v30; // edx
  int v31; // edx
  int v32; // r9d
  __int64 k; // rcx
  __int64 v34; // r8
  int v35; // r9d
  __int64 m; // rcx
  int v37; // r9d
  __int64 n; // rcx
  int v39; // r9d
  __int64 ii; // rcx
  __int64 v41; // rax
  __int64 v42; // r8
  int *v43; // r9
  unsigned int v44; // r10d
  unsigned int v45; // r11d
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  const char *v48; // rax
  int v49; // r9d
  unsigned int v50; // edx
  __int64 v51; // r8
  __int64 v52; // rsi
  unsigned int v53; // r15d
  unsigned int v54; // r14d
  __int64 v55; // rsi
  unsigned int v56; // r14d
  unsigned int v57; // r15d
  __int64 v58; // rax
  unsigned int v59; // r9d
  unsigned int v60; // r9d
  unsigned int v61; // r9d
  unsigned int v62; // r9d
  const char *v63; // [rsp+38h] [rbp-1B0h]
  int v64; // [rsp+50h] [rbp-198h] BYREF
  char v65; // [rsp+54h] [rbp-194h]
  enum D3D12_RESOURCE_BINDING_TIER v66; // [rsp+58h] [rbp-190h] BYREF
  char v67; // [rsp+60h] [rbp-188h]
  int v68; // [rsp+64h] [rbp-184h] BYREF
  unsigned int v69; // [rsp+68h] [rbp-180h]
  int v70; // [rsp+6Ch] [rbp-17Ch] BYREF
  unsigned int v71; // [rsp+70h] [rbp-178h]
  int *v72; // [rsp+78h] [rbp-170h] BYREF
  _DWORD *v73; // [rsp+80h] [rbp-168h] BYREF
  unsigned int v74; // [rsp+88h] [rbp-160h]
  unsigned int v75; // [rsp+8Ch] [rbp-15Ch]
  unsigned int v76; // [rsp+90h] [rbp-158h]
  _DWORD v77[2]; // [rsp+98h] [rbp-150h] BYREF
  const struct D3D12_ROOT_SIGNATURE_DESC2 *v78; // [rsp+A0h] [rbp-148h]
  _QWORD v79[8]; // [rsp+A8h] [rbp-140h] BYREF
  _OWORD v80[2]; // [rsp+E8h] [rbp-100h] BYREF
  _OWORD v81[2]; // [rsp+108h] [rbp-E0h] BYREF
  _OWORD v82[2]; // [rsp+128h] [rbp-C0h] BYREF
  _OWORD v83[2]; // [rsp+148h] [rbp-A0h] BYREF
  _QWORD v84[2]; // [rsp+170h] [rbp-78h] BYREF
  __int64 v85; // [rsp+180h] [rbp-68h]
  __int64 v86; // [rsp+190h] [rbp-58h]
  __int64 v87; // [rsp+1A0h] [rbp-48h]

  v67 = a4;
  v9 = a2;
  v78 = a2;
  v66 = a8;
  v64 = 0;
  memset(v80, 0, sizeof(v80));
  memset(v81, 0, sizeof(v81));
  memset(v83, 0, sizeof(v83));
  memset(v82, 0, sizeof(v82));
  v10 = dword_1802CBE28[a8];
  v71 = v10;
  if ( v10 < 0xF )
  {
    if ( a3 < D3D12_ROOT_SIGNATURE_FLAG_NONE )
      v10 = 15;
    v71 = v10;
  }
  if ( a9 == 256 )
  {
    v64 = 1;
    TDebugOutputFunctor::operator()(
      &g_coreRuntimeTallyErrorOutputFunctor,
      699,
      "Root Signature not supported in D3D_FEATURE_LEVEL_1_0_GENERIC.");
    return 2147942487LL;
  }
  v11 = 0;
  v69 = 0;
  v74 = dword_1802CBE70[a8];
  v12 = qword_1802CBE58;
  if ( a9 < D3D_FEATURE_LEVEL_11_1 )
    v12 = qword_1802CBE40;
  v76 = *((_DWORD *)v12 + (int)a8);
  v75 = dword_1802CBE10[a8];
  v65 = 0;
  if ( *((char *)a2 + 32) < 0 )
  {
    v65 = 1;
    if ( !a5 )
    {
      v64 = 1;
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        699,
        "Root Signature flag D3D12_ROOT_SIGNATURE_FLAG_LOCAL_ROOT_SIGNATURE can only be set on devices that support raytracing.");
    }
  }
  v13 = 0;
  for ( i = 0; ; i = v13 )
  {
    v70 = v13;
    if ( i >= *(_DWORD *)v9 )
      break;
    v16 = (_DWORD *)(*((_QWORD *)v9 + 1) + 32LL * i);
    v73 = v16;
    if ( !*v16 )
    {
      `eh vector constructor iterator'(
        v84,
        0x10u,
        4u,
        (void (*)(void *))CDescriptorHeap::TMirroredData::TMirroredData,
        RBTree::CIntervalTree<RBTree::CSimpleIntervalNode<unsigned int>,std::default_delete<RBTree::CSimpleIntervalNode<unsigned int>>>::~CIntervalTree<RBTree::CSimpleIntervalNode<unsigned int>,std::default_delete<RBTree::CSimpleIntervalNode<unsigned int>>>);
      v18 = 0;
      v19 = 0;
      v68 = 0;
      for ( j = 0; ; j = (unsigned int)++v68 )
      {
        if ( (unsigned int)j >= v73[2] )
        {
          v11 = ++v69;
          if ( a7 == (_BYTE)v18 )
          {
            v32 = v18;
            k = v18;
            if ( v84[0] )
            {
              for ( k = v84[0]; *(_QWORD *)(k + 8) != v18; k = *(_QWORD *)(k + 8) )
                ;
            }
            for ( ;
                  k;
                  k = RBTree::CTree<RBTree::CSimpleIntervalNode<unsigned int>,std::default_delete<RBTree::CSimpleIntervalNode<unsigned int>>>::IterateNext(
                        k,
                        k,
                        v17,
                        (unsigned int)(*(_DWORD *)(k + 36) - *(_DWORD *)(k + 32) + 1 + v32)) )
            {
              ;
            }
            v34 = (int)v73[6];
            *((_DWORD *)v81 + v34) += v32;
            v35 = v18;
            m = v18;
            if ( v85 )
            {
              for ( m = v85; *(_QWORD *)(m + 8) != v18; m = *(_QWORD *)(m + 8) )
                ;
            }
            for ( ;
                  m;
                  m = RBTree::CTree<RBTree::CSimpleIntervalNode<unsigned int>,std::default_delete<RBTree::CSimpleIntervalNode<unsigned int>>>::IterateNext(
                        m,
                        m,
                        v34,
                        (unsigned int)(*(_DWORD *)(m + 36) - *(_DWORD *)(m + 32) + 1 + v35)) )
            {
              ;
            }
            *((_DWORD *)v83 + v34) += v35;
            v37 = v18;
            n = v18;
            if ( v86 )
            {
              for ( n = v86; *(_QWORD *)(n + 8) != v18; n = *(_QWORD *)(n + 8) )
                ;
            }
            for ( ;
                  n;
                  n = RBTree::CTree<RBTree::CSimpleIntervalNode<unsigned int>,std::default_delete<RBTree::CSimpleIntervalNode<unsigned int>>>::IterateNext(
                        n,
                        n,
                        v34,
                        (unsigned int)(*(_DWORD *)(n + 36) - *(_DWORD *)(n + 32) + 1 + v37)) )
            {
              ;
            }
            *((_DWORD *)v80 + v34) += v37;
            v39 = v18;
            ii = v18;
            if ( v87 )
            {
              for ( ii = v87; *(_QWORD *)(ii + 8) != v18; ii = *(_QWORD *)(ii + 8) )
                ;
            }
            for ( ;
                  ii;
                  ii = RBTree::CTree<RBTree::CSimpleIntervalNode<unsigned int>,std::default_delete<RBTree::CSimpleIntervalNode<unsigned int>>>::IterateNext(
                         ii,
                         ii,
                         v34,
                         (unsigned int)(*(_DWORD *)(ii + 36) - *(_DWORD *)(ii + 32) + 1 + v39)) )
            {
              ;
            }
            *((_DWORD *)v82 + v34) += v39;
          }
          `eh vector destructor iterator'(
            v84,
            0x10u,
            4u,
            RBTree::CIntervalTree<RBTree::CSimpleIntervalNode<unsigned int>,std::default_delete<RBTree::CSimpleIntervalNode<unsigned int>>>::~CIntervalTree<RBTree::CSimpleIntervalNode<unsigned int>,std::default_delete<RBTree::CSimpleIntervalNode<unsigned int>>>);
          v13 = v70;
          v9 = v78;
          goto LABEL_39;
        }
        v21 = (int *)(*((_QWORD *)v73 + 2) + 24 * j);
        v72 = v21;
        if ( a9 == 4096 )
        {
          if ( (v21[4] & 0x10000) != 0 )
          {
            ++v64;
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              699,
              "Root signatures at D3D_FEATURE_LEVEL_1_0_CORE must not use D3D12_DESCRIPTOR_RANGE_FLAG_DESCRIPTORS_STATIC_"
              "KEEPING_BUFFER_BOUNDS_CHECKS flag since bounds checking isn't supported.");
            v21 = v72;
          }
          if ( *v21 == 3 )
          {
            ++v64;
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              699,
              "Root descriptors created at D3D_FEATURE_LEVEL_1_0_CORE must not use sampler descriptor ranges.");
            v21 = v72;
          }
        }
        v22 = v21[5];
        v17 = 0xFFFFFFFFLL;
        if ( v22 == -1 )
          v22 = v19;
        v23 = v21[1];
        if ( v23 == -1 )
          v24 = -1;
        else
          v24 = v23 + v22 - 1;
        if ( a7 == (_BYTE)v18 )
        {
          v25 = v24;
          v77[0] = v22;
          v77[1] = v24;
          FirstIntersectingInterval = RBTree::CIntervalTree<RBTree::CSimpleIntervalNode<unsigned int>,std::default_delete<RBTree::CSimpleIntervalNode<unsigned int>>>::FindFirstIntersectingInterval(
                                        &v84[2 * *v21],
                                        v77,
                                        0);
          if ( FirstIntersectingInterval )
          {
            do
            {
              v46 = *(_DWORD *)(FirstIntersectingInterval + 32);
              if ( v46 >= v22 )
                v46 = v22;
              v22 = v46;
              v47 = *(_DWORD *)(FirstIntersectingInterval + 36);
              if ( v47 <= v25 )
                v47 = v25;
              v25 = v47;
              while ( 1 )
              {
                v41 = ((__int64 (*)(void))RBTree::CTree<RBTree::CSimpleIntervalNode<unsigned int>,std::default_delete<RBTree::CSimpleIntervalNode<unsigned int>>>::IterateNext)();
                v18 = v41;
                if ( !v41 )
                  break;
                if ( v44 >= *(_DWORD *)(v41 + 32) )
                {
                  if ( v45 <= *(_DWORD *)(v41 + 36) )
                    break;
                  if ( v44 >= *(_DWORD *)(v41 + 32) )
                    continue;
                }
                v18 = 0;
                break;
              }
              RBTree::CRBTree<RBTree::CSimpleIntervalNode<unsigned int>,1,std::default_delete<RBTree::CSimpleIntervalNode<unsigned int>>,RBTree::Less<unsigned int>>::Delete(
                &v84[2 * *v43],
                v42);
              FirstIntersectingInterval = v18;
            }
            while ( v18 );
          }
          v27 = (__int64 *)operator new(0x30u);
          v28 = v27;
          if ( v27 )
          {
            *v27 = v18;
            v27[1] = v18;
            v27[2] = v18;
            *((_DWORD *)v27 + 6) = v18;
            *((_DWORD *)v27 + 7) = v22;
            *((_DWORD *)v27 + 8) = v22;
            *((_DWORD *)v27 + 9) = v25;
          }
          else
          {
            v28 = (_QWORD *)v18;
          }
          RBTree::CRBTree<RBTree::CSimpleIntervalNode<unsigned int>,1,std::default_delete<RBTree::CSimpleIntervalNode<unsigned int>>,RBTree::Less<unsigned int>>::Insert(
            &v84[2 * *v72],
            v28);
          v21 = v72;
          v10 = v71;
          v17 = 0xFFFFFFFFLL;
        }
        v19 = v24 + 1;
        v79[0] = &v72;
        v79[1] = &v64;
        v79[2] = &v70;
        v79[3] = &v68;
        v79[4] = &v66;
        v79[5] = &a7;
        v79[6] = &v73;
        if ( *v21 )
        {
          switch ( *v21 )
          {
            case 1:
              v29 = v21[1];
              if ( v29 == -1 )
              {
                if ( v76 == -1 )
                  continue;
                v63 = (const char *)off_18027B8C0[v66];
                v48 = "UAVs";
                goto LABEL_118;
              }
              if ( a7 != (_BYTE)v18 )
                *((_DWORD *)v83 + (int)v73[6]) += v29;
              break;
            case 2:
              lambda_816af2ad50554ed20ec27c82c6d41392_::operator()(v79, v80, v10, "CBVs");
              continue;
            case 3:
              v31 = v21[1];
              if ( v31 == -1 )
              {
                if ( v75 == -1 )
                  continue;
                v63 = (const char *)off_18027B8C0[v66];
                v48 = "Samplers";
LABEL_118:
                ++v64;
                TDebugOutputFunctor::operator()(
                  &g_coreRuntimeTallyErrorOutputFunctor,
                  699,
                  "Root Signature Parameter [%d], Descriptor Table Range [%d], for %s, specifies -1 for NumDescriptors, w"
                  "hich means an unbounded array size.  This is not supported for %s on a %s level device.",
                  v70,
                  v68,
                  v48,
                  v48,
                  v63);
                continue;
              }
              if ( a7 != (_BYTE)v18 )
                *((_DWORD *)v82 + (int)v73[6]) += v31;
              break;
            default:
              continue;
          }
        }
        else
        {
          v30 = v21[1];
          if ( v30 == -1 )
          {
            if ( v74 == -1 )
              continue;
            v63 = (const char *)off_18027B8C0[v66];
            v48 = "SRVs";
            goto LABEL_118;
          }
          if ( a7 != (_BYTE)v18 )
            *((_DWORD *)v81 + (int)v73[6]) += v30;
        }
      }
    }
    switch ( *v16 )
    {
      case 1:
        v11 += v16[4];
        goto LABEL_115;
      case 2:
        v11 += 2;
LABEL_115:
        v69 = v11;
        ++*((_DWORD *)v80 + (int)v16[6]);
        break;
      case 3:
        v11 += 2;
        v69 = v11;
        ++*((_DWORD *)v81 + (int)v16[6]);
        break;
      case 4:
        v11 += 2;
        v69 = v11;
        ++*((_DWORD *)v83 + (int)v16[6]);
        break;
    }
LABEL_39:
    ++v13;
  }
  if ( a9 == 4096 )
  {
    v49 = *((_DWORD *)v9 + 4);
    if ( v49 )
    {
      ++v64;
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        699,
        "This root signature has %d static sampler(s), but static samplers are not supported in D3D_FEATURE_LEVEL_1_0_CORE.",
        v49);
    }
  }
  if ( *((_DWORD *)v9 + 4) )
  {
    v50 = 0;
    v51 = *((_QWORD *)v9 + 3);
    do
    {
      v58 = *(int *)(56LL * v50 + v51 + 48);
      ++*((_DWORD *)v82 + v58);
      ++v50;
    }
    while ( v50 < *((_DWORD *)v9 + 4) );
  }
  if ( !v65 )
  {
    if ( v67 )
    {
      if ( v11 > 0x80 )
      {
        ++v64;
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          699,
          "Root Signature size exceeds maximum of %d 32-bit units (with system reserved space for tools enabled - not cou"
          "nting that, applications only have %d available).  Costs in units: Descriptor Tables cost %d each, Root CBVs c"
          "ost %d each, Root SRVs cost %d each, Root UAVs cost %d each, and Root Constants cost 1 per 32-bit value.",
          128,
          64,
          1,
          2,
          2,
          2);
      }
    }
    else if ( v11 > 0x40 )
    {
      ++v64;
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        699,
        "Root Signature size exceeds maximum of %d 32-bit units.  Costs in units: Descriptor Tables cost %d each, Root CB"
        "Vs cost %d each, Root SRVs cost %d each, Root UAVs cost %d each, and Root Constants cost 1 per 32-bit value.",
        64,
        1,
        2,
        2,
        2);
    }
  }
  if ( v66 <= D3D12_RESOURCE_BINDING_TIER_1 )
  {
    v52 = 0;
    v53 = v81[0];
    v54 = v82[0];
    do
    {
      if ( (_DWORD)v52 )
      {
        *((_DWORD *)v81 + v52) += v53;
        *((_DWORD *)v82 + v52) += v54;
        v53 = v81[0];
        v54 = v82[0];
      }
      v59 = *((_DWORD *)v81 + v52);
      if ( v59 > v74 && (!(_DWORD)v52 || v59 > v53) )
      {
        ++v64;
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          699,
          "Root Signature declares %d SRVs total across all parameters%s. This number cannot exceed %d for a %s level device.",
          v59,
          (const char *)off_18027B8F0[v52],
          v74,
          (const char *)off_18027B8C0[v66]);
      }
      v60 = *((_DWORD *)v82 + v52);
      if ( v60 > v75 && (!(_DWORD)v52 || v60 > v54) )
      {
        ++v64;
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          699,
          "Root Signature declares %d Samplers total across all parameters%s. This number cannot exceed %d for a %s level device.",
          v60,
          (const char *)off_18027B8F0[v52],
          v75,
          (const char *)off_18027B8C0[v66]);
      }
      v52 = (unsigned int)(v52 + 1);
    }
    while ( (unsigned int)v52 <= 7 );
  }
  if ( v66 <= D3D12_RESOURCE_BINDING_TIER_2 )
  {
    v55 = 0;
    v56 = v80[0];
    v57 = v83[0];
    do
    {
      if ( (_DWORD)v55 )
      {
        *((_DWORD *)v83 + v55) += v57;
        *((_DWORD *)v80 + v55) += v56;
        v56 = v80[0];
        v57 = v83[0];
      }
      v61 = *((_DWORD *)v83 + v55);
      if ( v61 > v76 && (!(_DWORD)v55 || v61 > v57) )
      {
        ++v64;
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          699,
          "Root Signature declares %d UAVs total across all parameters%s. This number cannot exceed %d for a %s level device.",
          v61,
          (const char *)off_18027B8F0[v55],
          v76,
          (const char *)off_18027B8C0[v66]);
      }
      v62 = *((_DWORD *)v80 + v55);
      if ( v62 > v71 && (!(_DWORD)v55 || v62 > v56) )
      {
        ++v64;
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          699,
          "Root Signature declares %d CBVs total across all parameters%s. This number cannot exceed %d for a %s level device.",
          v62,
          (const char *)off_18027B8F0[v55],
          v71,
          (const char *)off_18027B8C0[v66]);
      }
      v55 = (unsigned int)(v55 + 1);
    }
    while ( (unsigned int)v55 <= 7 );
  }
  return v64 != 0 ? 0x80070057 : 0;
}

```

## disassembly

```asm
0x18002f374  mov     [rsp+arg_0], rbx
0x18002f379  mov     [rsp+arg_10], rsi
0x18002f37e  push    rdi
0x18002f37f  push    r12
0x18002f381  push    r13
0x18002f383  push    r14
0x18002f385  push    r15
0x18002f387  sub     rsp, 1C0h
0x18002f38e  mov     rax, cs:__security_cookie
0x18002f395  xor     rax, rsp
0x18002f398  mov     [rsp+1E8h+var_38], rax
0x18002f3a0  mov     [rsp+1E8h+var_188], r9b
0x18002f3a5  mov     rsi, rdx
0x18002f3a8  mov     [rsp+1E8h+var_148], rdx
0x18002f3b0  movsxd  rcx, [rsp+1E8h+arg_38]
0x18002f3b8  mov     [rsp+1E8h+var_190], ecx
0x18002f3bc  mov     [rsp+1E8h+var_198], 0
0x18002f3c4  xorps   xmm0, xmm0
0x18002f3c7  movups  [rsp+1E8h+var_100], xmm0
0x18002f3cf  movups  [rsp+1E8h+var_F0], xmm0
0x18002f3d7  xorps   xmm1, xmm1
0x18002f3da  movups  [rsp+1E8h+var_E0], xmm1
0x18002f3e2  movups  [rsp+1E8h+var_D0], xmm1
0x18002f3ea  movups  [rsp+1E8h+var_A0], xmm0
0x18002f3f2  movups  [rsp+1E8h+var_90], xmm0
0x18002f3fa  movups  [rsp+1E8h+var_C0], xmm1
0x18002f402  movups  [rsp+1E8h+var_B0], xmm1
0x18002f40a  mov     rax, rcx
0x18002f40d  lea     r9, __ImageBase
0x18002f414  mov     r14d, ds:rva dword_1802CBE28[r9+rcx*4]
0x18002f41c  mov     [rsp+1E8h+var_178], r14d
0x18002f421  mov     edx, 0Fh
0x18002f426  cmp     r14d, edx
0x18002f429  jb      loc_18002F85D
0x18002f42f  cmp     [rsp+1E8h+arg_40], 100h
0x18002f43a  jz      loc_18002F54F
0x18002f440  xor     edi, edi
0x18002f442  mov     [rsp+1E8h+var_180], edi
0x18002f446  mov     rdx, rcx
0x18002f449  mov     ecx, ds:rva dword_1802CBE70[r9+rcx*4]
0x18002f451  mov     [rsp+1E8h+var_160], ecx
0x18002f458  cmp     [rsp+1E8h+arg_40], 0B100h
0x18002f463  lea     rcx, rva qword_1802CBE58[r9]
0x18002f46a  jl      loc_18002F81E
0x18002f470  lea     rcx, [rcx+rax*4]
0x18002f474  mov     eax, [rcx]
0x18002f476  mov     [rsp+1E8h+var_158], eax
0x18002f47d  mov     eax, ds:rva dword_1802CBE10[r9+rdx*4]
0x18002f485  mov     [rsp+1E8h+var_15C], eax
0x18002f48c  mov     [rsp+1E8h+var_194], dil
0x18002f491  mov     ebx, 1
0x18002f496  mov     r13d, 2BBh
0x18002f49c  lea     r15, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x18002f4a3  test    byte ptr [rsi+20h], 80h
0x18002f4a7  jnz     loc_18002FA15
0x18002f4ad  xor     r8d, r8d
0x18002f4b0  xor     eax, eax
0x18002f4b2  lea     r9d, [r8+2]
0x18002f4b6  lea     r12, ??1?$CIntervalTree@V?$CSimpleIntervalNode@I@RBTree@@U?$default_delete@V?$CSimpleIntervalNode@I@RBTree@@@std@@@RBTree@@QEAA@XZ; RBTree::CIntervalTree<RBTree::CSimpleIntervalNode<uint>,std::default_delete<RBTree::CSimpleIntervalNode<uint>>>::~CIntervalTree<RBTree::CSimpleIntervalNode<uint>,std::default_delete<RBTree::CSimpleIntervalNode<uint>>>(void)
0x18002f4bd  mov     [rsp+1E8h+var_17C], r8d
0x18002f4c2  cmp     eax, [rsi]
0x18002f4c4  jb      loc_18002F577
0x18002f4ca  cmp     [rsp+1E8h+arg_40], 1000h
0x18002f4d5  jz      loc_18002FC03
0x18002f4db  cmp     dword ptr [rsi+10h], 0
0x18002f4df  ja      loc_18002FC2C
0x18002f4e5  cmp     [rsp+1E8h+var_194], 0
0x18002f4ea  jnz     short loc_18002F500
0x18002f4ec  cmp     [rsp+1E8h+var_188], 0
0x18002f4f1  jnz     loc_18002FC37
0x18002f4f7  cmp     edi, 40h ; '@'
0x18002f4fa  ja      loc_18002FC7D
0x18002f500  cmp     [rsp+1E8h+var_190], ebx
0x18002f504  jle     loc_18002FCB1
0x18002f50a  cmp     [rsp+1E8h+var_190], 2
0x18002f50f  jle     loc_18002FCC8
0x18002f515  mov     eax, [rsp+1E8h+var_198]
0x18002f519  neg     eax
0x18002f51b  sbb     eax, eax
0x18002f51d  and     eax, 80070057h
0x18002f522  mov     rcx, [rsp+1E8h+var_38]
0x18002f52a  xor     rcx, rsp; StackCookie
0x18002f52d  call    __security_check_cookie
0x18002f532  lea     r11, [rsp+1E8h+var_28]
0x18002f53a  mov     rbx, [r11+30h]
0x18002f53e  mov     rsi, [r11+40h]
0x18002f542  mov     rsp, r11
0x18002f545  pop     r15
0x18002f547  pop     r14
0x18002f549  pop     r13
0x18002f54b  pop     r12
0x18002f54d  pop     rdi
0x18002f54e  retn
0x18002f54f  mov     ebx, 1
0x18002f554  mov     [rsp+1E8h+var_198], ebx
0x18002f558  lea     r8, aRootSignatureN; "Root Signature not supported in D3D_FEA"...
0x18002f55f  mov     edx, 2BBh
0x18002f564  lea     rcx, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x18002f56b  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18002f570  mov     eax, 80070057h
0x18002f575  jmp     short loc_18002F522
0x18002f577  mov     edx, eax
0x18002f579  shl     rdx, 5
0x18002f57d  add     rdx, [rsi+8]
0x18002f581  mov     [rsp+1E8h+var_168], rdx
0x18002f589  mov     ecx, [rdx]
0x18002f58b  test    ecx, ecx
0x18002f58d  jnz     loc_18002F95B
0x18002f593  mov     [rsp+1E8h+var_1C8], r12; void (*)(void *)
0x18002f598  lea     r9, ??0TMirroredData@CDescriptorHeap@@QEAA@XZ; void (*)(void *)
0x18002f59f  lea     edx, [rcx+10h]; unsigned __int64
0x18002f5a2  lea     r8d, [rcx+4]; unsigned __int64
0x18002f5a6  lea     rcx, [rsp+1E8h+var_78]; void *
0x18002f5ae  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18002f5b3  nop
0x18002f5b4  xor     esi, esi
0x18002f5b6  mov     r12d, esi
0x18002f5b9  mov     [rsp+1E8h+var_184], esi
0x18002f5bd  mov     eax, esi
0x18002f5bf  mov     rdx, [rsp+1E8h+var_168]
0x18002f5c7  cmp     eax, [rdx+8]
0x18002f5ca  jnb     loc_18002F762
0x18002f5d0  lea     rcx, [rax+rax*2]
0x18002f5d4  mov     rax, [rdx+10h]
0x18002f5d8  lea     r9, [rax+rcx*8]
0x18002f5dc  mov     [rsp+1E8h+var_170], r9
0x18002f5e1  cmp     [rsp+1E8h+arg_40], 1000h
0x18002f5ec  jz      loc_18002FA69
0x18002f5f2  mov     edi, [r9+14h]
0x18002f5f6  or      r8d, 0FFFFFFFFh
0x18002f5fa  cmp     edi, r8d
0x18002f5fd  cmovz   edi, r12d
0x18002f601  mov     eax, [r9+4]
0x18002f605  cmp     eax, r8d
0x18002f608  jnz     loc_18002F756
0x18002f60e  mov     r12d, r8d
0x18002f611  cmp     [rsp+1E8h+arg_30], sil
0x18002f619  jnz     loc_18002F6BD
0x18002f61f  mov     r14d, r12d
0x18002f622  mov     r11d, edi
0x18002f625  mov     [rsp+1E8h+var_150], edi
0x18002f62c  mov     r10d, r12d
0x18002f62f  mov     [rsp+1E8h+var_14C], r12d
0x18002f637  movsxd  rax, dword ptr [r9]
0x18002f63a  shl     rax, 4
0x18002f63e  lea     rcx, [rsp+1E8h+var_78]
0x18002f646  add     rcx, rax
0x18002f649  xor     r8d, r8d
0x18002f64c  lea     rdx, [rsp+1E8h+var_150]
0x18002f654  call    ?FindFirstIntersectingInterval@?$CIntervalTree@V?$CSimpleIntervalNode@I@RBTree@@U?$default_delete@V?$CSimpleIntervalNode@I@RBTree@@@std@@@RBTree@@QEBAPEAV?$CSimpleIntervalNode@I@2@AEBV?$CValueRange@I@2@PEAV32@@Z; RBTree::CIntervalTree<RBTree::CSimpleIntervalNode<uint>,std::default_delete<RBTree::CSimpleIntervalNode<uint>>>::FindFirstIntersectingInterval(RBTree::CValueRange<uint> const &,RBTree::CSimpleIntervalNode<uint> *)
0x18002f659  mov     r8, rax
0x18002f65c  test    rax, rax
0x18002f65f  jnz     loc_18002F9F7
0x18002f665  mov     ecx, 30h ; '0'; dwBytes
0x18002f66a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f66f  mov     rdx, rax
0x18002f672  test    rax, rax
0x18002f675  jz      loc_18002FA97
0x18002f67b  mov     [rax], rsi
0x18002f67e  mov     [rax+8], rsi
0x18002f682  mov     [rax+10h], rsi
0x18002f686  mov     [rax+18h], esi
0x18002f689  mov     [rax+1Ch], edi
0x18002f68c  mov     [rax+20h], edi
0x18002f68f  mov     [rax+24h], r14d
0x18002f693  mov     rax, [rsp+1E8h+var_170]
0x18002f698  movsxd  rcx, dword ptr [rax]
0x18002f69b  shl     rcx, 4
0x18002f69f  lea     rax, [rsp+1E8h+var_78]
0x18002f6a7  add     rcx, rax
0x18002f6aa  call    ?Insert@?$CRBTree@V?$CSimpleIntervalNode@I@RBTree@@$00U?$default_delete@V?$CSimpleIntervalNode@I@RBTree@@@std@@V?$Less@I@2@@RBTree@@QEAA_NPEAV?$CSimpleIntervalNode@I@2@@Z; RBTree::CRBTree<RBTree::CSimpleIntervalNode<uint>,1,std::default_delete<RBTree::CSimpleIntervalNode<uint>>,RBTree::Less<uint>>::Insert(RBTree::CSimpleIntervalNode<uint> *)
0x18002f6af  mov     r9, [rsp+1E8h+var_170]
0x18002f6b4  mov     r14d, [rsp+1E8h+var_178]
0x18002f6b9  or      r8d, 0FFFFFFFFh
0x18002f6bd  inc     r12d
0x18002f6c0  lea     rax, [rsp+1E8h+var_170]
0x18002f6c5  mov     [rsp+1E8h+var_140], rax
0x18002f6cd  lea     rax, [rsp+1E8h+var_198]
0x18002f6d2  mov     [rsp+1E8h+var_138], rax
0x18002f6da  lea     rax, [rsp+1E8h+var_17C]
0x18002f6df  mov     [rsp+1E8h+var_130], rax
0x18002f6e7  lea     rax, [rsp+1E8h+var_184]
0x18002f6ec  mov     [rsp+1E8h+var_128], rax
0x18002f6f4  lea     rax, [rsp+1E8h+var_190]
0x18002f6f9  mov     [rsp+1E8h+var_120], rax
0x18002f701  lea     rax, [rsp+1E8h+arg_30]
0x18002f709  mov     [rsp+1E8h+var_118], rax
0x18002f711  lea     rax, [rsp+1E8h+var_168]
0x18002f719  mov     [rsp+1E8h+var_110], rax
0x18002f721  mov     ecx, [r9]
0x18002f724  test    ecx, ecx
0x18002f726  jz      loc_18002F7EB
0x18002f72c  sub     ecx, 1
0x18002f72f  jz      loc_18002F7B8
0x18002f735  sub     ecx, 1
0x18002f738  jz      loc_18002FAF9
0x18002f73e  cmp     ecx, 1
0x18002f741  jz      loc_18002F82A
0x18002f747  mov     eax, [rsp+1E8h+var_184]
0x18002f74b  add     eax, ebx
0x18002f74d  mov     [rsp+1E8h+var_184], eax
0x18002f751  jmp     loc_18002F5BF
0x18002f756  lea     r12d, [rdi-1]
0x18002f75a  add     r12d, eax
0x18002f75d  jmp     loc_18002F611
0x18002f762  mov     edi, [rsp+1E8h+var_180]
0x18002f766  add     edi, ebx
0x18002f768  mov     [rsp+1E8h+var_180], edi
0x18002f76c  cmp     [rsp+1E8h+arg_30], sil
0x18002f774  jz      loc_18002F86E
0x18002f77a  lea     r12, ??1?$CIntervalTree@V?$CSimpleIntervalNode@I@RBTree@@U?$default_delete@V?$CSimpleIntervalNode@I@RBTree@@@std@@@RBTree@@QEAA@XZ; RBTree::CIntervalTree<RBTree::CSimpleIntervalNode<uint>,std::default_delete<RBTree::CSimpleIntervalNode<uint>>>::~CIntervalTree<RBTree::CSimpleIntervalNode<uint>,std::default_delete<RBTree::CSimpleIntervalNode<uint>>>(void)
0x18002f781  mov     r9, r12; void (*)(void *)
0x18002f784  mov     edx, 10h; unsigned __int64
0x18002f789  lea     r8d, [rdx-0Ch]; unsigned __int64
0x18002f78d  lea     rcx, [rsp+1E8h+var_78]; void *
0x18002f795  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18002f79a  mov     r8d, [rsp+1E8h+var_17C]
0x18002f79f  mov     rsi, [rsp+1E8h+var_148]
0x18002f7a7  mov     r9d, 2
0x18002f7ad  add     r8d, ebx
0x18002f7b0  mov     eax, r8d
0x18002f7b3  jmp     loc_18002F4BD
0x18002f7b8  mov     edx, [r9+4]
0x18002f7bc  cmp     edx, r8d
0x18002f7bf  jz      loc_18002FB1D
0x18002f7c5  cmp     [rsp+1E8h+arg_30], sil
0x18002f7cd  jz      loc_18002F747
0x18002f7d3  mov     rax, [rsp+1E8h+var_168]
0x18002f7db  movsxd  rcx, dword ptr [rax+18h]
0x18002f7df  add     dword ptr [rsp+rcx*4+1E8h+var_A0], edx
0x18002f7e6  jmp     loc_18002F747
0x18002f7eb  mov     edx, [r9+4]
0x18002f7ef  cmp     edx, r8d
0x18002f7f2  jz      loc_18002FB50
0x18002f7f8  cmp     [rsp+1E8h+arg_30], sil
0x18002f800  jz      loc_18002F747
0x18002f806  mov     rax, [rsp+1E8h+var_168]
0x18002f80e  movsxd  rcx, dword ptr [rax+18h]
0x18002f812  add     dword ptr [rsp+rcx*4+1E8h+var_E0], edx
0x18002f819  jmp     loc_18002F747
0x18002f81e  lea     rcx, rva qword_1802CBE40[r9]
0x18002f825  jmp     loc_18002F470
0x18002f82a  mov     edx, [r9+4]
0x18002f82e  cmp     edx, r8d
0x18002f831  jz      loc_18002FAC6
0x18002f837  cmp     [rsp+1E8h+arg_30], sil
0x18002f83f  jz      loc_18002F747
0x18002f845  mov     rax, [rsp+1E8h+var_168]
0x18002f84d  movsxd  rcx, dword ptr [rax+18h]
0x18002f851  add     dword ptr [rsp+rcx*4+1E8h+var_C0], edx
0x18002f858  jmp     loc_18002F747
0x18002f85d  test    r8d, r8d
0x18002f860  cmovs   r14d, edx
0x18002f864  mov     [rsp+1E8h+var_178], r14d
0x18002f869  jmp     loc_18002F42F
0x18002f86e  mov     r9d, esi
0x18002f871  mov     rcx, rsi
0x18002f874  mov     rax, [rsp+1E8h+var_78]
0x18002f87c  test    rax, rax
0x18002f87f  jz      short loc_18002F894
0x18002f881  mov     rcx, rax
0x18002f884  cmp     [rax+8], rsi
0x18002f888  jz      short loc_18002F894
0x18002f88a  mov     rcx, [rcx+8]
0x18002f88e  cmp     [rcx+8], rsi
0x18002f892  jnz     short loc_18002F88A
0x18002f894  test    rcx, rcx
0x18002f897  jnz     loc_18002FB83
0x18002f89d  mov     rax, [rsp+1E8h+var_168]
0x18002f8a5  movsxd  r8, dword ptr [rax+18h]
0x18002f8a9  add     dword ptr [rsp+r8*4+1E8h+var_E0], r9d
0x18002f8b1  mov     r9d, esi
0x18002f8b4  mov     rcx, rsi
0x18002f8b7  mov     rax, [rsp+1E8h+var_68]
0x18002f8bf  test    rax, rax
0x18002f8c2  jz      short loc_18002F8D7
0x18002f8c4  mov     rcx, rax
0x18002f8c7  cmp     [rax+8], rsi
0x18002f8cb  jz      short loc_18002F8D7
0x18002f8cd  mov     rcx, [rcx+8]
0x18002f8d1  cmp     [rcx+8], rsi
0x18002f8d5  jnz     short loc_18002F8CD
0x18002f8d7  test    rcx, rcx
0x18002f8da  jnz     loc_18002FBA3
0x18002f8e0  add     dword ptr [rsp+r8*4+1E8h+var_A0], r9d
0x18002f8e8  mov     r9d, esi
0x18002f8eb  mov     rcx, rsi
0x18002f8ee  mov     rax, [rsp+1E8h+var_58]
0x18002f8f6  test    rax, rax
0x18002f8f9  jz      short loc_18002F90E
0x18002f8fb  mov     rcx, rax
0x18002f8fe  cmp     [rax+8], rsi
0x18002f902  jz      short loc_18002F90E
0x18002f904  mov     rcx, [rcx+8]
0x18002f908  cmp     [rcx+8], rsi
0x18002f90c  jnz     short loc_18002F904
0x18002f90e  test    rcx, rcx
0x18002f911  jnz     loc_18002FBC3
0x18002f917  add     dword ptr [rsp+r8*4+1E8h+var_100], r9d
0x18002f91f  mov     r9d, esi
  ... truncated ...
```
