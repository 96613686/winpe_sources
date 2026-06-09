# CArbiterCbsClient::PopulateDeviceInfoFromSelectableUpdates(CDeviceInfo *)

- ea: `0x18007adb8`
- end: `0x18007b923`
- name: `?PopulateDeviceInfoFromSelectableUpdates@CArbiterCbsClient@@QEAAJPEAVCDeviceInfo@@@Z`
- size: `2923`
- prototype: `__int64 __fastcall(CArbiterCbsClient *__hidden this, struct CDeviceInfo *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180091aac`

## callees

- `0x1800031d0`
- `0x1800062b8`
- `0x18000aedc`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18003cd78`
- `0x18004c014`
- `0x180051984`
- `0x1800727f0`
- `0x180077654`
- `0x18007adb8`
- `0x180085620`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b20d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b3c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b46c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b558`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b62e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b6fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b7c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b20d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b3c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b46c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b558`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b62e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b6fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b7c8`

## string_xrefs

- `0x18007b885`: `Cannot get selectable updates without an ICbsSession`
- `0x18007b69a`: `Failed getting installed state`
- `0x18007b767`: `Failed getting update CbsUpdatePropertyName property`
- `0x18007aed0`: `Failed getting update enumerator`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CArbiterCbsClient::PopulateDeviceInfoFromSelectableUpdates(
        CArbiterCbsClient *this,
        struct CDeviceInfo *a2)
{
  int v3; // eax
  unsigned int v4; // edi
  __int64 v5; // rdx
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rax
  LPVOID v9; // r10
  __int64 v10; // rcx
  __int64 v11; // rcx
  unsigned __int16 *v12; // r11
  __int64 v13; // rbx
  __int64 v14; // rsi
  __int64 v15; // r8
  const wchar_t *i; // rdi
  __int64 v17; // rdx
  unsigned __int16 v18; // r9
  int v19; // eax
  int v20; // ecx
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int16 *v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // r9
  const wchar_t *v28; // r10
  __int16 v29; // cx
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v36; // rdx
  int *v37; // [rsp+28h] [rbp-69h]
  int *v38; // [rsp+30h] [rbp-61h]
  int v39[2]; // [rsp+38h] [rbp-59h] BYREF
  _QWORD v40[3]; // [rsp+40h] [rbp-51h] BYREF
  _QWORD v41[4]; // [rsp+58h] [rbp-39h] BYREF
  int v42; // [rsp+78h] [rbp-19h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-11h] BYREF
  __int64 v44; // [rsp+88h] [rbp-9h] BYREF
  __int64 v45; // [rsp+90h] [rbp-1h] BYREF
  struct ICbsPackage *v46; // [rsp+98h] [rbp+7h] BYREF
  __int64 v47; // [rsp+A0h] [rbp+Fh] BYREF
  int v48; // [rsp+A8h] [rbp+17h] BYREF
  int v49; // [rsp+ACh] [rbp+1Bh] BYREF
  int v50; // [rsp+B0h] [rbp+1Fh] BYREF
  int v51; // [rsp+B4h] [rbp+23h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]

  v41[3] = -2;
  if ( !*((_QWORD *)this + 2) )
  {
    v4 = -2147024846;
    v49 = -2147024846;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Cannot get selectable updates without an ICbsSession");
      *(_QWORD *)v39 = &v49;
      v37 = v39;
      LOBYTE(v36) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v36,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x299,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      (const char *)0x80070032LL,
      (int)v37);
    return v4;
  }
  v46 = 0;
  v3 = CArbiterCbsClient::OpenPackage(this, L"@Foundation", &v46);
  v4 = v3;
  if ( v3 < 0 )
  {
    v42 = v3;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed getting foundation package");
      *(_QWORD *)v39 = &v42;
      v37 = v39;
      LOBYTE(v5) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v5,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29C,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      (const char *)v4,
      (int)v37);
    if ( v46 )
      (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v46 + 16LL))(v46);
    return v4;
  }
  v45 = 0;
  v6 = (*(__int64 (__fastcall **)(struct ICbsPackage *, __int64, __int64, __int64 *))(*(_QWORD *)v46 + 40LL))(
         v46,
         4,
         18,
         &v45);
  v4 = v6;
  if ( v6 < 0 )
  {
    v42 = v6;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed getting update enumerator");
      *(_QWORD *)v39 = &v42;
      v37 = v39;
      LOBYTE(v7) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v7,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A4,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
      (const char *)v4,
      (int)v37);
    if ( v45 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      v45 = 0;
    }
    if ( v46 )
      (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v46 + 16LL))(v46);
    return v4;
  }
  v8 = 0;
  v44 = 0;
  v50 = 0;
  while ( 1 )
  {
    if ( v8 )
    {
      INTERNAL_ERROR_ACTION(-1073741595);
      INTERNAL_ERROR_ACTION(-1073741595);
LABEL_157:
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x18007B922LL);
    }
    if ( (*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v45 + 24LL))(
           v45,
           1,
           &v44,
           &v50)
      || !v50 )
    {
      break;
    }
    pv = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v44 + 24LL))(v44, 1, &pv);
    if ( (v4 & 0x80000000) != 0 )
    {
      v42 = v4;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed getting update CbsUpdatePropertyName property");
        *(_QWORD *)v39 = &v42;
        v37 = v39;
        LOBYTE(v34) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v34,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2AD,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
        (const char *)v4,
        (int)v37);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v44 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
        v44 = 0;
      }
      if ( v45 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
        v45 = 0;
      }
      if ( v46 )
        (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v46 + 16LL))(v46);
      return v4;
    }
    v48 = 0;
    v49 = 0;
    v51 = 5;
    v4 = (*(__int64 (__fastcall **)(__int64, int *, int *, int *))(*(_QWORD *)v44 + 64LL))(v44, &v48, &v49, &v51);
    if ( (v4 & 0x80000000) != 0 )
    {
      v42 = v4;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed getting installed state");
        *(_QWORD *)v39 = &v42;
        v37 = v39;
        LOBYTE(v33) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v33,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B8,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
        (const char *)v4,
        (int)v37);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v44 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
        v44 = 0;
      }
      if ( v45 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
        v45 = 0;
      }
      if ( v46 )
        (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v46 + 16LL))(v46);
      return v4;
    }
    if ( v48 >= 6 )
    {
      v47 = 0;
      *(_QWORD *)v39 = 0;
      v9 = pv;
      if ( pv )
      {
        v10 = -1;
        do
          ++v10;
        while ( *((_WORD *)pv + v10) );
        v11 = 2 * v10;
        v12 = (unsigned __int16 *)pv;
        v13 = v11 + 2;
      }
      else
      {
        v12 = 0;
        v11 = 0;
        v13 = 0;
      }
      v14 = 16;
      v15 = 14;
      for ( i = L"Preview"; ; ++i )
      {
        v17 = v15;
        if ( !v11 || !v15 )
        {
          if ( v11 )
            v19 = 1;
          else
            v19 = -(v15 != 0);
          goto LABEL_45;
        }
        if ( *v12 > 0x7Fu )
          break;
        v17 = *i;
        v18 = *v12 + 32;
        if ( (unsigned __int16)(*v12 - 65) > 0x19u )
          v18 = *v12;
        if ( (unsigned __int16)(v17 - 65) <= 0x19u )
          LOWORD(v17) = v17 + 32;
        if ( v18 != (_WORD)v17 )
        {
          v19 = v18 < (unsigned __int16)v17 ? -1 : 1;
LABEL_45:
          v20 = 0;
          goto LABEL_46;
        }
        ++v12;
        v11 -= 2;
        v13 -= 2;
        v15 -= 2;
        v14 -= 2;
      }
      v42 = 0;
      v41[0] = v11;
      v41[1] = v13;
      v41[2] = v12;
      v40[0] = v15;
      v40[1] = v14;
      v40[2] = i;
      v20 = RtlCompareEncodedLBlobs(
              (unsigned int)v41,
              (unsigned int)RtlDecodeUtf16LE,
              (unsigned int)v40,
              (unsigned int)RtlDecodeUtf16LE,
              (__int64)RtlDowncaseUCSCharacter,
              (__int64)&v42);
      if ( v20 >= 0 )
        v20 = 0;
      v9 = pv;
      v19 = v42;
LABEL_46:
      if ( v19 || v20 < 0 )
      {
        v4 = SczAllocConcat2Sz(&v47, L"OC-", v9);
        if ( (v4 & 0x80000000) != 0 )
        {
          v42 = v4;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "Failed creating feature name for OC: {0}",
              &pv,
              v38,
              *(_QWORD *)v39);
            *(_QWORD *)v39 = &v42;
            v37 = v39;
            LOBYTE(v31) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v31,
              3,
              ": {}");
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2CD,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
            (const char *)v4,
            (int)v37);
          if ( v47 )
          {
            operator delete((void *)(v47 - 8));
            v47 = 0;
          }
          if ( pv )
          {
            CoTaskMemFree(pv);
            pv = 0;
          }
          if ( v44 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
            v44 = 0;
          }
          if ( v45 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
            v45 = 0;
          }
          if ( v46 )
            (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v46 + 16LL))(v46);
          return v4;
        }
        v38 = v39;
        v37 = (int *)L"Microsoft";
        LOBYTE(v23) = 2;
        v4 = CDeviceInfo::AddInstalledFeature(a2, v23, v47, 0);
        if ( (v4 & 0x80000000) != 0 )
        {
          v42 = v4;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<AutoScz>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "Failed adding feature: {0}",
              &v47);
            *(_QWORD *)v39 = &v42;
            v37 = v39;
            LOBYTE(v30) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v30,
              3,
              ": {}");
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2D6,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
            (const char *)v4,
            (int)v37);
          if ( v47 )
          {
            operator delete((void *)(v47 - 8));
            v47 = 0;
          }
          if ( pv )
          {
            CoTaskMemFree(pv);
            pv = 0;
          }
          if ( v44 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
            v44 = 0;
          }
          if ( v45 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
            v45 = 0;
          }
          if ( v46 )
            (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v46 + 16LL))(v46);
          return v4;
        }
      }
      else
      {
        v38 = v39;
        v37 = (int *)L"Contained";
        LOBYTE(v17) = 26;
        v21 = CDeviceInfo::AddInstalledFeature(a2, v17, v9, 0);
        v4 = v21;
        if ( v21 < 0 )
        {
          v42 = v21;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "Failed adding feature: {0}",
              &pv,
              v39,
              *(_QWORD *)v39);
            *(_QWORD *)v39 = &v42;
            v37 = v39;
            LOBYTE(v22) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v22,
              3,
              ": {}");
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2C8,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
            (const char *)v4,
            (int)v37);
          if ( v47 )
          {
            operator delete((void *)(v47 - 8));
            v47 = 0;
          }
          if ( pv )
          {
            CoTaskMemFree(pv);
            pv = 0;
          }
          if ( v44 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
            v44 = 0;
          }
          if ( v45 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
            v45 = 0;
          }
          if ( v46 )
            (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v46 + 16LL))(v46);
          return v4;
        }
      }
      if ( v47 )
        operator delete((void *)(v47 - 8));
    }
    if ( (v48 & 0xFFFFFFFD) == 0 )
    {
      v24 = (__int16 *)pv;
      if ( pv )
      {
        v25 = -1;
        do
          ++v25;
        while ( *((_WORD *)pv + v25) );
        v26 = 2 * v25;
      }
      else
      {
        v24 = 0;
        v26 = 0;
      }
      if ( (v26 & 0xFFFFFFFFFFFFFFFEuLL) == 0xC )
      {
        v27 = 12;
        v28 = L"recall";
        while ( v26 )
        {
          v29 = *v24 + 32;
          if ( (unsigned __int16)(*v24 - 65) > 0x19u )
            v29 = *v24;
          if ( v29 != *v28 )
            goto LABEL_82;
          if ( !v27 )
            goto LABEL_157;
          ++v24;
          v26 -= 2;
          ++v28;
          v27 -= 2;
        }
        *(_QWORD *)v39 = 0;
        v38 = v39;
        LODWORD(v37) = 0;
        v4 = CDeviceInfo::AddInstalledFeature(a2, 2, L"OC-Recall", 0);
        if ( (v4 & 0x80000000) != 0 )
        {
          v42 = v4;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "Failed adding feature: {0}",
              &pv,
              v39,
              *(_QWORD *)v39);
            *(_QWORD *)v39 = &v42;
            v37 = v39;
            LOBYTE(v32) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v32,
              3,
              ": {}");
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2E2,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\carbitercbsclient.cpp",
            (const char *)v4,
            (int)v37);
          if ( pv )
          {
            CoTaskMemFree(pv);
            pv = 0;
          }
          if ( v44 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
            v44 = 0;
          }
          if ( v45 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
            v45 = 0;
          }
          if ( v46 )
            (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v46 + 16LL))(v46);
          return v4;
        }
        *(_DWORD *)(*(_QWORD *)v39 + 92LL) |= 1u;
      }
    }
LABEL_82:
    v8 = v44;
    if ( v44 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      v8 = 0;
      v44 = 0;
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      v8 = v44;
    }
  }
  if ( v44 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    v44 = 0;
  }
  if ( v45 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    v45 = 0;
  }
  if ( v46 )
    (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v46 + 16LL))(v46);
  return 0;
}

```

## disassembly

```asm
0x18007adb8  mov     rax, rsp
0x18007adbb  push    rbp
0x18007adbc  push    rsi
0x18007adbd  push    rdi
0x18007adbe  push    r14
0x18007adc0  push    r15
0x18007adc2  lea     rbp, [rax-5Fh]
0x18007adc6  sub     rsp, 0C0h
0x18007adcd  mov     [rbp+57h+var_78], 0FFFFFFFFFFFFFFFEh
0x18007add5  mov     [rax+18h], rbx
0x18007add9  mov     rax, cs:__security_cookie
0x18007ade0  xor     rax, rsp
0x18007ade3  mov     [rbp+57h+var_30], rax
0x18007ade7  mov     r14, rdx
0x18007adea  xor     r15d, r15d
0x18007aded  cmp     [rcx+10h], r15
0x18007adf1  jz      loc_18007B871
0x18007adf7  mov     [rbp+57h+var_50], r15
0x18007adfb  lea     r8, [rbp+57h+var_50]; struct ICbsPackage **
0x18007adff  lea     rdx, aFoundation; "@Foundation"
0x18007ae06  call    ?OpenPackage@CArbiterCbsClient@@QEAAJQEB_WPEAPEAUICbsPackage@@@Z; CArbiterCbsClient::OpenPackage(wchar_t const * const,ICbsPackage * *)
0x18007ae0b  mov     edi, eax
0x18007ae0d  test    eax, eax
0x18007ae0f  jns     loc_18007AE96
0x18007ae15  mov     [rbp+57h+var_70], eax
0x18007ae18  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007ae1f  test    rcx, rcx
0x18007ae22  jz      short loc_18007AE62
0x18007ae24  lea     r9, aFailedGettingF; "Failed getting foundation package"
0x18007ae2b  lea     ebx, [r15+3]
0x18007ae2f  mov     r8d, ebx
0x18007ae32  xor     edx, edx
0x18007ae34  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18007ae39  lea     rax, [rbp+57h+var_70]
0x18007ae3d  mov     qword ptr [rbp+57h+var_B0], rax
0x18007ae41  lea     rax, [rbp+57h+var_B0]
0x18007ae45  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18007ae4a  lea     r9, asc_1801CAFB4; ": {}"
0x18007ae51  mov     r8d, ebx
0x18007ae54  mov     dl, 1
0x18007ae56  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007ae5d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18007ae62  mov     rcx, [rbp+5Fh]; this
0x18007ae66  mov     r9d, edi; char *
0x18007ae69  lea     r8, aOnecoreBaseSer_13; "onecore\\base\\servicing\\arbiter\\carb"...
0x18007ae70  mov     edx, 29Ch; void *
0x18007ae75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ae7a  nop
0x18007ae7b  mov     rcx, [rbp+57h+var_50]
0x18007ae7f  test    rcx, rcx
0x18007ae82  jz      short loc_18007AE91
0x18007ae84  mov     rax, [rcx]
0x18007ae87  mov     rax, [rax+10h]
0x18007ae8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ae90  nop
0x18007ae91  jmp     loc_18007B8DC
0x18007ae96  mov     [rbp+57h+var_58], r15
0x18007ae9a  mov     rcx, [rbp+57h+var_50]
0x18007ae9e  mov     rax, [rcx]
0x18007aea1  lea     r9, [rbp+57h+var_58]
0x18007aea5  mov     edx, 4
0x18007aeaa  lea     r8d, [rdx+0Eh]
0x18007aeae  mov     rax, [rax+28h]
0x18007aeb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aeb7  mov     edi, eax
0x18007aeb9  test    eax, eax
0x18007aebb  jns     loc_18007AF5C
0x18007aec1  mov     [rbp+57h+var_70], eax
0x18007aec4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007aecb  test    rcx, rcx
0x18007aece  jz      short loc_18007AF0F
0x18007aed0  lea     r9, aFailedGettingU_1; "Failed getting update enumerator"
0x18007aed7  mov     ebx, 3
0x18007aedc  mov     r8d, ebx
0x18007aedf  xor     edx, edx
0x18007aee1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18007aee6  lea     rax, [rbp+57h+var_70]
0x18007aeea  mov     qword ptr [rbp+57h+var_B0], rax
0x18007aeee  lea     rax, [rbp+57h+var_B0]
0x18007aef2  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18007aef7  lea     r9, asc_1801CAFB4; ": {}"
0x18007aefe  mov     r8d, ebx
0x18007af01  mov     dl, 1
0x18007af03  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007af0a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18007af0f  mov     rcx, [rbp+5Fh]; this
0x18007af13  mov     r9d, edi; char *
0x18007af16  lea     r8, aOnecoreBaseSer_13; "onecore\\base\\servicing\\arbiter\\carb"...
0x18007af1d  mov     edx, 2A4h; void *
0x18007af22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007af27  nop
0x18007af28  mov     rcx, [rbp+57h+var_58]
0x18007af2c  test    rcx, rcx
0x18007af2f  jz      short loc_18007AF41
0x18007af31  mov     rax, [rcx]
0x18007af34  mov     rax, [rax+10h]
0x18007af38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007af3d  mov     [rbp+57h+var_58], r15
0x18007af41  mov     rcx, [rbp+57h+var_50]
0x18007af45  test    rcx, rcx
0x18007af48  jz      short loc_18007AF57
0x18007af4a  mov     rax, [rcx]
0x18007af4d  mov     rax, [rax+10h]
0x18007af51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007af56  nop
0x18007af57  jmp     loc_18007B8DC
0x18007af5c  mov     rax, r15
0x18007af5f  mov     [rbp+57h+var_60], rax
0x18007af63  mov     [rbp+57h+var_38], r15d
0x18007af67  test    rax, rax
0x18007af6a  jnz     loc_18007B902
0x18007af70  mov     rcx, [rbp+57h+var_58]
0x18007af74  mov     rax, [rcx]
0x18007af77  lea     r9, [rbp+57h+var_38]
0x18007af7b  lea     r8, [rbp+57h+var_60]
0x18007af7f  mov     edx, 1
0x18007af84  mov     rax, [rax+18h]
0x18007af88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007af8d  test    eax, eax
0x18007af8f  jnz     loc_18007B825
0x18007af95  cmp     [rbp+57h+var_38], r15d
0x18007af99  jbe     loc_18007B825
0x18007af9f  mov     [rbp+57h+pv], r15
0x18007afa3  mov     rcx, [rbp+57h+var_60]
0x18007afa7  mov     rax, [rcx]
0x18007afaa  lea     r8, [rbp+57h+pv]
0x18007afae  mov     edx, 1
0x18007afb3  mov     rax, [rax+18h]
0x18007afb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007afbc  mov     edi, eax
0x18007afbe  test    eax, eax
0x18007afc0  js      loc_18007B758
0x18007afc6  mov     [rbp+57h+var_40], r15d
0x18007afca  mov     [rbp+57h+var_3C], r15d
0x18007afce  mov     [rbp+57h+var_34], 5
0x18007afd5  mov     rcx, [rbp+57h+var_60]
0x18007afd9  mov     rax, [rcx]
0x18007afdc  lea     r9, [rbp+57h+var_34]
0x18007afe0  lea     r8, [rbp+57h+var_3C]
0x18007afe4  lea     rdx, [rbp+57h+var_40]
0x18007afe8  mov     rax, [rax+40h]
0x18007afec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aff1  mov     edi, eax
0x18007aff3  test    eax, eax
0x18007aff5  js      loc_18007B68B
0x18007affb  cmp     [rbp+57h+var_40], 6
0x18007afff  jl      loc_18007B2C9
0x18007b005  mov     [rbp+57h+var_48], r15
0x18007b009  mov     qword ptr [rbp+57h+var_B0], r15
0x18007b00d  mov     r10, [rbp+57h+pv]
0x18007b011  test    r10, r10
0x18007b014  jz      short loc_18007B030
0x18007b016  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18007b01a  inc     rcx
0x18007b01d  cmp     [r10+rcx*2], r15w
0x18007b022  jnz     short loc_18007B01A
0x18007b024  add     rcx, rcx
0x18007b027  mov     r11, r10
0x18007b02a  lea     rbx, [rcx+2]
0x18007b02e  jmp     short loc_18007B039
0x18007b030  mov     r11, r15
0x18007b033  mov     rcx, r15
0x18007b036  mov     rbx, r15
0x18007b039  mov     esi, 10h
0x18007b03e  lea     r8d, [rsi-2]
0x18007b042  lea     rdi, aPreview; "Preview"
0x18007b049  mov     rdx, r8
0x18007b04c  mov     rax, rcx
0x18007b04f  test    rax, rax
0x18007b052  jz      loc_18007B12B
0x18007b058  test    rdx, rdx
0x18007b05b  jz      loc_18007B12B
0x18007b061  cmp     word ptr [r11], 7Fh
0x18007b066  ja      short loc_18007B0CD
0x18007b068  movzx   edx, word ptr [rdi]
0x18007b06b  movzx   eax, word ptr [r11]
0x18007b06f  sub     ax, 41h ; 'A'
0x18007b073  movzx   r9d, word ptr [r11]
0x18007b077  add     r9w, 20h ; ' '
0x18007b07c  cmp     ax, 19h
0x18007b080  cmova   r9w, [r11]
0x18007b085  lea     eax, [rdx-41h]
0x18007b088  cmp     ax, 19h
0x18007b08c  ja      short loc_18007B092
0x18007b08e  add     dx, 20h ; ' '
0x18007b092  cmp     r9w, dx
0x18007b096  jnz     short loc_18007B0C4
0x18007b098  test    rcx, rcx
0x18007b09b  jz      loc_18007B90D
0x18007b0a1  test    r8, r8
0x18007b0a4  jz      loc_18007B90D
0x18007b0aa  add     r11, 2
0x18007b0ae  sub     rcx, 2
0x18007b0b2  sub     rbx, 2
0x18007b0b6  add     rdi, 2
0x18007b0ba  sub     r8, 2
0x18007b0be  sub     rsi, 2
0x18007b0c2  jmp     short loc_18007B049
0x18007b0c4  sbb     eax, eax
0x18007b0c6  and     eax, 0FFFFFFFEh
0x18007b0c9  inc     eax
0x18007b0cb  jmp     short loc_18007B13C
0x18007b0cd  mov     [rbp+57h+var_70], r15d
0x18007b0d1  mov     [rbp+57h+var_90], rcx
0x18007b0d5  mov     [rbp+57h+var_88], rbx
0x18007b0d9  mov     [rbp+57h+var_80], r11
0x18007b0dd  mov     [rbp+57h+var_A8], r8
0x18007b0e1  mov     [rbp+57h+var_A0], rsi
0x18007b0e5  mov     [rbp+57h+var_98], rdi
0x18007b0e9  lea     rax, [rbp+57h+var_70]
0x18007b0ed  mov     [rsp+28h], rax
0x18007b0f2  lea     rax, RtlDowncaseUCSCharacter
0x18007b0f9  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18007b0fe  lea     r9, RtlDecodeUtf16LE
0x18007b105  lea     r8, [rbp+57h+var_A8]
0x18007b109  lea     rdx, RtlDecodeUtf16LE
0x18007b110  lea     rcx, [rbp+57h+var_90]
0x18007b114  call    RtlCompareEncodedLBlobs
0x18007b119  mov     ecx, eax
0x18007b11b  test    eax, eax
0x18007b11d  js      short loc_18007B122
0x18007b11f  mov     ecx, r15d
0x18007b122  mov     r10, [rbp+57h+pv]
0x18007b126  mov     eax, [rbp+57h+var_70]
0x18007b129  jmp     short loc_18007B13F
0x18007b12b  test    rcx, rcx
0x18007b12e  jz      short loc_18007B137
0x18007b130  mov     eax, 1
0x18007b135  jmp     short loc_18007B13C
0x18007b137  neg     r8
0x18007b13a  sbb     eax, eax
0x18007b13c  mov     ecx, r15d
0x18007b13f  test    eax, eax
0x18007b141  jnz     loc_18007B26A
0x18007b147  test    ecx, ecx
0x18007b149  js      loc_18007B26A
0x18007b14f  lea     rax, [rbp+57h+var_B0]
0x18007b153  mov     [rsp+28h], rax
0x18007b158  lea     rax, aContained_0; "Contained"
0x18007b15f  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18007b164  xor     r9d, r9d
0x18007b167  mov     r8, r10
0x18007b16a  mov     dl, 1Ah
0x18007b16c  mov     rcx, r14
0x18007b16f  call    ?AddInstalledFeature@CDeviceInfo@@QEAAJW4FeatureType@CompositionDatabase@@QEB_W11PEAPEAUFeature@1@@Z; CDeviceInfo::AddInstalledFeature(CompositionDatabase::FeatureType,wchar_t const * const,wchar_t const * const,wchar_t const * const,CDeviceInfo::Feature * *)
0x18007b174  mov     edi, eax
0x18007b176  test    eax, eax
0x18007b178  jns     loc_18007B2B7
0x18007b17e  mov     [rbp+57h+var_70], eax
0x18007b181  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007b188  test    rcx, rcx
0x18007b18b  jz      short loc_18007B1D5
0x18007b18d  lea     rax, [rbp+57h+pv]
0x18007b191  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18007b196  lea     r9, aFailedAddingFe_3; "Failed adding feature: {0}"
0x18007b19d  mov     ebx, 3
0x18007b1a2  mov     r8d, ebx
0x18007b1a5  xor     edx, edx
0x18007b1a7  call    ??$LogNumObjects@V?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(bool,LogAdapter::LogLevel,char const * const,Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)> const &)
0x18007b1ac  lea     rax, [rbp+57h+var_70]
0x18007b1b0  mov     qword ptr [rbp+57h+var_B0], rax
0x18007b1b4  lea     rax, [rbp+57h+var_B0]
0x18007b1b8  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18007b1bd  lea     r9, asc_1801CAFB4; ": {}"
0x18007b1c4  mov     r8d, ebx
0x18007b1c7  mov     dl, 1
0x18007b1c9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007b1d0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18007b1d5  mov     rcx, [rbp+5Fh]; this
0x18007b1d9  mov     r9d, edi; char *
0x18007b1dc  lea     r8, aOnecoreBaseSer_13; "onecore\\base\\servicing\\arbiter\\carb"...
0x18007b1e3  mov     edx, 2C8h; void *
0x18007b1e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b1ed  nop
0x18007b1ee  mov     rcx, [rbp+57h+var_48]
0x18007b1f2  test    rcx, rcx
0x18007b1f5  jz      short loc_18007B204
0x18007b1f7  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x18007b1fb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007b200  mov     [rbp+57h+var_48], r15
0x18007b204  mov     rcx, [rbp+57h+pv]; pv
0x18007b208  test    rcx, rcx
0x18007b20b  jz      short loc_18007B21D
0x18007b20d  call    cs:__imp_CoTaskMemFree
0x18007b214  nop     dword ptr [rax+rax+00h]
0x18007b219  mov     [rbp+57h+pv], r15
0x18007b21d  mov     rcx, [rbp+57h+var_60]
0x18007b221  test    rcx, rcx
0x18007b224  jz      short loc_18007B236
0x18007b226  mov     rax, [rcx]
0x18007b229  mov     rax, [rax+10h]
0x18007b22d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b232  mov     [rbp+57h+var_60], r15
0x18007b236  mov     rcx, [rbp+57h+var_58]
0x18007b23a  test    rcx, rcx
0x18007b23d  jz      short loc_18007B24F
0x18007b23f  mov     rax, [rcx]
0x18007b242  mov     rax, [rax+10h]
0x18007b246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b24b  mov     [rbp+57h+var_58], r15
  ... truncated ...
```
