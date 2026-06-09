# CMapiManager::GetAllStores(ATL::CSimpleArray<CMapiStore *,ATL::CSimpleArrayEqualHelper<CMapiStore *>> &,ulong)

- ea: `0x18002e1c8`
- end: `0x18002e500`
- name: `?GetAllStores@CMapiManager@@QEAAJAEAV?$CSimpleArray@PEAVCMapiStore@@V?$CSimpleArrayEqualHelper@PEAVCMapiStore@@@ATL@@@ATL@@K@Z`
- size: `824`
- prototype: `__int64 __fastcall(CMapiManager *this, __int64, int)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800236d4`

## callees

- `0x180004c20`
- `0x18000ad14`
- `0x18000e6e0`
- `0x18000f1c4`
- `0x18000fd58`
- `0x1800113ac`
- `0x180011884`
- `0x1800122d8`
- `0x180022a78`
- `0x18002d048`
- `0x18002d270`
- `0x18002d3c8`
- `0x18002d454`
- `0x18002d654`
- `0x18002dc34`
- `0x18002dffc`
- `0x18002e1c8`
- `0x18002e890`
- `0x18002f52c`
- `0x18002f798`
- `0x18003577c`
- `0x180035898`
- `0x180036b6c`
- `0x18003f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002e3e5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002e42d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002e3e5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002e42d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e1f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e1f8`

## string_xrefs

- `0x18002e4cb`: `CMapiManager::GetAllStores() failed since we can't open any stores for on any profile.`

## pseudocode

```c
__int64 __fastcall CMapiManager::GetAllStores(CMapiManager *this, __int64 a2, int a3)
{
  int v3; // r13d
  CMapiManager *v4; // r14
  unsigned int v5; // r15d
  __int64 v6; // rdx
  __int64 v7; // r8
  const wchar_t *v8; // r9
  _QWORD *v9; // rax
  __int64 v10; // rcx
  int AllProfiles; // eax
  int v12; // esi
  int v13; // ebx
  __int64 v14; // rax
  unsigned int i; // r12d
  __int64 v16; // rdx
  const wchar_t *v17; // r8
  volatile signed __int32 *v18; // rcx
  wchar_t *v19; // rbx
  int *v20; // rdi
  volatile signed __int32 *v21; // rbx
  int Session; // eax
  unsigned int v23; // edi
  CMapiSession *v24; // rdi
  int AllStores; // eax
  int v26; // r13d
  __int64 v27; // r14
  _QWORD *v28; // rax
  __int64 v30; // [rsp+20h] [rbp-58h] BYREF
  wchar_t *v31; // [rsp+28h] [rbp-50h] BYREF
  CMapiSession *v32; // [rsp+30h] [rbp-48h] BYREF
  struct _RTL_CRITICAL_SECTION *v33; // [rsp+38h] [rbp-40h] BYREF
  __int64 v34; // [rsp+40h] [rbp-38h] BYREF
  void *Block; // [rsp+48h] [rbp-30h] BYREF
  __int64 v36; // [rsp+50h] [rbp-28h]
  _QWORD v37[4]; // [rsp+58h] [rbp-20h] BYREF
  __int64 v41; // [rsp+D8h] [rbp+60h] BYREF

  v3 = a3;
  v4 = this;
  v33 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v5 = 0;
  v30 = 0;
  v9 = TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>::operator&(
         &v30,
         v6,
         v7,
         v8);
  AllProfiles = CMapiManager::GetAllProfiles(v10, v9);
  v12 = AllProfiles;
  if ( AllProfiles >= 0 )
  {
    v13 = 0;
    LODWORD(v41) = 0;
    v14 = v30;
    if ( !v30 )
    {
LABEL_32:
      CMapiManager::ReleaseUnusedSessions(v4);
      if ( !v13 )
      {
        v12 = -2147216890;
        CLogger::Info(
          -2147216890,
          L"CMapiManager::GetAllStores() failed since we can't open any stores for on any profile.");
      }
      goto LABEL_34;
    }
    v37[0] = 0;
    v37[1] = 0;
    for ( i = 0; ; ++i )
    {
      if ( (signed int)i >= *(_DWORD *)(v14 + 8) )
      {
        CheckScopeExcludedStoresandICSCleanup(a2, v3 | 4);
        ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll(v37);
        v13 = v41;
        goto LABEL_32;
      }
      ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)&v31);
      v32 = 0;
      v16 = *(_QWORD *)ATL::CSimpleArray<CMapiStore *,ATL::CSimpleArrayEqualHelper<CMapiStore *>>::operator[](v30, i);
      v18 = (volatile signed __int32 *)(v16 - 24);
      v19 = v31;
      v20 = (int *)(v31 - 12);
      if ( (wchar_t *)(v16 - 24) != v31 - 12 )
      {
        if ( v20[4] >= 0 && *(_QWORD *)v18 == *(_QWORD *)v20 )
        {
          v21 = ATL::CSimpleStringT<wchar_t,0>::CloneData(v18);
          ATL::CStringData::Release((ATL::CStringData *)v20);
          v19 = (wchar_t *)(v21 + 6);
          v31 = v19;
        }
        else
        {
          ATL::CSimpleStringT<wchar_t,0>::SetString(&v31, v16, *(unsigned int *)(v16 - 16));
          v19 = v31;
        }
      }
      Session = CMapiManager::GetSession(v4, v19, v17, &v32);
      v23 = Session;
      if ( Session < 0 )
      {
        CLogger::Error((unsigned int)Session, L"CMapiManager::GetAllStores() failed to get session for %s", v19);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v32);
        ATL::CStringData::Release((ATL::CStringData *)(v19 - 12));
        ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll(v37);
        TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>::~TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>(&v30);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v33);
        return v23;
      }
      v24 = v32;
      v12 = CMapiSession::CloseAllStores(v32);
      if ( v12 >= 0 )
      {
        Block = 0;
        v36 = 0;
        AllStores = CMapiSession::GetAllStores(v24, &Block, v3 & 0xFFFFFFF9);
        v12 = AllStores;
        if ( AllStores < 0 )
        {
          CLogger::Error((unsigned int)AllStores, L"CMapiManager::GetAllStores() failed to get to stores for %s", v19);
          if ( Block )
            free(Block);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v32);
          ATL::CStringData::Release((ATL::CStringData *)(v19 - 12));
          ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll(v37);
          goto LABEL_34;
        }
        if ( (int)v36 > 0 )
        {
          v26 = v41;
          do
          {
            ++v26;
            v27 = *(_QWORD *)ATL::CSimpleArray<CMapiStore *,ATL::CSimpleArrayEqualHelper<CMapiStore *>>::operator[](
                               &Block,
                               v5);
            v34 = v27;
            if ( v27 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
            v41 = v27 + 40;
            if ( (int)ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::Find(
                        v37,
                        v27 + 40) < 0 )
            {
              v41 = v27;
              ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::Add(a2, &v41);
              ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::Add(
                v37,
                v27 + 40);
            }
            else
            {
              v28 = (_QWORD *)ATL::CSimpleArray<CMapiStore *,ATL::CSimpleArrayEqualHelper<CMapiStore *>>::operator[](
                                &Block,
                                v5);
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v28 + 16LL))(*v28);
              CMapiSession::ReleaseStore(v24, v41);
            }
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
            ++v5;
          }
          while ( (int)v5 < (int)v36 );
          LODWORD(v41) = v26;
          v19 = v31;
          v3 = a3;
          v4 = this;
        }
        v5 = 0;
        if ( Block )
        {
          free(Block);
          Block = 0;
        }
        v36 = 0;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v32);
      ATL::CStringData::Release((ATL::CStringData *)(v19 - 12));
      v14 = v30;
    }
  }
  CLogger::Error((unsigned int)AllProfiles, L"CMapiManager::GetAllStores() failed to get profiles");
LABEL_34:
  TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>::~TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>(&v30);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v33);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002e1c8  mov     [rsp-40h+arg_10], r8d
0x18002e1cd  mov     [rsp-40h+arg_8], rdx
0x18002e1d2  mov     [rsp-40h+arg_0], rcx
0x18002e1d7  push    rbp
0x18002e1d8  push    rbx
0x18002e1d9  push    rsi
0x18002e1da  push    rdi
0x18002e1db  push    r12
0x18002e1dd  push    r13
0x18002e1df  push    r14
0x18002e1e1  push    r15
0x18002e1e3  mov     rbp, rsp
0x18002e1e6  sub     rsp, 78h
0x18002e1ea  mov     r13d, r8d
0x18002e1ed  mov     r14, rcx
0x18002e1f0  add     rcx, 58h ; 'X'; lpCriticalSection
0x18002e1f4  mov     [rbp+var_40], rcx
0x18002e1f8  call    cs:__imp_EnterCriticalSection
0x18002e1fe  nop
0x18002e1ff  xor     r15d, r15d
0x18002e202  mov     [rbp+var_58], r15
0x18002e206  lea     rcx, [rbp+var_58]
0x18002e20a  call    ??I?$TPointer@V?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@@@QEAAPEAPEAV?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@XZ; TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>::operator&(void)
0x18002e20f  mov     rdx, rax
0x18002e212  call    ?GetAllProfiles@CMapiManager@@QEAAJPEAPEAV?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; CMapiManager::GetAllProfiles(ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>> * *)
0x18002e217  mov     esi, eax
0x18002e219  test    eax, eax
0x18002e21b  jns     short loc_18002E230
0x18002e21d  lea     rdx, aCmapimanagerGe_2; "CMapiManager::GetAllStores() failed to "...
0x18002e224  mov     ecx, eax; int
0x18002e226  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x18002e22b  jmp     loc_18002E4DA
0x18002e230  mov     ebx, r15d
0x18002e233  mov     dword ptr [rbp+arg_18], ebx
0x18002e236  mov     rax, [rbp+var_58]
0x18002e23a  test    rax, rax
0x18002e23d  jz      loc_18002E4BA
0x18002e243  mov     [rbp+var_20], r15
0x18002e247  mov     [rbp+var_18], r15
0x18002e24b  mov     r12d, r15d
0x18002e24e  cmp     r12d, [rax+8]
0x18002e252  jge     loc_18002E49D
0x18002e258  lea     rcx, [rbp+var_50]
0x18002e25c  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18002e261  nop
0x18002e262  mov     [rbp+var_48], r15
0x18002e266  mov     edx, r12d
0x18002e269  mov     rcx, [rbp+var_58]
0x18002e26d  call    ??A?$CSimpleArray@PEAVCMapiStore@@V?$CSimpleArrayEqualHelper@PEAVCMapiStore@@@ATL@@@ATL@@QEAAAEAPEAVCMapiStore@@H@Z; ATL::CSimpleArray<CMapiStore *,ATL::CSimpleArrayEqualHelper<CMapiStore *>>::operator[](int)
0x18002e272  mov     rdx, [rax]
0x18002e275  lea     rcx, [rdx-18h]
0x18002e279  mov     rbx, [rbp+var_50]
0x18002e27d  lea     rdi, [rbx-18h]
0x18002e281  cmp     rcx, rdi
0x18002e284  jz      short loc_18002E2BF
0x18002e286  cmp     [rdi+10h], r15d
0x18002e28a  jl      short loc_18002E2AE
0x18002e28c  mov     rax, [rdi]
0x18002e28f  cmp     [rcx], rax
0x18002e292  jnz     short loc_18002E2AE
0x18002e294  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x18002e299  mov     rbx, rax
0x18002e29c  mov     rcx, rdi; this
0x18002e29f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e2a4  add     rbx, 18h
0x18002e2a8  mov     [rbp+var_50], rbx
0x18002e2ac  jmp     short loc_18002E2BF
0x18002e2ae  mov     r8d, [rdx-10h]
0x18002e2b2  lea     rcx, [rbp+var_50]
0x18002e2b6  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18002e2bb  mov     rbx, [rbp+var_50]
0x18002e2bf  lea     r9, [rbp+var_48]; struct CMapiSession **
0x18002e2c3  mov     rdx, rbx; wchar_t *
0x18002e2c6  mov     rcx, r14; this
0x18002e2c9  call    ?GetSession@CMapiManager@@QEAAJPEB_W0PEAPEAVCMapiSession@@@Z; CMapiManager::GetSession(wchar_t const *,wchar_t const *,CMapiSession * *)
0x18002e2ce  mov     edi, eax
0x18002e2d0  test    eax, eax
0x18002e2d2  js      loc_18002E456
0x18002e2d8  mov     rdi, [rbp+var_48]
0x18002e2dc  mov     rcx, rdi; this
0x18002e2df  call    ?CloseAllStores@CMapiSession@@QEAAJXZ; CMapiSession::CloseAllStores(void)
0x18002e2e4  mov     esi, eax
0x18002e2e6  test    eax, eax
0x18002e2e8  js      loc_18002E3F3
0x18002e2ee  mov     [rbp+Block], r15
0x18002e2f2  mov     [rbp+var_28], 0
0x18002e2fa  mov     r8d, r13d
0x18002e2fd  and     r8d, 0FFFFFFF9h
0x18002e301  lea     rdx, [rbp+Block]
0x18002e305  mov     rcx, rdi
0x18002e308  call    ?GetAllStores@CMapiSession@@QEAAJAEAV?$CSimpleArray@PEAVCMapiStore@@V?$CSimpleArrayEqualHelper@PEAVCMapiStore@@@ATL@@@ATL@@K@Z; CMapiSession::GetAllStores(ATL::CSimpleArray<CMapiStore *,ATL::CSimpleArrayEqualHelper<CMapiStore *>> &,ulong)
0x18002e30d  mov     esi, eax
0x18002e30f  test    eax, eax
0x18002e311  js      loc_18002E412
0x18002e317  cmp     dword ptr [rbp+var_28], 0
0x18002e31b  jle     loc_18002E3D9
0x18002e321  mov     r13d, dword ptr [rbp+arg_18]
0x18002e325  mov     rbx, [rbp+arg_8]
0x18002e329  inc     r13d
0x18002e32c  mov     edx, r15d
0x18002e32f  lea     rcx, [rbp+Block]
0x18002e333  call    ??A?$CSimpleArray@PEAVCMapiStore@@V?$CSimpleArrayEqualHelper@PEAVCMapiStore@@@ATL@@@ATL@@QEAAAEAPEAVCMapiStore@@H@Z; ATL::CSimpleArray<CMapiStore *,ATL::CSimpleArrayEqualHelper<CMapiStore *>>::operator[](int)
0x18002e338  mov     r14, [rax]
0x18002e33b  mov     [rbp+var_38], r14
0x18002e33f  test    r14, r14
0x18002e342  jz      short loc_18002E354
0x18002e344  mov     rax, [r14]
0x18002e347  mov     rcx, r14
0x18002e34a  mov     rax, [rax+8]
0x18002e34e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e353  nop
0x18002e354  lea     rax, [r14+28h]
0x18002e358  mov     [rbp+arg_18], rax
0x18002e35c  mov     rdx, rax
0x18002e35f  lea     rcx, [rbp+var_20]
0x18002e363  call    ?Find@?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAHAEBV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@2@@Z; ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::Find(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x18002e368  test    eax, eax
0x18002e36a  js      short loc_18002E395
0x18002e36c  mov     edx, r15d
0x18002e36f  lea     rcx, [rbp+Block]
0x18002e373  call    ??A?$CSimpleArray@PEAVCMapiStore@@V?$CSimpleArrayEqualHelper@PEAVCMapiStore@@@ATL@@@ATL@@QEAAAEAPEAVCMapiStore@@H@Z; ATL::CSimpleArray<CMapiStore *,ATL::CSimpleArrayEqualHelper<CMapiStore *>>::operator[](int)
0x18002e378  mov     rcx, [rax]
0x18002e37b  mov     rax, [rcx]
0x18002e37e  mov     rax, [rax+10h]
0x18002e382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e387  mov     rdx, [rbp+arg_18]
0x18002e38b  mov     rcx, rdi
0x18002e38e  call    ?ReleaseStore@CMapiSession@@QEAAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSession::ReleaseStore(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x18002e393  jmp     short loc_18002E3B3
0x18002e395  mov     [rbp+arg_18], r14
0x18002e399  lea     rdx, [rbp+arg_18]
0x18002e39d  mov     rcx, rbx
0x18002e3a0  call    ?Add@?$CSimpleArray@PEAXV?$CSimpleArrayEqualHelper@PEAX@ATL@@@ATL@@QEAAHAEBQEAX@Z; ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::Add(void * const &)
0x18002e3a5  lea     rdx, [r14+28h]
0x18002e3a9  lea     rcx, [rbp+var_20]
0x18002e3ad  call    ?Add@?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAHAEBV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@2@@Z; ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::Add(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x18002e3b2  nop
0x18002e3b3  lea     rcx, [rbp+var_38]
0x18002e3b7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e3bc  inc     r15d
0x18002e3bf  cmp     r15d, dword ptr [rbp+var_28]
0x18002e3c3  jl      loc_18002E329
0x18002e3c9  mov     dword ptr [rbp+arg_18], r13d
0x18002e3cd  mov     rbx, [rbp+var_50]
0x18002e3d1  mov     r13d, [rbp+arg_10]
0x18002e3d5  mov     r14, [rbp+arg_0]
0x18002e3d9  mov     rcx, [rbp+Block]; Block
0x18002e3dd  xor     r15d, r15d
0x18002e3e0  test    rcx, rcx
0x18002e3e3  jz      short loc_18002E3EF
0x18002e3e5  call    cs:__imp_free
0x18002e3eb  mov     [rbp+Block], r15
0x18002e3ef  mov     [rbp+var_28], r15
0x18002e3f3  lea     rcx, [rbp+var_48]
0x18002e3f7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e3fc  nop
0x18002e3fd  lea     rcx, [rbx-18h]; this
0x18002e401  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e406  inc     r12d
0x18002e409  mov     rax, [rbp+var_58]
0x18002e40d  jmp     loc_18002E24E
0x18002e412  mov     r8, rbx
0x18002e415  lea     rdx, aCmapimanagerGe; "CMapiManager::GetAllStores() failed to "...
0x18002e41c  mov     ecx, esi; int
0x18002e41e  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x18002e423  nop
0x18002e424  mov     rcx, [rbp+Block]; Block
0x18002e428  test    rcx, rcx
0x18002e42b  jz      short loc_18002E434
0x18002e42d  call    cs:__imp_free
0x18002e433  nop
0x18002e434  lea     rcx, [rbp+var_48]
0x18002e438  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e43d  nop
0x18002e43e  lea     rcx, [rbx-18h]; this
0x18002e442  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e447  nop
0x18002e448  lea     rcx, [rbp+var_20]
0x18002e44c  call    ?RemoveAll@?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll(void)
0x18002e451  jmp     loc_18002E4DA
0x18002e456  mov     r8, rbx
0x18002e459  lea     rdx, aCmapimanagerGe_0; "CMapiManager::GetAllStores() failed to "...
0x18002e460  mov     ecx, edi; int
0x18002e462  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x18002e467  nop
0x18002e468  lea     rcx, [rbp+var_48]
0x18002e46c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e471  nop
0x18002e472  lea     rcx, [rbx-18h]; this
0x18002e476  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e47b  nop
0x18002e47c  lea     rcx, [rbp+var_20]
0x18002e480  call    ?RemoveAll@?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll(void)
0x18002e485  nop
0x18002e486  lea     rcx, [rbp+var_58]
0x18002e48a  call    ??1?$TPointer@V?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@@@QEAA@XZ; TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>::~TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>(void)
0x18002e48f  nop
0x18002e490  lea     rcx, [rbp+var_40]
0x18002e494  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002e499  mov     eax, edi
0x18002e49b  jmp     short loc_18002E4EF
0x18002e49d  or      r13d, 4
0x18002e4a1  mov     edx, r13d
0x18002e4a4  mov     rcx, [rbp+arg_8]
0x18002e4a8  call    ?CheckScopeExcludedStoresandICSCleanup@@YAJAEAV?$CSimpleArray@PEAVCMapiStore@@V?$CSimpleArrayEqualHelper@PEAVCMapiStore@@@ATL@@@ATL@@K@Z; CheckScopeExcludedStoresandICSCleanup(ATL::CSimpleArray<CMapiStore *,ATL::CSimpleArrayEqualHelper<CMapiStore *>> &,ulong)
0x18002e4ad  nop
0x18002e4ae  lea     rcx, [rbp+var_20]
0x18002e4b2  call    ?RemoveAll@?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll(void)
0x18002e4b7  mov     ebx, dword ptr [rbp+arg_18]
0x18002e4ba  mov     rcx, r14; this
0x18002e4bd  call    ?ReleaseUnusedSessions@CMapiManager@@QEAAXXZ; CMapiManager::ReleaseUnusedSessions(void)
0x18002e4c2  test    ebx, ebx
0x18002e4c4  jnz     short loc_18002E4DA
0x18002e4c6  mov     esi, 80041206h
0x18002e4cb  lea     rdx, aCmapimanagerGe_1; "CMapiManager::GetAllStores() failed sin"...
0x18002e4d2  mov     ecx, esi; int
0x18002e4d4  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x18002e4d9  nop
0x18002e4da  lea     rcx, [rbp+var_58]
0x18002e4de  call    ??1?$TPointer@V?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@@@QEAA@XZ; TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>::~TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>(void)
0x18002e4e3  nop
0x18002e4e4  lea     rcx, [rbp+var_40]
0x18002e4e8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002e4ed  mov     eax, esi
0x18002e4ef  add     rsp, 78h
0x18002e4f3  pop     r15
0x18002e4f5  pop     r14
0x18002e4f7  pop     r13
0x18002e4f9  pop     r12
0x18002e4fb  pop     rdi
0x18002e4fc  pop     rsi
0x18002e4fd  pop     rbx
0x18002e4fe  pop     rbp
0x18002e4ff  retn
```
