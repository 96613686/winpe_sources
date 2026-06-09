# GetInstalledContentIdsNoCV(Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *,Windows::Foundation::Collections::IVectorView<WindowsUpdate::Internal::ContentIdInfo *> * *)

- ea: `0x1801023b8`
- end: `0x180102a1a`
- name: `?GetInstalledContentIdsNoCV@@YAJPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@PEAPEAU?$IVectorView@PEAVContentIdInfo@Internal@WindowsUpdate@@@234@@Z`
- size: `1634`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800fc048`
- `0x180102358`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x18001c414`
- `0x18001c844`
- `0x180023f2c`
- `0x1800252e8`
- `0x18002cec8`
- `0x18003fe40`
- `0x1800da324`
- `0x180101c30`
- `0x180101e10`
- `0x180101e4c`
- `0x180101ec4`
- `0x1801023b8`
- `0x180103634`
- `0x1801deaf8`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180102a13`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180102a13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801026b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180102788`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180102937`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180102947`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801026b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180102788`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180102937`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180102947`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801026f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801027be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180102808`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801026f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801027be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180102808`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180102477`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180102477`

## string_xrefs

- `0x180102420`: `GetInstalledContentIdsNoCV`
- `0x180102722`: `GetInstalledContentIdsNoCV`
- `0x180102840`: `GetInstalledContentIdsNoCV`
- `0x180102909`: `GetInstalledContentIdsNoCV`
- `0x18010242a`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x18010272f`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x18010284d`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x180102916`: `onecoreuap\enduser\winstore\installservice\lib\appxhelpers.cpp`
- `0x1801028f9`: `Failed to add %s to list of installed ContentIDs`
- `0x18010270e`: `Package not installed: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall GetInstalledContentIdsNoCV(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rcx
  int v5; // eax
  int ActivationFactory; // esi
  __int64 v7; // rbx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  unsigned int i; // r15d
  __int64 v11; // rdi
  int (__fastcall *v12)(__int64, _QWORD, struct Windows::Internal::StateRepository::IPackage **); // rbx
  __int64 v13; // rdi
  int (__fastcall *v14)(__int64, __int64, __int64 *); // rbx
  int v15; // r14d
  struct Windows::Internal::StateRepository::IPackage *v16; // rdi
  int (__fastcall *v17)(struct Windows::Internal::StateRepository::IPackage *, __int64 *); // rbx
  __int64 v18; // rdi
  int (__fastcall *v19)(__int64, HSTRING *); // rbx
  PCWSTR v20; // rax
  int (__fastcall *v21)(__int64, HSTRING, HSTRING *); // rbx
  const WCHAR *StringRawBuffer; // rax
  unsigned __int64 v23; // r8
  PCWSTR v24; // rax
  unsigned __int64 v25; // rcx
  signed int v26; // eax
  unsigned int v27; // eax
  int v28; // eax
  int v30; // [rsp+28h] [rbp-D8h]
  __int64 v31; // [rsp+48h] [rbp-B8h]
  _BYTE v32[8]; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING string; // [rsp+68h] [rbp-98h] BYREF
  struct Windows::Internal::StateRepository::IPackage *v34; // [rsp+70h] [rbp-90h] BYREF
  HSTRING v35; // [rsp+78h] [rbp-88h] BYREF
  __int64 v36; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v37; // [rsp+88h] [rbp-78h] BYREF
  __int64 v38; // [rsp+90h] [rbp-70h] BYREF
  __int64 v39; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v40[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v41; // [rsp+A8h] [rbp-58h] BYREF
  int v42; // [rsp+ACh] [rbp-54h] BYREF
  int v43; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v44; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v45; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v46; // [rsp+C8h] [rbp-38h] BYREF
  struct Windows::Internal::StateRepository::IPackageUserStatics *v47; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v48; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v49; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v50; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v52; // [rsp+108h] [rbp+8h]
  HSTRING_HEADER v53; // [rsp+110h] [rbp+10h] BYREF
  __int64 v54; // [rsp+128h] [rbp+28h]
  WCHAR sourceString[40]; // [rsp+130h] [rbp+30h] BYREF

  *a2 = 0;
  v46 = 0;
  v48 = 0;
  v47 = 0;
  v39 = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v39);
  v5 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsUpdate::Internal::ContentIdInfo,Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::ContentIdInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::ContentIdInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::ContentIdInfo *>,0>>(
         v4,
         &v39);
  ActivationFactory = TraceHR(
                        "onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
                        0x63u,
                        "GetInstalledContentIdsNoCV",
                        "AgileVector<ContentIdInfo *>::Make(&contentIds)",
                        v5,
                        v30);
  if ( ActivationFactory >= 0 )
  {
    v52 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.StateRepository.TargetDeviceFamily",
      0x34u,
      0x33u);
    v7 = v52;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v46);
    ActivationFactory = RoGetActivationFactory(v7, &GUID_cb3a2a28_41c0_4687_9ea6_c248191321de, &v46);
    if ( ActivationFactory >= 0 )
    {
      v52 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Internal.StateRepository.Package",
        0x29u,
        0x28u);
      ActivationFactory = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
                            v52,
                            &v48);
      if ( ActivationFactory >= 0 )
      {
        v52 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Internal.StateRepository.PackageUser",
          0x2Du,
          0x2Cu);
        ActivationFactory = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageUserStatics>>(
                              v52,
                              &v47);
        if ( ActivationFactory >= 0 )
        {
          v44 = 0;
          v8 = v48;
          v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v48 + 192LL);
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v44);
          ActivationFactory = v9(v8, &v44);
          if ( ActivationFactory >= 0 )
          {
            v37 = 0;
            ActivationFactory = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v44 + 56LL))(v44, &v37);
            if ( ActivationFactory >= 0 )
            {
              for ( i = 0; i < v37; ++i )
              {
                v34 = 0;
                v11 = v44;
                v12 = *(int (__fastcall **)(__int64, _QWORD, struct Windows::Internal::StateRepository::IPackage **))(*(_QWORD *)v44 + 48LL);
                Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34);
                if ( v12(v11, i, &v34) >= 0 )
                {
                  v41 = 0;
                  if ( (*(int (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *, int *))(*(_QWORD *)v34 + 1000LL))(
                         v34,
                         &v41) >= 0
                    && (a1 || v41 == 2) )
                  {
                    v42 = 0;
                    if ( (*(int (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *, int *))(*(_QWORD *)v34 + 128LL))(
                           v34,
                           &v42) >= 0
                      && (v42 & 0x31) != 0 )
                    {
                      v49 = 0;
                      if ( (*(int (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *, __int64 *))(*(_QWORD *)v34 + 976LL))(
                             v34,
                             &v49) >= 0 )
                      {
                        v36 = 0;
                        v13 = v46;
                        v14 = *(int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v46 + 72LL);
                        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v36);
                        if ( v14(v13, v49, &v36) >= 0 )
                        {
                          v43 = 0;
                          if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v36 + 88LL))(v36, &v43) >= 0 )
                          {
                            if ( !v43 || (v15 = 0, v43 != 1) )
                              v15 = 2;
                            v38 = 0;
                            v16 = v34;
                            v17 = *(int (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *, __int64 *))(*(_QWORD *)v34 + 72LL);
                            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v38);
                            if ( v17(v16, &v38) >= 0 )
                            {
                              string = 0;
                              v18 = v38;
                              v19 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v38 + 88LL);
                              WindowsDeleteString(0);
                              string = 0;
                              if ( v19(v18, &string) >= 0 )
                              {
                                if ( PackageIsInstalled(v47, v34) )
                                {
                                  v35 = 0;
                                  if ( !a1
                                    || (v32[0] = 0,
                                        (*(int (__fastcall **)(__int64, HSTRING, _BYTE *))(*(_QWORD *)a1 + 64LL))(
                                          a1,
                                          string,
                                          v32) < 0)
                                    || v32[0]
                                    && (v21 = *(int (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)a1 + 48LL),
                                        WindowsDeleteString(v35),
                                        v35 = 0,
                                        v21(a1, string, &v35) >= 0) )
                                  {
                                    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = 0;
                                    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                                    if ( (int)GetContentId(StringRawBuffer) >= 0
                                      && GUIDToString((const struct _GUID *)&hstringHeader, sourceString, v23) >= 0
                                      && !(unsigned int)IsContentIdExcludedForUpdate(sourceString) )
                                    {
                                      v24 = WindowsGetStringRawBuffer(string, 0);
                                      LODWORD(v31) = v15;
                                      LogMessage(
                                        3u,
                                        "onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
                                        0x100u,
                                        "GetInstalledContentIdsNoCV",
                                        -1,
                                        L"PackageFamilyName: %s, type: %d, ContentId: %s",
                                        0,
                                        0,
                                        v24,
                                        v31,
                                        sourceString);
                                      v45 = 0;
                                      v50 = v35;
                                      v40[0] = 0;
                                      v25 = -1;
                                      do
                                        ++v25;
                                      while ( sourceString[v25] );
                                      v26 = ULongLongToUInt(v25, v40);
                                      if ( v26 < 0 )
                                      {
                                        RaiseException(v26, 1u, 0, 0);
                                        JUMPOUT(0x180102A19LL);
                                      }
                                      v27 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v40[0]);
                                      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                                        &v53,
                                        sourceString,
                                        v27,
                                        v40[0]);
                                      *(_QWORD *)v40 = v54;
                                      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v45);
                                      v28 = Microsoft::WRL::Details::MakeAndInitialize<WindowsUpdate::Internal::ContentIdInfo,WindowsUpdate::Internal::ContentIdInfo,HSTRING__ *,HSTRING__ *>(
                                              &v45,
                                              v40,
                                              &v50);
                                      if ( v28 < 0 )
                                        LogMessage(
                                          1u,
                                          "onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
                                          0x109u,
                                          "GetInstalledContentIdsNoCV",
                                          v28,
                                          L"Failed to add %s to list of installed ContentIDs",
                                          0,
                                          0,
                                          sourceString);
                                      else
                                        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 104LL))(v39, v45);
                                      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v45);
                                    }
                                  }
                                  WindowsDeleteString(v35);
                                  v35 = 0;
                                }
                                else
                                {
                                  v20 = WindowsGetStringRawBuffer(string, 0);
                                  LogMessage(
                                    4u,
                                    "onecoreuap\\enduser\\winstore\\installservice\\lib\\appxhelpers.cpp",
                                    0xD0u,
                                    "GetInstalledContentIdsNoCV",
                                    -1,
                                    L"Package not installed: %s",
                                    0,
                                    0,
                                    v20);
                                }
                              }
                              WindowsDeleteString(string);
                              string = 0;
                            }
                            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v38);
                          }
                        }
                        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v36);
                      }
                    }
                  }
                }
                Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34);
              }
              if ( (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v39 + 56LL))(v39, &v37) >= 0 )
                ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v39 + 64LL))(v39, a2);
            }
          }
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v44);
        }
      }
    }
  }
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v47);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v48);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v46);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1801023b8  mov     [rsp-8+arg_10], rbx
0x1801023bd  push    rbp
0x1801023be  push    rsi
0x1801023bf  push    rdi
0x1801023c0  push    r12
0x1801023c2  push    r13
0x1801023c4  push    r14
0x1801023c6  push    r15
0x1801023c8  lea     rbp, [rsp-90h]
0x1801023d0  sub     rsp, 190h
0x1801023d7  mov     rax, cs:__security_cookie
0x1801023de  xor     rax, rsp
0x1801023e1  mov     [rbp+0C0h+var_40], rax
0x1801023e8  mov     r13, rdx
0x1801023eb  mov     r12, rcx
0x1801023ee  xor     edi, edi
0x1801023f0  mov     [rdx], rdi
0x1801023f3  mov     [rbp+0C0h+var_F8], rdi
0x1801023f7  mov     [rbp+0C0h+var_E8], rdi
0x1801023fb  mov     [rbp+0C0h+var_F0], rdi
0x1801023ff  mov     [rbp+0C0h+var_128], rdi
0x180102403  lea     rcx, [rbp+0C0h+var_128]
0x180102407  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18010240c  lea     rdx, [rbp+0C0h+var_128]
0x180102410  call    ??$CreateExternalObjectVector@VContentIdInfo@Internal@WindowsUpdate@@V?$AgileVector@PEAVContentIdInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAVContentIdInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVContentIdInfo@Internal@WindowsUpdate@@@2567@$0A@@2Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVContentIdInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAVContentIdInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVContentIdInfo@Internal@WindowsUpdate@@@2567@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsUpdate::Internal::ContentIdInfo,Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::ContentIdInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::ContentIdInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::ContentIdInfo *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::ContentIdInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::ContentIdInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::ContentIdInfo *>,0> * *)
0x180102415  mov     [rsp+1C0h+var_1A0], eax; int
0x180102419  lea     r9, aAgilevectorCon; "AgileVector<ContentIdInfo *>::Make(&con"...
0x180102420  lea     r8, aGetinstalledco; "GetInstalledContentIdsNoCV"
0x180102427  lea     edx, [rdi+63h]; unsigned int
0x18010242a  lea     rcx, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180102431  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180102436  mov     esi, eax
0x180102438  test    eax, eax
0x18010243a  js      loc_1801029B4
0x180102440  mov     [rbp+0C0h+var_B8], rdi
0x180102444  lea     r9d, [rdi+33h]; unsigned int
0x180102448  lea     r8d, [rdi+34h]; unsigned int
0x18010244c  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_TargetDeviceFamily@@3QBGB; "Windows.Internal.StateRepository.Target"...
0x180102453  lea     rcx, [rbp+0C0h+hstringHeader]; hstringHeader
0x180102457  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18010245c  mov     rbx, [rbp+0C0h+var_B8]
0x180102460  lea     rcx, [rbp+0C0h+var_F8]
0x180102464  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180102469  lea     r8, [rbp+0C0h+var_F8]
0x18010246d  lea     rdx, _GUID_cb3a2a28_41c0_4687_9ea6_c248191321de
0x180102474  mov     rcx, rbx
0x180102477  call    cs:__imp_RoGetActivationFactory
0x18010247d  mov     esi, eax
0x18010247f  test    eax, eax
0x180102481  js      loc_1801029B4
0x180102487  mov     [rbp+0C0h+var_B8], rdi
0x18010248b  lea     r9d, [rdi+28h]; unsigned int
0x18010248f  lea     r8d, [rdi+29h]; unsigned int
0x180102493  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18010249a  lea     rcx, [rbp+0C0h+hstringHeader]; hstringHeader
0x18010249e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801024a3  lea     rdx, [rbp+0C0h+var_E8]
0x1801024a7  mov     rcx, [rbp+0C0h+var_B8]
0x1801024ab  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x1801024b0  mov     esi, eax
0x1801024b2  test    eax, eax
0x1801024b4  js      loc_1801029B4
0x1801024ba  mov     [rbp+0C0h+var_B8], rdi
0x1801024be  lea     r9d, [rdi+2Ch]; unsigned int
0x1801024c2  lea     r8d, [rdi+2Dh]; unsigned int
0x1801024c6  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_PackageUser@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x1801024cd  lea     rcx, [rbp+0C0h+hstringHeader]; hstringHeader
0x1801024d1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801024d6  lea     rdx, [rbp+0C0h+var_F0]
0x1801024da  mov     rcx, [rbp+0C0h+var_B8]
0x1801024de  call    ??$GetActivationFactory@V?$ComPtr@UIPackageUserStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageUserStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageUserStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageUserStatics>>)
0x1801024e3  mov     esi, eax
0x1801024e5  test    eax, eax
0x1801024e7  js      loc_1801029B4
0x1801024ed  mov     [rbp+0C0h+var_108], rdi
0x1801024f1  mov     rdi, [rbp+0C0h+var_E8]
0x1801024f5  mov     rax, [rdi]
0x1801024f8  mov     rbx, [rax+0C0h]
0x1801024ff  lea     rcx, [rbp+0C0h+var_108]
0x180102503  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180102508  lea     rdx, [rbp+0C0h+var_108]
0x18010250c  mov     rcx, rdi
0x18010250f  mov     rax, rbx
0x180102512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102517  mov     esi, eax
0x180102519  xor     edi, edi
0x18010251b  test    eax, eax
0x18010251d  js      loc_1801029AA
0x180102523  mov     [rbp+0C0h+var_138], edi
0x180102526  mov     rcx, [rbp+0C0h+var_108]
0x18010252a  mov     rax, [rcx]
0x18010252d  lea     rdx, [rbp+0C0h+var_138]
0x180102531  mov     rax, [rax+38h]
0x180102535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010253a  mov     esi, eax
0x18010253c  test    eax, eax
0x18010253e  js      loc_1801029AA
0x180102544  mov     r15d, edi
0x180102547  cmp     [rbp+0C0h+var_138], edi
0x18010254a  jbe     loc_18010297D
0x180102550  mov     [rsp+1C0h+var_150], rdi
0x180102555  mov     rdi, [rbp+0C0h+var_108]
0x180102559  mov     rax, [rdi]
0x18010255c  mov     rbx, [rax+30h]
0x180102560  lea     rcx, [rsp+1C0h+var_150]
0x180102565  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18010256a  lea     r8, [rsp+1C0h+var_150]
0x18010256f  mov     edx, r15d
0x180102572  mov     rcx, rdi
0x180102575  mov     rax, rbx
0x180102578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010257d  xor     edi, edi
0x18010257f  test    eax, eax
0x180102581  js      loc_180102966
0x180102587  mov     [rbp+0C0h+var_118], edi
0x18010258a  mov     rcx, [rsp+1C0h+var_150]
0x18010258f  mov     rax, [rcx]
0x180102592  lea     rdx, [rbp+0C0h+var_118]
0x180102596  mov     rax, [rax+3E8h]
0x18010259d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801025a2  test    eax, eax
0x1801025a4  js      loc_180102966
0x1801025aa  test    r12, r12
0x1801025ad  jnz     short loc_1801025B9
0x1801025af  cmp     [rbp+0C0h+var_118], 2
0x1801025b3  jnz     loc_180102966
0x1801025b9  mov     [rbp+0C0h+var_114], edi
0x1801025bc  mov     rcx, [rsp+1C0h+var_150]
0x1801025c1  mov     rax, [rcx]
0x1801025c4  lea     rdx, [rbp+0C0h+var_114]
0x1801025c8  mov     rax, [rax+80h]
0x1801025cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801025d4  test    eax, eax
0x1801025d6  js      loc_180102966
0x1801025dc  test    byte ptr [rbp+0C0h+var_114], 31h
0x1801025e0  jz      loc_180102966
0x1801025e6  mov     [rbp+0C0h+var_E0], rdi
0x1801025ea  mov     rcx, [rsp+1C0h+var_150]
0x1801025ef  mov     rax, [rcx]
0x1801025f2  lea     rdx, [rbp+0C0h+var_E0]
0x1801025f6  mov     rax, [rax+3D0h]
0x1801025fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102602  test    eax, eax
0x180102604  js      loc_180102966
0x18010260a  mov     [rbp+0C0h+var_140], rdi
0x18010260e  mov     rdi, [rbp+0C0h+var_F8]
0x180102612  mov     rax, [rdi]
0x180102615  mov     rbx, [rax+48h]
0x180102619  lea     rcx, [rbp+0C0h+var_140]
0x18010261d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180102622  lea     r8, [rbp+0C0h+var_140]
0x180102626  mov     rdx, [rbp+0C0h+var_E0]
0x18010262a  mov     rcx, rdi
0x18010262d  mov     rax, rbx
0x180102630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102635  xor     edi, edi
0x180102637  test    eax, eax
0x180102639  js      loc_18010295C
0x18010263f  mov     [rbp+0C0h+var_110], edi
0x180102642  mov     rcx, [rbp+0C0h+var_140]
0x180102646  mov     rax, [rcx]
0x180102649  lea     rdx, [rbp+0C0h+var_110]
0x18010264d  mov     rax, [rax+58h]
0x180102651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102656  test    eax, eax
0x180102658  js      loc_18010295C
0x18010265e  mov     ecx, [rbp+0C0h+var_110]
0x180102661  test    ecx, ecx
0x180102663  jz      short loc_18010266D
0x180102665  cmp     ecx, 1
0x180102668  mov     r14d, edi
0x18010266b  jz      short loc_180102673
0x18010266d  mov     r14d, 2
0x180102673  mov     [rbp+0C0h+var_130], rdi
0x180102677  mov     rdi, [rsp+1C0h+var_150]
0x18010267c  mov     rax, [rdi]
0x18010267f  mov     rbx, [rax+48h]
0x180102683  lea     rcx, [rbp+0C0h+var_130]
0x180102687  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18010268c  lea     rdx, [rbp+0C0h+var_130]
0x180102690  mov     rcx, rdi
0x180102693  mov     rax, rbx
0x180102696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010269b  xor     edi, edi
0x18010269d  test    eax, eax
0x18010269f  js      loc_180102952
0x1801026a5  mov     [rsp+1C0h+string], rdi
0x1801026aa  mov     rdi, [rbp+0C0h+var_130]
0x1801026ae  mov     rax, [rdi]
0x1801026b1  mov     rbx, [rax+58h]
0x1801026b5  xor     ecx, ecx; string
0x1801026b7  call    cs:__imp_WindowsDeleteString
0x1801026bd  mov     [rsp+1C0h+string], 0
0x1801026c6  lea     rdx, [rsp+1C0h+string]
0x1801026cb  mov     rcx, rdi
0x1801026ce  mov     rax, rbx
0x1801026d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801026d6  xor     edi, edi
0x1801026d8  test    eax, eax
0x1801026da  js      loc_180102942
0x1801026e0  mov     rdx, [rsp+1C0h+var_150]; struct Windows::Internal::StateRepository::IPackage *
0x1801026e5  mov     rcx, [rbp+0C0h+var_F0]; struct Windows::Internal::StateRepository::IPackageUserStatics *
0x1801026e9  call    ?PackageIsInstalled@@YA_NPEAUIPackageUserStatics@StateRepository@Internal@Windows@@PEAUIPackage@234@@Z; PackageIsInstalled(Windows::Internal::StateRepository::IPackageUserStatics *,Windows::Internal::StateRepository::IPackage *)
0x1801026ee  test    al, al
0x1801026f0  jnz     short loc_180102743
0x1801026f2  xor     edx, edx; length
0x1801026f4  mov     rcx, [rsp+1C0h+string]; string
0x1801026f9  call    cs:__imp_WindowsGetStringRawBuffer
0x1801026ff  mov     [rsp+1C0h+var_180], rax
0x180102704  mov     [rsp+1C0h+var_188], rdi; unsigned __int16 *
0x180102709  mov     [rsp+1C0h+var_190], rdi; char *
0x18010270e  lea     rax, aPackageNotInst_0; "Package not installed: %s"
0x180102715  mov     [rsp+1C0h+var_198], rax; unsigned __int16 *
0x18010271a  mov     [rsp+1C0h+var_1A0], 0FFFFFFFFh; int
0x180102722  lea     r9, aGetinstalledco; "GetInstalledContentIdsNoCV"
0x180102729  mov     r8d, 0D0h; unsigned int
0x18010272f  lea     rdx, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180102736  lea     ecx, [rdi+4]; unsigned int
0x180102739  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18010273e  jmp     loc_180102942
0x180102743  mov     [rsp+1C0h+var_148], rdi
0x180102748  test    r12, r12
0x18010274b  jz      short loc_1801027B0
0x18010274d  mov     [rsp+1C0h+var_160], dil
0x180102752  mov     rax, [r12]
0x180102756  lea     r8, [rsp+1C0h+var_160]
0x18010275b  mov     rdx, [rsp+1C0h+string]
0x180102760  mov     rcx, r12
0x180102763  mov     rax, [rax+40h]
0x180102767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010276c  test    eax, eax
0x18010276e  js      short loc_1801027B0
0x180102770  cmp     [rsp+1C0h+var_160], dil
0x180102775  jz      loc_180102932
0x18010277b  mov     rax, [r12]
0x18010277f  mov     rbx, [rax+30h]
0x180102783  mov     rcx, [rsp+1C0h+var_148]; string
0x180102788  call    cs:__imp_WindowsDeleteString
0x18010278e  mov     [rsp+1C0h+var_148], rdi
0x180102793  lea     r8, [rsp+1C0h+var_148]
0x180102798  mov     rdx, [rsp+1C0h+string]
0x18010279d  mov     rcx, r12
0x1801027a0  mov     rax, rbx
0x1801027a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801027a8  test    eax, eax
0x1801027aa  js      loc_180102932
0x1801027b0  xorps   xmm0, xmm0
0x1801027b3  movups  xmmword ptr [rbp+0C0h+hstringHeader.Reserved], xmm0
0x1801027b7  xor     edx, edx; length
0x1801027b9  mov     rcx, [rsp+1C0h+string]; string
0x1801027be  call    cs:__imp_WindowsGetStringRawBuffer
0x1801027c4  lea     r8, [rbp+0C0h+hstringHeader]
0x1801027c8  mov     edx, r14d
0x1801027cb  mov     rcx, rax; packageFamilyName
0x1801027ce  call    GetContentId
0x1801027d3  test    eax, eax
0x1801027d5  js      loc_180102932
0x1801027db  lea     rdx, [rbp+0C0h+sourceString]; unsigned __int16 *
0x1801027df  lea     rcx, [rbp+0C0h+hstringHeader]; struct _GUID *
0x1801027e3  call    ?GUIDToString@@YAJAEBU_GUID@@PEAG_K@Z; GUIDToString(_GUID const &,ushort *,unsigned __int64)
0x1801027e8  test    eax, eax
0x1801027ea  js      loc_180102932
0x1801027f0  lea     rcx, [rbp+0C0h+sourceString]; SubStr
0x1801027f4  call    ?IsContentIdExcludedForUpdate@@YAHPEBG@Z; IsContentIdExcludedForUpdate(ushort const *)
0x1801027f9  test    eax, eax
0x1801027fb  jnz     loc_180102932
0x180102801  xor     edx, edx; length
0x180102803  mov     rcx, [rsp+1C0h+string]; string
0x180102808  call    cs:__imp_WindowsGetStringRawBuffer
0x18010280e  lea     rcx, [rbp+0C0h+sourceString]
0x180102812  mov     [rsp+1C0h+var_170], rcx
0x180102817  mov     dword ptr [rsp+1C0h+var_178], r14d
0x18010281c  mov     [rsp+1C0h+var_180], rax
0x180102821  mov     [rsp+1C0h+var_188], rdi; unsigned __int16 *
0x180102826  mov     [rsp+1C0h+var_190], rdi; char *
0x18010282b  lea     rax, aPackagefamilyn_4; "PackageFamilyName: %s, type: %d, Conten"...
0x180102832  mov     [rsp+1C0h+var_198], rax; unsigned __int16 *
0x180102837  or      r14, 0FFFFFFFFFFFFFFFFh
0x18010283b  mov     [rsp+1C0h+var_1A0], r14d; int
0x180102840  lea     r9, aGetinstalledco; "GetInstalledContentIdsNoCV"
0x180102847  mov     r8d, 100h; unsigned int
0x18010284d  lea     rdx, aOnecoreuapEndu_54; "onecoreuap\\enduser\\winstore\\installs"...
0x180102854  lea     ecx, [r14+4]; unsigned int
0x180102858  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18010285d  mov     [rbp+0C0h+var_100], rdi
0x180102861  mov     rax, [rsp+1C0h+var_148]
0x180102866  mov     [rbp+0C0h+var_D8], rax
0x18010286a  mov     [rbp+0C0h+var_120], edi
0x18010286d  lea     rax, [rbp+0C0h+sourceString]
0x180102871  mov     rcx, r14
0x180102874  inc     rcx; unsigned __int64
0x180102877  cmp     [rax+rcx*2], di
0x18010287b  jnz     short loc_180102874
0x18010287d  lea     rdx, [rbp+0C0h+var_120]; unsigned int *
0x180102881  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180102886  test    eax, eax
0x180102888  js      loc_180102A07
0x18010288e  mov     ecx, [rbp+0C0h+var_120]; unsigned int
0x180102891  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180102896  mov     r9d, [rbp+0C0h+var_120]; unsigned int
  ... truncated ...
```
