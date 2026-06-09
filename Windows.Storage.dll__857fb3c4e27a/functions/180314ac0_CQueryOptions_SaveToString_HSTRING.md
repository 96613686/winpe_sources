# CQueryOptions::SaveToString(HSTRING__ * *)

- ea: `0x180314ac0`
- end: `0x1803154d7`
- name: `?SaveToString@CQueryOptions@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `2583`
- prototype: `int(CQueryOptions *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180061ba8`
- `0x18006d92c`
- `0x1802073d0`
- `0x180292cf0`
- `0x180314ac0`
- `0x1803a4cb0`
- `0x1803a4cd4`
- `0x1803a513c`
- `0x1803a518c`
- `0x180420c5c`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180314e75`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180314e75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803154a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803154a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180315059`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180315106`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180315059`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180315106`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180314e61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180314e61`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18031503e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1803150b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18031503e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1803150b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180314dd2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180314dd2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180315443`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180315443`
- `ntdll!EtwEventSetInformation` at `0x180314c08`
- `ntdll!EtwEventSetInformation` at `0x180314d49`
- `ntdll!EtwEventSetInformation` at `0x180314c08`
- `ntdll!EtwEventSetInformation` at `0x180314d49`
- `ntdll!EtwEventRegister` at `0x180314bed`
- `ntdll!EtwEventRegister` at `0x180314d2e`
- `ntdll!EtwEventRegister` at `0x180314bed`
- `ntdll!EtwEventRegister` at `0x180314d2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180315473`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180315473`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180314c37`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180314d78`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180314c37`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180314d78`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180314b22`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180314c78`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180314b22`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180314c78`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1803150c5`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1803150c5`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1803153b9`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1803153b9`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180314eb3`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180314ed0`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180314ef0`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180314f10`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180314f30`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180314f60`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180314f80`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18031506c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180315188`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1803151f9`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18031522a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180315246`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180315262`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18031527e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18031529a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1803152ce`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1803152fb`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180315342`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180314eb3`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180314ed0`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180314ef0`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180314f10`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180314f30`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180314f60`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180314f80`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18031506c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180315188`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1803151f9`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18031522a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180315246`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180315262`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18031527e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18031529a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1803152ce`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1803152fb`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180315342`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x1803153d4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x1803153d4`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180314e83`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180314e83`
- `api-ms-win-shcore-stream-l1-1-0!IStream_WriteStr` at `0x180314fa2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_WriteStr` at `0x180314fc4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_WriteStr` at `0x180314fe6`
- `api-ms-win-shcore-stream-l1-1-0!IStream_WriteStr` at `0x180315122`
- `api-ms-win-shcore-stream-l1-1-0!IStream_WriteStr` at `0x1803151e0`
- `api-ms-win-shcore-stream-l1-1-0!IStream_WriteStr` at `0x180315390`
- `api-ms-win-shcore-stream-l1-1-0!IStream_WriteStr` at `0x180314fa2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_WriteStr` at `0x180314fc4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_WriteStr` at `0x180314fe6`
- `api-ms-win-shcore-stream-l1-1-0!IStream_WriteStr` at `0x180315122`
- `api-ms-win-shcore-stream-l1-1-0!IStream_WriteStr` at `0x1803151e0`
- `api-ms-win-shcore-stream-l1-1-0!IStream_WriteStr` at `0x180315390`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180315456`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180315456`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180314f96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180314fb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180314fda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180315116`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803151d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180315384`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180314f96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180314fb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180314fda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180315116`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803151d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180315384`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803150d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180315133`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180315205`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803153a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803150d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180315133`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180315205`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803153a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1803150f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180315463`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1803150f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180315463`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CQueryOptions::SaveToString(CQueryOptions *this, HSTRING *a2)
{
  struct _tlgProvider_t *v4; // rbx
  _DWORD *v5; // rax
  struct _tlgProvider_t *v6; // rbx
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  _QWORD **v9; // rdi
  RTL_SRWLOCK *v10; // r14
  _QWORD *v11; // r9
  const WCHAR *v12; // rax
  int v13; // ecx
  int v14; // edx
  char *v15; // rsi
  _QWORD *v16; // rsi
  IStream *v17; // rax
  IStream *v18; // rdi
  HRESULT v19; // ebx
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v21; // rax
  const WCHAR *v22; // rax
  CQueryOptions *v23; // rcx
  __int64 v24; // rsi
  WINBOOL *v25; // rsi
  int v26; // eax
  __int64 v27; // r14
  __int64 v28; // rsi
  RTL_SRWLOCK *v29; // rcx
  RTL_SRWLOCK *v30; // rcx
  const WCHAR *v31; // rax
  __int64 v32; // rcx
  unsigned int v33; // esi
  const WCHAR *v34; // rax
  __int64 v35; // rax
  WINBOOL v36; // ecx
  __int64 v37; // rcx
  unsigned int v38; // esi
  const WCHAR *v39; // rax
  __int64 v40; // rcx
  unsigned __int64 v41; // rsi
  WCHAR *v42; // r14
  unsigned int v43; // ebx
  WINBOOL fPending; // [rsp+28h] [rbp-58h] BYREF
  LPVOID Context[2]; // [rsp+30h] [rbp-50h] BYREF
  __int128 v47; // [rsp+40h] [rbp-40h] BYREF
  PCWSTR sourceString; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF

  if ( _InterlockedIncrement(&`CQueryOptions::SaveToString'::`4'::__wil_apiCallCounter) == 1 )
  {
    Context[0] = 0;
    fPending = 0;
    if ( InitOnceBeginInitialize(&`wil::details::ApiTelemetryLogger::Instance'::`2'::wrapper, 0, &fPending, Context)
      && fPending )
    {
      Context[0] = &qword_180804908;
      qword_180804910 = 0;
      byte_180804918 = 0;
      dword_18080491C = 0;
      qword_180804908 = &wil::details::ApiTelemetryLogger::`vftable';
      qword_180804920 = (struct _tlgProvider_t *)&`wil::details::ApiTelemetryLogger::StaticHandle::StaticHandle'::`2'::__hInner;
      xmmword_180804928 = 0;
      qword_180804938 = 0;
      dword_180804940 = 0;
      dword_180804944 = 1200000;
      atexit(_lambda_6b26b9d13d28b4db0bc0125880e9ff13_::_lambda_invoker_cdecl_);
      v4 = qword_180804920;
      qword_180804910 = (__int64)qword_180804920;
      byte_180804918 = 1;
      v47 = *(_OWORD *)(*((_QWORD *)qword_180804920 + 1) - 16LL);
      if ( *((_QWORD *)qword_180804920 + 4) )
        __fastfail(5u);
      *((_QWORD *)qword_180804920 + 5) = 0;
      *((_QWORD *)v4 + 6) = 0;
      if ( !(unsigned int)EtwEventRegister(&v47, tlgEnableCallback, v4, (char *)v4 + 32) )
        EtwEventSetInformation(*((_QWORD *)v4 + 4), 2, *((_QWORD *)v4 + 1), **((unsigned __int16 **)v4 + 1));
      dword_18080491C = 1;
      (*(void (__fastcall **)(void *))(qword_180804908 + 8LL))(&qword_180804908);
      InitOnceComplete(&`wil::details::ApiTelemetryLogger::Instance'::`2'::wrapper, 0, &qword_180804908);
    }
    v5 = (_DWORD *)*((_QWORD *)Context[0] + 1);
    if ( v5 && *v5 )
    {
      Context[0] = 0;
      fPending = 0;
      if ( InitOnceBeginInitialize(&`wil::details::ApiTelemetryLogger::Instance'::`2'::wrapper, 0, &fPending, Context)
        && fPending )
      {
        Context[0] = &qword_180804908;
        qword_180804910 = 0;
        byte_180804918 = 0;
        dword_18080491C = 0;
        qword_180804908 = &wil::details::ApiTelemetryLogger::`vftable';
        qword_180804920 = (struct _tlgProvider_t *)&`wil::details::ApiTelemetryLogger::StaticHandle::StaticHandle'::`2'::__hInner;
        xmmword_180804928 = 0;
        qword_180804938 = 0;
        dword_180804940 = 0;
        dword_180804944 = 1200000;
        atexit(_lambda_6b26b9d13d28b4db0bc0125880e9ff13_::_lambda_invoker_cdecl_);
        v6 = qword_180804920;
        qword_180804910 = (__int64)qword_180804920;
        byte_180804918 = 1;
        v47 = *(_OWORD *)(*((_QWORD *)qword_180804920 + 1) - 16LL);
        if ( *((_QWORD *)qword_180804920 + 4) )
          __fastfail(5u);
        *((_QWORD *)qword_180804920 + 5) = 0;
        *((_QWORD *)v6 + 6) = 0;
        if ( !(unsigned int)EtwEventRegister(&v47, tlgEnableCallback, v6, (char *)v6 + 32) )
          EtwEventSetInformation(*((_QWORD *)v6 + 4), 2, *((_QWORD *)v6 + 1), **((unsigned __int16 **)v6 + 1));
        dword_18080491C = 1;
        (*(void (__fastcall **)(void *))(qword_180804908 + 8LL))(&qword_180804908);
        InitOnceComplete(&`wil::details::ApiTelemetryLogger::Instance'::`2'::wrapper, 0, &qword_180804908);
      }
      v7 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
      v8 = v7;
      if ( v7 )
      {
        *v7 = L"Windows.Storage.Search.QueryOptions";
        v7[1] = L"SaveToString";
        v7[2] = 0;
        v7[3] = &`CQueryOptions::SaveToString'::`4'::__wil_apiCallCounter;
        v7[4] = 0;
        v9 = (_QWORD **)((char *)Context[0] + 32);
        v10 = (RTL_SRWLOCK *)((char *)Context[0] + 40);
        AcquireSRWLockExclusive((PSRWLOCK)Context[0] + 5);
        while ( 1 )
        {
          v11 = *v9;
          if ( !*v9 )
            break;
          v12 = L"Windows.Storage.Search.QueryOptions";
          do
          {
            v13 = *(const WCHAR *)((char *)v12 + *v11 - (_QWORD)L"Windows.Storage.Search.QueryOptions");
            v14 = *v12 - v13;
            if ( v14 )
              break;
            ++v12;
          }
          while ( v13 );
          if ( v14 <= 0 )
            break;
          v9 = (_QWORD **)(v11 + 4);
        }
        *v9 = 0;
        v15 = (char *)v8[4];
        v8[4] = v11;
        if ( v15 )
        {
          wistd::unique_ptr<wil::details::ApiTelemetryLogger::ApiDataList::ApiData,wistd::default_delete<wil::details::ApiTelemetryLogger::ApiDataList::ApiData>>::reset(
            v15 + 32,
            0);
          operator delete(v15, (const struct std::nothrow_t *)0x28);
        }
        v16 = *v9;
        *v9 = v8;
        if ( v16 )
        {
          wistd::unique_ptr<wil::details::ApiTelemetryLogger::ApiDataList::ApiData,wistd::default_delete<wil::details::ApiTelemetryLogger::ApiDataList::ApiData>>::reset(
            v16 + 4,
            0);
          operator delete(v16, (const struct std::nothrow_t *)0x28);
        }
        if ( v10 )
          ReleaseSRWLockExclusive(v10);
      }
    }
  }
  *a2 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  v17 = SHCreateMemStream(0, 0);
  v18 = v17;
  *(_QWORD *)&v47 = v17;
  if ( !v17 )
  {
    v19 = -2147024882;
    goto LABEL_115;
  }
  fPending = 4;
  v19 = IStream_Write(v17, &fPending, 4u);
  if ( v19 >= 0 )
  {
    v19 = IStream_Write(v18, (char *)this + 96, 4u);
    if ( v19 >= 0 )
    {
      v19 = IStream_Write(v18, (char *)this + 128, 4u);
      if ( v19 >= 0 )
      {
        v19 = IStream_Write(v18, (char *)this + 144, 4u);
        if ( v19 >= 0 )
        {
          v19 = IStream_Write(v18, (char *)this + 176, 0x10u);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59687846>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_59687846>::GetImpl'::`2'::impl) )
          {
            if ( v19 < 0 )
              goto LABEL_115;
            v19 = IStream_Write(v18, (char *)this + 148, 1u);
            if ( v19 < 0 )
              goto LABEL_115;
            v19 = IStream_Write(v18, (char *)this + 149, 1u);
          }
          if ( v19 >= 0 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 13), 0);
            v19 = IStream_WriteStr(v18, StringRawBuffer);
            if ( v19 >= 0 )
            {
              v21 = WindowsGetStringRawBuffer(*((HSTRING *)this + 14), 0);
              v19 = IStream_WriteStr(v18, v21);
              if ( v19 >= 0 )
              {
                v22 = WindowsGetStringRawBuffer(*((HSTRING *)this + 15), 0);
                v19 = IStream_WriteStr(v18, v22);
                if ( v19 >= 0 )
                {
                  v19 = CQueryOptions::_IStream_WriteString(v23, v18, (CQueryOptions *)((char *)this + 136));
                  if ( v19 >= 0 )
                  {
                    fPending = 0;
                    v24 = *((_QWORD *)this + 20);
                    if ( v24 )
                    {
                      v25 = *(WINBOOL **)(v24 + 56);
                      if ( v25[28] == 1 )
                      {
                        v26 = v25[30];
                        if ( v26 >= 0 )
                          v25[30] = v26 + 1;
                      }
                      else
                      {
                        AcquireSRWLockShared((PSRWLOCK)v25 + 15);
                      }
                      fPending = v25[20];
                      if ( v25[28] == 1 )
                        --v25[30];
                      else
                        ReleaseSRWLockShared((PSRWLOCK)v25 + 15);
                    }
                    v19 = IStream_Write(v18, &fPending, 4u);
                    v27 = 0;
                    if ( fPending )
                    {
                      while ( v19 >= 0 )
                      {
                        Context[0] = 0;
                        v28 = *(_QWORD *)(*((_QWORD *)this + 20) + 56LL);
                        v29 = (RTL_SRWLOCK *)(v28 + 120);
                        if ( *(_DWORD *)(v28 + 112) == 1 )
                        {
                          if ( SLODWORD(v29->Ptr) >= 0 )
                            ++LODWORD(v29->Ptr);
                        }
                        else
                        {
                          AcquireSRWLockShared(v29);
                        }
                        if ( (unsigned int)v27 < *(_DWORD *)(v28 + 80) )
                        {
                          WindowsDeleteString((HSTRING)Context[0]);
                          Context[0] = 0;
                          v19 = WindowsDuplicateString(
                                  *(HSTRING *)(*(_QWORD *)(v28 + 96) + 8 * v27),
                                  (HSTRING *)Context);
                        }
                        else
                        {
                          RoOriginateError(2147483659LL, 0);
                          v19 = -2147483637;
                        }
                        v30 = (RTL_SRWLOCK *)(v28 + 120);
                        if ( *(_DWORD *)(v28 + 112) == 1 )
                          --LODWORD(v30->Ptr);
                        else
                          ReleaseSRWLockShared(v30);
                        if ( v19 >= 0 )
                        {
                          v31 = WindowsGetStringRawBuffer((HSTRING)Context[0], 0);
                          v19 = IStream_WriteStr(v18, v31);
                        }
                        if ( Context[0] )
                          WindowsDeleteString((HSTRING)Context[0]);
                        v27 = (unsigned int)(v27 + 1);
                        if ( (unsigned int)v27 >= fPending )
                          goto LABEL_72;
                      }
                    }
                    else
                    {
LABEL_72:
                      if ( v19 >= 0 )
                      {
                        fPending = 0;
                        v32 = *((_QWORD *)this + 19);
                        if ( !v32
                          || (v19 = (*(__int64 (__fastcall **)(__int64, WINBOOL *))(*(_QWORD *)v32 + 56LL))(
                                      v32,
                                      &fPending),
                              v19 >= 0) )
                        {
                          v19 = IStream_Write(v18, &fPending, 4u);
                          v33 = 0;
                          if ( fPending )
                          {
                            while ( v19 >= 0 )
                            {
                              *(_OWORD *)Context = 0;
                              v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPVOID *))(**((_QWORD **)this + 19) + 48LL))(
                                      *((_QWORD *)this + 19),
                                      v33,
                                      Context);
                              if ( v19 >= 0 )
                              {
                                v34 = WindowsGetStringRawBuffer((HSTRING)Context[0], 0);
                                v19 = IStream_WriteStr(v18, v34);
                                if ( v19 >= 0 )
                                  v19 = IStream_Write(v18, &Context[1], 1u);
                              }
                              WindowsDeleteString((HSTRING)Context[0]);
                              if ( ++v33 >= fPending )
                                goto LABEL_81;
                            }
                          }
                          else
                          {
LABEL_81:
                            if ( v19 >= 0 )
                            {
                              v19 = IStream_Write(v18, (char *)this + 232, 4u);
                              if ( v19 >= 0 )
                              {
                                v19 = IStream_Write(v18, (char *)this + 236, 4u);
                                if ( v19 >= 0 )
                                {
                                  v19 = IStream_Write(v18, (char *)this + 240, 4u);
                                  if ( v19 >= 0 )
                                  {
                                    v19 = IStream_Write(v18, (char *)this + 244, 4u);
                                    if ( v19 >= 0 )
                                      v19 = IStream_Write(v18, (char *)this + 248, 4u);
                                  }
                                }
                              }
                              v35 = *((_QWORD *)this + 32);
                              v36 = v35 ? *(_DWORD *)(v35 + 16) : 0;
                              fPending = v36;
                              if ( v19 >= 0 )
                              {
                                v19 = IStream_Write(v18, &fPending, 4u);
                                if ( v19 >= 0 )
                                {
                                  if ( !fPending
                                    || (v19 = IStream_Write(
                                                v18,
                                                *(const void **)(*((_QWORD *)this + 32) + 8LL),
                                                20 * fPending),
                                        v19 >= 0) )
                                  {
                                    fPending = 0;
                                    v37 = *((_QWORD *)this + 21);
                                    if ( !v37
                                      || (v19 = (*(__int64 (__fastcall **)(__int64, WINBOOL *))(*(_QWORD *)v37 + 56LL))(
                                                  v37,
                                                  &fPending),
                                          v19 >= 0) )
                                    {
                                      v19 = IStream_Write(v18, &fPending, 4u);
                                      v38 = 0;
                                      if ( fPending )
                                      {
                                        while ( v19 >= 0 )
                                        {
                                          Context[0] = 0;
                                          v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPVOID *))(**((_QWORD **)this + 21) + 48LL))(
                                                  *((_QWORD *)this + 21),
                                                  v38,
                                                  Context);
                                          if ( v19 >= 0 )
                                          {
                                            v39 = WindowsGetStringRawBuffer((HSTRING)Context[0], 0);
                                            v19 = IStream_WriteStr(v18, v39);
                                          }
                                          if ( Context[0] )
                                            WindowsDeleteString((HSTRING)Context[0]);
                                          if ( ++v38 >= fPending )
                                            goto LABEL_103;
                                        }
                                      }
                                      else
                                      {
LABEL_103:
                                        if ( v19 >= 0 )
                                        {
                                          v19 = IStream_Reset(v18);
                                          if ( v19 >= 0 )
                                          {
                                            Context[0] = 0;
                                            v19 = IStream_Size(v18, (ULARGE_INTEGER *)Context);
                                            if ( v19 >= 0 )
                                            {
                                              if ( Context[0] > (LPVOID)0xFFFFFFFFLL )
                                              {
                                                v19 = -2147024362;
                                              }
                                              else
                                              {
                                                sourceString = 0;
                                                v41 = -1;
                                                hstringHeader.Reserved.Reserved1 = (PVOID)-1LL;
                                                *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = -1;
                                                v19 = BinaryToText(
                                                        v40,
                                                        v18,
                                                        Context[0],
                                                        &sourceString,
                                                        (char *)this + 192);
                                                v42 = (WCHAR *)sourceString;
                                                if ( v19 >= 0 )
                                                {
                                                  do
                                                    ++v41;
                                                  while ( sourceString[v41] );
                                                  if ( v41 > 0xFFFFFFFF )
                                                  {
                                                    LODWORD(v41) = -1;
                                                    RaiseException(0xC000000D, 1u, 0, 0);
                                                  }
                                                  WindowsCreateStringReference(
                                                    v42,
                                                    v41,
                                                    &hstringHeader,
                                                    (HSTRING *)&sourceString);
                                                  v19 = WindowsDuplicateString((HSTRING)sourceString, a2);
                                                }
                                                if ( v42 )
                                                  LocalFree(v42);
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_115:
  v43 = SharedConvertHResultToWinRTFileAPIError(v19, 0);
  if ( v18 )
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v18 + 16LL))(v18);
  if ( this != (CQueryOptions *)-192LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  return v43;
}

```

## disassembly

```asm
0x180314ac0  mov     [rsp-38h+arg_10], rbx
0x180314ac5  push    rbp
0x180314ac6  push    rsi
0x180314ac7  push    rdi
0x180314ac8  push    r12
0x180314aca  push    r13
0x180314acc  push    r14
0x180314ace  push    r15
0x180314ad0  mov     rbp, rsp
0x180314ad3  sub     rsp, 80h
0x180314ada  mov     rax, cs:__security_cookie
0x180314ae1  xor     rax, rsp
0x180314ae4  mov     [rbp+var_10], rax
0x180314ae8  mov     r13, rdx
0x180314aeb  mov     r15, rcx
0x180314aee  mov     eax, 1
0x180314af3  lock xadd cs:?__wil_apiCallCounter@?3??SaveToString@CQueryOptions@@UEAAJPEAPEAUHSTRING__@@@Z@4JC, eax; long volatile `CQueryOptions::SaveToString(HSTRING__ * *)'::`4'::__wil_apiCallCounter
0x180314afb  inc     eax
0x180314afd  xor     r12d, r12d
0x180314b00  cmp     eax, 1
0x180314b03  jnz     loc_180314E67
0x180314b09  mov     [rbp+Context], r12
0x180314b0d  mov     [rbp+fPending], r12d
0x180314b11  lea     r9, [rbp+Context]; lpContext
0x180314b15  lea     r8, [rbp+fPending]; fPending
0x180314b19  xor     edx, edx; dwFlags
0x180314b1b  lea     rcx, ?wrapper@?1??Instance@ApiTelemetryLogger@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VApiTelemetryLogger@details@wil@@@34@A; lpInitOnce
0x180314b22  call    cs:__imp_InitOnceBeginInitialize
0x180314b28  lea     rsi, qword_180804908
0x180314b2f  lea     r14, ??_7ApiTelemetryLogger@details@wil@@6B@; const wil::details::ApiTelemetryLogger::`vftable'
0x180314b36  lea     rbx, ?__hInner@?1???0StaticHandle@ApiTelemetryLogger@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::ApiTelemetryLogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180314b3d  test    eax, eax
0x180314b3f  jz      loc_180314C44
0x180314b45  cmp     [rbp+fPending], r12d
0x180314b49  jz      loc_180314C44
0x180314b4f  mov     [rbp+Context], rsi
0x180314b53  mov     cs:qword_180804910, r12
0x180314b5a  mov     cs:byte_180804918, r12b
0x180314b61  mov     cs:dword_18080491C, r12d
0x180314b68  mov     cs:qword_180804908, r14
0x180314b6f  mov     cs:qword_180804920, rbx
0x180314b76  xorps   xmm0, xmm0
0x180314b79  movdqu  cs:xmmword_180804928, xmm0
0x180314b81  mov     cs:qword_180804938, r12
0x180314b88  mov     cs:dword_180804940, r12d
0x180314b8f  mov     cs:dword_180804944, 124F80h
0x180314b99  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_6b26b9d13d28b4db0bc0125880e9ff13_@@CA@XZ; void (__cdecl *)()
0x180314ba0  call    atexit
0x180314ba5  mov     rbx, cs:qword_180804920
0x180314bac  mov     cs:qword_180804910, rbx
0x180314bb3  mov     cs:byte_180804918, 1
0x180314bba  mov     rax, [rbx+8]
0x180314bbe  movups  xmm0, xmmword ptr [rax-10h]
0x180314bc2  movups  [rbp+var_40], xmm0
0x180314bc6  cmp     [rbx+20h], r12
0x180314bca  jz      short loc_180314BD3
0x180314bcc  mov     ecx, 5
0x180314bd1  int     29h; Win8: RtlFailFast(ecx)
0x180314bd3  mov     [rbx+28h], r12
0x180314bd7  mov     [rbx+30h], r12
0x180314bdb  lea     r9, [rbx+20h]
0x180314bdf  mov     r8, rbx
0x180314be2  lea     rdx, _tlgEnableCallback
0x180314be9  lea     rcx, [rbp+var_40]
0x180314bed  call    cs:__imp_EtwEventRegister
0x180314bf3  test    eax, eax
0x180314bf5  jnz     short loc_180314C0E
0x180314bf7  mov     r8, [rbx+8]
0x180314bfb  movzx   r9d, word ptr [r8]
0x180314bff  mov     edx, 2
0x180314c04  mov     rcx, [rbx+20h]
0x180314c08  call    cs:__imp_EtwEventSetInformation
0x180314c0e  mov     cs:dword_18080491C, 1
0x180314c18  mov     rax, cs:qword_180804908
0x180314c1f  mov     rcx, rsi
0x180314c22  mov     rax, [rax+8]
0x180314c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180314c2b  mov     r8, rsi; lpContext
0x180314c2e  xor     edx, edx; dwFlags
0x180314c30  lea     rcx, ?wrapper@?1??Instance@ApiTelemetryLogger@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VApiTelemetryLogger@details@wil@@@34@A; lpInitOnce
0x180314c37  call    cs:__imp_InitOnceComplete
0x180314c3d  lea     rbx, ?__hInner@?1???0StaticHandle@ApiTelemetryLogger@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::ApiTelemetryLogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180314c44  mov     rax, [rbp+Context]
0x180314c48  mov     rax, [rax+8]
0x180314c4c  test    rax, rax
0x180314c4f  jz      loc_180314E67
0x180314c55  mov     eax, [rax]
0x180314c57  test    eax, eax
0x180314c59  jz      loc_180314E67
0x180314c5f  mov     [rbp+Context], r12
0x180314c63  mov     [rbp+fPending], r12d
0x180314c67  lea     r9, [rbp+Context]; lpContext
0x180314c6b  lea     r8, [rbp+fPending]; fPending
0x180314c6f  xor     edx, edx; dwFlags
0x180314c71  lea     rcx, ?wrapper@?1??Instance@ApiTelemetryLogger@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VApiTelemetryLogger@details@wil@@@34@A; lpInitOnce
0x180314c78  call    cs:__imp_InitOnceBeginInitialize
0x180314c7e  test    eax, eax
0x180314c80  jz      loc_180314D7E
0x180314c86  cmp     [rbp+fPending], r12d
0x180314c8a  jz      loc_180314D7E
0x180314c90  mov     [rbp+Context], rsi
0x180314c94  mov     cs:qword_180804910, r12
0x180314c9b  mov     cs:byte_180804918, r12b
0x180314ca2  mov     cs:dword_18080491C, r12d
0x180314ca9  mov     cs:qword_180804908, r14
0x180314cb0  mov     cs:qword_180804920, rbx
0x180314cb7  xorps   xmm0, xmm0
0x180314cba  movdqu  cs:xmmword_180804928, xmm0
0x180314cc2  mov     cs:qword_180804938, r12
0x180314cc9  mov     cs:dword_180804940, r12d
0x180314cd0  mov     cs:dword_180804944, 124F80h
0x180314cda  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_6b26b9d13d28b4db0bc0125880e9ff13_@@CA@XZ; void (__cdecl *)()
0x180314ce1  call    atexit
0x180314ce6  mov     rbx, cs:qword_180804920
0x180314ced  mov     cs:qword_180804910, rbx
0x180314cf4  mov     cs:byte_180804918, 1
0x180314cfb  mov     rax, [rbx+8]
0x180314cff  movups  xmm0, xmmword ptr [rax-10h]
0x180314d03  movups  [rbp+var_40], xmm0
0x180314d07  cmp     [rbx+20h], r12
0x180314d0b  jz      short loc_180314D14
0x180314d0d  mov     ecx, 5
0x180314d12  int     29h; Win8: RtlFailFast(ecx)
0x180314d14  mov     [rbx+28h], r12
0x180314d18  mov     [rbx+30h], r12
0x180314d1c  lea     r9, [rbx+20h]
0x180314d20  mov     r8, rbx
0x180314d23  lea     rdx, _tlgEnableCallback
0x180314d2a  lea     rcx, [rbp+var_40]
0x180314d2e  call    cs:__imp_EtwEventRegister
0x180314d34  test    eax, eax
0x180314d36  jnz     short loc_180314D4F
0x180314d38  mov     r8, [rbx+8]
0x180314d3c  movzx   r9d, word ptr [r8]
0x180314d40  mov     edx, 2
0x180314d45  mov     rcx, [rbx+20h]
0x180314d49  call    cs:__imp_EtwEventSetInformation
0x180314d4f  mov     cs:dword_18080491C, 1
0x180314d59  mov     rax, cs:qword_180804908
0x180314d60  mov     rcx, rsi
0x180314d63  mov     rax, [rax+8]
0x180314d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180314d6c  mov     r8, rsi; lpContext
0x180314d6f  xor     edx, edx; dwFlags
0x180314d71  lea     rcx, ?wrapper@?1??Instance@ApiTelemetryLogger@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VApiTelemetryLogger@details@wil@@@34@A; lpInitOnce
0x180314d78  call    cs:__imp_InitOnceComplete
0x180314d7e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180314d85  mov     ecx, 28h ; '('; unsigned __int64
0x180314d8a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180314d8f  mov     rbx, rax
0x180314d92  test    rax, rax
0x180314d95  jz      loc_180314E67
0x180314d9b  lea     rsi, ?RuntimeClass_Windows_Storage_Search_QueryOptions@@3QBGB; "Windows.Storage.Search.QueryOptions"
0x180314da2  mov     [rax], rsi
0x180314da5  lea     rax, aSavetostring; "SaveToString"
0x180314dac  mov     [rbx+8], rax
0x180314db0  mov     [rbx+10h], r12
0x180314db4  lea     rax, ?__wil_apiCallCounter@?3??SaveToString@CQueryOptions@@UEAAJPEAPEAUHSTRING__@@@Z@4JC; long volatile `CQueryOptions::SaveToString(HSTRING__ * *)'::`4'::__wil_apiCallCounter
0x180314dbb  mov     [rbx+18h], rax
0x180314dbf  mov     [rbx+20h], r12
0x180314dc3  mov     rdi, [rbp+Context]
0x180314dc7  add     rdi, 20h ; ' '
0x180314dcb  lea     r14, [rdi+8]
0x180314dcf  mov     rcx, r14; SRWLock
0x180314dd2  call    cs:__imp_AcquireSRWLockExclusive
0x180314dd8  mov     r9, [rdi]
0x180314ddb  test    r9, r9
0x180314dde  jz      short loc_180314E0E
0x180314de0  mov     rax, rsi
0x180314de3  mov     r8, [r9]
0x180314de6  sub     r8, rsi
0x180314de9  nop     dword ptr [rax+00000000h]
0x180314df0  movzx   edx, word ptr [rax]
0x180314df3  movzx   ecx, word ptr [rax+r8]
0x180314df8  sub     edx, ecx
0x180314dfa  jnz     short loc_180314E04
0x180314dfc  add     rax, 2
0x180314e00  test    ecx, ecx
0x180314e02  jnz     short loc_180314DF0
0x180314e04  test    edx, edx
0x180314e06  jle     short loc_180314E0E
0x180314e08  lea     rdi, [r9+20h]
0x180314e0c  jmp     short loc_180314DD8
0x180314e0e  mov     [rdi], r12
0x180314e11  mov     rsi, [rbx+20h]
0x180314e15  mov     [rbx+20h], r9
0x180314e19  test    rsi, rsi
0x180314e1c  jz      short loc_180314E36
0x180314e1e  lea     rcx, [rsi+20h]
0x180314e22  xor     edx, edx
0x180314e24  call    ?reset@?$unique_ptr@UApiData@ApiDataList@ApiTelemetryLogger@details@wil@@U?$default_delete@UApiData@ApiDataList@ApiTelemetryLogger@details@wil@@@wistd@@@wistd@@QEAAXPEAUApiData@ApiDataList@ApiTelemetryLogger@details@wil@@@Z; wistd::unique_ptr<wil::details::ApiTelemetryLogger::ApiDataList::ApiData,wistd::default_delete<wil::details::ApiTelemetryLogger::ApiDataList::ApiData>>::reset(wil::details::ApiTelemetryLogger::ApiDataList::ApiData *)
0x180314e29  mov     edx, 28h ; '('; struct std::nothrow_t *
0x180314e2e  mov     rcx, rsi; void *
0x180314e31  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180314e36  mov     rsi, [rdi]
0x180314e39  mov     [rdi], rbx
0x180314e3c  test    rsi, rsi
0x180314e3f  jz      short loc_180314E59
0x180314e41  lea     rcx, [rsi+20h]
0x180314e45  xor     edx, edx
0x180314e47  call    ?reset@?$unique_ptr@UApiData@ApiDataList@ApiTelemetryLogger@details@wil@@U?$default_delete@UApiData@ApiDataList@ApiTelemetryLogger@details@wil@@@wistd@@@wistd@@QEAAXPEAUApiData@ApiDataList@ApiTelemetryLogger@details@wil@@@Z; wistd::unique_ptr<wil::details::ApiTelemetryLogger::ApiDataList::ApiData,wistd::default_delete<wil::details::ApiTelemetryLogger::ApiDataList::ApiData>>::reset(wil::details::ApiTelemetryLogger::ApiDataList::ApiData *)
0x180314e4c  mov     edx, 28h ; '('; struct std::nothrow_t *
0x180314e51  mov     rcx, rsi; void *
0x180314e54  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180314e59  test    r14, r14
0x180314e5c  jz      short loc_180314E67
0x180314e5e  mov     rcx, r14; SRWLock
0x180314e61  call    cs:__imp_ReleaseSRWLockExclusive
0x180314e67  mov     [r13+0], r12
0x180314e6b  lea     r12, [r15+0C0h]
0x180314e72  mov     rcx, r12; lpCriticalSection
0x180314e75  call    cs:__imp_EnterCriticalSection
0x180314e7b  mov     [rbp+var_60], r12
0x180314e7f  xor     edx, edx; cbInit
0x180314e81  xor     ecx, ecx; pInit
0x180314e83  call    cs:__imp_SHCreateMemStream
0x180314e89  mov     rdi, rax
0x180314e8c  mov     qword ptr [rbp+var_40], rax
0x180314e90  test    rax, rax
0x180314e93  jnz     short loc_180314E9F
0x180314e95  mov     ebx, 8007000Eh
0x180314e9a  jmp     loc_180315480
0x180314e9f  mov     [rbp+fPending], 4
0x180314ea6  mov     r8d, 4; cb
0x180314eac  lea     rdx, [rbp+fPending]; pv
0x180314eb0  mov     rcx, rdi; pstm
0x180314eb3  call    cs:__imp_IStream_Write
0x180314eb9  mov     ebx, eax
0x180314ebb  test    eax, eax
0x180314ebd  js      loc_180315480
0x180314ec3  lea     rdx, [r15+60h]; pv
0x180314ec7  mov     r8d, 4; cb
0x180314ecd  mov     rcx, rdi; pstm
0x180314ed0  call    cs:__imp_IStream_Write
0x180314ed6  mov     ebx, eax
0x180314ed8  test    eax, eax
0x180314eda  js      loc_180315480
0x180314ee0  lea     rdx, [r15+80h]; pv
0x180314ee7  mov     r8d, 4; cb
0x180314eed  mov     rcx, rdi; pstm
0x180314ef0  call    cs:__imp_IStream_Write
0x180314ef6  mov     ebx, eax
0x180314ef8  test    eax, eax
0x180314efa  js      loc_180315480
0x180314f00  lea     rdx, [r15+90h]; pv
0x180314f07  mov     r8d, 4; cb
0x180314f0d  mov     rcx, rdi; pstm
0x180314f10  call    cs:__imp_IStream_Write
0x180314f16  mov     ebx, eax
0x180314f18  test    eax, eax
0x180314f1a  js      loc_180315480
0x180314f20  lea     rdx, [r15+0B0h]; pv
0x180314f27  mov     r8d, 10h; cb
0x180314f2d  mov     rcx, rdi; pstm
0x180314f30  call    cs:__imp_IStream_Write
0x180314f36  mov     ebx, eax
0x180314f38  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59687846@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59687846@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59687846> `wil::Feature<__WilFeatureTraits_Feature_59687846>::GetImpl(void)'::`2'::impl
0x180314f3f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59687846@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59687846>::__private_IsEnabled(void)
0x180314f44  test    al, al
0x180314f46  jz      short loc_180314F88
0x180314f48  test    ebx, ebx
0x180314f4a  js      loc_180315480
0x180314f50  lea     rdx, [r15+94h]; pv
0x180314f57  mov     r8d, 1; cb
0x180314f5d  mov     rcx, rdi; pstm
0x180314f60  call    cs:__imp_IStream_Write
0x180314f66  mov     ebx, eax
0x180314f68  test    eax, eax
0x180314f6a  js      loc_180315480
0x180314f70  lea     rdx, [r15+95h]; pv
0x180314f77  mov     r8d, 1; cb
0x180314f7d  mov     rcx, rdi; pstm
0x180314f80  call    cs:__imp_IStream_Write
0x180314f86  mov     ebx, eax
0x180314f88  test    ebx, ebx
0x180314f8a  js      loc_180315480
0x180314f90  xor     edx, edx; length
0x180314f92  mov     rcx, [r15+68h]; string
0x180314f96  call    cs:__imp_WindowsGetStringRawBuffer
0x180314f9c  mov     rdx, rax; psz
0x180314f9f  mov     rcx, rdi; pstm
0x180314fa2  call    cs:__imp_IStream_WriteStr
0x180314fa8  mov     ebx, eax
0x180314faa  test    eax, eax
0x180314fac  js      loc_180315480
0x180314fb2  xor     edx, edx; length
0x180314fb4  mov     rcx, [r15+70h]; string
0x180314fb8  call    cs:__imp_WindowsGetStringRawBuffer
0x180314fbe  mov     rdx, rax; psz
0x180314fc1  mov     rcx, rdi; pstm
0x180314fc4  call    cs:__imp_IStream_WriteStr
0x180314fca  mov     ebx, eax
0x180314fcc  test    eax, eax
0x180314fce  js      loc_180315480
0x180314fd4  xor     edx, edx; length
0x180314fd6  mov     rcx, [r15+78h]; string
0x180314fda  call    cs:__imp_WindowsGetStringRawBuffer
0x180314fe0  mov     rdx, rax; psz
0x180314fe3  mov     rcx, rdi; pstm
0x180314fe6  call    cs:__imp_IStream_WriteStr
  ... truncated ...
```
