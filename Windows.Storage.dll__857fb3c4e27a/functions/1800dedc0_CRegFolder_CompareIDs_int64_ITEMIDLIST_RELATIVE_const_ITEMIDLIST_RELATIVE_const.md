# CRegFolder::CompareIDs(__int64,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)

- ea: `0x1800dedc0`
- end: `0x1800dfcea`
- name: `?CompareIDs@CRegFolder@@UEAAJ_JPEFBU_ITEMIDLIST_RELATIVE@@1@Z`
- size: `3882`
- prototype: `int(CRegFolder *__hidden this, __int64, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_RELATIVE *)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000d6cc`
- `0x1800d0ac0`
- `0x1800d13a0`
- `0x1800dd910`
- `0x1800dedc0`
- `0x1800dfcf0`
- `0x1800dfdd0`
- `0x1800e2c40`
- `0x1800e4810`
- `0x1801322d0`
- `0x180161490`
- `0x18016b130`
- `0x180170cf0`
- `0x1801a1560`
- `0x18020f020`
- `0x18027cc78`
- `0x1802cb924`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x1803a96d9`
- `0x1803a96e5`
- `0x18065a010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800df99d`
- `OLEAUT32!__imp_VariantClear` at `0x1800df9a8`
- `OLEAUT32!__imp_VariantClear` at `0x1800df99d`
- `OLEAUT32!__imp_VariantClear` at `0x1800df9a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800df279`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800df279`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800df29b`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800df29b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df395`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df3fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df442`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df9b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df9bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dfb75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dfb84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df395`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df3fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df442`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df9b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df9bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dfb75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dfb84`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x1800dee5c`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x1800dee5c`
- `PROPSYS!VariantCompare` at `0x1800df98d`
- `PROPSYS!VariantCompare` at `0x1800df98d`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CRegFolder::CompareIDs(
        CRegFolder *this,
        __int64 a2,
        ITEMIDLIST *a3,
        const struct _ITEMIDLIST_RELATIVE *a4)
{
  CRegFolder *v6; // rsi
  int v7; // r14d
  struct IUnknown *v8; // rdi
  _WORD *v9; // rax
  __int64 v10; // rcx
  unsigned __int64 cb; // rbx
  int v12; // r15d
  BYTE v13; // di
  __int64 v14; // rdx
  unsigned __int64 v15; // rax
  __int64 v16; // rdx
  ITEMIDLIST *v17; // rax
  struct _GUID *v18; // rax
  __int64 v19; // rdx
  _QWORD *v20; // r8
  __int64 v21; // rax
  unsigned __int64 v22; // rbx
  char v23; // di
  __int64 v24; // rdx
  unsigned __int64 v25; // rax
  __int64 v26; // rdx
  const struct _ITEMIDLIST_RELATIVE *v27; // rax
  struct _GUID *v28; // rax
  __int64 v29; // rdx
  _QWORD *v30; // r8
  __int64 v31; // rax
  int v32; // eax
  int v33; // r14d
  unsigned __int64 v34; // rdi
  BYTE v35; // r15
  CRegFolder *v36; // rcx
  ITEMIDLIST *v37; // r15
  unsigned __int64 v38; // rdi
  char v39; // r12
  CRegFolder *v40; // rcx
  const struct _ITEMIDLIST_RELATIVE *v41; // rdi
  int v42; // r13d
  unsigned __int64 v43; // rax
  __int64 v44; // rdx
  const struct _ITEMIDLIST_RELATIVE *v45; // rax
  const void *v46; // r14
  unsigned __int64 v47; // r12
  __int64 v48; // rdx
  ITEMIDLIST *v49; // rax
  char *v50; // rcx
  CRegFolder *v51; // rcx
  unsigned __int16 *p_cb; // rdx
  __int64 v53; // rdx
  const struct _ITEMIDLIST_RELATIVE *v54; // r15
  unsigned __int64 v55; // rax
  __int64 v56; // r9
  const struct _ITEMIDLIST_RELATIVE *v57; // r12
  int v58; // edx
  bool v59; // sf
  size_t v60; // rbx
  _WORD *v61; // rdi
  _WORD *v62; // r14
  char *v63; // r15
  size_t v64; // r12
  __int64 v65; // rdx
  BOOL v67; // r14d
  BOOL v68; // ebx
  int v69; // eax
  ITEMIDLIST *v70; // rdx
  int v71; // eax
  const struct _ITEMIDLIST_RELATIVE *v72; // rdx
  struct IShellFolder2 *v73; // rcx
  CRegFolder *v74; // rcx
  char v75; // al
  char v76; // al
  LPMALLOC v77; // rdi
  HRESULT (__stdcall *QueryInterface)(IMalloc *, const IID *const, void **); // rbx
  int v79; // r15d
  LPITEMIDLIST v80; // rbx
  struct DELEGATEITEMID *v81; // rax
  CRegFolder *v82; // rcx
  unsigned __int8 OrderPure; // r12
  struct DELEGATEITEMID *v84; // rax
  int v85; // r12d
  char v86; // al
  char v87; // al
  LPITEMIDLIST v88; // rdi
  LPVOID v89; // rcx
  char *v90; // rdx
  __int64 v91; // rax
  unsigned int v92; // eax
  char *v93; // rdx
  __int64 v94; // rax
  __int64 v95; // rax
  int v96; // r12d
  unsigned __int16 **v97; // rax
  unsigned __int16 **v98; // rax
  void *v99; // rax
  LPMALLOC v100; // rcx
  char *v101; // r14
  int v102; // eax
  void *Src; // [rsp+38h] [rbp-81h] BYREF
  __int64 v105; // [rsp+40h] [rbp-79h]
  int v106; // [rsp+48h] [rbp-71h]
  LPMALLOC ppMalloc; // [rsp+50h] [rbp-69h] BYREF
  unsigned int cb_low; // [rsp+58h] [rbp-61h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-59h] BYREF
  struct _GUID Buf1; // [rsp+68h] [rbp-51h] BYREF
  __int128 v111; // [rsp+78h] [rbp-41h] BYREF
  int v112; // [rsp+88h] [rbp-31h]
  VARIANT var2; // [rsp+90h] [rbp-29h] BYREF
  VARIANT var1; // [rsp+A8h] [rbp-11h] BYREF

  Src = a3;
  v105 = a2;
  v6 = this;
  if ( !a3 || !a4 )
    return 2147942487LL;
  Buf1 = 0;
  v7 = 0;
  if ( !*((_QWORD *)this + 17) )
  {
    v8 = (struct IUnknown *)*((_QWORD *)this + 18);
    *((_QWORD *)this + 17) = 0;
    if ( v8 )
    {
      if ( _GetIDListFromObjectWorker(v8, (struct _ITEMIDLIST_ABSOLUTE **)this + 17) < 0 )
      {
        ppMalloc = 0;
        if ( _GetItemFromObjectWorker(v8, &GUID_1079acfc_29bd_11d3_8e0d_00c04f6837d5, (void **)&ppMalloc) >= 0 )
        {
          ((void (__fastcall *)(LPMALLOC, char *))ppMalloc->lpVtbl->Free)(ppMalloc, (char *)v6 + 136);
          ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
        }
      }
    }
  }
  if ( ((v9 = (_WORD *)*((_QWORD *)v6 + 17)) != 0 && *v9
     || (v10 = *((_QWORD *)v6 + 18)) != 0
     && (int)IUnknown_GetClassID(v10, &Buf1) >= 0
     && memcmp_0(&Buf1, &CLSID_ShellDesktop, 0x10u))
    && (!a3->mkid.cb || !*(_WORD *)a4) )
  {
    return 2147942487LL;
  }
  cb = a3->mkid.cb;
  v12 = 2;
  if ( (unsigned int)cb < 3 )
    goto LABEL_119;
  v13 = a3->mkid.abID[0];
  if ( v13 != *((_BYTE *)v6 + 288) )
    goto LABEL_159;
  if ( cb >= (unsigned __int64)*((unsigned __int16 *)v6 + 158) + 20 )
    goto LABEL_15;
  v69 = IsDelegateRegId(a3);
  v70 = a3;
  if ( !v69 )
    v70 = 0;
  if ( v70 )
  {
LABEL_15:
    if ( (unsigned int)cb <= 7 )
      goto LABEL_17;
  }
  else
  {
LABEL_159:
    if ( !*((_DWORD *)v6 + 79) || (v75 = *((_BYTE *)v6 + 320)) == 0 || v13 != v75 || (unsigned int)cb < 0x14 )
    {
LABEL_119:
      v7 = *((_DWORD *)v6 + 64);
      goto LABEL_29;
    }
  }
  v14 = *(unsigned __int16 *)((char *)&a3[1].mkid.cb + 1);
  if ( cb >= v14 + 38 )
  {
    Buf1 = *(struct _GUID *)((char *)&a3[2].mkid.cb + v14);
    if ( !memcmp_0(&Buf1, &unk_1806FB0A8, 0x10u) )
    {
      v7 = 2;
      goto LABEL_29;
    }
  }
LABEL_17:
  v15 = a3->mkid.cb;
  if ( (unsigned int)v15 > 7
    && (v16 = *(unsigned __int16 *)((char *)&a3[1].mkid.cb + 1), v15 >= v16 + 38)
    && (Buf1 = *(struct _GUID *)((char *)&a3[2].mkid.cb + v16), !memcmp_0(&Buf1, &unk_1806FB0A8, 0x10u)) )
  {
    v18 = (struct _GUID *)((char *)&a3[7].mkid.cb + *(unsigned __int16 *)((char *)&a3[1].mkid.cb + 1) + 1);
  }
  else
  {
    if ( v13 == *((_BYTE *)v6 + 320) )
      v17 = a3;
    else
      v17 = (ITEMIDLIST *)((char *)a3 + *((unsigned int *)v6 + 79));
    v18 = (struct _GUID *)((char *)&v17[1].mkid.cb + 1);
  }
  Buf1 = *v18;
  v19 = (unsigned int)(*((_DWORD *)v6 + 74) - 1);
  if ( (int)v19 < 0 )
  {
LABEL_27:
    if ( (_DWORD)v19 == -1 )
      v7 = 1;
  }
  else
  {
    while ( 1 )
    {
      v20 = *(_QWORD **)(*((_QWORD *)v6 + 38) + 48 * v19);
      v21 = *(_QWORD *)&Buf1.Data1 - *v20;
      if ( *(_QWORD *)&Buf1.Data1 == *v20 )
        v21 = *(_QWORD *)Buf1.Data4 - v20[1];
      if ( !v21 )
        break;
      v19 = (unsigned int)(v19 - 1);
      if ( (int)v19 < 0 )
        goto LABEL_27;
    }
  }
LABEL_29:
  v22 = *(unsigned __int16 *)a4;
  if ( (unsigned int)v22 < 3 )
  {
LABEL_124:
    v12 = *((_DWORD *)v6 + 64);
    goto LABEL_46;
  }
  v23 = *((_BYTE *)a4 + 2);
  if ( v23 != *((_BYTE *)v6 + 288) )
    goto LABEL_163;
  if ( v22 < (unsigned __int64)*((unsigned __int16 *)v6 + 158) + 20 )
  {
    v71 = IsDelegateRegId(a4);
    v72 = a4;
    if ( !v71 )
      v72 = 0;
    if ( !v72 )
    {
LABEL_163:
      if ( !*((_DWORD *)v6 + 79) )
        goto LABEL_124;
      v76 = *((_BYTE *)v6 + 320);
      if ( !v76 || v23 != v76 || (unsigned int)v22 < 0x14 )
        goto LABEL_124;
LABEL_33:
      v24 = *((unsigned __int16 *)a4 + 2);
      if ( v22 >= v24 + 38 )
      {
        Buf1 = *(struct _GUID *)((char *)a4 + v24 + 6);
        if ( !memcmp_0(&Buf1, &unk_1806FB0A8, 0x10u) )
          goto LABEL_46;
      }
      goto LABEL_34;
    }
  }
  if ( (unsigned int)v22 > 7 )
    goto LABEL_33;
LABEL_34:
  v25 = *(unsigned __int16 *)a4;
  if ( (unsigned int)v25 > 7
    && (v26 = *((unsigned __int16 *)a4 + 2), v25 >= v26 + 38)
    && (Buf1 = *(struct _GUID *)((char *)a4 + v26 + 6), !memcmp_0(&Buf1, &unk_1806FB0A8, 0x10u)) )
  {
    v28 = (struct _GUID *)((char *)a4 + *((unsigned __int16 *)a4 + 2) + 22);
  }
  else
  {
    if ( v23 == *((_BYTE *)v6 + 320) )
      v27 = a4;
    else
      v27 = (const struct _ITEMIDLIST_RELATIVE *)((char *)a4 + *((unsigned int *)v6 + 79));
    v28 = (struct _GUID *)((char *)v27 + 4);
  }
  Buf1 = *v28;
  v29 = (unsigned int)(*((_DWORD *)v6 + 74) - 1);
  if ( (int)v29 < 0 )
  {
LABEL_44:
    if ( (_DWORD)v29 == -1 )
    {
      v12 = 1;
      goto LABEL_46;
    }
  }
  else
  {
    while ( 1 )
    {
      v30 = *(_QWORD **)(*((_QWORD *)v6 + 38) + 48 * v29);
      v31 = *(_QWORD *)&Buf1.Data1 - *v30;
      if ( *(_QWORD *)&Buf1.Data1 == *v30 )
        v31 = *(_QWORD *)Buf1.Data4 - v30[1];
      if ( !v31 )
        break;
      v29 = (unsigned int)(v29 - 1);
      if ( (int)v29 < 0 )
        goto LABEL_44;
    }
  }
  v12 = 0;
LABEL_46:
  v106 = v7 - v12;
  if ( v7 == v12 && v7 == *((_DWORD *)v6 + 64) )
    return (*(__int64 (__fastcall **)(_QWORD, __int64, ITEMIDLIST *, const struct _ITEMIDLIST_RELATIVE *))(**((_QWORD **)v6 + 18) + 56LL))(
             *((_QWORD *)v6 + 18),
             v105,
             a3,
             a4);
  v32 = *((_DWORD *)v6 + 78);
  if ( v32 == 2 )
  {
    v67 = 0;
    ppMalloc = (LPMALLOC)ILCloneFirst(a3);
    if ( ppMalloc )
    {
      cb_low = 541065216;
      if ( (int)CRegFolder::GetAttributesOf(v6, 1u, (const struct _ITEMID_CHILD *const *)&ppMalloc, &cb_low) >= 0 )
        v67 = cb_low == 0x20000000;
      CoTaskMemFree(ppMalloc);
    }
    v68 = 0;
    ppMalloc = (LPMALLOC)ILCloneFirst((LPCITEMIDLIST)a4);
    if ( ppMalloc )
    {
      cb_low = 541065216;
      if ( (int)CRegFolder::GetAttributesOf(v6, 1u, (const struct _ITEMID_CHILD *const *)&ppMalloc, &cb_low) >= 0 )
        v68 = cb_low == 0x20000000;
      CoTaskMemFree(ppMalloc);
    }
    if ( v67 )
    {
      if ( !v68 )
        goto LABEL_110;
    }
    else if ( v68 )
    {
LABEL_110:
      v33 = 2 * !v67 - 1;
      goto LABEL_111;
    }
    v73 = (struct IShellFolder2 *)v6;
    if ( v6 == (CRegFolder *)40 )
      v73 = 0;
    v33 = (__int16)CompareIDsImpl(v73, v105, (const struct _ITEMIDLIST_RELATIVE *)a3, a4);
LABEL_111:
    v59 = v33 < 0;
    if ( v33 )
    {
LABEL_112:
      if ( v59 )
        return 0xFFFF;
      else
        return v33 > 0;
    }
    goto LABEL_50;
  }
  if ( v32 == 4 )
  {
    v74 = v6;
    if ( v6 == (CRegFolder *)40 )
      v74 = 0;
    v33 = CompareIDsAlphabetical(v74, (unsigned __int16)v105, a3, a4);
    goto LABEL_111;
  }
LABEL_50:
  v33 = 0;
  v34 = a3->mkid.cb;
  if ( (unsigned int)v34 < 3 )
    goto LABEL_132;
  v35 = a3->mkid.abID[0];
  if ( v35 == *((_BYTE *)v6 + 288) )
  {
    v36 = (CRegFolder *)(*((unsigned __int16 *)v6 + 158) + 20LL);
    if ( v34 >= (unsigned __int64)v36 || CRegFolder::_IsDelegate(v36, (const struct IDLREGITEM *)a3) )
    {
      v37 = a3;
      goto LABEL_54;
    }
  }
  if ( *((_DWORD *)v6 + 79) && (v86 = *((_BYTE *)v6 + 320)) != 0 && v35 == v86 && (unsigned int)v34 >= 0x14 )
    v37 = a3;
  else
LABEL_132:
    v37 = 0;
LABEL_54:
  v38 = *(unsigned __int16 *)a4;
  if ( (unsigned int)v38 < 3 )
  {
LABEL_135:
    v41 = 0;
    goto LABEL_58;
  }
  v39 = *((_BYTE *)a4 + 2);
  if ( v39 != *((_BYTE *)v6 + 288)
    || (v40 = (CRegFolder *)(*((unsigned __int16 *)v6 + 158) + 20LL), v38 < (unsigned __int64)v40)
    && !CRegFolder::_IsDelegate(v40, a4) )
  {
    if ( *((_DWORD *)v6 + 79) )
    {
      v87 = *((_BYTE *)v6 + 320);
      if ( v87 )
      {
        if ( v39 == v87 && (unsigned int)v38 >= 0x14 )
        {
          v41 = a4;
          goto LABEL_58;
        }
      }
    }
    goto LABEL_135;
  }
  v41 = a4;
LABEL_58:
  v42 = -2147024882;
  if ( !v37 || !v41 )
    goto LABEL_80;
  v43 = *(unsigned __int16 *)v41;
  if ( (unsigned int)v43 > 7
    && (v44 = *((unsigned __int16 *)v41 + 2), v43 >= v44 + 38)
    && (v101 = (char *)v41 + v44,
        Buf1 = *(struct _GUID *)((char *)v41 + v44 + 6),
        !memcmp_0(&Buf1, &unk_1806FB0A8, 0x10u)) )
  {
    v46 = v101 + 22;
  }
  else
  {
    if ( *((_BYTE *)v41 + 2) == *((_BYTE *)v6 + 320) )
      v45 = v41;
    else
      v45 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v41 + *((unsigned int *)v6 + 79));
    v46 = (char *)v45 + 4;
  }
  v47 = v37->mkid.cb;
  if ( (unsigned int)v47 > 7
    && (v48 = *(unsigned __int16 *)((char *)&v37[1].mkid.cb + 1), v47 >= v48 + 38)
    && (ppMalloc = (LPMALLOC)((char *)v37 + v48),
        Buf1 = *(struct _GUID *)((char *)&v37[2].mkid.cb + v48),
        !memcmp_0(&Buf1, &unk_1806FB0A8, 0x10u)) )
  {
    v50 = (char *)&ppMalloc[2].lpVtbl + 6;
  }
  else
  {
    if ( v37->mkid.abID[0] == *((_BYTE *)v6 + 320) )
      v49 = v37;
    else
      v49 = (ITEMIDLIST *)((char *)v37 + *((unsigned int *)v6 + 79));
    v50 = (char *)&v49[1].mkid.cb + 1;
  }
  v33 = memcmp_0(v50, v46, 0x10u);
  cb_low = v33;
  if ( v33 )
  {
    if ( (v105 & 0x10000000) == 0 )
    {
      v81 = CRegFolder::_IsDelegate(v51, (const struct IDLREGITEM *)v37);
      OrderPure = 0x80;
      if ( v81 )
      {
        v90 = (char *)v81 + v81->cbInner;
        v91 = *(_QWORD *)(v90 + 22) - *(_QWORD *)&CLSID_RemovableDrivesFolder.Data1;
        if ( !v91 )
          v91 = *(_QWORD *)(v90 + 30) - *(_QWORD *)CLSID_RemovableDrivesFolder.Data4;
        if ( v91 )
        {
          v82 = (CRegFolder *)(*(_QWORD *)(v90 + 22) - *(_QWORD *)&CLSID_FrequentPlacesFolder.Data1);
          if ( !v82 )
            v82 = (CRegFolder *)(*(_QWORD *)(v90 + 30) - *(_QWORD *)CLSID_FrequentPlacesFolder.Data4);
          v92 = 128;
          if ( !v82 )
            v92 = 69;
          cb_low = v92;
        }
        else
        {
          LOBYTE(cb_low) = 86;
        }
      }
      else
      {
        cb_low = LOBYTE(v37[1].mkid.cb);
        if ( (unsigned __int8)cb_low <= 0x40u )
          LOBYTE(cb_low) = CRegFolder::_GetOrderPure((CRegFolder *)((char *)v6 - 40), (const struct IDLREGITEM *)v37);
      }
      v84 = CRegFolder::_IsDelegate(v82, v41);
      if ( v84 )
      {
        v93 = (char *)v84 + v84->cbInner;
        v94 = *(_QWORD *)(v93 + 22) - *(_QWORD *)&CLSID_RemovableDrivesFolder.Data1;
        if ( !v94 )
          v94 = *(_QWORD *)(v93 + 30) - *(_QWORD *)CLSID_RemovableDrivesFolder.Data4;
        if ( v94 )
        {
          v95 = *(_QWORD *)(v93 + 22) - *(_QWORD *)&CLSID_FrequentPlacesFolder.Data1;
          if ( !v95 )
            v95 = *(_QWORD *)(v93 + 30) - *(_QWORD *)CLSID_FrequentPlacesFolder.Data4;
          if ( !v95 )
            OrderPure = 69;
        }
        else
        {
          OrderPure = 86;
        }
      }
      else
      {
        OrderPure = *((_BYTE *)v41 + 3);
        if ( OrderPure <= 0x40u )
          OrderPure = CRegFolder::_GetOrderPure((CRegFolder *)((char *)v6 - 40), v41);
      }
      v85 = (unsigned __int8)cb_low - OrderPure;
      if ( v85 )
        goto LABEL_179;
      cb_low = CRegFolder::_ReqItemIndex((CRegFolder *)((char *)v6 - 40), (const struct IDLREGITEM *)v37);
      v96 = CRegFolder::_ReqItemIndex((CRegFolder *)((char *)v6 - 40), v41);
      if ( cb_low == -1 && v96 == -1 )
      {
        ppMalloc = 0;
        pv = 0;
        v97 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&ppMalloc);
        CRegFolder::_GetDisplayName((struct IShellItem2 *)v6 - 5, (const struct IDLREGITEM *)v37, 0, v97);
        v98 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
        CRegFolder::_GetDisplayName((struct IShellItem2 *)v6 - 5, v41, 0, v98);
        v99 = pv;
        v100 = ppMalloc;
        if ( ppMalloc && pv )
        {
          v85 = StrCmpLogicalRestricted((PCWSTR)ppMalloc, (PCWSTR)pv);
          v100 = ppMalloc;
          v99 = pv;
        }
        else
        {
          v85 = 0;
        }
        if ( v99 )
        {
          CoTaskMemFree(v99);
          v100 = ppMalloc;
        }
        if ( v100 )
          CoTaskMemFree(v100);
      }
      else
      {
        v85 = v96 - cb_low;
      }
      if ( v85 )
LABEL_179:
        v33 = v85;
    }
    goto LABEL_80;
  }
  p_cb = 0;
  pv = 0;
  if ( (unsigned int)v47 > 7 )
  {
    v53 = *(unsigned __int16 *)((char *)&v37[1].mkid.cb + 1);
    if ( v47 >= v53 + 38 )
    {
      Buf1 = *(struct _GUID *)((char *)&v37[2].mkid.cb + v53);
      v102 = memcmp_0(&Buf1, &unk_1806FB0A8, 0x10u);
      p_cb = (unsigned __int16 *)pv;
      if ( !v102 )
        p_cb = &v37->mkid.cb;
      pv = p_cb;
    }
    else
    {
      p_cb = (unsigned __int16 *)pv;
    }
  }
  v54 = 0;
  v55 = *(unsigned __int16 *)v41;
  if ( (unsigned int)v55 > 7 )
  {
    v56 = *((unsigned __int16 *)v41 + 2);
    if ( v55 >= v56 + 38 )
    {
      Buf1 = *(struct _GUID *)((char *)v41 + v56 + 6);
      if ( !memcmp_0(&Buf1, &unk_1806FB0A8, 0x10u) )
        v54 = v41;
      p_cb = (unsigned __int16 *)pv;
    }
  }
  if ( p_cb )
  {
    if ( !v54 )
    {
      v58 = 1;
      v33 = 1;
      v57 = a4;
      goto LABEL_82;
    }
    ppMalloc = 0;
    Buf1 = *(struct _GUID *)((char *)p_cb + p_cb[2] + 22);
    if ( (int)CRegFolder::_CreateCachedDelegateFolder(
                (CRegFolder *)((char *)v6 - 40),
                &Buf1,
                (struct IShellFolder **)&ppMalloc,
                0) >= 0 )
    {
      if ( (v105 & 0x90000000) != 0 )
      {
        v57 = a4;
      }
      else
      {
        v77 = ppMalloc;
        v33 = 0;
        cb_low = 0;
        pv = 0;
        QueryInterface = ppMalloc->lpVtbl->QueryInterface;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
        v79 = ((__int64 (__fastcall *)(LPMALLOC, GUID *, LPVOID *))QueryInterface)(
                v77,
                &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
                &pv);
        if ( v79 < 0
          || (v111 = 0,
              v112 = 0,
              v79 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *))(**((_QWORD **)v6 + 18) + 152LL))(
                      *((_QWORD *)v6 + 18),
                      (unsigned __int16)v105,
                      &v111),
              v79 < 0) )
        {
          v57 = a4;
        }
        else
        {
          v80 = ILCloneFirst((LPCITEMIDLIST)Src);
          *(_QWORD *)&Buf1.Data1 = v80;
          if ( v80 )
          {
            v57 = a4;
            v88 = ILCloneFirst((LPCITEMIDLIST)a4);
            v79 = -2147024882;
            if ( v88 )
              v79 = 0;
            if ( v79 >= 0 )
            {
              memset(&var1, 0, sizeof(var1));
              (*(void (__fastcall **)(LPVOID, LPITEMIDLIST, __int128 *, VARIANT *))(*(_QWORD *)pv + 136LL))(
                pv,
                v80,
                &v111,
                &var1);
              memset(&var2, 0, sizeof(var2));
              (*(void (__fastcall **)(LPVOID, LPITEMIDLIST, __int128 *, VARIANT *))(*(_QWORD *)pv + 136LL))(
                pv,
                v88,
                &v111,
                &var2);
              v33 = VariantCompare(&var1, &var2);
              cb_low = v33;
              VariantClear(&var2);
              VariantClear(&var1);
            }
            CoTaskMemFree(v88);
          }
          else
          {
            v79 = -2147024882;
            v57 = a4;
          }
          CoTaskMemFree(v80);
        }
        v89 = pv;
        if ( pv )
        {
          pv = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v89 + 16LL))(v89);
        }
        if ( v79 >= 0 )
          goto LABEL_198;
      }
      SHCompareIDs((struct IShellFolder *)ppMalloc, v105, (const struct _ITEMIDLIST_RELATIVE *)Src, v57, (int *)&cb_low);
      v33 = cb_low;
LABEL_198:
      ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
      goto LABEL_81;
    }
LABEL_80:
    v57 = a4;
LABEL_81:
    v58 = 1;
    goto LABEL_82;
  }
  v57 = a4;
  v58 = 1;
  if ( v54 )
    v33 = -1;
LABEL_82:
  v59 = v33 < 0;
  if ( v33 )
    goto LABEL_112;
  v33 = v106;
  v59 = v106 < 0;
  if ( v106 )
    goto LABEL_112;
  if ( v6 == (CRegFolder *)40 )
    v6 = 0;
  v60 = *(unsigned __int16 *)Src;
  v61 = (char *)Src + v60;
  v62 = (_WORD *)((char *)v57 + *(unsigned __int16 *)v57);
  if ( (char *)Src + v60 && *v61 )
  {
    if ( v62 && *v62 )
    {
      if ( (int)v60 + 2 >= (unsigned int)v60 )
      {
        v63 = (char *)CoTaskMemAlloc((unsigned int)(v60 + 2));
        if ( v63 )
        {
          v64 = 0;
          ppMalloc = 0;
          if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
          {
            v64 = ((__int64 (__fastcall *)(LPMALLOC, char *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v63);
            ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
          }
          memset_0(v63, 0, v64);
          memcpy_0(v63, Src, v60);
          *(_WORD *)&v63[v60] = 0;
          Src = 0;
          v42 = (*(__int64 (__fastcall **)(CRegFolder *, char *, _QWORD, GUID *, void **))(*(_QWORD *)v6 + 40LL))(
                  v6,
                  v63,
                  0,
                  &GUID_000214e6_0000_0000_c000_000000000046,
                  &Src);
          if ( v42 >= 0 )
          {
            ppMalloc = 0;
            if ( (**(int (__fastcall ***)(void *, GUID *, LPMALLOC *))Src)(
                   Src,
                   &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
                   &ppMalloc) < 0 )
            {
              v65 = 0;
            }
            else
            {
              ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
              v65 = v105;
            }
            v42 = (*(__int64 (__fastcall **)(void *, unsigned __int64, _WORD *, _WORD *))(*(_QWORD *)Src + 56LL))(
                    Src,
                    v65 & 0xFFFFFFFFFFFF0000uLL,
                    v61,
                    v62);
            (*(void (__fastcall **)(void *))(*(_QWORD *)Src + 16LL))(Src);
          }
          CoTaskMemFree(v63);
        }
      }
    }
    else
    {
      return 1;
    }
  }
  else
  {
    if ( v62 && *v62 )
      v58 = 0;
    v42 = 0;
    if ( !v58 )
      return 0xFFFF;
  }
  return (unsigned int)v42;
}

```

## disassembly

```asm
0x1800dedc0  push    rbp
0x1800dedc2  push    rbx
0x1800dedc3  push    rsi
0x1800dedc4  push    rdi
0x1800dedc5  push    r12
0x1800dedc7  push    r13
0x1800dedc9  push    r14
0x1800dedcb  push    r15
0x1800dedcd  lea     rbp, [rsp-1Fh]
0x1800dedd2  sub     rsp, 0D8h
0x1800dedd9  mov     rax, cs:__security_cookie
0x1800dede0  xor     rax, rsp
0x1800dede3  mov     [rbp+57h+var_50], rax
0x1800dede7  mov     r13, r9
0x1800dedea  mov     [rsp+110h+pidl], r9
0x1800dedef  mov     r12, r8
0x1800dedf2  mov     [rsp+110h+Src], r8
0x1800dedf7  mov     [rbp+57h+var_D0], rdx
0x1800dedfb  mov     rsi, rcx
0x1800dedfe  test    r8, r8
0x1800dee01  jz      loc_1800DFA9E
0x1800dee07  test    r9, r9
0x1800dee0a  jz      loc_1800DFA9E
0x1800dee10  xorps   xmm0, xmm0
0x1800dee13  movups  [rbp+57h+Buf1], xmm0
0x1800dee17  xor     r14d, r14d
0x1800dee1a  cmp     [rcx+88h], r14
0x1800dee21  jnz     short loc_1800DEE3A
0x1800dee23  mov     rdi, [rcx+90h]
0x1800dee2a  mov     [rcx+88h], r14
0x1800dee31  test    rdi, rdi
0x1800dee34  jnz     loc_1800DF522
0x1800dee3a  mov     rax, [rsi+88h]
0x1800dee41  test    rax, rax
0x1800dee44  jz      short loc_1800DEE4C
0x1800dee46  cmp     [rax], r14w
0x1800dee4a  jnz     short loc_1800DEE80
0x1800dee4c  mov     rcx, [rsi+90h]
0x1800dee53  test    rcx, rcx
0x1800dee56  jz      short loc_1800DEE96
0x1800dee58  lea     rdx, [rbp+57h+Buf1]
0x1800dee5c  call    cs:__imp_IUnknown_GetClassID
0x1800dee62  test    eax, eax
0x1800dee64  js      short loc_1800DEE96
0x1800dee66  mov     r8d, 10h; Size
0x1800dee6c  lea     rdx, CLSID_ShellDesktop; Buf2
0x1800dee73  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800dee77  call    memcmp_0
0x1800dee7c  test    eax, eax
0x1800dee7e  jz      short loc_1800DEE96
0x1800dee80  cmp     [r12], r14w
0x1800dee85  jz      loc_1800DFA9E
0x1800dee8b  cmp     [r13+0], r14w
0x1800dee90  jz      loc_1800DFA9E
0x1800dee96  movzx   ebx, word ptr [r12]
0x1800dee9b  mov     r15d, 2
0x1800deea1  cmp     ebx, 3
0x1800deea4  jb      loc_1800DF4B5
0x1800deeaa  movzx   edi, byte ptr [r12+2]
0x1800deeb0  cmp     dil, [rsi+120h]
0x1800deeb7  jnz     loc_1800DF4A8
0x1800deebd  movzx   ecx, word ptr [rsi+13Ch]
0x1800deec4  add     rcx, 14h
0x1800deec8  cmp     rbx, rcx
0x1800deecb  jb      loc_1800DF48E
0x1800deed1  cmp     ebx, 7
0x1800deed4  jbe     short loc_1800DEEE9
0x1800deed6  movzx   edx, word ptr [r12+4]
0x1800deedc  lea     rcx, [rdx+26h]
0x1800deee0  cmp     rbx, rcx
0x1800deee3  jnb     loc_1800DF626
0x1800deee9  movzx   eax, word ptr [r12]
0x1800deeee  cmp     eax, 7
0x1800deef1  jbe     short loc_1800DEF06
0x1800deef3  movzx   edx, word ptr [r12+4]
0x1800deef9  lea     rcx, [rdx+26h]
0x1800deefd  cmp     rax, rcx
0x1800def00  jnb     loc_1800DF683
0x1800def06  cmp     dil, [rsi+140h]
0x1800def0d  jz      loc_1800DFBB2
0x1800def13  mov     eax, [rsi+13Ch]
0x1800def19  add     rax, r12
0x1800def1c  add     rax, 4
0x1800def20  movups  xmm0, xmmword ptr [rax]
0x1800def23  movups  [rbp+57h+Buf1], xmm0
0x1800def27  mov     edx, [rsi+128h]
0x1800def2d  sub     edx, 1
0x1800def30  js      short loc_1800DEF65
0x1800def32  mov     r10, [rsi+130h]
0x1800def39  mov     r9, qword ptr [rbp+57h+Buf1+8]
0x1800def3d  mov     r11, qword ptr [rbp+57h+Buf1]
0x1800def41  lea     rcx, [rdx+rdx*2]
0x1800def45  add     rcx, rcx
0x1800def48  mov     r8, [r10+rcx*8]
0x1800def4c  mov     rax, r11
0x1800def4f  sub     rax, [r8]
0x1800def52  jnz     short loc_1800DEF5B
0x1800def54  mov     rax, r9
0x1800def57  sub     rax, [r8+8]
0x1800def5b  test    rax, rax
0x1800def5e  jz      short loc_1800DEF70
0x1800def60  sub     edx, 1
0x1800def63  jns     short loc_1800DEF41
0x1800def65  cmp     edx, 0FFFFFFFFh
0x1800def68  jnz     short loc_1800DEF70
0x1800def6a  mov     r14d, 1
0x1800def70  mov     eax, 120h
0x1800def75  mov     rcx, rsi
0x1800def78  movzx   ebx, word ptr [r13+0]
0x1800def7d  cmp     ebx, 3
0x1800def80  jb      loc_1800DF4EA
0x1800def86  movzx   edi, byte ptr [r13+2]
0x1800def8b  cmp     dil, [rcx+rax]
0x1800def8f  jnz     loc_1800DF4DD
0x1800def95  movzx   ecx, word ptr [rsi+13Ch]
0x1800def9c  add     rcx, 14h
0x1800defa0  cmp     rbx, rcx
0x1800defa3  jb      loc_1800DF4C1
0x1800defa9  cmp     ebx, 7
0x1800defac  jbe     short loc_1800DEFC0
0x1800defae  movzx   edx, word ptr [r13+4]
0x1800defb3  lea     rcx, [rdx+26h]
0x1800defb7  cmp     rbx, rcx
0x1800defba  jnb     loc_1800DF656
0x1800defc0  movzx   eax, word ptr [r13+0]
0x1800defc5  cmp     eax, 7
0x1800defc8  jbe     short loc_1800DEFDC
0x1800defca  movzx   edx, word ptr [r13+4]
0x1800defcf  lea     rcx, [rdx+26h]
0x1800defd3  cmp     rax, rcx
0x1800defd6  jnb     loc_1800DF6BD
0x1800defdc  cmp     dil, [rsi+140h]
0x1800defe3  jz      loc_1800DFBBA
0x1800defe9  mov     eax, [rsi+13Ch]
0x1800defef  add     rax, r13
0x1800deff2  add     rax, 4
0x1800deff6  movups  xmm0, xmmword ptr [rax]
0x1800deff9  movups  [rbp+57h+Buf1], xmm0
0x1800deffd  mov     edx, [rsi+128h]
0x1800df003  sub     edx, 1
0x1800df006  js      short loc_1800DF044
0x1800df008  mov     r10, [rsi+130h]
0x1800df00f  mov     r9, qword ptr [rbp+57h+Buf1+8]
0x1800df013  mov     r11, qword ptr [rbp+57h+Buf1]
0x1800df017  nop     word ptr [rax+rax+00000000h]
0x1800df020  lea     rcx, [rdx+rdx*2]
0x1800df024  add     rcx, rcx
0x1800df027  mov     r8, [r10+rcx*8]
0x1800df02b  mov     rax, r11
0x1800df02e  sub     rax, [r8]
0x1800df031  jnz     short loc_1800DF03A
0x1800df033  mov     rax, r9
0x1800df036  sub     rax, [r8+8]
0x1800df03a  test    rax, rax
0x1800df03d  jz      short loc_1800DF04D
0x1800df03f  sub     edx, 1
0x1800df042  jns     short loc_1800DF020
0x1800df044  cmp     edx, 0FFFFFFFFh
0x1800df047  jz      loc_1800DF481
0x1800df04d  xor     r15d, r15d
0x1800df050  mov     edi, 1
0x1800df055  mov     eax, r14d
0x1800df058  sub     eax, r15d
0x1800df05b  mov     [rbp+57h+var_C8], eax
0x1800df05e  jnz     short loc_1800DF06D
0x1800df060  cmp     r14d, [rsi+100h]
0x1800df067  jz      loc_1800DF4F6
0x1800df06d  mov     eax, [rsi+138h]
0x1800df073  cmp     eax, 2
0x1800df076  jz      loc_1800DF3BE
0x1800df07c  cmp     eax, 4
0x1800df07f  jz      loc_1800DF5FF
0x1800df085  xor     r14d, r14d
0x1800df088  movzx   edi, word ptr [r12]
0x1800df08d  cmp     edi, 3
0x1800df090  jb      loc_1800DF5A2
0x1800df096  movzx   r15d, byte ptr [r12+2]
0x1800df09c  cmp     r15b, [rsi+120h]
0x1800df0a3  jnz     loc_1800DF595
0x1800df0a9  movzx   ecx, word ptr [rsi+13Ch]
0x1800df0b0  add     rcx, 14h; this
0x1800df0b4  cmp     rdi, rcx
0x1800df0b7  jb      loc_1800DF584
0x1800df0bd  mov     r15, r12
0x1800df0c0  movzx   edi, word ptr [r13+0]
0x1800df0c5  cmp     edi, 3
0x1800df0c8  jb      loc_1800DF5C8
0x1800df0ce  movzx   r12d, byte ptr [r13+2]
0x1800df0d3  cmp     r12b, [rsi+120h]
0x1800df0da  jnz     loc_1800DF5BB
0x1800df0e0  movzx   ecx, word ptr [rsi+13Ch]
0x1800df0e7  add     rcx, 14h; this
0x1800df0eb  cmp     rdi, rcx
0x1800df0ee  jb      loc_1800DF5AA
0x1800df0f4  mov     rdi, r13
0x1800df0f7  mov     r13d, 8007000Eh
0x1800df0fd  test    r15, r15
0x1800df100  jz      loc_1800DF204
0x1800df106  test    rdi, rdi
0x1800df109  jz      loc_1800DF204
0x1800df10f  movzx   eax, word ptr [rdi]
0x1800df112  cmp     eax, 7
0x1800df115  jbe     short loc_1800DF128
0x1800df117  movzx   edx, word ptr [rdi+4]
0x1800df11b  lea     rcx, [rdx+26h]
0x1800df11f  cmp     rax, rcx
0x1800df122  jnb     loc_1800DFBD7
0x1800df128  movzx   eax, byte ptr [rsi+140h]
0x1800df12f  cmp     [rdi+2], al
0x1800df132  jz      loc_1800DFBC7
0x1800df138  mov     eax, [rsi+13Ch]
0x1800df13e  add     rax, rdi
0x1800df141  lea     r14, [rax+4]
0x1800df145  movzx   r12d, word ptr [r15]
0x1800df149  cmp     r12d, 7
0x1800df14d  jbe     short loc_1800DF161
0x1800df14f  movzx   edx, word ptr [r15+4]
0x1800df154  lea     rcx, [rdx+26h]
0x1800df158  cmp     r12, rcx
0x1800df15b  jnb     loc_1800DFC0B
0x1800df161  movzx   eax, byte ptr [rsi+140h]
0x1800df168  cmp     [r15+2], al
0x1800df16c  jz      loc_1800DFBCF
0x1800df172  mov     eax, [rsi+13Ch]
0x1800df178  add     rax, r15
0x1800df17b  lea     rcx, [rax+4]; Buf1
0x1800df17f  mov     r8d, 10h; Size
0x1800df185  mov     rdx, r14; Buf2
0x1800df188  call    memcmp_0
0x1800df18d  mov     r14d, eax
0x1800df190  mov     [rbp+57h+var_B8], eax
0x1800df193  test    eax, eax
0x1800df195  jnz     short loc_1800DF1F6
0x1800df197  xor     edx, edx
0x1800df199  mov     [rbp+57h+pv], rdx
0x1800df19d  cmp     r12d, 7
0x1800df1a1  jbe     short loc_1800DF1B9
0x1800df1a3  movzx   edx, word ptr [r15+4]
0x1800df1a8  lea     rcx, [rdx+26h]
0x1800df1ac  cmp     r12, rcx
0x1800df1af  jnb     loc_1800DFC46
0x1800df1b5  mov     rdx, [rbp+57h+pv]
0x1800df1b9  xor     r15d, r15d
0x1800df1bc  movzx   eax, word ptr [rdi]
0x1800df1bf  cmp     eax, 7
0x1800df1c2  jbe     short loc_1800DF1D6
0x1800df1c4  movzx   r9d, word ptr [rdi+4]
0x1800df1c9  lea     rcx, [r9+26h]
0x1800df1cd  cmp     rax, rcx
0x1800df1d0  jnb     loc_1800DFC79
0x1800df1d6  test    rdx, rdx
0x1800df1d9  jnz     loc_1800DF763
0x1800df1df  mov     r12, [rsp+110h+pidl]
0x1800df1e4  mov     edx, 1
0x1800df1e9  test    r15, r15
0x1800df1ec  jz      short loc_1800DF20E
0x1800df1ee  mov     r14d, 0FFFFFFFFh
0x1800df1f4  jmp     short loc_1800DF20E
0x1800df1f6  test    [rbp+57h+var_D0], 10000000h
0x1800df1fe  jz      loc_1800DF84A
0x1800df204  mov     r12, [rsp+110h+pidl]
0x1800df209  mov     edx, 1
0x1800df20e  test    r14d, r14d
0x1800df211  jnz     loc_1800DF46E
0x1800df217  mov     r14d, [rbp+57h+var_C8]
0x1800df21b  test    r14d, r14d
0x1800df21e  jnz     loc_1800DF46E
0x1800df224  lea     rcx, [rsi-28h]
0x1800df228  xor     eax, eax
0x1800df22a  test    rcx, rcx
0x1800df22d  cmovz   rsi, rax
0x1800df231  mov     rax, [rsp+110h+Src]
0x1800df236  movzx   ebx, word ptr [rax]
0x1800df239  lea     rdi, [rbx+rax]
0x1800df23d  movzx   r14d, word ptr [r12]
0x1800df242  add     r14, r12
0x1800df245  test    rdi, rdi
0x1800df248  jz      loc_1800DF6F6
0x1800df24e  cmp     word ptr [rdi], 0
0x1800df252  jz      loc_1800DF6F6
0x1800df258  test    r14, r14
0x1800df25b  jz      loc_1800DF903
0x1800df261  cmp     word ptr [r14], 0
0x1800df266  jz      loc_1800DF903
0x1800df26c  lea     edx, [rbx+2]
0x1800df26f  cmp     edx, ebx
0x1800df271  jb      loc_1800DF39B
0x1800df277  mov     ecx, edx; cb
0x1800df279  call    cs:__imp_CoTaskMemAlloc
0x1800df27f  mov     r15, rax
0x1800df282  test    rax, rax
0x1800df285  jz      loc_1800DF39B
0x1800df28b  xor     r12d, r12d
0x1800df28e  mov     [rbp+57h+ppMalloc], r12
0x1800df292  lea     rdx, [rbp+57h+ppMalloc]; ppMalloc
0x1800df296  mov     ecx, 1; dwMemContext
0x1800df29b  call    cs:__imp_CoGetMalloc
0x1800df2a1  test    eax, eax
0x1800df2a3  js      short loc_1800DF2CB
0x1800df2a5  mov     rcx, [rbp+57h+ppMalloc]
  ... truncated ...
```
