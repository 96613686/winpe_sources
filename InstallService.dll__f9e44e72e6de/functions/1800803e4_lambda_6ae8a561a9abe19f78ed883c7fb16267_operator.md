# _lambda_6ae8a561a9abe19f78ed883c7fb16267_::operator()

- ea: `0x1800803e4`
- end: `0x180080800`
- name: `_lambda_6ae8a561a9abe19f78ed883c7fb16267_::operator()`
- size: `1052`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180084040`

## callees

- `0x1800101f4`
- `0x18001c414`
- `0x18006888c`
- `0x180069af0`
- `0x18008004c`
- `0x1800803e4`
- `0x180082258`
- `0x180083e70`
- `0x1800d5fa8`
- `0x1800d9c20`
- `0x1800dc164`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008044f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008047b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008054e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080629`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080657`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080713`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080739`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080743`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800807d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800807e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008044f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008047b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008054e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080629`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080657`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080713`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080739`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080743`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800807d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800807e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008057d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008058c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800805e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180080667`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008068d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008069b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800806b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800806c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180080751`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008057d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008058c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800805e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180080667`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008068d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008069b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800806b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800806c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180080751`

## string_xrefs

- `0x1800805c7`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x1800806fe`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x180080784`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x180080500`: `AppUpdate`
- `0x1800805a6`: `ContentId: %s, non-cached FulfillmentData: %s`
- `0x180080766`: `Failed to Find fulfillmentdata in the response json for contentId %s`
- `0x1800806e0`: `Failed to cache fulfillmentdata. key = %s, data = %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall lambda_6ae8a561a9abe19f78ed883c7fb16267_::operator()(
        __int64 **a1,
        struct WindowsUpdate::Internal::IFulfillmentDataInfo *a2)
{
  __int64 v3; // rdi
  int (__fastcall *v4)(__int64, _QWORD, __int64 *); // rbx
  __int64 v5; // rdi
  int (__fastcall *v6)(__int64, HSTRING *); // rbx
  __int64 v7; // rdi
  void (__fastcall *v8)(__int64, HSTRING *); // rbx
  int ProductData; // r14d
  HSTRING v10; // rbx
  PCWSTR v11; // rdi
  PCWSTR v12; // rax
  const unsigned __int16 *v13; // rax
  const unsigned __int16 *v14; // rax
  HSTRING v15; // rdi
  PCWSTR v16; // rsi
  const WCHAR *v17; // rax
  int v18; // r12d
  PCWSTR v19; // rsi
  PCWSTR v20; // rax
  PCWSTR StringRawBuffer; // rax
  HSTRING v23; // [rsp+50h] [rbp-19h] BYREF
  struct IInspectable *v24; // [rsp+58h] [rbp-11h] BYREF
  struct Windows::Data::Json::IJsonObject *v25; // [rsp+60h] [rbp-9h] BYREF
  struct AppId *v26; // [rsp+68h] [rbp-1h] BYREF
  HSTRING v27; // [rsp+70h] [rbp+7h] BYREF
  HSTRING v28[9]; // [rsp+78h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+D0h] [rbp+67h] BYREF
  struct WindowsUpdate::Internal::IFulfillmentDataInfo *v30; // [rsp+D8h] [rbp+6Fh] BYREF
  HSTRING v31; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v32; // [rsp+E8h] [rbp+7Fh] BYREF

  v30 = a2;
  string = 0;
  v31 = 0;
  v32 = 0;
  v3 = **a1;
  v4 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v3 + 48LL);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
  if ( v4(v3, *((unsigned int *)a1 + 4), &v32) >= 0 )
  {
    v5 = v32;
    v6 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 48LL);
    WindowsDeleteString(string);
    string = 0;
    if ( v6(v5, &string) >= 0 )
    {
      v7 = v32;
      v8 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 56LL);
      WindowsDeleteString(v31);
      v31 = 0;
      v8(v7, &v31);
    }
  }
  v26 = 0;
  v28[0] = 0;
  v27 = 0;
  LODWORD(v30) = 5;
  v25 = (struct Windows::Data::Json::IJsonObject *)string;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v26);
  ProductData = Microsoft::WRL::Details::MakeAndInitialize<AppId,AppId,HSTRING__ * &,enum AppId::Type,HSTRING__ * &,HSTRING__ * &>(
                  (unsigned int)&v26,
                  (unsigned int)&v25,
                  (unsigned int)&v30,
                  (unsigned int)&v27,
                  (__int64)v28);
  if ( ProductData >= 0 )
  {
    v25 = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v25);
    ProductData = GetProductData(
                    (struct Windows::System::IUser *)a1[1],
                    v26,
                    (HSTRING)a1[4],
                    L"AppUpdate",
                    (struct TraceLoggingCorrelationVector *)a1[6],
                    &v25);
    if ( ProductData >= 0 )
    {
      v24 = 0;
      v30 = 0;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v24);
      ProductData = FindFulfillmentData(v25, (struct Windows::Data::Json::IJsonObject **)&v24);
      if ( ProductData < 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        LogMessage(
          1u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
          0x25Eu,
          "GetFulfillmentData::<lambda_6ae8a561a9abe19f78ed883c7fb16267>::operator ()",
          ProductData,
          L"Failed to Find fulfillmentdata in the response json for contentId %s",
          0,
          0,
          StringRawBuffer);
      }
      else
      {
        WindowsDeleteString(0);
        v27 = 0;
        ProductData = Json_Stringify(v24, &v27);
        v10 = v27;
        if ( ProductData >= 0 )
        {
          v23 = 0;
          v11 = WindowsGetStringRawBuffer(v27, 0);
          v12 = WindowsGetStringRawBuffer(string, 0);
          LogMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
            0x25Eu,
            "GetFulfillmentData::<lambda_6ae8a561a9abe19f78ed883c7fb16267>::operator ()",
            -1,
            L"ContentId: %s, non-cached FulfillmentData: %s",
            0,
            0,
            v12,
            v11);
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v30);
          v13 = WindowsGetStringRawBuffer(v10, 0);
          ProductData = WindowsUpdate::Internal::FulfillmentDataInfo::CreateFromFulfillmentData(v13, &v30);
          if ( ProductData >= 0 )
          {
            ProductData = (*(__int64 (__fastcall **)(struct WindowsUpdate::Internal::IFulfillmentDataInfo *, HSTRING))(*(_QWORD *)v30 + 208LL))(
                            v30,
                            v31);
            if ( ProductData >= 0 )
            {
              WindowsDeleteString(v23);
              v23 = 0;
              ProductData = (*(__int64 (__fastcall **)(struct WindowsUpdate::Internal::IFulfillmentDataInfo *, HSTRING *))(*(_QWORD *)v30 + 168LL))(
                              v30,
                              &v23);
              if ( ProductData >= 0 )
              {
                WindowsDeleteString(0);
                v28[0] = 0;
                v14 = WindowsGetStringRawBuffer(string, 0);
                ProductData = ConstructFulfillmentDataCacheKey(v14, v28);
                v15 = v28[0];
                if ( ProductData >= 0 )
                {
                  v16 = WindowsGetStringRawBuffer(v10, 0);
                  v17 = WindowsGetStringRawBuffer(v15, 0);
                  v18 = SetCachedFulfillmentData(v17, v16);
                  if ( v18 < 0 )
                  {
                    v19 = WindowsGetStringRawBuffer(v10, 0);
                    v20 = WindowsGetStringRawBuffer(v15, 0);
                    LogMessage(
                      2u,
                      "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
                      0x25Eu,
                      "GetFulfillmentData::<lambda_6ae8a561a9abe19f78ed883c7fb16267>::operator ()",
                      v18,
                      L"Failed to cache fulfillmentdata. key = %s, data = %s",
                      0,
                      0,
                      v20,
                      v19);
                  }
                }
                WindowsDeleteString(v15);
                if ( ProductData >= 0 )
                  ProductData = (*(__int64 (__fastcall **)(__int64 *, struct WindowsUpdate::Internal::IFulfillmentDataInfo *))(*a1[5] + 104))(
                                  a1[5],
                                  v30);
              }
            }
          }
          WindowsDeleteString(v23);
        }
        WindowsDeleteString(v10);
      }
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v30);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v24);
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v25);
  }
  RefCountedEvent::Release((RefCountedEvent *)a1[3]);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
  WindowsDeleteString(v31);
  v31 = 0;
  WindowsDeleteString(string);
  return (unsigned int)ProductData;
}

```

## disassembly

```asm
0x1800803e4  mov     [rsp-8+arg_8], rdx
0x1800803e9  push    rbp
0x1800803ea  push    rbx
0x1800803eb  push    rsi
0x1800803ec  push    rdi
0x1800803ed  push    r12
0x1800803ef  push    r13
0x1800803f1  push    r14
0x1800803f3  push    r15
0x1800803f5  lea     rbp, [rsp-1Fh]
0x1800803fa  sub     rsp, 88h
0x180080401  mov     r15, rcx
0x180080404  xor     r13d, r13d
0x180080407  mov     [rbp+57h+string], r13
0x18008040b  mov     [rbp+57h+arg_10], r13
0x18008040f  mov     [rbp+57h+arg_18], r13
0x180080413  mov     rax, [rcx]
0x180080416  mov     rdi, [rax]
0x180080419  mov     rax, [rdi]
0x18008041c  mov     rbx, [rax+30h]
0x180080420  lea     rcx, [rbp+57h+arg_18]
0x180080424  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180080429  lea     r8, [rbp+57h+arg_18]
0x18008042d  mov     edx, [r15+10h]
0x180080431  mov     rcx, rdi
0x180080434  mov     rax, rbx
0x180080437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008043c  test    eax, eax
0x18008043e  js      short loc_180080494
0x180080440  mov     rdi, [rbp+57h+arg_18]
0x180080444  mov     rax, [rdi]
0x180080447  mov     rbx, [rax+30h]
0x18008044b  mov     rcx, [rbp+57h+string]; string
0x18008044f  call    cs:__imp_WindowsDeleteString
0x180080455  mov     [rbp+57h+string], r13
0x180080459  lea     rdx, [rbp+57h+string]
0x18008045d  mov     rcx, rdi
0x180080460  mov     rax, rbx
0x180080463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080468  test    eax, eax
0x18008046a  js      short loc_180080494
0x18008046c  mov     rdi, [rbp+57h+arg_18]
0x180080470  mov     rax, [rdi]
0x180080473  mov     rbx, [rax+38h]
0x180080477  mov     rcx, [rbp+57h+arg_10]; string
0x18008047b  call    cs:__imp_WindowsDeleteString
0x180080481  mov     [rbp+57h+arg_10], r13
0x180080485  lea     rdx, [rbp+57h+arg_10]
0x180080489  mov     rcx, rdi
0x18008048c  mov     rax, rbx
0x18008048f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080494  mov     [rbp+57h+var_58], r13
0x180080498  mov     [rbp+57h+var_48], r13
0x18008049c  mov     [rbp+57h+var_50], r13
0x1800804a0  mov     dword ptr [rbp+57h+arg_8], 5
0x1800804a7  mov     rax, [rbp+57h+string]
0x1800804ab  mov     [rbp+57h+var_60], rax
0x1800804af  lea     rcx, [rbp+57h+var_58]
0x1800804b3  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800804b8  lea     rax, [rbp+57h+var_48]
0x1800804bc  mov     [rsp+0C0h+var_A0], rax
0x1800804c1  lea     r9, [rbp+57h+var_50]
0x1800804c5  lea     r8, [rbp+57h+arg_8]
0x1800804c9  lea     rdx, [rbp+57h+var_60]
0x1800804cd  lea     rcx, [rbp+57h+var_58]
0x1800804d1  call    ??$MakeAndInitialize@VAppId@@V1@AEAPEAUHSTRING__@@W4Type@1@AEAPEAU2@AEAPEAU2@@Details@WRL@Microsoft@@YAJPEAPEAVAppId@@AEAPEAUHSTRING__@@$$QEAW4Type@3@11@Z; Microsoft::WRL::Details::MakeAndInitialize<AppId,AppId,HSTRING__ * &,AppId::Type,HSTRING__ * &,HSTRING__ * &>(AppId * *,HSTRING__ * &,AppId::Type &&,HSTRING__ * &,HSTRING__ * &)
0x1800804d6  mov     r14d, eax
0x1800804d9  test    eax, eax
0x1800804db  js      loc_1800807B3
0x1800804e1  mov     [rbp+57h+var_60], r13
0x1800804e5  lea     rcx, [rbp+57h+var_60]
0x1800804e9  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800804ee  lea     rax, [rbp+57h+var_60]
0x1800804f2  mov     [rsp+0C0h+var_98], rax; struct Windows::Data::Json::IJsonObject **
0x1800804f7  mov     rax, [r15+30h]
0x1800804fb  mov     [rsp+0C0h+var_A0], rax; struct TraceLoggingCorrelationVector *
0x180080500  lea     r9, aAppupdate; "AppUpdate"
0x180080507  mov     r8, [r15+20h]; HSTRING
0x18008050b  mov     rdx, [rbp+57h+var_58]; struct AppId *
0x18008050f  mov     rcx, [r15+8]; struct Windows::System::IUser *
0x180080513  call    ?GetProductData@@YAJPEAUIUser@System@Windows@@PEAVAppId@@PEAUHSTRING__@@PEBGPEAVTraceLoggingCorrelationVector@@PEAPEAUIJsonObject@Json@Data@3@@Z; GetProductData(Windows::System::IUser *,AppId *,HSTRING__ *,ushort const *,TraceLoggingCorrelationVector *,Windows::Data::Json::IJsonObject * *)
0x180080518  mov     r14d, eax
0x18008051b  test    eax, eax
0x18008051d  js      loc_1800807AA
0x180080523  mov     [rbp+57h+var_68], r13
0x180080527  mov     [rbp+57h+arg_8], r13
0x18008052b  lea     rcx, [rbp+57h+var_68]
0x18008052f  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180080534  lea     rdx, [rbp+57h+var_68]; struct Windows::Data::Json::IJsonObject **
0x180080538  mov     rcx, [rbp+57h+var_60]; struct Windows::Data::Json::IJsonObject *
0x18008053c  call    ?FindFulfillmentData@@YAJPEAUIJsonObject@Json@Data@Windows@@PEAPEAU1234@@Z; FindFulfillmentData(Windows::Data::Json::IJsonObject *,Windows::Data::Json::IJsonObject * *)
0x180080541  mov     r14d, eax
0x180080544  test    eax, eax
0x180080546  js      loc_18008074B
0x18008054c  xor     ecx, ecx; string
0x18008054e  call    cs:__imp_WindowsDeleteString
0x180080554  mov     [rbp+57h+var_50], r13
0x180080558  lea     rdx, [rbp+57h+var_50]; HSTRING *
0x18008055c  mov     rcx, [rbp+57h+var_68]; struct IInspectable *
0x180080560  call    ?Json_Stringify@@YAJPEAUIInspectable@@PEAPEAUHSTRING__@@@Z; Json_Stringify(IInspectable *,HSTRING__ * *)
0x180080565  mov     r14d, eax
0x180080568  mov     rbx, [rbp+57h+var_50]
0x18008056c  test    eax, eax
0x18008056e  js      loc_180080740
0x180080574  mov     [rbp+57h+var_70], r13
0x180080578  xor     edx, edx; length
0x18008057a  mov     rcx, rbx; string
0x18008057d  call    cs:__imp_WindowsGetStringRawBuffer
0x180080583  mov     rdi, rax
0x180080586  xor     edx, edx; length
0x180080588  mov     rcx, [rbp+57h+string]; string
0x18008058c  call    cs:__imp_WindowsGetStringRawBuffer
0x180080592  mov     [rsp+0C0h+var_78], rdi
0x180080597  mov     [rsp+0C0h+var_80], rax
0x18008059c  mov     [rsp+0C0h+var_88], r13; unsigned __int16 *
0x1800805a1  mov     [rsp+0C0h+var_90], r13; char *
0x1800805a6  lea     rax, aContentidSNonC; "ContentId: %s, non-cached FulfillmentDa"...
0x1800805ad  mov     [rsp+0C0h+var_98], rax; unsigned __int16 *
0x1800805b2  mov     dword ptr [rsp+0C0h+var_A0], 0FFFFFFFFh; int
0x1800805ba  lea     r9, aGetfulfillment; "GetFulfillmentData::<lambda_6ae8a561a9a"...
0x1800805c1  mov     r8d, 25Eh; unsigned int
0x1800805c7  lea     rdx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x1800805ce  mov     ecx, 3; unsigned int
0x1800805d3  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800805d8  lea     rcx, [rbp+57h+arg_8]
0x1800805dc  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800805e1  xor     edx, edx; length
0x1800805e3  mov     rcx, rbx; string
0x1800805e6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800805ec  lea     rdx, [rbp+57h+arg_8]; struct WindowsUpdate::Internal::IFulfillmentDataInfo **
0x1800805f0  mov     rcx, rax; unsigned __int16 *
0x1800805f3  call    ?CreateFromFulfillmentData@FulfillmentDataInfo@Internal@WindowsUpdate@@SAJPEBGPEAPEAUIFulfillmentDataInfo@23@@Z; WindowsUpdate::Internal::FulfillmentDataInfo::CreateFromFulfillmentData(ushort const *,WindowsUpdate::Internal::IFulfillmentDataInfo * *)
0x1800805f8  mov     r14d, eax
0x1800805fb  test    eax, eax
0x1800805fd  js      loc_180080735
0x180080603  mov     rcx, [rbp+57h+arg_8]
0x180080607  mov     rax, [rcx]
0x18008060a  mov     rdx, [rbp+57h+arg_10]
0x18008060e  mov     rax, [rax+0D0h]
0x180080615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008061a  mov     r14d, eax
0x18008061d  test    eax, eax
0x18008061f  js      loc_180080735
0x180080625  mov     rcx, [rbp+57h+var_70]; string
0x180080629  call    cs:__imp_WindowsDeleteString
0x18008062f  mov     [rbp+57h+var_70], r13
0x180080633  mov     rcx, [rbp+57h+arg_8]
0x180080637  mov     rax, [rcx]
0x18008063a  lea     rdx, [rbp+57h+var_70]
0x18008063e  mov     rax, [rax+0A8h]
0x180080645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008064a  mov     r14d, eax
0x18008064d  test    eax, eax
0x18008064f  js      loc_180080735
0x180080655  xor     ecx, ecx; string
0x180080657  call    cs:__imp_WindowsDeleteString
0x18008065d  mov     [rbp+57h+var_48], r13
0x180080661  xor     edx, edx; length
0x180080663  mov     rcx, [rbp+57h+string]; string
0x180080667  call    cs:__imp_WindowsGetStringRawBuffer
0x18008066d  lea     rdx, [rbp+57h+var_48]; HSTRING *
0x180080671  mov     rcx, rax; unsigned __int16 *
0x180080674  call    ?ConstructFulfillmentDataCacheKey@@YAJPEBGPEAPEAUHSTRING__@@@Z; ConstructFulfillmentDataCacheKey(ushort const *,HSTRING__ * *)
0x180080679  mov     r14d, eax
0x18008067c  mov     rdi, [rbp+57h+var_48]
0x180080680  test    eax, eax
0x180080682  js      loc_180080710
0x180080688  xor     edx, edx; length
0x18008068a  mov     rcx, rbx; string
0x18008068d  call    cs:__imp_WindowsGetStringRawBuffer
0x180080693  mov     rsi, rax
0x180080696  xor     edx, edx; length
0x180080698  mov     rcx, rdi; string
0x18008069b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800806a1  mov     rdx, rsi; lpData
0x1800806a4  mov     rcx, rax; lpValueName
0x1800806a7  call    ?SetCachedFulfillmentData@@YAJPEBG0@Z; SetCachedFulfillmentData(ushort const *,ushort const *)
0x1800806ac  mov     r12d, eax
0x1800806af  test    eax, eax
0x1800806b1  jns     short loc_180080710
0x1800806b3  xor     edx, edx; length
0x1800806b5  mov     rcx, rbx; string
0x1800806b8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800806be  mov     rsi, rax
0x1800806c1  xor     edx, edx; length
0x1800806c3  mov     rcx, rdi; string
0x1800806c6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800806cc  mov     [rsp+0C0h+var_78], rsi
0x1800806d1  mov     [rsp+0C0h+var_80], rax
0x1800806d6  mov     [rsp+0C0h+var_88], r13; unsigned __int16 *
0x1800806db  mov     [rsp+0C0h+var_90], r13; char *
0x1800806e0  lea     rax, aFailedToCacheF; "Failed to cache fulfillmentdata. key = "...
0x1800806e7  mov     [rsp+0C0h+var_98], rax; unsigned __int16 *
0x1800806ec  mov     dword ptr [rsp+0C0h+var_A0], r12d; int
0x1800806f1  lea     r9, aGetfulfillment; "GetFulfillmentData::<lambda_6ae8a561a9a"...
0x1800806f8  mov     r8d, 25Eh; unsigned int
0x1800806fe  lea     rdx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x180080705  mov     ecx, 2; unsigned int
0x18008070a  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18008070f  nop
0x180080710  mov     rcx, rdi; string
0x180080713  call    cs:__imp_WindowsDeleteString
0x180080719  test    r14d, r14d
0x18008071c  js      short loc_180080735
0x18008071e  mov     rcx, [r15+28h]
0x180080722  mov     rax, [rcx]
0x180080725  mov     rdx, [rbp+57h+arg_8]
0x180080729  mov     rax, [rax+68h]
0x18008072d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080732  mov     r14d, eax
0x180080735  mov     rcx, [rbp+57h+var_70]; string
0x180080739  call    cs:__imp_WindowsDeleteString
0x18008073f  nop
0x180080740  mov     rcx, rbx; string
0x180080743  call    cs:__imp_WindowsDeleteString
0x180080749  jmp     short loc_180080796
0x18008074b  xor     edx, edx; length
0x18008074d  mov     rcx, [rbp+57h+string]; string
0x180080751  call    cs:__imp_WindowsGetStringRawBuffer
0x180080757  mov     [rsp+0C0h+var_80], rax
0x18008075c  mov     [rsp+0C0h+var_88], r13; unsigned __int16 *
0x180080761  mov     [rsp+0C0h+var_90], r13; char *
0x180080766  lea     rax, aFailedToFindFu; "Failed to Find fulfillmentdata in the r"...
0x18008076d  mov     [rsp+0C0h+var_98], rax; unsigned __int16 *
0x180080772  mov     dword ptr [rsp+0C0h+var_A0], r14d; int
0x180080777  lea     r9, aGetfulfillment; "GetFulfillmentData::<lambda_6ae8a561a9a"...
0x18008077e  mov     r8d, 25Eh; unsigned int
0x180080784  lea     rdx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x18008078b  mov     ecx, 1; unsigned int
0x180080790  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180080795  nop
0x180080796  lea     rcx, [rbp+57h+arg_8]
0x18008079a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18008079f  nop
0x1800807a0  lea     rcx, [rbp+57h+var_68]
0x1800807a4  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800807a9  nop
0x1800807aa  lea     rcx, [rbp+57h+var_60]
0x1800807ae  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800807b3  mov     rcx, [r15+18h]; this
0x1800807b7  call    ?Release@RefCountedEvent@@QEAAJXZ; RefCountedEvent::Release(void)
0x1800807bc  nop
0x1800807bd  lea     rcx, [rbp+57h+var_58]
0x1800807c1  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800807c6  nop
0x1800807c7  lea     rcx, [rbp+57h+arg_18]
0x1800807cb  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800807d0  nop
0x1800807d1  mov     rcx, [rbp+57h+arg_10]; string
0x1800807d5  call    cs:__imp_WindowsDeleteString
0x1800807db  mov     [rbp+57h+arg_10], r13
0x1800807df  mov     rcx, [rbp+57h+string]; string
0x1800807e3  call    cs:__imp_WindowsDeleteString
0x1800807e9  mov     eax, r14d
0x1800807ec  add     rsp, 88h
0x1800807f3  pop     r15
0x1800807f5  pop     r14
0x1800807f7  pop     r13
0x1800807f9  pop     r12
0x1800807fb  pop     rdi
0x1800807fc  pop     rsi
0x1800807fd  pop     rbx
0x1800807fe  pop     rbp
0x1800807ff  retn
```
