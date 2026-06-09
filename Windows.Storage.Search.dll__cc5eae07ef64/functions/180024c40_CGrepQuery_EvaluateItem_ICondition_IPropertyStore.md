# CGrepQuery::_EvaluateItem(ICondition *,IPropertyStore * *)

- ea: `0x180024c40`
- end: `0x180025ea5`
- name: `?_EvaluateItem@CGrepQuery@@AEAAJPEAUICondition@@PEAPEAUIPropertyStore@@@Z`
- size: `4709`
- prototype: `__int64 __fastcall(CGrepQuery *__hidden this, struct ICondition *, struct IPropertyStore **)`
- caller_count: `1`
- callee_count: `40`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180024130`

## callees

- `0x180014498`
- `0x180014e08`
- `0x180014e20`
- `0x18001e4c4`
- `0x180022cf4`
- `0x180024c40`
- `0x1800261e0`
- `0x180026bc0`
- `0x180026c80`
- `0x1800275d4`
- `0x180031548`
- `0x18003b150`
- `0x18003b1b0`
- `0x18003f9f8`
- `0x18003fba8`
- `0x180040020`
- `0x180043888`
- `0x1800438d0`
- `0x180045428`
- `0x18004c12c`
- `0x180051314`
- `0x180056bdc`
- `0x180063a68`
- `0x1800641a8`
- `0x1800668c0`
- `0x180066f8c`
- `0x180066fbc`
- `0x18006700c`
- `0x18006711c`
- `0x180067340`
- `0x180067368`
- `0x18006ce58`
- `0x18006d72c`
- `0x180071dc0`
- `0x180071df0`
- `0x1800878e0`
- `0x18008fb28`
- `0x1800928ac`
- `0x1800930e0`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x180024eed`
- `SHCORE!IUnknown_Set` at `0x180024efe`
- `SHCORE!IUnknown_Set` at `0x180024f14`
- `SHCORE!IUnknown_Set` at `0x180024f25`
- `SHCORE!IUnknown_Set` at `0x180025113`
- `SHCORE!IUnknown_Set` at `0x180025527`
- `SHCORE!IUnknown_Set` at `0x1800256b0`
- `SHCORE!IUnknown_Set` at `0x180024eed`
- `SHCORE!IUnknown_Set` at `0x180024efe`
- `SHCORE!IUnknown_Set` at `0x180024f14`
- `SHCORE!IUnknown_Set` at `0x180024f25`
- `SHCORE!IUnknown_Set` at `0x180025113`
- `SHCORE!IUnknown_Set` at `0x180025527`
- `SHCORE!IUnknown_Set` at `0x1800256b0`
- `Windows.Storage!SHGetIDListFromObject` at `0x18002545b`
- `Windows.Storage!SHGetIDListFromObject` at `0x18002545b`
- `Windows.Storage!SHCreateItemFromIDList` at `0x180025c93`
- `Windows.Storage!SHCreateItemFromIDList` at `0x180025c93`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025b70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025b70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025b93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025b93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002548b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800254c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002548b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800254c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b10`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180025032`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180025032`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800257c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800257c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180025088`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800259e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180025088`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800259e5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800259cd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800259cd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x1800256ec`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x1800256ec`
- `PROPSYS!PropVariantToInt32` at `0x18002501a`
- `PROPSYS!PropVariantToInt32` at `0x18002501a`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180025600`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180025600`
- `PROPSYS!__imp_PSCreatePropertyKeyStore` at `0x180025a0c`
- `PROPSYS!__imp_PSCreatePropertyKeyStore` at `0x180025a0c`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall CGrepQuery::_EvaluateItem(CGrepQuery *this, IUnknown *a2, IUnknown **a3)
{
  int KeyArrayFromPropertyKeyStore; // esi
  unsigned int v5; // r14d
  int v6; // r8d
  IUnknown *v7; // r13
  IUnknown *v8; // r14
  unsigned int v9; // esi
  int v10; // r12d
  int v11; // r15d
  int v12; // esi
  void *v13; // rcx
  IUnknown *v14; // rax
  LONG v15; // r14d
  HRESULT v16; // esi
  int v17; // esi
  int v18; // eax
  int v19; // ecx
  int v20; // r8d
  int DoesItemMatchConditionWorker; // esi
  BOOL v22; // r14d
  int v23; // ecx
  int v24; // r8d
  __int64 *v25; // rax
  IUnknown *v26; // rcx
  __int64 v27; // rcx
  IUnknown *v28; // rcx
  IUnknown *v29; // rcx
  IUnknown *v30; // rcx
  IUnknown *v31; // rcx
  __int64 v32; // rcx
  void *v33; // rcx
  GUID v35; // xmm6
  IUnknown *v36; // r15
  bool v37; // r14
  HRESULT v38; // esi
  void *v39; // rax
  void *v40; // rcx
  IUnknown **v41; // r14
  struct _RTL_CRITICAL_SECTION *v42; // rcx
  void *v43; // rdi
  __int64 v44; // r15
  void *v45; // rax
  CCachedFSFolderPropertyStore *v46; // rax
  CCachedFSFolderPropertyStore *v47; // r13
  HRESULT v48; // r12d
  __int64 v49; // r8
  __int64 v50; // rcx
  void *v51; // rcx
  _QWORD *v52; // rax
  IUnknown *v53; // rcx
  HLOCAL v54; // rcx
  int v55; // eax
  unsigned int v56; // r13d
  char *v57; // r14
  int v58; // eax
  int v59; // ecx
  __int64 v60; // rdx
  __int64 v61; // rax
  bool v62; // zf
  BOOL v63; // eax
  void *v64; // rcx
  __int64 v65; // rdi
  struct _RTL_CRITICAL_SECTION *v66; // r14
  __int16 SystemPreferredLocale; // ax
  unsigned int i; // r8d
  __int64 *v69; // rax
  HRESULT v70; // eax
  __int64 *v71; // r9
  const struct _GUID *v72; // r8
  int v73; // eax
  __int64 v74; // rdx
  struct CONDITIONEVALPROPS *v75; // r8
  __int64 *MatchedLeafConditions; // rsi
  __int64 v77; // r14
  __int64 v78; // r15
  GUID *pdwType; // [rsp+20h] [rbp-258h]
  LONG plRet[2]; // [rsp+40h] [rbp-238h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-230h] BYREF
  IUnknown *v82[2]; // [rsp+50h] [rbp-228h] BYREF
  LPVOID pv[2]; // [rsp+60h] [rbp-218h] BYREF
  int v84; // [rsp+70h] [rbp-208h] BYREF
  void *v85; // [rsp+78h] [rbp-200h] BYREF
  IUnknown *punk; // [rsp+80h] [rbp-1F8h] BYREF
  IUnknown *v87; // [rsp+88h] [rbp-1F0h] BYREF
  IUnknown *v88; // [rsp+90h] [rbp-1E8h]
  PROPVARIANT propvarIn[2]; // [rsp+98h] [rbp-1E0h] BYREF
  __int64 v90; // [rsp+A8h] [rbp-1D0h]
  IUnknown **v91; // [rsp+B0h] [rbp-1C8h]
  void *v92; // [rsp+B8h] [rbp-1C0h] BYREF
  __int64 v93; // [rsp+C0h] [rbp-1B8h]
  __int64 v94; // [rsp+C8h] [rbp-1B0h]
  _QWORD v95[2]; // [rsp+D0h] [rbp-1A8h] BYREF
  int v96; // [rsp+E0h] [rbp-198h]
  _QWORD v97[4]; // [rsp+E4h] [rbp-194h] BYREF
  int v98; // [rsp+104h] [rbp-174h]
  int v99; // [rsp+108h] [rbp-170h]
  _DWORD v100[9]; // [rsp+10Ch] [rbp-16Ch] BYREF
  void **v101; // [rsp+130h] [rbp-148h] BYREF
  IUnknown *v102; // [rsp+138h] [rbp-140h] BYREF
  IUnknown *ppunk; // [rsp+140h] [rbp-138h] BYREF
  __int64 v104; // [rsp+148h] [rbp-130h]
  IUnknown *v105[2]; // [rsp+150h] [rbp-128h] BYREF
  __int64 v106; // [rsp+160h] [rbp-118h]
  __int64 v107; // [rsp+168h] [rbp-110h] BYREF
  __int64 v108; // [rsp+170h] [rbp-108h]
  int v109; // [rsp+178h] [rbp-100h]
  HDPA hdpa[2]; // [rsp+180h] [rbp-F8h]
  int v111; // [rsp+190h] [rbp-E8h]
  __int64 v112; // [rsp+198h] [rbp-E0h]
  __int128 v113; // [rsp+1A0h] [rbp-D8h]
  __int128 v114; // [rsp+1B0h] [rbp-C8h]
  __int128 v115; // [rsp+1C0h] [rbp-B8h]
  __int128 v116; // [rsp+1D0h] [rbp-A8h]
  int v117; // [rsp+1E0h] [rbp-98h]
  IUnknown *v118; // [rsp+1E8h] [rbp-90h] BYREF
  unsigned __int64 v119; // [rsp+1F0h] [rbp-88h]
  __int64 v120; // [rsp+1F8h] [rbp-80h]
  char *v121; // [rsp+200h] [rbp-78h]
  __int64 v122[2]; // [rsp+210h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v91 = a3;
  punk = a2;
  *(_QWORD *)&v100[5] = this;
  *(_QWORD *)&v100[7] = a3;
  *a3 = 0;
  KeyArrayFromPropertyKeyStore = 0;
  if ( *((_QWORD *)this + 13) )
    goto LABEL_2;
  v85 = 0;
  CGrepQuery::_GetFastProperties(this, (const struct _GUID *)a2, &v85);
  hMem = 0;
  plRet[0] = 0;
  v50 = *((_QWORD *)this + 12);
  if ( !v50 || !v85 )
  {
    KeyArrayFromPropertyKeyStore = GetKeyArrayFromPropertyKeyStore(
                                     *((struct IPropertyKeyStore **)this + 11),
                                     (struct _tagpropertykey **)&hMem,
                                     (unsigned int *)plRet);
    goto LABEL_114;
  }
  v82[0] = 0;
  KeyArrayFromPropertyKeyStore = GetIntersectionOfPropertyKeyStores(v50, v85, v49, v82);
  if ( KeyArrayFromPropertyKeyStore >= 0 )
  {
    KeyArrayFromPropertyKeyStore = GetKeyArrayFromTwoPropertyKeyStores(
                                     *((struct IPropertyKeyStore **)this + 11),
                                     (struct IPropertyKeyStore *)v82[0],
                                     (struct _tagpropertykey **)&hMem,
                                     (unsigned int *)plRet);
    ((void (__fastcall *)(IUnknown *))v82[0]->lpVtbl->Release)(v82[0]);
LABEL_114:
    if ( KeyArrayFromPropertyKeyStore >= 0 )
    {
      *((_DWORD *)this + 28) = 1;
      KeyArrayFromPropertyKeyStore = PSCreatePropertyKeyStore(
                                       0,
                                       0,
                                       &GUID_75bd59aa_f23b_4963_aba4_0b355752a91b,
                                       (char *)this + 104);
      v56 = 0;
      if ( KeyArrayFromPropertyKeyStore >= 0 )
      {
        while ( v56 < plRet[0] )
        {
          v57 = (char *)hMem + 20 * v56;
          v58 = 1;
          v59 = 0;
          while ( v58 )
          {
            v60 = *((_QWORD *)&off_1800F2CC0 + v59);
            if ( *((_DWORD *)v57 + 4) != *(_DWORD *)(v60 + 16) )
              goto LABEL_141;
            v61 = *(_QWORD *)v57 - *(_QWORD *)v60;
            if ( *(_QWORD *)v57 == *(_QWORD *)v60 )
              v61 = *((_QWORD *)v57 + 1) - *(_QWORD *)(v60 + 8);
            v62 = v61 == 0;
            v58 = 0;
            if ( !v62 )
LABEL_141:
              v58 = 1;
            if ( (unsigned int)++v59 >= 7 )
            {
              if ( v58 )
              {
                KeyArrayFromPropertyKeyStore = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 13)
                                                                                         + 40LL))(
                                                 *((_QWORD *)this + 13),
                                                 (char *)hMem + 20 * v56);
                v63 = *((_DWORD *)this + 28)
                   && v85
                   && !(*(unsigned int (__fastcall **)(void *, char *))(*(_QWORD *)v85 + 56LL))(v85, v57);
                *((_DWORD *)this + 28) = v63;
              }
              break;
            }
          }
          ++v56;
          if ( KeyArrayFromPropertyKeyStore < 0 )
            goto LABEL_115;
        }
        KeyArrayFromPropertyKeyStore = GetKeyArrayFromPropertyKeyStore(
                                         *((struct IPropertyKeyStore **)this + 13),
                                         (struct _tagpropertykey **)this + 15,
                                         (unsigned int *)this + 32);
      }
    }
  }
LABEL_115:
  LocalFree(hMem);
  v51 = v85;
  v85 = 0;
  if ( v51 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v51 + 16LL))(v51);
LABEL_2:
  if ( KeyArrayFromPropertyKeyStore < 0 )
    return (unsigned int)KeyArrayFromPropertyKeyStore;
  v5 = 72;
  if ( (*((_BYTE *)this + 152) & 0x40) == 0 )
    v5 = 608;
  v87 = 0;
  v85 = 0;
  if ( *((_DWORD *)this + 28) )
  {
    v82[0] = *((IUnknown **)this + 13);
    v88 = (IUnknown *)*((_QWORD *)this + 24);
    v44 = *((_QWORD *)this + 23);
    v45 = operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
    hMem = v45;
    if ( v45 )
    {
      v46 = CCachedFSFolderPropertyStore::CCachedFSFolderPropertyStore((CCachedFSFolderPropertyStore *)v45);
      v47 = v46;
      if ( v46 )
      {
        *((_DWORD *)v46 + 18) = v5;
        v48 = PSCreateMemoryPropertyStore(&GUID_3017056d_9a91_4e90_937d_746c72abbf4f, (void **)v46 + 6);
        if ( v48 >= 0 )
        {
          LODWORD(pdwType) = (_DWORD)v47 + 64;
          v48 = (*(__int64 (__fastcall **)(__int64, IUnknown *, _QWORD, GUID *))(*(_QWORD *)v44 + 40LL))(
                  v44,
                  v88,
                  0,
                  &GUID_bc110b6d_57e8_4148_a9c6_91015ab2f3a5);
          if ( v48 >= 0 )
          {
            hMem = 0;
            v48 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, HLOCAL *))v47 + 8))(
                    *((_QWORD *)v47 + 8),
                    &GUID_40d4577f_e237_4bdb_bd69_58f089431b6a,
                    &hMem);
            if ( v48 >= 0 )
            {
              LODWORD(pdwType) = (_DWORD)v47 + 40;
              v48 = (*(__int64 (__fastcall **)(HLOCAL, __int64, _QWORD, GUID *))(*(_QWORD *)hMem + 40LL))(
                      hMem,
                      8,
                      0,
                      &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99);
              if ( v48 >= 0 )
              {
                IUnknown_Set((IUnknown **)v47 + 10, v82[0]);
                v48 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64))v47 + 6))(
                        *((_QWORD *)v47 + 6),
                        &GUID_388cec0d_4ef6_4015_a135_d96527fd84e2,
                        (__int64)v47 + 56);
                if ( v48 >= 0 )
                  v48 = QISearch(
                          v47,
                          &`CCachedFSFolderPropertyStore::QueryInterface'::`2'::qit,
                          &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                          (void **)&v87);
              }
              (*(void (__fastcall **)(HLOCAL))(*(_QWORD *)hMem + 16LL))(hMem);
            }
          }
        }
        CCachedFSFolderPropertyStore::Release(v47);
        if ( v48 >= 0 )
          ((void (__fastcall *)(IUnknown *, GUID *, void **))v87->lpVtbl->QueryInterface)(
            v87,
            &GUID_c24a3a5a_5ec8_458f_b90a_b3e42d41a6fd,
            &v85);
      }
    }
    v7 = v87;
    if ( v87 )
      goto LABEL_7;
  }
  pdwType = &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99;
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 25) + 80LL))(
    *((_QWORD *)this + 25),
    *((_QWORD *)this + 15),
    *((unsigned int *)this + 32),
    v5);
  v7 = v87;
  if ( v87 )
  {
LABEL_7:
    memset(v97, 0, sizeof(v97));
    v98 = 0;
    memset(v100, 0, 12);
    v95[0] = v7;
    v8 = (IUnknown *)*((_QWORD *)this + 25);
    *(_QWORD *)((char *)&v97[1] + 4) = v8;
    v9 = *((_DWORD *)this + 38);
    if ( (v9 & 0x40) != 0 )
    {
      v10 = 0;
      HIDWORD(v97[3]) = 0;
    }
    else
    {
      if ( *((_DWORD *)this + 52) )
      {
        v10 = 1;
        HIDWORD(v97[3]) = 1;
      }
      else
      {
        v10 = 0;
        HIDWORD(v97[3]) = 0;
      }
      if ( *((_DWORD *)this + 53) )
      {
        v11 = 1;
        v98 = 1;
        goto LABEL_12;
      }
    }
    v11 = 0;
    v98 = 0;
LABEL_12:
    *(_QWORD *)((char *)&v97[2] + 4) = (char *)this + 8;
    v88 = (IUnknown *)*((_QWORD *)this + 17);
    *(_QWORD *)((char *)v97 + 4) = v88;
    v96 = 1;
    v12 = (v9 >> 12) & 1;
    LODWORD(v97[0]) = v12;
    v99 = 1;
    *(_QWORD *)&v100[1] = (char *)this + 224;
    v13 = v85;
    if ( v85 )
    {
      (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v85 + 24LL))(v85, 1);
      v13 = v85;
    }
    v14 = punk;
    if ( !punk )
      goto LABEL_77;
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x200000) != 0 )
    {
      McGenEventWrite_EtwEventWriteTransfer(
        (_DWORD)v13,
        (unsigned int)ShellTraceId_Shell32_GrepDoesItemMatchCondition_Start,
        v6,
        1,
        (__int64)v122);
      v14 = punk;
    }
    v84 = 0;
    v102 = 0;
    ppunk = 0;
    v104 = 0;
    *(_OWORD *)v105 = 0;
    v106 = 0;
    v107 = 0;
    v108 = 0;
    v109 = 0;
    *(_OWORD *)hdpa = 0;
    v111 = 0;
    v101 = &CGrepConditionEvaluator::`vftable';
    v112 = 0;
    v117 = -1;
    v118 = 0;
    v119 = 0;
    v120 = 0;
    v113 = 0;
    v114 = 0;
    v115 = 0;
    v116 = 0;
    IUnknown_Set(&ppunk, v14);
    IUnknown_Set(&v102, v7);
    IUnknown_Set(v105, v88);
    IUnknown_Set(&v105[1], v8);
    LODWORD(v104) = 1;
    HIDWORD(v104) = v12;
    pv[0] = 0;
    if ( ((__int64 (__fastcall *)(IUnknown *, GUID *, LPVOID *))ppunk->lpVtbl->QueryInterface)(
           ppunk,
           &GUID_dbc3cbf5_4131_4730_a738_0684ebfeae43,
           pv) < 0 )
      goto LABEL_28;
    v15 = 0;
    v82[0] = 0;
    v16 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, GUID *, IUnknown **))(*(_QWORD *)pv[0] + 32LL))(
            pv[0],
            qword_1800F7E38,
            &GUID_a6087428_3be3_4d73_b308_7c04a540bf1a,
            v82);
    if ( v16 >= 0 )
    {
      hMem = 0;
      v16 = ((__int64 (__fastcall *)(IUnknown *, __int64 *, GUID *, HLOCAL *))v82[0]->lpVtbl[1].QueryInterface)(
              v82[0],
              &OID_PropertyStore,
              &GUID_71604b0f_97b0_4764_8577_2f13e98a1422,
              &hMem);
      if ( v16 >= 0 )
      {
        *(_OWORD *)propvarIn = 0;
        v90 = 0;
        v16 = (*(__int64 (__fastcall **)(HLOCAL, const wchar_t *, PROPVARIANT *))(*(_QWORD *)hMem + 24LL))(
                hMem,
                L"StartMenuCondition",
                propvarIn);
        if ( v16 >= 0 )
        {
          plRet[0] = 0;
          v16 = PropVariantToInt32(propvarIn, plRet);
          if ( v16 >= 0 )
            v15 = plRet[0];
          PropVariantClear(propvarIn);
        }
        (*(void (__fastcall **)(HLOCAL))(*(_QWORD *)hMem + 16LL))(hMem);
      }
      ((void (__fastcall *)(IUnknown *))v82[0]->lpVtbl->Release)(v82[0]);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv[0] + 16LL))(pv[0]);
    if ( v16 >= 0 && v15 == 1 )
      v17 = 1;
    else
LABEL_28:
      v17 = 0;
    if ( !g_dwNormalization || GetTickCount() - g_dwTicksNormalization > 0x4E20 )
    {
      plRet[0] = 0;
      LODWORD(pv[0]) = 4;
      if ( RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows Search",
             L"SystemIndexNormalization",
             0x18u,
             0,
             plRet,
             (LPDWORD)pv) )
      {
        plRet[0] = 1;
        SystemPreferredLocale = GetSystemPreferredLocale();
        for ( i = 0; i < 0x44; ++i )
        {
          if ( SystemPreferredLocale == *((_WORD *)&g_rgLanguageDiacriticSensitive + i) )
          {
            v55 = plRet[0] | 2;
            plRet[0] |= 2u;
            goto LABEL_135;
          }
        }
      }
      v55 = plRet[0];
LABEL_135:
      g_dwNormalization = v55;
      g_dwTicksNormalization = GetTickCount();
    }
    v18 = ~(_BYTE)g_dwNormalization & 2 | 0x30001;
    if ( !v17 )
      v18 = ~(_BYTE)g_dwNormalization & 2 | 0x8030001;
    v109 = v18;
    hdpa[0] = g_pfn_DPA_Create(8);
    if ( hdpa[0] && (hdpa[1] = g_pfn_DPA_Create(4)) != 0 )
    {
      IUnknown_Set(&v118, (IUnknown *)this + 1);
      v119 = __PAIR64__(v11, v10);
      v121 = (char *)this + 224;
      plRet[0] = 2;
      if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x200000) != 0 )
        McGenEventWrite_EtwEventWriteTransfer(
          v23,
          (unsigned int)ShellTraceId_Shell32_CConditionEvaluator_DoesItemMatchCondition_Start,
          v24,
          1,
          (__int64)v122);
      v25 = &v107;
      if ( !v106 )
        v25 = 0;
      DoesItemMatchConditionWorker = CConditionEvaluator::_DoesItemMatchConditionWorker(
                                       (CConditionEvaluator *)&v101,
                                       (struct ICondition *)ppunk,
                                       0,
                                       (enum TRIBIT *)plRet,
                                       v25);
      if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x200000) != 0 )
        McGenEventWrite_EtwEventWriteTransfer(
          v19,
          (unsigned int)ShellTraceId_Shell32_CConditionEvaluator_DoesItemMatchCondition_Stop,
          v20,
          1,
          (__int64)v122);
      if ( DoesItemMatchConditionWorker >= 0 )
      {
        HIDWORD(v108) = 1;
        if ( plRet[0] )
        {
LABEL_46:
          v22 = plRet[0] == 1;
          goto LABEL_47;
        }
        if ( !HIDWORD(v107) && (!(_DWORD)v108 || !(_DWORD)v119)
          || (DoesItemMatchConditionWorker = CGrepConditionEvaluator::DoesContentMatchCondition(
                                               (CGrepConditionEvaluator *)&v101,
                                               (enum TRIBIT *)plRet),
              DoesItemMatchConditionWorker >= 0) )
        {
          if ( !plRet[0] )
          {
            DoesItemMatchConditionWorker = CConditionEvaluator::FinalizeDeferredConditions((CConditionEvaluator *)&v101);
            if ( DoesItemMatchConditionWorker >= 0 )
              CConditionEvaluator::DoesItemMatchCondition((CConditionEvaluator *)&v101, (enum TRIBIT *)plRet);
          }
          goto LABEL_46;
        }
      }
    }
    else
    {
      DoesItemMatchConditionWorker = -2147024882;
    }
    v22 = v84;
LABEL_47:
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x200000) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(
        v19,
        (unsigned int)ShellTraceId_Shell32_GrepDoesItemMatchCondition_Stop,
        v20,
        1,
        (__int64)v122);
    v101 = &CGrepConditionEvaluator::`vftable';
    v26 = v118;
    v118 = 0;
    if ( v26 )
      ((void (__fastcall *)(IUnknown *))v26->lpVtbl->Release)(v26);
    v27 = v112;
    v112 = 0;
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v101 = &CConditionEvaluator::`vftable';
    v28 = v102;
    v102 = 0;
    if ( v28 )
      ((void (__fastcall *)(IUnknown *))v28->lpVtbl->Release)(v28);
    v29 = ppunk;
    ppunk = 0;
    if ( v29 )
      ((void (__fastcall *)(IUnknown *))v29->lpVtbl->Release)(v29);
    v30 = v105[0];
    v105[0] = 0;
    if ( v30 )
      ((void (__fastcall *)(IUnknown *))v30->lpVtbl->Release)(v30);
    v31 = v105[1];
    v105[1] = 0;
    if ( v31 )
      ((void (__fastcall *)(IUnknown *))v31->lpVtbl->Release)(v31);
    v32 = v106;
    v106 = 0;
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    if ( hdpa[1] )
    {
      g_pfn_DPA_DestroyCallback(hdpa[1], DPA_ReleaseCB<IScopeItem>, 0);
      hdpa[1] = 0;
      DPA_Destroy(0);
      hdpa[1] = 0;
    }
    if ( hdpa[0] )
    {
      g_pfn_DPA_DestroyCallback(hdpa[0], DPA_ReleaseCB<IScopeItem>, 0);
      hdpa[0] = 0;
      DPA_Destroy(0);
    }
    if ( DoesItemMatchConditionWorker < 0 || !v22 )
    {
      KeyArrayFromPropertyKeyStore = 1;
LABEL_70:
      ((void (__fastcall *)(IUnknown *))v87->lpVtbl->Release)(v87);
      goto LABEL_71;
    }
    v13 = v85;
LABEL_77:
    if ( v13 )
      (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)v13 + 24LL))(v13, 0);
    v88 = 0;
    std::vector<std::wstring>::vector<std::wstring>(&v92);
    *(_QWORD *)plRet = 0;
    v35 = GUID_NULL;
    *(GUID *)v122 = GUID_NULL;
    v36 = punk;
    if ( !punk )
      goto LABEL_89;
    v37 = 0;
    pv[0] = 0;
    propvarIn[0] = pv;
    propvarIn[1] = 0;
    LOBYTE(v90) = 1;
    v38 = SHGetIDListFromObject(*((IUnknown **)this + 23), (LPITEMIDLIST *)&propvarIn[1]);
    if ( (_BYTE)v90 )
    {
      v39 = *(void **)propvarIn[0];
      *(_QWORD *)propvarIn[0] = propvarIn[1];
      if ( v39 )
        CoTaskMemFree(v39);
    }
    if ( v38 >= 0 )
    {
      v82[0] = 0;
      v69 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>((__int64 *)v82);
      v70 = SHCreateItemFromIDList((LPCITEMIDLIST)pv[0], &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)v69);
      v38 = v70;
      if ( v70 >= 0 )
      {
        hMem = 0;
        v71 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>((__int64 *)&hMem);
        v73 = SHSimpleItemFromAttributes(L"shell:::{f874310e-b6b7-47dc-bc84-b9e6b38f5903}", 0x10u, v72, (void **)v71);
        v38 = v73;
        if ( v73 >= 0 )
        {
          v84 = -1;
          v73 = ((__int64 (__fastcall *)(IUnknown *, HLOCAL, __int64, int *))v82[0]->lpVtbl[2].AddRef)(
                  v82[0],
                  hMem,
                  0x10000000,
                  &v84);
          v38 = v73;
          if ( v73 >= 0 )
          {
            v37 = v84 == 0;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&hMem);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v82);
            v64 = pv[0];
            pv[0] = 0;
            if ( v64 )
              CoTaskMemFree(v64);
            v38 = 0;
            goto LABEL_87;
          }
          v74 = 29;
        }
        else
        {
          v74 = 26;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v74,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\GCQAHelpers.h",
          (const char *)(unsigned int)v73,
          (int)pdwType);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&hMem);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v82);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x17,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\GCQAHelpers.h",
          (const char *)(unsigned int)v70,
          (int)pdwType);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v82);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\GCQAHelpers.h",
        (const char *)(unsigned int)v38,
        (int)pdwType);
    }
    v40 = pv[0];
    pv[0] = 0;
    if ( v40 )
      CoTaskMemFree(v40);
LABEL_87:
    if ( v38 >= 0 && v37 )
    {
      if ( *(_QWORD *)plRet
        && (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(*(_QWORD *)plRet + 8LL) )
      {
        wil::com_ptr_t<tip2::details::merged_data<GraphItemSearchTip::_tip_GraphRankTest,GraphItemSearchTip::_tip_GraphRankTest>,wil::err_returncode_policy>::reset(plRet);
      }
      v52 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<GraphItemSearchTip::_tip_GraphRankTest,GraphItemSearchTip::_tip_GraphRankTest>>::ensure_data(plRet);
      tip2::details::shared_data<1,0,0>::start(*v52 + 8LL, v122);
      v35 = *(GUID *)v122;
      v53 = (IUnknown *)*((_QWORD *)this + 8);
      punk = v53;
      if ( v53 )
        ((void (__fastcall *)(IUnknown *))v53->lpVtbl->AddRef)(v53);
      v82[0] = v36;
      ((void (__fastcall *)(IUnknown *))v36->lpVtbl->AddRef)(v36);
      *(GUID *)pv = v35;
      anonymous_namespace_::GenerateUpgradedConditionTree(&hMem, v82, &punk, pv);
      v54 = hMem;
      if ( hMem )
      {
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<GraphItemSearchTip::_tip_GraphRankTest,GraphItemSearchTip::_tip_GraphRankTest>>::operator->(
                                plRet,
                                pv)
                 + 272LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<GraphItemSearchTip::_tip_GraphRankTest,GraphItemSearchTip::_tip_GraphRankTest>>::~test_data_control<tip2::details::merged_data<GraphItemSearchTip::_tip_GraphRankTest,GraphItemSearchTip::_tip_GraphRankTest>>(pv);
        v95[1] = hMem;
        LODWORD(pv[0]) = 0;
        if ( (int)GrepDoesItemMatchCondition((const struct CONDITIONEVALINFO *)v95, (int *)pv, v75) >= 0 )
        {
          wil::com_ptr_t<ICommand,wil::err_returncode_policy>::com_ptr_t<ICommand,wil::err_returncode_policy>(
            pv,
            (__int64)hMem);
          MatchedLeafConditions = (__int64 *)anonymous_namespace_::GetMatchedLeafConditions(propvarIn, pv);
          if ( &v92 == (void **)MatchedLeafConditions )
          {
            v78 = v93;
            v77 = (__int64)v92;
          }
          else
          {
            std::vector<wil::com_ptr_t<ICondition,wil::err_exception_policy>>::_Tidy(&v92);
            v77 = *MatchedLeafConditions;
            v92 = (void *)*MatchedLeafConditions;
            v78 = MatchedLeafConditions[1];
            v93 = v78;
            v94 = MatchedLeafConditions[2];
            *MatchedLeafConditions = 0;
            MatchedLeafConditions[1] = 0;
            MatchedLeafConditions[2] = 0;
          }
          std::vector<wil::com_ptr_t<ICondition,wil::err_exception_policy>>::_Tidy(propvarIn);
          if ( v77 != v78 )
          {
            *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<GraphItemSearchTip::_tip_GraphRankTest,GraphItemSearchTip::_tip_GraphRankTest>>::operator->(
                                    plRet,
                                    &punk)
                     + 273LL) = 1;
            tip2::test_data_control<tip2::details::merged_data<GraphItemSearchTip::_tip_GraphRankTest,GraphItemSearchTip::_tip_GraphRankTest>>::~test_data_control<tip2::details::merged_data<GraphItemSearchTip::_tip_GraphRankTest,GraphItemSearchTip::_tip_GraphRankTest>>(&punk);
          }
        }
        v54 = hMem;
      }
      if ( v54 )
        (*(void (__fastcall **)(HLOCAL))(*(_QWORD *)v54 + 16LL))(v54);
    }
LABEL_89:
    v41 = v91;
    *(GUID *)v122 = v35;
    KeyArrayFromPropertyKeyStore = CGrepQuery::_CreatePropertyStoreForResult(this, (__int64)v122);
    if ( KeyArrayFromPropertyKeyStore >= 0 )
    {
      IUnknown_Set(v41, v88);
      ((void (__fastcall *)(IUnknown *))v88->lpVtbl->Release)(v88);
    }
    v42 = *(struct _RTL_CRITICAL_SECTION **)plRet;
    if ( *(_QWORD *)plRet )
    {
      v65 = *(_QWORD *)plRet + 8LL;
      v66 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)plRet + 200LL);
      EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)plRet + 200LL));
      *(_DWORD *)(v65 + 64) |= 0x300u;
      if ( *(_QWORD *)(v65 + 240) )
        tip2::details::shared_data<1,0,0>::complete_helper(v65, 2);
      if ( v66 )
        LeaveCriticalSection(v66);
      v42 = *(struct _RTL_CRITICAL_SECTION **)plRet;
    }
    if ( v42 )
      tip2::details::merged_data<GraphItemSearchTip::_tip_GraphRankTest,GraphItemSearchTip::_tip_GraphRankTest>::Release(v42);
    v43 = v92;
    if ( v92 )
    {
      std::_Destroy_range<std::allocator<wil::com_ptr_t<ICondition,wil::err_exception_policy>>>((__int64)v92, v93);
      std::_Deallocate<16>(v43, (struct std::nothrow_t *)((v94 - (_QWORD)v43) & 0xFFFFFFFFFFFFFFF8uLL));
    }
    goto LABEL_70;
  }
LABEL_71:
  v33 = v85;
  v85 = 0;
  if ( v33 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v33 + 16LL))(v33);
  return (unsigned int)KeyArrayFromPropertyKeyStore;
}

```

## disassembly

```asm
0x180024c40  push    rbx
0x180024c42  push    rsi
0x180024c43  push    rdi
0x180024c44  push    r12
0x180024c46  push    r13
0x180024c48  push    r14
0x180024c4a  push    r15
0x180024c4c  sub     rsp, 240h
0x180024c53  movaps  [rsp+278h+var_48], xmm6
0x180024c5b  mov     rax, cs:__security_cookie
0x180024c62  xor     rax, rsp
0x180024c65  mov     [rsp+278h+var_58], rax
0x180024c6d  mov     rax, r8
0x180024c70  mov     [rsp+278h+var_1C8], rax
0x180024c78  mov     [rsp+278h+punk], rdx
0x180024c80  mov     rdi, rcx
0x180024c83  mov     [rsp+278h+var_158], rcx
0x180024c8b  mov     [rsp+278h+var_150], rax
0x180024c93  xor     ebx, ebx
0x180024c95  mov     [r8], rbx
0x180024c98  mov     esi, ebx
0x180024c9a  cmp     [rcx+68h], rbx
0x180024c9e  jz      loc_180025748
0x180024ca4  test    esi, esi
0x180024ca6  js      loc_18002536B
0x180024cac  test    byte ptr [rdi+98h], 40h
0x180024cb3  mov     eax, 260h
0x180024cb8  mov     r14d, 48h ; 'H'
0x180024cbe  cmovz   r14d, eax
0x180024cc2  mov     [rsp+278h+var_1F0], rbx
0x180024cca  mov     [rsp+278h+var_200], rbx
0x180024ccf  cmp     [rdi+70h], ebx
0x180024cd2  jnz     loc_18002559F
0x180024cd8  lea     r15, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180024cdf  mov     rcx, [rdi+0C8h]
0x180024ce6  mov     rax, [rcx]
0x180024ce9  lea     rdx, [rsp+278h+var_1F0]
0x180024cf1  mov     [rsp+278h+pvData], rdx
0x180024cf6  mov     [rsp+278h+pdwType], r15
0x180024cfb  mov     r9d, r14d
0x180024cfe  mov     r8d, [rdi+80h]
0x180024d05  mov     rdx, [rdi+78h]
0x180024d09  mov     rax, [rax+50h]
0x180024d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d12  mov     r13, [rsp+278h+var_1F0]
0x180024d1a  test    r13, r13
0x180024d1d  jz      loc_180025350
0x180024d23  mov     [rsp+278h+var_194], rbx
0x180024d2b  mov     [rsp+278h+var_18C], rbx
0x180024d33  mov     [rsp+278h+var_184], rbx
0x180024d3b  mov     [rsp+278h+var_17C], rbx
0x180024d43  mov     [rsp+278h+var_174], ebx
0x180024d4a  mov     [rsp+278h+var_16C], rbx
0x180024d52  mov     [rsp+278h+var_164], ebx
0x180024d59  mov     [rsp+278h+var_1A8], r13
0x180024d61  mov     r14, [rdi+0C8h]
0x180024d68  mov     [rsp+278h+var_18C+4], r14
0x180024d70  mov     esi, [rdi+98h]
0x180024d76  test    sil, 40h
0x180024d7a  jnz     loc_1800250EE
0x180024d80  cmp     [rdi+0D0h], ebx
0x180024d86  jnz     loc_180025945
0x180024d8c  mov     r12d, ebx
0x180024d8f  mov     dword ptr [rsp+278h+var_17C+4], ebx
0x180024d96  cmp     [rdi+0D4h], ebx
0x180024d9c  jz      loc_1800250F8
0x180024da2  mov     r15d, 1
0x180024da8  mov     [rsp+278h+var_174], r15d
0x180024db0  lea     rax, [rdi+8]
0x180024db4  mov     [rsp+278h+var_184+4], rax
0x180024dbc  mov     rax, [rdi+88h]
0x180024dc3  mov     [rsp+278h+var_1E8], rax
0x180024dcb  mov     [rsp+278h+var_194+4], rax
0x180024dd3  mov     [rsp+278h+var_198], 1
0x180024dde  shr     esi, 0Ch
0x180024de1  and     esi, 1
0x180024de4  mov     dword ptr [rsp+278h+var_194], esi
0x180024deb  mov     [rsp+278h+var_170], 1
0x180024df6  lea     rax, [rdi+0E0h]
0x180024dfd  mov     [rsp+278h+var_16C+4], rax
0x180024e05  mov     rcx, [rsp+278h+var_200]
0x180024e0a  test    rcx, rcx
0x180024e0d  jnz     loc_1800253B9
0x180024e13  mov     rax, [rsp+278h+punk]
0x180024e1b  test    rax, rax
0x180024e1e  jz      loc_1800253D9
0x180024e24  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+2, 20h
0x180024e2b  jnz     loc_180025BBE
0x180024e31  mov     [rsp+278h+var_208], ebx
0x180024e35  mov     [rsp+278h+var_140], rbx
0x180024e3d  mov     [rsp+278h+ppunk], rbx
0x180024e45  mov     [rsp+278h+var_130], rbx
0x180024e4d  xorps   xmm0, xmm0
0x180024e50  movdqa  xmmword ptr [rsp+278h+var_128], xmm0
0x180024e59  mov     [rsp+278h+var_118], rbx
0x180024e61  mov     [rsp+278h+var_110], rbx
0x180024e69  mov     [rsp+278h+var_108], rbx
0x180024e71  mov     [rsp+278h+var_100], ebx
0x180024e78  movdqa  xmmword ptr [rsp+278h+hdpa], xmm0
0x180024e81  mov     [rsp+278h+var_E8], ebx
0x180024e88  lea     rcx, ??_7CGrepConditionEvaluator@@6B@; const CGrepConditionEvaluator::`vftable'
0x180024e8f  mov     [rsp+278h+var_148], rcx
0x180024e97  mov     [rsp+278h+var_E0], rbx
0x180024e9f  mov     [rsp+278h+var_98], 0FFFFFFFFh
0x180024eaa  mov     [rsp+278h+var_90], rbx
0x180024eb2  mov     [rsp+278h+var_88], rbx
0x180024eba  mov     [rsp+278h+var_80], rbx
0x180024ec2  movups  [rsp+278h+var_D8], xmm0
0x180024eca  movups  [rsp+278h+var_C8], xmm0
0x180024ed2  movups  [rsp+278h+var_B8], xmm0
0x180024eda  movups  [rsp+278h+var_A8], xmm0
0x180024ee2  mov     rdx, rax; punk
0x180024ee5  lea     rcx, [rsp+278h+ppunk]; ppunk
0x180024eed  call    cs:__imp_IUnknown_Set
0x180024ef3  mov     rdx, r13; punk
0x180024ef6  lea     rcx, [rsp+278h+var_140]; ppunk
0x180024efe  call    cs:__imp_IUnknown_Set
0x180024f04  mov     rdx, [rsp+278h+var_1E8]; punk
0x180024f0c  lea     rcx, [rsp+278h+var_128]; ppunk
0x180024f14  call    cs:__imp_IUnknown_Set
0x180024f1a  mov     rdx, r14; punk
0x180024f1d  lea     rcx, [rsp+278h+var_128+8]; ppunk
0x180024f25  call    cs:__imp_IUnknown_Set
0x180024f2b  mov     dword ptr [rsp+278h+var_130], 1
0x180024f36  mov     dword ptr [rsp+278h+var_130+4], esi
0x180024f3d  mov     rcx, [rsp+278h+ppunk]
0x180024f45  mov     [rsp+278h+pv], rbx
0x180024f4a  mov     rax, [rcx]
0x180024f4d  lea     r8, [rsp+278h+pv]
0x180024f52  lea     rdx, _GUID_dbc3cbf5_4131_4730_a738_0684ebfeae43
0x180024f59  mov     rax, [rax]
0x180024f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f61  test    eax, eax
0x180024f63  js      loc_180025079
0x180024f69  mov     r14d, ebx
0x180024f6c  mov     [rsp+278h+var_228], rbx
0x180024f71  mov     rcx, [rsp+278h+pv]
0x180024f76  mov     rax, [rcx]
0x180024f79  lea     r9, [rsp+278h+var_228]
0x180024f7e  lea     r8, _GUID_a6087428_3be3_4d73_b308_7c04a540bf1a
0x180024f85  lea     rdx, qword_1800F7E38
0x180024f8c  mov     rax, [rax+20h]
0x180024f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f95  mov     esi, eax
0x180024f97  test    eax, eax
0x180024f99  js      loc_18002505A
0x180024f9f  mov     [rsp+278h+hMem], rbx
0x180024fa4  mov     rcx, [rsp+278h+var_228]
0x180024fa9  mov     rax, [rcx]
0x180024fac  lea     r9, [rsp+278h+hMem]
0x180024fb1  lea     r8, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422
0x180024fb8  lea     rdx, OID_PropertyStore
0x180024fbf  mov     rax, [rax+18h]
0x180024fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fc8  mov     esi, eax
0x180024fca  test    eax, eax
0x180024fcc  js      short loc_180025049
0x180024fce  xorps   xmm0, xmm0
0x180024fd1  xor     eax, eax
0x180024fd3  movups  xmmword ptr [rsp+278h+propvarIn], xmm0
0x180024fdb  mov     [rsp+278h+var_1D0], rax
0x180024fe3  mov     rcx, [rsp+278h+hMem]
0x180024fe8  mov     rax, [rcx]
0x180024feb  lea     r8, [rsp+278h+propvarIn]
0x180024ff3  lea     rdx, aStartmenucondi; "StartMenuCondition"
0x180024ffa  mov     rax, [rax+18h]
0x180024ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025003  mov     esi, eax
0x180025005  test    eax, eax
0x180025007  js      short loc_180025038
0x180025009  mov     [rsp+278h+plRet], ebx
0x18002500d  lea     rdx, [rsp+278h+plRet]; plRet
0x180025012  lea     rcx, [rsp+278h+propvarIn]; propvarIn
0x18002501a  call    cs:__imp_PropVariantToInt32
0x180025020  mov     esi, eax
0x180025022  test    eax, eax
0x180025024  cmovns  r14d, [rsp+278h+plRet]
0x18002502a  lea     rcx, [rsp+278h+propvarIn]; pvar
0x180025032  call    cs:__imp_PropVariantClear
0x180025038  mov     rcx, [rsp+278h+hMem]
0x18002503d  mov     rax, [rcx]
0x180025040  mov     rax, [rax+10h]
0x180025044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025049  mov     rcx, [rsp+278h+var_228]
0x18002504e  mov     rax, [rcx]
0x180025051  mov     rax, [rax+10h]
0x180025055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002505a  mov     rcx, [rsp+278h+pv]
0x18002505f  mov     rax, [rcx]
0x180025062  mov     rax, [rax+10h]
0x180025066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002506b  test    esi, esi
0x18002506d  js      short loc_180025079
0x18002506f  cmp     r14d, 1
0x180025073  jz      loc_180025595
0x180025079  mov     esi, ebx
0x18002507b  cmp     cs:?g_dwNormalization@@3KA, 0; ulong g_dwNormalization
0x180025082  jz      loc_18002598D
0x180025088  call    cs:__imp_GetTickCount
0x18002508e  sub     eax, cs:?g_dwTicksNormalization@@3KA; ulong g_dwTicksNormalization
0x180025094  cmp     eax, 4E20h
0x180025099  ja      loc_18002598D
0x18002509f  movzx   ecx, byte ptr cs:?g_dwNormalization@@3KA; ulong g_dwNormalization
0x1800250a6  not     cl
0x1800250a8  and     ecx, 2
0x1800250ab  or      ecx, 8030001h
0x1800250b1  mov     eax, ecx
0x1800250b3  btr     eax, 1Bh
0x1800250b7  test    esi, esi
0x1800250b9  cmovz   eax, ecx
0x1800250bc  mov     [rsp+278h+var_100], eax
0x1800250c3  mov     ecx, 8; cItemGrow
0x1800250c8  call    cs:g_pfn_DPA_Create
0x1800250ce  mov     [rsp+278h+hdpa], rax
0x1800250d6  test    rax, rax
0x1800250d9  jnz     loc_180025398
0x1800250df  mov     esi, 8007000Eh
0x1800250e4  mov     r14d, [rsp+278h+var_208]
0x1800250e9  jmp     loc_1800251BD
0x1800250ee  mov     r12d, ebx
0x1800250f1  mov     dword ptr [rsp+278h+var_17C+4], ebx
0x1800250f8  mov     r15d, ebx
0x1800250fb  mov     [rsp+278h+var_174], ebx
0x180025102  jmp     loc_180024DB0
0x180025107  lea     rdx, [rdi+8]; punk
0x18002510b  lea     rcx, [rsp+278h+var_90]; ppunk
0x180025113  call    cs:__imp_IUnknown_Set
0x180025119  mov     dword ptr [rsp+278h+var_88], r12d
0x180025121  mov     dword ptr [rsp+278h+var_88+4], r15d
0x180025129  lea     rax, [rdi+0E0h]
0x180025130  mov     [rsp+278h+var_78], rax
0x180025138  mov     [rsp+278h+plRet], 2
0x180025140  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+2, 20h
0x180025147  jnz     loc_180025C2D
0x18002514d  lea     rax, [rsp+278h+var_110]
0x180025155  cmp     [rsp+278h+var_118], 0
0x18002515e  cmovz   rax, rbx
0x180025162  mov     [rsp+278h+pdwType], rax; int
0x180025167  lea     r9, [rsp+278h+plRet]; enum TRIBIT *
0x18002516c  xor     r8d, r8d; int
0x18002516f  mov     rdx, [rsp+278h+ppunk]; struct ICondition *
0x180025177  lea     rcx, [rsp+278h+var_148]; this
0x18002517f  call    ?_DoesItemMatchConditionWorker@CConditionEvaluator@@AEAAJPEAUICondition@@HPEAW4TRIBIT@@PEAH@Z; CConditionEvaluator::_DoesItemMatchConditionWorker(ICondition *,int,TRIBIT *,int *)
0x180025184  mov     esi, eax
0x180025186  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+2, 20h
0x18002518d  jnz     loc_180025C51
0x180025193  test    esi, esi
0x180025195  js      loc_1800250E4
0x18002519b  mov     dword ptr [rsp+278h+var_108+4], 1
0x1800251a6  cmp     [rsp+278h+plRet], 0
0x1800251ab  jz      loc_1800258C6
0x1800251b1  mov     r14d, ebx
0x1800251b4  cmp     [rsp+278h+plRet], 1
0x1800251b9  setz    r14b
0x1800251bd  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+2, 20h
0x1800251c4  jnz     loc_180025958
0x1800251ca  lea     rax, ??_7CGrepConditionEvaluator@@6B@; const CGrepConditionEvaluator::`vftable'
0x1800251d1  mov     [rsp+278h+var_148], rax
0x1800251d9  mov     rcx, [rsp+278h+var_90]
0x1800251e1  mov     [rsp+278h+var_90], rbx
0x1800251e9  test    rcx, rcx
0x1800251ec  jz      short loc_1800251FA
0x1800251ee  mov     rax, [rcx]
0x1800251f1  mov     rax, [rax+10h]
0x1800251f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251fa  mov     rcx, [rsp+278h+var_E0]
0x180025202  mov     [rsp+278h+var_E0], rbx
0x18002520a  test    rcx, rcx
0x18002520d  jnz     loc_18002597C
0x180025213  lea     rax, ??_7CConditionEvaluator@@6B@; const CConditionEvaluator::`vftable'
0x18002521a  mov     [rsp+278h+var_148], rax
0x180025222  mov     rcx, [rsp+278h+var_140]
0x18002522a  mov     [rsp+278h+var_140], rbx
0x180025232  test    rcx, rcx
0x180025235  jz      short loc_180025243
0x180025237  mov     rax, [rcx]
0x18002523a  mov     rax, [rax+10h]
0x18002523e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025243  mov     rcx, [rsp+278h+ppunk]
0x18002524b  mov     [rsp+278h+ppunk], rbx
0x180025253  test    rcx, rcx
0x180025256  jz      short loc_180025264
0x180025258  mov     rax, [rcx]
0x18002525b  mov     rax, [rax+10h]
0x18002525f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025264  mov     rcx, [rsp+278h+var_128]
0x18002526c  mov     [rsp+278h+var_128], rbx
0x180025274  test    rcx, rcx
0x180025277  jz      short loc_180025285
0x180025279  mov     rax, [rcx]
0x18002527c  mov     rax, [rax+10h]
0x180025280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025285  mov     rcx, [rsp+278h+var_128+8]
0x18002528d  mov     [rsp+278h+var_128+8], rbx
0x180025295  test    rcx, rcx
0x180025298  jz      short loc_1800252A6
0x18002529a  mov     rax, [rcx]
0x18002529d  mov     rax, [rax+10h]
0x1800252a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252a6  mov     rcx, [rsp+278h+var_118]
  ... truncated ...
```
