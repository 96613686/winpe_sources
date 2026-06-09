# CodecUtil::CodecEncDecHelper::TranscodeFile(ushort const *,ushort const *,_GUID const &,uint)

- ea: `0x18001e5f0`
- end: `0x18001ee68`
- name: `?TranscodeFile@CodecEncDecHelper@CodecUtil@@QEAAXPEBG0AEBU_GUID@@I@Z`
- size: `2168`
- prototype: `void __usercall(LPVOID *ppv@<rcx>, PCWSTR pszName@<rdx>, PCWSTR@<r8>, const struct _GUID *@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004a000`

## callees

- `0x18000cb74`
- `0x18001e5f0`
- `0x18002f638`
- `0x18002f74c`
- `0x18002f854`
- `0x18002f894`
- `0x18003f800`
- `0x180080010`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x18001e6f7`
- `KERNEL32!CopyFileW` at `0x18001e6f7`
- `ole32!CoTaskMemFree` at `0x18001eba7`
- `ole32!CoTaskMemFree` at `0x18001eceb`
- `ole32!CoTaskMemFree` at `0x18001eba7`
- `ole32!CoTaskMemFree` at `0x18001eceb`
- `ole32!CoCreateInstance` at `0x18001e64a`
- `ole32!CoCreateInstance` at `0x18001e64a`
- `SHELL32!SHBindToParent` at `0x18001eab5`
- `SHELL32!SHBindToParent` at `0x18001ebfc`
- `SHELL32!SHBindToParent` at `0x18001eab5`
- `SHELL32!SHBindToParent` at `0x18001ebfc`
- `SHELL32!SHCreateItemWithParent` at `0x18001eaec`
- `SHELL32!SHCreateItemWithParent` at `0x18001ec33`
- `SHELL32!SHCreateItemWithParent` at `0x18001eaec`
- `SHELL32!SHCreateItemWithParent` at `0x18001ec33`
- `SHELL32!SHParseDisplayName` at `0x18001ea7d`
- `SHELL32!SHParseDisplayName` at `0x18001ebc4`
- `SHELL32!SHParseDisplayName` at `0x18001ea7d`
- `SHELL32!SHParseDisplayName` at `0x18001ebc4`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e656`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e6a3`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e6c9`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e733`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e759`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e780`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e7b0`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e7d9`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e821`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e8e0`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e966`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e972`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e9ba`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001ea1a`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001ea89`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001eac1`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001eaf8`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001eb25`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001eb56`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001ebd0`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001ec08`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001ec3f`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001ec6c`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001ec9a`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001ed1d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001ed63`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001eda3`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001ede6`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e656`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e6a3`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e6c9`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e733`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e759`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e780`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e7b0`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e7d9`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e821`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e8e0`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e966`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e972`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001e9ba`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001ea1a`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001ea89`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001eac1`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001eaf8`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001eb25`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001eb56`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001ebd0`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001ec08`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001ec3f`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001ec6c`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001ec9a`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001ed1d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001ed63`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001eda3`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001ede6`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
void __fastcall CodecUtil::CodecEncDecHelper::TranscodeFile(
        LPVOID *ppv,
        PCWSTR pszName,
        PCWSTR a3,
        const struct _GUID *a4,
        unsigned int a5)
{
  unsigned int v5; // r14d
  HRESULT Instance; // eax
  int v11; // edx
  unsigned int v12; // r15d
  int v13; // eax
  int v14; // edx
  int v15; // eax
  int v16; // edx
  __int64 v17; // rax
  int v18; // edx
  int v19; // eax
  int v20; // edx
  int v21; // eax
  int v22; // edx
  int v23; // eax
  int v24; // edx
  int v25; // eax
  int v26; // edx
  struct IWICBitmapEncoder *v27; // rdi
  struct IWICBitmapDecoder *v28; // rbx
  int v29; // eax
  int v30; // edx
  int v31; // edx
  int v32; // eax
  int v33; // edx
  unsigned int RequiredPaletteSize; // eax
  int v35; // eax
  int v36; // edx
  int v37; // eax
  int v38; // edx
  struct IWICBitmapEncoder *v39; // rcx
  unsigned int v40; // eax
  __int64 v41; // rcx
  struct IWICBitmapDecoder *v42; // rcx
  HRESULT v43; // eax
  int v44; // edx
  HRESULT v45; // eax
  int v46; // edx
  HRESULT v47; // eax
  int v48; // edx
  int v49; // eax
  int v50; // edx
  int v51; // eax
  int v52; // edx
  HRESULT v53; // eax
  int v54; // edx
  HRESULT v55; // eax
  int v56; // edx
  HRESULT v57; // eax
  int v58; // edx
  int v59; // eax
  int v60; // edx
  int v61; // eax
  int v62; // edx
  __int64 v63; // rsi
  __int64 v64; // rdi
  int v65; // eax
  int v66; // edx
  unsigned int i; // ebx
  int v68; // eax
  int v69; // edx
  int v70; // eax
  int v71; // edx
  int v72; // eax
  int v73; // edx
  unsigned int v74; // eax
  int v75; // edx
  void *ppvItem; // [rsp+40h] [rbp-E8h] BYREF
  IShellFolder *v77; // [rsp+48h] [rbp-E0h] BYREF
  __int64 v78; // [rsp+50h] [rbp-D8h] BYREF
  struct IWICBitmapEncoder *v79; // [rsp+58h] [rbp-D0h] BYREF
  __int64 v80; // [rsp+60h] [rbp-C8h] BYREF
  struct IWICBitmapDecoder *v81; // [rsp+68h] [rbp-C0h] BYREF
  IShellFolder *psfParent; // [rsp+70h] [rbp-B8h] BYREF
  LPITEMIDLIST ppidl; // [rsp+78h] [rbp-B0h] BYREF
  __int64 v84; // [rsp+80h] [rbp-A8h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+88h] [rbp-A0h] BYREF
  LPCWSTR v86; // [rsp+90h] [rbp-98h]
  __int128 v87; // [rsp+98h] [rbp-90h] BYREF
  __int64 v88; // [rsp+A8h] [rbp-80h]
  _BYTE v89[16]; // [rsp+B0h] [rbp-78h] BYREF
  __int128 v90; // [rsp+C0h] [rbp-68h] BYREF
  __int128 v91; // [rsp+D0h] [rbp-58h] BYREF
  int v92; // [rsp+E0h] [rbp-48h]

  v86 = a3;
  if ( !*ppv )
  {
    Instance = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, ppv);
    if ( Instance < 0 )
    {
      Base::Throw((Base *)(unsigned int)Instance, v11);
      __debugbreak();
    }
  }
  v12 = 0;
  v81 = 0;
  v90 = 0;
  v13 = (*(__int64 (__fastcall **)(_QWORD, PCWSTR, _QWORD, __int64, int, struct IWICBitmapDecoder **))(*(_QWORD *)*ppv + 24LL))(
          *ppv,
          pszName,
          0,
          0x80000000LL,
          1,
          &v81);
  if ( v13 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v13, v14);
    __debugbreak();
  }
  v15 = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, __int128 *))v81->lpVtbl->GetContainerFormat)(v81, &v90);
  if ( v15 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v15, v16);
    __debugbreak();
  }
  v17 = *(_QWORD *)&a4->Data1 - v90;
  if ( *(_QWORD *)&a4->Data1 == (_QWORD)v90 )
    v17 = *(_QWORD *)a4->Data4 - *((_QWORD *)&v90 + 1);
  if ( !v17 )
  {
    if ( !CopyFileW(pszName, a3, 0) )
    {
      Base::Throw((Base *)0x80004005LL, v18);
      __debugbreak();
    }
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v81);
    return;
  }
  v80 = 0;
  v19 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*ppv + 112LL))(*ppv, &v80);
  if ( v19 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v19, v20);
    __debugbreak();
  }
  v21 = (*(__int64 (__fastcall **)(__int64, PCWSTR, __int64))(*(_QWORD *)v80 + 120LL))(v80, a3, 3221225472LL);
  if ( v21 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v21, v22);
    __debugbreak();
  }
  v79 = 0;
  v23 = (*(__int64 (__fastcall **)(_QWORD, const struct _GUID *, GUID *, struct IWICBitmapEncoder **))(*(_QWORD *)*ppv + 64LL))(
          *ppv,
          a4,
          &GUID_VendorMicrosoft,
          &v79);
  if ( v23 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v23, v24);
    __debugbreak();
  }
  v25 = ((__int64 (__fastcall *)(struct IWICBitmapEncoder *, __int64, __int64))v79->lpVtbl->Initialize)(v79, v80, 2);
  if ( v25 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v25, v26);
    __debugbreak();
  }
  v27 = v79;
  v28 = v81;
  v77 = 0;
  if ( ((int (__fastcall *)(struct IWICBitmapDecoder *, IShellFolder **))v81->lpVtbl->GetPreview)(v81, &v77) >= 0 )
  {
    v29 = ((__int64 (__fastcall *)(struct IWICBitmapEncoder *, IShellFolder *))v27->lpVtbl->SetPreview)(v27, v77);
    if ( v29 < 0 )
    {
      Base::Throw((Base *)(unsigned int)v29, v30);
      __debugbreak();
    }
  }
  v78 = 0;
  if ( ((int (__fastcall *)(struct IWICBitmapDecoder *, __int64 *))v28->lpVtbl->GetThumbnail)(v28, &v78) >= 0 )
    ((void (__fastcall *)(struct IWICBitmapEncoder *, __int64))v27->lpVtbl->SetThumbnail)(v27, v78);
  if ( (unsigned int)CodecUtil::GetRequiredPaletteSize(v27) != -1 )
  {
    CodecUtil::CodecEncDecHelper::EnsureImagingFactory(ppv);
    ATL::CComQIPtr<IWICComponentFactory,&__s_GUID const _GUID_412d0c3a_9650_44fa_af5b_dd2a06c8e8fb>::CComQIPtr<IWICComponentFactory,&__s_GUID const _GUID_412d0c3a_9650_44fa_af5b_dd2a06c8e8fb>(
      &v84,
      *ppv);
    if ( !v84 )
      goto LABEL_41;
    ppvItem = 0;
    if ( (*(int (__fastcall **)(__int64, void **))(*(_QWORD *)v84 + 72LL))(v84, &ppvItem) >= 0
      && ((int (__fastcall *)(struct IWICBitmapDecoder *, void *))v28->lpVtbl->CopyPalette)(v28, ppvItem) >= 0 )
    {
      v32 = ((__int64 (__fastcall *)(struct IWICBitmapEncoder *, void *))v27->lpVtbl->SetPalette)(v27, ppvItem);
      if ( v32 < 0 )
        Base::Throw((Base *)(unsigned int)v32, v33);
    }
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&ppvItem);
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v84);
  }
  if ( v78 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
  if ( v77 )
    ((void (__fastcall *)(IShellFolder *))v77->lpVtbl->Release)(v77);
  RequiredPaletteSize = CodecUtil::GetRequiredPaletteSize(v27);
  v5 = RequiredPaletteSize;
  if ( a5 == -1 )
  {
    LODWORD(ppvItem) = 0;
    v35 = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, void **))v28->lpVtbl->GetFrameCount)(v28, &ppvItem);
    if ( v35 >= 0 )
      goto LABEL_42;
    Base::Throw((Base *)(unsigned int)v35, v36);
LABEL_41:
    Base::Throw((Base *)0x80004002LL, v31);
LABEL_42:
    if ( (_DWORD)ppvItem )
    {
      do
        CodecUtil::CodecEncDecHelper::TransferFrame(ppv, v28, v27, v12++, v5);
      while ( v12 < (unsigned int)ppvItem );
    }
    goto LABEL_44;
  }
  CodecUtil::CodecEncDecHelper::TransferFrame(ppv, v28, v27, a5, RequiredPaletteSize);
LABEL_44:
  v37 = ((__int64 (__fastcall *)(struct IWICBitmapEncoder *))v79->lpVtbl->Commit)(v79);
  if ( v37 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v37, v38);
    __debugbreak();
  }
  v39 = v79;
  if ( v79 )
  {
    v79 = 0;
    ((void (__fastcall *)(struct IWICBitmapEncoder *))v39->lpVtbl->Release)(v39);
  }
  v40 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v80 + 64LL))(v80, 0);
  if ( (int)(v40 + 0x80000000) >= 0 && v40 != -2147467263 )
    Base::Throw((Base *)v40, 0x80000000);
  v41 = v80;
  if ( v80 )
  {
    v80 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  }
  v42 = v81;
  if ( v81 )
  {
    v81 = 0;
    ((void (__fastcall *)(struct IWICBitmapDecoder *))v42->lpVtbl->Release)(v42);
  }
  try
  {
    v84 = 0;
    v78 = 0;
    ppidl = 0;
    v43 = SHParseDisplayName(pszName, 0, &ppidl, 0, 0);
    if ( v43 < 0 )
      Base::Throw((Base *)(unsigned int)v43, v44);
    psfParent = 0;
    ppidlLast = 0;
    v45 = SHBindToParent(ppidl, &GUID_000214e6_0000_0000_c000_000000000046, (void **)&psfParent, &ppidlLast);
    if ( v45 < 0 )
      Base::Throw((Base *)(unsigned int)v45, v46);
    ppvItem = 0;
    v47 = SHCreateItemWithParent(0, psfParent, ppidlLast, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppvItem);
    if ( v47 < 0 )
      Base::Throw((Base *)(unsigned int)v47, v48);
    v77 = 0;
    v49 = (**(__int64 (__fastcall ***)(void *, GUID *, IShellFolder **))ppvItem)(
            ppvItem,
            &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
            &v77);
    if ( v49 < 0 )
      Base::Throw((Base *)(unsigned int)v49, v50);
    v51 = ((__int64 (__fastcall *)(IShellFolder *, __int64, GUID *, __int64 *))v77->lpVtbl->CreateViewObject)(
            v77,
            64,
            &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
            &v84);
    if ( v51 < 0 )
      Base::Throw((Base *)(unsigned int)v51, v52);
    if ( v77 )
      ((void (__fastcall *)(IShellFolder *))v77->lpVtbl->Release)(v77);
    if ( ppvItem )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvItem + 16LL))(ppvItem);
    if ( psfParent )
      ((void (__fastcall *)(IShellFolder *))psfParent->lpVtbl->Release)(psfParent);
    CoTaskMemFree(ppidl);
    ppvItem = 0;
    v53 = SHParseDisplayName(a3, 0, (LPITEMIDLIST *)&ppvItem, 0, 0);
    if ( v53 < 0 )
      Base::Throw((Base *)(unsigned int)v53, v54);
    v77 = 0;
    ppidlLast = 0;
    v55 = SHBindToParent((LPCITEMIDLIST)ppvItem, &GUID_000214e6_0000_0000_c000_000000000046, (void **)&v77, &ppidlLast);
    if ( v55 < 0 )
      Base::Throw((Base *)(unsigned int)v55, v56);
    psfParent = 0;
    v57 = SHCreateItemWithParent(0, v77, ppidlLast, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)&psfParent);
    if ( v57 < 0 )
      Base::Throw((Base *)(unsigned int)v57, v58);
    ppidl = 0;
    v59 = ((__int64 (__fastcall *)(IShellFolder *, GUID *, LPITEMIDLIST *))psfParent->lpVtbl->QueryInterface)(
            psfParent,
            &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
            &ppidl);
    if ( v59 < 0 )
      Base::Throw((Base *)(unsigned int)v59, v60);
    v61 = (*(__int64 (__fastcall **)(LPITEMIDLIST, __int64, GUID *, __int64 *))(*(_QWORD *)&ppidl->mkid.cb + 64LL))(
            ppidl,
            2,
            &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
            &v78);
    if ( v61 < 0 )
      Base::Throw((Base *)(unsigned int)v61, v62);
    if ( ppidl )
      (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&ppidl->mkid.cb + 16LL))(ppidl);
    if ( psfParent )
      ((void (__fastcall *)(IShellFolder *))psfParent->lpVtbl->Release)(psfParent);
    if ( v77 )
      ((void (__fastcall *)(IShellFolder *))v77->lpVtbl->Release)(v77);
    CoTaskMemFree(ppvItem);
    v63 = v78;
    v64 = v84;
    LODWORD(ppvItem) = 0;
    v65 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v84 + 24LL))(v84, &ppvItem);
    if ( v65 < 0 )
      Base::Throw((Base *)(unsigned int)v65, v66);
    for ( i = 0; i < (unsigned int)ppvItem; ++i )
    {
      v91 = 0;
      v92 = 0;
      v68 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v64 + 32LL))(v64, i, &v91);
      if ( v68 < 0 )
        Base::Throw((Base *)(unsigned int)v68, v69);
      v87 = 0;
      v88 = 0;
      v70 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)v64 + 40LL))(v64, &v91, &v87);
      if ( v70 < 0 )
        Base::Throw((Base *)(unsigned int)v70, v71);
      (*(void (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)v63 + 48LL))(v63, &v91, &v87);
    }
    v72 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v78 + 56LL))(v78);
    if ( v72 < 0 )
      Base::Throw((Base *)(unsigned int)v72, v73);
    if ( v78 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
    if ( v84 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
  }
  catch ( Base::Exception v89 )
  {
    DeleteFileW(v86);
    v74 = Base::Exception::operator long(v89);
    Base::Throw((Base *)v74, v75);
    JUMPOUT(0x18007BFF0LL);
  }
  if ( v79 )
    ((void (__fastcall *)(struct IWICBitmapEncoder *))v79->lpVtbl->Release)(v79);
  if ( v80 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
  if ( v81 )
    ((void (__fastcall *)(struct IWICBitmapDecoder *))v81->lpVtbl->Release)(v81);
}

```

## disassembly

```asm
0x18001e5f0  push    rbx
0x18001e5f2  push    rsi
0x18001e5f3  push    rdi
0x18001e5f4  push    r12
0x18001e5f6  push    r13
0x18001e5f8  push    r14
0x18001e5fa  push    r15
0x18001e5fc  sub     rsp, 0F0h
0x18001e603  mov     rax, cs:__security_cookie
0x18001e60a  xor     rax, rsp
0x18001e60d  mov     [rsp+128h+var_40], rax
0x18001e615  mov     rbx, r9
0x18001e618  mov     r13, r8
0x18001e61b  mov     r12, rdx
0x18001e61e  mov     rsi, rcx
0x18001e621  mov     [rsp+128h+var_98], r8
0x18001e629  cmp     qword ptr [rcx], 0
0x18001e62d  jnz     short loc_18001E65D
0x18001e62f  mov     [rsp+128h+ppv], rcx; ppv
0x18001e634  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18001e63b  xor     edx, edx; pUnkOuter
0x18001e63d  mov     r8d, 1; dwClsContext
0x18001e643  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18001e64a  call    cs:__imp_CoCreateInstance
0x18001e650  test    eax, eax
0x18001e652  jns     short loc_18001E65D
0x18001e654  mov     ecx, eax
0x18001e656  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18001e65c  int     3; Trap to Debugger
0x18001e65d  xor     r15d, r15d
0x18001e660  mov     [rsp+128h+var_C0], r15
0x18001e665  xorps   xmm0, xmm0
0x18001e668  movups  [rsp+128h+var_68], xmm0
0x18001e670  mov     rcx, [rsi]
0x18001e673  mov     rax, [rcx]
0x18001e676  lea     rdx, [rsp+128h+var_C0]
0x18001e67b  mov     [rsp+128h+var_100], rdx
0x18001e680  mov     dword ptr [rsp+128h+ppv], 1
0x18001e688  mov     r9d, 80000000h
0x18001e68e  xor     r8d, r8d
0x18001e691  mov     rdx, r12
0x18001e694  mov     rax, [rax+18h]
0x18001e698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e69d  test    eax, eax
0x18001e69f  jns     short loc_18001E6AA
0x18001e6a1  mov     ecx, eax
0x18001e6a3  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18001e6a9  int     3; Trap to Debugger
0x18001e6aa  mov     rcx, [rsp+128h+var_C0]
0x18001e6af  mov     rax, [rcx]
0x18001e6b2  lea     rdx, [rsp+128h+var_68]
0x18001e6ba  mov     rax, [rax+28h]
0x18001e6be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6c3  test    eax, eax
0x18001e6c5  jns     short loc_18001E6D0
0x18001e6c7  mov     ecx, eax
0x18001e6c9  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18001e6cf  int     3; Trap to Debugger
0x18001e6d0  mov     rax, [rbx]
0x18001e6d3  sub     rax, qword ptr [rsp+128h+var_68]
0x18001e6db  jnz     short loc_18001E6E9
0x18001e6dd  mov     rax, [rbx+8]
0x18001e6e1  sub     rax, qword ptr [rsp+128h+var_68+8]
0x18001e6e9  test    rax, rax
0x18001e6ec  jnz     short loc_18001E73A
0x18001e6ee  xor     r8d, r8d; bFailIfExists
0x18001e6f1  mov     rdx, r13; lpNewFileName
0x18001e6f4  mov     rcx, r12; lpExistingFileName
0x18001e6f7  call    cs:__imp_CopyFileW
0x18001e6fd  test    eax, eax
0x18001e6ff  jz      short loc_18001E72E
0x18001e701  lea     rcx, [rsp+128h+var_C0]
0x18001e706  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18001e70b  mov     rcx, [rsp+128h+var_40]
0x18001e713  xor     rcx, rsp; StackCookie
0x18001e716  call    __security_check_cookie
0x18001e71b  add     rsp, 0F0h
0x18001e722  pop     r15
0x18001e724  pop     r14
0x18001e726  pop     r13
0x18001e728  pop     r12
0x18001e72a  pop     rdi
0x18001e72b  pop     rsi
0x18001e72c  pop     rbx
0x18001e72d  retn
0x18001e72e  mov     ecx, 80004005h
0x18001e733  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18001e739  int     3; Trap to Debugger
0x18001e73a  mov     [rsp+128h+var_C8], r15
0x18001e73f  mov     rcx, [rsi]
0x18001e742  mov     rax, [rcx]
0x18001e745  lea     rdx, [rsp+128h+var_C8]
0x18001e74a  mov     rax, [rax+70h]
0x18001e74e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e753  test    eax, eax
0x18001e755  jns     short loc_18001E760
0x18001e757  mov     ecx, eax
0x18001e759  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18001e75f  int     3; Trap to Debugger
0x18001e760  mov     rcx, [rsp+128h+var_C8]
0x18001e765  mov     rax, [rcx]
0x18001e768  mov     r8d, 0C0000000h
0x18001e76e  mov     rdx, r13
0x18001e771  mov     rax, [rax+78h]
0x18001e775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e77a  test    eax, eax
0x18001e77c  jns     short loc_18001E787
0x18001e77e  mov     ecx, eax
0x18001e780  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18001e786  int     3; Trap to Debugger
0x18001e787  mov     [rsp+128h+var_D0], r15
0x18001e78c  mov     rcx, [rsi]
0x18001e78f  mov     rax, [rcx]
0x18001e792  lea     r9, [rsp+128h+var_D0]
0x18001e797  lea     r8, GUID_VendorMicrosoft
0x18001e79e  mov     rdx, rbx
0x18001e7a1  mov     rax, [rax+40h]
0x18001e7a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7aa  test    eax, eax
0x18001e7ac  jns     short loc_18001E7B7
0x18001e7ae  mov     ecx, eax
0x18001e7b0  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18001e7b6  int     3; Trap to Debugger
0x18001e7b7  mov     rcx, [rsp+128h+var_D0]
0x18001e7bc  mov     rax, [rcx]
0x18001e7bf  mov     r8d, 2
0x18001e7c5  mov     rdx, [rsp+128h+var_C8]
0x18001e7ca  mov     rax, [rax+18h]
0x18001e7ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7d3  test    eax, eax
0x18001e7d5  jns     short loc_18001E7E0
0x18001e7d7  mov     ecx, eax
0x18001e7d9  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18001e7df  int     3; Trap to Debugger
0x18001e7e0  mov     rdi, [rsp+128h+var_D0]
0x18001e7e5  mov     rbx, [rsp+128h+var_C0]
0x18001e7ea  mov     [rsp+128h+var_E0], r15
0x18001e7ef  mov     rax, [rbx]
0x18001e7f2  lea     rdx, [rsp+128h+var_E0]
0x18001e7f7  mov     rcx, rbx
0x18001e7fa  mov     rax, [rax+48h]
0x18001e7fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e803  test    eax, eax
0x18001e805  js      short loc_18001E828
0x18001e807  mov     rax, [rdi]
0x18001e80a  mov     rdx, [rsp+128h+var_E0]
0x18001e80f  mov     rcx, rdi
0x18001e812  mov     rax, [rax+48h]
0x18001e816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e81b  test    eax, eax
0x18001e81d  jns     short loc_18001E828
0x18001e81f  mov     ecx, eax
0x18001e821  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18001e827  int     3; Trap to Debugger
0x18001e828  mov     [rsp+128h+var_D8], r15
0x18001e82d  mov     rax, [rbx]
0x18001e830  lea     rdx, [rsp+128h+var_D8]
0x18001e835  mov     rcx, rbx
0x18001e838  mov     rax, [rax+58h]
0x18001e83c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e841  test    eax, eax
0x18001e843  js      short loc_18001E859
0x18001e845  mov     rax, [rdi]
0x18001e848  mov     rdx, [rsp+128h+var_D8]
0x18001e84d  mov     rcx, rdi
0x18001e850  mov     rax, [rax+40h]
0x18001e854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e859  mov     rcx, rdi
0x18001e85c  call    CodecUtil__GetRequiredPaletteSize
0x18001e861  cmp     eax, 0FFFFFFFFh
0x18001e864  jz      loc_18001E900
0x18001e86a  mov     rcx, rsi; ppv
0x18001e86d  call    ?EnsureImagingFactory@CodecEncDecHelper@CodecUtil@@AEAAXXZ; CodecUtil::CodecEncDecHelper::EnsureImagingFactory(void)
0x18001e872  mov     rdx, [rsi]
0x18001e875  lea     rcx, [rsp+128h+var_A8]
0x18001e87d  call    ??0?$CComQIPtr@UIWICComponentFactory@@$1?_GUID_412d0c3a_9650_44fa_af5b_dd2a06c8e8fb@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IWICComponentFactory,&__s_GUID const _GUID_412d0c3a_9650_44fa_af5b_dd2a06c8e8fb>::CComQIPtr<IWICComponentFactory,&__s_GUID const _GUID_412d0c3a_9650_44fa_af5b_dd2a06c8e8fb>(IUnknown *)
0x18001e882  nop
0x18001e883  mov     rcx, [rsp+128h+var_A8]
0x18001e88b  test    rcx, rcx
0x18001e88e  jz      loc_18001E96D
0x18001e894  mov     [rsp+128h+ppvItem], r15
0x18001e899  mov     rax, [rcx]
0x18001e89c  lea     rdx, [rsp+128h+ppvItem]
0x18001e8a1  mov     rax, [rax+48h]
0x18001e8a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8aa  test    eax, eax
0x18001e8ac  js      short loc_18001E8E7
0x18001e8ae  mov     rax, [rbx]
0x18001e8b1  mov     rdx, [rsp+128h+ppvItem]
0x18001e8b6  mov     rcx, rbx
0x18001e8b9  mov     rax, [rax+38h]
0x18001e8bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8c2  test    eax, eax
0x18001e8c4  js      short loc_18001E8E7
0x18001e8c6  mov     rax, [rdi]
0x18001e8c9  mov     rdx, [rsp+128h+ppvItem]
0x18001e8ce  mov     rcx, rdi
0x18001e8d1  mov     rax, [rax+38h]
0x18001e8d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8da  test    eax, eax
0x18001e8dc  jns     short loc_18001E8E7
0x18001e8de  mov     ecx, eax
0x18001e8e0  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18001e8e6  nop
0x18001e8e7  lea     rcx, [rsp+128h+ppvItem]
0x18001e8ec  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18001e8f1  nop
0x18001e8f2  lea     rcx, [rsp+128h+var_A8]
0x18001e8fa  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18001e8ff  nop
0x18001e900  mov     rcx, [rsp+128h+var_D8]
0x18001e905  test    rcx, rcx
0x18001e908  jz      short loc_18001E917
0x18001e90a  mov     rax, [rcx]
0x18001e90d  mov     rax, [rax+10h]
0x18001e911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e916  nop
0x18001e917  mov     rcx, [rsp+128h+var_E0]
0x18001e91c  test    rcx, rcx
0x18001e91f  jz      short loc_18001E92E
0x18001e921  mov     rax, [rcx]
0x18001e924  mov     rax, [rax+10h]
0x18001e928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e92d  nop
0x18001e92e  mov     rcx, rdi
0x18001e931  call    CodecUtil__GetRequiredPaletteSize
0x18001e936  mov     r14d, eax
0x18001e939  mov     r9d, [rsp+128h+arg_20]; unsigned int
0x18001e941  cmp     r9d, 0FFFFFFFFh
0x18001e945  jnz     short loc_18001E9C1
0x18001e947  mov     dword ptr [rsp+128h+ppvItem], r15d
0x18001e94c  mov     rcx, [rbx]
0x18001e94f  mov     rax, [rcx+60h]
0x18001e953  lea     rdx, [rsp+128h+ppvItem]
0x18001e958  mov     rcx, rbx
0x18001e95b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e960  test    eax, eax
0x18001e962  jns     short loc_18001E979
0x18001e964  mov     ecx, eax
0x18001e966  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18001e96c  nop
0x18001e96d  mov     ecx, 80004002h
0x18001e972  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18001e978  nop
0x18001e979  cmp     dword ptr [rsp+128h+ppvItem], 0
0x18001e97e  jbe     short loc_18001E9A0
0x18001e980  mov     dword ptr [rsp+128h+ppv], r14d; unsigned int
0x18001e985  mov     r9d, r15d; unsigned int
0x18001e988  mov     r8, rdi; struct IWICBitmapEncoder *
0x18001e98b  mov     rdx, rbx; struct IWICBitmapDecoder *
0x18001e98e  mov     rcx, rsi; ppv
0x18001e991  call    ?TransferFrame@CodecEncDecHelper@CodecUtil@@AEAAXPEAUIWICBitmapDecoder@@PEAUIWICBitmapEncoder@@II@Z; CodecUtil::CodecEncDecHelper::TransferFrame(IWICBitmapDecoder *,IWICBitmapEncoder *,uint,uint)
0x18001e996  inc     r15d
0x18001e999  cmp     r15d, dword ptr [rsp+128h+ppvItem]
0x18001e99e  jb      short loc_18001E980
0x18001e9a0  xor     r15d, r15d
0x18001e9a3  mov     rcx, [rsp+128h+var_D0]
0x18001e9a8  mov     rax, [rcx]
0x18001e9ab  mov     rax, [rax+58h]
0x18001e9af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9b4  test    eax, eax
0x18001e9b6  jns     short loc_18001E9D6
0x18001e9b8  mov     ecx, eax
0x18001e9ba  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18001e9c0  int     3; Trap to Debugger
0x18001e9c1  mov     dword ptr [rsp+128h+ppv], r14d; unsigned int
0x18001e9c6  mov     r8, rdi; struct IWICBitmapEncoder *
0x18001e9c9  mov     rdx, rbx; struct IWICBitmapDecoder *
0x18001e9cc  mov     rcx, rsi; ppv
0x18001e9cf  call    ?TransferFrame@CodecEncDecHelper@CodecUtil@@AEAAXPEAUIWICBitmapDecoder@@PEAUIWICBitmapEncoder@@II@Z; CodecUtil::CodecEncDecHelper::TransferFrame(IWICBitmapDecoder *,IWICBitmapEncoder *,uint,uint)
0x18001e9d4  jmp     short loc_18001E9A3
0x18001e9d6  mov     rcx, [rsp+128h+var_D0]
0x18001e9db  test    rcx, rcx
0x18001e9de  jz      short loc_18001E9F2
0x18001e9e0  mov     [rsp+128h+var_D0], r15
0x18001e9e5  mov     rax, [rcx]
0x18001e9e8  mov     rax, [rax+10h]
0x18001e9ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9f1  nop
0x18001e9f2  mov     rcx, [rsp+128h+var_C8]
0x18001e9f7  mov     rax, [rcx]
0x18001e9fa  xor     edx, edx
0x18001e9fc  mov     rax, [rax+40h]
0x18001ea00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea05  mov     edx, 80000000h
0x18001ea0a  lea     ecx, [rax+rdx]
0x18001ea0d  test    edx, ecx
0x18001ea0f  jnz     short loc_18001EA21
0x18001ea11  cmp     eax, 80004001h
0x18001ea16  jz      short loc_18001EA21
0x18001ea18  mov     ecx, eax
0x18001ea1a  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18001ea20  nop
0x18001ea21  mov     rcx, [rsp+128h+var_C8]
0x18001ea26  test    rcx, rcx
0x18001ea29  jz      short loc_18001EA3D
0x18001ea2b  mov     [rsp+128h+var_C8], r15
0x18001ea30  mov     rax, [rcx]
0x18001ea33  mov     rax, [rax+10h]
0x18001ea37  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
