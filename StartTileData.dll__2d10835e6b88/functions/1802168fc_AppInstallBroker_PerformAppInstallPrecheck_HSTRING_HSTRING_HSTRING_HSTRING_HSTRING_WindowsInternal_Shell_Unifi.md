# AppInstallBroker::PerformAppInstallPrecheck(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::EntitlementOptions,ContentManagement::IAppManager *)

- ea: `0x1802168fc`
- end: `0x180216f79`
- name: `?PerformAppInstallPrecheck@AppInstallBroker@@AEAAJPEAUHSTRING__@@0000W4EntitlementOptions@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@PEAUIAppManager@ContentManagement@@@Z`
- size: `1661`
- prototype: `int __high(HSTRING, HSTRING, HSTRING, HSTRING, HSTRING, enum WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::EntitlementOptions, struct ContentManagement::IAppManager *)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180215884`
- `0x180216f80`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x1801bdff4`
- `0x180201e50`
- `0x18020ea0c`
- `0x18020eab0`
- `0x18020fcb0`
- `0x180210394`
- `0x180210840`
- `0x1802108a8`
- `0x180210944`
- `0x18021300c`
- `0x180214f40`
- `0x180216498`
- `0x1802168fc`
- `0x1802181ac`
- `0x180218444`
- `0x180218dec`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216a8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216a9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216cbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216ccd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216e3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216e53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216ed0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216ee0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216f30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216f40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216a8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216a9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216cbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216ccd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216e3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216e53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216ed0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216ee0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216f30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216f40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180216960`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021696e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021697c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021698a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021699a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180216960`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021696e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021697c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021698a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021699a`

## string_xrefs

- `0x180216a28`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x180216adc`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x180216bcd`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x180216c41`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x180216e1f`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x180216f0e`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x1802169a3`: `PreCheckForAppInstallation`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppInstallBroker::PerformAppInstallPrecheck(
        AppInstallBroker *a1,
        HSTRING a2,
        HSTRING a3,
        HSTRING a4,
        HSTRING string,
        HSTRING a6,
        int a7,
        __int64 a8)
{
  const unsigned __int16 *StringRawBuffer; // r15
  const unsigned __int16 *v11; // r14
  const unsigned __int16 *v12; // rsi
  const unsigned __int16 *v13; // rdi
  const unsigned __int16 *v14; // rbx
  int v15; // eax
  int v16; // ebx
  __int64 v17; // r9
  __int64 v18; // rdx
  int v19; // eax
  AppInstallBroker *v20; // rsi
  int ContentIdAndKeyIdFromProductId; // eax
  AppInstallBroker *v22; // rcx
  int LicenseSatisfactionResult; // eax
  unsigned __int64 v24; // r9
  __int64 v25; // rdx
  int v26; // eax
  struct Windows::ApplicationModel::Store::LicenseManagement::ILicenseSatisfactionResult *v27; // rdi
  __int64 (__fastcall *v28)(struct Windows::ApplicationModel::Store::LicenseManagement::ILicenseSatisfactionResult *, AppInstallBroker **); // rbx
  int v29; // eax
  __int64 v30; // r9
  __int64 v31; // rdx
  AppInstallBroker *v32; // rbx
  __int64 (__fastcall *v33)(AppInstallBroker *, HSTRING, HSTRING *); // rdi
  int IsStoreAppFree; // eax
  __int64 v35; // rdx
  __int64 v36; // r9
  HSTRING v37; // r15
  HSTRING v38; // rsi
  int v39; // edi
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  char v43[8]; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v44; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v45; // [rsp+50h] [rbp-B0h] BYREF
  bool v46; // [rsp+58h] [rbp-A8h] BYREF
  char v47; // [rsp+59h] [rbp-A7h] BYREF
  char v48; // [rsp+5Ah] [rbp-A6h] BYREF
  unsigned __int8 v49[5]; // [rsp+5Bh] [rbp-A5h] BYREF
  struct Windows::ApplicationModel::Store::LicenseManagement::ILicenseSatisfactionResult *v50; // [rsp+60h] [rbp-A0h] BYREF
  AppInstallBroker *v51; // [rsp+68h] [rbp-98h] BYREF
  HSTRING v52; // [rsp+70h] [rbp-90h] BYREF
  HSTRING v53; // [rsp+78h] [rbp-88h] BYREF
  char *v54; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v55; // [rsp+88h] [rbp-78h]
  HSTRING v56; // [rsp+90h] [rbp-70h]
  _QWORD v57[42]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  v56 = a4;
  v55 = a3;
  v51 = a1;
  v52 = string;
  v53 = a6;
  StringRawBuffer = WindowsGetStringRawBuffer(a4, 0);
  v11 = WindowsGetStringRawBuffer(a3, 0);
  v12 = WindowsGetStringRawBuffer(a2, 0);
  v13 = WindowsGetStringRawBuffer(string, 0);
  v14 = WindowsGetStringRawBuffer(a6, 0);
  wil::ActivityBase<ShellAppInstallationTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ShellAppInstallationTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v57);
  v57[0] = &AppInstallationTelemetry::PreCheckForAppInstallation::`vftable';
  AppInstallationTelemetry::PreCheckForAppInstallation::StartActivity(
    (AppInstallationTelemetry::PreCheckForAppInstallation *)v57,
    v14,
    v13,
    v12,
    v11,
    StringRawBuffer);
  v43[0] = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)a8 + 56LL))(a8, a2, v43);
  v16 = v15;
  if ( v15 >= 0 )
  {
    if ( !v43[0] )
    {
      AppInstallationTelemetry::PreCheckForAppInstallation::AppNotAllowedToInstall((AppInstallationTelemetry::PreCheckForAppInstallation *)v57);
      v18 = 617;
LABEL_5:
      v16 = -2147467260;
      v17 = 2147500036LL;
      goto LABEL_6;
    }
    v47 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)a8 + 48LL))(a8, &v47);
    v16 = v19;
    if ( v19 < 0 )
    {
      v17 = (unsigned int)v19;
      v18 = 626;
      goto LABEL_6;
    }
    if ( v47 )
    {
      AppInstallationTelemetry::PreCheckForAppInstallation::StoreBlockedByPolicy((AppInstallationTelemetry::PreCheckForAppInstallation *)v57);
      v18 = 631;
      goto LABEL_5;
    }
    v44 = 0;
    v45 = 0;
    WindowsDeleteString(0);
    v45 = 0;
    WindowsDeleteString(v44);
    v44 = 0;
    v20 = v51;
    ContentIdAndKeyIdFromProductId = AppInstallBroker::GetContentIdAndKeyIdFromProductId(v51, a2, v52, &v44, &v45);
    v16 = ContentIdAndKeyIdFromProductId;
    if ( ContentIdAndKeyIdFromProductId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x27C,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
        (const char *)(unsigned int)ContentIdAndKeyIdFromProductId,
        v42);
LABEL_59:
      WindowsDeleteString(v45);
      v45 = 0;
      WindowsDeleteString(v44);
      goto LABEL_60;
    }
    v50 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    LicenseSatisfactionResult = AppInstallBroker::GetLicenseSatisfactionResult(v22, v44, v45, &v50);
    v16 = LicenseSatisfactionResult;
    if ( LicenseSatisfactionResult < 0 )
    {
      v24 = (unsigned int)LicenseSatisfactionResult;
      v25 = 639;
LABEL_57:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
        (const char *)v24,
        v42);
      goto LABEL_58;
    }
    LODWORD(v54) = 0;
    v26 = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::Store::LicenseManagement::ILicenseSatisfactionResult *, char **))(*(_QWORD *)v50 + 56LL))(
            v50,
            &v54);
    v16 = v26;
    if ( v26 < 0 )
    {
      v24 = (unsigned int)v26;
      v25 = 642;
      goto LABEL_57;
    }
    v16 = (int)v54;
    if ( (int)v54 < 0 )
    {
      if ( (_DWORD)v54 != -2143322101 && (unsigned int)((_DWORD)v54 + 2143322111) > 1 && (_DWORD)v54 != -2143318016 )
      {
        v25 = 663;
LABEL_56:
        v24 = (unsigned int)v16;
        goto LABEL_57;
      }
LABEL_41:
      if ( a7 )
      {
        AppInstallationTelemetry::PreCheckForAppInstallation::AttemptEntitlement((AppInstallationTelemetry::PreCheckForAppInstallation *)v57);
        v46 = a7 == 1;
        v42 = 0;
        v37 = v53;
        v38 = v55;
        v39 = (*(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, HSTRING))(*(_QWORD *)a8 + 80LL))(a8, a2, v55, v53);
        LODWORD(v53) = v39;
        if ( v39 < 0 )
        {
          if ( a7 == 1 || (a7 & 2) == 0 )
          {
            AppInstallationTelemetry::PreCheckForAppInstallation::EntitlementFailed<long &,bool const &>(
              v57,
              &v53,
              &v46);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2D0,
              (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
              (const char *)(unsigned int)v39,
              0);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
            WindowsDeleteString(v45);
            v45 = 0;
            WindowsDeleteString(v44);
            v44 = 0;
            v16 = v39;
            goto LABEL_61;
          }
          v42 = 0;
          v16 = (*(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, HSTRING))(*(_QWORD *)a8 + 80LL))(a8, a2, v38, v37);
          LODWORD(v53) = v16;
          if ( v16 < 0 )
          {
            v46 = 1;
            AppInstallationTelemetry::PreCheckForAppInstallation::EntitlementFailed<long &,bool>(v57, &v53, &v46);
            v25 = 714;
            goto LABEL_56;
          }
        }
      }
      else
      {
        v38 = v55;
      }
      v16 = (*(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, char *))(*(_QWORD *)a8 + 64LL))(a8, a2, v38, v43);
      if ( (int)(v16 + 0x80000000) < 0 || v16 == -2145123271 )
      {
        if ( v43[0] && v16 != -2145123271 )
        {
          wil::ActivityBase<ShellAppInstallationTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
            v57,
            0);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
          WindowsDeleteString(v45);
          v45 = 0;
          WindowsDeleteString(v44);
          v44 = 0;
          AppInstallationTelemetry::PreCheckForAppInstallation::~PreCheckForAppInstallation((AppInstallationTelemetry::PreCheckForAppInstallation *)v57);
          return 0;
        }
        AppInstallationTelemetry::PreCheckForAppInstallation::AppIsNotApplicable((AppInstallationTelemetry::PreCheckForAppInstallation *)v57);
        v16 = -2147467260;
        v25 = 738;
      }
      else
      {
        v25 = 732;
      }
      goto LABEL_56;
    }
    v51 = 0;
    v27 = v50;
    v28 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Store::LicenseManagement::ILicenseSatisfactionResult *, AppInstallBroker **))(*(_QWORD *)v50 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    v29 = v28(v27, &v51);
    v16 = v29;
    if ( v29 < 0 )
    {
      v30 = (unsigned int)v29;
      v31 = 670;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v31,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
        (const char *)v30,
        v42);
LABEL_25:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
LABEL_58:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
      goto LABEL_59;
    }
    v32 = v51;
    if ( !v51 )
    {
      v16 = -2147023728;
      v30 = 2147943568LL;
      v31 = 671;
      goto LABEL_24;
    }
    v52 = 0;
    v33 = *(__int64 (__fastcall **)(AppInstallBroker *, HSTRING, HSTRING *))(*(_QWORD *)v51 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    IsStoreAppFree = v33(v32, v44, &v52);
    v16 = IsStoreAppFree;
    if ( IsStoreAppFree >= 0 )
    {
      v48 = 0;
      IsStoreAppFree = (*(__int64 (__fastcall **)(HSTRING, char *))(*(_QWORD *)v52 + 96LL))(v52, &v48);
      v16 = IsStoreAppFree;
      if ( IsStoreAppFree >= 0 )
      {
        if ( v48 )
        {
          wil::ActivityBase<ShellAppInstallationTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
            v57,
            0);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
          WindowsDeleteString(v45);
          v45 = 0;
          WindowsDeleteString(v44);
          v16 = 0;
LABEL_60:
          v44 = 0;
          goto LABEL_61;
        }
        v49[0] = 0;
        IsStoreAppFree = AppInstallBroker::IsStoreAppFree(v20, a2, v49);
        v16 = IsStoreAppFree;
        if ( IsStoreAppFree >= 0 )
        {
          if ( v49[0] )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
            goto LABEL_41;
          }
          AppInstallationTelemetry::PreCheckForAppInstallation::LicenseNotSatisfied((AppInstallationTelemetry::PreCheckForAppInstallation *)v57);
          v16 = -2147467260;
          v36 = 2147500036LL;
          v35 = 692;
          goto LABEL_31;
        }
        v35 = 687;
      }
      else
      {
        v35 = 677;
      }
    }
    else
    {
      v35 = 674;
    }
    v36 = (unsigned int)IsStoreAppFree;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
      (const char *)v36,
      v42);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    goto LABEL_25;
  }
  v17 = (unsigned int)v15;
  v18 = 613;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v18,
    (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
    (const char *)v17,
    v41);
LABEL_61:
  AppInstallationTelemetry::PreCheckForAppInstallation::~PreCheckForAppInstallation((AppInstallationTelemetry::PreCheckForAppInstallation *)v57);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1802168fc  push    rbp
0x1802168fe  push    rbx
0x1802168ff  push    rsi
0x180216900  push    rdi
0x180216901  push    r12
0x180216903  push    r13
0x180216905  push    r14
0x180216907  push    r15
0x180216909  lea     rbp, [rsp-108h]
0x180216911  sub     rsp, 208h
0x180216918  mov     rax, cs:__security_cookie
0x18021691f  xor     rax, rsp
0x180216922  mov     [rbp+140h+var_50], rax
0x180216929  mov     [rbp+140h+var_1B0], r9
0x18021692d  mov     rbx, r8
0x180216930  mov     [rbp+140h+var_1B8], rbx
0x180216934  mov     r13, rdx
0x180216937  mov     [rsp+240h+var_1D8], rcx
0x18021693c  mov     rdi, [rbp+140h+string]
0x180216943  mov     [rsp+240h+var_1D0], rdi
0x180216948  mov     rcx, [rbp+140h+arg_28]
0x18021694f  mov     [rsp+240h+var_1C8], rcx
0x180216954  mov     r12, [rbp+140h+arg_38]
0x18021695b  xor     edx, edx; length
0x18021695d  mov     rcx, r9; string
0x180216960  call    cs:__imp_WindowsGetStringRawBuffer
0x180216966  mov     r15, rax
0x180216969  xor     edx, edx; length
0x18021696b  mov     rcx, rbx; string
0x18021696e  call    cs:__imp_WindowsGetStringRawBuffer
0x180216974  mov     r14, rax
0x180216977  xor     edx, edx; length
0x180216979  mov     rcx, r13; string
0x18021697c  call    cs:__imp_WindowsGetStringRawBuffer
0x180216982  mov     rsi, rax
0x180216985  xor     edx, edx; length
0x180216987  mov     rcx, rdi; string
0x18021698a  call    cs:__imp_WindowsGetStringRawBuffer
0x180216990  mov     rdi, rax
0x180216993  xor     edx, edx; length
0x180216995  mov     rcx, [rsp+240h+var_1C8]; string
0x18021699a  call    cs:__imp_WindowsGetStringRawBuffer
0x1802169a0  mov     rbx, rax
0x1802169a3  lea     rdx, aPrecheckforapp; "PreCheckForAppInstallation"
0x1802169aa  lea     rcx, [rbp+140h+var_1A0]; struct wil::details::IFailureCallback *
0x1802169ae  call    ??0?$ActivityBase@VShellAppInstallationTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ShellAppInstallationTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ShellAppInstallationTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1802169b3  lea     rax, ??_7PreCheckForAppInstallation@AppInstallationTelemetry@@6B@; const AppInstallationTelemetry::PreCheckForAppInstallation::`vftable'
0x1802169ba  mov     [rbp+140h+var_1A0], rax
0x1802169be  mov     [rsp+240h+var_218], r15; unsigned __int16 *
0x1802169c3  mov     [rsp+240h+var_220], r14; int
0x1802169c8  mov     r9, rsi; unsigned __int16 *
0x1802169cb  mov     r8, rdi; unsigned __int16 *
0x1802169ce  mov     rdx, rbx; unsigned __int16 *
0x1802169d1  lea     rcx, [rbp+140h+var_1A0]; this
0x1802169d5  call    ?StartActivity@PreCheckForAppInstallation@AppInstallationTelemetry@@QEAAXPEBG0000@Z; AppInstallationTelemetry::PreCheckForAppInstallation::StartActivity(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1802169da  nop
0x1802169db  xor     r14d, r14d
0x1802169de  mov     [rsp+240h+var_200], r14b
0x1802169e3  mov     rax, [r12]
0x1802169e7  lea     r8, [rsp+240h+var_200]
0x1802169ec  mov     rdx, r13
0x1802169ef  mov     rcx, r12
0x1802169f2  mov     rax, [rax+38h]
0x1802169f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802169fb  mov     ebx, eax
0x1802169fd  test    eax, eax
0x1802169ff  jns     short loc_180216A0B
0x180216a01  mov     r9d, eax
0x180216a04  mov     edx, 265h
0x180216a09  jmp     short loc_180216A28
0x180216a0b  cmp     [rsp+240h+var_200], r14b
0x180216a10  jnz     short loc_180216A40
0x180216a12  lea     rcx, [rbp+140h+var_1A0]; this
0x180216a16  call    ?AppNotAllowedToInstall@PreCheckForAppInstallation@AppInstallationTelemetry@@QEAAXXZ; AppInstallationTelemetry::PreCheckForAppInstallation::AppNotAllowedToInstall(void)
0x180216a1b  mov     edx, 269h; void *
0x180216a20  mov     ebx, 80004004h
0x180216a25  mov     r9d, ebx; char *
0x180216a28  lea     r8, aShellcommonShe_48; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180216a2f  mov     rcx, [rbp+148h]; this
0x180216a36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180216a3b  jmp     loc_180216F4B
0x180216a40  mov     [rsp+240h+var_1E7], r14b
0x180216a45  mov     rax, [r12]
0x180216a49  lea     rdx, [rsp+240h+var_1E7]
0x180216a4e  mov     rcx, r12
0x180216a51  mov     rax, [rax+30h]
0x180216a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216a5a  mov     ebx, eax
0x180216a5c  test    eax, eax
0x180216a5e  jns     short loc_180216A6A
0x180216a60  mov     r9d, eax
0x180216a63  mov     edx, 272h
0x180216a68  jmp     short loc_180216A28
0x180216a6a  cmp     [rsp+240h+var_1E7], r14b
0x180216a6f  jz      short loc_180216A81
0x180216a71  lea     rcx, [rbp+140h+var_1A0]; this
0x180216a75  call    ?StoreBlockedByPolicy@PreCheckForAppInstallation@AppInstallationTelemetry@@QEAAXXZ; AppInstallationTelemetry::PreCheckForAppInstallation::StoreBlockedByPolicy(void)
0x180216a7a  mov     edx, 277h
0x180216a7f  jmp     short loc_180216A20
0x180216a81  mov     [rsp+240h+var_1F8], r14
0x180216a86  mov     [rsp+240h+var_1F0], r14
0x180216a8b  xor     ecx, ecx; string
0x180216a8d  call    cs:__imp_WindowsDeleteString
0x180216a93  mov     [rsp+240h+var_1F0], r14
0x180216a98  mov     rcx, [rsp+240h+var_1F8]; string
0x180216a9d  call    cs:__imp_WindowsDeleteString
0x180216aa3  mov     [rsp+240h+var_1F8], r14
0x180216aa8  lea     rax, [rsp+240h+var_1F0]
0x180216aad  mov     [rsp+240h+var_220], rax; int
0x180216ab2  lea     r9, [rsp+240h+var_1F8]; HSTRING *
0x180216ab7  mov     r8, [rsp+240h+var_1D0]; HSTRING
0x180216abc  mov     rdx, r13; HSTRING
0x180216abf  mov     rsi, [rsp+240h+var_1D8]
0x180216ac4  mov     rcx, rsi; this
0x180216ac7  call    ?GetContentIdAndKeyIdFromProductId@AppInstallBroker@@AEAAJPEAUHSTRING__@@0PEAPEAU2@1@Z; AppInstallBroker::GetContentIdAndKeyIdFromProductId(HSTRING__ *,HSTRING__ *,HSTRING__ * *,HSTRING__ * *)
0x180216acc  mov     ebx, eax
0x180216ace  test    eax, eax
0x180216ad0  jns     short loc_180216AF2
0x180216ad2  mov     rcx, [rbp+148h]; this
0x180216ad9  mov     r9d, eax; char *
0x180216adc  lea     r8, aShellcommonShe_48; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180216ae3  mov     edx, 27Ch; void *
0x180216ae8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180216aed  jmp     loc_180216F2B
0x180216af2  mov     [rsp+240h+var_1E0], r14
0x180216af7  lea     rcx, [rsp+240h+var_1E0]
0x180216afc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180216b01  lea     r9, [rsp+240h+var_1E0]; struct Windows::ApplicationModel::Store::LicenseManagement::ILicenseSatisfactionResult **
0x180216b06  mov     r8, [rsp+240h+var_1F0]; HSTRING
0x180216b0b  mov     rdx, [rsp+240h+var_1F8]; HSTRING
0x180216b10  call    ?GetLicenseSatisfactionResult@AppInstallBroker@@AEAAJPEAUHSTRING__@@0PEAPEAUILicenseSatisfactionResult@LicenseManagement@Store@ApplicationModel@Windows@@@Z; AppInstallBroker::GetLicenseSatisfactionResult(HSTRING__ *,HSTRING__ *,Windows::ApplicationModel::Store::LicenseManagement::ILicenseSatisfactionResult * *)
0x180216b15  mov     ebx, eax
0x180216b17  test    eax, eax
0x180216b19  jns     short loc_180216B28
0x180216b1b  mov     r9d, eax
0x180216b1e  mov     edx, 27Fh
0x180216b23  jmp     loc_180216F0E
0x180216b28  mov     dword ptr [rbp+140h+var_1C0], r14d
0x180216b2c  mov     rcx, [rsp+240h+var_1E0]
0x180216b31  mov     rax, [rcx]
0x180216b34  lea     rdx, [rbp+140h+var_1C0]
0x180216b38  mov     rax, [rax+38h]
0x180216b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216b41  mov     ebx, eax
0x180216b43  test    eax, eax
0x180216b45  jns     short loc_180216B54
0x180216b47  mov     r9d, eax
0x180216b4a  mov     edx, 282h
0x180216b4f  jmp     loc_180216F0E
0x180216b54  mov     ebx, dword ptr [rbp+140h+var_1C0]
0x180216b57  test    ebx, ebx
0x180216b59  jns     short loc_180216B94
0x180216b5b  cmp     ebx, 803F800Bh
0x180216b61  jz      loc_180216D36
0x180216b67  lea     eax, [rbx+7FC07FFFh]
0x180216b6d  cmp     eax, 1
0x180216b70  jbe     loc_180216D36
0x180216b76  cmp     ebx, 803F9000h
0x180216b7c  jz      loc_180216D36
0x180216b82  test    ebx, ebx
0x180216b84  jns     loc_180216F21
0x180216b8a  mov     edx, 297h
0x180216b8f  jmp     loc_180216F0B
0x180216b94  mov     [rsp+240h+var_1D8], r14
0x180216b99  mov     rdi, [rsp+240h+var_1E0]
0x180216b9e  mov     rax, [rdi]
0x180216ba1  mov     rbx, [rax+30h]
0x180216ba5  lea     rcx, [rsp+240h+var_1D8]
0x180216baa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180216baf  lea     rdx, [rsp+240h+var_1D8]
0x180216bb4  mov     rcx, rdi
0x180216bb7  mov     rax, rbx
0x180216bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216bbf  mov     ebx, eax
0x180216bc1  test    eax, eax
0x180216bc3  jns     short loc_180216BEF
0x180216bc5  mov     r9d, eax; char *
0x180216bc8  mov     edx, 29Eh; void *
0x180216bcd  lea     r8, aShellcommonShe_48; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180216bd4  mov     rcx, [rbp+148h]; this
0x180216bdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180216be0  lea     rcx, [rsp+240h+var_1D8]
0x180216be5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180216bea  jmp     loc_180216F21
0x180216bef  mov     rbx, [rsp+240h+var_1D8]
0x180216bf4  test    rbx, rbx
0x180216bf7  jnz     short loc_180216C08
0x180216bf9  mov     ebx, 80070490h
0x180216bfe  mov     r9d, ebx
0x180216c01  mov     edx, 29Fh
0x180216c06  jmp     short loc_180216BCD
0x180216c08  mov     [rsp+240h+var_1D0], r14
0x180216c0d  mov     rax, [rbx]
0x180216c10  mov     rdi, [rax+30h]
0x180216c14  lea     rcx, [rsp+240h+var_1D0]
0x180216c19  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180216c1e  lea     r8, [rsp+240h+var_1D0]
0x180216c23  mov     rdx, [rsp+240h+var_1F8]
0x180216c28  mov     rcx, rbx
0x180216c2b  mov     rax, rdi
0x180216c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216c33  mov     ebx, eax
0x180216c35  test    eax, eax
0x180216c37  jns     short loc_180216C60
0x180216c39  mov     edx, 2A2h; void *
0x180216c3e  mov     r9d, eax; char *
0x180216c41  lea     r8, aShellcommonShe_48; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180216c48  mov     rcx, [rbp+148h]; this
0x180216c4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180216c54  lea     rcx, [rsp+240h+var_1D0]
0x180216c59  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180216c5e  jmp     short loc_180216BE0
0x180216c60  mov     [rsp+240h+var_1E6], r14b
0x180216c65  mov     rcx, [rsp+240h+var_1D0]
0x180216c6a  mov     rax, [rcx]
0x180216c6d  lea     rdx, [rsp+240h+var_1E6]
0x180216c72  mov     rax, [rax+60h]
0x180216c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216c7b  mov     ebx, eax
0x180216c7d  test    eax, eax
0x180216c7f  jns     short loc_180216C88
0x180216c81  mov     edx, 2A5h
0x180216c86  jmp     short loc_180216C3E
0x180216c88  cmp     [rsp+240h+var_1E6], r14b
0x180216c8d  jz      short loc_180216CDB
0x180216c8f  xor     edx, edx
0x180216c91  lea     rcx, [rbp+140h+var_1A0]
0x180216c95  call    ?Stop@?$ActivityBase@VShellAppInstallationTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ShellAppInstallationTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180216c9a  lea     rcx, [rsp+240h+var_1D0]
0x180216c9f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180216ca4  lea     rcx, [rsp+240h+var_1D8]
0x180216ca9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180216cae  lea     rcx, [rsp+240h+var_1E0]
0x180216cb3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180216cb8  mov     rcx, [rsp+240h+var_1F0]; string
0x180216cbd  call    cs:__imp_WindowsDeleteString
0x180216cc3  mov     [rsp+240h+var_1F0], r14
0x180216cc8  mov     rcx, [rsp+240h+var_1F8]; string
0x180216ccd  call    cs:__imp_WindowsDeleteString
0x180216cd3  mov     ebx, r14d
0x180216cd6  jmp     loc_180216F46
0x180216cdb  mov     [rsp+240h+var_1E5], r14b
0x180216ce0  lea     r8, [rsp+240h+var_1E5]; unsigned __int8 *
0x180216ce5  mov     rdx, r13; HSTRING
0x180216ce8  mov     rcx, rsi; this
0x180216ceb  call    ?IsStoreAppFree@AppInstallBroker@@AEAAJPEAUHSTRING__@@PEAE@Z; AppInstallBroker::IsStoreAppFree(HSTRING__ *,uchar *)
0x180216cf0  mov     ebx, eax
0x180216cf2  test    eax, eax
0x180216cf4  jns     short loc_180216D00
0x180216cf6  mov     edx, 2AFh
0x180216cfb  jmp     loc_180216C3E
0x180216d00  cmp     [rsp+240h+var_1E5], r14b
0x180216d05  jnz     short loc_180216D22
0x180216d07  lea     rcx, [rbp+140h+var_1A0]; this
0x180216d0b  call    ?LicenseNotSatisfied@PreCheckForAppInstallation@AppInstallationTelemetry@@QEAAXXZ; AppInstallationTelemetry::PreCheckForAppInstallation::LicenseNotSatisfied(void)
0x180216d10  mov     ebx, 80004004h
0x180216d15  mov     r9d, ebx
0x180216d18  mov     edx, 2B4h
0x180216d1d  jmp     loc_180216C41
0x180216d22  lea     rcx, [rsp+240h+var_1D0]
0x180216d27  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180216d2c  lea     rcx, [rsp+240h+var_1D8]
0x180216d31  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180216d36  mov     ebx, [rbp+140h+arg_30]
0x180216d3c  test    ebx, ebx
0x180216d3e  jz      loc_180216E69
0x180216d44  lea     rcx, [rbp+140h+var_1A0]; this
0x180216d48  call    ?AttemptEntitlement@PreCheckForAppInstallation@AppInstallationTelemetry@@QEAAXXZ; AppInstallationTelemetry::PreCheckForAppInstallation::AttemptEntitlement(void)
0x180216d4d  cmp     ebx, 1
0x180216d50  setz    cl
0x180216d53  mov     [rsp+240h+var_1E8], cl
0x180216d57  mov     rax, [r12]
0x180216d5b  mov     r14, [rbp+140h+var_1B0]
0x180216d5f  mov     [rsp+240h+var_210], r14
0x180216d64  mov     byte ptr [rsp+240h+var_218], cl
0x180216d68  mov     [rsp+240h+var_220], 0; int
0x180216d71  mov     r15, [rsp+240h+var_1C8]
0x180216d76  mov     r9, r15
0x180216d79  mov     rsi, [rbp+140h+var_1B8]
0x180216d7d  mov     r8, rsi
0x180216d80  mov     rdx, r13
0x180216d83  mov     rcx, r12
0x180216d86  mov     rax, [rax+50h]
0x180216d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216d8f  mov     edi, eax
0x180216d91  mov     dword ptr [rsp+240h+var_1C8], eax
0x180216d95  test    eax, eax
0x180216d97  jns     loc_180216E6F
0x180216d9d  cmp     ebx, 1
0x180216da0  jz      short loc_180216E02
0x180216da2  test    bl, 2
0x180216da5  jz      short loc_180216E02
0x180216da7  mov     rax, [r12]
0x180216dab  mov     [rsp+240h+var_210], r14
0x180216db0  mov     byte ptr [rsp+240h+var_218], 1
0x180216db5  xor     r14d, r14d
0x180216db8  mov     [rsp+240h+var_220], r14
0x180216dbd  mov     r9, r15
0x180216dc0  mov     r8, rsi
0x180216dc3  mov     rdx, r13
  ... truncated ...
```
