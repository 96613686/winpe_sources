# _lambda_7c7358bdb8ad2d702609f9ef1e5c76e9_::operator()

- ea: `0x1800939ac`
- end: `0x18009480d`
- name: `_lambda_7c7358bdb8ad2d702609f9ef1e5c76e9_::operator()`
- size: `3681`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180105030`

## callees

- `0x180004e38`
- `0x18000522c`
- `0x180006038`
- `0x18000c4a8`
- `0x18000e090`
- `0x18000e5f4`
- `0x180013360`
- `0x18001a3c8`
- `0x18001bf30`
- `0x18002ee38`
- `0x1800542a8`
- `0x180067e60`
- `0x180075c5c`
- `0x180077010`
- `0x180084690`
- `0x180085b00`
- `0x1800939ac`
- `0x180094814`
- `0x180094854`
- `0x18009487c`
- `0x1800a45d4`
- `0x1800a56d4`
- `0x1800b9ecc`
- `0x1800ba0d0`
- `0x1800ba574`
- `0x180104628`
- `0x1801071a4`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180093adb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180093adb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180093b87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180093b87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180094547`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180094547`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180094007`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009410d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180094007`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009410d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180094751`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180094765`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009478c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800947c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180094751`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180094765`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009478c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800947c5`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180094690`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180094690`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180094565`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180094565`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18009459b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18009459b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800946a5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800946a5`

## string_xrefs

- `0x180093e13`: `AdaptiveJson`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall lambda_7c7358bdb8ad2d702609f9ef1e5c76e9_::operator()(__int64 **a1)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // eax
  __int64 v5; // rsi
  __int64 (__fastcall *v6)(__int64, __int64 *); // rdi
  __int64 *v7; // rbx
  int v8; // eax
  struct _RTL_CRITICAL_SECTION *v9; // rsi
  __int64 *v10; // rax
  __int64 *v11; // rdi
  char v12; // al
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, GUID *, int (__fastcall ****)(_QWORD, _QWORD, _QWORD)); // rbx
  int v15; // eax
  __int64 v16; // rdx
  unsigned __int16 **v17; // r8
  int v18; // eax
  void *v19; // rsi
  int v20; // eax
  int v21; // eax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, __int64 *); // rbx
  int v24; // eax
  __int64 v25; // rax
  int v26; // ecx
  __int64 *v27; // rcx
  __int64 v28; // rax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  __int64 v32; // r14
  __int64 (__fastcall *v33)(__int64, __int64 *); // rdi
  __int64 *v34; // rbx
  int v35; // eax
  LPVOID *v36; // rdi
  __int64 v37; // r14
  __int64 (__fastcall *v38)(__int64, LPCWCH *); // rbx
  int v39; // eax
  __int64 v40; // rdx
  const WCHAR *v41; // rbx
  const WCHAR *v42; // rcx
  __int64 v43; // r14
  __int64 (__fastcall *v44)(__int64, LPVOID *); // rbx
  int v45; // eax
  __int64 *v46; // rax
  int v47; // eax
  __int64 v48; // rdx
  __int64 v49; // r15
  int (__fastcall *v50)(__int64, __int64 *); // r14
  __int64 *v51; // rbx
  __int64 v52; // rcx
  __int64 v53; // rax
  __int64 v54; // r15
  __int64 (__fastcall *v55)(__int64, __int64 *); // r14
  __int64 *v56; // rbx
  int v57; // eax
  unsigned int v58; // r15d
  __int64 v59; // rcx
  __int64 v60; // rax
  int v61; // eax
  int v62; // eax
  __int64 *v63; // rcx
  __int64 v64; // rax
  int v65; // eax
  __int64 v66; // rcx
  int v67; // eax
  __int64 v68; // r14
  __int64 (__fastcall *v69)(__int64, __int64 *); // rbx
  int v70; // eax
  int v71; // eax
  __int64 v72; // r14
  __int64 (__fastcall *v73)(__int64, _QWORD, const WCHAR **, __int64 *); // rbx
  int v74; // eax
  __int64 *v75; // rdx
  int (__fastcall ***v76)(_QWORD, _QWORD, _QWORD); // rbx
  int (__fastcall *v77)(_QWORD, GUID *, struct _RTL_CRITICAL_SECTION **); // r14
  const char *v78; // r9
  __int64 v79; // rcx
  const char *v80; // r9
  __int64 v81; // rcx
  int (__fastcall ***v82)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 result; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-118h]
  LPCWCH lpString1; // [rsp+40h] [rbp-F8h] BYREF
  __int64 v86; // [rsp+48h] [rbp-F0h]
  void *phNewTimer; // [rsp+50h] [rbp-E8h] BYREF
  __int64 v88; // [rsp+58h] [rbp-E0h] BYREF
  const WCHAR *v89; // [rsp+60h] [rbp-D8h] BYREF
  __int64 v90; // [rsp+68h] [rbp-D0h] BYREF
  __int64 v91; // [rsp+70h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-C0h] BYREF
  LPVOID v93; // [rsp+80h] [rbp-B8h] BYREF
  wchar_t *String1; // [rsp+88h] [rbp-B0h] BYREF
  LPVOID v95; // [rsp+90h] [rbp-A8h] BYREF
  __int64 v96; // [rsp+98h] [rbp-A0h] BYREF
  __int128 v97; // [rsp+A0h] [rbp-98h] BYREF
  __int64 v98; // [rsp+B0h] [rbp-88h]
  __int128 v99; // [rsp+B8h] [rbp-80h] BYREF
  __int64 v100; // [rsp+C8h] [rbp-70h]
  LPVOID *v101; // [rsp+D0h] [rbp-68h]
  _QWORD v102[2]; // [rsp+D8h] [rbp-60h] BYREF
  __int64 v103; // [rsp+E8h] [rbp-50h] BYREF
  int v104; // [rsp+F0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]
  struct _RTL_CRITICAL_SECTION *v106; // [rsp+140h] [rbp+8h] BYREF
  int v107; // [rsp+148h] [rbp+10h] BYREF
  int v108; // [rsp+150h] [rbp+18h] BYREF
  int (__fastcall ***v109)(_QWORD, GUID *, struct _RTL_CRITICAL_SECTION **); // [rsp+158h] [rbp+20h] BYREF

  v2 = **a1;
  try
  {
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 72LL))(v2);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA3,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v3,
        bIgnoreCase);
    v107 = 0;
    v4 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a1[2] + 24LL))(*a1[2], &v107);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA5,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v4,
        bIgnoreCase);
    v5 = *a1[2];
    v6 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 32LL);
    v7 = a1[3];
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      v7,
      0);
    v8 = v6(v5, v7);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA7,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v8,
        bIgnoreCase);
    if ( (byte_18015DE48 & 1) != 0 )
      McTemplateU0dzqj_EventWriteTransfer(
        (unsigned int)a1[4],
        (unsigned int)WPNUI_NEW_TOAST_NOTIFICATION_DELIVERING,
        v107,
        *a1[3],
        *((_DWORD *)a1[4] + 4),
        (__int64)a1[1]);
    v109 = 0;
    v9 = (struct _RTL_CRITICAL_SECTION *)(a1[4] + 12);
    EnterCriticalSection(v9);
    v106 = v9;
    v10 = a1[4];
    v11 = v10 + 4;
    if ( !*((_DWORD *)v10 + 5) || (v12 = 0, !*v11) )
      v12 = 1;
    if ( v12 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB3,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)0x80004005LL,
        bIgnoreCase);
    v13 = *v11;
    v14 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, int (__fastcall ****)(_QWORD, _QWORD, _QWORD)))(*(_QWORD *)v13 + 40LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v109);
    v15 = v14(
            v13,
            *((unsigned int *)a1[4] + 5),
            &GUID_904a654e_bee8_4654_bbba_e78766776239,
            (int (__fastcall ****)(_QWORD, _QWORD, _QWORD))&v109);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB7,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v15,
        bIgnoreCase);
    if ( v9 )
      LeaveCriticalSection(v9);
    *a1[5] = *a1[3];
    v95 = 0;
    LOBYTE(v16) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_39992759>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_39992759>::GetImpl'::`2'::impl,
      v16);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v95,
      0);
    v18 = WpnDatabaseHelpers::PopulatePackageFullName(
            (WpnDatabaseHelpers *)*a1[6],
            (struct INotificationHandler *)&v95,
            v17);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBF,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v18,
        bIgnoreCase);
    v19 = v95;
    a1[5][1] = (__int64)v95;
    v20 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a1[2] + 24LL))(*a1[2], a1[5] + 2);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC8,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v20,
        bIgnoreCase);
    v96 = 0;
    (*(void (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a1[2] + 88LL))(*a1[2], &v96);
    a1[5][3] = v96;
    v108 = 0;
    v21 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a1[2] + 80LL))(*a1[2], &v108);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCF,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v21,
        bIgnoreCase);
    if ( v108 )
    {
      *((_DWORD *)a1[5] + 5) |= 1u;
      v106 = 0;
      (*(void (__fastcall **)(_QWORD, struct _RTL_CRITICAL_SECTION **))(*(_QWORD *)*a1[2] + 72LL))(*a1[2], &v106);
      a1[5][4] = (__int64)v106;
    }
    v91 = 0;
    v22 = *a1[2];
    v23 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v91);
    v24 = v23(v22, &v91);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDA,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v24,
        bIgnoreCase);
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<TileSession>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<TileSession>>>>>>>(&v103);
    v25 = WpnDatabaseHelpers::VectorFromStream(&lpString1, v91);
    std::vector<unsigned char>::operator=(&v103, v25);
    std::vector<unsigned char>::_Tidy(&lpString1);
    v26 = v103;
    a1[5][5] = v103;
    *((_DWORD *)a1[5] + 12) = v104 - v26;
    String1 = 0;
    v27 = (__int64 *)*a1[2];
    v28 = *v27;
    String1 = 0;
    v29 = (*(__int64 (__fastcall **)(__int64 *, wchar_t **))(v28 + 120))(v27, &String1);
    if ( v29 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE2,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v29,
        bIgnoreCase);
    *((_DWORD *)a1[5] + 13) = wcscmp_0(String1, L"AdaptiveJson") == 0;
    v30 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)**a1 + 56LL))(**a1, a1[5] + 8);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE5,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v30,
        bIgnoreCase);
    v31 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)**a1 + 96LL))(**a1, a1[5] + 20);
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE7,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v31,
        bIgnoreCase);
    v32 = **a1;
    v33 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 104LL);
    v34 = a1[7];
    wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
      v34,
      0);
    v35 = v33(v32, v34);
    if ( v35 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE9,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v35,
        bIgnoreCase);
    a1[5][21] = *a1[7];
    v36 = 0;
    v101 = 0;
    v93 = 0;
    if ( *a1[8] )
    {
      v36 = (LPVOID *)operator new(0xB0u);
      memset_0(v36, 0, 0xB0u);
      v101 = v36;
      lpString1 = 0;
      v86 = 0;
      phNewTimer = 0;
      v37 = *a1[8];
      v38 = *(__int64 (__fastcall **)(__int64, LPCWCH *))(*(_QWORD *)v37 + 40LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
      v86 = -1;
      phNewTimer = (void *)-1LL;
      v39 = v38(v37, &lpString1);
      if ( v39 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xF3,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v39,
          bIgnoreCase);
      LODWORD(v40) = v86;
      if ( v86 == -1 )
      {
        if ( lpString1 )
        {
          v40 = -1;
          do
            ++v40;
          while ( lpString1[v40] );
        }
        else
        {
          LODWORD(v40) = 0;
        }
      }
      v41 = &word_180124798;
      v42 = &word_180124798;
      if ( lpString1 )
        v42 = lpString1;
      if ( CompareStringOrdinal(v42, v40, L"toast", -1, 0) == 2 )
      {
        v43 = *a1[8];
        v44 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v43 + 32LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v93,
          0);
        v45 = v44(v43, &v93);
        if ( v45 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF7,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
            (const char *)(unsigned int)v45,
            bIgnoreCase);
        *v36 = v93;
        v46 = a1[5];
        if ( *(_BYTE *)a1[9] )
          *((_DWORD *)v46 + 5) |= 2u;
        else
          *((_DWORD *)v46 + 5) |= 4u;
        v47 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*a1[8] + 24LL))(*a1[8], v36 + 2);
        if ( v47 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x102,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
            (const char *)(unsigned int)v47,
            bIgnoreCase);
        a1[5][7] = (__int64)v36;
      }
      else
      {
        LODWORD(v48) = v86;
        if ( v86 == -1 )
        {
          if ( lpString1 )
          {
            v48 = -1;
            do
              ++v48;
            while ( lpString1[v48] );
          }
          else
          {
            LODWORD(v48) = 0;
          }
        }
        if ( lpString1 )
          v41 = lpString1;
        if ( CompareStringOrdinal(v41, v48, L"toastCondensed", -1, 0) == 2 )
          *((_DWORD *)a1[5] + 5) |= 8u;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
    }
    else
    {
      a1[5][7] = 0;
    }
    if ( *(_BYTE *)a1[10] )
      *((_DWORD *)a1[5] + 5) |= 8u;
    v49 = *a1[2];
    v50 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v49 + 56LL);
    v51 = a1[11];
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      v51,
      0);
    if ( v50(v49, v51) >= 0 )
    {
      v52 = *a1[11];
      if ( v52 )
      {
        v53 = -1;
        do
          ++v53;
        while ( *(_WORD *)(v52 + 2 * v53) );
        if ( v53 )
          a1[5][10] = v52;
      }
    }
    v54 = *a1[2];
    v55 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v54 + 64LL);
    v56 = a1[12];
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      v56,
      0);
    v57 = v55(v54, v56);
    v58 = 0;
    if ( v57 >= 0 )
    {
      v59 = *a1[12];
      if ( v59 )
      {
        v60 = -1;
        do
          ++v60;
        while ( *(_WORD *)(v59 + 2 * v60) );
        if ( v60 )
          a1[5][11] = v59;
      }
    }
    v61 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)**a1 + 48LL))(**a1, a1[13]);
    if ( v61 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11E,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v61,
        bIgnoreCase);
    if ( *(_DWORD *)a1[13] )
      *((_DWORD *)a1[5] + 5) |= 0x10u;
    v62 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)**a1 + 24LL))(**a1, a1[5] + 12);
    if ( v62 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x124,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v62,
        bIgnoreCase);
    pv = 0;
    v63 = (__int64 *)**a1;
    v64 = *v63;
    pv = 0;
    v65 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v64 + 32))(v63, &pv);
    if ( v65 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x127,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v65,
        bIgnoreCase);
    if ( pv )
    {
      v66 = -1;
      do
        ++v66;
      while ( *((_WORD *)pv + v66) );
      if ( v66 )
        a1[5][13] = (__int64)pv;
    }
    v67 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)**a1 + 72LL))(**a1, a1[5] + 14);
    if ( v67 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v67,
        bIgnoreCase);
    v90 = 0;
    v68 = *a1[2];
    v69 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v68 + 96LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v90);
    v70 = v69(v68, &v90);
    if ( v70 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x133,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v70,
        bIgnoreCase);
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<TileSession>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<TileSession>>>>>>>(&v97);
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<TileSession>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<TileSession>>>>>>>(&v99);
    if ( v90 )
    {
      LODWORD(v106) = 0;
      v71 = (*(__int64 (__fastcall **)(__int64, struct _RTL_CRITICAL_SECTION **))(*(_QWORD *)v90 + 48LL))(v90, &v106);
      if ( v71 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x13B,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v71,
          bIgnoreCase);
      if ( (_DWORD)v106 )
      {
        std::vector<_WPN_NOTIFICATION_METADATA_PAIR>::reserve(&v99, (unsigned int)v106);
        std::vector<std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>::reserve(
          &v97,
          (unsigned int)v106);
        while ( v58 < (unsigned int)v106 )
        {
          v89 = 0;
          v88 = 0;
          v72 = v90;
          v73 = *(__int64 (__fastcall **)(__int64, _QWORD, const WCHAR **, __int64 *))(*(_QWORD *)v90 + 56LL);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v88,
            0);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v89,
            0);
          v74 = v73(v72, v58, &v89, &v88);
          if ( v74 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x145,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
              (const char *)(unsigned int)v74,
              bIgnoreCase);
          lpString1 = v89;
          v86 = v88;
          std::vector<_WPN_NOTIFICATION_METADATA_PAIR>::push_back(&v99, &lpString1);
          v102[0] = v89;
          v89 = 0;
          v102[1] = v88;
          v88 = 0;
          std::vector<std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>::push_back(
            &v97,
            v102);
          std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v102);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v88);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v89);
          ++v58;
        }
        a1[5][17] = v99;
        *((_DWORD *)a1[5] + 33) = (_DWORD)v106;
      }
    }
    LODWORD(lpString1) = GetCurrentThreadId();
    BYTE4(lpString1) = 0;
    LODWORD(v86) = -2147467259;
    phNewTimer = 0;
    LODWORD(v86) = CoEnableCallCancellation(0);
    if ( (int)v86 >= 0 )
      CreateTimerQueueTimer(&phNewTimer, 0, CBaseRPCTimeout::s_Callback, &lpString1, 0x2710u, 0x3E8u, 0);
    v75 = a1[4];
    if ( *((_BYTE *)v75 + 136) )
    {
      v106 = 0;
      v76 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v109;
      v77 = **v109;
      Microsoft::WRL::ComPtr<INotificationDatabase5>::InternalRelease(&v106);
      if ( v77(v76, &GUID_4910aaa5_a6eb_45c1_9b08_67d9f538b991, &v106) >= 0 )
        *(_DWORD *)a1[14] = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, struct _RTL_CRITICAL_SECTION **), _QWORD, __int64 *, __int64))(*v109)[3])(
                              v109,
                              *((unsigned int *)a1[4] + 4),
                              a1[5],
                              1);
      Microsoft::WRL::ComPtr<INotificationDatabase5>::InternalRelease(&v106);
    }
    else
    {
      *(_DWORD *)a1[14] = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, struct _RTL_CRITICAL_SECTION **), _QWORD, __int64 *, __int64))(*v109)[3])(
                            v109,
                            *((unsigned int *)v75 + 4),
                            a1[5],
                            1);
    }
    v78 = (const char *)*(unsigned int *)a1[14];
    if ( (int)v78 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x15F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        v78,
        bIgnoreCase);
    if ( (int)v86 >= 0 )
    {
      LODWORD(v86) = -2147467259;
      CoDisableCallCancellation(0);
      if ( phNewTimer )
        DeleteTimerQueueTimer(0, phNewTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    }
    if ( (_QWORD)v99 )
    {
      std::_Deallocate<16>((void *)v99, (v100 - v99) & 0xFFFFFFFFFFFFFFF0uLL);
      v99 = 0;
      v100 = 0;
    }
    if ( (_QWORD)v97 )
    {
      std::_Destroy_range<std::allocator<std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>>(
        v97,
        *((__int64 *)&v97 + 1));
      std::_Deallocate<16>((void *)v97, (v98 - v97) & 0xFFFFFFFFFFFFFFF0uLL);
      v97 = 0;
      v98 = 0;
    }
    v79 = v90;
    if ( v90 )
    {
      v90 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
    }
    if ( pv )
      CoTaskMemFree(pv);
    if ( v93 )
      CoTaskMemFree(v93);
    if ( v36 )
      operator delete(v36);
    if ( String1 )
      CoTaskMemFree(String1);
    std::vector<unsigned char>::_Tidy(&v103);
    v81 = v91;
    if ( v91 )
    {
      v91 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
    }
    if ( v19 )
      CoTaskMemFree(v19);
    v82 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v109;
    if ( v109 )
    {
      v109 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v82)[2])(v82);
    }
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v106) = wil::details::in1diag3::Return_CaughtException(
                      retaddr,
                      (void *)0x163,
                      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
                      v80);
    return (unsigned int)v106;
  }
  return result;
}

```

## disassembly

```asm
0x1800939ac  push    rbx
0x1800939ae  push    rsi
0x1800939af  push    rdi
0x1800939b0  push    r12
0x1800939b2  push    r13
0x1800939b4  push    r14
0x1800939b6  push    r15
0x1800939b8  sub     rsp, 100h
0x1800939bf  mov     r12, rcx
0x1800939c2  mov     rax, [rcx]
0x1800939c5  mov     rcx, [rax]
0x1800939c8  mov     rax, [rcx]
0x1800939cb  mov     rdx, [r12+8]
0x1800939d0  mov     rax, [rax+48h]
0x1800939d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800939d9  mov     rcx, [rsp+138h]; this
0x1800939e1  xor     r15d, r15d
0x1800939e4  test    eax, eax
0x1800939e6  jns     short loc_1800939FC
0x1800939e8  mov     r9d, eax; char *
0x1800939eb  lea     r8, aOnecoreuapBase_46; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800939f2  mov     edx, 0A3h; void *
0x1800939f7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800939fc  mov     [rsp+138h+arg_8], r15d
0x180093a04  mov     rax, [r12+10h]
0x180093a09  mov     rcx, [rax]
0x180093a0c  mov     rax, [rcx]
0x180093a0f  lea     rdx, [rsp+138h+arg_8]
0x180093a17  mov     rax, [rax+18h]
0x180093a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093a20  mov     rcx, [rsp+138h]; this
0x180093a28  test    eax, eax
0x180093a2a  jns     short loc_180093A40
0x180093a2c  mov     r9d, eax; char *
0x180093a2f  lea     r8, aOnecoreuapBase_46; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180093a36  mov     edx, 0A5h; void *
0x180093a3b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093a40  mov     rax, [r12+10h]
0x180093a45  mov     rsi, [rax]
0x180093a48  mov     rax, [rsi]
0x180093a4b  mov     rdi, [rax+20h]
0x180093a4f  mov     rbx, [r12+18h]
0x180093a54  xor     edx, edx
0x180093a56  mov     rcx, rbx
0x180093a59  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180093a5e  mov     rdx, rbx
0x180093a61  mov     rcx, rsi
0x180093a64  mov     rax, rdi
0x180093a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093a6c  mov     rcx, [rsp+138h]; this
0x180093a74  test    eax, eax
0x180093a76  jns     short loc_180093A8C
0x180093a78  mov     r9d, eax; char *
0x180093a7b  lea     r8, aOnecoreuapBase_46; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180093a82  mov     edx, 0A7h; void *
0x180093a87  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093a8c  test    cs:byte_18015DE48, 1
0x180093a93  jz      short loc_180093AC7
0x180093a95  mov     rcx, [r12+20h]
0x180093a9a  mov     r9, [r12+18h]
0x180093a9f  mov     rax, [r12+8]
0x180093aa4  mov     qword ptr [rsp+138h+Period], rax
0x180093aa9  mov     eax, [rcx+10h]
0x180093aac  mov     [rsp+138h+bIgnoreCase], eax; int
0x180093ab0  mov     r9, [r9]
0x180093ab3  mov     r8d, [rsp+138h+arg_8]
0x180093abb  lea     rdx, WPNUI_NEW_TOAST_NOTIFICATION_DELIVERING
0x180093ac2  call    McTemplateU0dzqj_EventWriteTransfer
0x180093ac7  mov     [rsp+138h+arg_18], r15
0x180093acf  mov     rsi, [r12+20h]
0x180093ad4  add     rsi, 60h ; '`'
0x180093ad8  mov     rcx, rsi; lpCriticalSection
0x180093adb  call    cs:__imp_EnterCriticalSection
0x180093ae1  mov     [rsp+138h+arg_0], rsi
0x180093ae9  mov     rax, [r12+20h]
0x180093aee  lea     rdi, [rax+20h]
0x180093af2  cmp     [rax+14h], r15d
0x180093af6  jz      short loc_180093B00
0x180093af8  cmp     [rdi], r15
0x180093afb  mov     al, r15b
0x180093afe  jnz     short loc_180093B02
0x180093b00  mov     al, 1
0x180093b02  mov     rcx, [rsp+138h]; this
0x180093b0a  test    al, al
0x180093b0c  jz      short loc_180093B25
0x180093b0e  mov     r9d, 80004005h; char *
0x180093b14  lea     r8, aOnecoreuapBase_46; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180093b1b  mov     edx, 0B3h; void *
0x180093b20  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093b25  mov     rdi, [rdi]
0x180093b28  mov     rax, [rdi]
0x180093b2b  mov     rbx, [rax+28h]
0x180093b2f  lea     rcx, [rsp+138h+arg_18]
0x180093b37  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180093b3c  mov     rdx, [r12+20h]
0x180093b41  lea     r9, [rsp+138h+arg_18]
0x180093b49  lea     r8, _GUID_904a654e_bee8_4654_bbba_e78766776239
0x180093b50  mov     edx, [rdx+14h]
0x180093b53  mov     rcx, rdi
0x180093b56  mov     rax, rbx
0x180093b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093b5e  mov     rcx, [rsp+138h]; this
0x180093b66  test    eax, eax
0x180093b68  jns     short loc_180093B7F
0x180093b6a  mov     r9d, eax; char *
0x180093b6d  lea     r8, aOnecoreuapBase_46; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180093b74  mov     edx, 0B7h; void *
0x180093b79  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093b7f  test    rsi, rsi
0x180093b82  jz      short loc_180093B8D
0x180093b84  mov     rcx, rsi; lpCriticalSection
0x180093b87  call    cs:__imp_LeaveCriticalSection
0x180093b8d  mov     rax, [r12+18h]
0x180093b92  mov     rcx, [r12+28h]
0x180093b97  mov     rax, [rax]
0x180093b9a  mov     [rcx], rax
0x180093b9d  mov     [rsp+138h+var_A8], r15
0x180093ba5  mov     dl, 1
0x180093ba7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_39992759@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_39992759@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39992759> `wil::Feature<__WilFeatureTraits_Feature_39992759>::GetImpl(void)'::`2'::impl
0x180093bae  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_39992759@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39992759>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180093bb3  xor     edx, edx
0x180093bb5  lea     rcx, [rsp+138h+var_A8]
0x180093bbd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180093bc2  mov     rcx, [r12+30h]
0x180093bc7  lea     rdx, [rsp+138h+var_A8]; struct INotificationHandler *
0x180093bcf  mov     rcx, [rcx]; this
0x180093bd2  call    ?PopulatePackageFullName@WpnDatabaseHelpers@@YAJPEAUINotificationHandler@@PEAPEAG@Z; WpnDatabaseHelpers::PopulatePackageFullName(INotificationHandler *,ushort * *)
0x180093bd7  mov     rcx, [rsp+138h]; this
0x180093bdf  test    eax, eax
0x180093be1  jns     short loc_180093BF7
0x180093be3  mov     r9d, eax; char *
0x180093be6  lea     r8, aOnecoreuapBase_46; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180093bed  mov     edx, 0BFh; void *
0x180093bf2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093bf7  mov     rax, [r12+28h]
0x180093bfc  mov     rsi, [rsp+138h+var_A8]
0x180093c04  mov     [rax+8], rsi
0x180093c08  mov     rax, [r12+10h]
0x180093c0d  mov     rcx, [rax]
0x180093c10  mov     rax, [rcx]
0x180093c13  mov     rdx, [r12+28h]
0x180093c18  add     rdx, 10h
0x180093c1c  mov     rax, [rax+18h]
0x180093c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093c25  mov     rcx, [rsp+138h]; this
0x180093c2d  test    eax, eax
0x180093c2f  jns     short loc_180093C45
0x180093c31  mov     r9d, eax; char *
0x180093c34  lea     r8, aOnecoreuapBase_46; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180093c3b  mov     edx, 0C8h; void *
0x180093c40  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093c45  mov     [rsp+138h+var_A0], r15
0x180093c4d  mov     rax, [r12+10h]
0x180093c52  mov     rcx, [rax]
0x180093c55  mov     rax, [rcx]
0x180093c58  lea     rdx, [rsp+138h+var_A0]
0x180093c60  mov     rax, [rax+58h]
0x180093c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093c69  mov     ecx, dword ptr [rsp+138h+var_A0+4]
0x180093c70  shl     rcx, 20h
0x180093c74  mov     eax, dword ptr [rsp+138h+var_A0]
0x180093c7b  or      rcx, rax
0x180093c7e  mov     rax, [r12+28h]
0x180093c83  mov     [rax+18h], rcx
0x180093c87  mov     [rsp+138h+arg_10], r15d
0x180093c8f  mov     rax, [r12+10h]
0x180093c94  mov     rcx, [rax]
0x180093c97  mov     rax, [rcx]
0x180093c9a  lea     rdx, [rsp+138h+arg_10]
0x180093ca2  mov     rax, [rax+50h]
0x180093ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093cab  mov     rcx, [rsp+138h]; this
0x180093cb3  test    eax, eax
0x180093cb5  jns     short loc_180093CCB
0x180093cb7  mov     r9d, eax; char *
0x180093cba  lea     r8, aOnecoreuapBase_46; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180093cc1  mov     edx, 0CFh; void *
0x180093cc6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093ccb  cmp     [rsp+138h+arg_10], r15d
0x180093cd3  jz      short loc_180093D20
0x180093cd5  mov     rax, [r12+28h]
0x180093cda  or      dword ptr [rax+14h], 1
0x180093cde  mov     [rsp+138h+arg_0], r15
0x180093ce6  mov     rax, [r12+10h]
0x180093ceb  mov     rcx, [rax]
0x180093cee  mov     rax, [rcx]
0x180093cf1  lea     rdx, [rsp+138h+arg_0]
0x180093cf9  mov     rax, [rax+48h]
0x180093cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093d02  mov     ecx, dword ptr [rsp+138h+arg_0+4]
0x180093d09  shl     rcx, 20h
0x180093d0d  mov     eax, dword ptr [rsp+138h+arg_0]
0x180093d14  or      rcx, rax
0x180093d17  mov     rax, [r12+28h]
0x180093d1c  mov     [rax+20h], rcx
0x180093d20  mov     [rsp+138h+var_C8], r15
0x180093d25  mov     rax, [r12+10h]
0x180093d2a  mov     rdi, [rax]
0x180093d2d  mov     rax, [rdi]
0x180093d30  mov     rbx, [rax+30h]
0x180093d34  lea     rcx, [rsp+138h+var_C8]
0x180093d39  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180093d3e  lea     rdx, [rsp+138h+var_C8]
0x180093d43  mov     rcx, rdi
0x180093d46  mov     rax, rbx
0x180093d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093d4e  mov     rcx, [rsp+138h]; this
0x180093d56  test    eax, eax
0x180093d58  jns     short loc_180093D6E
0x180093d5a  mov     r9d, eax; char *
0x180093d5d  lea     r8, aOnecoreuapBase_46; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180093d64  mov     edx, 0DAh; void *
0x180093d69  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093d6e  lea     rcx, [rsp+138h+var_50]
0x180093d76  call    ??$?0AEBV?$allocator@U?$pair@$$CBKV?$shared_ptr@VTileSession@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@VTileSession@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBKV?$shared_ptr@VTileSession@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<TileSession>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<TileSession>>>>>>>(std::allocator<std::pair<ulong const,std::shared_ptr<TileSession>>> const &)
0x180093d7b  nop
0x180093d7c  mov     rdx, [rsp+138h+var_C8]
0x180093d81  lea     rcx, [rsp+138h+lpString1]
0x180093d86  call    ?VectorFromStream@WpnDatabaseHelpers@@YA?AV?$vector@EV?$allocator@E@std@@@std@@PEAUIStream@@@Z; WpnDatabaseHelpers::VectorFromStream(IStream *)
0x180093d8b  mov     rdx, rax
0x180093d8e  lea     rcx, [rsp+138h+var_50]
0x180093d96  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x180093d9b  lea     rcx, [rsp+138h+lpString1]
0x180093da0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180093da5  mov     rax, [r12+28h]
0x180093daa  mov     rcx, [rsp+138h+var_50]
0x180093db2  mov     [rax+28h], rcx
0x180093db6  mov     edx, [rsp+138h+var_48]
0x180093dbd  sub     edx, ecx
0x180093dbf  mov     rax, [r12+28h]
0x180093dc4  mov     [rax+30h], edx
0x180093dc7  mov     [rsp+138h+String1], r15
0x180093dcf  mov     rax, [r12+10h]
0x180093dd4  mov     rcx, [rax]
0x180093dd7  mov     rax, [rcx]
0x180093dda  mov     [rsp+138h+String1], r15
0x180093de2  lea     rdx, [rsp+138h+String1]
0x180093dea  mov     rax, [rax+78h]
0x180093dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093df3  mov     rcx, [rsp+138h]; this
0x180093dfb  test    eax, eax
0x180093dfd  jns     short loc_180093E13
0x180093dff  mov     r9d, eax; char *
0x180093e02  lea     r8, aOnecoreuapBase_46; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180093e09  mov     edx, 0E2h; void *
0x180093e0e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093e13  lea     rdx, aAdaptivejson; "AdaptiveJson"
0x180093e1a  mov     rcx, [rsp+138h+String1]; String1
0x180093e22  call    wcscmp_0
0x180093e27  mov     ecx, r15d
0x180093e2a  test    eax, eax
0x180093e2c  setz    cl
0x180093e2f  mov     rax, [r12+28h]
0x180093e34  mov     [rax+34h], ecx
0x180093e37  mov     rax, [r12]
0x180093e3b  mov     rcx, [rax]
0x180093e3e  mov     rax, [rcx]
0x180093e41  mov     rdx, [r12+28h]
0x180093e46  add     rdx, 40h ; '@'
0x180093e4a  mov     rax, [rax+38h]
0x180093e4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093e53  mov     rcx, [rsp+138h]; this
0x180093e5b  test    eax, eax
0x180093e5d  jns     short loc_180093E73
0x180093e5f  mov     r9d, eax; char *
0x180093e62  lea     r8, aOnecoreuapBase_46; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180093e69  mov     edx, 0E5h; void *
0x180093e6e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093e73  mov     rax, [r12]
0x180093e77  mov     rcx, [rax]
0x180093e7a  mov     rax, [rcx]
0x180093e7d  mov     rdx, [r12+28h]
0x180093e82  add     rdx, 0A0h
0x180093e89  mov     rax, [rax+60h]
0x180093e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093e92  mov     rcx, [rsp+138h]; this
0x180093e9a  test    eax, eax
0x180093e9c  jns     short loc_180093EB2
0x180093e9e  mov     r9d, eax; char *
0x180093ea1  lea     r8, aOnecoreuapBase_46; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180093ea8  mov     edx, 0E7h; void *
0x180093ead  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093eb2  mov     rax, [r12]
0x180093eb6  mov     r14, [rax]
0x180093eb9  mov     rax, [r14]
0x180093ebc  mov     rdi, [rax+68h]
0x180093ec0  mov     rbx, [r12+38h]
0x180093ec5  xor     edx, edx
0x180093ec7  mov     rcx, rbx
0x180093eca  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x180093ecf  mov     rdx, rbx
0x180093ed2  mov     rcx, r14
0x180093ed5  mov     rax, rdi
0x180093ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093edd  mov     rcx, [rsp+138h]; this
0x180093ee5  test    eax, eax
0x180093ee7  jns     short loc_180093EFD
0x180093ee9  mov     r9d, eax; char *
0x180093eec  lea     r8, aOnecoreuapBase_46; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180093ef3  mov     edx, 0E9h; void *
  ... truncated ...
```
