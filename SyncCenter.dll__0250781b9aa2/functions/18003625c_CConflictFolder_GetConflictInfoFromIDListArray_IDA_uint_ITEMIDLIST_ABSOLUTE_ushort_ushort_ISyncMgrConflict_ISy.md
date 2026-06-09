# CConflictFolder::_GetConflictInfoFromIDListArray(_IDA *,uint,_ITEMIDLIST_ABSOLUTE * *,ushort * *,ushort * *,ISyncMgrConflict * *,ISyncMgrConflictItems * *,uint *,ulong *,CLocalSimpleArray<SYNCMGR_CONFLICT_ITEM_TYPE,4294967294> *)

- ea: `0x18003625c`
- end: `0x1800365c4`
- name: `?_GetConflictInfoFromIDListArray@CConflictFolder@@AEAAJPEAU_IDA@@IPEAPEAU_ITEMIDLIST_ABSOLUTE@@PEAPEAG2PEAPEAUISyncMgrConflict@@PEAPEAUISyncMgrConflictItems@@PEAIPEAKPEAV?$CLocalSimpleArray@W4SYNCMGR_CONFLICT_ITEM_TYPE@@$0PPPPPPPO@@@@Z`
- size: `872`
- prototype: `__int64 __fastcall(CConflictFolder *this, unsigned int *, unsigned int, struct _ITEMIDLIST_ABSOLUTE **, _QWORD *, LPVOID *, __int64 *, __int64 *, _DWORD *, int *, _QWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180035358`

## callees

- `0x18000b310`
- `0x18001330c`
- `0x1800133b0`
- `0x1800134dc`
- `0x180013678`
- `0x180031880`
- `0x180032b20`
- `0x180033d7c`
- `0x18003468c`
- `0x180035194`
- `0x180035ccc`
- `0x18003625c`
- `0x18003849c`
- `0x18003852c`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `SHLWAPI!__imp_ualstrcpynW` at `0x1800363be`
- `SHLWAPI!__imp_ualstrcpynW` at `0x1800363be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003632b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800363aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800363fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036580`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036589`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003632b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800363aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800363fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036580`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036589`

## pseudocode

```c
__int64 __fastcall CConflictFolder::_GetConflictInfoFromIDListArray(
        CConflictFolder *this,
        unsigned int *a2,
        unsigned int a3,
        struct _ITEMIDLIST_ABSOLUTE **a4,
        _QWORD *a5,
        LPVOID *a6,
        __int64 *a7,
        __int64 *a8,
        _DWORD *a9,
        int *a10,
        _QWORD *a11)
{
  const struct _ITEMIDLIST_RELATIVE *v14; // rcx
  PERCEIVED *ValidIDCONFLICT; // rsi
  const struct _IDA *v16; // r11
  int v17; // edi
  struct _ITEMIDLIST_ABSOLUTE *v18; // rbx
  void **v19; // rax
  __int64 v20; // rdx
  PWSTR *v21; // r9
  __int64 v22; // rdx
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // r9
  __int64 v25; // rax
  __int64 v26; // rcx
  void *v27; // rax
  void *v28; // rbx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v32; // [rsp+20h] [rbp-E0h]
  unsigned int v33; // [rsp+30h] [rbp-D0h] BYREF
  struct ISyncMgrConflict *v34; // [rsp+38h] [rbp-C8h] BYREF
  int v35; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v36; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v38; // [rsp+58h] [rbp-A8h] BYREF
  void *v39; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+68h] [rbp-98h] BYREF
  __int64 v41; // [rsp+70h] [rbp-90h]
  __int64 v42; // [rsp+78h] [rbp-88h]
  __int64 v43; // [rsp+80h] [rbp-80h]
  struct _ITEMIDLIST_ABSOLUTE *v44; // [rsp+88h] [rbp-78h] BYREF
  __int64 *v45; // [rsp+90h] [rbp-70h]
  __int64 *v46; // [rsp+98h] [rbp-68h]
  _DWORD *v47; // [rsp+A0h] [rbp-60h]
  int *v48; // [rsp+A8h] [rbp-58h]
  WCHAR pszExt[64]; // [rsp+B0h] [rbp-50h] BYREF

  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  *a7 = 0;
  *a8 = 0;
  *a9 = 0;
  v46 = a8;
  v14 = 0;
  *a10 = 0;
  v45 = a7;
  v47 = a9;
  v48 = a10;
  if ( a2 && (a3 == -1 || a3 < *a2) )
    v14 = (const struct _ITEMIDLIST_RELATIVE *)((char *)a2 + a2[a3 + 2]);
  ValidIDCONFLICT = (PERCEIVED *)CConflictFolder::s_GetValidIDCONFLICT(v14);
  if ( ValidIDCONFLICT )
  {
    v18 = IDA_ILClone(v16, a3);
    CoTaskMemFree(0);
    v44 = v18;
    if ( v18 )
    {
      ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(&v34);
      v19 = (void **)ATL::CComPtrBase<ISyncClientFolderItemCache>::operator&(&v34);
      v17 = CConflictFolder::_BindToConflict(this, ValidIDCONFLICT, &GUID_9c204249_c443_4ba4_85ed_c972681db137, v19);
      if ( v17 >= 0 )
      {
        v39 = 0;
        pv = 0;
        v35 = 0;
        ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(&v36);
        v33 = v20;
        v40 = v20;
        v41 = v20;
        v42 = v20;
        v43 = v20;
        CoTaskMemFree(0);
        ualstrcpynW(pszExt, ValidIDCONFLICT + 2, (PERCEIVEDFLAG *)0x40, v21);
        v24 = -1;
        do
          ++v24;
        while ( pszExt[v24] );
        v17 = _AllocStringWorker<CTCoAllocPolicy>(v23, v22, pszExt, v24, v32, &v39);
        if ( v17 < 0 )
          goto LABEL_20;
        CoTaskMemFree(pv);
        CConflictPropertyStore::s_GetSyncItemID(v34, (unsigned __int16 **)&pv);
        ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(&v38);
        v25 = ATL::CComPtrBase<ISyncMgrConflictResolveInfo>::operator->((__int64)&v34);
        v17 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v25 + 56LL))(
                v25,
                &GUID_40a3d052_8bff_4c4b_a338_d4a395700de9,
                &v38);
        if ( v17 >= 0 )
          v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v38 + 24LL))(v38, &v35);
        ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)&v38);
        if ( v17 < 0
          || (v17 = ((__int64 (__fastcall *)(struct ISyncMgrConflict *, __int64 **))v34->lpVtbl->GetItemsArray)(
                      v34,
                      &v36),
              v17 < 0)
          || (v17 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v36 + 24))(v36, &v33), v17 < 0)
          || (v17 = CConflictFolder::_FillItemTypeArray(v26, v36, v33, &v40), v17 < 0) )
        {
LABEL_20:
          v28 = v39;
        }
        else
        {
          v27 = v39;
          *a4 = v18;
          v28 = 0;
          *a5 = v27;
          *a6 = pv;
          v44 = 0;
          pv = 0;
          v29 = ATL::CComPtrBase<ISyncMgrConflict>::Detach(&v34);
          *v45 = v29;
          v30 = ATL::CComPtrBase<ISyncMgrConflict>::Detach(&v36);
          v17 = 0;
          *v46 = v30;
          *v47 = v33;
          *v48 = v35 & 0x1F;
          *a11 = v40;
          a11[2] = v42;
          a11[1] = v41;
          a11[3] = v43;
          v40 = 0;
          v42 = 0;
          v41 = 0;
          v43 = 0;
        }
        CTSimpleArray<enum SYNCMGR_CONFLICT_ITEM_TYPE,4294967294,CTPolicyLocalMem<enum SYNCMGR_CONFLICT_ITEM_TYPE>,CSimpleArrayStandardCompareHelper<enum SYNCMGR_CONFLICT_ITEM_TYPE>,CSimpleArrayStandardMergeHelper<enum SYNCMGR_CONFLICT_ITEM_TYPE>>::RemoveAll(&v40);
        ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)&v36);
        CoTaskMemFree(pv);
        CoTaskMemFree(v28);
      }
      ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)&v34);
    }
    else
    {
      v17 = -2147024882;
    }
    CCoTaskMemPtr<_ITEMIDLIST_ABSOLUTE>::~CCoTaskMemPtr<_ITEMIDLIST_ABSOLUTE>((void **)&v44);
  }
  else
  {
    return 1;
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18003625c  push    rbp
0x18003625e  push    rbx
0x18003625f  push    rsi
0x180036260  push    rdi
0x180036261  push    r12
0x180036263  push    r13
0x180036265  push    r14
0x180036267  push    r15
0x180036269  lea     rbp, [rsp-48h]
0x18003626e  sub     rsp, 148h
0x180036275  mov     rax, cs:__security_cookie
0x18003627c  xor     rax, rsp
0x18003627f  mov     [rbp+80h+var_50], rax
0x180036283  mov     rax, [rbp+80h+arg_30]
0x18003628a  mov     r15, r9
0x18003628d  mov     r12, [rbp+80h+arg_20]
0x180036294  xor     r9d, r9d
0x180036297  mov     r13, [rbp+80h+arg_28]
0x18003629e  mov     rdi, rcx
0x1800362a1  mov     rcx, [rbp+80h+arg_38]
0x1800362a8  mov     r11, rdx
0x1800362ab  mov     rdx, [rbp+80h+arg_40]
0x1800362b2  mov     ebx, r8d
0x1800362b5  mov     r8, [rbp+80h+arg_48]
0x1800362bc  mov     r14, [rbp+80h+arg_50]
0x1800362c3  mov     [r15], r9
0x1800362c6  mov     [r12], r9
0x1800362ca  mov     [r13+0], r9
0x1800362ce  mov     [rax], r9
0x1800362d1  mov     [rcx], r9
0x1800362d4  mov     [rdx], r9d
0x1800362d7  mov     [rbp+80h+var_E8], rcx
0x1800362db  mov     ecx, r9d
0x1800362de  mov     [r8], r9d
0x1800362e1  mov     [rbp+80h+var_F0], rax
0x1800362e5  mov     [rbp+80h+var_E0], rdx
0x1800362e9  mov     [rbp+80h+var_D8], r8
0x1800362ed  test    r11, r11
0x1800362f0  jz      short loc_180036307
0x1800362f2  cmp     ebx, 0FFFFFFFFh
0x1800362f5  jz      short loc_1800362FC
0x1800362f7  cmp     ebx, [r11]
0x1800362fa  jnb     short loc_180036307
0x1800362fc  lea     eax, [rbx+1]
0x1800362ff  mov     ecx, [r11+rax*4+4]
0x180036304  add     rcx, r11; struct _ITEMIDLIST_RELATIVE *
0x180036307  call    ?s_GetValidIDCONFLICT@CConflictFolder@@CAPEFBUtagIDCONFLICT@1@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CConflictFolder::s_GetValidIDCONFLICT(_ITEMIDLIST_RELATIVE const *)
0x18003630c  mov     rsi, rax
0x18003630f  test    rax, rax
0x180036312  jnz     short loc_18003631C
0x180036314  lea     edi, [rax+1]
0x180036317  jmp     loc_1800365A2
0x18003631c  mov     edx, ebx; unsigned int
0x18003631e  mov     rcx, r11; struct _IDA *
0x180036321  call    ?IDA_ILClone@@YAPEAU_ITEMIDLIST_ABSOLUTE@@PEBU_IDA@@I@Z; IDA_ILClone(_IDA const *,uint)
0x180036326  xor     ecx, ecx; pv
0x180036328  mov     rbx, rax
0x18003632b  call    cs:__imp_CoTaskMemFree
0x180036331  mov     [rbp+80h+var_F8], rbx
0x180036335  test    rbx, rbx
0x180036338  jnz     short loc_180036344
0x18003633a  mov     edi, 8007000Eh
0x18003633f  jmp     loc_180036599
0x180036344  lea     rcx, [rsp+180h+var_148]; void *
0x180036349  call    ??0?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(void)
0x18003634e  lea     rcx, [rsp+180h+var_148]; void *
0x180036353  call    ??I?$CComPtrBase@UISyncClientFolderItemCache@@@ATL@@QEAAPEAPEAUISyncClientFolderItemCache@@XZ; ATL::CComPtrBase<ISyncClientFolderItemCache>::operator&(void)
0x180036358  mov     r9, rax; void **
0x18003635b  lea     r8, _GUID_9c204249_c443_4ba4_85ed_c972681db137; struct _GUID *
0x180036362  mov     rdx, rsi; struct CConflictFolder::tagIDCONFLICT *
0x180036365  mov     rcx, rdi; this
0x180036368  call    ?_BindToConflict@CConflictFolder@@AEAAJPEFBUtagIDCONFLICT@1@AEBU_GUID@@PEAPEAX@Z; CConflictFolder::_BindToConflict(CConflictFolder::tagIDCONFLICT const *,_GUID const &,void * *)
0x18003636d  xor     edx, edx
0x18003636f  mov     edi, eax
0x180036371  test    eax, eax
0x180036373  js      loc_18003658F
0x180036379  lea     rcx, [rsp+180h+var_138]; void *
0x18003637e  mov     [rsp+180h+var_120], rdx
0x180036383  mov     [rsp+180h+pv], rdx
0x180036388  mov     [rsp+180h+var_140], edx
0x18003638c  call    ??0?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(void)
0x180036391  xor     ecx, ecx; pv
0x180036393  mov     [rsp+180h+var_150], edx
0x180036397  mov     [rsp+180h+var_118], rdx
0x18003639c  mov     [rsp+180h+var_110], rdx
0x1800363a1  mov     [rsp+180h+var_108], rdx
0x1800363a6  mov     [rbp+80h+var_100], rdx
0x1800363aa  call    cs:__imp_CoTaskMemFree
0x1800363b0  lea     rdx, [rsi+8]; ptype
0x1800363b4  mov     r8d, 40h ; '@'; pflag
0x1800363ba  lea     rcx, [rbp+80h+pszExt]; pszExt
0x1800363be  call    cs:__imp_ualstrcpynW
0x1800363c4  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800363c8  lea     rax, [rbp+80h+pszExt]
0x1800363cc  xor     esi, esi
0x1800363ce  inc     r9
0x1800363d1  cmp     [rax+r9*2], si
0x1800363d6  jnz     short loc_1800363CE
0x1800363d8  lea     rax, [rsp+180h+var_120]
0x1800363dd  lea     r8, [rbp+80h+pszExt]
0x1800363e1  mov     [rsp+180h+var_158], rax
0x1800363e6  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800363eb  mov     edi, eax
0x1800363ed  test    eax, eax
0x1800363ef  js      loc_180036562
0x1800363f5  mov     rcx, [rsp+180h+pv]; pv
0x1800363fa  call    cs:__imp_CoTaskMemFree
0x180036400  mov     rcx, [rsp+180h+var_148]; struct ISyncMgrConflict *
0x180036405  lea     rdx, [rsp+180h+pv]; unsigned __int16 **
0x18003640a  call    ?s_GetSyncItemID@CConflictPropertyStore@@SAJPEAUISyncMgrConflict@@PEAPEAG@Z; CConflictPropertyStore::s_GetSyncItemID(ISyncMgrConflict *,ushort * *)
0x18003640f  lea     rcx, [rsp+180h+var_128]; void *
0x180036414  call    ??0?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(void)
0x180036419  lea     rcx, [rsp+180h+var_148]
0x18003641e  call    ??C?$CComPtrBase@UISyncMgrConflictResolveInfo@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UISyncMgrConflictResolveInfo@@@1@XZ; ATL::CComPtrBase<ISyncMgrConflictResolveInfo>::operator->(void)
0x180036423  mov     r9, rax
0x180036426  lea     r8, [rsp+180h+var_128]
0x18003642b  lea     rdx, _GUID_40a3d052_8bff_4c4b_a338_d4a395700de9
0x180036432  mov     rcx, [rax]
0x180036435  mov     rax, [rcx+38h]
0x180036439  mov     rcx, r9
0x18003643c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036441  mov     edi, eax
0x180036443  test    eax, eax
0x180036445  js      short loc_18003645F
0x180036447  mov     rcx, [rsp+180h+var_128]
0x18003644c  lea     rdx, [rsp+180h+var_140]
0x180036451  mov     rax, [rcx]
0x180036454  mov     rax, [rax+18h]
0x180036458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003645d  mov     edi, eax
0x18003645f  lea     rcx, [rsp+180h+var_128]
0x180036464  call    ??1?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>(void)
0x180036469  test    edi, edi
0x18003646b  js      loc_180036562
0x180036471  mov     rcx, [rsp+180h+var_148]
0x180036476  lea     rdx, [rsp+180h+var_138]
0x18003647b  mov     rax, [rcx]
0x18003647e  mov     rax, [rax+28h]
0x180036482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036487  mov     edi, eax
0x180036489  test    eax, eax
0x18003648b  js      loc_180036562
0x180036491  mov     rcx, [rsp+180h+var_138]
0x180036496  lea     rdx, [rsp+180h+var_150]
0x18003649b  mov     rax, [rcx]
0x18003649e  mov     rax, [rax+18h]
0x1800364a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364a7  mov     edi, eax
0x1800364a9  test    eax, eax
0x1800364ab  js      loc_180036562
0x1800364b1  mov     r8d, [rsp+180h+var_150]
0x1800364b6  lea     r9, [rsp+180h+var_118]
0x1800364bb  mov     rdx, [rsp+180h+var_138]
0x1800364c0  call    ?_FillItemTypeArray@CConflictFolder@@AEAAJPEAUISyncMgrConflictItems@@IPEAV?$CLocalSimpleArray@W4SYNCMGR_CONFLICT_ITEM_TYPE@@$0PPPPPPPO@@@@Z; CConflictFolder::_FillItemTypeArray(ISyncMgrConflictItems *,uint,CLocalSimpleArray<SYNCMGR_CONFLICT_ITEM_TYPE,4294967294> *)
0x1800364c5  mov     edi, eax
0x1800364c7  test    eax, eax
0x1800364c9  js      loc_180036562
0x1800364cf  mov     rax, [rsp+180h+var_120]
0x1800364d4  lea     rcx, [rsp+180h+var_148]
0x1800364d9  mov     [r15], rbx
0x1800364dc  mov     rbx, rsi
0x1800364df  mov     [r12], rax
0x1800364e3  mov     rax, [rsp+180h+pv]
0x1800364e8  mov     [r13+0], rax
0x1800364ec  mov     [rbp+80h+var_F8], rsi
0x1800364f0  mov     [rsp+180h+pv], rsi
0x1800364f5  call    ?Detach@?$CComPtrBase@UISyncMgrConflict@@@ATL@@QEAAPEAUISyncMgrConflict@@XZ; ATL::CComPtrBase<ISyncMgrConflict>::Detach(void)
0x1800364fa  mov     rcx, [rbp+80h+var_F0]
0x1800364fe  mov     [rcx], rax
0x180036501  lea     rcx, [rsp+180h+var_138]
0x180036506  call    ?Detach@?$CComPtrBase@UISyncMgrConflict@@@ATL@@QEAAPEAUISyncMgrConflict@@XZ; ATL::CComPtrBase<ISyncMgrConflict>::Detach(void)
0x18003650b  mov     rcx, [rbp+80h+var_E8]
0x18003650f  mov     edi, esi
0x180036511  mov     [rcx], rax
0x180036514  mov     eax, [rsp+180h+var_150]
0x180036518  mov     rcx, [rbp+80h+var_E0]
0x18003651c  mov     [rcx], eax
0x18003651e  mov     eax, [rsp+180h+var_140]
0x180036522  mov     rcx, [rbp+80h+var_D8]
0x180036526  and     eax, 1Fh
0x180036529  mov     [rcx], eax
0x18003652b  mov     rax, [rsp+180h+var_118]
0x180036530  mov     [r14], rax
0x180036533  mov     rax, [rsp+180h+var_108]
0x180036538  mov     [r14+10h], rax
0x18003653c  mov     rax, [rsp+180h+var_110]
0x180036541  mov     [r14+8], rax
0x180036545  mov     rax, [rbp+80h+var_100]
0x180036549  mov     [r14+18h], rax
0x18003654d  mov     [rsp+180h+var_118], rsi
0x180036552  mov     [rsp+180h+var_108], rsi
0x180036557  mov     [rsp+180h+var_110], rsi
0x18003655c  mov     [rbp+80h+var_100], rsi
0x180036560  jmp     short loc_180036567
0x180036562  mov     rbx, [rsp+180h+var_120]
0x180036567  lea     rcx, [rsp+180h+var_118]
0x18003656c  call    ?RemoveAll@?$CTSimpleArray@W4SYNCMGR_CONFLICT_ITEM_TYPE@@$0PPPPPPPO@V?$CTPolicyLocalMem@W4SYNCMGR_CONFLICT_ITEM_TYPE@@@@V?$CSimpleArrayStandardCompareHelper@W4SYNCMGR_CONFLICT_ITEM_TYPE@@@@V?$CSimpleArrayStandardMergeHelper@W4SYNCMGR_CONFLICT_ITEM_TYPE@@@@@@QEAAXXZ; CTSimpleArray<SYNCMGR_CONFLICT_ITEM_TYPE,4294967294,CTPolicyLocalMem<SYNCMGR_CONFLICT_ITEM_TYPE>,CSimpleArrayStandardCompareHelper<SYNCMGR_CONFLICT_ITEM_TYPE>,CSimpleArrayStandardMergeHelper<SYNCMGR_CONFLICT_ITEM_TYPE>>::RemoveAll(void)
0x180036571  lea     rcx, [rsp+180h+var_138]
0x180036576  call    ??1?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>(void)
0x18003657b  mov     rcx, [rsp+180h+pv]; pv
0x180036580  call    cs:__imp_CoTaskMemFree
0x180036586  mov     rcx, rbx; pv
0x180036589  call    cs:__imp_CoTaskMemFree
0x18003658f  lea     rcx, [rsp+180h+var_148]
0x180036594  call    ??1?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>(void)
0x180036599  lea     rcx, [rbp+80h+var_F8]
0x18003659d  call    ??1?$CCoTaskMemPtr@U_ITEMIDLIST_ABSOLUTE@@@@QEAA@XZ; CCoTaskMemPtr<_ITEMIDLIST_ABSOLUTE>::~CCoTaskMemPtr<_ITEMIDLIST_ABSOLUTE>(void)
0x1800365a2  mov     eax, edi
0x1800365a4  mov     rcx, [rbp+80h+var_50]
0x1800365a8  xor     rcx, rsp; StackCookie
0x1800365ab  call    __security_check_cookie
0x1800365b0  add     rsp, 148h
0x1800365b7  pop     r15
0x1800365b9  pop     r14
0x1800365bb  pop     r13
0x1800365bd  pop     r12
0x1800365bf  pop     rdi
0x1800365c0  pop     rsi
0x1800365c1  pop     rbx
0x1800365c2  pop     rbp
0x1800365c3  retn
```
