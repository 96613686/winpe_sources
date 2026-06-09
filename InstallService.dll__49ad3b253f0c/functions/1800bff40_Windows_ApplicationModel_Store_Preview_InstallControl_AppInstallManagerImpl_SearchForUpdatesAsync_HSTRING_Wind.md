# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::SearchForUpdatesAsync(HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppIdType,uchar,uchar,HSTRING__ *,HSTRING__ *,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> * *)

- ea: `0x1800bff40`
- end: `0x1800c0341`
- name: `?SearchForUpdatesAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@UEAAJPEAUHSTRING__@@W4AppIdType@Internal@23456@EE00PEAPEAU?$IAsyncOperation@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@6@@Z`
- size: `1025`
- prototype: `__int64 __fastcall(__int64, HSTRING, char *, char, char, HSTRING, WindowsUpdate::CommonTelemetry *, _QWORD *)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180010b74`
- `0x18001c414`
- `0x180023a9c`
- `0x18002548c`
- `0x180028cd4`
- `0x18003b08c`
- `0x18003f0dc`
- `0x180072420`
- `0x18007bff0`
- `0x18008004c`
- `0x180082af0`
- `0x18008f814`
- `0x1800923e8`
- `0x180095f40`
- `0x1800bff40`
- `0x1800c83a8`
- `0x1801473f4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bffe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c00fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c02c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bffe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c00fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c02c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c001a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c001a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c004c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c005a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c0068`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c0213`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c0236`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c004c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c005a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c0068`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c0213`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c0236`

## string_xrefs

- `0x1800c002b`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c00dd`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c028d`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c030b`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800bfff3`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::SearchForUpdatesAsync`
- `0x1800c00d0`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::SearchForUpdatesAsync`
- `0x1800c0280`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::SearchForUpdatesAsync`
- `0x1800c02fe`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::SearchForUpdatesAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::SearchForUpdatesAsync(
        __int64 a1,
        HSTRING a2,
        char *a3,
        char a4,
        char a5,
        HSTRING a6,
        WindowsUpdate::CommonTelemetry *a7,
        _QWORD *a8)
{
  HSTRING v10; // r12
  WindowsUpdate::CommonTelemetry *v11; // rcx
  unsigned __int32 v12; // r13d
  HRESULT CallingProcessAndFunction; // eax
  unsigned int v14; // ebx
  __int64 v15; // rdx
  PCWSTR StringRawBuffer; // rsi
  PCWSTR v17; // rdi
  PCWSTR v18; // rbx
  __int64 v19; // rax
  const unsigned __int16 *v20; // rcx
  Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *v21; // rcx
  int v22; // esi
  void *CurrentActiveUserAccessToken; // rax
  int v24; // ebx
  __int64 v25; // rax
  __int64 v26; // r8
  PCWSTR v27; // rdi
  bool v28; // zf
  const unsigned __int16 *v29; // r15
  PCWSTR v30; // rbx
  __int64 v31; // rax
  unsigned int v32; // edx
  int v34; // [rsp+20h] [rbp-E0h]
  __int64 v35; // [rsp+70h] [rbp-90h] BYREF
  __int64 v36; // [rsp+78h] [rbp-88h] BYREF
  HSTRING string; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v38; // [rsp+88h] [rbp-78h] BYREF
  __int64 v39; // [rsp+90h] [rbp-70h] BYREF
  HSTRING newString; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v41[2]; // [rsp+A0h] [rbp-60h] BYREF
  TraceLoggingCorrelationVector *v42; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v43; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING v44; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v45; // [rsp+C8h] [rbp-38h]
  __m128i si128; // [rsp+D0h] [rbp-30h]
  int v47; // [rsp+E0h] [rbp-20h]
  _BYTE v48[56]; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING__ v49; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v41[0] = a1;
  v44 = a2;
  LOBYTE(v35) = a4;
  v10 = a6;
  v38 = a6;
  v11 = a7;
  v45 = a8;
  *a8 = 0;
  if ( !a2 || (unsigned int)a3 > 4 )
  {
    v14 = -2147024809;
    LogMessage(
      1u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      0x178Au,
      "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::SearchForUpdatesAsync",
      -2147024809,
      L"%hs",
      0,
      0,
      0,
      "E_INVALIDARG");
    return v14;
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v47 = 4;
  v12 = si128.m128i_u32[(int)a3];
  LODWORD(v36) = v12;
  WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(v11, &v49, a3);
  WindowsDeleteString(0);
  string = 0;
  CallingProcessAndFunction = GetCallingProcessAndFunction(
                                0,
                                L"Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::SearchForUpdatesAsync",
                                &string);
  v14 = CallingProcessAndFunction;
  if ( CallingProcessAndFunction < 0 )
  {
    v15 = 6034;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)CallingProcessAndFunction,
      v34);
LABEL_12:
    WindowsDeleteString(string);
    return v14;
  }
  newString = 0;
  CallingProcessAndFunction = WindowsDuplicateString(string, &newString);
  v14 = CallingProcessAndFunction;
  if ( CallingProcessAndFunction < 0 )
  {
    v15 = 6036;
    goto LABEL_7;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(newString, 0);
  v17 = WindowsGetStringRawBuffer(v10, 0);
  v18 = WindowsGetStringRawBuffer(a2, 0);
  v19 = AppId::IdTypeName(v12);
  v20 = L"true";
  if ( !a4 )
    v20 = L"false";
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
    0x179Eu,
    "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::SearchForUpdatesAsync",
    -1,
    L"request: %s = %s, interactive = %s, catalogId = %s, CV = %hs, clientAppId = %s",
    0,
    0,
    v19,
    v18,
    v20,
    v17,
    &v49,
    StringRawBuffer,
    v35,
    v36);
  if ( (unsigned int)GetStoreAppsAreDisabled() )
  {
    v14 = -1073740956;
    goto LABEL_12;
  }
  v42 = TraceLoggingCorrelationVector::Extend((const char *)&v49, 0);
  v22 = v42 == 0 ? 0x8007000E : 0;
  v39 = 0;
  if ( v42 )
  {
    v43 = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v39);
    v22 = Microsoft::WRL::Details::MakeAndInitialize<AppId,AppId,HSTRING__ * &,enum AppId::Type,HSTRING__ * &,HSTRING__ * &>(
            (unsigned int)&v39,
            (unsigned int)&v44,
            (unsigned int)&v36,
            (unsigned int)&v43,
            (__int64)&v38);
  }
  v38 = 0;
  if ( v22 < 0 )
    goto LABEL_17;
  CurrentActiveUserAccessToken = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetCurrentActiveUserAccessToken(v21);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &v38,
    CurrentActiveUserAccessToken);
  v24 = LODWORD(v41[0]) - 88;
  v36 = v41[0] - 88LL;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&v36);
  v25 = lambda_cf484cc103cefee6d841b23325eb50b6_::_lambda_cf484cc103cefee6d841b23325eb50b6_(
          (unsigned int)v48,
          v24,
          (unsigned int)&v36,
          (unsigned int)&v38,
          (__int64)&v39,
          (__int64)&v35,
          (__int64)&a5,
          (__int64)&v42,
          (__int64)newString);
  LODWORD(v41[0]) = 0;
  *(_QWORD *)((char *)v41 + 4) = 128;
  v22 = Windows::Internal::MakeAsyncOperation_Windows::Internal::CMarshaledInterfaceResult_Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem__Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem___Windows::Internal::ComTaskPoolHandler__lambda_cf484cc103cefee6d841b23325eb50b6___(
          v41,
          v45,
          v26,
          v25);
  lambda_cf484cc103cefee6d841b23325eb50b6_::__lambda_cf484cc103cefee6d841b23325eb50b6_(v48);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v36);
  if ( v22 < 0 )
  {
LABEL_17:
    v27 = WindowsGetStringRawBuffer(v10, 0);
    v28 = a4 == 0;
    v29 = L"true";
    if ( v28 )
      v29 = L"false";
    v30 = WindowsGetStringRawBuffer(a2, 0);
    v31 = AppId::IdTypeName(v12);
    LogMessage(
      1u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      0x1804u,
      "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::SearchForUpdatesAsync",
      v22,
      L"initialization failed: %s = %s, interactive = %s, catalogId = %s, CV = %hs",
      0,
      0,
      v31,
      v30,
      v29,
      v27,
      &v49);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v39);
  if ( v42 )
    TraceLoggingCorrelationVector::`scalar deleting destructor'(v42, v32);
  WindowsDeleteString(string);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x1800bff40  push    rbp
0x1800bff42  push    rbx
0x1800bff43  push    rsi
0x1800bff44  push    rdi
0x1800bff45  push    r12
0x1800bff47  push    r13
0x1800bff49  push    r14
0x1800bff4b  push    r15
0x1800bff4d  lea     rbp, [rsp-0C8h]
0x1800bff55  sub     rsp, 1C8h
0x1800bff5c  mov     rax, cs:__security_cookie
0x1800bff63  xor     rax, rsp
0x1800bff66  mov     [rbp+100h+var_50], rax
0x1800bff6d  mov     r15b, r9b
0x1800bff70  mov     r14, rdx
0x1800bff73  mov     qword ptr [rbp+100h+var_160], rcx
0x1800bff77  mov     [rbp+100h+var_140], rdx
0x1800bff7b  mov     byte ptr [rsp+200h+var_190], r9b
0x1800bff80  mov     r12, [rbp+100h+arg_28]
0x1800bff87  mov     [rbp+100h+var_178], r12
0x1800bff8b  mov     rcx, [rbp+100h+arg_30]; this
0x1800bff92  mov     rax, [rbp+100h+arg_38]
0x1800bff99  mov     [rbp+100h+var_138], rax
0x1800bff9d  xor     edi, edi
0x1800bff9f  mov     [rax], rdi
0x1800bffa2  test    rdx, rdx
0x1800bffa5  jz      loc_1800C02CE
0x1800bffab  cmp     r8d, 4
0x1800bffaf  ja      loc_1800C02CE
0x1800bffb5  movdqa  xmm0, cs:__xmm@00000003000000020000000100000000
0x1800bffbd  movdqu  [rbp+100h+var_130], xmm0
0x1800bffc2  mov     [rbp+100h+var_120], 4
0x1800bffc9  movsxd  rax, r8d
0x1800bffcc  mov     r13d, dword ptr [rbp+rax*4+100h+var_130]
0x1800bffd1  mov     dword ptr [rsp+200h+var_188], r13d
0x1800bffd6  lea     rdx, [rbp+100h+var_E0]; HSTRING
0x1800bffda  call    ?GenerateIfMissingCorrelationVector@CommonTelemetry@WindowsUpdate@@YAXPEAUHSTRING__@@QEAD@Z; WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(HSTRING__ *,char * const)
0x1800bffdf  mov     [rbp+100h+string], rdi
0x1800bffe3  xor     ecx, ecx; string
0x1800bffe5  call    cs:__imp_WindowsDeleteString
0x1800bffeb  mov     [rbp+100h+string], rdi
0x1800bffef  lea     r8, [rbp+100h+string]; HSTRING *
0x1800bfff3  lea     rdx, aWindowsApplica_79; "Windows::ApplicationModel::Store::Previ"...
0x1800bfffa  xor     ecx, ecx; HSTRING
0x1800bfffc  call    ?GetCallingProcessAndFunction@@YAJPEAUHSTRING__@@PEBGPEAPEAU1@@Z; GetCallingProcessAndFunction(HSTRING__ *,ushort const *,HSTRING__ * *)
0x1800c0001  mov     ebx, eax
0x1800c0003  test    eax, eax
0x1800c0005  jns     short loc_1800C000E
0x1800c0007  mov     edx, 1792h
0x1800c000c  jmp     short loc_1800C002B
0x1800c000e  mov     [rbp+100h+newString], rdi
0x1800c0012  lea     rdx, [rbp+100h+newString]; newString
0x1800c0016  mov     rcx, [rbp+100h+string]; string
0x1800c001a  call    cs:__imp_WindowsDuplicateString
0x1800c0020  mov     ebx, eax
0x1800c0022  test    eax, eax
0x1800c0024  jns     short loc_1800C0046
0x1800c0026  mov     edx, 1794h; void *
0x1800c002b  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c0032  mov     r9d, eax; char *
0x1800c0035  mov     rcx, [rbp+108h]; this
0x1800c003c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0041  jmp     loc_1800C00FA
0x1800c0046  xor     edx, edx; length
0x1800c0048  mov     rcx, [rbp+100h+newString]; string
0x1800c004c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c0052  mov     rsi, rax
0x1800c0055  xor     edx, edx; length
0x1800c0057  mov     rcx, r12; string
0x1800c005a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c0060  mov     rdi, rax
0x1800c0063  xor     edx, edx; length
0x1800c0065  mov     rcx, r14; string
0x1800c0068  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c006e  mov     rbx, rax
0x1800c0071  mov     ecx, r13d
0x1800c0074  call    ?IdTypeName@AppId@@SAPEBGW4Type@1@@Z; AppId::IdTypeName(AppId::Type)
0x1800c0079  lea     rdx, aFalse_0; "false"
0x1800c0080  lea     rcx, aTrue; "true"
0x1800c0087  test    r15b, r15b
0x1800c008a  cmovz   rcx, rdx
0x1800c008e  mov     [rsp+200h+var_198], rsi
0x1800c0093  lea     rdx, [rbp+100h+var_E0]
0x1800c0097  mov     [rsp+200h+var_1A0], rdx
0x1800c009c  mov     [rsp+200h+var_1A8], rdi
0x1800c00a1  mov     [rsp+200h+var_1B0], rcx
0x1800c00a6  mov     [rsp+200h+var_1B8], rbx
0x1800c00ab  mov     [rsp+200h+var_1C0], rax
0x1800c00b0  xor     edi, edi
0x1800c00b2  mov     [rsp+200h+var_1C8], rdi; unsigned __int16 *
0x1800c00b7  mov     [rsp+200h+var_1D0], rdi; char *
0x1800c00bc  lea     rax, aRequestSSInter; "request: %s = %s, interactive = %s, cat"...
0x1800c00c3  mov     [rsp+200h+var_1D8], rax; unsigned __int16 *
0x1800c00c8  mov     [rsp+200h+var_1E0], 0FFFFFFFFh; int
0x1800c00d0  lea     r9, aWindowsApplica_88; "Windows::ApplicationModel::Store::Previ"...
0x1800c00d7  mov     r8d, 179Eh; unsigned int
0x1800c00dd  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c00e4  lea     ecx, [rdi+3]; unsigned int
0x1800c00e7  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800c00ec  call    ?GetStoreAppsAreDisabled@@YAHXZ; GetStoreAppsAreDisabled(void)
0x1800c00f1  test    eax, eax
0x1800c00f3  jz      short loc_1800C0109
0x1800c00f5  mov     ebx, 0C0000364h
0x1800c00fa  mov     rcx, [rbp+100h+string]; string
0x1800c00fe  call    cs:__imp_WindowsDeleteString
0x1800c0104  jmp     loc_1800C031C
0x1800c0109  xor     edx, edx; bool
0x1800c010b  lea     rcx, [rbp+100h+var_E0]; char *
0x1800c010f  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x1800c0114  mov     [rbp+100h+var_150], rax
0x1800c0118  neg     rax
0x1800c011b  sbb     esi, esi
0x1800c011d  not     esi
0x1800c011f  and     esi, 8007000Eh
0x1800c0125  mov     [rbp+100h+var_170], rdi
0x1800c0129  jl      short loc_1800C0159
0x1800c012b  mov     [rbp+100h+var_148], rdi
0x1800c012f  lea     rcx, [rbp+100h+var_170]
0x1800c0133  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c0138  lea     rax, [rbp+100h+var_178]
0x1800c013c  mov     qword ptr [rsp+200h+var_1E0], rax
0x1800c0141  lea     r9, [rbp+100h+var_148]
0x1800c0145  lea     r8, [rsp+200h+var_188]
0x1800c014a  lea     rdx, [rbp+100h+var_140]
0x1800c014e  lea     rcx, [rbp+100h+var_170]
0x1800c0152  call    ??$MakeAndInitialize@VAppId@@V1@AEAPEAUHSTRING__@@W4Type@1@AEAPEAU2@AEAPEAU2@@Details@WRL@Microsoft@@YAJPEAPEAVAppId@@AEAPEAUHSTRING__@@$$QEAW4Type@3@11@Z; Microsoft::WRL::Details::MakeAndInitialize<AppId,AppId,HSTRING__ * &,AppId::Type,HSTRING__ * &,HSTRING__ * &>(AppId * *,HSTRING__ * &,AppId::Type &&,HSTRING__ * &,HSTRING__ * &)
0x1800c0157  mov     esi, eax
0x1800c0159  mov     [rbp+100h+var_178], rdi
0x1800c015d  test    esi, esi
0x1800c015f  js      loc_1800C020E
0x1800c0165  call    ?_GetCurrentActiveUserAccessToken@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAPEAXXZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetCurrentActiveUserAccessToken(void)
0x1800c016a  mov     rdx, rax
0x1800c016d  lea     rcx, [rbp+100h+var_178]
0x1800c0171  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800c0176  mov     rbx, qword ptr [rbp+100h+var_160]
0x1800c017a  add     rbx, 0FFFFFFFFFFFFFFA8h
0x1800c017e  mov     [rsp+200h+var_188], rbx
0x1800c0183  lea     rcx, [rsp+200h+var_188]
0x1800c0188  call    ?InternalAddRef@?$ComPtr@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(void)
0x1800c018d  nop
0x1800c018e  mov     rax, [rbp+100h+newString]
0x1800c0192  mov     [rsp+200h+var_1C0], rax
0x1800c0197  lea     rax, [rbp+100h+var_150]
0x1800c019b  mov     [rsp+200h+var_1C8], rax
0x1800c01a0  lea     rax, [rbp+100h+arg_20]
0x1800c01a7  mov     [rsp+200h+var_1D0], rax
0x1800c01ac  lea     rax, [rsp+200h+var_190]
0x1800c01b1  mov     [rsp+200h+var_1D8], rax
0x1800c01b6  lea     rax, [rbp+100h+var_170]
0x1800c01ba  mov     qword ptr [rsp+200h+var_1E0], rax
0x1800c01bf  lea     r9, [rbp+100h+var_178]
0x1800c01c3  lea     r8, [rsp+200h+var_188]
0x1800c01c8  mov     rdx, rbx
0x1800c01cb  lea     rcx, [rbp+100h+var_118]
0x1800c01cf  call    _lambda_cf484cc103cefee6d841b23325eb50b6____lambda_cf484cc103cefee6d841b23325eb50b6_
0x1800c01d4  nop
0x1800c01d5  mov     dword ptr [rbp+100h+var_160], edi
0x1800c01d8  mov     qword ptr [rbp+100h+var_160+4], 80h
0x1800c01e0  mov     r9, rax
0x1800c01e3  mov     rdx, [rbp+100h+var_138]
0x1800c01e7  lea     rcx, [rbp+100h+var_160]
0x1800c01eb  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CMarshaledInterfaceResult_Windows__ApplicationModel__Store__Preview__InstallControl__IAppInstallItem__Windows__ApplicationModel__Store__Preview__InstallControl__AppInstallItem___Windows__Internal__ComTaskPoolHandler__lambda_cf484cc103cefee6d841b23325eb50b6___
0x1800c01f0  mov     esi, eax
0x1800c01f2  lea     rcx, [rbp+100h+var_118]
0x1800c01f6  call    _lambda_cf484cc103cefee6d841b23325eb50b6_____lambda_cf484cc103cefee6d841b23325eb50b6_
0x1800c01fb  nop
0x1800c01fc  lea     rcx, [rsp+200h+var_188]
0x1800c0201  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c0206  test    esi, esi
0x1800c0208  jns     loc_1800C029D
0x1800c020e  xor     edx, edx; length
0x1800c0210  mov     rcx, r12; string
0x1800c0213  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c0219  mov     rdi, rax
0x1800c021c  test    r15b, r15b
0x1800c021f  lea     r15, aTrue; "true"
0x1800c0226  lea     rax, aFalse_0; "false"
0x1800c022d  cmovz   r15, rax
0x1800c0231  xor     edx, edx; length
0x1800c0233  mov     rcx, r14; string
0x1800c0236  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c023c  mov     rbx, rax
0x1800c023f  mov     ecx, r13d
0x1800c0242  call    ?IdTypeName@AppId@@SAPEBGW4Type@1@@Z; AppId::IdTypeName(AppId::Type)
0x1800c0247  lea     rcx, [rbp+100h+var_E0]
0x1800c024b  mov     [rsp+200h+var_1A0], rcx
0x1800c0250  mov     [rsp+200h+var_1A8], rdi
0x1800c0255  mov     [rsp+200h+var_1B0], r15
0x1800c025a  mov     [rsp+200h+var_1B8], rbx
0x1800c025f  mov     [rsp+200h+var_1C0], rax
0x1800c0264  xor     edi, edi
0x1800c0266  mov     [rsp+200h+var_1C8], rdi; unsigned __int16 *
0x1800c026b  mov     [rsp+200h+var_1D0], rdi; char *
0x1800c0270  lea     rax, aInitialization_7; "initialization failed: %s = %s, interac"...
0x1800c0277  mov     [rsp+200h+var_1D8], rax; unsigned __int16 *
0x1800c027c  mov     [rsp+200h+var_1E0], esi; int
0x1800c0280  lea     r9, aWindowsApplica_88; "Windows::ApplicationModel::Store::Previ"...
0x1800c0287  mov     r8d, 1804h; unsigned int
0x1800c028d  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c0294  lea     ecx, [rdi+1]; unsigned int
0x1800c0297  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800c029c  nop
0x1800c029d  lea     rcx, [rbp+100h+var_178]
0x1800c02a1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800c02a6  nop
0x1800c02a7  lea     rcx, [rbp+100h+var_170]
0x1800c02ab  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c02b0  nop
0x1800c02b1  mov     rcx, [rbp+100h+var_150]; this
0x1800c02b5  test    rcx, rcx
0x1800c02b8  jz      short loc_1800C02C0
0x1800c02ba  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x1800c02bf  nop
0x1800c02c0  mov     rcx, [rbp+100h+string]; string
0x1800c02c4  call    cs:__imp_WindowsDeleteString
0x1800c02ca  mov     eax, esi
0x1800c02cc  jmp     short loc_1800C031E
0x1800c02ce  lea     rax, aEInvalidarg; "E_INVALIDARG"
0x1800c02d5  mov     [rsp+200h+var_1B8], rax
0x1800c02da  mov     [rsp+200h+var_1C0], rdi
0x1800c02df  mov     [rsp+200h+var_1C8], rdi; unsigned __int16 *
0x1800c02e4  mov     [rsp+200h+var_1D0], rdi; char *
0x1800c02e9  lea     rax, aHs_1; "%hs"
0x1800c02f0  mov     [rsp+200h+var_1D8], rax; unsigned __int16 *
0x1800c02f5  mov     ebx, 80070057h
0x1800c02fa  mov     [rsp+200h+var_1E0], ebx; int
0x1800c02fe  lea     r9, aWindowsApplica_88; "Windows::ApplicationModel::Store::Previ"...
0x1800c0305  mov     r8d, 178Ah; unsigned int
0x1800c030b  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c0312  mov     ecx, 1; unsigned int
0x1800c0317  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800c031c  mov     eax, ebx
0x1800c031e  mov     rcx, [rbp+100h+var_50]
0x1800c0325  xor     rcx, rsp; StackCookie
0x1800c0328  call    __security_check_cookie
0x1800c032d  add     rsp, 1C8h
0x1800c0334  pop     r15
0x1800c0336  pop     r14
0x1800c0338  pop     r13
0x1800c033a  pop     r12
0x1800c033c  pop     rdi
0x1800c033d  pop     rsi
0x1800c033e  pop     rbx
0x1800c033f  pop     rbp
0x1800c0340  retn
```
