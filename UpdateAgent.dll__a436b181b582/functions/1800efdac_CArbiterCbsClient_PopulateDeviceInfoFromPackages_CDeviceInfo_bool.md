# CArbiterCbsClient::PopulateDeviceInfoFromPackages(CDeviceInfo *,bool)

- ea: `0x1800efdac`
- end: `0x1800f0ed2`
- name: `?PopulateDeviceInfoFromPackages@CArbiterCbsClient@@QEAAJPEAVCDeviceInfo@@_N@Z`
- size: `4390`
- prototype: `__int64 __fastcall(CArbiterCbsClient *__hidden this, struct CDeviceInfo *, bool)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800dbecc`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x180006934`
- `0x18000a0e8`
- `0x18000b508`
- `0x18000c4c4`
- `0x180012d94`
- `0x180023b20`
- `0x1800692fc`
- `0x18008b38c`
- `0x1800a76dc`
- `0x1800d09a0`
- `0x1800d1384`
- `0x1800e8c2c`
- `0x1800eab14`
- `0x1800ed5c0`
- `0x1800efdac`
- `0x1801417cc`
- `0x18014b0c8`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f0412`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f0438`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f045e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f0412`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f0438`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f045e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f0016`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f03e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f04ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f052b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f055d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f065d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f075d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f080a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f090a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f0a08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f0b37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f0bdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f0d1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f0dd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f0e43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f0016`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f03e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f04ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f052b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f055d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f065d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f075d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f080a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f090a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f0a08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f0b37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f0bdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f0d1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f0dd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f0e43`

## string_xrefs

- `0x1800f005e`: `Failed to open package: {0} but proceeding to add it to device inventory because of repair/IPU scenario`
- `0x1800eff8f`: `Failed to open package: {0}`

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
  const struct std::nothrow_t *v11; // rdx
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
  const struct std::nothrow_t *v30; // rdx
  __int64 v31; // rdx
  const struct std::nothrow_t *v32; // rdx
  __int64 v33; // rdx
  const struct std::nothrow_t *v34; // rdx
  const struct std::nothrow_t *v35; // rdx
  __int64 v36; // rdx
  const struct std::nothrow_t *v37; // rdx
  __int64 v38; // rdx
  const struct std::nothrow_t *v39; // rdx
  wchar_t *v40; // r15
  int v41; // eax
  __int64 v42; // rdx
  const struct std::nothrow_t *v43; // rdx
  int v44; // eax
  const struct std::nothrow_t *v45; // rdx
  int v46; // eax
  __int64 v47; // rdx
  const struct std::nothrow_t *v48; // rdx
  int v49; // eax
  const struct std::nothrow_t *v50; // rdx
  const struct std::nothrow_t *v51; // rdx
  wchar_t **bIgnoreCase; // [rsp+20h] [rbp-E0h]
  wchar_t **bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  wchar_t **bIgnoreCaseb; // [rsp+20h] [rbp-E0h]
  wchar_t *v55; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v56; // [rsp+58h] [rbp-A8h] BYREF
  struct CDeviceInfo *v57; // [rsp+60h] [rbp-A0h]
  wchar_t *v58; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v59; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *v60; // [rsp+78h] [rbp-88h] BYREF
  __int128 v61; // [rsp+80h] [rbp-80h] BYREF
  __int128 v62; // [rsp+90h] [rbp-70h]
  wchar_t *v63; // [rsp+A0h] [rbp-60h] BYREF
  LPCWCH lpString1; // [rsp+A8h] [rbp-58h] BYREF
  struct ICbsIdentity *v65; // [rsp+B0h] [rbp-50h]
  __int128 v66; // [rsp+B8h] [rbp-48h] BYREF
  const wchar_t *v67; // [rsp+C8h] [rbp-38h]
  __int128 v68; // [rsp+D0h] [rbp-30h]
  const wchar_t *v69; // [rsp+E0h] [rbp-20h]
  __int64 v70; // [rsp+E8h] [rbp-18h]
  __int64 v71; // [rsp+F0h] [rbp-10h]
  struct ICbsIdentity *v72; // [rsp+F8h] [rbp-8h] BYREF
  LPVOID pv; // [rsp+100h] [rbp+0h] BYREF
  struct ICbsPackage *v74; // [rsp+108h] [rbp+8h] BYREF
  wchar_t *v75; // [rsp+110h] [rbp+10h] BYREF
  wchar_t *v76; // [rsp+118h] [rbp+18h] BYREF
  unsigned int v77; // [rsp+120h] [rbp+20h] BYREF
  int v78; // [rsp+124h] [rbp+24h] BYREF
  wchar_t *v79; // [rsp+128h] [rbp+28h] BYREF
  __int64 v80; // [rsp+130h] [rbp+30h] BYREF
  wchar_t *String1; // [rsp+138h] [rbp+38h] BYREF
  int v82; // [rsp+140h] [rbp+40h] BYREF
  int v83; // [rsp+144h] [rbp+44h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v70 = -2;
  v57 = a2;
  v3 = this;
  v79 = this;
  v80 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 2) + 56LL))(
         *((_QWORD *)this + 2),
         a3 != 0 ? 144 : 496,
         &v80);
  v5 = v4;
  if ( v4 < 0 )
  {
    v78 = v4;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed enumerating packages");
      v56 = (wchar_t *)&v78;
      bIgnoreCase = &v56;
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
    if ( v80 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
    return v5;
  }
  v72 = 0;
  v7 = 0;
  v65 = 0;
  v56 = 0;
  v8 = 0;
  v82 = 0;
  while ( 1 )
  {
    if ( v72 )
      goto LABEL_243;
    if ( (*(unsigned int (__fastcall **)(__int64, __int64, struct ICbsIdentity **, int *))(*(_QWORD *)v80 + 24LL))(
           v80,
           1,
           &v72,
           &v82)
      || !v82 )
    {
      break;
    }
    v75 = 0;
    pv = 0;
    v74 = 0;
    v78 = 0;
    v83 = 0;
    v9 = (*(__int64 (__fastcall **)(struct ICbsIdentity *, LPVOID *))(*(_QWORD *)v72 + 64LL))(v72, &pv);
    if ( (v9 & 0x80000000) != 0 )
    {
      v77 = v9;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed getting Identity as string");
        v55 = (wchar_t *)&v77;
        bIgnoreCase = &v55;
        LOBYTE(v38) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v38,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x336,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
        (const char *)v9,
        (int)bIgnoreCase);
      if ( v74 )
      {
        (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v74 + 16LL))(v74);
        v74 = 0;
      }
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v75 )
      {
        operator delete(v75 - 4, v39);
        v75 = 0;
      }
      if ( v7 )
        (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
      if ( v72 )
      {
        (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v72 + 16LL))(v72);
        v72 = 0;
      }
      if ( v80 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      return v9;
    }
    if ( v74 )
    {
      INTERNAL_ERROR_ACTION(-1073741595);
LABEL_243:
      INTERNAL_ERROR_ACTION(-1073741595);
LABEL_244:
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x1800F0ED1LL);
    }
    v10 = CArbiterCbsClient::OpenPackage((CArbiterCbsClient *)v3, v72, &v74);
    v12 = v10;
    if ( v10 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(struct ICbsPackage *, int *, int *))(*(_QWORD *)v74 + 96LL))(v74, &v78, &v83);
      if ( (v9 & 0x80000000) != 0 )
      {
        v77 = v9;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed getting package status");
          v55 = (wchar_t *)&v77;
          bIgnoreCase = &v55;
          LOBYTE(v36) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v36,
            3,
            ": {}");
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x354,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
          (const char *)v9,
          (int)bIgnoreCase);
        if ( v74 )
        {
          (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v74 + 16LL))(v74);
          v74 = 0;
        }
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        if ( v75 )
        {
          operator delete(v75 - 4, v37);
          v75 = 0;
        }
        if ( v7 )
          (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
        if ( v72 )
        {
          (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v72 + 16LL))(v72);
          v72 = 0;
        }
        if ( v80 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
        return v9;
      }
      if ( v78 != 4 && v78 != -17 && v78 < 6 )
      {
        if ( v72 )
        {
          (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v72 + 16LL))(v72);
          v72 = 0;
        }
        if ( v74 )
        {
          (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v74 + 16LL))(v74);
          v74 = 0;
        }
        goto LABEL_21;
      }
    }
    else
    {
      LODWORD(v76) = v10;
      v13 = *(_QWORD *)&LogAdapter::g_Logger;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          1,
          "Failed to open package: {0}",
          &pv);
        v60 = (wchar_t *)&v76;
        bIgnoreCase = &v60;
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
        if ( v72 )
        {
          (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v72 + 16LL))(v72);
          v72 = 0;
        }
        if ( v74 )
        {
          (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v74 + 16LL))(v74);
          v74 = 0;
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
        if ( v72 )
        {
          (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v72 + 16LL))(v72);
          v72 = 0;
        }
        if ( v74 )
        {
          (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v74 + 16LL))(v74);
          v74 = 0;
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
          &pv);
      }
    }
    v15 = SczAllocFromSz(&v75, pv);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x362,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
        (const char *)(unsigned int)v15,
        (int)bIgnoreCase);
      if ( v74 )
      {
        (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v74 + 16LL))(v74);
        v74 = 0;
      }
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v75 )
      {
        operator delete(v75 - 4, v35);
        v75 = 0;
      }
      if ( v7 )
        (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
      if ( v72 )
      {
        (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v72 + 16LL))(v72);
        v72 = 0;
      }
      if ( v80 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      return v16;
    }
    lpString1 = 0;
    v58 = 0;
    v59 = 0;
    v63 = 0;
    v76 = 0;
    v9 = ShredStringIdIntoAttributes(
           v75,
           0x7Eu,
           &lpString1,
           (const wchar_t **)&v58,
           (const wchar_t **)&v63,
           (const wchar_t **)&v59,
           (const wchar_t **)&v76);
    if ( (v9 & 0x80000000) != 0 )
    {
      v77 = v9;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<AutoScz>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to shred keyform: {0}",
          &v75);
        v55 = (wchar_t *)&v77;
        bIgnoreCasea = &v55;
        LOBYTE(v33) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v33,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36B,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
        (const char *)v9,
        (int)bIgnoreCasea);
      if ( v74 )
      {
        (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v74 + 16LL))(v74);
        v74 = 0;
      }
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v75 )
      {
        operator delete(v75 - 4, v34);
        v75 = 0;
      }
      if ( v7 )
        (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
      if ( v72 )
      {
        (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v72 + 16LL))(v72);
        v72 = 0;
      }
      if ( v80 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
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
        &pv);
    }
    v71 = 0;
    v18 = v76;
    LOBYTE(bIgnoreCasea) = 0;
    v19 = lpString1;
    v20 = v57;
    v9 = CDeviceInfo::AddOnDevicePackage(v57, lpString1, pv, 0);
    if ( (v9 & 0x80000000) != 0 )
    {
      LODWORD(v76) = v9;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to add on-device package");
        v58 = (wchar_t *)&v76;
        bIgnoreCasea = &v58;
        LOBYTE(v31) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v31,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37A,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
        (const char *)v9,
        (int)bIgnoreCasea);
      if ( v74 )
      {
        (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v74 + 16LL))(v74);
        v74 = 0;
      }
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v75 )
      {
        operator delete(v75 - 4, v32);
        v75 = 0;
      }
      if ( v7 )
        (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
      if ( v72 )
      {
        (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v72 + 16LL))(v72);
        v72 = 0;
      }
      if ( v80 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      return v9;
    }
    if ( v71 )
    {
      String1 = 0;
      if ( v78 == 4 )
      {
        *(_DWORD *)(v71 + 60) = 16;
      }
      else if ( v78 == -17 )
      {
        *(_DWORD *)(v71 + 60) = 32;
      }
      if ( v74 )
      {
        if ( String1 )
          goto LABEL_244;
        if ( !(*(unsigned int (__fastcall **)(struct ICbsPackage *, __int64, wchar_t **))(*(_QWORD *)v74 + 32LL))(
                v74,
                56,
                &String1)
          && !wcsicmp(String1, L"1") )
        {
          *(_DWORD *)(v71 + 60) |= 0x40u;
        }
      }
      if ( *(_DWORD *)v79 == 1 )
      {
        if ( (unsigned int)(v78 - 7) > 1 )
        {
LABEL_67:
          if ( !v8 && (unsigned int)(v78 - 7) <= 1 )
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
            v61 = v27;
            *(_QWORD *)&v62 = v26;
            if ( (unsigned __int8)Windows::StringUtil::IsStringLowerCaseAsciiPrefixEqualCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(
                                    &___LiteralObject__2U__BaseLiteralBuffer__0CG_U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0GN__0GJ__0GD__0HC__0GP__0HD__0GP__0GG__0HE__0CN__0HH__0GJ__0GO__0GE__0GP__0HH__0HD__0CN__0HD__0GF__0HC__0HG__0GJ__0GD__0GJ__0GO__0GH__0HD__0HE__0GB__0GD__0GL__0CN__0GG__0HF__0GM__0GM__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__0BC__0BD__0BE__0BF__0BG__0BH__0BI__0BJ__0BK__0BL__0BM__0BN__0BO__0BP__0CA__0CB__0CC__0CD__0CE__0CF__Details_RtlStringLiterals__3U_LUNICODE_STRING__B,
                                    &v61,
                                    0) )
            {
              if ( v7 )
              {
                (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
                v65 = 0;
              }
              v7 = v72;
              (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v72 + 8LL))(v72);
              v65 = v7;
              v56 = (wchar_t *)v71;
            }
          }
        }
        else
        {
          v66 = ___LiteralObject__2U__BaseLiteralBuffer__0BL_U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0HA__0GB__0GD__0GL__0GB__0GH__0GF__0FP__0GG__0GP__0HC__0FP__0HD__0GF__0HC__0HG__0GJ__0GD__0GJ__0GO__0GH__0HD__0HE__0GB__0GD__0GL__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__0BC__0BD__0BE__0BF__0BG__0BH__0BI__0BJ__0BK__Details_RtlStringLiterals__3U_LUNICODE_STRING__B;
          v67 = L"package_for_servicingstack";
          v68 = ___LiteralObject__2U__BaseLiteralBuffer__0CI_U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0GN__0GJ__0GD__0HC__0GP__0HD__0GP__0GG__0HE__0CN__0HH__0GJ__0GO__0GE__0GP__0HH__0HD__0CN__0HD__0GF__0HC__0HG__0GJ__0GD__0GJ__0GO__0GH__0HD__0HE__0GB__0GD__0GL__0CN__0GO__0GB__0HE__0GJ__0HG__0GF__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__0BC__0BD__0BE__0BF__0BG__0BH__0BI__0BJ__0BK__0BL__0BM__0BN__0BO__0BP__0CA__0CB__0CC__0CD__0CE__0CF__0CG__0CH__Details_RtlStringLiterals__3U_LUNICODE_STRING__B;
          v69 = L"microsoft-windows-servicingstack-native";
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
          v61 = v23;
          *(_QWORD *)&v62 = v22;
          v24 = 0;
          while ( !(unsigned __int8)Windows::StringUtil::IsStringLowerCaseAsciiPrefixEqualCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(
                                      (char *)&v66 + 24 * v24,
                                      &v61,
                                      0) )
          {
            if ( (unsigned __int64)++v24 >= 2 )
              goto LABEL_67;
          }
          v28 = AddSSUFeature(v18, pv, v57, v71);
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
            if ( v74 )
            {
              (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v74 + 16LL))(v74);
              v74 = 0;
            }
            if ( pv )
            {
              CoTaskMemFree(pv);
              pv = 0;
            }
            if ( v75 )
            {
              operator delete(v75 - 4, v30);
              v75 = 0;
            }
            if ( v7 )
              (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
            if ( v72 )
            {
              (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v72 + 16LL))(v72);
              v72 = 0;
            }
            if ( v80 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
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
      v20 = v57;
    }
    if ( CompareStringOrdinal(v19, -1, L"Microsoft-Windows-Client-LanguagePack-Package", -1, 1) == 2
      || CompareStringOrdinal(v19, -1, L"Microsoft-Windows-Server-LanguagePack-Package", -1, 1) == 2
      || CompareStringOrdinal(v19, -1, L"Microsoft-Windows-ServerDatacenterNano-LanguagePack-Package", -1, 1) == 2 )
    {
      v61 = 0;
      v62 = 0;
      v29 = -1;
      do
        ++v29;
      while ( v59[v29] );
      std::wstring::_Construct<1,wchar_t const *>(&v61, v59, v29);
      CDeviceInfo::AddSatelliteValue(v20, 0, &v61);
      std::wstring::~wstring(&v61);
    }
    if ( v72 )
    {
      (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v72 + 16LL))(v72);
      v72 = 0;
    }
    if ( v74 )
    {
      (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v74 + 16LL))(v74);
      v74 = 0;
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v3 = v79;
LABEL_23:
    if ( v75 )
    {
      operator delete(v75 - 4, v11);
      v75 = 0;
    }
  }
  if ( !v8 )
  {
    if ( v7 )
    {
      v40 = v56;
      if ( v56 )
      {
        v79 = 0;
        v76 = 0;
        v41 = (*(__int64 (__fastcall **)(struct ICbsIdentity *, wchar_t **))(*(_QWORD *)v7 + 64LL))(v7, &v76);
        v9 = v41;
        if ( v41 < 0 )
        {
          v77 = v41;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "Failed getting Identity as string");
            v55 = (wchar_t *)&v77;
            bIgnoreCase = &v55;
            LOBYTE(v42) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v42,
              3,
              ": {}");
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3C1,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
            (const char *)v9,
            (int)bIgnoreCase);
          if ( v76 )
          {
            CoTaskMemFree(v76);
            v76 = 0;
          }
          if ( v79 )
          {
            operator delete(v79 - 4, v43);
            v79 = 0;
          }
          (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
          if ( v72 )
          {
            (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v72 + 16LL))(v72);
            v72 = 0;
          }
          if ( v80 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
          return v9;
        }
        v44 = SczAllocFromSz(&v79, v76);
        v16 = v44;
        if ( v44 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3C2,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
            (const char *)(unsigned int)v44,
            (int)bIgnoreCase);
          if ( v76 )
          {
            CoTaskMemFree(v76);
            v76 = 0;
          }
          if ( v79 )
          {
            operator delete(v79 - 4, v45);
            v79 = 0;
          }
          (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
          if ( v72 )
          {
            (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v72 + 16LL))(v72);
            v72 = 0;
          }
          if ( v80 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
          return v16;
        }
        v59 = 0;
        v60 = 0;
        v55 = 0;
        v58 = 0;
        v56 = 0;
        v46 = ShredStringIdIntoAttributes(
                v79,
                0x7Eu,
                (const wchar_t **)&v59,
                (const wchar_t **)&v60,
                (const wchar_t **)&v58,
                (const wchar_t **)&v55,
                (const wchar_t **)&v56);
        v9 = v46;
        if ( v46 < 0 )
        {
          v77 = v46;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<AutoScz>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "Failed to shred keyform: {}",
              &v79);
            v55 = (wchar_t *)&v77;
            bIgnoreCaseb = &v55;
            LOBYTE(v47) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v47,
              3,
              ": {}");
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3CB,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
            (const char *)v9,
            (int)bIgnoreCaseb);
          if ( v76 )
          {
            CoTaskMemFree(v76);
            v76 = 0;
          }
          if ( v79 )
          {
            operator delete(v79 - 4, v48);
            v79 = 0;
          }
          (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
          if ( v72 )
          {
            (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v72 + 16LL))(v72);
            v72 = 0;
          }
          if ( v80 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
          return v9;
        }
        v49 = AddSSUFeature(v56, v76, v57, v40);
        v16 = v49;
        if ( v49 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3CE,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
            (const char *)(unsigned int)v49,
            (int)bIgnoreCaseb);
          if ( v76 )
          {
            CoTaskMemFree(v76);
            v76 = 0;
          }
          if ( v79 )
          {
            operator delete(v79 - 4, v51);
            v79 = 0;
          }
          (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
          if ( v72 )
          {
            (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v72 + 16LL))(v72);
            v72 = 0;
          }
          if ( v80 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
          return v16;
        }
        if ( v76 )
        {
          CoTaskMemFree(v76);
          v76 = 0;
        }
        if ( v79 )
          operator delete(v79 - 4, v50);
      }
    }
  }
  if ( v7 )
    (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v72 )
  {
    (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v72 + 16LL))(v72);
    v72 = 0;
  }
  if ( v80 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
  return 0;
}

```

## disassembly

```asm
0x1800efdac  mov     rax, rsp
0x1800efdaf  push    rbp
0x1800efdb0  push    rsi
0x1800efdb1  push    rdi
0x1800efdb2  push    r12
0x1800efdb4  push    r13
0x1800efdb6  push    r14
0x1800efdb8  push    r15
0x1800efdba  lea     rbp, [rsp-50h]
0x1800efdbf  sub     rsp, 150h
0x1800efdc6  mov     [rbp+80h+var_98], 0FFFFFFFFFFFFFFFEh
0x1800efdce  mov     [rax+18h], rbx
0x1800efdd2  mov     rax, cs:__security_cookie
0x1800efdd9  xor     rax, rsp
0x1800efddc  mov     [rbp+80h+var_38], rax
0x1800efde0  mov     [rsp+180h+var_120], rdx
0x1800efde5  mov     r12, rcx
0x1800efde8  mov     [rbp+80h+var_58], rcx
0x1800efdec  neg     r8b
0x1800efdef  sbb     edx, edx
0x1800efdf1  and     edx, 0FFFFFEA0h
0x1800efdf7  add     edx, 1F0h
0x1800efdfd  xor     esi, esi
0x1800efdff  mov     [rbp+80h+var_50], rsi
0x1800efe03  mov     rcx, [rcx+10h]
0x1800efe07  mov     rax, [rcx]
0x1800efe0a  lea     r8, [rbp+80h+var_50]
0x1800efe0e  mov     rax, [rax+38h]
0x1800efe12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efe17  mov     ebx, eax
0x1800efe19  test    eax, eax
0x1800efe1b  jns     loc_1800EFECC
0x1800efe21  mov     [rbp+80h+var_5C], eax
0x1800efe24  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800efe2b  test    rcx, rcx
0x1800efe2e  jz      short loc_1800EFE70
0x1800efe30  lea     r9, aFailedEnumerat_0; "Failed enumerating packages"
0x1800efe37  lea     edi, [rsi+3]
0x1800efe3a  mov     r8d, edi
0x1800efe3d  xor     edx, edx
0x1800efe3f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800efe44  lea     rax, [rbp+80h+var_5C]
0x1800efe48  mov     [rsp+180h+var_128], rax
0x1800efe4d  lea     rax, [rsp+180h+var_128]
0x1800efe52  mov     qword ptr [rsp+180h+bIgnoreCase], rax; int
0x1800efe57  lea     r9, asc_1802C6678; ": {}"
0x1800efe5e  mov     r8d, edi
0x1800efe61  lea     edx, [rsi+1]
0x1800efe64  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800efe6b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800efe70  mov     rcx, [rbp+88h]; this
0x1800efe77  mov     r9d, ebx; char *
0x1800efe7a  lea     r8, aOnecoreBaseSer_13; "onecore\\base\\servicing\\arbiter\\carb"...
0x1800efe81  mov     edx, 326h; void *
0x1800efe86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800efe8b  nop
0x1800efe8c  mov     rcx, [rbp+80h+var_50]
0x1800efe90  test    rcx, rcx
0x1800efe93  jz      short loc_1800EFEA2
0x1800efe95  mov     rax, [rcx]
0x1800efe98  mov     rax, [rax+10h]
0x1800efe9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efea1  nop
0x1800efea2  mov     eax, ebx
0x1800efea4  mov     rcx, [rbp+80h+var_38]
0x1800efea8  xor     rcx, rsp; StackCookie
0x1800efeab  call    __security_check_cookie
0x1800efeb0  mov     rbx, [rsp+180h+arg_10]
0x1800efeb8  add     rsp, 150h
0x1800efebf  pop     r15
0x1800efec1  pop     r14
0x1800efec3  pop     r13
0x1800efec5  pop     r12
0x1800efec7  pop     rdi
0x1800efec8  pop     rsi
0x1800efec9  pop     rbp
0x1800efeca  retn
0x1800efecc  mov     [rbp+80h+var_88], rsi
0x1800efed0  mov     rbx, rsi
0x1800efed3  mov     [rbp+80h+var_D0], rbx
0x1800efed7  mov     [rsp+180h+var_128], rsi
0x1800efedc  mov     r13b, sil
0x1800efedf  mov     [rbp+80h+var_40], esi
0x1800efee2  mov     r14d, 1
0x1800efee8  cmp     [rbp+80h+var_88], rsi
0x1800efeec  jnz     loc_1800F0EBC
0x1800efef2  mov     rcx, [rbp+80h+var_50]
0x1800efef6  mov     rax, [rcx]
0x1800efef9  lea     r9, [rbp+80h+var_40]
0x1800efefd  lea     r8, [rbp+80h+var_88]
0x1800eff01  mov     edx, r14d
0x1800eff04  mov     rax, [rax+18h]
0x1800eff08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eff0d  test    eax, eax
0x1800eff0f  jnz     loc_1800F0A79
0x1800eff15  cmp     [rbp+80h+var_40], esi
0x1800eff18  jbe     loc_1800F0A79
0x1800eff1e  mov     [rbp+80h+var_70], rsi
0x1800eff22  mov     [rbp+80h+pv], rsi
0x1800eff26  mov     [rbp+80h+var_78], rsi
0x1800eff2a  mov     [rbp+80h+var_5C], esi
0x1800eff2d  mov     [rbp+80h+var_3C], esi
0x1800eff30  mov     rcx, [rbp+80h+var_88]
0x1800eff34  mov     rax, [rcx]
0x1800eff37  lea     rdx, [rbp+80h+pv]
0x1800eff3b  mov     rax, [rax+40h]
0x1800eff3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eff44  mov     esi, eax
0x1800eff46  xor     r15d, r15d
0x1800eff49  test    eax, eax
0x1800eff4b  js      loc_1800F0979
0x1800eff51  xor     esi, esi
0x1800eff53  cmp     [rbp+80h+var_78], rsi
0x1800eff57  jnz     loc_1800F0EB1
0x1800eff5d  lea     r8, [rbp+80h+var_78]; struct ICbsPackage **
0x1800eff61  mov     rdx, [rbp+80h+var_88]; struct ICbsIdentity *
0x1800eff65  mov     rcx, r12; this
0x1800eff68  call    ?OpenPackage@CArbiterCbsClient@@QEAAJPEAUICbsIdentity@@PEAPEAUICbsPackage@@@Z; CArbiterCbsClient::OpenPackage(ICbsIdentity *,ICbsPackage * *)
0x1800eff6d  mov     edi, eax
0x1800eff6f  test    eax, eax
0x1800eff71  jns     loc_1800F00AC
0x1800eff77  mov     dword ptr [rbp+80h+var_68], eax
0x1800eff7a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800eff81  test    rcx, rcx
0x1800eff84  jz      short loc_1800EFFD3
0x1800eff86  lea     rax, [rbp+80h+pv]
0x1800eff8a  mov     qword ptr [rsp+180h+bIgnoreCase], rax
0x1800eff8f  lea     r9, aFailedToOpenPa; "Failed to open package: {0}"
0x1800eff96  mov     r8d, r14d
0x1800eff99  xor     edx, edx
0x1800eff9b  call    ??$LogNumObjects@V?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(bool,LogAdapter::LogLevel,char const * const,Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)> const &)
0x1800effa0  lea     rax, [rbp+80h+var_68]
0x1800effa4  mov     [rsp+180h+var_108], rax
0x1800effa9  lea     rax, [rsp+180h+var_108]
0x1800effae  mov     qword ptr [rsp+180h+bIgnoreCase], rax
0x1800effb3  lea     r9, a0; ": {0}"
0x1800effba  mov     r8d, r14d
0x1800effbd  mov     dl, r14b
0x1800effc0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800effc7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800effcc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800effd3  cmp     edi, 800F0805h
0x1800effd9  jnz     short loc_1800F0045
0x1800effdb  mov     rcx, [rbp+80h+var_88]
0x1800effdf  test    rcx, rcx
0x1800effe2  jz      short loc_1800EFFF4
0x1800effe4  mov     rax, [rcx]
0x1800effe7  mov     rax, [rax+10h]
0x1800effeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efff0  mov     [rbp+80h+var_88], rsi
0x1800efff4  mov     rcx, [rbp+80h+var_78]
0x1800efff8  test    rcx, rcx
0x1800efffb  jz      short loc_1800F000D
0x1800efffd  mov     rax, [rcx]
0x1800f0000  mov     rax, [rax+10h]
0x1800f0004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0009  mov     [rbp+80h+var_78], rsi
0x1800f000d  mov     rcx, [rbp+80h+pv]; pv
0x1800f0011  test    rcx, rcx
0x1800f0014  jz      short loc_1800F0026
0x1800f0016  call    cs:__imp_CoTaskMemFree
0x1800f001d  nop     dword ptr [rax+rax+00h]
0x1800f0022  mov     [rbp+80h+pv], rsi
0x1800f0026  mov     rcx, [rbp+80h+var_70]
0x1800f002a  test    rcx, rcx
0x1800f002d  jz      loc_1800EFEE8
0x1800f0033  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x1800f0037  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f003c  mov     [rbp+80h+var_70], rsi
0x1800f0040  jmp     loc_1800EFEE8
0x1800f0045  cmp     [r12+29h], sil
0x1800f004a  jz      short loc_1800F0075
0x1800f004c  test    rcx, rcx
0x1800f004f  jz      loc_1800F011B
0x1800f0055  lea     rax, [rbp+80h+pv]
0x1800f0059  mov     qword ptr [rsp+180h+bIgnoreCase], rax
0x1800f005e  lea     r9, aFailedToOpenPa_0; "Failed to open package: {0} but proceed"...
0x1800f0065  mov     r8d, r14d
0x1800f0068  mov     dl, r14b
0x1800f006b  call    ??$LogNumObjects@V?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(bool,LogAdapter::LogLevel,char const * const,Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)> const &)
0x1800f0070  jmp     loc_1800F011B
0x1800f0075  mov     rcx, [rbp+80h+var_88]
0x1800f0079  test    rcx, rcx
0x1800f007c  jz      short loc_1800F008E
0x1800f007e  mov     rax, [rcx]
0x1800f0081  mov     rax, [rax+10h]
0x1800f0085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f008a  mov     [rbp+80h+var_88], rsi
0x1800f008e  mov     rcx, [rbp+80h+var_78]
0x1800f0092  test    rcx, rcx
0x1800f0095  jz      short loc_1800F00A7
0x1800f0097  mov     rax, [rcx]
0x1800f009a  mov     rax, [rax+10h]
0x1800f009e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f00a3  mov     [rbp+80h+var_78], rsi
0x1800f00a7  jmp     loc_1800F000D
0x1800f00ac  mov     rcx, [rbp+80h+var_78]
0x1800f00b0  mov     rax, [rcx]
0x1800f00b3  lea     r8, [rbp+80h+var_3C]
0x1800f00b7  lea     rdx, [rbp+80h+var_5C]
0x1800f00bb  mov     rax, [rax+60h]
0x1800f00bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f00c4  mov     esi, eax
0x1800f00c6  test    eax, eax
0x1800f00c8  js      loc_1800F087B
0x1800f00ce  mov     eax, [rbp+80h+var_5C]
0x1800f00d1  cmp     eax, 4
0x1800f00d4  jz      short loc_1800F0119
0x1800f00d6  cmp     eax, 0FFFFFFEFh
0x1800f00d9  jz      short loc_1800F0119
0x1800f00db  xor     esi, esi
0x1800f00dd  cmp     eax, 6
0x1800f00e0  jge     short loc_1800F011B
0x1800f00e2  mov     rcx, [rbp+80h+var_88]
0x1800f00e6  test    rcx, rcx
0x1800f00e9  jz      short loc_1800F00FB
0x1800f00eb  mov     rax, [rcx]
0x1800f00ee  mov     rax, [rax+10h]
0x1800f00f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f00f7  mov     [rbp+80h+var_88], rsi
0x1800f00fb  mov     rcx, [rbp+80h+var_78]
0x1800f00ff  test    rcx, rcx
0x1800f0102  jz      short loc_1800F0114
0x1800f0104  mov     rax, [rcx]
0x1800f0107  mov     rax, [rax+10h]
0x1800f010b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0110  mov     [rbp+80h+var_78], rsi
0x1800f0114  jmp     loc_1800F000D
0x1800f0119  xor     esi, esi
0x1800f011b  mov     rdx, [rbp+80h+pv]
0x1800f011f  lea     rcx, [rbp+80h+var_70]
0x1800f0123  call    SczAllocFromSz
0x1800f0128  mov     edi, eax
0x1800f012a  test    eax, eax
0x1800f012c  js      loc_1800F07CC
0x1800f0132  mov     [rbp+80h+lpString1], rsi
0x1800f0136  mov     [rsp+180h+var_118], rsi
0x1800f013b  mov     [rsp+180h+var_110], rsi
0x1800f0140  mov     [rbp+80h+var_E0], rsi
0x1800f0144  mov     [rbp+80h+var_68], rsi
0x1800f0148  mov     edx, 7Eh ; '~'; wchar_t
0x1800f014d  lea     rax, [rbp+80h+var_68]
0x1800f0151  mov     [rsp+180h+var_150], rax; wchar_t **
0x1800f0156  lea     rax, [rsp+180h+var_110]
0x1800f015b  mov     [rsp+180h+var_158], rax; wchar_t **
0x1800f0160  lea     rax, [rbp+80h+var_E0]
0x1800f0164  mov     qword ptr [rsp+180h+bIgnoreCase], rax; wchar_t **
0x1800f0169  lea     r9, [rsp+180h+var_118]; wchar_t **
0x1800f016e  lea     r8, [rbp+80h+lpString1]; wchar_t **
0x1800f0172  mov     rcx, [rbp+80h+var_70]; wchar_t *
0x1800f0176  call    ?ShredStringIdIntoAttributes@@YAJPEA_W_WPEAPEB_W2222@Z; ShredStringIdIntoAttributes(wchar_t *,wchar_t,wchar_t const * *,wchar_t const * *,wchar_t const * *,wchar_t const * *,wchar_t const * *)
0x1800f017b  mov     esi, eax
0x1800f017d  xor     r15d, r15d
0x1800f0180  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f0187  test    eax, eax
0x1800f0189  js      loc_1800F06CC
0x1800f018f  test    rcx, rcx
0x1800f0192  jz      short loc_1800F01AF
0x1800f0194  lea     rax, [rbp+80h+pv]
0x1800f0198  mov     qword ptr [rsp+180h+bIgnoreCase], rax
0x1800f019d  lea     r9, aCbsPackageKeyf; "CBS: Package Keyform: {0}"
0x1800f01a4  mov     r8d, r14d
0x1800f01a7  mov     dl, r14b
0x1800f01aa  call    ??$LogNumObjects@V?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(bool,LogAdapter::LogLevel,char const * const,Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)> const &)
0x1800f01af  mov     [rbp+80h+var_90], r15
0x1800f01b3  lea     rax, [rbp+80h+var_90]
0x1800f01b7  mov     [rsp+180h+var_140], rax
0x1800f01bc  mov     [rsp+180h+var_148], r15d
0x1800f01c1  mov     r12, [rbp+80h+var_68]
0x1800f01c5  mov     [rsp+180h+var_150], r12
0x1800f01ca  mov     rax, [rbp+80h+var_E0]
0x1800f01ce  mov     [rsp+180h+var_158], rax
0x1800f01d3  mov     byte ptr [rsp+180h+bIgnoreCase], r15b; int
0x1800f01d8  xor     r9d, r9d
0x1800f01db  mov     r8, [rbp+80h+pv]
0x1800f01df  mov     r15, [rbp+80h+lpString1]
0x1800f01e3  mov     rdx, r15
0x1800f01e6  mov     rdi, [rsp+180h+var_120]
0x1800f01eb  mov     rcx, rdi
0x1800f01ee  call    ?AddOnDevicePackage@CDeviceInfo@@QEAAJQEB_W00_N00W4PackageFunction@ActionList@@PEAPEAUPackage@1@@Z; CDeviceInfo::AddOnDevicePackage(wchar_t const * const,wchar_t const * const,wchar_t const * const,bool,wchar_t const * const,wchar_t const * const,ActionList::PackageFunction,CDeviceInfo::Package * *)
0x1800f01f3  mov     esi, eax
0x1800f01f5  test    eax, eax
0x1800f01f7  js      loc_1800F05CC
0x1800f01fd  mov     rax, [rbp+80h+var_90]
0x1800f0201  xor     esi, esi
0x1800f0203  test    rax, rax
0x1800f0206  jz      loc_1800F03F9
0x1800f020c  mov     [rbp+80h+String1], rsi
0x1800f0210  cmp     [rbp+80h+var_5C], 4
0x1800f0214  jnz     short loc_1800F021F
0x1800f0216  mov     dword ptr [rax+3Ch], 10h
0x1800f021d  jmp     short loc_1800F022C
0x1800f021f  cmp     [rbp+80h+var_5C], 0FFFFFFEFh
0x1800f0223  jnz     short loc_1800F022C
0x1800f0225  mov     dword ptr [rax+3Ch], 20h ; ' '
0x1800f022c  mov     rcx, [rbp+80h+var_78]
0x1800f0230  test    rcx, rcx
0x1800f0233  jz      short loc_1800F0274
0x1800f0235  cmp     [rbp+80h+String1], rsi
0x1800f0239  jnz     loc_1800F0EC7
  ... truncated ...
```
