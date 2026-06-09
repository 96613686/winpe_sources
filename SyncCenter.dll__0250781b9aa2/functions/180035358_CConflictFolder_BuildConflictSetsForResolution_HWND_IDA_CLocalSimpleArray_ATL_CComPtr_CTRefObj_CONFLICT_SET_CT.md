# CConflictFolder::_BuildConflictSetsForResolution(HWND__ *,_IDA *,CLocalSimpleArray<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>,4294967294> *,uint *)

- ea: `0x180035358`
- end: `0x1800358c7`
- name: `?_BuildConflictSetsForResolution@CConflictFolder@@AEAAJPEAUHWND__@@PEAU_IDA@@PEAV?$CLocalSimpleArray@V?$CComPtr@V?$CTRefObj@UCONFLICT_SET@@VCTRefBase_NoModuleLifetimePolicy@@@@@ATL@@$0PPPPPPPO@@@PEAI@Z`
- size: `1391`
- prototype: `__int64 __fastcall(CConflictFolder *this, __int64, unsigned int *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180037a20`

## callees

- `0x180005660`
- `0x18000a5e4`
- `0x18000a8ac`
- `0x18000b310`
- `0x18000d62c`
- `0x1800133b0`
- `0x1800134dc`
- `0x180013678`
- `0x180031508`
- `0x180031528`
- `0x180031594`
- `0x180031880`
- `0x18003200c`
- `0x180032b20`
- `0x180034620`
- `0x18003468c`
- `0x180035358`
- `0x180035b94`
- `0x18003625c`
- `0x180037e98`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800353f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035400`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003554e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003571b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035826`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003582f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035874`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003587d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800353f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035400`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003554e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003571b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035826`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003582f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035874`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003587d`

## pseudocode

```c
__int64 __fastcall CConflictFolder::_BuildConflictSetsForResolution(
        CConflictFolder *this,
        __int64 a2,
        unsigned int *a3,
        _QWORD *a4,
        _DWORD *a5)
{
  CConflictFolder *v5; // r15
  unsigned __int64 v6; // r12
  int v7; // edi
  unsigned int *v9; // rbx
  struct IProgressDialog **v10; // rax
  HWND v11; // rdx
  CConflictFolder *v12; // rcx
  unsigned int i; // esi
  int ConflictInfoFromIDListArray; // eax
  WCHAR *v15; // rbx
  char v16; // si
  __int64 v17; // r15
  unsigned __int64 v18; // rax
  unsigned __int64 j; // rdx
  LPVOID v20; // rax
  __int64 v21; // rsi
  PCNZWCH v22; // rdi
  void *v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rdx
  _QWORD *v26; // rcx
  _DWORD *v27; // rax
  __int64 v28; // r10
  LPVOID v29; // rax
  __int64 v30; // rax
  __int64 v31; // rdi
  void *v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rdx
  _QWORD *v36; // rsi
  _QWORD *v37; // rcx
  __int64 v38; // rdx
  _QWORD *v39; // rcx
  unsigned int v41; // [rsp+68h] [rbp-61h]
  __int64 v42; // [rsp+6Ch] [rbp-5Dh] BYREF
  const WCHAR *v43; // [rsp+78h] [rbp-51h] BYREF
  PCNZWCH lpString1; // [rsp+80h] [rbp-49h] BYREF
  __int64 v45; // [rsp+88h] [rbp-41h] BYREF
  __int64 v46; // [rsp+90h] [rbp-39h] BYREF
  __int64 v47; // [rsp+98h] [rbp-31h] BYREF
  __int64 v48; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v49; // [rsp+A8h] [rbp-21h] BYREF
  __int64 v50; // [rsp+B0h] [rbp-19h] BYREF
  unsigned __int64 v51; // [rsp+B8h] [rbp-11h]
  __int64 v52; // [rsp+C0h] [rbp-9h]
  __int64 v53; // [rsp+C8h] [rbp-1h]
  __int64 v54; // [rsp+D0h] [rbp+7h] BYREF
  LPVOID pv[8]; // [rsp+D8h] [rbp+Fh] BYREF

  v5 = this;
  v6 = 0;
  v7 = 0;
  v9 = a3;
  ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(&v49);
  v10 = (struct IProgressDialog **)ATL::CComPtrBase<ISyncClientFolderItemCache>::operator&(&v49);
  CConflictFolder::_StartProgressDialog(v12, v11, v10);
  for ( i = 0; ; ++i )
  {
    v41 = i;
    if ( i >= *v9 || v7 < 0 )
      break;
    v43 = 0;
    lpString1 = 0;
    pv[0] = 0;
    ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(&v47);
    ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(&v54);
    v42 = 0;
    v50 = 0;
    v51 = 0;
    v52 = 0;
    v53 = 0;
    CoTaskMemFree(0);
    CoTaskMemFree(0);
    ConflictInfoFromIDListArray = CConflictFolder::_GetConflictInfoFromIDListArray(
                                    v5,
                                    (__int64)&lpString1,
                                    (__int64)pv,
                                    (__int64)&v47,
                                    (__int64)&v54,
                                    (__int64)&v42,
                                    (__int64)&v42 + 4,
                                    (__int64)&v50);
    v15 = (WCHAR *)lpString1;
    v7 = ConflictInfoFromIDListArray;
    if ( !ConflictInfoFromIDListArray )
    {
      v16 = 0;
      lpString1 = v43;
      while ( v6 < a4[1] )
      {
        v17 = *(_QWORD *)(*a4 + 8 * v6);
        if ( CSyncMgrID::s_AreIDStringsEqual(v15, (PCNZWCH)(v17 + 16))
          && __PAIR64__(v42, HIDWORD(v42)) == *(_QWORD *)(v17 + 272) )
        {
          v18 = v51;
          if ( v51 == *(_QWORD *)(v17 + 288) )
          {
            if ( v51 )
            {
              for ( j = 0; j < v18; ++j )
              {
                if ( *(_DWORD *)(v50 + 4 * j) != *(_DWORD *)(*(_QWORD *)(v17 + 280) + 4 * j) )
                {
                  v16 = 0;
                  goto LABEL_26;
                }
                v18 = v51;
              }
              v20 = operator new(0x20u);
              if ( v20 )
                v20 = (LPVOID)CTRefObj<CONFLICT_SET_ENTRY,CTRefBase_NoModuleLifetimePolicy>::CTRefObj<CONFLICT_SET_ENTRY,CTRefBase_NoModuleLifetimePolicy>(v20);
              ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>(
                &v45,
                (__int64)v20);
              if ( ATL::CComPtrBase<CTRefObj<CONFLICT_SET_ENTRY,CTRefBase_NoModuleLifetimePolicy>>::operator==(&v45) )
              {
                v7 = -2147024882;
              }
              else
              {
                v21 = v45;
                v22 = lpString1;
                lpString1 = 0;
                v43 = 0;
                v23 = *(void **)(v45 + 16);
                *(_QWORD *)(v45 + 16) = 0;
                CoTaskMemFree(v23);
                *(_QWORD *)(v21 + 16) = v22;
                v24 = ATL::CComPtrBase<ISyncMgrConflict>::Detach(&v47);
                ATL::CComPtrBase<CRenameCanonicalMenuWrapper>::Attach(v21 + 24, v24);
                v7 = 0;
                v25 = *(_QWORD *)(v17 + 320);
                if ( v25 != *(_QWORD *)(v17 + 336)
                  || (v7 = CTSimpleArray<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>,4294967294,CTPolicyLocalMem<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>>,CSimpleArrayStandardCompareHelper<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>>,CSimpleArrayStandardMergeHelper<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>>>::_EnsureCapacity(
                             v17 + 312,
                             v25 + 1),
                      v7 >= 0) )
                {
                  v26 = (_QWORD *)(*(_QWORD *)(v17 + 312) + 8 * (*(_QWORD *)(v17 + 320))++);
                  if ( v26 )
                    ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>(
                      v26,
                      &v45);
                }
                if ( v7 >= 0 )
                {
                  ++*a5;
                  ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)&v45);
                  v6 = 0;
                  goto LABEL_51;
                }
              }
              v16 = 1;
              ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)&v45);
            }
          }
        }
LABEL_26:
        ++v6;
      }
      v6 = 0;
      if ( !v16 )
      {
        v27 = operator new(0x158u);
        if ( v27 )
        {
          v27[2] = 0;
          *(_QWORD *)v27 = &CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>::`vftable';
          *((_QWORD *)v27 + 35) = 0;
          *((_QWORD *)v27 + 36) = 0;
          *((_QWORD *)v27 + 37) = 0;
          *((_QWORD *)v27 + 38) = 0;
          *((_QWORD *)v27 + 39) = 0;
          *((_QWORD *)v27 + 40) = 0;
          *((_QWORD *)v27 + 41) = 0;
          *((_QWORD *)v27 + 42) = 0;
        }
        else
        {
          v27 = 0;
        }
        ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>(
          &v46,
          (__int64)v27);
        if ( ATL::CComPtrBase<CTRefObj<CONFLICT_SET_ENTRY,CTRefBase_NoModuleLifetimePolicy>>::operator==(&v46) )
        {
          v7 = -2147024882;
        }
        else
        {
          StringCchCopyW((unsigned __int16 *)(v46 + 16), 0x40u, v15);
          *(_DWORD *)(v28 + 276) = v42;
          *(_DWORD *)(v28 + 272) = HIDWORD(v42);
          *(_QWORD *)(v28 + 280) = v50;
          *(_QWORD *)(v28 + 296) = v52;
          *(_QWORD *)(v28 + 288) = v51;
          *(_QWORD *)(v28 + 304) = v53;
          v50 = 0;
          v52 = 0;
          v51 = 0;
          v53 = 0;
          v29 = operator new(0x20u);
          if ( v29 )
            v30 = CTRefObj<CONFLICT_SET_ENTRY,CTRefBase_NoModuleLifetimePolicy>::CTRefObj<CONFLICT_SET_ENTRY,CTRefBase_NoModuleLifetimePolicy>(v29);
          else
            v30 = 0;
          ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>(
            &v48,
            v30);
          if ( ATL::CComPtrBase<CTRefObj<CONFLICT_SET_ENTRY,CTRefBase_NoModuleLifetimePolicy>>::operator==(&v48) )
          {
            v7 = -2147024882;
          }
          else
          {
            v31 = v48;
            v43 = 0;
            v32 = *(void **)(v48 + 16);
            *(_QWORD *)(v48 + 16) = 0;
            CoTaskMemFree(v32);
            *(_QWORD *)(v31 + 16) = lpString1;
            v33 = ATL::CComPtrBase<ISyncMgrConflict>::Detach(&v47);
            ATL::CComPtrBase<CRenameCanonicalMenuWrapper>::Attach(v31 + 24, v33);
            v34 = ATL::CComPtrBase<ISyncMgrConflictResolveInfo>::operator->((__int64)&v46);
            v35 = *(_QWORD *)(v34 + 320);
            v36 = (_QWORD *)(v34 + 312);
            if ( v35 != *(_QWORD *)(v34 + 336)
              || (v7 = CTSimpleArray<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>,4294967294,CTPolicyLocalMem<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>>,CSimpleArrayStandardCompareHelper<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>>,CSimpleArrayStandardMergeHelper<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>>>::_EnsureCapacity(
                         v34 + 312,
                         v35 + 1),
                  v7 >= 0) )
            {
              v37 = (_QWORD *)(*v36 + 8 * v36[1]++);
              if ( v37 )
                ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>(
                  v37,
                  &v48);
              v38 = a4[1];
              v7 = 0;
              if ( v38 != a4[3]
                || (v7 = CTSimpleArray<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>,4294967294,CTPolicyLocalMem<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>>,CSimpleArrayStandardCompareHelper<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>>,CSimpleArrayStandardMergeHelper<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>>>::_EnsureCapacity(
                           a4,
                           v38 + 1),
                    v7 >= 0) )
              {
                v39 = (_QWORD *)(*a4 + 8 * a4[1]++);
                if ( v39 )
                  ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>(
                    v39,
                    &v46);
              }
              if ( v7 >= 0 )
                ++*a5;
            }
          }
          ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)&v48);
        }
        ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)&v46);
      }
LABEL_51:
      i = v41;
      v5 = this;
    }
    if ( v49 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v49 + 56LL))(v49) )
    {
      CTSimpleArray<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>,4294967294,CTPolicyLocalMem<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>>,CSimpleArrayStandardCompareHelper<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>>,CSimpleArrayStandardMergeHelper<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>>>::RemoveAll(a4);
      *a5 = 0;
      CTSimpleArray<enum SYNCMGR_CONFLICT_ITEM_TYPE,4294967294,CTPolicyLocalMem<enum SYNCMGR_CONFLICT_ITEM_TYPE>,CSimpleArrayStandardCompareHelper<enum SYNCMGR_CONFLICT_ITEM_TYPE>,CSimpleArrayStandardMergeHelper<enum SYNCMGR_CONFLICT_ITEM_TYPE>>::RemoveAll(&v50);
      ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)&v54);
      ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)&v47);
      CoTaskMemFree(pv[0]);
      CoTaskMemFree(v15);
      CCoTaskMemPtr<_ITEMIDLIST_ABSOLUTE>::~CCoTaskMemPtr<_ITEMIDLIST_ABSOLUTE>((void **)&v43);
      break;
    }
    CTSimpleArray<enum SYNCMGR_CONFLICT_ITEM_TYPE,4294967294,CTPolicyLocalMem<enum SYNCMGR_CONFLICT_ITEM_TYPE>,CSimpleArrayStandardCompareHelper<enum SYNCMGR_CONFLICT_ITEM_TYPE>,CSimpleArrayStandardMergeHelper<enum SYNCMGR_CONFLICT_ITEM_TYPE>>::RemoveAll(&v50);
    ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)&v54);
    ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)&v47);
    CoTaskMemFree(pv[0]);
    CoTaskMemFree(v15);
    CCoTaskMemPtr<_ITEMIDLIST_ABSOLUTE>::~CCoTaskMemPtr<_ITEMIDLIST_ABSOLUTE>((void **)&v43);
    v9 = a3;
  }
  if ( v49 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 32LL))(v49);
  ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)&v49);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180035358  mov     rax, rsp
0x18003535b  mov     [rax+10h], rbx
0x18003535f  mov     [rax+18h], r8
0x180035363  mov     [rax+8], rcx
0x180035367  push    rbp
0x180035368  push    rsi
0x180035369  push    rdi
0x18003536a  push    r12
0x18003536c  push    r13
0x18003536e  push    r14
0x180035370  push    r15
0x180035372  lea     rbp, [rax-57h]
0x180035376  sub     rsp, 0E0h
0x18003537d  mov     r15, rcx
0x180035380  xor     r12d, r12d
0x180035383  lea     rcx, [rbp+4Fh+var_70]; void *
0x180035387  mov     edi, r12d
0x18003538a  mov     r14, r9
0x18003538d  mov     rbx, r8
0x180035390  call    ??0?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(void)
0x180035395  lea     rcx, [rbp+4Fh+var_70]; void *
0x180035399  call    ??I?$CComPtrBase@UISyncClientFolderItemCache@@@ATL@@QEAAPEAPEAUISyncClientFolderItemCache@@XZ; ATL::CComPtrBase<ISyncClientFolderItemCache>::operator&(void)
0x18003539e  mov     r8, rax; struct IProgressDialog **
0x1800353a1  call    ?_StartProgressDialog@CConflictFolder@@AEAAJPEAUHWND__@@PEAPEAUIProgressDialog@@@Z; CConflictFolder::_StartProgressDialog(HWND__ *,IProgressDialog * *)
0x1800353a6  mov     r13, [rbp+4Fh+arg_20]
0x1800353aa  mov     esi, r12d
0x1800353ad  mov     [rbp+4Fh+var_B0], esi
0x1800353b0  cmp     esi, [rbx]
0x1800353b2  jnb     loc_18003588C
0x1800353b8  test    edi, edi
0x1800353ba  js      loc_18003588C
0x1800353c0  lea     rcx, [rbp+4Fh+var_80]; void *
0x1800353c4  mov     [rbp+4Fh+var_A0], r12
0x1800353c8  mov     [rbp+4Fh+lpString1], r12
0x1800353cc  mov     [rbp+4Fh+pv], r12
0x1800353d0  call    ??0?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(void)
0x1800353d5  lea     rcx, [rbp+4Fh+var_48]; void *
0x1800353d9  call    ??0?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(void)
0x1800353de  xor     ecx, ecx; pv
0x1800353e0  mov     dword ptr [rbp+4Fh+var_AC], r12d
0x1800353e4  mov     dword ptr [rbp+4Fh+var_AC+4], r12d
0x1800353e8  mov     [rbp+4Fh+var_68], r12
0x1800353ec  mov     [rbp+4Fh+var_60], r12
0x1800353f0  mov     [rbp+4Fh+var_58], r12
0x1800353f4  mov     [rbp+4Fh+var_50], r12
0x1800353f8  call    cs:__imp_CoTaskMemFree
0x1800353fe  xor     ecx, ecx; pv
0x180035400  call    cs:__imp_CoTaskMemFree
0x180035406  lea     rax, [rbp+4Fh+var_68]
0x18003540a  mov     r8d, esi
0x18003540d  mov     [rsp+50h], rax; __int64
0x180035412  lea     r9, [rbp+4Fh+var_A0]
0x180035416  lea     rax, [rbp+4Fh+var_AC+4]
0x18003541a  mov     rdx, rbx
0x18003541d  mov     [rsp+110h+var_C8], rax; __int64
0x180035422  mov     rcx, r15; this
0x180035425  lea     rax, [rbp+4Fh+var_AC]
0x180035429  mov     [rsp+110h+var_D0], rax; __int64
0x18003542e  lea     rax, [rbp+4Fh+var_48]
0x180035432  mov     [rsp+110h+var_D8], rax; __int64
0x180035437  lea     rax, [rbp+4Fh+var_80]
0x18003543b  mov     [rsp+110h+var_E0], rax; __int64
0x180035440  lea     rax, [rbp+4Fh+pv]
0x180035444  mov     [rsp+110h+var_E8], rax; __int64
0x180035449  lea     rax, [rbp+4Fh+lpString1]
0x18003544d  mov     [rsp+110h+var_F0], rax; __int64
0x180035452  call    ?_GetConflictInfoFromIDListArray@CConflictFolder@@AEAAJPEAU_IDA@@IPEAPEAU_ITEMIDLIST_ABSOLUTE@@PEAPEAG2PEAPEAUISyncMgrConflict@@PEAPEAUISyncMgrConflictItems@@PEAIPEAKPEAV?$CLocalSimpleArray@W4SYNCMGR_CONFLICT_ITEM_TYPE@@$0PPPPPPPO@@@@Z; CConflictFolder::_GetConflictInfoFromIDListArray(_IDA *,uint,_ITEMIDLIST_ABSOLUTE * *,ushort * *,ushort * *,ISyncMgrConflict * *,ISyncMgrConflictItems * *,uint *,ulong *,CLocalSimpleArray<SYNCMGR_CONFLICT_ITEM_TYPE,4294967294> *)
0x180035457  mov     rbx, [rbp+4Fh+lpString1]
0x18003545b  mov     edi, eax
0x18003545d  test    eax, eax
0x18003545f  jnz     loc_1800357EE
0x180035465  mov     r15, [rbp+4Fh+var_A0]
0x180035469  mov     sil, r12b
0x18003546c  mov     [rbp+4Fh+lpString1], r15
0x180035470  cmp     r12, [r14+8]
0x180035474  jnb     loc_1800355DE
0x18003547a  mov     rax, [r14]
0x18003547d  mov     rcx, rbx; lpString1
0x180035480  mov     r15, [rax+r12*8]
0x180035484  lea     rdx, [r15+10h]; lpString2
0x180035488  call    ?s_AreIDStringsEqual@CSyncMgrID@@SA_NPEBG0@Z; CSyncMgrID::s_AreIDStringsEqual(ushort const *,ushort const *)
0x18003548d  cmp     al, 1
0x18003548f  jnz     loc_1800355C1
0x180035495  mov     eax, dword ptr [rbp+4Fh+var_AC]
0x180035498  cmp     eax, [r15+114h]
0x18003549f  jnz     loc_1800355C1
0x1800354a5  mov     eax, dword ptr [rbp+4Fh+var_AC+4]
0x1800354a8  cmp     eax, [r15+110h]
0x1800354af  jnz     loc_1800355C1
0x1800354b5  mov     rax, [rbp+4Fh+var_60]
0x1800354b9  cmp     rax, [r15+120h]
0x1800354c0  jnz     loc_1800355C1
0x1800354c6  test    rax, rax
0x1800354c9  jz      loc_1800355C1
0x1800354cf  xor     edx, edx
0x1800354d1  cmp     rdx, rax
0x1800354d4  jnb     short loc_1800354FA
0x1800354d6  mov     rax, [r15+118h]
0x1800354dd  mov     ecx, [rax+rdx*4]
0x1800354e0  mov     rax, [rbp+4Fh+var_68]
0x1800354e4  cmp     [rax+rdx*4], ecx
0x1800354e7  jnz     short loc_1800354F2
0x1800354e9  mov     rax, [rbp+4Fh+var_60]
0x1800354ed  inc     rdx
0x1800354f0  jmp     short loc_1800354D1
0x1800354f2  xor     sil, sil
0x1800354f5  jmp     loc_1800355C1
0x1800354fa  mov     ecx, 20h ; ' '; unsigned __int64
0x1800354ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035504  test    rax, rax
0x180035507  jz      short loc_180035511
0x180035509  mov     rcx, rax
0x18003550c  call    ??0?$CTRefObj@UCONFLICT_SET_ENTRY@@VCTRefBase_NoModuleLifetimePolicy@@@@QEAA@XZ; CTRefObj<CONFLICT_SET_ENTRY,CTRefBase_NoModuleLifetimePolicy>::CTRefObj<CONFLICT_SET_ENTRY,CTRefBase_NoModuleLifetimePolicy>(void)
0x180035511  mov     rdx, rax
0x180035514  lea     rcx, [rbp+4Fh+var_90]
0x180035518  call    ??0?$CComPtr@V?$CTRefObj@UCONFLICT_SET@@VCTRefBase_NoModuleLifetimePolicy@@@@@ATL@@QEAA@PEAV?$CTRefObj@UCONFLICT_SET@@VCTRefBase_NoModuleLifetimePolicy@@@@@Z; ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>(CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy> *)
0x18003551d  lea     rcx, [rbp+4Fh+var_90]
0x180035521  call    ??8?$CComPtrBase@V?$CTRefObj@UCONFLICT_SET_ENTRY@@VCTRefBase_NoModuleLifetimePolicy@@@@@ATL@@QEBA_NPEAV?$CTRefObj@UCONFLICT_SET_ENTRY@@VCTRefBase_NoModuleLifetimePolicy@@@@@Z; ATL::CComPtrBase<CTRefObj<CONFLICT_SET_ENTRY,CTRefBase_NoModuleLifetimePolicy>>::operator==(CTRefObj<CONFLICT_SET_ENTRY,CTRefBase_NoModuleLifetimePolicy> *)
0x180035526  test    al, al
0x180035528  jz      short loc_180035534
0x18003552a  mov     edi, 8007000Eh
0x18003552f  jmp     loc_1800355B5
0x180035534  mov     rsi, [rbp+4Fh+var_90]
0x180035538  xor     eax, eax
0x18003553a  mov     rdi, [rbp+4Fh+lpString1]
0x18003553e  mov     [rbp+4Fh+lpString1], rax
0x180035542  mov     [rbp+4Fh+var_A0], rax
0x180035546  mov     rcx, [rsi+10h]; pv
0x18003554a  mov     [rsi+10h], rax
0x18003554e  call    cs:__imp_CoTaskMemFree
0x180035554  lea     rcx, [rbp+4Fh+var_80]
0x180035558  mov     [rsi+10h], rdi
0x18003555c  call    ?Detach@?$CComPtrBase@UISyncMgrConflict@@@ATL@@QEAAPEAUISyncMgrConflict@@XZ; ATL::CComPtrBase<ISyncMgrConflict>::Detach(void)
0x180035561  mov     rdx, rax
0x180035564  lea     rcx, [rsi+18h]
0x180035568  call    ?Attach@?$CComPtrBase@VCRenameCanonicalMenuWrapper@@@ATL@@QEAAXPEAVCRenameCanonicalMenuWrapper@@@Z; ATL::CComPtrBase<CRenameCanonicalMenuWrapper>::Attach(CRenameCanonicalMenuWrapper *)
0x18003556d  lea     rsi, [r15+138h]
0x180035574  xor     edi, edi
0x180035576  mov     rdx, [rsi+8]
0x18003557a  cmp     rdx, [rsi+18h]
0x18003557e  jnz     short loc_180035591
0x180035580  inc     rdx
0x180035583  mov     rcx, rsi
0x180035586  call    ?_EnsureCapacity@?$CTSimpleArray@V?$CComPtr@V?$CTRefObj@UCONFLICT_SET@@VCTRefBase_NoModuleLifetimePolicy@@@@@ATL@@$0PPPPPPPO@V?$CTPolicyLocalMem@V?$CComPtr@V?$CTRefObj@UCONFLICT_SET@@VCTRefBase_NoModuleLifetimePolicy@@@@@ATL@@@@V?$CSimpleArrayStandardCompareHelper@V?$CComPtr@V?$CTRefObj@UCONFLICT_SET@@VCTRefBase_NoModuleLifetimePolicy@@@@@ATL@@@@V?$CSimpleArrayStandardMergeHelper@V?$CComPtr@V?$CTRefObj@UCONFLICT_SET@@VCTRefBase_NoModuleLifetimePolicy@@@@@ATL@@@@@@QEAAJ_K0@Z; CTSimpleArray<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>,4294967294,CTPolicyLocalMem<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>>,CSimpleArrayStandardCompareHelper<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>>,CSimpleArrayStandardMergeHelper<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18003558b  mov     edi, eax
0x18003558d  test    eax, eax
0x18003558f  js      short loc_1800355B1
0x180035591  inc     qword ptr [rsi+8]
0x180035595  mov     rcx, [rsi+8]
0x180035599  mov     rax, [rsi]
0x18003559c  dec     rcx
0x18003559f  lea     rcx, [rax+rcx*8]
0x1800355a3  test    rcx, rcx
0x1800355a6  jz      short loc_1800355B1
0x1800355a8  lea     rdx, [rbp+4Fh+var_90]
0x1800355ac  call    ??0?$CComPtr@V?$CTRefObj@UCONFLICT_SET@@VCTRefBase_NoModuleLifetimePolicy@@@@@ATL@@QEAA@AEBV01@@Z; ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>(ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>> const &)
0x1800355b1  test    edi, edi
0x1800355b3  jns     short loc_1800355C9
0x1800355b5  lea     rcx, [rbp+4Fh+var_90]
0x1800355b9  mov     sil, 1
0x1800355bc  call    ??1?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>(void)
0x1800355c1  inc     r12
0x1800355c4  jmp     loc_180035470
0x1800355c9  inc     dword ptr [r13+0]
0x1800355cd  lea     rcx, [rbp+4Fh+var_90]
0x1800355d1  call    ??1?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>(void)
0x1800355d6  xor     r12d, r12d
0x1800355d9  jmp     loc_1800357E7
0x1800355de  xor     r12d, r12d
0x1800355e1  test    sil, sil
0x1800355e4  jnz     loc_1800357E7
0x1800355ea  mov     ecx, 158h; unsigned __int64
0x1800355ef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800355f4  test    rax, rax
0x1800355f7  jz      short loc_180035641
0x1800355f9  mov     [rax+8], r12d
0x1800355fd  lea     rcx, ??_7?$CTRefObj@UCONFLICT_SET@@VCTRefBase_NoModuleLifetimePolicy@@@@6B@; const CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>::`vftable'
0x180035604  mov     [rax], rcx
0x180035607  mov     [rax+118h], r12
0x18003560e  mov     [rax+120h], r12
0x180035615  mov     [rax+128h], r12
0x18003561c  mov     [rax+130h], r12
0x180035623  mov     [rax+138h], r12
0x18003562a  mov     [rax+140h], r12
0x180035631  mov     [rax+148h], r12
0x180035638  mov     [rax+150h], r12
0x18003563f  jmp     short loc_180035644
0x180035641  mov     rax, r12
0x180035644  mov     rdx, rax
0x180035647  lea     rcx, [rbp+4Fh+var_88]
0x18003564b  call    ??0?$CComPtr@V?$CTRefObj@UCONFLICT_SET@@VCTRefBase_NoModuleLifetimePolicy@@@@@ATL@@QEAA@PEAV?$CTRefObj@UCONFLICT_SET@@VCTRefBase_NoModuleLifetimePolicy@@@@@Z; ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>(CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy> *)
0x180035650  lea     rcx, [rbp+4Fh+var_88]
0x180035654  call    ??8?$CComPtrBase@V?$CTRefObj@UCONFLICT_SET_ENTRY@@VCTRefBase_NoModuleLifetimePolicy@@@@@ATL@@QEBA_NPEAV?$CTRefObj@UCONFLICT_SET_ENTRY@@VCTRefBase_NoModuleLifetimePolicy@@@@@Z; ATL::CComPtrBase<CTRefObj<CONFLICT_SET_ENTRY,CTRefBase_NoModuleLifetimePolicy>>::operator==(CTRefObj<CONFLICT_SET_ENTRY,CTRefBase_NoModuleLifetimePolicy> *)
0x180035659  test    al, al
0x18003565b  jz      short loc_180035667
0x18003565d  mov     edi, 8007000Eh
0x180035662  jmp     loc_1800357DE
0x180035667  mov     r10, [rbp+4Fh+var_88]
0x18003566b  mov     r8, rbx; unsigned __int16 *
0x18003566e  mov     edx, 40h ; '@'; unsigned __int64
0x180035673  lea     rcx, [r10+10h]; unsigned __int16 *
0x180035677  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003567c  mov     eax, dword ptr [rbp+4Fh+var_AC]
0x18003567f  mov     ecx, 20h ; ' '; unsigned __int64
0x180035684  mov     [r10+114h], eax
0x18003568b  mov     eax, dword ptr [rbp+4Fh+var_AC+4]
0x18003568e  mov     [r10+110h], eax
0x180035695  mov     rax, [rbp+4Fh+var_68]
0x180035699  mov     [r10+118h], rax
0x1800356a0  mov     rax, [rbp+4Fh+var_58]
0x1800356a4  mov     [r10+128h], rax
0x1800356ab  mov     rax, [rbp+4Fh+var_60]
0x1800356af  mov     [r10+120h], rax
0x1800356b6  mov     rax, [rbp+4Fh+var_50]
0x1800356ba  mov     [r10+130h], rax
0x1800356c1  mov     [rbp+4Fh+var_68], r12
0x1800356c5  mov     [rbp+4Fh+var_58], r12
0x1800356c9  mov     [rbp+4Fh+var_60], r12
0x1800356cd  mov     [rbp+4Fh+var_50], r12
0x1800356d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800356d6  test    rax, rax
0x1800356d9  jz      short loc_1800356E5
0x1800356db  mov     rcx, rax
0x1800356de  call    ??0?$CTRefObj@UCONFLICT_SET_ENTRY@@VCTRefBase_NoModuleLifetimePolicy@@@@QEAA@XZ; CTRefObj<CONFLICT_SET_ENTRY,CTRefBase_NoModuleLifetimePolicy>::CTRefObj<CONFLICT_SET_ENTRY,CTRefBase_NoModuleLifetimePolicy>(void)
0x1800356e3  jmp     short loc_1800356E8
0x1800356e5  mov     rax, r12
0x1800356e8  mov     rdx, rax
0x1800356eb  lea     rcx, [rbp+4Fh+var_78]
0x1800356ef  call    ??0?$CComPtr@V?$CTRefObj@UCONFLICT_SET@@VCTRefBase_NoModuleLifetimePolicy@@@@@ATL@@QEAA@PEAV?$CTRefObj@UCONFLICT_SET@@VCTRefBase_NoModuleLifetimePolicy@@@@@Z; ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>(CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy> *)
0x1800356f4  lea     rcx, [rbp+4Fh+var_78]
0x1800356f8  call    ??8?$CComPtrBase@V?$CTRefObj@UCONFLICT_SET_ENTRY@@VCTRefBase_NoModuleLifetimePolicy@@@@@ATL@@QEBA_NPEAV?$CTRefObj@UCONFLICT_SET_ENTRY@@VCTRefBase_NoModuleLifetimePolicy@@@@@Z; ATL::CComPtrBase<CTRefObj<CONFLICT_SET_ENTRY,CTRefBase_NoModuleLifetimePolicy>>::operator==(CTRefObj<CONFLICT_SET_ENTRY,CTRefBase_NoModuleLifetimePolicy> *)
0x1800356fd  test    al, al
0x1800356ff  jz      short loc_18003570B
0x180035701  mov     edi, 8007000Eh
0x180035706  jmp     loc_1800357D5
0x18003570b  mov     rdi, [rbp+4Fh+var_78]
0x18003570f  mov     [rbp+4Fh+var_A0], r12
0x180035713  mov     rcx, [rdi+10h]; pv
0x180035717  mov     [rdi+10h], r12
0x18003571b  call    cs:__imp_CoTaskMemFree
0x180035721  mov     rax, [rbp+4Fh+lpString1]
0x180035725  lea     rcx, [rbp+4Fh+var_80]
0x180035729  mov     [rdi+10h], rax
0x18003572d  call    ?Detach@?$CComPtrBase@UISyncMgrConflict@@@ATL@@QEAAPEAUISyncMgrConflict@@XZ; ATL::CComPtrBase<ISyncMgrConflict>::Detach(void)
0x180035732  mov     rdx, rax
0x180035735  lea     rcx, [rdi+18h]
0x180035739  call    ?Attach@?$CComPtrBase@VCRenameCanonicalMenuWrapper@@@ATL@@QEAAXPEAVCRenameCanonicalMenuWrapper@@@Z; ATL::CComPtrBase<CRenameCanonicalMenuWrapper>::Attach(CRenameCanonicalMenuWrapper *)
0x18003573e  lea     rcx, [rbp+4Fh+var_88]
0x180035742  call    ??C?$CComPtrBase@UISyncMgrConflictResolveInfo@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UISyncMgrConflictResolveInfo@@@1@XZ; ATL::CComPtrBase<ISyncMgrConflictResolveInfo>::operator->(void)
0x180035747  mov     rdx, [rax+140h]
0x18003574e  lea     rsi, [rax+138h]
0x180035755  cmp     rdx, [rax+150h]
0x18003575c  jnz     short loc_18003576F
0x18003575e  inc     rdx
0x180035761  mov     rcx, rsi
0x180035764  call    ?_EnsureCapacity@?$CTSimpleArray@V?$CComPtr@V?$CTRefObj@UCONFLICT_SET@@VCTRefBase_NoModuleLifetimePolicy@@@@@ATL@@$0PPPPPPPO@V?$CTPolicyLocalMem@V?$CComPtr@V?$CTRefObj@UCONFLICT_SET@@VCTRefBase_NoModuleLifetimePolicy@@@@@ATL@@@@V?$CSimpleArrayStandardCompareHelper@V?$CComPtr@V?$CTRefObj@UCONFLICT_SET@@VCTRefBase_NoModuleLifetimePolicy@@@@@ATL@@@@V?$CSimpleArrayStandardMergeHelper@V?$CComPtr@V?$CTRefObj@UCONFLICT_SET@@VCTRefBase_NoModuleLifetimePolicy@@@@@ATL@@@@@@QEAAJ_K0@Z; CTSimpleArray<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>,4294967294,CTPolicyLocalMem<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>>,CSimpleArrayStandardCompareHelper<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>>,CSimpleArrayStandardMergeHelper<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180035769  mov     edi, eax
0x18003576b  test    eax, eax
0x18003576d  js      short loc_1800357D5
0x18003576f  inc     qword ptr [rsi+8]
0x180035773  mov     rcx, [rsi+8]
0x180035777  mov     rax, [rsi]
0x18003577a  dec     rcx
0x18003577d  lea     rcx, [rax+rcx*8]
0x180035781  test    rcx, rcx
0x180035784  jz      short loc_18003578F
0x180035786  lea     rdx, [rbp+4Fh+var_78]
0x18003578a  call    ??0?$CComPtr@V?$CTRefObj@UCONFLICT_SET@@VCTRefBase_NoModuleLifetimePolicy@@@@@ATL@@QEAA@AEBV01@@Z; ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>(ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>> const &)
0x18003578f  mov     rdx, [r14+8]
0x180035793  mov     edi, r12d
0x180035796  cmp     rdx, [r14+18h]
0x18003579a  jnz     short loc_1800357AD
0x18003579c  inc     rdx
0x18003579f  mov     rcx, r14
0x1800357a2  call    ?_EnsureCapacity@?$CTSimpleArray@V?$CComPtr@V?$CTRefObj@UCONFLICT_SET@@VCTRefBase_NoModuleLifetimePolicy@@@@@ATL@@$0PPPPPPPO@V?$CTPolicyLocalMem@V?$CComPtr@V?$CTRefObj@UCONFLICT_SET@@VCTRefBase_NoModuleLifetimePolicy@@@@@ATL@@@@V?$CSimpleArrayStandardCompareHelper@V?$CComPtr@V?$CTRefObj@UCONFLICT_SET@@VCTRefBase_NoModuleLifetimePolicy@@@@@ATL@@@@V?$CSimpleArrayStandardMergeHelper@V?$CComPtr@V?$CTRefObj@UCONFLICT_SET@@VCTRefBase_NoModuleLifetimePolicy@@@@@ATL@@@@@@QEAAJ_K0@Z; CTSimpleArray<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>,4294967294,CTPolicyLocalMem<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>>,CSimpleArrayStandardCompareHelper<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>>,CSimpleArrayStandardMergeHelper<ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x1800357a7  mov     edi, eax
0x1800357a9  test    eax, eax
0x1800357ab  js      short loc_1800357CD
0x1800357ad  inc     qword ptr [r14+8]
0x1800357b1  mov     rcx, [r14+8]
0x1800357b5  mov     rax, [r14]
0x1800357b8  dec     rcx
0x1800357bb  lea     rcx, [rax+rcx*8]
0x1800357bf  test    rcx, rcx
0x1800357c2  jz      short loc_1800357CD
0x1800357c4  lea     rdx, [rbp+4Fh+var_88]
0x1800357c8  call    ??0?$CComPtr@V?$CTRefObj@UCONFLICT_SET@@VCTRefBase_NoModuleLifetimePolicy@@@@@ATL@@QEAA@AEBV01@@Z; ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>>(ATL::CComPtr<CTRefObj<CONFLICT_SET,CTRefBase_NoModuleLifetimePolicy>> const &)
0x1800357cd  test    edi, edi
0x1800357cf  js      short loc_1800357D5
0x1800357d1  inc     dword ptr [r13+0]
0x1800357d5  lea     rcx, [rbp+4Fh+var_78]
0x1800357d9  call    ??1?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>(void)
0x1800357de  lea     rcx, [rbp+4Fh+var_88]
0x1800357e2  call    ??1?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>(void)
0x1800357e7  mov     esi, [rbp+4Fh+var_B0]
0x1800357ea  mov     r15, [rbp+4Fh+arg_0]
0x1800357ee  mov     rcx, [rbp+4Fh+var_70]
0x1800357f2  test    rcx, rcx
0x1800357f5  jz      short loc_180035807
0x1800357f7  mov     rax, [rcx]
  ... truncated ...
```
