# CLocationGnssAdapter::OnGnssPnPEvent(int,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>)

- ea: `0x1800dde30`
- end: `0x1800de6a5`
- name: `?OnGnssPnPEvent@CLocationGnssAdapter@@UEAAJHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `2165`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `28`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800036a8`
- `0x180003c08`
- `0x18000dc00`
- `0x180012398`
- `0x180013660`
- `0x180019704`
- `0x180020c64`
- `0x180021a4c`
- `0x18003a940`
- `0x180048a04`
- `0x18004c784`
- `0x180056a7c`
- `0x18006807c`
- `0x18009d8a0`
- `0x1800a98c0`
- `0x1800aa5ac`
- `0x1800d5d38`
- `0x1800da144`
- `0x1800da4a8`
- `0x1800db310`
- `0x1800dc880`
- `0x1800dc8ec`
- `0x1800dde30`
- `0x1800df2bc`
- `0x1800df99c`
- `0x1800e179c`
- `0x1800e5c80`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800de3b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800de547`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800de65e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800de3b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800de547`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800de65e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ddea2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800de3c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800de558`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ddea2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800de3c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800de558`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800de05a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800de2f9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800de32b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800de05a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800de2f9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800de32b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de511`

## string_xrefs

- `0x1800de259`: `CLocationGnssAdapter::FinalConstruct: incompatible version, adapter=%u, driver= %u`
- `0x1800de590`: `DriverPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CLocationGnssAdapter::OnGnssPnPEvent(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  char v6; // r13
  struct _RTL_CRITICAL_SECTION *v7; // r12
  CLocationGnssAdapter *v8; // r15
  int *v9; // rdi
  signed int GnssDriverInstance; // ebx
  int *v11; // r14
  struct CGnssDriver **v12; // r12
  _OWORD *v13; // rax
  char *v14; // rcx
  __int64 v15; // rdx
  _OWORD *v16; // rcx
  char *v17; // rax
  __int64 v18; // rdx
  HANDLE EventW; // rax
  int v20; // eax
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // r10
  _DWORD *v26; // r15
  int v27; // r13d
  HANDLE v28; // rax
  HANDLE v29; // rax
  int v30; // esi
  CLocationGnssAdapter *v31; // rdi
  __int64 v32; // rcx
  signed int LastError; // eax
  __int64 v34; // rdx
  __int64 v35; // rax
  _BYTE *v36; // r9
  int v37; // r8d
  int v38; // edx
  __int64 v39; // rdx
  __int64 v40; // r10
  int v41; // ecx
  int v42; // r8d
  int v43; // r9d
  int v45; // [rsp+20h] [rbp-E0h]
  char *v46; // [rsp+28h] [rbp-D8h]
  __int64 *v47; // [rsp+30h] [rbp-D0h]
  int v48; // [rsp+50h] [rbp-B0h] BYREF
  CLocationGnssAdapter *v49; // [rsp+58h] [rbp-A8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp-A0h]
  _QWORD v51[2]; // [rsp+68h] [rbp-98h] BYREF
  struct IUnknown *v52; // [rsp+78h] [rbp-88h] BYREF
  __int64 v53; // [rsp+80h] [rbp-80h] BYREF
  __int64 v54; // [rsp+88h] [rbp-78h]
  __int64 v55; // [rsp+90h] [rbp-70h]
  __int64 v56; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v57[2]; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v58[4]; // [rsp+B0h] [rbp-50h] BYREF
  char v59[8]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v60; // [rsp+C8h] [rbp-38h]
  __int128 v61; // [rsp+D8h] [rbp-28h]
  __int128 v62; // [rsp+E8h] [rbp-18h]
  __int16 v63; // [rsp+F8h] [rbp-8h]
  __int64 v64; // [rsp+FAh] [rbp-6h]
  __int128 v65; // [rsp+102h] [rbp+2h]
  _BYTE v66[26]; // [rsp+112h] [rbp+12h]
  __int64 v67; // [rsp+12Ch] [rbp+2Ch]
  __int128 v68; // [rsp+134h] [rbp+34h]
  __int128 v69; // [rsp+144h] [rbp+44h]
  _BYTE v70[528]; // [rsp+360h] [rbp+260h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5B8h] [rbp+4B8h]

  v54 = a4;
  v53 = a3;
  v48 = a2;
  v57[1] = a4;
  v52 = 0;
  v58[0] = LocationHelper::CreateLocationComponent<ILocationPalMisc>(a1, &v52);
  v6 = CLocationGnssAdapter::OnGnssPnPEvent_::_2_::_lambda_1_::operator()();
  v7 = (struct _RTL_CRITICAL_SECTION *)(a1 + 40);
  lpCriticalSection = (LPCRITICAL_SECTION)(a1 + 40);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  v8 = (CLocationGnssAdapter *)(a1 - 8);
  v49 = (CLocationGnssAdapter *)(a1 - 8);
  v9 = (int *)(a1 + 1560);
  if ( !*(_DWORD *)(a1 - 8 + 200) )
  {
    v11 = (int *)(a1 + 1560);
    if ( a2 )
    {
      if ( !*v9 )
      {
        std::shared_ptr<GEOFENCE_DISTANCE>::shared_ptr<GEOFENCE_DISTANCE>(v51, v54);
        v12 = (struct CGnssDriver **)(a1 + 1464);
        GnssDriverInstance = CreateGnssDriverInstance(a1 - 8, v51, a1 + 1464);
        if ( GnssDriverInstance < 0 )
        {
LABEL_41:
          v7 = lpCriticalSection;
          goto LABEL_42;
        }
        memset_0(v59, 0, 0x25Cu);
        v13 = (_OWORD *)(a1 + 196);
        v14 = v59;
        v15 = 4;
        do
        {
          *v13 = *(_OWORD *)v14;
          v13[1] = *((_OWORD *)v14 + 1);
          v13[2] = *((_OWORD *)v14 + 2);
          v13[3] = *((_OWORD *)v14 + 3);
          v13[4] = *((_OWORD *)v14 + 4);
          v13[5] = *((_OWORD *)v14 + 5);
          v13[6] = *((_OWORD *)v14 + 6);
          v13[7] = *((_OWORD *)v14 + 7);
          v13 += 8;
          v14 += 128;
          --v15;
        }
        while ( v15 );
        *v13 = *(_OWORD *)v14;
        v13[1] = *((_OWORD *)v14 + 1);
        v13[2] = *((_OWORD *)v14 + 2);
        v13[3] = *((_OWORD *)v14 + 3);
        v13[4] = *((_OWORD *)v14 + 4);
        *(_OWORD *)((char *)v13 + 76) = *(_OWORD *)(v14 + 76);
        memset_0(v59, 0, 0x214u);
        v16 = (_OWORD *)(a1 + 800);
        v17 = v59;
        v18 = 4;
        do
        {
          *v16 = *(_OWORD *)v17;
          v16[1] = *((_OWORD *)v17 + 1);
          v16[2] = *((_OWORD *)v17 + 2);
          v16[3] = *((_OWORD *)v17 + 3);
          v16[4] = *((_OWORD *)v17 + 4);
          v16[5] = *((_OWORD *)v17 + 5);
          v16[6] = *((_OWORD *)v17 + 6);
          v16[7] = *((_OWORD *)v17 + 7);
          v16 += 8;
          v17 += 128;
          --v18;
        }
        while ( v18 );
        *v16 = *(_OWORD *)v17;
        *((_DWORD *)v16 + 4) = *((_DWORD *)v17 + 4);
        *(_DWORD *)(a1 + 800) = 532;
        *(_DWORD *)(a1 + 804) = 6;
        *(_DWORD *)(a1 + 808) = 1;
        *(_DWORD *)(a1 + 812) = 127;
        EventW = CreateEventW(0, 1, 0, 0);
        _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
          a1 + 168,
          EventW);
        if ( *(_QWORD *)(a1 + 168) )
        {
          v20 = (**(__int64 (__fastcall ***)(struct CGnssDriver *, __int64))*v12)(*v12, a1 + 800);
          if ( v20 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x758,
              (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\gnssadapter\\locationgnssadapter.cpp",
              (const char *)(unsigned int)v20,
              v45);
          GnssDriverInstance = (*(__int64 (__fastcall **)(struct CGnssDriver *, __int64))(*(_QWORD *)*v12 + 8LL))(
                                 *v12,
                                 a1 + 196);
          if ( GnssDriverInstance < 0 )
            goto LABEL_39;
          if ( v6 )
          {
            *(_DWORD *)(a1 + 252) = 0;
            if ( (unsigned int)dword_1801DDF30 > 4 )
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                &dword_1801DDF30,
                &byte_1801AFB7F);
          }
          memset_0(v59, 0, 0x294u);
          v21 = (*(__int64 (__fastcall **)(struct CGnssDriver *, char *))(*(_QWORD *)*v12 + 16LL))(*v12, v59);
          if ( v21 < 0 )
          {
            v26 = (_DWORD *)(a1 + 200);
            if ( *(_DWORD *)(a1 + 200) >= 3u )
            {
              LODWORD(v46) = *(_DWORD *)(a1 + 200);
              wil::details::in1diag3::Log_IfFailedMsg(
                retaddr,
                (void *)0x783,
                (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\gnssadapter\\locationgnssadapter.cpp",
                (const char *)(unsigned int)v21,
                (int)"GetChipsetInfo failed on GnssDriver with version %u",
                v46);
            }
          }
          else
          {
            *(_OWORD *)(a1 + 1584) = v60;
            *(_OWORD *)(a1 + 1600) = v61;
            *(_OWORD *)(a1 + 1616) = v62;
            *(_WORD *)(a1 + 1632) = v63;
            *(_QWORD *)(a1 + 1636) = v64;
            *(_OWORD *)(a1 + 1644) = v65;
            *(_OWORD *)(a1 + 1660) = *(_OWORD *)v66;
            *(_OWORD *)(a1 + 1670) = *(_OWORD *)&v66[10];
            *(_QWORD *)(a1 + 1688) = v67;
            *(_OWORD *)(a1 + 1696) = v68;
            *(_OWORD *)(a1 + 1712) = v69;
            if ( (unsigned int)dword_1801DDF30 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801DDF30, 0x400000000000LL) )
            {
              v55 = 0x1000000;
              v56 = v25;
              v57[0] = v24;
              v51[0] = v23;
              v47 = &v56;
              v46 = (char *)v57;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
                v22,
                &dword_1801AF7AC);
            }
            v26 = (_DWORD *)(a1 + 200);
          }
          if ( *v26 > *(_DWORD *)(a1 + 804) )
          {
            LODWORD(v47) = *v26;
            LODWORD(v46) = *(_DWORD *)(a1 + 804);
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0x78F,
              (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\gnssadapter\\locationgnssadapter.cpp",
              (const char *)0x8000FFFFLL,
              (int)"CLocationGnssAdapter::FinalConstruct: incompatible version, adapter=%u, driver= %u",
              v46,
              v47);
          }
          (*(void (__fastcall **)(struct CGnssDriver *))(*(_QWORD *)*v12 + 136LL))(*v12);
          if ( *(_DWORD *)(a1 + 212) )
          {
            v27 = 0;
            do
            {
              GnssDriverInstance = (*(__int64 (__fastcall **)(struct CGnssDriver *))(*(_QWORD *)*v12 + 104LL))(*v12);
              v9 = (int *)(a1 + 1560);
              if ( GnssDriverInstance < 0 )
                goto LABEL_40;
            }
            while ( (unsigned int)++v27 < 3 );
          }
          if ( *v26 < 2u || (*(_BYTE *)(a1 + 252) & 3) != 3 )
          {
LABEL_45:
            if ( (*(_DWORD *)(a1 + 264) || *(_DWORD *)(a1 + 276) || *(_DWORD *)(a1 + 272) || *(_DWORD *)(a1 + 268))
              && (int)CreateSuplHandler(*v12, (struct ISuplHandler **)(a1 + 1488)) >= 0 )
            {
              if ( v58[0] >= 0 )
              {
                if ( *(struct IUnknown **)(a1 + 1480) != v52 )
                  ATL::AtlComPtrAssign((struct IUnknown **)(a1 + 1480), v52);
                GnssDriverInstance = (*(__int64 (__fastcall **)(struct CGnssDriver *))(*(_QWORD *)*v12 + 120LL))(*v12);
                if ( GnssDriverInstance < 0 )
                  goto LABEL_39;
              }
              if ( *v26 >= 3u )
                (*(void (__fastcall **)(struct CGnssDriver *))(*(_QWORD *)*v12 + 208LL))(*v12);
            }
            GnssDriverInstance = (*(__int64 (__fastcall **)(struct CGnssDriver *, __int64, _QWORD))(*(_QWORD *)*v12
                                                                                                  + 32LL))(
                                   *v12,
                                   1,
                                   *(unsigned int *)(a1 + 1564));
            if ( GnssDriverInstance < 0 )
            {
LABEL_39:
              v9 = (int *)(a1 + 1560);
LABEL_40:
              v8 = v49;
              goto LABEL_41;
            }
            v32 = *(_QWORD *)(a1 + 1488);
            if ( v32 )
              (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v32 + 24LL))(v32, *(unsigned int *)(a1 + 1564));
            *v11 = 1;
            if ( *(_BYTE *)(a1 + 1749) )
            {
              v31 = (CLocationGnssAdapter *)(a1 - 8);
              CLocationGnssAdapter::TryStartBreadcrumbingImpl((CLocationGnssAdapter *)(a1 - 8));
            }
            else
            {
              v31 = v49;
            }
            v58[0] = 0;
            if ( (int)LocationRegistryHelper::GetSettingValueDWORD(80, L"CurrentPeriodicSessionId", 0, v58) >= 0
              && v58[0] )
            {
              (*(void (__fastcall **)(struct CGnssDriver *))(*(_QWORD *)*v12 + 88LL))(*v12);
              LocationRegistryHelper::SetSettingValueDWORD(0x50u, L"CurrentPeriodicSessionId", 0);
            }
LABEL_73:
            v30 = v48;
            goto LABEL_74;
          }
          *(_DWORD *)(a1 + 1544) = 1;
          if ( *(_QWORD *)(a1 + 1528)
            || (v28 = CreateEventW(0, 0, 0, 0),
                _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
                  a1 + 1528,
                  v28),
                *(_QWORD *)(a1 + 1528)) )
          {
            if ( *(_QWORD *)(a1 + 1536)
              || (v29 = CreateEventW(0, 0, 0, 0),
                  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
                    a1 + 1536,
                    v29),
                  *(_QWORD *)(a1 + 1536)) )
            {
              GnssDriverInstance = (*(__int64 (__fastcall **)(struct CGnssDriver *))(*(_QWORD *)*v12 + 184LL))(*v12);
              if ( GnssDriverInstance < 0 )
                goto LABEL_39;
              GnssDriverInstance = (*(__int64 (__fastcall **)(struct CGnssDriver *))(*(_QWORD *)*v12 + 192LL))(*v12);
              if ( GnssDriverInstance < 0 )
                goto LABEL_39;
              GnssDriverInstance = (*(__int64 (__fastcall **)(struct CGnssDriver *, __int64))(*(_QWORD *)*v12 + 24LL))(
                                     *v12,
                                     16);
              if ( GnssDriverInstance < 0 )
                goto LABEL_39;
              goto LABEL_45;
            }
          }
        }
        LastError = GetLastError();
        GnssDriverInstance = LastError;
        if ( LastError > 0 )
          GnssDriverInstance = (unsigned __int16)LastError | 0x80070000;
        v9 = (int *)(a1 + 1560);
        if ( GnssDriverInstance < 0 )
          goto LABEL_40;
        v31 = v49;
        goto LABEL_73;
      }
      GnssDriverInstance = 0;
    }
    else
    {
      GnssDriverInstance = 0;
      if ( *v9 )
      {
        *v9 = 0;
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
        CLocationGnssAdapter::CleanupOutstandingConnections((CLocationGnssAdapter *)(a1 - 8));
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
      }
    }
    v31 = (CLocationGnssAdapter *)(a1 - 8);
    goto LABEL_73;
  }
  GnssDriverInstance = -2147467260;
LABEL_42:
  v30 = v48;
  if ( v48 )
  {
    *v9 = 0;
    LeaveCriticalSection(v7);
    CLocationGnssAdapter::CleanupOutstandingConnections(v8);
    EnterCriticalSection(v7);
  }
  v11 = v9;
  v31 = v49;
LABEL_74:
  v51[0] = v31;
  CLocationGnssAdapter::OnGnssPnPEvent_::_2_::_lambda_2_::operator()(v51);
  CLocationWnfNotify::NotifyCustomEvent<int>(*((_QWORD *)v31 + 197), v11);
  LocationRegistryHelper::GetSettingValueString(80, L"DriverPath", v70, 260);
  v35 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v53, v34);
  v36 = &v70[-v35];
  do
  {
    v37 = *(unsigned __int16 *)&v36[v35];
    v38 = *(unsigned __int16 *)v35 - v37;
    if ( v38 )
      break;
    v35 += 2;
  }
  while ( v37 );
  if ( v38 && (unsigned int)dword_1801DDF30 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801DDF30, 0x400000000000LL) )
  {
    v53 = 0x1000000;
    v58[0] = GnssDriverInstance;
    v48 = *v11;
    v51[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v40, v39);
    LODWORD(v49) = v30;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v41,
      (unsigned int)byte_1801AF60B,
      v42,
      v43,
      (__int64)&v49,
      (__int64)v51,
      (__int64)&v48,
      (__int64)v58,
      (__int64)&v53);
  }
  LeaveCriticalSection(lpCriticalSection);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
  std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(v54);
  return (unsigned int)GnssDriverInstance;
}

```

## disassembly

```asm
0x1800dde30  mov     [rsp-8+arg_8], rbx
0x1800dde35  push    rbp
0x1800dde36  push    rsi
0x1800dde37  push    rdi
0x1800dde38  push    r12
0x1800dde3a  push    r13
0x1800dde3c  push    r14
0x1800dde3e  push    r15
0x1800dde40  lea     rbp, [rsp-480h]
0x1800dde48  sub     rsp, 580h
0x1800dde4f  mov     rax, cs:__security_cookie
0x1800dde56  xor     rax, rsp
0x1800dde59  mov     [rbp+4B0h+var_40], rax
0x1800dde60  mov     rax, r9
0x1800dde63  mov     [rbp+4B0h+var_528], rax
0x1800dde67  mov     [rbp+4B0h+var_530], r8
0x1800dde6b  mov     ebx, edx
0x1800dde6d  mov     [rsp+5B0h+var_560], edx
0x1800dde71  mov     rsi, rcx
0x1800dde74  mov     [rbp+4B0h+var_508], rax
0x1800dde78  mov     [rsp+5B0h+var_538], 0
0x1800dde81  lea     rdx, [rsp+5B0h+var_538]
0x1800dde86  call    ??$CreateLocationComponent@UILocationPalMisc@@@LocationHelper@@SAJW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@PEAPEAUILocationPalMisc@@@Z; LocationHelper::CreateLocationComponent<ILocationPalMisc>(__MIDL___MIDL_itf_locationframework_0000_0000_0001,ILocationPalMisc * *)
0x1800dde8b  mov     [rbp+4B0h+var_500], eax
0x1800dde8e  call    _CLocationGnssAdapter__OnGnssPnPEvent____2____lambda_1___operator__
0x1800dde93  mov     r13b, al
0x1800dde96  lea     r12, [rsi+28h]
0x1800dde9a  mov     [rsp+5B0h+lpCriticalSection], r12
0x1800dde9f  mov     rcx, r12; lpCriticalSection
0x1800ddea2  call    cs:__imp_EnterCriticalSection
0x1800ddea8  lea     r15, [rsi-8]
0x1800ddeac  mov     [rsp+5B0h+var_558], r15
0x1800ddeb1  lea     rdi, [rsi+618h]
0x1800ddeb8  cmp     dword ptr [r15+0C8h], 0
0x1800ddec0  jz      short loc_1800DDECC
0x1800ddec2  mov     ebx, 80004004h
0x1800ddec7  jmp     loc_1800DE3A0
0x1800ddecc  mov     r14, rdi
0x1800ddecf  test    ebx, ebx
0x1800dded1  jz      loc_1800DE53C
0x1800dded7  cmp     dword ptr [rdi], 0
0x1800ddeda  jnz     loc_1800DE538
0x1800ddee0  mov     rdx, [rbp+4B0h+var_528]
0x1800ddee4  lea     rcx, [rsp+5B0h+var_548]
0x1800ddee9  call    ??0?$shared_ptr@UGEOFENCE_DISTANCE@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<GEOFENCE_DISTANCE>::shared_ptr<GEOFENCE_DISTANCE>(std::shared_ptr<GEOFENCE_DISTANCE> const &)
0x1800ddeee  lea     r12, [rsi+5B8h]
0x1800ddef5  mov     r8, r12
0x1800ddef8  lea     rdx, [rsp+5B0h+var_548]
0x1800ddefd  mov     rcx, r15
0x1800ddf00  call    ?CreateGnssDriverInstance@@YAJPEAVGnssDriverListener@@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@PEAPEAVCGnssDriver@@@Z; CreateGnssDriverInstance(GnssDriverListener *,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>,CGnssDriver * *)
0x1800ddf05  mov     ebx, eax
0x1800ddf07  test    eax, eax
0x1800ddf09  js      loc_1800DE39B
0x1800ddf0f  xor     edx, edx; Val
0x1800ddf11  mov     r8d, 25Ch; Size
0x1800ddf17  lea     rcx, [rbp+4B0h+var_4F0]; void *
0x1800ddf1b  call    memset_0
0x1800ddf20  lea     r15, [rsi+0C4h]
0x1800ddf27  mov     rax, r15
0x1800ddf2a  lea     rcx, [rbp+4B0h+var_4F0]
0x1800ddf2e  mov     edx, 4
0x1800ddf33  lea     ebx, [rdx+7Ch]
0x1800ddf36  movups  xmm0, xmmword ptr [rcx]
0x1800ddf39  movups  xmmword ptr [rax], xmm0
0x1800ddf3c  movups  xmm1, xmmword ptr [rcx+10h]
0x1800ddf40  movups  xmmword ptr [rax+10h], xmm1
0x1800ddf44  movups  xmm0, xmmword ptr [rcx+20h]
0x1800ddf48  movups  xmmword ptr [rax+20h], xmm0
0x1800ddf4c  movups  xmm1, xmmword ptr [rcx+30h]
0x1800ddf50  movups  xmmword ptr [rax+30h], xmm1
0x1800ddf54  movups  xmm0, xmmword ptr [rcx+40h]
0x1800ddf58  movups  xmmword ptr [rax+40h], xmm0
0x1800ddf5c  movups  xmm1, xmmword ptr [rcx+50h]
0x1800ddf60  movups  xmmword ptr [rax+50h], xmm1
0x1800ddf64  movups  xmm0, xmmword ptr [rcx+60h]
0x1800ddf68  movups  xmmword ptr [rax+60h], xmm0
0x1800ddf6c  movups  xmm1, xmmword ptr [rcx+70h]
0x1800ddf70  movups  xmmword ptr [rax+70h], xmm1
0x1800ddf74  add     rax, rbx
0x1800ddf77  add     rcx, rbx
0x1800ddf7a  sub     rdx, 1; Val
0x1800ddf7e  jnz     short loc_1800DDF36
0x1800ddf80  movups  xmm0, xmmword ptr [rcx]
0x1800ddf83  movups  xmmword ptr [rax], xmm0
0x1800ddf86  movups  xmm1, xmmword ptr [rcx+10h]
0x1800ddf8a  movups  xmmword ptr [rax+10h], xmm1
0x1800ddf8e  movups  xmm0, xmmword ptr [rcx+20h]
0x1800ddf92  movups  xmmword ptr [rax+20h], xmm0
0x1800ddf96  movups  xmm1, xmmword ptr [rcx+30h]
0x1800ddf9a  movups  xmmword ptr [rax+30h], xmm1
0x1800ddf9e  movups  xmm0, xmmword ptr [rcx+40h]
0x1800ddfa2  movups  xmmword ptr [rax+40h], xmm0
0x1800ddfa6  movups  xmm1, xmmword ptr [rcx+4Ch]
0x1800ddfaa  movups  xmmword ptr [rax+4Ch], xmm1
0x1800ddfae  mov     r8d, 214h; Size
0x1800ddfb4  lea     rcx, [rbp+4B0h+var_4F0]; void *
0x1800ddfb8  call    memset_0
0x1800ddfbd  lea     rdi, [rsi+320h]
0x1800ddfc4  mov     rcx, rdi
0x1800ddfc7  lea     rax, [rbp+4B0h+var_4F0]
0x1800ddfcb  mov     edx, 4
0x1800ddfd0  movups  xmm0, xmmword ptr [rax]
0x1800ddfd3  movups  xmmword ptr [rcx], xmm0
0x1800ddfd6  movups  xmm1, xmmword ptr [rax+10h]
0x1800ddfda  movups  xmmword ptr [rcx+10h], xmm1
0x1800ddfde  movups  xmm0, xmmword ptr [rax+20h]
0x1800ddfe2  movups  xmmword ptr [rcx+20h], xmm0
0x1800ddfe6  movups  xmm1, xmmword ptr [rax+30h]
0x1800ddfea  movups  xmmword ptr [rcx+30h], xmm1
0x1800ddfee  movups  xmm0, xmmword ptr [rax+40h]
0x1800ddff2  movups  xmmword ptr [rcx+40h], xmm0
0x1800ddff6  movups  xmm1, xmmword ptr [rax+50h]
0x1800ddffa  movups  xmmword ptr [rcx+50h], xmm1
0x1800ddffe  movups  xmm0, xmmword ptr [rax+60h]
0x1800de002  movups  xmmword ptr [rcx+60h], xmm0
0x1800de006  movups  xmm1, xmmword ptr [rax+70h]
0x1800de00a  movups  xmmword ptr [rcx+70h], xmm1
0x1800de00e  add     rcx, rbx
0x1800de011  add     rax, rbx
0x1800de014  sub     rdx, 1
0x1800de018  jnz     short loc_1800DDFD0
0x1800de01a  movups  xmm0, xmmword ptr [rax]
0x1800de01d  movups  xmmword ptr [rcx], xmm0
0x1800de020  mov     eax, [rax+10h]
0x1800de023  mov     [rcx+10h], eax
0x1800de026  mov     dword ptr [rdi], 214h
0x1800de02c  mov     dword ptr [rsi+324h], 6
0x1800de036  lea     eax, [rdx+1]
0x1800de039  mov     [rsi+328h], eax
0x1800de03f  mov     dword ptr [rsi+32Ch], 7Fh
0x1800de049  lea     rbx, [rsi+0A8h]
0x1800de050  xor     r9d, r9d; lpName
0x1800de053  xor     r8d, r8d; bInitialState
0x1800de056  mov     edx, eax; bManualReset
0x1800de058  xor     ecx, ecx; lpEventAttributes
0x1800de05a  call    cs:__imp_CreateEventW
0x1800de060  mov     rdx, rax
0x1800de063  mov     rcx, rbx
0x1800de066  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800de06b  cmp     qword ptr [rbx], 0
0x1800de06f  jz      loc_1800DE511
0x1800de075  mov     rcx, [r12]
0x1800de079  mov     rax, [rcx]
0x1800de07c  mov     rdx, rdi
0x1800de07f  mov     rax, [rax]
0x1800de082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de087  mov     rcx, [rbp+4B8h]; this
0x1800de08e  lea     rdi, aOnecoreuapDriv_2; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800de095  test    eax, eax
0x1800de097  jns     short loc_1800DE0A9
0x1800de099  mov     r9d, eax; char *
0x1800de09c  mov     r8, rdi; unsigned int
0x1800de09f  mov     edx, 758h; void *
0x1800de0a4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800de0a9  mov     rcx, [r12]
0x1800de0ad  mov     rax, [rcx]
0x1800de0b0  mov     rdx, r15
0x1800de0b3  mov     rax, [rax+8]
0x1800de0b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de0bc  mov     ebx, eax
0x1800de0be  test    eax, eax
0x1800de0c0  js      loc_1800DE393
0x1800de0c6  test    r13b, r13b
0x1800de0c9  jz      short loc_1800DE0F3
0x1800de0cb  mov     dword ptr [rsi+0FCh], 0
0x1800de0d5  mov     eax, cs:dword_1801DDF30
0x1800de0db  cmp     eax, 4
0x1800de0de  jbe     short loc_1800DE0F3
0x1800de0e0  lea     rdx, byte_1801AFB7F
0x1800de0e7  lea     rcx, dword_1801DDF30
0x1800de0ee  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800de0f3  xor     edx, edx; Val
0x1800de0f5  mov     r8d, 294h; Size
0x1800de0fb  lea     rcx, [rbp+4B0h+var_4F0]; void *
0x1800de0ff  call    memset_0
0x1800de104  mov     rcx, [r12]
0x1800de108  mov     rax, [rcx]
0x1800de10b  lea     rdx, [rbp+4B0h+var_4F0]
0x1800de10f  mov     rax, [rax+10h]
0x1800de113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de118  mov     r9d, eax; char *
0x1800de11b  test    eax, eax
0x1800de11d  js      loc_1800DE20A
0x1800de123  lea     r8, [rsi+630h]
0x1800de12a  movups  xmm0, [rbp+4B0h+var_4E8]
0x1800de12e  movups  xmmword ptr [r8], xmm0
0x1800de132  movups  xmm1, [rbp+4B0h+var_4D8]
0x1800de136  movups  xmmword ptr [r8+10h], xmm1
0x1800de13b  movups  xmm0, [rbp+4B0h+var_4C8]
0x1800de13f  movups  xmmword ptr [r8+20h], xmm0
0x1800de144  movzx   eax, [rbp+4B0h+var_4B8]
0x1800de148  mov     [r8+30h], ax
0x1800de14d  lea     r9, [rsi+664h]
0x1800de154  mov     rax, [rbp+4B0h+var_4B6]
0x1800de158  mov     [r9], rax
0x1800de15b  movups  xmm0, [rbp+4B0h+var_4AE]
0x1800de15f  movups  xmmword ptr [r9+8], xmm0
0x1800de164  movups  xmm1, xmmword ptr [rbp+4B0h+var_49E]
0x1800de168  movups  xmmword ptr [r9+18h], xmm1
0x1800de16d  movups  xmm0, xmmword ptr [rbp+4B0h+var_49E+0Ah]
0x1800de171  movups  xmmword ptr [r9+22h], xmm0
0x1800de176  lea     r10, [rsi+698h]
0x1800de17d  mov     rax, [rbp+4B0h+var_484]
0x1800de181  mov     [r10], rax
0x1800de184  movups  xmm0, [rbp+4B0h+var_47C]
0x1800de188  movups  xmmword ptr [r10+8], xmm0
0x1800de18d  movups  xmm1, [rbp+4B0h+var_46C]
0x1800de191  movups  xmmword ptr [r10+18h], xmm1
0x1800de196  mov     eax, cs:dword_1801DDF30
0x1800de19c  cmp     eax, 4
0x1800de19f  jbe     short loc_1800DE201
0x1800de1a1  mov     rdx, 400000000000h
0x1800de1ab  lea     rcx, dword_1801DDF30
0x1800de1b2  call    _tlgKeywordOn
0x1800de1b7  test    al, al
0x1800de1b9  jz      short loc_1800DE201
0x1800de1bb  mov     [rbp+4B0h+var_520], 1000000h
0x1800de1c3  mov     [rbp+4B0h+var_518], r10
0x1800de1c7  mov     [rbp+4B0h+var_510], r9
0x1800de1cb  mov     [rsp+5B0h+var_548], r8
0x1800de1d0  lea     rax, [rbp+4B0h+var_520]
0x1800de1d4  mov     [rsp+5B0h+var_578], rax
0x1800de1d9  lea     rax, [rbp+4B0h+var_518]
0x1800de1dd  mov     [rsp+5B0h+var_580], rax
0x1800de1e2  lea     rax, [rbp+4B0h+var_510]
0x1800de1e6  mov     [rsp+5B0h+var_588], rax
0x1800de1eb  lea     rax, [rsp+5B0h+var_548]
0x1800de1f0  mov     qword ptr [rsp+5B0h+var_590], rax
0x1800de1f5  lea     rdx, dword_1801AF7AC
0x1800de1fc  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1800de201  lea     r15, [rsi+0C8h]
0x1800de208  jmp     short loc_1800DE23D
0x1800de20a  lea     r15, [rsi+0C8h]
0x1800de211  mov     eax, [r15]
0x1800de214  cmp     eax, 3
0x1800de217  jb      short loc_1800DE23D
0x1800de219  mov     rcx, [rbp+4B8h]; this
0x1800de220  mov     dword ptr [rsp+5B0h+var_588], eax; char *
0x1800de224  lea     rax, aGetchipsetinfo; "GetChipsetInfo failed on GnssDriver wit"...
0x1800de22b  mov     qword ptr [rsp+5B0h+var_590], rax; int
0x1800de230  mov     r8, rdi; unsigned int
0x1800de233  mov     edx, 783h; void *
0x1800de238  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800de23d  mov     eax, [rsi+324h]
0x1800de243  mov     edx, [r15]
0x1800de246  cmp     edx, eax
0x1800de248  jbe     short loc_1800DE278
0x1800de24a  mov     rcx, [rbp+4B8h]; this
0x1800de251  mov     dword ptr [rsp+5B0h+var_580], edx
0x1800de255  mov     dword ptr [rsp+5B0h+var_588], eax; char *
0x1800de259  lea     rax, aClocationgnssa; "CLocationGnssAdapter::FinalConstruct: i"...
0x1800de260  mov     qword ptr [rsp+5B0h+var_590], rax; int
0x1800de265  mov     r9d, 8000FFFFh; char *
0x1800de26b  mov     r8, rdi; unsigned int
0x1800de26e  mov     edx, 78Fh; void *
0x1800de273  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800de278  mov     rcx, [r12]
0x1800de27c  mov     rax, [rcx]
0x1800de27f  mov     rax, [rax+88h]
0x1800de286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de28b  cmp     dword ptr [rsi+0D4h], 0
0x1800de292  jz      short loc_1800DE2BD
0x1800de294  xor     r13d, r13d
0x1800de297  mov     rcx, [r12]
0x1800de29b  mov     rax, [rcx]
0x1800de29e  mov     rax, [rax+68h]
0x1800de2a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de2a7  mov     ebx, eax
0x1800de2a9  mov     rdi, r14
0x1800de2ac  test    eax, eax
0x1800de2ae  js      loc_1800DE396
0x1800de2b4  inc     r13d
0x1800de2b7  cmp     r13d, 3
0x1800de2bb  jb      short loc_1800DE297
0x1800de2bd  cmp     dword ptr [r15], 2
0x1800de2c1  jb      loc_1800DE3D5
0x1800de2c7  mov     eax, [rsi+0FCh]
0x1800de2cd  and     eax, 3
0x1800de2d0  cmp     al, 3
0x1800de2d2  jnz     loc_1800DE3D5
0x1800de2d8  mov     dword ptr [rsi+608h], 1
0x1800de2e2  lea     rbx, [rsi+5F8h]
0x1800de2e9  cmp     qword ptr [rbx], 0
0x1800de2ed  jnz     short loc_1800DE314
0x1800de2ef  xor     r9d, r9d; lpName
0x1800de2f2  xor     r8d, r8d; bInitialState
0x1800de2f5  xor     edx, edx; bManualReset
0x1800de2f7  xor     ecx, ecx; lpEventAttributes
0x1800de2f9  call    cs:__imp_CreateEventW
0x1800de2ff  mov     rdx, rax
0x1800de302  mov     rcx, rbx
0x1800de305  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800de30a  cmp     qword ptr [rbx], 0
0x1800de30e  jz      loc_1800DE511
0x1800de314  lea     rbx, [rsi+600h]
0x1800de31b  cmp     qword ptr [rbx], 0
0x1800de31f  jnz     short loc_1800DE346
0x1800de321  xor     r9d, r9d; lpName
0x1800de324  xor     r8d, r8d; bInitialState
0x1800de327  xor     edx, edx; bManualReset
  ... truncated ...
```
