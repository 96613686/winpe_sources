# BackgroundActivation::ActivateRawNotificationWorkItem(INotificationHandler *,Notification *,TransientNotificationDetails *,_GUID)

- ea: `0x180099b48`
- end: `0x18009aa64`
- name: `?ActivateRawNotificationWorkItem@BackgroundActivation@@QEAAJPEAUINotificationHandler@@PEAVNotification@@PEAVTransientNotificationDetails@@U_GUID@@@Z`
- size: `3868`
- prototype: `int(BackgroundActivation *__hidden this, struct INotificationHandler *, struct Notification *, struct TransientNotificationDetails *, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `37`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180054a78`
- `0x180056420`

## callees

- `0x180004e38`
- `0x18000a784`
- `0x18000e090`
- `0x18000e5f4`
- `0x1800117c0`
- `0x18001bf30`
- `0x180023540`
- `0x1800236a4`
- `0x180023820`
- `0x18002ee38`
- `0x18002f224`
- `0x1800394ec`
- `0x18004d6f0`
- `0x18004f124`
- `0x1800542a8`
- `0x180057ad0`
- `0x180058bb4`
- `0x18005b2b4`
- `0x18005c090`
- `0x18006244c`
- `0x18006a36c`
- `0x18006a3f0`
- `0x18006dfa0`
- `0x180070fc0`
- `0x1800710cc`
- `0x180082308`
- `0x180099b48`
- `0x18009aa6c`
- `0x18009ab50`
- `0x18009ad38`
- `0x18009c2e0`
- `0x1800a57a0`
- `0x1800a5b54`
- `0x1800b99f0`
- `0x1800bc541`
- `0x1800f59ec`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180099e83`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180099e83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099e75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099f5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099e75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099f5f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099f6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099f6d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180099d70`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180099d70`
- `ntdll!RtlPublishWnfStateData` at `0x180099f43`
- `ntdll!RtlPublishWnfStateData` at `0x180099fa1`
- `ntdll!RtlPublishWnfStateData` at `0x180099f43`
- `ntdll!RtlPublishWnfStateData` at `0x180099fa1`

## string_xrefs

- `0x18009a4fb`: `Cached`
- `0x18009a53c`: `Cached`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall BackgroundActivation::ActivateRawNotificationWorkItem(
        BackgroundActivation *this,
        struct INotificationHandler *a2,
        struct Notification *a3,
        struct TransientNotificationDetails *a4,
        struct _GUID *a5)
{
  BackgroundActivation *v8; // rdi
  char v9; // r12
  int v10; // r13d
  __int64 correlationVector; // rbx
  __int64 (__fastcall *v12)(struct INotificationHandler *, LPCWCH *); // rbx
  int v13; // eax
  const WCHAR *v14; // r10
  const WCHAR *v15; // r8
  __int64 v16; // rdx
  int v17; // eax
  __int64 (__fastcall *v18)(struct INotificationHandler *, struct Windows::Storage::Streams::IBuffer **); // rbx
  int v19; // eax
  unsigned int v20; // edi
  HANDLE ProcessHeap; // rax
  _DWORD *v22; // rbx
  const char *v23; // r9
  int v24; // eax
  size_t payloadSize; // r14
  unsigned __int8 *payloadBytes; // rax
  unsigned int v27; // eax
  int v28; // edx
  __int64 v29; // rdx
  int v30; // ebx
  __int64 v31; // r8
  void *v32; // rdi
  HANDLE v33; // rax
  unsigned int v34; // ebx
  unsigned __int8 *v35; // rax
  unsigned int v36; // eax
  int v37; // edx
  int CurrentProcessIntegrityLevel; // eax
  int UserSidAccount; // eax
  int v40; // eax
  _QWORD *v41; // rax
  __int64 v42; // rcx
  bool v43; // zf
  _QWORD *handlerKey; // rax
  __int64 v45; // rcx
  int v46; // esi
  wil *v47; // rcx
  int v48; // eax
  char *v49; // rdi
  int (__fastcall *v50)(char *, const unsigned __int16 *, const WCHAR **); // rbx
  HSTRING_HEADER *v51; // rax
  int v52; // eax
  struct WpnNotificationData *v53; // rdi
  int (__fastcall *v54)(char *, const unsigned __int16 *, const WCHAR **); // rbx
  HSTRING_HEADER *v55; // rax
  int v56; // eax
  struct WpnNotificationData *v57; // rdi
  int (__fastcall *v58)(char *, const unsigned __int16 *, const WCHAR **); // rbx
  HSTRING_HEADER *v59; // rax
  int v60; // eax
  struct WpnNotificationData *v61; // rdi
  int (__fastcall *v62)(char *, const unsigned __int16 *, const WCHAR **); // rbx
  HSTRING_HEADER *v63; // rax
  int v64; // eax
  struct WpnNotificationData *v65; // rdi
  int (__fastcall *v66)(char *, const unsigned __int16 *, const WCHAR **); // rbx
  HSTRING_HEADER *v67; // rax
  int v68; // eax
  struct WpnNotificationData *v69; // rdi
  int (__fastcall *v70)(char *, const unsigned __int16 *, const WCHAR **); // rbx
  HSTRING_HEADER *v71; // rax
  int v72; // eax
  const unsigned __int8 *v73; // rax
  const unsigned __int16 *v74; // rdx
  int v75; // eax
  __int64 v76; // rdx
  __int128 *v77; // r8
  int v78; // eax
  __int64 v79; // rax
  HSTRING_HEADER *v80; // rax
  int v81; // eax
  int v82; // eax
  int v83; // eax
  int v84; // eax
  int v85; // eax
  __int64 (__fastcall *v86)(struct INotificationHandler *, LPVOID *); // rbx
  int v87; // eax
  __int64 v88; // rbx
  int v89; // r14d
  __int64 v90; // r15
  LPVOID v91; // r8
  _QWORD *v92; // rax
  int v93; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-208h]
  int bIgnoreCasea; // [rsp+20h] [rbp-208h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-208h]
  bool v98; // [rsp+70h] [rbp-1B8h] BYREF
  char v99; // [rsp+71h] [rbp-1B7h] BYREF
  char v100[2]; // [rsp+72h] [rbp-1B6h] BYREF
  int v101; // [rsp+74h] [rbp-1B4h] BYREF
  struct Windows::Storage::Streams::IBuffer *v102; // [rsp+78h] [rbp-1B0h] BYREF
  unsigned int v103; // [rsp+80h] [rbp-1A8h] BYREF
  int v104; // [rsp+84h] [rbp-1A4h] BYREF
  struct WpnNotificationData *v105; // [rsp+88h] [rbp-1A0h] BYREF
  LPVOID lpMem; // [rsp+90h] [rbp-198h] BYREF
  enum _SID_NAME_USE v107; // [rsp+98h] [rbp-190h] BYREF
  LPVOID *p_lpMem; // [rsp+A0h] [rbp-188h] BYREF
  char v109; // [rsp+A8h] [rbp-180h]
  __int64 v110; // [rsp+B0h] [rbp-178h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+B8h] [rbp-170h] BYREF
  unsigned int v112; // [rsp+BCh] [rbp-16Ch] BYREF
  const WCHAR *v113; // [rsp+C0h] [rbp-168h] BYREF
  const WCHAR *v114; // [rsp+C8h] [rbp-160h] BYREF
  const WCHAR *v115; // [rsp+D0h] [rbp-158h] BYREF
  const WCHAR *v116; // [rsp+D8h] [rbp-150h] BYREF
  const WCHAR *v117; // [rsp+E0h] [rbp-148h] BYREF
  const WCHAR *v118; // [rsp+E8h] [rbp-140h] BYREF
  struct _GUID *v119; // [rsp+F0h] [rbp-138h]
  LPCWCH lpString1; // [rsp+F8h] [rbp-130h] BYREF
  __int64 v121; // [rsp+100h] [rbp-128h]
  __int64 v122; // [rsp+108h] [rbp-120h]
  __int64 v123; // [rsp+110h] [rbp-118h] BYREF
  BackgroundActivation *v124; // [rsp+118h] [rbp-110h]
  struct Notification *v125; // [rsp+120h] [rbp-108h] BYREF
  struct _GUID *v126; // [rsp+130h] [rbp-F8h] BYREF
  __int64 v127; // [rsp+140h] [rbp-E8h] BYREF
  __int128 v128; // [rsp+148h] [rbp-E0h] BYREF
  __int64 v129; // [rsp+158h] [rbp-D0h]
  __int128 v130; // [rsp+168h] [rbp-C0h] BYREF
  __int128 v131; // [rsp+178h] [rbp-B0h]
  HSTRING_HEADER v132; // [rsp+188h] [rbp-A0h] BYREF
  GUID v133; // [rsp+1A8h] [rbp-80h] BYREF
  int v134; // [rsp+1B8h] [rbp-70h] BYREF
  HSTRING_HEADER v135; // [rsp+1C0h] [rbp-68h] BYREF
  __int64 v136; // [rsp+1D8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  v8 = this;
  v124 = this;
  v125 = a3;
  v119 = a5;
  v126 = a5;
  v9 = 0;
  v107 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ebc66346838a30418ba30573d23d0a14_Traceguids);
  }
  v10 = 0;
  v104 = 0;
  v100[0] = 0;
  v99 = 0;
  v103 = 0;
  v127 = 0;
  v112 = 0;
  peUse = SidTypeUnknown;
  v98 = 0;
  std::string::string(&v130);
  try
  {
    v133 = GUID_NULL;
    v134 = 0;
    correlationVector = TransientNotificationDetails::get_correlationVector(a4, &v128);
    if ( &v130 != (__int128 *)correlationVector )
    {
      std::string::_Tidy_deallocate(&v130);
      v130 = *(_OWORD *)correlationVector;
      v131 = *(_OWORD *)(correlationVector + 16);
      *(_QWORD *)(correlationVector + 16) = 0;
      *(_QWORD *)(correlationVector + 24) = 15;
      *(_BYTE *)correlationVector = 0;
    }
    std::string::_Tidy_deallocate(&v128);
    lpString1 = 0;
    v121 = 0;
    v122 = 0;
    v12 = *(__int64 (__fastcall **)(struct INotificationHandler *, LPCWCH *))(*(_QWORD *)a2 + 48LL);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
    v121 = -1;
    v122 = -1;
    v13 = v12(a2, &lpString1);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
        (const char *)(unsigned int)v13,
        bIgnoreCase);
    v14 = &word_180124798;
    v15 = &word_180124798;
    if ( L"app:system" )
      v15 = L"app:system";
    v16 = v121;
    if ( v121 == -1 )
    {
      if ( lpString1 )
      {
        do
          ++v16;
        while ( lpString1[v16] );
      }
      else
      {
        LODWORD(v16) = 0;
      }
    }
    if ( lpString1 )
      v14 = lpString1;
    if ( CompareStringOrdinal(v14, v16, v15, -(L"app:system" != 0), 0) == 2 )
    {
      v100[0] = 1;
      v110 = 0;
      v17 = (*(__int64 (__fastcall **)(struct INotificationHandler *, __int64 *))(*(_QWORD *)a2 + 64LL))(a2, &v110);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x74,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
          (const char *)(unsigned int)v17,
          bIgnoreCasea);
      if ( v110 )
      {
        v99 = 1;
        v127 = v110;
        v102 = 0;
        v18 = *(__int64 (__fastcall **)(struct INotificationHandler *, struct Windows::Storage::Streams::IBuffer **))(*(_QWORD *)a2 + 32LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
        v19 = v18(a2, &v102);
        if ( v19 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x81,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
            (const char *)(unsigned int)v19,
            bIgnoreCasea);
        v101 = 0;
        v10 = (*(__int64 (__fastcall **)(struct Windows::Storage::Streams::IBuffer *, const wchar_t *, int *))(*(_QWORD *)v102 + 32LL))(
                v102,
                L"c:offlineHeaders",
                &v101);
        if ( v10 < 0 )
          v10 = 0;
        v104 = v10;
        if ( v101 )
        {
          v20 = Notification::get_payloadSize(a3) + 8;
          v103 = v20;
          ProcessHeap = GetProcessHeap();
          v22 = HeapAlloc(ProcessHeap, 0, v20);
          lpMem = v22;
          if ( !v22 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0x8F,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
              v23);
          p_lpMem = &lpMem;
          v109 = 1;
          *v22 = 1;
          v24 = (*(__int64 (__fastcall **)(char *, _DWORD *))(*((_QWORD *)a4 + 4) + 24LL))((char *)a4 + 32, v22 + 1);
          if ( v24 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x99,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
              (const char *)(unsigned int)v24,
              bIgnoreCasea);
          payloadSize = Notification::get_payloadSize(a3);
          payloadBytes = Notification::get_payloadBytes(a3);
          memcpy_0(v22 + 2, payloadBytes, payloadSize);
          bIgnoreCaseb = 0;
          v27 = RtlPublishWnfStateData(v127, 0, lpMem, v20);
          v30 = wil::details::NtStatusToHr((wil::details *)v27, v28);
          v32 = lpMem;
          if ( lpMem )
          {
            v33 = GetProcessHeap();
            HeapFree(v33, 0, v32);
          }
        }
        else
        {
          v34 = Notification::get_payloadSize(a3);
          v103 = v34;
          v35 = Notification::get_payloadBytes(a3);
          bIgnoreCaseb = 0;
          v36 = RtlPublishWnfStateData(v127, 0, v35, v34);
          v30 = wil::details::NtStatusToHr((wil::details *)v36, v37);
        }
        if ( v30 == -2147024891 )
        {
          CurrentProcessIntegrityLevel = WpnGetCurrentProcessIntegrityLevel(&v112, v29, v31);
          if ( CurrentProcessIntegrityLevel < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xB8,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
              (const char *)(unsigned int)CurrentProcessIntegrityLevel,
              0);
          UserSidAccount = WpnGetUserSidAccount(&peUse);
          if ( UserSidAccount < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xB9,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
              (const char *)(unsigned int)UserSidAccount,
              bIgnoreCaseb);
          v40 = IsAuthenticatedUser(&v98);
          if ( v40 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xBA,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
              (const char *)(unsigned int)v40,
              bIgnoreCaseb);
        }
        if ( v30 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xBD,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
            (const char *)(unsigned int)v30,
            bIgnoreCaseb);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57975764>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57975764>::GetImpl'::`2'::impl) )
        {
          if ( (byte_18015DE47 & 2) != 0 )
          {
            handlerKey = (_QWORD *)Notification::get_handlerKey(a3, &v128);
            v9 = 1;
            if ( handlerKey[3] > 7u )
              handlerKey = (_QWORD *)*handlerKey;
            McTemplateU0z_EventWriteTransfer(v45, WPNEND_BACKGROUND_TASK_ACTIVATED_SYSTEM_UPDATED, handlerKey);
          }
          v43 = (v9 & 1) == 0;
        }
        else
        {
          if ( (byte_18015DE45 & 1) != 0 )
          {
            v41 = (_QWORD *)Notification::get_handlerKey(a3, &v128);
            v9 = 2;
            if ( v41[3] > 7u )
              v41 = (_QWORD *)*v41;
            McTemplateU0z_EventWriteTransfer(v42, WPNEND_BACKGROUND_TASK_ACTIVATED_SYSTEM, v41);
          }
          v43 = (v9 & 2) == 0;
        }
        if ( !v43 )
          std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(&v128);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
      }
      v46 = (int)v119;
    }
    else
    {
      v128 = 0;
      v129 = 0;
      v48 = PropertySetHelper::Initialize((PropertySetHelper *)&v128);
      if ( v48 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xCC,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
          (const char *)(unsigned int)v48,
          bIgnoreCasea);
      v105 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105);
      Notification::get_data(a3, &v105);
      if ( v105 )
      {
        v118 = 0;
        v49 = (char *)v105 + 32;
        v50 = *(int (__fastcall **)(char *, const unsigned __int16 *, const WCHAR **))(*((_QWORD *)v105 + 4) + 32LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v118,
          0);
        if ( v50(v49, L"SecondaryChannelId", &v118) >= 0 )
        {
          p_lpMem = (LPVOID *)v118;
          v51 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v132, (const WCHAR **)&p_lpMem);
          v52 = PropertySetHelper::SetValue<HSTRING__ *>(
                  (__int64)&v128,
                  L"SecondaryChannelId",
                  (__int64)v51[1].Reserved.Reserved1);
          if ( v52 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xD7,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
              (const char *)(unsigned int)v52,
              bIgnoreCasea);
        }
        v117 = 0;
        v53 = v105;
        v54 = *(int (__fastcall **)(char *, const unsigned __int16 *, const WCHAR **))(*((_QWORD *)v105 + 4) + 32LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v117,
          0);
        if ( v54((char *)v53 + 32, L"Encryption", &v117) >= 0 )
        {
          p_lpMem = (LPVOID *)v117;
          v55 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v132, (const WCHAR **)&p_lpMem);
          v56 = PropertySetHelper::SetValue<HSTRING__ *>(
                  (__int64)&v128,
                  L"Encryption",
                  (__int64)v55[1].Reserved.Reserved1);
          if ( v56 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xDE,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
              (const char *)(unsigned int)v56,
              bIgnoreCasea);
        }
        v116 = 0;
        v57 = v105;
        v58 = *(int (__fastcall **)(char *, const unsigned __int16 *, const WCHAR **))(*((_QWORD *)v105 + 4) + 32LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v116,
          0);
        if ( v58((char *)v57 + 32, L"Crypto-Key", &v116) >= 0 )
        {
          p_lpMem = (LPVOID *)v116;
          v59 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v132, (const WCHAR **)&p_lpMem);
          v60 = PropertySetHelper::SetValue<HSTRING__ *>(
                  (__int64)&v128,
                  L"Crypto-Key",
                  (__int64)v59[1].Reserved.Reserved1);
          if ( v60 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xE4,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
              (const char *)(unsigned int)v60,
              bIgnoreCasea);
        }
        v115 = 0;
        v61 = v105;
        v62 = *(int (__fastcall **)(char *, const unsigned __int16 *, const WCHAR **))(*((_QWORD *)v105 + 4) + 32LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v115,
          0);
        if ( v62((char *)v61 + 32, L"Content-Encoding", &v115) >= 0 )
        {
          p_lpMem = (LPVOID *)v115;
          v63 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v132, (const WCHAR **)&p_lpMem);
          v64 = PropertySetHelper::SetValue<HSTRING__ *>(
                  (__int64)&v128,
                  L"Content-Encoding",
                  (__int64)v63[1].Reserved.Reserved1);
          if ( v64 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xEA,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
              (const char *)(unsigned int)v64,
              bIgnoreCasea);
        }
        v114 = 0;
        v65 = v105;
        v66 = *(int (__fastcall **)(char *, const unsigned __int16 *, const WCHAR **))(*((_QWORD *)v105 + 4) + 32LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v114,
          0);
        if ( v66((char *)v65 + 32, L"Priority", &v114) >= 0 )
        {
          p_lpMem = (LPVOID *)v114;
          v67 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v132, (const WCHAR **)&p_lpMem);
          v68 = PropertySetHelper::SetValue<HSTRING__ *>(
                  (__int64)&v128,
                  L"Priority",
                  (__int64)v67[1].Reserved.Reserved1);
          if ( v68 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xF0,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
              (const char *)(unsigned int)v68,
              bIgnoreCasea);
        }
        v113 = 0;
        v69 = v105;
        v70 = *(int (__fastcall **)(char *, const unsigned __int16 *, const WCHAR **))(*((_QWORD *)v105 + 4) + 32LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v113,
          0);
        if ( v70((char *)v69 + 32, L"Cached", &v113) >= 0 )
        {
          p_lpMem = (LPVOID *)v113;
          v71 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v132, (const WCHAR **)&p_lpMem);
          v72 = PropertySetHelper::SetValue<HSTRING__ *>((__int64)&v128, L"Cached", (__int64)v71[1].Reserved.Reserved1);
          if ( v72 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xF6,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
              (const char *)(unsigned int)v72,
              bIgnoreCasea);
        }
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v113);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v114);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v115);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v116);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v117);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v118);
        v8 = v124;
      }
      v103 = Notification::get_payloadSize(a3);
      v73 = Notification::get_payloadBytes(a3);
      v75 = PropertySetHelper::SetByteArrayValue((PropertySetHelper *)&v128, v74, v103, v73);
      if ( v75 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xFB,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
          (const char *)(unsigned int)v75,
          bIgnoreCasea);
      v77 = &v130;
      if ( *((_QWORD *)&v131 + 1) > 0xFu )
        v77 = (__int128 *)v130;
      v78 = PropertySetHelper::SetValue<char const *>((__int64)&v128, v76, (__int64)v77);
      if ( v78 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xFD,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
          (const char *)(unsigned int)v78,
          bIgnoreCasea);
      v79 = Notification::get_handlerKey(a3, &v132);
      if ( *(_QWORD *)(v79 + 24) > 7u )
        v79 = *(_QWORD *)v79;
      p_lpMem = (LPVOID *)v79;
      v80 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v135, (const WCHAR **)&p_lpMem);
      v81 = PropertySetHelper::SetValue<HSTRING__ *>(
              (__int64)&v128,
              L"AppUserModelId",
              (__int64)v80[1].Reserved.Reserved1);
      if ( v81 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xFE,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
          (const char *)(unsigned int)v81,
          bIgnoreCasea);
      v136 = 0;
      std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(&v132);
      v102 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
      v82 = PropertySetHelper::Serialize((PropertySetHelper *)&v128, &v102);
      if ( v82 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x101,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
          (const char *)(unsigned int)v82,
          bIgnoreCasea);
      v110 = 0;
      v83 = Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::As<Windows::Storage::Streams::IBufferByteAccess>(
              (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v102,
              (__int64)&v110);
      if ( v83 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x104,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
          (const char *)(unsigned int)v83,
          bIgnoreCasea);
      v101 = 0;
      v84 = (*(__int64 (__fastcall **)(struct Windows::Storage::Streams::IBuffer *, int *))(*(_QWORD *)v102 + 56LL))(
              v102,
              &v101);
      if ( v84 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x107,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
          (const char *)(unsigned int)v84,
          bIgnoreCasea);
      v123 = 0;
      v85 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v110 + 24LL))(v110, &v123);
      if ( v85 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x10C,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
          (const char *)(unsigned int)v85,
          bIgnoreCasea);
      lpMem = 0;
      v86 = *(__int64 (__fastcall **)(struct INotificationHandler *, LPVOID *))(*(_QWORD *)a2 + 40LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &lpMem,
        0);
      v87 = v86(a2, &lpMem);
      if ( v87 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x10F,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
          (const char *)(unsigned int)v87,
          bIgnoreCasea);
      v88 = *(_QWORD *)v8;
      Notification::get_id(a3);
      v89 = v101;
      v90 = v123;
      v91 = lpMem;
      if ( !lpMem || !*(_WORD *)lpMem )
      {
        v92 = (_QWORD *)Notification::get_handlerKey(a3, &v132);
        v9 = 4;
        v107 = SidTypeAlias;
        if ( v92[3] > 7u )
          v92 = (_QWORD *)*v92;
        v91 = v92;
      }
      v46 = (int)v119;
      v93 = (*(__int64 (__fastcall **)(BackgroundActivation *, _QWORD, LPVOID, __int64))(v88 + 8))(v124, 0, v91, v90);
      if ( v93 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x118,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
          (const char *)(unsigned int)v93,
          v89);
      if ( (v9 & 4) != 0 )
        std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(&v132);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpMem);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v110);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105);
      PropertySetHelper::~PropertySetHelper((PropertySetHelper *)&v128);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
  }
  catch ( ... )
  {
    v104 = wil::ResultFromCaughtException(v47);
    v10 = v104;
    v46 = (int)v126;
  }
  v107 = peUse;
  v126 = (struct _GUID *)&v127;
  WpncoreTelemetryLegacy::ActivateRawNotificationWorkItem<Notification * &,_GUID &,std::string &,long &,bool &,bool &,unsigned char *,unsigned long &,unsigned long &,unsigned long,bool &,_GUID &,long &>(
    (unsigned int)&v125,
    v46,
    (unsigned int)&v130,
    (unsigned int)&v104,
    (__int64)v100,
    (__int64)&v99,
    (__int64)&v126,
    (__int64)&v103,
    (__int64)&v112,
    (__int64)&v107,
    (__int64)&v98,
    (__int64)&v133,
    (__int64)&v134);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ebc66346838a30418ba30573d23d0a14_Traceguids);
  }
  std::string::_Tidy_deallocate(&v130);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180099b48  push    rbx
0x180099b4a  push    rsi
0x180099b4b  push    rdi
0x180099b4c  push    r12
0x180099b4e  push    r13
0x180099b50  push    r14
0x180099b52  push    r15
0x180099b54  sub     rsp, 1F0h
0x180099b5b  mov     rax, cs:__security_cookie
0x180099b62  xor     rax, rsp
0x180099b65  mov     [rsp+228h+var_48], rax
0x180099b6d  mov     r14, r9
0x180099b70  mov     rsi, r8
0x180099b73  mov     r15, rdx
0x180099b76  mov     rdi, rcx
0x180099b79  mov     [rsp+228h+var_110], rcx
0x180099b81  mov     [rsp+228h+var_108], r8
0x180099b89  mov     rax, [rsp+228h+arg_20]
0x180099b91  mov     [rsp+228h+var_138], rax
0x180099b99  mov     [rsp+228h+var_F8], rax
0x180099ba1  xor     ebx, ebx
0x180099ba3  mov     r12d, ebx
0x180099ba6  mov     [rsp+228h+var_190], ebx
0x180099bad  lea     rax, WPP_GLOBAL_Control
0x180099bb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180099bbb  cmp     rcx, rax
0x180099bbe  jz      short loc_180099BDF
0x180099bc0  test    byte ptr [rcx+1Ch], 40h
0x180099bc4  jz      short loc_180099BDF
0x180099bc6  cmp     byte ptr [rcx+19h], 6
0x180099bca  jb      short loc_180099BDF
0x180099bcc  lea     edx, [rbx+0Ah]
0x180099bcf  lea     r8, WPP_ebc66346838a30418ba30573d23d0a14_Traceguids
0x180099bd6  mov     rcx, [rcx+10h]
0x180099bda  call    WPP_SF_
0x180099bdf  mov     r13d, ebx
0x180099be2  mov     [rsp+228h+var_1A4], ebx
0x180099be9  mov     [rsp+228h+var_1B6], bl
0x180099bed  mov     [rsp+228h+var_1B7], bl
0x180099bf1  mov     [rsp+228h+var_1A8], ebx
0x180099bf8  mov     [rsp+228h+var_E8], rbx
0x180099c00  mov     [rsp+228h+var_16C], ebx
0x180099c07  mov     [rsp+228h+peUse], 8
0x180099c12  mov     [rsp+228h+var_1B8], bl
0x180099c16  lea     rcx, [rsp+228h+var_C0]
0x180099c1e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x180099c23  nop
0x180099c24  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x180099c2b  movdqu  [rsp+228h+var_80], xmm1
0x180099c34  mov     [rsp+228h+var_70], ebx
0x180099c3b  lea     rdx, [rsp+228h+var_E0]
0x180099c43  mov     rcx, r14
0x180099c46  call    ?get_correlationVector@TransientNotificationDetails@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; TransientNotificationDetails::get_correlationVector(void)
0x180099c4b  mov     rbx, rax
0x180099c4e  lea     rax, [rsp+228h+var_C0]
0x180099c56  cmp     rax, rbx
0x180099c59  jz      short loc_180099C8F
0x180099c5b  lea     rcx, [rsp+228h+var_C0]; void *
0x180099c63  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180099c68  movups  xmm0, xmmword ptr [rbx]
0x180099c6b  movups  [rsp+228h+var_C0], xmm0
0x180099c73  movups  xmm1, xmmword ptr [rbx+10h]
0x180099c77  movups  [rsp+228h+var_B0], xmm1
0x180099c7f  xor     edx, edx
0x180099c81  mov     [rbx+10h], rdx
0x180099c85  mov     qword ptr [rbx+18h], 0Fh
0x180099c8d  mov     [rbx], dl
0x180099c8f  lea     rcx, [rsp+228h+var_E0]; void *
0x180099c97  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180099c9c  xor     eax, eax
0x180099c9e  mov     [rsp+228h+lpString1], rax
0x180099ca6  mov     [rsp+228h+var_128], rax
0x180099cae  mov     [rsp+228h+var_120], rax
0x180099cb6  mov     rax, [r15]
0x180099cb9  mov     rbx, [rax+30h]
0x180099cbd  lea     rcx, [rsp+228h+lpString1]
0x180099cc5  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180099cca  or      rax, 0FFFFFFFFFFFFFFFFh
0x180099cce  mov     [rsp+228h+var_128], rax
0x180099cd6  mov     [rsp+228h+var_120], rax
0x180099cde  lea     rdx, [rsp+228h+lpString1]
0x180099ce6  mov     rcx, r15
0x180099ce9  mov     rax, rbx
0x180099cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099cf1  mov     rcx, [rsp+228h]; this
0x180099cf9  xor     r11d, r11d
0x180099cfc  test    eax, eax
0x180099cfe  jns     short loc_180099D13
0x180099d00  mov     r9d, eax; char *
0x180099d03  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180099d0a  lea     edx, [r11+6Ch]; void *
0x180099d0e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180099d13  mov     rcx, cs:off_18011DEB0; "app:system"
0x180099d1a  mov     rax, rcx
0x180099d1d  neg     rax
0x180099d20  sbb     r9d, r9d; cchCount2
0x180099d23  lea     r10, word_180124798
0x180099d2a  mov     r8, r10
0x180099d2d  test    rcx, rcx
0x180099d30  cmovnz  r8, rcx; lpString2
0x180099d34  mov     rdx, [rsp+228h+var_128]
0x180099d3c  mov     rax, [rsp+228h+lpString1]
0x180099d44  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180099d48  jnz     short loc_180099D61
0x180099d4a  test    rax, rax
0x180099d4d  jz      short loc_180099D5E
0x180099d4f  or      rdx, rdx
0x180099d52  inc     rdx
0x180099d55  cmp     [rax+rdx*2], r11w
0x180099d5a  jnz     short loc_180099D52
0x180099d5c  jmp     short loc_180099D61
0x180099d5e  mov     rdx, r11; cchCount1
0x180099d61  test    rax, rax
0x180099d64  cmovnz  r10, rax
0x180099d68  mov     [rsp+228h+bIgnoreCase], r11d; int
0x180099d6d  mov     rcx, r10; lpString1
0x180099d70  call    cs:__imp_CompareStringOrdinal
0x180099d76  cmp     eax, 2
0x180099d79  jnz     loc_18009A11F
0x180099d7f  mov     [rsp+228h+var_1B6], 1
0x180099d84  xor     edi, edi
0x180099d86  mov     [rsp+228h+var_178], rdi
0x180099d8e  mov     rax, [r15]
0x180099d91  lea     rdx, [rsp+228h+var_178]
0x180099d99  mov     rcx, r15
0x180099d9c  mov     rax, [rax+40h]
0x180099da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099da5  mov     rcx, [rsp+228h]; this
0x180099dad  test    eax, eax
0x180099daf  jns     short loc_180099DC3
0x180099db1  mov     r9d, eax; char *
0x180099db4  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180099dbb  lea     edx, [rdi+74h]; void *
0x180099dbe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180099dc3  mov     rax, [rsp+228h+var_178]
0x180099dcb  test    rax, rax
0x180099dce  jz      loc_18009A104
0x180099dd4  mov     [rsp+228h+var_1B7], 1
0x180099dd9  mov     [rsp+228h+var_E8], rax
0x180099de1  mov     [rsp+228h+var_1B0], rdi
0x180099de6  mov     rax, [r15]
0x180099de9  mov     rbx, [rax+20h]
0x180099ded  lea     rcx, [rsp+228h+var_1B0]
0x180099df2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180099df7  lea     rdx, [rsp+228h+var_1B0]
0x180099dfc  mov     rcx, r15
0x180099dff  mov     rax, rbx
0x180099e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099e07  mov     rcx, [rsp+228h]; this
0x180099e0f  test    eax, eax
0x180099e11  jns     short loc_180099E27
0x180099e13  mov     r9d, eax; char *
0x180099e16  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180099e1d  mov     edx, 81h; void *
0x180099e22  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180099e27  mov     [rsp+228h+var_1B4], edi
0x180099e2b  mov     rcx, [rsp+228h+var_1B0]
0x180099e30  mov     rax, [rcx]
0x180099e33  lea     r8, [rsp+228h+var_1B4]
0x180099e38  mov     rdx, cs:off_18011DEF8; "c:offlineHeaders"
0x180099e3f  mov     rax, [rax+20h]
0x180099e43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099e48  mov     r13d, eax
0x180099e4b  test    eax, eax
0x180099e4d  cmovs   r13d, edi
0x180099e51  mov     [rsp+228h+var_1A4], r13d
0x180099e59  mov     rcx, rsi; this
0x180099e5c  cmp     [rsp+228h+var_1B4], edi
0x180099e60  jz      loc_180099F75
0x180099e66  call    ?get_payloadSize@Notification@@QEAA_KXZ; Notification::get_payloadSize(void)
0x180099e6b  lea     edi, [rax+8]
0x180099e6e  mov     [rsp+228h+var_1A8], edi
0x180099e75  call    cs:__imp_GetProcessHeap
0x180099e7b  mov     r8d, edi; dwBytes
0x180099e7e  xor     edx, edx; dwFlags
0x180099e80  mov     rcx, rax; hHeap
0x180099e83  call    cs:__imp_HeapAlloc
0x180099e89  mov     rbx, rax
0x180099e8c  mov     [rsp+228h+lpMem], rax
0x180099e94  mov     rcx, [rsp+228h]; this
0x180099e9c  xor     r15d, r15d
0x180099e9f  test    rax, rax
0x180099ea2  jnz     short loc_180099EB5
0x180099ea4  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180099eab  mov     edx, 8Fh; void *
0x180099eb0  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180099eb5  lea     rax, [rsp+228h+lpMem]
0x180099ebd  mov     [rsp+228h+var_188], rax
0x180099ec5  mov     [rsp+228h+var_180], 1
0x180099ecd  mov     dword ptr [rbx], 1
0x180099ed3  lea     rcx, [r14+20h]
0x180099ed7  mov     rax, [rcx]
0x180099eda  lea     rdx, [rbx+4]
0x180099ede  mov     rax, [rax+18h]
0x180099ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099ee7  mov     rcx, [rsp+228h]; this
0x180099eef  test    eax, eax
0x180099ef1  jns     short loc_180099F07
0x180099ef3  mov     r9d, eax; char *
0x180099ef6  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180099efd  mov     edx, 99h; void *
0x180099f02  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180099f07  mov     rcx, rsi; this
0x180099f0a  call    ?get_payloadSize@Notification@@QEAA_KXZ; Notification::get_payloadSize(void)
0x180099f0f  mov     r14, rax
0x180099f12  mov     rcx, rsi; this
0x180099f15  call    ?get_payloadBytes@Notification@@QEAAPEAEXZ; Notification::get_payloadBytes(void)
0x180099f1a  lea     rcx, [rbx+8]; void *
0x180099f1e  mov     r8, r14; Size
0x180099f21  mov     rdx, rax; Src
0x180099f24  call    memcpy_0
0x180099f29  mov     qword ptr [rsp+228h+bIgnoreCase], r15
0x180099f2e  mov     r9d, edi
0x180099f31  mov     r8, [rsp+228h+lpMem]
0x180099f39  xor     edx, edx
0x180099f3b  mov     rcx, [rsp+228h+var_E8]
0x180099f43  call    cs:__imp_RtlPublishWnfStateData
0x180099f49  mov     ecx, eax; this
0x180099f4b  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180099f50  mov     ebx, eax
0x180099f52  mov     rdi, [rsp+228h+lpMem]
0x180099f5a  test    rdi, rdi
0x180099f5d  jz      short loc_180099FB0
0x180099f5f  call    cs:__imp_GetProcessHeap
0x180099f65  mov     r8, rdi; lpMem
0x180099f68  xor     edx, edx; dwFlags
0x180099f6a  mov     rcx, rax; hHeap
0x180099f6d  call    cs:__imp_HeapFree
0x180099f73  jmp     short loc_180099FB0
0x180099f75  call    ?get_payloadSize@Notification@@QEAA_KXZ; Notification::get_payloadSize(void)
0x180099f7a  mov     rbx, rax
0x180099f7d  mov     [rsp+228h+var_1A8], ebx
0x180099f84  mov     rcx, rsi; this
0x180099f87  call    ?get_payloadBytes@Notification@@QEAAPEAEXZ; Notification::get_payloadBytes(void)
0x180099f8c  mov     qword ptr [rsp+228h+bIgnoreCase], rdi; int
0x180099f91  mov     r9d, ebx
0x180099f94  mov     r8, rax
0x180099f97  xor     edx, edx
0x180099f99  mov     rcx, [rsp+228h+var_E8]
0x180099fa1  call    cs:__imp_RtlPublishWnfStateData
0x180099fa7  mov     ecx, eax; this
0x180099fa9  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180099fae  mov     ebx, eax
0x180099fb0  cmp     ebx, 80070005h
0x180099fb6  jnz     loc_18009A040
0x180099fbc  lea     rcx, [rsp+228h+var_16C]; unsigned int *
0x180099fc4  call    ?WpnGetCurrentProcessIntegrityLevel@@YAJPEAK@Z; WpnGetCurrentProcessIntegrityLevel(ulong *)
0x180099fc9  mov     rcx, [rsp+228h]; this
0x180099fd1  test    eax, eax
0x180099fd3  jns     short loc_180099FE9
0x180099fd5  mov     r9d, eax; char *
0x180099fd8  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180099fdf  mov     edx, 0B8h; void *
0x180099fe4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180099fe9  lea     rcx, [rsp+228h+peUse]; peUse
0x180099ff1  call    ?WpnGetUserSidAccount@@YAJPEAW4_SID_NAME_USE@@@Z; WpnGetUserSidAccount(_SID_NAME_USE *)
0x180099ff6  mov     rcx, [rsp+228h]; this
0x180099ffe  test    eax, eax
0x18009a000  jns     short loc_18009A016
0x18009a002  mov     r9d, eax; char *
0x18009a005  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18009a00c  mov     edx, 0B9h; void *
0x18009a011  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009a016  lea     rcx, [rsp+228h+var_1B8]; bool *
0x18009a01b  call    ?IsAuthenticatedUser@@YAJPEA_N@Z; IsAuthenticatedUser(bool *)
0x18009a020  mov     rcx, [rsp+228h]; this
0x18009a028  test    eax, eax
0x18009a02a  jns     short loc_18009A040
0x18009a02c  mov     r9d, eax; char *
0x18009a02f  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18009a036  mov     edx, 0BAh; void *
0x18009a03b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009a040  mov     rcx, [rsp+228h]; this
0x18009a048  test    ebx, ebx
0x18009a04a  jns     short loc_18009A060
0x18009a04c  mov     r9d, ebx; char *
0x18009a04f  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18009a056  mov     edx, 0BDh; void *
0x18009a05b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009a060  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57975764@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57975764@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57975764> `wil::Feature<__WilFeatureTraits_Feature_57975764>::GetImpl(void)'::`2'::impl
0x18009a067  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57975764@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57975764>::__private_IsEnabled(void)
0x18009a06c  test    al, al
0x18009a06e  jnz     short loc_18009A0AE
0x18009a070  test    cs:byte_18015DE45, 1
0x18009a077  jz      short loc_18009A0A8
0x18009a079  lea     rdx, [rsp+228h+var_E0]
0x18009a081  mov     rcx, rsi
0x18009a084  call    ?get_handlerKey@Notification@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Notification::get_handlerKey(void)
0x18009a089  mov     r12d, 2
0x18009a08f  cmp     qword ptr [rax+18h], 7
0x18009a094  jbe     short loc_18009A099
0x18009a096  mov     rax, [rax]
0x18009a099  mov     r8, rax
0x18009a09c  lea     rdx, WPNEND_BACKGROUND_TASK_ACTIVATED_SYSTEM
0x18009a0a3  call    McTemplateU0z_EventWriteTransfer
0x18009a0a8  test    r12b, 2
0x18009a0ac  jmp     short loc_18009A0EA
0x18009a0ae  test    cs:byte_18015DE47, 2
0x18009a0b5  jz      short loc_18009A0E6
0x18009a0b7  lea     rdx, [rsp+228h+var_E0]
  ... truncated ...
```
