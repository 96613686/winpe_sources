# ProvHostManager::ProcessRequest(InboundRequestDetails *,Catalog *)

- ea: `0x18009858c`
- end: `0x18009934e`
- name: `?ProcessRequest@ProvHostManager@@QEAAHPEAVInboundRequestDetails@@PEAVCatalog@@@Z`
- size: `3522`
- prototype: `__int64 __fastcall(HANDLE *this, struct InboundRequestDetails *, const WCHAR *)`
- caller_count: `1`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d7530`

## callees

- `0x180005d10`
- `0x180019950`
- `0x18002b7a0`
- `0x18004e7e4`
- `0x180071cdc`
- `0x180071d20`
- `0x18008f6a0`
- `0x18009858c`
- `0x180099354`
- `0x18009977c`
- `0x180099f70`
- `0x18009bc00`
- `0x1800ba1d8`
- `0x1800bac30`
- `0x1800ddb10`
- `0x1800e219c`
- `0x1800f4100`
- `0x1800f5f04`
- `0x1800f9960`
- `0x1800fe3b0`
- `0x1800fe7a0`
- `0x18010d8c6`
- `0x180111270`
- `0x180112380`
- `0x1801123a8`
- `0x1801123e8`
- `0x1801133b0`
- `0x180165e04`
- `0x180169954`
- `0x180169a2c`
- `0x180169aec`
- `0x1801ba152`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180099180`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009931c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180099180`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009931c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009860d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098d95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098f35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099174`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099310`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009860d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098d95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098f35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099174`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099310`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180098ec6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180098ec6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180098e55`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180098e55`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180098600`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180098600`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x180098ab0`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x180098c06`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x180098ab0`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x180098c06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800990fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009910b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009911a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180099298`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800992a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800992b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800990fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009910b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009911a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180099298`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800992a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800992b6`

## string_xrefs

- `0x18009876f`: `onecore\admin\wmi\wmx\service\provhostmanager.cpp`
- `0x180098799`: `onecore\admin\wmi\wmx\service\provhostmanager.cpp`
- `0x1800991d0`: `onecore\admin\wmi\wmx\service\provhostmanager.cpp`
- `0x18009922c`: `onecore\admin\wmi\wmx\service\provhostmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ProvHostManager::ProcessRequest(HANDLE *this, struct InboundRequestDetails *a2, const WCHAR *a3)
{
  __int64 LastError; // rsi
  __int64 v7; // r15
  _DWORD *v8; // rdi
  struct IRequestContext *v9; // rsi
  _QWORD *v10; // rdx
  __int64 *v11; // rax
  unsigned int v12; // edi
  __int64 v13; // rcx
  unsigned int v14; // eax
  const CHAR *v15; // r13
  unsigned int v16; // edx
  int v17; // eax
  int v18; // r12d
  unsigned int v19; // r15d
  ProvHostManager *v20; // rcx
  int v21; // r8d
  int v22; // r9d
  ProvHostManager *v23; // rcx
  int v24; // r9d
  int v25; // eax
  ProvHostManager *v26; // rcx
  void *v27; // r12
  void *v28; // r13
  void *v29; // r15
  const unsigned __int16 *Value; // rax
  __int64 v31; // rax
  void (__fastcall *v32)(struct IRequestContext *, _QWORD); // rbx
  DWORD v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // r15d
  void (__fastcall *v36)(struct IRequestContext *, _QWORD); // rbx
  DWORD v37; // eax
  unsigned int v38; // eax
  unsigned int Packet; // eax
  HostMappingTableEntry *v40; // rbx
  int v41; // eax
  void *v42; // rbx
  int v43; // eax
  DWORD v44; // eax
  struct Packet *v45; // rdi
  HANDLE v46; // rax
  unsigned int v47; // esi
  bool v48; // si
  HostMappingTableEntry *v49; // rbx
  int v50; // eax
  void *v51; // rbx
  int v52; // eax
  DWORD v53; // eax
  LPUNKNOWN pUnk; // [rsp+40h] [rbp-C0h] BYREF
  void *v55; // [rsp+48h] [rbp-B8h] BYREF
  bool v56; // [rsp+50h] [rbp-B0h]
  int v57; // [rsp+54h] [rbp-ACh] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpValueName; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE *v60; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v63; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v64; // [rsp+88h] [rbp-78h] BYREF
  LPVOID v65; // [rsp+90h] [rbp-70h] BYREF
  LPVOID v66; // [rsp+98h] [rbp-68h]
  LPVOID Src[2]; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID pv[2]; // [rsp+B0h] [rbp-50h]
  __int64 v69; // [rsp+C0h] [rbp-40h]
  _QWORD v70[3]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v71; // [rsp+E8h] [rbp-18h]
  __int128 v72; // [rsp+F0h] [rbp-10h]
  __int64 v73; // [rsp+100h] [rbp+0h]
  __int64 v74; // [rsp+108h] [rbp+8h]
  int v75; // [rsp+110h] [rbp+10h]
  int v76; // [rsp+114h] [rbp+14h]
  char *v77; // [rsp+118h] [rbp+18h]
  __int128 v78; // [rsp+120h] [rbp+20h] BYREF
  __int128 v79; // [rsp+130h] [rbp+30h]
  __int128 v80; // [rsp+140h] [rbp+40h]
  __int64 v81; // [rsp+150h] [rbp+50h]

  lpValueName = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids);
  if ( WaitForSingleObject(this[33], 0xFFFFFFFF) )
  {
    LastError = GetLastError();
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)a2 + 9) + 72LL))(*((_QWORD *)a2 + 9), LastError);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        79,
        WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids,
        (unsigned int)LastError);
    return 0;
  }
  v60 = this;
  _InterlockedAdd((volatile signed __int32 *)this, 1u);
  if ( *((_DWORD *)this + 40) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids);
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)a2 + 9) + 72LL))(*((_QWORD *)a2 + 9), 1115);
    goto LABEL_14;
  }
  v7 = *((_QWORD *)a2 + 64);
  v69 = v7;
  v8 = (_DWORD *)*((_QWORD *)a2 + 10);
  v9 = (struct IRequestContext *)*((_QWORD *)a2 + 9);
  v55 = 0;
  pUnk = 0;
  v57 = 0;
  v56 = *(_DWORD *)(*((_QWORD *)a2 + 33) + 2864LL) == 1;
  if ( !(unsigned int)ProvHostManager::RetrieveHostForRequest(this, a2, &v55, &pUnk, &v57) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids);
LABEL_69:
    AutoCleanup<AutoReleaseEx<HostMappingTableEntry>,HostMappingTableEntry *>::ReleasePtr(&pUnk);
    AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&v55);
LABEL_14:
    AutoInterlockedIncrement::~AutoInterlockedIncrement((AutoInterlockedIncrement *)&v60);
    return 0;
  }
  if ( !v55 )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\provhostmanager.cpp", 0x3A8u, L"936", 0x54Fu, 0);
  if ( !pUnk )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\provhostmanager.cpp", 0x3A9u, L"937", 0x54Fu, 0);
  memset_0(v70, 0, 0x50u);
  v10 = (_QWORD *)*((_QWORD *)a2 + 82);
  v70[0] = v10[1];
  v70[1] = *((_QWORD *)a2 + 7);
  v70[2] = v10[2];
  v74 = v10[5];
  v75 = *((_DWORD *)a2 + 170);
  v76 = *((_DWORD *)a2 + 171);
  v77 = (char *)a2 + 120;
  v11 = (__int64 *)v10[3];
  if ( v11 )
  {
    v71 = *v11;
    v72 = *(_OWORD *)(v10[3] + 8LL);
    v73 = *(_QWORD *)(v10[3] + 24LL);
  }
  else
  {
    v71 = 0;
    v72 = 0;
    v73 = 0;
  }
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  LODWORD(v78) = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 24LL))(v8);
  DWORD1(v78) = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 32LL))(v8);
  DWORD2(v78) = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 40LL))(v8);
  HIDWORD(v78) = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 48LL))(v8);
  LODWORD(v79) = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 56LL))(v8);
  DWORD1(v79) = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 64LL))(v8);
  DWORD2(v79) = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 80LL))(v8);
  HIDWORD(v79) = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 72LL))(v8);
  LODWORD(v80) = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 88LL))(v8);
  DWORD1(v80) = v8[20];
  DWORD2(v80) = v8[22];
  LODWORD(v81) = v8[24];
  HIDWORD(v81) = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 168LL))(v8);
  v12 = v8[23];
  v13 = *(_QWORD *)(*((_QWORD *)a2 + 61) + 88LL);
  if ( v13 )
  {
    v14 = (*(__int64 (__fastcall **)(__int64, __int64, struct IRequestContext *))(*(_QWORD *)v13 + 8LL))(v13, 6009, v9);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids);
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)v9 + 72LL))(v9, 1359);
    v14 = 0;
  }
  if ( v14 < v12 )
    v12 = v14;
  HIDWORD(v80) = v12;
  v15 = *(const CHAR **)(v7 + 40);
  if ( v15 )
  {
    v16 = *(_DWORD *)(v7 + 48);
  }
  else
  {
    v16 = 0;
    v15 = Buf1;
  }
  *(_DWORD *)Data = v16;
  *(_OWORD *)Src = 0;
  *(_OWORD *)pv = 0;
  v17 = (*(__int64 (__fastcall **)(void *, const CHAR *, _QWORD, _QWORD *))(*(_QWORD *)v55 + 40LL))(v55, v15, v16, v70);
  v18 = v17;
  if ( v17 < 0 )
  {
    if ( *((_DWORD *)a2 + 116) == 13 && v17 == -2147023781 )
    {
      v19 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids);
    }
    else
    {
      v19 = (unsigned __int16)v17;
      if ( (v17 & 0x1FFF0000) != 0x70000 )
        v19 = v17;
      if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_OP_HOST_ABNORMAL_TERMINATION) )
        WSMan::LogEvent<long>((struct _EVENT_DESCRIPTOR *)&LOG_WSMAN_OP_HOST_ABNORMAL_TERMINATION);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids, v19);
    }
    hObject = this + 4;
    HostMappingTable::DeleteTableEntry((HostMappingTable *)(this + 4), (struct HostMappingTableEntry *)pUnk);
    CoDisconnectObject(pUnk, 0);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v55 + 64LL))(v55);
    v22 = v57;
    if ( v57 )
    {
      HostMappingTableEntry::SetHostUsable((HostMappingTableEntry *)pUnk, 0);
      v22 = v57;
    }
    if ( !(unsigned int)ProvHostManager::RequiresReRun(v20, a2, v21, v22) )
    {
      ProvHostManager::HandleFirstAttemptFailures(v23, a2, v18, v24);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids, v19);
      goto LABEL_69;
    }
    if ( !(unsigned int)ProvHostManager::RetrieveHostForRequest(this, a2, &v55, &pUnk, &v57) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids);
      goto LABEL_69;
    }
    v25 = (*(__int64 (__fastcall **)(void *, const CHAR *, _QWORD, _QWORD *))(*(_QWORD *)v55 + 40LL))(
            v55,
            v15,
            *(unsigned int *)Data,
            v70);
    if ( v25 < 0 )
    {
      ProvHostManager::HandleSecondAttemptFailures(v26, a2, v25);
      HostMappingTable::DeleteTableEntry((HostMappingTable *)hObject, (struct HostMappingTableEntry *)pUnk);
      CoDisconnectObject(pUnk, 0);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v55 + 64LL))(v55);
      if ( v57 )
        HostMappingTableEntry::SetHostUsable((HostMappingTableEntry *)pUnk, 0);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids, v19);
      goto LABEL_69;
    }
  }
  v27 = Src[0];
  v65 = Src[0];
  v28 = pv[0];
  v64 = pv[0];
  v29 = pv[1];
  v66 = pv[1];
  v63 = pv[1];
  if ( !ProvHostManager::PostProcessRequest(
          (ProvHostManager *)this,
          a2,
          (struct HostMappingTableEntry *)pUnk,
          (struct _WSMAN_PROVHOST_RESPONSE *)Src,
          (struct Catalog *)&v78,
          v57,
          v56) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids);
LABEL_74:
    AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v63);
    AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v64);
    AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v65);
    AutoCleanup<AutoReleaseEx<HostMappingTableEntry>,HostMappingTableEntry *>::ReleasePtr(&pUnk);
    AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&v55);
    goto LABEL_14;
  }
  if ( !v57 )
    goto LABEL_102;
  Value = (const unsigned __int16 *)PacketParser::PacketElement<unsigned short const *>::GetValue(*((_QWORD *)a2 + 33) + 3024LL);
  v31 = *((_QWORD *)Catalog::GetResource((Catalog *)lpValueName, Value, v9) + 2);
  if ( !*(_BYTE *)(v31 + 240) )
    goto LABEL_102;
  lpValueName = *(LPCWSTR *)v31;
  hObject = 0;
  if ( !(unsigned int)CSecurity::BeginRevertToSelf(&hObject, 0xCu) )
  {
    v32 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)v9 + 72LL);
    v33 = GetLastError();
    v32(v9, v33);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      v34 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)v9 + 152LL))(v9);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids, v34);
    }
    goto LABEL_74;
  }
  hKey = 0;
  v35 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSMAN\\AutoRestartList",
          0,
          3u,
          &hKey);
  if ( v35 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids, v35);
LABEL_90:
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)v9 + 72LL))(v9, v35);
    goto LABEL_91;
  }
  *(_DWORD *)Data = 0;
  v35 = RegSetValueExW(hKey, lpValueName, 0, 4u, Data, 4u);
  if ( v35 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        90,
        (unsigned int)WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids,
        (_DWORD)lpValueName,
        v35);
    goto LABEL_90;
  }
LABEL_91:
  if ( !(unsigned int)CSecurity::EndRevertToSelf(hObject) )
  {
    v36 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)v9 + 72LL);
    v37 = GetLastError();
    v36(v9, v37);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      v38 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)v9 + 152LL))(v9);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids, v38);
    }
    goto LABEL_97;
  }
  if ( v35 )
  {
LABEL_97:
    AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&hKey);
    AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v63);
    AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v64);
    AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v65);
    AutoCleanup<AutoReleaseEx<HostMappingTableEntry>,HostMappingTableEntry *>::ReleasePtr(&pUnk);
    AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&v55);
    goto LABEL_14;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids, lpValueName);
  AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&hKey);
  v29 = v66;
LABEL_102:
  lpValueName = 0;
  *(_DWORD *)Data = Src[1];
  v66 = 0;
  if ( !LODWORD(Src[1]) )
  {
    v45 = (struct Packet *)v66;
    goto LABEL_127;
  }
  Packet = PacketPool::GetPacket(*(PacketPool **)(v69 + 24), (unsigned int)Src[1], (struct Packet **)&lpValueName);
  LODWORD(hKey) = Packet;
  if ( Packet )
  {
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)v9 + 72LL))(v9, Packet);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        93,
        WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids,
        (unsigned int)hKey);
    if ( lpValueName )
      Packet::Recycle((Packet *)lpValueName);
    if ( v29 )
      CoTaskMemFree(v29);
    if ( v28 )
      CoTaskMemFree(v28);
    if ( v27 )
      CoTaskMemFree(v27);
    v40 = (HostMappingTableEntry *)pUnk;
    pUnk = 0;
    if ( v40 )
    {
      v41 = HostMappingTableEntry::ReleaseEx(v40);
      PrintReleaseTrace(v40, v41);
    }
    v42 = v55;
    v55 = 0;
    if ( v42 )
    {
      v43 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v42 + 16LL))(v42);
      PrintReleaseTrace(v42, v43);
    }
    v44 = GetLastError();
    _InterlockedDecrement((volatile signed __int32 *)this);
    SetLastError(v44);
    return 0;
  }
  v45 = (struct Packet *)lpValueName;
  v46 = (HANDLE)*((_QWORD *)lpValueName + 5);
  hObject = v46;
  v47 = *(_DWORD *)Data;
  if ( v46 )
  {
    if ( *((_DWORD *)lpValueName + 12) == *(_DWORD *)Data )
      goto LABEL_125;
  }
  else
  {
    hObject = (HANDLE)Buf1;
  }
  WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\provhostmanager.cpp", 0x47Bu, L"1147", 0x54Fu, 0);
  v46 = hObject;
LABEL_125:
  memcpy_0(v46, Src[0], v47);
LABEL_127:
  v48 = HIDWORD(Src[1]) != 0;
  if ( !*((_QWORD *)a2 + 89) )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\provhostmanager.cpp", 0x48Bu, L"1163", 0x54Fu, 0);
  lpValueName = 0;
  HostOperation::Send(*((HostOperation **)a2 + 89), v45, v48);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids);
  AutoCleanup<AutoLocklessItemRecycle<Packet>,Packet *>::ReleasePtr(&lpValueName);
  if ( v29 )
    CoTaskMemFree(v29);
  if ( v28 )
    CoTaskMemFree(v28);
  if ( v27 )
    CoTaskMemFree(v27);
  v49 = (HostMappingTableEntry *)pUnk;
  pUnk = 0;
  if ( v49 )
  {
    v50 = HostMappingTableEntry::ReleaseEx(v49);
    PrintReleaseTrace(v49, v50);
  }
  v51 = v55;
  v55 = 0;
  if ( v51 )
  {
    v52 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v51 + 16LL))(v51);
    PrintReleaseTrace(v51, v52);
  }
  v53 = GetLastError();
  _InterlockedDecrement((volatile signed __int32 *)this);
  SetLastError(v53);
  return 1;
}

```

## disassembly

```asm
0x18009858c  mov     [rsp-8+arg_18], rbx
0x180098591  push    rbp
0x180098592  push    rsi
0x180098593  push    rdi
0x180098594  push    r12
0x180098596  push    r13
0x180098598  push    r14
0x18009859a  push    r15
0x18009859c  lea     rbp, [rsp-60h]
0x1800985a1  sub     rsp, 160h
0x1800985a8  mov     rax, cs:__security_cookie
0x1800985af  xor     rax, rsp
0x1800985b2  mov     [rbp+90h+var_38], rax
0x1800985b6  mov     [rsp+190h+lpValueName], r8
0x1800985bb  mov     rbx, rdx
0x1800985be  mov     r14, rcx
0x1800985c1  lea     r13, WPP_GLOBAL_Control
0x1800985c8  mov     edi, 400h
0x1800985cd  lea     r15, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids
0x1800985d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800985db  cmp     rcx, r13
0x1800985de  jz      short loc_1800985F6
0x1800985e0  test    [rcx+1Ch], edi
0x1800985e3  jz      short loc_1800985F6
0x1800985e5  mov     edx, 4Eh ; 'N'
0x1800985ea  mov     r8, r15
0x1800985ed  mov     rcx, [rcx+10h]
0x1800985f1  call    WPP_SF_
0x1800985f6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800985f9  mov     rcx, [r14+108h]; hHandle
0x180098600  call    cs:__imp_WaitForSingleObject
0x180098606  xor     r12d, r12d
0x180098609  test    eax, eax
0x18009860b  jz      short loc_180098658
0x18009860d  call    cs:__imp_GetLastError
0x180098613  mov     esi, eax
0x180098615  mov     rcx, [rbx+48h]
0x180098619  mov     rdx, [rcx]
0x18009861c  mov     rax, [rdx+48h]
0x180098620  mov     edx, esi
0x180098622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098627  mov     rcx, cs:WPP_GLOBAL_Control
0x18009862e  cmp     rcx, r13
0x180098631  jz      short loc_180098651
0x180098633  mov     edi, 200h
0x180098638  test    [rcx+1Ch], edi
0x18009863b  jz      short loc_180098651
0x18009863d  lea     edx, [r12+4Fh]
0x180098642  mov     r9d, esi
0x180098645  mov     r8, r15
0x180098648  mov     rcx, [rcx+10h]
0x18009864c  call    WPP_SF_d
0x180098651  xor     eax, eax
0x180098653  jmp     loc_180099327
0x180098658  mov     [rsp+190h+var_128], r14
0x18009865d  mov     ecx, 1
0x180098662  lock add [r14], ecx
0x180098666  mov     eax, [r14+0A0h]
0x18009866d  test    eax, eax
0x18009866f  jz      short loc_1800986B5
0x180098671  mov     rcx, cs:WPP_GLOBAL_Control
0x180098678  cmp     rcx, r13
0x18009867b  jz      short loc_180098693
0x18009867d  test    [rcx+1Ch], edi
0x180098680  jz      short loc_180098693
0x180098682  mov     edx, 50h ; 'P'
0x180098687  mov     r8, r15
0x18009868a  mov     rcx, [rcx+10h]
0x18009868e  call    WPP_SF_
0x180098693  mov     rcx, [rbx+48h]
0x180098697  mov     rax, [rcx]
0x18009869a  mov     edx, 45Bh
0x18009869f  mov     rax, [rax+48h]
0x1800986a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800986a8  nop
0x1800986a9  lea     rcx, [rsp+190h+var_128]; this
0x1800986ae  call    ??1AutoInterlockedIncrement@@QEAA@XZ; AutoInterlockedIncrement::~AutoInterlockedIncrement(void)
0x1800986b3  jmp     short loc_180098651
0x1800986b5  mov     r15, [rbx+200h]
0x1800986bc  mov     [rbp+90h+var_D0], r15
0x1800986c0  mov     rdi, [rbx+50h]
0x1800986c4  mov     rsi, [rbx+48h]
0x1800986c8  mov     [rsp+190h+var_148], r12
0x1800986cd  mov     [rsp+190h+pUnk], r12
0x1800986d2  mov     [rsp+190h+var_13C], r12d
0x1800986d7  mov     rax, [rbx+108h]
0x1800986de  cmp     [rax+0B30h], ecx
0x1800986e4  setz    [rsp+190h+var_140]
0x1800986e9  lea     rax, [rsp+190h+var_13C]
0x1800986ee  mov     [rsp+190h+phkResult], rax
0x1800986f3  lea     r9, [rsp+190h+pUnk]
0x1800986f8  lea     r8, [rsp+190h+var_148]
0x1800986fd  mov     rdx, rbx
0x180098700  mov     rcx, r14
0x180098703  call    ?RetrieveHostForRequest@ProvHostManager@@AEAAHPEAVInboundRequestDetails@@AEAV?$AutoRelease@UIWSManProvHost@@@@AEAV?$AutoReleaseEx@VHostMappingTableEntry@@@@PEAHPEAVCatalog@@@Z; ProvHostManager::RetrieveHostForRequest(InboundRequestDetails *,AutoRelease<IWSManProvHost> &,AutoReleaseEx<HostMappingTableEntry> &,int *,Catalog *)
0x180098708  test    eax, eax
0x18009870a  jnz     short loc_180098751
0x18009870c  mov     rcx, cs:WPP_GLOBAL_Control
0x180098713  cmp     rcx, r13
0x180098716  jz      short loc_180098736
0x180098718  mov     edi, 200h
0x18009871d  test    [rcx+1Ch], edi
0x180098720  jz      short loc_180098736
0x180098722  lea     edx, [rax+51h]
0x180098725  lea     r8, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids
0x18009872c  mov     rcx, [rcx+10h]
0x180098730  call    WPP_SF_
0x180098735  nop
0x180098736  lea     rcx, [rsp+190h+pUnk]
0x18009873b  call    ?ReleasePtr@?$AutoCleanup@V?$AutoReleaseEx@VHostMappingTableEntry@@@@PEAVHostMappingTableEntry@@@@AEAAXXZ; AutoCleanup<AutoReleaseEx<HostMappingTableEntry>,HostMappingTableEntry *>::ReleasePtr(void)
0x180098740  nop
0x180098741  lea     rcx, [rsp+190h+var_148]
0x180098746  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@UIEnumWbemClassObject@@@@PEAUIEnumWbemClassObject@@@@AEAAXXZ; AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(void)
0x18009874b  nop
0x18009874c  jmp     loc_1800986A9
0x180098751  cmp     [rsp+190h+var_148], r12
0x180098756  jnz     short loc_18009877B
0x180098758  mov     [rsp+190h+phkResult], r12; struct IRequestContext *
0x18009875d  mov     r9d, 54Fh; unsigned int
0x180098763  lea     r8, a936; "936"
0x18009876a  mov     edx, 3A8h; unsigned int
0x18009876f  lea     rcx, aOnecoreAdminWm_100; "onecore\\admin\\wmi\\wmx\\service\\prov"...
0x180098776  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18009877b  cmp     [rsp+190h+pUnk], r12
0x180098780  jnz     short loc_1800987A5
0x180098782  mov     [rsp+190h+phkResult], r12; struct IRequestContext *
0x180098787  mov     r9d, 54Fh; unsigned int
0x18009878d  lea     r8, a937; "937"
0x180098794  mov     edx, 3A9h; unsigned int
0x180098799  lea     rcx, aOnecoreAdminWm_100; "onecore\\admin\\wmi\\wmx\\service\\prov"...
0x1800987a0  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800987a5  xor     edx, edx; Val
0x1800987a7  lea     r8d, [rdx+50h]; Size
0x1800987ab  lea     rcx, [rbp+90h+var_C0]; void *
0x1800987af  call    memset_0
0x1800987b4  mov     rdx, [rbx+290h]
0x1800987bb  mov     rax, [rdx+8]
0x1800987bf  mov     [rbp+90h+var_C0], rax
0x1800987c3  mov     rax, [rbx+38h]
0x1800987c7  mov     [rbp+90h+var_B8], rax
0x1800987cb  mov     rax, [rdx+10h]
0x1800987cf  mov     [rbp+90h+var_B0], rax
0x1800987d3  mov     rax, [rdx+28h]
0x1800987d7  mov     [rbp+90h+var_88], rax
0x1800987db  mov     eax, [rbx+2A8h]
0x1800987e1  mov     [rbp+90h+var_80], eax
0x1800987e4  mov     eax, [rbx+2ACh]
0x1800987ea  mov     [rbp+90h+var_7C], eax
0x1800987ed  lea     rax, [rbx+78h]
0x1800987f1  mov     [rbp+90h+var_78], rax
0x1800987f5  mov     rax, [rdx+18h]
0x1800987f9  test    rax, rax
0x1800987fc  jz      short loc_18009882B
0x1800987fe  mov     rax, [rax]
0x180098801  mov     [rbp+90h+var_A8], rax
0x180098805  mov     rax, [rdx+18h]
0x180098809  mov     rcx, [rax+8]
0x18009880d  mov     qword ptr [rbp+90h+var_A0], rcx
0x180098811  mov     rax, [rdx+18h]
0x180098815  mov     rcx, [rax+10h]
0x180098819  mov     qword ptr [rbp+90h+var_A0+8], rcx
0x18009881d  mov     rax, [rdx+18h]
0x180098821  mov     rcx, [rax+18h]
0x180098825  mov     [rbp+90h+var_90], rcx
0x180098829  jmp     short loc_18009883B
0x18009882b  mov     [rbp+90h+var_A8], r12
0x18009882f  xorps   xmm0, xmm0
0x180098832  movdqa  [rbp+90h+var_A0], xmm0
0x180098837  mov     [rbp+90h+var_90], r12
0x18009883b  xorps   xmm0, xmm0
0x18009883e  xor     eax, eax
0x180098840  movups  [rbp+90h+var_70], xmm0
0x180098844  movups  [rbp+90h+var_60], xmm0
0x180098848  movups  [rbp+90h+var_50], xmm0
0x18009884c  mov     [rbp+90h+var_40], rax
0x180098850  mov     rax, [rdi]
0x180098853  mov     rcx, rdi
0x180098856  mov     rax, [rax+18h]
0x18009885a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009885f  mov     dword ptr [rbp+90h+var_70], eax
0x180098862  mov     rax, [rdi]
0x180098865  mov     rcx, rdi
0x180098868  mov     rax, [rax+20h]
0x18009886c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098871  mov     dword ptr [rbp+90h+var_70+4], eax
0x180098874  mov     rax, [rdi]
0x180098877  mov     rcx, rdi
0x18009887a  mov     rax, [rax+28h]
0x18009887e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098883  mov     dword ptr [rbp+90h+var_70+8], eax
0x180098886  mov     rax, [rdi]
0x180098889  mov     rcx, rdi
0x18009888c  mov     rax, [rax+30h]
0x180098890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098895  mov     dword ptr [rbp+90h+var_70+0Ch], eax
0x180098898  mov     rax, [rdi]
0x18009889b  mov     rcx, rdi
0x18009889e  mov     rax, [rax+38h]
0x1800988a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800988a7  mov     dword ptr [rbp+90h+var_60], eax
0x1800988aa  mov     rax, [rdi]
0x1800988ad  mov     rcx, rdi
0x1800988b0  mov     rax, [rax+40h]
0x1800988b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800988b9  mov     dword ptr [rbp+90h+var_60+4], eax
0x1800988bc  mov     rax, [rdi]
0x1800988bf  mov     rcx, rdi
0x1800988c2  mov     rax, [rax+50h]
0x1800988c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800988cb  mov     dword ptr [rbp+90h+var_60+8], eax
0x1800988ce  mov     rax, [rdi]
0x1800988d1  mov     rcx, rdi
0x1800988d4  mov     rax, [rax+48h]
0x1800988d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800988dd  mov     dword ptr [rbp+90h+var_60+0Ch], eax
0x1800988e0  mov     rax, [rdi]
0x1800988e3  mov     rcx, rdi
0x1800988e6  mov     rax, [rax+58h]
0x1800988ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800988ef  mov     dword ptr [rbp+90h+var_50], eax
0x1800988f2  mov     eax, [rdi+50h]
0x1800988f5  mov     dword ptr [rbp+90h+var_50+4], eax
0x1800988f8  mov     eax, [rdi+58h]
0x1800988fb  mov     dword ptr [rbp+90h+var_50+8], eax
0x1800988fe  mov     eax, [rdi+60h]
0x180098901  mov     dword ptr [rbp+90h+var_40], eax
0x180098904  mov     rax, [rdi]
0x180098907  mov     rcx, rdi
0x18009890a  mov     rax, [rax+0A8h]
0x180098911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098916  mov     dword ptr [rbp+90h+var_40+4], eax
0x180098919  mov     edi, [rdi+5Ch]
0x18009891c  mov     rax, [rbx+1E8h]
0x180098923  mov     rcx, [rax+58h]
0x180098927  test    rcx, rcx
0x18009892a  jz      short loc_180098942
0x18009892c  mov     rax, [rcx]
0x18009892f  mov     r8, rsi
0x180098932  mov     edx, 1779h
0x180098937  mov     rax, [rax+8]
0x18009893b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098940  jmp     short loc_180098983
0x180098942  mov     rcx, cs:WPP_GLOBAL_Control
0x180098949  cmp     rcx, r13
0x18009894c  jz      short loc_18009896C
0x18009894e  test    dword ptr [rcx+1Ch], 40000h
0x180098955  jz      short loc_18009896C
0x180098957  mov     edx, 45h ; 'E'
0x18009895c  lea     r8, WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids
0x180098963  mov     rcx, [rcx+10h]
0x180098967  call    WPP_SF_
0x18009896c  mov     rax, [rsi]
0x18009896f  mov     edx, 54Fh
0x180098974  mov     rcx, rsi
0x180098977  mov     rax, [rax+48h]
0x18009897b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098980  mov     eax, r12d
0x180098983  cmp     eax, edi
0x180098985  cmovb   edi, eax
0x180098988  mov     dword ptr [rbp+90h+var_50+0Ch], edi
0x18009898b  mov     r13, [r15+28h]
0x18009898f  test    r13, r13
0x180098992  jz      short loc_18009899A
0x180098994  mov     edx, [r15+30h]
0x180098998  jmp     short loc_1800989A4
0x18009899a  mov     edx, r12d
0x18009899d  lea     r13, Buf1
0x1800989a4  mov     dword ptr [rsp+190h+Data], edx
0x1800989a8  xorps   xmm0, xmm0
0x1800989ab  movups  xmmword ptr [rbp+90h+Src], xmm0
0x1800989af  movups  xmmword ptr [rbp+90h+pv], xmm0
0x1800989b3  mov     rcx, [rsp+190h+var_148]
0x1800989b8  mov     rax, [rcx]
0x1800989bb  lea     r8, [rbp+90h+Src]
0x1800989bf  mov     qword ptr [rsp+190h+cbData], r8
0x1800989c4  lea     r8, [rbp+90h+var_70]
0x1800989c8  mov     [rsp+190h+phkResult], r8; struct Catalog *
0x1800989cd  lea     r9, [rbp+90h+var_C0]
0x1800989d1  mov     r8d, edx
0x1800989d4  mov     rdx, r13
0x1800989d7  mov     rax, [rax+28h]
0x1800989db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800989e0  mov     r12d, eax
0x1800989e3  mov     edi, 200h
0x1800989e8  test    eax, eax
0x1800989ea  jns     loc_180098C7C
0x1800989f0  cmp     dword ptr [rbx+1D0h], 0Dh
0x1800989f7  jnz     short loc_180098A31
0x1800989f9  cmp     eax, 8007045Bh
0x1800989fe  jnz     short loc_180098A31
0x180098a00  xor     r15d, r15d
0x180098a03  mov     rcx, cs:WPP_GLOBAL_Control
0x180098a0a  lea     rax, WPP_GLOBAL_Control
0x180098a11  cmp     rcx, rax
0x180098a14  jz      short loc_180098A93
0x180098a16  test    [rcx+1Ch], edi
0x180098a19  jz      short loc_180098A93
0x180098a1b  lea     edx, [r15+52h]
0x180098a1f  lea     r8, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids
0x180098a26  mov     rcx, [rcx+10h]
  ... truncated ...
```
