# CDesktopFolder::ParseDisplayName(HWND__ *,IBindCtx *,ushort *,ulong *,_ITEMIDLIST_RELATIVE * *,ulong *)

- ea: `0x18004caf0`
- end: `0x18004d8c1`
- name: `?ParseDisplayName@CDesktopFolder@@UEAAJPEAUHWND__@@PEAUIBindCtx@@PEAGPEAKPEAPEAU_ITEMIDLIST_RELATIVE@@3@Z`
- size: `3537`
- prototype: `int(CDesktopFolder *__hidden this, HWND, struct IBindCtx *, unsigned __int16 *, unsigned int *, struct _ITEMIDLIST_RELATIVE **, unsigned int *)`
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callees

- `0x180041b00`
- `0x18004bb30`
- `0x18004bdf0`
- `0x18004bee0`
- `0x18004caf0`
- `0x18004de7c`
- `0x18004e6b0`
- `0x180051fd0`
- `0x180054860`
- `0x1800551a0`
- `0x180093c20`
- `0x1800d3d10`
- `0x1800d5920`
- `0x1800d60a0`
- `0x1800d6b80`
- `0x18012c990`
- `0x18012fa50`
- `0x18016cd40`
- `0x1801b7428`
- `0x1802347ec`
- `0x1802ac0a0`
- `0x1803a4cb0`
- `0x1803a4cd4`
- `0x1803a518c`
- `0x1803a57e0`
- `0x1803a5bc5`
- `0x1803a96e5`
- `0x18050bda4`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!ParseURLW` at `0x18004d21e`
- `api-ms-win-core-url-l1-1-0!ParseURLW` at `0x18004d21e`
- `api-ms-win-core-url-l1-1-0!UrlIsW` at `0x18004cc6f`
- `api-ms-win-core-url-l1-1-0!UrlIsW` at `0x18004cc6f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18004cc5c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18004cc5c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18004cc41`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18004cc41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ce9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d061`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d073`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d523`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d82a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18063fccb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18063fcd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ce9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d061`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d073`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d523`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d82a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18063fccb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18063fcd6`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18004cc1b`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18004cc1b`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18004cd19`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18004cd19`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!IUnknown_GetWindow` at `0x18004d1dc`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!IUnknown_GetWindow` at `0x18004d1dc`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x18004cd51`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x18004cd51`

## string_xrefs

- `0x18004cc0f`: `SHBindCtxPathType`
- `0x18004d2e9`: `ParseAsCommonItem`
- `0x18004ce0c`: `UI During Binding`
- `0x18004d699`: `ParseAsDurableContentUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CDesktopFolder::ParseDisplayName(
        CDesktopFolder *this,
        HWND a2,
        struct IBindCtx *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        struct _ITEMIDLIST_RELATIVE **a6,
        unsigned int *a7)
{
  const wchar_t *v7; // r12
  struct IBindCtx *v8; // r15
  unsigned int *v10; // rbx
  struct _ITEMIDLIST_ABSOLUTE **v11; // rsi
  unsigned int v12; // r13d
  HRESULT v13; // edi
  HRESULT DWORD; // ebx
  int v15; // ebx
  char v16; // bl
  LPBC v17; // rbx
  LPBC v18; // rdi
  CDummyUnknown *v19; // rax
  CDummyUnknown *v20; // rax
  CDummyUnknown *v21; // rsi
  IShellFolder *v22; // rdi
  HRESULT (__stdcall *ParseDisplayName)(IShellFolder *, HWND, IBindCtx *, LPWSTR, ULONG *, LPITEMIDLIST *, ULONG *); // r14
  LPWSTR v24; // rsi
  const ITEMIDLIST *v25; // r14
  int v26; // eax
  char *v27; // rcx
  LPBC v28; // r15
  const ITEMIDLIST *v29; // rdx
  int v30; // r8d
  __int64 cb; // rcx
  __int64 v32; // rdi
  LPBC v33; // rdx
  __int64 lpVtbl_low; // rcx
  ITEMIDLIST *v35; // rax
  LPITEMIDLIST v36; // rsi
  struct _ITEMIDLIST_ABSOLUTE **v37; // r14
  const struct _GUID *v38; // rcx
  int v39; // esi
  __int64 v40; // rax
  int v41; // ecx
  const wchar_t *v42; // rax
  int v43; // ebx
  __int64 **v44; // rbx
  struct _ITEMIDLIST_ABSOLUTE **v45; // r14
  unsigned int *v46; // r13
  int *v47; // rsi
  int v48; // r13d
  int v50; // eax
  int v51; // edx
  struct _ITEMIDLIST_ABSOLUTE *v52; // rcx
  __int64 v53; // rax
  int v54; // eax
  __int64 v55; // rcx
  __int64 *v56; // rcx
  __int64 v57; // rax
  unsigned int *v58; // [rsp+28h] [rbp-D8h]
  LPBC ppbc; // [rsp+48h] [rbp-B8h] BYREF
  char *v60; // [rsp+50h] [rbp-B0h] BYREF
  void *Src; // [rsp+58h] [rbp-A8h] BYREF
  DWORD value[2]; // [rsp+60h] [rbp-A0h] BYREF
  IPropertyBag *propBag; // [rsp+68h] [rbp-98h] BYREF
  LPWSTR ppwsz; // [rsp+70h] [rbp-90h] BYREF
  IShellFolder *ppshf; // [rsp+78h] [rbp-88h] BYREF
  CDesktopFolder *v66; // [rsp+80h] [rbp-80h]
  PARSEDURLW ppu; // [rsp+88h] [rbp-78h] BYREF
  struct _ITEMIDLIST_ABSOLUTE **v68; // [rsp+B0h] [rbp-50h] BYREF
  HWND v69; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int *v70; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v71[12]; // [rsp+C8h] [rbp-38h] BYREF
  int v72; // [rsp+D4h] [rbp-2Ch]
  HWND phwnd[3]; // [rsp+D8h] [rbp-28h] BYREF
  int v74; // [rsp+F0h] [rbp-10h]
  int v75; // [rsp+F4h] [rbp-Ch]
  char v76[16]; // [rsp+100h] [rbp+0h] BYREF
  const wchar_t *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  DWORD *v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  _BYTE *v82; // [rsp+130h] [rbp+30h]
  __int64 v83; // [rsp+138h] [rbp+38h]
  HWND *v84; // [rsp+140h] [rbp+40h]
  __int64 v85; // [rsp+148h] [rbp+48h]
  HWND *v86; // [rsp+150h] [rbp+50h]
  __int64 v87; // [rsp+158h] [rbp+58h]
  unsigned int **v88; // [rsp+160h] [rbp+60h]
  __int64 v89; // [rsp+168h] [rbp+68h]
  struct _ITEMIDLIST_ABSOLUTE ***v90; // [rsp+170h] [rbp+70h]
  __int64 v91; // [rsp+178h] [rbp+78h]

  v7 = a4;
  v8 = a3;
  *(_QWORD *)v71 = a3;
  v69 = a2;
  v66 = this;
  v10 = a5;
  v11 = a6;
  v68 = a6;
  v70 = a7;
  v12 = 2;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
  {
    if ( a4 )
    {
      v40 = -1;
      do
        ++v40;
      while ( a4[v40] );
      v41 = 2 * v40 + 2;
    }
    else
    {
      v41 = 10;
    }
    v42 = a4;
    if ( !a4 )
      v42 = L"NULL";
    phwnd[2] = (HWND)v42;
    v74 = v41;
    v75 = 0;
    McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_Shell_Core_Provider_Context, "-L", L"NULL", 2, phwnd);
  }
  v13 = -2147024809;
  if ( !a6 )
    goto LABEL_172;
  *a6 = 0;
  if ( !v7 )
    goto LABEL_172;
  if ( !*v7 )
  {
    v13 = SHILClone((const struct _ITEMIDLIST_RELATIVE *)c_idlDrives, a6);
LABEL_172:
    v45 = a6;
    goto LABEL_107;
  }
  v60 = 0;
  Src = 0;
  value[0] = 0;
  propBag = 0;
  DWORD = -2147467262;
  ppbc = 0;
  if ( v8
    && ((int (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, LPBC *))v8->lpVtbl->GetObjectParam)(
         v8,
         L"SHBindCtxPropertyBag",
         &ppbc) >= 0 )
  {
    v15 = ((__int64 (__fastcall *)(LPBC, GUID *, IPropertyBag **))ppbc->lpVtbl->QueryInterface)(
            ppbc,
            &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
            &propBag);
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
    if ( v15 < 0 )
    {
LABEL_10:
      v16 = 0;
      goto LABEL_11;
    }
    DWORD = PSPropertyBag_ReadDWORD(propBag, L"SHBindCtxPathType", value);
    ((void (__fastcall *)(IPropertyBag *))propBag->lpVtbl->Release)(propBag);
  }
  if ( DWORD < 0 || (value[0] & 0x10) == 0 )
    goto LABEL_10;
  v16 = 1;
LABEL_11:
  if ( PathGetDriveNumberW(v7) == -1 )
    goto LABEL_14;
  if ( v16 )
  {
    if ( v7[1] != 58 )
      SHSetPathTypeBindCtx(v8, 0x12u);
    goto LABEL_23;
  }
  if ( v7[1] == 58 )
  {
LABEL_23:
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloBrokerShellObjects>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_AppSiloBrokerShellObjects>::GetImpl'::`2'::impl);
    if ( (int)Windows::Security::Isolation::TryBrokerSHParseDisplayName(
                (Windows::Security::Isolation *)L"::{20D04FE0-3AEA-1069-A2D8-08002B30309D}",
                0,
                (struct IBindCtx *)&Src,
                0,
                0,
                v58) >= 0 )
    {
      v13 = 0;
    }
    else
    {
      Src = 0;
      ppwsz = 0;
      v13 = SHStrDupW(L"::{20D04FE0-3AEA-1069-A2D8-08002B30309D}", &ppwsz);
      if ( v13 >= 0 )
      {
        ppshf = 0;
        v13 = SHGetDesktopFolder(&ppshf);
        if ( v13 >= 0 )
        {
          v17 = 0;
          ppbc = 0;
          v13 = CreateBindCtx(0, &ppbc);
          if ( v13 >= 0 )
          {
            v18 = ppbc;
            v19 = (CDummyUnknown *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
            phwnd[0] = (HWND)v19;
            if ( v19 && (v20 = CDummyUnknown::CDummyUnknown(v19), (v21 = v20) != 0) )
            {
              v13 = ((__int64 (__fastcall *)(LPBC, const wchar_t *, CDummyUnknown *))v18->lpVtbl->RegisterObjectParam)(
                      v18,
                      L"Parse Translate Aliases",
                      v20);
              if ( (int)--*((_DWORD *)v21 + 6) <= 0 )
                operator delete(v21, (const struct std::nothrow_t *)0x40);
              if ( v13 >= 0 )
              {
                v17 = ppbc;
                ((void (__fastcall *)(LPBC))ppbc->lpVtbl->AddRef)(ppbc);
              }
            }
            else
            {
              v13 = -2147024882;
            }
            ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
          }
          if ( v13 >= 0 )
          {
            v22 = ppshf;
            ParseDisplayName = ppshf->lpVtbl->ParseDisplayName;
            v24 = ppwsz;
            phwnd[0] = 0;
            propBag = 0;
            *(_OWORD *)&ppu.cbSize = *(_OWORD *)L"UI During Binding";
            *(_OWORD *)&ppu.cchProtocol = *(_OWORD *)L"g Binding";
            ppu.cchSuffix = *(_DWORD *)L"g";
            if ( v17
              && ((int (__fastcall *)(LPBC, PARSEDURLW *, IPropertyBag **))v17->lpVtbl->GetObjectParam)(
                   v17,
                   &ppu,
                   &propBag) >= 0 )
            {
              IUnknown_GetWindow((IUnknown *)propBag, phwnd);
              ((void (__fastcall *)(IPropertyBag *))propBag->lpVtbl->Release)(propBag);
            }
            v13 = ((__int64 (__fastcall *)(IShellFolder *, HWND, LPBC, LPWSTR, _QWORD, void **, _QWORD))ParseDisplayName)(
                    v22,
                    phwnd[0],
                    v17,
                    v24,
                    0,
                    &Src,
                    0);
          }
          if ( v17 )
            ((void (__fastcall *)(LPBC))v17->lpVtbl->Release)(v17);
          v11 = v68;
        }
        CoTaskMemFree(ppwsz);
        if ( ppshf )
          ((void (__fastcall *)(IShellFolder *))ppshf->lpVtbl->Release)(ppshf);
      }
    }
    goto LABEL_44;
  }
LABEL_14:
  if ( PathIsUNCW(v7) )
  {
    if ( v16 )
    {
      if ( v7[2] == 63 )
        SHSetPathTypeBindCtx(v8, 0x11u);
    }
    else if ( v7[2] == 63 )
    {
      goto LABEL_15;
    }
    if ( (unsigned int)BindCtx_ContainsObject(v8, L"OLD NETWORK PARSE") )
    {
      v13 = SHParseDisplayName(L"::{208D2C60-3AEA-1069-A2D7-08002B30309D}", 0, (LPITEMIDLIST *)&Src, 0, 0);
    }
    else
    {
      v13 = SHGetKnownFolderIDList_Internal(
              (struct _GUID *)&FOLDERID_NetworkFolder,
              0,
              0,
              (struct _ITEMIDLIST_ABSOLUTE **)&Src);
      if ( v13 == 1 )
      {
        v13 = -2147024809;
        goto LABEL_74;
      }
    }
    goto LABEL_44;
  }
LABEL_15:
  if ( !UrlIsW(v7, URLIS_URL)
    || v8
    && (phwnd[0] = (HWND)16,
        phwnd[1] = 0,
        ((int (__fastcall *)(struct IBindCtx *, HWND *))v8->lpVtbl->GetBindOptions)(v8, phwnd) >= 0)
    && HIDWORD(phwnd[0]) == 2 )
  {
    if ( !v16 )
      goto LABEL_74;
    phwnd[0] = 0;
    if ( (int)CMountPoint::GetSimulatedMountPointFromVolumeGuid(v7, (struct CMountPoint **)phwnd) < 0 )
      goto LABEL_74;
    SHSetPathTypeBindCtx(v8, 0x16u);
    v13 = SHParseDisplayName(L"::{20D04FE0-3AEA-1069-A2D8-08002B30309D}", 0, (LPITEMIDLIST *)&Src, 0, 0);
    CMountPoint::Release((CMountPoint *)phwnd[0]);
  }
  else
  {
    v60 = 0;
    Src = 0;
    *(_QWORD *)&ppu.cbSize = 40;
    memset(&ppu.pszProtocol, 0, 32);
    v13 = ParseURLW(v7, &ppu);
    if ( v13 >= 0 )
    {
      if ( ppu.nScheme == 12 )
      {
        v60 = (char *)this + 200;
      }
      else
      {
        switch ( ppu.nScheme )
        {
          case 2u:
          case 0xBu:
            if ( (unsigned int)BindCtx_ContainsObject(v8, L"Parse Prefer Folder Browsing")
              || (unsigned int)BindCtx_ContainsObject(v8, L"ParseAsDurableContentUri") )
            {
              v60 = (char *)this + 232;
            }
            else
            {
              v13 = -2147024809;
            }
            break;
          case 9u:
            v60 = (char *)this + 224;
            break;
          case 0x13u:
            v60 = (char *)this + 184;
            break;
          case 0x14u:
            goto LABEL_167;
          case 0x18u:
          case 0x19u:
            if ( (unsigned int)BindCtx_ContainsObject(v8, L"Parse Prefer Folder Browsing")
              && (ppu.nScheme == 24 || (unsigned int)IsExplorerDefaultSearchProvider()) )
            {
              v60 = (char *)this + 216;
            }
            else
            {
LABEL_167:
              v13 = -2147024809;
            }
            break;
          case 0x1Au:
            v60 = (char *)this + 208;
            break;
          default:
            v13 = _TryRegisteredUrlJunction(ppu.pszProtocol, ppu.cchProtocol, (struct _ITEMIDLIST_ABSOLUTE **)&Src);
            break;
        }
      }
    }
  }
LABEL_44:
  if ( v13 >= 0 )
  {
    v25 = (const ITEMIDLIST *)Src;
    if ( Src && !v60 )
    {
      v60 = 0;
      ppbc = 0;
      v13 = CDesktopFolder_CreateInstance(0, &GUID_000214e6_0000_0000_c000_000000000046, &ppbc);
      if ( v13 >= 0 )
      {
        if ( v25 && v25->mkid.cb )
          v26 = ((__int64 (__fastcall *)(LPBC, const ITEMIDLIST *, _QWORD, GUID *, char **))ppbc->lpVtbl->ReleaseBoundObjects)(
                  ppbc,
                  v25,
                  0,
                  &GUID_000214e6_0000_0000_c000_000000000046,
                  &v60);
        else
          v26 = ((__int64 (__fastcall *)(LPBC, GUID *, char **))ppbc->lpVtbl->QueryInterface)(
                  ppbc,
                  &GUID_000214e6_0000_0000_c000_000000000046,
                  &v60);
        v13 = v26;
        if ( v26 >= 0 && !v60 )
          v13 = -2147467259;
        ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
      }
      if ( v13 < 0 )
      {
        CoTaskMemFree(Src);
        Src = 0;
        goto LABEL_74;
      }
      v25 = (const ITEMIDLIST *)Src;
    }
    if ( a5 )
      *a5 = 0;
    v27 = v60;
    *v11 = 0;
    ppbc = 0;
    v13 = (*(__int64 (__fastcall **)(char *, HWND, struct IBindCtx *, const wchar_t *, unsigned int *, LPBC *, unsigned int *))(*(_QWORD *)v27 + 24LL))(
            v27,
            v69,
            v8,
            v7,
            a5,
            &ppbc,
            v70);
    if ( v13 >= 0 )
    {
      if ( v25 )
      {
        v28 = ppbc;
        if ( ppbc )
        {
          v29 = v25;
          v30 = 2;
          do
          {
            cb = v29->mkid.cb;
            if ( !(_WORD)cb )
              break;
            v30 += cb;
            v29 = (const ITEMIDLIST *)((char *)v29 + cb);
          }
          while ( v29 );
          v32 = (unsigned int)(v30 - 2);
          v33 = ppbc;
          do
          {
            lpVtbl_low = LOWORD(v33->lpVtbl);
            if ( !(_WORD)lpVtbl_low )
              break;
            v12 += lpVtbl_low;
            v33 = (LPBC)((char *)v33 + lpVtbl_low);
          }
          while ( v33 );
          v35 = (ITEMIDLIST *)WINRT_IMPL_CoTaskMemAlloc((unsigned int)v32 + v12);
          v36 = v35;
          if ( v35 )
          {
            memset_0(v35, 0, (unsigned int)v32 + v12);
            memcpy_0(v36, v25, (unsigned int)v32);
            memcpy_0((char *)v36 + v32, v28, v12);
          }
        }
        else
        {
          v36 = ILClone(v25);
        }
        v37 = v68;
        *v68 = (struct _ITEMIDLIST_ABSOLUTE *)v36;
        v13 = 0;
        if ( !v36 )
          v13 = -2147024882;
        CoTaskMemFree(ppbc);
        v8 = *(struct IBindCtx **)v71;
        v11 = v37;
      }
      else
      {
        *v11 = (struct _ITEMIDLIST_ABSOLUTE *)ppbc;
      }
    }
    CoTaskMemFree(Src);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v60 + 16LL))(v60);
  }
LABEL_74:
  if ( v13 >= 0 )
  {
    phwnd[0] = 0;
    if ( v8
      && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, HWND *))v8->lpVtbl->GetObjectParam)(
           v8,
           L"Parse Translate Aliases",
           phwnd) >= 0 )
    {
      (*(void (__fastcall **)(HWND))(*(_QWORD *)phwnd[0] + 16LL))(phwnd[0]);
      phwnd[0] = 0;
      if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, HWND *))v8->lpVtbl->GetObjectParam)(
             v8,
             L"Avoid Translate Desktop Alias",
             phwnd) >= 0 )
        (*(void (__fastcall **)(HWND))(*(_QWORD *)phwnd[0] + 16LL))(phwnd[0]);
      v66 = 0;
      if ( (int)SHILAliasTranslate(*v11) >= 0 )
      {
        CoTaskMemFree(*v11);
        *v11 = v66;
      }
    }
    goto LABEL_105;
  }
  if ( (unsigned int)FailForceReturn(v13) )
  {
LABEL_105:
    v45 = v68;
    goto LABEL_106;
  }
  phwnd[0] = 0;
  if ( v8
    && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, HWND *))v8->lpVtbl->GetObjectParam)(
         v8,
         L"Don't Parse Relative",
         phwnd) >= 0 )
  {
    (*(void (__fastcall **)(HWND))(*(_QWORD *)phwnd[0] + 16LL))(phwnd[0]);
    v13 = -2147024809;
    v45 = v68;
    v10 = a5;
    goto LABEL_107;
  }
  *(_DWORD *)v71 = 16;
  *(_QWORD *)&v71[4] = 0;
  v72 = 0;
  v39 = 0;
  if ( v8
    && ((int (__fastcall *)(struct IBindCtx *, _BYTE *))v8->lpVtbl->GetBindOptions)(v8, v71) >= 0
    && (*(_WORD *)&v71[8] & 0x1000) != 0 )
  {
    v39 = 1;
    *(_DWORD *)&v71[8] &= ~0x1000u;
    ((void (__fastcall *)(struct IBindCtx *, _BYTE *))v8->lpVtbl->SetBindOptions)(v8, v71);
    *(_QWORD *)value = 0;
    ppbc = 0;
  }
  else
  {
    *(_QWORD *)value = 0;
    ppbc = 0;
    if ( !v8 )
      goto LABEL_96;
  }
  if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, LPBC *))v8->lpVtbl->GetObjectParam)(
         v8,
         L"Root For Relative Parse",
         &ppbc) >= 0 )
  {
    v43 = ((__int64 (__fastcall *)(LPBC, GUID *, DWORD *))ppbc->lpVtbl->QueryInterface)(
            ppbc,
            &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
            value);
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
    if ( v43 >= 0 )
    {
      ppbc = 0;
      v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const GUID *, GUID *, LPBC *))(**(_QWORD **)value + 24LL))(
              *(_QWORD *)value,
              0,
              &BHID_SFObject,
              &GUID_000214e6_0000_0000_c000_000000000046,
              &ppbc);
      if ( v13 < 0 )
      {
        v45 = v68;
      }
      else
      {
        v13 = ((__int64 (__fastcall *)(struct IBindCtx *, const wchar_t *))v8->lpVtbl->RevokeObjectParam)(
                v8,
                L"Root For Relative Parse");
        if ( v13 < 0
          || (ppwsz = 0,
              v13 = ((__int64 (__fastcall *)(LPBC, HWND, struct IBindCtx *, const wchar_t *, unsigned int *, LPWSTR *, unsigned int *))ppbc->lpVtbl->RegisterObjectBound)(
                      ppbc,
                      v69,
                      v8,
                      v7,
                      a5,
                      &ppwsz,
                      v70),
              v13 < 0) )
        {
          v45 = v68;
        }
        else
        {
          ppshf = 0;
          v13 = SHGetIDListFromObject((IUnknown *)ppbc, (LPITEMIDLIST *)&ppshf);
          v45 = v68;
          if ( v13 >= 0 )
          {
            v13 = SHILCombine(
                    (const struct _ITEMIDLIST_ABSOLUTE *)ppshf,
                    (const struct _ITEMIDLIST_RELATIVE *)ppwsz,
                    v68);
            CoTaskMemFree(ppshf);
          }
          CoTaskMemFree(ppwsz);
        }
        ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
      }
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)value + 16LL))(*(_QWORD *)value);
      v44 = (__int64 **)((char *)v66 + 160);
LABEL_139:
      if ( v13 < 0 )
        goto LABEL_140;
LABEL_106:
      v10 = a5;
      goto LABEL_107;
    }
  }
LABEL_96:
  v44 = (__int64 **)((char *)v66 + 160);
  if ( !*((_QWORD *)v66 + 20) || (unsigned int)_ShouldParseFromKnownFolder(v38, v8) )
    goto LABEL_136;
  phwnd[0] = 0;
  if ( v8
    && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, HWND *))v8->lpVtbl->GetObjectParam)(
         v8,
         L"ParseAsCommonItem",
         phwnd) >= 0 )
  {
    (*(void (__fastcall **)(HWND))(*(_QWORD *)phwnd[0] + 16LL))(phwnd[0]);
LABEL_136:
    v45 = v68;
    v46 = a5;
    goto LABEL_137;
  }
  v45 = v68;
  v46 = a5;
  v13 = (*(__int64 (__fastcall **)(__int64 *, HWND, struct IBindCtx *, const wchar_t *, unsigned int *, struct _ITEMIDLIST_ABSOLUTE **, unsigned int *))(**v44 + 24))(
          *v44,
          v69,
          v8,
          v7,
          a5,
          v68,
          v70);
  if ( v13 >= 0 )
  {
    v10 = a5;
LABEL_107:
    v47 = (int *)v70;
    v48 = (int)v69;
    goto LABEL_108;
  }
LABEL_137:
  v55 = *((_QWORD *)v66 + 21);
  if ( v55 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, HWND, struct IBindCtx *, const wchar_t *, unsigned int *, struct _ITEMIDLIST_ABSOLUTE **, unsigned int *))(*(_QWORD *)v55 + 24LL))(
            v55,
            v69,
            v8,
            v7,
            v46,
            v45,
            v70);
    goto LABEL_139;
  }
LABEL_140:
  if ( !v39 || !*v44 )
    goto LABEL_106;
  *(_DWORD *)&v71[8] |= 0x1000u;
  ((void (__fastcall *)(struct IBindCtx *, _BYTE *))v8->lpVtbl->SetBindOptions)(v8, v71);
  v56 = *v44;
  v57 = **v44;
  v47 = (int *)v70;
  v10 = a5;
  v48 = (int)v69;
  v13 = (*(__int64 (__fastcall **)(__int64 *, HWND, struct IBindCtx *, const wchar_t *, unsigned int *, struct _ITEMIDLIST_ABSOLUTE **, unsigned int *))(v57 + 24))(
          v56,
          v69,
          v8,
          v7,
          a5,
          v45,
          v70);
LABEL_108:
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
  {
    v50 = -1;
    if ( v47 )
      v51 = *v47;
    else
      v51 = -1;
    if ( v10 )
      v50 = *v10;
    if ( v45 )
      v52 = *v45;
    else
      v52 = 0;
    *(_QWORD *)v71 = v52;
    LODWORD(v68) = v51;
    LODWORD(v70) = v50;
    phwnd[0] = (HWND)v8;
    LODWORD(v69) = v48;
    value[0] = v13;
    if ( v7 )
    {
      v53 = -1;
      do
        ++v53;
      while ( v7[v53] );
      v54 = 2 * v53 + 2;
    }
    else
    {
      v54 = 10;
    }
    if ( !v7 )
      v7 = L"NULL";
    v77 = v7;
    v78 = v54;
    v79 = 0;
    v80 = value;
    v81 = 4;
    v82 = v71;
    v83 = 8;
    v84 = &v69;
    v85 = 4;
    v86 = phwnd;
    v87 = 8;
    v88 = &v70;
    v89 = 4;
    v90 = &v68;
    v91 = 4;
    McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_Shell_Core_Provider_Context, ".L", 0, 8, v76);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18004caf0  push    rbp
0x18004caf2  push    rbx
0x18004caf3  push    rsi
0x18004caf4  push    rdi
0x18004caf5  push    r12
0x18004caf7  push    r13
0x18004caf9  push    r14
0x18004cafb  push    r15
0x18004cafd  lea     rbp, [rsp-98h]
0x18004cb05  sub     rsp, 198h
0x18004cb0c  mov     rax, cs:__security_cookie
0x18004cb13  xor     rax, rsp
0x18004cb16  mov     [rbp+0D0h+var_50], rax
0x18004cb1d  mov     r12, r9
0x18004cb20  mov     r15, r8
0x18004cb23  mov     [rbp+0D0h+var_108], r8
0x18004cb27  mov     [rbp+0D0h+var_118], rdx
0x18004cb2b  mov     r14, rcx
0x18004cb2e  mov     [rbp+0D0h+var_150], rcx
0x18004cb32  mov     rbx, [rbp+0D0h+arg_20]
0x18004cb39  mov     [rsp+1D0h+var_190], rbx
0x18004cb3e  mov     rsi, [rbp+0D0h+arg_28]
0x18004cb45  mov     [rbp+0D0h+var_120], rsi
0x18004cb49  mov     rax, [rbp+0D0h+arg_30]
0x18004cb50  mov     [rbp+0D0h+var_110], rax
0x18004cb54  lea     r8, aNull_0; "NULL"
0x18004cb5b  xor     edx, edx
0x18004cb5d  mov     r13d, 2
0x18004cb63  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18004cb6a  jnz     loc_18004D144
0x18004cb70  mov     edi, 80070057h
0x18004cb75  test    rsi, rsi
0x18004cb78  jz      loc_18004D870
0x18004cb7e  mov     [rsi], rdx
0x18004cb81  test    r12, r12
0x18004cb84  jz      loc_18004D870
0x18004cb8a  cmp     word ptr [r12], 0
0x18004cb90  jz      loc_18004D85F
0x18004cb96  mov     [rsp+1D0h+var_180], rdx
0x18004cb9b  mov     [rsp+1D0h+Src], rdx
0x18004cba0  mov     [rsp+1D0h+value], edx
0x18004cba4  mov     [rsp+1D0h+propBag], rdx
0x18004cba9  mov     ebx, 80004002h
0x18004cbae  mov     [rsp+1D0h+ppbc], rdx
0x18004cbb3  test    r15, r15
0x18004cbb6  jz      short loc_18004CC34
0x18004cbb8  mov     rax, [r15]
0x18004cbbb  lea     r8, [rsp+1D0h+ppbc]
0x18004cbc0  lea     rdx, aShbindctxprope; "SHBindCtxPropertyBag"
0x18004cbc7  mov     rcx, r15
0x18004cbca  mov     rax, [rax+50h]
0x18004cbce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cbd3  test    eax, eax
0x18004cbd5  js      short loc_18004CC34
0x18004cbd7  mov     rcx, [rsp+1D0h+ppbc]
0x18004cbdc  mov     rax, [rcx]
0x18004cbdf  lea     r8, [rsp+1D0h+propBag]
0x18004cbe4  lea     rdx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x18004cbeb  mov     rax, [rax]
0x18004cbee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cbf3  mov     ebx, eax
0x18004cbf5  mov     rcx, [rsp+1D0h+ppbc]
0x18004cbfa  mov     rax, [rcx]
0x18004cbfd  mov     rax, [rax+10h]
0x18004cc01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc06  test    ebx, ebx
0x18004cc08  js      short loc_18004CC3C
0x18004cc0a  lea     r8, [rsp+1D0h+value]; value
0x18004cc0f  lea     rdx, aShbindctxpatht; "SHBindCtxPathType"
0x18004cc16  mov     rcx, [rsp+1D0h+propBag]; propBag
0x18004cc1b  call    cs:__imp_PSPropertyBag_ReadDWORD
0x18004cc21  mov     ebx, eax
0x18004cc23  mov     rcx, [rsp+1D0h+propBag]
0x18004cc28  mov     rax, [rcx]
0x18004cc2b  mov     rax, [rax+10h]
0x18004cc2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc34  test    ebx, ebx
0x18004cc36  jns     loc_18004D65C
0x18004cc3c  xor     bl, bl
0x18004cc3e  mov     rcx, r12; pszPath
0x18004cc41  call    cs:__imp_PathGetDriveNumberW
0x18004cc47  cmp     eax, 0FFFFFFFFh
0x18004cc4a  jz      short loc_18004CC59
0x18004cc4c  test    bl, bl
0x18004cc4e  jnz     short loc_18004CCC4
0x18004cc50  cmp     word ptr [r12+2], 3Ah ; ':'
0x18004cc57  jz      short loc_18004CCD1
0x18004cc59  mov     rcx, r12; pszPath
0x18004cc5c  call    cs:__imp_PathIsUNCW
0x18004cc62  test    eax, eax
0x18004cc64  jnz     loc_18004D559
0x18004cc6a  xor     edx, edx; UrlIs
0x18004cc6c  mov     rcx, r12; pszUrl
0x18004cc6f  call    cs:__imp_UrlIsW
0x18004cc75  test    eax, eax
0x18004cc77  jz      short loc_18004CCB5
0x18004cc79  test    r15, r15
0x18004cc7c  jz      loc_18004D1F8
0x18004cc82  mov     [rbp+0D0h+phwnd], 10h
0x18004cc8a  xor     eax, eax
0x18004cc8c  mov     [rbp+0D0h+var_F0], rax
0x18004cc90  mov     rax, [r15]
0x18004cc93  lea     rdx, [rbp+0D0h+phwnd]
0x18004cc97  mov     rcx, r15
0x18004cc9a  mov     rax, [rax+38h]
0x18004cc9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cca3  test    eax, eax
0x18004cca5  js      loc_18004D1F8
0x18004ccab  cmp     dword ptr [rbp+0D0h+phwnd+4], r13d
0x18004ccaf  jnz     loc_18004D1F8
0x18004ccb5  test    bl, bl
0x18004ccb7  jnz     loc_18004D71D
0x18004ccbd  xor     ebx, ebx
0x18004ccbf  jmp     loc_18004D08A
0x18004ccc4  cmp     word ptr [r12+2], 3Ah ; ':'
0x18004cccb  jnz     loc_18004D7AB
0x18004ccd1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloBrokerShellObjects@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloBrokerShellObjects@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloBrokerShellObjects> `wil::Feature<__WilFeatureTraits_Feature_AppSiloBrokerShellObjects>::GetImpl(void)'::`2'::impl
0x18004ccd8  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloBrokerShellObjects@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloBrokerShellObjects>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18004ccdd  xor     r14d, r14d
0x18004cce0  mov     [rsp+1D0h+psfgaoOut], r14; unsigned int
0x18004cce5  xor     r9d, r9d; struct _ITEMIDLIST_ABSOLUTE **
0x18004cce8  lea     r8, [rsp+1D0h+Src]; struct IBindCtx *
0x18004cced  xor     edx, edx; unsigned __int16 *
0x18004ccef  lea     rcx, a20d04fe03aea10; "::{20D04FE0-3AEA-1069-A2D8-08002B30309D"...
0x18004ccf6  call    ?TryBrokerSHParseDisplayName@Isolation@Security@Windows@@YAJPEBGPEAUIBindCtx@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@KPEAK@Z; Windows::Security::Isolation::TryBrokerSHParseDisplayName(ushort const *,IBindCtx *,_ITEMIDLIST_ABSOLUTE * *,ulong,ulong *)
0x18004ccfb  test    eax, eax
0x18004ccfd  jns     loc_18004D654
0x18004cd03  mov     [rsp+1D0h+Src], r14
0x18004cd08  mov     [rsp+1D0h+ppwsz], r14
0x18004cd0d  lea     rdx, [rsp+1D0h+ppwsz]; ppwsz
0x18004cd12  lea     rcx, a20d04fe03aea10; "::{20D04FE0-3AEA-1069-A2D8-08002B30309D"...
0x18004cd19  call    cs:__imp_SHStrDupW
0x18004cd1f  mov     edi, eax
0x18004cd21  test    eax, eax
0x18004cd23  js      loc_18004CEB9
0x18004cd29  mov     [rsp+1D0h+ppshf], r14
0x18004cd2e  lea     rcx, [rsp+1D0h+ppshf]; ppshf
0x18004cd33  call    SHGetDesktopFolder
0x18004cd38  mov     edi, eax
0x18004cd3a  test    eax, eax
0x18004cd3c  js      loc_18004CE96
0x18004cd42  mov     ebx, r14d
0x18004cd45  mov     [rsp+1D0h+ppbc], r14
0x18004cd4a  lea     rdx, [rsp+1D0h+ppbc]; ppbc
0x18004cd4f  xor     ecx, ecx; reserved
0x18004cd51  call    cs:__imp_CreateBindCtx
0x18004cd57  mov     edi, eax
0x18004cd59  test    eax, eax
0x18004cd5b  js      loc_18004CDE8
0x18004cd61  mov     rdi, [rsp+1D0h+ppbc]
0x18004cd66  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004cd6d  mov     ecx, 40h ; '@'; unsigned __int64
0x18004cd72  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004cd77  mov     [rbp+0D0h+phwnd], rax
0x18004cd7b  test    rax, rax
0x18004cd7e  jz      loc_18004D348
0x18004cd84  mov     rcx, rax; this
0x18004cd87  call    ??0CDummyUnknown@@QEAA@XZ; CDummyUnknown::CDummyUnknown(void)
0x18004cd8c  mov     rsi, rax
0x18004cd8f  test    rax, rax
0x18004cd92  jz      loc_18004D348
0x18004cd98  mov     rax, [rdi]
0x18004cd9b  mov     r8, rsi
0x18004cd9e  lea     rdx, aParseTranslate; "Parse Translate Aliases"
0x18004cda5  mov     rcx, rdi
0x18004cda8  mov     rax, [rax+48h]
0x18004cdac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cdb1  mov     edi, eax
0x18004cdb3  dec     dword ptr [rsi+18h]
0x18004cdb6  cmp     [rsi+18h], ebx
0x18004cdb9  jle     loc_18004D1A0
0x18004cdbf  test    edi, edi
0x18004cdc1  js      short loc_18004CDD7
0x18004cdc3  mov     rbx, [rsp+1D0h+ppbc]
0x18004cdc8  mov     rax, [rbx]
0x18004cdcb  mov     rcx, rbx
0x18004cdce  mov     rax, [rax+8]
0x18004cdd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cdd7  mov     rcx, [rsp+1D0h+ppbc]
0x18004cddc  mov     rax, [rcx]
0x18004cddf  mov     rax, [rax+10h]
0x18004cde3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cde8  test    edi, edi
0x18004cdea  js      loc_18004CE7D
0x18004cdf0  mov     rdi, [rsp+1D0h+ppshf]
0x18004cdf5  mov     rax, [rdi]
0x18004cdf8  mov     r14, [rax+18h]
0x18004cdfc  mov     rsi, [rsp+1D0h+ppwsz]
0x18004ce01  xor     eax, eax
0x18004ce03  mov     [rbp+0D0h+phwnd], rax
0x18004ce07  mov     [rsp+1D0h+propBag], rax
0x18004ce0c  movups  xmm0, xmmword ptr cs:aUiDuringBindin; "UI During Binding"
0x18004ce13  movups  xmmword ptr [rbp+0D0h+ppu.cbSize], xmm0
0x18004ce17  movups  xmm1, xmmword ptr cs:aUiDuringBindin+10h; "g Binding"
0x18004ce1e  movups  xmmword ptr [rbp+0D0h+ppu.cchProtocol], xmm1
0x18004ce22  mov     eax, dword ptr cs:aUiDuringBindin+20h; "g"
0x18004ce28  mov     [rbp+0D0h+ppu.cchSuffix], eax
0x18004ce2b  test    rbx, rbx
0x18004ce2e  jz      short loc_18004CE50
0x18004ce30  mov     rax, [rbx]
0x18004ce33  lea     r8, [rsp+1D0h+propBag]
0x18004ce38  lea     rdx, [rbp+0D0h+ppu]
0x18004ce3c  mov     rcx, rbx
0x18004ce3f  mov     rax, [rax+50h]
0x18004ce43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce48  test    eax, eax
0x18004ce4a  jns     loc_18004D1D3
0x18004ce50  xor     ecx, ecx
0x18004ce52  mov     [rsp+1D0h+var_1A0], rcx
0x18004ce57  lea     rax, [rsp+1D0h+Src]
0x18004ce5c  mov     [rsp+1D0h+var_1A8], rax
0x18004ce61  mov     [rsp+1D0h+psfgaoOut], rcx
0x18004ce66  mov     r9, rsi
0x18004ce69  mov     r8, rbx
0x18004ce6c  mov     rdx, [rbp+0D0h+phwnd]
0x18004ce70  mov     rcx, rdi
0x18004ce73  mov     rax, r14
0x18004ce76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce7b  mov     edi, eax
0x18004ce7d  test    rbx, rbx
0x18004ce80  jz      short loc_18004CE92
0x18004ce82  mov     rax, [rbx]
0x18004ce85  mov     rcx, rbx
0x18004ce88  mov     rax, [rax+10h]
0x18004ce8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce91  nop
0x18004ce92  mov     rsi, [rbp+0D0h+var_120]
0x18004ce96  mov     rcx, [rsp+1D0h+ppwsz]; pv
0x18004ce9b  call    cs:__imp_CoTaskMemFree
0x18004cea1  nop
0x18004cea2  mov     rcx, [rsp+1D0h+ppshf]
0x18004cea7  test    rcx, rcx
0x18004ceaa  jz      short loc_18004CEB9
0x18004ceac  mov     rax, [rcx]
0x18004ceaf  mov     rax, [rax+10h]
0x18004ceb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ceb8  nop
0x18004ceb9  xor     ebx, ebx
0x18004cebb  test    edi, edi
0x18004cebd  js      loc_18004CCBD
0x18004cec3  mov     r14, [rsp+1D0h+Src]
0x18004cec8  test    r14, r14
0x18004cecb  jz      loc_18004CF6E
0x18004ced1  cmp     [rsp+1D0h+var_180], 0
0x18004ced7  jnz     loc_18004CF6E
0x18004cedd  mov     [rsp+1D0h+var_180], rbx
0x18004cee2  mov     [rsp+1D0h+ppbc], rbx
0x18004cee7  lea     r8, [rsp+1D0h+ppbc]
0x18004ceec  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x18004cef3  xor     ecx, ecx
0x18004cef5  call    CDesktopFolder_CreateInstance
0x18004cefa  mov     edi, eax
0x18004cefc  test    eax, eax
0x18004cefe  js      short loc_18004CF61
0x18004cf00  test    r14, r14
0x18004cf03  jz      loc_18004D1B2
0x18004cf09  cmp     word ptr [r14], 0
0x18004cf0e  jz      loc_18004D1B2
0x18004cf14  mov     rcx, [rsp+1D0h+ppbc]
0x18004cf19  mov     rax, [rcx]
0x18004cf1c  lea     rdx, [rsp+1D0h+var_180]
0x18004cf21  mov     [rsp+1D0h+psfgaoOut], rdx
0x18004cf26  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x18004cf2d  xor     r8d, r8d
0x18004cf30  mov     rdx, r14
0x18004cf33  mov     rax, [rax+28h]
0x18004cf37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf3c  mov     edi, eax
0x18004cf3e  test    eax, eax
0x18004cf40  js      short loc_18004CF50
0x18004cf42  mov     eax, 80004005h
0x18004cf47  cmp     [rsp+1D0h+var_180], 0
0x18004cf4d  cmovz   edi, eax
0x18004cf50  mov     rcx, [rsp+1D0h+ppbc]
0x18004cf55  mov     rax, [rcx]
0x18004cf58  mov     rax, [rax+10h]
0x18004cf5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf61  test    edi, edi
0x18004cf63  js      loc_18004D825
0x18004cf69  mov     r14, [rsp+1D0h+Src]
0x18004cf6e  mov     rdx, [rsp+1D0h+var_190]
0x18004cf73  test    rdx, rdx
0x18004cf76  jnz     loc_18004D13D
0x18004cf7c  mov     rcx, [rsp+1D0h+var_180]
0x18004cf81  mov     [rsi], rbx
0x18004cf84  mov     [rsp+1D0h+ppbc], rbx
0x18004cf89  mov     rax, [rcx]
0x18004cf8c  mov     r8, [rbp+0D0h+var_110]
0x18004cf90  mov     [rsp+1D0h+var_1A0], r8
0x18004cf95  lea     r8, [rsp+1D0h+ppbc]
0x18004cf9a  mov     [rsp+1D0h+var_1A8], r8
0x18004cf9f  mov     [rsp+1D0h+psfgaoOut], rdx
0x18004cfa4  mov     r9, r12
0x18004cfa7  mov     r8, r15
0x18004cfaa  mov     rdx, [rbp+0D0h+var_118]
0x18004cfae  mov     rax, [rax+18h]
0x18004cfb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cfb7  mov     edi, eax
0x18004cfb9  test    eax, eax
0x18004cfbb  js      loc_18004D06E
  ... truncated ...
```
