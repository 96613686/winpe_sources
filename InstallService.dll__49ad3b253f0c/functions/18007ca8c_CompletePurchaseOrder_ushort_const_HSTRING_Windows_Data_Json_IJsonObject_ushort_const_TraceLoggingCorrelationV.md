# CompletePurchaseOrder(ushort const *,HSTRING__ *,Windows::Data::Json::IJsonObject *,ushort const *,TraceLoggingCorrelationVector *)

- ea: `0x18007ca8c`
- end: `0x18007ccd2`
- name: `?CompletePurchaseOrder@@YAJPEBGPEAUHSTRING__@@PEAUIJsonObject@Json@Data@Windows@@0PEAVTraceLoggingCorrelationVector@@@Z`
- size: `582`
- prototype: `int(const unsigned __int16 *, HSTRING, struct Windows::Data::Json::IJsonObject *, const unsigned __int16 *, struct TraceLoggingCorrelationVector *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18007d7fc`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x18001c844`
- `0x1800252e8`
- `0x18007ca8c`
- `0x18007cf24`
- `0x18007d6a0`
- `0x18007d754`
- `0x18007e714`
- `0x1800d5db4`
- `0x180147988`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007cbe8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007cc5c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007cbe8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007cc5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007cad3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007cbf9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007cc8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ccaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007cad3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007cbf9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007cc8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ccaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007cb50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007cba1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007cb50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007cba1`

## string_xrefs

- `0x18007cb27`: `onecoreuap\enduser\winstore\installservice\lib\purchase.cpp`
- `0x18007cb78`: `onecoreuap\enduser\winstore\installservice\lib\purchase.cpp`
- `0x18007cbc9`: `onecoreuap\enduser\winstore\installservice\lib\purchase.cpp`
- `0x18007cb18`: `CompletePurchaseOrder`
- `0x18007cbba`: `CreateOrderBody(strOrderId.GetRawBuffer(nullptr), callerApplicationId, &spPurchasedOrderBody)`
- `0x18007cb69`: `MakePurchaseOrderUri(strOrderId.GetRawBuffer(nullptr), pCV, &spUri)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CompletePurchaseOrder(
        unsigned __int16 *a1,
        HSTRING a2,
        struct Windows::Data::Json::IJsonObject *a3,
        const unsigned __int16 *a4,
        struct TraceLoggingCorrelationVector *a5)
{
  __int64 (__fastcall *v9)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *); // rbx
  int v10; // eax
  int UriResponseWithAuthTicket; // edi
  const unsigned __int16 *StringRawBuffer; // rax
  int PurchaseOrderUri; // eax
  unsigned __int16 *v14; // rax
  int OrderBody; // eax
  ULONGLONG TickCount64; // r14
  int v17; // ebx
  ULONGLONG v18; // rax
  int v20; // [rsp+28h] [rbp-69h]
  int v21; // [rsp+28h] [rbp-69h]
  int v22; // [rsp+28h] [rbp-69h]
  struct Windows::Data::Json::IJsonObject *v23; // [rsp+28h] [rbp-69h]
  struct IInspectable *v24; // [rsp+50h] [rbp-41h] BYREF
  struct Windows::Foundation::IUriRuntimeClass *v25; // [rsp+58h] [rbp-39h] BYREF
  HSTRING string; // [rsp+60h] [rbp-31h] BYREF
  struct Windows::Data::Json::IJsonObject *v27; // [rsp+68h] [rbp-29h] BYREF
  HSTRING v28; // [rsp+70h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-19h] BYREF
  __int64 v30; // [rsp+90h] [rbp-1h]

  string = 0;
  v9 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *))(*(_QWORD *)a3 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v30 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"orderId", 8u, 7u);
  v10 = v9(a3, v30, &string);
  UriResponseWithAuthTicket = TraceHR(
                                "onecoreuap\\enduser\\winstore\\installservice\\lib\\purchase.cpp",
                                0x10Eu,
                                "CompletePurchaseOrder",
                                "pOrder->GetNamedString(HStringReference(L\"orderId\").Get(), strOrderId.GetAddressOf())",
                                v10,
                                v20);
  if ( UriResponseWithAuthTicket >= 0 )
  {
    v25 = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v25);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    PurchaseOrderUri = MakePurchaseOrderUri(StringRawBuffer, a5, &v25);
    UriResponseWithAuthTicket = TraceHR(
                                  "onecoreuap\\enduser\\winstore\\installservice\\lib\\purchase.cpp",
                                  0x112u,
                                  "CompletePurchaseOrder",
                                  "MakePurchaseOrderUri(strOrderId.GetRawBuffer(nullptr), pCV, &spUri)",
                                  PurchaseOrderUri,
                                  v21);
    if ( UriResponseWithAuthTicket >= 0 )
    {
      v24 = 0;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v24);
      v14 = (unsigned __int16 *)WindowsGetStringRawBuffer(string, 0);
      OrderBody = CreateOrderBody(v14, a4, (struct Windows::Data::Json::IJsonObject **)&v24);
      UriResponseWithAuthTicket = TraceHR(
                                    "onecoreuap\\enduser\\winstore\\installservice\\lib\\purchase.cpp",
                                    0x116u,
                                    "CompletePurchaseOrder",
                                    "CreateOrderBody(strOrderId.GetRawBuffer(nullptr), callerApplicationId, &spPurchasedOrderBody)",
                                    OrderBody,
                                    v22);
      LogPurchaseOrderBody(v24);
      if ( UriResponseWithAuthTicket >= 0 )
      {
        TickCount64 = GetTickCount64();
        v28 = 0;
        WindowsDeleteString(0);
        v28 = 0;
        UriResponseWithAuthTicket = FetchUriResponseWithAuthTicket(a5, v25, a2, v24, 2, 1, (__int64)a4, a1, &v28);
        if ( UriResponseWithAuthTicket >= 0 )
        {
          v27 = 0;
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v27);
          UriResponseWithAuthTicket = Json_Parse(v28, &v27);
          v17 = (int)v27;
          v18 = GetTickCount64();
          WindowsUpdate::CommonTelemetry::LogCompletePurchase(
            v25,
            a5,
            (struct TraceLoggingCorrelationVector *)(v18 - TickCount64),
            (unsigned int)UriResponseWithAuthTicket,
            v17,
            v23);
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v27);
        }
        WindowsDeleteString(v28);
      }
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v24);
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v25);
  }
  WindowsDeleteString(string);
  return (unsigned int)UriResponseWithAuthTicket;
}

```

## disassembly

```asm
0x18007ca8c  push    rbp
0x18007ca8e  push    rbx
0x18007ca8f  push    rsi
0x18007ca90  push    rdi
0x18007ca91  push    r12
0x18007ca93  push    r13
0x18007ca95  push    r14
0x18007ca97  push    r15
0x18007ca99  lea     rbp, [rsp-17h]
0x18007ca9e  sub     rsp, 0A8h
0x18007caa5  mov     rax, cs:__security_cookie
0x18007caac  xor     rax, rsp
0x18007caaf  mov     [rbp+4Fh+var_48], rax
0x18007cab3  mov     r15, r9
0x18007cab6  mov     rdi, r8
0x18007cab9  mov     r13, rdx
0x18007cabc  mov     r12, rcx
0x18007cabf  mov     rsi, [rbp+4Fh+arg_20]
0x18007cac3  xor     r14d, r14d
0x18007cac6  mov     [rbp+4Fh+string], r14
0x18007caca  mov     rax, [r8]
0x18007cacd  mov     rbx, [rax+50h]
0x18007cad1  xor     ecx, ecx; string
0x18007cad3  call    cs:__imp_WindowsDeleteString
0x18007cad9  mov     [rbp+4Fh+string], r14
0x18007cadd  mov     [rbp+4Fh+var_50], r14
0x18007cae1  lea     r9d, [r14+7]; unsigned int
0x18007cae5  lea     r8d, [r14+8]; unsigned int
0x18007cae9  lea     rdx, aOrderid_0; "orderId"
0x18007caf0  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x18007caf4  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007caf9  nop
0x18007cafa  lea     r8, [rbp+4Fh+string]
0x18007cafe  mov     rdx, [rbp+4Fh+var_50]
0x18007cb02  mov     rcx, rdi
0x18007cb05  mov     rax, rbx
0x18007cb08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cb0d  mov     [rsp+0E0h+var_C0], eax; int
0x18007cb11  lea     r9, aPorderGetnamed; "pOrder->GetNamedString(HStringReference"...
0x18007cb18  lea     rbx, aCompletepurcha_0; "CompletePurchaseOrder"
0x18007cb1f  mov     r8, rbx; char *
0x18007cb22  mov     edx, 10Eh; unsigned int
0x18007cb27  lea     rcx, aOnecoreuapEndu_44; "onecoreuap\\enduser\\winstore\\installs"...
0x18007cb2e  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x18007cb33  mov     edi, eax
0x18007cb35  test    eax, eax
0x18007cb37  js      loc_18007CCA6
0x18007cb3d  mov     [rbp+4Fh+var_88], r14
0x18007cb41  lea     rcx, [rbp+4Fh+var_88]
0x18007cb45  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007cb4a  xor     edx, edx; length
0x18007cb4c  mov     rcx, [rbp+4Fh+string]; string
0x18007cb50  call    cs:__imp_WindowsGetStringRawBuffer
0x18007cb56  lea     r8, [rbp+4Fh+var_88]; struct Windows::Foundation::IUriRuntimeClass **
0x18007cb5a  mov     rdx, rsi; struct TraceLoggingCorrelationVector *
0x18007cb5d  mov     rcx, rax; unsigned __int16 *
0x18007cb60  call    ?MakePurchaseOrderUri@@YAJPEBGPEAVTraceLoggingCorrelationVector@@PEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z; MakePurchaseOrderUri(ushort const *,TraceLoggingCorrelationVector *,Windows::Foundation::IUriRuntimeClass * *)
0x18007cb65  mov     [rsp+0E0h+var_C0], eax; int
0x18007cb69  lea     r9, aMakepurchaseor_0; "MakePurchaseOrderUri(strOrderId.GetRawB"...
0x18007cb70  mov     r8, rbx; char *
0x18007cb73  mov     edx, 112h; unsigned int
0x18007cb78  lea     rcx, aOnecoreuapEndu_44; "onecoreuap\\enduser\\winstore\\installs"...
0x18007cb7f  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x18007cb84  mov     edi, eax
0x18007cb86  test    eax, eax
0x18007cb88  js      loc_18007CC9C
0x18007cb8e  mov     [rbp+4Fh+var_90], r14
0x18007cb92  lea     rcx, [rbp+4Fh+var_90]
0x18007cb96  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007cb9b  xor     edx, edx; length
0x18007cb9d  mov     rcx, [rbp+4Fh+string]; string
0x18007cba1  call    cs:__imp_WindowsGetStringRawBuffer
0x18007cba7  lea     r8, [rbp+4Fh+var_90]; struct Windows::Data::Json::IJsonObject **
0x18007cbab  mov     rdx, r15; unsigned __int16 *
0x18007cbae  mov     rcx, rax; unsigned __int16 *
0x18007cbb1  call    ?CreateOrderBody@@YAJPEBG0PEAPEAUIJsonObject@Json@Data@Windows@@@Z; CreateOrderBody(ushort const *,ushort const *,Windows::Data::Json::IJsonObject * *)
0x18007cbb6  mov     [rsp+0E0h+var_C0], eax; int
0x18007cbba  lea     r9, aCreateorderbod_0; "CreateOrderBody(strOrderId.GetRawBuffer"...
0x18007cbc1  mov     r8, rbx; char *
0x18007cbc4  mov     edx, 116h; unsigned int
0x18007cbc9  lea     rcx, aOnecoreuapEndu_44; "onecoreuap\\enduser\\winstore\\installs"...
0x18007cbd0  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x18007cbd5  mov     edi, eax
0x18007cbd7  mov     rcx, [rbp+4Fh+var_90]; struct IInspectable *
0x18007cbdb  call    ?LogPurchaseOrderBody@@YAXPEAUIJsonObject@Json@Data@Windows@@@Z; LogPurchaseOrderBody(Windows::Data::Json::IJsonObject *)
0x18007cbe0  test    edi, edi
0x18007cbe2  js      loc_18007CC92
0x18007cbe8  call    cs:__imp_GetTickCount64
0x18007cbee  mov     r14, rax
0x18007cbf1  xor     ebx, ebx
0x18007cbf3  mov     [rbp+4Fh+var_70], rbx
0x18007cbf7  xor     ecx, ecx; string
0x18007cbf9  call    cs:__imp_WindowsDeleteString
0x18007cbff  mov     [rbp+4Fh+var_70], rbx
0x18007cc03  lea     rax, [rbp+4Fh+var_70]
0x18007cc07  mov     [rsp+0E0h+var_A0], rax
0x18007cc0c  mov     [rsp+0E0h+var_A8], r12
0x18007cc11  mov     [rsp+0E0h+var_B0], r15
0x18007cc16  mov     byte ptr [rsp+0E0h+var_B8], 1; struct Windows::Data::Json::IJsonObject *
0x18007cc1b  mov     [rsp+0E0h+var_C0], 2
0x18007cc23  mov     r9, [rbp+4Fh+var_90]
0x18007cc27  mov     r8, r13
0x18007cc2a  mov     rdx, [rbp+4Fh+var_88]
0x18007cc2e  mov     rcx, rsi
0x18007cc31  call    ?FetchUriResponseWithAuthTicket@@YAJPEAVTraceLoggingCorrelationVector@@PEAUIUriRuntimeClass@Foundation@Windows@@PEAUHSTRING__@@PEAUIJsonObject@Json@Data@4@W4Http_Verb@@_NPEBG6PEAPEAU5@@Z; FetchUriResponseWithAuthTicket(TraceLoggingCorrelationVector *,Windows::Foundation::IUriRuntimeClass *,HSTRING__ *,Windows::Data::Json::IJsonObject *,Http_Verb,bool,ushort const *,ushort const *,HSTRING__ * *)
0x18007cc36  mov     edi, eax
0x18007cc38  test    eax, eax
0x18007cc3a  js      short loc_18007CC87
0x18007cc3c  mov     [rbp+4Fh+var_78], rbx
0x18007cc40  lea     rcx, [rbp+4Fh+var_78]
0x18007cc44  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007cc49  lea     rdx, [rbp+4Fh+var_78]; struct Windows::Data::Json::IJsonObject **
0x18007cc4d  mov     rcx, [rbp+4Fh+var_70]; HSTRING
0x18007cc51  call    ?Json_Parse@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@Windows@@@Z; Json_Parse(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x18007cc56  mov     edi, eax
0x18007cc58  mov     rbx, [rbp+4Fh+var_78]
0x18007cc5c  call    cs:__imp_GetTickCount64
0x18007cc62  sub     rax, r14
0x18007cc65  mov     qword ptr [rsp+0E0h+var_C0], rbx; int
0x18007cc6a  mov     r9d, edi; unsigned __int64
0x18007cc6d  mov     r8, rax; struct TraceLoggingCorrelationVector *
0x18007cc70  mov     rdx, rsi; struct Windows::Foundation::IUriRuntimeClass *
0x18007cc73  mov     rcx, [rbp+4Fh+var_88]; this
0x18007cc77  call    ?LogCompletePurchase@CommonTelemetry@WindowsUpdate@@YAXPEAUIUriRuntimeClass@Foundation@Windows@@PEAVTraceLoggingCorrelationVector@@_KJPEAUIJsonObject@Json@Data@5@@Z; WindowsUpdate::CommonTelemetry::LogCompletePurchase(Windows::Foundation::IUriRuntimeClass *,TraceLoggingCorrelationVector *,unsigned __int64,long,Windows::Data::Json::IJsonObject *)
0x18007cc7c  nop
0x18007cc7d  lea     rcx, [rbp+4Fh+var_78]
0x18007cc81  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007cc86  nop
0x18007cc87  mov     rcx, [rbp+4Fh+var_70]; string
0x18007cc8b  call    cs:__imp_WindowsDeleteString
0x18007cc91  nop
0x18007cc92  lea     rcx, [rbp+4Fh+var_90]
0x18007cc96  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007cc9b  nop
0x18007cc9c  lea     rcx, [rbp+4Fh+var_88]
0x18007cca0  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007cca5  nop
0x18007cca6  mov     rcx, [rbp+4Fh+string]; string
0x18007ccaa  call    cs:__imp_WindowsDeleteString
0x18007ccb0  mov     eax, edi
0x18007ccb2  mov     rcx, [rbp+4Fh+var_48]
0x18007ccb6  xor     rcx, rsp; StackCookie
0x18007ccb9  call    __security_check_cookie
0x18007ccbe  add     rsp, 0A8h
0x18007ccc5  pop     r15
0x18007ccc7  pop     r14
0x18007ccc9  pop     r13
0x18007cccb  pop     r12
0x18007cccd  pop     rdi
0x18007ccce  pop     rsi
0x18007cccf  pop     rbx
0x18007ccd0  pop     rbp
0x18007ccd1  retn
```
