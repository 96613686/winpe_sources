# CNscTree::GetNextItem(IShellItem *,NSTCGNI,IShellItem * *)

- ea: `0x18002b8f0`
- end: `0x18002c1c8`
- name: `?GetNextItem@CNscTree@@UEAAJPEAUIShellItem@@W4NSTCGNI@@PEAPEAU2@@Z`
- size: `2264`
- prototype: `__int64 __fastcall(CNscTree *__hidden this, struct IShellItem *, enum NSTCGNI, struct IShellItem **)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800218ac`
- `0x18002a3c4`
- `0x18002aa70`
- `0x18002b8f0`
- `0x18002c398`
- `0x18002c854`
- `0x18002cb14`
- `0x1800340a0`
- `0x18014066e`
- `0x1801406d4`
- `0x180210010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002c04f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002c128`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002c04f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002c128`
- `SHCORE!IUnknown_Set` at `0x18002b957`
- `SHCORE!IUnknown_Set` at `0x18002bd00`
- `SHCORE!IUnknown_Set` at `0x18002bee1`
- `SHCORE!IUnknown_Set` at `0x18002b957`
- `SHCORE!IUnknown_Set` at `0x18002bd00`
- `SHCORE!IUnknown_Set` at `0x18002bee1`
- `SHELL32!SHCreateItemWithParent` at `0x18002bccc`
- `SHELL32!SHCreateItemWithParent` at `0x18002bccc`
- `SHELL32!SHGetIDListFromObject` at `0x18002bb38`
- `SHELL32!SHGetIDListFromObject` at `0x18002bb38`
- `SHELL32!SHCreateItemFromIDList` at `0x18002c0a8`
- `SHELL32!SHCreateItemFromIDList` at `0x18002c0a8`
- `SHELL32!SHSetTemporaryPropertyForItem` at `0x18002bd47`
- `SHELL32!SHSetTemporaryPropertyForItem` at `0x18002bd47`
- `SHELL32!SHGetTemporaryPropertyForItem` at `0x18002baa5`
- `SHELL32!SHGetTemporaryPropertyForItem` at `0x18002baa5`
- `SHELL32!__imp_ILClone` at `0x18002b964`
- `SHELL32!__imp_ILClone` at `0x18002b964`
- `SHELL32!__imp_ILCombine` at `0x18002be81`
- `SHELL32!__imp_ILCombine` at `0x18002be81`
- `SHELL32!__imp_ILFree` at `0x18002b9af`
- `SHELL32!__imp_ILFree` at `0x18002ba1b`
- `SHELL32!__imp_ILFree` at `0x18002be9a`
- `SHELL32!__imp_ILFree` at `0x18002bea3`
- `SHELL32!__imp_ILFree` at `0x18002c0b3`
- `SHELL32!__imp_ILFree` at `0x18002b9af`
- `SHELL32!__imp_ILFree` at `0x18002ba1b`
- `SHELL32!__imp_ILFree` at `0x18002be9a`
- `SHELL32!__imp_ILFree` at `0x18002bea3`
- `SHELL32!__imp_ILFree` at `0x18002c0b3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002bb91`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002bd51`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002bfa7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002bfd8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002bb91`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002bd51`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002bfa7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002bfd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bb77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bf9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bfcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bb77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bf9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bfcd`
- `USER32!SendMessageW` at `0x18002bb22`
- `USER32!SendMessageW` at `0x18002bc02`
- `USER32!SendMessageW` at `0x18002bc56`
- `USER32!SendMessageW` at `0x18002bda0`
- `USER32!SendMessageW` at `0x18002bb22`
- `USER32!SendMessageW` at `0x18002bc02`
- `USER32!SendMessageW` at `0x18002bc56`
- `USER32!SendMessageW` at `0x18002bda0`
- `PROPSYS!PropVariantToBuffer` at `0x18002bad4`
- `PROPSYS!PropVariantToBuffer` at `0x18002bad4`
- `PROPSYS!InitPropVariantFromBuffer` at `0x18002bd2e`
- `PROPSYS!InitPropVariantFromBuffer` at `0x18002bd2e`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CNscTree::GetNextItem(HWND *this, IUnknown *a2, enum NSTCGNI a3, struct IShellItem **a4)
{
  HWND *v6; // r12
  HRESULT TreeItemParentFolder; // ebx
  struct _TREEITEM *v8; // rcx
  ITEMIDLIST *v9; // r15
  signed int v10; // edi
  int v11; // r12d
  IUnknown *v12; // rcx
  int v13; // edi
  struct IShellItem *v14; // rbx
  int v15; // eax
  HRESULT v16; // eax
  IUnknown *v17; // rcx
  IShellItem *v18; // rcx
  unsigned int v19; // ebx
  WPARAM v20; // r15
  LRESULT v21; // rax
  const struct _GUID *v22; // r8
  struct _TREEITEM *v23; // rdi
  __int64 *v24; // rsi
  void *v25; // rsi
  const struct _GUID *v26; // r8
  ITEMIDLIST *v28; // r14
  ITEMIDLIST *v29; // rbx
  IUnknown *v30; // rcx
  int v31; // esi
  int v32; // esi
  int v33; // esi
  int v34; // esi
  int v35; // esi
  IUnknown *v36; // rcx
  IShellItem *v37; // rcx
  IShellItem *v38; // rcx
  IShellItem *v39; // rcx
  const ITEMIDLIST *FullIDList; // rax
  ITEMIDLIST *v41; // rdi
  int v42; // esi
  unsigned int v43; // ebx
  unsigned int v44; // ebx
  unsigned int v45; // ebx
  unsigned int v46; // ebx
  unsigned int v47; // ebx
  WPARAM v48; // r8
  struct IShellItem **p_pv; // [rsp+28h] [rbp-89h]
  IUnknown *ppunk; // [rsp+38h] [rbp-79h] BYREF
  IShellItem *psi; // [rsp+40h] [rbp-71h] BYREF
  struct _TREEITEM *pv; // [rsp+48h] [rbp-69h] BYREF
  struct _TREEITEM *v53; // [rsp+50h] [rbp-61h] BYREF
  IShellFolder *psfParent; // [rsp+58h] [rbp-59h] BYREF
  IUnknown *punk; // [rsp+60h] [rbp-51h] BYREF
  LPCITEMIDLIST pidl; // [rsp+68h] [rbp-49h] BYREF
  IUnknown *v57; // [rsp+70h] [rbp-41h] BYREF
  struct IShellItem *v58; // [rsp+78h] [rbp-39h] BYREF
  PROPVARIANT ppropvar[2]; // [rsp+80h] [rbp-31h] BYREF
  void *Src; // [rsp+90h] [rbp-21h]
  LPARAM lParam[2]; // [rsp+98h] [rbp-19h] BYREF
  __int128 v62; // [rsp+A8h] [rbp-9h]
  __int128 v63; // [rsp+B8h] [rbp+7h]
  __int64 **v64; // [rsp+C8h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+110h] [rbp+5Fh]
  void *ppvItem; // [rsp+130h] [rbp+7Fh] BYREF

  ppvItem = a4;
  v6 = this;
  TreeItemParentFolder = -2147467261;
  if ( !a4 )
    return (unsigned int)TreeItemParentFolder;
  *a4 = 0;
  v8 = 0;
  v53 = 0;
  TreeItemParentFolder = -2147024809;
  if ( a2 )
  {
    v58 = 0;
    pv = 0;
    ppunk = 0;
    IUnknown_Set(&ppunk, a2);
    v9 = ILClone(&c_idlDesktop);
    v10 = v9 == 0 ? 0x8007000E : 0;
    v11 = 0;
    if ( v9 )
    {
      while ( 1 )
      {
        v12 = ppunk;
        if ( !ppunk || v11 )
          break;
        p_pv = (struct IShellItem **)&pv;
        if ( ((int (__fastcall *)(IUnknown *, _QWORD, const GUID *, GUID *))ppunk->lpVtbl[1].QueryInterface)(
               ppunk,
               0,
               &BHID_SFObject,
               &GUID_51737562_4f12_4b7a_a3a0_6e9efe465e1e) >= 0 )
        {
          v11 = 1;
        }
        else
        {
          psfParent = 0;
          v10 = ((__int64 (__fastcall *)(IUnknown *, GUID *, IShellFolder **))ppunk->lpVtbl->QueryInterface)(
                  ppunk,
                  &GUID_b3a4b685_b685_4805_99d9_5dead2873236,
                  &psfParent);
          if ( v10 >= 0 )
          {
            pidl = 0;
            v10 = ((__int64 (__fastcall *)(IShellFolder *, _QWORD, _QWORD, LPCITEMIDLIST *))psfParent->lpVtbl->EnumObjects)(
                    psfParent,
                    0,
                    0,
                    &pidl);
            if ( v10 >= 0 )
            {
              v28 = (ITEMIDLIST *)pidl;
              if ( v9 && pidl )
              {
                v29 = v9;
                v9 = ILCombine(pidl, v9);
                v10 = v9 == 0 ? 0x8007000E : 0;
                ILFree(v28);
                ILFree(v29);
              }
              else
              {
                v10 = 0;
                if ( pidl )
                {
                  v9 = (ITEMIDLIST *)pidl;
                }
                else if ( !v9 )
                {
                  v10 = -2147024809;
                }
              }
            }
            ((void (__fastcall *)(IShellFolder *))psfParent->lpVtbl->Release)(psfParent);
          }
        }
        v57 = 0;
        ((void (__fastcall *)(IUnknown *, IUnknown **))ppunk->lpVtbl[1].AddRef)(ppunk, &v57);
        IUnknown_Set(&ppunk, v57);
        v30 = v57;
        v57 = 0;
        if ( v30 )
          ((void (__fastcall *)(IUnknown *))v30->lpVtbl->Release)(v30);
        if ( v10 < 0 )
          goto LABEL_4;
      }
    }
    else
    {
LABEL_4:
      v12 = ppunk;
    }
    ppunk = 0;
    if ( v12 )
      ((void (__fastcall *)(IUnknown *))v12->lpVtbl->Release)(v12);
    if ( v11 && v10 >= 0 )
    {
      v13 = 0;
      punk = 0;
      TreeItemParentFolder = (**(__int64 (__fastcall ***)(struct _TREEITEM *, GUID *, IUnknown **))pv)(
                               pv,
                               &GUID_6a9d9026_0e6e_464c_b000_42ecc07de673,
                               &punk);
      if ( TreeItemParentFolder >= 0 )
      {
        LODWORD(psi) = 0;
        if ( ((int (__fastcall *)(IUnknown *, IShellItem **))punk->lpVtbl[1].AddRef)(punk, &psi) < 0 || (_DWORD)psi == 1 )
        {
          v13 = 1;
        }
        else
        {
          p_pv = &v58;
          TreeItemParentFolder = (*(__int64 (__fastcall **)(struct _TREEITEM *, ITEMIDLIST *, __int64, GUID *))(*(_QWORD *)pv + 24LL))(
                                   pv,
                                   v9,
                                   1,
                                   &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe);
        }
        ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
      }
      ILFree(v9);
      (*(void (__fastcall **)(struct _TREEITEM *))(*(_QWORD *)pv + 16LL))(pv);
      if ( !v13 )
      {
LABEL_16:
        if ( TreeItemParentFolder < 0 )
          return (unsigned int)TreeItemParentFolder;
        v14 = v58;
        v53 = 0;
        psi = 0;
        Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(&psi);
        v15 = ConvertItemEnumMode(FEM_NAVIGATION, v14, 1, &psi);
        TreeItemParentFolder = v15;
        if ( v15 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC9E,
            (unsigned int)"shell\\explorerframe\\nsc.cpp",
            (const char *)(unsigned int)v15,
            (int)p_pv);
          v39 = psi;
          if ( psi )
          {
            psi = 0;
            ((void (__fastcall *)(IShellItem *))v39->lpVtbl->Release)(v39);
          }
          goto LABEL_33;
        }
        LOWORD(ppropvar[0]) = 0;
        if ( SHGetTemporaryPropertyForItem(psi, &PKEY_DescriptionID, ppropvar) < 0 || !LOWORD(ppropvar[0]) )
          goto LABEL_25;
        pv = 0;
        if ( LOWORD(ppropvar[0]) != 65 )
        {
          if ( PropVariantToBuffer(ppropvar, &pv, 8u) < 0 )
            goto LABEL_25;
          goto LABEL_22;
        }
        if ( LODWORD(ppropvar[1]) )
        {
          if ( Src )
          {
            if ( LODWORD(ppropvar[1]) <= 8 )
            {
              memcpy_0(&pv, Src, LODWORD(ppropvar[1]));
              goto LABEL_22;
            }
            *(_DWORD *)_o__errno() = 34;
          }
          else
          {
            *(_DWORD *)_o__errno() = 22;
          }
          invalid_parameter_noinfo();
        }
LABEL_22:
        if ( pv )
        {
          if ( pv != (struct _TREEITEM *)-65536LL )
          {
            v62 = 0;
            v63 = 0;
            v64 = 0;
            lParam[0] = 20;
            lParam[1] = (LPARAM)pv;
            if ( (unsigned int)SendMessageW(this[22], 0x113Eu, 0, (LPARAM)lParam) )
            {
              if ( v64 )
              {
                v53 = pv;
                goto LABEL_30;
              }
            }
          }
        }
LABEL_25:
        ppunk = 0;
        v16 = SHGetIDListFromObject((IUnknown *)psi, (LPITEMIDLIST *)&ppunk);
        TreeItemParentFolder = v16;
        if ( v16 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xCB4,
            (unsigned int)"shell\\explorerframe\\nsc.cpp",
            (const char *)(unsigned int)v16,
            (int)p_pv);
          v36 = ppunk;
          ppunk = 0;
          CoTaskMemFree(v36);
          PropVariantClear(ppropvar);
          v37 = psi;
          if ( psi )
          {
            psi = 0;
            ((void (__fastcall *)(IShellItem *))v37->lpVtbl->Release)(v37);
          }
          goto LABEL_33;
        }
        v53 = CNscTree::_FindFromRoot((CNscTree *)(this - 28), 0, 0, (const struct _ITEMIDLIST_ABSOLUTE *)ppunk, 0);
        v17 = ppunk;
        ppunk = 0;
        if ( !v53 )
        {
          CoTaskMemFree(v17);
          PropVariantClear(ppropvar);
          v38 = psi;
          if ( psi )
          {
            psi = 0;
            ((void (__fastcall *)(IShellItem *))v38->lpVtbl->Release)(v38);
          }
          TreeItemParentFolder = -2147024809;
          goto LABEL_33;
        }
        CoTaskMemFree(v17);
LABEL_30:
        PropVariantClear(ppropvar);
        v18 = psi;
        if ( psi )
        {
          psi = 0;
          ((void (__fastcall *)(IShellItem *))v18->lpVtbl->Release)(v18);
        }
        TreeItemParentFolder = 0;
LABEL_33:
        ((void (__fastcall *)(struct IShellItem *))v58->lpVtbl->Release)(v58);
        if ( TreeItemParentFolder < 0 )
          return (unsigned int)TreeItemParentFolder;
        v8 = v53;
        v6 = this;
        TreeItemParentFolder = -2147024809;
        goto LABEL_35;
      }
    }
    else
    {
      ILFree(v9);
    }
    TreeItemParentFolder = ((__int64 (__fastcall *)(IUnknown *, GUID *, struct IShellItem **))a2->lpVtbl->QueryInterface)(
                             a2,
                             &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                             &v58);
    goto LABEL_16;
  }
LABEL_35:
  if ( a3 )
  {
    v31 = a3 - 1;
    if ( v31 )
    {
      v32 = v31 - 1;
      if ( v32 )
      {
        v33 = v32 - 1;
        if ( v33 )
        {
          v34 = v33 - 1;
          if ( v34 )
          {
            v35 = v34 - 1;
            if ( v35 )
            {
              v42 = v35 - 1;
              if ( v42 )
              {
                if ( v42 != 1 )
                  return (unsigned int)TreeItemParentFolder;
                v19 = 10;
              }
              else
              {
                v19 = 5;
              }
            }
            else
            {
              v19 = 4;
            }
          }
          else
          {
            v19 = 3;
          }
        }
        else
        {
          v19 = 7;
        }
      }
      else
      {
        v19 = 2;
      }
    }
    else
    {
      v19 = 6;
    }
  }
  else
  {
    v19 = 1;
  }
  v20 = v19;
  v21 = SendMessageW(v6[22], 0x110Au, v19, (LPARAM)v8);
  v23 = (struct _TREEITEM *)v21;
  if ( !v21 )
    return (unsigned int)-2147467259;
  v24 = 0;
  if ( v21 != -65536 )
  {
    v62 = 0;
    v63 = 0;
    v64 = 0;
    lParam[0] = 20;
    lParam[1] = v21;
    if ( (unsigned int)SendMessageW(v6[22], 0x113Eu, 0, (LPARAM)lParam) )
    {
      if ( v64 )
      {
        if ( (*((_BYTE *)v64 + 12) & 2) != 0 )
          v24 = v64[2];
        else
          v24 = (__int64 *)**v64;
      }
    }
  }
  if ( (*((_DWORD *)v6 + 57) & 0x400000) != 0 && !v24 )
  {
    v43 = v19 - 1;
    if ( !v43 )
      goto LABEL_120;
    v44 = v43 - 1;
    if ( !v44 )
      goto LABEL_120;
    v45 = v44 - 3;
    if ( !v45 )
    {
      v48 = 6;
      goto LABEL_49;
    }
    v46 = v45 - 1;
    if ( v46 && (v47 = v46 - 1) != 0 )
    {
      if ( v47 != 3 )
        return (unsigned int)-2147467259;
      v48 = 7;
    }
    else
    {
LABEL_120:
      v48 = v20;
    }
LABEL_49:
    v23 = (struct _TREEITEM *)SendMessageW(v6[22], 0x110Au, v48, (LPARAM)v23);
    if ( !v23 )
      return (unsigned int)-2147467259;
  }
  v53 = v23;
  v25 = ppvItem;
  *(_QWORD *)ppvItem = 0;
  pidl = 0;
  psfParent = 0;
  TreeItemParentFolder = CNscTree::_GetTreeItemParentFolder(
                           (CNscTree *)(v6 - 28),
                           v23,
                           v22,
                           (void **)&psfParent,
                           (const struct _ITEMID_CHILD **)&pidl);
  if ( TreeItemParentFolder >= 0 )
  {
    ppvItem = 0;
    TreeItemParentFolder = SHCreateItemWithParent(
                             0,
                             psfParent,
                             pidl,
                             &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                             &ppvItem);
    if ( TreeItemParentFolder >= 0
      || (FullIDList = (const ITEMIDLIST *)CNscTree::_GetFullIDList((CNscTree *)(v6 - 28), v6[22], v53),
          (v41 = (ITEMIDLIST *)FullIDList) != 0)
      && (TreeItemParentFolder = SHCreateItemFromIDList(
                                   FullIDList,
                                   &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                   &ppvItem),
          ILFree(v41),
          TreeItemParentFolder >= 0) )
    {
      punk = 0;
      TreeItemParentFolder = _ConvertToViewResultItem((IUnknown *)ppvItem, 1, v26, (void **)&punk);
      if ( TreeItemParentFolder >= 0 )
      {
        IUnknown_Set((IUnknown **)&ppvItem, punk);
        ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
        *(_OWORD *)ppropvar = 0;
        Src = 0;
        if ( InitPropVariantFromBuffer(&v53, 8u, ppropvar) >= 0 )
        {
          SHSetTemporaryPropertyForItem((IShellItem *)ppvItem, &PKEY_DescriptionID, ppropvar);
          PropVariantClear(ppropvar);
        }
        TreeItemParentFolder = (**(__int64 (__fastcall ***)(void *, GUID *, void *))ppvItem)(
                                 ppvItem,
                                 &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                 v25);
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvItem + 16LL))(ppvItem);
    }
    ((void (__fastcall *)(IShellFolder *))psfParent->lpVtbl->Release)(psfParent);
  }
  return (unsigned int)TreeItemParentFolder;
}

```

## disassembly

```asm
0x18002b8f0  mov     rax, rsp
0x18002b8f3  mov     [rax+10h], rbx
0x18002b8f7  mov     [rax+20h], r9
0x18002b8fb  mov     [rax+8], rcx
0x18002b8ff  push    rbp
0x18002b900  push    rsi
0x18002b901  push    rdi
0x18002b902  push    r12
0x18002b904  push    r13
0x18002b906  push    r14
0x18002b908  push    r15
0x18002b90a  lea     rbp, [rax-5Fh]
0x18002b90e  sub     rsp, 0D0h
0x18002b915  mov     esi, r8d
0x18002b918  mov     r13, rdx
0x18002b91b  mov     r12, rcx
0x18002b91e  mov     ebx, 80004003h
0x18002b923  xor     r14d, r14d
0x18002b926  test    r9, r9
0x18002b929  jz      loc_18002BDB7
0x18002b92f  mov     [r9], r14
0x18002b932  mov     ecx, r14d
0x18002b935  mov     [rbp+57h+var_B8], rcx
0x18002b939  mov     ebx, 80070057h
0x18002b93e  test    rdx, rdx
0x18002b941  jz      loc_18002BBDA
0x18002b947  mov     [rbp+57h+var_90], r14
0x18002b94b  mov     [rbp+57h+pv], r14
0x18002b94f  mov     [rbp+57h+ppunk], r14
0x18002b953  lea     rcx, [rbp+57h+ppunk]; ppunk
0x18002b957  call    cs:__imp_IUnknown_Set
0x18002b95d  lea     rcx, c_idlDesktop; pidl
0x18002b964  call    cs:__imp_ILClone
0x18002b96a  mov     r15, rax
0x18002b96d  neg     rax
0x18002b970  sbb     edi, edi
0x18002b972  not     edi
0x18002b974  and     edi, 8007000Eh
0x18002b97a  mov     r12d, r14d
0x18002b97d  test    r15, r15
0x18002b980  jnz     loc_18002BDD4
0x18002b986  mov     rcx, [rbp+57h+ppunk]
0x18002b98a  mov     [rbp+57h+ppunk], r14
0x18002b98e  test    rcx, rcx
0x18002b991  jz      short loc_18002B99F
0x18002b993  mov     rax, [rcx]
0x18002b996  mov     rax, [rax+10h]
0x18002b99a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b99f  test    r12d, r12d
0x18002b9a2  jz      loc_18002BF42
0x18002b9a8  test    edi, edi
0x18002b9aa  jns     short loc_18002B9BC
0x18002b9ac  mov     rcx, r15; pidl
0x18002b9af  call    cs:__imp_ILFree
0x18002b9b5  mov     r15, r14
0x18002b9b8  test    edi, edi
0x18002b9ba  js      short loc_18002BA35
0x18002b9bc  mov     edi, r14d
0x18002b9bf  mov     [rbp+57h+punk], r14
0x18002b9c3  mov     rcx, [rbp+57h+pv]
0x18002b9c7  mov     rax, [rcx]
0x18002b9ca  lea     r8, [rbp+57h+punk]
0x18002b9ce  lea     rdx, _GUID_6a9d9026_0e6e_464c_b000_42ecc07de673
0x18002b9d5  mov     rax, [rax]
0x18002b9d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9dd  mov     ebx, eax
0x18002b9df  test    eax, eax
0x18002b9e1  js      short loc_18002BA18
0x18002b9e3  mov     dword ptr [rbp+57h+psi], r14d
0x18002b9e7  mov     rcx, [rbp+57h+punk]
0x18002b9eb  mov     rax, [rcx]
0x18002b9ee  lea     rdx, [rbp+57h+psi]
0x18002b9f2  mov     rax, [rax+20h]
0x18002b9f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9fb  test    eax, eax
0x18002b9fd  jns     loc_18002C0EE
0x18002ba03  mov     edi, 1
0x18002ba08  mov     rcx, [rbp+57h+punk]
0x18002ba0c  mov     rax, [rcx]
0x18002ba0f  mov     rax, [rax+10h]
0x18002ba13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba18  mov     rcx, r15; pidl
0x18002ba1b  call    cs:__imp_ILFree
0x18002ba21  mov     rcx, [rbp+57h+pv]
0x18002ba25  mov     rax, [rcx]
0x18002ba28  mov     rax, [rax+10h]
0x18002ba2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba31  test    edi, edi
0x18002ba33  jz      short loc_18002BA51
0x18002ba35  mov     rax, [r13+0]
0x18002ba39  lea     r8, [rbp+57h+var_90]
0x18002ba3d  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18002ba44  mov     rcx, r13
0x18002ba47  mov     rax, [rax]
0x18002ba4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba4f  mov     ebx, eax
0x18002ba51  test    ebx, ebx
0x18002ba53  js      loc_18002BDB7
0x18002ba59  mov     rbx, [rbp+57h+var_90]
0x18002ba5d  mov     [rbp+57h+var_B8], r14
0x18002ba61  mov     [rbp+57h+psi], r14
0x18002ba65  lea     rcx, [rbp+57h+psi]
0x18002ba69  call    ?InternalRelease@?$ComPtr@UIKnownFolderProperties@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(void)
0x18002ba6e  lea     r9, [rbp+57h+psi]; struct IShellItem **
0x18002ba72  mov     r8d, 1; int
0x18002ba78  mov     rdx, rbx; struct IShellItem *
0x18002ba7b  mov     ecx, r8d; enum FOLDER_ENUM_MODE
0x18002ba7e  call    ?ConvertItemEnumMode@@YAJW4FOLDER_ENUM_MODE@@PEAUIShellItem@@HPEAPEAU2@@Z; ConvertItemEnumMode(FOLDER_ENUM_MODE,IShellItem *,int,IShellItem * *)
0x18002ba83  mov     ebx, eax
0x18002ba85  test    eax, eax
0x18002ba87  js      loc_18002C003
0x18002ba8d  mov     rdi, [rbp+57h+arg_0]
0x18002ba91  mov     word ptr [rbp+57h+ppropvar], r14w
0x18002ba96  lea     r8, [rbp+57h+ppropvar]; ppropvar
0x18002ba9a  lea     rdx, PKEY_DescriptionID; propkey
0x18002baa1  mov     rcx, [rbp+57h+psi]; psi
0x18002baa5  call    cs:__imp_SHGetTemporaryPropertyForItem
0x18002baab  test    eax, eax
0x18002baad  js      short loc_18002BB2C
0x18002baaf  movzx   eax, word ptr [rbp+57h+ppropvar]
0x18002bab3  test    ax, ax
0x18002bab6  jz      short loc_18002BB2C
0x18002bab8  mov     [rbp+57h+pv], r14
0x18002babc  cmp     ax, 41h ; 'A'
0x18002bac0  jz      loc_18002C03B
0x18002bac6  mov     r8d, 8; cb
0x18002bacc  lea     rdx, [rbp+57h+pv]; pv
0x18002bad0  lea     rcx, [rbp+57h+ppropvar]; propvar
0x18002bad4  call    cs:__imp_PropVariantToBuffer
0x18002bada  test    eax, eax
0x18002badc  js      short loc_18002BB2C
0x18002bade  mov     rax, [rbp+57h+pv]
0x18002bae2  test    rax, rax
0x18002bae5  jz      short loc_18002BB2C
0x18002bae7  cmp     rax, 0FFFFFFFFFFFF0000h
0x18002baed  jz      short loc_18002BB2C
0x18002baef  xorps   xmm0, xmm0
0x18002baf2  xor     ecx, ecx
0x18002baf4  movups  xmmword ptr [rbp+57h+lParam], xmm0
0x18002baf8  movups  [rbp+57h+var_60], xmm0
0x18002bafc  movups  [rbp+57h+var_50], xmm0
0x18002bb00  mov     [rbp+57h+var_40], rcx
0x18002bb04  mov     dword ptr [rbp+57h+lParam], 14h
0x18002bb0b  mov     [rbp+57h+lParam+8], rax
0x18002bb0f  lea     r9, [rbp+57h+lParam]; lParam
0x18002bb13  xor     r8d, r8d; wParam
0x18002bb16  mov     edx, 113Eh; Msg
0x18002bb1b  mov     rcx, [rdi+0B0h]; hWnd
0x18002bb22  call    cs:__imp_SendMessageW
0x18002bb28  test    eax, eax
0x18002bb2a  jnz     short loc_18002BB7F
0x18002bb2c  mov     [rbp+57h+ppunk], r14
0x18002bb30  lea     rdx, [rbp+57h+ppunk]; ppidl
0x18002bb34  mov     rcx, [rbp+57h+psi]; punk
0x18002bb38  call    cs:__imp_SHGetIDListFromObject
0x18002bb3e  mov     ebx, eax
0x18002bb40  test    eax, eax
0x18002bb42  js      loc_18002BF7B
0x18002bb48  mov     [rsp+20h], r14d; int
0x18002bb4d  mov     r9, [rbp+57h+ppunk]; struct _ITEMIDLIST_ABSOLUTE *
0x18002bb51  xor     r8d, r8d; struct _ITEMIDLIST_ABSOLUTE *
0x18002bb54  xor     edx, edx; struct _TREEITEM *
0x18002bb56  lea     rcx, [rdi-0E0h]; this
0x18002bb5d  call    ?_FindFromRoot@CNscTree@@AEAAPEAU_TREEITEM@@PEAU2@PEBU_ITEMIDLIST_ABSOLUTE@@1H@Z; CNscTree::_FindFromRoot(_TREEITEM *,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *,int)
0x18002bb62  mov     [rbp+57h+var_B8], rax
0x18002bb66  mov     rcx, [rbp+57h+ppunk]; pv
0x18002bb6a  mov     [rbp+57h+ppunk], r14
0x18002bb6e  test    rax, rax
0x18002bb71  jz      loc_18002BFCD
0x18002bb77  call    cs:__imp_CoTaskMemFree
0x18002bb7d  jmp     short loc_18002BB8D
0x18002bb7f  cmp     [rbp+57h+var_40], r14
0x18002bb83  jz      short loc_18002BB2C
0x18002bb85  mov     rax, [rbp+57h+pv]
0x18002bb89  mov     [rbp+57h+var_B8], rax
0x18002bb8d  lea     rcx, [rbp+57h+ppropvar]; pvar
0x18002bb91  call    cs:__imp_PropVariantClear
0x18002bb97  nop
0x18002bb98  mov     rcx, [rbp+57h+psi]
0x18002bb9c  test    rcx, rcx
0x18002bb9f  jz      short loc_18002BBB2
0x18002bba1  mov     [rbp+57h+psi], r14
0x18002bba5  mov     rax, [rcx]
0x18002bba8  mov     rax, [rax+10h]
0x18002bbac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbb1  nop
0x18002bbb2  mov     ebx, r14d
0x18002bbb5  mov     rcx, [rbp+57h+var_90]
0x18002bbb9  mov     rax, [rcx]
0x18002bbbc  mov     rax, [rax+10h]
0x18002bbc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbc5  test    ebx, ebx
0x18002bbc7  js      loc_18002BDB7
0x18002bbcd  mov     rcx, [rbp+57h+var_B8]
0x18002bbd1  mov     r12, [rbp+57h+arg_0]
0x18002bbd5  mov     ebx, 80070057h
0x18002bbda  test    esi, esi
0x18002bbdc  jnz     loc_18002BF0D
0x18002bbe2  lea     ebx, [rsi+1]
0x18002bbe5  lea     r14, [r12-0E0h]
0x18002bbed  mov     r15d, ebx
0x18002bbf0  mov     r9, rcx; lParam
0x18002bbf3  mov     r8d, ebx; wParam
0x18002bbf6  mov     edx, 110Ah; Msg
0x18002bbfb  mov     rcx, [r14+190h]; hWnd
0x18002bc02  call    cs:__imp_SendMessageW
0x18002bc08  mov     rdi, rax
0x18002bc0b  xor     r13d, r13d
0x18002bc0e  test    rax, rax
0x18002bc11  jz      loc_18002BDB2
0x18002bc17  mov     esi, r13d
0x18002bc1a  cmp     rax, 0FFFFFFFFFFFF0000h
0x18002bc20  jz      short loc_18002BC64
0x18002bc22  xorps   xmm0, xmm0
0x18002bc25  xor     eax, eax
0x18002bc27  movups  xmmword ptr [rbp+57h+lParam], xmm0
0x18002bc2b  movups  [rbp+57h+var_60], xmm0
0x18002bc2f  movups  [rbp+57h+var_50], xmm0
0x18002bc33  mov     [rbp+57h+var_40], rax
0x18002bc37  mov     dword ptr [rbp+57h+lParam], 14h
0x18002bc3e  mov     [rbp+57h+lParam+8], rdi
0x18002bc42  lea     r9, [rbp+57h+lParam]; lParam
0x18002bc46  xor     r8d, r8d; wParam
0x18002bc49  mov     edx, 113Eh; Msg
0x18002bc4e  mov     rcx, [r12+0B0h]; hWnd
0x18002bc56  call    cs:__imp_SendMessageW
0x18002bc5c  test    eax, eax
0x18002bc5e  jnz     loc_18002BF54
0x18002bc64  test    dword ptr [r12+0E4h], 400000h
0x18002bc70  jnz     loc_18002C181
0x18002bc76  mov     [rbp+57h+var_B8], rdi
0x18002bc7a  mov     rsi, [rbp+57h+ppvItem]
0x18002bc7e  mov     [rsi], r13
0x18002bc81  mov     [rbp+57h+pidl], r13
0x18002bc85  mov     [rbp+57h+psfParent], r13
0x18002bc89  lea     rax, [rbp+57h+pidl]
0x18002bc8d  mov     [rsp+20h], rax; struct _ITEMID_CHILD **
0x18002bc92  lea     r9, [rbp+57h+psfParent]; void **
0x18002bc96  mov     rdx, rdi; struct _TREEITEM *
0x18002bc99  mov     rcx, r14; this
0x18002bc9c  call    ?_GetTreeItemParentFolder@CNscTree@@AEAAJPEAU_TREEITEM@@AEBU_GUID@@PEAPEAXPEAPEFBU_ITEMID_CHILD@@@Z; CNscTree::_GetTreeItemParentFolder(_TREEITEM *,_GUID const &,void * *,_ITEMID_CHILD const * *)
0x18002bca1  mov     ebx, eax
0x18002bca3  test    eax, eax
0x18002bca5  js      loc_18002BDB7
0x18002bcab  mov     [rbp+57h+ppvItem], r13
0x18002bcaf  lea     rax, [rbp+57h+ppvItem]
0x18002bcb3  mov     [rsp+20h], rax; ppvItem
0x18002bcb8  lea     r15, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18002bcbf  mov     r9, r15; riid
0x18002bcc2  mov     r8, [rbp+57h+pidl]; pidl
0x18002bcc6  mov     rdx, [rbp+57h+psfParent]; psfParent
0x18002bcca  xor     ecx, ecx; pidlParent
0x18002bccc  call    cs:__imp_SHCreateItemWithParent
0x18002bcd2  mov     ebx, eax
0x18002bcd4  test    eax, eax
0x18002bcd6  js      loc_18002C07F
0x18002bcdc  mov     [rbp+57h+punk], r13
0x18002bce0  lea     r9, [rbp+57h+punk]; void **
0x18002bce4  mov     edx, 1; int
0x18002bce9  mov     rcx, [rbp+57h+ppvItem]; punk
0x18002bced  call    ?_ConvertToViewResultItem@@YAJPEAUIShellItem@@HAEBU_GUID@@PEAPEAX@Z; _ConvertToViewResultItem(IShellItem *,int,_GUID const &,void * *)
0x18002bcf2  mov     ebx, eax
0x18002bcf4  test    eax, eax
0x18002bcf6  js      short loc_18002BD6E
0x18002bcf8  mov     rdx, [rbp+57h+punk]; punk
0x18002bcfc  lea     rcx, [rbp+57h+ppvItem]; ppunk
0x18002bd00  call    cs:__imp_IUnknown_Set
0x18002bd06  mov     rcx, [rbp+57h+punk]
0x18002bd0a  mov     rax, [rcx]
0x18002bd0d  mov     rax, [rax+10h]
0x18002bd11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd16  xorps   xmm0, xmm0
0x18002bd19  xor     eax, eax
0x18002bd1b  movups  xmmword ptr [rbp+57h+ppropvar], xmm0
0x18002bd1f  mov     [rbp+57h+Src], rax
0x18002bd23  lea     r8, [rbp+57h+ppropvar]; ppropvar
0x18002bd27  lea     edx, [rax+8]; cb
0x18002bd2a  lea     rcx, [rbp+57h+var_B8]; pv
0x18002bd2e  call    cs:__imp_InitPropVariantFromBuffer
0x18002bd34  test    eax, eax
0x18002bd36  js      short loc_18002BD57
0x18002bd38  lea     r8, [rbp+57h+ppropvar]; propvar
0x18002bd3c  lea     rdx, PKEY_DescriptionID; propkey
0x18002bd43  mov     rcx, [rbp+57h+ppvItem]; psi
0x18002bd47  call    cs:__imp_SHSetTemporaryPropertyForItem
0x18002bd4d  lea     rcx, [rbp+57h+ppropvar]; pvar
0x18002bd51  call    cs:__imp_PropVariantClear
0x18002bd57  mov     rcx, [rbp+57h+ppvItem]
0x18002bd5b  mov     rax, [rcx]
0x18002bd5e  mov     r8, rsi
0x18002bd61  mov     rdx, r15
0x18002bd64  mov     rax, [rax]
0x18002bd67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd6c  mov     ebx, eax
0x18002bd6e  mov     rcx, [rbp+57h+ppvItem]
0x18002bd72  mov     rax, [rcx]
0x18002bd75  mov     rax, [rax+10h]
0x18002bd79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd7e  mov     rcx, [rbp+57h+psfParent]
0x18002bd82  mov     rax, [rcx]
  ... truncated ...
```
