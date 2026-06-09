# SystemSettings::StorageSenseHandlers::UnusedApplicationsRemovalSetting::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x180064e50`
- end: `0x1800653ec`
- name: `?GetProperty@UnusedApplicationsRemovalSetting@StorageSenseHandlers@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `1436`
- prototype: `int(SystemSettings::StorageSenseHandlers::UnusedApplicationsRemovalSetting *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `28`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180006e50`
- `0x18000733c`
- `0x180007a00`
- `0x18000e6cc`
- `0x180010ecc`
- `0x180012374`
- `0x180012f88`
- `0x180016cbc`
- `0x180019eb4`
- `0x18001dfe8`
- `0x18001f230`
- `0x18001f468`
- `0x18001f4d0`
- `0x18001f688`
- `0x1800286c0`
- `0x18002adf4`
- `0x18002e5a0`
- `0x18003d408`
- `0x18005d944`
- `0x18005d9b0`
- `0x18005e430`
- `0x180061aa8`
- `0x1800630a8`
- `0x180064e50`
- `0x1800655e4`
- `0x180074b70`
- `0x180076958`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065350`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800653ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065350`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800653ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065393`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065393`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x18006500d`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x18006500d`

## string_xrefs

- `0x180064f6f`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommendationlist.cpp`
- `0x18006520e`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommendationlist.cpp`
- `0x1800652c7`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommendationlist.cpp`
- `0x180065379`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommendationlist.cpp`
- `0x180065360`: `SystemSettings_StorageSense_StorageRecommendations_UnusedApplications_InstalledApps`
- `0x180064f50`: `CleanupRecommendations`
- `0x1800651f3`: `CleanupRecommendations`
- `0x1800652ac`: `CleanupRecommendations`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::StorageSenseHandlers::UnusedApplicationsRemovalSetting::GetProperty(
        SystemSettings::StorageSenseHandlers::UnusedApplicationsRemovalSetting *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  const unsigned __int16 *v6; // r8
  struct SystemSettings::StorageSenseHandlers::RecommendationSingleton *Instance; // rax
  unsigned __int8 IsSectionExpandedByDefault; // cl
  const unsigned __int16 *v10; // r8
  __int64 (__fastcall ***v11)(_QWORD, GUID *, struct IInspectable **); // rcx
  char *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rdx
  HSTRING v15; // rcx
  __int64 v16; // rdx
  HRESULT Boolean; // ebx
  const unsigned __int16 *v18; // r8
  __int64 v19; // rcx
  const unsigned __int16 *v20; // r8
  const unsigned __int16 *v21; // r8
  const unsigned __int16 *v22; // r8
  SystemSettings::StorageSenseHandlers::UnusedApplicationsRemovalRecommendationList *v23; // rcx
  bool v24; // r12
  const unsigned __int16 *v25; // r8
  const unsigned __int16 *v26; // r8
  const unsigned __int16 *v27; // r8
  const unsigned __int16 *v28; // r8
  void *v29; // rax
  HSTRING v30; // rdi
  __int64 v31; // r8
  _QWORD *v32; // rdi
  _QWORD *i; // rbx
  __int64 v34; // rsi
  __int64 v35; // r9
  int v36; // r13d
  HSTRING *v37; // r8
  int ResourceStringById; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  int v41; // [rsp+20h] [rbp-A9h]
  HSTRING string; // [rsp+30h] [rbp-99h] BYREF
  unsigned int v43[2]; // [rsp+38h] [rbp-91h] BYREF
  char v44; // [rsp+40h] [rbp-89h] BYREF
  _BYTE v45[32]; // [rsp+48h] [rbp-81h] BYREF
  __int64 v46; // [rsp+68h] [rbp-61h] BYREF
  WCHAR pszBuf[56]; // [rsp+70h] [rbp-59h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010EF30, (const unsigned __int16 *)a3) )
  {
    Instance = SystemSettings::StorageSenseHandlers::RecommendationSingleton::GetInstance();
    IsSectionExpandedByDefault = SystemSettings::StorageSenseHandlers::RecommendationSingleton::IsSectionExpandedByDefault(
                                   Instance,
                                   3);
    return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateBoolean(IsSectionExpandedByDefault, a3);
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010F3D0, v6) )
  {
    v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IInspectable **))*((_QWORD *)this + 35);
    if ( v11 )
      return (unsigned int)(**v11)(v11, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, a3);
    v12 = (char *)Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::UnusedApplicationsRemovalRecommendationList,>(&string);
    v13 = 0;
    if ( &v44 != v12 )
    {
      v13 = *(_QWORD *)v12;
      *(_QWORD *)v12 = 0;
    }
    v14 = *((_QWORD *)this + 35);
    *((_QWORD *)this + 35) = v13;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v15 = string;
    if ( string )
    {
      string = 0;
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IInspectable **))*((_QWORD *)this + 35);
    if ( v11 )
      return (unsigned int)(**v11)(v11, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, a3);
    v16 = 1551;
    goto LABEL_14;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010F3A0, v10) )
  {
    v19 = *((_QWORD *)this + 35);
    if ( v19 )
      return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateUInt64(*(_QWORD *)(v19 + 232), a3);
    v16 = 1558;
LABEL_14:
    Boolean = -2147024882;
LABEL_15:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
      (const char *)(unsigned int)Boolean,
      (int)"%hs",
      "CleanupRecommendations");
    return (unsigned int)Boolean;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010F2A0, v18) )
  {
    memset_0(pszBuf, 0, 0x64u);
    Boolean = StrFormatByteSizeEx(*((_QWORD *)this + 37), 1, pszBuf, 0x32u);
    if ( Boolean >= 0 )
      return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateString(pszBuf, a3);
    v16 = 1569;
    goto LABEL_15;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010F240, v20) )
  {
    Boolean = SystemSettings::DataModel::PropValueHelper::CreateBoolean(*((_BYTE *)this + 288), a3);
    if ( !*((_BYTE *)this + 288) && *((_BYTE *)this + 289) )
    {
      v43[0] = 3;
      CleanupRecommendationsLogger::CleanupExecutionFinished<enum SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind,unsigned __int64 &,unsigned __int64 &>(
        v43,
        (char *)this + 304,
        (char *)this + 312);
      *((_BYTE *)this + 289) = 0;
    }
  }
  else
  {
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010B738, v21) )
    {
      v23 = (SystemSettings::StorageSenseHandlers::UnusedApplicationsRemovalRecommendationList *)*((_QWORD *)this + 35);
      if ( v23 )
      {
        v43[0] = 0;
        Boolean = SystemSettings::StorageSenseHandlers::UnusedApplicationsRemovalRecommendationList::GetSize(v23, v43);
        if ( Boolean >= 0 )
        {
          v24 = *((_BYTE *)this + 320) && v43[0];
          IsSectionExpandedByDefault = v24;
          return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateBoolean(IsSectionExpandedByDefault, a3);
        }
        v16 = 1593;
        goto LABEL_15;
      }
      v16 = 1589;
      goto LABEL_14;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010F438, v22) )
      return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateDouble((double)*((int *)this + 84), a3);
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010F018, v25) )
    {
      IsSectionExpandedByDefault = *((_BYTE *)this + 409);
      return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateBoolean(IsSectionExpandedByDefault, a3);
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010EFA0, v26) )
    {
      IsSectionExpandedByDefault = *((_BYTE *)this + 408);
      return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateBoolean(IsSectionExpandedByDefault, a3);
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010F400, v27) )
    {
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&string);
      string = 0;
      v29 = operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
      *(_QWORD *)v43 = v29;
      v30 = 0;
      if ( v29 )
      {
        v30 = (HSTRING)Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>(v29);
        *(_QWORD *)v43 = 0;
      }
      Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_1dabfb557c6ca53c8eb192beb0706936_ &>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_1dabfb557c6ca53c8eb192beb0706936_ &>>(v43);
      if ( v30 )
      {
        Boolean = 0;
        string = v30;
      }
      else
      {
        Boolean = -2147024882;
      }
      if ( Boolean >= 0 )
      {
        v32 = (_QWORD *)*((_QWORD *)this + 53);
        for ( i = (_QWORD *)*v32; ; i = (_QWORD *)*i )
        {
          if ( i == v32 )
          {
            Boolean = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IIterable<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>>(
                        string,
                        &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                        a3);
            v43[0] = 3;
            CleanupRecommendationsLogger::CleanupErrorsVisualized<enum SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind>(v43);
            *((_BYTE *)this + 216) = 1;
            goto LABEL_63;
          }
          std::wstring::wstring(v45, i + 2, v31);
          v46 = i[6];
          v34 = v46;
          Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v46);
          *(_QWORD *)v43 = v34;
          Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v43);
          LOBYTE(v35) = 1;
          v36 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(
                  string,
                  0,
                  v34,
                  v35);
          if ( v36 < 0 )
            break;
          if ( v34 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
          std::pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::UnusedApplicationItem>>::~pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::UnusedApplicationItem>>(v45);
        }
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x654,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
          (const char *)(unsigned int)v36,
          (int)"%hs",
          "CleanupRecommendations");
        if ( v34 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
        std::pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::UnusedApplicationItem>>::~pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::UnusedApplicationItem>>(v45);
        Boolean = v36;
      }
      else
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x64E,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
          (const char *)(unsigned int)Boolean,
          (int)"%hs",
          "CleanupRecommendations");
      }
LABEL_63:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&string);
    }
    else
    {
      if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010F518, v28) )
        return (unsigned int)SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetProperty(
                               this,
                               a2,
                               a3);
      WindowsDeleteString(0);
      string = 0;
      ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                             (SystemSettings::DataModel *)L"SystemSettings_StorageSense_StorageRecommendations_UnusedAppli"
                                                           "cations_InstalledApps",
                             &string,
                             v37);
      Boolean = ResourceStringById;
      if ( ResourceStringById >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        Boolean = SystemSettings::DataModel::PropValueHelper::CreateString(StringRawBuffer, a3);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x65F,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
          (const char *)(unsigned int)ResourceStringById,
          v41);
      }
      WindowsDeleteString(string);
    }
  }
  return (unsigned int)Boolean;
}

```

## disassembly

```asm
0x180064e50  mov     [rsp-8+arg_18], rbx
0x180064e55  push    rbp
0x180064e56  push    rsi
0x180064e57  push    rdi
0x180064e58  push    r12
0x180064e5a  push    r13
0x180064e5c  push    r14
0x180064e5e  push    r15
0x180064e60  lea     rbp, [rsp-27h]
0x180064e65  sub     rsp, 0F0h
0x180064e6c  mov     rax, cs:__security_cookie
0x180064e73  xor     rax, rsp
0x180064e76  mov     [rbp+57h+var_40], rax
0x180064e7a  mov     r15, r8
0x180064e7d  mov     rbx, rdx
0x180064e80  mov     r14, rcx
0x180064e83  lea     rdx, stru_18010EF30; HSTRING
0x180064e8a  mov     rcx, rbx; this
0x180064e8d  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180064e92  xor     esi, esi
0x180064e94  test    al, al
0x180064e96  jz      short loc_180064EB7
0x180064e98  call    ?GetInstance@RecommendationSingleton@StorageSenseHandlers@SystemSettings@@SAPEAV123@XZ; SystemSettings::StorageSenseHandlers::RecommendationSingleton::GetInstance(void)
0x180064e9d  lea     edx, [rsi+3]
0x180064ea0  mov     rcx, rax
0x180064ea3  call    ?IsSectionExpandedByDefault@RecommendationSingleton@StorageSenseHandlers@SystemSettings@@QEBA_NW4RecommenderKind@RecommenderEngineUtils@23@@Z; SystemSettings::StorageSenseHandlers::RecommendationSingleton::IsSectionExpandedByDefault(SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind)
0x180064ea8  mov     cl, al; unsigned __int8
0x180064eaa  mov     rdx, r15; struct IInspectable **
0x180064ead  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x180064eb2  jmp     loc_1800653C1
0x180064eb7  lea     rdx, stru_18010F3D0; HSTRING
0x180064ebe  mov     rcx, rbx; this
0x180064ec1  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180064ec6  test    al, al
0x180064ec8  jz      loc_180064F9C
0x180064ece  mov     rcx, [r14+118h]
0x180064ed5  test    rcx, rcx
0x180064ed8  jnz     loc_180064F80
0x180064ede  lea     rcx, [rsp+120h+string]
0x180064ee3  call    ??$Make@VUnusedApplicationsRemovalRecommendationList@StorageSenseHandlers@SystemSettings@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VUnusedApplicationsRemovalRecommendationList@StorageSenseHandlers@SystemSettings@@@12@XZ; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::UnusedApplicationsRemovalRecommendationList,>(void)
0x180064ee8  mov     rcx, rsi
0x180064eeb  lea     rdx, [rsp+120h+var_E0]
0x180064ef0  cmp     rdx, rax
0x180064ef3  jz      short loc_180064EFB
0x180064ef5  mov     rcx, [rax]
0x180064ef8  mov     [rax], rsi
0x180064efb  mov     rdx, [r14+118h]
0x180064f02  mov     [r14+118h], rcx
0x180064f09  test    rdx, rdx
0x180064f0c  jz      short loc_180064F1E
0x180064f0e  mov     rax, [rdx]
0x180064f11  mov     rcx, rdx
0x180064f14  mov     rax, [rax+10h]
0x180064f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064f1d  nop
0x180064f1e  mov     rcx, [rsp+120h+string]
0x180064f23  test    rcx, rcx
0x180064f26  jz      short loc_180064F3A
0x180064f28  mov     [rsp+120h+string], rsi
0x180064f2d  mov     rax, [rcx]
0x180064f30  mov     rax, [rax+10h]
0x180064f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064f39  nop
0x180064f3a  mov     rcx, [r14+118h]
0x180064f41  test    rcx, rcx
0x180064f44  jnz     short loc_180064F80
0x180064f46  mov     edx, 60Fh; void *
0x180064f4b  mov     ebx, 8007000Eh
0x180064f50  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x180064f57  mov     [rsp+120h+var_F8], rax; char *
0x180064f5c  lea     rax, aHs; "%hs"
0x180064f63  mov     rcx, [rbp+5Fh]; this
0x180064f67  mov     qword ptr [rsp+120h+var_100], rax; int
0x180064f6c  mov     r9d, ebx; char *
0x180064f6f  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\coresettinghandlers"...
0x180064f76  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180064f7b  jmp     loc_1800653C3
0x180064f80  mov     rax, [rcx]
0x180064f83  mov     r8, r15
0x180064f86  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x180064f8d  mov     rax, [rax]
0x180064f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064f95  mov     ebx, eax
0x180064f97  jmp     loc_1800653C3
0x180064f9c  lea     rdx, stru_18010F3A0; HSTRING
0x180064fa3  mov     rcx, rbx; this
0x180064fa6  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180064fab  test    al, al
0x180064fad  jz      short loc_180064FD6
0x180064faf  mov     rcx, [r14+118h]
0x180064fb6  test    rcx, rcx
0x180064fb9  jnz     short loc_180064FC2
0x180064fbb  mov     edx, 616h
0x180064fc0  jmp     short loc_180064F4B
0x180064fc2  mov     rdx, r15; struct IInspectable **
0x180064fc5  mov     rcx, [rcx+0E8h]; unsigned __int64
0x180064fcc  call    ?CreateUInt64@PropValueHelper@DataModel@SystemSettings@@SAJ_KPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateUInt64(unsigned __int64,IInspectable * *)
0x180064fd1  jmp     loc_1800653C1
0x180064fd6  lea     rdx, stru_18010F2A0; HSTRING
0x180064fdd  mov     rcx, rbx; this
0x180064fe0  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180064fe5  test    al, al
0x180064fe7  jz      short loc_180065034
0x180064fe9  xor     edx, edx; Val
0x180064feb  lea     r8d, [rdx+64h]; Size
0x180064fef  lea     rcx, [rbp+57h+pszBuf]; void *
0x180064ff3  call    memset_0
0x180064ff8  mov     r9d, 32h ; '2'; cchBuf
0x180064ffe  lea     r8, [rbp+57h+pszBuf]; pszBuf
0x180065002  lea     edx, [r9-31h]; flags
0x180065006  mov     rcx, [r14+128h]; ull
0x18006500d  call    cs:__imp_StrFormatByteSizeEx
0x180065013  mov     ebx, eax
0x180065015  test    eax, eax
0x180065017  jns     short loc_180065023
0x180065019  mov     edx, 621h
0x18006501e  jmp     loc_180064F50
0x180065023  mov     rdx, r15; struct IInspectable **
0x180065026  lea     rcx, [rbp+57h+pszBuf]; unsigned __int16 *
0x18006502a  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18006502f  jmp     loc_1800653C1
0x180065034  lea     rdx, stru_18010F240; HSTRING
0x18006503b  mov     rcx, rbx; this
0x18006503e  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180065043  test    al, al
0x180065045  jz      short loc_18006509E
0x180065047  mov     rdx, r15; struct IInspectable **
0x18006504a  mov     cl, [r14+120h]; unsigned __int8
0x180065051  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x180065056  mov     ebx, eax
0x180065058  cmp     [r14+120h], sil
0x18006505f  jnz     loc_1800653C3
0x180065065  cmp     [r14+121h], sil
0x18006506c  jz      loc_1800653C3
0x180065072  mov     [rsp+120h+var_E8], 3
0x18006507a  lea     r8, [r14+138h]
0x180065081  lea     rdx, [r14+130h]
0x180065088  lea     rcx, [rsp+120h+var_E8]
0x18006508d  call    ??$CleanupExecutionFinished@W4RecommenderKind@RecommenderEngineUtils@StorageSenseHandlers@SystemSettings@@AEA_KAEA_K@CleanupRecommendationsLogger@@SAX$$QEAW4RecommenderKind@RecommenderEngineUtils@StorageSenseHandlers@SystemSettings@@AEA_K1@Z; CleanupRecommendationsLogger::CleanupExecutionFinished<SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind,unsigned __int64 &,unsigned __int64 &>(SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind &&,unsigned __int64 &,unsigned __int64 &)
0x180065092  mov     [r14+121h], sil
0x180065099  jmp     loc_1800653C3
0x18006509e  lea     rdx, stru_18010B738; HSTRING
0x1800650a5  mov     rcx, rbx; this
0x1800650a8  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800650ad  test    al, al
0x1800650af  jz      short loc_180065107
0x1800650b1  mov     rcx, [r14+118h]; this
0x1800650b8  test    rcx, rcx
0x1800650bb  jnz     short loc_1800650C7
0x1800650bd  mov     edx, 635h
0x1800650c2  jmp     loc_180064F4B
0x1800650c7  mov     [rsp+120h+var_E8], esi
0x1800650cb  lea     rdx, [rsp+120h+var_E8]; unsigned int *
0x1800650d0  call    ?GetSize@UnusedApplicationsRemovalRecommendationList@StorageSenseHandlers@SystemSettings@@QEAAJPEAI@Z; SystemSettings::StorageSenseHandlers::UnusedApplicationsRemovalRecommendationList::GetSize(uint *)
0x1800650d5  mov     ebx, eax
0x1800650d7  test    eax, eax
0x1800650d9  jns     short loc_1800650E5
0x1800650db  mov     edx, 639h
0x1800650e0  jmp     loc_180064F50
0x1800650e5  cmp     [r14+140h], sil
0x1800650ec  jz      short loc_1800650FC
0x1800650ee  cmp     [rsp+120h+var_E8], esi
0x1800650f2  jbe     short loc_1800650FC
0x1800650f4  mov     r12d, 1
0x1800650fa  jmp     short loc_1800650FF
0x1800650fc  mov     r12b, sil
0x1800650ff  mov     cl, r12b
0x180065102  jmp     loc_180064EAA
0x180065107  lea     rdx, stru_18010F438; HSTRING
0x18006510e  mov     rcx, rbx; this
0x180065111  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180065116  test    al, al
0x180065118  jz      short loc_180065137
0x18006511a  mov     eax, [r14+150h]
0x180065121  nop
0x180065122  xorps   xmm0, xmm0
0x180065125  cvtsi2sd xmm0, rax; double
0x18006512a  mov     rdx, r15; struct IInspectable **
0x18006512d  call    ?CreateDouble@PropValueHelper@DataModel@SystemSettings@@SAJNPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateDouble(double,IInspectable * *)
0x180065132  jmp     loc_1800653C1
0x180065137  lea     rdx, stru_18010F018; HSTRING
0x18006513e  mov     rcx, rbx; this
0x180065141  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180065146  test    al, al
0x180065148  jz      short loc_180065156
0x18006514a  mov     cl, [r14+199h]
0x180065151  jmp     loc_180064EAA
0x180065156  lea     rdx, stru_18010EFA0; HSTRING
0x18006515d  mov     rcx, rbx; this
0x180065160  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180065165  test    al, al
0x180065167  jz      short loc_180065175
0x180065169  mov     cl, [r14+198h]
0x180065170  jmp     loc_180064EAA
0x180065175  lea     rdx, stru_18010F400; HSTRING
0x18006517c  mov     rcx, rbx; this
0x18006517f  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180065184  test    al, al
0x180065186  jz      loc_18006533B
0x18006518c  mov     [rsp+120h+string], rsi
0x180065191  lea     rcx, [rsp+120h+string]
0x180065196  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x18006519b  mov     [rsp+120h+string], rsi
0x1800651a0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800651a7  mov     ecx, 0B8h; unsigned __int64
0x1800651ac  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800651b1  mov     qword ptr [rsp+120h+var_E8], rax
0x1800651b6  mov     rdi, rsi
0x1800651b9  test    rax, rax
0x1800651bc  jz      short loc_1800651CE
0x1800651be  mov     rcx, rax
0x1800651c1  call    ??0?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@QEAA@AEBU?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@1234@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>(Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *> const &,Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::permission)
0x1800651c6  mov     rdi, rax
0x1800651c9  mov     qword ptr [rsp+120h+var_E8], rsi
0x1800651ce  lea     rcx, [rsp+120h+var_E8]
0x1800651d3  call    ??1?$MakeAllocator@V?$CTaskWrapper@AEAV_lambda_1dabfb557c6ca53c8eb192beb0706936_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_1dabfb557c6ca53c8eb192beb0706936_ &>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_1dabfb557c6ca53c8eb192beb0706936_ &>>(void)
0x1800651d8  test    rdi, rdi
0x1800651db  jnz     short loc_1800651E4
0x1800651dd  mov     ebx, 8007000Eh
0x1800651e2  jmp     short loc_1800651EB
0x1800651e4  mov     ebx, esi
0x1800651e6  mov     [rsp+120h+string], rdi
0x1800651eb  test    ebx, ebx
0x1800651ed  jns     short loc_180065224
0x1800651ef  mov     rcx, [rbp+5Fh]; this
0x1800651f3  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x1800651fa  mov     [rsp+120h+var_F8], rax; char *
0x1800651ff  lea     rax, aHs; "%hs"
0x180065206  mov     qword ptr [rsp+120h+var_100], rax; int
0x18006520b  mov     r9d, ebx; char *
0x18006520e  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\coresettinghandlers"...
0x180065215  mov     edx, 64Eh; void *
0x18006521a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006521f  jmp     loc_18006532C
0x180065224  mov     rdi, [r14+1A8h]
0x18006522b  mov     rbx, [rdi]
0x18006522e  mov     r12d, 1
0x180065234  cmp     rbx, rdi
0x180065237  jz      loc_1800652FD
0x18006523d  lea     rdx, [rbx+10h]
0x180065241  lea     rcx, [rsp+120h+var_D8]
0x180065246  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006524b  mov     rsi, [rbx+30h]
0x18006524f  mov     [rbp+57h+var_B8], rsi
0x180065253  lea     rcx, [rbp+57h+var_B8]
0x180065257  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18006525c  mov     qword ptr [rsp+120h+var_E8], rsi
0x180065261  lea     rcx, [rsp+120h+var_E8]
0x180065266  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18006526b  mov     r9b, r12b
0x18006526e  mov     r8, rsi
0x180065271  xor     edx, edx
0x180065273  mov     rcx, [rsp+120h+string]
0x180065278  call    ?InsertAtInternal@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUISettingItem@DataModel@SystemSettings@@_N@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(uint,SystemSettings::DataModel::ISettingItem *,bool)
0x18006527d  mov     r13d, eax
0x180065280  test    eax, eax
0x180065282  js      short loc_1800652A8
0x180065284  test    rsi, rsi
0x180065287  jz      short loc_180065299
0x180065289  mov     rax, [rsi]
0x18006528c  mov     rcx, rsi
0x18006528f  mov     rax, [rax+10h]
0x180065293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065298  nop
0x180065299  lea     rcx, [rsp+120h+var_D8]
0x18006529e  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@VUnusedApplicationItem@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@@std@@QEAA@XZ; std::pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::UnusedApplicationItem>>::~pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::UnusedApplicationItem>>(void)
0x1800652a3  mov     rbx, [rbx]
0x1800652a6  jmp     short loc_180065234
0x1800652a8  mov     rcx, [rbp+5Fh]; this
0x1800652ac  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x1800652b3  mov     [rsp+120h+var_F8], rax; char *
0x1800652b8  lea     rax, aHs; "%hs"
0x1800652bf  mov     qword ptr [rsp+120h+var_100], rax; int
0x1800652c4  mov     r9d, r13d; char *
0x1800652c7  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\coresettinghandlers"...
0x1800652ce  mov     edx, 654h; void *
0x1800652d3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800652d8  nop
0x1800652d9  test    rsi, rsi
0x1800652dc  jz      short loc_1800652EE
0x1800652de  mov     rax, [rsi]
0x1800652e1  mov     rcx, rsi
0x1800652e4  mov     rax, [rax+10h]
0x1800652e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800652ed  nop
0x1800652ee  lea     rcx, [rsp+120h+var_D8]
0x1800652f3  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@VUnusedApplicationItem@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@@std@@QEAA@XZ; std::pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::UnusedApplicationItem>>::~pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::UnusedApplicationItem>>(void)
0x1800652f8  mov     ebx, r13d
0x1800652fb  jmp     short loc_18006532C
0x1800652fd  mov     r8, r15
0x180065300  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x180065307  mov     rcx, [rsp+120h+string]
0x18006530c  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$IIterable@PEAUISettingItem@DataModel@SystemSettings@@@234@U?$IObservableVector@PEAUISettingItem@DataModel@SystemSettings@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$IIterable@PEAUISettingItem@DataModel@SystemSettings@@@234@U?$IObservableVector@PEAUISettingItem@DataModel@SystemSettings@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IIterable<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IIterable<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x180065311  mov     ebx, eax
0x180065313  mov     [rsp+120h+var_E8], 3
0x18006531b  lea     rcx, [rsp+120h+var_E8]
0x180065320  call    ??$CleanupErrorsVisualized@W4RecommenderKind@RecommenderEngineUtils@StorageSenseHandlers@SystemSettings@@@CleanupRecommendationsLogger@@SAX$$QEAW4RecommenderKind@RecommenderEngineUtils@StorageSenseHandlers@SystemSettings@@@Z; CleanupRecommendationsLogger::CleanupErrorsVisualized<SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind>(SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind &&)
0x180065325  mov     [r14+0D8h], r12b
0x18006532c  lea     rcx, [rsp+120h+string]
0x180065331  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
  ... truncated ...
```
