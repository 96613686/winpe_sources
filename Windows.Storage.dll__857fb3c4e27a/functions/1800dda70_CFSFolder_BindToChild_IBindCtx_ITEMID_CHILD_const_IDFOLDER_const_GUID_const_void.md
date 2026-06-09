# CFSFolder::_BindToChild(IBindCtx *,_ITEMID_CHILD const *,IDFOLDER const *,_GUID const &,void * *)

- ea: `0x1800dda70`
- end: `0x1800dedad`
- name: `?_BindToChild@CFSFolder@@IEAAJPEAUIBindCtx@@PEFBU_ITEMID_CHILD@@PEFBUIDFOLDER@@AEBU_GUID@@PEAPEAX@Z`
- size: `4925`
- prototype: `__int64 __usercall@<rax>(CFSFolder *__hidden this@<rcx>, struct IBindCtx *@<rdx>, const struct _ITEMID_CHILD *@<r8>, const struct IDFOLDER *@<r9>, IID *riid, void **)`
- caller_count: `1`
- callee_count: `43`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180174660`

## callees

- `0x18000d6cc`
- `0x180043320`
- `0x180047ec0`
- `0x1800495e0`
- `0x180067d10`
- `0x18008c9e0`
- `0x18008e240`
- `0x1800902d0`
- `0x180093d10`
- `0x180093ef0`
- `0x18009d3d4`
- `0x18009d520`
- `0x18009df20`
- `0x1800d13a0`
- `0x1800d3d10`
- `0x1800da5f0`
- `0x1800dd190`
- `0x1800dda70`
- `0x1800dfcf0`
- `0x1800e68c0`
- `0x1801289e0`
- `0x180128a90`
- `0x18016cca0`
- `0x18016cd40`
- `0x180181f30`
- `0x1801b0400`
- `0x1801cff20`
- `0x1801d2fe0`
- `0x1801ed410`
- `0x1801f2ef0`
- `0x180269698`
- `0x180270604`
- `0x1802aef20`
- `0x1802d4c14`
- `0x18030eabc`
- `0x180310f7c`
- `0x1803a4cb0`
- `0x1803a4cd4`
- `0x1803a518c`
- `0x1803a57e0`
- `0x1803a96d9`
- `0x1803aee20`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ded96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800deda1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ded96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800deda1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x1800ddc2d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x1800de17d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x1800de219`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x1800ddc2d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x1800de17d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x1800de219`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800de738`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800de738`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800de701`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800de701`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ddcc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ddcd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ddce3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800de338`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800de42d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800de461`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dea54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800debf1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800debfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dece5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ddcc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ddcd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ddce3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800de338`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800de42d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800de461`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dea54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800debf1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800debfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dece5`
- `SHCORE!__imp_SHManagedCreateStreamOnFile` at `0x1800de513`
- `SHCORE!__imp_SHManagedCreateStreamOnFile` at `0x1800de513`
- `SHCORE!__imp_CreateRandomAccessStreamOnFileWithOptions` at `0x1800de7aa`
- `SHCORE!__imp_CreateRandomAccessStreamOnFileWithOptions` at `0x1800de7aa`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1800de8b9`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1800de8b9`
- `edputil!EdpGetIsManaged` at `0x1800de7b7`
- `edputil!EdpGetIsManaged` at `0x1800de7b7`
- `srpapi!SrpRestoreEnterpriseContext` at `0x1800de7c4`
- `srpapi!SrpRestoreEnterpriseContext` at `0x1800de7c4`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800de36d`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800de36d`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageEx` at `0x1800de9c0`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageEx` at `0x1800dea3d`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageEx` at `0x1800de9c0`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageEx` at `0x1800dea3d`
- `ext-ms-win-com-ole32-l1-1-4!CreateFileMoniker` at `0x1800de322`
- `ext-ms-win-com-ole32-l1-1-4!CreateFileMoniker` at `0x1800de322`

## string_xrefs

- `0x1800de59d`: `RandomAccessStreamMode`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall CFSFolder::_BindToChild(
        CFSFolder *this,
        struct IBindCtx *a2,
        const ITEMIDLIST *a3,
        const struct IDFOLDER *a4,
        IID *riid,
        void **ppv)
{
  CFSFolder *v8; // r12
  int v9; // ebx
  unsigned int v10; // esi
  __int64 v11; // rax
  void **v12; // rdi
  __int64 v13; // rbx
  WCHAR *v14; // rax
  WCHAR *v15; // rdi
  LPITEMIDLIST v16; // rax
  unsigned int v17; // edx
  HRESULT Handler; // r15d
  __int64 v19; // rcx
  IUnknown *v20; // rcx
  __int64 v21; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  const unsigned __int16 *v29; // rax
  HRESULT inited; // ebx
  struct IUnknown *v31; // rax
  struct IUnknown *v32; // r12
  HRESULT FreeThreadedMarshaler; // eax
  CFreeThreadedItemContainer *v34; // rcx
  CShellItem *v35; // rax
  const WCHAR *v36; // rax
  _QWORD *v37; // rax
  _QWORD *v38; // rbx
  LPCOLESTR v39; // rcx
  LPITEMIDLIST v40; // rax
  unsigned int v41; // edx
  CFSPropertyStoreFactory *v42; // rcx
  LPCOLESTR v43; // rcx
  int (__fastcall *v44)(char *, LPCITEMIDLIST, __int64, __int64); // rbx
  __int64 v45; // rax
  CFSFolder *v46; // rcx
  __int64 v47; // rax
  struct IDFOLDER *v48; // rbx
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  HRESULT FileMoniker; // eax
  WCHAR *v53; // rdi
  void *v54; // rcx
  int FileFlagsFromBindCtx; // ebx
  WCHAR *v56; // rcx
  __int64 (__fastcall *v57)(_QWORD, GUID *, WCHAR **); // rbx
  int v58; // eax
  __int64 v59; // rax
  const WCHAR *ExtensionW; // rax
  void **v61; // r8
  PCWSTR v62; // rbx
  WCHAR *v63; // rcx
  __int64 v64; // rax
  struct IUnknown *v65; // rbx
  enum GETPROPERTYSTOREFLAGS v66; // eax
  __int64 (__fastcall *v67)(char *, LPCITEMIDLIST, __int64, __int64); // rbx
  __int64 v68; // rax
  int v69; // ebx
  HRESULT v70; // eax
  struct IUnknown *v71; // rbx
  enum GETPROPERTYSTOREFLAGS v72; // eax
  int v73; // eax
  int Object; // eax
  WCHAR *v75; // rcx
  __int64 (__fastcall ***v76)(_QWORD, IID *, void **); // rcx
  __int64 (__fastcall *v77)(char *, LPCITEMIDLIST, __int64, __int64); // rbx
  __int64 v78; // rax
  WCHAR *v79; // rbx
  WCHAR *v80; // rcx
  int pdwType; // [rsp+20h] [rbp-E0h]
  WCHAR *pwcsName; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v83)(_QWORD, IID *, void **); // [rsp+50h] [rbp-B0h] BYREF
  WCHAR *v84; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v85; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v86[4]; // [rsp+68h] [rbp-98h] BYREF
  _WORD *v87; // [rsp+78h] [rbp-88h]
  int v88; // [rsp+80h] [rbp-80h]
  int v89; // [rsp+84h] [rbp-7Ch]
  __int64 v90; // [rsp+88h] [rbp-78h]
  LPCOLESTR lpszPathName; // [rsp+90h] [rbp-70h] BYREF
  DWORD pcbData[2]; // [rsp+98h] [rbp-68h] BYREF
  LPCITEMIDLIST pidl; // [rsp+A0h] [rbp-60h] BYREF
  struct IDFOLDER *v94; // [rsp+A8h] [rbp-58h] BYREF
  PCWSTR pszPath[3]; // [rsp+B0h] [rbp-50h] BYREF
  IUnknown *punk; // [rsp+C8h] [rbp-38h] BYREF
  HANDLE hObject[2]; // [rsp+D0h] [rbp-30h] BYREF
  void *v98; // [rsp+E0h] [rbp-20h]
  _QWORD v99[2]; // [rsp+F0h] [rbp-10h] BYREF
  LPVOID v100; // [rsp+100h] [rbp+0h]
  LPVOID v101; // [rsp+108h] [rbp+8h]
  LPVOID pv; // [rsp+120h] [rbp+20h]
  IUnknown *ppunk; // [rsp+128h] [rbp+28h] BYREF
  __int64 v104; // [rsp+130h] [rbp+30h]
  __int64 v105; // [rsp+138h] [rbp+38h]
  _WORD pvData[312]; // [rsp+3A0h] [rbp+2A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+668h] [rbp+568h]

  v94 = a4;
  pidl = a3;
  v8 = this;
  hObject[0] = this;
  *ppv = 0;
  CFileSysItemString::CFileSysItemString((CFileSysItemString *)v99, this, (const struct _ITEMIDLIST_RELATIVE *)a3, a4);
  punk = 0;
  pwcsName = 0;
  if ( a2
    && ((int (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, WCHAR **))a2->lpVtbl->GetObjectParam)(
         a2,
         L"Delegate Object Creation",
         &pwcsName) >= 0
    && (v9 = (**(__int64 (__fastcall ***)(WCHAR *, GUID *, IUnknown **))pwcsName)(
               pwcsName,
               &GUID_00000000_0000_0000_c000_000000000046,
               &punk),
        (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)pwcsName + 16LL))(pwcsName),
        v9 >= 0) )
  {
    IUnknown_Set(&ppunk, punk);
    v10 = 32;
  }
  else
  {
    v10 = 32;
    if ( !a2 )
      goto LABEL_7;
  }
  *(_OWORD *)pszPath = 0x10u;
  if ( ((int (__fastcall *)(struct IBindCtx *, PCWSTR *))a2->lpVtbl->GetBindOptions)(a2, pszPath) >= 0 )
    v10 = (unsigned int)pszPath[1];
LABEL_7:
  v11 = *(_QWORD *)&IID_IPropertyStoreFactory.Data1 - *(_QWORD *)&riid->Data1;
  if ( *(_QWORD *)&IID_IPropertyStoreFactory.Data1 == *(_QWORD *)&riid->Data1 )
    v11 = *(_QWORD *)IID_IPropertyStoreFactory.Data4 - *(_QWORD *)riid->Data4;
  if ( !v11 )
  {
    v12 = (void **)((char *)v8 + 904);
    v13 = *((_QWORD *)v8 + 113);
    if ( v13 )
    {
      *ppv = 0;
      v14 = (WCHAR *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
      v15 = v14;
      pszPath[0] = v14;
      if ( v14 )
      {
        *(_QWORD *)v14 = &CFSPropertyStoreFactory::`vftable'{for `IDelayedPropertyStoreFactory'};
        *((_QWORD *)v14 + 1) = &CFSPropertyStoreFactory::`vftable'{for `IFreeThreadedItemContainer'};
        *((_DWORD *)v14 + 4) = 1;
        *((_QWORD *)v14 + 4) = 0;
        *((_QWORD *)v14 + 5) = 0;
        *((_BYTE *)v14 + 49) = 0;
        *((_QWORD *)v14 + 3) = v13;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
        v16 = ILCloneFirst(pidl);
        *((_QWORD *)v15 + 4) = v16;
        if ( v16 )
          Handler = QISearch(v15, &stru_18067F260, riid, ppv);
        else
          Handler = -2147024882;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15 + 4, 0xFFFFFFFF) == 1 )
          CFSPropertyStoreFactory::`scalar deleting destructor'((CFSPropertyStoreFactory *)v15, v17);
      }
      else
      {
        Handler = -2147024882;
      }
    }
    else
    {
      v84 = 0;
      Handler = (**(__int64 (__fastcall ***)(CFSFolder *, GUID *, WCHAR **))v8)(
                  v8,
                  &GUID_127f6acb_7e78_4368_83a4_ed1de72baca6,
                  &v84);
      if ( Handler < 0 )
        goto LABEL_85;
      pwcsName = v84;
      *v12 = 0;
      lpszPathName = 0;
      inited = -2147024882;
      v31 = (struct IUnknown *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
      v32 = v31;
      pszPath[0] = (PCWSTR)v31;
      if ( v31 )
      {
        v31[4].lpVtbl = 0;
        v31->lpVtbl = (struct IUnknownVtbl *)&CFreeThreadedItemContainer::`vftable'{for `IFreeThreadedItemContainer'};
        v31[1].lpVtbl = (struct IUnknownVtbl *)&CFreeThreadedItemContainer::`vftable'{for `IInitializeWithItem'};
        v31[2].lpVtbl = (struct IUnknownVtbl *)&CFreeThreadedItemContainer::`vftable'{for `IPersistIDList'};
        v31[3].lpVtbl = (struct IUnknownVtbl *)&CFreeThreadedItemContainer::`vftable'{for `CFreeThreadedObject'};
        LODWORD(v31[5].lpVtbl) = 1;
        v31[8].lpVtbl = 0;
        v31[6].lpVtbl = 0;
        v31[7].lpVtbl = 0;
        v31[9].lpVtbl = 0;
        if ( !memcmp_0(&GUID_0c904b4a_164a_4d81_92d9_a5fc866f7fb8, &IID_IMarshal, 0x10u) )
          FreeThreadedMarshaler = CFreeThreadedObject::GetFreeThreadedMarshaler(
                                    (CFreeThreadedObject *)&v32[3],
                                    v32,
                                    &GUID_0c904b4a_164a_4d81_92d9_a5fc866f7fb8,
                                    (void **)&lpszPathName);
        else
          FreeThreadedMarshaler = QISearch(
                                    v32,
                                    &`CFreeThreadedItemContainer::QueryInterface'::`2'::qit,
                                    &GUID_0c904b4a_164a_4d81_92d9_a5fc866f7fb8,
                                    (void **)&lpszPathName);
        inited = FreeThreadedMarshaler;
        v34 = (CFreeThreadedItemContainer *)pszPath[0];
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)pszPath[0] + 10, 0xFFFFFFFF) == 1 )
        {
          CFreeThreadedItemContainer::~CFreeThreadedItemContainer(v34);
          operator delete((void *)pszPath[0], (const struct std::nothrow_t *)0x50);
        }
        if ( inited >= 0 )
        {
          v85 = 0;
          inited = (**(__int64 (__fastcall ***)(LPCOLESTR, GUID *, __int64 *))lpszPathName)(
                     lpszPathName,
                     &GUID_7f73be3f_fb79_493c_a6c7_7ee14e245841,
                     &v85);
          if ( inited >= 0 )
          {
            *(_QWORD *)pcbData = 0;
            inited = (**(__int64 (__fastcall ***)(WCHAR *, GUID *, DWORD *))pwcsName)(
                       pwcsName,
                       &GUID_000214e6_0000_0000_c000_000000000046,
                       pcbData);
            if ( inited >= 0 )
            {
              pwcsName = 0;
              inited = -2147024882;
              v35 = (CShellItem *)operator new(0xD8u, (const struct std::nothrow_t *)&std::nothrow);
              if ( v35 )
              {
                v36 = (const WCHAR *)CShellItem::CShellItem(v35);
                pszPath[0] = v36;
                if ( v36 )
                {
                  inited = CObjectWithThreadUseDetection::InitApartmentId((CObjectWithThreadUseDetection *)(v36 + 40));
                  if ( inited >= 0 )
                    inited = (**(__int64 (__fastcall ***)(PCWSTR, GUID *, WCHAR **))pszPath[0])(
                               pszPath[0],
                               &GUID_1cbff8c0_da47_4ebe_9928_2e642f00b5bc,
                               &pwcsName);
                  (*(void (__fastcall **)(PCWSTR))(*(_QWORD *)pszPath[0] + 16LL))(pszPath[0]);
                  if ( inited >= 0 )
                  {
                    inited = (*(__int64 (__fastcall **)(WCHAR *, _QWORD))(*(_QWORD *)pwcsName + 24LL))(
                               pwcsName,
                               *(_QWORD *)pcbData);
                    if ( inited >= 0 )
                    {
                      v83 = 0;
                      inited = (**(__int64 (__fastcall ***)(WCHAR *, GUID *, _QWORD))pwcsName)(
                                 pwcsName,
                                 &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                 &v83);
                      if ( inited >= 0 )
                      {
                        inited = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v85 + 24LL))(
                                   v85,
                                   v83,
                                   0);
                        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, IID *, void **)))(*v83)[2])(v83);
                      }
                    }
                    (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)pwcsName + 16LL))(pwcsName);
                  }
                }
              }
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pcbData + 16LL))(*(_QWORD *)pcbData);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
            if ( inited >= 0 )
            {
              v37 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
              v38 = v37;
              pszPath[0] = (PCWSTR)v37;
              if ( v37 )
              {
                *v37 = &CFSPropertyStoreFactory::`vftable'{for `IDelayedPropertyStoreFactory'};
                v37[1] = &CFSPropertyStoreFactory::`vftable'{for `IFreeThreadedItemContainer'};
                *((_DWORD *)v37 + 4) = 1;
                v37[3] = 0;
                v37[4] = 0;
                v37[5] = 0;
                *((_BYTE *)v37 + 49) = 0;
                v39 = lpszPathName;
                v37[3] = lpszPathName;
                (*(void (__fastcall **)(LPCOLESTR))(*(_QWORD *)v39 + 8LL))(v39);
                v40 = ILCloneFirst(pidl);
                v38[4] = v40;
                if ( v40 )
                  inited = QISearch(v38, &stru_18067F260, &GUID_0c904b4a_164a_4d81_92d9_a5fc866f7fb8, v12);
                else
                  inited = -2147024882;
                v42 = (CFSPropertyStoreFactory *)pszPath[0];
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)pszPath[0] + 4, 0xFFFFFFFF) == 1 )
                  CFSPropertyStoreFactory::`scalar deleting destructor'(v42, v41);
              }
              else
              {
                inited = -2147024882;
              }
            }
          }
        }
      }
      v43 = lpszPathName;
      lpszPathName = 0;
      if ( v43 )
        (*(void (__fastcall **)(LPCOLESTR))(*(_QWORD *)v43 + 16LL))(v43);
      if ( inited < 0 )
      {
        Handler = inited;
      }
      else
      {
        (*(void (__fastcall **)(char *))(*((_QWORD *)hObject[0] + 29) + 24LL))((char *)hObject[0] + 232);
        Handler = (**(__int64 (__fastcall ***)(void *, IID *, void **))*v12)(*v12, riid, ppv);
      }
      (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v84 + 16LL))(v84);
    }
    goto LABEL_16;
  }
  if ( (unsigned int)IsPropertyIID(riid) )
  {
    v64 = *(_QWORD *)&IID_IPropertySetStorage.Data1 - *(_QWORD *)&riid->Data1;
    if ( *(_QWORD *)&IID_IPropertySetStorage.Data1 == *(_QWORD *)&riid->Data1 )
      v64 = *(_QWORD *)IID_IPropertySetStorage.Data4 - *(_QWORD *)riid->Data4;
    if ( v64 || (unsigned int)SHWindowsPolicy(&POLID_DisableBindDirectlyToPropertySetStorage) )
    {
      if ( (v10 & 1) != 0 )
      {
        Handler = -2147024809;
        goto LABEL_87;
      }
      if ( (v10 & 2) != 0 && (GetFullFileAttributes(v94) & 1) != 0 )
      {
        Handler = -2147287035;
        goto LABEL_17;
      }
      v65 = punk;
      v66 = FlagsFromBindCtx(a2, v10);
      Handler = CFSFolder::_BindToPropertyStore(v8, (const struct _ITEMID_CHILD *)a3, v66, v65, riid, ppv);
      goto LABEL_16;
    }
    pwcsName = 0;
    v67 = *(__int64 (__fastcall **)(char *, LPCITEMIDLIST, __int64, __int64))(*((_QWORD *)v8 + 39) + 112LL);
    v68 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pwcsName);
    Handler = v67((char *)v8 + 312, pidl, 1, v68);
    if ( Handler >= 0 )
    {
      v83 = 0;
      lpszPathName = 0;
      if ( a2 )
      {
        if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, LPCOLESTR *))a2->lpVtbl->GetObjectParam)(
               a2,
               L"OplockProvider",
               &lpszPathName) >= 0 )
        {
          v69 = (**(__int64 (__fastcall ***)(LPCOLESTR, GUID *, _QWORD))lpszPathName)(
                  lpszPathName,
                  &GUID_3119d9ab_dc96_4508_bc7d_14fbb3cb05e2,
                  &v83);
          (*(void (__fastcall **)(LPCOLESTR))(*(_QWORD *)lpszPathName + 16LL))(lpszPathName);
          if ( v69 >= 0 )
          {
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, IID *, void **), WCHAR *, _QWORD, _QWORD))(*v83)[4])(
              v83,
              pwcsName,
              0,
              0);
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, IID *, void **)))(*v83)[2])(v83);
          }
        }
      }
      v70 = StgOpenStorageEx(pwcsName, v10, 0, 0, 0, 0, riid, ppv);
      Handler = v70;
      if ( v70 < 0 && !(unsigned int)FailForceReturn(v70) )
      {
        v71 = punk;
        v72 = FlagsFromBindCtx(a2, v10);
        v73 = CFSFolder::_BindToPropertyStore(
                v8,
                (const struct _ITEMID_CHILD *)pidl,
                (enum GETPROPERTYSTOREFLAGS)(v72 | 1),
                v71,
                riid,
                ppv);
        Handler = v73;
        if ( v73 < 0 && !(unsigned int)FailForceReturn(v73) )
          Handler = StgOpenStorageEx(pwcsName, v10, 3u, 0, 0, 0, riid, ppv);
      }
    }
    v54 = pwcsName;
    if ( pwcsName )
      goto LABEL_115;
  }
  else
  {
    v23 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_ITransferMediumItem.Data1;
    if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_ITransferMediumItem.Data1 )
      v23 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_ITransferMediumItem.Data4;
    if ( v23 )
    {
      v24 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_ILocallyCachedItem.Data1;
      if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_ILocallyCachedItem.Data1 )
        v24 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_ILocallyCachedItem.Data4;
      if ( v24 )
      {
        Handler = -2147467259;
        v25 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IStream.Data1;
        if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IStream.Data1 )
          v25 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IStream.Data4;
        if ( !v25 )
          goto LABEL_87;
        v26 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data1;
        if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data1 )
          v26 = *(_QWORD *)riid->Data4 - *(_QWORD *)GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data4;
        if ( !v26 )
          goto LABEL_87;
        v27 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IMoniker.Data1;
        if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IMoniker.Data1 )
          v27 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IMoniker.Data4;
        if ( !v27 )
          goto LABEL_87;
        v28 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IPropertyBag.Data1;
        if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IPropertyBag.Data1 )
          v28 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IPropertyBag.Data4;
        if ( !v28 )
          goto LABEL_87;
        v29 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, IID *))(*((_QWORD *)v8 + 39) + 56LL))(
                                          (__int64)v8 + 312,
                                          riid);
        Handler = CFileSysItemString::LoadHandler((CFileSysItemString *)v99, v10, v29, a2, 0, &BHID_SFObject, riid, ppv);
        goto LABEL_16;
      }
      lpszPathName = 0;
      if ( (unsigned int)CFSFolder::_IsNetFolder(v8) )
      {
        v77 = *(__int64 (__fastcall **)(char *, LPCITEMIDLIST, __int64, __int64))(*((_QWORD *)v8 + 39) + 112LL);
        v78 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&lpszPathName);
        Handler = v77((char *)v8 + 312, pidl, 1, v78);
        if ( Handler >= 0 )
        {
          pszPath[0] = 0;
          pszPath[1] = (PCWSTR)-1LL;
          pszPath[2] = (PCWSTR)-1LL;
          Handler = PathConvertToCSC(lpszPathName, (unsigned __int16 **)pszPath);
          v79 = (WCHAR *)pszPath[0];
          if ( Handler >= 0 )
          {
            pwcsName = 0;
            Handler = SHCreateItemFromParsingName(
                        pszPath[0],
                        0,
                        &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                        (void **)&pwcsName);
            if ( Handler >= 0 )
              Handler = SHCreateRelatedItem((struct IShellItem *)pwcsName, riid);
            if ( pwcsName )
              (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)pwcsName + 16LL))(pwcsName);
          }
          if ( v79 )
            CoTaskMemFree(v79);
        }
      }
      else
      {
        Handler = -2147467262;
      }
      v54 = (void *)lpszPathName;
      if ( lpszPathName )
LABEL_115:
        CoTaskMemFree(v54);
    }
    else
    {
      memset_0(pvData, 0, 0x268u);
      Handler = CFileSysItemString::GetFindData(v99, 0, pvData);
      if ( Handler < 0 )
        goto LABEL_85;
      pwcsName = 0;
      pdwType = (int)a2;
      Handler = CFSFolder::_CreateIDListWithBindCtx(v8, pvData, 0, 0);
      if ( Handler < 0 )
        goto LABEL_85;
      v53 = pwcsName;
      if ( *((_QWORD *)v8 + 80) )
      {
        pszPath[0] = 0;
        Handler = CFSFolder::_CombineWithFolderIDList(
                    v8,
                    (const struct _ITEMIDLIST_RELATIVE *)pwcsName,
                    (struct _ITEMIDLIST_ABSOLUTE **)pszPath);
        if ( Handler >= 0 )
        {
          Handler = SHCreateRelatedItemFromIDList(pszPath[0], riid, ppv);
          CoTaskMemFree((LPVOID)pszPath[0]);
          CoTaskMemFree(v53);
          goto LABEL_16;
        }
      }
      else
      {
        Handler = SHCreateRelatedItemWithParent((char *)v8 + 48, pwcsName, riid, ppv);
      }
      CoTaskMemFree(v53);
    }
  }
LABEL_16:
  if ( Handler >= 0 )
    goto LABEL_17;
  v8 = (CFSFolder *)hObject[0];
LABEL_85:
  if ( Handler == -2147287035 || Handler == -2147287008 )
    goto LABEL_17;
LABEL_87:
  lpszPathName = 0;
  v44 = *(int (__fastcall **)(char *, LPCITEMIDLIST, __int64, __int64))(*((_QWORD *)v8 + 39) + 112LL);
  v45 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&lpszPathName);
  if ( v44((char *)v8 + 312, pidl, 1, v45) >= 0 )
  {
    v47 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IStream.Data1;
    if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IStream.Data1 )
      v47 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IStream.Data4;
    v48 = v94;
    if ( v47 || (((*((_BYTE *)v94 + 2) & 0x37) - 50) & 0xFB) != 0 )
    {
      v49 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data1;
      if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data1 )
        v49 = *(_QWORD *)riid->Data4 - *(_QWORD *)GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data4;
      if ( v49 || !(unsigned int)CFSFolder::_IsFile(v46, v94) )
      {
        v50 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IPropertyBag.Data1;
        if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IPropertyBag.Data1 )
          v50 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IPropertyBag.Data4;
        if ( v50 || !(unsigned int)IsFolder(v48) )
        {
          v51 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IMoniker.Data1;
          if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IMoniker.Data1 )
            v51 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IMoniker.Data4;
          if ( v51 )
            goto LABEL_102;
          FileMoniker = CreateFileMoniker(lpszPathName, (LPMONIKER *)ppv);
        }
        else
        {
          FileMoniker = CFSFolder::_CreateFolderPropertyBag(
                          v8,
                          v10,
                          (const struct _ITEMIDLIST_RELATIVE *)pidl,
                          riid,
                          ppv);
        }
        Handler = FileMoniker;
      }
      else
      {
        v83 = 0;
        Handler = -2147467262;
        pwcsName = 0;
        if ( a2 )
        {
          if ( ((int (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, WCHAR **))a2->lpVtbl->GetObjectParam)(
                 a2,
                 L"RandomAccessStreamMode",
                 &pwcsName) >= 0 )
          {
            Handler = (**(__int64 (__fastcall ***)(WCHAR *, GUID *, _QWORD))pwcsName)(
                        pwcsName,
                        &GUID_ba433434_2f07_4f5e_94ae_35c82fe1708a,
                        &v83);
            (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)pwcsName + 16LL))(pwcsName);
            if ( Handler >= 0 )
            {
              LODWORD(v94) = 0;
              Handler = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, IID *, void **), struct IDFOLDER **))(*v83)[3])(
                          v83,
                          &v94);
              if ( Handler >= 0 )
              {
                LODWORD(v84) = 0;
                Handler = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, IID *, void **), WCHAR **))(*v83)[4])(
                            v83,
                            &v84);
                if ( Handler >= 0 )
                {
                  LODWORD(v85) = 0;
                  Handler = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, IID *, void **), __int64 *))(*v83)[5])(
                              v83,
                              &v85);
                  if ( Handler >= 0 )
                  {
                    LODWORD(pidl) = 0;
                    pwcsName = 0;
                    v57 = (__int64 (__fastcall *)(_QWORD, GUID *, WCHAR **))**v83;
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pwcsName);
                    Handler = v57(v83, &GUID_2a33a3b1_21c9_4d11_bc6f_54f3f88d4190, &pwcsName);
                    if ( Handler >= 0 )
                    {
                      v58 = (*(__int64 (__fastcall **)(WCHAR *, LPCITEMIDLIST *))(*(_QWORD *)pwcsName + 24LL))(
                              pwcsName,
                              &pidl);
                      if ( v58 < 0 )
                        wil::details::in1diag3::_Log_Hr(
                          retaddr,
                          (void *)0x2833,
                          (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
                          (const char *)(unsigned int)v58,
                          pdwType);
                      hObject[0] = 0;
                      LOBYTE(hObject[1]) = 0;
                      v59 = *(_QWORD *)pwcsName;
                      hObject[0] = 0;
                      Handler = (*(__int64 (__fastcall **)(WCHAR *, HANDLE *))(v59 + 32))(pwcsName, hObject);
                      if ( Handler >= 0 )
                      {
                        pvData[0] = 0;
                        pcbData[0] = 520;
                        ExtensionW = PathFindExtensionW(lpszPathName);
                        if ( RegGetValueW(HKEY_CLASSES_ROOT, ExtensionW, L"Content Type", 2u, 0, pvData, pcbData) )
                          pvData[0] = 0;
                        v86[0] = (_DWORD)v94;
                        v86[1] = (_DWORD)v84;
                        v86[2] = v85;
                        v86[3] = 0;
                        v87 = pvData;
                        v88 = (int)pidl;
                        v89 = 0;
                        v90 = 0;
                        pszPath[0] = 0;
                        Handler = EdpHelpers::InheritCallerEnterpriseContextWithNetworkOverride(
                                    (EdpHelpers *)hObject[0],
                                    pszPath,
                                    v61);
                        if ( Handler >= 0 )
                        {
                          Handler = CreateRandomAccessStreamOnFileWithOptions(lpszPathName, v86, riid, ppv);
                          v62 = pszPath[0];
                          if ( (unsigned int)EdpGetIsManaged() )
                            SrpRestoreEnterpriseContext(v62);
                        }
                        if ( (unsigned __int64)pszPath[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
                          CloseHandle((HANDLE)pszPath[0]);
                      }
                      if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
                        CloseHandle(hObject[0]);
                    }
                    v63 = pwcsName;
                    if ( pwcsName )
                    {
                      pwcsName = 0;
                      (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v63 + 16LL))(v63);
                    }
                  }
                }
              }
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, IID *, void **)))(*v83)[2])(v83);
            }
          }
        }
      }
    }
    else if ( CFileSysItemString::FileIsPartialPlaceholder((CFileSysItemString *)v99)
           && (GetFullFileAttributes(v48) & 0x1000) != 0
           && (unsigned int)BindCtx_ContainsObject(a2, L"BindToThumbnailStream") )
    {
      *(_QWORD *)pcbData = 0;
      Handler = CFSFolder::_BindToPropertyStore(
                  v8,
                  (const struct _ITEMID_CHILD *)pidl,
                  GPS_EXTRINSICPROPERTIESONLY,
                  punk,
                  &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                  (void **)pcbData);
      if ( Handler >= 0 )
      {
        v83 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
        *(GUID *)hObject = PKEY_ThumbnailStream.fmtid;
        LODWORD(v98) = PKEY_ThumbnailStream.pid;
        Object = CPropertyStoreHelperBase<IPropertyStore>::GetObjectW<_tagpropertykey>(
                   pcbData,
                   hObject,
                   &GUID_0000000c_0000_0000_c000_000000000046,
                   &v83);
        Handler = Object;
        if ( Object < 0 )
        {
          if ( Object == -2147023728 )
          {
            pwcsName = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pwcsName);
            if ( (int)GetObjectFromBindCtx(
                        a2,
                        L"BindToThumbnailStream",
                        &GUID_5d7dccbd_8d93_4163_b5f3_8b23ee8961e5,
                        (void **)&pwcsName) >= 0 )
              (*(void (__fastcall **)(WCHAR *, __int64))(*(_QWORD *)pwcsName + 24LL))(pwcsName, 8);
            v80 = pwcsName;
            if ( pwcsName )
            {
              pwcsName = 0;
              (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v80 + 16LL))(v80);
            }
          }
        }
        else
        {
          pwcsName = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pwcsName);
          if ( (int)GetObjectFromBindCtx(
                      a2,
                      L"BindToThumbnailStream",
                      &GUID_5d7dccbd_8d93_4163_b5f3_8b23ee8961e5,
                      (void **)&pwcsName) >= 0 )
            (*(void (__fastcall **)(WCHAR *, __int64))(*(_QWORD *)pwcsName + 24LL))(pwcsName, 7);
          Handler = (**v83)(v83, riid, ppv);
          v75 = pwcsName;
          if ( pwcsName )
          {
            pwcsName = 0;
            (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v75 + 16LL))(v75);
          }
        }
        v76 = v83;
        if ( v83 )
        {
          v83 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, IID *, void **)))(*v76)[2])(v76);
        }
      }
      if ( *(_QWORD *)pcbData )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pcbData + 16LL))(*(_QWORD *)pcbData);
    }
    else
    {
      LODWORD(v94) = 0;
      hObject[0] = (HANDLE)lpszPathName;
      v98 = 0;
      LODWORD(hObject[1]) = 0;
      if ( !(unsigned __int8)IsSHELL32_SHIsVirtualDevicePresent()
        || (GetFullFileAttributes(v48) & 0x4010) != 0x4000
        || (int)CEfsUtil::IsPinRequired((CEfsUtil *)hObject, (int *)&v94) >= 0 && !(_DWORD)v94 )
      {
        pwcsName = 0;
        FileFlagsFromBindCtx = _ManagedCreateFileFlagsFromBindCtx(a2);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pwcsName);
        Handler = SHManagedCreateStreamOnFile(lpszPathName, v10, 128, 0, 0, FileFlagsFromBindCtx, &pwcsName);
        if ( Handler >= 0 )
          Handler = (**(__int64 (__fastcall ***)(WCHAR *, IID *, void **))pwcsName)(pwcsName, riid, ppv);
        v56 = pwcsName;
        if ( pwcsName )
        {
          pwcsName = 0;
          (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v56 + 16LL))(v56);
        }
      }
      operator delete(v98, (const struct std::nothrow_t *)1);
    }
  }
LABEL_102:
  if ( lpszPathName )
    CoTaskMemFree((LPVOID)lpszPathName);
LABEL_17:
  if ( punk )
    ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
  v99[0] = &CFileSysItemString::`vftable';
  v19 = v105;
  v105 = 0;
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  v20 = ppunk;
  ppunk = 0;
  if ( v20 )
    ((void (__fastcall *)(IUnknown *))v20->lpVtbl->Release)(v20);
  v21 = v104;
  v104 = 0;
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v101 )
    CoTaskMemFree(v101);
  if ( v100 )
    CoTaskMemFree(v100);
  return (unsigned int)Handler;
}

```

## disassembly

```asm
0x1800dda70  push    rbp
0x1800dda72  push    rbx
0x1800dda73  push    rsi
0x1800dda74  push    rdi
0x1800dda75  push    r12
0x1800dda77  push    r13
0x1800dda79  push    r14
0x1800dda7b  push    r15
0x1800dda7d  lea     rbp, [rsp-528h]
0x1800dda85  sub     rsp, 628h
0x1800dda8c  mov     rax, cs:__security_cookie
0x1800dda93  xor     rax, rsp
0x1800dda96  mov     [rbp+560h+var_50], rax
0x1800dda9d  mov     [rbp+560h+var_5B8], r9
0x1800ddaa1  mov     rdi, r8
0x1800ddaa4  mov     [rbp+560h+pidl], r8
0x1800ddaa8  mov     r14, rdx
0x1800ddaab  mov     r12, rcx
0x1800ddaae  mov     [rbp+560h+hObject], rcx
0x1800ddab2  mov     r13, [rbp+560h+riid]
0x1800ddab9  mov     r15, [rbp+560h+ppv]
0x1800ddac0  mov     [rsp+660h+ppmk], r15
0x1800ddac5  xor     ebx, ebx
0x1800ddac7  mov     [r15], rbx
0x1800ddaca  mov     rdx, rcx; struct CFSFolder *
0x1800ddacd  lea     rcx, [rbp+560h+var_570]; this
0x1800ddad1  call    ??0CFileSysItemString@@QEAA@PEAVCFSFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEFBUIDFOLDER@@@Z; CFileSysItemString::CFileSysItemString(CFSFolder *,_ITEMIDLIST_RELATIVE const *,IDFOLDER const *)
0x1800ddad6  nop
0x1800ddad7  mov     [rbp+560h+punk], rbx
0x1800ddadb  mov     [rsp+660h+pwcsName], rbx
0x1800ddae0  test    r14, r14
0x1800ddae3  jz      short loc_1800DDB3D
0x1800ddae5  mov     rax, [r14]
0x1800ddae8  lea     r8, [rsp+660h+pwcsName]
0x1800ddaed  lea     rdx, aDelegateObject; "Delegate Object Creation"
0x1800ddaf4  mov     rcx, r14
0x1800ddaf7  mov     rax, [rax+50h]
0x1800ddafb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddb00  test    eax, eax
0x1800ddb02  js      short loc_1800DDB3D
0x1800ddb04  mov     rcx, [rsp+660h+pwcsName]
0x1800ddb09  mov     rax, [rcx]
0x1800ddb0c  lea     r8, [rbp+560h+punk]
0x1800ddb10  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800ddb17  mov     rax, [rax]
0x1800ddb1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddb1f  mov     ebx, eax
0x1800ddb21  mov     rdx, [rsp+660h+pwcsName]
0x1800ddb26  mov     rcx, [rdx]
0x1800ddb29  mov     rax, [rcx+10h]
0x1800ddb2d  mov     rcx, rdx
0x1800ddb30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddb35  test    ebx, ebx
0x1800ddb37  jns     loc_1800DE365
0x1800ddb3d  mov     esi, 20h ; ' '
0x1800ddb42  test    r14, r14
0x1800ddb45  jz      short loc_1800DDB70
0x1800ddb47  mov     dword ptr [rbp+560h+pszPath], 10h
0x1800ddb4e  xor     eax, eax
0x1800ddb50  mov     [rbp+560h+pszPath+4], rax
0x1800ddb54  mov     [rbp+560h+var_5A4], eax
0x1800ddb57  mov     rax, [r14]
0x1800ddb5a  lea     rdx, [rbp+560h+pszPath]
0x1800ddb5e  mov     rcx, r14
0x1800ddb61  mov     rax, [rax+38h]
0x1800ddb65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddb6a  test    eax, eax
0x1800ddb6c  cmovns  esi, [rbp-48h]
0x1800ddb70  mov     rax, qword ptr cs:IID_IPropertyStoreFactory.Data1
0x1800ddb77  sub     rax, [r13+0]
0x1800ddb7b  jnz     short loc_1800DDB88
0x1800ddb7d  mov     rax, qword ptr cs:IID_IPropertyStoreFactory.Data4
0x1800ddb84  sub     rax, [r13+8]
0x1800ddb88  test    rax, rax
0x1800ddb8b  jnz     loc_1800DDD10
0x1800ddb91  lea     rdi, [r12+388h]
0x1800ddb99  mov     rbx, [rdi]
0x1800ddb9c  test    rbx, rbx
0x1800ddb9f  jz      loc_1800DDE51
0x1800ddba5  xor     r12d, r12d
0x1800ddba8  mov     [r15], r12
0x1800ddbab  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800ddbb2  mov     ecx, 38h ; '8'; unsigned __int64
0x1800ddbb7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800ddbbc  mov     rdi, rax
0x1800ddbbf  mov     [rbp+560h+pszPath], rax
0x1800ddbc3  test    rax, rax
0x1800ddbc6  jz      loc_1800DE37D
0x1800ddbcc  lea     rax, ??_7CFSPropertyStoreFactory@@6BIDelayedPropertyStoreFactory@@@; const CFSPropertyStoreFactory::`vftable'{for `IDelayedPropertyStoreFactory'}
0x1800ddbd3  mov     [rdi], rax
0x1800ddbd6  lea     rax, ??_7CFSPropertyStoreFactory@@6BIFreeThreadedItemContainer@@@; const CFSPropertyStoreFactory::`vftable'{for `IFreeThreadedItemContainer'}
0x1800ddbdd  mov     [rdi+8], rax
0x1800ddbe1  mov     dword ptr [rdi+10h], 1
0x1800ddbe8  mov     [rdi+20h], r12
0x1800ddbec  mov     [rdi+28h], r12
0x1800ddbf0  mov     [rdi+31h], r12b
0x1800ddbf4  mov     [rdi+18h], rbx
0x1800ddbf8  mov     rax, [rbx]
0x1800ddbfb  mov     rcx, rbx
0x1800ddbfe  mov     rax, [rax+8]
0x1800ddc02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddc07  mov     rcx, [rbp+560h+pidl]; pidl
0x1800ddc0b  call    ILCloneFirst
0x1800ddc10  mov     [rdi+20h], rax
0x1800ddc14  test    rax, rax
0x1800ddc17  jz      loc_1800DE204
0x1800ddc1d  mov     r9, r15; ppv
0x1800ddc20  mov     r8, r13; riid
0x1800ddc23  lea     rdx, stru_18067F260; pqit
0x1800ddc2a  mov     rcx, rdi; that
0x1800ddc2d  call    cs:__imp_QISearch
0x1800ddc33  mov     r15d, eax
0x1800ddc36  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800ddc3d  lock xadd [rdi+10h], r12d
0x1800ddc43  cmp     r12d, 1
0x1800ddc47  jz      loc_1800DE22C
0x1800ddc4d  test    r15d, r15d
0x1800ddc50  js      loc_1800DED8D
0x1800ddc56  mov     rcx, [rbp+560h+punk]
0x1800ddc5a  test    rcx, rcx
0x1800ddc5d  jz      short loc_1800DDC6C
0x1800ddc5f  mov     rax, [rcx]
0x1800ddc62  mov     rax, [rax+10h]
0x1800ddc66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddc6b  nop
0x1800ddc6c  lea     rax, ??_7CFileSysItemString@@6B@; const CFileSysItemString::`vftable'
0x1800ddc73  mov     [rbp+560h+var_570], rax
0x1800ddc77  mov     rcx, [rbp+560h+var_528]
0x1800ddc7b  xor     ebx, ebx
0x1800ddc7d  mov     [rbp+560h+var_528], rbx
0x1800ddc81  test    rcx, rcx
0x1800ddc84  jz      short loc_1800DDC92
0x1800ddc86  mov     rax, [rcx]
0x1800ddc89  mov     rax, [rax+10h]
0x1800ddc8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddc92  mov     rcx, [rbp+560h+ppunk]
0x1800ddc96  mov     [rbp+560h+ppunk], rbx
0x1800ddc9a  test    rcx, rcx
0x1800ddc9d  jnz     loc_1800DDE40
0x1800ddca3  mov     rcx, [rbp+560h+var_530]
0x1800ddca7  mov     [rbp+560h+var_530], rbx
0x1800ddcab  test    rcx, rcx
0x1800ddcae  jz      short loc_1800DDCBC
0x1800ddcb0  mov     rax, [rcx]
0x1800ddcb3  mov     rax, [rax+10h]
0x1800ddcb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddcbc  mov     rcx, [rbp+560h+pv]; pv
0x1800ddcc0  test    rcx, rcx
0x1800ddcc3  jz      short loc_1800DDCCB
0x1800ddcc5  call    cs:__imp_CoTaskMemFree
0x1800ddccb  mov     rcx, [rbp+560h+var_558]; pv
0x1800ddccf  test    rcx, rcx
0x1800ddcd2  jz      short loc_1800DDCDA
0x1800ddcd4  call    cs:__imp_CoTaskMemFree
0x1800ddcda  mov     rcx, [rbp+560h+var_560]; pv
0x1800ddcde  test    rcx, rcx
0x1800ddce1  jz      short loc_1800DDCEA
0x1800ddce3  call    cs:__imp_CoTaskMemFree
0x1800ddce9  nop
0x1800ddcea  mov     eax, r15d
0x1800ddced  mov     rcx, [rbp+560h+var_50]
0x1800ddcf4  xor     rcx, rsp; StackCookie
0x1800ddcf7  call    __security_check_cookie
0x1800ddcfc  add     rsp, 628h
0x1800ddd03  pop     r15
0x1800ddd05  pop     r14
0x1800ddd07  pop     r13
0x1800ddd09  pop     r12
0x1800ddd0b  pop     rdi
0x1800ddd0c  pop     rsi
0x1800ddd0d  pop     rbx
0x1800ddd0e  pop     rbp
0x1800ddd0f  retn
0x1800ddd10  mov     rcx, r13; struct _GUID *
0x1800ddd13  call    ?IsPropertyIID@@YAHAEBU_GUID@@@Z; IsPropertyIID(_GUID const &)
0x1800ddd18  test    eax, eax
0x1800ddd1a  jnz     loc_1800DE850
0x1800ddd20  mov     rax, [r13+0]
0x1800ddd24  sub     rax, qword ptr cs:IID_ITransferMediumItem.Data1
0x1800ddd2b  jnz     short loc_1800DDD38
0x1800ddd2d  mov     rax, [r13+8]
0x1800ddd31  sub     rax, qword ptr cs:IID_ITransferMediumItem.Data4
0x1800ddd38  test    rax, rax
0x1800ddd3b  jz      loc_1800DE390
0x1800ddd41  mov     rax, [r13+0]
0x1800ddd45  sub     rax, qword ptr cs:IID_ILocallyCachedItem.Data1
0x1800ddd4c  jnz     short loc_1800DDD59
0x1800ddd4e  mov     rax, [r13+8]
0x1800ddd52  sub     rax, qword ptr cs:IID_ILocallyCachedItem.Data4
0x1800ddd59  test    rax, rax
0x1800ddd5c  jz      loc_1800DE438
0x1800ddd62  mov     r15d, 80004005h
0x1800ddd68  mov     rax, [r13+0]
0x1800ddd6c  sub     rax, qword ptr cs:IID_IStream.Data1
0x1800ddd73  jnz     short loc_1800DDD80
0x1800ddd75  mov     rax, [r13+8]
0x1800ddd79  sub     rax, qword ptr cs:IID_IStream.Data4
0x1800ddd80  test    rax, rax
0x1800ddd83  jz      loc_1800DE253
0x1800ddd89  mov     rax, [r13+0]
0x1800ddd8d  sub     rax, qword ptr cs:_GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data1
0x1800ddd94  jnz     short loc_1800DDDA1
0x1800ddd96  mov     rax, [r13+8]
0x1800ddd9a  sub     rax, qword ptr cs:_GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data4
0x1800ddda1  test    rax, rax
0x1800ddda4  jz      loc_1800DE253
0x1800dddaa  mov     rax, [r13+0]
0x1800dddae  sub     rax, qword ptr cs:IID_IMoniker.Data1
0x1800dddb5  jnz     short loc_1800DDDC2
0x1800dddb7  mov     rax, [r13+8]
0x1800dddbb  sub     rax, qword ptr cs:IID_IMoniker.Data4
0x1800dddc2  test    rax, rax
0x1800dddc5  jz      loc_1800DE253
0x1800dddcb  mov     rax, [r13+0]
0x1800dddcf  sub     rax, qword ptr cs:IID_IPropertyBag.Data1
0x1800dddd6  jnz     short loc_1800DDDE3
0x1800dddd8  mov     rax, [r13+8]
0x1800ddddc  sub     rax, qword ptr cs:IID_IPropertyBag.Data4
0x1800ddde3  test    rax, rax
0x1800ddde6  jz      loc_1800DE253
0x1800dddec  lea     rcx, [r12+138h]
0x1800dddf4  mov     rax, [rcx]
0x1800dddf7  mov     rdx, r13
0x1800dddfa  mov     rax, [rax+38h]
0x1800dddfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dde03  mov     r8, rax; unsigned __int16 *
0x1800dde06  mov     rax, [rsp+660h+ppmk]
0x1800dde0b  mov     [rsp+660h+ppObjectOpen], rax; void **
0x1800dde10  mov     [rsp+660h+pcbData], r13; struct _GUID *
0x1800dde15  lea     rax, BHID_SFObject
0x1800dde1c  mov     [rsp+660h+pvData], rax; struct _GUID *
0x1800dde21  mov     [rsp+660h+pdwType], 0; struct IOplockProvider *
0x1800dde2a  mov     r9, r14; struct IBindCtx *
0x1800dde2d  mov     edx, esi; unsigned int
0x1800dde2f  lea     rcx, [rbp+560h+var_570]; this
0x1800dde33  call    ?LoadHandler@CFileSysItemString@@QEAAJKPEBGPEAUIBindCtx@@PEAUIOplockProvider@@AEBU_GUID@@3PEAPEAX@Z; CFileSysItemString::LoadHandler(ulong,ushort const *,IBindCtx *,IOplockProvider *,_GUID const &,_GUID const &,void * *)
0x1800dde38  mov     r15d, eax
0x1800dde3b  jmp     loc_1800DDC4D
0x1800dde40  mov     rax, [rcx]
0x1800dde43  mov     rax, [rax+10h]
0x1800dde47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dde4c  jmp     loc_1800DDCA3
0x1800dde51  mov     [rsp+660h+var_608], rbx
0x1800dde56  mov     rax, [r12]
0x1800dde5a  lea     r8, [rsp+660h+var_608]
0x1800dde5f  lea     rdx, _GUID_127f6acb_7e78_4368_83a4_ed1de72baca6
0x1800dde66  mov     rcx, r12
0x1800dde69  mov     rax, [rax]
0x1800dde6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dde71  mov     r15d, eax
0x1800dde74  test    eax, eax
0x1800dde76  js      loc_1800DE239
0x1800dde7c  mov     rax, [rsp+660h+var_608]
0x1800dde81  mov     [rsp+660h+pwcsName], rax
0x1800dde86  mov     [rdi], rbx
0x1800dde89  mov     [rbp+560h+lpszPathName], rbx
0x1800dde8d  mov     r15d, 8007000Eh
0x1800dde93  mov     ebx, r15d
0x1800dde96  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800dde9d  mov     ecx, 50h ; 'P'; unsigned __int64
0x1800ddea2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800ddea7  mov     r12, rax
0x1800ddeaa  mov     [rbp+560h+pszPath], rax
0x1800ddeae  test    rax, rax
0x1800ddeb1  jz      loc_1800DE199
0x1800ddeb7  xor     ecx, ecx
0x1800ddeb9  mov     [rax+20h], rcx
0x1800ddebd  lea     rax, ??_7CFreeThreadedItemContainer@@6BIFreeThreadedItemContainer@@@; const CFreeThreadedItemContainer::`vftable'{for `IFreeThreadedItemContainer'}
0x1800ddec4  mov     [r12], rax
0x1800ddec8  lea     rax, ??_7CFreeThreadedItemContainer@@6BIInitializeWithItem@@@; const CFreeThreadedItemContainer::`vftable'{for `IInitializeWithItem'}
0x1800ddecf  mov     [r12+8], rax
0x1800dded4  lea     rax, ??_7CFreeThreadedItemContainer@@6BIPersistIDList@@@; const CFreeThreadedItemContainer::`vftable'{for `IPersistIDList'}
0x1800ddedb  mov     [r12+10h], rax
0x1800ddee0  lea     rax, ??_7CFreeThreadedItemContainer@@6BCFreeThreadedObject@@@; const CFreeThreadedItemContainer::`vftable'{for `CFreeThreadedObject'}
0x1800ddee7  mov     [r12+18h], rax
0x1800ddeec  mov     dword ptr [r12+28h], 1
0x1800ddef5  mov     [r12+40h], rcx
0x1800ddefa  mov     [r12+30h], rcx
0x1800ddeff  mov     [r12+38h], rcx
0x1800ddf04  mov     [r12+48h], rcx
0x1800ddf09  mov     r8d, 10h; Size
0x1800ddf0f  lea     rdx, IID_IMarshal; Buf2
0x1800ddf16  lea     rcx, _GUID_0c904b4a_164a_4d81_92d9_a5fc866f7fb8; Buf1
0x1800ddf1d  call    memcmp_0
0x1800ddf22  lea     r9, [rbp+560h+lpszPathName]; void **
0x1800ddf26  lea     r8, _GUID_0c904b4a_164a_4d81_92d9_a5fc866f7fb8; struct _GUID *
0x1800ddf2d  test    eax, eax
0x1800ddf2f  jnz     loc_1800DE20F
0x1800ddf35  mov     rdx, r12; struct IUnknown *
0x1800ddf38  lea     rcx, [r12+18h]; this
0x1800ddf3d  call    ?GetFreeThreadedMarshaler@CFreeThreadedObject@@QEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CFreeThreadedObject::GetFreeThreadedMarshaler(IUnknown *,_GUID const &,void * *)
0x1800ddf42  mov     ebx, eax
0x1800ddf44  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800ddf4b  mov     eax, r12d
0x1800ddf4e  mov     rcx, [rbp+560h+pszPath]; this
0x1800ddf52  lock xadd [rcx+28h], eax
0x1800ddf57  cmp     eax, 1
0x1800ddf5a  jz      loc_1800DE343
0x1800ddf60  test    ebx, ebx
0x1800ddf62  js      loc_1800DE199
  ... truncated ...
```
