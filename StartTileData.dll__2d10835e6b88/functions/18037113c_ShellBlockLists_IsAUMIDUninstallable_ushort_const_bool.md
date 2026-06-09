# ShellBlockLists::IsAUMIDUninstallable(ushort const *,bool *)

- ea: `0x18037113c`
- end: `0x180371578`
- name: `?IsAUMIDUninstallable@ShellBlockLists@@YAJPEBGPEA_N@Z`
- size: `1084`
- prototype: `__int64 __fastcall(LPCWCH lpString2, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18036de84`

## callees

- `0x18000ce94`
- `0x18004ffc0`
- `0x1800db710`
- `0x1801f9f20`
- `0x180201e50`
- `0x18037113c`
- `0x180371580`
- `0x180372d98`
- `0x180372ec4`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1803711f5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180371234`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180371273`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1803712a9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18037138c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1803714c9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1803714f7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1803711f5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180371234`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180371273`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1803712a9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18037138c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1803714c9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1803714f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180371489`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037150e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180371537`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180371489`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037150e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180371537`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803714ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803714ae`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180371301`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1803713ca`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180371301`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1803713ca`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x180371199`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x180371199`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ShellBlockLists::IsAUMIDUninstallable(LPCWCH lpString2, unsigned __int16 *a2, bool *a3)
{
  DWORD v5; // eax
  const unsigned __int16 *const near *const *v6; // rdx
  unsigned int v7; // edi
  unsigned __int64 v8; // r14
  unsigned int v9; // ebx
  ShellBlockLists *v10; // rcx
  unsigned int i; // ebx
  LPCWCH *v12; // rdi
  bool v13; // bl
  LPCWCH *v14; // rbx
  int v15; // edi
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  const WCHAR *StringRawBuffer; // rax
  int v19; // ebx
  HSTRING string[2]; // [rsp+30h] [rbp-39h] BYREF
  int v22; // [rsp+40h] [rbp-29h] BYREF
  int v23; // [rsp+44h] [rbp-25h]
  int v24; // [rsp+48h] [rbp-21h]
  int v25; // [rsp+4Ch] [rbp-1Dh]
  __int64 v26; // [rsp+50h] [rbp-19h] BYREF
  __int64 v27; // [rsp+58h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-9h] BYREF
  __int64 v29; // [rsp+78h] [rbp+Fh]

  *(_BYTE *)a2 = 1;
  v5 = `ShellBlockLists::detail::IsCloudEdition'::`2'::s_dwProductType;
  if ( !`ShellBlockLists::detail::IsCloudEdition'::`2'::s_dwProductType )
  {
    if ( GetProductInfo(0xAu, 0, 0, 0, &`ShellBlockLists::detail::IsCloudEdition'::`2'::s_dwProductType) )
    {
      v5 = `ShellBlockLists::detail::IsCloudEdition'::`2'::s_dwProductType;
    }
    else
    {
      v5 = 0;
      `ShellBlockLists::detail::IsCloudEdition'::`2'::s_dwProductType = 0;
    }
  }
  v6 = &ShellBlockLists::AppsThatCantBeUninstalledFromCloudEdition;
  v7 = v5 - 202 <= 1 ? 0x19 : 0;
  v8 = (unsigned __int64)&ShellBlockLists::AppsThatCantBeUninstalledFromCloudEdition & -(__int64)(v5 - 202 <= 1);
  if ( v8 )
  {
    v9 = 0;
    if ( v7 )
    {
      while ( CompareStringOrdinal(*(LPCWCH *)(v8 + 8LL * v9), -1, lpString2, -1, 1) != 2 )
      {
        if ( ++v9 >= v7 )
          goto LABEL_9;
      }
LABEL_41:
      *(_BYTE *)a2 = 0;
      return 0;
    }
  }
LABEL_9:
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableUninstallSystemComponentsForDMARegions>::__private_IsEnabled(
                           `wil::Feature<__WilFeatureTraits_Feature_EnableUninstallSystemComponentsForDMARegions>::GetImpl'::`2'::impl,
                           v6,
                           a3)
    || CompareStringOrdinal(L"Microsoft.WindowsStore_8wekyb3d8bbwe!App", -1, lpString2, -1, 1) != 2
    || !ShellBlockLists::IsMicrosoftStoreUninstallable(v10) )
  {
    for ( i = 0; i < 0x4F; ++i )
    {
      if ( CompareStringOrdinal((LPCWCH)(&ShellBlockLists::AppsThatCantBeUninstalledAnywhere)[i], -1, lpString2, -1, 1) == 2 )
        goto LABEL_41;
    }
    v12 = (LPCWCH *)&ShellBlockLists::SearchAppsThatCantBeUninstalledOnNonDMARegion;
    while ( 1 )
    {
      if ( CompareStringOrdinal(*v12, -1, lpString2, -1, 1) == 2 )
      {
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_40979072>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_40979072>::GetImpl'::`2'::impl) )
          goto LABEL_41;
        v13 = 0;
        v26 = 0;
        v29 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Internal.System.Profile.RegionPolicyEvaluator",
          0x36u,
          0x35u);
        if ( (int)RoGetActivationFactory(v29, &GUID_1ca20398_c1d9_5f12_b40a_6528206e3b5e, &v26) >= 0 )
        {
          LODWORD(string[0]) = 0;
          v22 = -227060220;
          v23 = 1288860572;
          v24 = 82535300;
          v25 = -141853169;
          if ( (*(int (__fastcall **)(__int64, int *, HSTRING *))(*(_QWORD *)v26 + 48LL))(v26, &v22, string) >= 0 )
            v13 = LODWORD(string[0]) <= 1;
        }
        wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0>,wil::err_exception_policy>(&v26);
        if ( !v13 )
          goto LABEL_41;
      }
      if ( ++v12 == (LPCWCH *)&ShellBlockLists::AppsThatCantBeUninstalledAnywhere )
      {
        v14 = (LPCWCH *)&ShellBlockLists::StartExperiencesAppsThatCantBeUninstalledOnNonDMARegion;
        while ( 1 )
        {
          if ( CompareStringOrdinal(*v14, -1, lpString2, -1, 1) == 2 )
          {
            v26 = 0;
            v29 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(
              &hstringHeader,
              L"Windows.Internal.System.Profile.RegionPolicyEvaluator",
              0x36u,
              0x35u);
            if ( (int)RoGetActivationFactory(v29, &GUID_1ca20398_c1d9_5f12_b40a_6528206e3b5e, &v26) < 0
              || (LODWORD(string[0]) = 0,
                  v22 = -951338663,
                  v23 = 1268512611,
                  v24 = 829101211,
                  v25 = 935981613,
                  (*(int (__fastcall **)(__int64, int *, HSTRING *))(*(_QWORD *)v26 + 48LL))(v26, &v22, string) < 0)
              || LODWORD(string[0]) > 1 )
            {
              *(_BYTE *)a2 = 0;
              wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0>,wil::err_exception_policy>(&v26);
              return 0;
            }
            wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0>,wil::err_exception_policy>(&v26);
          }
          if ( ++v14 == (LPCWCH *)&ShellBlockLists::AppsThatCantBeUninstalledOutsideOfChina )
          {
            v27 = 0;
            v29 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(
              &hstringHeader,
              L"Windows.Globalization.GeographicRegion",
              0x27u,
              0x26u);
            v15 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Globalization::IGeographicRegion>>(
                    v29,
                    &v27);
            if ( v15 >= 0 )
            {
              string[0] = 0;
              v16 = v27;
              v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v27 + 56LL);
              WindowsDeleteString(0);
              string[0] = 0;
              v15 = v17(v16, string);
              if ( v15 >= 0 )
              {
                StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
                if ( CompareStringOrdinal(StringRawBuffer, -1, L"CN", -1, 1) != 2 )
                {
                  v19 = 0;
                  while ( CompareStringOrdinal(
                            (LPCWCH)(&ShellBlockLists::AppsThatCantBeUninstalledOutsideOfChina)[v19],
                            -1,
                            lpString2,
                            -1,
                            1) != 2 )
                  {
                    if ( (unsigned int)++v19 >= 2 )
                      goto LABEL_37;
                  }
                  *(_BYTE *)a2 = 0;
                  WindowsDeleteString(string[0]);
                  string[0] = 0;
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
                  return 0;
                }
              }
LABEL_37:
              WindowsDeleteString(string[0]);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
            return (unsigned int)v15;
          }
        }
      }
    }
  }
  *(_BYTE *)a2 = 1;
  return 0;
}

```

## disassembly

```asm
0x18037113c  mov     [rsp-8+arg_10], rbx
0x180371141  push    rbp
0x180371142  push    rsi
0x180371143  push    rdi
0x180371144  push    r12
0x180371146  push    r13
0x180371148  push    r14
0x18037114a  push    r15
0x18037114c  lea     rbp, [rsp-27h]
0x180371151  sub     rsp, 90h
0x180371158  mov     rax, cs:__security_cookie
0x18037115f  xor     rax, rsp
0x180371162  mov     [rbp+57h+var_40], rax
0x180371166  mov     rsi, rdx
0x180371169  mov     r15, rcx
0x18037116c  mov     r13d, 1
0x180371172  mov     [rdx], r13b
0x180371175  mov     eax, cs:?s_dwProductType@?1??IsCloudEdition@detail@ShellBlockLists@@YA?B_NXZ@4KA; ulong `ShellBlockLists::detail::IsCloudEdition(void)'::`2'::s_dwProductType
0x18037117b  xor     r12d, r12d
0x18037117e  test    eax, eax
0x180371180  jnz     short loc_1803711B4
0x180371182  lea     rax, ?s_dwProductType@?1??IsCloudEdition@detail@ShellBlockLists@@YA?B_NXZ@4KA; ulong `ShellBlockLists::detail::IsCloudEdition(void)'::`2'::s_dwProductType
0x180371189  mov     [rsp+0C0h+pdwReturnedProductType], rax; pdwReturnedProductType
0x18037118e  xor     r9d, r9d; dwSpMinorVersion
0x180371191  xor     r8d, r8d; dwSpMajorVersion
0x180371194  xor     edx, edx; dwOSMinorVersion
0x180371196  lea     ecx, [rdx+0Ah]; dwOSMajorVersion
0x180371199  call    cs:__imp_GetProductInfo
0x18037119f  test    eax, eax
0x1803711a1  jnz     short loc_1803711AE
0x1803711a3  mov     eax, r12d
0x1803711a6  mov     cs:?s_dwProductType@?1??IsCloudEdition@detail@ShellBlockLists@@YA?B_NXZ@4KA, eax; ulong `ShellBlockLists::detail::IsCloudEdition(void)'::`2'::s_dwProductType
0x1803711ac  jmp     short loc_1803711B4
0x1803711ae  mov     eax, cs:?s_dwProductType@?1??IsCloudEdition@detail@ShellBlockLists@@YA?B_NXZ@4KA; ulong `ShellBlockLists::detail::IsCloudEdition(void)'::`2'::s_dwProductType
0x1803711b4  add     eax, 0FFFFFF36h
0x1803711b9  cmp     eax, r13d
0x1803711bc  setbe   cl
0x1803711bf  mov     al, cl
0x1803711c1  lea     rdx, ?AppsThatCantBeUninstalledFromCloudEdition@ShellBlockLists@@3QBQEBGB; ushort const * const near * const ShellBlockLists::AppsThatCantBeUninstalledFromCloudEdition
0x1803711c8  neg     al
0x1803711ca  sbb     r14, r14
0x1803711cd  neg     cl
0x1803711cf  sbb     edi, edi
0x1803711d1  and     edi, 19h
0x1803711d4  and     r14, rdx
0x1803711d7  jz      short loc_18037120B
0x1803711d9  mov     ebx, r12d
0x1803711dc  test    edi, edi
0x1803711de  jz      short loc_18037120B
0x1803711e0  mov     ecx, ebx
0x1803711e2  mov     dword ptr [rsp+0C0h+pdwReturnedProductType], r13d; bIgnoreCase
0x1803711e7  or      r9d, 0FFFFFFFFh; cchCount2
0x1803711eb  mov     r8, r15; lpString2
0x1803711ee  or      edx, r9d; cchCount1
0x1803711f1  mov     rcx, [r14+rcx*8]; lpString1
0x1803711f5  call    cs:__imp_CompareStringOrdinal
0x1803711fb  cmp     eax, 2
0x1803711fe  jz      loc_18037154C
0x180371204  add     ebx, r13d
0x180371207  cmp     ebx, edi
0x180371209  jb      short loc_1803711E0
0x18037120b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableUninstallSystemComponentsForDMARegions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableUninstallSystemComponentsForDMARegions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableUninstallSystemComponentsForDMARegions> `wil::Feature<__WilFeatureTraits_Feature_EnableUninstallSystemComponentsForDMARegions>::GetImpl(void)'::`2'::impl
0x180371212  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableUninstallSystemComponentsForDMARegions@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableUninstallSystemComponentsForDMARegions>::__private_IsEnabled(void)
0x180371217  or      r14d, 0FFFFFFFFh
0x18037121b  test    al, al
0x18037121d  jz      short loc_180371250
0x18037121f  mov     dword ptr [rsp+0C0h+pdwReturnedProductType], r13d; bIgnoreCase
0x180371224  mov     r9d, r14d; cchCount2
0x180371227  mov     r8, r15; lpString2
0x18037122a  mov     edx, r14d; cchCount1
0x18037122d  lea     rcx, aMicrosoftWindo_32; "Microsoft.WindowsStore_8wekyb3d8bbwe!Ap"...
0x180371234  call    cs:__imp_CompareStringOrdinal
0x18037123a  cmp     eax, 2
0x18037123d  jnz     short loc_180371250
0x18037123f  call    ?IsMicrosoftStoreUninstallable@ShellBlockLists@@YA_NXZ; ShellBlockLists::IsMicrosoftStoreUninstallable(void)
0x180371244  test    al, al
0x180371246  jz      short loc_180371250
0x180371248  mov     [rsi], r13b
0x18037124b  jmp     loc_18037154F
0x180371250  mov     ebx, r12d
0x180371253  lea     rax, __ImageBase
0x18037125a  movsxd  rcx, ebx
0x18037125d  mov     dword ptr [rsp+0C0h+pdwReturnedProductType], r13d; bIgnoreCase
0x180371262  mov     r9d, r14d; cchCount2
0x180371265  mov     r8, r15; lpString2
0x180371268  mov     edx, r14d; cchCount1
0x18037126b  mov     rcx, ds:rva ?AppsThatCantBeUninstalledAnywhere@ShellBlockLists@@3QBQEBGB[rax+rcx*8]; lpString1
0x180371273  call    cs:__imp_CompareStringOrdinal
0x180371279  cmp     eax, 2
0x18037127c  jz      loc_18037154C
0x180371282  add     ebx, r13d
0x180371285  cmp     ebx, 4Fh ; 'O'
0x180371288  lea     rax, __ImageBase
0x18037128f  jb      short loc_18037125A
0x180371291  lea     rdi, ?SearchAppsThatCantBeUninstalledOnNonDMARegion@ShellBlockLists@@3QBQEBGB; ushort const * const near * const ShellBlockLists::SearchAppsThatCantBeUninstalledOnNonDMARegion
0x180371298  mov     dword ptr [rsp+0C0h+pdwReturnedProductType], r13d; bIgnoreCase
0x18037129d  mov     r9d, r14d; cchCount2
0x1803712a0  mov     r8, r15; lpString2
0x1803712a3  mov     edx, r14d; cchCount1
0x1803712a6  mov     rcx, [rdi]; lpString1
0x1803712a9  call    cs:__imp_CompareStringOrdinal
0x1803712af  cmp     eax, 2
0x1803712b2  jnz     loc_180371360
0x1803712b8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_40979072@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_40979072@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40979072> `wil::Feature<__WilFeatureTraits_Feature_40979072>::GetImpl(void)'::`2'::impl
0x1803712bf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_40979072@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40979072>::__private_IsEnabled(void)
0x1803712c4  test    al, al
0x1803712c6  jz      loc_18037154C
0x1803712cc  movzx   ebx, r12b
0x1803712d0  mov     [rbp+57h+var_70], r12
0x1803712d4  mov     [rbp+57h+var_48], r12
0x1803712d8  mov     r9d, 35h ; '5'; unsigned int
0x1803712de  lea     r8d, [r9+1]; unsigned int
0x1803712e2  lea     rdx, ?RuntimeClass_Windows_Internal_System_Profile_RegionPolicyEvaluator@@3QBGB; "Windows.Internal.System.Profile.RegionP"...
0x1803712e9  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1803712ed  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1803712f2  lea     r8, [rbp+57h+var_70]
0x1803712f6  lea     rdx, _GUID_1ca20398_c1d9_5f12_b40a_6528206e3b5e
0x1803712fd  mov     rcx, [rbp+57h+var_48]
0x180371301  call    cs:__imp_RoGetActivationFactory
0x180371307  test    eax, eax
0x180371309  js      short loc_18037134F
0x18037130b  mov     dword ptr [rbp+57h+string], r12d
0x18037130f  mov     rcx, [rbp+57h+var_70]
0x180371313  mov     [rbp+57h+var_80], 0F2775604h
0x18037131a  mov     [rbp+57h+var_7C], 4CD2739Ch
0x180371321  mov     [rbp+57h+var_78], 4EB6384h
0x180371328  mov     [rbp+57h+var_74], 0F78B7E0Fh
0x18037132f  mov     rax, [rcx]
0x180371332  lea     r8, [rbp+57h+string]
0x180371336  lea     rdx, [rbp+57h+var_80]
0x18037133a  mov     rax, [rax+30h]
0x18037133e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180371343  test    eax, eax
0x180371345  js      short loc_18037134F
0x180371347  cmp     dword ptr [rbp+57h+string], r13d
0x18037134b  cmovbe  ebx, r13d
0x18037134f  lea     rcx, [rbp+57h+var_70]
0x180371353  call    ??1?$com_ptr_t@V?$AgileVector@PEAVAppInstallInfoRecord@ContentManagement@@U?$DefaultEqualityPredicate@PEAVAppInstallInfoRecord@ContentManagement@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVAppInstallInfoRecord@ContentManagement@@@4567@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0>,wil::err_exception_policy>(void)
0x180371358  test    bl, bl
0x18037135a  jz      loc_18037154C
0x180371360  add     rdi, 8
0x180371364  lea     rax, ?AppsThatCantBeUninstalledAnywhere@ShellBlockLists@@3QBQEBGB; ushort const * const near * const ShellBlockLists::AppsThatCantBeUninstalledAnywhere
0x18037136b  cmp     rdi, rax
0x18037136e  jnz     loc_180371298
0x180371374  lea     rbx, ?StartExperiencesAppsThatCantBeUninstalledOnNonDMARegion@ShellBlockLists@@3QBQEBGB; ushort const * const near * const ShellBlockLists::StartExperiencesAppsThatCantBeUninstalledOnNonDMARegion
0x18037137b  mov     dword ptr [rsp+0C0h+pdwReturnedProductType], r13d; bIgnoreCase
0x180371380  mov     r9d, r14d; cchCount2
0x180371383  mov     r8, r15; lpString2
0x180371386  mov     edx, r14d; cchCount1
0x180371389  mov     rcx, [rbx]; lpString1
0x18037138c  call    cs:__imp_CompareStringOrdinal
0x180371392  cmp     eax, 2
0x180371395  jnz     loc_18037142B
0x18037139b  mov     [rbp+57h+var_70], r12
0x18037139f  mov     [rbp+57h+var_48], r12
0x1803713a3  lea     r9d, [rax+33h]; unsigned int
0x1803713a7  lea     r8d, [rax+34h]; unsigned int
0x1803713ab  lea     rdx, ?RuntimeClass_Windows_Internal_System_Profile_RegionPolicyEvaluator@@3QBGB; "Windows.Internal.System.Profile.RegionP"...
0x1803713b2  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1803713b6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1803713bb  lea     r8, [rbp+57h+var_70]
0x1803713bf  lea     rdx, _GUID_1ca20398_c1d9_5f12_b40a_6528206e3b5e
0x1803713c6  mov     rcx, [rbp+57h+var_48]
0x1803713ca  call    cs:__imp_RoGetActivationFactory
0x1803713d0  test    eax, eax
0x1803713d2  js      loc_180371522
0x1803713d8  mov     dword ptr [rbp+57h+string], r12d
0x1803713dc  mov     rcx, [rbp+57h+var_70]
0x1803713e0  mov     [rbp+57h+var_80], 0C74BB959h
0x1803713e7  mov     [rbp+57h+var_7C], 4B9BF763h
0x1803713ee  mov     [rbp+57h+var_78], 316B149Bh
0x1803713f5  mov     [rbp+57h+var_74], 37C9F22Dh
0x1803713fc  mov     rax, [rcx]
0x1803713ff  lea     r8, [rbp+57h+string]
0x180371403  lea     rdx, [rbp+57h+var_80]
0x180371407  mov     rax, [rax+30h]
0x18037140b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180371410  test    eax, eax
0x180371412  js      loc_180371522
0x180371418  cmp     dword ptr [rbp+57h+string], r13d
0x18037141c  ja      loc_180371522
0x180371422  lea     rcx, [rbp+57h+var_70]
0x180371426  call    ??1?$com_ptr_t@V?$AgileVector@PEAVAppInstallInfoRecord@ContentManagement@@U?$DefaultEqualityPredicate@PEAVAppInstallInfoRecord@ContentManagement@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVAppInstallInfoRecord@ContentManagement@@@4567@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0>,wil::err_exception_policy>(void)
0x18037142b  add     rbx, 8
0x18037142f  lea     rax, ?AppsThatCantBeUninstalledOutsideOfChina@ShellBlockLists@@3QBQEBGB; ushort const * const near * const ShellBlockLists::AppsThatCantBeUninstalledOutsideOfChina
0x180371436  cmp     rbx, rax
0x180371439  jnz     loc_18037137B
0x18037143f  mov     [rbp+57h+var_68], r12
0x180371443  mov     [rbp+57h+var_48], r12
0x180371447  mov     r9d, 26h ; '&'; unsigned int
0x18037144d  lea     r8d, [r9+1]; unsigned int
0x180371451  lea     rdx, ?RuntimeClass_Windows_Globalization_GeographicRegion@@3QBGB; "Windows.Globalization.GeographicRegion"
0x180371458  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18037145c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180371461  lea     rdx, [rbp+57h+var_68]
0x180371465  mov     rcx, [rbp+57h+var_48]
0x180371469  call    ??$ActivateInstance@V?$ComPtr@UIGeographicRegion@Globalization@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIGeographicRegion@Globalization@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Globalization::IGeographicRegion>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Globalization::IGeographicRegion>>)
0x18037146e  mov     edi, eax
0x180371470  test    eax, eax
0x180371472  js      loc_180371515
0x180371478  mov     [rbp+57h+string], r12
0x18037147c  mov     rdi, [rbp+57h+var_68]
0x180371480  mov     rax, [rdi]
0x180371483  mov     rbx, [rax+38h]
0x180371487  xor     ecx, ecx; string
0x180371489  call    cs:__imp_WindowsDeleteString
0x18037148f  mov     [rbp+57h+string], r12
0x180371493  lea     rdx, [rbp+57h+string]
0x180371497  mov     rcx, rdi
0x18037149a  mov     rax, rbx
0x18037149d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803714a2  mov     edi, eax
0x1803714a4  test    eax, eax
0x1803714a6  js      short loc_18037150A
0x1803714a8  xor     edx, edx; length
0x1803714aa  mov     rcx, [rbp+57h+string]; string
0x1803714ae  call    cs:__imp_WindowsGetStringRawBuffer
0x1803714b4  mov     dword ptr [rsp+0C0h+pdwReturnedProductType], r13d; bIgnoreCase
0x1803714b9  mov     r9d, r14d; cchCount2
0x1803714bc  lea     r8, aCn; "CN"
0x1803714c3  mov     edx, r14d; cchCount1
0x1803714c6  mov     rcx, rax; lpString1
0x1803714c9  call    cs:__imp_CompareStringOrdinal
0x1803714cf  cmp     eax, 2
0x1803714d2  jz      short loc_18037150A
0x1803714d4  mov     ebx, r12d
0x1803714d7  movsxd  rcx, ebx
0x1803714da  mov     dword ptr [rsp+0C0h+pdwReturnedProductType], r13d; bIgnoreCase
0x1803714df  mov     r9d, r14d; cchCount2
0x1803714e2  mov     r8, r15; lpString2
0x1803714e5  mov     edx, r14d; cchCount1
0x1803714e8  lea     rax, __ImageBase
0x1803714ef  mov     rcx, ds:rva ?AppsThatCantBeUninstalledOutsideOfChina@ShellBlockLists@@3QBQEBGB[rax+rcx*8]; lpString1
0x1803714f7  call    cs:__imp_CompareStringOrdinal
0x1803714fd  cmp     eax, 2
0x180371500  jz      short loc_180371530
0x180371502  add     ebx, r13d
0x180371505  cmp     ebx, 2
0x180371508  jb      short loc_1803714D7
0x18037150a  mov     rcx, [rbp+57h+string]; string
0x18037150e  call    cs:__imp_WindowsDeleteString
0x180371514  nop
0x180371515  lea     rcx, [rbp+57h+var_68]
0x180371519  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18037151e  mov     eax, edi
0x180371520  jmp     short loc_180371551
0x180371522  mov     [rsi], r12b
0x180371525  lea     rcx, [rbp+57h+var_70]
0x180371529  call    ??1?$com_ptr_t@V?$AgileVector@PEAVAppInstallInfoRecord@ContentManagement@@U?$DefaultEqualityPredicate@PEAVAppInstallInfoRecord@ContentManagement@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVAppInstallInfoRecord@ContentManagement@@@4567@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<ContentManagement::AppInstallInfoRecord *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<ContentManagement::AppInstallInfoRecord *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<ContentManagement::AppInstallInfoRecord *>,0>,wil::err_exception_policy>(void)
0x18037152e  jmp     short loc_18037154F
0x180371530  mov     [rsi], r12b
0x180371533  mov     rcx, [rbp+57h+string]; string
0x180371537  call    cs:__imp_WindowsDeleteString
0x18037153d  mov     [rbp+57h+string], r12
0x180371541  lea     rcx, [rbp+57h+var_68]
0x180371545  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18037154a  jmp     short loc_18037154F
0x18037154c  mov     [rsi], r12b
0x18037154f  xor     eax, eax
0x180371551  mov     rcx, [rbp+57h+var_40]
0x180371555  xor     rcx, rsp; StackCookie
0x180371558  call    __security_check_cookie
0x18037155d  mov     rbx, [rsp+0C0h+arg_10]
0x180371565  add     rsp, 90h
0x18037156c  pop     r15
0x18037156e  pop     r14
0x180371570  pop     r13
0x180371572  pop     r12
0x180371574  pop     rdi
0x180371575  pop     rsi
0x180371576  pop     rbp
0x180371577  retn
```
