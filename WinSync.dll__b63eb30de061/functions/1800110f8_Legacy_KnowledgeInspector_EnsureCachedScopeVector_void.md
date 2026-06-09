# Legacy::KnowledgeInspector::EnsureCachedScopeVector(void)

- ea: `0x1800110f8`
- end: `0x180011ba0`
- name: `?EnsureCachedScopeVector@KnowledgeInspector@Legacy@@AEAAJXZ`
- size: `2728`
- prototype: `__int64 __fastcall(Legacy::KnowledgeInspector *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180003830`
- `0x18008ef2c`

## callees

- `0x180007584`
- `0x18000a0f0`
- `0x18000c3e4`
- `0x18000c958`
- `0x18000f810`
- `0x18000f940`
- `0x1800110f8`
- `0x180011f60`
- `0x1800164e4`
- `0x180019d94`
- `0x18001a038`
- `0x18001ae20`
- `0x18001dea0`
- `0x180093232`
- `0x180094010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800112b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800112b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800112d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001136d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800112d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001136d`

## string_xrefs

- `0x18001189a`: `Legacy::KnowledgeInspector::EnsureCachedScopeVector`
- `0x180011ad7`: `Legacy::KnowledgeInspector::EnsureCachedScopeVector`

## pseudocode

```c
__int64 __fastcall Legacy::KnowledgeInspector::EnsureCachedScopeVector(Legacy::KnowledgeInspector *this)
{
  Legacy::KnowledgeInspector *v1; // rsi
  unsigned int v2; // edi
  __int64 v3; // rcx
  __int64 v4; // r14
  RangeSet *v5; // rax
  __int64 v6; // r12
  unsigned int v7; // ebx
  int v8; // r15d
  __int64 v9; // rcx
  __int64 *v10; // r10
  __int64 v11; // r15
  __int64 v12; // rax
  void *v13; // r8
  __int64 v14; // rcx
  int *v15; // r13
  unsigned int v16; // r11d
  int v17; // r9d
  unsigned __int16 i; // r8
  unsigned __int16 *v19; // rdx
  unsigned __int16 *v20; // rcx
  int v21; // r10d
  unsigned int v22; // ecx
  unsigned __int16 v23; // si
  unsigned __int16 *v24; // rbx
  char *v25; // rdx
  unsigned __int16 *v26; // r15
  unsigned __int16 *v27; // rcx
  bool v28; // zf
  unsigned int v29; // r11d
  char *v30; // rsi
  unsigned __int8 *v31; // rcx
  int v32; // r9d
  unsigned __int8 *v33; // rdx
  char *v34; // r8
  __int64 v35; // rax
  char *v37; // rax
  int v38; // ebx
  void *v39; // rcx
  unsigned __int8 v40; // al
  unsigned __int8 v41; // al
  unsigned __int8 v42; // al
  int v43; // eax
  unsigned __int16 *v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // rsi
  __int64 v47; // r14
  __int64 v48; // rbx
  char *v49; // rdx
  __int64 v50; // rsi
  unsigned int v51; // eax
  unsigned int v52; // edx
  unsigned int v53; // r8d
  __int64 v54; // r11
  __int64 v55; // r9
  __int64 v56; // r10
  unsigned int v57; // eax
  unsigned __int64 v58; // rax
  ClockVector *v59; // rax
  ClockVector *v60; // rax
  ClockVector *v61; // rax
  unsigned int v62; // eax
  unsigned __int16 *v63; // rax
  char *v64; // r10
  unsigned __int16 v65; // r8
  __int64 v66; // r9
  char *v67; // r8
  unsigned __int8 *v68; // r9
  unsigned __int8 *v69; // rdx
  unsigned __int16 *v70; // r8
  unsigned __int16 *v71; // rsi
  char *v72; // rdx
  unsigned __int16 *v73; // rax
  __int64 v74; // rcx
  RangeSet *v75; // [rsp+30h] [rbp-59h] BYREF
  _BYTE v76[4]; // [rsp+38h] [rbp-51h] BYREF
  int v77; // [rsp+3Ch] [rbp-4Dh]
  void *v78; // [rsp+40h] [rbp-49h]
  ClockVector *v79; // [rsp+48h] [rbp-41h] BYREF
  __int64 v80; // [rsp+50h] [rbp-39h]
  LPVOID lpMem; // [rsp+58h] [rbp-31h]
  unsigned int v82; // [rsp+60h] [rbp-29h]
  __int64 v83; // [rsp+68h] [rbp-21h]
  __int64 v84; // [rsp+70h] [rbp-19h]
  __int64 *v85; // [rsp+78h] [rbp-11h]
  char v86[4]; // [rsp+80h] [rbp-9h] BYREF
  unsigned int v87; // [rsp+84h] [rbp-5h]
  __int64 v88; // [rsp+88h] [rbp-1h]
  char v89; // [rsp+90h] [rbp+7h] BYREF
  int v91; // [rsp+F8h] [rbp+6Fh]
  unsigned int v92; // [rsp+100h] [rbp+77h]

  v1 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_48b71e9a06de38317ed143d1f750f029_Traceguids,
      "Legacy::KnowledgeInspector::EnsureCachedScopeVector");
  }
  v2 = 0;
  if ( *((_QWORD *)v1 + 1) )
    goto LABEL_55;
  v3 = *(_QWORD *)v1 + 184LL;
  v75 = 0;
  v2 = RangeSetManager::FindByIndex(v3, 0, &v75);
  v4 = 1;
  if ( v2 )
  {
    v79 = 0;
    goto LABEL_143;
  }
  v5 = v75;
  v6 = 0;
  v79 = 0;
  if ( !*((_DWORD *)v75 + 2) )
  {
    v2 = -2147217379;
    goto LABEL_143;
  }
  v7 = 0;
  while ( 1 )
  {
    if ( v7 >= *((_DWORD *)v5 + 2) )
      goto LABEL_50;
    v8 = 0;
    v9 = v7 + 1;
    v10 = (__int64 *)((char *)v5 + 24);
    v77 = 0;
    v78 = 0;
    v82 = v9;
    if ( (unsigned int)v9 >= *((_DWORD *)v5 + 2) )
    {
      v45 = v7;
      goto LABEL_94;
    }
    v11 = *v10;
    v85 = (__int64 *)((char *)v5 + 24);
    v83 = v11;
    v12 = v11 + 24 * v9;
    if ( v76 != (_BYTE *)v12 )
    {
      v13 = *(void **)(v12 + 8);
      v77 = *(_DWORD *)(v12 + 4);
      v78 = v13;
      if ( !v13 )
        goto LABEL_13;
      _InterlockedAdd((volatile signed __int32 *)v13, 1u);
      v11 = *v10;
    }
    v83 = v11;
LABEL_13:
    v84 = v7;
    v14 = 3LL * v7;
    v80 = v14;
    v15 = (int *)(v11 + 24LL * v7 + 4);
    v16 = *(unsigned __int16 *)v15;
    v17 = *v15 & 0x10000;
    if ( !v17 )
      goto LABEL_14;
    v19 = *(unsigned __int16 **)(v11 + 24LL * v7 + 8);
    v44 = v19;
    v21 = *v15 & 0x20000;
    if ( !v21 )
      v44 = v19 + 2;
    if ( *v44 >= v16 )
      break;
LABEL_19:
    v2 = 0;
    v22 = *v15 & 0xFFFDFFFF;
    v88 = 0;
    v92 = v22;
    v91 = v22 & 0x10000;
    v87 = v22;
    if ( (v22 & 0x10000) != 0 )
    {
      if ( v17 )
      {
        v70 = v19;
        if ( (*v15 & 0x20000) == 0 )
          v70 = v19 + 2;
      }
      else
      {
        v70 = (unsigned __int16 *)(v11 + 24LL * v7 + 4);
      }
      if ( *v70 >= (unsigned __int16)v22 )
      {
        if ( v17 )
        {
          v71 = v19;
          if ( (*v15 & 0x20000) == 0 )
            v71 = v19 + 2;
        }
        else
        {
          v71 = (unsigned __int16 *)(v11 + 24LL * v7 + 4);
        }
        v23 = *v71;
        if ( v23 <= 2u )
        {
LABEL_174:
          v2 = -2147024809;
        }
        else
        {
          if ( !v21 )
            v19 += 2;
          v72 = (char *)v19 - 1;
          while ( v72[v23] == -1 )
          {
            if ( --v23 <= 2u )
              goto LABEL_174;
          }
        }
      }
      else
      {
        if ( v17 )
        {
          if ( (*v15 & 0x20000) == 0 )
            v19 += 2;
        }
        else
        {
          v19 = (unsigned __int16 *)(v11 + 24LL * v7 + 4);
        }
        v23 = *v19 + 1;
      }
    }
    else
    {
      if ( v17 )
      {
        if ( !v21 )
          v19 += 2;
      }
      else
      {
        v19 = (unsigned __int16 *)(v11 + 24LL * v7 + 4);
      }
      v23 = *v19;
    }
    ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
    if ( v2 )
    {
      v24 = (unsigned __int16 *)lpMem;
LABEL_129:
      SyncId::~SyncId((SyncId *)v86);
      v29 = 0;
      v92 = 0;
      v30 = 0;
      goto LABEL_37;
    }
    v24 = (unsigned __int16 *)HeapAlloc(hHeap, 0, v23 + 7LL);
    if ( lpMem )
      HeapFree(hHeap, 0, lpMem);
    lpMem = v24;
    v2 = v24 == 0 ? 0x8007000E : 0;
    if ( !v24 )
    {
      v4 = 1;
      goto LABEL_129;
    }
    v25 = *(char **)(v11 + 8 * v80 + 8);
    v26 = v24 + 2;
    if ( (*v15 & 0x20000) == 0 )
      v25 += 4;
    memcpy_0(v24 + 2, v25, v23);
    if ( v91 )
    {
      v43 = *v15;
      if ( (*v15 & 0x10000) != 0 )
      {
        v15 = *(int **)(v83 + 8 * v80 + 8);
        if ( (v43 & 0x20000) == 0 )
          ++v15;
      }
      v29 = v92;
      if ( *(_WORD *)v15 >= (unsigned __int16)v92 )
        ++*((_BYTE *)v24 + v23 + 3);
      else
        *((_BYTE *)v24 + v23 + 3) = 0;
    }
    else
    {
      v27 = (unsigned __int16 *)((char *)v24 + v23 + 3);
      if ( v27 >= v26 )
      {
        v4 = (unsigned int)(v91 + 1);
        do
        {
          v28 = (_BYTE)v91 + 1 + *(_BYTE *)v27 == 0;
          *(_BYTE *)v27 += v91 + 1;
          if ( !v28 )
          {
            v29 = v92;
            goto LABEL_34;
          }
          v27 = (unsigned __int16 *)((char *)v27 - v4);
        }
        while ( v27 >= v26 );
        v2 = -2147024809;
        goto LABEL_129;
      }
      v29 = v92;
    }
    v4 = 1;
LABEL_34:
    *(_DWORD *)v24 = v4;
    if ( v91 )
      *v26 = v23;
    v30 = (char *)v24;
    v24 = 0;
    lpMem = 0;
LABEL_37:
    if ( v24 )
    {
      HeapFree(hHeap, 0, v24);
      v29 = v92;
    }
    if ( v2 )
    {
      v38 = 0;
      v8 = v77;
    }
    else
    {
      v8 = v77;
      v31 = (unsigned __int8 *)v78;
      v32 = v77 & 0x20000;
      if ( (v77 & 0x20000) == 0 )
        v31 = (unsigned __int8 *)v78 + 4;
      v33 = (unsigned __int8 *)v30;
      if ( (v29 & 0x20000) == 0 )
        v33 = (unsigned __int8 *)(v30 + 4);
      if ( v31 != v33 )
      {
        if ( (v77 & 0x10000) != 0 )
        {
          v63 = (unsigned __int16 *)v78;
          if ( !v32 )
            v63 = (unsigned __int16 *)((char *)v78 + 4);
          v64 = (char *)&v31[*v63];
          if ( (v29 & 0x10000) != 0 )
          {
            v73 = (unsigned __int16 *)v30;
            if ( (v29 & 0x20000) == 0 )
              v73 = (unsigned __int16 *)(v30 + 4);
            v65 = *v73;
          }
          else
          {
            v65 = v29;
          }
          v66 = v65;
          v67 = (char *)(v31 + 2);
          v68 = &v33[v66];
          v69 = v33 + 2;
          while ( v67 < v64 )
          {
            if ( v69 >= v68 || *v67 != *v69 )
              goto LABEL_62;
            v67 += v4;
            v69 += v4;
          }
          if ( v69 < v68 )
          {
LABEL_62:
            v38 = 0;
            goto LABEL_63;
          }
        }
        else
        {
          v34 = (char *)&v31[4 * ((unsigned __int64)(unsigned __int16)v77 >> 2)];
          while ( v31 < (unsigned __int8 *)v34 )
          {
            if ( *(_DWORD *)v31 != *(_DWORD *)v33 )
            {
              if ( *v31 > *v33 )
                goto LABEL_62;
              if ( *v31 < *v33 )
                goto LABEL_62;
              v40 = v33[1];
              if ( v31[1] < v40 )
                goto LABEL_62;
              if ( v31[1] > v40 )
                goto LABEL_62;
              v41 = v33[2];
              if ( v31[2] > v41 )
                goto LABEL_62;
              if ( v31[2] < v41 )
                goto LABEL_62;
              v42 = v33[3];
              if ( v31[3] > v42 || v31[3] < v42 )
                goto LABEL_62;
            }
            v31 += 4;
            v33 += 4;
          }
          if ( (v77 & 3) != 0 )
          {
            v37 = (char *)v78;
            if ( !v32 )
              v37 = (char *)v78 + 4;
            while ( v31 < (unsigned __int8 *)&v37[(unsigned __int16)v77] )
            {
              if ( *v31 > *v33 || *v31 < *v33 )
                goto LABEL_62;
              v31 += v4;
              v33 += v4;
            }
          }
        }
      }
      v38 = v4;
    }
LABEL_63:
    if ( (v29 & 0x20000) == 0 && v30 && _InterlockedExchangeAdd((volatile signed __int32 *)v30, 0xFFFFFFFF) == 1 )
    {
      SeFree(v30);
      v88 = 0;
    }
    if ( v2 )
      goto LABEL_139;
    if ( !v38 )
    {
      v45 = v84;
      v10 = v85;
      v1 = this;
      goto LABEL_94;
    }
LABEL_69:
    v7 = v82;
    v4 = 1;
    v5 = v75;
    v1 = this;
    if ( (v8 & 0x20000) == 0 )
    {
      v39 = v78;
      if ( v78 )
      {
        v28 = _InterlockedExchangeAdd((volatile signed __int32 *)v78, 0xFFFFFFFF) == 1;
        v5 = v75;
        if ( v28 )
        {
          SeFree(v39);
          v5 = v75;
          v78 = 0;
        }
      }
    }
  }
  v14 = v80;
LABEL_14:
  for ( i = v17 != 0 ? 2 : 0; i < v16; ++i )
  {
    v19 = *(unsigned __int16 **)(v11 + 8 * v14 + 8);
    v20 = v19;
    v21 = *v15 & 0x20000;
    if ( !v21 )
      v20 = v19 + 2;
    if ( *((_BYTE *)v20 + i) != 0xFF )
      goto LABEL_19;
    v14 = v80;
  }
  v45 = v84;
  v10 = v85;
  v8 = v77;
LABEL_94:
  v46 = *(_QWORD *)v1;
  v47 = *(unsigned int *)(*v10 + 24 * v45 + 16);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_e65626ae806d36e8966776faf765a664_Traceguids,
      "ClockVectorManager::FindByIndex");
  }
  v48 = 0;
  if ( (unsigned int)v47 >= *(_DWORD *)(v46 + 120) )
  {
    v50 = 0;
    v2 = -2147024809;
  }
  else
  {
    v2 = 0;
    v49 = (char *)(*(_QWORD *)(v46 + 136) + 8 * v47);
    if ( &v89 != v49 )
    {
      v48 = *(_QWORD *)v49;
      if ( *(_QWORD *)v49 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v48 + 8LL))(*(_QWORD *)v49);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 8LL))(v48);
      }
    }
    v50 = v48;
  }
  LODWORD(v4) = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)WPP_e65626ae806d36e8966776faf765a664_Traceguids,
      (unsigned int)"ClockVectorManager::FindByIndex",
      v2);
  }
  if ( v48 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  if ( v2 )
    goto LABEL_137;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        WPP_362d7c742a68350205e0bfe72ed984ca_Traceguids,
        "ClockVector::Intersect");
    }
    v51 = *(_DWORD *)(v6 + 28);
    if ( v51 )
    {
      v52 = 0;
      v53 = 0;
      while ( 1 )
      {
        if ( v53 >= *(_DWORD *)(v50 + 28) )
        {
          if ( v52 < v51 )
          {
            do
            {
              v74 = v52++;
              *(_QWORD *)(*(_QWORD *)(v6 + 40) + 16 * v74 + 8) = 0;
            }
            while ( v52 < *(_DWORD *)(v6 + 28) );
          }
          goto LABEL_121;
        }
        v54 = *(_QWORD *)(v50 + 40);
        v55 = *(_QWORD *)(v6 + 40);
        v56 = 2LL * v53;
        v57 = *(_DWORD *)(v54 + 16LL * v53);
        if ( *(_DWORD *)(v55 + 16LL * v52) < v57 )
          break;
        ++v53;
        if ( *(_DWORD *)(v55 + 16LL * v52) <= v57 )
        {
          v58 = *(_QWORD *)(v55 + 16LL * v52 + 8);
          if ( v58 >= *(_QWORD *)(v54 + 8 * v56 + 8) )
            v58 = *(_QWORD *)(v54 + 8 * v56 + 8);
          *(_QWORD *)(v55 + 16LL * v52 + 8) = v58;
          goto LABEL_117;
        }
LABEL_118:
        v51 = *(_DWORD *)(v6 + 28);
        if ( v52 >= v51 )
          goto LABEL_121;
      }
      *(_QWORD *)(v55 + 16LL * v52 + 8) = 0;
LABEL_117:
      ++v52;
      goto LABEL_118;
    }
LABEL_121:
    ClockVector::Compress((ClockVector *)v6);
    *(_DWORD *)(v6 + 56) = -1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        (unsigned int)WPP_362d7c742a68350205e0bfe72ed984ca_Traceguids,
        (unsigned int)"ClockVector::Intersect",
        0);
    }
    v2 = 0;
    goto LABEL_124;
  }
  v59 = (ClockVector *)SeAlloc(0x40u);
  if ( v59 )
  {
    v60 = ClockVector::ClockVector(v59);
    v79 = v60;
    v6 = (__int64)v60;
    if ( !v60 )
      goto LABEL_136;
    v2 = ClockVector::InitializeByCloning(v60, (const struct ClockVector *)v50);
    if ( v2 )
      goto LABEL_137;
LABEL_124:
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    goto LABEL_69;
  }
  v6 = 0;
  v79 = 0;
LABEL_136:
  v2 = -2147024882;
LABEL_137:
  if ( v50 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
LABEL_139:
  SyncId::~SyncId((SyncId *)v76);
  v1 = this;
LABEL_50:
  if ( v6 )
  {
    if ( !v2 )
      goto LABEL_52;
    goto LABEL_201;
  }
LABEL_143:
  if ( !v2 )
  {
    v61 = (ClockVector *)SeAlloc(0x40u);
    if ( v61 )
      v61 = ClockVector::ClockVector(v61);
    v62 = ScopedPtrBase<SyncKnowledge,ScopedRefPtr<SyncKnowledge>>::Attach((__int64 *)&v79, (__int64)v61);
    v6 = (__int64)v79;
    v2 = v62;
    if ( v62 )
      goto LABEL_201;
    *((_DWORD *)v79 + 9) |= v4;
LABEL_52:
    v35 = *((_QWORD *)v1 + 1);
    *((_QWORD *)v1 + 1) = v6;
    v6 = v35;
    if ( v35 )
    {
LABEL_201:
      if ( v6 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  if ( v75 )
    RangeSet::Release(v75);
LABEL_55:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)WPP_48b71e9a06de38317ed143d1f750f029_Traceguids,
      (unsigned int)"Legacy::KnowledgeInspector::EnsureCachedScopeVector",
      v2);
  }
  return v2;
}

```

## disassembly

```asm
0x1800110f8  mov     [rsp-8+arg_0], rcx
0x1800110fd  push    rbp
0x1800110fe  push    rbx
0x1800110ff  push    rsi
0x180011100  push    rdi
0x180011101  push    r12
0x180011103  push    r13
0x180011105  push    r14
0x180011107  push    r15
0x180011109  lea     rbp, [rsp-1Fh]
0x18001110e  sub     rsp, 0A8h
0x180011115  mov     rsi, rcx
0x180011118  mov     rcx, cs:WPP_GLOBAL_Control
0x18001111f  lea     r13, WPP_GLOBAL_Control
0x180011126  cmp     rcx, r13
0x180011129  jz      short loc_180011135
0x18001112b  test    byte ptr [rcx+1Ch], 40h
0x18001112f  jnz     loc_180011AC9
0x180011135  xor     edi, edi
0x180011137  cmp     [rsi+8], rdi
0x18001113b  jnz     loc_18001141C
0x180011141  mov     rcx, [rsi]
0x180011144  lea     r8, [rbp+57h+var_B0]
0x180011148  add     rcx, 0B8h
0x18001114f  mov     [rbp+57h+var_B0], rdi
0x180011153  xor     edx, edx
0x180011155  call    ?FindByIndex@RangeSetManager@@QEBAJKAEAV?$SharedRefPtr@VRangeSet@@@@@Z; RangeSetManager::FindByIndex(ulong,SharedRefPtr<RangeSet> &)
0x18001115a  mov     edi, eax
0x18001115c  mov     r14d, 1
0x180011162  test    eax, eax
0x180011164  jnz     loc_1800119A7
0x18001116a  mov     rax, [rbp+57h+var_B0]
0x18001116e  xor     r12d, r12d
0x180011171  mov     [rbp+57h+var_98], r12
0x180011175  cmp     [rax+8], r12d
0x180011179  jbe     loc_18001183C
0x18001117f  xor     ebx, ebx
0x180011181  cmp     ebx, [rax+8]
0x180011184  jnb     loc_1800113E9
0x18001118a  xor     r15d, r15d
0x18001118d  lea     ecx, [rbx+1]
0x180011190  lea     r10, [rax+18h]
0x180011194  mov     [rbp+57h+var_A4], r15d
0x180011198  mov     [rbp+57h+var_A0], r15
0x18001119c  mov     [rbp+57h+var_80], ecx
0x18001119f  cmp     ecx, [rax+8]
0x1800111a2  jnb     loc_180011835
0x1800111a8  mov     r15, [r10]
0x1800111ab  lea     rcx, [rcx+rcx*2]
0x1800111af  mov     [rbp+57h+var_68], r10
0x1800111b3  mov     [rbp+57h+var_78], r15
0x1800111b7  lea     rax, [r15+rcx*8]
0x1800111bb  lea     rcx, [rbp+57h+var_A8]
0x1800111bf  cmp     rcx, rax
0x1800111c2  jz      short loc_1800111DE
0x1800111c4  mov     r8, [rax+8]
0x1800111c8  mov     ecx, [rax+4]
0x1800111cb  mov     [rbp+57h+var_A4], ecx
0x1800111ce  mov     [rbp+57h+var_A0], r8
0x1800111d2  test    r8, r8
0x1800111d5  jz      short loc_1800111E2
0x1800111d7  lock add [r8], r14d
0x1800111db  mov     r15, [r10]
0x1800111de  mov     [rbp+57h+var_78], r15
0x1800111e2  mov     edx, ebx
0x1800111e4  mov     ebx, 20000h
0x1800111e9  mov     [rbp+57h+var_70], rdx
0x1800111ed  lea     rcx, [rdx+rdx*2]
0x1800111f1  lea     r13, ds:4[rcx*8]
0x1800111f9  mov     [rbp+57h+var_90], rcx
0x1800111fd  add     r13, r15
0x180011200  mov     r9d, [r13+0]
0x180011204  movzx   r11d, word ptr [r13+0]
0x180011209  and     r9d, 10000h
0x180011210  jnz     loc_18001159B
0x180011216  mov     eax, r9d
0x180011219  neg     eax
0x18001121b  sbb     r8w, r8w
0x18001121f  and     r8w, 2
0x180011224  movzx   eax, r8w
0x180011228  cmp     eax, r11d
0x18001122b  jnb     loc_180011792
0x180011231  mov     rdx, [r15+rcx*8+8]
0x180011236  mov     r10d, [r13+0]
0x18001123a  mov     rcx, rdx
0x18001123d  and     r10d, ebx
0x180011240  lea     rax, [rdx+4]
0x180011244  cmovz   rcx, rax
0x180011248  movzx   eax, r8w
0x18001124c  cmp     byte ptr [rcx+rax], 0FFh
0x180011250  jz      loc_18001177C
0x180011256  mov     ecx, [r13+0]
0x18001125a  xor     edi, edi
0x18001125c  btr     ecx, 11h
0x180011260  mov     [rbp+57h+arg_18], 0
0x180011267  mov     eax, ecx
0x180011269  mov     [rbp+57h+var_58], 0
0x180011271  and     eax, 10000h
0x180011276  mov     [rbp+57h+arg_10], ecx
0x180011279  mov     [rbp+57h+arg_8], eax
0x18001127c  mov     [rbp+57h+var_5C], ecx
0x18001127f  jnz     loc_180011919
0x180011285  test    r9d, r9d
0x180011288  jnz     loc_180011997
0x18001128e  mov     rdx, r13
0x180011291  movzx   esi, word ptr [rdx]
0x180011294  lea     rcx, [rbp+57h+lpMem]
0x180011298  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x18001129d  test    edi, edi
0x18001129f  jnz     loc_180011AF4
0x1800112a5  mov     rcx, cs:hHeap; hHeap
0x1800112ac  xor     edx, edx; dwFlags
0x1800112ae  movzx   r14d, si
0x1800112b2  lea     r8, [r14+7]; dwBytes
0x1800112b6  call    cs:__imp_HeapAlloc
0x1800112bc  mov     r8, [rbp+57h+lpMem]; lpMem
0x1800112c0  mov     rbx, rax
0x1800112c3  test    r8, r8
0x1800112c6  jz      short loc_1800112D7
0x1800112c8  mov     rcx, cs:hHeap; hHeap
0x1800112cf  xor     edx, edx; dwFlags
0x1800112d1  call    cs:__imp_HeapFree
0x1800112d7  mov     rax, rbx
0x1800112da  mov     [rbp+57h+lpMem], rbx
0x1800112de  neg     rax
0x1800112e1  sbb     edi, edi
0x1800112e3  not     edi
0x1800112e5  and     edi, 8007000Eh
0x1800112eb  test    rbx, rbx
0x1800112ee  jz      loc_180011AFD
0x1800112f4  mov     rax, [rbp+57h+var_90]
0x1800112f8  mov     r8, r14; Size
0x1800112fb  test    dword ptr [r13+0], 20000h
0x180011303  mov     rdx, [r15+rax*8+8]
0x180011308  lea     r15, [rbx+4]
0x18001130c  mov     rcx, r15; void *
0x18001130f  lea     rax, [rdx+4]
0x180011313  cmovz   rdx, rax; Src
0x180011317  call    memcpy_0
0x18001131c  mov     edx, [rbp+57h+arg_8]
0x18001131f  test    edx, edx
0x180011321  jnz     loc_18001154B
0x180011327  lea     rcx, [r14+3]
0x18001132b  add     rcx, rbx
0x18001132e  cmp     rcx, r15
0x180011331  jb      loc_180011789
0x180011337  lea     r14d, [rdx+1]
0x18001133b  add     [rcx], r14b
0x18001133e  jz      loc_180011754
0x180011344  mov     r11d, [rbp+57h+arg_10]
0x180011348  mov     [rbx], r14d
0x18001134b  test    edx, edx
0x18001134d  jnz     loc_180011910
0x180011353  mov     rsi, rbx
0x180011356  xor     ebx, ebx
0x180011358  mov     [rbp+57h+lpMem], rbx
0x18001135c  test    rbx, rbx
0x18001135f  jz      short loc_180011377
0x180011361  mov     rcx, cs:hHeap; hHeap
0x180011368  mov     r8, rbx; lpMem
0x18001136b  xor     edx, edx; dwFlags
0x18001136d  call    cs:__imp_HeapFree
0x180011373  mov     r11d, [rbp+57h+arg_10]
0x180011377  test    edi, edi
0x180011379  jnz     loc_180011B08
0x18001137f  mov     r15d, [rbp+57h+var_A4]
0x180011383  mov     rbx, [rbp+57h+var_A0]
0x180011387  mov     r9d, r15d
0x18001138a  mov     rcx, rbx
0x18001138d  and     r9d, 20000h
0x180011394  jnz     short loc_18001139A
0x180011396  lea     rcx, [rbx+4]
0x18001139a  mov     r8d, r11d
0x18001139d  mov     rdx, rsi
0x1800113a0  and     r8d, 20000h
0x1800113a7  jz      loc_180011542
0x1800113ad  cmp     rcx, rdx
0x1800113b0  jz      loc_180011582
0x1800113b6  bt      r15d, 10h
0x1800113bb  jb      loc_1800118BB
0x1800113c1  movzx   r10d, r15w
0x1800113c5  mov     eax, r10d
0x1800113c8  shr     rax, 2
0x1800113cc  lea     r8, [rcx+rax*4]
0x1800113d0  cmp     rcx, r8
0x1800113d3  jnb     short loc_180011442
0x1800113d5  mov     eax, [rcx]
0x1800113d7  cmp     eax, [rdx]
0x1800113d9  jnz     loc_1800114F7
0x1800113df  add     rcx, 4
0x1800113e3  add     rdx, 4
0x1800113e7  jmp     short loc_1800113D0
0x1800113e9  test    r12, r12
0x1800113ec  jz      loc_180011841
0x1800113f2  test    edi, edi
0x1800113f4  jnz     loc_180011A91
0x1800113fa  mov     rax, [rsi+8]
0x1800113fe  mov     [rsi+8], r12
0x180011402  mov     r12, rax
0x180011405  test    rax, rax
0x180011408  jnz     loc_180011A91
0x18001140e  mov     rcx, [rbp+57h+var_B0]; this
0x180011412  test    rcx, rcx
0x180011415  jz      short loc_18001141C
0x180011417  call    ?Release@RangeSet@@QEAAKXZ; RangeSet::Release(void)
0x18001141c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011423  cmp     rcx, r13
0x180011426  jnz     loc_180011882
0x18001142c  mov     eax, edi
0x18001142e  add     rsp, 0A8h
0x180011435  pop     r15
0x180011437  pop     r14
0x180011439  pop     r13
0x18001143b  pop     r12
0x18001143d  pop     rdi
0x18001143e  pop     rsi
0x18001143f  pop     rbx
0x180011440  pop     rbp
0x180011441  retn
0x180011442  test    r15b, 3
0x180011446  jz      loc_180011582
0x18001144c  mov     rax, rbx
0x18001144f  test    r9d, r9d
0x180011452  jz      loc_180011579
0x180011458  lea     r8, [r10+rax]
0x18001145c  cmp     rcx, r8
0x18001145f  jnb     loc_180011582
0x180011465  mov     al, [rcx]
0x180011467  cmp     al, [rdx]
0x180011469  jbe     loc_18001158A
0x18001146f  xor     ebx, ebx
0x180011471  bt      r11d, 11h
0x180011476  jb      short loc_18001148D
0x180011478  test    rsi, rsi
0x18001147b  jz      short loc_18001148D
0x18001147d  or      eax, 0FFFFFFFFh
0x180011480  lock xadd [rsi], eax
0x180011484  cmp     eax, 1
0x180011487  jz      loc_1800117AA
0x18001148d  test    edi, edi
0x18001148f  jnz     loc_180011823
0x180011495  lea     r13, WPP_GLOBAL_Control
0x18001149c  test    ebx, ebx
0x18001149e  jz      loc_1800115C7
0x1800114a4  mov     ebx, [rbp+57h+var_80]
0x1800114a7  mov     r14d, 1
0x1800114ad  mov     rax, [rbp+57h+var_B0]
0x1800114b1  mov     rsi, [rbp+57h+arg_0]
0x1800114b5  bt      r15d, 11h
0x1800114ba  jb      loc_180011181
0x1800114c0  mov     rcx, [rbp+57h+var_A0]; void *
0x1800114c4  test    rcx, rcx
0x1800114c7  jz      loc_180011181
0x1800114cd  or      eax, 0FFFFFFFFh
0x1800114d0  lock xadd [rcx], eax
0x1800114d4  cmp     eax, r14d
0x1800114d7  mov     rax, [rbp+57h+var_B0]
0x1800114db  jnz     loc_180011181
0x1800114e1  call    ?SeFree@@YAXPEAX@Z; SeFree(void *)
0x1800114e6  mov     rax, [rbp+57h+var_B0]
0x1800114ea  mov     [rbp+57h+var_A0], 0
0x1800114f2  jmp     loc_180011181
0x1800114f7  mov     al, [rcx]
0x1800114f9  cmp     al, [rdx]
0x1800114fb  ja      loc_18001146F
0x180011501  jb      loc_18001146F
0x180011507  mov     al, [rdx+1]
0x18001150a  cmp     [rcx+1], al
0x18001150d  jb      loc_18001146F
0x180011513  ja      loc_18001146F
0x180011519  mov     al, [rdx+2]
0x18001151c  cmp     [rcx+2], al
0x18001151f  ja      loc_18001146F
0x180011525  jb      loc_18001146F
0x18001152b  mov     al, [rdx+3]
0x18001152e  cmp     [rcx+3], al
0x180011531  ja      loc_18001146F
0x180011537  jnb     loc_1800113DF
0x18001153d  jmp     loc_18001146F
0x180011542  lea     rdx, [rsi+4]
0x180011546  jmp     loc_1800113AD
0x18001154b  mov     eax, [r13+0]
0x18001154f  bt      eax, 10h
0x180011553  jb      loc_1800119B4
0x180011559  mov     r11d, [rbp+57h+arg_10]
0x18001155d  cmp     [r13+0], r11w
0x180011562  jnb     loc_18001174A
0x180011568  mov     byte ptr [rbx+r14+3], 0
0x18001156e  mov     r14d, 1
0x180011574  jmp     loc_180011348
0x180011579  lea     rax, [rbx+4]
0x18001157d  jmp     loc_180011458
0x180011582  mov     ebx, r14d
0x180011585  jmp     loc_180011471
0x18001158a  jb      loc_18001146F
0x180011590  add     rcx, r14
0x180011593  add     rdx, r14
0x180011596  jmp     loc_18001145C
0x18001159b  mov     rdx, [r15+rcx*8+8]
0x1800115a0  mov     r10d, [r13+0]
  ... truncated ...
```
