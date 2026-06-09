# CDBFolder::GetQueryStore(_ITEMID_CHILD const *,PROPERTY_GET_TYPE,IPropertyKeyStore *,IScope *,_GUID const &,void * *)

- ea: `0x18001a200`
- end: `0x18001a63a`
- name: `?GetQueryStore@CDBFolder@@UEAAJPEFBU_ITEMID_CHILD@@W4PROPERTY_GET_TYPE@@PEAUIPropertyKeyStore@@PEAUIScope@@AEBU_GUID@@PEAPEAX@Z`
- size: `1082`
- prototype: `int __high(const struct _ITEMID_CHILD *, enum PROPERTY_GET_TYPE, struct IPropertyKeyStore *, struct IScope *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x18000a730`
- `0x180049b20`

## callees

- `0x180019f18`
- `0x18001a200`
- `0x18001a640`
- `0x18002e0ec`
- `0x180071df0`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x18001a4c5`
- `SHCORE!IUnknown_Set` at `0x18001a4c5`
- `Windows.Storage!ILFree` at `0x18001a4cf`
- `Windows.Storage!ILFree` at `0x18001a62e`
- `Windows.Storage!ILFree` at `0x18001a4cf`
- `Windows.Storage!ILFree` at `0x18001a62e`
- `Windows.Storage!SHGetIDListFromObject` at `0x18001a493`
- `Windows.Storage!SHGetIDListFromObject` at `0x18001a493`
- `Windows.Storage!SHCreateItemFromIDList` at `0x18001a4ae`
- `Windows.Storage!SHCreateItemFromIDList` at `0x18001a4ae`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18001a4e6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18001a4e6`
- `PROPSYS!__imp_PSCreateAggregatePropertyProvider` at `0x18001a589`
- `PROPSYS!__imp_PSCreateAggregatePropertyProvider` at `0x18001a589`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CDBFolder::GetQueryStore(
        __int64 a1,
        const ITEMIDLIST *a2,
        int a3,
        IUnknown *a4,
        __int64 a5,
        IID *riid,
        void **ppv)
{
  void **v9; // rsi
  void *v10; // r14
  int v11; // ebx
  __int64 v13; // rdi
  int v14; // r13d
  _QWORD *v15; // rax
  _QWORD *v16; // rdi
  int v17; // edi
  void *v18; // r13
  void **v19; // rax
  void **v20; // rdi
  unsigned int v21; // r14d
  void *v22; // [rsp+30h] [rbp-28h] BYREF
  _QWORD *v23; // [rsp+38h] [rbp-20h] BYREF
  void *v24; // [rsp+40h] [rbp-18h] BYREF
  LPITEMIDLIST ppidl; // [rsp+A0h] [rbp+48h] BYREF

  v9 = ppv;
  *ppv = 0;
  v22 = 0;
  v10 = (void *)(a1 - 32);
  v11 = CDBFolder::BindToObject((const ITEMIDLIST **)(a1 - 32), a2, 0, &GUID_656c5e34_f857_40d6_9d5c_9c5e6873e160, &v22);
  if ( v11 >= 0 )
  {
    v13 = a5;
    if ( !a5 )
      goto LABEL_11;
    ppv = 0;
    v11 = (**(__int64 (__fastcall ***)(void *, GUID *, void ***))v22)(
            v22,
            &GUID_df3cf8ce_9828_445c_888c_1e9c5b63dfca,
            &ppv);
    if ( v11 >= 0 )
      v11 = (*((__int64 (__fastcall **)(void **, __int64))*ppv + 3))(ppv, v13);
    if ( ppv )
      (*((void (__fastcall **)(void **))*ppv + 2))(ppv);
    if ( v11 >= 0 )
    {
LABEL_11:
      ppidl = (LPITEMIDLIST)v22;
      v24 = 0;
      ppv = 0;
      v11 = -2147024882;
      v14 = -2147024882;
      v15 = operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
      v16 = v15;
      v23 = v15;
      if ( !v15 )
        goto LABEL_30;
      *v15 = &CEnumerableObjectCollection::`vftable'{for `IObjectCollection'};
      v15[1] = &CEnumerableObjectCollection::`vftable'{for `IEnumObjects'};
      v15[2] = &CEnumerableObjectCollection::`vftable'{for `IEnumUnknown'};
      *((_DWORD *)v15 + 6) = 1;
      *(_QWORD *)((char *)v15 + 28) = 4;
      v15[5] = 0;
      v15[6] = 0;
      v15[7] = 0;
      v15[8] = 0;
      v14 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, void ***))*v15)(
              v15,
              &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
              &ppv);
      (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
      if ( v14 >= 0 )
      {
        v17 = (*((__int64 (__fastcall **)(void **, LPITEMIDLIST))*ppv + 5))(ppv, ppidl);
        if ( v17 >= 0 )
          v17 = (*(__int64 (__fastcall **)(void **, GUID *, void **))*ppv)(
                  ppv,
                  &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9,
                  &v24);
        (*((void (__fastcall **)(void **))*ppv + 2))(ppv);
        if ( v17 < 0 )
        {
          v11 = v17;
        }
        else
        {
          v18 = v24;
          *v9 = 0;
          v19 = (void **)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
          v20 = v19;
          ppv = v19;
          if ( v19 )
          {
            *v19 = &CQueryPropStore::`vftable'{for `IPropertyStoreCache'};
            v19[1] = &CQueryPropStore::`vftable'{for `IBatchedPropertyReader'};
            v19[2] = &CQueryPropStore::`vftable'{for `IObjectWithClassIdentity'};
            v19[3] = &CQueryPropStore::`vftable'{for `IObjectProvider'};
            *((_DWORD *)v19 + 8) = 1;
            *((_DWORD *)v19 + 9) = a3;
            v19[5] = v18;
            v19[11] = v10;
            _InterlockedIncrement(&g_cDllRef);
            (*(void (__fastcall **)(void *))(*(_QWORD *)v19[11] + 8LL))(v19[11]);
            (*(void (__fastcall **)(void *))(*(_QWORD *)v20[5] + 8LL))(v20[5]);
          }
          else
          {
            v20 = 0;
          }
          if ( v20 )
          {
            LODWORD(ppv) = 0;
            v11 = (*(__int64 (__fastcall **)(void *, void ***))(*(_QWORD *)v20[5] + 24LL))(v20[5], &ppv);
            if ( v11 >= 0 )
            {
              if ( (unsigned int)ppv <= 1 )
                goto LABEL_21;
              ppidl = 0;
              v11 = PSCreateAggregatePropertyProvider(&GUID_b8158717_9161_46fd_b8d2_26d42185bc69, &ppidl);
              if ( v11 >= 0 )
              {
                v21 = 0;
                if ( (_DWORD)ppv )
                {
                  while ( v11 >= 0 )
                  {
                    v23 = 0;
                    v11 = (*(__int64 (__fastcall **)(void *, _QWORD, GUID *, _QWORD **))(*(_QWORD *)v20[5] + 32LL))(
                            v20[5],
                            v21,
                            &GUID_656c5e34_f857_40d6_9d5c_9c5e6873e160,
                            &v23);
                    if ( v11 >= 0 )
                    {
                      v11 = (*(__int64 (__fastcall **)(LPITEMIDLIST, _QWORD *))(*(_QWORD *)&ppidl->mkid.cb + 24LL))(
                              ppidl,
                              v23);
                      (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
                    }
                    if ( ++v21 >= (unsigned int)ppv )
                    {
                      if ( v11 < 0 )
                        break;
                      goto LABEL_41;
                    }
                  }
                }
                else
                {
LABEL_41:
                  v11 = (**(__int64 (__fastcall ***)(LPITEMIDLIST, GUID *, __int64))&ppidl->mkid.cb)(
                          ppidl,
                          &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                          (__int64)(v20 + 10));
                }
                (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&ppidl->mkid.cb + 16LL))(ppidl);
                if ( v11 >= 0 )
                {
LABEL_21:
                  ppidl = 0;
                  v11 = SHGetIDListFromObject((IUnknown *)v20[11], &ppidl);
                  if ( v11 >= 0 )
                  {
                    v11 = SHCreateItemFromIDList(ppidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v20 + 12);
                    if ( v11 < 0 )
                    {
                      ILFree(ppidl);
                    }
                    else
                    {
                      IUnknown_Set((IUnknown **)v20 + 9, a4);
                      ILFree(ppidl);
                      v11 = QISearch(v20, &`CQueryPropStore::QueryInterface'::`2'::qit, riid, v9);
                    }
                  }
                }
              }
            }
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v20 + 8, 0xFFFFFFFF) == 1 )
            {
              CQueryPropStore::~CQueryPropStore((CQueryPropStore *)v20);
              operator delete(v20, (const struct std::nothrow_t *)0x68);
            }
          }
        }
      }
      else
      {
LABEL_30:
        v11 = v14;
      }
      if ( v24 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v24 + 16LL))(v24);
    }
  }
  if ( v22 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v22 + 16LL))(v22);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001a200  push    rbp
0x18001a202  push    rbx
0x18001a203  push    rsi
0x18001a204  push    rdi
0x18001a205  push    r12
0x18001a207  push    r13
0x18001a209  push    r14
0x18001a20b  push    r15
0x18001a20d  mov     rbp, rsp
0x18001a210  sub     rsp, 58h
0x18001a214  mov     r15, r9
0x18001a217  mov     r12d, r8d
0x18001a21a  xor     r13d, r13d
0x18001a21d  mov     rsi, [rbp+ppv]
0x18001a221  mov     [rsi], r13
0x18001a224  mov     [rbp+var_28], r13
0x18001a228  lea     r14, [rcx-20h]
0x18001a22c  lea     rax, [rbp+var_28]
0x18001a230  mov     [rsp+58h+var_38], rax; ppv
0x18001a235  lea     r9, _GUID_656c5e34_f857_40d6_9d5c_9c5e6873e160; struct _GUID *
0x18001a23c  xor     r8d, r8d; struct IBindCtx *
0x18001a23f  mov     rcx, r14; this
0x18001a242  call    ?BindToObject@CDBFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z; CDBFolder::BindToObject(_ITEMIDLIST_RELATIVE const *,IBindCtx *,_GUID const &,void * *)
0x18001a247  mov     ebx, eax
0x18001a249  test    eax, eax
0x18001a24b  jns     short loc_18001A276
0x18001a24d  mov     rcx, [rbp+var_28]
0x18001a251  test    rcx, rcx
0x18001a254  jz      short loc_18001A263
0x18001a256  mov     rax, [rcx]
0x18001a259  mov     rax, [rax+10h]
0x18001a25d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a262  nop
0x18001a263  mov     eax, ebx
0x18001a265  add     rsp, 58h
0x18001a269  pop     r15
0x18001a26b  pop     r14
0x18001a26d  pop     r13
0x18001a26f  pop     r12
0x18001a271  pop     rdi
0x18001a272  pop     rsi
0x18001a273  pop     rbx
0x18001a274  pop     rbp
0x18001a275  retn
0x18001a276  mov     rdi, [rbp+arg_20]
0x18001a27a  test    rdi, rdi
0x18001a27d  jz      short loc_18001A2C1
0x18001a27f  mov     [rbp+ppv], r13
0x18001a283  mov     rcx, [rbp+var_28]
0x18001a287  mov     rax, [rcx]
0x18001a28a  lea     r8, [rbp+ppv]
0x18001a28e  lea     rdx, _GUID_df3cf8ce_9828_445c_888c_1e9c5b63dfca
0x18001a295  mov     rax, [rax]
0x18001a298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a29d  mov     ebx, eax
0x18001a29f  test    eax, eax
0x18001a2a1  jns     loc_18001A538
0x18001a2a7  mov     rcx, [rbp+ppv]
0x18001a2ab  test    rcx, rcx
0x18001a2ae  jz      short loc_18001A2BD
0x18001a2b0  mov     rax, [rcx]
0x18001a2b3  mov     rax, [rax+10h]
0x18001a2b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2bc  nop
0x18001a2bd  test    ebx, ebx
0x18001a2bf  js      short loc_18001A24D
0x18001a2c1  mov     rax, [rbp+var_28]
0x18001a2c5  mov     [rbp+ppidl], rax
0x18001a2c9  mov     [rbp+var_18], r13
0x18001a2cd  mov     [rbp+ppv], r13
0x18001a2d1  mov     ebx, 8007000Eh
0x18001a2d6  mov     r13d, ebx
0x18001a2d9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a2e0  mov     ecx, 48h ; 'H'; unsigned __int64
0x18001a2e5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001a2ea  mov     rdi, rax
0x18001a2ed  mov     [rbp+var_20], rax
0x18001a2f1  test    rax, rax
0x18001a2f4  jz      loc_18001A533
0x18001a2fa  lea     rax, ??_7CEnumerableObjectCollection@@6BIObjectCollection@@@; const CEnumerableObjectCollection::`vftable'{for `IObjectCollection'}
0x18001a301  mov     [rdi], rax
0x18001a304  lea     rax, ??_7CEnumerableObjectCollection@@6BIEnumObjects@@@; const CEnumerableObjectCollection::`vftable'{for `IEnumObjects'}
0x18001a30b  mov     [rdi+8], rax
0x18001a30f  lea     rax, ??_7CEnumerableObjectCollection@@6BIEnumUnknown@@@; const CEnumerableObjectCollection::`vftable'{for `IEnumUnknown'}
0x18001a316  mov     [rdi+10h], rax
0x18001a31a  mov     dword ptr [rdi+18h], 1
0x18001a321  mov     qword ptr [rdi+1Ch], 4
0x18001a329  xor     eax, eax
0x18001a32b  mov     [rdi+28h], rax
0x18001a32f  mov     [rdi+30h], rax
0x18001a333  mov     [rdi+38h], rax
0x18001a337  mov     [rdi+40h], rax
0x18001a33b  mov     rax, [rdi]
0x18001a33e  lea     r8, [rbp+ppv]
0x18001a342  lea     rdx, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295
0x18001a349  mov     rcx, rdi
0x18001a34c  mov     rax, [rax]
0x18001a34f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a354  mov     r13d, eax
0x18001a357  mov     rcx, [rdi]
0x18001a35a  mov     rax, [rcx+10h]
0x18001a35e  mov     rcx, rdi
0x18001a361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a366  test    r13d, r13d
0x18001a369  js      loc_18001A533
0x18001a36f  mov     rcx, [rbp+ppv]
0x18001a373  mov     rax, [rcx]
0x18001a376  mov     rdx, [rbp+ppidl]
0x18001a37a  mov     rax, [rax+28h]
0x18001a37e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a383  mov     edi, eax
0x18001a385  test    eax, eax
0x18001a387  js      short loc_18001A3A5
0x18001a389  mov     rcx, [rbp+ppv]
0x18001a38d  mov     rax, [rcx]
0x18001a390  lea     r8, [rbp+var_18]
0x18001a394  lea     rdx, _GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9
0x18001a39b  mov     rax, [rax]
0x18001a39e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3a3  mov     edi, eax
0x18001a3a5  mov     rcx, [rbp+ppv]
0x18001a3a9  mov     rax, [rcx]
0x18001a3ac  mov     rax, [rax+10h]
0x18001a3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3b5  test    edi, edi
0x18001a3b7  js      loc_18001A52F
0x18001a3bd  mov     r13, [rbp+var_18]
0x18001a3c1  mov     qword ptr [rsi], 0
0x18001a3c8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a3cf  mov     ecx, 68h ; 'h'; unsigned __int64
0x18001a3d4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001a3d9  mov     rdi, rax
0x18001a3dc  mov     [rbp+ppv], rax
0x18001a3e0  test    rax, rax
0x18001a3e3  jz      loc_18001A552
0x18001a3e9  lea     rax, ??_7CQueryPropStore@@6BIPropertyStoreCache@@@; const CQueryPropStore::`vftable'{for `IPropertyStoreCache'}
0x18001a3f0  mov     [rdi], rax
0x18001a3f3  lea     rax, ??_7CQueryPropStore@@6BIBatchedPropertyReader@@@; const CQueryPropStore::`vftable'{for `IBatchedPropertyReader'}
0x18001a3fa  mov     [rdi+8], rax
0x18001a3fe  lea     rax, ??_7CQueryPropStore@@6BIObjectWithClassIdentity@@@; const CQueryPropStore::`vftable'{for `IObjectWithClassIdentity'}
0x18001a405  mov     [rdi+10h], rax
0x18001a409  lea     rax, ??_7CQueryPropStore@@6BIObjectProvider@@@; const CQueryPropStore::`vftable'{for `IObjectProvider'}
0x18001a410  mov     [rdi+18h], rax
0x18001a414  mov     dword ptr [rdi+20h], 1
0x18001a41b  mov     [rdi+24h], r12d
0x18001a41f  mov     [rdi+28h], r13
0x18001a423  mov     [rdi+58h], r14
0x18001a427  lock inc cs:?g_cDllRef@@3JA; long g_cDllRef
0x18001a42e  mov     rcx, [rdi+58h]
0x18001a432  mov     rax, [rcx]
0x18001a435  mov     rax, [rax+8]
0x18001a439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a43e  mov     rcx, [rdi+28h]
0x18001a442  mov     rax, [rcx]
0x18001a445  mov     rax, [rax+8]
0x18001a449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a44e  nop
0x18001a44f  test    rdi, rdi
0x18001a452  jz      loc_18001A4FD
0x18001a458  mov     dword ptr [rbp+ppv], 0
0x18001a45f  mov     rcx, [rdi+28h]
0x18001a463  mov     rax, [rcx]
0x18001a466  lea     rdx, [rbp+ppv]
0x18001a46a  mov     rax, [rax+18h]
0x18001a46e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a473  mov     ebx, eax
0x18001a475  test    eax, eax
0x18001a477  js      short loc_18001A4EE
0x18001a479  cmp     dword ptr [rbp+ppv], 1
0x18001a47d  ja      loc_18001A576
0x18001a483  mov     [rbp+ppidl], 0
0x18001a48b  lea     rdx, [rbp+ppidl]; ppidl
0x18001a48f  mov     rcx, [rdi+58h]; punk
0x18001a493  call    cs:__imp_SHGetIDListFromObject
0x18001a499  mov     ebx, eax
0x18001a49b  test    eax, eax
0x18001a49d  js      short loc_18001A4EE
0x18001a49f  lea     r8, [rdi+60h]; ppv
0x18001a4a3  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18001a4aa  mov     rcx, [rbp+ppidl]; pidl
0x18001a4ae  call    cs:__imp_SHCreateItemFromIDList
0x18001a4b4  mov     ebx, eax
0x18001a4b6  test    eax, eax
0x18001a4b8  js      loc_18001A62A
0x18001a4be  lea     rcx, [rdi+48h]; ppunk
0x18001a4c2  mov     rdx, r15; punk
0x18001a4c5  call    cs:__imp_IUnknown_Set
0x18001a4cb  mov     rcx, [rbp+ppidl]; pidl
0x18001a4cf  call    cs:__imp_ILFree
0x18001a4d5  mov     r9, rsi; ppv
0x18001a4d8  mov     r8, [rbp+riid]; riid
0x18001a4dc  lea     rdx, ?qit@?1??QueryInterface@CQueryPropStore@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; pqit
0x18001a4e3  mov     rcx, rdi; that
0x18001a4e6  call    cs:__imp_QISearch
0x18001a4ec  mov     ebx, eax
0x18001a4ee  mov     eax, 0FFFFFFFFh
0x18001a4f3  lock xadd [rdi+20h], eax
0x18001a4f8  cmp     eax, 1
0x18001a4fb  jz      short loc_18001A518
0x18001a4fd  mov     rcx, [rbp+var_18]
0x18001a501  test    rcx, rcx
0x18001a504  jz      short loc_18001A513
0x18001a506  mov     rax, [rcx]
0x18001a509  mov     rax, [rax+10h]
0x18001a50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a512  nop
0x18001a513  jmp     loc_18001A24D
0x18001a518  mov     rcx, rdi; this
0x18001a51b  call    ??1CQueryPropStore@@AEAA@XZ; CQueryPropStore::~CQueryPropStore(void)
0x18001a520  mov     edx, 68h ; 'h'; struct std::nothrow_t *
0x18001a525  mov     rcx, rdi; void *
0x18001a528  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a52d  jmp     short loc_18001A4FD
0x18001a52f  mov     ebx, edi
0x18001a531  jmp     short loc_18001A4FD
0x18001a533  mov     ebx, r13d
0x18001a536  jmp     short loc_18001A4FD
0x18001a538  mov     rcx, [rbp+ppv]
0x18001a53c  mov     rax, [rcx]
0x18001a53f  mov     rdx, rdi
0x18001a542  mov     rax, [rax+18h]
0x18001a546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a54b  mov     ebx, eax
0x18001a54d  jmp     loc_18001A2A7
0x18001a552  xor     edi, edi
0x18001a554  jmp     loc_18001A44F
0x18001a559  mov     rcx, [rbp+ppidl]
0x18001a55d  mov     rax, [rcx]
0x18001a560  mov     rax, [rax+10h]
0x18001a564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a569  test    ebx, ebx
0x18001a56b  jns     loc_18001A483
0x18001a571  jmp     loc_18001A4EE
0x18001a576  mov     [rbp+ppidl], 0
0x18001a57e  lea     rdx, [rbp+ppidl]
0x18001a582  lea     rcx, _GUID_b8158717_9161_46fd_b8d2_26d42185bc69
0x18001a589  call    cs:__imp_PSCreateAggregatePropertyProvider
0x18001a58f  mov     ebx, eax
0x18001a591  test    eax, eax
0x18001a593  js      loc_18001A4EE
0x18001a599  xor     r14d, r14d
0x18001a59c  cmp     dword ptr [rbp+ppv], r14d
0x18001a5a0  jbe     short loc_18001A609
0x18001a5a2  test    ebx, ebx
0x18001a5a4  js      short loc_18001A559
0x18001a5a6  mov     [rbp+var_20], 0
0x18001a5ae  mov     rcx, [rdi+28h]
0x18001a5b2  mov     rax, [rcx]
0x18001a5b5  lea     r9, [rbp+var_20]
0x18001a5b9  lea     r8, _GUID_656c5e34_f857_40d6_9d5c_9c5e6873e160
0x18001a5c0  mov     edx, r14d
0x18001a5c3  mov     rax, [rax+20h]
0x18001a5c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5cc  mov     ebx, eax
0x18001a5ce  test    eax, eax
0x18001a5d0  js      short loc_18001A5F8
0x18001a5d2  mov     rcx, [rbp+ppidl]
0x18001a5d6  mov     rax, [rcx]
0x18001a5d9  mov     rdx, [rbp+var_20]
0x18001a5dd  mov     rax, [rax+18h]
0x18001a5e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5e6  mov     ebx, eax
0x18001a5e8  mov     rcx, [rbp+var_20]
0x18001a5ec  mov     rax, [rcx]
0x18001a5ef  mov     rax, [rax+10h]
0x18001a5f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5f8  inc     r14d
0x18001a5fb  cmp     r14d, dword ptr [rbp+ppv]
0x18001a5ff  jb      short loc_18001A5A2
0x18001a601  test    ebx, ebx
0x18001a603  js      loc_18001A559
0x18001a609  mov     rcx, [rbp+ppidl]
0x18001a60d  mov     rax, [rcx]
0x18001a610  lea     r8, [rdi+50h]
0x18001a614  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18001a61b  mov     rax, [rax]
0x18001a61e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a623  mov     ebx, eax
0x18001a625  jmp     loc_18001A559
0x18001a62a  mov     rcx, [rbp+ppidl]; pidl
0x18001a62e  call    cs:__imp_ILFree
0x18001a634  jmp     loc_18001A4EE
```
