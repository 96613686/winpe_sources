# CRegFolder::_GetTargetFileSystemItem(IDLREGITEM const *,IShellItem2 * *)

- ea: `0x1800e5a70`
- end: `0x1800e65da`
- name: `?_GetTargetFileSystemItem@CRegFolder@@AEAAJPEFBUIDLREGITEM@@PEAPEAUIShellItem2@@@Z`
- size: `2922`
- prototype: `__int64 __fastcall(CRegFolder *__hidden this, const struct IDLREGITEM *, struct IShellItem2 **ppv)`
- caller_count: `7`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800e22c0`
- `0x1800e2c40`
- `0x1800e4bd0`
- `0x1800e5330`
- `0x18014de80`
- `0x180169ea0`
- `0x18016a210`

## callees

- `0x180048fb0`
- `0x18004bdf0`
- `0x18004bee0`
- `0x18005bf00`
- `0x1800ccbd0`
- `0x1800d5920`
- `0x1800d6b80`
- `0x1800e1b30`
- `0x1800e1c70`
- `0x1800e2c40`
- `0x1800e4730`
- `0x1800e5a70`
- `0x1800e67e0`
- `0x1800e6810`
- `0x1800e6df0`
- `0x1800e6ea0`
- `0x18027fca0`
- `0x180288824`
- `0x180333018`
- `0x1803a4cb0`
- `0x1803a4cd4`
- `0x1803a518c`
- `0x1803a57e0`
- `0x1803a96d9`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e5fab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e64e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e5fab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e64e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e6519`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e6519`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800e5eab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800e5eab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e64fe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e64fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e5d78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e60dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e62dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e63c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e5d78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e60dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e62dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e63c8`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1800e60bb`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1800e60bb`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800e6059`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800e6059`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800e6221`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800e6221`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x1800e5c8c`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x1800e63ff`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x1800e5c8c`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x1800e63ff`

## string_xrefs

- `0x1800e5e1e`: `BlockRegItemParsing`
- `0x1800e613f`: `ParseAndCreateItem`
- `0x1800e6334`: `ParseAndCreateItem`
- `0x1800e6470`: `ParseAndCreateItem`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CRegFolder::_GetTargetFileSystemItem(
        struct IShellItem2 *this,
        const struct IDLREGITEM *a2,
        struct IShellItem2 **ppv)
{
  int v6; // r14d
  HRESULT BindCtx; // esi
  unsigned __int16 v8; // cx
  const struct IDLREGITEM *v9; // rax
  const struct IDLREGITEM *v10; // rbx
  unsigned __int16 v11; // dx
  unsigned __int16 *v12; // rdi
  __int64 v13; // r8
  unsigned int v14; // ecx
  unsigned __int64 v15; // rcx
  unsigned __int16 *v16; // rbx
  char *v17; // rbx
  LPBC v18; // rdi
  CDummyUnknown *v19; // rax
  LPBC v20; // rcx
  unsigned __int16 *v21; // r8
  unsigned __int16 *v23; // rdx
  CDummyUnknown *v24; // rbx
  CCLSIDInfoCache *v25; // rcx
  unsigned __int64 v26; // rax
  __int64 v27; // rdx
  const struct IDLREGITEM *v28; // rax
  struct _GUID *v29; // rax
  struct _GUID v30; // xmm6
  CCLSIDInfoCache *v31; // rcx
  HDSA v32; // rdi
  int v33; // esi
  int v34; // r14d
  int v35; // eax
  int v36; // ebx
  const struct CLSID_CACHE_ENTRY *v37; // rdx
  int v38; // eax
  const struct CLSID_CACHE_ENTRY *v39; // rdx
  int v40; // eax
  __int64 v41; // rax
  LPCWSTR v42; // rcx
  LPBC v43; // rdi
  const WCHAR *v44; // rsi
  int v45; // ebx
  LPBC v46; // rbx
  WCHAR *v47; // r12
  __int64 v48; // r14
  void *v49; // rdi
  void *v50; // rdi
  CDummyUnknown *v51; // rax
  CDummyUnknown *v52; // rbx
  struct IBindCtx *v53; // r15
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // rbx
  __int64 v57; // r12
  IShellFolder *v58; // r14
  HRESULT (__stdcall *ParseDisplayName)(IShellFolder *, HWND, IBindCtx *, LPWSTR, ULONG *, LPITEMIDLIST *, ULONG *); // rsi
  LPCWSTR v60; // rdi
  HWND UIWindow; // rax
  void *v62; // rcx
  int v63; // esi
  CDummyUnknown *v64; // rax
  CDummyUnknown *v65; // r14
  CCLSIDInfoCache *v66; // rcx
  CCLSIDInfoCache *v67; // rcx
  int v68; // eax
  CCLSIDInfoCache *v69; // rcx
  int v70; // r10d
  unsigned int *v71; // [rsp+28h] [rbp-D8h]
  LPCITEMIDLIST pidl; // [rsp+40h] [rbp-C0h] BYREF
  void *ppva; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR value; // [rsp+50h] [rbp-B0h] BYREF
  IShellFolder *ppshf; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v76; // [rsp+60h] [rbp-A0h] BYREF
  LPBC ppbc; // [rsp+68h] [rbp-98h] BYREF
  struct _GUID Buf1; // [rsp+70h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID pitem; // [rsp+88h] [rbp-78h] BYREF
  __int128 v81; // [rsp+98h] [rbp-68h]
  __int64 v82; // [rsp+A8h] [rbp-58h]
  int v83; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v84; // [rsp+B4h] [rbp-4Ch]
  __int64 v85; // [rsp+BCh] [rbp-44h]
  __int64 v86; // [rsp+C4h] [rbp-3Ch]
  char v87[564]; // [rsp+CCh] [rbp-34h] BYREF
  _OWORD v88[3]; // [rsp+300h] [rbp+200h] BYREF

  v6 = 0;
  *ppv = 0;
  BindCtx = -2147023728;
  if ( a2 )
  {
    v8 = *(_WORD *)a2;
    if ( *(_WORD *)a2 )
    {
      v9 = a2;
      do
      {
        v10 = v9;
        v9 = (const struct IDLREGITEM *)((char *)v9 + v8);
        v8 = *(_WORD *)v9;
      }
      while ( *(_WORD *)v9 );
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl'::`2'::impl) )
      {
        if ( !v10 )
          return (unsigned int)BindCtx;
        v11 = *(_WORD *)v10;
        if ( *(_WORD *)v10 < 2u )
          return (unsigned int)BindCtx;
      }
      else
      {
        v11 = *(_WORD *)v10;
      }
      v12 = 0;
      v13 = *(unsigned __int16 *)((char *)v10 + v11 - 2);
      if ( (_WORD)v13 )
      {
        if ( v13 + 8 < (unsigned __int64)v11 )
        {
          v12 = (unsigned __int16 *)((char *)v10 + v13);
          v14 = *(unsigned __int16 *)((char *)v10 + v13);
          if ( v14 < 8 || HIWORD(*((_DWORD *)v12 + 1)) != 0xBEEF || (unsigned int)v13 + v14 > v11 )
            v12 = 0;
        }
      }
      v15 = (unsigned __int64)v10 + *(unsigned __int16 *)v10;
      if ( v12 )
      {
        while ( 1 )
        {
          v16 = v12 + 4;
          if ( *((_DWORD *)v12 + 1) == -1091633114 )
            break;
          v21 = 0;
          if ( (unsigned __int64)v16 <= v15 )
          {
            v23 = (unsigned __int16 *)((char *)v12 + *v12);
            if ( v23 == (unsigned __int16 *)v15 )
              return (unsigned int)BindCtx;
            if ( (unsigned __int64)v23 <= v15 )
            {
              if ( (unsigned __int64)(v23 + 4) > v15
                || HIWORD(*((_DWORD *)v23 + 1)) != 0xBEEF
                || (unsigned __int64)v23 + *v23 > v15
                || v23 < v16 )
              {
                return (unsigned int)BindCtx;
              }
              v21 = (unsigned __int16 *)((char *)v12 + *v12);
            }
          }
          v12 = v21;
          if ( !v21 )
            return (unsigned int)BindCtx;
        }
        v85 = 0;
        memset_0(v87, 0, sizeof(v87));
        v83 = *(_DWORD *)v16;
        v84 = *(_QWORD *)(v12 + 6);
        v86 = *(_QWORD *)(v12 + 10);
        if ( v12[1] )
          v85 = *(_QWORD *)(v12 + 14);
        pv = 0;
        if ( (int)CRegFolder::_GetDisplayName(this, a2, 0x8000u, (unsigned __int16 **)&pv) < 0 )
          goto LABEL_29;
        ppbc = 0;
        pidl = 0;
        BindCtx = -2147024882;
        v17 = (char *)operator new(0x278u, (const struct std::nothrow_t *)&std::nothrow);
        *(_QWORD *)&Buf1.Data1 = v17;
        if ( !v17 )
          goto LABEL_27;
        *(_QWORD *)v17 = &CFileSysBindData::`vftable';
        *((_DWORD *)v17 + 2) = 1;
        memset_0(v17 + 40, 0, 0x250u);
        *((_QWORD *)v17 + 2) = 0;
        *(_OWORD *)(v17 + 24) = xmmword_180702890;
        BindCtx = (**(__int64 (__fastcall ***)(void *, GUID *, LPCITEMIDLIST *))v17)(
                    v17,
                    &GUID_01e18d10_4d8b_11d2_855d_006008059367,
                    &pidl);
        (*(void (__fastcall **)(char *))(*(_QWORD *)v17 + 16LL))(v17);
        if ( BindCtx < 0 )
          goto LABEL_27;
        (*(void (__fastcall **)(LPCITEMIDLIST, int *))(*(_QWORD *)&pidl->mkid.cb + 24LL))(pidl, &v83);
        ppbc = 0;
        BindCtx = CreateBindCtx(0, &ppbc);
        if ( BindCtx >= 0 )
        {
          *(_QWORD *)&Buf1.Data1 = 16;
          *(_QWORD *)Buf1.Data4 = 4096;
          BindCtx = ((__int64 (__fastcall *)(LPBC, struct _GUID *))ppbc->lpVtbl->SetBindOptions)(ppbc, &Buf1);
          if ( BindCtx < 0 )
            SafeRelease<IFilterCreationCallback>(&ppbc);
        }
        if ( BindCtx >= 0 )
        {
          v88[0] = *(_OWORD *)L"File System Bind Data";
          v88[1] = *(_OWORD *)L"tem Bind Data";
          *(_OWORD *)((char *)&v88[1] + 12) = *(_OWORD *)L"nd Data";
          ((void (__fastcall *)(LPBC, _OWORD *, LPCITEMIDLIST))ppbc->lpVtbl->RegisterObjectParam)(ppbc, v88, pidl);
        }
        (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)&pidl->mkid.cb + 16LL))(pidl);
        if ( BindCtx < 0 )
        {
LABEL_27:
          v20 = ppbc;
          if ( ppbc )
          {
            ppbc = 0;
            ((void (__fastcall *)(LPBC))v20->lpVtbl->Release)(v20);
          }
LABEL_29:
          if ( pv )
            CoTaskMemFree(pv);
          return (unsigned int)BindCtx;
        }
        v18 = ppbc;
        v19 = (CDummyUnknown *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
        *(_QWORD *)&Buf1.Data1 = v19;
        if ( !v19 || (v24 = CDummyUnknown::CDummyUnknown(v19)) == 0 )
        {
          BindCtx = -2147024882;
          goto LABEL_27;
        }
        BindCtx = ((__int64 (__fastcall *)(LPBC, const wchar_t *, CDummyUnknown *))v18->lpVtbl->RegisterObjectParam)(
                    v18,
                    L"BlockRegItemParsing",
                    v24);
        CDummyUnknown::Release(v24);
        if ( BindCtx < 0 )
          goto LABEL_27;
        v26 = *(unsigned __int16 *)a2;
        if ( (unsigned int)v26 > 7
          && (v27 = *((unsigned __int16 *)a2 + 2), v25 = (CCLSIDInfoCache *)(v27 + 38), v26 >= v27 + 38)
          && (Buf1 = *(struct _GUID *)((char *)a2 + v27 + 6), !memcmp_0(&Buf1, &unk_1806FB0A8, 0x10u)) )
        {
          v29 = (struct _GUID *)((char *)a2 + *((unsigned __int16 *)a2 + 2) + 22);
        }
        else
        {
          v28 = *((_BYTE *)a2 + 2) == LOBYTE(this[45].lpVtbl)
              ? a2
              : (const struct IDLREGITEM *)((char *)a2 + HIDWORD(this[44].lpVtbl));
          v29 = (struct _GUID *)((char *)v28 + 4);
        }
        v30 = *v29;
        Buf1 = *v29;
        pitem = 0;
        v81 = 0;
        v82 = 0;
        if ( (unsigned int)CCLSIDInfoCache::_EnsureCacheIsValid(v25, 0) )
        {
          AcquireSRWLockShared(&g_clsidInfoCache);
          memset(&v88[1], 0, 24);
          v88[0] = v30;
          v32 = hdsa;
          if ( hdsa )
            v6 = *(_DWORD *)hdsa;
          v33 = 0;
          v34 = v6 - 1;
          while ( v33 <= v34 )
          {
            v35 = (v34 + v33) / 2;
            v36 = v35;
            v37 = 0;
            if ( v32 && v35 >= 0 && v35 < *(_DWORD *)v32 )
              v37 = (const struct CLSID_CACHE_ENTRY *)(*((_QWORD *)v32 + 1) + (unsigned int)(*((_DWORD *)v32 + 5) * v35));
            v38 = CCLSIDInfoCache::s_CompareEntries((const struct CLSID_CACHE_ENTRY *)v88, v37, 0);
            if ( v38 < 0 )
            {
              v34 = v36 - 1;
            }
            else
            {
              if ( v38 <= 0 )
              {
                for ( ; v36 > 0; --v36 )
                {
                  v39 = 0;
                  if ( v32 )
                  {
                    v40 = v36 - 1;
                    if ( v36 - 1 >= 0 && v40 < *(_DWORD *)v32 )
                      v39 = (const struct CLSID_CACHE_ENTRY *)(*((_QWORD *)v32 + 1)
                                                             + (unsigned int)(*((_DWORD *)v32 + 5) * v40));
                  }
                  if ( (unsigned int)CCLSIDInfoCache::s_CompareEntries((const struct CLSID_CACHE_ENTRY *)v88, v39, 0) )
                    break;
                }
                if ( v36 != -1 )
                {
                  v41 = 0;
                  if ( v32 && v36 >= 0 && v36 < *(_DWORD *)v32 )
                    v41 = *((_QWORD *)v32 + 1) + (unsigned int)(*((_DWORD *)v32 + 5) * v36);
                  pitem = *(struct _GUID *)v41;
                  v81 = *(_OWORD *)(v41 + 16);
                  v82 = *(_QWORD *)(v41 + 32);
                  ReleaseSRWLockShared(&g_clsidInfoCache);
                  goto LABEL_74;
                }
                break;
              }
              v33 = v36 + 1;
            }
          }
          ReleaseSRWLockShared(&g_clsidInfoCache);
          pitem = v30;
          CCLSIDInfoCache::_LoadValuesFromRegistry(v66, (struct CLSID_CACHE_ENTRY *)&pitem);
          AcquireSRWLockExclusive(&g_clsidInfoCache);
          if ( (unsigned int)CCLSIDInfoCache::_EnsureCacheIsValid(v67, 1) )
          {
            LODWORD(v71) = 3;
            v68 = CDSA_Base<CLSID_CACHE_ENTRY>::Search(&hdsa, &pitem);
            if ( !(unsigned int)CCLSIDInfoCache::_IsEntry(v69, &Buf1, v68) )
              DSA_InsertItem(hdsa, v70, &pitem);
          }
          ReleaseSRWLockExclusive(&g_clsidInfoCache);
        }
        else
        {
          pitem = v30;
          CCLSIDInfoCache::_LoadValuesFromRegistry(v31, (struct CLSID_CACHE_ENTRY *)&pitem);
        }
LABEL_74:
        if ( (v82 & 0x40000000000000LL) == 0 )
        {
          value = 0;
          if ( (int)CRegFolder::_GetDisplayName(this, a2, 0, (unsigned __int16 **)&value) >= 0 )
          {
            v43 = ppbc;
            if ( ppbc )
            {
              v44 = value;
              ppva = 0;
              pidl = 0;
              if ( ((int (__fastcall *)(LPBC, const unsigned __int16 *, LPCITEMIDLIST *))ppbc->lpVtbl->GetObjectParam)(
                     ppbc,
                     L"SHBindCtxPropertyBag",
                     &pidl) >= 0 )
              {
                v45 = (**(__int64 (__fastcall ***)(LPCITEMIDLIST, GUID *, void **))&pidl->mkid.cb)(
                        pidl,
                        &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
                        &ppva);
                (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)&pidl->mkid.cb + 16LL))(pidl);
                if ( v45 >= 0 )
                  goto LABEL_81;
              }
              if ( PSCreateMemoryPropertyStore(&GUID_55272a00_42cb_11ce_8135_00aa004bb851, &ppva) >= 0 )
              {
                v88[0] = *(_OWORD *)L"SHBindCtxPropertyBag";
                v88[1] = *(_OWORD *)L"xPropertyBag";
                *(_OWORD *)((char *)&v88[1] + 10) = *(_OWORD *)L"ertyBag";
                if ( ((int (__fastcall *)(LPBC, _OWORD *, void *))v43->lpVtbl->RegisterObjectParam)(v43, v88, ppva) >= 0 )
                {
LABEL_81:
                  PSPropertyBag_WriteStr((IPropertyBag *)ppva, L"LocalizedResourceName", v44);
                  (*(void (__fastcall **)(void *))(*(_QWORD *)ppva + 16LL))(ppva);
                }
              }
            }
          }
          v42 = value;
          if ( value )
            CoTaskMemFree((LPVOID)value);
        }
        v46 = ppbc;
        v47 = (WCHAR *)pv;
        *ppv = 0;
        v76 = 0;
        BindCtx = CTRefBase<CParseAndCreateItem,IParseAndCreateItem,CTRefBase_DllModuleLifetimePolicy>::CreateInstance(
                    v42,
                    &v76);
        if ( BindCtx < 0 )
          goto LABEL_27;
        v48 = v76;
        ppva = v46;
        if ( v46 )
        {
          ((void (__fastcall *)(LPBC))v46->lpVtbl->AddRef)(v46);
        }
        else
        {
          BindCtx = CreateBindCtx(0, (LPBC *)&ppva);
          if ( BindCtx < 0 )
            goto LABEL_115;
        }
        v49 = ppva;
        if ( v48 )
        {
          BindCtx = (*(__int64 (__fastcall **)(void *, const wchar_t *, __int64))(*(_QWORD *)ppva + 72LL))(
                      ppva,
                      L"ParseAndCreateItem",
                      v48);
        }
        else
        {
          v64 = (CDummyUnknown *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
          *(_QWORD *)&Buf1.Data1 = v64;
          if ( !v64 || (v65 = CDummyUnknown::CDummyUnknown(v64)) == 0 )
          {
            BindCtx = -2147024882;
            goto LABEL_129;
          }
          BindCtx = (*(__int64 (__fastcall **)(void *, const wchar_t *, CDummyUnknown *))(*(_QWORD *)v49 + 72LL))(
                      v49,
                      L"ParseAndCreateItem",
                      v65);
          if ( (int)--*((_DWORD *)v65 + 6) <= 0 )
            operator delete(v65, (const struct std::nothrow_t *)0x40);
        }
        if ( BindCtx >= 0 )
        {
          if ( !v46 )
          {
            v50 = ppva;
            v51 = (CDummyUnknown *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
            *(_QWORD *)&Buf1.Data1 = v51;
            if ( v51 && (v52 = CDummyUnknown::CDummyUnknown(v51)) != 0 )
            {
              BindCtx = (*(__int64 (__fastcall **)(void *, const wchar_t *, CDummyUnknown *))(*(_QWORD *)v50 + 72LL))(
                          v50,
                          L"Parse Translate Aliases",
                          v52);
              if ( (int)--*((_DWORD *)v52 + 6) <= 0 )
                operator delete(v52, (const struct std::nothrow_t *)0x40);
            }
            else
            {
              BindCtx = -2147024882;
            }
            if ( BindCtx < 0 )
              goto LABEL_114;
          }
          pidl = 0;
          v53 = (struct IBindCtx *)ppva;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloBrokerShellObjects>::__private_IsEnabledPreCheck(&`wil::Feature<__WilFeatureTraits_Feature_AppSiloBrokerShellObjects>::GetImpl'::`2'::impl);
          if ( (int)Windows::Security::Isolation::TryBrokerSHParseDisplayName(
                      (Windows::Security::Isolation *)v47,
                      (const unsigned __int16 *)v53,
                      (struct IBindCtx *)&pidl,
                      0,
                      0,
                      v71) < 0 )
          {
            pidl = 0;
            value = 0;
            BindCtx = SHStrDupW(v47, (LPWSTR *)&value);
            if ( BindCtx >= 0 )
            {
              ppshf = 0;
              BindCtx = SHGetDesktopFolder(&ppshf);
              if ( BindCtx >= 0 )
              {
                v56 = 0;
                *(_QWORD *)&Buf1.Data1 = 0;
                v57 = 0;
                if ( v53
                  || (BindCtx = BindCtx_CreateWithObjectParam_1(v55, v54, &Buf1),
                      v56 = *(_QWORD *)&Buf1.Data1,
                      v53 = *(struct IBindCtx **)&Buf1.Data1,
                      v57 = *(_QWORD *)&Buf1.Data1,
                      BindCtx >= 0) )
                {
                  v58 = ppshf;
                  ParseDisplayName = ppshf->lpVtbl->ParseDisplayName;
                  v60 = value;
                  UIWindow = BindCtx_GetUIWindow(v53);
                  BindCtx = ((__int64 (__fastcall *)(IShellFolder *, HWND, struct IBindCtx *, LPCWSTR, _QWORD, LPCITEMIDLIST *, _QWORD))ParseDisplayName)(
                              v58,
                              UIWindow,
                              v53,
                              v60,
                              0,
                              &pidl,
                              0);
                }
                if ( v57 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
              }
              CoTaskMemFree((LPVOID)value);
              if ( ppshf )
                ((void (__fastcall *)(IShellFolder *))ppshf->lpVtbl->Release)(ppshf);
            }
            if ( BindCtx < 0 )
              goto LABEL_114;
          }
          v62 = ppva;
          *ppv = 0;
          value = 0;
          BindCtx = -2147467262;
          ppshf = 0;
          if ( v62
            && (*(int (__fastcall **)(void *, const wchar_t *, IShellFolder **))(*(_QWORD *)v62 + 80LL))(
                 v62,
                 L"ParseAndCreateItem",
                 &ppshf) >= 0 )
          {
            v63 = ((__int64 (__fastcall *)(IShellFolder *, GUID *, LPCWSTR *))ppshf->lpVtbl->QueryInterface)(
                    ppshf,
                    &GUID_67efed0e_e827_4408_b493_78f3982b685c,
                    &value);
            ((void (__fastcall *)(IShellFolder *))ppshf->lpVtbl->Release)(ppshf);
            if ( v63 < 0 )
              goto LABEL_112;
            BindCtx = (*(__int64 (__fastcall **)(LPCWSTR, GUID *, struct IShellItem2 **))(*(_QWORD *)value + 32LL))(
                        value,
                        &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
                        ppv);
            (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)value + 16LL))(value);
          }
          if ( BindCtx >= 0 )
          {
LABEL_113:
            CoTaskMemFree((LPVOID)pidl);
LABEL_114:
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppva + 16LL))(ppva);
LABEL_115:
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
            goto LABEL_27;
          }
LABEL_112:
          BindCtx = SHCreateItemFromIDList(pidl, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, (void **)ppv);
          goto LABEL_113;
        }
LABEL_129:
        SafeRelease<IFilterCreationCallback>(&ppva);
        goto LABEL_115;
      }
    }
  }
  return (unsigned int)BindCtx;
}

```

## disassembly

```asm
0x1800e5a70  mov     [rsp-8+arg_18], rbx
0x1800e5a75  push    rbp
0x1800e5a76  push    rsi
0x1800e5a77  push    rdi
0x1800e5a78  push    r12
0x1800e5a7a  push    r13
0x1800e5a7c  push    r14
0x1800e5a7e  push    r15
0x1800e5a80  lea     rbp, [rsp-250h]
0x1800e5a88  sub     rsp, 350h
0x1800e5a8f  movaps  [rsp+380h+var_40], xmm6
0x1800e5a97  mov     rax, cs:__security_cookie
0x1800e5a9e  xor     rax, rsp
0x1800e5aa1  mov     [rbp+280h+var_50], rax
0x1800e5aa8  mov     r13, r8
0x1800e5aab  mov     r15, rdx
0x1800e5aae  mov     r12, rcx
0x1800e5ab1  xor     r14d, r14d
0x1800e5ab4  mov     [r8], r14
0x1800e5ab7  mov     esi, 80070490h
0x1800e5abc  test    rdx, rdx
0x1800e5abf  jz      loc_1800E5DB5
0x1800e5ac5  movzx   ecx, word ptr [rdx]
0x1800e5ac8  test    cx, cx
0x1800e5acb  jz      loc_1800E5DB5
0x1800e5ad1  mov     rax, rdx
0x1800e5ad4  nop     dword ptr [rax+00h]
0x1800e5ad8  nop     dword ptr [rax+rax+00000000h]
0x1800e5ae0  mov     rbx, rax
0x1800e5ae3  movzx   ecx, cx
0x1800e5ae6  add     rax, rcx
0x1800e5ae9  movzx   ecx, word ptr [rax]
0x1800e5aec  test    cx, cx
0x1800e5aef  jnz     short loc_1800E5AE0
0x1800e5af1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow> `wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl(void)'::`2'::impl
0x1800e5af8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(void)
0x1800e5afd  test    al, al
0x1800e5aff  jnz     loc_1800E658E
0x1800e5b05  movzx   edx, word ptr [rbx]
0x1800e5b08  mov     rdi, r14
0x1800e5b0b  movzx   ecx, dx
0x1800e5b0e  movzx   r8d, word ptr [rbx+rcx-2]
0x1800e5b14  mov     r10d, 0BEEFh
0x1800e5b1a  test    r8w, r8w
0x1800e5b1e  jz      short loc_1800E5B58
0x1800e5b20  lea     rax, [r8+8]
0x1800e5b24  cmp     rax, rcx
0x1800e5b27  jnb     short loc_1800E5B58
0x1800e5b29  lea     rdi, [rbx+r8]
0x1800e5b2d  movzx   ecx, word ptr [rdi]
0x1800e5b30  cmp     ecx, 8
0x1800e5b33  jb      loc_1800E6419
0x1800e5b39  mov     eax, [rdi+4]
0x1800e5b3c  shr     rax, 10h
0x1800e5b40  cmp     ax, r10w
0x1800e5b44  jnz     loc_1800E6419
0x1800e5b4a  add     ecx, r8d
0x1800e5b4d  movzx   eax, dx
0x1800e5b50  cmp     ecx, eax
0x1800e5b52  ja      loc_1800E6419
0x1800e5b58  movzx   ecx, word ptr [rbx]
0x1800e5b5b  add     rcx, rbx
0x1800e5b5e  test    rdi, rdi
0x1800e5b61  jz      loc_1800E5DB5
0x1800e5b67  lea     rbx, [rdi+8]
0x1800e5b6b  cmp     dword ptr [rdi+4], 0BEEF0026h
0x1800e5b72  jnz     loc_1800E5DE9
0x1800e5b78  xor     eax, eax
0x1800e5b7a  mov     [rbp+280h+var_2C4], rax
0x1800e5b7e  xor     edx, edx; Val
0x1800e5b80  mov     r8d, 234h; Size
0x1800e5b86  lea     rcx, [rbp+280h+var_2B4]; void *
0x1800e5b8a  call    memset_0
0x1800e5b8f  mov     eax, [rbx]
0x1800e5b91  mov     [rbp+280h+var_2D0], eax
0x1800e5b94  mov     rax, [rdi+0Ch]
0x1800e5b98  mov     [rbp+280h+var_2CC], rax
0x1800e5b9c  mov     rax, [rdi+14h]
0x1800e5ba0  mov     [rbp+280h+var_2BC], rax
0x1800e5ba4  cmp     word ptr [rdi+2], 1
0x1800e5ba9  jb      short loc_1800E5BB3
0x1800e5bab  mov     rax, [rdi+1Ch]
0x1800e5baf  mov     [rbp+280h+var_2C4], rax
0x1800e5bb3  mov     [rbp+280h+pv], r14
0x1800e5bb7  lea     r9, [rbp+280h+pv]; unsigned __int16 **
0x1800e5bbb  mov     r8d, 8000h; unsigned int
0x1800e5bc1  mov     rdx, r15; struct IDLREGITEM *
0x1800e5bc4  mov     rcx, r12; this
0x1800e5bc7  call    ?_GetDisplayName@CRegFolder@@AEAAJPEFBUIDLREGITEM@@KPEAPEAG@Z; CRegFolder::_GetDisplayName(IDLREGITEM const *,ulong,ushort * *)
0x1800e5bcc  test    eax, eax
0x1800e5bce  js      loc_1800E5D6F
0x1800e5bd4  mov     [rsp+380h+ppbc], r14
0x1800e5bd9  mov     [rsp+380h+pidl], r14
0x1800e5bde  mov     esi, 8007000Eh
0x1800e5be3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800e5bea  mov     ecx, 278h; unsigned __int64
0x1800e5bef  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800e5bf4  mov     rbx, rax
0x1800e5bf7  mov     qword ptr [rsp+380h+Buf1], rax
0x1800e5bfc  test    rax, rax
0x1800e5bff  jz      loc_1800E5D53
0x1800e5c05  lea     rax, ??_7CFileSysBindData@@6B@; const CFileSysBindData::`vftable'
0x1800e5c0c  mov     [rbx], rax
0x1800e5c0f  mov     dword ptr [rbx+8], 1
0x1800e5c16  lea     rcx, [rbx+28h]; void *
0x1800e5c1a  xor     edx, edx; Val
0x1800e5c1c  mov     r8d, 250h; Size
0x1800e5c22  call    memset_0
0x1800e5c27  xor     eax, eax
0x1800e5c29  mov     [rbx+10h], rax
0x1800e5c2d  movups  xmm0, cs:xmmword_180702890
0x1800e5c34  movups  xmmword ptr [rbx+18h], xmm0
0x1800e5c38  mov     rax, [rbx]
0x1800e5c3b  lea     r8, [rsp+380h+pidl]
0x1800e5c40  lea     rdx, _GUID_01e18d10_4d8b_11d2_855d_006008059367
0x1800e5c47  mov     rcx, rbx
0x1800e5c4a  mov     rax, [rax]
0x1800e5c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5c52  mov     esi, eax
0x1800e5c54  mov     rax, [rbx]
0x1800e5c57  mov     rcx, rbx
0x1800e5c5a  mov     rax, [rax+10h]
0x1800e5c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5c63  test    esi, esi
0x1800e5c65  js      loc_1800E5D53
0x1800e5c6b  mov     rcx, [rsp+380h+pidl]
0x1800e5c70  mov     rax, [rcx]
0x1800e5c73  lea     rdx, [rbp+280h+var_2D0]
0x1800e5c77  mov     rax, [rax+18h]
0x1800e5c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5c80  mov     [rsp+380h+ppbc], r14
0x1800e5c85  lea     rdx, [rsp+380h+ppbc]; ppbc
0x1800e5c8a  xor     ecx, ecx; reserved
0x1800e5c8c  call    cs:__imp_CreateBindCtx
0x1800e5c92  mov     esi, eax
0x1800e5c94  test    eax, eax
0x1800e5c96  js      short loc_1800E5CCA
0x1800e5c98  mov     qword ptr [rsp+380h+Buf1], 10h
0x1800e5ca1  mov     qword ptr [rsp+380h+Buf1+8], 1000h
0x1800e5caa  mov     rcx, [rsp+380h+ppbc]
0x1800e5caf  mov     rax, [rcx]
0x1800e5cb2  lea     rdx, [rsp+380h+Buf1]
0x1800e5cb7  mov     rax, [rax+30h]
0x1800e5cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5cc0  mov     esi, eax
0x1800e5cc2  test    eax, eax
0x1800e5cc4  js      loc_1800E65B8
0x1800e5cca  test    esi, esi
0x1800e5ccc  js      short loc_1800E5D15
0x1800e5cce  movups  xmm0, xmmword ptr cs:aFileSystemBind; "File System Bind Data"
0x1800e5cd5  movups  [rbp+280h+var_80], xmm0
0x1800e5cdc  movups  xmm1, xmmword ptr cs:aFileSystemBind+10h; "tem Bind Data"
0x1800e5ce3  movups  [rbp+280h+var_70], xmm1
0x1800e5cea  movups  xmm0, xmmword ptr cs:aFileSystemBind+1Ch; "nd Data"
0x1800e5cf1  movups  [rbp+280h+var_70+0Ch], xmm0
0x1800e5cf8  mov     rcx, [rsp+380h+ppbc]
0x1800e5cfd  mov     rax, [rcx]
0x1800e5d00  mov     r8, [rsp+380h+pidl]
0x1800e5d05  lea     rdx, [rbp+280h+var_80]
0x1800e5d0c  mov     rax, [rax+48h]
0x1800e5d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5d15  mov     rcx, [rsp+380h+pidl]
0x1800e5d1a  mov     rax, [rcx]
0x1800e5d1d  mov     rax, [rax+10h]
0x1800e5d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5d26  test    esi, esi
0x1800e5d28  js      short loc_1800E5D53
0x1800e5d2a  mov     rdi, [rsp+380h+ppbc]
0x1800e5d2f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800e5d36  mov     ecx, 40h ; '@'; unsigned __int64
0x1800e5d3b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800e5d40  mov     qword ptr [rsp+380h+Buf1], rax
0x1800e5d45  test    rax, rax
0x1800e5d48  jnz     loc_1800E5E00
0x1800e5d4e  mov     esi, 8007000Eh
0x1800e5d53  mov     rcx, [rsp+380h+ppbc]
0x1800e5d58  test    rcx, rcx
0x1800e5d5b  jz      short loc_1800E5D6F
0x1800e5d5d  mov     [rsp+380h+ppbc], r14
0x1800e5d62  mov     rax, [rcx]
0x1800e5d65  mov     rax, [rax+10h]
0x1800e5d69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5d6e  nop
0x1800e5d6f  mov     rcx, [rbp+280h+pv]; pv
0x1800e5d73  test    rcx, rcx
0x1800e5d76  jz      short loc_1800E5DB5
0x1800e5d78  call    cs:__imp_CoTaskMemFree
0x1800e5d7e  jmp     short loc_1800E5DB5
0x1800e5d80  lea     rax, [rdx+8]
0x1800e5d84  cmp     rax, rcx
0x1800e5d87  ja      short loc_1800E5DB5
0x1800e5d89  mov     eax, [rdx+4]
0x1800e5d8c  shr     rax, 10h
0x1800e5d90  cmp     ax, r10w
0x1800e5d94  jnz     short loc_1800E5DB5
0x1800e5d96  movzx   eax, word ptr [rdx]
0x1800e5d99  add     rax, rdx
0x1800e5d9c  cmp     rax, rcx
0x1800e5d9f  ja      short loc_1800E5DB5
0x1800e5da1  cmp     rdx, rbx
0x1800e5da4  jb      short loc_1800E5DB5
0x1800e5da6  mov     r8, rdx
0x1800e5da9  mov     rdi, r8
0x1800e5dac  test    r8, r8
0x1800e5daf  jnz     loc_1800E5B67
0x1800e5db5  mov     eax, esi
0x1800e5db7  mov     rcx, [rbp+280h+var_50]
0x1800e5dbe  xor     rcx, rsp; StackCookie
0x1800e5dc1  call    __security_check_cookie
0x1800e5dc6  mov     rbx, [rsp+380h+arg_18]
0x1800e5dce  movaps  xmm6, [rsp+380h+var_40]
0x1800e5dd6  add     rsp, 350h
0x1800e5ddd  pop     r15
0x1800e5ddf  pop     r14
0x1800e5de1  pop     r13
0x1800e5de3  pop     r12
0x1800e5de5  pop     rdi
0x1800e5de6  pop     rsi
0x1800e5de7  pop     rbp
0x1800e5de8  retn
0x1800e5de9  mov     r8, r14
0x1800e5dec  cmp     rbx, rcx
0x1800e5def  ja      short loc_1800E5DA9
0x1800e5df1  movzx   edx, word ptr [rdi]
0x1800e5df4  add     rdx, rdi
0x1800e5df7  cmp     rdx, rcx
0x1800e5dfa  jz      short loc_1800E5DB5
0x1800e5dfc  ja      short loc_1800E5DA9
0x1800e5dfe  jmp     short loc_1800E5D80
0x1800e5e00  mov     rcx, rax; this
0x1800e5e03  call    ??0CDummyUnknown@@QEAA@XZ; CDummyUnknown::CDummyUnknown(void)
0x1800e5e08  mov     rbx, rax
0x1800e5e0b  test    rax, rax
0x1800e5e0e  jz      loc_1800E5D4E
0x1800e5e14  mov     rcx, [rdi]
0x1800e5e17  mov     rax, [rcx+48h]
0x1800e5e1b  mov     r8, rbx
0x1800e5e1e  lea     rdx, aBlockregitempa; "BlockRegItemParsing"
0x1800e5e25  mov     rcx, rdi
0x1800e5e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5e2d  mov     esi, eax
0x1800e5e2f  mov     rcx, rbx; this
0x1800e5e32  call    ?Release@CDummyUnknown@@UEAAKXZ; CDummyUnknown::Release(void)
0x1800e5e37  test    esi, esi
0x1800e5e39  js      loc_1800E5D53
0x1800e5e3f  movzx   eax, word ptr [r15]
0x1800e5e43  cmp     eax, 7
0x1800e5e46  jbe     short loc_1800E5E5A
0x1800e5e48  movzx   edx, word ptr [r15+4]
0x1800e5e4d  lea     rcx, [rdx+26h]; this
0x1800e5e51  cmp     rax, rcx
0x1800e5e54  jnb     loc_1800E64A2
0x1800e5e5a  movzx   eax, byte ptr [r12+168h]
0x1800e5e63  cmp     [r15+2], al
0x1800e5e67  jz      loc_1800E6586
0x1800e5e6d  mov     eax, [r12+164h]
0x1800e5e75  add     rax, r15
0x1800e5e78  add     rax, 4
0x1800e5e7c  movups  xmm6, xmmword ptr [rax]
0x1800e5e7f  movups  [rsp+380h+Buf1], xmm6
0x1800e5e84  xorps   xmm0, xmm0
0x1800e5e87  xor     eax, eax
0x1800e5e89  movups  [rbp+280h+pitem], xmm0
0x1800e5e8d  movups  [rbp+280h+var_2E8], xmm0
0x1800e5e91  mov     [rbp+280h+var_2D8], rax
0x1800e5e95  xor     edx, edx; int
0x1800e5e97  call    ?_EnsureCacheIsValid@CCLSIDInfoCache@@AEAAHH@Z; CCLSIDInfoCache::_EnsureCacheIsValid(int)
0x1800e5e9c  test    eax, eax
0x1800e5e9e  jz      loc_1800E65C7
0x1800e5ea4  lea     rcx, ?g_clsidInfoCache@@3VCCLSIDInfoCache@@A; SRWLock
0x1800e5eab  call    cs:__imp_AcquireSRWLockShared
0x1800e5eb1  xorps   xmm0, xmm0
0x1800e5eb4  movdqu  [rbp+280h+var_70], xmm0
0x1800e5ebc  mov     [rbp+280h+var_60], r14
0x1800e5ec3  movups  [rbp+280h+var_80], xmm6
0x1800e5eca  mov     rdi, cs:hdsa
0x1800e5ed1  test    rdi, rdi
0x1800e5ed4  jz      short loc_1800E5ED9
0x1800e5ed6  mov     r14d, [rdi]
0x1800e5ed9  xor     esi, esi
0x1800e5edb  dec     r14d
0x1800e5ede  xchg    ax, ax
0x1800e5ee0  cmp     esi, r14d
0x1800e5ee3  jg      loc_1800E64DD
0x1800e5ee9  lea     eax, [r14+rsi]
0x1800e5eed  cdq
0x1800e5eee  sub     eax, edx
0x1800e5ef0  sar     eax, 1
0x1800e5ef2  mov     ebx, eax
0x1800e5ef4  xor     edx, edx
0x1800e5ef6  test    rdi, rdi
0x1800e5ef9  jz      short loc_1800E5F0D
0x1800e5efb  test    eax, eax
0x1800e5efd  js      short loc_1800E5F0D
0x1800e5eff  cmp     eax, [rdi]
0x1800e5f01  jge     short loc_1800E5F0D
0x1800e5f03  mov     edx, eax
0x1800e5f05  imul    edx, [rdi+14h]
0x1800e5f09  add     rdx, [rdi+8]; struct CLSID_CACHE_ENTRY *
0x1800e5f0d  xor     r8d, r8d; __int64
  ... truncated ...
```
