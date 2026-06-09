# CGrepQuery::CrawlForNextItemImpl(IPropertyStore * *)

- ea: `0x180024130`
- end: `0x180024c30`
- name: `?CrawlForNextItemImpl@CGrepQuery@@QEAAJPEAPEAUIPropertyStore@@@Z`
- size: `2816`
- prototype: `__int64 __fastcall(CGrepQuery *__hidden this, struct IPropertyStore **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180094c30`

## callees

- `0x180006ca8`
- `0x18001e4c4`
- `0x180022d60`
- `0x1800230b0`
- `0x180023530`
- `0x18002379c`
- `0x180023d50`
- `0x180024130`
- `0x180024c40`
- `0x180040b10`
- `0x18004c220`
- `0x18006a928`
- `0x18006c840`
- `0x180071dc0`
- `0x18009202c`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!ILFree` at `0x180024523`
- `Windows.Storage!ILFree` at `0x180024574`
- `Windows.Storage!ILFree` at `0x18002458a`
- `Windows.Storage!ILFree` at `0x180024523`
- `Windows.Storage!ILFree` at `0x180024574`
- `Windows.Storage!ILFree` at `0x18002458a`
- `Windows.Storage!SHGetIDListFromObject` at `0x1800245b3`
- `Windows.Storage!SHGetIDListFromObject` at `0x1800245b3`
- `Windows.Storage!SHCreateItemWithParent` at `0x18002426c`
- `Windows.Storage!SHCreateItemWithParent` at `0x18002426c`
- `Windows.Storage!__imp_SHLogILFromFSIL` at `0x18002468c`
- `Windows.Storage!__imp_SHLogILFromFSIL` at `0x18002468c`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1800243d1`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1800243d1`

## pseudocode

```c
__int64 __fastcall CGrepQuery::CrawlForNextItemImpl(CGrepQuery *this, struct IPropertyStore **a2, int a3)
{
  CGrepQuery *v3; // rax
  int v4; // edi
  int v5; // r13d
  int v6; // ebx
  int v7; // esi
  int v8; // r14d
  int v9; // r15d
  int v10; // r12d
  CGrepQuery *v11; // rcx
  __int64 v12; // r10
  const ITEMIDLIST *v13; // r8
  IShellFolder *v14; // rdx
  CGrepQuery *v15; // rax
  int v16; // edx
  int v17; // edx
  struct IShellFolderVtbl *lpVtbl; // r9
  unsigned int v19; // ecx
  int v20; // eax
  char v21; // cl
  struct IShellFolderVtbl *v22; // rcx
  int v23; // ecx
  struct CIDLNode *v24; // rdx
  __int64 **v25; // r9
  __int64 *v26; // r8
  ITEMIDLIST *v27; // rax
  bool v28; // zf
  int v29; // ecx
  struct CIDLNode *v30; // rdx
  __int64 **v31; // r9
  __int64 *v32; // r8
  struct CIDLNode *v33; // rax
  int v34; // eax
  int NextFolder; // eax
  CGrepQuery *v36; // rcx
  struct IShellFolder *v37; // rdx
  struct CIDLNode *v38; // rax
  int v39; // eax
  char IsSearchCandidateItemIndexed; // al
  void *v42; // rax
  void *v43; // rax
  struct CIDLNode *v44; // rax
  struct CIDLNode *v45; // rax
  int matched; // eax
  int v47; // ecx
  int v48; // [rsp+30h] [rbp-D0h] BYREF
  struct IShellFolderVtbl *v49; // [rsp+38h] [rbp-C8h] BYREF
  CGrepQuery *v50; // [rsp+40h] [rbp-C0h]
  int v51; // [rsp+48h] [rbp-B8h]
  unsigned int v52; // [rsp+50h] [rbp-B0h]
  struct CIDLNode *v53; // [rsp+58h] [rbp-A8h] BYREF
  __int64 **v54; // [rsp+60h] [rbp-A0h]
  __int64 *v55; // [rsp+68h] [rbp-98h]
  HDPA hdpa; // [rsp+70h] [rbp-90h] BYREF
  LPITEMIDLIST ppidl; // [rsp+78h] [rbp-88h] BYREF
  void *p; // [rsp+80h] [rbp-80h] BYREF
  struct IShellFolder *v59; // [rsp+88h] [rbp-78h] BYREF
  int v60; // [rsp+90h] [rbp-70h] BYREF
  struct CIDLNode *v61; // [rsp+98h] [rbp-68h] BYREF
  LPBC ppbc; // [rsp+A0h] [rbp-60h] BYREF
  struct IPropertyStore **v63; // [rsp+A8h] [rbp-58h]
  __int64 (__fastcall *v64)(CGrepQuery *__hidden, struct IShellItem *, unsigned int); // [rsp+B0h] [rbp-50h]
  _DWORD v65[2]; // [rsp+B8h] [rbp-48h]
  __int64 (__fastcall *v66)(CGrepQuery *__hidden, struct IShellItem *, unsigned int); // [rsp+C0h] [rbp-40h]
  int v67; // [rsp+C8h] [rbp-38h]
  int v68; // [rsp+CCh] [rbp-34h]
  int (*v69)(CGrepQuery *__hidden, struct IShellItem *, unsigned int); // [rsp+D0h] [rbp-30h]
  int v70; // [rsp+D8h] [rbp-28h]
  int v71; // [rsp+DCh] [rbp-24h]
  __int64 (__fastcall *v72)(CGrepQuery *__hidden, struct IShellItem *, unsigned int); // [rsp+E0h] [rbp-20h]
  int v73; // [rsp+E8h] [rbp-18h]
  int v74; // [rsp+ECh] [rbp-14h]
  _BOOL8 (__fastcall *v75)(CGrepQuery *, struct IShellItem *); // [rsp+F0h] [rbp-10h]
  int v76; // [rsp+F8h] [rbp-8h]
  int v77; // [rsp+FCh] [rbp-4h]
  __int64 (__fastcall *v78)(CGrepQuery *__hidden, struct IShellItem *, unsigned int); // [rsp+100h] [rbp+0h]
  int v79; // [rsp+108h] [rbp+8h]
  int v80; // [rsp+10Ch] [rbp+Ch]
  LPITEMIDLIST pidl; // [rsp+110h] [rbp+10h] BYREF
  int v82; // [rsp+11Ch] [rbp+1Ch]

  *a2 = 0;
  v3 = this;
  v63 = a2;
  v50 = this;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x200000) != 0 )
  {
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)this,
      (unsigned int)ShellTraceId_Shell32_CGrepQuery_Crawl_Start,
      a3,
      1,
      (__int64)&pidl);
    v3 = v50;
    a2 = v63;
  }
  v4 = v82;
  v5 = 1;
  v6 = v82;
  v7 = v82;
  v8 = v82;
  v9 = v82;
  while ( 1 )
  {
    if ( v5 == 265926 || *a2 )
      goto LABEL_118;
    if ( v3 )
    {
      this = (CGrepQuery *)((char *)v3 + 8);
      if ( v3 != (CGrepQuery *)-8LL )
      {
        if ( (*(unsigned int (__fastcall **)(CGrepQuery *))(*(_QWORD *)this + 24LL))(this) )
          break;
      }
    }
    v5 = 0;
    *v63 = 0;
    v10 = v82;
    while ( v5 != 265926 )
    {
      v11 = v50;
      v12 = *((_QWORD *)v50 + 21);
      v61 = (CGrepQuery *)((char *)v50 + 168);
      if ( v12 )
      {
        if ( !(*(unsigned int (__fastcall **)(__int64, __int64, char *, _QWORD))(*(_QWORD *)v12 + 24LL))(
                v12,
                1,
                (char *)v50 + 192,
                0) )
          break;
        v11 = v50;
      }
      v59 = 0;
      NextFolder = CGrepQuery::_GetNextFolder(v11, &v59);
      v5 = NextFolder;
      if ( NextFolder == 265926 )
      {
        SafeRelease<IShellItemArray>((__int64 *)v61);
        SafeRelease<IShellItemArray>((__int64 *)v50 + 23);
      }
      else
      {
        if ( NextFolder < 0 )
          goto LABEL_44;
        v36 = v50;
        v37 = v59;
        *((_DWORD *)v50 + 45) = *((_DWORD *)v50 + 44);
        CGrepQuery::_EnumFolder(v36, (IUnknown *)v37);
        ((void (__fastcall *)(struct IShellFolder *))v59->lpVtbl->Release)(v59);
      }
    }
    v3 = v50;
    if ( v5 < 0 )
      goto LABEL_118;
    if ( v5 != 265926 )
    {
      v13 = (const ITEMIDLIST *)*((_QWORD *)v50 + 24);
      v14 = (IShellFolder *)*((_QWORD *)v50 + 23);
      v59 = (struct IShellFolder *)((char *)v50 + 200);
      v5 = SHCreateItemWithParent(0, v14, v13, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, (void **)v50 + 25);
      if ( v5 < 0 )
        goto LABEL_42;
      v15 = v50;
      v16 = 1;
      v51 = 1;
      if ( (*((_BYTE *)v50 + 152) & 1) == 0 || !*((_DWORD *)v50 + 45) )
        goto LABEL_35;
      v60 = 0;
      v5 = (*((__int64 (__fastcall **)(struct IShellFolderVtbl *, __int64, int *))v59->lpVtbl->QueryInterface + 6))(
             v59->lpVtbl,
             541130752,
             &v60);
      if ( v5 < 0 )
        goto LABEL_53;
      v17 = v60;
      v64 = CGrepQuery::_IsFolder;
      v66 = CGrepQuery::_IsNotDBFolder;
      lpVtbl = v59->lpVtbl;
      a3 = 0;
      v69 = CGrepQuery::_IsNotExcludedFolder;
      v19 = 0;
      v51 = v60;
      v72 = CGrepQuery::_IsNotArchiveFolder;
      v75 = CGrepQuery::_IsNotRestrictedFolder;
      v78 = CGrepQuery::_IsNotRecycleBin;
      v20 = 1;
      v49 = lpVtbl;
      v65[0] = 0;
      v65[1] = v6;
      v67 = 0;
      v68 = v4;
      v70 = 0;
      v71 = v7;
      v73 = 0;
      v74 = v8;
      v76 = 0;
      v77 = v9;
      v79 = 0;
      v80 = v10;
      v48 = 0;
      do
      {
        if ( !v20 )
          goto LABEL_33;
        v20 = (*(__int64 (__fastcall **)(char *, struct IShellFolderVtbl *, _QWORD))&v65[4 * v19 - 2])(
                (CGrepQuery *)((char *)v50 + (int)v65[4 * v19]),
                (struct IShellItem *)lpVtbl,
                v17);
        v17 = v51;
        v19 = v48 + 1;
        lpVtbl = v49;
        v48 = v19;
      }
      while ( v19 < 6 );
      if ( !v20 )
        goto LABEL_33;
      if ( (*((_DWORD *)v50 + 38) & 0x200) == 0 )
      {
        ppidl = 0;
LABEL_28:
        p = 0;
        if ( (*((int (__fastcall **)(struct IShellFolderVtbl *, LPITEMIDLIST, const GUID *, GUID *, void **))v49->QueryInterface
              + 3))(
               v49,
               ppidl,
               &BHID_SFObject,
               &GUID_000214e6_0000_0000_c000_000000000046,
               &p) >= 0
          && DPA_InsertPtr(*((HDPA *)v50 + 6), 0x7FFFFFFF, p) == -1 )
        {
          (*(void (__fastcall **)(void *))(*(_QWORD *)p + 16LL))(p);
        }
        if ( ppidl )
          (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&ppidl->mkid.cb + 16LL))(ppidl);
        goto LABEL_33;
      }
      ppidl = 0;
      ppbc = 0;
      if ( CreateBindCtx(0, &ppbc) >= 0 )
      {
        v48 = BindCtx_AddObjectParam_0(ppbc, L"AssumeWritable");
        if ( v48 >= 0 )
        {
          ppidl = (LPITEMIDLIST)ppbc;
          ((void (__fastcall *)(LPBC))ppbc->lpVtbl->AddRef)(ppbc);
        }
        ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
        if ( v48 >= 0 )
          goto LABEL_28;
      }
LABEL_33:
      v15 = v50;
      v16 = 1;
      v51 = 1;
      if ( (*((_DWORD *)v50 + 38) & 0x800) != 0 || (v60 & 0x20000000) == 0 )
      {
LABEL_35:
        v21 = 0;
        if ( (*((_BYTE *)v15 + 152) & 0x10) != 0 )
        {
          IsSearchCandidateItemIndexed = anonymous_namespace_::IsSearchCandidateItemIndexed((struct IShellItem *)v59->lpVtbl);
          v16 = v51;
          v21 = IsSearchCandidateItemIndexed;
          v15 = v50;
        }
        if ( v16 && !v21 )
          v5 = CGrepQuery::_EvaluateItem(v15, *((IUnknown **)v15 + 7), (IUnknown **)v63);
        v22 = v59->lpVtbl;
        v59->lpVtbl = 0;
        if ( v22 )
          (*((void (__fastcall **)(struct IShellFolderVtbl *))v22->QueryInterface + 2))(v22);
LABEL_42:
        v3 = v50;
        this = (CGrepQuery *)_InterlockedExchange64((volatile __int64 *)v50 + 24, 0);
        if ( this )
        {
          ILFree((LPITEMIDLIST)this);
LABEL_44:
          v3 = v50;
        }
        goto LABEL_45;
      }
      ppidl = 0;
      if ( SHGetIDListFromObject((IUnknown *)v59->lpVtbl, &ppidl) < 0 )
      {
LABEL_53:
        v15 = v50;
        v16 = v51;
        goto LABEL_35;
      }
      p = 0;
      v61 = 0;
      v48 = 0;
      if ( (int)CIDLNode::GetNode(
                  *((CIDLNode **)v50 + 18),
                  0,
                  (const struct _ITEMIDLIST_RELATIVE *)ppidl,
                  &v61,
                  (enum IDLDATAF *)&v48) >= 0
        && (v23 = v48 & 7, LODWORD(v49) = v23, (v48 & 7) != 0) )
      {
        v24 = v61;
      }
      else
      {
        v23 = 7;
        v24 = 0;
        LODWORD(v49) = 7;
      }
      if ( !v24 )
        goto LABEL_68;
      v25 = (__int64 **)((char *)v24 + 40);
      v53 = v24;
      v26 = 0;
      v54 = (__int64 **)((char *)v24 + 40);
      v55 = 0;
      hdpa = 0;
LABEL_60:
      v52 = v23;
      while ( 2 )
      {
        v48 = -2147467259;
        if ( !v24 )
          goto LABEL_65;
        if ( (v23 & 0xF) == 0 && (v23 & 0x10000001) != 0x10000001 )
        {
          v48 = -2147467259;
LABEL_65:
          CDPA_Base<CIDLNode,CTContainer_PolicyUnOwned<CIDLNode>>::Destroy(&hdpa);
          if ( hdpa )
            CDPA_Base<CIDLNode,CTContainer_PolicyUnOwned<CIDLNode>>::Destroy(&hdpa);
          if ( v48 >= 0 )
            goto LABEL_142;
LABEL_68:
          v27 = (ITEMIDLIST *)SHLogILFromFSIL(ppidl);
          pidl = v27;
          if ( !v27 )
            goto LABEL_52;
          v48 = -2147467259;
          v61 = 0;
          LODWORD(v49) = 0;
          if ( (int)CIDLNode::GetNode(
                      *((CIDLNode **)v50 + 18),
                      0,
                      (const struct _ITEMIDLIST_RELATIVE *)v27,
                      &v61,
                      (enum IDLDATAF *)&v49) < 0
            || (v28 = ((unsigned __int8)v49 & 7) == 0, v29 = (unsigned __int8)v49 & 7, LODWORD(v49) = v29, v28) )
          {
            v29 = 7;
            v30 = 0;
            LODWORD(v49) = 7;
          }
          else
          {
            v30 = v61;
          }
          if ( !v30 )
            goto LABEL_51;
          v31 = (__int64 **)((char *)v30 + 40);
          v53 = v30;
          v32 = 0;
          v54 = (__int64 **)((char *)v30 + 40);
          v55 = 0;
          hdpa = 0;
LABEL_74:
          v52 = v29;
          while ( 1 )
          {
            v48 = -2147467259;
            if ( !v30 )
              goto LABEL_49;
            if ( (v29 & 0xF) == 0 && (v29 & 0x10000001) != 0x10000001 )
            {
              v48 = -2147467259;
              goto LABEL_49;
            }
            if ( (v29 & 0x10000001) == 0x10000001 )
            {
              v43 = (void *)*((_QWORD *)v30 + 6);
              v52 = v29 & 0xEFFFFFFE;
              p = v43;
              v48 = 0;
              goto LABEL_49;
            }
            if ( v32 )
            {
              v32 = (__int64 *)*v32;
            }
            else
            {
              if ( !v31 )
                goto LABEL_82;
              v32 = *v31;
            }
            v55 = v32;
            if ( !v32 )
            {
LABEL_82:
              if ( (v29 & 7) != 0 )
              {
                v33 = (struct CIDLNode *)*((_QWORD *)v30 + 3);
                v53 = v33;
                v30 = v33;
                if ( v33 )
                {
                  v32 = 0;
                  v31 = (__int64 **)((char *)v33 + 40);
                  v54 = (__int64 **)((char *)v33 + 40);
                  v55 = 0;
                  if ( (v29 & 1) != 0 )
                  {
                    v29 &= ~1u;
                    LODWORD(v49) = v29;
                    goto LABEL_74;
                  }
                  if ( (v29 & 3) != 0 )
                  {
                    v29 &= 0xFFFFFFFC;
                    LODWORD(v49) = v29;
                    goto LABEL_74;
                  }
                }
                else
                {
                  v29 &= 0xFFFFFFF8;
                  LODWORD(v49) = v29;
                  v52 = v29;
                  if ( (v29 & 8) != 0 )
                  {
                    v34 = CIDLTreeTraversor::Next((CIDLTreeTraversor *)&hdpa, &v53);
                    v29 = v52;
                    v30 = v53;
                    LODWORD(v49) = v52;
                    if ( v34 )
                    {
                      v32 = v55;
                      v31 = v54;
                    }
                    else
                    {
                      v31 = (__int64 **)((char *)v53 + 40);
                      v32 = 0;
                      v54 = (__int64 **)((char *)v53 + 40);
                      v55 = 0;
                    }
                  }
                }
              }
              else if ( (v29 & 8) != 0 )
              {
                if ( !hdpa || *(int *)hdpa <= 0 )
                {
                  v30 = 0;
                  v53 = 0;
LABEL_115:
                  v32 = v55;
                  v29 &= ~8u;
                  LODWORD(v49) = v29;
                  goto LABEL_74;
                }
                v45 = (struct CIDLNode *)g_pfn_DPA_DeletePtr(hdpa, *(_DWORD *)hdpa - 1);
                v29 = (int)v49;
                v30 = v45;
                v53 = v45;
                if ( !v45 )
                {
                  v31 = v54;
                  goto LABEL_115;
                }
                v31 = (__int64 **)((char *)v45 + 40);
                v32 = 0;
                v54 = (__int64 **)((char *)v45 + 40);
                v55 = 0;
              }
              continue;
            }
            if ( (v29 & (_DWORD)v32[1]) != 0 )
            {
              p = (void *)v32[2];
              v48 = 0;
LABEL_49:
              CDPA_Base<CIDLNode,CTContainer_PolicyUnOwned<CIDLNode>>::Destroy(&hdpa);
              if ( hdpa )
                CDPA_Base<CIDLNode,CTContainer_PolicyUnOwned<CIDLNode>>::Destroy(&hdpa);
LABEL_51:
              ILFree(pidl);
              if ( v48 < 0 )
              {
LABEL_52:
                ILFree(ppidl);
                goto LABEL_53;
              }
LABEL_142:
              v51 = 0;
              if ( p == (void *)2 )
              {
                matched = CIDLTree::MatchOne(*((_QWORD *)v50 + 18), 1, ppidl, &pidl);
                v47 = v51;
                if ( matched < 0 )
                  v47 = 1;
                v51 = v47;
              }
              goto LABEL_52;
            }
          }
        }
        if ( (v23 & 0x10000001) == 0x10000001 )
        {
          v42 = (void *)*((_QWORD *)v24 + 6);
          v52 = v23 & 0xEFFFFFFE;
          p = v42;
          v48 = 0;
          goto LABEL_65;
        }
        if ( !v26 )
        {
          if ( v25 )
          {
            v26 = *v25;
LABEL_95:
            v55 = v26;
            if ( v26 )
            {
              if ( (v23 & (_DWORD)v26[1]) != 0 )
              {
                p = (void *)v26[2];
                v48 = 0;
                goto LABEL_65;
              }
              continue;
            }
          }
          if ( (v23 & 7) != 0 )
          {
            v38 = (struct CIDLNode *)*((_QWORD *)v24 + 3);
            v53 = v38;
            v24 = v38;
            if ( v38 )
            {
              v26 = 0;
              v25 = (__int64 **)((char *)v38 + 40);
              v54 = (__int64 **)((char *)v38 + 40);
              v55 = 0;
              if ( (v23 & 1) != 0 )
              {
                v23 &= ~1u;
                LODWORD(v49) = v23;
                goto LABEL_60;
              }
              if ( (v23 & 3) != 0 )
              {
                v23 &= 0xFFFFFFFC;
                LODWORD(v49) = v23;
                goto LABEL_60;
              }
            }
            else
            {
              v23 &= 0xFFFFFFF8;
              LODWORD(v49) = v23;
              v52 = v23;
              if ( (v23 & 8) != 0 )
              {
                v39 = CIDLTreeTraversor::Next((CIDLTreeTraversor *)&hdpa, &v53);
                v23 = v52;
                v24 = v53;
                LODWORD(v49) = v52;
                if ( v39 )
                {
                  v26 = v55;
                  v25 = v54;
                }
                else
                {
                  v25 = (__int64 **)((char *)v53 + 40);
                  v26 = 0;
                  v54 = (__int64 **)((char *)v53 + 40);
                  v55 = 0;
                }
              }
            }
          }
          else if ( (v23 & 8) != 0 )
          {
            if ( !hdpa || *(int *)hdpa <= 0 )
            {
              v24 = 0;
              v53 = 0;
              goto LABEL_108;
            }
            v44 = (struct CIDLNode *)g_pfn_DPA_DeletePtr(hdpa, *(_DWORD *)hdpa - 1);
            v23 = (int)v49;
            v24 = v44;
            v53 = v44;
            if ( !v44 )
            {
              v25 = v54;
LABEL_108:
              v26 = v55;
              v23 &= ~8u;
              LODWORD(v49) = v23;
              goto LABEL_60;
            }
            v25 = (__int64 **)((char *)v44 + 40);
            v26 = 0;
            v54 = (__int64 **)((char *)v44 + 40);
            v55 = 0;
          }
          continue;
        }
        break;
      }
      v26 = (__int64 *)*v26;
      goto LABEL_95;
    }
LABEL_45:
    if ( v5 < 0 )
      goto LABEL_118;
    a2 = v63;
  }
  v5 = -2147023673;
LABEL_118:
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x200000) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)this,
      (unsigned int)ShellTraceId_Shell32_CGrepQuery_Crawl_Stop,
      a3,
      1,
      (__int64)&pidl);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180024130  mov     [rsp-8+arg_10], rbx
0x180024135  push    rbp
0x180024136  push    rsi
0x180024137  push    rdi
0x180024138  push    r12
0x18002413a  push    r13
0x18002413c  push    r14
0x18002413e  push    r15
0x180024140  lea     rbp, [rsp-30h]
0x180024145  sub     rsp, 130h
0x18002414c  mov     rax, cs:__security_cookie
0x180024153  xor     rax, rsp
0x180024156  mov     [rbp+60h+var_40], rax
0x18002415a  mov     qword ptr [rdx], 0
0x180024161  mov     rax, rcx
0x180024164  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+2, 20h
0x18002416b  mov     ebx, 1
0x180024170  mov     [rbp+60h+var_B8], rdx
0x180024174  mov     [rsp+160h+var_120], rcx
0x180024179  jnz     loc_1800249B9
0x18002417f  mov     edi, [rbp+60h+var_44]
0x180024182  mov     r13d, ebx
0x180024185  mov     ebx, [rbp+60h+var_44]
0x180024188  mov     esi, [rbp+60h+var_44]
0x18002418b  mov     r14d, [rbp+60h+var_44]
0x18002418f  mov     r15d, [rbp+60h+var_44]
0x180024193  cmp     r13d, 40EC6h
0x18002419a  jz      loc_1800249EF
0x1800241a0  cmp     qword ptr [rdx], 0
0x1800241a4  jnz     loc_1800249EF
0x1800241aa  test    rax, rax
0x1800241ad  jz      short loc_1800241CC
0x1800241af  lea     rcx, [rax+8]
0x1800241b3  test    rcx, rcx
0x1800241b6  jz      short loc_1800241CC
0x1800241b8  mov     rax, [rcx]
0x1800241bb  mov     rax, [rax+18h]
0x1800241bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241c4  test    eax, eax
0x1800241c6  jnz     loc_180024C05
0x1800241cc  mov     r12, [rbp+60h+var_B8]
0x1800241d0  xor     r13d, r13d
0x1800241d3  mov     qword ptr [r12], 0
0x1800241db  mov     r12d, [rbp+60h+var_44]
0x1800241df  cmp     r13d, 40EC6h
0x1800241e6  jz      short loc_18002422A
0x1800241e8  mov     rcx, [rsp+160h+var_120]
0x1800241ed  lea     rax, [rcx+0A8h]
0x1800241f4  mov     r10, [rax]
0x1800241f7  mov     [rbp+60h+var_C8], rax
0x1800241fb  test    r10, r10
0x1800241fe  jz      loc_1800247D2
0x180024204  mov     rax, [r10]
0x180024207  lea     r8, [rcx+0C0h]
0x18002420e  xor     r9d, r9d
0x180024211  mov     edx, 1
0x180024216  mov     rcx, r10
0x180024219  mov     rax, [rax+18h]
0x18002421d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024222  test    eax, eax
0x180024224  jnz     loc_1800247CD
0x18002422a  mov     rax, [rsp+160h+var_120]
0x18002422f  test    r13d, r13d
0x180024232  js      loc_1800249EF
0x180024238  cmp     r13d, 40EC6h
0x18002423f  jz      loc_18002452E
0x180024245  mov     r8, [rax+0C0h]; pidl
0x18002424c  lea     rcx, [rax+0C8h]
0x180024253  mov     rdx, [rax+0B8h]; psfParent
0x18002425a  lea     r9, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x180024261  mov     [rbp+60h+var_D8], rcx
0x180024265  mov     [rsp+160h+ppvItem], rcx; ppvItem
0x18002426a  xor     ecx, ecx; pidlParent
0x18002426c  call    cs:__imp_SHCreateItemWithParent
0x180024272  mov     r13d, eax
0x180024275  test    eax, eax
0x180024277  js      loc_180024510
0x18002427d  mov     rax, [rsp+160h+var_120]
0x180024282  mov     edx, 1
0x180024287  mov     [rsp+160h+var_118], edx
0x18002428b  test    [rax+98h], dl
0x180024291  jz      loc_1800244C7
0x180024297  cmp     dword ptr [rax+0B4h], 0
0x18002429e  jz      loc_1800244C7
0x1800242a4  mov     rcx, [rbp+60h+var_D8]
0x1800242a8  lea     r8, [rbp+60h+var_D0]
0x1800242ac  mov     [rbp+60h+var_D0], 0
0x1800242b3  mov     edx, 20410000h
0x1800242b8  mov     rcx, [rcx]
0x1800242bb  mov     rax, [rcx]
0x1800242be  mov     rax, [rax+30h]
0x1800242c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242c7  mov     r13d, eax
0x1800242ca  test    eax, eax
0x1800242cc  js      loc_180024590
0x1800242d2  mov     r8, [rbp+60h+var_D8]
0x1800242d6  lea     rax, ?_IsFolder@CGrepQuery@@AEAAHPEAUIShellItem@@K@Z; CGrepQuery::_IsFolder(IShellItem *,ulong)
0x1800242dd  mov     edx, [rbp+60h+var_D0]
0x1800242e0  mov     [rbp+60h+var_B0], rax
0x1800242e4  lea     rax, ?_IsNotDBFolder@CGrepQuery@@AEAAHPEAUIShellItem@@K@Z; CGrepQuery::_IsNotDBFolder(IShellItem *,ulong)
0x1800242eb  mov     [rbp+60h+var_A0], rax
0x1800242ef  lea     rax, ?_IsNotExcludedFolder@CGrepQuery@@AEAAHPEAUIShellItem@@K@Z; CGrepQuery::_IsNotExcludedFolder(IShellItem *,ulong)
0x1800242f6  mov     r9, [r8]
0x1800242f9  xor     r8d, r8d
0x1800242fc  mov     [rbp+60h+var_90], rax
0x180024300  mov     ecx, r8d
0x180024303  lea     rax, ?_IsNotArchiveFolder@CGrepQuery@@AEAAHPEAUIShellItem@@K@Z; CGrepQuery::_IsNotArchiveFolder(IShellItem *,ulong)
0x18002430a  mov     [rsp+160h+var_118], edx
0x18002430e  mov     [rbp+60h+var_80], rax
0x180024312  lea     rax, ?_IsNotRestrictedFolder@CGrepQuery@@AEAAHPEAUIShellItem@@K@Z; CGrepQuery::_IsNotRestrictedFolder(IShellItem *,ulong)
0x180024319  mov     [rbp+60h+var_70], rax
0x18002431d  lea     rax, ?_IsNotRecycleBin@CGrepQuery@@AEAAHPEAUIShellItem@@K@Z; CGrepQuery::_IsNotRecycleBin(IShellItem *,ulong)
0x180024324  mov     [rbp+60h+var_60], rax
0x180024328  mov     eax, 1
0x18002432d  mov     [rsp+160h+var_128], r9
0x180024332  mov     [rbp+60h+var_A8], r8d
0x180024336  mov     [rbp+60h+var_A4], ebx
0x180024339  mov     [rbp+60h+var_98], r8d
0x18002433d  mov     [rbp+60h+var_94], edi
0x180024340  mov     [rbp+60h+var_88], r8d
0x180024344  mov     [rbp+60h+var_84], esi
0x180024347  mov     [rbp+60h+var_78], r8d
0x18002434b  mov     [rbp+60h+var_74], r14d
0x18002434f  mov     [rbp+60h+var_68], r8d
0x180024353  mov     [rbp+60h+var_64], r15d
0x180024357  mov     [rbp+60h+var_58], r8d
0x18002435b  mov     [rbp+60h+var_54], r12d
0x18002435f  mov     [rsp+160h+var_130], ecx
0x180024363  test    eax, eax
0x180024365  jz      loc_1800244A0
0x18002436b  movsxd  rax, ecx
0x18002436e  mov     r8d, edx
0x180024371  add     rax, rax
0x180024374  mov     rdx, r9
0x180024377  movsxd  rcx, [rbp+rax*8+60h+var_A8]
0x18002437c  add     rcx, [rsp+160h+var_120]
0x180024381  mov     rax, [rbp+rax*8+60h+var_B0]
0x180024386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002438b  mov     ecx, [rsp+160h+var_130]
0x18002438f  mov     edx, [rsp+160h+var_118]
0x180024393  inc     ecx
0x180024395  mov     r9, [rsp+160h+var_128]
0x18002439a  mov     [rsp+160h+var_130], ecx
0x18002439e  cmp     ecx, 6
0x1800243a1  jb      short loc_180024363
0x1800243a3  test    eax, eax
0x1800243a5  jz      loc_1800244A0
0x1800243ab  mov     rax, [rsp+160h+var_120]
0x1800243b0  test    dword ptr [rax+98h], 200h
0x1800243ba  jz      loc_180024AC0
0x1800243c0  xor     eax, eax
0x1800243c2  lea     rdx, [rbp+60h+ppbc]; ppbc
0x1800243c6  xor     ecx, ecx; reserved
0x1800243c8  mov     [rsp+160h+ppidl], rax
0x1800243cd  mov     [rbp+60h+ppbc], rax
0x1800243d1  call    cs:__imp_CreateBindCtx
0x1800243d7  test    eax, eax
0x1800243d9  js      loc_1800244A0
0x1800243df  mov     rcx, [rbp+60h+ppbc]
0x1800243e3  lea     rdx, aAssumewritable; "AssumeWritable"
0x1800243ea  call    BindCtx_AddObjectParam_0
0x1800243ef  mov     [rsp+160h+var_130], eax
0x1800243f3  test    eax, eax
0x1800243f5  js      short loc_18002440C
0x1800243f7  mov     rcx, [rbp+60h+ppbc]
0x1800243fb  mov     [rsp+160h+ppidl], rcx
0x180024400  mov     rax, [rcx]
0x180024403  mov     rax, [rax+8]
0x180024407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002440c  mov     rcx, [rbp+60h+ppbc]
0x180024410  mov     rax, [rcx]
0x180024413  mov     rax, [rax+10h]
0x180024417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002441c  mov     eax, [rsp+160h+var_130]
0x180024420  test    eax, eax
0x180024422  js      short loc_1800244A0
0x180024424  mov     rcx, [rsp+160h+var_128]
0x180024429  lea     rdx, [rbp+60h+p]
0x18002442d  mov     [rsp+160h+ppvItem], rdx
0x180024432  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x180024439  mov     rdx, [rsp+160h+ppidl]
0x18002443e  lea     r8, BHID_SFObject
0x180024445  mov     [rbp+60h+p], 0
0x18002444d  mov     rax, [rcx]
0x180024450  mov     rax, [rax+18h]
0x180024454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024459  test    eax, eax
0x18002445b  js      short loc_18002448A
0x18002445d  mov     rax, [rsp+160h+var_120]
0x180024462  mov     edx, 7FFFFFFFh; i
0x180024467  mov     r8, [rbp+60h+p]; p
0x18002446b  mov     rcx, [rax+30h]; hdpa
0x18002446f  call    cs:__imp_DPA_InsertPtr
0x180024475  cmp     eax, 0FFFFFFFFh
0x180024478  jnz     short loc_18002448A
0x18002447a  mov     rcx, [rbp+60h+p]
0x18002447e  mov     rax, [rcx]
0x180024481  mov     rax, [rax+10h]
0x180024485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002448a  mov     rcx, [rsp+160h+ppidl]
0x18002448f  test    rcx, rcx
0x180024492  jz      short loc_1800244A0
0x180024494  mov     rax, [rcx]
0x180024497  mov     rax, [rax+10h]
0x18002449b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244a0  mov     rax, [rsp+160h+var_120]
0x1800244a5  mov     edx, 1
0x1800244aa  mov     [rsp+160h+var_118], edx
0x1800244ae  test    dword ptr [rax+98h], 800h
0x1800244b8  jnz     short loc_1800244C7
0x1800244ba  test    [rbp+60h+var_D0], 20000000h
0x1800244c1  jnz     loc_18002459E
0x1800244c7  xor     cl, cl
0x1800244c9  test    byte ptr [rax+98h], 10h
0x1800244d0  jnz     loc_1800248C1
0x1800244d6  test    edx, edx
0x1800244d8  jz      short loc_1800244F1
0x1800244da  test    cl, cl
0x1800244dc  jnz     short loc_1800244F1
0x1800244de  mov     r8, [rbp+60h+var_B8]; struct IPropertyStore **
0x1800244e2  mov     rcx, rax; this
0x1800244e5  mov     rdx, [rax+38h]; struct ICondition *
0x1800244e9  call    ?_EvaluateItem@CGrepQuery@@AEAAJPEAUICondition@@PEAPEAUIPropertyStore@@@Z; CGrepQuery::_EvaluateItem(ICondition *,IPropertyStore * *)
0x1800244ee  mov     r13d, eax
0x1800244f1  mov     rax, [rbp+60h+var_D8]
0x1800244f5  mov     rcx, [rax]
0x1800244f8  mov     qword ptr [rax], 0
0x1800244ff  test    rcx, rcx
0x180024502  jz      short loc_180024510
0x180024504  mov     rax, [rcx]
0x180024507  mov     rax, [rax+10h]
0x18002450b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024510  mov     rax, [rsp+160h+var_120]
0x180024515  xor     ecx, ecx
0x180024517  xchg    rcx, [rax+0C0h]; pidl
0x18002451e  test    rcx, rcx
0x180024521  jz      short loc_18002452E
0x180024523  call    cs:__imp_ILFree
0x180024529  mov     rax, [rsp+160h+var_120]
0x18002452e  test    r13d, r13d
0x180024531  js      loc_1800249EF
0x180024537  mov     rdx, [rbp+60h+var_B8]
0x18002453b  jmp     loc_180024193
0x180024540  mov     eax, ecx
0x180024542  and     eax, 10000001h
0x180024547  cmp     eax, 10000001h
0x18002454c  jz      loc_180024738
0x180024552  mov     [rsp+160h+var_130], 80004005h
0x18002455a  lea     rcx, [rsp+160h+hdpa]
0x18002455f  call    ?Destroy@?$CDPA_Base@VCIDLNode@@V?$CTContainer_PolicyUnOwned@VCIDLNode@@@@@@QEAAHXZ; CDPA_Base<CIDLNode,CTContainer_PolicyUnOwned<CIDLNode>>::Destroy(void)
0x180024564  cmp     [rsp+160h+hdpa], 0
0x18002456a  jnz     loc_180024BAD
0x180024570  mov     rcx, [rbp+60h+pidl]; pidl
0x180024574  call    cs:__imp_ILFree
0x18002457a  cmp     [rsp+160h+var_130], 0
0x18002457f  jge     loc_180024BBC
0x180024585  mov     rcx, [rsp+160h+ppidl]; pidl
0x18002458a  call    cs:__imp_ILFree
0x180024590  mov     rax, [rsp+160h+var_120]
0x180024595  mov     edx, [rsp+160h+var_118]
0x180024599  jmp     loc_1800244C7
0x18002459e  mov     rcx, [rbp+60h+var_D8]
0x1800245a2  lea     rdx, [rsp+160h+ppidl]; ppidl
0x1800245a7  mov     [rsp+160h+ppidl], 0
0x1800245b0  mov     rcx, [rcx]; punk
0x1800245b3  call    cs:__imp_SHGetIDListFromObject
0x1800245b9  test    eax, eax
0x1800245bb  js      short loc_180024590
0x1800245bd  mov     r8, [rsp+160h+ppidl]; struct _ITEMIDLIST_RELATIVE *
0x1800245c2  lea     r9, [rbp+60h+var_C8]; struct CIDLNode **
0x1800245c6  xor     eax, eax
0x1800245c8  xor     edx, edx; int
0x1800245ca  mov     [rbp+60h+p], rax
0x1800245ce  mov     [rbp+60h+var_C8], rax
0x1800245d2  mov     [rsp+160h+var_130], eax
0x1800245d6  lea     rax, [rsp+160h+var_130]
0x1800245db  mov     [rsp+160h+ppvItem], rax; enum IDLDATAF *
0x1800245e0  mov     rax, [rsp+160h+var_120]
0x1800245e5  mov     rcx, [rax+90h]; this
0x1800245ec  call    ?GetNode@CIDLNode@@IEAAJHPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAV1@PEAW4IDLDATAF@@@Z; CIDLNode::GetNode(int,_ITEMIDLIST_RELATIVE const *,CIDLNode * *,IDLDATAF *)
0x1800245f1  test    eax, eax
0x1800245f3  js      loc_180024A64
0x1800245f9  mov     ecx, [rsp+160h+var_130]
0x1800245fd  and     ecx, 7
0x180024600  mov     dword ptr [rsp+160h+var_128], ecx
0x180024604  jz      loc_180024A64
0x18002460a  mov     rdx, [rbp+60h+var_C8]
0x18002460e  test    rdx, rdx
0x180024611  jz      short loc_180024687
0x180024613  lea     r9, [rdx+28h]
0x180024617  mov     [rsp+160h+var_108], rdx
0x18002461c  xor     r8d, r8d
0x18002461f  mov     [rsp+160h+var_100], r9
0x180024624  mov     [rsp+160h+var_F8], r8
0x180024629  mov     [rsp+160h+hdpa], 0
0x180024632  mov     [rsp+160h+var_110], ecx
0x180024636  mov     [rsp+160h+var_130], 80004005h
0x18002463e  test    rdx, rdx
0x180024641  jz      short loc_180024666
0x180024643  test    cl, 0Fh
  ... truncated ...
```
