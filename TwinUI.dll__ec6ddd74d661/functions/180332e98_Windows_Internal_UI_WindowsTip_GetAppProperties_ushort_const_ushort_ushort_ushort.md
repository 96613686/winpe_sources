# Windows::Internal::UI::WindowsTip::GetAppProperties(ushort const *,ushort * *,ushort * *,ushort * *)

- ea: `0x180332e98`
- end: `0x1803336a8`
- name: `?GetAppProperties@WindowsTip@UI@Internal@Windows@@YAJPEBGPEAPEAG11@Z`
- size: `2064`
- prototype: `__int64 __fastcall(Windows::Internal::UI::WindowsTip *__hidden this, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180336280`

## callees

- `0x180009dd0`
- `0x180009dfc`
- `0x18000e2b0`
- `0x18000e498`
- `0x18001c710`
- `0x1800378dc`
- `0x180041d1c`
- `0x180041f54`
- `0x180053740`
- `0x180055268`
- `0x180142e10`
- `0x1802542ec`
- `0x18032fd5c`
- `0x18032fde4`
- `0x1803300b8`
- `0x180331024`
- `0x180332e98`
- `0x180336124`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803331f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180333239`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803333f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180333439`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033345d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803334a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803335d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803335ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180333624`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803331f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180333239`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803333f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180333439`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033345d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803334a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803335d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803335ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180333624`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033325f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803334df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033353a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033325f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803334df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033353a`

## string_xrefs

- `0x18033350f`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::UI::WindowsTip::GetAppProperties(
        Windows::Internal::UI::WindowsTip *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, __int64, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rdx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r9
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, _QWORD, __int64 *); // rbx
  __int64 v25; // rax
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64, __int64 *); // rbx
  __int64 v28; // rbx
  __int64 (__fastcall *v29)(__int64, __int64 *); // rdi
  int v30; // eax
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, HSTRING *); // rbx
  int v33; // eax
  PCWSTR StringRawBuffer; // rax
  int v35; // eax
  __int64 v36; // rdx
  int v37; // eax
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, __int64 *); // rbx
  int v40; // eax
  __int64 v41; // rdi
  __int64 (__fastcall *v42)(__int64, __int64 *); // rbx
  int v43; // eax
  __int64 v44; // rdi
  __int64 (__fastcall *v45)(__int64, HSTRING *); // rbx
  int v46; // eax
  __int64 v47; // rdi
  __int64 (__fastcall *v48)(__int64, HSTRING *); // rbx
  int v49; // eax
  PCWSTR v50; // rax
  int v51; // eax
  const unsigned __int16 *v52; // rax
  int v53; // eax
  __int64 v54; // rax
  unsigned __int16 *Reserved1; // rax
  unsigned __int16 *v56; // rax
  int v58; // [rsp+20h] [rbp-E0h]
  int v59; // [rsp+20h] [rbp-E0h]
  __int64 v60; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v62; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v63; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v64; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v65; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v66; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v67; // [rsp+68h] [rbp-98h] BYREF
  int v68; // [rsp+70h] [rbp-90h] BYREF
  HSTRING v69; // [rsp+78h] [rbp-88h] BYREF
  HSTRING v70; // [rsp+80h] [rbp-80h] BYREF
  __int64 v71; // [rsp+88h] [rbp-78h] BYREF
  __int64 v72; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v73; // [rsp+98h] [rbp-68h] BYREF
  __int64 v74; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v75; // [rsp+A8h] [rbp-58h]
  __int64 v76; // [rsp+B0h] [rbp-50h]
  __int64 v77; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v78; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v79; // [rsp+D0h] [rbp-30h]
  __int128 v80; // [rsp+D8h] [rbp-28h]
  __int64 v81; // [rsp+E8h] [rbp-18h]
  _OWORD v82[3]; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+120h] [rbp+20h] BYREF
  __int64 v84; // [rsp+138h] [rbp+38h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v73 = (unsigned __int16 *)this;
  *(_QWORD *)a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v77 = 0;
  v84 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"WindowsInternal.Shell.UnifiedTile.UnifiedTileManager",
    0x35u,
    0x34u);
  v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerStatics>>(
         v84,
         &v77);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v60 = 0;
    v9 = v77;
    v10 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v77 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
    v11 = v10(v9, 3, 1, &v60);
    v8 = v11;
    if ( v11 < 0 )
    {
      v12 = 827;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v11,
        v58);
LABEL_6:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
      goto LABEL_61;
    }
    v11 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *>,Windows::Foundation::IAsyncOperation<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *>>(v60);
    v8 = v11;
    if ( v11 < 0 )
    {
      v12 = 828;
      goto LABEL_5;
    }
    v62 = 0;
    v13 = v60;
    v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v60 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
    v15 = v14(v13, &v62);
    v8 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x33F,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v15,
        v58);
LABEL_11:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
      goto LABEL_6;
    }
    v63 = 0;
    v16 = v62;
    v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v62 + 80LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v63);
    v18 = v17(v16, &v63);
    v8 = v18;
    if ( v18 < 0 )
    {
      v19 = 834;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v18,
        v58);
LABEL_15:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v63);
      goto LABEL_11;
    }
    v18 = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
            v63,
            0xFFFFFFFFLL);
    v8 = v18;
    if ( v18 < 0 )
    {
      v19 = 835;
      goto LABEL_14;
    }
    v64 = 0;
    v65 = 0;
    v66 = 0;
    v84 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"WindowsInternal.Shell.UnifiedTile.PackagedUnifiedTileIdentifier",
      0x40u,
      0x3Fu);
    v20 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifierFactory>>(
            v84,
            &v66);
    v8 = v20;
    if ( v20 < 0 )
    {
      v21 = 841;
LABEL_20:
      v22 = (unsigned int)v20;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)v22,
        v58);
LABEL_22:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
      goto LABEL_15;
    }
    v23 = v66;
    v24 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v66 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
    v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v73);
    v20 = v24(v23, *(_QWORD *)(v25 + 24), &v65);
    v8 = v20;
    if ( v20 < 0 )
    {
      v21 = 843;
      goto LABEL_20;
    }
    v26 = v62;
    v27 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v62 + 72LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
    v20 = v27(v26, v65, &v64);
    v8 = v20;
    if ( v20 < 0 )
    {
      v21 = 844;
      goto LABEL_20;
    }
    v28 = v64;
    if ( !v64 )
    {
      v8 = -2147023728;
      v22 = 2147943568LL;
      v21 = 845;
      goto LABEL_21;
    }
    v67 = 0;
    v29 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v64 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
    v30 = v29(v28, &v67);
    v8 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x350,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v30,
        v58);
LABEL_31:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
      goto LABEL_22;
    }
    string = 0;
    v31 = v67;
    v32 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v67 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v33 = v32(v31, &string);
    v8 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x353,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v33,
        v58);
LABEL_34:
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_31;
    }
    v74 = 0;
    v75 = 0;
    v76 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v35 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            &v74,
            StringRawBuffer,
            -1);
    v8 = v35;
    if ( v35 >= 0 )
    {
      v68 = 0;
      v35 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v67 + 72LL))(v67, &v68);
      v8 = v35;
      if ( v35 >= 0 )
      {
        memset(&hstringHeader, 0, sizeof(hstringHeader));
        v59 = BYTE2(v68);
        v37 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                &hstringHeader,
                L"#%02x%02x%02x%02x",
                (unsigned __int8)v68,
                BYTE1(v68));
        v8 = v37;
        if ( v37 >= 0 )
        {
          v71 = 0;
          v38 = v64;
          v39 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v64 + 104LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
          v40 = v39(v38, &v71);
          v8 = v40;
          if ( v40 >= 0 )
          {
            v72 = 0;
            v41 = v67;
            v42 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v67 + 64LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
            v43 = v42(v41, &v72);
            v8 = v43;
            if ( v43 >= 0 )
            {
              v69 = 0;
              v44 = v72;
              v45 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v72 + 64LL);
              WindowsDeleteString(0);
              v69 = 0;
              v46 = v45(v44, &v69);
              v8 = v46;
              if ( v46 >= 0 )
              {
                v70 = 0;
                v47 = v71;
                v48 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v71 + 56LL);
                WindowsDeleteString(0);
                v70 = 0;
                v49 = v48(v47, &v70);
                v8 = v49;
                if ( v49 >= 0 )
                {
                  v78 = 0;
                  v79 = 0;
                  v80 = 0;
                  v81 = 0;
                  memset(v82, 0, sizeof(v82));
                  v50 = WindowsGetStringRawBuffer(v70, 0);
                  *(_WORD *)((char *)&v81 + 5) = 1;
                  v51 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                          v82,
                          v50,
                          -1);
                  if ( v51 < 0 )
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x30,
                      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
                      (const char *)(unsigned int)v51,
                      v59);
                  HIBYTE(v81) = 1;
                  v73 = 0;
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                    &v73,
                    0);
                  v52 = WindowsGetStringRawBuffer(v69, 0);
                  v53 = ShellMRTHelper::MRTHelperBase::ResolvePath((ShellMRTHelper::MRTHelperBase *)&v78, v52, &v73);
                  v8 = v53;
                  if ( v53 >= 0 )
                  {
                    v54 = v74;
                    v74 = 0;
                    v76 = 0;
                    v75 = 0;
                    *(_QWORD *)a2 = v54;
                    Reserved1 = (unsigned __int16 *)hstringHeader.Reserved.Reserved1;
                    memset(&hstringHeader, 0, sizeof(hstringHeader));
                    *a4 = Reserved1;
                    v56 = v73;
                    v73 = 0;
                    *a3 = v56;
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v73);
                    ShellMRTHelper::MRTHelperBase::~MRTHelperBase((ShellMRTHelper::MRTHelperBase *)&v78);
                    WindowsDeleteString(v70);
                    v70 = 0;
                    WindowsDeleteString(v69);
                    v69 = 0;
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
                    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
                    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v74);
                    WindowsDeleteString(string);
                    string = 0;
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
                    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v63);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
                    v8 = 0;
                    goto LABEL_61;
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x370,
                    (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
                    (const char *)(unsigned int)v53,
                    v59);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v73);
                  ShellMRTHelper::MRTHelperBase::~MRTHelperBase((ShellMRTHelper::MRTHelperBase *)&v78);
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x369,
                    (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
                    (const char *)(unsigned int)v49,
                    v59);
                }
                WindowsDeleteString(v70);
                v70 = 0;
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x366,
                  (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
                  (const char *)(unsigned int)v46,
                  v59);
              }
              WindowsDeleteString(v69);
              v69 = 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x363,
                (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
                (const char *)(unsigned int)v43,
                v59);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x35F,
              (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
              (const char *)(unsigned int)v40,
              v59);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x35C,
            (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
            (const char *)(unsigned int)v37,
            v59);
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
        goto LABEL_38;
      }
      v36 = 857;
    }
    else
    {
      v36 = 854;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v36,
      (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
      (const char *)(unsigned int)v35,
      v58);
LABEL_38:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v74);
    goto LABEL_34;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x338,
    (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
    (const char *)(unsigned int)v7,
    v58);
LABEL_61:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
  return v8;
}

```

## disassembly

```asm
0x180332e98  push    rbp
0x180332e9a  push    rbx
0x180332e9b  push    rsi
0x180332e9c  push    rdi
0x180332e9d  push    r12
0x180332e9f  push    r14
0x180332ea1  push    r15
0x180332ea3  lea     rbp, [rsp-50h]
0x180332ea8  sub     rsp, 150h
0x180332eaf  mov     rax, cs:__security_cookie
0x180332eb6  xor     rax, rsp
0x180332eb9  mov     [rbp+80h+var_40], rax
0x180332ebd  mov     r15, r9
0x180332ec0  mov     r14, r8
0x180332ec3  mov     rsi, rdx
0x180332ec6  mov     [rbp+80h+var_E8], rcx
0x180332eca  xor     r12d, r12d
0x180332ecd  mov     [rdx], r12
0x180332ed0  mov     [r8], r12
0x180332ed3  mov     [r9], r12
0x180332ed6  mov     [rbp+80h+var_C8], r12
0x180332eda  mov     [rbp+80h+var_48], r12
0x180332ede  lea     r9d, [r12+34h]; unsigned int
0x180332ee3  lea     r8d, [r12+35h]; unsigned int
0x180332ee8  lea     rdx, ?RuntimeClass_WindowsInternal_Shell_UnifiedTile_UnifiedTileManager@@3QBGB; "WindowsInternal.Shell.UnifiedTile.Unifi"...
0x180332eef  lea     rcx, [rbp+80h+hstringHeader]; hstringHeader
0x180332ef3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180332ef8  lea     rdx, [rbp+80h+var_C8]
0x180332efc  mov     rcx, [rbp+80h+var_48]
0x180332f00  call    ??$GetActivationFactory@V?$ComPtr@UIUnifiedTileManagerStatics@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUnifiedTileManagerStatics@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerStatics>>)
0x180332f05  mov     ebx, eax
0x180332f07  test    eax, eax
0x180332f09  jns     short loc_180332F2B
0x180332f0b  mov     rcx, [rbp+88h]; this
0x180332f12  mov     r9d, eax; char *
0x180332f15  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180332f1c  mov     edx, 338h; void *
0x180332f21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180332f26  jmp     loc_18033367E
0x180332f2b  mov     [rsp+180h+var_150], r12
0x180332f30  mov     rdi, [rbp+80h+var_C8]
0x180332f34  mov     rax, [rdi]
0x180332f37  mov     rbx, [rax+30h]
0x180332f3b  lea     rcx, [rsp+180h+var_150]
0x180332f40  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180332f45  lea     r9, [rsp+180h+var_150]
0x180332f4a  mov     edx, 3
0x180332f4f  lea     r8d, [rdx-2]
0x180332f53  mov     rcx, rdi
0x180332f56  mov     rax, rbx
0x180332f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180332f5e  mov     ebx, eax
0x180332f60  test    eax, eax
0x180332f62  jns     short loc_180332F8E
0x180332f64  mov     edx, 33Bh; void *
0x180332f69  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180332f70  mov     r9d, eax; char *
0x180332f73  mov     rcx, [rbp+88h]; this
0x180332f7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180332f7f  lea     rcx, [rsp+180h+var_150]
0x180332f84  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180332f89  jmp     loc_18033367E
0x180332f8e  mov     rcx, [rsp+180h+var_150]
0x180332f93  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *>,Windows::Foundation::IAsyncOperation<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *>>(Windows::Foundation::IAsyncOperation<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *> *,tagCOWAIT_FLAGS,void *)
0x180332f98  mov     ebx, eax
0x180332f9a  test    eax, eax
0x180332f9c  jns     short loc_180332FA5
0x180332f9e  mov     edx, 33Ch
0x180332fa3  jmp     short loc_180332F69
0x180332fa5  mov     [rsp+180h+var_140], r12
0x180332faa  mov     rdi, [rsp+180h+var_150]
0x180332faf  mov     rax, [rdi]
0x180332fb2  mov     rbx, [rax+40h]
0x180332fb6  lea     rcx, [rsp+180h+var_140]
0x180332fbb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180332fc0  lea     rdx, [rsp+180h+var_140]
0x180332fc5  mov     rcx, rdi
0x180332fc8  mov     rax, rbx
0x180332fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180332fd0  mov     ebx, eax
0x180332fd2  test    eax, eax
0x180332fd4  jns     short loc_180332FFD
0x180332fd6  mov     rcx, [rbp+88h]; this
0x180332fdd  mov     r9d, eax; char *
0x180332fe0  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180332fe7  mov     edx, 33Fh; void *
0x180332fec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180332ff1  lea     rcx, [rsp+180h+var_140]
0x180332ff6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180332ffb  jmp     short loc_180332F7F
0x180332ffd  mov     [rsp+180h+var_138], r12
0x180333002  mov     rdi, [rsp+180h+var_140]
0x180333007  mov     rax, [rdi]
0x18033300a  mov     rbx, [rax+50h]
0x18033300e  lea     rcx, [rsp+180h+var_138]
0x180333013  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180333018  lea     rdx, [rsp+180h+var_138]
0x18033301d  mov     rcx, rdi
0x180333020  mov     rax, rbx
0x180333023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180333028  mov     ebx, eax
0x18033302a  test    eax, eax
0x18033302c  jns     short loc_180333055
0x18033302e  mov     edx, 342h; void *
0x180333033  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18033303a  mov     r9d, eax; char *
0x18033303d  mov     rcx, [rbp+88h]; this
0x180333044  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180333049  lea     rcx, [rsp+180h+var_138]
0x18033304e  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180333053  jmp     short loc_180332FF1
0x180333055  or      edx, 0FFFFFFFFh
0x180333058  mov     rcx, [rsp+180h+var_138]
0x18033305d  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)
0x180333062  mov     ebx, eax
0x180333064  test    eax, eax
0x180333066  jns     short loc_18033306F
0x180333068  mov     edx, 343h
0x18033306d  jmp     short loc_180333033
0x18033306f  mov     [rsp+180h+var_130], r12
0x180333074  mov     [rsp+180h+var_128], r12
0x180333079  mov     [rsp+180h+var_120], r12
0x18033307e  mov     [rbp+80h+var_48], r12
0x180333082  mov     r9d, 3Fh ; '?'; unsigned int
0x180333088  lea     r8d, [r9+1]; unsigned int
0x18033308c  lea     rdx, ?RuntimeClass_WindowsInternal_Shell_UnifiedTile_PackagedUnifiedTileIdentifier@@3QBGB; "WindowsInternal.Shell.UnifiedTile.Packa"...
0x180333093  lea     rcx, [rbp+80h+hstringHeader]; hstringHeader
0x180333097  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18033309c  lea     rdx, [rsp+180h+var_120]
0x1803330a1  mov     rcx, [rbp+80h+var_48]
0x1803330a5  call    ??$GetActivationFactory@V?$ComPtr@UIPackagedUnifiedTileIdentifierFactory@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackagedUnifiedTileIdentifierFactory@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifierFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifierFactory>>)
0x1803330aa  mov     ebx, eax
0x1803330ac  test    eax, eax
0x1803330ae  jns     short loc_1803330EE
0x1803330b0  mov     edx, 349h; void *
0x1803330b5  mov     r9d, eax; char *
0x1803330b8  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x1803330bf  mov     rcx, [rbp+88h]; this
0x1803330c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803330cb  lea     rcx, [rsp+180h+var_120]
0x1803330d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803330d5  lea     rcx, [rsp+180h+var_128]
0x1803330da  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803330df  lea     rcx, [rsp+180h+var_130]
0x1803330e4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803330e9  jmp     loc_180333049
0x1803330ee  mov     rdi, [rsp+180h+var_120]
0x1803330f3  mov     rax, [rdi]
0x1803330f6  mov     rbx, [rax+30h]
0x1803330fa  lea     rcx, [rsp+180h+var_128]
0x1803330ff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180333104  lea     rdx, [rbp+80h+var_E8]
0x180333108  lea     rcx, [rbp+80h+hstringHeader]
0x18033310c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180333111  lea     r8, [rsp+180h+var_128]
0x180333116  mov     rdx, [rax+18h]
0x18033311a  mov     rcx, rdi
0x18033311d  mov     rax, rbx
0x180333120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180333125  mov     ebx, eax
0x180333127  test    eax, eax
0x180333129  jns     short loc_180333132
0x18033312b  mov     edx, 34Bh
0x180333130  jmp     short loc_1803330B5
0x180333132  mov     rdi, [rsp+180h+var_140]
0x180333137  mov     rax, [rdi]
0x18033313a  mov     rbx, [rax+48h]
0x18033313e  lea     rcx, [rsp+180h+var_130]
0x180333143  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180333148  lea     r8, [rsp+180h+var_130]
0x18033314d  mov     rdx, [rsp+180h+var_128]
0x180333152  mov     rcx, rdi
0x180333155  mov     rax, rbx
0x180333158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033315d  mov     ebx, eax
0x18033315f  test    eax, eax
0x180333161  jns     short loc_18033316D
0x180333163  mov     edx, 34Ch
0x180333168  jmp     loc_1803330B5
0x18033316d  mov     rbx, [rsp+180h+var_130]
0x180333172  test    rbx, rbx
0x180333175  jnz     short loc_180333189
0x180333177  mov     ebx, 80070490h
0x18033317c  mov     r9d, ebx
0x18033317f  mov     edx, 34Dh
0x180333184  jmp     loc_1803330B8
0x180333189  mov     [rsp+180h+var_118], r12
0x18033318e  mov     rax, [rbx]
0x180333191  mov     rdi, [rax+38h]
0x180333195  lea     rcx, [rsp+180h+var_118]
0x18033319a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18033319f  lea     rdx, [rsp+180h+var_118]
0x1803331a4  mov     rcx, rbx
0x1803331a7  mov     rax, rdi
0x1803331aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803331af  mov     ebx, eax
0x1803331b1  test    eax, eax
0x1803331b3  jns     short loc_1803331DF
0x1803331b5  mov     rcx, [rbp+88h]; this
0x1803331bc  mov     r9d, eax; char *
0x1803331bf  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x1803331c6  mov     edx, 350h; void *
0x1803331cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803331d0  lea     rcx, [rsp+180h+var_118]
0x1803331d5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803331da  jmp     loc_1803330CB
0x1803331df  mov     [rsp+180h+string], r12
0x1803331e4  mov     rdi, [rsp+180h+var_118]
0x1803331e9  mov     rax, [rdi]
0x1803331ec  mov     rbx, [rax+30h]
0x1803331f0  xor     ecx, ecx; string
0x1803331f2  call    cs:__imp_WindowsDeleteString
0x1803331f9  nop     dword ptr [rax+rax+00h]
0x1803331fe  mov     [rsp+180h+string], r12
0x180333203  lea     rdx, [rsp+180h+string]
0x180333208  mov     rcx, rdi
0x18033320b  mov     rax, rbx
0x18033320e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180333213  mov     ebx, eax
0x180333215  test    eax, eax
0x180333217  jns     short loc_18033324C
0x180333219  mov     rcx, [rbp+88h]; this
0x180333220  mov     r9d, eax; char *
0x180333223  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18033322a  mov     edx, 353h; void *
0x18033322f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180333234  mov     rcx, [rsp+180h+string]; string
0x180333239  call    cs:__imp_WindowsDeleteString
0x180333240  nop     dword ptr [rax+rax+00h]
0x180333245  mov     [rsp+180h+string], r12
0x18033324a  jmp     short loc_1803331D0
0x18033324c  mov     [rbp+80h+var_E0], r12
0x180333250  mov     [rbp+80h+var_D8], r12
0x180333254  mov     [rbp+80h+var_D0], r12
0x180333258  xor     edx, edx; length
0x18033325a  mov     rcx, [rsp+180h+string]; string
0x18033325f  call    cs:__imp_WindowsGetStringRawBuffer
0x180333266  nop     dword ptr [rax+rax+00h]
0x18033326b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18033326f  mov     rdx, rax
0x180333272  lea     rcx, [rbp+80h+var_E0]
0x180333276  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18033327b  mov     ebx, eax
0x18033327d  test    eax, eax
0x18033327f  jns     short loc_1803332A7
0x180333281  mov     edx, 356h; void *
0x180333286  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18033328d  mov     r9d, eax; char *
0x180333290  mov     rcx, [rbp+88h]; this
0x180333297  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033329c  lea     rcx, [rbp+80h+var_E0]
0x1803332a0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1803332a5  jmp     short loc_180333234
0x1803332a7  mov     [rsp+180h+var_110], r12d
0x1803332ac  mov     rcx, [rsp+180h+var_118]
0x1803332b1  mov     rax, [rcx]
0x1803332b4  lea     rdx, [rsp+180h+var_110]
0x1803332b9  mov     rax, [rax+48h]
0x1803332bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803332c2  mov     ebx, eax
0x1803332c4  test    eax, eax
0x1803332c6  jns     short loc_1803332CF
0x1803332c8  mov     edx, 359h
0x1803332cd  jmp     short loc_180333286
0x1803332cf  mov     qword ptr [rbp+80h+hstringHeader.Reserved], r12
0x1803332d3  mov     qword ptr [rbp+80h+hstringHeader.Reserved+8], r12
0x1803332d7  mov     qword ptr [rbp+80h+hstringHeader.Reserved+10h], r12
0x1803332db  movzx   eax, byte ptr [rsp+180h+var_110+3]
0x1803332e0  movzx   ecx, byte ptr [rsp+180h+var_110+2]
0x1803332e5  movzx   r9d, byte ptr [rsp+180h+var_110+1]
0x1803332eb  movzx   r8d, byte ptr [rsp+180h+var_110]
0x1803332f1  mov     [rsp+180h+var_158], eax
0x1803332f5  mov     [rsp+180h+var_160], ecx; int
0x1803332f9  lea     rdx, a02x02x02x02x; "#%02x%02x%02x%02x"
0x180333300  lea     rcx, [rbp+80h+hstringHeader]
0x180333304  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180333309  mov     ebx, eax
0x18033330b  test    eax, eax
0x18033330d  jns     short loc_180333338
0x18033330f  mov     rcx, [rbp+88h]; this
0x180333316  mov     r9d, eax; char *
0x180333319  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180333320  mov     edx, 35Ch; void *
0x180333325  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033332a  lea     rcx, [rbp+80h+hstringHeader]
0x18033332e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180333333  jmp     loc_18033329C
0x180333338  mov     [rbp+80h+var_F8], r12
0x18033333c  mov     rdi, [rsp+180h+var_130]
0x180333341  mov     rax, [rdi]
0x180333344  mov     rbx, [rax+68h]
0x180333348  lea     rcx, [rbp+80h+var_F8]
0x18033334c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180333351  lea     rdx, [rbp+80h+var_F8]
0x180333355  mov     rcx, rdi
0x180333358  mov     rax, rbx
0x18033335b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180333360  mov     ebx, eax
0x180333362  test    eax, eax
0x180333364  jns     short loc_18033338C
  ... truncated ...
```
