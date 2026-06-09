# CStartMenuProgramsResultSetManager::_EnsureChildResultSetManager(void)

- ea: `0x180033838`
- end: `0x180033bd4`
- name: `?_EnsureChildResultSetManager@CStartMenuProgramsResultSetManager@@AEAAJXZ`
- size: `924`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `3`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002b370`
- `0x18002b590`
- `0x18002c360`

## callees

- `0x180005460`
- `0x1800054b0`
- `0x180005c88`
- `0x180006900`
- `0x1800076dc`
- `0x1800113b4`
- `0x180013638`
- `0x18002850c`
- `0x18002cd68`
- `0x18003166c`
- `0x180033838`
- `0x180035090`
- `0x180038730`
- `0x180038bc0`
- `0x18003a420`
- `0x18003a980`
- `0x180051010`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x1800339f4`
- `SHELL32!SHCreateItemFromIDList` at `0x1800339f4`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180033af1`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180033af1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003386c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003386c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033ba8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033ba8`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateAutoList` at `0x18003393b`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateAutoList` at `0x18003393b`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateSingleVisibleInList` at `0x1800338f2`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateSingleVisibleInList` at `0x1800338f2`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateResultSetFactory` at `0x180033a25`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateResultSetFactory` at `0x180033a25`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateSearchIDListFromAutoList` at `0x18003396f`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateSearchIDListFromAutoList` at `0x18003396f`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CStartMenuProgramsResultSetManager::_EnsureChildResultSetManager(RTL_SRWLOCK *this)
{
  HRESULT ModifiedConditionTree; // ebx
  const unsigned __int16 *Ptr; // rdx
  int v4; // eax
  void (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rcx
  void *v7; // [rsp+60h] [rbp-A0h] BYREF
  void *ppv; // [rsp+68h] [rbp-98h] BYREF
  __int64 v9; // [rsp+70h] [rbp-90h] BYREF
  LPCITEMIDLIST pidl; // [rsp+78h] [rbp-88h] BYREF
  LPCITEMIDLIST v11; // [rsp+80h] [rbp-80h] BYREF
  __int64 v12; // [rsp+88h] [rbp-78h] BYREF
  __int64 v13; // [rsp+90h] [rbp-70h] BYREF
  __int64 v14; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v15[2]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v16[8]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v17; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v18[20]; // [rsp+C0h] [rbp-40h] BYREF
  int v19; // [rsp+D4h] [rbp-2Ch]
  int v20; // [rsp+D8h] [rbp-28h]
  int v21; // [rsp+DCh] [rbp-24h]
  int v22; // [rsp+E0h] [rbp-20h]
  _BYTE v23[8]; // [rsp+128h] [rbp+28h] BYREF
  struct IScope *v24[2]; // [rsp+130h] [rbp+30h] BYREF
  struct ICondition *v25; // [rsp+140h] [rbp+40h] BYREF

  ModifiedConditionTree = 1;
  AcquireSRWLockExclusive(this + 11);
  if ( ATL::CComPtrBase<IResultSetManager>::operator!(&this[20].Ptr) )
  {
    memset_0(v16, 0, 0xB0u);
    v19 = 0x40000000;
    v20 = 2;
    v21 = 1;
    v22 = 16;
    s_InitFolderTypeFromPropertyStore(this[9].Ptr, v18);
    ModifiedConditionTree = CStartMenuProgramsResultSetManager::_GetModifiedConditionTree(
                              (CStartMenuProgramsResultSetManager *)this,
                              &v25);
    if ( ModifiedConditionTree >= 0 )
    {
      ModifiedConditionTree = CStartMenuProgramsResultSetManager::s_GetScope(v24);
      if ( ModifiedConditionTree >= 0 )
      {
        ModifiedConditionTree = CreateSingleVisibleInList(L"item", &GUID_d18f09e2_81c2_4217_a295_43b66fa4e495, v23);
        if ( ModifiedConditionTree >= 0 )
          ModifiedConditionTree = GetStartMenuSearchFolderName(
                                    L"programs",
                                    v24[0],
                                    (struct IShellItemArray *)v24[1],
                                    &v17);
      }
    }
    ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(v15);
    if ( ModifiedConditionTree >= 0 )
    {
      ModifiedConditionTree = SHCreateAutoList(v16, 0, &GUID_607c87f7_0696_4558_a368_de5e59cfe456, v15);
      if ( ModifiedConditionTree >= 0 )
      {
        ModifiedConditionTree = CStartMenuProgramsResultSetManager::_CheckIfCancelled((CStartMenuProgramsResultSetManager *)this);
        if ( ModifiedConditionTree >= 0 )
        {
          v11 = 0;
          ModifiedConditionTree = SHCreateSearchIDListFromAutoList(v15[0], 0, &v11);
          if ( ModifiedConditionTree >= 0 )
          {
            pidl = 0;
            Ptr = (const unsigned __int16 *)this[12].Ptr;
            if ( Ptr )
              v4 = CStartMenuResultSetManagerBase::s_AddTextFilterToLocation(
                     v11,
                     Ptr,
                     (struct _ITEMIDLIST_ABSOLUTE **)&pidl);
            else
              v4 = SHILClone((const struct _ITEMIDLIST_RELATIVE *)v11, (struct _ITEMIDLIST_RELATIVE **)&pidl);
            ModifiedConditionTree = v4;
            if ( v4 >= 0 )
            {
              ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v9);
              ModifiedConditionTree = s_CreateChildShape(this[7].Ptr, &v9);
              if ( ModifiedConditionTree >= 0 )
              {
                ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppv);
                ModifiedConditionTree = SHCreateItemFromIDList(pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
                if ( ModifiedConditionTree >= 0 )
                {
                  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v14);
                  ModifiedConditionTree = CreateResultSetFactory(
                                            ppv,
                                            PKEY_StartMenu_ResultSourceId,
                                            &GUID_8e621d2b_5a4c_450c_8b78_c7f52c1f1d9b,
                                            &v14);
                  if ( ModifiedConditionTree >= 0 )
                  {
                    ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v13);
                    v5 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))this[3].Ptr;
                    if ( v5 )
                      (**v5)(v5, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &v13);
                    ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v12);
                    ModifiedConditionTree = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, const PROPERTYKEY *, PVOID, _QWORD, _DWORD, GUID *, __int64 *))(*(_QWORD *)v14 + 32LL))(
                                              v14,
                                              v13,
                                              v9,
                                              0,
                                              &PKEY_Null,
                                              this[10].Ptr,
                                              0,
                                              0,
                                              &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
                                              &v12);
                    if ( ModifiedConditionTree >= 0 )
                    {
                      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v7);
                      ModifiedConditionTree = SHCoCreateInstance(
                                                0,
                                                &CLSID_ResultSetManager,
                                                0,
                                                &GUID_d6effa92_c1ad_4416_b077_84d5e448bdb8,
                                                &v7);
                      if ( ModifiedConditionTree >= 0 )
                      {
                        ModifiedConditionTree = (*(__int64 (__fastcall **)(void *, __int64, __int64, void *))(*(_QWORD *)v7 + 24LL))(
                                                  v7,
                                                  v12,
                                                  v9,
                                                  ppv);
                        if ( ModifiedConditionTree >= 0 )
                          ModifiedConditionTree = (**(__int64 (__fastcall ***)(void *, GUID *, char *))v7)(
                                                    v7,
                                                    &GUID_d3b521a9_64fb_463e_b2cd_6ebbd1c50330,
                                                    (char *)&this[20]);
                      }
                      ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v7);
                    }
                    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v12);
                    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v13);
                  }
                  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v14);
                }
                ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&ppv);
              }
              ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v9);
            }
            CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&pidl);
          }
          CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&v11);
        }
      }
    }
    ClearAutoListInit((struct AUTOLISTINIT *)v16);
    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)v15);
  }
  ReleaseSRWLockExclusive(this + 11);
  return (unsigned int)ModifiedConditionTree;
}

```

## disassembly

```asm
0x180033838  mov     [rsp-8+arg_8], rbx
0x18003383d  mov     [rsp-8+arg_10], rsi
0x180033842  push    rbp
0x180033843  push    rdi
0x180033844  push    r14
0x180033846  lea     rbp, [rsp-70h]
0x18003384b  sub     rsp, 170h
0x180033852  mov     rax, cs:__security_cookie
0x180033859  xor     rax, rsp
0x18003385c  mov     [rbp+80h+var_20], rax
0x180033860  mov     rdi, rcx
0x180033863  mov     ebx, 1
0x180033868  add     rcx, 58h ; 'X'; SRWLock
0x18003386c  call    cs:__imp_AcquireSRWLockExclusive
0x180033872  lea     r14, [rdi+0A0h]
0x180033879  mov     rcx, r14
0x18003387c  call    ??7?$CComPtrBase@UIResultSetManager@@@ATL@@QEBA_NXZ; ATL::CComPtrBase<IResultSetManager>::operator!(void)
0x180033881  test    al, al
0x180033883  jz      loc_180033BA4
0x180033889  xor     edx, edx; Val
0x18003388b  mov     r8d, 0B0h; Size
0x180033891  lea     rcx, [rbp+80h+var_D0]; void *
0x180033895  call    memset_0
0x18003389a  mov     [rbp+80h+var_AC], 40000000h
0x1800338a1  mov     [rbp+80h+var_A8], 2
0x1800338a8  mov     [rbp+80h+var_A4], ebx
0x1800338ab  mov     [rbp+80h+var_A0], 10h
0x1800338b2  lea     rdx, [rbp+80h+var_C0]
0x1800338b6  mov     rcx, [rdi+48h]
0x1800338ba  call    s_InitFolderTypeFromPropertyStore
0x1800338bf  lea     rdx, [rbp+80h+var_40]; struct ICondition **
0x1800338c3  mov     rcx, rdi; this
0x1800338c6  call    ?_GetModifiedConditionTree@CStartMenuProgramsResultSetManager@@AEAAJPEAPEAUICondition@@@Z; CStartMenuProgramsResultSetManager::_GetModifiedConditionTree(ICondition * *)
0x1800338cb  mov     ebx, eax
0x1800338cd  test    eax, eax
0x1800338cf  js      short loc_180033918
0x1800338d1  lea     rcx, [rbp+80h+var_50]; struct IScope **
0x1800338d5  call    ?s_GetScope@CStartMenuProgramsResultSetManager@@SAJPEAPEAUIScope@@@Z; CStartMenuProgramsResultSetManager::s_GetScope(IScope * *)
0x1800338da  mov     ebx, eax
0x1800338dc  test    eax, eax
0x1800338de  js      short loc_180033918
0x1800338e0  lea     r8, [rbp+80h+var_58]
0x1800338e4  lea     rdx, _GUID_d18f09e2_81c2_4217_a295_43b66fa4e495
0x1800338eb  lea     rcx, aItem; "item"
0x1800338f2  call    cs:__imp_CreateSingleVisibleInList
0x1800338f8  mov     ebx, eax
0x1800338fa  test    eax, eax
0x1800338fc  js      short loc_180033918
0x1800338fe  lea     r9, [rbp+80h+var_C8]; unsigned __int16 **
0x180033902  mov     r8, [rbp+80h+var_48]; struct IShellItemArray *
0x180033906  mov     rdx, [rbp+80h+var_50]; struct IScope *
0x18003390a  lea     rcx, aPrograms; "programs"
0x180033911  call    ?GetStartMenuSearchFolderName@@YAJPEBGPEAUIScope@@PEAUIShellItemArray@@PEAPEAG@Z; GetStartMenuSearchFolderName(ushort const *,IScope *,IShellItemArray *,ushort * *)
0x180033916  mov     ebx, eax
0x180033918  lea     rcx, [rbp+80h+var_E0]; void *
0x18003391c  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180033921  nop
0x180033922  test    ebx, ebx
0x180033924  js      loc_180033B91
0x18003392a  lea     r9, [rbp+80h+var_E0]
0x18003392e  lea     r8, _GUID_607c87f7_0696_4558_a368_de5e59cfe456
0x180033935  xor     edx, edx
0x180033937  lea     rcx, [rbp+80h+var_D0]
0x18003393b  call    cs:__imp_SHCreateAutoList
0x180033941  mov     ebx, eax
0x180033943  test    eax, eax
0x180033945  js      loc_180033B91
0x18003394b  mov     rcx, rdi; this
0x18003394e  call    ?_CheckIfCancelled@CStartMenuProgramsResultSetManager@@AEAAJXZ; CStartMenuProgramsResultSetManager::_CheckIfCancelled(void)
0x180033953  mov     ebx, eax
0x180033955  test    eax, eax
0x180033957  js      loc_180033B91
0x18003395d  mov     [rbp+80h+var_100], 0
0x180033965  lea     r8, [rbp+80h+var_100]
0x180033969  xor     edx, edx
0x18003396b  mov     rcx, [rbp+80h+var_E0]
0x18003396f  call    cs:__imp_SHCreateSearchIDListFromAutoList
0x180033975  mov     ebx, eax
0x180033977  test    eax, eax
0x180033979  js      loc_180033B88
0x18003397f  mov     [rsp+180h+pidl], 0
0x180033988  mov     rdx, [rdi+60h]; unsigned __int16 *
0x18003398c  mov     rcx, [rbp+80h+var_100]; struct _ITEMIDLIST_RELATIVE *
0x180033990  test    rdx, rdx
0x180033993  jz      short loc_1800339A1
0x180033995  lea     r8, [rsp+180h+pidl]; struct _ITEMIDLIST_ABSOLUTE **
0x18003399a  call    ?s_AddTextFilterToLocation@CStartMenuResultSetManagerBase@@KAJPEBU_ITEMIDLIST_ABSOLUTE@@PEBGPEAPEAU2@@Z; CStartMenuResultSetManagerBase::s_AddTextFilterToLocation(_ITEMIDLIST_ABSOLUTE const *,ushort const *,_ITEMIDLIST_ABSOLUTE * *)
0x18003399f  jmp     short loc_1800339AB
0x1800339a1  lea     rdx, [rsp+180h+pidl]; struct _ITEMIDLIST_RELATIVE **
0x1800339a6  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILClone(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE * *)
0x1800339ab  mov     ebx, eax
0x1800339ad  test    eax, eax
0x1800339af  js      loc_180033B7D
0x1800339b5  lea     rcx, [rsp+180h+var_110]; void *
0x1800339ba  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x1800339bf  nop
0x1800339c0  lea     rdx, [rsp+180h+var_110]
0x1800339c5  mov     rcx, [rdi+38h]
0x1800339c9  call    s_CreateChildShape
0x1800339ce  mov     ebx, eax
0x1800339d0  test    eax, eax
0x1800339d2  js      loc_180033B72
0x1800339d8  lea     rcx, [rsp+180h+ppv]; void *
0x1800339dd  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x1800339e2  nop
0x1800339e3  lea     r8, [rsp+180h+ppv]; ppv
0x1800339e8  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800339ef  mov     rcx, [rsp+180h+pidl]; pidl
0x1800339f4  call    cs:__imp_SHCreateItemFromIDList
0x1800339fa  mov     ebx, eax
0x1800339fc  test    eax, eax
0x1800339fe  js      loc_180033B67
0x180033a04  lea     rcx, [rbp+80h+var_E8]; void *
0x180033a08  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180033a0d  nop
0x180033a0e  lea     r9, [rbp+80h+var_E8]
0x180033a12  lea     r8, _GUID_8e621d2b_5a4c_450c_8b78_c7f52c1f1d9b
0x180033a19  lea     rdx, PKEY_StartMenu_ResultSourceId
0x180033a20  mov     rcx, [rsp+180h+ppv]
0x180033a25  call    cs:__imp_CreateResultSetFactory
0x180033a2b  mov     ebx, eax
0x180033a2d  test    eax, eax
0x180033a2f  js      loc_180033B5D
0x180033a35  lea     rcx, [rbp+80h+var_F0]; void *
0x180033a39  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180033a3e  nop
0x180033a3f  mov     rcx, [rdi+18h]
0x180033a43  test    rcx, rcx
0x180033a46  jz      short loc_180033A5E
0x180033a48  mov     rax, [rcx]
0x180033a4b  lea     r8, [rbp+80h+var_F0]
0x180033a4f  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x180033a56  mov     rax, [rax]
0x180033a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a5e  lea     rcx, [rbp+80h+var_F8]; void *
0x180033a62  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180033a67  nop
0x180033a68  mov     rcx, [rbp+80h+var_E8]
0x180033a6c  mov     rax, [rcx]
0x180033a6f  lea     rdx, [rbp+80h+var_F8]
0x180033a73  mov     [rsp+180h+var_138], rdx
0x180033a78  lea     rdx, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295
0x180033a7f  mov     [rsp+180h+var_140], rdx
0x180033a84  mov     [rsp+180h+var_148], 0
0x180033a8c  mov     [rsp+180h+var_150], 0
0x180033a95  mov     r8, [rdi+50h]
0x180033a99  mov     [rsp+180h+var_158], r8
0x180033a9e  lea     rdx, PKEY_Null
0x180033aa5  mov     [rsp+180h+var_160], rdx
0x180033aaa  xor     r9d, r9d
0x180033aad  mov     r8, [rsp+180h+var_110]
0x180033ab2  mov     rdx, [rbp+80h+var_F0]
0x180033ab6  mov     rax, [rax+20h]
0x180033aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033abf  mov     ebx, eax
0x180033ac1  test    eax, eax
0x180033ac3  js      loc_180033B49
0x180033ac9  lea     rcx, [rsp+180h+var_120]; void *
0x180033ace  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180033ad3  nop
0x180033ad4  lea     rax, [rsp+180h+var_120]
0x180033ad9  mov     [rsp+180h+var_160], rax; ppv
0x180033ade  lea     r9, _GUID_d6effa92_c1ad_4416_b077_84d5e448bdb8; riid
0x180033ae5  xor     r8d, r8d; pUnkOuter
0x180033ae8  lea     rdx, CLSID_ResultSetManager; pclsid
0x180033aef  xor     ecx, ecx; pszCLSID
0x180033af1  call    cs:__imp_SHCoCreateInstance
0x180033af7  mov     ebx, eax
0x180033af9  test    eax, eax
0x180033afb  js      short loc_180033B3E
0x180033afd  mov     rcx, [rsp+180h+var_120]
0x180033b02  mov     rax, [rcx]
0x180033b05  mov     r9, [rsp+180h+ppv]
0x180033b0a  mov     r8, [rsp+180h+var_110]
0x180033b0f  mov     rdx, [rbp+80h+var_F8]
0x180033b13  mov     rax, [rax+18h]
0x180033b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b1c  mov     ebx, eax
0x180033b1e  test    eax, eax
0x180033b20  js      short loc_180033B3E
0x180033b22  mov     rcx, [rsp+180h+var_120]
0x180033b27  mov     rax, [rcx]
0x180033b2a  mov     r8, r14
0x180033b2d  lea     rdx, _GUID_d3b521a9_64fb_463e_b2cd_6ebbd1c50330
0x180033b34  mov     rax, [rax]
0x180033b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b3c  mov     ebx, eax
0x180033b3e  lea     rcx, [rsp+180h+var_120]
0x180033b43  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180033b48  nop
0x180033b49  lea     rcx, [rbp+80h+var_F8]
0x180033b4d  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180033b52  nop
0x180033b53  lea     rcx, [rbp+80h+var_F0]
0x180033b57  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180033b5c  nop
0x180033b5d  lea     rcx, [rbp+80h+var_E8]
0x180033b61  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180033b66  nop
0x180033b67  lea     rcx, [rsp+180h+ppv]
0x180033b6c  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180033b71  nop
0x180033b72  lea     rcx, [rsp+180h+var_110]
0x180033b77  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180033b7c  nop
0x180033b7d  lea     rcx, [rsp+180h+pidl]; void *
0x180033b82  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180033b87  nop
0x180033b88  lea     rcx, [rbp+80h+var_100]; void *
0x180033b8c  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180033b91  lea     rcx, [rbp+80h+var_D0]; struct AUTOLISTINIT *
0x180033b95  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x180033b9a  nop
0x180033b9b  lea     rcx, [rbp+80h+var_E0]
0x180033b9f  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180033ba4  lea     rcx, [rdi+58h]; SRWLock
0x180033ba8  call    cs:__imp_ReleaseSRWLockExclusive
0x180033bae  mov     eax, ebx
0x180033bb0  mov     rcx, [rbp+80h+var_20]
0x180033bb4  xor     rcx, rsp; StackCookie
0x180033bb7  call    __security_check_cookie
0x180033bbc  lea     r11, [rsp+180h+var_10]
0x180033bc4  mov     rbx, [r11+28h]
0x180033bc8  mov     rsi, [r11+30h]
0x180033bcc  mov     rsp, r11
0x180033bcf  pop     r14
0x180033bd1  pop     rdi
0x180033bd2  pop     rbp
0x180033bd3  retn
```
