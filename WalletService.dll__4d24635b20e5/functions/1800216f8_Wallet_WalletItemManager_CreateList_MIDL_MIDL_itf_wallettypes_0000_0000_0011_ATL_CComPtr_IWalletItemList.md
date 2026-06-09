# Wallet::WalletItemManager::CreateList(__MIDL___MIDL_itf_wallettypes_0000_0000_0011,ATL::CComPtr<IWalletItemList> &)

- ea: `0x1800216f8`
- end: `0x180021ff6`
- name: `?CreateList@WalletItemManager@Wallet@@AEAAJW4__MIDL___MIDL_itf_wallettypes_0000_0000_0011@@AEAV?$CComPtr@UIWalletItemList@@@ATL@@@Z`
- size: `2302`
- prototype: `__int64 __fastcall(__int64 *, int, struct IUnknown **)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022b60`

## callees

- `0x180002214`
- `0x1800039ec`
- `0x180003ae4`
- `0x180003b40`
- `0x1800043b8`
- `0x18000d980`
- `0x180014328`
- `0x18001ed70`
- `0x18001f880`
- `0x1800213d8`
- `0x180021410`
- `0x1800216f8`
- `0x1800227b4`
- `0x180022928`
- `0x1800371d4`
- `0x180038540`
- `0x18003912c`
- `0x180039888`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180021d9e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180021d9e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800218d1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021ae6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021b35`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021b40`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800218d1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021ae6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021b35`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021b40`

## pseudocode

```c
__int64 __fastcall Wallet::WalletItemManager::CreateList(__int64 *a1, int a2, struct IUnknown **a3)
{
  void *v6; // rax
  __int64 v7; // rax
  struct IUnknown *v8; // rsi
  Wallet::Utils *v9; // rcx
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdx
  int v17; // eax
  int FilteredList; // ebx
  __int64 v19; // rax
  __int64 (__fastcall *v20)(__int64 *, __int64, __int64 *); // rbx
  __int64 *v21; // rax
  unsigned int k; // r14d
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, _QWORD, __int64 *); // rbx
  __int64 *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  int v28; // ebx
  int v29; // ebx
  int v30; // ebx
  int v31; // ebx
  __int64 (__fastcall *v32)(__int64 *, __int64, __int64 *); // rbx
  __int64 *v33; // rax
  unsigned int i; // r15d
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, _QWORD, __int64 *); // rbx
  __int64 *v37; // rax
  PROPVARIANT *v38; // rbx
  __int64 v39; // rdi
  int v40; // r8d
  int v41; // r8d
  unsigned __int64 v42; // rdx
  unsigned __int64 v43; // r8
  void (*v44)(void *); // r9
  __int64 v45; // rax
  __int64 (__fastcall *v46)(__int64 *, __int64, PROPVARIANT *, __int64, __int64 *); // rbx
  __int64 *v47; // rax
  unsigned int j; // r14d
  __int64 v49; // rdi
  __int64 (__fastcall *v50)(__int64, _QWORD, __int64 *); // rbx
  __int64 *v51; // rax
  unsigned __int64 v52; // rdx
  unsigned __int64 v53; // r8
  void (*v54)(void *); // r9
  __int64 v56; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v57; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v58; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v59; // [rsp+48h] [rbp-B8h] BYREF
  void *v60; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  PROPVARIANT pvar[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v63; // [rsp+70h] [rbp-90h]
  __int16 v64; // [rsp+78h] [rbp-88h]
  struct _FILETIME v65; // [rsp+80h] [rbp-80h]
  int v66; // [rsp+90h] [rbp-70h] BYREF
  int v67; // [rsp+94h] [rbp-6Ch] BYREF
  PROPVARIANT v68[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v69; // [rsp+A8h] [rbp-58h]
  __int64 v70; // [rsp+B0h] [rbp-50h] BYREF
  int v71; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v72; // [rsp+C0h] [rbp-40h]
  int v73; // [rsp+C8h] [rbp-38h]
  int v74; // [rsp+D0h] [rbp-30h]
  PROPVARIANT *v75; // [rsp+D8h] [rbp-28h]
  int v76; // [rsp+E0h] [rbp-20h]
  int v77; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v78; // [rsp+F0h] [rbp-10h]
  int v79; // [rsp+F8h] [rbp-8h]
  int v80; // [rsp+100h] [rbp+0h]
  PROPVARIANT *v81; // [rsp+108h] [rbp+8h]
  int v82; // [rsp+110h] [rbp+10h]
  unsigned int v83; // [rsp+188h] [rbp+88h] BYREF

  v6 = operator new(0xA0u);
  if ( !v6 )
    return (unsigned int)-2147024882;
  v7 = Wallet::WalletItemList::WalletItemList(v6, a1, (unsigned int)a2);
  if ( (v8 = (struct IUnknown *)v7) == 0 )
    return (unsigned int)-2147024882;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  if ( a2 > 55 )
  {
    if ( a2 <= 62 )
    {
      if ( a2 != 62 )
      {
        v28 = a2 - 56;
        if ( !v28 )
        {
          LODWORD(pvar[0]) = 153;
          goto LABEL_104;
        }
        v29 = v28 - 1;
        if ( !v29 )
        {
          LODWORD(pvar[0]) = 159;
          goto LABEL_104;
        }
        v30 = v29 - 2;
        if ( v30 )
        {
          v31 = v30 - 1;
          if ( v31 )
          {
            if ( v31 != 1 )
              goto LABEL_70;
            v16 = 0xFFFFFFFFLL;
          }
          else
          {
            v16 = 4294967294LL;
          }
        }
        else
        {
          v16 = 4294967293LL;
        }
        goto LABEL_29;
      }
      v26 = 1;
      v27 = 11;
      goto LABEL_46;
    }
    switch ( a2 )
    {
      case 64:
        LODWORD(pvar[0]) = 165;
        goto LABEL_104;
      case 100:
        v16 = 10;
        goto LABEL_29;
      case 400:
        goto LABEL_28;
    }
    if ( a2 != 610 )
      goto LABEL_70;
    v58 = 0;
    v59 = 0;
    v56 = 0;
    v83 = 0;
    v66 = 1;
    if ( (unsigned int)Wallet::Utils::IsRelevanceTracked(v9) )
    {
      v32 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(*a1 + 72);
      v33 = ce::pointerTo<IWalletNotification>(&v58);
      FilteredList = v32(a1, 1, v33);
      if ( FilteredList >= 0 )
      {
        FilteredList = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v58 + 32LL))(v58, &v83);
        if ( FilteredList >= 0 )
        {
          Wallet::Utils::GetWalletLocationManager(&v56);
          (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v56 + 72LL))(v56, &v66);
          if ( v66 )
          {
            for ( i = 0; i < v83; ++i )
            {
              v35 = v58;
              v36 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v58 + 40LL);
              v37 = ce::pointerTo<IWalletNotification>(&v59);
              FilteredList = v36(v35, i, v37);
              if ( FilteredList < 0 )
                goto LABEL_73;
              ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(
                &SystemTimeAsFileTime,
                v59);
              if ( (unsigned int)Wallet::Utils::GetItemFlag(&SystemTimeAsFileTime, 8) )
              {
                ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(&v57, v59);
                if ( !(unsigned int)Wallet::Utils::GetItemFlag(&v57, 4) )
                {
                  v60 = 0;
                  FilteredList = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v59 + 24LL))(v59, &v60);
                  if ( FilteredList < 0 )
                    goto LABEL_73;
                  FilteredList = ((__int64 (__fastcall *)(struct IUnknown *, void *, _QWORD))v8[1].lpVtbl->AddRef)(
                                   &v8[1],
                                   v60,
                                   0);
                  if ( FilteredList < 0 )
                    goto LABEL_73;
                }
              }
            }
          }
          SystemTimeAsFileTime = 0;
          v38 = pvar;
          v39 = 2;
          do
          {
            ce::WrappedPropVariant::WrappedPropVariant((ce::WrappedPropVariant *)v38);
            v38 += 3;
            --v39;
          }
          while ( v39 );
          v57 = 0;
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          v60 = (void *)SystemTimeAsFileTime;
          FilteredList = Wallet::Utils::AddSecondsToFileTime(
                           (Wallet::Utils *)&v60,
                           (struct _FILETIME *)0xFFFFF1F0LL,
                           v40);
          if ( FilteredList >= 0 )
          {
            FilteredList = Wallet::Utils::AddSecondsToFileTime(
                             (Wallet::Utils *)&SystemTimeAsFileTime,
                             (struct _FILETIME *)0x1C20,
                             v41);
            if ( FilteredList >= 0 )
            {
              pvar[1] = v60;
              v65 = SystemTimeAsFileTime;
              v45 = *a1;
              v64 = 64;
              LOWORD(pvar[0]) = 64;
              v46 = *(__int64 (__fastcall **)(__int64 *, __int64, PROPVARIANT *, __int64, __int64 *))(v45 + 88);
              v47 = ce::pointerTo<IWalletNotification>(&v57);
              FilteredList = v46(a1, 611, pvar, 2, v47);
              if ( FilteredList >= 0 )
              {
                FilteredList = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v57 + 32LL))(v57, &v83);
                if ( FilteredList >= 0 )
                {
                  for ( j = 0; j < v83; ++j )
                  {
                    v60 = 0;
                    v67 = 0;
                    if ( (*(int (__fastcall **)(__int64, _QWORD, void **))(*(_QWORD *)v57 + 56LL))(v57, j, &v60) >= 0
                      && ((int (__fastcall *)(struct IUnknown *, void *, int *))v8->lpVtbl[2].Release)(v8, v60, &v67) >= 0
                      && !v67 )
                    {
                      v49 = v57;
                      v50 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v57 + 40LL);
                      v51 = ce::pointerTo<IWalletNotification>(&v59);
                      FilteredList = v50(v49, j, v51);
                      if ( FilteredList < 0 )
                        goto LABEL_87;
                      ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(
                        &v70,
                        v59);
                      if ( !(unsigned int)Wallet::Utils::GetItemFlag(&v70, 4) )
                      {
                        FilteredList = ((__int64 (__fastcall *)(struct IUnknown *, void *, _QWORD))v8[1].lpVtbl->AddRef)(
                                         &v8[1],
                                         v60,
                                         0);
                        if ( FilteredList < 0 )
                          goto LABEL_87;
                      }
                    }
                  }
                  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v57);
                  `vector destructor iterator'(pvar, v52, v53, v54);
                  goto LABEL_101;
                }
              }
            }
          }
LABEL_87:
          ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v57);
          `vector destructor iterator'(pvar, v42, v43, v44);
        }
      }
LABEL_73:
      ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v56);
      ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v59);
      goto LABEL_34;
    }
LABEL_101:
    ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v56);
    ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v59);
LABEL_44:
    ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v58);
    goto LABEL_107;
  }
  if ( a2 == 55 )
  {
    v63 = 0;
    v69 = 0;
    v71 = 3000;
    v77 = 3000;
    v72 = 0;
    *(_OWORD *)pvar = 0;
    LOWORD(pvar[0]) = 22;
    v74 = 3003;
    *(_OWORD *)v68 = 0;
    LOWORD(v68[0]) = 22;
    v75 = pvar;
    v80 = 3003;
    v81 = v68;
    LODWORD(pvar[1]) = 2;
    LODWORD(v68[1]) = 3;
    v73 = 8;
    v76 = 0;
    v78 = 0;
    v79 = 8;
    v82 = 0;
    FilteredList = Wallet::WalletItemManager::GetFilteredList(a1, 1, &v71);
    if ( FilteredList < 0
      || (FilteredList = Wallet::WalletItemManager::GetFilteredList(a1, 1, &v77), FilteredList < 0)
      || (FilteredList = Wallet::WalletItemList::Sort(v8, Wallet::WalletItemList::ProductIdSort), FilteredList < 0) )
    {
      PropVariantClear(v68);
      goto LABEL_31;
    }
    PropVariantClear(v68);
LABEL_52:
    PropVariantClear(pvar);
    goto LABEL_107;
  }
  if ( a2 > 14 )
  {
    if ( a2 != 16 )
    {
      if ( a2 != 18 )
      {
        if ( a2 != 20 )
        {
          if ( a2 != 22 )
          {
            if ( a2 != 50 )
              goto LABEL_70;
            v16 = 4;
LABEL_29:
            v17 = Wallet::WalletItemManager::AddItemsByType(a1, v16, v8);
            goto LABEL_106;
          }
          FilteredList = Wallet::WalletItemManager::AddCardsFromQuery(a1, 1, v8);
          if ( FilteredList < 0 )
            goto LABEL_109;
          FilteredList = Wallet::WalletItemManager::AddItemsByType(a1, 10, v8);
          if ( FilteredList < 0 )
            goto LABEL_109;
          FilteredList = Wallet::WalletItemManager::AddItemsByType(a1, 11, v8);
          if ( FilteredList < 0 )
            goto LABEL_109;
LABEL_28:
          v16 = 13;
          goto LABEL_29;
        }
        v63 = 0;
        LODWORD(v68[0]) = 151;
        *(_OWORD *)pvar = 0;
        LODWORD(pvar[1]) = 1;
        LODWORD(v69) = 0;
        LOWORD(pvar[0]) = 22;
        v68[1] = pvar;
        FilteredList = Wallet::WalletItemManager::GetFilteredList(a1, 3, v68);
        if ( FilteredList < 0 )
        {
LABEL_31:
          PropVariantClear(pvar);
          goto LABEL_109;
        }
        goto LABEL_52;
      }
      v19 = *a1;
      v58 = 0;
      v56 = 0;
      v57 = 0;
      v20 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v19 + 72);
      v83 = 0;
      v21 = ce::pointerTo<IWalletNotification>(&v56);
      FilteredList = v20(a1, 3, v21);
      if ( FilteredList >= 0 )
      {
        FilteredList = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v56 + 32LL))(v56, &v83);
        if ( FilteredList >= 0 )
        {
          for ( k = 0; k < v83; ++k )
          {
            v23 = v56;
            v24 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v56 + 40LL);
            v25 = ce::pointerTo<IWalletNotification>(&v57);
            FilteredList = v24(v23, k, v25);
            if ( FilteredList < 0 )
              goto LABEL_33;
            ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(
              &SystemTimeAsFileTime,
              v57);
            if ( (unsigned int)Wallet::Utils::GetItemFlag(&SystemTimeAsFileTime, 2) )
            {
              v60 = 0;
              FilteredList = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v57 + 24LL))(v57, &v60);
              if ( FilteredList < 0 )
                goto LABEL_33;
              FilteredList = ((__int64 (__fastcall *)(struct IUnknown *, void *, _QWORD))v8[1].lpVtbl->AddRef)(
                               &v8[1],
                               v60,
                               0);
              if ( FilteredList < 0 )
                goto LABEL_33;
            }
          }
          ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v57);
          ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v56);
          goto LABEL_44;
        }
      }
LABEL_33:
      ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v57);
      ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v56);
LABEL_34:
      ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v58);
      goto LABEL_109;
    }
    v26 = 11;
    v27 = 19;
LABEL_46:
    v17 = Wallet::WalletItemManager::GetFilteredList(a1, v26, v27, v8);
    goto LABEL_106;
  }
  if ( a2 == 14 )
  {
    v16 = 2;
    goto LABEL_29;
  }
  v10 = a2 - 1;
  if ( !v10 )
  {
    v14 = 1;
    goto LABEL_17;
  }
  v11 = v10 - 2;
  if ( !v11 )
  {
    v16 = 1;
    goto LABEL_29;
  }
  v12 = v11 - 1;
  if ( v12 )
  {
    v13 = v12 - 3;
    if ( v13 )
    {
      if ( v13 == 4 )
      {
        LODWORD(pvar[0]) = 2005;
LABEL_104:
        v15 = 1;
        goto LABEL_105;
      }
LABEL_70:
      FilteredList = -2147467263;
      goto LABEL_109;
    }
    v14 = 0;
LABEL_17:
    v17 = Wallet::WalletItemManager::AddCardsFromQuery(a1, v14, v8);
    goto LABEL_106;
  }
  LODWORD(pvar[0]) = 350;
  v15 = 3;
LABEL_105:
  LODWORD(v63) = 8;
  pvar[1] = 0;
  v17 = Wallet::WalletItemManager::GetFilteredList(a1, v15, pvar);
LABEL_106:
  FilteredList = v17;
  if ( v17 >= 0 )
  {
LABEL_107:
    FilteredList = 0;
    if ( *a3 != v8 )
      ATL::AtlComPtrAssign(a3, v8);
  }
LABEL_109:
  ((void (__fastcall *)(struct IUnknown *))v8->lpVtbl->Release)(v8);
  return (unsigned int)FilteredList;
}

```

## disassembly

```asm
0x1800216f8  push    rbp
0x1800216fa  push    rbx
0x1800216fb  push    rsi
0x1800216fc  push    rdi
0x1800216fd  push    r12
0x1800216ff  push    r13
0x180021701  push    r14
0x180021703  push    r15
0x180021705  lea     rbp, [rsp-28h]
0x18002170a  sub     rsp, 128h
0x180021711  mov     r14, rcx
0x180021714  mov     r12, r8
0x180021717  mov     ecx, 0A0h; Size
0x18002171c  mov     ebx, edx
0x18002171e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021723  xor     r13d, r13d
0x180021726  test    rax, rax
0x180021729  jz      loc_180021FDB
0x18002172f  mov     r8d, ebx
0x180021732  mov     rdx, r14
0x180021735  mov     rcx, rax
0x180021738  call    ??0WalletItemList@Wallet@@QEAA@PEAUIWalletItemManager@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0011@@@Z; Wallet::WalletItemList::WalletItemList(IWalletItemManager *,__MIDL___MIDL_itf_wallettypes_0000_0000_0011)
0x18002173d  mov     rsi, rax
0x180021740  test    rax, rax
0x180021743  jz      loc_180021FDB
0x180021749  mov     rax, [rax]
0x18002174c  mov     rcx, rsi
0x18002174f  mov     rax, [rax+8]
0x180021753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021758  cmp     ebx, 37h ; '7'
0x18002175b  jg      loc_180021B4B
0x180021761  jz      loc_180021A42
0x180021767  cmp     ebx, 0Eh
0x18002176a  jg      short loc_1800217DC
0x18002176c  jz      short loc_1800217D2
0x18002176e  sub     ebx, 1
0x180021771  jz      short loc_1800217BD
0x180021773  sub     ebx, 2
0x180021776  jz      short loc_1800217B3
0x180021778  sub     ebx, 1
0x18002177b  jz      short loc_18002179C
0x18002177d  sub     ebx, 3
0x180021780  jz      short loc_180021798
0x180021782  cmp     ebx, 4
0x180021785  jnz     loc_180021BDB
0x18002178b  mov     dword ptr [rsp+160h+pvar], 7D5h
0x180021793  jmp     loc_180021F83
0x180021798  xor     edx, edx
0x18002179a  jmp     short loc_1800217C2
0x18002179c  mov     r9d, 1
0x1800217a2  mov     dword ptr [rsp+160h+pvar], 15Eh
0x1800217aa  lea     edx, [r9+2]
0x1800217ae  jmp     loc_180021F8C
0x1800217b3  mov     edx, 1
0x1800217b8  jmp     loc_18002185D
0x1800217bd  mov     edx, 1
0x1800217c2  mov     r8, rsi
0x1800217c5  mov     rcx, r14
0x1800217c8  call    ?AddCardsFromQuery@WalletItemManager@Wallet@@AEAAJW4__MIDL___MIDL_itf_wallettypes_0000_0000_0006@@PEAVWalletItemList@2@@Z; Wallet::WalletItemManager::AddCardsFromQuery(__MIDL___MIDL_itf_wallettypes_0000_0000_0006,Wallet::WalletItemList *)
0x1800217cd  jmp     loc_180021FB0
0x1800217d2  mov     edx, 2
0x1800217d7  jmp     loc_18002185D
0x1800217dc  cmp     ebx, 10h
0x1800217df  jz      loc_180021A29
0x1800217e5  cmp     ebx, 12h
0x1800217e8  jz      loc_1800218DC
0x1800217ee  cmp     ebx, 14h
0x1800217f1  jz      short loc_18002186D
0x1800217f3  mov     eax, 16h
0x1800217f8  cmp     ebx, eax
0x1800217fa  jz      short loc_18002180A
0x1800217fc  cmp     ebx, 32h ; '2'
0x1800217ff  jnz     loc_180021BDB
0x180021805  lea     edx, [rax-12h]
0x180021808  jmp     short loc_18002185D
0x18002180a  mov     r8, rsi
0x18002180d  mov     edx, 1
0x180021812  mov     rcx, r14
0x180021815  call    ?AddCardsFromQuery@WalletItemManager@Wallet@@AEAAJW4__MIDL___MIDL_itf_wallettypes_0000_0000_0006@@PEAVWalletItemList@2@@Z; Wallet::WalletItemManager::AddCardsFromQuery(__MIDL___MIDL_itf_wallettypes_0000_0000_0006,Wallet::WalletItemList *)
0x18002181a  mov     ebx, eax
0x18002181c  test    eax, eax
0x18002181e  js      loc_180021FCA
0x180021824  mov     r8, rsi
0x180021827  mov     edx, 0Ah
0x18002182c  mov     rcx, r14
0x18002182f  call    ?AddItemsByType@WalletItemManager@Wallet@@AEAAJW4__MIDL___MIDL_itf_wallettypes_0000_0000_0001@@PEAVWalletItemList@2@@Z; Wallet::WalletItemManager::AddItemsByType(__MIDL___MIDL_itf_wallettypes_0000_0000_0001,Wallet::WalletItemList *)
0x180021834  mov     ebx, eax
0x180021836  test    eax, eax
0x180021838  js      loc_180021FCA
0x18002183e  mov     r8, rsi
0x180021841  mov     edx, 0Bh
0x180021846  mov     rcx, r14
0x180021849  call    ?AddItemsByType@WalletItemManager@Wallet@@AEAAJW4__MIDL___MIDL_itf_wallettypes_0000_0000_0001@@PEAVWalletItemList@2@@Z; Wallet::WalletItemManager::AddItemsByType(__MIDL___MIDL_itf_wallettypes_0000_0000_0001,Wallet::WalletItemList *)
0x18002184e  mov     ebx, eax
0x180021850  test    eax, eax
0x180021852  js      loc_180021FCA
0x180021858  mov     edx, 0Dh
0x18002185d  mov     r8, rsi
0x180021860  mov     rcx, r14
0x180021863  call    ?AddItemsByType@WalletItemManager@Wallet@@AEAAJW4__MIDL___MIDL_itf_wallettypes_0000_0000_0001@@PEAVWalletItemList@2@@Z; Wallet::WalletItemManager::AddItemsByType(__MIDL___MIDL_itf_wallettypes_0000_0000_0001,Wallet::WalletItemList *)
0x180021868  jmp     loc_180021FB0
0x18002186d  xor     eax, eax
0x18002186f  mov     [rsp+160h+var_138], rsi
0x180021874  mov     [rsp+160h+var_F0], rax
0x180021879  lea     r8, [rbp+60h+var_C8]
0x18002187d  xorps   xmm0, xmm0
0x180021880  mov     dword ptr [rbp+60h+var_C8], 97h
0x180021887  movups  xmmword ptr [rsp+160h+pvar], xmm0
0x18002188c  mov     r9d, 1
0x180021892  mov     dword ptr [rsp+160h+pvar+8], 1
0x18002189a  mov     eax, 16h
0x18002189f  mov     dword ptr [rbp+60h+var_B8], r13d
0x1800218a3  mov     word ptr [rsp+160h+pvar], ax
0x1800218a8  mov     rcx, r14
0x1800218ab  lea     rax, [rsp+160h+pvar]
0x1800218b0  mov     dword ptr [rsp+160h+var_140], r13d
0x1800218b5  lea     edx, [r9+2]
0x1800218b9  mov     [rbp+60h+var_C8+8], rax
0x1800218bd  call    ?GetFilteredList@WalletItemManager@Wallet@@AEAAJW4__MIDL___MIDL_itf_wallettypes_0000_0000_0011@@PEAUFilterCondition@12@IKPEAVWalletItemList@2@@Z; Wallet::WalletItemManager::GetFilteredList(__MIDL___MIDL_itf_wallettypes_0000_0000_0011,Wallet::WalletItemManager::FilterCondition *,uint,ulong,Wallet::WalletItemList *)
0x1800218c2  lea     rcx, [rsp+160h+pvar]; pvar
0x1800218c7  mov     ebx, eax
0x1800218c9  test    eax, eax
0x1800218cb  jns     loc_180021B40
0x1800218d1  call    cs:__imp_PropVariantClear
0x1800218d7  jmp     loc_180021FCA
0x1800218dc  mov     rax, [r14]
0x1800218df  lea     rcx, [rsp+160h+var_130]
0x1800218e4  mov     [rsp+160h+var_120], r13
0x1800218e9  mov     [rsp+160h+var_130], r13
0x1800218ee  mov     [rsp+160h+var_128], r13
0x1800218f3  mov     rbx, [rax+48h]
0x1800218f7  mov     [rbp+60h+arg_18], r13d
0x1800218fe  call    ??$pointerTo@UIWalletNotification@@@ce@@YAPEAPEAUIWalletNotification@@AEAV?$CComPtr@UIWalletNotification@@@ATL@@@Z; ce::pointerTo<IWalletNotification>(ATL::CComPtr<IWalletNotification> &)
0x180021903  mov     r8, rax
0x180021906  mov     edx, 3
0x18002190b  mov     rax, rbx
0x18002190e  mov     rcx, r14
0x180021911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021916  mov     ebx, eax
0x180021918  test    eax, eax
0x18002191a  jns     short loc_18002193F
0x18002191c  lea     rcx, [rsp+160h+var_128]
0x180021921  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180021926  lea     rcx, [rsp+160h+var_130]
0x18002192b  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180021930  lea     rcx, [rsp+160h+var_120]
0x180021935  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18002193a  jmp     loc_180021FCA
0x18002193f  mov     rcx, [rsp+160h+var_130]
0x180021944  lea     rdx, [rbp+60h+arg_18]
0x18002194b  mov     rax, [rcx]
0x18002194e  mov     rax, [rax+20h]
0x180021952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021957  mov     ebx, eax
0x180021959  test    eax, eax
0x18002195b  js      short loc_18002191C
0x18002195d  mov     r14d, r13d
0x180021960  lea     rcx, [rsp+160h+var_128]
0x180021965  cmp     r14d, [rbp+60h+arg_18]
0x18002196c  jnb     loc_180021A0B
0x180021972  mov     rdi, [rsp+160h+var_130]
0x180021977  mov     rax, [rdi]
0x18002197a  mov     rbx, [rax+28h]
0x18002197e  call    ??$pointerTo@UIWalletNotification@@@ce@@YAPEAPEAUIWalletNotification@@AEAV?$CComPtr@UIWalletNotification@@@ATL@@@Z; ce::pointerTo<IWalletNotification>(ATL::CComPtr<IWalletNotification> &)
0x180021983  mov     r8, rax
0x180021986  mov     edx, r14d
0x180021989  mov     rax, rbx
0x18002198c  mov     rcx, rdi
0x18002198f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021994  mov     ebx, eax
0x180021996  test    eax, eax
0x180021998  js      short loc_18002191C
0x18002199a  mov     rdx, [rsp+160h+var_128]
0x18002199f  lea     rcx, [rsp+160h+SystemTimeAsFileTime]
0x1800219a4  call    ??0?$CComPtrBase@UIWalletBackgroundAgentListener@@@ATL@@IEAA@PEAUIWalletBackgroundAgentListener@@@Z; ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(IWalletBackgroundAgentListener *)
0x1800219a9  mov     edx, 2
0x1800219ae  lea     rcx, [rsp+160h+SystemTimeAsFileTime]
0x1800219b3  call    ?GetItemFlag@Utils@Wallet@@YAHV?$CComPtr@UIWalletItem@@@ATL@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0008@@@Z; Wallet::Utils::GetItemFlag(ATL::CComPtr<IWalletItem>,__MIDL___MIDL_itf_wallettypes_0000_0000_0008)
0x1800219b8  test    eax, eax
0x1800219ba  jz      short loc_180021A03
0x1800219bc  mov     rcx, [rsp+160h+var_128]
0x1800219c1  lea     rdx, [rsp+160h+var_110]
0x1800219c6  mov     [rsp+160h+var_110], r13
0x1800219cb  mov     rax, [rcx]
0x1800219ce  mov     rax, [rax+18h]
0x1800219d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219d7  mov     ebx, eax
0x1800219d9  test    eax, eax
0x1800219db  js      loc_18002191C
0x1800219e1  mov     rdx, [rsp+160h+var_110]
0x1800219e6  lea     rcx, [rsi+8]
0x1800219ea  mov     rax, [rcx]
0x1800219ed  xor     r8d, r8d
0x1800219f0  mov     rax, [rax+8]
0x1800219f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219f9  mov     ebx, eax
0x1800219fb  test    eax, eax
0x1800219fd  js      loc_18002191C
0x180021a03  inc     r14d
0x180021a06  jmp     loc_180021960
0x180021a0b  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180021a10  lea     rcx, [rsp+160h+var_130]
0x180021a15  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180021a1a  lea     rcx, [rsp+160h+var_120]
0x180021a1f  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180021a24  jmp     loc_180021FB6
0x180021a29  mov     edx, 0Bh
0x180021a2e  lea     r8d, [rdx+8]
0x180021a32  mov     r9, rsi
0x180021a35  mov     rcx, r14
0x180021a38  call    ?GetFilteredList@WalletItemManager@Wallet@@AEAAJW4__MIDL___MIDL_itf_wallettypes_0000_0000_0011@@0PEAVWalletItemList@2@@Z; Wallet::WalletItemManager::GetFilteredList(__MIDL___MIDL_itf_wallettypes_0000_0000_0011,__MIDL___MIDL_itf_wallettypes_0000_0000_0011,Wallet::WalletItemList *)
0x180021a3d  jmp     loc_180021FB0
0x180021a42  xor     eax, eax
0x180021a44  mov     [rsp+160h+var_138], rsi
0x180021a49  mov     edx, 0BB8h
0x180021a4e  mov     [rsp+160h+var_F0], rax
0x180021a53  mov     [rbp+60h+var_B8], rax
0x180021a57  lea     r8, [rbp+60h+var_A8]
0x180021a5b  mov     eax, 16h
0x180021a60  mov     [rbp+60h+var_A8], edx
0x180021a63  xorps   xmm0, xmm0
0x180021a66  mov     [rbp+60h+var_78], edx
0x180021a69  lea     ecx, [rdx+3]
0x180021a6c  mov     [rbp+60h+var_A0], r13
0x180021a70  movups  xmmword ptr [rsp+160h+pvar], xmm0
0x180021a75  mov     word ptr [rsp+160h+pvar], ax
0x180021a7a  mov     r9d, 2
0x180021a80  xorps   xmm1, xmm1
0x180021a83  mov     [rbp+60h+var_90], ecx
0x180021a86  movups  xmmword ptr [rbp+60h+var_C8], xmm1
0x180021a8a  mov     word ptr [rbp+60h+var_C8], ax
0x180021a8e  lea     rax, [rsp+160h+pvar]
0x180021a93  mov     [rbp+60h+var_88], rax
0x180021a97  lea     edx, [r9-1]
0x180021a9b  lea     rax, [rbp+60h+var_C8]
0x180021a9f  mov     [rbp+60h+var_60], ecx
0x180021aa2  mov     rcx, r14
0x180021aa5  mov     [rbp+60h+var_58], rax
0x180021aa9  mov     dword ptr [rsp+160h+pvar+8], 2
0x180021ab1  mov     dword ptr [rbp+60h+var_C8+8], 3
0x180021ab8  mov     [rbp+60h+var_98], 8
0x180021abf  mov     [rbp+60h+var_80], r13d
0x180021ac3  mov     [rbp+60h+var_70], r13
0x180021ac7  mov     [rbp+60h+var_68], 8
0x180021ace  mov     [rbp+60h+var_50], r13d
0x180021ad2  mov     dword ptr [rsp+160h+var_140], r13d
0x180021ad7  call    ?GetFilteredList@WalletItemManager@Wallet@@AEAAJW4__MIDL___MIDL_itf_wallettypes_0000_0000_0011@@PEAUFilterCondition@12@IKPEAVWalletItemList@2@@Z; Wallet::WalletItemManager::GetFilteredList(__MIDL___MIDL_itf_wallettypes_0000_0000_0011,Wallet::WalletItemManager::FilterCondition *,uint,ulong,Wallet::WalletItemList *)
0x180021adc  mov     ebx, eax
0x180021ade  test    eax, eax
0x180021ae0  jns     short loc_180021AF6
0x180021ae2  lea     rcx, [rbp+60h+var_C8]; pvar
0x180021ae6  call    cs:__imp_PropVariantClear
0x180021aec  lea     rcx, [rsp+160h+pvar]
0x180021af1  jmp     loc_1800218D1
0x180021af6  mov     r9d, 2
0x180021afc  mov     [rsp+160h+var_138], rsi
0x180021b01  lea     r8, [rbp+60h+var_78]
0x180021b05  mov     dword ptr [rsp+160h+var_140], r13d
0x180021b0a  mov     rcx, r14
0x180021b0d  lea     edx, [r9-1]
0x180021b11  call    ?GetFilteredList@WalletItemManager@Wallet@@AEAAJW4__MIDL___MIDL_itf_wallettypes_0000_0000_0011@@PEAUFilterCondition@12@IKPEAVWalletItemList@2@@Z; Wallet::WalletItemManager::GetFilteredList(__MIDL___MIDL_itf_wallettypes_0000_0000_0011,Wallet::WalletItemManager::FilterCondition *,uint,ulong,Wallet::WalletItemList *)
0x180021b16  mov     ebx, eax
0x180021b18  test    eax, eax
0x180021b1a  js      short loc_180021AE2
0x180021b1c  lea     rdx, ?ProductIdSort@WalletItemList@Wallet@@SA_NAEAV?$CComPtr@UIWalletItem@@@ATL@@0@Z; Wallet::WalletItemList::ProductIdSort(ATL::CComPtr<IWalletItem> &,ATL::CComPtr<IWalletItem> &)
0x180021b23  mov     rcx, rsi
0x180021b26  call    ?Sort@WalletItemList@Wallet@@QEAAJP6A_NAEAV?$CComPtr@UIWalletItem@@@ATL@@0@Z@Z; Wallet::WalletItemList::Sort(bool (*)(ATL::CComPtr<IWalletItem> &,ATL::CComPtr<IWalletItem> &))
0x180021b2b  lea     rcx, [rbp+60h+var_C8]; pvar
0x180021b2f  mov     ebx, eax
0x180021b31  test    eax, eax
0x180021b33  js      short loc_180021AE6
0x180021b35  call    cs:__imp_PropVariantClear
0x180021b3b  lea     rcx, [rsp+160h+pvar]; pvar
0x180021b40  call    cs:__imp_PropVariantClear
0x180021b46  jmp     loc_180021FB6
0x180021b4b  cmp     ebx, 3Eh ; '>'
0x180021b4e  jg      short loc_180021BAF
0x180021b50  jz      short loc_180021BA1
0x180021b52  sub     ebx, 38h ; '8'
0x180021b55  jz      short loc_180021B94
0x180021b57  sub     ebx, 1
0x180021b5a  jz      short loc_180021B87
0x180021b5c  sub     ebx, 2
0x180021b5f  jz      short loc_180021B7D
0x180021b61  sub     ebx, 1
0x180021b64  jz      short loc_180021B73
0x180021b66  cmp     ebx, 1
0x180021b69  jnz     short loc_180021BDB
0x180021b6b  or      edx, 0FFFFFFFFh
0x180021b6e  jmp     loc_18002185D
0x180021b73  mov     edx, 0FFFFFFFEh
0x180021b78  jmp     loc_18002185D
0x180021b7d  mov     edx, 0FFFFFFFDh
0x180021b82  jmp     loc_18002185D
0x180021b87  mov     dword ptr [rsp+160h+pvar], 9Fh
0x180021b8f  jmp     loc_180021F83
0x180021b94  mov     dword ptr [rsp+160h+pvar], 99h
0x180021b9c  jmp     loc_180021F83
0x180021ba1  mov     edx, 1
0x180021ba6  lea     r8d, [rdx+0Ah]
  ... truncated ...
```
