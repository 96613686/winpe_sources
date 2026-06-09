# SystemSettings::StorageSenseHandlers::TemporaryFilesCleanupRecommendationList::InitializeTemporaryFilesCleanupRecommendationList(void)

- ea: `0x180065f34`
- end: `0x18006646b`
- name: `?InitializeTemporaryFilesCleanupRecommendationList@TemporaryFilesCleanupRecommendationList@StorageSenseHandlers@SystemSettings@@QEAAJXZ`
- size: `1335`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::TemporaryFilesCleanupRecommendationList *__hidden this)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180063a50`
- `0x1800659e0`

## callees

- `0x180012374`
- `0x180014940`
- `0x180019d30`
- `0x18001f230`
- `0x18001fc0c`
- `0x180026994`
- `0x18004ef90`
- `0x18005c450`
- `0x18005d794`
- `0x18005e2e0`
- `0x18005fa88`
- `0x1800604a8`
- `0x180062404`
- `0x180065f34`
- `0x18006a180`
- `0x180074b70`
- `0x18007523c`
- `0x180075840`
- `0x1800759b8`
- `0x18008cb08`
- `0x1800e3010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180066103`
- `msvcp_win!_Mtx_unlock` at `0x180066333`
- `msvcp_win!_Mtx_unlock` at `0x180066103`
- `msvcp_win!_Mtx_unlock` at `0x180066333`

## string_xrefs

- `0x180065f98`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommendationlist.cpp`
- `0x180065ffb`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommendationlist.cpp`
- `0x1800660ad`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommendationlist.cpp`
- `0x18006636f`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommendationlist.cpp`
- `0x180066429`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommendationlist.cpp`
- `0x180065f7d`: `CleanupRecommendations`
- `0x180065fda`: `CleanupRecommendations`
- `0x180066092`: `CleanupRecommendations`
- `0x180066354`: `CleanupRecommendations`
- `0x180066408`: `CleanupRecommendations`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall SystemSettings::StorageSenseHandlers::TemporaryFilesCleanupRecommendationList::InitializeTemporaryFilesCleanupRecommendationList(
        SystemSettings::StorageSenseHandlers::TemporaryFilesCleanupRecommendationList *this)
{
  struct _Mtx_internal_imp_t *v2; // rdi
  int UserSelectableCleanupPlugins; // ebx
  struct SystemSettings::StorageSenseHandlers::RecommendationSingleton *Instance; // rax
  __int64 Recommender; // rax
  SystemSettings::StorageSenseHandlers::CStorageCleanupItem **v7; // r12
  SystemSettings::StorageSenseHandlers::CStorageCleanupItem **v8; // r14
  bool v9; // zf
  __int64 v10; // rax
  char *v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rcx
  char IsSelected; // al
  __int64 v15; // r9
  char v16; // r15
  __int64 v17; // rdx
  struct SystemSettings::StorageSenseHandlers::RecommendationSingleton *v18; // rax
  __int64 v19; // r8
  int v20; // r15d
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  char v24; // [rsp+38h] [rbp-41h] BYREF
  __int64 v25; // [rsp+40h] [rbp-39h]
  __int64 v26; // [rsp+48h] [rbp-31h] BYREF
  std::_Ref_count_base *v27; // [rsp+50h] [rbp-29h]
  __int64 v28; // [rsp+58h] [rbp-21h] BYREF
  std::_Ref_count_base *v29; // [rsp+60h] [rbp-19h]
  _BYTE v30[8]; // [rsp+68h] [rbp-11h] BYREF
  std::_Ref_count_base *v31; // [rsp+70h] [rbp-9h]
  __int128 v32; // [rsp+78h] [rbp-1h] BYREF
  __int64 v33; // [rsp+88h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  __int64 v35; // [rsp+E0h] [rbp+67h] BYREF
  __int64 v36; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 *v37; // [rsp+F0h] [rbp+77h] BYREF
  char *v38; // [rsp+F8h] [rbp+7Fh]

  v2 = (SystemSettings::StorageSenseHandlers::TemporaryFilesCleanupRecommendationList *)((char *)this + 256);
  v38 = (char *)this + 256;
  std::_Mutex_base::lock((SystemSettings::StorageSenseHandlers::TemporaryFilesCleanupRecommendationList *)((char *)this + 256));
  UserSelectableCleanupPlugins = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::Clear(*((_QWORD *)this + 26));
  if ( UserSelectableCleanupPlugins < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x3A3,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
      (const char *)(unsigned int)UserSelectableCleanupPlugins,
      (int)"%hs",
      "CleanupRecommendations");
LABEL_18:
    _Mtx_unlock(v2);
    return (unsigned int)UserSelectableCleanupPlugins;
  }
  Instance = SystemSettings::StorageSenseHandlers::RecommendationSingleton::GetInstance();
  Recommender = SystemSettings::StorageSenseHandlers::RecommendationSingleton::GetRecommender(Instance, 2);
  SystemSettings::StorageSenseHandlers::TemporaryFilesCleanupRecommender::GetStorageSenseTemporaryFilesCleanupWrapper(
    Recommender,
    &v26);
  if ( !v26 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x3A8,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
      (const char *)0x8007000ELL,
      (int)"%hs",
      "CleanupRecommendations");
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
    UserSelectableCleanupPlugins = -2147024882;
    goto LABEL_18;
  }
  v32 = 0;
  v33 = 0;
  UserSelectableCleanupPlugins = SystemSettings::StorageSenseHandlers::StorageSenseTemporaryFilesCleanupWrapper::GetUserSelectableCleanupPlugins(
                                   v26,
                                   &v32);
  if ( UserSelectableCleanupPlugins == -2147483638 )
  {
    if ( (_QWORD)v32 )
    {
      std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem>>>(
        v32,
        *((_QWORD *)&v32 + 1));
      std::_Deallocate<16>(v32, (v33 - v32) & 0xFFFFFFFFFFFFFFF8uLL);
      v32 = 0;
      v33 = 0;
    }
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
    UserSelectableCleanupPlugins = 0;
    goto LABEL_18;
  }
  if ( UserSelectableCleanupPlugins < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x3B2,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
      (const char *)(unsigned int)UserSelectableCleanupPlugins,
      (int)"%hs",
      "CleanupRecommendations");
    if ( (_QWORD)v32 )
    {
      std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem>>>(
        v32,
        *((_QWORD *)&v32 + 1));
      std::_Deallocate<16>(v32, (v33 - v32) & 0xFFFFFFFFFFFFFFF8uLL);
      v32 = 0;
      v33 = 0;
    }
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
    goto LABEL_18;
  }
  v7 = (SystemSettings::StorageSenseHandlers::CStorageCleanupItem **)*((_QWORD *)&v32 + 1);
  v8 = (SystemSettings::StorageSenseHandlers::CStorageCleanupItem **)v32;
  v9 = (_QWORD)v32 == *((_QWORD *)&v32 + 1);
  if ( (_QWORD)v32 == *((_QWORD *)&v32 + 1) )
  {
LABEL_37:
    *((_BYTE *)this + 248) = !v9;
    *((_BYTE *)this + 249) = 1;
    SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_18010F168);
    SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_18010F140);
    SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_18010F210);
    if ( (_QWORD)v32 )
    {
      std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem>>>(
        v32,
        *((_QWORD *)&v32 + 1));
      std::_Deallocate<16>(v32, (v33 - v32) & 0xFFFFFFFFFFFFFFF8uLL);
      v32 = 0;
      v33 = 0;
    }
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
    v20 = 0;
  }
  else
  {
    while ( 1 )
    {
      v35 = 0;
      (*(void (__fastcall **)(SystemSettings::StorageSenseHandlers::TemporaryFilesCleanupRecommendationList *))(*(_QWORD *)this + 8LL))(this);
      v37 = &v35;
      v10 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v37);
      Microsoft::WRL::AsWeak<SystemSettings::StorageSenseHandlers::FileRecommendationListBase>(this, v10);
      v11 = (char *)Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::TemporaryFilesCleanupRecommendationSetting,Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CStorageCleanupItem> &,Microsoft::WRL::WeakRef &>(
                      &v36,
                      v8,
                      &v35);
      v12 = 0;
      if ( &v24 != v11 )
      {
        v12 = *(_QWORD *)v11;
        *(_QWORD *)v11 = 0;
      }
      v25 = v12;
      v13 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      if ( !v12 )
        break;
      IsSelected = SystemSettings::StorageSenseHandlers::CStorageCleanupItem::GetIsSelected(*v8);
      v16 = IsSelected;
      if ( IsSelected != *(_BYTE *)(v12 + 224) )
      {
        *(_BYTE *)(v12 + 224) = IsSelected;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)(v12 + 208) + 8LL))(v12 + 208);
      }
      if ( v16 )
      {
        std::make_shared<SystemSettings::StorageSenseHandlers::TemporaryFilesCleanupSelectionChangedNotification,>(&v28);
        v17 = v28;
        *(_BYTE *)(v28 + 8) = 1;
        *(_QWORD *)(v17 + 16) = *(_QWORD *)(*(_QWORD *)(v12 + 264) + 272LL);
        *(_BYTE *)(v17 + 24) = 1;
        v18 = SystemSettings::StorageSenseHandlers::RecommendationSingleton::GetInstance();
        std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>(
          v30,
          &v28,
          v18);
        v37 = (__int64 *)v30;
        SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(
          v19,
          &v37);
        if ( v31 )
          std::_Ref_count_base::_Decref(v31);
        if ( v29 )
          std::_Ref_count_base::_Decref(v29);
      }
      LOBYTE(v15) = 1;
      v20 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(
              *((_QWORD *)this + 26),
              0,
              v12,
              v15);
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x3D1,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
          (const char *)(unsigned int)v20,
          (int)"%hs",
          "CleanupRecommendations",
          this);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        (*(void (__fastcall **)(SystemSettings::StorageSenseHandlers::TemporaryFilesCleanupRecommendationList *))(*(_QWORD *)this + 16LL))(this);
        v22 = v35;
        if ( v35 )
        {
          v35 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        }
        goto LABEL_45;
      }
      *(_QWORD *)(v12 + 104) = this;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      (*(void (__fastcall **)(SystemSettings::StorageSenseHandlers::TemporaryFilesCleanupRecommendationList *))(*(_QWORD *)this + 16LL))(this);
      v21 = v35;
      if ( v35 )
      {
        v35 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      if ( ++v8 == v7 )
      {
        v9 = (_QWORD)v32 == *((_QWORD *)&v32 + 1);
        goto LABEL_37;
      }
    }
    v20 = -2147024882;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x3BD,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
      (const char *)0x8007000ELL,
      (int)"%hs",
      "CleanupRecommendations",
      this);
    (*(void (__fastcall **)(SystemSettings::StorageSenseHandlers::TemporaryFilesCleanupRecommendationList *))(*(_QWORD *)this + 16LL))(this);
    v23 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
LABEL_45:
    if ( (_QWORD)v32 )
    {
      std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem>>>(
        v32,
        *((_QWORD *)&v32 + 1));
      std::_Deallocate<16>(v32, (v33 - v32) & 0xFFFFFFFFFFFFFFF8uLL);
      v32 = 0;
      v33 = 0;
    }
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
  }
  _Mtx_unlock(v2);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180065f34  push    rbp
0x180065f36  push    rbx
0x180065f37  push    rsi
0x180065f38  push    rdi
0x180065f39  push    r12
0x180065f3b  push    r13
0x180065f3d  push    r14
0x180065f3f  push    r15
0x180065f41  lea     rbp, [rsp-1Fh]
0x180065f46  sub     rsp, 98h
0x180065f4d  mov     rsi, rcx
0x180065f50  lea     rdi, [rcx+100h]
0x180065f57  mov     [rbp+57h+arg_18], rdi
0x180065f5b  mov     rcx, rdi; this
0x180065f5e  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180065f63  nop
0x180065f64  mov     rcx, [rsi+0D0h]
0x180065f6b  call    ?Clear@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJXZ; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::Clear(void)
0x180065f70  mov     ebx, eax
0x180065f72  xor     r13d, r13d
0x180065f75  test    eax, eax
0x180065f77  jns     short loc_180065FAE
0x180065f79  mov     rcx, [rbp+5Fh]; this
0x180065f7d  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x180065f84  mov     [rsp+0D0h+var_A8], rax; char *
0x180065f89  lea     rax, aHs; "%hs"
0x180065f90  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x180065f95  mov     r9d, ebx; char *
0x180065f98  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\coresettinghandlers"...
0x180065f9f  mov     edx, 3A3h; void *
0x180065fa4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180065fa9  jmp     loc_180066100
0x180065fae  call    ?GetInstance@RecommendationSingleton@StorageSenseHandlers@SystemSettings@@SAPEAV123@XZ; SystemSettings::StorageSenseHandlers::RecommendationSingleton::GetInstance(void)
0x180065fb3  mov     edx, 2
0x180065fb8  mov     rcx, rax
0x180065fbb  call    ?GetRecommender@RecommendationSingleton@StorageSenseHandlers@SystemSettings@@QEAAPEAVCleanupRecommender@23@W4RecommenderKind@RecommenderEngineUtils@23@@Z; SystemSettings::StorageSenseHandlers::RecommendationSingleton::GetRecommender(SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind)
0x180065fc0  lea     rdx, [rbp+57h+var_88]
0x180065fc4  mov     rcx, rax
0x180065fc7  call    ?GetStorageSenseTemporaryFilesCleanupWrapper@TemporaryFilesCleanupRecommender@StorageSenseHandlers@SystemSettings@@QEAA?AV?$shared_ptr@VStorageSenseTemporaryFilesCleanupWrapper@StorageSenseHandlers@SystemSettings@@@std@@XZ; SystemSettings::StorageSenseHandlers::TemporaryFilesCleanupRecommender::GetStorageSenseTemporaryFilesCleanupWrapper(void)
0x180065fcc  nop
0x180065fcd  mov     rcx, [rbp+57h+var_88]
0x180065fd1  test    rcx, rcx
0x180065fd4  jnz     short loc_180066023
0x180065fd6  mov     rcx, [rbp+5Fh]; this
0x180065fda  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x180065fe1  mov     [rsp+0D0h+var_A8], rax; char *
0x180065fe6  lea     rax, aHs; "%hs"
0x180065fed  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x180065ff2  mov     r15d, 8007000Eh
0x180065ff8  mov     r9d, r15d; char *
0x180065ffb  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\coresettinghandlers"...
0x180066002  mov     edx, 3A8h; void *
0x180066007  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006600c  nop
0x18006600d  mov     rcx, [rbp+57h+var_80]; this
0x180066011  test    rcx, rcx
0x180066014  jz      short loc_18006601B
0x180066016  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006601b  mov     ebx, r15d
0x18006601e  jmp     loc_180066100
0x180066023  xorps   xmm0, xmm0
0x180066026  movdqu  [rbp+57h+var_58], xmm0
0x18006602b  mov     [rbp+57h+var_48], r13
0x18006602f  lea     rdx, [rbp+57h+var_58]
0x180066033  call    ?GetUserSelectableCleanupPlugins@StorageSenseTemporaryFilesCleanupWrapper@StorageSenseHandlers@SystemSettings@@QEAAJAEAV?$vector@V?$ComPtr@VCStorageCleanupItem@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCStorageCleanupItem@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@@std@@@std@@@Z; SystemSettings::StorageSenseHandlers::StorageSenseTemporaryFilesCleanupWrapper::GetUserSelectableCleanupPlugins(std::vector<Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CStorageCleanupItem>> &)
0x180066038  mov     ebx, eax
0x18006603a  cmp     eax, 8000000Ah
0x18006603f  jnz     short loc_180066086
0x180066041  mov     rcx, qword ptr [rbp+57h+var_58]
0x180066045  test    rcx, rcx
0x180066048  jz      short loc_180066073
0x18006604a  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18006604e  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@UISettingItem@DataModel@SystemSettings@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@UISettingItem@DataModel@SystemSettings@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@UISettingItem@DataModel@SystemSettings@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem>>>(Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem> *,Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem> * const,std::allocator<Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem>> &)
0x180066053  mov     rcx, qword ptr [rbp+57h+var_58]
0x180066057  mov     rdx, [rbp+57h+var_48]
0x18006605b  sub     rdx, rcx
0x18006605e  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180066062  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180066067  xorps   xmm0, xmm0
0x18006606a  movdqu  [rbp+57h+var_58], xmm0
0x18006606f  mov     [rbp+57h+var_48], r13
0x180066073  mov     rcx, [rbp+57h+var_80]; this
0x180066077  test    rcx, rcx
0x18006607a  jz      short loc_180066081
0x18006607c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180066081  mov     ebx, r13d
0x180066084  jmp     short loc_180066100
0x180066086  test    ebx, ebx
0x180066088  jns     loc_180066110
0x18006608e  mov     rcx, [rbp+5Fh]; this
0x180066092  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x180066099  mov     [rsp+0D0h+var_A8], rax; char *
0x18006609e  lea     rax, aHs; "%hs"
0x1800660a5  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x1800660aa  mov     r9d, ebx; char *
0x1800660ad  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\coresettinghandlers"...
0x1800660b4  mov     edx, 3B2h; void *
0x1800660b9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800660be  nop
0x1800660bf  mov     rcx, qword ptr [rbp+57h+var_58]
0x1800660c3  test    rcx, rcx
0x1800660c6  jz      short loc_1800660F1
0x1800660c8  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x1800660cc  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@UISettingItem@DataModel@SystemSettings@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@UISettingItem@DataModel@SystemSettings@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@UISettingItem@DataModel@SystemSettings@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem>>>(Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem> *,Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem> * const,std::allocator<Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem>> &)
0x1800660d1  mov     rcx, qword ptr [rbp+57h+var_58]
0x1800660d5  mov     rdx, [rbp+57h+var_48]
0x1800660d9  sub     rdx, rcx
0x1800660dc  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800660e0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800660e5  xorps   xmm0, xmm0
0x1800660e8  movdqu  [rbp+57h+var_58], xmm0
0x1800660ed  mov     [rbp+57h+var_48], r13
0x1800660f1  mov     rcx, [rbp+57h+var_80]; this
0x1800660f5  test    rcx, rcx
0x1800660f8  jz      short loc_180066100
0x1800660fa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800660ff  nop
0x180066100  mov     rcx, rdi; _Mtx_t
0x180066103  call    cs:__imp__Mtx_unlock
0x180066109  mov     eax, ebx
0x18006610b  jmp     loc_18006633C
0x180066110  mov     r14, qword ptr [rbp+57h+var_58]
0x180066114  mov     r12, qword ptr [rbp+57h+var_58+8]
0x180066118  cmp     r14, r12
0x18006611b  jz      loc_1800662AF
0x180066121  mov     [rbp+57h+var_A0], rsi
0x180066125  mov     [rbp+57h+arg_0], r13
0x180066129  mov     rax, [rsi]
0x18006612c  mov     rcx, rsi
0x18006612f  mov     rax, [rax+8]
0x180066133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066138  nop
0x180066139  lea     rax, [rbp+57h+arg_0]
0x18006613d  mov     [rbp+57h+arg_10], rax
0x180066141  lea     rcx, [rbp+57h+arg_10]
0x180066145  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18006614a  mov     rdx, rax
0x18006614d  mov     rcx, rsi
0x180066150  call    ??$AsWeak@VFileRecommendationListBase@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@YAJPEAVFileRecommendationListBase@StorageSenseHandlers@SystemSettings@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<SystemSettings::StorageSenseHandlers::FileRecommendationListBase>(SystemSettings::StorageSenseHandlers::FileRecommendationListBase *,Microsoft::WRL::WeakRef *)
0x180066155  nop
0x180066156  lea     r8, [rbp+57h+arg_0]
0x18006615a  mov     rdx, r14
0x18006615d  lea     rcx, [rbp+57h+arg_8]
0x180066161  call    ??$Make@VTemporaryFilesCleanupRecommendationSetting@StorageSenseHandlers@SystemSettings@@AEAV?$ComPtr@VCStorageCleanupItem@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@AEAVWeakRef@56@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VTemporaryFilesCleanupRecommendationSetting@StorageSenseHandlers@SystemSettings@@@12@AEAV?$ComPtr@VCStorageCleanupItem@StorageSenseHandlers@SystemSettings@@@12@AEAVWeakRef@12@@Z; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::TemporaryFilesCleanupRecommendationSetting,Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CStorageCleanupItem> &,Microsoft::WRL::WeakRef &>(Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CStorageCleanupItem> &,Microsoft::WRL::WeakRef &)
0x180066166  mov     rbx, r13
0x180066169  lea     rcx, [rbp+57h+var_98]
0x18006616d  cmp     rcx, rax
0x180066170  jz      short loc_180066178
0x180066172  mov     rbx, [rax]
0x180066175  mov     [rax], r13
0x180066178  mov     [rbp+57h+var_90], rbx
0x18006617c  mov     rcx, [rbp+57h+arg_8]
0x180066180  test    rcx, rcx
0x180066183  jz      short loc_180066196
0x180066185  mov     [rbp+57h+arg_8], r13
0x180066189  mov     rax, [rcx]
0x18006618c  mov     rax, [rax+10h]
0x180066190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066195  nop
0x180066196  test    rbx, rbx
0x180066199  jz      loc_180066404
0x18006619f  mov     rcx, [r14]; this
0x1800661a2  call    ?GetIsSelected@CStorageCleanupItem@StorageSenseHandlers@SystemSettings@@QEAA_NXZ; SystemSettings::StorageSenseHandlers::CStorageCleanupItem::GetIsSelected(void)
0x1800661a7  mov     r15b, al
0x1800661aa  lea     rcx, [rbx+0D0h]
0x1800661b1  cmp     al, [rcx+10h]
0x1800661b4  jz      short loc_1800661C5
0x1800661b6  mov     [rcx+10h], al
0x1800661b9  mov     rdx, [rcx]
0x1800661bc  mov     rax, [rdx+8]
0x1800661c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800661c5  test    r15b, r15b
0x1800661c8  jz      short loc_18006623A
0x1800661ca  lea     rcx, [rbp+57h+var_78]
0x1800661ce  call    ??$make_shared@UTemporaryFilesCleanupSelectionChangedNotification@StorageSenseHandlers@SystemSettings@@$$V@std@@YA?AV?$shared_ptr@UTemporaryFilesCleanupSelectionChangedNotification@StorageSenseHandlers@SystemSettings@@@0@XZ; std::make_shared<SystemSettings::StorageSenseHandlers::TemporaryFilesCleanupSelectionChangedNotification,>(void)
0x1800661d3  nop
0x1800661d4  mov     rdx, [rbp+57h+var_78]
0x1800661d8  mov     byte ptr [rdx+8], 1
0x1800661dc  mov     rax, [rbx+108h]
0x1800661e3  mov     rcx, [rax+110h]
0x1800661ea  mov     [rdx+10h], rcx
0x1800661ee  mov     byte ptr [rdx+18h], 1
0x1800661f2  call    ?GetInstance@RecommendationSingleton@StorageSenseHandlers@SystemSettings@@SAPEAV123@XZ; SystemSettings::StorageSenseHandlers::RecommendationSingleton::GetInstance(void)
0x1800661f7  mov     r8, rax
0x1800661fa  lea     rdx, [rbp+57h+var_78]
0x1800661fe  lea     rcx, [rbp+57h+var_68]
0x180066202  call    ??$?0UCleanupListOperationProgress@StorageSenseHandlers@SystemSettings@@$0A@@?$shared_ptr@UCleanupListHandlerEvent@StorageSenseHandlers@SystemSettings@@@std@@QEAA@AEBV?$shared_ptr@UCleanupListOperationProgress@StorageSenseHandlers@SystemSettings@@@1@@Z; std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>(std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListOperationProgress> const &)
0x180066207  nop
0x180066208  lea     rax, [rbp+57h+var_68]
0x18006620c  mov     [rbp+57h+arg_10], rax
0x180066210  lea     rdx, [rbp+57h+arg_10]
0x180066214  mov     rcx, r8
0x180066217  call    ??$_Notify@V_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_@@@?$CSingletonHelper@AEBV?$shared_ptr@UCleanupListHandlerEvent@StorageSenseHandlers@SystemSettings@@@std@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_@@@Z; SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_ const &)
0x18006621c  nop
0x18006621d  mov     rcx, [rbp+57h+var_60]; this
0x180066221  test    rcx, rcx
0x180066224  jz      short loc_18006622C
0x180066226  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006622b  nop
0x18006622c  mov     rcx, [rbp+57h+var_70]; this
0x180066230  test    rcx, rcx
0x180066233  jz      short loc_18006623A
0x180066235  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006623a  mov     r9b, 1
0x18006623d  mov     r8, rbx
0x180066240  xor     edx, edx
0x180066242  mov     rcx, [rsi+0D0h]
0x180066249  call    ?InsertAtInternal@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUISettingItem@DataModel@SystemSettings@@_N@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(uint,SystemSettings::DataModel::ISettingItem *,bool)
0x18006624e  mov     r15d, eax
0x180066251  test    eax, eax
0x180066253  js      loc_180066350
0x180066259  mov     [rbx+68h], rsi
0x18006625d  mov     rax, [rbx]
0x180066260  mov     rcx, rbx
0x180066263  mov     rax, [rax+10h]
0x180066267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006626c  nop
0x18006626d  mov     rax, [rsi]
0x180066270  mov     rcx, rsi
0x180066273  mov     rax, [rax+10h]
0x180066277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006627c  nop
0x18006627d  mov     rcx, [rbp+57h+arg_0]
0x180066281  test    rcx, rcx
0x180066284  jz      short loc_180066297
0x180066286  mov     [rbp+57h+arg_0], r13
0x18006628a  mov     rax, [rcx]
0x18006628d  mov     rax, [rax+10h]
0x180066291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066296  nop
0x180066297  add     r14, 8
0x18006629b  cmp     r14, r12
0x18006629e  jnz     loc_180066125
0x1800662a4  mov     r12, qword ptr [rbp+57h+var_58+8]
0x1800662a8  mov     r14, qword ptr [rbp+57h+var_58]
0x1800662ac  cmp     r14, r12
0x1800662af  setnz   al
0x1800662b2  mov     [rsi+0F8h], al
0x1800662b8  mov     byte ptr [rsi+0F9h], 1
0x1800662bf  lea     rdx, stru_18010F168; unsigned __int16 *
0x1800662c6  mov     rcx, rsi; this
0x1800662c9  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x1800662ce  lea     rdx, stru_18010F140; unsigned __int16 *
0x1800662d5  mov     rcx, rsi; this
0x1800662d8  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x1800662dd  lea     rdx, stru_18010F210; unsigned __int16 *
0x1800662e4  mov     rcx, rsi; this
0x1800662e7  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x1800662ec  nop
0x1800662ed  mov     rcx, qword ptr [rbp+57h+var_58]
0x1800662f1  test    rcx, rcx
0x1800662f4  jz      short loc_18006631F
0x1800662f6  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x1800662fa  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@UISettingItem@DataModel@SystemSettings@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@UISettingItem@DataModel@SystemSettings@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@UISettingItem@DataModel@SystemSettings@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem>>>(Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem> *,Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem> * const,std::allocator<Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem>> &)
0x1800662ff  mov     rcx, qword ptr [rbp+57h+var_58]
0x180066303  mov     rdx, [rbp+57h+var_48]
0x180066307  sub     rdx, rcx
0x18006630a  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18006630e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180066313  xorps   xmm0, xmm0
0x180066316  movdqu  [rbp+57h+var_58], xmm0
0x18006631b  mov     [rbp+57h+var_48], r13
0x18006631f  mov     rcx, [rbp+57h+var_80]; this
0x180066323  test    rcx, rcx
0x180066326  jz      short loc_18006632D
0x180066328  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006632d  mov     r15d, r13d
0x180066330  mov     rcx, rdi; _Mtx_t
0x180066333  call    cs:__imp__Mtx_unlock
0x180066339  mov     eax, r15d
0x18006633c  add     rsp, 98h
0x180066343  pop     r15
0x180066345  pop     r14
0x180066347  pop     r13
0x180066349  pop     r12
0x18006634b  pop     rdi
0x18006634c  pop     rsi
0x18006634d  pop     rbx
0x18006634e  pop     rbp
0x18006634f  retn
0x180066350  mov     rcx, [rbp+5Fh]; this
0x180066354  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x18006635b  mov     [rsp+0D0h+var_A8], rax; char *
0x180066360  lea     rax, aHs; "%hs"
0x180066367  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18006636c  mov     r9d, r15d; char *
0x18006636f  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\coresettinghandlers"...
0x180066376  mov     edx, 3D1h; void *
0x18006637b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180066380  nop
0x180066381  mov     rax, [rbx]
0x180066384  mov     rcx, rbx
0x180066387  mov     rax, [rax+10h]
0x18006638b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066390  nop
0x180066391  mov     rax, [rsi]
0x180066394  mov     rcx, rsi
0x180066397  mov     rax, [rax+10h]
0x18006639b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800663a0  nop
  ... truncated ...
```
