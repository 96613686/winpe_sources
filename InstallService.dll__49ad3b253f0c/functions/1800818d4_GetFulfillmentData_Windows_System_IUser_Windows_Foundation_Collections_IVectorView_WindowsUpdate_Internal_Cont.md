# GetFulfillmentData(Windows::System::IUser *,Windows::Foundation::Collections::IVectorView<WindowsUpdate::Internal::ContentIdInfo *> *,HSTRING__ *,TraceLoggingCorrelationVector *,Windows::Foundation::Collections::IVectorView<WindowsUpdate::Internal::IFulfillmentDataInfo *> * *)

- ea: `0x1800818d4`
- end: `0x180081df6`
- name: `?GetFulfillmentData@@YAJPEAUIUser@System@Windows@@PEAU?$IVectorView@PEAVContentIdInfo@Internal@WindowsUpdate@@@Collections@Foundation@3@PEAUHSTRING__@@PEAVTraceLoggingCorrelationVector@@PEAPEAU?$IVectorView@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@563@@Z`
- size: `1314`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `21`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800cbedc`
- `0x1800cc51c`

## callees

- `0x180009ea0`
- `0x18000e44c`
- `0x1800101f4`
- `0x18001c414`
- `0x18001c844`
- `0x18001ddb0`
- `0x18001f0ac`
- `0x18003f884`
- `0x18006888c`
- `0x18007fb50`
- `0x180080360`
- `0x1800818d4`
- `0x180082b74`
- `0x180083e70`
- `0x180084c74`
- `0x1800d9c20`
- `0x1800d9d1c`
- `0x1800daa98`
- `0x180145a00`
- `0x180146a04`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081a34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081a6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081a9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081acb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081b96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081c01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081c29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081cff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081d0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081d1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081a34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081a6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081a9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081acb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081b96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081c01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081c29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081cff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081d0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081d1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081aab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081ada`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081b12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081b34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081b43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081c0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081aab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081ada`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081b12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081b34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081b43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081c0c`

## string_xrefs

- `0x180081968`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x180081b80`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x180081b5f`: `ContentId: %s, cached FulfillmentData: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall GetFulfillmentData(
        __int64 a1,
        __int64 a2,
        HSTRING a3,
        TraceLoggingCorrelationVector *a4,
        _QWORD *a5)
{
  _QWORD *v7; // r12
  const char *v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  int CachedFulfillmentData; // esi
  int v12; // r8d
  unsigned int v13; // r15d
  HSTRING v14; // r12
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  int v21; // eax
  HSTRING v22; // rdi
  const WCHAR *v23; // rax
  HSTRING v24; // rbx
  const unsigned __int16 *v25; // rax
  PCWSTR v26; // rsi
  PCWSTR v27; // rax
  const WCHAR *v28; // rax
  void *v29; // rax
  __int64 v30; // r8
  __int64 v31; // rax
  int v32; // ebx
  unsigned int v33; // edx
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, __int64 *); // rbx
  __int64 v36; // rax
  int v38; // [rsp+28h] [rbp-D8h]
  __int64 v39; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v40; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v41; // [rsp+60h] [rbp-A0h] BYREF
  struct WindowsUpdate::Internal::IFulfillmentDataInfo *v42; // [rsp+68h] [rbp-98h] BYREF
  HSTRING string; // [rsp+70h] [rbp-90h] BYREF
  __int64 v44; // [rsp+78h] [rbp-88h] BYREF
  HSTRING v45; // [rsp+80h] [rbp-80h] BYREF
  signed __int32 v46; // [rsp+88h] [rbp-78h] BYREF
  __int64 v47; // [rsp+90h] [rbp-70h]
  HSTRING v48; // [rsp+98h] [rbp-68h] BYREF
  HSTRING v49; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v50; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v51; // [rsp+B0h] [rbp-50h] BYREF
  int v52; // [rsp+B8h] [rbp-48h]
  __int64 v53; // [rsp+C0h] [rbp-40h]
  _QWORD *v54; // [rsp+C8h] [rbp-38h]
  _QWORD v55[2]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v56; // [rsp+E0h] [rbp-20h]
  signed __int32 *v57; // [rsp+E8h] [rbp-18h]
  HSTRING v58; // [rsp+F0h] [rbp-10h]
  _QWORD v59[3]; // [rsp+F8h] [rbp-8h] BYREF
  char v60[144]; // [rsp+110h] [rbp+10h] BYREF

  v48 = a3;
  v53 = a1;
  v7 = a5;
  v54 = a5;
  *a5 = 0;
  TraceLoggingCorrelationVector::Increment(a4, v60);
  WindowsUpdate::CommonTelemetry::BeginUpdateMetadataPrepare((WindowsUpdate::CommonTelemetry *)v60, v8);
  v44 = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v44);
  v10 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsUpdate::Internal::IFulfillmentDataInfo,Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>(
          v9,
          &v44);
  CachedFulfillmentData = TraceHR(
                            "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
                            0x1C8u,
                            "GetFulfillmentData",
                            "(AgileVector<IFulfillmentDataInfo *>::Make(&fulfillmentData))",
                            v10,
                            v38);
  if ( CachedFulfillmentData >= 0 )
  {
    v50 = a2;
    if ( a2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    v46 = 0;
    v47 = 0;
    CachedFulfillmentData = RefCountedEvent::Initialize((RefCountedEvent *)&v46);
    if ( CachedFulfillmentData >= 0 )
    {
      _InterlockedIncrement(&v46);
      v39 = 0;
      v40 = 0;
      CachedFulfillmentData = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 56LL))(a2, &v40);
      v13 = 0;
      if ( v40 )
      {
        v14 = v48;
        do
        {
          if ( CachedFulfillmentData < 0 )
            break;
          v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a2 + 48LL);
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v39);
          CachedFulfillmentData = v15(a2, v13, &v39);
          if ( CachedFulfillmentData >= 0 )
          {
            v45 = 0;
            string = 0;
            v16 = v39;
            v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 48LL);
            WindowsDeleteString(0);
            v45 = 0;
            CachedFulfillmentData = v17(v16, &v45);
            if ( CachedFulfillmentData >= 0 )
            {
              v18 = v39;
              v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 56LL);
              WindowsDeleteString(string);
              string = 0;
              CachedFulfillmentData = v19(v18, &string);
              if ( CachedFulfillmentData >= 0 )
              {
                WindowsDeleteString(0);
                v49 = 0;
                StringRawBuffer = WindowsGetStringRawBuffer(v45, 0);
                v21 = ConstructFulfillmentDataCacheKey(StringRawBuffer, &v49);
                v22 = v49;
                if ( v21 < 0 )
                  goto LABEL_22;
                WindowsDeleteString(0);
                v48 = 0;
                v23 = WindowsGetStringRawBuffer(v22, 0);
                CachedFulfillmentData = GetCachedFulfillmentData(v23, &v48);
                v24 = v48;
                if ( CachedFulfillmentData >= 0 )
                {
                  v42 = 0;
                  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v42);
                  v25 = WindowsGetStringRawBuffer(v24, 0);
                  CachedFulfillmentData = WindowsUpdate::Internal::FulfillmentDataInfo::CreateFromFulfillmentData(
                                            v25,
                                            &v42);
                  if ( CachedFulfillmentData < 0 )
                  {
                    v28 = WindowsGetStringRawBuffer(v22, 0);
                    DeleteCachedFulfillmentData(v28);
                  }
                  else
                  {
                    v26 = WindowsGetStringRawBuffer(v24, 0);
                    v27 = WindowsGetStringRawBuffer(v45, 0);
                    LogMessage(
                      3u,
                      "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
                      0x1F2u,
                      "GetFulfillmentData",
                      -1,
                      L"ContentId: %s, cached FulfillmentData: %s",
                      0,
                      0,
                      v27,
                      v26);
                    v41 = 0;
                    WindowsDeleteString(0);
                    v41 = 0;
                    CachedFulfillmentData = (*(__int64 (__fastcall **)(struct WindowsUpdate::Internal::IFulfillmentDataInfo *, HSTRING *))(*(_QWORD *)v42 + 168LL))(
                                              v42,
                                              &v41);
                    if ( CachedFulfillmentData >= 0 )
                    {
                      if ( !string
                        || (CachedFulfillmentData = (*(__int64 (__fastcall **)(struct WindowsUpdate::Internal::IFulfillmentDataInfo *))(*(_QWORD *)v42 + 208LL))(v42),
                            CachedFulfillmentData >= 0) )
                      {
                        CachedFulfillmentData = (*(__int64 (__fastcall **)(__int64, struct WindowsUpdate::Internal::IFulfillmentDataInfo *))(*(_QWORD *)v44 + 104LL))(
                                                  v44,
                                                  v42);
                      }
                    }
                    WindowsDeleteString(v41);
                  }
                  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v42);
                }
                WindowsDeleteString(v24);
                if ( CachedFulfillmentData < 0 )
                {
LABEL_22:
                  CachedFulfillmentData = 0;
                  _InterlockedIncrement(&v46);
                  v41 = 0;
                  v55[0] = &v50;
                  v55[1] = v53;
                  v56 = v13;
                  v57 = &v46;
                  v58 = v14;
                  v59[0] = v44;
                  if ( v44 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 8LL))(v44);
                  v59[1] = a4;
                  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v41);
                  v51 = 2;
                  v52 = 0;
                  v29 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
                  v59[2] = v29;
                  if ( v29 )
                    v31 = Windows::Internal::COperationLambdaVar_0__lambda_6ae8a561a9abe19f78ed883c7fb16267__Windows::Internal::CNoResult_::COperationLambdaVar_0__lambda_6ae8a561a9abe19f78ed883c7fb16267__Windows::Internal::CNoResult___lambda_6ae8a561a9abe19f78ed883c7fb16267___(
                            v29,
                            v55);
                  else
                    v31 = 0;
                  v32 = Windows::Internal::MakeAsyncActionHelper<Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::DisableCausality>(
                          &v51,
                          &v41,
                          v30,
                          v31);
                  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v59);
                  if ( v32 < 0 )
                    RefCountedEvent::Release((RefCountedEvent *)&v46);
                  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v41);
                }
                WindowsDeleteString(v22);
              }
            }
            WindowsDeleteString(string);
            string = 0;
            WindowsDeleteString(v45);
          }
          ++v13;
        }
        while ( v13 < v40 );
        v7 = v54;
      }
      RefCountedEvent::Release((RefCountedEvent *)&v46);
      RefCountedEvent::Wait((RefCountedEvent *)&v46, v33);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v39);
    }
    RefCountedEvent::~RefCountedEvent((RefCountedEvent *)&v46);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v50);
    if ( CachedFulfillmentData >= 0 )
    {
      v39 = 0;
      v34 = v44;
      v35 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 64LL);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v39);
      CachedFulfillmentData = v35(v34, &v39);
      if ( CachedFulfillmentData >= 0 )
      {
        v36 = v39;
        v39 = 0;
        *v7 = v36;
      }
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v39);
    }
  }
  WindowsUpdate::CommonTelemetry::EndUpdateMetadataPrepare(
    (WindowsUpdate::CommonTelemetry *)v60,
    (const char *)(unsigned int)CachedFulfillmentData,
    v12);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v44);
  return (unsigned int)CachedFulfillmentData;
}

```

## disassembly

```asm
0x1800818d4  mov     [rsp-8+arg_0], rbx
0x1800818d9  push    rbp
0x1800818da  push    rsi
0x1800818db  push    rdi
0x1800818dc  push    r12
0x1800818de  push    r13
0x1800818e0  push    r14
0x1800818e2  push    r15
0x1800818e4  lea     rbp, [rsp-0B0h]
0x1800818ec  sub     rsp, 1B0h
0x1800818f3  mov     rax, cs:__security_cookie
0x1800818fa  xor     rax, rsp
0x1800818fd  mov     [rbp+0E0h+var_40], rax
0x180081904  mov     r13, r9
0x180081907  mov     [rbp+0E0h+var_148], r8
0x18008190b  mov     r14, rdx
0x18008190e  mov     [rbp+0E0h+var_120], rcx
0x180081912  mov     r12, [rbp+0E0h+arg_20]
0x180081919  mov     [rbp+0E0h+var_118], r12
0x18008191d  xor     ebx, ebx
0x18008191f  mov     [r12], rbx
0x180081923  lea     rdx, [rbp+0E0h+var_D0]; char *
0x180081927  mov     rcx, r9; this
0x18008192a  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x18008192f  lea     rcx, [rbp+0E0h+var_D0]; this
0x180081933  call    ?BeginUpdateMetadataPrepare@CommonTelemetry@WindowsUpdate@@YAXPEBD@Z; WindowsUpdate::CommonTelemetry::BeginUpdateMetadataPrepare(char const *)
0x180081938  mov     [rsp+1E0h+var_168], rbx
0x18008193d  lea     rcx, [rsp+1E0h+var_168]
0x180081942  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180081947  lea     rdx, [rsp+1E0h+var_168]
0x18008194c  call    ??$CreateExternalObjectVector@UIFulfillmentDataInfo@Internal@WindowsUpdate@@V?$AgileVector@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2567@$0A@@2Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2567@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsUpdate::Internal::IFulfillmentDataInfo,Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0> * *)
0x180081951  mov     [rsp+1E0h+var_1C0], eax; int
0x180081955  lea     r9, aAgilevectorIfu; "(AgileVector<IFulfillmentDataInfo *>::M"...
0x18008195c  lea     r8, aGetfulfillment_0; "GetFulfillmentData"
0x180081963  mov     edx, 1C8h; unsigned int
0x180081968  lea     rcx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x18008196f  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180081974  mov     esi, eax
0x180081976  test    eax, eax
0x180081978  js      loc_180081DB4
0x18008197e  mov     [rbp+0E0h+var_138], r14
0x180081982  test    r14, r14
0x180081985  jz      short loc_180081997
0x180081987  mov     rax, [r14]
0x18008198a  mov     rcx, r14
0x18008198d  mov     rax, [rax+8]
0x180081991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081996  nop
0x180081997  mov     [rbp+0E0h+var_158], ebx
0x18008199a  mov     [rbp+0E0h+var_150], rbx
0x18008199e  lea     rcx, [rbp+0E0h+var_158]; this
0x1800819a2  call    ?Initialize@RefCountedEvent@@QEAAJXZ; RefCountedEvent::Initialize(void)
0x1800819a7  mov     esi, eax
0x1800819a9  test    eax, eax
0x1800819ab  js      loc_180081D50
0x1800819b1  lock inc [rbp+0E0h+var_158]
0x1800819b5  mov     [rsp+1E0h+var_190], rbx
0x1800819ba  mov     [rsp+1E0h+var_188], ebx
0x1800819be  mov     rax, [r14]
0x1800819c1  lea     rdx, [rsp+1E0h+var_188]
0x1800819c6  mov     rcx, r14
0x1800819c9  mov     rax, [rax+38h]
0x1800819cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800819d2  mov     esi, eax
0x1800819d4  mov     r15d, ebx
0x1800819d7  cmp     [rsp+1E0h+var_188], ebx
0x1800819db  jbe     loc_180081D32
0x1800819e1  mov     r12, [rbp+0E0h+var_148]
0x1800819e5  test    esi, esi
0x1800819e7  js      loc_180081D2E
0x1800819ed  mov     rax, [r14]
0x1800819f0  mov     rbx, [rax+30h]
0x1800819f4  lea     rcx, [rsp+1E0h+var_190]
0x1800819f9  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800819fe  lea     r8, [rsp+1E0h+var_190]
0x180081a03  mov     edx, r15d
0x180081a06  mov     rcx, r14
0x180081a09  mov     rax, rbx
0x180081a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081a11  mov     esi, eax
0x180081a13  xor     ebx, ebx
0x180081a15  test    eax, eax
0x180081a17  js      loc_180081D20
0x180081a1d  mov     [rbp+0E0h+var_160], rbx
0x180081a21  mov     [rsp+1E0h+string], rbx
0x180081a26  mov     rdi, [rsp+1E0h+var_190]
0x180081a2b  mov     rax, [rdi]
0x180081a2e  mov     rbx, [rax+30h]
0x180081a32  xor     ecx, ecx; string
0x180081a34  call    cs:__imp_WindowsDeleteString
0x180081a3a  mov     [rbp+0E0h+var_160], 0
0x180081a42  lea     rdx, [rbp+0E0h+var_160]
0x180081a46  mov     rcx, rdi
0x180081a49  mov     rax, rbx
0x180081a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081a51  mov     esi, eax
0x180081a53  xor     ebx, ebx
0x180081a55  test    eax, eax
0x180081a57  js      loc_180081D06
0x180081a5d  mov     rdi, [rsp+1E0h+var_190]
0x180081a62  mov     rax, [rdi]
0x180081a65  mov     rbx, [rax+38h]
0x180081a69  mov     rcx, [rsp+1E0h+string]; string
0x180081a6e  call    cs:__imp_WindowsDeleteString
0x180081a74  mov     [rsp+1E0h+string], 0
0x180081a7d  lea     rdx, [rsp+1E0h+string]
0x180081a82  mov     rcx, rdi
0x180081a85  mov     rax, rbx
0x180081a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081a8d  mov     esi, eax
0x180081a8f  xor     ebx, ebx
0x180081a91  test    eax, eax
0x180081a93  js      loc_180081D06
0x180081a99  xor     ecx, ecx; string
0x180081a9b  call    cs:__imp_WindowsDeleteString
0x180081aa1  mov     [rbp+0E0h+var_140], rbx
0x180081aa5  xor     edx, edx; length
0x180081aa7  mov     rcx, [rbp+0E0h+var_160]; string
0x180081aab  call    cs:__imp_WindowsGetStringRawBuffer
0x180081ab1  lea     rdx, [rbp+0E0h+var_140]; HSTRING *
0x180081ab5  mov     rcx, rax; unsigned __int16 *
0x180081ab8  call    ?ConstructFulfillmentDataCacheKey@@YAJPEBGPEAPEAUHSTRING__@@@Z; ConstructFulfillmentDataCacheKey(ushort const *,HSTRING__ * *)
0x180081abd  mov     rdi, [rbp+0E0h+var_140]
0x180081ac1  test    eax, eax
0x180081ac3  js      loc_180081C39
0x180081ac9  xor     ecx, ecx; string
0x180081acb  call    cs:__imp_WindowsDeleteString
0x180081ad1  mov     [rbp+0E0h+var_148], rbx
0x180081ad5  xor     edx, edx; length
0x180081ad7  mov     rcx, rdi; string
0x180081ada  call    cs:__imp_WindowsGetStringRawBuffer
0x180081ae0  lea     rdx, [rbp+0E0h+var_148]; HSTRING *
0x180081ae4  mov     rcx, rax; lpValue
0x180081ae7  call    ?GetCachedFulfillmentData@@YAJPEBGPEAPEAUHSTRING__@@@Z; GetCachedFulfillmentData(ushort const *,HSTRING__ * *)
0x180081aec  mov     esi, eax
0x180081aee  mov     rbx, [rbp+0E0h+var_148]
0x180081af2  test    eax, eax
0x180081af4  js      loc_180081C26
0x180081afa  mov     [rsp+1E0h+var_178], 0
0x180081b03  lea     rcx, [rsp+1E0h+var_178]
0x180081b08  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180081b0d  xor     edx, edx; length
0x180081b0f  mov     rcx, rbx; string
0x180081b12  call    cs:__imp_WindowsGetStringRawBuffer
0x180081b18  lea     rdx, [rsp+1E0h+var_178]; struct WindowsUpdate::Internal::IFulfillmentDataInfo **
0x180081b1d  mov     rcx, rax; unsigned __int16 *
0x180081b20  call    ?CreateFromFulfillmentData@FulfillmentDataInfo@Internal@WindowsUpdate@@SAJPEBGPEAPEAUIFulfillmentDataInfo@23@@Z; WindowsUpdate::Internal::FulfillmentDataInfo::CreateFromFulfillmentData(ushort const *,WindowsUpdate::Internal::IFulfillmentDataInfo * *)
0x180081b25  mov     esi, eax
0x180081b27  xor     edx, edx; length
0x180081b29  test    eax, eax
0x180081b2b  js      loc_180081C09
0x180081b31  mov     rcx, rbx; string
0x180081b34  call    cs:__imp_WindowsGetStringRawBuffer
0x180081b3a  mov     rsi, rax
0x180081b3d  xor     edx, edx; length
0x180081b3f  mov     rcx, [rbp+0E0h+var_160]; string
0x180081b43  call    cs:__imp_WindowsGetStringRawBuffer
0x180081b49  mov     [rsp+1E0h+var_198], rsi
0x180081b4e  mov     [rsp+1E0h+var_1A0], rax
0x180081b53  xor     esi, esi
0x180081b55  mov     [rsp+1E0h+var_1A8], rsi; unsigned __int16 *
0x180081b5a  mov     [rsp+1E0h+var_1B0], rsi; char *
0x180081b5f  lea     rax, aContentidSCach; "ContentId: %s, cached FulfillmentData: "...
0x180081b66  mov     [rsp+1E0h+var_1B8], rax; unsigned __int16 *
0x180081b6b  mov     [rsp+1E0h+var_1C0], 0FFFFFFFFh; int
0x180081b73  lea     r9, aGetfulfillment_0; "GetFulfillmentData"
0x180081b7a  mov     r8d, 1F2h; unsigned int
0x180081b80  lea     rdx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x180081b87  lea     ecx, [rsi+3]; unsigned int
0x180081b8a  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180081b8f  mov     [rsp+1E0h+var_180], rsi
0x180081b94  xor     ecx, ecx; string
0x180081b96  call    cs:__imp_WindowsDeleteString
0x180081b9c  mov     [rsp+1E0h+var_180], rsi
0x180081ba1  mov     rcx, [rsp+1E0h+var_178]
0x180081ba6  mov     rax, [rcx]
0x180081ba9  lea     rdx, [rsp+1E0h+var_180]
0x180081bae  mov     rax, [rax+0A8h]
0x180081bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081bba  mov     esi, eax
0x180081bbc  test    eax, eax
0x180081bbe  js      short loc_180081BFC
0x180081bc0  mov     rdx, [rsp+1E0h+string]
0x180081bc5  test    rdx, rdx
0x180081bc8  jz      short loc_180081BE4
0x180081bca  mov     rcx, [rsp+1E0h+var_178]
0x180081bcf  mov     rax, [rcx]
0x180081bd2  mov     rax, [rax+0D0h]
0x180081bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081bde  mov     esi, eax
0x180081be0  test    eax, eax
0x180081be2  js      short loc_180081BFC
0x180081be4  mov     rcx, [rsp+1E0h+var_168]
0x180081be9  mov     rax, [rcx]
0x180081bec  mov     rdx, [rsp+1E0h+var_178]
0x180081bf1  mov     rax, [rax+68h]
0x180081bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081bfa  mov     esi, eax
0x180081bfc  mov     rcx, [rsp+1E0h+var_180]; string
0x180081c01  call    cs:__imp_WindowsDeleteString
0x180081c07  jmp     short loc_180081C1B
0x180081c09  mov     rcx, rdi; string
0x180081c0c  call    cs:__imp_WindowsGetStringRawBuffer
0x180081c12  mov     rcx, rax; lpValueName
0x180081c15  call    ?DeleteCachedFulfillmentData@@YAJPEBG@Z; DeleteCachedFulfillmentData(ushort const *)
0x180081c1a  nop
0x180081c1b  lea     rcx, [rsp+1E0h+var_178]
0x180081c20  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180081c25  nop
0x180081c26  mov     rcx, rbx; string
0x180081c29  call    cs:__imp_WindowsDeleteString
0x180081c2f  xor     ebx, ebx
0x180081c31  test    esi, esi
0x180081c33  jns     loc_180081CFC
0x180081c39  mov     esi, ebx
0x180081c3b  lock inc [rbp+0E0h+var_158]
0x180081c3f  mov     [rsp+1E0h+var_180], rbx
0x180081c44  lea     rax, [rbp+0E0h+var_138]
0x180081c48  mov     [rbp+0E0h+var_110], rax
0x180081c4c  mov     rax, [rbp+0E0h+var_120]
0x180081c50  mov     [rbp+0E0h+var_108], rax
0x180081c54  mov     [rbp+0E0h+var_100], r15d
0x180081c58  lea     rax, [rbp+0E0h+var_158]
0x180081c5c  mov     [rbp+0E0h+var_F8], rax
0x180081c60  mov     [rbp+0E0h+var_F0], r12
0x180081c64  mov     rcx, [rsp+1E0h+var_168]
0x180081c69  mov     [rbp+0E0h+var_E8], rcx
0x180081c6d  test    rcx, rcx
0x180081c70  jz      short loc_180081C7F
0x180081c72  mov     rax, [rcx]
0x180081c75  mov     rax, [rax+8]
0x180081c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081c7e  nop
0x180081c7f  mov     [rbp+0E0h+var_E0], r13
0x180081c83  lea     rcx, [rsp+1E0h+var_180]
0x180081c88  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180081c8d  mov     [rbp+0E0h+var_130], 2
0x180081c95  mov     [rbp+0E0h+var_128], ebx
0x180081c98  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180081c9f  mov     ecx, 50h ; 'P'; unsigned __int64
0x180081ca4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180081ca9  mov     [rbp+0E0h+var_D8], rax
0x180081cad  test    rax, rax
0x180081cb0  jz      short loc_180081CC0
0x180081cb2  lea     rdx, [rbp+0E0h+var_110]
0x180081cb6  mov     rcx, rax
0x180081cb9  call    Windows__Internal__COperationLambdaVar_0__lambda_6ae8a561a9abe19f78ed883c7fb16267__Windows__Internal__CNoResult___COperationLambdaVar_0__lambda_6ae8a561a9abe19f78ed883c7fb16267__Windows__Internal__CNoResult___lambda_6ae8a561a9abe19f78ed883c7fb16267___
0x180081cbe  jmp     short loc_180081CC3
0x180081cc0  mov     rax, rbx
0x180081cc3  mov     r9, rax
0x180081cc6  lea     rdx, [rsp+1E0h+var_180]
0x180081ccb  lea     rcx, [rbp+0E0h+var_130]
0x180081ccf  call    ??$MakeAsyncActionHelper@VComTaskPoolHandler@Internal@Windows@@UDisableCausality@WRL@Microsoft@@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAUIAsyncAction@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@VCNoResult@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncActionHelper<Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::DisableCausality>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncAction * *,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CNoResult> *)
0x180081cd4  mov     ebx, eax
0x180081cd6  lea     rcx, [rbp+0E0h+var_E8]
0x180081cda  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180081cdf  shr     ebx, 1Fh
0x180081ce2  test    bl, bl
0x180081ce4  jz      short loc_180081CF0
0x180081ce6  lea     rcx, [rbp+0E0h+var_158]; this
0x180081cea  call    ?Release@RefCountedEvent@@QEAAJXZ; RefCountedEvent::Release(void)
0x180081cef  nop
0x180081cf0  lea     rcx, [rsp+1E0h+var_180]
0x180081cf5  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180081cfa  xor     ebx, ebx
0x180081cfc  mov     rcx, rdi; string
0x180081cff  call    cs:__imp_WindowsDeleteString
0x180081d05  nop
0x180081d06  mov     rcx, [rsp+1E0h+string]; string
0x180081d0b  call    cs:__imp_WindowsDeleteString
0x180081d11  mov     [rsp+1E0h+string], rbx
0x180081d16  mov     rcx, [rbp+0E0h+var_160]; string
0x180081d1a  call    cs:__imp_WindowsDeleteString
0x180081d20  inc     r15d
0x180081d23  cmp     r15d, [rsp+1E0h+var_188]
0x180081d28  jb      loc_1800819E5
0x180081d2e  mov     r12, [rbp+0E0h+var_118]
0x180081d32  lea     rcx, [rbp+0E0h+var_158]; this
0x180081d36  call    ?Release@RefCountedEvent@@QEAAJXZ; RefCountedEvent::Release(void)
0x180081d3b  lea     rcx, [rbp+0E0h+var_158]; this
0x180081d3f  call    ?Wait@RefCountedEvent@@QEAAKK@Z; RefCountedEvent::Wait(ulong)
0x180081d44  nop
0x180081d45  lea     rcx, [rsp+1E0h+var_190]
0x180081d4a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180081d4f  nop
0x180081d50  lea     rcx, [rbp+0E0h+var_158]; this
0x180081d54  call    ??1RefCountedEvent@@QEAA@XZ; RefCountedEvent::~RefCountedEvent(void)
0x180081d59  nop
0x180081d5a  lea     rcx, [rbp+0E0h+var_138]
0x180081d5e  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180081d63  test    esi, esi
0x180081d65  js      short loc_180081DB4
0x180081d67  mov     [rsp+1E0h+var_190], rbx
0x180081d6c  mov     rdi, [rsp+1E0h+var_168]
0x180081d71  mov     rax, [rdi]
0x180081d74  mov     rbx, [rax+40h]
0x180081d78  lea     rcx, [rsp+1E0h+var_190]
0x180081d7d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180081d82  lea     rdx, [rsp+1E0h+var_190]
0x180081d87  mov     rcx, rdi
  ... truncated ...
```
