# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppRestoreForUserAsync(Windows::System::IUser *,HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppIdType,uchar,HSTRING__ *,HSTRING__ *,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> * *)

- ea: `0x1800c3820`
- end: `0x1800c3ba2`
- name: `?StartAppRestoreForUserAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@UEAAJPEAUIUser@System@6@PEAUHSTRING__@@W4AppIdType@Internal@23456@E11PEAPEAU?$IAsyncOperation@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@6@@Z`
- size: `898`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180010b74`
- `0x18001c414`
- `0x180020274`
- `0x180023a9c`
- `0x18002548c`
- `0x180028cd4`
- `0x18002ec2c`
- `0x18003b08c`
- `0x18006e510`
- `0x180082af0`
- `0x18008df48`
- `0x18008f684`
- `0x180095bf4`
- `0x1800c3820`
- `0x18012efb0`
- `0x1801473f4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c38be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c39bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3b54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c38be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c39bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3b54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c3a10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c3a10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c390d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3926`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3934`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3ad7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c390d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3926`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3934`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3ad7`

## string_xrefs

- `0x1800c38ed`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c398b`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c3b23`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c3b90`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c397e`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppRestoreForUserAsync`
- `0x1800c3b16`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppRestoreForUserAsync`
- `0x1800c38ce`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppRestoreForUserAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppRestoreForUserAsync(
        __int64 a1,
        UserHelpers *a2,
        HSTRING a3,
        unsigned int a4,
        __int64 a5,
        HSTRING a6,
        WindowsUpdate::CommonTelemetry *a7,
        _QWORD *a8)
{
  unsigned __int32 v10; // r13d
  int CallingProcessAndFunction; // eax
  unsigned int v12; // ebx
  HSTRING v13; // r14
  wchar_t *StringRawBuffer; // rax
  const unsigned __int16 *v15; // rdx
  bool v16; // r8
  struct Windows::System::IUser *v17; // rdx
  struct TraceLoggingCorrelationVector *v18; // rsi
  int v20; // eax
  int v21; // edi
  __int64 v22; // rbx
  __int64 v23; // r8
  TraceLoggingCorrelationVector *v24; // rbx
  PCWSTR v25; // rbx
  __int64 v26; // rax
  unsigned int v27; // edx
  int v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+20h] [rbp-E0h]
  bool IsCallerInteractive; // [rsp+60h] [rbp-A0h]
  unsigned __int32 v31; // [rsp+64h] [rbp-9Ch] BYREF
  HSTRING string; // [rsp+68h] [rbp-98h] BYREF
  __int64 v33; // [rsp+70h] [rbp-90h] BYREF
  UserHelpers *v34; // [rsp+78h] [rbp-88h] BYREF
  __int64 v35; // [rsp+80h] [rbp-80h] BYREF
  HSTRING newString; // [rsp+88h] [rbp-78h] BYREF
  HSTRING v37; // [rsp+90h] [rbp-70h] BYREF
  __m128i si128; // [rsp+98h] [rbp-68h] BYREF
  int v39; // [rsp+A8h] [rbp-58h]
  struct TraceLoggingCorrelationVector *v40; // [rsp+B0h] [rbp-50h]
  __int64 v41; // [rsp+B8h] [rbp-48h] BYREF
  char v42[8]; // [rsp+C0h] [rbp-40h] BYREF
  char v43[8]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v44[2]; // [rsp+D0h] [rbp-30h] BYREF
  bool v45; // [rsp+E0h] [rbp-20h]
  HSTRING v46; // [rsp+E8h] [rbp-18h]
  HSTRING__ v47; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v33 = a1;
  v37 = a3;
  *a8 = 0;
  if ( !a3 || a4 > 4 )
    return 2147942487LL;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v39 = 4;
  v10 = si128.m128i_u32[a4];
  v31 = v10;
  WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(a7, &v47, (char *const)a3);
  WindowsDeleteString(0);
  string = 0;
  CallingProcessAndFunction = GetCallingProcessAndFunction(
                                a6,
                                L"Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartA"
                                 "ppRestoreForUserAsync",
                                &string);
  v12 = CallingProcessAndFunction;
  if ( CallingProcessAndFunction < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C88,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)CallingProcessAndFunction,
      v28);
LABEL_7:
    WindowsDeleteString(string);
    return v12;
  }
  v13 = string;
  StringRawBuffer = (wchar_t *)WindowsGetStringRawBuffer(string, 0);
  LOBYTE(v15) = 1;
  IsCallerInteractive = Utils::IsCallerInteractive(StringRawBuffer, v15, v16);
  WindowsGetStringRawBuffer(v13, 0);
  WindowsGetStringRawBuffer(a3, 0);
  AppId::IdTypeName(v10);
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
    0x1C91u,
    "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppRestoreForUserAsync",
    -1,
    L"request:  %s = %s, CV = %hs, clientAppId = %s",
    0,
    0);
  v18 = TraceLoggingCorrelationVector::Extend((const char *)&v47, 0);
  v40 = v18;
  if ( !v18 )
  {
    v12 = -2147024882;
    goto LABEL_7;
  }
  v20 = UserHelpers::ValidateMultiUserApiCall(a2, v17);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C9A,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v20,
      v29);
  v35 = 0;
  v21 = Microsoft::WRL::Details::MakeAndInitialize<AppId,AppId,HSTRING__ * &,enum AppId::Type &>(&v35, &v37, &v31);
  if ( v21 < 0 )
    goto LABEL_13;
  newString = 0;
  if ( v13 )
    WindowsDuplicateString(v13, &newString);
  v33 -= 136;
  v22 = v33;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&v33);
  v34 = a2;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&v34);
  v41 = v22;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>(
    v42,
    &v33);
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>(
    v43,
    &v34);
  v44[0] = v35;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(v44);
  v40 = 0;
  v44[1] = v18;
  v45 = IsCallerInteractive;
  v46 = newString;
  si128.m128i_i64[0] = 2;
  si128.m128i_i32[2] = 0;
  v21 = Windows::Internal::MakeAsyncOperation_Windows::Internal::CMarshaledInterfaceResult_Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem__Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem___Windows::Internal::ComTaskPoolHandler__lambda_371a52f92a59bb61ede4865a021f8944___(
          &si128,
          a8,
          v23,
          &v41);
  lambda_7d4e25090a3a4b87115c2ebaa24685ac_::__lambda_7d4e25090a3a4b87115c2ebaa24685ac_(&v41);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v33);
  v18 = 0;
  v24 = 0;
  if ( v21 < 0 )
  {
LABEL_13:
    v25 = WindowsGetStringRawBuffer(v37, 0);
    v26 = AppId::IdTypeName(v31);
    LogMessage(
      1u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      0x1CDCu,
      "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppRestoreForUserAsync",
      v21,
      L"initialization failed: %s = %s, CV = %hs",
      0,
      0,
      v26,
      v25,
      &v47);
    v24 = v18;
  }
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
  if ( v24 )
    TraceLoggingCorrelationVector::`scalar deleting destructor'(v24, v27);
  WindowsDeleteString(string);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x1800c3820  mov     [rsp-8+arg_0], rbx
0x1800c3825  push    rbp
0x1800c3826  push    rsi
0x1800c3827  push    rdi
0x1800c3828  push    r12
0x1800c382a  push    r13
0x1800c382c  push    r14
0x1800c382e  push    r15
0x1800c3830  lea     rbp, [rsp-90h]
0x1800c3838  sub     rsp, 190h
0x1800c383f  mov     rax, cs:__security_cookie
0x1800c3846  xor     rax, rsp
0x1800c3849  mov     [rbp+0C0h+var_40], rax
0x1800c3850  mov     rsi, r8
0x1800c3853  mov     r15, rdx
0x1800c3856  mov     [rsp+1C0h+var_150], rcx
0x1800c385b  mov     [rbp+0C0h+var_130], r8
0x1800c385f  mov     rbx, [rbp+0C0h+arg_28]
0x1800c3866  mov     rcx, [rbp+0C0h+arg_30]; this
0x1800c386d  mov     r12, [rbp+0C0h+arg_38]
0x1800c3874  xor     edi, edi
0x1800c3876  mov     [r12], rdi
0x1800c387a  test    r8, r8
0x1800c387d  jz      loc_1800C3B5E
0x1800c3883  cmp     r9d, 4
0x1800c3887  ja      loc_1800C3B5E
0x1800c388d  movdqa  xmm0, cs:__xmm@00000003000000020000000100000000
0x1800c3895  movdqu  [rbp+0C0h+var_128], xmm0
0x1800c389a  mov     [rbp+0C0h+var_118], 4
0x1800c38a1  movsxd  rax, r9d
0x1800c38a4  mov     r13d, dword ptr [rbp+rax*4+0C0h+var_128]
0x1800c38a9  mov     [rsp+1C0h+var_15C], r13d
0x1800c38ae  lea     rdx, [rbp+0C0h+var_D0]; HSTRING
0x1800c38b2  call    ?GenerateIfMissingCorrelationVector@CommonTelemetry@WindowsUpdate@@YAXPEAUHSTRING__@@QEAD@Z; WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(HSTRING__ *,char * const)
0x1800c38b7  mov     [rsp+1C0h+string], rdi
0x1800c38bc  xor     ecx, ecx; string
0x1800c38be  call    cs:__imp_WindowsDeleteString
0x1800c38c4  mov     [rsp+1C0h+string], rdi
0x1800c38c9  lea     r8, [rsp+1C0h+string]; HSTRING *
0x1800c38ce  lea     rdx, aWindowsApplica_151; "Windows::ApplicationModel::Store::Previ"...
0x1800c38d5  mov     rcx, rbx; HSTRING
0x1800c38d8  call    ?GetCallingProcessAndFunction@@YAJPEAUHSTRING__@@PEBGPEAPEAU1@@Z; GetCallingProcessAndFunction(HSTRING__ *,ushort const *,HSTRING__ * *)
0x1800c38dd  mov     ebx, eax
0x1800c38df  test    eax, eax
0x1800c38e1  jns     short loc_1800C3903
0x1800c38e3  mov     rcx, [rbp+0C8h]; this
0x1800c38ea  mov     r9d, eax; char *
0x1800c38ed  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c38f4  mov     edx, 1C88h; void *
0x1800c38f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c38fe  jmp     loc_1800C39B7
0x1800c3903  mov     r14, [rsp+1C0h+string]
0x1800c3908  xor     edx, edx; length
0x1800c390a  mov     rcx, r14; string
0x1800c390d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c3913  mov     rcx, rax; Str
0x1800c3916  mov     dl, 1; unsigned __int16 *
0x1800c3918  call    ?IsCallerInteractive@Utils@@YA_NPEBG_N@Z; Utils::IsCallerInteractive(ushort const *,bool)
0x1800c391d  mov     [rsp+1C0h+var_160], al
0x1800c3921  xor     edx, edx; length
0x1800c3923  mov     rcx, r14; string
0x1800c3926  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c392c  mov     rdi, rax
0x1800c392f  xor     edx, edx; length
0x1800c3931  mov     rcx, rsi; string
0x1800c3934  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c393a  mov     rbx, rax
0x1800c393d  mov     ecx, r13d
0x1800c3940  call    ?IdTypeName@AppId@@SAPEBGW4Type@1@@Z; AppId::IdTypeName(AppId::Type)
0x1800c3945  mov     [rsp+1C0h+var_168], rdi
0x1800c394a  lea     rcx, [rbp+0C0h+var_D0]
0x1800c394e  mov     [rsp+1C0h+var_170], rcx
0x1800c3953  mov     [rsp+1C0h+var_178], rbx
0x1800c3958  mov     [rsp+1C0h+var_180], rax
0x1800c395d  xor     r13d, r13d
0x1800c3960  mov     [rsp+1C0h+var_188], r13; unsigned __int16 *
0x1800c3965  mov     [rsp+1C0h+var_190], r13; char *
0x1800c396a  lea     rax, aRequestSSCvHsC_0; "request:  %s = %s, CV = %hs, clientAppI"...
0x1800c3971  mov     [rsp+1C0h+var_198], rax; unsigned __int16 *
0x1800c3976  mov     [rsp+1C0h+var_1A0], 0FFFFFFFFh; int
0x1800c397e  lea     r9, aWindowsApplica_10; "Windows::ApplicationModel::Store::Previ"...
0x1800c3985  mov     r8d, 1C91h; unsigned int
0x1800c398b  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c3992  lea     ecx, [r13+3]; unsigned int
0x1800c3996  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800c399b  xor     edx, edx; bool
0x1800c399d  lea     rcx, [rbp+0C0h+var_D0]; char *
0x1800c39a1  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x1800c39a6  mov     rsi, rax
0x1800c39a9  mov     [rbp+0C0h+var_110], rax
0x1800c39ad  test    rax, rax
0x1800c39b0  jnz     short loc_1800C39C9
0x1800c39b2  mov     ebx, 8007000Eh
0x1800c39b7  mov     rcx, [rsp+1C0h+string]; string
0x1800c39bc  call    cs:__imp_WindowsDeleteString
0x1800c39c2  mov     eax, ebx
0x1800c39c4  jmp     loc_1800C3B63
0x1800c39c9  mov     rcx, r15; this
0x1800c39cc  call    ?ValidateMultiUserApiCall@UserHelpers@@YAJPEAUIUser@System@Windows@@@Z; UserHelpers::ValidateMultiUserApiCall(Windows::System::IUser *)
0x1800c39d1  mov     rcx, [rbp+0C8h]; this
0x1800c39d8  test    eax, eax
0x1800c39da  js      loc_1800C3B8D
0x1800c39e0  mov     [rbp+0C0h+var_140], r13
0x1800c39e4  lea     r8, [rsp+1C0h+var_15C]
0x1800c39e9  lea     rdx, [rbp+0C0h+var_130]
0x1800c39ed  lea     rcx, [rbp+0C0h+var_140]
0x1800c39f1  call    ??$MakeAndInitialize@VAppId@@V1@AEAPEAUHSTRING__@@AEAW4Type@1@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VAppId@@@WRL@Microsoft@@@012@AEAPEAUHSTRING__@@AEAW4Type@AppId@@@Z; Microsoft::WRL::Details::MakeAndInitialize<AppId,AppId,HSTRING__ * &,AppId::Type &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<AppId>>,HSTRING__ * &,AppId::Type &)
0x1800c39f6  mov     edi, eax
0x1800c39f8  test    eax, eax
0x1800c39fa  js      loc_1800C3AD1
0x1800c3a00  mov     [rbp+0C0h+newString], r13
0x1800c3a04  test    r14, r14
0x1800c3a07  jz      short loc_1800C3A16
0x1800c3a09  lea     rdx, [rbp+0C0h+newString]; newString
0x1800c3a0d  mov     rcx, r14; string
0x1800c3a10  call    cs:__imp_WindowsDuplicateString
0x1800c3a16  mov     rbx, [rsp+1C0h+var_150]
0x1800c3a1b  add     rbx, 0FFFFFFFFFFFFFF78h
0x1800c3a22  mov     [rsp+1C0h+var_150], rbx
0x1800c3a27  lea     rcx, [rsp+1C0h+var_150]
0x1800c3a2c  call    ?InternalAddRef@?$ComPtr@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(void)
0x1800c3a31  nop
0x1800c3a32  mov     [rsp+1C0h+var_148], r15
0x1800c3a37  lea     rcx, [rsp+1C0h+var_148]
0x1800c3a3c  call    ?InternalAddRef@?$ComPtr@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(void)
0x1800c3a41  nop
0x1800c3a42  mov     [rbp+0C0h+var_108], rbx
0x1800c3a46  lea     rdx, [rsp+1C0h+var_150]
0x1800c3a4b  lea     rcx, [rbp+0C0h+var_100]
0x1800c3a4f  call    ??0?$ComPtr@VAppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>(Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl> &&)
0x1800c3a54  lea     rdx, [rsp+1C0h+var_148]
0x1800c3a59  lea     rcx, [rbp+0C0h+var_F8]
0x1800c3a5d  call    ??0?$ComPtr@VAppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>(Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl> &&)
0x1800c3a62  mov     rcx, [rbp+0C0h+var_140]
0x1800c3a66  mov     [rbp+0C0h+var_F0], rcx
0x1800c3a6a  lea     rcx, [rbp+0C0h+var_F0]
0x1800c3a6e  call    ?InternalAddRef@?$ComPtr@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(void)
0x1800c3a73  mov     [rbp+0C0h+var_110], r13
0x1800c3a77  mov     [rbp+0C0h+var_E8], rsi
0x1800c3a7b  mov     al, [rsp+1C0h+var_160]
0x1800c3a7f  mov     [rbp+0C0h+var_E0], al
0x1800c3a82  mov     rax, [rbp+0C0h+newString]
0x1800c3a86  mov     [rbp+0C0h+var_D8], rax
0x1800c3a8a  mov     qword ptr [rbp+0C0h+var_128], 2
0x1800c3a92  mov     dword ptr [rbp+0C0h+var_128+8], r13d
0x1800c3a96  lea     r9, [rbp+0C0h+var_108]
0x1800c3a9a  mov     rdx, r12
0x1800c3a9d  lea     rcx, [rbp+0C0h+var_128]
0x1800c3aa1  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CMarshaledInterfaceResult_Windows__ApplicationModel__Store__Preview__InstallControl__IAppInstallItem__Windows__ApplicationModel__Store__Preview__InstallControl__AppInstallItem___Windows__Internal__ComTaskPoolHandler__lambda_371a52f92a59bb61ede4865a021f8944___
0x1800c3aa6  mov     edi, eax
0x1800c3aa8  lea     rcx, [rbp+0C0h+var_108]
0x1800c3aac  call    _lambda_7d4e25090a3a4b87115c2ebaa24685ac_____lambda_7d4e25090a3a4b87115c2ebaa24685ac_
0x1800c3ab1  nop
0x1800c3ab2  lea     rcx, [rsp+1C0h+var_148]
0x1800c3ab7  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c3abc  nop
0x1800c3abd  lea     rcx, [rsp+1C0h+var_150]
0x1800c3ac2  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c3ac7  mov     rsi, r13
0x1800c3aca  mov     rbx, r13
0x1800c3acd  test    edi, edi
0x1800c3acf  jns     short loc_1800C3B37
0x1800c3ad1  xor     edx, edx; length
0x1800c3ad3  mov     rcx, [rbp+0C0h+var_130]; string
0x1800c3ad7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c3add  mov     rbx, rax
0x1800c3ae0  mov     ecx, [rsp+1C0h+var_15C]
0x1800c3ae4  call    ?IdTypeName@AppId@@SAPEBGW4Type@1@@Z; AppId::IdTypeName(AppId::Type)
0x1800c3ae9  lea     rdx, [rbp+0C0h+var_D0]
0x1800c3aed  mov     [rsp+1C0h+var_170], rdx
0x1800c3af2  mov     [rsp+1C0h+var_178], rbx
0x1800c3af7  mov     [rsp+1C0h+var_180], rax
0x1800c3afc  mov     [rsp+1C0h+var_188], r13; unsigned __int16 *
0x1800c3b01  mov     [rsp+1C0h+var_190], r13; char *
0x1800c3b06  lea     rax, aInitialization_10; "initialization failed: %s = %s, CV = %h"...
0x1800c3b0d  mov     [rsp+1C0h+var_198], rax; unsigned __int16 *
0x1800c3b12  mov     [rsp+1C0h+var_1A0], edi; int
0x1800c3b16  lea     r9, aWindowsApplica_10; "Windows::ApplicationModel::Store::Previ"...
0x1800c3b1d  mov     r8d, 1CDCh; unsigned int
0x1800c3b23  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c3b2a  mov     ecx, 1; unsigned int
0x1800c3b2f  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800c3b34  mov     rbx, rsi
0x1800c3b37  lea     rcx, [rbp+0C0h+var_140]
0x1800c3b3b  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c3b40  nop
0x1800c3b41  test    rbx, rbx
0x1800c3b44  jz      short loc_1800C3B4F
0x1800c3b46  mov     rcx, rbx; this
0x1800c3b49  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x1800c3b4e  nop
0x1800c3b4f  mov     rcx, [rsp+1C0h+string]; string
0x1800c3b54  call    cs:__imp_WindowsDeleteString
0x1800c3b5a  mov     eax, edi
0x1800c3b5c  jmp     short loc_1800C3B63
0x1800c3b5e  mov     eax, 80070057h
0x1800c3b63  mov     rcx, [rbp+0C0h+var_40]
0x1800c3b6a  xor     rcx, rsp; StackCookie
0x1800c3b6d  call    __security_check_cookie
0x1800c3b72  mov     rbx, [rsp+1C0h+arg_0]
0x1800c3b7a  add     rsp, 190h
0x1800c3b81  pop     r15
0x1800c3b83  pop     r14
0x1800c3b85  pop     r13
0x1800c3b87  pop     r12
0x1800c3b89  pop     rdi
0x1800c3b8a  pop     rsi
0x1800c3b8b  pop     rbp
0x1800c3b8c  retn
0x1800c3b8d  mov     r9d, eax; char *
0x1800c3b90  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c3b97  mov     edx, 1C9Ah; void *
0x1800c3b9c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
