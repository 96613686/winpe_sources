# CCreateGeometryShaderWithStreamOutputValidator::ValidateDecl(void)

- ea: `0x18014d66c`
- end: `0x18014dfc1`
- name: `?ValidateDecl@CCreateGeometryShaderWithStreamOutputValidator@@IEAAXXZ`
- size: `2389`
- prototype: `void __fastcall(CCreateGeometryShaderWithStreamOutputValidator *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18014d63c`

## callees

- `0x18002ef50`
- `0x18004db04`
- `0x1800bb480`
- `0x1800bc094`
- `0x18014d66c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18014dd0e`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18014dd0e`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x18014dc37`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x18014dc37`

## string_xrefs

- `0x18014dd72`: `Stream Output Declaration Element[%d] and Element[%d] have the same Semantic (%s %d), which is fine, except the components declared cannot overlap.  Element[%d] has StartComponent %d and ComponentCount %d, while Element[%d] has StartComponent %d and ComponentCount %d.`
- `0x18014dbc1`: `Stream Output Declaration Element[%d]:  For declaration entries that are not gaps, StartComponent must be <= %d, and the sum of StartComponent and ComponentCount must be <= %d. StartComponent of %d and ComponentCount of %d were specified.`
- `0x18014db4a`: `Stream Output Declaration Element[%d]:  ComponentCount must be in the range [1..%d] (except for gap entries).  %d was specified. `
- `0x18014db05`: `Stream Output Declaration Element[%d]:  When SemanticName is NULL, signifying a gap in stream output, SemanticIndex (%d specified) and StartComponent (%d specified) must both be 0.`
- `0x18014df1e`: `pBufferStride[%d] must be a multiple of 4, must be >= the total declared structure size for all Elements (sum of ComponentCount for all Elements * 4 bytes per component), and must be <= %d bytes.  The declaration provided has a total structure size of %d, and pBufferStride[%d] is set to %d.`
- `0x18014de6f`: `The total of ComponentCount values for all entries of buffer %u in the declaration summed must be <= %d. The specified declaration has an overall ComponentCount sum of %d.`

## pseudocode

```c
void __fastcall CCreateGeometryShaderWithStreamOutputValidator::ValidateDecl(
        CCreateGeometryShaderWithStreamOutputValidator *this)
{
  __int64 *v1; // r13
  const char *v3; // r8
  __int64 v4; // rdx
  unsigned int v5; // r12d
  __int64 v6; // rax
  __int64 i; // r15
  unsigned int v8; // edx
  __int64 v9; // rcx
  const char *v10; // r8
  __int64 v11; // r9
  __int64 j; // r8
  __int64 v13; // r9
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // r12
  unsigned int v17; // r9d
  unsigned int v18; // r8d
  __int64 v19; // rdx
  __int64 v20; // rax
  unsigned int v21; // eax
  unsigned int v22; // r12d
  int v23; // ecx
  __int64 m; // rax
  __int64 v25; // r15
  int v26; // r8d
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rcx
  bool v30; // zf
  __int64 v31; // rax
  __int64 v32; // rax
  unsigned __int8 v33; // cl
  __int64 v34; // r8
  __int64 v35; // rdx
  int v36; // ecx
  int v37; // r9d
  __int64 v38; // rcx
  __int64 v39; // rdx
  char *v40; // rax
  int v41; // ecx
  char *v42; // rdx
  __int64 v43; // rax
  unsigned int v44; // r11d
  __int64 v45; // rcx
  int v46; // r10d
  __int64 v47; // r9
  unsigned __int8 v48; // al
  __int64 v49; // rcx
  char v50; // al
  __int64 v51; // rcx
  __int64 v52; // rdx
  __int64 v53; // rax
  __int64 v54; // r8
  __int64 v55; // r9
  __int64 n; // rdx
  _DWORD *v57; // r9
  __int64 k; // rdx
  int v59; // eax
  __int64 v60; // r15
  unsigned int v61; // r13d
  unsigned int v62; // ecx
  __int64 v63; // rax
  __int64 v64; // r8
  int v65; // eax
  __int64 v66; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v67; // [rsp+70h] [rbp-90h]
  char v68; // [rsp+71h] [rbp-8Fh]
  unsigned int v69; // [rsp+74h] [rbp-8Ch]
  unsigned int v70; // [rsp+78h] [rbp-88h]
  unsigned __int8 v71; // [rsp+7Ch] [rbp-84h]
  int v72; // [rsp+80h] [rbp-80h]
  unsigned int v73; // [rsp+84h] [rbp-7Ch]
  int v74; // [rsp+88h] [rbp-78h]
  int v75; // [rsp+8Ch] [rbp-74h]
  unsigned int v76; // [rsp+90h] [rbp-70h]
  int v77; // [rsp+94h] [rbp-6Ch]
  unsigned int v78; // [rsp+98h] [rbp-68h]
  __int64 v79; // [rsp+A0h] [rbp-60h]
  __int64 v80; // [rsp+A8h] [rbp-58h]
  __int64 v81; // [rsp+B0h] [rbp-50h]
  _BYTE v82[256]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v83; // [rsp+1C0h] [rbp+C0h]
  __int128 v84; // [rsp+1D0h] [rbp+D0h]
  _DWORD v85[128]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v86[128]; // [rsp+3E0h] [rbp+2E0h] BYREF

  v1 = (__int64 *)((char *)this + 88);
  if ( !*((_DWORD *)this + 24) && *v1 )
  {
    v3 = "When NumEntries equals 0, pDeclEntries must be NULL.";
    v4 = 285;
LABEL_4:
    ++*((_DWORD *)this + 8);
    goto LABEL_129;
  }
  v5 = *((_DWORD *)this + 28);
  v6 = *((_QWORD *)this + 13);
  v79 = v6;
  v78 = v5;
  if ( v5 )
  {
    if ( !v6 )
    {
      v3 = "When pBufferStrides is NULL, NumStrides must be 0.";
      goto LABEL_8;
    }
  }
  else if ( v6 )
  {
    v3 = "When NumStrides equals 0, pBufferStrides must be NULL.";
LABEL_8:
    v4 = 286;
    goto LABEL_4;
  }
  if ( *((int *)this + 9) < 45056 )
  {
    if ( v5 > 1 )
    {
      ++*((_DWORD *)this + 8);
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        287,
        "NumStrides (=%u) must be less than or equal to 1, unless GetFeatureLevel returns D3D_FEATURE_LEVEL_11_0 or greater.",
        v5);
      return;
    }
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      v8 = *((_DWORD *)this + 24);
      if ( (unsigned int)i >= v8 )
        goto LABEL_33;
      v9 = *((_QWORD *)this + 11);
      if ( *(_DWORD *)(v9 + 24 * i) )
        break;
      if ( v8 > 4 )
      {
        if ( *(_BYTE *)(v9 + 24 * i + 22) )
        {
          ++*((_DWORD *)this + 8);
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            79,
            "When NumEntries is greater than %d, OutputSlot must be 0 for all entries in the declaration.  The provided N"
            "umEntries is %d, while Element[%d] has an OutputSlot of %d.",
            4,
            v8,
            i,
            *(unsigned __int8 *)(v9 + 24 * i + 22));
        }
      }
    }
    ++*((_DWORD *)this + 8);
    v10 = "Element[%d].Stream (=%u) must be 0, unless GetFeatureLevel returns D3D_FEATURE_LEVEL_11_0 or greater.";
    v11 = (unsigned int)i;
    LODWORD(v66) = *(_DWORD *)(v9 + 24 * i);
LABEL_22:
    TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 284, v10, v11, v66);
    return;
  }
  for ( j = 0; (unsigned int)j < *((_DWORD *)this + 24); j = (unsigned int)(j + 1) )
  {
    v13 = 24 * j;
    if ( (_DWORD)j && *(_DWORD *)(v13 + *v1) < *(_DWORD *)(*v1 + 24LL * (unsigned int)(j - 1)) )
    {
      v3 = "Stream out declaration entries must be in non-decreasing order by stream.";
      v4 = 284;
      goto LABEL_128;
    }
    v14 = *v1;
    if ( *(_DWORD *)(*v1 + 24 * j) >= 4u )
    {
      ++*((_DWORD *)this + 8);
      v10 = "Stream (=%u) must be less than or equal to %u.";
      v11 = *(unsigned int *)(v14 + v13);
      LODWORD(v66) = 3;
      goto LABEL_22;
    }
  }
  if ( v5 > 4 )
  {
    ++*((_DWORD *)this + 8);
    TDebugOutputFunctor::operator()(
      &g_coreRuntimeTallyErrorOutputFunctor,
      287,
      "NumStrides (=%u) must be less than or equal to %u.",
      v5,
      4);
    return;
  }
LABEL_33:
  v15 = *((_DWORD *)this + 9);
  if ( v15 == 45056 || v15 == 45312 || v15 == 49152 || v15 == 49408 || (v73 = 64, v15 == 49664) )
    v73 = 128;
  v16 = 0;
  v71 = 0;
  v17 = 0;
  v74 = 0;
  v70 = 0;
  v72 = 252645135;
  v83 = 0;
  v84 = 0;
  do
  {
    if ( (unsigned int)v16 >= *((_DWORD *)this + 24) )
      break;
    if ( *(_DWORD *)(*v1 + 24 * v16) > v17 )
      goto LABEL_52;
    v68 = 0;
    memset_0(v85, 0, sizeof(v85));
    memset_0(v86, 0, sizeof(v86));
    memset_0(v82, 0, sizeof(v82));
    v17 = v70;
    v18 = 0;
    v69 = 0;
    do
    {
      v19 = *v1;
      if ( *(_DWORD *)(*v1 + 24 * v16) > v17 )
        break;
      if ( v18 < v73 )
      {
        v20 = *(unsigned __int8 *)(v19 + 24 * v16 + 22);
        if ( (unsigned __int8)v20 >= 4u )
        {
          ++*((_DWORD *)this + 8);
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            80,
            "Stream Output Declaration Element[%d]:  OutputSlot out of range (set to %d).  OutputSlot must be in the range [0...%d].",
            v16,
            *(unsigned __int8 *)(v19 + 24 * v16 + 22),
            3);
          goto LABEL_47;
        }
        ++v85[v20 - 4];
        v26 = v71 | (1 << v20);
        v27 = *((unsigned __int8 *)&v72 + v20);
        v71 = v26;
        if ( (_BYTE)v27 != 15 && v27 != v17 )
        {
          ++*((_DWORD *)this + 8);
          v28 = *(unsigned __int8 *)(v19 + 24 * v16 + 22);
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            80,
            "Stream Output Declaration Element[%d]:  OutputSlot %d was previously declared for output in stream %d.",
            v16,
            v28,
            *((unsigned __int8 *)&v72 + v28));
          LOBYTE(v17) = v70;
        }
        v29 = *v1;
        v30 = *(_QWORD *)(*v1 + 24 * v16 + 8) == 0;
        *((_BYTE *)&v72 + *(unsigned __int8 *)(*v1 + 24 * v16 + 22)) = v17;
        if ( v30 )
        {
          v31 = v29 + 24 * v16;
          if ( *(_DWORD *)(v31 + 16) || *(_BYTE *)(v31 + 20) )
          {
            ++*((_DWORD *)this + 8);
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              84,
              "Stream Output Declaration Element[%d]:  When SemanticName is NULL, signifying a gap in stream output, Sema"
              "nticIndex (%d specified) and StartComponent (%d specified) must both be 0.",
              v16,
              *(_DWORD *)(v29 + 24 * v16 + 16),
              *(unsigned __int8 *)(v31 + 20));
          }
        }
        v32 = *v1;
        v33 = *(_BYTE *)(*v1 + 24 * v16 + 21);
        if ( !v33 || v33 > 4u && *(_QWORD *)(v32 + 24 * v16 + 8) )
        {
          ++*((_DWORD *)this + 8);
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            82,
            "Stream Output Declaration Element[%d]:  ComponentCount must be in the range [1..%d] (except for gap entries)"
            ".  %d was specified. ",
            v16,
            4,
            *(unsigned __int8 *)(v32 + 24 * v16 + 21));
        }
        v34 = *v1;
        if ( *(_QWORD *)(*v1 + 24 * v16 + 8) )
        {
          v35 = v34 + 24 * v16;
          if ( *(_BYTE *)(v35 + 20) < 4u )
          {
            v36 = *(unsigned __int8 *)(v35 + 21);
            v37 = *(unsigned __int8 *)(v34 + 24 * v16 + 20);
            if ( (unsigned int)(v36 + v37) <= 4 )
            {
              v18 = v69;
              v86[v69] = ((1 << v36) - 1) << v37;
              goto LABEL_84;
            }
          }
          ++*((_DWORD *)this + 8);
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            83,
            "Stream Output Declaration Element[%d]:  For declaration entries that are not gaps, StartComponent must be <="
            " %d, and the sum of StartComponent and ComponentCount must be <= %d. StartComponent of %d and ComponentCount"
            " of %d were specified.",
            v16,
            3,
            4,
            *(unsigned __int8 *)(v34 + 24 * v16 + 20),
            *(unsigned __int8 *)(v35 + 21));
        }
        v18 = v69;
LABEL_84:
        v38 = *v1;
        v39 = *(unsigned __int8 *)(*v1 + 24 * v16 + 22);
        *((_DWORD *)&v83 + v39) += *(unsigned __int8 *)(*v1 + 24 * v16 + 21);
        v40 = *(char **)(v38 + 24 * v16 + 8);
        if ( v40 )
        {
          v41 = 0;
          *((_BYTE *)&v74 + v39) = 1;
          if ( *v40 )
          {
            do
            {
              v42 = v40;
              ++v41;
              ++v40;
            }
            while ( *v40 );
            if ( v41 && (unsigned int)_o_isdigit((unsigned int)*v42) )
            {
              v43 = *v1;
              ++*((_DWORD *)this + 8);
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                240,
                "Stream Output Declaration Element[%d]: SemanticName string (\"%s\") cannot end with a number. Instead, u"
                "se the number in the SemanticIndex field. For example, suppose a float4x4 in HLSL is given the semantic "
                "\"foo13\". To match that name via declaration element, the SemanticName field would have to be \"foo\", "
                "and SemanticIndex for the declarations of each of the 4 rows of the float4x4 would have to be 13, 14, 15, and 16.",
                v16,
                *(const char **)(v43 + 24 * v16 + 8));
            }
          }
          if ( v68 )
          {
LABEL_47:
            v18 = v69;
          }
          else
          {
            v44 = LowerCaseCharSum(*(const char **)(*v1 + 24 * v16 + 8));
            v45 = *v1;
            v76 = v44;
            v46 = v16 - v69;
            v47 = v69;
            v80 = v69;
            v85[v69] = v44;
            v48 = v44 + *(_BYTE *)(v45 + 24 * v16 + 16);
            v75 = v16 - v69;
            while ( 1 )
            {
              v49 = v48;
              v67 = v48;
              v50 = v82[v48];
              if ( v50 >= 0 )
                break;
              v51 = *v1;
              v52 = v50 & 0x7F;
              v53 = (unsigned int)(v52 + v46);
              v54 = 3 * v53;
              v77 = v52 + v46;
              LODWORD(v53) = *(_DWORD *)(v51 + 24 * v53 + 16);
              v81 = v54;
              if ( *(_DWORD *)(v51 + 24 * v16 + 16) == (_DWORD)v53 && v44 == v85[v52] && (v86[v52] & v86[v47]) != 0 )
              {
                if ( !(unsigned int)_o__stricmp(*(_QWORD *)(v51 + 24 * v16 + 8), *(_QWORD *)(v51 + 8 * v54 + 8)) )
                {
                  v55 = *v1;
                  ++*((_DWORD *)this + 8);
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    85,
                    "Stream Output Declaration Element[%d] and Element[%d] have the same Semantic (%s %d), which is fine,"
                    " except the components declared cannot overlap.  Element[%d] has StartComponent %d and ComponentCoun"
                    "t %d, while Element[%d] has StartComponent %d and ComponentCount %d.",
                    v16,
                    v77,
                    *(const char **)(v55 + 24 * v16 + 8),
                    *(_DWORD *)(v55 + 24 * v16 + 16),
                    v16,
                    *(unsigned __int8 *)(v55 + 24 * v16 + 20),
                    *(unsigned __int8 *)(v55 + 24 * v16 + 21),
                    v77,
                    *(unsigned __int8 *)(v55 + 8 * v81 + 20),
                    *(unsigned __int8 *)(v55 + 8 * v81 + 21));
                  v68 = 1;
                  goto LABEL_47;
                }
                v47 = v80;
                v46 = v75;
                v44 = v76;
              }
              v48 = v67 + 1;
            }
            v18 = v69;
            v82[v49] = v69 | 0x80;
          }
        }
        v17 = v70;
      }
      ++v18;
      v16 = (unsigned int)(v16 + 1);
      v69 = v18;
    }
    while ( (unsigned int)v16 < *((_DWORD *)this + 24) );
    v21 = v73;
    if ( v18 > v73 )
    {
      ++*((_DWORD *)this + 8);
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        75,
        "The number of entries in a stream cannot be greater than %d (%d specified).",
        v21,
        v18);
      v17 = v70;
    }
LABEL_52:
    v70 = ++v17;
  }
  while ( v17 < 4 );
  v22 = v78;
  if ( v78 && (1 << v78) - 1 < v71 )
  {
    ++*((_DWORD *)this + 8);
    TDebugOutputFunctor::operator()(
      &g_coreRuntimeTallyErrorOutputFunctor,
      287,
      "If NumStrides (=%u) is greater than 0, a stride must be declared for all used buffer slots.",
      v22);
  }
  if ( *((int *)this + 9) >= 45056 )
  {
    if ( !v22 )
    {
      for ( k = 0; k != 4; ++k )
        *(_DWORD *)(*((_QWORD *)this + 15) + 4 * k) = 4 * *((_DWORD *)&v83 + k);
      v22 = 4;
      v79 = *((_QWORD *)this + 15);
      **((_DWORD **)this + 16) = 4;
    }
  }
  else
  {
    v23 = 0;
    for ( m = 1; m != 4; ++m )
      v23 += v85[m - 4];
    if ( v23 )
    {
      v25 = 0;
      do
      {
        if ( v85[v25 - 4] > 1u )
        {
          ++*((_DWORD *)this + 8);
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            81,
            "When the stream out declaration includes any slot other than zero, only one element can be defined per Outpu"
            "t Slot (including slot zero).  Multiple elements per OutputSlot are only permitted if all elements go to Out"
            "putSlot 0.  OutputSlot[%d] has been declared by multiple elements.",
            v25);
        }
        v25 = (unsigned int)(v25 + 1);
      }
      while ( (unsigned int)v25 < 4 );
    }
    if ( v22 )
    {
      if ( v71 != 1 )
      {
        v57 = (_DWORD *)*((_QWORD *)this + 13);
        ++*((_DWORD *)this + 8);
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          76,
          "If any OutputSlot other than 0 is declared, or NumEntries is 0, then OutputStreamStride must be 0 (%d specified).",
          *v57);
      }
    }
    else
    {
      if ( v71 == 1 )
      {
        v22 = 1;
        **((_DWORD **)this + 15) = 4 * v83;
        **((_DWORD **)this + 16) = 1;
      }
      else
      {
        for ( n = 0; n != 4; ++n )
          *(_DWORD *)(*((_QWORD *)this + 15) + 4 * n) = 4 * *((_DWORD *)&v83 + n);
        v22 = 4;
        **((_DWORD **)this + 16) = 4;
      }
      v79 = *((_QWORD *)this + 15);
    }
  }
  v59 = v71;
  v60 = 0;
  do
  {
    if ( _bittest(&v59, v60) )
    {
      v61 = *((_DWORD *)&v83 + v60);
      v62 = v73;
      v63 = (unsigned int)v60;
      if ( v61 > v73 )
      {
        ++*((_DWORD *)this + 8);
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          90,
          "The total of ComponentCount values for all entries of buffer %u in the declaration summed must be <= %d. The s"
          "pecified declaration has an overall ComponentCount sum of %d.",
          v60,
          v62,
          v61);
        v63 = (unsigned int)v60;
      }
      if ( !*((_BYTE *)&v74 + v63) )
      {
        ++*((_DWORD *)this + 8);
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          89,
          "It is invalid to define stream output with nothing but gap entries. ");
      }
      if ( v22 > (unsigned int)v60 )
      {
        v64 = v79;
        if ( (*(_BYTE *)(v79 + 4 * v60) & 3) != 0
          || *(_DWORD *)(v79 + 4 * v60) < 4 * v61
          || *(_DWORD *)(v79 + 4 * v60) > 0x800u )
        {
          ++*((_DWORD *)this + 8);
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            86,
            "pBufferStride[%d] must be a multiple of 4, must be >= the total declared structure size for all Elements (su"
            "m of ComponentCount for all Elements * 4 bytes per component), and must be <= %d bytes.  The declaration pro"
            "vided has a total structure size of %d, and pBufferStride[%d] is set to %d.",
            v60,
            2048,
            4 * v61,
            v60,
            *(_DWORD *)(v64 + 4 * v60));
        }
      }
      else
      {
        ++*((_DWORD *)this + 8);
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          287,
          "No output stride was given for buffer %d, but an entry is outputting to that buffer.",
          v60);
      }
      v59 = v71;
    }
    v60 = (unsigned int)(v60 + 1);
  }
  while ( (unsigned int)v60 < 4 );
  v65 = *((_DWORD *)this + 29);
  if ( *((int *)this + 9) >= 45056 )
  {
    if ( (unsigned int)(v65 - 4) <= 0xFFFFFFFA )
    {
      ++*((_DWORD *)this + 8);
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        280,
        "RasterizedStream must be less then %d.",
        4);
    }
  }
  else if ( v65 )
  {
    v3 = "RasterizedStream must be 0, unless GetFeatureLevel returns D3D_FEATURE_LEVEL_11_0 or greater.";
    v4 = 280;
LABEL_128:
    ++*((_DWORD *)this + 8);
LABEL_129:
    TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, v4, v3);
  }
}

```

## disassembly

```asm
0x18014d66c  push    rbp
0x18014d66e  push    rbx
0x18014d66f  push    rsi
0x18014d670  push    rdi
0x18014d671  push    r12
0x18014d673  push    r13
0x18014d675  push    r14
0x18014d677  push    r15
0x18014d679  lea     rbp, [rsp-378h]
0x18014d681  sub     rsp, 478h
0x18014d688  mov     rax, cs:__security_cookie
0x18014d68f  xor     rax, rsp
0x18014d692  mov     [rbp+3B0h+var_50], rax
0x18014d699  cmp     dword ptr [rcx+60h], 0
0x18014d69d  lea     r13, [rcx+58h]
0x18014d6a1  mov     rbx, rcx
0x18014d6a4  jnz     short loc_18014D6CD
0x18014d6a6  cmp     qword ptr [r13+0], 0
0x18014d6ab  jz      short loc_18014D6CD
0x18014d6ad  lea     r8, aWhenNumentries; "When NumEntries equals 0, pDeclEntries "...
0x18014d6b4  mov     edx, 11Dh
0x18014d6b9  mov     edi, 1
0x18014d6be  add     [rcx+20h], edi
0x18014d6c1  lea     rcx, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x18014d6c8  jmp     loc_18014DF75
0x18014d6cd  mov     r12d, [rcx+70h]
0x18014d6d1  mov     rax, [rcx+68h]
0x18014d6d5  mov     [rbp+3B0h+var_410], rax
0x18014d6d9  mov     [rbp+3B0h+var_418], r12d
0x18014d6dd  test    r12d, r12d
0x18014d6e0  jnz     short loc_18014D6F5
0x18014d6e2  test    rax, rax
0x18014d6e5  jz      short loc_18014D703
0x18014d6e7  lea     r8, aWhenNumstrides; "When NumStrides equals 0, pBufferStride"...
0x18014d6ee  mov     edx, 11Eh
0x18014d6f3  jmp     short loc_18014D6B9
0x18014d6f5  test    rax, rax
0x18014d6f8  jnz     short loc_18014D703
0x18014d6fa  lea     r8, aWhenPbufferstr; "When pBufferStrides is NULL, NumStrides"...
0x18014d701  jmp     short loc_18014D6EE
0x18014d703  cmp     dword ptr [rcx+24h], 0B000h
0x18014d70a  lea     rsi, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x18014d711  mov     edi, 1
0x18014d716  jge     loc_18014D7BC
0x18014d71c  cmp     r12d, edi
0x18014d71f  jbe     short loc_18014D738
0x18014d721  add     [rcx+20h], edi
0x18014d724  lea     r8, aNumstridesUMus; "NumStrides (=%u) must be less than or e"...
0x18014d72b  mov     r9d, r12d
0x18014d72e  mov     edx, 11Fh
0x18014d733  jmp     loc_18014DF96
0x18014d738  xor     r15d, r15d
0x18014d73b  lea     r14d, [r15+4]
0x18014d73f  mov     edx, [rbx+60h]
0x18014d742  cmp     r15d, edx
0x18014d745  jnb     loc_18014D848
0x18014d74b  mov     rcx, [rbx+58h]
0x18014d74f  lea     rax, [r15+r15*2]
0x18014d753  cmp     dword ptr [rcx+rax*8], 0
0x18014d757  ja      short loc_18014D796
0x18014d759  cmp     edx, r14d
0x18014d75c  jbe     short loc_18014D791
0x18014d75e  cmp     byte ptr [rcx+rax*8+16h], 0
0x18014d763  jbe     short loc_18014D791
0x18014d765  add     [rbx+20h], edi
0x18014d768  lea     r8, aWhenNumentries_0; "When NumEntries is greater than %d, Out"...
0x18014d76f  movzx   eax, byte ptr [rcx+rax*8+16h]
0x18014d774  mov     r9d, r14d
0x18014d777  mov     [rsp+4B0h+var_480], eax
0x18014d77b  mov     rcx, rsi
0x18014d77e  mov     dword ptr [rsp+4B0h+var_488], r15d
0x18014d783  mov     dword ptr [rsp+4B0h+var_490], edx
0x18014d787  mov     edx, 4Fh ; 'O'
0x18014d78c  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18014d791  add     r15d, edi
0x18014d794  jmp     short loc_18014D73F
0x18014d796  add     [rbx+20h], edi
0x18014d799  lea     r8, aElementDStream; "Element[%d].Stream (=%u) must be 0, unl"...
0x18014d7a0  mov     eax, [rcx+rax*8]
0x18014d7a3  mov     r9d, r15d
0x18014d7a6  mov     dword ptr [rsp+4B0h+var_490], eax
0x18014d7aa  mov     edx, 11Ch
0x18014d7af  mov     rcx, rsi
0x18014d7b2  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18014d7b7  jmp     loc_18014DF9E
0x18014d7bc  xor     r8d, r8d
0x18014d7bf  lea     r14d, [r8+4]
0x18014d7c3  cmp     r8d, [rbx+60h]
0x18014d7c7  jnb     short loc_18014D827
0x18014d7c9  lea     rcx, [r8+r8*2]
0x18014d7cd  lea     r9, ds:0[rcx*8]
0x18014d7d5  test    r8d, r8d
0x18014d7d8  jz      short loc_18014D7EF
0x18014d7da  mov     rdx, [r13+0]
0x18014d7de  lea     eax, [r8-1]
0x18014d7e2  lea     rax, [rax+rax*2]
0x18014d7e6  mov     ecx, [rdx+rax*8]
0x18014d7e9  cmp     [r9+rdx], ecx
0x18014d7ed  jb      short loc_18014D7FE
0x18014d7ef  mov     rax, [r13+0]
0x18014d7f3  cmp     [rax+r9], r14d
0x18014d7f7  jnb     short loc_18014D80F
0x18014d7f9  add     r8d, edi
0x18014d7fc  jmp     short loc_18014D7C3
0x18014d7fe  lea     r8, aStreamOutDecla; "Stream out declaration entries must be "...
0x18014d805  mov     edx, 11Ch
0x18014d80a  jmp     loc_18014DF6F
0x18014d80f  add     [rbx+20h], edi
0x18014d812  lea     r8, aStreamUMustBeL; "Stream (=%u) must be less than or equal"...
0x18014d819  mov     r9d, [rax+r9]
0x18014d81d  mov     dword ptr [rsp+4B0h+var_490], 3
0x18014d825  jmp     short loc_18014D7AA
0x18014d827  cmp     r12d, r14d
0x18014d82a  jbe     short loc_18014D848
0x18014d82c  add     [rbx+20h], edi
0x18014d82f  lea     r8, aNumstridesUMus_0; "NumStrides (=%u) must be less than or e"...
0x18014d836  mov     dword ptr [rsp+4B0h+var_490], r14d
0x18014d83b  mov     r9d, r12d
0x18014d83e  mov     edx, 11Fh
0x18014d843  jmp     loc_18014D7AF
0x18014d848  mov     eax, [rbx+24h]
0x18014d84b  cmp     eax, 0B000h
0x18014d850  jz      short loc_18014D875
0x18014d852  cmp     eax, 0B100h
0x18014d857  jz      short loc_18014D875
0x18014d859  cmp     eax, 0C000h
0x18014d85e  jz      short loc_18014D875
0x18014d860  cmp     eax, 0C100h
0x18014d865  jz      short loc_18014D875
0x18014d867  mov     [rbp+3B0h+var_42C], 40h ; '@'
0x18014d86e  cmp     eax, 0C200h
0x18014d873  jnz     short loc_18014D87C
0x18014d875  mov     [rbp+3B0h+var_42C], 80h
0x18014d87c  xor     r12d, r12d
0x18014d87f  mov     byte ptr [rsp+4B0h+var_434], 0
0x18014d884  xor     r9d, r9d
0x18014d887  mov     [rbp+3B0h+var_428], 0
0x18014d88e  xorps   xmm0, xmm0
0x18014d891  mov     [rsp+4B0h+var_438], r9d
0x18014d896  xorps   xmm1, xmm1
0x18014d899  mov     [rbp+3B0h+var_430], 0F0F0F0Fh
0x18014d8a0  movups  [rbp+3B0h+var_2F0], xmm0
0x18014d8a7  movups  [rbp+3B0h+var_2E0], xmm1
0x18014d8ae  cmp     r12d, [rbx+60h]
0x18014d8b2  jnb     loc_18014D9BD
0x18014d8b8  mov     rax, [r13+0]
0x18014d8bc  lea     rcx, [r12+r12*2]
0x18014d8c0  cmp     [rax+rcx*8], r9d
0x18014d8c4  ja      loc_18014D9AC
0x18014d8ca  xor     al, al
0x18014d8cc  lea     rcx, [rbp+3B0h+var_2D0]; void *
0x18014d8d3  xor     edx, edx; Val
0x18014d8d5  mov     [rsp+4B0h+var_43F], al
0x18014d8d9  mov     r8d, 200h; Size
0x18014d8df  call    memset_0
0x18014d8e4  xor     edx, edx; Val
0x18014d8e6  lea     rcx, [rbp+3B0h+var_D0]; void *
0x18014d8ed  mov     r8d, 80h; Size
0x18014d8f3  call    memset_0
0x18014d8f8  xor     edx, edx; Val
0x18014d8fa  lea     rcx, [rbp+3B0h+var_3F0]; void *
0x18014d8fe  mov     r8d, 100h; Size
0x18014d904  call    memset_0
0x18014d909  mov     r9d, [rsp+4B0h+var_438]
0x18014d90e  xor     r8d, r8d
0x18014d911  mov     [rsp+4B0h+var_43C], r8d
0x18014d916  mov     rdx, [r13+0]
0x18014d91a  lea     r15, [r12+r12*2]
0x18014d91e  cmp     [rdx+r15*8], r9d
0x18014d922  ja      short loc_18014D980
0x18014d924  cmp     r8d, [rbp+3B0h+var_42C]
0x18014d928  jnb     short loc_18014D96F
0x18014d92a  movzx   eax, byte ptr [rdx+r15*8+16h]
0x18014d930  cmp     al, r14b
0x18014d933  jb      loc_18014DA80
0x18014d939  add     [rbx+20h], edi
0x18014d93c  lea     r8, aStreamOutputDe_8; "Stream Output Declaration Element[%d]: "...
0x18014d943  movzx   eax, byte ptr [rdx+r15*8+16h]
0x18014d949  mov     r9d, r12d
0x18014d94c  mov     edx, 50h ; 'P'
0x18014d951  mov     dword ptr [rsp+4B0h+var_488], 3
0x18014d959  mov     rcx, rsi
0x18014d95c  mov     dword ptr [rsp+4B0h+var_490], eax
0x18014d960  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18014d965  mov     r8d, [rsp+4B0h+var_43C]
0x18014d96a  mov     r9d, [rsp+4B0h+var_438]
0x18014d96f  add     r8d, edi
0x18014d972  add     r12d, edi
0x18014d975  mov     [rsp+4B0h+var_43C], r8d
0x18014d97a  cmp     r12d, [rbx+60h]
0x18014d97e  jb      short loc_18014D916
0x18014d980  mov     eax, [rbp+3B0h+var_42C]
0x18014d983  cmp     r8d, eax
0x18014d986  jbe     short loc_18014D9AC
0x18014d988  add     [rbx+20h], edi
0x18014d98b  mov     r9d, eax
0x18014d98e  mov     dword ptr [rsp+4B0h+var_490], r8d
0x18014d993  mov     edx, 4Bh ; 'K'
0x18014d998  lea     r8, aTheNumberOfEnt; "The number of entries in a stream canno"...
0x18014d99f  mov     rcx, rsi
0x18014d9a2  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18014d9a7  mov     r9d, [rsp+4B0h+var_438]
0x18014d9ac  add     r9d, edi
0x18014d9af  mov     [rsp+4B0h+var_438], r9d
0x18014d9b4  cmp     r9d, r14d
0x18014d9b7  jb      loc_18014D8AE
0x18014d9bd  mov     r12d, [rbp+3B0h+var_418]
0x18014d9c1  mov     r13d, [rsp+4B0h+var_434]
0x18014d9c6  test    r12d, r12d
0x18014d9c9  jz      short loc_18014D9F6
0x18014d9cb  mov     ecx, r12d
0x18014d9ce  movzx   eax, r13b
0x18014d9d2  mov     edx, edi
0x18014d9d4  shl     edx, cl
0x18014d9d6  sub     edx, edi
0x18014d9d8  cmp     edx, eax
0x18014d9da  jge     short loc_18014D9F6
0x18014d9dc  add     [rbx+20h], edi
0x18014d9df  lea     r8, aIfNumstridesUI; "If NumStrides (=%u) is greater than 0, "...
0x18014d9e6  mov     r9d, r12d
0x18014d9e9  mov     edx, 11Fh
0x18014d9ee  mov     rcx, rsi
0x18014d9f1  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18014d9f6  cmp     dword ptr [rbx+24h], 0B000h
0x18014d9fd  jge     loc_18014DE0F
0x18014da03  xor     ecx, ecx
0x18014da05  mov     rax, rdi
0x18014da08  add     ecx, dword ptr [rbp+rax*4+3B0h+var_2E0]
0x18014da0f  add     rax, rdi
0x18014da12  cmp     rax, r14
0x18014da15  jnz     short loc_18014DA08
0x18014da17  test    ecx, ecx
0x18014da19  jz      short loc_18014DA4A
0x18014da1b  xor     r15d, r15d
0x18014da1e  cmp     dword ptr [rbp+r15*4+3B0h+var_2E0], edi
0x18014da26  jbe     short loc_18014DA42
0x18014da28  add     [rbx+20h], edi
0x18014da2b  lea     r8, aWhenTheStreamO; "When the stream out declaration include"...
0x18014da32  mov     r9d, r15d
0x18014da35  mov     edx, 51h ; 'Q'
0x18014da3a  mov     rcx, rsi
0x18014da3d  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18014da42  add     r15d, edi
0x18014da45  cmp     r15d, r14d
0x18014da48  jb      short loc_18014DA1E
0x18014da4a  test    r12d, r12d
0x18014da4d  jnz     loc_18014DDEA
0x18014da53  cmp     r13b, dil
0x18014da56  jnz     loc_18014DDB8
0x18014da5c  mov     eax, dword ptr [rbp+3B0h+var_2F0]
0x18014da62  mov     r12d, edi
0x18014da65  lea     ecx, ds:0[rax*4]
0x18014da6c  mov     rax, [rbx+78h]
0x18014da70  mov     [rax], ecx
0x18014da72  mov     rax, [rbx+80h]
0x18014da79  mov     [rax], edi
0x18014da7b  jmp     loc_18014DDE0
0x18014da80  mov     r8d, [rsp+4B0h+var_434]
0x18014da85  add     dword ptr [rbp+rax*4+3B0h+var_2E0], edi
0x18014da8c  movzx   r8d, r8b
0x18014da90  bts     r8d, eax
0x18014da94  movzx   eax, byte ptr [rbp+rax+3B0h+var_430]
0x18014da99  mov     [rsp+4B0h+var_434], r8d
0x18014da9e  cmp     al, 0Fh
0x18014daa0  jz      short loc_18014DAD9
0x18014daa2  cmp     eax, r9d
0x18014daa5  jz      short loc_18014DAD9
0x18014daa7  add     [rbx+20h], edi
0x18014daaa  lea     r8, aStreamOutputDe_3; "Stream Output Declaration Element[%d]: "...
0x18014dab1  movzx   ecx, byte ptr [rdx+r15*8+16h]
0x18014dab7  mov     r9d, r12d
0x18014daba  mov     edx, 50h ; 'P'
0x18014dabf  movzx   eax, byte ptr [rbp+rcx+3B0h+var_430]
0x18014dac4  mov     dword ptr [rsp+4B0h+var_488], eax
0x18014dac8  mov     dword ptr [rsp+4B0h+var_490], ecx
0x18014dacc  mov     rcx, rsi
0x18014dacf  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18014dad4  mov     r9d, [rsp+4B0h+var_438]
0x18014dad9  mov     rcx, [r13+0]
0x18014dadd  cmp     qword ptr [rcx+r15*8+8], 0
0x18014dae3  movzx   eax, byte ptr [rcx+r15*8+16h]
0x18014dae9  mov     byte ptr [rbp+rax+3B0h+var_430], r9b
0x18014daee  jnz     short loc_18014DB2D
0x18014daf0  cmp     dword ptr [rcx+r15*8+10h], 0
0x18014daf6  lea     rax, [rcx+r15*8]
0x18014dafa  jnz     short loc_18014DB02
0x18014dafc  cmp     byte ptr [rax+14h], 0
0x18014db00  jz      short loc_18014DB2D
0x18014db02  add     [rbx+20h], edi
0x18014db05  lea     r8, aStreamOutputDe_6; "Stream Output Declaration Element[%d]: "...
0x18014db0c  movzx   eax, byte ptr [rax+14h]
0x18014db10  mov     r9d, r12d
0x18014db13  mov     dword ptr [rsp+4B0h+var_488], eax
0x18014db17  mov     edx, 54h ; 'T'
0x18014db1c  mov     eax, [rcx+r15*8+10h]
0x18014db21  mov     rcx, rsi
0x18014db24  mov     dword ptr [rsp+4B0h+var_490], eax
0x18014db28  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18014db2d  mov     rax, [r13+0]
0x18014db31  mov     cl, [rax+r15*8+15h]
  ... truncated ...
```
