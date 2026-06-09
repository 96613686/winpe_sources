# CStorageFolderProxyBase::_CheckItemInProc(HSTRING__ *,Windows::Storage::CreationCollisionOption,ushort * *)

- ea: `0x18000f7e0`
- end: `0x180010104`
- name: `?_CheckItemInProc@CStorageFolderProxyBase@@IEAAJPEAUHSTRING__@@W4CreationCollisionOption@Storage@Windows@@PEAPEAG@Z`
- size: `2340`
- prototype: `int __high(HSTRING, enum Windows::Storage::CreationCollisionOption, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002cd44`
- `0x18002d150`
- `0x18002dbc8`

## callees

- `0x18000d6cc`
- `0x18000f7e0`
- `0x180010110`
- `0x180010360`
- `0x180011660`
- `0x1800432f0`
- `0x180047aa0`
- `0x18005f240`
- `0x1803a4cb0`
- `0x1803a93cc`
- `0x1803a9434`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f91f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800100ed`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f91f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800100ed`
- `ntdll!EtwEventActivityIdControl` at `0x18000f835`
- `ntdll!EtwEventActivityIdControl` at `0x18000f835`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18000fafa`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18000fafa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000fc3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000fe3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000fc3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000fe3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fc75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fe6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fc75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fe6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ffa7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010019`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ffa7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010019`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000fa72`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000fa72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsTrimStringEnd` at `0x18000fb20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsTrimStringEnd` at `0x18000fb20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f935`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fd8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f935`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fd8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000faf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000fb4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000faf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000fb4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f964`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fb33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fd4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ffed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010064`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800100b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f964`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fb33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fd4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ffed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010064`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800100b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000fd32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000fd32`

## string_xrefs

- `0x18000ff2d`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18000ff8d`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18000ffd3`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18000ffff`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18001004a`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18001009c`: `onecoreuap\shell\windows.storage\dataaccess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CStorageFolderProxyBase::_CheckItemInProc(__int64 a1, HSTRING a2, int a3, WCHAR **a4)
{
  __int64 v8; // rcx
  GUID v9; // xmm6
  __int64 v10; // rax
  __int64 v11; // rbx
  int v13; // eax
  HRESULT v14; // edi
  int v15; // eax
  unsigned int v16; // ebx
  unsigned __int64 v17; // r12
  WCHAR *v18; // r15
  int v19; // ebx
  __int64 v20; // rsi
  unsigned __int64 v21; // rbx
  HSTRING v22; // rbx
  const WCHAR *StringRawBuffer; // rax
  PCWSTR v24; // rax
  WCHAR *v25; // rdi
  unsigned __int64 v26; // r14
  unsigned __int64 v27; // r13
  int v28; // r9d
  unsigned __int64 v29; // r8
  unsigned __int64 v30; // rdx
  WCHAR *v31; // rax
  unsigned __int64 v32; // rax
  WCHAR *v33; // r8
  unsigned __int64 v34; // rcx
  WCHAR v35; // dx
  WCHAR *v36; // rcx
  unsigned __int64 v37; // r14
  unsigned __int64 v38; // rdx
  WCHAR *v39; // rax
  __int64 v40; // rcx
  const WCHAR *v41; // rdx
  __int64 v42; // r9
  WCHAR *v43; // r8
  WCHAR v44; // ax
  WCHAR *v45; // rcx
  unsigned int v46; // r15d
  int v47[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v48; // [rsp+28h] [rbp-D8h]
  __int64 v49; // [rsp+30h] [rbp-D0h]
  WCHAR **v50; // [rsp+38h] [rbp-C8h]
  HSTRING newString; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v52; // [rsp+48h] [rbp-B8h] BYREF
  GUID v53; // [rsp+50h] [rbp-B0h] BYREF
  int v54; // [rsp+60h] [rbp-A0h]
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-90h] BYREF
  void **v56; // [rsp+90h] [rbp-70h] BYREF
  int v57; // [rsp+98h] [rbp-68h] BYREF
  const char *v58; // [rsp+A0h] [rbp-60h]
  __int64 v59; // [rsp+A8h] [rbp-58h]
  char v60; // [rsp+B0h] [rbp-50h]
  _QWORD v61[3]; // [rsp+B8h] [rbp-48h] BYREF
  int v62; // [rsp+D0h] [rbp-30h]
  int *v63; // [rsp+D8h] [rbp-28h]
  char v64; // [rsp+E0h] [rbp-20h]
  __int64 v65; // [rsp+E8h] [rbp-18h]
  __int64 v66; // [rsp+F0h] [rbp-10h]
  GUID v67; // [rsp+F8h] [rbp-8h]
  __int64 v68; // [rsp+108h] [rbp+8h]
  __int64 v69; // [rsp+110h] [rbp+10h]
  const char *v70; // [rsp+118h] [rbp+18h]
  const char *v71; // [rsp+120h] [rbp+20h]
  const char *v72; // [rsp+128h] [rbp+28h]
  const char *v73; // [rsp+130h] [rbp+30h]
  char v74; // [rsp+138h] [rbp+38h]
  const char *v75; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v50 = a4;
  v53 = 0;
  if ( (unsigned int)EtwEventActivityIdControl(1, &v53) )
  {
    v9 = GUID_NULL;
    v53 = GUID_NULL;
  }
  else
  {
    v9 = v53;
  }
  v10 = wil::details::static_lazy<WinRTStorageTelemetry>::get(
          v8,
          _lambda_6185f7d59584f69b5a44cbef7cf75836_::_lambda_invoker_cdecl_);
  v11 = v10 + 40;
  if ( !v10 )
    v11 = 0;
  v56 = &StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::`vftable';
  v60 = 0;
  v57 = 0;
  v58 = "_CheckItemInProc";
  v59 = 0;
  v61[0] = 0;
  v61[1] = &v56;
  v61[2] = 0;
  v62 = 0;
  v63 = &v57;
  v64 = 0;
  wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)v61);
  v65 = 0;
  v66 = v11;
  v67 = v9;
  v68 = 0;
  v69 = 0;
  v70 = word_1806F1E2A;
  v71 = word_1806F1E2A;
  v72 = word_1806F1E2A;
  v73 = word_1806F1E2A;
  v75 = "_CheckItemInProc";
  v74 = 0;
  *a4 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 48) + 56LL))(a1 + 48) || !a3 )
  {
    StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)&v56);
    return 2147500033LL;
  }
  v52 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)(a1 + 192) + 24LL))(
          a1 + 192,
          &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
          &v52);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCC1,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v15,
      v47[0]);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)&v56);
    return v16;
  }
  v17 = -1;
  v48 = -1;
  v49 = -1;
  v18 = 0;
  *(_QWORD *)v47 = 0;
  LOWORD(hstringHeader.Reserved.Reserved1) = 0;
  v53 = (GUID)PKEY_FileAPI_Path;
  v54 = 3;
  v19 = (*(__int64 (__fastcall **)(__int64, GUID *, HSTRING_HEADER *))(*(_QWORD *)v52 + 40LL))(
          v52,
          &v53,
          &hstringHeader);
  if ( v19 >= 0 )
  {
    if ( LOWORD(hstringHeader.Reserved.Reserved1) )
    {
      *(_QWORD *)v47 = 0;
      if ( LOWORD(hstringHeader.Reserved.Reserved1) == 31 && *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] )
      {
        v18 = *(WCHAR **)&hstringHeader.Reserved.Reserved2[8];
        *(_QWORD *)v47 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[8];
        memset(&hstringHeader, 0, sizeof(hstringHeader));
      }
      else
      {
        v19 = -2147352571;
      }
    }
    else
    {
      v19 = -2147023728;
    }
  }
  PropVariantClear(&hstringHeader.Reserved.Reserved1);
  if ( v19 >= 0 )
  {
    if ( v18 )
    {
      v20 = -1;
      do
        ++v20;
      while ( v18[v20] );
    }
    else
    {
      v20 = 0;
    }
    v48 = v20;
    v21 = v20 + 2;
    if ( v20 + 2 < (unsigned __int64)(v20 + 1) )
      goto LABEL_23;
    if ( v20 == -1 )
    {
      if ( !v18 )
      {
        v20 = 0;
        v48 = 0;
        goto LABEL_118;
      }
      v20 = -1;
      do
        ++v20;
      while ( v18[v20] );
      v48 = v20;
    }
    if ( v18 )
    {
      v37 = v20 + 1;
      goto LABEL_87;
    }
LABEL_118:
    v37 = 0;
LABEL_87:
    v49 = v37;
    if ( v37 )
    {
      v14 = 0;
      if ( v21 <= v37 )
      {
LABEL_100:
        if ( v14 < 0 )
          goto LABEL_123;
        v40 = 1;
        v41 = L"\\";
        v42 = 2;
        v43 = &v18[v20];
        do
        {
          if ( !v40 )
            break;
          v44 = *v41;
          if ( !*v41 )
            break;
          ++v41;
          *v43++ = v44;
          --v40;
          --v42;
        }
        while ( v42 );
        v45 = v43 - 1;
        if ( v42 )
          v45 = v43;
        *v45 = 0;
        v48 = ++v20;
LABEL_24:
        if ( v14 >= 0 )
        {
          v22 = 0;
          *(_QWORD *)&v53.Data1 = 0;
          if ( dword_180808188 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                             + (unsigned int)tls_index)
                                           + 8LL) )
          {
            Init_thread_header(&dword_180808188);
            if ( dword_180808188 == -1 )
            {
              if ( WindowsCreateStringReference(L"\\/", 2u, &::hstringHeader, &string) < 0 )
                RaiseException(0xC000000D, 1u, 0, 0);
              Init_thread_footer(&dword_180808188);
            }
          }
          StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
          newString = 0;
          if ( PathIsRootW(StringRawBuffer) )
          {
            v14 = WindowsDuplicateString(a2, &newString);
            if ( v14 >= 0 )
            {
              v22 = newString;
              *(_QWORD *)&v53.Data1 = newString;
              WindowsDeleteString(0);
            }
          }
          else
          {
            v14 = WindowsTrimStringEnd(a2, string, &newString);
            if ( v14 >= 0 )
            {
              v22 = newString;
              WindowsDeleteString(0);
            }
            *(_QWORD *)&v53.Data1 = v22;
          }
          if ( v14 >= 0 )
          {
            v24 = WindowsGetStringRawBuffer(v22, 0);
            v25 = (WCHAR *)v24;
            if ( !v24 )
            {
              do
LABEL_42:
                ++v17;
              while ( v18[v17] );
              if ( v17 > 0xFFFFFFFF )
              {
                LODWORD(v17) = -1;
                RaiseException(0xC000000D, 1u, 0, 0);
              }
              WindowsCreateStringReference(
                v18,
                v17,
                (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
                (HSTRING *)&hstringHeader);
              v13 = StorageItemHelpers::ValidateCanonicalPath(hstringHeader.Reserved.Reserved1, 1);
              v14 = v13;
              if ( v13 >= 0 )
              {
                *v50 = v18;
                if ( v22 )
                  WindowsDeleteString(v22);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
                StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)&v56);
                return 0;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xCC8,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
                (const char *)(unsigned int)v13,
                v47[0]);
              if ( v22 )
                WindowsDeleteString(v22);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v47);
LABEL_126:
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
              StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)&v56);
              return (unsigned int)v14;
            }
            v26 = -1;
            do
              ++v26;
            while ( v24[v26] );
            if ( v20 == -1 )
            {
              if ( v18 )
              {
                v20 = -1;
                do
                  ++v20;
                while ( v18[v20] );
              }
              else
              {
                v20 = 0;
              }
              v48 = v20;
            }
            v27 = v26 + v20 + 1;
            if ( v27 < v26 + v20 )
              goto LABEL_40;
            v29 = v49;
            if ( v49 != -1 )
            {
LABEL_47:
              if ( v29 )
              {
                v28 = 0;
                LODWORD(newString) = 0;
                if ( v27 <= v29 )
                {
LABEL_60:
                  if ( v28 < 0 )
                  {
LABEL_132:
                    v46 = (unsigned int)newString;
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xCC7,
                      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
                      (const char *)(unsigned int)newString,
                      v47[0]);
                    if ( v22 )
                      WindowsDeleteString(v22);
                    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v47);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
                    StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)&v56);
                    return v46;
                  }
                  v32 = v26 + 1;
                  v33 = &v18[v20];
                  if ( v26 != -1 )
                  {
                    if ( v32 > 0x7FFFFFFF || v26 > 0x7FFFFFFE )
                    {
                      *v33 = 0;
                    }
                    else
                    {
                      v34 = v26;
                      do
                      {
                        if ( !v34 )
                          break;
                        v35 = *v25;
                        if ( !*v25 )
                          break;
                        ++v25;
                        *v33++ = v35;
                        --v34;
                        --v32;
                      }
                      while ( v32 );
                      v36 = v33 - 1;
                      if ( v32 )
                        v36 = v33;
                      *v36 = 0;
                    }
                  }
                  v48 = v26 + v20;
LABEL_41:
                  if ( v28 >= 0 )
                    goto LABEL_42;
                  goto LABEL_132;
                }
                newString = 0;
                if ( is_mul_ok(v29, 2u) )
                {
                  v30 = v29 + 2048;
                  if ( v29 <= 0x800 )
                    v30 = 2 * v29;
                  if ( v27 <= v30 )
                    v27 = v30;
                  v31 = (WCHAR *)CoTaskMemRealloc(v18, 2 * v27);
                  if ( v31 )
                  {
                    LODWORD(newString) = 0;
                    v28 = 0;
LABEL_59:
                    *(_QWORD *)v47 = v31;
                    v18 = v31;
                    v49 = v27;
                    goto LABEL_60;
                  }
                  goto LABEL_79;
                }
              }
              else
              {
                newString = 0;
                if ( is_mul_ok(v27, 2u) )
                {
                  v31 = (WCHAR *)CoTaskMemAlloc(2 * v27);
                  if ( v31 )
                  {
                    LODWORD(newString) = 0;
                    *v31 = 0;
                    v28 = 0;
                    goto LABEL_59;
                  }
LABEL_79:
                  v28 = -2147024882;
                  LODWORD(newString) = -2147024882;
                  goto LABEL_60;
                }
              }
LABEL_40:
              v28 = -2147024362;
              LODWORD(newString) = -2147024362;
              goto LABEL_41;
            }
            if ( v20 == -1 )
            {
              if ( !v18 )
              {
                v20 = 0;
                v48 = 0;
                goto LABEL_120;
              }
              v20 = -1;
              do
                ++v20;
              while ( v18[v20] );
              v48 = v20;
            }
            if ( v18 )
            {
              v29 = v20 + 1;
LABEL_115:
              v49 = v29;
              goto LABEL_47;
            }
LABEL_120:
            v29 = 0;
            goto LABEL_115;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xCC6,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
            (const char *)(unsigned int)v14,
            v47[0]);
          if ( v22 )
            WindowsDeleteString(v22);
LABEL_124:
          if ( v18 )
            CoTaskMemFree(v18);
          goto LABEL_126;
        }
LABEL_123:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCC4,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
          (const char *)(unsigned int)v14,
          v47[0]);
        goto LABEL_124;
      }
      *(_QWORD *)&v53.Data1 = 0;
      if ( is_mul_ok(v37, 2u) )
      {
        v38 = v37 + 2048;
        if ( v37 <= 0x800 )
          v38 = 2 * v37;
        if ( v21 <= v38 )
          v21 = v38;
        v39 = (WCHAR *)CoTaskMemRealloc(v18, 2 * v21);
        if ( !v39 )
          goto LABEL_95;
        goto LABEL_99;
      }
    }
    else
    {
      *(_QWORD *)&v53.Data1 = 0;
      if ( is_mul_ok(v21, 2u) )
      {
        v39 = (WCHAR *)CoTaskMemAlloc(2 * v21);
        if ( !v39 )
        {
LABEL_95:
          v14 = -2147024882;
          goto LABEL_100;
        }
        v14 = 0;
        *v39 = 0;
LABEL_99:
        *(_QWORD *)v47 = v39;
        v18 = v39;
        v49 = v21;
        goto LABEL_100;
      }
    }
LABEL_23:
    v14 = -2147024362;
    goto LABEL_24;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xCC3,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
    (const char *)(unsigned int)v19,
    v47[0]);
  if ( v18 )
    CoTaskMemFree(v18);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
  StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)&v56);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18000f7e0  mov     [rsp-8+arg_8], rbx
0x18000f7e5  push    rbp
0x18000f7e6  push    rsi
0x18000f7e7  push    rdi
0x18000f7e8  push    r12
0x18000f7ea  push    r13
0x18000f7ec  push    r14
0x18000f7ee  push    r15
0x18000f7f0  lea     rbp, [rsp-70h]
0x18000f7f5  sub     rsp, 170h
0x18000f7fc  movaps  [rsp+1A0h+var_40], xmm6
0x18000f804  mov     rax, cs:__security_cookie
0x18000f80b  xor     rax, rsp
0x18000f80e  mov     [rbp+0A0h+var_50], rax
0x18000f812  mov     r14, r9
0x18000f815  mov     [rsp+1A0h+var_168], r9
0x18000f81a  mov     esi, r8d
0x18000f81d  mov     r13, rdx
0x18000f820  mov     rdi, rcx
0x18000f823  xorps   xmm0, xmm0
0x18000f826  movups  [rsp+1A0h+var_150], xmm0
0x18000f82b  lea     rdx, [rsp+1A0h+var_150]
0x18000f830  mov     ecx, 1
0x18000f835  call    cs:__imp_EtwEventActivityIdControl
0x18000f83b  test    eax, eax
0x18000f83d  jnz     loc_1800100CC
0x18000f843  movups  xmm6, [rsp+1A0h+var_150]
0x18000f848  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_6185f7d59584f69b5a44cbef7cf75836_@@CA@XZ; _lambda_6185f7d59584f69b5a44cbef7cf75836_::_lambda_invoker_cdecl_(void)
0x18000f84f  call    ?get@?$static_lazy@VWinRTStorageTelemetry@@@details@wil@@QEAAPEAVWinRTStorageTelemetry@@P6AXXZ@Z; wil::details::static_lazy<WinRTStorageTelemetry>::get(void (*)(void))
0x18000f854  lea     rbx, [rax+28h]
0x18000f858  xor     r12d, r12d
0x18000f85b  test    rax, rax
0x18000f85e  cmovz   rbx, r12
0x18000f862  lea     rax, ??_7ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@6B@; const StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::`vftable'
0x18000f869  mov     [rbp+0A0h+var_110], rax
0x18000f86d  mov     [rbp+0A0h+var_F0], r12b
0x18000f871  mov     [rbp+0A0h+var_108], r12d
0x18000f875  lea     r15, aCheckiteminpro; "_CheckItemInProc"
0x18000f87c  mov     [rbp+0A0h+var_100], r15
0x18000f880  mov     [rbp+0A0h+var_F8], r12
0x18000f884  mov     [rbp+0A0h+var_E8], r12
0x18000f888  lea     rax, [rbp+0A0h+var_110]
0x18000f88c  mov     [rbp+0A0h+var_E0], rax
0x18000f890  mov     [rbp+0A0h+var_D8], r12
0x18000f894  mov     [rbp+0A0h+var_D0], r12d
0x18000f898  lea     rax, [rbp+0A0h+var_108]
0x18000f89c  mov     [rbp+0A0h+var_C8], rax
0x18000f8a0  mov     [rbp+0A0h+var_C0], r12b
0x18000f8a4  lea     rcx, [rbp+0A0h+var_E8]; this
0x18000f8a8  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18000f8ad  nop
0x18000f8ae  mov     [rbp+0A0h+var_B8], r12
0x18000f8b2  mov     [rbp+0A0h+var_B0], rbx
0x18000f8b6  movups  [rbp+0A0h+var_A8], xmm6
0x18000f8ba  mov     [rbp+0A0h+var_98], r12
0x18000f8be  mov     [rbp+0A0h+var_90], r12
0x18000f8c2  lea     rax, word_1806F1E2A
0x18000f8c9  mov     [rbp+0A0h+var_88], rax
0x18000f8cd  mov     [rbp+0A0h+var_80], rax
0x18000f8d1  mov     [rbp+0A0h+var_78], rax
0x18000f8d5  mov     [rbp+0A0h+var_70], rax
0x18000f8d9  mov     [rbp+0A0h+var_60], r15
0x18000f8dd  mov     [rbp+0A0h+var_68], r12b
0x18000f8e1  mov     [r14], r12
0x18000f8e4  lea     rcx, [rdi+30h]
0x18000f8e8  mov     rax, [rcx]
0x18000f8eb  mov     rax, [rax+38h]
0x18000f8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8f4  test    al, al
0x18000f8f6  jz      loc_18000F9B0
0x18000f8fc  lea     rcx, [rbp+0A0h+var_110]; this
0x18000f900  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x18000f905  mov     eax, 80004001h
0x18000f90a  jmp     short loc_18000F981
0x18000f90c  mov     r12d, eax
0x18000f90f  xor     r9d, r9d; lpArguments
0x18000f912  xor     r8d, r8d; nNumberOfArguments
0x18000f915  mov     edx, 1; dwExceptionFlags
0x18000f91a  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000f91f  call    cs:__imp_RaiseException
0x18000f925  lea     r9, [rsp+1A0h+hstringHeader]; string
0x18000f92a  lea     r8, [rsp+1A0h+hstringHeader.Reserved+8]; hstringHeader
0x18000f92f  mov     edx, r12d; length
0x18000f932  mov     rcx, r15; sourceString
0x18000f935  call    cs:__imp_WindowsCreateStringReference
0x18000f93b  mov     edx, 1
0x18000f940  mov     rcx, qword ptr [rsp+1A0h+hstringHeader.Reserved]
0x18000f945  call    ?ValidateCanonicalPath@StorageItemHelpers@@YAJPEAUHSTRING__@@W4CANONICALIZE_FLAGS@@@Z; StorageItemHelpers::ValidateCanonicalPath(HSTRING__ *,CANONICALIZE_FLAGS)
0x18000f94a  mov     edi, eax
0x18000f94c  test    eax, eax
0x18000f94e  js      loc_180010092
0x18000f954  mov     rax, [rsp+1A0h+var_168]
0x18000f959  mov     [rax], r15
0x18000f95c  test    rbx, rbx
0x18000f95f  jz      short loc_18000F96B
0x18000f961  mov     rcx, rbx; string
0x18000f964  call    cs:__imp_WindowsDeleteString
0x18000f96a  nop
0x18000f96b  lea     rcx, [rsp+1A0h+var_158]
0x18000f970  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000f975  nop
0x18000f976  lea     rcx, [rbp+0A0h+var_110]; this
0x18000f97a  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x18000f97f  xor     eax, eax
0x18000f981  mov     rcx, [rbp+0A0h+var_50]
0x18000f985  xor     rcx, rsp; StackCookie
0x18000f988  call    __security_check_cookie
0x18000f98d  mov     rbx, [rsp+1A0h+arg_8]
0x18000f995  movaps  xmm6, [rsp+1A0h+var_40]
0x18000f99d  add     rsp, 170h
0x18000f9a4  pop     r15
0x18000f9a6  pop     r14
0x18000f9a8  pop     r13
0x18000f9aa  pop     r12
0x18000f9ac  pop     rdi
0x18000f9ad  pop     rsi
0x18000f9ae  pop     rbp
0x18000f9af  retn
0x18000f9b0  test    esi, esi
0x18000f9b2  jz      loc_18000F8FC
0x18000f9b8  mov     [rsp+1A0h+var_158], r12
0x18000f9bd  lea     rcx, [rdi+0C0h]
0x18000f9c4  mov     rax, [rcx]
0x18000f9c7  lea     r8, [rsp+1A0h+var_158]
0x18000f9cc  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18000f9d3  mov     rax, [rax+18h]
0x18000f9d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9dc  mov     ebx, eax
0x18000f9de  test    eax, eax
0x18000f9e0  js      loc_18000FF23
0x18000f9e6  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18000f9ed  mov     [rsp+1A0h+var_178], r12
0x18000f9f2  mov     [rsp+1A0h+var_170], r12
0x18000f9f7  movups  xmm0, cs:PKEY_FileAPI_Path
0x18000f9fe  mov     ecx, cs:dword_180717500
0x18000fa04  xor     r15d, r15d
0x18000fa07  mov     qword ptr [rsp+1A0h+var_180], r15
0x18000fa0c  xor     eax, eax
0x18000fa0e  mov     word ptr [rsp+1A0h+hstringHeader.Reserved], ax
0x18000fa13  movaps  [rsp+1A0h+var_150], xmm0
0x18000fa18  mov     [rsp+1A0h+var_140], ecx
0x18000fa1c  mov     rcx, [rsp+1A0h+var_158]
0x18000fa21  mov     rax, [rcx]
0x18000fa24  lea     r8, [rsp+1A0h+hstringHeader]
0x18000fa29  lea     rdx, [rsp+1A0h+var_150]
0x18000fa2e  mov     rax, [rax+28h]
0x18000fa32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa37  mov     ebx, eax
0x18000fa39  movzx   eax, word ptr [rsp+1A0h+hstringHeader.Reserved]
0x18000fa3e  test    ebx, ebx
0x18000fa40  js      short loc_18000FA6D
0x18000fa42  test    ax, ax
0x18000fa45  jz      loc_18000FBCF
0x18000fa4b  test    ebx, ebx
0x18000fa4d  js      short loc_18000FA6D
0x18000fa4f  mov     qword ptr [rsp+1A0h+var_180], r15; int
0x18000fa54  cmp     ax, 1Fh
0x18000fa58  jnz     short loc_18000FA68
0x18000fa5a  mov     rax, qword ptr [rsp+1A0h+hstringHeader.Reserved+8]
0x18000fa5f  test    rax, rax
0x18000fa62  jnz     loc_18000FD12
0x18000fa68  mov     ebx, 80020005h
0x18000fa6d  lea     rcx, [rsp+1A0h+hstringHeader]; pvar
0x18000fa72  call    cs:__imp_PropVariantClear
0x18000fa78  test    ebx, ebx
0x18000fa7a  js      loc_18000FFF5
0x18000fa80  test    r15, r15
0x18000fa83  jz      loc_18000FF75
0x18000fa89  mov     rsi, r12
0x18000fa8c  nop     dword ptr [rax+00h]
0x18000fa90  inc     rsi
0x18000fa93  cmp     word ptr [r15+rsi*2], 0
0x18000fa99  jnz     short loc_18000FA90
0x18000fa9b  mov     [rsp+1A0h+var_178], rsi
0x18000faa0  lea     rax, [rsi+1]
0x18000faa4  lea     rbx, [rax+1]
0x18000faa8  cmp     rbx, rax
0x18000faab  jnb     loc_18000FDBB
0x18000fab1  mov     edi, 80070216h
0x18000fab6  test    edi, edi
0x18000fab8  js      loc_18000FF83
0x18000fabe  xor     ebx, ebx
0x18000fac0  mov     qword ptr [rsp+1A0h+var_150], rbx
0x18000fac5  mov     ecx, cs:_tls_index
0x18000facb  mov     rax, gs:58h
0x18000fad4  mov     edx, 8
0x18000fad9  mov     rax, [rax+rcx*8]
0x18000fadd  mov     eax, [rdx+rax]
0x18000fae0  cmp     cs:dword_180808188, eax
0x18000fae6  jg      loc_18000FD59
0x18000faec  xor     edx, edx; length
0x18000faee  mov     rcx, r13; string
0x18000faf1  call    cs:__imp_WindowsGetStringRawBuffer
0x18000faf7  mov     rcx, rax; pszPath
0x18000fafa  call    cs:__imp_PathIsRootW
0x18000fb00  mov     [rsp+1A0h+newString], 0
0x18000fb09  mov     rcx, r13; string
0x18000fb0c  test    eax, eax
0x18000fb0e  jnz     loc_18000FD2D
0x18000fb14  lea     r8, [rsp+1A0h+newString]; newString
0x18000fb19  mov     rdx, cs:string; trimString
0x18000fb20  call    cs:__imp_WindowsTrimStringEnd
0x18000fb26  mov     edi, eax
0x18000fb28  test    eax, eax
0x18000fb2a  js      short loc_18000FB39
0x18000fb2c  mov     rbx, [rsp+1A0h+newString]
0x18000fb31  xor     ecx, ecx; string
0x18000fb33  call    cs:__imp_WindowsDeleteString
0x18000fb39  mov     qword ptr [rsp+1A0h+var_150], rbx
0x18000fb3e  test    edi, edi
0x18000fb40  js      loc_18000FFC9
0x18000fb46  xor     edx, edx; length
0x18000fb48  mov     rcx, rbx; string
0x18000fb4b  call    cs:__imp_WindowsGetStringRawBuffer
0x18000fb51  mov     rdi, rax
0x18000fb54  test    rax, rax
0x18000fb57  jz      short loc_18000FBB1
0x18000fb59  mov     r14, r12
0x18000fb5c  nop     dword ptr [rax+00h]
0x18000fb60  inc     r14
0x18000fb63  cmp     word ptr [rax+r14*2], 0
0x18000fb69  jnz     short loc_18000FB60
0x18000fb6b  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000fb6f  jnz     short loc_18000FB90
0x18000fb71  test    r15, r15
0x18000fb74  jz      loc_18000FF7C
0x18000fb7a  mov     rsi, r12
0x18000fb7d  nop     dword ptr [rax]
0x18000fb80  inc     rsi
0x18000fb83  cmp     word ptr [r15+rsi*2], 0
0x18000fb89  jnz     short loc_18000FB80
0x18000fb8b  mov     [rsp+1A0h+var_178], rsi
0x18000fb90  lea     rax, [r14+rsi]
0x18000fb94  lea     r13, [rax+1]
0x18000fb98  cmp     r13, rax
0x18000fb9b  jnb     short loc_18000FBD9
0x18000fb9d  mov     r9d, 80070216h
0x18000fba3  mov     dword ptr [rsp+1A0h+newString], r9d
0x18000fba8  test    r9d, r9d
0x18000fbab  js      loc_18001003B
0x18000fbb1  inc     r12
0x18000fbb4  cmp     word ptr [r15+r12*2], 0
0x18000fbba  jnz     short loc_18000FBB1
0x18000fbbc  mov     eax, 0FFFFFFFFh
0x18000fbc1  cmp     r12, rax
0x18000fbc4  jbe     loc_18000F925
0x18000fbca  jmp     loc_18000F90C
0x18000fbcf  mov     ebx, 80070490h
0x18000fbd4  jmp     loc_18000FA6D
0x18000fbd9  mov     r8, [rsp+1A0h+var_170]
0x18000fbde  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000fbe2  jz      loc_18000FEEF
0x18000fbe8  test    r8, r8
0x18000fbeb  jz      short loc_18000FC58
0x18000fbed  xor     r9d, r9d
0x18000fbf0  mov     dword ptr [rsp+1A0h+newString], r9d
0x18000fbf5  cmp     r13, r8
0x18000fbf8  jbe     loc_18000FCA1
0x18000fbfe  mov     [rsp+1A0h+newString], r9
0x18000fc03  mov     eax, 2
0x18000fc08  mul     r8
0x18000fc0b  test    rdx, rdx
0x18000fc0e  jnz     short loc_18000FB9D
0x18000fc10  mov     rcx, rax
0x18000fc13  sub     rcx, r8
0x18000fc16  lea     rdx, [r8+800h]
0x18000fc1d  cmp     rcx, 800h
0x18000fc24  cmovbe  rdx, rax
0x18000fc28  cmp     r13, rdx
0x18000fc2b  cmovbe  r13, rdx
0x18000fc2f  lea     rdx, ds:0[r13*2]; cb
0x18000fc37  mov     rcx, r15; pv
0x18000fc3a  call    cs:__imp_CoTaskMemRealloc
0x18000fc40  test    rax, rax
0x18000fc43  jz      loc_18000FDAB
0x18000fc49  mov     dword ptr [rsp+1A0h+newString], 0
0x18000fc51  mov     r9d, dword ptr [rsp+1A0h+newString]
0x18000fc56  jmp     short loc_18000FC94
0x18000fc58  mov     [rsp+1A0h+newString], 0
0x18000fc61  mov     eax, 2
0x18000fc66  mul     r13
0x18000fc69  test    rdx, rdx
0x18000fc6c  jnz     loc_18000FB9D
0x18000fc72  mov     rcx, rax; cb
0x18000fc75  call    cs:__imp_CoTaskMemAlloc
0x18000fc7b  test    rax, rax
0x18000fc7e  jz      loc_18000FDAB
0x18000fc84  mov     dword ptr [rsp+1A0h+newString], 0
0x18000fc8c  xor     ecx, ecx
0x18000fc8e  mov     [rax], cx
0x18000fc91  mov     r9d, ecx
0x18000fc94  mov     qword ptr [rsp+1A0h+var_180], rax
0x18000fc99  mov     r15, rax
0x18000fc9c  mov     [rsp+1A0h+var_170], r13
0x18000fca1  test    r9d, r9d
0x18000fca4  js      loc_18001003B
0x18000fcaa  lea     rax, [r14+1]
0x18000fcae  lea     r8, [r15+rsi*2]
0x18000fcb2  test    rax, rax
0x18000fcb5  jz      short loc_18000FD05
  ... truncated ...
```
