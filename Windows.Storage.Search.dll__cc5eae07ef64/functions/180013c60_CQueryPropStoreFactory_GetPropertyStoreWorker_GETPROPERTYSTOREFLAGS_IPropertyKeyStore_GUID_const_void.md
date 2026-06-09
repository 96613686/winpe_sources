# CQueryPropStoreFactory::_GetPropertyStoreWorker(GETPROPERTYSTOREFLAGS,IPropertyKeyStore *,_GUID const &,void * *)

- ea: `0x180013c60`
- end: `0x18001448f`
- name: `?_GetPropertyStoreWorker@CQueryPropStoreFactory@@AEAAJW4GETPROPERTYSTOREFLAGS@@PEAUIPropertyKeyStore@@AEBU_GUID@@PEAPEAX@Z`
- size: `2095`
- prototype: `__int64 __usercall@<rax>(CQueryPropStoreFactory *__hidden this@<rcx>, enum GETPROPERTYSTOREFLAGS@<edx>, struct IPropertyKeyStore *@<r8>, const struct _GUID *@<r9>, void **)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180013a30`
- `0x180013a60`

## callees

- `0x180006ca8`
- `0x18001173c`
- `0x180013000`
- `0x180013c60`
- `0x180014498`
- `0x1800144c4`
- `0x180014704`
- `0x180014740`
- `0x1800147c0`
- `0x180071dc0`
- `0x180071df0`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x180013f93`
- `SHCORE!IUnknown_Set` at `0x180013fa0`
- `SHCORE!IUnknown_Set` at `0x180013f93`
- `SHCORE!IUnknown_Set` at `0x180013fa0`
- `Windows.Storage!SHParseDisplayName` at `0x180014148`
- `Windows.Storage!SHParseDisplayName` at `0x180014148`
- `Windows.Storage!SHBindToFolderIDListParentEx` at `0x180013df9`
- `Windows.Storage!SHBindToFolderIDListParentEx` at `0x180013df9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014375`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014375`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014272`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014299`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014272`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014299`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800142a4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800142a4`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800140ff`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800140ff`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x180013fb7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x180013fb7`
- `PROPSYS!PSCreateMultiplexPropertyStore` at `0x180013d4e`
- `PROPSYS!PSCreateMultiplexPropertyStore` at `0x180013ff3`
- `PROPSYS!PSCreateMultiplexPropertyStore` at `0x1800143d8`
- `PROPSYS!PSCreateMultiplexPropertyStore` at `0x180013d4e`
- `PROPSYS!PSCreateMultiplexPropertyStore` at `0x180013ff3`
- `PROPSYS!PSCreateMultiplexPropertyStore` at `0x1800143d8`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800140cf`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800140cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
HRESULT __fastcall CQueryPropStoreFactory::_GetPropertyStoreWorker(
        CQueryPropStoreFactory *this,
        unsigned int a2,
        IUnknown *a3,
        const struct _GUID *a4,
        void **a5)
{
  IUnknown *v6; // rdi
  HRESULT FileSysBindCtx; // edi
  int v10; // ebx
  HRESULT result; // eax
  int v12; // edi
  unsigned int v13; // esi
  __int64 v14; // rsi
  __int64 (__fastcall *v15)(__int64, _QWORD, GUID *, __int64 *); // rdi
  char v16; // di
  DWORD v17; // esi
  int ProviderCapabilities; // eax
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, _QWORD, _QWORD, IUnknown **); // rdi
  IUnknown *v21; // rsi
  IUnknown *v22; // r14
  CDBComputedPropStore *v23; // rax
  CDBComputedPropStore *v24; // rax
  IUnknown **v25; // rbx
  int v26; // esi
  __int64 v27; // rsi
  void *v28; // rcx
  IUnknown *v29; // rcx
  IUnknown *v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rax
  struct IUnknown *v33; // rcx
  __int64 v34; // rsi
  __int64 (__fastcall *v35)(__int64, _QWORD, __int64, IUnknown *, void *, GUID *, IUnknown **); // rdi
  LPITEMIDLIST v36; // rcx
  __int64 v37; // rbx
  char v38; // [rsp+40h] [rbp-A1h]
  PWSTR ppszOut; // [rsp+48h] [rbp-99h] BYREF
  int v40; // [rsp+50h] [rbp-91h] BYREF
  IUnknown *v41; // [rsp+58h] [rbp-89h] BYREF
  void *ppv; // [rsp+60h] [rbp-81h] BYREF
  void *v43; // [rsp+68h] [rbp-79h] BYREF
  IUnknown *punk; // [rsp+70h] [rbp-71h] BYREF
  __int64 v45; // [rsp+78h] [rbp-69h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+80h] [rbp-61h] BYREF
  IUnknown *prgpunkStores[2]; // [rsp+88h] [rbp-59h] BYREF
  void *v48; // [rsp+98h] [rbp-49h] BYREF
  LPITEMIDLIST ppidl; // [rsp+A0h] [rbp-41h] BYREF
  int v50; // [rsp+A8h] [rbp-39h]
  __int64 v51; // [rsp+B0h] [rbp-31h] BYREF
  PROPVARIANT propvar[3]; // [rsp+B8h] [rbp-29h] BYREF
  IUnknown *v53[2]; // [rsp+D0h] [rbp-11h] BYREF
  __int64 v54; // [rsp+E0h] [rbp-1h]

  v6 = a3;
  prgpunkStores[0] = a3;
  *a5 = 0;
  if ( (a2 & 0xFFFFE000) != 0 && a2 != 1073742848 && a2 != -2147483646 )
    return -2147024809;
  ppv = 0;
  if ( (a2 & 3) != 0 )
  {
    FileSysBindCtx = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, void **))(**((_QWORD **)this + 4) + 64LL))(
                       *((_QWORD *)this + 4),
                       *((_QWORD *)this + 5),
                       a2,
                       &ppv);
LABEL_8:
    if ( FileSysBindCtx < 0 )
      return FileSysBindCtx;
    v10 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))ppv)(ppv, a4, a5);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    return v10;
  }
  if ( (a2 & 8) != 0 )
  {
    v41 = 0;
    FileSysBindCtx = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, GUID *, IUnknown **))(**((_QWORD **)this + 4) + 72LL))(
                       *((_QWORD *)this + 4),
                       *((_QWORD *)this + 5),
                       0,
                       0,
                       0,
                       &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                       &v41);
    if ( FileSysBindCtx >= 0 )
    {
      ppszOut = 0;
      if ( (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD, PWSTR *))(**((_QWORD **)this + 4) + 64LL))(
             *((_QWORD *)this + 4),
             *((_QWORD *)this + 5),
             a2,
             &ppszOut) < 0 )
      {
        FileSysBindCtx = ((__int64 (__fastcall *)(IUnknown *, GUID *, void **))v41->lpVtbl->QueryInterface)(
                           v41,
                           &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                           &ppv);
      }
      else
      {
        prgpunkStores[0] = (IUnknown *)ppszOut;
        prgpunkStores[1] = v41;
        FileSysBindCtx = PSCreateMultiplexPropertyStore(
                           prgpunkStores,
                           2u,
                           &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                           &ppv);
        (*(void (__fastcall **)(PWSTR))(*(_QWORD *)ppszOut + 16LL))(ppszOut);
      }
      ((void (__fastcall *)(IUnknown *))v41->lpVtbl->Release)(v41);
    }
    goto LABEL_8;
  }
  ppidlLast = 0;
  ppszOut = 0;
  if ( SHBindToFolderIDListParentEx(
         *((IShellFolder **)this + 3),
         *((LPCITEMIDLIST *)this + 5),
         0,
         &GUID_000214e6_0000_0000_c000_000000000046,
         (void **)&ppszOut,
         &ppidlLast) < 0 )
  {
    v13 = 1;
  }
  else
  {
    v12 = 0;
    v40 = 0x40000000;
    v13 = 1;
    if ( (*(int (__fastcall **)(PWSTR, __int64, LPCITEMIDLIST *, int *))(*(_QWORD *)ppszOut + 72LL))(
           ppszOut,
           1,
           &ppidlLast,
           &v40) >= 0 )
      v12 = v40 & 0x40000000;
    (*(void (__fastcall **)(PWSTR))(*(_QWORD *)ppszOut + 16LL))(ppszOut);
    if ( v12 == 0x40000000
      && (*(int (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 4) + 104LL))(
           *((_QWORD *)this + 4),
           *((_QWORD *)this + 5),
           0xFFFFFFFFLL) >= 0 )
    {
      *(_OWORD *)v53 = 0;
      v54 = 0;
      v45 = 0;
      v14 = *((_QWORD *)this + 4);
      v15 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v14 + 80LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
      FileSysBindCtx = v15(v14, *((_QWORD *)this + 5), &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v45);
      if ( FileSysBindCtx < 0 )
      {
LABEL_33:
        v31 = v45;
        if ( v45 )
        {
          v45 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        }
        goto LABEL_8;
      }
      v16 = 0;
      v38 = 0;
      v17 = 0;
      v40 = 0;
      v41 = 0;
      punk = 0;
      v43 = 0;
      ProviderCapabilities = GetProviderCapabilities(v45);
      v50 = ProviderCapabilities;
      if ( (ProviderCapabilities & 0x200) != 0 )
      {
        LOWORD(propvar[0]) = 0;
        FileSysBindCtx = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v45 + 40LL))(
                           v45,
                           &PKEY_ParsingPath,
                           propvar);
        if ( FileSysBindCtx >= 0 )
        {
          ppszOut = 0;
          FileSysBindCtx = PropVariantToStringAlloc(propvar, &ppszOut);
          if ( FileSysBindCtx >= 0 )
          {
            v32 = -1;
            do
              ++v32;
            while ( ppszOut[v32] );
            FileSysBindCtx = PathCchRemoveFileSpec(ppszOut, v32 + 1);
            if ( !FileSysBindCtx )
            {
              ppidlLast = 0;
              FileSysBindCtx = CQueryPropStoreFactory::_CreateFileSysBindCtx(this, (struct IBindCtx **)&ppidlLast);
              if ( FileSysBindCtx >= 0 )
              {
                ppidl = 0;
                FileSysBindCtx = SHParseDisplayName(ppszOut, (IBindCtx *)ppidlLast, &ppidl, 0, 0);
                if ( FileSysBindCtx >= 0 )
                {
                  v48 = 0;
                  FileSysBindCtx = CScope_CreateInstance(v33, 0, &GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798, &v48);
                  if ( FileSysBindCtx >= 0 )
                  {
                    v51 = 0;
                    FileSysBindCtx = SHCreateScopeItemFromIDList(
                                       (_DWORD)ppidl,
                                       1,
                                       1,
                                       0,
                                       (__int64)&GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0,
                                       (__int64)&v51);
                    if ( FileSysBindCtx >= 0 )
                    {
                      FileSysBindCtx = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)v48 + 24LL))(v48, v51);
                      if ( FileSysBindCtx >= 0 )
                      {
                        v34 = *((_QWORD *)this + 4);
                        v35 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, IUnknown *, void *, GUID *, IUnknown **))(*(_QWORD *)v34 + 72LL);
                        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
                        FileSysBindCtx = v35(
                                           v34,
                                           *((_QWORD *)this + 5),
                                           1,
                                           prgpunkStores[0],
                                           v48,
                                           &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                                           &v41);
                        if ( FileSysBindCtx < 0 )
                        {
                          v17 = v40;
                        }
                        else
                        {
                          v53[0] = v41;
                          v17 = 1;
                          v40 = 1;
                          v38 = 1;
                        }
                      }
                    }
                    if ( v51 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
                  }
                  if ( v48 )
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v48 + 16LL))(v48);
                }
                v36 = ppidl;
                ppidl = 0;
                CoTaskMemFree(v36);
              }
              if ( ppidlLast )
                (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)&ppidlLast->mkid.cb + 16LL))(ppidlLast);
            }
          }
          if ( ppszOut )
            CoTaskMemFree(ppszOut);
        }
        PropVariantClear(propvar);
        if ( FileSysBindCtx < 0 )
          goto LABEL_27;
        LOWORD(ProviderCapabilities) = v50;
        v16 = v38;
      }
      if ( (ProviderCapabilities & 0x400) == 0 && ((a2 & 0x100) == 0 || !v16) )
      {
        v19 = *((_QWORD *)this + 4);
        v20 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, IUnknown **))(*(_QWORD *)v19 + 64LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punk);
        FileSysBindCtx = v20(v19, *((_QWORD *)this + 5), a2, &punk);
        if ( FileSysBindCtx < 0 )
          goto LABEL_27;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
        v21 = punk;
        v22 = (IUnknown *)*((_QWORD *)this + 3);
        v43 = 0;
        v23 = (CDBComputedPropStore *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
        FileSysBindCtx = -2147024882;
        if ( !v23 )
          goto LABEL_27;
        v24 = CDBComputedPropStore::CDBComputedPropStore(v23);
        v25 = (IUnknown **)v24;
        if ( v24 )
        {
          IUnknown_Set((IUnknown **)v24 + 2, v22);
          IUnknown_Set(v25 + 3, v21);
          FileSysBindCtx = QISearch(v25, &stru_1800EE5B0, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v43);
          CDBComputedPropStore::Release((CDBComputedPropStore *)v25);
        }
        if ( FileSysBindCtx < 0 )
          goto LABEL_27;
        v26 = v40;
        v53[v40] = (IUnknown *)v43;
        v27 = (unsigned int)(v26 + 1);
        v53[v27] = punk;
        v17 = v27 + 1;
      }
      FileSysBindCtx = PSCreateMultiplexPropertyStore(v53, v17, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
LABEL_27:
      v28 = v43;
      if ( v43 )
      {
        v43 = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v28 + 16LL))(v28);
      }
      v29 = punk;
      if ( punk )
      {
        punk = 0;
        ((void (__fastcall *)(IUnknown *))v29->lpVtbl->Release)(v29);
      }
      v30 = v41;
      if ( v41 )
      {
        v41 = 0;
        ((void (__fastcall *)(IUnknown *))v30->lpVtbl->Release)(v30);
      }
      goto LABEL_33;
    }
    v6 = prgpunkStores[0];
  }
  *(_OWORD *)prgpunkStores = 0;
  if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 4) + 88LL))(
         *((_QWORD *)this + 4),
         *((_QWORD *)this + 5))
    || !(*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 4) + 96LL))(
          *((_QWORD *)this + 4),
          *((_QWORD *)this + 5)) )
  {
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, IUnknown *, _QWORD, GUID *, IUnknown **))(**((_QWORD **)this + 4) + 72LL))(
               *((_QWORD *)this + 4),
               *((_QWORD *)this + 5),
               1,
               v6,
               0,
               &GUID_00000000_0000_0000_c000_000000000046,
               prgpunkStores);
  }
  else
  {
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, IUnknown **))(**((_QWORD **)this + 4) + 80LL))(
               *((_QWORD *)this + 4),
               *((_QWORD *)this + 5),
               &GUID_00000000_0000_0000_c000_000000000046,
               prgpunkStores);
  }
  if ( result >= 0 )
  {
    ppszOut = 0;
    result = CoCreateInstance(
               &CLSID_AssocPropertyStore,
               0,
               1u,
               &GUID_b3a4b685_b685_4805_99d9_5dead2873236,
               (LPVOID *)&ppszOut);
    if ( result >= 0 )
    {
      FileSysBindCtx = (*(__int64 (__fastcall **)(PWSTR, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppszOut + 24LL))(
                         ppszOut,
                         0,
                         *((_QWORD *)this + 3),
                         *((_QWORD *)this + 5));
      if ( FileSysBindCtx >= 0 )
      {
        FileSysBindCtx = (**(__int64 (__fastcall ***)(PWSTR, GUID *, IUnknown **))ppszOut)(
                           ppszOut,
                           &GUID_00000000_0000_0000_c000_000000000046,
                           &prgpunkStores[1]);
        if ( FileSysBindCtx >= 0 )
        {
          v13 = 2;
          FileSysBindCtx = PSCreateMultiplexPropertyStore(
                             prgpunkStores,
                             2u,
                             &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                             &ppv);
        }
        v37 = 0;
        do
        {
          SafeRelease<IShellItemArray>((__int64 *)&prgpunkStores[v37]);
          v37 = (unsigned int)(v37 + 1);
        }
        while ( (unsigned int)v37 < v13 );
      }
      (*(void (__fastcall **)(PWSTR))(*(_QWORD *)ppszOut + 16LL))(ppszOut);
      goto LABEL_8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180013c60  push    rbp
0x180013c62  push    rbx
0x180013c63  push    rsi
0x180013c64  push    rdi
0x180013c65  push    r12
0x180013c67  push    r13
0x180013c69  push    r14
0x180013c6b  push    r15
0x180013c6d  lea     rbp, [rsp-17h]
0x180013c72  sub     rsp, 0F8h
0x180013c79  mov     rax, cs:__security_cookie
0x180013c80  xor     rax, rsp
0x180013c83  mov     [rbp+4Fh+var_48], rax
0x180013c87  mov     r12, r9
0x180013c8a  mov     rdi, r8
0x180013c8d  mov     [rbp+4Fh+prgpunkStores], r8
0x180013c91  mov     ebx, edx
0x180013c93  mov     r14, rcx
0x180013c96  mov     r15, [rbp+4Fh+arg_20]
0x180013c9a  xor     esi, esi
0x180013c9c  mov     [r15], rsi
0x180013c9f  test    edx, 0FFFFE000h
0x180013ca5  jnz     loc_180014070
0x180013cab  mov     [rsp+130h+ppv], rsi
0x180013cb0  test    bl, 3
0x180013cb3  jnz     loc_1800142BF
0x180013cb9  test    bl, 8
0x180013cbc  jz      loc_180013DCB
0x180013cc2  mov     [rsp+130h+var_D8], rsi
0x180013cc7  mov     rcx, [rcx+20h]
0x180013ccb  mov     rax, [rcx]
0x180013cce  lea     rdx, [rsp+130h+var_D8]
0x180013cd3  mov     [rsp+130h+var_100], rdx
0x180013cd8  lea     r13, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180013cdf  mov     [rsp+130h+ppidlLast], r13
0x180013ce4  mov     [rsp+130h+psfgaoOut], rsi
0x180013ce9  xor     r9d, r9d
0x180013cec  xor     r8d, r8d
0x180013cef  mov     rdx, [r14+28h]
0x180013cf3  mov     rax, [rax+48h]
0x180013cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cfc  mov     edi, eax
0x180013cfe  test    eax, eax
0x180013d00  js      short loc_180013D78
0x180013d02  mov     [rsp+130h+ppszOut], rsi
0x180013d07  mov     rcx, [r14+20h]
0x180013d0b  mov     rax, [rcx]
0x180013d0e  lea     r9, [rsp+130h+ppszOut]
0x180013d13  mov     r8d, ebx
0x180013d16  mov     rdx, [r14+28h]
0x180013d1a  mov     rax, [rax+40h]
0x180013d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d23  test    eax, eax
0x180013d25  js      loc_18001445D
0x180013d2b  mov     rax, [rsp+130h+ppszOut]
0x180013d30  mov     [rbp+4Fh+prgpunkStores], rax
0x180013d34  mov     rax, [rsp+130h+var_D8]
0x180013d39  mov     [rbp+4Fh+prgpunkStores+8], rax
0x180013d3d  lea     r9, [rsp+130h+ppv]; ppv
0x180013d42  mov     r8, r13; riid
0x180013d45  mov     edx, 2; cStores
0x180013d4a  lea     rcx, [rbp+4Fh+prgpunkStores]; prgpunkStores
0x180013d4e  call    cs:__imp_PSCreateMultiplexPropertyStore
0x180013d54  mov     edi, eax
0x180013d56  mov     rcx, [rsp+130h+ppszOut]
0x180013d5b  mov     rax, [rcx]
0x180013d5e  mov     rax, [rax+10h]
0x180013d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d67  mov     rcx, [rsp+130h+var_D8]
0x180013d6c  mov     rax, [rcx]
0x180013d6f  mov     rax, [rax+10h]
0x180013d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d78  test    edi, edi
0x180013d7a  js      loc_180014456
0x180013d80  mov     rcx, [rsp+130h+ppv]
0x180013d85  mov     rax, [rcx]
0x180013d88  mov     r8, r15
0x180013d8b  mov     rdx, r12
0x180013d8e  mov     rax, [rax]
0x180013d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d96  mov     ebx, eax
0x180013d98  mov     rcx, [rsp+130h+ppv]
0x180013d9d  mov     rdx, [rcx]
0x180013da0  mov     rax, [rdx+10h]
0x180013da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013da9  mov     eax, ebx
0x180013dab  mov     rcx, [rbp+4Fh+var_48]
0x180013daf  xor     rcx, rsp; StackCookie
0x180013db2  call    __security_check_cookie
0x180013db7  add     rsp, 0F8h
0x180013dbe  pop     r15
0x180013dc0  pop     r14
0x180013dc2  pop     r13
0x180013dc4  pop     r12
0x180013dc6  pop     rdi
0x180013dc7  pop     rsi
0x180013dc8  pop     rbx
0x180013dc9  pop     rbp
0x180013dca  retn
0x180013dcb  mov     [rbp+4Fh+var_B0], rsi
0x180013dcf  mov     [rsp+130h+ppszOut], rsi
0x180013dd4  lea     rax, [rbp+4Fh+var_B0]
0x180013dd8  mov     [rsp+130h+ppidlLast], rax; ppidlLast
0x180013ddd  lea     rax, [rsp+130h+ppszOut]
0x180013de2  mov     [rsp+130h+psfgaoOut], rax; ppv
0x180013de7  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180013dee  xor     r8d, r8d; ppbc
0x180013df1  mov     rdx, [rcx+28h]; pidl
0x180013df5  mov     rcx, [rcx+18h]; psfRoot
0x180013df9  call    cs:__imp_SHBindToFolderIDListParentEx
0x180013dff  test    eax, eax
0x180013e01  js      loc_180014485
0x180013e07  mov     edi, esi
0x180013e09  mov     [rsp+130h+var_E0], 40000000h
0x180013e11  mov     rcx, [rsp+130h+ppszOut]
0x180013e16  mov     rax, [rcx]
0x180013e19  lea     r9, [rsp+130h+var_E0]
0x180013e1e  lea     r8, [rbp+4Fh+var_B0]
0x180013e22  mov     esi, 1
0x180013e27  mov     edx, esi
0x180013e29  mov     rax, [rax+48h]
0x180013e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e32  test    eax, eax
0x180013e34  js      short loc_180013E40
0x180013e36  mov     edi, [rsp+130h+var_E0]
0x180013e3a  and     edi, 40000000h
0x180013e40  mov     rcx, [rsp+130h+ppszOut]
0x180013e45  mov     rax, [rcx]
0x180013e48  mov     rax, [rax+10h]
0x180013e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e51  cmp     edi, 40000000h
0x180013e57  jnz     loc_1800142E2
0x180013e5d  mov     rcx, [r14+20h]
0x180013e61  mov     rax, [rcx]
0x180013e64  mov     r8d, 0FFFFFFFFh
0x180013e6a  mov     rdx, [r14+28h]
0x180013e6e  mov     rax, [rax+68h]
0x180013e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e77  test    eax, eax
0x180013e79  js      loc_1800142E2
0x180013e7f  xorps   xmm0, xmm0
0x180013e82  xor     eax, eax
0x180013e84  movups  xmmword ptr [rbp+4Fh+var_60], xmm0
0x180013e88  mov     [rbp+4Fh+var_50], rax
0x180013e8c  mov     [rbp+4Fh+var_B8], rax
0x180013e90  mov     rsi, [r14+20h]
0x180013e94  mov     rax, [rsi]
0x180013e97  mov     rdi, [rax+50h]
0x180013e9b  lea     rcx, [rbp+4Fh+var_B8]
0x180013e9f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013ea4  lea     r9, [rbp+4Fh+var_B8]
0x180013ea8  lea     r13, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180013eaf  mov     r8, r13
0x180013eb2  mov     rdx, [r14+28h]
0x180013eb6  mov     rcx, rsi
0x180013eb9  mov     rax, rdi
0x180013ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ec1  mov     edi, eax
0x180013ec3  test    eax, eax
0x180013ec5  js      loc_18001404D
0x180013ecb  xor     dil, dil
0x180013ece  mov     [rsp+130h+var_F0], dil
0x180013ed3  xor     eax, eax
0x180013ed5  mov     esi, eax
0x180013ed7  mov     [rsp+130h+var_E0], eax
0x180013edb  mov     [rsp+130h+var_D8], rax
0x180013ee0  mov     [rbp+4Fh+punk], rax
0x180013ee4  mov     [rbp+4Fh+var_C8], rax
0x180013ee8  mov     rcx, [rbp+4Fh+var_B8]
0x180013eec  call    ?GetProviderCapabilities@@YA?AW4PROVIDER_CAPABILITIES@@PEAUIPropertyStore@@@Z; GetProviderCapabilities(IPropertyStore *)
0x180013ef1  mov     [rbp+4Fh+var_88], eax
0x180013ef4  bt      eax, 9
0x180013ef8  jb      loc_180014092
0x180013efe  bt      eax, 0Ah
0x180013f02  jb      loc_180013FE5
0x180013f08  bt      ebx, 8
0x180013f0c  jb      loc_18001440B
0x180013f12  mov     rsi, [r14+20h]
0x180013f16  mov     rax, [rsi]
0x180013f19  mov     rdi, [rax+40h]
0x180013f1d  lea     rcx, [rbp+4Fh+punk]
0x180013f21  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013f26  lea     r9, [rbp+4Fh+punk]
0x180013f2a  mov     r8d, ebx
0x180013f2d  mov     rdx, [r14+28h]
0x180013f31  mov     rcx, rsi
0x180013f34  mov     rax, rdi
0x180013f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f3c  mov     edi, eax
0x180013f3e  test    eax, eax
0x180013f40  js      loc_180013FFB
0x180013f46  lea     rcx, [rbp+4Fh+var_C8]
0x180013f4a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013f4f  mov     rsi, [rbp+4Fh+punk]
0x180013f53  mov     r14, [r14+18h]
0x180013f57  xor     ebx, ebx
0x180013f59  mov     [rbp+4Fh+var_C8], rbx
0x180013f5d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013f64  mov     ecx, 20h ; ' '; unsigned __int64
0x180013f69  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180013f6e  mov     edi, 8007000Eh
0x180013f73  test    rax, rax
0x180013f76  jz      loc_180013FFD
0x180013f7c  mov     rcx, rax; this
0x180013f7f  call    ??0CDBComputedPropStore@@QEAA@XZ; CDBComputedPropStore::CDBComputedPropStore(void)
0x180013f84  mov     rbx, rax
0x180013f87  test    rax, rax
0x180013f8a  jz      short loc_180013FC7
0x180013f8c  lea     rcx, [rax+10h]; ppunk
0x180013f90  mov     rdx, r14; punk
0x180013f93  call    cs:__imp_IUnknown_Set
0x180013f99  lea     rcx, [rbx+18h]; ppunk
0x180013f9d  mov     rdx, rsi; punk
0x180013fa0  call    cs:__imp_IUnknown_Set
0x180013fa6  lea     r9, [rbp+4Fh+var_C8]; ppv
0x180013faa  mov     r8, r13; riid
0x180013fad  lea     rdx, stru_1800EE5B0; pqit
0x180013fb4  mov     rcx, rbx; that
0x180013fb7  call    cs:__imp_QISearch
0x180013fbd  mov     edi, eax
0x180013fbf  mov     rcx, rbx; this
0x180013fc2  call    ?Release@CDBComputedPropStore@@UEAAKXZ; CDBComputedPropStore::Release(void)
0x180013fc7  test    edi, edi
0x180013fc9  js      short loc_180013FFB
0x180013fcb  mov     esi, [rsp+130h+var_E0]
0x180013fcf  mov     rax, [rbp+4Fh+var_C8]
0x180013fd3  mov     [rbp+rsi*8+4Fh+var_60], rax
0x180013fd8  inc     esi
0x180013fda  mov     rax, [rbp+4Fh+punk]
0x180013fde  mov     [rbp+rsi*8+4Fh+var_60], rax
0x180013fe3  inc     esi
0x180013fe5  lea     r9, [rsp+130h+ppv]; ppv
0x180013fea  mov     r8, r13; riid
0x180013fed  mov     edx, esi; cStores
0x180013fef  lea     rcx, [rbp+4Fh+var_60]; prgpunkStores
0x180013ff3  call    cs:__imp_PSCreateMultiplexPropertyStore
0x180013ff9  mov     edi, eax
0x180013ffb  xor     ebx, ebx
0x180013ffd  mov     rcx, [rbp+4Fh+var_C8]
0x180014001  test    rcx, rcx
0x180014004  jz      short loc_180014017
0x180014006  mov     [rbp+4Fh+var_C8], rbx
0x18001400a  mov     rax, [rcx]
0x18001400d  mov     rax, [rax+10h]
0x180014011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014016  nop
0x180014017  mov     rcx, [rbp+4Fh+punk]
0x18001401b  test    rcx, rcx
0x18001401e  jz      short loc_180014031
0x180014020  mov     [rbp+4Fh+punk], rbx
0x180014024  mov     rax, [rcx]
0x180014027  mov     rax, [rax+10h]
0x18001402b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014030  nop
0x180014031  mov     rcx, [rsp+130h+var_D8]
0x180014036  test    rcx, rcx
0x180014039  jz      short loc_18001404D
0x18001403b  mov     [rsp+130h+var_D8], rbx
0x180014040  mov     rax, [rcx]
0x180014043  mov     rax, [rax+10h]
0x180014047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001404c  nop
0x18001404d  mov     rcx, [rbp+4Fh+var_B8]
0x180014051  test    rcx, rcx
0x180014054  jz      short loc_18001406B
0x180014056  mov     [rbp+4Fh+var_B8], 0
0x18001405e  mov     rax, [rcx]
0x180014061  mov     rax, [rax+10h]
0x180014065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001406a  nop
0x18001406b  jmp     loc_180013D78
0x180014070  cmp     ebx, 40000400h
0x180014076  jz      loc_180013CAB
0x18001407c  cmp     ebx, 80000002h
0x180014082  jz      loc_180013CAB
0x180014088  mov     eax, 80070057h
0x18001408d  jmp     loc_180013DAB
0x180014092  xor     ecx, ecx
0x180014094  mov     word ptr [rbp+4Fh+propvar], cx
0x180014098  mov     rcx, [rbp+4Fh+var_B8]
0x18001409c  mov     rdx, [rcx]
0x18001409f  mov     rax, [rdx+28h]
0x1800140a3  lea     r8, [rbp+4Fh+propvar]
0x1800140a7  lea     rdx, PKEY_ParsingPath
0x1800140ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140b3  mov     edi, eax
0x1800140b5  test    eax, eax
0x1800140b7  js      loc_1800142A0
0x1800140bd  mov     [rsp+130h+ppszOut], 0
0x1800140c6  lea     rdx, [rsp+130h+ppszOut]; ppszOut
0x1800140cb  lea     rcx, [rbp+4Fh+propvar]; propvar
0x1800140cf  call    cs:__imp_PropVariantToStringAlloc
0x1800140d5  mov     edi, eax
0x1800140d7  test    eax, eax
0x1800140d9  js      loc_18001428F
0x1800140df  mov     rcx, [rsp+130h+ppszOut]; pszPath
0x1800140e4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800140eb  nop     dword ptr [rax+rax+00h]
0x1800140f0  lea     rax, [rax+1]
0x1800140f4  cmp     word ptr [rcx+rax*2], 0
  ... truncated ...
```
