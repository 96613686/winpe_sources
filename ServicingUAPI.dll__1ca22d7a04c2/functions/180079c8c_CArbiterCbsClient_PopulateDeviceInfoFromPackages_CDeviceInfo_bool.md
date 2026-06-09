# CArbiterCbsClient::PopulateDeviceInfoFromPackages(CDeviceInfo *,bool)

- ea: `0x180079c8c`
- end: `0x18007adb2`
- name: `?PopulateDeviceInfoFromPackages@CArbiterCbsClient@@QEAAJPEAVCDeviceInfo@@_N@Z`
- size: `4390`
- prototype: `__int64 __fastcall(CArbiterCbsClient *__hidden this, struct CDeviceInfo *, bool)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180091aac`

## callees

- `0x1800031d0`
- `0x180003ba4`
- `0x1800062b8`
- `0x180007f68`
- `0x180009750`
- `0x18000aedc`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18003ddc8`
- `0x180051984`
- `0x1800721b4`
- `0x1800727f0`
- `0x1800747bc`
- `0x1800774a0`
- `0x180079c8c`
- `0x1800865f4`
- `0x180086fd8`
- `0x1800ebb74`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007a2f2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007a318`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007a33e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007a2f2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007a318`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007a33e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079ef6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a2c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a3cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a40b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a43d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a53d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a63d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a6ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a7ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a8e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007aa17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007aabd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007abff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007acb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ad23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079ef6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a2c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a3cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a40b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a43d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a53d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a63d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a6ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a7ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a8e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007aa17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007aabd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007abff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007acb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ad23`

## string_xrefs

- `0x180079f3e`: `Failed to open package: {0} but proceeding to add it to device inventory because of repair/IPU scenario`
- `0x180079e6f`: `Failed to open package: {0}`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CArbiterCbsClient::PopulateDeviceInfoFromPackages(wchar_t *this, struct CDeviceInfo *a2, char a3)
{
  wchar_t *v3; // r12
  int v4; // eax
  unsigned int v5; // ebx
  struct ICbsIdentity *v7; // rbx
  char v8; // r13
  unsigned int v9; // esi
  int v10; // eax
  __int64 v11; // rdx
  int v12; // edi
  __int64 v13; // rcx
  __int64 v14; // rdx
  int v15; // eax
  unsigned int v16; // edi
  __int64 v17; // rdx
  wchar_t *v18; // r12
  const WCHAR *v19; // r15
  struct CDeviceInfo *v20; // rdi
  __int64 v21; // rax
  const WCHAR *v22; // rcx
  __int128 v23; // rax
  __int64 v24; // rdi
  __int64 v25; // rax
  const WCHAR *v26; // rcx
  __int128 v27; // rax
  int v28; // eax
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rdx
  wchar_t *v34; // r15
  int v35; // eax
  __int64 v36; // rdx
  int v37; // eax
  int v38; // eax
  __int64 v39; // rdx
  int v40; // eax
  wchar_t **bIgnoreCase; // [rsp+20h] [rbp-E0h]
  wchar_t **bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  wchar_t **bIgnoreCaseb; // [rsp+20h] [rbp-E0h]
  wchar_t **v44; // [rsp+28h] [rbp-D8h]
  wchar_t **v45; // [rsp+28h] [rbp-D8h]
  wchar_t **v46; // [rsp+30h] [rbp-D0h]
  wchar_t **v47; // [rsp+30h] [rbp-D0h]
  int v48; // [rsp+38h] [rbp-C8h]
  __int64 *v49; // [rsp+40h] [rbp-C0h]
  wchar_t *v50; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v51; // [rsp+58h] [rbp-A8h] BYREF
  struct CDeviceInfo *v52; // [rsp+60h] [rbp-A0h]
  wchar_t *v53; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v54; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *v55; // [rsp+78h] [rbp-88h] BYREF
  __int128 v56; // [rsp+80h] [rbp-80h] BYREF
  __int128 v57; // [rsp+90h] [rbp-70h]
  wchar_t *v58; // [rsp+A0h] [rbp-60h] BYREF
  LPCWCH lpString1; // [rsp+A8h] [rbp-58h] BYREF
  struct ICbsIdentity *v60; // [rsp+B0h] [rbp-50h]
  __int128 v61; // [rsp+B8h] [rbp-48h] BYREF
  const wchar_t *v62; // [rsp+C8h] [rbp-38h]
  __int128 v63; // [rsp+D0h] [rbp-30h]
  const wchar_t *v64; // [rsp+E0h] [rbp-20h]
  __int64 v65; // [rsp+E8h] [rbp-18h]
  __int64 v66; // [rsp+F0h] [rbp-10h] BYREF
  struct ICbsIdentity *v67; // [rsp+F8h] [rbp-8h] BYREF
  LPVOID pv; // [rsp+100h] [rbp+0h] BYREF
  struct ICbsPackage *v69; // [rsp+108h] [rbp+8h] BYREF
  wchar_t *v70; // [rsp+110h] [rbp+10h] BYREF
  wchar_t *v71; // [rsp+118h] [rbp+18h] BYREF
  unsigned int v72; // [rsp+120h] [rbp+20h] BYREF
  int v73; // [rsp+124h] [rbp+24h] BYREF
  wchar_t *v74; // [rsp+128h] [rbp+28h] BYREF
  __int64 v75; // [rsp+130h] [rbp+30h] BYREF
  wchar_t *String1; // [rsp+138h] [rbp+38h] BYREF
  int v77; // [rsp+140h] [rbp+40h] BYREF
  int v78; // [rsp+144h] [rbp+44h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v65 = -2;
  v52 = a2;
  v3 = this;
  v74 = this;
  v75 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 2) + 56LL))(
         *((_QWORD *)this + 2),
         a3 != 0 ? 144 : 496,
         &v75);
  v5 = v4;
  if ( v4 < 0 )
  {
    v73 = v4;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed enumerating packages");
      v51 = (wchar_t *)&v73;
      bIgnoreCase = &v51;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        1,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x326,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      (const char *)v5,
      (int)bIgnoreCase);
    if ( v75 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
    return v5;
  }
  v67 = 0;
  v7 = 0;
  v60 = 0;
  v51 = 0;
  v8 = 0;
  v77 = 0;
  while ( 1 )
  {
    if ( v67 )
      goto LABEL_243;
    if ( (*(unsigned int (__fastcall **)(__int64, __int64, struct ICbsIdentity **, int *))(*(_QWORD *)v75 + 24LL))(
           v75,
           1,
           &v67,
           &v77)
      || !v77 )
    {
      break;
    }
    v70 = 0;
    pv = 0;
    v69 = 0;
    v73 = 0;
    v78 = 0;
    v9 = (*(__int64 (__fastcall **)(struct ICbsIdentity *, LPVOID *))(*(_QWORD *)v67 + 64LL))(v67, &pv);
    if ( (v9 & 0x80000000) != 0 )
    {
      v72 = v9;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed getting Identity as string");
        v50 = (wchar_t *)&v72;
        bIgnoreCase = &v50;
        LOBYTE(v33) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v33,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x336,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
        (const char *)v9,
        (int)bIgnoreCase);
      if ( v69 )
      {
        (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v69 + 16LL))(v69);
        v69 = 0;
      }
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v70 )
      {
        operator delete(v70 - 4);
        v70 = 0;
      }
      if ( v7 )
        (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
      if ( v67 )
      {
        (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v67 + 16LL))(v67);
        v67 = 0;
      }
      if ( v75 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
      return v9;
    }
    if ( v69 )
    {
      INTERNAL_ERROR_ACTION(-1073741595);
LABEL_243:
      INTERNAL_ERROR_ACTION(-1073741595);
LABEL_244:
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x18007ADB1LL);
    }
    v10 = CArbiterCbsClient::OpenPackage((CArbiterCbsClient *)v3, v67, &v69);
    v12 = v10;
    if ( v10 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(struct ICbsPackage *, int *, int *))(*(_QWORD *)v69 + 96LL))(v69, &v73, &v78);
      if ( (v9 & 0x80000000) != 0 )
      {
        v72 = v9;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed getting package status");
          v50 = (wchar_t *)&v72;
          bIgnoreCase = &v50;
          LOBYTE(v32) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v32,
            3,
            ": {}");
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x354,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
          (const char *)v9,
          (int)bIgnoreCase);
        if ( v69 )
        {
          (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v69 + 16LL))(v69);
          v69 = 0;
        }
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        if ( v70 )
        {
          operator delete(v70 - 4);
          v70 = 0;
        }
        if ( v7 )
          (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
        if ( v67 )
        {
          (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v67 + 16LL))(v67);
          v67 = 0;
        }
        if ( v75 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
        return v9;
      }
      if ( v73 != 4 && v73 != -17 && v73 < 6 )
      {
        if ( v67 )
        {
          (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v67 + 16LL))(v67);
          v67 = 0;
        }
        if ( v69 )
        {
          (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v69 + 16LL))(v69);
          v69 = 0;
        }
        goto LABEL_21;
      }
    }
    else
    {
      LODWORD(v71) = v10;
      v13 = *(_QWORD *)&LogAdapter::g_Logger;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          1,
          "Failed to open package: {0}",
          &pv,
          v44,
          v46,
          v48,
          v49);
        v55 = (wchar_t *)&v71;
        bIgnoreCase = &v55;
        LOBYTE(v14) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v14,
          1,
          ": {0}");
        v13 = *(_QWORD *)&LogAdapter::g_Logger;
      }
      if ( v12 == -2146498555 )
      {
        if ( v67 )
        {
          (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v67 + 16LL))(v67);
          v67 = 0;
        }
        if ( v69 )
        {
          (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v69 + 16LL))(v69);
          v69 = 0;
        }
LABEL_21:
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        goto LABEL_23;
      }
      if ( !*((_BYTE *)v3 + 41) )
      {
        if ( v67 )
        {
          (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v67 + 16LL))(v67);
          v67 = 0;
        }
        if ( v69 )
        {
          (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v69 + 16LL))(v69);
          v69 = 0;
        }
        goto LABEL_21;
      }
      if ( v13 )
      {
        LOBYTE(v11) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
          v13,
          v11,
          1,
          "Failed to open package: {0} but proceeding to add it to device inventory because of repair/IPU scenario",
          &pv,
          v44,
          v46,
          v48,
          v49);
      }
    }
    v15 = SczAllocFromSz(&v70);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x362,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
        (const char *)(unsigned int)v15,
        (int)bIgnoreCase);
      if ( v69 )
      {
        (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v69 + 16LL))(v69);
        v69 = 0;
      }
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v70 )
      {
        operator delete(v70 - 4);
        v70 = 0;
      }
      if ( v7 )
        (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
      if ( v67 )
      {
        (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v67 + 16LL))(v67);
        v67 = 0;
      }
      if ( v75 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
      return v16;
    }
    lpString1 = 0;
    v53 = 0;
    v54 = 0;
    v58 = 0;
    v71 = 0;
    v9 = ShredStringIdIntoAttributes(
           v70,
           0x7Eu,
           &lpString1,
           (const wchar_t **)&v53,
           (const wchar_t **)&v58,
           (const wchar_t **)&v54,
           (const wchar_t **)&v71);
    if ( (v9 & 0x80000000) != 0 )
    {
      v72 = v9;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<AutoScz>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to shred keyform: {0}",
          &v70);
        v50 = (wchar_t *)&v72;
        bIgnoreCasea = &v50;
        LOBYTE(v31) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v31,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36B,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
        (const char *)v9,
        (int)bIgnoreCasea);
      if ( v69 )
      {
        (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v69 + 16LL))(v69);
        v69 = 0;
      }
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v70 )
      {
        operator delete(v70 - 4);
        v70 = 0;
      }
      if ( v7 )
        (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
      if ( v67 )
      {
        (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v67 + 16LL))(v67);
        v67 = 0;
      }
      if ( v75 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
      return v9;
    }
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LOBYTE(v17) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v17,
        1,
        "CBS: Package Keyform: {0}",
        &pv,
        v45,
        v47,
        v48,
        v49);
    }
    v66 = 0;
    v49 = &v66;
    v48 = 0;
    v18 = v71;
    v46 = (wchar_t **)v71;
    v44 = (wchar_t **)v58;
    LOBYTE(bIgnoreCasea) = 0;
    v19 = lpString1;
    v20 = v52;
    v9 = CDeviceInfo::AddOnDevicePackage(v52, lpString1, pv, 0);
    if ( (v9 & 0x80000000) != 0 )
    {
      LODWORD(v71) = v9;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to add on-device package");
        v53 = (wchar_t *)&v71;
        bIgnoreCasea = &v53;
        LOBYTE(v30) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v30,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37A,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
        (const char *)v9,
        (int)bIgnoreCasea);
      if ( v69 )
      {
        (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v69 + 16LL))(v69);
        v69 = 0;
      }
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v70 )
      {
        operator delete(v70 - 4);
        v70 = 0;
      }
      if ( v7 )
        (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
      if ( v67 )
      {
        (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v67 + 16LL))(v67);
        v67 = 0;
      }
      if ( v75 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
      return v9;
    }
    if ( v66 )
    {
      String1 = 0;
      if ( v73 == 4 )
      {
        *(_DWORD *)(v66 + 60) = 16;
      }
      else if ( v73 == -17 )
      {
        *(_DWORD *)(v66 + 60) = 32;
      }
      if ( v69 )
      {
        if ( String1 )
          goto LABEL_244;
        if ( !(*(unsigned int (__fastcall **)(struct ICbsPackage *, __int64, wchar_t **))(*(_QWORD *)v69 + 32LL))(
                v69,
                56,
                &String1)
          && !wcsicmp(String1, L"1") )
        {
          *(_DWORD *)(v66 + 60) |= 0x40u;
        }
      }
      if ( *(_DWORD *)v74 == 1 )
      {
        if ( (unsigned int)(v73 - 7) > 1 )
        {
LABEL_67:
          if ( !v8 && (unsigned int)(v73 - 7) <= 1 )
          {
            if ( v19 )
            {
              v25 = -1;
              do
                ++v25;
              while ( v19[v25] );
              *(_QWORD *)&v27 = 2 * v25;
              v26 = v19;
              *((_QWORD *)&v27 + 1) = v27 + 2;
            }
            else
            {
              v26 = 0;
              v27 = 0u;
            }
            v56 = v27;
            *(_QWORD *)&v57 = v26;
            if ( (unsigned __int8)Windows::StringUtil::IsStringLowerCaseAsciiPrefixEqualCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(
                                    ___LiteralObject__2U__BaseLiteralBuffer__0CG_U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0GN__0GJ__0GD__0HC__0GP__0HD__0GP__0GG__0HE__0CN__0HH__0GJ__0GO__0GE__0GP__0HH__0HD__0CN__0HD__0GF__0HC__0HG__0GJ__0GD__0GJ__0GO__0GH__0HD__0HE__0GB__0GD__0GL__0CN__0GG__0HF__0GM__0GM__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__0BC__0BD__0BE__0BF__0BG__0BH__0BI__0BJ__0BK__0BL__0BM__0BN__0BO__0BP__0CA__0CB__0CC__0CD__0CE__0CF__Details_RtlStringLiterals__3U_LUNICODE_STRING__B,
                                    &v56,
                                    0) )
            {
              if ( v7 )
              {
                (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
                v60 = 0;
              }
              v7 = v67;
              (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v67 + 8LL))(v67);
              v60 = v7;
              v51 = (wchar_t *)v66;
            }
          }
        }
        else
        {
          v61 = ___LiteralObject__2U__BaseLiteralBuffer__0BL_U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0HA__0GB__0GD__0GL__0GB__0GH__0GF__0FP__0GG__0GP__0HC__0FP__0HD__0GF__0HC__0HG__0GJ__0GD__0GJ__0GO__0GH__0HD__0HE__0GB__0GD__0GL__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__0BC__0BD__0BE__0BF__0BG__0BH__0BI__0BJ__0BK__Details_RtlStringLiterals__3U_LUNICODE_STRING__B;
          v62 = L"package_for_servicingstack";
          v63 = ___LiteralObject__2U__BaseLiteralBuffer__0CI_U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0GN__0GJ__0GD__0HC__0GP__0HD__0GP__0GG__0HE__0CN__0HH__0GJ__0GO__0GE__0GP__0HH__0HD__0CN__0HD__0GF__0HC__0HG__0GJ__0GD__0GJ__0GO__0GH__0HD__0HE__0GB__0GD__0GL__0CN__0GO__0GB__0HE__0GJ__0HG__0GF__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__0BC__0BD__0BE__0BF__0BG__0BH__0BI__0BJ__0BK__0BL__0BM__0BN__0BO__0BP__0CA__0CB__0CC__0CD__0CE__0CF__0CG__0CH__Details_RtlStringLiterals__3U_LUNICODE_STRING__B;
          v64 = L"microsoft-windows-servicingstack-native";
          if ( v19 )
          {
            v21 = -1;
            do
              ++v21;
            while ( v19[v21] );
            *(_QWORD *)&v23 = 2 * v21;
            v22 = v19;
            *((_QWORD *)&v23 + 1) = v23 + 2;
          }
          else
          {
            v22 = 0;
            v23 = 0u;
          }
          v56 = v23;
          *(_QWORD *)&v57 = v22;
          v24 = 0;
          while ( !(unsigned __int8)Windows::StringUtil::IsStringLowerCaseAsciiPrefixEqualCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(
                                      (char *)&v61 + 24 * v24,
                                      &v56,
                                      0) )
          {
            if ( (unsigned __int64)++v24 >= 2 )
              goto LABEL_67;
          }
          v28 = AddSSUFeature(v18, pv, v52, v66);
          v16 = v28;
          if ( v28 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x39F,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
              (const char *)(unsigned int)v28,
              (int)bIgnoreCasea);
            if ( String1 )
            {
              CoTaskMemFree(String1);
              String1 = 0;
            }
            if ( v69 )
            {
              (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v69 + 16LL))(v69);
              v69 = 0;
            }
            if ( pv )
            {
              CoTaskMemFree(pv);
              pv = 0;
            }
            if ( v70 )
            {
              operator delete(v70 - 4);
              v70 = 0;
            }
            if ( v7 )
              (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
            if ( v67 )
            {
              (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v67 + 16LL))(v67);
              v67 = 0;
            }
            if ( v75 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
            return v16;
          }
          v8 = 1;
        }
      }
      if ( String1 )
      {
        CoTaskMemFree(String1);
        String1 = 0;
      }
      v20 = v52;
    }
    if ( CompareStringOrdinal(v19, -1, L"Microsoft-Windows-Client-LanguagePack-Package", -1, 1) == 2
      || CompareStringOrdinal(v19, -1, L"Microsoft-Windows-Server-LanguagePack-Package", -1, 1) == 2
      || CompareStringOrdinal(v19, -1, L"Microsoft-Windows-ServerDatacenterNano-LanguagePack-Package", -1, 1) == 2 )
    {
      v56 = 0;
      v57 = 0;
      v29 = -1;
      do
        ++v29;
      while ( v54[v29] );
      std::wstring::_Construct<1,wchar_t const *>(&v56);
      CDeviceInfo::AddSatelliteValue(v20, 0, &v56);
      std::wstring::~wstring(&v56);
    }
    if ( v67 )
    {
      (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v67 + 16LL))(v67);
      v67 = 0;
    }
    if ( v69 )
    {
      (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v69 + 16LL))(v69);
      v69 = 0;
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v3 = v74;
LABEL_23:
    if ( v70 )
    {
      operator delete(v70 - 4);
      v70 = 0;
    }
  }
  if ( !v8 )
  {
    if ( v7 )
    {
      v34 = v51;
      if ( v51 )
      {
        v74 = 0;
        v71 = 0;
        v35 = (*(__int64 (__fastcall **)(struct ICbsIdentity *, wchar_t **))(*(_QWORD *)v7 + 64LL))(v7, &v71);
        v9 = v35;
        if ( v35 < 0 )
        {
          v72 = v35;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "Failed getting Identity as string");
            v50 = (wchar_t *)&v72;
            bIgnoreCase = &v50;
            LOBYTE(v36) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v36,
              3,
              ": {}");
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3C1,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
            (const char *)v9,
            (int)bIgnoreCase);
          if ( v71 )
          {
            CoTaskMemFree(v71);
            v71 = 0;
          }
          if ( v74 )
          {
            operator delete(v74 - 4);
            v74 = 0;
          }
          (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
          if ( v67 )
          {
            (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v67 + 16LL))(v67);
            v67 = 0;
          }
          if ( v75 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
          return v9;
        }
        v37 = SczAllocFromSz(&v74);
        v16 = v37;
        if ( v37 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3C2,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
            (const char *)(unsigned int)v37,
            (int)bIgnoreCase);
          if ( v71 )
          {
            CoTaskMemFree(v71);
            v71 = 0;
          }
          if ( v74 )
          {
            operator delete(v74 - 4);
            v74 = 0;
          }
          (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
          if ( v67 )
          {
            (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v67 + 16LL))(v67);
            v67 = 0;
          }
          if ( v75 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
          return v16;
        }
        v54 = 0;
        v55 = 0;
        v50 = 0;
        v53 = 0;
        v51 = 0;
        v38 = ShredStringIdIntoAttributes(
                v74,
                0x7Eu,
                (const wchar_t **)&v54,
                (const wchar_t **)&v55,
                (const wchar_t **)&v53,
                (const wchar_t **)&v50,
                (const wchar_t **)&v51);
        v9 = v38;
        if ( v38 < 0 )
        {
          v72 = v38;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<AutoScz>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "Failed to shred keyform: {}",
              &v74);
            v50 = (wchar_t *)&v72;
            bIgnoreCaseb = &v50;
            LOBYTE(v39) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v39,
              3,
              ": {}");
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3CB,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
            (const char *)v9,
            (int)bIgnoreCaseb);
          if ( v71 )
          {
            CoTaskMemFree(v71);
            v71 = 0;
          }
          if ( v74 )
          {
            operator delete(v74 - 4);
            v74 = 0;
          }
          (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
          if ( v67 )
          {
            (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v67 + 16LL))(v67);
            v67 = 0;
          }
          if ( v75 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
          return v9;
        }
        v40 = AddSSUFeature(v51, v71, v52, v34);
        v16 = v40;
        if ( v40 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3CE,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
            (const char *)(unsigned int)v40,
            (int)bIgnoreCaseb);
          if ( v71 )
          {
            CoTaskMemFree(v71);
            v71 = 0;
          }
          if ( v74 )
          {
            operator delete(v74 - 4);
            v74 = 0;
          }
          (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
          if ( v67 )
          {
            (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v67 + 16LL))(v67);
            v67 = 0;
          }
          if ( v75 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
          return v16;
        }
        if ( v71 )
        {
          CoTaskMemFree(v71);
          v71 = 0;
        }
        if ( v74 )
          operator delete(v74 - 4);
      }
    }
  }
  if ( v7 )
    (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v67 )
  {
    (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v67 + 16LL))(v67);
    v67 = 0;
  }
  if ( v75 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
  return 0;
}

```

## disassembly

```asm
0x180079c8c  mov     rax, rsp
0x180079c8f  push    rbp
0x180079c90  push    rsi
0x180079c91  push    rdi
0x180079c92  push    r12
0x180079c94  push    r13
0x180079c96  push    r14
0x180079c98  push    r15
0x180079c9a  lea     rbp, [rsp-50h]
0x180079c9f  sub     rsp, 150h
0x180079ca6  mov     [rbp+80h+var_98], 0FFFFFFFFFFFFFFFEh
0x180079cae  mov     [rax+18h], rbx
0x180079cb2  mov     rax, cs:__security_cookie
0x180079cb9  xor     rax, rsp
0x180079cbc  mov     [rbp+80h+var_38], rax
0x180079cc0  mov     [rsp+180h+var_120], rdx
0x180079cc5  mov     r12, rcx
0x180079cc8  mov     [rbp+80h+var_58], rcx
0x180079ccc  neg     r8b
0x180079ccf  sbb     edx, edx
0x180079cd1  and     edx, 0FFFFFEA0h
0x180079cd7  add     edx, 1F0h
0x180079cdd  xor     esi, esi
0x180079cdf  mov     [rbp+80h+var_50], rsi
0x180079ce3  mov     rcx, [rcx+10h]
0x180079ce7  mov     rax, [rcx]
0x180079cea  lea     r8, [rbp+80h+var_50]
0x180079cee  mov     rax, [rax+38h]
0x180079cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079cf7  mov     ebx, eax
0x180079cf9  test    eax, eax
0x180079cfb  jns     loc_180079DAC
0x180079d01  mov     [rbp+80h+var_5C], eax
0x180079d04  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180079d0b  test    rcx, rcx
0x180079d0e  jz      short loc_180079D50
0x180079d10  lea     r9, aFailedEnumerat_0; "Failed enumerating packages"
0x180079d17  lea     edi, [rsi+3]
0x180079d1a  mov     r8d, edi
0x180079d1d  xor     edx, edx
0x180079d1f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180079d24  lea     rax, [rbp+80h+var_5C]
0x180079d28  mov     [rsp+180h+var_128], rax
0x180079d2d  lea     rax, [rsp+180h+var_128]
0x180079d32  mov     qword ptr [rsp+180h+bIgnoreCase], rax; int
0x180079d37  lea     r9, asc_1801CAFB4; ": {}"
0x180079d3e  mov     r8d, edi
0x180079d41  lea     edx, [rsi+1]
0x180079d44  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180079d4b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180079d50  mov     rcx, [rbp+88h]; this
0x180079d57  mov     r9d, ebx; char *
0x180079d5a  lea     r8, aOnecoreBaseSer_13; "onecore\\base\\servicing\\arbiter\\carb"...
0x180079d61  mov     edx, 326h; void *
0x180079d66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079d6b  nop
0x180079d6c  mov     rcx, [rbp+80h+var_50]
0x180079d70  test    rcx, rcx
0x180079d73  jz      short loc_180079D82
0x180079d75  mov     rax, [rcx]
0x180079d78  mov     rax, [rax+10h]
0x180079d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079d81  nop
0x180079d82  mov     eax, ebx
0x180079d84  mov     rcx, [rbp+80h+var_38]
0x180079d88  xor     rcx, rsp; StackCookie
0x180079d8b  call    __security_check_cookie
0x180079d90  mov     rbx, [rsp+180h+arg_10]
0x180079d98  add     rsp, 150h
0x180079d9f  pop     r15
0x180079da1  pop     r14
0x180079da3  pop     r13
0x180079da5  pop     r12
0x180079da7  pop     rdi
0x180079da8  pop     rsi
0x180079da9  pop     rbp
0x180079daa  retn
0x180079dac  mov     [rbp+80h+var_88], rsi
0x180079db0  mov     rbx, rsi
0x180079db3  mov     [rbp+80h+var_D0], rbx
0x180079db7  mov     [rsp+180h+var_128], rsi
0x180079dbc  mov     r13b, sil
0x180079dbf  mov     [rbp+80h+var_40], esi
0x180079dc2  mov     r14d, 1
0x180079dc8  cmp     [rbp+80h+var_88], rsi
0x180079dcc  jnz     loc_18007AD9C
0x180079dd2  mov     rcx, [rbp+80h+var_50]
0x180079dd6  mov     rax, [rcx]
0x180079dd9  lea     r9, [rbp+80h+var_40]
0x180079ddd  lea     r8, [rbp+80h+var_88]
0x180079de1  mov     edx, r14d
0x180079de4  mov     rax, [rax+18h]
0x180079de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079ded  test    eax, eax
0x180079def  jnz     loc_18007A959
0x180079df5  cmp     [rbp+80h+var_40], esi
0x180079df8  jbe     loc_18007A959
0x180079dfe  mov     [rbp+80h+var_70], rsi
0x180079e02  mov     [rbp+80h+pv], rsi
0x180079e06  mov     [rbp+80h+var_78], rsi
0x180079e0a  mov     [rbp+80h+var_5C], esi
0x180079e0d  mov     [rbp+80h+var_3C], esi
0x180079e10  mov     rcx, [rbp+80h+var_88]
0x180079e14  mov     rax, [rcx]
0x180079e17  lea     rdx, [rbp+80h+pv]
0x180079e1b  mov     rax, [rax+40h]
0x180079e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079e24  mov     esi, eax
0x180079e26  xor     r15d, r15d
0x180079e29  test    eax, eax
0x180079e2b  js      loc_18007A859
0x180079e31  xor     esi, esi
0x180079e33  cmp     [rbp+80h+var_78], rsi
0x180079e37  jnz     loc_18007AD91
0x180079e3d  lea     r8, [rbp+80h+var_78]; struct ICbsPackage **
0x180079e41  mov     rdx, [rbp+80h+var_88]; struct ICbsIdentity *
0x180079e45  mov     rcx, r12; this
0x180079e48  call    ?OpenPackage@CArbiterCbsClient@@QEAAJPEAUICbsIdentity@@PEAPEAUICbsPackage@@@Z; CArbiterCbsClient::OpenPackage(ICbsIdentity *,ICbsPackage * *)
0x180079e4d  mov     edi, eax
0x180079e4f  test    eax, eax
0x180079e51  jns     loc_180079F8C
0x180079e57  mov     dword ptr [rbp+80h+var_68], eax
0x180079e5a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180079e61  test    rcx, rcx
0x180079e64  jz      short loc_180079EB3
0x180079e66  lea     rax, [rbp+80h+pv]
0x180079e6a  mov     qword ptr [rsp+180h+bIgnoreCase], rax
0x180079e6f  lea     r9, aFailedToOpenPa; "Failed to open package: {0}"
0x180079e76  mov     r8d, r14d
0x180079e79  xor     edx, edx
0x180079e7b  call    ??$LogNumObjects@V?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(bool,LogAdapter::LogLevel,char const * const,Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)> const &)
0x180079e80  lea     rax, [rbp+80h+var_68]
0x180079e84  mov     [rsp+180h+var_108], rax
0x180079e89  lea     rax, [rsp+180h+var_108]
0x180079e8e  mov     qword ptr [rsp+180h+bIgnoreCase], rax
0x180079e93  lea     r9, a0; ": {0}"
0x180079e9a  mov     r8d, r14d
0x180079e9d  mov     dl, r14b
0x180079ea0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180079ea7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180079eac  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180079eb3  cmp     edi, 800F0805h
0x180079eb9  jnz     short loc_180079F25
0x180079ebb  mov     rcx, [rbp+80h+var_88]
0x180079ebf  test    rcx, rcx
0x180079ec2  jz      short loc_180079ED4
0x180079ec4  mov     rax, [rcx]
0x180079ec7  mov     rax, [rax+10h]
0x180079ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079ed0  mov     [rbp+80h+var_88], rsi
0x180079ed4  mov     rcx, [rbp+80h+var_78]
0x180079ed8  test    rcx, rcx
0x180079edb  jz      short loc_180079EED
0x180079edd  mov     rax, [rcx]
0x180079ee0  mov     rax, [rax+10h]
0x180079ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079ee9  mov     [rbp+80h+var_78], rsi
0x180079eed  mov     rcx, [rbp+80h+pv]; pv
0x180079ef1  test    rcx, rcx
0x180079ef4  jz      short loc_180079F06
0x180079ef6  call    cs:__imp_CoTaskMemFree
0x180079efd  nop     dword ptr [rax+rax+00h]
0x180079f02  mov     [rbp+80h+pv], rsi
0x180079f06  mov     rcx, [rbp+80h+var_70]
0x180079f0a  test    rcx, rcx
0x180079f0d  jz      loc_180079DC8
0x180079f13  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180079f17  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180079f1c  mov     [rbp+80h+var_70], rsi
0x180079f20  jmp     loc_180079DC8
0x180079f25  cmp     [r12+29h], sil
0x180079f2a  jz      short loc_180079F55
0x180079f2c  test    rcx, rcx
0x180079f2f  jz      loc_180079FFB
0x180079f35  lea     rax, [rbp+80h+pv]
0x180079f39  mov     qword ptr [rsp+180h+bIgnoreCase], rax
0x180079f3e  lea     r9, aFailedToOpenPa_0; "Failed to open package: {0} but proceed"...
0x180079f45  mov     r8d, r14d
0x180079f48  mov     dl, r14b
0x180079f4b  call    ??$LogNumObjects@V?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(bool,LogAdapter::LogLevel,char const * const,Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)> const &)
0x180079f50  jmp     loc_180079FFB
0x180079f55  mov     rcx, [rbp+80h+var_88]
0x180079f59  test    rcx, rcx
0x180079f5c  jz      short loc_180079F6E
0x180079f5e  mov     rax, [rcx]
0x180079f61  mov     rax, [rax+10h]
0x180079f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079f6a  mov     [rbp+80h+var_88], rsi
0x180079f6e  mov     rcx, [rbp+80h+var_78]
0x180079f72  test    rcx, rcx
0x180079f75  jz      short loc_180079F87
0x180079f77  mov     rax, [rcx]
0x180079f7a  mov     rax, [rax+10h]
0x180079f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079f83  mov     [rbp+80h+var_78], rsi
0x180079f87  jmp     loc_180079EED
0x180079f8c  mov     rcx, [rbp+80h+var_78]
0x180079f90  mov     rax, [rcx]
0x180079f93  lea     r8, [rbp+80h+var_3C]
0x180079f97  lea     rdx, [rbp+80h+var_5C]
0x180079f9b  mov     rax, [rax+60h]
0x180079f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079fa4  mov     esi, eax
0x180079fa6  test    eax, eax
0x180079fa8  js      loc_18007A75B
0x180079fae  mov     eax, [rbp+80h+var_5C]
0x180079fb1  cmp     eax, 4
0x180079fb4  jz      short loc_180079FF9
0x180079fb6  cmp     eax, 0FFFFFFEFh
0x180079fb9  jz      short loc_180079FF9
0x180079fbb  xor     esi, esi
0x180079fbd  cmp     eax, 6
0x180079fc0  jge     short loc_180079FFB
0x180079fc2  mov     rcx, [rbp+80h+var_88]
0x180079fc6  test    rcx, rcx
0x180079fc9  jz      short loc_180079FDB
0x180079fcb  mov     rax, [rcx]
0x180079fce  mov     rax, [rax+10h]
0x180079fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079fd7  mov     [rbp+80h+var_88], rsi
0x180079fdb  mov     rcx, [rbp+80h+var_78]
0x180079fdf  test    rcx, rcx
0x180079fe2  jz      short loc_180079FF4
0x180079fe4  mov     rax, [rcx]
0x180079fe7  mov     rax, [rax+10h]
0x180079feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079ff0  mov     [rbp+80h+var_78], rsi
0x180079ff4  jmp     loc_180079EED
0x180079ff9  xor     esi, esi
0x180079ffb  mov     rdx, [rbp+80h+pv]
0x180079fff  lea     rcx, [rbp+80h+var_70]
0x18007a003  call    SczAllocFromSz
0x18007a008  mov     edi, eax
0x18007a00a  test    eax, eax
0x18007a00c  js      loc_18007A6AC
0x18007a012  mov     [rbp+80h+lpString1], rsi
0x18007a016  mov     [rsp+180h+var_118], rsi
0x18007a01b  mov     [rsp+180h+var_110], rsi
0x18007a020  mov     [rbp+80h+var_E0], rsi
0x18007a024  mov     [rbp+80h+var_68], rsi
0x18007a028  mov     edx, 7Eh ; '~'; wchar_t
0x18007a02d  lea     rax, [rbp+80h+var_68]
0x18007a031  mov     [rsp+180h+var_150], rax; wchar_t **
0x18007a036  lea     rax, [rsp+180h+var_110]
0x18007a03b  mov     [rsp+180h+var_158], rax; wchar_t **
0x18007a040  lea     rax, [rbp+80h+var_E0]
0x18007a044  mov     qword ptr [rsp+180h+bIgnoreCase], rax; wchar_t **
0x18007a049  lea     r9, [rsp+180h+var_118]; wchar_t **
0x18007a04e  lea     r8, [rbp+80h+lpString1]; wchar_t **
0x18007a052  mov     rcx, [rbp+80h+var_70]; wchar_t *
0x18007a056  call    ?ShredStringIdIntoAttributes@@YAJPEA_W_WPEAPEB_W2222@Z; ShredStringIdIntoAttributes(wchar_t *,wchar_t,wchar_t const * *,wchar_t const * *,wchar_t const * *,wchar_t const * *,wchar_t const * *)
0x18007a05b  mov     esi, eax
0x18007a05d  xor     r15d, r15d
0x18007a060  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007a067  test    eax, eax
0x18007a069  js      loc_18007A5AC
0x18007a06f  test    rcx, rcx
0x18007a072  jz      short loc_18007A08F
0x18007a074  lea     rax, [rbp+80h+pv]
0x18007a078  mov     qword ptr [rsp+180h+bIgnoreCase], rax
0x18007a07d  lea     r9, aCbsPackageKeyf; "CBS: Package Keyform: {0}"
0x18007a084  mov     r8d, r14d
0x18007a087  mov     dl, r14b
0x18007a08a  call    ??$LogNumObjects@V?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(bool,LogAdapter::LogLevel,char const * const,Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)> const &)
0x18007a08f  mov     [rbp+80h+var_90], r15
0x18007a093  lea     rax, [rbp+80h+var_90]
0x18007a097  mov     [rsp+180h+var_140], rax
0x18007a09c  mov     [rsp+180h+var_148], r15d
0x18007a0a1  mov     r12, [rbp+80h+var_68]
0x18007a0a5  mov     [rsp+180h+var_150], r12
0x18007a0aa  mov     rax, [rbp+80h+var_E0]
0x18007a0ae  mov     [rsp+180h+var_158], rax
0x18007a0b3  mov     byte ptr [rsp+180h+bIgnoreCase], r15b; int
0x18007a0b8  xor     r9d, r9d
0x18007a0bb  mov     r8, [rbp+80h+pv]
0x18007a0bf  mov     r15, [rbp+80h+lpString1]
0x18007a0c3  mov     rdx, r15
0x18007a0c6  mov     rdi, [rsp+180h+var_120]
0x18007a0cb  mov     rcx, rdi
0x18007a0ce  call    ?AddOnDevicePackage@CDeviceInfo@@QEAAJQEB_W00_N00W4PackageFunction@ActionList@@PEAPEAUPackage@1@@Z; CDeviceInfo::AddOnDevicePackage(wchar_t const * const,wchar_t const * const,wchar_t const * const,bool,wchar_t const * const,wchar_t const * const,ActionList::PackageFunction,CDeviceInfo::Package * *)
0x18007a0d3  mov     esi, eax
0x18007a0d5  test    eax, eax
0x18007a0d7  js      loc_18007A4AC
0x18007a0dd  mov     rax, [rbp+80h+var_90]
0x18007a0e1  xor     esi, esi
0x18007a0e3  test    rax, rax
0x18007a0e6  jz      loc_18007A2D9
0x18007a0ec  mov     [rbp+80h+String1], rsi
0x18007a0f0  cmp     [rbp+80h+var_5C], 4
0x18007a0f4  jnz     short loc_18007A0FF
0x18007a0f6  mov     dword ptr [rax+3Ch], 10h
0x18007a0fd  jmp     short loc_18007A10C
0x18007a0ff  cmp     [rbp+80h+var_5C], 0FFFFFFEFh
0x18007a103  jnz     short loc_18007A10C
0x18007a105  mov     dword ptr [rax+3Ch], 20h ; ' '
0x18007a10c  mov     rcx, [rbp+80h+var_78]
0x18007a110  test    rcx, rcx
0x18007a113  jz      short loc_18007A154
0x18007a115  cmp     [rbp+80h+String1], rsi
0x18007a119  jnz     loc_18007ADA7
  ... truncated ...
```
