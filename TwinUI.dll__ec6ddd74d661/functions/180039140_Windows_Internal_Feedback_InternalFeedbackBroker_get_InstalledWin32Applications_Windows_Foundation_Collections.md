# Windows::Internal::Feedback::InternalFeedbackBroker::get_InstalledWin32Applications(Windows::Foundation::Collections::IVectorView<Windows::Internal::Feedback::FeedbackItem *> * *)

- ea: `0x180039140`
- end: `0x1800398d4`
- name: `?get_InstalledWin32Applications@InternalFeedbackBroker@Feedback@Internal@Windows@@UEAAJPEAPEAU?$IVectorView@PEAVFeedbackItem@Feedback@Internal@Windows@@@Collections@Foundation@4@@Z`
- size: `1940`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180009dd0`
- `0x180009dfc`
- `0x18001d654`
- `0x1800378dc`
- `0x1800390a0`
- `0x180039140`
- `0x1800398dc`
- `0x180039bd4`
- `0x1800eefa4`
- `0x180142e34`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039567`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800395b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800395f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039635`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039567`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800395b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800395f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039635`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180039582`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800395c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003960a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003964c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180039582`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800395c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003960a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003964c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003944b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039716`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003944b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039716`
- `AEPIC!PicFreeFileInfo` at `0x18003968f`
- `AEPIC!PicFreeFileInfo` at `0x18003968f`
- `AEPIC!PicRetrieveFileInfo` at `0x1800394e4`
- `AEPIC!PicRetrieveFileInfo` at `0x1800394e4`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180039700`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180039700`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x180039420`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x180039420`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18003949a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18003949a`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderItem` at `0x1800391c7`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderItem` at `0x1800391c7`

## string_xrefs

- `0x180039259`: `shell\twinui\feedback\lib\feedbackbroker.cpp`
- `0x1800392c2`: `shell\twinui\feedback\lib\feedbackbroker.cpp`
- `0x180039360`: `shell\twinui\feedback\lib\feedbackbroker.cpp`
- `0x1800397e3`: `shell\twinui\feedback\lib\feedbackbroker.cpp`
- `0x18003984f`: `shell\twinui\feedback\lib\feedbackbroker.cpp`
- `0x180039878`: `shell\twinui\feedback\lib\feedbackbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall Windows::Internal::Feedback::InternalFeedbackBroker::get_InstalledWin32Applications(
        Windows::Internal::Feedback *a1,
        __int64 a2)
{
  __int64 v2; // rsi
  int HasPackageQueryCapability; // ebx
  __int64 v4; // rcx
  int v5; // eax
  HRESULT v6; // eax
  void *v7; // rdi
  __int64 (__fastcall *v8)(void *, _QWORD, const GUID *, GUID *); // rbx
  int v9; // eax
  IShellFolder *v10; // rdi
  HRESULT (__stdcall *EnumObjects)(IShellFolder *, HWND, SHCONTF, IEnumIDList **); // rbx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rcx
  IShellFolder *v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  void *v18; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  IShellFolder *v22; // rcx
  void *v23; // rbx
  int (__fastcall *v24)(void *, const PROPERTYKEY *, LPVOID *); // rdi
  const WCHAR *FileNameW; // r15
  LPVOID v26; // rbx
  Windows::Internal::Feedback *v27; // rcx
  HRESULT String; // ebx
  const WCHAR **v29; // rbx
  HSTRING *v30; // rcx
  Windows::Internal::Feedback::InternalFeedbackItem *v31; // rax
  HSTRING *v32; // rsi
  const WCHAR *v33; // r13
  const WCHAR *v34; // r12
  const WCHAR *v35; // r14
  __int64 v36; // rdi
  __int64 v37; // rdi
  __int64 v38; // rdi
  __int64 v39; // rdi
  __int64 v40; // rdx
  HSTRING *v41; // rcx
  HSTRING *v42; // rcx
  void *v43; // rcx
  HSTRING *v44; // rcx
  int v45; // eax
  __int64 v46; // rcx
  __int64 v47; // rcx
  IShellFolder *v48; // rcx
  __int64 v49; // rdx
  int ppv; // [rsp+20h] [rbp-49h]
  int ppva; // [rsp+20h] [rbp-49h]
  void **ppvb; // [rsp+20h] [rbp-49h]
  IShellFolder *psfParent; // [rsp+30h] [rbp-39h] BYREF
  void *v54; // [rsp+38h] [rbp-31h] BYREF
  HSTRING *v55; // [rsp+40h] [rbp-29h] BYREF
  HSTRING *v56; // [rsp+48h] [rbp-21h]
  void *ppvItem; // [rsp+50h] [rbp-19h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-11h] BYREF
  __int64 v59; // [rsp+60h] [rbp-9h]
  __int64 v60; // [rsp+68h] [rbp-1h]
  const WCHAR **v61; // [rsp+70h] [rbp+7h] BYREF
  LPCITEMIDLIST pidl; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v63[8]; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  __int64 v66; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v67; // [rsp+E8h] [rbp+7Fh] BYREF

  v2 = a2;
  v54 = 0;
  psfParent = 0;
  v67 = 0;
  HasPackageQueryCapability = Windows::Internal::Feedback::HasPackageQueryCapability(a1);
  if ( HasPackageQueryCapability < 0 )
    goto LABEL_92;
  v66 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
  v5 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::Feedback::FeedbackItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Feedback::FeedbackItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Feedback::FeedbackItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Feedback::FeedbackItem *>,0>>(
         v4,
         &v66);
  HasPackageQueryCapability = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"shell\\twinui\\feedback\\lib\\feedbackbroker.cpp",
      (const char *)(unsigned int)v5,
      ppv);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
    goto LABEL_92;
  }
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v54);
  v6 = SHGetKnownFolderItem(&FOLDERID_AppsFolder, KF_FLAG_DEFAULT, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &v54);
  HasPackageQueryCapability = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA3,
      (unsigned int)"shell\\twinui\\feedback\\lib\\feedbackbroker.cpp",
      (const char *)(unsigned int)v6,
      ppva);
    v16 = v66;
    if ( v66 )
    {
      v66 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    v17 = v67;
    if ( v67 )
    {
      v67 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    goto LABEL_17;
  }
  v7 = v54;
  v8 = *(__int64 (__fastcall **)(void *, _QWORD, const GUID *, GUID *))(*(_QWORD *)v54 + 24LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&psfParent);
  ppvb = (void **)&psfParent;
  v9 = v8(v7, 0, &BHID_SFObject, &GUID_000214e6_0000_0000_c000_000000000046);
  HasPackageQueryCapability = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA4,
      (unsigned int)"shell\\twinui\\feedback\\lib\\feedbackbroker.cpp",
      (const char *)(unsigned int)v9,
      (int)&psfParent);
    v20 = v66;
    if ( v66 )
    {
      v66 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v21 = v67;
    if ( v67 )
    {
      v67 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v22 = psfParent;
    if ( psfParent )
    {
      psfParent = 0;
      ((void (__fastcall *)(IShellFolder *))v22->lpVtbl->Release)(v22);
    }
LABEL_17:
    v18 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return (unsigned int)HasPackageQueryCapability;
  }
  v10 = psfParent;
  EnumObjects = psfParent->lpVtbl->EnumObjects;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
  v12 = ((__int64 (__fastcall *)(IShellFolder *, _QWORD, __int64, __int64 *))EnumObjects)(v10, 0, 64, &v67);
  HasPackageQueryCapability = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"shell\\twinui\\feedback\\lib\\feedbackbroker.cpp",
      (const char *)(unsigned int)v12,
      (int)&psfParent);
    v13 = v66;
    if ( v66 )
    {
      v66 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v14 = v67;
    if ( v67 )
    {
      v67 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = psfParent;
    if ( psfParent )
    {
      psfParent = 0;
      ((void (__fastcall *)(IShellFolder *))v15->lpVtbl->Release)(v15);
    }
    goto LABEL_17;
  }
  if ( !v67 )
    goto LABEL_78;
  pidl = 0;
  while ( !(*(unsigned int (__fastcall **)(__int64, __int64, LPCITEMIDLIST *))(*(_QWORD *)v67 + 24LL))(v67, 1, &pidl) )
  {
    ppvItem = 0;
    pv = 0;
    v59 = 0;
    v60 = 0;
    if ( SHCreateItemWithParent(0, psfParent, pidl, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppvItem) >= 0 )
    {
      v23 = ppvItem;
      v24 = *(int (__fastcall **)(void *, const PROPERTYKEY *, LPVOID *))(*(_QWORD *)ppvItem + 136LL);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v59 = -1;
      v60 = -1;
      if ( v24(v23, &PKEY_Link_TargetParsingPath, &pv) >= 0 )
      {
        if ( pv )
        {
          v56 = 0;
          FileNameW = PathFindFileNameW((LPCWSTR)pv);
          v26 = pv;
          v61 = 0;
          v55 = 0;
          if ( (int)Windows::Internal::Feedback::HasPackageQueryCapability(v27) < 0 )
          {
            v44 = v55;
            if ( v55 )
            {
              v55 = 0;
              (*((void (__fastcall **)(HSTRING *))*v44 + 2))(v44);
            }
            goto LABEL_63;
          }
          if ( v26 )
          {
            if ( FileNameW )
            {
              v56 = 0;
              String = PicRetrieveFileInfo(v26, 16400, &v61);
              if ( String < 0 )
                goto LABEL_90;
              v29 = v61;
              v30 = v55;
              if ( v55 )
              {
                v55 = 0;
                (*((void (__fastcall **)(HSTRING *))*v30 + 2))(v30);
              }
              v55 = 0;
              v31 = (Windows::Internal::Feedback::InternalFeedbackItem *)operator new(
                                                                           0x60u,
                                                                           (const struct std::nothrow_t *)std::nothrow);
              if ( !v31 )
              {
                String = -2147024882;
                goto LABEL_56;
              }
              v32 = (HSTRING *)Windows::Internal::Feedback::InternalFeedbackItem::InternalFeedbackItem(v31);
              v63[0] = 0;
              v33 = *v29;
              v34 = v29[1];
              v35 = v29[2];
              v36 = -1;
              do
                ++v36;
              while ( v35[v36] );
              WindowsDeleteString(v32[8]);
              v32[8] = 0;
              String = WindowsCreateString(v35, v36, v32 + 8);
              if ( String < 0 )
              {
                v40 = 24;
              }
              else
              {
                v37 = -1;
                do
                  ++v37;
                while ( v34[v37] );
                WindowsDeleteString(v32[9]);
                v32[9] = 0;
                String = WindowsCreateString(v34, v37, v32 + 9);
                if ( String < 0 )
                {
                  v40 = 25;
                }
                else
                {
                  v38 = -1;
                  do
                    ++v38;
                  while ( v33[v38] );
                  WindowsDeleteString(v32[10]);
                  v32[10] = 0;
                  String = WindowsCreateString(v33, v38, v32 + 10);
                  if ( String >= 0 )
                  {
                    v39 = -1;
                    do
                      ++v39;
                    while ( FileNameW[v39] );
                    WindowsDeleteString(v32[11]);
                    v32[11] = 0;
                    String = WindowsCreateString(FileNameW, v39, v32 + 11);
                    if ( String < 0 )
                    {
                      v40 = 27;
                      goto LABEL_55;
                    }
                    v55 = v32;
                    (*((void (__fastcall **)(HSTRING *))*v32 + 1))(v32);
                    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::Release(v32);
                    String = 0;
LABEL_56:
                    PicFreeFileInfo(v61);
                    if ( String >= 0 )
                    {
                      v41 = 0;
                      v56 = v55;
                      goto LABEL_58;
                    }
LABEL_90:
                    v41 = v55;
LABEL_58:
                    if ( v41 )
                    {
                      v55 = 0;
                      (*((void (__fastcall **)(HSTRING *))*v41 + 2))(v41);
                    }
                    if ( String >= 0 && v56 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 104LL))(v66);
LABEL_63:
                    v42 = v56;
                    if ( v56 )
                    {
                      v56 = 0;
                      (*((void (__fastcall **)(HSTRING *))*v42 + 2))(v42);
                    }
                    goto LABEL_65;
                  }
                  v40 = 26;
                }
              }
LABEL_55:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v40,
                (unsigned int)"shell\\twinui\\feedback\\lib\\internalfeedbackhubapp.cpp",
                (const char *)(unsigned int)String,
                (int)ppvb);
              Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::Release(v32);
              Microsoft::WRL::Details::MakeAllocator<SttExperienceManagerFactory>::~MakeAllocator<SttExperienceManagerFactory>(v63);
              goto LABEL_56;
            }
            v49 = 237;
          }
          else
          {
            v49 = 236;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v49,
            (unsigned int)"shell\\twinui\\feedback\\lib\\feedbackbroker.cpp",
            (const char *)0x80070057LL,
            (int)ppvb);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
          goto LABEL_63;
        }
      }
    }
LABEL_65:
    ILFree((LPITEMIDLIST)pidl);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v59 = 0;
    v60 = 0;
    v43 = ppvItem;
    if ( ppvItem )
    {
      ppvItem = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v43 + 16LL))(v43);
    }
  }
  v2 = a2;
LABEL_78:
  v45 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v66 + 64LL))(v66, v2);
  HasPackageQueryCapability = v45;
  if ( v45 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"shell\\twinui\\feedback\\lib\\feedbackbroker.cpp",
      (const char *)(unsigned int)v45,
      (int)ppvb);
    v46 = v66;
    if ( v66 )
    {
      v66 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    }
    v47 = v67;
    if ( v67 )
    {
      v67 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    }
    v48 = psfParent;
    if ( psfParent )
    {
      psfParent = 0;
      ((void (__fastcall *)(IShellFolder *))v48->lpVtbl->Release)(v48);
    }
    goto LABEL_17;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
  HasPackageQueryCapability = 0;
LABEL_92:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&psfParent);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v54);
  return (unsigned int)HasPackageQueryCapability;
}

```

## disassembly

```asm
0x180039140  mov     [rsp-8+arg_0], rbx
0x180039145  mov     [rsp-8+arg_8], rdx
0x18003914a  push    rbp
0x18003914b  push    rsi
0x18003914c  push    rdi
0x18003914d  push    r12
0x18003914f  push    r13
0x180039151  push    r14
0x180039153  push    r15
0x180039155  lea     rbp, [rsp-27h]
0x18003915a  sub     rsp, 90h
0x180039161  mov     rsi, rdx
0x180039164  xor     r14d, r14d
0x180039167  mov     [rbp+57h+var_88], r14
0x18003916b  mov     [rbp+57h+psfParent], r14
0x18003916f  mov     [rbp+57h+arg_18], r14
0x180039173  call    ?HasPackageQueryCapability@Feedback@Internal@Windows@@YAJXZ; Windows::Internal::Feedback::HasPackageQueryCapability(void)
0x180039178  mov     ebx, eax
0x18003917a  test    eax, eax
0x18003917c  js      loc_1800398B2
0x180039182  mov     [rbp+57h+arg_10], r14
0x180039186  lea     rcx, [rbp+57h+arg_10]
0x18003918a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003918f  lea     rdx, [rbp+57h+arg_10]
0x180039193  call    ??$CreateExternalObjectVector@VFeedbackItem@Feedback@Internal@Windows@@V?$AgileVector@PEAVFeedbackItem@Feedback@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVFeedbackItem@Feedback@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVFeedbackItem@Feedback@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVFeedbackItem@Feedback@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVFeedbackItem@Feedback@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVFeedbackItem@Feedback@Internal@Windows@@@3674@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::Feedback::FeedbackItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Feedback::FeedbackItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Feedback::FeedbackItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Feedback::FeedbackItem *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Feedback::FeedbackItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Feedback::FeedbackItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Feedback::FeedbackItem *>,0> * *)
0x180039198  mov     ebx, eax
0x18003919a  test    eax, eax
0x18003919c  js      loc_180039848
0x1800391a2  lea     rcx, [rbp+57h+var_88]
0x1800391a6  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1800391ab  lea     rax, [rbp+57h+var_88]
0x1800391af  mov     [rsp+0C0h+ppv], rax; int
0x1800391b4  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800391bb  xor     r8d, r8d; hToken
0x1800391be  xor     edx, edx; flags
0x1800391c0  lea     rcx, FOLDERID_AppsFolder; rfid
0x1800391c7  call    cs:__imp_SHGetKnownFolderItem
0x1800391ce  nop     dword ptr [rax+rax+00h]
0x1800391d3  mov     ebx, eax
0x1800391d5  test    eax, eax
0x1800391d7  js      loc_1800392BB
0x1800391dd  mov     rdi, [rbp+57h+var_88]
0x1800391e1  mov     rax, [rdi]
0x1800391e4  mov     rbx, [rax+18h]
0x1800391e8  lea     rcx, [rbp+57h+psfParent]
0x1800391ec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800391f1  lea     rax, [rbp+57h+psfParent]
0x1800391f5  mov     [rsp+0C0h+ppv], rax; int
0x1800391fa  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x180039201  lea     r8, BHID_SFObject
0x180039208  xor     edx, edx
0x18003920a  mov     rcx, rdi
0x18003920d  mov     rax, rbx
0x180039210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039215  mov     ebx, eax
0x180039217  test    eax, eax
0x180039219  js      loc_180039359
0x18003921f  mov     rdi, [rbp+57h+psfParent]
0x180039223  mov     rax, [rdi]
0x180039226  mov     rbx, [rax+20h]
0x18003922a  lea     rcx, [rbp+57h+arg_18]
0x18003922e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180039233  lea     r9, [rbp+57h+arg_18]
0x180039237  xor     edx, edx
0x180039239  lea     r8d, [r14+40h]
0x18003923d  mov     rcx, rdi
0x180039240  mov     rax, rbx
0x180039243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039248  mov     ebx, eax
0x18003924a  test    eax, eax
0x18003924c  jns     loc_1800393C5
0x180039252  mov     rcx, [rbp+5Fh]; this
0x180039256  mov     r9d, eax; char *
0x180039259  lea     r8, aShellTwinuiFee; "shell\\twinui\\feedback\\lib\\feedbackb"...
0x180039260  mov     edx, 0A5h; void *
0x180039265  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003926a  nop
0x18003926b  mov     rcx, [rbp+57h+arg_10]
0x18003926f  test    rcx, rcx
0x180039272  jz      short loc_180039285
0x180039274  mov     [rbp+57h+arg_10], r14
0x180039278  mov     rax, [rcx]
0x18003927b  mov     rax, [rax+10h]
0x18003927f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039284  nop
0x180039285  mov     rcx, [rbp+57h+arg_18]
0x180039289  test    rcx, rcx
0x18003928c  jz      short loc_18003929F
0x18003928e  mov     [rbp+57h+arg_18], r14
0x180039292  mov     rax, [rcx]
0x180039295  mov     rax, [rax+10h]
0x180039299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003929e  nop
0x18003929f  mov     rcx, [rbp+57h+psfParent]
0x1800392a3  test    rcx, rcx
0x1800392a6  jz      short loc_1800392B9
0x1800392a8  mov     [rbp+57h+psfParent], r14
0x1800392ac  mov     rax, [rcx]
0x1800392af  mov     rax, [rax+10h]
0x1800392b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392b8  nop
0x1800392b9  jmp     short loc_180039322
0x1800392bb  mov     rcx, [rbp+5Fh]; this
0x1800392bf  mov     r9d, ebx; char *
0x1800392c2  lea     r8, aShellTwinuiFee; "shell\\twinui\\feedback\\lib\\feedbackb"...
0x1800392c9  mov     edx, 0A3h; void *
0x1800392ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800392d3  nop
0x1800392d4  mov     rcx, [rbp+57h+arg_10]
0x1800392d8  test    rcx, rcx
0x1800392db  jz      short loc_1800392EE
0x1800392dd  mov     [rbp+57h+arg_10], r14
0x1800392e1  mov     rax, [rcx]
0x1800392e4  mov     rax, [rax+10h]
0x1800392e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392ed  nop
0x1800392ee  mov     rcx, [rbp+57h+arg_18]
0x1800392f2  test    rcx, rcx
0x1800392f5  jz      short loc_180039308
0x1800392f7  mov     [rbp+57h+arg_18], r14
0x1800392fb  mov     rax, [rcx]
0x1800392fe  mov     rax, [rax+10h]
0x180039302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039307  nop
0x180039308  mov     rcx, [rbp+57h+psfParent]
0x18003930c  test    rcx, rcx
0x18003930f  jz      short loc_180039322
0x180039311  mov     [rbp+57h+psfParent], r14
0x180039315  mov     rax, [rcx]
0x180039318  mov     rax, [rax+10h]
0x18003931c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039321  nop
0x180039322  mov     rcx, [rbp+57h+var_88]
0x180039326  test    rcx, rcx
0x180039329  jz      short loc_18003933B
0x18003932b  mov     [rbp+57h+var_88], r14
0x18003932f  mov     rax, [rcx]
0x180039332  mov     rax, [rax+10h]
0x180039336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003933b  mov     eax, ebx
0x18003933d  mov     rbx, [rsp+0C0h+arg_0]
0x180039345  add     rsp, 90h
0x18003934c  pop     r15
0x18003934e  pop     r14
0x180039350  pop     r13
0x180039352  pop     r12
0x180039354  pop     rdi
0x180039355  pop     rsi
0x180039356  pop     rbp
0x180039357  retn
0x180039359  mov     rcx, [rbp+5Fh]; this
0x18003935d  mov     r9d, ebx; char *
0x180039360  lea     r8, aShellTwinuiFee; "shell\\twinui\\feedback\\lib\\feedbackb"...
0x180039367  mov     edx, 0A4h; void *
0x18003936c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039371  nop
0x180039372  mov     rcx, [rbp+57h+arg_10]
0x180039376  test    rcx, rcx
0x180039379  jz      short loc_18003938C
0x18003937b  mov     [rbp+57h+arg_10], r14
0x18003937f  mov     rax, [rcx]
0x180039382  mov     rax, [rax+10h]
0x180039386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003938b  nop
0x18003938c  mov     rcx, [rbp+57h+arg_18]
0x180039390  test    rcx, rcx
0x180039393  jz      short loc_1800393A6
0x180039395  mov     [rbp+57h+arg_18], r14
0x180039399  mov     rax, [rcx]
0x18003939c  mov     rax, [rax+10h]
0x1800393a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393a5  nop
0x1800393a6  mov     rcx, [rbp+57h+psfParent]
0x1800393aa  test    rcx, rcx
0x1800393ad  jz      short loc_1800393C0
0x1800393af  mov     [rbp+57h+psfParent], r14
0x1800393b3  mov     rax, [rcx]
0x1800393b6  mov     rax, [rax+10h]
0x1800393ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393bf  nop
0x1800393c0  jmp     loc_180039322
0x1800393c5  cmp     [rbp+57h+arg_18], r14
0x1800393c9  jz      loc_1800397BF
0x1800393cf  mov     [rbp+57h+pidl], r14
0x1800393d3  mov     rcx, [rbp+57h+arg_18]
0x1800393d7  mov     rax, [rcx]
0x1800393da  xor     r9d, r9d
0x1800393dd  lea     r8, [rbp+57h+pidl]
0x1800393e1  lea     edx, [r9+1]
0x1800393e5  mov     rax, [rax+18h]
0x1800393e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393ee  test    eax, eax
0x1800393f0  jnz     loc_1800397BB
0x1800393f6  mov     [rbp+57h+ppvItem], r14
0x1800393fa  mov     [rbp+57h+pv], r14
0x1800393fe  mov     [rbp+57h+var_60], r14
0x180039402  mov     [rbp+57h+var_58], r14
0x180039406  lea     rax, [rbp+57h+ppvItem]
0x18003940a  mov     [rsp+0C0h+ppv], rax; int
0x18003940f  lea     r9, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x180039416  mov     r8, [rbp+57h+pidl]; pidl
0x18003941a  mov     rdx, [rbp+57h+psfParent]; psfParent
0x18003941e  xor     ecx, ecx; pidlParent
0x180039420  call    cs:__imp_SHCreateItemWithParent
0x180039427  nop     dword ptr [rax+rax+00h]
0x18003942c  test    eax, eax
0x18003942e  js      loc_1800396FC
0x180039434  mov     rbx, [rbp+57h+ppvItem]
0x180039438  mov     rax, [rbx]
0x18003943b  mov     rdi, [rax+88h]
0x180039442  mov     rcx, [rbp+57h+pv]; pv
0x180039446  test    rcx, rcx
0x180039449  jz      short loc_18003945B
0x18003944b  call    cs:__imp_CoTaskMemFree
0x180039452  nop     dword ptr [rax+rax+00h]
0x180039457  mov     [rbp+57h+pv], r14
0x18003945b  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFFh
0x180039463  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFFh
0x18003946b  lea     r8, [rbp+57h+pv]
0x18003946f  lea     rdx, PKEY_Link_TargetParsingPath
0x180039476  mov     rcx, rbx
0x180039479  mov     rax, rdi
0x18003947c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039481  test    eax, eax
0x180039483  js      loc_1800396FC
0x180039489  mov     rcx, [rbp+57h+pv]; pszPath
0x18003948d  test    rcx, rcx
0x180039490  jz      loc_1800396FC
0x180039496  mov     [rbp+57h+var_78], r14
0x18003949a  call    cs:__imp_PathFindFileNameW
0x1800394a1  nop     dword ptr [rax+rax+00h]
0x1800394a6  mov     r15, rax
0x1800394a9  mov     rbx, [rbp+57h+pv]
0x1800394ad  mov     [rbp+57h+var_50], r14
0x1800394b1  mov     [rbp+57h+var_80], r14
0x1800394b5  call    ?HasPackageQueryCapability@Feedback@Internal@Windows@@YAJXZ; Windows::Internal::Feedback::HasPackageQueryCapability(void)
0x1800394ba  test    eax, eax
0x1800394bc  js      loc_18003976E
0x1800394c2  test    rbx, rbx
0x1800394c5  jz      loc_18003986C
0x1800394cb  test    r15, r15
0x1800394ce  jz      loc_180039873
0x1800394d4  mov     [rbp+57h+var_78], r14
0x1800394d8  lea     r8, [rbp+57h+var_50]
0x1800394dc  mov     edx, 4010h
0x1800394e1  mov     rcx, rbx
0x1800394e4  call    cs:__imp_PicRetrieveFileInfo
0x1800394eb  nop     dword ptr [rax+rax+00h]
0x1800394f0  mov     ebx, eax
0x1800394f2  test    eax, eax
0x1800394f4  js      loc_18003989D
0x1800394fa  mov     rbx, [rbp+57h+var_50]
0x1800394fe  mov     rcx, [rbp+57h+var_80]
0x180039502  test    rcx, rcx
0x180039505  jz      short loc_180039518
0x180039507  mov     [rbp+57h+var_80], r14
0x18003950b  mov     rax, [rcx]
0x18003950e  mov     rax, [rax+10h]
0x180039512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039517  nop
0x180039518  mov     [rbp+57h+var_80], r14
0x18003951c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180039523  mov     ecx, 60h ; '`'; unsigned __int64
0x180039528  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003952d  test    rax, rax
0x180039530  jz      loc_1800397B1
0x180039536  mov     rcx, rax; this
0x180039539  call    ??0InternalFeedbackItem@Feedback@Internal@Windows@@QEAA@XZ; Windows::Internal::Feedback::InternalFeedbackItem::InternalFeedbackItem(void)
0x18003953e  mov     rsi, rax
0x180039541  mov     [rbp+57h+var_40], r14
0x180039545  mov     r13, [rbx]
0x180039548  mov     r12, [rbx+8]
0x18003954c  mov     r14, [rbx+10h]
0x180039550  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180039554  xor     eax, eax
0x180039556  inc     rdi
0x180039559  cmp     [r14+rdi*2], ax
0x18003955e  jnz     short loc_180039556
0x180039560  lea     rbx, [rsi+40h]
0x180039564  mov     rcx, [rbx]; string
0x180039567  call    cs:__imp_WindowsDeleteString
0x18003956e  nop     dword ptr [rax+rax+00h]
0x180039573  mov     qword ptr [rbx], 0
0x18003957a  mov     r8, rbx; string
0x18003957d  mov     edx, edi; length
0x18003957f  mov     rcx, r14; sourceString
0x180039582  call    cs:__imp_WindowsCreateString
0x180039589  nop     dword ptr [rax+rax+00h]
0x18003958e  mov     ebx, eax
0x180039590  xor     r14d, r14d
0x180039593  test    eax, eax
0x180039595  js      loc_18003975A
0x18003959b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003959f  inc     rdi
0x1800395a2  cmp     [r12+rdi*2], r14w
0x1800395a7  jnz     short loc_18003959F
0x1800395a9  lea     rbx, [rsi+48h]
0x1800395ad  mov     rcx, [rbx]; string
0x1800395b0  call    cs:__imp_WindowsDeleteString
0x1800395b7  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
