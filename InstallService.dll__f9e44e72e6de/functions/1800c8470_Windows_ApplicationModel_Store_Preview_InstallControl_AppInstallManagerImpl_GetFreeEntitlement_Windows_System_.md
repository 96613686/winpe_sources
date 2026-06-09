# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetFreeEntitlement(Windows::System::IUser *,HSTRING__ *,HSTRING__ *,uchar,HSTRING__ *,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::GetEntitlementResult *> * *)

- ea: `0x1800c8470`
- end: `0x1800c8856`
- name: `?_GetFreeEntitlement@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAJPEAUIUser@System@6@PEAUHSTRING__@@1E1PEAPEAU?$IAsyncOperation@PEAVGetEntitlementResult@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@6@@Z`
- size: `998`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800add00`
- `0x1800ae550`
- `0x1800ae590`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x18001c414`
- `0x180023a9c`
- `0x18002548c`
- `0x180028cd4`
- `0x180084280`
- `0x18008e1ac`
- `0x18008f9a4`
- `0x180092378`
- `0x180095ef8`
- `0x1800c8470`
- `0x1801143a0`
- `0x180117d4c`
- `0x1801473f4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c85a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c85ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c85ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c8767`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c8800`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c880a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c8814`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c85a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c85ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c85ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c8767`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c8800`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c880a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c8814`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c8675`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c8675`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c8502`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c8510`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c8784`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c8792`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c8502`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c8510`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c8784`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c8792`

## string_xrefs

- `0x1800c8559`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c87e0`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c854c`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetFreeEntitlement`
- `0x1800c87d3`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetFreeEntitlement`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetFreeEntitlement(
        HSTRING a1,
        __int64 a2,
        char *a3,
        HSTRING a4,
        HSTRING a5,
        WindowsUpdate::CommonTelemetry *a6,
        _QWORD *a7)
{
  WindowsUpdate::CommonTelemetry *v9; // rcx
  HSTRING v10; // rsi
  HSTRING v11; // r8
  const unsigned __int16 *v12; // r13
  HSTRING v13; // r8
  HRESULT v14; // r15d
  HSTRING v15; // rbx
  HSTRING v16; // rdi
  int v17; // r15d
  __int64 v18; // rax
  __int64 v19; // r8
  PCWSTR StringRawBuffer; // r14
  PCWSTR v21; // rax
  unsigned int v22; // edx
  const char *v24; // [rsp+20h] [rbp-E0h]
  char *v25; // [rsp+30h] [rbp-D0h]
  int v26; // [rsp+38h] [rbp-C8h]
  __int64 v27; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v28; // [rsp+68h] [rbp-98h] BYREF
  __int64 v29; // [rsp+70h] [rbp-90h] BYREF
  HSTRING v30; // [rsp+78h] [rbp-88h] BYREF
  HSTRING v31; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v32; // [rsp+88h] [rbp-78h] BYREF
  HSTRING newString; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v34[2]; // [rsp+98h] [rbp-68h] BYREF
  TraceLoggingCorrelationVector *v35; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v36; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v37; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING v38; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v39; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING v40; // [rsp+D0h] [rbp-30h]
  _QWORD *v41; // [rsp+D8h] [rbp-28h]
  _BYTE v42[64]; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING__ v43; // [rsp+120h] [rbp+20h] BYREF

  v34[0] = a2;
  v40 = a1;
  v9 = a6;
  v41 = a7;
  v10 = 0;
  *a7 = 0;
  WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(v9, &v43, a3);
  LOBYTE(v11) = (_BYTE)a5;
  WindowsUpdate::Telemetry::BeginGetFreeEntitlement((HSTRING)a3, a4, v11, (unsigned __int8)&v43, v24);
  v12 = L"true";
  WindowsGetStringRawBuffer(a4, 0);
  WindowsGetStringRawBuffer((HSTRING)a3, 0);
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
    0xD44u,
    "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetFreeEntitlement",
    -1,
    L"Request: storeId = %s, campaignId = %s, useDeviceId = %s, CV = %hs",
    0,
    0);
  v35 = TraceLoggingCorrelationVector::Extend((const char *)&v43, 0);
  v14 = v35 == 0 ? 0x8007000E : 0;
  v15 = 0;
  v30 = 0;
  v16 = 0;
  v31 = 0;
  v32 = 0;
  if ( v35 )
  {
    WindowsDeleteString(0);
    v32 = 0;
    WindowsDeleteString(0);
    v31 = 0;
    WindowsDeleteString(0);
    v30 = 0;
    v14 = AppId::SplitStoreId((HSTRING)a3, &v30, &v31, &v32);
    v15 = v30;
    v16 = v31;
    v10 = v32;
  }
  v29 = 0;
  if ( v14 >= 0 )
  {
    v28 = v10;
    v36 = 0;
    v37 = 0;
    v38 = v16;
    LODWORD(v27) = 0;
    v39 = v15;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v29);
    v14 = Microsoft::WRL::Details::MakeAndInitialize<AppId,AppId,HSTRING__ *,enum AppId::Type,HSTRING__ *,std::nullptr_t,std::nullptr_t,HSTRING__ *>(
            (unsigned int)&v29,
            (unsigned int)&v39,
            (unsigned int)&v27,
            (unsigned int)&v38,
            (__int64)&v37,
            (__int64)&v36,
            (__int64)&v28);
  }
  newString = 0;
  if ( v14 < 0 )
    goto LABEL_8;
  v14 = WindowsDuplicateString(a4, &newString);
  if ( v14 < 0 )
    goto LABEL_8;
  v17 = (int)v40;
  v28 = v40;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&v28);
  v27 = v34[0];
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&v27);
  v18 = lambda_c606bd4078877996c9c45a4c1c7a5640_::_lambda_c606bd4078877996c9c45a4c1c7a5640_(
          (unsigned int)v42,
          v17,
          (unsigned int)&v28,
          (unsigned int)&v27,
          (__int64)&v29,
          (__int64)&newString,
          (__int64)&a5,
          (__int64)&v35);
  LODWORD(v34[0]) = 0;
  *(_QWORD *)((char *)v34 + 4) = 128;
  v14 = Windows::Internal::MakeAsyncOperation_Windows::Internal::CMarshaledInterfaceResult_Windows::ApplicationModel::Store::Preview::InstallControl::IGetEntitlementResult__Windows::ApplicationModel::Store::Preview::InstallControl::GetEntitlementResult___Windows::Internal::ComTaskPoolHandler__lambda_c606bd4078877996c9c45a4c1c7a5640___(
          v34,
          v41,
          v19,
          v18);
  lambda_c606bd4078877996c9c45a4c1c7a5640_::__lambda_c606bd4078877996c9c45a4c1c7a5640_(v42);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v27);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v28);
  if ( v14 < 0 )
  {
LABEL_8:
    LODWORD(v25) = v14;
    LOBYTE(v13) = (_BYTE)a5;
    WindowsUpdate::Telemetry::EndGetFreeEntitlement((HSTRING)a3, a4, v13, 0, 0, &v43, v25, v26);
    WindowsDeleteString(newString);
    if ( !(_BYTE)a5 )
      v12 = L"false";
    StringRawBuffer = WindowsGetStringRawBuffer(a4, 0);
    v21 = WindowsGetStringRawBuffer((HSTRING)a3, 0);
    LogMessage(
      1u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      0xDDDu,
      "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetFreeEntitlement",
      v14,
      L"Failed: storeId = %s, campaignId = %s, useDeviceId = %s, CV = %hs",
      0,
      0,
      v21,
      StringRawBuffer,
      v12,
      &v43);
  }
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v29);
  WindowsDeleteString(v10);
  WindowsDeleteString(v16);
  WindowsDeleteString(v15);
  if ( v35 )
    TraceLoggingCorrelationVector::`scalar deleting destructor'(v35, v22);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800c8470  mov     [rsp-8+arg_8], rbx
0x1800c8475  push    rbp
0x1800c8476  push    rsi
0x1800c8477  push    rdi
0x1800c8478  push    r12
0x1800c847a  push    r13
0x1800c847c  push    r14
0x1800c847e  push    r15
0x1800c8480  lea     rbp, [rsp-0C0h]
0x1800c8488  sub     rsp, 1C0h
0x1800c848f  mov     rax, cs:__security_cookie
0x1800c8496  xor     rax, rsp
0x1800c8499  mov     [rbp+0F0h+var_40], rax
0x1800c84a0  mov     r14, r9
0x1800c84a3  mov     r12, r8
0x1800c84a6  mov     qword ptr [rbp+0F0h+var_158], rdx
0x1800c84aa  mov     [rbp+0F0h+var_120], rcx
0x1800c84ae  mov     rcx, [rbp+0F0h+arg_28]; this
0x1800c84b5  mov     rax, [rbp+0F0h+arg_30]
0x1800c84bc  mov     [rbp+0F0h+var_118], rax
0x1800c84c0  xor     esi, esi
0x1800c84c2  mov     [rax], rsi
0x1800c84c5  lea     rdx, [rbp+0F0h+var_D0]; HSTRING
0x1800c84c9  call    ?GenerateIfMissingCorrelationVector@CommonTelemetry@WindowsUpdate@@YAXPEAUHSTRING__@@QEAD@Z; WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(HSTRING__ *,char * const)
0x1800c84ce  lea     r9, [rbp+0F0h+var_D0]; unsigned __int8
0x1800c84d2  mov     bl, byte ptr [rbp+0F0h+arg_20]
0x1800c84d8  mov     r8b, bl; HSTRING
0x1800c84db  mov     rdx, r14; HSTRING
0x1800c84de  mov     rcx, r12; string
0x1800c84e1  call    ?BeginGetFreeEntitlement@Telemetry@WindowsUpdate@@YAXPEAUHSTRING__@@0EPEBD@Z; WindowsUpdate::Telemetry::BeginGetFreeEntitlement(HSTRING__ *,HSTRING__ *,uchar,char const *)
0x1800c84e6  lea     r13, aTrue; "true"
0x1800c84ed  mov     rdi, r13
0x1800c84f0  lea     rax, aFalse_0; "false"
0x1800c84f7  test    bl, bl
0x1800c84f9  cmovz   rdi, rax
0x1800c84fd  xor     edx, edx; length
0x1800c84ff  mov     rcx, r14; string
0x1800c8502  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c8508  mov     rbx, rax
0x1800c850b  xor     edx, edx; length
0x1800c850d  mov     rcx, r12; string
0x1800c8510  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c8516  lea     rcx, [rbp+0F0h+var_D0]
0x1800c851a  mov     [rsp+1F0h+var_198], rcx
0x1800c851f  mov     [rsp+1F0h+var_1A0], rdi
0x1800c8524  mov     [rsp+1F0h+var_1A8], rbx
0x1800c8529  mov     [rsp+1F0h+var_1B0], rax
0x1800c852e  mov     [rsp+1F0h+var_1B8], rsi; unsigned __int16 *
0x1800c8533  mov     [rsp+1F0h+var_1C0], rsi; char *
0x1800c8538  lea     rax, aRequestStoreid; "Request: storeId = %s, campaignId = %s,"...
0x1800c853f  mov     [rsp+1F0h+var_1C8], rax; unsigned __int16 *
0x1800c8544  mov     dword ptr [rsp+1F0h+var_1D0], 0FFFFFFFFh; int
0x1800c854c  lea     r9, aWindowsApplica_133; "Windows::ApplicationModel::Store::Previ"...
0x1800c8553  mov     r8d, 0D44h; unsigned int
0x1800c8559  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c8560  lea     ecx, [rsi+3]; unsigned int
0x1800c8563  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800c8568  xor     edx, edx; bool
0x1800c856a  lea     rcx, [rbp+0F0h+var_D0]; char *
0x1800c856e  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x1800c8573  mov     [rbp+0F0h+var_148], rax
0x1800c8577  test    rax, rax
0x1800c857a  setz    cl
0x1800c857d  mov     al, cl
0x1800c857f  neg     al
0x1800c8581  sbb     r15d, r15d
0x1800c8584  and     r15d, 8007000Eh
0x1800c858b  mov     ebx, esi
0x1800c858d  mov     [rsp+1F0h+var_178], rbx
0x1800c8592  mov     edi, esi
0x1800c8594  mov     [rbp+0F0h+var_170], rsi
0x1800c8598  mov     [rbp+0F0h+var_168], rsi
0x1800c859c  test    cl, cl
0x1800c859e  jnz     short loc_1800C85EA
0x1800c85a0  xor     ecx, ecx; string
0x1800c85a2  call    cs:__imp_WindowsDeleteString
0x1800c85a8  mov     [rbp+0F0h+var_168], rbx
0x1800c85ac  xor     ecx, ecx; string
0x1800c85ae  call    cs:__imp_WindowsDeleteString
0x1800c85b4  mov     [rbp+0F0h+var_170], rbx
0x1800c85b8  xor     ecx, ecx; string
0x1800c85ba  call    cs:__imp_WindowsDeleteString
0x1800c85c0  mov     [rsp+1F0h+var_178], rbx
0x1800c85c5  lea     r9, [rbp+0F0h+var_168]; HSTRING *
0x1800c85c9  lea     r8, [rbp+0F0h+var_170]; HSTRING *
0x1800c85cd  lea     rdx, [rsp+1F0h+var_178]; HSTRING *
0x1800c85d2  mov     rcx, r12; HSTRING
0x1800c85d5  call    ?SplitStoreId@AppId@@SAJPEAUHSTRING__@@PEAPEAU2@11@Z; AppId::SplitStoreId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)
0x1800c85da  mov     r15d, eax
0x1800c85dd  mov     rbx, [rsp+1F0h+var_178]
0x1800c85e2  mov     rdi, [rbp+0F0h+var_170]
0x1800c85e6  mov     rsi, [rbp+0F0h+var_168]
0x1800c85ea  mov     [rsp+1F0h+var_180], 0
0x1800c85f3  test    r15d, r15d
0x1800c85f6  js      short loc_1800C865D
0x1800c85f8  mov     [rsp+1F0h+var_188], rsi
0x1800c85fd  mov     [rbp+0F0h+var_140], 0
0x1800c8605  mov     [rbp+0F0h+var_138], 0
0x1800c860d  mov     [rbp+0F0h+var_130], rdi
0x1800c8611  mov     dword ptr [rsp+1F0h+var_190], 0
0x1800c8619  mov     [rbp+0F0h+var_128], rbx
0x1800c861d  lea     rcx, [rsp+1F0h+var_180]
0x1800c8622  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c8627  lea     rax, [rsp+1F0h+var_188]
0x1800c862c  mov     [rsp+1F0h+var_1C0], rax
0x1800c8631  lea     rax, [rbp+0F0h+var_140]
0x1800c8635  mov     [rsp+1F0h+var_1C8], rax
0x1800c863a  lea     rax, [rbp+0F0h+var_138]
0x1800c863e  mov     [rsp+1F0h+var_1D0], rax
0x1800c8643  lea     r9, [rbp+0F0h+var_130]
0x1800c8647  lea     r8, [rsp+1F0h+var_190]
0x1800c864c  lea     rdx, [rbp+0F0h+var_128]
0x1800c8650  lea     rcx, [rsp+1F0h+var_180]
0x1800c8655  call    ??$MakeAndInitialize@VAppId@@V1@PEAUHSTRING__@@W4Type@1@PEAU2@$$T$$TPEAU2@@Details@WRL@Microsoft@@YAJPEAPEAVAppId@@$$QEAPEAUHSTRING__@@$$QEAW4Type@3@1$$QEA$$T31@Z
0x1800c865a  mov     r15d, eax
0x1800c865d  mov     [rbp+0F0h+newString], 0
0x1800c8665  test    r15d, r15d
0x1800c8668  js      loc_1800C8737
0x1800c866e  lea     rdx, [rbp+0F0h+newString]; newString
0x1800c8672  mov     rcx, r14; string
0x1800c8675  call    cs:__imp_WindowsDuplicateString
0x1800c867b  mov     r15d, eax
0x1800c867e  test    eax, eax
0x1800c8680  js      loc_1800C8737
0x1800c8686  mov     r15, [rbp+0F0h+var_120]
0x1800c868a  mov     [rsp+1F0h+var_188], r15
0x1800c868f  lea     rcx, [rsp+1F0h+var_188]
0x1800c8694  call    ?InternalAddRef@?$ComPtr@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(void)
0x1800c8699  nop
0x1800c869a  mov     rax, qword ptr [rbp+0F0h+var_158]
0x1800c869e  mov     [rsp+1F0h+var_190], rax
0x1800c86a3  lea     rcx, [rsp+1F0h+var_190]
0x1800c86a8  call    ?InternalAddRef@?$ComPtr@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(void)
0x1800c86ad  nop
0x1800c86ae  lea     rax, [rbp+0F0h+var_148]
0x1800c86b2  mov     [rsp+1F0h+var_1B8], rax; int
0x1800c86b7  lea     rax, [rbp+0F0h+arg_20]
0x1800c86be  mov     [rsp+1F0h+var_1C0], rax
0x1800c86c3  lea     rax, [rbp+0F0h+newString]
0x1800c86c7  mov     [rsp+1F0h+var_1C8], rax
0x1800c86cc  lea     rax, [rsp+1F0h+var_180]
0x1800c86d1  mov     [rsp+1F0h+var_1D0], rax
0x1800c86d6  lea     r9, [rsp+1F0h+var_190]
0x1800c86db  lea     r8, [rsp+1F0h+var_188]
0x1800c86e0  mov     rdx, r15
0x1800c86e3  lea     rcx, [rbp+0F0h+var_110]
0x1800c86e7  call    _lambda_c606bd4078877996c9c45a4c1c7a5640____lambda_c606bd4078877996c9c45a4c1c7a5640_
0x1800c86ec  nop
0x1800c86ed  mov     dword ptr [rbp+0F0h+var_158], 0
0x1800c86f4  mov     qword ptr [rbp+0F0h+var_158+4], 80h
0x1800c86fc  mov     r9, rax
0x1800c86ff  mov     rdx, [rbp+0F0h+var_118]
0x1800c8703  lea     rcx, [rbp+0F0h+var_158]
0x1800c8707  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CMarshaledInterfaceResult_Windows__ApplicationModel__Store__Preview__InstallControl__IGetEntitlementResult__Windows__ApplicationModel__Store__Preview__InstallControl__GetEntitlementResult___Windows__Internal__ComTaskPoolHandler__lambda_c606bd4078877996c9c45a4c1c7a5640___
0x1800c870c  mov     r15d, eax
0x1800c870f  lea     rcx, [rbp+0F0h+var_110]
0x1800c8713  call    _lambda_c606bd4078877996c9c45a4c1c7a5640_____lambda_c606bd4078877996c9c45a4c1c7a5640_
0x1800c8718  nop
0x1800c8719  lea     rcx, [rsp+1F0h+var_190]
0x1800c871e  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c8723  nop
0x1800c8724  lea     rcx, [rsp+1F0h+var_188]
0x1800c8729  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c872e  test    r15d, r15d
0x1800c8731  jns     loc_1800C87F2
0x1800c8737  mov     dword ptr [rsp+1F0h+var_1C0], r15d; char *
0x1800c873c  lea     rax, [rbp+0F0h+var_D0]
0x1800c8740  mov     [rsp+1F0h+var_1C8], rax; HSTRING
0x1800c8745  mov     [rsp+1F0h+var_1D0], 0; HSTRING
0x1800c874e  xor     r9d, r9d; unsigned __int8
0x1800c8751  mov     r8b, byte ptr [rbp+0F0h+arg_20]; HSTRING
0x1800c8758  mov     rdx, r14; HSTRING
0x1800c875b  mov     rcx, r12; string
0x1800c875e  call    ?EndGetFreeEntitlement@Telemetry@WindowsUpdate@@YAXPEAUHSTRING__@@0EE0PEBDJ@Z; WindowsUpdate::Telemetry::EndGetFreeEntitlement(HSTRING__ *,HSTRING__ *,uchar,uchar,HSTRING__ *,char const *,long)
0x1800c8763  mov     rcx, [rbp+0F0h+newString]; string
0x1800c8767  call    cs:__imp_WindowsDeleteString
0x1800c876d  cmp     byte ptr [rbp+0F0h+arg_20], 0
0x1800c8774  lea     rax, aFalse_0; "false"
0x1800c877b  cmovz   r13, rax
0x1800c877f  xor     edx, edx; length
0x1800c8781  mov     rcx, r14; string
0x1800c8784  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c878a  mov     r14, rax
0x1800c878d  xor     edx, edx; length
0x1800c878f  mov     rcx, r12; string
0x1800c8792  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c8798  lea     rcx, [rbp+0F0h+var_D0]
0x1800c879c  mov     [rsp+1F0h+var_198], rcx
0x1800c87a1  mov     [rsp+1F0h+var_1A0], r13
0x1800c87a6  mov     [rsp+1F0h+var_1A8], r14
0x1800c87ab  mov     [rsp+1F0h+var_1B0], rax
0x1800c87b0  mov     [rsp+1F0h+var_1B8], 0; unsigned __int16 *
0x1800c87b9  mov     [rsp+1F0h+var_1C0], 0; char *
0x1800c87c2  lea     rax, aFailedStoreidS; "Failed: storeId = %s, campaignId = %s, "...
0x1800c87c9  mov     [rsp+1F0h+var_1C8], rax; unsigned __int16 *
0x1800c87ce  mov     dword ptr [rsp+1F0h+var_1D0], r15d; int
0x1800c87d3  lea     r9, aWindowsApplica_133; "Windows::ApplicationModel::Store::Previ"...
0x1800c87da  mov     r8d, 0DDDh; unsigned int
0x1800c87e0  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c87e7  mov     ecx, 1; unsigned int
0x1800c87ec  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800c87f1  nop
0x1800c87f2  lea     rcx, [rsp+1F0h+var_180]
0x1800c87f7  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c87fc  nop
0x1800c87fd  mov     rcx, rsi; string
0x1800c8800  call    cs:__imp_WindowsDeleteString
0x1800c8806  nop
0x1800c8807  mov     rcx, rdi; string
0x1800c880a  call    cs:__imp_WindowsDeleteString
0x1800c8810  nop
0x1800c8811  mov     rcx, rbx; string
0x1800c8814  call    cs:__imp_WindowsDeleteString
0x1800c881a  nop
0x1800c881b  mov     rcx, [rbp+0F0h+var_148]; this
0x1800c881f  test    rcx, rcx
0x1800c8822  jz      short loc_1800C8829
0x1800c8824  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x1800c8829  mov     eax, r15d
0x1800c882c  mov     rcx, [rbp+0F0h+var_40]
0x1800c8833  xor     rcx, rsp; StackCookie
0x1800c8836  call    __security_check_cookie
0x1800c883b  mov     rbx, [rsp+1F0h+arg_8]
0x1800c8843  add     rsp, 1C0h
0x1800c884a  pop     r15
0x1800c884c  pop     r14
0x1800c884e  pop     r13
0x1800c8850  pop     r12
0x1800c8852  pop     rdi
0x1800c8853  pop     rsi
0x1800c8854  pop     rbp
0x1800c8855  retn
```
