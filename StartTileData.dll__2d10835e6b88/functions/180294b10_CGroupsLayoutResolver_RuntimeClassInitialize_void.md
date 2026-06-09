# CGroupsLayoutResolver::RuntimeClassInitialize(void)

- ea: `0x180294b10`
- end: `0x180295529`
- name: `?RuntimeClassInitialize@CGroupsLayoutResolver@@UEAAJXZ`
- size: `2585`
- prototype: `__int64 __fastcall(CGroupsLayoutResolver *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18001aca4`
- `0x180025868`
- `0x1800c0988`
- `0x180201e50`
- `0x18020be0c`
- `0x1802909d8`
- `0x18029239c`
- `0x180292598`
- `0x18029272c`
- `0x1802937ac`
- `0x180293968`
- `0x180294b10`
- `0x180295590`
- `0x180299740`
- `0x18029ac28`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180294dd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180294f8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802954d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180295501`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180294dd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180294f8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802954d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180295501`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180294db1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180294f6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802954b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180294db1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180294f6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802954b6`

## string_xrefs

- `0x180294ba2`: `shellcommon\shell\tiles\sharedstartlayout\lib\groupslayoutresolver.cpp`
- `0x180294c77`: `shellcommon\shell\tiles\sharedstartlayout\lib\groupslayoutresolver.cpp`
- `0x180294d31`: `shellcommon\shell\tiles\sharedstartlayout\lib\groupslayoutresolver.cpp`
- `0x180294e20`: `shellcommon\shell\tiles\sharedstartlayout\lib\groupslayoutresolver.cpp`
- `0x180294eea`: `shellcommon\shell\tiles\sharedstartlayout\lib\groupslayoutresolver.cpp`
- `0x180294fd7`: `shellcommon\shell\tiles\sharedstartlayout\lib\groupslayoutresolver.cpp`
- `0x180295087`: `shellcommon\shell\tiles\sharedstartlayout\lib\groupslayoutresolver.cpp`
- `0x180295140`: `shellcommon\shell\tiles\sharedstartlayout\lib\groupslayoutresolver.cpp`
- `0x1802951f9`: `shellcommon\shell\tiles\sharedstartlayout\lib\groupslayoutresolver.cpp`
- `0x1802952c4`: `shellcommon\shell\tiles\sharedstartlayout\lib\groupslayoutresolver.cpp`
- `0x180295387`: `shellcommon\shell\tiles\sharedstartlayout\lib\groupslayoutresolver.cpp`
- `0x1802954e9`: `shellcommon\shell\tiles\sharedstartlayout\lib\groupslayoutresolver.cpp`

## pseudocode

```c
__int64 __fastcall CGroupsLayoutResolver::RuntimeClassInitialize(CGroupsLayoutResolver *this)
{
  struct IItemLayoutDisplacementHandler **v2; // rax
  int v3; // eax
  struct IItemLayoutDisplacementHandler *v4; // rcx
  int v5; // ebx
  __int64 v6; // rcx
  _DWORD *v7; // rdx
  __int64 v8; // rdx
  _DWORD *v9; // rdx
  __int64 v10; // rdx
  struct IItemLayoutDisplacementHandler *v11; // rax
  struct IItemLayoutDisplacementHandler *v12; // rbx
  __int64 v13; // rdx
  int v14; // eax
  unsigned int v15; // esi
  _DWORD *v16; // rcx
  unsigned int v17; // edx
  unsigned int i; // ebx
  __int64 v19; // rdx
  __int64 v21; // rdx
  _DWORD *v22; // rcx
  int v23; // eax
  unsigned int v24; // edx
  unsigned int j; // ebx
  __int64 v26; // rdx
  _DWORD *v27; // rdx
  int updated; // eax
  unsigned int v29; // edi
  _DWORD *v30; // rcx
  unsigned int v31; // edx
  unsigned int k; // ebx
  __int64 v33; // rdx
  int v34; // eax
  unsigned int v35; // edx
  unsigned int m; // ebx
  __int64 v37; // rdx
  int v38; // eax
  unsigned int v39; // edx
  unsigned int n; // ebx
  __int64 v41; // rdx
  int v42; // eax
  unsigned int v43; // edx
  unsigned int ii; // ebx
  __int64 v45; // rdx
  int v46; // eax
  unsigned int v47; // edx
  unsigned int jj; // ebx
  __int64 v49; // rdx
  int v50; // eax
  unsigned int v51; // edx
  unsigned int kk; // ebx
  __int64 v53; // rdx
  int v54; // eax
  unsigned int v55; // edx
  unsigned int mm; // ebx
  __int64 v57; // rdx
  _DWORD *v58; // rcx
  unsigned int v59; // edx
  unsigned int nn; // ebx
  __int64 v61; // rdx
  int v62; // [rsp+20h] [rbp-69h]
  int v63; // [rsp+30h] [rbp-59h] BYREF
  __int64 v64; // [rsp+34h] [rbp-55h]
  HLOCAL hMem; // [rsp+40h] [rbp-49h]
  struct IItemLayoutDisplacementHandler *v66; // [rsp+48h] [rbp-41h] BYREF
  struct IItemLayoutDisplacementHandler *v67; // [rsp+50h] [rbp-39h] BYREF
  struct IItemLayoutDisplacementHandler *v68; // [rsp+58h] [rbp-31h] BYREF
  int v69; // [rsp+60h] [rbp-29h] BYREF
  struct IItemLayoutDisplacementHandler *v70; // [rsp+68h] [rbp-21h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-19h] BYREF
  __int64 v72; // [rsp+78h] [rbp-11h]
  __int64 v73; // [rsp+80h] [rbp-9h]
  __int64 v74; // [rsp+88h] [rbp-1h]
  int *v75; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  CItemLayoutResolver::RuntimeClassInitialize(this);
  *((_BYTE *)this + 252) = 0;
  *((_OWORD *)this + 16) = xmmword_18041A3A8;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  v2 = (struct IItemLayoutDisplacementHandler **)Microsoft::WRL::Details::Make<CEmptyCellDisplacementHandler,>(&v66);
  v3 = CItemLayoutDisplacement::AddDisplacementHandler((CGroupsLayoutResolver *)((char *)this + 56), *v2);
  v4 = v66;
  v5 = v3;
  if ( v66 )
  {
    v66 = 0;
    (*(void (__fastcall **)(struct IItemLayoutDisplacementHandler *))(*(_QWORD *)v4 + 16LL))(v4);
  }
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedstartlayout\\lib\\groupslayoutresolver.cpp",
      (const char *)(unsigned int)v5,
      v62);
    return (unsigned int)v5;
  }
  pv = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v5 = CTSimpleArray<enum DISPLACEMENT_DIRECTION,4294967294,CTPolicyCoTaskMem<enum DISPLACEMENT_DIRECTION>,CSimpleArrayStandardCompareHelper<enum DISPLACEMENT_DIRECTION>,CSimpleArrayStandardMergeHelper<enum DISPLACEMENT_DIRECTION>>::_EnsureCapacity(
         &pv,
         1);
  if ( v5 < 0 )
  {
    v8 = 40;
    goto LABEL_147;
  }
  v6 = v72 + 1;
  v72 = v6;
  v7 = (char *)pv + 4 * v6 - 4;
  if ( v7 )
  {
    *v7 = 0;
    v6 = v72;
  }
  if ( v6 == v74 )
  {
    v5 = CTSimpleArray<enum DISPLACEMENT_DIRECTION,4294967294,CTPolicyCoTaskMem<enum DISPLACEMENT_DIRECTION>,CSimpleArrayStandardCompareHelper<enum DISPLACEMENT_DIRECTION>,CSimpleArrayStandardMergeHelper<enum DISPLACEMENT_DIRECTION>>::_EnsureCapacity(
           &pv,
           v6 + 1);
    if ( v5 < 0 )
    {
      v8 = 41;
LABEL_147:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedstartlayout\\lib\\groupslayoutresolver.cpp",
        (const char *)(unsigned int)v5,
        v62);
LABEL_148:
      if ( pv )
        CoTaskMemFree(pv);
      return (unsigned int)v5;
    }
    v6 = v72;
  }
  v72 = v6 + 1;
  v9 = (char *)pv + 4 * v6;
  if ( v9 )
    *v9 = 1;
  v67 = 0;
  LODWORD(v68) = 3;
  v5 = Microsoft::WRL::Details::MakeAndInitialize<CAdjacentDisplacementHandler,CAdjacentDisplacementHandler,CCoSimpleArray<enum DISPLACEMENT_DIRECTION,4294967294,CSimpleArrayStandardCompareHelper<enum DISPLACEMENT_DIRECTION>> &,enum SINGLE_TILE_ADJACENT_OPTION_FLAGS>(
         &v67,
         &pv,
         &v68);
  if ( v5 < 0 )
  {
    v10 = 47;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedstartlayout\\lib\\groupslayoutresolver.cpp",
      (const char *)(unsigned int)v5,
      v62);
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v67);
    goto LABEL_148;
  }
  v5 = CItemLayoutDisplacement::AddDisplacementHandler((CGroupsLayoutResolver *)((char *)this + 56), v67);
  if ( v5 < 0 )
  {
    v10 = 48;
    goto LABEL_16;
  }
  v63 = 0;
  v64 = 31;
  hMem = 0;
  v11 = (struct IItemLayoutDisplacementHandler *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
  v12 = v11;
  if ( v11 )
  {
    *((_QWORD *)v11 + 1) = 0;
    *((_QWORD *)v11 + 2) = 0;
    *((_QWORD *)v11 + 3) = 0;
    *((_QWORD *)v11 + 4) = 0;
    *(_QWORD *)v11 = &CRefCountedObject<CCoSimpleArray<enum DISPLACEMENT_DIRECTION,4294967294,CSimpleArrayStandardCompareHelper<enum DISPLACEMENT_DIRECTION>>>::`vftable';
    *((_DWORD *)v11 + 10) = 0;
  }
  else
  {
    v12 = 0;
  }
  v66 = v12;
  Microsoft::WRL::ComPtr<CRefCountedObject<CItemLayoutChainDisplacement::ChainLink>>::InternalAddRef(&v66);
  v13 = *((_QWORD *)v12 + 2);
  if ( v13 == *((_QWORD *)v12 + 4) )
  {
    v14 = CTSimpleArray<enum DISPLACEMENT_DIRECTION,4294967294,CTPolicyCoTaskMem<enum DISPLACEMENT_DIRECTION>,CSimpleArrayStandardCompareHelper<enum DISPLACEMENT_DIRECTION>,CSimpleArrayStandardMergeHelper<enum DISPLACEMENT_DIRECTION>>::_EnsureCapacity(
            (char *)v12 + 8,
            v13 + 1);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedstartlayout\\lib\\groupslayoutresolver.cpp",
        (const char *)(unsigned int)v14,
        v62);
      if ( v12 )
        (*(void (__fastcall **)(struct IItemLayoutDisplacementHandler *))(*(_QWORD *)v12 + 16LL))(v12);
      v16 = hMem;
      if ( !hMem )
        goto LABEL_34;
      v17 = v64;
      for ( i = 0; i < v17; ++i )
      {
        if ( v16[4 * i] == 1 )
        {
          v16[4 * i] = 2;
          v19 = *(_QWORD *)&v16[4 * i + 2];
          if ( v19 )
          {
            *(_QWORD *)&v16[4 * i + 2] = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          }
          ++HIDWORD(v64);
          --v63;
          v16 = hMem;
          v17 = v64;
        }
      }
LABEL_33:
      LocalFree(v16);
      hMem = 0;
LABEL_34:
      v63 = 0;
      Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v67);
      if ( pv )
        CoTaskMemFree(pv);
      return v15;
    }
  }
  v21 = ++*((_QWORD *)v12 + 2);
  v22 = (_DWORD *)(*((_QWORD *)v12 + 1) + 4 * (v21 - 1));
  if ( v22 )
  {
    *v22 = 0;
    v21 = *((_QWORD *)v12 + 2);
  }
  if ( v21 == *((_QWORD *)v12 + 4) )
  {
    v23 = CTSimpleArray<enum DISPLACEMENT_DIRECTION,4294967294,CTPolicyCoTaskMem<enum DISPLACEMENT_DIRECTION>,CSimpleArrayStandardCompareHelper<enum DISPLACEMENT_DIRECTION>,CSimpleArrayStandardMergeHelper<enum DISPLACEMENT_DIRECTION>>::_EnsureCapacity(
            (char *)v12 + 8,
            v21 + 1);
    v15 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedstartlayout\\lib\\groupslayoutresolver.cpp",
        (const char *)(unsigned int)v23,
        v62);
      if ( v12 )
        (*(void (__fastcall **)(struct IItemLayoutDisplacementHandler *))(*(_QWORD *)v12 + 16LL))(v12);
      v16 = hMem;
      if ( !hMem )
        goto LABEL_34;
      v24 = v64;
      for ( j = 0; j < v24; ++j )
      {
        if ( v16[4 * j] == 1 )
        {
          v16[4 * j] = 2;
          v26 = *(_QWORD *)&v16[4 * j + 2];
          if ( v26 )
          {
            *(_QWORD *)&v16[4 * j + 2] = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          }
          ++HIDWORD(v64);
          --v63;
          v16 = hMem;
          v24 = v64;
        }
      }
      goto LABEL_33;
    }
  }
  v27 = (_DWORD *)(*((_QWORD *)v12 + 1) + 4 * (*((_QWORD *)v12 + 2))++);
  if ( v27 )
    *v27 = 1;
  LODWORD(v68) = 0;
  updated = CSimpleHashTable<unsigned int,Microsoft::WRL::ComPtr<CRefCountedObject<CCoSimpleArray<enum DISPLACEMENT_DIRECTION,4294967294,CSimpleArrayStandardCompareHelper<enum DISPLACEMENT_DIRECTION>>>>,CDefaultHashPolicy<unsigned int>,CDefaultKeyCompare<unsigned int>,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(
              &v63,
              v27,
              &v68,
              &v66);
  v29 = updated;
  if ( updated < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedstartlayout\\lib\\groupslayoutresolver.cpp",
      (const char *)(unsigned int)updated,
      v62);
    if ( v12 )
      (*(void (__fastcall **)(struct IItemLayoutDisplacementHandler *))(*(_QWORD *)v12 + 16LL))(v12);
    v30 = hMem;
    if ( !hMem )
      goto LABEL_64;
    v31 = v64;
    for ( k = 0; k < v31; ++k )
    {
      if ( v30[4 * k] == 1 )
      {
        v30[4 * k] = 2;
        v33 = *(_QWORD *)&v30[4 * k + 2];
        if ( v33 )
        {
          *(_QWORD *)&v30[4 * k + 2] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
        }
        ++HIDWORD(v64);
        --v63;
        v30 = hMem;
        v31 = v64;
      }
    }
LABEL_63:
    LocalFree(v30);
    hMem = 0;
LABEL_64:
    v63 = 0;
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v67);
    if ( pv )
      CoTaskMemFree(pv);
    return v29;
  }
  v66 = 0;
  v75 = &v63;
  LODWORD(v68) = 0;
  v69 = 0;
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v66);
  v34 = Microsoft::WRL::Details::MakeAndInitialize<CItemLayoutChainDisplacement,CItemLayoutChainDisplacement,CSimpleHashTable<unsigned int,Microsoft::WRL::ComPtr<CRefCountedObject<CCoSimpleArray<enum DISPLACEMENT_DIRECTION,4294967294,CSimpleArrayStandardCompareHelper<enum DISPLACEMENT_DIRECTION>>>>,CDefaultHashPolicy<unsigned int>,CDefaultKeyCompare<unsigned int>,CDefaultResizePolicy,CDefaultRehashPolicy> *,int,enum CHAIN_DISPLACEMENT_OPTION_FLAGS>(
          &v66,
          &v75,
          &v69,
          &v68);
  v29 = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedstartlayout\\lib\\groupslayoutresolver.cpp",
      (const char *)(unsigned int)v34,
      v62);
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v66);
    if ( v12 )
      (*(void (__fastcall **)(struct IItemLayoutDisplacementHandler *))(*(_QWORD *)v12 + 16LL))(v12);
    v30 = hMem;
    if ( !hMem )
      goto LABEL_64;
    v35 = v64;
    for ( m = 0; m < v35; ++m )
    {
      if ( v30[4 * m] == 1 )
      {
        v30[4 * m] = 2;
        v37 = *(_QWORD *)&v30[4 * m + 2];
        if ( v37 )
        {
          *(_QWORD *)&v30[4 * m + 2] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        }
        ++HIDWORD(v64);
        --v63;
        v30 = hMem;
        v35 = v64;
      }
    }
    goto LABEL_63;
  }
  v38 = CItemLayoutDisplacement::AddDisplacementHandler((CGroupsLayoutResolver *)((char *)this + 56), v66);
  v29 = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedstartlayout\\lib\\groupslayoutresolver.cpp",
      (const char *)(unsigned int)v38,
      v62);
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v66);
    if ( v12 )
      (*(void (__fastcall **)(struct IItemLayoutDisplacementHandler *))(*(_QWORD *)v12 + 16LL))(v12);
    v30 = hMem;
    if ( !hMem )
      goto LABEL_64;
    v39 = v64;
    for ( n = 0; n < v39; ++n )
    {
      if ( v30[4 * n] == 1 )
      {
        v30[4 * n] = 2;
        v41 = *(_QWORD *)&v30[4 * n + 2];
        if ( v41 )
        {
          *(_QWORD *)&v30[4 * n + 2] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
        }
        ++HIDWORD(v64);
        --v63;
        v30 = hMem;
        v39 = v64;
      }
    }
    goto LABEL_63;
  }
  v70 = 0;
  v69 = 0;
  v42 = Microsoft::WRL::Details::MakeAndInitialize<CExpandDisplacementHandler,CExpandDisplacementHandler,enum EXPAND_COLLAPSE_DIRECTION>(
          &v70,
          &v69);
  v29 = v42;
  if ( v42 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedstartlayout\\lib\\groupslayoutresolver.cpp",
      (const char *)(unsigned int)v42,
      v62);
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v70);
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v66);
    if ( v12 )
      (*(void (__fastcall **)(struct IItemLayoutDisplacementHandler *))(*(_QWORD *)v12 + 16LL))(v12);
    v30 = hMem;
    if ( !hMem )
      goto LABEL_64;
    v43 = v64;
    for ( ii = 0; ii < v43; ++ii )
    {
      if ( v30[4 * ii] == 1 )
      {
        v30[4 * ii] = 2;
        v45 = *(_QWORD *)&v30[4 * ii + 2];
        if ( v45 )
        {
          *(_QWORD *)&v30[4 * ii + 2] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
        }
        ++HIDWORD(v64);
        --v63;
        v30 = hMem;
        v43 = v64;
      }
    }
    goto LABEL_63;
  }
  v46 = CItemLayoutDisplacement::AddDisplacementHandler((CGroupsLayoutResolver *)((char *)this + 56), v70);
  v29 = v46;
  if ( v46 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedstartlayout\\lib\\groupslayoutresolver.cpp",
      (const char *)(unsigned int)v46,
      v62);
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v70);
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v66);
    if ( v12 )
      (*(void (__fastcall **)(struct IItemLayoutDisplacementHandler *))(*(_QWORD *)v12 + 16LL))(v12);
    v30 = hMem;
    if ( !hMem )
      goto LABEL_64;
    v47 = v64;
    for ( jj = 0; jj < v47; ++jj )
    {
      if ( v30[4 * jj] == 1 )
      {
        v30[4 * jj] = 2;
        v49 = *(_QWORD *)&v30[4 * jj + 2];
        if ( v49 )
        {
          *(_QWORD *)&v30[4 * jj + 2] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
        }
        ++HIDWORD(v64);
        --v63;
        v30 = hMem;
        v47 = v64;
      }
    }
    goto LABEL_63;
  }
  v68 = 0;
  v69 = 0;
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v68);
  v50 = Microsoft::WRL::Details::MakeAndInitialize<CGroupsLayoutCollapseHandler,CGroupsLayoutCollapseHandler,enum EXPAND_COLLAPSE_DIRECTION>(
          &v68,
          &v69);
  v29 = v50;
  if ( v50 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedstartlayout\\lib\\groupslayoutresolver.cpp",
      (const char *)(unsigned int)v50,
      v62);
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v68);
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v70);
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v66);
    if ( v12 )
      (*(void (__fastcall **)(struct IItemLayoutDisplacementHandler *))(*(_QWORD *)v12 + 16LL))(v12);
    v30 = hMem;
    if ( !hMem )
      goto LABEL_64;
    v51 = v64;
    for ( kk = 0; kk < v51; ++kk )
    {
      if ( v30[4 * kk] == 1 )
      {
        v30[4 * kk] = 2;
        v53 = *(_QWORD *)&v30[4 * kk + 2];
        if ( v53 )
        {
          *(_QWORD *)&v30[4 * kk + 2] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
        }
        ++HIDWORD(v64);
        --v63;
        v30 = hMem;
        v51 = v64;
      }
    }
    goto LABEL_63;
  }
  v54 = CItemLayoutDisplacement::AddDisplacementHandler((CGroupsLayoutResolver *)((char *)this + 88), v68);
  v29 = v54;
  if ( v54 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedstartlayout\\lib\\groupslayoutresolver.cpp",
      (const char *)(unsigned int)v54,
      v62);
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v68);
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v70);
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v66);
    if ( v12 )
      (*(void (__fastcall **)(struct IItemLayoutDisplacementHandler *))(*(_QWORD *)v12 + 16LL))(v12);
    v30 = hMem;
    if ( !hMem )
      goto LABEL_64;
    v55 = v64;
    for ( mm = 0; mm < v55; ++mm )
    {
      if ( v30[4 * mm] == 1 )
      {
        v30[4 * mm] = 2;
        v57 = *(_QWORD *)&v30[4 * mm + 2];
        if ( v57 )
        {
          *(_QWORD *)&v30[4 * mm + 2] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
        }
        ++HIDWORD(v64);
        --v63;
        v30 = hMem;
        v55 = v64;
      }
    }
    goto LABEL_63;
  }
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v68);
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v70);
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v66);
  if ( v12 )
    (*(void (__fastcall **)(struct IItemLayoutDisplacementHandler *))(*(_QWORD *)v12 + 16LL))(v12);
  v58 = hMem;
  if ( hMem )
  {
    v59 = v64;
    for ( nn = 0; nn < v59; ++nn )
    {
      if ( v58[4 * nn] == 1 )
      {
        v58[4 * nn] = 2;
        v61 = *(_QWORD *)&v58[4 * nn + 2];
        if ( v61 )
        {
          *(_QWORD *)&v58[4 * nn + 2] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
        }
        ++HIDWORD(v64);
        --v63;
        v58 = hMem;
        v59 = v64;
      }
    }
    LocalFree(v58);
    hMem = 0;
  }
  v63 = 0;
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v67);
  if ( pv )
    CoTaskMemFree(pv);
  return 0;
}

```

## disassembly

```asm
0x180294b10  push    rbp
0x180294b12  push    rbx
0x180294b13  push    rsi
0x180294b14  push    rdi
0x180294b15  push    r12
0x180294b17  push    r13
0x180294b19  push    r14
0x180294b1b  push    r15
0x180294b1d  lea     rbp, [rsp-1Fh]
0x180294b22  sub     rsp, 0A8h
0x180294b29  mov     rax, cs:__security_cookie
0x180294b30  xor     rax, rsp
0x180294b33  mov     [rbp+57h+var_48], rax
0x180294b37  mov     r14, rcx
0x180294b3a  call    ?RuntimeClassInitialize@CItemLayoutResolver@@UEAAJXZ; CItemLayoutResolver::RuntimeClassInitialize(void)
0x180294b3f  xor     r12d, r12d
0x180294b42  lea     rcx, [rbp+57h+var_98]
0x180294b46  mov     [r14+0FCh], r12b
0x180294b4d  movups  xmm0, cs:xmmword_18041A3A8
0x180294b54  movdqu  xmmword ptr [r14+100h], xmm0
0x180294b5d  mov     [r14+110h], r12
0x180294b64  mov     [r14+118h], r12
0x180294b6b  call    ??$Make@VCEmptyCellDisplacementHandler@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCEmptyCellDisplacementHandler@@@12@XZ; Microsoft::WRL::Details::Make<CEmptyCellDisplacementHandler,>(void)
0x180294b70  lea     r15, [r14+38h]
0x180294b74  mov     rcx, r15; this
0x180294b77  mov     rdx, [rax]; struct IItemLayoutDisplacementHandler *
0x180294b7a  call    ?AddDisplacementHandler@CItemLayoutDisplacement@@QEAAJPEAUIItemLayoutDisplacementHandler@@@Z; CItemLayoutDisplacement::AddDisplacementHandler(IItemLayoutDisplacementHandler *)
0x180294b7f  mov     rcx, [rbp+57h+var_98]
0x180294b83  mov     ebx, eax
0x180294b85  test    rcx, rcx
0x180294b88  jz      short loc_180294B9A
0x180294b8a  mov     [rbp+57h+var_98], r12
0x180294b8e  mov     rdx, [rcx]
0x180294b91  mov     rax, [rdx+10h]
0x180294b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180294b9a  test    ebx, ebx
0x180294b9c  jns     short loc_180294BBB
0x180294b9e  mov     rcx, [rbp+5Fh]; this
0x180294ba2  lea     r8, aShellcommonShe_175; "shellcommon\\shell\\tiles\\sharedstartl"...
0x180294ba9  mov     r9d, ebx; char *
0x180294bac  mov     edx, 23h ; '#'; void *
0x180294bb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180294bb6  jmp     loc_180295507
0x180294bbb  mov     r13d, 1
0x180294bc1  mov     [rbp+57h+pv], r12
0x180294bc5  mov     edx, r13d
0x180294bc8  mov     [rbp+57h+var_68], r12
0x180294bcc  lea     rcx, [rbp+57h+pv]
0x180294bd0  mov     [rbp+57h+var_60], r12
0x180294bd4  mov     [rbp+57h+var_58], r12
0x180294bd8  call    ?_EnsureCapacity@?$CTSimpleArray@W4DISPLACEMENT_DIRECTION@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@W4DISPLACEMENT_DIRECTION@@@@V?$CSimpleArrayStandardCompareHelper@W4DISPLACEMENT_DIRECTION@@@@V?$CSimpleArrayStandardMergeHelper@W4DISPLACEMENT_DIRECTION@@@@@@QEAAJ_K0@Z; CTSimpleArray<DISPLACEMENT_DIRECTION,4294967294,CTPolicyCoTaskMem<DISPLACEMENT_DIRECTION>,CSimpleArrayStandardCompareHelper<DISPLACEMENT_DIRECTION>,CSimpleArrayStandardMergeHelper<DISPLACEMENT_DIRECTION>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180294bdd  mov     ebx, eax
0x180294bdf  test    eax, eax
0x180294be1  js      loc_1802954E0
0x180294be7  mov     rcx, [rbp+57h+var_68]
0x180294beb  mov     rdx, [rbp+57h+pv]
0x180294bef  add     rcx, r13
0x180294bf2  add     rdx, 0FFFFFFFFFFFFFFFCh
0x180294bf6  mov     [rbp+57h+var_68], rcx
0x180294bfa  lea     rdx, [rdx+rcx*4]
0x180294bfe  test    rdx, rdx
0x180294c01  jz      short loc_180294C0A
0x180294c03  mov     [rdx], r12d
0x180294c06  mov     rcx, [rbp+57h+var_68]
0x180294c0a  cmp     rcx, [rbp+57h+var_58]
0x180294c0e  jnz     short loc_180294C31
0x180294c10  lea     rdx, [rcx+1]
0x180294c14  lea     rcx, [rbp+57h+pv]
0x180294c18  call    ?_EnsureCapacity@?$CTSimpleArray@W4DISPLACEMENT_DIRECTION@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@W4DISPLACEMENT_DIRECTION@@@@V?$CSimpleArrayStandardCompareHelper@W4DISPLACEMENT_DIRECTION@@@@V?$CSimpleArrayStandardMergeHelper@W4DISPLACEMENT_DIRECTION@@@@@@QEAAJ_K0@Z; CTSimpleArray<DISPLACEMENT_DIRECTION,4294967294,CTPolicyCoTaskMem<DISPLACEMENT_DIRECTION>,CSimpleArrayStandardCompareHelper<DISPLACEMENT_DIRECTION>,CSimpleArrayStandardMergeHelper<DISPLACEMENT_DIRECTION>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180294c1d  mov     ebx, eax
0x180294c1f  test    eax, eax
0x180294c21  jns     short loc_180294C2D
0x180294c23  mov     edx, 29h ; ')'
0x180294c28  jmp     loc_1802954E5
0x180294c2d  mov     rcx, [rbp+57h+var_68]
0x180294c31  mov     rdx, [rbp+57h+pv]
0x180294c35  add     rcx, r13
0x180294c38  add     rdx, 0FFFFFFFFFFFFFFFCh
0x180294c3c  mov     [rbp+57h+var_68], rcx
0x180294c40  lea     rdx, [rdx+rcx*4]
0x180294c44  test    rdx, rdx
0x180294c47  jz      short loc_180294C4C
0x180294c49  mov     [rdx], r13d
0x180294c4c  lea     r8, [rbp+57h+var_88]
0x180294c50  mov     [rbp+57h+var_90], r12
0x180294c54  lea     rdx, [rbp+57h+pv]
0x180294c58  mov     dword ptr [rbp+57h+var_88], 3
0x180294c5f  lea     rcx, [rbp+57h+var_90]
0x180294c63  call    ??$MakeAndInitialize@VCAdjacentDisplacementHandler@@V1@AEAV?$CCoSimpleArray@W4DISPLACEMENT_DIRECTION@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@W4DISPLACEMENT_DIRECTION@@@@@@W4SINGLE_TILE_ADJACENT_OPTION_FLAGS@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCAdjacentDisplacementHandler@@@WRL@Microsoft@@@012@AEAV?$CCoSimpleArray@W4DISPLACEMENT_DIRECTION@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@W4DISPLACEMENT_DIRECTION@@@@@@$$QEAW4SINGLE_TILE_ADJACENT_OPTION_FLAGS@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CAdjacentDisplacementHandler,CAdjacentDisplacementHandler,CCoSimpleArray<DISPLACEMENT_DIRECTION,4294967294,CSimpleArrayStandardCompareHelper<DISPLACEMENT_DIRECTION>> &,SINGLE_TILE_ADJACENT_OPTION_FLAGS>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<CAdjacentDisplacementHandler>>,CCoSimpleArray<DISPLACEMENT_DIRECTION,4294967294,CSimpleArrayStandardCompareHelper<DISPLACEMENT_DIRECTION>> &,SINGLE_TILE_ADJACENT_OPTION_FLAGS &&)
0x180294c68  mov     ebx, eax
0x180294c6a  test    eax, eax
0x180294c6c  jns     short loc_180294C94
0x180294c6e  mov     edx, 2Fh ; '/'; void *
0x180294c73  mov     rcx, [rbp+5Fh]; this
0x180294c77  lea     r8, aShellcommonShe_175; "shellcommon\\shell\\tiles\\sharedstartl"...
0x180294c7e  mov     r9d, ebx; char *
0x180294c81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180294c86  lea     rcx, [rbp+57h+var_90]
0x180294c8a  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x180294c8f  jmp     loc_1802954F8
0x180294c94  mov     rdx, [rbp+57h+var_90]; struct IItemLayoutDisplacementHandler *
0x180294c98  mov     rcx, r15; this
0x180294c9b  call    ?AddDisplacementHandler@CItemLayoutDisplacement@@QEAAJPEAUIItemLayoutDisplacementHandler@@@Z; CItemLayoutDisplacement::AddDisplacementHandler(IItemLayoutDisplacementHandler *)
0x180294ca0  mov     ebx, eax
0x180294ca2  test    eax, eax
0x180294ca4  jns     short loc_180294CAD
0x180294ca6  mov     edx, 30h ; '0'
0x180294cab  jmp     short loc_180294C73
0x180294cad  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180294cb4  mov     [rbp+57h+var_B0], r12d
0x180294cb8  mov     ecx, 30h ; '0'; unsigned __int64
0x180294cbd  mov     [rbp+57h+var_AC], 1Fh
0x180294cc5  mov     [rbp+57h+hMem], r12
0x180294cc9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180294cce  mov     rbx, rax
0x180294cd1  test    rax, rax
0x180294cd4  jz      short loc_180294CF6
0x180294cd6  mov     [rax+8], r12
0x180294cda  mov     [rax+10h], r12
0x180294cde  mov     [rax+18h], r12
0x180294ce2  mov     [rax+20h], r12
0x180294ce6  lea     rax, ??_7?$CRefCountedObject@V?$CCoSimpleArray@W4DISPLACEMENT_DIRECTION@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@W4DISPLACEMENT_DIRECTION@@@@@@@@6B@; const CRefCountedObject<CCoSimpleArray<DISPLACEMENT_DIRECTION,4294967294,CSimpleArrayStandardCompareHelper<DISPLACEMENT_DIRECTION>>>::`vftable'
0x180294ced  mov     [rbx], rax
0x180294cf0  mov     [rbx+28h], r12d
0x180294cf4  jmp     short loc_180294CF9
0x180294cf6  mov     rbx, r12
0x180294cf9  lea     rcx, [rbp+57h+var_98]
0x180294cfd  mov     [rbp+57h+var_98], rbx
0x180294d01  call    ?InternalAddRef@?$ComPtr@V?$CRefCountedObject@UChainLink@CItemLayoutChainDisplacement@@@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CRefCountedObject<CItemLayoutChainDisplacement::ChainLink>>::InternalAddRef(void)
0x180294d06  lea     rdi, [rbx+8]
0x180294d0a  mov     rdx, [rdi+8]
0x180294d0e  cmp     rdx, [rdi+18h]
0x180294d12  jnz     loc_180294DDE
0x180294d18  inc     rdx
0x180294d1b  mov     rcx, rdi
0x180294d1e  call    ?_EnsureCapacity@?$CTSimpleArray@W4DISPLACEMENT_DIRECTION@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@W4DISPLACEMENT_DIRECTION@@@@V?$CSimpleArrayStandardCompareHelper@W4DISPLACEMENT_DIRECTION@@@@V?$CSimpleArrayStandardMergeHelper@W4DISPLACEMENT_DIRECTION@@@@@@QEAAJ_K0@Z; CTSimpleArray<DISPLACEMENT_DIRECTION,4294967294,CTPolicyCoTaskMem<DISPLACEMENT_DIRECTION>,CSimpleArrayStandardCompareHelper<DISPLACEMENT_DIRECTION>,CSimpleArrayStandardMergeHelper<DISPLACEMENT_DIRECTION>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180294d23  mov     esi, eax
0x180294d25  test    eax, eax
0x180294d27  jns     loc_180294DDE
0x180294d2d  mov     rcx, [rbp+5Fh]; this
0x180294d31  lea     r8, aShellcommonShe_175; "shellcommon\\shell\\tiles\\sharedstartl"...
0x180294d38  mov     r9d, eax; char *
0x180294d3b  mov     edx, 36h ; '6'; void *
0x180294d40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180294d45  test    rbx, rbx
0x180294d48  jz      short loc_180294D59
0x180294d4a  mov     rdx, [rbx]
0x180294d4d  mov     rcx, rbx
0x180294d50  mov     rax, [rdx+10h]
0x180294d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180294d59  mov     rcx, [rbp+57h+hMem]
0x180294d5d  test    rcx, rcx
0x180294d60  jz      short loc_180294DBB
0x180294d62  mov     edx, dword ptr [rbp+57h+var_AC]
0x180294d65  mov     ebx, r12d
0x180294d68  test    edx, edx
0x180294d6a  jz      short loc_180294DB1
0x180294d6c  mov     eax, ebx
0x180294d6e  add     rax, rax
0x180294d71  cmp     [rcx+rax*8], r13d
0x180294d75  jnz     short loc_180294DAA
0x180294d77  mov     dword ptr [rcx+rax*8], 2
0x180294d7e  mov     rdx, [rcx+rax*8+8]
0x180294d83  test    rdx, rdx
0x180294d86  jz      short loc_180294D9C
0x180294d88  mov     [rcx+rax*8+8], r12
0x180294d8d  mov     rcx, rdx
0x180294d90  mov     rax, [rdx]
0x180294d93  mov     rax, [rax+10h]
0x180294d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180294d9c  add     dword ptr [rbp+57h+var_AC+4], r13d
0x180294da0  dec     [rbp+57h+var_B0]
0x180294da3  mov     rcx, [rbp+57h+hMem]; hMem
0x180294da7  mov     edx, dword ptr [rbp+57h+var_AC]
0x180294daa  add     ebx, r13d
0x180294dad  cmp     ebx, edx
0x180294daf  jb      short loc_180294D6C
0x180294db1  call    cs:__imp_LocalFree
0x180294db7  mov     [rbp+57h+hMem], r12
0x180294dbb  lea     rcx, [rbp+57h+var_90]
0x180294dbf  mov     [rbp+57h+var_B0], r12d
0x180294dc3  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x180294dc8  mov     rcx, [rbp+57h+pv]; pv
0x180294dcc  test    rcx, rcx
0x180294dcf  jz      short loc_180294DD7
0x180294dd1  call    cs:__imp_CoTaskMemFree
0x180294dd7  mov     eax, esi
0x180294dd9  jmp     loc_180295509
0x180294dde  add     [rdi+8], r13
0x180294de2  mov     rdx, [rdi+8]
0x180294de6  mov     rax, [rdi]
0x180294de9  lea     rcx, [rdx-1]
0x180294ded  lea     rcx, [rax+rcx*4]
0x180294df1  test    rcx, rcx
0x180294df4  jz      short loc_180294DFD
0x180294df6  mov     [rcx], r12d
0x180294df9  mov     rdx, [rdi+8]
0x180294dfd  cmp     rdx, [rdi+18h]
0x180294e01  jnz     loc_180294EAD
0x180294e07  inc     rdx
0x180294e0a  mov     rcx, rdi
0x180294e0d  call    ?_EnsureCapacity@?$CTSimpleArray@W4DISPLACEMENT_DIRECTION@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@W4DISPLACEMENT_DIRECTION@@@@V?$CSimpleArrayStandardCompareHelper@W4DISPLACEMENT_DIRECTION@@@@V?$CSimpleArrayStandardMergeHelper@W4DISPLACEMENT_DIRECTION@@@@@@QEAAJ_K0@Z; CTSimpleArray<DISPLACEMENT_DIRECTION,4294967294,CTPolicyCoTaskMem<DISPLACEMENT_DIRECTION>,CSimpleArrayStandardCompareHelper<DISPLACEMENT_DIRECTION>,CSimpleArrayStandardMergeHelper<DISPLACEMENT_DIRECTION>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180294e12  mov     esi, eax
0x180294e14  test    eax, eax
0x180294e16  jns     loc_180294EAD
0x180294e1c  mov     rcx, [rbp+5Fh]; this
0x180294e20  lea     r8, aShellcommonShe_175; "shellcommon\\shell\\tiles\\sharedstartl"...
0x180294e27  mov     r9d, eax; char *
0x180294e2a  mov     edx, 37h ; '7'; void *
0x180294e2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180294e34  test    rbx, rbx
0x180294e37  jz      short loc_180294E48
0x180294e39  mov     rcx, [rbx]
0x180294e3c  mov     rax, [rcx+10h]
0x180294e40  mov     rcx, rbx
0x180294e43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180294e48  mov     rcx, [rbp+57h+hMem]
0x180294e4c  test    rcx, rcx
0x180294e4f  jz      loc_180294DBB
0x180294e55  mov     edx, dword ptr [rbp+57h+var_AC]
0x180294e58  mov     ebx, r12d
0x180294e5b  test    edx, edx
0x180294e5d  jz      loc_180294DB1
0x180294e63  mov     eax, ebx
0x180294e65  add     rax, rax
0x180294e68  cmp     [rcx+rax*8], r13d
0x180294e6c  jnz     short loc_180294EA1
0x180294e6e  mov     dword ptr [rcx+rax*8], 2
0x180294e75  mov     rdx, [rcx+rax*8+8]
0x180294e7a  test    rdx, rdx
0x180294e7d  jz      short loc_180294E93
0x180294e7f  mov     [rcx+rax*8+8], r12
0x180294e84  mov     rcx, rdx
0x180294e87  mov     rax, [rdx]
0x180294e8a  mov     rax, [rax+10h]
0x180294e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180294e93  add     dword ptr [rbp+57h+var_AC+4], r13d
0x180294e97  dec     [rbp+57h+var_B0]
0x180294e9a  mov     rcx, [rbp+57h+hMem]
0x180294e9e  mov     edx, dword ptr [rbp+57h+var_AC]
0x180294ea1  add     ebx, r13d
0x180294ea4  cmp     ebx, edx
0x180294ea6  jb      short loc_180294E63
0x180294ea8  jmp     loc_180294DB1
0x180294ead  add     [rdi+8], r13
0x180294eb1  mov     rdx, [rdi+8]
0x180294eb5  mov     rax, [rdi]
0x180294eb8  dec     rdx
0x180294ebb  lea     rdx, [rax+rdx*4]
0x180294ebf  test    rdx, rdx
0x180294ec2  jz      short loc_180294EC7
0x180294ec4  mov     [rdx], r13d
0x180294ec7  lea     r9, [rbp+57h+var_98]
0x180294ecb  mov     dword ptr [rbp+57h+var_88], r12d
0x180294ecf  lea     r8, [rbp+57h+var_88]
0x180294ed3  lea     rcx, [rbp+57h+var_B0]
0x180294ed7  call    ?_AddUpdateItem@?$CSimpleHashTable@IV?$ComPtr@V?$CRefCountedObject@V?$CCoSimpleArray@W4DISPLACEMENT_DIRECTION@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@W4DISPLACEMENT_DIRECTION@@@@@@@@@WRL@Microsoft@@V?$CDefaultHashPolicy@I@@V?$CDefaultKeyCompare@I@@VCDefaultResizePolicy@@VCDefaultRehashPolicy@@@@AEAAJHAEBIAEBV?$ComPtr@V?$CRefCountedObject@V?$CCoSimpleArray@W4DISPLACEMENT_DIRECTION@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@W4DISPLACEMENT_DIRECTION@@@@@@@@@WRL@Microsoft@@PEAV234@@Z; CSimpleHashTable<uint,Microsoft::WRL::ComPtr<CRefCountedObject<CCoSimpleArray<DISPLACEMENT_DIRECTION,4294967294,CSimpleArrayStandardCompareHelper<DISPLACEMENT_DIRECTION>>>>,CDefaultHashPolicy<uint>,CDefaultKeyCompare<uint>,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(int,uint const &,Microsoft::WRL::ComPtr<CRefCountedObject<CCoSimpleArray<DISPLACEMENT_DIRECTION,4294967294,CSimpleArrayStandardCompareHelper<DISPLACEMENT_DIRECTION>>>> const &,Microsoft::WRL::ComPtr<CRefCountedObject<CCoSimpleArray<DISPLACEMENT_DIRECTION,4294967294,CSimpleArrayStandardCompareHelper<DISPLACEMENT_DIRECTION>>>> *)
0x180294edc  mov     edi, eax
0x180294ede  test    eax, eax
0x180294ee0  jns     loc_180294F97
0x180294ee6  mov     rcx, [rbp+5Fh]; this
0x180294eea  lea     r8, aShellcommonShe_175; "shellcommon\\shell\\tiles\\sharedstartl"...
0x180294ef1  mov     r9d, eax; char *
0x180294ef4  mov     edx, 38h ; '8'; void *
0x180294ef9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180294efe  test    rbx, rbx
0x180294f01  jz      short loc_180294F12
0x180294f03  mov     rcx, [rbx]
0x180294f06  mov     rax, [rcx+10h]
0x180294f0a  mov     rcx, rbx
0x180294f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180294f12  mov     rcx, [rbp+57h+hMem]
0x180294f16  test    rcx, rcx
0x180294f19  jz      short loc_180294F74
0x180294f1b  mov     edx, dword ptr [rbp+57h+var_AC]
0x180294f1e  mov     ebx, r12d
0x180294f21  test    edx, edx
0x180294f23  jz      short loc_180294F6A
0x180294f25  mov     eax, ebx
0x180294f27  add     rax, rax
0x180294f2a  cmp     [rcx+rax*8], r13d
0x180294f2e  jnz     short loc_180294F63
0x180294f30  mov     dword ptr [rcx+rax*8], 2
0x180294f37  mov     rdx, [rcx+rax*8+8]
0x180294f3c  test    rdx, rdx
0x180294f3f  jz      short loc_180294F55
0x180294f41  mov     [rcx+rax*8+8], r12
0x180294f46  mov     rcx, rdx
0x180294f49  mov     rax, [rdx]
0x180294f4c  mov     rax, [rax+10h]
0x180294f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180294f55  add     dword ptr [rbp+57h+var_AC+4], r13d
0x180294f59  dec     [rbp+57h+var_B0]
0x180294f5c  mov     rcx, [rbp+57h+hMem]; hMem
0x180294f60  mov     edx, dword ptr [rbp+57h+var_AC]
0x180294f63  add     ebx, r13d
0x180294f66  cmp     ebx, edx
0x180294f68  jb      short loc_180294F25
0x180294f6a  call    cs:__imp_LocalFree
0x180294f70  mov     [rbp+57h+hMem], r12
  ... truncated ...
```
