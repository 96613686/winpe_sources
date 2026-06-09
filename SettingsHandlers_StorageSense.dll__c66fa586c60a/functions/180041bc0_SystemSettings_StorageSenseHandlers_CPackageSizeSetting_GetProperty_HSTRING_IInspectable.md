# SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x180041bc0`
- end: `0x180042446`
- name: `?GetProperty@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `2182`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CPackageSizeSetting *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180074e30`

## callees

- `0x180001c1c`
- `0x180006e50`
- `0x180007a00`
- `0x18000a6e8`
- `0x18000c964`
- `0x180019eb4`
- `0x180019ff0`
- `0x18001dfe8`
- `0x18001f468`
- `0x18001f688`
- `0x18001fe08`
- `0x180022a1c`
- `0x18002adf4`
- `0x180036ae4`
- `0x180036bd4`
- `0x18003d408`
- `0x18003dbc4`
- `0x18003e344`
- `0x1800401cc`
- `0x180040c70`
- `0x180041bc0`
- `0x180043f48`
- `0x180044ddc`
- `0x180046408`
- `0x180049f18`
- `0x1800a26c0`
- `0x1800a8194`
- `0x1800a8734`
- `0x1800a8dd0`
- `0x1800a8fc8`
- `0x1800a9a84`
- `0x1800bb784`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041e55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041e55`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180041e1e`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180041e1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041c35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041d06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042183`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004230d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004234e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042380`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042403`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041c35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041d06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042183`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004230d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004234e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042380`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042403`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041c63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800421b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800423b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800423c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041c63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800421b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800423b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800423c5`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x180041cce`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x180041cce`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180041e4b`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180041e4b`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOnFile` at `0x1800421ce`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOnFile` at `0x1800421ce`

## string_xrefs

- `0x180041d38`: `InstallDate`
- `0x180042115`: `SystemSettings_StorageSense_App_Sizes_List_Uninstalling`
- `0x18004211c`: `SystemSettings_StorageSense_App_Sizes_List_Uninstalled`
- `0x180042139`: `SystemSettings_StorageSense_App_Sizes_List_Moved`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetProperty(
        SystemSettings::StorageSenseHandlers::CPackageSizeSetting *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  const unsigned __int16 *v6; // r8
  HSTRING v7; // rcx
  HSTRING *v8; // r8
  const unsigned __int16 *v9; // rax
  int Publisher; // edi
  SystemSettings::StorageSenseHandlers::CSizeCalculationThreadPool *v11; // rcx
  ULONGLONG v12; // rbx
  WCHAR *v13; // rcx
  int Double; // eax
  const unsigned __int16 *v15; // r8
  SystemSettings::StorageSenseHandlers::CAppTileData *v16; // rbx
  const unsigned __int16 *v17; // r8
  unsigned int InstallDate; // ebx
  signed int LastError; // eax
  bool v20; // sf
  unsigned __int64 v21; // rcx
  const unsigned __int16 *v22; // r8
  char *v23; // rcx
  const unsigned __int16 *v24; // r8
  const unsigned __int16 *v25; // r8
  const unsigned __int16 *v26; // r8
  const unsigned __int16 *v27; // r8
  const unsigned __int16 *v28; // r8
  unsigned __int8 v29; // cl
  const unsigned __int16 *v30; // r8
  const unsigned __int16 *v31; // r8
  double v32; // xmm0_8
  const unsigned __int16 *v33; // r8
  const unsigned __int16 *v34; // r8
  const unsigned __int16 *v35; // r8
  const unsigned __int16 *v36; // r8
  int v37; // ecx
  int v38; // ecx
  int v39; // ecx
  int v40; // ecx
  int v41; // ecx
  const wchar_t *v42; // rax
  const wchar_t *v43; // rcx
  const unsigned __int16 *v44; // r8
  SystemSettings::StorageSenseHandlers::CAppTileData *v45; // rbx
  PCWSTR StringRawBuffer; // rax
  HSTRING v47; // rcx
  const unsigned __int16 *v48; // r8
  struct IInspectable *v49; // rax
  const unsigned __int16 *v50; // r8
  const unsigned __int16 *v51; // r8
  SystemSettings::StorageSenseHandlers::CAppTileData *v52; // rbx
  int v53; // eax
  void (__fastcall *v54)(SystemSettings::StorageSenseHandlers::CPackageSizeSetting *, HSTRING *); // rbx
  const struct _tlgProvider_t *v55; // rax
  int v56; // ebx
  int v57; // r8d
  int v58; // r9d
  unsigned int v60; // eax
  void *v61; // rdx
  unsigned int v62; // r8d
  int lpDateStr; // [rsp+20h] [rbp-E0h]
  HSTRING v64; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  ULONGLONG ull; // [rsp+50h] [rbp-B0h] BYREF
  SYSTEMTIME Date; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszBuf[64]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR DateStr[152]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR LCData[152]; // [rsp+220h] [rbp+120h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+298h]

  *a3 = 0;
  ull = 0;
  if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010A898, (const unsigned __int16 *)a3) )
  {
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180109340, v6) )
    {
      string = 0;
      v16 = (SystemSettings::StorageSenseHandlers::CAppTileData *)*((_QWORD *)this + 30);
      WindowsDeleteString(0);
      string = 0;
      Publisher = SystemSettings::StorageSenseHandlers::CAppTileData::GetPublisher(v16, &string);
      if ( Publisher >= 0 )
        Publisher = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
LABEL_88:
      v47 = string;
LABEL_105:
      WindowsDeleteString(v47);
      goto LABEL_108;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)L"InstallDate", v15) )
    {
      v64 = 0;
      InstallDate = SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetInstallDate(this);
      memset_0(LCData, 0, 0x12Cu);
      memset_0(DateStr, 0, 0x12Cu);
      Date = 0;
      Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v64, &word_180106450, 0);
      if ( InstallDate )
      {
        Date.wDay = InstallDate % 0x64;
        Date.wMonth = InstallDate / 0x64 % 0x64;
        Date.wYear = InstallDate / 0x2710 % 0x2710;
        if ( GetLocaleInfoEx(0, 0x1Fu, LCData, 150) )
        {
          if ( GetDateFormatEx(0, 0x40u, &Date, LCData, DateStr, 150, 0) )
            goto LABEL_24;
        }
        LastError = GetLastError();
        v20 = LastError < 0;
        if ( LastError > 0 )
          v20 = 1;
        if ( !v20 )
        {
LABEL_24:
          LODWORD(string) = 0;
          v21 = -1;
          do
            ++v21;
          while ( DateStr[v21] );
          if ( (int)ULongLongToUInt(v21, (unsigned int *)&string) >= 0 )
            Microsoft::WRL::Wrappers::HString::Set(
              (Microsoft::WRL::Wrappers::HString *)&v64,
              DateStr,
              (unsigned int)string);
        }
      }
      Publisher = SystemSettings::DataModel::PropValueHelper::CreateString(v64, a3);
LABEL_104:
      v47 = v64;
      goto LABEL_105;
    }
    Publisher = -2147024809;
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010A8B0, v17) )
    {
      v23 = (char *)this + 256;
      goto LABEL_31;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010A900, v22) )
    {
      v23 = (char *)this + 264;
      goto LABEL_31;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010A8E0, v24) )
    {
      v23 = (char *)this + 272;
      goto LABEL_31;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010A958, v25) )
    {
      v23 = (char *)this + 280;
LABEL_31:
      if ( *(_QWORD *)v23 )
      {
        Double = Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppOperationSetting>::CopyTo<IInspectable>(
                   v23,
                   (__int64)a3);
        goto LABEL_107;
      }
      goto LABEL_109;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010A920, v26) )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59787121>::GetImpl'::`2'::impl) )
        goto LABEL_109;
      v23 = (char *)this + 288;
      goto LABEL_31;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010A990, v27) )
    {
      v29 = *((_BYTE *)this + 248);
      goto LABEL_44;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010A978, v28) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59787121>::GetImpl'::`2'::impl) )
      {
        v29 = *((_BYTE *)this + 249);
        goto LABEL_44;
      }
LABEL_48:
      v29 = 0;
      goto LABEL_44;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010A9D8, v30) )
    {
      if ( *((_BYTE *)this + 250) )
        v32 = DOUBLE_1_0;
      else
        v32 = DOUBLE_0_2;
      Double = SystemSettings::DataModel::PropValueHelper::CreateDouble(v32, a3);
      goto LABEL_107;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010A9B0, v31) )
    {
      v29 = *((_BYTE *)this + 312);
      goto LABEL_44;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010AA30, v33) )
    {
LABEL_57:
      if ( !*((_BYTE *)this + 312) || *((_BYTE *)this + 248) )
        goto LABEL_48;
LABEL_59:
      v29 = 1;
      goto LABEL_44;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010A9F0, v34) )
    {
      if ( SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageOrigin(*((SystemSettings::StorageSenseHandlers::CAppTileData **)this
                                                                                + 30)) == PackageOrigin_Inbox )
        goto LABEL_59;
      goto LABEL_57;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010AA90, v35) )
    {
      Double = SystemSettings::DataModel::PropValueHelper::CreateUInt32(*((_DWORD *)this + 77), a3);
      goto LABEL_107;
    }
    if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010AA68, v36) )
    {
      if ( !IsDesktopSKU() && SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180108C20, v44) )
      {
        string = 0;
        v45 = (SystemSettings::StorageSenseHandlers::CAppTileData *)*((_QWORD *)this + 30);
        WindowsDeleteString(0);
        string = 0;
        Publisher = SystemSettings::StorageSenseHandlers::CAppTileData::GetLogoPath(v45, &string);
        if ( Publisher >= 0 )
        {
          v64 = 0;
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v64);
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          Publisher = CreateRandomAccessStreamOnFile(
                        StringRawBuffer,
                        0,
                        &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da,
                        &v64);
          if ( Publisher >= 0 )
            Publisher = (**(__int64 (__fastcall ***)(HSTRING, GUID *, struct IInspectable **))v64)(
                          v64,
                          &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                          a3);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v64);
        }
        goto LABEL_88;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180108C70, v44) )
      {
        string = 0;
        v64 = 0;
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&string);
        ull = *((_QWORD *)this + 30);
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&ull);
        Publisher = SystemSettings::StorageSenseHandlers::CAppAdvancedInfoDynamicDatabase::CreateInstance(&ull, &string);
        if ( Publisher >= 0 )
        {
          Publisher = Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CStorageSenseDynamicDatabase>::As<IInspectable>(
                        (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&string,
                        (__int64)&v64);
          if ( Publisher >= 0 )
          {
            v49 = (struct IInspectable *)v64;
            v64 = 0;
            *a3 = v49;
          }
        }
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v64);
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&string);
LABEL_108:
        if ( Publisher >= 0 )
          return (unsigned int)Publisher;
        goto LABEL_109;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010AD80, v48) )
      {
        v29 = SystemSettings::StorageSenseHandlers::CAppTileData::AreAdvancedOptionsSupported(*((SystemSettings::StorageSenseHandlers::CAppTileData **)this
                                                                                              + 30));
      }
      else
      {
        if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010AD68, v50) )
        {
          if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010ADD0, v51) )
          {
            Double = SystemSettings::StorageSenseHandlers::CAppTileData::GetNamedValue(
                       *((SystemSettings::StorageSenseHandlers::CAppTileData **)this + 30),
                       (HSTRING)a2,
                       a3);
            goto LABEL_107;
          }
          v64 = 0;
          if ( *((_BYTE *)this + 248)
            && (v52 = (SystemSettings::StorageSenseHandlers::CAppTileData *)*((_QWORD *)this + 30),
                WindowsDeleteString(0),
                v64 = 0,
                SystemSettings::StorageSenseHandlers::CAppTileData::GetVersionNumber(v52, &v64) >= 0) )
          {
            v53 = SystemSettings::DataModel::PropValueHelper::CreateString(v64, a3);
          }
          else
          {
            v53 = SystemSettings::DataModel::PropValueHelper::CreateString(&word_180106450, a3);
          }
          Publisher = v53;
          goto LABEL_104;
        }
        v29 = *((_DWORD *)this + 63) != 0;
      }
LABEL_44:
      Double = SystemSettings::DataModel::PropValueHelper::CreateBoolean(v29, a3);
      goto LABEL_107;
    }
    v37 = *((_DWORD *)this + 79);
    if ( !v37 )
    {
      v42 = L"SystemSettings_StorageSense_App_Sizes_List_Moved";
      if ( *((_DWORD *)this + 77) != 100 )
        v42 = L"SystemSettings_StorageSense_App_Sizes_List_Moving";
      goto LABEL_81;
    }
    v38 = v37 - 1;
    if ( v38 )
    {
      v39 = v38 - 1;
      if ( v39 )
      {
        v40 = v39 - 1;
        if ( v40 )
        {
          v41 = v40 - 1;
          if ( v41 )
          {
            if ( v41 != 1
              || !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59787121>::GetImpl'::`2'::impl) )
            {
              v60 = wil::verify_hresult<long>(2147549183LL);
              wil::details::in1diag3::FailFast_Hr(retaddr, v61, v62, (const char *)v60, lpDateStr);
            }
          }
        }
        v42 = &word_180106450;
LABEL_81:
        v13 = (WCHAR *)v42;
        goto LABEL_10;
      }
      v43 = L"SystemSettings_StorageSense_App_Sizes_List_Modifying";
      v42 = L"SystemSettings_StorageSense_App_Sizes_List_Modified";
    }
    else
    {
      v43 = L"SystemSettings_StorageSense_App_Sizes_List_Uninstalling";
      v42 = L"SystemSettings_StorageSense_App_Sizes_List_Uninstalled";
    }
    if ( *((_DWORD *)this + 77) != 100 )
      v42 = v43;
    goto LABEL_81;
  }
  if ( (int)SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetPackageSize(this, 0, &ull) < 0 )
  {
    v7 = SystemSettings::StorageSenseHandlers::CPackageSizeSetting::_packageSizeLoadingString;
    if ( SystemSettings::StorageSenseHandlers::CPackageSizeSetting::_packageSizeLoadingString
      || (WindowsDeleteString(0),
          SystemSettings::StorageSenseHandlers::CPackageSizeSetting::_packageSizeLoadingString = 0,
          SystemSettings::DataModel::GetResourceStringById(
            (SystemSettings::DataModel *)L"SystemSettings_StorageSense_App_Sizes_List_Size_Calculating",
            &SystemSettings::StorageSenseHandlers::CPackageSizeSetting::_packageSizeLoadingString,
            v8),
          (v7 = SystemSettings::StorageSenseHandlers::CPackageSizeSetting::_packageSizeLoadingString) != 0) )
    {
      v9 = WindowsGetStringRawBuffer(v7, 0);
    }
    else
    {
      v9 = &word_180106450;
    }
    Publisher = SystemSettings::DataModel::PropValueHelper::CreateString(v9, a3);
    SystemSettings::StorageSenseHandlers::CSizeCalculationThreadPool::SubmitPackage(v11, this);
    goto LABEL_108;
  }
  v12 = ull;
  if ( !ull )
  {
    v13 = (WCHAR *)&word_180106450;
LABEL_10:
    Double = SystemSettings::DataModel::PropValueHelper::CreateString(v13, a3);
LABEL_107:
    Publisher = Double;
    goto LABEL_108;
  }
  memset_0(pszBuf, 0, sizeof(pszBuf));
  Publisher = StrFormatByteSizeEx(v12, 1, pszBuf, 0x40u);
  if ( Publisher >= 0 )
  {
    v13 = pszBuf;
    goto LABEL_10;
  }
LABEL_109:
  v64 = 0;
  v54 = *(void (__fastcall **)(SystemSettings::StorageSenseHandlers::CPackageSizeSetting *, HSTRING *))(*(_QWORD *)this + 48LL);
  WindowsDeleteString(0);
  v64 = 0;
  v54(this, &v64);
  v55 = SettingsHandlersStorageSenseLogging::Provider();
  v56 = (int)v55;
  if ( *(_DWORD *)v55 > 2u )
  {
    LODWORD(string) = Publisher;
    ull = (ULONGLONG)WindowsGetStringRawBuffer(v64, 0);
    *(_QWORD *)&Date.wYear = WindowsGetStringRawBuffer((HSTRING)a2, 0);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v56,
      (unsigned int)&unk_18014FD08,
      v57,
      v58,
      (__int64)&Date,
      (__int64)&ull,
      (__int64)&string);
  }
  WindowsDeleteString(v64);
  return (unsigned int)Publisher;
}

```

## disassembly

```asm
0x180041bc0  push    rbp
0x180041bc2  push    rbx
0x180041bc3  push    rsi
0x180041bc4  push    rdi
0x180041bc5  push    r12
0x180041bc7  push    r14
0x180041bc9  push    r15
0x180041bcb  lea     rbp, [rsp-260h]
0x180041bd3  sub     rsp, 360h
0x180041bda  mov     rax, cs:__security_cookie
0x180041be1  xor     rax, rsp
0x180041be4  mov     [rbp+290h+var_40], rax
0x180041beb  mov     rsi, r8
0x180041bee  mov     r15, rdx
0x180041bf1  mov     r14, rcx
0x180041bf4  xor     r12d, r12d
0x180041bf7  mov     [r8], r12
0x180041bfa  mov     [rsp+390h+ull], r12
0x180041bff  lea     rdx, stru_18010A898; HSTRING
0x180041c06  mov     rcx, r15; this
0x180041c09  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180041c0e  test    al, al
0x180041c10  jz      loc_180041CE5
0x180041c16  lea     r8, [rsp+390h+ull]; unsigned __int64 *
0x180041c1b  xor     edx, edx; bool
0x180041c1d  mov     rcx, r14; this
0x180041c20  call    ?GetPackageSize@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@QEAAJ_NPEA_K@Z; SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetPackageSize(bool,unsigned __int64 *)
0x180041c25  test    eax, eax
0x180041c27  jns     short loc_180041C8C
0x180041c29  mov     rcx, cs:?_packageSizeLoadingString@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@0VHString@Wrappers@WRL@Microsoft@@A; string
0x180041c30  test    rcx, rcx
0x180041c33  jnz     short loc_180041C61
0x180041c35  call    cs:__imp_WindowsDeleteString
0x180041c3b  mov     cs:?_packageSizeLoadingString@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@0VHString@Wrappers@WRL@Microsoft@@A, r12; Microsoft::WRL::Wrappers::HString SystemSettings::StorageSenseHandlers::CPackageSizeSetting::_packageSizeLoadingString
0x180041c42  lea     rdx, ?_packageSizeLoadingString@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@0VHString@Wrappers@WRL@Microsoft@@A; HSTRING *
0x180041c49  lea     rcx, aSystemsettings_363; "SystemSettings_StorageSense_App_Sizes_L"...
0x180041c50  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180041c55  mov     rcx, cs:?_packageSizeLoadingString@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@0VHString@Wrappers@WRL@Microsoft@@A; string
0x180041c5c  test    rcx, rcx
0x180041c5f  jz      short loc_180041C6B
0x180041c61  xor     edx, edx; length
0x180041c63  call    cs:__imp_WindowsGetStringRawBuffer
0x180041c69  jmp     short loc_180041C72
0x180041c6b  lea     rax, word_180106450
0x180041c72  mov     rdx, rsi; struct IInspectable **
0x180041c75  mov     rcx, rax; unsigned __int16 *
0x180041c78  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180041c7d  mov     edi, eax
0x180041c7f  mov     rdx, r14; struct SystemSettings::StorageSenseHandlers::CPackageSizeSetting *
0x180041c82  call    ?SubmitPackage@CSizeCalculationThreadPool@StorageSenseHandlers@SystemSettings@@QEAAXPEAVCPackageSizeSetting@23@@Z; SystemSettings::StorageSenseHandlers::CSizeCalculationThreadPool::SubmitPackage(SystemSettings::StorageSenseHandlers::CPackageSizeSetting *)
0x180041c87  jmp     loc_18004236A
0x180041c8c  mov     rbx, [rsp+390h+ull]
0x180041c91  test    rbx, rbx
0x180041c94  jnz     short loc_180041CAA
0x180041c96  lea     rcx, word_180106450; unsigned __int16 *
0x180041c9d  mov     rdx, rsi; struct IInspectable **
0x180041ca0  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180041ca5  jmp     loc_180042368
0x180041caa  xor     edx, edx; Val
0x180041cac  mov     r8d, 80h; Size
0x180041cb2  lea     rcx, [rsp+390h+pszBuf]; void *
0x180041cb7  call    memset_0
0x180041cbc  mov     r9d, 40h ; '@'; cchBuf
0x180041cc2  lea     r8, [rsp+390h+pszBuf]; pszBuf
0x180041cc7  lea     edx, [r9-3Fh]; flags
0x180041ccb  mov     rcx, rbx; ull
0x180041cce  call    cs:__imp_StrFormatByteSizeEx
0x180041cd4  mov     edi, eax
0x180041cd6  test    eax, eax
0x180041cd8  js      loc_180042372
0x180041cde  lea     rcx, [rsp+390h+pszBuf]
0x180041ce3  jmp     short loc_180041C9D
0x180041ce5  lea     rdx, stru_180109340; HSTRING
0x180041cec  mov     rcx, r15; this
0x180041cef  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180041cf4  test    al, al
0x180041cf6  jz      short loc_180041D38
0x180041cf8  mov     [rsp+390h+string], r12
0x180041cfd  mov     rbx, [r14+0F0h]
0x180041d04  xor     ecx, ecx; string
0x180041d06  call    cs:__imp_WindowsDeleteString
0x180041d0c  mov     [rsp+390h+string], r12
0x180041d11  lea     rdx, [rsp+390h+string]; HSTRING *
0x180041d16  mov     rcx, rbx; this
0x180041d19  call    ?GetPublisher@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetPublisher(HSTRING__ * *)
0x180041d1e  mov     edi, eax
0x180041d20  test    eax, eax
0x180041d22  js      short loc_180041D33
0x180041d24  mov     rdx, rsi; struct IInspectable **
0x180041d27  mov     rcx, [rsp+390h+string]; HSTRING
0x180041d2c  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x180041d31  mov     edi, eax
0x180041d33  jmp     loc_180042201
0x180041d38  lea     rdx, aInstalldate; "InstallDate"
0x180041d3f  mov     rcx, r15; this
0x180041d42  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180041d47  test    al, al
0x180041d49  jz      loc_180041EB7
0x180041d4f  mov     [rsp+390h+var_350], r12
0x180041d54  mov     rcx, r14; this
0x180041d57  call    ?GetInstallDate@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@QEAAIXZ; SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetInstallDate(void)
0x180041d5c  mov     ebx, eax
0x180041d5e  mov     edi, 12Ch
0x180041d63  mov     r8d, edi; Size
0x180041d66  xor     edx, edx; Val
0x180041d68  lea     rcx, [rbp+290h+LCData]; void *
0x180041d6f  call    memset_0
0x180041d74  mov     r8d, edi; Size
0x180041d77  xor     edx, edx; Val
0x180041d79  lea     rcx, [rbp+290h+DateStr]; void *
0x180041d7d  call    memset_0
0x180041d82  xorps   xmm0, xmm0
0x180041d85  movups  xmmword ptr [rsp+390h+Date.wYear], xmm0
0x180041d8a  xor     r8d, r8d; unsigned int
0x180041d8d  lea     rdx, word_180106450; unsigned __int16 *
0x180041d94  lea     rcx, [rsp+390h+var_350]; this
0x180041d99  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180041d9e  test    ebx, ebx
0x180041da0  jz      loc_180041EA3
0x180041da6  mov     r10d, 51EB851Fh
0x180041dac  mov     eax, r10d
0x180041daf  mul     ebx
0x180041db1  mov     r9d, edx
0x180041db4  shr     r9d, 5
0x180041db8  movzx   ecx, r9w
0x180041dbc  imul    r8d, ecx, 64h ; 'd'
0x180041dc0  movzx   ecx, bx
0x180041dc3  sub     cx, r8w
0x180041dc7  mov     [rsp+390h+Date.wDay], cx
0x180041dcc  mov     eax, r10d
0x180041dcf  mul     r9d
0x180041dd2  shr     edx, 5
0x180041dd5  movzx   eax, dx
0x180041dd8  imul    ecx, eax, 64h ; 'd'
0x180041ddb  sub     r9w, cx
0x180041ddf  mov     [rsp+390h+Date.wMonth], r9w
0x180041de5  mov     r8d, 0D1B71759h
0x180041deb  mov     eax, r8d
0x180041dee  mul     ebx
0x180041df0  mov     ecx, edx
0x180041df2  shr     ecx, 0Dh
0x180041df5  mov     eax, r8d
0x180041df8  mul     ecx
0x180041dfa  shr     edx, 0Dh
0x180041dfd  imul    eax, edx, 2710h
0x180041e03  sub     ecx, eax
0x180041e05  mov     [rsp+390h+Date.wYear], cx
0x180041e0a  mov     ebx, 96h
0x180041e0f  mov     r9d, ebx; cchData
0x180041e12  lea     r8, [rbp+290h+LCData]; lpLCData
0x180041e19  lea     edx, [rbx-77h]; LCType
0x180041e1c  xor     ecx, ecx; lpLocaleName
0x180041e1e  call    cs:__imp_GetLocaleInfoEx
0x180041e24  test    eax, eax
0x180041e26  jz      short loc_180041E55
0x180041e28  mov     [rsp+390h+lpCalendar], r12; lpCalendar
0x180041e2d  mov     [rsp+390h+cchDate], ebx; cchDate
0x180041e31  lea     rax, [rbp+290h+DateStr]
0x180041e35  mov     [rsp+390h+lpDateStr], rax; lpDateStr
0x180041e3a  lea     r9, [rbp+290h+LCData]; lpFormat
0x180041e41  lea     r8, [rsp+390h+Date]; lpDate
0x180041e46  lea     edx, [rbx-56h]; dwFlags
0x180041e49  xor     ecx, ecx; lpLocaleName
0x180041e4b  call    cs:__imp_GetDateFormatEx
0x180041e51  test    eax, eax
0x180041e53  jnz     short loc_180041E6B
0x180041e55  call    cs:__imp_GetLastError
0x180041e5b  test    eax, eax
0x180041e5d  jle     short loc_180041E69
0x180041e5f  movzx   eax, ax
0x180041e62  or      eax, 80070000h
0x180041e67  test    eax, eax
0x180041e69  js      short loc_180041EA3
0x180041e6b  mov     dword ptr [rsp+390h+string], r12d
0x180041e70  lea     rax, [rbp+290h+DateStr]
0x180041e74  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180041e78  inc     rcx; unsigned __int64
0x180041e7b  cmp     [rax+rcx*2], r12w
0x180041e80  jnz     short loc_180041E78
0x180041e82  lea     rdx, [rsp+390h+string]; unsigned int *
0x180041e87  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180041e8c  test    eax, eax
0x180041e8e  js      short loc_180041EA3
0x180041e90  mov     r8d, dword ptr [rsp+390h+string]; unsigned int
0x180041e95  lea     rdx, [rbp+290h+DateStr]; unsigned __int16 *
0x180041e99  lea     rcx, [rsp+390h+var_350]; this
0x180041e9e  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180041ea3  mov     rdx, rsi; struct IInspectable **
0x180041ea6  mov     rcx, [rsp+390h+var_350]; HSTRING
0x180041eab  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x180041eb0  mov     edi, eax
0x180041eb2  jmp     loc_180042349
0x180041eb7  mov     edi, 80070057h
0x180041ebc  lea     rdx, stru_18010A8B0; HSTRING
0x180041ec3  mov     rcx, r15; this
0x180041ec6  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180041ecb  test    al, al
0x180041ecd  jz      short loc_180041EEC
0x180041ecf  lea     rcx, [r14+100h]
0x180041ed6  cmp     [rcx], r12
0x180041ed9  jz      loc_180042372
0x180041edf  mov     rdx, rsi
0x180041ee2  call    ??$CopyTo@UIInspectable@@@?$ComPtr@VCAppOperationSetting@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@QEBAJPEAPEAUIInspectable@@@Z; Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppOperationSetting>::CopyTo<IInspectable>(IInspectable * *)
0x180041ee7  jmp     loc_180042368
0x180041eec  lea     rdx, stru_18010A900; HSTRING
0x180041ef3  mov     rcx, r15; this
0x180041ef6  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180041efb  test    al, al
0x180041efd  jz      short loc_180041F08
0x180041eff  lea     rcx, [r14+108h]
0x180041f06  jmp     short loc_180041ED6
0x180041f08  lea     rdx, stru_18010A8E0; HSTRING
0x180041f0f  mov     rcx, r15; this
0x180041f12  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180041f17  test    al, al
0x180041f19  jz      short loc_180041F24
0x180041f1b  lea     rcx, [r14+110h]
0x180041f22  jmp     short loc_180041ED6
0x180041f24  lea     rdx, stru_18010A958; HSTRING
0x180041f2b  mov     rcx, r15; this
0x180041f2e  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180041f33  test    al, al
0x180041f35  jz      short loc_180041F40
0x180041f37  lea     rcx, [r14+118h]
0x180041f3e  jmp     short loc_180041ED6
0x180041f40  lea     rdx, stru_18010A920; HSTRING
0x180041f47  mov     rcx, r15; this
0x180041f4a  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180041f4f  test    al, al
0x180041f51  jz      short loc_180041F73
0x180041f53  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59787121@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59787121@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121> `wil::Feature<__WilFeatureTraits_Feature_ID59787121>::GetImpl(void)'::`2'::impl
0x180041f5a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59787121@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121>::__private_IsEnabled(void)
0x180041f5f  test    al, al
0x180041f61  jz      loc_180042372
0x180041f67  lea     rcx, [r14+120h]
0x180041f6e  jmp     loc_180041ED6
0x180041f73  lea     rdx, stru_18010A990; HSTRING
0x180041f7a  mov     rcx, r15; this
0x180041f7d  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180041f82  test    al, al
0x180041f84  jz      short loc_180041F9A
0x180041f86  mov     cl, [r14+0F8h]; unsigned __int8
0x180041f8d  mov     rdx, rsi; struct IInspectable **
0x180041f90  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x180041f95  jmp     loc_180042368
0x180041f9a  lea     rdx, stru_18010A978; HSTRING
0x180041fa1  mov     rcx, r15; this
0x180041fa4  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180041fa9  test    al, al
0x180041fab  jz      short loc_180041FCB
0x180041fad  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59787121@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59787121@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121> `wil::Feature<__WilFeatureTraits_Feature_ID59787121>::GetImpl(void)'::`2'::impl
0x180041fb4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59787121@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121>::__private_IsEnabled(void)
0x180041fb9  test    al, al
0x180041fbb  jz      short loc_180041FC6
0x180041fbd  mov     cl, [r14+0F9h]
0x180041fc4  jmp     short loc_180041F8D
0x180041fc6  mov     cl, r12b
0x180041fc9  jmp     short loc_180041F8D
0x180041fcb  lea     rdx, stru_18010A9D8; HSTRING
0x180041fd2  mov     rcx, r15; this
0x180041fd5  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180041fda  test    al, al
0x180041fdc  jz      short loc_180042008
0x180041fde  mov     al, [r14+0FAh]
0x180041fe5  test    al, al
0x180041fe7  jz      short loc_180041FF3
0x180041fe9  movsd   xmm0, cs:__real@3ff0000000000000
0x180041ff1  jmp     short loc_180041FFB
0x180041ff3  movsd   xmm0, cs:__real@3fc999999999999a; double
0x180041ffb  mov     rdx, rsi; struct IInspectable **
0x180041ffe  call    ?CreateDouble@PropValueHelper@DataModel@SystemSettings@@SAJNPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateDouble(double,IInspectable * *)
0x180042003  jmp     loc_180042368
0x180042008  lea     rdx, stru_18010A9B0; HSTRING
0x18004200f  mov     rcx, r15; this
0x180042012  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180042017  test    al, al
0x180042019  jz      short loc_180042027
0x18004201b  mov     cl, [r14+138h]
0x180042022  jmp     loc_180041F8D
0x180042027  lea     rdx, stru_18010AA30; HSTRING
0x18004202e  mov     rcx, r15; this
0x180042031  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180042036  test    al, al
0x180042038  jz      short loc_18004205C
0x18004203a  mov     al, [r14+138h]
0x180042041  test    al, al
0x180042043  jz      short loc_180041FC6
0x180042045  cmp     [r14+0F8h], r12b
0x18004204c  jnz     loc_180041FC6
0x180042052  mov     ecx, 1
0x180042057  jmp     loc_180041F8D
0x18004205c  lea     rdx, stru_18010A9F0; HSTRING
0x180042063  mov     rcx, r15; this
0x180042066  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004206b  test    al, al
0x18004206d  jz      short loc_180042082
0x18004206f  mov     rcx, [r14+0F0h]; this
0x180042076  call    ?GetPackageOrigin@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAA?AW4PackageOrigin@StateRepository@Internal@Windows@@XZ; SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageOrigin(void)
0x18004207b  cmp     eax, 2
0x18004207e  jnz     short loc_18004203A
  ... truncated ...
```
