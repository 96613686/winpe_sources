# CMDMPushConfiguration::GetChannelObjectHelper(Windows::Networking::PushNotifications::IPushNotificationChannel * *,__int64)

- ea: `0x140024bc4`
- end: `0x140025a16`
- name: `?GetChannelObjectHelper@CMDMPushConfiguration@@AEAAJPEAPEAUIPushNotificationChannel@PushNotifications@Networking@Windows@@_J@Z`
- size: `3666`
- prototype: `__int64 __fastcall(CMDMPushConfiguration *__hidden this, struct Windows::Networking::PushNotifications::IPushNotificationChannel **, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400249a4`

## callees

- `0x1400042f0`
- `0x140004e28`
- `0x140009140`
- `0x1400095b4`
- `0x14001e2cc`
- `0x14001e458`
- `0x14001eb6c`
- `0x14002448c`
- `0x14002478c`
- `0x140024bc4`
- `0x140028d38`
- `0x140029248`
- `0x14002a688`
- `0x14002a87c`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1400250e3`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1400250e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400250f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400250f5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140024d43`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140024fb2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140024d43`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140024fb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140024d2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140024fcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400251dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140024d2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140024fcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400251dd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140024d7c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14002521e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140024d7c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14002521e`
- `OLEAUT32!__imp_SysFreeString` at `0x140024ed9`
- `OLEAUT32!__imp_SysFreeString` at `0x140025052`
- `OLEAUT32!__imp_SysFreeString` at `0x1400252dd`
- `OLEAUT32!__imp_SysFreeString` at `0x140025462`
- `OLEAUT32!__imp_SysFreeString` at `0x140025647`
- `OLEAUT32!__imp_SysFreeString` at `0x1400257e7`
- `OLEAUT32!__imp_SysFreeString` at `0x140025923`
- `OLEAUT32!__imp_SysFreeString` at `0x140024ed9`
- `OLEAUT32!__imp_SysFreeString` at `0x140025052`
- `OLEAUT32!__imp_SysFreeString` at `0x1400252dd`
- `OLEAUT32!__imp_SysFreeString` at `0x140025462`
- `OLEAUT32!__imp_SysFreeString` at `0x140025647`
- `OLEAUT32!__imp_SysFreeString` at `0x1400257e7`
- `OLEAUT32!__imp_SysFreeString` at `0x140025923`

## string_xrefs

- `0x1400251d6`: `Windows.System.Threading.ThreadPoolTimer`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall CMDMPushConfiguration::GetChannelObjectHelper(
        CMDMPushConfiguration *this,
        struct Windows::Networking::PushNotifications::IPushNotificationChannel **a2)
{
  HRESULT v3; // eax
  int ActivationFactory; // eax
  unsigned int v5; // ebx
  __int64 v6; // rcx
  int (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rcx
  int AppId; // eax
  __int64 v9; // rcx
  int (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING, _QWORD); // rsi
  int (__fastcall ***v13)(_QWORD, GUID *, __int64 *); // rcx
  WCHAR *v14; // r14
  unsigned __int64 v15; // rbx
  int v16; // eax
  __int64 v17; // rcx
  int (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // rcx
  const char *v19; // r9
  __int64 result; // rax
  void *v21; // rdx
  HANDLE Event; // rbx
  unsigned int v23; // r8d
  const char *v24; // r9
  volatile signed __int32 *v25; // rdi
  void **v26; // r15
  char *v27; // rax
  __int64 v28; // rbx
  __int64 v29; // rcx
  volatile signed __int32 *Reserved1; // rsi
  HRESULT StringReference; // eax
  int v32; // edx
  unsigned int v33; // r8d
  __int64 v34; // rsi
  __int64 v35; // rcx
  int v36; // eax
  unsigned int v37; // esi
  HSTRING v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  struct Windows::Networking::PushNotifications::IPushNotificationChannel *v41; // rcx
  int (__fastcall ***v42)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v43; // rsi
  __int64 (__fastcall *v44)(__int64, __int64, __int64, HSTRING *); // r12
  HSTRING v45; // rcx
  int v46; // eax
  HRESULT v47; // edx
  unsigned int v48; // esi
  HSTRING v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  struct Windows::Networking::PushNotifications::IPushNotificationChannel *v52; // rcx
  int (__fastcall ***v53)(_QWORD, GUID *, __int64 *); // rcx
  HSTRING v54; // rsi
  void *v55; // r15
  int (__fastcall ***v56)(_QWORD, GUID *, __int64 *); // r12
  struct Windows::Networking::PushNotifications::IPushNotificationChannel *v57; // rcx
  int v58; // r15d
  struct Windows::Networking::PushNotifications::IPushNotificationChannel *v59; // rax
  HSTRING v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rcx
  struct Windows::Networking::PushNotifications::IPushNotificationChannel *v63; // rcx
  int (__fastcall ***v64)(_QWORD, GUID *, __int64 *); // rcx
  HSTRING v65; // rcx
  __int64 v66; // rcx
  __int64 v67; // rcx
  struct Windows::Networking::PushNotifications::IPushNotificationChannel *v68; // rcx
  int (__fastcall ***v69)(_QWORD, GUID *, __int64 *); // rcx
  HSTRING v70; // rcx
  __int64 v71; // rcx
  __int64 v72; // rcx
  struct Windows::Networking::PushNotifications::IPushNotificationChannel *v73; // rcx
  int (__fastcall ***v74)(_QWORD, GUID *, __int64 *); // rcx
  int v75; // [rsp+20h] [rbp-218h]
  struct Windows::Networking::PushNotifications::IPushNotificationChannel *v76; // [rsp+30h] [rbp-208h] BYREF
  HSTRING v77; // [rsp+38h] [rbp-200h] BYREF
  __int64 v78; // [rsp+40h] [rbp-1F8h] BYREF
  __int64 v79; // [rsp+48h] [rbp-1F0h] BYREF
  int (__fastcall ***v80)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-1E8h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-1E0h] BYREF
  __int64 v82; // [rsp+60h] [rbp-1D8h] BYREF
  __int128 v83; // [rsp+68h] [rbp-1D0h] BYREF
  __int64 v84; // [rsp+78h] [rbp-1C0h]
  struct Windows::Networking::PushNotifications::IPushNotificationChannel **v85; // [rsp+80h] [rbp-1B8h]
  char v86; // [rsp+88h] [rbp-1B0h] BYREF
  HSTRING string; // [rsp+90h] [rbp-1A8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-1A0h] BYREF
  void **v89; // [rsp+B0h] [rbp-188h] BYREF
  int v90; // [rsp+B8h] [rbp-180h] BYREF
  char v91; // [rsp+BCh] [rbp-17Ch]
  int v92; // [rsp+E0h] [rbp-158h] BYREF
  const char *v93; // [rsp+E8h] [rbp-150h]
  __int64 v94; // [rsp+F0h] [rbp-148h]
  char v95; // [rsp+F8h] [rbp-140h]
  int v96; // [rsp+100h] [rbp-138h]
  _BYTE v97[168]; // [rsp+108h] [rbp-130h] BYREF
  int v98; // [rsp+1B0h] [rbp-88h]
  __int64 v99; // [rsp+1B8h] [rbp-80h]
  int *v100; // [rsp+1C0h] [rbp-78h]
  __int64 v101; // [rsp+1C8h] [rbp-70h]
  __int64 v102; // [rsp+1D0h] [rbp-68h]
  void ***v103; // [rsp+1D8h] [rbp-60h]
  __int64 v104; // [rsp+1E0h] [rbp-58h]
  int v105; // [rsp+1E8h] [rbp-50h]
  int *v106; // [rsp+1F0h] [rbp-48h]
  char v107; // [rsp+1F8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  v85 = a2;
  v90 = 0;
  v91 = 0;
  v95 = 0;
  v92 = 0;
  v93 = "GetChannelObjectHelperActivity";
  v94 = 0;
  v96 = 0;
  *(_OWORD *)&v97[152] = 0;
  memset_0(v97, 0, 0x98u);
  v98 = 1;
  v99 = 0;
  v100 = &v90;
  v101 = 0;
  v102 = 0;
  v103 = &v89;
  v104 = 0;
  v105 = 0;
  v106 = &v92;
  v107 = 0;
  v89 = &MDMPushProvider::GetChannelObjectHelperActivity::`vftable';
  MDMPushProvider::GetChannelObjectHelperActivity::StartActivity((MDMPushProvider::GetChannelObjectHelperActivity *)&v89);
  v80 = 0;
  v76 = 0;
  v79 = 0;
  bstrString = 0;
  v78 = 0;
  v77 = 0;
  v83 = 0;
  v84 = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Networking.PushNotifications.PushNotificationChannelManager",
         0x43u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  try
  {
    ActivationFactory = RoGetActivationFactory(string, &GUID_8baf9b65_77a1_4588_bd19_861529a9dcf0, &v79);
    v5 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C7,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v75);
      v6 = v79;
      if ( v79 )
      {
        v79 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      }
      v7 = v80;
      if ( v80 )
      {
        v80 = 0;
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v7)[2])(v7);
      }
LABEL_30:
      v89 = &MDMPushProvider::GetChannelObjectHelperActivity::`vftable';
      wil::ActivityBase<MDMPushProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v89);
      wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v89);
      return v5;
    }
    bstrString = 0;
    AppId = CMDMPushConfiguration::GetAppId(this, &bstrString);
    v5 = AppId;
    if ( AppId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C9,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
        (const char *)(unsigned int)AppId,
        v75);
      if ( bstrString )
        SysFreeString(bstrString);
      v9 = v79;
      if ( v79 )
      {
        v79 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      v10 = v80;
      if ( v80 )
      {
        v80 = 0;
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v10)[2])(v10);
      }
      goto LABEL_30;
    }
    v11 = v79;
    v12 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v79 + 56LL);
    v13 = v80;
    if ( v80 )
    {
      v80 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v13)[2])(v13);
    }
    v14 = bstrString;
    v15 = -1;
    do
      ++v15;
    while ( bstrString[v15] );
    if ( v15 > 0xFFFFFFFF )
    {
      LODWORD(v15) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(v14, v15, &hstringHeader, &string);
    v16 = v12(v11, string, &v80);
    v5 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CD,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
        (const char *)(unsigned int)v16,
        v75);
      if ( v14 )
        SysFreeString(v14);
      v17 = v79;
      if ( v79 )
      {
        v79 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      v18 = v80;
      if ( v80 )
      {
        v80 = 0;
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v18)[2])(v18);
      }
      goto LABEL_30;
    }
    Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
    if ( !Event )
      wil::details::in1diag3::Throw_GetLastError(retaddr, v21, v23, v24);
    GetLastError();
    _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
      &v83,
      Event);
    v25 = (volatile signed __int32 *)*((_QWORD *)&v83 + 1);
    if ( *((_QWORD *)&v83 + 1) )
      _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v83 + 1) + 8LL), 1u);
    v26 = (void **)v83;
    string = (HSTRING)v83;
    hstringHeader.Reserved.Reserved1 = (PVOID)v25;
    v27 = (char *)Microsoft::WRL::Callback_Windows::System::Threading::ITimerElapsedHandler__lambda_5c2cd178e30082c76c93240c01ceecaf___(
                    &v82,
                    &string);
    v28 = 0;
    if ( &v86 != v27 )
    {
      v28 = *(_QWORD *)v27;
      *(_QWORD *)v27 = 0;
    }
    v84 = v28;
    v29 = v82;
    if ( v82 )
    {
      v82 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    Reserved1 = (volatile signed __int32 *)hstringHeader.Reserved.Reserved1;
    if ( hstringHeader.Reserved.Reserved1 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)hstringHeader.Reserved.Reserved1 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))Reserved1)(Reserved1);
        if ( _InterlockedExchangeAdd(Reserved1 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)Reserved1 + 8LL))(Reserved1);
      }
    }
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
    StringReference = WindowsCreateStringReference(
                        L"Windows.System.Threading.ThreadPoolTimer",
                        0x28u,
                        (HSTRING_HEADER *)&string,
                        (HSTRING *)&hstringHeader.Reserved.Reserved2[16]);
    if ( StringReference < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v32, v33);
      __debugbreak();
    }
    v34 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[16];
    v35 = v78;
    if ( v78 )
    {
      v78 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    v36 = RoGetActivationFactory(v34, &GUID_1a8a9d02_e482_461b_b8c7_8efad1cce590, &v78);
    v37 = v36;
    if ( v36 >= 0 )
    {
      v43 = v78;
      v44 = *(__int64 (__fastcall **)(__int64, __int64, __int64, HSTRING *))(*(_QWORD *)v78 + 56LL);
      v45 = v77;
      if ( v77 )
      {
        v77 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v45 + 16LL))(v45);
      }
      v46 = v44(v43, v28, 400000000, &v77);
      v48 = v46;
      if ( v46 >= 0 )
      {
        v54 = v77;
        if ( v77 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v77 + 8LL))(v77);
        string = v54;
        hstringHeader.Reserved.Reserved2[0] = 1;
        if ( v26 )
          v55 = *v26;
        else
          v55 = 0;
        v56 = v80;
        v57 = v76;
        if ( v76 )
        {
          v76 = 0;
          (*(void (__fastcall **)(struct Windows::Networking::PushNotifications::IPushNotificationChannel *))(*(_QWORD *)v57 + 16LL))(v57);
        }
        v58 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>(
                v56,
                v47,
                v55);
        if ( v58 < 0
          || (v58 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), struct Windows::Networking::PushNotifications::IPushNotificationChannel **))(*v56)[8])(
                      v56,
                      &v76),
              v58 < 0) )
        {
          if ( v58 == -2147418110 || (unsigned int)(v58 + 2147023674) <= 1 || v58 == -2147023436 || v58 == -2013002776 )
          {
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v54 + 64LL))(v54);
            if ( v54 )
              (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v54 + 16LL))(v54);
            if ( v28 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
            if ( v25 )
            {
              if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
                if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
              }
            }
            v70 = v77;
            if ( v77 )
            {
              v77 = 0;
              (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v70 + 16LL))(v70);
            }
            v71 = v78;
            if ( v78 )
            {
              v78 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
            }
            if ( v14 )
              SysFreeString(v14);
            v72 = v79;
            if ( v79 )
            {
              v79 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
            }
            v73 = v76;
            if ( v76 )
            {
              v76 = 0;
              (*(void (__fastcall **)(struct Windows::Networking::PushNotifications::IPushNotificationChannel *))(*(_QWORD *)v73 + 16LL))(v73);
            }
            v74 = v80;
            if ( v80 )
            {
              v80 = 0;
              ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v74)[2])(v74);
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1EB,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
              (const char *)(unsigned int)v58,
              v75);
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v54 + 64LL))(v54);
            if ( v54 )
              (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v54 + 16LL))(v54);
            if ( v28 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
            if ( v25 )
            {
              if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
                if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
              }
            }
            v65 = v77;
            if ( v77 )
            {
              v77 = 0;
              (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v65 + 16LL))(v65);
            }
            v66 = v78;
            if ( v78 )
            {
              v78 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
            }
            if ( v14 )
              SysFreeString(v14);
            v67 = v79;
            if ( v79 )
            {
              v79 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
            }
            v68 = v76;
            if ( v76 )
            {
              v76 = 0;
              (*(void (__fastcall **)(struct Windows::Networking::PushNotifications::IPushNotificationChannel *))(*(_QWORD *)v68 + 16LL))(v68);
            }
            v69 = v80;
            if ( v80 )
            {
              v80 = 0;
              ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v69)[2])(v69);
            }
          }
          v89 = &MDMPushProvider::GetChannelObjectHelperActivity::`vftable';
          wil::ActivityBase<MDMPushProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v89);
          wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v89);
          result = (unsigned int)v58;
        }
        else
        {
          v59 = v76;
          v76 = 0;
          *v85 = v59;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v54 + 64LL))(v54);
          if ( v54 )
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v54 + 16LL))(v54);
          if ( v28 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          if ( v25 )
          {
            if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
              if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
            }
          }
          v60 = v77;
          if ( v77 )
          {
            v77 = 0;
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v60 + 16LL))(v60);
          }
          v61 = v78;
          if ( v78 )
          {
            v78 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
          }
          if ( v14 )
            SysFreeString(v14);
          v62 = v79;
          if ( v79 )
          {
            v79 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
          }
          v63 = v76;
          if ( v76 )
          {
            v76 = 0;
            (*(void (__fastcall **)(struct Windows::Networking::PushNotifications::IPushNotificationChannel *))(*(_QWORD *)v63 + 16LL))(v63);
          }
          v64 = v80;
          if ( v80 )
          {
            v80 = 0;
            ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v64)[2])(v64);
          }
          wil::ActivityBase<MDMPushProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v89);
          v89 = &MDMPushProvider::GetChannelObjectHelperActivity::`vftable';
          wil::ActivityBase<MDMPushProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v89);
          wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v89);
          result = 0;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1DD,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
          (const char *)(unsigned int)v46,
          v75);
        if ( v28 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        if ( v25 )
        {
          if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
            if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
          }
        }
        v49 = v77;
        if ( v77 )
        {
          v77 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v49 + 16LL))(v49);
        }
        v50 = v78;
        if ( v78 )
        {
          v78 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
        }
        if ( v14 )
          SysFreeString(v14);
        v51 = v79;
        if ( v79 )
        {
          v79 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        }
        v52 = v76;
        if ( v76 )
        {
          v76 = 0;
          (*(void (__fastcall **)(struct Windows::Networking::PushNotifications::IPushNotificationChannel *))(*(_QWORD *)v52 + 16LL))(v52);
        }
        v53 = v80;
        if ( v80 )
        {
          v80 = 0;
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v53)[2])(v53);
        }
        v89 = &MDMPushProvider::GetChannelObjectHelperActivity::`vftable';
        wil::ActivityBase<MDMPushProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v89);
        wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v89);
        result = v48;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D9,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
        (const char *)(unsigned int)v36,
        v75);
      if ( v28 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      if ( v25 )
      {
        if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
          if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
        }
      }
      v38 = v77;
      if ( v77 )
      {
        v77 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v38 + 16LL))(v38);
      }
      v39 = v78;
      if ( v78 )
      {
        v78 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      }
      if ( v14 )
        SysFreeString(v14);
      v40 = v79;
      if ( v79 )
      {
        v79 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      }
      v41 = v76;
      if ( v76 )
      {
        v76 = 0;
        (*(void (__fastcall **)(struct Windows::Networking::PushNotifications::IPushNotificationChannel *))(*(_QWORD *)v41 + 16LL))(v41);
      }
      v42 = v80;
      if ( v80 )
      {
        v80 = 0;
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v42)[2])(v42);
      }
      v89 = &MDMPushProvider::GetChannelObjectHelperActivity::`vftable';
      wil::ActivityBase<MDMPushProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v89);
      wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v89);
      result = v37;
    }
  }
  catch ( ... )
  {
    LODWORD(v76) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x1F0,
                     (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
                     v19);
    v89 = &MDMPushProvider::GetChannelObjectHelperActivity::`vftable';
    wil::ActivityBase<MDMPushProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v89);
    wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v89);
    return (unsigned int)v76;
  }
  return result;
}

```

## disassembly

```asm
0x140024bc4  mov     r11, rsp
0x140024bc7  mov     [r11+18h], rbx
0x140024bcb  mov     [r11+20h], rsi
0x140024bcf  push    rdi
0x140024bd0  push    r12
0x140024bd2  push    r13
0x140024bd4  push    r14
0x140024bd6  push    r15
0x140024bd8  sub     rsp, 210h
0x140024bdf  mov     rax, cs:__security_cookie
0x140024be6  xor     rax, rsp
0x140024be9  mov     [rsp+238h+var_38], rax
0x140024bf1  mov     [rsp+238h+var_1B8], rdx
0x140024bf9  mov     rdi, rcx
0x140024bfc  xor     r12d, r12d
0x140024bff  mov     [r11-180h], r12d
0x140024c06  mov     [r11-17Ch], r12b
0x140024c0d  mov     [r11-140h], r12b
0x140024c14  mov     [r11-158h], r12d
0x140024c1b  lea     rax, aGetchannelobje_0; "GetChannelObjectHelperActivity"
0x140024c22  mov     [r11-150h], rax
0x140024c29  mov     [r11-148h], r12
0x140024c30  mov     [r11-138h], r12d
0x140024c37  xorps   xmm0, xmm0
0x140024c3a  movdqa  [rsp+238h+var_98], xmm0
0x140024c43  xor     edx, edx; Val
0x140024c45  mov     r8d, 98h; Size
0x140024c4b  lea     rcx, [r11-130h]; void *
0x140024c52  call    memset_0
0x140024c57  lea     r15d, [r12+1]
0x140024c5c  mov     [rsp+238h+var_88], r15d
0x140024c64  xor     eax, eax
0x140024c66  mov     [rsp+238h+var_80], rax
0x140024c6e  lea     rax, [rsp+238h+var_180]
0x140024c76  mov     [rsp+238h+var_78], rax
0x140024c7e  mov     [rsp+238h+var_70], r12
0x140024c86  mov     [rsp+238h+var_68], r12
0x140024c8e  lea     rax, [rsp+238h+var_188]
0x140024c96  mov     [rsp+238h+var_60], rax
0x140024c9e  mov     [rsp+238h+var_58], r12
0x140024ca6  mov     [rsp+238h+var_50], r12d
0x140024cae  lea     rax, [rsp+238h+var_158]
0x140024cb6  mov     [rsp+238h+var_48], rax
0x140024cbe  mov     [rsp+238h+var_40], r12b
0x140024cc6  lea     r13, ??_7GetChannelObjectHelperActivity@MDMPushProvider@@6B@; const MDMPushProvider::GetChannelObjectHelperActivity::`vftable'
0x140024ccd  mov     [rsp+238h+var_188], r13
0x140024cd5  lea     rcx, [rsp+238h+var_188]; this
0x140024cdd  call    ?StartActivity@GetChannelObjectHelperActivity@MDMPushProvider@@QEAAXXZ; MDMPushProvider::GetChannelObjectHelperActivity::StartActivity(void)
0x140024ce2  nop
0x140024ce3  mov     [rsp+238h+var_1E8], r12
0x140024ce8  mov     [rsp+238h+var_208], r12
0x140024ced  mov     [rsp+238h+var_1F0], r12
0x140024cf2  mov     [rsp+238h+bstrString], r12
0x140024cf7  mov     [rsp+238h+var_1F8], r12
0x140024cfc  mov     [rsp+238h+var_200], r12
0x140024d01  xorps   xmm1, xmm1
0x140024d04  movdqu  [rsp+238h+var_1D0], xmm1
0x140024d0a  mov     [rsp+238h+var_1C0], r12
0x140024d0f  lea     r9, [rsp+238h+string]; string
0x140024d17  lea     r8, [rsp+238h+hstringHeader]; hstringHeader
0x140024d1f  lea     edx, [r12+43h]; length
0x140024d24  lea     rcx, ?RuntimeClass_Windows_Networking_PushNotifications_PushNotificationChannelManager@@3QBGB; "Windows.Networking.PushNotifications.Pu"...
0x140024d2b  call    cs:__imp_WindowsCreateStringReference
0x140024d31  test    eax, eax
0x140024d33  jns     short loc_140024D49
0x140024d35  xor     r9d, r9d; lpArguments
0x140024d38  xor     r8d, r8d; nNumberOfArguments
0x140024d3b  mov     edx, r15d; dwExceptionFlags
0x140024d3e  mov     ecx, 0C000000Dh; dwExceptionCode
0x140024d43  call    cs:__imp_RaiseException
0x140024d49  mov     rbx, [rsp+238h+string]
0x140024d51  mov     rcx, [rsp+238h+var_1F0]
0x140024d56  test    rcx, rcx
0x140024d59  jz      short loc_140024D6D
0x140024d5b  mov     [rsp+238h+var_1F0], r12
0x140024d60  mov     rax, [rcx]
0x140024d63  mov     rax, [rax+10h]
0x140024d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024d6c  nop
0x140024d6d  lea     r8, [rsp+238h+var_1F0]
0x140024d72  lea     rdx, _GUID_8baf9b65_77a1_4588_bd19_861529a9dcf0
0x140024d79  mov     rcx, rbx
0x140024d7c  call    cs:__imp_RoGetActivationFactory
0x140024d82  mov     ebx, eax
0x140024d84  test    eax, eax
0x140024d86  jns     loc_140024E5E
0x140024d8c  mov     rcx, [rsp+238h]; this
0x140024d94  mov     r9d, eax; char *
0x140024d97  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x140024d9e  mov     edx, 1C7h; void *
0x140024da3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140024da8  nop
0x140024da9  mov     rcx, [rsp+238h+var_200]
0x140024dae  test    rcx, rcx
0x140024db1  jz      short loc_140024DC5
0x140024db3  mov     [rsp+238h+var_200], r12
0x140024db8  mov     rax, [rcx]
0x140024dbb  mov     rax, [rax+10h]
0x140024dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024dc4  nop
0x140024dc5  mov     rcx, [rsp+238h+var_1F8]
0x140024dca  test    rcx, rcx
0x140024dcd  jz      short loc_140024DE1
0x140024dcf  mov     [rsp+238h+var_1F8], r12
0x140024dd4  mov     rax, [rcx]
0x140024dd7  mov     rax, [rax+10h]
0x140024ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024de0  nop
0x140024de1  mov     rcx, [rsp+238h+var_1F0]
0x140024de6  test    rcx, rcx
0x140024de9  jz      short loc_140024DFD
0x140024deb  mov     [rsp+238h+var_1F0], r12
0x140024df0  mov     rax, [rcx]
0x140024df3  mov     rax, [rax+10h]
0x140024df7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024dfc  nop
0x140024dfd  mov     rcx, [rsp+238h+var_208]
0x140024e02  test    rcx, rcx
0x140024e05  jz      short loc_140024E19
0x140024e07  mov     [rsp+238h+var_208], r12
0x140024e0c  mov     rax, [rcx]
0x140024e0f  mov     rax, [rax+10h]
0x140024e13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024e18  nop
0x140024e19  mov     rcx, [rsp+238h+var_1E8]
0x140024e1e  test    rcx, rcx
0x140024e21  jz      short loc_140024E35
0x140024e23  mov     [rsp+238h+var_1E8], r12
0x140024e28  mov     rax, [rcx]
0x140024e2b  mov     rax, [rax+10h]
0x140024e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024e34  nop
0x140024e35  mov     [rsp+238h+var_188], r13
0x140024e3d  lea     rcx, [rsp+238h+var_188]
0x140024e45  call    ?Destroy@?$ActivityBase@VMDMPushProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MDMPushProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140024e4a  lea     rcx, [rsp+238h+var_188]
0x140024e52  call    ??1?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x140024e57  mov     eax, ebx
0x140024e59  jmp     loc_1400259D2
0x140024e5e  mov     [rsp+238h+bstrString], r12
0x140024e63  lea     rdx, [rsp+238h+bstrString]; unsigned __int16 **
0x140024e68  mov     rcx, rdi; this
0x140024e6b  call    ?GetAppId@CMDMPushConfiguration@@QEAAJPEAPEAG@Z; CMDMPushConfiguration::GetAppId(ushort * *)
0x140024e70  mov     ebx, eax
0x140024e72  test    eax, eax
0x140024e74  jns     loc_140024F5D
0x140024e7a  mov     rcx, [rsp+238h]; this
0x140024e82  mov     r9d, eax; char *
0x140024e85  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x140024e8c  mov     edx, 1C9h; void *
0x140024e91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140024e96  nop
0x140024e97  mov     rcx, [rsp+238h+var_200]
0x140024e9c  test    rcx, rcx
0x140024e9f  jz      short loc_140024EB3
0x140024ea1  mov     [rsp+238h+var_200], r12
0x140024ea6  mov     rax, [rcx]
0x140024ea9  mov     rax, [rax+10h]
0x140024ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024eb2  nop
0x140024eb3  mov     rcx, [rsp+238h+var_1F8]
0x140024eb8  test    rcx, rcx
0x140024ebb  jz      short loc_140024ECF
0x140024ebd  mov     [rsp+238h+var_1F8], r12
0x140024ec2  mov     rax, [rcx]
0x140024ec5  mov     rax, [rax+10h]
0x140024ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024ece  nop
0x140024ecf  mov     rcx, [rsp+238h+bstrString]; bstrString
0x140024ed4  test    rcx, rcx
0x140024ed7  jz      short loc_140024EE0
0x140024ed9  call    cs:__imp_SysFreeString
0x140024edf  nop
0x140024ee0  mov     rcx, [rsp+238h+var_1F0]
0x140024ee5  test    rcx, rcx
0x140024ee8  jz      short loc_140024EFC
0x140024eea  mov     [rsp+238h+var_1F0], r12
0x140024eef  mov     rax, [rcx]
0x140024ef2  mov     rax, [rax+10h]
0x140024ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024efb  nop
0x140024efc  mov     rcx, [rsp+238h+var_208]
0x140024f01  test    rcx, rcx
0x140024f04  jz      short loc_140024F18
0x140024f06  mov     [rsp+238h+var_208], r12
0x140024f0b  mov     rax, [rcx]
0x140024f0e  mov     rax, [rax+10h]
0x140024f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024f17  nop
0x140024f18  mov     rcx, [rsp+238h+var_1E8]
0x140024f1d  test    rcx, rcx
0x140024f20  jz      short loc_140024F34
0x140024f22  mov     [rsp+238h+var_1E8], r12
0x140024f27  mov     rax, [rcx]
0x140024f2a  mov     rax, [rax+10h]
0x140024f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024f33  nop
0x140024f34  mov     [rsp+238h+var_188], r13
0x140024f3c  lea     rcx, [rsp+238h+var_188]
0x140024f44  call    ?Destroy@?$ActivityBase@VMDMPushProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MDMPushProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140024f49  lea     rcx, [rsp+238h+var_188]
0x140024f51  call    ??1?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x140024f56  mov     eax, ebx
0x140024f58  jmp     loc_1400259D2
0x140024f5d  mov     rdi, [rsp+238h+var_1F0]
0x140024f62  mov     rax, [rdi]
0x140024f65  mov     rsi, [rax+38h]
0x140024f69  mov     rcx, [rsp+238h+var_1E8]
0x140024f6e  test    rcx, rcx
0x140024f71  jz      short loc_140024F85
0x140024f73  mov     [rsp+238h+var_1E8], r12
0x140024f78  mov     rax, [rcx]
0x140024f7b  mov     rax, [rax+10h]
0x140024f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024f84  nop
0x140024f85  mov     r14, [rsp+238h+bstrString]
0x140024f8a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140024f8e  inc     rbx
0x140024f91  cmp     [r14+rbx*2], r12w
0x140024f96  jnz     short loc_140024F8E
0x140024f98  mov     eax, 0FFFFFFFFh
0x140024f9d  cmp     rbx, rax
0x140024fa0  jbe     short loc_140024FB8
0x140024fa2  mov     ebx, eax
0x140024fa4  xor     r9d, r9d; lpArguments
0x140024fa7  xor     r8d, r8d; nNumberOfArguments
0x140024faa  mov     edx, r15d; dwExceptionFlags
0x140024fad  mov     ecx, 0C000000Dh; dwExceptionCode
0x140024fb2  call    cs:__imp_RaiseException
0x140024fb8  lea     r9, [rsp+238h+string]; string
0x140024fc0  lea     r8, [rsp+238h+hstringHeader]; hstringHeader
0x140024fc8  mov     edx, ebx; length
0x140024fca  mov     rcx, r14; sourceString
0x140024fcd  call    cs:__imp_WindowsCreateStringReference
0x140024fd3  lea     r8, [rsp+238h+var_1E8]
0x140024fd8  mov     rdx, [rsp+238h+string]
0x140024fe0  mov     rcx, rdi
0x140024fe3  mov     rax, rsi
0x140024fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024feb  mov     ebx, eax
0x140024fed  test    eax, eax
0x140024fef  jns     loc_1400250D6
0x140024ff5  mov     rcx, [rsp+238h]; this
0x140024ffd  mov     r9d, eax; char *
0x140025000  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x140025007  mov     edx, 1CDh; void *
0x14002500c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025011  nop
0x140025012  mov     rcx, [rsp+238h+var_200]
0x140025017  test    rcx, rcx
0x14002501a  jz      short loc_14002502E
0x14002501c  mov     [rsp+238h+var_200], r12
0x140025021  mov     rax, [rcx]
0x140025024  mov     rax, [rax+10h]
0x140025028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002502d  nop
0x14002502e  mov     rcx, [rsp+238h+var_1F8]
0x140025033  test    rcx, rcx
0x140025036  jz      short loc_14002504A
0x140025038  mov     [rsp+238h+var_1F8], r12
0x14002503d  mov     rax, [rcx]
0x140025040  mov     rax, [rax+10h]
0x140025044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025049  nop
0x14002504a  test    r14, r14
0x14002504d  jz      short loc_140025059
0x14002504f  mov     rcx, r14; bstrString
0x140025052  call    cs:__imp_SysFreeString
0x140025058  nop
0x140025059  mov     rcx, [rsp+238h+var_1F0]
0x14002505e  test    rcx, rcx
0x140025061  jz      short loc_140025075
0x140025063  mov     [rsp+238h+var_1F0], r12
0x140025068  mov     rax, [rcx]
0x14002506b  mov     rax, [rax+10h]
0x14002506f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025074  nop
0x140025075  mov     rcx, [rsp+238h+var_208]
0x14002507a  test    rcx, rcx
0x14002507d  jz      short loc_140025091
0x14002507f  mov     [rsp+238h+var_208], r12
0x140025084  mov     rax, [rcx]
0x140025087  mov     rax, [rax+10h]
0x14002508b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025090  nop
0x140025091  mov     rcx, [rsp+238h+var_1E8]
0x140025096  test    rcx, rcx
0x140025099  jz      short loc_1400250AD
0x14002509b  mov     [rsp+238h+var_1E8], r12
0x1400250a0  mov     rax, [rcx]
0x1400250a3  mov     rax, [rax+10h]
0x1400250a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400250ac  nop
0x1400250ad  mov     [rsp+238h+var_188], r13
0x1400250b5  lea     rcx, [rsp+238h+var_188]
0x1400250bd  call    ?Destroy@?$ActivityBase@VMDMPushProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MDMPushProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1400250c2  lea     rcx, [rsp+238h+var_188]
0x1400250ca  call    ??1?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1400250cf  mov     eax, ebx
0x1400250d1  jmp     loc_1400259D2
  ... truncated ...
```
