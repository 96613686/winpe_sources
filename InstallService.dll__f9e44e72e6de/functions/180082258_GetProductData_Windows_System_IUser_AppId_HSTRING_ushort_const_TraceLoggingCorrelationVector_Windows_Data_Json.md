# GetProductData(Windows::System::IUser *,AppId *,HSTRING__ *,ushort const *,TraceLoggingCorrelationVector *,Windows::Data::Json::IJsonObject * *)

- ea: `0x180082258`
- end: `0x1800826e2`
- name: `?GetProductData@@YAJPEAUIUser@System@Windows@@PEAVAppId@@PEAUHSTRING__@@PEBGPEAVTraceLoggingCorrelationVector@@PEAPEAUIJsonObject@Json@Data@3@@Z`
- size: `1162`
- prototype: `int(struct Windows::System::IUser *, struct AppId *, HSTRING, const unsigned __int16 *, struct TraceLoggingCorrelationVector *, struct Windows::Data::Json::IJsonObject **)`
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800803e4`
- `0x180082824`
- `0x18012d378`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x18001c414`
- `0x18001c844`
- `0x18003f884`
- `0x18008104c`
- `0x1800816b0`
- `0x18008176c`
- `0x180082258`
- `0x18008297c`
- `0x180082c10`
- `0x180083b2c`
- `0x1800d5fa8`
- `0x18011be34`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082641`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082641`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800822a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008250e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082622`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082664`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800822a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008250e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082622`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082664`

## string_xrefs

- `0x1800822ef`: `InstallAgent`
- `0x1800822dd`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x180082327`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x180082368`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x1800823c4`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x18008241f`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x180082485`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x1800824d3`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x180082549`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x1800825a1`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x1800825ea`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x180082696`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x1800823a3`: `Product data cache hit: %s`
- `0x18008240c`: `MakeAlternateIdUri(pAppId, szMoId, pszFieldsTemplate, pCV, &spUri)`
- `0x180082355`: `GenerateCacheKey(pAppId, szMoId, pszFieldsTemplate, szCacheKey, ARRAYSIZE(szCacheKey))`
- `0x1800824c0`: `ProductDataFromCatalogResponse(pAppId, spJsonObject.Get(), &spProduct)`
- `0x1800825d7`: `ProductDataFromCatalogResponse(pAppId, spJsonObject.Get(), &spProduct)`
- `0x180082472`: `GetUriResponseWithAuthTicket(user, spUri.Get(), pCV, pAppId->CatalogIdHStr().Get(), acquistionIdentity, false , &spJsonObject)`
- `0x18008258e`: `GetUriResponseWithAuthTicket(user, spUri.Get(), pCV, pAppId->CatalogIdHStr().Get(), acquistionIdentity, true , &spJsonObject)`
- `0x18008252c`: `Could not find Product Document for productId = %s, CV = %hs. This was an M$ search. Retrying with AAD tokens`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetProductData(
        struct Windows::System::IUser *a1,
        HSTRING *a2,
        HSTRING a3,
        const unsigned __int16 *a4,
        struct TraceLoggingCorrelationVector *a5,
        struct Windows::Data::Json::IJsonObject **a6)
{
  unsigned int v10; // r8d
  const unsigned __int16 *v11; // rsi
  int ExclusivityId; // eax
  __int64 result; // rax
  int CacheKey; // eax
  int DataFromCache; // ebx
  int AlternateIdUri; // eax
  int UriResponseWithAuthTicket; // eax
  int v18; // eax
  PCWSTR StringRawBuffer; // rax
  int v20; // eax
  int v21; // eax
  const unsigned __int8 *v22; // rax
  struct IInspectable *v23; // rax
  PCWSTR v24; // rax
  HSTRING v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+28h] [rbp-D8h]
  int v27; // [rsp+28h] [rbp-D8h]
  int v28; // [rsp+28h] [rbp-D8h]
  int v29; // [rsp+28h] [rbp-D8h]
  int v30; // [rsp+28h] [rbp-D8h]
  int v31; // [rsp+28h] [rbp-D8h]
  int v32; // [rsp+28h] [rbp-D8h]
  struct IInspectable *v33; // [rsp+50h] [rbp-B0h] BYREF
  struct Windows::Data::Json::IJsonObject *v34; // [rsp+58h] [rbp-A8h] BYREF
  struct Windows::Foundation::IUriRuntimeClass *v35; // [rsp+60h] [rbp-A0h] BYREF
  UINT32 length; // [rsp+68h] [rbp-98h] BYREF
  HSTRING string; // [rsp+70h] [rbp-90h] BYREF
  char v38[144]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v39[264]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v40[256]; // [rsp+320h] [rbp+220h] BYREF

  WindowsGetStringRawBuffer(a2[8], 0);
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
    0x3A8u,
    "GetProductData",
    -1,
    L"request: productId = %s",
    0,
    0);
  *a6 = 0;
  v11 = L"InstallAgent";
  if ( a4 )
    v11 = a4;
  ExclusivityId = GetExclusivityId(L"MOID", v40, v10);
  result = TraceHR(
             "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
             0x3B3u,
             "GetProductData",
             "GetExclusivityId(L\"MOID\", szMoId, ARRAYSIZE(szMoId))",
             ExclusivityId,
             v26);
  if ( (int)result >= 0 )
  {
    CacheKey = GenerateCacheKey((struct AppId *)a2, v40, v11, v39, (unsigned __int64)v25);
    result = TraceHR(
               "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
               0x3B6u,
               "GetProductData",
               "GenerateCacheKey(pAppId, szMoId, pszFieldsTemplate, szCacheKey, ARRAYSIZE(szCacheKey))",
               CacheKey,
               v27);
    if ( (int)result >= 0 )
    {
      DataFromCache = GetDataFromCache(v39, a6);
      if ( DataFromCache < 0 )
      {
        v35 = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
        AlternateIdUri = MakeAlternateIdUri((struct AppId *)a2, v40, v11, a5, &v35);
        DataFromCache = TraceHR(
                          "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
                          0x3C8u,
                          "GetProductData",
                          "MakeAlternateIdUri(pAppId, szMoId, pszFieldsTemplate, pCV, &spUri)",
                          AlternateIdUri,
                          v28);
        if ( DataFromCache >= 0 )
        {
          v34 = 0;
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34);
          UriResponseWithAuthTicket = GetUriResponseWithAuthTicket(a1, v35, a5, a2[10], a3, 0, &v34);
          DataFromCache = TraceHR(
                            "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
                            0x3D0u,
                            "GetProductData",
                            "GetUriResponseWithAuthTicket(user, spUri.Get(), pCV, pAppId->CatalogIdHStr().Get(), acquisti"
                            "onIdentity, false , &spJsonObject)",
                            UriResponseWithAuthTicket,
                            v29);
          if ( DataFromCache >= 0 )
          {
            v33 = 0;
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v33);
            v18 = ProductDataFromCatalogResponse(
                    (struct AppId *)a2,
                    v34,
                    (struct Windows::Data::Json::IJsonObject **)&v33);
            DataFromCache = TraceHR(
                              "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
                              0x3D4u,
                              "GetProductData",
                              "ProductDataFromCatalogResponse(pAppId, spJsonObject.Get(), &spProduct)",
                              v18,
                              v30);
            if ( DataFromCache >= 0 )
              goto LABEL_14;
            if ( *((_DWORD *)a2 + 14) )
            {
              if ( *((_DWORD *)a2 + 14) != 7 )
              {
                TraceLoggingCorrelationVector::Increment(a5, v38);
                StringRawBuffer = WindowsGetStringRawBuffer(a2[8], 0);
                LogMessage(
                  3u,
                  "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
                  0x3DBu,
                  "GetProductData",
                  DataFromCache,
                  L"Could not find Product Document for productId = %s, CV = %hs. This was an M$ search. Retrying with AAD tokens",
                  0,
                  0,
                  StringRawBuffer,
                  v38);
                Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34);
                v20 = GetUriResponseWithAuthTicket(a1, v35, a5, a2[10], a3, 1u, &v34);
                DataFromCache = TraceHR(
                                  "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
                                  0x3DDu,
                                  "GetProductData",
                                  "GetUriResponseWithAuthTicket(user, spUri.Get(), pCV, pAppId->CatalogIdHStr().Get(), ac"
                                  "quistionIdentity, true , &spJsonObject)",
                                  v20,
                                  v31);
                if ( DataFromCache >= 0 )
                {
                  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v33);
                  v21 = ProductDataFromCatalogResponse(
                          (struct AppId *)a2,
                          v34,
                          (struct Windows::Data::Json::IJsonObject **)&v33);
                  DataFromCache = TraceHR(
                                    "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
                                    0x3E1u,
                                    "GetProductData",
                                    "ProductDataFromCatalogResponse(pAppId, spJsonObject.Get(), &spProduct)",
                                    v21,
                                    v32);
                  if ( DataFromCache >= 0 )
                  {
LABEL_14:
                    string = 0;
                    if ( (int)Json_Stringify(v33, &string) >= 0 )
                    {
                      length = 0;
                      v22 = (const unsigned __int8 *)WindowsGetStringRawBuffer(string, &length);
                      DataCache::StoreData(v39, v22, 2LL * length);
                      WindowsDeleteString(string);
                    }
                    v23 = v33;
                    v33 = 0;
                    *a6 = (struct Windows::Data::Json::IJsonObject *)v23;
                  }
                }
              }
            }
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v33);
          }
          v24 = WindowsGetStringRawBuffer(a2[8], 0);
          LogMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
            0x3EBu,
            "GetProductData",
            DataFromCache,
            L"result: productId = %s",
            0,
            0,
            v24);
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34);
        }
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
      }
      else
      {
        LogMessage(
          4u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
          0x3C3u,
          "GetProductData",
          -1,
          L"Product data cache hit: %s",
          0,
          0,
          v39);
      }
      return (unsigned int)DataFromCache;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180082258  push    rbp
0x18008225a  push    rbx
0x18008225b  push    rsi
0x18008225c  push    rdi
0x18008225d  push    r12
0x18008225f  push    r13
0x180082261  push    r14
0x180082263  push    r15
0x180082265  lea     rbp, [rsp-438h]
0x18008226d  sub     rsp, 538h
0x180082274  mov     rax, cs:__security_cookie
0x18008227b  xor     rax, rsp
0x18008227e  mov     [rbp+470h+var_50], rax
0x180082285  mov     rbx, r9
0x180082288  mov     r13, r8
0x18008228b  mov     rdi, rdx
0x18008228e  mov     r12, rcx
0x180082291  mov     r14, [rbp+470h+arg_20]
0x180082298  mov     r15, [rbp+470h+arg_28]
0x18008229f  xor     edx, edx; length
0x1800822a1  mov     rcx, [rdi+40h]; string
0x1800822a5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800822ab  mov     [rsp+570h+var_530], rax
0x1800822b0  xor     esi, esi
0x1800822b2  mov     [rsp+570h+var_538], rsi; unsigned __int16 *
0x1800822b7  mov     [rsp+570h+var_540], rsi; char *
0x1800822bc  lea     rax, aRequestProduct_6; "request: productId = %s"
0x1800822c3  mov     [rsp+570h+var_548], rax; int
0x1800822c8  mov     dword ptr [rsp+570h+var_550], 0FFFFFFFFh; int
0x1800822d0  lea     r9, aGetproductdata; "GetProductData"
0x1800822d7  mov     r8d, 3A8h; unsigned int
0x1800822dd  lea     rdx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x1800822e4  lea     ecx, [rsi+3]; unsigned int
0x1800822e7  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800822ec  mov     [r15], rsi
0x1800822ef  lea     rsi, aInstallagent; "InstallAgent"
0x1800822f6  test    rbx, rbx
0x1800822f9  cmovnz  rsi, rbx
0x1800822fd  lea     rdx, [rbp+470h+var_250]; unsigned __int16 *
0x180082304  lea     rcx, aMoid; "MOID"
0x18008230b  call    ?GetExclusivityId@@YAJPEBGPEAGK@Z; GetExclusivityId(ushort const *,ushort *,ulong)
0x180082310  mov     dword ptr [rsp+570h+var_550], eax; unsigned __int64
0x180082314  lea     r9, aGetexclusivity; "GetExclusivityId(L\"MOID\", szMoId, ARR"...
0x18008231b  lea     r8, aGetproductdata; "GetProductData"
0x180082322  mov     edx, 3B3h; unsigned int
0x180082327  lea     rcx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x18008232e  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180082333  test    eax, eax
0x180082335  js      loc_1800826BF
0x18008233b  lea     r9, [rbp+470h+var_460]; unsigned __int16 *
0x18008233f  mov     r8, rsi; unsigned __int16 *
0x180082342  lea     rdx, [rbp+470h+var_250]; unsigned __int16 *
0x180082349  mov     rcx, rdi; struct AppId *
0x18008234c  call    ?GenerateCacheKey@@YAJPEAVAppId@@PEBG1PEAG_K@Z; GenerateCacheKey(AppId *,ushort const *,ushort const *,ushort *,unsigned __int64)
0x180082351  mov     dword ptr [rsp+570h+var_550], eax; int
0x180082355  lea     r9, aGeneratecachek_0; "GenerateCacheKey(pAppId, szMoId, pszFie"...
0x18008235c  lea     r8, aGetproductdata; "GetProductData"
0x180082363  mov     edx, 3B6h; unsigned int
0x180082368  lea     rcx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x18008236f  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180082374  test    eax, eax
0x180082376  js      loc_1800826BF
0x18008237c  mov     rdx, r15; struct Windows::Data::Json::IJsonObject **
0x18008237f  lea     rcx, [rbp+470h+var_460]; unsigned __int16 *
0x180082383  call    ?GetDataFromCache@@YAJPEBGPEAPEAUIJsonObject@Json@Data@Windows@@@Z; GetDataFromCache(ushort const *,Windows::Data::Json::IJsonObject * *)
0x180082388  mov     ebx, eax
0x18008238a  xor     ecx, ecx
0x18008238c  test    eax, eax
0x18008238e  js      short loc_1800823DA
0x180082390  lea     rax, [rbp+470h+var_460]
0x180082394  mov     [rsp+570h+var_530], rax
0x180082399  mov     [rsp+570h+var_538], rcx; unsigned __int16 *
0x18008239e  mov     [rsp+570h+var_540], rcx; char *
0x1800823a3  lea     rax, aProductDataCac; "Product data cache hit: %s"
0x1800823aa  mov     [rsp+570h+var_548], rax; unsigned __int16 *
0x1800823af  mov     dword ptr [rsp+570h+var_550], 0FFFFFFFFh; int
0x1800823b7  lea     r9, aGetproductdata; "GetProductData"
0x1800823be  mov     r8d, 3C3h; unsigned int
0x1800823c4  lea     rdx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x1800823cb  mov     ecx, 4; unsigned int
0x1800823d0  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800823d5  jmp     loc_1800826BD
0x1800823da  mov     [rsp+570h+var_510], rcx
0x1800823df  lea     rcx, [rsp+570h+var_510]
0x1800823e4  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800823e9  lea     rax, [rsp+570h+var_510]
0x1800823ee  mov     [rsp+570h+var_550], rax; struct Windows::Foundation::IUriRuntimeClass **
0x1800823f3  mov     r9, r14; struct TraceLoggingCorrelationVector *
0x1800823f6  mov     r8, rsi; unsigned __int16 *
0x1800823f9  lea     rdx, [rbp+470h+var_250]; unsigned __int16 *
0x180082400  mov     rcx, rdi; struct AppId *
0x180082403  call    ?MakeAlternateIdUri@@YAJPEAVAppId@@PEBG1PEAVTraceLoggingCorrelationVector@@PEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z; MakeAlternateIdUri(AppId *,ushort const *,ushort const *,TraceLoggingCorrelationVector *,Windows::Foundation::IUriRuntimeClass * *)
0x180082408  mov     dword ptr [rsp+570h+var_550], eax; int
0x18008240c  lea     r9, aMakealternatei_0; "MakeAlternateIdUri(pAppId, szMoId, pszF"...
0x180082413  lea     r8, aGetproductdata; "GetProductData"
0x18008241a  mov     edx, 3C8h; unsigned int
0x18008241f  lea     rcx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x180082426  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x18008242b  mov     ebx, eax
0x18008242d  xor     esi, esi
0x18008242f  test    eax, eax
0x180082431  js      loc_1800826B3
0x180082437  mov     [rsp+570h+var_518], rsi
0x18008243c  lea     rcx, [rsp+570h+var_518]
0x180082441  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180082446  lea     rax, [rsp+570h+var_518]
0x18008244b  mov     [rsp+570h+var_540], rax; struct Windows::Data::Json::IJsonObject **
0x180082450  mov     byte ptr [rsp+570h+var_548], sil; int
0x180082455  mov     [rsp+570h+var_550], r13; HSTRING
0x18008245a  mov     r9, [rdi+50h]; HSTRING
0x18008245e  mov     r8, r14; struct TraceLoggingCorrelationVector *
0x180082461  mov     rdx, [rsp+570h+var_510]; struct Windows::Foundation::IUriRuntimeClass *
0x180082466  mov     rcx, r12; struct Windows::System::IUser *
0x180082469  call    ?GetUriResponseWithAuthTicket@@YAJPEAUIUser@System@Windows@@PEAUIUriRuntimeClass@Foundation@3@PEAVTraceLoggingCorrelationVector@@PEAUHSTRING__@@3EPEAPEAUIJsonObject@Json@Data@3@@Z; GetUriResponseWithAuthTicket(Windows::System::IUser *,Windows::Foundation::IUriRuntimeClass *,TraceLoggingCorrelationVector *,HSTRING__ *,HSTRING__ *,uchar,Windows::Data::Json::IJsonObject * *)
0x18008246e  mov     dword ptr [rsp+570h+var_550], eax; int
0x180082472  lea     r9, aGeturiresponse; "GetUriResponseWithAuthTicket(user, spUr"...
0x180082479  lea     r8, aGetproductdata; "GetProductData"
0x180082480  mov     edx, 3D0h; unsigned int
0x180082485  lea     rcx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x18008248c  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180082491  mov     ebx, eax
0x180082493  test    eax, eax
0x180082495  js      loc_18008265E
0x18008249b  mov     [rsp+570h+var_520], rsi
0x1800824a0  lea     rcx, [rsp+570h+var_520]
0x1800824a5  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800824aa  lea     r8, [rsp+570h+var_520]; struct Windows::Data::Json::IJsonObject **
0x1800824af  mov     rdx, [rsp+570h+var_518]; struct Windows::Data::Json::IJsonObject *
0x1800824b4  mov     rcx, rdi; struct AppId *
0x1800824b7  call    ?ProductDataFromCatalogResponse@@YAJPEAVAppId@@PEAUIJsonObject@Json@Data@Windows@@PEAPEAU2345@@Z; ProductDataFromCatalogResponse(AppId *,Windows::Data::Json::IJsonObject *,Windows::Data::Json::IJsonObject * *)
0x1800824bc  mov     dword ptr [rsp+570h+var_550], eax; int
0x1800824c0  lea     r9, aProductdatafro; "ProductDataFromCatalogResponse(pAppId, "...
0x1800824c7  lea     r8, aGetproductdata; "GetProductData"
0x1800824ce  mov     edx, 3D4h; unsigned int
0x1800824d3  lea     rcx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x1800824da  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x1800824df  mov     ebx, eax
0x1800824e1  test    eax, eax
0x1800824e3  jns     loc_1800825FC
0x1800824e9  cmp     [rdi+38h], esi
0x1800824ec  jz      loc_180082654
0x1800824f2  cmp     dword ptr [rdi+38h], 7
0x1800824f6  jz      loc_180082654
0x1800824fc  lea     rdx, [rbp+470h+var_4F0]; char *
0x180082500  mov     rcx, r14; this
0x180082503  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x180082508  xor     edx, edx; length
0x18008250a  mov     rcx, [rdi+40h]; string
0x18008250e  call    cs:__imp_WindowsGetStringRawBuffer
0x180082514  lea     rcx, [rbp+470h+var_4F0]
0x180082518  mov     [rsp+570h+var_528], rcx
0x18008251d  mov     [rsp+570h+var_530], rax
0x180082522  mov     [rsp+570h+var_538], rsi; unsigned __int16 *
0x180082527  mov     [rsp+570h+var_540], rsi; char *
0x18008252c  lea     rax, aCouldNotFindPr; "Could not find Product Document for pro"...
0x180082533  mov     [rsp+570h+var_548], rax; unsigned __int16 *
0x180082538  mov     dword ptr [rsp+570h+var_550], ebx; int
0x18008253c  lea     r9, aGetproductdata; "GetProductData"
0x180082543  mov     r8d, 3DBh; unsigned int
0x180082549  lea     rdx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x180082550  lea     ecx, [rsi+3]; unsigned int
0x180082553  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180082558  lea     rcx, [rsp+570h+var_518]
0x18008255d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180082562  lea     rax, [rsp+570h+var_518]
0x180082567  mov     [rsp+570h+var_540], rax; struct Windows::Data::Json::IJsonObject **
0x18008256c  mov     byte ptr [rsp+570h+var_548], 1; int
0x180082571  mov     [rsp+570h+var_550], r13; HSTRING
0x180082576  mov     r9, [rdi+50h]; HSTRING
0x18008257a  mov     r8, r14; struct TraceLoggingCorrelationVector *
0x18008257d  mov     rdx, [rsp+570h+var_510]; struct Windows::Foundation::IUriRuntimeClass *
0x180082582  mov     rcx, r12; struct Windows::System::IUser *
0x180082585  call    ?GetUriResponseWithAuthTicket@@YAJPEAUIUser@System@Windows@@PEAUIUriRuntimeClass@Foundation@3@PEAVTraceLoggingCorrelationVector@@PEAUHSTRING__@@3EPEAPEAUIJsonObject@Json@Data@3@@Z; GetUriResponseWithAuthTicket(Windows::System::IUser *,Windows::Foundation::IUriRuntimeClass *,TraceLoggingCorrelationVector *,HSTRING__ *,HSTRING__ *,uchar,Windows::Data::Json::IJsonObject * *)
0x18008258a  mov     dword ptr [rsp+570h+var_550], eax; int
0x18008258e  lea     r9, aGeturiresponse_0; "GetUriResponseWithAuthTicket(user, spUr"...
0x180082595  lea     r8, aGetproductdata; "GetProductData"
0x18008259c  mov     edx, 3DDh; unsigned int
0x1800825a1  lea     rcx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x1800825a8  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x1800825ad  mov     ebx, eax
0x1800825af  test    eax, eax
0x1800825b1  js      loc_180082654
0x1800825b7  lea     rcx, [rsp+570h+var_520]
0x1800825bc  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800825c1  lea     r8, [rsp+570h+var_520]; struct Windows::Data::Json::IJsonObject **
0x1800825c6  mov     rdx, [rsp+570h+var_518]; struct Windows::Data::Json::IJsonObject *
0x1800825cb  mov     rcx, rdi; struct AppId *
0x1800825ce  call    ?ProductDataFromCatalogResponse@@YAJPEAVAppId@@PEAUIJsonObject@Json@Data@Windows@@PEAPEAU2345@@Z; ProductDataFromCatalogResponse(AppId *,Windows::Data::Json::IJsonObject *,Windows::Data::Json::IJsonObject * *)
0x1800825d3  mov     dword ptr [rsp+570h+var_550], eax; int
0x1800825d7  lea     r9, aProductdatafro; "ProductDataFromCatalogResponse(pAppId, "...
0x1800825de  lea     r8, aGetproductdata; "GetProductData"
0x1800825e5  mov     edx, 3E1h; unsigned int
0x1800825ea  lea     rcx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x1800825f1  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x1800825f6  mov     ebx, eax
0x1800825f8  test    eax, eax
0x1800825fa  js      short loc_180082654
0x1800825fc  mov     [rsp+570h+string], rsi
0x180082601  lea     rdx, [rsp+570h+string]; HSTRING *
0x180082606  mov     rcx, [rsp+570h+var_520]; struct IInspectable *
0x18008260b  call    ?Json_Stringify@@YAJPEAUIInspectable@@PEAPEAUHSTRING__@@@Z; Json_Stringify(IInspectable *,HSTRING__ * *)
0x180082610  test    eax, eax
0x180082612  js      short loc_180082647
0x180082614  mov     [rsp+570h+length], esi
0x180082618  lea     rdx, [rsp+570h+length]; length
0x18008261d  mov     rcx, [rsp+570h+string]; string
0x180082622  call    cs:__imp_WindowsGetStringRawBuffer
0x180082628  mov     r8d, [rsp+570h+length]
0x18008262d  add     r8, r8; unsigned __int64
0x180082630  mov     rdx, rax; unsigned __int8 *
0x180082633  lea     rcx, [rbp+470h+var_460]; unsigned __int16 *
0x180082637  call    ?StoreData@DataCache@@SAJPEBGPEBE_K@Z; DataCache::StoreData(ushort const *,uchar const *,unsigned __int64)
0x18008263c  mov     rcx, [rsp+570h+string]; string
0x180082641  call    cs:__imp_WindowsDeleteString
0x180082647  mov     rax, [rsp+570h+var_520]
0x18008264c  mov     [rsp+570h+var_520], rsi
0x180082651  mov     [r15], rax
0x180082654  lea     rcx, [rsp+570h+var_520]
0x180082659  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18008265e  xor     edx, edx; length
0x180082660  mov     rcx, [rdi+40h]; string
0x180082664  call    cs:__imp_WindowsGetStringRawBuffer
0x18008266a  mov     [rsp+570h+var_530], rax
0x18008266f  mov     [rsp+570h+var_538], rsi; unsigned __int16 *
0x180082674  mov     [rsp+570h+var_540], rsi; char *
0x180082679  lea     rax, aResultProducti_3; "result: productId = %s"
0x180082680  mov     [rsp+570h+var_548], rax; unsigned __int16 *
0x180082685  mov     dword ptr [rsp+570h+var_550], ebx; int
0x180082689  lea     r9, aGetproductdata; "GetProductData"
0x180082690  mov     r8d, 3EBh; unsigned int
0x180082696  lea     rdx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x18008269d  mov     ecx, 3; unsigned int
0x1800826a2  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800826a7  nop
0x1800826a8  lea     rcx, [rsp+570h+var_518]
0x1800826ad  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800826b2  nop
0x1800826b3  lea     rcx, [rsp+570h+var_510]
0x1800826b8  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800826bd  mov     eax, ebx
0x1800826bf  mov     rcx, [rbp+470h+var_50]
0x1800826c6  xor     rcx, rsp; StackCookie
0x1800826c9  call    __security_check_cookie
0x1800826ce  add     rsp, 538h
0x1800826d5  pop     r15
0x1800826d7  pop     r14
0x1800826d9  pop     r13
0x1800826db  pop     r12
0x1800826dd  pop     rdi
0x1800826de  pop     rsi
0x1800826df  pop     rbx
0x1800826e0  pop     rbp
0x1800826e1  retn
```
