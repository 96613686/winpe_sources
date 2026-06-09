# LogStoreUpdateEvent(void)

- ea: `0x180044fd8`
- end: `0x180045ece`
- name: `?LogStoreUpdateEvent@@YAXXZ`
- size: `3830`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180030f28`

## callees

- `0x1800013a0`
- `0x1800026b0`
- `0x1800033c7`
- `0x1800033f7`
- `0x180021cdc`
- `0x180022408`
- `0x180022888`
- `0x180022ab4`
- `0x18002c378`
- `0x18002d5f8`
- `0x18002da38`
- `0x18002e398`
- `0x18002e550`
- `0x18002e5e4`
- `0x18002e64c`
- `0x180030aac`
- `0x180044974`
- `0x180044b44`
- `0x180044d24`
- `0x180044e68`
- `0x180044f30`
- `0x180044fd8`
- `0x180045ed4`
- `0x180045f2c`
- `0x18004f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800452c8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180045e5c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180045e67`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180045e73`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800452c8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180045e5c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180045e67`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180045e73`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180045248`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180045248`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045e2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045e2a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180045255`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180045255`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180045b3d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180045b3d`

## string_xrefs

- `0x180045048`: `SOFTWARE\Microsoft\Windows\CurrentVersion\InstallService\State`
- `0x180045034`: `AutoUpdatePauseEndTime`
- `0x180045073`: `AutoUpdateLastSuccessTime`
- `0x1800450ba`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsStore\WindowsUpdate`
- `0x18004513d`: `SYSTEM\CurrentControlSet\Services\DoSvc`
- `0x180045101`: `SYSTEM\CurrentControlSet\Services\wuauserv`
- `0x180045180`: `SOFTWARE\Microsoft\WindowsUpdate\UX\Settings`
- `0x1800451ad`: `NumUpdatesLastScan`
- `0x1800451f4`: `SOFTWARE\Microsoft\Windows\CurrentVersion\DeviceAccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=47
void LogStoreUpdateEvent(void)
{
  char v0; // r12
  volatile signed __int32 *v1; // r14
  const WCHAR *v2; // rcx
  void (__fastcall ***v3)(_QWORD, __int64 *, __int64 **); // rcx
  int v4; // r15d
  __int64 v5; // rax
  char v6; // bl
  __int64 v7; // rax
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rsi
  __int64 v11; // rdi
  __int64 v12; // rbx
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  __m256i *v16; // rax
  _QWORD *v17; // rax
  __m256i *v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rax
  void (__fastcall ***v21)(_QWORD, __int64 *, __int64 **); // rcx
  char v22; // bl
  __int64 v23; // rax
  int v24; // r15d
  __int64 *v25; // rax
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rsi
  __int64 v29; // rdi
  __int64 v30; // rbx
  _QWORD *v31; // rax
  __m256i *v32; // rax
  _QWORD *v33; // rax
  __m256i *v34; // rax
  int v35; // r15d
  _QWORD *v36; // rax
  _QWORD *v37; // rax
  __int64 v38; // rbx
  int v39; // r15d
  int v40; // eax
  LPVOID v41; // rsi
  int v42; // r15d
  int v43; // eax
  unsigned int v44; // ecx
  int v45; // r15d
  int v46; // eax
  unsigned int v47; // r15d
  int v48; // eax
  LPVOID v49; // rdi
  int v50; // eax
  unsigned int v51; // ebx
  unsigned int v52; // ebx
  unsigned int v53; // ebx
  unsigned int v54; // ebx
  bool v55; // r8
  LPVOID v56; // rbx
  LPVOID v57; // rdi
  __int64 v58; // r8
  __int64 v59; // r9
  __int128 *v60; // rax
  __int128 *v61; // rax
  WCHAR *v62; // rcx
  const WCHAR *v63; // rax
  int v64; // eax
  HANDLE ProcessHeap; // rax
  int v66; // eax
  HANDLE v67; // rax
  int v68; // r13d
  HANDLE v69; // rax
  __int64 v70; // [rsp+C0h] [rbp-80h] BYREF
  LPVOID ppv; // [rsp+C8h] [rbp-78h] BYREF
  int v72; // [rsp+D0h] [rbp-70h] BYREF
  unsigned int v73; // [rsp+D4h] [rbp-6Ch] BYREF
  bool v74; // [rsp+D8h] [rbp-68h]
  bool v75; // [rsp+D9h] [rbp-67h]
  bool v76; // [rsp+DAh] [rbp-66h]
  bool v77; // [rsp+DBh] [rbp-65h]
  bool v78; // [rsp+DCh] [rbp-64h]
  char v79; // [rsp+DDh] [rbp-63h]
  bool v80; // [rsp+DEh] [rbp-62h]
  bool v81; // [rsp+DFh] [rbp-61h]
  bool v82; // [rsp+E0h] [rbp-60h]
  bool v83[3]; // [rsp+E1h] [rbp-5Fh] BYREF
  unsigned int v84; // [rsp+E4h] [rbp-5Ch] BYREF
  __int64 v85; // [rsp+E8h] [rbp-58h] BYREF
  int v86; // [rsp+F0h] [rbp-50h] BYREF
  unsigned int v87; // [rsp+F4h] [rbp-4Ch]
  int v88; // [rsp+F8h] [rbp-48h]
  int v89; // [rsp+FCh] [rbp-44h]
  int v90; // [rsp+100h] [rbp-40h]
  __int64 v91; // [rsp+108h] [rbp-38h] BYREF
  __int64 (__fastcall *v92)(const struct winrt::Windows::Foundation::IActivationFactory *); // [rsp+110h] [rbp-30h] BYREF
  bool v93[8]; // [rsp+118h] [rbp-28h] BYREF
  __int64 v94; // [rsp+120h] [rbp-20h]
  int v95; // [rsp+128h] [rbp-18h] BYREF
  __int64 v96; // [rsp+130h] [rbp-10h] BYREF
  int v97; // [rsp+138h] [rbp-8h] BYREF
  __int64 v98; // [rsp+140h] [rbp+0h] BYREF
  LPVOID lpMem; // [rsp+148h] [rbp+8h] BYREF
  LPVOID v100; // [rsp+150h] [rbp+10h] BYREF
  LPVOID v101; // [rsp+158h] [rbp+18h] BYREF
  __int64 v102; // [rsp+160h] [rbp+20h] BYREF
  int v103; // [rsp+168h] [rbp+28h]
  int v104; // [rsp+16Ch] [rbp+2Ch]
  _QWORD v105[2]; // [rsp+170h] [rbp+30h] BYREF
  __int64 v106; // [rsp+180h] [rbp+40h] BYREF
  __m256i v107; // [rsp+188h] [rbp+48h] BYREF
  __m256i v108; // [rsp+1A8h] [rbp+68h] BYREF
  __int128 v109; // [rsp+1C8h] [rbp+88h] BYREF
  __m128i v110; // [rsp+1D8h] [rbp+98h]
  __int128 v111; // [rsp+1E8h] [rbp+A8h] BYREF
  __m128i si128; // [rsp+1F8h] [rbp+B8h]
  __int128 v113; // [rsp+208h] [rbp+C8h] BYREF
  __int128 v114; // [rsp+218h] [rbp+D8h]
  struct _SYSTEMTIME SystemTime; // [rsp+228h] [rbp+E8h] BYREF
  char *v116[4]; // [rsp+238h] [rbp+F8h] BYREF
  char *v117[4]; // [rsp+258h] [rbp+118h] BYREF
  char *v118[4]; // [rsp+278h] [rbp+138h] BYREF
  char *v119[4]; // [rsp+298h] [rbp+158h] BYREF
  char *v120[4]; // [rsp+2B8h] [rbp+178h] BYREF
  char *v121[4]; // [rsp+2D8h] [rbp+198h] BYREF
  char *v122[4]; // [rsp+2F8h] [rbp+1B8h] BYREF

  v73 = 0;
  v0 = 1;
  v94 = -2147483646;
  v93[0] = wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_InstallServiceShutdown>::GetImpl'::`2'::impl) == 0;
  v100 = 0;
  v107.m256i_i64[0] = (__int64)L"AutoUpdatePauseEndTime";
  v107.m256i_i64[1] = 22;
  v108.m256i_i64[0] = (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\InstallService\\State";
  v108.m256i_i64[1] = 62;
  Registry::TryGetValue<winrt::hstring>((__int64)v93, (LPCWSTR *)&v108, (LPCWSTR *)&v107, (char *)&v100);
  v101 = 0;
  v107.m256i_i64[0] = (__int64)L"AutoUpdateLastSuccessTime";
  v107.m256i_i64[1] = 25;
  v108.m256i_i64[0] = (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\InstallService\\State";
  v108.m256i_i64[1] = 62;
  Registry::TryGetValue<winrt::hstring>((__int64)v93, (LPCWSTR *)&v108, (LPCWSTR *)&v107, (char *)&v101);
  v72 = 0;
  v107.m256i_i64[0] = (__int64)L"AutoDownload";
  v107.m256i_i64[1] = 12;
  v108.m256i_i64[0] = (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsStore\\WindowsUpdate";
  v108.m256i_i64[1] = 68;
  Registry::TryGetValue<unsigned int>((__int64)v93, (LPCWSTR *)&v108, (LPCWSTR *)&v107, &v72);
  v77 = v72 == 2;
  v72 = 0;
  v107.m256i_i64[0] = (__int64)L"START";
  v107.m256i_i64[1] = 5;
  v108.m256i_i64[0] = (__int64)L"SYSTEM\\CurrentControlSet\\Services\\wuauserv";
  v108.m256i_i64[1] = 42;
  Registry::TryGetValue<unsigned int>((__int64)v93, (LPCWSTR *)&v108, (LPCWSTR *)&v107, &v72);
  v76 = v72 == 2;
  v72 = 0;
  v107.m256i_i64[0] = (__int64)L"START";
  v107.m256i_i64[1] = 5;
  v108.m256i_i64[0] = (__int64)L"SYSTEM\\CurrentControlSet\\Services\\DoSvc";
  v108.m256i_i64[1] = 39;
  Registry::TryGetValue<unsigned int>((__int64)v93, (LPCWSTR *)&v108, (LPCWSTR *)&v107, &v72);
  v75 = v72 == 2;
  v97 = 0;
  v107.m256i_i64[0] = (__int64)L"AlwaysAllowCTADownload";
  v107.m256i_i64[1] = 22;
  v108.m256i_i64[0] = (__int64)L"SOFTWARE\\Microsoft\\WindowsUpdate\\UX\\Settings";
  v108.m256i_i64[1] = 44;
  Registry::TryGetValue<unsigned int>((__int64)v93, (LPCWSTR *)&v108, (LPCWSTR *)&v107, &v97);
  v95 = 0;
  v107.m256i_i64[0] = (__int64)L"NumUpdatesLastScan";
  v107.m256i_i64[1] = 18;
  v108.m256i_i64[0] = (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\InstallService\\State";
  v108.m256i_i64[1] = 62;
  Registry::TryGetValue<unsigned int>((__int64)v93, (LPCWSTR *)&v108, (LPCWSTR *)&v107, &v95);
  lpMem = 0;
  v107.m256i_i64[0] = (__int64)L"ActivePolicyCode";
  v107.m256i_i64[1] = 16;
  v108.m256i_i64[0] = (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DeviceAccess";
  v108.m256i_i64[1] = 54;
  Registry::TryGetValue<winrt::hstring>((__int64)v93, (LPCWSTR *)&v108, (LPCWSTR *)&v107, (char *)&lpMem);
  v1 = (volatile signed __int32 *)lpMem;
  if ( lpMem )
    v2 = (const WCHAR *)*((_QWORD *)lpMem + 2);
  else
    v2 = &ApplicationName;
  v74 = CompareStringOrdinal(v2, -1, L"zh", -1, 1) == 2;
  v105[0] = GetTickCount64();
  v107.m256i_i64[0] = (__int64)&qword_18007F958;
  _InterlockedAdd64(&qword_18007F958, 1u);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory> )
  {
    _lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_::operator()(
      v3,
      &v96,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>);
    v4 = 3;
    _InterlockedAdd64(&qword_18007F958, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_18007F958, 0xFFFFFFFFFFFFFFFFuLL);
    v92 = _lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Management::Deployment::PackageManager (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      v3,
      (__int64)&v96,
      (void (__fastcall **)(__int64, __int64 *))&v92);
    v4 = 3;
  }
  if ( aMicrosoftWindo_3[36] )
    abort();
  v107.m256i_i64[1] = 0x2400000001LL;
  v107.m256i_i64[3] = (__int64)L"Microsoft.WindowsStore_8wekyb3d8bbwe";
  v107.m256i_i64[0] = (__int64)&v107.m256i_i64[1];
  winrt::impl::consume_Windows_Management_Deployment_IPackageManager<winrt::Windows::Management::Deployment::IPackageManager>::FindPackages(
    &v96,
    &v92,
    &v107);
  v111 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v111) = 0;
  ppv = 0;
  v5 = winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::begin(
         &v92,
         &v85);
  v6 = winrt::Windows::Foundation::operator!=(v5, &ppv);
  if ( v85 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v85);
  if ( v6 )
  {
    v7 = winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::begin(
           &v92,
           &ppv);
    winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::Current(
      v7,
      &v85);
    if ( ppv )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&ppv);
    v70 = 0;
    v8 = *(_QWORD *)winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::First(
                      &v85,
                      &v91);
    v107.m256i_i32[0] = 0;
    *(_OWORD *)&v107.m256i_u64[1] = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 56LL))(v8, &v70);
    if ( v9 < 0 )
      winrt::throw_hresult((unsigned int)v9, &v107);
    if ( v91 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v91);
    v10 = std::to_wstring(v122, HIWORD(v70));
    v11 = std::to_wstring(v121, WORD2(v70));
    v12 = std::to_wstring(v120, WORD1(v70));
    v13 = (_QWORD *)std::to_wstring(v119, (unsigned __int16)v70);
    v14 = std::wstring::_Append<unsigned short>(v13, L".", 1u);
    v113 = *(_OWORD *)v14;
    v114 = *((_OWORD *)v14 + 1);
    v14[2] = 0;
    v14[3] = 7;
    *(_WORD *)v14 = 0;
    v15 = (_QWORD *)std::operator+<unsigned short>(v118, &v113, v12);
    v16 = (__m256i *)std::wstring::_Append<unsigned short>(v15, L".", 1u);
    v108 = *v16;
    v16->m256i_i64[2] = 0;
    v16->m256i_i64[3] = 7;
    v16->m256i_i16[0] = 0;
    v17 = (_QWORD *)std::operator+<unsigned short>(v117, &v108, v11);
    v18 = (__m256i *)std::wstring::_Append<unsigned short>(v17, L".", 1u);
    v107 = *v18;
    v18->m256i_i64[2] = 0;
    v18->m256i_i64[3] = 7;
    v18->m256i_i16[0] = 0;
    v4 = 63;
    v19 = std::operator+<unsigned short>(v116, &v107, v10);
    if ( &v111 != (__int128 *)v19 )
    {
      std::wstring::_Tidy_deallocate((char **)&v111);
      v111 = *(_OWORD *)v19;
      si128 = *(__m128i *)(v19 + 16);
      *(_QWORD *)(v19 + 16) = 0;
      *(_QWORD *)(v19 + 24) = 7;
      *(_WORD *)v19 = 0;
    }
    std::wstring::_Tidy_deallocate(v116);
    std::wstring::_Tidy_deallocate((char **)&v107);
    std::wstring::_Tidy_deallocate(v117);
    std::wstring::_Tidy_deallocate((char **)&v108);
    std::wstring::_Tidy_deallocate(v118);
    std::wstring::_Tidy_deallocate((char **)&v113);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::_Tidy_deallocate(v120);
    std::wstring::_Tidy_deallocate(v121);
    std::wstring::_Tidy_deallocate(v122);
    if ( v85 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v85);
  }
  v107.m256i_i64[1] = 0x2800000001LL;
  v107.m256i_i64[3] = (__int64)L"Microsoft.StorePurchaseApp_8wekyb3d8bbwe";
  v107.m256i_i64[0] = (__int64)&v107.m256i_i64[1];
  winrt::impl::consume_Windows_Management_Deployment_IPackageManager<winrt::Windows::Management::Deployment::IPackageManager>::FindPackages(
    &v96,
    &v85,
    &v107);
  v109 = 0;
  v110 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v109) = 0;
  v70 = 0;
  v20 = winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::begin(
          &v85,
          &ppv);
  v22 = winrt::Windows::Foundation::operator!=(v20, &v70);
  if ( ppv )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&ppv);
  if ( v22 )
  {
    v23 = winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::begin(
            &v85,
            &v91);
    winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::Current(
      v23,
      &ppv);
    v24 = v4 | 0x40;
    if ( v91 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v91);
    v25 = (__int64 *)winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::First(
                       &ppv,
                       &v102);
    v70 = 0;
    v26 = *v25;
    v107.m256i_i32[0] = 0;
    *(_OWORD *)&v107.m256i_u64[1] = 0;
    v27 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 56LL))(v26, &v70);
    if ( v27 < 0 )
      winrt::throw_hresult((unsigned int)v27, &v107);
    if ( v102 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v102);
    v28 = std::to_wstring(v116, HIWORD(v70));
    v29 = std::to_wstring(v117, WORD2(v70));
    v30 = std::to_wstring(v118, WORD1(v70));
    v31 = (_QWORD *)std::to_wstring(v119, (unsigned __int16)v70);
    v32 = (__m256i *)std::wstring::_Append<unsigned short>(v31, L".", 1u);
    v108 = *v32;
    v32->m256i_i64[2] = 0;
    v32->m256i_i64[3] = 7;
    v32->m256i_i16[0] = 0;
    v33 = (_QWORD *)std::operator+<unsigned short>(v120, &v108, v30);
    v34 = (__m256i *)std::wstring::_Append<unsigned short>(v33, L".", 1u);
    v107 = *v34;
    v34->m256i_i64[2] = 0;
    v34->m256i_i64[3] = 7;
    v34->m256i_i16[0] = 0;
    v35 = v24 | 0x180;
    v73 = v35;
    v36 = (_QWORD *)std::operator+<unsigned short>(v121, &v107, v29);
    v37 = std::wstring::_Append<unsigned short>(v36, L".", 1u);
    v113 = *(_OWORD *)v37;
    v114 = *((_OWORD *)v37 + 1);
    v37[2] = 0;
    v37[3] = 7;
    *(_WORD *)v37 = 0;
    v4 = v35 | 0x200;
    v38 = std::operator+<unsigned short>(v122, &v113, v28);
    if ( &v109 != (__int128 *)v38 )
    {
      std::wstring::_Tidy_deallocate((char **)&v109);
      v109 = *(_OWORD *)v38;
      v110 = *(__m128i *)(v38 + 16);
      *(_QWORD *)(v38 + 16) = 0;
      *(_QWORD *)(v38 + 24) = 7;
      *(_WORD *)v38 = 0;
    }
    std::wstring::_Tidy_deallocate(v122);
    std::wstring::_Tidy_deallocate((char **)&v113);
    std::wstring::_Tidy_deallocate(v121);
    std::wstring::_Tidy_deallocate((char **)&v107);
    std::wstring::_Tidy_deallocate(v120);
    std::wstring::_Tidy_deallocate((char **)&v108);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::_Tidy_deallocate(v118);
    std::wstring::_Tidy_deallocate(v117);
    std::wstring::_Tidy_deallocate(v116);
    if ( ppv )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&ppv);
  }
  v107.m256i_i64[0] = (__int64)&qword_18007F9C8;
  _InterlockedAdd64(&qword_18007F9C8, 1u);
  v39 = v4 | 0x400;
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory> )
  {
    _lambda_145d7b08a85782a985a0b0a38cc4c355_::operator()(
      v21,
      &v98,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedAdd64(&qword_18007F9C8, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_18007F9C8, 0xFFFFFFFFFFFFFFFFuLL);
    ppv = _lambda_145d7b08a85782a985a0b0a38cc4c355_::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      v21,
      (__int64)&v98,
      (void (__fastcall **)(__int64, __int64 *))&ppv);
  }
  ppv = 0;
  v107.m256i_i32[0] = 0;
  *(_OWORD *)&v107.m256i_u64[1] = 0;
  v40 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v98 + 48LL))(v98, &ppv);
  if ( v40 < 0 )
    winrt::throw_hresult((unsigned int)v40, &v107);
  v41 = ppv;
  v107.m256i_i64[0] = (__int64)ppv;
  v42 = v39 | 0x800;
  v86 = 0;
  v108.m256i_i32[0] = 0;
  *(_OWORD *)&v108.m256i_u64[1] = 0;
  v43 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 56LL))(ppv, &v86);
  if ( v43 < 0 )
    winrt::throw_hresult((unsigned int)v43, &v108);
  v44 = 0;
  v72 = 0;
  v90 = 0;
  v89 = 0;
  v88 = 0;
  v87 = 0;
  while ( 1 )
  {
    v84 = v44;
    if ( v44 == v86 )
      break;
    v70 = 0;
    v45 = v42 | 0x2000;
    v73 = v45;
    v108.m256i_i32[0] = 0;
    *(_OWORD *)&v108.m256i_u64[1] = 0;
    v46 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v41 + 48LL))(v41, v44, &v70);
    if ( v46 < 0 )
      winrt::throw_hresult((unsigned int)v46, &v108);
    v47 = v45 & 0xFFFFCFFF | 0x1000;
    v73 = v47;
    ppv = 0;
    v108.m256i_i32[0] = 0;
    *(_OWORD *)&v108.m256i_u64[1] = 0;
    v48 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v70 + 80LL))(v70, &ppv);
    if ( v48 < 0 )
      winrt::throw_hresult((unsigned int)v48, &v108);
    v49 = ppv;
    v42 = v47 | 0x4000;
    v73 = 0;
    v108.m256i_i32[0] = 0;
    *(_OWORD *)&v108.m256i_u64[1] = 0;
    v50 = (*(__int64 (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)ppv + 48LL))(ppv, &v73);
    if ( v50 < 0 )
      winrt::throw_hresult((unsigned int)v50, &v108);
    v51 = v73;
    if ( v49 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&ppv);
    if ( v51 )
    {
      v52 = v51 - 5;
      if ( v52 )
      {
        v53 = v52 - 3;
        if ( v53 )
        {
          v54 = v53 - 1;
          if ( v54 )
          {
            if ( v54 == 4 )
              ++v88;
          }
          else
          {
            ++v87;
          }
        }
        else
        {
          ++v89;
        }
      }
      else
      {
        ++v72;
      }
    }
    else
    {
      ++v90;
    }
    if ( v70 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v70);
    v44 = v84 + 1;
  }
  SystemTime = 0;
  v55 = IsScanForUpdatesEnabled(&SystemTime);
  v56 = v100;
  v57 = v101;
  if ( (unsigned int)dword_1800651B0 > 5
    && (qword_1800651C0 & 0x800000000000LL) != 0
    && (qword_1800651C8 & 0x800000000000LL) == qword_1800651C8 )
  {
    v105[1] = &SystemTime;
    v78 = v55;
    ppv = 0;
    if ( CoCreateInstance(
           &GUID_46687f54_2097_4fc1_9173_3863021dc370,
           0,
           4u,
           &GUID_39cdd716_77a8_4031_93bb_bd7492d52b4d,
           &ppv) >= 0
      && (v84 = 0, (*(int (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)ppv + 24LL))(ppv, &v84) >= 0)
      && v84 )
    {
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    else
    {
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      v0 = 0;
    }
    v79 = v0;
    v86 = v97;
    v80 = v74;
    v81 = v75;
    v82 = v76;
    v73 = v87;
    v104 = v88;
    v103 = v89;
    LODWORD(v102) = v90;
    LODWORD(v91) = v72;
    v60 = &v109;
    if ( v110.m128i_i64[1] > 7uLL )
      v60 = (__int128 *)v109;
    v101 = v60;
    v61 = &v111;
    if ( si128.m128i_i64[1] > 7uLL )
      v61 = (__int128 *)v111;
    v100 = v61;
    v106 = v105[0];
    LODWORD(v70) = v95;
    v62 = (WCHAR *)&ApplicationName;
    if ( v57 )
      v63 = (const WCHAR *)*((_QWORD *)v57 + 2);
    else
      v63 = &ApplicationName;
    v105[0] = v63;
    if ( v56 )
      v62 = (WCHAR *)*((_QWORD *)v56 + 2);
    lpMem = v62;
    v83[0] = v77;
    v108.m256i_i64[0] = 0x80000000LL;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>>(
      (__int64)v62,
      (__int64)byte_18005B3FD,
      v58,
      v59,
      (__int64)&v108,
      (__int64)v83,
      &lpMem,
      v105,
      (__int64)&v70,
      (__int64)&v106,
      &v100,
      &v101);
  }
  if ( v41 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v107);
  if ( v98 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v98);
  std::wstring::_Tidy_deallocate((char **)&v109);
  if ( v85 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v85);
  std::wstring::_Tidy_deallocate((char **)&v111);
  if ( v92 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v92);
  if ( v96 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v96);
  if ( v1 )
  {
    v64 = _InterlockedDecrement(v1 + 6);
    if ( v64 )
    {
      if ( v64 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v1);
    }
  }
  if ( v57 )
  {
    v66 = _InterlockedDecrement((volatile signed __int32 *)v57 + 6);
    if ( v66 )
    {
      if ( v66 < 0 )
        abort();
    }
    else
    {
      v67 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v67, 0, v57);
    }
  }
  if ( v56 )
  {
    v68 = _InterlockedDecrement((volatile signed __int32 *)v56 + 6);
    if ( v68 )
    {
      if ( v68 < 0 )
        abort();
    }
    else
    {
      v69 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v69, 0, v56);
    }
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_InstallServiceShutdown>::GetImpl'::`2'::impl)
    && v93[0] )
  {
    RegCloseKey(HKEY_LOCAL_MACHINE);
  }
}

```

## disassembly

```asm
0x180044fd8  push    rbp
0x180044fda  push    rbx
0x180044fdb  push    rsi
0x180044fdc  push    rdi
0x180044fdd  push    r12
0x180044fdf  push    r13
0x180044fe1  push    r14
0x180044fe3  push    r15
0x180044fe5  lea     rbp, [rsp-1E8h]
0x180044fed  sub     rsp, 328h
0x180044ff4  mov     rax, cs:__security_cookie
0x180044ffb  xor     rax, rsp
0x180044ffe  mov     [rbp+220h+var_48], rax
0x180045005  xor     r15d, r15d
0x180045008  mov     [rbp+220h+var_28C], r15d
0x18004500c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InstallServiceShutdown@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InstallServiceShutdown@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown> `wil::Feature<__WilFeatureTraits_Feature_InstallServiceShutdown>::GetImpl(void)'::`2'::impl
0x180045013  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InstallServiceShutdown@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::__private_IsEnabled(void)
0x180045018  lea     r12d, [r15+1]
0x18004501c  mov     [rbp+220h+var_240], 0FFFFFFFF80000002h
0x180045024  test    al, al
0x180045026  mov     [rbp+220h+var_248], r15b
0x18004502a  jnz     short loc_180045030
0x18004502c  mov     [rbp+220h+var_248], r12b
0x180045030  mov     [rbp+220h+var_210], r15
0x180045034  lea     rax, aAutoupdatepaus; "AutoUpdatePauseEndTime"
0x18004503b  mov     qword ptr [rbp+220h+var_1D8], rax
0x18004503f  mov     edi, 16h
0x180045044  mov     qword ptr [rbp+220h+var_1D8+8], rdi
0x180045048  lea     r14, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18004504f  mov     qword ptr [rbp+220h+var_1B8], r14
0x180045053  lea     esi, [rdi+28h]
0x180045056  mov     qword ptr [rbp+220h+var_1B8+8], rsi
0x18004505a  lea     r9, [rbp+220h+var_210]
0x18004505e  lea     r8, [rbp+220h+var_1D8]
0x180045062  lea     rdx, [rbp+220h+var_1B8]
0x180045066  lea     rcx, [rbp+220h+var_248]
0x18004506a  call    ??$TryGetValue@Uhstring@winrt@@@Registry@@YA_NAEBUKey@0@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@1AEAUhstring@winrt@@@Z; Registry::TryGetValue<winrt::hstring>(Registry::Key const &,std::basic_string_view<ushort> const &,std::basic_string_view<ushort> const &,winrt::hstring &)
0x18004506f  mov     [rbp+220h+var_208], r15
0x180045073  lea     rax, aAutoupdatelast; "AutoUpdateLastSuccessTime"
0x18004507a  mov     qword ptr [rbp+220h+var_1D8], rax
0x18004507e  mov     qword ptr [rbp+220h+var_1D8+8], 19h
0x180045086  mov     qword ptr [rbp+220h+var_1B8], r14
0x18004508a  mov     qword ptr [rbp+220h+var_1B8+8], rsi
0x18004508e  lea     r9, [rbp+220h+var_208]
0x180045092  lea     r8, [rbp+220h+var_1D8]
0x180045096  lea     rdx, [rbp+220h+var_1B8]
0x18004509a  lea     rcx, [rbp+220h+var_248]
0x18004509e  call    ??$TryGetValue@Uhstring@winrt@@@Registry@@YA_NAEBUKey@0@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@1AEAUhstring@winrt@@@Z; Registry::TryGetValue<winrt::hstring>(Registry::Key const &,std::basic_string_view<ushort> const &,std::basic_string_view<ushort> const &,winrt::hstring &)
0x1800450a3  mov     [rbp+220h+var_290], r15d
0x1800450a7  lea     rax, aAutodownload; "AutoDownload"
0x1800450ae  mov     qword ptr [rbp+220h+var_1D8], rax
0x1800450b2  mov     qword ptr [rbp+220h+var_1D8+8], 0Ch
0x1800450ba  lea     rax, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800450c1  mov     qword ptr [rbp+220h+var_1B8], rax
0x1800450c5  mov     qword ptr [rbp+220h+var_1B8+8], 44h ; 'D'
0x1800450cd  lea     r9, [rbp+220h+var_290]
0x1800450d1  lea     r8, [rbp+220h+var_1D8]
0x1800450d5  lea     rdx, [rbp+220h+var_1B8]
0x1800450d9  lea     rcx, [rbp+220h+var_248]
0x1800450dd  call    ??$TryGetValue@I@Registry@@YA_NAEBUKey@0@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@1AEAI@Z; Registry::TryGetValue<uint>(Registry::Key const &,std::basic_string_view<ushort> const &,std::basic_string_view<ushort> const &,uint &)
0x1800450e2  cmp     [rbp+220h+var_290], 2
0x1800450e6  setz    [rbp+220h+var_285]
0x1800450ea  mov     [rbp+220h+var_290], r15d
0x1800450ee  lea     rbx, aStart; "START"
0x1800450f5  mov     qword ptr [rbp+220h+var_1D8], rbx
0x1800450f9  lea     r13d, [rdi-11h]
0x1800450fd  mov     qword ptr [rbp+220h+var_1D8+8], r13
0x180045101  lea     rax, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\wu"...
0x180045108  mov     qword ptr [rbp+220h+var_1B8], rax
0x18004510c  mov     qword ptr [rbp+220h+var_1B8+8], 2Ah ; '*'
0x180045114  lea     r9, [rbp+220h+var_290]
0x180045118  lea     r8, [rbp+220h+var_1D8]
0x18004511c  lea     rdx, [rbp+220h+var_1B8]
0x180045120  lea     rcx, [rbp+220h+var_248]
0x180045124  call    ??$TryGetValue@I@Registry@@YA_NAEBUKey@0@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@1AEAI@Z; Registry::TryGetValue<uint>(Registry::Key const &,std::basic_string_view<ushort> const &,std::basic_string_view<ushort> const &,uint &)
0x180045129  cmp     [rbp+220h+var_290], 2
0x18004512d  setz    [rbp+220h+var_286]
0x180045131  mov     [rbp+220h+var_290], r15d
0x180045135  mov     qword ptr [rbp+220h+var_1D8], rbx
0x180045139  mov     qword ptr [rbp+220h+var_1D8+8], r13
0x18004513d  lea     rax, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Do"...
0x180045144  mov     qword ptr [rbp+220h+var_1B8], rax
0x180045148  mov     qword ptr [rbp+220h+var_1B8+8], 27h ; '''
0x180045150  lea     r9, [rbp+220h+var_290]
0x180045154  lea     r8, [rbp+220h+var_1D8]
0x180045158  lea     rdx, [rbp+220h+var_1B8]
0x18004515c  lea     rcx, [rbp+220h+var_248]
0x180045160  call    ??$TryGetValue@I@Registry@@YA_NAEBUKey@0@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@1AEAI@Z; Registry::TryGetValue<uint>(Registry::Key const &,std::basic_string_view<ushort> const &,std::basic_string_view<ushort> const &,uint &)
0x180045165  cmp     [rbp+220h+var_290], 2
0x180045169  setz    [rbp+220h+var_287]
0x18004516d  mov     [rbp+220h+var_228], r15d
0x180045171  lea     rax, aAlwaysallowcta; "AlwaysAllowCTADownload"
0x180045178  mov     qword ptr [rbp+220h+var_1D8], rax
0x18004517c  mov     qword ptr [rbp+220h+var_1D8+8], rdi
0x180045180  lea     rax, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\WindowsUpdate\\UX"...
0x180045187  mov     qword ptr [rbp+220h+var_1B8], rax
0x18004518b  mov     qword ptr [rbp+220h+var_1B8+8], 2Ch ; ','
0x180045193  lea     r9, [rbp+220h+var_228]
0x180045197  lea     r8, [rbp+220h+var_1D8]
0x18004519b  lea     rdx, [rbp+220h+var_1B8]
0x18004519f  lea     rcx, [rbp+220h+var_248]
0x1800451a3  call    ??$TryGetValue@I@Registry@@YA_NAEBUKey@0@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@1AEAI@Z; Registry::TryGetValue<uint>(Registry::Key const &,std::basic_string_view<ushort> const &,std::basic_string_view<ushort> const &,uint &)
0x1800451a8  xor     edi, edi
0x1800451aa  mov     [rbp+220h+var_238], edi
0x1800451ad  lea     rax, aNumupdateslast; "NumUpdatesLastScan"
0x1800451b4  mov     qword ptr [rbp+220h+var_1D8], rax
0x1800451b8  mov     qword ptr [rbp+220h+var_1D8+8], 12h
0x1800451c0  mov     qword ptr [rbp+220h+var_1B8], r14
0x1800451c4  mov     qword ptr [rbp+220h+var_1B8+8], rsi
0x1800451c8  lea     r9, [rbp+220h+var_238]
0x1800451cc  lea     r8, [rbp+220h+var_1D8]
0x1800451d0  lea     rdx, [rbp+220h+var_1B8]
0x1800451d4  lea     rcx, [rbp+220h+var_248]
0x1800451d8  call    ??$TryGetValue@I@Registry@@YA_NAEBUKey@0@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@1AEAI@Z; Registry::TryGetValue<uint>(Registry::Key const &,std::basic_string_view<ushort> const &,std::basic_string_view<ushort> const &,uint &)
0x1800451dd  mov     [rbp+220h+lpMem], rdi
0x1800451e1  lea     rax, aActivepolicyco; "ActivePolicyCode"
0x1800451e8  mov     qword ptr [rbp+220h+var_1D8], rax
0x1800451ec  mov     qword ptr [rbp+220h+var_1D8+8], 10h
0x1800451f4  lea     rax, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800451fb  mov     qword ptr [rbp+220h+var_1B8], rax
0x1800451ff  mov     qword ptr [rbp+220h+var_1B8+8], 36h ; '6'
0x180045207  lea     r9, [rbp+220h+lpMem]
0x18004520b  lea     r8, [rbp+220h+var_1D8]
0x18004520f  lea     rdx, [rbp+220h+var_1B8]
0x180045213  lea     rcx, [rbp+220h+var_248]
0x180045217  call    ??$TryGetValue@Uhstring@winrt@@@Registry@@YA_NAEBUKey@0@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@1AEAUhstring@winrt@@@Z; Registry::TryGetValue<winrt::hstring>(Registry::Key const &,std::basic_string_view<ushort> const &,std::basic_string_view<ushort> const &,winrt::hstring &)
0x18004521c  mov     r14, [rbp+220h+lpMem]
0x180045220  test    r14, r14
0x180045223  jz      short loc_18004522B
0x180045225  mov     rcx, [r14+10h]
0x180045229  jmp     short loc_180045232
0x18004522b  lea     rcx, ApplicationName; lpString1
0x180045232  mov     [rsp+360h+bIgnoreCase], r12d; bIgnoreCase
0x180045237  or      r13, 0FFFFFFFFFFFFFFFFh
0x18004523b  mov     r9d, r13d; cchCount2
0x18004523e  lea     r8, aZh; "zh"
0x180045245  mov     edx, r13d; cchCount1
0x180045248  call    cs:__imp_CompareStringOrdinal
0x18004524e  cmp     eax, 2
0x180045251  setz    [rbp+220h+var_288]
0x180045255  call    cs:__imp_GetTickCount64
0x18004525b  mov     [rbp+220h+var_1F0], rax
0x18004525f  lea     rax, qword_18007F958
0x180045266  mov     qword ptr [rbp+220h+var_1D8], rax
0x18004526a  lock add cs:qword_18007F958, r12
0x180045272  cmp     cs:??$factory_cache_entry_v@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, rdi; factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>
0x180045279  jz      short loc_180045299
0x18004527b  lea     r8, ??$factory_cache_entry_v@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>
0x180045282  lea     rdx, [rbp+220h+var_230]
0x180045286  call    ??R_lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_@@QEBA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x18004528b  lea     r15d, [r13+4]
0x18004528f  lock add cs:qword_18007F958, r13
0x180045297  jmp     short loc_1800452BF
0x180045299  lock add cs:qword_18007F958, r13
0x1800452a1  lea     rax, ?_lambda_invoker_cdecl_@_lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x1800452a8  mov     [rbp+220h+var_250], rax
0x1800452ac  lea     r8, [rbp+220h+var_250]
0x1800452b0  lea     rdx, [rbp+220h+var_230]
0x1800452b4  call    ??$call@P6A?AUPackageManager@Deployment@Management@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUPackageManager@Deployment@Management@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x1800452b9  mov     r15d, 3
0x1800452bf  cmp     word ptr cs:aMicrosoftWindo_3+48h, di; ""
0x1800452c6  jz      short loc_1800452CF
0x1800452c8  call    cs:__imp_abort
0x1800452cf  mov     dword ptr [rbp+220h+var_1D8+8], r12d
0x1800452d3  mov     dword ptr [rbp+220h+var_1D8+0Ch], 24h ; '$'
0x1800452da  lea     rax, aMicrosoftWindo_3; "Microsoft.WindowsStore_8wekyb3d8bbwe"
0x1800452e1  mov     [rbp+220h+var_1C0], rax
0x1800452e5  lea     rax, [rbp+220h+var_1D8+8]
0x1800452e9  mov     qword ptr [rbp+220h+var_1D8], rax
0x1800452ed  lea     r8, [rbp+220h+var_1D8]
0x1800452f1  lea     rdx, [rbp+220h+var_250]
0x1800452f5  lea     rcx, [rbp+220h+var_230]
0x1800452f9  call    ?FindPackages@?$consume_Windows_Management_Deployment_IPackageManager@UIPackageManager@Deployment@Management@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Management_Deployment_IPackageManager<winrt::Windows::Management::Deployment::IPackageManager>::FindPackages(winrt::param::hstring const &)
0x1800452fe  nop
0x1800452ff  xorps   xmm0, xmm0
0x180045302  movups  [rbp+220h+var_178], xmm0
0x180045309  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180045311  movdqu  [rbp+220h+var_168], xmm1
0x180045319  mov     word ptr [rbp+220h+var_178], di
0x180045320  mov     [rbp+220h+ppv], rdi
0x180045324  lea     rdx, [rbp+220h+var_278]
0x180045328  lea     rcx, [rbp+220h+var_250]
0x18004532c  call    ?begin@?$consume_Windows_Foundation_Collections_IIterable@U?$IIterable@UPackage@ApplicationModel@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UPackage@ApplicationModel@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::begin(void)
0x180045331  lea     rdx, [rbp+220h+ppv]
0x180045335  mov     rcx, rax
0x180045338  call    ??9Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator!=(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18004533d  mov     bl, al
0x18004533f  cmp     [rbp+220h+var_278], rdi
0x180045343  jz      short loc_18004534F
0x180045345  lea     rcx, [rbp+220h+var_278]
0x180045349  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18004534e  nop
0x18004534f  test    bl, bl
0x180045351  jz      loc_1800455BC
0x180045357  lea     rdx, [rbp+220h+ppv]
0x18004535b  lea     rcx, [rbp+220h+var_250]
0x18004535f  call    ?begin@?$consume_Windows_Foundation_Collections_IIterable@U?$IIterable@UPackage@ApplicationModel@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UPackage@ApplicationModel@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::begin(void)
0x180045364  nop
0x180045365  lea     rdx, [rbp+220h+var_278]
0x180045369  mov     rcx, rax
0x18004536c  call    ?Current@?$consume_Windows_Foundation_Collections_IIterator@U?$IIterator@UPackage@ApplicationModel@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UPackage@ApplicationModel@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::Current(void)
0x180045371  nop
0x180045372  cmp     [rbp+220h+ppv], rdi
0x180045376  jz      short loc_180045381
0x180045378  lea     rcx, [rbp+220h+ppv]
0x18004537c  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180045381  lea     rdx, [rbp+220h+var_258]
0x180045385  lea     rcx, [rbp+220h+var_278]
0x180045389  call    ?First@?$consume_Windows_Foundation_Collections_IIterable@U?$IIterable@UPackage@ApplicationModel@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UPackage@ApplicationModel@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::First(void)
0x18004538e  nop
0x18004538f  mov     [rbp+220h+var_2A0], rdi
0x180045393  mov     rcx, [rax]
0x180045396  mov     dword ptr [rbp+220h+var_1D8], edi
0x180045399  xorps   xmm0, xmm0
0x18004539c  movdqu  [rbp+220h+var_1D8+8], xmm0
0x1800453a1  mov     rax, [rcx]
0x1800453a4  lea     rdx, [rbp+220h+var_2A0]
0x1800453a8  mov     rax, [rax+38h]
0x1800453ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800453b1  test    eax, eax
0x1800453b3  js      loc_180045E86
0x1800453b9  cmp     [rbp+220h+var_258], rdi
0x1800453bd  jz      short loc_1800453C8
0x1800453bf  lea     rcx, [rbp+220h+var_258]
0x1800453c3  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800453c8  movzx   edx, word ptr [rbp+220h+var_2A0+6]
0x1800453cc  lea     rcx, [rbp+220h+var_68]
0x1800453d3  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x1800453d8  mov     rsi, rax
0x1800453db  movzx   edx, word ptr [rbp+220h+var_2A0+4]
0x1800453df  lea     rcx, [rbp+220h+var_88]
0x1800453e6  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x1800453eb  mov     rdi, rax
0x1800453ee  movzx   edx, word ptr [rbp+220h+var_2A0+2]
0x1800453f2  lea     rcx, [rbp+220h+var_A8]
0x1800453f9  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x1800453fe  mov     rbx, rax
0x180045401  movzx   edx, word ptr [rbp+220h+var_2A0]
0x180045405  lea     rcx, [rbp+220h+var_C8]
0x18004540c  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x180045411  nop
0x180045412  mov     r8, r12
0x180045415  lea     rdx, asc_180059520; "."
0x18004541c  mov     rcx, rax; Src
0x18004541f  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180045424  movups  xmm0, xmmword ptr [rax]
0x180045427  movups  [rbp+220h+var_158], xmm0
0x18004542e  movups  xmm1, xmmword ptr [rax+10h]
0x180045432  movups  [rbp+220h+var_148], xmm1
0x180045439  mov     qword ptr [rax+10h], 0
0x180045441  mov     r15d, 7
0x180045447  mov     [rax+18h], r15
0x18004544b  xor     ecx, ecx
0x18004544d  mov     [rax], cx
0x180045450  mov     r8, rbx
0x180045453  lea     rdx, [rbp+220h+var_158]
0x18004545a  lea     rcx, [rbp+220h+var_E8]
0x180045461  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180045466  nop
0x180045467  mov     r8, r12
0x18004546a  lea     rdx, asc_180059520; "."
0x180045471  mov     rcx, rax; Src
0x180045474  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180045479  movups  xmm0, xmmword ptr [rax]
0x18004547c  movups  [rbp+220h+var_1B8], xmm0
0x180045480  movups  xmm1, xmmword ptr [rax+10h]
0x180045484  movups  [rbp+220h+var_1A8], xmm1
0x180045488  mov     qword ptr [rax+10h], 0
0x180045490  mov     [rax+18h], r15
0x180045494  xor     ecx, ecx
0x180045496  mov     [rax], cx
0x180045499  mov     r8, rdi
0x18004549c  lea     rdx, [rbp+220h+var_1B8]
0x1800454a0  lea     rcx, [rbp+220h+var_108]
0x1800454a7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1800454ac  nop
0x1800454ad  mov     r8, r12
0x1800454b0  lea     rdx, asc_180059520; "."
0x1800454b7  mov     rcx, rax; Src
0x1800454ba  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800454bf  movups  xmm0, xmmword ptr [rax]
0x1800454c2  movups  [rbp+220h+var_1D8], xmm0
0x1800454c6  movups  xmm1, xmmword ptr [rax+10h]
0x1800454ca  movups  xmmword ptr [rbp+58h], xmm1
0x1800454ce  xor     edi, edi
0x1800454d0  mov     [rax+10h], rdi
0x1800454d4  mov     [rax+18h], r15
0x1800454d8  mov     [rax], di
0x1800454db  lea     r15d, [rdi+3Fh]
0x1800454df  mov     r8, rsi
0x1800454e2  lea     rdx, [rbp+220h+var_1D8]
0x1800454e6  lea     rcx, [rbp+220h+var_128]
0x1800454ed  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1800454f2  mov     rbx, rax
0x1800454f5  lea     rax, [rbp+220h+var_178]
0x1800454fc  cmp     rax, rbx
0x1800454ff  jz      short loc_180045531
0x180045501  lea     rcx, [rbp+220h+var_178]
0x180045508  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004550d  movups  xmm0, xmmword ptr [rbx]
  ... truncated ...
```
