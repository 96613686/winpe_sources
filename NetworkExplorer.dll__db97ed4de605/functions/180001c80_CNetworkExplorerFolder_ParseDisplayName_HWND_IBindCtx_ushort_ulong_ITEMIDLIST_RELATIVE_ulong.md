# CNetworkExplorerFolder::ParseDisplayName(HWND__ *,IBindCtx *,ushort *,ulong *,_ITEMIDLIST_RELATIVE * *,ulong *)

- ea: `0x180001c80`
- end: `0x18000251c`
- name: `?ParseDisplayName@CNetworkExplorerFolder@@UEAAJPEAUHWND__@@PEAUIBindCtx@@PEAGPEAKPEAPEAU_ITEMIDLIST_RELATIVE@@3@Z`
- size: `2204`
- prototype: `int(CNetworkExplorerFolder *__hidden this, HWND, struct IBindCtx *, unsigned __int16 *, unsigned int *, struct _ITEMIDLIST_RELATIVE **, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001c80`
- `0x180002524`
- `0x180002874`
- `0x180005eb4`
- `0x180007c76`
- `0x18000f076`
- `0x18000f0a0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x180001cf2`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x180002090`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x180001cf2`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x180002090`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002308`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002403`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000240d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002416`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002308`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002403`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000240d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002416`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001de5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800022a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001de5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800022a3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000216f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000216f`
- `OLEAUT32!__imp_VariantClear` at `0x180002038`
- `OLEAUT32!__imp_VariantClear` at `0x1800024a5`
- `OLEAUT32!__imp_VariantClear` at `0x180002038`
- `OLEAUT32!__imp_VariantClear` at `0x1800024a5`
- `SHLWAPI!PathStripToRootW` at `0x180001ea1`
- `SHLWAPI!PathStripToRootW` at `0x180001ea1`
- `SHLWAPI!SHStrDupW` at `0x180001e8d`
- `SHLWAPI!SHStrDupW` at `0x18000249b`
- `SHLWAPI!SHStrDupW` at `0x180001e8d`
- `SHLWAPI!SHStrDupW` at `0x18000249b`
- `SHELL32!__imp_ILCloneFirst` at `0x180001f73`
- `SHELL32!__imp_ILCloneFirst` at `0x180001f73`
- `SHELL32!__imp_ILCombine` at `0x1800023bc`
- `SHELL32!__imp_ILCombine` at `0x1800023bc`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180001ed3`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180001ed3`
- `SHELL32!__imp_ILFree` at `0x180002041`
- `SHELL32!__imp_ILFree` at `0x18000204c`
- `SHELL32!__imp_ILFree` at `0x1800023d1`
- `SHELL32!__imp_ILFree` at `0x1800023f9`
- `SHELL32!__imp_ILFree` at `0x180002041`
- `SHELL32!__imp_ILFree` at `0x18000204c`
- `SHELL32!__imp_ILFree` at `0x1800023d1`
- `SHELL32!__imp_ILFree` at `0x1800023f9`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800020ae`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800020ae`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolder::ParseDisplayName(
        CNetworkExplorerFolder *this,
        HWND a2,
        struct IBindCtx *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        struct _ITEMIDLIST_RELATIVE **a6,
        unsigned int *a7)
{
  unsigned int *v8; // r12
  __int64 result; // rax
  PCWSTR v12; // rdi
  WCHAR i; // ax
  struct INetworkItemFactory *v14; // rbx
  HRESULT Instance; // edi
  CNetworkExplorerFolder *v16; // rcx
  unsigned __int64 v17; // rbx
  WCHAR *v18; // r12
  unsigned __int64 v19; // r8
  unsigned __int16 *v20; // rcx
  WCHAR *v21; // rdx
  WCHAR *v22; // rcx
  WCHAR *v23; // rax
  WCHAR v24; // dx
  LPWSTR v25; // rbx
  int v26; // r15d
  LPITEMIDLIST v27; // rax
  ITEMIDLIST *v28; // rbx
  const WCHAR *v29; // r14
  IRecordInfo *v30; // rbx
  BOOL IsUNCEx; // eax
  struct IPropertyStoreVtbl *lpVtbl; // rax
  struct IPropertyStore *v33; // rsi
  __int64 v34; // rbx
  int v35; // eax
  ITEMIDLIST *v36; // r14
  struct IPropertyStoreVtbl *v37; // rax
  __int64 v38; // r15
  __int16 v39; // di
  void *v40; // rax
  __int64 v41; // rbx
  CNetworkExplorerFolder *v42; // rcx
  __int64 v43; // rbx
  __int64 v44; // rax
  struct IBindCtx *v45; // rdi
  LPITEMIDLIST v46; // rax
  ITEMIDLIST *v47; // rcx
  LPITEMIDLIST v48; // rbx
  unsigned int *v49; // r8
  struct IPropertyStore *v50; // [rsp+48h] [rbp-C0h] BYREF
  LPCITEMIDLIST pidl; // [rsp+50h] [rbp-B8h] BYREF
  size_t Size; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int *v53; // [rsp+60h] [rbp-A8h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v55; // [rsp+80h] [rbp-88h]
  struct INetworkItemFactory *v56; // [rsp+88h] [rbp-80h] BYREF
  LPWSTR ppwsz; // [rsp+90h] [rbp-78h] BYREF
  void *Src; // [rsp+98h] [rbp-70h] BYREF
  PCNZWCH lpString2; // [rsp+A0h] [rbp-68h] BYREF
  PCWSTR ppszServer; // [rsp+A8h] [rbp-60h] BYREF
  PCWSTR v61; // [rsp+B0h] [rbp-58h] BYREF
  HWND v62; // [rsp+B8h] [rbp-50h]
  struct IBindCtx *v63; // [rsp+C0h] [rbp-48h]
  VARIANTARG psz; // [rsp+C8h] [rbp-40h] BYREF
  PROPERTYKEY v65; // [rsp+E0h] [rbp-28h] BYREF

  v8 = a7;
  v63 = a3;
  v62 = a2;
  v56 = (struct INetworkItemFactory *)a6;
  v53 = a7;
  if ( !a6 )
    return 2147942487LL;
  result = 0;
  if ( a4 )
  {
    ppszServer = 0;
    if ( !PathIsUNCEx(a4, &ppszServer) )
      goto LABEL_8;
    v12 = ppszServer;
    for ( i = *ppszServer; i; ++v12 )
    {
      if ( i == 92 )
        break;
      i = v12[1];
    }
    if ( (char *)v12 - (char *)ppszServer < 0 || (((char *)v12 - (char *)ppszServer) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      goto LABEL_8;
    v17 = v12 - a4;
    v18 = (WCHAR *)CoTaskMemAlloc(2 * v17 + 2);
    if ( !v18 )
    {
      v8 = v53;
LABEL_8:
      v56 = 0;
      result = CNetworkExplorerFolder::GetFactory((CNetworkExplorerFolder *)((char *)this - 32), &v56);
      if ( (int)result < 0 )
        return result;
      v14 = v56;
      v53 = 0;
      Instance = (*(__int64 (__fastcall **)(struct INetworkItemFactory *, unsigned __int16 *, unsigned int **))(*(_QWORD *)v56 + 72LL))(
                   v56,
                   a4,
                   &v53);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(struct INetworkItemFactory *, unsigned int *, struct _ITEMIDLIST_RELATIVE **))(*(_QWORD *)v14 + 104LL))(
                     v14,
                     v53,
                     a6);
        if ( Instance >= 0 && v8 )
        {
          if ( *v8 )
            CNetworkExplorerFolder::_GetAttributesOf(v16, *a6, v8);
        }
        (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v53 + 16LL))(v53);
      }
      (*(void (__fastcall **)(struct INetworkItemFactory *))(*(_QWORD *)v14 + 16LL))(v14);
      return (unsigned int)Instance;
    }
    v19 = v17 + 1;
    *v18 = 0;
    *(_QWORD *)&pvarg.vt = 0;
    if ( v17 <= 0x7FFFFFFE )
    {
      v20 = a4;
      v21 = v18;
      do
      {
        if ( !v17 )
          break;
        if ( !*v20 )
          break;
        *v21++ = *v20++;
        --v17;
        --v19;
      }
      while ( v19 );
      v22 = v21 - 1;
      if ( v19 )
        v22 = v21;
      *v22 = 0;
    }
    v23 = (WCHAR *)(v12 + 1);
    if ( *v12 == 92 )
      v24 = *v23;
    else
      v24 = *v12;
    if ( *v12 != 92 )
      v23 = (WCHAR *)v12;
    if ( v24 )
      *(_QWORD *)&pvarg.vt = v23;
    ppwsz = 0;
    Instance = SHStrDupW(a4, &ppwsz);
    if ( Instance < 0 )
    {
LABEL_79:
      CoTaskMemFree(v18);
      return (unsigned int)Instance;
    }
    PathStripToRootW(ppwsz);
    v25 = ppwsz;
    lpString2 = 0;
    Size = 0;
    Instance = SHCoCreateInstance(
                 0,
                 &CLSID_NetworkPlaces,
                 0,
                 &GUID_000214ea_0000_0000_c000_000000000046,
                 (void **)&Size);
    if ( Instance < 0 )
      goto LABEL_78;
    v26 = 0;
    Instance = (*(__int64 (__fastcall **)(size_t, _QWORD))(*(_QWORD *)Size + 32LL))(Size, *((_QWORD *)this + 9));
    if ( Instance >= 0 )
    {
      v50 = 0;
      Instance = (**(__int64 (__fastcall ***)(size_t, GUID *, struct IPropertyStore **))Size)(
                   Size,
                   &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
                   &v50);
      if ( Instance >= 0 )
      {
        pidl = 0;
        Instance = ((__int64 (__fastcall *)(struct IPropertyStore *, HWND, struct IBindCtx *, LPWSTR, _QWORD, LPCITEMIDLIST *, _QWORD))v50->lpVtbl->GetCount)(
                     v50,
                     v62,
                     a3,
                     v25,
                     0,
                     &pidl,
                     0);
        if ( Instance >= 0 )
        {
          v27 = ILCloneFirst(pidl);
          v28 = v27;
          if ( v27 )
          {
            v65 = PKEY_NetworkProvider;
            memset(&psz, 0, sizeof(psz));
            if ( ((int (__fastcall *)(struct IPropertyStore *, LPITEMIDLIST, PROPERTYKEY *, VARIANTARG *))v50->lpVtbl[2].AddRef)(
                   v50,
                   v27,
                   &v65,
                   &psz) >= 0 )
            {
              if ( psz.vt == 8 && psz.llVal )
                SHStrDupW(psz.bstrVal, (LPWSTR *)&lpString2);
              VariantClear(&psz);
            }
            v55 = 0;
            v65.pid = 1;
            v65.fmtid = (GUID)PKEY_NetworkResource;
            *(_OWORD *)&pvarg.decVal.Lo32 = 0;
            if ( ((int (__fastcall *)(struct IPropertyStore *, ITEMIDLIST *, PROPERTYKEY *, ULONG *))v50->lpVtbl[2].AddRef)(
                   v50,
                   v28,
                   &v65,
                   &pvarg.decVal.Lo32) >= 0 )
            {
              if ( pvarg.iVal == 8209 && LODWORD(pvarg.pRecInfo[2].lpVtbl->AddRef) == 10 )
                v26 = 10;
              VariantClear((VARIANTARG *)&pvarg.decVal.8);
            }
            ILFree(v28);
          }
          ILFree((LPITEMIDLIST)pidl);
        }
        ((void (__fastcall *)(struct IPropertyStore *))v50->lpVtbl->Release)(v50);
      }
    }
    (*(void (__fastcall **)(size_t))(*(_QWORD *)Size + 16LL))(Size);
    if ( Instance < 0 )
    {
LABEL_78:
      CoTaskMemFree(ppwsz);
      goto LABEL_79;
    }
    v29 = lpString2;
    v30 = (IRecordInfo *)(v18 + 2);
    v61 = 0;
    IsUNCEx = PathIsUNCEx(v18 + 2, &v61);
    v50 = 0;
    if ( IsUNCEx )
      v30 = (IRecordInfo *)v61;
    Instance = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, (void **)&v50);
    if ( Instance >= 0 )
    {
      v55 = 0;
      pvarg.llVal = 31;
      pvarg.pRecInfo = v30;
      Instance = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, ULONG *))v50->lpVtbl->SetValue)(
                   v50,
                   &PKEY_ItemNameDisplay,
                   &pvarg.decVal.Lo32);
      if ( Instance >= 0 )
      {
        v55 = 0;
        *(_OWORD *)&pvarg.decVal.Lo32 = 0;
        pvarg.iVal = 11;
        lpVtbl = v50->lpVtbl;
        *((_WORD *)&pvarg.decVal + 8) = -1;
        Instance = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, CY *))lpVtbl->SetValue)(
                     v50,
                     &rpkey,
                     &pvarg.cyVal);
        if ( Instance >= 0 )
        {
          if ( !v29
            || CompareStringW(0x7Fu, 1u, L"Microsoft Windows Network", -1, v29, -1) == 2
            || (Instance = IPropertyStore_SetString(v50, &PKEY_NetworkProvider, v29), Instance >= 0) )
          {
            v55 = 0;
            *(_OWORD *)&pvarg.decVal.Lo32 = 0;
            *((_DWORD *)&pvarg.decVal + 4) = v26;
            pvarg.iVal = 19;
            Instance = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, ULONG *))v50->lpVtbl->SetValue)(
                         v50,
                         &PKEY_WNET_DisplayType,
                         &pvarg.decVal.Lo32);
            if ( Instance >= 0 )
            {
              ((void (__fastcall *)(struct IPropertyStore *))v50->lpVtbl->AddRef)(v50);
              v33 = v50;
              ((void (__fastcall *)(struct IPropertyStore *))v50->lpVtbl->Release)(v50);
              v34 = *((_QWORD *)this + 8);
              Src = 0;
              v35 = 0;
              LODWORD(Size) = 0;
              v36 = 0;
              if ( v33 )
              {
                v37 = v33->lpVtbl;
                pidl = 0;
                Instance = ((__int64 (__fastcall *)(struct IPropertyStore *, GUID *, LPCITEMIDLIST *))v37->QueryInterface)(
                             v33,
                             &GUID_e318ad57_0aa0_450f_aca5_6fab7103d917,
                             &pidl);
                if ( Instance < 0
                  || (Instance = (*(__int64 (__fastcall **)(LPCITEMIDLIST, void **, size_t *))(*(_QWORD *)&pidl->mkid.cb
                                                                                             + 40LL))(
                                   pidl,
                                   &Src,
                                   &Size),
                      (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)&pidl->mkid.cb + 16LL))(pidl),
                      Instance < 0) )
                {
LABEL_69:
                  ((void (__fastcall *)(struct IPropertyStore *))v33->lpVtbl->Release)(v33);
                  if ( Instance >= 0 )
                  {
                    v43 = *(_QWORD *)&pvarg.vt;
                    if ( *(_QWORD *)&pvarg.vt )
                    {
                      v44 = *(_QWORD *)this;
                      v45 = v63;
                      *(_QWORD *)&pvarg.vt = 0;
                      if ( (*(int (__fastcall **)(CNetworkExplorerFolder *, ITEMIDLIST *, struct IBindCtx *, GUID *, VARIANTARG *))(v44 + 40))(
                             this,
                             v36,
                             v63,
                             &GUID_000214e6_0000_0000_c000_000000000046,
                             &pvarg) < 0 )
                      {
                        Instance = -2147024843;
                      }
                      else
                      {
                        LODWORD(v50) = 0;
                        pidl = 0;
                        Instance = (*(__int64 (__fastcall **)(_QWORD, HWND, struct IBindCtx *, __int64, struct IPropertyStore **, LPCITEMIDLIST *, unsigned int *))(**(_QWORD **)&pvarg.vt + 24LL))(
                                     *(_QWORD *)&pvarg.vt,
                                     v62,
                                     v45,
                                     v43,
                                     &v50,
                                     &pidl,
                                     v53);
                        if ( Instance >= 0 )
                        {
                          v46 = ILCombine(v36, pidl);
                          v47 = (ITEMIDLIST *)pidl;
                          v48 = v46;
                          *(_QWORD *)v56 = v46;
                          ILFree(v47);
                          Instance = 0;
                          if ( !v48 )
                            Instance = -2147024882;
                        }
                        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&pvarg.vt + 16LL))(*(_QWORD *)&pvarg.vt);
                      }
                      ILFree(v36);
                    }
                    else
                    {
                      v49 = v53;
                      *(_QWORD *)v56 = v36;
                      if ( v49 && *v49 )
                        CNetworkExplorerFolder::_GetAttributesOf(v42, (const struct _ITEMID_CHILD *)v36, v49);
                    }
                  }
                  goto LABEL_77;
                }
                v35 = Size;
              }
              v38 = (unsigned int)(v35 + 12) + 2LL;
              if ( v34 )
              {
                v41 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v34 + 24LL))(
                        v34,
                        (unsigned int)(v35 + 12) + 2LL);
              }
              else
              {
                v39 = v35 + 22;
                if ( (unsigned __int64)(unsigned int)(v35 + 12) + 10 > 0x10001 )
                  goto LABEL_93;
                v40 = CoTaskMemAlloc((unsigned int)(v35 + 12) + 10LL);
                v41 = (__int64)v40;
                if ( v40 )
                {
                  memset_0(v40, 0, v38 + 8);
                  *(_WORD *)(v41 + 4) = v38;
                  *(_WORD *)v41 = v39 - 2;
LABEL_65:
                  *(_DWORD *)(v41 + 6) = 999534523;
                  *(_WORD *)(v41 + 10) = Size;
                  *(_WORD *)(v41 + 12) = 4;
                  if ( Src )
                    memcpy_0((void *)(v41 + 18), Src, (unsigned int)Size);
                  v36 = (ITEMIDLIST *)v41;
                  Instance = 0;
                  goto LABEL_68;
                }
              }
              if ( v41 )
                goto LABEL_65;
LABEL_93:
              Instance = -2147024882;
LABEL_68:
              CoTaskMemFree(Src);
              goto LABEL_69;
            }
          }
        }
      }
      ((void (__fastcall *)(struct IPropertyStore *))v50->lpVtbl->Release)(v50);
    }
LABEL_77:
    CoTaskMemFree((LPVOID)lpString2);
    goto LABEL_78;
  }
  return result;
}

```

## disassembly

```asm
0x180001c80  mov     r11, rsp
0x180001c83  push    rbp
0x180001c84  push    rsi
0x180001c85  push    r12
0x180001c87  push    r13
0x180001c89  push    r14
0x180001c8b  push    r15
0x180001c8d  lea     rbp, [r11-48h]
0x180001c91  sub     rsp, 118h
0x180001c98  mov     rax, cs:__security_cookie
0x180001c9f  xor     rax, rsp
0x180001ca2  mov     [rbp+40h+var_50], rax
0x180001ca6  mov     r15, [rbp+40h+arg_28]
0x180001caa  mov     rsi, r9
0x180001cad  mov     r12, [rbp+40h+arg_30]
0x180001cb4  mov     r14, r8
0x180001cb7  mov     [rbp+40h+var_88], r8
0x180001cbb  mov     r13, rcx
0x180001cbe  mov     [rbp+40h+var_90], rdx
0x180001cc2  mov     [rbp+40h+var_C0], r15
0x180001cc6  mov     [rsp+140h+var_E8], r12
0x180001ccb  test    r15, r15
0x180001cce  jz      loc_180002507
0x180001cd4  xor     eax, eax
0x180001cd6  test    r9, r9
0x180001cd9  jz      loc_18000242E
0x180001cdf  mov     [r11-38h], rbx
0x180001ce3  lea     rdx, [rbp+40h+ppszServer]; ppszServer
0x180001ce7  mov     rcx, r9; pszPath
0x180001cea  mov     [r11-40h], rdi
0x180001cee  mov     [rbp+40h+ppszServer], rax
0x180001cf2  call    cs:__imp_PathIsUNCEx
0x180001cf8  test    eax, eax
0x180001cfa  jz      short loc_180001D34
0x180001cfc  mov     rcx, [rbp+40h+ppszServer]
0x180001d00  mov     edx, 5Ch ; '\'
0x180001d05  mov     rdi, rcx
0x180001d08  movzx   eax, word ptr [rcx]
0x180001d0b  test    ax, ax
0x180001d0e  jz      short loc_180001D22
0x180001d10  cmp     dx, ax
0x180001d13  jz      short loc_180001D22
0x180001d15  movzx   eax, word ptr [rdi+2]
0x180001d19  add     rdi, 2
0x180001d1d  test    ax, ax
0x180001d20  jnz     short loc_180001D10
0x180001d22  mov     rax, rdi
0x180001d25  sub     rax, rcx
0x180001d28  test    rax, 0FFFFFFFFFFFFFFFEh
0x180001d2e  jg      loc_180001DD4
0x180001d34  lea     rcx, [r13-20h]; this
0x180001d38  mov     [rbp+40h+var_C0], 0
0x180001d40  lea     rdx, [rbp+40h+var_C0]; struct INetworkItemFactory **
0x180001d44  call    ?GetFactory@CNetworkExplorerFolder@@QEAAJPEAPEAUINetworkItemFactory@@@Z; CNetworkExplorerFolder::GetFactory(INetworkItemFactory * *)
0x180001d49  test    eax, eax
0x180001d4b  js      loc_18000241E
0x180001d51  mov     rbx, [rbp+40h+var_C0]
0x180001d55  lea     r8, [rsp+140h+var_E8]
0x180001d5a  mov     [rsp+140h+var_E8], 0
0x180001d63  mov     rdx, rsi
0x180001d66  mov     rcx, rbx
0x180001d69  mov     rax, [rbx]
0x180001d6c  mov     rax, [rax+48h]
0x180001d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d75  mov     edi, eax
0x180001d77  test    eax, eax
0x180001d79  js      short loc_180001DC0
0x180001d7b  mov     rax, [rbx]
0x180001d7e  mov     r8, r15
0x180001d81  mov     rdx, [rsp+140h+var_E8]
0x180001d86  mov     rcx, rbx
0x180001d89  mov     rax, [rax+68h]
0x180001d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d92  mov     edi, eax
0x180001d94  test    eax, eax
0x180001d96  js      short loc_180001DAF
0x180001d98  test    r12, r12
0x180001d9b  jz      short loc_180001DAF
0x180001d9d  cmp     dword ptr [r12], 0
0x180001da2  jz      short loc_180001DAF
0x180001da4  mov     rdx, [r15]; struct _ITEMID_CHILD *
0x180001da7  mov     r8, r12; unsigned int *
0x180001daa  call    ?_GetAttributesOf@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAK@Z; CNetworkExplorerFolder::_GetAttributesOf(_ITEMID_CHILD const *,ulong *)
0x180001daf  mov     rcx, [rsp+140h+var_E8]
0x180001db4  mov     rax, [rcx]
0x180001db7  mov     rax, [rax+10h]
0x180001dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dc0  mov     rax, [rbx]
0x180001dc3  mov     rcx, rbx
0x180001dc6  mov     rax, [rax+10h]
0x180001dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dcf  jmp     loc_18000241C
0x180001dd4  mov     rbx, rdi
0x180001dd7  sub     rbx, rsi
0x180001dda  sar     rbx, 1
0x180001ddd  lea     rcx, ds:2[rbx*2]; cb
0x180001de5  call    cs:__imp_CoTaskMemAlloc
0x180001deb  mov     r12, rax
0x180001dee  test    rax, rax
0x180001df1  jz      loc_18000245B
0x180001df7  xor     ecx, ecx
0x180001df9  lea     r8, [rbx+1]
0x180001dfd  xor     eax, eax
0x180001dff  mov     [r12], cx
0x180001e04  mov     qword ptr [rsp+140h+pvarg], rax
0x180001e09  lea     rcx, [r8-1]
0x180001e0d  cmp     rbx, 7FFFFFFEh
0x180001e14  ja      short loc_180001E56
0x180001e16  cmp     rcx, 7FFFFFFEh
0x180001e1d  ja      short loc_180001E56
0x180001e1f  mov     rcx, rsi
0x180001e22  mov     rdx, r12
0x180001e25  test    rbx, rbx
0x180001e28  jz      short loc_180001E46
0x180001e2a  movzx   eax, word ptr [rcx]
0x180001e2d  test    ax, ax
0x180001e30  jz      short loc_180001E46
0x180001e32  mov     [rdx], ax
0x180001e35  add     rcx, 2
0x180001e39  add     rdx, 2
0x180001e3d  dec     rbx
0x180001e40  sub     r8, 1
0x180001e44  jnz     short loc_180001E25
0x180001e46  test    r8, r8
0x180001e49  lea     rcx, [rdx-2]
0x180001e4d  cmovnz  rcx, rdx
0x180001e51  xor     eax, eax
0x180001e53  mov     [rcx], ax
0x180001e56  movzx   ecx, word ptr [rdi]
0x180001e59  lea     rax, [rdi+2]
0x180001e5d  mov     r8d, 5Ch ; '\'
0x180001e63  cmp     r8w, cx
0x180001e67  jnz     loc_180002453
0x180001e6d  movzx   edx, word ptr [rax]
0x180001e70  cmovnz  rax, rdi
0x180001e74  test    dx, dx
0x180001e77  jz      short loc_180001E7E
0x180001e79  mov     qword ptr [rsp+140h+pvarg], rax
0x180001e7e  lea     rdx, [rbp+40h+ppwsz]; ppwsz
0x180001e82  mov     [rbp+40h+ppwsz], 0
0x180001e8a  mov     rcx, rsi; psz
0x180001e8d  call    cs:__imp_SHStrDupW
0x180001e93  mov     edi, eax
0x180001e95  test    eax, eax
0x180001e97  js      loc_180002413
0x180001e9d  mov     rcx, [rbp+40h+ppwsz]; pszPath
0x180001ea1  call    cs:__imp_PathStripToRootW
0x180001ea7  mov     rbx, [rbp+40h+ppwsz]
0x180001eab  lea     rax, [rsp+140h+Size]
0x180001eb0  xor     esi, esi
0x180001eb2  mov     [rsp+140h+ppv], rax; ppv
0x180001eb7  lea     r9, _GUID_000214ea_0000_0000_c000_000000000046; riid
0x180001ebe  mov     [rbp+40h+lpString2], rsi
0x180001ec2  xor     r8d, r8d; pUnkOuter
0x180001ec5  mov     [rsp+140h+Size], rsi
0x180001eca  lea     rdx, CLSID_NetworkPlaces; pclsid
0x180001ed1  xor     ecx, ecx; pszCLSID
0x180001ed3  call    cs:__imp_SHCoCreateInstance
0x180001ed9  mov     edi, eax
0x180001edb  test    eax, eax
0x180001edd  js      loc_180002409
0x180001ee3  mov     rcx, [rsp+140h+Size]
0x180001ee8  mov     r15d, esi
0x180001eeb  mov     rdx, [r13+48h]
0x180001eef  mov     rax, [rcx]
0x180001ef2  mov     rax, [rax+20h]
0x180001ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001efb  mov     edi, eax
0x180001efd  test    eax, eax
0x180001eff  js      loc_180002063
0x180001f05  mov     rcx, [rsp+140h+Size]
0x180001f0a  lea     r8, [rsp+140h+var_100]
0x180001f0f  mov     [rsp+140h+var_100], rsi
0x180001f14  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x180001f1b  mov     rax, [rcx]
0x180001f1e  mov     rax, [rax]
0x180001f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f26  mov     edi, eax
0x180001f28  test    eax, eax
0x180001f2a  js      loc_180002063
0x180001f30  mov     rcx, [rsp+140h+var_100]
0x180001f35  lea     rdx, [rsp+140h+pidl]
0x180001f3a  mov     [rsp+140h+pidl], rsi
0x180001f3f  mov     r9, rbx
0x180001f42  mov     [rsp+30h], rsi
0x180001f47  mov     r8, r14
0x180001f4a  mov     qword ptr [rsp+140h+cchCount2], rdx
0x180001f4f  mov     rax, [rcx]
0x180001f52  mov     rdx, [rbp+40h+var_90]
0x180001f56  mov     [rsp+140h+ppv], rsi
0x180001f5b  mov     rax, [rax+18h]
0x180001f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f64  mov     edi, eax
0x180001f66  test    eax, eax
0x180001f68  js      loc_180002052
0x180001f6e  mov     rcx, [rsp+140h+pidl]; pidl
0x180001f73  call    cs:__imp_ILCloneFirst
0x180001f79  mov     rbx, rax
0x180001f7c  test    rax, rax
0x180001f7f  jz      loc_180002047
0x180001f85  movups  xmm0, xmmword ptr cs:PKEY_NetworkProvider.fmtid.Data1
0x180001f8c  mov     ecx, cs:PKEY_NetworkProvider.pid
0x180001f92  lea     r9, [rbp+40h+psz]
0x180001f96  xor     eax, eax
0x180001f98  mov     [rbp+40h+var_58], ecx
0x180001f9b  mov     rcx, [rsp+140h+var_100]
0x180001fa0  lea     r8, [rbp+40h+var_68]
0x180001fa4  movups  [rbp+40h+var_68], xmm0
0x180001fa8  mov     [rbp+40h+var_70], rax
0x180001fac  mov     rdx, rbx
0x180001faf  xorps   xmm0, xmm0
0x180001fb2  movups  xmmword ptr [rbp+40h+psz], xmm0
0x180001fb6  mov     rax, [rcx]
0x180001fb9  mov     rax, [rax+88h]
0x180001fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fc5  test    eax, eax
0x180001fc7  jns     loc_180002483
0x180001fcd  movups  xmm1, cs:PKEY_NetworkResource
0x180001fd4  mov     rcx, [rsp+140h+var_100]
0x180001fd9  lea     r9, [rsp+140h+pvarg+8]
0x180001fde  xor     eax, eax
0x180001fe0  lea     r8, [rbp+40h+var_68]
0x180001fe4  mov     [rsp+140h+var_C8], rax
0x180001fe9  xorps   xmm0, xmm0
0x180001fec  mov     eax, cs:dword_180013AB8
0x180001ff2  mov     rdx, rbx
0x180001ff5  mov     [rbp+40h+var_58], eax
0x180001ff8  movups  [rbp+40h+var_68], xmm1
0x180001ffc  movups  xmmword ptr [rsp+140h+pvarg+8], xmm0
0x180002001  mov     rax, [rcx]
0x180002004  mov     rax, [rax+88h]
0x18000200b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002010  test    eax, eax
0x180002012  js      short loc_18000203E
0x180002014  mov     eax, 2011h
0x180002019  cmp     ax, word ptr [rsp+140h+pvarg+8]
0x18000201e  jnz     short loc_180002033
0x180002020  mov     rax, qword ptr [rsp+140h+pvarg+10h]
0x180002025  mov     rcx, [rax+10h]
0x180002029  cmp     dword ptr [rcx+8], 0Ah
0x18000202d  jz      loc_180002511
0x180002033  lea     rcx, [rsp+140h+pvarg+8]; pvarg
0x180002038  call    cs:__imp_VariantClear
0x18000203e  mov     rcx, rbx; pidl
0x180002041  call    cs:__imp_ILFree
0x180002047  mov     rcx, [rsp+140h+pidl]; pidl
0x18000204c  call    cs:__imp_ILFree
0x180002052  mov     rcx, [rsp+140h+var_100]
0x180002057  mov     rax, [rcx]
0x18000205a  mov     rax, [rax+10h]
0x18000205e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002063  mov     rcx, [rsp+140h+Size]
0x180002068  mov     rax, [rcx]
0x18000206b  mov     rax, [rax+10h]
0x18000206f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002074  test    edi, edi
0x180002076  js      loc_180002409
0x18000207c  mov     r14, [rbp+40h+lpString2]
0x180002080  lea     rbx, [r12+4]
0x180002085  mov     rcx, rbx; pszPath
0x180002088  mov     [rbp+40h+var_98], rsi
0x18000208c  lea     rdx, [rbp+40h+var_98]; ppszServer
0x180002090  call    cs:__imp_PathIsUNCEx
0x180002096  lea     rdx, [rsp+140h+var_100]; ppv
0x18000209b  mov     [rsp+140h+var_100], rsi
0x1800020a0  test    eax, eax
0x1800020a2  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x1800020a9  cmovnz  rbx, [rbp+40h+var_98]
0x1800020ae  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800020b4  mov     edi, eax
0x1800020b6  test    eax, eax
0x1800020b8  js      loc_1800023FF
0x1800020be  mov     rcx, [rsp+140h+var_100]
0x1800020c3  lea     r8, [rsp+140h+pvarg+8]
0x1800020c8  xor     eax, eax
0x1800020ca  lea     rdx, PKEY_ItemNameDisplay
0x1800020d1  mov     [rsp+140h+var_C8], rax
0x1800020d6  xorps   xmm0, xmm0
0x1800020d9  movups  xmmword ptr [rsp+140h+pvarg+8], xmm0
0x1800020de  mov     eax, 1Fh
0x1800020e3  mov     qword ptr [rsp+140h+pvarg+10h], rbx
0x1800020e8  mov     word ptr [rsp+140h+pvarg+8], ax
0x1800020ed  mov     rax, [rcx]
0x1800020f0  mov     rax, [rax+30h]
0x1800020f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020f9  mov     edi, eax
0x1800020fb  test    eax, eax
0x1800020fd  js      loc_180002465
0x180002103  mov     rcx, [rsp+140h+var_100]
0x180002108  lea     r8, [rsp+140h+pvarg+8]
0x18000210d  xor     eax, eax
0x18000210f  lea     rdx, rpkey
0x180002116  mov     [rsp+140h+var_C8], rax
0x18000211b  xorps   xmm0, xmm0
0x18000211e  movups  xmmword ptr [rsp+140h+pvarg+8], xmm0
0x180002123  mov     eax, 0Bh
0x180002128  mov     ebx, 0FFFFFFFFh
0x18000212d  mov     word ptr [rsp+140h+pvarg+8], ax
0x180002132  mov     rax, [rcx]
0x180002135  mov     word ptr [rsp+140h+pvarg+10h], bx
  ... truncated ...
```
