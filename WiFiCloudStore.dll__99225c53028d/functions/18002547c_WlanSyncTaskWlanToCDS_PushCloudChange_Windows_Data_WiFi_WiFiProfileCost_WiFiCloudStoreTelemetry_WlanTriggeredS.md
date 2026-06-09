# WlanSyncTaskWlanToCDS::PushCloudChange<Windows::Data::WiFi::WiFiProfileCost>(WiFiCloudStoreTelemetry::WlanTriggeredSync &,wil::ActivityThreadWatcher &,void * const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_GUID const &,Windows::Internal::WiFiCloudStore::SyncNeededProfile const &,PushCloudChangeOptionFlags,ulong,ushort const *)

- ea: `0x18002547c`
- end: `0x180025a98`
- name: `??$PushCloudChange@UWiFiProfileCost@WiFi@Data@Windows@@@WlanSyncTaskWlanToCDS@@CA?AW4WiFiSyncAction@@AEAVWlanTriggeredSync@WiFiCloudStoreTelemetry@@AEAVActivityThreadWatcher@wil@@AEBQEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@AEBUSyncNeededProfile@WiFiCloudStore@Internal@Windows@@W4PushCloudChangeOptionFlags@@KPEBG@Z`
- size: `1564`
- prototype: `__int64 __fastcall(int, __int64, HANDLE *, const WCHAR *, GUID *pInterfaceGuid, __int64, __int64, char, __int64)`
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180035d7c`
- `0x180038280`

## callees

- `0x18000a944`
- `0x180010c8c`
- `0x180011560`
- `0x1800115a0`
- `0x1800169bc`
- `0x18001738c`
- `0x1800174a8`
- `0x1800174c0`
- `0x180017de4`
- `0x18001c92c`
- `0x18002547c`
- `0x180025aa0`
- `0x180025b20`
- `0x180025c04`
- `0x180025c9c`
- `0x18002a030`
- `0x18002aad0`
- `0x18002e2d0`
- `0x180031ce4`
- `0x180032d2c`

## import_xrefs

- `wlanapi!WlanGetProfile` at `0x180025705`
- `wlanapi!WlanGetProfile` at `0x180025705`
- `dusmapi!DusmQueryUserCost` at `0x1800257d0`
- `dusmapi!DusmQueryUserCost` at `0x1800257d0`

## string_xrefs

- `0x180025719`: `onecoreuap\net\wlan\cloudstore\provider\lib\WlanSyncTaskWlanToCDS.h`
- `0x1800257ad`: `onecoreuap\net\wlan\cloudstore\provider\lib\WlanSyncTaskWlanToCDS.h`
- `0x1800257e4`: `onecoreuap\net\wlan\cloudstore\provider\lib\WlanSyncTaskWlanToCDS.h`

## pseudocode

```c
__int64 __fastcall WlanSyncTaskWlanToCDS::PushCloudChange<Windows::Data::WiFi::WiFiProfileCost>(
        int a1,
        __int64 a2,
        HANDLE *a3,
        const WCHAR *a4,
        GUID *pInterfaceGuid,
        __int64 a6,
        __int64 a7,
        char a8,
        __int64 a9)
{
  __int64 v13; // rdi
  __int64 v14; // r15
  __int64 v15; // rdx
  const struct _FILETIME *v16; // rdx
  unsigned __int64 v17; // rax
  char v18; // r8
  DWORD v19; // esi
  __int64 **v20; // rdx
  int v21; // eax
  DWORD Profile; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  const char *v26; // r9
  const unsigned __int16 *v27; // r8
  int v28; // eax
  unsigned int v29; // eax
  int v30; // ecx
  const WCHAR *v31; // rax
  unsigned int pstrProfileXml; // [rsp+20h] [rbp-E0h]
  unsigned int pstrProfileXmla; // [rsp+20h] [rbp-E0h]
  DWORD pdwFlags; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v36; // [rsp+58h] [rbp-A8h] BYREF
  const WCHAR *v37; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v38; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v39; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v40; // [rsp+78h] [rbp-88h] BYREF
  const WCHAR *v41; // [rsp+80h] [rbp-80h] BYREF
  LPWSTR v42; // [rsp+88h] [rbp-78h] BYREF
  char v43; // [rsp+90h] [rbp-70h]
  __int64 v44; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v45; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v46; // [rsp+A8h] [rbp-58h]
  char v47[8]; // [rsp+B0h] [rbp-50h] BYREF
  char v48; // [rsp+B8h] [rbp-48h]
  _BYTE v49[40]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v50[8]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v51[24]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v52[24]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v53[64]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v54[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  GUID v55; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int16 v56[256]; // [rsp+1F0h] [rbp+F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+438h] [rbp+338h]

  v13 = a6;
  v14 = a9;
  wil::cloud_store::cloud_store(v49);
  if ( *(_QWORD *)(a6 + 24) <= 7u )
    v15 = a6;
  else
    v15 = *(_QWORD *)a6;
  wil::make_cloud_store_data_reference<Windows::Data::WiFi::WiFiProfileCost>((__int64)v53, v15, v14);
  wil::cloud_store::load<Windows::Data::WiFi::WiFiProfileCost>(v49, &v44, v53, 2);
  v17 = wil::FileTime::ToInt64((wil::FileTime *)(a6 + 32), v16);
  v38 = v17;
  v39 = v45;
  v40 = v46;
  if ( !v46 || (v18 = 1, !v48) )
    v18 = 0;
  v36 = (__int64)(v17 - 116444736000000000LL) / 10000000;
  v50[0] = a2;
  v50[1] = a4;
  v50[2] = a6;
  v50[3] = &v36;
  v50[4] = &v40;
  v50[5] = &v38;
  v50[6] = &v39;
  v50[7] = &a8;
  if ( v18 )
  {
    if ( v46 < (__int64)(v17 - 116444736000000000LL) / 10000000 )
      goto LABEL_9;
LABEL_15:
    pdwFlags = 0;
    if ( *((_QWORD *)a4 + 3) > 7u )
      a4 = *(const WCHAR **)a4;
    v37 = a4;
    WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned long const &,enum WiFiSyncAction>(
      a1,
      (unsigned int)&v37,
      a6 + 44,
      (unsigned int)&v36,
      (__int64)&v40,
      (__int64)&v38,
      (__int64)&v39,
      (__int64)&a8,
      (__int64)&pdwFlags);
    v19 = 0;
    goto LABEL_54;
  }
  if ( v45 >= v17 )
    goto LABEL_15;
LABEL_9:
  if ( v36 > GetFutureIgnoreDateAsStdTime() )
  {
    v19 = 13;
    pdwFlags = 13;
    if ( *((_QWORD *)a4 + 3) > 7u )
      a4 = *(const WCHAR **)a4;
    v37 = a4;
    v20 = (__int64 **)&v37;
LABEL_13:
    WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned long const &,enum WiFiSyncAction>(
      a1,
      (_DWORD)v20,
      a6 + 44,
      (unsigned int)&v36,
      (__int64)&v40,
      (__int64)&v38,
      (__int64)&v39,
      (__int64)&a8,
      (__int64)&pdwFlags);
    goto LABEL_54;
  }
  v21 = *(_DWORD *)(a6 + 40);
  if ( v21 == 2 )
  {
    _lambda_834179fdd55a229c72548d3f0ce5fcd7_::operator()(v50, 1);
    pdwFlags = 4;
    v37 = 0;
    v41 = (const WCHAR *)&v37;
    v42 = 0;
    v43 = 1;
    if ( *((_QWORD *)a4 + 3) > 7u )
      a4 = *(const WCHAR **)a4;
    Profile = WlanGetProfile(*a3, pInterfaceGuid, a4, 0, &v42, &pdwFlags, 0);
    if ( Profile )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x9F,
        (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\WlanSyncTaskWlanToCDS.h",
        (const char *)Profile,
        pstrProfileXmla);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>(&v41);
    WlanSyncTaskWlanToCDS::PopulateProfileXml<Windows::Data::WiFi::WiFiProfileCost>(v24, v23, v25, v26);
  }
  if ( v21 == 1 || v21 == 8 )
  {
    v19 = 2;
    if ( v21 != 1 )
      v19 = 8;
    pdwFlags = v19;
    _lambda_834179fdd55a229c72548d3f0ce5fcd7_::operator()(v50, v19);
    wil::cloud_store::save<Windows::Data::WiFi::WiFiProfileCost>(
      (unsigned int)v49,
      (unsigned int)&v41,
      (unsigned int)&v44,
      (unsigned int)v53,
      8,
      v36);
    if ( *((_QWORD *)a4 + 3) <= 7u )
      v31 = a4;
    else
      v31 = *(const WCHAR **)a4;
    v41 = v31;
    WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned long const &,enum WiFiSyncAction const &>(
      a1,
      (unsigned int)&v41,
      a6 + 44,
      (unsigned int)&v36,
      (__int64)&v40,
      (__int64)&v38,
      (__int64)&v39,
      (__int64)&a8,
      (__int64)&pdwFlags);
    if ( *(_DWORD *)(a6 + 40) == 1 )
    {
      if ( *(_QWORD *)(a6 + 24) > 7u )
        v13 = *(_QWORD *)a6;
      wil::make_cloud_store_data_reference<Windows::Data::WiFi::WiFiProfileCost>(
        (__int64)v54,
        v13,
        (__int64)c_wiFiCloudStoreDataReferenceDefaultCollectionName);
      wil::cloud_store::load<Windows::Data::WiFi::WiFiProfileCost>(v49, v51, v54, 2);
      if ( !v52[8] )
      {
        _lambda_834179fdd55a229c72548d3f0ce5fcd7_::operator()(v50, 8);
        wil::cloud_store::save<Windows::Data::WiFi::WiFiProfileCost>(
          (unsigned int)v49,
          (unsigned int)&v41,
          (unsigned int)v51,
          (unsigned int)v54,
          8,
          v36);
        pdwFlags = 8;
        if ( *((_QWORD *)a4 + 3) > 7u )
          a4 = *(const WCHAR **)a4;
        v41 = a4;
        WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned long const &,enum WiFiSyncAction>(
          a1,
          (unsigned int)&v41,
          a6 + 44,
          (unsigned int)&v36,
          (__int64)&v40,
          (__int64)&v38,
          (__int64)&v39,
          (__int64)&a8,
          (__int64)&pdwFlags);
      }
      wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(v52);
      Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfileCost>::~ItemReference<Windows::Data::WiFi::WiFiProfileCost>(v54);
    }
  }
  else
  {
    v45 = v38;
    memset_0(&v55, 0, 0x210u);
    v55 = *pInterfaceGuid;
    if ( *((_QWORD *)a4 + 3) <= 7u )
      v27 = a4;
    else
      v27 = *(const unsigned __int16 **)a4;
    v28 = StringCchCopyW(v56, 0x100u, v27);
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE0,
        (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\WlanSyncTaskWlanToCDS.h",
        (const char *)(unsigned int)v28,
        pstrProfileXml);
    v37 = 0;
    v29 = DusmQueryUserCost(&v55, &v37);
    if ( v29 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xE3,
        (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\WlanSyncTaskWlanToCDS.h",
        (const char *)v29,
        pstrProfileXml);
    v30 = v44;
    v44 = (int)v37;
    if ( !v48 && v30 == (_DWORD)v37 )
    {
      v19 = 11;
      pdwFlags = 11;
      if ( *((_QWORD *)a4 + 3) > 7u )
        a4 = *(const WCHAR **)a4;
      v41 = a4;
      v20 = (__int64 **)&v41;
      goto LABEL_13;
    }
    _lambda_834179fdd55a229c72548d3f0ce5fcd7_::operator()(v50, 7);
    wil::cloud_store::save<Windows::Data::WiFi::WiFiProfileCost>(
      (unsigned int)v49,
      (unsigned int)&v41,
      (unsigned int)&v44,
      (unsigned int)v53,
      0,
      v36);
    pdwFlags = 7;
    if ( *((_QWORD *)a4 + 3) > 7u )
      a4 = *(const WCHAR **)a4;
    v41 = a4;
    WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned long const &,enum WiFiSyncAction>(
      a1,
      (unsigned int)&v41,
      a6 + 44,
      (unsigned int)&v36,
      (__int64)&v40,
      (__int64)&v38,
      (__int64)&v39,
      (__int64)&a8,
      (__int64)&pdwFlags);
    v19 = 7;
  }
LABEL_54:
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(v47);
  Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfileCost>::~ItemReference<Windows::Data::WiFi::WiFiProfileCost>(v53);
  wil::cloud_store::~cloud_store((wil::cloud_store *)v49);
  return v19;
}

```

## disassembly

```asm
0x18002547c  mov     [rsp-8+arg_8], rbx
0x180025481  push    rbp
0x180025482  push    rsi
0x180025483  push    rdi
0x180025484  push    r12
0x180025486  push    r13
0x180025488  push    r14
0x18002548a  push    r15
0x18002548c  lea     rbp, [rsp-300h]
0x180025494  sub     rsp, 400h
0x18002549b  mov     rax, cs:__security_cookie
0x1800254a2  xor     rax, rsp
0x1800254a5  mov     [rbp+330h+var_40], rax
0x1800254ac  mov     rbx, r9
0x1800254af  mov     r12, r8
0x1800254b2  mov     r13, rdx
0x1800254b5  mov     r14, rcx
0x1800254b8  mov     rdi, [rbp+330h+arg_28]
0x1800254bf  mov     rsi, [rbp+330h+pInterfaceGuid]
0x1800254c6  mov     r15, [rbp+330h+arg_40]
0x1800254cd  lea     rcx, [rbp+330h+var_368]
0x1800254d1  call    ??0cloud_store@wil@@QEAA@W4PartitionKind@Cloud@Storage@Internal@Windows@@PEBG1W4CloudStoreOptions@3456@II@Z; wil::cloud_store::cloud_store(Windows::Internal::Storage::Cloud::PartitionKind,ushort const *,ushort const *,Windows::Internal::Storage::Cloud::CloudStoreOptions,uint,uint)
0x1800254d6  nop
0x1800254d7  cmp     qword ptr [rdi+18h], 7
0x1800254dc  jbe     short loc_1800254E3
0x1800254de  mov     rdx, [rdi]
0x1800254e1  jmp     short loc_1800254E6
0x1800254e3  mov     rdx, rdi
0x1800254e6  mov     r8, r15
0x1800254e9  lea     rcx, [rbp+330h+var_2D0]
0x1800254ed  call    ??$make_cloud_store_data_reference@UWiFiProfileCost@WiFi@Data@Windows@@@wil@@YA?AU?$ItemReference@UWiFiProfileCost@WiFi@Data@Windows@@@Platform@Data@Windows@@PEBG0@Z; wil::make_cloud_store_data_reference<Windows::Data::WiFi::WiFiProfileCost>(ushort const *,ushort const *)
0x1800254f2  nop
0x1800254f3  mov     r9d, 2
0x1800254f9  lea     r8, [rbp+330h+var_2D0]
0x1800254fd  lea     rdx, [rbp+330h+var_398]
0x180025501  lea     rcx, [rbp+330h+var_368]
0x180025505  call    ??$load@UWiFiProfileCost@WiFi@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@1@AEBU?$ItemReference@UWiFiProfileCost@WiFi@Data@Windows@@@Platform@Data@Windows@@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::WiFi::WiFiProfileCost>(Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfileCost> const &,wil::cloud_store_load_options,char const *)
0x18002550a  nop
0x18002550b  lea     rcx, [rdi+20h]; this
0x18002550f  call    ?ToInt64@FileTime@wil@@YA_KAEBU_FILETIME@@@Z; wil::FileTime::ToInt64(_FILETIME const &)
0x180025514  mov     r10, rax
0x180025517  mov     [rsp+430h+var_3C8], rax
0x18002551c  mov     r11, [rbp+330h+var_390]
0x180025520  mov     [rsp+430h+var_3C0], r11
0x180025525  mov     r9, [rbp+330h+var_388]
0x180025529  mov     [rsp+430h+var_3B8], r9
0x18002552e  xor     r15d, r15d
0x180025531  test    r9, r9
0x180025534  jz      short loc_18002553F
0x180025536  cmp     [rbp+330h+var_378], r15b
0x18002553a  mov     r8b, 1
0x18002553d  jnz     short loc_180025542
0x18002553f  mov     r8b, r15b
0x180025542  mov     rcx, 0FE624E212AC18000h
0x18002554c  add     rcx, r10
0x18002554f  mov     rax, 0D6BF94D5E57A42BDh
0x180025559  imul    rcx
0x18002555c  add     rdx, rcx
0x18002555f  sar     rdx, 17h
0x180025563  mov     rax, rdx
0x180025566  shr     rax, 3Fh
0x18002556a  add     rdx, rax
0x18002556d  mov     [rsp+430h+var_3D8], rdx
0x180025572  mov     [rbp+330h+var_340], r13
0x180025576  mov     [rbp+330h+var_338], rbx
0x18002557a  mov     [rbp+330h+var_330], rdi
0x18002557e  lea     rax, [rsp+430h+var_3D8]
0x180025583  mov     [rbp+330h+var_328], rax
0x180025587  lea     rax, [rsp+430h+var_3B8]
0x18002558c  mov     [rbp+330h+var_320], rax
0x180025590  lea     rax, [rsp+430h+var_3C8]
0x180025595  mov     [rbp+330h+var_318], rax
0x180025599  lea     rax, [rsp+430h+var_3C0]
0x18002559e  mov     [rbp+330h+var_310], rax
0x1800255a2  lea     rax, [rbp+330h+arg_38]
0x1800255a9  mov     [rbp+330h+var_308], rax
0x1800255ad  test    r8b, r8b
0x1800255b0  jnz     short loc_18002562E
0x1800255b2  cmp     r11, r10
0x1800255b5  jnb     short loc_180025633
0x1800255b7  call    ?GetFutureIgnoreDateAsStdTime@@YA_JXZ; GetFutureIgnoreDateAsStdTime(void)
0x1800255bc  cmp     [rsp+430h+var_3D8], rax
0x1800255c1  jbe     loc_180025699
0x1800255c7  mov     esi, 0Dh
0x1800255cc  mov     [rsp+430h+var_3E0], esi
0x1800255d0  cmp     qword ptr [rbx+18h], 7
0x1800255d5  jbe     short loc_1800255DA
0x1800255d7  mov     rbx, [rbx]
0x1800255da  mov     [rsp+430h+var_3D0], rbx
0x1800255df  lea     rdx, [rsp+430h+var_3D0]
0x1800255e4  lea     rax, [rsp+430h+var_3E0]
0x1800255e9  mov     [rsp+430h+var_3F0], rax
0x1800255ee  lea     rax, [rbp+330h+arg_38]
0x1800255f5  mov     [rsp+430h+var_3F8], rax
0x1800255fa  lea     rax, [rsp+430h+var_3C0]
0x1800255ff  mov     [rsp+430h+pdwGrantedAccess], rax
0x180025604  lea     rax, [rsp+430h+var_3C8]
0x180025609  mov     [rsp+430h+pdwFlags], rax
0x18002560e  lea     rax, [rsp+430h+var_3B8]
0x180025613  lea     r9, [rsp+430h+var_3D8]
0x180025618  mov     [rsp+430h+pstrProfileXml], rax
0x18002561d  lea     r8, [rdi+2Ch]
0x180025621  mov     rcx, r14
0x180025624  call    ??$ActionTakenOnWiFiProfile@PEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEB_KAEB_KAEB_KAEB_KAEBKW4WiFiSyncAction@@@WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAAX$$QEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEB_K222AEBK$$QEAW4WiFiSyncAction@@@Z; WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<ushort const *,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,ulong const &,WiFiSyncAction>(ushort const * &&,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,ulong const &,WiFiSyncAction &&)
0x180025629  jmp     loc_180025A4F
0x18002562e  cmp     r9, rdx
0x180025631  jb      short loc_1800255B7
0x180025633  mov     [rsp+430h+var_3E0], r15d
0x180025638  cmp     qword ptr [rbx+18h], 7
0x18002563d  jbe     short loc_180025642
0x18002563f  mov     rbx, [rbx]
0x180025642  mov     [rsp+430h+var_3D0], rbx
0x180025647  lea     r8, [rdi+2Ch]
0x18002564b  lea     rax, [rsp+430h+var_3E0]
0x180025650  mov     [rsp+430h+var_3F0], rax
0x180025655  lea     rax, [rbp+330h+arg_38]
0x18002565c  mov     [rsp+430h+var_3F8], rax
0x180025661  lea     rax, [rsp+430h+var_3C0]
0x180025666  mov     [rsp+430h+pdwGrantedAccess], rax
0x18002566b  lea     rax, [rsp+430h+var_3C8]
0x180025670  mov     [rsp+430h+pdwFlags], rax
0x180025675  lea     rax, [rsp+430h+var_3B8]
0x18002567a  mov     [rsp+430h+pstrProfileXml], rax
0x18002567f  lea     r9, [rsp+430h+var_3D8]
0x180025684  lea     rdx, [rsp+430h+var_3D0]
0x180025689  mov     rcx, r14
0x18002568c  call    ??$ActionTakenOnWiFiProfile@PEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEB_KAEB_KAEB_KAEB_KAEBKW4WiFiSyncAction@@@WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAAX$$QEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEB_K222AEBK$$QEAW4WiFiSyncAction@@@Z; WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<ushort const *,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,ulong const &,WiFiSyncAction>(ushort const * &&,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,ulong const &,WiFiSyncAction &&)
0x180025691  mov     esi, r15d
0x180025694  jmp     loc_180025A4F
0x180025699  mov     eax, [rdi+28h]
0x18002569c  mov     r13d, 2
0x1800256a2  cmp     eax, r13d
0x1800256a5  jnz     loc_18002573A
0x1800256ab  lea     edx, [r13-1]
0x1800256af  lea     rcx, [rbp+330h+var_340]
0x1800256b3  call    ??R_lambda_834179fdd55a229c72548d3f0ce5fcd7_@@QEBA@W4WiFiSyncAction@@@Z; _lambda_834179fdd55a229c72548d3f0ce5fcd7_::operator()(WiFiSyncAction)
0x1800256b8  mov     [rsp+430h+var_3E0], 4
0x1800256c0  mov     [rsp+430h+var_3D0], r15
0x1800256c5  lea     rax, [rsp+430h+var_3D0]
0x1800256ca  mov     [rbp+330h+var_3B0], rax
0x1800256ce  mov     [rbp+330h+var_3A8], r15
0x1800256d2  mov     [rbp+330h+var_3A0], 1
0x1800256d6  cmp     qword ptr [rbx+18h], 7
0x1800256db  jbe     short loc_1800256E0
0x1800256dd  mov     rbx, [rbx]
0x1800256e0  mov     [rsp+430h+pdwGrantedAccess], r15; pdwGrantedAccess
0x1800256e5  lea     rax, [rsp+430h+var_3E0]
0x1800256ea  mov     [rsp+430h+pdwFlags], rax; pdwFlags
0x1800256ef  lea     rax, [rbp+330h+var_3A8]
0x1800256f3  mov     [rsp+430h+pstrProfileXml], rax; unsigned int
0x1800256f8  xor     r9d, r9d; pReserved
0x1800256fb  mov     r8, rbx; strProfileName
0x1800256fe  mov     rdx, rsi; pInterfaceGuid
0x180025701  mov     rcx, [r12]; hClientHandle
0x180025705  call    cs:__imp_WlanGetProfile
0x18002570b  mov     rcx, [rbp+338h]; this
0x180025712  test    eax, eax
0x180025714  jz      short loc_18002572B
0x180025716  mov     r9d, eax; char *
0x180025719  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180025720  mov     edx, 9Fh; void *
0x180025725  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002572b  lea     rcx, [rbp+330h+var_3B0]
0x18002572f  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>(void)
0x180025734  call    ??$PopulateProfileXml@UWiFiProfileCost@WiFi@Data@Windows@@@WlanSyncTaskWlanToCDS@@CAXAEAV?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@wil@@PEBGAEBU_GUID@@1@Z; WlanSyncTaskWlanToCDS::PopulateProfileXml<Windows::Data::WiFi::WiFiProfileCost>(wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost> &,ushort const *,_GUID const &,ushort const *)
0x18002573a  mov     r12d, 8
0x180025740  cmp     eax, 1
0x180025743  jz      loc_1800258C0
0x180025749  cmp     eax, r12d
0x18002574c  jz      loc_1800258C0
0x180025752  mov     rax, [rsp+430h+var_3C8]
0x180025757  mov     [rbp+330h+var_390], rax
0x18002575b  xor     edx, edx; Val
0x18002575d  mov     r8d, 210h; Size
0x180025763  lea     rcx, [rbp+330h+var_250]; void *
0x18002576a  call    memset_0
0x18002576f  movups  xmm0, xmmword ptr [rsi]
0x180025772  movdqu  [rbp+330h+var_250], xmm0
0x18002577a  mov     r12d, 7
0x180025780  cmp     [rbx+18h], r12
0x180025784  jbe     short loc_18002578B
0x180025786  mov     r8, [rbx]
0x180025789  jmp     short loc_18002578E
0x18002578b  mov     r8, rbx; unsigned __int16 *
0x18002578e  mov     edx, 100h; unsigned __int64
0x180025793  lea     rcx, [rbp+330h+var_240]; unsigned __int16 *
0x18002579a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002579f  mov     rcx, [rbp+338h]; this
0x1800257a6  test    eax, eax
0x1800257a8  jns     short loc_1800257BF
0x1800257aa  mov     r9d, eax; char *
0x1800257ad  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x1800257b4  mov     edx, 0E0h; void *
0x1800257b9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800257bf  mov     [rsp+430h+var_3D0], r15
0x1800257c4  lea     rdx, [rsp+430h+var_3D0]
0x1800257c9  lea     rcx, [rbp+330h+var_250]
0x1800257d0  call    cs:__imp_DusmQueryUserCost
0x1800257d6  mov     rcx, [rbp+338h]; this
0x1800257dd  test    eax, eax
0x1800257df  jz      short loc_1800257F6
0x1800257e1  mov     r9d, eax; char *
0x1800257e4  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x1800257eb  mov     edx, 0E3h; void *
0x1800257f0  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800257f6  mov     ecx, dword ptr [rbp+330h+var_398]
0x1800257f9  movsxd  rax, dword ptr [rsp+430h+var_3D0]
0x1800257fe  mov     [rbp+330h+var_398], rax
0x180025802  cmp     [rbp+330h+var_378], r15b
0x180025806  jnz     short loc_18002582D
0x180025808  cmp     ecx, dword ptr [rsp+430h+var_3D0]
0x18002580c  jnz     short loc_18002582D
0x18002580e  mov     esi, 0Bh
0x180025813  mov     [rsp+430h+var_3E0], esi
0x180025817  cmp     [rbx+18h], r12
0x18002581b  jbe     short loc_180025820
0x18002581d  mov     rbx, [rbx]
0x180025820  mov     [rbp+330h+var_3B0], rbx
0x180025824  lea     rdx, [rbp+330h+var_3B0]
0x180025828  jmp     loc_1800255E4
0x18002582d  mov     edx, r12d
0x180025830  lea     rcx, [rbp+330h+var_340]
0x180025834  call    ??R_lambda_834179fdd55a229c72548d3f0ce5fcd7_@@QEBA@W4WiFiSyncAction@@@Z; _lambda_834179fdd55a229c72548d3f0ce5fcd7_::operator()(WiFiSyncAction)
0x180025839  mov     rax, [rsp+430h+var_3D8]
0x18002583e  mov     [rsp+430h+pdwFlags], rax
0x180025843  mov     dword ptr [rsp+430h+pstrProfileXml], r15d
0x180025848  lea     r9, [rbp+330h+var_2D0]
0x18002584c  lea     r8, [rbp+330h+var_398]
0x180025850  lea     rdx, [rbp+330h+var_3B0]
0x180025854  lea     rcx, [rbp+330h+var_368]
0x180025858  call    ??$save@UWiFiProfileCost@WiFi@Data@Windows@@@cloud_store@wil@@QEAA?AVcloud_store_save_result@1@AEBV?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@1@AEBU?$ItemReference@UWiFiProfileCost@WiFi@Data@Windows@@@Platform@Data@Windows@@W4cloud_store_save_options@1@_KPEBD@Z; wil::cloud_store::save<Windows::Data::WiFi::WiFiProfileCost>(wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost> const &,Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfileCost> const &,wil::cloud_store_save_options,unsigned __int64,char const *)
0x18002585d  mov     [rsp+430h+var_3E0], r12d
0x180025862  cmp     [rbx+18h], r12
0x180025866  jbe     short loc_18002586B
0x180025868  mov     rbx, [rbx]
0x18002586b  mov     [rbp+330h+var_3B0], rbx
0x18002586f  lea     r8, [rdi+2Ch]
0x180025873  lea     rax, [rsp+430h+var_3E0]
0x180025878  mov     [rsp+430h+var_3F0], rax
0x18002587d  lea     rax, [rbp+330h+arg_38]
0x180025884  mov     [rsp+430h+var_3F8], rax
0x180025889  lea     rax, [rsp+430h+var_3C0]
0x18002588e  mov     [rsp+430h+pdwGrantedAccess], rax
0x180025893  lea     rax, [rsp+430h+var_3C8]
0x180025898  mov     [rsp+430h+pdwFlags], rax
0x18002589d  lea     rax, [rsp+430h+var_3B8]
0x1800258a2  mov     [rsp+430h+pstrProfileXml], rax
0x1800258a7  lea     r9, [rsp+430h+var_3D8]
0x1800258ac  lea     rdx, [rbp+330h+var_3B0]
0x1800258b0  mov     rcx, r14
0x1800258b3  call    ??$ActionTakenOnWiFiProfile@PEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEB_KAEB_KAEB_KAEB_KAEBKW4WiFiSyncAction@@@WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAAX$$QEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEB_K222AEBK$$QEAW4WiFiSyncAction@@@Z; WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<ushort const *,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,ulong const &,WiFiSyncAction>(ushort const * &&,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,ulong const &,WiFiSyncAction &&)
0x1800258b8  mov     esi, r12d
0x1800258bb  jmp     loc_180025A4F
0x1800258c0  mov     esi, r13d
0x1800258c3  cmp     eax, 1
0x1800258c6  cmovnz  esi, r12d
0x1800258ca  mov     [rsp+430h+var_3E0], esi
0x1800258ce  mov     edx, esi
0x1800258d0  lea     rcx, [rbp+330h+var_340]
0x1800258d4  call    ??R_lambda_834179fdd55a229c72548d3f0ce5fcd7_@@QEBA@W4WiFiSyncAction@@@Z; _lambda_834179fdd55a229c72548d3f0ce5fcd7_::operator()(WiFiSyncAction)
0x1800258d9  mov     rax, [rsp+430h+var_3D8]
0x1800258de  mov     [rsp+430h+pdwFlags], rax
0x1800258e3  mov     dword ptr [rsp+430h+pstrProfileXml], r12d
0x1800258e8  lea     r9, [rbp+330h+var_2D0]
0x1800258ec  lea     r8, [rbp+330h+var_398]
0x1800258f0  lea     rdx, [rbp+330h+var_3B0]
0x1800258f4  lea     rcx, [rbp+330h+var_368]
0x1800258f8  call    ??$save@UWiFiProfileCost@WiFi@Data@Windows@@@cloud_store@wil@@QEAA?AVcloud_store_save_result@1@AEBV?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@1@AEBU?$ItemReference@UWiFiProfileCost@WiFi@Data@Windows@@@Platform@Data@Windows@@W4cloud_store_save_options@1@_KPEBD@Z; wil::cloud_store::save<Windows::Data::WiFi::WiFiProfileCost>(wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost> const &,Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfileCost> const &,wil::cloud_store_save_options,unsigned __int64,char const *)
0x1800258fd  cmp     qword ptr [rbx+18h], 7
0x180025902  jbe     short loc_180025909
0x180025904  mov     rax, [rbx]
0x180025907  jmp     short loc_18002590C
0x180025909  mov     rax, rbx
0x18002590c  mov     [rbp+330h+var_3B0], rax
0x180025910  lea     r15, [rdi+2Ch]
0x180025914  lea     rax, [rsp+430h+var_3E0]
0x180025919  mov     [rsp+430h+var_3F0], rax
0x18002591e  lea     rax, [rbp+330h+arg_38]
0x180025925  mov     [rsp+430h+var_3F8], rax
0x18002592a  lea     rax, [rsp+430h+var_3C0]
0x18002592f  mov     [rsp+430h+pdwGrantedAccess], rax
0x180025934  lea     rax, [rsp+430h+var_3C8]
0x180025939  mov     [rsp+430h+pdwFlags], rax
0x18002593e  lea     rax, [rsp+430h+var_3B8]
0x180025943  mov     [rsp+430h+pstrProfileXml], rax
0x180025948  lea     r9, [rsp+430h+var_3D8]
0x18002594d  mov     r8, r15
0x180025950  lea     rdx, [rbp+330h+var_3B0]
0x180025954  mov     rcx, r14
0x180025957  call    ??$ActionTakenOnWiFiProfile@PEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEB_KAEB_KAEB_KAEB_KAEBKAEBW4WiFiSyncAction@@@WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAAX$$QEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEB_K222AEBKAEBW4WiFiSyncAction@@@Z; WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<ushort const *,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,ulong const &,WiFiSyncAction const &>(ushort const * &&,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,ulong const &,WiFiSyncAction const &)
0x18002595c  cmp     dword ptr [rdi+28h], 1
0x180025960  jnz     loc_180025A4F
0x180025966  cmp     qword ptr [rdi+18h], 7
0x18002596b  jbe     short loc_180025970
0x18002596d  mov     rdi, [rdi]
0x180025970  mov     r8, cs:?c_wiFiCloudStoreDataReferenceDefaultCollectionName@@3PEBGEB; ushort const * const c_wiFiCloudStoreDataReferenceDefaultCollectionName
0x180025977  mov     rdx, rdi
0x18002597a  lea     rcx, [rbp+330h+var_290]
0x180025981  call    ??$make_cloud_store_data_reference@UWiFiProfileCost@WiFi@Data@Windows@@@wil@@YA?AU?$ItemReference@UWiFiProfileCost@WiFi@Data@Windows@@@Platform@Data@Windows@@PEBG0@Z; wil::make_cloud_store_data_reference<Windows::Data::WiFi::WiFiProfileCost>(ushort const *,ushort const *)
0x180025986  nop
  ... truncated ...
```
