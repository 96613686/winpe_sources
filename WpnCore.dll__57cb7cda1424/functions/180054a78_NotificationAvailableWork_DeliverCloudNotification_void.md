# NotificationAvailableWork::DeliverCloudNotification(void)

- ea: `0x180054a78`
- end: `0x180056419`
- name: `?DeliverCloudNotification@NotificationAvailableWork@@AEAAJXZ`
- size: `6561`
- prototype: `__int64 __fastcall(NotificationAvailableWork *__hidden this)`
- caller_count: `1`
- callee_count: `43`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180054894`

## callees

- `0x180004e38`
- `0x18000a784`
- `0x1800117c0`
- `0x180024890`
- `0x1800293c0`
- `0x18002ee38`
- `0x18004af34`
- `0x18004b4c4`
- `0x18004ee24`
- `0x180054160`
- `0x1800542a8`
- `0x1800542ec`
- `0x180054314`
- `0x180054388`
- `0x1800543ac`
- `0x1800544b4`
- `0x180054a78`
- `0x1800575b8`
- `0x180057ad0`
- `0x180057c5c`
- `0x180058bb4`
- `0x18006cdfc`
- `0x18006df78`
- `0x18007bb74`
- `0x18007d358`
- `0x18007ed94`
- `0x180094bec`
- `0x180094e20`
- `0x180095274`
- `0x18009574c`
- `0x180099b48`
- `0x18009ad38`
- `0x1800a5b54`
- `0x1800af0a4`
- `0x1800b1e68`
- `0x1800b99f0`
- `0x1800dfb00`
- `0x1800e14d4`
- `0x1800e15ec`
- `0x1800e1754`
- `0x1800e18b0`
- `0x1800e1918`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005561a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005561a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800563ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800563bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800563e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800563ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800563bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800563e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=50
__int64 __fastcall NotificationAvailableWork::DeliverCloudNotification(NotificationAvailableWork *this)
{
  int v2; // r14d
  char v3; // r13
  Notification **notification; // rax
  char id; // di
  __int64 *channelId; // rax
  __int64 v7; // rbx
  _QWORD *v8; // rax
  _QWORD *type; // rax
  int v10; // edx
  int v11; // r8d
  int v12; // eax
  int v13; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  struct INotificationHandler **notificationHandler; // rax
  NotificationAvailableWork *v18; // rcx
  int ParentId; // eax
  __int64 v20; // rax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, LPVOID *); // rbx
  __int64 v23; // r8
  PVOID *v24; // rcx
  __int64 v25; // rax
  __int64 (__fastcall *v26)(__int64, LPVOID, _QWORD, _QWORD); // rsi
  Notification **v27; // rax
  Notification **v28; // rax
  unsigned int v29; // ebx
  _QWORD *v30; // rax
  unsigned __int8 *v31; // rax
  unsigned int v32; // eax
  __int64 v33; // rax
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, WpnDatabaseHelpers **); // rbx
  enum WPN_SETTING_TYPE *v36; // r8
  CtaManager **v37; // rsi
  _QWORD *v38; // rax
  __int64 v39; // rax
  const unsigned __int16 *v40; // rdi
  WpnDatabaseHelpers *PackageFullName; // rbx
  struct INotificationHandler **v42; // rax
  int v43; // eax
  unsigned int v44; // edi
  int v45; // eax
  _QWORD *v46; // rax
  _QWORD *v47; // rax
  __int64 v48; // rdx
  char v49; // bl
  _QWORD *v50; // rax
  __int64 v51; // rax
  const unsigned __int16 *v52; // rbx
  struct INotificationHandler **v53; // rax
  unsigned int v54; // edi
  _QWORD *v55; // rax
  _QWORD *handlerKey; // rax
  int v57; // eax
  __int64 v58; // rax
  __int64 v59; // rdi
  __int64 (__fastcall *v60)(__int64, unsigned __int16 **); // rbx
  PVOID *v61; // rcx
  RunningApps *v62; // rdi
  struct TransientNotificationDetails *v63; // rbx
  struct Notification **v64; // rax
  _QWORD *v65; // rax
  int v66; // r14d
  _QWORD *v67; // rax
  __int64 v68; // rdx
  __int64 v69; // rdi
  int v70; // ebx
  ResumeNotificationHandler *v71; // r13
  __int64 v72; // rax
  const unsigned __int16 *v73; // rsi
  const unsigned __int16 *v74; // rdi
  struct TransientNotificationDetails *v75; // rbx
  struct Notification **v76; // rax
  _QWORD *v77; // rax
  _QWORD *v78; // rax
  __int64 v79; // rdx
  char v80; // bl
  BackgroundActivation *v81; // rsi
  TransientNotificationDetails **notificationTransientDetails; // rax
  struct _GUID v83; // xmm6
  struct TransientNotificationDetails *v84; // rdi
  struct Notification *v85; // rbx
  struct INotificationHandler **v86; // rax
  PVOID *v87; // rcx
  _QWORD *v88; // rax
  __int64 v89; // r8
  BlockedRawChannels *v90; // rsi
  __int64 v91; // rax
  const unsigned __int16 *v92; // rdi
  _QWORD *v93; // rax
  __int64 v94; // rax
  PVOID *v95; // r10
  __int64 (__fastcall ***v96)(_QWORD, _QWORD, __int64, __int64); // r13
  __int64 (__fastcall *v97)(_QWORD, _QWORD, __int64, __int64); // rsi
  __int64 v98; // rdi
  __int64 v99; // rbx
  _QWORD *v100; // rax
  __int64 *v101; // rax
  __int64 v102; // rdi
  int v103; // r14d
  _QWORD *v104; // rax
  int v105; // r14d
  __int64 *v106; // rax
  __int64 v107; // rsi
  int v108; // r14d
  Notification **v109; // rax
  char v110; // r13
  _QWORD *v111; // rax
  int v112; // r14d
  __int64 *v113; // rax
  __int64 v114; // r12
  _QWORD *v115; // rax
  int v116; // edx
  int v117; // ecx
  _BYTE *v118; // rcx
  TransientNotificationDetails **v119; // rax
  __int64 *NotificationPolicyReasonString; // rax
  __int64 v121; // rdi
  int v122; // r14d
  _QWORD *v123; // rax
  int v124; // r14d
  __int64 *v125; // rax
  __int64 v126; // rsi
  int v127; // r14d
  Notification **v128; // rax
  char v129; // r13
  _QWORD *v130; // rax
  int v131; // r14d
  __int64 *v132; // rax
  __int64 v133; // r12
  int v134; // r14d
  _QWORD *v135; // rax
  int v136; // edx
  _QWORD *v137; // rax
  int v138; // r14d
  __int64 *v139; // rax
  __int64 v140; // rdi
  int v141; // r14d
  Notification **v142; // rax
  char v143; // r12
  _QWORD *v144; // rax
  int v145; // r14d
  __int64 *v146; // rax
  __int64 v147; // rsi
  int v148; // r14d
  _QWORD *v149; // rax
  int v150; // edx
  int v151; // ecx
  WpnDatabaseHelpers *v152; // rcx
  int v154; // [rsp+20h] [rbp-E0h]
  int v155; // [rsp+20h] [rbp-E0h]
  int v156; // [rsp+20h] [rbp-E0h]
  int v157; // [rsp+20h] [rbp-E0h]
  int v158; // [rsp+20h] [rbp-E0h]
  int v159; // [rsp+20h] [rbp-E0h]
  __int64 v160; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v161; // [rsp+58h] [rbp-A8h] BYREF
  char v162; // [rsp+60h] [rbp-A0h]
  int v163; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v164[8]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v165; // [rsp+78h] [rbp-88h] BYREF
  int v166; // [rsp+7Ch] [rbp-84h] BYREF
  LPVOID v167; // [rsp+80h] [rbp-80h] BYREF
  WpnDatabaseHelpers *v168; // [rsp+88h] [rbp-78h] BYREF
  int v169; // [rsp+90h] [rbp-70h] BYREF
  LPVOID pv; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v171; // [rsp+A0h] [rbp-60h] BYREF
  int v172; // [rsp+A8h] [rbp-58h] BYREF
  struct _GUID v173; // [rsp+B0h] [rbp-50h] BYREF
  struct _GUID v174; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v175[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v176[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v177[32]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v2 = 0;
  v163 = 0;
  v166 = 0;
  v167 = 0;
  v168 = 0;
  v172 = 0;
  v171 = 0;
  pv = 0;
  v162 = 0;
  v165 = 0;
  v169 = 0;
  v3 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    notification = (Notification **)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), &v161);
    v163 = 1;
    id = Notification::get_id(*notification);
    channelId = (__int64 *)NotificationDeliveryTransaction::get_channelId(*((_QWORD *)this + 22), &v174);
    v7 = (__int64)channelId;
    if ( (unsigned __int64)channelId[3] > 7 )
      v7 = *channelId;
    v8 = (_QWORD *)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), v164);
    v163 = 7;
    type = (_QWORD *)Notification::get_type(*v8, &v173);
    v2 = 15;
    if ( type[3] > 7u )
      type = (_QWORD *)*type;
    WPP_SF_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, (_DWORD)type, v7, id);
  }
  if ( (v2 & 8) != 0 )
  {
    v2 &= ~8u;
    std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(&v173);
  }
  if ( (v2 & 4) != 0 )
  {
    v2 &= ~4u;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v164);
  }
  if ( (v2 & 2) != 0 )
  {
    v2 &= ~2u;
    std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(&v174);
  }
  if ( (v2 & 1) != 0 )
  {
    v2 &= ~1u;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v161);
  }
  v12 = NotificationAvailableWork::ProcessChannel(this);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x363,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
      (const char *)(unsigned int)v12,
      v154);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v15 = 119;
LABEL_21:
      v16 = (unsigned int)v13;
LABEL_22:
      WPP_SF_d(v14[2], v15, &WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids, v16);
      goto LABEL_232;
    }
    goto LABEL_232;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  notificationHandler = (struct INotificationHandler **)NotificationDeliveryTransaction::get_notificationHandler(
                                                          *((_QWORD *)this + 22),
                                                          &v161);
  ParentId = NotificationAvailableWork::GetParentId(v18, *notificationHandler, (unsigned __int16 **)&pv);
  if ( ParentId < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x369,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
      (const char *)(unsigned int)ParentId,
      v154);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v161);
  v20 = NotificationDeliveryTransaction::get_notificationHandler(*((_QWORD *)this + 22), &v161);
  v21 = *(_QWORD *)v20;
  v22 = *(__int64 (__fastcall **)(__int64, LPVOID *))(**(_QWORD **)v20 + 24LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v167,
    0);
  v13 = v22(v21, &v167);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v161);
  if ( v13 >= 0 )
  {
    v24 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, v23, v167);
      v24 = (PVOID *)WPP_GLOBAL_Control;
    }
    v25 = *(_QWORD *)(*((_QWORD *)this + 23) + 120LL);
    v161 = v25;
    if ( !v25 )
    {
      if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 0x40) != 0 && *((_BYTE *)v24 + 25) >= 2u )
        WPP_SF_d(v24[2], 122, &WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids, 2151547141LL);
      v13 = -2143420155;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x373,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
        (const char *)0x803E0105LL,
        v154);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_232;
      v15 = 123;
      goto LABEL_41;
    }
    v26 = *(__int64 (__fastcall **)(__int64, LPVOID, _QWORD, _QWORD))(*(_QWORD *)v25 + 64LL);
    v27 = (Notification **)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), &v160);
    Notification::get_payloadSize(*v27);
    v28 = (Notification **)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), &v163);
    v29 = Notification::get_id(*v28);
    v30 = (_QWORD *)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), v164);
    v31 = (unsigned __int8 *)Notification::get_type(*v30, &v173);
    v32 = WpnDatabaseHelpers::NotificationTypeFromName(v31);
    v155 = v29;
    v13 = v26(v161, v167, 0, v32);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v164);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v163);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v160);
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          124,
          &WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids,
          (unsigned int)v13);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x37E,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
        (const char *)(unsigned int)v13,
        v155);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v15 = 125;
        goto LABEL_21;
      }
      goto LABEL_232;
    }
    v33 = NotificationDeliveryTransaction::get_notificationHandler(*((_QWORD *)this + 22), &v160);
    v34 = *(_QWORD *)v33;
    v35 = *(__int64 (__fastcall **)(__int64, WpnDatabaseHelpers **))(**(_QWORD **)v33 + 32LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v168);
    v13 = v35(v34, &v168);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v160);
    if ( v13 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x382,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
        (const char *)(unsigned int)v13,
        v155);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v15 = 126;
        goto LABEL_21;
      }
      goto LABEL_232;
    }
    WpnDatabaseHelpers::GetSettingMaskFromObject(v168, (struct INotificationHandlerSettings *)&v169, v36);
    v37 = (CtaManager **)*((_QWORD *)this + 23);
    v38 = (_QWORD *)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), &v161);
    v39 = Notification::get_type(*v38, &v173);
    v40 = (const unsigned __int16 *)v39;
    if ( *(_QWORD *)(v39 + 24) > 7u )
      v40 = *(const unsigned __int16 **)v39;
    PackageFullName = (WpnDatabaseHelpers *)NotificationDeliveryTransaction::get_PackageFullName(*((NotificationDeliveryTransaction **)this
                                                                                                 + 22));
    v42 = (struct INotificationHandler **)NotificationDeliveryTransaction::get_notificationHandler(
                                            *((_QWORD *)this + 22),
                                            &v160);
    v13 = NotificationPlatform::CheckNotificationHandlerSettingsEnabled(
            v37,
            *v42,
            PackageFullName,
            v40,
            1,
            (enum NOTIFICATION_POLICY_REASON *)&v165,
            (enum PolicyLevel *)&v166);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v160);
    std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(&v173);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v161);
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          128,
          &WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids,
          (unsigned int)v13);
      }
      NotificationAvailableWork::LogSettingsDropped(this, (unsigned int)v13, v167, (unsigned int)v166);
      if ( v13 == -2143420140 )
      {
        v43 = NotificationAvailableWork::BlockNotificationType(this);
        v44 = v43;
        if ( v43 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              129,
              &WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids,
              (unsigned int)v43);
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x399,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
            (const char *)v44,
            v156);
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
            goto LABEL_232;
          v15 = 130;
          goto LABEL_70;
        }
LABEL_79:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x3A2,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
          (const char *)(unsigned int)v13,
          v156);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v15 = 133;
          goto LABEL_21;
        }
        goto LABEL_232;
      }
      v45 = NotificationAvailableWork::BlockChannel(this, v165);
      v44 = v45;
      if ( v45 >= 0 )
        goto LABEL_79;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          131,
          &WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids,
          (unsigned int)v45);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x39F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
        (const char *)v44,
        v156);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_232;
      v15 = 132;
LABEL_70:
      v16 = v44;
      goto LABEL_22;
    }
    v46 = (_QWORD *)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), &v160);
    v47 = (_QWORD *)Notification::get_type(*v46, &v173);
    v48 = v47[2];
    if ( v47[3] > 7u )
      v47 = (_QWORD *)*v47;
    v49 = std::_Traits_equal<std::char_traits<unsigned short>>(v47, v48, L"toast", 5);
    std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(&v173);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v160);
    if ( v49 )
    {
      v50 = (_QWORD *)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), v164);
      v51 = Notification::get_type(*v50, &v174);
      v52 = (const unsigned __int16 *)v51;
      if ( *(_QWORD *)(v51 + 24) > 7u )
        v52 = *(const unsigned __int16 **)v51;
      v53 = (struct INotificationHandler **)NotificationDeliveryTransaction::get_notificationHandler(
                                              *((_QWORD *)this + 22),
                                              &v161);
      v13 = NotificationAvailableWork::CheckNotificationHandlerSettingsEnabledForParent(
              this,
              *v53,
              v52,
              1,
              (enum PolicyLevel *)&v166,
              (enum NOTIFICATION_POLICY_REASON *)&v165);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v161);
      std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(&v174);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v164);
      if ( v13 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            134,
            &WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids,
            (unsigned int)v13);
        }
        v54 = v166;
        v55 = (_QWORD *)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), &v160);
        handlerKey = (_QWORD *)Notification::get_handlerKey(*v55, &v173);
        if ( handlerKey[3] > 7u )
          handlerKey = (_QWORD *)*handlerKey;
        NotificationAvailableWork::LogSettingsDropped(this, (unsigned int)v13, handlerKey, v54);
        std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(&v173);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v160);
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x3B3,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
          (const char *)(unsigned int)v13,
          v156);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v15 = 135;
          goto LABEL_21;
        }
        goto LABEL_232;
      }
    }
    v57 = (*(__int64 (__fastcall **)(WpnDatabaseHelpers *, const wchar_t *, int *))(*(_QWORD *)v168 + 32LL))(
            v168,
            L"c:voip",
            &v172);
    v13 = v57;
    if ( v57 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3B8,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
        (const char *)(unsigned int)v57,
        v156);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v15 = 136;
        goto LABEL_21;
      }
      goto LABEL_232;
    }
    v58 = NotificationDeliveryTransaction::get_notificationHandler(*((_QWORD *)this + 22), &v160);
    v59 = *(_QWORD *)v58;
    v60 = *(__int64 (__fastcall **)(__int64, unsigned __int16 **))(**(_QWORD **)v58 + 48LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v171,
      0);
    v13 = v60(v59, &v171);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v160);
    if ( v13 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3BB,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
        (const char *)(unsigned int)v13,
        v156);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v15 = 137;
        goto LABEL_21;
      }
      goto LABEL_232;
    }
    v61 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, &WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids);
      v61 = (PVOID *)WPP_GLOBAL_Control;
    }
    v62 = *(RunningApps **)(*((_QWORD *)this + 23) + 200LL);
    if ( !v62 )
    {
      if ( v61 != &WPP_GLOBAL_Control && (*((_BYTE *)v61 + 28) & 0x40) != 0 && *((_BYTE *)v61 + 25) >= 2u )
        WPP_SF_d(v61[2], 139, &WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids, 2151547141LL);
      v13 = -2143420155;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3C1,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
        (const char *)0x803E0105LL,
        v156);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_232;
      v15 = 140;
      goto LABEL_41;
    }
    v63 = *(struct TransientNotificationDetails **)NotificationDeliveryTransaction::get_notificationTransientDetails(
                                                     *((_QWORD *)this + 22),
                                                     &v161);
    v64 = (struct Notification **)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), &v160);
    v13 = RunningApps::CallAppSink(v62, v171, (const unsigned __int16 *)pv, *v64, v63);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v160);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v161);
    if ( v13 >= 0 )
    {
      if ( !v13 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 162, &WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids);
        }
        v162 = 1;
        goto LABEL_232;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        141,
        &WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids,
        (unsigned int)v13);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID54436891>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID54436891>::GetImpl'::`2'::impl) )
      goto LABEL_158;
    v65 = (_QWORD *)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), v164);
    v66 = v2 | 0x10;
    v163 = v66;
    v67 = (_QWORD *)Notification::get_type(*v65, &v173);
    v2 = v66 | 0x20;
    v68 = v67[2];
    if ( v67[3] > 7u )
      v67 = (_QWORD *)*v67;
    if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v67, v68, L"raw", 3)
      || (v2 |= 0x40u,
          v69 = *(_QWORD *)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), &v161),
          AcquireSRWLockShared((PSRWLOCK)(v69 + 352)),
          v160 = v69 + 352,
          v70 = *(_DWORD *)(v69 + 316),
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v160),
          v70) )
    {
      v3 = 0;
    }
    if ( (v2 & 0x40) != 0 )
    {
      v2 &= ~0x40u;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v161);
    }
    if ( (v2 & 0x20) != 0 )
    {
      v2 &= ~0x20u;
      std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(&v173);
    }
    if ( (v2 & 0x10) != 0 )
    {
      v2 &= ~0x10u;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v164);
    }
    if ( v3 )
    {
      v71 = *(ResumeNotificationHandler **)(*((_QWORD *)this + 23) + 216LL);
      if ( v71 )
      {
        v72 = NotificationDeliveryTransaction::get_channelId(*((_QWORD *)this + 22), &v173);
        v73 = (const unsigned __int16 *)v72;
        if ( *(_QWORD *)(v72 + 24) > 7u )
          v73 = *(const unsigned __int16 **)v72;
        v74 = NotificationDeliveryTransaction::get_PackageFullName(*((NotificationDeliveryTransaction **)this + 22));
        v75 = *(struct TransientNotificationDetails **)NotificationDeliveryTransaction::get_notificationTransientDetails(
                                                         *((_QWORD *)this + 22),
                                                         &v161);
        v76 = (struct Notification **)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), &v160);
        v13 = ResumeNotificationHandler::ProcessResumeNotification(v71, *v76, v75, v74, v73);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v160);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v161);
        std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(&v173);
        if ( v13 >= 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, &WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              144,
              &WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids,
              (unsigned int)v13);
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x3E1,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
            (const char *)(unsigned int)v13,
            v158);
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v15 = 146;
            goto LABEL_21;
          }
        }
        goto LABEL_232;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          142,
          &WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids,
          2151547141LL);
      }
      v13 = -2143420155;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3D3,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
        (const char *)0x803E0105LL,
        v157);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_232;
      v15 = 143;
    }
    else
    {
LABEL_158:
      v77 = (_QWORD *)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), &v160);
      v78 = (_QWORD *)Notification::get_type(*v77, &v173);
      v79 = v78[2];
      if ( v78[3] > 7u )
        v78 = (_QWORD *)*v78;
      v80 = std::_Traits_equal<std::char_traits<unsigned short>>(v78, v79, L"raw", 3);
      std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(&v173);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v160);
      if ( v80 )
      {
        v81 = *(BackgroundActivation **)(*((_QWORD *)this + 23) + 208LL);
        if ( !v81 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              147,
              &WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids,
              2151547141LL);
          }
          v13 = -2143420155;
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x3EA,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
            (const char *)0x803E0105LL,
            v157);
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
            goto LABEL_232;
          v15 = 148;
          goto LABEL_41;
        }
        notificationTransientDetails = (TransientNotificationDetails **)NotificationDeliveryTransaction::get_notificationTransientDetails(
                                                                          *((_QWORD *)this + 22),
                                                                          &v163);
        v83 = *TransientNotificationDetails::get_messageId(*notificationTransientDetails, &v173);
        v84 = *(struct TransientNotificationDetails **)NotificationDeliveryTransaction::get_notificationTransientDetails(
                                                         *((_QWORD *)this + 22),
                                                         v164);
        v85 = *(struct Notification **)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), &v161);
        v86 = (struct INotificationHandler **)NotificationDeliveryTransaction::get_notificationHandler(
                                                *((_QWORD *)this + 22),
                                                &v160);
        v174 = v83;
        v13 = BackgroundActivation::ActivateRawNotificationWorkItem(v81, *v86, v85, v84, &v174);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v160);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v161);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v164);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v163);
        if ( v13 >= 0 )
          goto LABEL_232;
        v87 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            149,
            &WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids,
            (unsigned int)v13);
          v87 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v13 == -2147023728 || v13 == -2147024894 )
        {
          if ( v87 != &WPP_GLOBAL_Control && (*((_BYTE *)v87 + 28) & 0x40) != 0 && *((_BYTE *)v87 + 25) >= 5u )
          {
            v88 = (_QWORD *)NotificationDeliveryTransaction::get_channelId(*((_QWORD *)this + 22), &v173);
            v2 |= 0x80u;
            if ( v88[3] > 7u )
              v88 = (_QWORD *)*v88;
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, v89, v88);
            v87 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( (v2 & 0x80u) != 0 )
          {
            v2 &= ~0x80u;
            std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(&v173);
            v87 = (PVOID *)WPP_GLOBAL_Control;
          }
          v90 = *(BlockedRawChannels **)(*((_QWORD *)this + 23) + 296LL);
          if ( !v90 )
          {
            if ( v87 != &WPP_GLOBAL_Control && (*((_BYTE *)v87 + 28) & 0x40) != 0 && *((_BYTE *)v87 + 25) >= 2u )
              WPP_SF_d(v87[2], 151, &WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids, 2151547141LL);
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x400,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
              (const char *)0x803E0105LL,
              v159);
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
              goto LABEL_232;
            v15 = 152;
            goto LABEL_41;
          }
          v91 = NotificationDeliveryTransaction::get_channelId(*((_QWORD *)this + 22), &v174);
          v92 = (const unsigned __int16 *)v91;
          if ( *(_QWORD *)(v91 + 24) > 7u )
            v92 = *(const unsigned __int16 **)v91;
          v93 = (_QWORD *)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), &v160);
          v94 = Notification::get_handlerKey(*v93, &v173);
          if ( *(_QWORD *)(v94 + 24) > 7u )
            v94 = *(_QWORD *)v94;
          v44 = BlockedRawChannels::BlockChannel(v90, (const unsigned __int16 *)v94, v92);
          std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(&v173);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v160);
          std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(&v174);
          if ( (v44 & 0x80000000) != 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, &WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids, v44);
            }
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x404,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
              (const char *)v44,
              v159);
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
              goto LABEL_232;
            v15 = 154;
            goto LABEL_70;
          }
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x407,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
          (const char *)(unsigned int)v13,
          v159);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v15 = 155;
          goto LABEL_21;
        }
        goto LABEL_232;
      }
      v95 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 156, &WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids);
        v95 = (PVOID *)WPP_GLOBAL_Control;
      }
      v96 = (__int64 (__fastcall ***)(_QWORD, _QWORD, __int64, __int64))((*(_QWORD *)(*((_QWORD *)this + 23) + 128LL)
                                                                        + 16LL)
                                                                       & -(__int64)(*(_QWORD *)(*((_QWORD *)this + 23)
                                                                                              + 128LL) != 0));
      if ( v96 )
      {
        v97 = **v96;
        v98 = *(_QWORD *)NotificationDeliveryTransaction::get_notificationTransientDetails(*((_QWORD *)this + 22), v164);
        v99 = *(_QWORD *)NotificationDeliveryTransaction::get_notificationHandler(*((_QWORD *)this + 22), &v161);
        v100 = (_QWORD *)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), &v160);
        v13 = v97(v96, *v100, v99, v98);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v160);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v161);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v164);
        if ( v13 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              160,
              &WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids,
              (unsigned int)v13);
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x41C,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
            (const char *)(unsigned int)v13,
            v157);
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v15 = 161;
            goto LABEL_21;
          }
        }
        goto LABEL_232;
      }
      if ( v95 != &WPP_GLOBAL_Control && (*((_BYTE *)v95 + 28) & 0x40) != 0 && *((_BYTE *)v95 + 25) >= 2u )
        WPP_SF_d(v95[2], 158, &WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids, 2151547141LL);
      v13 = -2143420155;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x413,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
        (const char *)0x803E0105LL,
        v157);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_232;
      v15 = 159;
    }
LABEL_41:
    v16 = 2151547141LL;
    goto LABEL_22;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x36C,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
    (const char *)(unsigned int)v13,
    v154);
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v15 = 120;
    goto LABEL_21;
  }
LABEL_232:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57975764>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57975764>::GetImpl'::`2'::impl) )
  {
    if ( v13 >= 0 )
    {
      v119 = (TransientNotificationDetails **)NotificationDeliveryTransaction::get_notificationTransientDetails(
                                                *((_QWORD *)this + 22),
                                                &v160);
      v161 = *(_QWORD *)TransientNotificationDetails::get_messageId(*v119, &v173)->Data4;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v160);
      if ( (byte_18015DE45 & 4) != 0 )
      {
        NotificationPolicyReasonString = (__int64 *)NotificationAvailableWork::GetNotificationPolicyReasonString(
                                                      v177,
                                                      v165);
        v121 = (__int64)NotificationPolicyReasonString;
        v122 = v2 | 0x8000;
        if ( (unsigned __int64)NotificationPolicyReasonString[3] > 7 )
          v121 = *NotificationPolicyReasonString;
        v123 = (_QWORD *)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), &v174);
        v124 = v122 | 0x10000;
        v163 = v124;
        v125 = (__int64 *)Notification::get_handlerKey(*v123, &v173);
        v126 = (__int64)v125;
        v127 = v124 | 0x20000;
        v163 = v127;
        if ( (unsigned __int64)v125[3] > 7 )
          v126 = *v125;
        v128 = (Notification **)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), v164);
        v129 = Notification::get_id(*v128);
        v130 = (_QWORD *)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), &v160);
        v131 = v127 | 0xC0000;
        v163 = v131;
        v132 = (__int64 *)Notification::get_type(*v130, v175);
        LODWORD(v133) = (_DWORD)v132;
        v134 = v131 | 0x100000;
        v163 = v134;
        if ( (unsigned __int64)v132[3] > 7 )
          v133 = *v132;
        v135 = (_QWORD *)NotificationDeliveryTransaction::get_channelId(*((_QWORD *)this + 22), v176);
        v2 = v134 | 0x200000;
        if ( v135[3] > 7u )
          v135 = (_QWORD *)*v135;
        McTemplateU0zzqzxzd_EventWriteTransfer(v161, v136, (_DWORD)v135, v133, v129, v126, v161, v121, v13);
      }
      if ( (v2 & 0x200000) != 0 )
      {
        v2 &= ~0x200000u;
        std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(v176);
      }
      if ( (v2 & 0x100000) != 0 )
      {
        v2 &= ~0x100000u;
        std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(v175);
      }
      if ( (v2 & 0x80000) != 0 )
      {
        v2 &= ~0x80000u;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v160);
      }
      if ( (v2 & 0x40000) != 0 )
      {
        v2 &= ~0x40000u;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v164);
      }
      if ( (v2 & 0x20000) != 0 )
      {
        v2 &= ~0x20000u;
        std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(&v173);
      }
      if ( (v2 & 0x10000) != 0 )
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v174);
      if ( (v2 & 0x8000) != 0 )
      {
        v118 = v177;
        goto LABEL_282;
      }
    }
    else
    {
      if ( (byte_18015DE49 & 4) != 0 )
      {
        v101 = (__int64 *)NotificationAvailableWork::GetNotificationPolicyReasonString(v176, v165);
        v102 = (__int64)v101;
        v103 = v2 | 0x100;
        if ( (unsigned __int64)v101[3] > 7 )
          v102 = *v101;
        v104 = (_QWORD *)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), v164);
        v105 = v103 | 0x200;
        v163 = v105;
        v106 = (__int64 *)Notification::get_handlerKey(*v104, v175);
        v107 = (__int64)v106;
        v108 = v105 | 0x400;
        v163 = v108;
        if ( (unsigned __int64)v106[3] > 7 )
          v107 = *v106;
        v109 = (Notification **)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), &v161);
        v110 = Notification::get_id(*v109);
        v111 = (_QWORD *)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), &v160);
        v112 = v108 | 0x1800;
        v163 = v112;
        v113 = (__int64 *)Notification::get_type(*v111, &v174);
        LODWORD(v114) = (_DWORD)v113;
        v2 = v112 | 0x2000;
        v163 = v2;
        if ( (unsigned __int64)v113[3] > 7 )
          v114 = *v113;
        v115 = (_QWORD *)NotificationDeliveryTransaction::get_channelId(*((_QWORD *)this + 22), &v173);
        LOWORD(v2) = v2 | 0x4000;
        if ( v115[3] > 7u )
          v115 = (_QWORD *)*v115;
        McTemplateU0zzqzzd_EventWriteTransfer(v117, v116, (_DWORD)v115, v114, v110, v107, v102, v13);
      }
      if ( (v2 & 0x4000) != 0 )
      {
        LOWORD(v2) = v2 & 0xBFFF;
        std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(&v173);
      }
      if ( (v2 & 0x2000) != 0 )
      {
        LOWORD(v2) = v2 & 0xDFFF;
        std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(&v174);
      }
      if ( (v2 & 0x1000) != 0 )
      {
        LOWORD(v2) = v2 & 0xEFFF;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v160);
      }
      if ( (v2 & 0x800) != 0 )
      {
        LOWORD(v2) = v2 & 0xF7FF;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v161);
      }
      if ( (v2 & 0x400) != 0 )
      {
        LOWORD(v2) = v2 & 0xFBFF;
        std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(v175);
      }
      if ( (v2 & 0x200) != 0 )
      {
        LOWORD(v2) = v2 & 0xFDFF;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v164);
      }
      if ( (v2 & 0x100) != 0 )
      {
        v118 = v176;
LABEL_282:
        std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(v118);
      }
    }
  }
  else if ( v13 < 0 )
  {
    if ( byte_18015DE45 < 0 )
    {
      v137 = (_QWORD *)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), &v161);
      v138 = v2 | 0x400000;
      v163 = v138;
      v139 = (__int64 *)Notification::get_handlerKey(*v137, v175);
      v140 = (__int64)v139;
      v141 = v138 | 0x800000;
      v163 = v141;
      if ( (unsigned __int64)v139[3] > 7 )
        v140 = *v139;
      v142 = (Notification **)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), &v160);
      v143 = Notification::get_id(*v142);
      v144 = (_QWORD *)NotificationDeliveryTransaction::get_notification(*((_QWORD *)this + 22), &v174);
      v145 = v141 | 0x3000000;
      v163 = v145;
      v146 = (__int64 *)Notification::get_type(*v144, v176);
      LODWORD(v147) = (_DWORD)v146;
      v148 = v145 | 0x4000000;
      v163 = v148;
      if ( (unsigned __int64)v146[3] > 7 )
        v147 = *v146;
      v149 = (_QWORD *)NotificationDeliveryTransaction::get_channelId(*((_QWORD *)this + 22), v177);
      v2 = v148 | 0x8000000;
      if ( v149[3] > 7u )
        v149 = (_QWORD *)*v149;
      McTemplateU0zzqzd_EventWriteTransfer(v151, v150, (_DWORD)v149, v147, v143, v140, v13);
    }
    if ( (v2 & 0x8000000) != 0 )
    {
      v2 &= ~0x8000000u;
      std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(v177);
    }
    if ( (v2 & 0x4000000) != 0 )
    {
      v2 &= ~0x4000000u;
      std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(v176);
    }
    if ( (v2 & 0x2000000) != 0 )
    {
      v2 &= ~0x2000000u;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v174);
    }
    if ( (v2 & 0x1000000) != 0 )
    {
      v2 &= ~0x1000000u;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v160);
    }
    if ( (v2 & 0x800000) != 0 )
    {
      v2 &= ~0x800000u;
      std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(v175);
    }
    if ( (v2 & 0x400000) != 0 )
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v161);
  }
  NotificationAvailableWork::LogPushNotificationDelivered(
    (_DWORD)this,
    (unsigned int)&v167,
    (unsigned int)&pv,
    (unsigned int)&v169,
    (__int64)&v171,
    v162,
    v165,
    v13);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      163,
      &WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids,
      (unsigned int)v13);
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( v171 )
    CoTaskMemFree(v171);
  v152 = v168;
  if ( v168 )
  {
    v168 = 0;
    (*(void (__fastcall **)(WpnDatabaseHelpers *))(*(_QWORD *)v152 + 16LL))(v152);
  }
  if ( v167 )
    CoTaskMemFree(v167);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180054a78  mov     rax, rsp
0x180054a7b  push    rbp
0x180054a7c  push    rbx
0x180054a7d  push    rsi
0x180054a7e  push    rdi
0x180054a7f  push    r12
0x180054a81  push    r13
0x180054a83  push    r14
0x180054a85  push    r15
0x180054a87  lea     rbp, [rsp-78h]
0x180054a8c  sub     rsp, 178h
0x180054a93  movaps  xmmword ptr [rax-58h], xmm6
0x180054a97  mov     rax, cs:__security_cookie
0x180054a9e  xor     rax, rsp
0x180054aa1  mov     [rbp+0B0h+var_60], rax
0x180054aa5  mov     r15, rcx
0x180054aa8  xor     r12d, r12d
0x180054aab  mov     r14d, r12d
0x180054aae  mov     [rsp+1B0h+var_148], r12d
0x180054ab3  mov     [rsp+1B0h+var_134], r12d
0x180054ab8  mov     [rbp+0B0h+var_130], r12
0x180054abc  mov     [rbp+0B0h+var_128], r12
0x180054ac0  mov     [rbp+0B0h+var_108], r12d
0x180054ac4  mov     [rbp+0B0h+var_110], r12
0x180054ac8  mov     [rbp+0B0h+pv], r12
0x180054acc  mov     [rsp+1B0h+var_150], r12b
0x180054ad1  mov     [rsp+1B0h+var_138], r12d
0x180054ad6  mov     [rbp+0B0h+var_120], r12d
0x180054ada  lea     rsi, WPP_GLOBAL_Control
0x180054ae1  lea     r13d, [r12+1]
0x180054ae6  mov     rax, cs:WPP_GLOBAL_Control
0x180054aed  cmp     rax, rsi
0x180054af0  jz      loc_180054B9A
0x180054af6  test    byte ptr [rax+1Ch], 40h
0x180054afa  jz      loc_180054B9A
0x180054b00  cmp     byte ptr [rax+19h], 6
0x180054b04  jb      loc_180054B9A
0x180054b0a  lea     rdx, [rsp+1B0h+var_158]
0x180054b0f  mov     rcx, [rcx+0B0h]
0x180054b16  call    ?get_notification@NotificationDeliveryTransaction@@QEAA?AV?$ComPtr@VNotification@@@WRL@Microsoft@@XZ; NotificationDeliveryTransaction::get_notification(void)
0x180054b1b  nop
0x180054b1c  mov     [rsp+1B0h+var_148], r13d
0x180054b21  mov     rcx, [rax]; this
0x180054b24  call    ?get_id@Notification@@QEAAKXZ; Notification::get_id(void)
0x180054b29  mov     edi, eax
0x180054b2b  lea     rdx, [rbp+0B0h+var_E0]
0x180054b2f  mov     rcx, [r15+0B0h]
0x180054b36  call    ?get_channelId@NotificationDeliveryTransaction@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; NotificationDeliveryTransaction::get_channelId(void)
0x180054b3b  mov     rbx, rax
0x180054b3e  cmp     qword ptr [rax+18h], 7
0x180054b43  jbe     short loc_180054B48
0x180054b45  mov     rbx, [rax]
0x180054b48  lea     rdx, [rsp+1B0h+var_140]
0x180054b4d  mov     rcx, [r15+0B0h]
0x180054b54  call    ?get_notification@NotificationDeliveryTransaction@@QEAA?AV?$ComPtr@VNotification@@@WRL@Microsoft@@XZ; NotificationDeliveryTransaction::get_notification(void)
0x180054b59  nop
0x180054b5a  mov     [rsp+1B0h+var_148], 7
0x180054b62  lea     rdx, [rbp+0B0h+var_100]
0x180054b66  mov     rcx, [rax]
0x180054b69  call    ?get_type@Notification@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Notification::get_type(void)
0x180054b6e  mov     r14d, 0Fh
0x180054b74  cmp     qword ptr [rax+18h], 7
0x180054b79  jbe     short loc_180054B7E
0x180054b7b  mov     rax, [rax]
0x180054b7e  mov     dword ptr [rsp+1B0h+var_188], edi
0x180054b82  mov     [rsp+1B0h+var_190], rbx; int
0x180054b87  mov     r9, rax
0x180054b8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180054b91  mov     rcx, [rcx+10h]
0x180054b95  call    WPP_SF_SSd
0x180054b9a  test    r14b, 8
0x180054b9e  jz      short loc_180054BAE
0x180054ba0  and     r14d, 0FFFFFFF7h
0x180054ba4  lea     rcx, [rbp+0B0h+var_100]; void *
0x180054ba8  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@@std@@QEAA@XZ; std::pair<std::wstring const,__MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,__MIDL___MIDL_itf_wpntypes_0000_0000_0005>(void)
0x180054bad  nop
0x180054bae  test    r14b, 4
0x180054bb2  jz      short loc_180054BC3
0x180054bb4  and     r14d, 0FFFFFFFBh
0x180054bb8  lea     rcx, [rsp+1B0h+var_140]
0x180054bbd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180054bc2  nop
0x180054bc3  test    r14b, 2
0x180054bc7  jz      short loc_180054BD7
0x180054bc9  and     r14d, 0FFFFFFFDh
0x180054bcd  lea     rcx, [rbp+0B0h+var_E0]; void *
0x180054bd1  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@@std@@QEAA@XZ; std::pair<std::wstring const,__MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,__MIDL___MIDL_itf_wpntypes_0000_0000_0005>(void)
0x180054bd6  nop
0x180054bd7  test    r13b, r14b
0x180054bda  jz      short loc_180054BEA
0x180054bdc  and     r14d, 0FFFFFFFEh
0x180054be0  lea     rcx, [rsp+1B0h+var_158]
0x180054be5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180054bea  mov     rcx, r15; this
0x180054bed  call    ?ProcessChannel@NotificationAvailableWork@@AEAAJXZ; NotificationAvailableWork::ProcessChannel(void)
0x180054bf2  mov     ebx, eax
0x180054bf4  test    eax, eax
0x180054bf6  jns     short loc_180054C4A
0x180054bf8  mov     rcx, [rbp+0B8h]; this
0x180054bff  mov     r9d, eax; char *
0x180054c02  lea     r8, aOnecoreuapBase_80; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180054c09  mov     edx, 363h; void *
0x180054c0e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180054c13  mov     rcx, cs:WPP_GLOBAL_Control
0x180054c1a  cmp     rcx, rsi
0x180054c1d  jz      loc_180055E2A
0x180054c23  test    byte ptr [rcx+1Ch], 80h
0x180054c27  jz      loc_180055E2A
0x180054c2d  mov     edx, 77h ; 'w'
0x180054c32  mov     r9d, ebx
0x180054c35  lea     r8, WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids
0x180054c3c  mov     rcx, [rcx+10h]
0x180054c40  call    WPP_SF_d
0x180054c45  jmp     loc_180055E2A
0x180054c4a  xor     edx, edx
0x180054c4c  lea     rcx, [rbp+0B0h+pv]
0x180054c50  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180054c55  lea     rdx, [rsp+1B0h+var_158]
0x180054c5a  mov     rcx, [r15+0B0h]
0x180054c61  call    ?get_notificationHandler@NotificationDeliveryTransaction@@QEAA?AV?$ComPtr@UINotificationHandler@@@WRL@Microsoft@@XZ; NotificationDeliveryTransaction::get_notificationHandler(void)
0x180054c66  lea     r8, [rbp+0B0h+pv]; unsigned __int16 **
0x180054c6a  mov     rdx, [rax]; struct INotificationHandler *
0x180054c6d  call    ?GetParentId@NotificationAvailableWork@@AEAAJPEAUINotificationHandler@@PEAPEAG@Z; NotificationAvailableWork::GetParentId(INotificationHandler *,ushort * *)
0x180054c72  mov     rcx, [rbp+0B8h]; this
0x180054c79  lea     r12, aOnecoreuapBase_80; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180054c80  test    eax, eax
0x180054c82  jns     short loc_180054C94
0x180054c84  mov     r9d, eax; char *
0x180054c87  mov     r8, r12; unsigned int
0x180054c8a  mov     edx, 369h; void *
0x180054c8f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180054c94  lea     rcx, [rsp+1B0h+var_158]
0x180054c99  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180054c9e  lea     rdx, [rsp+1B0h+var_158]
0x180054ca3  mov     rcx, [r15+0B0h]
0x180054caa  call    ?get_notificationHandler@NotificationDeliveryTransaction@@QEAA?AV?$ComPtr@UINotificationHandler@@@WRL@Microsoft@@XZ; NotificationDeliveryTransaction::get_notificationHandler(void)
0x180054caf  nop
0x180054cb0  mov     rdi, [rax]
0x180054cb3  mov     rax, [rdi]
0x180054cb6  mov     rbx, [rax+18h]
0x180054cba  xor     edx, edx
0x180054cbc  lea     rcx, [rbp+0B0h+var_130]
0x180054cc0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180054cc5  lea     rdx, [rbp+0B0h+var_130]
0x180054cc9  mov     rcx, rdi
0x180054ccc  mov     rax, rbx
0x180054ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054cd4  mov     ebx, eax
0x180054cd6  lea     rcx, [rsp+1B0h+var_158]
0x180054cdb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180054ce0  test    ebx, ebx
0x180054ce2  jns     short loc_180054D1F
0x180054ce4  mov     rcx, [rbp+0B8h]; this
0x180054ceb  mov     r9d, ebx; char *
0x180054cee  mov     r8, r12; unsigned int
0x180054cf1  mov     edx, 36Ch; void *
0x180054cf6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180054cfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180054d02  cmp     rcx, rsi
0x180054d05  jz      loc_180055E2A
0x180054d0b  test    byte ptr [rcx+1Ch], 80h
0x180054d0f  jz      loc_180055E2A
0x180054d15  mov     edx, 78h ; 'x'
0x180054d1a  jmp     loc_180054C32
0x180054d1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180054d26  cmp     rcx, rsi
0x180054d29  jz      short loc_180054D50
0x180054d2b  test    byte ptr [rcx+1Ch], 40h
0x180054d2f  jz      short loc_180054D50
0x180054d31  cmp     byte ptr [rcx+19h], 5
0x180054d35  jb      short loc_180054D50
0x180054d37  mov     edx, 79h ; 'y'
0x180054d3c  mov     r9, [rbp+0B0h+var_130]
0x180054d40  mov     rcx, [rcx+10h]
0x180054d44  call    WPP_SF_S
0x180054d49  mov     rcx, cs:WPP_GLOBAL_Control
0x180054d50  mov     rax, [r15+0B8h]
0x180054d57  mov     rax, [rax+78h]
0x180054d5b  mov     [rsp+1B0h+var_158], rax
0x180054d60  test    rax, rax
0x180054d63  jnz     short loc_180054DD4
0x180054d65  mov     edi, 803E0105h
0x180054d6a  cmp     rcx, rsi
0x180054d6d  jz      short loc_180054D91
0x180054d6f  test    byte ptr [rcx+1Ch], 40h
0x180054d73  jz      short loc_180054D91
0x180054d75  cmp     byte ptr [rcx+19h], 2
0x180054d79  jb      short loc_180054D91
0x180054d7b  lea     edx, [rax+7Ah]
0x180054d7e  mov     r9d, edi
0x180054d81  lea     r8, WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids
0x180054d88  mov     rcx, [rcx+10h]
0x180054d8c  call    WPP_SF_d
0x180054d91  mov     ebx, edi
0x180054d93  mov     rcx, [rbp+0B8h]; this
0x180054d9a  mov     r9d, edi; char *
0x180054d9d  mov     r8, r12; unsigned int
0x180054da0  mov     edx, 373h; void *
0x180054da5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180054daa  mov     rcx, cs:WPP_GLOBAL_Control
0x180054db1  cmp     rcx, rsi
0x180054db4  jz      loc_180055E2A
0x180054dba  test    byte ptr [rcx+1Ch], 80h
0x180054dbe  jz      loc_180055E2A
0x180054dc4  mov     edx, 7Bh ; '{'
0x180054dc9  mov     r9d, 803E0105h
0x180054dcf  jmp     loc_180054C35
0x180054dd4  mov     rax, [rax]
0x180054dd7  mov     rsi, [rax+40h]
0x180054ddb  lea     rdx, [rsp+1B0h+var_160]
0x180054de0  mov     rcx, [r15+0B0h]
0x180054de7  call    ?get_notification@NotificationDeliveryTransaction@@QEAA?AV?$ComPtr@VNotification@@@WRL@Microsoft@@XZ; NotificationDeliveryTransaction::get_notification(void)
0x180054dec  nop
0x180054ded  mov     rcx, [rax]; this
0x180054df0  call    ?get_payloadSize@Notification@@QEAA_KXZ; Notification::get_payloadSize(void)
0x180054df5  mov     edi, eax
0x180054df7  lea     rdx, [rsp+1B0h+var_148]
0x180054dfc  mov     rcx, [r15+0B0h]
0x180054e03  call    ?get_notification@NotificationDeliveryTransaction@@QEAA?AV?$ComPtr@VNotification@@@WRL@Microsoft@@XZ; NotificationDeliveryTransaction::get_notification(void)
0x180054e08  nop
0x180054e09  mov     rcx, [rax]; this
0x180054e0c  call    ?get_id@Notification@@QEAAKXZ; Notification::get_id(void)
0x180054e11  mov     ebx, eax
0x180054e13  lea     rdx, [rsp+1B0h+var_140]
0x180054e18  mov     rcx, [r15+0B0h]
0x180054e1f  call    ?get_notification@NotificationDeliveryTransaction@@QEAA?AV?$ComPtr@VNotification@@@WRL@Microsoft@@XZ; NotificationDeliveryTransaction::get_notification(void)
0x180054e24  nop
0x180054e25  lea     rdx, [rbp+0B0h+var_100]
0x180054e29  mov     rcx, [rax]
0x180054e2c  call    ?get_type@Notification@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Notification::get_type(void)
0x180054e31  mov     rcx, rax; unsigned __int8 *
0x180054e34  call    ?NotificationTypeFromName@WpnDatabaseHelpers@@YA?AW4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WpnDatabaseHelpers::NotificationTypeFromName(std::wstring)
0x180054e39  mov     [rsp+1B0h+var_188], rdi
0x180054e3e  mov     dword ptr [rsp+1B0h+var_190], ebx; int
0x180054e42  mov     r9d, eax
0x180054e45  xor     r8d, r8d
0x180054e48  mov     rdx, [rbp+0B0h+var_130]
0x180054e4c  mov     rcx, [rsp+1B0h+var_158]
0x180054e51  mov     rax, rsi
0x180054e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054e59  mov     ebx, eax
0x180054e5b  lea     rcx, [rsp+1B0h+var_140]
0x180054e60  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180054e65  nop
0x180054e66  lea     rcx, [rsp+1B0h+var_148]
0x180054e6b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180054e70  nop
0x180054e71  lea     rcx, [rsp+1B0h+var_160]
0x180054e76  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180054e7b  test    ebx, ebx
0x180054e7d  jns     short loc_180054EF1
0x180054e7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180054e86  lea     rsi, WPP_GLOBAL_Control
0x180054e8d  cmp     rcx, rsi
0x180054e90  jz      short loc_180054EB6
0x180054e92  test    byte ptr [rcx+1Ch], 40h
0x180054e96  jz      short loc_180054EB6
0x180054e98  cmp     byte ptr [rcx+19h], 2
0x180054e9c  jb      short loc_180054EB6
0x180054e9e  mov     edx, 7Ch ; '|'
0x180054ea3  mov     r9d, ebx
0x180054ea6  lea     r8, WPP_5ffd1009b41e3432588be146eff6c2b8_Traceguids
0x180054ead  mov     rcx, [rcx+10h]
0x180054eb1  call    WPP_SF_d
0x180054eb6  mov     rcx, [rbp+0B8h]; this
0x180054ebd  mov     r9d, ebx; char *
0x180054ec0  mov     r8, r12; unsigned int
0x180054ec3  mov     edx, 37Eh; void *
0x180054ec8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180054ecd  mov     rcx, cs:WPP_GLOBAL_Control
0x180054ed4  cmp     rcx, rsi
0x180054ed7  jz      loc_180055E2A
0x180054edd  test    byte ptr [rcx+1Ch], 80h
0x180054ee1  jz      loc_180055E2A
0x180054ee7  mov     edx, 7Dh ; '}'
0x180054eec  jmp     loc_180054C32
0x180054ef1  lea     rdx, [rsp+1B0h+var_160]
0x180054ef6  mov     rcx, [r15+0B0h]
0x180054efd  call    ?get_notificationHandler@NotificationDeliveryTransaction@@QEAA?AV?$ComPtr@UINotificationHandler@@@WRL@Microsoft@@XZ; NotificationDeliveryTransaction::get_notificationHandler(void)
0x180054f02  nop
0x180054f03  mov     rdi, [rax]
0x180054f06  mov     rax, [rdi]
0x180054f09  mov     rbx, [rax+20h]
0x180054f0d  lea     rcx, [rbp+0B0h+var_128]
0x180054f11  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180054f16  lea     rdx, [rbp+0B0h+var_128]
0x180054f1a  mov     rcx, rdi
0x180054f1d  mov     rax, rbx
0x180054f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054f25  mov     ebx, eax
0x180054f27  lea     rcx, [rsp+1B0h+var_160]
0x180054f2c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180054f31  test    ebx, ebx
0x180054f33  jns     short loc_180054F77
0x180054f35  mov     rcx, [rbp+0B8h]; this
0x180054f3c  mov     r9d, ebx; char *
0x180054f3f  mov     r8, r12; unsigned int
0x180054f42  mov     edx, 382h; void *
0x180054f47  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180054f4c  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
