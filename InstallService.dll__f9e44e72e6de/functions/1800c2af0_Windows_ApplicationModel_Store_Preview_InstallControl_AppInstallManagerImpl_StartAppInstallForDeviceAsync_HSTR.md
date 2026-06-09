# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppInstallForDeviceAsync(HSTRING__ *,HSTRING__ *,uchar,uchar,HSTRING__ *,HSTRING__ *,Windows::Management::Deployment::IPackageVolume *,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> * *)

- ea: `0x1800c2af0`
- end: `0x1800c2dec`
- name: `?StartAppInstallForDeviceAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@UEAAJPEAUHSTRING__@@0EE00PEAUIPackageVolume@Deployment@Management@6@PEAPEAU?$IAsyncOperation@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@6@@Z`
- size: `764`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180010b74`
- `0x18001c414`
- `0x18002548c`
- `0x180028cd4`
- `0x18002d98c`
- `0x18002ec2c`
- `0x18003b08c`
- `0x1800865d4`
- `0x18008e7c4`
- `0x18008f940`
- `0x1800926dc`
- `0x180096074`
- `0x1800c2af0`
- `0x1801473f4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2b73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2bba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2da8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2b73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2bba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2da8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c2c12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c2c20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c2c2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c2c12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c2c20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c2c2e`

## string_xrefs

- `0x1800c2ba3`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c2c7d`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c2d53`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c2b83`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppInstallForDeviceAsync`
- `0x1800c2c70`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppInstallForDeviceAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppInstallForDeviceAsync(
        __int64 a1,
        HSTRING a2,
        HSTRING a3,
        char a4,
        char a5,
        HSTRING a6,
        WindowsUpdate::CommonTelemetry *a7,
        __int64 a8,
        _QWORD *a9)
{
  HSTRING v12; // rsi
  WindowsUpdate::CommonTelemetry *v13; // rdi
  _QWORD *v14; // r12
  int CallingProcessAndFunction; // eax
  char *v16; // r8
  unsigned int v17; // ebx
  struct TraceLoggingCorrelationVector *v19; // rax
  PCWSTR StringRawBuffer; // rdi
  PCWSTR v21; // rbx
  PCWSTR v22; // rax
  __int64 v23; // rax
  __int64 v24; // r8
  int v25; // eax
  int v26; // [rsp+20h] [rbp-1A8h]
  int v27; // [rsp+20h] [rbp-1A8h]
  __int64 v28; // [rsp+60h] [rbp-168h] BYREF
  __int64 v29; // [rsp+68h] [rbp-160h] BYREF
  HSTRING string; // [rsp+70h] [rbp-158h] BYREF
  _BYTE v31[12]; // [rsp+78h] [rbp-150h] BYREF
  __int64 v32; // [rsp+88h] [rbp-140h] BYREF
  _BYTE v33[8]; // [rsp+90h] [rbp-138h] BYREF
  HSTRING v34; // [rsp+98h] [rbp-130h] BYREF
  _BYTE v35[8]; // [rsp+A0h] [rbp-128h] BYREF
  std::_Ref_count_base *v36; // [rsp+A8h] [rbp-120h]
  _BYTE v37[64]; // [rsp+B0h] [rbp-118h] BYREF
  HSTRING__ v38; // [rsp+F0h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  *(_QWORD *)v31 = a2;
  v34 = a3;
  LOBYTE(v28) = a4;
  v12 = a6;
  v13 = a7;
  v14 = a9;
  *a9 = 0;
  v32 = a8;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&v32);
  WindowsDeleteString(0);
  string = 0;
  CallingProcessAndFunction = GetCallingProcessAndFunction(
                                v12,
                                L"Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartA"
                                 "ppInstallForDeviceAsync",
                                &string);
  v17 = CallingProcessAndFunction;
  if ( CallingProcessAndFunction >= 0 )
  {
    WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(v13, &v38, v16);
    v19 = TraceLoggingCorrelationVector::Extend((const char *)&v38, 0);
    std::shared_ptr<TraceLoggingCorrelationVector>::shared_ptr<TraceLoggingCorrelationVector>(v35, v19);
    StringRawBuffer = WindowsGetStringRawBuffer(v12, 0);
    v21 = WindowsGetStringRawBuffer(a3, 0);
    v22 = WindowsGetStringRawBuffer(a2, 0);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      0x1999u,
      "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppInstallForDeviceAsync",
      -1,
      L"request: productId = %s, skuId = %s, clientId = %s, CV = %hs",
      0,
      0,
      v22,
      v21,
      StringRawBuffer,
      &v38,
      v28);
    LODWORD(v29) = 0;
    wil::MakeAndInitializeOrThrow<AppId,HSTRING__ * &,enum AppId::Type,HSTRING__ * &>(v33, v31, &v29, &v34);
    *(_QWORD *)v31 = string;
    v29 = a1 - 104;
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&v29);
    v23 = lambda_ff3919bc47410d386a3a684a501fa3a6_::_lambda_ff3919bc47410d386a3a684a501fa3a6_(
            (unsigned int)v37,
            (int)a1 - 104,
            (unsigned int)&v29,
            (unsigned int)v33,
            (__int64)&v28,
            (__int64)&a5,
            (__int64)&v32,
            (__int64)v31,
            (__int64)v35);
    *(_DWORD *)v31 = 0;
    *(_QWORD *)&v31[4] = 128;
    v25 = Windows::Internal::MakeAsyncOperation_Windows::Internal::CMarshaledInterfaceResult_Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem__Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem___Windows::Internal::ComTaskPoolHandler__lambda_ff3919bc47410d386a3a684a501fa3a6___(
            v31,
            v14,
            v24,
            v23);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x19EE,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
        (const char *)(unsigned int)v25,
        v27);
    lambda_ff3919bc47410d386a3a684a501fa3a6_::__lambda_ff3919bc47410d386a3a684a501fa3a6_(v37);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v29);
    string = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v33);
    if ( v36 )
      std::_Ref_count_base::_Decref(v36);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1992,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)CallingProcessAndFunction,
      v26);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
    return v17;
  }
}

```

## disassembly

```asm
0x1800c2af0  push    rbx
0x1800c2af2  push    rsi
0x1800c2af3  push    rdi
0x1800c2af4  push    r12
0x1800c2af6  push    r13
0x1800c2af8  push    r14
0x1800c2afa  push    r15
0x1800c2afc  sub     rsp, 190h
0x1800c2b03  mov     rax, cs:__security_cookie
0x1800c2b0a  xor     rax, rsp
0x1800c2b0d  mov     [rsp+1C8h+var_48], rax
0x1800c2b15  mov     r15, r8
0x1800c2b18  mov     r14, rdx
0x1800c2b1b  mov     r13, rcx
0x1800c2b1e  mov     [rsp+1C8h+var_150], rdx
0x1800c2b23  mov     [rsp+1C8h+var_130], r8
0x1800c2b2b  mov     byte ptr [rsp+1C8h+var_168], r9b
0x1800c2b30  mov     rsi, [rsp+1C8h+arg_28]
0x1800c2b38  mov     rdi, [rsp+1C8h+arg_30]
0x1800c2b40  mov     r12, [rsp+1C8h+arg_40]
0x1800c2b48  xor     ebx, ebx
0x1800c2b4a  mov     [r12], rbx
0x1800c2b4e  mov     rax, [rsp+1C8h+arg_38]
0x1800c2b56  mov     [rsp+1C8h+var_140], rax
0x1800c2b5e  lea     rcx, [rsp+1C8h+var_140]
0x1800c2b66  call    ?InternalAddRef@?$ComPtr@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(void)
0x1800c2b6b  nop
0x1800c2b6c  mov     [rsp+1C8h+string], rbx
0x1800c2b71  xor     ecx, ecx; string
0x1800c2b73  call    cs:__imp_WindowsDeleteString
0x1800c2b79  mov     [rsp+1C8h+string], rbx
0x1800c2b7e  lea     r8, [rsp+1C8h+string]; HSTRING *
0x1800c2b83  lea     rdx, aWindowsApplica_109; "Windows::ApplicationModel::Store::Previ"...
0x1800c2b8a  mov     rcx, rsi; HSTRING
0x1800c2b8d  call    ?GetCallingProcessAndFunction@@YAJPEAUHSTRING__@@PEBGPEAPEAU1@@Z; GetCallingProcessAndFunction(HSTRING__ *,ushort const *,HSTRING__ * *)
0x1800c2b92  mov     ebx, eax
0x1800c2b94  test    eax, eax
0x1800c2b96  jns     short loc_1800C2BDD
0x1800c2b98  mov     rcx, [rsp+1C8h]; this
0x1800c2ba0  mov     r9d, eax; char *
0x1800c2ba3  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c2baa  mov     edx, 1992h; void *
0x1800c2baf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c2bb4  nop
0x1800c2bb5  mov     rcx, [rsp+1C8h+string]; string
0x1800c2bba  call    cs:__imp_WindowsDeleteString
0x1800c2bc0  mov     [rsp+1C8h+string], 0
0x1800c2bc9  lea     rcx, [rsp+1C8h+var_140]
0x1800c2bd1  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c2bd6  mov     eax, ebx
0x1800c2bd8  jmp     loc_1800C2DC8
0x1800c2bdd  lea     rdx, [rsp+1C8h+var_D8]; HSTRING
0x1800c2be5  mov     rcx, rdi; this
0x1800c2be8  call    ?GenerateIfMissingCorrelationVector@CommonTelemetry@WindowsUpdate@@YAXPEAUHSTRING__@@QEAD@Z; WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(HSTRING__ *,char * const)
0x1800c2bed  xor     edx, edx; bool
0x1800c2bef  lea     rcx, [rsp+1C8h+var_D8]; char *
0x1800c2bf7  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x1800c2bfc  mov     rdx, rax
0x1800c2bff  lea     rcx, [rsp+1C8h+var_128]
0x1800c2c07  call    ??$?0VTraceLoggingCorrelationVector@@$0A@@?$shared_ptr@VTraceLoggingCorrelationVector@@@std@@QEAA@PEAVTraceLoggingCorrelationVector@@@Z; std::shared_ptr<TraceLoggingCorrelationVector>::shared_ptr<TraceLoggingCorrelationVector>(TraceLoggingCorrelationVector *)
0x1800c2c0c  nop
0x1800c2c0d  xor     edx, edx; length
0x1800c2c0f  mov     rcx, rsi; string
0x1800c2c12  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c2c18  mov     rdi, rax
0x1800c2c1b  xor     edx, edx; length
0x1800c2c1d  mov     rcx, r15; string
0x1800c2c20  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c2c26  mov     rbx, rax
0x1800c2c29  xor     edx, edx; length
0x1800c2c2b  mov     rcx, r14; string
0x1800c2c2e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c2c34  lea     rcx, [rsp+1C8h+var_D8]
0x1800c2c3c  mov     [rsp+1C8h+var_170], rcx
0x1800c2c41  mov     [rsp+1C8h+var_178], rdi
0x1800c2c46  mov     [rsp+1C8h+var_180], rbx
0x1800c2c4b  mov     [rsp+1C8h+var_188], rax
0x1800c2c50  xor     edi, edi
0x1800c2c52  mov     [rsp+1C8h+var_190], rdi; unsigned __int16 *
0x1800c2c57  mov     [rsp+1C8h+var_198], rdi; char *
0x1800c2c5c  lea     rax, aRequestProduct_9; "request: productId = %s, skuId = %s, cl"...
0x1800c2c63  mov     [rsp+1C8h+var_1A0], rax; unsigned __int16 *
0x1800c2c68  mov     [rsp+1C8h+var_1A8], 0FFFFFFFFh; int
0x1800c2c70  lea     r9, aWindowsApplica_152; "Windows::ApplicationModel::Store::Previ"...
0x1800c2c77  mov     r8d, 1999h; unsigned int
0x1800c2c7d  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c2c84  lea     ecx, [rdi+3]; unsigned int
0x1800c2c87  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800c2c8c  mov     dword ptr [rsp+1C8h+var_160], edi
0x1800c2c90  lea     r9, [rsp+1C8h+var_130]
0x1800c2c98  lea     r8, [rsp+1C8h+var_160]
0x1800c2c9d  lea     rdx, [rsp+1C8h+var_150]
0x1800c2ca2  lea     rcx, [rsp+1C8h+var_138]
0x1800c2caa  call    ??$MakeAndInitializeOrThrow@VAppId@@AEAPEAUHSTRING__@@W4Type@1@AEAPEAU2@@wil@@YA?AV?$ComPtr@VAppId@@@WRL@Microsoft@@AEAPEAUHSTRING__@@$$QEAW4Type@AppId@@0@Z; wil::MakeAndInitializeOrThrow<AppId,HSTRING__ * &,AppId::Type,HSTRING__ * &>(HSTRING__ * &,AppId::Type &&,HSTRING__ * &)
0x1800c2caf  nop
0x1800c2cb0  mov     rax, [rsp+1C8h+string]
0x1800c2cb5  mov     [rsp+1C8h+var_150], rax
0x1800c2cba  lea     rbx, [r13-68h]
0x1800c2cbe  mov     [rsp+1C8h+var_160], rbx
0x1800c2cc3  lea     rcx, [rsp+1C8h+var_160]
0x1800c2cc8  call    ?InternalAddRef@?$ComPtr@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(void)
0x1800c2ccd  nop
0x1800c2cce  lea     rax, [rsp+1C8h+var_128]
0x1800c2cd6  mov     [rsp+1C8h+var_188], rax
0x1800c2cdb  lea     rax, [rsp+1C8h+var_150]
0x1800c2ce0  mov     [rsp+1C8h+var_190], rax
0x1800c2ce5  lea     rax, [rsp+1C8h+var_140]
0x1800c2ced  mov     [rsp+1C8h+var_198], rax
0x1800c2cf2  lea     rax, [rsp+1C8h+arg_20]
0x1800c2cfa  mov     [rsp+1C8h+var_1A0], rax
0x1800c2cff  lea     rax, [rsp+1C8h+var_168]
0x1800c2d04  mov     qword ptr [rsp+1C8h+var_1A8], rax; int
0x1800c2d09  lea     r9, [rsp+1C8h+var_138]
0x1800c2d11  lea     r8, [rsp+1C8h+var_160]
0x1800c2d16  mov     rdx, rbx
0x1800c2d19  lea     rcx, [rsp+1C8h+var_118]
0x1800c2d21  call    _lambda_ff3919bc47410d386a3a684a501fa3a6____lambda_ff3919bc47410d386a3a684a501fa3a6_
0x1800c2d26  nop
0x1800c2d27  mov     dword ptr [rsp+1C8h+var_150], edi
0x1800c2d2b  mov     [rsp+1C8h+var_150+4], 80h
0x1800c2d34  mov     r9, rax
0x1800c2d37  mov     rdx, r12
0x1800c2d3a  lea     rcx, [rsp+1C8h+var_150]
0x1800c2d3f  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CMarshaledInterfaceResult_Windows__ApplicationModel__Store__Preview__InstallControl__IAppInstallItem__Windows__ApplicationModel__Store__Preview__InstallControl__AppInstallItem___Windows__Internal__ComTaskPoolHandler__lambda_ff3919bc47410d386a3a684a501fa3a6___
0x1800c2d44  mov     rcx, [rsp+1C8h]; this
0x1800c2d4c  test    eax, eax
0x1800c2d4e  jns     short loc_1800C2D65
0x1800c2d50  mov     r9d, eax; char *
0x1800c2d53  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c2d5a  mov     edx, 19EEh; void *
0x1800c2d5f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c2d65  lea     rcx, [rsp+1C8h+var_118]
0x1800c2d6d  call    _lambda_ff3919bc47410d386a3a684a501fa3a6_____lambda_ff3919bc47410d386a3a684a501fa3a6_
0x1800c2d72  nop
0x1800c2d73  lea     rcx, [rsp+1C8h+var_160]
0x1800c2d78  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c2d7d  mov     [rsp+1C8h+string], rdi
0x1800c2d82  lea     rcx, [rsp+1C8h+var_138]
0x1800c2d8a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c2d8f  nop
0x1800c2d90  mov     rcx, [rsp+1C8h+var_120]; this
0x1800c2d98  test    rcx, rcx
0x1800c2d9b  jz      short loc_1800C2DA3
0x1800c2d9d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c2da2  nop
0x1800c2da3  mov     rcx, [rsp+1C8h+string]; string
0x1800c2da8  call    cs:__imp_WindowsDeleteString
0x1800c2dae  mov     [rsp+1C8h+string], rdi
0x1800c2db3  lea     rcx, [rsp+1C8h+var_140]
0x1800c2dbb  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c2dc0  xor     eax, eax
0x1800c2dc2  jmp     short loc_1800C2DC8
0x1800c2dc4  mov     eax, dword ptr [rsp+1C8h+var_160]
0x1800c2dc8  mov     rcx, [rsp+1C8h+var_48]
0x1800c2dd0  xor     rcx, rsp; StackCookie
0x1800c2dd3  call    __security_check_cookie
0x1800c2dd8  add     rsp, 190h
0x1800c2ddf  pop     r15
0x1800c2de1  pop     r14
0x1800c2de3  pop     r13
0x1800c2de5  pop     r12
0x1800c2de7  pop     rdi
0x1800c2de8  pop     rsi
0x1800c2de9  pop     rbx
0x1800c2dea  retn
```
