# CNscEnumTask::InternalResumeRT(void)

- ea: `0x18002d5f0`
- end: `0x18002e1e5`
- name: `?InternalResumeRT@CNscEnumTask@@UEAAJXZ`
- size: `3061`
- prototype: `__int64 __fastcall(CNscEnumTask *__hidden this)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800218ac`
- `0x180026424`
- `0x18002d5f0`
- `0x18002ea60`
- `0x18002ea94`
- `0x18002f35c`
- `0x180045ea4`
- `0x1800471dc`
- `0x1800703fc`
- `0x180073f20`
- `0x18008d790`
- `0x1800b1640`
- `0x1800c93cc`
- `0x1800c9514`
- `0x1800ca414`
- `0x1800f5e0c`
- `0x18013f7d0`
- `0x18013fcac`
- `0x1801406c8`
- `0x1801406ec`
- `0x180210010`

## import_xrefs

- `SHCORE!IUnknown_SetSite` at `0x18002d7a6`
- `SHCORE!IUnknown_SetSite` at `0x18002dce0`
- `SHCORE!IUnknown_SetSite` at `0x18002e0d5`
- `SHCORE!IUnknown_SetSite` at `0x18002d7a6`
- `SHCORE!IUnknown_SetSite` at `0x18002dce0`
- `SHCORE!IUnknown_SetSite` at `0x18002e0d5`
- `SHCORE!__imp_SHRegGetValueFromHKCUHKLM` at `0x18002dfbc`
- `SHCORE!__imp_SHRegGetValueFromHKCUHKLM` at `0x18002dfbc`
- `SHELL32!SHCreateItemWithParent` at `0x18002d8b4`
- `SHELL32!SHCreateItemWithParent` at `0x18002d8b4`
- `SHELL32!SHBindToObject` at `0x18002d681`
- `SHELL32!SHBindToObject` at `0x18002d681`
- `SHELL32!SHBindToFolderIDListParentEx` at `0x18002dd93`
- `SHELL32!SHBindToFolderIDListParentEx` at `0x18002dd93`
- `SHELL32!SHCreateItemFromIDList` at `0x18002d6c7`
- `SHELL32!SHCreateItemFromIDList` at `0x18002d6c7`
- `SHELL32!__imp_ILClone` at `0x18002dbf1`
- `SHELL32!__imp_ILClone` at `0x18002dbf1`
- `SHELL32!__imp_ILCloneFirst` at `0x18002dc1c`
- `SHELL32!__imp_ILCloneFirst` at `0x18002dc1c`
- `SHELL32!__imp_ILFree` at `0x18002da1c`
- `SHELL32!__imp_ILFree` at `0x18002da1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002dee8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002df1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002dee8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002df1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002df3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002df3b`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x18002d781`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x18002d781`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d990`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d990`

## string_xrefs

- `0x18002d917`: `shell\explorerframe\nsctask.cpp`
- `0x18002de32`: `shell\explorerframe\nsctask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CNscEnumTask::InternalResumeRT(CNscEnumTask *this)
{
  struct _DPA **v2; // r12
  HDPA v3; // rax
  _WORD *v4; // rax
  HRESULT v5; // esi
  int v6; // ecx
  HWND NscHwnd; // rbx
  void **v8; // rax
  __int64 v9; // r8
  HRESULT v10; // eax
  __int64 v11; // rbx
  IStream *v12; // rcx
  HRESULT InterfaceAndReleaseStream; // esi
  __int64 v14; // rcx
  int v15; // r8d
  int v16; // r14d
  const ITEMIDLIST *v17; // r15
  IShellFolder *v18; // rsi
  int v19; // ebx
  IUnknown *v20; // rcx
  char v21; // bl
  int v22; // eax
  int v23; // esi
  IUnknown *v24; // rcx
  LPCITEMIDLIST v25; // rsi
  struct _DPA *v26; // r14
  struct ORDERITEM *v27; // rax
  struct ORDERITEM *v28; // rbx
  FARPROC v29; // rax
  signed int v30; // ecx
  void *v31; // r14
  struct _DPA *v32; // rdx
  int SortColumnsFromFolder; // eax
  struct _DPA *v34; // rbx
  FARPROC ProcAddress; // rax
  unsigned int v36; // r12d
  __int64 v37; // r15
  const ITEMIDLIST *v38; // r13
  CQueueItem *v39; // rax
  CQueueItem *v40; // rbx
  LPITEMIDLIST v41; // rax
  signed int v42; // r13d
  int v43; // r12d
  __int64 *v44; // rcx
  __int64 v45; // rax
  CQueueItem *v46; // r15
  struct IUnknownVtbl *lpVtbl; // rax
  __int64 v48; // rcx
  IBindCtx *v49; // rcx
  int v51; // ebx
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // r8
  int v55; // eax
  HMODULE v56; // rcx
  HMODULE v57; // rcx
  LPCITEMIDLIST v58; // rbx
  __int64 v59; // rbx
  int ppv; // [rsp+20h] [rbp-E0h]
  void **ppva; // [rsp+20h] [rbp-E0h]
  LPCITEMIDLIST *ppidlLast; // [rsp+28h] [rbp-D8h]
  unsigned int v63; // [rsp+70h] [rbp-90h] BYREF
  IUnknown *punkSite; // [rsp+78h] [rbp-88h] BYREF
  DWORD pcbData; // [rsp+80h] [rbp-80h] BYREF
  IUnknown *punk; // [rsp+88h] [rbp-78h] BYREF
  LPCITEMIDLIST pidl; // [rsp+90h] [rbp-70h] BYREF
  IShellFolder *psfParent; // [rsp+98h] [rbp-68h] BYREF
  int v69; // [rsp+A0h] [rbp-60h] BYREF
  IBindCtx *pbc; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v71; // [rsp+B0h] [rbp-50h] BYREF
  LPCITEMIDLIST v72; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v73; // [rsp+C0h] [rbp-40h] BYREF
  int v74; // [rsp+C8h] [rbp-38h] BYREF
  LPCITEMIDLIST v75; // [rsp+D0h] [rbp-30h]
  __int64 v76; // [rsp+D8h] [rbp-28h]
  __int64 v77[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v78; // [rsp+F0h] [rbp-10h]
  __int128 v79; // [rsp+100h] [rbp+0h]
  __int64 v80; // [rsp+110h] [rbp+10h]
  void *v81; // [rsp+118h] [rbp+18h]
  __int64 v82; // [rsp+120h] [rbp+20h]
  __int64 v83; // [rsp+128h] [rbp+28h]
  __int64 v84; // [rsp+130h] [rbp+30h]
  CQueueItem *v85; // [rsp+138h] [rbp+38h]
  __int128 Buf1; // [rsp+140h] [rbp+40h] BYREF
  int v87; // [rsp+150h] [rbp+50h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  if ( !CNscEnumTask::s_dwMaxItems )
  {
    pcbData = 4;
    if ( SHRegGetValueFromHKCUHKLM(
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
           L"PartialExpandLimit",
           24,
           0,
           &CNscEnumTask::s_dwMaxItems,
           &pcbData)
      || !CNscEnumTask::s_dwMaxItems )
    {
      CNscEnumTask::s_dwMaxItems = 100;
    }
  }
  v2 = (struct _DPA **)((char *)this + 136);
  v3 = DPA_Create(2);
  *((_QWORD *)this + 17) = v3;
  if ( !v3 )
    goto LABEL_132;
  psfParent = 0;
  pbc = 0;
  v4 = (_WORD *)*((_QWORD *)this + 10);
  if ( (!v4 || !*v4) && (*((_BYTE *)this + 152) & 0x10) != 0 )
  {
    Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(&pbc);
    v55 = _CreatePropertyBagBindCtx<int>(v53, v52, v54, &pbc);
    if ( v55 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1E5,
        (unsigned int)"shell\\explorerframe\\nsctask.cpp",
        (const char *)(unsigned int)v55,
        ppv);
  }
  v5 = SHBindToObject(
         0,
         *((LPCITEMIDLIST *)this + 10),
         pbc,
         &GUID_000214e6_0000_0000_c000_000000000046,
         (void **)&psfParent);
  if ( v5 >= 0 )
  {
    v6 = *((_DWORD *)this + 38);
    if ( (v6 & 2) != 0 || (v6 & 0x21) != 0x21 )
    {
      NscHwnd = 0;
      if ( (v6 & 1) == 0 )
      {
        punk = 0;
        if ( (int)IUnknown_QueryObject(
                    (struct IUnknown *)psfParent,
                    &OID_AutoExpandInNSC,
                    &GUID_498175a5_67a8_4e7d_b666_b0fb9d029b6b,
                    (void **)&punk) >= 0 )
        {
          ((void (__fastcall *)(IUnknown *))punk->lpVtbl[1].QueryInterface)(punk);
          ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
        }
      }
    }
    else
    {
      NscHwnd = CNscLock::GetNscHwnd(*((CNscLock **)this + 9));
    }
    v73 = 0;
    v8 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ISyncRootManager>>(&v73);
    v5 = SHCreateItemFromIDList(*((LPCITEMIDLIST *)this + 10), &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v8);
    if ( v5 < 0 )
      goto LABEL_77;
    v9 = *((_DWORD *)this + 38) >> 5;
    LOBYTE(v9) = (*((_DWORD *)this + 38) & 0x20) != 0;
    v5 = VerifyAndDownloadCloudItem(v73, NscHwnd, v9);
    if ( v5 < 0 )
      goto LABEL_77;
    punk = 0;
    v10 = ((__int64 (__fastcall *)(IShellFolder *, HWND, _QWORD, IUnknown **))psfParent->lpVtbl->EnumObjects)(
            psfParent,
            NscHwnd,
            *((unsigned int *)this + 27),
            &punk);
    v5 = v10;
    if ( !v10 )
    {
      v71 = 0;
      if ( ((__int64 (__fastcall *)(IShellFolder *, GUID *, __int64 *))psfParent->lpVtbl->QueryInterface)(
             psfParent,
             &GUID_711b2cfd_93d1_422b_bdf4_69be923f2449,
             &v71) >= 0 )
      {
        IUnknown_SetSite(punk, (IUnknown *)this + 1);
        v14 = v71;
      }
      else
      {
        v11 = *((_QWORD *)this + 18);
        if ( !v11 )
          goto LABEL_18;
        *((_QWORD *)this + 18) = 0;
        punkSite = 0;
        if ( *(_DWORD *)(v11 + 24) == 2 )
        {
          InterfaceAndReleaseStream = *(_QWORD *)(v11 + 32)
                                    ? (*(__int64 (__fastcall **)(_QWORD, GUID *, IUnknown **))(**(_QWORD **)(v11 + 32)
                                                                                             + 24LL))(
                                        *(_QWORD *)(v11 + 32),
                                        &GUID_00000000_0000_0000_c000_000000000046,
                                        &punkSite)
                                    : -2147024809;
        }
        else
        {
          v12 = *(IStream **)(v11 + 16);
          *(_QWORD *)(v11 + 16) = 0;
          InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(
                                        v12,
                                        &GUID_00000000_0000_0000_c000_000000000046,
                                        (LPVOID *)&punkSite);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        if ( InterfaceAndReleaseStream < 0 )
          goto LABEL_18;
        IUnknown_SetSite(punk, punkSite);
        v14 = (__int64)punkSite;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
LABEL_18:
      v5 = 0;
      v74 = 0;
      pidl = 0;
      while ( 1 )
      {
        if ( ((unsigned int (__fastcall *)(IUnknown *, __int64, LPCITEMIDLIST *, int *))punk->lpVtbl[1].QueryInterface)(
               punk,
               1,
               &pidl,
               &v74) )
        {
LABEL_51:
          if ( v5 < 0 )
            goto LABEL_75;
          v31 = 0;
          v81 = 0;
          v82 = 0;
          v83 = 0;
          v84 = 0;
          v78 = 0;
          v79 = 0;
          v80 = 0;
          v77[1] = (__int64)psfParent;
          v77[0] = 0;
          v32 = (struct _DPA *)*((_QWORD *)this + 14);
          if ( v32 && *(int *)v32 > 0 )
          {
            OrderList_Merge(
              *v2,
              v32,
              v15,
              (__int64)v77,
              (void (*)(void *, const struct _ITEMID_CHILD *))ppva,
              ppidlLast);
            LODWORD(v77[0]) = 1;
          }
          else
          {
            punkSite = 0;
            if ( ((__int64 (__fastcall *)(IShellFolder *, GUID *, IUnknown **))psfParent->lpVtbl->QueryInterface)(
                   psfParent,
                   &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
                   &punkSite) >= 0 )
            {
              v63 = 0;
              v69 = 0;
              pcbData = 0;
              if ( ((int (__fastcall *)(IUnknown *, _QWORD, unsigned int *, int *))punkSite->lpVtbl[5].QueryInterface)(
                     punkSite,
                     0,
                     &v63,
                     &v69) >= 0
                && v63 )
              {
                Buf1 = 0;
                v87 = 0;
                if ( ((int (__fastcall *)(IUnknown *, _QWORD, __int128 *))punkSite->lpVtbl[6].AddRef)(
                       punkSite,
                       v63,
                       &Buf1) >= 0
                  && (v87 != 26 || memcmp_0(&Buf1, PKEY_Order, 0x10u)) )
                {
                  LODWORD(v77[0]) = 0;
                  *(_QWORD *)&v79 = v63;
                }
              }
              else
              {
                SortColumnsFromFolder = _GetSortColumnsFromFolder(*((LPCITEMIDLIST *)this + 10));
                v31 = v81;
                if ( SortColumnsFromFolder >= 0 )
                {
                  *((_QWORD *)&v79 + 1) = v81;
                  LODWORD(v80) = pcbData;
                  LODWORD(v77[0]) = 3;
                }
              }
              ((void (__fastcall *)(IUnknown *))punkSite->lpVtbl->Release)(punkSite);
            }
          }
          v34 = *v2;
          if ( *v2 )
          {
            ProcAddress = (FARPROC)qword_180291238;
            if ( qword_180291238 == -1 )
            {
              v56 = g_hinstCC;
              if ( g_hinstCC || (DelayLoadCC(0), (v56 = g_hinstCC) != 0) )
                ProcAddress = GetProcAddress(v56, (LPCSTR)0x152);
              else
                ProcAddress = 0;
              qword_180291238 = (__int64)ProcAddress;
            }
            if ( ProcAddress )
              ((void (__fastcall *)(struct _DPA *, __int64 (__fastcall *)(struct ORDERITEM *, struct ORDERITEM *, __int64), __int64 *))ProcAddress)(
                v34,
                DPA_OrderItemCompare,
                v77);
          }
          OrderList_Reorder(*v2);
          v36 = *((_DWORD *)this + 38);
          LODWORD(punkSite) = (v36 >> 2) & 1;
          LODWORD(v72) = (v36 >> 1) & 1;
          v63 = *((_DWORD *)this + 33);
          pcbData = *((_DWORD *)this + 32);
          v75 = (LPCITEMIDLIST)*((_QWORD *)this + 15);
          v69 = *((_DWORD *)this + 26);
          v37 = *((_QWORD *)this + 12);
          v76 = *((_QWORD *)this + 11);
          v38 = (const ITEMIDLIST *)*((_QWORD *)this + 10);
          v39 = (CQueueItem *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
          v40 = v39;
          v85 = v39;
          if ( !v39 )
            goto LABEL_73;
          memset_0(v39, 0, 0x60u);
          CQueueItem::CQueueItem(v40);
          *(_QWORD *)v40 = &CNscEnumQueueItem::`vftable'{for `IQueueItem2'};
          *((_QWORD *)v40 + 1) = &CNscInfoTipQueueItem::`vftable'{for `IQueryContinue'};
          *((_QWORD *)v40 + 4) = 0;
          if ( v38 )
          {
            v41 = ILClone(v38);
            v42 = v41 == 0 ? 0x8007000E : 0;
            *((_QWORD *)v40 + 3) = v41;
            if ( v41 )
            {
              v43 = v36 & 1;
              *((_QWORD *)v40 + 5) = ILCloneFirst(v75);
              v44 = (__int64 *)((char *)this + 136);
              if ( this == (CNscEnumTask *)-136LL )
              {
                v45 = 0;
              }
              else
              {
                v45 = *v44;
                *v44 = 0;
              }
              *((_QWORD *)v40 + 4) = v45;
              *((_DWORD *)v40 + 16) = v69;
              *((_DWORD *)v40 + 17) = pcbData;
              *((_DWORD *)v40 + 18) = v63;
              *((_DWORD *)v40 + 19) = (_DWORD)v72;
              *((_DWORD *)v40 + 20) = (_DWORD)punkSite;
              *((_DWORD *)v40 + 21) = v43;
              *((_DWORD *)v40 + 22) = 0;
              if ( v37 )
              {
                *((_QWORD *)v40 + 7) = v37;
                _InterlockedIncrement((volatile signed __int32 *)(v37 + 56));
              }
              *((_QWORD *)v40 + 6) = v76;
              v46 = v40;
              (*(void (__fastcall **)(CQueueItem *))(*(_QWORD *)v40 + 8LL))(v40);
LABEL_71:
              (*(void (__fastcall **)(CQueueItem *))(*(_QWORD *)v40 + 16LL))(v40);
              if ( v42 >= 0 )
              {
                (*(void (__fastcall **)(_QWORD, CQueueItem *))(**((_QWORD **)this + 9) + 8LL))(
                  *((_QWORD *)this + 9),
                  v46);
                (*(void (__fastcall **)(CQueueItem *))(*(_QWORD *)v46 + 16LL))(v46);
              }
LABEL_73:
              if ( v31 )
                CoTaskMemFree(v31);
LABEL_75:
              IUnknown_SetSite(punk, 0);
              lpVtbl = punk->lpVtbl;
LABEL_76:
              ((void (*)(void))lpVtbl->Release)();
              goto LABEL_77;
            }
          }
          else
          {
            *((_QWORD *)v40 + 3) = 0;
            v42 = -2147024809;
          }
          v46 = 0;
          goto LABEL_71;
        }
        if ( (*((_BYTE *)this + 108) & 0x40) == 0 && (*((_BYTE *)this + 152) & 8) == 0 )
        {
          v72 = 0;
          punkSite = 0;
          if ( SHBindToFolderIDListParentEx(
                 psfParent,
                 pidl,
                 0,
                 &GUID_000214e6_0000_0000_c000_000000000046,
                 (void **)&punkSite,
                 &v72) >= 0 )
          {
            v51 = 0;
            v63 = 1614807040;
            if ( ((int (__fastcall *)(IUnknown *, __int64, LPCITEMIDLIST *, unsigned int *))punkSite->lpVtbl[3].QueryInterface)(
                   punkSite,
                   1,
                   &v72,
                   &v63) >= 0 )
              v51 = v63 & 0x60400000;
            ((void (__fastcall *)(IUnknown *))punkSite->lpVtbl->Release)(punkSite);
            if ( v51 == 1614807040 )
              goto LABEL_45;
          }
        }
        if ( (*((_BYTE *)this + 152) & 0x10) != 0 )
        {
          v16 = *((_DWORD *)this + 27);
          v17 = pidl;
          v18 = psfParent;
          v19 = 0;
          punkSite = 0;
          if ( ((__int64 (__fastcall *)(IShellFolder *, GUID *, IUnknown **))psfParent->lpVtbl->QueryInterface)(
                 psfParent,
                 &GUID_e9701183_e6b3_4ff2_8568_813615fec7be,
                 &punkSite) >= 0 )
          {
            v63 = 0;
            if ( ((int (__fastcall *)(IUnknown *, __int64, unsigned int *))punkSite->lpVtbl[1].QueryInterface)(
                   punkSite,
                   1,
                   &v63) >= 0 )
              v19 = v63 & 1;
          }
          v20 = punkSite;
          if ( punkSite )
          {
            punkSite = 0;
            ((void (__fastcall *)(IUnknown *))v20->lpVtbl->Release)(v20);
          }
          if ( v19 )
          {
            v21 = 1;
            punkSite = 0;
            if ( SHCreateItemWithParent(0, v18, v17, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, (void **)&punkSite) >= 0 )
            {
              v63 = 0;
              if ( (v16 & 0x80u) == 0 )
                v21 = ((unsigned int (__fastcall *)(IUnknown *, __int64, unsigned int *))punkSite->lpVtbl[2].QueryInterface)(
                        punkSite,
                        0x80000,
                        &v63) != 0;
              v22 = ((__int64 (__fastcall *)(IUnknown *, __int64, unsigned int *))punkSite->lpVtbl[2].QueryInterface)(
                      punkSite,
                      0x100000,
                      &v63);
              v23 = v22;
              if ( v22 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x1A6,
                  (unsigned int)"shell\\explorerframe\\nsctask.cpp",
                  (const char *)(unsigned int)v22,
                  (int)ppva);
              v21 = v23 != 0 ? v21 : 0;
              pcbData = 0;
              if ( v21
                && ((int (__fastcall *)(IUnknown *, const PROPERTYKEY *, DWORD *))punkSite->lpVtbl[6].Release)(
                     punkSite,
                     &PKEY_IsPinnedToNameSpaceTree,
                     &pcbData) >= 0 )
              {
                v21 &= pcbData != 0;
              }
            }
            v24 = punkSite;
            if ( punkSite )
            {
              punkSite = 0;
              ((void (__fastcall *)(IUnknown *))v24->lpVtbl->Release)(v24);
            }
            if ( !v21 )
              goto LABEL_45;
          }
        }
        v25 = pidl;
        v26 = *v2;
        v27 = (struct ORDERITEM *)LocalAlloc(0x40u, 0x30u);
        v28 = v27;
        if ( v27 )
        {
          *(_QWORD *)v27 = v25;
          *((_DWORD *)v27 + 2) = -1;
          *((_DWORD *)v27 + 3) = 0;
          v29 = (FARPROC)qword_180291248;
          if ( qword_180291248 == -1 )
          {
            v57 = g_hinstCC;
            if ( g_hinstCC || (DelayLoadCC(0), (v57 = g_hinstCC) != 0) )
              v29 = GetProcAddress(v57, (LPCSTR)0x14E);
            else
              v29 = 0;
            qword_180291248 = (__int64)v29;
          }
          if ( v29
            && ((unsigned int (__fastcall *)(struct _DPA *, __int64, struct ORDERITEM *))v29)(v26, 0x7FFFFFFF, v28) != -1 )
          {
            pidl = 0;
LABEL_45:
            if ( (*((_BYTE *)this + 152) & 0x20) != 0
              || (!*v2 ? (v30 = 0) : (v30 = *(_DWORD *)*v2), v30 <= (int)CNscEnumTask::s_dwMaxItems) )
            {
              v5 = 0;
              if ( *((_DWORD *)this + 16) )
              {
                v5 = -2147467259;
                if ( *((_DWORD *)this + 11) == 2 )
                  v5 = -2147483638;
              }
            }
            else
            {
              v5 = -2147467260;
            }
            goto LABEL_50;
          }
          OrderItem_Free(v28, 0);
        }
        v5 = -2147024882;
LABEL_50:
        ILFree((LPITEMIDLIST)pidl);
        if ( v5 < 0 )
          goto LABEL_51;
      }
    }
    if ( v10 == 1 )
    {
      pidl = 0;
      if ( (int)CNscEnumQueueItem_CreateInstance(
                  *((LPCITEMIDLIST *)this + 10),
                  (__int64)this + 136,
                  *((LPCITEMIDLIST *)this + 15),
                  *((_DWORD *)this + 32),
                  *((_DWORD *)this + 33),
                  (*((_DWORD *)this + 38) >> 1) & 1,
                  (*((_DWORD *)this + 38) >> 2) & 1,
                  *((_DWORD *)this + 38) & 1,
                  0,
                  (__int64)&pidl) >= 0 )
      {
        v58 = pidl;
        (*(void (__fastcall **)(_QWORD, LPCITEMIDLIST))(**((_QWORD **)this + 9) + 8LL))(*((_QWORD *)this + 9), pidl);
        lpVtbl = *(struct IUnknownVtbl **)&v58->mkid.cb;
        goto LABEL_76;
      }
    }
LABEL_77:
    ((void (__fastcall *)(IShellFolder *))psfParent->lpVtbl->Release)(psfParent);
    v48 = v73;
    if ( v73 )
    {
      v73 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    }
  }
  v49 = pbc;
  if ( pbc )
  {
    pbc = 0;
    ((void (__fastcall *)(IBindCtx *))v49->lpVtbl->Release)(v49);
  }
  if ( v5 < 0 )
  {
LABEL_132:
    v71 = 0;
    if ( (int)CNscEnumQueueItem_CreateInstance(*((LPCITEMIDLIST *)this + 10), 0, 0, 0, 0, 0, 0, 0, 1, (__int64)&v71) >= 0 )
    {
      v59 = v71;
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 9) + 8LL))(*((_QWORD *)this + 9), v71);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002d5f0  push    rbp
0x18002d5f2  push    rbx
0x18002d5f3  push    rsi
0x18002d5f4  push    rdi
0x18002d5f5  push    r12
0x18002d5f7  push    r13
0x18002d5f9  push    r14
0x18002d5fb  push    r15
0x18002d5fd  lea     rbp, [rsp-68h]
0x18002d602  sub     rsp, 168h
0x18002d609  mov     rax, cs:__security_cookie
0x18002d610  xor     rax, rsp
0x18002d613  mov     [rbp+0A0h+var_48], rax
0x18002d617  mov     rdi, rcx
0x18002d61a  xor     r13d, r13d
0x18002d61d  cmp     cs:?s_dwMaxItems@CNscEnumTask@@0KA, r13d; ulong CNscEnumTask::s_dwMaxItems
0x18002d624  jz      loc_18002DF8B
0x18002d62a  lea     r12, [rdi+88h]
0x18002d631  mov     ecx, 2; cItemGrow
0x18002d636  call    DPA_Create
0x18002d63b  mov     [r12], rax
0x18002d63f  test    rax, rax
0x18002d642  jz      loc_18002E166
0x18002d648  mov     [rbp+0A0h+psfParent], r13
0x18002d64c  mov     [rbp+0A0h+pbc], r13
0x18002d650  mov     rax, [rdi+50h]
0x18002d654  test    rax, rax
0x18002d657  jz      loc_18002DE01
0x18002d65d  cmp     [rax], r13w
0x18002d661  jz      loc_18002DE01
0x18002d667  lea     rax, [rbp+0A0h+psfParent]
0x18002d66b  mov     [rsp+1A0h+ppv], rax; ppv
0x18002d670  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18002d677  mov     r8, [rbp+0A0h+pbc]; pbc
0x18002d67b  mov     rdx, [rdi+50h]; pidl
0x18002d67f  xor     ecx, ecx; psf
0x18002d681  call    cs:__imp_SHBindToObject
0x18002d687  mov     esi, eax
0x18002d689  test    eax, eax
0x18002d68b  js      loc_18002DD21
0x18002d691  mov     ecx, [rdi+98h]
0x18002d697  test    cl, 2
0x18002d69a  jz      loc_18002DE75
0x18002d6a0  mov     rbx, r13
0x18002d6a3  test    cl, 1
0x18002d6a6  jz      loc_18002DFE2
0x18002d6ac  mov     [rbp+0A0h+var_E0], r13
0x18002d6b0  lea     rcx, [rbp+0A0h+var_E0]
0x18002d6b4  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ISyncRootManager>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ISyncRootManager>>)
0x18002d6b9  mov     r8, rax; ppv
0x18002d6bc  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18002d6c3  mov     rcx, [rdi+50h]; pidl
0x18002d6c7  call    cs:__imp_SHCreateItemFromIDList
0x18002d6cd  mov     esi, eax
0x18002d6cf  test    eax, eax
0x18002d6d1  js      loc_18002DCF6
0x18002d6d7  mov     r8d, [rdi+98h]
0x18002d6de  shr     r8d, 5
0x18002d6e2  and     r8b, 1
0x18002d6e6  mov     rdx, rbx
0x18002d6e9  mov     rcx, [rbp+0A0h+var_E0]
0x18002d6ed  call    ?VerifyAndDownloadCloudItem@@YAJPEAUIShellItem@@PEAUHWND__@@_NW4VerifyDownloadSource@@@Z; VerifyAndDownloadCloudItem(IShellItem *,HWND__ *,bool,VerifyDownloadSource)
0x18002d6f2  mov     esi, eax
0x18002d6f4  test    eax, eax
0x18002d6f6  js      loc_18002DCF6
0x18002d6fc  mov     [rbp+0A0h+punk], r13
0x18002d700  mov     rcx, [rbp+0A0h+psfParent]
0x18002d704  mov     rax, [rcx]
0x18002d707  lea     r9, [rbp+0A0h+punk]
0x18002d70b  mov     r8d, [rdi+6Ch]
0x18002d70f  mov     rdx, rbx
0x18002d712  mov     rax, [rax+20h]
0x18002d716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d71b  mov     esi, eax
0x18002d71d  test    eax, eax
0x18002d71f  jnz     loc_18002E02E
0x18002d725  mov     [rbp+0A0h+var_F0], r13
0x18002d729  mov     rcx, [rbp+0A0h+psfParent]
0x18002d72d  mov     rax, [rcx]
0x18002d730  lea     r8, [rbp+0A0h+var_F0]
0x18002d734  lea     rdx, _GUID_711b2cfd_93d1_422b_bdf4_69be923f2449
0x18002d73b  mov     rax, [rax]
0x18002d73e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d743  test    eax, eax
0x18002d745  jns     loc_18002E0CD
0x18002d74b  mov     rbx, [rdi+90h]
0x18002d752  test    rbx, rbx
0x18002d755  jz      short loc_18002D7BD
0x18002d757  mov     [rdi+90h], r13
0x18002d75e  mov     [rsp+1A0h+punkSite], r13
0x18002d763  cmp     dword ptr [rbx+18h], 2
0x18002d767  jz      loc_18002DE93
0x18002d76d  mov     rcx, [rbx+10h]; pStm
0x18002d771  mov     [rbx+10h], r13
0x18002d775  lea     r8, [rsp+1A0h+punkSite]; ppv
0x18002d77a  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; iid
0x18002d781  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x18002d787  mov     esi, eax
0x18002d789  mov     rdx, [rbx]
0x18002d78c  mov     rcx, rbx
0x18002d78f  mov     rax, [rdx+10h]
0x18002d793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d798  nop
0x18002d799  test    esi, esi
0x18002d79b  js      short loc_18002D7BD
0x18002d79d  mov     rdx, [rsp+1A0h+punkSite]; punkSite
0x18002d7a2  mov     rcx, [rbp+0A0h+punk]; punk
0x18002d7a6  call    cs:__imp_IUnknown_SetSite
0x18002d7ac  mov     rcx, [rsp+1A0h+punkSite]
0x18002d7b1  mov     rax, [rcx]
0x18002d7b4  mov     rax, [rax+10h]
0x18002d7b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7bd  mov     esi, r13d
0x18002d7c0  mov     [rbp+0A0h+var_D8], r13d
0x18002d7c4  mov     [rbp+0A0h+pidl], r13
0x18002d7c8  mov     r14d, 60400000h
0x18002d7ce  mov     rcx, [rbp+0A0h+punk]
0x18002d7d2  mov     rax, [rcx]
0x18002d7d5  lea     r9, [rbp+0A0h+var_D8]
0x18002d7d9  lea     r8, [rbp+0A0h+pidl]
0x18002d7dd  mov     edx, 1
0x18002d7e2  mov     rax, [rax+18h]
0x18002d7e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7eb  test    eax, eax
0x18002d7ed  jnz     loc_18002DA30
0x18002d7f3  test    byte ptr [rdi+6Ch], 40h
0x18002d7f7  jnz     short loc_18002D806
0x18002d7f9  test    byte ptr [rdi+98h], 8
0x18002d800  jz      loc_18002DD65
0x18002d806  test    byte ptr [rdi+98h], 10h
0x18002d80d  jz      loc_18002D980
0x18002d813  mov     r14d, [rdi+6Ch]
0x18002d817  mov     r15, [rbp+0A0h+pidl]
0x18002d81b  mov     rsi, [rbp+0A0h+psfParent]
0x18002d81f  mov     ebx, r13d
0x18002d822  mov     [rsp+1A0h+punkSite], r13
0x18002d827  mov     rax, [rsi]
0x18002d82a  lea     r8, [rsp+1A0h+punkSite]
0x18002d82f  lea     rdx, _GUID_e9701183_e6b3_4ff2_8568_813615fec7be
0x18002d836  mov     rcx, rsi
0x18002d839  mov     rax, [rax]
0x18002d83c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d841  test    eax, eax
0x18002d843  js      short loc_18002D870
0x18002d845  mov     rcx, [rsp+1A0h+punkSite]
0x18002d84a  mov     [rsp+1A0h+var_130], r13d
0x18002d84f  mov     rax, [rcx]
0x18002d852  lea     r8, [rsp+1A0h+var_130]
0x18002d857  mov     edx, 1
0x18002d85c  mov     rax, [rax+18h]
0x18002d860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d865  test    eax, eax
0x18002d867  js      short loc_18002D870
0x18002d869  mov     ebx, [rsp+1A0h+var_130]
0x18002d86d  and     ebx, 1
0x18002d870  mov     rcx, [rsp+1A0h+punkSite]
0x18002d875  test    rcx, rcx
0x18002d878  jz      short loc_18002D88C
0x18002d87a  mov     [rsp+1A0h+punkSite], r13
0x18002d87f  mov     rax, [rcx]
0x18002d882  mov     rax, [rax+10h]
0x18002d886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d88b  nop
0x18002d88c  test    ebx, ebx
0x18002d88e  jz      loc_18002D980
0x18002d894  mov     bl, 1
0x18002d896  mov     [rsp+1A0h+punkSite], r13
0x18002d89b  lea     rax, [rsp+1A0h+punkSite]
0x18002d8a0  mov     [rsp+1A0h+ppv], rax; void (*)(void *, const struct _ITEMID_CHILD *)
0x18002d8a5  lea     r9, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x18002d8ac  mov     r8, r15; pidl
0x18002d8af  mov     rdx, rsi; psfParent
0x18002d8b2  xor     ecx, ecx; pidlParent
0x18002d8b4  call    cs:__imp_SHCreateItemWithParent
0x18002d8ba  test    eax, eax
0x18002d8bc  js      loc_18002D960
0x18002d8c2  mov     [rsp+1A0h+var_130], r13d
0x18002d8c7  test    r14b, r14b
0x18002d8ca  js      short loc_18002D8EC
0x18002d8cc  mov     rcx, [rsp+1A0h+punkSite]
0x18002d8d1  mov     rax, [rcx]
0x18002d8d4  lea     r8, [rsp+1A0h+var_130]
0x18002d8d9  mov     edx, 80000h
0x18002d8de  mov     rax, [rax+30h]
0x18002d8e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d8e7  test    eax, eax
0x18002d8e9  setnz   bl
0x18002d8ec  mov     rcx, [rsp+1A0h+punkSite]
0x18002d8f1  mov     rax, [rcx]
0x18002d8f4  lea     r8, [rsp+1A0h+var_130]
0x18002d8f9  mov     edx, 100000h
0x18002d8fe  mov     rax, [rax+30h]
0x18002d902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d907  mov     esi, eax
0x18002d909  mov     rcx, [rbp+0A8h]; this
0x18002d910  test    eax, eax
0x18002d912  jns     short loc_18002D928
0x18002d914  mov     r9d, eax; char *
0x18002d917  lea     r8, aShellExplorerf_3; "shell\\explorerframe\\nsctask.cpp"
0x18002d91e  mov     edx, 1A6h; void *
0x18002d923  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002d928  neg     esi
0x18002d92a  sbb     al, al
0x18002d92c  and     bl, al
0x18002d92e  mov     [rbp+0A0h+pcbData], r13d
0x18002d932  jz      short loc_18002D960
0x18002d934  mov     rcx, [rsp+1A0h+punkSite]
0x18002d939  mov     rax, [rcx]
0x18002d93c  lea     r8, [rbp+0A0h+pcbData]
0x18002d940  lea     rdx, PKEY_IsPinnedToNameSpaceTree
0x18002d947  mov     rax, [rax+0A0h]
0x18002d94e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d953  test    eax, eax
0x18002d955  js      short loc_18002D960
0x18002d957  cmp     [rbp+0A0h+pcbData], r13d
0x18002d95b  setnz   al
0x18002d95e  and     bl, al
0x18002d960  mov     rcx, [rsp+1A0h+punkSite]
0x18002d965  test    rcx, rcx
0x18002d968  jz      short loc_18002D97C
0x18002d96a  mov     [rsp+1A0h+punkSite], r13
0x18002d96f  mov     rax, [rcx]
0x18002d972  mov     rax, [rax+10h]
0x18002d976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d97b  nop
0x18002d97c  test    bl, bl
0x18002d97e  jz      short loc_18002D9E7
0x18002d980  mov     rsi, [rbp+0A0h+pidl]
0x18002d984  mov     r14, [r12]
0x18002d988  mov     edx, 30h ; '0'; uBytes
0x18002d98d  lea     ecx, [rdx+10h]; uFlags
0x18002d990  call    cs:__imp_LocalAlloc
0x18002d996  mov     rbx, rax
0x18002d999  test    rax, rax
0x18002d99c  jz      loc_18002DE6B
0x18002d9a2  mov     [rax], rsi
0x18002d9a5  mov     dword ptr [rax+8], 0FFFFFFFFh
0x18002d9ac  mov     [rax+0Ch], r13d
0x18002d9b0  mov     rax, cs:qword_180291248
0x18002d9b7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d9bb  jz      loc_18002DEFA
0x18002d9c1  test    rax, rax
0x18002d9c4  jz      loc_18002DE61
0x18002d9ca  mov     r8, rbx
0x18002d9cd  mov     edx, 7FFFFFFFh
0x18002d9d2  mov     rcx, r14
0x18002d9d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d9da  cmp     eax, 0FFFFFFFFh
0x18002d9dd  jz      loc_18002DE61
0x18002d9e3  mov     [rbp+0A0h+pidl], r13
0x18002d9e7  test    byte ptr [rdi+98h], 20h
0x18002d9ee  jnz     short loc_18002DA0B
0x18002d9f0  mov     rax, [r12]
0x18002d9f4  test    rax, rax
0x18002d9f7  jz      loc_18002DDF2
0x18002d9fd  mov     ecx, [rax]
0x18002d9ff  cmp     ecx, cs:?s_dwMaxItems@CNscEnumTask@@0KA; ulong CNscEnumTask::s_dwMaxItems
0x18002da05  jg      loc_18002E0E4
0x18002da0b  mov     esi, r13d
0x18002da0e  cmp     [rdi+40h], r13d
0x18002da12  jnz     loc_18002E0EE
0x18002da18  mov     rcx, [rbp+0A0h+pidl]; pidl
0x18002da1c  call    cs:__imp_ILFree
0x18002da22  test    esi, esi
0x18002da24  mov     r14d, 60400000h
0x18002da2a  jns     loc_18002D7CE
0x18002da30  test    esi, esi
0x18002da32  js      loc_18002DCDA
0x18002da38  mov     r14, r13
0x18002da3b  mov     [rbp+0A0h+var_88], r13
0x18002da3f  mov     [rbp+0A0h+var_80], r13
0x18002da43  mov     [rbp+0A0h+var_78], r13
0x18002da47  mov     [rbp+0A0h+var_70], r13
0x18002da4b  xorps   xmm0, xmm0
0x18002da4e  xor     eax, eax
0x18002da50  movups  xmmword ptr [rbp+0A0h+var_C0], xmm0
0x18002da54  movups  [rbp+0A0h+var_B0], xmm0
0x18002da58  movups  [rbp+0A0h+var_A0], xmm0
0x18002da5c  mov     [rbp+0A0h+var_90], rax
0x18002da60  mov     rcx, [rbp+0A0h+psfParent]
0x18002da64  mov     [rbp+0A0h+var_C0+8], rcx
0x18002da68  mov     dword ptr [rbp+0A0h+var_C0], r13d
0x18002da6c  mov     rdx, [rdi+70h]; hdpaSrc
0x18002da70  test    rdx, rdx
0x18002da73  jz      short loc_18002DA7E
0x18002da75  cmp     [rdx], r13d
0x18002da78  jg      loc_18002DE48
0x18002da7e  mov     [rsp+1A0h+punkSite], r13
0x18002da83  mov     rax, [rcx]
0x18002da86  lea     r8, [rsp+1A0h+punkSite]
0x18002da8b  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x18002da92  mov     rax, [rax]
0x18002da95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da9a  test    eax, eax
0x18002da9c  js      short loc_18002DAFD
0x18002da9e  mov     [rsp+1A0h+var_130], r13d
0x18002daa3  mov     [rbp+0A0h+var_100], r13d
0x18002daa7  mov     [rbp+0A0h+pcbData], r13d
0x18002daab  mov     rcx, [rsp+1A0h+punkSite]
0x18002dab0  mov     rax, [rcx]
  ... truncated ...
```
