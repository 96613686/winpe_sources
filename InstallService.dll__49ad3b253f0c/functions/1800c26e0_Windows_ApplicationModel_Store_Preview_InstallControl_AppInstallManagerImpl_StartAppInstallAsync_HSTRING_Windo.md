# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppInstallAsync(HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppIdType,uchar,uchar,uchar,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> * *)

- ea: `0x1800c26e0`
- end: `0x1800c2ae7`
- name: `?StartAppInstallAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@UEAAJPEAUHSTRING__@@W4AppIdType@Internal@23456@EEE0000PEAPEAU?$IAsyncOperation@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@6@@Z`
- size: `1031`
- prototype: `__int64 __fastcall(__int64, HSTRING, char *, char, __int64, char, HSTRING, HSTRING, __int64, WindowsUpdate::CommonTelemetry *, _QWORD *)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180010b74`
- `0x18001c414`
- `0x180020274`
- `0x180023a9c`
- `0x18002548c`
- `0x180028cd4`
- `0x18003b08c`
- `0x18006e510`
- `0x180072420`
- `0x18007bff0`
- `0x180082af0`
- `0x18008df88`
- `0x18008f74c`
- `0x180095df8`
- `0x1800c26e0`
- `0x1800c83a8`
- `0x1801473f4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c27a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2808`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2aad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c27a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2808`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2aad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c27db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c27db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c281f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c282d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c283b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c2934`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c2a02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c2a10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c2a1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c281f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c282d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c283b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c2934`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c2a02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c2a10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c2a1e`

## string_xrefs

- `0x1800c27ef`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c289b`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c2a76`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c27b3`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppInstallAsync`
- `0x1800c288e`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppInstallAsync`
- `0x1800c2a69`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppInstallAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppInstallAsync(
        __int64 a1,
        HSTRING a2,
        char *a3,
        char a4,
        __int64 a5,
        char a6,
        HSTRING a7,
        HSTRING a8,
        __int64 a9,
        WindowsUpdate::CommonTelemetry *a10,
        _QWORD *a11)
{
  unsigned __int32 v12; // r15d
  HRESULT CallingProcessAndFunction; // eax
  unsigned int v14; // ebx
  __int64 v15; // rdx
  HSTRING v17; // r14
  PCWSTR StringRawBuffer; // rsi
  PCWSTR v19; // rdi
  PCWSTR v20; // rbx
  __int64 v21; // rax
  TraceLoggingCorrelationVector *v22; // r15
  Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *v23; // rcx
  int v24; // r14d
  __int64 v25; // rbx
  void *CurrentActiveUserAccessToken; // rax
  wchar_t *v27; // rax
  const unsigned __int16 *v28; // rdx
  bool v29; // r8
  __int64 v30; // rdi
  HSTRING v31; // rsi
  __int64 v32; // r8
  PCWSTR v33; // rsi
  PCWSTR v34; // rdi
  PCWSTR v35; // rbx
  __int64 v36; // rax
  unsigned int v37; // edx
  int v38; // [rsp+20h] [rbp-E0h]
  bool IsCallerInteractive; // [rsp+71h] [rbp-8Fh]
  HSTRING string; // [rsp+78h] [rbp-88h] BYREF
  __int64 v42; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v43; // [rsp+88h] [rbp-78h] BYREF
  __int64 v44; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int32 v45; // [rsp+98h] [rbp-68h]
  __m128i si128; // [rsp+A0h] [rbp-60h] BYREF
  int v47; // [rsp+B0h] [rbp-50h]
  HSTRING newString; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING v49; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v50; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING v51; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v52; // [rsp+D8h] [rbp-28h]
  __int64 v53; // [rsp+E0h] [rbp-20h]
  _QWORD *v54; // [rsp+E8h] [rbp-18h]
  HSTRING v55; // [rsp+F0h] [rbp-10h]
  __int64 v56; // [rsp+F8h] [rbp-8h] BYREF
  char v57[8]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v58; // [rsp+108h] [rbp+8h] BYREF
  char v59; // [rsp+110h] [rbp+10h]
  bool v60; // [rsp+111h] [rbp+11h]
  char v61; // [rsp+112h] [rbp+12h]
  __int64 v62; // [rsp+118h] [rbp+18h]
  __int64 v63; // [rsp+120h] [rbp+20h]
  HSTRING v64; // [rsp+128h] [rbp+28h]
  HSTRING__ v65; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v52 = a1;
  v51 = a2;
  v49 = a7;
  v55 = a8;
  v43 = a8;
  v50 = a9;
  v54 = a11;
  *a11 = 0;
  if ( !a2 || (unsigned int)a3 > 4 )
    return 2147942487LL;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v47 = 4;
  v12 = si128.m128i_u32[(int)a3];
  v45 = v12;
  LODWORD(v42) = v12;
  WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(a10, &v65, a3);
  WindowsDeleteString(0);
  string = 0;
  CallingProcessAndFunction = GetCallingProcessAndFunction(
                                0,
                                L"Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppInstallAsync",
                                &string);
  v14 = CallingProcessAndFunction;
  if ( CallingProcessAndFunction < 0 )
  {
    v15 = 1524;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)CallingProcessAndFunction,
      v38);
    WindowsDeleteString(string);
    return v14;
  }
  newString = 0;
  CallingProcessAndFunction = WindowsDuplicateString(string, &newString);
  v14 = CallingProcessAndFunction;
  if ( CallingProcessAndFunction < 0 )
  {
    v15 = 1526;
    goto LABEL_7;
  }
  v17 = string;
  StringRawBuffer = WindowsGetStringRawBuffer(a8, 0);
  v19 = WindowsGetStringRawBuffer(a7, 0);
  v20 = WindowsGetStringRawBuffer(a2, 0);
  v21 = AppId::IdTypeName(v12);
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
    0x5FFu,
    "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppInstallAsync",
    -1,
    L"request: %s = %s, catalogId = %s, flightId  = %s, CV = %hs, clientId = %s",
    0,
    0,
    v21,
    v20,
    v19,
    StringRawBuffer,
    &v65,
    v17);
  si128.m128i_i64[0] = (__int64)TraceLoggingCorrelationVector::Extend((const char *)&v65, 0);
  v22 = (TraceLoggingCorrelationVector *)si128.m128i_i64[0];
  v53 = si128.m128i_i64[0];
  v23 = (Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *)-si128.m128i_i64[0];
  v24 = si128.m128i_i64[0] == 0 ? 0x8007000E : 0;
  v44 = 0;
  if ( si128.m128i_i64[0] )
  {
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v44);
    v24 = Microsoft::WRL::Details::MakeAndInitialize<AppId,AppId,HSTRING__ * &,enum AppId::Type,HSTRING__ * &,HSTRING__ * &,HSTRING__ * &>(
            (unsigned int)&v44,
            (unsigned int)&v51,
            (unsigned int)&v42,
            (unsigned int)&v50,
            (__int64)&v49,
            (__int64)&v43);
  }
  v25 = 0;
  v42 = 0;
  if ( v24 >= 0 )
  {
    CurrentActiveUserAccessToken = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetCurrentActiveUserAccessToken(v23);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v42,
      CurrentActiveUserAccessToken);
    v25 = v42;
  }
  v27 = (wchar_t *)WindowsGetStringRawBuffer(string, 0);
  LOBYTE(v28) = 1;
  IsCallerInteractive = Utils::IsCallerInteractive(v27, v28, v29);
  if ( v24 < 0 )
    goto LABEL_14;
  v30 = v52 - 72;
  v43 = (HSTRING)(v52 - 72);
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&v43);
  v31 = newString;
  v56 = v30;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>(
    v57,
    &v43);
  v58 = v44;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&v58);
  v59 = a4;
  v60 = IsCallerInteractive;
  v61 = a6;
  v62 = v25;
  v42 = 0;
  v22 = 0;
  v53 = 0;
  v63 = si128.m128i_i64[0];
  v64 = v31;
  si128.m128i_i32[0] = 0;
  *(__int64 *)((char *)si128.m128i_i64 + 4) = 128;
  v24 = Windows::Internal::MakeAsyncOperation_Windows::Internal::CMarshaledInterfaceResult_Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem__Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem___Windows::Internal::ComTaskPoolHandler__lambda_c6f1c6a9ddf4305a8f4b0f277ad85766___(
          &si128,
          v54,
          v32,
          &v56);
  lambda_c6f1c6a9ddf4305a8f4b0f277ad85766_::__lambda_c6f1c6a9ddf4305a8f4b0f277ad85766_(&v56);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v43);
  if ( v24 < 0 )
  {
LABEL_14:
    v33 = WindowsGetStringRawBuffer(v55, 0);
    v34 = WindowsGetStringRawBuffer(a7, 0);
    v35 = WindowsGetStringRawBuffer(a2, 0);
    v36 = AppId::IdTypeName(v45);
    LogMessage(
      1u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      0x669u,
      "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppInstallAsync",
      v24,
      L"initialization failed: %s = %s, catalogId = %s, flightId  = %s, CV = %hs",
      0,
      0,
      v36,
      v35,
      v34,
      v33,
      &v65);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v42);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v44);
  if ( v22 )
    TraceLoggingCorrelationVector::`scalar deleting destructor'(v22, v37);
  WindowsDeleteString(string);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x1800c26e0  mov     [rsp-8+arg_0], rbx
0x1800c26e5  push    rbp
0x1800c26e6  push    rsi
0x1800c26e7  push    rdi
0x1800c26e8  push    r12
0x1800c26ea  push    r13
0x1800c26ec  push    r14
0x1800c26ee  push    r15
0x1800c26f0  lea     rbp, [rsp-0D0h]
0x1800c26f8  sub     rsp, 1D0h
0x1800c26ff  mov     rax, cs:__security_cookie
0x1800c2706  xor     rax, rsp
0x1800c2709  mov     [rbp+100h+var_40], rax
0x1800c2710  mov     [rsp+200h+var_190], r9b
0x1800c2715  mov     r12, rdx
0x1800c2718  mov     [rbp+100h+var_128], rcx
0x1800c271c  mov     [rbp+100h+var_130], rdx
0x1800c2720  mov     r13, [rbp+100h+arg_30]
0x1800c2727  mov     [rbp+100h+var_140], r13
0x1800c272b  mov     rdi, [rbp+100h+arg_38]
0x1800c2732  mov     [rbp+100h+var_110], rdi
0x1800c2736  mov     [rbp+100h+var_178], rdi
0x1800c273a  mov     rax, [rbp+100h+arg_40]
0x1800c2741  mov     [rbp+100h+var_138], rax
0x1800c2745  mov     rcx, [rbp+100h+arg_48]; this
0x1800c274c  mov     rax, [rbp+100h+arg_50]
0x1800c2753  mov     [rbp+100h+var_118], rax
0x1800c2757  xor     esi, esi
0x1800c2759  mov     [rax], rsi
0x1800c275c  test    rdx, rdx
0x1800c275f  jz      loc_1800C2AB8
0x1800c2765  cmp     r8d, 4
0x1800c2769  ja      loc_1800C2AB8
0x1800c276f  movdqa  xmm0, cs:__xmm@00000003000000020000000100000000
0x1800c2777  movdqu  [rbp+100h+var_160], xmm0
0x1800c277c  mov     [rbp+100h+var_150], 4
0x1800c2783  movsxd  rax, r8d
0x1800c2786  mov     r15d, dword ptr [rbp+rax*4+100h+var_160]
0x1800c278b  mov     [rbp+100h+var_168], r15d
0x1800c278f  mov     dword ptr [rbp+100h+var_180], r15d
0x1800c2793  lea     rdx, [rbp+100h+var_D0]; HSTRING
0x1800c2797  call    ?GenerateIfMissingCorrelationVector@CommonTelemetry@WindowsUpdate@@YAXPEAUHSTRING__@@QEAD@Z; WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(HSTRING__ *,char * const)
0x1800c279c  mov     [rsp+200h+string], rsi
0x1800c27a1  xor     ecx, ecx; string
0x1800c27a3  call    cs:__imp_WindowsDeleteString
0x1800c27a9  mov     [rsp+200h+string], rsi
0x1800c27ae  lea     r8, [rsp+200h+string]; HSTRING *
0x1800c27b3  lea     rdx, aWindowsApplica_75; "Windows::ApplicationModel::Store::Previ"...
0x1800c27ba  xor     ecx, ecx; HSTRING
0x1800c27bc  call    ?GetCallingProcessAndFunction@@YAJPEAUHSTRING__@@PEBGPEAPEAU1@@Z; GetCallingProcessAndFunction(HSTRING__ *,ushort const *,HSTRING__ * *)
0x1800c27c1  mov     ebx, eax
0x1800c27c3  test    eax, eax
0x1800c27c5  jns     short loc_1800C27CE
0x1800c27c7  mov     edx, 5F4h
0x1800c27cc  jmp     short loc_1800C27EC
0x1800c27ce  mov     [rbp+100h+newString], rsi
0x1800c27d2  lea     rdx, [rbp+100h+newString]; newString
0x1800c27d6  mov     rcx, [rsp+200h+string]; string
0x1800c27db  call    cs:__imp_WindowsDuplicateString
0x1800c27e1  mov     ebx, eax
0x1800c27e3  test    eax, eax
0x1800c27e5  jns     short loc_1800C2815
0x1800c27e7  mov     edx, 5F6h; void *
0x1800c27ec  mov     r9d, eax; char *
0x1800c27ef  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c27f6  mov     rcx, [rbp+108h]; this
0x1800c27fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c2802  nop
0x1800c2803  mov     rcx, [rsp+200h+string]; string
0x1800c2808  call    cs:__imp_WindowsDeleteString
0x1800c280e  mov     eax, ebx
0x1800c2810  jmp     loc_1800C2ABD
0x1800c2815  mov     r14, [rsp+200h+string]
0x1800c281a  xor     edx, edx; length
0x1800c281c  mov     rcx, rdi; string
0x1800c281f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c2825  mov     rsi, rax
0x1800c2828  xor     edx, edx; length
0x1800c282a  mov     rcx, r13; string
0x1800c282d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c2833  mov     rdi, rax
0x1800c2836  xor     edx, edx; length
0x1800c2838  mov     rcx, r12; string
0x1800c283b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c2841  mov     rbx, rax
0x1800c2844  mov     ecx, r15d
0x1800c2847  call    ?IdTypeName@AppId@@SAPEBGW4Type@1@@Z; AppId::IdTypeName(AppId::Type)
0x1800c284c  mov     [rsp+200h+var_198], r14
0x1800c2851  lea     rcx, [rbp+100h+var_D0]
0x1800c2855  mov     [rsp+200h+var_1A0], rcx
0x1800c285a  mov     [rsp+200h+var_1A8], rsi
0x1800c285f  mov     [rsp+200h+var_1B0], rdi
0x1800c2864  mov     [rsp+200h+var_1B8], rbx
0x1800c2869  mov     [rsp+200h+var_1C0], rax
0x1800c286e  xor     edi, edi
0x1800c2870  mov     [rsp+200h+var_1C8], rdi; unsigned __int16 *
0x1800c2875  mov     [rsp+200h+var_1D0], rdi; char *
0x1800c287a  lea     rax, aRequestSSCatal; "request: %s = %s, catalogId = %s, fligh"...
0x1800c2881  mov     [rsp+200h+var_1D8], rax; unsigned __int16 *
0x1800c2886  mov     [rsp+200h+var_1E0], 0FFFFFFFFh; int
0x1800c288e  lea     r9, aWindowsApplica_111; "Windows::ApplicationModel::Store::Previ"...
0x1800c2895  mov     r8d, 5FFh; unsigned int
0x1800c289b  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c28a2  lea     ecx, [rdi+3]; unsigned int
0x1800c28a5  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800c28aa  xor     edx, edx; bool
0x1800c28ac  lea     rcx, [rbp+100h+var_D0]; char *
0x1800c28b0  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x1800c28b5  mov     qword ptr [rbp+100h+var_160], rax
0x1800c28b9  mov     r15, rax
0x1800c28bc  mov     [rbp+100h+var_120], rax
0x1800c28c0  mov     rcx, rax
0x1800c28c3  neg     rcx
0x1800c28c6  sbb     r14d, r14d
0x1800c28c9  not     r14d
0x1800c28cc  and     r14d, 8007000Eh
0x1800c28d3  mov     [rbp+100h+var_170], rdi
0x1800c28d7  jl      short loc_1800C290C
0x1800c28d9  lea     rcx, [rbp+100h+var_170]
0x1800c28dd  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c28e2  lea     rax, [rbp+100h+var_178]
0x1800c28e6  mov     [rsp+200h+var_1D8], rax
0x1800c28eb  lea     rax, [rbp+100h+var_140]
0x1800c28ef  mov     qword ptr [rsp+200h+var_1E0], rax
0x1800c28f4  lea     r9, [rbp+100h+var_138]
0x1800c28f8  lea     r8, [rbp+100h+var_180]
0x1800c28fc  lea     rdx, [rbp+100h+var_130]
0x1800c2900  lea     rcx, [rbp+100h+var_170]
0x1800c2904  call    ??$MakeAndInitialize@VAppId@@V1@AEAPEAUHSTRING__@@W4Type@1@AEAPEAU2@AEAPEAU2@AEAPEAU2@@Details@WRL@Microsoft@@YAJPEAPEAVAppId@@AEAPEAUHSTRING__@@$$QEAW4Type@3@111@Z; Microsoft::WRL::Details::MakeAndInitialize<AppId,AppId,HSTRING__ * &,AppId::Type,HSTRING__ * &,HSTRING__ * &,HSTRING__ * &>(AppId * *,HSTRING__ * &,AppId::Type &&,HSTRING__ * &,HSTRING__ * &,HSTRING__ * &)
0x1800c2909  mov     r14d, eax
0x1800c290c  mov     rbx, rdi
0x1800c290f  mov     [rbp+100h+var_180], rbx
0x1800c2913  test    r14d, r14d
0x1800c2916  js      short loc_1800C292D
0x1800c2918  call    ?_GetCurrentActiveUserAccessToken@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAPEAXXZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetCurrentActiveUserAccessToken(void)
0x1800c291d  mov     rdx, rax
0x1800c2920  lea     rcx, [rbp+100h+var_180]
0x1800c2924  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800c2929  mov     rbx, [rbp+100h+var_180]
0x1800c292d  xor     edx, edx; length
0x1800c292f  mov     rcx, [rsp+200h+string]; string
0x1800c2934  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c293a  mov     rcx, rax; Str
0x1800c293d  mov     dl, 1; unsigned __int16 *
0x1800c293f  call    ?IsCallerInteractive@Utils@@YA_NPEBG_N@Z; Utils::IsCallerInteractive(ushort const *,bool)
0x1800c2944  mov     [rsp+200h+var_18F], al
0x1800c2948  test    r14d, r14d
0x1800c294b  js      loc_1800C29FC
0x1800c2951  mov     rdi, [rbp+100h+var_128]
0x1800c2955  add     rdi, 0FFFFFFFFFFFFFFB8h
0x1800c2959  mov     [rbp+100h+var_178], rdi
0x1800c295d  lea     rcx, [rbp+100h+var_178]
0x1800c2961  call    ?InternalAddRef@?$ComPtr@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(void)
0x1800c2966  nop
0x1800c2967  mov     rsi, [rbp+100h+newString]
0x1800c296b  mov     [rbp+100h+var_108], rdi
0x1800c296f  lea     rdx, [rbp+100h+var_178]
0x1800c2973  lea     rcx, [rbp+100h+var_100]
0x1800c2977  call    ??0?$ComPtr@VAppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>(Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl> &&)
0x1800c297c  mov     rcx, [rbp+100h+var_170]
0x1800c2980  mov     [rbp+100h+var_F8], rcx
0x1800c2984  lea     rcx, [rbp+100h+var_F8]
0x1800c2988  call    ?InternalAddRef@?$ComPtr@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(void)
0x1800c298d  mov     al, [rsp+200h+var_190]
0x1800c2991  mov     [rbp+100h+var_F0], al
0x1800c2994  mov     al, [rsp+200h+var_18F]
0x1800c2998  mov     [rbp+100h+var_EF], al
0x1800c299b  mov     al, [rbp+100h+arg_28]
0x1800c29a1  mov     [rbp+100h+var_EE], al
0x1800c29a4  mov     [rbp+100h+var_E8], rbx
0x1800c29a8  xor     ebx, ebx
0x1800c29aa  mov     [rbp+100h+var_180], rbx
0x1800c29ae  mov     r15d, ebx
0x1800c29b1  mov     [rbp+100h+var_120], rbx
0x1800c29b5  mov     rax, qword ptr [rbp+100h+var_160]
0x1800c29b9  mov     [rbp+100h+var_E0], rax
0x1800c29bd  mov     [rbp+100h+var_D8], rsi
0x1800c29c1  mov     dword ptr [rbp+100h+var_160], ebx
0x1800c29c4  mov     qword ptr [rbp+100h+var_160+4], 80h
0x1800c29cc  lea     r9, [rbp+100h+var_108]
0x1800c29d0  mov     rdx, [rbp+100h+var_118]
0x1800c29d4  lea     rcx, [rbp+100h+var_160]
0x1800c29d8  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CMarshaledInterfaceResult_Windows__ApplicationModel__Store__Preview__InstallControl__IAppInstallItem__Windows__ApplicationModel__Store__Preview__InstallControl__AppInstallItem___Windows__Internal__ComTaskPoolHandler__lambda_c6f1c6a9ddf4305a8f4b0f277ad85766___
0x1800c29dd  mov     r14d, eax
0x1800c29e0  lea     rcx, [rbp+100h+var_108]
0x1800c29e4  call    _lambda_c6f1c6a9ddf4305a8f4b0f277ad85766_____lambda_c6f1c6a9ddf4305a8f4b0f277ad85766_
0x1800c29e9  nop
0x1800c29ea  lea     rcx, [rbp+100h+var_178]
0x1800c29ee  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c29f3  test    r14d, r14d
0x1800c29f6  jns     loc_1800C2A86
0x1800c29fc  xor     edx, edx; length
0x1800c29fe  mov     rcx, [rbp+100h+var_110]; string
0x1800c2a02  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c2a08  mov     rsi, rax
0x1800c2a0b  xor     edx, edx; length
0x1800c2a0d  mov     rcx, r13; string
0x1800c2a10  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c2a16  mov     rdi, rax
0x1800c2a19  xor     edx, edx; length
0x1800c2a1b  mov     rcx, r12; string
0x1800c2a1e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c2a24  mov     rbx, rax
0x1800c2a27  mov     ecx, [rbp+100h+var_168]
0x1800c2a2a  call    ?IdTypeName@AppId@@SAPEBGW4Type@1@@Z; AppId::IdTypeName(AppId::Type)
0x1800c2a2f  lea     rdx, [rbp+100h+var_D0]
0x1800c2a33  mov     [rsp+200h+var_1A0], rdx
0x1800c2a38  mov     [rsp+200h+var_1A8], rsi
0x1800c2a3d  mov     [rsp+200h+var_1B0], rdi
0x1800c2a42  mov     [rsp+200h+var_1B8], rbx
0x1800c2a47  mov     [rsp+200h+var_1C0], rax
0x1800c2a4c  xor     ebx, ebx
0x1800c2a4e  mov     [rsp+200h+var_1C8], rbx; unsigned __int16 *
0x1800c2a53  mov     [rsp+200h+var_1D0], rbx; char *
0x1800c2a58  lea     rax, aInitialization_3; "initialization failed: %s = %s, catalog"...
0x1800c2a5f  mov     [rsp+200h+var_1D8], rax; unsigned __int16 *
0x1800c2a64  mov     [rsp+200h+var_1E0], r14d; int
0x1800c2a69  lea     r9, aWindowsApplica_111; "Windows::ApplicationModel::Store::Previ"...
0x1800c2a70  mov     r8d, 669h; unsigned int
0x1800c2a76  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c2a7d  lea     ecx, [rbx+1]; unsigned int
0x1800c2a80  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800c2a85  nop
0x1800c2a86  lea     rcx, [rbp+100h+var_180]
0x1800c2a8a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800c2a8f  nop
0x1800c2a90  lea     rcx, [rbp+100h+var_170]
0x1800c2a94  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c2a99  nop
0x1800c2a9a  test    r15, r15
0x1800c2a9d  jz      short loc_1800C2AA8
0x1800c2a9f  mov     rcx, r15; this
0x1800c2aa2  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x1800c2aa7  nop
0x1800c2aa8  mov     rcx, [rsp+200h+string]; string
0x1800c2aad  call    cs:__imp_WindowsDeleteString
0x1800c2ab3  mov     eax, r14d
0x1800c2ab6  jmp     short loc_1800C2ABD
0x1800c2ab8  mov     eax, 80070057h
0x1800c2abd  mov     rcx, [rbp+100h+var_40]
0x1800c2ac4  xor     rcx, rsp; StackCookie
0x1800c2ac7  call    __security_check_cookie
0x1800c2acc  mov     rbx, [rsp+200h+arg_0]
0x1800c2ad4  add     rsp, 1D0h
0x1800c2adb  pop     r15
0x1800c2add  pop     r14
0x1800c2adf  pop     r13
0x1800c2ae1  pop     r12
0x1800c2ae3  pop     rdi
0x1800c2ae4  pop     rsi
0x1800c2ae5  pop     rbp
0x1800c2ae6  retn
```
