# CDBFolder::BindToObject(_ITEMIDLIST_RELATIVE const *,IBindCtx *,_GUID const &,void * *)

- ea: `0x18001a640`
- end: `0x18001b3dc`
- name: `?BindToObject@CDBFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z`
- size: `3484`
- prototype: `__int64 __fastcall(CDBFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, struct IBindCtx *, const struct _GUID *, void **ppv)`
- caller_count: `8`
- callee_count: `27`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180008aa0`
- `0x18000bd60`
- `0x1800171dc`
- `0x18001a200`
- `0x18001a640`
- `0x18006000c`
- `0x180084320`
- `0x18008cb30`

## callees

- `0x1800074dc`
- `0x1800082a0`
- `0x18000a350`
- `0x18000c420`
- `0x18000c910`
- `0x1800184e0`
- `0x180019b60`
- `0x18001a050`
- `0x18001a16c`
- `0x18001a640`
- `0x18001b544`
- `0x18001b580`
- `0x18001c700`
- `0x18001c870`
- `0x18001c9a8`
- `0x18001c9e0`
- `0x18001ca40`
- `0x180043bcc`
- `0x180057d14`
- `0x180063a68`
- `0x180071dc0`
- `0x180071df0`
- `0x180072cdc`
- `0x180083098`
- `0x180088fa0`
- `0x18008ae74`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x18001aa2c`
- `SHCORE!IUnknown_Set` at `0x18001acc0`
- `SHCORE!IUnknown_Set` at `0x18001ad5b`
- `SHCORE!IUnknown_Set` at `0x18001aa2c`
- `SHCORE!IUnknown_Set` at `0x18001acc0`
- `SHCORE!IUnknown_Set` at `0x18001ad5b`
- `Windows.Storage!ILFindLastID` at `0x18001a936`
- `Windows.Storage!ILFindLastID` at `0x18001ab04`
- `Windows.Storage!ILFindLastID` at `0x18001a936`
- `Windows.Storage!ILFindLastID` at `0x18001ab04`
- `Windows.Storage!ILFree` at `0x18001a9ae`
- `Windows.Storage!ILFree` at `0x18001b01d`
- `Windows.Storage!ILFree` at `0x18001b3d1`
- `Windows.Storage!ILFree` at `0x18001a9ae`
- `Windows.Storage!ILFree` at `0x18001b01d`
- `Windows.Storage!ILFree` at `0x18001b3d1`
- `Windows.Storage!SHCreateItemWithParent` at `0x18001b07e`
- `Windows.Storage!SHCreateItemWithParent` at `0x18001b07e`
- `Windows.Storage!ILClone` at `0x18001b117`
- `Windows.Storage!ILClone` at `0x18001b117`
- `Windows.Storage!ILCloneFirst` at `0x18001a685`
- `Windows.Storage!ILCloneFirst` at `0x18001aa16`
- `Windows.Storage!ILCloneFirst` at `0x18001ad00`
- `Windows.Storage!ILCloneFirst` at `0x18001a685`
- `Windows.Storage!ILCloneFirst` at `0x18001aa16`
- `Windows.Storage!ILCloneFirst` at `0x18001ad00`
- `Windows.Storage!__imp_SHCreateRelatedItemFromIDList` at `0x18001b3c6`
- `Windows.Storage!__imp_SHCreateRelatedItemFromIDList` at `0x18001b3c6`
- `Windows.Storage!__imp_SHCreateRelatedItemWithParent` at `0x18001ae54`
- `Windows.Storage!__imp_SHCreateRelatedItemWithParent` at `0x18001afff`
- `Windows.Storage!__imp_SHCreateRelatedItemWithParent` at `0x18001ae54`
- `Windows.Storage!__imp_SHCreateRelatedItemWithParent` at `0x18001afff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ad4e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ad4e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ad68`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ad68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a83e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a83e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a925`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a925`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001a915`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001ac13`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001a915`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001ac13`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18001aa62`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18001ad2e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18001ad7e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18001b391`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18001aa62`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18001ad2e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18001ad7e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18001b391`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x18001a7f1`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x18001a7f1`
- `PROPSYS!PropVariantToInt32` at `0x18001ac06`
- `PROPSYS!PropVariantToInt32` at `0x18001ac06`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18001b1ea`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18001b1ea`

## pseudocode

```c
__int64 __fastcall CDBFolder::BindToObject(
        const ITEMIDLIST **this,
        const ITEMIDLIST *a2,
        IUnknown *a3,
        struct _GUID *a4,
        void **ppv)
{
  CDBFolder *v9; // rcx
  LPITEMIDLIST v10; // r15
  _WORD *v11; // r14
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  IUnknown *v17; // r9
  unsigned __int64 cb; // rax
  HRESULT v19; // ebx
  __int64 v20; // rdi
  HRESULT FilterConditionForChild; // edi
  __int64 v22; // r14
  bool v23; // zf
  IUnknown *v24; // rax
  __int64 v25; // rdi
  IUnknown *v26; // rcx
  IUnknown *v27; // rdi
  struct IUnknownVtbl *lpVtbl; // rax
  LPITEMIDLIST ID; // rax
  LPITEMIDLIST v30; // r8
  unsigned __int64 v31; // rax
  __int64 v32; // rax
  ITEMIDLIST *v33; // rax
  int PreviewItem; // eax
  int HandlerFromTarget; // ebx
  CQueryPropStoreFactory *v37; // rax
  CQueryPropStoreFactory *v38; // rdi
  LPITEMIDLIST v39; // rax
  unsigned int v40; // edx
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  LPITEMIDLIST v44; // rax
  LPITEMIDLIST v45; // r8
  unsigned __int64 v46; // rax
  __int64 v47; // rax
  ITEMIDLIST *v48; // r8
  int v49; // eax
  LONG v50; // ecx
  struct IUnknownVtbl *v51; // rax
  struct IUnknownVtbl *v52; // rax
  IUnknown *v53; // r13
  CQueryResult *v54; // rax
  CQueryResult *v55; // rax
  CQueryResult *v56; // r14
  CChildId *v57; // rax
  CChildId *v58; // r13
  LPITEMIDLIST v59; // rax
  IUnknown *v60; // rbx
  __int64 v61; // rax
  __int64 v62; // rax
  int v63; // r14d
  __int64 v64; // r8
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  unsigned int v68; // r14d
  __int64 v69; // rax
  struct IUnknown *v70; // rdi
  __int64 v71; // rax
  const ITEMIDLIST *v72; // rcx
  LPITEMIDLIST v73; // rax
  int v74; // ecx
  struct _ITEMIDLIST_RELATIVE *v75; // r14
  CDBFolderLinkResolver *v76; // rax
  CDBFolderLinkResolver *v77; // rax
  CDBFolderLinkResolver *v78; // rdi
  int ppvItem; // [rsp+20h] [rbp-C1h]
  IUnknown *v80; // [rsp+40h] [rbp-A1h] BYREF
  IUnknown *punk; // [rsp+48h] [rbp-99h] BYREF
  LONG plRet; // [rsp+50h] [rbp-91h] BYREF
  void *v83; // [rsp+58h] [rbp-89h] BYREF
  PROPVARIANT pvar[2]; // [rsp+60h] [rbp-81h] BYREF
  __int128 v85; // [rsp+70h] [rbp-71h]
  IUnknown *v86; // [rsp+80h] [rbp-61h]
  _DWORD Src[2]; // [rsp+90h] [rbp-51h] BYREF
  __int128 v88; // [rsp+98h] [rbp-49h]
  __int128 v89; // [rsp+A8h] [rbp-39h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+57h]

  punk = a3;
  *ppv = 0;
  v10 = ILCloneFirst(a2);
  if ( !v10 )
    return 2147942414LL;
  v11 = (USHORT *)((char *)&a2->mkid.cb + a2->mkid.cb);
  if ( v11 && *v11 )
  {
    v80 = 0;
    HandlerFromTarget = CDBFolder::BindToObject(
                          (CDBFolder *)this,
                          (const struct _ITEMIDLIST_RELATIVE *)v10,
                          0,
                          &GUID_000214e6_0000_0000_c000_000000000046,
                          (void **)&v80);
    if ( HandlerFromTarget >= 0 )
    {
      HandlerFromTarget = ((__int64 (__fastcall *)(IUnknown *, _WORD *, IUnknown *, struct _GUID *, void **))v80->lpVtbl[1].Release)(
                            v80,
                            v11,
                            punk,
                            a4,
                            ppv);
      ((void (__fastcall *)(IUnknown *))v80->lpVtbl->Release)(v80);
    }
    goto LABEL_45;
  }
  v12 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IPropertyStoreFactory.Data1;
  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IPropertyStoreFactory.Data1 )
    v12 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IPropertyStoreFactory.Data4;
  if ( !v12 )
  {
    *ppv = 0;
    HandlerFromTarget = -2147024882;
    v37 = (CQueryPropStoreFactory *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    v86 = (IUnknown *)v37;
    if ( v37 )
    {
      v38 = CQueryPropStoreFactory::CQueryPropStoreFactory(v37);
      if ( v38 )
      {
        v39 = ILCloneFirst(v10);
        *((_QWORD *)v38 + 5) = v39;
        if ( v39 )
        {
          IUnknown_Set((IUnknown **)v38 + 3, (IUnknown *)this);
          HandlerFromTarget = (*(__int64 (__fastcall **)(const ITEMIDLIST **, GUID *, __int64))&(*this)->mkid.cb)(
                                this,
                                &GUID_1af4b01d_4a4a_489c_8f9f_243612300d24,
                                (__int64)v38 + 32);
          if ( HandlerFromTarget >= 0 )
            HandlerFromTarget = QISearch(v38, &stru_1800EBB90, a4, ppv);
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v38 + 4, 0xFFFFFFFF) == 1 )
          CQueryPropStoreFactory::`scalar deleting destructor'(v38, v40);
      }
    }
    goto LABEL_45;
  }
  v13 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IPropertyStoreCache.Data1;
  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IPropertyStoreCache.Data1 )
    v13 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IPropertyStoreCache.Data4;
  if ( v13 )
  {
    v14 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IPropertyStore.Data1;
    if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IPropertyStore.Data1 )
      v14 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IPropertyStore.Data4;
    if ( !v14 )
      goto LABEL_43;
    v15 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IPropertySetStorage.Data1;
    if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IPropertySetStorage.Data1 )
      v15 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IPropertySetStorage.Data4;
    if ( v15 )
    {
      v16 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&GUID_656c5e34_f857_40d6_9d5c_9c5e6873e160.Data1;
      if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_656c5e34_f857_40d6_9d5c_9c5e6873e160.Data1 )
        v16 = *(_QWORD *)a4->Data4 - *(_QWORD *)GUID_656c5e34_f857_40d6_9d5c_9c5e6873e160.Data4;
      if ( !v16 )
      {
        plRet = 1;
        *ppv = 0;
        v17 = 0;
        cb = v10->mkid.cb;
        v19 = -2147024809;
        punk = 0;
        v80 = 0;
        if ( (unsigned int)cb >= 0x2E && *(_DWORD *)&v10[2].mkid.cb == 269752705 )
        {
          v20 = *(unsigned __int16 *)((char *)&v10[3].mkid.cb + 1);
          if ( cb >= v20 + 46 && (_WORD)v20 && v10 != (LPITEMIDLIST)-46LL )
          {
            v83 = 0;
            v19 = PSCreateMemoryPropertyStore(&GUID_e318ad57_0aa0_450f_aca5_6fab7103d917, &v83);
            if ( v19 >= 0 )
            {
              v19 = (*(__int64 (__fastcall **)(void *, __int64, _QWORD))(*(_QWORD *)v83 + 32LL))(
                      v83,
                      (__int64)&v10[15].mkid.cb + 1,
                      (unsigned int)v20);
              if ( v19 >= 0 )
              {
                v19 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)v83 + 24LL))(v83, 1);
                if ( v19 >= 0 )
                  v19 = (**(__int64 (__fastcall ***)(void *, GUID *, IUnknown **))v83)(
                          v83,
                          &GUID_e318ad57_0aa0_450f_aca5_6fab7103d917,
                          &v80);
              }
              (*(void (__fastcall **)(void *))(*(_QWORD *)v83 + 16LL))(v83);
              if ( v19 >= 0 )
              {
                ((void (__fastcall *)(IUnknown *, _QWORD))v80->lpVtbl[1].QueryInterface)(v80, 0);
                v19 = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))v80->lpVtbl->QueryInterface)(
                        v80,
                        &GUID_3017056d_9a91_4e90_937d_746c72abbf4f,
                        &punk);
                ((void (__fastcall *)(IUnknown *))v80->lpVtbl->Release)(v80);
              }
            }
            v17 = punk;
          }
        }
        if ( v19 < 0 )
        {
          FilterConditionForChild = v19;
          goto LABEL_93;
        }
        LODWORD(v83) = 0;
        if ( ((int (__fastcall *)(IUnknown *, const struct _tagpropertykey *, void **))v17->lpVtbl[2].Release)(
               v17,
               &PKEY_ResultSourceId,
               &v83) >= 0
          && !(_DWORD)v83 )
        {
          goto LABEL_75;
        }
        v86 = punk;
        FilterConditionForChild = SHStringFromGUIDW(&GUID_1685d4ab_a51b_4af1_a4e5_cee87002431d, Src, 39);
        if ( FilterConditionForChild < 0 )
        {
LABEL_100:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x95,
            (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
            (const char *)(unsigned int)FilterConditionForChild,
            ppvItem);
          goto LABEL_92;
        }
        v22 = -1;
        do
          v23 = *((_WORD *)Src + ++v22) == 0;
        while ( !v23 );
        v80 = 0;
        if ( !is_mul_ok(v22 + 11, 2u) )
        {
          FilterConditionForChild = -2147024362;
          goto LABEL_100;
        }
        v24 = (IUnknown *)CoTaskMemAlloc(2 * (v22 + 11));
        v80 = v24;
        if ( !v24 )
        {
          FilterConditionForChild = -2147024882;
          goto LABEL_100;
        }
        v25 = 2 * v22;
        memcpy_0(v24, Src, 2 * v22);
        v26 = v80;
        *((_WORD *)&v80->lpVtbl + v22) = 46;
        *(_OWORD *)((char *)&v26->lpVtbl + v25 + 2) = *(_OWORD *)L"Merge Any";
        *(_WORD *)((char *)&v26[2].lpVtbl + v25 + 2) = aMergeAny[8];
        v27 = v86;
        *((_WORD *)&v26[2].lpVtbl + v22 + 2) = 0;
        *(_QWORD *)&v85 = 0;
        *(_OWORD *)pvar = 0;
        LOWORD(pvar[0]) = 31;
        lpVtbl = v27->lpVtbl;
        pvar[1] = v26;
        v80 = 0;
        if ( ((int (__fastcall *)(IUnknown *, GUID *, IUnknown **))lpVtbl->QueryInterface)(
               v27,
               &GUID_388cec0d_4ef6_4015_a135_d96527fd84e2,
               &v80) < 0 )
        {
          FilterConditionForChild = ((__int64 (__fastcall *)(IUnknown *, const struct _tagpropertykey *, PROPVARIANT *))v27->lpVtbl[2].QueryInterface)(
                                      v27,
                                      &PKEY_ResultSourceId,
                                      pvar);
        }
        else
        {
          FilterConditionForChild = ((__int64 (__fastcall *)(IUnknown *, const struct _tagpropertykey *, PROPVARIANT *, _QWORD))v80->lpVtbl[2].Release)(
                                      v80,
                                      &PKEY_ResultSourceId,
                                      pvar,
                                      0);
          ((void (__fastcall *)(IUnknown *))v80->lpVtbl->Release)(v80);
        }
        PropVariantClear(pvar);
        if ( FilterConditionForChild < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7A,
            (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
            (const char *)(unsigned int)FilterConditionForChild,
            ppvItem);
        CoTaskMemFree(0);
        if ( FilterConditionForChild < 0 )
          goto LABEL_100;
        ID = ILFindLastID(v10);
        v30 = ID;
        if ( ID
          && (v31 = ID->mkid.cb, (unsigned int)v31 >= 0x2E)
          && *(_DWORD *)&v30[2].mkid.cb == 269752705
          && v31 >= (unsigned __int64)*(unsigned __int16 *)((char *)&v30[3].mkid.cb + 1) + 46
          && v30 != (LPITEMIDLIST)-14LL )
        {
          v33 = v30 + 14;
        }
        else
        {
          v32 = ILFindHiddenIDOn(v10, 3203334163LL);
          if ( !v32 )
            goto LABEL_74;
          v33 = (ITEMIDLIST *)(v32 + 36);
        }
        v49 = *(_DWORD *)&v33->mkid.cb;
        if ( (v49 & 2) != 0 )
        {
          plRet = 4;
        }
        else if ( (v49 & 4) != 0 )
        {
          plRet = 2;
        }
        else
        {
          v50 = 1;
          if ( (v49 & 8) != 0 )
            v50 = 3;
          plRet = v50;
        }
LABEL_74:
        *(_QWORD *)&v85 = 0;
        *(_OWORD *)pvar = 0;
        LODWORD(pvar[1]) = plRet;
        v51 = punk->lpVtbl;
        LOWORD(pvar[0]) = 3;
        FilterConditionForChild = ((__int64 (__fastcall *)(IUnknown *, __int64 *, PROPVARIANT *))v51[2].QueryInterface)(
                                    punk,
                                    &PKEY_ResultType,
                                    pvar);
        if ( FilterConditionForChild < 0 )
        {
LABEL_92:
          ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
LABEL_93:
          HandlerFromTarget = FilterConditionForChild;
          goto LABEL_45;
        }
LABEL_75:
        plRet = 0;
        *(_QWORD *)&v85 = 0;
        v52 = punk->lpVtbl;
        *(_OWORD *)pvar = 0;
        FilterConditionForChild = ((__int64 (__fastcall *)(IUnknown *, __int64 *, PROPVARIANT *))v52[1].Release)(
                                    punk,
                                    &PKEY_ResultType,
                                    pvar);
        if ( FilterConditionForChild >= 0 )
        {
          if ( LOWORD(pvar[0]) )
            FilterConditionForChild = PropVariantToInt32(pvar, &plRet);
          else
            FilterConditionForChild = -2147023728;
          PropVariantClear(pvar);
        }
        if ( FilterConditionForChild >= 0 )
        {
          if ( plRet == 1
            || (v80 = 0,
                FilterConditionForChild = CDBFolder::GetFilterConditionForChild(
                                            (CDBFolder *)(this + 23),
                                            (const struct _ITEMID_CHILD *)v10,
                                            &GUID_fca2857d_1760_4ad3_8c63_c9b602fcbaea,
                                            (void **)&v80),
                FilterConditionForChild >= 0)
            && (FilterConditionForChild = SetFilterConditionOnGroupStore(punk, v80),
                ((void (__fastcall *)(IUnknown *))v80->lpVtbl->Release)(v80),
                FilterConditionForChild >= 0) )
          {
            v53 = punk;
            *ppv = 0;
            FilterConditionForChild = -2147024882;
            v54 = (CQueryResult *)operator new(0xD8u, (const struct std::nothrow_t *)&std::nothrow);
            v86 = (IUnknown *)v54;
            if ( !v54 )
              goto LABEL_143;
            v55 = CQueryResult::CQueryResult(v54);
            v56 = v55;
            if ( !v55 )
              goto LABEL_143;
            IUnknown_Set((IUnknown **)v55 + 13, v53);
            v80 = 0;
            v57 = (CChildId *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
            if ( v57 )
            {
              v58 = CChildId::CChildId(v57);
              if ( v58 )
              {
                v59 = ILCloneFirst(v10);
                *((_QWORD *)v58 + 2) = v59;
                if ( v59 )
                {
                  FilterConditionForChild = QISearch(
                                              v58,
                                              &`CChildId::QueryInterface'::`2'::qit,
                                              &GUID_c412bf5b_91ea_4904_b34a_855504fbbf0b,
                                              (void **)&v80);
                  CChildId::Release(v58);
                  if ( FilterConditionForChild >= 0 )
                  {
                    v60 = v80;
                    AcquireSRWLockExclusive((PSRWLOCK)v56 + 21);
                    IUnknown_Set((IUnknown **)v56 + 14, v60);
                    ReleaseSRWLockExclusive((PSRWLOCK)v56 + 21);
                    FilterConditionForChild = QISearch(v56, &`CQueryResult::QueryInterface'::`2'::qit, a4, ppv);
                    ((void (__fastcall *)(IUnknown *))v80->lpVtbl->Release)(v80);
                  }
                }
                else
                {
                  FilterConditionForChild = -2147024882;
                  CChildId::Release(v58);
                }
              }
            }
            CQueryResult::Release(v56);
            if ( FilterConditionForChild < 0 )
LABEL_143:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x44D,
                (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
                (const char *)(unsigned int)FilterConditionForChild,
                ppvItem);
          }
        }
        goto LABEL_92;
      }
      v41 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IFilterCondition.Data1;
      if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IFilterCondition.Data1 )
        v41 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IFilterCondition.Data4;
      if ( v41 )
      {
        v42 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IDisplayItem.Data1;
        if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IDisplayItem.Data1 )
          v42 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IDisplayItem.Data4;
        if ( v42 )
        {
          v43 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IResolveShellLink.Data1;
          if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IResolveShellLink.Data1 )
            v43 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IResolveShellLink.Data4;
          if ( !v43 )
          {
            v76 = (CDBFolderLinkResolver *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
            v86 = (IUnknown *)v76;
            if ( v76 && (v77 = CDBFolderLinkResolver::CDBFolderLinkResolver(v76), (v78 = v77) != 0) )
            {
              HandlerFromTarget = QISearch(v77, &`CDBFolderLinkResolver::QueryInterface'::`2'::qit, a4, ppv);
              CDBFolderLinkResolver::Release(v78);
            }
            else
            {
              HandlerFromTarget = -2147024882;
            }
            goto LABEL_45;
          }
          v44 = ILFindLastID(v10);
          v45 = v44;
          if ( v44
            && (v46 = v44->mkid.cb, (unsigned int)v46 >= 0x2E)
            && *(_DWORD *)&v45[2].mkid.cb == 269752705
            && v46 >= (unsigned __int64)*(unsigned __int16 *)((char *)&v45[3].mkid.cb + 1) + 46
            && v45 != (LPITEMIDLIST)-14LL )
          {
            v48 = v45 + 14;
          }
          else
          {
            v47 = ILFindHiddenIDOn(v10, 3203334163LL);
            if ( !v47 )
            {
LABEL_102:
              v61 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_ITransferMediumItem.Data1;
              if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_ITransferMediumItem.Data1 )
                v61 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_ITransferMediumItem.Data4;
              if ( !v61 )
              {
                HandlerFromTarget = -2147467259;
                goto LABEL_45;
              }
              v62 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IPreviewItem.Data1;
              if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IPreviewItem.Data1 )
                v62 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IPreviewItem.Data4;
              if ( v62 )
              {
                v63 = 0;
                v80 = 0;
                if ( a3
                  && ((int (__fastcall *)(IUnknown *, const wchar_t *, IUnknown **))a3->lpVtbl[3].AddRef)(
                       a3,
                       L"Full Parse Bind",
                       &v80) >= 0 )
                {
                  v63 = 1;
                  ((void (__fastcall *)(IUnknown *))v80->lpVtbl->Release)(v80);
                }
                v64 = (unsigned int)(v63 + 1);
                v65 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IIdentityName.Data1;
                if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IIdentityName.Data1 )
                  v65 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IIdentityName.Data4;
                if ( !v65 )
                  goto LABEL_117;
                v66 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IDelegateItem.Data1;
                if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IDelegateItem.Data1 )
                  v66 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IDelegateItem.Data4;
                if ( v66 )
                {
                  HandlerFromTarget = CDBFolder::_GetHandlerFromTarget(
                                        (struct IShellFolder *)this,
                                        v10,
                                        2,
                                        0,
                                        (struct IBindCtx *)a3,
                                        v64,
                                        a4,
                                        ppv);
                  if ( HandlerFromTarget >= 0 )
                  {
                    v70 = (struct IUnknown *)*ppv;
                    v80 = 0;
                    HandlerFromTarget = SHCreateItemWithParent(
                                          0,
                                          (IShellFolder *)this,
                                          v10,
                                          &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                          (void **)&v80);
                    if ( HandlerFromTarget >= 0 )
                    {
                      HandlerFromTarget = RelocateFolder(v70, (struct IShellItem *)v80, (struct IBindCtx *)punk);
                      ((void (__fastcall *)(IUnknown *))v80->lpVtbl->Release)(v80);
                    }
                    if ( HandlerFromTarget < 0 )
                    {
                      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*ppv + 16LL))(*ppv);
                      *ppv = 0;
                    }
                  }
                }
                else
                {
LABEL_117:
                  v67 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_ITransferSource.Data1;
                  v23 = *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_ITransferSource.Data1;
                  v80 = 0;
                  punk = 0;
                  if ( v23 )
                    v67 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_ITransferSource.Data4;
                  if ( !v67 )
                    goto LABEL_123;
                  v68 = -1;
                  v69 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_ITransferSource2.Data1;
                  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_ITransferSource2.Data1 )
                    v69 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_ITransferSource2.Data4;
                  if ( !v69 )
LABEL_123:
                    v68 = 1;
                  HandlerFromTarget = CDBFolder::DelegateBindToParent(
                                        this + 23,
                                        v10,
                                        v64,
                                        v68,
                                        &GUID_000214e6_0000_0000_c000_000000000046,
                                        &v80,
                                        &punk);
                  if ( HandlerFromTarget >= 0 )
                  {
                    HandlerFromTarget = SHCreateRelatedItemWithParent(v80, punk, a4, ppv);
                    ((void (__fastcall *)(IUnknown *))v80->lpVtbl->Release)(v80);
                    ILFree((LPITEMIDLIST)punk);
                  }
                }
                goto LABEL_45;
              }
              PreviewItem = CDBFolder::_CreatePreviewItem((IShellFolder *)this, v10, a4, ppv);
              goto LABEL_44;
            }
            v48 = (ITEMIDLIST *)(v47 + 36);
          }
          if ( (v48->mkid.cb & 1) == 0 )
            goto LABEL_102;
          v71 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IViewStateIdentityItem.Data1;
          if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IViewStateIdentityItem.Data1 )
            v71 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IViewStateIdentityItem.Data4;
          if ( !v71 )
          {
            v72 = this[28];
            if ( v72 )
            {
              v73 = ILClone(v72);
              v74 = 0;
              v75 = (struct _ITEMIDLIST_RELATIVE *)v73;
              if ( !v73 )
                v74 = -2147024882;
              HandlerFromTarget = v74;
            }
            else
            {
              v75 = 0;
              HandlerFromTarget = -2147024809;
            }
            if ( HandlerFromTarget >= 0 )
            {
              *(_OWORD *)pvar = 0;
              v85 = 0;
              if ( (int)GetTopViewKeyFromIDListHiddenData(
                          (const struct _ITEMIDLIST_RELATIVE *)a2,
                          (struct TOPVIEWKEY *)pvar) < 0
                || (ILRemoveHiddenID(v75, 3203334169LL),
                    Src[0] = 40,
                    v88 = *(_OWORD *)pvar,
                    Src[1] = -1091633127,
                    v89 = v85,
                    (v75 = ILAppendHiddenID(v75, (const struct _HIDDENITEMID *)Src)) != 0) )
              {
                HandlerFromTarget = SHCreateRelatedItemFromIDList(v75, a4, ppv);
              }
              else
              {
                HandlerFromTarget = -2147467259;
              }
              ILFree((LPITEMIDLIST)v75);
            }
            goto LABEL_45;
          }
          PreviewItem = CDBFolder::_BindContainer(
                          (CDBFolder *)this,
                          (const struct _ITEMID_CHILD *)v10,
                          (struct IBindCtx *)a3,
                          a4,
                          ppv);
        }
        else
        {
          PreviewItem = SHCreateRelatedItemWithParent(this, v10, a4, ppv);
        }
      }
      else
      {
        PreviewItem = CDBFolder::GetFilterConditionForChild(
                        (CDBFolder *)(this + 23),
                        (const struct _ITEMID_CHILD *)v10,
                        a4,
                        ppv);
      }
    }
    else
    {
LABEL_43:
      PreviewItem = CDBFolder::_BindToPropertyStore(
                      (CDBFolder *)this,
                      (const struct _ITEMID_CHILD *)v10,
                      (struct IBindCtx *)a3,
                      a4,
                      ppv);
    }
  }
  else
  {
    PreviewItem = CDBFolder::_BindToPropStoreCache(v9, (const struct _ITEMID_CHILD *)v10, a4, ppv);
  }
LABEL_44:
  HandlerFromTarget = PreviewItem;
LABEL_45:
  ILFree(v10);
  return (unsigned int)HandlerFromTarget;
}

```

## disassembly

```asm
0x18001a640  push    rbp
0x18001a642  push    rbx
0x18001a643  push    rsi
0x18001a644  push    rdi
0x18001a645  push    r12
0x18001a647  push    r13
0x18001a649  push    r15
0x18001a64b  lea     rbp, [rsp-1Fh]
0x18001a650  sub     rsp, 100h
0x18001a657  mov     rax, cs:__security_cookie
0x18001a65e  xor     rax, rsp
0x18001a661  mov     [rbp+4Fh+var_50], rax
0x18001a665  mov     r12, [rbp+4Fh+ppv]
0x18001a669  mov     rbx, r8
0x18001a66c  mov     r13, rcx
0x18001a66f  mov     [rsp+130h+punk], rbx
0x18001a674  mov     rcx, rdx; pidl
0x18001a677  mov     rsi, r9
0x18001a67a  mov     rdi, rdx
0x18001a67d  mov     qword ptr [r12], 0
0x18001a685  call    cs:__imp_ILCloneFirst
0x18001a68b  mov     r15, rax
0x18001a68e  test    rax, rax
0x18001a691  jz      loc_18001A98C
0x18001a697  mov     [rsp+130h+var_38], r14
0x18001a69f  movzx   r14d, word ptr [rdi]
0x18001a6a3  add     r14, rdi
0x18001a6a6  jz      short loc_18001A6B3
0x18001a6a8  cmp     word ptr [r14], 0
0x18001a6ad  jnz     loc_18001ADC3
0x18001a6b3  mov     rax, [rsi]
0x18001a6b6  sub     rax, qword ptr cs:IID_IPropertyStoreFactory.Data1
0x18001a6bd  jnz     short loc_18001A6CA
0x18001a6bf  mov     rax, [rsi+8]
0x18001a6c3  sub     rax, qword ptr cs:IID_IPropertyStoreFactory.Data4
0x18001a6ca  test    rax, rax
0x18001a6cd  jz      loc_18001A9DC
0x18001a6d3  mov     rax, [rsi]
0x18001a6d6  sub     rax, qword ptr cs:IID_IPropertyStoreCache.Data1
0x18001a6dd  jnz     short loc_18001A6EA
0x18001a6df  mov     rax, [rsi+8]
0x18001a6e3  sub     rax, qword ptr cs:IID_IPropertyStoreCache.Data4
0x18001a6ea  test    rax, rax
0x18001a6ed  jz      loc_18001AA8E
0x18001a6f3  mov     rax, [rsi]
0x18001a6f6  sub     rax, qword ptr cs:IID_IPropertyStore.Data1
0x18001a6fd  jnz     short loc_18001A70A
0x18001a6ff  mov     rax, [rsi+8]
0x18001a703  sub     rax, qword ptr cs:IID_IPropertyStore.Data4
0x18001a70a  test    rax, rax
0x18001a70d  jz      loc_18001A993
0x18001a713  mov     rax, [rsi]
0x18001a716  sub     rax, qword ptr cs:IID_IPropertySetStorage.Data1
0x18001a71d  jnz     short loc_18001A72A
0x18001a71f  mov     rax, [rsi+8]
0x18001a723  sub     rax, qword ptr cs:IID_IPropertySetStorage.Data4
0x18001a72a  test    rax, rax
0x18001a72d  jz      loc_18001A993
0x18001a733  mov     rax, [rsi]
0x18001a736  sub     rax, qword ptr cs:_GUID_656c5e34_f857_40d6_9d5c_9c5e6873e160.Data1
0x18001a73d  jnz     short loc_18001A74A
0x18001a73f  mov     rax, [rsi+8]
0x18001a743  sub     rax, qword ptr cs:_GUID_656c5e34_f857_40d6_9d5c_9c5e6873e160.Data4
0x18001a74a  test    rax, rax
0x18001a74d  jnz     loc_18001AAA1
0x18001a753  xor     edx, edx
0x18001a755  mov     [rsp+130h+plRet], 1
0x18001a75d  mov     [r12], rdx
0x18001a761  mov     r9d, edx
0x18001a764  movzx   eax, word ptr [r15]
0x18001a768  mov     ebx, 80070057h
0x18001a76d  mov     [rsp+130h+punk], rdx
0x18001a772  mov     [rsp+130h+var_F0], rdx
0x18001a777  cmp     eax, 2Eh ; '.'
0x18001a77a  jb      short loc_18001A798
0x18001a77c  cmp     dword ptr [r15+6], 10141981h
0x18001a784  jnz     short loc_18001A798
0x18001a786  movzx   edi, word ptr [r15+0Ah]
0x18001a78b  lea     rcx, [rdi+2Eh]
0x18001a78f  cmp     rax, rcx
0x18001a792  jnb     loc_18001B1C3
0x18001a798  test    ebx, ebx
0x18001a79a  js      loc_18001ADBF
0x18001a7a0  xor     r14d, r14d
0x18001a7a3  lea     r8, [rsp+130h+var_D8]
0x18001a7a8  mov     dword ptr [rsp+130h+var_D8], r14d
0x18001a7ad  lea     rdx, PKEY_ResultSourceId
0x18001a7b4  mov     rax, [r9]
0x18001a7b7  mov     rcx, r9
0x18001a7ba  mov     rax, [rax+40h]
0x18001a7be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7c3  mov     ebx, 8007000Eh
0x18001a7c8  test    eax, eax
0x18001a7ca  js      short loc_18001A7D7
0x18001a7cc  cmp     dword ptr [rsp+130h+var_D8], r14d
0x18001a7d1  jz      loc_18001ABBA
0x18001a7d7  mov     rax, [rsp+130h+punk]
0x18001a7dc  lea     rdx, [rbp+4Fh+Src]
0x18001a7e0  mov     r8d, 27h ; '''
0x18001a7e6  mov     [rbp+4Fh+var_B0], rax
0x18001a7ea  lea     rcx, _GUID_1685d4ab_a51b_4af1_a4e5_cee87002431d
0x18001a7f1  call    cs:__imp_SHStringFromGUIDW
0x18001a7f7  mov     edi, eax
0x18001a7f9  test    eax, eax
0x18001a7fb  js      loc_18001AE67
0x18001a801  lea     rax, [rbp+4Fh+Src]
0x18001a805  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18001a80c  nop     dword ptr [rax+00h]
0x18001a810  cmp     word ptr [rax+r14*2+2], 0
0x18001a817  lea     r14, [r14+1]
0x18001a81b  jnz     short loc_18001A810
0x18001a81d  lea     rcx, [r14+0Bh]
0x18001a821  mov     [rsp+130h+var_F0], 0
0x18001a82a  mov     eax, 2
0x18001a82f  mul     rcx
0x18001a832  test    rdx, rdx
0x18001a835  jnz     loc_18001AE5F
0x18001a83b  mov     rcx, rax; cb
0x18001a83e  call    cs:__imp_CoTaskMemAlloc
0x18001a844  xor     edi, edi
0x18001a846  mov     [rsp+130h+var_F0], rax
0x18001a84b  test    rax, rax
0x18001a84e  cmovz   edi, ebx
0x18001a851  jz      loc_18001AE64
0x18001a857  lea     rdi, [r14+r14]
0x18001a85b  mov     rcx, rax; void *
0x18001a85e  mov     r8, rdi; Size
0x18001a861  lea     rdx, [rbp+4Fh+Src]; Src
0x18001a865  call    memcpy_0
0x18001a86a  mov     rcx, [rsp+130h+var_F0]
0x18001a86f  lea     r8, [rsp+130h+var_F0]
0x18001a874  lea     rdx, _GUID_388cec0d_4ef6_4015_a135_d96527fd84e2
0x18001a87b  mov     word ptr [rcx+rdi], 2Eh ; '.'
0x18001a881  movups  xmm0, xmmword ptr cs:aMergeAny; "Merge Any"
0x18001a888  movups  xmmword ptr [rcx+rdi+2], xmm0
0x18001a88d  movzx   eax, word ptr cs:aMergeAny+10h; "y"
0x18001a894  mov     [rcx+rdi+12h], ax
0x18001a899  xorps   xmm0, xmm0
0x18001a89c  mov     rdi, [rbp+4Fh+var_B0]
0x18001a8a0  xor     eax, eax
0x18001a8a2  mov     [rcx+r14*2+14h], ax
0x18001a8a8  xor     r14d, r14d
0x18001a8ab  mov     qword ptr [rbp+4Fh+var_C0], rax
0x18001a8af  mov     eax, 1Fh
0x18001a8b4  movups  xmmword ptr [rsp+130h+pvar], xmm0
0x18001a8b9  mov     word ptr [rsp+130h+pvar], ax
0x18001a8be  mov     rax, [rdi]
0x18001a8c1  mov     [rbp+4Fh+pvar+8], rcx
0x18001a8c5  mov     rcx, rdi
0x18001a8c8  mov     [rsp+130h+var_F0], r14
0x18001a8cd  mov     rax, [rax]
0x18001a8d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8d5  lea     r8, [rsp+130h+pvar]
0x18001a8da  lea     rdx, PKEY_ResultSourceId
0x18001a8e1  test    eax, eax
0x18001a8e3  js      loc_18001B303
0x18001a8e9  mov     rcx, [rsp+130h+var_F0]
0x18001a8ee  xor     r9d, r9d
0x18001a8f1  mov     rax, [rcx]
0x18001a8f4  mov     rax, [rax+40h]
0x18001a8f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8fd  mov     rcx, [rsp+130h+var_F0]
0x18001a902  mov     edi, eax
0x18001a904  mov     rax, [rcx]
0x18001a907  mov     rax, [rax+10h]
0x18001a90b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a910  lea     rcx, [rsp+130h+pvar]; pvar
0x18001a915  call    cs:__imp_PropVariantClear
0x18001a91b  test    edi, edi
0x18001a91d  js      loc_18001B323
0x18001a923  xor     ecx, ecx; pv
0x18001a925  call    cs:__imp_CoTaskMemFree
0x18001a92b  test    edi, edi
0x18001a92d  js      loc_18001AE67
0x18001a933  mov     rcx, r15; pidl
0x18001a936  call    cs:__imp_ILFindLastID
0x18001a93c  mov     r8, rax
0x18001a93f  mov     edi, 3
0x18001a944  test    rax, rax
0x18001a947  jz      short loc_18001A96D
0x18001a949  movzx   eax, word ptr [rax]
0x18001a94c  cmp     eax, 2Eh ; '.'
0x18001a94f  jb      short loc_18001A96D
0x18001a951  cmp     dword ptr [r8+6], 10141981h
0x18001a959  jnz     short loc_18001A96D
0x18001a95b  movzx   edx, word ptr [r8+0Ah]
0x18001a960  add     rdx, 2Eh ; '.'
0x18001a964  cmp     rax, rdx
0x18001a967  jnb     loc_18001B2D5
0x18001a96d  mov     edx, 0BEEF0013h
0x18001a972  mov     rcx, r15
0x18001a975  call    ?ILFindHiddenIDOn@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@W4IDLHID@@H@Z; ILFindHiddenIDOn(_ITEMIDLIST_RELATIVE const *,IDLHID,int)
0x18001a97a  test    rax, rax
0x18001a97d  jz      loc_18001AB79
0x18001a983  add     rax, 24h ; '$'
0x18001a987  jmp     loc_18001AB59
0x18001a98c  mov     eax, 8007000Eh
0x18001a991  jmp     short loc_18001A9BE
0x18001a993  mov     r9, rsi; struct _GUID *
0x18001a996  mov     [rsp+130h+ppvItem], r12; void **
0x18001a99b  mov     r8, rbx; struct IBindCtx *
0x18001a99e  mov     rdx, r15; struct _ITEMID_CHILD *
0x18001a9a1  mov     rcx, r13; this
0x18001a9a4  call    ?_BindToPropertyStore@CDBFolder@@AEAAJPEBU_ITEMID_CHILD@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z; CDBFolder::_BindToPropertyStore(_ITEMID_CHILD const *,IBindCtx *,_GUID const &,void * *)
0x18001a9a9  mov     ebx, eax
0x18001a9ab  mov     rcx, r15; pidl
0x18001a9ae  call    cs:__imp_ILFree
0x18001a9b4  mov     r14, [rsp+130h+var_38]
0x18001a9bc  mov     eax, ebx
0x18001a9be  mov     rcx, [rbp+4Fh+var_50]
0x18001a9c2  xor     rcx, rsp; StackCookie
0x18001a9c5  call    __security_check_cookie
0x18001a9ca  add     rsp, 100h
0x18001a9d1  pop     r15
0x18001a9d3  pop     r13
0x18001a9d5  pop     r12
0x18001a9d7  pop     rdi
0x18001a9d8  pop     rsi
0x18001a9d9  pop     rbx
0x18001a9da  pop     rbp
0x18001a9db  retn
0x18001a9dc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a9e3  mov     qword ptr [r12], 0
0x18001a9eb  mov     ecx, 30h ; '0'; unsigned __int64
0x18001a9f0  mov     ebx, 8007000Eh
0x18001a9f5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001a9fa  mov     [rbp+4Fh+var_B0], rax
0x18001a9fe  test    rax, rax
0x18001aa01  jz      short loc_18001A9AB
0x18001aa03  mov     rcx, rax; this
0x18001aa06  call    ??0CQueryPropStoreFactory@@AEAA@XZ; CQueryPropStoreFactory::CQueryPropStoreFactory(void)
0x18001aa0b  mov     rdi, rax
0x18001aa0e  test    rax, rax
0x18001aa11  jz      short loc_18001A9AB
0x18001aa13  mov     rcx, r15; pidl
0x18001aa16  call    cs:__imp_ILCloneFirst
0x18001aa1c  mov     [rdi+28h], rax
0x18001aa20  test    rax, rax
0x18001aa23  jz      short loc_18001AA6A
0x18001aa25  lea     rcx, [rdi+18h]; ppunk
0x18001aa29  mov     rdx, r13; punk
0x18001aa2c  call    cs:__imp_IUnknown_Set
0x18001aa32  mov     rcx, [r13+0]
0x18001aa36  lea     r8, [rdi+20h]
0x18001aa3a  lea     rdx, _GUID_1af4b01d_4a4a_489c_8f9f_243612300d24
0x18001aa41  mov     rax, [rcx]
0x18001aa44  mov     rcx, r13
0x18001aa47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa4c  mov     ebx, eax
0x18001aa4e  test    eax, eax
0x18001aa50  js      short loc_18001AA6A
0x18001aa52  mov     r9, r12; ppv
0x18001aa55  lea     rdx, stru_1800EBB90; pqit
0x18001aa5c  mov     r8, rsi; riid
0x18001aa5f  mov     rcx, rdi; that
0x18001aa62  call    cs:__imp_QISearch
0x18001aa68  mov     ebx, eax
0x18001aa6a  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18001aa71  lock xadd [rdi+10h], r14d
0x18001aa77  cmp     r14d, 1
0x18001aa7b  jnz     loc_18001A9AB
0x18001aa81  mov     rcx, rdi; this
0x18001aa84  call    ??_GCQueryPropStoreFactory@@AEAAPEAXI@Z; CQueryPropStoreFactory::`scalar deleting destructor'(uint)
0x18001aa89  jmp     loc_18001A9AB
0x18001aa8e  mov     r9, r12; void **
0x18001aa91  mov     r8, rsi; struct _GUID *
0x18001aa94  mov     rdx, r15; struct _ITEMID_CHILD *
0x18001aa97  call    ?_BindToPropStoreCache@CDBFolder@@AEAAJPEBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z; CDBFolder::_BindToPropStoreCache(_ITEMID_CHILD const *,_GUID const &,void * *)
0x18001aa9c  jmp     loc_18001A9A9
0x18001aaa1  mov     rax, [rsi]
0x18001aaa4  sub     rax, qword ptr cs:IID_IFilterCondition.Data1
0x18001aaab  jnz     short loc_18001AAB8
0x18001aaad  mov     rax, [rsi+8]
0x18001aab1  sub     rax, qword ptr cs:IID_IFilterCondition.Data4
0x18001aab8  test    rax, rax
0x18001aabb  jz      loc_18001AE2E
0x18001aac1  mov     rax, [rsi]
0x18001aac4  sub     rax, qword ptr cs:IID_IDisplayItem.Data1
0x18001aacb  jnz     short loc_18001AAD8
0x18001aacd  mov     rax, [rsi+8]
0x18001aad1  sub     rax, qword ptr cs:IID_IDisplayItem.Data4
0x18001aad8  test    rax, rax
0x18001aadb  jz      loc_18001AE48
0x18001aae1  mov     rax, [rsi]
0x18001aae4  sub     rax, qword ptr cs:IID_IResolveShellLink.Data1
0x18001aaeb  jnz     short loc_18001AAF8
0x18001aaed  mov     rax, [rsi+8]
0x18001aaf1  sub     rax, qword ptr cs:IID_IResolveShellLink.Data4
0x18001aaf8  test    rax, rax
0x18001aafb  jz      loc_18001B357
0x18001ab01  mov     rcx, r15; pidl
0x18001ab04  call    cs:__imp_ILFindLastID
0x18001ab0a  mov     r8, rax
0x18001ab0d  test    rax, rax
0x18001ab10  jz      short loc_18001AB36
0x18001ab12  movzx   eax, word ptr [rax]
0x18001ab15  cmp     eax, 2Eh ; '.'
0x18001ab18  jb      short loc_18001AB36
0x18001ab1a  cmp     dword ptr [r8+6], 10141981h
0x18001ab22  jnz     short loc_18001AB36
  ... truncated ...
```
