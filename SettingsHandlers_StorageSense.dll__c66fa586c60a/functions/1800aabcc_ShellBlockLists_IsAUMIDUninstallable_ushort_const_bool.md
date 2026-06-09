# ShellBlockLists::IsAUMIDUninstallable(ushort const *,bool *)

- ea: `0x1800aabcc`
- end: `0x1800ab008`
- name: `?IsAUMIDUninstallable@ShellBlockLists@@YAJPEBGPEA_N@Z`
- size: `1084`
- prototype: `__int64 __fastcall(LPCWCH lpString2, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800a7cd4`

## callees

- `0x180006e50`
- `0x18000c964`
- `0x180018244`
- `0x180019fa8`
- `0x180049edc`
- `0x1800a0248`
- `0x1800aabcc`
- `0x1800ab0b8`
- `0x1800afc70`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aac85`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aacc4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aad03`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aad39`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aae1c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aaf59`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aaf87`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aac85`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aacc4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aad03`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aad39`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aae1c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aaf59`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aaf87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aaf19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aaf9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aafc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aaf19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aaf9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aafc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800aaf3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800aaf3e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800aad91`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800aae5a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800aad91`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800aae5a`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x1800aac29`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x1800aac29`

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
        wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(&v26);
        if ( !v13 )
          goto LABEL_41;
      }
      if ( ++v12 == (LPCWCH *)&ShellBlockLists::PackagesThatHaveAlternativeReset )
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
              wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(&v26);
              return 0;
            }
            wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(&v26);
          }
          if ( ++v14 == (LPCWCH *)off_1800FED40 )
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
                  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v27);
                  return 0;
                }
              }
LABEL_37:
              WindowsDeleteString(string[0]);
            }
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v27);
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
0x1800aabcc  mov     [rsp-8+arg_10], rbx
0x1800aabd1  push    rbp
0x1800aabd2  push    rsi
0x1800aabd3  push    rdi
0x1800aabd4  push    r12
0x1800aabd6  push    r13
0x1800aabd8  push    r14
0x1800aabda  push    r15
0x1800aabdc  lea     rbp, [rsp-27h]
0x1800aabe1  sub     rsp, 90h
0x1800aabe8  mov     rax, cs:__security_cookie
0x1800aabef  xor     rax, rsp
0x1800aabf2  mov     [rbp+57h+var_40], rax
0x1800aabf6  mov     rsi, rdx
0x1800aabf9  mov     r15, rcx
0x1800aabfc  mov     r13d, 1
0x1800aac02  mov     [rdx], r13b
0x1800aac05  mov     eax, cs:?s_dwProductType@?1??IsCloudEdition@detail@ShellBlockLists@@YA?B_NXZ@4KA; ulong `ShellBlockLists::detail::IsCloudEdition(void)'::`2'::s_dwProductType
0x1800aac0b  xor     r12d, r12d
0x1800aac0e  test    eax, eax
0x1800aac10  jnz     short loc_1800AAC44
0x1800aac12  lea     rax, ?s_dwProductType@?1??IsCloudEdition@detail@ShellBlockLists@@YA?B_NXZ@4KA; ulong `ShellBlockLists::detail::IsCloudEdition(void)'::`2'::s_dwProductType
0x1800aac19  mov     [rsp+0C0h+pdwReturnedProductType], rax; pdwReturnedProductType
0x1800aac1e  xor     r9d, r9d; dwSpMinorVersion
0x1800aac21  xor     r8d, r8d; dwSpMajorVersion
0x1800aac24  xor     edx, edx; dwOSMinorVersion
0x1800aac26  lea     ecx, [rdx+0Ah]; dwOSMajorVersion
0x1800aac29  call    cs:__imp_GetProductInfo
0x1800aac2f  test    eax, eax
0x1800aac31  jnz     short loc_1800AAC3E
0x1800aac33  mov     eax, r12d
0x1800aac36  mov     cs:?s_dwProductType@?1??IsCloudEdition@detail@ShellBlockLists@@YA?B_NXZ@4KA, eax; ulong `ShellBlockLists::detail::IsCloudEdition(void)'::`2'::s_dwProductType
0x1800aac3c  jmp     short loc_1800AAC44
0x1800aac3e  mov     eax, cs:?s_dwProductType@?1??IsCloudEdition@detail@ShellBlockLists@@YA?B_NXZ@4KA; ulong `ShellBlockLists::detail::IsCloudEdition(void)'::`2'::s_dwProductType
0x1800aac44  add     eax, 0FFFFFF36h
0x1800aac49  cmp     eax, r13d
0x1800aac4c  setbe   cl
0x1800aac4f  mov     al, cl
0x1800aac51  lea     rdx, ?AppsThatCantBeUninstalledFromCloudEdition@ShellBlockLists@@3QBQEBGB; ushort const * const near * const ShellBlockLists::AppsThatCantBeUninstalledFromCloudEdition
0x1800aac58  neg     al
0x1800aac5a  sbb     r14, r14
0x1800aac5d  neg     cl
0x1800aac5f  sbb     edi, edi
0x1800aac61  and     edi, 19h
0x1800aac64  and     r14, rdx
0x1800aac67  jz      short loc_1800AAC9B
0x1800aac69  mov     ebx, r12d
0x1800aac6c  test    edi, edi
0x1800aac6e  jz      short loc_1800AAC9B
0x1800aac70  mov     ecx, ebx
0x1800aac72  mov     dword ptr [rsp+0C0h+pdwReturnedProductType], r13d; bIgnoreCase
0x1800aac77  or      r9d, 0FFFFFFFFh; cchCount2
0x1800aac7b  mov     r8, r15; lpString2
0x1800aac7e  or      edx, r9d; cchCount1
0x1800aac81  mov     rcx, [r14+rcx*8]; lpString1
0x1800aac85  call    cs:__imp_CompareStringOrdinal
0x1800aac8b  cmp     eax, 2
0x1800aac8e  jz      loc_1800AAFDC
0x1800aac94  add     ebx, r13d
0x1800aac97  cmp     ebx, edi
0x1800aac99  jb      short loc_1800AAC70
0x1800aac9b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableUninstallSystemComponentsForDMARegions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableUninstallSystemComponentsForDMARegions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableUninstallSystemComponentsForDMARegions> `wil::Feature<__WilFeatureTraits_Feature_EnableUninstallSystemComponentsForDMARegions>::GetImpl(void)'::`2'::impl
0x1800aaca2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableUninstallSystemComponentsForDMARegions@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableUninstallSystemComponentsForDMARegions>::__private_IsEnabled(void)
0x1800aaca7  or      r14d, 0FFFFFFFFh
0x1800aacab  test    al, al
0x1800aacad  jz      short loc_1800AACE0
0x1800aacaf  mov     dword ptr [rsp+0C0h+pdwReturnedProductType], r13d; bIgnoreCase
0x1800aacb4  mov     r9d, r14d; cchCount2
0x1800aacb7  mov     r8, r15; lpString2
0x1800aacba  mov     edx, r14d; cchCount1
0x1800aacbd  lea     rcx, String1; "Microsoft.WindowsStore_8wekyb3d8bbwe!Ap"...
0x1800aacc4  call    cs:__imp_CompareStringOrdinal
0x1800aacca  cmp     eax, 2
0x1800aaccd  jnz     short loc_1800AACE0
0x1800aaccf  call    ?IsMicrosoftStoreUninstallable@ShellBlockLists@@YA_NXZ; ShellBlockLists::IsMicrosoftStoreUninstallable(void)
0x1800aacd4  test    al, al
0x1800aacd6  jz      short loc_1800AACE0
0x1800aacd8  mov     [rsi], r13b
0x1800aacdb  jmp     loc_1800AAFDF
0x1800aace0  mov     ebx, r12d
0x1800aace3  lea     rax, __ImageBase
0x1800aacea  movsxd  rcx, ebx
0x1800aaced  mov     dword ptr [rsp+0C0h+pdwReturnedProductType], r13d; bIgnoreCase
0x1800aacf2  mov     r9d, r14d; cchCount2
0x1800aacf5  mov     r8, r15; lpString2
0x1800aacf8  mov     edx, r14d; cchCount1
0x1800aacfb  mov     rcx, ds:rva ?AppsThatCantBeUninstalledAnywhere@ShellBlockLists@@3QBQEBGB[rax+rcx*8]; lpString1
0x1800aad03  call    cs:__imp_CompareStringOrdinal
0x1800aad09  cmp     eax, 2
0x1800aad0c  jz      loc_1800AAFDC
0x1800aad12  add     ebx, r13d
0x1800aad15  cmp     ebx, 4Fh ; 'O'
0x1800aad18  lea     rax, __ImageBase
0x1800aad1f  jb      short loc_1800AACEA
0x1800aad21  lea     rdi, ?SearchAppsThatCantBeUninstalledOnNonDMARegion@ShellBlockLists@@3QBQEBGB; ushort const * const near * const ShellBlockLists::SearchAppsThatCantBeUninstalledOnNonDMARegion
0x1800aad28  mov     dword ptr [rsp+0C0h+pdwReturnedProductType], r13d; bIgnoreCase
0x1800aad2d  mov     r9d, r14d; cchCount2
0x1800aad30  mov     r8, r15; lpString2
0x1800aad33  mov     edx, r14d; cchCount1
0x1800aad36  mov     rcx, [rdi]; lpString1
0x1800aad39  call    cs:__imp_CompareStringOrdinal
0x1800aad3f  cmp     eax, 2
0x1800aad42  jnz     loc_1800AADF0
0x1800aad48  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_40979072@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_40979072@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40979072> `wil::Feature<__WilFeatureTraits_Feature_40979072>::GetImpl(void)'::`2'::impl
0x1800aad4f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_40979072@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40979072>::__private_IsEnabled(void)
0x1800aad54  test    al, al
0x1800aad56  jz      loc_1800AAFDC
0x1800aad5c  movzx   ebx, r12b
0x1800aad60  mov     [rbp+57h+var_70], r12
0x1800aad64  mov     [rbp+57h+var_48], r12
0x1800aad68  mov     r9d, 35h ; '5'; unsigned int
0x1800aad6e  lea     r8d, [r9+1]; unsigned int
0x1800aad72  lea     rdx, ?RuntimeClass_Windows_Internal_System_Profile_RegionPolicyEvaluator@@3QBGB; "Windows.Internal.System.Profile.RegionP"...
0x1800aad79  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800aad7d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800aad82  lea     r8, [rbp+57h+var_70]
0x1800aad86  lea     rdx, _GUID_1ca20398_c1d9_5f12_b40a_6528206e3b5e
0x1800aad8d  mov     rcx, [rbp+57h+var_48]
0x1800aad91  call    cs:__imp_RoGetActivationFactory
0x1800aad97  test    eax, eax
0x1800aad99  js      short loc_1800AADDF
0x1800aad9b  mov     dword ptr [rbp+57h+string], r12d
0x1800aad9f  mov     rcx, [rbp+57h+var_70]
0x1800aada3  mov     [rbp+57h+var_80], 0F2775604h
0x1800aadaa  mov     [rbp+57h+var_7C], 4CD2739Ch
0x1800aadb1  mov     [rbp+57h+var_78], 4EB6384h
0x1800aadb8  mov     [rbp+57h+var_74], 0F78B7E0Fh
0x1800aadbf  mov     rax, [rcx]
0x1800aadc2  lea     r8, [rbp+57h+string]
0x1800aadc6  lea     rdx, [rbp+57h+var_80]
0x1800aadca  mov     rax, [rax+30h]
0x1800aadce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aadd3  test    eax, eax
0x1800aadd5  js      short loc_1800AADDF
0x1800aadd7  cmp     dword ptr [rbp+57h+string], r13d
0x1800aaddb  cmovbe  ebx, r13d
0x1800aaddf  lea     rcx, [rbp+57h+var_70]
0x1800aade3  call    ??1?$com_ptr_t@UIApplicationStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(void)
0x1800aade8  test    bl, bl
0x1800aadea  jz      loc_1800AAFDC
0x1800aadf0  add     rdi, 8
0x1800aadf4  lea     rax, ?PackagesThatHaveAlternativeReset@ShellBlockLists@@3QBQEBGB; ushort const * const near * const ShellBlockLists::PackagesThatHaveAlternativeReset
0x1800aadfb  cmp     rdi, rax
0x1800aadfe  jnz     loc_1800AAD28
0x1800aae04  lea     rbx, ?StartExperiencesAppsThatCantBeUninstalledOnNonDMARegion@ShellBlockLists@@3QBQEBGB; ushort const * const near * const ShellBlockLists::StartExperiencesAppsThatCantBeUninstalledOnNonDMARegion
0x1800aae0b  mov     dword ptr [rsp+0C0h+pdwReturnedProductType], r13d; bIgnoreCase
0x1800aae10  mov     r9d, r14d; cchCount2
0x1800aae13  mov     r8, r15; lpString2
0x1800aae16  mov     edx, r14d; cchCount1
0x1800aae19  mov     rcx, [rbx]; lpString1
0x1800aae1c  call    cs:__imp_CompareStringOrdinal
0x1800aae22  cmp     eax, 2
0x1800aae25  jnz     loc_1800AAEBB
0x1800aae2b  mov     [rbp+57h+var_70], r12
0x1800aae2f  mov     [rbp+57h+var_48], r12
0x1800aae33  lea     r9d, [rax+33h]; unsigned int
0x1800aae37  lea     r8d, [rax+34h]; unsigned int
0x1800aae3b  lea     rdx, ?RuntimeClass_Windows_Internal_System_Profile_RegionPolicyEvaluator@@3QBGB; "Windows.Internal.System.Profile.RegionP"...
0x1800aae42  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800aae46  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800aae4b  lea     r8, [rbp+57h+var_70]
0x1800aae4f  lea     rdx, _GUID_1ca20398_c1d9_5f12_b40a_6528206e3b5e
0x1800aae56  mov     rcx, [rbp+57h+var_48]
0x1800aae5a  call    cs:__imp_RoGetActivationFactory
0x1800aae60  test    eax, eax
0x1800aae62  js      loc_1800AAFB2
0x1800aae68  mov     dword ptr [rbp+57h+string], r12d
0x1800aae6c  mov     rcx, [rbp+57h+var_70]
0x1800aae70  mov     [rbp+57h+var_80], 0C74BB959h
0x1800aae77  mov     [rbp+57h+var_7C], 4B9BF763h
0x1800aae7e  mov     [rbp+57h+var_78], 316B149Bh
0x1800aae85  mov     [rbp+57h+var_74], 37C9F22Dh
0x1800aae8c  mov     rax, [rcx]
0x1800aae8f  lea     r8, [rbp+57h+string]
0x1800aae93  lea     rdx, [rbp+57h+var_80]
0x1800aae97  mov     rax, [rax+30h]
0x1800aae9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aaea0  test    eax, eax
0x1800aaea2  js      loc_1800AAFB2
0x1800aaea8  cmp     dword ptr [rbp+57h+string], r13d
0x1800aaeac  ja      loc_1800AAFB2
0x1800aaeb2  lea     rcx, [rbp+57h+var_70]
0x1800aaeb6  call    ??1?$com_ptr_t@UIApplicationStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(void)
0x1800aaebb  add     rbx, 8
0x1800aaebf  lea     rax, off_1800FED40; "Volume"
0x1800aaec6  cmp     rbx, rax
0x1800aaec9  jnz     loc_1800AAE0B
0x1800aaecf  mov     [rbp+57h+var_68], r12
0x1800aaed3  mov     [rbp+57h+var_48], r12
0x1800aaed7  mov     r9d, 26h ; '&'; unsigned int
0x1800aaedd  lea     r8d, [r9+1]; unsigned int
0x1800aaee1  lea     rdx, ?RuntimeClass_Windows_Globalization_GeographicRegion@@3QBGB; "Windows.Globalization.GeographicRegion"
0x1800aaee8  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800aaeec  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800aaef1  lea     rdx, [rbp+57h+var_68]
0x1800aaef5  mov     rcx, [rbp+57h+var_48]
0x1800aaef9  call    ??$ActivateInstance@V?$ComPtr@UIGeographicRegion@Globalization@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIGeographicRegion@Globalization@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Globalization::IGeographicRegion>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Globalization::IGeographicRegion>>)
0x1800aaefe  mov     edi, eax
0x1800aaf00  test    eax, eax
0x1800aaf02  js      loc_1800AAFA5
0x1800aaf08  mov     [rbp+57h+string], r12
0x1800aaf0c  mov     rdi, [rbp+57h+var_68]
0x1800aaf10  mov     rax, [rdi]
0x1800aaf13  mov     rbx, [rax+38h]
0x1800aaf17  xor     ecx, ecx; string
0x1800aaf19  call    cs:__imp_WindowsDeleteString
0x1800aaf1f  mov     [rbp+57h+string], r12
0x1800aaf23  lea     rdx, [rbp+57h+string]
0x1800aaf27  mov     rcx, rdi
0x1800aaf2a  mov     rax, rbx
0x1800aaf2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aaf32  mov     edi, eax
0x1800aaf34  test    eax, eax
0x1800aaf36  js      short loc_1800AAF9A
0x1800aaf38  xor     edx, edx; length
0x1800aaf3a  mov     rcx, [rbp+57h+string]; string
0x1800aaf3e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800aaf44  mov     dword ptr [rsp+0C0h+pdwReturnedProductType], r13d; bIgnoreCase
0x1800aaf49  mov     r9d, r14d; cchCount2
0x1800aaf4c  lea     r8, String2; "CN"
0x1800aaf53  mov     edx, r14d; cchCount1
0x1800aaf56  mov     rcx, rax; lpString1
0x1800aaf59  call    cs:__imp_CompareStringOrdinal
0x1800aaf5f  cmp     eax, 2
0x1800aaf62  jz      short loc_1800AAF9A
0x1800aaf64  mov     ebx, r12d
0x1800aaf67  movsxd  rcx, ebx
0x1800aaf6a  mov     dword ptr [rsp+0C0h+pdwReturnedProductType], r13d; bIgnoreCase
0x1800aaf6f  mov     r9d, r14d; cchCount2
0x1800aaf72  mov     r8, r15; lpString2
0x1800aaf75  mov     edx, r14d; cchCount1
0x1800aaf78  lea     rax, __ImageBase
0x1800aaf7f  mov     rcx, ds:rva ?AppsThatCantBeUninstalledOutsideOfChina@ShellBlockLists@@3QBQEBGB[rax+rcx*8]; lpString1
0x1800aaf87  call    cs:__imp_CompareStringOrdinal
0x1800aaf8d  cmp     eax, 2
0x1800aaf90  jz      short loc_1800AAFC0
0x1800aaf92  add     ebx, r13d
0x1800aaf95  cmp     ebx, 2
0x1800aaf98  jb      short loc_1800AAF67
0x1800aaf9a  mov     rcx, [rbp+57h+string]; string
0x1800aaf9e  call    cs:__imp_WindowsDeleteString
0x1800aafa4  nop
0x1800aafa5  lea     rcx, [rbp+57h+var_68]
0x1800aafa9  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800aafae  mov     eax, edi
0x1800aafb0  jmp     short loc_1800AAFE1
0x1800aafb2  mov     [rsi], r12b
0x1800aafb5  lea     rcx, [rbp+57h+var_70]
0x1800aafb9  call    ??1?$com_ptr_t@UIApplicationStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(void)
0x1800aafbe  jmp     short loc_1800AAFDF
0x1800aafc0  mov     [rsi], r12b
0x1800aafc3  mov     rcx, [rbp+57h+string]; string
0x1800aafc7  call    cs:__imp_WindowsDeleteString
0x1800aafcd  mov     [rbp+57h+string], r12
0x1800aafd1  lea     rcx, [rbp+57h+var_68]
0x1800aafd5  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800aafda  jmp     short loc_1800AAFDF
0x1800aafdc  mov     [rsi], r12b
0x1800aafdf  xor     eax, eax
0x1800aafe1  mov     rcx, [rbp+57h+var_40]
0x1800aafe5  xor     rcx, rsp; StackCookie
0x1800aafe8  call    __security_check_cookie
0x1800aafed  mov     rbx, [rsp+0C0h+arg_10]
0x1800aaff5  add     rsp, 90h
0x1800aaffc  pop     r15
0x1800aaffe  pop     r14
0x1800ab000  pop     r13
0x1800ab002  pop     r12
0x1800ab004  pop     rdi
0x1800ab005  pop     rsi
0x1800ab006  pop     rbp
0x1800ab007  retn
```
