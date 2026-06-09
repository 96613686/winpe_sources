# WlanSyncTaskWlanToCDS::PushCloudChange<Windows::Data::WiFi::WiFiProfile>(WiFiCloudStoreTelemetry::WlanTriggeredSync &,wil::ActivityThreadWatcher &,void * const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_GUID const &,Windows::Internal::WiFiCloudStore::SyncNeededProfile const &,PushCloudChangeOptionFlags,ulong,ushort const *)

- ea: `0x180016ba4`
- end: `0x180017386`
- name: `??$PushCloudChange@UWiFiProfile@WiFi@Data@Windows@@@WlanSyncTaskWlanToCDS@@CA?AW4WiFiSyncAction@@AEAVWlanTriggeredSync@WiFiCloudStoreTelemetry@@AEAVActivityThreadWatcher@wil@@AEBQEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@AEBUSyncNeededProfile@WiFiCloudStore@Internal@Windows@@W4PushCloudChangeOptionFlags@@KPEBG@Z`
- size: `2018`
- prototype: `__int64 __fastcall(int, wil::ActivityThreadWatcher *, HANDLE *, _QWORD *, GUID *pInterfaceGuid, __int64 *, char, int, __int64)`
- caller_count: `2`
- callee_count: `30`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180035d7c`
- `0x180038310`

## callees

- `0x18000766c`
- `0x180007f90`
- `0x18000982c`
- `0x18000a710`
- `0x18000a944`
- `0x180010c8c`
- `0x180011560`
- `0x1800115a0`
- `0x180011690`
- `0x1800169bc`
- `0x180016ba4`
- `0x18001738c`
- `0x1800174a8`
- `0x1800174c0`
- `0x180017d2c`
- `0x180017de4`
- `0x180025308`
- `0x180025aa0`
- `0x180025b20`
- `0x180025c04`
- `0x180026bc8`
- `0x180027898`
- `0x18002794c`
- `0x18002a030`
- `0x18002aad0`
- `0x18002e2d0`
- `0x180031ce4`
- `0x180032d2c`
- `0x180033458`
- `0x1800365d8`

## import_xrefs

- `wlanapi!WlanGetProfile` at `0x180016edc`
- `wlanapi!WlanGetProfile` at `0x180016edc`
- `wlanapi!WlanFreeMemory` at `0x180016f1b`
- `wlanapi!WlanFreeMemory` at `0x18001708b`
- `wlanapi!WlanFreeMemory` at `0x180016f1b`
- `wlanapi!WlanFreeMemory` at `0x18001708b`
- `dusmapi!DusmQueryUserCost` at `0x180017174`
- `dusmapi!DusmQueryUserCost` at `0x180017174`

## string_xrefs

- `0x180016e7b`: `Profile name: %ws, Generation: %d, Local version: %llu, Cloud version: %llu, Local modified time: %llu, Cloud modified time: %llu, Attempting action: %u, Retry count: %lu`
- `0x180016ef0`: `onecoreuap\net\wlan\cloudstore\provider\lib\WlanSyncTaskWlanToCDS.h`
- `0x180017151`: `onecoreuap\net\wlan\cloudstore\provider\lib\WlanSyncTaskWlanToCDS.h`
- `0x180017188`: `onecoreuap\net\wlan\cloudstore\provider\lib\WlanSyncTaskWlanToCDS.h`

## pseudocode

```c
__int64 __fastcall WlanSyncTaskWlanToCDS::PushCloudChange<Windows::Data::WiFi::WiFiProfile>(
        int a1,
        wil::ActivityThreadWatcher *a2,
        HANDLE *a3,
        _QWORD *a4,
        GUID *pInterfaceGuid,
        __int64 *a6,
        char a7,
        int a8,
        __int64 a9)
{
  __int64 *v13; // rbx
  __int64 v14; // rsi
  __int64 *v15; // rdx
  const struct _FILETIME *v16; // rdx
  unsigned __int64 v17; // rax
  DWORD v18; // esi
  char v19; // r9
  bool v21; // cf
  bool v22; // cc
  int v23; // eax
  unsigned int *v24; // rsi
  _QWORD *v25; // r8
  const WCHAR *v26; // r8
  DWORD Profile; // eax
  PVOID v28; // rcx
  _QWORD *v29; // r9
  unsigned __int64 v30; // rbx
  __int64 v31; // rax
  __int64 v32; // r8
  PVOID v33; // rcx
  int v34; // eax
  unsigned int v35; // eax
  _QWORD *v36; // rax
  unsigned int pstrProfileXml; // [rsp+20h] [rbp-E0h]
  unsigned int pstrProfileXmla; // [rsp+20h] [rbp-E0h]
  DWORD pdwFlags; // [rsp+50h] [rbp-B0h] BYREF
  int v40; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v41; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v42; // [rsp+68h] [rbp-98h] BYREF
  PVOID pMemory; // [rsp+70h] [rbp-90h] BYREF
  _BYTE *v44; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v45; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v46; // [rsp+88h] [rbp-78h] BYREF
  PVOID *p_pMemory; // [rsp+90h] [rbp-70h] BYREF
  LPWSTR v48; // [rsp+98h] [rbp-68h] BYREF
  char v49; // [rsp+A0h] [rbp-60h]
  char v50[8]; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v51; // [rsp+B0h] [rbp-50h]
  std::_Ref_count_base *v52; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v53; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v54[3]; // [rsp+D8h] [rbp-28h] BYREF
  __int16 v55; // [rsp+F0h] [rbp-10h] BYREF
  char v56; // [rsp+F8h] [rbp-8h]
  _QWORD v57[8]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v58[32]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int64 v59; // [rsp+170h] [rbp+70h]
  unsigned __int64 v60; // [rsp+178h] [rbp+78h]
  _BYTE v61[32]; // [rsp+180h] [rbp+80h] BYREF
  __int128 v62; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v63; // [rsp+1B0h] [rbp+B0h]
  _BYTE v64[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v65[32]; // [rsp+200h] [rbp+100h] BYREF
  GUID v66; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v67[256]; // [rsp+230h] [rbp+130h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+478h] [rbp+378h]

  v13 = a6;
  v14 = a9;
  wil::cloud_store::cloud_store(v50);
  if ( (unsigned __int64)a6[3] <= 7 )
    v15 = a6;
  else
    v15 = (__int64 *)*a6;
  wil::make_cloud_store_data_reference<Windows::Data::WiFi::WiFiProfileCost>(v64, v15, v14);
  wil::cloud_store::load<Windows::Data::WiFi::WiFiProfile>(v50, v58, v64, 2);
  v17 = wil::FileTime::ToInt64((wil::FileTime *)(a6 + 4), v16);
  v42 = v17;
  v45 = v59;
  v46 = v60;
  v18 = 0;
  if ( !v60 || (v19 = 1, !v61[8]) )
    v19 = 0;
  v41 = (__int64)(v17 - 116444736000000000LL) / 10000000;
  v57[0] = a2;
  v57[1] = a4;
  v57[2] = a6;
  v57[3] = &v41;
  v57[4] = &v46;
  v57[5] = &v42;
  v57[6] = &v45;
  v57[7] = &a8;
  if ( (a7 & 1) != 0 && !v60 )
  {
    pdwFlags = 14;
    if ( a4[3] > 7u )
      a4 = (_QWORD *)*a4;
    pMemory = a4;
    WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned long const &,enum WiFiSyncAction>(
      a1,
      (unsigned int)&pMemory,
      (_DWORD)a6 + 44,
      (unsigned int)&v41,
      (__int64)&v46,
      (__int64)&v42,
      (__int64)&v45,
      (__int64)&a8,
      (__int64)&pdwFlags);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(v61);
    std::wstring::~wstring(v58);
    std::wstring::~wstring(v65);
    std::wstring::~wstring(v64);
    if ( v52 )
      std::_Ref_count_base::_Decref(v52);
    if ( v51 )
      std::_Ref_count_base::_Decref(v51);
    return 14;
  }
  if ( v19 )
    v21 = v60 < (__int64)(v17 - 116444736000000000LL) / 10000000;
  else
    v21 = v59 < v17;
  if ( !v21 )
    goto LABEL_22;
  if ( v41 > GetFutureIgnoreDateAsStdTime() )
  {
    v18 = 13;
LABEL_22:
    v22 = a4[3] <= 7u;
    pdwFlags = v18;
    if ( !v22 )
      a4 = (_QWORD *)*a4;
    pMemory = a4;
    WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned long const &,enum WiFiSyncAction>(
      a1,
      (unsigned int)&pMemory,
      (_DWORD)a6 + 44,
      (unsigned int)&v41,
      (__int64)&v46,
      (__int64)&v42,
      (__int64)&v45,
      (__int64)&a8,
      (__int64)&pdwFlags);
LABEL_73:
    wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>::~cloud_store_data<Windows::Data::WiFi::WiFiProfile>(v58);
    Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfileCost>::~ItemReference<Windows::Data::WiFi::WiFiProfileCost>(v64);
    wil::cloud_store::~cloud_store((wil::cloud_store *)v50);
    return v18;
  }
  v23 = *((_DWORD *)a6 + 10);
  if ( v23 != 2 )
  {
    if ( v23 != 1 && v23 != 8 )
    {
      v59 = v42;
      memset_0(&v66, 0, 0x210u);
      v66 = *pInterfaceGuid;
      if ( a4[3] > 7u )
        a4 = (_QWORD *)*a4;
      v34 = StringCchCopyW(v67, 0x100u, (const unsigned __int16 *)a4);
      if ( v34 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE0,
          (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\WlanSyncTaskWlanToCDS.h",
          (const char *)(unsigned int)v34,
          pstrProfileXml);
      v44 = 0;
      v35 = DusmQueryUserCost(&v66, &v44);
      if ( v35 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xE3,
          (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\WlanSyncTaskWlanToCDS.h",
          (const char *)v35,
          pstrProfileXml);
      WlanSyncTaskWlanToCDS::PopulateDusmCost<Windows::Data::WiFi::WiFiProfile>();
    }
    v18 = 2;
    if ( v23 != 1 )
      v18 = 8;
    v40 = v18;
    _lambda_834179fdd55a229c72548d3f0ce5fcd7_::operator()(v57, v18);
    wil::cloud_store::save<Windows::Data::WiFi::WiFiProfile>(
      (unsigned int)v50,
      (unsigned int)&p_pMemory,
      (unsigned int)v58,
      (unsigned int)v64,
      8,
      v41);
    if ( a4[3] <= 7u )
      v36 = a4;
    else
      v36 = (_QWORD *)*a4;
    v44 = v36;
    WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned long const &,enum WiFiSyncAction const &>(
      a1,
      (unsigned int)&v44,
      (_DWORD)a6 + 44,
      (unsigned int)&v41,
      (__int64)&v46,
      (__int64)&v42,
      (__int64)&v45,
      (__int64)&a8,
      (__int64)&v40);
    if ( *((_DWORD *)a6 + 10) == 1 )
    {
      if ( (unsigned __int64)a6[3] > 7 )
        v13 = (__int64 *)*a6;
      wil::make_cloud_store_data_reference<Windows::Data::WiFi::WiFiProfileCost>(
        &v62,
        v13,
        c_wiFiCloudStoreDataReferenceDefaultCollectionName);
      wil::cloud_store::load<Windows::Data::WiFi::WiFiProfileCost>(v50, v54, &v62, 2);
      if ( !v56 )
      {
        _lambda_834179fdd55a229c72548d3f0ce5fcd7_::operator()(v57, 8);
        wil::cloud_store::save<Windows::Data::WiFi::WiFiProfileCost>(
          (unsigned int)v50,
          (unsigned int)&p_pMemory,
          (unsigned int)v54,
          (unsigned int)&v62,
          8,
          v41);
        v40 = 8;
        if ( a4[3] > 7u )
          a4 = (_QWORD *)*a4;
        v44 = a4;
        WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned long const &,enum WiFiSyncAction>(
          a1,
          (unsigned int)&v44,
          (_DWORD)a6 + 44,
          (unsigned int)&v41,
          (__int64)&v46,
          (__int64)&v42,
          (__int64)&v45,
          (__int64)&a8,
          (__int64)&v40);
      }
      wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v55);
      Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfileCost>::~ItemReference<Windows::Data::WiFi::WiFiProfileCost>(&v62);
    }
    goto LABEL_73;
  }
  v24 = (unsigned int *)a6 + 11;
  if ( a4[3] <= 7u )
    v25 = a4;
  else
    v25 = (_QWORD *)*a4;
  wil::ActivityThreadWatcher::SetMessage(
    a2,
    "Profile name: %ws, Generation: %d, Local version: %llu, Cloud version: %llu, Local modified time: %llu, Cloud modifi"
    "ed time: %llu, Attempting action: %u, Retry count: %lu",
    v25,
    *v24,
    v41,
    v46,
    v42,
    v45,
    1,
    a8);
  pdwFlags = 4;
  pMemory = 0;
  p_pMemory = &pMemory;
  v48 = 0;
  v49 = 1;
  if ( a4[3] <= 7u )
    v26 = (const WCHAR *)a4;
  else
    v26 = (const WCHAR *)*a4;
  Profile = WlanGetProfile(*a3, pInterfaceGuid, v26, 0, &v48, &pdwFlags, 0);
  if ( Profile )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\WlanSyncTaskWlanToCDS.h",
      (const char *)Profile,
      pstrProfileXmla);
  if ( v49 )
  {
    v28 = *p_pMemory;
    *p_pMemory = v48;
    if ( v28 )
      WlanFreeMemory(v28);
  }
  if ( a4[3] <= 7u )
    v29 = a4;
  else
    v29 = (_QWORD *)*a4;
  WlanSyncTaskWlanToCDS::PopulateProfileXml(v58, pMemory, pInterfaceGuid, v29);
  v59 = v42;
  v30 = v41;
  v62 = 0;
  v63 = 0;
  std::string::_Construct<1,char const *>(&v62, &dword_180043B4C, 0);
  v53 = v30;
  v40 = 0;
  v44 = v64;
  v31 = _lambda_674e7f38fe24bd48e51e45f3355ba613_::_lambda_674e7f38fe24bd48e51e45f3355ba613_(
          (unsigned int)v57,
          (unsigned int)v50,
          (unsigned int)v58,
          (unsigned int)&v44,
          (__int64)&v40,
          (__int64)&v53,
          (__int64)&v62);
  v54[0] = retaddr;
  v54[1] = "onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h";
  v54[2] = "Save";
  v55 = 1434;
  wil::cloud_store::RunWithTelemetry<_lambda_258e352bb213654b51d69bac061d8e08_>(&p_pMemory, v54, v32, v31);
  if ( *((_QWORD *)&v63 + 1) > 0xFu )
    std::_Deallocate<16>(v62, *((_QWORD *)&v63 + 1) + 1LL);
  v40 = 1;
  if ( a4[3] > 7u )
    a4 = (_QWORD *)*a4;
  v44 = a4;
  WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned long const &,enum WiFiSyncAction>(
    a1,
    (unsigned int)&v44,
    (_DWORD)v24,
    (unsigned int)&v41,
    (__int64)&v46,
    (__int64)&v42,
    (__int64)&v45,
    (__int64)&a8,
    (__int64)&v40);
  v33 = pMemory;
  pMemory = 0;
  if ( v33 )
    WlanFreeMemory(v33);
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(v61);
  std::wstring::~wstring(v58);
  std::wstring::~wstring(v65);
  std::wstring::~wstring(v64);
  if ( v52 )
    std::_Ref_count_base::_Decref(v52);
  if ( v51 )
    std::_Ref_count_base::_Decref(v51);
  return 1;
}

```

## disassembly

```asm
0x180016ba4  mov     [rsp-8+arg_8], rbx
0x180016ba9  push    rbp
0x180016baa  push    rsi
0x180016bab  push    rdi
0x180016bac  push    r12
0x180016bae  push    r13
0x180016bb0  push    r14
0x180016bb2  push    r15
0x180016bb4  lea     rbp, [rsp-340h]
0x180016bbc  sub     rsp, 440h
0x180016bc3  mov     rax, cs:__security_cookie
0x180016bca  xor     rax, rsp
0x180016bcd  mov     [rbp+370h+var_40], rax
0x180016bd4  mov     rdi, r9
0x180016bd7  mov     r13, r8
0x180016bda  mov     r12, rdx
0x180016bdd  mov     r14, rcx
0x180016be0  mov     rbx, [rbp+370h+arg_28]
0x180016be7  mov     r15, [rbp+370h+pInterfaceGuid]
0x180016bee  mov     rsi, [rbp+370h+arg_40]
0x180016bf5  lea     rcx, [rbp+370h+var_3C8]
0x180016bf9  call    ??0cloud_store@wil@@QEAA@W4PartitionKind@Cloud@Storage@Internal@Windows@@PEBG1W4CloudStoreOptions@3456@II@Z; wil::cloud_store::cloud_store(Windows::Internal::Storage::Cloud::PartitionKind,ushort const *,ushort const *,Windows::Internal::Storage::Cloud::CloudStoreOptions,uint,uint)
0x180016bfe  nop
0x180016bff  cmp     qword ptr [rbx+18h], 7
0x180016c04  jbe     short loc_180016C0B
0x180016c06  mov     rdx, [rbx]
0x180016c09  jmp     short loc_180016C0E
0x180016c0b  mov     rdx, rbx
0x180016c0e  mov     r8, rsi
0x180016c11  lea     rcx, [rbp+370h+var_290]
0x180016c18  call    ??$make_cloud_store_data_reference@UWiFiProfileCost@WiFi@Data@Windows@@@wil@@YA?AU?$ItemReference@UWiFiProfileCost@WiFi@Data@Windows@@@Platform@Data@Windows@@PEBG0@Z; wil::make_cloud_store_data_reference<Windows::Data::WiFi::WiFiProfileCost>(ushort const *,ushort const *)
0x180016c1d  nop
0x180016c1e  mov     r9d, 2
0x180016c24  lea     r8, [rbp+370h+var_290]
0x180016c2b  lea     rdx, [rbp+370h+var_320]
0x180016c2f  lea     rcx, [rbp+370h+var_3C8]
0x180016c33  call    ??$load@UWiFiProfile@WiFi@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@1@AEBU?$ItemReference@UWiFiProfile@WiFi@Data@Windows@@@Platform@Data@Windows@@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::WiFi::WiFiProfile>(Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile> const &,wil::cloud_store_load_options,char const *)
0x180016c38  nop
0x180016c39  lea     rcx, [rbx+20h]; this
0x180016c3d  call    ?ToInt64@FileTime@wil@@YA_KAEBU_FILETIME@@@Z; wil::FileTime::ToInt64(_FILETIME const &)
0x180016c42  mov     r10, rax
0x180016c45  mov     [rsp+470h+var_408], rax
0x180016c4a  mov     r11, [rbp+370h+var_300]
0x180016c4e  mov     [rbp+370h+var_3F0], r11
0x180016c52  mov     r8, [rbp+370h+var_2F8]
0x180016c56  mov     [rbp+370h+var_3E8], r8
0x180016c5a  xor     esi, esi
0x180016c5c  test    r8, r8
0x180016c5f  jz      short loc_180016C6D
0x180016c61  cmp     [rbp+370h+var_2E8], sil
0x180016c68  mov     r9b, 1
0x180016c6b  jnz     short loc_180016C70
0x180016c6d  mov     r9b, sil
0x180016c70  mov     rcx, 0FE624E212AC18000h
0x180016c7a  add     rcx, r10
0x180016c7d  mov     rax, 0D6BF94D5E57A42BDh
0x180016c87  imul    rcx
0x180016c8a  add     rdx, rcx
0x180016c8d  sar     rdx, 17h
0x180016c91  mov     rax, rdx
0x180016c94  shr     rax, 3Fh
0x180016c98  add     rdx, rax
0x180016c9b  mov     [rsp+470h+var_410], rdx
0x180016ca0  mov     [rbp+370h+var_360], r12
0x180016ca4  mov     [rbp+370h+var_358], rdi
0x180016ca8  mov     [rbp+370h+var_350], rbx
0x180016cac  lea     rax, [rsp+470h+var_410]
0x180016cb1  mov     [rbp+370h+var_348], rax
0x180016cb5  lea     rax, [rbp+370h+var_3E8]
0x180016cb9  mov     [rbp+370h+var_340], rax
0x180016cbd  lea     rax, [rsp+470h+var_408]
0x180016cc2  mov     [rbp+370h+var_338], rax
0x180016cc6  lea     rax, [rbp+370h+var_3F0]
0x180016cca  mov     [rbp+370h+var_330], rax
0x180016cce  lea     rax, [rbp+370h+arg_38]
0x180016cd5  mov     [rbp+370h+var_328], rax
0x180016cd9  test    [rbp+370h+arg_30], 1
0x180016ce0  jz      loc_180016DA3
0x180016ce6  test    r8, r8
0x180016ce9  jnz     loc_180016DA3
0x180016cef  lea     r15d, [r8+0Eh]
0x180016cf3  mov     [rsp+470h+var_420], r15d
0x180016cf8  cmp     qword ptr [rdi+18h], 7
0x180016cfd  jbe     short loc_180016D02
0x180016cff  mov     rdi, [rdi]
0x180016d02  mov     [rsp+470h+pMemory], rdi
0x180016d07  lea     r8, [rbx+2Ch]
0x180016d0b  lea     rax, [rsp+470h+var_420]
0x180016d10  mov     [rsp+470h+var_430], rax
0x180016d15  lea     rax, [rbp+370h+arg_38]
0x180016d1c  mov     [rsp+470h+var_438], rax
0x180016d21  lea     rax, [rbp+370h+var_3F0]
0x180016d25  mov     [rsp+470h+pdwGrantedAccess], rax
0x180016d2a  lea     rax, [rsp+470h+var_408]
0x180016d2f  mov     [rsp+470h+pdwFlags], rax
0x180016d34  lea     rax, [rbp+370h+var_3E8]
0x180016d38  mov     [rsp+470h+pstrProfileXml], rax
0x180016d3d  lea     r9, [rsp+470h+var_410]
0x180016d42  lea     rdx, [rsp+470h+pMemory]
0x180016d47  mov     rcx, r14
0x180016d4a  call    ??$ActionTakenOnWiFiProfile@PEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEB_KAEB_KAEB_KAEB_KAEBKW4WiFiSyncAction@@@WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAAX$$QEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEB_K222AEBK$$QEAW4WiFiSyncAction@@@Z; WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<ushort const *,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,ulong const &,WiFiSyncAction>(ushort const * &&,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,ulong const &,WiFiSyncAction &&)
0x180016d4f  nop
0x180016d50  lea     rcx, [rbp+370h+var_2F0]
0x180016d57  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x180016d5c  lea     rcx, [rbp+370h+var_320]
0x180016d60  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016d65  nop
0x180016d66  lea     rcx, [rbp+370h+var_270]
0x180016d6d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016d72  lea     rcx, [rbp+370h+var_290]
0x180016d79  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016d7e  nop
0x180016d7f  mov     rcx, [rbp+370h+var_3A8]; this
0x180016d83  test    rcx, rcx
0x180016d86  jz      short loc_180016D8D
0x180016d88  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016d8d  mov     rcx, [rbp+370h+var_3C0]; this
0x180016d91  test    rcx, rcx
0x180016d94  jz      short loc_180016D9B
0x180016d96  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016d9b  mov     eax, r15d
0x180016d9e  jmp     loc_18001735C
0x180016da3  test    r9b, r9b
0x180016da6  jnz     short loc_180016DAD
0x180016da8  cmp     r11, r10
0x180016dab  jmp     short loc_180016DB0
0x180016dad  cmp     r8, rdx
0x180016db0  jnb     short loc_180016DC6
0x180016db2  call    ?GetFutureIgnoreDateAsStdTime@@YA_JXZ; GetFutureIgnoreDateAsStdTime(void)
0x180016db7  mov     rcx, [rsp+470h+var_410]
0x180016dbc  cmp     rcx, rax
0x180016dbf  jbe     short loc_180016E26
0x180016dc1  mov     esi, 0Dh
0x180016dc6  cmp     qword ptr [rdi+18h], 7
0x180016dcb  mov     [rsp+470h+var_420], esi
0x180016dcf  jbe     short loc_180016DD4
0x180016dd1  mov     rdi, [rdi]
0x180016dd4  lea     rax, [rsp+470h+var_420]
0x180016dd9  mov     [rsp+470h+var_430], rax
0x180016dde  lea     rax, [rbp+370h+arg_38]
0x180016de5  mov     [rsp+470h+var_438], rax
0x180016dea  lea     rax, [rbp+370h+var_3F0]
0x180016dee  mov     [rsp+470h+pdwGrantedAccess], rax
0x180016df3  lea     rax, [rsp+470h+var_408]
0x180016df8  mov     [rsp+470h+pdwFlags], rax
0x180016dfd  lea     rax, [rbp+370h+var_3E8]
0x180016e01  mov     [rsp+470h+pstrProfileXml], rax
0x180016e06  mov     [rsp+470h+pMemory], rdi
0x180016e0b  lea     r9, [rsp+470h+var_410]
0x180016e10  lea     r8, [rbx+2Ch]
0x180016e14  lea     rdx, [rsp+470h+pMemory]
0x180016e19  mov     rcx, r14
0x180016e1c  call    ??$ActionTakenOnWiFiProfile@PEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEB_KAEB_KAEB_KAEB_KAEBKW4WiFiSyncAction@@@WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAAX$$QEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEB_K222AEBK$$QEAW4WiFiSyncAction@@@Z; WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<ushort const *,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,ulong const &,WiFiSyncAction>(ushort const * &&,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,ulong const &,WiFiSyncAction &&)
0x180016e21  jmp     loc_18001733A
0x180016e26  mov     eax, [rbx+28h]
0x180016e29  cmp     eax, 2
0x180016e2c  jnz     loc_1800170E4
0x180016e32  mov     eax, [rbp+370h+arg_38]
0x180016e38  mov     rdx, [rbp+370h+var_3F0]
0x180016e3c  mov     r9, [rsp+470h+var_408]
0x180016e41  mov     r10, [rbp+370h+var_3E8]
0x180016e45  lea     rsi, [rbx+2Ch]
0x180016e49  cmp     qword ptr [rdi+18h], 7
0x180016e4e  jbe     short loc_180016E55
0x180016e50  mov     r8, [rdi]
0x180016e53  jmp     short loc_180016E58
0x180016e55  mov     r8, rdi
0x180016e58  mov     [rsp+470h+var_428], eax
0x180016e5c  mov     dword ptr [rsp+470h+var_430], 1
0x180016e64  mov     [rsp+470h+var_438], rdx
0x180016e69  mov     [rsp+470h+pdwGrantedAccess], r9
0x180016e6e  mov     [rsp+470h+pdwFlags], r10
0x180016e73  mov     [rsp+470h+pstrProfileXml], rcx
0x180016e78  mov     r9d, [rsi]
0x180016e7b  lea     rdx, aProfileNameWsG; "Profile name: %ws, Generation: %d, Loca"...
0x180016e82  mov     rcx, r12; this
0x180016e85  call    ?SetMessage@ActivityThreadWatcher@wil@@QEAAXPEBDZZ; wil::ActivityThreadWatcher::SetMessage(char const *,...)
0x180016e8a  mov     [rsp+470h+var_420], 4
0x180016e92  xor     r12d, r12d
0x180016e95  mov     [rsp+470h+pMemory], r12
0x180016e9a  lea     rax, [rsp+470h+pMemory]
0x180016e9f  mov     [rbp+370h+var_3E0], rax
0x180016ea3  mov     [rbp+370h+var_3D8], r12
0x180016ea7  mov     [rbp+370h+var_3D0], 1
0x180016eab  cmp     qword ptr [rdi+18h], 7
0x180016eb0  jbe     short loc_180016EB7
0x180016eb2  mov     r8, [rdi]
0x180016eb5  jmp     short loc_180016EBA
0x180016eb7  mov     r8, rdi; strProfileName
0x180016eba  mov     [rsp+470h+pdwGrantedAccess], r12; pdwGrantedAccess
0x180016ebf  lea     rax, [rsp+470h+var_420]
0x180016ec4  mov     [rsp+470h+pdwFlags], rax; pdwFlags
0x180016ec9  lea     rax, [rbp+370h+var_3D8]
0x180016ecd  mov     [rsp+470h+pstrProfileXml], rax; unsigned int
0x180016ed2  xor     r9d, r9d; pReserved
0x180016ed5  mov     rdx, r15; pInterfaceGuid
0x180016ed8  mov     rcx, [r13+0]; hClientHandle
0x180016edc  call    cs:__imp_WlanGetProfile
0x180016ee2  mov     rcx, [rbp+378h]; this
0x180016ee9  test    eax, eax
0x180016eeb  jz      short loc_180016F02
0x180016eed  mov     r9d, eax; char *
0x180016ef0  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180016ef7  mov     edx, 9Fh; void *
0x180016efc  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180016f02  cmp     [rbp+370h+var_3D0], r12b
0x180016f06  jz      short loc_180016F21
0x180016f08  mov     rdx, [rbp+370h+var_3E0]
0x180016f0c  mov     rcx, [rdx]; pMemory
0x180016f0f  mov     rax, [rbp+370h+var_3D8]
0x180016f13  mov     [rdx], rax
0x180016f16  test    rcx, rcx
0x180016f19  jz      short loc_180016F21
0x180016f1b  call    cs:__imp_WlanFreeMemory
0x180016f21  cmp     qword ptr [rdi+18h], 7
0x180016f26  jbe     short loc_180016F2D
0x180016f28  mov     r9, [rdi]
0x180016f2b  jmp     short loc_180016F30
0x180016f2d  mov     r9, rdi
0x180016f30  mov     r8, r15
0x180016f33  mov     rdx, [rsp+470h+pMemory]
0x180016f38  lea     rcx, [rbp+370h+var_320]
0x180016f3c  call    ?PopulateProfileXml@WlanSyncTaskWlanToCDS@@CAXAEAV?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@PEBGAEBU_GUID@@QEBG@Z; WlanSyncTaskWlanToCDS::PopulateProfileXml(wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile> &,ushort const *,_GUID const &,ushort const * const)
0x180016f41  mov     rax, [rsp+470h+var_408]
0x180016f46  mov     [rbp+370h+var_300], rax
0x180016f4a  mov     rbx, [rsp+470h+var_410]
0x180016f4f  xorps   xmm0, xmm0
0x180016f52  movups  [rbp+370h+var_2D0], xmm0
0x180016f59  xorps   xmm1, xmm1
0x180016f5c  movdqu  [rbp+370h+var_2C0], xmm1
0x180016f64  xor     r8d, r8d
0x180016f67  lea     rdx, dword_180043B4C
0x180016f6e  lea     rcx, [rbp+370h+var_2D0]
0x180016f75  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180016f7a  nop
0x180016f7b  mov     [rbp+370h+var_3A0], rbx
0x180016f7f  mov     [rsp+470h+var_418], r12d
0x180016f84  lea     rax, [rbp+370h+var_290]
0x180016f8b  mov     [rsp+470h+var_3F8], rax
0x180016f90  lea     rax, [rbp+370h+var_2D0]
0x180016f97  mov     [rsp+470h+pdwGrantedAccess], rax
0x180016f9c  lea     rax, [rbp+370h+var_3A0]
0x180016fa0  mov     [rsp+470h+pdwFlags], rax
0x180016fa5  lea     rax, [rsp+470h+var_418]
0x180016faa  mov     [rsp+470h+pstrProfileXml], rax
0x180016faf  lea     r9, [rsp+470h+var_3F8]
0x180016fb4  lea     r8, [rbp+370h+var_320]
0x180016fb8  lea     rdx, [rbp+370h+var_3C8]
0x180016fbc  lea     rcx, [rbp+370h+var_360]
0x180016fc0  call    ??0_lambda_674e7f38fe24bd48e51e45f3355ba613_@@QEAA@PEAVcloud_store@wil@@AEBV?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@2@AEAPEBU?$ItemReference@UWiFiProfileCost@WiFi@Data@Windows@@@Platform@Data@Windows@@AEAW4cloud_store_save_options@2@AEA_KAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; _lambda_674e7f38fe24bd48e51e45f3355ba613_::_lambda_674e7f38fe24bd48e51e45f3355ba613_(wil::cloud_store *,wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost> const &,Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfileCost> const * &,wil::cloud_store_save_options &,unsigned __int64 &,std::string const &)
0x180016fc5  mov     rcx, [rbp+378h]
0x180016fcc  mov     [rbp+370h+var_398], rcx
0x180016fd0  lea     rcx, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180016fd7  mov     [rbp+370h+var_390], rcx
0x180016fdb  lea     rcx, aSave; "Save"
0x180016fe2  mov     [rbp+370h+var_388], rcx
0x180016fe6  mov     ecx, 59Ah
0x180016feb  mov     [rbp+370h+var_380], cx
0x180016fef  mov     r9, rax
0x180016ff2  lea     rdx, [rbp+370h+var_398]
0x180016ff6  lea     rcx, [rbp+370h+var_3E0]
0x180016ffa  call    ??$RunWithTelemetry@V_lambda_258e352bb213654b51d69bac061d8e08_@@@cloud_store@wil@@CA?AVcloud_store_save_result@1@AEBUDiagnosticsInfo@1@W4ReportingKind@1@$$QEAV_lambda_258e352bb213654b51d69bac061d8e08_@@@Z; wil::cloud_store::RunWithTelemetry<_lambda_258e352bb213654b51d69bac061d8e08_>(wil::DiagnosticsInfo const &,wil::ReportingKind,_lambda_258e352bb213654b51d69bac061d8e08_ &&)
0x180016fff  nop
0x180017000  mov     rdx, qword ptr [rbp+370h+var_2C0+8]
0x180017007  cmp     rdx, 0Fh
0x18001700b  jbe     short loc_18001701C
0x18001700d  inc     rdx
0x180017010  mov     rcx, qword ptr [rbp+370h+var_2D0]
0x180017017  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001701c  mov     ebx, 1
0x180017021  mov     [rsp+470h+var_418], ebx
0x180017025  cmp     qword ptr [rdi+18h], 7
0x18001702a  jbe     short loc_18001702F
0x18001702c  mov     rdi, [rdi]
0x18001702f  mov     [rsp+470h+var_3F8], rdi
0x180017034  lea     rax, [rsp+470h+var_418]
0x180017039  mov     [rsp+470h+var_430], rax
0x18001703e  lea     rax, [rbp+370h+arg_38]
0x180017045  mov     [rsp+470h+var_438], rax
0x18001704a  lea     rax, [rbp+370h+var_3F0]
0x18001704e  mov     [rsp+470h+pdwGrantedAccess], rax
0x180017053  lea     rax, [rsp+470h+var_408]
0x180017058  mov     [rsp+470h+pdwFlags], rax
0x18001705d  lea     rax, [rbp+370h+var_3E8]
0x180017061  mov     [rsp+470h+pstrProfileXml], rax
0x180017066  lea     r9, [rsp+470h+var_410]
0x18001706b  mov     r8, rsi
0x18001706e  lea     rdx, [rsp+470h+var_3F8]
0x180017073  mov     rcx, r14
0x180017076  call    ??$ActionTakenOnWiFiProfile@PEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEB_KAEB_KAEB_KAEB_KAEBKW4WiFiSyncAction@@@WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAAX$$QEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEB_K222AEBK$$QEAW4WiFiSyncAction@@@Z; WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<ushort const *,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,ulong const &,WiFiSyncAction>(ushort const * &&,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,ulong const &,WiFiSyncAction &&)
0x18001707b  nop
0x18001707c  mov     rcx, [rsp+470h+pMemory]; pMemory
0x180017081  mov     [rsp+470h+pMemory], r12
0x180017086  test    rcx, rcx
0x180017089  jz      short loc_180017092
0x18001708b  call    cs:__imp_WlanFreeMemory
0x180017091  nop
0x180017092  lea     rcx, [rbp+370h+var_2F0]
0x180017099  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x18001709e  lea     rcx, [rbp+370h+var_320]
  ... truncated ...
```
