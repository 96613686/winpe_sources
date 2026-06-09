# SystemSettings::StorageSenseHandlers::FileRemovalSetting::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x1800645a0`
- end: `0x180064a30`
- name: `?GetProperty@FileRemovalSetting@StorageSenseHandlers@SystemSettings@@MEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `1168`
- prototype: `int(SystemSettings::StorageSenseHandlers::FileRemovalSetting *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006e50`
- `0x18000733c`
- `0x18000c964`
- `0x180010ecc`
- `0x180012374`
- `0x180012f88`
- `0x180016cbc`
- `0x180019eb4`
- `0x18001f230`
- `0x18001f4d0`
- `0x18001f688`
- `0x180023928`
- `0x1800286c0`
- `0x18002adf4`
- `0x18002e5a0`
- `0x180034cd8`
- `0x18003c2c0`
- `0x18005d8d8`
- `0x18005dfb4`
- `0x18005e060`
- `0x1800630a8`
- `0x1800645a0`
- `0x180074b70`
- `0x180076958`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x180064787`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x180064787`

## string_xrefs

- `0x18006468f`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommendationlist.cpp`
- `0x1800647b2`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommendationlist.cpp`
- `0x180064920`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommendationlist.cpp`
- `0x18006497e`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommendationlist.cpp`
- `0x1800649ba`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommendationlist.cpp`
- `0x18006467c`: `CleanupRecommendations`
- `0x180064797`: `CleanupRecommendations`
- `0x18006496b`: `CleanupRecommendations`
- `0x18006499c`: `CleanupRecommendations`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HRESULT __fastcall SystemSettings::StorageSenseHandlers::FileRemovalSetting::GetProperty(
        SystemSettings::StorageSenseHandlers::FileRemovalSetting *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  const unsigned __int16 *v6; // r8
  struct SystemSettings::StorageSenseHandlers::RecommendationSingleton *Instance; // rax
  unsigned __int8 IsSectionExpandedByDefault; // cl
  const unsigned __int16 *v10; // r8
  char *v11; // rdi
  __int64 (__fastcall ***v12)(_QWORD, GUID *, struct IInspectable **); // rcx
  __int64 v13; // rax
  void *v14; // rcx
  __int64 v15; // rdx
  const unsigned __int16 *v16; // r8
  char *v17; // rdi
  __int64 v18; // rax
  void *v19; // rcx
  const unsigned __int16 *v20; // r8
  HRESULT v21; // ebx
  const unsigned __int16 *v22; // r8
  const unsigned __int16 *v23; // r8
  const unsigned __int16 *v24; // r8
  void *v25; // rax
  __int64 v26; // r15
  int v27; // edi
  __int64 v28; // rdx
  __int64 v29; // rdi
  __int64 v30; // r15
  __int64 v31; // r9
  int v32; // eax
  int v33; // [rsp+20h] [rbp-39h]
  void *v34; // [rsp+30h] [rbp-29h] BYREF
  __int64 v35; // [rsp+38h] [rbp-21h] BYREF
  WCHAR pszBuf[16]; // [rsp+40h] [rbp-19h] BYREF
  int v37[8]; // [rsp+60h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010EF30, (const unsigned __int16 *)a3) )
  {
    Instance = SystemSettings::StorageSenseHandlers::RecommendationSingleton::GetInstance();
    IsSectionExpandedByDefault = SystemSettings::StorageSenseHandlers::RecommendationSingleton::IsSectionExpandedByDefault(
                                   Instance,
                                   *((unsigned int *)this + 76));
    return SystemSettings::DataModel::PropValueHelper::CreateBoolean(IsSectionExpandedByDefault, a3);
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010EF10, v6) )
  {
    v11 = (char *)this + 312;
    v12 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IInspectable **))*((_QWORD *)this + 39);
    if ( !v12 )
    {
      LODWORD(v35) = 1;
      v13 = Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::FileRecommendationListBase,enum SystemSettings::StorageSenseHandlers::FileRemoveRecommendationKind,enum SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind &>(
              &v34,
              &v35,
              (char *)this + 304);
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::operator=(
        (char *)this + 312,
        v13);
      v14 = v34;
      if ( v34 )
      {
        v34 = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 16LL))(v14);
      }
      v12 = *(__int64 (__fastcall ****)(_QWORD, GUID *, struct IInspectable **))v11;
      if ( !*(_QWORD *)v11 )
      {
        v15 = 631;
LABEL_10:
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)v15,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
          (const char *)0x8007000ELL,
          (int)"%hs",
          "CleanupRecommendations");
        return -2147024882;
      }
    }
    return (**v12)(v12, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, a3);
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010EF80, v10) )
  {
    v17 = (char *)this + 320;
    v12 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IInspectable **))*((_QWORD *)this + 40);
    if ( !v12 )
    {
      LODWORD(v35) = 0;
      v18 = Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::FileRecommendationListBase,enum SystemSettings::StorageSenseHandlers::FileRemoveRecommendationKind,enum SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind &>(
              &v34,
              &v35,
              (char *)this + 304);
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::operator=(
        (char *)this + 320,
        v18);
      v19 = v34;
      if ( v34 )
      {
        v34 = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v19 + 16LL))(v19);
      }
      v12 = *(__int64 (__fastcall ****)(_QWORD, GUID *, struct IInspectable **))v17;
      if ( !*(_QWORD *)v17 )
      {
        v15 = 641;
        goto LABEL_10;
      }
    }
    return (**v12)(v12, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, a3);
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010EF58, v16) )
  {
    v21 = StrFormatByteSizeEx(*((_QWORD *)this + 36), 2, pszBuf, 0x20u);
    if ( v21 >= 0 )
    {
      return SystemSettings::DataModel::PropValueHelper::CreateString(pszBuf, a3);
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x28A,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
        (const char *)(unsigned int)v21,
        (int)"%hs",
        "CleanupRecommendations");
      return v21;
    }
  }
  else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010EFC8, v20) )
  {
    return SystemSettings::DataModel::PropValueHelper::CreateUInt64(*((_QWORD *)this + 37), a3);
  }
  else
  {
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010EFA0, v22) )
    {
      IsSectionExpandedByDefault = *((_BYTE *)this + 282);
      return SystemSettings::DataModel::PropValueHelper::CreateBoolean(IsSectionExpandedByDefault, a3);
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010F018, v23) )
    {
      IsSectionExpandedByDefault = *((_BYTE *)this + 283);
      return SystemSettings::DataModel::PropValueHelper::CreateBoolean(IsSectionExpandedByDefault, a3);
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010EFF0, v24) )
    {
      v35 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v35);
      v35 = 0;
      v25 = operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
      v34 = v25;
      v26 = 0;
      if ( v25 )
      {
        v26 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>(v25);
        v34 = 0;
      }
      Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_1dabfb557c6ca53c8eb192beb0706936_ &>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_1dabfb557c6ca53c8eb192beb0706936_ &>>(&v34);
      if ( v26 )
      {
        v27 = 0;
        v35 = v26;
      }
      else
      {
        v27 = -2147024882;
      }
      if ( v27 >= 0 )
      {
        v29 = *((_QWORD *)this + 41);
        v30 = *((_QWORD *)this + 42);
        while ( v29 != v30 )
        {
          std::wstring::wstring(pszBuf, v29);
          v37[0] = *(_DWORD *)(v29 + 32);
          Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::FileRecommendationSetting,std::wstring &,unsigned long &>(
            &v34,
            pszBuf,
            v37);
          if ( !v34 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x2A3,
              (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
              (const char *)0x8007000ELL,
              (int)"%hs",
              "CleanupRecommendations");
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v34);
            std::wstring::_Tidy_deallocate(pszBuf);
            v27 = -2147024882;
            goto LABEL_48;
          }
          LOBYTE(v31) = 1;
          v32 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(
                  v35,
                  0,
                  v34,
                  v31);
          if ( v32 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x2A4,
              (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
              (const char *)(unsigned int)v32,
              v33);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v34);
          std::wstring::_Tidy_deallocate(pszBuf);
          v29 += 40;
        }
        v27 = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IIterable<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>>(
                v35,
                &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                a3);
        if ( v27 < 0 )
        {
          v28 = 679;
          goto LABEL_45;
        }
        CleanupRecommendationsLogger::CleanupErrorsVisualized<enum SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind &>((char *)this + 304);
        *((_BYTE *)this + 216) = 1;
        v27 = 0;
      }
      else
      {
        v28 = 669;
LABEL_45:
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)v28,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
          (const char *)(unsigned int)v27,
          (int)"%hs",
          "CleanupRecommendations");
      }
LABEL_48:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v35);
      return v27;
    }
    else
    {
      return SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetProperty(
               this,
               a2,
               a3);
    }
  }
}

```

## disassembly

```asm
0x1800645a0  push    rbp
0x1800645a2  push    rbx
0x1800645a3  push    rdi
0x1800645a4  push    r14
0x1800645a6  push    r15
0x1800645a8  lea     rbp, [rsp-37h]
0x1800645ad  sub     rsp, 90h
0x1800645b4  mov     rax, cs:__security_cookie
0x1800645bb  xor     rax, rsp
0x1800645be  mov     [rbp+57h+var_30], rax
0x1800645c2  mov     r14, r8
0x1800645c5  mov     rdi, rdx
0x1800645c8  mov     rbx, rcx
0x1800645cb  lea     rdx, stru_18010EF30; HSTRING
0x1800645d2  mov     rcx, rdi; this
0x1800645d5  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800645da  test    al, al
0x1800645dc  jz      short loc_180064600
0x1800645de  call    ?GetInstance@RecommendationSingleton@StorageSenseHandlers@SystemSettings@@SAPEAV123@XZ; SystemSettings::StorageSenseHandlers::RecommendationSingleton::GetInstance(void)
0x1800645e3  mov     edx, [rbx+130h]
0x1800645e9  mov     rcx, rax
0x1800645ec  call    ?IsSectionExpandedByDefault@RecommendationSingleton@StorageSenseHandlers@SystemSettings@@QEBA_NW4RecommenderKind@RecommenderEngineUtils@23@@Z; SystemSettings::StorageSenseHandlers::RecommendationSingleton::IsSectionExpandedByDefault(SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind)
0x1800645f1  mov     cl, al; unsigned __int8
0x1800645f3  mov     rdx, r14; struct IInspectable **
0x1800645f6  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x1800645fb  jmp     loc_180064A15
0x180064600  lea     rdx, stru_18010EF10; HSTRING
0x180064607  mov     rcx, rdi; this
0x18006460a  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18006460f  test    al, al
0x180064611  jz      loc_1800646CF
0x180064617  lea     rdi, [rbx+138h]
0x18006461e  mov     rcx, [rdi]
0x180064621  test    rcx, rcx
0x180064624  jnz     loc_1800646B4
0x18006462a  mov     dword ptr [rbp+57h+var_78], 1
0x180064631  lea     r8, [rbx+130h]
0x180064638  lea     rdx, [rbp+57h+var_78]
0x18006463c  lea     rcx, [rbp+57h+var_80]
0x180064640  call    ??$Make@VFileRecommendationListBase@StorageSenseHandlers@SystemSettings@@W4FileRemoveRecommendationKind@23@AEAW4RecommenderKind@RecommenderEngineUtils@23@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VFileRecommendationListBase@StorageSenseHandlers@SystemSettings@@@12@$$QEAW4FileRemoveRecommendationKind@StorageSenseHandlers@SystemSettings@@AEAW4RecommenderKind@RecommenderEngineUtils@56@@Z; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::FileRecommendationListBase,SystemSettings::StorageSenseHandlers::FileRemoveRecommendationKind,SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind &>(SystemSettings::StorageSenseHandlers::FileRemoveRecommendationKind &&,SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind &)
0x180064645  mov     rdx, rax
0x180064648  mov     rcx, rdi
0x18006464b  call    ??4?$ComPtr@U?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::operator=(Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>> &&)
0x180064650  nop
0x180064651  mov     rcx, [rbp+57h+var_80]
0x180064655  test    rcx, rcx
0x180064658  jz      short loc_18006466F
0x18006465a  mov     [rbp+57h+var_80], 0
0x180064662  mov     rax, [rcx]
0x180064665  mov     rax, [rax+10h]
0x180064669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006466e  nop
0x18006466f  mov     rcx, [rdi]
0x180064672  test    rcx, rcx
0x180064675  jnz     short loc_1800646B4
0x180064677  mov     edx, 277h; void *
0x18006467c  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x180064683  mov     [rsp+0B0h+var_88], rax; char *
0x180064688  lea     rax, aHs; "%hs"
0x18006468f  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\coresettinghandlers"...
0x180064696  mov     r9d, 8007000Eh; char *
0x18006469c  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x1800646a1  mov     rcx, [rbp+5Fh]; this
0x1800646a5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800646aa  mov     eax, 8007000Eh
0x1800646af  jmp     loc_180064A15
0x1800646b4  mov     rax, [rcx]
0x1800646b7  mov     r8, r14
0x1800646ba  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x1800646c1  mov     rax, [rax]
0x1800646c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800646c9  nop
0x1800646ca  jmp     loc_180064A15
0x1800646cf  lea     rdx, stru_18010EF80; HSTRING
0x1800646d6  mov     rcx, rdi; this
0x1800646d9  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800646de  test    al, al
0x1800646e0  jz      short loc_18006475F
0x1800646e2  lea     rdi, [rbx+140h]
0x1800646e9  mov     rcx, [rdi]
0x1800646ec  test    rcx, rcx
0x1800646ef  jnz     short loc_180064744
0x1800646f1  mov     dword ptr [rbp+57h+var_78], ecx
0x1800646f4  lea     r8, [rbx+130h]
0x1800646fb  lea     rdx, [rbp+57h+var_78]
0x1800646ff  lea     rcx, [rbp+57h+var_80]
0x180064703  call    ??$Make@VFileRecommendationListBase@StorageSenseHandlers@SystemSettings@@W4FileRemoveRecommendationKind@23@AEAW4RecommenderKind@RecommenderEngineUtils@23@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VFileRecommendationListBase@StorageSenseHandlers@SystemSettings@@@12@$$QEAW4FileRemoveRecommendationKind@StorageSenseHandlers@SystemSettings@@AEAW4RecommenderKind@RecommenderEngineUtils@56@@Z; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::FileRecommendationListBase,SystemSettings::StorageSenseHandlers::FileRemoveRecommendationKind,SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind &>(SystemSettings::StorageSenseHandlers::FileRemoveRecommendationKind &&,SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind &)
0x180064708  mov     rdx, rax
0x18006470b  mov     rcx, rdi
0x18006470e  call    ??4?$ComPtr@U?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::operator=(Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>> &&)
0x180064713  nop
0x180064714  mov     rcx, [rbp+57h+var_80]
0x180064718  test    rcx, rcx
0x18006471b  jz      short loc_180064732
0x18006471d  mov     [rbp+57h+var_80], 0
0x180064725  mov     rax, [rcx]
0x180064728  mov     rax, [rax+10h]
0x18006472c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064731  nop
0x180064732  mov     rcx, [rdi]
0x180064735  test    rcx, rcx
0x180064738  jnz     short loc_180064744
0x18006473a  mov     edx, 281h
0x18006473f  jmp     loc_18006467C
0x180064744  mov     rax, [rcx]
0x180064747  mov     r8, r14
0x18006474a  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x180064751  mov     rax, [rax]
0x180064754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064759  nop
0x18006475a  jmp     loc_180064A15
0x18006475f  lea     rdx, stru_18010EF58; HSTRING
0x180064766  mov     rcx, rdi; this
0x180064769  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18006476e  test    al, al
0x180064770  jz      short loc_1800647DB
0x180064772  mov     r9d, 20h ; ' '; cchBuf
0x180064778  lea     r8, [rbp+57h+pszBuf]; pszBuf
0x18006477c  lea     edx, [r9-1Eh]; flags
0x180064780  mov     rcx, [rbx+120h]; ull
0x180064787  call    cs:__imp_StrFormatByteSizeEx
0x18006478d  mov     ebx, eax
0x18006478f  test    eax, eax
0x180064791  jns     short loc_1800647CA
0x180064793  mov     rcx, [rbp+5Fh]; this
0x180064797  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x18006479e  mov     [rsp+0B0h+var_88], rax; char *
0x1800647a3  lea     rax, aHs; "%hs"
0x1800647aa  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x1800647af  mov     r9d, ebx; char *
0x1800647b2  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\coresettinghandlers"...
0x1800647b9  mov     edx, 28Ah; void *
0x1800647be  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800647c3  mov     eax, ebx
0x1800647c5  jmp     loc_180064A15
0x1800647ca  mov     rdx, r14; struct IInspectable **
0x1800647cd  lea     rcx, [rbp+57h+pszBuf]; unsigned __int16 *
0x1800647d1  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1800647d6  jmp     loc_180064A15
0x1800647db  lea     rdx, stru_18010EFC8; HSTRING
0x1800647e2  mov     rcx, rdi; this
0x1800647e5  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800647ea  test    al, al
0x1800647ec  jz      short loc_180064802
0x1800647ee  mov     rdx, r14; struct IInspectable **
0x1800647f1  mov     rcx, [rbx+128h]; unsigned __int64
0x1800647f8  call    ?CreateUInt64@PropValueHelper@DataModel@SystemSettings@@SAJ_KPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateUInt64(unsigned __int64,IInspectable * *)
0x1800647fd  jmp     loc_180064A15
0x180064802  lea     rdx, stru_18010EFA0; HSTRING
0x180064809  mov     rcx, rdi; this
0x18006480c  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180064811  test    al, al
0x180064813  jz      short loc_180064820
0x180064815  mov     cl, [rbx+11Ah]
0x18006481b  jmp     loc_1800645F3
0x180064820  lea     rdx, stru_18010F018; HSTRING
0x180064827  mov     rcx, rdi; this
0x18006482a  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18006482f  test    al, al
0x180064831  jz      short loc_18006483E
0x180064833  mov     cl, [rbx+11Bh]
0x180064839  jmp     loc_1800645F3
0x18006483e  lea     rdx, stru_18010EFF0; HSTRING
0x180064845  mov     rcx, rdi; this
0x180064848  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18006484d  test    al, al
0x18006484f  jz      loc_180064A07
0x180064855  mov     [rbp+57h+var_78], 0
0x18006485d  lea     rcx, [rbp+57h+var_78]
0x180064861  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x180064866  mov     [rbp+57h+var_78], 0
0x18006486e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180064875  mov     ecx, 0B8h; unsigned __int64
0x18006487a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006487f  mov     [rbp+57h+var_80], rax
0x180064883  xor     r15d, r15d
0x180064886  test    rax, rax
0x180064889  jz      short loc_18006489E
0x18006488b  mov     rcx, rax
0x18006488e  call    ??0?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@QEAA@AEBU?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@1234@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>(Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *> const &,Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::permission)
0x180064893  mov     r15, rax
0x180064896  mov     [rbp+57h+var_80], 0
0x18006489e  lea     rcx, [rbp+57h+var_80]
0x1800648a2  call    ??1?$MakeAllocator@V?$CTaskWrapper@AEAV_lambda_1dabfb557c6ca53c8eb192beb0706936_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_1dabfb557c6ca53c8eb192beb0706936_ &>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_1dabfb557c6ca53c8eb192beb0706936_ &>>(void)
0x1800648a7  test    r15, r15
0x1800648aa  jnz     short loc_1800648B3
0x1800648ac  mov     edi, 8007000Eh
0x1800648b1  jmp     short loc_1800648B9
0x1800648b3  xor     edi, edi
0x1800648b5  mov     [rbp+57h+var_78], r15
0x1800648b9  test    edi, edi
0x1800648bb  jns     short loc_1800648C7
0x1800648bd  mov     edx, 29Dh
0x1800648c2  jmp     loc_18006496B
0x1800648c7  mov     rdi, [rbx+148h]
0x1800648ce  mov     r15, [rbx+150h]
0x1800648d5  jmp     short loc_180064948
0x1800648d7  mov     rdx, rdi
0x1800648da  lea     rcx, [rbp+57h+pszBuf]
0x1800648de  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800648e3  mov     eax, [rdi+20h]
0x1800648e6  mov     [rbp+57h+var_50], eax
0x1800648e9  lea     r8, [rbp+57h+var_50]
0x1800648ed  lea     rdx, [rbp+57h+pszBuf]
0x1800648f1  lea     rcx, [rbp+57h+var_80]
0x1800648f5  call    ??$Make@VFileRecommendationSetting@StorageSenseHandlers@SystemSettings@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAK@Details@WRL@Microsoft@@YA?AV?$ComPtr@VFileRecommendationSetting@StorageSenseHandlers@SystemSettings@@@12@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAK@Z; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::FileRecommendationSetting,std::wstring &,ulong &>(std::wstring &,ulong &)
0x1800648fa  mov     r8, [rbp+57h+var_80]
0x1800648fe  test    r8, r8
0x180064901  jz      loc_180064998
0x180064907  mov     r9b, 1
0x18006490a  xor     edx, edx
0x18006490c  mov     rcx, [rbp+57h+var_78]
0x180064910  call    ?InsertAtInternal@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUISettingItem@DataModel@SystemSettings@@_N@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(uint,SystemSettings::DataModel::ISettingItem *,bool)
0x180064915  mov     rcx, [rbp+5Fh]; this
0x180064919  test    eax, eax
0x18006491b  jns     short loc_180064931
0x18006491d  mov     r9d, eax; char *
0x180064920  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\coresettinghandlers"...
0x180064927  mov     edx, 2A4h; void *
0x18006492c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180064931  lea     rcx, [rbp+57h+var_80]
0x180064935  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18006493a  nop
0x18006493b  lea     rcx, [rbp+57h+pszBuf]
0x18006493f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180064944  add     rdi, 28h ; '('
0x180064948  cmp     rdi, r15
0x18006494b  jnz     short loc_1800648D7
0x18006494d  mov     r8, r14
0x180064950  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x180064957  mov     rcx, [rbp+57h+var_78]
0x18006495b  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$IIterable@PEAUISettingItem@DataModel@SystemSettings@@@234@U?$IObservableVector@PEAUISettingItem@DataModel@SystemSettings@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$IIterable@PEAUISettingItem@DataModel@SystemSettings@@@234@U?$IObservableVector@PEAUISettingItem@DataModel@SystemSettings@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IIterable<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IIterable<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x180064960  mov     edi, eax
0x180064962  test    eax, eax
0x180064964  jns     short loc_1800649E5
0x180064966  mov     edx, 2A7h; void *
0x18006496b  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x180064972  mov     [rsp+0B0h+var_88], rax; char *
0x180064977  lea     rax, aHs; "%hs"
0x18006497e  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\coresettinghandlers"...
0x180064985  mov     r9d, edi; char *
0x180064988  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x18006498d  mov     rcx, [rbp+5Fh]; this
0x180064991  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180064996  jmp     short loc_1800649FA
0x180064998  mov     rcx, [rbp+5Fh]; this
0x18006499c  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x1800649a3  mov     [rsp+0B0h+var_88], rax; char *
0x1800649a8  lea     rax, aHs; "%hs"
0x1800649af  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x1800649b4  mov     r9d, 8007000Eh; char *
0x1800649ba  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\coresettinghandlers"...
0x1800649c1  mov     edx, 2A3h; void *
0x1800649c6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800649cb  lea     rcx, [rbp+57h+var_80]
0x1800649cf  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800649d4  nop
0x1800649d5  lea     rcx, [rbp+57h+pszBuf]
0x1800649d9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800649de  mov     edi, 8007000Eh
0x1800649e3  jmp     short loc_1800649FA
0x1800649e5  lea     rcx, [rbx+130h]
0x1800649ec  call    ??$CleanupErrorsVisualized@AEAW4RecommenderKind@RecommenderEngineUtils@StorageSenseHandlers@SystemSettings@@@CleanupRecommendationsLogger@@SAXAEAW4RecommenderKind@RecommenderEngineUtils@StorageSenseHandlers@SystemSettings@@@Z; CleanupRecommendationsLogger::CleanupErrorsVisualized<SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind &>(SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind &)
0x1800649f1  mov     byte ptr [rbx+0D8h], 1
0x1800649f8  xor     edi, edi
0x1800649fa  lea     rcx, [rbp+57h+var_78]
0x1800649fe  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x180064a03  mov     eax, edi
0x180064a05  jmp     short loc_180064A15
0x180064a07  mov     r8, r14
0x180064a0a  mov     rdx, rdi
0x180064a0d  mov     rcx, rbx
0x180064a10  call    ?GetProperty@?$CActionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetProperty(HSTRING__ *,IInspectable * *)
0x180064a15  mov     rcx, [rbp+57h+var_30]
0x180064a19  xor     rcx, rsp; StackCookie
0x180064a1c  call    __security_check_cookie
0x180064a21  add     rsp, 90h
0x180064a28  pop     r15
0x180064a2a  pop     r14
0x180064a2c  pop     rdi
0x180064a2d  pop     rbx
0x180064a2e  pop     rbp
0x180064a2f  retn
```
