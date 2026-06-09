# Windows::Networking::UX::Internal::CAccessPointHelper::_OnTetheringStationConnectionNotification(TETHERING_NOTIFICATION_DATA const &,Windows::Networking::UX::Internal::TetheringNotificationContext &)

- ea: `0x180033650`
- end: `0x180033b6c`
- name: `?_OnTetheringStationConnectionNotification@CAccessPointHelper@Internal@UX@Networking@Windows@@AEAAJAEBUTETHERING_NOTIFICATION_DATA@@AEAUTetheringNotificationContext@2345@@Z`
- size: `1308`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CAccessPointHelper *__hidden this, const struct TETHERING_NOTIFICATION_DATA *, struct Windows::Networking::UX::Internal::TetheringNotificationContext *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800341f0`

## callees

- `0x180003ed0`
- `0x1800097b4`
- `0x18000de4c`
- `0x180011a64`
- `0x1800121e8`
- `0x1800141a0`
- `0x18001b838`
- `0x18001c044`
- `0x18001d4d4`
- `0x18002f1a8`
- `0x180031b6c`
- `0x1800332f0`
- `0x180033650`
- `0x18003409c`
- `0x18003443c`
- `0x18008e010`

## string_xrefs

- `0x1800336d5`: `onecoreuap\net\ux\wlanmediamanager\lib\accesspointhelpers.cpp`
- `0x180033810`: `onecoreuap\net\ux\wlanmediamanager\lib\accesspointhelpers.cpp`
- `0x1800338fb`: `onecoreuap\net\ux\wlanmediamanager\lib\accesspointhelpers.cpp`
- `0x1800339cd`: `onecoreuap\net\ux\wlanmediamanager\lib\accesspointhelpers.cpp`
- `0x180033a97`: `onecoreuap\net\ux\wlanmediamanager\lib\accesspointhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Windows::Networking::UX::Internal::CAccessPointHelper::_OnTetheringStationConnectionNotification(
        Windows::Networking::UX::Internal::CAccessPointHelper *this,
        const struct TETHERING_NOTIFICATION_DATA *a2,
        struct Windows::Networking::UX::Internal::TetheringNotificationContext *a3)
{
  Windows::Networking::UX::Internal::CAccessPointHelper *v5; // rsi
  __int64 v6; // rdi
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned __int16 *v10; // rax
  int v11; // eax
  unsigned int v12; // esi
  const struct Windows::Networking::UX::Internal::CAccessPointHelper::CONNECTION_FLOW_EVENT_ENTRY near *const *v13; // r8
  __int64 v14; // rax
  unsigned __int64 v15; // rdx
  __int64 v16; // r8
  char v17; // r10
  __int64 v18; // r11
  int v19; // r9d
  int v20; // eax
  unsigned int v21; // esi
  __int64 v22; // rax
  __int64 v23; // rax
  int v24; // eax
  unsigned int v25; // ebx
  __int64 v26; // rax
  __int64 v27; // rax
  int v28; // eax
  unsigned int v29; // ebx
  __int64 v30; // rax
  int v31; // [rsp+20h] [rbp-C8h]
  int v32; // [rsp+20h] [rbp-C8h]
  int v33; // [rsp+20h] [rbp-C8h]
  int v34; // [rsp+20h] [rbp-C8h]
  int v35; // [rsp+20h] [rbp-C8h]
  __int64 v36; // [rsp+50h] [rbp-98h] BYREF
  __int64 v37; // [rsp+58h] [rbp-90h] BYREF
  _BYTE v38[8]; // [rsp+60h] [rbp-88h] BYREF
  unsigned int v39[4]; // [rsp+68h] [rbp-80h] BYREF
  __int64 v40; // [rsp+78h] [rbp-70h]
  int v41[4]; // [rsp+88h] [rbp-60h] BYREF
  _OWORD v42[2]; // [rsp+98h] [rbp-50h] BYREF
  int v43; // [rsp+B8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v5 = Windows::Networking::UX::Internal::CAccessPointHelper::s_pSingletonInstance;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids);
  wil::EnterCriticalSection(v38, (char *)a3 + 16);
  v6 = *((_QWORD *)a3 + 1);
  if ( !v6 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x59F,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\accesspointhelpers.cpp",
      (const char *)0x80070057LL,
      v31);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v38);
    return 2147942487LL;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_L_guid__guid_L(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      140,
      (_DWORD)a2 + 4,
      *(_DWORD *)a2,
      (__int64)a2 + 4,
      (__int64)a2 + 20);
  *(_OWORD *)v41 = 0;
  memset(v42, 0, sizeof(v42));
  v43 = 0;
  std::wstring::wstring(v39);
  Windows::Networking::UX::Internal::CAccessPointHelper::_GetWlanInfoForTetheringNotification(v5, (unsigned int)v39);
  if ( v40 )
  {
    if ( !LODWORD(v42[0]) )
    {
      v10 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v39, v8, v9);
      v11 = Windows::Networking::UX::Internal::_StringToSsid(v10);
      v12 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5B8,
          (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\accesspointhelpers.cpp",
          (const char *)(unsigned int)v11,
          v32);
        std::wstring::_Tidy_deallocate(v39);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v38);
        return v12;
      }
    }
    v36 = 0;
    switch ( *(_DWORD *)a2 )
    {
      case 1:
        v27 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v39, v8, v9);
        v28 = Windows::Networking::UX::Internal::CAccessPointHelper::_CreateNotificationListForFlowEvents(
                &v36,
                4u,
                (__int64)&Windows::Networking::UX::Internal::CAccessPointHelper::sc_rgConnectStartFlowEvents,
                0,
                (__int64)v41,
                (int)v42,
                v27,
                0,
                0,
                &v36);
        v29 = v28;
        if ( v28 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5C8,
            (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\accesspointhelpers.cpp",
            (const char *)(unsigned int)v28,
            v35);
          std::unique_ptr<Windows::Networking::UX::Internal::IWlanNotificationList>::~unique_ptr<Windows::Networking::UX::Internal::IWlanNotificationList>(&v36);
          std::wstring::_Tidy_deallocate(v39);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v38);
          return v29;
        }
        v30 = v36;
        v36 = 0;
        v37 = v30;
        (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 8LL))(v6, &v37);
        break;
      case 2:
        v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v39, v8, v9);
        v24 = Windows::Networking::UX::Internal::CAccessPointHelper::_CreateNotificationListForFlowEvents(
                &v36,
                2u,
                (__int64)&Windows::Networking::UX::Internal::CAccessPointHelper::sc_rgConnectCompleteFlowEvents,
                0,
                (__int64)v41,
                (int)v42,
                v23,
                0,
                0,
                &v36);
        v25 = v24;
        if ( v24 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5D5,
            (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\accesspointhelpers.cpp",
            (const char *)(unsigned int)v24,
            v34);
          std::unique_ptr<Windows::Networking::UX::Internal::IWlanNotificationList>::~unique_ptr<Windows::Networking::UX::Internal::IWlanNotificationList>(&v36);
          std::wstring::_Tidy_deallocate(v39);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v38);
          return v25;
        }
        v26 = v36;
        v36 = 0;
        v37 = v26;
        (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 16LL))(v6, &v37);
        break;
      case 3:
      case 5:
        v13 = &Windows::Networking::UX::Internal::CAccessPointHelper::sc_rgConnectFailFlowEvents;
        if ( *(_DWORD *)a2 != 3 )
          v13 = &Windows::Networking::UX::Internal::CAccessPointHelper::sc_rgDisconnectFlowEvents;
        v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v39, 3LL - (*(_DWORD *)a2 != 3), v13);
        v19 = *((_DWORD *)a2 + 9);
        if ( v19 == 5 )
          v19 = 229377;
        v20 = Windows::Networking::UX::Internal::CAccessPointHelper::_CreateNotificationListForFlowEvents(
                &v36,
                v15,
                v16,
                v19,
                (__int64)v41,
                (int)v42,
                v14,
                v17,
                v18,
                &v36);
        v21 = v20;
        if ( v20 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5E9,
            (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\accesspointhelpers.cpp",
            (const char *)(unsigned int)v20,
            v33);
          std::unique_ptr<Windows::Networking::UX::Internal::IWlanNotificationList>::~unique_ptr<Windows::Networking::UX::Internal::IWlanNotificationList>(&v36);
          std::wstring::_Tidy_deallocate(v39);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v38);
          return v21;
        }
        v22 = v36;
        v36 = 0;
        v37 = v22;
        (*(void (__fastcall **)(__int64, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v6 + 24LL))(
          v6,
          &v37,
          *((unsigned int *)a2 + 9),
          *((_QWORD *)a2 + 5));
        break;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids, 0);
    std::unique_ptr<Windows::Networking::UX::Internal::IWlanNotificationList>::~unique_ptr<Windows::Networking::UX::Internal::IWlanNotificationList>(&v36);
    std::wstring::_Tidy_deallocate(v39);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v38);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids, 0);
    std::wstring::_Tidy_deallocate(v39);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v38);
    return 0;
  }
}

```

## disassembly

```asm
0x180033650  mov     [rsp+arg_0], rbx
0x180033655  push    rsi
0x180033656  push    rdi
0x180033657  push    r15
0x180033659  sub     rsp, 0D0h
0x180033660  mov     rax, cs:__security_cookie
0x180033667  xor     rax, rsp
0x18003366a  mov     [rsp+0E8h+var_28], rax
0x180033672  mov     rdi, r8
0x180033675  mov     rbx, rdx
0x180033678  mov     rsi, cs:?s_pSingletonInstance@CAccessPointHelper@Internal@UX@Networking@Windows@@0PEAV12345@EA; Windows::Networking::UX::Internal::CAccessPointHelper * Windows::Networking::UX::Internal::CAccessPointHelper::s_pSingletonInstance
0x18003367f  lea     r15, WPP_GLOBAL_Control
0x180033686  mov     rcx, cs:WPP_GLOBAL_Control
0x18003368d  cmp     rcx, r15
0x180033690  jz      short loc_1800336AD
0x180033692  test    byte ptr [rcx+1Ch], 40h
0x180033696  jz      short loc_1800336AD
0x180033698  mov     edx, 8Bh
0x18003369d  lea     r8, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x1800336a4  mov     rcx, [rcx+10h]
0x1800336a8  call    WPP_SF_
0x1800336ad  lea     rdx, [rdi+10h]
0x1800336b1  lea     rcx, [rsp+0E8h+var_88]
0x1800336b6  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800336bb  nop
0x1800336bc  mov     rdi, [rdi+8]
0x1800336c0  test    rdi, rdi
0x1800336c3  jnz     short loc_1800336F8
0x1800336c5  mov     rcx, [rsp+0E8h]; this
0x1800336cd  mov     ebx, 80070057h
0x1800336d2  mov     r9d, ebx; char *
0x1800336d5  lea     r8, aOnecoreuapNetU_0; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x1800336dc  mov     edx, 59Fh; void *
0x1800336e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800336e6  nop
0x1800336e7  lea     rcx, [rsp+0E8h+var_88]
0x1800336ec  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800336f1  mov     eax, ebx
0x1800336f3  jmp     loc_180033B47
0x1800336f8  mov     r10, cs:WPP_GLOBAL_Control
0x1800336ff  cmp     r10, r15
0x180033702  jz      short loc_180033735
0x180033704  test    byte ptr [r10+1Ch], 8
0x180033709  jz      short loc_180033735
0x18003370b  lea     rcx, [rbx+14h]
0x18003370f  lea     r8, [rbx+4]
0x180033713  mov     edx, 8Ch
0x180033718  mov     eax, [rbx+24h]
0x18003371b  mov     dword ptr [rsp+0E8h+var_B8], eax
0x18003371f  mov     [rsp+0E8h+var_C0], rcx
0x180033724  mov     qword ptr [rsp+0E8h+var_C8], r8
0x180033729  mov     r9d, [rbx]
0x18003372c  mov     rcx, [r10+10h]
0x180033730  call    WPP_SF_L_guid__guid_L
0x180033735  xorps   xmm0, xmm0
0x180033738  movups  xmmword ptr [rsp+0E8h+var_60], xmm0
0x180033740  xorps   xmm1, xmm1
0x180033743  xor     eax, eax
0x180033745  movups  [rsp+0E8h+var_50], xmm1
0x18003374d  movups  [rsp+0E8h+var_40], xmm1
0x180033755  mov     [rsp+0E8h+var_30], eax
0x18003375c  lea     rcx, [rsp+0E8h+var_80]
0x180033761  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180033766  nop
0x180033767  lea     rax, [rsp+0E8h+var_80]
0x18003376c  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x180033771  lea     r9, [rsp+0E8h+var_50]
0x180033779  lea     r8, [rsp+0E8h+var_60]
0x180033781  mov     rdx, rbx
0x180033784  mov     rcx, rsi; this
0x180033787  call    ?_GetWlanInfoForTetheringNotification@CAccessPointHelper@Internal@UX@Networking@Windows@@AEAAXAEBUTETHERING_NOTIFICATION_DATA@@AEAU_GUID@@AEAU_DOT11_SSID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Networking::UX::Internal::CAccessPointHelper::_GetWlanInfoForTetheringNotification(TETHERING_NOTIFICATION_DATA const &,_GUID &,_DOT11_SSID &,std::wstring &)
0x18003378c  cmp     [rsp+0E8h+var_70], 0
0x180033792  jnz     short loc_1800337DB
0x180033794  mov     rcx, cs:WPP_GLOBAL_Control
0x18003379b  cmp     rcx, r15
0x18003379e  jz      short loc_1800337BF
0x1800337a0  test    byte ptr [rcx+1Ch], 40h
0x1800337a4  jz      short loc_1800337BF
0x1800337a6  mov     edx, 8Dh
0x1800337ab  xor     r9d, r9d
0x1800337ae  lea     r8, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x1800337b5  mov     rcx, [rcx+10h]
0x1800337b9  call    WPP_SF_d
0x1800337be  nop
0x1800337bf  lea     rcx, [rsp+0E8h+var_80]
0x1800337c4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800337c9  nop
0x1800337ca  lea     rcx, [rsp+0E8h+var_88]
0x1800337cf  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800337d4  xor     eax, eax
0x1800337d6  jmp     loc_180033B47
0x1800337db  cmp     dword ptr [rsp+0E8h+var_50], 0
0x1800337e3  jnz     short loc_18003383E
0x1800337e5  lea     rcx, [rsp+0E8h+var_80]
0x1800337ea  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800337ef  mov     rcx, rax; unsigned __int16 *
0x1800337f2  lea     rdx, [rsp+0E8h+var_50]
0x1800337fa  call    Windows__Networking__UX__Internal___StringToSsid
0x1800337ff  mov     esi, eax
0x180033801  test    eax, eax
0x180033803  jns     short loc_18003383E
0x180033805  mov     rcx, [rsp+0E8h]; this
0x18003380d  mov     r9d, eax; char *
0x180033810  lea     r8, aOnecoreuapNetU_0; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180033817  mov     edx, 5B8h; void *
0x18003381c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033821  nop
0x180033822  lea     rcx, [rsp+0E8h+var_80]
0x180033827  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003382c  nop
0x18003382d  lea     rcx, [rsp+0E8h+var_88]
0x180033832  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180033837  mov     eax, esi
0x180033839  jmp     loc_180033B47
0x18003383e  mov     [rsp+0E8h+var_98], 0
0x180033847  mov     eax, [rbx]
0x180033849  sub     eax, 1
0x18003384c  jz      loc_180033A32
0x180033852  sub     eax, 1
0x180033855  jz      loc_180033968
0x18003385b  sub     eax, 1
0x18003385e  jz      short loc_180033869
0x180033860  cmp     eax, 2
0x180033863  jnz     loc_180033AF4
0x180033869  lea     rax, ?sc_rgDisconnectFlowEvents@CAccessPointHelper@Internal@UX@Networking@Windows@@0QBUCONNECTION_FLOW_EVENT_ENTRY@12345@B; Windows::Networking::UX::Internal::CAccessPointHelper::CONNECTION_FLOW_EVENT_ENTRY const near * const Windows::Networking::UX::Internal::CAccessPointHelper::sc_rgDisconnectFlowEvents
0x180033870  lea     r8, ?sc_rgConnectFailFlowEvents@CAccessPointHelper@Internal@UX@Networking@Windows@@0QBUCONNECTION_FLOW_EVENT_ENTRY@12345@B; Windows::Networking::UX::Internal::CAccessPointHelper::CONNECTION_FLOW_EVENT_ENTRY const near * const Windows::Networking::UX::Internal::CAccessPointHelper::sc_rgConnectFailFlowEvents
0x180033877  cmp     dword ptr [rbx], 3
0x18003387a  cmovnz  r8, rax
0x18003387e  mov     eax, [rbx]
0x180033880  sub     eax, 3
0x180033883  neg     eax
0x180033885  sbb     rdx, rdx
0x180033888  add     rdx, 3
0x18003388c  mov     r11, [rbx+28h]
0x180033890  cmp     dword ptr [rbx], 3
0x180033893  setz    r10b
0x180033897  lea     rcx, [rsp+0E8h+var_80]
0x18003389c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800338a1  mov     r9d, [rbx+24h]
0x1800338a5  mov     ecx, 38001h
0x1800338aa  cmp     r9d, 5
0x1800338ae  cmovz   r9d, ecx
0x1800338b2  lea     rcx, [rsp+0E8h+var_98]
0x1800338b7  mov     [rsp+0E8h+var_A0], rcx
0x1800338bc  mov     [rsp+0E8h+var_A8], r11
0x1800338c1  mov     [rsp+0E8h+var_B0], r10b
0x1800338c6  mov     [rsp+0E8h+var_B8], rax
0x1800338cb  lea     rax, [rsp+0E8h+var_50]
0x1800338d3  mov     [rsp+0E8h+var_C0], rax
0x1800338d8  lea     rax, [rsp+0E8h+var_60]
0x1800338e0  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x1800338e5  call    ?_CreateNotificationListForFlowEvents@CAccessPointHelper@Internal@UX@Networking@Windows@@AEAAJ_KPEBUCONNECTION_FLOW_EVENT_ENTRY@12345@KAEBU_GUID@@AEBU_DOT11_SSID@@PEBG_N4AEAV?$unique_ptr@UIWlanNotificationList@Internal@UX@Networking@Windows@@U?$default_delete@UIWlanNotificationList@Internal@UX@Networking@Windows@@@std@@@std@@@Z; Windows::Networking::UX::Internal::CAccessPointHelper::_CreateNotificationListForFlowEvents(unsigned __int64,Windows::Networking::UX::Internal::CAccessPointHelper::CONNECTION_FLOW_EVENT_ENTRY const *,ulong,_GUID const &,_DOT11_SSID const &,ushort const *,bool,ushort const *,std::unique_ptr<Windows::Networking::UX::Internal::IWlanNotificationList> &)
0x1800338ea  mov     esi, eax
0x1800338ec  test    eax, eax
0x1800338ee  jns     short loc_180033934
0x1800338f0  mov     rcx, [rsp+0E8h]; this
0x1800338f8  mov     r9d, eax; char *
0x1800338fb  lea     r8, aOnecoreuapNetU_0; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180033902  mov     edx, 5E9h; void *
0x180033907  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003390c  nop
0x18003390d  lea     rcx, [rsp+0E8h+var_98]
0x180033912  call    ??1?$unique_ptr@UIWlanNotificationList@Internal@UX@Networking@Windows@@U?$default_delete@UIWlanNotificationList@Internal@UX@Networking@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Networking::UX::Internal::IWlanNotificationList>::~unique_ptr<Windows::Networking::UX::Internal::IWlanNotificationList>(void)
0x180033917  nop
0x180033918  lea     rcx, [rsp+0E8h+var_80]
0x18003391d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033922  nop
0x180033923  lea     rcx, [rsp+0E8h+var_88]
0x180033928  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18003392d  mov     eax, esi
0x18003392f  jmp     loc_180033B47
0x180033934  mov     rax, [rsp+0E8h+var_98]
0x180033939  mov     [rsp+0E8h+var_98], 0
0x180033942  mov     [rsp+0E8h+var_90], rax
0x180033947  mov     rax, [rdi]
0x18003394a  mov     r9, [rbx+28h]
0x18003394e  mov     r8d, [rbx+24h]
0x180033952  lea     rdx, [rsp+0E8h+var_90]
0x180033957  mov     rcx, rdi
0x18003395a  mov     rax, [rax+18h]
0x18003395e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033963  jmp     loc_180033A2D
0x180033968  lea     rcx, [rsp+0E8h+var_80]
0x18003396d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180033972  lea     rcx, [rsp+0E8h+var_98]
0x180033977  mov     [rsp+0E8h+var_A0], rcx
0x18003397c  mov     [rsp+0E8h+var_A8], 0
0x180033985  mov     [rsp+0E8h+var_B0], 0
0x18003398a  mov     [rsp+0E8h+var_B8], rax
0x18003398f  lea     rax, [rsp+0E8h+var_50]
0x180033997  mov     [rsp+0E8h+var_C0], rax
0x18003399c  lea     rax, [rsp+0E8h+var_60]
0x1800339a4  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x1800339a9  xor     r9d, r9d
0x1800339ac  lea     r8, ?sc_rgConnectCompleteFlowEvents@CAccessPointHelper@Internal@UX@Networking@Windows@@0QBUCONNECTION_FLOW_EVENT_ENTRY@12345@B; Windows::Networking::UX::Internal::CAccessPointHelper::CONNECTION_FLOW_EVENT_ENTRY const near * const Windows::Networking::UX::Internal::CAccessPointHelper::sc_rgConnectCompleteFlowEvents
0x1800339b3  lea     edx, [r9+2]
0x1800339b7  call    ?_CreateNotificationListForFlowEvents@CAccessPointHelper@Internal@UX@Networking@Windows@@AEAAJ_KPEBUCONNECTION_FLOW_EVENT_ENTRY@12345@KAEBU_GUID@@AEBU_DOT11_SSID@@PEBG_N4AEAV?$unique_ptr@UIWlanNotificationList@Internal@UX@Networking@Windows@@U?$default_delete@UIWlanNotificationList@Internal@UX@Networking@Windows@@@std@@@std@@@Z; Windows::Networking::UX::Internal::CAccessPointHelper::_CreateNotificationListForFlowEvents(unsigned __int64,Windows::Networking::UX::Internal::CAccessPointHelper::CONNECTION_FLOW_EVENT_ENTRY const *,ulong,_GUID const &,_DOT11_SSID const &,ushort const *,bool,ushort const *,std::unique_ptr<Windows::Networking::UX::Internal::IWlanNotificationList> &)
0x1800339bc  mov     ebx, eax
0x1800339be  test    eax, eax
0x1800339c0  jns     short loc_180033A06
0x1800339c2  mov     rcx, [rsp+0E8h]; this
0x1800339ca  mov     r9d, eax; char *
0x1800339cd  lea     r8, aOnecoreuapNetU_0; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x1800339d4  mov     edx, 5D5h; void *
0x1800339d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800339de  nop
0x1800339df  lea     rcx, [rsp+0E8h+var_98]
0x1800339e4  call    ??1?$unique_ptr@UIWlanNotificationList@Internal@UX@Networking@Windows@@U?$default_delete@UIWlanNotificationList@Internal@UX@Networking@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Networking::UX::Internal::IWlanNotificationList>::~unique_ptr<Windows::Networking::UX::Internal::IWlanNotificationList>(void)
0x1800339e9  nop
0x1800339ea  lea     rcx, [rsp+0E8h+var_80]
0x1800339ef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800339f4  nop
0x1800339f5  lea     rcx, [rsp+0E8h+var_88]
0x1800339fa  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800339ff  mov     eax, ebx
0x180033a01  jmp     loc_180033B47
0x180033a06  mov     rax, [rsp+0E8h+var_98]
0x180033a0b  mov     [rsp+0E8h+var_98], 0
0x180033a14  mov     [rsp+0E8h+var_90], rax
0x180033a19  mov     rax, [rdi]
0x180033a1c  lea     rdx, [rsp+0E8h+var_90]
0x180033a21  mov     rcx, rdi
0x180033a24  mov     rax, [rax+10h]
0x180033a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a2d  jmp     loc_180033AF4
0x180033a32  lea     rcx, [rsp+0E8h+var_80]
0x180033a37  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180033a3c  lea     rcx, [rsp+0E8h+var_98]
0x180033a41  mov     [rsp+0E8h+var_A0], rcx
0x180033a46  mov     [rsp+0E8h+var_A8], 0
0x180033a4f  mov     [rsp+0E8h+var_B0], 0
0x180033a54  mov     [rsp+0E8h+var_B8], rax
0x180033a59  lea     rax, [rsp+0E8h+var_50]
0x180033a61  mov     [rsp+0E8h+var_C0], rax
0x180033a66  lea     rax, [rsp+0E8h+var_60]
0x180033a6e  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x180033a73  xor     r9d, r9d
0x180033a76  lea     r8, ?sc_rgConnectStartFlowEvents@CAccessPointHelper@Internal@UX@Networking@Windows@@0QBUCONNECTION_FLOW_EVENT_ENTRY@12345@B; Windows::Networking::UX::Internal::CAccessPointHelper::CONNECTION_FLOW_EVENT_ENTRY const near * const Windows::Networking::UX::Internal::CAccessPointHelper::sc_rgConnectStartFlowEvents
0x180033a7d  lea     edx, [r9+4]
0x180033a81  call    ?_CreateNotificationListForFlowEvents@CAccessPointHelper@Internal@UX@Networking@Windows@@AEAAJ_KPEBUCONNECTION_FLOW_EVENT_ENTRY@12345@KAEBU_GUID@@AEBU_DOT11_SSID@@PEBG_N4AEAV?$unique_ptr@UIWlanNotificationList@Internal@UX@Networking@Windows@@U?$default_delete@UIWlanNotificationList@Internal@UX@Networking@Windows@@@std@@@std@@@Z; Windows::Networking::UX::Internal::CAccessPointHelper::_CreateNotificationListForFlowEvents(unsigned __int64,Windows::Networking::UX::Internal::CAccessPointHelper::CONNECTION_FLOW_EVENT_ENTRY const *,ulong,_GUID const &,_DOT11_SSID const &,ushort const *,bool,ushort const *,std::unique_ptr<Windows::Networking::UX::Internal::IWlanNotificationList> &)
0x180033a86  mov     ebx, eax
0x180033a88  test    eax, eax
0x180033a8a  jns     short loc_180033ACD
0x180033a8c  mov     rcx, [rsp+0E8h]; this
0x180033a94  mov     r9d, eax; char *
0x180033a97  lea     r8, aOnecoreuapNetU_0; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180033a9e  mov     edx, 5C8h; void *
0x180033aa3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033aa8  nop
0x180033aa9  lea     rcx, [rsp+0E8h+var_98]
0x180033aae  call    ??1?$unique_ptr@UIWlanNotificationList@Internal@UX@Networking@Windows@@U?$default_delete@UIWlanNotificationList@Internal@UX@Networking@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Networking::UX::Internal::IWlanNotificationList>::~unique_ptr<Windows::Networking::UX::Internal::IWlanNotificationList>(void)
0x180033ab3  nop
0x180033ab4  lea     rcx, [rsp+0E8h+var_80]
0x180033ab9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033abe  nop
0x180033abf  lea     rcx, [rsp+0E8h+var_88]
0x180033ac4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180033ac9  mov     eax, ebx
0x180033acb  jmp     short loc_180033B47
0x180033acd  mov     rax, [rsp+0E8h+var_98]
0x180033ad2  mov     [rsp+0E8h+var_98], 0
0x180033adb  mov     [rsp+0E8h+var_90], rax
0x180033ae0  mov     rax, [rdi]
0x180033ae3  lea     rdx, [rsp+0E8h+var_90]
0x180033ae8  mov     rcx, rdi
0x180033aeb  mov     rax, [rax+8]
0x180033aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033af4  mov     rcx, cs:WPP_GLOBAL_Control
0x180033afb  cmp     rcx, r15
0x180033afe  jz      short loc_180033B1F
0x180033b00  test    byte ptr [rcx+1Ch], 40h
0x180033b04  jz      short loc_180033B1F
0x180033b06  mov     edx, 8Eh
0x180033b0b  xor     r9d, r9d
0x180033b0e  lea     r8, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x180033b15  mov     rcx, [rcx+10h]
0x180033b19  call    WPP_SF_d
0x180033b1e  nop
0x180033b1f  lea     rcx, [rsp+0E8h+var_98]
0x180033b24  call    ??1?$unique_ptr@UIWlanNotificationList@Internal@UX@Networking@Windows@@U?$default_delete@UIWlanNotificationList@Internal@UX@Networking@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Networking::UX::Internal::IWlanNotificationList>::~unique_ptr<Windows::Networking::UX::Internal::IWlanNotificationList>(void)
0x180033b29  nop
0x180033b2a  lea     rcx, [rsp+0E8h+var_80]
0x180033b2f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033b34  nop
0x180033b35  lea     rcx, [rsp+0E8h+var_88]
0x180033b3a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180033b3f  xor     eax, eax
0x180033b41  jmp     short loc_180033B47
0x180033b43  mov     eax, dword ptr [rsp+0E8h+var_98]
0x180033b47  mov     rcx, [rsp+0E8h+var_28]
0x180033b4f  xor     rcx, rsp; StackCookie
0x180033b52  call    __security_check_cookie
0x180033b57  mov     rbx, [rsp+0E8h+arg_0]
0x180033b5f  add     rsp, 0D0h
0x180033b66  pop     r15
0x180033b68  pop     rdi
0x180033b69  pop     rsi
0x180033b6a  retn
```
