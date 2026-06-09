# CBinaryAutoList::Load(IStream *)

- ea: `0x18000eb40`
- end: `0x18000f88b`
- name: `?Load@CBinaryAutoList@@UEAAJPEAUIStream@@@Z`
- size: `3403`
- prototype: `__int64 __fastcall(CBinaryAutoList *this, struct IStream *, int)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000d610`
- `0x18000dec0`
- `0x18000e1c0`
- `0x18000e450`
- `0x18000eb40`
- `0x18000f894`
- `0x180010470`
- `0x180011ce0`
- `0x18001e4c4`
- `0x180035860`
- `0x180042a50`
- `0x180042b90`
- `0x180044ae0`
- `0x18004a5c0`
- `0x18004bc10`
- `0x180071dc0`
- `0x180071df0`
- `0x180072cf4`
- `0x18007d908`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x18000f56f`
- `SHCORE!IUnknown_Set` at `0x18000f56f`
- `SHCORE!IStream_Read` at `0x18000eb9e`
- `SHCORE!IStream_Read` at `0x18000ec2f`
- `SHCORE!IStream_Read` at `0x18000ec5f`
- `SHCORE!IStream_Read` at `0x18000ee5d`
- `SHCORE!IStream_Read` at `0x18000eea7`
- `SHCORE!IStream_Read` at `0x18000ef38`
- `SHCORE!IStream_Read` at `0x18000ef54`
- `SHCORE!IStream_Read` at `0x18000ef70`
- `SHCORE!IStream_Read` at `0x18000ef98`
- `SHCORE!IStream_Read` at `0x18000efb3`
- `SHCORE!IStream_Read` at `0x18000efd2`
- `SHCORE!IStream_Read` at `0x18000efee`
- `SHCORE!IStream_Read` at `0x18000f009`
- `SHCORE!IStream_Read` at `0x18000f024`
- `SHCORE!IStream_Read` at `0x18000f03b`
- `SHCORE!IStream_Read` at `0x18000f058`
- `SHCORE!IStream_Read` at `0x18000f091`
- `SHCORE!IStream_Read` at `0x18000f194`
- `SHCORE!IStream_Read` at `0x18000f1cc`
- `SHCORE!IStream_Read` at `0x18000f28c`
- `SHCORE!IStream_Read` at `0x18000f307`
- `SHCORE!IStream_Read` at `0x18000f363`
- `SHCORE!IStream_Read` at `0x18000f425`
- `SHCORE!IStream_Read` at `0x18000f4bd`
- `SHCORE!IStream_Read` at `0x18000f69f`
- `SHCORE!IStream_Read` at `0x18000f6ff`
- `SHCORE!IStream_Read` at `0x18000eb9e`
- `SHCORE!IStream_Read` at `0x18000ec2f`
- `SHCORE!IStream_Read` at `0x18000ec5f`
- `SHCORE!IStream_Read` at `0x18000ee5d`
- `SHCORE!IStream_Read` at `0x18000eea7`
- `SHCORE!IStream_Read` at `0x18000ef38`
- `SHCORE!IStream_Read` at `0x18000ef54`
- `SHCORE!IStream_Read` at `0x18000ef70`
- `SHCORE!IStream_Read` at `0x18000ef98`
- `SHCORE!IStream_Read` at `0x18000efb3`
- `SHCORE!IStream_Read` at `0x18000efd2`
- `SHCORE!IStream_Read` at `0x18000efee`
- `SHCORE!IStream_Read` at `0x18000f009`
- `SHCORE!IStream_Read` at `0x18000f024`
- `SHCORE!IStream_Read` at `0x18000f03b`
- `SHCORE!IStream_Read` at `0x18000f058`
- `SHCORE!IStream_Read` at `0x18000f091`
- `SHCORE!IStream_Read` at `0x18000f194`
- `SHCORE!IStream_Read` at `0x18000f1cc`
- `SHCORE!IStream_Read` at `0x18000f28c`
- `SHCORE!IStream_Read` at `0x18000f307`
- `SHCORE!IStream_Read` at `0x18000f363`
- `SHCORE!IStream_Read` at `0x18000f425`
- `SHCORE!IStream_Read` at `0x18000f4bd`
- `SHCORE!IStream_Read` at `0x18000f69f`
- `SHCORE!IStream_Read` at `0x18000f6ff`
- `SHCORE!IStream_ReadStr` at `0x18000f074`
- `SHCORE!IStream_ReadStr` at `0x18000f757`
- `SHCORE!IStream_ReadStr` at `0x18000f074`
- `SHCORE!IStream_ReadStr` at `0x18000f757`
- `Windows.Storage!__imp_CreateDateGroupDescription` at `0x18000f83f`
- `Windows.Storage!__imp_CreateDateGroupDescription` at `0x18000f83f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18000ed9d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18000ed9d`
- `PROPSYS!__imp_PSCreatePropertyKeyStore` at `0x18000f5f5`
- `PROPSYS!__imp_PSCreatePropertyKeyStore` at `0x18000f5f5`

## pseudocode

```c
__int64 __fastcall CBinaryAutoList::Load(CBinaryAutoList *this, struct IStream *a2, int a3)
{
  int v5; // r13d
  int v6; // ecx
  int v7; // r8d
  HRESULT KnownImplFromStream; // r15d
  __int64 v10; // rdi
  char *v11; // rax
  void *v12; // rbx
  __int64 v13; // rcx
  volatile signed __int32 *v14; // rax
  void *v15; // rdi
  int v16; // esi
  unsigned int v17; // edx
  HINSTANCE v18; // rcx
  char *v19; // rax
  char *v20; // rbx
  __int64 v21; // rdi
  unsigned int v22; // ebx
  struct _DSA *v23; // rdi
  struct _DSA *v24; // r14
  struct IUnknown *v25; // rax
  IUnknown *v26; // rbx
  IUnknown v27; // rax
  struct _DSA *v28; // rsi
  struct _DSA *v29; // rbx
  struct _DSA *v30; // rcx
  struct _DSA *v31; // rbx
  int v32; // edi
  struct _DSA *v33; // rcx
  struct _DSA *v34; // rbx
  struct _DSA *v35; // rsi
  struct _DSA *v36; // rcx
  int v37; // eax
  int v38; // eax
  PVOID v39; // rax
  CBinaryAutoList *v40; // rbx
  unsigned int v41; // esi
  PVOID ItemPtr; // rax
  struct IUnknown *pv; // [rsp+30h] [rbp-D0h] BYREF
  void *ppv; // [rsp+38h] [rbp-C8h] BYREF
  IUnknown *punk[2]; // [rsp+40h] [rbp-C0h] BYREF
  PWSTR v46; // [rsp+50h] [rbp-B0h] BYREF
  PWSTR ppsz; // [rsp+58h] [rbp-A8h] BYREF
  GUID v48; // [rsp+60h] [rbp-A0h] BYREF
  char v49[4]; // [rsp+70h] [rbp-90h] BYREF
  char v50[4]; // [rsp+74h] [rbp-8Ch] BYREF
  char v51[4]; // [rsp+78h] [rbp-88h] BYREF
  int v52; // [rsp+7Ch] [rbp-84h] BYREF
  int v53; // [rsp+80h] [rbp-80h] BYREF
  char v54[4]; // [rsp+84h] [rbp-7Ch] BYREF
  char v55[4]; // [rsp+88h] [rbp-78h] BYREF
  char v56[20]; // [rsp+8Ch] [rbp-74h] BYREF
  char v57[4]; // [rsp+A0h] [rbp-60h] BYREF
  int v58; // [rsp+A4h] [rbp-5Ch]
  PVOID v59; // [rsp+A8h] [rbp-58h]
  int v60; // [rsp+B0h] [rbp-50h]
  PVOID v61; // [rsp+B8h] [rbp-48h]
  IUnknown *v62; // [rsp+C0h] [rbp-40h]
  __int64 v63; // [rsp+C8h] [rbp-38h] BYREF
  struct IScope *v64; // [rsp+D0h] [rbp-30h] BYREF
  struct IShellItemArray *v65; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v66; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v67; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v68; // [rsp+F8h] [rbp-8h] BYREF
  __int128 pitem; // [rsp+100h] [rbp+0h] BYREF
  __int64 v70; // [rsp+110h] [rbp+10h]
  _QWORD v71[2]; // [rsp+118h] [rbp+18h] BYREF
  CBinaryAutoList *v72; // [rsp+128h] [rbp+28h] BYREF

  v72 = this;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)this,
      (unsigned int)AutoLists_LoadFromStream_Start,
      a3,
      1,
      (__int64)v71);
  v5 = 0;
  LODWORD(pv) = 0;
  KnownImplFromStream = IStream_Read(a2, &pv, 4u);
  if ( KnownImplFromStream >= 0 )
  {
    if ( (_DWORD)pv != -2147483642 )
    {
      KnownImplFromStream = -2147024809;
      goto LABEL_6;
    }
    memset_0(&v46, 0, 0xB0u);
    v65 = 0;
    v52 = -1;
    v53 = -1;
    LODWORD(pv) = 0;
    v48 = FOLDERTYPEID_Invalid;
    KnownImplFromStream = IStream_Read(a2, &pv, 4u);
    if ( KnownImplFromStream >= 0 )
    {
      if ( !(_DWORD)pv
        || (KnownImplFromStream = IUnknown_LoadKnownImplFromStream(
                                    a2,
                                    (const struct _GUID *const *)&off_1800EB330,
                                    2u,
                                    &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
                                    (void **)&v65),
            KnownImplFromStream >= 0) )
      {
        v64 = 0;
        LODWORD(pv) = 0;
        KnownImplFromStream = IStream_Read(a2, &pv, 4u);
        if ( KnownImplFromStream < 0 )
          goto LABEL_122;
        if ( (_DWORD)pv )
        {
          v10 = *((_QWORD *)this + 2);
          ppv = 0;
          KnownImplFromStream = -2147024882;
          v11 = (char *)operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
          v71[0] = v11;
          v12 = v11;
          if ( !v11 )
            goto LABEL_122;
          *(_QWORD *)v11 = &CScope::`vftable'{for `IRootScope'};
          *((_QWORD *)v11 + 1) = &CScope::`vftable'{for `IBindScopeDialog'};
          *((_QWORD *)v11 + 2) = &CScope::`vftable'{for `IScopeResolver'};
          *((_QWORD *)v11 + 3) = &CScope::`vftable'{for `IPersistStream'};
          *((_QWORD *)v11 + 4) = &CScope::`vftable'{for `IPersistXML'};
          *((_QWORD *)v11 + 5) = &CScope::`vftable'{for `IObjectWithCachedState'};
          *((_DWORD *)v11 + 17) = 1;
          *(GUID *)(v11 + 52) = GUID_NULL;
          *((_QWORD *)v11 + 9) = 0;
          *((_QWORD *)v11 + 10) = 0;
          *((_QWORD *)v11 + 12) = v10;
          *((_QWORD *)v11 + 13) = 0;
          *((_DWORD *)v11 + 28) = 1;
          _InterlockedAdd(&g_cDllRef, 1u);
          v13 = *((_QWORD *)v11 + 12);
          *((_QWORD *)v11 + 13) = 0;
          if ( v13 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
          if ( !v12 )
            goto LABEL_122;
          *((_QWORD *)v12 + 11) = 0;
          v14 = (volatile signed __int32 *)operator new(0x228u, (const struct std::nothrow_t *)&std::nothrow);
          if ( v14 )
          {
            *v14 = 1;
            *((_QWORD *)v14 + 3) = 0;
            *((_QWORD *)v12 + 11) = v14;
            _InterlockedAdd(v14, 1u);
            CScopeTreeNode::Release((CScopeTreeNode *)v14);
            v15 = v12;
            _InterlockedAdd((volatile signed __int32 *)v12 + 28, 1u);
            v16 = 0;
            KnownImplFromStream = 0;
          }
          else
          {
            v15 = 0;
            v16 = -2147024882;
          }
          CScope::Release((CScope *)v12);
          if ( v16 < 0 )
            goto LABEL_122;
          KnownImplFromStream = QISearch(v15, &stru_1800EE140, &GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798, &ppv);
          CScope::Release((CScope *)v15);
          if ( KnownImplFromStream < 0 )
            goto LABEL_122;
          punk[0] = 0;
          KnownImplFromStream = (**(__int64 (__fastcall ***)(void *, GUID *, IUnknown **))ppv)(
                                  ppv,
                                  &GUID_00000109_0000_0000_c000_000000000046,
                                  punk);
          if ( KnownImplFromStream >= 0 )
          {
            KnownImplFromStream = ((__int64 (__fastcall *)(IUnknown *, struct IStream *))punk[0]->lpVtbl[1].Release)(
                                    punk[0],
                                    a2);
            ((void (__fastcall *)(IUnknown *))punk[0]->lpVtbl->Release)(punk[0]);
            if ( KnownImplFromStream >= 0 )
              KnownImplFromStream = (**(__int64 (__fastcall ***)(void *, GUID *, struct IScope **))ppv)(
                                      ppv,
                                      &GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798,
                                      &v64);
          }
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
          if ( KnownImplFromStream < 0 )
            goto LABEL_122;
        }
        v63 = 0;
        LODWORD(pv) = 0;
        KnownImplFromStream = IStream_Read(a2, &pv, 4u);
        if ( KnownImplFromStream < 0 )
          goto LABEL_122;
        if ( (_DWORD)pv )
        {
          KnownImplFromStream = CreateVisibleInList(a2, &GUID_d18f09e2_81c2_4217_a295_43b66fa4e495, &v63);
          if ( KnownImplFromStream < 0 )
            goto LABEL_122;
        }
        v66 = 0;
        LODWORD(pv) = 0;
        KnownImplFromStream = IStream_Read(a2, &pv, 4u);
        if ( KnownImplFromStream < 0 )
          goto LABEL_122;
        if ( (_DWORD)pv )
        {
          v66 = 0;
          punk[0] = 0;
          KnownImplFromStream = IUnknown_LoadKnownImplFromStream(
                                  a2,
                                  (const struct _GUID *const *)&off_1800EB310,
                                  3u,
                                  &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                                  (void **)punk);
          if ( KnownImplFromStream >= 0 )
          {
            KnownImplFromStream = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))punk[0]->lpVtbl->QueryInterface)(
                                    punk[0],
                                    &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                                    &v66);
            ((void (__fastcall *)(IUnknown *))punk[0]->lpVtbl->Release)(punk[0]);
          }
          if ( KnownImplFromStream < 0 )
            goto LABEL_122;
        }
        KnownImplFromStream = IStream_Read(a2, v49, 4u);
        if ( KnownImplFromStream < 0 )
          goto LABEL_122;
        KnownImplFromStream = IStream_Read(a2, v50, 4u);
        if ( KnownImplFromStream < 0 )
          goto LABEL_122;
        KnownImplFromStream = IStream_Read(a2, v51, 4u);
        if ( KnownImplFromStream < 0 )
          goto LABEL_122;
        ppsz = 0;
        v46 = 0;
        KnownImplFromStream = IStream_Read(a2, v56, 0x14u);
        if ( KnownImplFromStream >= 0 )
        {
          KnownImplFromStream = IStream_Read(a2, v57, 4u);
          if ( KnownImplFromStream >= 0 )
          {
            KnownImplFromStream = IStream_Read(a2, &v48, 0x10u);
            if ( KnownImplFromStream >= 0 )
            {
              KnownImplFromStream = IStream_Read(a2, &v52, 4u);
              if ( KnownImplFromStream >= 0 )
              {
                KnownImplFromStream = IStream_Read(a2, &v53, 4u);
                if ( KnownImplFromStream >= 0 )
                {
                  KnownImplFromStream = IStream_Read(a2, v54, 4u);
                  if ( KnownImplFromStream >= 0 )
                  {
                    KnownImplFromStream = IStream_Read(a2, v55, 4u);
                    if ( KnownImplFromStream >= 0 )
                    {
                      LODWORD(pv) = 0;
                      KnownImplFromStream = IStream_Read(a2, &pv, 4u);
                      if ( KnownImplFromStream >= 0 )
                      {
                        if ( !(_DWORD)pv || (KnownImplFromStream = IStream_ReadStr(a2, &ppsz), KnownImplFromStream >= 0) )
                        {
                          LODWORD(ppv) = 0;
                          KnownImplFromStream = IStream_Read(a2, &ppv, 4u);
                          if ( KnownImplFromStream >= 0 )
                          {
                            if ( (_DWORD)ppv )
                              KnownImplFromStream = IStream_ReadStr(a2, &v46);
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
        if ( KnownImplFromStream < 0 )
          goto LABEL_122;
        if ( !ppsz )
        {
          KnownImplFromStream = GetSearchFolderName(v18, v17, v64, v65, &ppsz);
          if ( KnownImplFromStream < 0 )
            goto LABEL_122;
        }
        v71[0] = 0;
        KnownImplFromStream = -2147024882;
        v19 = (char *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
        punk[0] = (IUnknown *)v19;
        v20 = v19;
        if ( !v19 )
          goto LABEL_122;
        *((_DWORD *)v19 + 6) = 1;
        *(_QWORD *)v19 = &CEnumerableObjectCollection::`vftable'{for `IObjectCollection'};
        *((_QWORD *)v19 + 1) = &CEnumerableObjectCollection::`vftable'{for `IEnumObjects'};
        *((_QWORD *)v19 + 2) = &CEnumerableObjectCollection::`vftable'{for `IEnumUnknown'};
        *(_QWORD *)(v19 + 28) = 4;
        *((_QWORD *)v19 + 5) = 0;
        *((_QWORD *)v19 + 6) = 0;
        *((_QWORD *)v19 + 7) = 0;
        *((_QWORD *)v19 + 8) = 0;
        KnownImplFromStream = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD *))v19)(
                                v19,
                                &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
                                v71);
        (*(void (__fastcall **)(char *))(*(_QWORD *)v20 + 16LL))(v20);
        if ( KnownImplFromStream < 0 )
          goto LABEL_122;
        v21 = v71[0];
        LODWORD(ppv) = 0;
        KnownImplFromStream = IStream_Read(a2, &ppv, 4u);
        v22 = 0;
        if ( KnownImplFromStream >= 0 )
        {
          while ( v22 < (unsigned int)ppv )
          {
            pv = 0;
            KnownImplFromStream = CQueryFactoryWithOptions_CreateInstance(
                                    0,
                                    &GUID_00000000_0000_0000_c000_000000000046,
                                    &pv);
            if ( KnownImplFromStream >= 0 )
            {
              KnownImplFromStream = IUnknown_LoadFromStream(a2, pv);
              if ( KnownImplFromStream >= 0 )
                KnownImplFromStream = (*(__int64 (__fastcall **)(__int64, struct IUnknown *))(*(_QWORD *)v21 + 40LL))(
                                        v21,
                                        pv);
              ((void (__fastcall *)(struct IUnknown *))pv->lpVtbl->Release)(pv);
            }
            ++v22;
            if ( KnownImplFromStream < 0 )
              goto LABEL_121;
          }
          v62 = 0;
          LODWORD(ppv) = 0;
          v23 = 0;
          v24 = 0;
          KnownImplFromStream = IStream_Read(a2, &ppv, 4u);
          if ( KnownImplFromStream < 0 )
            goto LABEL_93;
          punk[0] = 0;
          if ( !(_DWORD)ppv )
            goto LABEL_62;
          KnownImplFromStream = -2147024882;
          v25 = (struct IUnknown *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
          pv = v25;
          v26 = v25;
          if ( !v25 )
          {
LABEL_93:
            if ( KnownImplFromStream >= 0 )
            {
              v67 = 0;
              LODWORD(pv) = 0;
              v34 = 0;
              KnownImplFromStream = IStream_Read(a2, &pv, 4u);
              if ( KnownImplFromStream >= 0 )
              {
                v35 = g_pfn_DSA_Create(20, (int)pv + 1);
                KnownImplFromStream = v35 == 0 ? 0x8007000E : 0;
                if ( (_DWORD)pv )
                {
                  while ( KnownImplFromStream >= 0 )
                  {
                    LODWORD(v70) = 0;
                    pitem = 0;
                    KnownImplFromStream = IStream_Read(a2, &pitem, 0x14u);
                    if ( KnownImplFromStream >= 0 )
                    {
                      KnownImplFromStream = 0;
                      if ( DSA_InsertItem(v35, 0x7FFFFFFF, &pitem) == -1 )
                        KnownImplFromStream = -2147024882;
                    }
                    if ( ++v5 >= (unsigned int)pv )
                      goto LABEL_96;
                  }
                }
                else
                {
LABEL_96:
                  if ( KnownImplFromStream >= 0 )
                    v34 = v35;
                }
                v36 = 0;
                if ( KnownImplFromStream < 0 )
                  v36 = v35;
                if ( v36 )
                  DSA_Destroy(v36);
              }
              if ( KnownImplFromStream >= 0 )
              {
                if ( !v34 )
                  goto LABEL_107;
                if ( *(_DWORD *)v34 )
                {
                  v41 = *(_DWORD *)v34;
                  ItemPtr = g_pfn_DSA_GetItemPtr(v34, 0);
                  KnownImplFromStream = PSCreatePropertyKeyStore(
                                          ItemPtr,
                                          v41,
                                          &GUID_75bd59aa_f23b_4963_aba4_0b355752a91b,
                                          &v67);
                }
                DSA_Destroy(v34);
                if ( KnownImplFromStream >= 0 )
                {
LABEL_107:
                  v68 = 0;
                  LODWORD(ppv) = 0;
                  KnownImplFromStream = IStream_Read(a2, &ppv, 4u);
                  if ( KnownImplFromStream >= 0 )
                  {
                    if ( !(_DWORD)ppv )
                      goto LABEL_109;
                    pv = 0;
                    punk[0] = 0;
                    KnownImplFromStream = CreateDateGroupDescription(
                                            0,
                                            punk,
                                            punk,
                                            &GUID_67ba1597_eda6_4554_96a0_2e5a008916f7,
                                            &pv);
                    if ( KnownImplFromStream >= 0 )
                    {
                      KnownImplFromStream = IUnknown_LoadFromStream(a2, pv);
                      if ( KnownImplFromStream >= 0 )
                        KnownImplFromStream = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))pv->lpVtbl->QueryInterface)(
                                                pv,
                                                &GUID_00000000_0000_0000_c000_000000000046,
                                                &v68);
                      ((void (__fastcall *)(struct IUnknown *))pv->lpVtbl->Release)(pv);
                      if ( KnownImplFromStream >= 0 )
                      {
LABEL_109:
                        if ( v23 )
                          v37 = *(_DWORD *)v23;
                        else
                          v37 = 0;
                        v58 = v37;
                        v59 = g_pfn_DSA_GetItemPtr(v23, 0);
                        if ( v24 )
                          v38 = *(_DWORD *)v24;
                        else
                          v38 = 0;
                        v60 = v38;
                        v39 = g_pfn_DSA_GetItemPtr(v24, 0);
                        v40 = v72;
                        v61 = v39;
                        ppv = 0;
                        KnownImplFromStream = CAutoList::s_CreateInstance(
                                                (const struct AUTOLISTINIT *)&v46,
                                                *((struct ICompositionProcessor **)v72 + 2),
                                                &GUID_607c87f7_0696_4558_a368_de5e59cfe456,
                                                &ppv);
                        if ( KnownImplFromStream >= 0 )
                        {
                          punk[0] = 0;
                          KnownImplFromStream = (**(__int64 (__fastcall ***)(void *, GUID *, IUnknown **))ppv)(
                                                  ppv,
                                                  &GUID_607c87f7_0696_4558_a368_de5e59cfe456,
                                                  punk);
                          if ( KnownImplFromStream >= 0 )
                          {
                            IUnknown_Set((IUnknown **)v40 + 3, punk[0]);
                            ((void (__fastcall *)(IUnknown *))punk[0]->lpVtbl->Release)(punk[0]);
                          }
                          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
                        }
                      }
                    }
                  }
                }
              }
              if ( v23 )
                DSA_Destroy(v23);
              if ( v24 )
                DSA_Destroy(v24);
            }
            goto LABEL_121;
          }
          LODWORD(v25[2].lpVtbl) = 1;
          v25->lpVtbl = (struct IUnknownVtbl *)&CColumnList::`vftable'{for `IColumnList'};
          v25[1].lpVtbl = (struct IUnknownVtbl *)&CColumnList::`vftable'{for `IPersistStream'};
          v25[3].lpVtbl = 0;
          _InterlockedIncrement(&g_cDllRef);
          KnownImplFromStream = IUnknown_LoadFromStream(a2, v25);
          if ( KnownImplFromStream >= 0 )
          {
            v27.lpVtbl = v26->lpVtbl;
            punk[0] = v26;
            ((void (__fastcall *)(IUnknown *))v27.lpVtbl->AddRef)(v26);
          }
          CColumnList::Release((CColumnList *)v26);
          if ( KnownImplFromStream >= 0 )
          {
LABEL_62:
            LODWORD(pv) = 0;
            KnownImplFromStream = IStream_Read(a2, &pv, 4u);
            if ( KnownImplFromStream >= 0 )
            {
              v28 = 0;
              v29 = g_pfn_DSA_Create(20, (int)pv + 1);
              KnownImplFromStream = v29 == 0 ? 0x8007000E : 0;
              if ( (_DWORD)pv )
              {
                while ( KnownImplFromStream >= 0 )
                {
                  LODWORD(v70) = 0;
                  pitem = 0;
                  KnownImplFromStream = IStream_Read(a2, &pitem, 0x14u);
                  if ( KnownImplFromStream >= 0 )
                  {
                    KnownImplFromStream = 0;
                    if ( DSA_InsertItem(v29, 0x7FFFFFFF, &pitem) == -1 )
                      KnownImplFromStream = -2147024882;
                  }
                  if ( ++v5 >= (unsigned int)pv )
                  {
                    v5 = 0;
                    goto LABEL_64;
                  }
                }
                v5 = 0;
              }
              else
              {
LABEL_64:
                if ( KnownImplFromStream >= 0 )
                  v28 = v29;
              }
              v30 = 0;
              if ( KnownImplFromStream < 0 )
                v30 = v29;
              if ( v30 )
                DSA_Destroy(v30);
              if ( KnownImplFromStream >= 0 )
              {
                LODWORD(pv) = 0;
                KnownImplFromStream = IStream_Read(a2, &pv, 4u);
                if ( KnownImplFromStream >= 0 )
                {
                  v31 = g_pfn_DSA_Create(24, (int)pv + 1);
                  KnownImplFromStream = v31 == 0 ? 0x8007000E : 0;
                  if ( (_DWORD)pv )
                  {
                    v32 = 0;
                    while ( KnownImplFromStream >= 0 )
                    {
                      v70 = 0;
                      pitem = 0;
                      KnownImplFromStream = IStream_Read(a2, &pitem, 0x18u);
                      if ( KnownImplFromStream >= 0 )
                      {
                        KnownImplFromStream = 0;
                        if ( DSA_InsertItem(v31, 0x7FFFFFFF, &pitem) == -1 )
                          KnownImplFromStream = -2147024882;
                      }
                      if ( ++v32 >= (unsigned int)pv )
                        goto LABEL_79;
                    }
                  }
                  else
                  {
LABEL_79:
                    if ( KnownImplFromStream >= 0 )
                      v24 = v31;
                  }
                  v33 = 0;
                  if ( KnownImplFromStream < 0 )
                    v33 = v31;
                  if ( v33 )
                    DSA_Destroy(v33);
                }
                if ( KnownImplFromStream < 0 )
                {
                  v23 = 0;
                  if ( v28 )
                    DSA_Destroy(v28);
                }
                else
                {
                  if ( punk[0] )
                  {
                    v62 = punk[0];
                    ((void (__fastcall *)(IUnknown *))punk[0]->lpVtbl->AddRef)(punk[0]);
                  }
                  v23 = v28;
                }
              }
            }
            if ( punk[0] )
              ((void (__fastcall *)(IUnknown *))punk[0]->lpVtbl->Release)(punk[0]);
            goto LABEL_93;
          }
        }
LABEL_121:
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v71[0] + 16LL))(v71[0]);
LABEL_122:
        ClearAutoListInit((struct AUTOLISTINIT *)&v46);
      }
    }
  }
LABEL_6:
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v6, (unsigned int)AutoLists_LoadFromStream_Stop, v7, 1, (__int64)&v72);
  return (unsigned int)KnownImplFromStream;
}

```

## disassembly

```asm
0x18000eb40  mov     [rsp-8+arg_10], rbx
0x18000eb45  push    rbp
0x18000eb46  push    rsi
0x18000eb47  push    rdi
0x18000eb48  push    r12
0x18000eb4a  push    r13
0x18000eb4c  push    r14
0x18000eb4e  push    r15
0x18000eb50  lea     rbp, [rsp-40h]
0x18000eb55  sub     rsp, 140h
0x18000eb5c  mov     rax, cs:__security_cookie
0x18000eb63  xor     rax, rsp
0x18000eb66  mov     [rbp+70h+var_38], rax
0x18000eb6a  mov     r14d, 1
0x18000eb70  mov     [rbp+70h+var_48], rcx
0x18000eb74  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, r14b
0x18000eb7b  mov     r12, rdx
0x18000eb7e  mov     rbx, rcx
0x18000eb81  jnz     loc_18000F634
0x18000eb87  xor     r13d, r13d
0x18000eb8a  lea     rdx, [rsp+170h+pv]; pv
0x18000eb8f  mov     rcx, r12; pstm
0x18000eb92  mov     dword ptr [rsp+170h+pv], r13d
0x18000eb97  lea     esi, [r13+4]
0x18000eb9b  mov     r8d, esi; cb
0x18000eb9e  call    cs:__imp_IStream_Read
0x18000eba4  mov     r15d, eax
0x18000eba7  test    eax, eax
0x18000eba9  js      short loc_18000EBBB
0x18000ebab  cmp     dword ptr [rsp+170h+pv], 80000006h
0x18000ebb3  jz      short loc_18000EBF2
0x18000ebb5  mov     r15d, 80070057h
0x18000ebbb  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, r14b
0x18000ebc2  jnz     loc_18000F651
0x18000ebc8  mov     eax, r15d
0x18000ebcb  mov     rcx, [rbp+70h+var_38]
0x18000ebcf  xor     rcx, rsp; StackCookie
0x18000ebd2  call    __security_check_cookie
0x18000ebd7  mov     rbx, [rsp+170h+arg_10]
0x18000ebdf  add     rsp, 140h
0x18000ebe6  pop     r15
0x18000ebe8  pop     r14
0x18000ebea  pop     r13
0x18000ebec  pop     r12
0x18000ebee  pop     rdi
0x18000ebef  pop     rsi
0x18000ebf0  pop     rbp
0x18000ebf1  retn
0x18000ebf2  xor     edx, edx; Val
0x18000ebf4  lea     rcx, [rsp+170h+var_120]; void *
0x18000ebf9  mov     r8d, 0B0h; Size
0x18000ebff  call    memset_0
0x18000ec04  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_Invalid.Data1
0x18000ec0b  or      eax, 0FFFFFFFFh
0x18000ec0e  mov     [rbp+70h+var_98], r13
0x18000ec12  mov     r8d, esi; cb
0x18000ec15  mov     [rsp+170h+var_F4], eax
0x18000ec19  lea     rdx, [rsp+170h+pv]; pv
0x18000ec1e  mov     [rbp+70h+var_F0], eax
0x18000ec21  mov     rcx, r12; pstm
0x18000ec24  mov     dword ptr [rsp+170h+pv], r13d
0x18000ec29  movdqu  [rsp+170h+var_110], xmm0
0x18000ec2f  call    cs:__imp_IStream_Read
0x18000ec35  mov     r15d, eax
0x18000ec38  test    eax, eax
0x18000ec3a  js      loc_18000EBBB
0x18000ec40  cmp     dword ptr [rsp+170h+pv], r13d
0x18000ec45  jnz     loc_18000F773
0x18000ec4b  mov     r8d, esi; cb
0x18000ec4e  mov     [rbp+70h+var_A0], r13
0x18000ec52  lea     rdx, [rsp+170h+pv]; pv
0x18000ec57  mov     dword ptr [rsp+170h+pv], r13d
0x18000ec5c  mov     rcx, r12; pstm
0x18000ec5f  call    cs:__imp_IStream_Read
0x18000ec65  mov     r15d, eax
0x18000ec68  test    eax, eax
0x18000ec6a  js      loc_18000F5C9
0x18000ec70  cmp     dword ptr [rsp+170h+pv], r13d
0x18000ec75  jz      loc_18000EE49
0x18000ec7b  mov     rdi, [rbx+10h]
0x18000ec7f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ec86  mov     ecx, 78h ; 'x'; unsigned __int64
0x18000ec8b  mov     [rsp+170h+ppv], r13
0x18000ec90  mov     r15d, 8007000Eh
0x18000ec96  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ec9b  mov     [rbp+70h+var_58], rax
0x18000ec9f  mov     rbx, rax
0x18000eca2  test    rax, rax
0x18000eca5  jz      loc_18000F5C9
0x18000ecab  lea     rax, ??_7CScope@@6BIRootScope@@@; const CScope::`vftable'{for `IRootScope'}
0x18000ecb2  mov     [rbx], rax
0x18000ecb5  lea     rax, ??_7CScope@@6BIBindScopeDialog@@@; const CScope::`vftable'{for `IBindScopeDialog'}
0x18000ecbc  mov     [rbx+8], rax
0x18000ecc0  lea     rax, ??_7CScope@@6BIScopeResolver@@@; const CScope::`vftable'{for `IScopeResolver'}
0x18000ecc7  mov     [rbx+10h], rax
0x18000eccb  lea     rax, ??_7CScope@@6BIPersistStream@@@; const CScope::`vftable'{for `IPersistStream'}
0x18000ecd2  mov     [rbx+18h], rax
0x18000ecd6  lea     rax, ??_7CScope@@6BIPersistXML@@@; const CScope::`vftable'{for `IPersistXML'}
0x18000ecdd  mov     [rbx+20h], rax
0x18000ece1  lea     rax, ??_7CScope@@6BIObjectWithCachedState@@@; const CScope::`vftable'{for `IObjectWithCachedState'}
0x18000ece8  mov     [rbx+28h], rax
0x18000ecec  xor     eax, eax
0x18000ecee  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000ecf5  mov     [rbx+44h], r14d
0x18000ecf9  movdqu  xmmword ptr [rbx+34h], xmm0
0x18000ecfe  mov     [rbx+48h], r13
0x18000ed02  mov     [rbx+50h], r13
0x18000ed06  mov     [rbx+60h], rdi
0x18000ed0a  mov     [rbx+68h], rax
0x18000ed0e  mov     [rbx+70h], r14d
0x18000ed12  lock add cs:?g_cDllRef@@3JA, r14d; long g_cDllRef
0x18000ed1a  mov     rcx, [rbx+60h]
0x18000ed1e  mov     [rbx+68h], r13
0x18000ed22  test    rcx, rcx
0x18000ed25  jnz     loc_18000F66E
0x18000ed2b  test    rbx, rbx
0x18000ed2e  jz      loc_18000F5C9
0x18000ed34  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ed3b  mov     [rbx+58h], r13
0x18000ed3f  mov     ecx, 228h; unsigned __int64
0x18000ed44  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ed49  test    rax, rax
0x18000ed4c  jz      loc_18000F765
0x18000ed52  mov     [rax], r14d
0x18000ed55  mov     [rax+18h], r13
0x18000ed59  mov     [rbx+58h], rax
0x18000ed5d  lock add [rax], r14d
0x18000ed61  mov     rcx, rax; this
0x18000ed64  call    ?Release@CScopeTreeNode@@QEAAXXZ; CScopeTreeNode::Release(void)
0x18000ed69  mov     rdi, rbx
0x18000ed6c  lock add [rbx+70h], r14d
0x18000ed71  mov     esi, r13d
0x18000ed74  mov     r15d, r13d
0x18000ed77  mov     rcx, rbx; this
0x18000ed7a  call    ?Release@CScope@@UEAAKXZ; CScope::Release(void)
0x18000ed7f  test    esi, esi
0x18000ed81  js      loc_18000F5C9
0x18000ed87  lea     r9, [rsp+170h+ppv]; ppv
0x18000ed8c  mov     rcx, rdi; that
0x18000ed8f  lea     r8, _GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798; riid
0x18000ed96  lea     rdx, stru_1800EE140; pqit
0x18000ed9d  call    cs:__imp_QISearch
0x18000eda3  mov     rcx, rdi; this
0x18000eda6  mov     r15d, eax
0x18000eda9  call    ?Release@CScope@@UEAAKXZ; CScope::Release(void)
0x18000edae  test    r15d, r15d
0x18000edb1  js      loc_18000F5C9
0x18000edb7  mov     rcx, [rsp+170h+ppv]
0x18000edbc  lea     r8, [rsp+170h+punk]
0x18000edc1  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x18000edc8  mov     [rsp+170h+punk], r13
0x18000edcd  mov     rax, [rcx]
0x18000edd0  mov     rax, [rax]
0x18000edd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edd8  mov     r15d, eax
0x18000eddb  test    eax, eax
0x18000eddd  js      short loc_18000EE2A
0x18000eddf  mov     rcx, [rsp+170h+punk]
0x18000ede4  mov     rdx, r12
0x18000ede7  mov     rax, [rcx]
0x18000edea  mov     rax, [rax+28h]
0x18000edee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edf3  mov     rcx, [rsp+170h+punk]
0x18000edf8  mov     r15d, eax
0x18000edfb  mov     rax, [rcx]
0x18000edfe  mov     rax, [rax+10h]
0x18000ee02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee07  test    r15d, r15d
0x18000ee0a  js      short loc_18000EE2A
0x18000ee0c  mov     rcx, [rsp+170h+ppv]
0x18000ee11  lea     r8, [rbp+70h+var_A0]
0x18000ee15  lea     rdx, _GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798
0x18000ee1c  mov     rax, [rcx]
0x18000ee1f  mov     rax, [rax]
0x18000ee22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee27  mov     r15d, eax
0x18000ee2a  mov     rcx, [rsp+170h+ppv]
0x18000ee2f  mov     rax, [rcx]
0x18000ee32  mov     rax, [rax+10h]
0x18000ee36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee3b  test    r15d, r15d
0x18000ee3e  js      loc_18000F5C9
0x18000ee44  mov     esi, 4
0x18000ee49  mov     r8d, esi; cb
0x18000ee4c  mov     [rbp+70h+var_A8], r13
0x18000ee50  lea     rdx, [rsp+170h+pv]; pv
0x18000ee55  mov     dword ptr [rsp+170h+pv], r13d
0x18000ee5a  mov     rcx, r12; pstm
0x18000ee5d  call    cs:__imp_IStream_Read
0x18000ee63  mov     r15d, eax
0x18000ee66  test    eax, eax
0x18000ee68  js      loc_18000F5C9
0x18000ee6e  cmp     dword ptr [rsp+170h+pv], r13d
0x18000ee73  jz      short loc_18000EE93
0x18000ee75  lea     r8, [rbp+70h+var_A8]
0x18000ee79  mov     rcx, r12
0x18000ee7c  lea     rdx, _GUID_d18f09e2_81c2_4217_a295_43b66fa4e495
0x18000ee83  call    CreateVisibleInList
0x18000ee88  mov     r15d, eax
0x18000ee8b  test    eax, eax
0x18000ee8d  js      loc_18000F5C9
0x18000ee93  mov     r8d, esi; cb
0x18000ee96  mov     [rbp+70h+var_90], r13
0x18000ee9a  lea     rdx, [rsp+170h+pv]; pv
0x18000ee9f  mov     dword ptr [rsp+170h+pv], r13d
0x18000eea4  mov     rcx, r12; pstm
0x18000eea7  call    cs:__imp_IStream_Read
0x18000eead  mov     r15d, eax
0x18000eeb0  test    eax, eax
0x18000eeb2  js      loc_18000F5C9
0x18000eeb8  cmp     dword ptr [rsp+170h+pv], r13d
0x18000eebd  jz      short loc_18000EF2D
0x18000eebf  lea     rax, [rsp+170h+punk]
0x18000eec4  mov     [rbp+70h+var_90], r13
0x18000eec8  lea     r9, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8; struct _GUID *
0x18000eecf  mov     [rsp+170h+var_150], rax; void **
0x18000eed4  mov     r8d, 3; unsigned int
0x18000eeda  mov     [rsp+170h+punk], r13
0x18000eedf  lea     rdx, off_1800EB310; struct _GUID **
0x18000eee6  mov     rcx, r12; struct IStream *
0x18000eee9  call    ?IUnknown_LoadKnownImplFromStream@@YAJPEAUIStream@@PEBQEBU_GUID@@IAEBU2@PEAPEAX@Z; IUnknown_LoadKnownImplFromStream(IStream *,_GUID const * const *,uint,_GUID const &,void * *)
0x18000eeee  mov     r15d, eax
0x18000eef1  test    eax, eax
0x18000eef3  js      short loc_18000EF24
0x18000eef5  mov     rcx, [rsp+170h+punk]
0x18000eefa  lea     r8, [rbp+70h+var_90]
0x18000eefe  lea     rdx, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x18000ef05  mov     rax, [rcx]
0x18000ef08  mov     rax, [rax]
0x18000ef0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef10  mov     rcx, [rsp+170h+punk]
0x18000ef15  mov     r15d, eax
0x18000ef18  mov     rax, [rcx]
0x18000ef1b  mov     rax, [rax+10h]
0x18000ef1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef24  test    r15d, r15d
0x18000ef27  js      loc_18000F5C9
0x18000ef2d  mov     r8d, esi; cb
0x18000ef30  lea     rdx, [rsp+170h+var_100]; pv
0x18000ef35  mov     rcx, r12; pstm
0x18000ef38  call    cs:__imp_IStream_Read
0x18000ef3e  mov     r15d, eax
0x18000ef41  test    eax, eax
0x18000ef43  js      loc_18000F5C9
0x18000ef49  mov     r8d, esi; cb
0x18000ef4c  lea     rdx, [rsp+170h+var_FC]; pv
0x18000ef51  mov     rcx, r12; pstm
0x18000ef54  call    cs:__imp_IStream_Read
0x18000ef5a  mov     r15d, eax
0x18000ef5d  test    eax, eax
0x18000ef5f  js      loc_18000F5C9
0x18000ef65  mov     r8d, esi; cb
0x18000ef68  lea     rdx, [rsp+170h+var_F8]; pv
0x18000ef6d  mov     rcx, r12; pstm
0x18000ef70  call    cs:__imp_IStream_Read
0x18000ef76  mov     r15d, eax
0x18000ef79  test    eax, eax
0x18000ef7b  js      loc_18000F5C9
0x18000ef81  mov     r8d, 14h; cb
0x18000ef87  mov     [rsp+170h+ppsz], r13
0x18000ef8c  lea     rdx, [rbp+70h+var_E4]; pv
0x18000ef90  mov     [rsp+170h+var_120], r13
0x18000ef95  mov     rcx, r12; pstm
0x18000ef98  call    cs:__imp_IStream_Read
0x18000ef9e  mov     r15d, eax
0x18000efa1  test    eax, eax
0x18000efa3  js      loc_18000F0A9
0x18000efa9  mov     r8d, esi; cb
0x18000efac  lea     rdx, [rbp+70h+var_D0]; pv
0x18000efb0  mov     rcx, r12; pstm
0x18000efb3  call    cs:__imp_IStream_Read
0x18000efb9  mov     r15d, eax
0x18000efbc  test    eax, eax
0x18000efbe  js      loc_18000F0A9
0x18000efc4  mov     r8d, 10h; cb
0x18000efca  lea     rdx, [rsp+170h+var_110]; pv
0x18000efcf  mov     rcx, r12; pstm
0x18000efd2  call    cs:__imp_IStream_Read
0x18000efd8  mov     r15d, eax
0x18000efdb  test    eax, eax
0x18000efdd  js      loc_18000F0A9
0x18000efe3  mov     r8d, esi; cb
0x18000efe6  lea     rdx, [rsp+170h+var_F4]; pv
0x18000efeb  mov     rcx, r12; pstm
0x18000efee  call    cs:__imp_IStream_Read
0x18000eff4  mov     r15d, eax
0x18000eff7  test    eax, eax
0x18000eff9  js      loc_18000F0A9
0x18000efff  mov     r8d, esi; cb
0x18000f002  lea     rdx, [rbp+70h+var_F0]; pv
0x18000f006  mov     rcx, r12; pstm
0x18000f009  call    cs:__imp_IStream_Read
0x18000f00f  mov     r15d, eax
0x18000f012  test    eax, eax
0x18000f014  js      loc_18000F0A9
0x18000f01a  mov     r8d, esi; cb
0x18000f01d  lea     rdx, [rbp+70h+var_EC]; pv
0x18000f021  mov     rcx, r12; pstm
0x18000f024  call    cs:__imp_IStream_Read
0x18000f02a  mov     r15d, eax
  ... truncated ...
```
