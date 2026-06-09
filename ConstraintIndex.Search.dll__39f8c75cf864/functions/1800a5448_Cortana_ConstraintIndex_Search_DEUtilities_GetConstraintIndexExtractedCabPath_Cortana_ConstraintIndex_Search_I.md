# Cortana::ConstraintIndex::Search::DEUtilities::GetConstraintIndexExtractedCabPath(Cortana::ConstraintIndex::Search::IConstraintIndexOptions *,Platform::Object * *)

- ea: `0x1800a5448`
- end: `0x1800a5da0`
- name: `?GetConstraintIndexExtractedCabPath@DEUtilities@Search@ConstraintIndex@Cortana@@SAPE$AAVString@Platform@@PE$AAUIConstraintIndexOptions@234@PEAPE$AAVObject@6@@Z`
- size: `2392`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `41`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c19a0`

## callees

- `0x1800049e0`
- `0x18000616e`
- `0x18000617a`
- `0x18000619e`
- `0x1800061aa`
- `0x18000cdf0`
- `0x18003a660`
- `0x18003b2f4`
- `0x18003b6f8`
- `0x18003fd04`
- `0x18003feb4`
- `0x18003fee0`
- `0x18003ff00`
- `0x18003ff8c`
- `0x1800819a8`
- `0x1800830d0`
- `0x180086610`
- `0x180086680`
- `0x18008ca74`
- `0x180092490`
- `0x180092508`
- `0x180092be4`
- `0x180092d24`
- `0x180092f34`
- `0x1800930a8`
- `0x1800940f8`
- `0x1800942dc`
- `0x18009440c`
- `0x1800a2ab8`
- `0x1800a3f7c`
- `0x1800a4028`
- `0x1800a4e30`
- `0x1800a4f10`
- `0x1800a5168`
- `0x1800a5448`
- `0x1800a5dfc`
- `0x1800a60c8`
- `0x1800a9860`
- `0x1800a9b4c`
- `0x1800a9d10`
- `0x1800a9e3c`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800a54d8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800a5a85`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800a5ac3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800a54d8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800a5a85`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800a5ac3`

## string_xrefs

- `0x1800a5517`: `com.microsoft.windows.services.experiences`
- `0x1800a5503`: `WindowsUdk.Services.Experiences.ExperiencePackProvider`

## pseudocode

```c
__int64 __fastcall Cortana::ConstraintIndex::Search::DEUtilities::GetConstraintIndexExtractedCabPath(
        __int64 a1,
        __int64 a2)
{
  HSTRING v4; // r12
  Cortana::ConstraintIndex::Search *v5; // rcx
  const WCHAR *v6; // rax
  HRESULT v7; // eax
  __int64 v8; // rax
  HSTRING v9; // rsi
  __int64 v10; // r14
  __int64 v11; // rbx
  HRESULT v12; // eax
  __int64 v13; // r15
  __int64 v14; // rcx
  HSTRING v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rbx
  HSTRING v18; // rsi
  __int64 v19; // rcx
  __int64 v20; // rbx
  HSTRING v21; // r15
  __int64 v22; // rbx
  HSTRING v23; // rsi
  HSTRING v24; // r12
  HRESULT v25; // eax
  HSTRING v26; // rsi
  HSTRING v27; // r15
  HSTRING v28; // rbx
  std::filesystem *v29; // rcx
  const struct std::filesystem::path *v30; // rdx
  HSTRING UserSettingsDirectoryLanguage; // rbx
  HSTRING v32; // r13
  HRESULT v33; // eax
  HSTRING v34; // rsi
  HSTRING v35; // r15
  HSTRING v36; // rbx
  std::filesystem *v37; // rcx
  const struct std::filesystem::path *v38; // rdx
  HRESULT v39; // eax
  HSTRING v40; // rsi
  HSTRING v41; // rbx
  __int64 v42; // rbx
  HSTRING LastDownloadedConstraintIndexCabPath; // rbx
  HSTRING v44; // r13
  const WCHAR *v45; // rax
  const WCHAR *StringRawBuffer_0; // rax
  HRESULT v47; // eax
  HSTRING v48; // rbx
  HSTRING v49; // rcx
  HSTRING v50; // rcx
  HRESULT v51; // eax
  __int64 v52; // r15
  HSTRING GuidString; // r15
  HRESULT v54; // eax
  HRESULT v56; // eax
  HSTRING v57; // rdi
  HSTRING v58; // rbx
  __int64 Factory; // [rsp+20h] [rbp-1E8h]
  __int64 v61; // [rsp+20h] [rbp-1E8h]
  HSTRING v62; // [rsp+20h] [rbp-1E8h]
  HSTRING v63; // [rsp+28h] [rbp-1E0h] BYREF
  HSTRING v64; // [rsp+30h] [rbp-1D8h]
  __int64 v65; // [rsp+38h] [rbp-1D0h]
  HSTRING v66[2]; // [rsp+40h] [rbp-1C8h] BYREF
  HSTRING Results; // [rsp+50h] [rbp-1B8h]
  __int64 v68; // [rsp+58h] [rbp-1B0h]
  HSTRING v69; // [rsp+60h] [rbp-1A8h]
  HSTRING v70; // [rsp+68h] [rbp-1A0h]
  HSTRING_HEADER v71; // [rsp+70h] [rbp-198h] BYREF
  __int128 v72; // [rsp+90h] [rbp-178h] BYREF
  _BYTE v73[8]; // [rsp+A0h] [rbp-168h] BYREF
  std::_Ref_count_base *v74; // [rsp+A8h] [rbp-160h]
  HSTRING_HEADER v75; // [rsp+B0h] [rbp-158h] BYREF
  HSTRING v76; // [rsp+C8h] [rbp-140h]
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp-138h] BYREF
  HSTRING_HEADER v78; // [rsp+E8h] [rbp-120h] BYREF
  _BYTE v79[96]; // [rsp+100h] [rbp-108h] BYREF
  _BYTE v80[96]; // [rsp+160h] [rbp-A8h] BYREF
  HSTRING v81; // [rsp+1C0h] [rbp-48h] BYREF
  HSTRING string; // [rsp+1C8h] [rbp-40h] BYREF
  HSTRING v83; // [rsp+1D0h] [rbp-38h] BYREF

  v64 = (HSTRING)Cortana::ConstraintIndex::Search::IConstraintIndexOptions::CurrentConstraintIndexCabPath::get();
  v4 = (HSTRING)__abi_winrt_ptrto_string_ctor(v64);
  v63 = v4;
  WindowsDeleteString_0(v64);
  __abi_winrt_ptr_assign(a2, 0);
  if ( Cortana::ConstraintIndex::Search::IsCShellSettingsApp(v5) )
  {
    LastDownloadedConstraintIndexCabPath = (HSTRING)Cortana::ConstraintIndex::Search::DEUtilities::GetLastDownloadedConstraintIndexCabPath(a1);
    v44 = (HSTRING)__abi_winrt_ptrto_string_ctor(LastDownloadedConstraintIndexCabPath);
    v65 = (__int64)v44;
    WindowsDeleteString_0(LastDownloadedConstraintIndexCabPath);
    string = 0;
    if ( WindowsIsStringEmpty_0(v4) || (v45 = WindowsGetStringRawBuffer_0(v4, 0), !PathFileExistsW(v45)) )
    {
      v83 = 0;
      v51 = WindowsCreateStringReference_0(L"\\ConstraintIndex\\ConstraintIndex.cab", 0x24u, &v71, &v83);
      if ( v51 < 0 )
        __abi_WinRTraiseException(v51);
      v52 = Windows::ApplicationModel::Package::Current::get();
      Results = (HSTRING)Windows::Networking::BackgroundTransfer::IBackgroundTransferOperation::RequestedUri::get(v52);
      v70 = (HSTRING)__abi_winrt_cast_to(0, Results, _uuidof__AUIStorageItem_Storage_Windows__);
      v69 = (HSTRING)Windows::Storage::IStorageItem::Path::get(v70);
      v64 = (HSTRING)Platform::String::Concat(v69, v83);
      __abi_winrt_ptrto_string_assign(&string, v64);
      WindowsDeleteString_0(v64);
      WindowsDeleteString_0(v69);
      __abi_winrt_ptr_dtor(v70);
      __abi_winrt_ptr_dtor(Results);
      __abi_winrt_ptr_dtor(v52);
      GuidString = (HSTRING)Cortana::ConstraintIndex::Search::DEUtilities::GenerateGuidString();
      v66[0] = GuidString;
      v83 = 0;
      v54 = WindowsCreateStringReference_0(L"\\ConstraintIndex\\Input_", 0x17u, &v71, &v83);
      if ( v54 < 0 )
        __abi_WinRTraiseException(v54);
      Results = (HSTRING)Windows::Foundation::IAsyncOperation<Platform::String __gc *>::GetResults(a1);
      v70 = (HSTRING)Platform::String::Concat(Results, v83);
      v69 = (HSTRING)Platform::String::Concat(v70, GuidString);
      v66[0] = (HSTRING)__abi_winrt_ptrto_string_ctor(v69);
      WindowsDeleteString_0(v69);
      WindowsDeleteString_0(v70);
      WindowsDeleteString_0(Results);
      WindowsDeleteString_0(GuidString);
      Cortana::ConstraintIndex::Search::DEUtilities::ExtractCab(string, v66[0]);
      v42 = __abi_winrt_ptrto_string_ctor(v66[0]);
      v49 = v66[0];
    }
    else
    {
      if ( WindowsIsStringEmpty_0(v44)
        || (unsigned __int8)Platform::String::operator==(v4, v44)
        || (StringRawBuffer_0 = WindowsGetStringRawBuffer_0(v44, 0), !PathFileExistsW(StringRawBuffer_0)) )
      {
        v42 = __abi_winrt_ptrto_string_ctor(v4);
        v50 = 0;
LABEL_39:
        WindowsDeleteString_0(v50);
        WindowsDeleteString_0(v44);
        goto LABEL_40;
      }
      v83 = 0;
      v47 = WindowsCreateStringReference_0(L"\\ConstraintIndex.cab", 0x14u, &v71, &v83);
      if ( v47 < 0 )
        __abi_WinRTraiseException(v47);
      v48 = (HSTRING)Platform::String::Concat(v44, v83);
      __abi_winrt_ptrto_string_assign(&string, v48);
      WindowsDeleteString_0(v48);
      v66[0] = (HSTRING)__abi_winrt_ptrto_string_ctor(v44);
      Cortana::ConstraintIndex::Search::DEUtilities::ExtractCab(string, v66[0]);
      v42 = __abi_winrt_ptrto_string_ctor(v66[0]);
      v49 = v66[0];
    }
    WindowsDeleteString_0(v49);
    v50 = string;
    goto LABEL_39;
  }
  if ( WindowsIsStringEmpty_0(v4) || (v6 = WindowsGetStringRawBuffer_0(v4, 0), !PathFileExistsW(v6)) )
  {
    string = 0;
    v7 = WindowsCreateStringReference_0(
           L"WindowsUdk.Services.Experiences.ExperiencePackProvider",
           0x36u,
           &hstringHeader,
           &string);
    if ( v7 < 0 )
      __abi_WinRTraiseException(v7);
    v8 = Platform::StringReference::StringReference(&v75, L"com.microsoft.windows.services.experiences");
    Factory = WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory::GetFactory(*(_QWORD *)(v8 + 24), string);
    v64 = (HSTRING)__abi_winrt_cast_to(
                     0,
                     Factory,
                     _uuidof__AUIExperiencePackProviderStatics_Experiences_Services_WindowsUdk__);
    v9 = (HSTRING)__abi_winrt_ptr_ctor(v64);
    v83 = v9;
    __abi_winrt_ptr_dtor(v64);
    __abi_winrt_ptr_dtor(Factory);
    WindowsDeleteString_0(v76);
    if ( v9 )
    {
      v61 = Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<Platform::String __gc *,Windows::Data::Json::IJsonValue __gc *> __gc *>::Current::get(v9);
      v10 = __abi_winrt_ptr_ctor(v61);
      v68 = v10;
      __abi_winrt_ptr_dtor(v61);
      if ( v10 )
      {
        v11 = Concurrency::task_options::task_options((Concurrency::task_options *)v79);
        string = 0;
        v12 = WindowsCreateStringReference_0(L"Windows.Settings.SearchData", 0x1Bu, &v78, &string);
        if ( v12 < 0 )
          __abi_WinRTraiseException(v12);
        v13 = Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue __gc *>::GetAt(v10, string);
        v14 = Concurrency::create_task<Windows::Foundation::IAsyncOperation<WindowsUdk::Services::Experiences::ExperiencePack __gc *> __gc *>(
                v73,
                v13,
                v11);
        v64 = (HSTRING)Concurrency::task<WindowsUdk::Services::Experiences::ExperiencePackLock __gc *>::get(v14);
        v15 = (HSTRING)__abi_winrt_ptr_ctor(v64);
        string = v15;
        __abi_winrt_ptr_dtor(v64);
        if ( v74 )
          std::_Ref_count_base::_Decref(v74);
        __abi_winrt_ptr_dtor(v13);
        if ( v15 )
        {
          v16 = Concurrency::task_options::task_options((Concurrency::task_options *)v80);
          try
          {
            v17 = v16;
            v18 = (HSTRING)Windows::Networking::BackgroundTransfer::IDownloadOperation::AttachAsync(v15);
            v64 = v18;
            v19 = Concurrency::create_task<Windows::Foundation::IAsyncOperation<WindowsUdk::Services::Experiences::ExperiencePackLock __gc *> __gc *>(
                    &v72,
                    v18,
                    v17);
            v20 = Concurrency::task<WindowsUdk::Services::Experiences::ExperiencePackLock __gc *>::get(v19);
            v21 = (HSTRING)__abi_winrt_ptr_ctor(v20);
            v62 = v21;
            v69 = v21;
            __abi_winrt_ptr_dtor(v20);
            if ( *((_QWORD *)&v72 + 1) )
              std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v72 + 1));
            __abi_winrt_ptr_dtor(v18);
            __abi_winrt_ptr_assign(a2, v21);
            v22 = Windows::System::UserProfile::GlobalizationPreferences::Languages::get();
            v23 = (HSTRING)Windows::Foundation::Collections::IVectorView<Platform::String __gc *>::GetAt(v22, 0);
            v81 = v23;
            v24 = (HSTRING)__abi_winrt_ptrto_string_ctor(v23);
            v64 = v24;
            v70 = v24;
            WindowsDeleteString_0(v23);
            __abi_winrt_ptr_dtor(v22);
            v81 = 0;
            v25 = WindowsCreateStringReference_0(L"\\", 1u, &v71, &v81);
            if ( v25 < 0 )
              __abi_WinRTraiseException(v25);
            v26 = (HSTRING)WindowsUdk::Services::Experiences::IExperiencePack::ContentPath::get(v15);
            Results = v26;
            v27 = (HSTRING)Platform::String::Concat(v26, v81);
            v81 = v27;
            v28 = (HSTRING)Platform::String::Concat(v27, v24);
            v66[0] = v28;
            __abi_winrt_ptrto_string_assign(&v63, v28);
            WindowsDeleteString_0(v28);
            WindowsDeleteString_0(v27);
            WindowsDeleteString_0(v26);
            v4 = v63;
            v81 = (HSTRING)WindowsGetStringRawBuffer_0(v63, 0);
            v29 = (std::filesystem *)std::filesystem::path::path(&v71, &v81);
            LOBYTE(v28) = std::filesystem::exists(v29, v30);
            std::wstring::_Tidy_deallocate(&v71);
            if ( !(_BYTE)v28 )
            {
              UserSettingsDirectoryLanguage = (HSTRING)Cortana::ConstraintIndex::Search::GetUserSettingsDirectoryLanguage();
              v66[0] = UserSettingsDirectoryLanguage;
              v32 = (HSTRING)__abi_winrt_ptrto_string_ctor(UserSettingsDirectoryLanguage);
              v66[0] = v32;
              WindowsDeleteString_0(UserSettingsDirectoryLanguage);
              v81 = 0;
              v33 = WindowsCreateStringReference_0(L"\\", 1u, &v71, &v81);
              if ( v33 < 0 )
                __abi_WinRTraiseException(v33);
              v34 = (HSTRING)WindowsUdk::Services::Experiences::IExperiencePack::ContentPath::get(v15);
              Results = v34;
              v35 = (HSTRING)Platform::String::Concat(v34, v81);
              v81 = v35;
              v36 = (HSTRING)Platform::String::Concat(v35, v32);
              v65 = (__int64)v36;
              __abi_winrt_ptrto_string_assign(&v63, v36);
              WindowsDeleteString_0(v36);
              WindowsDeleteString_0(v35);
              WindowsDeleteString_0(v34);
              v4 = v63;
              v81 = (HSTRING)WindowsGetStringRawBuffer_0(v63, 0);
              v37 = (std::filesystem *)std::filesystem::path::path(&v71, &v81);
              LOBYTE(v36) = std::filesystem::exists(v37, v38);
              std::wstring::_Tidy_deallocate(&v71);
              if ( !(_BYTE)v36 )
              {
                v81 = 0;
                v39 = WindowsCreateStringReference_0(L"\\en-US", 6u, &v71, &v81);
                if ( v39 < 0 )
                  __abi_WinRTraiseException(v39);
                v40 = (HSTRING)WindowsUdk::Services::Experiences::IExperiencePack::ContentPath::get(v15);
                v65 = (__int64)v40;
                v41 = (HSTRING)Platform::String::Concat(v40, v81);
                Results = v41;
                __abi_winrt_ptrto_string_assign(&v63, v41);
                WindowsDeleteString_0(v41);
                WindowsDeleteString_0(v40);
                v4 = v63;
              }
              WindowsDeleteString_0(v32);
            }
            WindowsDeleteString_0(v64);
            __abi_winrt_ptr_dtor(v62);
          }
          catch ( ... )
          {
            v81 = 0;
            v56 = WindowsCreateStringReference_0(L"\\en-US", 6u, &v71, &v81);
            if ( v56 < 0 )
              __abi_WinRTraiseException(v56);
            v57 = (HSTRING)WindowsUdk::Services::Experiences::IExperiencePack::ContentPath::get(string);
            v65 = (__int64)v57;
            v58 = (HSTRING)Platform::String::Concat(v57, v81);
            v66[0] = v58;
            __abi_winrt_ptrto_string_assign(&v63, v58);
            WindowsDeleteString_0(v58);
            WindowsDeleteString_0(v57);
            v72 = *(_OWORD *)WindowsUdk::Services::Experiences::IExperiencePack::Id::get(string, v66);
            v65 = WindowsUdk::Services::Experiences::IExperiencePackProvider::ReportPackFailedAsync(v68, &v72);
            __abi_winrt_ptr_dtor(v65);
            std::pair<Platform::String __gc * const,Platform::String __gc *>::~pair<Platform::String __gc * const,Platform::String __gc *>(v66);
            v4 = v63;
            v10 = v68;
            v15 = string;
          }
          v9 = v83;
        }
        __abi_winrt_ptr_dtor(v15);
      }
      __abi_winrt_ptr_dtor(v10);
    }
    __abi_winrt_ptr_dtor(v9);
  }
  v42 = __abi_winrt_ptrto_string_ctor(v4);
LABEL_40:
  WindowsDeleteString_0(v4);
  return v42;
}

```

## disassembly

```asm
0x1800a5448  mov     [rsp+arg_10], rbx
0x1800a544d  mov     [rsp+arg_18], rsi
0x1800a5452  push    rdi
0x1800a5453  push    r12
0x1800a5455  push    r13
0x1800a5457  push    r14
0x1800a5459  push    r15
0x1800a545b  sub     rsp, 1E0h
0x1800a5462  mov     rax, cs:__security_cookie
0x1800a5469  xor     rax, rsp
0x1800a546c  mov     [rsp+208h+var_30], rax
0x1800a5474  mov     r13, rdx
0x1800a5477  mov     rdi, rcx
0x1800a547a  mov     [rsp+208h+var_1E8], rcx
0x1800a547f  call    ?get@CurrentConstraintIndexCabPath@IConstraintIndexOptions@Search@ConstraintIndex@Cortana@@UE$AAAPE$AAVString@Platform@@XZ; Cortana::ConstraintIndex::Search::IConstraintIndexOptions::CurrentConstraintIndexCabPath::get(void)
0x1800a5484  mov     rbx, rax
0x1800a5487  mov     [rsp+208h+var_1D8], rax
0x1800a548c  mov     rcx, rax
0x1800a548f  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x1800a5494  mov     r12, rax
0x1800a5497  mov     [rsp+208h+var_1E0], rax
0x1800a549c  mov     rcx, rbx; string
0x1800a549f  call    WindowsDeleteString_0
0x1800a54a4  nop
0x1800a54a5  xor     edx, edx
0x1800a54a7  mov     rcx, r13
0x1800a54aa  call    ?__abi_winrt_ptr_assign@@YAPEAXPEAPEAXPE$ADVObject@Platform@@@Z; __abi_winrt_ptr_assign(void * *,Platform::Object const volatile *)
0x1800a54af  call    ?IsCShellSettingsApp@Search@ConstraintIndex@Cortana@@YA_NXZ; Cortana::ConstraintIndex::Search::IsCShellSettingsApp(void)
0x1800a54b4  xor     r15d, r15d
0x1800a54b7  test    al, al
0x1800a54b9  jnz     loc_1800A5A37
0x1800a54bf  mov     rcx, r12; string
0x1800a54c2  call    WindowsIsStringEmpty_0
0x1800a54c7  test    eax, eax
0x1800a54c9  jnz     short loc_1800A54E6
0x1800a54cb  xor     edx, edx; length
0x1800a54cd  mov     rcx, r12; string
0x1800a54d0  call    WindowsGetStringRawBuffer_0
0x1800a54d5  mov     rcx, rax; pszPath
0x1800a54d8  call    cs:__imp_PathFileExistsW
0x1800a54de  test    eax, eax
0x1800a54e0  jnz     loc_1800A5A27
0x1800a54e6  mov     [rsp+208h+string], r15
0x1800a54ee  lea     r9, [rsp+208h+string]; string
0x1800a54f6  lea     r8, [rsp+208h+hstringHeader]; hstringHeader
0x1800a54fe  mov     edx, 36h ; '6'; length
0x1800a5503  lea     rcx, aWindowsudkServ; "WindowsUdk.Services.Experiences.Experie"...
0x1800a550a  call    WindowsCreateStringReference_0
0x1800a550f  test    eax, eax
0x1800a5511  js      loc_1800A5D61
0x1800a5517  lea     rdx, aComMicrosoftWi; "com.microsoft.windows.services.experien"...
0x1800a551e  lea     rcx, [rsp+208h+var_158]; hstringHeader
0x1800a5526  call    ??0StringReference@Platform@@QEAA@PEB_W@Z; Platform::StringReference::StringReference(wchar_t const *)
0x1800a552b  nop
0x1800a552c  mov     rdx, [rsp+208h+string]
0x1800a5534  mov     rcx, [rax+18h]
0x1800a5538  call    ?GetFactory@ExtensionFactory@AppExtensions@ApplicationModel@WindowsUdk@@SAPE$AAVObject@Platform@@PE$AAVString@6@0@Z; WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory::GetFactory(Platform::String *,Platform::String *)
0x1800a553d  mov     rdi, rax
0x1800a5540  mov     [rsp+208h+var_1E8], rax
0x1800a5545  lea     r8, __uuidof_?AUIExperiencePackProviderStatics@Experiences@Services@WindowsUdk@@
0x1800a554c  mov     rdx, rax
0x1800a554f  xor     ecx, ecx
0x1800a5551  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x1800a5556  mov     rbx, rax
0x1800a5559  mov     [rsp+208h+var_1D8], rax
0x1800a555e  mov     rcx, rax
0x1800a5561  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800a5566  mov     rsi, rax
0x1800a5569  mov     [rsp+208h+var_38], rax
0x1800a5571  mov     rcx, rbx
0x1800a5574  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800a5579  nop
0x1800a557a  mov     rcx, rdi
0x1800a557d  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800a5582  nop
0x1800a5583  mov     rcx, [rsp+208h+var_140]; string
0x1800a558b  call    WindowsDeleteString_0
0x1800a5590  nop
0x1800a5591  test    rsi, rsi
0x1800a5594  jz      loc_1800A5A1F
0x1800a559a  mov     rcx, rsi
0x1800a559d  call    ?get@Current@?$IIterator@PE$AAU?$IKeyValuePair@PE$AAVString@Platform@@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@UE$AAAPE$AAU?$IKeyValuePair@PE$AAVString@Platform@@PE$AAUIJsonValue@Json@Data@Windows@@@345@XZ; Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<Platform::String *,Windows::Data::Json::IJsonValue *> *>::Current::get(void)
0x1800a55a2  mov     rbx, rax
0x1800a55a5  mov     [rsp+208h+var_1E8], rax
0x1800a55aa  mov     rcx, rax
0x1800a55ad  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800a55b2  mov     r14, rax
0x1800a55b5  mov     [rsp+208h+var_1B0], rax
0x1800a55ba  mov     rcx, rbx
0x1800a55bd  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800a55c2  nop
0x1800a55c3  test    r14, r14
0x1800a55c6  jz      loc_1800A5A16
0x1800a55cc  lea     rax, [rsp+208h+var_108]
0x1800a55d4  mov     [rsp+208h+var_1E8], rax
0x1800a55d9  lea     rcx, [rsp+208h+var_108]; this
0x1800a55e1  call    ??0task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::task_options(void)
0x1800a55e6  mov     rbx, rax
0x1800a55e9  mov     [rsp+208h+string], r15
0x1800a55f1  lea     r9, [rsp+208h+string]; string
0x1800a55f9  lea     r8, [rsp+208h+var_120]; hstringHeader
0x1800a5601  mov     edx, 1Bh; length
0x1800a5606  lea     rcx, aWindowsSetting; "Windows.Settings.SearchData"
0x1800a560d  call    WindowsCreateStringReference_0
0x1800a5612  test    eax, eax
0x1800a5614  js      loc_1800A5D69
0x1800a561a  mov     rdx, [rsp+208h+string]
0x1800a5622  mov     rcx, r14
0x1800a5625  call    ?GetAt@?$IVector@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@UE$AAAPE$AAUIJsonValue@Json@Data@4@I@Z; Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>::GetAt(uint)
0x1800a562a  mov     r15, rax
0x1800a562d  mov     [rsp+208h+var_1E8], rax
0x1800a5632  mov     r8, rbx
0x1800a5635  mov     rdx, rax
0x1800a5638  lea     rcx, [rsp+208h+var_168]
0x1800a5640  call    ??$create_task@PE$AAU?$IAsyncOperation@PE$AAVExperiencePack@Experiences@Services@WindowsUdk@@@Foundation@Windows@@@Concurrency@@YA?AV?$task@PE$AAVExperiencePack@Experiences@Services@WindowsUdk@@@0@PE$AAU?$IAsyncOperation@PE$AAVExperiencePack@Experiences@Services@WindowsUdk@@@Foundation@Windows@@Vtask_options@0@@Z; Concurrency::create_task<Windows::Foundation::IAsyncOperation<WindowsUdk::Services::Experiences::ExperiencePack *> *>(Windows::Foundation::IAsyncOperation<WindowsUdk::Services::Experiences::ExperiencePack *> *,Concurrency::task_options)
0x1800a5645  nop
0x1800a5646  mov     rcx, rax
0x1800a5649  call    ?get@?$task@PE$AAVExperiencePackLock@Experiences@Services@WindowsUdk@@@Concurrency@@QEBAPE$AAVExperiencePackLock@Experiences@Services@WindowsUdk@@XZ; Concurrency::task<WindowsUdk::Services::Experiences::ExperiencePackLock *>::get(void)
0x1800a564e  mov     rbx, rax
0x1800a5651  mov     [rsp+208h+var_1D8], rax
0x1800a5656  mov     rcx, rax
0x1800a5659  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800a565e  mov     rdi, rax
0x1800a5661  mov     [rsp+208h+string], rax
0x1800a5669  mov     rcx, rbx
0x1800a566c  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800a5671  nop
0x1800a5672  mov     rcx, [rsp+208h+var_160]; this
0x1800a567a  test    rcx, rcx
0x1800a567d  jz      short loc_1800A5685
0x1800a567f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a5684  nop
0x1800a5685  mov     rcx, r15
0x1800a5688  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800a568d  nop
0x1800a568e  test    rdi, rdi
0x1800a5691  jz      loc_1800A5A0D
0x1800a5697  lea     rax, [rsp+208h+var_A8]
0x1800a569f  mov     [rsp+208h+var_1E8], rax
0x1800a56a4  lea     rcx, [rsp+208h+var_A8]; this
0x1800a56ac  call    ??0task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::task_options(void)
0x1800a56b1  mov     rbx, rax
0x1800a56b4  mov     rcx, rdi
0x1800a56b7  call    ?AttachAsync@IDownloadOperation@BackgroundTransfer@Networking@Windows@@UE$AAAPE$AAU?$IAsyncOperationWithProgress@PE$AAVDownloadOperation@BackgroundTransfer@Networking@Windows@@PE$AAV1234@@Foundation@4@XZ; Windows::Networking::BackgroundTransfer::IDownloadOperation::AttachAsync(void)
0x1800a56bc  mov     rsi, rax
0x1800a56bf  mov     [rsp+208h+var_1D8], rax
0x1800a56c4  mov     r8, rbx
0x1800a56c7  mov     rdx, rax
0x1800a56ca  lea     rcx, [rsp+208h+var_178]
0x1800a56d2  call    ??$create_task@PE$AAU?$IAsyncOperation@PE$AAVExperiencePackLock@Experiences@Services@WindowsUdk@@@Foundation@Windows@@@Concurrency@@YA?AV?$task@PE$AAVExperiencePackLock@Experiences@Services@WindowsUdk@@@0@PE$AAU?$IAsyncOperation@PE$AAVExperiencePackLock@Experiences@Services@WindowsUdk@@@Foundation@Windows@@Vtask_options@0@@Z; Concurrency::create_task<Windows::Foundation::IAsyncOperation<WindowsUdk::Services::Experiences::ExperiencePackLock *> *>(Windows::Foundation::IAsyncOperation<WindowsUdk::Services::Experiences::ExperiencePackLock *> *,Concurrency::task_options)
0x1800a56d7  nop
0x1800a56d8  mov     rcx, rax
0x1800a56db  call    ?get@?$task@PE$AAVExperiencePackLock@Experiences@Services@WindowsUdk@@@Concurrency@@QEBAPE$AAVExperiencePackLock@Experiences@Services@WindowsUdk@@XZ; Concurrency::task<WindowsUdk::Services::Experiences::ExperiencePackLock *>::get(void)
0x1800a56e0  mov     rbx, rax
0x1800a56e3  mov     [rsp+208h+var_1E8], rax
0x1800a56e8  mov     rcx, rax
0x1800a56eb  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800a56f0  mov     r15, rax
0x1800a56f3  mov     [rsp+208h+var_1E8], rax
0x1800a56f8  mov     [rsp+208h+var_1A8], rax
0x1800a56fd  mov     rcx, rbx
0x1800a5700  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800a5705  nop
0x1800a5706  mov     rcx, [rsp+208h+var_170]; this
0x1800a570e  test    rcx, rcx
0x1800a5711  jz      short loc_1800A5719
0x1800a5713  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a5718  nop
0x1800a5719  mov     rcx, rsi
0x1800a571c  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800a5721  nop
0x1800a5722  mov     rdx, r15
0x1800a5725  mov     rcx, r13
0x1800a5728  call    ?__abi_winrt_ptr_assign@@YAPEAXPEAPEAXPE$ADVObject@Platform@@@Z; __abi_winrt_ptr_assign(void * *,Platform::Object const volatile *)
0x1800a572d  call    ?get@Languages@GlobalizationPreferences@UserProfile@System@Windows@@SAPE$AAU?$IVectorView@PE$AAVString@Platform@@@Collections@Foundation@5@XZ; Windows::System::UserProfile::GlobalizationPreferences::Languages::get(void)
0x1800a5732  mov     rbx, rax
0x1800a5735  mov     [rsp+208h+var_1D8], rax
0x1800a573a  xor     edx, edx
0x1800a573c  mov     rcx, rax
0x1800a573f  call    ?GetAt@?$IVectorView@PE$AAVString@Platform@@@Collections@Foundation@Windows@@UE$AAAPE$AAVString@Platform@@I@Z; Windows::Foundation::Collections::IVectorView<Platform::String *>::GetAt(uint)
0x1800a5744  mov     rsi, rax
0x1800a5747  mov     [rsp+208h+var_48], rax
0x1800a574f  mov     rcx, rax
0x1800a5752  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x1800a5757  mov     r12, rax
0x1800a575a  mov     [rsp+208h+var_1D8], rax
0x1800a575f  mov     [rsp+208h+var_1A0], rax
0x1800a5764  mov     rcx, rsi; string
0x1800a5767  call    WindowsDeleteString_0
0x1800a576c  nop
0x1800a576d  mov     rcx, rbx
0x1800a5770  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800a5775  nop
0x1800a5776  mov     [rsp+208h+var_48], 0
0x1800a5782  lea     r9, [rsp+208h+var_48]; string
0x1800a578a  lea     r8, [rsp+208h+var_198]; hstringHeader
0x1800a578f  mov     edx, 1; length
0x1800a5794  lea     rcx, asc_180104F88; "\\"
0x1800a579b  call    WindowsCreateStringReference_0
0x1800a57a0  test    eax, eax
0x1800a57a2  js      loc_1800A5D71
0x1800a57a8  mov     rcx, rdi
0x1800a57ab  call    ?get@ContentPath@IExperiencePack@Experiences@Services@WindowsUdk@@UE$AAAPE$AAVString@Platform@@XZ; WindowsUdk::Services::Experiences::IExperiencePack::ContentPath::get(void)
0x1800a57b0  mov     rsi, rax
0x1800a57b3  mov     [rsp+208h+var_1B8], rax
0x1800a57b8  mov     rdx, [rsp+208h+var_48]
0x1800a57c0  mov     rcx, rax
0x1800a57c3  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x1800a57c8  mov     r15, rax
0x1800a57cb  mov     [rsp+208h+var_48], rax
0x1800a57d3  mov     rdx, r12
0x1800a57d6  mov     rcx, rax
0x1800a57d9  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x1800a57de  mov     rbx, rax
0x1800a57e1  mov     [rsp+208h+var_1C8], rax
0x1800a57e6  mov     rdx, rax
0x1800a57e9  lea     rcx, [rsp+208h+var_1E0]
0x1800a57ee  call    ?__abi_winrt_ptrto_string_assign@@YAPEAXPEAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_assign(void * *,Platform::String const volatile *)
0x1800a57f3  nop
0x1800a57f4  mov     rcx, rbx; string
0x1800a57f7  call    WindowsDeleteString_0
0x1800a57fc  nop
0x1800a57fd  mov     rcx, r15; string
0x1800a5800  call    WindowsDeleteString_0
0x1800a5805  nop
0x1800a5806  mov     rcx, rsi; string
0x1800a5809  call    WindowsDeleteString_0
0x1800a580e  xor     edx, edx; length
0x1800a5810  mov     r12, [rsp+208h+var_1E0]
0x1800a5815  mov     rcx, r12; string
0x1800a5818  call    WindowsGetStringRawBuffer_0
0x1800a581d  mov     [rsp+208h+var_48], rax
0x1800a5825  lea     rdx, [rsp+208h+var_48]
0x1800a582d  lea     rcx, [rsp+208h+var_198]
0x1800a5832  call    ??$?0PEB_W$0A@@path@filesystem@std@@QEAA@AEBQEB_WW4format@012@@Z; std::filesystem::path::path(wchar_t const * const &,std::filesystem::path::format)
0x1800a5837  nop
0x1800a5838  mov     rcx, rax; this
0x1800a583b  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x1800a5840  mov     bl, al
0x1800a5842  lea     rcx, [rsp+208h+var_198]
0x1800a5847  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a584c  test    bl, bl
0x1800a584e  jnz     loc_1800A59DB
0x1800a5854  call    ?GetUserSettingsDirectoryLanguage@Search@ConstraintIndex@Cortana@@YAPE$AAVString@Platform@@XZ; Cortana::ConstraintIndex::Search::GetUserSettingsDirectoryLanguage(void)
0x1800a5859  mov     rbx, rax
0x1800a585c  mov     [rsp+208h+var_1C8], rax
0x1800a5861  mov     rcx, rax
0x1800a5864  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x1800a5869  mov     r13, rax
0x1800a586c  mov     [rsp+208h+var_1C8], rax
0x1800a5871  mov     rcx, rbx; string
0x1800a5874  call    WindowsDeleteString_0
0x1800a5879  nop
0x1800a587a  mov     [rsp+208h+var_48], 0
0x1800a5886  lea     r9, [rsp+208h+var_48]; string
0x1800a588e  lea     r8, [rsp+208h+var_198]; hstringHeader
0x1800a5893  mov     edx, 1; length
0x1800a5898  lea     rcx, asc_180104F88; "\\"
0x1800a589f  call    WindowsCreateStringReference_0
0x1800a58a4  test    eax, eax
0x1800a58a6  js      loc_1800A5D79
0x1800a58ac  mov     rcx, rdi
0x1800a58af  call    ?get@ContentPath@IExperiencePack@Experiences@Services@WindowsUdk@@UE$AAAPE$AAVString@Platform@@XZ; WindowsUdk::Services::Experiences::IExperiencePack::ContentPath::get(void)
0x1800a58b4  mov     rsi, rax
0x1800a58b7  mov     [rsp+208h+var_1B8], rax
0x1800a58bc  mov     rdx, [rsp+208h+var_48]
0x1800a58c4  mov     rcx, rax
0x1800a58c7  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x1800a58cc  mov     r15, rax
0x1800a58cf  mov     [rsp+208h+var_48], rax
0x1800a58d7  mov     rdx, r13
0x1800a58da  mov     rcx, rax
0x1800a58dd  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x1800a58e2  mov     rbx, rax
0x1800a58e5  mov     [rsp+208h+var_1D0], rax
0x1800a58ea  mov     rdx, rax
0x1800a58ed  lea     rcx, [rsp+208h+var_1E0]
0x1800a58f2  call    ?__abi_winrt_ptrto_string_assign@@YAPEAXPEAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_assign(void * *,Platform::String const volatile *)
0x1800a58f7  nop
0x1800a58f8  mov     rcx, rbx; string
0x1800a58fb  call    WindowsDeleteString_0
0x1800a5900  nop
0x1800a5901  mov     rcx, r15; string
0x1800a5904  call    WindowsDeleteString_0
0x1800a5909  nop
0x1800a590a  mov     rcx, rsi; string
0x1800a590d  call    WindowsDeleteString_0
0x1800a5912  xor     edx, edx; length
0x1800a5914  mov     r12, [rsp+208h+var_1E0]
0x1800a5919  mov     rcx, r12; string
0x1800a591c  call    WindowsGetStringRawBuffer_0
0x1800a5921  mov     [rsp+208h+var_48], rax
0x1800a5929  lea     rdx, [rsp+208h+var_48]
0x1800a5931  lea     rcx, [rsp+208h+var_198]
0x1800a5936  call    ??$?0PEB_W$0A@@path@filesystem@std@@QEAA@AEBQEB_WW4format@012@@Z; std::filesystem::path::path(wchar_t const * const &,std::filesystem::path::format)
0x1800a593b  nop
0x1800a593c  mov     rcx, rax; this
0x1800a593f  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x1800a5944  mov     bl, al
0x1800a5946  lea     rcx, [rsp+208h+var_198]
  ... truncated ...
```
