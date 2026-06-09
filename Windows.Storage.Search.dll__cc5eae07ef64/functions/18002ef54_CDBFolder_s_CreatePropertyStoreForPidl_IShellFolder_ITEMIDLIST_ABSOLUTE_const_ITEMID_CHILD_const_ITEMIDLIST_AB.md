# CDBFolder::s_CreatePropertyStoreForPidl(IShellFolder *,_ITEMIDLIST_ABSOLUTE const *,_ITEMID_CHILD const *,_ITEMIDLIST_ABSOLUTE const *,IAliasedNamespace *,_GUID const &,void * *)

- ea: `0x18002ef54`
- end: `0x18002f6d9`
- name: `?s_CreatePropertyStoreForPidl@CDBFolder@@SAJPEAUIShellFolder@@PEBU_ITEMIDLIST_ABSOLUTE@@PEFBU_ITEMID_CHILD@@1PEAUIAliasedNamespace@@AEBU_GUID@@PEAPEAX@Z`
- size: `1925`
- prototype: `__int64 __fastcall(IUnknown *punk, LPCITEMIDLIST pidl1, LPCITEMIDLIST pidl2, LPCITEMIDLIST pidl, struct IAliasedNamespace *, const struct _GUID *, LPCITEMIDLIST)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18000782c`
- `0x180014e20`

## callees

- `0x180014498`
- `0x18002ef54`
- `0x18002f6e0`
- `0x180063a68`
- `0x180072cf4`
- `0x1800ea010`

## import_xrefs

- `SHCORE!__imp_StrRetToStrW` at `0x18002f04f`
- `SHCORE!__imp_StrRetToStrW` at `0x18002f10e`
- `SHCORE!__imp_StrRetToStrW` at `0x18002f1cd`
- `SHCORE!__imp_StrRetToStrW` at `0x18002f04f`
- `SHCORE!__imp_StrRetToStrW` at `0x18002f10e`
- `SHCORE!__imp_StrRetToStrW` at `0x18002f1cd`
- `Windows.Storage!ILFree` at `0x18002f467`
- `Windows.Storage!ILFree` at `0x18002f549`
- `Windows.Storage!ILFree` at `0x18002f467`
- `Windows.Storage!ILFree` at `0x18002f549`
- `Windows.Storage!SHGetIDListFromObject` at `0x18002f5f3`
- `Windows.Storage!SHGetIDListFromObject` at `0x18002f5f3`
- `Windows.Storage!SHCreateItemWithParent` at `0x18002f449`
- `Windows.Storage!SHCreateItemWithParent` at `0x18002f449`
- `Windows.Storage!ILCombine` at `0x18002f4de`
- `Windows.Storage!ILCombine` at `0x18002f4de`
- `Windows.Storage!ILGetSize` at `0x18002f518`
- `Windows.Storage!ILGetSize` at `0x18002f614`
- `Windows.Storage!ILGetSize` at `0x18002f518`
- `Windows.Storage!ILGetSize` at `0x18002f614`
- `Windows.Storage!SHBindToFolderIDListParent` at `0x18002eff9`
- `Windows.Storage!SHBindToFolderIDListParent` at `0x18002f0b5`
- `Windows.Storage!SHBindToFolderIDListParent` at `0x18002f174`
- `Windows.Storage!SHBindToFolderIDListParent` at `0x18002f41f`
- `Windows.Storage!SHBindToFolderIDListParent` at `0x18002eff9`
- `Windows.Storage!SHBindToFolderIDListParent` at `0x18002f0b5`
- `Windows.Storage!SHBindToFolderIDListParent` at `0x18002f174`
- `Windows.Storage!SHBindToFolderIDListParent` at `0x18002f41f`
- `Windows.Storage!SHGetItemFromObject` at `0x18002f322`
- `Windows.Storage!SHGetItemFromObject` at `0x18002f322`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002f5a1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002f5ab`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002f5b5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002f6ca`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002f5a1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002f5ab`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002f5b5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002f6ca`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18002ef9a`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18002ef9a`

## string_xrefs

- `0x18002f656`: `onecoreuap\internal\shell\inc\private\ReparseHelpers.h`
- `0x18002f693`: `onecoreuap\internal\shell\inc\private\ReparseHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CDBFolder::s_CreatePropertyStoreForPidl(
        IShellFolder *punk,
        LPCITEMIDLIST pidl1,
        LPCITEMIDLIST pidl2,
        LPCITEMIDLIST pidl,
        struct IAliasedNamespace *a5,
        const struct _GUID *a6,
        LPCITEMIDLIST pidla)
{
  LPCITEMIDLIST v11; // rdi
  LPCITEMIDLIST v12; // r12
  HRESULT v13; // ebx
  IUnknown *v14; // rcx
  HRESULT v15; // ebx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _QWORD, const GUID *, GUID *); // rbx
  int v18; // eax
  __int64 v19; // r8
  IShellFolder *v20; // rdi
  IShellFolder *v21; // rcx
  void *v22; // rbx
  HRESULT v23; // eax
  ITEMIDLIST *v24; // rcx
  PROPVARIANT *v25; // rcx
  void *v27; // rdi
  IShellFolder *v28; // rcx
  IShellFolder *v29; // rcx
  IShellFolder **ppidlLast; // [rsp+20h] [rbp-E0h]
  void *v31; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR ppsz; // [rsp+48h] [rbp-B8h] BYREF
  IShellFolder *psfRoot; // [rsp+50h] [rbp-B0h] BYREF
  void *ppv; // [rsp+58h] [rbp-A8h] BYREF
  void *ppvItem; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v36; // [rsp+68h] [rbp-98h] BYREF
  IShellFolder *psfParent; // [rsp+70h] [rbp-90h] BYREF
  LPCITEMIDLIST v38; // [rsp+78h] [rbp-88h]
  __int64 v39; // [rsp+80h] [rbp-80h] BYREF
  __int64 v40; // [rsp+88h] [rbp-78h]
  LPCITEMIDLIST v41; // [rsp+90h] [rbp-70h]
  LPCITEMIDLIST v42; // [rsp+98h] [rbp-68h] BYREF
  PROPVARIANT v43[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v44; // [rsp+B0h] [rbp-50h]
  PROPVARIANT v45[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v46; // [rsp+C8h] [rbp-38h]
  PROPVARIANT pvar[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v48; // [rsp+E0h] [rbp-20h]
  STRRET pstr; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  v11 = 0;
  v12 = pidla;
  *(_QWORD *)&pidla->mkid.cb = 0;
  ppv = 0;
  v13 = PSCreateMemoryPropertyStore(&GUID_388cec0d_4ef6_4015_a135_d96527fd84e2, &ppv);
  if ( v13 >= 0 )
  {
    *(_OWORD *)pvar = 0;
    v48 = 0;
    *(_OWORD *)v45 = 0;
    v46 = 0;
    *(_OWORD *)v43 = 0;
    v44 = 0;
    ppsz = 0;
    v31 = 0;
    pidla = 0;
    v13 = SHBindToFolderIDListParent(punk, pidl2, &GUID_000214e6_0000_0000_c000_000000000046, &v31, &pidla);
    if ( v13 < 0 )
      goto LABEL_52;
    memset_0(&pstr, 0, sizeof(pstr));
    v13 = (*(__int64 (__fastcall **)(void *, LPCITEMIDLIST, _QWORD, STRRET *))(*(_QWORD *)v31 + 88LL))(
            v31,
            pidla,
            0,
            &pstr);
    if ( v13 >= 0 )
      v13 = StrRetToStrW(&pstr, pidla, &ppsz);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v31 + 16LL))(v31);
    if ( v13 < 0 )
      goto LABEL_52;
    LOWORD(pvar[0]) = 31;
    pvar[1] = ppsz;
    LOWORD(v43[0]) = 0;
    ppsz = 0;
    v31 = 0;
    pidla = 0;
    v13 = SHBindToFolderIDListParent(punk, pidl2, &GUID_000214e6_0000_0000_c000_000000000046, &v31, &pidla);
    if ( v13 >= 0 )
    {
      memset_0(&pstr, 0, sizeof(pstr));
      v13 = (*(__int64 (__fastcall **)(void *, LPCITEMIDLIST, __int64, STRRET *))(*(_QWORD *)v31 + 88LL))(
              v31,
              pidla,
              32769,
              &pstr);
      if ( v13 >= 0 )
        v13 = StrRetToStrW(&pstr, pidla, &ppsz);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v31 + 16LL))(v31);
      if ( v13 >= 0 )
      {
        LOWORD(v43[0]) = 31;
        v43[1] = ppsz;
        LOWORD(v45[0]) = 0;
        ppsz = 0;
        v31 = 0;
        pidla = 0;
        v13 = SHBindToFolderIDListParent(punk, pidl2, &GUID_000214e6_0000_0000_c000_000000000046, &v31, &pidla);
        if ( v13 >= 0 )
        {
          memset_0(&pstr, 0, sizeof(pstr));
          v13 = (*(__int64 (__fastcall **)(void *, LPCITEMIDLIST, __int64, STRRET *))(*(_QWORD *)v31 + 88LL))(
                  v31,
                  pidla,
                  0x8000,
                  &pstr);
          if ( v13 >= 0 )
            v13 = StrRetToStrW(&pstr, pidla, &ppsz);
          (*(void (__fastcall **)(void *))(*(_QWORD *)v31 + 16LL))(v31);
          if ( v13 >= 0 )
          {
            LOWORD(v45[0]) = 31;
            v45[1] = ppsz;
            v13 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *, _QWORD))(*(_QWORD *)ppv + 64LL))(
                    ppv,
                    &PKEY_ItemNameDisplay,
                    pvar,
                    0);
            if ( v13 < 0
              || (v13 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *, _QWORD))(*(_QWORD *)ppv + 64LL))(
                          ppv,
                          &PKEY_ParsingName,
                          v43,
                          0),
                  v13 < 0)
              || (v13 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *, _QWORD))(*(_QWORD *)ppv + 64LL))(
                          ppv,
                          &PKEY_ItemId,
                          v45,
                          0),
                  v13 < 0) )
            {
LABEL_50:
              PropVariantClear(pvar);
              PropVariantClear(v45);
              v25 = v43;
LABEL_51:
              PropVariantClear(v25);
LABEL_52:
              (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
              return (unsigned int)v13;
            }
            v14 = 0;
            ppvItem = 0;
            LODWORD(pidla) = 0;
            v31 = 0;
            if ( !a5 )
            {
LABEL_38:
              if ( v14 )
              {
                v27 = ppv;
                ppsz = 0;
                v13 = SHGetIDListFromObject(v14, (LPITEMIDLIST *)&ppsz);
                if ( v13 < 0 )
                {
LABEL_44:
                  if ( v13 >= 0 )
                    v13 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, LPCITEMIDLIST))ppv)(ppv, a6, v12);
                  goto LABEL_46;
                }
                v39 = 0;
                v40 = 0;
                v41 = (LPCITEMIDLIST)ppsz;
                LODWORD(v40) = ILGetSize((LPCITEMIDLIST)ppsz);
                LOWORD(v39) = 4113;
                v23 = (*(__int64 (__fastcall **)(void *, __int128 *, __int64 *))(*(_QWORD *)v27 + 48LL))(
                        v27,
                        &PKEY_DelegateIDList,
                        &v39);
                v24 = (ITEMIDLIST *)ppsz;
LABEL_43:
                v13 = v23;
                ILFree(v24);
                goto LABEL_44;
              }
LABEL_39:
              if ( !pidl )
              {
                pidl = ILCombine(pidl1, pidl2);
                v13 = pidl == 0 ? 0x8007000E : 0;
                if ( !pidl )
                {
LABEL_46:
                  if ( v31 )
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v31 + 16LL))(v31);
                  if ( ppvItem )
                    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvItem + 16LL))(ppvItem);
                  goto LABEL_50;
                }
                v11 = pidl;
              }
              v22 = ppv;
              v39 = 0;
              v40 = 0;
              v41 = pidl;
              LODWORD(v40) = ILGetSize(pidl);
              LOWORD(v39) = 4113;
              v23 = (*(__int64 (__fastcall **)(void *, __int128 *, __int64 *))(*(_QWORD *)v22 + 48LL))(
                      v22,
                      &PKEY_DelegateIDList,
                      &v39);
              v24 = (ITEMIDLIST *)v11;
              goto LABEL_43;
            }
            if ( (*(int (__fastcall **)(struct IAliasedNamespace *, void **))(*(_QWORD *)a5 + 24LL))(a5, &v31) < 0
              || (*(int (__fastcall **)(void *, LPCITEMIDLIST *))(*(_QWORD *)v31 + 56LL))(v31, &pidla) < 0
              || (_DWORD)pidla != 1 )
            {
LABEL_37:
              v14 = (IUnknown *)ppvItem;
              goto LABEL_38;
            }
            v36 = 0;
            v15 = (*(__int64 (__fastcall **)(void *, _QWORD, __int64 *))(*(_QWORD *)v31 + 64LL))(v31, 0, &v36);
            if ( v15 < 0 )
            {
LABEL_34:
              if ( v36 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
              if ( v15 < 0 )
                goto LABEL_39;
              goto LABEL_37;
            }
            ppsz = 0;
            v15 = SHGetItemFromObject((IUnknown *)punk, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)&ppsz);
            if ( v15 >= 0 )
            {
              LODWORD(psfRoot) = 0;
              if ( !(*(unsigned int (__fastcall **)(__int64, LPWSTR, __int64, IShellFolder **))(*(_QWORD *)v36 + 56LL))(
                      v36,
                      ppsz,
                      805306368,
                      &psfRoot) )
              {
                v16 = v36;
                ppvItem = 0;
                psfRoot = 0;
                v17 = *(__int64 (__fastcall **)(__int64, _QWORD, const GUID *, GUID *))(*(_QWORD *)v36 + 24LL);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&psfRoot);
                ppidlLast = &psfRoot;
                v18 = v17(v16, 0, &BHID_SFObject, &GUID_000214e6_0000_0000_c000_000000000046);
                v15 = v18;
                v11 = 0;
                if ( v18 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x1D5,
                    (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\ReparseHelpers.h",
                    (const char *)(unsigned int)v18,
                    (int)&psfRoot);
                  v29 = psfRoot;
                  if ( psfRoot )
                  {
                    psfRoot = 0;
                    ((void (__fastcall *)(IShellFolder *))v29->lpVtbl->Release)(v29);
                  }
                  goto LABEL_32;
                }
                v20 = psfRoot;
                ppvItem = 0;
                v38 = 0;
                v15 = ReparseRelativeIDListInternal(punk, pidl2, v19, psfRoot);
                if ( v15 < 0 )
                {
                  v11 = 0;
                }
                else
                {
                  psfParent = 0;
                  v42 = 0;
                  v15 = SHBindToFolderIDListParent(
                          v20,
                          v38,
                          &GUID_000214e6_0000_0000_c000_000000000046,
                          (void **)&psfParent,
                          &v42);
                  v11 = 0;
                  if ( v15 >= 0 )
                  {
                    v15 = SHCreateItemWithParent(
                            0,
                            psfParent,
                            v42,
                            &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                            &ppvItem);
                    ((void (__fastcall *)(IShellFolder *))psfParent->lpVtbl->Release)(psfParent);
                  }
                  ILFree((LPITEMIDLIST)v38);
                  if ( v15 >= 0 )
                  {
                    v21 = psfRoot;
                    if ( psfRoot )
                    {
                      psfRoot = 0;
                      ((void (__fastcall *)(IShellFolder *))v21->lpVtbl->Release)(v21);
                    }
                    v15 = 0;
                    goto LABEL_32;
                  }
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1D6,
                  (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\ReparseHelpers.h",
                  (const char *)(unsigned int)v15,
                  (int)ppidlLast);
                v28 = psfRoot;
                if ( psfRoot )
                {
                  psfRoot = 0;
                  ((void (__fastcall *)(IShellFolder *))v28->lpVtbl->Release)(v28);
                }
              }
            }
LABEL_32:
            if ( ppsz )
              (*(void (__fastcall **)(LPWSTR))(*(_QWORD *)ppsz + 16LL))(ppsz);
            goto LABEL_34;
          }
        }
        PropVariantClear(v43);
      }
    }
    v25 = pvar;
    goto LABEL_51;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002ef54  push    rbp
0x18002ef56  push    rbx
0x18002ef57  push    rsi
0x18002ef58  push    rdi
0x18002ef59  push    r12
0x18002ef5b  push    r13
0x18002ef5d  push    r14
0x18002ef5f  push    r15
0x18002ef61  lea     rbp, [rsp-108h]
0x18002ef69  sub     rsp, 208h
0x18002ef70  mov     rsi, r9
0x18002ef73  mov     r15, r8
0x18002ef76  mov     r13, rdx
0x18002ef79  mov     r14, rcx
0x18002ef7c  xor     edi, edi
0x18002ef7e  mov     r12, [rbp+140h+pidl]
0x18002ef85  mov     [r12], rdi
0x18002ef89  mov     [rsp+240h+ppv], rdi
0x18002ef8e  lea     rdx, [rsp+240h+ppv]; ppv
0x18002ef93  lea     rcx, _GUID_388cec0d_4ef6_4015_a135_d96527fd84e2; riid
0x18002ef9a  call    cs:__imp_PSCreateMemoryPropertyStore
0x18002efa0  mov     ebx, eax
0x18002efa2  test    eax, eax
0x18002efa4  js      loc_18002F5CC
0x18002efaa  xorps   xmm0, xmm0
0x18002efad  xor     eax, eax
0x18002efaf  movups  xmmword ptr [rbp+140h+pvar], xmm0
0x18002efb3  mov     [rbp+140h+var_160], rax
0x18002efb7  xorps   xmm1, xmm1
0x18002efba  movups  xmmword ptr [rbp+140h+var_188], xmm1
0x18002efbe  mov     [rbp+140h+var_178], rax
0x18002efc2  movups  xmmword ptr [rbp+140h+var_1A0], xmm0
0x18002efc6  mov     [rbp+140h+var_190], rax
0x18002efca  mov     [rsp+240h+ppsz], rdi
0x18002efcf  mov     [rsp+240h+var_200], rdi
0x18002efd4  mov     [rbp+140h+pidl], rdi
0x18002efdb  lea     rax, [rbp+140h+pidl]
0x18002efe2  mov     [rsp+240h+ppidlLast], rax; ppidlLast
0x18002efe7  lea     r9, [rsp+240h+var_200]; ppv
0x18002efec  lea     r8, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18002eff3  mov     rdx, r15; pidl
0x18002eff6  mov     rcx, r14; psfRoot
0x18002eff9  call    cs:__imp_SHBindToFolderIDListParent
0x18002efff  mov     ebx, eax
0x18002f001  test    eax, eax
0x18002f003  js      loc_18002F5BB
0x18002f009  xor     edx, edx; Val
0x18002f00b  mov     r8d, 110h; Size
0x18002f011  lea     rcx, [rbp+140h+pstr]; void *
0x18002f015  call    memset_0
0x18002f01a  mov     rcx, [rsp+240h+var_200]
0x18002f01f  mov     rax, [rcx]
0x18002f022  lea     r9, [rbp+140h+pstr]
0x18002f026  xor     r8d, r8d
0x18002f029  mov     rdx, [rbp+140h+pidl]
0x18002f030  mov     rax, [rax+58h]
0x18002f034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f039  mov     ebx, eax
0x18002f03b  test    eax, eax
0x18002f03d  js      short loc_18002F057
0x18002f03f  lea     r8, [rsp+240h+ppsz]; ppsz
0x18002f044  mov     rdx, [rbp+140h+pidl]; pidl
0x18002f04b  lea     rcx, [rbp+140h+pstr]; pstr
0x18002f04f  call    cs:__imp_StrRetToStrW
0x18002f055  mov     ebx, eax
0x18002f057  mov     rcx, [rsp+240h+var_200]
0x18002f05c  mov     rax, [rcx]
0x18002f05f  mov     rax, [rax+10h]
0x18002f063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f068  test    ebx, ebx
0x18002f06a  js      loc_18002F5BB
0x18002f070  mov     eax, 1Fh
0x18002f075  mov     word ptr [rbp+140h+pvar], ax
0x18002f079  mov     rax, [rsp+240h+ppsz]
0x18002f07e  mov     [rbp+140h+pvar+8], rax
0x18002f082  mov     word ptr [rbp+140h+var_1A0], di
0x18002f086  mov     [rsp+240h+ppsz], rdi
0x18002f08b  mov     [rsp+240h+var_200], rdi
0x18002f090  mov     [rbp+140h+pidl], rdi
0x18002f097  lea     rax, [rbp+140h+pidl]
0x18002f09e  mov     [rsp+240h+ppidlLast], rax; ppidlLast
0x18002f0a3  lea     r9, [rsp+240h+var_200]; ppv
0x18002f0a8  lea     r8, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18002f0af  mov     rdx, r15; pidl
0x18002f0b2  mov     rcx, r14; psfRoot
0x18002f0b5  call    cs:__imp_SHBindToFolderIDListParent
0x18002f0bb  mov     ebx, eax
0x18002f0bd  test    eax, eax
0x18002f0bf  js      loc_18002F6D0
0x18002f0c5  xor     edx, edx; Val
0x18002f0c7  mov     r8d, 110h; Size
0x18002f0cd  lea     rcx, [rbp+140h+pstr]; void *
0x18002f0d1  call    memset_0
0x18002f0d6  mov     rcx, [rsp+240h+var_200]
0x18002f0db  mov     rax, [rcx]
0x18002f0de  lea     r9, [rbp+140h+pstr]
0x18002f0e2  mov     r8d, 8001h
0x18002f0e8  mov     rdx, [rbp+140h+pidl]
0x18002f0ef  mov     rax, [rax+58h]
0x18002f0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0f8  mov     ebx, eax
0x18002f0fa  test    eax, eax
0x18002f0fc  js      short loc_18002F116
0x18002f0fe  lea     r8, [rsp+240h+ppsz]; ppsz
0x18002f103  mov     rdx, [rbp+140h+pidl]; pidl
0x18002f10a  lea     rcx, [rbp+140h+pstr]; pstr
0x18002f10e  call    cs:__imp_StrRetToStrW
0x18002f114  mov     ebx, eax
0x18002f116  mov     rcx, [rsp+240h+var_200]
0x18002f11b  mov     rax, [rcx]
0x18002f11e  mov     rax, [rax+10h]
0x18002f122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f127  test    ebx, ebx
0x18002f129  js      loc_18002F6D0
0x18002f12f  mov     eax, 1Fh
0x18002f134  mov     word ptr [rbp+140h+var_1A0], ax
0x18002f138  mov     rax, [rsp+240h+ppsz]
0x18002f13d  mov     [rbp+140h+var_1A0+8], rax
0x18002f141  mov     word ptr [rbp+140h+var_188], di
0x18002f145  mov     [rsp+240h+ppsz], rdi
0x18002f14a  mov     [rsp+240h+var_200], rdi
0x18002f14f  mov     [rbp+140h+pidl], rdi
0x18002f156  lea     rax, [rbp+140h+pidl]
0x18002f15d  mov     [rsp+240h+ppidlLast], rax; ppidlLast
0x18002f162  lea     r9, [rsp+240h+var_200]; ppv
0x18002f167  lea     r8, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18002f16e  mov     rdx, r15; pidl
0x18002f171  mov     rcx, r14; psfRoot
0x18002f174  call    cs:__imp_SHBindToFolderIDListParent
0x18002f17a  mov     ebx, eax
0x18002f17c  test    eax, eax
0x18002f17e  js      loc_18002F6C6
0x18002f184  xor     edx, edx; Val
0x18002f186  mov     r8d, 110h; Size
0x18002f18c  lea     rcx, [rbp+140h+pstr]; void *
0x18002f190  call    memset_0
0x18002f195  mov     rcx, [rsp+240h+var_200]
0x18002f19a  mov     rax, [rcx]
0x18002f19d  lea     r9, [rbp+140h+pstr]
0x18002f1a1  mov     r8d, 8000h
0x18002f1a7  mov     rdx, [rbp+140h+pidl]
0x18002f1ae  mov     rax, [rax+58h]
0x18002f1b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1b7  mov     ebx, eax
0x18002f1b9  test    eax, eax
0x18002f1bb  js      short loc_18002F1D5
0x18002f1bd  lea     r8, [rsp+240h+ppsz]; ppsz
0x18002f1c2  mov     rdx, [rbp+140h+pidl]; pidl
0x18002f1c9  lea     rcx, [rbp+140h+pstr]; pstr
0x18002f1cd  call    cs:__imp_StrRetToStrW
0x18002f1d3  mov     ebx, eax
0x18002f1d5  mov     rcx, [rsp+240h+var_200]
0x18002f1da  mov     rax, [rcx]
0x18002f1dd  mov     rax, [rax+10h]
0x18002f1e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1e6  test    ebx, ebx
0x18002f1e8  js      loc_18002F6C6
0x18002f1ee  mov     eax, 1Fh
0x18002f1f3  mov     word ptr [rbp+140h+var_188], ax
0x18002f1f7  mov     rax, [rsp+240h+ppsz]
0x18002f1fc  mov     [rbp+140h+var_188+8], rax
0x18002f200  mov     rcx, [rsp+240h+ppv]
0x18002f205  mov     rax, [rcx]
0x18002f208  xor     r9d, r9d
0x18002f20b  lea     r8, [rbp+140h+pvar]
0x18002f20f  lea     rdx, PKEY_ItemNameDisplay
0x18002f216  mov     rax, [rax+40h]
0x18002f21a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f21f  mov     ebx, eax
0x18002f221  test    eax, eax
0x18002f223  js      loc_18002F59D
0x18002f229  mov     rcx, [rsp+240h+ppv]
0x18002f22e  mov     rax, [rcx]
0x18002f231  xor     r9d, r9d
0x18002f234  lea     r8, [rbp+140h+var_1A0]
0x18002f238  lea     rdx, PKEY_ParsingName
0x18002f23f  mov     rax, [rax+40h]
0x18002f243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f248  mov     ebx, eax
0x18002f24a  test    eax, eax
0x18002f24c  js      loc_18002F59D
0x18002f252  mov     rcx, [rsp+240h+ppv]
0x18002f257  mov     rax, [rcx]
0x18002f25a  xor     r9d, r9d
0x18002f25d  lea     r8, [rbp+140h+var_188]
0x18002f261  lea     rdx, PKEY_ItemId
0x18002f268  mov     rax, [rax+40h]
0x18002f26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f271  mov     ebx, eax
0x18002f273  test    eax, eax
0x18002f275  js      loc_18002F59D
0x18002f27b  mov     rcx, rdi
0x18002f27e  mov     [rsp+240h+ppvItem], rcx
0x18002f283  mov     dword ptr [rbp+140h+pidl], edi
0x18002f289  mov     [rsp+240h+var_200], rdi
0x18002f28e  mov     r8, [rbp+140h+arg_20]
0x18002f295  test    r8, r8
0x18002f298  jz      loc_18002F4CA
0x18002f29e  mov     rax, [r8]
0x18002f2a1  lea     rdx, [rsp+240h+var_200]
0x18002f2a6  mov     rcx, r8
0x18002f2a9  mov     rax, [rax+18h]
0x18002f2ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2b2  test    eax, eax
0x18002f2b4  js      loc_18002F4C5
0x18002f2ba  mov     rcx, [rsp+240h+var_200]
0x18002f2bf  mov     rax, [rcx]
0x18002f2c2  lea     rdx, [rbp+140h+pidl]
0x18002f2c9  mov     rax, [rax+38h]
0x18002f2cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2d2  test    eax, eax
0x18002f2d4  js      loc_18002F4C5
0x18002f2da  cmp     dword ptr [rbp+140h+pidl], 1
0x18002f2e1  jnz     loc_18002F4C5
0x18002f2e7  mov     [rsp+240h+var_1D8], rdi
0x18002f2ec  mov     rcx, [rsp+240h+var_200]
0x18002f2f1  mov     rax, [rcx]
0x18002f2f4  lea     r8, [rsp+240h+var_1D8]
0x18002f2f9  xor     edx, edx
0x18002f2fb  mov     rax, [rax+40h]
0x18002f2ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f304  mov     ebx, eax
0x18002f306  test    eax, eax
0x18002f308  js      loc_18002F4AA
0x18002f30e  mov     [rsp+240h+ppsz], rdi
0x18002f313  lea     r8, [rsp+240h+ppsz]; ppv
0x18002f318  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18002f31f  mov     rcx, r14; punk
0x18002f322  call    cs:__imp_SHGetItemFromObject
0x18002f328  mov     ebx, eax
0x18002f32a  test    eax, eax
0x18002f32c  js      loc_18002F493
0x18002f332  mov     rcx, [rsp+240h+var_1D8]
0x18002f337  mov     dword ptr [rsp+240h+psfRoot], edi
0x18002f33b  mov     rax, [rcx]
0x18002f33e  lea     r9, [rsp+240h+psfRoot]
0x18002f343  mov     r8d, 30000000h
0x18002f349  mov     rdx, [rsp+240h+ppsz]
0x18002f34e  mov     rax, [rax+38h]
0x18002f352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f357  test    eax, eax
0x18002f359  jnz     loc_18002F493
0x18002f35f  mov     rdi, [rsp+240h+var_1D8]
0x18002f364  mov     [rsp+240h+ppvItem], 0
0x18002f36d  mov     [rsp+240h+psfRoot], 0
0x18002f376  mov     rax, [rdi]
0x18002f379  mov     rbx, [rax+18h]
0x18002f37d  lea     rcx, [rsp+240h+psfRoot]
0x18002f382  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f387  lea     rax, [rsp+240h+psfRoot]
0x18002f38c  mov     [rsp+240h+ppidlLast], rax; int
0x18002f391  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x18002f398  lea     r8, BHID_SFObject
0x18002f39f  xor     edx, edx
0x18002f3a1  mov     rcx, rdi
0x18002f3a4  mov     rax, rbx
0x18002f3a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3ac  mov     ebx, eax
0x18002f3ae  xor     edi, edi
0x18002f3b0  test    eax, eax
0x18002f3b2  js      loc_18002F689
0x18002f3b8  mov     rdi, [rsp+240h+psfRoot]
0x18002f3bd  mov     [rsp+240h+ppvItem], 0
0x18002f3c6  mov     [rsp+240h+var_1C8], 0
0x18002f3cf  lea     rax, [rsp+240h+var_1C8]
0x18002f3d4  mov     [rsp+240h+var_210], rax
0x18002f3d9  mov     r9, rdi
0x18002f3dc  mov     rdx, r15
0x18002f3df  mov     rcx, r14
0x18002f3e2  call    ?ReparseRelativeIDListInternal@@YAJPEAUIShellFolder@@PEFBU_ITEMIDLIST_RELATIVE@@AEBU_GUID@@0W4ReparseRelativeIdListFlags@@PEAUIBindCtx@@PEAPEAU2@@Z; ReparseRelativeIDListInternal(IShellFolder *,_ITEMIDLIST_RELATIVE const *,_GUID const &,IShellFolder *,ReparseRelativeIdListFlags,IBindCtx *,_ITEMIDLIST_RELATIVE * *)
0x18002f3e7  mov     ebx, eax
0x18002f3e9  test    eax, eax
0x18002f3eb  js      loc_18002F64A
0x18002f3f1  mov     [rsp+240h+psfParent], 0
0x18002f3fa  mov     [rbp+140h+var_1A8], 0
0x18002f402  lea     rax, [rbp+140h+var_1A8]
0x18002f406  mov     [rsp+240h+ppidlLast], rax; ppidlLast
0x18002f40b  lea     r9, [rsp+240h+psfParent]; ppv
0x18002f410  lea     r8, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18002f417  mov     rdx, [rsp+240h+var_1C8]; pidl
0x18002f41c  mov     rcx, rdi; psfRoot
0x18002f41f  call    cs:__imp_SHBindToFolderIDListParent
0x18002f425  mov     ebx, eax
0x18002f427  xor     edi, edi
0x18002f429  test    eax, eax
0x18002f42b  js      short loc_18002F462
0x18002f42d  lea     rax, [rsp+240h+ppvItem]
0x18002f432  mov     [rsp+240h+ppidlLast], rax; ppvItem
0x18002f437  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18002f43e  mov     r8, [rbp+140h+var_1A8]; pidl
0x18002f442  mov     rdx, [rsp+240h+psfParent]; psfParent
0x18002f447  xor     ecx, ecx; pidlParent
0x18002f449  call    cs:__imp_SHCreateItemWithParent
0x18002f44f  mov     ebx, eax
0x18002f451  mov     rcx, [rsp+240h+psfParent]
0x18002f456  mov     rax, [rcx]
0x18002f459  mov     rax, [rax+10h]
0x18002f45d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f462  mov     rcx, [rsp+240h+var_1C8]; pidl
0x18002f467  call    cs:__imp_ILFree
  ... truncated ...
```
