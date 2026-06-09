# CNscTree::_TreeInvalidateItemInfo(_TREEITEM *,uint)

- ea: `0x18009ac90`
- end: `0x18009b6eb`
- name: `?_TreeInvalidateItemInfo@CNscTree@@AEAAXPEAU_TREEITEM@@I@Z`
- size: `2651`
- prototype: `void __fastcall(CNscTree *__hidden this, struct _TREEITEM *, unsigned int)`
- caller_count: `6`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180096e58`
- `0x180097f44`
- `0x18009aa84`
- `0x18009abf4`
- `0x1800c1824`
- `0x1800d0e90`

## callees

- `0x18002903c`
- `0x180029078`
- `0x1800290d0`
- `0x18002aa70`
- `0x18002c854`
- `0x18003503c`
- `0x180045ce0`
- `0x1800492b0`
- `0x18009ac90`
- `0x1800dc3a4`
- `0x1800edf80`
- `0x180123448`
- `0x18013fcac`
- `0x18015042c`
- `0x1801b2730`
- `0x180210010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18009af43`
- `SHCORE!IUnknown_QueryService` at `0x18009af43`
- `SHCORE!IUnknown_Set` at `0x18009b018`
- `SHCORE!IUnknown_Set` at `0x18009b018`
- `SHELL32!SHCreateItemWithParent` at `0x18009ad87`
- `SHELL32!SHCreateItemWithParent` at `0x18009b060`
- `SHELL32!SHCreateItemWithParent` at `0x18009ad87`
- `SHELL32!SHCreateItemWithParent` at `0x18009b060`
- `SHELL32!SHCreateItemFromIDList` at `0x18009adc4`
- `SHELL32!SHCreateItemFromIDList` at `0x18009adc4`
- `SHELL32!SHSetTemporaryPropertyForItem` at `0x18009ae14`
- `SHELL32!SHSetTemporaryPropertyForItem` at `0x18009ae14`
- `SHELL32!__imp_ILClone` at `0x18009b2e2`
- `SHELL32!__imp_ILClone` at `0x18009b4f5`
- `SHELL32!__imp_ILClone` at `0x18009b2e2`
- `SHELL32!__imp_ILClone` at `0x18009b4f5`
- `SHELL32!__imp_ILFree` at `0x18009adcf`
- `SHELL32!__imp_ILFree` at `0x18009b62b`
- `SHELL32!__imp_ILFree` at `0x18009adcf`
- `SHELL32!__imp_ILFree` at `0x18009b62b`
- `SHELL32!__imp_SHMapIDListToSystemImageListIndexAsync` at `0x18009b0f3`
- `SHELL32!__imp_SHMapIDListToSystemImageListIndexAsync` at `0x18009b0f3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18009ae1f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18009ae1f`
- `USER32!SendMessageW` at `0x18009ad07`
- `USER32!SendMessageW` at `0x18009af10`
- `USER32!SendMessageW` at `0x18009afb0`
- `USER32!SendMessageW` at `0x18009b6a4`
- `USER32!SendMessageW` at `0x18009ad07`
- `USER32!SendMessageW` at `0x18009af10`
- `USER32!SendMessageW` at `0x18009afb0`
- `USER32!SendMessageW` at `0x18009b6a4`
- `PROPSYS!InitPropVariantFromBuffer` at `0x18009adf7`
- `PROPSYS!InitPropVariantFromBuffer` at `0x18009adf7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CNscTree::_TreeInvalidateItemInfo(CNscTree *this, struct _TREEITEM *a2, unsigned int a3)
{
  const struct _GUID *v5; // r8
  HRESULT v6; // ebx
  const ITEMIDLIST *FullIDList; // rax
  ITEMIDLIST *v8; // rsi
  __int64 v9; // r13
  BOOL v10; // esi
  LRESULT v11; // rbx
  int (__fastcall *v12)(LRESULT, GUID *, IUnknown **); // rax
  const ITEMIDLIST *v13; // r14
  IUnknown *v14; // rbx
  int v15; // ebx
  volatile signed __int32 *v16; // r14
  int v17; // esi
  _QWORD *v18; // rax
  _QWORD *v19; // rbx
  int v20; // esi
  LPITEMIDLIST v21; // rax
  _OWORD *v22; // rax
  CNscLock *v23; // rax
  volatile signed __int32 *v24; // rbx
  int v25; // r14d
  volatile signed __int32 *v26; // r14
  _QWORD *v27; // rax
  _QWORD *v28; // rbx
  LPITEMIDLIST v29; // rax
  _lambda_6e94a9908247e7c461efc54ef4c28ef6_ *v30; // r12
  __int64 v31; // rdx
  wil::details_abi *v32; // rcx
  bool v33; // dl
  struct wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax
  struct wil::details_abi::ThreadLocalData *v35; // rbx
  int v36; // r14d
  int v37; // eax
  IUnknown *v38; // rcx
  __int64 v39; // rcx
  void **ppvItem; // [rsp+20h] [rbp-E0h]
  IShellFolder *v41; // [rsp+40h] [rbp-C0h] BYREF
  struct _TREEITEM *pv; // [rsp+48h] [rbp-B8h] BYREF
  IUnknown *ppunk; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v44; // [rsp+58h] [rbp-A8h] BYREF
  PROPVARIANT ppropvar[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v46; // [rsp+70h] [rbp-90h]
  IUnknown *punk; // [rsp+78h] [rbp-88h] BYREF
  void *v48; // [rsp+80h] [rbp-80h] BYREF
  IUnknown *v49; // [rsp+88h] [rbp-78h] BYREF
  LPARAM v50; // [rsp+A0h] [rbp-60h] BYREF
  const char *v51; // [rsp+A8h] [rbp-58h]
  __int128 v52; // [rsp+B0h] [rbp-50h]
  _BYTE v53[40]; // [rsp+C0h] [rbp-40h] BYREF
  int v54; // [rsp+E8h] [rbp-18h]
  int v55; // [rsp+ECh] [rbp-14h]
  LPARAM lParam[2]; // [rsp+F0h] [rbp-10h] BYREF
  int v57; // [rsp+100h] [rbp+0h]
  int v58; // [rsp+104h] [rbp+4h]
  __int64 v59; // [rsp+108h] [rbp+8h]
  __int64 v60; // [rsp+110h] [rbp+10h]
  int v61; // [rsp+118h] [rbp+18h]
  int v62; // [rsp+11Ch] [rbp+1Ch]
  __int128 v63; // [rsp+120h] [rbp+20h]
  __int128 v64; // [rsp+130h] [rbp+30h]
  LPARAM retaddr; // [rsp+188h] [rbp+88h]
  void *ppv; // [rsp+190h] [rbp+90h] BYREF
  IShellFolder *psfParent; // [rsp+198h] [rbp+98h] BYREF
  unsigned int v68; // [rsp+1A0h] [rbp+A0h]
  LPCITEMIDLIST pidl; // [rsp+1A8h] [rbp+A8h] BYREF

  v60 = 0;
  v61 = 0;
  v63 = 0;
  v64 = 0;
  lParam[0] = a3 | 0x48LL;
  v58 = 3840;
  v57 = 0;
  lParam[1] = (LPARAM)a2;
  v62 = -1;
  v59 = -1;
  SendMessageW(*((HWND *)this + 50), 0x113Fu, 0, (LPARAM)lParam);
  v44 = 0;
  if ( *((_QWORD *)this + 75) )
  {
    pv = a2;
    v44 = 0;
    pidl = 0;
    psfParent = 0;
    if ( (int)CNscTree::_GetTreeItemParentFolder(
                this,
                a2,
                v5,
                (void **)&psfParent,
                (const struct _ITEMID_CHILD **)&pidl) >= 0 )
    {
      ppv = 0;
      v6 = SHCreateItemWithParent(0, psfParent, pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
      if ( v6 >= 0
        || (FullIDList = (const ITEMIDLIST *)CNscTree::_GetFullIDList(this, *((HWND *)this + 50), pv),
            (v8 = (ITEMIDLIST *)FullIDList) != 0)
        && (v6 = SHCreateItemFromIDList(FullIDList, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv),
            ILFree(v8),
            v6 >= 0) )
      {
        *(_OWORD *)ppropvar = 0;
        v46 = 0;
        if ( InitPropVariantFromBuffer(&pv, 8u, ppropvar) >= 0 )
        {
          SHSetTemporaryPropertyForItem((IShellItem *)ppv, &PKEY_DescriptionID, ppropvar);
          PropVariantClear(ppropvar);
        }
        v6 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))ppv)(
               ppv,
               &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
               &v44);
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      ((void (__fastcall *)(IShellFolder *))psfParent->lpVtbl->Release)(psfParent);
      if ( v6 >= 0 )
        (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 75) + 32LL))(*((_QWORD *)this + 75), v44);
    }
  }
  v48 = 0;
  ppv = 0;
  if ( (int)CNscTree::_GetTreeItemParentFolder(this, a2, v5, &v48, (const struct _ITEMID_CHILD **)&ppv) >= 0 )
  {
    v41 = (IShellFolder *)v48;
    LODWORD(psfParent) = 0;
    LODWORD(pidl) = 0;
    v9 = 0;
    if ( a2 )
    {
      if ( a2 != (struct _TREEITEM *)-65536LL )
      {
        v50 = 20;
        v52 = 0;
        memset(v53, 0, 24);
        v51 = (const char *)a2;
        if ( (unsigned int)SendMessageW(*((HWND *)this + 50), 0x113Eu, 0, (LPARAM)&v50) )
          v9 = *(_QWORD *)&v53[16];
      }
    }
    if ( !*((_QWORD *)this + 86)
      && IUnknown_QueryService(
           *((IUnknown **)this + 22),
           &IID_IShellTaskScheduler,
           &GUID_6ccb7be0_6807_11d0_b810_00c04fd706ec,
           (void **)this + 86) < 0
      && (int)CreateDefaultTaskScheduler(&GUID_6ccb7be0_6807_11d0_b810_00c04fd706ec, (void **)this + 86) < 0
      || !v9
      || (pv = CNscTree::_GetFullIDList(this, *((HWND *)this + 50), a2)) == 0 )
    {
LABEL_76:
      v50 = 546;
      v52 = 0;
      *(_DWORD *)v53 = 0;
      memset(&v53[12], 0, 28);
      v55 = 0;
      v51 = (const char *)a2;
      *(_DWORD *)&v53[4] = (_DWORD)psfParent;
      *(_DWORD *)&v53[8] = (_DWORD)psfParent;
      v54 = (int)pidl;
      SendMessageW(*((HWND *)this + 50), 0x113Fu, 0, (LPARAM)&v50);
LABEL_77:
      (*(void (__fastcall **)(void *))(*(_QWORD *)v48 + 16LL))(v48);
      goto LABEL_78;
    }
    v10 = 0;
    ppunk = 0;
    punk = 0;
    v11 = SendMessageW(*((HWND *)this + 50), 0x1108u, 0, 0);
    if ( !v11 )
      goto LABEL_73;
    v12 = (int (__fastcall *)(LRESULT, GUID *, IUnknown **))qword_180291358;
    if ( qword_180291358 == -1 )
    {
      GetProcFromComCtl32(&qword_180291358, "HIMAGELIST_QueryInterface");
      v12 = (int (__fastcall *)(LRESULT, GUID *, IUnknown **))qword_180291358;
    }
    if ( !v12 || v12(v11, &GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1, &punk) < 0 )
    {
LABEL_73:
      ILFree((LPITEMIDLIST)pv);
      v38 = ppunk;
      ppunk = 0;
      if ( v38 )
        ((void (__fastcall *)(IUnknown *))v38->lpVtbl->Release)(v38);
      if ( v10 )
        goto LABEL_77;
      goto LABEL_76;
    }
    IUnknown_Set(&ppunk, punk);
    v13 = (const ITEMIDLIST *)ppv;
    v14 = ppunk;
    v49 = ppunk;
    if ( *((_QWORD *)this + 69) )
    {
      if ( ppv )
      {
        ppv = 0;
        if ( SHCreateItemWithParent(0, v41, v13, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv) >= 0 )
        {
          v15 = (*(__int64 (__fastcall **)(_QWORD, void *, IShellFolder **, LPCITEMIDLIST *))(**((_QWORD **)this + 69)
                                                                                            + 160LL))(
                  *((_QWORD *)this + 69),
                  ppv,
                  &psfParent,
                  &pidl);
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
          if ( v15 >= 0 )
            goto LABEL_51;
          v14 = v49;
        }
      }
    }
    v68 = 0;
    LODWORD(ppv) = 0;
    ppvItem = 0;
    if ( (int)SHMapIDListToSystemImageListIndexAsync(0, v41, v13, 0) >= 0 )
    {
      LODWORD(psfParent) = v68;
      LODWORD(pidl) = (_DWORD)ppv;
      v41 = 0;
      if ( ((__int64 (__fastcall *)(IUnknown *, GUID *, IShellFolder **))v14->lpVtbl->QueryInterface)(
             v14,
             &GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1,
             &v41) >= 0 )
      {
        if ( ((int (__fastcall *)(IShellFolder *, _QWORD, __int64))v41->lpVtbl[2].GetDisplayNameOf)(v41, v68, 1) >= 0
          && ((_DWORD)ppv == v68
           || ((int (__fastcall *)(IShellFolder *, _QWORD, __int64))v41->lpVtbl[2].GetDisplayNameOf)(
                v41,
                (unsigned int)ppv,
                1) >= 0) )
        {
          ((void (__fastcall *)(IShellFolder *))v41->lpVtbl->Release)(v41);
LABEL_51:
          ppv = ppunk;
          if ( *((_QWORD *)this + 87) )
            goto LABEL_57;
          *((_QWORD *)this + 87) = 0;
          v22 = operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
          ppropvar[0] = v22;
          if ( v22 )
          {
            *v22 = 0;
            v22[1] = 0;
            v22[2] = 0;
            v22[3] = 0;
            v22[4] = 0;
            v22[5] = 0;
            v22[6] = 0;
            *((_QWORD *)v22 + 14) = 0;
            v23 = CNscLock::CNscLock((CNscLock *)v22);
            v24 = (volatile signed __int32 *)v23;
            if ( v23 )
            {
              v25 = CNscLock::Init(v23, this);
              if ( v25 >= 0 )
              {
                *((_QWORD *)this + 87) = v24;
                _InterlockedIncrement(v24 + 26);
              }
              CTaskLock::Release((CTaskLock *)v24);
              if ( v25 >= 0 )
              {
LABEL_57:
                v26 = (volatile signed __int32 *)*((_QWORD *)this + 87);
                _InterlockedIncrement(v26 + 26);
                LOBYTE(v68) = *((_BYTE *)this + 768);
                v49 = (IUnknown *)*((_QWORD *)this + 86);
                v27 = operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
                v28 = v27;
                ppropvar[0] = v27;
                if ( v27 )
                {
                  *((_DWORD *)v27 + 10) = 1;
                  *(_QWORD *)((char *)v27 + 44) = 0;
                  v27[7] = 0;
                  *((_DWORD *)v27 + 16) = 0;
                  *v27 = &CNscOverlayTask::`vftable'{for `IRunnableTask'};
                  v27[1] = &CNscSortTask::`vftable'{for `IServiceProvider'};
                  v27[2] = &CNscSortTask::`vftable'{for `IQueryContinue'};
                  v27[3] = &CComCatCacheTask::`vftable'{for `IObjectWithCancelEvent'};
                  v27[4] = &CFrameTask::`vftable'{for `ITestRunnableTask'};
                  v27[10] = 0;
                  v27[11] = a2;
                  *((_DWORD *)v27 + 26) = (unsigned __int8)v68;
                  _InterlockedIncrement(&g_cRefThisDll);
                  v27[9] = v26;
                  _InterlockedIncrement(v26 + 26);
                  v27[12] = v9;
                  _InterlockedIncrement((volatile signed __int32 *)(v9 + 56));
                  if ( !ppv
                    || (**(int (__fastcall ***)(void *, GUID *, __int64))ppv)(
                         ppv,
                         &GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1,
                         (__int64)(v27 + 14)) >= 0 )
                  {
                    v29 = ILClone((LPCITEMIDLIST)pv);
                    v28[10] = v29;
                    if ( v29 )
                    {
                      LODWORD(ppvItem) = 0x10000000;
                      ((void (__fastcall *)(IUnknown *, _QWORD *, __int64 *, __int64))v49->lpVtbl[1].QueryInterface)(
                        v49,
                        v28,
                        TASKID_OverlayExtraction,
                        -1);
                    }
                  }
                  (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
                }
                if ( _InterlockedExchangeAdd(v26 + 26, 0xFFFFFFFF) == 1 && v26 )
                  (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v26 + 16LL))(v26, 1);
              }
            }
          }
          ppv = a2;
          v30 = _lambda_6e94a9908247e7c461efc54ef4c28ef6_::_lambda_6e94a9908247e7c461efc54ef4c28ef6_(
                  (_lambda_6e94a9908247e7c461efc54ef4c28ef6_ *)&v49,
                  (struct _ITEMIDLIST_ABSOLUTE **)this,
                  (struct FileExplorerSessionWatcher::details::FileExplorerSessionWatcher *)&ppv);
          v50 = retaddr;
          v51 = "shell\\explorerframe\\nsc.cpp";
          *(_QWORD *)&v52 = "114_NavPaneSetCloudStateIcon";
          WORD4(v52) = 822;
          LOBYTE(v31) = 114;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudFileStateIcon>::__private_IsEnabledPreCheck(
            &`wil::Feature<__WilFeatureTraits_Feature_CloudFileStateIcon>::GetImpl'::`2'::impl,
            v31);
          LOBYTE(v32) = 1;
          ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v32, v33);
          v35 = ThreadLocalDataCache;
          ppropvar[0] = ThreadLocalDataCache;
          ppropvar[1] = 0;
          v36 = 0;
          if ( ThreadLocalDataCache )
          {
            v36 = *((_DWORD *)ThreadLocalDataCache + 4);
            HIDWORD(ppropvar[1]) = v36;
            LODWORD(ppropvar[1]) = **((_DWORD **)ThreadLocalDataCache + 1);
            *((_DWORD *)ThreadLocalDataCache + 4) = ppropvar[1];
          }
          v37 = lambda_127891c1ee58b494369a315531b4610d_::operator()(v30);
          if ( v37 < 0 )
            wil::details::ReportFeatureError(
              (wil::details *)(unsigned int)v37,
              (int)ppropvar,
              (struct wil::ThreadErrorContext *)0x605A2,
              (unsigned int)&v50,
              (const struct DiagnosticsInfo *)ppvItem);
          if ( v35 )
            *((_DWORD *)v35 + 4) = v36;
          ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
          goto LABEL_73;
        }
        ((void (__fastcall *)(IShellFolder *))v41->lpVtbl->Release)(v41);
      }
    }
    if ( *((_QWORD *)this + 87) || (int)CNscLock_Create(this, (struct CNscLock **)this + 87) >= 0 )
    {
      v16 = (volatile signed __int32 *)*((_QWORD *)this + 87);
      _InterlockedIncrement(v16 + 26);
      v17 = *((unsigned __int8 *)this + 768);
      v41 = (IShellFolder *)*((_QWORD *)this + 86);
      v18 = operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
      v19 = v18;
      ppropvar[0] = v18;
      if ( v18 )
      {
        *((_DWORD *)v18 + 10) = 1;
        *(_QWORD *)((char *)v18 + 44) = 0;
        v18[7] = 0;
        *((_DWORD *)v18 + 16) = 0;
        *v18 = &CNscOverlayTask::`vftable'{for `IRunnableTask'};
        v18[1] = &CNscSortTask::`vftable'{for `IServiceProvider'};
        v18[2] = &CNscSortTask::`vftable'{for `IQueryContinue'};
        v18[3] = &CComCatCacheTask::`vftable'{for `IObjectWithCancelEvent'};
        v18[4] = &CFrameTask::`vftable'{for `ITestRunnableTask'};
        v18[10] = 0;
        v18[11] = a2;
        *((_DWORD *)v18 + 26) = v17;
        _InterlockedIncrement(&g_cRefThisDll);
        v18[9] = v16;
        _InterlockedIncrement(v16 + 26);
        v18[12] = v9;
        _InterlockedIncrement((volatile signed __int32 *)(v9 + 56));
        *v18 = &CNscIconTask::`vftable'{for `IRunnableTask'};
        v18[1] = &CNscSortTask::`vftable'{for `IServiceProvider'};
        v18[2] = &CNscSortTask::`vftable'{for `IQueryContinue'};
        v18[3] = &CComCatCacheTask::`vftable'{for `IObjectWithCancelEvent'};
        v18[4] = &CFrameTask::`vftable'{for `ITestRunnableTask'};
        if ( !v49
          || (v20 = ((__int64 (__fastcall *)(IUnknown *, GUID *, _QWORD *))v49->lpVtbl->QueryInterface)(
                      v49,
                      &GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1,
                      v18 + 14),
              v20 >= 0) )
        {
          v21 = ILClone((LPCITEMIDLIST)pv);
          v19[10] = v21;
          if ( v21 )
          {
            LODWORD(ppvItem) = 268435459;
            v20 = ((__int64 (__fastcall *)(IShellFolder *, _QWORD *, __int64 *, __int64))v41->lpVtbl->ParseDisplayName)(
                    v41,
                    v19,
                    TASKID_IconExtraction,
                    -1);
          }
          else
          {
            v20 = -2147024882;
          }
        }
        (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
      }
      else
      {
        v20 = -2147024882;
      }
      v10 = v20 >= 0;
      if ( _InterlockedExchangeAdd(v16 + 26, 0xFFFFFFFF) == 1 && v16 )
        (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v16 + 16LL))(v16, 1);
    }
    goto LABEL_51;
  }
LABEL_78:
  v39 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  }
}

```

## disassembly

```asm
0x18009ac90  push    rbp
0x18009ac92  push    rbx
0x18009ac93  push    rsi
0x18009ac94  push    rdi
0x18009ac95  push    r12
0x18009ac97  push    r13
0x18009ac99  push    r14
0x18009ac9b  push    r15
0x18009ac9d  lea     rbp, [rsp-48h]
0x18009aca2  sub     rsp, 148h
0x18009aca9  mov     r15, rdx
0x18009acac  mov     rdi, rcx
0x18009acaf  xor     r14d, r14d
0x18009acb2  mov     dword ptr [rbp+80h+lParam+4], r14d
0x18009acb6  mov     [rbp+80h+var_70], r14
0x18009acba  mov     [rbp+80h+var_68], r14d
0x18009acbe  xorps   xmm0, xmm0
0x18009acc1  movdqa  [rbp+80h+var_60], xmm0
0x18009acc6  xorps   xmm1, xmm1
0x18009acc9  movdqa  [rbp+80h+var_50], xmm1
0x18009acce  or      r8d, 48h
0x18009acd2  mov     dword ptr [rbp+80h+lParam], r8d
0x18009acd6  mov     [rbp+80h+var_7C], 0F00h
0x18009acdd  mov     [rbp+80h+var_80], r14d
0x18009ace1  mov     [rbp+80h+var_88], rdx
0x18009ace5  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18009acec  mov     [rbp+80h+var_64], r12d
0x18009acf0  mov     [rbp+80h+var_78], r12
0x18009acf4  lea     r9, [rbp+80h+lParam]; lParam
0x18009acf8  xor     r8d, r8d; wParam
0x18009acfb  mov     edx, 113Fh; Msg
0x18009ad00  mov     rcx, [rcx+190h]; hWnd
0x18009ad07  call    cs:__imp_SendMessageW
0x18009ad0d  mov     [rsp+180h+var_128], r14
0x18009ad12  cmp     [rdi+258h], r14
0x18009ad19  jz      loc_18009AE87
0x18009ad1f  mov     [rsp+180h+pv], r15
0x18009ad24  mov     [rsp+180h+var_128], r14
0x18009ad29  mov     [rbp+80h+pidl], r14
0x18009ad30  mov     [rbp+80h+psfParent], r14
0x18009ad37  lea     rax, [rbp+80h+pidl]
0x18009ad3e  mov     [rsp+180h+ppvItem], rax; struct _ITEMID_CHILD **
0x18009ad43  lea     r9, [rbp+80h+psfParent]; void **
0x18009ad4a  mov     rdx, r15; struct _TREEITEM *
0x18009ad4d  mov     rcx, rdi; this
0x18009ad50  call    ?_GetTreeItemParentFolder@CNscTree@@AEAAJPEAU_TREEITEM@@AEBU_GUID@@PEAPEAXPEAPEFBU_ITEMID_CHILD@@@Z; CNscTree::_GetTreeItemParentFolder(_TREEITEM *,_GUID const &,void * *,_ITEMID_CHILD const * *)
0x18009ad55  test    eax, eax
0x18009ad57  js      loc_18009AE87
0x18009ad5d  mov     [rbp+80h+ppv], r14
0x18009ad64  lea     rax, [rbp+80h+ppv]
0x18009ad6b  mov     [rsp+180h+ppvItem], rax; ppvItem
0x18009ad70  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18009ad77  mov     r8, [rbp+80h+pidl]; pidl
0x18009ad7e  mov     rdx, [rbp+80h+psfParent]; psfParent
0x18009ad85  xor     ecx, ecx; pidlParent
0x18009ad87  call    cs:__imp_SHCreateItemWithParent
0x18009ad8d  mov     ebx, eax
0x18009ad8f  test    eax, eax
0x18009ad91  jns     short loc_18009ADD9
0x18009ad93  mov     r8, [rsp+180h+pv]; struct _TREEITEM *
0x18009ad98  mov     rdx, [rdi+190h]; HWND
0x18009ad9f  mov     rcx, rdi; this
0x18009ada2  call    ?_GetFullIDList@CNscTree@@AEAAPEAU_ITEMIDLIST_ABSOLUTE@@PEAUHWND__@@PEAU_TREEITEM@@@Z; CNscTree::_GetFullIDList(HWND__ *,_TREEITEM *)
0x18009ada7  mov     rsi, rax
0x18009adaa  test    rax, rax
0x18009adad  jz      loc_18009AE58
0x18009adb3  lea     r8, [rbp+80h+ppv]; ppv
0x18009adba  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18009adc1  mov     rcx, rax; pidl
0x18009adc4  call    cs:__imp_SHCreateItemFromIDList
0x18009adca  mov     ebx, eax
0x18009adcc  mov     rcx, rsi; pidl
0x18009adcf  call    cs:__imp_ILFree
0x18009add5  test    ebx, ebx
0x18009add7  js      short loc_18009AE58
0x18009add9  xorps   xmm0, xmm0
0x18009addc  xor     eax, eax
0x18009adde  movups  xmmword ptr [rsp+180h+ppropvar], xmm0
0x18009ade3  mov     [rsp+180h+var_110], rax
0x18009ade8  lea     r8, [rsp+180h+ppropvar]; ppropvar
0x18009aded  mov     edx, 8; cb
0x18009adf2  lea     rcx, [rsp+180h+pv]; pv
0x18009adf7  call    cs:__imp_InitPropVariantFromBuffer
0x18009adfd  test    eax, eax
0x18009adff  js      short loc_18009AE25
0x18009ae01  lea     r8, [rsp+180h+ppropvar]; propvar
0x18009ae06  lea     rdx, PKEY_DescriptionID; propkey
0x18009ae0d  mov     rcx, [rbp+80h+ppv]; psi
0x18009ae14  call    cs:__imp_SHSetTemporaryPropertyForItem
0x18009ae1a  lea     rcx, [rsp+180h+ppropvar]; pvar
0x18009ae1f  call    cs:__imp_PropVariantClear
0x18009ae25  mov     rcx, [rbp+80h+ppv]
0x18009ae2c  mov     rax, [rcx]
0x18009ae2f  lea     r8, [rsp+180h+var_128]
0x18009ae34  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18009ae3b  mov     rax, [rax]
0x18009ae3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ae43  mov     ebx, eax
0x18009ae45  mov     rcx, [rbp+80h+ppv]
0x18009ae4c  mov     rax, [rcx]
0x18009ae4f  mov     rax, [rax+10h]
0x18009ae53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ae58  mov     rcx, [rbp+80h+psfParent]
0x18009ae5f  mov     rax, [rcx]
0x18009ae62  mov     rax, [rax+10h]
0x18009ae66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ae6b  test    ebx, ebx
0x18009ae6d  js      short loc_18009AE87
0x18009ae6f  mov     rcx, [rdi+258h]
0x18009ae76  mov     rax, [rcx]
0x18009ae79  mov     rdx, [rsp+180h+var_128]
0x18009ae7e  mov     rax, [rax+20h]
0x18009ae82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ae87  mov     [rbp+80h+var_100], r14
0x18009ae8b  mov     [rbp+80h+ppv], r14
0x18009ae92  lea     rax, [rbp+80h+ppv]
0x18009ae99  mov     [rsp+180h+ppvItem], rax; struct _ITEMID_CHILD **
0x18009ae9e  lea     r9, [rbp+80h+var_100]; void **
0x18009aea2  mov     rdx, r15; struct _TREEITEM *
0x18009aea5  mov     rcx, rdi; this
0x18009aea8  call    ?_GetTreeItemParentFolder@CNscTree@@AEAAJPEAU_TREEITEM@@AEBU_GUID@@PEAPEAXPEAPEFBU_ITEMID_CHILD@@@Z; CNscTree::_GetTreeItemParentFolder(_TREEITEM *,_GUID const &,void * *,_ITEMID_CHILD const * *)
0x18009aead  test    eax, eax
0x18009aeaf  js      loc_18009B6BB
0x18009aeb5  mov     rax, [rbp+80h+var_100]
0x18009aeb9  mov     [rsp+180h+var_140], rax
0x18009aebe  mov     dword ptr [rbp+80h+psfParent], r14d
0x18009aec5  mov     dword ptr [rbp+80h+pidl], r14d
0x18009aecc  mov     r13, r14
0x18009aecf  test    r15, r15
0x18009aed2  jz      short loc_18009AF1D
0x18009aed4  cmp     r15, 0FFFFFFFFFFFF0000h
0x18009aedb  jz      short loc_18009AF1D
0x18009aedd  mov     [rbp+80h+var_E0], 14h
0x18009aee5  xorps   xmm0, xmm0
0x18009aee8  movdqu  [rbp+80h+var_D0], xmm0
0x18009aeed  xorps   xmm1, xmm1
0x18009aef0  movdqu  xmmword ptr [rbp+80h+var_C0], xmm1
0x18009aef5  mov     qword ptr [rbp+80h+var_C0+10h], r14
0x18009aef9  mov     [rbp+80h+var_D8], r15
0x18009aefd  lea     r9, [rbp+80h+var_E0]; lParam
0x18009af01  xor     r8d, r8d; wParam
0x18009af04  mov     edx, 113Eh; Msg
0x18009af09  mov     rcx, [rdi+190h]; hWnd
0x18009af10  call    cs:__imp_SendMessageW
0x18009af16  test    eax, eax
0x18009af18  cmovnz  r13, qword ptr [rbp+80h+var_C0+10h]
0x18009af1d  cmp     qword ptr [rdi+2B0h], 0
0x18009af25  jnz     short loc_18009AF68
0x18009af27  lea     r9, [rdi+2B0h]; ppvOut
0x18009af2e  lea     r8, _GUID_6ccb7be0_6807_11d0_b810_00c04fd706ec; riid
0x18009af35  lea     rdx, IID_IShellTaskScheduler; guidService
0x18009af3c  mov     rcx, [rdi+0B0h]; punk
0x18009af43  call    cs:__imp_IUnknown_QueryService
0x18009af49  test    eax, eax
0x18009af4b  jns     short loc_18009AF68
0x18009af4d  lea     rdx, [rdi+2B0h]; void **
0x18009af54  lea     rcx, _GUID_6ccb7be0_6807_11d0_b810_00c04fd706ec; struct _GUID *
0x18009af5b  call    ?CreateDefaultTaskScheduler@@YAJAEBU_GUID@@PEAPEAX@Z; CreateDefaultTaskScheduler(_GUID const &,void * *)
0x18009af60  test    eax, eax
0x18009af62  js      loc_18009B650
0x18009af68  test    r13, r13
0x18009af6b  jz      loc_18009B650
0x18009af71  mov     r8, r15; struct _TREEITEM *
0x18009af74  mov     rdx, [rdi+190h]; HWND
0x18009af7b  mov     rcx, rdi; this
0x18009af7e  call    ?_GetFullIDList@CNscTree@@AEAAPEAU_ITEMIDLIST_ABSOLUTE@@PEAUHWND__@@PEAU_TREEITEM@@@Z; CNscTree::_GetFullIDList(HWND__ *,_TREEITEM *)
0x18009af83  mov     [rsp+180h+pv], rax
0x18009af88  test    rax, rax
0x18009af8b  jz      loc_18009B650
0x18009af91  mov     esi, r14d
0x18009af94  mov     [rsp+180h+ppunk], r14
0x18009af99  mov     [rsp+180h+punk], r14
0x18009af9e  xor     r9d, r9d; lParam
0x18009afa1  xor     r8d, r8d; wParam
0x18009afa4  mov     edx, 1108h; Msg
0x18009afa9  mov     rcx, [rdi+190h]; hWnd
0x18009afb0  call    cs:__imp_SendMessageW
0x18009afb6  mov     rbx, rax
0x18009afb9  test    rax, rax
0x18009afbc  jz      loc_18009B626
0x18009afc2  mov     rax, cs:qword_180291358
0x18009afc9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009afcd  jnz     short loc_18009AFE9
0x18009afcf  lea     rdx, aHimagelistQuer; "HIMAGELIST_QueryInterface"
0x18009afd6  lea     rcx, qword_180291358
0x18009afdd  call    _GetProcFromComCtl32
0x18009afe2  mov     rax, cs:qword_180291358
0x18009afe9  test    rax, rax
0x18009afec  jz      loc_18009B626
0x18009aff2  lea     r8, [rsp+180h+punk]
0x18009aff7  lea     rdx, _GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1
0x18009affe  mov     rcx, rbx
0x18009b001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b006  test    eax, eax
0x18009b008  js      loc_18009B626
0x18009b00e  mov     rdx, [rsp+180h+punk]; punk
0x18009b013  lea     rcx, [rsp+180h+ppunk]; ppunk
0x18009b018  call    cs:__imp_IUnknown_Set
0x18009b01e  mov     r14, [rbp+80h+ppv]
0x18009b025  mov     rbx, [rsp+180h+ppunk]
0x18009b02a  mov     [rbp+80h+var_F8], rbx
0x18009b02e  xor     ecx, ecx; pidlParent
0x18009b030  cmp     [rdi+228h], rcx
0x18009b037  jz      short loc_18009B0B8
0x18009b039  test    r14, r14
0x18009b03c  jz      short loc_18009B0B8
0x18009b03e  mov     [rbp+80h+ppv], rcx
0x18009b045  lea     rax, [rbp+80h+ppv]
0x18009b04c  mov     [rsp+180h+ppvItem], rax; ppvItem
0x18009b051  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18009b058  mov     r8, r14; pidl
0x18009b05b  mov     rdx, [rsp+180h+var_140]; psfParent
0x18009b060  call    cs:__imp_SHCreateItemWithParent
0x18009b066  test    eax, eax
0x18009b068  js      short loc_18009B0B6
0x18009b06a  mov     rcx, [rdi+228h]
0x18009b071  mov     rax, [rcx]
0x18009b074  lea     r9, [rbp+80h+pidl]
0x18009b07b  lea     r8, [rbp+80h+psfParent]
0x18009b082  mov     rdx, [rbp+80h+ppv]
0x18009b089  mov     rax, [rax+0A0h]
0x18009b090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b095  mov     ebx, eax
0x18009b097  mov     rcx, [rbp+80h+ppv]
0x18009b09e  mov     rdx, [rcx]
0x18009b0a1  mov     rax, [rdx+10h]
0x18009b0a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b0aa  test    ebx, ebx
0x18009b0ac  jns     loc_18009B365
0x18009b0b2  mov     rbx, [rbp+80h+var_F8]
0x18009b0b6  xor     ecx, ecx
0x18009b0b8  mov     [rbp+80h+arg_10], ecx
0x18009b0be  mov     dword ptr [rbp+80h+ppv], ecx
0x18009b0c4  lea     rax, [rbp+80h+ppv]
0x18009b0cb  mov     [rsp+180h+var_148], rax
0x18009b0d0  lea     rax, [rbp+80h+arg_10]
0x18009b0d7  mov     [rsp+180h+var_150], rax
0x18009b0dc  mov     [rsp+180h+var_158], rcx
0x18009b0e1  mov     [rsp+180h+ppvItem], rcx
0x18009b0e6  xor     r9d, r9d
0x18009b0e9  mov     r8, r14
0x18009b0ec  mov     rdx, [rsp+180h+var_140]
0x18009b0f1  xor     ecx, ecx
0x18009b0f3  call    cs:__imp_SHMapIDListToSystemImageListIndexAsync
0x18009b0f9  test    eax, eax
0x18009b0fb  js      loc_18009B1B3
0x18009b101  mov     eax, [rbp+80h+arg_10]
0x18009b107  mov     dword ptr [rbp+80h+psfParent], eax
0x18009b10d  mov     eax, dword ptr [rbp+80h+ppv]
0x18009b113  mov     dword ptr [rbp+80h+pidl], eax
0x18009b119  mov     [rsp+180h+var_140], rsi
0x18009b11e  mov     rax, [rbx]
0x18009b121  lea     r8, [rsp+180h+var_140]
0x18009b126  lea     rdx, _GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1
0x18009b12d  mov     rcx, rbx
0x18009b130  mov     rax, [rax]
0x18009b133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b138  test    eax, eax
0x18009b13a  js      short loc_18009B1B3
0x18009b13c  mov     rcx, [rsp+180h+var_140]
0x18009b141  mov     rax, [rcx]
0x18009b144  mov     r8d, 1
0x18009b14a  mov     edx, [rbp+80h+arg_10]
0x18009b150  mov     rax, [rax+128h]
0x18009b157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b15c  test    eax, eax
0x18009b15e  js      short loc_18009B1A2
0x18009b160  mov     edx, dword ptr [rbp+80h+ppv]
0x18009b166  cmp     edx, [rbp+80h+arg_10]
0x18009b16c  jz      short loc_18009B18C
0x18009b16e  mov     rcx, [rsp+180h+var_140]
0x18009b173  mov     rax, [rcx]
0x18009b176  mov     r8d, 1
0x18009b17c  mov     rax, [rax+128h]
0x18009b183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b188  test    eax, eax
0x18009b18a  js      short loc_18009B1A2
0x18009b18c  mov     rcx, [rsp+180h+var_140]
0x18009b191  mov     rax, [rcx]
0x18009b194  mov     rax, [rax+10h]
0x18009b198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b19d  jmp     loc_18009B365
0x18009b1a2  mov     rcx, [rsp+180h+var_140]
0x18009b1a7  mov     rax, [rcx]
0x18009b1aa  mov     rax, [rax+10h]
0x18009b1ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b1b3  cmp     [rdi+2B8h], rsi
0x18009b1ba  jnz     short loc_18009B1D3
0x18009b1bc  lea     rdx, [rdi+2B8h]; struct CNscLock **
0x18009b1c3  mov     rcx, rdi; struct CNscTree *
0x18009b1c6  call    ?CNscLock_Create@@YAJPEAVCNscTree@@PEAPEAVCNscLock@@@Z; CNscLock_Create(CNscTree *,CNscLock * *)
0x18009b1cb  test    eax, eax
0x18009b1cd  js      loc_18009B365
0x18009b1d3  mov     r14, [rdi+2B8h]
0x18009b1da  lock inc dword ptr [r14+68h]
0x18009b1df  movzx   esi, byte ptr [rdi+300h]
0x18009b1e6  mov     rax, [rdi+2B0h]
0x18009b1ed  mov     [rsp+180h+var_140], rax
0x18009b1f2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009b1f9  mov     ecx, 78h ; 'x'; unsigned __int64
  ... truncated ...
```
