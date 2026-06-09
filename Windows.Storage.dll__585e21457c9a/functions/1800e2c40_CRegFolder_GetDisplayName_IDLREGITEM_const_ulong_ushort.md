# CRegFolder::_GetDisplayName(IDLREGITEM const *,ulong,ushort * *)

- ea: `0x1800e2c40`
- end: `0x1800e3b13`
- name: `?_GetDisplayName@CRegFolder@@AEAAJPEFBUIDLREGITEM@@KPEAPEAG@Z`
- size: `3795`
- prototype: `int(CRegFolder *__hidden this, const struct IDLREGITEM *, unsigned int, unsigned __int16 **)`
- caller_count: `9`
- callee_count: `41`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180094040`
- `0x1800d1d90`
- `0x1800dedc0`
- `0x1800e4500`
- `0x1800e5a70`
- `0x1801ade60`
- `0x18052bcbc`
- `0x18052d778`
- `0x18052e830`

## callees

- `0x18000d6cc`
- `0x1800361c8`
- `0x1800586b0`
- `0x18005f240`
- `0x18005f6c0`
- `0x1800a36b4`
- `0x1800a376c`
- `0x1800ccbd0`
- `0x1800d0990`
- `0x1800d13a0`
- `0x1800d2dc0`
- `0x1800dd190`
- `0x1800dd1c0`
- `0x1800dd310`
- `0x1800dfcf0`
- `0x1800e1b30`
- `0x1800e1c70`
- `0x1800e1c90`
- `0x1800e2c40`
- `0x1800e4330`
- `0x1800e4730`
- `0x1800e4810`
- `0x1800e5690`
- `0x1800e5a70`
- `0x180129da0`
- `0x18014c06c`
- `0x18014d4e0`
- `0x18016b130`
- `0x1801f7890`
- `0x18027fca0`
- `0x180288824`
- `0x1802c0f84`
- `0x1803440d0`
- `0x1803a4cb0`
- `0x1803a570a`
- `0x1803a57e0`
- `0x1803a96d9`
- `0x1803a96e5`
- `0x1803d3328`
- `0x18052bf88`
- `0x18065a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800e3a9f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800e3a9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e2ea3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e38fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e2ea3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e38fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e3939`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e3939`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800e2dae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800e2dae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e391c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e391c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e302a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e302a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800e30f5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800e3240`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800e30f5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800e3240`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e32cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e32cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3048`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3146`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e320d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3393`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3419`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e381a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e382b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3840`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e38e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3048`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3146`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e320d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3393`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3419`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e381a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e382b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3840`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e38e1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800e3785`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800e3785`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x1800e2ff3`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x1800e2ff3`
- `SHCORE!__imp_StrRetToStrW` at `0x1800e31b0`
- `SHCORE!__imp_StrRetToStrW` at `0x1800e3489`
- `SHCORE!__imp_StrRetToStrW` at `0x1800e31b0`
- `SHCORE!__imp_StrRetToStrW` at `0x1800e3489`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800e3746`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800e3746`

## string_xrefs

- `0x1800e38ba`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CRegFolder::_GetDisplayName(
        struct IShellItem2 *this,
        const struct IDLREGITEM *a2,
        unsigned int a3,
        unsigned __int16 **a4)
{
  unsigned int v4; // r15d
  const struct IDLREGITEM *v5; // rdi
  struct IShellItem2 *v6; // r14
  int v7; // ebx
  unsigned __int64 v8; // rax
  __int64 v9; // rdx
  unsigned __int64 v10; // rax
  __int64 v11; // rdx
  const struct IDLREGITEM *v12; // rax
  __m128i v13; // xmm0
  int v14; // esi
  CCLSIDInfoCache *v15; // rcx
  HRESULT CachedRegFolder; // r12d
  unsigned __int64 v17; // rax
  __int64 v18; // r8
  const struct IDLREGITEM *v19; // rax
  struct _GUID *v20; // rax
  CCLSIDInfoCache *v21; // rcx
  HDSA v22; // rsi
  int v23; // r15d
  int v24; // r14d
  int v25; // r15d
  int v26; // eax
  int v27; // ebx
  const struct CLSID_CACHE_ENTRY *v28; // rdx
  int v29; // eax
  const struct CLSID_CACHE_ENTRY *v30; // rdx
  int v31; // eax
  __int64 v32; // rax
  const struct IDLREGITEM *v33; // rbx
  const struct IDLREGITEM *v34; // rsi
  _WORD *v35; // rcx
  int v36; // eax
  struct IShellItem2 *v37; // r14
  __int64 v38; // rcx
  unsigned __int64 v39; // rbx
  LPWSTR v40; // rax
  __int64 v41; // rdx
  __int64 v42; // r9
  struct IShellItem2 *v43; // r8
  WCHAR v44; // cx
  struct IShellItem2 *v45; // rcx
  unsigned __int16 v46; // ax
  const ITEMIDLIST *v47; // rbx
  IShellFolder *v48; // rcx
  LPWSTR v49; // rax
  int lpVtbl; // ebx
  const char *v52; // r9
  struct IShellItem2 *v53; // r15
  __int64 v54; // rcx
  char *v55; // rax
  size_t v56; // rbx
  size_t v57; // r14
  WCHAR *v58; // rax
  WCHAR *v59; // rsi
  struct IShellItem2 *v60; // rcx
  HKEY v61; // rbx
  __int64 v62; // rax
  int v63; // eax
  struct IShellItem2 *v64; // rax
  int v65; // eax
  int v66; // eax
  wil::details::in1diag3 *v67; // rcx
  __int64 v68; // rdx
  struct IShellItem2 *v69; // rcx
  IShellFolder *v70; // rbx
  ITEMIDLIST *v71; // rsi
  _WORD *v72; // rcx
  int v73; // eax
  int v74; // eax
  LPWSTR *cotaskmem_string_nothrow; // rdi
  WCHAR *v76; // rsi
  CCLSIDInfoCache *v77; // rcx
  CCLSIDInfoCache *v78; // rcx
  void **v79; // rax
  int v80; // r9d
  int v81; // eax
  CCLSIDInfoCache *v82; // rcx
  int v83; // r10d
  const ITEMIDLIST *FolderIDList; // rax
  int v85; // eax
  __int64 v86; // rcx
  void **ppv; // [rsp+20h] [rbp-E0h]
  unsigned int *v88; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v89; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v90; // [rsp+38h] [rbp-C8h]
  __int64 v91; // [rsp+40h] [rbp-C0h]
  unsigned __int16 **v92; // [rsp+48h] [rbp-B8h]
  struct IShellItem2 *v93; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR ppsz; // [rsp+60h] [rbp-A0h] BYREF
  IShellFolder *psf; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID v98; // [rsp+78h] [rbp-88h] BYREF
  __int64 v99; // [rsp+88h] [rbp-78h]
  __m128i Buf1; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID pitem; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v102; // [rsp+B0h] [rbp-50h]
  __int64 v103; // [rsp+C0h] [rbp-40h]
  struct _GUID v104; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v105; // [rsp+D8h] [rbp-28h]
  __int64 v106; // [rsp+E8h] [rbp-18h]
  STRRET pstr; // [rsp+F0h] [rbp-10h] BYREF
  int v108; // [rsp+200h] [rbp+100h] BYREF
  OLECHAR sz[46]; // [rsp+204h] [rbp+104h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v92 = a4;
  v4 = a3;
  LODWORD(hKey) = a3;
  v5 = a2;
  v6 = this;
  v93 = this;
  v7 = 0;
  LODWORD(psf) = 0;
  *a4 = 0;
  ppsz = 0;
  if ( !a2 )
    goto LABEL_6;
  v8 = *(unsigned __int16 *)a2;
  if ( (unsigned int)v8 <= 7
    || (v9 = *((unsigned __int16 *)a2 + 2), v8 < v9 + 38)
    || (Buf1 = *(__m128i *)((char *)v5 + v9 + 6), memcmp_0(&Buf1, qword_1806FB0A8, 0x10u)) )
  {
    v10 = *(unsigned __int16 *)v5;
    if ( (unsigned int)v10 > 7 )
    {
      v11 = *((unsigned __int16 *)v5 + 2);
      if ( v10 >= v11 + 38 )
      {
        Buf1 = *(__m128i *)((char *)v5 + v11 + 6);
        if ( !memcmp_0(&Buf1, qword_1806FB0A8, 0x10u) )
        {
          v13 = *(__m128i *)((char *)v5 + *((unsigned __int16 *)v5 + 2) + 22);
          goto LABEL_9;
        }
      }
    }
LABEL_6:
    if ( *((_BYTE *)v5 + 2) == LOBYTE(v6[45].lpVtbl) )
      v12 = v5;
    else
      v12 = (const struct IDLREGITEM *)((char *)v5 + HIDWORD(v6[44].lpVtbl));
    v13 = *(__m128i *)((char *)v12 + 4);
LABEL_9:
    Buf1 = v13;
    v14 = 0;
    ppsz = 0;
    if ( _mm_cvtsi128_si32(v13) != HIDWORD(v6[46].lpVtbl) )
      goto LABEL_10;
    lpVtbl = (int)v6[46].lpVtbl;
    if ( GetTickCount() - lpVtbl < 0x1F4 )
    {
      if ( !_InterlockedIncrement((volatile signed __int32 *)&v6[45].lpVtbl + 1)
        && !memcmp_0(&Buf1, (char *)&v6[46].lpVtbl + 4, 0x10u)
        && HIDWORD(v6[48].lpVtbl) == v4 )
      {
        v53 = v6 + 49;
        if ( v6 == (struct IShellItem2 *)-392LL )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xF89,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v52);
        v54 = 0x7FFFFFFF;
        v55 = (char *)&v6[49];
        do
        {
          if ( !*(_WORD *)v55 )
            break;
          v55 += 2;
          --v54;
        }
        while ( v54 );
        v56 = 2 * ((v55 - (char *)v53) >> 1);
        v57 = v56 + 2;
        v58 = (WCHAR *)CoTaskMemAlloc(v56 + 2);
        v59 = v58;
        if ( v58 )
        {
          if ( v56 )
          {
            if ( v57 < v56 )
            {
              memset_0(v58, 0, v57);
              *(_DWORD *)_o__errno(v86) = 34;
              invalid_parameter_noinfo();
            }
            else
            {
              memcpy_0(v58, v53, v56);
            }
          }
          v59[v56 / 2] = 0;
        }
        v6 = v93;
        _InterlockedDecrement((volatile signed __int32 *)&v93[45].lpVtbl + 1);
        ppsz = v59;
        v14 = 1;
        v4 = (unsigned int)hKey;
        v7 = 0;
LABEL_10:
        if ( v14 )
        {
          CachedRegFolder = 0;
LABEL_95:
          v49 = ppsz;
          ppsz = 0;
          *v92 = v49;
          goto LABEL_96;
        }
        v15 = (CCLSIDInfoCache *)ppsz;
        if ( ppsz )
          wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(ppsz);
        ppsz = 0;
        psf = 0;
        CachedRegFolder = 1;
        if ( v5
          && (v17 = *(unsigned __int16 *)v5, (unsigned int)v17 > 7)
          && (v18 = *((unsigned __int16 *)v5 + 2), v15 = (CCLSIDInfoCache *)(v18 + 38), v17 >= v18 + 38)
          && (v98 = *(struct _GUID *)((char *)v5 + v18 + 6), !memcmp_0(&v98, qword_1806FB0A8, 0x10u)) )
        {
          v20 = (struct _GUID *)((char *)v5 + *((unsigned __int16 *)v5 + 2) + 22);
        }
        else
        {
          if ( *((_BYTE *)v5 + 2) == LOBYTE(v6[45].lpVtbl) )
            v19 = v5;
          else
            v19 = (const struct IDLREGITEM *)((char *)v5 + HIDWORD(v6[44].lpVtbl));
          v20 = (struct _GUID *)((char *)v19 + 4);
        }
        v98 = *v20;
        if ( (v4 & 0xC001) == 0x8000 )
        {
          pitem = 0;
          v102 = 0;
          v103 = 0;
          if ( (unsigned int)CCLSIDInfoCache::_EnsureCacheIsValid(v15, 0) )
          {
            AcquireSRWLockShared(&g_clsidInfoCache);
            v105 = 0;
            v106 = 0;
            v104 = v98;
            v22 = hdsa;
            if ( hdsa )
              v23 = *(_DWORD *)hdsa;
            else
              v23 = 0;
            v24 = 0;
            v25 = v23 - 1;
            while ( v24 <= v25 )
            {
              v26 = (v25 + v24) / 2;
              v27 = v26;
              v28 = 0;
              if ( v22 && v26 >= 0 && v26 < *(_DWORD *)v22 )
                v28 = (const struct CLSID_CACHE_ENTRY *)(*((_QWORD *)v22 + 1)
                                                       + (unsigned int)(*((_DWORD *)v22 + 5) * v26));
              v29 = CCLSIDInfoCache::s_CompareEntries((const struct CLSID_CACHE_ENTRY *)&v104, v28, 0);
              if ( v29 < 0 )
              {
                v25 = v27 - 1;
              }
              else
              {
                if ( v29 <= 0 )
                {
                  for ( ; v27 > 0; --v27 )
                  {
                    v30 = 0;
                    if ( v22 )
                    {
                      v31 = v27 - 1;
                      if ( v27 - 1 >= 0 && v31 < *(_DWORD *)v22 )
                        v30 = (const struct CLSID_CACHE_ENTRY *)(*((_QWORD *)v22 + 1)
                                                               + (unsigned int)(*((_DWORD *)v22 + 5) * v31));
                    }
                    if ( (unsigned int)CCLSIDInfoCache::s_CompareEntries(
                                         (const struct CLSID_CACHE_ENTRY *)&v104,
                                         v30,
                                         0) )
                      break;
                  }
                  if ( v27 != -1 )
                  {
                    v32 = 0;
                    if ( v22 && v27 >= 0 && v27 < *(_DWORD *)v22 )
                      v32 = *((_QWORD *)v22 + 1) + (unsigned int)(*((_DWORD *)v22 + 5) * v27);
                    pitem = *(struct _GUID *)v32;
                    v102 = *(_OWORD *)(v32 + 16);
                    v103 = *(_QWORD *)(v32 + 32);
                    ReleaseSRWLockShared(&g_clsidInfoCache);
                    v4 = (unsigned int)hKey;
                    goto LABEL_45;
                  }
                  break;
                }
                v24 = v27 + 1;
              }
            }
            ReleaseSRWLockShared(&g_clsidInfoCache);
            pitem = v98;
            CCLSIDInfoCache::_LoadValuesFromRegistry(v77, (struct CLSID_CACHE_ENTRY *)&pitem);
            AcquireSRWLockExclusive(&g_clsidInfoCache);
            if ( (unsigned int)CCLSIDInfoCache::_EnsureCacheIsValid(v78, 1) )
            {
              v81 = CDSA_Base<CLSID_CACHE_ENTRY>::Search(&hdsa, &pitem);
              if ( !(unsigned int)CCLSIDInfoCache::_IsEntry(v82, &v98, v81) )
                DSA_InsertItem(hdsa, v83, &pitem);
            }
            ReleaseSRWLockExclusive(&g_clsidInfoCache);
            v4 = (unsigned int)hKey;
          }
          else
          {
            pitem = v98;
            CCLSIDInfoCache::_LoadValuesFromRegistry(v21, (struct CLSID_CACHE_ENTRY *)&pitem);
          }
LABEL_45:
          v7 = (HIDWORD(v103) >> 3) & 1;
        }
        else
        {
          if ( (v4 & 0x8000) != 0 && (v4 & 0x4000) == 0 )
          {
            v37 = v93;
            goto LABEL_70;
          }
          hKey = 0;
          if ( (int)SHRegGetCLSIDKey(&v98, 0, 1, 0, 1, &hKey) >= 0 )
          {
            v79 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&psf);
            if ( SHRegAllocData(hKey, 0, 0, v80, v79, v88) < 0 )
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                &psf,
                0);
          }
          if ( !psf && (unsigned int)CCLSIDInfoCache::GetFolderValue(v38, &v98, 1) )
            v7 = 1;
          if ( hKey )
            RegCloseKey(hKey);
        }
        if ( !v7 )
          goto LABEL_67;
        v33 = v5;
        hKey = 0;
        v34 = 0;
        v35 = (_WORD *)((char *)v5 + *(unsigned __int16 *)v5);
        if ( v35 && *v35 )
        {
          v33 = (const struct IDLREGITEM *)ILCloneFirst((LPCITEMIDLIST)v5);
          v36 = 0;
          if ( !v33 )
            v36 = -2147024882;
          CachedRegFolder = v36;
          if ( !v33 )
            goto LABEL_67;
          v34 = v33;
        }
        if ( (!(unsigned int)IsDelegateRegId(v33) || !v33)
          && (!memcmp_0(&GUID_000214e6_0000_0000_c000_000000000046, &IID_IIdentityName, 0x10u)
           || !memcmp_0(&GUID_000214e6_0000_0000_c000_000000000046, &IID_IDelegateItem, 0x10u)) )
        {
          pv = 0;
          v37 = v93;
          CachedRegFolder = CRegFolder::_CreateCachedRegFolder(
                              (CRegFolder *)v93,
                              v33,
                              0,
                              &GUID_000214e6_0000_0000_c000_000000000046,
                              &pv);
          if ( CachedRegFolder >= 0 )
          {
            CachedRegFolder = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, HKEY *))(*(_QWORD *)pv + 64LL))(
                                pv,
                                0,
                                &GUID_000214e6_0000_0000_c000_000000000046,
                                &hKey);
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
          }
          goto LABEL_123;
        }
        if ( memcmp_0(&GUID_000214e6_0000_0000_c000_000000000046, &IID_ICapabilities, 0x10u) )
        {
          v37 = v93;
          CachedRegFolder = CRegFolder::_CreateCachedRegFolder(
                              (CRegFolder *)v93,
                              v33,
                              0,
                              &GUID_000214e6_0000_0000_c000_000000000046,
                              (void **)&hKey);
          if ( CachedRegFolder != -2147467262 )
          {
LABEL_123:
            CoTaskMemFree(v34);
            if ( CachedRegFolder >= 0 )
            {
              if ( psf )
                wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(psf);
              v61 = hKey;
              psf = 0;
              memset_0(&pstr, 0, sizeof(pstr));
              CachedRegFolder = (*(__int64 (__fastcall **)(HKEY, const ITEMIDLIST *, _QWORD, STRRET *))(*(_QWORD *)v61 + 88LL))(
                                  v61,
                                  &c_idlDesktop,
                                  v4,
                                  &pstr);
              if ( CachedRegFolder )
              {
                if ( CachedRegFolder == -2147467263 )
                  CachedRegFolder = 1;
              }
              else
              {
                CachedRegFolder = StrRetToStrW(&pstr, &c_idlDesktop, (LPWSTR *)&psf);
              }
              (*(void (__fastcall **)(HKEY))(*(_QWORD *)hKey + 16LL))(hKey);
            }
            goto LABEL_68;
          }
          if ( !memcmp_0(&GUID_000214e6_0000_0000_c000_000000000046, &IID_IPropertyStoreFactory, 0x10u) )
          {
            v93 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
            CachedRegFolder = CRegFolder::_GetTargetFileSystemItem((CRegFolder *)v37, v33, &v93);
            if ( CachedRegFolder >= 0 )
            {
              ppv = (void **)&hKey;
              CachedRegFolder = ((__int64 (__fastcall *)(struct IShellItem2 *, _QWORD, const GUID *, GUID *))v93->lpVtbl->BindToHandler)(
                                  v93,
                                  0,
                                  &BHID_SFObject,
                                  &GUID_000214e6_0000_0000_c000_000000000046);
            }
            v60 = v93;
            if ( v93 )
            {
              v93 = 0;
              ((void (__fastcall *)(struct IShellItem2 *))v60->lpVtbl->Release)(v60);
            }
            goto LABEL_123;
          }
          CoTaskMemFree(v34);
LABEL_68:
          if ( psf )
            ppsz = (LPWSTR)psf;
LABEL_70:
          v39 = -1;
          if ( CachedRegFolder != 1 )
          {
LABEL_71:
            if ( CachedRegFolder < 0 )
              goto LABEL_96;
            v40 = ppsz;
            do
              ++v39;
            while ( ppsz[v39] );
            if ( v39 < 0x40 )
            {
              if ( !_InterlockedIncrement((volatile signed __int32 *)&v37[45].lpVtbl + 1) )
              {
                v41 = 2147483646;
                v42 = 64;
                v43 = v37 + 49;
                do
                {
                  if ( !v41 )
                    break;
                  v44 = *v40;
                  if ( !*v40 )
                    break;
                  ++v40;
                  LOWORD(v43->lpVtbl) = v44;
                  v43 = (struct IShellItem2 *)((char *)v43 + 2);
                  --v41;
                  --v42;
                }
                while ( v42 );
                v45 = (struct IShellItem2 *)((char *)v43 - 2);
                if ( v42 )
                  v45 = v43;
                LOWORD(v45->lpVtbl) = 0;
                HIDWORD(v37[48].lpVtbl) = v4;
                *(__m128i *)((char *)&v37[46].lpVtbl + 4) = Buf1;
                LODWORD(v37[46].lpVtbl) = GetTickCount();
              }
              _InterlockedDecrement((volatile signed __int32 *)&v37[45].lpVtbl + 1);
            }
            goto LABEL_95;
          }
          v89 = 0;
          v90 = 0;
          v91 = 0;
          *(_QWORD *)&v98.Data1 = 0;
          *(_QWORD *)v98.Data4 = 0;
          v99 = 0;
          if ( (v4 & 0x8000) != 0 )
          {
            if ( (v4 & 1) == 0 && !(unsigned int)CRegFolder::_IsDesktop((CRegFolder *)v37) )
            {
              v90 = -1;
              v91 = -1;
              FolderIDList = (const ITEMIDLIST *)CRegFolder::_GetFolderIDList((CRegFolder *)v37);
              v85 = SHGetNameAndFlagsAlloc(FolderIDList, v4);
              if ( v85 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x6D7,
                  (unsigned int)"onecoreuap\\shell\\windows.storage\\regfldr.cpp",
                  (const char *)(unsigned int)v85,
                  (int)ppv);
              else
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(&v89, L"\\");
            }
            if ( (unsigned int)IsAppCompatModeEnabled(5) )
              v4 &= ~0x8000u;
            if ( (v4 & 0x8000) != 0 && (v4 & 0x4000) == 0 )
            {
              v108 = 3801146;
              StringFromGUID2((const GUID *const)&Buf1, sz, 39);
              v73 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
                      &v98,
                      &v108);
              CachedRegFolder = v73;
              if ( v73 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x6F2,
                  (unsigned int)"onecoreuap\\shell\\windows.storage\\regfldr.cpp",
                  (const char *)(unsigned int)v73,
                  (int)ppv);
              goto LABEL_163;
            }
          }
          pv = v5;
          v93 = 0;
          LODWORD(psf) = 1;
          v62 = _lambda_b461f0d585b4e5be4448ff82c363a670_::_lambda_b461f0d585b4e5be4448ff82c363a670_(
                  &pitem,
                  v37,
                  &pv,
                  &v93);
          v63 = lambda_b354619901b1de20493e1a841af0ba1e_::operator()(v62);
          if ( v63 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x659,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\regfldr.cpp",
              (const char *)(unsigned int)v63,
              (int)ppv);
          v64 = v93;
          v99 = -1;
          *(_QWORD *)v98.Data4 = -1;
          if ( v93 )
          {
            v69 = 0;
            v93 = 0;
            *(_QWORD *)&v98.Data1 = v64;
LABEL_181:
            if ( v69 )
              CoTaskMemFree(v69);
LABEL_163:
            if ( CachedRegFolder >= 0 )
            {
              v74 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
                      &v89,
                      &v98);
              CachedRegFolder = v74;
              if ( v74 < 0 )
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x715,
                  (unsigned int)"onecoreuap\\shell\\windows.storage\\regfldr.cpp",
                  (const char *)(unsigned int)v74,
                  (int)ppv);
              }
              else
              {
                cotaskmem_string_nothrow = (LPWSTR *)wil::make_cotaskmem_string_nothrow(
                                                       (wil *)&pv,
                                                       v89,
                                                       0xFFFFFFFFFFFFFFFFuLL);
                if ( &ppsz != cotaskmem_string_nothrow )
                {
                  v76 = *cotaskmem_string_nothrow;
                  if ( ppsz )
                    wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(ppsz);
                  ppsz = v76;
                  *cotaskmem_string_nothrow = 0;
                }
                if ( pv )
                  CoTaskMemFree(pv);
              }
            }
            if ( *(_QWORD *)&v98.Data1 )
              CoTaskMemFree(*(LPVOID *)&v98.Data1);
            if ( v89 )
              CoTaskMemFree(v89);
            goto LABEL_71;
          }
          CachedRegFolder = CRegFolder::_GetRegistryDisplayName((CRegFolder *)v37, v5, (unsigned __int16 **)&v98);
          if ( CachedRegFolder < 0 || !v37[21].lpVtbl || (v4 & 0x8001) != 0 )
          {
LABEL_143:
            v69 = v93;
            goto LABEL_181;
          }
          pitem = (struct _GUID)0LL;
          *(_QWORD *)&v102 = 0;
          v65 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
                  &pitem,
                  g_hinst,
                  4257);
          if ( v65 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x705,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\regfldr.cpp",
              (const char *)(unsigned int)v65,
              (int)ppv);
            goto LABEL_142;
          }
          v104 = (struct _GUID)0LL;
          *(_QWORD *)&v105 = 0;
          v66 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeMessage(
                  &v104,
                  *(_QWORD *)&pitem.Data1,
                  v37[21].lpVtbl,
                  *(_QWORD *)&v98.Data1);
          v67 = retaddr;
          if ( v66 < 0 )
          {
            v68 = 1800;
          }
          else
          {
            v66 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
                    &v98,
                    &v104);
            CachedRegFolder = v66;
            v67 = retaddr;
            if ( v66 >= 0 )
            {
LABEL_141:
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v104);
LABEL_142:
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pitem);
              goto LABEL_143;
            }
            v68 = 1802;
          }
          wil::details::in1diag3::_Log_Hr(
            v67,
            (void *)v68,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\regfldr.cpp",
            (const char *)(unsigned int)v66,
            (int)ppv);
          goto LABEL_141;
        }
        CachedRegFolder = -2147467259;
        CoTaskMemFree(v34);
LABEL_67:
        v37 = v93;
        goto LABEL_68;
      }
      _InterlockedDecrement((volatile signed __int32 *)&v6[45].lpVtbl + 1);
    }
    v7 = 0;
    goto LABEL_10;
  }
  psf = 0;
  Buf1 = *(__m128i *)((char *)v5 + *((unsigned __int16 *)v5 + 2) + 22);
  CachedRegFolder = CRegFolder::_CreateCachedDelegateFolder((CRegFolder *)v6, (const struct _GUID *)&Buf1, &psf, 0);
  if ( CachedRegFolder < 0 )
    goto LABEL_92;
  ppsz = 0;
  v93 = 0;
  v70 = psf;
  if ( !psf || *(_WORD *)v5 && (v72 = (_WORD *)((char *)v5 + *(unsigned __int16 *)v5)) != 0 && *v72 )
  {
    v71 = (ITEMIDLIST *)ILCloneParent(v5);
    if ( !v71 )
    {
      CachedRegFolder = -2147024882;
      goto LABEL_92;
    }
    CachedRegFolder = SHBindToObject(v70, v71, 0, &GUID_000214e6_0000_0000_c000_000000000046, (void **)&v93);
    CoTaskMemFree(v71);
  }
  else
  {
    CachedRegFolder = ((__int64 (__fastcall *)(IShellFolder *, GUID *, struct IShellItem2 **))psf->lpVtbl->QueryInterface)(
                        psf,
                        &GUID_000214e6_0000_0000_c000_000000000046,
                        &v93);
  }
  if ( CachedRegFolder >= 0 )
  {
    v46 = *(_WORD *)v5;
    if ( *(_WORD *)v5 )
    {
      do
      {
        v47 = (const ITEMIDLIST *)v5;
        v5 = (const struct IDLREGITEM *)((char *)v5 + v46);
        v46 = *(_WORD *)v5;
      }
      while ( *(_WORD *)v5 );
    }
    else
    {
      v47 = (const ITEMIDLIST *)v5;
    }
    memset_0(&pstr, 0, sizeof(pstr));
    CachedRegFolder = ((__int64 (__fastcall *)(struct IShellItem2 *, const ITEMIDLIST *, _QWORD, STRRET *))v93->lpVtbl->GetPropertyDescriptionList)(
                        v93,
                        v47,
                        v4,
                        &pstr);
    if ( CachedRegFolder >= 0 )
      CachedRegFolder = StrRetToStrW(&pstr, v47, &ppsz);
    ((void (__fastcall *)(struct IShellItem2 *))v93->lpVtbl->Release)(v93);
  }
LABEL_92:
  v48 = psf;
  if ( psf )
  {
    psf = 0;
    ((void (__fastcall *)(IShellFolder *))v48->lpVtbl->Release)(v48);
  }
  if ( CachedRegFolder >= 0 )
    goto LABEL_95;
LABEL_96:
  if ( ppsz )
    CoTaskMemFree(ppsz);
  return (unsigned int)CachedRegFolder;
}

```

## disassembly

```asm
0x1800e2c40  push    rbp
0x1800e2c42  push    rbx
0x1800e2c43  push    rsi
0x1800e2c44  push    rdi
0x1800e2c45  push    r12
0x1800e2c47  push    r13
0x1800e2c49  push    r14
0x1800e2c4b  push    r15
0x1800e2c4d  lea     rbp, [rsp-178h]
0x1800e2c55  sub     rsp, 278h
0x1800e2c5c  mov     rax, cs:__security_cookie
0x1800e2c63  xor     rax, rsp
0x1800e2c66  mov     [rbp+1B0h+var_50], rax
0x1800e2c6d  mov     [rsp+2B0h+var_268], r9
0x1800e2c72  mov     r15d, r8d
0x1800e2c75  mov     dword ptr [rsp+2B0h+hKey], r8d
0x1800e2c7a  mov     rdi, rdx
0x1800e2c7d  mov     r14, rcx
0x1800e2c80  mov     [rsp+2B0h+var_260], rcx
0x1800e2c85  xor     ebx, ebx
0x1800e2c87  mov     dword ptr [rsp+2B0h+psf], ebx
0x1800e2c8b  mov     [r9], rbx
0x1800e2c8e  mov     [rsp+2B0h+ppsz], rbx
0x1800e2c93  test    rdx, rdx
0x1800e2c96  jz      short loc_1800E2CCA
0x1800e2c98  movzx   eax, word ptr [rdx]
0x1800e2c9b  cmp     eax, 7
0x1800e2c9e  jbe     short loc_1800E2CB1
0x1800e2ca0  movzx   edx, word ptr [rdx+4]
0x1800e2ca4  lea     rcx, [rdx+26h]
0x1800e2ca8  cmp     rax, rcx
0x1800e2cab  jnb     loc_1800E3658
0x1800e2cb1  movzx   eax, word ptr [rdi]
0x1800e2cb4  cmp     eax, 7
0x1800e2cb7  jbe     short loc_1800E2CCA
0x1800e2cb9  movzx   edx, word ptr [rdi+4]
0x1800e2cbd  lea     rcx, [rdx+26h]
0x1800e2cc1  cmp     rax, rcx
0x1800e2cc4  jnb     loc_1800E384B
0x1800e2cca  movzx   eax, byte ptr [r14+168h]
0x1800e2cd2  cmp     [rdi+2], al
0x1800e2cd5  jz      loc_1800E3A6E
0x1800e2cdb  mov     eax, [r14+164h]
0x1800e2ce2  add     rax, rdi
0x1800e2ce5  movups  xmm0, xmmword ptr [rax+4]
0x1800e2ce9  movups  [rbp+1B0h+Buf1], xmm0
0x1800e2ced  mov     esi, ebx
0x1800e2cef  mov     [rsp+2B0h+ppsz], rbx
0x1800e2cf4  mov     r13d, 1
0x1800e2cfa  movd    eax, xmm0
0x1800e2cfe  cmp     eax, [r14+174h]
0x1800e2d05  jz      loc_1800E3239
0x1800e2d0b  test    esi, esi
0x1800e2d0d  jnz     loc_1800E3119
0x1800e2d13  mov     rcx, [rsp+2B0h+ppsz]; pv
0x1800e2d18  test    rcx, rcx
0x1800e2d1b  jnz     loc_1800E3035
0x1800e2d21  mov     [rsp+2B0h+ppsz], rbx
0x1800e2d26  mov     [rsp+2B0h+psf], rbx
0x1800e2d2b  mov     r12d, r13d
0x1800e2d2e  test    rdi, rdi
0x1800e2d31  jz      short loc_1800E2D4D
0x1800e2d33  movzx   eax, word ptr [rdi]
0x1800e2d36  cmp     eax, 7
0x1800e2d39  jbe     short loc_1800E2D4D
0x1800e2d3b  movzx   r8d, word ptr [rdi+4]
0x1800e2d40  lea     rcx, [r8+26h]; this
0x1800e2d44  cmp     rax, rcx
0x1800e2d47  jnb     loc_1800E3880
0x1800e2d4d  movzx   eax, byte ptr [r14+168h]
0x1800e2d55  cmp     [rdi+2], al
0x1800e2d58  jz      loc_1800E3A76
0x1800e2d5e  mov     eax, [r14+164h]
0x1800e2d65  add     rax, rdi
0x1800e2d68  add     rax, 4
0x1800e2d6c  movups  xmm0, xmmword ptr [rax]
0x1800e2d6f  movups  xmmword ptr [rsp+2B0h+var_238.Data1], xmm0
0x1800e2d74  mov     eax, r15d
0x1800e2d77  and     eax, 0C001h
0x1800e2d7c  cmp     eax, 8000h
0x1800e2d81  jnz     loc_1800E2FC3
0x1800e2d87  xorps   xmm0, xmm0
0x1800e2d8a  xor     eax, eax
0x1800e2d8c  movups  [rbp+1B0h+pitem], xmm0
0x1800e2d90  movups  [rbp+1B0h+var_200], xmm0
0x1800e2d94  mov     [rbp+1B0h+var_1F0], rax
0x1800e2d98  xor     edx, edx; int
0x1800e2d9a  call    ?_EnsureCacheIsValid@CCLSIDInfoCache@@AEAAHH@Z; CCLSIDInfoCache::_EnsureCacheIsValid(int)
0x1800e2d9f  test    eax, eax
0x1800e2da1  jz      loc_1800E3AB5
0x1800e2da7  lea     rcx, ?g_clsidInfoCache@@3VCCLSIDInfoCache@@A; SRWLock
0x1800e2dae  call    cs:__imp_AcquireSRWLockShared
0x1800e2db4  xorps   xmm0, xmm0
0x1800e2db7  movdqu  [rbp+1B0h+var_1D8], xmm0
0x1800e2dbc  mov     [rbp+1B0h+var_1C8], rbx
0x1800e2dc0  movups  xmm0, xmmword ptr [rsp+2B0h+var_238.Data1]
0x1800e2dc5  movups  [rbp+1B0h+var_1E8], xmm0
0x1800e2dc9  mov     rsi, cs:hdsa
0x1800e2dd0  test    rsi, rsi
0x1800e2dd3  jz      loc_1800E3A7E
0x1800e2dd9  mov     r15d, [rsi]
0x1800e2ddc  mov     r14d, ebx
0x1800e2ddf  dec     r15d
0x1800e2de2  cmp     r14d, r15d
0x1800e2de5  jg      loc_1800E38F6
0x1800e2deb  lea     eax, [r15+r14]
0x1800e2def  cdq
0x1800e2df0  sub     eax, edx
0x1800e2df2  sar     eax, 1
0x1800e2df4  mov     ebx, eax
0x1800e2df6  xor     edx, edx
0x1800e2df8  test    rsi, rsi
0x1800e2dfb  jz      short loc_1800E2E0F
0x1800e2dfd  test    eax, eax
0x1800e2dff  js      short loc_1800E2E0F
0x1800e2e01  cmp     eax, [rsi]
0x1800e2e03  jge     short loc_1800E2E0F
0x1800e2e05  mov     edx, eax
0x1800e2e07  imul    edx, [rsi+14h]
0x1800e2e0b  add     rdx, [rsi+8]; struct CLSID_CACHE_ENTRY *
0x1800e2e0f  xor     r8d, r8d; __int64
0x1800e2e12  lea     rcx, [rbp+1B0h+var_1E8]; struct CLSID_CACHE_ENTRY *
0x1800e2e16  call    ?s_CompareEntries@CCLSIDInfoCache@@CAHPEBUCLSID_CACHE_ENTRY@@0_J@Z; CCLSIDInfoCache::s_CompareEntries(CLSID_CACHE_ENTRY const *,CLSID_CACHE_ENTRY const *,__int64)
0x1800e2e1b  test    eax, eax
0x1800e2e1d  js      short loc_1800E2E27
0x1800e2e1f  jle     short loc_1800E2E2D
0x1800e2e21  lea     r14d, [rbx+1]
0x1800e2e25  jmp     short loc_1800E2DE2
0x1800e2e27  lea     r15d, [rbx-1]
0x1800e2e2b  jmp     short loc_1800E2DE2
0x1800e2e2d  test    ebx, ebx
0x1800e2e2f  jle     short loc_1800E2E61
0x1800e2e31  xor     edx, edx
0x1800e2e33  test    rsi, rsi
0x1800e2e36  jz      short loc_1800E2E4D
0x1800e2e38  lea     eax, [rbx-1]
0x1800e2e3b  test    eax, eax
0x1800e2e3d  js      short loc_1800E2E4D
0x1800e2e3f  cmp     eax, [rsi]
0x1800e2e41  jge     short loc_1800E2E4D
0x1800e2e43  imul    eax, [rsi+14h]
0x1800e2e47  mov     edx, eax
0x1800e2e49  add     rdx, [rsi+8]; struct CLSID_CACHE_ENTRY *
0x1800e2e4d  xor     r8d, r8d; __int64
0x1800e2e50  lea     rcx, [rbp+1B0h+var_1E8]; struct CLSID_CACHE_ENTRY *
0x1800e2e54  call    ?s_CompareEntries@CCLSIDInfoCache@@CAHPEBUCLSID_CACHE_ENTRY@@0_J@Z; CCLSIDInfoCache::s_CompareEntries(CLSID_CACHE_ENTRY const *,CLSID_CACHE_ENTRY const *,__int64)
0x1800e2e59  test    eax, eax
0x1800e2e5b  jz      loc_1800E3A86
0x1800e2e61  cmp     ebx, 0FFFFFFFFh
0x1800e2e64  jz      loc_1800E38F6
0x1800e2e6a  xor     eax, eax
0x1800e2e6c  test    rsi, rsi
0x1800e2e6f  jz      short loc_1800E2E83
0x1800e2e71  test    ebx, ebx
0x1800e2e73  js      short loc_1800E2E83
0x1800e2e75  cmp     ebx, [rsi]
0x1800e2e77  jge     short loc_1800E2E83
0x1800e2e79  imul    ebx, [rsi+14h]
0x1800e2e7d  mov     eax, ebx
0x1800e2e7f  add     rax, [rsi+8]
0x1800e2e83  movups  xmm0, xmmword ptr [rax]
0x1800e2e86  movups  [rbp+1B0h+pitem], xmm0
0x1800e2e8a  movups  xmm1, xmmword ptr [rax+10h]
0x1800e2e8e  movups  [rbp+1B0h+var_200], xmm1
0x1800e2e92  movsd   xmm0, qword ptr [rax+20h]
0x1800e2e97  movsd   [rbp+1B0h+var_1F0], xmm0
0x1800e2e9c  lea     rcx, ?g_clsidInfoCache@@3VCCLSIDInfoCache@@A; SRWLock
0x1800e2ea3  call    cs:__imp_ReleaseSRWLockShared
0x1800e2ea9  mov     r15d, dword ptr [rsp+2B0h+hKey]
0x1800e2eae  mov     ebx, dword ptr [rbp+1B0h+var_1F0+4]
0x1800e2eb1  shr     ebx, 3
0x1800e2eb4  and     ebx, r13d
0x1800e2eb7  test    ebx, ebx
0x1800e2eb9  jz      loc_1800E304E
0x1800e2ebf  mov     rbx, rdi
0x1800e2ec2  mov     [rsp+2B0h+hKey], 0
0x1800e2ecb  xor     esi, esi
0x1800e2ecd  movzx   ecx, word ptr [rdi]
0x1800e2ed0  add     rcx, rdi
0x1800e2ed3  jz      short loc_1800E2F00
0x1800e2ed5  cmp     [rcx], si
0x1800e2ed8  jz      short loc_1800E2F00
0x1800e2eda  mov     rcx, rdi; pidl
0x1800e2edd  call    ILCloneFirst
0x1800e2ee2  mov     rbx, rax
0x1800e2ee5  xor     eax, eax
0x1800e2ee7  mov     r12d, 8007000Eh
0x1800e2eed  test    rbx, rbx
0x1800e2ef0  cmovz   eax, r12d
0x1800e2ef4  mov     r12d, eax
0x1800e2ef7  jz      loc_1800E304E
0x1800e2efd  mov     rsi, rbx
0x1800e2f00  mov     rcx, rbx
0x1800e2f03  call    IsDelegateRegId
0x1800e2f08  test    eax, eax
0x1800e2f0a  jz      short loc_1800E2F15
0x1800e2f0c  test    rbx, rbx
0x1800e2f0f  jnz     loc_1800E3320
0x1800e2f15  mov     r8d, 10h; Size
0x1800e2f1b  lea     rdx, IID_IIdentityName; Buf2
0x1800e2f22  lea     rcx, _GUID_000214e6_0000_0000_c000_000000000046; Buf1
0x1800e2f29  call    memcmp_0
0x1800e2f2e  test    eax, eax
0x1800e2f30  jz      short loc_1800E2F53
0x1800e2f32  mov     r8d, 10h; Size
0x1800e2f38  lea     rdx, IID_IDelegateItem; Buf2
0x1800e2f3f  lea     rcx, _GUID_000214e6_0000_0000_c000_000000000046; Buf1
0x1800e2f46  call    memcmp_0
0x1800e2f4b  test    eax, eax
0x1800e2f4d  jnz     loc_1800E3320
0x1800e2f53  mov     [rsp+2B0h+pv], 0
0x1800e2f5c  lea     rax, [rsp+2B0h+pv]
0x1800e2f61  mov     [rsp+2B0h+ppv], rax; void **
0x1800e2f66  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; struct _GUID *
0x1800e2f6d  xor     r8d, r8d; pbc
0x1800e2f70  mov     rdx, rbx; struct IDLREGITEM *
0x1800e2f73  mov     r14, [rsp+2B0h+var_260]
0x1800e2f78  mov     rcx, r14; this
0x1800e2f7b  call    ?_CreateCachedRegFolder@CRegFolder@@AEAAJPEFBUIDLREGITEM@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z; CRegFolder::_CreateCachedRegFolder(IDLREGITEM const *,IBindCtx *,_GUID const &,void * *)
0x1800e2f80  mov     r12d, eax
0x1800e2f83  test    eax, eax
0x1800e2f85  js      loc_1800E3416
0x1800e2f8b  mov     rcx, [rsp+2B0h+pv]
0x1800e2f90  mov     rax, [rcx]
0x1800e2f93  lea     r9, [rsp+2B0h+hKey]
0x1800e2f98  lea     r8, _GUID_000214e6_0000_0000_c000_000000000046
0x1800e2f9f  xor     edx, edx
0x1800e2fa1  mov     rax, [rax+40h]
0x1800e2fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2faa  mov     r12d, eax
0x1800e2fad  mov     rcx, [rsp+2B0h+pv]
0x1800e2fb2  mov     rax, [rcx]
0x1800e2fb5  mov     rax, [rax+10h]
0x1800e2fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2fbe  jmp     loc_1800E3416
0x1800e2fc3  bt      r15d, 0Fh
0x1800e2fc8  jb      loc_1800E3643
0x1800e2fce  mov     [rsp+2B0h+hKey], 0
0x1800e2fd7  lea     rax, [rsp+2B0h+hKey]
0x1800e2fdc  mov     [rsp+2B0h+var_288], rax; unsigned int *
0x1800e2fe1  mov     dword ptr [rsp+2B0h+ppv], r13d
0x1800e2fe6  xor     r9d, r9d
0x1800e2fe9  mov     r8d, r13d
0x1800e2fec  xor     edx, edx
0x1800e2fee  lea     rcx, [rsp+2B0h+var_238]
0x1800e2ff3  call    cs:__imp_SHRegGetCLSIDKey
0x1800e2ff9  test    eax, eax
0x1800e2ffb  jns     loc_1800E399C
0x1800e3001  cmp     [rsp+2B0h+psf], 0
0x1800e3007  jnz     short loc_1800E301C
0x1800e3009  mov     r8d, r13d
0x1800e300c  lea     rdx, [rsp+2B0h+var_238]
0x1800e3011  call    ?GetFolderValue@CCLSIDInfoCache@@QEAAHAEBU_GUID@@W4CLSID_FOLDER_VALUE_FLAGS@@@Z; CCLSIDInfoCache::GetFolderValue(_GUID const &,CLSID_FOLDER_VALUE_FLAGS)
0x1800e3016  test    eax, eax
0x1800e3018  cmovnz  ebx, r13d
0x1800e301c  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800e3021  test    rcx, rcx
0x1800e3024  jz      loc_1800E2EB7
0x1800e302a  call    cs:__imp_RegCloseKey
0x1800e3030  jmp     loc_1800E2EB7
0x1800e3035  call    ?close_reset@?$close_invoke_helper@$00P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZPEAG@details@wil@@SAXPEAG@Z; wil::details::close_invoke_helper<1,void (*)(void *),&CoTaskMemFree(void *),ushort *>::close_reset(ushort *)
0x1800e303a  jmp     loc_1800E2D21
0x1800e303f  mov     r12d, 80004005h
0x1800e3045  mov     rcx, rsi; pv
0x1800e3048  call    cs:__imp_CoTaskMemFree
0x1800e304e  mov     r14, [rsp+2B0h+var_260]
0x1800e3053  mov     rax, [rsp+2B0h+psf]
0x1800e3058  test    rax, rax
0x1800e305b  jnz     loc_1800E310F
0x1800e3061  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800e3068  cmp     r12d, 1
0x1800e306c  jz      loc_1800E34AF
0x1800e3072  test    r12d, r12d
0x1800e3075  js      loc_1800E3203
0x1800e307b  mov     rax, [rsp+2B0h+ppsz]
0x1800e3080  inc     rbx
0x1800e3083  cmp     word ptr [rax+rbx*2], 0
0x1800e3088  jnz     short loc_1800E3080
0x1800e308a  cmp     rbx, 40h ; '@'
0x1800e308e  jnb     loc_1800E31ED
0x1800e3094  lock inc dword ptr [r14+16Ch]
0x1800e309c  jnz     short loc_1800E3102
0x1800e309e  mov     edx, 7FFFFFFEh
0x1800e30a3  mov     r9d, 40h ; '@'
0x1800e30a9  lea     r8, [r14+188h]
0x1800e30b0  test    rdx, rdx
0x1800e30b3  jz      short loc_1800E30D2
0x1800e30b5  movzx   ecx, word ptr [rax]
0x1800e30b8  test    cx, cx
0x1800e30bb  jz      short loc_1800E30D2
0x1800e30bd  add     rax, 2
0x1800e30c1  mov     [r8], cx
0x1800e30c5  add     r8, 2
0x1800e30c9  dec     rdx
0x1800e30cc  sub     r9, 1
0x1800e30d0  jnz     short loc_1800E30B0
0x1800e30d2  lea     rcx, [r8-2]
0x1800e30d6  test    r9, r9
0x1800e30d9  cmovnz  rcx, r8
0x1800e30dd  xor     eax, eax
  ... truncated ...
```
